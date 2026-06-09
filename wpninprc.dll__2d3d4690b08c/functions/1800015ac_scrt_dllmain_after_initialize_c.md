# __scrt_dllmain_after_initialize_c

- ea: `0x1800015ac`
- end: `0x1800015e0`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x1800011f8`

## callees

- `0x1800015ac`
- `0x180001b0c`
- `0x180001d98`
- `0x180001da4`
- `0x18000200e`
- `0x180002032`

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
0x1800015ac  sub     rsp, 28h
0x1800015b0  call    __scrt_is_ucrt_dll_in_use
0x1800015b5  test    eax, eax
0x1800015b7  jz      short loc_1800015C0
0x1800015b9  call    __isa_available_init
0x1800015be  jmp     short loc_1800015D9
0x1800015c0  call    _get_startup_argv_mode
0x1800015c5  mov     ecx, eax; mode
0x1800015c7  call    _o__configure_narrow_argv_0
0x1800015cc  test    eax, eax
0x1800015ce  jz      short loc_1800015D4
0x1800015d0  xor     al, al
0x1800015d2  jmp     short loc_1800015DB
0x1800015d4  call    _initialize_narrow_environment
0x1800015d9  mov     al, 1
0x1800015db  add     rsp, 28h
0x1800015df  retn
```
