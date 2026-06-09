# CApplicationManager::OnShellHookMessage(unsigned __int64,__int64)

- ea: `0x18002b250`
- end: `0x18002bd20`
- name: `?OnShellHookMessage@CApplicationManager@@UEAAJ_K_J@Z`
- size: `2768`
- prototype: `int(CApplicationManager *__hidden this, unsigned __int64, __int64)`
- caller_count: `2`
- callee_count: `30`
- tags: `file_ops, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18009f6f0`
- `0x1801cfb60`

## callees

- `0x1800134f8`
- `0x180029b80`
- `0x18002aec0`
- `0x18002b250`
- `0x18002bd28`
- `0x18002be00`
- `0x18002bff0`
- `0x18002d790`
- `0x180031200`
- `0x180031c70`
- `0x180033d10`
- `0x1800370fc`
- `0x18003922c`
- `0x180084d88`
- `0x1800fd230`
- `0x1800fd348`
- `0x1800fd810`
- `0x1800fd990`
- `0x18013a5d0`
- `0x18014bd50`
- `0x18017d2a0`
- `0x180197e4c`
- `0x1801b3330`
- `0x1801bfd44`
- `0x1801c23cc`
- `0x1802f61b4`
- `0x180356360`
- `0x180356760`
- `0x180373254`
- `0x1806fa010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18002b348`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18002b348`
- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x18002bb44`
- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x18002bb44`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002b4c4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002b662`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002b9b4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1806ed141`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002b4c4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002b662`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002b9b4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1806ed141`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002b62e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002b696`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002ba5f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1806ed161`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002b62e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002b696`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002ba5f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1806ed161`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002b744`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002b744`
- `api-ms-win-core-synch-l1-1-0!TryEnterCriticalSection` at `0x18002b36b`
- `api-ms-win-core-synch-l1-1-0!TryEnterCriticalSection` at `0x18002b36b`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x18002b2eb`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x18002b2eb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b736`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002bb61`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b736`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002bb61`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002b304`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002b304`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetPropW` at `0x18002b55c`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetPropW` at `0x18002b55c`
- `api-ms-win-rtcore-ntuser-shell-l1-1-0!GetShellWindow` at `0x18002b547`
- `api-ms-win-rtcore-ntuser-shell-l1-1-0!GetShellWindow` at `0x18002b547`
- `SHCORE!__imp_IsAppCompatModeEnabled` at `0x18002bb06`
- `SHCORE!__imp_IsAppCompatModeEnabled` at `0x18002bb06`

## string_xrefs

