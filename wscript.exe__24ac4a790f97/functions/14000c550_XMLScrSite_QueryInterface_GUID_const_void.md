# XMLScrSite::QueryInterface(_GUID const &,void * *)

- ea: `0x14000c550`
- end: `0x14000c60c`
- name: `?QueryInterface@XMLScrSite@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `188`
- prototype: `__int64 __fastcall(XMLScrSite *__hidden this, const struct _GUID *, void **)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14000c620`
- `0x14000c630`

## callees

- `0x14000c550`
- `0x140018010`

## pseudocode

```c
__int64 __fastcall XMLScrSite::QueryInterface(XMLScrSite *this, const struct _GUID *a2, XMLScrSite **a3)
{
  XMLScrSite *v5; // rax
  unsigned __int64 v6; // rcx

  if ( !a3 )
    return 2147500035LL;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IUnknown.Data1 && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IUnknown.Data4
    || *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IScriptletSite.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IScriptletSite.Data4 )
  {
    v5 = this;
LABEL_15:
    *a3 = v5;
    (*(void (__fastcall **)(XMLScrSite *))(*(_QWORD *)this + 8LL))(this);
    return 0;
  }
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IScriptletSitePoll.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IScriptletSitePoll.Data4 )
  {
    v6 = (unsigned __int64)this + 8;
LABEL_14:
    v5 = (XMLScrSite *)(v6 & -(__int64)(this != 0));
    goto LABEL_15;
  }
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IScriptletSiteWSH.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IScriptletSiteWSH.Data4 )
  {
    v6 = (unsigned __int64)this + 16;
    goto LABEL_14;
  }
  *a3 = 0;
  return 2147500034LL;
}

```

## disassembly

```asm
0x14000c550  sub     rsp, 28h
0x14000c554  mov     r9, rcx
0x14000c557  test    r8, r8
0x14000c55a  jnz     short loc_14000C566
0x14000c55c  mov     eax, 80004003h
0x14000c561  jmp     loc_14000C607
0x14000c566  mov     rax, [rdx]
0x14000c569  cmp     rax, qword ptr cs:IID_IUnknown.Data1
0x14000c570  jnz     short loc_14000C57F
0x14000c572  mov     rax, [rdx+8]
0x14000c576  cmp     rax, qword ptr cs:IID_IUnknown.Data4
0x14000c57d  jz      short loc_14000C598
0x14000c57f  mov     rax, [rdx]
0x14000c582  cmp     rax, qword ptr cs:IID_IScriptletSite.Data1
0x14000c589  jnz     short loc_14000C59D
0x14000c58b  mov     rax, [rdx+8]
0x14000c58f  cmp     rax, qword ptr cs:IID_IScriptletSite.Data4
0x14000c596  jnz     short loc_14000C59D
0x14000c598  mov     rax, r9
0x14000c59b  jmp     short loc_14000C5E5
0x14000c59d  mov     rax, [rdx]
0x14000c5a0  cmp     rax, qword ptr cs:IID_IScriptletSitePoll.Data1
0x14000c5a7  jnz     short loc_14000C5BC
0x14000c5a9  mov     rax, [rdx+8]
0x14000c5ad  cmp     rax, qword ptr cs:IID_IScriptletSitePoll.Data4
0x14000c5b4  jnz     short loc_14000C5BC
0x14000c5b6  add     rcx, 8
0x14000c5ba  jmp     short loc_14000C5D9
0x14000c5bc  mov     rax, [rdx]
0x14000c5bf  cmp     rax, qword ptr cs:IID_IScriptletSiteWSH.Data1
0x14000c5c6  jnz     short loc_14000C5FB
0x14000c5c8  mov     rax, [rdx+8]
0x14000c5cc  cmp     rax, qword ptr cs:IID_IScriptletSiteWSH.Data4
0x14000c5d3  jnz     short loc_14000C5FB
0x14000c5d5  add     rcx, 10h
0x14000c5d9  mov     rax, r9
0x14000c5dc  neg     rax
0x14000c5df  sbb     rax, rax
0x14000c5e2  and     rax, rcx
0x14000c5e5  mov     [r8], rax
0x14000c5e8  mov     rcx, r9
0x14000c5eb  mov     rax, [r9]
0x14000c5ee  mov     rax, [rax+8]
0x14000c5f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c5f7  xor     eax, eax
0x14000c5f9  jmp     short loc_14000C607
0x14000c5fb  mov     qword ptr [r8], 0
0x14000c602  mov     eax, 80004002h
0x14000c607  add     rsp, 28h
0x14000c60b  retn
```
