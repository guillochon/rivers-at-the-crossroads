# Rivers at the Crossroads — OEIS A076906 and family

**https://guillochon.github.io/rivers-at-the-crossroads/**

A river flows in from infinity, crosses two perpendicular roads n times (never at the junction), and flows out to
infinity. Six OEIS entries count these meanders in different ways: directed or not, by where the river ends, by which
road it crosses first, and up to the eight symmetries of the crossroads ([A076906](https://oeis.org/A076906),
[A076907](https://oeis.org/A076907), [A077551](https://oeis.org/A077551), [A076875](https://oeis.org/A076875),
[A077550](https://oeis.org/A077550), [A077556](https://oeis.org/A077556)). The first three were known to n = 20, the
other three only to n = 7. All six now run to n = 37 (A077556 to n = 35), and four old terms turned out to be wrong:
A076875(6) = 146 (not 176), A077550(5) = 16 (not 21), A077550(7) = 110 (not 131), A077556(7) = 218 (not 239).
The method, the checks and the b-files are in
[oeis-results/A076906](https://github.com/guillochon/oeis-results/tree/main/A076906).

The page has a viewer, a gallery and the table of counts:

- **Viewer.** One river drawn large, with its itinerary: the order in which it crosses the four half-roads.
- **Gallery.** Every river for n up to 8: one per symmetry class (with the size of its class), or all directed
  rivers from the south-west quarter to the far quarter or to any quarter, for n up to 7.
- **Counts.** All six sequences to n = 37, with the new terms and the corrected ones marked.

## How it works

The page is static: `index.html` plus `data.js`, which holds the enumerated curves and the counts.

- **Curves.** Cut the plane along the four half-roads. In each quarter the river pieces form a non-crossing matching
  of that quarter's boundary points, and a valid river is a choice of matchings whose union is one path. The gallery
  lists them all and groups them into symmetry classes.
- **Drawing.** Squaring a quarter of the plane opens it into a half-plane, where each stretch of river between two
  crossings is a semicircle; taking the square root bends it back, so the river meets each road at a right angle.
- **Counts.** A Jensen-style transfer matrix whose cut line sweeps along the west road, down the north road, around
  the junction, down the south road and out along the east road (n = 36 in four minutes). The undirected and
  up-to-symmetry entries follow by formula; a mirror-symmetric river's halves are counted by
  [A005316](https://oeis.org/A005316) (open meanders) and [A076876](https://oeis.org/A076876) (meanders across two
  parallel roads).

Made by James Guillochon with Claude. The source lives in the oeis-sniper project (`viz/A076906/`); this repo holds
the published copy.
