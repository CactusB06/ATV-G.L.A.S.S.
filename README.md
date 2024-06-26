[{"id":"15cb52e6ae5a9b6d","type":"tab","label":"Flow 4","disabled":false,"info":"","env":[]},{"id":"c66eb75cc348fd13","type":"rpi-srf","z":"15cb52e6ae5a9b6d","name":"Supersonic","topic":"SRF","pulse":"0.5","pins":"16,18","precision":"0","x":80,"y":20,"wires":[["686b8b9364711c43","604414540acf428c"]]},{"id":"686b8b9364711c43","type":"switch","z":"15cb52e6ae5a9b6d","name":"","property":"payload","propertyType":"msg","rules":[{"t":"lte","v":"300","vt":"num"},{"t":"gt","v":"300","vt":"num"}],"checkall":"true","repair":false,"outputs":2,"x":90,"y":100,"wires":[["1fd0a2c9cc26c4b1","48d15d2de047a613"],["8176ed8a8ac9519c"]]},{"id":"1fd0a2c9cc26c4b1","type":"change","z":"15cb52e6ae5a9b6d","name":"On Road","rules":[{"t":"set","p":"payload","pt":"msg","to":"1","tot":"num"}],"action":"","property":"","from":"","to":"","reg":false,"x":100,"y":140,"wires":[["6d2b6f4b9f38d6d2"]]},{"id":"907ec941c7560ef7","type":"thingspeak42","z":"15cb52e6ae5a9b6d","name":"","delay":"15","topic1":"Traffic Count","topic2":"Sound","topic3":"Threshold","topic4":"Pos_Val","topic5":"Distance","topic6":"","topic7":"","topic8":"","endpoint":"https://thingspeak.com","x":130,"y":300,"wires":[]},{"id":"b1cc177f38abe082","type":"change","z":"15cb52e6ae5a9b6d","name":"Traffic","rules":[{"t":"set","p":"topic","pt":"msg","to":"Traffic Count","tot":"str"}],"action":"","property":"","from":"","to":"","reg":false,"x":90,"y":260,"wires":[["907ec941c7560ef7"]]},{"id":"8176ed8a8ac9519c","type":"change","z":"15cb52e6ae5a9b6d","name":"Off Road","rules":[{"t":"set","p":"payload","pt":"msg","to":"0","tot":"num"}],"action":"","property":"","from":"","to":"","reg":false,"x":100,"y":180,"wires":[["6d2b6f4b9f38d6d2"]]},{"id":"0952e8f880b99830","type":"serial in","z":"15cb52e6ae5a9b6d","name":"Sound","serial":"3e517049f3f5152e","x":250,"y":20,"wires":[["572d4664bc58e5a3","f075a7772ece8d26"]]},{"id":"572d4664bc58e5a3","type":"change","z":"15cb52e6ae5a9b6d","name":"Sound above 32","rules":[{"t":"set","p":"topic","pt":"msg","to":"Sound","tot":"str"}],"action":"","property":"","from":"","to":"","reg":false,"x":280,"y":60,"wires":[["907ec941c7560ef7"]]},{"id":"6d2b6f4b9f38d6d2","type":"rbe","z":"15cb52e6ae5a9b6d","name":"","func":"rbe","gap":"","start":"","inout":"out","septopics":true,"property":"payload","topi":"topic","x":90,"y":220,"wires":[["b1cc177f38abe082"]]},{"id":"f075a7772ece8d26","type":"switch","z":"15cb52e6ae5a9b6d","name":"","property":"payload","propertyType":"msg","rules":[{"t":"gte","v":"38","vt":"num"}],"checkall":"true","repair":false,"outputs":1,"x":270,"y":100,"wires":[["024030d281fc3997","48d15d2de047a613"]]},{"id":"48d15d2de047a613","type":"and-gate","z":"15cb52e6ae5a9b6d","name":"","rules":[{"t":"eq","v":"","vt":"str","propertyType":"msg","property":"payload","topic":""}],"outputTopic":"","gateType":"and","emitOnlyIfTrue":false,"x":460,"y":20,"wires":[["4444899f519821eb"]]},{"id":"024030d281fc3997","type":"change","z":"15cb52e6ae5a9b6d","name":"Sound above 70db","rules":[{"t":"set","p":"topic","pt":"msg","to":"Threshold","tot":"str"}],"action":"","property":"","from":"","to":"","reg":false,"x":310,"y":140,"wires":[["907ec941c7560ef7"]]},{"id":"d10f5575a926474f","type":"change","z":"15cb52e6ae5a9b6d","name":"Possible value","rules":[{"t":"set","p":"topic","pt":"msg","to":"Pos_Val","tot":"str"}],"action":"","property":"","from":"","to":"","reg":false,"x":480,"y":100,"wires":[["907ec941c7560ef7"]]},{"id":"4444899f519821eb","type":"rbe","z":"15cb52e6ae5a9b6d","name":"","func":"rbe","gap":"","start":"","inout":"out","septopics":true,"property":"payload","topi":"topic","x":450,"y":60,"wires":[["d10f5575a926474f"]]},{"id":"604414540acf428c","type":"change","z":"15cb52e6ae5a9b6d","name":"Distance","rules":[{"t":"set","p":"topic","pt":"msg","to":"Distance","tot":"str"}],"action":"","property":"","from":"","to":"","reg":false,"x":100,"y":60,"wires":[["907ec941c7560ef7"]]},{"id":"3e517049f3f5152e","type":"serial-port","serialport":"/dev/ttyACM0","serialbaud":"9600","databits":"8","parity":"none","stopbits":"1","waitfor":"","dtr":"none","rts":"none","cts":"none","dsr":"none","newline":"\\n","bin":"false","out":"char","addchar":"","responsetimeout":"10000"}]
