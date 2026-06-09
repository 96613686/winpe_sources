# __scrt_dllmain_crt_thread_attach

- ea: `0x180001858`
- end: `0x180001880`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800013f0`

## callees

- `0x180001858`
- `0x18000229c`

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
0x180001858  sub     rsp, 28h
0x18000185c  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001861  test    al, al
0x180001863  jnz     short loc_180001869
0x180001865  xor     al, al
0x180001867  jmp     short loc_18000187B
0x180001869  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000186e  test    al, al
0x180001870  jnz     short loc_180001879
0x180001872  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001877  jmp     short loc_180001865
0x180001879  mov     al, 1
0x18000187b  add     rsp, 28h
0x18000187f  retn
```
