# __scrt_dllmain_uninitialize_critical

- ea: `0x1800029ac`
- end: `0x1800029c0`
- name: `__scrt_dllmain_uninitialize_critical`
- size: `20`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800025c8`

## callees

- `0x1800036a0`

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
0x1800029ac  sub     rsp, 28h
0x1800029b0  xor     ecx, ecx
0x1800029b2  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800029b7  add     rsp, 28h
0x1800029bb  jmp     __scrt_stub_for_acrt_uninitialize_critical
```
