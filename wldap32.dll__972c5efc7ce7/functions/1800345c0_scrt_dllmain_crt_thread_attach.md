# __scrt_dllmain_crt_thread_attach

- ea: `0x1800345c0`
- end: `0x1800345e8`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800341a0`

## callees

- `0x1800345c0`
- `0x180035664`

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
0x1800345c0  sub     rsp, 28h
0x1800345c4  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800345c9  test    al, al
0x1800345cb  jnz     short loc_1800345D1
0x1800345cd  xor     al, al
0x1800345cf  jmp     short loc_1800345E3
0x1800345d1  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800345d6  test    al, al
0x1800345d8  jnz     short loc_1800345E1
0x1800345da  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800345df  jmp     short loc_1800345CD
0x1800345e1  mov     al, 1
0x1800345e3  add     rsp, 28h
0x1800345e7  retn
```
