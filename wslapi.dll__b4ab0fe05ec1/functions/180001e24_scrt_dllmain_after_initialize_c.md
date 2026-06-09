# __scrt_dllmain_after_initialize_c

- ea: `0x180001e24`
- end: `0x180001e58`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: `char()`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180001aa8`

## callees

- `0x180001e24`
- `0x180002690`
- `0x18000291c`
- `0x180002928`
- `0x180002a0e`
- `0x180002a32`

## pseudocode

```c
char _scrt_dllmain_after_initialize_c()
{
  _crt_argv_mode startup_argv_mode; // eax

  if ( (unsigned int)_scrt_is_ucrt_dll_in_use() )
  {
    _isa_available_init();
  }
  else
  {
    startup_argv_mode = get_startup_argv_mode();
    if ( o__configure_narrow_argv_0(startup_argv_mode) )
      return 0;
    initialize_narrow_environment();
  }
  return 1;
}

```

## disassembly

```asm
0x180001e24  sub     rsp, 28h
0x180001e28  call    __scrt_is_ucrt_dll_in_use
0x180001e2d  test    eax, eax
0x180001e2f  jz      short loc_180001E38
0x180001e31  call    __isa_available_init
0x180001e36  jmp     short loc_180001E51
0x180001e38  call    _get_startup_argv_mode
0x180001e3d  mov     ecx, eax; mode
0x180001e3f  call    _o__configure_narrow_argv_0
0x180001e44  test    eax, eax
0x180001e46  jz      short loc_180001E4C
0x180001e48  xor     al, al
0x180001e4a  jmp     short loc_180001E53
0x180001e4c  call    _initialize_narrow_environment
0x180001e51  mov     al, 1
0x180001e53  add     rsp, 28h
0x180001e57  retn
```
