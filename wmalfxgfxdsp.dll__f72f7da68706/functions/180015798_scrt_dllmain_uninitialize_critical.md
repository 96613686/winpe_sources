# __scrt_dllmain_uninitialize_critical

- ea: `0x180015798`
- end: `0x1800157ac`
- name: `__scrt_dllmain_uninitialize_critical`
- size: `20`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180015318`

## callees

- `0x180075af4`

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
0x180015798  sub     rsp, 28h
0x18001579c  xor     ecx, ecx
0x18001579e  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800157a3  add     rsp, 28h
0x1800157a7  jmp     __scrt_stub_for_acrt_uninitialize_critical
```
