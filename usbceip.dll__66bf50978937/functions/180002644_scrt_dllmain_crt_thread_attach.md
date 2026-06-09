# __scrt_dllmain_crt_thread_attach

- ea: `0x180002644`
- end: `0x18000266c`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: `char()`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002090`

## callees

- `0x180002644`
- `0x180002fd4`

## pseudocode

```c
char _scrt_dllmain_crt_thread_attach()
{
  if ( !(unsigned __int8)_scrt_stub_for_acrt_uninitialize_critical() )
    return 0;
  if ( !(unsigned __int8)_scrt_stub_for_acrt_uninitialize_critical() )
  {
    _scrt_stub_for_acrt_uninitialize_critical();
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x180002644  sub     rsp, 28h
0x180002648  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000264d  test    al, al
0x18000264f  jnz     short loc_180002655
0x180002651  xor     al, al
0x180002653  jmp     short loc_180002667
0x180002655  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000265a  test    al, al
0x18000265c  jnz     short loc_180002665
0x18000265e  call    __scrt_stub_for_acrt_uninitialize_critical
0x180002663  jmp     short loc_180002651
0x180002665  mov     al, 1
0x180002667  add     rsp, 28h
0x18000266b  retn
```
