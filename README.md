# vec3_asm
## Reference

| Function | Parameters | Returns | Example |
|----------|-----------|---------|---------|
| `vec3_add` | `result*, a*, b*` | void | `(1,2,3) + (4,5,6) = (5,7,9)` |
| `vec3_sub` | `result*, a*, b*` | void | `(5,7,9) - (1,2,3) = (4,5,6)` |
| `vec3_mul_scalar` | `result*, v*, scalar` | void | `(1,2,3) * 2 = (2,4,6)` |
| `vec3_div_scalar` | `result*, v*, scalar` | void | `(4,6,8) / 2 = (2,3,4)` |
| `vec3_dot` | `a*, b*` | float | `(1,0,0) · (1,0,0) = 1.0` |
| `vec3_cross` | `result*, a*, b*` | void | `(1,0,0) × (0,1,0) = (0,0,1)` |
| `vec3_length` | `v*` | float | `len(3,4,0) = 5.0` |
| `vec3_length_squared` | `v*` | float | `len²(3,4,0) = 25.0` |
| `vec3_distance` | `a*, b*` | float | `dist((0,0,0), (3,4,0)) = 5.0` |
| `vec3_normalize` | `result*, v*` | void | `(3,4,0) → (0.6,0.8,0)` |
| `vec3_lerp` | `result*, a*, b*, t` | void | `lerp((0,0,0), (10,0,0), 0.5) = (5,0,0)` |
| `vec3_reflect` | `result*, v*, n*` | void | `reflect((1,-1,0), (0,1,0)) = (1,1,0)` |

## Usage
Vectors are stored as three consecutive floats (12 bytes). Uses System V AMD64 calling convention.

```c
// C interface example
typedef struct { float x, y, z; } vec3;

extern void vec3_add(vec3* result, const vec3* a, const vec3* b);
extern float vec3_dot(const vec3* a, const vec3* b);

vec3 a = {1.0f, 2.0f, 3.0f};
vec3 b = {4.0f, 5.0f, 6.0f};
vec3 result;

vec3_add(&result, &a, &b);  // result = (5, 7, 9)
float dot = vec3_dot(&a, &b);  // dot = 32.0
```
