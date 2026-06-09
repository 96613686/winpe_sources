# SyncProviderRecycleBinLinks::UpdateLocation(IShellFolder *)

- ea: `0x180085cb8`
- end: `0x180086a51`
- name: `?UpdateLocation@SyncProviderRecycleBinLinks@@QEAAJPEAUIShellFolder@@@Z`
- size: `3481`
- prototype: `int(SyncProviderRecycleBinLinks *__hidden this, struct IShellFolder *)`
- caller_count: `1`
- callee_count: `23`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180085ab0`

## callees

- `0x18000f05c`
- `0x18003cd64`
- `0x180047d00`
- `0x180061090`
- `0x180085cb8`
- `0x180088280`
- `0x18009c148`
- `0x18009c168`
- `0x1800ac89c`
- `0x1800ad7dc`
- `0x1800af208`
- `0x1800af998`
- `0x1800b4154`
- `0x1800f8b50`
- `0x1801bb298`
- `0x1801bb590`
- `0x1801c1444`
- `0x18021e0f8`
- `0x180233280`
- `0x18023378c`
- `0x1803575e0`
- `0x180357604`
- `0x180571010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180085df3`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180085df3`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180085dab`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180085dab`
- `USER32!LoadImageW` at `0x180085e7c`
- `USER32!LoadImageW` at `0x180085e7c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800869f9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800869f9`
- `DUI70!?ContentProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x180085e89`
- `DUI70!?GetRoot@Element@DirectUI@@QEAAPEAV12@XZ` at `0x180085e32`
- `DUI70!?GetRoot@Element@DirectUI@@QEAAPEAV12@XZ` at `0x180085e32`
- `DUI70!?SetVisible@Element@DirectUI@@QEAAJ_N@Z` at `0x180086495`
- `DUI70!?SetVisible@Element@DirectUI@@QEAAJ_N@Z` at `0x180086495`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x180086483`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x180086483`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x180085f99`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x180086073`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x1800860e2`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x180086142`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x1800861bb`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x180086350`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x180086568`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x1800865f5`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x180086682`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x18008670f`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x180086785`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x1800867fb`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x180086866`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x1800868c7`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x18008691e`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x180086968`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x1800869cf`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x180085f99`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x180086073`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x1800860e2`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x180086142`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x1800861bb`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x180086350`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x180086568`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x1800865f5`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x180086682`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x18008670f`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x180086785`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x1800867fb`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x180086866`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x1800868c7`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x18008691e`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x180086968`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x1800869cf`
- `DUI70!?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z` at `0x180086396`
- `DUI70!?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z` at `0x180086396`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x180086462`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x180086462`
- `DUI70!?RemoveLocalValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZ@Z` at `0x180085e93`
- `DUI70!?RemoveLocalValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZ@Z` at `0x180085e93`
- `DUI70!StrToID` at `0x180085dc1`
- `DUI70!StrToID` at `0x180085ede`
- `DUI70!StrToID` at `0x180085dc1`
- `DUI70!StrToID` at `0x180085ede`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180085dcd`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180085eea`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180085dcd`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180085eea`
- `DUI70!?StartDefer@Element@DirectUI@@QEAAXPEAK@Z` at `0x180085fb4`
- `DUI70!?StartDefer@Element@DirectUI@@QEAAXPEAK@Z` at `0x180085fb4`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x1800864b9`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x180086599`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x180086626`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x1800866b3`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x1800864b9`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x180086599`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x180086626`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x1800866b3`
- `DUI70!?Create@DUIXmlParser@DirectUI@@SAJPEAPEAV12@P6APEAVValue@2@PEBGPEAX@Z2P6AX11H2@Z2@Z` at `0x180085f2d`
- `DUI70!?Create@DUIXmlParser@DirectUI@@SAJPEAPEAV12@P6APEAVValue@2@PEBGPEAX@Z2P6AX11H2@Z2@Z` at `0x180085f2d`
- `DUI70!?SetXMLFromResource@DUIXmlParser@DirectUI@@QEAAJIPEAUHINSTANCE__@@0@Z` at `0x180085f75`
- `DUI70!?SetXMLFromResource@DUIXmlParser@DirectUI@@QEAAJIPEAUHINSTANCE__@@0@Z` at `0x180085f75`
- `ext-ms-win-shell-fileplaceholder-l1-1-0!FECommon_CSyncRootManager_CreateInstance` at `0x18008603b`
- `ext-ms-win-shell-fileplaceholder-l1-1-0!FECommon_CSyncRootManager_CreateInstance` at `0x18008603b`
- `Windows.Storage!SHGetItemFromObject` at `0x180085d06`
- `Windows.Storage!SHGetItemFromObject` at `0x180085d06`

## string_xrefs

- `0x180085dec`: `imageres.dll`
- `0x180085ed7`: `SyncProviderLinks`
- `0x18008638b`: `LinkTemplate`

## pseudocode

