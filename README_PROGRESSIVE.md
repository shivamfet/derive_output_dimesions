# Progressive Formula Derivation 📊

**Learn by Discovery**: Build the convolution output formula step-by-step through progressive exploration.

## 🎯 What This Tool Does

Instead of showing you the formula, it helps you **discover it yourself** through systematic exploration:

1. **Start simple**: Input H×W, Filter F×F, Padding=0, Stride=1
2. **Add padding**: See what happens when P increases
3. **Add stride**: Observe the effect of larger strides
4. **Recognize patterns**: Identify how each parameter affects output
5. **Generalize**: Build the complete formula from observations

## 🚀 Quick Start

```bash
open progressive.html
```

## 📐 The Exploration Journey

### Initial Setup:
- **Input**: H × W (e.g., 7×7)
- **Filter**: F × F (e.g., 3×3)
- **Start**: Padding = 0, Stride = 1

### Progressive Cases:

#### **Case 1: Base Case (P=0, S=1)**
```
Input: 7×7, Filter: 3×3, Padding: 0, Stride: 1
Output: 5×5
Observation: Output is smaller by (F-1) = 2
```

#### **Case 2: Add Padding +1 (P=1, S=1)**
```
Input: 7×7, Filter: 3×3, Padding: 1, Stride: 1
Output: 7×7
Observation: Gained 2 in each dimension!
Pattern: Each padding unit adds ~2 to output
```

#### **Case 3: Add Padding +1 More (P=2, S=1)**
```
Input: 7×7, Filter: 3×3, Padding: 2, Stride: 1
Output: 9×9
Observation: Gained 2 more in each dimension
Confirmed: Padding adds 2P to effective size
```

#### **Case 4: Increase Stride (P=0, S=2)**
```
Input: 7×7, Filter: 3×3, Padding: 0, Stride: 2
Output: 3×3
Observation: Roughly halved the output!
Pattern: Stride divides the range
```

#### **Case 5: Combined (P=1, S=2)**
```
Input: 7×7, Filter: 3×3, Padding: 1, Stride: 2
Output: 4×4
Observation: Both effects work together
```

#### **Case 6: Combined (P=2, S=2)**
```
Input: 7×7, Filter: 3×3, Padding: 2, Stride: 2
Output: 5×5
Observation: More padding = larger output even with stride
```

## 🔍 Pattern Recognition

From these experiments, we observe:

### **Padding Effect:**
- Base (P=0): Output = 5
- P=1: Output = 7 (gained +2)
- P=2: Output = 9 (gained +2 more)
- **Pattern**: Padding adds 2P to the effective input size

### **Stride Effect:**
- S=1: Output = 5
- S=2: Output = 3 (roughly half)
- **Pattern**: Stride divides the number of positions

### **Combined Pattern:**
```
1. Start with input size: H or W
2. Subtract filter size: Input - F (available range)
3. Add padding effect: Input - F + 2P (extended range)
4. Divide by stride: (Input - F + 2P) / S (jumping reduces positions)
5. Add starting position: ((Input - F + 2P) / S) + 1
6. Floor to integer: ⌊(Input - F + 2P) / S⌋ + 1
```

## 🎓 Building the Formula

### **Evolution:**

```
Step 1: Base (P=0, S=1)
Output = Input - Filter + 1

Step 2: Add Padding
Output = Input - Filter + 2P + 1

Step 3: Add Stride
Output = (Input - Filter + 2P) / Stride + 1

Step 4: Ensure Integer
Output = ⌊(Input - Filter + 2P) / Stride⌋ + 1
```

### **Final Formula:**
```
Output_H = ⌊(H - F + 2P) / S⌋ + 1
Output_W = ⌊(W - F + 2P) / S⌋ + 1
```

## 💡 Key Insights

### **Why (Input - Filter)?**
The filter needs F positions to operate. From Input positions, we can only place the filter at (Input - F + 1) starting positions when it must fit completely.

### **Why +2P?**
Padding adds P pixels on **both sides** (left/right or top/bottom), so total addition is 2P.

### **Why / Stride?**
If we can place the filter at N positions with stride=1, then with stride=S, we jump S positions each time, giving us N/S positions.

### **Why +1?**
We're counting positions, and positions are 0-indexed but count is 1-indexed. The first position (0) counts as 1 position.

## 📊 Interactive Features

### **Adjustable Parameters:**
- Change input dimensions (H, W)
- Change filter size (F)
- Automatically shows 6 cases with increasing P and S

### **Visual Comparisons:**
- Side-by-side case display
- Step-by-step calculations for each case
- Change from base case highlighted
- Color-coded parameters

### **Comparison Table:**
| Case | Padding | Stride | Output | Change |
|------|---------|--------|--------|--------|
| 1 | 0 | 1 | 5×5 | Base |
| 2 | 1 | 1 | 7×7 | ▲ +2 |
| 3 | 2 | 1 | 9×9 | ▲ +4 |
| 4 | 0 | 2 | 3×3 | ▼ -2 |
| 5 | 1 | 2 | 4×4 | ▼ -1 |
| 6 | 2 | 2 | 5×5 | = 0 |

## 🎯 Learning Outcomes

After using this tool, you will understand:

1. **Why** we subtract the filter size
2. **Why** padding is multiplied by 2
3. **How** stride reduces output dimensions
4. **When** configurations produce integer outputs
5. **How** to derive formulas from first principles

## 🔗 Comparison with Other Tools

| Tool | Purpose | Best For |
|------|---------|----------|
| `index.html` | Complete derivation | Understanding the math |
| `progressive.html` | Discovery-based | Learning by exploration |

## 💻 Try Different Inputs

### **Small Input:**
```
H=5, W=5, F=3
Watch outputs change from 3×3 to 1×1
```

### **Large Input:**
```
H=224, W=224, F=7
See ImageNet-style dimensions
```

### **Non-Square:**
```
H=7, W=10, F=3
Observe different H and W outputs
```

## 🎓 Educational Value

### **Discovery Learning:**
- Students discover patterns themselves
- More engaging than formula presentation
- Better retention through active learning

### **Pattern Recognition:**
- Trains mathematical intuition
- Shows how formulas are derived
- Demonstrates systematic exploration

### **Practical Skills:**
- Debug dimension mismatches
- Design CNN architectures
- Understand tradeoffs

## 📱 Works Everywhere

- Desktop browsers
- Mobile devices
- Tablets
- No installation required

---

**Created**: February 2026
**Approach**: Discovery-based learning
**Target**: Students, researchers, engineers
**Method**: Progressive exploration → Pattern recognition → Generalization

Start exploring and discover the formula yourself! 🚀
