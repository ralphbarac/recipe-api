# recipe-api
Documentation for my personal recipe API

This Recipe API is organized around REST. It has predictable resource-oriented URLs, returns JSON-encoded responses, and uses standard HTTP response codes, authentication, and verbs.

Note that there are only a few recipes in the database currently, however more are being added every day.

A GraphQL implementation is also coming soon, as are specific error response codes (internal server error means the recipe or ingredient doesn't exist).

### Searching for a Recipe

#### By Name

Generic

```
curl https://ralphbarac.com/recipe/<string:name>
```

Example

```
curl https://ralphbarac.com/recipe/chicken
```

Response

```
[{"name": "Beer Can Chicken", "servings": 6, "prepTime": 10, "cookTime": 75, "ingredients": [{"ingredient": {"name": "Salt"}, "quantity": 1.0, "unit": "tsp"}, {"ingredient": {"name": "Pepper"}, "quantity": 1.0, "unit": "tsp"}, {"ingredient": {"name": "Paprika"}, "quantity": 1.0, "unit": "tbsp"}, {"ingredient": {"name": "Whole Chicken"}, "quantity": 1.0, "unit": null}, {"ingredient": {"name": "Beer"}, "quantity": 12.0, "unit": "oz"}, {"ingredient": {"name": "Brown Sugar"}, "quantity": 1.0, "unit": "tbsp"}, {"ingredient": {"name": "Garlic Powder"}, "quantity": 1.0, "unit": "tsp"}, {"ingredient": {"name": "Chili Powder"}, "quantity": 0.5, "unit": "tsp"}], "steps": [{"number": 1, "text": "Preheat oven to 425F. Place a small roasting pan on a baking dish to prevent spills. (Note: Can also do this for same amount of time on high heat barbecue)."}, {"number": 2, "text": "Remove any giblets from the chicken if it has any and pat it dry with paper towels."}, {"number": 3, "text": "Open the can of beer and pour about 1/4 of it in the roasting pan and set the can of beer in the center of the roasting pan."}, {"number": 4, "text": "Mix all the rub ingredients together in a bowl, drizzle olive oil over the chicken, and rub the spices into the chicken."}, {"number": 5, "text": "Place the chicken upright over the beer can. Use the chicken legs as support to prevent the chicken from falling over."}, {"number": 6, "text": "Transfer the roasting pan into the oven. Bake for about 1 hour and 15 minutes or until cooked through. If using a meat thermometer, internal temperature should read 165F."}, {"number": 7, "text": "Transfer the done chicken to a cutting board and cover with aluminum foil. Let it sit for 15 minutes before carving."}]}]
```

#### By ID

Generic

```
curl https://ralphbarac.com/recipe/<int:id>
```

Example

```
curl https://ralphbarac.com/recipe/2
```

Response

```
{"name": "Italian Sausage Orzo", "servings": 6, "prepTime": 15, "cookTime": 25, "ingredients": [{"ingredient": {"name": "Salt"}, "quantity": 0.125, "unit": "tsp"}, {"ingredient": {"name": "Pepper"}, "quantity": 0.125, "unit": "tsp"}, {"ingredient": {"name": "Water"}, "quantity": 6.0, "unit": "cups"}, {"ingredient": {"name": "Chicken Bouillon"}, "quantity": 1.0, "unit": "cube"}, {"ingredient": {"name": "Italian Sausage"}, "quantity": 6.0, "unit": null}, {"ingredient": {"name": "Sweet Onion"}, "quantity": 0.5, "unit": "cups"}, {"ingredient": {"name": "Basil"}, "quantity": 0.33, "unit": "cups"}, {"ingredient": {"name": "Garlic Clove"}, "quantity": 2.0, "unit": null}, {"ingredient": {"name": "Orzo"}, "quantity": 1.5, "unit": "cups"}, {"ingredient": {"name": "Plum Tomato"}, "quantity": 3.0, "unit": null}, {"ingredient": {"name": "Sweet Red Pepper"}, "quantity": 0.5, "unit": "cups"}], "steps": [{"number": 1, "text": "In a large saucepan, bring water and bouillon to a boil. Stir in orzo; return to a boil. Cook until al dente, 8-10 minutes. Drain orzo, reserving 3/4 cup cooking liquid."}, {"number": 2, "text": "In a large skilled coated with oil, cook and crumble sausage with onion and garlic over medium heat until no longer pink, 6-8 minutes. Stir in tomatoes, roasted pepper, salt, pepper, pepper flakes, and orzo. Heat through over medium-low heat; stir in reserved cooking liquid to moisten if desired. Remove from heat; stir in basil."}]}
```

#### By Ingredient

Generic

```
curl https://ralphbarac.com/ingredient/<string:ingredient_in_recipe>
```

Example

```
curl https://ralphbarac.com/ingredient/tomato
```

Response

```
{"name": "Italian Sausage Orzo", "servings": 6, "prepTime": 15, "cookTime": 25, "ingredients": [{"ingredient": {"name": "Salt"}, "quantity": 0.125, "unit": "tsp"}, {"ingredient": {"name": "Pepper"}, "quantity": 0.125, "unit": "tsp"}, {"ingredient": {"name": "Water"}, "quantity": 6.0, "unit": "cups"}, {"ingredient": {"name": "Chicken Bouillon"}, "quantity": 1.0, "unit": "cube"}, {"ingredient": {"name": "Italian Sausage"}, "quantity": 6.0, "unit": null}, {"ingredient": {"name": "Sweet Onion"}, "quantity": 0.5, "unit": "cups"}, {"ingredient": {"name": "Basil"}, "quantity": 0.33, "unit": "cups"}, {"ingredient": {"name": "Garlic Clove"}, "quantity": 2.0, "unit": null}, {"ingredient": {"name": "Orzo"}, "quantity": 1.5, "unit": "cups"}, {"ingredient": {"name": "Plum Tomato"}, "quantity": 3.0, "unit": null}, {"ingredient": {"name": "Sweet Red Pepper"}, "quantity": 0.5, "unit": "cups"}], "steps": [{"number": 1, "text": "In a large saucepan, bring water and bouillon to a boil. Stir in orzo; return to a boil. Cook until al dente, 8-10 minutes. Drain orzo, reserving 3/4 cup cooking liquid."}, {"number": 2, "text": "In a large skilled coated with oil, cook and crumble sausage with onion and garlic over medium heat until no longer pink, 6-8 minutes. Stir in tomatoes, roasted pepper, salt, pepper, pepper flakes, and orzo. Heat through over medium-low heat; stir in reserved cooking liquid to moisten if desired. Remove from heat; stir in basil."}]}
```
