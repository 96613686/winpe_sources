# SttExperienceManager::AddMessage(HSTRING__ *,HSTRING__ *,Windows::Gaming::UI::GameChatMessageOrigin)

- ea: `0x180337e50`
- end: `0x180338a04`
- name: `?AddMessage@SttExperienceManager@@UEAAJPEAUHSTRING__@@0W4GameChatMessageOrigin@UI@Gaming@Windows@@@Z`
- size: `2996`
- prototype: ``
- caller_count: `0`
- callee_count: `34`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180008acc`
- `0x18000ae4c`
- `0x18000b7e8`
- `0x18000c350`
- `0x180037e18`
- `0x18003c5e4`
- `0x180052980`
- `0x1800542a8`
- `0x180059ddc`
- `0x18008c4e0`
- `0x1800a3cec`
- `0x1800a9328`
- `0x1800f4a30`
- `0x1800fc80c`
- `0x18013d330`
- `0x18014bac8`
- `0x18015a840`
- `0x180193320`
- `0x1802cbaac`
- `0x1802cbae8`
- `0x180308420`
- `0x18031b318`
- `0x18031b390`
- `0x1803374b4`
- `0x1803375f4`
- `0x1803376b0`
- `0x180337860`
- `0x180337b00`
- `0x180337b9c`
- `0x180337e50`
- `0x180338bb8`
- `0x180339b54`
- `0x18036dd0c`
- `0x1803a3010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18033838d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1803386ab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1803387d2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180338890`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18033891c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180338972`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1803389ae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18033838d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1803386ab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1803387d2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180338890`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18033891c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180338972`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1803389ae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180338289`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1803382dc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18033839b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1803383ac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180338985`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180338994`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1803389c6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1803389d7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180338289`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1803382dc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18033839b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1803383ac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180338985`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180338994`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1803389c6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1803389d7`

## pseudocode

```c
// Hidden C++ exception states: #wind=25
__int64 __fastcall SttExperienceManager::AddMessage(_QWORD *a1, __int64 a2, __int64 a3, unsigned int a4)
{
  bool v5; // si
  _QWORD *v6; // r14
  __int64 v7; // rcx
  _QWORD *v8; // rax
  int v9; // eax
  unsigned int v10; // ebx
  LPVOID v11; // rdi
  __int64 (__fastcall *v12)(LPVOID, _QWORD, __int64 *); // rbx
  __int64 v13; // rax
  int v14; // eax
  __int64 v15; // rbx
  int v16; // eax
  __int64 v17; // rdx
  const unsigned __int16 *v18; // rdx
  _QWORD *v19; // rax
  int v20; // eax
  int v21; // eax
  HSTRING v23; // rdi
  __int64 (__fastcall *v24)(HSTRING, PVOID, __int64 *); // rbx
  int v25; // eax
  _QWORD *v26; // rax
  int v27; // eax
  LPVOID v28; // rdi
  __int64 (__fastcall *v29)(LPVOID, __int64, HSTRING *); // rbx
  int v30; // eax
  unsigned __int16 **v31; // rdx
  int CallingProcessPackageFamilyName; // eax
  unsigned __int16 **v33; // rdx
  int CallingProcessAppId; // eax
  HSTRING v35; // rbx
  _QWORD *v36; // r14
  int v37; // eax
  int v38; // edi
  HSTRING v39; // rsi
  __int64 (__fastcall *v40)(HSTRING, __int64, __int64, __int64 *); // rdi
  __int64 v41; // rdx
  __int64 v42; // rsi
  __int64 (__fastcall *v43)(__int64, _QWORD *); // rdi
  __int64 v44; // rsi
  __int64 (__fastcall *v45)(__int64, __int64 *); // rdi
  __int64 v46; // rdx
  __int64 v47; // rsi
  __int64 (__fastcall *v48)(__int64, _QWORD, __int64 *); // rdi
  __int64 v49; // rax
  int v50; // eax
  __int64 v51; // rsi
  __int64 (__fastcall *v52)(__int64, __int64, HSTRING *); // rdi
  int v53; // eax
  HSTRING v54; // rdi
  __int64 (__fastcall *v55)(HSTRING, HSTRING *); // rsi
  __int64 v56; // rdx
  HSTRING v57; // rdi
  __int64 (__fastcall *v58)(HSTRING, HSTRING *); // rsi
  __int64 v59; // r13
  __int64 v60; // rcx
  const char *v61; // r9
  __int128 *v62; // rax
  char v63; // si
  void *v64; // rdi
  __int64 v65; // rbx
  HSTRING v66; // rsi
  _QWORD *v67; // rax
  __int64 v68; // rax
  __int64 v69; // rdx
  const char *v70; // r9
  __int64 v71; // rax
  bool v72; // zf
  __int64 v73; // rsi
  HSTRING v74; // rcx
  __int64 v75; // r15
  void (__fastcall *v76)(__int64, _QWORD, HSTRING, __int64, __int64, unsigned int); // r14
  HSTRING v77; // rsi
  _QWORD *v78; // rax
  int v79; // [rsp+20h] [rbp-108h]
  HSTRING string; // [rsp+40h] [rbp-E8h] BYREF
  HSTRING v81; // [rsp+48h] [rbp-E0h] BYREF
  HSTRING v82; // [rsp+50h] [rbp-D8h] BYREF
  __int64 v83; // [rsp+58h] [rbp-D0h] BYREF
  LPVOID pv; // [rsp+60h] [rbp-C8h] BYREF
  LPVOID v85; // [rsp+68h] [rbp-C0h] BYREF
  char v86; // [rsp+70h] [rbp-B8h]
  unsigned int v87; // [rsp+74h] [rbp-B4h]
  _BYTE v88[8]; // [rsp+78h] [rbp-B0h] BYREF
  __int64 v89; // [rsp+80h] [rbp-A8h] BYREF
  __int64 v90; // [rsp+88h] [rbp-A0h] BYREF
  __int128 v91; // [rsp+90h] [rbp-98h] BYREF
  __int64 v92; // [rsp+A0h] [rbp-88h]
  __int64 v93; // [rsp+A8h] [rbp-80h]
  __int64 v94; // [rsp+B0h] [rbp-78h]
  HSTRING_HEADER hstringHeader; // [rsp+B8h] [rbp-70h] BYREF
  __int64 v96; // [rsp+D0h] [rbp-58h]
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+0h]

  v87 = a4;
  v93 = a3;
  v94 = a2;
  v5 = 0;
  v6 = a1 + 25;
  wil::EnterCriticalSection(&v81, a1 + 25);
  SttExperienceManager::ResetHideAndCloseTimers((SttExperienceManager *)(a1 - 16));
  v7 = a1[8];
  if ( v7 )
  {
    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v7 + 40LL))(v7, 0);
    v21 = SttExperienceManager::TriggerHideAndCloseTimers(a1 - 16);
    v10 = v21;
    if ( v21 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x288,
        (unsigned int)"shell\\twinui\\sttexperiencemanager\\lib\\sttexperiencemanager.cpp",
        (const char *)(unsigned int)v21,
        v79);
      goto LABEL_19;
    }
  }
  else
  {
    v85 = 0;
    v8 = (_QWORD *)Windows::Internal::StringReference::StringReference(
                     (HSTRING *)&hstringHeader,
                     L"Windows.System.Launcher");
    v9 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::System::ILauncherStatics2>>(
           *v8,
           &v85);
    v10 = v9;
    if ( v9 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x276,
        (unsigned int)"shell\\twinui\\sttexperiencemanager\\lib\\sttexperiencemanager.cpp",
        (const char *)(unsigned int)v9,
        v79);
LABEL_12:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v85);
LABEL_19:
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(&v81);
      return v10;
    }
    v83 = 0;
    v11 = v85;
    v12 = *(__int64 (__fastcall **)(LPVOID, _QWORD, __int64 *))(*(_QWORD *)v85 + 104LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v83);
    v13 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &c_AppProtocol);
    v14 = v12(v11, *(_QWORD *)(v13 + 24), &v83);
    v10 = v14;
    if ( v14 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x278,
        (unsigned int)"shell\\twinui\\sttexperiencemanager\\lib\\sttexperiencemanager.cpp",
        (const char *)(unsigned int)v14,
        v79);
