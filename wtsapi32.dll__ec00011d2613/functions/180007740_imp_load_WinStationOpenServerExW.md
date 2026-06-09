# __imp_load_WinStationOpenServerExW

- ea: `0x180007740`
- end: `0x18000774c`
- name: `__imp_load_WinStationOpenServerExW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800075e9`

## import_xrefs

- `WINSTA!WinStationOpenServerExW` at `0x180007740`

## pseudocode

```c
__int64 load_WinStationOpenServerExW()
{
  return _tailMerge_winsta_dll();
}

```

## disassembly

```asm
0x180007740  lea     rax, __imp_WinStationOpenServerExW
0x180007747  jmp     __tailMerge_winsta_dll
```
