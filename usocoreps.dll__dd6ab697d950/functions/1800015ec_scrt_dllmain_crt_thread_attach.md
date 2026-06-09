# __scrt_dllmain_crt_thread_attach

- ea: `0x1800015ec`
- end: `0x180001614`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: `char()`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001190`

## callees

- `0x1800015ec`
- `0x1800021bc`

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
0x1800015ec  sub     rsp, 28h
0x1800015f0  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800015f5  test    al, al
0x1800015f7  jnz     short loc_1800015FD
0x1800015f9  xor     al, al
0x1800015fb  jmp     short loc_18000160F
0x1800015fd  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001602  test    al, al
0x180001604  jnz     short loc_18000160D
0x180001606  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000160b  jmp     short loc_1800015F9
0x18000160d  mov     al, 1
0x18000160f  add     rsp, 28h
0x180001613  retn
```
