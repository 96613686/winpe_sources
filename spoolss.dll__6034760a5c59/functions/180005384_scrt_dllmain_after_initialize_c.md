# __scrt_dllmain_after_initialize_c

- ea: `0x180005384`
- end: `0x1800053b8`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180005008`

## callees

- `0x180005384`
- `0x1800058e0`
- `0x180005b6c`
- `0x180005b78`
- `0x180005c1a`
- `0x180005c3e`

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
0x180005384  sub     rsp, 28h
0x180005388  call    __scrt_is_ucrt_dll_in_use
0x18000538d  test    eax, eax
0x18000538f  jz      short loc_180005398
0x180005391  call    __isa_available_init
0x180005396  jmp     short loc_1800053B1
0x180005398  call    _get_startup_argv_mode
0x18000539d  mov     ecx, eax; mode
0x18000539f  call    _o__configure_narrow_argv_0
0x1800053a4  test    eax, eax
0x1800053a6  jz      short loc_1800053AC
0x1800053a8  xor     al, al
0x1800053aa  jmp     short loc_1800053B3
0x1800053ac  call    _initialize_narrow_environment
0x1800053b1  mov     al, 1
0x1800053b3  add     rsp, 28h
0x1800053b7  retn
```
