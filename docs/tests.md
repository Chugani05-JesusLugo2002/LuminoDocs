# **Pruebas**

## Estrategia

La herramienta utilizada para probar los distintos elementos que componen nuestra aplicación web, tanto su estructura como funcionamiento, es Pytest, un framework dedicado al uso de prueba unitarias para software de Python, junto a scripts generadores de datos de prueba proporcionados por nuestro docente con el uso de librerías como Faker y Baker.

## Casos

Algunos casos específicos a destacar pueden ser:

1. Que el modelo **Subject** tenga los campos requeridos: `code`, `name`, `teacher` y `students`.

```py
@pytest.mark.django_db
def test_subject_model_has_proper_fields():
    PROPER_FIELDS = ('code', 'name', 'teacher', 'students')
    for field in PROPER_FIELDS:
        assert (
            getattr(Subject, field) is not None
        ), f'El campo <{field}> no está en el modelo Subject.'
```

2. Que los modelos estén disponibles en la interfaz administrativa.

```py
@pytest.mark.django_db
def test_models_are_available_on_admin(admin_client):
    MODELS = ('subjects.Subject', 'subjects.Lesson', 'subjects.Enrollment', 'users.Profile')

    for model in MODELS:
        url_model_path = model.replace('.', '/').lower()
        url = f'/admin/{url_model_path}/'
        response = admin_client.get(url)
        assert response.status_code == 200, f'El modelo <{model}> no está habilitado en el admin.'
```

3. O algunos más extensos como el que comprueba que la página de **User Detail** contenga todos los elementos esperados de un usuario determinado.

```py
@pytest.mark.django_db
def test_user_detail_displays_all_elements(client, student, teacher):
    client.force_login(student)
    response = client.get(f'/users/{student.username}/')
    assert response.status_code == HTTPStatus.OK
    assertContains(response, f'{student.first_name} {student.last_name}')
    assertContains(response, 'Student')
    assertContains(response, student.email)
    assertContains(response, student.profile.bio)
    response_text = response.content.decode()
    # sorl-thumbnail creates this path for thumbnails
    assert re.search(r'<img.*?src="/media/cache.*?"', response_text)

    response = client.get(f'/users/{teacher.username}/')
    assert response.status_code == HTTPStatus.OK
    assertContains(response, 'Teacher')
```

## Cobertura 

Los tests cubren una variedad de puntos y elementos que se presentan (o deberían estar presente) en el código de nuestra aplicación, esto incluye:

- Los campos de los modelos
- La buena configuración de *Foreign Keys*
- El resultado de las vistas
- Redirecciones de las urls
- Que la autenticación se haya cumplido para la ejecución de ciertas acciones

## Automatización

Como se ha mencionado, se ha hecho uso de *scripts* encargados de generar datos para poblar la base de datos y ejecutar sobre ellos los tests preparados. Un ejemplo de un registro del modelo **User** es:

```json
{
  "model": "subjects.subject",
  "pk": 446,
  "fields": {
    "code": "AAB",
    "name": "First do exist whether",
    "teacher": 349
  }
},
```

Donde datos como `code` y `name` fueron generados a través de librerías de generación de datos como Faker y Baker.