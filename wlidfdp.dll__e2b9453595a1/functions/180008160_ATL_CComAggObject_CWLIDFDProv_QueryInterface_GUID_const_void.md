# ATL::CComAggObject<CWLIDFDProv>::QueryInterface(_GUID const &,void * *)

- ea: `0x180008160`
- end: `0x1800081ba`
- name: `?QueryInterface@?$CComAggObject@VCWLIDFDProv@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `90`
- prototype: `__int64 __fastcall(__int64, const struct _GUID *, _QWORD *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180005c60`
- `0x180007200`
- `0x180008160`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CWLIDFDProv>::QueryInterface(__int64 a1, const struct _GUID *a2, _QWORD *a3)
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
                           (const struct ATL::_ATL_INTMAP_ENTRY *)&`CWLIDFDProv::_GetEntries'::`2'::_entries,
                           v5,
                           v6);
  }
  return v3;
}

```

## disassembly

```asm
0x180008160  push    rbx
0x180008162  sub     rsp, 20h
0x180008166  xor     ebx, ebx
0x180008168  mov     r9, rcx
0x18000816b  test    r8, r8
0x18000816e  jnz     short loc_180008177
0x180008170  mov     eax, 80004003h
0x180008175  jmp     short loc_1800081B4
0x180008177  mov     rcx, rdx; struct _GUID *
0x18000817a  mov     [r8], rbx
0x18000817d  call    ?InlineIsEqualUnknown@ATL@@YAHAEBU_GUID@@@Z; ATL::InlineIsEqualUnknown(_GUID const &)
0x180008182  test    eax, eax
0x180008184  jz      short loc_18000819A
0x180008186  mov     [r8], r9
0x180008189  mov     rcx, r9
0x18000818c  mov     rax, [r9]
0x18000818f  mov     rax, [rax+8]
0x180008193  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008198  jmp     short loc_1800081B2
0x18000819a  lea     rcx, [r9+18h]; void *
0x18000819e  mov     r9, r8; void **
0x1800081a1  mov     r8, rdx; struct _GUID *
0x1800081a4  lea     rdx, ?_entries@?1??_GetEntries@CWLIDFDProv@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; struct ATL::_ATL_INTMAP_ENTRY *
0x1800081ab  call    ?AtlInternalQueryInterface@ATL@@YAJPEAXPEBU_ATL_INTMAP_ENTRY@1@AEBU_GUID@@PEAPEAX@Z; ATL::AtlInternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
0x1800081b0  mov     ebx, eax
0x1800081b2  mov     eax, ebx
0x1800081b4  add     rsp, 20h
0x1800081b8  pop     rbx
0x1800081b9  retn
```
