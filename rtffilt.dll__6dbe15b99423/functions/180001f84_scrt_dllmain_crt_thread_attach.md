# __scrt_dllmain_crt_thread_attach

- ea: `0x180001f84`
- end: `0x180001fac`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001ac0`

## callees

- `0x180001f84`
- `0x180002b30`

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
0x180001f84  sub     rsp, 28h
0x180001f88  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001f8d  test    al, al
0x180001f8f  jnz     short loc_180001F95
0x180001f91  xor     al, al
0x180001f93  jmp     short loc_180001FA7
0x180001f95  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001f9a  test    al, al
0x180001f9c  jnz     short loc_180001FA5
0x180001f9e  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001fa3  jmp     short loc_180001F91
0x180001fa5  mov     al, 1
0x180001fa7  add     rsp, 28h
0x180001fab  retn
```
