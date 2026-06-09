# __scrt_dllmain_crt_thread_detach

- ea: `0x18000cb5c`
- end: `0x18000cb71`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000c620`

## callees

- `0x18000dd84`

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
0x18000cb5c  sub     rsp, 28h
0x18000cb60  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000cb65  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000cb6a  mov     al, 1
0x18000cb6c  add     rsp, 28h
0x18000cb70  retn
```
