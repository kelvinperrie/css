
flexbox - see flex.html

* one dimensional - can makes rows OR columns
* putting `display: flex` on the container makes the direct descendants a flex item
* `flex-direction` can be either row or column (or row-reverse or column-reverse)
* `flex-wrap` lets items move to next line if they run out of space: wrap | nowrap | wrap-reverse. Flex items that wrap turn into their own flex line and may not line-up (width wise) with the above line
* if you have a height on the container then items will stretch vertically to fit that container (unless you give the items a specific height)

grid - see grid.html

* two dimensional - has rows AND columns
* putting `display: grid` on the container makes it a grid, also can use `inline-grid` = inline / not full screen
* define the grid a couple of ways:
  * `grid-template-columns: 1fr 1fr 2fr` where free = free space, makes 3 cols, where the last is half the available space
  * `grid-template-rows: 1fr 1fr 1fr`
  * or `grid-template-columns: repeat(3, 1fr)` <- make 3 cols
  * can create named areas in a grid by
  ```
            grid-template-areas: 
                "header header header header"
                "main main . sidebar"
                "footer footer footer footer";
  ```
  to create four cols and three rows
* grid items can be 
  * inserted by area
  ```
          .item-a {
            grid-area: header;
        }
  ```
  * or by index
  ```
          .item-f {
            grid-column: 5;
            grid-row: 3;
        }
  ```
  * and can span multiple grid cells either by saying what col/row it should end on or how many it should span
  ```
          .item-e {
            grid-column: 3 / span 4;
            grid-row: 3 / 4;
        }
  ```
  * an item is individually aligned using `jusitfy-self` (inline-horizontal) and `align-self` (block/vertical)
 * make the gaps between the rows and cols bigger using `column-gap: 15px;` and `row-gap: 15px;`
