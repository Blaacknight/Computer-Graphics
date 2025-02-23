Graphics Programming Using OpenGL

## Introduction
- Discusses the second part of OpenGL, a standard for computer graphics.
- Recap of previous lecture:
  - OpenGL as a standard
  - Features: drawing, shading, clipping, rendering, transformations
  - Event-driven mechanism, state machine
  - Framework: segment, vertex, fragment operations, pixel operations
  - Abstractions: GL, GLU, GLUT
  - 3D Viewing Pipeline

## 3D Viewing Pipeline
- Starts with object coordinates (vertices of lines, polygons, polylines)
- Passes through:
  - **Modelview Matrix** → Generates world coordinates
  - **Projection Matrix** → Defines perspective, look-up angle
  - **Clipping Tools** → Generates clip coordinates
  - **Perspective Division** → Converts to Normalized Device Coordinates (NDC)
  - **Viewport Matrix** → Converts to window coordinates (frame buffer output)

## Viewing Transformations
- `glLoadIdentity()` → Loads identity matrix
- `gluLookAt(eyeX, eyeY, eyeZ, lookAtX, lookAtY, lookAtZ, upX, upY, upZ)` → Defines camera position and direction
- Scaling:
  - `glScalef(x, y, z)` → Scales along specified axes
  - Different data types: integer, float, byte

## Projection Transformations
- `glMatrixMode(GL_PROJECTION)` → Switches to projection mode
- `glLoadIdentity()` → Resets the projection matrix
- `glPerspective(viewAngle, aspectRatio, nearZ, farZ)` → Sets perspective projection

## Initializing OpenGL
- **GLUT Setup:**
  - `glutInit()` → Initializes GLUT
  - `glutInitDisplayMode(GLUT_RGB | GLUT_DOUBLE)` → Sets display mode
  - `glutCreateWindow("Title")` → Creates window
  - `glutDisplayFunc(displayFunction)` → Registers display callback
  - `glutKeyboardFunc(myKeyHandler)` → Registers keyboard callback
  - `glutMouseFunc(myMouseClickHandler)` → Registers mouse callback
  - `glutMotionFunc(myMouseMotionHandler)` → Tracks mouse motion

## Rendering Primitives
- `glBegin(GL_POINTS)` → Draws points
- `glBegin(GL_POLYGON)` → Draws polygons
- `glColor3f(r, g, b)` → Sets color (float values from 0 to 1)
- `glColor3ub(r, g, b)` → Sets color (byte values from 0 to 255)

## Shading Models
- `glShadeModel(GL_SMOOTH)` → Enables smooth shading (Gouraud shading)
- `glShadeModel(GL_FLAT)` → Enables flat shading
- Gouraud shading: interpolates colors between vertices

## Lighting in OpenGL
- **Light types:**
  - Ambient light → Comes from all directions
  - Diffuse light → Spreads in all directions from a point source
- **Setting up lighting:**
  - `glLightfv(GL_LIGHT0, GL_DIFFUSE, {r, g, b})` → Sets diffuse light color
  - `glLightfv(GL_LIGHT0, GL_POSITION, {x, y, z, w})` → Sets light position
  - `glEnable(GL_LIGHTING)` → Enables lighting
  - `glEnable(GL_LIGHT0)` → Enables light source 0

## Conclusion
- OpenGL follows an event-driven pipeline with transformations, shading, and lighting features.
- Sample programs available in OpenGL reference books (Red Book, Blue Book).
- Understanding the pipeline is crucial for efficient graphics programming.
