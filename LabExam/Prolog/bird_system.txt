
bird_data(sparrow, small, brown, social, trees, flies, short_beak, builds_nests).
bird_data(pigeon, medium, gray, social, urban_areas, flies, short_beak, builds_nests).
bird_data(hawk, medium, brown, solitary, mountains, flies, sharp_beak, builds_nests).
bird_data(canary, small, yellow, solitary, cages, flies, short_beak, builds_nests).
bird_data(ostrich, large, brown, solitary, plains, does_not_fly, long_beak, ground_nester).
bird_data(crow, medium, black, social, various, flies, sharp_beak, builds_nests).
bird_data(eagle, large, brown, solitary, mountains, flies, sharp_beak, builds_nests).
bird_data(falcon, medium, brown, solitary, cliffs, flies, sharp_beak, builds_nests).
bird_data(seagull, medium, white_and_gray, social, coastlines, flies, medium_beak, builds_nests).
bird_data(owl, medium, brown, solitary, forests, flies, sharp_beak, builds_nests).
bird_data(parrot, small, colorful, social, forests, flies, short_beak, builds_nests).
bird_data(peacock, large, colorful, solitary, gardens, does_not_fly, medium_beak, ground_nester).
bird_data(swallow, small, blue_and_white, social, skies, flies, short_beak, builds_nests).
bird_data(woodpecker, small, black_and_white, solitary, forests, flies, sharp_beak, builds_nests).
bird_data(canadian_goose, large, gray_and_white, social, lakes, flies, medium_beak, builds_nests).
bird_data(penguin, medium, black_and_white, social, polar_regions, does_not_fly, medium_beak, ground_nester).
bird_data(blue_jay, small, blue_and_white, solitary, forests, flies, medium_beak, builds_nests).
bird_data(robin, small, red_breast, social, gardens, flies, short_beak, builds_nests).
bird_data(duck, medium, various, social, lakes, flies, medium_beak, builds_nests).
bird_data(hummingbird, small, iridescent, solitary, gardens, flies, long_beak, builds_nests).
bird_data(stork, large, white, solitary, wetlands, flies, long_beak, builds_nests).


identify_bird(Color, Size, Social, Habitat, Flight, BeakShape, NestingBehavior, Bird) :-
    bird_data(Bird, Size, Color, Social, Habitat, Flight, BeakShape, NestingBehavior).

start :-
    write('Welcome to the Bird Identifier!'), nl,
    write('Please describe the bird you want to identify.'), nl,
    write('What is the color of the bird? '), read(Color), nl,
    write('What is the size of the bird (small, medium, large)? '), read(Size), nl,
    write('Is the bird social (social or solitary)? '), read(Social), nl,
    write('Where is the bird commonly found (e.g., "forests," "urban_areas", "plains")? '), read(Habitat), nl,
    write('Can the bird fly (flies or does_not_fly)? '), read(Flight), nl,
    write('What is the shape of the bird\'s beak (short_beak, medium_beak, sharp_beak, long_beak)? '), read(BeakShape), nl,
    write('What is the nesting behavior of the bird (builds_nests or ground_nester)? '), read(NestingBehavior), nl,
    identify_bird(Color, Size, Social, Habitat, Flight, BeakShape, NestingBehavior, Bird),
    (
        Bird \= [] -> write('Based on your description, the bird may be a '), write(Bird), nl
        ; write('No bird identified based on your given information'), nl
    ).
