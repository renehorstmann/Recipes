
# Tortillas

![result](build/Tortillas.jpg "Build")

## Source code
Run the following code to cook four Tortillas:

```c
#include <kitchen.h>

static const bool got_tortilla_press = true;

int main() {

    // ingredients
    Portion *flour     = Flour_g(50);
    Portion *cornflour = CornFlour_g(50);
    Portion *oil       = OliveOil_ml(8);


    // make tortilla dough
    bowl_include(flour);
    bowl_include(cornflour);
    bowl_include(oil);
    bowl_include(WarnWater_ml(50));
    bowl_include(SALT);
    bowl_knead_min(5);
    Portion *dough = bowl_content();
    fridge_include(dough);
    hourglass_wait_min(15);

    // fry tortillas
    roll_out(dough);
    knife_cut_into_n_pieces(dough, 4);
    roll_out(dough);
    pan_heat_level(8);

    Portion *tortillas[4];

    for(int i=0; i<4; i++) {
        if(got_tortilla_press) {
            tortilla_press(dough);
        } else {
            rolling_pin_flatten(dough);
        }
        pan_include(dough);
        hourglass_wait_sec(45);
        pan_turn_content();
        hourglass_wait_sec(45);
        tortillas[i] = pan_content();
    }

    serve_portions(tortillas, 4);
}

```
