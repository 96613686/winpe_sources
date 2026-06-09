# __scrt_dllmain_crt_thread_detach

- ea: `0x18000fd7c`
- end: `0x18000fd91`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: `char()`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180010130`

## callees

- `0x180011bf4`
- `0x180015890`

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
0x18000fd7c  sub     rsp, 28h
0x18000fd80  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000fd85  call    __vcrt_thread_detach
0x18000fd8a  mov     al, 1
0x18000fd8c  add     rsp, 28h
0x18000fd90  retn
```
