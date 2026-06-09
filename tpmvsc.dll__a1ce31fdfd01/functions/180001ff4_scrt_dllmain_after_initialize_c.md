# __scrt_dllmain_after_initialize_c

- ea: `0x180001ff4`
- end: `0x180002028`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: `char()`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180001b98`

## callees

- `0x180001ff4`
- `0x180002628`
- `0x1800028b4`
- `0x1800028c0`
- `0x1800029e6`
- `0x180002a0a`

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
0x180001ff4  sub     rsp, 28h
0x180001ff8  call    __scrt_is_ucrt_dll_in_use
0x180001ffd  test    eax, eax
0x180001fff  jz      short loc_180002008
0x180002001  call    __isa_available_init
0x180002006  jmp     short loc_180002021
0x180002008  call    _get_startup_argv_mode
0x18000200d  mov     ecx, eax; mode
0x18000200f  call    _o__configure_narrow_argv_0
0x180002014  test    eax, eax
0x180002016  jz      short loc_18000201C
0x180002018  xor     al, al
0x18000201a  jmp     short loc_180002023
0x18000201c  call    _initialize_narrow_environment
0x180002021  mov     al, 1
0x180002023  add     rsp, 28h
0x180002027  retn
```
