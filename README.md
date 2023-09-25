# Scriptless CSS Attack POC

Demo: https://anthony-dandrea.github.io/scriptless-attack-poc/

See network tab for "SECRET" characters discovered.

Largely inspired from [Mike West's talk](https://mikewest.org/2013/09/xss-no-the-other-s-cssconfeu-2013/).

General steps:
- Extract attribute(`content: attr(href)`) into psuedo element `:after`.
- Assign font to the characters in this element so only a single character has a size at a time. All others are 0x0.
- Add `background-url` style to scrollbar for sending findings to other server.
- Adjust width of container with animation that stops at width of link. Scrollbar will show if there are any characters shown in psuedo element.
