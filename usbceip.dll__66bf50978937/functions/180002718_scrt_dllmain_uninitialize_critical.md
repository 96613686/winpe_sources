# __scrt_dllmain_uninitialize_critical

- ea: `0x180002718`
- end: `0x18000272c`
- name: `__scrt_dllmain_uninitialize_critical`
- size: `20`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800021e8`

## callees

- `0x180002fd4`

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
0x180002718  sub     rsp, 28h
0x18000271c  xor     ecx, ecx
0x18000271e  call    __scrt_stub_for_acrt_uninitialize_critical
0x180002723  add     rsp, 28h
0x180002727  jmp     __scrt_stub_for_acrt_uninitialize_critical
```
