# __scrt_dllmain_crt_thread_detach

- ea: `0x18000161c`
- end: `0x180001631`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: `char()`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001190`

## callees

- `0x1800021bc`

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
0x18000161c  sub     rsp, 28h
0x180001620  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001625  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000162a  mov     al, 1
0x18000162c  add     rsp, 28h
0x180001630  retn
```
