-----------------------------------------------------------------------------------------
--
-- main.lua
--
-- Created by: Aayman Shameem
-- Created on: May 7, 2018
-- 
-- This code animates a character using a spritesheet
-----------------------------------------------------------------------------------------

display.setStatusBar(display.HiddenStatusBar)
 
centerX = display.contentWidth * .5
centerY = display.contentHeight * .5

local sheetOptionsIdle =
{
    width = 232,
    height = 439,
    numFrames = 10
}
local sheetIdleNinja = graphics.newImageSheet( "./assets/spritesheets/ninjaBoyIdle.png", sheetOptionsIdle )

local sheetOptionsWalk =
{
    width = 363,
    height = 458,
    numFrames = 10
}
local sheetWalkingNinja = graphics.newImageSheet( "./assets/spritesheets/ninjaBoyJumpRun.png", sheetOptionsWalk )


-- sequences table
local sequence_data = {
    -- consecutive frames sequence
    {
        name = "idle",
        start = 1,
        count = 10,
        time = 800,
        loopCount = 0,
        sheet = sheetIdleNinja
    },
    {
        name = "walk",
        start = 1,
        count = 10,
        time = 800,
        loopCount = 0,
        sheet = sheetWalkingNinja
    }
}

local ninja = display.newSprite( sheetIdleNinja, sequence_data )
ninja.x = centerX - 650
ninja.y = centerY

ninja:play()

-- After a short time, swap the sequence to 'seq2' which uses the second image sheet
local function swapSheet()
    ninja:setSequence( "walk" )
    ninja:play()
    print("walk")
end
timer.performWithDelay( 2000, swapSheet )

----------------------------------------------------------------------------------------------------------------

local sheetOptionsIdle2 =
{
    width = 567,
    height = 556,
    numFrames = 10
}
local sheetIdleRobot = graphics.newImageSheet( "./assets/spritesheets/robotIdle.png", sheetOptionsIdle2 )

local sheetOptionsWalk2 =
{
    width = 567,
    height = 556,
    numFrames = 8
}
local sheetWalkingRobot = graphics.newImageSheet( "./assets/spritesheets/robotRun.png", sheetOptionsWalk2 )


-- sequences table
local sequence_data2 = {
    -- consecutive frames sequence
    {
        name = "idle",
        start = 1,
        count = 10,
        time = 800,
        loopCount = 0,
        sheet = sheetIdleRobot
    },
    {
        name = "walk",
        start = 1,
        count = 10,
        time = 800,
        loopCount = 0,
        sheet = sheetWalkingRobot
    }
}

local robot = display.newSprite( sheetIdleRobot, sequence_data2 )
robot.x = centerX + 650
robot.y = centerY

robot:play()

-- After a short time, swap the sequence to 'seq2' which uses the second image sheet
local function swapSheet2()
    robot:setSequence( "walk" )
    robot:play()
    print("walk")
end


timer.performWithDelay( 2000, swapSheet2 )
