# __scrt_dllmain_after_initialize_c

- ea: `0x1800015e8`
- end: `0x18000161c`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: `char()`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180001158`

## callees

- `0x1800015e8`
- `0x1800019bc`
- `0x180001c48`
- `0x180001c54`
- `0x180001cba`
- `0x180001cd2`

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
0x1800015e8  sub     rsp, 28h
0x1800015ec  call    __scrt_is_ucrt_dll_in_use
0x1800015f1  test    eax, eax
0x1800015f3  jz      short loc_1800015FC
0x1800015f5  call    __isa_available_init
0x1800015fa  jmp     short loc_180001615
0x1800015fc  call    _get_startup_argv_mode
0x180001601  mov     ecx, eax; mode
0x180001603  call    _o__configure_narrow_argv_0
0x180001608  test    eax, eax
0x18000160a  jz      short loc_180001610
0x18000160c  xor     al, al
0x18000160e  jmp     short loc_180001617
0x180001610  call    _initialize_narrow_environment
0x180001615  mov     al, 1
0x180001617  add     rsp, 28h
0x18000161b  retn
```
