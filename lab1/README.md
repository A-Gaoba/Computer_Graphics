This lesson talking about how to create a window in Computer graphics using OpenGL
First we need to initialize GLUT with
glutInit(&argc, argv);
to use its features. We then set the display mode to glutInitDisplayMode(GLUT_DOUBLE | GLUT_RGBA);
GLUT_DOUBLE means two buffers when one buffer is rendered, rendering in the other buffer (two buffers cycle through render-render) and the Color Mode rendered by GLUT_RGBA.
Set window size glutInitWindowSize(Scr_Width, Scr_Height); , window position glutInitWindowPosition(x , y); with the top left corner of the screen as the starting point, create a window glutCreateWindow(" "); and name it "Great Window". Set color glClearColor(red, green, blue, alpha); , options from left to right: red, green, blue, transparency, (0.1f, 0.1f, 0.1f, 0.0f) Dark purple.
Set the display callback function to glutDisplayFunc(RenderSceneCB); value of RenderSceneCB because the program is running on the window system, so most of the work is done through a callback, where RenderSceneCB is the callback needed for rendering.
RenderSceneCB callback function First use the clear color (GL_COLOR_BUFFER_BIT) set by glClearColor() to clear the window's current color,
Then replace the current display buffer that matches the GLUT_DOUBLE mode set by glutInitDisplayMode and display the two buffers in a loop.
glutMainLoop(); This function indicates that the operation of the inner loop is running, that is, the event of entering the listen window occurs, call the callback function for processing, this program only has a display callback function (RenderSceneCB) for continuous callback
