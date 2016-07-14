local CATERGORY_NAME = "Utility"

function ulx.respawn( calling_ply, target_ply )
	if not target_ply:Alive() then
		target_ply:Spawn()
		ulx.fancyLogAdmin( calling_ply, true, "#A respawned #T", target_ply )
	end
end

local respawn = ulx.command( CATERGORY_NAME, "ulx respawn", ulx.respawn, "!respawn", true )
respawn:addParam{ type=ULib.cmds.PlayerArg }
respawn:defaultAccess( ULib.ACCESS_ADMIN )
respawn:help( "Respawns a selected player.")
