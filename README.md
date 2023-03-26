# chatGPT-plugin-template
For Gophers

# Building a ChatGPT Plugin
You need to add at least 2 files from root:
1. Add and edit the file `openapi.yaml`
2. Add and edit the file `.well-known/ai-plugin.json` (you might need to sudo this)
As comments are not allowed in a JSON file, check `out ai-plugin_example.md` for some more details on structuring this file
3. As a sanity check, double check the paths from file 1 match the endpoints from path 2 
4. execute: `$ go run main.go`
5. Add the plugin via the ChatGPT UI

If you are running in localhost, use a tunneling tool like ngrok to expose the files. Change in `openapi.yaml` and in `.well-known/ai-plugin.json`. And your `main.go` can remain on localhost.


# Debug
Problem: You can't access the `.well-known/ai-plugin.json` file, it might be a permissions issues.

Solution: 
Go to the root of the repo (e.g. `~/Projects/chatGPT-plugin-template`) and run `ls -la`. If you see that the permissions for the `.well-known` folder look different - make it the same.


Problem: 
You are running on localhost and the file `.well-known/ai-plugin.json` exists in the right place, but the ChatGPT Plugin UI can't find a manifest.

Solution: 
Use a tunneling tool like ngrok to expose the files. Change to the ngrok url in `openapi.yaml` and in `.well-known/ai-plugin.json`. And your `main.go` can remain on localhost.


Problem: 
You have successfully added the plugin but it shows an empty field.

Solution: 
Improve the descriptions for a simpler prompt engineering in the files: `openapi.yaml` and  `.well-known/ai-plugin.json`.