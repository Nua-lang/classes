# classes
new feature added to lua's syntax: classes!!!
---

You can use classes in Nua by adding it to your request list:

```
Object = require "classic"
```

After that you need to put the classic.nua file in your local project.


Then you can start writing classes: look at this sample file(test.nua):

```
PairPrinter = Object:extend()

function PairPrinter:printPairs()
  for k, v in pairs(self) do
    print(k, v)
  end
end


Point = Object:extend()
Point:implement(PairPrinter)

function Point:new(x, y)
  self.x = x or 0
  self.y = y or 0
end


local p = Point()
p:printPairs()
Point = Object:extend()
Point.scale = 2

function Point:new(x, y)
  self.x = x or 0
  self.y = y or 0
end

function Point:getScaled()
  return self.x * Point.scale, self.y * Point.scale
end
```

And the output will be shown as:
```
x       0
y       0
```
