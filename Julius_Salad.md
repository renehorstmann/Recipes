
# Julius Salad

![result](build/Julius_Salad.jpg "Build")

## Source code
Run the following code to cook one meal:

```c
#include <kitchen.h>

// recipes below main
void bake_chicken_breast(ChickenBreast chicken);

CaesarSauce make_CaesarSauce();


int main() {

    // ingredients
    ChickenBreast  chicken  = 1;
    CherryTomatoes tomatoes = 6;
    Onion          onion    = 1;
    Feta           feta     = G(25);

    // warning: CaeserSauce has its own ingredients

    // cook chicken breast (see below)
    cook_in_parallel(bake_chicken_breast, chicken);

    // see below (own ingredients)
    CaeserSauce sauce = make_CaeserSauce();

    // todo...

    serve();
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

CaesarSauce make_CaesarSauce() {
    // sauce ingredients
    Parmesan        cheese = G(50);
    Garlic          garlic = 1;
    SaladMayonnaise mayo   = G(250);
    CremeFraiche    creme  = G(150);

    grater_rasp(cheese);
    knife_cut_into_slices(garlic);

    mixing_bowl_include(cheese);
    mixing_bowl_include(garlic);
    mixing_bowl_include(mayo);
    mixing_bowl_include(creme);
    mixing_bowl_include(2 * SPOON_VINEGAR);
    mixing_bowl_include(SALT_AND_PEPPER);

    hand_mixer_mix(mixing_bowl_content());
   
    while(too_tight(mixing_bowl_content()) {
         mixing_bowl_include(SPOON_WATER);
         hand_mixer_mix(mixing_bowl_content());
    }

    return mixing_bowl_content();
}

```
