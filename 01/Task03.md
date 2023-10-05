## Task 3

### Wykorzystanie kontenera IoC

1. Dodaj interfejsy dla rejestracji implementacji klas jako Transient, Scoped oraz Singleton.

```cs
  public interface IIocService
  {
     public Guid Guid { get; }
  }
  
  public interface IScopedService : IIocService
  {
  }
  
  public interface ISingletonService : IIocService
  {
  }
  
  public interface ITransientService : IIocService
  {
  }
```

2. Dodaj implementację, która implementuje te interfejsy.

```cs
  public class SomeService : ISingletonService, IScopedService, ITransientService
  {
	//Twoja implementacja
  }

```

3. Dodaj model widoku 

```cs
 public class IocTestViewModel
 {
    public Guid ScopedGuid1 { get; set; }
    public Guid ScopedGuid2 { get; set; }

    public Guid TransientGuid1 { get; set; }
    public Guid TransientGuid2 { get; set; }

    public Guid SingletonGuid1 { get; set; }
    public Guid SingletonGuid2 { get; set; }
 }
```

4. Dodaj kontroler, który jako konstrukor przyjmie po dwie instancje każdej z implementacji interfejsów. 

```cs
    public IoCController(IScopedService scopedService1, IScopedService scopedService2, ITransientService transientService1,
        ITransientService transientService2, ISingletonService singletonService1, ISingletonService singletonService2)
    {
        _scopedService1 = scopedService1;
        _scopedService2 = scopedService2;
        _transientService1 = transientService1;
        _transientService2 = transientService2;
        _singletonService1 = singletonService1;
        _singletonService2 = singletonService2;
    }
```

5. Stwórz metodę akcji, która przypisuje guid do każdej z właściwości w viewmodelu.

6. Stwórz widok, który wyświetli guidy w widoku