LABEL_11:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v83);
      goto LABEL_12;
    }
    v82 = 0;
    v15 = v83;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v82);
    v16 = BlockOnCompletionAndGetResults<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::AppInfo *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::AppInfo *> *>,Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::AppInfo *> *>(
            v15,
            &v82);
    v10 = v16;
    if ( v16 < 0 )
    {
      v17 = 634;
LABEL_10:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v17,
        (unsigned int)"shell\\twinui\\sttexperiencemanager\\lib\\sttexperiencemanager.cpp",
        (const char *)(unsigned int)v16,
        v79);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v82);
      goto LABEL_11;
    }
    LODWORD(pv) = 0;
    v16 = (*(__int64 (__fastcall **)(HSTRING, LPVOID *))(*(_QWORD *)v82 + 56LL))(v82, &pv);
    v10 = v16;
    if ( v16 < 0 )
    {
      v17 = 637;
      goto LABEL_10;
    }
    v5 = (_DWORD)pv != 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v82);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v83);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v85);
  }
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(&v81);
  if ( v5 )
  {
    v81 = 0;
    v19 = (_QWORD *)Windows::Internal::StringReference::StringReference(
                      (HSTRING *)&hstringHeader,
                      (const unsigned __int16 (*)[23])v18);
    v20 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory>>(
            *v19,
            &v81);
    v10 = v20;
    if ( v20 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x290,
        (unsigned int)"shell\\twinui\\sttexperiencemanager\\lib\\sttexperiencemanager.cpp",
        (const char *)(unsigned int)v20,
        v79);
LABEL_29:
      Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v81);
      return v10;
    }
    v83 = 0;
    v23 = v81;
    v24 = *(__int64 (__fastcall **)(HSTRING, PVOID, __int64 *))(*(_QWORD *)v81 + 48LL);
    Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v83);
    Windows::Internal::StringReference::_ConstructorHelper(
      (Windows::Internal::StringReference *)&hstringHeader,
      c_AppProtocolUri);
    v25 = v24(v23, hstringHeader.Reserved.Reserved1, &v83);
    v10 = v25;
    if ( v25 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x293,
        (unsigned int)"shell\\twinui\\sttexperiencemanager\\lib\\sttexperiencemanager.cpp",
        (const char *)(unsigned int)v25,
        v79);
