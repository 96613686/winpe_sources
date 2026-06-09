# __scrt_dllmain_crt_thread_attach

- ea: `0x180003d94`
- end: `0x180003dbc`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180003840`

## callees

- `0x180003d94`
- `0x1800045e0`

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
0x180003d94  sub     rsp, 28h
0x180003d98  call    __scrt_stub_for_acrt_uninitialize_critical
0x180003d9d  test    al, al
0x180003d9f  jnz     short loc_180003DA5
0x180003da1  xor     al, al
0x180003da3  jmp     short loc_180003DB7
0x180003da5  call    __scrt_stub_for_acrt_uninitialize_critical
0x180003daa  test    al, al
0x180003dac  jnz     short loc_180003DB5
0x180003dae  call    __scrt_stub_for_acrt_uninitialize_critical
0x180003db3  jmp     short loc_180003DA1
0x180003db5  mov     al, 1
0x180003db7  add     rsp, 28h
0x180003dbb  retn
```
