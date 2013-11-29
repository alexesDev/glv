## GLV
GLV (Graphics Library of Views) is a GUI building toolkit written in C++ for Linux, OSX, and Win32. GLV is specifically designed for creating interfaces to real-time, multimedia applications using hardware accelerated graphics. GLV is designed to be lightweight and modular so as to make it easy to integrate with existing projects. Its only dependency is OpenGL. Although windowing is technically not a part of GLV, it does provide an abstraction layer for creating bindings to a particular windowing system for creating an OpenGL context and getting mouse and keyboard input. A binding to GLUT is currently provided. 

GLV observes a very minimal rectilinear design. Not only does this result in a straightforward presentation, but also optimizes many aspects of the underlying rendering system, such as number of vertices used, hit detection, and child cropping, making it run more efficiently. 

The main View class provides a common interface that all other widgets inherit from. There is no concept of "leaf" or "composite" views, as typically seen in other GUI toolkits, making the API easier to learn and extend. A unique feature of Views is that they support both early- and late-bound event handlers. Furthermore, each View can contain multiple late-bound event handlers per event type. This provides a general model for extending the behavior of Views, such as adding mouse-controlled translation or resizing to any View.

More information on http://mat.ucsb.edu/glv/

### Build on Linux

```
cd build
cmake ..
make -j8
```
