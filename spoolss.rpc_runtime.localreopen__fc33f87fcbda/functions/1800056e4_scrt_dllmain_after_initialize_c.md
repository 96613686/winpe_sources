# __scrt_dllmain_after_initialize_c

- ea: `0x1800056e4`
- end: `0x180005718`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180005368`

## callees

- `0x1800056e4`
- `0x180005c40`
- `0x180005ecc`
- `0x180005ed8`
- `0x180005f8a`
- `0x180005fae`

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
0x1800056e4  sub     rsp, 28h
0x1800056e8  call    __scrt_is_ucrt_dll_in_use
0x1800056ed  test    eax, eax
0x1800056ef  jz      short loc_1800056F8
0x1800056f1  call    __isa_available_init
0x1800056f6  jmp     short loc_180005711
0x1800056f8  call    _get_startup_argv_mode
0x1800056fd  mov     ecx, eax; mode
0x1800056ff  call    _o__configure_narrow_argv_0
0x180005704  test    eax, eax
0x180005706  jz      short loc_18000570C
0x180005708  xor     al, al
0x18000570a  jmp     short loc_180005713
0x18000570c  call    _initialize_narrow_environment
0x180005711  mov     al, 1
0x180005713  add     rsp, 28h
0x180005717  retn
```
