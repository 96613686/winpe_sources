# __imp_load_DevObjCreateDeviceInfoList

- ea: `0x180022ee9`
- end: `0x180022ef5`
- name: `__imp_load_DevObjCreateDeviceInfoList`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180022e22`

## import_xrefs

- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x180022ee9`

## pseudocode

```c
__int64 load_DevObjCreateDeviceInfoList()
{
  return _tailMerge_devobj_dll();
}

```

## disassembly

```asm
0x180022ee9  lea     rax, __imp_DevObjCreateDeviceInfoList
0x180022ef0  jmp     __tailMerge_devobj_dll
```
