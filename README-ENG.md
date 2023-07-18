# AELX

AELX is a command-line software that allows you to read and process `.aelx` configuration files. This software supports extracting key-value pairs from the configuration file and provides options to output the data in JSON format or as environment variables.

## Installation

To install AELX, follow these steps:

1. Clone the AELX repository:

   ```shell
   git clone https://github.com/refaldyrk/aelx.git
   ```

2. Switch to the project directory:

   ```shell
   cd aelx
   ```

3. Run AELX:

   ```shell
   aelx --f config.aelx -k hello
   ```

## Usage

Run the `aelx` command with the following flags:

- `-k`: The key whose value you want to retrieve from the configuration file.
- `--f`: The name of the `.aelx` file you want to read.
- `-j`: Optional flag to output the data in JSON format. Default: `false`.
- `--o`: Optional flag to specify the output file name in JSON format. Default: `aelx.json`.
- `-e`: Optional flag to output the data as environment variables. Default: `false`.

### Example Usage

1. Retrieve a specific key's value from the configuration file:

   ```shell
   aelx -k <key-name> --f <file-name.aelx>
   ```

   Example:
   ```shell
   aelx -k hello --f config.aelx
   ```

2. Output the data in JSON format:

   ```shell
   aelx -k <key-name> --f <file-name.aelx> -j true
   ```

   Example:
   ```shell
   aelx -k hello --f config.aelx -j true
   ```

3. Output the data in JSON format with a custom file name:

   ```shell
   aelx -k <key-name> --f <file-name.aelx> -j true --o <output.json>
   ```

   Example:
   ```shell
   aelx -k hello --f config.aelx -j true --o output.json
   ```

4. Output the data as environment variables:

   ```shell
   aelx -k <key-name> --f <file-name.aelx> -e true
   ```

   Example:
   ```shell
   aelx -k hello --f config.aelx -e true
   ```

## `.aelx` File Format

The `.aelx` file uses a specific format. Here is an example of the supported `.aelx` file format:

```
project: start|
[key-1] value-1|
[key-2] value-2|
[key-3] value-3|
project: end|
```

Make sure your `.aelx` file follows this format to ensure proper data extraction.

## Example `.aelx` Configuration File

Here is an example content of a `.aelx` configuration file:

```
project: start|
hello[world]|
lorem[ipsum]|
project: end|
```

In this example, there are two key-value pairs:

- Key: `hello`, Value: `world`
- Key: `lorem`, Value: `ipsum`

You can use the `aelx` command to retrieve the values of these keys or perform data extraction as per your needs.