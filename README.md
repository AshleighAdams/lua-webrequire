# lua-webrequire

## Concept:

```lua
local webrequire = webrequire()

--- info
webrequire = {
	__call = function(name, options) ... end
	repos = {
		KateAdams = {
			require = function(user, name)
				return http_require("http://kateadams.eu/webrequire/" .. user .. "/" .. name)
			end,
			priority = 0,
		},
		GitHub = {
			require = function(user, name) end,
			priority = 0,
		}
	}
}

-- options listing
local valid_options = {
	api_version = ">=5",
}

local configor = webrequire("configor") -- for "approved" versions, may not be original author (could be a fork)
local configor = webrequire("Kobra.configor")
local configor = webrequire("KateAdams.Kobra.configor")
local configor = webrequire("GitHub.Kobra.lua-configor")
```