```c
// Hidden C++ exception states: #wind=19
__int64 __fastcall SyncProviderRecycleBinLinks::UpdateLocation(SyncProviderRecycleBinLinks *this, IUnknown *a2)
{
  HRESULT v4; // eax
  unsigned int LastError; // ebx
  void *v6; // rcx
  __int64 v8; // rax
  int v9; // eax
  __int64 v10; // rdx
  unsigned __int16 v11; // ax
  DirectUI::Element *Descendent; // rdi
  HMODULE Library; // rbx
  const char *v14; // r9
  struct DirectUI::Element *Root; // rax
  __int64 v16; // rax
  HWND v17; // rax
  HANDLE ImageW; // rbx
  int v19; // eax
  unsigned __int16 v20; // ax
  DirectUI::DUIXmlParser *v21; // rbx
  int v22; // eax
  int v23; // edi
  char *v24; // rax
  int v25; // edx
  unsigned int v26; // edi
  __int64 v27; // rax
  int v28; // eax
  __int64 v29; // rsi
  __int64 (__fastcall *v30)(__int64, __int64 *); // rdi
  int v31; // eax
  int v32; // eax
  int v33; // eax
  unsigned int i; // r13d
  __int64 v35; // rsi
  __int64 (__fastcall *v36)(__int64, _QWORD, GUID *, HMODULE *); // rdi
  int v37; // eax
  HMODULE v38; // rsi
  __int64 (__fastcall *v39)(HMODULE, unsigned __int16 **); // rdi
  int v40; // eax
  HMODULE v41; // rsi
  __int64 (__fastcall *v42)(HMODULE, __int64 *); // rdi
  int v43; // eax
  int v44; // eax
  int v45; // eax
  int Element; // eax
  char v47; // r12
  HMODULE v48; // rsi
  __int64 (__fastcall *v49)(HMODULE, unsigned __int16 **); // rdi
  int v50; // eax
  SyncProviderRecycleBinLinks::ElementData *v51; // rax
  __int64 v52; // rdx
  int updated; // eax
  int v54; // eax
  int v55; // eax
  void *v56; // rcx
  int bIgnoreCase; // [rsp+20h] [rbp-E0h]
  int bIgnoreCasea; // [rsp+20h] [rbp-E0h]
  _QWORD v59[3]; // [rsp+30h] [rbp-D0h] BYREF
  const unsigned __int16 *v60[3]; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v61[2]; // [rsp+60h] [rbp-A0h] BYREF
  char v62; // [rsp+70h] [rbp-90h]
  struct DirectUI::DUIXmlParser *v63; // [rsp+78h] [rbp-88h]
  char v64; // [rsp+80h] [rbp-80h]
  int cy[2]; // [rsp+88h] [rbp-78h] BYREF
  struct DirectUI::DUIXmlParser *v66; // [rsp+90h] [rbp-70h] BYREF
  DirectUI::Element *v67; // [rsp+98h] [rbp-68h] BYREF
  __int64 v68; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v69; // [rsp+A8h] [rbp-58h] BYREF
  HMODULE v70; // [rsp+B0h] [rbp-50h] BYREF
  void *ppv; // [rsp+B8h] [rbp-48h] BYREF
  SyncProviderRecycleBinLinks *v72; // [rsp+C0h] [rbp-40h] BYREF
  unsigned int v73; // [rsp+C8h] [rbp-38h] BYREF
  unsigned int v74; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int16 *v75; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v76; // [rsp+E0h] [rbp-20h]
  __int64 v77; // [rsp+E8h] [rbp-18h]
  __int64 v78; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v79; // [rsp+F8h] [rbp-8h]
  __int64 v80; // [rsp+100h] [rbp+0h]
  unsigned __int16 *v81; // [rsp+108h] [rbp+8h] BYREF
  __int64 v82; // [rsp+110h] [rbp+10h]
  __int64 v83; // [rsp+118h] [rbp+18h]
  LPCWCH lpString2; // [rsp+120h] [rbp+20h] BYREF
  __int64 v85; // [rsp+128h] [rbp+28h]
  __int64 v86; // [rsp+130h] [rbp+30h]
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+78h]

  ppv = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
  v4 = SHGetItemFromObject(a2, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, &ppv);
  LastError = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5B,
      (unsigned int)"shell\\shell32\\syncproviderrecyclebin.cpp",
      (const char *)(unsigned int)v4,
      bIgnoreCase);
    v6 = ppv;
    if ( ppv )
    {
      ppv = 0;
      (*(void (__fastcall **)(void *))(*(_QWORD *)v6 + 16LL))(v6);
    }
    return LastError;
  }
  lpString2 = 0;
  v85 = 0;
  v86 = 0;
  v8 = *(_QWORD *)ppv;
  v85 = -1;
  v86 = -1;
  v9 = (*(__int64 (__fastcall **)(void *, __int64, LPCWCH *))(v8 + 40))(ppv, 2147647488LL, &lpString2);
  LastError = v9;
  if ( v9 < 0 )
  {
    v10 = 94;
LABEL_18:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"shell\\shell32\\syncproviderrecyclebin.cpp",
      (const char *)(unsigned int)v9,
      bIgnoreCase);
    goto LABEL_73;
  }
  if ( CompareStringOrdinal(L"::{645FF040-5081-101B-9F08-00AA002F954E}", -1, lpString2, -1, 1) == 2 )
  {
    v11 = StrToID(L"RecycleBinLogo");
    Descendent = DirectUI::Element::FindDescendent(this, v11);
    if ( Descendent )
    {
      Library = LoadLibraryExW(L"imageres.dll", 0, 2u);
      v70 = Library;
      if ( !Library )
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x68,
                      (unsigned int)"shell\\shell32\\syncproviderrecyclebin.cpp",
                      v14);
        wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&v70);
LABEL_73:
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpString2);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
        return LastError;
      }
      cy[0] = 32;
      cy[1] = 32;
      Root = DirectUI::Element::GetRoot(this);
      v16 = element_cast<DirectUI::HWNDElement>(Root);
      v17 = (HWND)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v16 + 360LL))(v16);
      SHLogicalToPhysicalDPI(v17, (struct tagSIZE *)cy);
      ImageW = LoadImageW(Library, (LPCWSTR)0x36, 1u, cy[0], cy[1], 0);
      *(_QWORD *)cy = ImageW;
      DirectUI::Element::RemoveLocalValue(Descendent, DirectUI::Element::ContentProp);
      *(_QWORD *)cy = 0;
      v19 = DUI_SetElementIcon(Descendent, ImageW, 0);
      if ( v19 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x70,
          (unsigned int)"shell\\shell32\\syncproviderrecyclebin.cpp",
          (const char *)(unsigned int)v19,
          bIgnoreCasea);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HICON__ *,int (*)(HICON__ *),&int DestroyIcon(HICON__ *),wistd::integral_constant<unsigned __int64,0>,HICON__ *,HICON__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HICON__ *,int (*)(HICON__ *),&int DestroyIcon(HICON__ *),wistd::integral_constant<unsigned __int64,0>,HICON__ *,HICON__ *,0,std::nullptr_t>>>(cy);
      wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&v70);
    }
    v20 = StrToID(L"SyncProviderLinks");
    v67 = DirectUI::Element::FindDescendent(this, v20);
    if ( !v67 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x74,
        (unsigned int)"shell\\shell32\\syncproviderrecyclebin.cpp",
        (const char *)0x80070490LL,
        bIgnoreCasea);
      LastError = -2147023728;
      goto LABEL_73;
    }
    v66 = 0;
    v9 = DirectUI::DUIXmlParser::Create(&v66, 0, 0, 0, 0);
    LastError = v9;
    if ( v9 < 0 )
    {
      v10 = 119;
      goto LABEL_18;
    }
    v21 = v66;
    v63 = v66;
    v64 = 1;
    v22 = DirectUI::DUIXmlParser::SetXMLFromResource(v66, 0x44u, g_hinst, &_ImageBase);
    v23 = v22;
    if ( v22 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x7D,
        (unsigned int)"shell\\shell32\\syncproviderrecyclebin.cpp",
        (const char *)(unsigned int)v22,
        bIgnoreCase);
      DirectUI::DUIXmlParser::Destroy(v21);
LABEL_72:
      LastError = v23;
      goto LABEL_73;
    }
    v72 = this;
    v73 = 0;
    DirectUI::Element::StartDefer(this, &v73);
    v24 = (char *)this + 208;
    *(_QWORD *)cy = &v67;
    if ( *((_QWORD *)this + 28) )
    {
      v25 = 1;
      v26 = 0;
      do
      {
        if ( v26 >= *((_DWORD *)this + 53) )
          break;
        v27 = *((_QWORD *)this + 28);
        if ( *(_DWORD *)(v27 + 24LL * v26) == 1 )
          v25 = CSimpleHashTable_DirectUI::Element___SyncProviderRecycleBinLinks::ElementData___CDefaultHashPolicy_DirectUI::Element____CDefaultKeyCompare_DirectUI::Element____CDefaultResizePolicy_CDefaultRehashPolicy_::s_EnumAdaptor__lambda_bbd800a050a3b62209283f06f1265ba1___(
                  cy,
                  v27 + 8 + 24LL * v26,
                  v27 + 16 + 24LL * v26);
        ++v26;
      }
      while ( v25 );
      v24 = (char *)this + 208;
    }
    CSimpleHashTable<unsigned short const *,NewMenuEntry *,CCaseInsensitiveStringHashPolicy,CCaseInsensitiveStringCompare,CDefaultResizePolicy,CDefaultRehashPolicy>::RemoveAll(v24);
    v69 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v69);
    v28 = FECommon_CSyncRootManager_CreateInstance(&GUID_a2ceecd8_bae5_49ed_939b_cd07bf7b02ad, &v69);
    v23 = v28;
    if ( v28 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x89,
        (unsigned int)"shell\\shell32\\syncproviderrecyclebin.cpp",
        (const char *)(unsigned int)v28,
        bIgnoreCase);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v69);
      DirectUI::AutoDefer::EndDefer((DirectUI::AutoDefer *)&v72);
      DirectUI::DUIXmlParser::Destroy(v21);
      goto LABEL_72;
    }
    v68 = 0;
    v29 = v69;
    v30 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v69 + 24LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v68);
    v31 = v30(v29, &v68);
    v23 = v31;
    if ( v31 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8C,
        (unsigned int)"shell\\shell32\\syncproviderrecyclebin.cpp",
        (const char *)(unsigned int)v31,
        bIgnoreCase);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v68);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v69);
      DirectUI::AutoDefer::EndDefer((DirectUI::AutoDefer *)&v72);
      DirectUI::DUIXmlParser::Destroy(v21);
      goto LABEL_72;
    }
    v74 = 0;
    v32 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v68 + 24LL))(v68, &v74);
    v23 = v32;
    if ( v32 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8F,
        (unsigned int)"shell\\shell32\\syncproviderrecyclebin.cpp",
        (const char *)(unsigned int)v32,
        bIgnoreCase);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v68);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v69);
      DirectUI::AutoDefer::EndDefer((DirectUI::AutoDefer *)&v72);
      DirectUI::DUIXmlParser::Destroy(v21);
      goto LABEL_72;
    }
    memset(v59, 0, sizeof(v59));
    v33 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::Initialize(
            v59,
            g_hinst,
            51542);
    v23 = v33;
    if ( v33 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x92,
        (unsigned int)"shell\\shell32\\syncproviderrecyclebin.cpp",
        (const char *)(unsigned int)v33,
        bIgnoreCase);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v59);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v68);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v69);
      DirectUI::AutoDefer::EndDefer((DirectUI::AutoDefer *)&v72);
      DirectUI::DUIXmlParser::Destroy(v21);
      goto LABEL_72;
    }
    for ( i = 0; i < v74; ++i )
    {
      v70 = 0;
      v35 = v68;
      v36 = *(__int64 (__fastcall **)(__int64, _QWORD, GUID *, HMODULE *))(*(_QWORD *)v68 + 32LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v70);
      v37 = v36(v35, i, &GUID_ca01c124_2769_4576_bf12_8a54ee671a86, &v70);
      v23 = v37;
      if ( v37 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x96,
          (unsigned int)"shell\\shell32\\syncproviderrecyclebin.cpp",
          (const char *)(unsigned int)v37,
          bIgnoreCase);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v70);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v59);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v68);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v69);
        DirectUI::AutoDefer::EndDefer((DirectUI::AutoDefer *)&v72);
        DirectUI::DUIXmlParser::Destroy(v21);
        goto LABEL_72;
      }
      v75 = 0;
      v76 = 0;
      v77 = 0;
      v38 = v70;
      v39 = *(__int64 (__fastcall **)(HMODULE, unsigned __int16 **))(*(_QWORD *)v70 + 216LL);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v75);
      v76 = -1;
      v77 = -1;
      v40 = v39(v38, &v75);
      v23 = v40;
      if ( v40 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x99,
          (unsigned int)"shell\\shell32\\syncproviderrecyclebin.cpp",
          (const char *)(unsigned int)v40,
          bIgnoreCase);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v75);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v70);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v59);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v68);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v69);
        DirectUI::AutoDefer::EndDefer((DirectUI::AutoDefer *)&v72);
        DirectUI::DUIXmlParser::Destroy(v21);
        goto LABEL_72;
      }
      if ( v75 )
      {
        v78 = 0;
        v79 = 0;
        v80 = 0;
        v41 = v70;
        v42 = *(__int64 (__fastcall **)(HMODULE, __int64 *))(*(_QWORD *)v70 + 56LL);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v78);
        v79 = -1;
        v80 = -1;
        v43 = v42(v41, &v78);
        v23 = v43;
        if ( v43 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x9E,
            (unsigned int)"shell\\shell32\\syncproviderrecyclebin.cpp",
            (const char *)(unsigned int)v43,
            bIgnoreCase);
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v78);
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v75);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v70);
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v59);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v68);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v69);
          DirectUI::AutoDefer::EndDefer((DirectUI::AutoDefer *)&v72);
          DirectUI::DUIXmlParser::Destroy(v21);
          goto LABEL_72;
        }
        memset(v60, 0, sizeof(v60));
        if ( i + 1 >= v74 )
        {
          v45 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
                  v60,
                  v78,
                  -1);
          v23 = v45;
          if ( v45 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xA7,
              (unsigned int)"shell\\shell32\\syncproviderrecyclebin.cpp",
              (const char *)(unsigned int)v45,
              bIgnoreCase);
            Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v60);
            Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v78);
            Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v75);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v70);
            Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v59);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v68);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v69);
            DirectUI::AutoDefer::EndDefer((DirectUI::AutoDefer *)&v72);
            DirectUI::DUIXmlParser::Destroy(v21);
            goto LABEL_72;
          }
        }
        else
        {
          v44 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
                  v60,
                  L"%s%s",
                  v78,
                  v59[0]);
          v23 = v44;
          if ( v44 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xA3,
              (unsigned int)"shell\\shell32\\syncproviderrecyclebin.cpp",
              (const char *)(unsigned int)v44,
              bIgnoreCase);
            Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v60);
            Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v78);
            Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v75);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v70);
            Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v59);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v68);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v69);
            DirectUI::AutoDefer::EndDefer((DirectUI::AutoDefer *)&v72);
            DirectUI::DUIXmlParser::Destroy(v21);
            goto LABEL_72;
          }
        }
        *(_QWORD *)cy = 0;
        Element = DirectUI::DUIXmlParser::CreateElement(v66, L"LinkTemplate", 0, 0, 0, (struct DirectUI::Element **)cy);
        v23 = Element;
        if ( Element < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xAB,
            (unsigned int)"shell\\shell32\\syncproviderrecyclebin.cpp",
            (const char *)(unsigned int)Element,
            bIgnoreCase);
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v60);
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v78);
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v75);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v70);
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v59);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v68);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v69);
          DirectUI::AutoDefer::EndDefer((DirectUI::AutoDefer *)&v72);
          DirectUI::DUIXmlParser::Destroy(v21);
          goto LABEL_72;
        }
        v61[1] = cy;
        v47 = 1;
        v62 = 1;
        v81 = 0;
        v82 = 0;
        v83 = 0;
        v48 = v70;
        v49 = *(__int64 (__fastcall **)(HMODULE, unsigned __int16 **))(*(_QWORD *)v70 + 40LL);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v81);
        v82 = -1;
        v83 = -1;
        v50 = v49(v48, &v81);
        v23 = v50;
        if ( v50 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xAF,
            (unsigned int)"shell\\shell32\\syncproviderrecyclebin.cpp",
            (const char *)(unsigned int)v50,
            bIgnoreCase);
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v81);
          DirectUI::Element::Destroy(*(DirectUI::Element **)cy, 1);
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v60);
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v78);
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v75);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v70);
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v59);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v68);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v69);
          DirectUI::AutoDefer::EndDefer((DirectUI::AutoDefer *)&v72);
          DirectUI::DUIXmlParser::Destroy(v21);
          goto LABEL_72;
        }
        v51 = (SyncProviderRecycleBinLinks::ElementData *)operator new(
                                                            0x10u,
                                                            (const struct std::nothrow_t *)std::nothrow);
        v61[0] = v51;
        if ( v51 )
          v51 = (SyncProviderRecycleBinLinks::ElementData *)SyncProviderRecycleBinLinks::ElementData::ElementData(
                                                              v51,
                                                              v81,
                                                              v75);
        v61[0] = v51;
        if ( *(_QWORD *)v51 && *((_QWORD *)v51 + 1) )
        {
          updated = CSimpleHashTable<DirectUI::Element *,SyncProviderRecycleBinLinks::ElementData *,CDefaultHashPolicy<DirectUI::Element *>,CDefaultKeyCompare<DirectUI::Element *>,CDefaultResizePolicy,CDefaultRehashPolicy>::_AddUpdateItem(
                      (char *)this + 208,
                      v52,
                      cy,
                      v61);
          v23 = updated;
          if ( updated < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xB4,
              (unsigned int)"shell\\shell32\\syncproviderrecyclebin.cpp",
              (const char *)(unsigned int)updated,
              bIgnoreCase);
            Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v81);
            DirectUI::Element::Destroy(*(DirectUI::Element **)cy, 1);
            Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v60);
            Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v78);
            Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v75);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v70);
            Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v59);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v68);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v69);
            DirectUI::AutoDefer::EndDefer((DirectUI::AutoDefer *)&v72);
            DirectUI::DUIXmlParser::Destroy(v21);
            goto LABEL_72;
          }
          v54 = DirectUI::Element::Add(v67, *(struct DirectUI::Element **)cy);
          v23 = v54;
          if ( v54 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xB7,
              (unsigned int)"shell\\shell32\\syncproviderrecyclebin.cpp",
              (const char *)(unsigned int)v54,
              bIgnoreCase);
            Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v81);
            DirectUI::Element::Destroy(*(DirectUI::Element **)cy, 1);
            Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v60);
            Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v78);
            Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v75);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v70);
            Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v59);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v68);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v69);
            DirectUI::AutoDefer::EndDefer((DirectUI::AutoDefer *)&v72);
            DirectUI::DUIXmlParser::Destroy(v21);
            goto LABEL_72;
          }
          v47 = 0;
          v62 = 0;
          v55 = DirectUI::Element::SetContentString(*(DirectUI::Element **)cy, v60[0]);
          v23 = v55;
          if ( v55 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xB9,
              (unsigned int)"shell\\shell32\\syncproviderrecyclebin.cpp",
              (const char *)(unsigned int)v55,
              bIgnoreCase);
            Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v81);
            Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v60);
            Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v78);
            Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v75);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v70);
            Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v59);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v68);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v69);
            DirectUI::AutoDefer::EndDefer((DirectUI::AutoDefer *)&v72);
            DirectUI::DUIXmlParser::Destroy(v21);
            goto LABEL_72;
          }
          DirectUI::Element::SetVisible(*(DirectUI::Element **)cy, 1);
        }
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v81);
        if ( v47 )
        {
          v62 = 0;
          DirectUI::Element::Destroy(*(DirectUI::Element **)cy, 1);
        }
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v60);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v78);
      }
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v75);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v70);
    }
    if ( !*((_DWORD *)this + 52) )
    {
      v23 = -2147024883;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xBE,
        (unsigned int)"shell\\shell32\\syncproviderrecyclebin.cpp",
        (const char *)0x8007000DLL,
        bIgnoreCase);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v59);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v68);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v69);
      DirectUI::AutoDefer::EndDefer((DirectUI::AutoDefer *)&v72);
      DirectUI::DUIXmlParser::Destroy(v21);
      goto LABEL_72;
    }
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v59);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v68);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v69);
    DirectUI::AutoDefer::EndDefer((DirectUI::AutoDefer *)&v72);
    SyncProviderRecycleBinLinks::SetColors(this);
    DirectUI::DUIXmlParser::Destroy(v21);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpString2);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
    return 0;
  }
  else
  {
    if ( lpString2 )
    {
      CoTaskMemFree((LPVOID)lpString2);
      lpString2 = 0;
    }
    v85 = 0;
    v86 = 0;
    v56 = ppv;
    if ( ppv )
    {
      ppv = 0;
      (*(void (__fastcall **)(void *))(*(_QWORD *)v56 + 16LL))(v56);
    }
    return 2147943568LL;
  }
}

```

