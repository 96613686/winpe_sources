# ClientProxyManager::InternalGetProxyProvider(ProviderEntryPoint *,long,long,UiaClientState *,int,int,int,int,IRawElementProviderSimple * *,IUiaNode * *,int *,ElementExtraInfo *,std::optional<ElementCompletionInfo> *)

- ea: `0x1800922e0`
- end: `0x180092d62`
- name: `?InternalGetProxyProvider@ClientProxyManager@@AEAAJPEAVProviderEntryPoint@@JJPEAVUiaClientState@@HHHHPEAPEAUIRawElementProviderSimple@@PEAPEAVIUiaNode@@PEAHPEAUElementExtraInfo@@PEAV?$optional@UElementCompletionInfo@@@std@@@Z`
- size: `2690`
- prototype: ``
- caller_count: `4`
- callee_count: `21`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18002bf40`
- `0x1800367c0`
- `0x180092184`
- `0x1800934cc`

## callees

- `0x18000a1a8`
- `0x18000f680`
- `0x18001c498`
- `0x18002f580`
- `0x18003c820`
- `0x18004cb90`
- `0x1800697bc`
- `0x1800922e0`
- `0x180092d68`
- `0x18009c800`
- `0x1800cc348`
- `0x1800d9490`
- `0x18010e230`
- `0x180181488`
- `0x1801975f4`
- `0x1801b02c4`
- `0x1801e8320`
- `0x1801e9258`
- `0x1801fc5d8`
- `0x1802bfde4`
- `0x1802dd010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800926dc`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800926dc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180092570`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180092570`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800926a8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800928c5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180092d3c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180092d56`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800926a8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800928c5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180092d3c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180092d56`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800926ca`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180092773`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800926ca`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180092773`
- `api-ms-win-core-string-l2-1-0!CharLowerW` at `0x18009262b`
- `api-ms-win-core-string-l2-1-0!CharLowerW` at `0x180092737`
- `api-ms-win-core-string-l2-1-0!CharLowerW` at `0x180092c1c`
- `api-ms-win-core-string-l2-1-0!CharLowerW` at `0x18009262b`
- `api-ms-win-core-string-l2-1-0!CharLowerW` at `0x180092737`
- `api-ms-win-core-string-l2-1-0!CharLowerW` at `0x180092c1c`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800925de`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180092668`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800925de`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180092668`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetWindowThreadProcessId` at `0x18009276a`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetWindowThreadProcessId` at `0x18009276a`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetClassNameW` at `0x180092720`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetClassNameW` at `0x180092720`
- `OLEAUT32!__imp_SysFreeString` at `0x1800924a2`
- `OLEAUT32!__imp_SysFreeString` at `0x1800924a2`

## string_xrefs

- `0x180092399`: `onecore\windows\accessibletech\uiautomationcore\clientproxymanager.cpp`
- `0x180092d27`: `onecore\windows\accessibletech\uiautomationcore\clientproxymanager.cpp`
- `0x18009297f`: `IUIAutomationProxyFactory::CreateProvider`
- `0x180092bb3`: `onecore\windows\accessibletech\uiautomationcore\hwndutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall ClientProxyManager::InternalGetProxyProvider(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        unsigned int a4,
        __int64 a5,
        int a6,
        int a7,
        int a8,
        int a9,
        _QWORD *a10,
        _QWORD *a11,
        int *a12,
        struct IUnknown **a13,
        __int64 a14)
{
  struct ProviderEntryPoint *v14; // r13
  __int64 v15; // rbx
  __int64 v17; // rcx
  int v18; // r9d
  int v19; // r8d
  int v20; // eax
  __int64 v21; // rcx
  int v22; // eax
  unsigned int v23; // r14d
  int v24; // r13d
  struct IUnknown **v25; // r14
  char v26; // r12
  struct _GUID v27; // xmm6
  int v28; // r15d
  int v29; // r14d
  __int64 *v30; // rsi
  struct _RTL_CRITICAL_SECTION *v31; // rdi
  int v32; // r8d
  int v33; // r14d
  const WCHAR *v34; // rbx
  __int64 (__fastcall *v35)(struct ProviderEntryPoint *, _QWORD, _QWORD, _DWORD *, PCNZWCH, __int64, _QWORD *, struct IUnknown **, __int64); // r12
  int v36; // r14d
  __int64 v37; // rbx
  _BYTE *v38; // r15
  char v39; // al
  DWORD WindowThreadProcessId; // r14d
  __int64 v41; // r14
  bool v42; // dl
  __int64 v43; // rax
  __int64 v44; // r14
  const unsigned __int16 *v45; // rcx
  __int64 *v46; // rdx
  _QWORD *v47; // rcx
  __int64 v48; // rcx
  unsigned int v49; // r15d
  unsigned int v50; // r14d
  unsigned int v51; // r12d
  int v52; // eax
  void (__fastcall ***v53)(_QWORD, GUID *, __int64 *); // rcx
  struct ProviderEntryPoint *v54; // rcx
  struct IRawElementProviderSimple **v55; // rsi
  void (__fastcall ***v56)(_QWORD, GUID *, __int64 *); // rcx
  __int64 v57; // rcx
  struct IRawElementProviderSimple *v58; // rcx
  __int64 v59; // rcx
  struct IRawElementProviderSimple *FocusedChild; // rdi
  int CrossMachineHwndClassName; // eax
  int BaseClassName; // eax
  unsigned int v63; // ebx
  PCNZWCH lpString2; // [rsp+20h] [rbp-E0h]
  int lpString2a; // [rsp+20h] [rbp-E0h]
  OLECHAR pbstr[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v67; // [rsp+58h] [rbp-A8h] BYREF
  int v68; // [rsp+60h] [rbp-A0h]
  __int16 v69; // [rsp+64h] [rbp-9Ch]
  struct ProviderEntryPoint *v70; // [rsp+68h] [rbp-98h] BYREF
  int v71; // [rsp+70h] [rbp-90h]
  int v72; // [rsp+74h] [rbp-8Ch]
  int v73; // [rsp+78h] [rbp-88h]
  unsigned int v74; // [rsp+7Ch] [rbp-84h]
  unsigned int v75; // [rsp+80h] [rbp-80h]
  int v76; // [rsp+84h] [rbp-7Ch]
  int v77; // [rsp+88h] [rbp-78h]
  HWND hWnd; // [rsp+90h] [rbp-70h]
  __int64 v79; // [rsp+98h] [rbp-68h]
  int v80; // [rsp+A0h] [rbp-60h]
  _QWORD *v81; // [rsp+A8h] [rbp-58h]
  __int64 v82; // [rsp+B0h] [rbp-50h]
  __int64 v83; // [rsp+B8h] [rbp-48h] BYREF
  _DWORD v84[4]; // [rsp+C0h] [rbp-40h] BYREF
  struct _RTL_CRITICAL_SECTION *v85; // [rsp+D0h] [rbp-30h]
  char v86[8]; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v87; // [rsp+E0h] [rbp-20h]
  int *v88; // [rsp+E8h] [rbp-18h]
  struct IUnknown **v89; // [rsp+F0h] [rbp-10h]
  struct _GUID v90; // [rsp+F8h] [rbp-8h] BYREF
  char v91; // [rsp+108h] [rbp+8h]
  __int16 v92; // [rsp+109h] [rbp+9h]
  char v93; // [rsp+10Bh] [rbp+Bh]
  struct IUnknown *v94; // [rsp+110h] [rbp+10h] BYREF
  char v95; // [rsp+118h] [rbp+18h]
  GUID v96; // [rsp+11Ch] [rbp+1Ch]
  BSTR bstrString; // [rsp+130h] [rbp+30h] BYREF
  __int64 v98; // [rsp+138h] [rbp+38h] BYREF
  __int128 v99; // [rsp+140h] [rbp+40h]
  struct IUnknown *v100; // [rsp+150h] [rbp+50h]
  __int64 v101; // [rsp+158h] [rbp+58h] BYREF
  char v102; // [rsp+160h] [rbp+60h]
  WCHAR String1[264]; // [rsp+170h] [rbp+70h] BYREF
  WCHAR Str[264]; // [rsp+380h] [rbp+280h] BYREF
  WCHAR sz[264]; // [rsp+590h] [rbp+490h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+808h] [rbp+708h]

  v74 = a4;
  v75 = a3;
  v14 = (struct ProviderEntryPoint *)a2;
  v70 = (struct ProviderEntryPoint *)a2;
  v15 = a1;
  v79 = a1;
  v87 = a14;
  v89 = a13;
  v82 = a5;
  v67 = (__int64)a10;
  v81 = a11;
  v88 = a12;
  *a10 = 0;
  if ( a6 )
  {
    *a11 = 0;
    *a12 = 0;
  }
  if ( *(_DWORD *)(a2 + 40) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x297,
      (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\clientproxymanager.cpp",
      (const char *)0x8000FFFFLL,
      (int)lpString2);
    return 2147549183LL;
  }
  v26 = *(_BYTE *)(a2 + 60);
  LOBYTE(pbstr[1]) = v26;
  hWnd = *(HWND *)(a2 + 24);
  v27 = *(struct _GUID *)(a2 + 44);
  v69 = *(_WORD *)(a2 + 61);
  HIBYTE(pbstr[0]) = *(_BYTE *)(a2 + 63);
  v28 = 0;
  v76 = 0;
  v72 = 0;
  memset_0(Str, 0, 0x20Au);
  v73 = 0;
  v29 = 0;
  v77 = 0;
  v30 = 0;
  v71 = 0;
  v31 = (struct _RTL_CRITICAL_SECTION *)(v15 + 8);
  while ( 1 )
  {
    v83 = 0;
    v85 = v31;
    EnterCriticalSection(v31);
    if ( v29 && v71 == *(_DWORD *)(v15 + 48) )
    {
      v30 = (__int64 *)*v30;
    }
    else
    {
      v30 = *(__int64 **)(v15 + 64);
      v71 = *(_DWORD *)(v15 + 48);
      v77 = 1;
    }
    while ( 1 )
    {
      if ( !v30 )
      {
        LeaveCriticalSection(v31);
        return 0;
      }
      if ( !a7 || *((_DWORD *)v30 + 20) )
      {
        if ( !v30[7] )
          goto LABEL_40;
        if ( !v28 )
        {
          v90 = v27;
          v91 = v26;
          v92 = v69;
          v93 = HIBYTE(pbstr[0]);
          if ( v26 )
          {
            LOBYTE(pbstr[0]) = 0;
            CrossMachineHwndClassName = HwndUtils::GetCrossMachineHwndClassName(&v90, hWnd, String1, 260, pbstr);
            if ( CrossMachineHwndClassName < 0 )
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x203,
                (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\hwndutils.cpp",
                (const char *)(unsigned int)CrossMachineHwndClassName,
                lpString2a);
            v39 = pbstr[0];
          }
          else
          {
            v39 = GetClassNameW(hWnd, String1, 260) != 0;
          }
          if ( !v39 )
          {
            LeaveCriticalSection(v31);
            return 0;
          }
          CharLowerW(String1);
          v28 = 1;
          v76 = 1;
        }
        v33 = *((_DWORD *)v30 + 18);
        v34 = (const WCHAR *)v30[7];
        if ( CompareStringW(0x7Fu, 0, String1, -1, v34, -1) == 2 || v33 && wcsstr(String1, v34) )
          goto LABEL_40;
        if ( *((_DWORD *)v30 + 19) && !v26 )
        {
          if ( !v72 )
          {
            UiaClientState::GetTimeoutData(v82, v86, 1);
            BaseClassName = BasicHwndUtils::GetBaseClassName(hWnd, (struct UIA_TIMEOUTDATA *)v86, Str, 261);
            v63 = BaseClassName;
            if ( BaseClassName < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x2E5,
                (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\clientproxymanager.cpp",
                (const char *)(unsigned int)BaseClassName,
                (int)lpString2);
              LeaveCriticalSection(v31);
              wil::com_ptr_t<IAccessibleAction,wil::err_exception_policy>::~com_ptr_t<IAccessibleAction,wil::err_exception_policy>(&v83);
              return v63;
            }
            CharLowerW(Str);
            v72 = 1;
          }
          if ( (unsigned int)HwndUtils::ClassNameMatch(Str, (wchar_t *)v30[7], *((_DWORD *)v30 + 18), 0) )
          {
LABEL_40:
            if ( !v30[8] )
              break;
            if ( !v26 )
            {
              if ( !v73 )
              {
                HwndUtils::GetImageName(hWnd, sz, v32);
                CharLowerW(sz);
                v73 = 1;
              }
              if ( !sz[0] || CompareStringW(0x7Fu, 0, sz, -1, (PCNZWCH)v30[8], -1) == 2 )
                break;
            }
          }
        }
      }
      v30 = (__int64 *)*v30;
    }
    v35 = (__int64 (__fastcall *)(struct ProviderEntryPoint *, _QWORD, _QWORD, _DWORD *, PCNZWCH, __int64, _QWORD *, struct IUnknown **, __int64))v30[3];
    v68 = *((_DWORD *)v30 + 8);
    v80 = *((_DWORD *)v30 + 9);
    v36 = *((_DWORD *)v30 + 10);
    v37 = v30[6];
    v83 = v37;
    if ( v37 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 8LL))(v37);
    LeaveCriticalSection(v31);
    if ( a9 && !v36 )
    {
LABEL_21:
      if ( v37 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
      return 0;
    }
    v38 = (char *)v14 + 60;
    if ( *((_DWORD *)v14 + 10) || *v38 )
      break;
    WindowThreadProcessId = GetWindowThreadProcessId(*((HWND *)v14 + 3), 0);
    if ( WindowThreadProcessId != GetCurrentThreadId() )
      goto LABEL_56;
LABEL_80:
    if ( !*v38 )
    {
      v48 = *(_QWORD *)(v79 + 56);
      v49 = *(_DWORD *)(v48 + 864);
      g_dwProxyBehaviorVersion = v49;
      if ( g_connectionTimeout )
        v50 = g_connectionTimeout;
      else
        v50 = *(_DWORD *)(v48 + 872);
      g_dwConnectionTimeout = v50;
      if ( g_transactionTimeout )
        v51 = g_transactionTimeout;
      else
        v51 = *(_DWORD *)(*(_QWORD *)(v79 + 56) + 876LL);
      v52 = (*(__int64 (__fastcall **)(__int64, HWND, _QWORD, _QWORD, __int64))(*(_QWORD *)v37 + 24LL))(
              v37,
              hWnd,
              v75,
              v74,
              v67);
      if ( v52 >= 0 )
      {
        v53 = *(void (__fastcall ****)(_QWORD, GUID *, __int64 *))v67;
        if ( *(_QWORD *)v67 )
        {
          v70 = 0;
          (**v53)(v53, &GUID_55f9c234_79cd_4699_89e7_5518fd88bcde, (__int64 *)&v70);
          v54 = v70;
          if ( v70 )
          {
            (*(void (__fastcall **)(struct ProviderEntryPoint *, _QWORD))(*(_QWORD *)v70 + 32LL))(v70, v49);
            v54 = v70;
          }
          if ( v54 )
            (*(void (__fastcall **)(struct ProviderEntryPoint *))(*(_QWORD *)v54 + 16LL))(v54);
          v55 = (struct IRawElementProviderSimple **)v67;
          v56 = *(void (__fastcall ****)(_QWORD, GUID *, __int64 *))v67;
          v67 = 0;
          (**v56)(v56, &GUID_f660d979_a938_423f_b5b9_12e4028c50b0, &v67);
          v57 = v67;
          if ( v67 )
          {
            (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v67 + 32LL))(v67, v50);
            v57 = v67;
          }
          if ( v57 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v57 + 16LL))(v57);
          v58 = *v55;
          v67 = 0;
          ((void (__fastcall *)(struct IRawElementProviderSimple *, GUID *, __int64 *))v58->lpVtbl->QueryInterface)(
            v58,
            &GUID_f660d979_a938_423f_b5b9_12e4028c50b0,
            &v67);
          v59 = v67;
          if ( v67 )
          {
            (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v67 + 48LL))(v67, v51);
            v59 = v67;
          }
          if ( v59 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 16LL))(v59);
          if ( a8 )
          {
            FocusedChild = GetFocusedChild(*v55);
            if ( FocusedChild )
            {
              ((void (__fastcall *)(struct IRawElementProviderSimple *))(*v55)->lpVtbl->Release)(*v55);
              *v55 = FocusedChild;
            }
          }
          goto LABEL_21;
        }
      }
      else
      {
        Error::GeneralProviderError(0, L"IUIAutomationProxyFactory::CreateProvider", v52, v70, 417, 0);
      }
    }
