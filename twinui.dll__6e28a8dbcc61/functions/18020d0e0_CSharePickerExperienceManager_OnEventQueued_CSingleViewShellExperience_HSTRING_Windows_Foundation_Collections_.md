# CSharePickerExperienceManager::OnEventQueued(CSingleViewShellExperience *,HSTRING__ *,Windows::Foundation::Collections::IPropertySet *)

- ea: `0x18020d0e0`
- end: `0x18020d66b`
- name: `?OnEventQueued@CSharePickerExperienceManager@@MEAAJPEAVCSingleViewShellExperience@@PEAUHSTRING__@@PEAUIPropertySet@Collections@Foundation@Windows@@@Z`
- size: `1419`
- prototype: `int(CSharePickerExperienceManager *__hidden this, struct CSingleViewShellExperience *, HSTRING, struct Windows::Foundation::Collections::IPropertySet *)`
- caller_count: `0`
- callee_count: `21`
- tags: `broker_com_uri`

## callees

- `0x180008acc`
- `0x18000cf94`
- `0x18000d348`
- `0x18003c5e4`
- `0x180052980`
- `0x18006d698`
- `0x1800f96d4`
- `0x18012e758`
- `0x18013d330`
- `0x1801fbc04`
- `0x180209b20`
- `0x18020a038`
- `0x18020a670`
- `0x18020a6e0`
- `0x18020ac5c`
- `0x18020d0e0`
- `0x18020f5fc`
- `0x18020f944`
- `0x1802115b0`
- `0x180211b10`
- `0x180212604`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x18020d34e`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x18020d34e`
- `USER32!GetLastActivePopup` at `0x18020d18a`
- `USER32!GetLastActivePopup` at `0x18020d18a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18020d1dc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18020d235`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18020d2d6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18020d369`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18020d1dc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18020d235`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18020d2d6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18020d369`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18020d261`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18020d345`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18020d261`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18020d345`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetForegroundWindow` at `0x18020d193`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetForegroundWindow` at `0x18020d193`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetWindowTextW` at `0x18020d26d`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetWindowTextW` at `0x18020d26d`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CSharePickerExperienceManager::OnEventQueued(
        HWND *this,
        ExperienceManagerUtils **a2,
        Microsoft::WRL::Wrappers::Details *a3,
        struct Windows::Foundation::Collections::IPropertySet *a4)
{
  __int64 v8; // rax
  HSTRING v9; // r8
  int PropVal; // ebx
  __int64 v11; // rdx
  __int64 v13; // rax
  HSTRING v14; // r8
  HWND LastActivePopup; // rax
  __int64 v16; // rax
  HSTRING v17; // r8
  __int64 v18; // rax
  int v19; // eax
  HSTRING v20; // r8
  struct Windows::Internal::Shell::ViewManagerInterop::IViewWrapper *v21; // rdx
  HWND v22; // rbx
  const WCHAR *v23; // rax
  const char *v24; // r9
  __int64 v25; // rax
  HSTRING v26; // r8
  __int64 v27; // rax
  int v28; // eax
  HSTRING v29; // r8
  PCWSTR StringRawBuffer; // rax
  __int64 v31; // rax
  HSTRING v32; // r8
  __int64 v33; // rax
  HSTRING v34; // r8
  __int64 v35; // rax
  HSTRING v36; // r8
  HSTRING v37; // rbx
  int v38; // eax
  unsigned __int64 v39; // r9
  __int64 v40; // rdx
  int v41; // eax
  HSTRING v42; // rbx
  int v43; // eax
  int v44; // eax
  HSTRING string; // [rsp+20h] [rbp-69h] BYREF
  struct Windows::Foundation::IPropertyValue *v46; // [rsp+28h] [rbp-61h] BYREF
  _QWORD v47[2]; // [rsp+30h] [rbp-59h] BYREF
  _BYTE v48[56]; // [rsp+40h] [rbp-49h] BYREF
  __int64 v49; // [rsp+78h] [rbp-11h] BYREF
  _BYTE v50[32]; // [rsp+80h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  v8 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v50, off_1803E1A78);
  if ( (unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(a3, *(HSTRING *)(v8 + 24), v9) )
  {
    v13 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v50, off_1803E1A68);
    if ( !(unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(a3, *(HSTRING *)(v13 + 24), v14) )
    {
      LastActivePopup = GetLastActivePopup(this[5]);
      SetForegroundWindow(LastActivePopup);
      goto LABEL_22;
    }
    v16 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v50, off_1803E1A60);
    if ( (unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(a3, *(HSTRING *)(v16 + 24), v17) )
    {
      v25 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v50, off_1803E1A50);
      if ( (unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(a3, *(HSTRING *)(v25 + 24), v26) )
        goto LABEL_22;
      v46 = a4;
      Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v46);
      WindowsDeleteString(0);
      string = 0;
      v27 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v50, off_1803E1A48);
      v28 = Windows::Internal::ShellHelpers::PropertySetHelper::GetValue<HSTRING__ *>(
              (Windows::Internal::ShellHelpers::PropertySetHelper *)&v46,
              *(HSTRING *)(v27 + 24));
      PropVal = v28;
      if ( v28 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x3A4,
          (unsigned int)"shell\\twinui\\experiencemanagers\\lib\\sharepickerexperiencemanager.cpp",
          (const char *)(unsigned int)v28,
          (int)string);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
        goto LABEL_11;
      }
      if ( (unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(
                           (Microsoft::WRL::Wrappers::Details *)string,
                           0,
                           v29) )
      {
        StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
        this[5] = (HWND)(int)_o__wtoi(StringRawBuffer);
      }
    }
    else
    {
      v46 = a4;
      Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v46);
      WindowsDeleteString(0);
      string = 0;
      v18 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v50, off_1803E1A58);
      v19 = Windows::Internal::ShellHelpers::PropertySetHelper::GetValue<HSTRING__ *>(
              (Windows::Internal::ShellHelpers::PropertySetHelper *)&v46,
              *(HSTRING *)(v18 + 24));
      PropVal = v19;
      if ( v19 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x399,
          (unsigned int)"shell\\twinui\\experiencemanagers\\lib\\sharepickerexperiencemanager.cpp",
          (const char *)(unsigned int)v19,
          (int)string);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
LABEL_11:
        WindowsDeleteString(string);
        return (unsigned int)PropVal;
      }
      if ( (unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(
                           (Microsoft::WRL::Wrappers::Details *)string,
                           0,
                           v20) )
      {
        v22 = ExperienceManagerUtils::WindowFromViewWrapper(a2[3], v21);
        v23 = WindowsGetStringRawBuffer(string, 0);
        if ( !SetWindowTextW(v22, v23) )
          wil::details::in1diag3::_Log_GetLastError(
            retaddr,
            (void *)0x39D,
            (unsigned int)"shell\\twinui\\experiencemanagers\\lib\\sharepickerexperiencemanager.cpp",
            v24);
      }
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
    WindowsDeleteString(string);
    goto LABEL_22;
  }
  PropVal = CSharePickerExperienceManager::TryDismissShareExperience((CSharePickerExperienceManager *)(this - 7));
  if ( PropVal < 0 )
  {
    v11 = 911;
LABEL_4:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"shell\\twinui\\experiencemanagers\\lib\\sharepickerexperiencemanager.cpp",
      (const char *)(unsigned int)PropVal,
      (int)string);
    return (unsigned int)PropVal;
  }
LABEL_22:
  v31 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v50, off_1803E1A70);
  if ( !(unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(a3, *(HSTRING *)(v31 + 24), v32) )
  {
    PropVal = CSharePickerExperienceManager::TryDismissShareExperience((CSharePickerExperienceManager *)(this - 7));
    if ( PropVal < 0 )
    {
      v11 = 941;
      goto LABEL_4;
    }
  }
  v33 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v50, off_1803E1A30);
  if ( (unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(a3, *(HSTRING *)(v33 + 24), v34) )
  {
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CAI>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CAI>::GetImpl'::`2'::impl) )
      return 0;
    v35 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v50, off_1803E1A20);
    if ( (unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(a3, *(HSTRING *)(v35 + 24), v36) )
      return 0;
    tip2::start_and_watch_errors<tip2::tip_test<tip2::details::merged_data<_tip_ShareSheetResizeTest,_tip_ShareSheetResizeTest>>>((struct wil::details::IFailureCallback *)v48);
    if ( (unsigned __int8)tip2::details::shared_data<1,0,0>::is_running(v49 + 8) )
    {
      tip2::test_data_control<tip2::details::merged_data<_tip_ShareSheetResizeTest,_tip_ShareSheetResizeTest>>::test_data_control<tip2::details::merged_data<_tip_ShareSheetResizeTest,_tip_ShareSheetResizeTest>>(
        &v46,
        &v49);
      *((_BYTE *)v46 + 272) = 1;
      tip2::test_data_control<tip2::details::merged_data<_tip_ShareSheetResizeTest,_tip_ShareSheetResizeTest>>::~test_data_control<tip2::details::merged_data<_tip_ShareSheetResizeTest,_tip_ShareSheetResizeTest>>(&v46);
    }
    v47[0] = 0;
    string = (HSTRING)a4;
    Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&string);
    v37 = *(HSTRING *)(Microsoft::WRL::Wrappers::HStringReference::HStringReference(v50, off_1803E1A28) + 24);
    v47[0] = 0;
    v46 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
    PropVal = Windows::Internal::ShellHelpers::PropertySetHelper::GetPropVal(
                (Windows::Internal::ShellHelpers::PropertySetHelper *)&string,
                v37,
                &v46);
    if ( PropVal >= 0 )
    {
      v38 =  Windows::Foundation::IPropertyValue::`vcall'{192,{flat}}(v46, v47);
      PropVal = v38;
      if ( v38 >= 0 )
        PropVal = 0;
      else
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2F,
          (unsigned int)"onecore\\internal\\shell\\inc\\PropertySetHelpers.h",
          (const char *)(unsigned int)v38,
          (int)string);
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
    if ( PropVal < 0 )
    {
      v39 = (unsigned int)PropVal;
      v40 = 967;
LABEL_49:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v40,
        (unsigned int)"shell\\twinui\\experiencemanagers\\lib\\sharepickerexperiencemanager.cpp",
        (const char *)v39,
        (int)string);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&string);
      tip2::test_watcher<tip2::details::merged_data<_tip_ShareSheetResizeTest,_tip_ShareSheetResizeTest>>::~test_watcher<tip2::details::merged_data<_tip_ShareSheetResizeTest,_tip_ShareSheetResizeTest>>(v48);
      return (unsigned int)PropVal;
    }
    v41 = CSharePickerExperienceManager::ResizeWindowWithScaling(this - 7, v47[0]);
    PropVal = v41;
    if ( v41 < 0 )
    {
      v39 = (unsigned int)v41;
      v40 = 968;
      goto LABEL_49;
    }
  }
  else
  {
    tip2::start_and_watch_errors<tip2::tip_test<tip2::details::merged_data<_tip_ShareSheetResizeTest,_tip_ShareSheetResizeTest>>>((struct wil::details::IFailureCallback *)v48);
    if ( (unsigned __int8)tip2::details::shared_data<1,0,0>::is_running(v49 + 8) )
    {
      tip2::test_data_control<tip2::details::merged_data<_tip_ShareSheetResizeTest,_tip_ShareSheetResizeTest>>::test_data_control<tip2::details::merged_data<_tip_ShareSheetResizeTest,_tip_ShareSheetResizeTest>>(
        &v46,
        &v49);
      *((_BYTE *)v46 + 272) = 1;
      tip2::test_data_control<tip2::details::merged_data<_tip_ShareSheetResizeTest,_tip_ShareSheetResizeTest>>::~test_data_control<tip2::details::merged_data<_tip_ShareSheetResizeTest,_tip_ShareSheetResizeTest>>(&v46);
    }
    v47[0] = 0;
    string = (HSTRING)a4;
    Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&string);
    v42 = *(HSTRING *)(Microsoft::WRL::Wrappers::HStringReference::HStringReference(v50, off_1803E1A28) + 24);
    v47[0] = 0;
    v46 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
    PropVal = Windows::Internal::ShellHelpers::PropertySetHelper::GetPropVal(
                (Windows::Internal::ShellHelpers::PropertySetHelper *)&string,
                v42,
                &v46);
    if ( PropVal >= 0 )
    {
      v43 =  Windows::Foundation::IPropertyValue::`vcall'{192,{flat}}(v46, v47);
      PropVal = v43;
      if ( v43 >= 0 )
        PropVal = 0;
      else
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2F,
          (unsigned int)"onecore\\internal\\shell\\inc\\PropertySetHelpers.h",
          (const char *)(unsigned int)v43,
          (int)string);
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
    if ( PropVal < 0 )
    {
      v39 = (unsigned int)PropVal;
      v40 = 953;
      goto LABEL_49;
    }
    v44 = CSharePickerExperienceManager::ResizeWindow(this - 7, v47[0]);
    PropVal = v44;
    if ( v44 < 0 )
    {
      v39 = (unsigned int)v44;
      v40 = 954;
      goto LABEL_49;
    }
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&string);
  tip2::test_watcher<tip2::details::merged_data<_tip_ShareSheetResizeTest,_tip_ShareSheetResizeTest>>::~test_watcher<tip2::details::merged_data<_tip_ShareSheetResizeTest,_tip_ShareSheetResizeTest>>(v48);
  return 0;
}

