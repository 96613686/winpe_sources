# __imp_load_WinStationOpenServerW

- ea: `0x180007764`
- end: `0x180007770`
- name: `__imp_load_WinStationOpenServerW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800075e9`

## import_xrefs

- `WINSTA!WinStationOpenServerW` at `0x180007764`

## pseudocode

```c
__int64 load_WinStationOpenServerW()
{
  return _tailMerge_winsta_dll();
}

```

## disassembly

```asm
0x180007764  lea     rax, __imp_WinStationOpenServerW
0x18000776b  jmp     __tailMerge_winsta_dll
```
