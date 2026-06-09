# __scrt_dllmain_after_initialize_c

- ea: `0x18000fd44`
- end: `0x18000fd78`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x1800101d8`

## callees

- `0x18000fbfa`
- `0x18000fc36`
- `0x18000fd44`
- `0x1800106a4`
- `0x180010940`
- `0x18001094c`

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
0x18000fd44  sub     rsp, 28h
0x18000fd48  call    __scrt_is_ucrt_dll_in_use
0x18000fd4d  test    eax, eax
0x18000fd4f  jz      short loc_18000FD58
0x18000fd51  call    __isa_available_init
0x18000fd56  jmp     short loc_18000FD71
0x18000fd58  call    _get_startup_argv_mode
0x18000fd5d  mov     ecx, eax; mode
0x18000fd5f  call    _o__configure_narrow_argv_0
0x18000fd64  test    eax, eax
0x18000fd66  jz      short loc_18000FD6C
0x18000fd68  xor     al, al
0x18000fd6a  jmp     short loc_18000FD73
0x18000fd6c  call    _initialize_narrow_environment
0x18000fd71  mov     al, 1
0x18000fd73  add     rsp, 28h
0x18000fd77  retn
```
