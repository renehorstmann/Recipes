# Tomato Sauce

![result](build/Tomato_Sauce.jpg "Build")

## Source code
Run the following code to cook a sauce:

```c
#include <kitchen.h>

// recipe below main
void peel_tomatoes(Portion *tomatoes);

int main() {

    // ingredients
    Portion *tomatoes = Tomatoes(4);
    Portion *garlic   = Garlic(1);
    Portion *onion    = Onion(1);
    Portion *basil    = Basil(6);
    Portion *wine     = RedWine_ml(100);
    Portion *vinegar  = BalsamicVinegar_ml(25);

    // prepare tomatoes (see below)
    peel_tomatoes(tomatoes);

    knife_cut_into_pieces(tomatoes);
    knife_cut_into_slices(garlic);
    knife_cut_into_slices(onion);

    // roast garlic and onion
    pot_heat_level(9);
    pot_include(3 * SPOON_OLIVE_OIL);
    pot_include(garlic);
    pot_include(onion);
    hourglass_wait_min(1);

    // deglaze with wine
    pot_include(wine);
    pot_include(tomatoes);
    hourglass_wait_min(2);

    pot_heat_level(5);
    pot_include(vinegar);
    pot_include(PINCH_OF_SUGAR);
    pot_include(TEA_SPOON_SALT);

    // reduce the sauce
    hourglass_wait_min(20);

    // finish the sauce
    knife_cut_into_pieces(basil);
    hand_mixer_blend(pot_content());
    pot_include(basil);
    pot_include(OREGANO);

    do {
        pot_stir();
        hourglass_wait_min(5);
    } while( too_fluid(pot_content()) );
    // approx. 4 runs...

    Portion *sauce = pot_content();
    
    serve_portion(sauce);
}

void peel_tomatoes(Portion *tomatoes) {
    pot_fill_water_L(1);
    pot_heat_level(9);
    knife_cut_in(tomatoes);
    pot_wait_until_boil();
    pot_include(tomatoes);
    hourglass_wait_sec(45);
    pot_pour_out();
    cool_under_water(tomatoes);
    pull_off_skin(tomatoes);
}

```
