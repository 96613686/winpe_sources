# Windows::UI::Core::CCoreInput<&ushort const near * const RuntimeClass_Windows_UI_Core_CoreIndependentInputSource>::RuntimeClassInitialize(_COREINPUT_TYPE,_COREINPUT_POINTER_TYPE,ulong,IUnknown *,HWND__ *)

- ea: `0x18000e620`
- end: `0x18000eafe`
- name: `?RuntimeClassInitialize@?$CCoreInput@$1?RuntimeClass_Windows_UI_Core_CoreIndependentInputSource@@3QBGB@Core@UI@Windows@@UEAAJW4_COREINPUT_TYPE@@W4_COREINPUT_POINTER_TYPE@@KPEAUIUnknown@@PEAUHWND__@@@Z`
- size: `1246`
- prototype: `__int64 __usercall@<rax>(LPVOID lpParam@<rcx>, Windows::UI::Core *, __int64)`
- caller_count: `0`
- callee_count: `22`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x1800038e0`
- `0x180004e00`
- `0x18000c2a0`
- `0x18000c7d4`
- `0x18000e620`
- `0x18000eb04`
- `0x18000f048`
- `0x18000f35c`
- `0x18000f4bc`
- `0x180016064`
- `0x18003c7c8`
- `0x180050360`
- `0x1800517a0`
- `0x180056348`
- `0x18006d3e4`
- `0x18006d434`
- `0x18006d484`
- `0x18006f264`
- `0x180071c60`
- `0x180071cbc`
- `0x180071d6c`
- `0x1800ca010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000eade`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000eade`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000e654`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000e654`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000e6b8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000e6b8`
- `api-ms-win-core-processthreads-l1-1-1!GetProcessMitigationPolicy` at `0x18000e6cc`
- `api-ms-win-core-processthreads-l1-1-1!GetProcessMitigationPolicy` at `0x18000e6cc`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000e967`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000e967`

## string_xrefs

- `0x18000e74c`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\input.cpp`
- `0x18000e790`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\input.cpp`
- `0x18000e7be`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\input.cpp`
- `0x18000e7fe`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\input.cpp`
- `0x18000e86a`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\input.cpp`

## pseudocode

