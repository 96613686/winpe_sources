# __scrt_dllmain_crt_thread_attach

- ea: `0x18000fd9c`
- end: `0x18000fdc4`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180010180`

## callees

- `0x18000fd9c`
- `0x180011c28`
- `0x180011c44`
- `0x1800158e0`

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
0x18000fd9c  sub     rsp, 28h
0x18000fda0  call    __vcrt_thread_attach
0x18000fda5  test    al, al
0x18000fda7  jnz     short loc_18000FDAD
0x18000fda9  xor     al, al
0x18000fdab  jmp     short loc_18000FDBF
0x18000fdad  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000fdb2  test    al, al
0x18000fdb4  jnz     short loc_18000FDBD
0x18000fdb6  call    __vcrt_thread_detach
0x18000fdbb  jmp     short loc_18000FDA9
0x18000fdbd  mov     al, 1
0x18000fdbf  add     rsp, 28h
0x18000fdc3  retn
```
