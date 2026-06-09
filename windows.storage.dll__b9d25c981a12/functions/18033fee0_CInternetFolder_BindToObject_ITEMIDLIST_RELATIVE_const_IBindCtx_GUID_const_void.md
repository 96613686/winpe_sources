# CInternetFolder::BindToObject(_ITEMIDLIST_RELATIVE const *,IBindCtx *,_GUID const &,void * *)

- ea: `0x18033fee0`
- end: `0x18034067b`
- name: `?BindToObject@CInternetFolder@@UEAAJPEFBU_ITEMIDLIST_RELATIVE@@PEAUIBindCtx@@AEBU_GUID@@PEAPEAX@Z`
- size: `1947`
- prototype: `int(CInternetFolder *__hidden this, const struct _ITEMIDLIST_RELATIVE *, struct IBindCtx *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1806163e0`

## callees

- `0x180013140`
- `0x180038f50`
- `0x18006b698`
- `0x1800899a4`
- `0x1800c72b0`
- `0x1800d1620`
- `0x1800d1b40`
- `0x1800d1ed4`
- `0x18015c5a0`
- `0x1801ae280`
- `0x1801ee6c0`
- `0x18022d568`
- `0x18024e524`
- `0x18033fee0`
- `0x1803554b0`
- `0x1803b1f60`
- `0x1803b243c`
- `0x1803b2ac0`
- `0x1803b2ea5`
- `0x18067d010`

## import_xrefs

