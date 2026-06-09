# CPenWorkspaceExperienceManager::OnEventQueued(CSingleViewShellExperience *,HSTRING__ *,Windows::Foundation::Collections::IPropertySet *)

- ea: `0x1802024c0`
- end: `0x180203001`
- name: `?OnEventQueued@CPenWorkspaceExperienceManager@@EEAAJPEAVCSingleViewShellExperience@@PEAUHSTRING__@@PEAUIPropertySet@Collections@Foundation@Windows@@@Z`
- size: `2881`
- prototype: `int(CPenWorkspaceExperienceManager *__hidden this, struct CSingleViewShellExperience *, HSTRING, struct Windows::Foundation::Collections::IPropertySet *)`
- caller_count: `0`
- callee_count: `43`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180008acc`
- `0x18000b7e8`
- `0x18000c350`
- `0x18000cf94`
- `0x18001f3c0`
- `0x180020f80`
- `0x18003c5e4`
- `0x18003c898`
- `0x180052980`
- `0x18006276c`
- `0x18006d698`
- `0x18008308c`
- `0x180085aa4`
- `0x180092448`
- `0x1800a1e90`
- `0x1800c02b0`
- `0x1800ef220`
- `0x1800ef6dc`
- `0x1800f94d8`
- `0x18011b240`
- `0x1801307d8`
- `0x18013d330`
- `0x1801fb9c4`
- `0x1801fbc04`
- `0x1801fbed8`
- `0x1801fc900`
- `0x1801fc934`
- `0x1801ff6a0`
- `0x1801ffa78`
- `0x1801ffd84`
- `0x1802007d0`
- `0x180200cf0`
- `0x180200ef0`
- `0x1802011c4`
- `0x180201658`
- `0x18020180c`
- `0x1802019b8`
- `0x1802024c0`
- `0x180204490`
- `0x18020483c`
- `0x1802057b0`
- `0x1802250a4`
- `0x1803a3010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180202569`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802025df`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180202b1b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180202bc4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180202569`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802025df`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180202b1b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180202bc4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18020250c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1802025c7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180202b6a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18020250c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1802025c7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180202b6a`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetWindowTextW` at `0x1802025d4`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetWindowTextW` at `0x1802025d4`

## string_xrefs

- `0x180202cec`: `WhiteboardInstallStatusChanged`
- `0x180202e6f`: `WhiteboardInstallStatusChanged`
- `0x180202cf3`: `JournalInstallStatusChanged`
- `0x180202e76`: `JournalInstallStatusChanged`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
__int64 __fastcall CPenWorkspaceExperienceManager::OnEventQueued(
        CPenWorkspaceExperienceManager *this,
        struct CSingleViewShellExperience *a2,
        Microsoft::WRL::Wrappers::Details *a3,
        struct Windows::Foundation::Collections::IPropertySet *a4)
{
  const struct _tlgProvider_t *v7; // rax
  int v8; // esi
  int v9; // r9d
  __int64 v10; // rax
  HSTRING v11; // r8
  __int64 v12; // rax
  unsigned int ViewWindow; // esi
  HSTRING v14; // r8
  const WCHAR *StringRawBuffer; // rax
  __int64 v16; // rax
  HSTRING v17; // r8
  __int64 v18; // rax
  HSTRING v19; // r8
  __int64 v20; // rax
  HSTRING v21; // r8
  __int64 v22; // rax
  int v23; // eax
  int v24; // ebx
  __int64 v26; // rax
  HSTRING v27; // r8
  int v28; // edx
  __int64 v29; // rax
  HSTRING v30; // r8
  __int64 v31; // rax
  HSTRING v32; // r8
  __int64 v33; // rdx
  __int64 v34; // rax
  HSTRING v35; // r8
  __int64 v36; // rax
  HSTRING v37; // r8
  __int64 v38; // rax
  HSTRING v39; // r8
  __int64 v40; // rax
  HSTRING v41; // r8
  __int64 v42; // rax
  HSTRING v43; // r8
  __int64 v44; // rcx
  __int64 v45; // rax
  HSTRING v46; // r8
  char *v47; // r14
  int LockAppHost; // eax
  __int64 v49; // rdx
  HSTRING v50; // rbx
  __int64 (__fastcall *v51)(HSTRING, GUID *, HSTRING *); // rdi
  __int64 v52; // rax
  HSTRING v53; // r8
  __int64 v54; // rax
  HSTRING v55; // r8
  int v56; // eax
  int v57; // eax
  __int64 v58; // rdx
  __int64 v59; // rax
  HSTRING v60; // r8
  int v61; // eax
  __int64 v62; // rax
  HSTRING v63; // r8
  __int64 v64; // rax
  int v65; // eax
  const unsigned __int16 *v66; // rax
  int v67; // eax
  int v68; // eax
  HSTRING *p_string; // rcx
  __int64 v70; // rax
  HSTRING v71; // r8
  __int64 v72; // rdx
  __int64 v73; // rax
  HSTRING v74; // r8
  __int64 v75; // rax
  HSTRING v76; // r8
  __int64 v77; // rdx
  __int64 v78; // rax
  HSTRING v79; // r8
  __int64 v80; // rax
  HSTRING v81; // r8
  __int64 v82; // rax
  HSTRING v83; // r8
  const unsigned __int16 *v84; // r14
  __int64 v85; // rax
  HSTRING v86; // r8
  const wchar_t *v87; // r15
  CPenWorkspaceExperienceManager *v88; // rdi
  int IsAppInstalling; // eax
  __int64 v90; // rax
  int v91; // eax
  __int64 v92; // rax
  __int64 v93; // rbx
  __int64 v94; // rax
  HSTRING v95; // r8
  const unsigned __int16 *v96; // r14
  __int64 v97; // rax
  HSTRING v98; // r8
  wchar_t *v99; // r15
  int v100; // eax
  int v101; // eax
  __int64 v102; // rax
  int v103; // eax
  __int64 v104; // rdx
  struct Windows::Foundation::Collections::IPropertySet *v105; // rbx
  __int64 v106; // rax
  int v107; // [rsp+20h] [rbp-59h]
  bool v108; // [rsp+30h] [rbp-49h] BYREF
  HSTRING v109; // [rsp+38h] [rbp-41h] BYREF
  HSTRING string; // [rsp+40h] [rbp-39h] BYREF
  std::_Ref_count_base *v111; // [rsp+48h] [rbp-31h]
  HWND hWnd; // [rsp+50h] [rbp-29h] BYREF
  std::_Ref_count_base *v113; // [rsp+58h] [rbp-21h]
  HSTRING_HEADER hstringHeader; // [rsp+60h] [rbp-19h] BYREF
  __int64 v115; // [rsp+78h] [rbp-1h]
  _BYTE v116[8]; // [rsp+80h] [rbp+7h] BYREF
  std::_Ref_count_base *v117; // [rsp+88h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v7 = SingleViewExperienceLogging::Provider();
  v8 = (int)v7;
  if ( *(_DWORD *)v7 > 5u )
  {
    hWnd = (HWND)WindowsGetStringRawBuffer((HSTRING)a3, 0);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      v8,
      (unsigned int)&word_180446C0E,
      0,
      v9,
      (__int64)&hWnd);
  }
  v10 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, off_1803E1A08);
  if ( !(unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(a3, *(HSTRING *)(v10 + 24), v11) )
  {
    v109 = (HSTRING)a4;
    Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v109);
    string = 0;
    WindowsDeleteString(0);
    string = 0;
    v12 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &off_1803E1A10);
    ViewWindow = Windows::Internal::ShellHelpers::PropertySetHelper::GetValue<HSTRING__ *>(
                   (Windows::Internal::ShellHelpers::PropertySetHelper *)&v109,
                   *(HSTRING *)(v12 + 24));
    if ( (ViewWindow & 0x80000000) == 0
      && (unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(
                         (Microsoft::WRL::Wrappers::Details *)string,
                         0,
                         v14) )
    {
      hWnd = 0;
      ViewWindow = CPenWorkspaceExperienceManager::GetViewWindow(
                     (CPenWorkspaceExperienceManager *)((char *)this - 104),
                     &hWnd);
      if ( (ViewWindow & 0x80000000) == 0 )
      {
        StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
        SetWindowTextW(hWnd, StringRawBuffer);
      }
    }
    WindowsDeleteString(string);
    string = 0;
    goto LABEL_119;
  }
  ViewWindow = 0;
  v16 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, off_1803E1A00);
  if ( (unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(a3, *(HSTRING *)(v16 + 24), v17) )
  {
    v18 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, off_1803E1998);
    if ( !(unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(a3, *(HSTRING *)(v18 + 24), v19) )
    {
      CPenWorkspaceExperienceManager::DestroyExperienceView((CPenWorkspaceExperienceManager *)((char *)this - 104));
      return ViewWindow;
    }
    v20 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, off_1803E19A0);
    if ( !(unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(a3, *(HSTRING *)(v20 + 24), v21) )
    {
      v109 = (HSTRING)a4;
      Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v109);
      LODWORD(string) = -1;
      v22 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, off_1803E19A8);
      ViewWindow = Windows::Internal::ShellHelpers::PropertySetHelper::GetValue<int>(
                     (Windows::Internal::ShellHelpers::PropertySetHelper *)&v109,
                     *(HSTRING *)(v22 + 24));
      if ( (ViewWindow & 0x80000000) == 0 && (int)string >= 0 )
      {
        if ( *((_QWORD *)this + 8) )
        {
          v23 = CSingleViewShellExperience::SetWindowBand((char *)this + 40);
          v24 = v23;
          if ( v23 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x487,
              (unsigned int)"shell\\twinui\\experiencemanagers\\lib\\penworkspaceexperiencemanager.cpp",
              (const char *)(unsigned int)v23,
              v107);
LABEL_19:
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v109);
            return (unsigned int)v24;
          }
        }
      }
LABEL_119:
      p_string = &v109;
LABEL_120:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(p_string);
      return ViewWindow;
    }
    v26 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, off_1803E19D0);
    if ( !(unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(a3, *(HSTRING *)(v26 + 24), v27) )
    {
      v28 = 0;
LABEL_26:
      CPenWorkspaceExperienceManager::SetBorderAccent((CPenWorkspaceExperienceManager *)((char *)this - 104), v28);
      return ViewWindow;
    }
    v29 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, off_1803E19D8);
    if ( !(unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(a3, *(HSTRING *)(v29 + 24), v30) )
    {
      v28 = 1;
      goto LABEL_26;
    }
    v31 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, off_1803E19B0);
    if ( !(unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(a3, *(HSTRING *)(v31 + 24), v32) )
    {
      v24 = CPenWorkspaceExperienceManager::ShowRemember((CPenWorkspaceExperienceManager *)((char *)this - 104));
      if ( v24 >= 0 )
        return (unsigned int)v24;
      v33 = 1173;
LABEL_30:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v33,
        (unsigned int)"shell\\twinui\\experiencemanagers\\lib\\penworkspaceexperiencemanager.cpp",
        (const char *)(unsigned int)v24,
        v107);
      return (unsigned int)v24;
    }
    v34 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, off_1803E19B8);
    if ( !(unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(a3, *(HSTRING *)(v34 + 24), v35) )
    {
      v24 = CPenWorkspaceExperienceManager::HideRemember((CPenWorkspaceExperienceManager *)((char *)this - 104));
      if ( v24 >= 0 )
        return (unsigned int)v24;
      v33 = 1177;
      goto LABEL_30;
    }
    v36 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, off_1803E1940);
    if ( !(unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(a3, *(HSTRING *)(v36 + 24), v37) )
    {
      v24 = CPenWorkspaceExperienceManager::SizeWindowForHome((CPenWorkspaceExperienceManager *)((char *)this - 104));
      if ( v24 >= 0 )
        return (unsigned int)v24;
      v33 = 1181;
      goto LABEL_30;
    }
    v38 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, off_1803E1948);
    if ( !(unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(a3, *(HSTRING *)(v38 + 24), v39) )
    {
      v24 = CPenWorkspaceExperienceManager::ShowExperienceView((CPenWorkspaceExperienceManager *)((char *)this - 104));
      if ( v24 >= 0 )
        return ViewWindow;
      v33 = 1186;
      goto LABEL_30;
    }
    v40 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, off_1803E1950);
    if ( !(unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(a3, *(HSTRING *)(v40 + 24), v41) )
    {
      v24 = CPenWorkspaceExperienceManager::CloseUI((CPenWorkspaceExperienceManager *)((char *)this - 104));
      if ( v24 >= 0 )
        return (unsigned int)v24;
      v33 = 1190;
      goto LABEL_30;
    }
    v42 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, off_1803E1958);
    if ( !(unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(a3, *(HSTRING *)(v42 + 24), v43) )
    {
      v44 = *((_QWORD *)this + 50);
      if ( v44 )
        return (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v44 + 72LL))(v44);
      v24 = -2147418113;
      v33 = 1194;
      goto LABEL_30;
    }
    v45 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, off_1803E1960);
    if ( !(unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(a3, *(HSTRING *)(v45 + 24), v46) )
    {
      v47 = (char *)this - 104;
      if ( !*((_BYTE *)this + 336) )
        return ViewWindow;
      v109 = 0;
      string = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v109);
      LockAppHost = GetLockAppHost((struct ILockAppHost **)&v109);
      v24 = LockAppHost;
      if ( LockAppHost >= 0 )
      {
        v50 = v109;
        v51 = **(__int64 (__fastcall ***)(HSTRING, GUID *, HSTRING *))v109;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&string);
        LockAppHost = v51(v50, &GUID_f2f2e6cf_4806_4728_954a_ef83a6301791, &string);
        v24 = LockAppHost;
        if ( LockAppHost >= 0 )
        {
          LockAppHost = (*(__int64 (__fastcall **)(HSTRING, char *))(*(_QWORD *)string + 32LL))(string, v47);
          v24 = LockAppHost;
          if ( LockAppHost >= 0 )
          {
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&string);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v109);
            return ViewWindow;
          }
          v49 = 1206;
        }
        else
        {
          v49 = 1205;
        }
      }
      else
      {
        v49 = 1204;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v49,
        (unsigned int)"shell\\twinui\\experiencemanagers\\lib\\penworkspaceexperiencemanager.cpp",
        (const char *)(unsigned int)LockAppHost,
        v107);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&string);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v109);
      return (unsigned int)v24;
    }
    v52 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, off_1803E1968);
    if ( !(unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(a3, *(HSTRING *)(v52 + 24), v53) )
    {
      v24 = CPenWorkspaceExperienceManager::BringToForeground((CPenWorkspaceExperienceManager *)((char *)this - 104));
      if ( v24 >= 0 )
        return ViewWindow;
      v33 = 1211;
      goto LABEL_30;
    }
    v54 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, off_1803E1918);
    if ( !(unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(a3, *(HSTRING *)(v54 + 24), v55) )
    {
      v56 = CPenWorkspaceExperienceManager::LaunchCustomSketchApp((CPenWorkspaceExperienceManager *)((char *)this - 104));
      if ( v56 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x4BF,
          (unsigned int)"shell\\twinui\\experiencemanagers\\lib\\penworkspaceexperiencemanager.cpp",
          (const char *)(unsigned int)v56,
          v107);
      v57 = CPenWorkspaceExperienceManager::Hide((CPenWorkspaceExperienceManager *)((char *)this - 104), 1);
      if ( v57 >= 0 )
        return ViewWindow;
      v58 = 1216;
      goto LABEL_70;
    }
    v59 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, off_1803E1970);
    if ( !(unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(a3, *(HSTRING *)(v59 + 24), v60) )
    {
      v61 = CPenWorkspaceExperienceManager::LaunchInkGrabApp((CPenWorkspaceExperienceManager *)((char *)this - 104));
      if ( v61 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x4C4,
          (unsigned int)"shell\\twinui\\experiencemanagers\\lib\\penworkspaceexperiencemanager.cpp",
          (const char *)(unsigned int)v61,
          v107);
      v57 = CPenWorkspaceExperienceManager::Hide((CPenWorkspaceExperienceManager *)((char *)this - 104), 1);
      if ( v57 >= 0 )
        return ViewWindow;
      v58 = 1221;
LABEL_70:
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)v58,
        (unsigned int)"shell\\twinui\\experiencemanagers\\lib\\penworkspaceexperiencemanager.cpp",
        (const char *)(unsigned int)v57,
        v107);
      return ViewWindow;
    }
    v62 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, off_1803E1978);
    if ( !(unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(a3, *(HSTRING *)(v62 + 24), v63) )
    {
      string = (HSTRING)a4;
      Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&string);
      WindowsDeleteString(0);
      v109 = 0;
      v64 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, off_1803E1920);
      v65 = Windows::Internal::ShellHelpers::PropertySetHelper::GetValue<HSTRING__ *>(
              (Windows::Internal::ShellHelpers::PropertySetHelper *)&string,
              *(HSTRING *)(v64 + 24));
      if ( v65 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x4CB,
          (unsigned int)"shell\\twinui\\experiencemanagers\\lib\\penworkspaceexperiencemanager.cpp",
          (const char *)(unsigned int)v65,
          v107);
      v66 = WindowsGetStringRawBuffer(v109, 0);
      v67 = CPenWorkspaceExperienceManager::LaunchScreenSketchApp(
              (CPenWorkspaceExperienceManager *)((char *)this - 104),
              v66);
      if ( v67 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x4CC,
          (unsigned int)"shell\\twinui\\experiencemanagers\\lib\\penworkspaceexperiencemanager.cpp",
          (const char *)(unsigned int)v67,
          v107);
      v68 = CPenWorkspaceExperienceManager::Hide((CPenWorkspaceExperienceManager *)((char *)this - 104), 1);
      if ( v68 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x4CD,
          (unsigned int)"shell\\twinui\\experiencemanagers\\lib\\penworkspaceexperiencemanager.cpp",
          (const char *)(unsigned int)v68,
          v107);
      WindowsDeleteString(v109);
      v109 = 0;
      p_string = &string;
      goto LABEL_120;
    }
    v70 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, off_1803E1930);
    if ( (unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(a3, *(HSTRING *)(v70 + 24), v71) )
    {
      v73 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v116, off_1803E1900);
      if ( (unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(a3, *(HSTRING *)(v73 + 24), v74) )
      {
        v75 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, off_1803E1938);
        if ( (unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(a3, *(HSTRING *)(v75 + 24), v76) )
        {
          v78 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v116, off_1803E1908);
          if ( (unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(a3, *(HSTRING *)(v78 + 24), v79) )
          {
            v80 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, off_1803E1910);
            if ( !(unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(a3, *(HSTRING *)(v80 + 24), v81) )
              Concurrency::details::_CancellationTokenState::_Cancel(*((Concurrency::details::_CancellationTokenState **)this
                                                                     + 69));
            return ViewWindow;
          }
        }
        LOBYTE(v77) = 1;
        wil::details::FeatureImpl<__WilFeatureTraits_Feature_PenDetachIWS>::ReportUsage(
          `wil::Feature<__WilFeatureTraits_Feature_PenDetachIWS>::GetImpl'::`2'::impl,
          v77);
        v82 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, off_1803E1908);
        v84 = L"9n318r854rhh";
        if ( (unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(a3, *(HSTRING *)(v82 + 24), v83) )
          v84 = L"9MSPC6MP8FM4";
        v85 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, off_1803E1908);
        v87 = L"JournalInstallStatusChanged";
        if ( (unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(a3, *(HSTRING *)(v85 + 24), v86) )
          v87 = L"WhiteboardInstallStatusChanged";
        v108 = 0;
        v88 = (CPenWorkspaceExperienceManager *)((char *)this - 104);
        IsAppInstalling = CPenWorkspaceExperienceManager::GetIsAppInstalling(v88, v84, &v108);
        if ( IsAppInstalling < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x4F0,
            (unsigned int)"shell\\twinui\\experiencemanagers\\lib\\penworkspaceexperiencemanager.cpp",
            (const char *)(unsigned int)IsAppInstalling,
            v107);
        if ( v108 )
          return 0;
        v109 = 0;
        hWnd = (HWND)&v109;
        v90 = Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::WeakRef>::operator Microsoft::WRL::WeakRef *(&hWnd);
        v91 = Microsoft::WRL::AsWeak<CPenWorkspaceExperienceManager>(v88, v90);
        v24 = v91;
        if ( v91 >= 0 )
        {
          v92 = CPenWorkspaceExperienceManager::InstallApp(v88, v116, v84, v87);
          v93 = Concurrency::create_task<void>(&string, v92);
          hstringHeader.Reserved.Reserved1 = v88;
          *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] = v109;
          Microsoft::WRL::ComPtr<IWindowingEnvironmentConfig>::InternalAddRef(&hstringHeader.Reserved.Reserved2[8]);
          *(_QWORD *)&hstringHeader.Reserved.Reserved2[16] = v87;
          Concurrency::task_bool_::then__lambda_150eaf9c64461fd64252382c642fd320___(v93, &hWnd, &hstringHeader);
          if ( v113 )
            std::_Ref_count_base::_Decref(v113);
          Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&hstringHeader.Reserved.Reserved2[8]);
          if ( v111 )
            std::_Ref_count_base::_Decref(v111);
          if ( v117 )
            std::_Ref_count_base::_Decref(v117);
          Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v109);
          return ViewWindow;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x4F7,
          (unsigned int)"shell\\twinui\\experiencemanagers\\lib\\penworkspaceexperiencemanager.cpp",
          (const char *)(unsigned int)v91,
          v107);
        Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v109);
        return (unsigned int)v24;
      }
    }
    LOBYTE(v72) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_PenDetachIWS>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_PenDetachIWS>::GetImpl'::`2'::impl,
      v72);
    v94 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, off_1803E1900);
    v96 = L"9n318r854rhh";
    if ( (unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(a3, *(HSTRING *)(v94 + 24), v95) )
      v96 = L"9MSPC6MP8FM4";
    v97 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, off_1803E1900);
    v99 = L"JournalInstallStatusChanged";
    if ( (unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(a3, *(HSTRING *)(v97 + 24), v98) )
      v99 = L"WhiteboardInstallStatusChanged";
    hWnd = (HWND)v99;
    v109 = 0;
    v115 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Foundation.Collections.ValueSet",
      0x28u,
      0x27u);
    v100 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>>(
             v115,
             &v109);
    v24 = v100;
    if ( v100 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4D7,
        (unsigned int)"shell\\twinui\\experiencemanagers\\lib\\penworkspaceexperiencemanager.cpp",
        (const char *)(unsigned int)v100,
        v107);
      goto LABEL_19;
    }
    string = v109;
    Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&string);
    v108 = 0;
    v101 = CPenWorkspaceExperienceManager::GetIsAppInstalling(
             (CPenWorkspaceExperienceManager *)((char *)this - 104),
             v96,
             &v108);
    if ( v101 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x4DB,
        (unsigned int)"shell\\twinui\\experiencemanagers\\lib\\penworkspaceexperiencemanager.cpp",
        (const char *)(unsigned int)v101,
        v107);
    v102 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, off_1803E1928);
    if ( v108 )
    {
      v103 = Windows::Internal::ShellHelpers::PropertySetHelper::SetValue<int>(
               (Windows::Internal::ShellHelpers::PropertySetHelper *)&string,
               *(HSTRING *)(v102 + 24));
      v24 = v103;
      if ( v103 < 0 )
      {
        v104 = 1246;
        goto LABEL_117;
      }
    }
    else
    {
      v103 = Windows::Internal::ShellHelpers::PropertySetHelper::SetValue<int>(
               (Windows::Internal::ShellHelpers::PropertySetHelper *)&string,
               *(HSTRING *)(v102 + 24));
      v24 = v103;
      if ( v103 < 0 )
      {
        v104 = 1250;
        goto LABEL_117;
      }
    }
    v105 = (struct Windows::Foundation::Collections::IPropertySet *)v109;
    v106 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &hWnd);
    v103 = CSingleViewShellExperience::Reactivate(
             (CPenWorkspaceExperienceManager *)((char *)this + 40),
             *(HSTRING *)(v106 + 24),
             v105,
             0);
    v24 = v103;
    if ( v103 >= 0 )
    {
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&string);
      goto LABEL_119;
    }
    v104 = 1253;
