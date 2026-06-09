# __scrt_dllmain_uninitialize_critical

- ea: `0x18000192c`
- end: `0x180001940`
- name: `__scrt_dllmain_uninitialize_critical`
- size: `20`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001548`

## callees

- `0x18000229c`

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
0x18000192c  sub     rsp, 28h
0x180001930  xor     ecx, ecx
0x180001932  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001937  add     rsp, 28h
0x18000193b  jmp     __scrt_stub_for_acrt_uninitialize_critical
```