- `api-ms-win-core-url-l1-1-0!UrlGetLocationW` at `0x1803403c2`
- `api-ms-win-core-url-l1-1-0!UrlGetLocationW` at `0x1803403c2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1803401fe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1803403f3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1803401fe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1803403f3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18034003e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18034024b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1803404c1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1803404f2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180340575`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180340604`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180340613`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180340628`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18034003e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18034024b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1803404c1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1803404f2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180340575`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180340604`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180340613`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180340628`
- `SHCORE!__imp_ualstrcpynW` at `0x180340541`
- `SHCORE!__imp_ualstrcpynW` at `0x180340541`
- `urlmon!CreateURLMonikerEx` at `0x180340088`
- `urlmon!CreateURLMonikerEx` at `0x180340088`
- `api-ms-win-ole32-ie-l1-1-0!CreateBindCtx` at `0x1803400ab`
- `api-ms-win-ole32-ie-l1-1-0!CreateBindCtx` at `0x1803400ab`
- `ext-ms-win-com-ole32-l1-1-1!MkParseDisplayName` at `0x1803400d3`
- `ext-ms-win-com-ole32-l1-1-1!MkParseDisplayName` at `0x1803400d3`

## string_xrefs

- `0x180340669`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
        memcpy_s(v24, v23 + 2, v17, v23);
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
0x18033fee0  push    rbp
0x18033fee2  push    rbx
0x18033fee3  push    rsi
0x18033fee4  push    rdi
0x18033fee5  push    r12
0x18033fee7  push    r13
0x18033fee9  push    r14
0x18033feeb  push    r15
0x18033feed  mov     rbp, rsp
0x18033fef0  sub     rsp, 78h
0x18033fef4  mov     rax, cs:__security_cookie
0x18033fefb  xor     rax, rsp
0x18033fefe  mov     [rbp+var_10], rax
0x18033ff02  mov     r12, r9
0x18033ff05  mov     [rbp+var_30], r9
0x18033ff09  mov     rdi, r8
0x18033ff0c  mov     r14, rdx
0x18033ff0f  mov     rsi, rcx
0x18033ff12  mov     [rbp+ppbc], rcx
0x18033ff16  mov     rax, [rbp+arg_20]
0x18033ff1a  mov     [rbp+ppmk], rax
0x18033ff1e  xor     r15d, r15d
0x18033ff21  mov     [rax], r15
0x18033ff24  mov     ebx, 80070057h
0x18033ff29  mov     dl, 1; bool
0x18033ff2b  mov     rcx, r14; struct _ITEMIDLIST_RELATIVE *
0x18033ff2e  call    ?_IsValidUrlID@@YAPEFBUtagURLID@@PEFBU_ITEMIDLIST_RELATIVE@@_N@Z; _IsValidUrlID(_ITEMIDLIST_RELATIVE const *,bool)
0x18033ff33  test    rax, rax
0x18033ff36  jz      loc_180340649
0x18033ff3c  mov     [rbp+var_20], r15
0x18033ff40  lea     r13, [rsi-8]
0x18033ff44  movzx   eax, word ptr [r14]
0x18033ff48  mov     r15d, 7FFFFFFFh
0x18033ff4e  cmp     eax, 7
0x18033ff51  jbe     loc_18033FFF4
0x18033ff57  mov     ecx, 361h
0x18033ff5c  cmp     [r14+2], cx
0x18033ff61  jnz     loc_18033FFF4
0x18033ff67  movzx   edx, word ptr [r14+4]
0x18033ff6c  mov     ecx, eax
0x18033ff6e  lea     eax, [rdx+6]
0x18033ff71  cmp     ecx, eax
0x18033ff73  jb      short loc_18033FFF4
0x18033ff75  lea     r10, [rdx+6]
0x18033ff79  add     r10, r14
0x18033ff7c  jz      short loc_18033FFF4
0x18033ff7e  sub     ecx, edx
0x18033ff80  sub     ecx, 6
0x18033ff83  movsxd  rcx, ecx
0x18033ff86  cmp     rcx, r15
0x18033ff89  ja      short loc_18033FFF4
0x18033ff8b  mov     rax, r10
0x18033ff8e  test    rcx, rcx
0x18033ff91  jz      short loc_18033FFF4
0x18033ff93  cmp     byte ptr [rax], 0
0x18033ff96  jz      short loc_18033FFA1
0x18033ff98  inc     rax
0x18033ff9b  sub     rcx, 1
0x18033ff9f  jnz     short loc_18033FF93
0x18033ffa1  test    rcx, rcx
0x18033ffa4  jz      short loc_18033FFF4
0x18033ffa6  mov     [rsp+78h+var_58], 1; int
0x18033ffae  lea     r9, [rbp+var_20]; struct IShellFolder **
0x18033ffb2  mov     r8, rdi; struct IBindCtx *
0x18033ffb5  mov     rdx, r10; char *
0x18033ffb8  mov     rcx, r13; this
0x18033ffbb  call    ?_CreateProtocolHandler@CInternetFolder@@IEAAJPEBDPEAUIBindCtx@@PEAPEAUIShellFolder@@H@Z; CInternetFolder::_CreateProtocolHandler(char const *,IBindCtx *,IShellFolder * *,int)
0x18033ffc0  test    eax, eax
0x18033ffc2  jnz     short loc_18033FFFC
0x18033ffc4  mov     rcx, [rbp+var_20]
0x18033ffc8  mov     rax, [rcx]
0x18033ffcb  mov     rdx, [rbp+ppmk]
0x18033ffcf  mov     qword ptr [rsp+78h+var_58], rdx
0x18033ffd4  mov     r9, r12
0x18033ffd7  mov     r8, rdi
0x18033ffda  mov     rdx, r14
0x18033ffdd  mov     rax, [rax+28h]
0x18033ffe1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18033ffe6  mov     ebx, eax
0x18033ffe8  cmp     eax, 800704C7h
0x18033ffed  jz      short loc_18033FFFC
0x18033ffef  jmp     loc_180340634
0x18033fff4  mov     [rbp+var_20], 0
0x18033fffc  mov     [rbp+pv], 0
0x180340004  lea     r8, [rbp+pv]
0x180340008  xor     edx, edx
0x18034000a  mov     rcx, r14
0x18034000d  call    ?GetUriFromUrlIdList@@YAJPEFBUtagURLID@@W4UriFromIdListOptions@@PEAPEAG@Z; GetUriFromUrlIdList(tagURLID const *,UriFromIdListOptions,ushort * *)
0x180340012  mov     ebx, eax
0x180340014  test    eax, eax
0x180340016  jns     short loc_18034004F
0x180340018  mov     rcx, [rbp+40h]; this
0x18034001c  mov     r9d, eax; char *
0x18034001f  lea     r8, aOnecoreuapShel_154; "onecoreuap\\shell\\windows.storage\\int"...
0x180340026  mov     edx, 6EEh; void *
0x18034002b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180340030  nop
0x180340031  mov     rcx, [rbp+pv]; pv
0x180340035  test    rcx, rcx
0x180340038  jz      loc_180340649
0x18034003e  call    cs:__imp_CoTaskMemFree
0x180340045  nop     dword ptr [rax+rax+00h]
0x18034004a  jmp     loc_180340649
0x18034004f  mov     rax, qword ptr cs:IID_IMoniker.Data1
0x180340056  mov     rsi, [rbp+pv]
0x18034005a  cmp     rax, [r12]
0x18034005e  jnz     loc_1803400F6
0x180340064  mov     rax, qword ptr cs:IID_IMoniker.Data4
0x18034006b  cmp     rax, [r12+8]
0x180340070  jnz     loc_1803400F6
0x180340076  mov     r9d, 1; dwFlags
0x18034007c  mov     rdi, [rbp+ppmk]
0x180340080  mov     r8, rdi; ppmk
0x180340083  mov     rdx, rsi; szURL
0x180340086  xor     ecx, ecx; pMkCtx
0x180340088  call    cs:__imp_CreateURLMonikerEx
0x18034008f  nop     dword ptr [rax+rax+00h]
0x180340094  mov     ebx, eax
0x180340096  test    eax, eax
0x180340098  jns     loc_180340620
0x18034009e  xor     r14d, r14d
0x1803400a1  mov     [rbp+ppbc], r14
0x1803400a5  lea     rdx, [rbp+ppbc]; ppbc
0x1803400a9  xor     ecx, ecx; reserved
0x1803400ab  call    cs:__imp_CreateBindCtx
0x1803400b2  nop     dword ptr [rax+rax+00h]
0x1803400b7  mov     ebx, eax
0x1803400b9  test    eax, eax
0x1803400bb  js      loc_180340620
0x1803400c1  mov     [rbp+pchEaten], r14d
0x1803400c5  mov     r9, rdi; ppmk
0x1803400c8  lea     r8, [rbp+pchEaten]; pchEaten
0x1803400cc  mov     rdx, rsi; szUserName
0x1803400cf  mov     rcx, [rbp+ppbc]; pbc
0x1803400d3  call    cs:__imp_MkParseDisplayName
0x1803400da  nop     dword ptr [rax+rax+00h]
0x1803400df  mov     ebx, eax
0x1803400e1  mov     rcx, [rbp+ppbc]
0x1803400e5  mov     rax, [rcx]
0x1803400e8  mov     rax, [rax+10h]
0x1803400ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803400f1  jmp     loc_180340620
0x1803400f6  mov     rax, qword ptr cs:IID_IPropertyStoreFactory.Data1
0x1803400fd  cmp     rax, [r12]
0x180340101  jnz     short loc_180340111
0x180340103  mov     rax, qword ptr cs:IID_IPropertyStoreFactory.Data4
0x18034010a  cmp     rax, [r12+8]
0x18034010f  jz      short loc_180340134
0x180340111  mov     rax, qword ptr cs:IID_IPropertyStore.Data1
0x180340118  cmp     rax, [r12]
0x18034011c  jnz     loc_1803403B3
0x180340122  mov     rax, qword ptr cs:IID_IPropertyStore.Data4
0x180340129  cmp     rax, [r12+8]
0x18034012e  jnz     loc_1803403B3
0x180340134  xor     edx, edx
0x180340136  mov     rcx, rdi
0x180340139  call    BindCtx_GetMode
0x18034013e  test    al, 3
0x180340140  jz      short loc_18034014C
0x180340142  mov     ebx, 80030005h
0x180340147  jmp     loc_180340620
0x18034014c  mov     [rbp+ppbc], 0
0x180340154  lea     rdx, [rbp+ppbc]; struct IUrlHistoryStg **
0x180340158  mov     rcx, r13; this
0x18034015b  call    ?_InitHistoryStg@CInternetFolder@@IEAAJPEAPEAUIUrlHistoryStg@@@Z; CInternetFolder::_InitHistoryStg(IUrlHistoryStg * *)
0x180340160  nop
0x180340161  mov     rbx, [rbp+ppbc]
0x180340165  xor     r13d, r13d
0x180340168  mov     qword ptr [rbp+pchEaten], r13
0x18034016c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180340173  mov     ecx, 20h ; ' '; unsigned __int64
0x180340178  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18034017d  mov     rdi, rax
0x180340180  test    rax, rax
0x180340183  jnz     short loc_18034018F
0x180340185  mov     ebx, 8007000Eh
0x18034018a  jmp     loc_18034037A
0x18034018f  mov     dword ptr [rax+0Ch], 1
0x180340196  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIPropertyStoreFactory@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IPropertyStoreFactory>::`vftable'
0x18034019d  mov     [rdi], rax
0x1803401a0  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1803401a7  test    rcx, rcx
0x1803401aa  jz      short loc_1803401B9
0x1803401ac  mov     rax, [rcx]
0x1803401af  mov     rax, [rax+8]
0x1803401b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803401b8  nop
0x1803401b9  lea     rax, ??_7CInternetFolderPropertyStoreFactory@@6B@; const CInternetFolderPropertyStoreFactory::`vftable'
0x1803401c0  mov     [rdi], rax
0x1803401c3  mov     [rdi+10h], r13
0x1803401c7  mov     [rdi+18h], r13
0x1803401cb  mov     rcx, [rbp+40h]; this
0x1803401cf  test    rsi, rsi
0x1803401d2  jz      loc_180340669
0x1803401d8  mov     rax, rsi
0x1803401db  nop     dword ptr [rax+rax+00h]
0x1803401e0  cmp     word ptr [rax], 0
0x1803401e4  jz      short loc_1803401F0
0x1803401e6  add     rax, 2
0x1803401ea  sub     r15, 1
0x1803401ee  jnz     short loc_1803401E0
0x1803401f0  sub     rax, rsi
0x1803401f3  sar     rax, 1
0x1803401f6  lea     r15, [rax+rax]
0x1803401fa  lea     rcx, [r15+2]; cb
0x1803401fe  call    cs:__imp_CoTaskMemAlloc
0x180340205  nop     dword ptr [rax+rax+00h]
0x18034020a  mov     r14, rax
0x18034020d  test    rax, rax
0x180340210  jz      short loc_18034022E
0x180340212  mov     r9, r15; SourceSize
0x180340215  mov     r8, rsi; Source
0x180340218  lea     rdx, [r15+2]; DestinationSize
0x18034021c  mov     rcx, rax; Destination
0x18034021f  call    memcpy_s
0x180340224  xor     r13d, r13d
0x180340227  mov     [r15+r14], r13w
0x18034022c  jmp     short loc_180340231
0x18034022e  xor     r13d, r13d
0x180340231  mov     [rbp+Size], r14
0x180340235  lea     rdx, [rbp+Size]
0x180340239  lea     rcx, [rdi+10h]
0x18034023d  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x180340242  mov     rcx, [rbp+Size]; pv
0x180340246  test    rcx, rcx
0x180340249  jz      short loc_180340257
0x18034024b  call    cs:__imp_CoTaskMemFree
0x180340252  nop     dword ptr [rax+rax+00h]
0x180340257  cmp     qword ptr [rdi+10h], 0
0x18034025c  jnz     short loc_180340291
0x18034025e  mov     rcx, [rbp+40h]; this
0x180340262  mov     ebx, 8007000Eh
0x180340267  mov     r9d, ebx; char *
0x18034026a  lea     r8, aOnecoreuapShel_154; "onecoreuap\\shell\\windows.storage\\int"...
0x180340271  mov     edx, 3CBh; void *
0x180340276  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18034027b  nop
0x18034027c  mov     rax, [rdi]
0x18034027f  mov     rcx, rdi
0x180340282  mov     rax, [rax+10h]
0x180340286  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18034028b  nop
0x18034028c  jmp     loc_18034037A
0x180340291  cmp     [rdi+18h], rbx
0x180340295  jz      short loc_1803402C6
0x180340297  test    rbx, rbx
0x18034029a  jz      short loc_1803402AC
0x18034029c  mov     rax, [rbx]
0x18034029f  mov     rcx, rbx
0x1803402a2  mov     rax, [rax+8]
0x1803402a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803402ab  nop
0x1803402ac  mov     rcx, [rdi+18h]
0x1803402b0  mov     [rdi+18h], rbx
0x1803402b4  test    rcx, rcx
0x1803402b7  jz      short loc_1803402C6
0x1803402b9  mov     rax, [rcx]
0x1803402bc  mov     rax, [rax+10h]
0x1803402c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803402c5  nop
0x1803402c6  mov     rax, [rdi]
0x1803402c9  lea     r8, [rbp+pchEaten]
0x1803402cd  lea     rdx, _GUID_bc110b6d_57e8_4148_a9c6_91015ab2f3a5
0x1803402d4  mov     rcx, rdi
0x1803402d7  mov     rax, [rax]
0x1803402da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803402df  mov     ebx, eax
0x1803402e1  mov     rax, [rdi]
0x1803402e4  mov     rcx, rdi
0x1803402e7  mov     rax, [rax+10h]
0x1803402eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803402f0  nop
0x1803402f1  test    ebx, ebx
0x1803402f3  js      loc_18034037A
0x1803402f9  mov     r9, [rbp+var_30]
0x1803402fd  mov     rax, [r9]
0x180340300  cmp     rax, qword ptr cs:IID_IPropertyStoreFactory.Data1
0x180340307  jnz     short loc_18034033D
0x180340309  mov     rax, [r9+8]
0x18034030d  cmp     rax, qword ptr cs:IID_IPropertyStoreFactory.Data4
0x180340314  jnz     short loc_18034033D
0x180340316  mov     rcx, qword ptr [rbp+pchEaten]
0x18034031a  mov     rax, [rcx]
0x18034031d  mov     r8, [rbp+ppmk]
0x180340321  mov     rdx, r9
0x180340324  mov     rax, [rax]
0x180340327  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18034032c  mov     ebx, eax
0x18034032e  mov     rcx, [rbp+40h]
0x180340332  test    eax, eax
0x180340334  jns     short loc_18034037A
0x180340336  mov     edx, 707h
0x18034033b  jmp     short loc_18034036A
0x18034033d  mov     rcx, qword ptr [rbp+pchEaten]
0x180340341  mov     rax, [rcx]
0x180340344  mov     rdx, [rbp+ppmk]
0x180340348  mov     qword ptr [rsp+78h+var_58], rdx; int
0x18034034d  xor     r8d, r8d
0x180340350  xor     edx, edx
0x180340352  mov     rax, [rax+18h]
  ... truncated ...
```
