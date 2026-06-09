# __scrt_dllmain_after_initialize_c

- ea: `0x180001998`
- end: `0x1800019cc`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180001278`

## callees

- `0x180001998`
- `0x180002248`
- `0x1800024e4`
- `0x1800024f0`
- `0x1800025c2`
- `0x1800025e6`

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
0x180001998  sub     rsp, 28h
0x18000199c  call    __scrt_is_ucrt_dll_in_use
0x1800019a1  test    eax, eax
0x1800019a3  jz      short loc_1800019AC
0x1800019a5  call    __isa_available_init
0x1800019aa  jmp     short loc_1800019C5
0x1800019ac  call    _get_startup_argv_mode
0x1800019b1  mov     ecx, eax; mode
0x1800019b3  call    _o__configure_narrow_argv_0
0x1800019b8  test    eax, eax
0x1800019ba  jz      short loc_1800019C0
0x1800019bc  xor     al, al
0x1800019be  jmp     short loc_1800019C7
0x1800019c0  call    _initialize_narrow_environment
0x1800019c5  mov     al, 1
0x1800019c7  add     rsp, 28h
0x1800019cb  retn
```
