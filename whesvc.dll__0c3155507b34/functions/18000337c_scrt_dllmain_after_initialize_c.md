# __scrt_dllmain_after_initialize_c

- ea: `0x18000337c`
- end: `0x1800033b0`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180002fc8`

## callees

- `0x18000337c`
- `0x18000392c`
- `0x180003bb8`
- `0x180003bc4`
- `0x180003cce`
- `0x180003cf2`

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
0x18000337c  sub     rsp, 28h
0x180003380  call    __scrt_is_ucrt_dll_in_use
0x180003385  test    eax, eax
0x180003387  jz      short loc_180003390
0x180003389  call    __isa_available_init
0x18000338e  jmp     short loc_1800033A9
0x180003390  call    _get_startup_argv_mode
0x180003395  mov     ecx, eax; mode
0x180003397  call    _o__configure_narrow_argv_0
0x18000339c  test    eax, eax
0x18000339e  jz      short loc_1800033A4
0x1800033a0  xor     al, al
0x1800033a2  jmp     short loc_1800033AB
0x1800033a4  call    _initialize_narrow_environment
0x1800033a9  mov     al, 1
0x1800033ab  add     rsp, 28h
0x1800033af  retn
```
