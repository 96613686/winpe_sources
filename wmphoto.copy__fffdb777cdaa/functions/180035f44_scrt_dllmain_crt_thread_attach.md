# __scrt_dllmain_crt_thread_attach

- ea: `0x180035f44`
- end: `0x180035f6c`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180035ae0`

## callees

- `0x180035f44`
- `0x180036e2c`

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
0x180035f44  sub     rsp, 28h
0x180035f48  call    __scrt_stub_for_acrt_uninitialize_critical
0x180035f4d  test    al, al
0x180035f4f  jnz     short loc_180035F55
0x180035f51  xor     al, al
0x180035f53  jmp     short loc_180035F67
0x180035f55  call    __scrt_stub_for_acrt_uninitialize_critical
0x180035f5a  test    al, al
0x180035f5c  jnz     short loc_180035F65
0x180035f5e  call    __scrt_stub_for_acrt_uninitialize_critical
0x180035f63  jmp     short loc_180035F51
0x180035f65  mov     al, 1
0x180035f67  add     rsp, 28h
0x180035f6b  retn
```
