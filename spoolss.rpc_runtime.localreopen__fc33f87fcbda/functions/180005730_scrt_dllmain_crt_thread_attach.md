# __scrt_dllmain_crt_thread_attach

- ea: `0x180005730`
- end: `0x180005758`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180005310`

## callees

- `0x180005730`
- `0x180006804`

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
0x180005730  sub     rsp, 28h
0x180005734  call    __scrt_stub_for_acrt_uninitialize_critical
0x180005739  test    al, al
0x18000573b  jnz     short loc_180005741
0x18000573d  xor     al, al
0x18000573f  jmp     short loc_180005753
0x180005741  call    __scrt_stub_for_acrt_uninitialize_critical
0x180005746  test    al, al
0x180005748  jnz     short loc_180005751
0x18000574a  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000574f  jmp     short loc_18000573D
0x180005751  mov     al, 1
0x180005753  add     rsp, 28h
0x180005757  retn
```
