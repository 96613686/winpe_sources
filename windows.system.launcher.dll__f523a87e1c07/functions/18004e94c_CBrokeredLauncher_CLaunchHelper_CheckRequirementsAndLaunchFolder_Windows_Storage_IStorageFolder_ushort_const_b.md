# CBrokeredLauncher::CLaunchHelper::_CheckRequirementsAndLaunchFolder(Windows::Storage::IStorageFolder *,ushort const *,bool)

- ea: `0x18004e94c`
- end: `0x18004ee47`
- name: `?_CheckRequirementsAndLaunchFolder@CLaunchHelper@CBrokeredLauncher@@AEAAJPEAUIStorageFolder@Storage@Windows@@PEBG_N@Z`
- size: `1275`
- prototype: `__int64 __fastcall(CBrokeredLauncher::CLaunchHelper *__hidden this, struct Windows::Storage::IStorageFolder *, const unsigned __int16 *, bool)`
- caller_count: `1`
- callee_count: `19`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18004e7f8`

## callees

- `0x1800049bc`
- `0x18000f194`
- `0x18004c62c`
- `0x18004c690`
- `0x18004e94c`
- `0x18004f054`
- `0x1800561e0`
- `0x1800579c4`
- `0x1800591d4`
- `0x1800692bc`
- `0x18007e640`
- `0x180086c28`
- `0x180086ec4`
- `0x180086fb8`
- `0x18008d3f0`
- `0x1800e1050`
- `0x1800e23ac`
- `0x1800e2f64`
- `0x180111010`

## import_xrefs

- `Windows.Storage!STORAGE_CStorageItem_GetValidatedStorageItem` at `0x18004e9a3`
- `Windows.Storage!STORAGE_CStorageItem_GetValidatedStorageItem` at `0x18004e9a3`
- `Windows.Storage!SHOpenFolderAndSelectItems` at `0x18004ebf6`
- `Windows.Storage!SHOpenFolderAndSelectItems` at `0x18004ebf6`
- `Windows.Storage!__imp_GetShellItemFromStorageItem` at `0x18004eaa2`
- `Windows.Storage!__imp_GetShellItemFromStorageItem` at `0x18004eaa2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004ec30`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004ec30`

## string_xrefs

