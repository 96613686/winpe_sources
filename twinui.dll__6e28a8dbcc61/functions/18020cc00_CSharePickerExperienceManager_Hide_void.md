# CSharePickerExperienceManager::Hide(void)

- ea: `0x18020cc00`
- end: `0x18020cdd4`
- name: `?Hide@CSharePickerExperienceManager@@UEAAJXZ`
- size: `468`
- prototype: `__int64 __fastcall(CSharePickerExperienceManager *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18020b25c`

## callees

- `0x180008acc`
- `0x1801052f0`
- `0x18020cc00`
- `0x18020cddc`
- `0x18020cf50`
- `0x180211564`
- `0x180211b50`
- `0x1803a3010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18020cc39`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18020cc5b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18020cc92`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18020cd7a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18020cc39`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18020cc5b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18020cc92`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18020cd7a`
- `USER32!GetLastActivePopup` at `0x18020cd4e`
- `USER32!GetLastActivePopup` at `0x18020cd4e`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetForegroundWindow` at `0x18020cd40`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetForegroundWindow` at `0x18020cd57`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetForegroundWindow` at `0x18020cd40`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetForegroundWindow` at `0x18020cd57`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetForegroundWindow` at `0x18020cd2c`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetForegroundWindow` at `0x18020cd2c`

## string_xrefs

- `0x18020cc6d`: `%S(%d) No frame exists, setting state to Destroyed without transitioning through Hiding. ThreadId=%u`
- `0x18020cc45`: `%S(%d) Already in Hiding state, skipping re-entrant Hide(). ThreadId=%u`
- `0x18020cd86`: `%S(%d) No frame to hide. ThreadId=%u`
- `0x18020cca4`: `%S(%d) State set to Hiding by Hide() method (likely called from Destroy()). ThreadId=%u`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSharePickerExperienceManager::Hide(HWND *this)
{
  DWORD CurrentThreadId; // eax
  DWORD v3; // eax
  DWORD v4; // eax
  HWND v5; // rdi
  __int64 (__fastcall *v6)(HWND, __int64 *); // rbx
  int v7; // eax
  int v8; // eax
  HWND LastActivePopup; // rax
  DWORD v10; // eax
  int v12; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  __int64 v14; // [rsp+38h] [rbp+10h] BYREF
  HWND v15; // [rsp+40h] [rbp+18h] BYREF

  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_IVCFTest>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_IVCFTest>::GetImpl'::`2'::impl) )
  {
    if ( CSharePickerExperienceManager::IsDestroyInProgress((CSharePickerExperienceManager *)this) )
    {
      CurrentThreadId = GetCurrentThreadId();
      NearbyShareUXTraceLogging::TraceLoggingInfo(
        "%S(%d) Already in Hiding state, skipping re-entrant Hide(). ThreadId=%u",
        "CSharePickerExperienceManager::Hide",
        705,
        CurrentThreadId);
      return 0;
    }
    if ( !this[82] )
    {
      v3 = GetCurrentThreadId();
      NearbyShareUXTraceLogging::TraceLoggingInfo(
        "%S(%d) No frame exists, setting state to Destroyed without transitioning through Hiding. ThreadId=%u",
        (const wchar_t *)"CSharePickerExperienceManager::Hide",
        712,
        v3);
      *((_DWORD *)this + 171) = 4;
      return 0;
    }
    *((_DWORD *)this + 171) = 3;
    v4 = GetCurrentThreadId();
    NearbyShareUXTraceLogging::TraceLoggingInfo(
      "%S(%d) State set to Hiding by Hide() method (likely called from Destroy()). ThreadId=%u",
      (const wchar_t *)"CSharePickerExperienceManager::Hide",
      717,
      v4);
  }
  if ( this[82] )
  {
    CSharePickerExperienceManager::HideInternal((CSharePickerExperienceManager *)this);
    v14 = 0;
    v5 = this[82];
    v6 = *(__int64 (__fastcall **)(HWND, __int64 *))(*(_QWORD *)v5 + 32LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v14);
    v7 = v6(v5, &v14);
    if ( v7 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x2D4,
        (unsigned int)"shell\\twinui\\experiencemanagers\\lib\\sharepickerexperiencemanager.cpp",
        (const char *)(unsigned int)v7,
        v12);
    v15 = 0;
    v8 = (*(__int64 (__fastcall **)(__int64, HWND *))(*(_QWORD *)v14 + 24LL))(v14, &v15);
    if ( v8 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x2D6,
        (unsigned int)"shell\\twinui\\experiencemanagers\\lib\\sharepickerexperiencemanager.cpp",
        (const char *)(unsigned int)v8,
        v12);
    if ( GetForegroundWindow() == v15 && !SetForegroundWindow(this[103]) )
    {
      LastActivePopup = GetLastActivePopup(this[12]);
      SetForegroundWindow(LastActivePopup);
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v14);
  }
  else if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_IVCFTest>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_IVCFTest>::GetImpl'::`2'::impl) )
  {
    v10 = GetCurrentThreadId();
    NearbyShareUXTraceLogging::TraceLoggingInfo(
      "%S(%d) No frame to hide. ThreadId=%u",
      "CSharePickerExperienceManager::Hide",
      740,
      v10);
  }
  return 0;
}