LABEL_28:
      Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v83);
      goto LABEL_29;
    }
    v85 = 0;
    v26 = (_QWORD *)Windows::Internal::StringReference::StringReference(
                      (HSTRING *)&hstringHeader,
                      L"Windows.System.Launcher");
    v27 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::System::ILauncherStatics>>(
            *v26,
            &v85);
    v10 = v27;
    if ( v27 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x296,
        (unsigned int)"shell\\twinui\\sttexperiencemanager\\lib\\sttexperiencemanager.cpp",
        (const char *)(unsigned int)v27,
        v79);
LABEL_27:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v85);
      goto LABEL_28;
    }
    v82 = 0;
    v28 = v85;
    v29 = *(__int64 (__fastcall **)(LPVOID, __int64, HSTRING *))(*(_QWORD *)v85 + 64LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v82);
    v30 = v29(v28, v83, &v82);
    v10 = v30;
    if ( v30 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x299,
        (unsigned int)"shell\\twinui\\sttexperiencemanager\\lib\\sttexperiencemanager.cpp",
        (const char *)(unsigned int)v30,
        v79);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v82);
      goto LABEL_27;
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v82);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v85);
    Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v83);
    Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v81);
  }
  pv = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &pv,
    0);
  CallingProcessPackageFamilyName = CallerIdentity::GetCallingProcessPackageFamilyName((CallerIdentity *)&pv, v31);
  v10 = CallingProcessPackageFamilyName;
  if ( CallingProcessPackageFamilyName < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x29E,
      (unsigned int)"shell\\twinui\\sttexperiencemanager\\lib\\sttexperiencemanager.cpp",
      (const char *)(unsigned int)CallingProcessPackageFamilyName,
      v79);
LABEL_33:
    if ( pv )
      CoTaskMemFree(pv);
    return v10;
  }
  v85 = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &v85,
    0);
  CallingProcessAppId = CallerIdentity::GetCallingProcessAppId((CallerIdentity *)&v85, v33);
  v10 = CallingProcessAppId;
  if ( CallingProcessAppId < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2A1,
      (unsigned int)"shell\\twinui\\sttexperiencemanager\\lib\\sttexperiencemanager.cpp",
      (const char *)(unsigned int)CallingProcessAppId,
      v79);
    if ( v85 )
      CoTaskMemFree(v85);
    goto LABEL_33;
  }
  string = 0;
  v35 = (HSTRING)v85;
  if ( v85 )
  {
    wil::EnterCriticalSection(v88, v6);
    v36 = a1 + 12;
    if ( !a1[12] )
    {
      v81 = 0;
      v96 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        &hstringHeader,
        L"WindowsInternal.Shell.UnifiedTile.UnifiedTileManager",
        0x35u,
        0x34u);
      v37 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::IUnifiedTileManagerStatics>>(
              v96,
              &v81);
      v38 = v37;
      if ( v37 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2AE,
          (unsigned int)"shell\\twinui\\sttexperiencemanager\\lib\\sttexperiencemanager.cpp",
          (const char *)(unsigned int)v37,
          v79);
LABEL_42:
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v81);
LABEL_43:
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(v88);
        WindowsDeleteString(string);
        string = 0;
        CoTaskMemFree(v35);
        if ( pv )
          CoTaskMemFree(pv);
        return (unsigned int)v38;
      }
      v90 = 0;
      v39 = v81;
      v40 = *(__int64 (__fastcall **)(HSTRING, __int64, __int64, __int64 *))(*(_QWORD *)v81 + 48LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v90);
      v38 = v40(v39, 3, 3, &v90);
      if ( v38 < 0 )
      {
        v41 = 697;
LABEL_48:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v41,
          (unsigned int)"shell\\twinui\\sttexperiencemanager\\lib\\sttexperiencemanager.cpp",
          (const char *)(unsigned int)v38,
          v79);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v90);
        goto LABEL_42;
      }
      v38 = wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<WindowsInternal::Shell::UnifiedTile::UnifiedTileManager *> *>(v90);
      if ( v38 < 0 )
      {
        v41 = 698;
        goto LABEL_48;
      }
      v42 = v90;
      v43 = *(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v90 + 64LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(a1 + 12);
      v38 = v43(v42, a1 + 12);
      if ( v38 < 0 )
      {
        v41 = 699;
        goto LABEL_48;
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v90);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v81);
    }
    v89 = 0;
    v44 = *v36;
    v45 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)*v36 + 80LL);
    Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v89);
    v38 = v45(v44, &v89);
    if ( v38 < 0 )
    {
      v46 = 704;
LABEL_56:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v46,
        (unsigned int)"shell\\twinui\\sttexperiencemanager\\lib\\sttexperiencemanager.cpp",
        (const char *)(unsigned int)v38,
        v79);
