# __scrt_dllmain_crt_thread_attach

- ea: `0x180002218`
- end: `0x180002240`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: `char()`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001d60`

## callees

- `0x180002218`
- `0x180002ca8`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
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
0x180002218  sub     rsp, 28h
0x18000221c  call    __scrt_stub_for_acrt_uninitialize_critical
0x180002221  test    al, al
0x180002223  jnz     short loc_180002229
0x180002225  xor     al, al
0x180002227  jmp     short loc_18000223B
0x180002229  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000222e  test    al, al
0x180002230  jnz     short loc_180002239
0x180002232  call    __scrt_stub_for_acrt_uninitialize_critical
0x180002237  jmp     short loc_180002225
0x180002239  mov     al, 1
0x18000223b  add     rsp, 28h
0x18000223f  retn
```
