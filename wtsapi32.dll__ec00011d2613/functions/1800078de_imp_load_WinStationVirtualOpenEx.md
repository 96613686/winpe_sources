# __imp_load_WinStationVirtualOpenEx

- ea: `0x1800078de`
- end: `0x1800078ea`
- name: `__imp_load_WinStationVirtualOpenEx`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800075e9`

## import_xrefs

- `WINSTA!WinStationVirtualOpenEx` at `0x1800078de`

## pseudocode

```c
__int64 load_WinStationVirtualOpenEx()
{
  return _tailMerge_winsta_dll();
}

```

## disassembly

```asm
0x1800078de  lea     rax, __imp_WinStationVirtualOpenEx
0x1800078e5  jmp     __tailMerge_winsta_dll
```
