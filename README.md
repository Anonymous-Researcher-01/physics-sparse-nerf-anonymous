# PhysicsNeRF: Physics-Guided Neural Radiance Fields for Plausible 3D Reconstruction from Sparse Views

**Anonymous Submission to ICML 2025 Workshop: Building Physically Plausible World Models**

## Abstract

We present PhysicsNeRF, a novel approach for physically consistent 3D reconstruction from sparse views by augmenting Neural Radiance Fields with physical priors. Our method integrates four complementary physics-based constraints: depth ranking supervision, RegNeRF consistency regularization, sparsity constraints, and cross-view consistency through a carefully designed 0.67M parameter architecture.

## Key Features

- **Sparse-view reconstruction** with only 8 training views
- **Physics-guided constraints** for geometric plausibility
- **Progressive training strategy** with curriculum learning
- **Balanced architecture design** (0.67M parameters)
- **Comprehensive evaluation** on static and dynamic scenes

## Results Summary

| Object | Train PSNR | Test PSNR | Gap (dB) |
|--------|-------------|------------|----------|
| Chair | 23.2 | 18.5 | 4.7 |
| Lego | 21.7 | 15.0 | 6.7 |
| Drums | 19.2 | 12.0 | 7.2 |
| **Average** | **21.4** | **15.2** | **6.2** |

## Method Overview

### Architecture
- Dual-scale coordinate processing (1× and 2×)
- D=7 layers, W=192 dimensions
- Moderate dropout (0.25) for regularization
- LayerNorm for training stability

### Physics Constraints
1. **Depth Ranking**: Monocular depth consistency using MiDaS
2. **RegNeRF Consistency**: Ray perturbation regularization  
3. **Sparsity**: Realistic density distributions
4. **Cross-View**: Multi-view geometric coherence

### Progressive Training
- Phase 1 (0-5k): α=0.008 (gentle start)
- Phase 2 (5k-15k): α=0.025 (light regularization)
- Phase 3 (15k+): α=0.08 (full constraints)



