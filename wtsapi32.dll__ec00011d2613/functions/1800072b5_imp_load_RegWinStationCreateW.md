# __imp_load_RegWinStationCreateW

- ea: `0x1800072b5`
- end: `0x1800072c1`
- name: `__imp_load_RegWinStationCreateW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180007200`

## import_xrefs

- `REGAPI!RegWinStationCreateW` at `0x1800072b5`

## pseudocode

```c
__int64 load_RegWinStationCreateW()
{
  return _tailMerge_regapi_dll();
}

```

## disassembly

```asm
0x1800072b5  lea     rax, __imp_RegWinStationCreateW
0x1800072bc  jmp     __tailMerge_regapi_dll
```