LABEL_87:
    if ( v37 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
    v28 = v76;
    v14 = v70;
    v15 = v79;
    v26 = pbstr[1];
    v29 = v77;
  }
  GetCurrentThreadId();
LABEL_56:
  v24 = 0;
  if ( !a6 || !v35 )
  {
LABEL_79:
    if ( v80 )
      goto LABEL_87;
    goto LABEL_80;
  }
  v41 = v87;
  v42 = v87 && *(_BYTE *)(v87 + 104);
  v94 = 0;
  v95 &= 0xC0u;
  v96 = GUID_NULL;
  bstrString = 0;
  v102 = 0;
  if ( v42 && *(_DWORD *)(*(_QWORD *)(v79 + 56) + 864LL) >= 0x80000u )
  {
    v43 = *(_QWORD *)(v87 + 24);
    if ( v43 )
    {
      if ( *(_DWORD *)(v87 + 100) == v68 )
      {
        *(_QWORD *)(v87 + 24) = 0;
        *v81 = v43;
        v44 = *(_QWORD *)(v41 + 32);
        if ( *(_QWORD *)v44 )
          ATL::AtlComPtrAssign(&v94, *(struct IUnknown **)v44);
        v95 = *(_BYTE *)(v44 + 8);
        v96 = *(GUID *)(v44 + 12);
        v45 = *(const unsigned __int16 **)(v44 + 32);
        if ( v45 && (int)HrSysAllocString(v45, &bstrString) < 0 )
          v96 = GUID_NULL;
        v46 = (__int64 *)(v44 + 40);
        if ( *(_BYTE *)(v44 + 80) )
        {
          if ( v102 )
          {
            v98 = *v46;
            v99 = *(_OWORD *)(v44 + 48);
            v100 = *(struct IUnknown **)(v44 + 64);
            wil::com_ptr_t<ProviderEntryPoint,wil::err_exception_policy>::operator=(&v101, *(_QWORD *)(v44 + 72));
          }
          else
          {
            std::_Optional_construct_base<CrossMachinePlaceholderInfo>::_Construct<CrossMachinePlaceholderInfo const &>(
              &v98,
              v46);
          }
        }
        else if ( v102 )
        {
          wil::com_ptr_t<IAccessibleAction,wil::err_exception_policy>::~com_ptr_t<IAccessibleAction,wil::err_exception_policy>(&v101);
          v102 = 0;
        }
LABEL_14:
        if ( *v81 )
        {
          v24 = 1;
          *v88 = v95 & 1;
          v25 = v89;
          if ( v89 )
          {
            if ( *v89 != v94 )
              ATL::AtlComPtrAssign(v89, v94);
            *((_BYTE *)v25 + 8) = v95;
            *(GUID *)((char *)v25 + 12) = v96;
            if ( bstrString && (int)HrSysAllocString(bstrString, (unsigned __int16 **)v25 + 4) < 0 )
              *(GUID *)((char *)v25 + 12) = GUID_NULL;
            v47 = v25 + 5;
            if ( v102 )
            {
              if ( *((_BYTE *)v25 + 80) )
              {
                *v47 = v98;
                *((_OWORD *)v25 + 3) = v99;
                v25[8] = v100;
                wil::com_ptr_t<ProviderEntryPoint,wil::err_exception_policy>::operator=(v25 + 9, v101);
              }
              else
              {
                std::_Optional_construct_base<CrossMachinePlaceholderInfo>::_Construct<CrossMachinePlaceholderInfo const &>(
                  v47,
                  &v98);
              }
            }
            else
            {
              std::_Optional_destruct_base<CrossMachinePlaceholderInfo,0>::reset(v47);
            }
          }
        }
LABEL_16:
        if ( v102 )
          wil::com_ptr_t<IAccessibleAction,wil::err_exception_policy>::~com_ptr_t<IAccessibleAction,wil::err_exception_policy>(&v101);
        if ( bstrString )
        {
          SysFreeString(bstrString);
          bstrString = 0;
        }
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v94);
        if ( v24 )
          goto LABEL_21;
        goto LABEL_79;
      }
    }
  }
  v17 = *(_QWORD *)(v79 + 56);
  v18 = *(_DWORD *)(v17 + 864);
  if ( g_connectionTimeout )
    v19 = g_connectionTimeout;
  else
    v19 = *(_DWORD *)(v17 + 872);
  if ( g_transactionTimeout )
    v20 = g_transactionTimeout;
  else
    v20 = *(_DWORD *)(*(_QWORD *)(v79 + 56) + 876LL);
  v84[0] = v68;
  v84[1] = v18;
  v84[2] = v19;
  v84[3] = v20;
  v21 = 0;
  if ( !v42 )
    v21 = v87;
  LODWORD(lpString2) = a8;
  v22 = v35(v70, v75, v74, v84, lpString2, v82, v81, &v94, v21);
  v23 = v22;
  if ( v22 != -2146233083 && v22 != -2147023436 )
  {
    if ( v22 < 0 )
      goto LABEL_16;
    goto LABEL_14;
  }
  ElementExtraInfo::~ElementExtraInfo((ElementExtraInfo *)&v94);
  if ( v37 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
  return v23;
}

