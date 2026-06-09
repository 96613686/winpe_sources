# __scrt_dllmain_crt_thread_detach

- ea: `0x1800107cc`
- end: `0x1800107e1`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180010350`

## callees

- `0x1800119d0`

## pseudocode

```c
char _scrt_dllmain_crt_thread_detach()
{
  _scrt_stub_for_acrt_uninitialize_critical();
  _scrt_stub_for_acrt_uninitialize_critical();
  return 1;
}

```

## disassembly

```asm
0x1800107cc  sub     rsp, 28h
0x1800107d0  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800107d5  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800107da  mov     al, 1
0x1800107dc  add     rsp, 28h
0x1800107e0  retn
```
