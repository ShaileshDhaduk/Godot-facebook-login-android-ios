# Godot-facebook-login-android-ios
Facebook login in app

## Android
```
if Engine.has_singleton("GodotFacebook"):
  print("Facebook was detected")
	facebookObj = Engine.get_singleton("GodotFacebook")
	facebookObj.connect("login_success",self,"login_success")
	facebookObj.connect("login_cancelled",self,"login_cancelled")
	facebookObj.connect("login_failed",self,"login_failed")
	facebookObj.connect("get_user_profile",self,"_fetch_UserProfile")
	facebookObj.init(facebook_app_id)
else:
	print("Facebook was not detected")
  ```
  
 Button click
 
 ```
 if facebookObj != null:
		facebookObj.login(["public_profile", "email"])
 ```
 
  Signal Call back
```
func login_success(token):
	print('Facebook login success: %s'%token)
  facebookObj.userProfile()
  
func login_cancelled():
	print('Facebook login cancelled')
  
func login_failed(error):
	print('Facebook login failed::: %s'%error)
  
func _fetch_UserProfile(data):
	print("Facebook Data : ",data)
```
