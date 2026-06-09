# __imp_load_WinStationOpenServerA

- ea: `0x18000771c`
- end: `0x180007728`
- name: `__imp_load_WinStationOpenServerA`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800075e9`

## import_xrefs

- `WINSTA!WinStationOpenServerA` at `0x18000771c`

## pseudocode

```c
__int64 load_WinStationOpenServerA()
{
  return _tailMerge_winsta_dll();
}

```

## disassembly

```asm
0x18000771c  lea     rax, __imp_WinStationOpenServerA
0x180007723  jmp     __tailMerge_winsta_dll
```