```

## disassembly

```asm
0x18020cc00  mov     [rsp+arg_0], rbx
0x18020cc05  mov     [rsp+arg_18], rsi
0x18020cc0a  push    rdi; int
0x18020cc0b  sub     rsp, 20h
0x18020cc0f  mov     rsi, rcx
0x18020cc12  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_IVCFTest@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_IVCFTest@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_IVCFTest> `wil::Feature<__WilFeatureTraits_Feature_IVCFTest>::GetImpl(void)'::`2'::impl
0x18020cc19  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_IVCFTest@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_IVCFTest>::__private_IsEnabled(void)
0x18020cc1e  lea     rbx, aCsharepickerex_11; "CSharePickerExperienceManager::Hide"
0x18020cc25  test    al, al
0x18020cc27  jz      loc_18020CCB0
0x18020cc2d  mov     rcx, rsi; this
0x18020cc30  call    ?IsDestroyInProgress@CSharePickerExperienceManager@@AEBA_NXZ; CSharePickerExperienceManager::IsDestroyInProgress(void)
0x18020cc35  test    al, al
0x18020cc37  jz      short loc_18020CC51
0x18020cc39  call    cs:__imp_GetCurrentThreadId
0x18020cc3f  mov     r8d, 2C1h
0x18020cc45  lea     rcx, aSDAlreadyInHid; "%S(%d) Already in Hiding state, skippin"...
0x18020cc4c  jmp     loc_18020CD8D
0x18020cc51  cmp     qword ptr [rsi+290h], 0
0x18020cc59  jnz     short loc_18020CC88
0x18020cc5b  call    cs:__imp_GetCurrentThreadId
0x18020cc61  mov     r9d, eax
0x18020cc64  mov     r8d, 2C8h
0x18020cc6a  mov     rdx, rbx
0x18020cc6d  lea     rcx, aSDNoFrameExist; "%S(%d) No frame exists, setting state t"...
0x18020cc74  call    ?TraceLoggingInfo@NearbyShareUXTraceLogging@@SAXPEBDZZ; NearbyShareUXTraceLogging::TraceLoggingInfo(char const *,...)
0x18020cc79  mov     dword ptr [rsi+2ACh], 4
0x18020cc83  jmp     loc_18020CD98
0x18020cc88  mov     dword ptr [rsi+2ACh], 3
0x18020cc92  call    cs:__imp_GetCurrentThreadId
0x18020cc98  mov     r9d, eax
0x18020cc9b  mov     r8d, 2CDh
0x18020cca1  mov     rdx, rbx
0x18020cca4  lea     rcx, aSDStateSetToHi_0; "%S(%d) State set to Hiding by Hide() me"...
0x18020ccab  call    ?TraceLoggingInfo@NearbyShareUXTraceLogging@@SAXPEBDZZ; NearbyShareUXTraceLogging::TraceLoggingInfo(char const *,...)
0x18020ccb0  cmp     qword ptr [rsi+290h], 0
0x18020ccb8  jz      loc_18020CD6A
0x18020ccbe  mov     rcx, rsi; this
0x18020ccc1  call    ?HideInternal@CSharePickerExperienceManager@@AEAAJXZ; CSharePickerExperienceManager::HideInternal(void)
0x18020ccc6  mov     [rsp+28h+arg_8], 0
0x18020cccf  mov     rdi, [rsi+290h]
0x18020ccd6  mov     rax, [rdi]
0x18020ccd9  mov     rbx, [rax+20h]
0x18020ccdd  lea     rcx, [rsp+28h+arg_8]
0x18020cce2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18020cce7  lea     rdx, [rsp+28h+arg_8]
0x18020ccec  mov     rcx, rdi
0x18020ccef  mov     rax, rbx
0x18020ccf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18020ccf7  mov     rcx, [rsp+28h]; this
0x18020ccfc  test    eax, eax
0x18020ccfe  js      loc_18020CDBF
0x18020cd04  mov     [rsp+28h+arg_10], 0
0x18020cd0d  mov     rcx, [rsp+28h+arg_8]
0x18020cd12  mov     rax, [rcx]
0x18020cd15  lea     rdx, [rsp+28h+arg_10]
0x18020cd1a  mov     rax, [rax+18h]
0x18020cd1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18020cd23  mov     rcx, [rsp+28h]; this
0x18020cd28  test    eax, eax
0x18020cd2a  js      short loc_18020CDAA
0x18020cd2c  call    cs:__imp_GetForegroundWindow
0x18020cd32  cmp     rax, [rsp+28h+arg_10]
0x18020cd37  jnz     short loc_18020CD5E
0x18020cd39  mov     rcx, [rsi+338h]; hWnd
0x18020cd40  call    cs:__imp_SetForegroundWindow
0x18020cd46  test    eax, eax
0x18020cd48  jnz     short loc_18020CD5E
0x18020cd4a  mov     rcx, [rsi+60h]; hWnd
0x18020cd4e  call    cs:__imp_GetLastActivePopup
0x18020cd54  mov     rcx, rax; hWnd
0x18020cd57  call    cs:__imp_SetForegroundWindow
0x18020cd5d  nop
0x18020cd5e  lea     rcx, [rsp+28h+arg_8]
0x18020cd63  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18020cd68  jmp     short loc_18020CD98
0x18020cd6a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_IVCFTest@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_IVCFTest@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_IVCFTest> `wil::Feature<__WilFeatureTraits_Feature_IVCFTest>::GetImpl(void)'::`2'::impl
0x18020cd71  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_IVCFTest@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_IVCFTest>::__private_IsEnabled(void)
0x18020cd76  test    al, al
0x18020cd78  jz      short loc_18020CD98
0x18020cd7a  call    cs:__imp_GetCurrentThreadId
0x18020cd80  mov     r8d, 2E4h
0x18020cd86  lea     rcx, aSDNoFrameToHid; "%S(%d) No frame to hide. ThreadId=%u"
0x18020cd8d  mov     r9d, eax
0x18020cd90  mov     rdx, rbx
0x18020cd93  call    ?TraceLoggingInfo@NearbyShareUXTraceLogging@@SAXPEBDZZ; NearbyShareUXTraceLogging::TraceLoggingInfo(char const *,...)
0x18020cd98  xor     eax, eax
0x18020cd9a  mov     rbx, [rsp+28h+arg_0]
0x18020cd9f  mov     rsi, [rsp+28h+arg_18]
0x18020cda4  add     rsp, 20h
0x18020cda8  pop     rdi
0x18020cda9  retn
0x18020cdaa  mov     r9d, eax; char *
0x18020cdad  lea     r8, aShellTwinuiExp_4; "shell\\twinui\\experiencemanagers\\lib"...
0x18020cdb4  mov     edx, 2D6h; void *
0x18020cdb9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18020cdbf  mov     r9d, eax; char *
0x18020cdc2  lea     r8, aShellTwinuiExp_4; "shell\\twinui\\experiencemanagers\\lib"...
0x18020cdc9  mov     edx, 2D4h; void *
0x18020cdce  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
