# __scrt_dllmain_after_initialize_c

- ea: `0x180035ef8`
- end: `0x180035f2c`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180035b38`

## callees

- `0x180035ef8`
- `0x1800367a8`
- `0x180036a34`
- `0x180036a40`
- `0x180036b06`
- `0x180036b2a`

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
0x180035ef8  sub     rsp, 28h
0x180035efc  call    __scrt_is_ucrt_dll_in_use
0x180035f01  test    eax, eax
0x180035f03  jz      short loc_180035F0C
0x180035f05  call    __isa_available_init
0x180035f0a  jmp     short loc_180035F25
0x180035f0c  call    _get_startup_argv_mode
0x180035f11  mov     ecx, eax; mode
0x180035f13  call    _o__configure_narrow_argv_0
0x180035f18  test    eax, eax
0x180035f1a  jz      short loc_180035F20
0x180035f1c  xor     al, al
0x180035f1e  jmp     short loc_180035F27
0x180035f20  call    _initialize_narrow_environment
0x180035f25  mov     al, 1
0x180035f27  add     rsp, 28h
0x180035f2b  retn
```
