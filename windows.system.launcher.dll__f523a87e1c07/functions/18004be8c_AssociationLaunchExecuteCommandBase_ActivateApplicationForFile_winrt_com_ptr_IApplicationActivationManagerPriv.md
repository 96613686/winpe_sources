# AssociationLaunchExecuteCommandBase::ActivateApplicationForFile(winrt::com_ptr<IApplicationActivationManagerPriv> const &,Microsoft::WRL::Wrappers::HString const &,unsigned __int64)

- ea: `0x18004be8c`
- end: `0x18004c624`
- name: `?ActivateApplicationForFile@AssociationLaunchExecuteCommandBase@@AEAAJAEBU?$com_ptr@UIApplicationActivationManagerPriv@@@winrt@@AEBVHString@Wrappers@WRL@Microsoft@@_K@Z`
- size: `1944`
- prototype: ``
- caller_count: `1`
- callee_count: `23`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180054940`

## callees

- `0x1800049bc`
- `0x18000f194`
- `0x18004966c`
- `0x18004be54`
- `0x18004be8c`
- `0x18004c62c`
- `0x18004c658`
- `0x18004c690`
- `0x18004cee0`
- `0x18004d2d0`
- `0x18004d3ec`
- `0x18004d508`
- `0x18004d538`
- `0x18008a030`
- `0x1800aae88`
- `0x1800eeebc`
- `0x1800eef28`
- `0x1800efc40`
- `0x1800f01ac`
- `0x1800f0258`
- `0x1800f061c`
- `0x1800f1144`
- `0x180111010`

## import_xrefs

- `Windows.Storage!STORAGE_CreateStorageItemFromShellItem_FullTrustCaller` at `0x18004c13d`
- `Windows.Storage!STORAGE_CreateStorageItemFromShellItem_FullTrustCaller` at `0x18004c13d`
- `Windows.Storage!CShellItemArray_CreateInstance` at `0x18004c293`
- `Windows.Storage!CShellItemArray_CreateInstance` at `0x18004c293`
- `ntdll!RtlIsMultiSessionSku` at `0x18004bf83`
- `ntdll!RtlIsMultiSessionSku` at `0x18004bf83`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004bfa5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004c2c0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004c2d4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004c41c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004c430`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004bfa5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004c2c0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004c2d4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004c41c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004c430`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageFamilyNameFromFullName` at `0x18004bfbe`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageFamilyNameFromFullName` at `0x18004bfbe`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x18004bf2f`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x18004c1cb`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x18004bf2f`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x18004c1cb`

## string_xrefs

- `0x18004bfd3`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\associationlaunchexecutecommand.cpp`
- `0x18004c094`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\associationlaunchexecutecommand.cpp`
- `0x18004c10b`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\associationlaunchexecutecommand.cpp`
- `0x18004c152`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\associationlaunchexecutecommand.cpp`
- `0x18004c193`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\associationlaunchexecutecommand.cpp`
- `0x18004c21c`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\associationlaunchexecutecommand.cpp`
- `0x18004c262`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\associationlaunchexecutecommand.cpp`
- `0x18004c2a8`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\associationlaunchexecutecommand.cpp`
- `0x18004c354`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\associationlaunchexecutecommand.cpp`
- `0x18004c405`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\associationlaunchexecutecommand.cpp`
- `0x18004c4a6`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\associationlaunchexecutecommand.cpp`
- `0x18004c521`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\associationlaunchexecutecommand.cpp`
- `0x18004c611`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\associationlaunchexecutecommand.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=21
__int64 __fastcall AssociationLaunchExecuteCommandBase::ActivateApplicationForFile(
        LaunchExecuteCommandBase *this,
        _QWORD *a2,
        HSTRING *a3,
        const WCHAR *a4)
{
  __int64 v7; // rbx
  __int64 v8; // rsi
  void *v9; // rax
  __int64 *v10; // rax
  const WCHAR *StringRawBuffer; // rax
  unsigned int v12; // eax
  __int64 v13; // rdx
  __int64 CurrentQueryOptions; // r8
  int v15; // eax
  int v16; // eax
  int v17; // eax
  int v18; // eax
  void *v19; // r14
  __int64 (__fastcall *v20)(void *, __int64 *); // r15
  int v21; // eax
  int v22; // eax
  int v23; // eax
  __int64 v24; // rax
  __int64 v25; // rdx
  int v26; // ecx
  int v27; // eax
  int v28; // eax
  __int64 v29; // rax
  __int64 v30; // rdx
  int v31; // ecx
  int v32; // eax
  int v33; // eax
  const char *v34; // r9
  struct IShellItemArray *v35; // rcx
  __int64 result; // rax
  int v37; // eax
  unsigned int v38; // [rsp+20h] [rbp-1B8h]
  int v39; // [rsp+20h] [rbp-1B8h]
  int v40; // [rsp+20h] [rbp-1B8h]
  int v41[2]; // [rsp+20h] [rbp-1B8h]
  int v42; // [rsp+20h] [rbp-1B8h]
  void *v43; // [rsp+50h] [rbp-188h] BYREF
  int v44; // [rsp+58h] [rbp-180h]
  __int64 v45; // [rsp+60h] [rbp-178h] BYREF
  struct IShellItemArray *v46; // [rsp+68h] [rbp-170h] BYREF
  __int64 v47; // [rsp+70h] [rbp-168h] BYREF
  __int64 v48; // [rsp+78h] [rbp-160h] BYREF
  void *v49; // [rsp+80h] [rbp-158h] BYREF
  void *v50; // [rsp+88h] [rbp-150h] BYREF
  __int64 v51; // [rsp+90h] [rbp-148h] BYREF
  void *ppvOut; // [rsp+98h] [rbp-140h] BYREF
  PCWSTR v53; // [rsp+A0h] [rbp-138h] BYREF
  __int64 v54; // [rsp+A8h] [rbp-130h] BYREF
  UINT32 packageFamilyNameLength; // [rsp+B0h] [rbp-128h] BYREF
  int v56[2]; // [rsp+B8h] [rbp-120h] BYREF
  __int64 v57; // [rsp+C0h] [rbp-118h] BYREF
  _BYTE v58[56]; // [rsp+C8h] [rbp-110h] BYREF
  WCHAR packageFamilyName[72]; // [rsp+100h] [rbp-D8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1D8h] [rbp+0h]

  v53 = a4;
  v46 = 0;
  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v46);
  try
  {
    if ( !LaunchExecuteCommandBase::TryCreateViewItemsArray(this, &v46) )
      Microsoft::WRL::ComPtr<IShellItemArray>::operator=(&v46, (char *)this + 160);
    v7 = 0;
    v57 = 0;
    ppvOut = 0;
    v8 = 0;
    if ( !*((_DWORD *)this + 26)
      && IUnknown_QueryService(
           *((IUnknown **)this + 4),
           &GUID_bafa21d8_b071_4cd8_853e_341203e557d3,
           &winrt::impl::guid_v<winrt::Windows::Foundation::IUnknown>,
           &ppvOut) >= 0 )
    {
      v9 = ppvOut;
      ppvOut = 0;
      v43 = v9;
      v10 = (__int64 *)winrt::impl::consume_Windows_System_ILauncherOptions2<winrt::Windows::System::LauncherOptions>::NeighboringFilesQuery(
                         &v43,
                         &v48);
      v7 = *v10;
      *v10 = 0;
      v57 = v7;
      _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_((_lambda_12ef4a55c56a96ec7ad58335194b061f_ *)&v48);
      _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_((_lambda_12ef4a55c56a96ec7ad58335194b061f_ *)&v43);
      v8 = v7;
    }
    if ( (unsigned __int8)RtlIsMultiSessionSku() )
    {
      v42 = (int)v46;
      v37 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(*(_QWORD *)*a2 + 176LL))(
              *a2,
              *((_QWORD *)this + 29),
              *((_QWORD *)this + 27),
              *((_QWORD *)this + 12));
      if ( v37 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x156,
          (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\associationlaunchexecutecommand.cpp",
          (const char *)(unsigned int)v37,
          v42);
    }
    else
    {
      packageFamilyNameLength = 65;
      StringRawBuffer = WindowsGetStringRawBuffer(*((HSTRING *)this + 29), 0);
      v12 = PackageFamilyNameFromFullName(StringRawBuffer, &packageFamilyNameLength, packageFamilyName);
      if ( v12 )
        wil::details::in1diag3::_Throw_Win32(
          retaddr,
          (void *)0x118,
          (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\associationlaunchexecutecommand.cpp",
          (const char *)v12,
          v38);
      v54 = 0;
      if ( v8 )
      {
        winrt::impl::as<winrt::Windows::Storage::Search::IStorageQueryResultBase,Windows::Storage::Search::IStorageFileQueryResult,0>(
          &v47,
          v7);
        v13 = *(_QWORD *)winrt::impl::consume_Windows_Storage_Search_IStorageQueryResultBase<winrt::Windows::Storage::Search::IStorageQueryResultBase>::Folder(
                           &v47,
                           &v51);
        winrt::impl::as<winrt::Windows::Storage::Search::IStorageFolderQueryOperations,winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type,0>(
          &v48,
          v13);
        _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_((_lambda_12ef4a55c56a96ec7ad58335194b061f_ *)&v51);
        CurrentQueryOptions = winrt::impl::consume_Windows_Storage_Search_IStorageQueryResultBase<winrt::Windows::Storage::Search::IStorageQueryResultBase>::GetCurrentQueryOptions(
                                &v47,
                                &v50);
        winrt::impl::consume_Windows_Storage_Search_IStorageFolderQueryOperations<winrt::Windows::Storage::Search::IStorageFolderQueryOperations>::CreateFileQueryWithOptions(
          &v48,
          &v43,
          CurrentQueryOptions);
        _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_((_lambda_12ef4a55c56a96ec7ad58335194b061f_ *)&v50);
        v15 = CMarshaledInterface::Marshal(&v54, &GUID_52fda447_2baa_412c_b29f_d4b1778efa1e, v43, 1);
        if ( v15 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x124,
            (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\associationlaunchexecutecommand.cpp",
            (const char *)(unsigned int)v15,
            v38);
        _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_((_lambda_12ef4a55c56a96ec7ad58335194b061f_ *)&v43);
        _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_((_lambda_12ef4a55c56a96ec7ad58335194b061f_ *)&v48);
        _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_((_lambda_12ef4a55c56a96ec7ad58335194b061f_ *)&v47);
      }
      v49 = 0;
      if ( *((_DWORD *)this + 26) == 3 )
      {
        v47 = 0;
        v16 = ((__int64 (__fastcall *)(struct IShellItemArray *, _QWORD, __int64 *))v46->lpVtbl->GetItemAt)(
                v46,
                0,
                &v47);
        if ( v16 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x12B,
            (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\associationlaunchexecutecommand.cpp",
            (const char *)(unsigned int)v16,
            v38);
        v51 = 0;
        v17 = STORAGE_CreateStorageItemFromShellItem_FullTrustCaller(
                v47,
                4098,
                &GUID_72d1cb78_b3ef_4f75_a80b_6fd9dae2944b,
                &v51);
        if ( v17 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x12E,
            (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\associationlaunchexecutecommand.cpp",
            (const char *)(unsigned int)v17,
            v38);
        v43 = 0;
        v18 = CMarshaledInterface::Marshal(&v43, &GUID_72d1cb78_b3ef_4f75_a80b_6fd9dae2944b, v51, 1);
        if ( v18 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x131,
            (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\associationlaunchexecutecommand.cpp",
            (const char *)(unsigned int)v18,
            v38);
        v45 = 0;
        v50 = 0;
        if ( IUnknown_QueryService(
               *((IUnknown **)this + 4),
               &guidService,
               &GUID_121b45ea_779e_40f8_8e4f_dcb2bc788e36,
               &v50) < 0 )
        {
          if ( v45 )
            winrt::com_ptr<IPropertyBag>::unconditional_release_ref(&v45);
          v23 = CShellItemArray_CreateInstance(0, &GUID_b63ea76d_1f85_456f_a19c_48159efa858b, &v45);
          if ( v23 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x13B,
              (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\associationlaunchexecutecommand.cpp",
              (const char *)(unsigned int)v23,
              v38);
        }
        else
        {
          v19 = v50;
          v20 = *(__int64 (__fastcall **)(void *, __int64 *))(*(_QWORD *)v50 + 24LL);
          if ( v45 )
            winrt::com_ptr<IPropertyBag>::unconditional_release_ref(&v45);
          v21 = v20(v19, &v45);
          if ( v21 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x137,
              (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\associationlaunchexecutecommand.cpp",
              (const char *)(unsigned int)v21,
              v38);
        }
        v48 = 0;
        v22 = CMarshaledInterface::Marshal(&v48, &GUID_b63ea76d_1f85_456f_a19c_48159efa858b, v45, 1);
        if ( v22 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x13F,
            (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\associationlaunchexecutecommand.cpp",
            (const char *)(unsigned int)v22,
            v38);
        v53 = WindowsGetStringRawBuffer(*a3, 0);
        *(_QWORD *)v56 = WindowsGetStringRawBuffer(*((HSTRING *)this + 12), 0);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v49);
        v24 = _lambda_1ad717cd63abbe8bc6f22e820e288409_::_lambda_1ad717cd63abbe8bc6f22e820e288409_(
                (unsigned int)v58,
                (unsigned int)&v48,
                (unsigned int)&v43,
                (unsigned int)&v54,
                (__int64)v56,
                (__int64)packageFamilyName,
                (__int64)&v53);
        v27 = Windows::Internal::ComTaskPool::_MakeAndInitializeOnSTAThread<CFileActivatedEventArgs,Windows::ApplicationModel::Activation::IActivatedEventArgs,_lambda_1ad717cd63abbe8bc6f22e820e288409_>(
                v26,
                v25,
                &v49,
                v24);
        if ( v27 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x143,
            (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\associationlaunchexecutecommand.cpp",
            (const char *)(unsigned int)v27,
            v39);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v48);
        if ( v50 )
          winrt::com_ptr<IPropertyBag>::unconditional_release_ref(&v50);
        if ( v45 )
          winrt::com_ptr<IPropertyBag>::unconditional_release_ref(&v45);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43);
        if ( v51 )
          winrt::com_ptr<IPropertyBag>::unconditional_release_ref(&v51);
        if ( v47 )
          winrt::com_ptr<IPropertyBag>::unconditional_release_ref(&v47);
      }
      else
      {
        v43 = 0;
        v28 = CMarshaledInterface::Marshal(&v43, &GUID_b63ea76d_1f85_456f_a19c_48159efa858b, v46, 1);
        if ( v28 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x148,
            (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\associationlaunchexecutecommand.cpp",
            (const char *)(unsigned int)v28,
            v38);
        *(_QWORD *)v56 = WindowsGetStringRawBuffer(*a3, 0);
        v53 = WindowsGetStringRawBuffer(*((HSTRING *)this + 12), 0);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v49);
        v29 = _lambda_0b73f2a213eb7edf311fc48959107450_::_lambda_0b73f2a213eb7edf311fc48959107450_(
                (unsigned int)v58,
                (unsigned int)&v43,
                (unsigned int)&v54,
                (unsigned int)&v53,
                (__int64)packageFamilyName,
                (__int64)v56);
        v32 = Windows::Internal::ComTaskPool::_MakeAndInitializeOnSTAThread<CFileActivatedEventArgs,Windows::ApplicationModel::Activation::IActivatedEventArgs,_lambda_88b6e73b306a1e983eae8862895e0d4d_>(
                v31,
                v30,
                &v49,
                v29);
        if ( v32 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x14C,
            (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\associationlaunchexecutecommand.cpp",
            (const char *)(unsigned int)v32,
            v40);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43);
      }
      v44 = 0;
      *(_QWORD *)v41 = *((_QWORD *)this + 11);
      v33 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(*(_QWORD *)*a2 + 120LL))(
              *a2,
              *((_QWORD *)this + 29),
              *((_QWORD *)this + 27),
              0);
      if ( v33 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x151,
          (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\associationlaunchexecutecommand.cpp",
          (const char *)(unsigned int)v33,
          v41[0]);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v49);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v54);
    }
    if ( ppvOut )
      winrt::com_ptr<winrt::Windows::Foundation::IUnknown>::unconditional_release_ref(&ppvOut);
    if ( v7 )
      winrt::com_ptr<IPropertyBag>::unconditional_release_ref(&v57);
    v35 = v46;
    if ( v46 )
    {
      v46 = 0;
      ((void (__fastcall *)(struct IShellItemArray *))v35->lpVtbl->Release)(v35);
    }
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x15B,
                           (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\associationlaunch"
                                         "executecommand.cpp",
                           v34);
  }
  return result;
}

```

