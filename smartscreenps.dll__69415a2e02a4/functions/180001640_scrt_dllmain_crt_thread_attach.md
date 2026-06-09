# __scrt_dllmain_crt_thread_attach

- ea: `0x180001640`
- end: `0x180001668`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180001220`

## callees

- `0x180001640`
- `0x1800031dc`
- `0x1800031f8`
- `0x180006bec`

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
0x180001640  sub     rsp, 28h
0x180001644  call    __vcrt_thread_attach
0x180001649  test    al, al
0x18000164b  jnz     short loc_180001651
0x18000164d  xor     al, al
0x18000164f  jmp     short loc_180001663
0x180001651  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001656  test    al, al
0x180001658  jnz     short loc_180001661
0x18000165a  call    __vcrt_thread_detach
0x18000165f  jmp     short loc_18000164D
0x180001661  mov     al, 1
0x180001663  add     rsp, 28h
0x180001667  retn
```
