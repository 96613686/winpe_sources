# __scrt_dllmain_crt_thread_attach

- ea: `0x180009880`
- end: `0x1800098a8`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: `char()`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180009460`

## callees

- `0x180009880`
- `0x18000b030`

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
0x180009880  sub     rsp, 28h
0x180009884  call    __scrt_stub_for_acrt_uninitialize_critical
0x180009889  test    al, al
0x18000988b  jnz     short loc_180009891
0x18000988d  xor     al, al
0x18000988f  jmp     short loc_1800098A3
0x180009891  call    __scrt_stub_for_acrt_uninitialize_critical
0x180009896  test    al, al
0x180009898  jnz     short loc_1800098A1
0x18000989a  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000989f  jmp     short loc_18000988D
0x1800098a1  mov     al, 1
0x1800098a3  add     rsp, 28h
0x1800098a7  retn
```
