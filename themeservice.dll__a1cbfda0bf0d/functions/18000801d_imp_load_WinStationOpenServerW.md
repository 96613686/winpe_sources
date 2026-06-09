# __imp_load_WinStationOpenServerW

- ea: `0x18000801d`
- end: `0x180008029`
- name: `__imp_load_WinStationOpenServerW`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180007f9e`

## import_xrefs

- `ext-ms-win-session-winsta-l1-1-0!WinStationOpenServerW` at `0x18000801d`

## pseudocode

```c
__int64 load_WinStationOpenServerW()
{
  return _tailMerge_ext_ms_win_session_winsta_l1_1_0_dll();
}

```

## disassembly

```asm
0x18000801d  lea     rax, __imp_WinStationOpenServerW
0x180008024  jmp     __tailMerge_ext_ms_win_session_winsta_l1_1_0_dll
```
