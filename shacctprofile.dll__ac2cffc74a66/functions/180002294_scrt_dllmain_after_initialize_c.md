# __scrt_dllmain_after_initialize_c

- ea: `0x180002294`
- end: `0x1800022c8`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: `char()`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180001f18`

## callees

- `0x180002294`
- `0x180002800`
- `0x180002a8c`
- `0x180002afe`
- `0x180002b22`
- `0x180007650`

## pseudocode

```c
char _scrt_dllmain_after_initialize_c()
{
  void *v0; // rdx
  void *v1; // rcx
  _crt_argv_mode v2; // eax

  if ( (unsigned int)_scrt_is_ucrt_dll_in_use() )
  {
    _isa_available_init();
  }
  else
  {
    v2 = CDPA_Base<CAce,CTContainer_PolicyUnOwned<CAce>>::_StandardDestroyCB(v1, v0);
    if ( o__configure_narrow_argv_0(v2) )
      return 0;
    initialize_narrow_environment();
  }
  return 1;
}

```

## disassembly

```asm
0x180002294  sub     rsp, 28h
0x180002298  call    __scrt_is_ucrt_dll_in_use
0x18000229d  test    eax, eax
0x18000229f  jz      short loc_1800022A8
0x1800022a1  call    __isa_available_init
0x1800022a6  jmp     short loc_1800022C1
0x1800022a8  call    ?_StandardDestroyCB@?$CDPA_Base@VCAce@@V?$CTContainer_PolicyUnOwned@VCAce@@@@@@CAHPEAVCAce@@PEAX@Z; CDPA_Base<CAce,CTContainer_PolicyUnOwned<CAce>>::_StandardDestroyCB(CAce *,void *)
0x1800022ad  mov     ecx, eax; mode
0x1800022af  call    _o__configure_narrow_argv_0
0x1800022b4  test    eax, eax
0x1800022b6  jz      short loc_1800022BC
0x1800022b8  xor     al, al
0x1800022ba  jmp     short loc_1800022C3
0x1800022bc  call    _initialize_narrow_environment
0x1800022c1  mov     al, 1
0x1800022c3  add     rsp, 28h
0x1800022c7  retn
```