```

## disassembly

```asm
0x1800922e0  push    rbp
0x1800922e2  push    rbx
0x1800922e3  push    rsi
0x1800922e4  push    rdi
0x1800922e5  push    r12
0x1800922e7  push    r13
0x1800922e9  push    r14
0x1800922eb  push    r15
0x1800922ed  lea     rbp, [rsp-6C8h]
0x1800922f5  sub     rsp, 7C8h
0x1800922fc  movaps  [rsp+800h+var_50], xmm6
0x180092304  mov     rax, cs:__security_cookie
0x18009230b  xor     rax, rsp
0x18009230e  mov     [rbp+700h+var_60], rax
0x180092315  mov     [rsp+800h+var_784], r9d
0x18009231a  mov     [rbp+700h+var_780], r8d
0x18009231e  mov     r13, rdx
0x180092321  mov     [rsp+800h+var_798], rdx
0x180092326  mov     rbx, rcx
0x180092329  mov     [rbp+700h+var_768], rcx
0x18009232d  mov     rax, [rbp+700h+arg_68]
0x180092334  mov     [rbp+700h+var_720], rax
0x180092338  mov     rax, [rbp+700h+arg_60]
0x18009233f  mov     [rbp+700h+var_710], rax
0x180092343  mov     rax, [rbp+700h+arg_20]
0x18009234a  mov     [rbp+700h+var_750], rax
0x18009234e  mov     rdx, [rbp+700h+arg_48]
0x180092355  mov     [rsp+800h+var_7A8], rdx
0x18009235a  mov     rax, [rbp+700h+arg_50]
0x180092361  mov     [rbp+700h+var_758], rax
0x180092365  mov     rcx, [rbp+700h+arg_58]
0x18009236c  mov     [rbp+700h+var_718], rcx
0x180092370  xor     edi, edi
0x180092372  mov     [rdx], rdi
0x180092375  cmp     [rbp+700h+arg_28], edi
0x18009237b  jz      short loc_180092382
0x18009237d  mov     [rax], rdi
0x180092380  mov     [rcx], edi
0x180092382  cmp     [r13+28h], edi
0x180092386  jz      loc_180092504
0x18009238c  mov     rcx, [rbp+708h]; this
0x180092393  mov     r9d, 8000FFFFh; char *
0x180092399  lea     r8, aOnecoreWindows_185; "onecore\\windows\\accessibletech\\uiaut"...
0x1800923a0  mov     edx, 297h; void *
0x1800923a5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800923aa  mov     eax, 8000FFFFh
0x1800923af  jmp     loc_1800924D9
0x1800923b4  mov     rcx, [r11+38h]
0x1800923b8  mov     r9d, [rcx+360h]
0x1800923bf  mov     eax, cs:?g_connectionTimeout@@3U?$atomic@K@std@@A; std::atomic<ulong> g_connectionTimeout
0x1800923c5  nop
0x1800923c6  test    eax, eax
0x1800923c8  jnz     loc_180092A12
0x1800923ce  mov     r8d, [rcx+368h]
0x1800923d5  mov     rcx, [r11+38h]
0x1800923d9  mov     eax, cs:?g_transactionTimeout@@3U?$atomic@K@std@@A; std::atomic<ulong> g_transactionTimeout
0x1800923df  nop
0x1800923e0  test    eax, eax
0x1800923e2  jnz     loc_180092B66
0x1800923e8  mov     eax, [rcx+36Ch]
0x1800923ee  mov     [rbp+700h+var_740], r10d
0x1800923f2  mov     [rbp+700h+var_73C], r9d
0x1800923f6  mov     [rbp+700h+var_738], r8d
0x1800923fa  mov     [rbp+700h+var_734], eax
0x1800923fd  xor     ecx, ecx
0x1800923ff  test    dl, dl
0x180092401  cmovz   rcx, r14
0x180092405  mov     [rsp+800h+var_7C0], rcx
0x18009240a  lea     rax, [rbp+700h+var_6F0]
0x18009240e  mov     [rsp+800h+var_7C8], rax
0x180092413  mov     rax, [rbp+700h+var_758]
0x180092417  mov     [rsp+800h+var_7D0], rax
0x18009241c  mov     rax, [rbp+700h+var_750]
0x180092420  mov     qword ptr [rsp+800h+cchCount2], rax
0x180092425  mov     eax, [rbp+700h+arg_38]
0x18009242b  mov     dword ptr [rsp+800h+lpString2], eax
0x18009242f  lea     r9, [rbp+700h+var_740]
0x180092433  mov     r8d, [rsp+800h+var_784]
0x180092438  mov     edx, [rbp+700h+var_780]
0x18009243b  mov     rcx, [rsp+800h+var_798]
0x180092440  mov     rax, r12
0x180092443  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092448  mov     r14d, eax
0x18009244b  cmp     eax, 80131505h
0x180092450  jz      loc_1800929EB
0x180092456  cmp     eax, 800705B4h
0x18009245b  jz      loc_1800929EB
0x180092461  test    eax, eax
0x180092463  js      short loc_18009248F
0x180092465  mov     rax, [rbp+700h+var_758]
0x180092469  cmp     qword ptr [rax], 0
0x18009246d  jz      short loc_18009248F
0x18009246f  mov     r13d, 1
0x180092475  movzx   eax, [rbp+700h+var_6E8]
0x180092479  and     eax, r13d
0x18009247c  mov     rcx, [rbp+700h+var_718]
0x180092480  mov     [rcx], eax
0x180092482  mov     r14, [rbp+700h+var_710]
0x180092486  test    r14, r14
0x180092489  jnz     loc_18009287B
0x18009248f  cmp     [rbp+700h+var_6A0], 0
0x180092493  jnz     loc_180092D0F
0x180092499  mov     rcx, [rbp+700h+bstrString]; bstrString
0x18009249d  test    rcx, rcx
0x1800924a0  jz      short loc_1800924B0
0x1800924a2  call    cs:__imp_SysFreeString
0x1800924a8  mov     [rbp+700h+bstrString], 0
0x1800924b0  lea     rcx, [rbp+700h+var_6F0]
0x1800924b4  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800924b9  test    r13d, r13d
0x1800924bc  jz      loc_1800928D8
0x1800924c2  test    rbx, rbx
0x1800924c5  jz      short loc_1800924D7
0x1800924c7  mov     rax, [rbx]
0x1800924ca  mov     rcx, rbx
0x1800924cd  mov     rax, [rax+10h]
0x1800924d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800924d6  nop
0x1800924d7  xor     eax, eax
0x1800924d9  mov     rcx, [rbp+700h+var_60]
0x1800924e0  xor     rcx, rsp; StackCookie
0x1800924e3  call    __security_check_cookie
0x1800924e8  movaps  xmm6, [rsp+800h+var_50]
0x1800924f0  add     rsp, 7C8h
0x1800924f7  pop     r15
0x1800924f9  pop     r14
0x1800924fb  pop     r13
0x1800924fd  pop     r12
0x1800924ff  pop     rdi
0x180092500  pop     rsi
0x180092501  pop     rbx
0x180092502  pop     rbp
0x180092503  retn
0x180092504  movzx   r12d, byte ptr [r13+3Ch]
0x180092509  mov     byte ptr [rsp+800h+pbstr+2], r12b
0x18009250e  mov     rax, [r13+18h]
0x180092512  mov     [rbp+700h+hWnd], rax
0x180092516  movups  xmm6, xmmword ptr [r13+2Ch]
0x18009251b  movzx   eax, word ptr [r13+3Dh]
0x180092520  mov     [rsp+800h+var_79C], ax
0x180092525  movzx   eax, byte ptr [r13+3Fh]
0x18009252a  mov     byte ptr [rsp+800h+pbstr+1], al
0x18009252e  mov     r15d, edi
0x180092531  mov     [rbp+700h+var_77C], edi
0x180092534  mov     [rsp+800h+var_78C], edi
0x180092538  xor     edx, edx; Val
0x18009253a  mov     r8d, 20Ah; Size
0x180092540  lea     rcx, [rbp+700h+Str]; void *
0x180092547  call    memset_0
0x18009254c  mov     [rsp+800h+var_788], edi
0x180092550  mov     r14d, edi
0x180092553  mov     [rbp+700h+var_778], edi
0x180092556  mov     rsi, rdi
0x180092559  mov     [rsp+800h+var_790], edi
0x18009255d  lea     rdi, [rbx+8]
0x180092561  mov     [rbp+700h+var_748], 0
0x180092569  mov     [rbp+700h+var_730], rdi
0x18009256d  mov     rcx, rdi; lpCriticalSection
0x180092570  call    cs:__imp_EnterCriticalSection
0x180092576  nop
0x180092577  test    r14d, r14d
0x18009257a  jnz     loc_1800929C7
0x180092580  mov     rsi, [rbx+40h]
0x180092584  mov     eax, [rbx+30h]
0x180092587  mov     [rsp+800h+var_790], eax
0x18009258b  mov     [rbp+700h+var_778], 1
0x180092592  test    rsi, rsi
0x180092595  jz      loc_180092D53
0x18009259b  cmp     [rbp+700h+arg_30], 0
0x1800925a2  jnz     loc_1800929DC
0x1800925a8  cmp     qword ptr [rsi+38h], 0
0x1800925ad  jz      short loc_180092601
0x1800925af  test    r15d, r15d
0x1800925b2  jz      loc_1800926F0
0x1800925b8  mov     r14d, [rsi+48h]
0x1800925bc  mov     rbx, [rsi+38h]
0x1800925c0  mov     [rsp+800h+cchCount2], 0FFFFFFFFh; cchCount2
0x1800925c8  mov     [rsp+800h+lpString2], rbx; int
0x1800925cd  mov     r9d, 0FFFFFFFFh; cchCount1
0x1800925d3  lea     r8, [rbp+700h+String1]; lpString1
0x1800925d7  xor     edx, edx; dwCmpFlags
0x1800925d9  mov     ecx, 7Fh; Locale
0x1800925de  call    cs:__imp_CompareStringW
0x1800925e4  cmp     eax, 2
0x1800925e7  jz      short loc_180092601
0x1800925e9  test    r14d, r14d
0x1800925ec  jnz     loc_1800926D5
0x1800925f2  cmp     dword ptr [rsi+4Ch], 0
0x1800925f6  jnz     loc_180092BCE
0x1800925fc  mov     rsi, [rsi]
0x1800925ff  jmp     short loc_180092592
0x180092601  cmp     qword ptr [rsi+40h], 0
0x180092606  jz      short loc_180092673
0x180092608  test    r12b, r12b
0x18009260b  jnz     short loc_1800925FC
0x18009260d  cmp     [rsp+800h+var_788], 0
0x180092612  jnz     short loc_180092639
0x180092614  lea     rdx, [rbp+700h+sz]; lpBaseName
0x18009261b  mov     rcx, [rbp+700h+hWnd]; hWnd
0x18009261f  call    ?GetImageName@HwndUtils@@SAXPEAUHWND__@@PEAGH@Z; HwndUtils::GetImageName(HWND__ *,ushort *,int)
0x180092624  lea     rcx, [rbp+700h+sz]; lpsz
0x18009262b  call    cs:__imp_CharLowerW
0x180092631  mov     [rsp+800h+var_788], 1
0x180092639  cmp     [rbp+700h+sz], 0
0x180092641  jz      short loc_180092673
0x180092643  mov     [rsp+800h+cchCount2], 0FFFFFFFFh; cchCount2
0x18009264b  mov     rax, [rsi+40h]
0x18009264f  mov     [rsp+800h+lpString2], rax; lpString2
0x180092654  mov     r9d, 0FFFFFFFFh; cchCount1
0x18009265a  lea     r8, [rbp+700h+sz]; lpString1
0x180092661  xor     edx, edx; dwCmpFlags
0x180092663  mov     ecx, 7Fh; Locale
0x180092668  call    cs:__imp_CompareStringW
0x18009266e  cmp     eax, 2
0x180092671  jnz     short loc_1800925FC
0x180092673  mov     r12, [rsi+18h]
0x180092677  mov     eax, [rsi+20h]
0x18009267a  mov     [rsp+800h+var_7A0], eax
0x18009267e  mov     eax, [rsi+24h]
0x180092681  mov     [rbp+700h+var_760], eax
0x180092684  mov     r14d, [rsi+28h]
0x180092688  mov     rbx, [rsi+30h]
0x18009268c  mov     [rbp+700h+var_748], rbx
0x180092690  test    rbx, rbx
0x180092693  jz      short loc_1800926A5
0x180092695  mov     rax, [rbx]
0x180092698  mov     rcx, rbx
0x18009269b  mov     rax, [rax+8]
0x18009269f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800926a4  nop
0x1800926a5  mov     rcx, rdi; lpCriticalSection
0x1800926a8  call    cs:__imp_LeaveCriticalSection
0x1800926ae  cmp     [rbp+700h+arg_40], 0
0x1800926b5  jnz     loc_18009274C
0x1800926bb  lea     r15, [r13+3Ch]
0x1800926bf  cmp     dword ptr [r13+28h], 0
0x1800926c4  jz      loc_18009275A
0x1800926ca  call    cs:__imp_GetCurrentThreadId
0x1800926d0  jmp     loc_180092782
0x1800926d5  mov     rdx, rbx; SubStr
0x1800926d8  lea     rcx, [rbp+700h+String1]; Str
0x1800926dc  call    cs:__imp_wcsstr
0x1800926e2  test    rax, rax
0x1800926e5  jz      loc_1800925F2
0x1800926eb  jmp     loc_180092601
0x1800926f0  movups  xmmword ptr [rbp+700h+var_708.Data1], xmm6
0x1800926f4  mov     [rbp+700h+var_6F8], r12b
0x1800926f8  movzx   eax, [rsp+800h+var_79C]
0x1800926fd  mov     [rbp+700h+var_6F7], ax
0x180092701  movzx   eax, byte ptr [rsp+800h+pbstr+1]
0x180092706  mov     [rbp+700h+var_6F5], al
0x180092709  test    r12b, r12b
0x18009270c  jnz     loc_180092B7F
0x180092712  mov     r8d, 104h; nMaxCount
0x180092718  lea     rdx, [rbp+700h+String1]; lpClassName
0x18009271c  mov     rcx, [rbp+700h+hWnd]; hWnd
0x180092720  call    cs:__imp_GetClassNameW
0x180092726  test    eax, eax
0x180092728  setnz   al
0x18009272b  test    al, al
0x18009272d  jz      loc_1800928C2
0x180092733  lea     rcx, [rbp+700h+String1]; lpsz
0x180092737  call    cs:__imp_CharLowerW
0x18009273d  mov     r15d, 1
0x180092743  mov     [rbp+700h+var_77C], r15d
0x180092747  jmp     loc_1800925B8
0x18009274c  test    r14d, r14d
0x18009274f  jnz     loc_1800926BB
0x180092755  jmp     loc_1800924C2
0x18009275a  cmp     byte ptr [r15], 0
0x18009275e  jnz     loc_1800926CA
0x180092764  xor     edx, edx; lpdwProcessId
0x180092766  mov     rcx, [r13+18h]; hWnd
0x18009276a  call    cs:__imp_GetWindowThreadProcessId
0x180092770  mov     r14d, eax
0x180092773  call    cs:__imp_GetCurrentThreadId
0x180092779  cmp     r14d, eax
0x18009277c  jz      loc_1800928D3
0x180092782  xor     ecx, ecx
0x180092784  mov     r13d, ecx
0x180092787  cmp     [rbp+700h+arg_28], ecx
0x18009278d  jz      loc_1800928D8
0x180092793  test    r12, r12
0x180092796  jz      loc_1800928D8
0x18009279c  mov     r14, [rbp+700h+var_720]
0x1800927a0  test    r14, r14
0x1800927a3  jz      loc_180092874
0x1800927a9  cmp     [r14+68h], cl
0x1800927ad  jz      loc_180092874
0x1800927b3  mov     dl, 1
0x1800927b5  mov     [rbp+700h+var_6F0], rcx
0x1800927b9  and     [rbp+700h+var_6E8], 0C0h
0x1800927bd  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800927c4  movups  [rbp+700h+var_6E4], xmm0
0x1800927c8  mov     [rbp+700h+bstrString], rcx
0x1800927cc  mov     [rbp+700h+var_6A0], 0
0x1800927d0  mov     r11, [rbp+700h+var_768]
0x1800927d4  mov     r10d, [rsp+800h+var_7A0]
0x1800927d9  test    dl, dl
0x1800927db  jz      loc_1800923B4
  ... truncated ...
```
