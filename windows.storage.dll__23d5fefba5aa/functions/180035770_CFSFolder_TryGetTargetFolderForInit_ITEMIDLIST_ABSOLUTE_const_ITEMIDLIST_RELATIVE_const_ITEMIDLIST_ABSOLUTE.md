# CFSFolder::TryGetTargetFolderForInit(_ITEMIDLIST_ABSOLUTE const *,_ITEMIDLIST_RELATIVE const *,_ITEMIDLIST_ABSOLUTE * *)

- ea: `0x180035770`
- end: `0x180035d26`
- name: `?TryGetTargetFolderForInit@CFSFolder@@IEAAJPEBU_ITEMIDLIST_ABSOLUTE@@PEFBU_ITEMIDLIST_RELATIVE@@PEAPEAU2@@Z`
- size: `1462`
- prototype: `__int64 __fastcall(CFSFolder *__hidden this, const struct _ITEMIDLIST_ABSOLUTE *, const struct _ITEMIDLIST_RELATIVE *, struct _ITEMIDLIST_ABSOLUTE **)`
- caller_count: `1`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callers

- `0x180524a68`

## callees

- `0x180035770`
- `0x1800376a0`
- `0x180038f50`
- `0x180045230`
- `0x18005fa70`
- `0x18006cd90`
- `0x18006dd50`
- `0x18008c740`
- `0x1800ab340`
- `0x1803b1f60`
- `0x1803b2ac0`
- `0x1803b2ea5`
- `0x1803b69c5`
- `0x18067d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180035826`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180035922`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180035826`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180035922`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x18003584a`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x180035945`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x18003584a`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x180035945`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800358bb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800359bd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035ae8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035b36`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035b93`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035bd8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035c18`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035c57`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035c92`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035cb0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800358bb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800359bd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035ae8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035b36`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035b93`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035bd8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035c18`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035c57`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035c92`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035cb0`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CFSFolder::TryGetTargetFolderForInit(
        CFSFolder *this,
        const struct _ITEMIDLIST_ABSOLUTE *a2,
        IMalloc *a3,
        struct _ITEMIDLIST_ABSOLUTE **a4)
{
  CFSFolder *v4; // r14
  void *v5; // rbx
  _QWORD *v6; // r13
  __int64 v7; // rax
  SIZE_T v8; // rdi
  int v9; // r15d
  int v10; // esi
  const void *v11; // r14
  unsigned __int16 *v12; // rdx
  unsigned int v13; // r8d
  __int64 v14; // rax
  size_t v15; // rsi
  size_t v16; // r15
  void *v17; // rcx
  __int64 v18; // rax
  void *v19; // r14
  unsigned __int16 *v20; // rdx
  __int64 v21; // rcx
  void *v22; // rbx
  size_t v23; // rsi
  unsigned int v24; // edi
  void *v25; // rcx
  const void *v27; // r14
  LPMALLOC v28; // r13
  unsigned __int16 *v29; // rdx
  int v30; // r8d
  __int64 v31; // rcx
  __int64 v32; // r12
  LPMALLOC v33; // rdx
  __int64 lpVtbl_low; // rcx
  ITEMIDLIST *v35; // rax
  LPITEMIDLIST v36; // rsi
  void *v37; // rcx
  void *v38; // rcx
  char v39; // r14
  IMalloc *v40; // rbx
  const struct _ITEMIDLIST_RELATIVE *v41; // r13
  const ITEMIDLIST *v42; // rax
  __int64 v43; // rcx
  LPMALLOC v44; // rcx
  int v45; // eax
  unsigned int v46; // ebx
  LPMALLOC v47; // rcx
  LPMALLOC v48; // rdi
  LPMALLOC v49; // rcx
  LPMALLOC v50; // rcx
  void *v51; // rcx
  struct _ITEMIDLIST_ABSOLUTE *TokenHandle; // [rsp+30h] [rbp-48h] BYREF
  char v54; // [rsp+38h] [rbp-40h]
  CFSFolder *v55; // [rsp+40h] [rbp-38h]
  void *Src; // [rsp+48h] [rbp-30h]
  LPMALLOC ppMalloc; // [rsp+50h] [rbp-28h] BYREF
  LPMALLOC v58; // [rsp+58h] [rbp-20h] BYREF
  LPVOID pv; // [rsp+60h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+40h]

