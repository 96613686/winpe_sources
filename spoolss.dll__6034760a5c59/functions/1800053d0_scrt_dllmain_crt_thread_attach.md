# __scrt_dllmain_crt_thread_attach

- ea: `0x1800053d0`
- end: `0x1800053f8`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180004fb0`

## callees

- `0x1800053d0`
- `0x180006494`

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
0x1800053d0  sub     rsp, 28h
0x1800053d4  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800053d9  test    al, al
0x1800053db  jnz     short loc_1800053E1
0x1800053dd  xor     al, al
0x1800053df  jmp     short loc_1800053F3
0x1800053e1  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800053e6  test    al, al
0x1800053e8  jnz     short loc_1800053F1
0x1800053ea  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800053ef  jmp     short loc_1800053DD
0x1800053f1  mov     al, 1
0x1800053f3  add     rsp, 28h
0x1800053f7  retn
```
