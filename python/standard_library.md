# Python - Standard Library

## `dataclasses`

- Reduces boilerplate code
- Syntax

    ```python
    from dataclasses import dataclass
    from typing import ClassVar

    @dataclass
    class MyClass:
        foo: int
        bar: str = "Hello" # default value

        # Be careful with default mutable arguments
        # wrong_baz: list[int] = [] # NO!
        baz: list[int] = field(default_factory=list) # Correct!

        # Class variables
        class_var1 = 0.5 # don't annotate the field
        class_var2: ClassVar[float] = 0.5 
    ```

- `@dataclasses.dataclass` decorator adds the **special methods** `__init__()`, `__repr__()` and `__eq__()` to the class it decorates
    - arg `frozen=True` to get inmutable instances (i.e. read-only attributes)
- Useful functions
    - `dataclasses.astuple`
    - `dataclasses.asdict`
- References
    - [Youtube - Python dataclasses will save you HOURS, also featuring attrs - mCoding](https://youtu.be/vBH6GRJ1REM)
    - [Stack Overflow - Proper way to create class variable in Data Class](https://stackoverflow.com/a/61938635/5662304)


## `inspect`

- List functions inside class `MyClass`

    ```python
    import inspect
    
    inspect.getmembers(MyClass, inspect.isfunction)
    ```

