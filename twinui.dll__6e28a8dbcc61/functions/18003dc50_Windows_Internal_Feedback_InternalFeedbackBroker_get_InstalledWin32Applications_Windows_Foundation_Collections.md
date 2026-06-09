# Windows::Internal::Feedback::InternalFeedbackBroker::get_InstalledWin32Applications(Windows::Foundation::Collections::IVectorView<Windows::Internal::Feedback::FeedbackItem *> * *)

- ea: `0x18003dc50`
- end: `0x18003e383`
- name: `?get_InstalledWin32Applications@InternalFeedbackBroker@Feedback@Internal@Windows@@UEAAJPEAPEAU?$IVectorView@PEAVFeedbackItem@Feedback@Internal@Windows@@@Collections@Foundation@4@@Z`
- size: `1843`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x180008acc`
- `0x18000b7e8`
- `0x18000d50c`
- `0x18003c5e4`
- `0x18003dbb0`
- `0x18003dc50`
- `0x18003e38c`
- `0x18003e64c`
- `0x1800e9c10`
- `0x18013d354`
- `0x1803a3010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e058`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e095`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e0cc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e102`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e058`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e095`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e0cc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e102`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003e06d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003e0a6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003e0dd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003e113`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003e06d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003e0a6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003e0dd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003e113`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003df4e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003e1cb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003df4e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003e1cb`
- `AEPIC!PicFreeFileInfo` at `0x18003e150`
- `AEPIC!PicFreeFileInfo` at `0x18003e150`
- `AEPIC!PicRetrieveFileInfo` at `0x18003dfdb`
- `AEPIC!PicRetrieveFileInfo` at `0x18003dfdb`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x18003e1bb`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x18003e1bb`
- `api-ms-win-shell-namespace-l1-1-0!SHCreateItemWithParent` at `0x18003df29`
- `api-ms-win-shell-namespace-l1-1-0!SHCreateItemWithParent` at `0x18003df29`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18003df97`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18003df97`
- `api-ms-win-storage-exports-internal-l1-1-0!SHGetKnownFolderItem` at `0x18003dcd7`
- `api-ms-win-storage-exports-internal-l1-1-0!SHGetKnownFolderItem` at `0x18003dcd7`

## string_xrefs

- `0x18003dd63`: `shell\twinui\feedback\lib\feedbackbroker.cpp`
- `0x18003ddcc`: `shell\twinui\feedback\lib\feedbackbroker.cpp`
- `0x18003de69`: `shell\twinui\feedback\lib\feedbackbroker.cpp`
- `0x18003e292`: `shell\twinui\feedback\lib\feedbackbroker.cpp`
- `0x18003e2fe`: `shell\twinui\feedback\lib\feedbackbroker.cpp`
- `0x18003e327`: `shell\twinui\feedback\lib\feedbackbroker.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall Windows::Internal::Feedback::InternalFeedbackBroker::get_InstalledWin32Applications(
        Windows::Internal::Feedback *a1,
        __int64 a2)
{
  __int64 v2; // rsi
  int HasPackageQueryCapability; // ebx
  __int64 v4; // rcx
  int v5; // eax
  HRESULT v6; // eax
  void *v7; // rdi
  __int64 (__fastcall *v8)(void *, _QWORD, const GUID *, GUID *); // rbx
  int v9; // eax
  IShellFolder *v10; // rdi
  HRESULT (__stdcall *EnumObjects)(IShellFolder *, HWND, SHCONTF, IEnumIDList **); // rbx
  int v12; // eax
  __int64 v13; // rcx
  __int64 v14; // rcx
  IShellFolder *v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // rcx
  void *v18; // rcx
  __int64 v20; // rcx
  __int64 v21; // rcx
  IShellFolder *v22; // rcx
  void *v23; // rbx
  int (__fastcall *v24)(void *, const PROPERTYKEY *, LPVOID *); // rdi
  const WCHAR *FileNameW; // r15
  LPVOID v26; // rbx
  Windows::Internal::Feedback *v27; // rcx
  HRESULT String; // ebx
  const WCHAR **v29; // rbx
  HSTRING *v30; // rcx
  Windows::Internal::Feedback::InternalFeedbackItem *v31; // rax
  HSTRING *v32; // rsi
  const WCHAR *v33; // r13
  const WCHAR *v34; // r12
  const WCHAR *v35; // r14
  __int64 v36; // rdi
  __int64 v37; // rdi
  __int64 v38; // rdi
  __int64 v39; // rdi
  __int64 v40; // rdx
  HSTRING *v41; // rcx
  HSTRING *v42; // rcx
  void *v43; // rcx
  HSTRING *v44; // rcx
  int v45; // eax
  __int64 v46; // rcx
  __int64 v47; // rcx
  IShellFolder *v48; // rcx
  __int64 v49; // rdx
  int ppv; // [rsp+20h] [rbp-49h]
  int ppva; // [rsp+20h] [rbp-49h]
  void **ppvb; // [rsp+20h] [rbp-49h]
  IShellFolder *psfParent; // [rsp+30h] [rbp-39h] BYREF
  void *v54; // [rsp+38h] [rbp-31h] BYREF
  HSTRING *v55; // [rsp+40h] [rbp-29h] BYREF
  HSTRING *v56; // [rsp+48h] [rbp-21h]
  void *ppvItem; // [rsp+50h] [rbp-19h] BYREF
  LPVOID pv; // [rsp+58h] [rbp-11h] BYREF
  __int64 v59; // [rsp+60h] [rbp-9h]
  __int64 v60; // [rsp+68h] [rbp-1h]
  const WCHAR **v61; // [rsp+70h] [rbp+7h] BYREF
  LPCITEMIDLIST pidl; // [rsp+78h] [rbp+Fh] BYREF
  __int64 v63[8]; // [rsp+80h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]
  __int64 v66; // [rsp+E0h] [rbp+77h] BYREF
  __int64 v67; // [rsp+E8h] [rbp+7Fh] BYREF

  v2 = a2;
  v54 = 0;
  psfParent = 0;
  v67 = 0;
  HasPackageQueryCapability = Windows::Internal::Feedback::HasPackageQueryCapability(a1);
  if ( HasPackageQueryCapability < 0 )
    goto LABEL_92;
  v66 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v66);
  v5 = Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Internal::Feedback::FeedbackItem,Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Feedback::FeedbackItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Feedback::FeedbackItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Feedback::FeedbackItem *>,0>>(
         v4,
         &v66);
  HasPackageQueryCapability = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9E,
      (unsigned int)"shell\\twinui\\feedback\\lib\\feedbackbroker.cpp",
      (const char *)(unsigned int)v5,
      ppv);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v66);
    goto LABEL_92;
  }
  Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v54);
  v6 = SHGetKnownFolderItem(&FOLDERID_AppsFolder, KF_FLAG_DEFAULT, 0, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, &v54);
  HasPackageQueryCapability = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA3,
      (unsigned int)"shell\\twinui\\feedback\\lib\\feedbackbroker.cpp",
      (const char *)(unsigned int)v6,
      ppva);
    v16 = v66;
    if ( v66 )
    {
      v66 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    }
    v17 = v67;
    if ( v67 )
    {
      v67 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    }
    goto LABEL_17;
  }
  v7 = v54;
  v8 = *(__int64 (__fastcall **)(void *, _QWORD, const GUID *, GUID *))(*(_QWORD *)v54 + 24LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&psfParent);
  ppvb = (void **)&psfParent;
  v9 = v8(v7, 0, &BHID_SFObject, &GUID_000214e6_0000_0000_c000_000000000046);
  HasPackageQueryCapability = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA4,
      (unsigned int)"shell\\twinui\\feedback\\lib\\feedbackbroker.cpp",
      (const char *)(unsigned int)v9,
      (int)&psfParent);
    v20 = v66;
    if ( v66 )
    {
      v66 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    }
    v21 = v67;
    if ( v67 )
    {
      v67 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    }
    v22 = psfParent;
    if ( psfParent )
    {
      psfParent = 0;
      ((void (__fastcall *)(IShellFolder *))v22->lpVtbl->Release)(v22);
    }
