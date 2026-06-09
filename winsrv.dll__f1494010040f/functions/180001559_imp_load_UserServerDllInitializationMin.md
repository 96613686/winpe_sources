# __imp_load_UserServerDllInitializationMin

- ea: `0x180001559`
- end: `0x180001565`
- name: `__imp_load_UserServerDllInitializationMin`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800014da`

## import_xrefs

- `ext-ms-win-core-winsrv-min-l1-1-0!UserServerDllInitializationMin` at `0x180001559`

## pseudocode

```c
__int64 load_UserServerDllInitializationMin()
{
  return _tailMerge_ext_ms_win_core_winsrv_min_l1_1_0_dll();
}

```

## disassembly

```asm
0x180001559  lea     rax, __imp_UserServerDllInitializationMin
0x180001560  jmp     __tailMerge_ext_ms_win_core_winsrv_min_l1_1_0_dll
```
