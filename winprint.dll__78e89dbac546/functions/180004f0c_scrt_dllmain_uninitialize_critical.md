# __scrt_dllmain_uninitialize_critical

- ea: `0x180004f0c`
- end: `0x180004f20`
- name: `__scrt_dllmain_uninitialize_critical`
- size: `20`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180004a68`

## callees

- `0x1800055e8`

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
0x180004f0c  sub     rsp, 28h
0x180004f10  xor     ecx, ecx
0x180004f12  call    __scrt_stub_for_acrt_uninitialize_critical
0x180004f17  add     rsp, 28h
0x180004f1b  jmp     __scrt_stub_for_acrt_uninitialize_critical
```
