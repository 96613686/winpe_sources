# __scrt_dllmain_crt_thread_attach

- ea: `0x1800067d8`
- end: `0x180006800`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800062b0`

## callees

- `0x1800067d8`
- `0x1800075bc`

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
0x1800067d8  sub     rsp, 28h
0x1800067dc  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800067e1  test    al, al
0x1800067e3  jnz     short loc_1800067E9
0x1800067e5  xor     al, al
0x1800067e7  jmp     short loc_1800067FB
0x1800067e9  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800067ee  test    al, al
0x1800067f0  jnz     short loc_1800067F9
0x1800067f2  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800067f7  jmp     short loc_1800067E5
0x1800067f9  mov     al, 1
0x1800067fb  add     rsp, 28h
0x1800067ff  retn
```
