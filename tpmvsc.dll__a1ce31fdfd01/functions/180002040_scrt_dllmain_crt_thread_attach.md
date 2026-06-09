# __scrt_dllmain_crt_thread_attach

- ea: `0x180002040`
- end: `0x180002068`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: `char()`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001b40`

## callees

- `0x180002040`
- `0x180002c08`

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
0x180002040  sub     rsp, 28h
0x180002044  call    __scrt_stub_for_acrt_uninitialize_critical
0x180002049  test    al, al
0x18000204b  jnz     short loc_180002051
0x18000204d  xor     al, al
0x18000204f  jmp     short loc_180002063
0x180002051  call    __scrt_stub_for_acrt_uninitialize_critical
0x180002056  test    al, al
0x180002058  jnz     short loc_180002061
0x18000205a  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000205f  jmp     short loc_18000204D
0x180002061  mov     al, 1
0x180002063  add     rsp, 28h
0x180002067  retn
```
