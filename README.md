# Derive Output Dimension Formula 📐

Interactive educational tool showing the **step-by-step mathematical derivation** of the convolution output dimension formula.

## 🎯 What This Tool Does

Shows **where** the formula comes from:
```
Output = ⌊(Input - Filter + 2×Padding) / Stride⌋ + 1
```

## 🚀 Quick Start

Simply open `index.html` in your browser:
```bash
open index.html
```

Or double-click the file.

## 📚 What You'll Learn

### Step-by-Step Derivation:

1. **Start with Input Size** - Understanding the base dimension
2. **Add Padding** - How padding extends the input (N + 2P)
3. **Consider Filter Size** - Why we subtract (F - 1)
4. **Calculate Valid Positions** - Counting where the filter fits
5. **Introduce Stride** - How stride reduces output positions
6. **Final Formula** - Putting it all together

### Visual Examples:

- 📊 **Grid Visualizations** - See padding, filter, and positions
- 🎨 **Color Coding** - Blue (input), Purple (padding), Red (filter), Green (output)
- 🧮 **Interactive Calculator** - Try your own values in real-time
- 📋 **Common Examples** - MNIST, ImageNet, Max Pooling, etc.

## 🎨 Features

### Interactive Calculator:
- **Input Size (N)**: Set your input dimension
- **Filter Size (F)**: Choose filter/kernel size
- **Padding (P)**: Add padding amount
- **Stride (S)**: Set stride value
- **Live Results**: See calculation update in real-time
- **Validation**: Checks if configuration produces integer output

### Visual Learning:
- **Step-by-step breakdown** with explanations
- **Visual grids** showing each concept
- **Color-coded elements** for clarity
- **Formula progression** from simple to complete

### Example Scenarios:
- Valid Padding (no padding)
- Same Padding (output = input)
- Stride 2 (downsampling)
- ImageNet-like convolution
- Max Pooling operation

## 📖 Understanding Each Step

### Step 1: Input Size
```
Input: [0, 1, 2, 3, 4, 5, 6]
Size N = 7
```

### Step 2: Add Padding
```
Padded: [P, P, 0, 1, 2, 3, 4, 5, 6, P, P]
New Size = 7 + 2(2) = 11
Formula: N + 2P
```

### Step 3: Filter Size
```
Filter needs F consecutive positions
Must fit completely on input
Covers F = 3 positions
```

### Step 4: Valid Positions (Stride 1)
```
First position: 0
Last position: (N + 2P - F)
Count: (N + 2P - F) + 1
```

### Step 5: Add Stride
```
Stride S jumps S positions each time
Divides positions by S
Formula: ((N + 2P - F) / S) + 1
```

### Step 6: Final Formula
```
Output = ⌊(N - F + 2P) / S⌋ + 1
```

## 💡 Key Insights

1. **Padding Effect**: Adds 2P to effective input size (P on each side)
2. **Filter Effect**: Reduces positions by (F - 1)
3. **Stride Effect**: Divides number of positions by S
4. **The +1**: Accounts for the first position (0-indexed to count)

## 🎓 Why This Matters

Understanding the derivation helps you:
- **Design CNN architectures** with correct dimensions
- **Debug dimension mismatches** in neural networks
- **Choose appropriate padding** for desired output
- **Calculate memory requirements** accurately
- **Understand receptive fields** better

## 📊 Example Calculations

### Example 1: MNIST-like
```
Input:   28
Filter:  5
Padding: 0
Stride:  1
Output:  ⌊(28 - 5 + 0) / 1⌋ + 1 = 24
```

### Example 2: Same Padding
```
Input:   28
Filter:  5
Padding: 2
Stride:  1
Output:  ⌊(28 - 5 + 4) / 1⌋ + 1 = 28
```

### Example 3: Downsampling
```
Input:   56
Filter:  2
Padding: 0
Stride:  2
Output:  ⌊(56 - 2 + 0) / 2⌋ + 1 = 28
```

## 🔗 Related Tools

This tool complements:
- **Convolution Calculator** (`../convolution_calculator/`) - Apply the formula
- Shows the "why" while calculator shows the "how"

## 🎯 Learning Path

1. **Start here** to understand the math
2. **Try examples** with the interactive calculator
3. **Experiment** with different values
4. **Move to** the convolution calculator for practical use
5. **See** the animated version for visual convolution process

## 💻 Technical Details

### Built With:
- Pure HTML/CSS/JavaScript
- No external dependencies
- Responsive design
- Works on all modern browsers

### Educational Design:
- Progressive disclosure of complexity
- Visual + Mathematical explanations
- Interactive experimentation
- Real-world examples

## 🎨 Color Scheme

- **Blue (#3498db)**: Input image
- **Purple (#9b59b6)**: Padding
- **Red (#e74c3c)**: Filter/kernel
- **Green (#27ae60)**: Output
- **Yellow (#ffc107)**: Highlights/warnings

## 📱 Responsive

Works on:
- Desktop computers
- Laptops
- Tablets
- Mobile phones (portrait/landscape)

## 🤝 For Educators

Perfect for:
- Teaching CNN fundamentals
- Linear algebra applications
- Understanding dimensions in deep learning
- Visual mathematics education
- Step-by-step problem solving

## 📈 Difficulty Level

- **Beginner-friendly**: No prior CNN knowledge needed
- **Progressive**: Builds from simple to complex
- **Interactive**: Learn by doing
- **Visual**: See the math in action

---

**Created**: February 2026
**Purpose**: Educational tool for understanding convolution mathematics
**Audience**: Students, researchers, engineers learning CNNs
**Companion to**: Convolution Calculator

Start exploring the mathematics behind CNNs! 🚀
