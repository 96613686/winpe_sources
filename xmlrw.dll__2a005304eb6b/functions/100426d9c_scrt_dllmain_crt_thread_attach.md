# __scrt_dllmain_crt_thread_attach

- ea: `0x100426d9c`
- end: `0x100426dc4`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1004265b0`

## callees

- `0x100426d9c`
- `0x1004275a0`
- `0x1004275bc`
- `0x10042aff0`

## pseudocode

```c
char _scrt_dllmain_crt_thread_attach()
{
  if ( !_vcrt_thread_attach() )
    return 0;
  if ( !_acrt_thread_attach() )
  {
    _vcrt_thread_detach();
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x100426d9c  sub     rsp, 28h
0x100426da0  call    __vcrt_thread_attach
0x100426da5  test    al, al
0x100426da7  jnz     short loc_100426DAD
0x100426da9  xor     al, al
0x100426dab  jmp     short loc_100426DBF
0x100426dad  call    __acrt_thread_attach
0x100426db2  test    al, al
0x100426db4  jnz     short loc_100426DBD
0x100426db6  call    __vcrt_thread_detach
0x100426dbb  jmp     short loc_100426DA9
0x100426dbd  mov     al, 1
0x100426dbf  add     rsp, 28h
0x100426dc3  retn
```
