TiledSharp
==========
A .NET C# library for importing Tiled TMX tile maps

About TiledSharp
----------------
TiledSharp is a .NET C# library for importing TMX tilemaps and TSX tilesets
generated by Tiled, a tile map generation tool. The data is saved as a Map
object whose structure is to the TMX file, and is constructed from standard
.NET C#4 structures and objects.

As a generic TMX and TSX parser, TiledSharp does not use any XNA Game Studio
libraries. However, it can be used as a starting point for XNA game and library
development.

This project is currently under development.

Usage
-----
To import a TMX file into your C# application:

- Include TiledSharp into your project, either as source or a DLL
- Use the TiledSharp namespace:
```csharp
using TiledSharp;
```
- Create a Map object:
```csharp
var map = new Map("yourFile.tmx");`
```

TiledSharp supports both resource names and file paths, and should work as
expected in most situations. A detailed description will be placed in the wiki.

Map fields generally correspond with the XML structure:

```csharp
var map = new Map("yourFile.tmx");

var version = map.version;
var myTileset = map.tileset["myTileset"];
var myLayer = map.layer[2];
var hiddenChest = map.objectgroup["Chests"].object["hiddenChest"];
```

A detailed explanation of data access will be provided in the wiki.

__Please Note:__

Currently all tilesets, layers, object groups, and objects must have
unique names. In the future, I hope to use an interface that integrates Lists
and Dictionaries. For example, a map with one layer named "Ocean" and two
layers with identical name "Lake" could be accessed as follows:

```csharp
var ocean = map.layer["Ocean"]
var lake1 = map.layer["Lake"][0]
var lake2 = map.layer["Lake"][1]
```

Licensing
---------
I have not yet chosen a license, although I soon plan to release it under
one permitting public use and modification. Please feel free to use or modify
the code as necessary.

Contact
-------
Marshall Ward (<marshall.ward@gmail.com>)

Notes
-----
Tiled (<http://mapeditor.org>) is an open-source (GPL) tile map editor
developed and maintained by Thorbjørn Lindeijer.

Zlib decompression uses the Zlib implementation of DotNetZip v1.9.1.8
(<http://dotnetzip.codeplex.com>).
