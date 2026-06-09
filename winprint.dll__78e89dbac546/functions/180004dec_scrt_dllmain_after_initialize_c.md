# __scrt_dllmain_after_initialize_c

- ea: `0x180004dec`
- end: `0x180004e20`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180004968`

## callees

- `0x1800023f0`
- `0x180004dec`
- `0x1800051c0`
- `0x18000544c`
- `0x1800054be`
- `0x1800054d6`

## pseudocode

```c
char _scrt_dllmain_after_initialize_c()
{
  DWORD v0; // edx
  HINSTANCE v1; // rcx
  void *v2; // r8
  BOOL startup_argv_mode; // eax

  if ( (unsigned int)_scrt_is_ucrt_dll_in_use() )
  {
    _isa_available_init();
  }
  else
  {
    startup_argv_mode = get_startup_argv_mode(v1, v0, v2);
    if ( o__configure_narrow_argv_0((_crt_argv_mode)startup_argv_mode) )
      return 0;
    initialize_narrow_environment();
  }
  return 1;
}

```

## disassembly

```asm
0x180004dec  sub     rsp, 28h
0x180004df0  call    __scrt_is_ucrt_dll_in_use
0x180004df5  test    eax, eax
0x180004df7  jz      short loc_180004E00
0x180004df9  call    __isa_available_init
0x180004dfe  jmp     short loc_180004E19
0x180004e00  call    _get_startup_argv_mode
0x180004e05  mov     ecx, eax; mode
0x180004e07  call    _o__configure_narrow_argv_0
0x180004e0c  test    eax, eax
0x180004e0e  jz      short loc_180004E14
0x180004e10  xor     al, al
0x180004e12  jmp     short loc_180004E1B
0x180004e14  call    _initialize_narrow_environment
0x180004e19  mov     al, 1
0x180004e1b  add     rsp, 28h
0x180004e1f  retn
```
