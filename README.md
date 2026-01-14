# Fluvial Particle Examples

> **Note**
> This repository is a **DRAFT** and under active development. Example datasets and tutorials are incomplete.

Example datasets, tutorials, and visualizations for [fluvial-particle](https://github.com/rmcd-mscb/fluvial-particle) - a Lagrangian particle tracking model for river flows.

## Quick Start

```bash
# Clone this repository (includes Git LFS data)
git clone https://github.com/rmcd-mscb/fluvial-particle-examples.git
cd fluvial-particle-examples

# Install pixi (if not already installed)
curl -fsSL https://pixi.sh/install.sh | bash

# Install all dependencies
pixi install

# Run an example simulation
pixi run simulate --settings examples/basic/options_straight.py --output outputs/test

# View the documentation
pixi run preview
```

## Contents

### Examples

| Example | Description |
|---------|-------------|
| [Quickstart](examples/basic/quickstart.qmd) | Run your first simulation |
| [Straight Channel](examples/basic/straight_channel.qmd) | Basic 2D particle tracking |
| [Time-Varying Flow](examples/time_varying/unsteady_flow.qmd) | Unsteady flow conditions |
| [3D Tracking](examples/3d_tracking/vertical_mixing.qmd) | Full 3D velocity interpolation |

### Datasets

| Dataset | Description | Size |
|---------|-------------|------|
| `data/grids/straight_channel/` | Simple straight channel | ~5 MB |
| `data/grids/time_series/` | Time-varying flow (5 timesteps) | ~20 MB |

## Requirements

This project uses [pixi](https://pixi.sh) for dependency management. Pixi handles both conda packages (VTK, HDF5) and PyPI packages (fluvial-particle) in a single tool.

### What pixi provides

- **Python 3.11+** - Interpreter
- **VTK** - Visualization Toolkit for grid I/O
- **h5py** - HDF5 file handling
- **NumPy** - Array operations
- **Quarto** - Documentation rendering
- **JupyterLab** - Interactive notebooks
- **fluvial-particle** - The main simulation package

## Usage

### Pixi Tasks

```bash
# Run a simulation
pixi run simulate --settings <options.py> --output <output_dir>

# Start JupyterLab
pixi run lab

# Render documentation
pixi run render

# Preview documentation site
pixi run preview

# Clean outputs
pixi run clean
```

### Development

```bash
# Install with dev dependencies
pixi install -e dev

# Run linter
pixi run lint

# Format code
pixi run format
```

## Git LFS

Large data files (VTS, H5, etc.) are stored using [Git LFS](https://git-lfs.github.com/).

```bash
# Pull all LFS files
git lfs pull

# Pull specific dataset
git lfs pull --include="data/grids/straight_channel/*"

# Check LFS status
git lfs status
```

## Documentation

The documentation is built with [Quarto](https://quarto.org/):

```bash
# Preview locally (with live reload)
pixi run preview

# Build static site
pixi run render

# Output is in _output/
```

## License

MIT License - see [LICENSE](LICENSE) for details.

## Related Projects

- [fluvial-particle](https://github.com/rmcd-mscb/fluvial-particle) - The main simulation package
- [fluvial-particle docs](https://fluvial-particle.readthedocs.io) - API documentation
