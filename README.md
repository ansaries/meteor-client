# meteor-client
meteor-client file to include in Cordova or Other Client projects to access a Meteor Server.

Include following in the dependecies of your package.json
"meteor-client": "git+https://github.com/ansaries/meteor-client.git",

npm install


Include following script in your index.html.
```
<script> 
  function() {      
        var url= 'https://www.YourProductionMeteorServerUrl.com';

        var stagging = false;
        var local = false;

        if(stagging) {
          url= "http://www.YourstaggingMeteorServerUrl.com"
          if(local)
            url = "http://localhost:3000";                
        }

        __meteor_runtime_config__ = {
          "meteorEnv": {},          
          "DDP_DEFAULT_CONNECTION_URL": url, 
          "ROOT_URL": url,
          "MOBILE_URL": url,
          "MOBILE_ROOT_URL": url
        };        
  }();
</script>
```

Do not forget to change the urls.


