# __scrt_dllmain_uninitialize_critical

- ea: `0x180002854`
- end: `0x180002868`
- name: `__scrt_dllmain_uninitialize_critical`
- size: `20`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800024b8`

## callees

- `0x180003210`

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
0x180002854  sub     rsp, 28h
0x180002858  xor     ecx, ecx
0x18000285a  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000285f  add     rsp, 28h
0x180002863  jmp     __scrt_stub_for_acrt_uninitialize_critical
```
