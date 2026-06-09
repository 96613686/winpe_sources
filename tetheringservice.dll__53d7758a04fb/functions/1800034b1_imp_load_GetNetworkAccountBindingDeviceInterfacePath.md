# __imp_load_GetNetworkAccountBindingDeviceInterfacePath

- ea: `0x1800034b1`
- end: `0x1800034bd`
- name: `__imp_load_GetNetworkAccountBindingDeviceInterfacePath`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180003420`

## import_xrefs

- `MobileNetworking!GetNetworkAccountBindingDeviceInterfacePath` at `0x1800034b1`

## pseudocode

```c
__int64 load_GetNetworkAccountBindingDeviceInterfacePath()
{
  return _tailMerge_mobilenetworking_dll();
}

```

## disassembly

```asm
0x1800034b1  lea     rax, __imp_GetNetworkAccountBindingDeviceInterfacePath
0x1800034b8  jmp     __tailMerge_mobilenetworking_dll
```
