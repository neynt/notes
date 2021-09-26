## How the hell do you organize your music?

There are so many dimensions to consider.

Oh here's an idea:

- one flat directory of all files
- valid file formats:
  - singles: `<artist> - <title>.<ext>`
  -          `<artist> - <album> - <title>.<ext>`
  - albums:  `<artist> - <album> - <index> - <title>.<ext>`
  - for multi artist, separate artists by + or &
  - all other metadata stored in an sqlite database in the same directory
  - title can have alternative title / qualifier in parens
