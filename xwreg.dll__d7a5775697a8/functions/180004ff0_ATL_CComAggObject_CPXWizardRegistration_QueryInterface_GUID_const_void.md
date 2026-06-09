# ATL::CComAggObject<CPXWizardRegistration>::QueryInterface(_GUID const &,void * *)

- ea: `0x180004ff0`
- end: `0x18000504a`
- name: `?QueryInterface@?$CComAggObject@VCPXWizardRegistration@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `90`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180003bcc`
- `0x180004ab4`
- `0x180004ff0`
- `0x180013010`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CPXWizardRegistration>::QueryInterface(
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
                           (const struct ATL::_ATL_INTMAP_ENTRY *)&`CPXWizardRegistration::_GetEntries'::`2'::_entries,
                           v5,
                           v6);
  }
  return v3;
}

```

## disassembly

```asm
0x180004ff0  push    rbx
0x180004ff2  sub     rsp, 20h
0x180004ff6  xor     ebx, ebx
0x180004ff8  mov     r9, rcx
0x180004ffb  test    r8, r8
0x180004ffe  jnz     short loc_180005007
0x180005000  mov     eax, 80004003h
0x180005005  jmp     short loc_180005044
0x180005007  mov     rcx, rdx; struct _GUID *
0x18000500a  mov     [r8], rbx
0x18000500d  call    ?InlineIsEqualUnknown@ATL@@YAHAEBU_GUID@@@Z; ATL::InlineIsEqualUnknown(_GUID const &)
0x180005012  test    eax, eax
0x180005014  jz      short loc_18000502A
0x180005016  mov     [r8], r9
0x180005019  mov     rcx, r9
0x18000501c  mov     rax, [r9]
0x18000501f  mov     rax, [rax+8]
0x180005023  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005028  jmp     short loc_180005042
0x18000502a  lea     rcx, [r9+18h]; void *
0x18000502e  mov     r9, r8; void **
0x180005031  mov     r8, rdx; struct _GUID *
0x180005034  lea     rdx, ?_entries@?1??_GetEntries@CPXWizardRegistration@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; struct ATL::_ATL_INTMAP_ENTRY *
0x18000503b  call    ?AtlInternalQueryInterface@ATL@@YAJPEAXPEBU_ATL_INTMAP_ENTRY@1@AEBU_GUID@@PEAPEAX@Z; ATL::AtlInternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
0x180005040  mov     ebx, eax
0x180005042  mov     eax, ebx
0x180005044  add     rsp, 20h
0x180005048  pop     rbx
0x180005049  retn
```
