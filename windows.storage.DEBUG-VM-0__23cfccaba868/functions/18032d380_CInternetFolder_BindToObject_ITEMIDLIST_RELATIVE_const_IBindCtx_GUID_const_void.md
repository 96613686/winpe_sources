# CInternetFolder::BindToObject(_ITEMIDLIST_RELATIVE const *,IBindCtx *,_GUID const &,void * *)

- ea: `0x18032d380`
- end: `0x18032dab7`
- name: `?BindToObject@CInternetFolder@@UEAAJPEFBU_ITEMIDLIST_RELATIVE@@PEAUIBindCtx@@AEBU_GUID@@PEAPEAX@Z`
- size: `1847`
- prototype: `int(CInternetFolder *__hidden this, const struct _ITEMIDLIST_RELATIVE *, struct IBindCtx *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1805f63b0`

## callees

- `0x1800432f0`
- `0x18007e0a0`
- `0x1800d98d0`
- `0x1800dd190`
- `0x1801279b0`
- `0x180129650`
- `0x180129b40`
- `0x180129edc`
- `0x18014be50`
- `0x18014c740`
- `0x180197520`
- `0x180217d88`
- `0x18023da3c`
- `0x18032d380`
- `0x1803440d0`
- `0x1803a4cb0`
- `0x1803a518c`
- `0x1803a57e0`
- `0x1803a5bc5`
- `0x18065a010`

## import_xrefs