```c
__int64 __fastcall Windows::UI::Core::CCoreInput<&unsigned short const near * const RuntimeClass_Windows_UI_Core_CoreIndependentInputSource>::RuntimeClassInitialize(
        char *lpParam,
        int a2,
        int a3,
        char a4,
        Windows::UI::Core *a5,
        HWND a6)
{
  char v9; // al
  HANDLE CurrentProcess; // rax
  Windows::UI::Core *v11; // rdi
  int (__fastcall *v12)(Windows::UI::Core *, GUID *, char *); // rbx
  int v13; // eax
  Windows::UI::Core *v14; // rdi
  __int64 (__fastcall *v15)(Windows::UI::Core *, Windows::UI::Core **); // rbx
  int v16; // eax
  int v17; // eax
  __int64 v18; // rdi
  __int64 (__fastcall *v19)(__int64, Windows::UI::Core **); // rbx
  int v20; // eax
  struct IInspectable *v21; // rdx
  Windows::UI::Core *v22; // r15
  Windows::UI::Core *v23; // rsi
  void (__fastcall *v24)(Windows::UI::Core *, char *); // rdi
  struct IInspectable *v25; // rdx
  HWND v26; // rbx
  HWND WindowHandle; // rax
  int NewWindow; // ebx
  int InputThreadContext; // eax
  HWND v30; // rdx
  Windows::UI::Core *v31; // rcx
  int v33; // [rsp+20h] [rbp-30h]
  __int64 v34; // [rsp+28h] [rbp-28h]
  __int64 v35; // [rsp+40h] [rbp-10h] BYREF
  Windows::UI::Core *v36; // [rsp+48h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+38h]
  Windows::UI::Core *v38; // [rsp+90h] [rbp+40h] BYREF
  int v39; // [rsp+98h] [rbp+48h] BYREF

  *((_DWORD *)lpParam + 332) = a2;
  *((_DWORD *)lpParam + 333) = a3;
  AcquireSRWLockExclusive(&Windows::UI::Core::_InputSinkGlobals::s_srwCoreInputLock);
  v9 = ++Windows::UI::Core::CCoreInput<&unsigned short const near * const RuntimeClass_Windows_UI_Core_CoreIndependentInputSource>::s_instanceCount;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_qDds(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      18,
      (unsigned int)L"Windows.UI.Core.CoreIndependentInputSource",
      (_DWORD)lpParam,
      *((_DWORD *)lpParam + 64),
      v9,
      (__int64)L"Windows.UI.Core.CoreIndependentInputSource");
  }
  v39 = 0;
  CurrentProcess = GetCurrentProcess();
  if ( (unsigned int)GetProcessMitigationPolicy(CurrentProcess, 11, &v39, 4) )
    lpParam[1318] = (v39 & 0xF) == 5;
  v11 = a5;
  v38 = 0;
  if ( a5 )
  {
    v12 = **(int (__fastcall ***)(Windows::UI::Core *, GUID *, char *))a5;
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(lpParam + 1384);
    if ( v12(v11, &GUID_26b79665_54be_4aec_b1b7_c18403ce36ae, lpParam + 1384) >= 0 )
    {
      v36 = 0;
      v13 = Microsoft::WRL::ComPtr<Windows::UI::Composition::Internal::ICompositionIslandPartner>::As<Windows::UI::Composition::ICompositionObject>(
              lpParam + 1384,
              &v36);
      if ( v13 < 0 )
        wil::details::in1diag3::FailFast_Hr(
          retaddr,
          (void *)0x108,
          (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\input.cpp",
          (const char *)(unsigned int)v13,
          v33);
      a5 = 0;
      v14 = v36;
      v15 = *(__int64 (__fastcall **)(Windows::UI::Core *, Windows::UI::Core **))(*(_QWORD *)v36 + 48LL);
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&a5);
      v16 = v15(v14, &a5);
      if ( v16 < 0 )
        wil::details::in1diag3::FailFast_Hr(
          retaddr,
          (void *)0x10B,
          (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\input.cpp",
          (const char *)(unsigned int)v16,
          v33);
      v35 = 0;
      v17 = Microsoft::WRL::ComPtr<Windows::UI::Composition::ICompositor>::As<Windows::UI::Composition::Private::ICompositorForSystemPartner>(
              &a5,
              &v35);
      if ( v17 < 0 )
        wil::details::in1diag3::FailFast_Hr(
          retaddr,
          (void *)0x10F,
          (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\input.cpp",
          (const char *)(unsigned int)v17,
          v33);
      v18 = v35;
      v19 = *(__int64 (__fastcall **)(__int64, Windows::UI::Core **))(*(_QWORD *)v35 + 48LL);
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v38);
      v20 = v19(v18, &v38);
      if ( v20 < 0 )
        wil::details::in1diag3::FailFast_Hr(
          retaddr,
          (void *)0x113,
          (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\input.cpp",
          (const char *)(unsigned int)v20,
          v33);
      v11 = v38;
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v35);
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&a5);
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v36);
    }
  }
  a5 = 0;
  if ( (unsigned int)Windows::UI::Core::WindowServer::GetWindowForThread(&a5) )
  {
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(lpParam + 248);
    Windows::UI::Core::CDispatcher::GetDispatcherForThread((struct Windows::UI::Core::CDispatcher **)lpParam + 31);
    if ( !*((_QWORD *)lpParam + 31) )
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0x122,
        (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\input.cpp",
        (const char *)0x8000FFFFLL,
        v33);
  }
  v22 = a5;
  if ( !v11 )
  {
    WindowHandle = a6;
    if ( !a6 )
    {
      if ( a2 != 1 || !a5 )
        goto LABEL_35;
      WindowHandle = Windows::UI::Core::GetWindowHandle(a5, v21);
    }
    *((_QWORD *)lpParam + 175) = WindowHandle;
    goto LABEL_35;
  }
  a5 = 0;
  v35 = 0;
  v36 = v11;
  Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v36);
  Microsoft::WRL::ComPtr<IUnknown>::As<Windows::UI::Core::ICoreWindow>(&v36, &a5);
  Microsoft::WRL::ComPtr<Windows::UI::Core::ICoreWindow>::As<ICoreWindowInterop>(&a5, &v35);
  (*(void (__fastcall **)(__int64, char *))(*(_QWORD *)v35 + 24LL))(v35, lpParam + 1400);
  v23 = a5;
  v24 = *(void (__fastcall **)(Windows::UI::Core *, char *))(*(_QWORD *)a5 + 72LL);
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(lpParam + 1360);
  v24(v23, lpParam + 1360);
  if ( v22 )
  {
    v26 = (HWND)*((_QWORD *)lpParam + 175);
    if ( v26 != Windows::UI::Core::GetWindowHandle(v22, v25) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_qDqq(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          19,
          &WPP_3b510a2a222231b0f6327a10e76445fa_Traceguids,
          lpParam,
          *((_DWORD *)lpParam + 64),
          a5,
          v22);
      }
      RoOriginateError(2147942487LL, 0);
    }
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v36);
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v35);
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&a5);
LABEL_35:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    v34 = *((_QWORD *)lpParam + 175);
    WPP_SF_qDq(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_3b510a2a222231b0f6327a10e76445fa_Traceguids, lpParam);
  }
  NewWindow = Windows::UI::Core::CCoreInput<&unsigned short const near * const RuntimeClass_Windows_UI_Core_CoreIndependentInputSource>::CreateNewWindow(lpParam);
  if ( NewWindow >= 0 )
  {
    if ( a2 )
    {
      if ( a2 != 1 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          LODWORD(v34) = a2;
          WPP_SF_qDD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            21,
            &WPP_3b510a2a222231b0f6327a10e76445fa_Traceguids,
            lpParam,
            *((_DWORD *)lpParam + 64),
            v34);
        }
        NewWindow = -2147418113;
        goto LABEL_51;
      }
      InputThreadContext = Windows::UI::Core::CCoreInput<&unsigned short const near * const RuntimeClass_Windows_UI_Core_CoreIndependentInputSource>::InitializeComponentInput(
                             lpParam,
                             v22);
    }
    else
    {
      InputThreadContext = Windows::UI::Core::CCoreInput<&unsigned short const near * const RuntimeClass_Windows_UI_Core_CoreIndependentInputSource>::GetOrCreateInputThreadContext(
                             lpParam,
                             v22,
                             0);
    }
    NewWindow = InputThreadContext;
    if ( InputThreadContext >= 0 )
    {
      Windows::UI::Core::CCoreInput<&unsigned short const near * const RuntimeClass_Windows_UI_Core_CoreIndependentInputSource>::CreateDefaultCursor(lpParam);
      Windows::UI::Core::SetWindowVisualizationHelper(*((Windows::UI::Core **)lpParam + 165), v30);
    }
  }
LABEL_51:
  lpParam[1313] = a4 & 1;
  if ( v22 )
    (*(void (__fastcall **)(Windows::UI::Core *))(*(_QWORD *)v22 + 16LL))(v22);
  v31 = v38;
  if ( v38 )
  {
    v38 = 0;
    (*(void (__fastcall **)(Windows::UI::Core *))(*(_QWORD *)v31 + 16LL))(v31);
  }
  ReleaseSRWLockExclusive(&Windows::UI::Core::_InputSinkGlobals::s_srwCoreInputLock);
  return (unsigned int)NewWindow;
}

```

