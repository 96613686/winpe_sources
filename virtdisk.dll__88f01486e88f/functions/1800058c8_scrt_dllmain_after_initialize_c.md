# __scrt_dllmain_after_initialize_c

- ea: `0x1800058c8`
- end: `0x1800058fc`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: `char()`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180005418`

## callees

- `0x1800058c8`
- `0x180005c78`
- `0x180005f04`
- `0x180005f10`
- `0x180005f8e`
- `0x180005fa6`

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
0x1800058c8  sub     rsp, 28h
0x1800058cc  call    __scrt_is_ucrt_dll_in_use
0x1800058d1  test    eax, eax
0x1800058d3  jz      short loc_1800058DC
0x1800058d5  call    __isa_available_init
0x1800058da  jmp     short loc_1800058F5
0x1800058dc  call    _get_startup_argv_mode
0x1800058e1  mov     ecx, eax; mode
0x1800058e3  call    _o__configure_narrow_argv_0
0x1800058e8  test    eax, eax
0x1800058ea  jz      short loc_1800058F0
0x1800058ec  xor     al, al
0x1800058ee  jmp     short loc_1800058F7
0x1800058f0  call    _initialize_narrow_environment
0x1800058f5  mov     al, 1
0x1800058f7  add     rsp, 28h
0x1800058fb  retn
```
