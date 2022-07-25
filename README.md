# [Live Demo](https://zenab12.github.io/Freecodecamp-Magazine/)
## Tips i learned While coding this task :
- The `loading` attribute on an `img` element can be set to `lazy` to tell the browser not to fetch the image resource until it is needed (as in, when the user scrolls the image into view). As an additional benefit, lazy loaded elements will not load until the non-lazy elements are loaded - this means users with slow internet connections can view the content of your page without having to wait for the images to load.

- The `Referer` HTTP header contains information about the address or `URL` of a page that a user might be visiting from. This information can be used in analytics to track how many users from your page visit freecodecamp.org, for example. Setting the `rel` attribute to `noreferrer` omits this information from the HTTP request. Give your a element a rel attribute set to noreferrer.

-if i creat `html` selector and give it a `font-size` property set to `62.5%`. This will set the default font size for your web page to 10px (the browser default is 16px).

This will make it easier for you to work with rem units later, as 2rem would be 20px

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
