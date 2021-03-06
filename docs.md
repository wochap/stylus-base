## Boilerplate docs

#### What naming convention use?

Use [Bemit](http://csswizardry.com/2015/08/bemit-taking-the-bem-naming-convention-a-step-further/)

```css
/* components */
.c-blog {}
.c-blog__title {}

.c-blog-post {}
.c-blog-post__time {}

/* modifiers */
.c--featured {}
/* states */
.is-stateOfComponent {}
.has- {}

/* objects */
.o-media {}

/* theme */
.t-theme-name {}
.t-light {}

/* utilities */
.u-wrapper {}

/* responsive classes */
.u-hidden\@lg {}
```

#### How do you order your CSS properties?

```css
.selector {
    /* other */
    /* box model */
    /* typography */
    /* position */
}
```

#### Namespaces

[Methods for Theming](https://speakerdeck.com/csswizardry/4half-methods-for-theming-in-s-css)

`o-`: Signify that something is an Object, and that it may be used in any number of unrelated contexts to the one you can currently see it in. Making modifications to these types of class could potentially have knock-on effects in a lot of other unrelated places. Tread carefully.

`c-`: Signify that something is a Component. This is a concrete, implementation-specific piece of UI. All of the changes you make to its styles should be detectable in the context you’re currently looking at. Modifying these styles should be safe and have no side effects.

`u-`: Signify that this class is a Utility class. It has a very specific role (often providing only one declaration) and should not be bound onto or changed. It can be reused and is not tied to any specific piece of UI. You will probably recognise this namespace from libraries and methodologies like SUIT.

`t-`: Signify that a class is responsible for adding a Theme to a view. It lets us know that UI Components’ current cosmetic appearance may be due to the presence of a theme.

`s-`: Signify that a class creates a new styling context or Scope. Similar to a Theme, but not necessarily cosmetic, these should be used sparingly—they can be open to abuse and lead to poor CSS if not used wisely.

`is-, has-`: Signify that the piece of UI in question is currently styled a certain way because of a state or condition. This stateful namespace is gorgeous, and comes from SMACSS. It tells us that the DOM currently has a temporary, optional, or short-lived style applied to it due to a certain state being invoked.