## disassembly

```asm
0x18004be8c  push    rbx
0x18004be8e  push    rsi
0x18004be8f  push    rdi
0x18004be90  push    r12
0x18004be92  push    r13
0x18004be94  push    r14
0x18004be96  push    r15
0x18004be98  sub     rsp, 1A0h
0x18004be9f  mov     rax, cs:__security_cookie
0x18004bea6  xor     rax, rsp
0x18004bea9  mov     [rsp+1D8h+var_48], rax
0x18004beb1  mov     r14, r9
0x18004beb4  mov     [rsp+1D8h+var_138], r9
0x18004bebc  mov     r12, r8
0x18004bebf  mov     r13, rdx
0x18004bec2  mov     rdi, rcx
0x18004bec5  xor     r15d, r15d
0x18004bec8  mov     [rsp+1D8h+var_170], r15
0x18004becd  lea     rcx, [rsp+1D8h+var_170]
0x18004bed2  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x18004bed7  lea     rdx, [rsp+1D8h+var_170]; struct IShellItemArray **
0x18004bedc  mov     rcx, rdi; this
0x18004bedf  call    ?TryCreateViewItemsArray@LaunchExecuteCommandBase@@IEAA_NPEAPEAUIShellItemArray@@@Z; LaunchExecuteCommandBase::TryCreateViewItemsArray(IShellItemArray * *)
0x18004bee4  test    al, al
0x18004bee6  jnz     short loc_18004BEF9
0x18004bee8  lea     rdx, [rdi+0A0h]
0x18004beef  lea     rcx, [rsp+1D8h+var_170]
0x18004bef4  call    ??4?$ComPtr@UIShellItemArray@@@WRL@Microsoft@@QEAAAEAV012@AEBV012@@Z; Microsoft::WRL::ComPtr<IShellItemArray>::operator=(Microsoft::WRL::ComPtr<IShellItemArray> const &)
0x18004bef9  mov     rbx, r15
0x18004befc  mov     [rsp+1D8h+var_118], rbx
0x18004bf04  mov     [rsp+1D8h+ppvOut], r15
0x18004bf0c  mov     rsi, r15
0x18004bf0f  cmp     [rdi+68h], r15d
0x18004bf13  jnz     short loc_18004BF83
0x18004bf15  lea     r9, [rsp+1D8h+ppvOut]; ppvOut
0x18004bf1d  lea     r8, ??$guid_v@UIUnknown@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; riid
0x18004bf24  lea     rdx, _GUID_bafa21d8_b071_4cd8_853e_341203e557d3; guidService
0x18004bf2b  mov     rcx, [rdi+20h]; punk
0x18004bf2f  call    cs:__imp_IUnknown_QueryService
0x18004bf35  test    eax, eax
0x18004bf37  js      short loc_18004BF83
0x18004bf39  mov     rax, [rsp+1D8h+ppvOut]
0x18004bf41  mov     [rsp+1D8h+ppvOut], r15
0x18004bf49  mov     [rsp+1D8h+var_188], rax
0x18004bf4e  lea     rdx, [rsp+1D8h+var_160]
0x18004bf53  lea     rcx, [rsp+1D8h+var_188]
0x18004bf58  call    ?NeighboringFilesQuery@?$consume_Windows_System_ILauncherOptions2@ULauncherOptions@System@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_System_ILauncherOptions2<winrt::Windows::System::LauncherOptions>::NeighboringFilesQuery(void)
0x18004bf5d  mov     rbx, [rax]
0x18004bf60  mov     [rax], r15
0x18004bf63  mov     [rsp+1D8h+var_118], rbx
0x18004bf6b  lea     rcx, [rsp+1D8h+var_160]; this
0x18004bf70  call    ??1_lambda_12ef4a55c56a96ec7ad58335194b061f_@@QEAA@XZ; _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_(void)
0x18004bf75  nop
0x18004bf76  lea     rcx, [rsp+1D8h+var_188]; this
0x18004bf7b  call    ??1_lambda_12ef4a55c56a96ec7ad58335194b061f_@@QEAA@XZ; _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_(void)
0x18004bf80  mov     rsi, rbx
0x18004bf83  call    cs:__imp_RtlIsMultiSessionSku
0x18004bf89  test    al, al
0x18004bf8b  jnz     loc_18004C5C1
0x18004bf91  mov     [rsp+1D8h+packageFamilyNameLength], 41h ; 'A'
0x18004bf9c  xor     edx, edx; length
0x18004bf9e  mov     rcx, [rdi+0E8h]; string
0x18004bfa5  call    cs:__imp_WindowsGetStringRawBuffer
0x18004bfab  lea     r8, [rsp+1D8h+packageFamilyName]; packageFamilyName
0x18004bfb3  lea     rdx, [rsp+1D8h+packageFamilyNameLength]; packageFamilyNameLength
0x18004bfbb  mov     rcx, rax; packageFullName
0x18004bfbe  call    cs:__imp_PackageFamilyNameFromFullName
0x18004bfc4  mov     rcx, [rsp+1D8h]; this
0x18004bfcc  test    eax, eax
0x18004bfce  jz      short loc_18004BFE4
0x18004bfd0  mov     r9d, eax; char *
0x18004bfd3  lea     r8, aOnecoreuapShel_19; "onecoreuap\\shell\\windows.system.launc"...
0x18004bfda  mov     edx, 118h; void *
0x18004bfdf  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18004bfe4  mov     [rsp+1D8h+var_130], r15
0x18004bfec  test    rsi, rsi
0x18004bfef  jz      loc_18004C0C8
0x18004bff5  mov     rdx, rbx
0x18004bff8  lea     rcx, [rsp+1D8h+var_168]
0x18004bffd  call    ??$as@UIStorageQueryResultBase@Search@Storage@Windows@winrt@@UIStorageFileQueryResult@234@$0A@@impl@winrt@@YA?AUIStorageQueryResultBase@Search@Storage@Windows@1@PEAUIStorageFileQueryResult@345@@Z; winrt::impl::as<winrt::Windows::Storage::Search::IStorageQueryResultBase,Windows::Storage::Search::IStorageFileQueryResult,0>(Windows::Storage::Search::IStorageFileQueryResult *)
0x18004c002  nop
0x18004c003  lea     rdx, [rsp+1D8h+var_148]
0x18004c00b  lea     rcx, [rsp+1D8h+var_168]
0x18004c010  call    ?Folder@?$consume_Windows_Storage_Search_IStorageQueryResultBase@UIStorageQueryResultBase@Search@Storage@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Storage_Search_IStorageQueryResultBase<winrt::Windows::Storage::Search::IStorageQueryResultBase>::Folder(void)
0x18004c015  nop
0x18004c016  mov     rdx, [rax]
0x18004c019  lea     rcx, [rsp+1D8h+var_160]
0x18004c01e  call    ??$as@UIStorageFolderQueryOperations@Search@Storage@Windows@winrt@@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@5@$0A@@impl@winrt@@YA?AUIStorageFolderQueryOperations@Search@Storage@Windows@1@PEAUtype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@01@@Z; winrt::impl::as<winrt::Windows::Storage::Search::IStorageFolderQueryOperations,winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type,0>(winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type *)
0x18004c023  nop
0x18004c024  lea     rcx, [rsp+1D8h+var_148]; this
0x18004c02c  call    ??1_lambda_12ef4a55c56a96ec7ad58335194b061f_@@QEAA@XZ; _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_(void)
0x18004c031  lea     rdx, [rsp+1D8h+var_150]
0x18004c039  lea     rcx, [rsp+1D8h+var_168]
0x18004c03e  call    ?GetCurrentQueryOptions@?$consume_Windows_Storage_Search_IStorageQueryResultBase@UIStorageQueryResultBase@Search@Storage@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Storage_Search_IStorageQueryResultBase<winrt::Windows::Storage::Search::IStorageQueryResultBase>::GetCurrentQueryOptions(void)
0x18004c043  nop
0x18004c044  mov     r8, rax
0x18004c047  lea     rdx, [rsp+1D8h+var_188]
0x18004c04c  lea     rcx, [rsp+1D8h+var_160]
0x18004c051  call    ?CreateFileQueryWithOptions@?$consume_Windows_Storage_Search_IStorageFolderQueryOperations@UIStorageFolderQueryOperations@Search@Storage@Windows@winrt@@@impl@winrt@@QEBA@AEBUQueryOptions@Search@Storage@Windows@3@@Z; winrt::impl::consume_Windows_Storage_Search_IStorageFolderQueryOperations<winrt::Windows::Storage::Search::IStorageFolderQueryOperations>::CreateFileQueryWithOptions(winrt::Windows::Storage::Search::QueryOptions const &)
0x18004c056  nop
0x18004c057  lea     rcx, [rsp+1D8h+var_150]; this
0x18004c05f  call    ??1_lambda_12ef4a55c56a96ec7ad58335194b061f_@@QEAA@XZ; _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_(void)
0x18004c064  mov     esi, 1
0x18004c069  mov     r9d, esi
0x18004c06c  mov     r8, [rsp+1D8h+var_188]
0x18004c071  lea     rdx, _GUID_52fda447_2baa_412c_b29f_d4b1778efa1e
0x18004c078  lea     rcx, [rsp+1D8h+var_130]
0x18004c080  call    ?Marshal@CMarshaledInterface@@QEAAJAEBU_GUID@@PEAUIUnknown@@W4MARSHAL_KIND@@@Z; CMarshaledInterface::Marshal(_GUID const &,IUnknown *,MARSHAL_KIND)
0x18004c085  mov     rcx, [rsp+1D8h]; this
0x18004c08d  test    eax, eax
0x18004c08f  jns     short loc_18004C0A6
0x18004c091  mov     r9d, eax; char *
0x18004c094  lea     r8, aOnecoreuapShel_19; "onecoreuap\\shell\\windows.system.launc"...
0x18004c09b  mov     edx, 124h; void *
0x18004c0a0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004c0a6  lea     rcx, [rsp+1D8h+var_188]; this
0x18004c0ab  call    ??1_lambda_12ef4a55c56a96ec7ad58335194b061f_@@QEAA@XZ; _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_(void)
0x18004c0b0  nop
0x18004c0b1  lea     rcx, [rsp+1D8h+var_160]; this
0x18004c0b6  call    ??1_lambda_12ef4a55c56a96ec7ad58335194b061f_@@QEAA@XZ; _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_(void)
0x18004c0bb  nop
0x18004c0bc  lea     rcx, [rsp+1D8h+var_168]; this
0x18004c0c1  call    ??1_lambda_12ef4a55c56a96ec7ad58335194b061f_@@QEAA@XZ; _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_(void)
0x18004c0c6  jmp     short loc_18004C0CD
0x18004c0c8  mov     esi, 1
0x18004c0cd  mov     [rsp+1D8h+var_158], r15
0x18004c0d5  cmp     dword ptr [rdi+68h], 3
0x18004c0d9  jnz     loc_18004C3D8
0x18004c0df  mov     [rsp+1D8h+var_168], r15
0x18004c0e4  mov     rcx, [rsp+1D8h+var_170]
0x18004c0e9  mov     rax, [rcx]
0x18004c0ec  lea     r8, [rsp+1D8h+var_168]
0x18004c0f1  xor     edx, edx
0x18004c0f3  mov     rax, [rax+40h]
0x18004c0f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c0fc  mov     rcx, [rsp+1D8h]; this
0x18004c104  test    eax, eax
0x18004c106  jns     short loc_18004C11C
0x18004c108  mov     r9d, eax; char *
0x18004c10b  lea     r8, aOnecoreuapShel_19; "onecoreuap\\shell\\windows.system.launc"...
0x18004c112  mov     edx, 12Bh; void *
0x18004c117  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004c11c  mov     [rsp+1D8h+var_148], r15
0x18004c124  lea     r9, [rsp+1D8h+var_148]
0x18004c12c  lea     r8, _GUID_72d1cb78_b3ef_4f75_a80b_6fd9dae2944b
0x18004c133  mov     edx, 1002h
0x18004c138  mov     rcx, [rsp+1D8h+var_168]
0x18004c13d  call    cs:__imp_STORAGE_CreateStorageItemFromShellItem_FullTrustCaller
0x18004c143  mov     rcx, [rsp+1D8h]; this
0x18004c14b  test    eax, eax
0x18004c14d  jns     short loc_18004C163
0x18004c14f  mov     r9d, eax; char *
0x18004c152  lea     r8, aOnecoreuapShel_19; "onecoreuap\\shell\\windows.system.launc"...
0x18004c159  mov     edx, 12Eh; void *
0x18004c15e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004c163  mov     [rsp+1D8h+var_188], r15
0x18004c168  mov     r9d, esi
0x18004c16b  mov     r8, [rsp+1D8h+var_148]
0x18004c173  lea     rdx, _GUID_72d1cb78_b3ef_4f75_a80b_6fd9dae2944b
0x18004c17a  lea     rcx, [rsp+1D8h+var_188]
0x18004c17f  call    ?Marshal@CMarshaledInterface@@QEAAJAEBU_GUID@@PEAUIUnknown@@W4MARSHAL_KIND@@@Z; CMarshaledInterface::Marshal(_GUID const &,IUnknown *,MARSHAL_KIND)
0x18004c184  mov     rcx, [rsp+1D8h]; this
0x18004c18c  test    eax, eax
0x18004c18e  jns     short loc_18004C1A4
0x18004c190  mov     r9d, eax; char *
0x18004c193  lea     r8, aOnecoreuapShel_19; "onecoreuap\\shell\\windows.system.launc"...
0x18004c19a  mov     edx, 131h; void *
0x18004c19f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004c1a4  mov     [rsp+1D8h+var_178], r15
0x18004c1a9  mov     [rsp+1D8h+var_150], r15
0x18004c1b1  lea     r9, [rsp+1D8h+var_150]; ppvOut
0x18004c1b9  lea     r8, _GUID_121b45ea_779e_40f8_8e4f_dcb2bc788e36; riid
0x18004c1c0  lea     rdx, guidService; guidService
0x18004c1c7  mov     rcx, [rdi+20h]; punk
0x18004c1cb  call    cs:__imp_IUnknown_QueryService
0x18004c1d1  test    eax, eax
0x18004c1d3  js      loc_18004C274
0x18004c1d9  mov     r14, [rsp+1D8h+var_150]
0x18004c1e1  mov     rax, [r14]
0x18004c1e4  mov     r15, [rax+18h]
0x18004c1e8  cmp     [rsp+1D8h+var_178], 0
0x18004c1ee  jz      short loc_18004C1FA
0x18004c1f0  lea     rcx, [rsp+1D8h+var_178]
0x18004c1f5  call    ?unconditional_release_ref@?$com_ptr@UIPropertyBag@@@winrt@@AEAAXXZ; winrt::com_ptr<IPropertyBag>::unconditional_release_ref(void)
0x18004c1fa  lea     rdx, [rsp+1D8h+var_178]
0x18004c1ff  mov     rcx, r14
0x18004c202  mov     rax, r15
0x18004c205  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c20a  mov     rcx, [rsp+1D8h]; this
0x18004c212  xor     r15d, r15d
0x18004c215  test    eax, eax
0x18004c217  jns     short loc_18004C22D
0x18004c219  mov     r9d, eax; char *
0x18004c21c  lea     r8, aOnecoreuapShel_19; "onecoreuap\\shell\\windows.system.launc"...
0x18004c223  mov     edx, 137h; void *
0x18004c228  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004c22d  mov     r14, [rsp+1D8h+var_138]
0x18004c235  mov     [rsp+1D8h+var_160], r15
0x18004c23a  mov     r9d, esi
0x18004c23d  mov     r8, [rsp+1D8h+var_178]
0x18004c242  lea     rdx, _GUID_b63ea76d_1f85_456f_a19c_48159efa858b
0x18004c249  lea     rcx, [rsp+1D8h+var_160]
0x18004c24e  call    ?Marshal@CMarshaledInterface@@QEAAJAEBU_GUID@@PEAUIUnknown@@W4MARSHAL_KIND@@@Z; CMarshaledInterface::Marshal(_GUID const &,IUnknown *,MARSHAL_KIND)
0x18004c253  mov     rcx, [rsp+1D8h]; this
0x18004c25b  test    eax, eax
0x18004c25d  jns     short loc_18004C2BA
0x18004c25f  mov     r9d, eax; char *
0x18004c262  lea     r8, aOnecoreuapShel_19; "onecoreuap\\shell\\windows.system.launc"...
0x18004c269  mov     edx, 13Fh; void *
0x18004c26e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004c274  cmp     [rsp+1D8h+var_178], r15
0x18004c279  jz      short loc_18004C285
0x18004c27b  lea     rcx, [rsp+1D8h+var_178]
0x18004c280  call    ?unconditional_release_ref@?$com_ptr@UIPropertyBag@@@winrt@@AEAAXXZ; winrt::com_ptr<IPropertyBag>::unconditional_release_ref(void)
0x18004c285  lea     r8, [rsp+1D8h+var_178]
0x18004c28a  lea     rdx, _GUID_b63ea76d_1f85_456f_a19c_48159efa858b
0x18004c291  xor     ecx, ecx
0x18004c293  call    cs:__imp_CShellItemArray_CreateInstance
0x18004c299  mov     rcx, [rsp+1D8h]; this
0x18004c2a1  test    eax, eax
0x18004c2a3  jns     short loc_18004C235
0x18004c2a5  mov     r9d, eax; char *
0x18004c2a8  lea     r8, aOnecoreuapShel_19; "onecoreuap\\shell\\windows.system.launc"...
0x18004c2af  mov     edx, 13Bh; void *
0x18004c2b4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004c2ba  xor     edx, edx; length
0x18004c2bc  mov     rcx, [r12]; string
0x18004c2c0  call    cs:__imp_WindowsGetStringRawBuffer
0x18004c2c6  mov     [rsp+1D8h+var_138], rax
0x18004c2ce  xor     edx, edx; length
0x18004c2d0  mov     rcx, [rdi+60h]; string
0x18004c2d4  call    cs:__imp_WindowsGetStringRawBuffer
0x18004c2da  mov     qword ptr [rsp+1D8h+var_120], rax
0x18004c2e2  lea     rcx, [rsp+1D8h+var_158]
0x18004c2ea  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004c2ef  lea     rax, [rsp+1D8h+var_138]
0x18004c2f7  mov     [rsp+1D8h+var_1A8], rax
0x18004c2fc  lea     rax, [rsp+1D8h+packageFamilyName]
0x18004c304  mov     [rsp+1D8h+var_1B0], rax
0x18004c309  lea     rax, [rsp+1D8h+var_120]
0x18004c311  mov     qword ptr [rsp+1D8h+var_1B8], rax; int
0x18004c316  lea     r9, [rsp+1D8h+var_130]
0x18004c31e  lea     r8, [rsp+1D8h+var_188]
0x18004c323  lea     rdx, [rsp+1D8h+var_160]
0x18004c328  lea     rcx, [rsp+1D8h+var_110]
0x18004c330  call    ??0_lambda_1ad717cd63abbe8bc6f22e820e288409_@@QEAA@AEAV?$CMarshalInterfaceOnce@UIShellItemArray@@@@AEAV?$CMarshalInterfaceOnce@UIStorageFolder@Storage@Windows@@@@AEAV?$CMarshalInterfaceOnce@UIStorageFileQueryResult@Search@Storage@Windows@@@@AEAPEBGAEAY0EB@G3@Z; _lambda_1ad717cd63abbe8bc6f22e820e288409_::_lambda_1ad717cd63abbe8bc6f22e820e288409_(CMarshalInterfaceOnce<IShellItemArray> &,CMarshalInterfaceOnce<Windows::Storage::IStorageFolder> &,CMarshalInterfaceOnce<Windows::Storage::Search::IStorageFileQueryResult> &,ushort const * &,ushort (&)[65],ushort const * &)
0x18004c335  mov     r9, rax
0x18004c338  lea     r8, [rsp+1D8h+var_158]
0x18004c340  call    ??$_MakeAndInitializeOnSTAThread@VCFileActivatedEventArgs@@UIActivatedEventArgs@Activation@ApplicationModel@Windows@@V_lambda_1ad717cd63abbe8bc6f22e820e288409_@@@ComTaskPool@Internal@Windows@@CAJW4TaskOptions@12@KPEAPEAUIActivatedEventArgs@Activation@ApplicationModel@2@AEBV_lambda_1ad717cd63abbe8bc6f22e820e288409_@@@Z; Windows::Internal::ComTaskPool::_MakeAndInitializeOnSTAThread<CFileActivatedEventArgs,Windows::ApplicationModel::Activation::IActivatedEventArgs,_lambda_1ad717cd63abbe8bc6f22e820e288409_>(Windows::Internal::TaskOptions,ulong,Windows::ApplicationModel::Activation::IActivatedEventArgs * *,_lambda_1ad717cd63abbe8bc6f22e820e288409_ const &)
0x18004c345  mov     rcx, [rsp+1D8h]; this
0x18004c34d  test    eax, eax
0x18004c34f  jns     short loc_18004C366
0x18004c351  mov     r9d, eax; char *
0x18004c354  lea     r8, aOnecoreuapShel_19; "onecoreuap\\shell\\windows.system.launc"...
0x18004c35b  mov     edx, 143h; void *
0x18004c360  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004c366  lea     rcx, [rsp+1D8h+var_160]
0x18004c36b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004c370  nop
0x18004c371  cmp     [rsp+1D8h+var_150], r15
0x18004c379  jz      short loc_18004C389
0x18004c37b  lea     rcx, [rsp+1D8h+var_150]
0x18004c383  call    ?unconditional_release_ref@?$com_ptr@UIPropertyBag@@@winrt@@AEAAXXZ; winrt::com_ptr<IPropertyBag>::unconditional_release_ref(void)
0x18004c388  nop
0x18004c389  cmp     [rsp+1D8h+var_178], r15
0x18004c38e  jz      short loc_18004C39B
0x18004c390  lea     rcx, [rsp+1D8h+var_178]
0x18004c395  call    ?unconditional_release_ref@?$com_ptr@UIPropertyBag@@@winrt@@AEAAXXZ; winrt::com_ptr<IPropertyBag>::unconditional_release_ref(void)
0x18004c39a  nop
0x18004c39b  lea     rcx, [rsp+1D8h+var_188]
0x18004c3a0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004c3a5  nop
0x18004c3a6  cmp     [rsp+1D8h+var_148], r15
0x18004c3ae  jz      short loc_18004C3BE
0x18004c3b0  lea     rcx, [rsp+1D8h+var_148]
0x18004c3b8  call    ?unconditional_release_ref@?$com_ptr@UIPropertyBag@@@winrt@@AEAAXXZ; winrt::com_ptr<IPropertyBag>::unconditional_release_ref(void)
0x18004c3bd  nop
0x18004c3be  cmp     [rsp+1D8h+var_168], r15
0x18004c3c3  jz      loc_18004C4C2
0x18004c3c9  lea     rcx, [rsp+1D8h+var_168]
0x18004c3ce  call    ?unconditional_release_ref@?$com_ptr@UIPropertyBag@@@winrt@@AEAAXXZ; winrt::com_ptr<IPropertyBag>::unconditional_release_ref(void)
0x18004c3d3  jmp     loc_18004C4C2
0x18004c3d8  mov     [rsp+1D8h+var_188], r15
0x18004c3dd  mov     r9d, esi
0x18004c3e0  mov     r8, [rsp+1D8h+var_170]
0x18004c3e5  lea     rdx, _GUID_b63ea76d_1f85_456f_a19c_48159efa858b
0x18004c3ec  lea     rcx, [rsp+1D8h+var_188]
0x18004c3f1  call    ?Marshal@CMarshaledInterface@@QEAAJAEBU_GUID@@PEAUIUnknown@@W4MARSHAL_KIND@@@Z; CMarshaledInterface::Marshal(_GUID const &,IUnknown *,MARSHAL_KIND)
0x18004c3f6  mov     rcx, [rsp+1D8h]; this
0x18004c3fe  test    eax, eax
0x18004c400  jns     short loc_18004C416
0x18004c402  mov     r9d, eax; char *
0x18004c405  lea     r8, aOnecoreuapShel_19; "onecoreuap\\shell\\windows.system.launc"...
0x18004c40c  mov     edx, 148h; void *
0x18004c411  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004c416  xor     edx, edx; length
0x18004c418  mov     rcx, [r12]; string
0x18004c41c  call    cs:__imp_WindowsGetStringRawBuffer
0x18004c422  mov     qword ptr [rsp+1D8h+var_120], rax
0x18004c42a  xor     edx, edx; length
  ... truncated ...
```
