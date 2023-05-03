# Why is this forked?

This fork provides a way to inject information in the response of `Sys.GetInfo`.

This is done by creating a header file that defines the macros: `CUSTOM_SYS_INFO_PROPERTY_KEYS` and `CUSTOM_SYS_INFO_PROPERTY_VALUES`. The file the needs to be specified in mos.yaml as a global macro. For example:

mos.yaml
```yaml
cdefs:
  MGOS_SYS_INFO_MACRO_FILE: SomeFile.h
```

The header file:
```C
#define CUSTOM_SYS_INFO_PROPERTY_KEYS \
"hello: %Q, foo: %Q"

#define CUSTOM_SYS_INFO_PROPERTY_VALUES \
"world", "bar"
```

# RPC - Remote Procedure Calls

See [MG-RPC Guide](https://mongoose-os.com/docs/mongoose-os/userguide/rpc.md)
for detailed documentation.
