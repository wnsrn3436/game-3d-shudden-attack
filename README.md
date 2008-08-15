# 3D Shudden Attack

A first person shooter made with GameMaker's built in d3d functions. It pays homage to the popular FPS Sudden Attack, with one letter of the name changed.

<p>
  <img src="docs/screenshots/screenshot-1.png" width="480" alt="Gameplay">
</p>


## How to play

Download from Releases and run it.

Move forward and back with W and S and turn the view with A and D. Fire with the left mouse button. Monsters stand still until you get close, then chase you. Remaining lives are shown in the window title bar.


## How it works

The player object turns on 3D mode when it is created and, in its Draw event every frame, resets the view from its own position and facing direction. The floor and sky are two room sized planes laid above and below.

Walls are objects placed in a 2D room that each raise themselves into 3D. One parent object handles drawing by calling the wall drawing function, and the horizontal and vertical wall objects are its children, which on creation set only the two end coordinates, the height and the texture, based on their own position.

```gml
// horizontal wall
{
  x1 = x-16;
  x2 = x+16;
  y1 = y;
  y2 = y;
  z1 = 32;
  z2 = 0;
  tex = background_get_texture(wall);
}
```

So building a map is just laying out wall objects in a top down 2D room.


## Files

| Path | Contents |
|---|---|
| `source/3d-shudden-attack.gmk` | Original project file |
| `source/lib/AI.lib` | Action library used for monster detection. Put it in GameMaker's `lib` folder or the project will not open |
| `source/split/` | Text tree produced by GmkSplitter |
| `docs/screenshots/` | Screenshots |
| Releases | Distributed build |


## Credits

`source/lib/AI.lib` is an action library made by 멍멍이 (qw5628).


## License

CC BY-NC-ND 4.0. Unmodified copies may be shared for noncommercial purposes with attribution. Modified versions and commercial use are not allowed. Bundled libraries, graphics, sounds, and maps made by other people keep their own rights. See [LICENSE](LICENSE).
