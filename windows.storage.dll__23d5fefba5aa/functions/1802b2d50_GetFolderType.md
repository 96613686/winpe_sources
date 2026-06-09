# GetFolderType

- ea: `0x1802b2d50`
- end: `0x1802b3496`
- name: `GetFolderType`
- size: `1862`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1802b2c80`

## callees

- `0x180009fc0`
- `0x18000b1a0`
- `0x18003af90`
- `0x18003e0a0`
- `0x180055910`
- `0x180058560`
- `0x1800fd8e0`
- `0x18012b1c0`
- `0x1801b0490`
- `0x1801d8da0`
- `0x180229580`
- `0x18029c6f0`
- `0x1802b2d50`
- `0x1802bbf88`
- `0x1802d26e8`
- `0x180302d20`
- `0x1803b1f60`
- `0x1803b69b9`
- `0x1805242b0`
- `0x1806496a4`
- `0x18067d010`

## import_xrefs

- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRootW` at `0x1802b30ed`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRootW` at `0x1802b30ed`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x1802b3052`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x1802b3052`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1802b32d6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1802b32d6`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1802b339a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1802b339a`
- `PROPSYS!PSPropertyBag_ReadStr` at `0x1802b2f3b`
- `PROPSYS!PSPropertyBag_ReadStr` at `0x1802b318c`
- `PROPSYS!PSPropertyBag_ReadStr` at `0x1802b2f3b`
- `PROPSYS!PSPropertyBag_ReadStr` at `0x1802b318c`
- `PROPSYS!PSPropertyBag_ReadGUID` at `0x1802b2e44`
- `PROPSYS!PSPropertyBag_ReadGUID` at `0x1802b2f94`
- `PROPSYS!PSPropertyBag_ReadGUID` at `0x1802b3272`
- `PROPSYS!PSPropertyBag_ReadGUID` at `0x1802b2e44`
- `PROPSYS!PSPropertyBag_ReadGUID` at `0x1802b2f94`
- `PROPSYS!PSPropertyBag_ReadGUID` at `0x1802b3272`
- `PROPSYS!PSPropertyBag_Delete` at `0x1802b2e83`
- `PROPSYS!PSPropertyBag_Delete` at `0x1802b2e9b`
- `PROPSYS!PSPropertyBag_Delete` at `0x1802b2ec7`
- `PROPSYS!PSPropertyBag_Delete` at `0x1802b2e83`
- `PROPSYS!PSPropertyBag_Delete` at `0x1802b2e9b`
- `PROPSYS!PSPropertyBag_Delete` at `0x1802b2ec7`
- `PROPSYS!PSPropertyBag_WriteGUID` at `0x1802b2eda`
- `PROPSYS!PSPropertyBag_WriteGUID` at `0x1802b33ee`
- `PROPSYS!PSPropertyBag_WriteGUID` at `0x1802b2eda`
- `PROPSYS!PSPropertyBag_WriteGUID` at `0x1802b33ee`
- `api-ms-win-shcore-path-l1-1-0!__imp_PathIsNetworkPathW` at `0x1802b2fcd`
- `api-ms-win-shcore-path-l1-1-0!__imp_PathIsNetworkPathW` at `0x1802b2fcd`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!SHGetViewStatePropertyBag` at `0x1802b2dc4`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!SHGetViewStatePropertyBag` at `0x1802b2dc4`

## pseudocode

```c
GUID *__fastcall GetFolderType(GUID *a1, IUnknown *a2, unsigned __int16 *a3, const ITEMIDLIST *a4)
{
  const unsigned __int16 *v8; // rdx
  GUID v9; // xmm6
  __int64 v10; // rdx
  unsigned __int64 v11; // xmm0_8
  unsigned __int64 v12; // rax
  int DriveNumberW; // eax
  CMountPoint *v14; // rbx
  int v15; // ebx
  int v16; // eax
  struct IShellItem2 *v17; // rdi
  HRESULT (__stdcall *GetPropertyStoreForKeys)(IShellItem2 *, const PROPERTYKEY *, UINT, GETPROPERTYSTOREFLAGS, const IID *const, void **); // rbx
  __int64 v19; // rdi
  bool v20; // r14
  int (__fastcall *v21)(__int64, GUID *, GUID *); // rbx
  GUID v22; // xmm0
  struct IShellItem2 *ppv; // [rsp+38h] [rbp-D0h] BYREF
  IPropertyBag *propBag; // [rsp+40h] [rbp-C8h] BYREF
  PROPVARIANT pvar[3]; // [rsp+48h] [rbp-C0h] BYREF
  GUID Buf1_8; // [rsp+68h] [rbp-A0h] BYREF
  GUID value_8; // [rsp+78h] [rbp-90h] BYREF
  GUID v29; // [rsp+88h] [rbp-80h] BYREF
  WCHAR pszStr2[264]; // [rsp+98h] [rbp-70h] BYREF
  WCHAR String2[264]; // [rsp+2A8h] [rbp+1A0h] BYREF

  *a1 = FOLDERTYPEID_Invalid;
  propBag = 0;
  SHGetViewStatePropertyBag(a4, L"Shell", 5u, &GUID_55272a00_42cb_11ce_8135_00aa004bb851, (void **)&propBag);
  if ( !propBag )
    goto LABEL_10;
  Buf1_8 = FOLDERTYPEID_Invalid;
  if ( Windows::Internal::PerFolderRoots::IsUnderPerFolderRoot((Windows::Internal::PerFolderRoots *)a3, v8) )
  {
    winrt::param::hstring::hstring((winrt::param::hstring *)pvar, a3);
    ppv = (struct IShellItem2 *)pvar;
    winrt::impl::call_factory<winrt::Windows::Internal::Storage::PerFolderRootManager,winrt::Windows::Internal::Storage::IPerFolderRootManagerStatics,_lambda_e1fe1346832bb179b80bcbcd404a46b3_>(
      &v29,
      &ppv);
    Buf1_8 = v29;
  }
  value_8 = 0;
  v9 = FOLDERTYPEID_Invalid;
  if ( PSPropertyBag_ReadGUID(propBag, L"PerFolderRootDerivedFolderType", &value_8) < 0 )
    value_8 = FOLDERTYPEID_Invalid;
  if ( memcmp_0(&Buf1_8, &value_8, 0x10u) )
  {
    PSPropertyBag_Delete(propBag, L"SniffedFolderType");
    PSPropertyBag_Delete(propBag, L"FolderType");
    if ( !memcmp_0(&FOLDERTYPEID_Invalid, &Buf1_8, 0x10u) )
    {
      PSPropertyBag_Delete(propBag, L"PerFolderRootDerivedFolderType");
    }
    else
    {
      PSPropertyBag_WriteGUID(propBag, L"PerFolderRootDerivedFolderType", &Buf1_8);
      *a1 = Buf1_8;
    }
LABEL_10:
    v9 = FOLDERTYPEID_Invalid;
  }
  v10 = *(_QWORD *)&v9.Data1;
  v11 = _mm_srli_si128((__m128i)v9, 8).m128i_u64[0];
  v12 = v11;
  if ( *(_QWORD *)&v9.Data1 == *(_QWORD *)&a1->Data1 )
  {
    if ( v11 == *(_QWORD *)a1->Data4 && propBag )
    {
      pszStr2[0] = 0;
      PSPropertyBag_ReadStr(propBag, L"FolderType", pszStr2, 260);
      if ( pszStr2[0] )
        SHGetFolderTypeFromCanonicalName(pszStr2);
      v9 = FOLDERTYPEID_Invalid;
      v12 = *(_QWORD *)FOLDERTYPEID_Invalid.Data4;
      v10 = *(_QWORD *)&FOLDERTYPEID_Invalid.Data1;
    }
    if ( v10 == *(_QWORD *)&a1->Data1 )
    {
      if ( v12 == *(_QWORD *)a1->Data4 && propBag )
      {
        Buf1_8 = v9;
        if ( PSPropertyBag_ReadGUID(propBag, L"PerFolderRootDerivedFolderType", &Buf1_8) >= 0 )
          *a1 = Buf1_8;
        v10 = *(_QWORD *)&FOLDERTYPEID_Invalid.Data1;
        v12 = *(_QWORD *)FOLDERTYPEID_Invalid.Data4;
      }
      if ( v10 == *(_QWORD *)&a1->Data1 )
      {
        if ( v12 == *(_QWORD *)a1->Data4 )
        {
          if ( PathIsNetworkPathW(a3) )
          {
            ppv = 0;
            if ( SHCreateItemFromIDList(a4, &GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93, (void **)&ppv) >= 0 )
            {
              if ( !(unsigned int)CachedIsOfflineAvailable(ppv, propBag) )
                *a1 = FOLDERTYPEID_Generic;
              ((void (__fastcall *)(struct IShellItem2 *))ppv->lpVtbl->Release)(ppv);
            }
          }
          v10 = *(_QWORD *)&FOLDERTYPEID_Invalid.Data1;
          v12 = *(_QWORD *)FOLDERTYPEID_Invalid.Data4;
        }
        if ( v10 == *(_QWORD *)&a1->Data1 )
        {
          if ( v12 == *(_QWORD *)a1->Data4 )
          {
            ppv = 0;
            DriveNumberW = PathGetDriveNumberW(a3);
            if ( (int)CMountPoint::GetMountPoint(DriveNumberW, (struct CMountPoint **)&ppv) >= 0 )
            {
              v14 = (CMountPoint *)ppv;
              if ( ((unsigned int (__fastcall *)(struct IShellItem2 *))ppv->lpVtbl[2].GetFileTime)(ppv)
                || (*(unsigned int (__fastcall **)(CMountPoint *))(*(_QWORD *)v14 + 368LL))(v14)
                || (*(unsigned int (__fastcall **)(CMountPoint *))(*(_QWORD *)v14 + 392LL))(v14) )
              {
                *a1 = FOLDERTYPEID_Generic;
              }
              CMountPoint::Release(v14);
            }
            v10 = *(_QWORD *)&FOLDERTYPEID_Invalid.Data1;
            v12 = *(_QWORD *)FOLDERTYPEID_Invalid.Data4;
          }
          if ( v10 == *(_QWORD *)&a1->Data1 )
          {
            if ( v12 == *(_QWORD *)a1->Data4 )
            {
              ppv = 0;
              if ( !PathIsRootW(a3) && (int)GetCachedIniForFolder(a2, a4, a3, (void **)&ppv) >= 0 )
              {
                if ( (unsigned int)GetFolderString(
                                     (_DWORD)ppv,
                                     (unsigned int)L"ViewState",
                                     (unsigned int)L"FolderType",
                                     (unsigned int)pszStr2,
                                     260) )
                  SHGetFolderTypeFromCanonicalName(pszStr2);
                ((void (__fastcall *)(struct IShellItem2 *))ppv->lpVtbl->Release)(ppv);
              }
              v10 = *(_QWORD *)&FOLDERTYPEID_Invalid.Data1;
              v12 = *(_QWORD *)FOLDERTYPEID_Invalid.Data4;
            }
            if ( v10 == *(_QWORD *)&a1->Data1 && v12 == *(_QWORD *)a1->Data4 && propBag )
            {
              pszStr2[0] = 0;
              PSPropertyBag_ReadStr(propBag, L"SniffedFolderType", pszStr2, 260);
              if ( pszStr2[0] )
                SHGetFolderTypeFromCanonicalName(pszStr2);
              v10 = *(_QWORD *)&FOLDERTYPEID_Invalid.Data1;
              v12 = *(_QWORD *)FOLDERTYPEID_Invalid.Data4;
            }
          }
        }
      }
    }
  }
  if ( v10 == *(_QWORD *)&a1->Data1 && v12 == *(_QWORD *)a1->Data4 )
  {
    v15 = 0;
    while ( 1 )
    {
      if ( (int)SHGetFolderPathEx((unsigned int)off_180825780[3 * v15], 0x4000, 0, (unsigned int)String2, 260) >= 0 )
      {
        v16 = PathComparePaths(String2, a3);
        v10 = (4 * (~LOBYTE(off_180825780[3 * v15 + 2]) & 2)) | 2u;
        if ( ((unsigned int)v10 & v16) != 0 )
          break;
      }
      if ( (unsigned int)++v15 >= 9 )
        goto LABEL_62;
    }
    *a1 = *off_180825780[3 * v15 + 1];
  }
LABEL_62:
  LOBYTE(v10) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_DefaultDownloadsSorting>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_DefaultDownloadsSorting>::GetImpl'::`2'::impl,
    v10);
  if ( propBag )
  {
    Buf1_8 = FOLDERTYPEID_Invalid;
    if ( PSPropertyBag_ReadGUID(propBag, L"KnownFolderDerivedFolderType", &Buf1_8) >= 0 )
      *a1 = Buf1_8;
    if ( !memcmp_0(&FOLDERTYPEID_Invalid, &Buf1_8, 0x10u) )
    {
      ppv = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
      if ( CoCreateInstance(
             &CLSID_KnownFolderManager,
             0,
             1u,
             &GUID_8be2d872_86aa_4d47_b776_32cca40c7018,
             (LPVOID *)&ppv) >= 0 )
      {
        v17 = ppv;
        *(_QWORD *)&v29.Data1 = 0;
        GetPropertyStoreForKeys = ppv->lpVtbl->GetPropertyStoreForKeys;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v29);
        if ( ((int (__fastcall *)(struct IShellItem2 *, unsigned __int16 *, __int64, GUID *))GetPropertyStoreForKeys)(
               v17,
               a3,
               1,
               &v29) >= 0 )
        {
          v19 = *(_QWORD *)&v29.Data1;
          *(_QWORD *)&value_8.Data1 = 0;
          v20 = 0;
          v21 = ***(int (__fastcall ****)(__int64, GUID *, GUID *))&v29.Data1;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&value_8);
          if ( v21(v19, &GUID_0e207e42_dc38_440d_9b00_2e8cf0e23c8d, &value_8) >= 0 )
          {
            LOWORD(pvar[0]) = 0;
            if ( (*(int (__fastcall **)(_QWORD, const wchar_t *, PROPVARIANT *))(**(_QWORD **)&value_8.Data1 + 24LL))(
                   *(_QWORD *)&value_8.Data1,
                   L"SniffPolicy",
                   pvar) >= 0 )
              v20 = wcscmp_0((const wchar_t *)pvar[1], L"override") == 0;
            PropVariantClear(pvar);
          }
          if ( (*(_QWORD *)&a1->Data1 == *(_QWORD *)&FOLDERTYPEID_Invalid.Data1
             && *(_QWORD *)a1->Data4 == *(_QWORD *)FOLDERTYPEID_Invalid.Data4
             || v20)
            && (*(int (__fastcall **)(_QWORD, GUID *))(**(_QWORD **)&v29.Data1 + 72LL))(*(_QWORD *)&v29.Data1, &Buf1_8) >= 0 )
          {
            PSPropertyBag_WriteGUID(propBag, L"KnownFolderDerivedFolderType", &Buf1_8);
            *a1 = Buf1_8;
          }
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&value_8);
        }
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v29);
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
    }
  }
  SafeRelease<IFilterCreationCallback>(&propBag);
  if ( *(_QWORD *)&FOLDERTYPEID_Invalid.Data1 == *(_QWORD *)&a1->Data1
    && *(_QWORD *)FOLDERTYPEID_Invalid.Data4 == *(_QWORD *)a1->Data4 )
  {
    if ( (unsigned int)ShouldUseStorageProviderViews(a3) )
      v22 = FOLDERTYPEID_StorageProviderGeneric;
    else
      v22 = FOLDERTYPEID_Generic;
    *a1 = v22;
  }
  return a1;
}

