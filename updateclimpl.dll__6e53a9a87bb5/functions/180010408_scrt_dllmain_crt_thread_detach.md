# __scrt_dllmain_crt_thread_detach

- ea: `0x180010408`
- end: `0x18001041d`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: `char()`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180010740`

## callees

- `0x180011ca4`
- `0x1800147cc`

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
0x180010408  sub     rsp, 28h
0x18001040c  call    __scrt_stub_for_acrt_uninitialize_critical
0x180010411  call    __vcrt_thread_detach
0x180010416  mov     al, 1
0x180010418  add     rsp, 28h
0x18001041c  retn
```
