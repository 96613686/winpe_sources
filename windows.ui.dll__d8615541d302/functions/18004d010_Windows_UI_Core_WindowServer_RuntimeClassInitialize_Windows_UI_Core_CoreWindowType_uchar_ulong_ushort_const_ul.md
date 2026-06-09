# Windows::UI::Core::WindowServer::RuntimeClassInitialize(Windows::UI::Core::CoreWindowType,uchar,ulong,ushort const *,ulong,Windows::Foundation::Rect,ZBID,ulong,ulong)

- ea: `0x18004d010`
- end: `0x18004d535`
- name: `?RuntimeClassInitialize@WindowServer@Core@UI@Windows@@UEAAJW4CoreWindowType@234@EKPEBGKURect@Foundation@4@W4ZBID@@KK@Z`
- size: `1317`
- prototype: ``
- caller_count: `0`
- callee_count: `27`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180002684`
- `0x1800038e0`
- `0x18000aff0`
- `0x18000b2b8`
- `0x18000c7d4`
- `0x18000f048`
- `0x18000f35c`
- `0x18000fb38`
- `0x1800126c8`
- `0x1800127ec`
- `0x180013830`
- `0x180014754`
- `0x18001b90c`
- `0x180039d30`
- `0x18003f584`
- `0x180040e00`
- `0x180041280`
- `0x18004cb8c`
- `0x18004d010`
- `0x18004f4c4`
- `0x180056a14`
- `0x180056d3c`
- `0x1800586fc`
- `0x1800726fc`
- `0x180073f44`
- `0x18007f7e0`
- `0x1800ca010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18004d04d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18004d04d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18004d11d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18004d11d`
- `api-ms-win-core-processthreads-l1-1-1!GetProcessMitigationPolicy` at `0x18004d065`
- `api-ms-win-core-processthreads-l1-1-1!GetProcessMitigationPolicy` at `0x18004d065`
- `api-ms-win-core-quirks-l1-1-0!QuirkIsEnabled` at `0x18004d3c2`
- `api-ms-win-core-quirks-l1-1-0!QuirkIsEnabled` at `0x18004d3c2`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18004d413`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18004d413`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x18004d428`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x18004d428`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004d0d8`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004d38b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004d0d8`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004d38b`
- `WindowManagementAPI!CreateWindowLayout` at `0x18004d4b6`
- `WindowManagementAPI!CreateWindowLayout` at `0x18004d4b6`
- `WindowManagementAPI!CreateWindowInformation` at `0x18004d503`
- `WindowManagementAPI!CreateWindowInformation` at `0x18004d503`
- `SHCORE!__imp_RegisterScaleChangeNotificationsForWindow` at `0x18004d3e3`
- `SHCORE!__imp_RegisterScaleChangeNotificationsForWindow` at `0x18004d3e3`
- `CoreMessaging!CreateDispatcherQueueForCurrentThread` at `0x18004d2ad`
- `CoreMessaging!CreateDispatcherQueueForCurrentThread` at `0x18004d2ad`
- `api-ms-win-rtcore-ntuser-private-l1-1-7!IsOneCoreTransformMode` at `0x18004d1ca`
- `api-ms-win-rtcore-ntuser-private-l1-1-7!IsOneCoreTransformMode` at `0x18004d1ca`

## string_xrefs

