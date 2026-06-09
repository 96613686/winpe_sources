# ___scrt_dllmain_after_initialize_c

- ea: `0x10003df8`
- end: `0x10003e23`
- name: `___scrt_dllmain_after_initialize_c`
- size: `43`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x100038db`

## callees

- `0x10003df8`
- `0x10004199`
- `0x100044bb`
- `0x100044c5`
- `0x1000451f`
- `0x10004537`

## pseudocode

```c
char __scrt_dllmain_after_initialize_c()
{
  _crt_argv_mode startup_argv_mode; // eax

  if ( __scrt_is_ucrt_dll_in_use() )
  {
    __isa_available_init();
  }
  else
  {
    startup_argv_mode = _get_startup_argv_mode();
    if ( _o__configure_narrow_argv(startup_argv_mode) )
      return 0;
    _o__initialize_narrow_environment();
  }
  return 1;
}

```

## disassembly

```asm
0x10003df8  call    ___scrt_is_ucrt_dll_in_use
0x10003dfd  test    eax, eax
0x10003dff  jz      short loc_10003E08
0x10003e01  call    ___isa_available_init
0x10003e06  jmp     short loc_10003E20
0x10003e08  call    __get_startup_argv_mode
0x10003e0d  push    eax; mode
0x10003e0e  call    __o__configure_narrow_argv
0x10003e13  pop     ecx
0x10003e14  test    eax, eax
0x10003e16  jz      short loc_10003E1B
0x10003e18  xor     al, al
0x10003e1a  retn
0x10003e1b  call    __o__initialize_narrow_environment
0x10003e20  mov     al, 1
0x10003e22  retn
```
