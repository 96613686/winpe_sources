# __scrt_dllmain_after_initialize_c

- ea: `0x180010234`
- end: `0x180010268`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: `char()`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x18000fd58`

## callees

- `0x180010234`
- `0x1800105e8`
- `0x180010874`
- `0x180010880`
- `0x1800108fe`
- `0x180010916`

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
0x180010234  sub     rsp, 28h
0x180010238  call    __scrt_is_ucrt_dll_in_use
0x18001023d  test    eax, eax
0x18001023f  jz      short loc_180010248
0x180010241  call    __isa_available_init
0x180010246  jmp     short loc_180010261
0x180010248  call    _get_startup_argv_mode
0x18001024d  mov     ecx, eax; mode
0x18001024f  call    _o__configure_narrow_argv_0
0x180010254  test    eax, eax
0x180010256  jz      short loc_18001025C
0x180010258  xor     al, al
0x18001025a  jmp     short loc_180010263
0x18001025c  call    _initialize_narrow_environment
0x180010261  mov     al, 1
0x180010263  add     rsp, 28h
0x180010267  retn
```
