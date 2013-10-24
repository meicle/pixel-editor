Hotkeys
=======

Hotkeys for the pixel editor.

    module.exports = (I={}, self)->
      self.extend
        addHotkey: (key, method) ->
          $(document).bind "keydown", key, ->
            console.log key, method
            self[method]()

      hotkeys =
        "ctrl+z": "undo"
        "ctrl+y": "redo"

      Object.keys(hotkeys).forEach (key) ->
        console.log "Adding", key
        self.addHotkey(key, hotkeys[key])

      return self