LABEL_57:
      Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v89);
      goto LABEL_43;
    }
    v38 = wil::details::WaitForCompletion<Windows::Foundation::IAsyncAction *>(v89);
    if ( v38 < 0 )
    {
      v46 = 705;
      goto LABEL_56;
    }
    if ( !a1[10] )
    {
      v96 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        &hstringHeader,
        L"WindowsInternal.Shell.UnifiedTile.PackagedUnifiedTileIdentifier",
        0x40u,
        0x3Fu);
      v38 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::IPackagedUnifiedTileIdentifierFactory>>(
              v96,
              a1 + 10);
      if ( v38 < 0 )
      {
        v46 = 710;
        goto LABEL_56;
      }
    }
    v83 = 0;
    v47 = a1[10];
    v48 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v47 + 48LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v83);
    v81 = v35;
    v49 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v81);
    v50 = v48(v47, *(_QWORD *)(v49 + 24), &v83);
    v38 = v50;
    if ( v50 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2CB,
        (unsigned int)"shell\\twinui\\sttexperiencemanager\\lib\\sttexperiencemanager.cpp",
        (const char *)(unsigned int)v50,
        v79);
LABEL_65:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v83);
      goto LABEL_57;
    }
    v82 = 0;
    v51 = *v36;
    v52 = *(__int64 (__fastcall **)(__int64, __int64, HSTRING *))(*(_QWORD *)*v36 + 72LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v82);
    v53 = v52(v51, v83, &v82);
    v38 = v53;
    if ( v53 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2CF,
        (unsigned int)"shell\\twinui\\sttexperiencemanager\\lib\\sttexperiencemanager.cpp",
        (const char *)(unsigned int)v53,
        v79);
LABEL_68:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v82);
      goto LABEL_65;
    }
    v54 = v82;
    if ( v82 )
    {
      v81 = 0;
      v55 = *(__int64 (__fastcall **)(HSTRING, HSTRING *))(*(_QWORD *)v82 + 56LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v81);
      v38 = v55(v54, &v81);
      if ( v38 < 0 )
      {
        v56 = 725;
LABEL_72:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v56,
          (unsigned int)"shell\\twinui\\sttexperiencemanager\\lib\\sttexperiencemanager.cpp",
          (const char *)(unsigned int)v38,
          v79);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v81);
        goto LABEL_68;
      }
      v57 = v81;
      if ( v81 )
      {
        v58 = *(__int64 (__fastcall **)(HSTRING, HSTRING *))(*(_QWORD *)v81 + 48LL);
        WindowsDeleteString(string);
        string = 0;
        v38 = v58(v57, &string);
        if ( v38 < 0 )
        {
          v56 = 729;
          goto LABEL_72;
        }
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v81);
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v82);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v83);
    Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v89);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(v88);
    v6 = a1 + 25;
  }
  v86 = 0;
  v91 = 0;
  v59 = 0;
  v92 = 0;
  wil::EnterCriticalSection(&v82, v6);
  v62 = (__int128 *)(a1 + 19);
  if ( (__int64)(a1[20] - a1[19]) >> 3 )
  {
    try
    {
      v63 = 1;
      if ( &v91 != v62 )
      {
        std::vector<Microsoft::WRL::ComPtr<SttInternal::IInternalMessageReceivedListener>>::_Assign_counted_range<Microsoft::WRL::ComPtr<SttInternal::IInternalMessageReceivedListener> *>(
          &v91,
          *(_QWORD *)v62);
        v59 = v92;
      }
      v64 = pv;
    }
    catch ( ... )
    {
      v87 = wil::details::in1diag3::Return_CaughtException(
              retaddr,
              (void *)0x2EC,
              (unsigned int)"shell\\twinui\\sttexperiencemanager\\lib\\sttexperiencemanager.cpp",
              v61);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(&v82);
      v65 = v91;
      if ( (_QWORD)v91 )
      {
        std::_Destroy_range<std::allocator<Microsoft::WRL::ComPtr<SttInternal::IInternalMessageReceivedListener>>>(
          v91,
          *((_QWORD *)&v91 + 1));
        std::_Deallocate<16>(v65, (v92 - v65) & 0xFFFFFFFFFFFFFFF8uLL);
      }
      WindowsDeleteString(string);
      goto LABEL_100;
    }
  }
  else
  {
    v66 = string;
    v64 = pv;
    v67 = (_QWORD *)SttExperienceManager::CreateHString(v60, &v81, pv);
    v68 = StoredMessage::StoredMessage(&hstringHeader, *v67, v66, v94, v93, v87);
    v69 = a1[23];
    if ( v69 == a1[24] )
    {
      try
      {
        std::vector<StoredMessage>::_Emplace_reallocate<StoredMessage>(a1 + 22);
      }
      catch ( ... )
      {
        v87 = wil::details::in1diag3::Return_CaughtException(
                retaddr,
                (void *)0x2FA,
                (unsigned int)"shell\\twinui\\sttexperiencemanager\\lib\\sttexperiencemanager.cpp",
                v70);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(&v82);
        WindowsDeleteString(string);
LABEL_100:
        string = 0;
        if ( v85 )
          CoTaskMemFree(v85);
        if ( pv )
          CoTaskMemFree(pv);
        return v87;
      }
    }
    else
    {
      *(_QWORD *)v69 = *(_QWORD *)v68;
      *(_QWORD *)v68 = 0;
      *(_QWORD *)(v69 + 8) = *(_QWORD *)(v68 + 8);
      *(_QWORD *)(v68 + 8) = 0;
      *(_QWORD *)(v69 + 16) = *(_QWORD *)(v68 + 16);
      *(_QWORD *)(v68 + 16) = 0;
      *(_QWORD *)(v69 + 24) = *(_QWORD *)(v68 + 24);
      *(_QWORD *)(v68 + 24) = 0;
      *(_DWORD *)(v69 + 32) = *(_DWORD *)(v68 + 32);
      a1[23] += 40LL;
    }
    StoredMessage::~StoredMessage((StoredMessage *)&hstringHeader);
    WindowsDeleteString(v81);
    v63 = v86;
  }
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(&v82);
  v71 = *((_QWORD *)&v91 + 1);
  v72 = v63 == 0;
  v73 = v91;
  if ( !v72 )
  {
    v74 = (HSTRING)v91;
    v81 = (HSTRING)v91;
    if ( (_QWORD)v91 != *((_QWORD *)&v91 + 1) )
    {
      do
      {
        v75 = *(_QWORD *)v74;
        v76 = *(void (__fastcall **)(__int64, _QWORD, HSTRING, __int64, __int64, unsigned int))(**(_QWORD **)v74 + 48LL);
        v77 = string;
        v78 = (_QWORD *)SttExperienceManager::CreateHString(v74, &v82, v64);
        v76(v75, *v78, v77, v94, v93, v87);
        WindowsDeleteString(v82);
        v82 = 0;
        v74 = v81 + 2;
        v81 = v74;
        v71 = *((_QWORD *)&v91 + 1);
      }
      while ( v74 != *((HSTRING *)&v91 + 1) );
      v73 = v91;
    }
  }
  if ( v73 )
  {
    std::_Destroy_range<std::allocator<Microsoft::WRL::ComPtr<SttInternal::IInternalMessageReceivedListener>>>(v73, v71);
    std::_Deallocate<16>(v73, (v59 - v73) & 0xFFFFFFFFFFFFFFF8uLL);
  }
  WindowsDeleteString(string);
  string = 0;
  if ( v35 )
    CoTaskMemFree(v35);
  if ( v64 )
    CoTaskMemFree(v64);
  return 0;
}

