# protoc php generator docker helper


### USAGE

```bash
docker run -v `pwd`:/data cnam/protoc-gen-php -i /data -o /data /data/test.proto
```

### DESCRIPTION
protoc-gen-php is a Google's Protocol Buffers compiler plugin for the protoc tool. It generates PHP classes compatible with Protobuf for PHP from .proto files.

### OPTIONS
The command accepts the following command-line options (switches).

-v, --verbose: Enables verbose mode. Additional information will be printed when processing the files.

-h, --help: Prints the usage help message and quits.

-i directory, --include=directory: Tells the protoc compiler to look into that directory when resolving import statements. Note that you can use this switch more than once to configure multiple directories.

-o directory, --out=directory: Tells the protoc compiler to create generated files in the given directory. If not set it will create the files in the working directory.

--protoc=path to protoc binary: If you don't happen to have the protoc binary in your path, you can use this option to indicate a path to it.

--skip-imported Flags the compiler to only generate source code for the proto file explicitely given on the command line. This means that imported files will not be generated when using this option.

--comments Parses the .proto files looking for multiline comments (/ ... /) to include them in the generated files.

-Ddefine, -Ddefine=value: Defines an option (defaults to true if no value given) to pass to the generator. See protobuf-php(5) for supported options, noting that the php. prefix shall not be used here.

### EXAMPLES
Generate a PHP file from a proto file:

$ protoc-gen-php tutorial.proto
Generate PHP files in the "build" directory for each proto file found the "protos" directory:

$ protoc-gen-php -o build protos/*.proto
Generate a PHP file from a proto file using imports from an include path:

$ protoc-gen-php -i ./protos protos/tutorial.proto
Generate a PHP file with a custom extension

$ protoc-gen-php -Dsuffix=pb.php tutorial.proto

