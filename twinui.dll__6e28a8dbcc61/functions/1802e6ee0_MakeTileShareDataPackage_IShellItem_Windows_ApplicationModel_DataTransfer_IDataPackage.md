# MakeTileShareDataPackage(IShellItem *,Windows::ApplicationModel::DataTransfer::IDataPackage * *)

- ea: `0x1802e6ee0`
- end: `0x1802e74de`
- name: `?MakeTileShareDataPackage@@YAJPEAUIShellItem@@PEAPEAUIDataPackage@DataTransfer@ApplicationModel@Windows@@@Z`
- size: `1534`
- prototype: `__int64 __fastcall(struct IShellItem *, struct Windows::ApplicationModel::DataTransfer::IDataPackage **)`
- caller_count: `1`
- callee_count: `23`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1802e2900`

## callees

- `0x180008acc`
- `0x18000b7e8`
- `0x18000c350`
- `0x18001f3c0`
- `0x180037e18`
- `0x180047224`
- `0x180052980`
- `0x180059ddc`
- `0x18008e9d4`
- `0x1800a3cec`
- `0x1800a6a98`
- `0x1800bb114`
- `0x18011a164`
- `0x18013d330`
- `0x180156bd0`
- `0x18025c2c0`
- `0x18027db98`
- `0x18028a014`
- `0x1802e6c80`
- `0x1802e6e94`
- `0x1802e6ee0`
- `0x18035bba0`
- `0x1803a3010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1802e706f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1802e70dc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1802e71dc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1802e706f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1802e70dc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1802e71dc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802e725a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802e72ab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802e725a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802e72ab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802e6f49`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802e6f7a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802e7003`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802e7481`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802e749d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802e74af`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802e6f49`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802e6f7a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802e7003`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802e7481`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802e749d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802e74af`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1802e723d`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1802e723d`
- `WSClient!GetApplicationURL` at `0x1802e6f8b`
- `WSClient!GetApplicationURL` at `0x1802e6f8b`
- `api-ms-win-shcore-stream-winrt-l1-1-0!CreateRandomAccessStreamOverStream` at `0x1802e73bd`
- `api-ms-win-shcore-stream-winrt-l1-1-0!CreateRandomAccessStreamOverStream` at `0x1802e73bd`

## pseudocode