LABEL_17:
    v18 = v54;
    if ( v54 )
    {
      v54 = 0;
      (*(void (__fastcall **)(void *))(*(_QWORD *)v18 + 16LL))(v18);
    }
    return (unsigned int)HasPackageQueryCapability;
  }
  v10 = psfParent;
  EnumObjects = psfParent->lpVtbl->EnumObjects;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v67);
  v12 = ((__int64 (__fastcall *)(IShellFolder *, _QWORD, __int64, __int64 *))EnumObjects)(v10, 0, 64, &v67);
  HasPackageQueryCapability = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA5,
      (unsigned int)"shell\\twinui\\feedback\\lib\\feedbackbroker.cpp",
      (const char *)(unsigned int)v12,
      (int)&psfParent);
    v13 = v66;
    if ( v66 )
    {
      v66 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    }
    v14 = v67;
    if ( v67 )
    {
      v67 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    }
    v15 = psfParent;
    if ( psfParent )
    {
      psfParent = 0;
      ((void (__fastcall *)(IShellFolder *))v15->lpVtbl->Release)(v15);
    }
    goto LABEL_17;
  }
  if ( !v67 )
    goto LABEL_78;
  pidl = 0;
  while ( !(*(unsigned int (__fastcall **)(__int64, __int64, LPCITEMIDLIST *))(*(_QWORD *)v67 + 24LL))(v67, 1, &pidl) )
  {
    ppvItem = 0;
    pv = 0;
    v59 = 0;
    v60 = 0;
    if ( SHCreateItemWithParent(0, psfParent, pidl, &GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93, &ppvItem) >= 0 )
    {
      v23 = ppvItem;
      v24 = *(int (__fastcall **)(void *, const PROPERTYKEY *, LPVOID *))(*(_QWORD *)ppvItem + 136LL);
      if ( pv )
      {
        CoTaskMemFree(pv);
        pv = 0;
      }
      v59 = -1;
      v60 = -1;
      if ( v24(v23, &PKEY_Link_TargetParsingPath, &pv) >= 0 )
      {
        if ( pv )
        {
          v56 = 0;
          FileNameW = PathFindFileNameW((LPCWSTR)pv);
          v26 = pv;
          v61 = 0;
          v55 = 0;
          if ( (int)Windows::Internal::Feedback::HasPackageQueryCapability(v27) < 0 )
          {
            v44 = v55;
            if ( v55 )
            {
              v55 = 0;
              (*((void (__fastcall **)(HSTRING *))*v44 + 2))(v44);
            }
            goto LABEL_63;
          }
          if ( v26 )
          {
            if ( FileNameW )
            {
              v56 = 0;
              String = PicRetrieveFileInfo(v26, 16400, &v61);
              if ( String < 0 )
                goto LABEL_90;
              v29 = v61;
              v30 = v55;
              if ( v55 )
              {
                v55 = 0;
                (*((void (__fastcall **)(HSTRING *))*v30 + 2))(v30);
              }
              v55 = 0;
              v31 = (Windows::Internal::Feedback::InternalFeedbackItem *)operator new(
                                                                           0x60u,
                                                                           (const struct std::nothrow_t *)&std::nothrow);
              if ( !v31 )
              {
                String = -2147024882;
                goto LABEL_56;
              }
              v32 = (HSTRING *)Windows::Internal::Feedback::InternalFeedbackItem::InternalFeedbackItem(v31);
              v63[0] = 0;
              v33 = *v29;
              v34 = v29[1];
              v35 = v29[2];
              v36 = -1;
              do
                ++v36;
              while ( v35[v36] );
              WindowsDeleteString(v32[8]);
              v32[8] = 0;
              String = WindowsCreateString(v35, v36, v32 + 8);
              if ( String < 0 )
              {
                v40 = 24;
              }
              else
              {
                v37 = -1;
                do
                  ++v37;
                while ( v34[v37] );
                WindowsDeleteString(v32[9]);
                v32[9] = 0;
                String = WindowsCreateString(v34, v37, v32 + 9);
                if ( String < 0 )
                {
                  v40 = 25;
                }
                else
                {
                  v38 = -1;
                  do
                    ++v38;
                  while ( v33[v38] );
                  WindowsDeleteString(v32[10]);
                  v32[10] = 0;
                  String = WindowsCreateString(v33, v38, v32 + 10);
                  if ( String >= 0 )
                  {
                    v39 = -1;
                    do
                      ++v39;
                    while ( FileNameW[v39] );
                    WindowsDeleteString(v32[11]);
                    v32[11] = 0;
                    String = WindowsCreateString(FileNameW, v39, v32 + 11);
                    if ( String < 0 )
                    {
                      v40 = 27;
                      goto LABEL_55;
                    }
                    v55 = v32;
                    (*((void (__fastcall **)(HSTRING *))*v32 + 1))(v32);
                    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::Feedback::IFeedbackItem,Microsoft::WRL::FtmBase>::Release(v32);
                    String = 0;
LABEL_56:
                    PicFreeFileInfo(v61);
                    if ( String >= 0 )
                    {
                      v41 = 0;
                      v56 = v55;
                      goto LABEL_58;
                    }
LABEL_90:
                    v41 = v55;
LABEL_58:
                    if ( v41 )
                    {
                      v55 = 0;
                      (*((void (__fastcall **)(HSTRING *))*v41 + 2))(v41);
                    }
                    if ( String >= 0 && v56 )
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v66 + 104LL))(v66);
LABEL_63:
                    v42 = v56;
                    if ( v56 )
                    {
                      v56 = 0;
                      (*((void (__fastcall **)(HSTRING *))*v42 + 2))(v42);
                    }
                    goto LABEL_65;
                  }
                  v40 = 26;
                }
              }
LABEL_55:
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)v40,
                (unsigned int)"shell\\twinui\\feedback\\lib\\internalfeedbackhubapp.cpp",
                (const char *)(unsigned int)String,
                (int)ppvb);
              Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::Feedback::IFeedbackItem,Microsoft::WRL::FtmBase>::Release(v32);
              Microsoft::WRL::Details::MakeAllocator<SttExperienceManagerFactory>::~MakeAllocator<SttExperienceManagerFactory>(v63);
              goto LABEL_56;
            }
            v49 = 237;
          }
          else
          {
            v49 = 236;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v49,
            (unsigned int)"shell\\twinui\\feedback\\lib\\feedbackbroker.cpp",
            (const char *)0x80070057LL,
            (int)ppvb);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v55);
          goto LABEL_63;
        }
      }
    }
