# __scrt_dllmain_crt_thread_attach

- ea: `0x180036514`
- end: `0x18003653c`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800360b0`

## callees

- `0x180036514`
- `0x1800373fc`

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
0x180036514  sub     rsp, 28h
0x180036518  call    __scrt_stub_for_acrt_uninitialize_critical
0x18003651d  test    al, al
0x18003651f  jnz     short loc_180036525
0x180036521  xor     al, al
0x180036523  jmp     short loc_180036537
0x180036525  call    __scrt_stub_for_acrt_uninitialize_critical
0x18003652a  test    al, al
0x18003652c  jnz     short loc_180036535
0x18003652e  call    __scrt_stub_for_acrt_uninitialize_critical
0x180036533  jmp     short loc_180036521
0x180036535  mov     al, 1
0x180036537  add     rsp, 28h
0x18003653b  retn
```
