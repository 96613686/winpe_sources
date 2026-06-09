# __scrt_dllmain_after_initialize_c

- ea: `0x100426d44`
- end: `0x100426d78`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x100426608`

## callees

- `0x100404060`
- `0x1004263cc`
- `0x100426d44`
- `0x1004272e0`
- `0x10042a604`
- `0x10042a9f8`

## pseudocode

```c
char _scrt_dllmain_after_initialize_c()
{
  CharacterSource *v0; // rcx
  _crt_argv_mode CharacterSize; // eax

  if ( (unsigned int)_scrt_is_ucrt_dll_in_use() )
  {
    _isa_available_init();
  }
  else
  {
    CharacterSize = (unsigned int)CharacterSource::GetCharacterSize(v0);
    if ( configure_narrow_argv(CharacterSize) )
      return 0;
    initialize_narrow_environment();
  }
  return 1;
}

```

## disassembly

```asm
0x100426d44  sub     rsp, 28h
0x100426d48  call    __scrt_is_ucrt_dll_in_use
0x100426d4d  test    eax, eax
0x100426d4f  jz      short loc_100426D58
0x100426d51  call    __isa_available_init
0x100426d56  jmp     short loc_100426D71
0x100426d58  call    ?GetCharacterSize@CharacterSource@@UEAAHXZ; CharacterSource::GetCharacterSize(void)
0x100426d5d  mov     ecx, eax; mode
0x100426d5f  call    _configure_narrow_argv
0x100426d64  test    eax, eax
0x100426d66  jz      short loc_100426D6C
0x100426d68  xor     al, al
0x100426d6a  jmp     short loc_100426D73
0x100426d6c  call    _initialize_narrow_environment
0x100426d71  mov     al, 1
0x100426d73  add     rsp, 28h
0x100426d77  retn
```