LABEL_65:
    ILFree((LPITEMIDLIST)pidl);
    if ( pv )
    {
      CoTaskMemFree(pv);
      pv = 0;
    }
    v59 = 0;
    v60 = 0;
    v43 = ppvItem;
    if ( ppvItem )
    {
      ppvItem = 0;
      (*(void (__fastcall **)(void *))(*(_QWORD *)v43 + 16LL))(v43);
    }
  }
  v2 = a2;
LABEL_78:
  v45 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v66 + 64LL))(v66, v2);
  HasPackageQueryCapability = v45;
  if ( v45 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC7,
      (unsigned int)"shell\\twinui\\feedback\\lib\\feedbackbroker.cpp",
      (const char *)(unsigned int)v45,
      (int)ppvb);
    v46 = v66;
    if ( v66 )
    {
      v66 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
    }
    v47 = v67;
    if ( v67 )
    {
      v67 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
    }
    v48 = psfParent;
    if ( psfParent )
    {
      psfParent = 0;
      ((void (__fastcall *)(IShellFolder *))v48->lpVtbl->Release)(v48);
    }
    goto LABEL_17;
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v66);
  HasPackageQueryCapability = 0;
LABEL_92:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v67);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&psfParent);
  Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v54);
  return (unsigned int)HasPackageQueryCapability;
}

