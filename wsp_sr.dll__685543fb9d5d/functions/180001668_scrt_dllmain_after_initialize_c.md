# __scrt_dllmain_after_initialize_c

- ea: `0x180001668`
- end: `0x18000169c`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x1800011c8`

## callees

- `0x180001668`
- `0x180001a78`
- `0x180001d04`
- `0x180001d10`
- `0x180001da6`
- `0x180001dca`

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
0x180001668  sub     rsp, 28h
0x18000166c  call    __scrt_is_ucrt_dll_in_use
0x180001671  test    eax, eax
0x180001673  jz      short loc_18000167C
0x180001675  call    __isa_available_init
0x18000167a  jmp     short loc_180001695
0x18000167c  call    _get_startup_argv_mode
0x180001681  mov     ecx, eax; mode
0x180001683  call    _o__configure_narrow_argv_0
0x180001688  test    eax, eax
0x18000168a  jz      short loc_180001690
0x18000168c  xor     al, al
0x18000168e  jmp     short loc_180001697
0x180001690  call    _initialize_narrow_environment
0x180001695  mov     al, 1
0x180001697  add     rsp, 28h
0x18000169b  retn
```
