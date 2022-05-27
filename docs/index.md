# Home

For full documentation visit [mkdocs.org](https://www.mkdocs.org).

## Starting commands

* `mkdocs new [dir-name]` - Create a new project.
* `mkdocs serve` - Start the live-reloading docs server.
* `mkdocs build` - Build the documentation site.
* `mkdocs -h` - Print help message and exit.

## Write code snippets

```c linenums="1" hl_lines="7 8"
#include <stdio.h>
#include <stdlib.h>

#define N_MARKS 5

int main (int argc, char const *argv[]) {
    double marks[N_MARKS] = {14, 12.5, 13, 16, 9.5};
    double total_marks = 0., average = 0.;

    for (int i = 0; i < N_MARKS; ++i) {
        total_marks += marks[i];
    }

    average = total_marks / N_MARKS;

    if (average < 10) {
        printf("FAILED\n");
    } else {
        printf("SUCCEEDED\n");
    }

    return EXIT_SUCCESS;
}
```

## Fancy blockquotes

Simply neat.

### With default title

!!! tip
    Chase laser. Licks paws throwup on your pillow, sit on the laptop, lick the plastic bag. Cat not kitten around scamper hiss at vacuum cleaner. Licks paws throwup on your pillow, sit on the laptop, lick the plastic bag.

### With custom title

!!! success "You got it"
    Chase laser. Licks paws throwup on your pillow, sit on the laptop, lick the plastic bag. Cat not kitten around scamper hiss at vacuum cleaner. Licks paws throwup on your pillow, sit on the laptop, lick the plastic bag.

### Collapsible please

??? question
    Chase laser. Licks paws throwup on your pillow, sit on the laptop, lick the plastic bag. Cat not kitten around scamper hiss at vacuum cleaner. Licks paws throwup on your pillow, sit on the laptop, lick the plastic bag.
    
## Formatting

You can use ++cmd+c++ then ++cmd+v++ to get your shit done.


## Using card grids
<div class="grid cards" markdown>

- :fontawesome-brands-html5: __HTML__ for content and structure
- :fontawesome-brands-js: __JavaScript__ for interactivity
- :fontawesome-brands-css3: __CSS__ for text running out of boxes
- :fontawesome-brands-internet-explorer: __Internet Explorer__ ... huh?

</div>

## Include math in your website

The homomorphism $f$ is injective if and only if its kernel is only the 
singleton set $e_G$, because otherwise $\exists a,b\in G$ with $a\neq b$ such 
that $f(a)=f(b)$.

$$
\operatorname{ker} f=\{g\in G:f(g)=e_{H}\}{\mbox{.}}
$$
