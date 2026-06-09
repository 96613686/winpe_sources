# __scrt_dllmain_uninitialize_critical

- ea: `0x1800059e8`
- end: `0x1800059fc`
- name: `__scrt_dllmain_uninitialize_critical`
- size: `20`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180005518`

## callees

- `0x1800061b4`

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
0x1800059e8  sub     rsp, 28h
0x1800059ec  xor     ecx, ecx
0x1800059ee  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800059f3  add     rsp, 28h
0x1800059f7  jmp     __scrt_stub_for_acrt_uninitialize_critical
```
