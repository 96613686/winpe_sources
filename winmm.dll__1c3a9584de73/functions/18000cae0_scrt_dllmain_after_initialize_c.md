# __scrt_dllmain_after_initialize_c

- ea: `0x18000cae0`
- end: `0x18000cb14`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x18000c678`

## callees

- `0x18000cae0`
- `0x18000d0b8`
- `0x18000d344`
- `0x18000d3c2`
- `0x18000d3e6`
- `0x180019850`

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
0x18000cae0  sub     rsp, 28h
0x18000cae4  call    __scrt_is_ucrt_dll_in_use
0x18000cae9  test    eax, eax
0x18000caeb  jz      short loc_18000CAF4
0x18000caed  call    __isa_available_init
0x18000caf2  jmp     short loc_18000CB0D
0x18000caf4  call    _get_startup_argv_mode
0x18000caf9  mov     ecx, eax; mode
0x18000cafb  call    _o__configure_narrow_argv_0
0x18000cb00  test    eax, eax
0x18000cb02  jz      short loc_18000CB08
0x18000cb04  xor     al, al
0x18000cb06  jmp     short loc_18000CB0F
0x18000cb08  call    _initialize_narrow_environment
0x18000cb0d  mov     al, 1
0x18000cb0f  add     rsp, 28h
0x18000cb13  retn
```