- `0x18004d4cb`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\windowserver.cpp`

## pseudocode

```c
__int64 __fastcall Windows::UI::Core::WindowServer::RuntimeClassInitialize(
        __int64 a1,
        int a2,
        char a3,
        unsigned int a4,
        __int64 a5,
        unsigned int a6,
        const __m128i *a7,
        __int64 a8,
        int a9)
{
  HANDLE CurrentProcess; // rax
  bool v14; // zf
  LPCWSTR v15; // rsi
  void (__fastcall *v16)(LPCWSTR, GUID *, GUID *, __int64); // rdi
  DWORD CurrentProcessId; // eax
  __int64 v18; // rdx
  LPCWSTR v19; // rbx
  int DispatcherQueueForCurrentThread; // edi
  unsigned __int16 v21; // r8
  Windows::Internal::ApplicationModel::WindowManagement *v22; // rcx
  bool v23; // bl
  int v24; // eax
  __m128i v25; // xmm6
  const __m128i *v26; // rbx
  int NewWindow; // eax
  __int64 v28; // r8
  HWND v29; // rdx
  __int64 v30; // rdx
  __int64 v31; // rcx
  const WCHAR *FileNameW; // rax
  int v33; // ecx
  int v34; // r8d
  int v35; // r9d
  int WindowLayout; // ebx
  __int64 v37; // rdx
  LPVOID *ppv; // [rsp+20h] [rbp-40h]
  __m128i v40; // [rsp+40h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+38h]
  LPCWSTR pszPath; // [rsp+A0h] [rbp+40h] BYREF
  int v43; // [rsp+A8h] [rbp+48h] BYREF
  int v44; // [rsp+B0h] [rbp+50h] BYREF

  *(_BYTE *)(a1 + 2163) = 1;
  _InterlockedIncrement(&Windows::UI::Core::WindowServer::s_instanceCount);
  v43 = 0;
  CurrentProcess = GetCurrentProcess();
  if ( (unsigned int)GetProcessMitigationPolicy(CurrentProcess, 11, &v43, 4) )
    *(_BYTE *)(a1 + 2172) = (v43 & 0xF) == 5;
  v14 = (a9 & 2) == 0;
  *(_DWORD *)(a1 + 2148) = a2;
  *(_BYTE *)(a1 + 2156) = a3;
  if ( !v14 )
  {
    *(_BYTE *)(a1 + 2617) = 1;
    pszPath = 0;
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&pszPath);
    if ( CoCreateInstance(
           &CLSID_ShellServiceHostBrokerProvider,
           0,
           4u,
           &GUID_0f4accb1_d8f9_4011_ba37_2557925a78cf,
           (LPVOID *)&pszPath) >= 0 )
    {
      v15 = pszPath;
      v16 = *(void (__fastcall **)(LPCWSTR, GUID *, GUID *, __int64))(*(_QWORD *)pszPath + 24LL);
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(a1 + 3096);
      v16(v15, &GUID_1f79f7de_20bf_4591_930a_d490b78fb09f, &GUID_1f79f7de_20bf_4591_930a_d490b78fb09f, a1 + 3096);
    }
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&pszPath);
  }
  CurrentProcessId = GetCurrentProcessId();
  pszPath = 0;
  *(_DWORD *)(a1 + 2144) = CurrentProcessId;
  if ( (unsigned int)Windows::UI::Core::WindowServer::GetWindowForThread((struct Windows::UI::Core::ICoreWindow **)&pszPath) )
  {
    v19 = pszPath;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        15,
        &WPP_850f2c403a353c03d19f0821ea469488_Traceguids,
        pszPath,
        *(_DWORD *)(a1 + 376));
    }
    (*(void (__fastcall **)(LPCWSTR))(*(_QWORD *)v19 + 16LL))(v19);
    DispatcherQueueForCurrentThread = -2147483634;
    Windows::UI::Core::OriginateError((Windows::UI::Core *)0x8000000ELL, 1004, v21);
  }
  else
  {
    v23 = *(_BYTE *)(a1 + 2617) != 0;
    LOBYTE(v18) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_NoPlatformScaling>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_NoPlatformScaling>::GetImpl'::`2'::impl,
      v18);
    v24 = IsOneCoreTransformMode();
    *(_BYTE *)(a1 + 3133) = v23;
    v25 = 0;
    v26 = a7;
    *(_BYTE *)(a1 + 3132) = v24 != 0;
    if ( !v24 || CompositionIslandBridge::IsNavigationPhysicalCoordinates((CompositionIslandBridge *)(a1 + 3112)) )
      v25 = _mm_loadu_si128(v26);
    ppv = (LPVOID *)&v40;
    v40 = v25;
    NewWindow = Windows::UI::Core::WindowServer::CreateNewWindow(a1, a4, a5, a6);
    DispatcherQueueForCurrentThread = NewWindow;
    if ( *(_BYTE *)(a1 + 3132) )
    {
      if ( NewWindow < 0 )
        goto LABEL_35;
      if ( *(_BYTE *)(a1 + 2617) )
        DispatcherQueueForCurrentThread = Windows::UI::Core::WindowServer::InitializeGlobalCoreAppDCompDevice((Windows::UI::Core::WindowServer *)a1);
      CompositionIslandBridge::InitializeHwnd(
        (CompositionIslandBridge *)(a1 + 3112),
        *(HWND *)(a1 + 3464),
        *(struct IDCompositionDesktopDevicePartner **)(a1 + 2728));
      v40 = *v26;
      CompositionIslandBridge::NotifyNavigationBoundsChanged(a1 + 3112, &v40);
    }
    if ( DispatcherQueueForCurrentThread >= 0 )
    {
      *(_QWORD *)(a1 + 3016) = a1;
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DisableCoreDispatcherInWin32>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DisableCoreDispatcherInWin32>::GetImpl'::`2'::impl) )
      {
        Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(a1 + 3352);
        DispatcherQueueForCurrentThread = CreateDispatcherQueueForCurrentThread(a1 + 3352);
        if ( DispatcherQueueForCurrentThread < 0 )
          goto LABEL_35;
      }
      else
      {
        Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(a1 + 368);
        if ( !(unsigned int)Windows::UI::Core::CDispatcher::GetDispatcherForThread((struct Windows::UI::Core::CDispatcher **)(a1 + 368)) )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          {
            WPP_SF_qqD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              16,
              v28,
              *(_QWORD *)(a1 + 3016),
              *(_QWORD *)(a1 + 3464),
              *(_DWORD *)(a1 + 376));
          }
          Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(a1 + 368);
          Windows::UI::Core::CDispatcher::Create(a2 == 3, (struct Windows::UI::Core::CDispatcher **)(a1 + 368));
        }
        Windows::UI::Core::CDispatcher::SetPolicyForCoreWindow(*(Windows::UI::Core::CDispatcher **)(a1 + 368));
      }
      Windows::UI::Core::WindowServer::CreateDefaultCursor((Windows::UI::Core::WindowServer *)a1);
      Windows::UI::Core::SetWindowVisualizationHelper(*(Windows::UI::Core **)(a1 + 3464), v29);
      Windows::UI::Core::WindowServer::InitializeBoundsModeOverride((Windows::UI::Core::WindowServer *)a1);
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(a1 + 3088);
      if ( CoCreateInstance(
             &CLSID_UiaWindowNotifier,
             0,
             1u,
             &GUID_94552329_f99e_4f8a_b128_6cc2ae7fe28c,
             (LPVOID *)(a1 + 3088)) >= 0 )
        (*(void (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(a1 + 3088) + 24LL))(
          *(_QWORD *)(a1 + 3088),
          *(_QWORD *)(a1 + 3464));
      Windows::UI::Core::WindowServer::AddCoreWindowEntry((Windows::UI::Core::WindowServer *)a1);
    }
  }
