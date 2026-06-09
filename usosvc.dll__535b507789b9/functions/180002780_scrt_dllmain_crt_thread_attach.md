# __scrt_dllmain_crt_thread_attach

- ea: `0x180002780`
- end: `0x1800027a8`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: `char()`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002360`

## callees

- `0x180002780`
- `0x180003210`

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
0x180002780  sub     rsp, 28h
0x180002784  call    __scrt_stub_for_acrt_uninitialize_critical
0x180002789  test    al, al
0x18000278b  jnz     short loc_180002791
0x18000278d  xor     al, al
0x18000278f  jmp     short loc_1800027A3
0x180002791  call    __scrt_stub_for_acrt_uninitialize_critical
0x180002796  test    al, al
0x180002798  jnz     short loc_1800027A1
0x18000279a  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000279f  jmp     short loc_18000278D
0x1800027a1  mov     al, 1
0x1800027a3  add     rsp, 28h
0x1800027a7  retn
```
