pod package 是 cocoapods 的一个插件，如果没有的话使用以下命令安装：

sudo gem install cocoapods-packager

pod package 是根据 .podspec 描述文件来生成二进制库



	//强制覆盖之前已经生成过的二进制库 
	--force
		
	//生成静态.framework 
	--embedded
		
	//生成静态.a 
	--library
		
	//生成动态.framework 
	--dynamic
		
	//动态.framework是需要签名的，所以只有生成动态库的时候需要这个BundleId 
	--bundle-identifier
		
	//不包含依赖的符号表，生成动态库的时候不能包含这个命令，动态库一定需要包含依赖的符号表。 
	--exclude-deps
		
	//表示生成的库是debug还是release，默认是release。--configuration=Debug 
	--configuration
		
		
	--no-mangle
	//表示不使用name mangling技术，pod package默认是使用这个技术的。我们能在用pod package生成二进制库的时候会看到终端有输出Mangling symbols和Building mangled framework。表示使用了这个技术。
	//如果你的pod库没有其他依赖的话，那么不使用这个命令也不会报错。但是如果有其他依赖，不使用--no-mangle这个命令的话，那么你在工程里使用生成的二进制库的时候就会报错：Undefined symbols for architecture x86_64。
		
	--subspecs
		
	//如果你的pod库有subspec，那么加上这个命名表示只给某个或几个subspec生成二进制库，--subspecs=subspec1,subspec2。生成的库的名字就是你podspec的名字，如果你想生成的库的名字跟subspec的名字一样，那么就需要修改podspec的名字。 
	这个脚本就是批量生成subspec的二进制库，每一个subspec的库名就是podspecName+subspecName。
		
	--spec-sources``
	
	//一些依赖的source，如果你有依赖是来自于私有库的，那就需要加上那个私有库的source，默认是cocoapods的Specs仓库。--spec-sources=private,https://github.com/CocoaPods/Specs.git。