  v58 = a3;
  Src = a2;
  v4 = this;
  v55 = this;
  *a4 = 0;
  pv = 0;
  v54 = 1;
  v5 = 0;
  TokenHandle = 0;
  v6 = (_QWORD *)((char *)this + 496);
  v7 = *((_QWORD *)this + 62) - *(_QWORD *)&GUID_NULL.Data1;
  if ( !v7 )
    v7 = *((_QWORD *)this + 63) - *(_QWORD *)GUID_NULL.Data4;
  v8 = 2;
  v9 = -2147024882;
  if ( v7 )
  {
    v10 = SHGetKnownFolderIDList_Internal((struct _GUID *)this + 31, 0x1000u, 0, &TokenHandle);
    if ( !v54 )
      goto LABEL_17;
    v5 = TokenHandle;
  }
  else
  {
    v10 = -2147467259;
    v11 = (const void *)*((_QWORD *)this + 55);
    if ( v11 )
    {
      v12 = (unsigned __int16 *)*((_QWORD *)this + 55);
      v13 = 2;
      do
      {
        v14 = *v12;
        if ( !(_WORD)v14 )
          break;
        v13 += v14;
        v12 = (unsigned __int16 *)((char *)v12 + v14);
      }
      while ( v12 );
      v15 = v13;
      v5 = CoTaskMemAlloc(v13);
      if ( v5 )
      {
        v16 = 0;
        ppMalloc = 0;
        if ( CoGetMalloc(1u, &ppMalloc) >= 0 )
        {
          v16 = ((__int64 (__fastcall *)(LPMALLOC, void *))ppMalloc->lpVtbl->GetSize)(ppMalloc, v5);
          ((void (__fastcall *)(LPMALLOC))ppMalloc->lpVtbl->Release)(ppMalloc);
        }
        memset_0(v5, 0, v16);
        memcpy_0(v5, v11, v15);
        v9 = -2147024882;
      }
      v10 = 0;
      if ( !v5 )
        v10 = -2147024882;
    }
    v4 = v55;
  }
  v17 = pv;
  pv = v5;
  if ( v17 )
    CoTaskMemFree(v17);
LABEL_17:
  if ( v10 < 0 )
  {
    v18 = *v6 - *(_QWORD *)&GUID_NULL.Data1;
    if ( *v6 == *(_QWORD *)&GUID_NULL.Data1 )
      v18 = v6[1] - *(_QWORD *)GUID_NULL.Data4;
    if ( !v18 && !*((_QWORD *)v4 + 55) )
    {
      v19 = Src;
      if ( !Src )
      {
        *a4 = 0;
        v24 = -2147024809;
        goto LABEL_54;
      }
      v20 = (unsigned __int16 *)Src;
      do
      {
        v21 = *v20;
        if ( !(_WORD)v21 )
          break;
        v8 = (unsigned int)(v21 + v8);
        v20 = (unsigned __int16 *)((char *)v20 + v21);
      }
      while ( v20 );
      v22 = CoTaskMemAlloc(v8);
      if ( v22 )
      {
        v23 = 0;
        v58 = 0;
        if ( CoGetMalloc(1u, &v58) >= 0 )
        {
          v23 = ((__int64 (__fastcall *)(LPMALLOC, void *))v58->lpVtbl->GetSize)(v58, v22);
          ((void (__fastcall *)(LPMALLOC))v58->lpVtbl->Release)(v58);
        }
        memset_0(v22, 0, v23);
        memcpy_0(v22, v19, v8);
      }
      *a4 = (struct _ITEMIDLIST_ABSOLUTE *)v22;
      if ( !v22 )
      {
        v24 = -2147024882;
LABEL_54:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x257F,
          (unsigned int)"onecoreuap\\shell\\windows.storage\\filefldr.cpp",
          (const char *)v24,
          (int)a4);
        v38 = pv;
        pv = 0;
        if ( v38 )
          CoTaskMemFree(v38);
        return v24;
      }
    }
    goto LABEL_32;
  }
  if ( !*((_QWORD *)v4 + 77) )
  {
    v27 = pv;
    v28 = v58;
    if ( pv )
    {
      if ( v58 )
      {
        v29 = (unsigned __int16 *)pv;
        v30 = 2;
        do
        {
          v31 = *v29;
          if ( !(_WORD)v31 )
            break;
          v30 += v31;
          v29 = (unsigned __int16 *)((char *)v29 + v31);
        }
        while ( v29 );
        v32 = (unsigned int)(v30 - 2);
        v33 = v58;
        do
        {
          lpVtbl_low = LOWORD(v33->lpVtbl);
          if ( !(_WORD)lpVtbl_low )
            break;
          LODWORD(v8) = lpVtbl_low + v8;
          v33 = (LPMALLOC)((char *)v33 + lpVtbl_low);
        }
        while ( v33 );
        v35 = (ITEMIDLIST *)WINRT_IMPL_CoTaskMemAlloc((unsigned int)(v8 + v32));
        v36 = v35;
        if ( v35 )
        {
          memset_0(v35, 0, (unsigned int)(v8 + v32));
          memcpy_0(v36, v27, (unsigned int)v32);
          memcpy_0((char *)v36 + v32, v28, (unsigned int)v8);
        }
      }
      else
      {
        v36 = ILClone((LPCITEMIDLIST)pv);
      }
    }
    else
    {
      if ( !v58 )
      {
        *a4 = 0;
        goto LABEL_49;
      }
      v36 = ILClone((LPCITEMIDLIST)v58);
    }
    *a4 = (struct _ITEMIDLIST_ABSOLUTE *)v36;
    if ( !v36 )
    {
LABEL_49:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2577,
        (unsigned int)"onecoreuap\\shell\\windows.storage\\filefldr.cpp",
        (const char *)0x8007000ELL,
        (int)a4);
LABEL_50:
      v37 = pv;
      pv = 0;
      if ( v37 )
        CoTaskMemFree(v37);
      return (unsigned int)v9;
    }
