# __scrt_dllmain_uninitialize_critical

- ea: `0x1800365e8`
- end: `0x1800365fc`
- name: `__scrt_dllmain_uninitialize_critical`
- size: `20`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180036208`

## callees

- `0x1800373fc`

## pseudocode

```c
__int64 _scrt_dllmain_uninitialize_critical()
{
  __int64 v0; // rcx

  _scrt_stub_for_acrt_uninitialize_critical(0);
  return _scrt_stub_for_acrt_uninitialize_critical(v0);
}

```

## disassembly

```asm
0x1800365e8  sub     rsp, 28h
0x1800365ec  xor     ecx, ecx
0x1800365ee  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800365f3  add     rsp, 28h
0x1800365f7  jmp     __scrt_stub_for_acrt_uninitialize_critical
```
