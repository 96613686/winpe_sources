# __scrt_dllmain_after_initialize_c

- ea: `0x180009834`
- end: `0x180009868`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: `char()`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x1800094b8`

## callees

- `0x180009834`
- `0x180009db8`
- `0x18000a044`
- `0x18000a050`
- `0x18000a0f6`
- `0x18000a11a`

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
0x180009834  sub     rsp, 28h
0x180009838  call    __scrt_is_ucrt_dll_in_use
0x18000983d  test    eax, eax
0x18000983f  jz      short loc_180009848
0x180009841  call    __isa_available_init
0x180009846  jmp     short loc_180009861
0x180009848  call    _get_startup_argv_mode
0x18000984d  mov     ecx, eax; mode
0x18000984f  call    _o__configure_narrow_argv_0
0x180009854  test    eax, eax
0x180009856  jz      short loc_18000985C
0x180009858  xor     al, al
0x18000985a  jmp     short loc_180009863
0x18000985c  call    _initialize_narrow_environment
0x180009861  mov     al, 1
0x180009863  add     rsp, 28h
0x180009867  retn
```