## disassembly

```asm
0x180085cb8  mov     [rsp-8+arg_10], rbx
0x180085cbd  push    rbp
0x180085cbe  push    rsi
0x180085cbf  push    rdi
0x180085cc0  push    r12
0x180085cc2  push    r13
0x180085cc4  push    r14
0x180085cc6  push    r15
0x180085cc8  lea     rbp, [rsp-40h]
0x180085ccd  sub     rsp, 140h
0x180085cd4  mov     rax, cs:__security_cookie
0x180085cdb  xor     rax, rsp
0x180085cde  mov     [rbp+70h+var_38], rax
0x180085ce2  mov     rbx, rdx
0x180085ce5  mov     r15, rcx
0x180085ce8  xor     r12d, r12d
0x180085ceb  mov     [rbp+70h+ppv], r12
0x180085cef  lea     rcx, [rbp+70h+ppv]
0x180085cf3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180085cf8  lea     r8, [rbp+70h+ppv]; ppv
0x180085cfc  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x180085d03  mov     rcx, rbx; punk
0x180085d06  call    cs:__imp_SHGetItemFromObject
0x180085d0c  mov     ebx, eax
0x180085d0e  test    eax, eax
0x180085d10  jns     short loc_180085D4C
0x180085d12  mov     rcx, [rbp+78h]; this
0x180085d16  mov     r9d, eax; char *
0x180085d19  lea     r8, aShellShell32Sy; "shell\\shell32\\syncproviderrecyclebin."...
0x180085d20  lea     edx, [r12+5Bh]; void *
0x180085d25  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180085d2a  nop
0x180085d2b  mov     rcx, [rbp+70h+ppv]
0x180085d2f  test    rcx, rcx
0x180085d32  jz      short loc_180085D45
0x180085d34  mov     [rbp+70h+ppv], r12
0x180085d38  mov     rax, [rcx]
0x180085d3b  mov     rax, [rax+10h]
0x180085d3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085d44  nop
0x180085d45  mov     eax, ebx
0x180085d47  jmp     loc_180086A2A
0x180085d4c  mov     [rbp+70h+lpString2], r12
0x180085d50  mov     [rbp+70h+var_48], r12
0x180085d54  mov     [rbp+70h+var_40], r12
0x180085d58  mov     rcx, [rbp+70h+ppv]
0x180085d5c  mov     rax, [rcx]
0x180085d5f  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180085d63  mov     [rbp+70h+var_48], rdi
0x180085d67  mov     [rbp+70h+var_40], rdi
0x180085d6b  lea     r8, [rbp+70h+lpString2]
0x180085d6f  mov     edx, 80028000h
0x180085d74  mov     rax, [rax+28h]
0x180085d78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085d7d  mov     ebx, eax
0x180085d7f  test    eax, eax
0x180085d81  jns     short loc_180085D92
0x180085d83  lea     r8, aShellShell32Sy; "shell\\shell32\\syncproviderrecyclebin."...
0x180085d8a  lea     edx, [rdi+5Fh]
0x180085d8d  jmp     loc_180085F41
0x180085d92  mov     esi, 1
0x180085d97  mov     [rsp+170h+bIgnoreCase], esi; bIgnoreCase
0x180085d9b  mov     r9d, edi; cchCount2
0x180085d9e  mov     r8, [rbp+70h+lpString2]; lpString2
0x180085da2  mov     edx, edi; cchCount1
0x180085da4  lea     rcx, String1; "::{645FF040-5081-101B-9F08-00AA002F954E"...
0x180085dab  call    cs:__imp_CompareStringOrdinal
0x180085db1  cmp     eax, 2
0x180085db4  jnz     loc_1800869F0
0x180085dba  lea     rcx, aRecyclebinlogo; "RecycleBinLogo"
0x180085dc1  call    cs:__imp_StrToID
0x180085dc7  movzx   edx, ax
0x180085dca  mov     rcx, r15
0x180085dcd  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180085dd3  mov     rdi, rax
0x180085dd6  lea     r14, aShellShell32Sy; "shell\\shell32\\syncproviderrecyclebin."...
0x180085ddd  test    rax, rax
0x180085de0  jz      loc_180085ED7
0x180085de6  xor     edx, edx; hFile
0x180085de8  lea     r8d, [rsi+1]; dwFlags
0x180085dec  lea     rcx, pszIconPath; "imageres.dll"
0x180085df3  call    cs:__imp_LoadLibraryExW
0x180085df9  mov     rbx, rax
0x180085dfc  mov     [rbp+70h+var_C0], rax
0x180085e00  test    rax, rax
0x180085e03  jnz     short loc_180085E24
0x180085e05  mov     rcx, [rbp+78h]; this
0x180085e09  mov     r8, r14; unsigned int
0x180085e0c  lea     edx, [rsi+67h]; void *
0x180085e0f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180085e14  mov     ebx, eax
0x180085e16  lea     rcx, [rbp+70h+var_C0]
0x180085e1a  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x180085e1f  jmp     loc_1800869D8
0x180085e24  mov     eax, 20h ; ' '
0x180085e29  mov     [rbp+70h+cy], eax
0x180085e2c  mov     [rbp+70h+cy+4], eax
0x180085e2f  mov     rcx, r15
0x180085e32  call    cs:__imp_?GetRoot@Element@DirectUI@@QEAAPEAV12@XZ; DirectUI::Element::GetRoot(void)
0x180085e38  mov     rcx, rax
0x180085e3b  call    ??$element_cast@VHWNDElement@DirectUI@@@@YAPEAVHWNDElement@DirectUI@@PEAVElement@1@@Z; element_cast<DirectUI::HWNDElement>(DirectUI::Element *)
0x180085e40  mov     rdx, rax
0x180085e43  mov     rcx, [rax]
0x180085e46  mov     rax, [rcx+168h]
0x180085e4d  mov     rcx, rdx
0x180085e50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085e55  mov     rcx, rax; HWND
0x180085e58  lea     rdx, [rbp+70h+cy]; struct tagSIZE *
0x180085e5c  call    ?SHLogicalToPhysicalDPI@@YAXPEAUHWND__@@PEAUtagSIZE@@@Z; SHLogicalToPhysicalDPI(HWND__ *,tagSIZE *)
0x180085e61  mov     [rsp+170h+fuLoad], r12d; fuLoad
0x180085e66  mov     eax, [rbp+70h+cy+4]
0x180085e69  mov     [rsp+170h+bIgnoreCase], eax; int
0x180085e6d  mov     r9d, [rbp+70h+cy]; cx
0x180085e71  mov     r8d, esi; type
0x180085e74  mov     edx, 36h ; '6'; name
0x180085e79  mov     rcx, rbx; hInst
0x180085e7c  call    cs:__imp_LoadImageW
0x180085e82  mov     rbx, rax
0x180085e85  mov     qword ptr [rbp+70h+cy], rax
0x180085e89  mov     rdx, cs:__imp_?ContentProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ; DirectUI::Element::ContentProp(void)
0x180085e90  mov     rcx, rdi
0x180085e93  call    cs:__imp_?RemoveLocalValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZ@Z; DirectUI::Element::RemoveLocalValue(DirectUI::PropertyInfo const * (*)(void))
0x180085e99  mov     qword ptr [rbp+70h+cy], r12
0x180085e9d  xor     r8d, r8d
0x180085ea0  mov     rdx, rbx
0x180085ea3  mov     rcx, rdi
0x180085ea6  call    ?DUI_SetElementIcon@@YAJPEAVElement@DirectUI@@PEAUHICON__@@W4ImageRtlMode@@@Z; DUI_SetElementIcon(DirectUI::Element *,HICON__ *,ImageRtlMode)
0x180085eab  mov     rcx, [rbp+78h]; this
0x180085eaf  test    eax, eax
0x180085eb1  jns     short loc_180085EC4
0x180085eb3  mov     r9d, eax; char *
0x180085eb6  mov     r8, r14; unsigned int
0x180085eb9  mov     edx, 70h ; 'p'; void *
0x180085ebe  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180085ec3  nop
0x180085ec4  lea     rcx, [rbp+70h+cy]
0x180085ec8  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHICON__@@P6AHPEAU1@@Z$1?DestroyIcon@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HICON__ *,int (*)(HICON__ *),&DestroyIcon(HICON__ *),wistd::integral_constant<unsigned __int64,0>,HICON__ *,HICON__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HICON__ *,int (*)(HICON__ *),&DestroyIcon(HICON__ *),wistd::integral_constant<unsigned __int64,0>,HICON__ *,HICON__ *,0,std::nullptr_t>>>(void)
0x180085ecd  nop
0x180085ece  lea     rcx, [rbp+70h+var_C0]
0x180085ed2  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x180085ed7  lea     rcx, aSyncproviderli; "SyncProviderLinks"
0x180085ede  call    cs:__imp_StrToID
0x180085ee4  movzx   edx, ax
0x180085ee7  mov     rcx, r15
0x180085eea  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180085ef0  mov     [rbp+70h+var_D8], rax
0x180085ef4  test    rax, rax
0x180085ef7  jnz     short loc_180085F18
0x180085ef9  mov     rcx, [rbp+78h]; this
0x180085efd  mov     r9d, 80070490h; char *
0x180085f03  mov     r8, r14; unsigned int
0x180085f06  lea     edx, [rax+74h]; void *
0x180085f09  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180085f0e  mov     ebx, 80070490h
0x180085f13  jmp     loc_1800869D8
0x180085f18  mov     [rbp+70h+var_E0], r12
0x180085f1c  mov     qword ptr [rsp+170h+bIgnoreCase], r12; int
0x180085f21  xor     r9d, r9d
0x180085f24  xor     r8d, r8d
0x180085f27  xor     edx, edx
0x180085f29  lea     rcx, [rbp+70h+var_E0]
0x180085f2d  call    cs:__imp_?Create@DUIXmlParser@DirectUI@@SAJPEAPEAV12@P6APEAVValue@2@PEBGPEAX@Z2P6AX11H2@Z2@Z; DirectUI::DUIXmlParser::Create(DirectUI::DUIXmlParser * *,DirectUI::Value * (*)(ushort const *,void *),void *,void (*)(ushort const *,ushort const *,int,void *),void *)
0x180085f33  mov     ebx, eax
0x180085f35  test    eax, eax
0x180085f37  jns     short loc_180085F52
0x180085f39  mov     r8, r14; unsigned int
0x180085f3c  mov     edx, 77h ; 'w'; void *
0x180085f41  mov     r9d, eax; char *
0x180085f44  mov     rcx, [rbp+78h]; this
0x180085f48  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180085f4d  jmp     loc_1800869D8
0x180085f52  mov     rbx, [rbp+70h+var_E0]
0x180085f56  mov     [rsp+170h+var_F8], rbx
0x180085f5b  mov     [rbp+70h+var_F0], sil
0x180085f5f  lea     r9, __ImageBase
0x180085f66  mov     r8, cs:g_hinst
0x180085f6d  mov     edx, 44h ; 'D'
0x180085f72  mov     rcx, rbx
0x180085f75  call    cs:__imp_?SetXMLFromResource@DUIXmlParser@DirectUI@@QEAAJIPEAUHINSTANCE__@@0@Z; DirectUI::DUIXmlParser::SetXMLFromResource(uint,HINSTANCE__ *,HINSTANCE__ *)
0x180085f7b  mov     edi, eax
0x180085f7d  test    eax, eax
0x180085f7f  jns     short loc_180085FA5
0x180085f81  mov     rcx, [rbp+78h]; this
0x180085f85  mov     r9d, eax; char *
0x180085f88  mov     r8, r14; unsigned int
0x180085f8b  mov     edx, 7Dh ; '}'; void *
0x180085f90  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180085f95  nop
0x180085f96  mov     rcx, rbx
0x180085f99  call    cs:__imp_?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ; DirectUI::DUIXmlParser::Destroy(void)
0x180085f9f  nop
0x180085fa0  jmp     loc_1800869D6
0x180085fa5  mov     [rbp+70h+var_B0], r15
0x180085fa9  mov     [rbp+70h+var_A8], r12d
0x180085fad  lea     rdx, [rbp+70h+var_A8]
0x180085fb1  mov     rcx, r15
0x180085fb4  call    cs:__imp_?StartDefer@Element@DirectUI@@QEAAXPEAK@Z; DirectUI::Element::StartDefer(ulong *)
0x180085fba  nop
0x180085fbb  lea     rax, [r15+0D0h]
0x180085fc2  lea     rcx, [rbp+70h+var_D8]
0x180085fc6  mov     qword ptr [rbp+70h+cy], rcx
0x180085fca  cmp     [r15+0E0h], r12
0x180085fd1  jz      short loc_18008601B
0x180085fd3  mov     edx, esi
0x180085fd5  mov     edi, r12d
0x180085fd8  cmp     edi, [r15+0D4h]
0x180085fdf  jnb     short loc_180086014
0x180085fe1  mov     eax, edi
0x180085fe3  lea     rcx, [rax+rax*2]
0x180085fe7  mov     rax, [r15+0E0h]
0x180085fee  cmp     [rax+rcx*8], esi
0x180085ff1  jnz     short loc_18008600E
0x180085ff3  lea     r8, [rax+10h]
0x180085ff7  lea     r8, [r8+rcx*8]
0x180085ffb  add     rax, 8
0x180085fff  lea     rdx, [rax+rcx*8]
0x180086003  lea     rcx, [rbp+70h+cy]
0x180086007  call    CSimpleHashTable_DirectUI__Element___SyncProviderRecycleBinLinks__ElementData___CDefaultHashPolicy_DirectUI__Element____CDefaultKeyCompare_DirectUI__Element____CDefaultResizePolicy_CDefaultRehashPolicy___s_EnumAdaptor__lambda_bbd800a050a3b62209283f06f1265ba1___
0x18008600c  mov     edx, eax
0x18008600e  add     edi, esi
0x180086010  test    edx, edx
0x180086012  jnz     short loc_180085FD8
0x180086014  lea     rax, [r15+0D0h]
0x18008601b  mov     rcx, rax
0x18008601e  call    ?RemoveAll@?$CSimpleHashTable@PEBGPEAUNewMenuEntry@@VCCaseInsensitiveStringHashPolicy@@VCCaseInsensitiveStringCompare@@VCDefaultResizePolicy@@VCDefaultRehashPolicy@@@@QEAAXXZ; CSimpleHashTable<ushort const *,NewMenuEntry *,CCaseInsensitiveStringHashPolicy,CCaseInsensitiveStringCompare,CDefaultResizePolicy,CDefaultRehashPolicy>::RemoveAll(void)
0x180086023  mov     [rbp+70h+var_C8], r12
0x180086027  lea     rcx, [rbp+70h+var_C8]
0x18008602b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180086030  lea     rdx, [rbp+70h+var_C8]
0x180086034  lea     rcx, _GUID_a2ceecd8_bae5_49ed_939b_cd07bf7b02ad
0x18008603b  call    cs:__imp_FECommon_CSyncRootManager_CreateInstance
0x180086041  mov     edi, eax
0x180086043  test    eax, eax
0x180086045  jns     short loc_18008607F
0x180086047  mov     rcx, [rbp+78h]; this
0x18008604b  mov     r9d, eax; char *
0x18008604e  mov     r8, r14; unsigned int
0x180086051  mov     edx, 89h; void *
0x180086056  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008605b  nop
0x18008605c  lea     rcx, [rbp+70h+var_C8]
0x180086060  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180086065  nop
0x180086066  lea     rcx, [rbp+70h+var_B0]; this
0x18008606a  call    ?EndDefer@AutoDefer@DirectUI@@QEAAXXZ; DirectUI::AutoDefer::EndDefer(void)
0x18008606f  nop
0x180086070  mov     rcx, rbx
0x180086073  call    cs:__imp_?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ; DirectUI::DUIXmlParser::Destroy(void)
0x180086079  nop
0x18008607a  jmp     loc_1800869D6
0x18008607f  mov     [rbp+70h+var_D0], r12
0x180086083  mov     rsi, [rbp+70h+var_C8]
0x180086087  mov     rax, [rsi]
0x18008608a  mov     rdi, [rax+18h]
0x18008608e  lea     rcx, [rbp+70h+var_D0]
0x180086092  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180086097  lea     rdx, [rbp+70h+var_D0]
0x18008609b  mov     rcx, rsi
0x18008609e  mov     rax, rdi
0x1800860a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800860a6  mov     edi, eax
0x1800860a8  test    eax, eax
0x1800860aa  jns     short loc_1800860EE
0x1800860ac  mov     rcx, [rbp+78h]; this
0x1800860b0  mov     r9d, eax; char *
0x1800860b3  mov     r8, r14; unsigned int
0x1800860b6  mov     edx, 8Ch; void *
0x1800860bb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800860c0  nop
0x1800860c1  lea     rcx, [rbp+70h+var_D0]
0x1800860c5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800860ca  nop
0x1800860cb  lea     rcx, [rbp+70h+var_C8]
0x1800860cf  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800860d4  nop
0x1800860d5  lea     rcx, [rbp+70h+var_B0]; this
0x1800860d9  call    ?EndDefer@AutoDefer@DirectUI@@QEAAXXZ; DirectUI::AutoDefer::EndDefer(void)
0x1800860de  nop
0x1800860df  mov     rcx, rbx
0x1800860e2  call    cs:__imp_?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ; DirectUI::DUIXmlParser::Destroy(void)
0x1800860e8  nop
0x1800860e9  jmp     loc_1800869D6
0x1800860ee  mov     [rbp+70h+var_A0], r12d
0x1800860f2  mov     rcx, [rbp+70h+var_D0]
0x1800860f6  mov     rax, [rcx]
0x1800860f9  lea     rdx, [rbp+70h+var_A0]
0x1800860fd  mov     rax, [rax+18h]
0x180086101  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086106  mov     edi, eax
0x180086108  test    eax, eax
0x18008610a  jns     short loc_18008614E
0x18008610c  mov     rcx, [rbp+78h]; this
0x180086110  mov     r9d, eax; char *
0x180086113  mov     r8, r14; unsigned int
0x180086116  mov     edx, 8Fh; void *
0x18008611b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180086120  nop
0x180086121  lea     rcx, [rbp+70h+var_D0]
0x180086125  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18008612a  nop
  ... truncated ...
```