## disassembly

```asm
0x18000e620  mov     [rsp-38h+arg_10], rbx
0x18000e625  push    rbp
0x18000e626  push    rsi
0x18000e627  push    rdi
0x18000e628  push    r12
0x18000e62a  push    r13
0x18000e62c  push    r14
0x18000e62e  push    r15
0x18000e630  mov     rbp, rsp
0x18000e633  sub     rsp, 50h
0x18000e637  mov     r13d, r9d
0x18000e63a  mov     r12d, edx
0x18000e63d  mov     r14, rcx
0x18000e640  mov     [rcx+530h], edx
0x18000e646  mov     [rcx+534h], r8d
0x18000e64d  lea     rcx, ?s_srwCoreInputLock@_InputSinkGlobals@Core@UI@Windows@@2VSRWLock@Wrappers@WRL@Microsoft@@A; SRWLock
0x18000e654  call    cs:__imp_AcquireSRWLockExclusive
0x18000e65a  mov     eax, cs:?s_instanceCount@?$CCoreInput@$1?RuntimeClass_Windows_UI_Core_CoreIndependentInputSource@@3QBGB@Core@UI@Windows@@2JA; long Windows::UI::Core::CCoreInput<&ushort const near * const RuntimeClass_Windows_UI_Core_CoreIndependentInputSource>::s_instanceCount
0x18000e660  inc     eax
0x18000e662  mov     cs:?s_instanceCount@?$CCoreInput@$1?RuntimeClass_Windows_UI_Core_CoreIndependentInputSource@@3QBGB@Core@UI@Windows@@2JA, eax; long Windows::UI::Core::CCoreInput<&ushort const near * const RuntimeClass_Windows_UI_Core_CoreIndependentInputSource>::s_instanceCount
0x18000e668  lea     rdx, WPP_GLOBAL_Control
0x18000e66f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e676  cmp     rcx, rdx
0x18000e679  jz      short loc_18000E6B3
0x18000e67b  test    byte ptr [rcx+1Ch], 40h
0x18000e67f  jz      short loc_18000E6B3
0x18000e681  cmp     byte ptr [rcx+19h], 4
0x18000e685  jb      short loc_18000E6B3
0x18000e687  mov     edx, 12h
0x18000e68c  lea     r8, ?RuntimeClass_Windows_UI_Core_CoreIndependentInputSource@@3QBGB; "Windows.UI.Core.CoreIndependentInputSou"...
0x18000e693  mov     [rsp+50h+var_20], r8
0x18000e698  mov     dword ptr [rsp+50h+var_28], eax
0x18000e69c  mov     eax, [r14+100h]
0x18000e6a3  mov     [rsp+50h+var_30], eax; int
0x18000e6a7  mov     r9, r14
0x18000e6aa  mov     rcx, [rcx+10h]
0x18000e6ae  call    WPP_SF_qDds
0x18000e6b3  xor     esi, esi
0x18000e6b5  mov     [rbp+arg_8], esi
0x18000e6b8  call    cs:__imp_GetCurrentProcess
0x18000e6be  mov     rcx, rax
0x18000e6c1  lea     r9d, [rsi+4]
0x18000e6c5  lea     r8, [rbp+arg_8]
0x18000e6c9  lea     edx, [rsi+0Bh]
0x18000e6cc  call    cs:__imp_GetProcessMitigationPolicy
0x18000e6d2  test    eax, eax
0x18000e6d4  jz      short loc_18000E6E8
0x18000e6d6  mov     eax, [rbp+arg_8]
0x18000e6d9  and     eax, 0Fh
0x18000e6dc  cmp     al, 5
0x18000e6de  setz    al
0x18000e6e1  mov     [r14+526h], al
0x18000e6e8  mov     rdi, [rbp+arg_20]
0x18000e6ec  mov     [rbp+arg_0], rsi
0x18000e6f0  test    rdi, rdi
0x18000e6f3  jz      loc_18000E833
0x18000e6f9  mov     rax, [rdi]
0x18000e6fc  mov     rbx, [rax]
0x18000e6ff  lea     rsi, [r14+568h]
0x18000e706  mov     rcx, rsi
0x18000e709  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18000e70e  mov     r8, rsi
0x18000e711  lea     rdx, _GUID_26b79665_54be_4aec_b1b7_c18403ce36ae
0x18000e718  mov     rcx, rdi
0x18000e71b  mov     rax, rbx
0x18000e71e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e723  test    eax, eax
0x18000e725  js      loc_18000E831
0x18000e72b  mov     [rbp+var_8], 0
0x18000e733  lea     rdx, [rbp+var_8]
0x18000e737  mov     rcx, rsi
0x18000e73a  call    ??$As@UICompositionObject@Composition@UI@Windows@@@?$ComPtr@UICompositionIslandPartner@Internal@Composition@UI@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UICompositionObject@Composition@UI@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::UI::Composition::Internal::ICompositionIslandPartner>::As<Windows::UI::Composition::ICompositionObject>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::UI::Composition::ICompositionObject>>)
0x18000e73f  mov     rcx, [rbp+38h]; this
0x18000e743  xor     esi, esi
0x18000e745  test    eax, eax
0x18000e747  jns     short loc_18000E75E
0x18000e749  mov     r9d, eax; char *
0x18000e74c  lea     r8, aOnecoreuapWind_17; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x18000e753  mov     edx, 108h; void *
0x18000e758  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x18000e75e  mov     [rbp+arg_20], rsi
0x18000e762  mov     rdi, [rbp+var_8]
0x18000e766  mov     rax, [rdi]
0x18000e769  mov     rbx, [rax+30h]
0x18000e76d  lea     rcx, [rbp+arg_20]
0x18000e771  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18000e776  lea     rdx, [rbp+arg_20]
0x18000e77a  mov     rcx, rdi
0x18000e77d  mov     rax, rbx
0x18000e780  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e785  mov     rcx, [rbp+38h]; this
0x18000e789  test    eax, eax
0x18000e78b  jns     short loc_18000E7A2
0x18000e78d  mov     r9d, eax; char *
0x18000e790  lea     r8, aOnecoreuapWind_17; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x18000e797  mov     edx, 10Bh; void *
0x18000e79c  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x18000e7a2  mov     [rbp+var_10], rsi
0x18000e7a6  lea     rdx, [rbp+var_10]
0x18000e7aa  lea     rcx, [rbp+arg_20]
0x18000e7ae  call    ??$As@UICompositorForSystemPartner@Private@Composition@UI@Windows@@@?$ComPtr@UICompositor@Composition@UI@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UICompositorForSystemPartner@Private@Composition@UI@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::UI::Composition::ICompositor>::As<Windows::UI::Composition::Private::ICompositorForSystemPartner>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::UI::Composition::Private::ICompositorForSystemPartner>>)
0x18000e7b3  mov     rcx, [rbp+38h]; this
0x18000e7b7  test    eax, eax
0x18000e7b9  jns     short loc_18000E7D0
0x18000e7bb  mov     r9d, eax; char *
0x18000e7be  lea     r8, aOnecoreuapWind_17; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x18000e7c5  mov     edx, 10Fh; void *
0x18000e7ca  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x18000e7d0  mov     rdi, [rbp+var_10]
0x18000e7d4  mov     rax, [rdi]
0x18000e7d7  mov     rbx, [rax+30h]
0x18000e7db  lea     rcx, [rbp+arg_0]
0x18000e7df  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18000e7e4  lea     rdx, [rbp+arg_0]
0x18000e7e8  mov     rcx, rdi
0x18000e7eb  mov     rax, rbx
0x18000e7ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e7f3  mov     rcx, [rbp+38h]; this
0x18000e7f7  test    eax, eax
0x18000e7f9  jns     short loc_18000E810
0x18000e7fb  mov     r9d, eax; char *
0x18000e7fe  lea     r8, aOnecoreuapWind_17; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x18000e805  mov     edx, 113h; void *
0x18000e80a  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x18000e810  mov     rdi, [rbp+arg_0]
0x18000e814  lea     rcx, [rbp+var_10]
0x18000e818  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18000e81d  lea     rcx, [rbp+arg_20]
0x18000e821  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18000e826  lea     rcx, [rbp+var_8]
0x18000e82a  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18000e82f  jmp     short loc_18000E833
0x18000e831  xor     esi, esi
0x18000e833  mov     [rbp+arg_20], rsi
0x18000e837  lea     rcx, [rbp+arg_20]; struct Windows::UI::Core::ICoreWindow **
0x18000e83b  call    ?GetWindowForThread@WindowServer@Core@UI@Windows@@SAHPEAPEAUICoreWindow@234@@Z; Windows::UI::Core::WindowServer::GetWindowForThread(Windows::UI::Core::ICoreWindow * *)
0x18000e840  test    eax, eax
0x18000e842  jz      short loc_18000E87C
0x18000e844  lea     rbx, [r14+0F8h]
0x18000e84b  mov     rcx, rbx
0x18000e84e  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18000e853  mov     rcx, rbx; struct Windows::UI::Core::CDispatcher **
0x18000e856  call    ?GetDispatcherForThread@CDispatcher@Core@UI@Windows@@SAHPEAPEAV1234@@Z; Windows::UI::Core::CDispatcher::GetDispatcherForThread(Windows::UI::Core::CDispatcher * *)
0x18000e85b  cmp     [rbx], rsi
0x18000e85e  jnz     short loc_18000E87C
0x18000e860  mov     rcx, [rbp+38h]; this
0x18000e864  mov     r9d, 8000FFFFh; char *
0x18000e86a  lea     r8, aOnecoreuapWind_17; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x18000e871  mov     edx, 122h; void *
0x18000e876  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x18000e87c  mov     r15, [rbp+arg_20]
0x18000e880  test    rdi, rdi
0x18000e883  jz      loc_18000E993
0x18000e889  mov     [rbp+arg_20], rsi
0x18000e88d  mov     [rbp+var_10], rsi
0x18000e891  mov     [rbp+var_8], rdi
0x18000e895  lea     rcx, [rbp+var_8]
0x18000e899  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x18000e89e  lea     rdx, [rbp+arg_20]
0x18000e8a2  lea     rcx, [rbp+var_8]
0x18000e8a6  call    ??$As@UICoreWindow@Core@UI@Windows@@@?$ComPtr@UIUnknown@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UICoreWindow@Core@UI@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IUnknown>::As<Windows::UI::Core::ICoreWindow>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::UI::Core::ICoreWindow>>)
0x18000e8ab  lea     rdx, [rbp+var_10]
0x18000e8af  lea     rcx, [rbp+arg_20]
0x18000e8b3  call    ??$As@UICoreWindowInterop@@@?$ComPtr@UICoreWindow@Core@UI@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UICoreWindowInterop@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::UI::Core::ICoreWindow>::As<ICoreWindowInterop>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<ICoreWindowInterop>>)
0x18000e8b8  mov     rcx, [rbp+var_10]
0x18000e8bc  lea     rdx, [r14+578h]
0x18000e8c3  mov     rax, [rcx]
0x18000e8c6  mov     rax, [rax+18h]
0x18000e8ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e8cf  mov     rsi, [rbp+arg_20]
0x18000e8d3  mov     rax, [rsi]
0x18000e8d6  mov     rdi, [rax+48h]
0x18000e8da  lea     rbx, [r14+550h]
0x18000e8e1  mov     rcx, rbx
0x18000e8e4  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18000e8e9  mov     rdx, rbx
0x18000e8ec  mov     rcx, rsi
0x18000e8ef  mov     rax, rdi
0x18000e8f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e8f7  xor     esi, esi
0x18000e8f9  test    r15, r15
0x18000e8fc  jz      short loc_18000E96F
0x18000e8fe  mov     rbx, [r14+578h]
0x18000e905  mov     rcx, r15; this
0x18000e908  call    ?GetWindowHandle@Core@UI@Windows@@YAPEAUHWND__@@PEAUIInspectable@@@Z; Windows::UI::Core::GetWindowHandle(IInspectable *)
0x18000e90d  cmp     rbx, rax
0x18000e910  jz      short loc_18000E96F
0x18000e912  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e919  lea     rdi, WPP_GLOBAL_Control
0x18000e920  cmp     rcx, rdi
0x18000e923  jz      short loc_18000E960
0x18000e925  test    byte ptr [rcx+1Ch], 40h
0x18000e929  jz      short loc_18000E960
0x18000e92b  cmp     byte ptr [rcx+19h], 2
0x18000e92f  jb      short loc_18000E960
0x18000e931  lea     edx, [rsi+13h]
0x18000e934  mov     [rsp+50h+var_20], r15
0x18000e939  mov     rax, [rbp+arg_20]
0x18000e93d  mov     [rsp+50h+var_28], rax
0x18000e942  mov     eax, [r14+100h]
0x18000e949  mov     [rsp+50h+var_30], eax
0x18000e94d  mov     r9, r14
0x18000e950  lea     r8, WPP_3b510a2a222231b0f6327a10e76445fa_Traceguids
0x18000e957  mov     rcx, [rcx+10h]
0x18000e95b  call    WPP_SF_qDqq
0x18000e960  xor     edx, edx
0x18000e962  mov     ecx, 80070057h
0x18000e967  call    cs:__imp_RoOriginateError
0x18000e96d  jmp     short loc_18000E976
0x18000e96f  lea     rdi, WPP_GLOBAL_Control
0x18000e976  lea     rcx, [rbp+var_8]
0x18000e97a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000e97f  lea     rcx, [rbp+var_10]
0x18000e983  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18000e988  lea     rcx, [rbp+arg_20]
0x18000e98c  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18000e991  jmp     short loc_18000E9BD
0x18000e993  mov     rax, [rbp+arg_28]
0x18000e997  test    rax, rax
0x18000e99a  jnz     short loc_18000E9AF
0x18000e99c  cmp     r12d, 1
0x18000e9a0  jnz     short loc_18000E9B6
0x18000e9a2  test    r15, r15
0x18000e9a5  jz      short loc_18000E9B6
0x18000e9a7  mov     rcx, r15; this
0x18000e9aa  call    ?GetWindowHandle@Core@UI@Windows@@YAPEAUHWND__@@PEAUIInspectable@@@Z; Windows::UI::Core::GetWindowHandle(IInspectable *)
0x18000e9af  mov     [r14+578h], rax
0x18000e9b6  lea     rdi, WPP_GLOBAL_Control
0x18000e9bd  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e9c4  cmp     rcx, rdi
0x18000e9c7  jz      short loc_18000EA04
0x18000e9c9  test    byte ptr [rcx+1Ch], 40h
0x18000e9cd  jz      short loc_18000EA04
0x18000e9cf  cmp     byte ptr [rcx+19h], 4
0x18000e9d3  jb      short loc_18000EA04
0x18000e9d5  mov     edx, 14h
0x18000e9da  mov     rax, [r14+578h]
0x18000e9e1  mov     [rsp+50h+var_28], rax
0x18000e9e6  mov     eax, [r14+100h]
0x18000e9ed  mov     [rsp+50h+var_30], eax
0x18000e9f1  mov     r9, r14
0x18000e9f4  lea     r8, WPP_3b510a2a222231b0f6327a10e76445fa_Traceguids
0x18000e9fb  mov     rcx, [rcx+10h]
0x18000e9ff  call    WPP_SF_qDq
0x18000ea04  mov     rcx, r14; lpParam
0x18000ea07  call    ?CreateNewWindow@?$CCoreInput@$1?RuntimeClass_Windows_UI_Core_CoreIndependentInputSource@@3QBGB@Core@UI@Windows@@IEAAJXZ; Windows::UI::Core::CCoreInput<&ushort const near * const RuntimeClass_Windows_UI_Core_CoreIndependentInputSource>::CreateNewWindow(void)
0x18000ea0c  mov     ebx, eax
0x18000ea0e  test    eax, eax
0x18000ea10  js      loc_18000EA9D
0x18000ea16  test    r12d, r12d
0x18000ea19  jz      short loc_18000EA75
0x18000ea1b  cmp     r12d, 1
0x18000ea1f  jz      short loc_18000EA68
0x18000ea21  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ea28  cmp     rcx, rdi
0x18000ea2b  jz      short loc_18000EA61
0x18000ea2d  test    byte ptr [rcx+1Ch], 40h
0x18000ea31  jz      short loc_18000EA61
0x18000ea33  cmp     byte ptr [rcx+19h], 2
0x18000ea37  jb      short loc_18000EA61
0x18000ea39  mov     edx, 15h
0x18000ea3e  mov     dword ptr [rsp+50h+var_28], r12d
0x18000ea43  mov     eax, [r14+100h]
0x18000ea4a  mov     [rsp+50h+var_30], eax
0x18000ea4e  mov     r9, r14
0x18000ea51  lea     r8, WPP_3b510a2a222231b0f6327a10e76445fa_Traceguids
0x18000ea58  mov     rcx, [rcx+10h]
0x18000ea5c  call    WPP_SF_qDD
0x18000ea61  mov     ebx, 8000FFFFh
0x18000ea66  jmp     short loc_18000EA9D
0x18000ea68  mov     rdx, r15
0x18000ea6b  mov     rcx, r14
0x18000ea6e  call    ?InitializeComponentInput@?$CCoreInput@$1?RuntimeClass_Windows_UI_Core_CoreIndependentInputSource@@3QBGB@Core@UI@Windows@@AEAAJPEAUICoreWindow@234@@Z; Windows::UI::Core::CCoreInput<&ushort const near * const RuntimeClass_Windows_UI_Core_CoreIndependentInputSource>::InitializeComponentInput(Windows::UI::Core::ICoreWindow *)
0x18000ea73  jmp     short loc_18000EA83
0x18000ea75  xor     r8d, r8d
0x18000ea78  mov     rdx, r15
0x18000ea7b  mov     rcx, r14
0x18000ea7e  call    ?GetOrCreateInputThreadContext@?$CCoreInput@$1?RuntimeClass_Windows_UI_Core_CoreIndependentInputSource@@3QBGB@Core@UI@Windows@@AEAAJPEAUICoreWindow@234@W4_COREINPUT_TYPE@@@Z; Windows::UI::Core::CCoreInput<&ushort const near * const RuntimeClass_Windows_UI_Core_CoreIndependentInputSource>::GetOrCreateInputThreadContext(Windows::UI::Core::ICoreWindow *,_COREINPUT_TYPE)
0x18000ea83  mov     ebx, eax
0x18000ea85  test    eax, eax
0x18000ea87  js      short loc_18000EA9D
0x18000ea89  mov     rcx, r14
0x18000ea8c  call    ?CreateDefaultCursor@?$CCoreInput@$1?RuntimeClass_Windows_UI_Core_CoreIndependentInputSource@@3QBGB@Core@UI@Windows@@IEAAXXZ; Windows::UI::Core::CCoreInput<&ushort const near * const RuntimeClass_Windows_UI_Core_CoreIndependentInputSource>::CreateDefaultCursor(void)
0x18000ea91  mov     rcx, [r14+528h]; this
0x18000ea98  call    ?SetWindowVisualizationHelper@Core@UI@Windows@@YAXPEAUHWND__@@@Z; Windows::UI::Core::SetWindowVisualizationHelper(HWND__ *)
0x18000ea9d  and     r13b, 1
0x18000eaa1  mov     [r14+521h], r13b
0x18000eaa8  test    r15, r15
0x18000eaab  jz      short loc_18000EABD
0x18000eaad  mov     rax, [r15]
0x18000eab0  mov     rcx, r15
0x18000eab3  mov     rax, [rax+10h]
0x18000eab7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eabc  nop
0x18000eabd  mov     rcx, [rbp+arg_0]
0x18000eac1  test    rcx, rcx
0x18000eac4  jz      short loc_18000EAD7
0x18000eac6  mov     [rbp+arg_0], rsi
0x18000eaca  mov     rax, [rcx]
0x18000eacd  mov     rax, [rax+10h]
  ... truncated ...
```