- `api-ms-win-core-url-l1-1-0!UrlGetLocationW` at `0x18032d836`
- `api-ms-win-core-url-l1-1-0!UrlGetLocationW` at `0x18032d836`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18032d67e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18032d863`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18032d67e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18032d863`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18032d4de`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18032d6c5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18032d92c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18032d957`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18032d9ce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18032da53`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18032da5c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18032da6b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18032d4de`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18032d6c5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18032d92c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18032d957`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18032d9ce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18032da53`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18032da5c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18032da6b`
- `SHCORE!__imp_ualstrcpynW` at `0x18032d9a0`
- `SHCORE!__imp_ualstrcpynW` at `0x18032d9a0`
- `urlmon!CreateURLMonikerEx` at `0x18032d51a`
- `urlmon!CreateURLMonikerEx` at `0x18032d51a`
- `api-ms-win-ole32-ie-l1-1-0!CreateBindCtx` at `0x18032d537`
- `api-ms-win-ole32-ie-l1-1-0!CreateBindCtx` at `0x18032d537`
- `ext-ms-win-com-ole32-l1-1-1!MkParseDisplayName` at `0x18032d559`
- `ext-ms-win-com-ole32-l1-1-1!MkParseDisplayName` at `0x18032d559`

## string_xrefs

- `0x18032daa5`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CInternetFolder::BindToObject(
        IBindCtx *this,
        const struct _ITEMIDLIST_RELATIVE *a2,
        struct IBindCtx *a3,
        const struct _GUID *a4,
        void **a5)
{
  const struct _GUID *v5; // r12
  const struct _ITEMIDLIST_RELATIVE *v7; // r14
  HRESULT URLMoniker; // ebx
  CInternetFolder *v10; // r13
  unsigned int v11; // eax
  __int64 v12; // r15
  __int64 v13; // rdx
  unsigned __int64 v14; // rcx
  _BYTE *v15; // rax
  int UriFromUrlIdList; // eax
  OLECHAR *v17; // rsi
  LPBC v18; // rbx
  _QWORD *v19; // rax
  const char *v20; // r9
  _QWORD *v21; // rdi
  OLECHAR *v22; // rax
  rsize_t v23; // r15
  void *v24; // rax
  size_t v25; // r14
  __int64 v26; // rcx
  int v27; // eax
  wil::details::in1diag3 *v28; // rcx
  __int64 v29; // rdx
  __int64 v30; // rcx
  LPBC v31; // rcx
  _WORD *v32; // rdi
  LPCWSTR LocationW; // r12
  __int64 v34; // rbx
  __int64 v35; // rcx
  unsigned __int64 v36; // rdi
  unsigned __int16 *v37; // rax
  unsigned __int16 *v38; // r15
  OLECHAR *v39; // r14
  unsigned int v40; // r13d
  _WORD *v41; // rax
  const struct _ITEMIDLIST_ABSOLUTE *v42; // r14
  CDocObjectFolder *v43; // rax
  CDocObjectFolder *v44; // rax
  CDocObjectFolder *v45; // r15
  int v47; // [rsp+20h] [rbp-58h]
  int v48; // [rsp+20h] [rbp-58h]
  int v49; // [rsp+20h] [rbp-58h]
  size_t Size; // [rsp+38h] [rbp-40h] BYREF
  LPVOID pv; // [rsp+40h] [rbp-38h] BYREF
  const struct _GUID *v52; // [rsp+48h] [rbp-30h]
  LPBC ppbc; // [rsp+50h] [rbp-28h] BYREF
  struct IShellFolder *v54; // [rsp+58h] [rbp-20h] BYREF
  ULONG pchEaten[2]; // [rsp+60h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+40h]

  v5 = a4;
  v52 = a4;
  v7 = a2;
  ppbc = this;
  *a5 = 0;
  URLMoniker = -2147024809;
  if ( !_IsValidUrlID(a2, 1) )
    return (unsigned int)URLMoniker;
  v54 = 0;
  v10 = (CInternetFolder *)&this[-1];
  v11 = *(unsigned __int16 *)v7;
  v12 = 0x7FFFFFFF;
  if ( v11 <= 7 )
    goto LABEL_14;
  if ( *((_WORD *)v7 + 1) != 865 )
    goto LABEL_14;
  v13 = *((unsigned __int16 *)v7 + 2);
  if ( v11 < (int)v13 + 6 )
    goto LABEL_14;
  if ( !(const struct _ITEMIDLIST_RELATIVE *)((char *)v7 + v13 + 6) )
    goto LABEL_14;
  v14 = (int)(v11 - v13 - 6);
  if ( v14 > 0x7FFFFFFF )
    goto LABEL_14;
  v15 = (char *)v7 + v13 + 6;
  if ( !v14 )
    goto LABEL_14;
  do
  {
    if ( !*v15 )
      break;
    ++v15;
    --v14;
  }
  while ( v14 );
  if ( v14 )
  {
    if ( !CInternetFolder::_CreateProtocolHandler((CInternetFolder *)&this[-1], (const char *)v7 + v13 + 6, a3, &v54, 1) )
    {
      v47 = (int)a5;
      URLMoniker = ((__int64 (__fastcall *)(struct IShellFolder *, const struct _ITEMIDLIST_RELATIVE *, struct IBindCtx *, const struct _GUID *))v54->lpVtbl->BindToObject)(
                     v54,
                     v7,
                     a3,
                     v5);
      if ( URLMoniker != -2147023673 )
      {
LABEL_94:
        if ( v54 )
          ((void (__fastcall *)(struct IShellFolder *))v54->lpVtbl->Release)(v54);
        return (unsigned int)URLMoniker;
      }
    }
  }
  else
  {
LABEL_14:
    v54 = 0;
  }
  pv = 0;
  UriFromUrlIdList = GetUriFromUrlIdList(v7, 0, &pv);
  URLMoniker = UriFromUrlIdList;
  if ( UriFromUrlIdList < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6EE,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\internetfolder\\internetfolder.cpp",
      (const char *)(unsigned int)UriFromUrlIdList,
      v47);
    if ( pv )
      CoTaskMemFree(pv);
    return (unsigned int)URLMoniker;
  }
  v17 = (OLECHAR *)pv;
  if ( *(_QWORD *)&IID_IMoniker.Data1 == *(_QWORD *)&v5->Data1 && *(_QWORD *)IID_IMoniker.Data4 == *(_QWORD *)v5->Data4 )
  {
    URLMoniker = CreateURLMonikerEx(0, (LPCWSTR)pv, (LPMONIKER *)a5, 1u);
    if ( URLMoniker < 0 )
    {
      ppbc = 0;
      URLMoniker = CreateBindCtx(0, &ppbc);
      if ( URLMoniker >= 0 )
      {
        pchEaten[0] = 0;
        URLMoniker = MkParseDisplayName(ppbc, v17, pchEaten, (LPMONIKER *)a5);
        ((void (__fastcall *)(LPBC))ppbc->lpVtbl->Release)(ppbc);
      }
    }
    goto LABEL_92;
  }
  if ( *(_QWORD *)&IID_IPropertyStoreFactory.Data1 == *(_QWORD *)&v5->Data1
    && *(_QWORD *)IID_IPropertyStoreFactory.Data4 == *(_QWORD *)v5->Data4
    || *(_QWORD *)&IID_IPropertyStore.Data1 == *(_QWORD *)&v5->Data1
    && *(_QWORD *)IID_IPropertyStore.Data4 == *(_QWORD *)v5->Data4 )
  {
    if ( (BindCtx_GetMode(a3, 0) & 3) != 0 )
    {
      URLMoniker = -2147287035;
LABEL_92:
      if ( v17 )
        CoTaskMemFree(v17);
      goto LABEL_94;
    }
    ppbc = 0;
    CInternetFolder::_InitHistoryStg(v10, (struct IUrlHistoryStg **)&ppbc);
    v18 = ppbc;
    *(_QWORD *)pchEaten = 0;
    v19 = operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
    v21 = v19;
    if ( v19 )
    {
      *((_DWORD *)v19 + 3) = 1;
      *v19 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IPropertyStoreFactory>::`vftable';
      if ( Microsoft::WRL::Details::ModuleBase::module_ )
        (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                             + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
      *v21 = &CInternetFolderPropertyStoreFactory::`vftable';
      v21[2] = 0;
      v21[3] = 0;
      if ( !v17 )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0xF89,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
          v20);
      v22 = v17;
      do
      {
        if ( !*v22 )
          break;
        ++v22;
        --v12;
      }
      while ( v12 );
      v23 = 2 * (v22 - v17);
      v24 = CoTaskMemAlloc(v23 + 2);
      v25 = (size_t)v24;
      if ( v24 )
      {
        memcpy_s_0(v24, v23 + 2, v17, v23);
        *(_WORD *)(v23 + v25) = 0;
      }
      Size = v25;
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
        v21 + 2,
        &Size);
      if ( Size )
        CoTaskMemFree((LPVOID)Size);
      if ( v21[2] )
      {
        if ( (LPBC)v21[3] != v18 )
        {
          if ( v18 )
            ((void (__fastcall *)(LPBC))v18->lpVtbl->AddRef)(v18);
          v26 = v21[3];
          v21[3] = v18;
          if ( v26 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
        }
        URLMoniker = (*(__int64 (__fastcall **)(_QWORD *, GUID *, ULONG *))*v21)(
                       v21,
                       &GUID_bc110b6d_57e8_4148_a9c6_91015ab2f3a5,
                       pchEaten);
        (*(void (__fastcall **)(_QWORD *))(*v21 + 16LL))(v21);
        if ( URLMoniker < 0 )
          goto LABEL_56;
        if ( *(_QWORD *)&v52->Data1 == *(_QWORD *)&IID_IPropertyStoreFactory.Data1
          && *(_QWORD *)v52->Data4 == *(_QWORD *)IID_IPropertyStoreFactory.Data4 )
        {
          v27 = (***(__int64 (__fastcall ****)(_QWORD, const struct _GUID *, void **))pchEaten)(
                  *(_QWORD *)pchEaten,
                  v52,
                  a5);
          URLMoniker = v27;
          v28 = retaddr;
          if ( v27 >= 0 )
            goto LABEL_56;
          v29 = 1799;
        }
        else
        {
          v47 = (int)a5;
          v27 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(**(_QWORD **)pchEaten + 24LL))(
                  *(_QWORD *)pchEaten,
                  0,
                  0);
          URLMoniker = v27;
          v28 = retaddr;
          if ( v27 >= 0 )
            goto LABEL_56;
          v29 = 1803;
        }
        wil::details::in1diag3::_Log_Hr(
          v28,
          (void *)v29,
          (unsigned int)"onecoreuap\\shell\\windows.storage\\internetfolder\\internetfolder.cpp",
          (const char *)(unsigned int)v27,
          v47);
        goto LABEL_56;
      }
      URLMoniker = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3CB,
        (unsigned int)"onecoreuap\\shell\\windows.storage\\internetfolder\\internetfolder.cpp",
        (const char *)0x8007000ELL,
        v47);
      (*(void (__fastcall **)(_QWORD *))(*v21 + 16LL))(v21);
    }
    else
    {
      URLMoniker = -2147024882;
    }
LABEL_56:
    v30 = *(_QWORD *)pchEaten;
    if ( *(_QWORD *)pchEaten )
    {
      *(_QWORD *)pchEaten = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
    }
    v31 = ppbc;
    if ( ppbc )
    {
      ppbc = 0;
      ((void (__fastcall *)(LPBC))v31->lpVtbl->Release)(v31);
    }
    goto LABEL_92;
  }
  v32 = 0;
  if ( !v54 )
  {
LABEL_85:
    URLMoniker = -2147024882;
    if ( v7 )
    {
      v42 = (const struct _ITEMIDLIST_ABSOLUTE *)ILCombine((LPCITEMIDLIST)ppbc[4].lpVtbl, (LPCITEMIDLIST)v7);
      if ( v42 )
      {
        v43 = (CDocObjectFolder *)operator new(0x30u, (const struct std::nothrow_t *)&std::nothrow);
        v52 = (const struct _GUID *)v43;
        if ( v43 )
        {
          v44 = CDocObjectFolder::CDocObjectFolder(v43, v42);
          v45 = v44;
          if ( v44 )
          {
            URLMoniker = (**(__int64 (__fastcall ***)(CDocObjectFolder *, const struct _GUID *, void **))v44)(
                           v44,
                           v5,
                           a5);
            (*(void (__fastcall **)(CDocObjectFolder *))(*(_QWORD *)v45 + 16LL))(v45);
          }
        }
        CoTaskMemFree(v42);
      }
      CoTaskMemFree(v32);
    }
    goto LABEL_92;
  }
  LocationW = UrlGetLocationW((PCWSTR)pv);
  v34 = -1;
  v35 = -1;
  do
    ++v35;
  while ( v17[v35] );
  v36 = (unsigned int)v35;
  v37 = (unsigned __int16 *)CoTaskMemAlloc(2LL * (unsigned int)v35 + 2);
  v38 = v37;
  if ( v37 )
  {
    *v37 = 0;
    v37[v36] = 0;
  }
  *(_QWORD *)pchEaten = v37;
  if ( !v37 )
  {
    URLMoniker = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x53C,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\internetfolder\\internetfolder.cpp",
      (const char *)0x8007000ELL,
      v47);
    goto LABEL_76;
  }
  if ( LocationW )
  {
    StringCchCopyNW(v37, v36, v17, LocationW - v17);
    v39 = v38;
  }
  else
  {
    v39 = v17;
    if ( !v17 )
    {
      LODWORD(v34) = 0;
      goto LABEL_74;
    }
  }
  do
    ++v34;
  while ( v39[v34] );
LABEL_74:
  v40 = v34 + 1;
  if ( (unsigned int)(2 * (v34 + 1) + 10) <= 0xFFFF )
  {
    Size = 2 * v40 + 12;
    v41 = WINRT_IMPL_CoTaskMemAlloc(Size);
    v32 = v41;
    if ( v41 )
    {
      memset_0(v41, 0, Size);
      *v32 = 2 * v40 + 10;
      v32[1] = -32671;
      *((_DWORD *)v32 + 1) = 0;
      ualstrcpynW(v32 + 4, v39, v40);
    }
    if ( v32 && LocationW && *LocationW )
      v32 = (_WORD *)ILAppendHiddenStringW(v32, 3203334145LL, LocationW);
    CoTaskMemFree(v38);
    v7 = (const struct _ITEMIDLIST_RELATIVE *)v32;
    v5 = v52;
    goto LABEL_85;
  }
  URLMoniker = -2147024882;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x526,
    (unsigned int)"onecoreuap\\shell\\windows.storage\\internetfolder\\internetfolder.cpp",
    (const char *)0x8007000ELL,
    v47);
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x547,
    (unsigned int)"onecoreuap\\shell\\windows.storage\\internetfolder\\internetfolder.cpp",
    (const char *)0x8007000ELL,
    v49);
  CoTaskMemFree(v38);
LABEL_76:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x71C,
    (unsigned int)"onecoreuap\\shell\\windows.storage\\internetfolder\\internetfolder.cpp",
    (const char *)0x8007000ELL,
    v48);
  if ( v17 )
    CoTaskMemFree(v17);
  return (unsigned int)URLMoniker;
}

```

## disassembly

```asm
0x18032d380  push    rbp
0x18032d382  push    rbx
0x18032d383  push    rsi
0x18032d384  push    rdi
0x18032d385  push    r12
0x18032d387  push    r13
0x18032d389  push    r14
0x18032d38b  push    r15
0x18032d38d  mov     rbp, rsp
0x18032d390  sub     rsp, 78h
0x18032d394  mov     rax, cs:__security_cookie
0x18032d39b  xor     rax, rsp
0x18032d39e  mov     [rbp+var_10], rax
0x18032d3a2  mov     r12, r9
0x18032d3a5  mov     [rbp+var_30], r9
0x18032d3a9  mov     rdi, r8
0x18032d3ac  mov     r14, rdx
0x18032d3af  mov     rsi, rcx
0x18032d3b2  mov     [rbp+ppbc], rcx
0x18032d3b6  mov     rax, [rbp+arg_20]
0x18032d3ba  mov     [rbp+ppmk], rax
0x18032d3be  xor     r15d, r15d
0x18032d3c1  mov     [rax], r15
0x18032d3c4  mov     ebx, 80070057h
0x18032d3c9  mov     dl, 1; bool
0x18032d3cb  mov     rcx, r14; struct _ITEMIDLIST_RELATIVE *
0x18032d3ce  call    ?_IsValidUrlID@@YAPEFBUtagURLID@@PEFBU_ITEMIDLIST_RELATIVE@@_N@Z; _IsValidUrlID(_ITEMIDLIST_RELATIVE const *,bool)
0x18032d3d3  test    rax, rax
0x18032d3d6  jz      loc_18032DA86
0x18032d3dc  mov     [rbp+var_20], r15
0x18032d3e0  lea     r13, [rsi-8]
0x18032d3e4  movzx   eax, word ptr [r14]
0x18032d3e8  mov     r15d, 7FFFFFFFh
0x18032d3ee  cmp     eax, 7
0x18032d3f1  jbe     loc_18032D494
0x18032d3f7  mov     ecx, 361h
0x18032d3fc  cmp     [r14+2], cx
0x18032d401  jnz     loc_18032D494
0x18032d407  movzx   edx, word ptr [r14+4]
0x18032d40c  mov     ecx, eax
0x18032d40e  lea     eax, [rdx+6]
0x18032d411  cmp     ecx, eax
0x18032d413  jb      short loc_18032D494
0x18032d415  lea     r10, [rdx+6]
0x18032d419  add     r10, r14
0x18032d41c  jz      short loc_18032D494
0x18032d41e  sub     ecx, edx
0x18032d420  sub     ecx, 6
0x18032d423  movsxd  rcx, ecx
0x18032d426  cmp     rcx, r15
0x18032d429  ja      short loc_18032D494
0x18032d42b  mov     rax, r10
0x18032d42e  test    rcx, rcx
0x18032d431  jz      short loc_18032D494
0x18032d433  cmp     byte ptr [rax], 0
0x18032d436  jz      short loc_18032D441
0x18032d438  inc     rax
0x18032d43b  sub     rcx, 1
0x18032d43f  jnz     short loc_18032D433
0x18032d441  test    rcx, rcx
0x18032d444  jz      short loc_18032D494
0x18032d446  mov     [rsp+78h+var_58], 1; int
0x18032d44e  lea     r9, [rbp+var_20]; struct IShellFolder **
0x18032d452  mov     r8, rdi; struct IBindCtx *
0x18032d455  mov     rdx, r10; char *
0x18032d458  mov     rcx, r13; this
0x18032d45b  call    ?_CreateProtocolHandler@CInternetFolder@@IEAAJPEBDPEAUIBindCtx@@PEAPEAUIShellFolder@@H@Z; CInternetFolder::_CreateProtocolHandler(char const *,IBindCtx *,IShellFolder * *,int)
0x18032d460  test    eax, eax
0x18032d462  jnz     short loc_18032D49C
0x18032d464  mov     rcx, [rbp+var_20]
0x18032d468  mov     rax, [rcx]
0x18032d46b  mov     rdx, [rbp+ppmk]
0x18032d46f  mov     qword ptr [rsp+78h+var_58], rdx
0x18032d474  mov     r9, r12
0x18032d477  mov     r8, rdi
0x18032d47a  mov     rdx, r14
0x18032d47d  mov     rax, [rax+28h]
0x18032d481  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18032d486  mov     ebx, eax
0x18032d488  cmp     eax, 800704C7h
0x18032d48d  jz      short loc_18032D49C
0x18032d48f  jmp     loc_18032DA71
0x18032d494  mov     [rbp+var_20], 0
0x18032d49c  mov     [rbp+pv], 0
0x18032d4a4  lea     r8, [rbp+pv]
0x18032d4a8  xor     edx, edx
0x18032d4aa  mov     rcx, r14
0x18032d4ad  call    ?GetUriFromUrlIdList@@YAJPEFBUtagURLID@@W4UriFromIdListOptions@@PEAPEAG@Z; GetUriFromUrlIdList(tagURLID const *,UriFromIdListOptions,ushort * *)
0x18032d4b2  mov     ebx, eax
0x18032d4b4  test    eax, eax
0x18032d4b6  jns     short loc_18032D4E9
0x18032d4b8  mov     rcx, [rbp+40h]; this
0x18032d4bc  mov     r9d, eax; char *
0x18032d4bf  lea     r8, aOnecoreuapShel_154; "onecoreuap\\shell\\windows.storage\\int"...
0x18032d4c6  mov     edx, 6EEh; void *
0x18032d4cb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18032d4d0  nop
0x18032d4d1  mov     rcx, [rbp+pv]; pv
0x18032d4d5  test    rcx, rcx
0x18032d4d8  jz      loc_18032DA86
0x18032d4de  call    cs:__imp_CoTaskMemFree
0x18032d4e4  jmp     loc_18032DA86
0x18032d4e9  mov     rax, qword ptr cs:IID_IMoniker.Data1
0x18032d4f0  mov     rsi, [rbp+pv]
0x18032d4f4  cmp     rax, [r12]
0x18032d4f8  jnz     short loc_18032D576
0x18032d4fa  mov     rax, qword ptr cs:IID_IMoniker.Data4
0x18032d501  cmp     rax, [r12+8]
0x18032d506  jnz     short loc_18032D576
0x18032d508  mov     r9d, 1; dwFlags
0x18032d50e  mov     rdi, [rbp+ppmk]
0x18032d512  mov     r8, rdi; ppmk
0x18032d515  mov     rdx, rsi; szURL
0x18032d518  xor     ecx, ecx; pMkCtx
0x18032d51a  call    cs:__imp_CreateURLMonikerEx
0x18032d520  mov     ebx, eax
0x18032d522  test    eax, eax
0x18032d524  jns     loc_18032DA63
0x18032d52a  xor     r14d, r14d
0x18032d52d  mov     [rbp+ppbc], r14
0x18032d531  lea     rdx, [rbp+ppbc]; ppbc
0x18032d535  xor     ecx, ecx; reserved
0x18032d537  call    cs:__imp_CreateBindCtx
0x18032d53d  mov     ebx, eax
0x18032d53f  test    eax, eax
0x18032d541  js      loc_18032DA63
0x18032d547  mov     [rbp+pchEaten], r14d
0x18032d54b  mov     r9, rdi; ppmk
0x18032d54e  lea     r8, [rbp+pchEaten]; pchEaten
0x18032d552  mov     rdx, rsi; szUserName
0x18032d555  mov     rcx, [rbp+ppbc]; pbc
0x18032d559  call    cs:__imp_MkParseDisplayName
0x18032d55f  mov     ebx, eax
0x18032d561  mov     rcx, [rbp+ppbc]
0x18032d565  mov     rax, [rcx]
0x18032d568  mov     rax, [rax+10h]
0x18032d56c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18032d571  jmp     loc_18032DA63
0x18032d576  mov     rax, qword ptr cs:IID_IPropertyStoreFactory.Data1
0x18032d57d  cmp     rax, [r12]
0x18032d581  jnz     short loc_18032D591
0x18032d583  mov     rax, qword ptr cs:IID_IPropertyStoreFactory.Data4
0x18032d58a  cmp     rax, [r12+8]
0x18032d58f  jz      short loc_18032D5B4
0x18032d591  mov     rax, qword ptr cs:IID_IPropertyStore.Data1
0x18032d598  cmp     rax, [r12]
0x18032d59c  jnz     loc_18032D827
0x18032d5a2  mov     rax, qword ptr cs:IID_IPropertyStore.Data4
0x18032d5a9  cmp     rax, [r12+8]
0x18032d5ae  jnz     loc_18032D827
0x18032d5b4  xor     edx, edx
0x18032d5b6  mov     rcx, rdi
0x18032d5b9  call    BindCtx_GetMode
0x18032d5be  test    al, 3
0x18032d5c0  jz      short loc_18032D5CC
0x18032d5c2  mov     ebx, 80030005h
0x18032d5c7  jmp     loc_18032DA63
0x18032d5cc  mov     [rbp+ppbc], 0
0x18032d5d4  lea     rdx, [rbp+ppbc]; struct IUrlHistoryStg **
0x18032d5d8  mov     rcx, r13; this
0x18032d5db  call    ?_InitHistoryStg@CInternetFolder@@IEAAJPEAPEAUIUrlHistoryStg@@@Z; CInternetFolder::_InitHistoryStg(IUrlHistoryStg * *)
0x18032d5e0  nop
0x18032d5e1  mov     rbx, [rbp+ppbc]
0x18032d5e5  xor     r13d, r13d
0x18032d5e8  mov     qword ptr [rbp+pchEaten], r13
0x18032d5ec  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18032d5f3  mov     ecx, 20h ; ' '; unsigned __int64
0x18032d5f8  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18032d5fd  mov     rdi, rax
0x18032d600  test    rax, rax
0x18032d603  jnz     short loc_18032D60F
0x18032d605  mov     ebx, 8007000Eh
0x18032d60a  jmp     loc_18032D7EE
0x18032d60f  mov     dword ptr [rax+0Ch], 1
0x18032d616  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIPropertyStoreFactory@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IPropertyStoreFactory>::`vftable'
0x18032d61d  mov     [rdi], rax
0x18032d620  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18032d627  test    rcx, rcx
0x18032d62a  jz      short loc_18032D639
0x18032d62c  mov     rax, [rcx]
0x18032d62f  mov     rax, [rax+8]
0x18032d633  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18032d638  nop
0x18032d639  lea     rax, ??_7CInternetFolderPropertyStoreFactory@@6B@; const CInternetFolderPropertyStoreFactory::`vftable'
0x18032d640  mov     [rdi], rax
0x18032d643  mov     [rdi+10h], r13
0x18032d647  mov     [rdi+18h], r13
0x18032d64b  mov     rcx, [rbp+40h]; this
0x18032d64f  test    rsi, rsi
0x18032d652  jz      loc_18032DAA5
0x18032d658  mov     rax, rsi
0x18032d65b  nop     dword ptr [rax+rax+00h]
0x18032d660  cmp     word ptr [rax], 0
0x18032d664  jz      short loc_18032D670
0x18032d666  add     rax, 2
0x18032d66a  sub     r15, 1
0x18032d66e  jnz     short loc_18032D660
0x18032d670  sub     rax, rsi
0x18032d673  sar     rax, 1
0x18032d676  lea     r15, [rax+rax]
0x18032d67a  lea     rcx, [r15+2]; cb
0x18032d67e  call    cs:__imp_CoTaskMemAlloc
0x18032d684  mov     r14, rax
0x18032d687  test    rax, rax
0x18032d68a  jz      short loc_18032D6A8
0x18032d68c  mov     r9, r15; SourceSize
0x18032d68f  mov     r8, rsi; Source
0x18032d692  lea     rdx, [r15+2]; DestinationSize
0x18032d696  mov     rcx, rax; Destination
0x18032d699  call    memcpy_s_0
0x18032d69e  xor     r13d, r13d
0x18032d6a1  mov     [r15+r14], r13w
0x18032d6a6  jmp     short loc_18032D6AB
0x18032d6a8  xor     r13d, r13d
0x18032d6ab  mov     [rbp+Size], r14
0x18032d6af  lea     rdx, [rbp+Size]
0x18032d6b3  lea     rcx, [rdi+10h]
0x18032d6b7  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x18032d6bc  mov     rcx, [rbp+Size]; pv
0x18032d6c0  test    rcx, rcx
0x18032d6c3  jz      short loc_18032D6CB
0x18032d6c5  call    cs:__imp_CoTaskMemFree
0x18032d6cb  cmp     qword ptr [rdi+10h], 0
0x18032d6d0  jnz     short loc_18032D705
0x18032d6d2  mov     rcx, [rbp+40h]; this
0x18032d6d6  mov     ebx, 8007000Eh
0x18032d6db  mov     r9d, ebx; char *
0x18032d6de  lea     r8, aOnecoreuapShel_154; "onecoreuap\\shell\\windows.storage\\int"...
0x18032d6e5  mov     edx, 3CBh; void *
0x18032d6ea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18032d6ef  nop
0x18032d6f0  mov     rax, [rdi]
0x18032d6f3  mov     rcx, rdi
0x18032d6f6  mov     rax, [rax+10h]
0x18032d6fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18032d6ff  nop
0x18032d700  jmp     loc_18032D7EE
0x18032d705  cmp     [rdi+18h], rbx
0x18032d709  jz      short loc_18032D73A
0x18032d70b  test    rbx, rbx
0x18032d70e  jz      short loc_18032D720
0x18032d710  mov     rax, [rbx]
0x18032d713  mov     rcx, rbx
0x18032d716  mov     rax, [rax+8]
0x18032d71a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18032d71f  nop
0x18032d720  mov     rcx, [rdi+18h]
0x18032d724  mov     [rdi+18h], rbx
0x18032d728  test    rcx, rcx
0x18032d72b  jz      short loc_18032D73A
0x18032d72d  mov     rax, [rcx]
0x18032d730  mov     rax, [rax+10h]
0x18032d734  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18032d739  nop
0x18032d73a  mov     rax, [rdi]
0x18032d73d  lea     r8, [rbp+pchEaten]
0x18032d741  lea     rdx, _GUID_bc110b6d_57e8_4148_a9c6_91015ab2f3a5
0x18032d748  mov     rcx, rdi
0x18032d74b  mov     rax, [rax]
0x18032d74e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18032d753  mov     ebx, eax
0x18032d755  mov     rax, [rdi]
0x18032d758  mov     rcx, rdi
0x18032d75b  mov     rax, [rax+10h]
0x18032d75f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18032d764  nop
0x18032d765  test    ebx, ebx
0x18032d767  js      loc_18032D7EE
0x18032d76d  mov     r9, [rbp+var_30]
0x18032d771  mov     rax, [r9]
0x18032d774  cmp     rax, qword ptr cs:IID_IPropertyStoreFactory.Data1
0x18032d77b  jnz     short loc_18032D7B1
0x18032d77d  mov     rax, [r9+8]
0x18032d781  cmp     rax, qword ptr cs:IID_IPropertyStoreFactory.Data4
0x18032d788  jnz     short loc_18032D7B1
0x18032d78a  mov     rcx, qword ptr [rbp+pchEaten]
0x18032d78e  mov     rax, [rcx]
0x18032d791  mov     r8, [rbp+ppmk]
0x18032d795  mov     rdx, r9
0x18032d798  mov     rax, [rax]
0x18032d79b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18032d7a0  mov     ebx, eax
0x18032d7a2  mov     rcx, [rbp+40h]
0x18032d7a6  test    eax, eax
0x18032d7a8  jns     short loc_18032D7EE
0x18032d7aa  mov     edx, 707h
0x18032d7af  jmp     short loc_18032D7DE
0x18032d7b1  mov     rcx, qword ptr [rbp+pchEaten]
0x18032d7b5  mov     rax, [rcx]
0x18032d7b8  mov     rdx, [rbp+ppmk]
0x18032d7bc  mov     qword ptr [rsp+78h+var_58], rdx; int
0x18032d7c1  xor     r8d, r8d
0x18032d7c4  xor     edx, edx
0x18032d7c6  mov     rax, [rax+18h]
0x18032d7ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18032d7cf  mov     ebx, eax
0x18032d7d1  mov     rcx, [rbp+40h]; this
0x18032d7d5  test    eax, eax
0x18032d7d7  jns     short loc_18032D7EE
0x18032d7d9  mov     edx, 70Bh; void *
  ... truncated ...
```