LABEL_35:
  if ( !*(_BYTE *)(a1 + 2173) && !(unsigned int)QuirkIsEnabled(589829) )
    RegisterScaleChangeNotificationsForWindow(*(_QWORD *)(a1 + 3464), *(_QWORD *)(a1 + 3464), 1925, a1 + 2736);
  if ( Windows::Internal::ApplicationModel::WindowManagement::IsComponentUICShellPolicyEnabled(v22) )
  {
    pszPath = 0;
    if ( (int)wil::K32GetModuleFileNameExW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,128>(
                v31,
                v30,
                &pszPath) >= 0 )
    {
      FileNameW = PathFindFileNameW(pszPath);
      if ( FileNameW )
      {
        if ( StrStrIW(FileNameW, L"zStartApp.exe") && (unsigned int)dword_1801340C0 > 5 )
        {
          if ( (unsigned __int8)tlgKeywordOn(&dword_1801340C0, 0x400000000000LL) )
          {
            a9 = *(_DWORD *)(a1 + 3464);
            LOBYTE(v44) = *(_BYTE *)(a1 + 2617);
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<1>,_tlgWrapperByVal<4>>(
              v33,
              (unsigned int)byte_18011EEBD,
              v34,
              v35,
              (__int64)&v44,
              (__int64)&a9);
          }
        }
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pszPath);
  }
  if ( DispatcherQueueForCurrentThread >= 0 )
  {
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(a1 + 3328);
    WindowLayout = CreateWindowLayout(*(HWND *)(a1 + 3464), (struct Windows::UI::Core::IWindowLayout **)(a1 + 3328));
    if ( WindowLayout < 0 )
    {
      v37 = 779;
LABEL_49:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v37,
        (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\windowserver.cpp",
        (const char *)(unsigned int)WindowLayout,
        (int)ppv);
      return (unsigned int)WindowLayout;
    }
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(a1 + 3336);
    WindowLayout = CreateWindowInformation(
                     ~*(_DWORD *)(a1 + 3464),
                     *(HWND *)(a1 + 3464),
                     (struct Windows::UI::Core::IWindowInformation **)(a1 + 3336));
    if ( WindowLayout < 0 )
    {
      v37 = 780;
      goto LABEL_49;
    }
  }
  return (unsigned int)DispatcherQueueForCurrentThread;
}

