# SparxECS
![NuGet Downloads](https://img.shields.io/nuget/dt/SparxECS) ![GitHub code size in bytes](https://img.shields.io/github/languages/code-size/josephheinz/SparxECS) ![GitHub License](https://img.shields.io/github/license/josephheinz/SparxECS) ![NuGet Version](https://img.shields.io/nuget/v/SparxECS) ![GitHub Issues or Pull Requests](https://img.shields.io/github/issues/josephheinz/SparxECS)

A lightweight, generic Entity Component System (ECS) library for C# projects.

---

## Overview

SparxECS is a simple and efficient ECS framework designed to help you manage entities and their components with minimal boilerplate and high performance. It supports:

- Dynamic entity creation and deletion
- Generic component registration and management
- Efficient querying for entities with single or multiple components
- Component cloning and entity duplication
- Internal reuse of entity IDs for memory efficiency

SparxECS is suitable for games, simulations, or any application requiring flexible, data-driven architecture.

---

## Features

- Register and manage components of any type
- Add, set, get, and remove components per entity
- Query entities with one or more components with optional filtering
- Clone entities and copy components
- Lightweight with minimal dependencies (.NET Standard 2.1+ compatible)
- Easy integration into existing projects

---

## Installation

Install via NuGet:

```bash
dotnet add package SparxECS
````

Or via the NuGet Package Manager:

Install-Package SparxECS

---

## Usage Example

```csharp
using SparxECS;

var ecs = new ECS();

// Register your components
ecs.RegisterComponent<Position>();
ecs.RegisterComponent<Velocity>();

// Create an entity
EntityID player = ecs.AddEntity();

// Add components
ecs.Add(player, new Position(10, 20));
ecs.Add(player, new Velocity(1, 0));

// Query entities with Position and Velocity components
foreach (var (pos, vel) in ecs.Query<Position, Velocity>())
{
    Console.WriteLine($"Entity Position: {pos}, Velocity: {vel}");
}
```

---

## Documentation

Full documentation and API references are available in the repository. Feel free to explore the source code and examples.

---

## Contributing

Contributions, issues, and feature requests are welcome!
Please feel free to check the [issues page](https://github.com/josephheinz/SparxECS/issues).

---

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

---

## Contact

Created by [Joseph Heinz](https://github.com/josephheinz).
Feel free to reach out for questions or collaboration.

