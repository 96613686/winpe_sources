# __scrt_dllmain_uninitialize_critical

- ea: `0x180001714`
- end: `0x180001728`
- name: `__scrt_dllmain_uninitialize_critical`
- size: `20`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001378`

## callees

- `0x180003230`
- `0x180006bec`

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
0x180001714  sub     rsp, 28h
0x180001718  xor     ecx, ecx
0x18000171a  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000171f  add     rsp, 28h
0x180001723  jmp     __vcrt_uninitialize_critical
```
