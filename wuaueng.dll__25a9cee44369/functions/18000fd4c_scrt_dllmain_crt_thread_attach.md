# __scrt_dllmain_crt_thread_attach

- ea: `0x18000fd4c`
- end: `0x18000fd74`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: `char()`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180010130`

## callees

- `0x18000fd4c`
- `0x180011bd8`
- `0x180011bf4`
- `0x180015890`

## pseudocode

```c
char _scrt_dllmain_crt_thread_attach()
{
  if ( !_vcrt_thread_attach() )
    return 0;
  if ( !(unsigned __int8)_scrt_stub_for_acrt_uninitialize_critical() )
  {
    _vcrt_thread_detach();
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x18000fd4c  sub     rsp, 28h
0x18000fd50  call    __vcrt_thread_attach
0x18000fd55  test    al, al
0x18000fd57  jnz     short loc_18000FD5D
0x18000fd59  xor     al, al
0x18000fd5b  jmp     short loc_18000FD6F
0x18000fd5d  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000fd62  test    al, al
0x18000fd64  jnz     short loc_18000FD6D
0x18000fd66  call    __vcrt_thread_detach
0x18000fd6b  jmp     short loc_18000FD59
0x18000fd6d  mov     al, 1
0x18000fd6f  add     rsp, 28h
0x18000fd73  retn
```
