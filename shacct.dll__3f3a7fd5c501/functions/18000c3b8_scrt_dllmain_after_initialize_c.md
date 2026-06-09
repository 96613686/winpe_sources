# __scrt_dllmain_after_initialize_c

- ea: `0x18000c3b8`
- end: `0x18000c3ec`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x18000bf28`

## callees

- `0x18000bda0`
- `0x18000c3b8`
- `0x18000c7ec`
- `0x18000ca78`
- `0x18000caee`
- `0x18000cb12`

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
    v2 = CDPA_Base<_SID,CTContainer_PolicyUnOwned<_SID>>::_StandardDestroyCB(v1, v0);
    if ( o__configure_narrow_argv_0(v2) )
      return 0;
    initialize_narrow_environment();
  }
  return 1;
}

```

## disassembly

```asm
0x18000c3b8  sub     rsp, 28h
0x18000c3bc  call    __scrt_is_ucrt_dll_in_use
0x18000c3c1  test    eax, eax
0x18000c3c3  jz      short loc_18000C3CC
0x18000c3c5  call    __isa_available_init
0x18000c3ca  jmp     short loc_18000C3E5
0x18000c3cc  call    ?_StandardDestroyCB@?$CDPA_Base@U_SID@@V?$CTContainer_PolicyUnOwned@U_SID@@@@@@CAHPEAU_SID@@PEAX@Z; CDPA_Base<_SID,CTContainer_PolicyUnOwned<_SID>>::_StandardDestroyCB(_SID *,void *)
0x18000c3d1  mov     ecx, eax; mode
0x18000c3d3  call    _o__configure_narrow_argv_0
0x18000c3d8  test    eax, eax
0x18000c3da  jz      short loc_18000C3E0
0x18000c3dc  xor     al, al
0x18000c3de  jmp     short loc_18000C3E7
0x18000c3e0  call    _initialize_narrow_environment
0x18000c3e5  mov     al, 1
0x18000c3e7  add     rsp, 28h
0x18000c3eb  retn
```
