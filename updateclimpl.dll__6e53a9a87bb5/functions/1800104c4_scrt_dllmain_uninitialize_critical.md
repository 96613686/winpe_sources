# __scrt_dllmain_uninitialize_critical

- ea: `0x1800104c4`
- end: `0x1800104d8`
- name: `__scrt_dllmain_uninitialize_critical`
- size: `20`
- prototype: `__vcrt_bool()`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800108b0`

## callees

- `0x180011cdc`
- `0x1800147cc`

## pseudocode

```c
__vcrt_bool _scrt_dllmain_uninitialize_critical()
{
  _scrt_stub_for_acrt_uninitialize_critical(0);
  return _vcrt_uninitialize_critical();
}

```

## disassembly

```asm
0x1800104c4  sub     rsp, 28h
0x1800104c8  xor     ecx, ecx
0x1800104ca  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800104cf  add     rsp, 28h
0x1800104d3  jmp     __vcrt_uninitialize_critical
```
