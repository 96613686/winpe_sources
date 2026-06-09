# __scrt_dllmain_after_initialize_c

- ea: `0x1800364c8`
- end: `0x1800364fc`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180036108`

## callees

- `0x1800364c8`
- `0x180036d78`
- `0x180037004`
- `0x180037010`
- `0x1800370d6`
- `0x1800370fa`

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
0x1800364c8  sub     rsp, 28h
0x1800364cc  call    __scrt_is_ucrt_dll_in_use
0x1800364d1  test    eax, eax
0x1800364d3  jz      short loc_1800364DC
0x1800364d5  call    __isa_available_init
0x1800364da  jmp     short loc_1800364F5
0x1800364dc  call    _get_startup_argv_mode
0x1800364e1  mov     ecx, eax; mode
0x1800364e3  call    _o__configure_narrow_argv_0
0x1800364e8  test    eax, eax
0x1800364ea  jz      short loc_1800364F0
0x1800364ec  xor     al, al
0x1800364ee  jmp     short loc_1800364F7
0x1800364f0  call    _initialize_narrow_environment
0x1800364f5  mov     al, 1
0x1800364f7  add     rsp, 28h
0x1800364fb  retn
```
