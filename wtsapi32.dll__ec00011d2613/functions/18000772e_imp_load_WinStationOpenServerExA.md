# __imp_load_WinStationOpenServerExA

- ea: `0x18000772e`
- end: `0x18000773a`
- name: `__imp_load_WinStationOpenServerExA`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800075e9`

## import_xrefs

- `WINSTA!WinStationOpenServerExA` at `0x18000772e`

## pseudocode

```c
__int64 load_WinStationOpenServerExA()
{
  return _tailMerge_winsta_dll();
}

```

## disassembly

```asm
0x18000772e  lea     rax, __imp_WinStationOpenServerExA
0x180007735  jmp     __tailMerge_winsta_dll
```