```

## disassembly

```asm
0x18003dc50  mov     [rsp-8+arg_0], rbx
0x18003dc55  mov     [rsp-8+arg_8], rdx
0x18003dc5a  push    rbp
0x18003dc5b  push    rsi
0x18003dc5c  push    rdi
0x18003dc5d  push    r12
0x18003dc5f  push    r13
0x18003dc61  push    r14
0x18003dc63  push    r15
0x18003dc65  lea     rbp, [rsp-27h]
0x18003dc6a  sub     rsp, 90h
0x18003dc71  mov     rsi, rdx
0x18003dc74  xor     r14d, r14d
0x18003dc77  mov     [rbp+57h+var_88], r14
0x18003dc7b  mov     [rbp+57h+psfParent], r14
0x18003dc7f  mov     [rbp+57h+arg_18], r14
0x18003dc83  call    ?HasPackageQueryCapability@Feedback@Internal@Windows@@YAJXZ; Windows::Internal::Feedback::HasPackageQueryCapability(void)
0x18003dc88  mov     ebx, eax
0x18003dc8a  test    eax, eax
0x18003dc8c  js      loc_18003E361
0x18003dc92  mov     [rbp+57h+arg_10], r14
0x18003dc96  lea     rcx, [rbp+57h+arg_10]
0x18003dc9a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003dc9f  lea     rdx, [rbp+57h+arg_10]
0x18003dca3  call    ??$CreateExternalObjectVector@VFeedbackItem@Feedback@Internal@Windows@@V?$AgileVector@PEAVFeedbackItem@Feedback@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVFeedbackItem@Feedback@Internal@Windows@@@3Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVFeedbackItem@Feedback@Internal@Windows@@@3674@$0A@@3Collections@Foundation@4@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$AgileVector@PEAVFeedbackItem@Feedback@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVFeedbackItem@Feedback@Internal@Windows@@@3Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVFeedbackItem@Feedback@Internal@Windows@@@3674@$0A@@1234@@Z; Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Internal::Feedback::FeedbackItem,Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Feedback::FeedbackItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Feedback::FeedbackItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Feedback::FeedbackItem *>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Feedback::FeedbackItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Feedback::FeedbackItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Feedback::FeedbackItem *>,0> * *)
0x18003dca8  mov     ebx, eax
0x18003dcaa  test    eax, eax
0x18003dcac  js      loc_18003E2F7
0x18003dcb2  lea     rcx, [rbp+57h+var_88]
0x18003dcb6  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18003dcbb  lea     rax, [rbp+57h+var_88]
0x18003dcbf  mov     [rsp+0C0h+ppv], rax; int
0x18003dcc4  lea     r9, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x18003dccb  xor     r8d, r8d; hToken
0x18003dcce  xor     edx, edx; flags
0x18003dcd0  lea     rcx, FOLDERID_AppsFolder; rfid
0x18003dcd7  call    cs:__imp_SHGetKnownFolderItem
0x18003dcdd  mov     ebx, eax
0x18003dcdf  test    eax, eax
0x18003dce1  js      loc_18003DDC5
0x18003dce7  mov     rdi, [rbp+57h+var_88]
0x18003dceb  mov     rax, [rdi]
0x18003dcee  mov     rbx, [rax+18h]
0x18003dcf2  lea     rcx, [rbp+57h+psfParent]
0x18003dcf6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003dcfb  lea     rax, [rbp+57h+psfParent]
0x18003dcff  mov     [rsp+0C0h+ppv], rax; int
0x18003dd04  lea     r9, _GUID_000214e6_0000_0000_c000_000000000046
0x18003dd0b  lea     r8, BHID_SFObject
0x18003dd12  xor     edx, edx
0x18003dd14  mov     rcx, rdi
0x18003dd17  mov     rax, rbx
0x18003dd1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dd1f  mov     ebx, eax
0x18003dd21  test    eax, eax
0x18003dd23  js      loc_18003DE62
0x18003dd29  mov     rdi, [rbp+57h+psfParent]
0x18003dd2d  mov     rax, [rdi]
0x18003dd30  mov     rbx, [rax+20h]
0x18003dd34  lea     rcx, [rbp+57h+arg_18]
0x18003dd38  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003dd3d  lea     r9, [rbp+57h+arg_18]
0x18003dd41  xor     edx, edx
0x18003dd43  lea     r8d, [r14+40h]
0x18003dd47  mov     rcx, rdi
0x18003dd4a  mov     rax, rbx
0x18003dd4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dd52  mov     ebx, eax
0x18003dd54  test    eax, eax
0x18003dd56  jns     loc_18003DECE
0x18003dd5c  mov     rcx, [rbp+5Fh]; this
0x18003dd60  mov     r9d, eax; char *
0x18003dd63  lea     r8, aShellTwinuiFee; "shell\\twinui\\feedback\\lib\\feedbackb"...
0x18003dd6a  mov     edx, 0A5h; void *
0x18003dd6f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003dd74  nop
0x18003dd75  mov     rcx, [rbp+57h+arg_10]
0x18003dd79  test    rcx, rcx
0x18003dd7c  jz      short loc_18003DD8F
0x18003dd7e  mov     [rbp+57h+arg_10], r14
0x18003dd82  mov     rax, [rcx]
0x18003dd85  mov     rax, [rax+10h]
0x18003dd89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dd8e  nop
0x18003dd8f  mov     rcx, [rbp+57h+arg_18]
0x18003dd93  test    rcx, rcx
0x18003dd96  jz      short loc_18003DDA9
0x18003dd98  mov     [rbp+57h+arg_18], r14
0x18003dd9c  mov     rax, [rcx]
0x18003dd9f  mov     rax, [rax+10h]
0x18003dda3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dda8  nop
0x18003dda9  mov     rcx, [rbp+57h+psfParent]
0x18003ddad  test    rcx, rcx
0x18003ddb0  jz      short loc_18003DDC3
0x18003ddb2  mov     [rbp+57h+psfParent], r14
0x18003ddb6  mov     rax, [rcx]
0x18003ddb9  mov     rax, [rax+10h]
0x18003ddbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ddc2  nop
0x18003ddc3  jmp     short loc_18003DE2C
0x18003ddc5  mov     rcx, [rbp+5Fh]; this
0x18003ddc9  mov     r9d, ebx; char *
0x18003ddcc  lea     r8, aShellTwinuiFee; "shell\\twinui\\feedback\\lib\\feedbackb"...
0x18003ddd3  mov     edx, 0A3h; void *
0x18003ddd8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003dddd  nop
0x18003ddde  mov     rcx, [rbp+57h+arg_10]
0x18003dde2  test    rcx, rcx
0x18003dde5  jz      short loc_18003DDF8
0x18003dde7  mov     [rbp+57h+arg_10], r14
0x18003ddeb  mov     rax, [rcx]
0x18003ddee  mov     rax, [rax+10h]
0x18003ddf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ddf7  nop
0x18003ddf8  mov     rcx, [rbp+57h+arg_18]
0x18003ddfc  test    rcx, rcx
0x18003ddff  jz      short loc_18003DE12
0x18003de01  mov     [rbp+57h+arg_18], r14
0x18003de05  mov     rax, [rcx]
0x18003de08  mov     rax, [rax+10h]
0x18003de0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003de11  nop
0x18003de12  mov     rcx, [rbp+57h+psfParent]
0x18003de16  test    rcx, rcx
0x18003de19  jz      short loc_18003DE2C
0x18003de1b  mov     [rbp+57h+psfParent], r14
0x18003de1f  mov     rax, [rcx]
0x18003de22  mov     rax, [rax+10h]
0x18003de26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003de2b  nop
0x18003de2c  mov     rcx, [rbp+57h+var_88]
0x18003de30  test    rcx, rcx
0x18003de33  jz      short loc_18003DE45
0x18003de35  mov     [rbp+57h+var_88], r14
0x18003de39  mov     rax, [rcx]
0x18003de3c  mov     rax, [rax+10h]
0x18003de40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003de45  mov     eax, ebx
0x18003de47  mov     rbx, [rsp+0C0h+arg_0]
0x18003de4f  add     rsp, 90h
0x18003de56  pop     r15
0x18003de58  pop     r14
0x18003de5a  pop     r13
0x18003de5c  pop     r12
0x18003de5e  pop     rdi
0x18003de5f  pop     rsi
0x18003de60  pop     rbp
0x18003de61  retn
0x18003de62  mov     rcx, [rbp+5Fh]; this
0x18003de66  mov     r9d, ebx; char *
0x18003de69  lea     r8, aShellTwinuiFee; "shell\\twinui\\feedback\\lib\\feedbackb"...
0x18003de70  mov     edx, 0A4h; void *
0x18003de75  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003de7a  nop
0x18003de7b  mov     rcx, [rbp+57h+arg_10]
0x18003de7f  test    rcx, rcx
0x18003de82  jz      short loc_18003DE95
0x18003de84  mov     [rbp+57h+arg_10], r14
0x18003de88  mov     rax, [rcx]
0x18003de8b  mov     rax, [rax+10h]
0x18003de8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003de94  nop
0x18003de95  mov     rcx, [rbp+57h+arg_18]
0x18003de99  test    rcx, rcx
0x18003de9c  jz      short loc_18003DEAF
0x18003de9e  mov     [rbp+57h+arg_18], r14
0x18003dea2  mov     rax, [rcx]
0x18003dea5  mov     rax, [rax+10h]
0x18003dea9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003deae  nop
0x18003deaf  mov     rcx, [rbp+57h+psfParent]
0x18003deb3  test    rcx, rcx
0x18003deb6  jz      short loc_18003DEC9
0x18003deb8  mov     [rbp+57h+psfParent], r14
0x18003debc  mov     rax, [rcx]
0x18003debf  mov     rax, [rax+10h]
0x18003dec3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dec8  nop
0x18003dec9  jmp     loc_18003DE2C
0x18003dece  cmp     [rbp+57h+arg_18], r14
0x18003ded2  jz      loc_18003E26E
0x18003ded8  mov     [rbp+57h+pidl], r14
0x18003dedc  mov     rcx, [rbp+57h+arg_18]
0x18003dee0  mov     rax, [rcx]
0x18003dee3  xor     r9d, r9d
0x18003dee6  lea     r8, [rbp+57h+pidl]
0x18003deea  lea     edx, [r9+1]
0x18003deee  mov     rax, [rax+18h]
0x18003def2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003def7  test    eax, eax
0x18003def9  jnz     loc_18003E26A
0x18003deff  mov     [rbp+57h+ppvItem], r14
0x18003df03  mov     [rbp+57h+pv], r14
0x18003df07  mov     [rbp+57h+var_60], r14
0x18003df0b  mov     [rbp+57h+var_58], r14
0x18003df0f  lea     rax, [rbp+57h+ppvItem]
0x18003df13  mov     [rsp+0C0h+ppv], rax; int
0x18003df18  lea     r9, _GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93; riid
0x18003df1f  mov     r8, [rbp+57h+pidl]; pidl
0x18003df23  mov     rdx, [rbp+57h+psfParent]; psfParent
0x18003df27  xor     ecx, ecx; pidlParent
0x18003df29  call    cs:__imp_SHCreateItemWithParent
0x18003df2f  test    eax, eax
0x18003df31  js      loc_18003E1B7
0x18003df37  mov     rbx, [rbp+57h+ppvItem]
0x18003df3b  mov     rax, [rbx]
0x18003df3e  mov     rdi, [rax+88h]
0x18003df45  mov     rcx, [rbp+57h+pv]; pv
0x18003df49  test    rcx, rcx
0x18003df4c  jz      short loc_18003DF58
0x18003df4e  call    cs:__imp_CoTaskMemFree
0x18003df54  mov     [rbp+57h+pv], r14
0x18003df58  mov     [rbp+57h+var_60], 0FFFFFFFFFFFFFFFFh
0x18003df60  mov     [rbp+57h+var_58], 0FFFFFFFFFFFFFFFFh
0x18003df68  lea     r8, [rbp+57h+pv]
0x18003df6c  lea     rdx, PKEY_Link_TargetParsingPath
0x18003df73  mov     rcx, rbx
0x18003df76  mov     rax, rdi
0x18003df79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003df7e  test    eax, eax
0x18003df80  js      loc_18003E1B7
0x18003df86  mov     rcx, [rbp+57h+pv]; pszPath
0x18003df8a  test    rcx, rcx
0x18003df8d  jz      loc_18003E1B7
0x18003df93  mov     [rbp+57h+var_78], r14
0x18003df97  call    cs:__imp_PathFindFileNameW
0x18003df9d  mov     r15, rax
0x18003dfa0  mov     rbx, [rbp+57h+pv]
0x18003dfa4  mov     [rbp+57h+var_50], r14
0x18003dfa8  mov     [rbp+57h+var_80], r14
0x18003dfac  call    ?HasPackageQueryCapability@Feedback@Internal@Windows@@YAJXZ; Windows::Internal::Feedback::HasPackageQueryCapability(void)
0x18003dfb1  test    eax, eax
0x18003dfb3  js      loc_18003E21D
0x18003dfb9  test    rbx, rbx
0x18003dfbc  jz      loc_18003E31B
0x18003dfc2  test    r15, r15
0x18003dfc5  jz      loc_18003E322
0x18003dfcb  mov     [rbp+57h+var_78], r14
0x18003dfcf  lea     r8, [rbp+57h+var_50]
0x18003dfd3  mov     edx, 4010h
0x18003dfd8  mov     rcx, rbx
0x18003dfdb  call    cs:__imp_PicRetrieveFileInfo
0x18003dfe1  mov     ebx, eax
0x18003dfe3  test    eax, eax
0x18003dfe5  js      loc_18003E34C
0x18003dfeb  mov     rbx, [rbp+57h+var_50]
0x18003dfef  mov     rcx, [rbp+57h+var_80]
0x18003dff3  test    rcx, rcx
0x18003dff6  jz      short loc_18003E009
0x18003dff8  mov     [rbp+57h+var_80], r14
0x18003dffc  mov     rax, [rcx]
0x18003dfff  mov     rax, [rax+10h]
0x18003e003  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e008  nop
0x18003e009  mov     [rbp+57h+var_80], r14
0x18003e00d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003e014  mov     ecx, 60h ; '`'; unsigned __int64
0x18003e019  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18003e01e  test    rax, rax
0x18003e021  jz      loc_18003E260
0x18003e027  mov     rcx, rax; this
0x18003e02a  call    ??0InternalFeedbackItem@Feedback@Internal@Windows@@QEAA@XZ; Windows::Internal::Feedback::InternalFeedbackItem::InternalFeedbackItem(void)
0x18003e02f  mov     rsi, rax
0x18003e032  mov     [rbp+57h+var_40], r14
0x18003e036  mov     r13, [rbx]
0x18003e039  mov     r12, [rbx+8]
0x18003e03d  mov     r14, [rbx+10h]
0x18003e041  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18003e045  xor     eax, eax
0x18003e047  inc     rdi
0x18003e04a  cmp     [r14+rdi*2], ax
0x18003e04f  jnz     short loc_18003E047
0x18003e051  lea     rbx, [rsi+40h]
0x18003e055  mov     rcx, [rbx]; string
0x18003e058  call    cs:__imp_WindowsDeleteString
0x18003e05e  mov     qword ptr [rbx], 0
0x18003e065  mov     r8, rbx; string
0x18003e068  mov     edx, edi; length
0x18003e06a  mov     rcx, r14; sourceString
0x18003e06d  call    cs:__imp_WindowsCreateString
0x18003e073  mov     ebx, eax
0x18003e075  xor     r14d, r14d
0x18003e078  test    eax, eax
0x18003e07a  js      loc_18003E209
0x18003e080  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18003e084  inc     rdi
0x18003e087  cmp     [r12+rdi*2], r14w
0x18003e08c  jnz     short loc_18003E084
0x18003e08e  lea     rbx, [rsi+48h]
0x18003e092  mov     rcx, [rbx]; string
0x18003e095  call    cs:__imp_WindowsDeleteString
0x18003e09b  mov     [rbx], r14
0x18003e09e  mov     r8, rbx; string
0x18003e0a1  mov     edx, edi; length
0x18003e0a3  mov     rcx, r12; sourceString
0x18003e0a6  call    cs:__imp_WindowsCreateString
0x18003e0ac  mov     ebx, eax
0x18003e0ae  test    eax, eax
0x18003e0b0  js      loc_18003E1FF
  ... truncated ...
```
