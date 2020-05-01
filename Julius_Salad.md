
# Julius Salad

![result](build/Julius_Salad.jpg "Build")

## Source code
Run the following code to cook one meal:

```c
#include <kitchen.h>

// recipes below main
void bake_chicken_breast(Portion *chicken);

Portion *make_CaesarSauce();

int main() {

    // ingredients
    Portion *chicken   = ChickenBreast(1);
    Portion *salad     = Salad_g(50); // romaine + iceberg lettuce 
    Portion *tomatoes  = CherryTomato(6);
    Portion *paprika   = Paprika(1);
    Portion *mushrooms = Mushroom(3);
    Portion *onion     = Onion(1);
    Portion *radish    = Radish(4);
    Portion *feta      = Feta_g(25);
    Portion *wine      = RedWine_ml(50);
    // warning: CaeserSauce has its own ingredients

    // cook chicken breast (see below)
    cook_in_parallel(bake_chicken_breast, chicken);

    // see below (own ingredients)
    Portion *sauce = make_CaeserSauce();

    knife_cut_into_pieces(paprika);
    knife_cut_into_pieces(mushrooms);
    knife_cut_into_slices(onions);

    pan_heat_level(7); // same as for the chicken
    pan_include(paprika);
    pan_include(mushrooms);
    pan_include(onions);
    hourglass_wait_min(3);

    knife_cut_in_half(tomatoes);

    // deglaze with wine
    pan_include(wine);
    pan_include(SALT_AND_PEPPER);
    pan_include(tomatoes);
    pan_heat_level(5);
    hourglass_wait_min(10);

    knife_cut_into_slices(radish);

    plate_include(salad);
    plate_include(pan_content());
    plate_include(chicken);
    plate_include(sauce);
    plate_include(radish);
    plate_include(feta);

    serve(plate);
}

void bake_chicken_breast(Portion *chicken) {
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
    Portion *cheese = Parmesan_g(50);
    Portion *garlic = Garlic(1);
    Portion *mayo   = SaladMayonnaise_g(250);
    Portion *creme  = CremeFraiche_g(150);

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
