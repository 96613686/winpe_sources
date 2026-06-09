# CTypeLibWrapper::Create(ICreateTypeLib *,ITypeInfo *,CTypeLibWrapper * *)

- ea: `0x18006726c`
- end: `0x180067543`
- name: `?Create@CTypeLibWrapper@@SAJPEAUICreateTypeLib@@PEAUITypeInfo@@PEAPEAV1@@Z`
- size: `727`
- prototype: `__int64 __fastcall(struct ICreateTypeLib *, struct ITypeInfo *, struct CTypeLibWrapper **)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18006754c`

## callees

- `0x180046884`
- `0x180066b64`
- `0x180066c94`
- `0x180066cbc`
- `0x180066dd8`
- `0x18006726c`
- `0x18007a010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18006743f`
- `OLEAUT32!__imp_SysFreeString` at `0x18006743f`
- `OLEAUT32!__imp_VariantCopy` at `0x1800673df`
- `OLEAUT32!__imp_VariantCopy` at `0x1800673df`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180067350`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180067350`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800674fb`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800674fb`

## pseudocode

```c
__int64 __fastcall CTypeLibWrapper::Create(
        struct ICreateTypeLib *a1,
        struct ITypeInfo *a2,
        struct CTypeLibWrapper **a3)
{
  struct ITypeInfoVtbl *lpVtbl; // rax
  CHashTable *v5; // rsi
  HRESULT (__stdcall *GetTypeAttr)(ITypeInfo *, TYPEATTR **); // rax
  SAFEARRAY *v7; // r15
  HRESULT v8; // ebx
  ULONG v9; // r14d
  unsigned int i; // r12d
  SAFEARRAY *v11; // rax
  int v12; // eax
  __int64 v13; // r12
  unsigned int j; // r13d
  CTypeLibWrapper *v15; // rax
  CTypeLibWrapper *v16; // rax
  CTypeLibWrapper *v17; // rbx
  struct CTypeLibWrapper **v18; // rax
  unsigned int v19; // edx
  SAFEARRAYBOUND rgsabound; // [rsp+40h] [rbp-28h] BYREF
  BSTR bstrString; // [rsp+48h] [rbp-20h] BYREF
  struct CHashTable *v23; // [rsp+50h] [rbp-18h] BYREF
  VARIANTARG *pvData; // [rsp+58h] [rbp-10h]
  const VARIANTARG **v26; // [rsp+B8h] [rbp+50h] BYREF
  struct CTypeLibWrapper **v27; // [rsp+C0h] [rbp+58h]
  __int64 v28; // [rsp+C8h] [rbp+60h] BYREF

  v27 = a3;
  lpVtbl = a2->lpVtbl;
  v5 = 0;
  rgsabound = 0;
  bstrString = 0;
  v28 = 0;
  GetTypeAttr = lpVtbl->GetTypeAttr;
  v7 = 0;
  v23 = 0;
  v26 = 0;
  *a3 = 0;
  v8 = ((__int64 (__fastcall *)(struct ITypeInfo *, __int64 *))GetTypeAttr)(a2, &v28);
  if ( v8 >= 0 )
  {
    v9 = 0;
    for ( i = 0; i < *(unsigned __int16 *)(v28 + 50); ++i )
    {
      v8 = ((__int64 (__fastcall *)(struct ITypeInfo *, _QWORD, const VARIANTARG ***))a2->lpVtbl->GetVarDesc)(
             a2,
             i,
             &v26);
      if ( v8 < 0 )
        goto LABEL_25;
      if ( *((_DWORD *)v26 + 15) == 2 )
        ++v9;
      ((void (__fastcall *)(struct ITypeInfo *))a2->lpVtbl->ReleaseVarDesc)(a2);
      v26 = 0;
    }
    if ( !v9 )
    {
      v8 = 1;
      goto LABEL_25;
    }
    rgsabound.cElements = v9;
    rgsabound.lLbound = 0;
    v11 = SafeArrayCreate(0xCu, 1u, &rgsabound);
    v7 = v11;
    if ( !v11 )
      goto LABEL_24;
    pvData = (VARIANTARG *)v11->pvData;
    v12 = CHashTable::Create(v9, &v23);
    v5 = v23;
    v8 = v12;
    if ( v12 < 0 )
      goto LABEL_25;
    v13 = 0;
    for ( j = 0; j < *(unsigned __int16 *)(v28 + 50); ++j )
    {
      v8 = ((__int64 (__fastcall *)(struct ITypeInfo *, _QWORD, const VARIANTARG ***))a2->lpVtbl->GetVarDesc)(
             a2,
             j,
             &v26);
      if ( v8 < 0 )
        goto LABEL_25;
      if ( *((_DWORD *)v26 + 15) == 2 )
      {
        v8 = VariantCopy(&pvData[v13], v26[2]);
        if ( v8 < 0 )
          goto LABEL_25;
        v8 = ((__int64 (__fastcall *)(struct ITypeInfo *, _QWORD, BSTR *, _QWORD, _QWORD, _QWORD))a2->lpVtbl->GetDocumentation)(
               a2,
               *(unsigned int *)v26,
               &bstrString,
               0,
               0,
               0);
        if ( v8 < 0 )
          goto LABEL_25;
        v8 = CHashTable::Add(v5, bstrString);
        SysFreeString(bstrString);
        if ( v8 < 0 )
          goto LABEL_25;
        v13 = (unsigned int)(v13 + 1);
        if ( (_DWORD)v13 == v9 )
          break;
      }
      ((void (__fastcall *)(struct ITypeInfo *))a2->lpVtbl->ReleaseVarDesc)(a2);
      v26 = 0;
    }
    v15 = (CTypeLibWrapper *)operator new(0x60u);
    if ( v15 && (v16 = CTypeLibWrapper::CTypeLibWrapper(v15), (v17 = v16) != 0) )
    {
      *((_DWORD *)v16 + 3) = v9;
      *((_QWORD *)v16 + 3) = v7;
      v7 = 0;
      *((_QWORD *)v16 + 2) = v5;
      v5 = 0;
      ((void (__fastcall *)(struct ICreateTypeLib *))a1->lpVtbl->AddRef)(a1);
      v18 = v27;
      *((_QWORD *)v17 + 4) = a1;
      *v18 = v17;
      v8 = 0;
    }
    else
    {
LABEL_24:
      v8 = -2147024882;
    }
  }
LABEL_25:
  v19 = v28;
  if ( v28 )
    ((void (__fastcall *)(struct ITypeInfo *))a2->lpVtbl->ReleaseTypeAttr)(a2);
  if ( v7 )
    SafeArrayDestroy(v7);
  if ( v5 )
    CHashTable::`scalar deleting destructor'(v5, v19);
  if ( v26 )
    ((void (__fastcall *)(struct ITypeInfo *))a2->lpVtbl->ReleaseVarDesc)(a2);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18006726c  mov     [rsp-40h+arg_10], r8