```

## disassembly

```asm
0x180337e50  push    rbx
0x180337e52  push    rsi
0x180337e53  push    rdi
0x180337e54  push    r12
0x180337e56  push    r13
0x180337e58  push    r14
0x180337e5a  push    r15
0x180337e5c  sub     rsp, 0F0h
0x180337e63  mov     rax, cs:__security_cookie
0x180337e6a  xor     rax, rsp
0x180337e6d  mov     [rsp+128h+var_48], rax
0x180337e75  mov     [rsp+128h+var_B4], r9d
0x180337e7a  mov     [rsp+128h+var_80], r8
0x180337e82  mov     [rsp+128h+var_78], rdx
0x180337e8a  mov     r15, rcx
0x180337e8d  xor     r12d, r12d
0x180337e90  movzx   esi, r12b
0x180337e94  lea     r14, [rcx+0C8h]
0x180337e9b  mov     rdx, r14
0x180337e9e  lea     rcx, [rsp+128h+var_E0]
0x180337ea3  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x180337ea8  nop
0x180337ea9  lea     rcx, [r15-80h]; this
0x180337ead  call    ?ResetHideAndCloseTimers@SttExperienceManager@@AEAAXXZ; SttExperienceManager::ResetHideAndCloseTimers(void)
0x180337eb2  mov     rcx, [r15+40h]
0x180337eb6  test    rcx, rcx
0x180337eb9  jnz     loc_18033808C
0x180337ebf  mov     [rsp+128h+var_C0], r12
0x180337ec4  lea     rdx, ?RuntimeClass_Windows_System_Launcher@@3QBGB; "Windows.System.Launcher"
0x180337ecb  lea     rcx, [rsp+128h+hstringHeader]; string
0x180337ed3  call    ??$?0$0BI@@StringReference@Internal@Windows@@QEAA@AEAY0BI@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[24])
0x180337ed8  lea     rdx, [rsp+128h+var_C0]
0x180337edd  mov     rcx, [rax]
0x180337ee0  call    ??$GetActivationFactory@V?$ComPtr@UILauncherStatics2@System@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UILauncherStatics2@System@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::System::ILauncherStatics2>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::System::ILauncherStatics2>>)
0x180337ee5  mov     ebx, eax
0x180337ee7  test    eax, eax
0x180337ee9  jns     short loc_180337F0C
0x180337eeb  mov     rcx, [rsp+128h]; this
0x180337ef3  mov     r9d, eax; char *
0x180337ef6  lea     r8, aShellTwinuiStt; "shell\\twinui\\sttexperiencemanager\\li"...
0x180337efd  mov     edx, 276h; void *
0x180337f02  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180337f07  jmp     loc_180337FF6
0x180337f0c  mov     [rsp+128h+var_D0], r12
0x180337f11  mov     rdi, [rsp+128h+var_C0]
0x180337f16  mov     rax, [rdi]
0x180337f19  mov     rbx, [rax+68h]
0x180337f1d  lea     rcx, [rsp+128h+var_D0]
0x180337f22  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180337f27  lea     rdx, ?c_AppProtocol@@3PEBGEB; ushort const * const c_AppProtocol
0x180337f2e  lea     rcx, [rsp+128h+hstringHeader]
0x180337f36  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180337f3b  nop
0x180337f3c  lea     r8, [rsp+128h+var_D0]
0x180337f41  mov     rdx, [rax+18h]
0x180337f45  mov     rcx, rdi
0x180337f48  mov     rax, rbx
0x180337f4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180337f50  mov     ebx, eax
0x180337f52  test    eax, eax
0x180337f54  jns     short loc_180337F74
0x180337f56  mov     rcx, [rsp+128h]; this
0x180337f5e  mov     r9d, eax; char *
0x180337f61  lea     r8, aShellTwinuiStt; "shell\\twinui\\sttexperiencemanager\\li"...
0x180337f68  mov     edx, 278h; void *
0x180337f6d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180337f72  jmp     short loc_180337FEB
0x180337f74  mov     [rsp+128h+var_D8], r12
0x180337f79  mov     rbx, [rsp+128h+var_D0]
0x180337f7e  lea     rcx, [rsp+128h+var_D8]
0x180337f83  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180337f88  lea     rdx, [rsp+128h+var_D8]
0x180337f8d  mov     rcx, rbx
0x180337f90  call    ??$BlockOnCompletionAndGetResults@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVAppInfo@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAU?$IVectorView@PEAVAppInfo@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@23@PEAU?$IVectorView@PEAVAppInfo@ApplicationModel@Windows@@@Collections@23@@@YAJPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVAppInfo@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@PEAPEAU?$IVectorView@PEAVAppInfo@ApplicationModel@Windows@@@Collections@12@W4tagCOWAIT_FLAGS@@PEAX@Z; BlockOnCompletionAndGetResults<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::AppInfo *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::AppInfo *> *>,Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::AppInfo *> *>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::AppInfo *> *> *,Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::AppInfo *> * *,tagCOWAIT_FLAGS,void *)
0x180337f95  mov     ebx, eax
0x180337f97  test    eax, eax
0x180337f99  jns     short loc_180337FA2
0x180337f9b  mov     edx, 27Ah
0x180337fa0  jmp     short loc_180337FC8
0x180337fa2  mov     dword ptr [rsp+128h+pv], r12d
0x180337fa7  mov     rcx, [rsp+128h+var_D8]
0x180337fac  mov     rax, [rcx]
0x180337faf  lea     rdx, [rsp+128h+pv]
0x180337fb4  mov     rax, [rax+38h]
0x180337fb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180337fbd  mov     ebx, eax
0x180337fbf  test    eax, eax
0x180337fc1  jns     short loc_180338005
0x180337fc3  mov     edx, 27Dh; void *
0x180337fc8  mov     r9d, eax; char *
0x180337fcb  lea     r8, aShellTwinuiStt; "shell\\twinui\\sttexperiencemanager\\li"...
0x180337fd2  mov     rcx, [rsp+128h]; this
0x180337fda  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180337fdf  nop
0x180337fe0  lea     rcx, [rsp+128h+var_D8]
0x180337fe5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180337fea  nop
0x180337feb  lea     rcx, [rsp+128h+var_D0]
0x180337ff0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180337ff5  nop
0x180337ff6  lea     rcx, [rsp+128h+var_C0]
0x180337ffb  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180338000  jmp     loc_1803380C6
0x180338005  mov     ebx, 1
0x18033800a  cmp     dword ptr [rsp+128h+pv], r12d
0x18033800f  cmova   esi, ebx
0x180338012  lea     rcx, [rsp+128h+var_D8]
0x180338017  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18033801c  nop
0x18033801d  lea     rcx, [rsp+128h+var_D0]
0x180338022  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180338027  nop
0x180338028  lea     rcx, [rsp+128h+var_C0]
0x18033802d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180338032  nop
0x180338033  lea     rcx, [rsp+128h+var_E0]
0x180338038  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(void)
0x18033803d  test    sil, sil
0x180338040  jz      loc_18033823D
0x180338046  mov     [rsp+128h+var_E0], r12
0x18033804b  lea     rcx, [rsp+128h+hstringHeader]; string
0x180338053  call    ??$?0$0BH@@StringReference@Internal@Windows@@QEAA@AEAY0BH@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[23])
0x180338058  lea     rdx, [rsp+128h+var_E0]
0x18033805d  mov     rcx, [rax]
0x180338060  call    ??$GetActivationFactory@V?$ComPtr@UIUriRuntimeClassFactory@Foundation@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIUriRuntimeClassFactory@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory>>)
0x180338065  mov     ebx, eax
0x180338067  test    eax, eax
0x180338069  jns     short loc_1803380D7
0x18033806b  mov     rcx, [rsp+128h]; this
0x180338073  mov     r9d, eax; char *
0x180338076  lea     r8, aShellTwinuiStt; "shell\\twinui\\sttexperiencemanager\\li"...
0x18033807d  mov     edx, 290h; void *
0x180338082  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180338087  jmp     loc_180338203
0x18033808c  mov     rax, [rcx]
0x18033808f  xor     edx, edx
0x180338091  mov     rax, [rax+28h]
0x180338095  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18033809a  lea     rcx, [r15-80h]; pv
0x18033809e  call    ?TriggerHideAndCloseTimers@SttExperienceManager@@AEAAJXZ; SttExperienceManager::TriggerHideAndCloseTimers(void)
0x1803380a3  mov     ebx, eax
0x1803380a5  test    eax, eax
0x1803380a7  jns     short loc_180338033
0x1803380a9  mov     rcx, [rsp+128h]; this
0x1803380b1  mov     r9d, eax; char *
0x1803380b4  lea     r8, aShellTwinuiStt; "shell\\twinui\\sttexperiencemanager\\li"...
0x1803380bb  mov     edx, 288h; void *
0x1803380c0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1803380c5  nop
0x1803380c6  lea     rcx, [rsp+128h+var_E0]
0x1803380cb  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(void)
0x1803380d0  mov     eax, ebx
0x1803380d2  jmp     loc_1803389E1
0x1803380d7  mov     [rsp+128h+var_D0], r12
0x1803380dc  mov     rdi, [rsp+128h+var_E0]
0x1803380e1  mov     rax, [rdi]
0x1803380e4  mov     rbx, [rax+30h]
0x1803380e8  lea     rcx, [rsp+128h+var_D0]
0x1803380ed  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1803380f2  mov     rdx, cs:?c_AppProtocolUri@@3PEBGEB; unsigned __int16 *
0x1803380f9  lea     rcx, [rsp+128h+hstringHeader]; this
0x180338101  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x180338106  lea     r8, [rsp+128h+var_D0]
0x18033810b  mov     rdx, qword ptr [rsp+128h+hstringHeader.Reserved]
0x180338113  mov     rcx, rdi
0x180338116  mov     rax, rbx
0x180338119  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18033811e  mov     ebx, eax
0x180338120  test    eax, eax
0x180338122  jns     short loc_180338145
0x180338124  mov     rcx, [rsp+128h]; this
0x18033812c  mov     r9d, eax; char *
0x18033812f  lea     r8, aShellTwinuiStt; "shell\\twinui\\sttexperiencemanager\\li"...
0x180338136  mov     edx, 293h; void *
0x18033813b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180338140  jmp     loc_1803381F8
0x180338145  mov     [rsp+128h+var_C0], r12
0x18033814a  lea     rdx, ?RuntimeClass_Windows_System_Launcher@@3QBGB; "Windows.System.Launcher"
0x180338151  lea     rcx, [rsp+128h+hstringHeader]; string
0x180338159  call    ??$?0$0BI@@StringReference@Internal@Windows@@QEAA@AEAY0BI@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[24])
0x18033815e  lea     rdx, [rsp+128h+var_C0]
0x180338163  mov     rcx, [rax]
0x180338166  call    ??$GetActivationFactory@V?$ComPtr@UILauncherStatics@System@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UILauncherStatics@System@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::System::ILauncherStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::System::ILauncherStatics>>)
0x18033816b  mov     ebx, eax
0x18033816d  test    eax, eax
0x18033816f  jns     short loc_18033818F
0x180338171  mov     rcx, [rsp+128h]; this
0x180338179  mov     r9d, eax; char *
0x18033817c  lea     r8, aShellTwinuiStt; "shell\\twinui\\sttexperiencemanager\\li"...
0x180338183  mov     edx, 296h; void *
0x180338188  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18033818d  jmp     short loc_1803381ED
0x18033818f  mov     [rsp+128h+var_D8], r12
0x180338194  mov     rdi, [rsp+128h+var_C0]
0x180338199  mov     rax, [rdi]
0x18033819c  mov     rbx, [rax+40h]
0x1803381a0  lea     rcx, [rsp+128h+var_D8]
0x1803381a5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1803381aa  lea     r8, [rsp+128h+var_D8]
0x1803381af  mov     rdx, [rsp+128h+var_D0]
0x1803381b4  mov     rcx, rdi
0x1803381b7  mov     rax, rbx
0x1803381ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803381bf  mov     ebx, eax
0x1803381c1  test    eax, eax
0x1803381c3  jns     short loc_180338212
0x1803381c5  mov     rcx, [rsp+128h]; this
0x1803381cd  mov     r9d, eax; char *
0x1803381d0  lea     r8, aShellTwinuiStt; "shell\\twinui\\sttexperiencemanager\\li"...
0x1803381d7  mov     edx, 299h; void *
0x1803381dc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1803381e1  nop
0x1803381e2  lea     rcx, [rsp+128h+var_D8]
0x1803381e7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1803381ec  nop
0x1803381ed  lea     rcx, [rsp+128h+var_C0]
0x1803381f2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1803381f7  nop
0x1803381f8  lea     rcx, [rsp+128h+var_D0]
0x1803381fd  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x180338202  nop
0x180338203  lea     rcx, [rsp+128h+var_E0]
0x180338208  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18033820d  jmp     loc_1803380D0
0x180338212  lea     rcx, [rsp+128h+var_D8]
0x180338217  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18033821c  nop
0x18033821d  lea     rcx, [rsp+128h+var_C0]
0x180338222  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180338227  nop
0x180338228  lea     rcx, [rsp+128h+var_D0]
0x18033822d  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x180338232  nop
0x180338233  lea     rcx, [rsp+128h+var_E0]
0x180338238  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18033823d  mov     [rsp+128h+pv], r12
0x180338242  xor     edx, edx
0x180338244  lea     rcx, [rsp+128h+pv]
0x180338249  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18033824e  lea     rcx, [rsp+128h+pv]; this
0x180338253  call    ?GetCallingProcessPackageFamilyName@CallerIdentity@@YAJPEAPEAG@Z; CallerIdentity::GetCallingProcessPackageFamilyName(ushort * *)
0x180338258  mov     ebx, eax
0x18033825a  test    eax, eax
0x18033825c  jns     short loc_180338294
0x18033825e  mov     rcx, [rsp+128h]; this
0x180338266  mov     r9d, eax; char *
0x180338269  lea     r8, aShellTwinuiStt; "shell\\twinui\\sttexperiencemanager\\li"...
0x180338270  mov     edx, 29Eh; void *
0x180338275  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18033827a  nop
0x18033827b  mov     rcx, [rsp+128h+pv]; pv
0x180338280  test    rcx, rcx
0x180338283  jz      loc_1803380D0
0x180338289  call    cs:__imp_CoTaskMemFree
0x18033828f  jmp     loc_1803380D0
0x180338294  mov     [rsp+128h+var_C0], r12
0x180338299  xor     edx, edx
0x18033829b  lea     rcx, [rsp+128h+var_C0]
0x1803382a0  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1803382a5  lea     rcx, [rsp+128h+var_C0]; this
0x1803382aa  call    ?GetCallingProcessAppId@CallerIdentity@@YAJPEAPEAG@Z; CallerIdentity::GetCallingProcessAppId(ushort * *)
0x1803382af  mov     ebx, eax
0x1803382b1  test    eax, eax
0x1803382b3  jns     short loc_1803382E4
0x1803382b5  mov     rcx, [rsp+128h]; this
0x1803382bd  mov     r9d, eax; char *
0x1803382c0  lea     r8, aShellTwinuiStt; "shell\\twinui\\sttexperiencemanager\\li"...
0x1803382c7  mov     edx, 2A1h; void *
0x1803382cc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1803382d1  nop
0x1803382d2  mov     rcx, [rsp+128h+var_C0]; pv
0x1803382d7  test    rcx, rcx
0x1803382da  jz      short loc_18033827B
0x1803382dc  call    cs:__imp_CoTaskMemFree
0x1803382e2  jmp     short loc_18033827B
0x1803382e4  mov     [rsp+128h+string], r12
0x1803382e9  mov     rbx, [rsp+128h+var_C0]
0x1803382ee  test    rbx, rbx
0x1803382f1  jz      loc_180338713
0x1803382f7  mov     rdx, r14
0x1803382fa  lea     rcx, [rsp+128h+var_B0]
0x1803382ff  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x180338304  nop
0x180338305  lea     r14, [r15+60h]
0x180338309  cmp     [r14], r12
0x18033830c  jnz     loc_18033848E
0x180338312  mov     [rsp+128h+var_E0], r12
0x180338317  mov     [rsp+128h+var_58], r12
0x18033831f  mov     r9d, 34h ; '4'; unsigned int
0x180338325  lea     r8d, [r9+1]; unsigned int
0x180338329  lea     rdx, ?RuntimeClass_WindowsInternal_Shell_UnifiedTile_UnifiedTileManager@@3QBGB; "WindowsInternal.Shell.UnifiedTile.Unifi"...
0x180338330  lea     rcx, [rsp+128h+hstringHeader]; hstringHeader
0x180338338  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18033833d  lea     rdx, [rsp+128h+var_E0]
0x180338342  mov     rcx, [rsp+128h+var_58]
0x18033834a  call    ??$GetActivationFactory@V?$ComPtr@UIUnifiedTileManagerStatics@UnifiedTile@Shell@WindowsInternal@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIUnifiedTileManagerStatics@UnifiedTile@Shell@WindowsInternal@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::IUnifiedTileManagerStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::IUnifiedTileManagerStatics>>)
0x18033834f  mov     edi, eax
0x180338351  test    eax, eax
0x180338353  jns     short loc_1803383B9
0x180338355  mov     rcx, [rsp+128h]; this
  ... truncated ...
```
