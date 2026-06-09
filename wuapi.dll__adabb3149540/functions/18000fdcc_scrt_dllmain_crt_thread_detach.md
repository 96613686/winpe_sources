# __scrt_dllmain_crt_thread_detach

- ea: `0x18000fdcc`
- end: `0x18000fde1`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180010180`

## callees

- `0x180011c44`
- `0x1800158e0`

## pseudocode

```c
char _scrt_dllmain_crt_thread_detach()
{
  _scrt_stub_for_acrt_uninitialize_critical();
  _vcrt_thread_detach();
  return 1;
}

```

## disassembly

```asm
0x18000fdcc  sub     rsp, 28h
0x18000fdd0  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000fdd5  call    __vcrt_thread_detach
0x18000fdda  mov     al, 1
0x18000fddc  add     rsp, 28h
0x18000fde0  retn
```
