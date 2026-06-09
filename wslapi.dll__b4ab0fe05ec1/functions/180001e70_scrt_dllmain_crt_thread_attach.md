# __scrt_dllmain_crt_thread_attach

- ea: `0x180001e70`
- end: `0x180001e98`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: `char()`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001a50`

## callees

- `0x180001e70`
- `0x180002b50`

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
0x180001e70  sub     rsp, 28h
0x180001e74  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001e79  test    al, al
0x180001e7b  jnz     short loc_180001E81
0x180001e7d  xor     al, al
0x180001e7f  jmp     short loc_180001E93
0x180001e81  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001e86  test    al, al
0x180001e88  jnz     short loc_180001E91
0x180001e8a  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001e8f  jmp     short loc_180001E7D
0x180001e91  mov     al, 1
0x180001e93  add     rsp, 28h
0x180001e97  retn
```
