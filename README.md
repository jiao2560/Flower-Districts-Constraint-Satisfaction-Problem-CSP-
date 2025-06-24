# Flower Districts Constraint Satisfaction Problem (CSP)

## Overview

This repository contains a visual implementation and analysis of a Constraint Satisfaction Problem (CSP) involving the coloring of 9 flower districts. The problem demonstrates key CSP concepts including backtracking search, variable ordering heuristics, constraint propagation, and cutset conditioning.

## Problem Description

### The Challenge
Color 9 flower districts using a limited color palette while ensuring that no two adjacent districts (sharing a border) have the same color. The districts that must be colored are:

- **Daisy (D)**
- **Daffodil (DF)** 
- **Marigold (MG)**
- **Sun Flower (SF)**
- **Violet (V)**
- **Tulip (T)**
- **Poppy (P)**
- **Bluebell (BB)**
- **Rose (R)**

### Adjacency Constraints
The following districts share borders and cannot have the same color:
- Daisy ↔ Daffodil, Sun Flower, Violet, Bluebell
- Daffodil ↔ Daisy, Sun Flower, Marigold
- Marigold ↔ Daffodil, Sun Flower, Tulip
- Sun Flower ↔ Daffodil, Daisy, Marigold, Violet
- Violet ↔ Sun Flower, Daisy, Tulip, Poppy, Bluebell
- Tulip ↔ Marigold, Poppy, Violet
- Poppy ↔ Tulip, Rose, Bluebell, Violet
- Bluebell ↔ Daisy, Violet, Poppy, Rose
- Rose ↔ Bluebell, Poppy

## Questions Explored

### 1. Variable Ordering Analysis
**Question:** Based on the constraint graph and variable ordering heuristics, which district should be assigned a color first? Why?

**Answer:** Violet (V) should be assigned first because it has the highest degree (5 neighbors), making it the most constrained variable according to the Most Constrained Variable (MCV) heuristic.

### 2. 4-Color Problem
**Question:** Color the 9 flower districts using maximum 4 colors (Red, Green, Yellow, Blue) while satisfying all constraints.

**Solution:** Successfully solved using backtracking search with MRV and degree heuristics.

### 3. 3-Color Problem  
**Question:** Color the 9 flower districts using maximum 3 colors (Red, Green, Blue) while satisfying all constraints.

**Result:** Successfully solved, demonstrating that the graph is 3-colorable despite initial complexity.

### 4. Cutset Analysis
**Question:** Extract the smallest cutset from the constraint graph that results in a tree-structured residual problem.

**Answer:** The smallest connected cutset is {Sun Flower, Violet, Poppy}, which when removed leaves the remaining districts in a tree structure.

### 5. Cutset Conditioning
**Question:** Solve the CSP using cutset conditioning by first coloring the cutset, then solving the residual tree CSP.

**Result:** Demonstrates an alternative solving approach that can be more efficient for certain graph structures.

## Implementation Features

### Visual Constraint Graph
- Interactive SVG visualization of the constraint graph
- Color-coded districts with clear edge relationships
- Degree analysis table for variable ordering decisions

### CSP Techniques Demonstrated
- **Backtracking Search** with intelligent variable ordering
- **Most Constrained Variable (MCV)** heuristic
- **Minimum Remaining Values (MRV)** heuristic  
- **Forward Checking** for constraint propagation
- **Arc Consistency** enforcement
- **Cutset Conditioning** for tree decomposition
- **Least Constraining Value (LCV)** for value ordering

### Educational Value
This implementation serves as an excellent educational tool for understanding:
- Constraint satisfaction fundamentals
- Graph coloring algorithms
- Heuristic search strategies
- Tree decomposition techniques
- Complexity analysis of CSP problems

## Files

- `flower_constraint_graph.html` - Main visualization and analysis interface
- `README.md` - This documentation file

## Usage

Simply open `flower_constraint_graph.html` in a web browser to view the interactive constraint graph and analysis. The visualization includes:

- Complete constraint graph with all 9 districts
- Adjacency relationships clearly marked
- Variable degree analysis table
- Step-by-step reasoning for variable ordering decisions

## Key Insights

1. **Graph Structure Matters**: The constraint graph's topology directly impacts solving difficulty
2. **Heuristic Selection**: Proper variable and value ordering can dramatically reduce search space
3. **Multiple Solutions**: CSPs often have multiple valid solutions using different approaches
4. **Structural Techniques**: Cutset conditioning can convert complex problems into simpler tree-structured ones
5. **Chromatic Number**: This particular graph requires exactly 3 colors (chromatic number = 3)

## Educational Applications

This problem is ideal for:
- Artificial Intelligence coursework
- Algorithms and data structures classes  
- Graph theory demonstrations
- Constraint programming workshops
- Interactive learning about CSP solving techniques

---

*This implementation demonstrates practical applications of constraint satisfaction techniques as taught in CS5100 Foundations of Artificial Intelligence and similar courses.*
