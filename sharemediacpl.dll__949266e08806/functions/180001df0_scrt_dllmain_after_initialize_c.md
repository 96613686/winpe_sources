# __scrt_dllmain_after_initialize_c

- ea: `0x180001df0`
- end: `0x180001e24`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180001a48`

## callees

- `0x180001df0`
- `0x1800025a8`
- `0x180002834`
- `0x18000289a`
- `0x1800028be`
- `0x180013000`

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
0x180001df0  sub     rsp, 28h
0x180001df4  call    __scrt_is_ucrt_dll_in_use
0x180001df9  test    eax, eax
0x180001dfb  jz      short loc_180001E04
0x180001dfd  call    __isa_available_init
0x180001e02  jmp     short loc_180001E1D
0x180001e04  call    _get_startup_argv_mode
0x180001e09  mov     ecx, eax; mode
0x180001e0b  call    _o__configure_narrow_argv_0
0x180001e10  test    eax, eax
0x180001e12  jz      short loc_180001E18
0x180001e14  xor     al, al
0x180001e16  jmp     short loc_180001E1F
0x180001e18  call    _initialize_narrow_environment
0x180001e1d  mov     al, 1
0x180001e1f  add     rsp, 28h
0x180001e23  retn
```
