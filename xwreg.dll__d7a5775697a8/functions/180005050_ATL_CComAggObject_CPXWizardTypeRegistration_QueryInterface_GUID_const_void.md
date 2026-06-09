# ATL::CComAggObject<CPXWizardTypeRegistration>::QueryInterface(_GUID const &,void * *)

- ea: `0x180005050`
- end: `0x1800050aa`
- name: `?QueryInterface@?$CComAggObject@VCPXWizardTypeRegistration@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `90`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180003bcc`
- `0x180004ab4`
- `0x180005050`
- `0x180013010`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CPXWizardTypeRegistration>::QueryInterface(
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
                           (const struct ATL::_ATL_INTMAP_ENTRY *)&`CPXWizardTypeRegistration::_GetEntries'::`2'::_entries,
                           v5,
                           v6);
  }
  return v3;
}

```

## disassembly

```asm
0x180005050  push    rbx
0x180005052  sub     rsp, 20h
0x180005056  xor     ebx, ebx
0x180005058  mov     r9, rcx
0x18000505b  test    r8, r8
0x18000505e  jnz     short loc_180005067
0x180005060  mov     eax, 80004003h
0x180005065  jmp     short loc_1800050A4
0x180005067  mov     rcx, rdx; struct _GUID *
0x18000506a  mov     [r8], rbx
0x18000506d  call    ?InlineIsEqualUnknown@ATL@@YAHAEBU_GUID@@@Z; ATL::InlineIsEqualUnknown(_GUID const &)
0x180005072  test    eax, eax
0x180005074  jz      short loc_18000508A
0x180005076  mov     [r8], r9
0x180005079  mov     rcx, r9
0x18000507c  mov     rax, [r9]
0x18000507f  mov     rax, [rax+8]
0x180005083  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005088  jmp     short loc_1800050A2
0x18000508a  lea     rcx, [r9+18h]; void *
0x18000508e  mov     r9, r8; void **
0x180005091  mov     r8, rdx; struct _GUID *
0x180005094  lea     rdx, ?_entries@?1??_GetEntries@CPXWizardTypeRegistration@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; struct ATL::_ATL_INTMAP_ENTRY *
0x18000509b  call    ?AtlInternalQueryInterface@ATL@@YAJPEAXPEBU_ATL_INTMAP_ENTRY@1@AEBU_GUID@@PEAPEAX@Z; ATL::AtlInternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
0x1800050a0  mov     ebx, eax
0x1800050a2  mov     eax, ebx
0x1800050a4  add     rsp, 20h
0x1800050a8  pop     rbx
0x1800050a9  retn
```
