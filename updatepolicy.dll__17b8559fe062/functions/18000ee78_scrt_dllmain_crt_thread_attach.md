# __scrt_dllmain_crt_thread_attach

- ea: `0x18000ee78`
- end: `0x18000eea0`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: `char()`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18000f1e0`

## callees

- `0x18000ee78`
- `0x180010c98`
- `0x180010cb4`
- `0x180015314`

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
0x18000ee78  sub     rsp, 28h
0x18000ee7c  call    __vcrt_thread_attach
0x18000ee81  test    al, al
0x18000ee83  jnz     short loc_18000EE89
0x18000ee85  xor     al, al
0x18000ee87  jmp     short loc_18000EE9B
0x18000ee89  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000ee8e  test    al, al
0x18000ee90  jnz     short loc_18000EE99
0x18000ee92  call    __vcrt_thread_detach
0x18000ee97  jmp     short loc_18000EE85
0x18000ee99  mov     al, 1
0x18000ee9b  add     rsp, 28h
0x18000ee9f  retn
```