- `0x18004e9b8`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\brokeredlauncher.cpp`
- `0x18004e9fa`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\brokeredlauncher.cpp`
- `0x18004ea40`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\brokeredlauncher.cpp`
- `0x18004ea71`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\brokeredlauncher.cpp`
- `0x18004eab7`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\brokeredlauncher.cpp`
- `0x18004eafa`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\brokeredlauncher.cpp`
- `0x18004eb29`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\brokeredlauncher.cpp`
- `0x18004eb63`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\brokeredlauncher.cpp`
- `0x18004eb96`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\brokeredlauncher.cpp`
- `0x18004ec0b`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\brokeredlauncher.cpp`
- `0x18004ece9`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\brokeredlauncher.cpp`
- `0x18004ed3a`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\brokeredlauncher.cpp`
- `0x18004ed95`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\brokeredlauncher.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall CBrokeredLauncher::CLaunchHelper::_CheckRequirementsAndLaunchFolder(
        CBrokeredLauncher::CLaunchHelper *this,
        __int64 (__fastcall ***a2)(struct Windows::Storage::IStorageFolder *, GUID *, __int64 *),
        const unsigned __int16 *a3,
        char a4)
{
  int ValidatedStorageItem; // eax
  __int64 (__fastcall *v9)(struct Windows::Storage::IStorageFolder *, GUID *, __int64 *); // rbx
  int v10; // eax
  int v11; // eax
  int ShellItemFromStorageItem; // eax
  int v13; // edx
  int v14; // r8d
  int v15; // r9d
  int Related; // eax
  int v17; // eax
  int v18; // eax
  int v19; // eax
  HRESULT v20; // eax
  ITEMIDLIST *v21; // rcx
  int v22; // eax
  int v23; // eax
  __int64 (__fastcall ***v24)(_QWORD, GUID *, LPCITEMIDLIST *); // rbx
  int v25; // eax
  const char *v26; // r9
  __int64 result; // rax
  int v28; // [rsp+20h] [rbp-98h]
  int v29; // [rsp+20h] [rbp-98h]
  int v30; // [rsp+20h] [rbp-98h]
  LPCITEMIDLIST pidlFolder; // [rsp+30h] [rbp-88h] BYREF
  struct IShellItem *v32; // [rsp+38h] [rbp-80h] BYREF
  __int64 v33; // [rsp+40h] [rbp-78h] BYREF
  struct IShellItem *v34; // [rsp+48h] [rbp-70h] BYREF
  LPCITEMIDLIST *apidl[2]; // [rsp+50h] [rbp-68h] BYREF
  __int64 v36; // [rsp+60h] [rbp-58h]
  __int64 (__fastcall ***v37)(_QWORD, __int64 *, __int64 *); // [rsp+68h] [rbp-50h] BYREF
  __int64 v38; // [rsp+70h] [rbp-48h] BYREF
  struct IShellItem *v39; // [rsp+78h] [rbp-40h] BYREF
  LPCITEMIDLIST *v40; // [rsp+80h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]
  char v42; // [rsp+C0h] [rbp+8h] BYREF
  const unsigned __int16 *v43; // [rsp+D0h] [rbp+18h] BYREF
  int v44; // [rsp+D8h] [rbp+20h] BYREF

  LOBYTE(v44) = a4;
  v43 = a3;
  LauncherDesktopProvider::CheckRequirementsAndLaunchFolder<winrt::guid &,unsigned short const * &,bool &>(
    (char *)this + 100,
    &v43,
    &v44);
  try
  {
    v33 = 0;
    if ( a4 )
    {
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
      ValidatedStorageItem = STORAGE_CStorageItem_GetValidatedStorageItem(a2, a3, &v33);
      if ( ValidatedStorageItem < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x843,
          (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\brokeredlauncher.cpp",
          (const char *)(unsigned int)ValidatedStorageItem,
          v28);
    }
    else
    {
      v9 = **a2;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
      v10 = v9((struct Windows::Storage::IStorageFolder *)a2, &GUID_4207a996_ca2f_42f7_bde8_8b10457a7f30, &v33);
      if ( v10 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x847,
          (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\brokeredlauncher.cpp",
          (const char *)(unsigned int)v10,
          v28);
    }
    v42 = 0;
    v11 = (*(__int64 (__fastcall **)(__int64, __int64, char *))(*(_QWORD *)v33 + 120LL))(v33, 2, &v42);
    if ( v11 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x84B,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\brokeredlauncher.cpp",
        (const char *)(unsigned int)v11,
        v28);
    if ( !v42 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x84F,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\brokeredlauncher.cpp",
        (const char *)0x80070057LL,
        v28);
    v34 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v34);
    ShellItemFromStorageItem = GetShellItemFromStorageItem(v33, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, &v34);
    if ( ShellItemFromStorageItem < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x853,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\brokeredlauncher.cpp",
        (const char *)(unsigned int)ShellItemFromStorageItem,
        v28);
    v32 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
    Related = GetRelatedItem<IIdentityName>((_DWORD)v34, v13, v14, v15, (__int64)&v32);
    if ( Related < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x857,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\brokeredlauncher.cpp",
        (const char *)(unsigned int)Related,
        v29);
    v17 = CopyAllMissingSupplementalHiddenData(v34, v32);
    if ( v17 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x858,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\brokeredlauncher.cpp",
        (const char *)(unsigned int)v17,
        v29);
    v38 = 0;
    v18 = CPropertyStoreHelperBase<IPropertyStore>::InitFromItem(&v38, v32, 8);
    if ( v18 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x85B,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\brokeredlauncher.cpp",
        (const char *)(unsigned int)v18,
        v29);
    if ( *((_BYTE *)this + 81) )
      v19 = CBrokeredLauncher::CLaunchHelper::_CheckCallerVisibilityAndContext(this);
    else
      v19 = 0;
    if ( v19 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x85D,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\brokeredlauncher.cpp",
        (const char *)(unsigned int)v19,
        v29);
    CBrokeredLauncher::CLaunchHelper::_GetSelectedIDListArrayForFolderLaunch(this, apidl, a3);
    if ( apidl[0] == apidl[1] || !(unsigned __int8)IsSHOpenOrGetFolderViewPresent() )
    {
      pidlFolder = 0;
      if ( (unsigned __int8)IsSHOpenOrGetFolderViewPresent() || apidl[0] == apidl[1] )
      {
        v24 = (__int64 (__fastcall ***)(_QWORD, GUID *, LPCITEMIDLIST *))*((_QWORD *)this + 5);
        if ( v24 )
        {
          v25 = (**v24)(v24, &GUID_fc4801a3_2ba9_11cf_a229_00aa003d7352, &pidlFolder);
          if ( v25 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x86C,
              (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\brokeredlauncher.cpp",
              (const char *)(unsigned int)v25,
              v29);
        }
      }
      else
      {
        v40 = apidl[0];
        v44 = apidl[1] - apidl[0];
        v39 = v32;
        winrt::make_self<FolderLaunchItemsToSelect,IShellItem *,unsigned int,_ITEMID_CHILD const __unaligned * const *>(
          &v37,
          &v39,
          &v44,
          &v40);
        winrt::impl::as<IObjectWithSite,PendingLaunchRequest,0>(&v39, v37);
        pidlFolder = (LPCITEMIDLIST)v39;
        v22 = ((__int64 (__fastcall *)(struct IShellItem *, _QWORD))v39->lpVtbl->BindToHandler)(
                v39,
                *((_QWORD *)this + 5));
        if ( v22 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x868,
            (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\brokeredlauncher.cpp",
            (const char *)(unsigned int)v22,
            v29);
        if ( v37 )
          winrt::com_ptr<winrt::Windows::Foundation::IUnknown>::unconditional_release_ref(&v37);
      }
      v23 = CBrokeredLauncher::CLaunchHelper::_LaunchShellItemWithOptionsAndVerb(
              this,
              v32,
              (struct IUnknown *)pidlFolder,
              0,
              0,
              0);
      if ( v23 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x86F,
          (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\brokeredlauncher.cpp",
          (const char *)(unsigned int)v23,
          v30);
      if ( pidlFolder )
        winrt::com_ptr<IPropertyBag>::unconditional_release_ref(&pidlFolder);
    }
    else
    {
      wil::GetAbsoluteIdList(&pidlFolder, v32);
      v20 = SHOpenFolderAndSelectItems(pidlFolder, apidl[1] - apidl[0], apidl[0], 0);
      if ( v20 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x875,
          (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\brokeredlauncher.cpp",
          (const char *)(unsigned int)v20,
          v29);
      v21 = (ITEMIDLIST *)pidlFolder;
      pidlFolder = 0;
      if ( v21 )
        CoTaskMemFree(v21);
    }
    if ( apidl[0] )
    {
      std::_Destroy_range<std::allocator<wistd::unique_ptr<_ITEMID_CHILD,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>>(
        (void **)apidl[0],
        (void **)apidl[1]);
      std::_Deallocate<16>(
        apidl[0],
        (const struct std::nothrow_t *)((v36 - (unsigned __int64)apidl[0]) & 0xFFFFFFFFFFFFFFF8uLL));
      *(_OWORD *)apidl = 0;
      v36 = 0;
    }
    if ( v38 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
      v38 = 0;
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v34);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x878,
                           (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\brokeredlauncher.cpp",
                           v26);
  }
  return result;
}

```

## disassembly

```asm
0x18004e94c  mov     rax, rsp
0x18004e94f  mov     [rax+20h], r9b
0x18004e953  mov     [rax+18h], r8
0x18004e957  push    rbx
0x18004e958  push    rsi
0x18004e959  push    rdi
0x18004e95a  push    r14
0x18004e95c  push    r15
0x18004e95e  sub     rsp, 90h
0x18004e965  mov     bl, r9b
0x18004e968  mov     rsi, r8
0x18004e96b  mov     r14, rdx
0x18004e96e  mov     rdi, rcx
0x18004e971  xor     r15d, r15d
0x18004e974  add     rcx, 64h ; 'd'
0x18004e978  lea     r8, [rax+20h]
0x18004e97c  lea     rdx, [rax+18h]
0x18004e980  call    ??$CheckRequirementsAndLaunchFolder@AEAUguid@winrt@@AEAPEBGAEA_N@LauncherDesktopProvider@@SAXAEAUguid@winrt@@AEAPEBGAEA_N@Z; LauncherDesktopProvider::CheckRequirementsAndLaunchFolder<winrt::guid &,ushort const * &,bool &>(winrt::guid &,ushort const * &,bool &)
0x18004e985  mov     [rsp+0B8h+var_78], r15
0x18004e98a  lea     rcx, [rsp+0B8h+var_78]
0x18004e98f  test    bl, bl
0x18004e991  jz      short loc_18004E9C9
0x18004e993  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004e998  lea     r8, [rsp+0B8h+var_78]
0x18004e99d  mov     rdx, rsi
0x18004e9a0  mov     rcx, r14
0x18004e9a3  call    cs:__imp_STORAGE_CStorageItem_GetValidatedStorageItem
0x18004e9a9  mov     rcx, [rsp+0B8h]; this
0x18004e9b1  test    eax, eax
0x18004e9b3  jns     short loc_18004EA0B
0x18004e9b5  mov     r9d, eax; char *
0x18004e9b8  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\windows.system.launc"...
0x18004e9bf  mov     edx, 843h; void *
0x18004e9c4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004e9c9  mov     rax, [r14]
0x18004e9cc  mov     rbx, [rax]
0x18004e9cf  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004e9d4  lea     r8, [rsp+0B8h+var_78]
0x18004e9d9  lea     rdx, _GUID_4207a996_ca2f_42f7_bde8_8b10457a7f30
0x18004e9e0  mov     rcx, r14
0x18004e9e3  mov     rax, rbx
0x18004e9e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e9eb  mov     rcx, [rsp+0B8h]; this
0x18004e9f3  test    eax, eax
0x18004e9f5  jns     short loc_18004EA0B
0x18004e9f7  mov     r9d, eax; char *
0x18004e9fa  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\windows.system.launc"...
0x18004ea01  mov     edx, 847h; void *
0x18004ea06  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004ea0b  mov     [rsp+0B8h+arg_0], r15b
0x18004ea13  mov     rcx, [rsp+0B8h+var_78]
0x18004ea18  mov     rax, [rcx]
0x18004ea1b  lea     r8, [rsp+0B8h+arg_0]
0x18004ea23  mov     edx, 2
0x18004ea28  mov     rax, [rax+78h]
0x18004ea2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ea31  mov     rcx, [rsp+0B8h]; this
0x18004ea39  test    eax, eax
0x18004ea3b  jns     short loc_18004EA51
0x18004ea3d  mov     r9d, eax; char *
0x18004ea40  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\windows.system.launc"...
0x18004ea47  mov     edx, 84Bh; void *
0x18004ea4c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004ea51  mov     al, [rsp+0B8h+arg_0]
0x18004ea58  neg     al
0x18004ea5a  sbb     r9d, r9d
0x18004ea5d  not     r9d
0x18004ea60  and     r9d, 80070057h; char *
0x18004ea67  mov     rcx, [rsp+0B8h]; this
0x18004ea6f  jge     short loc_18004EA82
0x18004ea71  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\windows.system.launc"...
0x18004ea78  mov     edx, 84Fh; void *
0x18004ea7d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004ea82  mov     [rsp+0B8h+var_70], r15
0x18004ea87  lea     rcx, [rsp+0B8h+var_70]
0x18004ea8c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004ea91  lea     r8, [rsp+0B8h+var_70]
0x18004ea96  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe
0x18004ea9d  mov     rcx, [rsp+0B8h+var_78]
0x18004eaa2  call    cs:__imp_GetShellItemFromStorageItem
0x18004eaa8  mov     rcx, [rsp+0B8h]; this
0x18004eab0  test    eax, eax
0x18004eab2  jns     short loc_18004EAC8
0x18004eab4  mov     r9d, eax; char *
0x18004eab7  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\windows.system.launc"...
0x18004eabe  mov     edx, 853h; void *
0x18004eac3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004eac8  mov     [rsp+0B8h+var_80], r15
0x18004eacd  lea     rcx, [rsp+0B8h+var_80]
0x18004ead2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004ead7  lea     rax, [rsp+0B8h+var_80]
0x18004eadc  mov     [rsp+0B8h+var_98], rax; int
0x18004eae1  mov     rcx, [rsp+0B8h+var_70]
0x18004eae6  call    ??$GetRelatedItem@UIIdentityName@@@@YAJPEAUIShellItem@@PEAUIBindCtx@@_NAEBU_GUID@@PEAPEAX@Z; GetRelatedItem<IIdentityName>(IShellItem *,IBindCtx *,bool,_GUID const &,void * *)
0x18004eaeb  mov     rcx, [rsp+0B8h]; this
0x18004eaf3  test    eax, eax
0x18004eaf5  jns     short loc_18004EB0B
0x18004eaf7  mov     r9d, eax; char *
0x18004eafa  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\windows.system.launc"...
0x18004eb01  mov     edx, 857h; void *
0x18004eb06  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004eb0b  mov     rdx, [rsp+0B8h+var_80]; struct IShellItem *
0x18004eb10  mov     rcx, [rsp+0B8h+var_70]; struct IShellItem *
0x18004eb15  call    ?CopyAllMissingSupplementalHiddenData@@YAJPEAUIShellItem@@0@Z; CopyAllMissingSupplementalHiddenData(IShellItem *,IShellItem *)
0x18004eb1a  mov     rcx, [rsp+0B8h]; this
0x18004eb22  test    eax, eax
0x18004eb24  jns     short loc_18004EB3A
0x18004eb26  mov     r9d, eax; char *
0x18004eb29  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\windows.system.launc"...
0x18004eb30  mov     edx, 858h; void *
0x18004eb35  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004eb3a  mov     [rsp+0B8h+var_48], r15
0x18004eb3f  mov     r8d, 8
0x18004eb45  mov     rdx, [rsp+0B8h+var_80]
0x18004eb4a  lea     rcx, [rsp+0B8h+var_48]
0x18004eb4f  call    ?InitFromItem@?$CPropertyStoreHelperBase@UIPropertyStore@@@@QEAAJPEAUIUnknown@@W4GETPROPERTYSTOREFLAGS@@@Z; CPropertyStoreHelperBase<IPropertyStore>::InitFromItem(IUnknown *,GETPROPERTYSTOREFLAGS)
0x18004eb54  mov     rcx, [rsp+0B8h]; this
0x18004eb5c  test    eax, eax
0x18004eb5e  jns     short loc_18004EB74
0x18004eb60  mov     r9d, eax; char *
0x18004eb63  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\windows.system.launc"...
0x18004eb6a  mov     edx, 85Bh; void *
0x18004eb6f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004eb74  cmp     [rdi+51h], r15b
0x18004eb78  jz      short loc_18004EB84
0x18004eb7a  mov     rcx, rdi; this
0x18004eb7d  call    ?_CheckCallerVisibilityAndContext@CLaunchHelper@CBrokeredLauncher@@AEAAJXZ; CBrokeredLauncher::CLaunchHelper::_CheckCallerVisibilityAndContext(void)
0x18004eb82  jmp     short loc_18004EB87
0x18004eb84  mov     eax, r15d
0x18004eb87  mov     rcx, [rsp+0B8h]; this
0x18004eb8f  test    eax, eax
0x18004eb91  jns     short loc_18004EBA7
0x18004eb93  mov     r9d, eax; char *
0x18004eb96  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\windows.system.launc"...
0x18004eb9d  mov     edx, 85Dh; void *
0x18004eba2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004eba7  mov     r8, rsi
0x18004ebaa  lea     rdx, [rsp+0B8h+apidl]
0x18004ebaf  mov     rcx, rdi
0x18004ebb2  call    ?_GetSelectedIDListArrayForFolderLaunch@CLaunchHelper@CBrokeredLauncher@@AEAA?AV?$vector@V?$unique_ptr@U_ITEMID_CHILD@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@V?$allocator@V?$unique_ptr@U_ITEMID_CHILD@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@std@@@std@@PEBG@Z; CBrokeredLauncher::CLaunchHelper::_GetSelectedIDListArrayForFolderLaunch(ushort const *)
0x18004ebb7  nop
0x18004ebb8  mov     rax, [rsp+0B8h+apidl+8]
0x18004ebbd  cmp     [rsp+0B8h+apidl], rax
0x18004ebc2  jz      short loc_18004EC3B
0x18004ebc4  call    IsSHOpenOrGetFolderViewPresent
0x18004ebc9  test    al, al
0x18004ebcb  jz      short loc_18004EC3B
0x18004ebcd  mov     rdx, [rsp+0B8h+var_80]
0x18004ebd2  lea     rcx, [rsp+0B8h+pidlFolder]
0x18004ebd7  call    ?GetAbsoluteIdList@wil@@YA?AV?$unique_ptr@U_ITEMIDLIST_ABSOLUTE@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@PEAUIShellItem@@@Z; wil::GetAbsoluteIdList(IShellItem *)
0x18004ebdc  nop
0x18004ebdd  mov     r8, [rsp+0B8h+apidl]; apidl
0x18004ebe2  mov     rdx, [rsp+0B8h+apidl+8]
0x18004ebe7  sub     rdx, r8
0x18004ebea  sar     rdx, 3; cidl
0x18004ebee  xor     r9d, r9d; dwFlags
0x18004ebf1  mov     rcx, [rsp+0B8h+pidlFolder]; pidlFolder
0x18004ebf6  call    cs:__imp_SHOpenFolderAndSelectItems
0x18004ebfc  mov     rcx, [rsp+0B8h]; this
0x18004ec04  test    eax, eax
0x18004ec06  jns     short loc_18004EC1D
0x18004ec08  mov     r9d, eax; char *
0x18004ec0b  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\windows.system.launc"...
0x18004ec12  mov     edx, 875h; void *
0x18004ec17  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004ec1d  mov     rcx, [rsp+0B8h+pidlFolder]; pv
0x18004ec22  mov     [rsp+0B8h+pidlFolder], r15
0x18004ec27  test    rcx, rcx
0x18004ec2a  jz      loc_18004EDB9
0x18004ec30  call    cs:__imp_CoTaskMemFree
0x18004ec36  jmp     loc_18004EDB9
0x18004ec3b  mov     [rsp+0B8h+pidlFolder], r15
0x18004ec40  call    IsSHOpenOrGetFolderViewPresent
0x18004ec45  test    al, al
0x18004ec47  jnz     loc_18004ED4B
0x18004ec4d  mov     rax, [rsp+0B8h+apidl+8]
0x18004ec52  mov     rcx, [rsp+0B8h+apidl]
0x18004ec57  cmp     rcx, rax
0x18004ec5a  jz      loc_18004ED4B
0x18004ec60  mov     [rsp+0B8h+var_38], rcx
0x18004ec68  sub     rax, rcx
0x18004ec6b  sar     rax, 3
0x18004ec6f  mov     [rsp+0B8h+arg_18], eax
0x18004ec76  mov     rax, [rsp+0B8h+var_80]
0x18004ec7b  mov     [rsp+0B8h+var_40], rax
0x18004ec80  lea     r9, [rsp+0B8h+var_38]
0x18004ec88  lea     r8, [rsp+0B8h+arg_18]
0x18004ec90  lea     rdx, [rsp+0B8h+var_40]
0x18004ec95  lea     rcx, [rsp+0B8h+var_50]
0x18004ec9a  call    ??$make_self@VFolderLaunchItemsToSelect@@PEAUIShellItem@@IPEBQEFBU_ITEMID_CHILD@@@winrt@@YA?AU?$com_ptr@VFolderLaunchItemsToSelect@@@0@$$QEAPEAUIShellItem@@$$QEAI$$QEAPEBQEFBU_ITEMID_CHILD@@@Z; winrt::make_self<FolderLaunchItemsToSelect,IShellItem *,uint,_ITEMID_CHILD const * const *>(IShellItem * &&,uint &&,_ITEMID_CHILD const * const * &&)
0x18004ec9f  nop
0x18004eca0  mov     rdx, [rsp+0B8h+var_50]
0x18004eca5  lea     rcx, [rsp+0B8h+var_40]
0x18004ecaa  call    ??$as@UIObjectWithSite@@VPendingLaunchRequest@@$0A@@impl@winrt@@YA?AU?$com_ptr@UIObjectWithSite@@@1@PEAVPendingLaunchRequest@@@Z; winrt::impl::as<IObjectWithSite,PendingLaunchRequest,0>(PendingLaunchRequest *)
0x18004ecaf  cmp     [rsp+0B8h+pidlFolder], r15
0x18004ecb4  jz      short loc_18004ECC0
0x18004ecb6  lea     rcx, [rsp+0B8h+pidlFolder]
0x18004ecbb  call    ?unconditional_release_ref@?$com_ptr@UIPropertyBag@@@winrt@@AEAAXXZ; winrt::com_ptr<IPropertyBag>::unconditional_release_ref(void)
0x18004ecc0  mov     rcx, [rsp+0B8h+var_40]
0x18004ecc5  mov     [rsp+0B8h+pidlFolder], rcx
0x18004ecca  mov     rax, [rcx]
0x18004eccd  mov     rdx, [rdi+28h]
0x18004ecd1  mov     rax, [rax+18h]
0x18004ecd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ecda  mov     rcx, [rsp+0B8h]; this
0x18004ece2  test    eax, eax
0x18004ece4  jns     short loc_18004ECFB
0x18004ece6  mov     r9d, eax; char *
0x18004ece9  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\windows.system.launc"...
0x18004ecf0  mov     edx, 868h; void *
0x18004ecf5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004ecfb  cmp     [rsp+0B8h+var_50], r15
0x18004ed00  jz      short loc_18004ED0C
0x18004ed02  lea     rcx, [rsp+0B8h+var_50]
0x18004ed07  call    ?unconditional_release_ref@?$com_ptr@UIUnknown@Foundation@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Foundation::IUnknown>::unconditional_release_ref(void)
0x18004ed0c  mov     [rsp+0B8h+var_90], r15; unsigned __int16 *
0x18004ed11  mov     [rsp+0B8h+var_98], r15; int
0x18004ed16  xor     r9d, r9d; unsigned __int16 *
0x18004ed19  mov     r8, [rsp+0B8h+pidlFolder]; struct IUnknown *
0x18004ed1e  mov     rdx, [rsp+0B8h+var_80]; struct IShellItem *
0x18004ed23  mov     rcx, rdi; this
0x18004ed26  call    ?_LaunchShellItemWithOptionsAndVerb@CLaunchHelper@CBrokeredLauncher@@AEAAJPEAUIShellItem@@PEAUIUnknown@@PEBG22@Z; CBrokeredLauncher::CLaunchHelper::_LaunchShellItemWithOptionsAndVerb(IShellItem *,IUnknown *,ushort const *,ushort const *,ushort const *)
0x18004ed2b  mov     rcx, [rsp+0B8h]; this
0x18004ed33  test    eax, eax
0x18004ed35  jns     short loc_18004EDA7
0x18004ed37  mov     r9d, eax; char *
0x18004ed3a  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\windows.system.launc"...
0x18004ed41  mov     edx, 86Fh; void *
0x18004ed46  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004ed4b  mov     rbx, [rdi+28h]
0x18004ed4f  test    rbx, rbx
0x18004ed52  jz      short loc_18004ED0C
0x18004ed54  mov     rax, [rbx]
0x18004ed57  mov     rsi, [rax]
0x18004ed5a  cmp     [rsp+0B8h+pidlFolder], r15
0x18004ed5f  jz      short loc_18004ED6B
0x18004ed61  lea     rcx, [rsp+0B8h+pidlFolder]
0x18004ed66  call    ?unconditional_release_ref@?$com_ptr@UIPropertyBag@@@winrt@@AEAAXXZ; winrt::com_ptr<IPropertyBag>::unconditional_release_ref(void)
0x18004ed6b  lea     r8, [rsp+0B8h+pidlFolder]
0x18004ed70  lea     rdx, _GUID_fc4801a3_2ba9_11cf_a229_00aa003d7352
0x18004ed77  mov     rcx, rbx
0x18004ed7a  mov     rax, rsi
0x18004ed7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ed82  mov     rcx, [rsp+0B8h]; this
0x18004ed8a  test    eax, eax
0x18004ed8c  jns     loc_18004ED0C
0x18004ed92  mov     r9d, eax; char *
0x18004ed95  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\windows.system.launc"...
0x18004ed9c  mov     edx, 86Ch; void *
0x18004eda1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004eda7  cmp     [rsp+0B8h+pidlFolder], r15
0x18004edac  jz      short loc_18004EDB9
0x18004edae  lea     rcx, [rsp+0B8h+pidlFolder]
0x18004edb3  call    ?unconditional_release_ref@?$com_ptr@UIPropertyBag@@@winrt@@AEAAXXZ; winrt::com_ptr<IPropertyBag>::unconditional_release_ref(void)
0x18004edb8  nop
0x18004edb9  mov     rcx, [rsp+0B8h+apidl]
0x18004edbe  test    rcx, rcx
0x18004edc1  jz      short loc_18004EDF1
0x18004edc3  mov     rdx, [rsp+0B8h+apidl+8]
0x18004edc8  call    ??$_Destroy_range@V?$allocator@V?$unique_ptr@U_ITEMID_CHILD@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@std@@@std@@YAXPEAV?$unique_ptr@U_ITEMID_CHILD@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAV12@AEAV?$allocator@V?$unique_ptr@U_ITEMID_CHILD@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@0@@Z; std::_Destroy_range<std::allocator<wistd::unique_ptr<_ITEMID_CHILD,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>>(wistd::unique_ptr<_ITEMID_CHILD,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>> *,wistd::unique_ptr<_ITEMID_CHILD,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>> * const,std::allocator<wistd::unique_ptr<_ITEMID_CHILD,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>> &)
0x18004edcd  mov     rcx, [rsp+0B8h+apidl]
0x18004edd2  mov     rdx, [rsp+0B8h+var_58]
0x18004edd7  sub     rdx, rcx
0x18004edda  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18004edde  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18004ede3  xorps   xmm0, xmm0
0x18004ede6  movdqu  xmmword ptr [rsp+0B8h+apidl], xmm0
0x18004edec  mov     [rsp+0B8h+var_58], r15
0x18004edf1  mov     rcx, [rsp+0B8h+var_48]
0x18004edf6  test    rcx, rcx
0x18004edf9  jz      short loc_18004EE0C
0x18004edfb  mov     rax, [rcx]
0x18004edfe  mov     rax, [rax+10h]
0x18004ee02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ee07  mov     [rsp+0B8h+var_48], r15
0x18004ee0c  lea     rcx, [rsp+0B8h+var_80]
0x18004ee11  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004ee16  nop
0x18004ee17  lea     rcx, [rsp+0B8h+var_70]
0x18004ee1c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004ee21  nop
0x18004ee22  lea     rcx, [rsp+0B8h+var_78]
0x18004ee27  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004ee2c  xor     eax, eax
0x18004ee2e  jmp     short loc_18004EE37
0x18004ee30  mov     eax, [rsp+0B8h+arg_18]
0x18004ee37  add     rsp, 90h
0x18004ee3e  pop     r15
0x18004ee40  pop     r14
0x18004ee42  pop     rdi
0x18004ee43  pop     rsi
0x18004ee44  pop     rbx
0x18004ee45  retn
```
