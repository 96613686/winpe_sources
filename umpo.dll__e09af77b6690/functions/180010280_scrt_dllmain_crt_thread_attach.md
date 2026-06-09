# __scrt_dllmain_crt_thread_attach

- ea: `0x180010280`
- end: `0x1800102a8`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: `char()`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000fd00`

## callees

- `0x180010280`
- `0x180010e20`

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
0x180010280  sub     rsp, 28h
0x180010284  call    __scrt_stub_for_acrt_uninitialize_critical
0x180010289  test    al, al
0x18001028b  jnz     short loc_180010291
0x18001028d  xor     al, al
0x18001028f  jmp     short loc_1800102A3
0x180010291  call    __scrt_stub_for_acrt_uninitialize_critical
0x180010296  test    al, al
0x180010298  jnz     short loc_1800102A1
0x18001029a  call    __scrt_stub_for_acrt_uninitialize_critical
0x18001029f  jmp     short loc_18001028D
0x1800102a1  mov     al, 1
0x1800102a3  add     rsp, 28h
0x1800102a7  retn
```
