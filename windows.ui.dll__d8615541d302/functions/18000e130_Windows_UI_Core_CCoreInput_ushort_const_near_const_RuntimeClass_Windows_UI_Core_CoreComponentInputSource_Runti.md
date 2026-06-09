# Windows::UI::Core::CCoreInput<&ushort const near * const RuntimeClass_Windows_UI_Core_CoreComponentInputSource>::RuntimeClassInitialize(_COREINPUT_TYPE,_COREINPUT_POINTER_TYPE,ulong,IUnknown *,HWND__ *)

- ea: `0x18000e130`
- end: `0x18000e60e`
- name: `?RuntimeClassInitialize@?$CCoreInput@$1?RuntimeClass_Windows_UI_Core_CoreComponentInputSource@@3QBGB@Core@UI@Windows@@UEAAJW4_COREINPUT_TYPE@@W4_COREINPUT_POINTER_TYPE@@KPEAUIUnknown@@PEAUHWND__@@@Z`
- size: `1246`
- prototype: `__int64 __usercall@<rax>(LPVOID lpParam@<rcx>, Windows::UI::Core *, __int64)`
- caller_count: `0`
- callee_count: `22`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x1800038e0`
- `0x180004e00`
- `0x18000c2a0`
- `0x18000c3c4`
- `0x18000c7d4`
- `0x18000e130`
- `0x18000f048`
- `0x18000f118`
- `0x18000f35c`
- `0x180016064`
- `0x18003c7c8`
- `0x180050360`
- `0x1800517a0`
- `0x180056348`
- `0x18006d3e4`
- `0x18006d434`
- `0x18006d484`
- `0x18006e270`
- `0x180071c60`
- `0x180071cbc`
- `0x180071d6c`
- `0x1800ca010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000e5ee`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000e5ee`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000e164`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000e164`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000e1c8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000e1c8`
- `api-ms-win-core-processthreads-l1-1-1!GetProcessMitigationPolicy` at `0x18000e1dc`
- `api-ms-win-core-processthreads-l1-1-1!GetProcessMitigationPolicy` at `0x18000e1dc`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000e477`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000e477`

## string_xrefs

- `0x18000e25c`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\input.cpp`
- `0x18000e2a0`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\input.cpp`
- `0x18000e2ce`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\input.cpp`
- `0x18000e30e`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\input.cpp`
- `0x18000e37a`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\input.cpp`
- `0x18000e19c`: `Windows.UI.Core.CoreComponentInputSource`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::UI::Core::CCoreInput<&unsigned short const near * const RuntimeClass_Windows_UI_Core_CoreComponentInputSource>::RuntimeClassInitialize(
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
  v9 = ++Windows::UI::Core::CCoreInput<&unsigned short const near * const RuntimeClass_Windows_UI_Core_CoreComponentInputSource>::s_instanceCount;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_qDds(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      18,
      (unsigned int)L"Windows.UI.Core.CoreComponentInputSource",
      (_DWORD)lpParam,
      *((_DWORD *)lpParam + 64),
      v9,
      (__int64)L"Windows.UI.Core.CoreComponentInputSource");
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
  NewWindow = Windows::UI::Core::CCoreInput<&unsigned short const near * const RuntimeClass_Windows_UI_Core_CoreComponentInputSource>::CreateNewWindow(lpParam);
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
      InputThreadContext = Windows::UI::Core::CCoreInput<&unsigned short const near * const RuntimeClass_Windows_UI_Core_CoreComponentInputSource>::InitializeComponentInput(
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
      Windows::UI::Core::CCoreInput<&unsigned short const near * const RuntimeClass_Windows_UI_Core_CoreComponentInputSource>::CreateDefaultCursor(lpParam);
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
0x18000e130  mov     [rsp-38h+arg_10], rbx
0x18000e135  push    rbp
0x18000e136  push    rsi
0x18000e137  push    rdi
0x18000e138  push    r12
0x18000e13a  push    r13
0x18000e13c  push    r14
0x18000e13e  push    r15
0x18000e140  mov     rbp, rsp
0x18000e143  sub     rsp, 50h
0x18000e147  mov     r13d, r9d
0x18000e14a  mov     r12d, edx
0x18000e14d  mov     r14, rcx
0x18000e150  mov     [rcx+530h], edx
0x18000e156  mov     [rcx+534h], r8d
0x18000e15d  lea     rcx, ?s_srwCoreInputLock@_InputSinkGlobals@Core@UI@Windows@@2VSRWLock@Wrappers@WRL@Microsoft@@A; SRWLock
0x18000e164  call    cs:__imp_AcquireSRWLockExclusive
0x18000e16a  mov     eax, cs:?s_instanceCount@?$CCoreInput@$1?RuntimeClass_Windows_UI_Core_CoreComponentInputSource@@3QBGB@Core@UI@Windows@@2JA; long Windows::UI::Core::CCoreInput<&ushort const near * const RuntimeClass_Windows_UI_Core_CoreComponentInputSource>::s_instanceCount
0x18000e170  inc     eax
0x18000e172  mov     cs:?s_instanceCount@?$CCoreInput@$1?RuntimeClass_Windows_UI_Core_CoreComponentInputSource@@3QBGB@Core@UI@Windows@@2JA, eax; long Windows::UI::Core::CCoreInput<&ushort const near * const RuntimeClass_Windows_UI_Core_CoreComponentInputSource>::s_instanceCount
0x18000e178  lea     rdx, WPP_GLOBAL_Control
0x18000e17f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e186  cmp     rcx, rdx
0x18000e189  jz      short loc_18000E1C3
0x18000e18b  test    byte ptr [rcx+1Ch], 40h
0x18000e18f  jz      short loc_18000E1C3
0x18000e191  cmp     byte ptr [rcx+19h], 4
0x18000e195  jb      short loc_18000E1C3
0x18000e197  mov     edx, 12h
0x18000e19c  lea     r8, ?RuntimeClass_Windows_UI_Core_CoreComponentInputSource@@3QBGB; "Windows.UI.Core.CoreComponentInputSourc"...
0x18000e1a3  mov     [rsp+50h+var_20], r8
0x18000e1a8  mov     dword ptr [rsp+50h+var_28], eax
0x18000e1ac  mov     eax, [r14+100h]
0x18000e1b3  mov     [rsp+50h+var_30], eax; int
0x18000e1b7  mov     r9, r14
0x18000e1ba  mov     rcx, [rcx+10h]
0x18000e1be  call    WPP_SF_qDds
0x18000e1c3  xor     esi, esi
0x18000e1c5  mov     [rbp+arg_8], esi
0x18000e1c8  call    cs:__imp_GetCurrentProcess
0x18000e1ce  mov     rcx, rax
0x18000e1d1  lea     r9d, [rsi+4]
0x18000e1d5  lea     r8, [rbp+arg_8]
0x18000e1d9  lea     edx, [rsi+0Bh]
0x18000e1dc  call    cs:__imp_GetProcessMitigationPolicy
0x18000e1e2  test    eax, eax
0x18000e1e4  jz      short loc_18000E1F8
0x18000e1e6  mov     eax, [rbp+arg_8]
0x18000e1e9  and     eax, 0Fh
0x18000e1ec  cmp     al, 5
0x18000e1ee  setz    al
0x18000e1f1  mov     [r14+526h], al
0x18000e1f8  mov     rdi, [rbp+arg_20]
0x18000e1fc  mov     [rbp+arg_0], rsi
0x18000e200  test    rdi, rdi
0x18000e203  jz      loc_18000E343
0x18000e209  mov     rax, [rdi]
0x18000e20c  mov     rbx, [rax]
0x18000e20f  lea     rsi, [r14+568h]
0x18000e216  mov     rcx, rsi
0x18000e219  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18000e21e  mov     r8, rsi
0x18000e221  lea     rdx, _GUID_26b79665_54be_4aec_b1b7_c18403ce36ae
0x18000e228  mov     rcx, rdi
0x18000e22b  mov     rax, rbx
0x18000e22e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e233  test    eax, eax
0x18000e235  js      loc_18000E341
0x18000e23b  mov     [rbp+var_8], 0
0x18000e243  lea     rdx, [rbp+var_8]
0x18000e247  mov     rcx, rsi
0x18000e24a  call    ??$As@UICompositionObject@Composition@UI@Windows@@@?$ComPtr@UICompositionIslandPartner@Internal@Composition@UI@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UICompositionObject@Composition@UI@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::UI::Composition::Internal::ICompositionIslandPartner>::As<Windows::UI::Composition::ICompositionObject>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::UI::Composition::ICompositionObject>>)
0x18000e24f  mov     rcx, [rbp+38h]; this
0x18000e253  xor     esi, esi
0x18000e255  test    eax, eax
0x18000e257  jns     short loc_18000E26E
0x18000e259  mov     r9d, eax; char *
0x18000e25c  lea     r8, aOnecoreuapWind_17; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x18000e263  mov     edx, 108h; void *
0x18000e268  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x18000e26e  mov     [rbp+arg_20], rsi
0x18000e272  mov     rdi, [rbp+var_8]
0x18000e276  mov     rax, [rdi]
0x18000e279  mov     rbx, [rax+30h]
0x18000e27d  lea     rcx, [rbp+arg_20]
0x18000e281  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18000e286  lea     rdx, [rbp+arg_20]
0x18000e28a  mov     rcx, rdi
0x18000e28d  mov     rax, rbx
0x18000e290  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e295  mov     rcx, [rbp+38h]; this
0x18000e299  test    eax, eax
0x18000e29b  jns     short loc_18000E2B2
0x18000e29d  mov     r9d, eax; char *
0x18000e2a0  lea     r8, aOnecoreuapWind_17; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x18000e2a7  mov     edx, 10Bh; void *
0x18000e2ac  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x18000e2b2  mov     [rbp+var_10], rsi
0x18000e2b6  lea     rdx, [rbp+var_10]
0x18000e2ba  lea     rcx, [rbp+arg_20]
0x18000e2be  call    ??$As@UICompositorForSystemPartner@Private@Composition@UI@Windows@@@?$ComPtr@UICompositor@Composition@UI@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UICompositorForSystemPartner@Private@Composition@UI@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::UI::Composition::ICompositor>::As<Windows::UI::Composition::Private::ICompositorForSystemPartner>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::UI::Composition::Private::ICompositorForSystemPartner>>)
0x18000e2c3  mov     rcx, [rbp+38h]; this
0x18000e2c7  test    eax, eax
0x18000e2c9  jns     short loc_18000E2E0
0x18000e2cb  mov     r9d, eax; char *
0x18000e2ce  lea     r8, aOnecoreuapWind_17; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x18000e2d5  mov     edx, 10Fh; void *
0x18000e2da  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x18000e2e0  mov     rdi, [rbp+var_10]
0x18000e2e4  mov     rax, [rdi]
0x18000e2e7  mov     rbx, [rax+30h]
0x18000e2eb  lea     rcx, [rbp+arg_0]
0x18000e2ef  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18000e2f4  lea     rdx, [rbp+arg_0]
0x18000e2f8  mov     rcx, rdi
0x18000e2fb  mov     rax, rbx
0x18000e2fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e303  mov     rcx, [rbp+38h]; this
0x18000e307  test    eax, eax
0x18000e309  jns     short loc_18000E320
0x18000e30b  mov     r9d, eax; char *
0x18000e30e  lea     r8, aOnecoreuapWind_17; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x18000e315  mov     edx, 113h; void *
0x18000e31a  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x18000e320  mov     rdi, [rbp+arg_0]
0x18000e324  lea     rcx, [rbp+var_10]
0x18000e328  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18000e32d  lea     rcx, [rbp+arg_20]
0x18000e331  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18000e336  lea     rcx, [rbp+var_8]
0x18000e33a  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18000e33f  jmp     short loc_18000E343
0x18000e341  xor     esi, esi
0x18000e343  mov     [rbp+arg_20], rsi
0x18000e347  lea     rcx, [rbp+arg_20]; struct Windows::UI::Core::ICoreWindow **
0x18000e34b  call    ?GetWindowForThread@WindowServer@Core@UI@Windows@@SAHPEAPEAUICoreWindow@234@@Z; Windows::UI::Core::WindowServer::GetWindowForThread(Windows::UI::Core::ICoreWindow * *)
0x18000e350  test    eax, eax
0x18000e352  jz      short loc_18000E38C
0x18000e354  lea     rbx, [r14+0F8h]
0x18000e35b  mov     rcx, rbx
0x18000e35e  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18000e363  mov     rcx, rbx; struct Windows::UI::Core::CDispatcher **
0x18000e366  call    ?GetDispatcherForThread@CDispatcher@Core@UI@Windows@@SAHPEAPEAV1234@@Z; Windows::UI::Core::CDispatcher::GetDispatcherForThread(Windows::UI::Core::CDispatcher * *)
0x18000e36b  cmp     [rbx], rsi
0x18000e36e  jnz     short loc_18000E38C
0x18000e370  mov     rcx, [rbp+38h]; this
0x18000e374  mov     r9d, 8000FFFFh; char *
0x18000e37a  lea     r8, aOnecoreuapWind_17; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x18000e381  mov     edx, 122h; void *
0x18000e386  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x18000e38c  mov     r15, [rbp+arg_20]
0x18000e390  test    rdi, rdi
0x18000e393  jz      loc_18000E4A3
0x18000e399  mov     [rbp+arg_20], rsi
0x18000e39d  mov     [rbp+var_10], rsi
0x18000e3a1  mov     [rbp+var_8], rdi
0x18000e3a5  lea     rcx, [rbp+var_8]
0x18000e3a9  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x18000e3ae  lea     rdx, [rbp+arg_20]
0x18000e3b2  lea     rcx, [rbp+var_8]
0x18000e3b6  call    ??$As@UICoreWindow@Core@UI@Windows@@@?$ComPtr@UIUnknown@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UICoreWindow@Core@UI@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IUnknown>::As<Windows::UI::Core::ICoreWindow>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::UI::Core::ICoreWindow>>)
0x18000e3bb  lea     rdx, [rbp+var_10]
0x18000e3bf  lea     rcx, [rbp+arg_20]
0x18000e3c3  call    ??$As@UICoreWindowInterop@@@?$ComPtr@UICoreWindow@Core@UI@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UICoreWindowInterop@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::UI::Core::ICoreWindow>::As<ICoreWindowInterop>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<ICoreWindowInterop>>)
0x18000e3c8  mov     rcx, [rbp+var_10]
0x18000e3cc  lea     rdx, [r14+578h]
0x18000e3d3  mov     rax, [rcx]
0x18000e3d6  mov     rax, [rax+18h]
0x18000e3da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e3df  mov     rsi, [rbp+arg_20]
0x18000e3e3  mov     rax, [rsi]
0x18000e3e6  mov     rdi, [rax+48h]
0x18000e3ea  lea     rbx, [r14+550h]
0x18000e3f1  mov     rcx, rbx
0x18000e3f4  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18000e3f9  mov     rdx, rbx
0x18000e3fc  mov     rcx, rsi
0x18000e3ff  mov     rax, rdi
0x18000e402  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e407  xor     esi, esi
0x18000e409  test    r15, r15
0x18000e40c  jz      short loc_18000E47F
0x18000e40e  mov     rbx, [r14+578h]
0x18000e415  mov     rcx, r15; this
0x18000e418  call    ?GetWindowHandle@Core@UI@Windows@@YAPEAUHWND__@@PEAUIInspectable@@@Z; Windows::UI::Core::GetWindowHandle(IInspectable *)
0x18000e41d  cmp     rbx, rax
0x18000e420  jz      short loc_18000E47F
0x18000e422  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e429  lea     rdi, WPP_GLOBAL_Control
0x18000e430  cmp     rcx, rdi
0x18000e433  jz      short loc_18000E470
0x18000e435  test    byte ptr [rcx+1Ch], 40h
0x18000e439  jz      short loc_18000E470
0x18000e43b  cmp     byte ptr [rcx+19h], 2
0x18000e43f  jb      short loc_18000E470
0x18000e441  lea     edx, [rsi+13h]
0x18000e444  mov     [rsp+50h+var_20], r15
0x18000e449  mov     rax, [rbp+arg_20]
0x18000e44d  mov     [rsp+50h+var_28], rax
0x18000e452  mov     eax, [r14+100h]
0x18000e459  mov     [rsp+50h+var_30], eax
0x18000e45d  mov     r9, r14
0x18000e460  lea     r8, WPP_3b510a2a222231b0f6327a10e76445fa_Traceguids
0x18000e467  mov     rcx, [rcx+10h]
0x18000e46b  call    WPP_SF_qDqq
0x18000e470  xor     edx, edx
0x18000e472  mov     ecx, 80070057h
0x18000e477  call    cs:__imp_RoOriginateError
0x18000e47d  jmp     short loc_18000E486
0x18000e47f  lea     rdi, WPP_GLOBAL_Control
0x18000e486  lea     rcx, [rbp+var_8]
0x18000e48a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000e48f  lea     rcx, [rbp+var_10]
0x18000e493  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18000e498  lea     rcx, [rbp+arg_20]
0x18000e49c  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18000e4a1  jmp     short loc_18000E4CD
0x18000e4a3  mov     rax, [rbp+arg_28]
0x18000e4a7  test    rax, rax
0x18000e4aa  jnz     short loc_18000E4BF
0x18000e4ac  cmp     r12d, 1
0x18000e4b0  jnz     short loc_18000E4C6
0x18000e4b2  test    r15, r15
0x18000e4b5  jz      short loc_18000E4C6
0x18000e4b7  mov     rcx, r15; this
0x18000e4ba  call    ?GetWindowHandle@Core@UI@Windows@@YAPEAUHWND__@@PEAUIInspectable@@@Z; Windows::UI::Core::GetWindowHandle(IInspectable *)
0x18000e4bf  mov     [r14+578h], rax
0x18000e4c6  lea     rdi, WPP_GLOBAL_Control
0x18000e4cd  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e4d4  cmp     rcx, rdi
0x18000e4d7  jz      short loc_18000E514
0x18000e4d9  test    byte ptr [rcx+1Ch], 40h
0x18000e4dd  jz      short loc_18000E514
0x18000e4df  cmp     byte ptr [rcx+19h], 4
0x18000e4e3  jb      short loc_18000E514
0x18000e4e5  mov     edx, 14h
0x18000e4ea  mov     rax, [r14+578h]
0x18000e4f1  mov     [rsp+50h+var_28], rax
0x18000e4f6  mov     eax, [r14+100h]
0x18000e4fd  mov     [rsp+50h+var_30], eax
0x18000e501  mov     r9, r14
0x18000e504  lea     r8, WPP_3b510a2a222231b0f6327a10e76445fa_Traceguids
0x18000e50b  mov     rcx, [rcx+10h]
0x18000e50f  call    WPP_SF_qDq
0x18000e514  mov     rcx, r14; lpParam
0x18000e517  call    ?CreateNewWindow@?$CCoreInput@$1?RuntimeClass_Windows_UI_Core_CoreComponentInputSource@@3QBGB@Core@UI@Windows@@IEAAJXZ; Windows::UI::Core::CCoreInput<&ushort const near * const RuntimeClass_Windows_UI_Core_CoreComponentInputSource>::CreateNewWindow(void)
0x18000e51c  mov     ebx, eax
0x18000e51e  test    eax, eax
0x18000e520  js      loc_18000E5AD
0x18000e526  test    r12d, r12d
0x18000e529  jz      short loc_18000E585
0x18000e52b  cmp     r12d, 1
0x18000e52f  jz      short loc_18000E578
0x18000e531  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e538  cmp     rcx, rdi
0x18000e53b  jz      short loc_18000E571
0x18000e53d  test    byte ptr [rcx+1Ch], 40h
0x18000e541  jz      short loc_18000E571
0x18000e543  cmp     byte ptr [rcx+19h], 2
0x18000e547  jb      short loc_18000E571
0x18000e549  mov     edx, 15h
0x18000e54e  mov     dword ptr [rsp+50h+var_28], r12d
0x18000e553  mov     eax, [r14+100h]
0x18000e55a  mov     [rsp+50h+var_30], eax
0x18000e55e  mov     r9, r14
0x18000e561  lea     r8, WPP_3b510a2a222231b0f6327a10e76445fa_Traceguids
0x18000e568  mov     rcx, [rcx+10h]
0x18000e56c  call    WPP_SF_qDD
0x18000e571  mov     ebx, 8000FFFFh
0x18000e576  jmp     short loc_18000E5AD
0x18000e578  mov     rdx, r15
0x18000e57b  mov     rcx, r14
0x18000e57e  call    ?InitializeComponentInput@?$CCoreInput@$1?RuntimeClass_Windows_UI_Core_CoreComponentInputSource@@3QBGB@Core@UI@Windows@@AEAAJPEAUICoreWindow@234@@Z; Windows::UI::Core::CCoreInput<&ushort const near * const RuntimeClass_Windows_UI_Core_CoreComponentInputSource>::InitializeComponentInput(Windows::UI::Core::ICoreWindow *)
0x18000e583  jmp     short loc_18000E593
0x18000e585  xor     r8d, r8d
0x18000e588  mov     rdx, r15
0x18000e58b  mov     rcx, r14
0x18000e58e  call    ?GetOrCreateInputThreadContext@?$CCoreInput@$1?RuntimeClass_Windows_UI_Core_CoreIndependentInputSource@@3QBGB@Core@UI@Windows@@AEAAJPEAUICoreWindow@234@W4_COREINPUT_TYPE@@@Z; Windows::UI::Core::CCoreInput<&ushort const near * const RuntimeClass_Windows_UI_Core_CoreIndependentInputSource>::GetOrCreateInputThreadContext(Windows::UI::Core::ICoreWindow *,_COREINPUT_TYPE)
0x18000e593  mov     ebx, eax
0x18000e595  test    eax, eax
0x18000e597  js      short loc_18000E5AD
0x18000e599  mov     rcx, r14
0x18000e59c  call    ?CreateDefaultCursor@?$CCoreInput@$1?RuntimeClass_Windows_UI_Core_CoreComponentInputSource@@3QBGB@Core@UI@Windows@@IEAAXXZ; Windows::UI::Core::CCoreInput<&ushort const near * const RuntimeClass_Windows_UI_Core_CoreComponentInputSource>::CreateDefaultCursor(void)
0x18000e5a1  mov     rcx, [r14+528h]; this
0x18000e5a8  call    ?SetWindowVisualizationHelper@Core@UI@Windows@@YAXPEAUHWND__@@@Z; Windows::UI::Core::SetWindowVisualizationHelper(HWND__ *)
0x18000e5ad  and     r13b, 1
0x18000e5b1  mov     [r14+521h], r13b
0x18000e5b8  test    r15, r15
0x18000e5bb  jz      short loc_18000E5CD
0x18000e5bd  mov     rax, [r15]
0x18000e5c0  mov     rcx, r15
0x18000e5c3  mov     rax, [rax+10h]
0x18000e5c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e5cc  nop
0x18000e5cd  mov     rcx, [rbp+arg_0]
0x18000e5d1  test    rcx, rcx
0x18000e5d4  jz      short loc_18000E5E7
0x18000e5d6  mov     [rbp+arg_0], rsi
0x18000e5da  mov     rax, [rcx]
0x18000e5dd  mov     rax, [rax+10h]
  ... truncated ...
```