- `0x18002bb97`: `onecoreuap\internal\shell\inc\private\Cowthreadusedetection.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
__int64 __fastcall CApplicationManager::OnShellHookMessage(CApplicationManager *this, unsigned __int64 a2, HWND a3)
{
  HWND v3; // r14
  CApplicationManager *v5; // r12
  CApplicationManager *v6; // r13
  char *v7; // rsi
  int v8; // ebx
  int v9; // eax
  DWORD CurrentThreadId; // r14d
  HRESULT ApartmentType; // ebx
  unsigned __int64 v12; // rdi
  __int64 v13; // rcx
  unsigned __int8 (__fastcall *v14)(__int64, struct IObjectArray *); // rax
  struct IObjectArray *v15; // r15
  HWND v16; // r14
  unsigned int v17; // r12d
  __int64 *v18; // rcx
  __int64 v19; // rax
  char v20; // al
  int v21; // r14d
  struct IImmersiveMonitor *v22; // rdi
  struct IObjectArray *v23; // rdi
  unsigned __int64 v24; // r14
  unsigned __int64 v25; // r15
  struct IImmersiveApplication *v26; // rcx
  struct IObjectArray *v28; // rdi
  struct ISyncIAMEventHandler *v29; // rcx
  struct IObjectArray *v30; // rcx
  __int64 v31; // rcx
  RTL_SRWLOCK *v32; // r14
  char v33; // di
  unsigned int v34; // edx
  CApplicationManager *v35; // rsi
  APTTYPEQUALIFIER v36; // eax
  __int64 v37; // rdx
  void *v38; // rdi
  struct CDelayIAMOperations::COperation *v39; // r12
  int cchValue; // [rsp+20h] [rbp-E0h]
  APTTYPEQUALIFIER pAptQualifier[2]; // [rsp+50h] [rbp-B0h] BYREF
  APTTYPE pAptType; // [rsp+58h] [rbp-A8h] BYREF
  HWND v43; // [rsp+60h] [rbp-A0h] BYREF
  bool v44; // [rsp+68h] [rbp-98h] BYREF
  __int64 v45; // [rsp+70h] [rbp-90h] BYREF
  struct ISyncIAMEventHandler *v46; // [rsp+78h] [rbp-88h] BYREF
  struct IImmersiveApplication *v47; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int64 v48; // [rsp+88h] [rbp-78h] BYREF
  struct IObjectArray *v49; // [rsp+90h] [rbp-70h]
  unsigned int v50; // [rsp+98h] [rbp-68h]
  char v51; // [rsp+9Ch] [rbp-64h]
  char v52; // [rsp+9Dh] [rbp-63h]
  unsigned int v53; // [rsp+A0h] [rbp-60h]
  char v54; // [rsp+A4h] [rbp-5Ch]
  HWND hWnd[2]; // [rsp+A8h] [rbp-58h]
  struct IObjectArray *v56; // [rsp+B8h] [rbp-48h] BYREF
  unsigned __int64 v57; // [rsp+C0h] [rbp-40h]
  __int64 v58; // [rsp+C8h] [rbp-38h]
  __int64 v59; // [rsp+D0h] [rbp-30h]
  CApplicationManager *v60; // [rsp+D8h] [rbp-28h]
  char *v61; // [rsp+E0h] [rbp-20h]
  char *v62; // [rsp+E8h] [rbp-18h]
  HRESULT v63; // [rsp+F0h] [rbp-10h]
  void **v64; // [rsp+100h] [rbp+0h] BYREF
  int v65; // [rsp+108h] [rbp+8h] BYREF
  char v66; // [rsp+10Ch] [rbp+Ch]
  int v67; // [rsp+130h] [rbp+30h] BYREF
  const char *v68; // [rsp+138h] [rbp+38h]
  __int64 v69; // [rsp+140h] [rbp+40h]
  char v70; // [rsp+148h] [rbp+48h]
  int v71; // [rsp+150h] [rbp+50h]
  __int128 v72; // [rsp+158h] [rbp+58h]
  __int128 v73; // [rsp+168h] [rbp+68h]
  __int128 v74; // [rsp+178h] [rbp+78h]
  __int128 v75; // [rsp+188h] [rbp+88h]
  __int128 v76; // [rsp+198h] [rbp+98h]
  __int128 v77; // [rsp+1A8h] [rbp+A8h]
  __int128 v78; // [rsp+1B8h] [rbp+B8h]
  __int128 v79; // [rsp+1C8h] [rbp+C8h]
  __int128 v80; // [rsp+1D8h] [rbp+D8h]
  __int64 v81; // [rsp+1E8h] [rbp+E8h]
  __int128 v82; // [rsp+1F0h] [rbp+F0h]
  int v83; // [rsp+200h] [rbp+100h]
  __int64 v84; // [rsp+208h] [rbp+108h]
  int *v85; // [rsp+210h] [rbp+110h]
  void *Block; // [rsp+218h] [rbp+118h] BYREF
  _QWORD v87[3]; // [rsp+220h] [rbp+120h] BYREF
  int v88; // [rsp+238h] [rbp+138h]
  int *v89; // [rsp+240h] [rbp+140h]
  char v90; // [rsp+248h] [rbp+148h]
  WCHAR Filename[264]; // [rsp+250h] [rbp+150h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+4A8h] [rbp+3A8h]

  v3 = a3;
  v43 = a3;
  v5 = this;
  v60 = this;
  v6 = (CApplicationManager *)((char *)this - 160);
  v7 = (char *)this + 232;
  if ( this == (CApplicationManager *)160 )
    v7 = 0;
  v61 = v7;
  v62 = v7;
  v8 = *((_DWORD *)v7 + 11);
  if ( v8 == 2 )
    goto LABEL_6;
  v9 = `_ShouldCheckApartments'::`5'::s_tbEnforceForProcess;
  if ( `_ShouldCheckApartments'::`5'::s_tbEnforceForProcess )
    goto LABEL_5;
  if ( GetModuleFileNameW(0, Filename, 0x104u) )
  {
    if ( FindStringOrdinal(0x800000u, Filename, -1, L"\\EXPLORER.EXE", -1, 1) != -1 )
    {
      `_ShouldCheckApartments'::`5'::s_tbEnforceForProcess = 2;
      goto LABEL_17;
    }
    `_ShouldCheckApartments'::`5'::s_tbEnforceForProcess = 1;
  }
  else if ( `_ShouldCheckApartments'::`5'::s_tbEnforceForProcess != 1 )
  {
    goto LABEL_17;
  }
  if ( v8 == 1 )
  {
    if ( (unsigned int)IsAppCompatModeEnabled(16) )
    {
      `_ShouldCheckApartments'::`5'::s_tbEnforceForProcess = 2;
      goto LABEL_17;
    }
    v9 = `_ShouldCheckApartments'::`5'::s_tbEnforceForProcess;
LABEL_5:
    if ( v9 != 1 )
      goto LABEL_17;
  }
LABEL_6:
  if ( *((_DWORD *)v7 + 10) == -3 )
    goto LABEL_17;
  CurrentThreadId = 0;
  pAptType = APTTYPE_STA;
  pAptQualifier[0] = APTTYPEQUALIFIER_NONE;
  ApartmentType = CoGetApartmentType(&pAptType, pAptQualifier);
  if ( ApartmentType >= 0 )
  {
    switch ( pAptType )
    {
      case APTTYPE_MAINSTA:
      case APTTYPE_STA:
        CurrentThreadId = GetCurrentThreadId();
        goto LABEL_11;
      case APTTYPE_MTA:
LABEL_11:
        if ( CurrentThreadId != *((_DWORD *)v7 + 10) )
          ApartmentType = -2147417842;
        goto LABEL_13;
      case APTTYPE_NA:
        CurrentThreadId = -1;
        goto LABEL_11;
    }
  }
  if ( ApartmentType >= 0 )
    goto LABEL_11;
LABEL_13:
  if ( ApartmentType < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xC8,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\Cowthreadusedetection.h",
      (const char *)(unsigned int)ApartmentType,
      cchValue);
    v3 = v43;
    goto LABEL_19;
  }
  v3 = v43;
LABEL_17:
  ApartmentType = -2147417842;
  if ( TryEnterCriticalSection((LPCRITICAL_SECTION)v7) )
    ApartmentType = 0;
LABEL_19:
  v63 = ApartmentType;
  v48 = a2;
  v49 = (struct IObjectArray *)v3;
  v50 = 0;
  v52 = 0;
  v53 = 0;
  v54 = 0;
  *(_OWORD *)hWnd = 0;
  if ( a2 != 32 )
  {
    if ( a2 > 0x22 )
    {
      if ( a2 != 65533 )
      {
LABEL_64:
        v51 = 1;
        goto LABEL_21;
      }
    }
    else if ( a2 != 34 )
    {
      switch ( a2 )
      {
        case 0x11uLL:
        case 0x12uLL:
        case 0x13uLL:
        case 0x14uLL:
        case 0x1AuLL:
        case 0x1DuLL:
          break;
        default:
          goto LABEL_64;
      }
    }
  }
  v51 = 0;
LABEL_21:
  v47 = 0;
  v65 = 0;
  v66 = 0;
  v70 = 0;
  v67 = 0;
  v68 = "OnShellHookMessage";
  v69 = 0;
  v71 = 0;
  v82 = 0;
  v72 = 0;
  v73 = 0;
  v74 = 0;
  v75 = 0;
  v76 = 0;
  v77 = 0;
  v78 = 0;
  v79 = 0;
  v80 = 0;
  v81 = 0;
  v83 = 1;
  v84 = 0;
  v85 = &v65;
  Block = 0;
  v87[0] = 0;
  v87[1] = &v64;
  v87[2] = 0;
  v88 = 0;
  v89 = &v67;
  v90 = 0;
  v64 = &IamTraceLogging::OnShellHookMessage::`vftable';
  IamTraceLogging::OnShellHookMessage::StartActivity((IamTraceLogging::OnShellHookMessage *)&v64, a2, v3);
  if ( a2 - 65534 > 1
    && CApplicationManager::_AnalyzeShellNotification(v6, (struct CApplicationManager::HSHELL_DATA *)&v48) )
  {
    AcquireSRWLockExclusive(CApplicationManagerUtility::g_pIAMGlobals);
    v12 = v48;
    switch ( v48 )
    {
      case 0x15uLL:
        if ( v50 - 2 > 1 )
          goto LABEL_29;
        CApplicationManager::_HandleImmersiveOwnedWindowVisibilityChange(
          v6,
          (const struct CApplicationManager::HSHELL_DATA *const)&v48,
          v3);
        break;
      case 0x12uLL:
        v13 = *((_QWORD *)v5 + 47);
        v14 = *(unsigned __int8 (__fastcall **)(__int64, struct IObjectArray *))(*(_QWORD *)v13 + 72LL);
LABEL_66:
        v28 = v49;
        if ( !v14(v13, v49) )
          (*(void (__fastcall **)(_QWORD, struct IObjectArray *))(**((_QWORD **)v5 + 54) + 32LL))(
            *((_QWORD *)v5 + 54),
            v28);
        break;
      case 0x18uLL:
LABEL_29:
        v15 = v49;
        v16 = (HWND)v49;
        if ( hWnd[1] )
          v16 = hWnd[1];
        v17 = v53;
        *(_QWORD *)pAptQualifier = 0;
        if ( GetShellWindow() != v16
          && !(unsigned int)GetPropW(v16, L"MultimonitorActivationException")
          && (HWND)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v6 + 94) + 24LL))(*((_QWORD *)v6 + 94)) != v16 )
        {
          (*(void (__fastcall **)(_QWORD, HWND, GUID *, GUID *, APTTYPEQUALIFIER *))(**((_QWORD **)v6 + 70) + 88LL))(
            *((_QWORD *)v6 + 70),
            v16,
            &GUID_880b26f8_9197_43d0_8045_8702d0d72000,
            &GUID_880b26f8_9197_43d0_8045_8702d0d72000,
            pAptQualifier);
        }
        v18 = (__int64 *)*((_QWORD *)v6 + 67);
        v19 = *v18;
        if ( v12 == 21 )
        {
          v20 = (*(__int64 (__fastcall **)(__int64 *, struct IObjectArray *, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD, _QWORD))(v19 + 24))(
                  v18,
                  v15,
                  v17,
                  0,
                  *(_QWORD *)pAptQualifier,
                  0,
                  0,
                  0);
          v21 = 3;
        }
        else
        {
          v20 = (*(__int64 (__fastcall **)(__int64 *, struct IObjectArray *, _QWORD))(v19 + 32))(
                  v18,
                  v15,
                  *(_QWORD *)pAptQualifier);
          v21 = 2;
        }
        if ( v20 )
        {
          v22 = *(struct IImmersiveMonitor **)pAptQualifier;
          if ( !*(_QWORD *)pAptQualifier )
            goto LABEL_39;
          pAptType = APTTYPE_STA;
          (*(void (__fastcall **)(_QWORD, APTTYPE *))(**((_QWORD **)v6 + 70) + 32LL))(*((_QWORD *)v6 + 70), &pAptType);
          if ( (unsigned int)pAptType > APTTYPE_MTA
            && (*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)v6 + 66) + 56LL))(*((_QWORD *)v6 + 66)) == 1
            && (*(unsigned __int8 (__fastcall **)(_QWORD, struct IObjectArray *))(**((_QWORD **)v6 + 67) + 88LL))(
                 *((_QWORD *)v6 + 67),
                 v15) )
          {
            v56 = 0;
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v56);
            if ( (int)CApplicationManager::_GetSingleMonitorObjectArray(v6, v22, &v56) >= 0 )
            {
              v46 = 0;
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
              if ( (int)CApplicationManager::_GetGlobalSyncEventHandler(v6, &v46) >= 0 )
                (*(void (__fastcall **)(struct ISyncIAMEventHandler *, struct IObjectArray *, char *, _QWORD, int, int, int))(*(_QWORD *)v46 + 24LL))(
                  v46,
                  v56,
                  (char *)v6 + 248,
                  0,
                  1,
                  v21,
                  0xFFFF);
              v29 = v46;
              if ( v46 )
              {
                v46 = 0;
                (*(void (__fastcall **)(struct ISyncIAMEventHandler *))(*(_QWORD *)v29 + 16LL))(v29);
              }
            }
            v30 = v56;
            if ( v56 )
            {
              v56 = 0;
              ((void (__fastcall *)(struct IObjectArray *))v30->lpVtbl->Release)(v30);
            }
          }
        }
        v22 = *(struct IImmersiveMonitor **)pAptQualifier;
LABEL_39:
        if ( v22 )
        {
          *(_QWORD *)pAptQualifier = 0;
          (*(void (__fastcall **)(struct IImmersiveMonitor *))(*(_QWORD *)v22 + 16LL))(v22);
        }
        v3 = v43;
        v5 = v60;
        break;
      default:
        switch ( v48 )
        {
          case 0x11uLL:
            CApplicationManager::_HandleWindowCreation(v6, (const struct CApplicationManager::HSHELL_DATA *const)&v48);
            break;
          case 0x13uLL:
          case 0x17uLL:
            v45 = 0;
            if ( v50 == 2 )
            {
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45);
              v56 = v49;
              LODWORD(v57) = 2;
              if ( (int)CApplicationManager::_FindFirstApplication<CImmersiveAppFinderByHwnd>(v6, &v56, &v45, &v43) >= 0 )
                CApplicationManager::_UpdatePerApplicationDataIfNeeded(v6, v45, v49, 0);
            }
            (*(void (__fastcall **)(_QWORD, struct IObjectArray *, _QWORD, __int64))(**((_QWORD **)v6 + 68) + 24LL))(
              *((_QWORD *)v6 + 68),
              v49,
              v50,
              v45);
            CApplicationManager::_HandleActivation2(v6, &v48, 1);
            v31 = v45;
            if ( v45 )
            {
              v45 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
            }
            break;
          case 0x14uLL:
            CApplicationManager::_HandleMonitorChanged(v6, (const struct CApplicationManager::HSHELL_DATA *const)&v48);
            break;
          case 0x16uLL:
            v13 = *((_QWORD *)v5 + 47);
            v14 = *(unsigned __int8 (__fastcall **)(__int64, struct IObjectArray *))(*(_QWORD *)v13 + 64LL);
            goto LABEL_66;
          case 0x19uLL:
          case 0x1CuLL:
            CApplicationManager::_HandleWindowBecameOwned(
              v6,
              v3,
              (const struct CApplicationManager::HSHELL_DATA *const)&v48);
            break;
          case 0x1AuLL:
          case 0x1DuLL:
            CApplicationManager::_HandleWindowBecameUnowned(
              v6,
              (const struct CApplicationManager::HSHELL_DATA *const)&v48);
            break;
          case 0x1BuLL:
          case 0x1EuLL:
            CApplicationManager::_HandleWindowChangedOwner(
              v6,
              (const struct CApplicationManager::HSHELL_DATA *const)&v48,
              v3);
            break;
          case 0x20uLL:
            v43 = 0;
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43);
            v56 = v49;
            LODWORD(v57) = 2;
            if ( (int)CApplicationManager::_FindFirstApplication<CImmersiveAppFinderByHwnd>(v6, &v56, &v43, 0) >= 0 )
            {
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v47);
              (**(void (__fastcall ***)(HWND, GUID *, struct IImmersiveApplication **))v43)(
                v43,
                &GUID_8b14e88b_5663_4caf_b196_c31479262831,
                &v47);
            }
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43);
            break;
          case 0x22uLL:
            if ( v50 == 2 )
              CApplicationManager::_HandleApplicationRequestActivation(
                v6,
                (const struct CApplicationManager::HSHELL_DATA *const)&v48);
            break;
          default:
            goto LABEL_42;
        }
        break;
    }
LABEL_42:
    ReleaseSRWLockExclusive(CApplicationManagerUtility::g_pIAMGlobals);
  }
  if ( v48 == 32 )
  {
    CApplicationManager::_HandleCloseRequested(v6, (const struct CApplicationManager::HSHELL_DATA *)&v48, v47);
  }
  else
  {
    if ( v48 == 65534 )
    {
      v34 = 1026;
    }
    else
    {
      if ( v48 != 0xFFFF )
        goto LABEL_46;
      v34 = 1025;
    }
    CApplicationManager::OnMessage((CApplicationManager *)((char *)v5 + 40), v34, 0, (__int64)v3, &v44);
  }
LABEL_46:
  AcquireSRWLockExclusive(CApplicationManagerUtility::g_pIAMGlobals);
  v23 = 0;
  v56 = 0;
  v57 = 0;
  v58 = 0;
  v59 = 0;
  v24 = *((_QWORD *)v5 + 102);
  if ( v24 )
  {
    v23 = (struct IObjectArray *)*((_QWORD *)v5 + 101);
    v56 = v23;
    v58 = *((_QWORD *)v5 + 103);
    v57 = v24;
    v59 = *((_QWORD *)v5 + 104);
    *((_QWORD *)v5 + 101) = 0;
    *((_QWORD *)v5 + 103) = 0;
    *((_QWORD *)v5 + 102) = 0;
    *((_QWORD *)v5 + 104) = 0;
  }
  ReleaseSRWLockExclusive(CApplicationManagerUtility::g_pIAMGlobals);
  v25 = 0;
  if ( v24 )
  {
    v35 = v60;
    do
    {
      AcquireSRWLockExclusive(CApplicationManagerUtility::g_pIAMGlobals);
      v39 = CDelayIAMOperations::RemoveOperation(*((CDelayIAMOperations **)v35 + 80), *((_DWORD *)&v23->lpVtbl + v25));
      ReleaseSRWLockExclusive(CApplicationManagerUtility::g_pIAMGlobals);
      if ( v39 )
      {
        (*(void (__fastcall **)(struct CDelayIAMOperations::COperation *))(*(_QWORD *)v39 + 8LL))(v39);
        (**(void (__fastcall ***)(struct CDelayIAMOperations::COperation *, __int64))v39)(v39, 1);
      }
      ++v25;
    }
    while ( v25 < v24 );
    v7 = v61;
  }
  if ( v23 )
    CoTaskMemFree(v23);
  wil::ActivityBase<CAppManagerLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(&v64, 0);
  v64 = &IamTraceLogging::OnShellHookMessage::`vftable';
  if ( !Block )
    goto LABEL_52;
  v32 = (RTL_SRWLOCK *)((char *)Block + 264);
  AcquireSRWLockExclusive((PSRWLOCK)Block + 33);
  if ( Block && *(_DWORD *)Block == 1 )
  {
    v33 = 1;
  }
  else
  {
    v33 = 0;
    wil::details::shared_object<wil::ActivityBase<CAppManagerLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<CAppManagerLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(&Block);
  }
  if ( v32 )
    ReleaseSRWLockExclusive(v32);
  if ( v33 )
  {
LABEL_52:
    if ( *v85 == 1 )
    {
      v36 = v85[22];
      pAptQualifier[0] = v36;
      v37 = 2147942974LL;
      if ( v36 < APTTYPEQUALIFIER_NONE )
        v37 = (unsigned int)v36;
      wil::ActivityBase<CAppManagerLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<CAppManagerLogging,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(
        v85,
        v37,
        pAptQualifier);
      wil::ActivityBase<CortanaProactiveLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(&v64);
    }
  }
  if ( v88 )
    wil::details::ThreadFailureCallbackHolder::StopWatching((wil::details::ThreadFailureCallbackHolder *)v87);
  if ( Block )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)Block, 0xFFFFFFFF) == 1 )
    {
      v38 = Block;
      if ( Block )
      {
        wil::ActivityBase<CAppManagerLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<CAppManagerLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<CAppManagerLogging,_TlgReflectorTag_Param0IsProviderType>((char *)Block + 8);
        operator delete(v38);
      }
    }
    Block = 0;
  }
  wil::ActivityBase<CAppManagerLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<CAppManagerLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<CAppManagerLogging,_TlgReflectorTag_Param0IsProviderType>(&v65);
  v26 = v47;
  if ( v47 )
  {
    v47 = 0;
    (*(void (__fastcall **)(struct IImmersiveApplication *))(*(_QWORD *)v26 + 16LL))(v26);
  }
  CoTaskMemFree(hWnd[0]);
  if ( ApartmentType >= 0 )
    LeaveCriticalSection((LPCRITICAL_SECTION)v7);
  return 0;
}

