# 3. Goodbye, My Friend! (goodbye.cpp | Goodbye.java)

Trisolarans Alice and Bob used to be best friends, but have now become rivals. They are consumed by the desire to shoot each other dead. Alice and Bob live in an n × m rectangular grid, with three types of cells:

• Obstacles (#): cannot be entered or shot through.
• Empty spaces (.): can be freely entered.
• Water (~): cannot be entered, but can be shot through.

Both Alice and Bob can move freely to any reachable empty space (including their house), and can shoot in any of the four cardinal directions (up, down, left, right) from their current position. Bullet range is infinite: it travels in a straight line, passing through empty spaces, houses, and water, but stops when hitting obstacles.

Alice's house (denoted as A) and Bob's house (denoted as B) act as normal empty spaces for movement, and can be shot through. (Yes, Trisolarans' bullets are very powerful; they can pass through houses.) Initially, Alice and Bob are in their own houses. Moves are only allowed between edge-adjacent cells.

Your task is: by converting some empty spaces (.) into obstacles (#), make it so that the two cannot possibly shoot each other (i.e., from any position, Alice cannot shoot Bob, and vice versa, over any possible moves), using the minimum number of such conversions. Houses cannot be converted. If it is impossible (i.e., no matter how you block, they can always shoot each other), output -1.