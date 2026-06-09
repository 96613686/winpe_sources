# __scrt_dllmain_after_initialize_c

- ea: `0x180034574`
- end: `0x1800345a8`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x1800341f8`

## callees

- `0x180034574`
- `0x180034ab0`
- `0x180034d3c`
- `0x180034d48`
- `0x180034de6`
- `0x180034e0a`

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
0x180034574  sub     rsp, 28h
0x180034578  call    __scrt_is_ucrt_dll_in_use
0x18003457d  test    eax, eax
0x18003457f  jz      short loc_180034588
0x180034581  call    __isa_available_init
0x180034586  jmp     short loc_1800345A1
0x180034588  call    _get_startup_argv_mode
0x18003458d  mov     ecx, eax; mode
0x18003458f  call    _o__configure_narrow_argv_0
0x180034594  test    eax, eax
0x180034596  jz      short loc_18003459C
0x180034598  xor     al, al
0x18003459a  jmp     short loc_1800345A3
0x18003459c  call    _initialize_narrow_environment
0x1800345a1  mov     al, 1
0x1800345a3  add     rsp, 28h
0x1800345a7  retn
```
