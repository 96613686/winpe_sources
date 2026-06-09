# ATL::CComAggObject<CPXWizardFactoryRegistration>::QueryInterface(_GUID const &,void * *)

- ea: `0x180004f90`
- end: `0x180004fea`
- name: `?QueryInterface@?$CComAggObject@VCPXWizardFactoryRegistration@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `90`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180003bcc`
- `0x180004ab4`
- `0x180004f90`
- `0x180013010`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CPXWizardFactoryRegistration>::QueryInterface(
        __int64 a1,
        const struct _GUID *a2,
        _QWORD *a3)
{
  unsigned int v3; // ebx
  const struct _GUID *v5; // rdx
  void **v6; // r8
  __int64 v7; // r9

  v3 = 0;
  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  if ( (unsigned int)ATL::InlineIsEqualUnknown(a2) )
  {
    *v6 = (void *)v7;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 8LL))(v7);
  }
  else
  {
    return (unsigned int)ATL::AtlInternalQueryInterface(
                           (void *)(v7 + 24),
                           (const struct ATL::_ATL_INTMAP_ENTRY *)&`CPXWizardFactoryRegistration::_GetEntries'::`2'::_entries,
                           v5,
                           v6);
  }
  return v3;
}

```

## disassembly

```asm
0x180004f90  push    rbx
0x180004f92  sub     rsp, 20h
0x180004f96  xor     ebx, ebx
0x180004f98  mov     r9, rcx
0x180004f9b  test    r8, r8
0x180004f9e  jnz     short loc_180004FA7
0x180004fa0  mov     eax, 80004003h
0x180004fa5  jmp     short loc_180004FE4
0x180004fa7  mov     rcx, rdx; struct _GUID *
0x180004faa  mov     [r8], rbx
0x180004fad  call    ?InlineIsEqualUnknown@ATL@@YAHAEBU_GUID@@@Z; ATL::InlineIsEqualUnknown(_GUID const &)
0x180004fb2  test    eax, eax
0x180004fb4  jz      short loc_180004FCA
0x180004fb6  mov     [r8], r9
0x180004fb9  mov     rcx, r9
0x180004fbc  mov     rax, [r9]
0x180004fbf  mov     rax, [rax+8]
0x180004fc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004fc8  jmp     short loc_180004FE2
0x180004fca  lea     rcx, [r9+18h]; void *
0x180004fce  mov     r9, r8; void **
0x180004fd1  mov     r8, rdx; struct _GUID *
0x180004fd4  lea     rdx, ?_entries@?1??_GetEntries@CPXWizardFactoryRegistration@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; struct ATL::_ATL_INTMAP_ENTRY *
0x180004fdb  call    ?AtlInternalQueryInterface@ATL@@YAJPEAXPEBU_ATL_INTMAP_ENTRY@1@AEBU_GUID@@PEAPEAX@Z; ATL::AtlInternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
0x180004fe0  mov     ebx, eax
0x180004fe2  mov     eax, ebx
0x180004fe4  add     rsp, 20h
0x180004fe8  pop     rbx
0x180004fe9  retn
```