```c
__int64 __fastcall MakeTileShareDataPackage(
        struct IShellItem *a1,
        struct Windows::ApplicationModel::DataTransfer::IDataPackage **a2)
{
  unsigned __int16 *v4; // rbx
  int ApplicationURL; // edi
  _QWORD *v6; // rax
  struct Windows::ApplicationModel::DataTransfer::IDataPackage *v7; // rsi
  __int64 (__fastcall *v8)(struct Windows::ApplicationModel::DataTransfer::IDataPackage *, __int64 *); // rdi
  struct IShellItemVtbl *lpVtbl; // rax
  HRESULT (__stdcall *GetDisplayName)(IShellItem *, SIGDN, LPWSTR *); // rdi
  __int64 v11; // rsi
  __int64 (__fastcall *v12)(__int64, PVOID); // rdi
  unsigned __int16 *v13; // r14
  __int64 v14; // rsi
  __int64 (__fastcall *v15)(__int64, PVOID); // rdi
  int Error; // eax
  unsigned __int16 *v17; // r14
  struct Windows::ApplicationModel::DataTransfer::IDataPackage *v18; // rsi
  __int64 (__fastcall *v19)(struct Windows::ApplicationModel::DataTransfer::IDataPackage *, PVOID); // rdi
  int v20; // eax
  const unsigned __int16 *v21; // rdx
  _QWORD *v22; // rax
  unsigned __int16 *v23; // rsi
  __int64 (__fastcall *v24)(unsigned __int16 *, PVOID, HSTRING *); // rdi
  unsigned __int16 *v25; // r14
  __int64 v26; // rdi
  __int64 v27; // rsi
  __int64 (__fastcall *v28)(__int64, _QWORD, HSTRING *); // rdi
  __int64 v29; // rax
  struct IShellItemVtbl *v30; // rax
  HRESULT (__stdcall *QueryInterface)(IShellItem *, const IID *const, void **); // rdi
  int ScaleFactorForPart; // eax
  unsigned __int16 *v33; // rsi
  __int64 (__fastcall *v34)(unsigned __int16 *, __int64, __int64, __int64 *); // rdi
  __int64 v35; // rdx
  const unsigned __int16 *v36; // rdx
  _QWORD *v37; // rax
  unsigned __int16 *v38; // rsi
  __int64 (__fastcall *v39)(unsigned __int16 *, HSTRING, __int64 *); // rdi
  HSTRING string; // [rsp+30h] [rbp-69h] BYREF
  unsigned __int16 *v42; // [rsp+38h] [rbp-61h] BYREF
  unsigned __int16 *v43; // [rsp+40h] [rbp-59h] BYREF
  __int64 v44; // [rsp+48h] [rbp-51h] BYREF
  struct Windows::ApplicationModel::DataTransfer::IDataPackage *v45; // [rsp+50h] [rbp-49h] BYREF
  __int64 v46; // [rsp+58h] [rbp-41h] BYREF
  LPVOID pv; // [rsp+60h] [rbp-39h] BYREF
  __int64 v48; // [rsp+68h] [rbp-31h] BYREF
  unsigned __int16 *v49; // [rsp+70h] [rbp-29h] BYREF
  __int64 v50; // [rsp+78h] [rbp-21h] BYREF
  __int64 v51[2]; // [rsp+80h] [rbp-19h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+90h] [rbp-9h] BYREF
  __int64 v53; // [rsp+A8h] [rbp+Fh]

  *a2 = 0;
  v51[0] = 0;
  v4 = 0;
  v42 = 0;
  ApplicationURL = CPropertyStoreHelperBase<IPropertyStore>::InitFromItem(
                     (unsigned int)v51,
                     (_DWORD)a1,
                     1,
                     (unsigned int)&PKEY_AppUserModel_PackageFamilyName,
                     1);
  if ( ApplicationURL >= 0 )
  {
    CoTaskMemFree(0);
    *(_DWORD *)&hstringHeader.Reserved.Reserved2[16] = 17;
    *(_OWORD *)&hstringHeader.Reserved.Reserved1 = PKEY_AppUserModel_PackageFamilyName;
    CPropertyStoreHelperBase<IPropertyStore>::GetString<_tagpropertykey>(v51, (__int128 *)&hstringHeader, &v42);
    v49 = 0;
    CoTaskMemFree(0);
    v4 = v42;
    ApplicationURL = GetApplicationURL(v42, &v49);
    if ( ApplicationURL >= 0 )
    {
      v45 = 0;
      v6 = (_QWORD *)Windows::Internal::StringReference::StringReference(
                       (HSTRING *)&hstringHeader,
                       L"Windows.ApplicationModel.DataTransfer.DataPackage");
      ApplicationURL = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::ApplicationModel::DataTransfer::IDataPackage>>(
                         *v6,
                         &v45);
      if ( ApplicationURL >= 0 )
      {
        v7 = v45;
        v48 = 0;
        v8 = *(__int64 (__fastcall **)(struct Windows::ApplicationModel::DataTransfer::IDataPackage *, __int64 *))(*(_QWORD *)v45 + 56LL);
        Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v48);
        ApplicationURL = v8(v7, &v48);
        if ( ApplicationURL >= 0 )
        {
          lpVtbl = a1->lpVtbl;
          pv = 0;
          GetDisplayName = lpVtbl->GetDisplayName;
          CoTaskMemFree(0);
          ApplicationURL = ((__int64 (__fastcall *)(struct IShellItem *, _QWORD, LPVOID *))GetDisplayName)(a1, 0, &pv);
          if ( ApplicationURL >= 0 )
          {
            v11 = v48;
            v12 = *(__int64 (__fastcall **)(__int64, PVOID))(*(_QWORD *)v48 + 56LL);
            Windows::Internal::StringReference::_ConstructorHelper(
              (Windows::Internal::StringReference *)&hstringHeader,
              (const unsigned __int16 *)pv);
            ApplicationURL = v12(v11, hstringHeader.Reserved.Reserved1);
            if ( ApplicationURL >= 0 )
            {
              v13 = (unsigned __int16 *)ShellConstructMessageStringW(&_ImageBase, 9587, pv);
              LocalFree(0);
              v42 = v13;
              if ( v13 )
              {
                v14 = v48;
                v15 = *(__int64 (__fastcall **)(__int64, PVOID))(*(_QWORD *)v48 + 72LL);
                Windows::Internal::StringReference::_ConstructorHelper(
                  (Windows::Internal::StringReference *)&hstringHeader,
                  v13);
                Error = v15(v14, hstringHeader.Reserved.Reserved1);
              }
              else
              {
                Error = ResultFromKnownLastError();
              }
              ApplicationURL = Error;
              CMemString<CMemString_PolicyLocalMem>::~CMemString<CMemString_PolicyLocalMem>(&v42);
              if ( ApplicationURL >= 0 )
              {
                v17 = (unsigned __int16 *)ShellConstructMessageStringW(&_ImageBase, 9588, pv);
                LocalFree(0);
                v42 = v17;
                if ( v17 )
                {
                  v18 = v45;
                  v19 = *(__int64 (__fastcall **)(struct Windows::ApplicationModel::DataTransfer::IDataPackage *, PVOID))(*(_QWORD *)v45 + 128LL);
                  Windows::Internal::StringReference::_ConstructorHelper(
                    (Windows::Internal::StringReference *)&hstringHeader,
                    v17);
                  v20 = v19(v18, hstringHeader.Reserved.Reserved1);
                }
                else
                {
                  v20 = ResultFromKnownLastError();
                }
                ApplicationURL = v20;
                CMemString<CMemString_PolicyLocalMem>::~CMemString<CMemString_PolicyLocalMem>(&v42);
                if ( ApplicationURL >= 0 )
                {
                  v43 = 0;
                  v22 = (_QWORD *)Windows::Internal::StringReference::StringReference(
                                    (HSTRING *)&hstringHeader,
                                    (const unsigned __int16 (*)[23])v21);
                  ApplicationURL = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory>>(
                                     *v22,
                                     &v43);
                  if ( ApplicationURL >= 0 )
                  {
                    v23 = v43;
                    string = 0;
                    v24 = *(__int64 (__fastcall **)(unsigned __int16 *, PVOID, HSTRING *))(*(_QWORD *)v43 + 48LL);
                    Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&string);
                    Windows::Internal::StringReference::_ConstructorHelper(
                      (Windows::Internal::StringReference *)&hstringHeader,
                      v49);
                    ApplicationURL = v24(v23, hstringHeader.Reserved.Reserved1, &string);
                    if ( ApplicationURL >= 0 )
                      ApplicationURL = (*(__int64 (__fastcall **)(struct Windows::ApplicationModel::DataTransfer::IDataPackage *, HSTRING))(*(_QWORD *)v45 + 136LL))(
                                         v45,
                                         string);
                    Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&string);
                  }
                  Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v43);
                  if ( ApplicationURL >= 0 )
                  {
                    v25 = (unsigned __int16 *)ShellConstructMessageStringW(&_ImageBase, 9589, v49);
                    LocalFree(0);
                    v43 = v25;
                    if ( v25 && *v25 || (ApplicationURL = ResultFromKnownLastError(), ApplicationURL >= 0) )
                    {
                      v44 = 0;
                      v53 = 0;
                      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
                        &hstringHeader,
                        L"Windows.ApplicationModel.DataTransfer.HtmlFormatHelper",
                        0x37u,
                        0x36u);
                      v26 = v53;
                      Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v44);
                      ApplicationURL = RoGetActivationFactory(v26, &GUID_e22e7749_dd70_446f_aefc_61cee59f655e, &v44);
                      if ( ApplicationURL >= 0 )
                      {
                        v27 = v44;
                        string = 0;
                        v28 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)v44 + 56LL);
                        WindowsDeleteString(0);
                        string = 0;
                        v42 = v25;
                        v29 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v42);
                        ApplicationURL = v28(v27, *(_QWORD *)(v29 + 24), &string);
                        if ( ApplicationURL >= 0 )
                          ApplicationURL = (*(__int64 (__fastcall **)(struct Windows::ApplicationModel::DataTransfer::IDataPackage *, HSTRING))(*(_QWORD *)v45 + 144LL))(
                                             v45,
                                             string);
                        WindowsDeleteString(string);
                      }
                      Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v44);
                    }
                    CMemString<CMemString_PolicyLocalMem>::~CMemString<CMemString_PolicyLocalMem>(&v43);
                    if ( ApplicationURL >= 0 )
                    {
                      v30 = a1->lpVtbl;
                      v43 = 0;
                      QueryInterface = v30->QueryInterface;
                      Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v43);
                      ApplicationURL = ((__int64 (__fastcall *)(struct IShellItem *, GUID *, unsigned __int16 **))QueryInterface)(
                                         a1,
                                         &GUID_8a322201_0a87_46c1_9c77_7620e0cc5bbc,
                                         &v43);
                      if ( ApplicationURL >= 0 )
                      {
                        v50 = 0;
                        ScaleFactorForPart = CLauncherSettings::GetScaleFactorForPart();
                        v33 = v43;
                        v46 = 0;
                        if ( ScaleFactorForPart < 100 )
                          ScaleFactorForPart = 100;
                        LODWORD(v46) = (int)(float)((float)((float)ScaleFactorForPart * 30.0) / 100.0);
                        HIDWORD(v46) = v46;
                        v34 = *(__int64 (__fastcall **)(unsigned __int16 *, __int64, __int64, __int64 *))(*(_QWORD *)v43 + 32LL);
                        Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v50);
                        ApplicationURL = v34(v33, v46, 9, &v50);
                        if ( ApplicationURL >= 0 )
                        {
                          LODWORD(string) = 0;
                          v46 = 0;
                          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
                          ApplicationURL = GetStreamFromSharedBitmap(v50, v35, &string);
                          if ( ApplicationURL >= 0 )
                          {
                            string = 0;
                            Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&string);
                            ApplicationURL = CreateRandomAccessStreamOverStream(
                                               v46,
                                               0,
                                               &GUID_905a0fe1_bc53_11df_8c49_001e4fc686da,
                                               &string);
                            if ( ApplicationURL >= 0 )
                            {
                              v42 = 0;
                              v37 = (_QWORD *)Windows::Internal::StringReference::StringReference(
                                                (HSTRING *)&hstringHeader,
                                                (const unsigned __int16 (*)[52])v36);
                              ApplicationURL = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Storage::Streams::IRandomAccessStreamReferenceStatics>>(
                                                 *v37,
                                                 &v42);
                              if ( ApplicationURL >= 0 )
                              {
                                v38 = v42;
                                v44 = 0;
                                v39 = *(__int64 (__fastcall **)(unsigned __int16 *, HSTRING, __int64 *))(*(_QWORD *)v42 + 64LL);
                                Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v44);
                                ApplicationURL = v39(v38, string, &v44);
                                if ( ApplicationURL >= 0 )
                                  ApplicationURL = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v48 + 88LL))(
                                                     v48,
                                                     v44);
                                Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v44);
                              }
                              Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v42);
                            }
                            Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&string);
                          }
                          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
                        }
                        Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v50);
                      }
                      Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v43);
                      if ( ApplicationURL >= 0 )
                      {
                        Microsoft::WRL::ComPtr<IWindowingEnvironmentConfig>::InternalAddRef(&v45);
                        ApplicationURL = 0;
                        *a2 = v45;
                      }
                    }
                  }
                }
              }
            }
          }
          CoTaskMemFree(pv);
        }
        Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v48);
      }
      Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v45);
    }
    CoTaskMemFree(v49);
  }
  DirectUI::DuiPVLTrigger::~DuiPVLTrigger((DirectUI::DuiPVLTrigger *)v51);
  CoTaskMemFree(v4);
  return (unsigned int)ApplicationURL;
}

```

