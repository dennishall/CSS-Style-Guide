# CSS Development Guide

1.     Do not use inline styles, neither the block kind (`<style></style>`), nor the tag attribute kind (`style=””`).
2.     Implied by #1 – use external stylesheets
3.     Expansion of #2 – Most projects should use a global stylesheet plus section-specific stylesheets. Some projects may use a single stylesheet for all styles.
4.     Do not use @import, unless the backend system will ‘inline’ the file
5.     Use semantically descriptive classes and ids. (I.e., “.redbox” is bad, “.errorMessage” is good.)
6.     Keep it organized. Use project-standard comment blocks to demarcate major sections and subsections (may vary somewhat by project):
  1.     Reset
  1.     Base styling
  1.     Header
  1.     Nav
  1.     Main content
         *     Content type or item
         *     Other content type or item
         *     Etc.
  1.     Aside
  1.     Footer
7.    Use the least specific selector expression possible
a.     Avoid !important
b.     Introduce new namespaced classnames, even new wrapper elements, if needed (and possible) so as to reduce cascade override hell (most commonly happens with nested lists) – example: “.mymodule li li” -> “.mymodule-subitem”
8.     Abstract repeating visual patterns, use them as base classes and extend and or override them as needed, using a more specific classname.
9.     Do not use javascript in css (“:expression(…)”) – if absolutely needed, write it in an actual js file, and either conditionally serve it to the affected browser(s), or wrap the code in a lambda that is conditionally executed only in the affected browser(s).
10. Use shorthands unless overriding an inherited style (for layout properties, there’s the “trouble” mnemonic: top, right, bottom, left)
11. Use sprites, and consider using data-urls and application cache.
12. When using sprites or other image-replacement styling, include fallback text content as appropriate (it is usually appropriate) – think “alt tag”
13. Use *property to target ie6+7, follow with _property to exclusively target ie6 if needed. Although “hacks” are hotly debated, they preserve specificity and facilitate maintainability.
14. Specify units for non-zero properties (0 is 0, but 1 can be px, em, in)
15. Do not specify a unitsfor zero (i.e., “0px” is bad)
16. Use ids for content that will never repeat per page, use classnames for elements that do repeat per page – as needed for either.
17. Favor classnames over ids.
18. Judiciously choose whether to use descendant selectors or namespaced classnames. The performance overhead of descendant selectors is negligible.
  1.     Descendant selector/ root classname example: “.bio img {float:left;}”
  1.     Namespaced classname example: “.bio-img {float:left;}”
19. Property group order does not matter, but properties should be grouped together:
  1.     layout-related: position, float, width, height, padding, margin, border
  1.     font-related
  1.      backgrounds
  1.     vendor-prefixed and filters (-webkit-, -moz-, -o-, -ms-)
  1.     hacks follow whatever property they override
20.  Never code text in all caps in the markup (and usually not all lowercase either). Always choose an appropriate casing: either sentence case or title case. Use text-transform to achieve the desired casing.
 
Project-specific
1.     Property rules per line (all or one): one
2.     Grouped selectors should appear on (the same line, separate lines): separate lines
3.     Indentation: two spaces