
# How to add a submodule

```
git submodule add https://github.com/someuser/somelibrary.git vendor/somelibrary
```

# Setup this project

### Adding Imgui
#### 1. Add the Imgui repo as submodule
```git
git submodule add https://github.com/ocornut/imgui.git vendor/imgui
```
#### 2. [Optional] Switch to Docking branch if desire to su/pport docking and viewport

Edit file ```.gitmodules``` putting the branch field
```
[submodule "vendor/imgui"]
	path = vendor/imgui
	url = https://github.com/ocornut/imgui.git
	branch = docking <--------
```
Update the submodule with ```git submodule update --remote```


### Adding GLWM

### Adding OpenCV

### Adding OnnxRuntime

