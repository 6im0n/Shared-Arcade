# Arcade Memo

## Project Overview:
This project involves developing game and graphical libraries in C++.

## Library Requirements:
- Each library must include:
    - A `load<_>Instance` function.
    - The function should return an `IGame` interface for game libraries or an `IGraphic` interface for graphical libraries.
    - The `load<_>Instance` function should take no parameters.

## Interface Definitions:
### IGame Interface:
```cpp
class IGame {
public:
    virtual ~IGame() {}
    // Define game-related methods here
};
```

### IGraphic Interface:
```cpp
class IGraphic {
public:
    virtual ~IGraphic() {}
    // Define graphical-related methods here
};
```

## Example `load<_>Instance` Function Prototypes:
```cpp
// Prototype for a game library
extern "C" std::unique_ptr<IGame> loadGameInstance();

// Prototype for a graphical library
extern "C" std::unique_ptr<IGraphic> loadGraphicInstance();
```

## Usage:
- Ensure that the `load<_>Instance` functions are implemented according to the specified requirements.
- **Please ensure that the `load<_>Instance` function is called inside your library loader to instantiate the appropriate interface.**

```cpp
// Load the instance of the library
dlsym(lib, "loadGameInstance");
dlsym(lib, "loadGraphicInstance");
```
this must be called to load the library.

## Conclusion:
Follow the provided structure and guidelines to develop libraries that conform to the project requirements. Ensure consistency and adherence to the defined interfaces.