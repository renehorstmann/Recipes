
# Gnocchi

![result](build/Gnocchi.jpg "Build")

## Source code
Run the following code to cook one meal:

```c
#include <kitchen.h>

// recipe below main
void cook_potatoes(Potatoes potatoes);

int main() {

    // ingredients
    Portion *potatoes = Potatoes_g(150);
    Portion *flour    = Flour_g(50);
    Portion *egg      = Egg(1);

   
    // cook potatoes (see below)
    cook_potatoes(potatoes);

    // make gnocci dough
    bowl_include(potatoes);
    bowl_include(flour);
    bowl_include(egg);
    bowl_include(SALT);
    masher_mash(bowl_content());
    Portion *dough = bowl_content());

    // divide into gnocchis
    roll_out(dough);
    knife_cut_into_pieces(dough);
    fork_press(dough);
    
    // fry gnocchis
    pan_heat_level(7);
    pan_include(2 * SPOON_OLIVE_OIL);
    pan_include(dough);
    for(int i=0; i<2; i++) {
        pan_turn_content();
        hourglass_wait_min(3);
    }

    serve();
}

void cook_potatoes(Potatoes potatoes) {
    pot_fill_water_L(1);
    pot_heat_level(9);
    knife_peel(potatoes);
    pot_wait_until_boil();
    pot_include(potatoes);
    hourglass_sleep_min(15);
    pot_pour_out();
}

```
