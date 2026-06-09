# __scrt_dllmain_crt_thread_attach

- ea: `0x180008b9c`
- end: `0x180008bc4`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180008710`

## callees

- `0x180008b9c`
- `0x180009718`

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
0x180008b9c  sub     rsp, 28h
0x180008ba0  call    __scrt_stub_for_acrt_uninitialize_critical
0x180008ba5  test    al, al
0x180008ba7  jnz     short loc_180008BAD
0x180008ba9  xor     al, al
0x180008bab  jmp     short loc_180008BBF
0x180008bad  call    __scrt_stub_for_acrt_uninitialize_critical
0x180008bb2  test    al, al
0x180008bb4  jnz     short loc_180008BBD
0x180008bb6  call    __scrt_stub_for_acrt_uninitialize_critical
0x180008bbb  jmp     short loc_180008BA9
0x180008bbd  mov     al, 1
0x180008bbf  add     rsp, 28h
0x180008bc3  retn
```
