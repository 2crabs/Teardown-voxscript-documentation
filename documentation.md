# Voxscript functions

## **CreateMaterial**
Material  = CreateMaterial("material type", red, green, blue, transparency, metallic, roughness )

### arguments
`Material (string)` - Type of material. Can be glass, wood, masonry, plaster, metal, heavymetal, rock, dirt, foliage, or unphysical.  
`red (float)` - Red value of material. On a range of 0 to 1.  
`green (float)` - Green value of material. On a range of 0 to 1.  
`blue (float)` - Blue value of material. On a range of 0 to 1.  
`transparency (float)` - Transparency of material. On a range of 0 to 1.  
`metallic (float)` - How metallic the material is. On a range of 0 to 1.  
`roughness (float)` - roughness of material. On a range of 0 to 1.

Return value  
`material (material)` - The material created.

```lua
metal = CreateMaterial("rock",0.5,0.5,0.5,1,1,0.1)
```

## **CreateBrush**
brush  = CreateBrush("filepath")

### arguments
`filepath (string)` Path to .vox file used.

Return value  
`brush (brush)` - The brush created.

```lua
fence = CreateBrush("LEVEL/fence.vox")
```


## **FlipBrush**
FlipBrush(brush, "axis")

### arguments
`brush (brush)` Which brush to flip.  
`axis (string)` axis to flip brush over.

Return value  
`none`

```lua
FlipBrush(fence,"x")
```