# __scrt_dllmain_crt_thread_attach

- ea: `0x180001f78`
- end: `0x180001fa0`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001a50`

## callees

- `0x180001f78`
- `0x18000276c`

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
0x180001f78  sub     rsp, 28h
0x180001f7c  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001f81  test    al, al
0x180001f83  jnz     short loc_180001F89
0x180001f85  xor     al, al
0x180001f87  jmp     short loc_180001F9B
0x180001f89  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001f8e  test    al, al
0x180001f90  jnz     short loc_180001F99
0x180001f92  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001f97  jmp     short loc_180001F85
0x180001f99  mov     al, 1
0x180001f9b  add     rsp, 28h
0x180001f9f  retn
```