```

## disassembly

```asm
0x1802b2d50  mov     rax, rsp
0x1802b2d53  mov     [rax+8], rbx
0x1802b2d57  push    rbp
0x1802b2d58  push    rsi
0x1802b2d59  push    rdi
0x1802b2d5a  push    r12
0x1802b2d5c  push    r13
0x1802b2d5e  push    r14
0x1802b2d60  push    r15
0x1802b2d62  lea     rbp, [rax-408h]
0x1802b2d69  sub     rsp, 4D0h
0x1802b2d70  movaps  xmmword ptr [rax-48h], xmm6
0x1802b2d74  mov     rax, cs:__security_cookie
0x1802b2d7b  xor     rax, rsp
0x1802b2d7e  mov     [rbp+400h+var_50], rax
0x1802b2d85  movups  xmm0, xmmword ptr cs:FOLDERTYPEID_Invalid.Data1
0x1802b2d8c  mov     rdi, r9
0x1802b2d8f  lea     rax, [rsp+500h+propBag]
0x1802b2d94  xor     r12d, r12d
0x1802b2d97  mov     [rsp+500h+ppv], rax; ppv
0x1802b2d9c  movdqu  xmmword ptr [rcx], xmm0
0x1802b2da0  mov     r15, r8
0x1802b2da3  mov     [rsp+500h+propBag], r12
0x1802b2da8  mov     r14, rdx
0x1802b2dab  lea     r9, _GUID_55272a00_42cb_11ce_8135_00aa004bb851; riid
0x1802b2db2  mov     rsi, rcx
0x1802b2db5  lea     r8d, [r12+5]; dwFlags
0x1802b2dba  mov     rcx, rdi; pidl
0x1802b2dbd  lea     rdx, pszBagName; "Shell"
0x1802b2dc4  call    cs:__imp_SHGetViewStatePropertyBag
0x1802b2dcb  nop     dword ptr [rax+rax+00h]
0x1802b2dd0  lea     rbx, aPerfolderrootd; "PerFolderRootDerivedFolderType"
0x1802b2dd7  lea     r13d, [r12+10h]
0x1802b2ddc  cmp     [rsp+500h+propBag], r12
0x1802b2de1  jz      loc_1802B2EEF
0x1802b2de7  movups  xmm0, xmmword ptr cs:FOLDERTYPEID_Invalid.Data1
0x1802b2dee  mov     rcx, r15; this
0x1802b2df1  movdqu  [rsp+500h+Buf1+8], xmm0
0x1802b2df7  call    ?IsUnderPerFolderRoot@PerFolderRoots@Internal@Windows@@YA_NPEBG@Z; Windows::Internal::PerFolderRoots::IsUnderPerFolderRoot(ushort const *)
0x1802b2dfc  test    al, al
0x1802b2dfe  jz      short loc_1802B2E2F
0x1802b2e00  mov     rdx, r15; unsigned __int16 *
0x1802b2e03  lea     rcx, [rsp+500h+pvar]; this
0x1802b2e08  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x1802b2e0d  lea     rax, [rsp+500h+pvar]
0x1802b2e12  lea     rdx, [rsp+500h+var_4D0]
0x1802b2e17  mov     [rsp+500h+var_4D0], rax
0x1802b2e1c  lea     rcx, [rbp+400h+var_480]
0x1802b2e20  call    ??$call_factory@UPerFolderRootManager@Storage@Internal@Windows@winrt@@UIPerFolderRootManagerStatics@2345@V_lambda_e1fe1346832bb179b80bcbcd404a46b3_@@@impl@winrt@@YA?A_P$$QEAV_lambda_e1fe1346832bb179b80bcbcd404a46b3_@@@Z
0x1802b2e25  movaps  xmm0, [rbp+400h+var_480]
0x1802b2e29  movdqa  [rsp+500h+Buf1+8], xmm0
0x1802b2e2f  mov     rcx, [rsp+500h+propBag]; propBag
0x1802b2e34  lea     r8, [rsp+500h+value+8]; value
0x1802b2e39  xorps   xmm0, xmm0
0x1802b2e3c  mov     rdx, rbx; propName
0x1802b2e3f  movups  xmmword ptr [rsp+500h+value+8], xmm0
0x1802b2e44  call    cs:__imp_PSPropertyBag_ReadGUID
0x1802b2e4b  nop     dword ptr [rax+rax+00h]
0x1802b2e50  movups  xmm6, xmmword ptr cs:FOLDERTYPEID_Invalid.Data1
0x1802b2e57  test    eax, eax
0x1802b2e59  jns     short loc_1802B2E61
0x1802b2e5b  movdqu  xmmword ptr [rsp+500h+value+8], xmm6
0x1802b2e61  mov     r8, r13; Size
0x1802b2e64  lea     rdx, [rsp+500h+value+8]; Buf2
0x1802b2e69  lea     rcx, [rsp+500h+Buf1+8]; Buf1
0x1802b2e6e  call    memcmp_0
0x1802b2e73  test    eax, eax
0x1802b2e75  jz      short loc_1802B2EF6
0x1802b2e77  mov     rcx, [rsp+500h+propBag]; propBag
0x1802b2e7c  lea     rdx, aSniffedfoldert; "SniffedFolderType"
0x1802b2e83  call    cs:__imp_PSPropertyBag_Delete
0x1802b2e8a  nop     dword ptr [rax+rax+00h]
0x1802b2e8f  mov     rcx, [rsp+500h+propBag]; propBag
0x1802b2e94  lea     rdx, aFoldertype; "FolderType"
0x1802b2e9b  call    cs:__imp_PSPropertyBag_Delete
0x1802b2ea2  nop     dword ptr [rax+rax+00h]
0x1802b2ea7  mov     r8, r13; Size
0x1802b2eaa  lea     rdx, [rsp+500h+Buf1+8]; Buf2
0x1802b2eaf  lea     rcx, FOLDERTYPEID_Invalid; Buf1
0x1802b2eb6  call    memcmp_0
0x1802b2ebb  mov     rcx, [rsp+500h+propBag]; propBag
0x1802b2ec0  mov     rdx, rbx; propName
0x1802b2ec3  test    eax, eax
0x1802b2ec5  jnz     short loc_1802B2ED5
0x1802b2ec7  call    cs:__imp_PSPropertyBag_Delete
0x1802b2ece  nop     dword ptr [rax+rax+00h]
0x1802b2ed3  jmp     short loc_1802B2EEF
0x1802b2ed5  lea     r8, [rsp+500h+Buf1+8]; value
0x1802b2eda  call    cs:__imp_PSPropertyBag_WriteGUID
0x1802b2ee1  nop     dword ptr [rax+rax+00h]
0x1802b2ee6  movaps  xmm0, [rsp+500h+Buf1+8]
0x1802b2eeb  movdqu  xmmword ptr [rsi], xmm0
0x1802b2eef  movups  xmm6, xmmword ptr cs:FOLDERTYPEID_Invalid.Data1
0x1802b2ef6  movdqa  xmm0, xmm6
0x1802b2efa  movq    rdx, xmm6
0x1802b2eff  mov     r13d, 104h
0x1802b2f05  psrldq  xmm0, 8
0x1802b2f0a  movq    rax, xmm0
0x1802b2f0f  cmp     rdx, [rsi]
0x1802b2f12  jnz     loc_1802B31B9
0x1802b2f18  cmp     rax, [rsi+8]
0x1802b2f1c  jnz     short loc_1802B2F6D
0x1802b2f1e  mov     rcx, [rsp+500h+propBag]; propBag
0x1802b2f23  test    rcx, rcx
0x1802b2f26  jz      short loc_1802B2F6D
0x1802b2f28  mov     r9d, r13d; characterCount
0x1802b2f2b  mov     [rbp+400h+pszStr2], r12w
0x1802b2f30  lea     r8, [rbp+400h+pszStr2]; value
0x1802b2f34  lea     rdx, aFoldertype; "FolderType"
0x1802b2f3b  call    cs:__imp_PSPropertyBag_ReadStr
0x1802b2f42  nop     dword ptr [rax+rax+00h]
0x1802b2f47  cmp     [rbp+400h+pszStr2], r12w
0x1802b2f4c  jz      short loc_1802B2F5A
0x1802b2f4e  mov     rdx, rsi
0x1802b2f51  lea     rcx, [rbp+400h+pszStr2]; pszStr2
0x1802b2f55  call    SHGetFolderTypeFromCanonicalName
0x1802b2f5a  movups  xmm6, xmmword ptr cs:FOLDERTYPEID_Invalid.Data1
0x1802b2f61  mov     rax, qword ptr cs:FOLDERTYPEID_Invalid.Data4
0x1802b2f68  movq    rdx, xmm6
0x1802b2f6d  cmp     rdx, [rsi]
0x1802b2f70  jnz     loc_1802B31B9
0x1802b2f76  cmp     rax, [rsi+8]
0x1802b2f7a  jnz     short loc_1802B2FBB
0x1802b2f7c  mov     rcx, [rsp+500h+propBag]; propBag
0x1802b2f81  test    rcx, rcx
0x1802b2f84  jz      short loc_1802B2FBB
0x1802b2f86  lea     r8, [rsp+500h+Buf1+8]; value
0x1802b2f8b  mov     rdx, rbx; propName
0x1802b2f8e  movdqu  [rsp+500h+Buf1+8], xmm6
0x1802b2f94  call    cs:__imp_PSPropertyBag_ReadGUID
0x1802b2f9b  nop     dword ptr [rax+rax+00h]
0x1802b2fa0  test    eax, eax
0x1802b2fa2  js      short loc_1802B2FAD
0x1802b2fa4  movups  xmm0, [rsp+500h+Buf1+8]
0x1802b2fa9  movdqu  xmmword ptr [rsi], xmm0
0x1802b2fad  mov     rdx, qword ptr cs:FOLDERTYPEID_Invalid.Data1
0x1802b2fb4  mov     rax, qword ptr cs:FOLDERTYPEID_Invalid.Data4
0x1802b2fbb  cmp     rdx, [rsi]
0x1802b2fbe  jnz     loc_1802B31B9
0x1802b2fc4  cmp     rax, [rsi+8]
0x1802b2fc8  jnz     short loc_1802B3037
0x1802b2fca  mov     rcx, r15; pszPath
0x1802b2fcd  call    cs:__imp_PathIsNetworkPathW
0x1802b2fd4  nop     dword ptr [rax+rax+00h]
0x1802b2fd9  test    eax, eax
0x1802b2fdb  jz      short loc_1802B3029
0x1802b2fdd  lea     r8, [rsp+500h+var_4D0]; ppv
0x1802b2fe2  mov     [rsp+500h+var_4D0], r12
0x1802b2fe7  lea     rdx, _GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93; riid
0x1802b2fee  mov     rcx, rdi; pidl
0x1802b2ff1  call    SHCreateItemFromIDList
0x1802b2ff6  test    eax, eax
0x1802b2ff8  js      short loc_1802B3029
0x1802b2ffa  mov     rdx, [rsp+500h+propBag]; struct IPropertyBag *
0x1802b2fff  mov     rcx, [rsp+500h+var_4D0]; struct IShellItem2 *
0x1802b3004  call    ?CachedIsOfflineAvailable@@YAHPEAUIShellItem2@@PEAUIPropertyBag@@@Z; CachedIsOfflineAvailable(IShellItem2 *,IPropertyBag *)
0x1802b3009  test    eax, eax
0x1802b300b  jnz     short loc_1802B3018
0x1802b300d  movups  xmm0, xmmword ptr cs:FOLDERTYPEID_Generic.Data1
0x1802b3014  movdqu  xmmword ptr [rsi], xmm0
0x1802b3018  mov     rcx, [rsp+500h+var_4D0]
0x1802b301d  mov     rax, [rcx]
0x1802b3020  mov     rax, [rax+10h]
0x1802b3024  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802b3029  mov     rdx, qword ptr cs:FOLDERTYPEID_Invalid.Data1
0x1802b3030  mov     rax, qword ptr cs:FOLDERTYPEID_Invalid.Data4
0x1802b3037  cmp     rdx, [rsi]
0x1802b303a  jnz     loc_1802B31B9
0x1802b3040  cmp     rax, [rsi+8]
0x1802b3044  jnz     loc_1802B30D6
0x1802b304a  mov     rcx, r15; pszPath
0x1802b304d  mov     [rsp+500h+var_4D0], r12
0x1802b3052  call    cs:__imp_PathGetDriveNumberW
0x1802b3059  nop     dword ptr [rax+rax+00h]
0x1802b305e  mov     ecx, eax; int
0x1802b3060  lea     rdx, [rsp+500h+var_4D0]; struct CMountPoint **
0x1802b3065  call    ?GetMountPoint@CMountPoint@@SAJHPEAPEAV1@@Z; CMountPoint::GetMountPoint(int,CMountPoint * *)
0x1802b306a  test    eax, eax
0x1802b306c  js      short loc_1802B30C8
0x1802b306e  mov     rbx, [rsp+500h+var_4D0]
0x1802b3073  mov     rcx, rbx
0x1802b3076  mov     rax, [rbx]
0x1802b3079  mov     rax, [rax+1C8h]
0x1802b3080  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802b3085  test    eax, eax
0x1802b3087  jnz     short loc_1802B30B5
0x1802b3089  mov     rax, [rbx]
0x1802b308c  mov     rcx, rbx
0x1802b308f  mov     rax, [rax+170h]
0x1802b3096  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802b309b  test    eax, eax
0x1802b309d  jnz     short loc_1802B30B5
0x1802b309f  mov     rax, [rbx]
0x1802b30a2  mov     rcx, rbx
0x1802b30a5  mov     rax, [rax+188h]
0x1802b30ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802b30b1  test    eax, eax
0x1802b30b3  jz      short loc_1802B30C0
0x1802b30b5  movups  xmm0, xmmword ptr cs:FOLDERTYPEID_Generic.Data1
0x1802b30bc  movdqu  xmmword ptr [rsi], xmm0
0x1802b30c0  mov     rcx, rbx; this
0x1802b30c3  call    ?Release@CMountPoint@@QEAAKXZ; CMountPoint::Release(void)
0x1802b30c8  mov     rdx, qword ptr cs:FOLDERTYPEID_Invalid.Data1
0x1802b30cf  mov     rax, qword ptr cs:FOLDERTYPEID_Invalid.Data4
0x1802b30d6  cmp     rdx, [rsi]
0x1802b30d9  jnz     loc_1802B31B9
0x1802b30df  cmp     rax, [rsi+8]
0x1802b30e3  jnz     short loc_1802B3164
0x1802b30e5  mov     rcx, r15; pszPath
0x1802b30e8  mov     [rsp+500h+var_4D0], r12
0x1802b30ed  call    cs:__imp_PathIsRootW
0x1802b30f4  nop     dword ptr [rax+rax+00h]
0x1802b30f9  test    eax, eax
0x1802b30fb  jnz     short loc_1802B3156
0x1802b30fd  lea     r9, [rsp+500h+var_4D0]; ppv
0x1802b3102  mov     r8, r15; pszName
0x1802b3105  mov     rdx, rdi; pidl
0x1802b3108  mov     rcx, r14; punk
0x1802b310b  call    GetCachedIniForFolder
0x1802b3110  test    eax, eax
0x1802b3112  js      short loc_1802B3156
0x1802b3114  mov     rcx, [rsp+500h+var_4D0]
0x1802b3119  lea     r9, [rbp+400h+pszStr2]
0x1802b311d  lea     r8, aFoldertype; "FolderType"
0x1802b3124  mov     dword ptr [rsp+500h+ppv], r13d
0x1802b3129  lea     rdx, aViewstate; "ViewState"
0x1802b3130  call    GetFolderString
0x1802b3135  test    eax, eax
0x1802b3137  jz      short loc_1802B3145
0x1802b3139  mov     rdx, rsi
0x1802b313c  lea     rcx, [rbp+400h+pszStr2]; pszStr2
0x1802b3140  call    SHGetFolderTypeFromCanonicalName
0x1802b3145  mov     rcx, [rsp+500h+var_4D0]
0x1802b314a  mov     rax, [rcx]
0x1802b314d  mov     rax, [rax+10h]
0x1802b3151  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802b3156  mov     rdx, qword ptr cs:FOLDERTYPEID_Invalid.Data1
0x1802b315d  mov     rax, qword ptr cs:FOLDERTYPEID_Invalid.Data4
0x1802b3164  cmp     rdx, [rsi]
0x1802b3167  jnz     short loc_1802B31B9
0x1802b3169  cmp     rax, [rsi+8]
0x1802b316d  jnz     short loc_1802B31B9
0x1802b316f  mov     rcx, [rsp+500h+propBag]; propBag
0x1802b3174  test    rcx, rcx
0x1802b3177  jz      short loc_1802B31B9
0x1802b3179  mov     r9d, r13d; characterCount
0x1802b317c  mov     [rbp+400h+pszStr2], r12w
0x1802b3181  lea     r8, [rbp+400h+pszStr2]; value
0x1802b3185  lea     rdx, aSniffedfoldert; "SniffedFolderType"
0x1802b318c  call    cs:__imp_PSPropertyBag_ReadStr
0x1802b3193  nop     dword ptr [rax+rax+00h]
0x1802b3198  cmp     [rbp+400h+pszStr2], r12w
0x1802b319d  jz      short loc_1802B31AB
0x1802b319f  mov     rdx, rsi
0x1802b31a2  lea     rcx, [rbp+400h+pszStr2]; pszStr2
0x1802b31a6  call    SHGetFolderTypeFromCanonicalName
0x1802b31ab  mov     rdx, qword ptr cs:FOLDERTYPEID_Invalid.Data1
0x1802b31b2  mov     rax, qword ptr cs:FOLDERTYPEID_Invalid.Data4
0x1802b31b9  mov     r14d, 1
0x1802b31bf  cmp     rdx, [rsi]
0x1802b31c2  jnz     short loc_1802B323C
0x1802b31c4  cmp     rax, [rsi+8]
0x1802b31c8  jnz     short loc_1802B323C
0x1802b31ca  mov     ebx, r12d
0x1802b31cd  lea     r13, off_180825780
0x1802b31d4  movsxd  rax, ebx
0x1802b31d7  lea     r9, [rbp+400h+String2]
0x1802b31de  xor     r8d, r8d
0x1802b31e1  mov     dword ptr [rsp+500h+ppv], 104h
0x1802b31e9  mov     edx, 4000h
0x1802b31ee  lea     rdi, [rax+rax*2]
0x1802b31f2  mov     rcx, [r13+rdi*8+0]
0x1802b31f7  call    SHGetFolderPathEx
0x1802b31fc  test    eax, eax
0x1802b31fe  js      short loc_1802B3226
0x1802b3200  mov     rdx, r15; lpString1
0x1802b3203  lea     rcx, [rbp+400h+String2]; lpString2
0x1802b320a  call    PathComparePaths
0x1802b320f  mov     cl, [r13+rdi*8+10h]
0x1802b3214  not     cl
0x1802b3216  movzx   edx, cl
0x1802b3219  and     edx, 2
0x1802b321c  shl     edx, 2
0x1802b321f  or      edx, 2
0x1802b3222  test    eax, edx
0x1802b3224  jnz     short loc_1802B3230
0x1802b3226  add     ebx, r14d
0x1802b3229  cmp     ebx, 9
0x1802b322c  jb      short loc_1802B31D4
0x1802b322e  jmp     short loc_1802B323C
0x1802b3230  mov     rax, [r13+rdi*8+8]
0x1802b3235  movups  xmm0, xmmword ptr [rax]
0x1802b3238  movdqu  xmmword ptr [rsi], xmm0
0x1802b323c  mov     dl, r14b
0x1802b323f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DefaultDownloadsSorting@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DefaultDownloadsSorting@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DefaultDownloadsSorting> `wil::Feature<__WilFeatureTraits_Feature_DefaultDownloadsSorting>::GetImpl(void)'::`2'::impl
0x1802b3246  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_DefaultDownloadsSorting@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DefaultDownloadsSorting>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1802b324b  mov     rcx, [rsp+500h+propBag]; propBag
0x1802b3250  test    rcx, rcx
0x1802b3253  jz      loc_1802B3420
0x1802b3259  movups  xmm0, xmmword ptr cs:FOLDERTYPEID_Invalid.Data1
  ... truncated ...
```
