# __scrt_dllmain_crt_thread_attach

- ea: `0x1800019f0`
- end: `0x180001a18`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001220`

## callees

- `0x1800019f0`
- `0x180002700`

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
0x1800019f0  sub     rsp, 28h
0x1800019f4  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800019f9  test    al, al
0x1800019fb  jnz     short loc_180001A01
0x1800019fd  xor     al, al
0x1800019ff  jmp     short loc_180001A13
0x180001a01  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001a06  test    al, al
0x180001a08  jnz     short loc_180001A11
0x180001a0a  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001a0f  jmp     short loc_1800019FD
0x180001a11  mov     al, 1
0x180001a13  add     rsp, 28h
0x180001a17  retn
```