LABEL_117:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v104,
      (unsigned int)"shell\\twinui\\experiencemanagers\\lib\\penworkspaceexperiencemanager.cpp",
      (const char *)(unsigned int)v103,
      v107);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&string);
    goto LABEL_19;
  }
  CPenWorkspaceExperienceManager::Hide((CPenWorkspaceExperienceManager *)((char *)this - 104), 0);
  return ViewWindow;
}

```

## disassembly

```asm
0x1802024c0  mov     [rsp-8+arg_8], rbx
0x1802024c5  mov     [rsp-8+arg_18], rsi
0x1802024ca  push    rbp
0x1802024cb  push    rdi
0x1802024cc  push    r12
0x1802024ce  push    r14
0x1802024d0  push    r15
0x1802024d2  lea     rbp, [rsp-37h]
0x1802024d7  sub     rsp, 0B0h
0x1802024de  mov     rax, cs:__security_cookie
0x1802024e5  xor     rax, rsp
0x1802024e8  mov     [rbp+57h+var_30], rax
0x1802024ec  mov     r14, r9
0x1802024ef  mov     rbx, r8
0x1802024f2  mov     rdi, rcx
0x1802024f5  xor     r12d, r12d
0x1802024f8  call    ?Provider@SingleViewExperienceLogging@@SAPEBU_tlgProvider_t@@XZ; SingleViewExperienceLogging::Provider(void)
0x1802024fd  mov     rsi, rax
0x180202500  mov     ecx, [rax]
0x180202502  cmp     ecx, 5
0x180202505  jbe     short loc_180202531
0x180202507  xor     edx, edx; length
0x180202509  mov     rcx, rbx; string
0x18020250c  call    cs:__imp_WindowsGetStringRawBuffer
0x180202512  mov     [rbp+57h+hWnd], rax
0x180202516  lea     rax, [rbp+57h+hWnd]
0x18020251a  mov     qword ptr [rsp+0D0h+var_B0], rax; int
0x18020251f  xor     r8d, r8d
0x180202522  lea     rdx, word_180446C0E
0x180202529  mov     rcx, rsi
0x18020252c  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180202531  lea     rdx, off_1803E1A08; "NotifyWindowName"
0x180202538  lea     rcx, [rbp+57h+hstringHeader]
0x18020253c  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180202541  mov     rdx, [rax+18h]; HSTRING
0x180202545  mov     rcx, rbx; this
0x180202548  call    ?CompareStringOrdinal@Details@Wrappers@WRL@Microsoft@@YAHPEAUHSTRING__@@0@Z; Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(HSTRING__ *,HSTRING__ *)
0x18020254d  test    eax, eax
0x18020254f  jnz     loc_1802025EE
0x180202555  mov     [rbp+57h+var_98], r14
0x180202559  lea     rcx, [rbp+57h+var_98]
0x18020255d  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x180202562  nop
0x180202563  mov     [rbp+57h+string], r12
0x180202567  xor     ecx, ecx; string
0x180202569  call    cs:__imp_WindowsDeleteString
0x18020256f  mov     [rbp+57h+string], r12
0x180202573  lea     rdx, off_1803E1A10; "Name"
0x18020257a  lea     rcx, [rbp+57h+hstringHeader]
0x18020257e  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180202583  nop
0x180202584  lea     r9, [rbp+57h+string]
0x180202588  mov     rdx, [rax+18h]; HSTRING
0x18020258c  lea     rcx, [rbp+57h+var_98]; this
0x180202590  call    ??$GetValue@PEAUHSTRING__@@@PropertySetHelper@ShellHelpers@Internal@Windows@@AEAAJPEAUHSTRING__@@P8IPropertyValue@Foundation@3@EAAJPEAPEAU4@@Z1@Z; Windows::Internal::ShellHelpers::PropertySetHelper::GetValue<HSTRING__ *>(HSTRING__ *,long (Windows::Foundation::IPropertyValue::*)(HSTRING__ * *),HSTRING__ * *)
0x180202595  mov     esi, eax
0x180202597  test    eax, eax
0x180202599  js      short loc_1802025DB
0x18020259b  xor     edx, edx; HSTRING
0x18020259d  mov     rcx, [rbp+57h+string]; this
0x1802025a1  call    ?CompareStringOrdinal@Details@Wrappers@WRL@Microsoft@@YAHPEAUHSTRING__@@0@Z; Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(HSTRING__ *,HSTRING__ *)
0x1802025a6  test    eax, eax
0x1802025a8  jz      short loc_1802025DB
0x1802025aa  mov     [rbp+57h+hWnd], r12
0x1802025ae  lea     rcx, [rdi-68h]; this
0x1802025b2  lea     rdx, [rbp+57h+hWnd]; HWND *
0x1802025b6  call    ?GetViewWindow@CPenWorkspaceExperienceManager@@AEAAJPEAPEAUHWND__@@@Z; CPenWorkspaceExperienceManager::GetViewWindow(HWND__ * *)
0x1802025bb  mov     esi, eax
0x1802025bd  test    eax, eax
0x1802025bf  js      short loc_1802025DB
0x1802025c1  xor     edx, edx; length
0x1802025c3  mov     rcx, [rbp+57h+string]; string
0x1802025c7  call    cs:__imp_WindowsGetStringRawBuffer
0x1802025cd  mov     rdx, rax; lpString
0x1802025d0  mov     rcx, [rbp+57h+hWnd]; hWnd
0x1802025d4  call    cs:__imp_SetWindowTextW
0x1802025da  nop
0x1802025db  mov     rcx, [rbp+57h+string]; string
0x1802025df  call    cs:__imp_WindowsDeleteString
0x1802025e5  mov     [rbp+57h+string], r12
0x1802025e9  jmp     loc_180202FCE
0x1802025ee  mov     esi, r12d
0x1802025f1  lea     rdx, off_1803E1A00; "Dismiss"
0x1802025f8  lea     rcx, [rbp+57h+hstringHeader]
0x1802025fc  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180202601  mov     rdx, [rax+18h]; HSTRING
0x180202605  mov     rcx, rbx; this
0x180202608  call    ?CompareStringOrdinal@Details@Wrappers@WRL@Microsoft@@YAHPEAUHSTRING__@@0@Z; Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(HSTRING__ *,HSTRING__ *)
0x18020260d  test    eax, eax
0x18020260f  jnz     short loc_180202621
0x180202611  lea     rcx, [rdi-68h]; this
0x180202615  xor     edx, edx; bool
0x180202617  call    ?Hide@CPenWorkspaceExperienceManager@@AEAAJ_N@Z; CPenWorkspaceExperienceManager::Hide(bool)
0x18020261c  jmp     loc_180202FD7
0x180202621  lea     rdx, off_1803E1998; "StartActualDestroy"
0x180202628  lea     rcx, [rbp+57h+hstringHeader]
0x18020262c  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180202631  mov     rdx, [rax+18h]; HSTRING
0x180202635  mov     rcx, rbx; this
0x180202638  call    ?CompareStringOrdinal@Details@Wrappers@WRL@Microsoft@@YAHPEAUHSTRING__@@0@Z; Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(HSTRING__ *,HSTRING__ *)
0x18020263d  test    eax, eax
0x18020263f  jnz     short loc_18020264F
0x180202641  lea     rcx, [rdi-68h]; this
0x180202645  call    ?DestroyExperienceView@CPenWorkspaceExperienceManager@@AEAAJXZ; CPenWorkspaceExperienceManager::DestroyExperienceView(void)
0x18020264a  jmp     loc_180202FD7
0x18020264f  lea     rdx, off_1803E19A0; "ChangeZBand"
0x180202656  lea     rcx, [rbp+57h+hstringHeader]
0x18020265a  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18020265f  mov     rdx, [rax+18h]; HSTRING
0x180202663  mov     rcx, rbx; this
0x180202666  call    ?CompareStringOrdinal@Details@Wrappers@WRL@Microsoft@@YAHPEAUHSTRING__@@0@Z; Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(HSTRING__ *,HSTRING__ *)
0x18020266b  test    eax, eax
0x18020266d  jnz     loc_1802026FA
0x180202673  mov     [rbp+57h+var_98], r14
0x180202677  lea     rcx, [rbp+57h+var_98]
0x18020267b  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x180202680  nop
0x180202681  mov     dword ptr [rbp+57h+string], 0FFFFFFFFh
0x180202688  lea     rdx, off_1803E19A8; "ZBandValue"
0x18020268f  lea     rcx, [rbp+57h+hstringHeader]
0x180202693  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180202698  nop
0x180202699  lea     r9, [rbp+57h+string]
0x18020269d  mov     rdx, [rax+18h]; HSTRING
0x1802026a1  lea     rcx, [rbp+57h+var_98]; this
0x1802026a5  call    ??$GetValue@H@PropertySetHelper@ShellHelpers@Internal@Windows@@AEAAJPEAUHSTRING__@@P8IPropertyValue@Foundation@3@EAAJPEAH@Z1@Z; Windows::Internal::ShellHelpers::PropertySetHelper::GetValue<int>(HSTRING__ *,long (Windows::Foundation::IPropertyValue::*)(int *),int *)
0x1802026aa  mov     esi, eax
0x1802026ac  test    eax, eax
0x1802026ae  js      short loc_1802026F5
0x1802026b0  mov     edx, dword ptr [rbp+57h+string]
0x1802026b3  test    edx, edx
0x1802026b5  js      short loc_1802026F5
0x1802026b7  cmp     [rdi+40h], r12
0x1802026bb  jz      short loc_1802026F5
0x1802026bd  lea     rcx, [rdi+28h]
0x1802026c1  call    ?SetWindowBand@CSingleViewShellExperience@@QEAAJW4ZBID@@@Z; CSingleViewShellExperience::SetWindowBand(ZBID)
0x1802026c6  mov     ebx, eax
0x1802026c8  test    eax, eax
0x1802026ca  jns     short loc_1802026F5
0x1802026cc  mov     rcx, [rbp+5Fh]; this
0x1802026d0  mov     r9d, eax; char *
0x1802026d3  lea     r8, aShellTwinuiExp_9; "shell\\twinui\\experiencemanagers\\lib"...
0x1802026da  mov     edx, 487h; void *
0x1802026df  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802026e4  nop
0x1802026e5  lea     rcx, [rbp+57h+var_98]
0x1802026e9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1802026ee  mov     eax, ebx
0x1802026f0  jmp     loc_180202FD9
0x1802026f5  jmp     loc_180202FCE
0x1802026fa  lea     rdx, off_1803E19D0; "HideBlur"
0x180202701  lea     rcx, [rbp+57h+hstringHeader]
0x180202705  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18020270a  mov     rdx, [rax+18h]; HSTRING
0x18020270e  mov     rcx, rbx; this
0x180202711  call    ?CompareStringOrdinal@Details@Wrappers@WRL@Microsoft@@YAHPEAUHSTRING__@@0@Z; Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(HSTRING__ *,HSTRING__ *)
0x180202716  test    eax, eax
0x180202718  jnz     short loc_18020271E
0x18020271a  xor     edx, edx
0x18020271c  jmp     short loc_180202741
0x18020271e  lea     rdx, off_1803E19D8; "ShowBlur"
0x180202725  lea     rcx, [rbp+57h+hstringHeader]
0x180202729  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18020272e  mov     rdx, [rax+18h]; HSTRING
0x180202732  mov     rcx, rbx; this
0x180202735  call    ?CompareStringOrdinal@Details@Wrappers@WRL@Microsoft@@YAHPEAUHSTRING__@@0@Z; Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(HSTRING__ *,HSTRING__ *)
0x18020273a  test    eax, eax
0x18020273c  jnz     short loc_18020274F
0x18020273e  lea     edx, [rax+1]; int
0x180202741  lea     rcx, [rdi-68h]; this
0x180202745  call    ?SetBorderAccent@CPenWorkspaceExperienceManager@@AEAAJH@Z; CPenWorkspaceExperienceManager::SetBorderAccent(int)
0x18020274a  jmp     loc_180202FD7
0x18020274f  lea     rdx, off_1803E19B0; "ShowRemember"
0x180202756  lea     rcx, [rbp+57h+hstringHeader]
0x18020275a  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18020275f  mov     rdx, [rax+18h]; HSTRING
0x180202763  mov     rcx, rbx; this
0x180202766  call    ?CompareStringOrdinal@Details@Wrappers@WRL@Microsoft@@YAHPEAUHSTRING__@@0@Z; Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(HSTRING__ *,HSTRING__ *)
0x18020276b  test    eax, eax
0x18020276d  jnz     short loc_18020279F
0x18020276f  lea     rcx, [rdi-68h]; this
0x180202773  call    ?ShowRemember@CPenWorkspaceExperienceManager@@AEAAJXZ; CPenWorkspaceExperienceManager::ShowRemember(void)
0x180202778  mov     ebx, eax
0x18020277a  test    eax, eax
0x18020277c  jns     loc_1802026EE
0x180202782  mov     edx, 495h; void *
0x180202787  mov     rcx, [rbp+5Fh]; this
0x18020278b  mov     r9d, ebx; char *
0x18020278e  lea     r8, aShellTwinuiExp_9; "shell\\twinui\\experiencemanagers\\lib"...
0x180202795  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18020279a  jmp     loc_1802026EE
0x18020279f  lea     rdx, off_1803E19B8; "HideRemember"
0x1802027a6  lea     rcx, [rbp+57h+hstringHeader]
0x1802027aa  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1802027af  mov     rdx, [rax+18h]; HSTRING
0x1802027b3  mov     rcx, rbx; this
0x1802027b6  call    ?CompareStringOrdinal@Details@Wrappers@WRL@Microsoft@@YAHPEAUHSTRING__@@0@Z; Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(HSTRING__ *,HSTRING__ *)
0x1802027bb  test    eax, eax
0x1802027bd  jnz     short loc_1802027D9
0x1802027bf  lea     rcx, [rdi-68h]; this
0x1802027c3  call    ?HideRemember@CPenWorkspaceExperienceManager@@AEAAJXZ; CPenWorkspaceExperienceManager::HideRemember(void)
0x1802027c8  mov     ebx, eax
0x1802027ca  test    eax, eax
0x1802027cc  jns     loc_1802026EE
0x1802027d2  mov     edx, 499h
0x1802027d7  jmp     short loc_180202787
0x1802027d9  lea     rdx, off_1803E1940; "SizeWindowForHome"
0x1802027e0  lea     rcx, [rbp+57h+hstringHeader]
0x1802027e4  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1802027e9  mov     rdx, [rax+18h]; HSTRING
0x1802027ed  mov     rcx, rbx; this
0x1802027f0  call    ?CompareStringOrdinal@Details@Wrappers@WRL@Microsoft@@YAHPEAUHSTRING__@@0@Z; Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(HSTRING__ *,HSTRING__ *)
0x1802027f5  test    eax, eax
0x1802027f7  jnz     short loc_180202816
0x1802027f9  lea     rcx, [rdi-68h]; this
0x1802027fd  call    ?SizeWindowForHome@CPenWorkspaceExperienceManager@@AEAAJXZ; CPenWorkspaceExperienceManager::SizeWindowForHome(void)
0x180202802  mov     ebx, eax
0x180202804  test    eax, eax
0x180202806  jns     loc_1802026EE
0x18020280c  mov     edx, 49Dh
0x180202811  jmp     loc_180202787
0x180202816  lea     rdx, off_1803E1948; "ShowExperienceFromUri"
0x18020281d  lea     rcx, [rbp+57h+hstringHeader]
0x180202821  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180202826  mov     rdx, [rax+18h]; HSTRING
0x18020282a  mov     rcx, rbx; this
0x18020282d  call    ?CompareStringOrdinal@Details@Wrappers@WRL@Microsoft@@YAHPEAUHSTRING__@@0@Z; Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(HSTRING__ *,HSTRING__ *)
0x180202832  test    eax, eax
0x180202834  jnz     short loc_180202853
0x180202836  lea     rcx, [rdi-68h]; this
0x18020283a  call    ?ShowExperienceView@CPenWorkspaceExperienceManager@@AEAAJXZ; CPenWorkspaceExperienceManager::ShowExperienceView(void)
0x18020283f  mov     ebx, eax
0x180202841  test    eax, eax
0x180202843  jns     loc_180202FD7
0x180202849  mov     edx, 4A2h
0x18020284e  jmp     loc_180202787
0x180202853  lea     rdx, off_1803E1950; "CloseUI"
0x18020285a  lea     rcx, [rbp+57h+hstringHeader]
0x18020285e  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180202863  mov     rdx, [rax+18h]; HSTRING
0x180202867  mov     rcx, rbx; this
0x18020286a  call    ?CompareStringOrdinal@Details@Wrappers@WRL@Microsoft@@YAHPEAUHSTRING__@@0@Z; Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(HSTRING__ *,HSTRING__ *)
0x18020286f  test    eax, eax
0x180202871  jnz     short loc_180202890
0x180202873  lea     rcx, [rdi-68h]; this
0x180202877  call    ?CloseUI@CPenWorkspaceExperienceManager@@AEAAJXZ; CPenWorkspaceExperienceManager::CloseUI(void)
0x18020287c  mov     ebx, eax
0x18020287e  test    eax, eax
0x180202880  jns     loc_1802026EE
0x180202886  mov     edx, 4A6h
0x18020288b  jmp     loc_180202787
0x180202890  lea     rdx, off_1803E1958; "GiveFocusToNotes"
0x180202897  lea     rcx, [rbp+57h+hstringHeader]
0x18020289b  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1802028a0  mov     rdx, [rax+18h]; HSTRING
0x1802028a4  mov     rcx, rbx; this
0x1802028a7  call    ?CompareStringOrdinal@Details@Wrappers@WRL@Microsoft@@YAHPEAUHSTRING__@@0@Z; Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(HSTRING__ *,HSTRING__ *)
0x1802028ac  test    eax, eax
0x1802028ae  jnz     short loc_1802028DE
0x1802028b0  mov     rcx, [rdi+190h]
0x1802028b7  test    rcx, rcx
0x1802028ba  jnz     short loc_1802028CB
0x1802028bc  mov     ebx, 8000FFFFh
0x1802028c1  mov     edx, 4AAh
0x1802028c6  jmp     loc_180202787
0x1802028cb  mov     rax, [rcx]
0x1802028ce  mov     rax, [rax+48h]
0x1802028d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802028d7  mov     esi, eax
0x1802028d9  jmp     loc_180202FD7
0x1802028de  lea     rdx, off_1803E1960; "RequestUnlock"
0x1802028e5  lea     rcx, [rbp+57h+hstringHeader]
0x1802028e9  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1802028ee  mov     rdx, [rax+18h]; HSTRING
0x1802028f2  mov     rcx, rbx; this
0x1802028f5  call    ?CompareStringOrdinal@Details@Wrappers@WRL@Microsoft@@YAHPEAUHSTRING__@@0@Z; Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(HSTRING__ *,HSTRING__ *)
0x1802028fa  test    eax, eax
0x1802028fc  jnz     loc_1802029D2
0x180202902  lea     r14, [rdi-68h]
0x180202906  cmp     [r14+1B8h], r12b
0x18020290d  jz      loc_180202FD7
0x180202913  mov     [rbp+57h+var_98], r12
0x180202917  mov     [rbp+57h+string], r12
0x18020291b  lea     rcx, [rbp+57h+var_98]
0x18020291f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180202924  lea     rcx, [rbp+57h+var_98]; struct ILockAppHost **
0x180202928  call    ?GetLockAppHost@@YAJPEAPEAUILockAppHost@@@Z; GetLockAppHost(ILockAppHost * *)
0x18020292d  mov     ebx, eax
0x18020292f  test    eax, eax
0x180202931  jns     short loc_18020293A
0x180202933  mov     edx, 4B4h
0x180202938  jmp     short loc_18020298E
0x18020293a  mov     rbx, [rbp+57h+var_98]
0x18020293e  mov     rax, [rbx]
0x180202941  mov     rdi, [rax]
0x180202944  lea     rcx, [rbp+57h+string]
0x180202948  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18020294d  lea     r8, [rbp+57h+string]
0x180202951  lea     rdx, _GUID_f2f2e6cf_4806_4728_954a_ef83a6301791
0x180202958  mov     rcx, rbx
  ... truncated ...
```
