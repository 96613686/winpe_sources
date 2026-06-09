# __scrt_dllmain_crt_thread_attach

- ea: `0x18000267c`
- end: `0x1800026a4`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002200`

## callees

- `0x18000267c`
- `0x180002efc`

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
0x18000267c  sub     rsp, 28h
0x180002680  call    __scrt_stub_for_acrt_uninitialize_critical
0x180002685  test    al, al
0x180002687  jnz     short loc_18000268D
0x180002689  xor     al, al
0x18000268b  jmp     short loc_18000269F
0x18000268d  call    __scrt_stub_for_acrt_uninitialize_critical
0x180002692  test    al, al
0x180002694  jnz     short loc_18000269D
0x180002696  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000269b  jmp     short loc_180002689
0x18000269d  mov     al, 1
0x18000269f  add     rsp, 28h
0x1800026a3  retn
```
