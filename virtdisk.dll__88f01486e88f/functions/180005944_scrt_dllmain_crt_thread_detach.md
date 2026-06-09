# __scrt_dllmain_crt_thread_detach

- ea: `0x180005944`
- end: `0x180005959`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: `char()`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800053c0`

## callees

- `0x1800061b4`

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
0x180005944  sub     rsp, 28h
0x180005948  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000594d  call    __scrt_stub_for_acrt_uninitialize_critical
0x180005952  mov     al, 1
0x180005954  add     rsp, 28h
0x180005958  retn
```
