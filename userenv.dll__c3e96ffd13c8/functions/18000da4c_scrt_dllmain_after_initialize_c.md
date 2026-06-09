# __scrt_dllmain_after_initialize_c

- ea: `0x18000da4c`
- end: `0x18000da80`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: `char()`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x18000d698`

## callees

- `0x18000da4c`
- `0x18000df8c`
- `0x18000e218`
- `0x18000e224`
- `0x18000e2ae`
- `0x18000e2d2`

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
0x18000da4c  sub     rsp, 28h
0x18000da50  call    __scrt_is_ucrt_dll_in_use
0x18000da55  test    eax, eax
0x18000da57  jz      short loc_18000DA60
0x18000da59  call    __isa_available_init
0x18000da5e  jmp     short loc_18000DA79
0x18000da60  call    _get_startup_argv_mode
0x18000da65  mov     ecx, eax; mode
0x18000da67  call    _o__configure_narrow_argv_0
0x18000da6c  test    eax, eax
0x18000da6e  jz      short loc_18000DA74
0x18000da70  xor     al, al
0x18000da72  jmp     short loc_18000DA7B
0x18000da74  call    _initialize_narrow_environment
0x18000da79  mov     al, 1
0x18000da7b  add     rsp, 28h
0x18000da7f  retn
```