0x180067271  mov     [rsp-40h+arg_0], rcx
0x180067276  push    rbp
0x180067277  push    rbx
0x180067278  push    rsi
0x180067279  push    rdi
0x18006727a  push    r12
0x18006727c  push    r13
0x18006727e  push    r14
0x180067280  push    r15
0x180067282  mov     rbp, rsp
0x180067285  sub     rsp, 68h
0x180067289  mov     rax, [rdx]
0x18006728c  mov     rdi, rdx
0x18006728f  xor     esi, esi
0x180067291  mov     qword ptr [rbp+rgsabound.cElements], 0
0x180067299  lea     rdx, [rbp+arg_18]
0x18006729d  mov     [rbp+bstrString], 0
0x1800672a5  mov     rcx, rdi
0x1800672a8  mov     [rbp+arg_18], 0
0x1800672b0  mov     rax, [rax+18h]
0x1800672b4  xor     r15d, r15d
0x1800672b7  mov     [rbp+var_18], rsi
0x1800672bb  mov     [rbp+arg_8], rsi
0x1800672bf  mov     [r8], rsi
0x1800672c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800672c7  mov     ebx, eax
0x1800672c9  test    eax, eax
0x1800672cb  js      loc_1800674D8
0x1800672d1  xor     r14d, r14d
0x1800672d4  lea     r13d, [r15+1]
0x1800672d8  xor     r12d, r12d
0x1800672db  mov     rax, [rbp+arg_18]
0x1800672df  movzx   ecx, word ptr [rax+32h]
0x1800672e3  cmp     r12d, ecx
0x1800672e6  jnb     short loc_180067330
0x1800672e8  mov     rax, [rdi]
0x1800672eb  lea     r8, [rbp+arg_8]
0x1800672ef  mov     edx, r12d
0x1800672f2  mov     rcx, rdi
0x1800672f5  mov     rax, [rax+30h]
0x1800672f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800672fe  mov     ebx, eax
0x180067300  test    eax, eax
0x180067302  js      loc_1800674D8
0x180067308  mov     rdx, [rbp+arg_8]
0x18006730c  cmp     dword ptr [rdx+3Ch], 2
0x180067310  jnz     short loc_180067315
0x180067312  add     r14d, r13d
0x180067315  mov     rax, [rdi]
0x180067318  mov     rcx, rdi
0x18006731b  mov     rax, [rax+0A8h]
0x180067322  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067327  add     r12d, r13d
0x18006732a  mov     [rbp+arg_8], rsi
0x18006732e  jmp     short loc_1800672DB
0x180067330  test    r14d, r14d
0x180067333  jnz     short loc_18006733D
0x180067335  mov     ebx, r13d
0x180067338  jmp     loc_1800674D8
0x18006733d  mov     ecx, 0Ch; vt
0x180067342  mov     [rbp+rgsabound.cElements], r14d
0x180067346  lea     r8, [rbp+rgsabound]; rgsabound
0x18006734a  mov     [rbp+rgsabound.lLbound], esi
0x18006734d  mov     edx, r13d; cDims
0x180067350  call    cs:__imp_SafeArrayCreate
0x180067357  nop     dword ptr [rax+rax+00h]
0x18006735c  mov     r15, rax
0x18006735f  test    rax, rax
0x180067362  jz      loc_1800674D3
0x180067368  mov     rax, [rax+10h]
0x18006736c  lea     rdx, [rbp+var_18]; struct CHashTable **
0x180067370  mov     ecx, r14d; unsigned int
0x180067373  mov     [rbp+var_10], rax
0x180067377  call    ?Create@CHashTable@@SAJIPEAPEAV1@@Z; CHashTable::Create(uint,CHashTable * *)
0x18006737c  mov     rsi, [rbp+var_18]
0x180067380  mov     ebx, eax
0x180067382  test    eax, eax
0x180067384  js      loc_1800674D8
0x18006738a  xor     r12d, r12d
0x18006738d  xor     r13d, r13d
0x180067390  mov     rax, [rbp+arg_18]
0x180067394  movzx   ecx, word ptr [rax+32h]
0x180067398  cmp     r13d, ecx
0x18006739b  jnb     loc_180067481
0x1800673a1  mov     rax, [rdi]
0x1800673a4  lea     r8, [rbp+arg_8]
0x1800673a8  mov     edx, r13d
0x1800673ab  mov     rcx, rdi
0x1800673ae  mov     rax, [rax+30h]
0x1800673b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800673b7  mov     ebx, eax
0x1800673b9  test    eax, eax
0x1800673bb  js      loc_1800674D8
0x1800673c1  mov     rdx, [rbp+arg_8]
0x1800673c5  cmp     dword ptr [rdx+3Ch], 2
0x1800673c9  jnz     loc_18006745F
0x1800673cf  mov     rax, [rbp+var_10]
0x1800673d3  lea     rcx, [r12+r12*2]
0x1800673d7  mov     rdx, [rdx+10h]; pvargSrc
0x1800673db  lea     rcx, [rax+rcx*8]; pvargDest
0x1800673df  call    cs:__imp_VariantCopy
0x1800673e6  nop     dword ptr [rax+rax+00h]
0x1800673eb  mov     ebx, eax
0x1800673ed  test    eax, eax
0x1800673ef  js      loc_1800674D8
0x1800673f5  mov     rax, [rdi]
0x1800673f8  lea     r8, [rbp+bstrString]
0x1800673fc  mov     rdx, [rbp+arg_8]
0x180067400  xor     r9d, r9d
0x180067403  mov     [rsp+68h+var_40], 0
0x18006740c  mov     rcx, rdi
0x18006740f  mov     [rsp+68h+var_48], 0
0x180067418  mov     rax, [rax+60h]
0x18006741c  mov     edx, [rdx]
0x18006741e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067423  mov     ebx, eax
0x180067425  test    eax, eax
0x180067427  js      loc_1800674D8
0x18006742d  mov     rdx, [rbp+bstrString]; unsigned __int16 *
0x180067431  mov     rcx, rsi; this
0x180067434  call    ?Add@CHashTable@@QEAAJPEAG@Z; CHashTable::Add(ushort *)
0x180067439  mov     rcx, [rbp+bstrString]; bstrString
0x18006743d  mov     ebx, eax
0x18006743f  call    cs:__imp_SysFreeString
0x180067446  nop     dword ptr [rax+rax+00h]
0x18006744b  test    ebx, ebx
0x18006744d  js      loc_1800674D8
0x180067453  inc     r12d
0x180067456  cmp     r12d, r14d
0x180067459  jz      short loc_180067481
0x18006745b  mov     rdx, [rbp+arg_8]
0x18006745f  mov     rax, [rdi]
0x180067462  mov     rcx, rdi
0x180067465  mov     rax, [rax+0A8h]
0x18006746c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067471  inc     r13d
0x180067474  mov     [rbp+arg_8], 0
0x18006747c  jmp     loc_180067390
0x180067481  mov     ecx, 60h ; '`'; Size
0x180067486  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006748b  test    rax, rax
0x18006748e  jz      short loc_1800674D3
0x180067490  mov     rcx, rax; this
0x180067493  call    ??0CTypeLibWrapper@@AEAA@XZ; CTypeLibWrapper::CTypeLibWrapper(void)
0x180067498  mov     rbx, rax
0x18006749b  test    rax, rax
0x18006749e  jz      short loc_1800674D3
0x1800674a0  mov     [rax+0Ch], r14d
0x1800674a4  mov     r14, [rbp+arg_0]
0x1800674a8  mov     [rax+18h], r15
0x1800674ac  xor     r15d, r15d
0x1800674af  mov     [rax+10h], rsi
0x1800674b3  xor     esi, esi
0x1800674b5  mov     rcx, [r14]
0x1800674b8  mov     rax, [rcx+8]
0x1800674bc  mov     rcx, r14
0x1800674bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800674c4  mov     rax, [rbp+arg_10]
0x1800674c8  mov     [rbx+20h], r14
0x1800674cc  mov     [rax], rbx
0x1800674cf  xor     ebx, ebx
0x1800674d1  jmp     short loc_1800674D8
0x1800674d3  mov     ebx, 8007000Eh
0x1800674d8  mov     rdx, [rbp+arg_18]
0x1800674dc  test    rdx, rdx
0x1800674df  jz      short loc_1800674F3
0x1800674e1  mov     rax, [rdi]
0x1800674e4  mov     rcx, rdi
0x1800674e7  mov     rax, [rax+98h]
0x1800674ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800674f3  test    r15, r15
0x1800674f6  jz      short loc_180067507
0x1800674f8  mov     rcx, r15; psa
0x1800674fb  call    cs:__imp_SafeArrayDestroy
0x180067502  nop     dword ptr [rax+rax+00h]
0x180067507  test    rsi, rsi
0x18006750a  jz      short loc_180067514
0x18006750c  mov     rcx, rsi; this
0x18006750f  call    ??_GCHashTable@@QEAAPEAXI@Z; CHashTable::`scalar deleting destructor'(uint)
0x180067514  mov     rdx, [rbp+arg_8]
0x180067518  test    rdx, rdx
0x18006751b  jz      short loc_18006752F
0x18006751d  mov     rax, [rdi]
0x180067520  mov     rcx, rdi
0x180067523  mov     rax, [rax+0A8h]
0x18006752a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006752f  mov     eax, ebx
0x180067531  add     rsp, 68h
0x180067535  pop     r15
0x180067537  pop     r14
0x180067539  pop     r13
0x18006753b  pop     r12
0x18006753d  pop     rdi
0x18006753e  pop     rsi
0x18006753f  pop     rbx
0x180067540  pop     rbp
0x180067541  retn
```
