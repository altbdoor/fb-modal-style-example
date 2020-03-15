# fb-modal-style-example

A small test ground to try to see how Facebook does its modal-ish interface for creating new post.


### Notes:

- We really need to know where the scrollable, parent container is. With Facebook, they have the whole body as a scrollable element. So the modal backdrop could be added with `position: fixed`.

- For complex, gridded layouts and such, it will get quite tricky. Because using a `position: fixed` modal backdrop will mean that the background is not scrollable, but the modal content is scrollable. Using a `position: absolute` modal backdrop is possible, but will need a parent that is `position: relative`, to properly wrap over the whole scrollable content.

- We can use [`IntersectionObserver`](https://developer.mozilla.org/en-US/docs/Web/API/Intersection_Observer_API) to detect when user has scrolled away instead, which is a lot better than [`getBoundingClientRect`](https://developer.mozilla.org/en-US/docs/Web/API/Element/getBoundingClientRect). Only problem is, `IntersectionObserver` is not supported in IE11, and will require a [polyfill](https://github.com/w3c/IntersectionObserver).
