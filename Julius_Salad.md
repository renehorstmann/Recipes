
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
    ChickenBreast chicken   = 1;
    Salad         salad     = G(50);
    CherryTomato  tomatoes  = 6;
    Paprika       paprika   = 1;
    Mushroom      mushrooms = 3;
    Onion         onion     = 1;
    Feta          feta      = G(25);
    RedWine       wine      = ML(50);
    // warning: CaeserSauce has its own ingredients

    // cook chicken breast (see below)
    cook_in_parallel(bake_chicken_breast, chicken);

    // see below (own ingredients)
    CaeserSauce sauce = make_CaeserSauce();

    knife_cut_into_pieces(paprika);
    knife_cut_into_pieces(mushrooms);
    knife_cut_into_slices(onions);

    pan_heat_level(7);
    pan_include(paprika);
    pan_include(mushrooms);
    pan_include(onions);
    hourglass_wait_min(3);

    pan_include(wine);
    
    knife_cut_in_half(tomatoes);
    pan_include(wine);
    pan_heat_level(5);
    hourglass_wait_min(10);

    plate_include(salad);
    plate_include(pan_content());
    plate_include(chicken);
    plate_include(sauce);
    plate_include(feta);

    serve(plate);
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
