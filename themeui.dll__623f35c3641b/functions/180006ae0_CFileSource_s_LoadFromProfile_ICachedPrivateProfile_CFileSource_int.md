# CFileSource::s_LoadFromProfile(ICachedPrivateProfile *,CFileSource * *,int)

- ea: `0x180006ae0`
- end: `0x180007154`
- name: `?s_LoadFromProfile@CFileSource@@SAJPEAUICachedPrivateProfile@@PEAPEAV1@H@Z`
- size: `1652`
- prototype: `__int64 __fastcall(struct ICachedPrivateProfile *, struct CFileSource **, int)`
- caller_count: `3`
- callee_count: `14`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000561c`
- `0x1800065a0`
- `0x180061240`

## callees

- `0x180004c78`
- `0x1800051b8`
- `0x180005410`
- `0x180006ae0`
- `0x1800089c0`
- `0x180008e20`
- `0x180019160`
- `0x180030f64`
- `0x1800358c0`
- `0x180035ccc`
- `0x180052974`
- `0x180060fac`
- `0x1800618d0`
- `0x18006d010`

## import_xrefs

- `SHELL32!SHCreateItemFromParsingName` at `0x180006c25`
- `SHELL32!SHCreateItemFromParsingName` at `0x180006dd2`
- `SHELL32!SHCreateItemFromParsingName` at `0x180006c25`
- `SHELL32!SHCreateItemFromParsingName` at `0x180006dd2`
- `SHELL32!SHGetIDListFromObject` at `0x180006f6b`
- `SHELL32!SHGetIDListFromObject` at `0x180007033`
- `SHELL32!SHGetIDListFromObject` at `0x180006f6b`
- `SHELL32!SHGetIDListFromObject` at `0x180007033`
- `SHELL32!__imp_ILClone` at `0x180006e4a`
- `SHELL32!__imp_ILClone` at `0x180006e4a`
- `SHELL32!__imp_ILCombine` at `0x180006eed`
- `SHELL32!__imp_ILCombine` at `0x180006fcc`
- `SHELL32!__imp_ILCombine` at `0x180006eed`
- `SHELL32!__imp_ILCombine` at `0x180006fcc`
- `SHELL32!__imp_ILFree` at `0x180006e7c`
- `SHELL32!__imp_ILFree` at `0x180006efd`
- `SHELL32!__imp_ILFree` at `0x180006fdc`
- `SHELL32!__imp_ILFree` at `0x180007107`
- `SHELL32!__imp_ILFree` at `0x180006e7c`
- `SHELL32!__imp_ILFree` at `0x180006efd`
- `SHELL32!__imp_ILFree` at `0x180006fdc`
- `SHELL32!__imp_ILFree` at `0x180007107`
- `SHELL32!__imp_ILLoadFromStreamEx` at `0x180006eda`
- `SHELL32!__imp_ILLoadFromStreamEx` at `0x180006fb8`
- `SHELL32!__imp_ILLoadFromStreamEx` at `0x180006eda`
- `SHELL32!__imp_ILLoadFromStreamEx` at `0x180006fb8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006c3a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006de7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006c3a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006de7`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180006f08`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180006fe7`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180006f08`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180006fe7`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180006bff`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180006dad`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180006bff`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180006dad`

## pseudocode

```c
__int64 __fastcall CFileSource::s_LoadFromProfile(struct ICachedPrivateProfile *a1, struct CFileSource **a2, int a3)
{
  __int64 v3; // rax
  int v5; // edi
  int (__fastcall *v6)(struct ICachedPrivateProfile *, const WCHAR *, const unsigned __int16 *, __int64, __int16, IStream **); // rax
  HRESULT Error; // ebx
  __int64 v8; // rax
  struct IUnknown *v9; // rdx
  unsigned int v10; // r8d
  int v11; // edi
  volatile signed __int32 *v12; // rsi
  bool v13; // bl
  int v14; // r15d
  int v15; // r14d
  const ITEMIDLIST *v16; // r12
  __int64 v17; // rax
  int (__fastcall *v18)(struct ICachedPrivateProfile *, const WCHAR *, unsigned __int16 *, __int64, LPCITEMIDLIST, IStream **); // rax
  HRESULT v19; // edi
  __int64 v20; // rax
  struct IUnknown *v21; // rdx
  unsigned int v22; // r8d
  struct CFileSource **v23; // r14
  const ITEMIDLIST *v24; // rdi
  volatile signed __int32 *v25; // rax
  volatile signed __int32 *v26; // rbx
  LPITEMIDLIST v27; // rax
  HRESULT v29; // eax
  int Instance; // eax
  LPCITEMIDLIST pidl1; // [rsp+20h] [rbp-E0h]
  bool v32; // [rsp+40h] [rbp-C0h] BYREF
  LPCWSTR v33; // [rsp+48h] [rbp-B8h] BYREF
  void *ppv; // [rsp+50h] [rbp-B0h] BYREF
  LPCWSTR lpSrc; // [rsp+58h] [rbp-A8h] BYREF
  int v36; // [rsp+60h] [rbp-A0h]
  LPCITEMIDLIST pidl; // [rsp+68h] [rbp-98h] BYREF
  volatile signed __int32 *v38; // [rsp+70h] [rbp-90h]
  IStream *pstm[2]; // [rsp+78h] [rbp-88h] BYREF
  __int64 v40; // [rsp+88h] [rbp-78h]
  struct CFileSource **v41; // [rsp+90h] [rbp-70h]
  unsigned __int16 v42[16]; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int16 v43[20]; // [rsp+B8h] [rbp-48h] BYREF
  unsigned __int16 v44[64]; // [rsp+E0h] [rbp-20h] BYREF
  WCHAR Dst[264]; // [rsp+160h] [rbp+60h] BYREF

  v36 = a3;
  v40 = 0;
  *a2 = 0;
  v3 = *(_QWORD *)a1;
  v41 = a2;
  v5 = a3;
  pidl = 0;
  v6 = *(int (__fastcall **)(struct ICachedPrivateProfile *, const WCHAR *, const unsigned __int16 *, __int64, __int16, IStream **))(v3 + 40);
  *(_OWORD *)pstm = 0;
  if ( v6(a1, L"Slideshow", L"ImagesRootPIDL", 1, 66, pstm) >= 0 )
  {
    v33 = 0;
    Error = ILLoadFromStreamEx(pstm[1], (LPITEMIDLIST *)&v33);
    if ( Error >= 0 )
    {
      pidl = ILCombine(0, (LPCITEMIDLIST)v33);
      ILFree((LPITEMIDLIST)v33);
    }
    PropVariantClear((PROPVARIANT *)pstm);
  }
  else
  {
    pidl = 0;
    Error = StringCchPrintfW(v44, 0x40u, L"%s%s", L"ImagesRootPIDL", L"Path");
    if ( Error >= 0 )
    {
      v8 = *(_QWORD *)a1;
      lpSrc = 0;
      Error = (*(__int64 (__fastcall **)(struct ICachedPrivateProfile *, const WCHAR *, unsigned __int16 *, _QWORD, int, LPCWSTR *))(v8 + 48))(
                a1,
                L"Slideshow",
                v44,
                0,
                1,
                &lpSrc);
      if ( Error >= 0 )
      {
        if ( v5 != 1
          || (LODWORD(ppv) = -1, SHMapUrlToZoneEx(lpSrc, v9, v10, (unsigned int *)&ppv), !(_DWORD)ppv)
          || CFileSource::s_IsUncPathAllowedForThumbnailImage() )
        {
          if ( ExpandEnvironmentStringsW(lpSrc, Dst, 0x104u) > 0x104 )
          {
            Error = ResultFromKnownLastError();
          }
          else
          {
            ppv = 0;
            Error = SHCreateItemFromParsingName(Dst, 0, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, &ppv);
            if ( Error >= 0 )
            {
              v33 = 0;
              Error = GetFilteredShellItem((struct IShellItem *)ppv, (struct IShellItem **)&v33);
              if ( Error >= 0 )
              {
                Error = SHGetIDListFromObject((IUnknown *)v33, (LPITEMIDLIST *)&pidl);
                (*(void (__fastcall **)(LPCWSTR))(*(_QWORD *)v33 + 16LL))(v33);
              }
              (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
            }
          }
        }
        CoTaskMemFree((LPVOID)lpSrc);
      }
    }
  }
  if ( Error < 0 )
  {
    v11 = CFileSource::s_LoadPIDL(a1, L"Slideshow", L"ImagesRoot", 1, 0, (LPITEMIDLIST *)&pidl, 0, v5);
    if ( v11 < 0 )
      return (unsigned int)v11;
    v5 = v36;
  }
  v12 = 0;
  v38 = 0;
  v13 = 1;
  v14 = 0;
LABEL_12:
  v15 = 0;
  v32 = 1;
  do
  {
    LODWORD(pidl1) = v15;
    if ( (int)StringCchPrintfW(v42, 0x10u, L"%s%u", L"Item", pidl1) < 0 )
    {
      v13 = 0;
      v32 = 0;
    }
    else
    {
      lpSrc = 0;
      if ( v14 )
      {
        LODWORD(pidl1) = v14;
        if ( (int)StringCchPrintfW(v43, 0x10u, L"%s%u", L"Slideshow", pidl1) < 0 )
          goto LABEL_24;
        v29 = CFileSource::s_LoadPIDL(a1, v43, v42, 0, pidl, (LPITEMIDLIST *)&lpSrc, &v32, v5);
        v13 = v32;
        v19 = v29;
      }
      else
      {
        v16 = pidl;
        v40 = 0;
        v17 = *(_QWORD *)a1;
        LOWORD(pidl1) = 66;
        v13 = 1;
        v32 = 1;
        v18 = *(int (__fastcall **)(struct ICachedPrivateProfile *, const WCHAR *, unsigned __int16 *, __int64, LPCITEMIDLIST, IStream **))(v17 + 40);
        *(_OWORD *)pstm = 0;
        if ( v18(a1, L"Slideshow", v42, 1, pidl1, pstm) >= 0 )
        {
          v33 = 0;
          v19 = ILLoadFromStreamEx(pstm[1], (LPITEMIDLIST *)&v33);
          if ( v19 >= 0 )
          {
            lpSrc = (LPCWSTR)ILCombine(v16, (LPCITEMIDLIST)v33);
            ILFree((LPITEMIDLIST)v33);
          }
          PropVariantClear((PROPVARIANT *)pstm);
        }
        else
        {
          lpSrc = 0;
          v19 = StringCchPrintfW(v44, 0x40u, L"%s%s", v42, L"Path");
          if ( v19 < 0
            || (v20 = *(_QWORD *)a1,
                v33 = 0,
                v19 = (*(__int64 (__fastcall **)(struct ICachedPrivateProfile *, const WCHAR *, unsigned __int16 *, _QWORD, int, LPCWSTR *))(v20 + 48))(
                        a1,
                        L"Slideshow",
                        v44,
                        0,
                        1,
                        &v33),
                v19 < 0) )
          {
            v13 = 0;
            v32 = 0;
          }
          else
          {
            if ( v36 != 1
              || (LODWORD(ppv) = -1, SHMapUrlToZoneEx(v33, v21, v22, (unsigned int *)&ppv), !(_DWORD)ppv)
              || CFileSource::s_IsUncPathAllowedForThumbnailImage() )
            {
              if ( ExpandEnvironmentStringsW(v33, Dst, 0x104u) > 0x104 )
              {
                v19 = ResultFromKnownLastError();
              }
              else
              {
                ppv = 0;
                v19 = SHCreateItemFromParsingName(Dst, 0, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, &ppv);
                if ( v19 >= 0 )
                {
                  v19 = SHGetIDListFromObject((IUnknown *)ppv, (LPITEMIDLIST *)&lpSrc);
                  (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
                }
              }
            }
            CoTaskMemFree((LPVOID)v33);
          }
        }
      }
      if ( v19 >= 0 )
      {
        if ( !v12
          && (Instance = CRefCountedDPA<CDPAItemIdList<_ITEMIDLIST_ABSOLUTE>>::s_CreateInstance(64),
              v12 = v38,
              Instance < 0)
          || (int)CDPA_Base<_ITEMIDLIST_ABSOLUTE,CTContainer_PolicyCoTaskMem>::AppendPtr(v12, lpSrc) < 0 )
        {
          ILFree((LPITEMIDLIST)lpSrc);
        }
      }
    }
LABEL_24:
    if ( !v13 && (!v14 || v15) )
    {
      v5 = v36;
      ++v14;
      v13 = 1;
      goto LABEL_12;
    }
    v5 = v36;
    ++v15;
  }
  while ( v13 );
  v23 = v41;
  v24 = pidl;
  *v41 = 0;
  v25 = (volatile signed __int32 *)operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
  v26 = v25;
  if ( !v25 )
  {
    v11 = -2147024882;
    goto LABEL_30;
  }
  *v25 = 1;
  *((_QWORD *)v25 + 1) = 0;
  *((_QWORD *)v25 + 2) = 0;
  *((_QWORD *)v25 + 3) = 0;
  v27 = ILClone(v24);
  *((_QWORD *)v26 + 1) = v27;
  if ( v27 )
  {
    _InterlockedIncrement(v26);
    *v23 = (struct CFileSource *)v26;
    v11 = 0;
  }
  else
  {
    v11 = -2147024882;
  }
  CFileSource::Release((CFileSource *)v26);
  if ( v11 >= 0 )
  {
    if ( v12 )
    {
      *((_QWORD *)*v23 + 2) = v12;
      _InterlockedIncrement(v12 + 2);
      goto LABEL_30;
    }
  }
  else
  {
LABEL_30:
    if ( v12 )
      CRefCountedDPA<CDPAItemIdList<_ITEMIDLIST_ABSOLUTE>>::Release((void *)v12);
  }
  ILFree((LPITEMIDLIST)pidl);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180006ae0  mov     [rsp-8+arg_10], rbx
0x180006ae5  push    rbp
0x180006ae6  push    rsi
0x180006ae7  push    rdi
0x180006ae8  push    r12
0x180006aea  push    r13
0x180006aec  push    r14
0x180006aee  push    r15
0x180006af0  lea     rbp, [rsp-280h]
0x180006af8  sub     rsp, 380h
0x180006aff  mov     rax, cs:__security_cookie
0x180006b06  xor     rax, rsp
0x180006b09  mov     [rbp+2B0h+var_40], rax
0x180006b10  xor     eax, eax
0x180006b12  mov     [rsp+3B0h+var_350], r8d
0x180006b17  xor     r12d, r12d
0x180006b1a  mov     [rbp+2B0h+var_328], rax
0x180006b1e  mov     [rdx], r12
0x180006b21  lea     rsi, aSlideshow; "Slideshow"
0x180006b28  mov     rax, [rcx]
0x180006b2b  mov     r13, rcx
0x180006b2e  lea     rcx, [rsp+3B0h+pstm]
0x180006b33  mov     [rbp+2B0h+var_320], rdx
0x180006b37  mov     [rsp+3B0h+ppidl], rcx
0x180006b3c  lea     r14d, [r12+1]
0x180006b41  mov     edi, r8d
0x180006b44  mov     [rsp+3B0h+pidl], r12
0x180006b49  mov     rax, [rax+28h]
0x180006b4d  lea     r8, aImagesrootpidl; "ImagesRootPIDL"
0x180006b54  xorps   xmm0, xmm0
0x180006b57  mov     word ptr [rsp+3B0h+pidl1], 42h ; 'B'
0x180006b5e  mov     r9d, r14d
0x180006b61  mov     rdx, rsi
0x180006b64  mov     rcx, r13
0x180006b67  movups  xmmword ptr [rsp+3B0h+pstm], xmm0
0x180006b6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b71  lea     rcx, aPath; "Path"
0x180006b78  mov     r15d, 104h
0x180006b7e  test    eax, eax
0x180006b80  jns     loc_180006ECC
0x180006b86  mov     [rsp+3B0h+pidl1], rcx
0x180006b8b  lea     r9, aImagesrootpidl; "ImagesRootPIDL"
0x180006b92  lea     rcx, [rbp+2B0h+var_2D0]; unsigned __int16 *
0x180006b96  mov     [rsp+3B0h+pidl], r12
0x180006b9b  lea     r8, aSS_0; "%s%s"
0x180006ba2  lea     edx, [r12+40h]; unsigned __int64
0x180006ba7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180006bac  mov     ebx, eax
0x180006bae  test    eax, eax
0x180006bb0  js      loc_180006C40
0x180006bb6  mov     rax, [r13+0]
0x180006bba  lea     rcx, [rsp+3B0h+lpSrc]
0x180006bbf  mov     [rsp+3B0h+ppidl], rcx
0x180006bc4  lea     r8, [rbp+2B0h+var_2D0]
0x180006bc8  xor     r9d, r9d
0x180006bcb  mov     [rsp+3B0h+lpSrc], r12
0x180006bd0  mov     rdx, rsi
0x180006bd3  mov     dword ptr [rsp+3B0h+pidl1], r14d
0x180006bd8  mov     rax, [rax+30h]
0x180006bdc  mov     rcx, r13
0x180006bdf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006be4  mov     ebx, eax
0x180006be6  test    eax, eax
0x180006be8  js      short loc_180006C40
0x180006bea  cmp     edi, r14d
0x180006bed  jz      loc_180006F13
0x180006bf3  mov     rcx, [rsp+3B0h+lpSrc]; lpSrc
0x180006bf8  lea     rdx, [rbp+2B0h+Dst]; lpDst
0x180006bfc  mov     r8d, r15d; nSize
0x180006bff  call    cs:__imp_ExpandEnvironmentStringsW
0x180006c05  cmp     eax, r15d
0x180006c08  ja      loc_180006F9A
0x180006c0e  lea     r9, [rsp+3B0h+ppv]; ppv
0x180006c13  mov     [rsp+3B0h+ppv], r12
0x180006c18  lea     r8, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x180006c1f  xor     edx, edx; pbc
0x180006c21  lea     rcx, [rbp+2B0h+Dst]; pszPath
0x180006c25  call    cs:__imp_SHCreateItemFromParsingName
0x180006c2b  mov     ebx, eax
0x180006c2d  test    eax, eax
0x180006c2f  jns     loc_180006F47
0x180006c35  mov     rcx, [rsp+3B0h+lpSrc]; pv
0x180006c3a  call    cs:__imp_CoTaskMemFree
0x180006c40  test    ebx, ebx
0x180006c42  jns     short loc_180006C7F
0x180006c44  mov     [rsp+3B0h+var_378], edi; int
0x180006c48  lea     rax, [rsp+3B0h+pidl]
0x180006c4d  mov     [rsp+3B0h+var_380], r12; bool *
0x180006c52  lea     r8, aImagesroot; "ImagesRoot"
0x180006c59  mov     [rsp+3B0h+ppidl], rax; ppidl
0x180006c5e  mov     r9b, r14b; bool
0x180006c61  mov     rdx, rsi; unsigned __int16 *
0x180006c64  mov     [rsp+3B0h+pidl1], r12; pidl1
0x180006c69  mov     rcx, r13; struct ICachedPrivateProfile *
0x180006c6c  call    ?s_LoadPIDL@CFileSource@@CAJPEAUICachedPrivateProfile@@PEBG1_NPEBU_ITEMIDLIST_ABSOLUTE@@PEAPEAU3@PEA_NH@Z; CFileSource::s_LoadPIDL(ICachedPrivateProfile *,ushort const *,ushort const *,bool,_ITEMIDLIST_ABSOLUTE const *,_ITEMIDLIST_ABSOLUTE * *,bool *,int)
0x180006c71  mov     edi, eax
0x180006c73  test    eax, eax
0x180006c75  js      loc_180006E82
0x180006c7b  mov     edi, [rsp+3B0h+var_350]
0x180006c7f  mov     rsi, r12
0x180006c82  mov     [rsp+3B0h+var_340], r12
0x180006c87  mov     bl, r14b
0x180006c8a  mov     r15d, r12d
0x180006c8d  mov     r14d, r12d
0x180006c90  mov     [rsp+3B0h+var_370], bl
0x180006c94  lea     r9, aItem; "Item"
0x180006c9b  mov     dword ptr [rsp+3B0h+pidl1], r14d
0x180006ca0  lea     r8, aSU; "%s%u"
0x180006ca7  mov     edx, 10h; unsigned __int64
0x180006cac  lea     rcx, [rbp+2B0h+var_318]; unsigned __int16 *
0x180006cb0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180006cb5  test    eax, eax
0x180006cb7  js      loc_180006EAE
0x180006cbd  mov     [rsp+3B0h+lpSrc], r12
0x180006cc2  test    r15d, r15d
0x180006cc5  jnz     loc_180007069
0x180006ccb  mov     r12, [rsp+3B0h+pidl]
0x180006cd0  lea     rcx, [rsp+3B0h+pstm]
0x180006cd5  xor     eax, eax
0x180006cd7  mov     [rsp+3B0h+ppidl], rcx
0x180006cdc  mov     [rbp+2B0h+var_328], rax
0x180006ce0  lea     r9d, [r15+1]
0x180006ce4  mov     rax, [r13+0]
0x180006ce8  lea     r8, [rbp+2B0h+var_318]
0x180006cec  xorps   xmm0, xmm0
0x180006cef  mov     word ptr [rsp+3B0h+pidl1], 42h ; 'B'
0x180006cf6  mov     bl, 1
0x180006cf8  lea     rdx, aSlideshow; "Slideshow"
0x180006cff  mov     rcx, r13
0x180006d02  mov     [rsp+3B0h+var_370], bl
0x180006d06  mov     rax, [rax+28h]
0x180006d0a  movups  xmmword ptr [rsp+3B0h+pstm], xmm0
0x180006d0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d14  test    eax, eax
0x180006d16  jns     loc_180006FA6
0x180006d1c  lea     rax, aPath; "Path"
0x180006d23  xor     r12d, r12d
0x180006d26  lea     r9, [rbp+2B0h+var_318]
0x180006d2a  mov     [rsp+3B0h+lpSrc], r12
0x180006d2f  lea     r8, aSS_0; "%s%s"
0x180006d36  mov     [rsp+3B0h+pidl1], rax
0x180006d3b  lea     edx, [r15+40h]; unsigned __int64
0x180006d3f  lea     rcx, [rbp+2B0h+var_2D0]; unsigned __int16 *
0x180006d43  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180006d48  mov     edi, eax
0x180006d4a  test    eax, eax
0x180006d4c  js      loc_18000705D
0x180006d52  mov     rax, [r13+0]
0x180006d56  lea     rcx, [rsp+3B0h+var_368]
0x180006d5b  mov     [rsp+3B0h+ppidl], rcx
0x180006d60  lea     r8, [rbp+2B0h+var_2D0]
0x180006d64  xor     r9d, r9d
0x180006d67  mov     [rsp+3B0h+var_368], r12
0x180006d6c  lea     rdx, aSlideshow; "Slideshow"
0x180006d73  mov     dword ptr [rsp+3B0h+pidl1], 1
0x180006d7b  mov     rax, [rax+30h]
0x180006d7f  mov     rcx, r13
0x180006d82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d87  mov     edi, eax
0x180006d89  test    eax, eax
0x180006d8b  js      loc_18000705D
0x180006d91  cmp     [rsp+3B0h+var_350], 1
0x180006d96  jz      loc_180006FF5
0x180006d9c  mov     rcx, [rsp+3B0h+var_368]; lpSrc
0x180006da1  lea     rdx, [rbp+2B0h+Dst]; lpDst
0x180006da5  mov     edi, 104h
0x180006daa  mov     r8d, edi; nSize
0x180006dad  call    cs:__imp_ExpandEnvironmentStringsW
0x180006db3  cmp     eax, edi
0x180006db5  ja      loc_180007051
0x180006dbb  lea     r9, [rsp+3B0h+ppv]; ppv
0x180006dc0  mov     [rsp+3B0h+ppv], r12
0x180006dc5  lea     r8, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x180006dcc  xor     edx, edx; pbc
0x180006dce  lea     rcx, [rbp+2B0h+Dst]; pszPath
0x180006dd2  call    cs:__imp_SHCreateItemFromParsingName
0x180006dd8  mov     edi, eax
0x180006dda  test    eax, eax
0x180006ddc  jns     loc_180007029
0x180006de2  mov     rcx, [rsp+3B0h+var_368]; pv
0x180006de7  call    cs:__imp_CoTaskMemFree
0x180006ded  test    edi, edi
0x180006def  jns     loc_1800070D2
0x180006df5  test    bl, bl
0x180006df7  jz      loc_180007112
0x180006dfd  mov     edi, [rsp+3B0h+var_350]
0x180006e01  inc     r14d
0x180006e04  test    bl, bl
0x180006e06  jnz     loc_180006C94
0x180006e0c  mov     r14, [rbp+2B0h+var_320]
0x180006e10  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180006e17  mov     rdi, [rsp+3B0h+pidl]
0x180006e1c  mov     ecx, 20h ; ' '; unsigned __int64
0x180006e21  mov     [r14], r12
0x180006e24  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180006e29  mov     rbx, rax
0x180006e2c  test    rax, rax
0x180006e2f  jz      loc_180006EBA
0x180006e35  mov     rcx, rdi; pidl
0x180006e38  mov     dword ptr [rax], 1
0x180006e3e  mov     [rax+8], r12
0x180006e42  mov     [rax+10h], r12
0x180006e46  mov     [rax+18h], r12
0x180006e4a  call    cs:__imp_ILClone
0x180006e50  mov     [rbx+8], rax
0x180006e54  test    rax, rax
0x180006e57  jnz     short loc_180006EC1
0x180006e59  mov     edi, 8007000Eh
0x180006e5e  mov     rcx, rbx; this
0x180006e61  call    ?Release@CFileSource@@QEAAKXZ; CFileSource::Release(void)
0x180006e66  test    edi, edi
0x180006e68  jns     loc_18000712E
0x180006e6e  test    rsi, rsi
0x180006e71  jnz     loc_180007147
0x180006e77  mov     rcx, [rsp+3B0h+pidl]; pidl
0x180006e7c  call    cs:__imp_ILFree
0x180006e82  mov     eax, edi
0x180006e84  mov     rcx, [rbp+2B0h+var_40]
0x180006e8b  xor     rcx, rsp; StackCookie
0x180006e8e  call    __security_check_cookie
0x180006e93  mov     rbx, [rsp+3B0h+arg_10]
0x180006e9b  add     rsp, 380h
0x180006ea2  pop     r15
0x180006ea4  pop     r14
0x180006ea6  pop     r13
0x180006ea8  pop     r12
0x180006eaa  pop     rdi
0x180006eab  pop     rsi
0x180006eac  pop     rbp
0x180006ead  retn
0x180006eae  mov     bl, r12b
0x180006eb1  mov     [rsp+3B0h+var_370], bl
0x180006eb5  jmp     loc_180006DF5
0x180006eba  mov     edi, 8007000Eh
0x180006ebf  jmp     short loc_180006E6E
0x180006ec1  lock inc dword ptr [rbx]
0x180006ec4  mov     [r14], rbx
0x180006ec7  mov     edi, r12d
0x180006eca  jmp     short loc_180006E5E
0x180006ecc  mov     rcx, [rbp+2B0h+pstm+8]; pstm
0x180006ed0  lea     rdx, [rsp+3B0h+var_368]; pidl
0x180006ed5  mov     [rsp+3B0h+var_368], r12
0x180006eda  call    cs:__imp_ILLoadFromStreamEx
0x180006ee0  mov     ebx, eax
0x180006ee2  test    eax, eax
0x180006ee4  js      short loc_180006F03
0x180006ee6  mov     rdx, [rsp+3B0h+var_368]; pidl2
0x180006eeb  xor     ecx, ecx; pidl1
0x180006eed  call    cs:__imp_ILCombine
0x180006ef3  mov     rcx, [rsp+3B0h+var_368]; pidl
0x180006ef8  mov     [rsp+3B0h+pidl], rax
0x180006efd  call    cs:__imp_ILFree
0x180006f03  lea     rcx, [rsp+3B0h+pstm]; pvar
0x180006f08  call    cs:__imp_PropVariantClear
0x180006f0e  jmp     loc_180006C40
0x180006f13  mov     rcx, [rsp+3B0h+lpSrc]; unsigned __int16 *
0x180006f18  lea     r9, [rsp+3B0h+ppv]; unsigned int *
0x180006f1d  mov     dword ptr [rsp+3B0h+ppv], 0FFFFFFFFh
0x180006f25  call    ?SHMapUrlToZoneEx@@YAJPEBGPEAUIUnknown@@KPEAK@Z; SHMapUrlToZoneEx(ushort const *,IUnknown *,ulong,ulong *)
0x180006f2a  cmp     dword ptr [rsp+3B0h+ppv], r12d
0x180006f2f  jz      loc_180006BF3
0x180006f35  call    ?s_IsUncPathAllowedForThumbnailImage@CFileSource@@SAHXZ; CFileSource::s_IsUncPathAllowedForThumbnailImage(void)
0x180006f3a  test    eax, eax
0x180006f3c  jz      loc_180006C35
0x180006f42  jmp     loc_180006BF3
0x180006f47  mov     rcx, [rsp+3B0h+ppv]; struct IShellItem *
0x180006f4c  lea     rdx, [rsp+3B0h+var_368]; struct IShellItem **
0x180006f51  mov     [rsp+3B0h+var_368], r12
0x180006f56  call    ?GetFilteredShellItem@@YAJPEAUIShellItem@@PEAPEAU1@@Z; GetFilteredShellItem(IShellItem *,IShellItem * *)
0x180006f5b  mov     ebx, eax
0x180006f5d  test    eax, eax
0x180006f5f  js      short loc_180006F84
0x180006f61  mov     rcx, [rsp+3B0h+var_368]; punk
0x180006f66  lea     rdx, [rsp+3B0h+pidl]; ppidl
0x180006f6b  call    cs:__imp_SHGetIDListFromObject
0x180006f71  mov     rcx, [rsp+3B0h+var_368]
0x180006f76  mov     ebx, eax
0x180006f78  mov     rax, [rcx]
0x180006f7b  mov     rax, [rax+10h]
0x180006f7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f84  mov     rcx, [rsp+3B0h+ppv]
0x180006f89  mov     rax, [rcx]
0x180006f8c  mov     rax, [rax+10h]
0x180006f90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f95  jmp     loc_180006C35
0x180006f9a  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180006f9f  mov     ebx, eax
0x180006fa1  jmp     loc_180006C35
0x180006fa6  mov     rcx, [rbp+2B0h+pstm+8]; pstm
0x180006faa  lea     rdx, [rsp+3B0h+var_368]; pidl
0x180006faf  mov     [rsp+3B0h+var_368], 0
0x180006fb8  call    cs:__imp_ILLoadFromStreamEx
0x180006fbe  mov     edi, eax
0x180006fc0  test    eax, eax
0x180006fc2  js      short loc_180006FE2
0x180006fc4  mov     rdx, [rsp+3B0h+var_368]; pidl2
0x180006fc9  mov     rcx, r12; pidl1
0x180006fcc  call    cs:__imp_ILCombine
0x180006fd2  mov     rcx, [rsp+3B0h+var_368]; pidl
0x180006fd7  mov     [rsp+3B0h+lpSrc], rax
  ... truncated ...
```
