# Section 3: Yocto Project Basics
	Pasi pentru a face un Software Package:
		- Fetch
		- Decompress
		- Patch
		- Configure
		- Compile
		- Install
		- Deploy & Package
		- Q/A (Quality Assurance)
	
## Directoare/Fisiere din Poky:
		- build:
			- conf
				- local.conf -> fisier de configuratii globare pentru environment
				- bblayers.conf -> Ce layere sa se adauge in environment de unde se face reteta
			- downloads 	-> aici se descarca arhive "tar" si repo de git
			- tmp 		-> Fisiere temporare dupa build
				-log -> director de log-uri 
				- deploy -> output final dupa build
					- rpm -> packages de tip rpm
					- images -> final image
					- sdk -> final sdk output
				- work	
			- cache
			- sstate-cache
### Fisiere care se gasesc in build/tmp/work/core2-64-poky-linux/dropbear (dropbear este reteta compilata prin bitbake)
		- build -> Se gasesc fisierele de build (.o)
		- deploy-rpms -> fisiere de tip rpm specific
		- dropbear-2022.83 -> Source Folder
		- image -> Fisiere output pe care sa le dai deploy la rootFS image atunci cand se alege generare de imagini
		- package -> Fisiere output pentru a da deploy la packages cand se genereaza package
		- pkgdata -> Package gen related data
		- recipe-sysroot -> Filesystem temporar care contine dependenetele pentru dropbear pentru build pentru target
		- recipe-sysroot-native -> La fel ca la recip-sysroot dar este build pentru host
		- temp -> contine log-uri pentru build
			- log.task_order -> ordinea in timpul do_patch in care se executa bitbake build
			- log.do_patch -> Log in timpu do_patch task
			- log.do_compile -> log pentru do_compile task
			- run.do_compile -> lista de comenzi py/bash care sunt executate in ordine pentru a face do_compile



# Section 4: Layers