## disassembly

```asm
0x1802e6ee0  mov     [rsp-8+arg_10], rbx
0x1802e6ee5  push    rbp
0x1802e6ee6  push    rsi
0x1802e6ee7  push    rdi
0x1802e6ee8  push    r12
0x1802e6eea  push    r13
0x1802e6eec  push    r14
0x1802e6eee  push    r15
0x1802e6ef0  lea     rbp, [rsp-27h]
0x1802e6ef5  sub     rsp, 0C0h
0x1802e6efc  mov     rax, cs:__security_cookie
0x1802e6f03  xor     rax, rsp
0x1802e6f06  mov     [rbp+57h+var_40], rax
0x1802e6f0a  xor     r13d, r13d
0x1802e6f0d  lea     r9, PKEY_AppUserModel_PackageFamilyName
0x1802e6f14  mov     r12, rdx
0x1802e6f17  mov     [rdx], r13
0x1802e6f1a  mov     r15, rcx
0x1802e6f1d  mov     [rbp+57h+var_70], r13
0x1802e6f21  mov     rdx, rcx
0x1802e6f24  mov     ebx, r13d
0x1802e6f27  lea     r8d, [r13+1]
0x1802e6f2b  mov     [rbp+57h+var_B8], rbx
0x1802e6f2f  lea     rcx, [rbp+57h+var_70]
0x1802e6f33  mov     dword ptr [rsp+0F0h+var_D0], r8d
0x1802e6f38  call    ?InitFromItem@?$CPropertyStoreHelperBase@UIPropertyStore@@@@QEAAJPEAUIUnknown@@W4GETPROPERTYSTOREFLAGS@@PEBU_tagpropertykey@@I@Z; CPropertyStoreHelperBase<IPropertyStore>::InitFromItem(IUnknown *,GETPROPERTYSTOREFLAGS,_tagpropertykey const *,uint)
0x1802e6f3d  mov     edi, eax
0x1802e6f3f  test    eax, eax
0x1802e6f41  js      loc_1802E74A3
0x1802e6f47  xor     ecx, ecx; pv
0x1802e6f49  call    cs:__imp_CoTaskMemFree
0x1802e6f4f  movups  xmm0, cs:PKEY_AppUserModel_PackageFamilyName
0x1802e6f56  mov     eax, cs:dword_18040A550
0x1802e6f5c  lea     r8, [rbp+57h+var_B8]
0x1802e6f60  lea     rdx, [rbp+57h+hstringHeader]
0x1802e6f64  mov     dword ptr [rbp+57h+hstringHeader.Reserved+10h], eax
0x1802e6f67  lea     rcx, [rbp+57h+var_70]
0x1802e6f6b  movaps  xmmword ptr [rbp+57h+hstringHeader.Reserved], xmm0
0x1802e6f6f  call    ??$GetString@U_tagpropertykey@@@?$CPropertyStoreHelperBase@UIPropertyStore@@@@QEBAJU_tagpropertykey@@PEAPEAG@Z; CPropertyStoreHelperBase<IPropertyStore>::GetString<_tagpropertykey>(_tagpropertykey,ushort * *)
0x1802e6f74  xor     ecx, ecx; pv
0x1802e6f76  mov     [rbp+57h+var_80], r13
0x1802e6f7a  call    cs:__imp_CoTaskMemFree
0x1802e6f80  mov     rbx, [rbp+57h+var_B8]
0x1802e6f84  lea     rdx, [rbp+57h+var_80]
0x1802e6f88  mov     rcx, rbx
0x1802e6f8b  call    cs:__imp_GetApplicationURL
0x1802e6f91  mov     edi, eax
0x1802e6f93  test    eax, eax
0x1802e6f95  js      loc_1802E7499
0x1802e6f9b  lea     rdx, ?RuntimeClass_Windows_ApplicationModel_DataTransfer_DataPackage@@3QBGB; "Windows.ApplicationModel.DataTransfer.D"...
0x1802e6fa2  mov     [rbp+57h+var_A0], r13
0x1802e6fa6  lea     rcx, [rbp+57h+hstringHeader]; string
0x1802e6faa  call    ??$?0$0DC@@StringReference@Internal@Windows@@QEAA@AEAY0DC@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[50])
0x1802e6faf  lea     rdx, [rbp+57h+var_A0]
0x1802e6fb3  mov     rcx, [rax]
0x1802e6fb6  call    ??$ActivateInstance@V?$ComPtr@UIDataPackage@DataTransfer@ApplicationModel@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIDataPackage@DataTransfer@ApplicationModel@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::ApplicationModel::DataTransfer::IDataPackage>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::ApplicationModel::DataTransfer::IDataPackage>>)
0x1802e6fbb  mov     edi, eax
0x1802e6fbd  test    eax, eax
0x1802e6fbf  js      loc_1802E7490
0x1802e6fc5  mov     rsi, [rbp+57h+var_A0]
0x1802e6fc9  lea     rcx, [rbp+57h+var_88]
0x1802e6fcd  mov     [rbp+57h+var_88], r13
0x1802e6fd1  mov     rax, [rsi]
0x1802e6fd4  mov     rdi, [rax+38h]
0x1802e6fd8  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1802e6fdd  lea     rdx, [rbp+57h+var_88]
0x1802e6fe1  mov     rcx, rsi
0x1802e6fe4  mov     rax, rdi
0x1802e6fe7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802e6fec  mov     edi, eax
0x1802e6fee  test    eax, eax
0x1802e6ff0  js      loc_1802E7487
0x1802e6ff6  mov     rax, [r15]
0x1802e6ff9  xor     ecx, ecx; pv
0x1802e6ffb  mov     [rbp+57h+pv], r13
0x1802e6fff  mov     rdi, [rax+28h]
0x1802e7003  call    cs:__imp_CoTaskMemFree
0x1802e7009  lea     r8, [rbp+57h+pv]
0x1802e700d  xor     edx, edx
0x1802e700f  mov     rcx, r15
0x1802e7012  mov     rax, rdi
0x1802e7015  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802e701a  mov     edi, eax
0x1802e701c  test    eax, eax
0x1802e701e  js      loc_1802E747D
0x1802e7024  mov     rsi, [rbp+57h+var_88]
0x1802e7028  lea     rcx, [rbp+57h+hstringHeader]; this
0x1802e702c  mov     rdx, [rbp+57h+pv]; unsigned __int16 *
0x1802e7030  mov     rax, [rsi]
0x1802e7033  mov     rdi, [rax+38h]
0x1802e7037  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x1802e703c  mov     rdx, qword ptr [rbp+57h+hstringHeader.Reserved]
0x1802e7040  mov     rcx, rsi
0x1802e7043  mov     rax, rdi
0x1802e7046  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802e704b  mov     edi, eax
0x1802e704d  test    eax, eax
0x1802e704f  js      loc_1802E747D
0x1802e7055  mov     r8, [rbp+57h+pv]
0x1802e7059  lea     rcx, __ImageBase
0x1802e7060  mov     edx, 2573h
0x1802e7065  call    ShellConstructMessageStringW
0x1802e706a  xor     ecx, ecx; hMem
0x1802e706c  mov     r14, rax
0x1802e706f  call    cs:__imp_LocalFree
0x1802e7075  mov     [rbp+57h+var_B8], r14
0x1802e7079  test    r14, r14
0x1802e707c  jz      short loc_1802E70A6
0x1802e707e  mov     rsi, [rbp+57h+var_88]
0x1802e7082  mov     rdx, r14; unsigned __int16 *
0x1802e7085  mov     rcx, [rsi]
0x1802e7088  mov     rdi, [rcx+48h]
0x1802e708c  lea     rcx, [rbp+57h+hstringHeader]; this
0x1802e7090  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x1802e7095  mov     rdx, qword ptr [rbp+57h+hstringHeader.Reserved]
0x1802e7099  mov     rcx, rsi
0x1802e709c  mov     rax, rdi
0x1802e709f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802e70a4  jmp     short loc_1802E70AB
0x1802e70a6  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1802e70ab  lea     rcx, [rbp+57h+var_B8]
0x1802e70af  mov     edi, eax
0x1802e70b1  call    ??1?$CMemString@UCMemString_PolicyLocalMem@@@@QEAA@XZ; CMemString<CMemString_PolicyLocalMem>::~CMemString<CMemString_PolicyLocalMem>(void)
0x1802e70b6  test    edi, edi
0x1802e70b8  js      loc_1802E747D
0x1802e70be  mov     r9, [rbp+57h+var_80]
0x1802e70c2  lea     rcx, __ImageBase
0x1802e70c9  mov     r8, [rbp+57h+pv]
0x1802e70cd  mov     edx, 2574h
0x1802e70d2  call    ShellConstructMessageStringW
0x1802e70d7  xor     ecx, ecx; hMem
0x1802e70d9  mov     r14, rax
0x1802e70dc  call    cs:__imp_LocalFree
0x1802e70e2  mov     [rbp+57h+var_B8], r14
0x1802e70e6  test    r14, r14
0x1802e70e9  jz      short loc_1802E7116
0x1802e70eb  mov     rsi, [rbp+57h+var_A0]
0x1802e70ef  mov     rdx, r14; unsigned __int16 *
0x1802e70f2  mov     rcx, [rsi]
0x1802e70f5  mov     rdi, [rcx+80h]
0x1802e70fc  lea     rcx, [rbp+57h+hstringHeader]; this
0x1802e7100  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x1802e7105  mov     rdx, qword ptr [rbp+57h+hstringHeader.Reserved]
0x1802e7109  mov     rcx, rsi
0x1802e710c  mov     rax, rdi
0x1802e710f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802e7114  jmp     short loc_1802E711B
0x1802e7116  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1802e711b  lea     rcx, [rbp+57h+var_B8]
0x1802e711f  mov     edi, eax
0x1802e7121  call    ??1?$CMemString@UCMemString_PolicyLocalMem@@@@QEAA@XZ; CMemString<CMemString_PolicyLocalMem>::~CMemString<CMemString_PolicyLocalMem>(void)
0x1802e7126  test    edi, edi
0x1802e7128  js      loc_1802E747D
0x1802e712e  lea     rcx, [rbp+57h+hstringHeader]; string
0x1802e7132  mov     [rbp+57h+var_B0], r13
0x1802e7136  call    ??$?0$0BH@@StringReference@Internal@Windows@@QEAA@AEAY0BH@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[23])
0x1802e713b  lea     rdx, [rbp+57h+var_B0]
0x1802e713f  mov     rcx, [rax]
0x1802e7142  call    ??$GetActivationFactory@V?$ComPtr@UIUriRuntimeClassFactory@Foundation@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIUriRuntimeClassFactory@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory>>)
0x1802e7147  mov     edi, eax
0x1802e7149  test    eax, eax
0x1802e714b  js      short loc_1802E71AD
0x1802e714d  mov     rsi, [rbp+57h+var_B0]
0x1802e7151  lea     rcx, [rbp+57h+string]
0x1802e7155  mov     [rbp+57h+string], r13
0x1802e7159  mov     rax, [rsi]
0x1802e715c  mov     rdi, [rax+30h]
0x1802e7160  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1802e7165  mov     rdx, [rbp+57h+var_80]; unsigned __int16 *
0x1802e7169  lea     rcx, [rbp+57h+hstringHeader]; this
0x1802e716d  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x1802e7172  mov     rdx, qword ptr [rbp+57h+hstringHeader.Reserved]
0x1802e7176  lea     r8, [rbp+57h+string]
0x1802e717a  mov     rcx, rsi
0x1802e717d  mov     rax, rdi
0x1802e7180  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802e7185  mov     edi, eax
0x1802e7187  test    eax, eax
0x1802e7189  js      short loc_1802E71A4
0x1802e718b  mov     rcx, [rbp+57h+var_A0]
0x1802e718f  mov     rdx, [rbp+57h+string]
0x1802e7193  mov     rax, [rcx]
0x1802e7196  mov     rax, [rax+88h]
0x1802e719d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802e71a2  mov     edi, eax
0x1802e71a4  lea     rcx, [rbp+57h+string]
0x1802e71a8  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1802e71ad  lea     rcx, [rbp+57h+var_B0]
0x1802e71b1  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1802e71b6  test    edi, edi
0x1802e71b8  js      loc_1802E747D
0x1802e71be  mov     r9, [rbp+57h+pv]
0x1802e71c2  lea     rcx, __ImageBase
0x1802e71c9  mov     r8, [rbp+57h+var_80]
0x1802e71cd  mov     edx, 2575h
0x1802e71d2  call    ShellConstructMessageStringW
0x1802e71d7  xor     ecx, ecx; hMem
0x1802e71d9  mov     r14, rax
0x1802e71dc  call    cs:__imp_LocalFree
0x1802e71e2  mov     [rbp+57h+var_B0], r14
0x1802e71e6  test    r14, r14
0x1802e71e9  jz      short loc_1802E71F1
0x1802e71eb  cmp     [r14], r13w
0x1802e71ef  jnz     short loc_1802E7200
0x1802e71f1  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1802e71f6  mov     edi, eax
0x1802e71f8  test    eax, eax
0x1802e71fa  js      loc_1802E72BA
0x1802e7200  mov     r9d, 36h ; '6'; unsigned int
0x1802e7206  mov     [rbp+57h+var_A8], r13
0x1802e720a  lea     rdx, ?RuntimeClass_Windows_ApplicationModel_DataTransfer_HtmlFormatHelper@@3QBGB; "Windows.ApplicationModel.DataTransfer.H"...
0x1802e7211  mov     [rbp+57h+var_48], r13
0x1802e7215  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1802e7219  lea     r8d, [r9+1]; unsigned int
0x1802e721d  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1802e7222  mov     rdi, [rbp+57h+var_48]
0x1802e7226  lea     rcx, [rbp+57h+var_A8]
0x1802e722a  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1802e722f  lea     r8, [rbp+57h+var_A8]
0x1802e7233  mov     rcx, rdi
0x1802e7236  lea     rdx, _GUID_e22e7749_dd70_446f_aefc_61cee59f655e
0x1802e723d  call    cs:__imp_RoGetActivationFactory
0x1802e7243  mov     edi, eax
0x1802e7245  test    eax, eax
0x1802e7247  js      short loc_1802E72B1
0x1802e7249  mov     rsi, [rbp+57h+var_A8]
0x1802e724d  xor     ecx, ecx; string
0x1802e724f  mov     [rbp+57h+string], r13
0x1802e7253  mov     rax, [rsi]
0x1802e7256  mov     rdi, [rax+38h]
0x1802e725a  call    cs:__imp_WindowsDeleteString
0x1802e7260  lea     rdx, [rbp+57h+var_B8]
0x1802e7264  mov     [rbp+57h+string], r13
0x1802e7268  lea     rcx, [rbp+57h+hstringHeader]
0x1802e726c  mov     [rbp+57h+var_B8], r14
0x1802e7270  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1802e7275  lea     r8, [rbp+57h+string]
0x1802e7279  mov     rcx, rsi
0x1802e727c  mov     rdx, [rax+18h]
0x1802e7280  mov     rax, rdi
0x1802e7283  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802e7288  mov     edi, eax
0x1802e728a  test    eax, eax
0x1802e728c  js      short loc_1802E72A7
0x1802e728e  mov     rcx, [rbp+57h+var_A0]
0x1802e7292  mov     rdx, [rbp+57h+string]
0x1802e7296  mov     rax, [rcx]
0x1802e7299  mov     rax, [rax+90h]
0x1802e72a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802e72a5  mov     edi, eax
0x1802e72a7  mov     rcx, [rbp+57h+string]; string
0x1802e72ab  call    cs:__imp_WindowsDeleteString
0x1802e72b1  lea     rcx, [rbp+57h+var_A8]
0x1802e72b5  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1802e72ba  lea     rcx, [rbp+57h+var_B0]
0x1802e72be  call    ??1?$CMemString@UCMemString_PolicyLocalMem@@@@QEAA@XZ; CMemString<CMemString_PolicyLocalMem>::~CMemString<CMemString_PolicyLocalMem>(void)
0x1802e72c3  test    edi, edi
0x1802e72c5  js      loc_1802E747D
0x1802e72cb  mov     rax, [r15]
0x1802e72ce  lea     rcx, [rbp+57h+var_B0]
0x1802e72d2  mov     [rbp+57h+var_B0], r13
0x1802e72d6  mov     rdi, [rax]
0x1802e72d9  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1802e72de  lea     r8, [rbp+57h+var_B0]
0x1802e72e2  mov     rcx, r15
0x1802e72e5  lea     rdx, _GUID_8a322201_0a87_46c1_9c77_7620e0cc5bbc
0x1802e72ec  mov     rax, rdi
0x1802e72ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802e72f4  mov     edi, eax
0x1802e72f6  test    eax, eax
0x1802e72f8  js      loc_1802E745C
0x1802e72fe  mov     [rbp+57h+var_78], r13
0x1802e7302  call    ?GetScaleFactorForPart@CLauncherSettings@@QEAA?AW4DEVICE_SCALE_FACTOR@@W4ScalablePart@@@Z; CLauncherSettings::GetScaleFactorForPart(ScalablePart)
0x1802e7307  mov     rsi, [rbp+57h+var_B0]
0x1802e730b  xorps   xmm0, xmm0
0x1802e730e  mov     ecx, 64h ; 'd'
0x1802e7313  mov     [rbp+57h+var_98], r13
0x1802e7317  cmp     eax, ecx
0x1802e7319  cmovl   eax, ecx
0x1802e731c  lea     rcx, [rbp+57h+var_78]
0x1802e7320  cvtsi2ss xmm0, rax
0x1802e7325  mulss   xmm0, cs:__real@41f00000
0x1802e732d  divss   xmm0, cs:__real@42c80000
0x1802e7335  cvttss2si eax, xmm0
0x1802e7339  mov     dword ptr [rbp+57h+var_98], eax
0x1802e733c  mov     dword ptr [rbp+57h+var_98+4], eax
0x1802e733f  mov     rax, [rsi]
0x1802e7342  mov     rdi, [rax+20h]
0x1802e7346  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1802e734b  mov     rdx, [rbp+57h+var_98]
0x1802e734f  lea     r9, [rbp+57h+var_78]
0x1802e7353  mov     r8d, 9
0x1802e7359  mov     rcx, rsi
0x1802e735c  mov     rax, rdi
0x1802e735f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802e7364  mov     edi, eax
0x1802e7366  test    eax, eax
0x1802e7368  js      loc_1802E7453
0x1802e736e  lea     rcx, [rbp+57h+var_98]
0x1802e7372  mov     dword ptr [rbp+57h+string], r13d
  ... truncated ...
```
