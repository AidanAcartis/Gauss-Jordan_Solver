# Gauss-Jordan Solver

This project automates the resolution of a linear system of equations using the **Gauss-Jordan elimination method**.  
All calculations are done with exact fractions to avoid rounding errors.

---

## 🔍 Mathematical Method

A linear system is written as:

```

P * X = B

```

Where:
- `P` is the coefficient matrix (m x n)
- `X` is the unknown vector
- `B` is the constant vector

### Gauss-Jordan elimination

The algorithm transforms the augmented matrix `(P | B)` into **Reduced Row Echelon Form (RREF)**.

The goal is to obtain:
- pivot = 1
- zeros above and below each pivot

Once the matrix is in RREF, the solution is directly read from the last column.

---

## 🧠 Algorithm (High Level)

1. For each row and column:
   - Find the first non-zero element (pivot)
   - Divide the row by the pivot to make it 1
   - Eliminate all other values in that column (above and below the pivot)
2. Check for inconsistency:
   - If a row becomes `[0 0 0 | b]` with `b != 0` → no solution
3. Reorder rows so that zero rows are at the bottom
4. Output the solution vector

---

## 📁 Project Structure

```

Gauss-Jordan_Solver/
├── Fraction.java
├── FractionApp.java
├── Main.java
├── MatrixUtils.java
├── Solver.java
└── README.md

```

---

## 📌 Example Session

```

Nombre de lignes : 4
Nombre de colonnes : 3
Entrez les coefficients de la matrice P (forme a/b) :
P[0][0] = -1/2
P[0][1] = 1/3
P[0][2] = 0
P[1][0] = 1/2
P[1][1] = -2/3
P[1][2] = 1/2
P[2][0] = 0
P[2][1] = 1/3
P[2][2] = -1/2
P[3][0] = 1
P[3][1] = 1
P[3][2] = 1
Entrez les valeurs du second membre B (forme a/b) :
B[0] = 0
B[1] = 0
B[2] = 0
B[3] = 1
Matrice augmentée (P | B) :
| 1 -2/3 0 | 0 |
| 0 -1/3 1/2 | 0 |
| 0 1/3 -1/2 | 0 |
| 0 5/3 1 | 1 |

Matrice augmentée (P | B) :
| 1 0 -1 | 0 |
| 0 1 -3/2 | 0 |
| 0 0 0 | 0 |
| 0 0 7/2 | 1 |

Matrice augmentée (P | B) :
| 1 0 0 | 2/7 |
| 0 1 0 | 3/7 |
| 0 0 0 | 0 |
| 0 0 1 | 2/7 |

Matrice réordonnée (lignes nulles en bas) :
Matrice augmentée (P | B) :
| 1 0 0 | 2/7 |
| 0 1 0 | 3/7 |
| 0 0 1 | 2/7 |
| 0 0 0 | 0 |

X[0] = 2/7
X[1] = 3/7
X[2] = 2/7

```

---

## 🚀 How to run

```

javac *.java
java Main

```
