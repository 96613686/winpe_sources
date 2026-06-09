# __scrt_dllmain_crt_thread_attach

- ea: `0x1800017e8`
- end: `0x180001810`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001300`

## callees

- `0x1800017e8`
- `0x180002004`

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
0x1800017e8  sub     rsp, 28h
0x1800017ec  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800017f1  test    al, al
0x1800017f3  jnz     short loc_1800017F9
0x1800017f5  xor     al, al
0x1800017f7  jmp     short loc_18000180B
0x1800017f9  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800017fe  test    al, al
0x180001800  jnz     short loc_180001809
0x180001802  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001807  jmp     short loc_1800017F5
0x180001809  mov     al, 1
0x18000180b  add     rsp, 28h
0x18000180f  retn
```
