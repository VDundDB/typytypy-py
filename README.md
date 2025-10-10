# TypyTypy *(typytypy-py)*

*— A Bespoke Character-by-Character Text Printer.*

> *[click-clack-clack...]*

A utility Python library which provides for a realistic, "real-time typing" simulation with highly configurable implementations. It features a flexible API for both simple and advanced use, quick-use "character personality" presets, and granular timing control for creating custom text presentations with authentic temporal dynamics.

*Born of the [KitschCode](https://github.com/VDundDB/KitschCode-py) philosophy of applying meticulous craftsmanship to humble functionality.*

...

---

## Features

### > Developer-Focused API

- 🎯 **Simple Direct Usage**: Get started with a single function call: `typytypy.type_out("Hello, World!")`.
- 📊 **Layered Design**: A flexible API offers both module-level convenience functions and advanced, object-oriented instance management.

### > Expressive Typing Engine

- 🎭 **Character Personalities**: Simulate distinct typing styles with built-in presets like `NERVOUS`, `CONFIDENT`, and `ROBOTIC`.
- ⏱️ **Granular Timing Control**: Define custom timing profiles to precisely control typing rhythm for specific keywords.
- 👁️‍🗨️ **High-Fidelity Output**: Renders text as "real-time typing" simulation, perfectly preserving all original formatting, spacing, and line breaks.

### > Professional-Grade Foundation

- ⚡ **Zero Dependencies**: Pure Python implementation for a lightweight and hassle-free integration.
- 🔒 **Robust & Type-Safe**: Comprehensive validation and full type safety ensure predictable, error-free behavior.
- 📦 **Modern Packaging**: Built and packaged using contemporary Python standards for seamless installation and use.

...

---

## API Reference

### Module-Level Functions

#### `typytypy.type_out(text, base_delay=None, delay_range=None)`

- Print text character-by-character using the default printer instance with optional timing overrides.

#### `typytypy.get_available_presets()`

- List all predefined timing presets (Character Presets) with their timing configuration details.

#### `typytypy.use_preset(preset_name)`

- Create a limited printer instance using a predefined timing preset.
  - only the `type_out()` method is available

### Advanced Class

#### `typytypy.PrintingPress(base_delay=None, delay_range=None)`

*Advanced printer with full profile management capabilities.*

**Core Methods:**

- `type_out(text, base_delay=None, delay_range=None)`: Print text character-by-character, applying profile timings for recognized words and fallback timings for others.
- `set_timing(base_delay, delay_range)`: Update the instance's default timing parameters.

**Profile Management:**

- `create_profile(profile_name, base_delay, delay_range, words=None)`: Create a new timing profile with optional initial words.
- `add_words_to_profile(profile_name, words)`: Add words to an existing profile. Accepts a single string or list of strings.
- `remove_words_from_profile(profile_name, words)`: Remove words from a profile. Accepts a single string or list of strings.
- `list_profiles()`: Return list of all profile names in insertion order.
- `get_profile_info(profile_name)`: Return dictionary with profile details: `base_delay`, `delay_range`, `word_count`, and `words` list.
- `update_profile_timing(profile_name, base_delay, delay_range)`: Update timing parameters for an existing profile.
- `delete_profile(profile_name)`: Delete an entire profile and clean up all mappings.

**Configuration:**

- `set_profile_case_sensitivity(sensitive)`: Configure case-sensitivity for word matching.

---

## Development

### Requirements

- Python 3.10+
- No runtime dependencies

### Development Setup

#### Clone repository

```shell
git clone https://github.com/VDundDB/typytypy-py.git

cd typytypy-py
```

#### Install development dependencies

```python
pip install -e ".[dev]"
```

#### Run quality checks

```python
ruff check src/ tests/
black --check src/ tests/
mypy src/ tests/

# Run all tests with coverage
pytest
```

---

## License

Apache License 2.0. See [LICENSE](LICENSE) for details.

---

...