```

## disassembly

```asm
0x18002b250  mov     [rsp-8+arg_8], rbx
0x18002b255  push    rbp
0x18002b256  push    rsi
0x18002b257  push    rdi
0x18002b258  push    r12
0x18002b25a  push    r13
0x18002b25c  push    r14
0x18002b25e  push    r15
0x18002b260  lea     rbp, [rsp-370h]
0x18002b268  sub     rsp, 470h
0x18002b26f  mov     rax, cs:__security_cookie
0x18002b276  xor     rax, rsp
0x18002b279  mov     [rbp+3A0h+var_40], rax
0x18002b280  mov     r14, r8
0x18002b283  mov     [rsp+4A0h+var_440], r8
0x18002b288  mov     r15, rdx
0x18002b28b  mov     r12, rcx
0x18002b28e  mov     [rbp+3A0h+var_3C8], rcx
0x18002b292  xor     edi, edi
0x18002b294  lea     r13, [rcx-0A0h]
0x18002b29b  lea     rsi, [rcx+0E8h]
0x18002b2a2  test    r13, r13
0x18002b2a5  cmovz   rsi, rdi
0x18002b2a9  mov     [rbp+3A0h+var_3C0], rsi
0x18002b2ad  mov     [rbp+3A0h+var_3B8], rsi
0x18002b2b1  mov     ebx, [rsi+2Ch]
0x18002b2b4  cmp     ebx, 2
0x18002b2b7  jz      short loc_18002B2CC
0x18002b2b9  mov     eax, cs:?s_tbEnforceForProcess@?4??_ShouldCheckApartments@@YA_NW4ApartmentCheckEnum@@@Z@4W4TRIBIT@@A; TRIBIT `_ShouldCheckApartments(ApartmentCheckEnum)'::`5'::s_tbEnforceForProcess
0x18002b2bf  test    eax, eax
0x18002b2c1  jz      short loc_18002B339
0x18002b2c3  cmp     eax, 1
0x18002b2c6  jnz     loc_18002B363
0x18002b2cc  cmp     dword ptr [rsi+28h], 0FFFFFFFDh
0x18002b2d0  jz      loc_18002B363
0x18002b2d6  mov     r14d, edi
0x18002b2d9  mov     [rsp+4A0h+pAptType], edi
0x18002b2dd  mov     [rsp+4A0h+pAptQualifier], edi
0x18002b2e1  lea     rdx, [rsp+4A0h+pAptQualifier]; pAptQualifier
0x18002b2e6  lea     rcx, [rsp+4A0h+pAptType]; pAptType
0x18002b2eb  call    cs:__imp_CoGetApartmentType
0x18002b2f1  mov     ebx, eax
0x18002b2f3  test    eax, eax
0x18002b2f5  js      short loc_18002B30F
0x18002b2f7  mov     ecx, [rsp+4A0h+pAptType]
0x18002b2fb  cmp     ecx, 3
0x18002b2fe  jnz     loc_18002BBB2
0x18002b304  call    cs:__imp_GetCurrentThreadId
0x18002b30a  mov     r14d, eax
0x18002b30d  jmp     short loc_18002B317
0x18002b30f  test    ebx, ebx
0x18002b311  js      loc_18002BBD7
0x18002b317  mov     edi, 8001010Eh
0x18002b31c  cmp     r14d, [rsi+28h]
0x18002b320  cmovnz  ebx, edi
0x18002b323  mov     rcx, [rbp+3A8h]; this
0x18002b32a  test    ebx, ebx
0x18002b32c  js      loc_18002BB94
0x18002b332  mov     r14, [rsp+4A0h+var_440]
0x18002b337  jmp     short loc_18002B368
0x18002b339  mov     r8d, 104h; nSize
0x18002b33f  lea     rdx, [rbp+3A0h+Filename]; lpFilename
0x18002b346  xor     ecx, ecx; hModule
0x18002b348  call    cs:__imp_GetModuleFileNameW
0x18002b34e  test    eax, eax
0x18002b350  jnz     loc_18002BB1B
0x18002b356  cmp     cs:?s_tbEnforceForProcess@?4??_ShouldCheckApartments@@YA_NW4ApartmentCheckEnum@@@Z@4W4TRIBIT@@A, 1; TRIBIT `_ShouldCheckApartments(ApartmentCheckEnum)'::`5'::s_tbEnforceForProcess
0x18002b35d  jz      loc_18002BAF8
0x18002b363  mov     edi, 8001010Eh
0x18002b368  mov     rcx, rsi; lpCriticalSection
0x18002b36b  call    cs:__imp_TryEnterCriticalSection
0x18002b371  mov     ebx, edi
0x18002b373  xor     ecx, ecx
0x18002b375  test    eax, eax
0x18002b377  cmovnz  ebx, ecx
0x18002b37a  mov     [rbp+3A0h+var_3B0], ebx
0x18002b37d  mov     [rbp+3A0h+var_418], r15
0x18002b381  mov     [rbp+3A0h+var_410], r14
0x18002b385  xor     ecx, ecx
0x18002b387  mov     [rbp+3A0h+var_408], ecx
0x18002b38a  mov     [rbp+3A0h+var_403], cl
0x18002b38d  mov     [rbp+3A0h+var_400], ecx
0x18002b390  mov     [rbp+3A0h+var_3FC], cl
0x18002b393  xorps   xmm0, xmm0
0x18002b396  movdqu  xmmword ptr [rbp+3A0h+hWnd], xmm0
0x18002b39b  lea     rdx, __ImageBase
0x18002b3a2  cmp     r15, 20h ; ' '
0x18002b3a6  jnz     loc_18002B776
0x18002b3ac  mov     [rbp+3A0h+var_404], cl; jumptable 00000001806ED0C8 cases 17-20,26,29
0x18002b3af  mov     [rbp+3A0h+var_420], rcx
0x18002b3b3  lea     rax, [r15-0FFFEh]
0x18002b3ba  cmp     rax, 1
0x18002b3be  ja      loc_18002BBE1
0x18002b3c4  mov     dil, 1
0x18002b3c7  mov     [rbp+3A0h+var_398], ecx
0x18002b3ca  mov     [rbp+3A0h+var_394], 0
0x18002b3ce  mov     [rbp+3A0h+var_358], 0
0x18002b3d2  mov     [rbp+3A0h+var_370], ecx
0x18002b3d5  lea     rax, aOnshellhookmes; "OnShellHookMessage"
0x18002b3dc  mov     [rbp+3A0h+var_368], rax
0x18002b3e0  mov     [rbp+3A0h+var_360], rcx
0x18002b3e4  mov     [rbp+3A0h+var_350], ecx
0x18002b3e7  movdqa  [rbp+3A0h+var_2B0], xmm0
0x18002b3ef  xorps   xmm1, xmm1
0x18002b3f2  xor     eax, eax
0x18002b3f4  movups  [rbp+3A0h+var_348], xmm1
0x18002b3f8  movups  [rbp+3A0h+var_338], xmm1
0x18002b3fc  movups  [rbp+3A0h+var_328], xmm1
0x18002b400  movups  [rbp+3A0h+var_318], xmm1
0x18002b407  movups  [rbp+3A0h+var_308], xmm1
0x18002b40e  movups  [rbp+3A0h+var_2F8], xmm1
0x18002b415  movups  [rbp+3A0h+var_2E8], xmm1
0x18002b41c  movups  [rbp+3A0h+var_2D8], xmm1
0x18002b423  movups  [rbp+3A0h+var_2C8], xmm1
0x18002b42a  mov     [rbp+3A0h+var_2B8], rax
0x18002b431  mov     [rbp+3A0h+var_2A0], 1
0x18002b43b  mov     [rbp+3A0h+var_298], rax
0x18002b442  lea     rax, [rbp+3A0h+var_398]
0x18002b446  mov     [rbp+3A0h+var_290], rax
0x18002b44d  mov     [rbp+3A0h+Block], rcx
0x18002b454  mov     [rbp+3A0h+var_280], rcx
0x18002b45b  lea     rax, [rbp+3A0h+var_3A0]
0x18002b45f  mov     [rbp+3A0h+var_278], rax
0x18002b466  mov     [rbp+3A0h+var_270], rcx
0x18002b46d  mov     [rbp+3A0h+var_268], ecx
0x18002b473  lea     rax, [rbp+3A0h+var_370]
0x18002b477  mov     [rbp+3A0h+var_260], rax
0x18002b47e  mov     [rbp+3A0h+var_258], 0
0x18002b485  lea     rax, ??_7OnShellHookMessage@IamTraceLogging@@6B@; const IamTraceLogging::OnShellHookMessage::`vftable'
0x18002b48c  mov     [rbp+3A0h+var_3A0], rax
0x18002b490  mov     r8, r14; HWND
0x18002b493  mov     rdx, r15; unsigned __int64
0x18002b496  lea     rcx, [rbp+3A0h+var_3A0]; this
0x18002b49a  call    ?StartActivity@OnShellHookMessage@IamTraceLogging@@QEAAX_KPEAUHWND__@@@Z; IamTraceLogging::OnShellHookMessage::StartActivity(unsigned __int64,HWND__ *)
0x18002b49f  nop
0x18002b4a0  test    dil, dil
0x18002b4a3  jnz     loc_18002B634
0x18002b4a9  lea     rdx, [rbp+3A0h+var_418]; struct CApplicationManager::HSHELL_DATA *
0x18002b4ad  mov     rcx, r13; this
0x18002b4b0  call    ?_AnalyzeShellNotification@CApplicationManager@@AEAA_NPEAUHSHELL_DATA@1@@Z; CApplicationManager::_AnalyzeShellNotification(CApplicationManager::HSHELL_DATA *)
0x18002b4b5  test    al, al
0x18002b4b7  jz      loc_18002B634
0x18002b4bd  mov     rcx, cs:?g_pIAMGlobals@CApplicationManagerUtility@@3PEAVCIAMGlobals@@EA; SRWLock
0x18002b4c4  call    cs:__imp_AcquireSRWLockExclusive
0x18002b4ca  mov     rdi, [rbp+3A0h+var_418]
0x18002b4ce  cmp     rdi, 15h
0x18002b4d2  jz      short loc_18002B519
0x18002b4d4  cmp     rdi, 12h
0x18002b4d8  jz      loc_18002B799
0x18002b4de  cmp     rdi, 18h
0x18002b4e2  jz      short loc_18002B528
0x18002b4e4  add     rdi, 0FFFFFFFFFFFFFFEFh; switch 18 cases
0x18002b4e8  cmp     rdi, 11h
0x18002b4ec  ja      def_18002B503; jumptable 000000018002B503 default case, cases 18,21,24,31,33
0x18002b4f2  lea     rcx, __ImageBase
0x18002b4f9  mov     eax, ds:(jpt_18002B503 - 180000000h)[rcx+rdi*4]
0x18002b500  add     rax, rcx
0x18002b503  jmp     rax; switch jump
0x18002b505  mov     rcx, [r12+178h]; jumptable 000000018002B503 case 22
0x18002b50d  mov     rax, [rcx]
0x18002b510  mov     rax, [rax+40h]
0x18002b514  jmp     loc_18002B7A8
0x18002b519  mov     eax, [rbp+3A0h+var_408]
0x18002b51c  add     eax, 0FFFFFFFEh
0x18002b51f  cmp     eax, 1
0x18002b522  jbe     loc_18002BB6C
0x18002b528  mov     r15, [rbp+3A0h+var_410]
0x18002b52c  mov     r14, r15
0x18002b52f  mov     rax, [rbp+3A0h+hWnd+8]
0x18002b533  test    rax, rax
0x18002b536  cmovnz  r14, rax
0x18002b53a  mov     r12d, [rbp+3A0h+var_400]
0x18002b53e  mov     qword ptr [rsp+4A0h+pAptQualifier], 0
0x18002b547  call    cs:__imp_GetShellWindow
0x18002b54d  cmp     rax, r14
0x18002b550  jz      short loc_18002B5AC
0x18002b552  lea     rdx, aMultimonitorac; "MultimonitorActivationException"
0x18002b559  mov     rcx, r14; hWnd
0x18002b55c  call    cs:__imp_GetPropW
0x18002b562  test    eax, eax
0x18002b564  jnz     short loc_18002B5AC
0x18002b566  mov     rcx, [r13+2F0h]
0x18002b56d  mov     rax, [rcx]
0x18002b570  mov     rax, [rax+18h]
0x18002b574  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b579  cmp     rax, r14
0x18002b57c  jz      short loc_18002B5AC
0x18002b57e  mov     rcx, [r13+230h]
0x18002b585  mov     rax, [rcx]
0x18002b588  lea     rdx, [rsp+4A0h+pAptQualifier]
0x18002b58d  mov     qword ptr [rsp+4A0h+cchValue], rdx
0x18002b592  lea     r9, _GUID_880b26f8_9197_43d0_8045_8702d0d72000
0x18002b599  lea     r8, _GUID_880b26f8_9197_43d0_8045_8702d0d72000
0x18002b5a0  mov     rdx, r14
0x18002b5a3  mov     rax, [rax+58h]
0x18002b5a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b5ac  mov     rcx, [r13+218h]
0x18002b5b3  mov     rax, [rcx]
0x18002b5b6  cmp     rdi, 15h
0x18002b5ba  jnz     loc_18002BA1E
0x18002b5c0  mov     rdx, qword ptr [rsp+4A0h+pAptQualifier]
0x18002b5c5  xor     r8d, r8d
0x18002b5c8  mov     [rsp+4A0h+var_468], r8
0x18002b5cd  mov     [rsp+4A0h+var_470], r8d
0x18002b5d2  mov     [rsp+4A0h+bIgnoreCase], r8d
0x18002b5d7  mov     qword ptr [rsp+4A0h+cchValue], rdx
0x18002b5dc  xor     r9d, r9d
0x18002b5df  mov     r8d, r12d
0x18002b5e2  mov     rdx, r15
0x18002b5e5  mov     rax, [rax+18h]
0x18002b5e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b5ee  mov     r14d, 3
0x18002b5f4  test    al, al
0x18002b5f6  jnz     loc_18002B7E6
0x18002b5fc  mov     rdi, qword ptr [rsp+4A0h+pAptQualifier]
0x18002b601  test    rdi, rdi
0x18002b604  jz      short loc_18002B61E
0x18002b606  mov     qword ptr [rsp+4A0h+pAptQualifier], 0
0x18002b60f  mov     rax, [rdi]
0x18002b612  mov     rcx, rdi
0x18002b615  mov     rax, [rax+10h]
0x18002b619  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b61e  mov     r14, [rsp+4A0h+var_440]
0x18002b623  mov     r12, [rbp+3A0h+var_3C8]
0x18002b627  mov     rcx, cs:?g_pIAMGlobals@CApplicationManagerUtility@@3PEAVCIAMGlobals@@EA; jumptable 000000018002B503 default case, cases 18,21,24,31,33
0x18002b62e  call    cs:__imp_ReleaseSRWLockExclusive
0x18002b634  mov     rcx, [rbp+3A0h+var_418]
0x18002b638  mov     rax, rcx
0x18002b63b  sub     rax, 20h ; ' '
0x18002b63f  jz      loc_18002BC18
0x18002b645  sub     rax, 0FFDEh
0x18002b64b  jz      loc_18002B9F1
0x18002b651  cmp     rax, 1
0x18002b655  jz      loc_18002B9FA
0x18002b65b  mov     rcx, cs:?g_pIAMGlobals@CApplicationManagerUtility@@3PEAVCIAMGlobals@@EA; SRWLock
0x18002b662  call    cs:__imp_AcquireSRWLockExclusive
0x18002b668  xor     r13d, r13d
0x18002b66b  mov     edi, r13d
0x18002b66e  mov     [rbp+3A0h+var_3E8], r13
0x18002b672  mov     [rbp+3A0h+var_3E0], r13
0x18002b676  mov     [rbp+3A0h+var_3D8], r13
0x18002b67a  mov     [rbp+3A0h+var_3D0], r13
0x18002b67e  mov     r14, [r12+330h]
0x18002b686  test    r14, r14
0x18002b689  jnz     loc_18002BC2D
0x18002b68f  mov     rcx, cs:?g_pIAMGlobals@CApplicationManagerUtility@@3PEAVCIAMGlobals@@EA; SRWLock
0x18002b696  call    cs:__imp_ReleaseSRWLockExclusive
0x18002b69c  mov     r15, r13
0x18002b69f  test    r14, r14
0x18002b6a2  jnz     loc_18002BC7A
0x18002b6a8  test    rdi, rdi
0x18002b6ab  jnz     loc_18002BB5E
0x18002b6b1  xor     edx, edx
0x18002b6b3  lea     rcx, [rbp+3A0h+var_3A0]
0x18002b6b7  call    ?Stop@?$ActivityBase@VCAppManagerLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<CAppManagerLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18002b6bc  nop
0x18002b6bd  lea     rax, ??_7OnShellHookMessage@IamTraceLogging@@6B@; const IamTraceLogging::OnShellHookMessage::`vftable'
0x18002b6c4  mov     [rbp+3A0h+var_3A0], rax
0x18002b6c8  mov     rdx, [rbp+3A0h+Block]
0x18002b6cf  test    rdx, rdx
0x18002b6d2  jnz     loc_18002B99F
0x18002b6d8  mov     rcx, [rbp+3A0h+var_290]
0x18002b6df  cmp     dword ptr [rcx], 1
0x18002b6e2  jz      loc_18002BC83
0x18002b6e8  cmp     [rbp+3A0h+var_268], 0
0x18002b6ef  jz      short loc_18002B6FE
0x18002b6f1  lea     rcx, [rbp+3A0h+var_280]; this
0x18002b6f8  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x18002b6fd  nop
0x18002b6fe  mov     rax, [rbp+3A0h+Block]
0x18002b705  test    rax, rax
0x18002b708  jnz     loc_18002B981
0x18002b70e  lea     rcx, [rbp+3A0h+var_398]
0x18002b712  call    ??1?$ActivityData@VCAppManagerLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VCAppManagerLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<CAppManagerLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<CAppManagerLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<CAppManagerLogging,_TlgReflectorTag_Param0IsProviderType>(void)
0x18002b717  nop
0x18002b718  mov     rcx, [rbp+3A0h+var_420]
0x18002b71c  test    rcx, rcx
0x18002b71f  jz      short loc_18002B732
0x18002b721  mov     [rbp+3A0h+var_420], r13
0x18002b725  mov     rax, [rcx]
0x18002b728  mov     rax, [rax+10h]
0x18002b72c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b731  nop
0x18002b732  mov     rcx, [rbp+3A0h+hWnd]; pv
0x18002b736  call    cs:__imp_CoTaskMemFree
0x18002b73c  nop
0x18002b73d  test    ebx, ebx
0x18002b73f  js      short loc_18002B74A
0x18002b741  mov     rcx, rsi; lpCriticalSection
0x18002b744  call    cs:__imp_LeaveCriticalSection
0x18002b74a  xor     eax, eax
0x18002b74c  mov     rcx, [rbp+3A0h+var_40]
0x18002b753  xor     rcx, rsp; StackCookie
0x18002b756  call    __security_check_cookie
0x18002b75b  mov     rbx, [rsp+4A0h+arg_8]
0x18002b763  add     rsp, 470h
0x18002b76a  pop     r15
0x18002b76c  pop     r14
0x18002b76e  pop     r13
0x18002b770  pop     r12
  ... truncated ...
```