LABEL_32:
    v25 = pv;
    pv = 0;
    if ( v25 )
      CoTaskMemFree(v25);
    return 0;
  }
  ppMalloc = 0;
  v39 = 1;
  v54 = 1;
  v40 = 0;
  TokenHandle = 0;
  v41 = (const struct _ITEMIDLIST_RELATIVE *)v58;
  v42 = (const ITEMIDLIST *)CFSFolder::_IsValidID((CFSFolder *)v17, (const struct _ITEMIDLIST_RELATIVE *)v58);
  v58 = (LPMALLOC)ILCloneFirst(v42);
  if ( v58 )
  {
    v9 = CFSFolder::_CopyHiddenData(v43, v41, 2, &v58);
    if ( v9 >= 0 )
    {
      if ( (unsigned int)ILIsChild(v41) )
      {
        v40 = v58;
        v48 = 0;
      }
      else
      {
        v48 = v58;
        v9 = SHILCombine(
               (const struct _ITEMIDLIST_ABSOLUTE *)v58,
               (const struct _ITEMIDLIST_RELATIVE *)((char *)v41 + *(unsigned __int16 *)v41),
               &TokenHandle);
        v39 = v54;
        v40 = (IMalloc *)TokenHandle;
      }
      CoTaskMemFree(v48);
    }
  }
  if ( v39 )
  {
    v44 = ppMalloc;
    ppMalloc = v40;
    if ( v44 )
      CoTaskMemFree(v44);
  }
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2572,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\filefldr.cpp",
      (const char *)(unsigned int)v9,
      (int)a4);
    v49 = ppMalloc;
    ppMalloc = 0;
    if ( v49 )
      CoTaskMemFree(v49);
    goto LABEL_50;
  }
  v45 = SHILCombine((const struct _ITEMIDLIST_ABSOLUTE *)pv, (const struct _ITEMIDLIST_RELATIVE *)ppMalloc, a4);
  v46 = v45;
  if ( v45 >= 0 )
  {
    v47 = ppMalloc;
    ppMalloc = 0;
    if ( v47 )
      CoTaskMemFree(v47);
    goto LABEL_32;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x2573,
    (unsigned int)"onecoreuap\\shell\\windows.storage\\filefldr.cpp",
    (const char *)(unsigned int)v45,
    (int)a4);
  v50 = ppMalloc;
  ppMalloc = 0;
  if ( v50 )
    CoTaskMemFree(v50);
  v51 = pv;
  pv = 0;
  if ( v51 )
    CoTaskMemFree(v51);
  return v46;
}

