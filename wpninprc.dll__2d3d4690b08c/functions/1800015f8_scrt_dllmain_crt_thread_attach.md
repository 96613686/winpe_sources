# __scrt_dllmain_crt_thread_attach

- ea: `0x1800015f8`
- end: `0x180001620`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800011a0`

## callees

- `0x1800015f8`
- `0x18000210c`

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
0x1800015f8  sub     rsp, 28h
0x1800015fc  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001601  test    al, al
0x180001603  jnz     short loc_180001609
0x180001605  xor     al, al
0x180001607  jmp     short loc_18000161B
0x180001609  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000160e  test    al, al
0x180001610  jnz     short loc_180001619
0x180001612  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001617  jmp     short loc_180001605
0x180001619  mov     al, 1
0x18000161b  add     rsp, 28h
0x18000161f  retn
```
