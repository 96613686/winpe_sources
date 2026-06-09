# CTypeLibWrapper::Create(ICreateTypeLib *,ITypeInfo *,CTypeLibWrapper * *)

- ea: `0x180065470`
- end: `0x18006572e`
- name: `?Create@CTypeLibWrapper@@SAJPEAUICreateTypeLib@@PEAUITypeInfo@@PEAPEAV1@@Z`
- size: `702`
- prototype: `__int64 __fastcall(struct ICreateTypeLib *, struct ITypeInfo *, struct CTypeLibWrapper **)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180065734`

## callees

- `0x180045490`
- `0x180064db4`
- `0x180064ecc`
- `0x180064ef4`
- `0x18006500c`
- `0x180065470`
- `0x180077010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180065637`
- `OLEAUT32!__imp_SysFreeString` at `0x180065637`
- `OLEAUT32!__imp_VariantCopy` at `0x1800655dd`
- `OLEAUT32!__imp_VariantCopy` at `0x1800655dd`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180065554`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180065554`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800656ed`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800656ed`

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
0x180065470  mov     [rsp-40h+arg_10], r8
0x180065475  mov     [rsp-40h+arg_0], rcx
0x18006547a  push    rbp
0x18006547b  push    rbx
0x18006547c  push    rsi
0x18006547d  push    rdi
0x18006547e  push    r12
0x180065480  push    r13
0x180065482  push    r14
0x180065484  push    r15
0x180065486  mov     rbp, rsp
0x180065489  sub     rsp, 68h
0x18006548d  mov     rax, [rdx]
0x180065490  mov     rdi, rdx
0x180065493  xor     esi, esi
0x180065495  mov     qword ptr [rbp+rgsabound.cElements], 0
0x18006549d  lea     rdx, [rbp+arg_18]
0x1800654a1  mov     [rbp+bstrString], 0
0x1800654a9  mov     rcx, rdi
0x1800654ac  mov     [rbp+arg_18], 0
0x1800654b4  mov     rax, [rax+18h]
0x1800654b8  xor     r15d, r15d
0x1800654bb  mov     [rbp+var_18], rsi
0x1800654bf  mov     [rbp+arg_8], rsi
0x1800654c3  mov     [r8], rsi
0x1800654c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800654cb  mov     ebx, eax
0x1800654cd  test    eax, eax
0x1800654cf  js      loc_1800656CA
0x1800654d5  xor     r14d, r14d
0x1800654d8  lea     r13d, [r15+1]
0x1800654dc  xor     r12d, r12d
0x1800654df  mov     rax, [rbp+arg_18]
0x1800654e3  movzx   ecx, word ptr [rax+32h]
0x1800654e7  cmp     r12d, ecx
0x1800654ea  jnb     short loc_180065534
0x1800654ec  mov     rax, [rdi]
0x1800654ef  lea     r8, [rbp+arg_8]
0x1800654f3  mov     edx, r12d
0x1800654f6  mov     rcx, rdi
0x1800654f9  mov     rax, [rax+30h]
0x1800654fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065502  mov     ebx, eax
0x180065504  test    eax, eax
0x180065506  js      loc_1800656CA
0x18006550c  mov     rdx, [rbp+arg_8]
0x180065510  cmp     dword ptr [rdx+3Ch], 2
0x180065514  jnz     short loc_180065519
0x180065516  add     r14d, r13d
0x180065519  mov     rax, [rdi]
0x18006551c  mov     rcx, rdi
0x18006551f  mov     rax, [rax+0A8h]
0x180065526  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006552b  add     r12d, r13d
0x18006552e  mov     [rbp+arg_8], rsi
0x180065532  jmp     short loc_1800654DF
0x180065534  test    r14d, r14d
0x180065537  jnz     short loc_180065541
0x180065539  mov     ebx, r13d
0x18006553c  jmp     loc_1800656CA
0x180065541  mov     ecx, 0Ch; vt
0x180065546  mov     [rbp+rgsabound.cElements], r14d
0x18006554a  lea     r8, [rbp+rgsabound]; rgsabound
0x18006554e  mov     [rbp+rgsabound.lLbound], esi
0x180065551  mov     edx, r13d; cDims
0x180065554  call    cs:__imp_SafeArrayCreate
0x18006555a  mov     r15, rax
0x18006555d  test    rax, rax
0x180065560  jz      loc_1800656C5
0x180065566  mov     rax, [rax+10h]
0x18006556a  lea     rdx, [rbp+var_18]; struct CHashTable **
0x18006556e  mov     ecx, r14d; unsigned int
0x180065571  mov     [rbp+var_10], rax
0x180065575  call    ?Create@CHashTable@@SAJIPEAPEAV1@@Z; CHashTable::Create(uint,CHashTable * *)
0x18006557a  mov     rsi, [rbp+var_18]
0x18006557e  mov     ebx, eax
0x180065580  test    eax, eax
0x180065582  js      loc_1800656CA
0x180065588  xor     r12d, r12d
0x18006558b  xor     r13d, r13d
0x18006558e  mov     rax, [rbp+arg_18]
0x180065592  movzx   ecx, word ptr [rax+32h]
0x180065596  cmp     r13d, ecx
0x180065599  jnb     loc_180065673
0x18006559f  mov     rax, [rdi]
0x1800655a2  lea     r8, [rbp+arg_8]
0x1800655a6  mov     edx, r13d
0x1800655a9  mov     rcx, rdi
0x1800655ac  mov     rax, [rax+30h]
0x1800655b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800655b5  mov     ebx, eax
0x1800655b7  test    eax, eax
0x1800655b9  js      loc_1800656CA
0x1800655bf  mov     rdx, [rbp+arg_8]
0x1800655c3  cmp     dword ptr [rdx+3Ch], 2
0x1800655c7  jnz     loc_180065651
0x1800655cd  mov     rax, [rbp+var_10]
0x1800655d1  lea     rcx, [r12+r12*2]
0x1800655d5  mov     rdx, [rdx+10h]; pvargSrc
0x1800655d9  lea     rcx, [rax+rcx*8]; pvargDest
0x1800655dd  call    cs:__imp_VariantCopy
0x1800655e3  mov     ebx, eax
0x1800655e5  test    eax, eax
0x1800655e7  js      loc_1800656CA
0x1800655ed  mov     rax, [rdi]
0x1800655f0  lea     r8, [rbp+bstrString]
0x1800655f4  mov     rdx, [rbp+arg_8]
0x1800655f8  xor     r9d, r9d
0x1800655fb  mov     [rsp+68h+var_40], 0
0x180065604  mov     rcx, rdi
0x180065607  mov     [rsp+68h+var_48], 0
0x180065610  mov     rax, [rax+60h]
0x180065614  mov     edx, [rdx]
0x180065616  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006561b  mov     ebx, eax
0x18006561d  test    eax, eax
0x18006561f  js      loc_1800656CA
0x180065625  mov     rdx, [rbp+bstrString]; unsigned __int16 *
0x180065629  mov     rcx, rsi; this
0x18006562c  call    ?Add@CHashTable@@QEAAJPEAG@Z; CHashTable::Add(ushort *)
0x180065631  mov     rcx, [rbp+bstrString]; bstrString
0x180065635  mov     ebx, eax
0x180065637  call    cs:__imp_SysFreeString
0x18006563d  test    ebx, ebx
0x18006563f  js      loc_1800656CA
0x180065645  inc     r12d
0x180065648  cmp     r12d, r14d
0x18006564b  jz      short loc_180065673
0x18006564d  mov     rdx, [rbp+arg_8]
0x180065651  mov     rax, [rdi]
0x180065654  mov     rcx, rdi
0x180065657  mov     rax, [rax+0A8h]
0x18006565e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065663  inc     r13d
0x180065666  mov     [rbp+arg_8], 0
0x18006566e  jmp     loc_18006558E
0x180065673  mov     ecx, 60h ; '`'; Size
0x180065678  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006567d  test    rax, rax
0x180065680  jz      short loc_1800656C5
0x180065682  mov     rcx, rax; this
0x180065685  call    ??0CTypeLibWrapper@@AEAA@XZ; CTypeLibWrapper::CTypeLibWrapper(void)
0x18006568a  mov     rbx, rax
0x18006568d  test    rax, rax
0x180065690  jz      short loc_1800656C5
0x180065692  mov     [rax+0Ch], r14d
0x180065696  mov     r14, [rbp+arg_0]
0x18006569a  mov     [rax+18h], r15
0x18006569e  xor     r15d, r15d
0x1800656a1  mov     [rax+10h], rsi
0x1800656a5  xor     esi, esi
0x1800656a7  mov     rcx, [r14]
0x1800656aa  mov     rax, [rcx+8]
0x1800656ae  mov     rcx, r14
0x1800656b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800656b6  mov     rax, [rbp+arg_10]
0x1800656ba  mov     [rbx+20h], r14
0x1800656be  mov     [rax], rbx
0x1800656c1  xor     ebx, ebx
0x1800656c3  jmp     short loc_1800656CA
0x1800656c5  mov     ebx, 8007000Eh
0x1800656ca  mov     rdx, [rbp+arg_18]
0x1800656ce  test    rdx, rdx
0x1800656d1  jz      short loc_1800656E5
0x1800656d3  mov     rax, [rdi]
0x1800656d6  mov     rcx, rdi
0x1800656d9  mov     rax, [rax+98h]
0x1800656e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800656e5  test    r15, r15
0x1800656e8  jz      short loc_1800656F3
0x1800656ea  mov     rcx, r15; psa
0x1800656ed  call    cs:__imp_SafeArrayDestroy
0x1800656f3  test    rsi, rsi
0x1800656f6  jz      short loc_180065700
0x1800656f8  mov     rcx, rsi; this
0x1800656fb  call    ??_GCHashTable@@QEAAPEAXI@Z; CHashTable::`scalar deleting destructor'(uint)
0x180065700  mov     rdx, [rbp+arg_8]
0x180065704  test    rdx, rdx
0x180065707  jz      short loc_18006571B
0x180065709  mov     rax, [rdi]
0x18006570c  mov     rcx, rdi
0x18006570f  mov     rax, [rax+0A8h]
0x180065716  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006571b  mov     eax, ebx
0x18006571d  add     rsp, 68h
0x180065721  pop     r15
0x180065723  pop     r14
0x180065725  pop     r13
0x180065727  pop     r12
0x180065729  pop     rdi
0x18006572a  pop     rsi
0x18006572b  pop     rbx
0x18006572c  pop     rbp
0x18006572d  retn
```