```

## disassembly

```asm
0x180035770  push    rbp
0x180035772  push    rbx
0x180035773  push    rsi
0x180035774  push    rdi
0x180035775  push    r12
0x180035777  push    r13
0x180035779  push    r14
0x18003577b  push    r15
0x18003577d  mov     rbp, rsp
0x180035780  sub     rsp, 78h
0x180035784  mov     rax, cs:__security_cookie
0x18003578b  xor     rax, rsp
0x18003578e  mov     [rbp+var_10], rax
0x180035792  mov     [rbp+var_58], r9
0x180035796  mov     [rbp+var_20], r8
0x18003579a  mov     [rbp+Src], rdx
0x18003579e  mov     r14, rcx
0x1800357a1  mov     [rbp+var_38], rcx
0x1800357a5  xor     ecx, ecx
0x1800357a7  mov     [r9], rcx
0x1800357aa  mov     [rbp+pv], rcx
0x1800357ae  lea     r12, [rbp+pv]
0x1800357b2  mov     [rbp+var_50], r12
0x1800357b6  mov     [rbp+var_40], 1
0x1800357ba  mov     ebx, ecx
0x1800357bc  mov     [rbp+TokenHandle], rcx
0x1800357c0  lea     r13, [r14+1F0h]
0x1800357c7  mov     rax, [r13+0]
0x1800357cb  sub     rax, qword ptr cs:GUID_NULL.Data1
0x1800357d2  jnz     short loc_1800357DF
0x1800357d4  mov     rax, [r13+8]
0x1800357d8  sub     rax, qword ptr cs:GUID_NULL.Data4
0x1800357df  mov     edi, 2
0x1800357e4  mov     r15d, 8007000Eh
0x1800357ea  test    rax, rax
0x1800357ed  jnz     loc_1800359E9
0x1800357f3  mov     esi, 80004005h
0x1800357f8  mov     r14, [r14+1B8h]
0x1800357ff  test    r14, r14
0x180035802  jz      loc_1800358AA
0x180035808  mov     rdx, r14
0x18003580b  mov     r8d, edi
0x18003580e  xchg    ax, ax
0x180035810  movzx   eax, word ptr [rdx]
0x180035813  test    ax, ax
0x180035816  jz      short loc_180035820
0x180035818  add     r8d, eax
0x18003581b  add     rdx, rax
0x18003581e  jnz     short loc_180035810
0x180035820  mov     esi, r8d
0x180035823  mov     ecx, r8d; cb
0x180035826  call    cs:__imp_CoTaskMemAlloc
0x18003582d  nop     dword ptr [rax+rax+00h]
0x180035832  mov     rbx, rax
0x180035835  test    rax, rax
0x180035838  jz      short loc_1800358A1
0x18003583a  xor     r15d, r15d
0x18003583d  mov     [rbp+ppMalloc], r15
0x180035841  lea     rdx, [rbp+ppMalloc]; ppMalloc
0x180035845  mov     ecx, 1; dwMemContext
0x18003584a  call    cs:__imp_CoGetMalloc
0x180035851  nop     dword ptr [rax+rax+00h]
0x180035856  test    eax, eax
0x180035858  js      short loc_180035880
0x18003585a  mov     rcx, [rbp+ppMalloc]
0x18003585e  mov     rax, [rcx]
0x180035861  mov     rdx, rbx
0x180035864  mov     rax, [rax+30h]
0x180035868  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003586d  mov     r15, rax
0x180035870  mov     rcx, [rbp+ppMalloc]
0x180035874  mov     rdx, [rcx]
0x180035877  mov     rax, [rdx+10h]
0x18003587b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035880  mov     r8, r15; Size
0x180035883  xor     edx, edx; Val
0x180035885  mov     rcx, rbx; void *
0x180035888  call    memset_0
0x18003588d  mov     r8, rsi; Size
0x180035890  mov     rdx, r14; Src
0x180035893  mov     rcx, rbx; void *
0x180035896  call    memcpy_0
0x18003589b  mov     r15d, 8007000Eh
0x1800358a1  xor     esi, esi
0x1800358a3  test    rbx, rbx
0x1800358a6  cmovz   esi, r15d
0x1800358aa  mov     r14, [rbp+var_38]
0x1800358ae  mov     rcx, [r12]; pv
0x1800358b2  mov     [r12], rbx
0x1800358b6  test    rcx, rcx
0x1800358b9  jz      short loc_1800358C7
0x1800358bb  call    cs:__imp_CoTaskMemFree
0x1800358c2  nop     dword ptr [rax+rax+00h]
0x1800358c7  test    esi, esi
0x1800358c9  jns     loc_180035A15
0x1800358cf  mov     rax, [r13+0]
0x1800358d3  sub     rax, qword ptr cs:GUID_NULL.Data1
0x1800358da  jnz     short loc_1800358E7
0x1800358dc  mov     rax, [r13+8]
0x1800358e0  sub     rax, qword ptr cs:GUID_NULL.Data4
0x1800358e7  test    rax, rax
0x1800358ea  jnz     loc_1800359AC
0x1800358f0  cmp     [r14+1B8h], rax
0x1800358f7  jnz     loc_1800359AC
0x1800358fd  mov     r14, [rbp+Src]
0x180035901  test    r14, r14
0x180035904  jz      loc_180035AFC
0x18003590a  mov     rdx, r14
0x18003590d  nop     dword ptr [rax]
0x180035910  movzx   ecx, word ptr [rdx]
0x180035913  test    cx, cx
0x180035916  jz      short loc_18003591F
0x180035918  add     edi, ecx
0x18003591a  add     rdx, rcx
0x18003591d  jnz     short loc_180035910
0x18003591f  mov     rcx, rdi; cb
0x180035922  call    cs:__imp_CoTaskMemAlloc
0x180035929  nop     dword ptr [rax+rax+00h]
0x18003592e  mov     rbx, rax
0x180035931  test    rax, rax
0x180035934  jz      short loc_180035996
0x180035936  xor     esi, esi
0x180035938  mov     [rbp+var_20], rsi
0x18003593c  lea     rdx, [rbp+var_20]; ppMalloc
0x180035940  mov     ecx, 1; dwMemContext
0x180035945  call    cs:__imp_CoGetMalloc
0x18003594c  nop     dword ptr [rax+rax+00h]
0x180035951  test    eax, eax
0x180035953  js      short loc_18003597B
0x180035955  mov     rcx, [rbp+var_20]
0x180035959  mov     rdx, [rcx]
0x18003595c  mov     rax, [rdx+30h]
0x180035960  mov     rdx, rbx
0x180035963  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035968  mov     rsi, rax
0x18003596b  mov     rcx, [rbp+var_20]
0x18003596f  mov     r9, [rcx]
0x180035972  mov     rax, [r9+10h]
0x180035976  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003597b  mov     r8, rsi; Size
0x18003597e  xor     edx, edx; Val
0x180035980  mov     rcx, rbx; void *
0x180035983  call    memset_0
0x180035988  mov     r8, rdi; Size
0x18003598b  mov     rdx, r14; Src
0x18003598e  mov     rcx, rbx; void *
0x180035991  call    memcpy_0
0x180035996  mov     rax, [rbp+var_58]
0x18003599a  mov     [rax], rbx
0x18003599d  xor     edi, edi
0x18003599f  test    rbx, rbx
0x1800359a2  cmovz   edi, r15d
0x1800359a6  jz      loc_180035B0C
0x1800359ac  mov     rcx, [rbp+pv]; pv
0x1800359b0  mov     [rbp+pv], 0
0x1800359b8  test    rcx, rcx
0x1800359bb  jz      short loc_1800359C9
0x1800359bd  call    cs:__imp_CoTaskMemFree
0x1800359c4  nop     dword ptr [rax+rax+00h]
0x1800359c9  xor     eax, eax
0x1800359cb  mov     rcx, [rbp+var_10]
0x1800359cf  xor     rcx, rsp; StackCookie
0x1800359d2  call    __security_check_cookie
0x1800359d7  add     rsp, 78h
0x1800359db  pop     r15
0x1800359dd  pop     r14
0x1800359df  pop     r13
0x1800359e1  pop     r12
0x1800359e3  pop     rdi
0x1800359e4  pop     rsi
0x1800359e5  pop     rbx
0x1800359e6  pop     rbp
0x1800359e7  retn
0x1800359e9  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800359ed  xor     r8d, r8d; void *
0x1800359f0  mov     edx, 1000h; unsigned int
0x1800359f5  mov     rcx, r13; struct _GUID *
0x1800359f8  call    SHGetKnownFolderIDList_Internal
0x1800359fd  mov     esi, eax
0x1800359ff  cmp     [rbp+var_40], bl
0x180035a02  jz      loc_1800358C7
0x180035a08  mov     rbx, [rbp+TokenHandle]
0x180035a0c  mov     r12, [rbp+var_50]
0x180035a10  jmp     loc_1800358AE
0x180035a15  cmp     qword ptr [r14+268h], 0
0x180035a1d  jnz     loc_180035B49
0x180035a23  mov     r14, [rbp+pv]
0x180035a27  mov     r13, [rbp+var_20]
0x180035a2b  test    r14, r14
0x180035a2e  jz      loc_180035CC3
0x180035a34  test    r13, r13
0x180035a37  jz      loc_180035D15
0x180035a3d  mov     rdx, r14
0x180035a40  mov     r8d, edi
0x180035a43  movzx   ecx, word ptr [rdx]
0x180035a46  test    cx, cx
0x180035a49  jz      short loc_180035A53
0x180035a4b  add     r8d, ecx
0x180035a4e  add     rdx, rcx
0x180035a51  jnz     short loc_180035A43
0x180035a53  lea     r12d, [r8-2]
0x180035a57  mov     rdx, r13
0x180035a5a  nop     word ptr [rax+rax+00h]
0x180035a60  movzx   ecx, word ptr [rdx]
0x180035a63  test    cx, cx
0x180035a66  jz      short loc_180035A6F
0x180035a68  add     edi, ecx
0x180035a6a  add     rdx, rcx
0x180035a6d  jnz     short loc_180035A60
0x180035a6f  lea     eax, [rdi+r12]
0x180035a73  mov     ebx, eax
0x180035a75  mov     ecx, eax; cb
0x180035a77  call    WINRT_IMPL_CoTaskMemAlloc
0x180035a7c  mov     rsi, rax
0x180035a7f  test    rax, rax
0x180035a82  jz      short loc_180035AAE
0x180035a84  mov     r8d, ebx; Size
0x180035a87  xor     edx, edx; Val
0x180035a89  mov     rcx, rax; void *
0x180035a8c  call    memset_0
0x180035a91  mov     r8d, r12d; Size
0x180035a94  mov     rdx, r14; Src
0x180035a97  mov     rcx, rsi; void *
0x180035a9a  call    memcpy_0
0x180035a9f  mov     r8d, edi; Size
0x180035aa2  lea     rcx, [r12+rsi]; void *
0x180035aa6  mov     rdx, r13; Src
0x180035aa9  call    memcpy_0
0x180035aae  mov     rax, [rbp+var_58]
0x180035ab2  mov     [rax], rsi
0x180035ab5  test    rsi, rsi
0x180035ab8  jnz     loc_1800359AC
0x180035abe  mov     rcx, [rbp+40h]; this
0x180035ac2  mov     r9d, r15d; char *
0x180035ac5  lea     r8, aOnecoreuapShel_18; "onecoreuap\\shell\\windows.storage\\fil"...
0x180035acc  mov     edx, 2577h; void *
0x180035ad1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180035ad6  nop
0x180035ad7  mov     rcx, [rbp+pv]; pv
0x180035adb  mov     [rbp+pv], 0
0x180035ae3  test    rcx, rcx
0x180035ae6  jz      short loc_180035AF4
0x180035ae8  call    cs:__imp_CoTaskMemFree
0x180035aef  nop     dword ptr [rax+rax+00h]
0x180035af4  mov     eax, r15d
0x180035af7  jmp     loc_1800359CB
0x180035afc  mov     rax, [rbp+var_58]
0x180035b00  mov     qword ptr [rax], 0
0x180035b07  mov     edi, 80070057h
0x180035b0c  mov     rcx, [rbp+40h]; this
0x180035b10  mov     r9d, edi; char *
0x180035b13  lea     r8, aOnecoreuapShel_18; "onecoreuap\\shell\\windows.storage\\fil"...
0x180035b1a  mov     edx, 257Fh; void *
0x180035b1f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180035b24  nop
0x180035b25  mov     rcx, [rbp+pv]; pv
0x180035b29  mov     [rbp+pv], 0
0x180035b31  test    rcx, rcx
0x180035b34  jz      short loc_180035B42
0x180035b36  call    cs:__imp_CoTaskMemFree
0x180035b3d  nop     dword ptr [rax+rax+00h]
0x180035b42  mov     eax, edi
0x180035b44  jmp     loc_1800359CB
0x180035b49  mov     [rbp+ppMalloc], 0
0x180035b51  lea     rsi, [rbp+ppMalloc]
0x180035b55  mov     [rbp+var_50], rsi
0x180035b59  mov     r14b, 1
0x180035b5c  mov     [rbp+var_40], r14b
0x180035b60  xor     ebx, ebx
0x180035b62  mov     [rbp+TokenHandle], rbx
0x180035b66  mov     r13, [rbp+var_20]
0x180035b6a  mov     rdx, r13; struct _ITEMIDLIST_RELATIVE *
0x180035b6d  call    ?_IsValidID@CFSFolder@@IEAAPEFBUIDFOLDER@@PEFBU_ITEMIDLIST_RELATIVE@@@Z; CFSFolder::_IsValidID(_ITEMIDLIST_RELATIVE const *)
0x180035b72  mov     rcx, rax; pidl
0x180035b75  call    ILCloneFirst
0x180035b7a  mov     [rbp+var_20], rax
0x180035b7e  test    rax, rax
0x180035b81  jnz     short loc_180035BE9
0x180035b83  test    r14b, r14b
0x180035b86  jz      short loc_180035B9F
0x180035b88  mov     rcx, [rsi]; pv
0x180035b8b  mov     [rsi], rbx
0x180035b8e  test    rcx, rcx
0x180035b91  jz      short loc_180035B9F
0x180035b93  call    cs:__imp_CoTaskMemFree
0x180035b9a  nop     dword ptr [rax+rax+00h]
0x180035b9f  test    r15d, r15d
0x180035ba2  js      loc_180035C29
0x180035ba8  mov     r8, [rbp+var_58]; struct _ITEMIDLIST_ABSOLUTE **
0x180035bac  mov     rdx, [rbp+ppMalloc]; struct _ITEMIDLIST_RELATIVE *
0x180035bb0  mov     rcx, [rbp+pv]; Src
0x180035bb4  call    ?SHILCombine@@YAJPEBU_ITEMIDLIST_ABSOLUTE@@PEFBU_ITEMIDLIST_RELATIVE@@PEAPEAU1@@Z; SHILCombine(_ITEMIDLIST_ABSOLUTE const *,_ITEMIDLIST_RELATIVE const *,_ITEMIDLIST_ABSOLUTE * *)
0x180035bb9  mov     ebx, eax
0x180035bbb  test    eax, eax
0x180035bbd  js      loc_180035C68
0x180035bc3  mov     rcx, [rbp+ppMalloc]; pv
0x180035bc7  mov     [rbp+ppMalloc], 0
0x180035bcf  test    rcx, rcx
0x180035bd2  jz      loc_1800359AC
0x180035bd8  call    cs:__imp_CoTaskMemFree
  ... truncated ...
```
