# OpenGL Graphics Programming Notes

## Introduction to OpenGL
- OpenGL (Open Graphics Library) is a cross-platform API for rendering 2D and 3D vector graphics.
- Used in gaming, simulations, and visualization applications.

## Setting Up OpenGL
### Installing Dependencies
```bash
sudo apt update
sudo apt install freeglut3-dev
```

### Initializing OpenGL
```cpp
#include <GL/glut.h>

void display() {
    glClear(GL_COLOR_BUFFER_BIT);
    glFlush();
}

int main(int argc, char** argv) {
    glutInit(&argc, argv);
    glutCreateWindow("OpenGL Setup Test");
    glutDisplayFunc(display);
    glutMainLoop();
    return 0;
}
```

## Basic OpenGL Concepts
### 1. **Rendering Pipeline**
- **Vertex Processing**: Transformations and lighting calculations.
- **Rasterization**: Converts primitives into fragments.
- **Fragment Processing**: Texturing, shading, and depth testing.

### 2. **Shaders**
- Written in GLSL (OpenGL Shading Language).
- Two main types:
  - **Vertex Shader**: Processes vertex attributes.
  - **Fragment Shader**: Determines pixel colors.

### 3. **Drawing Primitives**
```cpp
glBegin(GL_TRIANGLES);
glVertex2f(-0.5f, -0.5f);
glVertex2f( 0.5f, -0.5f);
glVertex2f( 0.0f,  0.5f);
glEnd();
```

## Transformations
- **Translation:** Moves objects.
- **Scaling:** Resizes objects.
- **Rotation:** Rotates objects around an axis.
```cpp
glTranslatef(1.0f, 0.0f, 0.0f);
glRotatef(45, 0, 0, 1);
glScalef(2.0f, 2.0f, 1.0f);
```

## Buffers
### Color Buffer
- Stores pixel color data.
- Cleared using `glClear(GL_COLOR_BUFFER_BIT);`

### Depth Buffer
- Handles object occlusion.
- Cleared using `glClear(GL_DEPTH_BUFFER_BIT);`

## Texture Mapping
- Load an image as a texture and map it onto a 3D model.
```cpp
glEnable(GL_TEXTURE_2D);
glBindTexture(GL_TEXTURE_2D, textureID);
```

## Lighting
- Uses **ambient**, **diffuse**, and **specular** components.
```cpp
glEnable(GL_LIGHTING);
glEnable(GL_LIGHT0);
```

## Double Buffering
- Prevents flickering by using two buffers.
```cpp
glutSwapBuffers();
```

## Event Handling
- **Keyboard Input:**
```cpp
void keyboard(unsigned char key, int x, int y) {
    if (key == 'q') exit(0);
}
```

- **Mouse Input:**
```cpp
void mouse(int button, int state, int x, int y) {
    if (button == GLUT_LEFT_BUTTON && state == GLUT_DOWN) {
        // Handle click
    }
}
```

## Conclusion
- OpenGL provides a powerful API for graphics rendering.
- Mastering shaders and transformations is key.
- Experiment with different primitives and lighting models.

---

**References:**
- [Official OpenGL Documentation](https://www.opengl.org/documentation/)
- [OpenGL Tutorials](https://learnopengl.com/)
