# Tomato Sauce

![result](build/Tomato_Sauce.jpg "Build")

## Source code
Run the following code to cook a sauce:

```c
#include <kitchen.h>

// recipe below main
void peel_tomatoes(Tomatoes tomatoes);

int main() {

    // ingredients
    Tomatoes        tomatoes = 4;
    Garlic          garlic   = 1;
    Onion           onion    = 1;
    Basil           basil    = 6;
    RedWine         wine     = ML(100);
    BalsamicVinegar vinegar  = ML(25);

    
    peel_tomatoes(tomatoes);
    knife_cut_into_pieces(tomatoes);
    knife_cut_into_slices(garlic);
    knife_cut_into_slices(onion);

    pot_heat_level(9);
    pot_include(3 * SPOON_OLIVE_OIL);
    pot_include(garlic);
    pot_include(onion);
    hourglass_wait_min(2);

    pot_include(wine);
    pot_include(tomatoes);
    hourglass_wait_min(3);

    pot_include(TEA_SPOON_SUGAR);
    pot_include(2 * TEA_SPOON_SALT);
    pot_include(vinegar);
    pot_heat_level(5);
    hourglass_wait_min(20);

    knife_cut_into_pieces(basil);
    hand_mixer_blend(pot_content());
    pot_include(basil);
    hourglass_wait_min(5);
    
    serve();
}

void peel_tomatoes(Tomatoes tomatoes) {
    pot_fill_water_L(1);
    pot_heat_level(9);
    knife_cut_in(tomatoes);
    pot_wait_until_boil();
    pot_include(tomatoes)
    hourglass_wait_min(1.5)
    pot_pour_out();
    cool_under_water(tomatoes);
    pull_off_skin(tomatoes);
}

```
