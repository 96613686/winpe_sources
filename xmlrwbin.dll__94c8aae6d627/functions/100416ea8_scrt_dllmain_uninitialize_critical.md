# __scrt_dllmain_uninitialize_critical

- ea: `0x100416ea8`
- end: `0x100416ebc`
- name: `__scrt_dllmain_uninitialize_critical`
- size: `20`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x100416734`

## callees

- `0x100417624`
- `0x10041b0d0`

## pseudocode

```c
__vcrt_bool _scrt_dllmain_uninitialize_critical()
{
  _acrt_uninitialize_critical(0);
  return _vcrt_uninitialize_critical();
}

```

## disassembly

```asm
0x100416ea8  sub     rsp, 28h
0x100416eac  xor     ecx, ecx; Terminating
0x100416eae  call    __acrt_uninitialize_critical
0x100416eb3  add     rsp, 28h
0x100416eb7  jmp     __vcrt_uninitialize_critical
```
