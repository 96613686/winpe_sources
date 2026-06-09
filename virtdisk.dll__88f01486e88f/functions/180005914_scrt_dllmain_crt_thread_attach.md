# __scrt_dllmain_crt_thread_attach

- ea: `0x180005914`
- end: `0x18000593c`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: `char()`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800053c0`

## callees

- `0x180005914`
- `0x1800061b4`

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
0x180005914  sub     rsp, 28h
0x180005918  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000591d  test    al, al
0x18000591f  jnz     short loc_180005925
0x180005921  xor     al, al
0x180005923  jmp     short loc_180005937
0x180005925  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000592a  test    al, al
0x18000592c  jnz     short loc_180005935
0x18000592e  call    __scrt_stub_for_acrt_uninitialize_critical
0x180005933  jmp     short loc_180005921
0x180005935  mov     al, 1
0x180005937  add     rsp, 28h
0x18000593b  retn
```
