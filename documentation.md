# Voxscript functions
[CreateMaterial](documentation.md#CreateMaterial)  
[CreateBrush](documentation.md#CreateBrush)  
[FlipBrush](documentation.md#FlipBrush)  
[TranslateBrush](documentation.md#TranslateBrush)  
[GetBrushSize](documentation.md#GetBrushSize)  
[Material](documentation.md#Material)  
[Pos](documentation.md#Pos)  
[Box](documentation.md#Box)  
[Sphere](documentation.md#Sphere)  
[Expand](documentation.md#Expand)  
[LoadImage](documentation.md#LoadImage)  
[GetImageSize](documentation.md#GetImageSize)  
[GetImagePixel](documentation.md#GetImagePixel)  
[Heightmap](documentation.md#Heightmap)  
[Vox](documentation.md#Vox)

## **CreateMaterial**
Material  = CreateMaterial("material type", red, green, blue, alpha, reflective, shiny, metallic, emission)

### arguments
`Material (string)` - Type of material. Can be glass, wood, masonry, plaster, metal, heavymetal, rock, dirt, foliage, or unphysical.  
`red (float)` - Red value of material on a range of 0 to 1.  
`green (float)` - Green value of material on a range of 0 to 1.  
`blue (float)` - Blue value of material on a range of 0 to 1.  
`alpha (float)` - Alpha value of material on a range of 0 to 1.  
`reflective (float)` - How reflective the material is on a range of 0 to 1.  
`shiny (float)` - How shiny the material is on a range of 0 to 1.  
`metallic(float)` - How metallic the material is on a range of 0 to 1.   
`emission(float)` - The emission of the material on a range of 0 to 32.

### Return value  
`material (material)` - The material created.

```lua
metal = CreateMaterial("metal",0.5,0.5,0.5,1,0.2,0.8,0)
```

## **CreateBrush**
brush  = CreateBrush("filepath")

### arguments
`filepath (string)` Path to .vox file used.

### Return value  
`brush (brush)` - The brush created.

```lua
fence = CreateBrush("LEVEL/fence.vox")
```


## **FlipBrush**
FlipBrush(brush, "axis")

### arguments
`brush (brush)` Which brush to flip.  
`axis (string)` axis to flip brush over.

### Return value  
`none`

```lua
FlipBrush(fence,"x")
```

## **TranslateBrush**
TranslateBrush(brush, x, y, z)

### arguments
`brush (brush)` Which brush to translate.  
`x (int)` How much to translate in the x direction in voxels.  
`y (int)` How much to translate in the y direction in voxels.  
`z (int)` How much to translate in the z direction in voxels.

Return value  
`none`

```lua
TranslateBrush(planks, 12, 0, 3)
```

## **GetBrushSize**
sizex, sizey, sizez = GetBrushSize(brush)

### arguments
`brush (brush)` Which brush to get size of.

### Return value  
`sizex (int)` - The size of the brush in the x direction.  
`sizey (int)` - The size of the brush in the y direction.  
`sizez (int)` - The size of the brush in the z direction.

```lua
local x, y, z = GetBrushSize(barrel)
```

## **Material**
Material(brush/material)

### arguments
`brush/material (brush/material(palette index))` Which brush/material to set to be currently used.

### Return value  
`none`  
Sets which material or brush to be used for the next objects placed.

```lua
--Creates dirt material and sets that as the current material
dirt = CreateMaterial("dirt", 0.26, 0.23, 0.20, 1, 0, 0.1)
Material(dirt)

--Sets material to be index 255 on the palette
Material(255)
```

## **Pos**
?

## **Box**
Box(startX, startY, startZ, endX, endY, endZ)

### arguments
`startX (int)` - The starting position in the x direction.  
`startY (int)` - The starting position in the y direction.  
`startZ (int)` - The starting position in the z direction.  
`endX (int)` - The ending position in the x direction.  
`endY (int)` - The ending position in the y direction.  
`endZ (int)` - The ending position in the z direction.

Return value  
`none`

```lua
Vox(0,0,0)
Box(0,0,0,10,10,10)
```

## **Sphere**
Sphere(middleX, middleY, middleZ, radius)

### arguments
`middleX (int)` - The middle position in the x direction.  
`middleY (int)` - The middle position in the y direction.  
`middleZ (int)` - The middle position in the z direction.  
`radius (int)` - The radius in voxels.

### Return value  
`none`

```lua
Vox(0,0,0)
Sphere(10,10,10,25)
```

## **Expand**
?

## **LoadImage**
image = LoadImage("filepath")

### arguments
`filepath (string)` - The path to the the image loaded. 

Return value  
`image (image)` - The image loaded.

```lua
MainImage = LoadImage("MOD/images/image1.png")
```

## **GetImageSize**
sizeX, sizeY = GetImageSize(image)

### arguments
`image (image)` - The image to get the size of.

### Return value  
`sizeX (int)` - The size of the image in pixels in the x direction.  
`sizeY (int)` - The size of the image in pixels in the y direction.

```lua
local x, y = GetImageSize(FenceImage)
```

## **GetImagePixel**
red, green, blue, alpha = GetImagePixel(image)

### arguments
`image (image)` - The image to use.

### Return value  
`red (float)` - The red value of the pixel in a range of 0 to 1.  
`green (float)` - The green value of the pixel in a range of 0 to 1.  
`blue (float)` - The blue value of the pixel in a range of 0 to 1.  
`alpha (float)` - The alpha of the pixel in a range of 0 to 1.

```lua
local r, g, b, a = GetImagePixel(FenceImage)
```

## **Heightmap**
Heightmap(startX, startY, endX, endY, scale,hollow)

### arguments
`startX (int)` - The pixel in the image to start from in the x direction.  
`startY (int)` - The pixel in the image to start from in the y direction.  
`endX (int)` - The pixel in the image to end in the x direction.  
`endY (int)` - The pixel in the image to end in the y direction.  
`scale (float)` - How much to multiply the height.  
`hollow (bool)` - ?

### Return value  
`none`

```lua
Heightmap(x0, y0, x1, y1, heightScale, hollow==0)
```

## **Vox**
Vox(x, y, z, rotX, rotY, rotZ)

### arguments
`x (int)` - Where to place the vox in the x direction in voxels.  
`y (int)` - Where to place the vox in the y direction in voxels.  
`z (int)` - Where to place the vox in the z direction in voxels.  
`rotX` - How much to rotate the vox around the x axis in degrees.  
`rotY` - How much to rotate the vox around the y axis in degrees.  
`rotZ` - How much to rotate the vox around the z axis in degrees.

### Return value  
`none`  
Will create a compund out of all of the objects created below it until another Vox() is called.

```lua
Vox(0,20,0,0,45,0)
Box(0,0,0,1,10,1)
Box(2,0,0,3,10,1)
```
