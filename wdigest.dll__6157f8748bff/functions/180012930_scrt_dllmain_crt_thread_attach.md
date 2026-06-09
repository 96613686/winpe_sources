# __scrt_dllmain_crt_thread_attach

- ea: `0x180012930`
- end: `0x180012958`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180012510`

## callees

- `0x180012930`
- `0x180013c20`

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
0x180012930  sub     rsp, 28h
0x180012934  call    __scrt_stub_for_acrt_uninitialize_critical
0x180012939  test    al, al
0x18001293b  jnz     short loc_180012941
0x18001293d  xor     al, al
0x18001293f  jmp     short loc_180012953
0x180012941  call    __scrt_stub_for_acrt_uninitialize_critical
0x180012946  test    al, al
0x180012948  jnz     short loc_180012951
0x18001294a  call    __scrt_stub_for_acrt_uninitialize_critical
0x18001294f  jmp     short loc_18001293D
0x180012951  mov     al, 1
0x180012953  add     rsp, 28h
0x180012957  retn
```
