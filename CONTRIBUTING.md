# Contributing to 3D Geological Modeling Project

🙏 **Thank you for your interest in contributing to the 3D Geological Modeling and Analysis Project!**

We welcome contributions from the geological engineering, mining, data science, and computational geometry communities. This document provides guidelines for contributing to make the process smooth and effective for everyone.

## 📋 Table of Contents

- [🎯 How to Contribute](#-how-to-contribute)
- [🐛 Reporting Issues](#-reporting-issues)
- [✨ Suggesting Features](#-suggesting-features)
- [🔧 Development Setup](#-development-setup)
- [📝 Code Contribution Process](#-code-contribution-process)
- [🎨 Code Style Guidelines](#-code-style-guidelines)
- [🧪 Testing Guidelines](#-testing-guidelines)
- [📚 Documentation](#-documentation)
- [🤝 Community Guidelines](#-community-guidelines)

## 🎯 How to Contribute

There are many ways to contribute to this project:

### 🔬 **Research & Development**
- Implement new geological modeling algorithms
- Add support for additional geological data formats
- Develop machine learning models for automatic discontinuity detection
- Create new optimization algorithms for block extraction

### 💻 **Software Development**
- Fix bugs and improve performance
- Add new visualization features
- Enhance interactive dashboard capabilities
- Improve data processing pipelines

### 📖 **Documentation & Education**
- Improve documentation and tutorials
- Create educational examples and case studies
- Translate documentation to other languages
- Write blog posts about use cases

### 🧪 **Testing & Quality Assurance**
- Test with different geological datasets
- Report bugs and edge cases
- Improve test coverage
- Validate results against real-world data

## 🐛 Reporting Issues

### Before Reporting
1. **Search existing issues** to avoid duplicates
2. **Test with the latest version** to ensure the issue still exists
3. **Gather information** about your environment and data

### Issue Template
When reporting issues, please include:

```markdown
**Bug Description**
Clear description of what's wrong

**To Reproduce**
Steps to reproduce the behavior:
1. Load data file '...'
2. Run notebook cell '...'
3. Execute function '...'
4. See error

**Expected Behavior**
What you expected to happen

**Environment**
- OS: [e.g., Windows 10, Ubuntu 20.04]
- Python version: [e.g., 3.8.5]
- Library versions: [e.g., trimesh 3.15.0, open3d 0.15.0]
- Jupyter version: [e.g., Lab 3.2.0]

**Data Details**
- Data format: [e.g., Excel, CSV]
- Number of discontinuities: [e.g., 12]
- Stone dimensions: [e.g., 2×21×4.6 meters]

**Screenshots/Outputs**
If applicable, add screenshots or error outputs
```

## ✨ Suggesting Features

We welcome feature suggestions! Please:

1. **Check existing feature requests** first
2. **Describe the use case** clearly
3. **Explain the geological/engineering motivation**
4. **Suggest implementation approach** if possible

### Feature Request Template
```markdown
**Feature Description**
Brief description of the proposed feature

**Geological/Engineering Use Case**
Why is this feature needed? What problem does it solve?

**Proposed Implementation**
How could this be implemented? Any specific algorithms or libraries?

**Examples**
Provide examples of similar features in other tools

**Additional Context**
Any other relevant information
```

## 🔧 Development Setup

### Prerequisites
- **Python 3.8+**
- **Git**
- **Jupyter Lab**
- **Modern browser** with WebGL support

### Setup Instructions

1. **Fork and Clone**
```bash
# Fork the repository on GitHub first
git clone https://github.com/sepehrkdi/3DStone.git
cd 3DStone
```

2. **Create Development Environment**
```bash
# Create virtual environment
python -m venv venv

# Activate environment
source venv/bin/activate  # Linux/Mac
# or
venv\Scripts\activate     # Windows
```

3. **Install Dependencies**
```bash
# Install main dependencies
pip install -r requirements.txt

# Install development dependencies
pip install -r requirements-dev.txt
```

4. **Install in Development Mode**
```bash
pip install -e .
```

5. **Verify Setup**
```bash
# Run tests
pytest tests/

# Start Jupyter Lab
jupyter lab
```

### Development Dependencies
```txt
# requirements-dev.txt
pytest>=6.0.0
pytest-cov>=2.10.0
black>=21.0.0
flake8>=3.8.0
isort>=5.0.0
mypy>=0.910
pre-commit>=2.15.0
nbformat>=5.0.0
nbconvert>=6.0.0
```

## 📝 Code Contribution Process

### 1. **Create Feature Branch**
```bash
git checkout -b feature/your-feature-name
# or
git checkout -b bugfix/issue-description
```

### 2. **Make Changes**
- Write clean, documented code
- Follow the coding style guidelines
- Add tests for new features
- Update documentation as needed

### 3. **Test Your Changes**
```bash
# Run all tests
pytest tests/

# Run specific test file
pytest tests/test_geological_modeling.py

# Run with coverage
pytest --cov=src tests/
```

### 4. **Commit Changes**
```bash
# Stage changes
git add .

# Commit with descriptive message
git commit -m "feat: add rotation optimization algorithm

- Implement automatic orientation finding for maximum voxelization efficiency
- Add support for custom rotation angle ranges
- Include performance benchmarking
- Update documentation with usage examples

Fixes #123"
```

### 5. **Push and Create Pull Request**
```bash
git push origin feature/your-feature-name
```

Then create a Pull Request on GitHub with:
- **Clear description** of changes
- **Reference to related issues**
- **Screenshots** of new visualizations (if applicable)
- **Test results** and performance impact

## 🎨 Code Style Guidelines

### Python Code Style
We use **Black** for code formatting and **flake8** for linting:

```bash
# Format code
black src/ tests/

# Check linting
flake8 src/ tests/

# Sort imports
isort src/ tests/
```

### Notebook Guidelines
- **Clear cell organization** with markdown headers
- **Comprehensive documentation** for each section
- **Remove output** before committing (except for demonstration purposes)
- **Use descriptive variable names**
- **Add timing information** for performance-critical sections

### Documentation Style
- Use **clear, concise language**
- Include **code examples** for functions
- Add **geological context** where relevant
- Follow **NumPy docstring format**

```python
def calculate_hull_volume(points):
    """
    Calculate volume of convex hull from geological points.
    
    Parameters
    ----------
    points : array_like, shape (n, 3)
        3D coordinates of geological vertices
        
    Returns
    -------
    float
        Volume of the convex hull in cubic units
        
    Examples
    --------
    >>> points = np.array([[0, 0, 0], [1, 0, 0], [0, 1, 0], [0, 0, 1]])
    >>> volume = calculate_hull_volume(points)
    >>> print(f"Volume: {volume:.3f}")
    Volume: 0.167
    
    Notes
    -----
    Uses scipy.spatial.ConvexHull for robust volume calculation.
    Returns 0 if insufficient points are provided (< 4 points).
    """
```

## 🧪 Testing Guidelines

### Test Structure
```
tests/
├── test_geological_modeling.py    # Core geological functions
├── test_visualization.py          # Visualization functions
├── test_optimization.py           # Optimization algorithms
├── test_data_processing.py        # Data I/O and processing
├── fixtures/                      # Test data files
│   ├── sample_discontinuities.xlsx
│   └── test_segments.json
└── conftest.py                    # Pytest configuration
```

### Writing Tests
```python
import pytest
import numpy as np
from src.geological_modeling import Stone, calculate_hull_volume

class TestGeologicalModeling:
    """Test suite for geological modeling functions."""
    
    def test_stone_initialization(self):
        """Test Stone class initialization with valid dimensions."""
        stone = Stone(width=2, length=21, height=4.6)
        assert stone.width == 2
        assert stone.length == 21
        assert stone.height == 4.6
        
    def test_hull_volume_calculation(self):
        """Test convex hull volume calculation accuracy."""
        # Test with known tetrahedron
        points = np.array([[0, 0, 0], [1, 0, 0], [0, 1, 0], [0, 0, 1]])
        volume = calculate_hull_volume(points)
        expected = 1/6  # Tetrahedron volume formula
        assert abs(volume - expected) < 1e-10
        
    def test_insufficient_points(self):
        """Test behavior with insufficient points for hull calculation."""
        points = np.array([[0, 0, 0], [1, 0, 0]])  # Only 2 points
        volume = calculate_hull_volume(points)
        assert volume == 0
        
    @pytest.mark.parametrize("width,length,height", [
        (1, 10, 5),
        (2.5, 15.2, 3.8),
        (0.5, 25, 10)
    ])
    def test_stone_various_dimensions(self, width, length, height):
        """Test Stone class with various realistic dimensions."""
        stone = Stone(width, length, height)
        assert stone.width == width
        assert stone.length == length
        assert stone.height == height
```

### Performance Testing
```python
import time
import pytest

@pytest.mark.performance
def test_large_dataset_performance():
    """Test performance with large geological datasets."""
    # Generate large dataset
    large_discontinuities = generate_test_discontinuities(n=100)
    
    start_time = time.time()
    stone = Stone(10, 50, 20)
    stone.discontinuities = large_discontinuities
    segments = stone.slice_with_discontinuities()
    processing_time = time.time() - start_time
    
    # Should process 100 discontinuities in under 30 seconds
    assert processing_time < 30
    assert len(segments) > 0
```

## 📚 Documentation

### Types of Documentation

1. **Code Documentation**: Inline comments and docstrings
2. **API Documentation**: Function and class documentation
3. **Tutorials**: Step-by-step guides for common tasks
4. **Examples**: Real-world use cases and demonstrations
5. **Technical Notes**: Algorithm explanations and geological background

### Documentation Standards
- **Keep it current** with code changes
- **Use examples** liberally
- **Explain geological context** when relevant
- **Include performance notes** for computationally intensive operations
- **Add references** to relevant papers and standards

## 🤝 Community Guidelines

### Be Respectful and Inclusive
- **Welcome newcomers** from different backgrounds
- **Respect diverse perspectives** on geological modeling approaches
- **Provide constructive feedback** in code reviews
- **Be patient** with questions and learning processes

### Communication Guidelines
- **Use clear, professional language**
- **Stay on topic** in discussions
- **Provide context** for geological or technical terms
- **Share resources** and references when helpful

### Recognition
Contributors will be:
- **Listed in CONTRIBUTORS.md**
- **Acknowledged in release notes**
- **Credited in academic citations** (for significant contributions)
- **Invited to co-author papers** (for major algorithmic contributions)

## 🏷️ Commit Message Guidelines

Use conventional commit format:

```
<type>(<scope>): <subject>

<body>

<footer>
```

**Types:**
- `feat`: New feature
- `fix`: Bug fix
- `docs`: Documentation changes
- `style`: Code style changes (formatting, etc.)
- `refactor`: Code refactoring
- `test`: Adding or updating tests
- `perf`: Performance improvements
- `chore`: Maintenance tasks

**Examples:**
```
feat(optimization): add genetic algorithm for cutting optimization

Implement genetic algorithm approach for multi-objective optimization
of geological block cutting patterns. Includes population initialization,
selection, crossover, and mutation operators specifically designed for
geological segment geometries.

- Add GA class with geological-specific operators
- Include convergence monitoring and early stopping
- Add benchmark comparison with existing methods
- Update documentation with usage examples

Closes #45
```

## 📞 Getting Help

### Community Support
- **GitHub Discussions**: General questions and ideas
- **Issues**: Bug reports and feature requests
- **Email**: Direct contact for collaboration opportunities

### Development Questions
- **Code Review**: Request feedback on implementation approaches
- **Algorithm Discussion**: Discuss geological modeling techniques
- **Performance**: Help with optimization and scaling

### Geological Domain Questions
- **Data Formats**: Help with geological data interpretation
- **Standards**: Guidance on industry standards and practices
- **Applications**: Discussion of real-world use cases

---

## 🎉 Thank You!

Your contributions help advance the field of computational geology and make geological modeling more accessible to researchers, engineers, and practitioners worldwide.

**Happy Contributing! 🗿💻🎯**

---

*For additional questions or clarifications, please reach out via [GitHub Issues](https://github.com/sepehrkdi/3DStone/issues) or email [thisissepehrkhd@gmail.com](mailto:thisissepehrkhd@gmail.com).*