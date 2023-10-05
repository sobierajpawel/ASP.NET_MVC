## Task 2

### Utworzenie kontrolera oraz metod akcji wraz z widokami do operacji CRUD

1. Utwórz klasę viewmodelu, która będzie wyświetlana na widokach. 

2. Dodaj atrybuty odnoszące się do walidacji, wykorzystaj DisplayName.

```cs
[StringLength(50, MinimumLength = 5)]
[DisplayName("Nazwa produktu")]
[Required (ErrorMessage ="Pole jest wymagane")]
```

3. Zbuduj aplikacje CRUD, który będzie wykorzystywał klasę `ViewModel` jako model widoku dla każdego z widoków. 

4. Możesz wygenerować widoku przy wykorzystaniu scaffoldingu.

5. Stwórz kontrolery do obsługi - do mapowania obiektów możesz użyć własnej implementacji prostego mappera lub skorzystać z AutoMappera.
