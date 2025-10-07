# cppGlm

**cppGlm** is a lightweight C++ header package that integrates the [GLM (OpenGL Mathematics)](https://github.com/g-truc/glm) library and adds helper functions for working with 4×4 matrices — ideal for graphics and linear algebra applications.

---

## 🧩 Distributed via **vicmil-pip**

This library is officially distributed through **[vicmil-pip](https://github.com/vicmil-pip-v2/vicmil-pip)** — a cross-platform C++ package manager inspired by Python’s `pip`.

To install **cppGlm**:

```bash
python3 vicmil-pip.py install cppGlm
```

After installation, include it in your project like so:

```cpp
#include "vicmil_pip_cppGlm.hpp"
```

That’s it — no manual setup or global installs required!

---

## 📘 Description

`cppGlm` wraps GLM’s matrix utilities and adds convenience helpers to simplify integration with external data formats like **glTF**, which use **column-major order**.

---

## 🚀 Features

- ✅ Bundles key GLM headers:

  - `glm/glm/gtx/transform.hpp`
  - `glm/glm/gtx/string_cast.hpp`

- 🧠 Provides helper functions to safely build `glm::mat4` matrices from standard containers or raw pointers.
- 🔒 Safe fallbacks — returns identity matrices on invalid inputs.
- 🧩 Seamless integration with **vicmil-pip** environments.

---

## 🧱 API Reference

### `glm::mat4 make_mat4(const std::vector<double> &mat)`

Creates a 4×4 matrix from a 16-element vector of doubles.

- **Parameters:**
  `mat` — vector containing 16 double values (column-major order)
- **Returns:**
  A `glm::mat4` initialized with the given values, or the identity matrix if the vector size is not 16.

---

### `glm::mat4 make_mat4(const double *mat)`

Creates a 4×4 matrix from a pointer to 16 double values.

- **Parameters:**
  `mat` — pointer to an array of 16 doubles (column-major order)
- **Returns:**
  A `glm::mat4` initialized with the data, or the identity matrix if the pointer is null.

---

## 🧠 Example Usage

```cpp
#include "cppGlm.hpp"

int main()
{
    std::vector<double> data = {
        1.0, 0.0, 0.0, 0.0,
        0.0, 1.0, 0.0, 0.0,
        0.0, 0.0, 1.0, 0.0,
        0.5, 0.5, 0.0, 1.0
    };

    glm::mat4 transform = vicmil::make_mat4(data);
    std::cout << glm::to_string(transform) << std::endl;
}
```

---

## 🧰 Integration Notes

When installed through **vicmil-pip**, `cppGlm` resides inside:

```
vicmil_pip/lib/cppGlm/
```

Include paths are automatically handled by **vicmil-pip**, ensuring a clean and reproducible environment.

---

## 🪪 License

Distributed under the **MIT License**.
See `LICENSE` for details.
Some included third-party components are provided under their own licenses (see their respective folders in third_party/).

---

**Author:** [02vicmil](https://github.com/02vicmil)
**Package Source:** [vicmil-pip / cppGlm](https://github.com/vicmil-pip-v2)
**Version:** 1.0.0
