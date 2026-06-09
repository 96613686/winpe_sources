# __scrt_dllmain_uninitialize_critical

- ea: `0x18000fe88`
- end: `0x18000fe9c`
- name: `__scrt_dllmain_uninitialize_critical`
- size: `20`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800102f0`

## callees

- `0x180011c7c`
- `0x1800158e0`

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
0x18000fe88  sub     rsp, 28h
0x18000fe8c  xor     ecx, ecx
0x18000fe8e  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000fe93  add     rsp, 28h
0x18000fe97  jmp     __vcrt_uninitialize_critical
```
