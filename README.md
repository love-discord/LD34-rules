LD 34 DISCORD GROUP PARTICIPANTS
===
- Muddmaker (Programming)
- Odyssey (Programming)
- Mahham (Programming)
- Soso (Programming)
- Petros (Music)
- Fantos (Art)
- YoohooYuzu (Art)
- VideahGams (Idea discussion)
 
Ludum Dare 34 starts at [__Satuday 11:00(AM, KST[GMT +9])__](http://www.wolframalpha.com/input/?i=Saturday+11%3A00+AM+KST+to+local+time+zone) (Click the time for time converting)
 
Make sure to be online here **1 HOUR** before LD starts for your timezone.
I am aware that the time is ridiculous for some people but we only have 72 hours.


PROGRAMMING RULES FOR LD34
===

In order to make it easy to read each others code, we have decided to implement rules for styles of coding.

1. Comment each chunk of code with at least 1 comment. Even if it seems obvious for you. It might not be at easy to understand for others. ex)

    ```lua
    -- loops through every tile
    for i = 1, #tiles do
        -- prints tile with given id
        print(tile[i].name)
    end
    ```

2. The way we are going to fuse our code is through modular code. However, the only functions that are going to be in the main.lua file, are for example:

    ```lua
    player = {}

    -- handles player movement
    function player:movement(dt)
        -- moves player up by x[100]
        if love.keyboard.isDown("w") then
            player.x = player.x + 100
        end
    end
    
    function player:update(dt)
        player:movement(dt)
    end
    
    function player:draw()
        -- draws rectangle at player pos
        love.graphics.rectangle("fill", x, y, w, h)
    end
    ```

    ```lua
    --[[ main.lua ]]--
    
    function love.load()
    
    end
    
    function love.update(dt)
        player:update(dt)
        map:update(dt)
    end
    
    function love.draw()
        player:draw()
        map:draw()
    end
    
    function love.keypressed(key)
        -- item usage
        item:keypressed(key)
    end
    ```
    
3. The way functions and variables are named are not set. However, you should name function with a ":" and variables with a ".". ex)
    ```lua
    player = {
        shooting = false,
        name = "Hello"
    }
    
    function player:shoot()
        -- spawns bullet if player is shooting
        if player.shooting then
            spawn:bullet()
        end
    end
    
    function player:draw()
        -- prints player's name
        print(player.name)
    end
    ```
