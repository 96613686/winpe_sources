# __scrt_dllmain_after_initialize_c

- ea: `0x18000e6dc`
- end: `0x18000e710`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x18000e328`

## callees

- `0x18000e6dc`
- `0x18000ec1c`
- `0x18000eea8`
- `0x18000eeb4`
- `0x18000ef5e`
- `0x18000ef82`

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
0x18000e6dc  sub     rsp, 28h
0x18000e6e0  call    __scrt_is_ucrt_dll_in_use
0x18000e6e5  test    eax, eax
0x18000e6e7  jz      short loc_18000E6F0
0x18000e6e9  call    __isa_available_init
0x18000e6ee  jmp     short loc_18000E709
0x18000e6f0  call    _get_startup_argv_mode
0x18000e6f5  mov     ecx, eax; mode
0x18000e6f7  call    _o__configure_narrow_argv_0
0x18000e6fc  test    eax, eax
0x18000e6fe  jz      short loc_18000E704
0x18000e700  xor     al, al
0x18000e702  jmp     short loc_18000E70B
0x18000e704  call    _initialize_narrow_environment
0x18000e709  mov     al, 1
0x18000e70b  add     rsp, 28h
0x18000e70f  retn
```
