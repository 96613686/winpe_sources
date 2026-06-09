# __scrt_dllmain_crt_thread_attach

- ea: `0x1800025c0`
- end: `0x1800025e8`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002170`

## callees

- `0x1800025c0`
- `0x18000311c`

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
0x1800025c0  sub     rsp, 28h
0x1800025c4  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800025c9  test    al, al
0x1800025cb  jnz     short loc_1800025D1
0x1800025cd  xor     al, al
0x1800025cf  jmp     short loc_1800025E3
0x1800025d1  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800025d6  test    al, al
0x1800025d8  jnz     short loc_1800025E1
0x1800025da  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800025df  jmp     short loc_1800025CD
0x1800025e1  mov     al, 1
0x1800025e3  add     rsp, 28h
0x1800025e7  retn
```
