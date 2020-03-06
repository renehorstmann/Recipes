# Spaghetti Pollo che Brucia

![result](build/Spaghetti_Pollo_che_Brucia.jpg "Build")

## Source code
Run the following code to cook one meal:

```c
#include <kitchen.h>

// recipes below main
void peel_tomatoes(Tomatoes tomatoes);
void bake_chicken_breast(ChickenBreast chicken);
void cook_spaghetti(Spaghetti spaghetti);

static const bool spicy = true;

int main() {

    // ingredients
    Spaghetti     speghetti = G(125);
    Tomatoes      tomatoes  = 2;
    ChickenBreast chicken   = 1;
    Garlic        garlic    = 1;
    RedChili      chili     = CM(spicy ? 1.5 : 0.5);
    Basil         basil     = 10
    RedWine       wine      = ML(100);

   
    // prepare tomatoes (see below)
    peel_tomatoes(tomatoes);

    // cook chicken breast (see below)
    cook_in_parallel(bake_chicken_breast, chicken);

    // make sauce
    knife_cut_slices(garlic);
    knife_cut_slices(chili);
    knife_cut_into_pieces(tomatoes);
    pan_heat_level(7);  // same pan as from the chicken
    pan_include(garlic);
    pan_include(chili);
    hourglass_wait_min(2);
    pan_include(wine);
    pan_include(tomatoes);
    pan_heat_level(4);
    
    // spaghetti (see below)
    cook_in_parallel(cook_spaghetti, spaghetti);

    // finish sauce
    hourglass_wait_min(6);
    handblender_blend(pan_content());
    pan_include(SPOON_SUGAR);
    pan_include(SALT_AND_PEPPER);
    knife_cut_into_pieces(basil);
    pan_include(basil);
    pan_include(pot_take_off(SALT_WATER));

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

void bake_chicken_breast(ChickenBreast chicken) {
    oven_heat_C(160);
    wash_under_water(chicken);
    pan_heat_level(8);
    pan_include(3*SPOON_OLIVE_OIL);
    pan_include(chicken);
    hourglass_wait_min(2);
    pan_turn_content();
    pan_include(SALT_AND_PEPPER);
    hourglass_wait_min(2);
    oven_include(chicken);
    hourglass_wait_min(20);
    oven_take_out(chicken);
}

void cook_spaghetti(Spaghetti spaghetti) {
    pot_fill_water_L(2);
    pot_heat_level(9);
    pot_wait_until_boil();
    pot_include(SALT);
    pot_include(spaghetti);
    hourglass_wait_min(SPAGHETTI_COOK_TIME);
    pot_pour_out();
}

```
