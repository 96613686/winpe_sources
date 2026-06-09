# __scrt_dllmain_uninitialize_critical

- ea: `0x18000fe38`
- end: `0x18000fe4c`
- name: `__scrt_dllmain_uninitialize_critical`
- size: `20`
- prototype: `__vcrt_bool()`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800102a0`

## callees

- `0x180011c2c`
- `0x180015890`

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
0x18000fe38  sub     rsp, 28h
0x18000fe3c  xor     ecx, ecx
0x18000fe3e  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000fe43  add     rsp, 28h
0x18000fe47  jmp     __vcrt_uninitialize_critical
```
