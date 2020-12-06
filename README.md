# pantry-project
A cooking project to suggest meals based on logged ingredients, use-by dates, etc.

## Ethos:
Make cooking as accessible as possible. Allow substitution of ingredients, suggest recipes based on user stock and ingredients due for expiry.

## Notes:

### Recipes:
```
{
  recipe: "Recipe Name",
  serves: value;
  ingredients: {
    recipePart: {
      keyIngredients: {
        ingredient: amount,
        ingredient: amount
      },
      optionalIngredients: {
        ingredient: amount,
        ingredient: amount
      }
    }
  },
  steps: {
    step1: "Description",
    step2: "Description"
  }
} 
```

Need to get shopping list: combined dict of ingredients and amounts. Sorted by ingredient type?

### User ingredients:
Log user's ingredients:
- `amount`
- `type` - meat/poultry, fresh herbs, fruit/veg, canned
- `{(useby/bestbefore): datetime, opened: datetime}` - if ingredient has no useby/bestbefore then leave dict empty. If user input that ingredient is opened add datetime to dict

### Ingredient info:
- `type`
- `openedWindow` - no. permissible days ingredient should be considered useable

### Recipe suggester:
Find recpes requiring the minimum no. new ingredients.

### Future implementations:
- A weekly recpie planner which considers user favourites and returns the most efficient use of ingredients
- Integration of online shopping cart APIs
