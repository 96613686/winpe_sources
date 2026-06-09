# __scrt_dllmain_after_initialize_c

- ea: `0x18000288c`
- end: `0x1800028c0`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: `char()`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x1800024c8`

## callees

- `0x18000288c`
- `0x180002e48`
- `0x1800030d4`
- `0x1800030e0`
- `0x18000330a`
- `0x18000332e`

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
0x18000288c  sub     rsp, 28h
0x180002890  call    __scrt_is_ucrt_dll_in_use
0x180002895  test    eax, eax
0x180002897  jz      short loc_1800028A0
0x180002899  call    __isa_available_init
0x18000289e  jmp     short loc_1800028B9
0x1800028a0  call    _get_startup_argv_mode
0x1800028a5  mov     ecx, eax; mode
0x1800028a7  call    _o__configure_narrow_argv_0
0x1800028ac  test    eax, eax
0x1800028ae  jz      short loc_1800028B4
0x1800028b0  xor     al, al
0x1800028b2  jmp     short loc_1800028BB
0x1800028b4  call    _initialize_narrow_environment
0x1800028b9  mov     al, 1
0x1800028bb  add     rsp, 28h
0x1800028bf  retn
```