```

## disassembly

```asm
0x18020d0e0  push    rbp
0x18020d0e2  push    rbx
0x18020d0e3  push    rsi
0x18020d0e4  push    rdi
0x18020d0e5  push    r13
0x18020d0e7  push    r14
0x18020d0e9  push    r15
0x18020d0eb  lea     rbp, [rsp-27h]
0x18020d0f0  sub     rsp, 0B0h
0x18020d0f7  mov     rax, cs:__security_cookie
0x18020d0fe  xor     rax, rsp
0x18020d101  mov     [rbp+57h+var_40], rax
0x18020d105  mov     r15, r9
0x18020d108  mov     rsi, r8
0x18020d10b  mov     r14, rdx
0x18020d10e  mov     rdi, rcx
0x18020d111  lea     rdx, off_1803E1A78; "DestroyPicker"
0x18020d118  lea     rcx, [rbp+57h+var_60]
0x18020d11c  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18020d121  mov     rdx, [rax+18h]; HSTRING
0x18020d125  mov     rcx, rsi; this
0x18020d128  call    ?CompareStringOrdinal@Details@Wrappers@WRL@Microsoft@@YAHPEAUHSTRING__@@0@Z; Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(HSTRING__ *,HSTRING__ *)
0x18020d12d  lea     r13, aShellTwinuiExp_4; "shell\\twinui\\experiencemanagers\\lib"...
0x18020d134  test    eax, eax
0x18020d136  jnz     short loc_18020D166
0x18020d138  lea     rcx, [rdi-38h]; this
0x18020d13c  call    ?TryDismissShareExperience@CSharePickerExperienceManager@@AEAAJXZ; CSharePickerExperienceManager::TryDismissShareExperience(void)
0x18020d141  mov     ebx, eax
0x18020d143  test    eax, eax
0x18020d145  jns     loc_18020D36F
0x18020d14b  mov     edx, 38Fh; void *
0x18020d150  mov     r8, r13; unsigned int
0x18020d153  mov     r9d, ebx; char *
0x18020d156  mov     rcx, [rbp+5Fh]; this
0x18020d15a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18020d15f  mov     eax, ebx
0x18020d161  jmp     loc_18020D64D
0x18020d166  lea     rdx, off_1803E1A68; "SetSourceAppAsForegroundWindow"
0x18020d16d  lea     rcx, [rbp+57h+var_60]
0x18020d171  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18020d176  mov     rdx, [rax+18h]; HSTRING
0x18020d17a  mov     rcx, rsi; this
0x18020d17d  call    ?CompareStringOrdinal@Details@Wrappers@WRL@Microsoft@@YAHPEAUHSTRING__@@0@Z; Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(HSTRING__ *,HSTRING__ *)
0x18020d182  test    eax, eax
0x18020d184  jnz     short loc_18020D19E
0x18020d186  mov     rcx, [rdi+28h]; hWnd
0x18020d18a  call    cs:__imp_GetLastActivePopup
0x18020d190  mov     rcx, rax; hWnd
0x18020d193  call    cs:__imp_SetForegroundWindow
0x18020d199  jmp     loc_18020D36F
0x18020d19e  lea     rdx, off_1803E1A60; "SharePickerExperienceWindowTitle"
0x18020d1a5  lea     rcx, [rbp+57h+var_60]
0x18020d1a9  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18020d1ae  mov     rdx, [rax+18h]; HSTRING
0x18020d1b2  mov     rcx, rsi; this
0x18020d1b5  call    ?CompareStringOrdinal@Details@Wrappers@WRL@Microsoft@@YAHPEAUHSTRING__@@0@Z; Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(HSTRING__ *,HSTRING__ *)
0x18020d1ba  test    eax, eax
0x18020d1bc  jnz     loc_18020D298
0x18020d1c2  mov     [rbp+57h+string], 0
0x18020d1ca  mov     [rbp+57h+var_B8], r15
0x18020d1ce  lea     rcx, [rbp+57h+var_B8]
0x18020d1d2  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x18020d1d7  nop
0x18020d1d8  mov     rcx, [rbp+57h+string]; string
0x18020d1dc  call    cs:__imp_WindowsDeleteString
0x18020d1e2  mov     [rbp+57h+string], 0
0x18020d1ea  lea     rdx, off_1803E1A58; "TitleParam"
0x18020d1f1  lea     rcx, [rbp+57h+var_60]
0x18020d1f5  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18020d1fa  nop
0x18020d1fb  lea     r9, [rbp+57h+string]
0x18020d1ff  mov     rdx, [rax+18h]; HSTRING
0x18020d203  lea     rcx, [rbp+57h+var_B8]; this
0x18020d207  call    ??$GetValue@PEAUHSTRING__@@@PropertySetHelper@ShellHelpers@Internal@Windows@@AEAAJPEAUHSTRING__@@P8IPropertyValue@Foundation@3@EAAJPEAPEAU4@@Z1@Z; Windows::Internal::ShellHelpers::PropertySetHelper::GetValue<HSTRING__ *>(HSTRING__ *,long (Windows::Foundation::IPropertyValue::*)(HSTRING__ * *),HSTRING__ * *)
0x18020d20c  mov     ebx, eax
0x18020d20e  test    eax, eax
0x18020d210  jns     short loc_18020D240
0x18020d212  mov     rcx, [rbp+5Fh]; this
0x18020d216  mov     r9d, eax; char *
0x18020d219  mov     r8, r13; unsigned int
0x18020d21c  mov     edx, 399h; void *
0x18020d221  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18020d226  nop
0x18020d227  lea     rcx, [rbp+57h+var_B8]
0x18020d22b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18020d230  nop
0x18020d231  mov     rcx, [rbp+57h+string]; string
0x18020d235  call    cs:__imp_WindowsDeleteString
0x18020d23b  jmp     loc_18020D15F
0x18020d240  xor     edx, edx; HSTRING
0x18020d242  mov     rcx, [rbp+57h+string]; this
0x18020d246  call    ?CompareStringOrdinal@Details@Wrappers@WRL@Microsoft@@YAHPEAUHSTRING__@@0@Z; Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(HSTRING__ *,HSTRING__ *)
0x18020d24b  test    eax, eax
0x18020d24d  jz      short loc_18020D289
0x18020d24f  mov     rcx, [r14+18h]; this
0x18020d253  call    ?WindowFromViewWrapper@ExperienceManagerUtils@@YAPEAUHWND__@@PEAUIViewWrapper@ViewManagerInterop@Shell@Internal@Windows@@@Z; ExperienceManagerUtils::WindowFromViewWrapper(Windows::Internal::Shell::ViewManagerInterop::IViewWrapper *)
0x18020d258  mov     rbx, rax
0x18020d25b  xor     edx, edx; length
0x18020d25d  mov     rcx, [rbp+57h+string]; string
0x18020d261  call    cs:__imp_WindowsGetStringRawBuffer
0x18020d267  mov     rdx, rax; lpString
0x18020d26a  mov     rcx, rbx; hWnd
0x18020d26d  call    cs:__imp_SetWindowTextW
0x18020d273  mov     rcx, [rbp+5Fh]; this
0x18020d277  test    eax, eax
0x18020d279  jnz     short loc_18020D289
0x18020d27b  mov     r8, r13; unsigned int
0x18020d27e  mov     edx, 39Dh; void *
0x18020d283  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x18020d288  nop
0x18020d289  lea     rcx, [rbp+57h+var_B8]
0x18020d28d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18020d292  nop
0x18020d293  jmp     loc_18020D365
0x18020d298  lea     rdx, off_1803E1A50; "UpdateParentWindow"
0x18020d29f  lea     rcx, [rbp+57h+var_60]
0x18020d2a3  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18020d2a8  mov     rdx, [rax+18h]; HSTRING
0x18020d2ac  mov     rcx, rsi; this
0x18020d2af  call    ?CompareStringOrdinal@Details@Wrappers@WRL@Microsoft@@YAHPEAUHSTRING__@@0@Z; Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(HSTRING__ *,HSTRING__ *)
0x18020d2b4  test    eax, eax
0x18020d2b6  jnz     loc_18020D36F
0x18020d2bc  mov     [rbp+57h+string], 0
0x18020d2c4  mov     [rbp+57h+var_B8], r15
0x18020d2c8  lea     rcx, [rbp+57h+var_B8]
0x18020d2cc  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x18020d2d1  nop
0x18020d2d2  mov     rcx, [rbp+57h+string]; string
0x18020d2d6  call    cs:__imp_WindowsDeleteString
0x18020d2dc  mov     [rbp+57h+string], 0
0x18020d2e4  lea     rdx, off_1803E1A48; "ParentWindowId"
0x18020d2eb  lea     rcx, [rbp+57h+var_60]
0x18020d2ef  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18020d2f4  nop
0x18020d2f5  lea     r9, [rbp+57h+string]
0x18020d2f9  mov     rdx, [rax+18h]; HSTRING
0x18020d2fd  lea     rcx, [rbp+57h+var_B8]; this
0x18020d301  call    ??$GetValue@PEAUHSTRING__@@@PropertySetHelper@ShellHelpers@Internal@Windows@@AEAAJPEAUHSTRING__@@P8IPropertyValue@Foundation@3@EAAJPEAPEAU4@@Z1@Z; Windows::Internal::ShellHelpers::PropertySetHelper::GetValue<HSTRING__ *>(HSTRING__ *,long (Windows::Foundation::IPropertyValue::*)(HSTRING__ * *),HSTRING__ * *)
0x18020d306  mov     ebx, eax
0x18020d308  test    eax, eax
0x18020d30a  jns     short loc_18020D330
0x18020d30c  mov     rcx, [rbp+5Fh]; this
0x18020d310  mov     r9d, eax; char *
0x18020d313  mov     r8, r13; unsigned int
0x18020d316  mov     edx, 3A4h; void *
0x18020d31b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18020d320  nop
0x18020d321  lea     rcx, [rbp+57h+var_B8]
0x18020d325  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18020d32a  nop
0x18020d32b  jmp     loc_18020D231
0x18020d330  xor     edx, edx; HSTRING
0x18020d332  mov     rcx, [rbp+57h+string]; this
0x18020d336  call    ?CompareStringOrdinal@Details@Wrappers@WRL@Microsoft@@YAHPEAUHSTRING__@@0@Z; Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(HSTRING__ *,HSTRING__ *)
0x18020d33b  test    eax, eax
0x18020d33d  jz      short loc_18020D35B
0x18020d33f  xor     edx, edx; length
0x18020d341  mov     rcx, [rbp+57h+string]; string
0x18020d345  call    cs:__imp_WindowsGetStringRawBuffer
0x18020d34b  mov     rcx, rax
0x18020d34e  call    cs:__imp__o__wtoi
0x18020d354  movsxd  rcx, eax
0x18020d357  mov     [rdi+28h], rcx
0x18020d35b  lea     rcx, [rbp+57h+var_B8]
0x18020d35f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18020d364  nop
0x18020d365  mov     rcx, [rbp+57h+string]; string
0x18020d369  call    cs:__imp_WindowsDeleteString
0x18020d36f  lea     rdx, off_1803E1A70; "DestroyFrame"
0x18020d376  lea     rcx, [rbp+57h+var_60]
0x18020d37a  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18020d37f  mov     rdx, [rax+18h]; HSTRING
0x18020d383  mov     rcx, rsi; this
0x18020d386  call    ?CompareStringOrdinal@Details@Wrappers@WRL@Microsoft@@YAHPEAUHSTRING__@@0@Z; Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(HSTRING__ *,HSTRING__ *)
0x18020d38b  test    eax, eax
0x18020d38d  jnz     short loc_18020D3A8
0x18020d38f  lea     rcx, [rdi-38h]; this
0x18020d393  call    ?TryDismissShareExperience@CSharePickerExperienceManager@@AEAAJXZ; CSharePickerExperienceManager::TryDismissShareExperience(void)
0x18020d398  mov     ebx, eax
0x18020d39a  test    eax, eax
0x18020d39c  jns     short loc_18020D3A8
0x18020d39e  mov     edx, 3ADh
0x18020d3a3  jmp     loc_18020D150
0x18020d3a8  lea     rdx, off_1803E1A30; "ResizeWindow"
0x18020d3af  lea     rcx, [rbp+57h+var_60]
0x18020d3b3  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18020d3b8  mov     rdx, [rax+18h]; HSTRING
0x18020d3bc  mov     rcx, rsi; this
0x18020d3bf  call    ?CompareStringOrdinal@Details@Wrappers@WRL@Microsoft@@YAHPEAUHSTRING__@@0@Z; Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(HSTRING__ *,HSTRING__ *)
0x18020d3c4  test    eax, eax
0x18020d3c6  jz      loc_18020D521
0x18020d3cc  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CAI@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CAI@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CAI> `wil::Feature<__WilFeatureTraits_Feature_CAI>::GetImpl(void)'::`2'::impl
0x18020d3d3  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CAI@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CAI>::__private_IsEnabled(void)
0x18020d3d8  test    al, al
0x18020d3da  jz      loc_18020D64B
0x18020d3e0  lea     rdx, off_1803E1A20; "ResizeWindowWithScaling"
0x18020d3e7  lea     rcx, [rbp+57h+var_60]
0x18020d3eb  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18020d3f0  mov     rdx, [rax+18h]; HSTRING
0x18020d3f4  mov     rcx, rsi; this
0x18020d3f7  call    ?CompareStringOrdinal@Details@Wrappers@WRL@Microsoft@@YAHPEAUHSTRING__@@0@Z; Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(HSTRING__ *,HSTRING__ *)
0x18020d3fc  test    eax, eax
0x18020d3fe  jnz     loc_18020D64B
0x18020d404  lea     rcx, [rbp+57h+var_A0]; struct wil::details::IFailureCallback *
0x18020d408  call    ??$start_and_watch_errors@V?$tip_test@V?$merged_data@U_tip_ShareSheetResizeTest@@U1@@details@tip2@@@tip2@@@tip2@@YA?A_PXZ
0x18020d40d  nop
0x18020d40e  mov     rcx, [rbp+57h+var_68]
0x18020d412  add     rcx, 8
0x18020d416  call    ?is_running@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::is_running(void)
0x18020d41b  test    al, al
0x18020d41d  jz      short loc_18020D440
0x18020d41f  lea     rdx, [rbp+57h+var_68]
0x18020d423  lea     rcx, [rbp+57h+var_B8]
0x18020d427  call    ??0?$test_data_control@V?$merged_data@U_tip_ShareSheetResizeTest@@U1@@details@tip2@@@tip2@@IEAA@AEBV?$com_ptr_t@V?$merged_data@U_tip_ShareSheetResizeTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@@Z; tip2::test_data_control<tip2::details::merged_data<_tip_ShareSheetResizeTest,_tip_ShareSheetResizeTest>>::test_data_control<tip2::details::merged_data<_tip_ShareSheetResizeTest,_tip_ShareSheetResizeTest>>(wil::com_ptr_t<tip2::details::merged_data<_tip_ShareSheetResizeTest,_tip_ShareSheetResizeTest>,wil::err_returncode_policy> const &)
0x18020d42c  mov     rax, [rbp+57h+var_B8]
0x18020d430  mov     byte ptr [rax+110h], 1
0x18020d437  lea     rcx, [rbp+57h+var_B8]
0x18020d43b  call    ??1?$test_data_control@V?$merged_data@U_tip_ShareSheetResizeTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_ShareSheetResizeTest,_tip_ShareSheetResizeTest>>::~test_data_control<tip2::details::merged_data<_tip_ShareSheetResizeTest,_tip_ShareSheetResizeTest>>(void)
0x18020d440  xor     eax, eax
0x18020d442  mov     [rbp+57h+var_B0], rax
0x18020d446  mov     [rbp+57h+string], r15
0x18020d44a  lea     rcx, [rbp+57h+string]
0x18020d44e  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x18020d453  nop
0x18020d454  lea     rdx, off_1803E1A28; "ResizeWindowSize"
0x18020d45b  lea     rcx, [rbp+57h+var_60]
0x18020d45f  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18020d464  nop
0x18020d465  mov     rbx, [rax+18h]
0x18020d469  xor     eax, eax
0x18020d46b  mov     [rbp+57h+var_B0], rax
0x18020d46f  mov     [rbp+57h+var_B8], rax
0x18020d473  lea     rcx, [rbp+57h+var_B8]
0x18020d477  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18020d47c  lea     r8, [rbp+57h+var_B8]; struct Windows::Foundation::IPropertyValue **
0x18020d480  mov     rdx, rbx; HSTRING
0x18020d483  lea     rcx, [rbp+57h+string]; this
0x18020d487  call    ?GetPropVal@PropertySetHelper@ShellHelpers@Internal@Windows@@AEAAJPEAUHSTRING__@@PEAPEAUIPropertyValue@Foundation@4@@Z; Windows::Internal::ShellHelpers::PropertySetHelper::GetPropVal(HSTRING__ *,Windows::Foundation::IPropertyValue * *)
0x18020d48c  mov     ebx, eax
0x18020d48e  test    eax, eax
0x18020d490  jns     short loc_18020D494
0x18020d492  jmp     short loc_18020D4C3
0x18020d494  lea     rdx, [rbp+57h+var_B0]
0x18020d498  mov     rcx, [rbp+57h+var_B8]
0x18020d49c  call    ??_9IPropertyValue@Foundation@Windows@@$BMA@AA; [thunk]: Windows::Foundation::IPropertyValue::`vcall'{192,{flat}}
0x18020d4a1  mov     ebx, eax
0x18020d4a3  test    eax, eax
0x18020d4a5  jns     short loc_18020D4C1
0x18020d4a7  mov     rcx, [rbp+5Fh]; this
0x18020d4ab  mov     r9d, eax; char *
0x18020d4ae  lea     r8, aOnecoreInterna_14; "onecore\\internal\\shell\\inc\\Property"...
0x18020d4b5  mov     edx, 2Fh ; '/'; void *
0x18020d4ba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18020d4bf  jmp     short loc_18020D492
0x18020d4c1  xor     ebx, ebx
0x18020d4c3  lea     rcx, [rbp+57h+var_B8]
0x18020d4c7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18020d4cc  nop
0x18020d4cd  test    ebx, ebx
0x18020d4cf  jns     short loc_18020D4DB
0x18020d4d1  mov     r9d, ebx
0x18020d4d4  mov     edx, 3C7h
0x18020d4d9  jmp     short loc_18020D4F6
0x18020d4db  lea     rcx, [rdi-38h]
0x18020d4df  mov     rdx, [rbp+57h+var_B0]
0x18020d4e3  call    ?ResizeWindowWithScaling@CSharePickerExperienceManager@@AEAAJUSize@Foundation@Windows@@@Z; CSharePickerExperienceManager::ResizeWindowWithScaling(Windows::Foundation::Size)
0x18020d4e8  mov     ebx, eax
0x18020d4ea  test    eax, eax
0x18020d4ec  jns     short loc_18020D512
0x18020d4ee  mov     r9d, eax; char *
0x18020d4f1  mov     edx, 3C8h; void *
0x18020d4f6  mov     r8, r13; unsigned int
0x18020d4f9  mov     rcx, [rbp+5Fh]; this
0x18020d4fd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18020d502  nop
0x18020d503  lea     rcx, [rbp+57h+string]
0x18020d507  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18020d50c  nop
0x18020d50d  jmp     loc_18020D62A
0x18020d512  lea     rcx, [rbp+57h+string]
0x18020d516  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18020d51b  nop
0x18020d51c  jmp     loc_18020D642
0x18020d521  lea     rcx, [rbp+57h+var_A0]; struct wil::details::IFailureCallback *
0x18020d525  call    ??$start_and_watch_errors@V?$tip_test@V?$merged_data@U_tip_ShareSheetResizeTest@@U1@@details@tip2@@@tip2@@@tip2@@YA?A_PXZ
0x18020d52a  nop
0x18020d52b  mov     rcx, [rbp+57h+var_68]
0x18020d52f  add     rcx, 8
0x18020d533  call    ?is_running@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::is_running(void)
0x18020d538  test    al, al
0x18020d53a  jz      short loc_18020D55D
0x18020d53c  lea     rdx, [rbp+57h+var_68]
0x18020d540  lea     rcx, [rbp+57h+var_B8]
0x18020d544  call    ??0?$test_data_control@V?$merged_data@U_tip_ShareSheetResizeTest@@U1@@details@tip2@@@tip2@@IEAA@AEBV?$com_ptr_t@V?$merged_data@U_tip_ShareSheetResizeTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@@Z; tip2::test_data_control<tip2::details::merged_data<_tip_ShareSheetResizeTest,_tip_ShareSheetResizeTest>>::test_data_control<tip2::details::merged_data<_tip_ShareSheetResizeTest,_tip_ShareSheetResizeTest>>(wil::com_ptr_t<tip2::details::merged_data<_tip_ShareSheetResizeTest,_tip_ShareSheetResizeTest>,wil::err_returncode_policy> const &)
0x18020d549  mov     rax, [rbp+57h+var_B8]
0x18020d54d  mov     byte ptr [rax+110h], 1
0x18020d554  lea     rcx, [rbp+57h+var_B8]
0x18020d558  call    ??1?$test_data_control@V?$merged_data@U_tip_ShareSheetResizeTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_ShareSheetResizeTest,_tip_ShareSheetResizeTest>>::~test_data_control<tip2::details::merged_data<_tip_ShareSheetResizeTest,_tip_ShareSheetResizeTest>>(void)
0x18020d55d  xor     eax, eax
0x18020d55f  mov     [rbp+57h+var_B0], rax
  ... truncated ...
```
