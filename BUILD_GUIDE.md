### Win64 Dev Mono:

- Install Scons
	```shell
	pip install scons (--upgrade)
	scons -v
	```

- Generate VS Project
	```shell
	scons p=windows vsproj=yes dev_build=yes module_mono_enabled=yes
	```

- Build From VS/Rider

- Generate C# Glue
	```shell
	.\bin\godot.windows.editor.dev.x86_64.mono.exe --headless --generate-mono-glue modules/mono/glue
	```

- Add Local Nuget Source
	```shell
	mkdir bin/LocalNugetSource
	dotnet nuget add source C:\Project\Engine\godot\bin\LocalNugetSource --name GodotNugetSource
	dotnet nuget list source
	```

- Generate C# Assembly
	```shell
	python .\modules\mono\build_scripts\build_assemblies.py --godot-output-dir .\bin --push-nupkgs-local .\bin\LocalNugetSource\
	```
