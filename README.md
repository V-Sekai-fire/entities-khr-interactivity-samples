# KHR_interactivity Behavior Graph Samples

This repository contains sample KHR_interactivity behavior graph JSON files demonstrating various features and patterns of the KHR_interactivity extension.

## Overview

KHR_interactivity is a glTF extension from Khronos Group for encoding behavior graphs. These samples demonstrate standalone JSON behavior graphs that can be:

- Executed directly in custom runtimes (aria-gltf - interpreted)
- Compiled to RISC-V binaries and executed in libriscv (2.5-10x faster)
- Embedded in glTF assets (optional)
- Used as a pure intermediate representation

## Sample Files

### Basic Operations

- **`customEventsLoop.json`** - Demonstrates custom event sending and receiving with loop control
  - Uses `event/send` and `event/receive` operations
  - Shows flow control with `flow/branch` and conditional logic
  - Example of async event handling

- **`variableSetGetInterpolate.json`** - Demonstrates variable operations and interpolation
  - Uses `variable/get`, `variable/set`, and `variable/interpolate`
  - Shows lifecycle events (`event/onStart`, `event/onTick`)
  - Demonstrates math operations with variables

- **`pointerGetSet.json`** - Demonstrates glTF pointer operations
  - Uses `pointer/get` and `pointer/set` to access glTF node properties
  - Shows math operations on pointer values
  - Example of conditional logic based on pointer values

- **`pointerInterpolateSet.json`** - Demonstrates pointer interpolation
  - Uses `pointer/interpolate` for smooth transitions
  - Shows delay operations with `flow/setDelay`
  - Demonstrates pointer value manipulation

### Flow Control

- **`loopReEvaulation.json`** - Demonstrates loop re-evaluation patterns
  - Uses `flow/while` for conditional loops
  - Shows `flow/doN` for counted iterations
  - Demonstrates variable updates in loops

- **`setCancelDelay.json`** - Demonstrates delay and cancellation
  - Uses `flow/setDelay` and `flow/cancelDelay`
  - Shows `flow/sequence` for ordered execution
  - Demonstrates delay index tracking

### Math and Logic

- **`randomTest.json`** - Demonstrates random number generation
  - Uses `math/random` operation
  - Shows boolean logic with `math/and`, `math/not`, `math/eq`
  - Demonstrates conditional variable setting

### Error Handling

- **`unkownNodes.json`** - Demonstrates handling of unknown/extension nodes
  - Shows custom extension nodes (`KHR_fakity_fake_fake`)
  - Demonstrates graceful handling of unsupported operations
  - Example of extension node definitions

## Structure

Each sample JSON file follows the KHR_interactivity behavior graph structure:

```json
{
  "declarations": [...],  // Node type declarations
  "nodes": [...],        // Behavior graph nodes
  "variables": [...],    // Graph variables
  "events": [...],       // Custom events
  "types": [...]         // Type definitions
}
```

## Node Operations

These samples demonstrate various node operation categories:

### Math Operations
- Arithmetic: `math/add`, `math/sub`, `math/multiply`, `math/divide`
- Comparison: `math/eq`, `math/lt`, `math/gt`
- Functions: `math/abs`, `math/length`, `math/random`

### Flow Control
- Loops: `flow/while`, `flow/doN`, `flow/forLoop`
- Conditionals: `flow/branch`, `flow/switch`
- Sequencing: `flow/sequence`, `flow/waitAll`
- Delays: `flow/setDelay`, `flow/cancelDelay`

### Variables
- `variable/get` - Read variable value
- `variable/set` - Set variable value
- `variable/interpolate` - Interpolate between values

### Pointers (glTF-specific)
- `pointer/get` - Read glTF property
- `pointer/set` - Set glTF property
- `pointer/interpolate` - Interpolate glTF property

### Events
- `event/onStart` - Lifecycle: graph start
- `event/onTick` - Lifecycle: per-frame update
- `event/send` - Send custom event
- `event/receive` - Receive custom event

## Usage

These samples can be used for:

1. **Testing behavior graph runtimes** - Validate runtime implementations
2. **Learning KHR_interactivity** - Understand behavior graph patterns
3. **Development reference** - Examples for building new graphs
4. **Integration testing** - Test Part 1 (AST → JSON) and Part 2 (JSON → C++) pipelines

## Source

These samples were extracted from the [glTF-InteractivityGraph-AuthoringTool](https://github.com/KhronosGroup/glTF-InteractivityGraph-AuthoringTool) test suite.

## License

These samples are provided for educational and testing purposes. Please refer to the original source repository for licensing information.

## Related Documentation

- [KHR_interactivity Specification](../gltf-interactivity/extensions/2.0/Khronos/KHR_interactivity/Specification.adoc)
- [Part 1: AST → JSON Plan](../part1_ast_to_json_plan.md)
- [Part 2: JSON → C++ Plan](../part2_json_to_cpp_plan.md)

