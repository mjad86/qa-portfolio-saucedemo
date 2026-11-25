# BUG-0XX: Product not displayed in cart until page refresh

**Related test case:** TC-003
**Module:** Cart
**Severity:** Medium
**Priority:** Medium
**Status:** Open
**Environment:** Chrome versión 158.0.8127.88 (Build oficial) (64 bits)/M. Edge Version 158.0.4370.33, windows 10, Desktop
**Date found:** [fecha]

## Description
After clicking "Add to cart", the product is added with the correct price, but it is not displayed in the cart until the page is refreshed or the user navigates to another module.

## Steps to reproduce
1. Open a product page
2. Click "Add to cart"
3. Open the cart (or look at the cart view) without refreshing

## Expected result
The product appears in the cart immediately after being added.

## Actual result
The cart does not show the product. It appears only after refreshing the page or changing module.

## Frequency
Always: 3 de 3 intentos

## Additional notes
Contador del carrito: se actualiza
Otros navegadores: se reproduce

## Evidence
![Before refresh](../evidence/BUG-005before_refresh.png)
![After refresh](../evidence/BUG-005after_refresh.png)
[Video evidence (10s)](../evidence/BUG-005.mp4)