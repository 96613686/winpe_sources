# __scrt_dllmain_crt_thread_detach

- ea: `0x180005760`
- end: `0x180005775`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180005310`

## callees

- `0x180006804`

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
0x180005760  sub     rsp, 28h
0x180005764  call    __scrt_stub_for_acrt_uninitialize_critical
0x180005769  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000576e  mov     al, 1
0x180005770  add     rsp, 28h
0x180005774  retn
```
