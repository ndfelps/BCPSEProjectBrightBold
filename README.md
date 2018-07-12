# BCPSEProject: THEME-608 Fix for Bright & Bold Theme

The goal of this project is to fix THEME-608 for the Bright & Bold theme. The issue that is occurring is within the currency list dropdown menu. When there are too many currencies (this varies based on the viewport size), some of the currencies at the bottom of the list cannot be accessed because the list runs off the page.

## Reproducing The Issue

  1. Apply Bright and Bold through your store
  2. Create enough currencies to cause the issue (I created 18)
  3. Attempt to access the currency selector dropdown menu
  
  ### Expected Result
  
  You are able to select any of the available currencies
  
  ### Actual Result
  
  Currencies near the bottom of the list cannot be accessed
  
## The Solution

The solution for this issue is to limit the size of the currency dropdown, and to apply the value of scroll to the overflow attribute. I applied the following code to the theme.css file:

.CurrencyList {
  height: 250px;
  overflow: scroll;
}
 
 I applied this code, along with some comments for details on lines 556-561.

## Testing

Here is a pretty brief video of me testing this fix: https://youtu.be/xZ3XcRTJj2I

This fix didn't really impact any other part of the store, and does still work fine on stores that have a small number of currencies.
