# [Live Demo](https://zenab12.github.io/Freecodecamp-Magazine/)
## Tips i learned While coding this task :

### Here are the supported values for the `loading` attribute:
> - The `loading` attribute on an `img` element can be set to `lazy` to tell the browser not to fetch the image resource until it is needed (as in, when the user scrolls the image into view). As an additional benefit, lazy loaded elements will not load until the non-lazy elements are loaded - this means users with slow internet connections can view the content of your page without having to wait for the images to load.

> - `lazy`: Defer loading of the resource until it reaches a [calculated distance](https://web.dev/browser-level-image-lazy-loading/#distance-from-viewport-thresholds) from the viewport.
> - `eager`: Default loading behavior of the browser, which is the same as not
including the attribute and means the image is loaded as soon as
possible, regardless of where it's located on the page. While this is
the default, it can be useful to explicitly set this if your tooling
automatically adds `loading="lazy"` if there is no explicit value, or if your linter complains if it is not explicitly set.

## 🤩 Notes I learned from Freecodecamp about grid-template :

- in grid-template Use the minmax function to make your columns responsive on any device. The minmax function takes two arguments, the first being the minimum value and the second being the maximum. These values could be a length, percentage, fr, or even a keyword like max-content

- One option is the `grid-column` property for children, which is shorthand for grid-column-start and grid-column-end. The grid-column property tells the grid item which grid line to start and end at.There may be times where you are unsure of how many columns your grid will have, but you want an element to stop at the last column. To do this, you can use -1 for the end column.

- The CSS `repeat()` function is used to repeat a value, rather than writing it out manually, and is helpful for grid layouts. For example, setting the grid-template-columns property to repeat(20, 200px) would create 20 columns each 200px wide.

- If you wanted to add more social icons more than 5 , but keep them on the same row, you would need to update `grid-template-columns` to create additional columns. As an alternative, you can use the `grid-auto-flow property`.This property takes either row or column as the first value, with an optional second value of dense. grid-auto-flow uses an auto-placement algorithm to adjust the grid layout. Setting it to column will tell the algorithm to create new columns for content as needed. The dense value allows the algorithm to backtrack and fill holes in the grid with smaller items, which can result in items appearing out of order
- the auto-placement algorithm will kick in when you add a new icon element. However, the algorithm defaults the new column width to be auto, which will not match your current columns.
- You can override this with the grid-auto-columns property

-  you can create columns within an element without using Grid by using the `column-width` property.
- The `gap` property is a shorthand way to set the value of column-gap and row-gap at the same time. If given one value, it sets the column-gap and row-gap both to that value. If given two values, it sets the row-gap to the first value and the column-gap to the second.
- The `place-items` property can be used to set the `align-items` and `justify-items` values at the same time. The place-items property takes one or two values. If one value is provided, it is used for both the align-items and justify-items properties. If two values are provided, the first value is used for the align-items property and the second value is used for the justify-items property.
```


main {
  display: grid;
  grid-template-columns: minmax(2rem, 1fr) minmax(min-content, 94rem) minmax(2rem, 1fr);
  row-gap: 3rem;
}

.heading {
  grid-column: 2 / 3;
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  row-gap: 1.5rem;
}

.social-icons {
  display: grid;
  font-size: 3rem;
  grid-template-columns: repeat(5, 1fr);
  grid-auto-flow: column;
  grid-auto-columns: 1fr;
  align-items: center;
}
```

- > Magazines often use justified text in their printed content to structure their layout and control the flow of their content. While this works in printed form, justified text on websites can be an accessibility concern, for example presenting challenges for folks with dyslexia.
- > The `object-fit` property tells the browser how to position the element within its container. In this case, cover will set the image to fill the container, cropping as needed to avoid changing the aspect ratio.
- > The `::first-letter` pseudo-selector allows you to target the first letter in the text content of an element.

<!--
![Screenshot 2022-07-25 at 14-14-40 Magazine](https://user-images.githubusercontent.com/78083890/180775457-8bf42f4f-e37d-4e2e-9a89-fc37f5e8230e.png)
-->


## 🤩 Notes I learned from Maharatech about grid-template :
<aside >

## grid container :

`display:grid;` `grid-template-columns:`  `px` or `fr` or `min-content` or `max-content` or `minmax(minnumpx, maxnumpx)` or `fit-content(numpx)`  or `auto` or `repeat()`

`grid-auto-flow:row or column` created automatic but default option is row and it is used with `grid-auto-columns`; and `grid-auto-rows` 

`gap: row column` 

`***justify-content: end` or `right` related it’s related to language (English, arabic ,…)so `end` related to the end of font but `right` it will be in the right direction*** 

`**justify-items:center; align-items:center` mean width will be ignored and will be centered in it’s column horizontally and vertically 

`grid-template-colums:repeat(auto-fill,100px)` mean will create automatic column with container parent width but `auto-fit`  will create automatic column with count with child elements only.

`grid-template: template-area  template-rows template-area  template-rows / template-columns` #two rows
*`#if we use grid-template with repeat function will damage area and columns so we should use units not functions`   as this will not work `.element{grid-template: “area-1 area-2” 100px “. area-4” 100px/repeat(2,50%)` but to make it work we use this instead 
`.element{grid-template: “area-1 area-2” 100px “. area-4” 100px/50% 50%` 
`grid-auto-flow: column or row dense`  dense mean full any empty space.

### grid items we use this :

`grid-column-start:1; grid-template-end :span 2;`#mean take two space and end at column num3. and we can use shorthand rule called `grid-column: column-start/column-end` 

`grid-area: row-start / column-start/ row-end / column-end`   or `grid-area: area-name.` 

#if we give in parent in lines or columns names as `[red-1-col] 100px [red-2-col] 200px`   and used inside red div we will give for `grid-area:red;` and it will work***

</aside>


> - if i creat `html` selector and give it a `font-size` property set to `62.5%`. This will set the default font size for your web page to 10px (the browser default is 16px). This will make it easier for you to work with rem units later, as 2rem would be 20px
> - The `Referer` HTTP header contains information about the address or `URL` of a page that a user might be visiting from. This information can be used in analytics to track how many users from your page visit freecodecamp.org, for example. Setting the `rel` attribute to `noreferrer` omits this information from the HTTP request. Give your a element a rel attribute set to noreferrer.
