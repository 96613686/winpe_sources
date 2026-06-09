# __scrt_dllmain_after_initialize_c

- ea: `0x180002574`
- end: `0x1800025a8`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x1800021c8`

## callees

- `0x180002574`
- `0x180002b50`
- `0x180002ddc`
- `0x180002de8`
- `0x18000301e`
- `0x180003042`

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
0x180002574  sub     rsp, 28h
0x180002578  call    __scrt_is_ucrt_dll_in_use
0x18000257d  test    eax, eax
0x18000257f  jz      short loc_180002588
0x180002581  call    __isa_available_init
0x180002586  jmp     short loc_1800025A1
0x180002588  call    _get_startup_argv_mode
0x18000258d  mov     ecx, eax; mode
0x18000258f  call    _o__configure_narrow_argv_0
0x180002594  test    eax, eax
0x180002596  jz      short loc_18000259C
0x180002598  xor     al, al
0x18000259a  jmp     short loc_1800025A3
0x18000259c  call    _initialize_narrow_environment
0x1800025a1  mov     al, 1
0x1800025a3  add     rsp, 28h
0x1800025a7  retn
```