```

## disassembly

```asm
0x18004d010  mov     [rsp-38h+arg_18], rbx
0x18004d015  push    rbp
0x18004d016  push    rsi
0x18004d017  push    rdi
0x18004d018  push    r12
0x18004d01a  push    r13
0x18004d01c  push    r14
0x18004d01e  push    r15
0x18004d020  mov     rbp, rsp
0x18004d023  sub     rsp, 60h
0x18004d027  movaps  [rsp+60h+var_10], xmm6
0x18004d02c  mov     r13d, r9d
0x18004d02f  mov     bl, r8b
0x18004d032  mov     byte ptr [rcx+873h], 1
0x18004d039  mov     r12d, edx
0x18004d03c  mov     r14, rcx
0x18004d03f  lock inc cs:?s_instanceCount@WindowServer@Core@UI@Windows@@2JA; long Windows::UI::Core::WindowServer::s_instanceCount
0x18004d046  mov     [rbp+arg_8], 0
0x18004d04d  call    cs:__imp_GetCurrentProcess
0x18004d053  mov     edi, 4
0x18004d058  lea     r8, [rbp+arg_8]
0x18004d05c  mov     rcx, rax
0x18004d05f  mov     r9d, edi
0x18004d062  lea     edx, [rdi+7]
0x18004d065  call    cs:__imp_GetProcessMitigationPolicy
0x18004d06b  test    eax, eax
0x18004d06d  jz      short loc_18004D081
0x18004d06f  mov     eax, [rbp+arg_8]
0x18004d072  and     eax, 0Fh
0x18004d075  cmp     al, 5
0x18004d077  setz    al
0x18004d07a  mov     [r14+87Ch], al
0x18004d081  test    byte ptr [rbp+arg_40], 2
0x18004d088  mov     r15d, [rbp+arg_48]
0x18004d08f  mov     [r14+864h], r12d
0x18004d096  mov     [r14+86Ch], bl
0x18004d09d  jz      short loc_18004D11D
0x18004d09f  lea     rcx, [rbp+pszPath]
0x18004d0a3  mov     byte ptr [r14+0A39h], 1
0x18004d0ab  or      r15d, 5
0x18004d0af  mov     [rbp+pszPath], 0
0x18004d0b7  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18004d0bc  lea     rax, [rbp+pszPath]
0x18004d0c0  mov     r8d, edi; dwClsContext
0x18004d0c3  lea     r9, _GUID_0f4accb1_d8f9_4011_ba37_2557925a78cf; riid
0x18004d0ca  mov     [rsp+60h+ppv], rax; ppv
0x18004d0cf  xor     edx, edx; pUnkOuter
0x18004d0d1  lea     rcx, CLSID_ShellServiceHostBrokerProvider; rclsid
0x18004d0d8  call    cs:__imp_CoCreateInstance
0x18004d0de  test    eax, eax
0x18004d0e0  js      short loc_18004D114
0x18004d0e2  mov     rsi, [rbp+pszPath]
0x18004d0e6  lea     rbx, [r14+0C18h]
0x18004d0ed  mov     rcx, rbx
0x18004d0f0  mov     rax, [rsi]
0x18004d0f3  mov     rdi, [rax+18h]
0x18004d0f7  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18004d0fc  lea     rdx, _GUID_1f79f7de_20bf_4591_930a_d490b78fb09f
0x18004d103  mov     r9, rbx
0x18004d106  mov     r8, rdx
0x18004d109  mov     rcx, rsi
0x18004d10c  mov     rax, rdi
0x18004d10f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d114  lea     rcx, [rbp+pszPath]
0x18004d118  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18004d11d  call    cs:__imp_GetCurrentProcessId
0x18004d123  lea     rcx, [rbp+pszPath]; struct Windows::UI::Core::ICoreWindow **
0x18004d127  mov     [rbp+pszPath], 0
0x18004d12f  mov     [r14+860h], eax
0x18004d136  call    ?GetWindowForThread@WindowServer@Core@UI@Windows@@SAHPEAPEAUICoreWindow@234@@Z; Windows::UI::Core::WindowServer::GetWindowForThread(Windows::UI::Core::ICoreWindow * *)
0x18004d13b  test    eax, eax
0x18004d13d  jz      short loc_18004D1AA
0x18004d13f  mov     rcx, cs:WPP_GLOBAL_Control
0x18004d146  lea     rax, WPP_GLOBAL_Control
0x18004d14d  mov     rbx, [rbp+pszPath]
0x18004d151  cmp     rcx, rax
0x18004d154  jz      short loc_18004D185
0x18004d156  test    byte ptr [rcx+1Ch], 2
0x18004d15a  jz      short loc_18004D185
0x18004d15c  cmp     byte ptr [rcx+19h], 2
0x18004d160  jb      short loc_18004D185
0x18004d162  mov     eax, [r14+178h]
0x18004d169  lea     r8, WPP_850f2c403a353c03d19f0821ea469488_Traceguids
0x18004d170  mov     rcx, [rcx+10h]
0x18004d174  mov     edx, 0Fh
0x18004d179  mov     r9, rbx
0x18004d17c  mov     dword ptr [rsp+60h+ppv], eax
0x18004d180  call    WPP_SF_qD
0x18004d185  mov     rax, [rbx]
0x18004d188  mov     rcx, rbx
0x18004d18b  mov     rax, [rax+10h]
0x18004d18f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d194  mov     edi, 8000000Eh
0x18004d199  mov     edx, 3ECh; int
0x18004d19e  mov     ecx, edi; this
0x18004d1a0  call    ?OriginateError@Core@UI@Windows@@YAXJG@Z; Windows::UI::Core::OriginateError(long,ushort)
0x18004d1a5  jmp     loc_18004D3B3
0x18004d1aa  cmp     byte ptr [r14+0A39h], 0
0x18004d1b2  setnz   bl
0x18004d1b5  mov     dl, 1
0x18004d1b7  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_NoPlatformScaling@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_NoPlatformScaling@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NoPlatformScaling> `wil::Feature<__WilFeatureTraits_Feature_NoPlatformScaling>::GetImpl(void)'::`2'::impl
0x18004d1be  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_NoPlatformScaling@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NoPlatformScaling>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18004d1c3  lea     rsi, [r14+0C28h]
0x18004d1ca  call    cs:__imp_IsOneCoreTransformMode
0x18004d1d0  mov     [r14+0C3Dh], bl
0x18004d1d7  xorps   xmm6, xmm6
0x18004d1da  mov     rbx, [rbp+arg_30]
0x18004d1de  test    eax, eax
0x18004d1e0  setnz   cl
0x18004d1e3  mov     [r14+0C3Ch], cl
0x18004d1ea  test    eax, eax
0x18004d1ec  jz      short loc_18004D1FA
0x18004d1ee  mov     rcx, rsi; this
0x18004d1f1  call    ?IsNavigationPhysicalCoordinates@CompositionIslandBridge@@QEBA_NXZ; CompositionIslandBridge::IsNavigationPhysicalCoordinates(void)
0x18004d1f6  test    al, al
0x18004d1f8  jz      short loc_18004D1FE
0x18004d1fa  movdqu  xmm6, xmmword ptr [rbx]
0x18004d1fe  mov     eax, [rbp+arg_38]
0x18004d201  mov     edx, r13d
0x18004d204  mov     r9d, [rbp+arg_28]
0x18004d208  mov     rcx, r14
0x18004d20b  mov     r8, [rbp+arg_20]
0x18004d20f  mov     [rsp+60h+var_30], r15d
0x18004d214  mov     dword ptr [rsp+60h+var_38], eax
0x18004d218  lea     rax, [rbp+var_20]
0x18004d21c  mov     [rsp+60h+ppv], rax
0x18004d221  movups  [rbp+var_20], xmm6
0x18004d225  call    ?CreateNewWindow@WindowServer@Core@UI@Windows@@QEAAJKPEBGKURect@Foundation@4@W4ZBID@@K@Z; Windows::UI::Core::WindowServer::CreateNewWindow(ulong,ushort const *,ulong,Windows::Foundation::Rect,ZBID,ulong)
0x18004d22a  cmp     byte ptr [r14+0C3Ch], 0
0x18004d232  mov     edi, eax
0x18004d234  jz      short loc_18004D27C
0x18004d236  test    eax, eax
0x18004d238  js      loc_18004D3B3
0x18004d23e  cmp     byte ptr [r14+0A39h], 0
0x18004d246  jz      short loc_18004D252
0x18004d248  mov     rcx, r14; this
0x18004d24b  call    ?InitializeGlobalCoreAppDCompDevice@WindowServer@Core@UI@Windows@@AEAAJXZ; Windows::UI::Core::WindowServer::InitializeGlobalCoreAppDCompDevice(void)
0x18004d250  mov     edi, eax
0x18004d252  mov     r8, [r14+0AA8h]; struct IDCompositionDesktopDevicePartner *
0x18004d259  mov     rcx, rsi; this
0x18004d25c  mov     rdx, [r14+0D88h]; HWND
0x18004d263  call    ?InitializeHwnd@CompositionIslandBridge@@QEAAXPEAUHWND__@@PEAUIDCompositionDesktopDevicePartner@@@Z; CompositionIslandBridge::InitializeHwnd(HWND__ *,IDCompositionDesktopDevicePartner *)
0x18004d268  movups  xmm0, xmmword ptr [rbx]
0x18004d26b  lea     rdx, [rbp+var_20]
0x18004d26f  mov     rcx, rsi
0x18004d272  movdqu  [rbp+var_20], xmm0
0x18004d277  call    ?NotifyNavigationBoundsChanged@CompositionIslandBridge@@QEAAXURect@Foundation@Windows@@@Z; CompositionIslandBridge::NotifyNavigationBoundsChanged(Windows::Foundation::Rect)
0x18004d27c  test    edi, edi
0x18004d27e  js      loc_18004D3B3
0x18004d284  mov     [r14+0BC8h], r14
0x18004d28b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DisableCoreDispatcherInWin32@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DisableCoreDispatcherInWin32@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DisableCoreDispatcherInWin32> `wil::Feature<__WilFeatureTraits_Feature_DisableCoreDispatcherInWin32>::GetImpl(void)'::`2'::impl
0x18004d292  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DisableCoreDispatcherInWin32@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DisableCoreDispatcherInWin32>::__private_IsEnabled(void)
0x18004d297  test    al, al
0x18004d299  jz      short loc_18004D2C2
0x18004d29b  lea     rbx, [r14+0D18h]
0x18004d2a2  mov     rcx, rbx
0x18004d2a5  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18004d2aa  mov     rcx, rbx
0x18004d2ad  call    cs:__imp_CreateDispatcherQueueForCurrentThread
0x18004d2b3  mov     edi, eax
0x18004d2b5  test    eax, eax
0x18004d2b7  js      loc_18004D3B3
0x18004d2bd  jmp     loc_18004D347
0x18004d2c2  lea     rbx, [r14+170h]
0x18004d2c9  mov     rcx, rbx
0x18004d2cc  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18004d2d1  mov     rcx, rbx; struct Windows::UI::Core::CDispatcher **
0x18004d2d4  call    ?GetDispatcherForThread@CDispatcher@Core@UI@Windows@@SAHPEAPEAV1234@@Z; Windows::UI::Core::CDispatcher::GetDispatcherForThread(Windows::UI::Core::CDispatcher * *)
0x18004d2d9  test    eax, eax
0x18004d2db  jnz     short loc_18004D33F
0x18004d2dd  mov     rcx, cs:WPP_GLOBAL_Control
0x18004d2e4  lea     rax, WPP_GLOBAL_Control
0x18004d2eb  cmp     rcx, rax
0x18004d2ee  jz      short loc_18004D328
0x18004d2f0  test    byte ptr [rcx+1Ch], 2
0x18004d2f4  jz      short loc_18004D328
0x18004d2f6  cmp     byte ptr [rcx+19h], 4
0x18004d2fa  jb      short loc_18004D328
0x18004d2fc  mov     eax, [r14+178h]
0x18004d303  mov     edx, 10h
0x18004d308  mov     r9, [r14+0BC8h]
0x18004d30f  mov     rcx, [rcx+10h]
0x18004d313  mov     dword ptr [rsp+60h+var_38], eax
0x18004d317  mov     rax, [r14+0D88h]
0x18004d31e  mov     [rsp+60h+ppv], rax
0x18004d323  call    WPP_SF_qqD
0x18004d328  mov     rcx, rbx
0x18004d32b  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18004d330  cmp     r12d, 3
0x18004d334  mov     rdx, rbx; struct Windows::UI::Core::CDispatcher **
0x18004d337  setz    cl; bool
0x18004d33a  call    ?Create@CDispatcher@Core@UI@Windows@@SAX_NPEAPEAV1234@@Z; Windows::UI::Core::CDispatcher::Create(bool,Windows::UI::Core::CDispatcher * *)
0x18004d33f  mov     rcx, [rbx]; this
0x18004d342  call    ?SetPolicyForCoreWindow@CDispatcher@Core@UI@Windows@@QEAAXXZ; Windows::UI::Core::CDispatcher::SetPolicyForCoreWindow(void)
0x18004d347  mov     rcx, r14; this
0x18004d34a  call    ?CreateDefaultCursor@WindowServer@Core@UI@Windows@@QEAAXXZ; Windows::UI::Core::WindowServer::CreateDefaultCursor(void)
0x18004d34f  mov     rcx, [r14+0D88h]; this
0x18004d356  call    ?SetWindowVisualizationHelper@Core@UI@Windows@@YAXPEAUHWND__@@@Z; Windows::UI::Core::SetWindowVisualizationHelper(HWND__ *)
0x18004d35b  mov     rcx, r14; this
0x18004d35e  call    ?InitializeBoundsModeOverride@WindowServer@Core@UI@Windows@@AEAAXXZ; Windows::UI::Core::WindowServer::InitializeBoundsModeOverride(void)
0x18004d363  lea     rbx, [r14+0C10h]
0x18004d36a  mov     rcx, rbx
0x18004d36d  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18004d372  xor     edx, edx; pUnkOuter
0x18004d374  mov     [rsp+60h+ppv], rbx; ppv
0x18004d379  lea     r9, _GUID_94552329_f99e_4f8a_b128_6cc2ae7fe28c; riid
0x18004d380  lea     rcx, CLSID_UiaWindowNotifier; rclsid
0x18004d387  lea     r8d, [rdx+1]; dwClsContext
0x18004d38b  call    cs:__imp_CoCreateInstance
0x18004d391  test    eax, eax
0x18004d393  js      short loc_18004D3AB
0x18004d395  mov     rcx, [rbx]
0x18004d398  mov     rdx, [r14+0D88h]
0x18004d39f  mov     rax, [rcx]
0x18004d3a2  mov     rax, [rax+18h]
0x18004d3a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d3ab  mov     rcx, r14; this
0x18004d3ae  call    ?AddCoreWindowEntry@WindowServer@Core@UI@Windows@@AEAAXXZ; Windows::UI::Core::WindowServer::AddCoreWindowEntry(void)
0x18004d3b3  cmp     byte ptr [r14+87Dh], 0
0x18004d3bb  jnz     short loc_18004D3E9
0x18004d3bd  mov     ecx, 90005h
0x18004d3c2  call    cs:__imp_QuirkIsEnabled
0x18004d3c8  test    eax, eax
0x18004d3ca  jnz     short loc_18004D3E9
0x18004d3cc  mov     rcx, [r14+0D88h]
0x18004d3d3  lea     r9, [r14+0AB0h]
0x18004d3da  mov     rdx, rcx
0x18004d3dd  mov     r8d, 785h
0x18004d3e3  call    cs:__imp_RegisterScaleChangeNotificationsForWindow
0x18004d3e9  call    ?IsComponentUICShellPolicyEnabled@WindowManagement@ApplicationModel@Internal@Windows@@YA_NXZ; Windows::Internal::ApplicationModel::WindowManagement::IsComponentUICShellPolicyEnabled(void)
0x18004d3ee  test    al, al
0x18004d3f0  jz      loc_18004D499
0x18004d3f6  lea     r8, [rbp+pszPath]
0x18004d3fa  mov     [rbp+pszPath], 0
0x18004d402  call    ??$K32GetModuleFileNameExW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0IA@@wil@@YAJPEAXPEAUHINSTANCE__@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@@Z; wil::K32GetModuleFileNameExW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,128>(void *,HINSTANCE__ *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x18004d407  test    eax, eax
0x18004d409  js      loc_18004D490
0x18004d40f  mov     rcx, [rbp+pszPath]; pszPath
0x18004d413  call    cs:__imp_PathFindFileNameW
0x18004d419  test    rax, rax
0x18004d41c  jz      short loc_18004D490
0x18004d41e  lea     rdx, pszSrch; "zStartApp.exe"
0x18004d425  mov     rcx, rax; pszFirst
0x18004d428  call    cs:__imp_StrStrIW
0x18004d42e  test    rax, rax
0x18004d431  jz      short loc_18004D490
0x18004d433  mov     eax, cs:dword_1801340C0
0x18004d439  cmp     eax, 5
0x18004d43c  jbe     short loc_18004D490
0x18004d43e  mov     rdx, 400000000000h
0x18004d448  lea     rcx, dword_1801340C0
0x18004d44f  call    _tlgKeywordOn
0x18004d454  test    al, al
0x18004d456  jz      short loc_18004D490
0x18004d458  mov     eax, [r14+0D88h]
0x18004d45f  lea     rdx, byte_18011EEBD
0x18004d466  mov     [rbp+arg_40], eax
0x18004d46c  mov     al, [r14+0A39h]
0x18004d473  mov     byte ptr [rbp+arg_10], al
0x18004d476  lea     rax, [rbp+arg_40]
0x18004d47d  mov     [rsp+60h+var_38], rax
0x18004d482  lea     rax, [rbp+arg_10]
0x18004d486  mov     [rsp+60h+ppv], rax; int
0x18004d48b  call    ??$Write@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<1>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<4> const &)
0x18004d490  lea     rcx, [rbp+pszPath]
0x18004d494  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18004d499  test    edi, edi
0x18004d49b  js      short loc_18004D516
0x18004d49d  lea     rbx, [r14+0D00h]
0x18004d4a4  mov     rcx, rbx
0x18004d4a7  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18004d4ac  mov     rcx, [r14+0D88h]
0x18004d4b3  mov     rdx, rbx
0x18004d4b6  call    cs:__imp_?CreateWindowLayout@@YAJPEAUHWND__@@PEAPEAUIWindowLayout@Core@UI@Windows@@@Z; CreateWindowLayout(HWND__ *,Windows::UI::Core::IWindowLayout * *)
0x18004d4bc  mov     ebx, eax
0x18004d4be  test    eax, eax
0x18004d4c0  jns     short loc_18004D4DE
0x18004d4c2  mov     edx, 30Bh; void *
0x18004d4c7  mov     rcx, [rbp+38h]; this
0x18004d4cb  lea     r8, aOnecoreuapWind_28; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x18004d4d2  mov     r9d, ebx; char *
0x18004d4d5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004d4da  mov     eax, ebx
0x18004d4dc  jmp     short loc_18004D518
0x18004d4de  lea     rbx, [r14+0D08h]
0x18004d4e5  mov     rcx, rbx
0x18004d4e8  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18004d4ed  mov     eax, [r14+0D88h]
0x18004d4f4  mov     r8, rbx
0x18004d4f7  mov     rdx, [r14+0D88h]
0x18004d4fe  not     eax
0x18004d500  movsxd  rcx, eax
0x18004d503  call    cs:__imp_?CreateWindowInformation@@YAJ_KPEAUHWND__@@PEAPEAUIWindowInformation@Core@UI@Windows@@@Z; CreateWindowInformation(unsigned __int64,HWND__ *,Windows::UI::Core::IWindowInformation * *)
0x18004d509  mov     ebx, eax
0x18004d50b  test    eax, eax
0x18004d50d  jns     short loc_18004D516
0x18004d50f  mov     edx, 30Ch
0x18004d514  jmp     short loc_18004D4C7
0x18004d516  mov     eax, edi
0x18004d518  mov     rbx, [rsp+60h+arg_18]
  ... truncated ...
```
