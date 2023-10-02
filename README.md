Name : Armadya Hermawan <br>
NRP : 5025211243 <br>

# ComputerGraphics-3
## 2D Square From 2 Triangle
![Foto](./img/square.png)<br>
``` function draw() {

    gl.clearColor(0,0,0,1);  // specify the color to be used for clearing
    gl.clear(gl.COLOR_BUFFER_BIT);  // clear the canvas (to black)

    /* Set up values for the "coords" attribute */

    let  coords = new Float32Array( [ -0.5,-0.5, 0.5,-0.5, -0.5,0.5, 0.5,-0.5, -0.5,0.5, 0.5,0.5 ] );
   
    gl.bindBuffer(gl.ARRAY_BUFFER, bufferCoords);
    gl.bufferData(gl.ARRAY_BUFFER, coords, gl.STREAM_DRAW);
    gl.vertexAttribPointer(attributeCoords, 2, gl.FLOAT, false, 0, 0);
    gl.enableVertexAttribArray(attributeCoords);
   
    /* Set up values for the "color" attribute */
   
    let  color = new Float32Array( [ 0,0,1, 0,1,0, 1,0,0, 0,1,0, 1,0,0, 0,0,1] );

    gl.bindBuffer(gl.ARRAY_BUFFER, bufferColor);
    gl.bufferData(gl.ARRAY_BUFFER, color, gl.STREAM_DRAW);
    gl.vertexAttribPointer(attributeColor, 3, gl.FLOAT, false, 0, 0);
    gl.enableVertexAttribArray(attributeColor);
   
    /* Draw the triangle. */
   
    gl.drawArrays(gl.TRIANGLES, 0, 6);

}
```

## Show Another Side Of The 3d Cube
![Foto](./img/cube.png)<br>
```
        //drawPrimitive(gl.TRIANGLE_FAN, [255, 0, 0, 1], [0, -0.4, 0, 0.5, -0.2, 0, 0.5, 0.3, 0, 0, 0.1, 0]); // front right side (red)
        drawPrimitive(gl.TRIANGLE_FAN, [0, 255, 0, 1], [-0.5, -0.2, -0.5, -0.5, 0.3, -0.5, 0, 0.1, -0.5, 0, -0.4, -0.5]); // front left side (green)
        drawPrimitive(gl.TRIANGLE_FAN, [0, 0, 255, 1], [-0.5, 0.3, 0.5, -0.5, -0.2, 0.5, 0, 0, 0.5, 0, 0.5, 0.4]); //back left side (blue)
        drawPrimitive(gl.TRIANGLE_FAN, [255, 165, 0, 1], [0.5, 0.3, 0.5, 0.5, -0.2, 0.5, 0, 0, 0.5, 0, 0.5, 0.4]); //back right side (magenta)
        drawPrimitive(gl.TRIANGLE_FAN, [255, 192, 203, 1], [-0.5, -0.2, 0.5, 0, -0, 0.5, 0.5, -0.2, 0.5, 0, -0.4, 0.4] ); //base (teal) 
```
