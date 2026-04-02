# Backprop Golf

Learn backpropagation and gradient descent by playing mini golf!

**[Play the live demo](https://timvieira.github.io/backprop-pool/)**

## How it works

Choose an **angle** and **force** to hit the ball. The ball bounces around following physics (friction, wall reflections, sand traps). After each shot, **backpropagation** computes the gradient of the loss (squared distance to the hole) with respect to your parameters. Use the gradient to make small adjustments -- this is **gradient descent**!

### The differentiable physics engine

The simulation is built as a tape-based automatic differentiation system:

- **Forward pass**: Runs the full physics simulation while recording every operation (position updates, friction, wall collisions) onto a tape.
- **Backward pass**: Walks the tape in reverse, propagating gradients through each operation using its Jacobian transpose.
- **Verification**: A "Verify with finite differences" button confirms the analytical gradients match numerical ones. ([How to test gradient implementations](https://timvieira.github.io/blog/post/2017/04/21/how-to-test-gradient-implementations/))

### Differentiable operations

| Operation | Forward | Backward |
|-----------|---------|----------|
| Position update | `x += vx` | `gvx += gx` |
| Friction | `vx *= f` | `gvx *= f` |
| Wall collision | Reflect velocity through normal `(nx, ny)` with 0.8 damping | Transpose of reflection matrix `0.8 * [[1-2nx², -2nxny], [-2nxny, 1-2ny²]]` |

The final chain rule maps velocity gradients back to `dL/d(angle)` and `dL/d(force)`.
