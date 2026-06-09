# CThemeManager2::SetCurrentTheme(HWND__ *,int,int,THEME_APPLY_FLAGS,THEMEPACK_FLAGS)

- ea: `0x180054e80`
- end: `0x1800554c2`
- name: `?SetCurrentTheme@CThemeManager2@@UEAAJPEAUHWND__@@HHW4THEME_APPLY_FLAGS@@W4THEMEPACK_FLAGS@@@Z`
- size: `1602`
- prototype: ``
- caller_count: `0`
- callee_count: `27`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x1800089c0`
- `0x18000ab10`
- `0x18000b644`
- `0x18000b9cc`
- `0x18000c470`
- `0x18000c598`
- `0x18001ed40`
- `0x180021134`
- `0x180030dac`
- `0x180030f64`
- `0x180032754`
- `0x18003324c`
- `0x1800358c0`
- `0x180042664`
- `0x18004aa1c`
- `0x18004aa8c`
- `0x18004b9f0`
- `0x18004ca20`
- `0x18004caac`
- `0x18004cc7c`
- `0x18004d958`
- `0x18004eb1c`
- `0x18004f044`
- `0x1800510bc`
- `0x180054e80`
- `0x18006ab10`
- `0x18006d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180055404`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18005542c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180055450`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180055404`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18005542c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180055450`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180054f4a`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180054f4a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800553ca`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800553ca`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800550a7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800550a7`
- `OLEAUT32!__imp_SysFreeString` at `0x1800553ac`
- `OLEAUT32!__imp_SysFreeString` at `0x1800553ac`
- `SspiCli!GetUserNameExW` at `0x180054efd`
- `SspiCli!GetUserNameExW` at `0x180054efd`

## string_xrefs

- `0x18005532a`: `CThemeManager2::SetCurrentTheme path=%ws iIndex=%d iIndexOld=%d _fIsFirstLogin=%d`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CThemeManager2::SetCurrentTheme(
        __int64 a1,
        HWND a2,
        unsigned int a3,
        int a4,
        unsigned int a5,
        int a6)
{
  unsigned int v6; // r12d
  unsigned __int16 *v7; // r15
  HANDLE *v8; // rbx
  int Error; // r14d
  HANDLE MutexW; // rax
  __int64 v11; // rdx
  __int64 (__fastcall ***v12)(_QWORD, GUID *, __int64 *); // rdi
  __int64 (__fastcall *v13)(_QWORD, GUID *, __int64 *); // rbx
  int v14; // eax
  CThemeManager2 *v15; // rcx
  __int64 v16; // rdx
  int v17; // ebx
  wil *v18; // rcx
  _QWORD *v19; // rdi
  bool v20; // dl
  int v21; // eax
  _QWORD *v22; // rbx
  __int64 v23; // rdx
  HWND v24; // r12
  __int64 v25; // rcx
  PCWSTR pszContent; // [rsp+20h] [rbp-538h]
  ULONG nSize; // [rsp+40h] [rbp-518h] BYREF
  unsigned int v29; // [rsp+44h] [rbp-514h] BYREF
  HWND hwndOwner; // [rsp+48h] [rbp-510h]
  int v31; // [rsp+50h] [rbp-508h] BYREF
  unsigned int v32; // [rsp+54h] [rbp-504h]
  BSTR bstrString; // [rsp+58h] [rbp-500h] BYREF
  int v34; // [rsp+60h] [rbp-4F8h] BYREF
  __int64 v35; // [rsp+68h] [rbp-4F0h] BYREF
  int v36; // [rsp+70h] [rbp-4E8h] BYREF
  int v37; // [rsp+74h] [rbp-4E4h]
  unsigned int v38; // [rsp+78h] [rbp-4E0h]
  _BYTE *v39; // [rsp+80h] [rbp-4D8h]
  unsigned __int16 *v40; // [rsp+88h] [rbp-4D0h]
  HWND v41; // [rsp+90h] [rbp-4C8h]
  HANDLE *v42; // [rsp+98h] [rbp-4C0h]
  WCHAR Buffer[40]; // [rsp+A0h] [rbp-4B8h] BYREF
  WCHAR NameBuffer[264]; // [rsp+F0h] [rbp-468h] BYREF
  WCHAR Name[264]; // [rsp+300h] [rbp-258h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+558h] [rbp+0h]

  v6 = a3;
  hwndOwner = a2;
  v7 = (unsigned __int16 *)a1;
  v40 = (unsigned __int16 *)a1;
  v41 = a2;
  v38 = a3;
  v8 = (HANDLE *)(a1 + 2096);
  v42 = (HANDLE *)(a1 + 2096);
  if ( *(_QWORD *)(a1 + 2096) )
  {
    if ( WaitForSingleObject(*v8, 0) )
    {
LABEL_6:
      Error = ResultFromKnownLastError();
      if ( Error < 0 )
        return (unsigned int)Error;
LABEL_7:
      v29 = -1;
      v39 = (char *)v7 + 2145;
      v32 = a5;
      if ( !*((_BYTE *)v7 + 2145)
        && (a5 & 0x80u) == 0
        && (*(int (__fastcall **)(unsigned __int16 *, unsigned int *))(*(_QWORD *)v7 + 88LL))(v7, &v29) >= 0
        && v29 == v6 )
      {
        goto LABEL_56;
      }
      v31 = 0;
      Error = (*(__int64 (__fastcall **)(unsigned __int16 *, _QWORD, int *))(*(_QWORD *)v7 + 80LL))(v7, v6, &v31);
      if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DesktopSpotlightOEMContentDefaultImages>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DesktopSpotlightOEMContentDefaultImages>::GetImpl'::`2'::impl) )
      {
        LOBYTE(v11) = 1;
        wil::details::FeatureImpl<__WilFeatureTraits_Feature_DisableDesktopSpotlightOnFatalFailure>::ReportUsage(
          `wil::Feature<__WilFeatureTraits_Feature_DisableDesktopSpotlightOnFatalFailure>::GetImpl'::`2'::impl,
          v11);
        if ( Error < 0 )
          goto LABEL_56;
        if ( v31 )
        {
LABEL_55:
          Error = -2147467259;
          goto LABEL_56;
        }
        Error = (*(__int64 (__fastcall **)(unsigned __int16 *, _QWORD, unsigned __int16 *))(*(_QWORD *)v7 + 72LL))(
                  v7,
                  v6,
                  v7 + 1064);
        v37 = Error;
        if ( Error < 0 )
          goto LABEL_56;
        if ( !IsDesktopSpotlightAllowedByPolicy() )
        {
LABEL_36:
          if ( !v31 )
          {
            v19 = v7 + 1064;
            Error = (*(__int64 (__fastcall **)(unsigned __int16 *, _QWORD, unsigned __int16 *))(*(_QWORD *)v7 + 72LL))(
                      v7,
                      v6,
                      v7 + 1064);
            if ( Error >= 0 )
            {
              bstrString = 0;
              Error = (*(__int64 (__fastcall **)(_QWORD, __int64, BSTR *))(*(_QWORD *)*v19 + 288LL))(
                        *v19,
                        0xFFFFFFFFLL,
                        &bstrString);
              if ( Error < 0 )
                goto LABEL_53;
              Error = StringCchCopyW(v7 + 6, 0x104u, bstrString);
              if ( Error < 0 )
                goto LABEL_53;
              nSize = 0;
              if ( (*(int (__fastcall **)(_QWORD, ULONG *))(*(_QWORD *)*v19 + 464LL))(*v19, &nSize) < 0
                || (v20 = 1, (int)nSize <= 0) )
              {
                v20 = 0;
              }
              v21 = CThemeManager2::_SetCurrentThemeInRegistry((CThemeManager2 *)v7, v20);
              Error = v21;
              if ( !a4 || v21 < 0 )
                goto LABEL_53;
              v22 = v7 + 1060;
              v23 = v29;
              if ( v29 == -1 )
                v23 = v6;
              Error = (*(__int64 (__fastcall **)(unsigned __int16 *, __int64, unsigned __int16 *))(*(_QWORD *)v7 + 72LL))(
                        v7,
                        v23,
                        v7 + 1060);
              if ( Error >= 0 )
              {
                LODWORD(pszContent) = (unsigned __int8)*v39;
                ThemesTelemetry::TraceLoggingInfo(
                  "CThemeManager2::SetCurrentTheme path=%ws iIndex=%d iIndexOld=%d _fIsFirstLogin=%d",
                  v7 + 6,
                  v6,
                  v29,
                  pszContent);
                v24 = hwndOwner;
                Error = CThemeManager2::_ApplyTheme((__int64)v7, (__int64)hwndOwner, v32, a6);
                if ( Error >= 0 )
                {
                  if ( (Microsoft_Windows_ThemeUIEnableBits & 1) != 0 )
                    McTemplateU0z_EtwEventWriteTransfer(v25, ThemeSelected_Info, v7 + 6);
                  NotifyThemeCPLs(2);
                }
                (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v22 + 16LL))(*v22);
                *v22 = 0;
              }
              else
              {
LABEL_53:
                v24 = hwndOwner;
              }
              (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v19 + 16LL))(*v19);
              *v19 = 0;
              SysFreeString(bstrString);
              goto LABEL_57;
            }
LABEL_56:
            v24 = hwndOwner;
LABEL_57:
            ReleaseMutex(*v42);
            if ( Error < 0
              && !*v39
              && LoadStringW(g_hinst, 0xBBDu, Buffer, 40)
              && LoadStringW(g_hinst, 0xBBEu, NameBuffer, 260)
              && LoadStringW(g_hinst, 0xBBFu, Name, 260) )
            {
              TaskDialog(v24, g_hinst, Buffer, NameBuffer, Name, 32, (PCWSTR)0xFFFE, 0);
            }
            return (unsigned int)Error;
          }
          goto LABEL_55;
        }
        v34 = 0;
        v35 = 0;
        v12 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)v7 + 266);
        v13 = **v12;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v35);
        v14 = v13(v12, &GUID_6a0522b4_8e09_4aa8_985a_9e52d534977a, &v35);
        if ( v14 >= 0 )
        {
          if ( (*(int (__fastcall **)(__int64, int *))(*(_QWORD *)v35 + 32LL))(v35, &v34) >= 0 && v34 == 1 )
          {
            v17 = CThemeManager2::_ApplyDesktopSpotlight(v15);
            nSize = v17;
            if ( v17 < 0 )
            {
              LOBYTE(v16) = 1;
              wil::details::FeatureImpl<__WilFeatureTraits_Feature_DesktopSpotlightThemeEnabledOnFirstLogon>::ReportUsage(
                `wil::Feature<__WilFeatureTraits_Feature_DesktopSpotlightThemeEnabledOnFirstLogon>::GetImpl'::`2'::impl,
                v16);
              if ( *v39 && v29 == -1 )
              {
                SHRegSetDWORD(
                  HKEY_CURRENT_USER,
                  L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\DesktopSpotlight\\Settings",
                  L"EnabledState",
                  1u);
                nSize = 1;
              }
              else
              {
                CThemeManager2::s_UpdateResultOrLogFailure(
                  L"Failed to apply desktop spotlight and reverting to previous theme",
                  v17,
                  Error);
                v31 = 0;
                v6 = v29;
                Error = (*(__int64 (__fastcall **)(unsigned __int16 *, _QWORD, int *))(*(_QWORD *)v7 + 80LL))(
                          v7,
                          v29,
                          &v31);
              }
            }
            else
            {
              v32 = a5 | 1;
            }
            ThemesTelemetry::DesktopSpotlightThemeEnabled<long &>(&nSize);
          }
          else
          {
            nSize = 0;
            try
            {
              winrt::WindowsUdk::System::UserProfile::UserProfilePersonalizationSettings::UserProfilePersonalizationSettings((winrt::WindowsUdk::System::UserProfile::UserProfilePersonalizationSettings *)&bstrString);
              if ( (unsigned int)winrt::impl::consume_WindowsUdk_UI_Shell_DesktopSpotlight_IDesktopSpotlightExtension<winrt::WindowsUdk::UI::Shell::DesktopSpotlight::IDesktopSpotlightExtension>::WallpaperCount(&bstrString) == 1 )
              {
                v36 = 0;
                winrt::impl::consume_WindowsUdk_System_UserProfile_IUserProfilePersonalizationSettings<winrt::WindowsUdk::System::UserProfile::IUserProfilePersonalizationSettings>::DesktopSpotlightStatus(
                  &bstrString,
                  &v36);
              }
              winrt::Windows::Foundation::IAsyncAction::~IAsyncAction((winrt::Windows::Foundation::IAsyncAction *)&bstrString);
            }
            catch ( ... )
            {
              nSize = wil::ResultFromCaughtException(v18);
              v32 = a5;
              Error = v37;
              v7 = v40;
              hwndOwner = v41;
              v6 = v38;
            }
            ThemesTelemetry::DesktopSpotlightThemeDisabled<long &>(&nSize);
          }
        }
        else
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x1D6,
            (unsigned int)"shell\\themes\\themeui\\thememanager.cpp",
            (const char *)(unsigned int)v14,
            (int)pszContent);
        }
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v35);
      }
      if ( Error < 0 )
        goto LABEL_56;
      goto LABEL_36;
    }
LABEL_19:
    Error = 0;
    goto LABEL_7;
  }
  nSize = 260;
  if ( !GetUserNameExW((EXTENDED_NAME_FORMAT)65538, NameBuffer, &nSize) )
    NameBuffer[0] = 0;
  Error = StringCchPrintfW(Name, 0x104u, L"Local\\%s{34C08E7C-946E-4C99-BBD6-B810626DCF83}", NameBuffer);
  if ( Error >= 0 )
  {
    MutexW = CreateMutexW(0, 1, Name);
    *v8 = MutexW;
    if ( !MutexW )
      goto LABEL_6;
    goto LABEL_19;
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180054e80  mov     [rsp+arg_18], r9d
0x180054e85  push    rbx
0x180054e86  push    rsi
0x180054e87  push    rdi
0x180054e88  push    r12
0x180054e8a  push    r13
0x180054e8c  push    r14
0x180054e8e  push    r15
0x180054e90  sub     rsp, 520h
0x180054e97  mov     rax, cs:__security_cookie
0x180054e9e  xor     rax, rsp
0x180054ea1  mov     [rsp+558h+var_48], rax
0x180054ea9  mov     r12d, r8d
0x180054eac  mov     [rsp+558h+hwndOwner], rdx
0x180054eb1  mov     r15, rcx
0x180054eb4  mov     [rsp+558h+var_4D0], rcx
0x180054ebc  mov     [rsp+558h+var_4C8], rdx
0x180054ec4  mov     [rsp+558h+var_4E0], r8d
0x180054ec9  lea     rbx, [rcx+830h]
0x180054ed0  mov     [rsp+558h+var_4C0], rbx
0x180054ed8  xor     esi, esi
0x180054eda  cmp     [rbx], rsi
0x180054edd  jnz     loc_1800550A2
0x180054ee3  mov     [rsp+558h+nSize], 104h
0x180054eeb  lea     r8, [rsp+558h+nSize]; nSize
0x180054ef0  lea     rdx, [rsp+558h+NameBuffer]; lpNameBuffer
0x180054ef8  mov     ecx, 10002h; NameFormat
0x180054efd  call    cs:__imp_GetUserNameExW
0x180054f03  test    al, al
0x180054f05  jnz     short loc_180054F0F
0x180054f07  mov     [rsp+558h+NameBuffer], si
0x180054f0f  lea     r9, [rsp+558h+NameBuffer]
0x180054f17  lea     r8, aLocalS34c08e7c; "Local\\%s{34C08E7C-946E-4C99-BBD6-B8106"...
0x180054f1e  mov     edx, 104h; unsigned __int64
0x180054f23  lea     rcx, [rsp+558h+Name]; unsigned __int16 *
0x180054f2b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180054f30  mov     r14d, eax
0x180054f33  test    eax, eax
0x180054f35  js      loc_18005549C
0x180054f3b  lea     r8, [rsp+558h+Name]; lpName
0x180054f43  mov     edx, 1; bInitialOwner
0x180054f48  xor     ecx, ecx; lpMutexAttributes
0x180054f4a  call    cs:__imp_CreateMutexW
0x180054f50  mov     [rbx], rax
0x180054f53  test    rax, rax
0x180054f56  jnz     loc_1800550B5
0x180054f5c  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180054f61  mov     r14d, eax
0x180054f64  test    eax, eax
0x180054f66  js      loc_18005549C
0x180054f6c  mov     [rsp+558h+var_514], 0FFFFFFFFh
0x180054f74  lea     rax, [r15+861h]
0x180054f7b  mov     [rsp+558h+var_4D8], rax
0x180054f83  mov     r13d, [rsp+558h+arg_20]
0x180054f8b  mov     [rsp+558h+var_504], r13d
0x180054f90  cmp     [rax], sil
0x180054f93  jnz     short loc_180054FBD
0x180054f95  test    r13b, r13b
0x180054f98  js      short loc_180054FBD
0x180054f9a  mov     rax, [r15]
0x180054f9d  lea     rdx, [rsp+558h+var_514]
0x180054fa2  mov     rcx, r15
0x180054fa5  mov     rax, [rax+58h]
0x180054fa9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054fae  test    eax, eax
0x180054fb0  js      short loc_180054FBD
0x180054fb2  cmp     [rsp+558h+var_514], r12d
0x180054fb7  jz      loc_1800553BA
0x180054fbd  mov     [rsp+558h+var_508], esi
0x180054fc1  mov     rax, [r15]
0x180054fc4  lea     r8, [rsp+558h+var_508]
0x180054fc9  mov     edx, r12d
0x180054fcc  mov     rcx, r15
0x180054fcf  mov     rax, [rax+50h]
0x180054fd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054fd8  mov     r14d, eax
0x180054fdb  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DesktopSpotlightOEMContentDefaultImages@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DesktopSpotlightOEMContentDefaultImages@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DesktopSpotlightOEMContentDefaultImages> `wil::Feature<__WilFeatureTraits_Feature_DesktopSpotlightOEMContentDefaultImages>::GetImpl(void)'::`2'::impl
0x180054fe2  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DesktopSpotlightOEMContentDefaultImages@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DesktopSpotlightOEMContentDefaultImages>::__private_IsEnabled(void)
0x180054fe7  test    al, al
0x180054fe9  jnz     loc_18005520F
0x180054fef  mov     dl, 1
0x180054ff1  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DisableDesktopSpotlightOnFatalFailure@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DisableDesktopSpotlightOnFatalFailure@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DisableDesktopSpotlightOnFatalFailure> `wil::Feature<__WilFeatureTraits_Feature_DisableDesktopSpotlightOnFatalFailure>::GetImpl(void)'::`2'::impl
0x180054ff8  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_DisableDesktopSpotlightOnFatalFailure@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DisableDesktopSpotlightOnFatalFailure>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180054ffd  test    r14d, r14d
0x180055000  js      loc_1800553BA
0x180055006  mov     eax, [rsp+558h+var_508]
0x18005500a  test    eax, eax
0x18005500c  jnz     loc_1800553B4
0x180055012  lea     rdi, [r15+850h]
0x180055019  mov     rax, [r15]
0x18005501c  mov     r8, rdi
0x18005501f  mov     edx, r12d
0x180055022  mov     rcx, r15
0x180055025  mov     rax, [rax+48h]
0x180055029  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005502e  mov     r14d, eax
0x180055031  mov     [rsp+558h+var_4E4], eax
0x180055035  test    eax, eax
0x180055037  js      loc_1800553BA
0x18005503d  call    ?IsDesktopSpotlightAllowedByPolicy@@YA_NXZ; IsDesktopSpotlightAllowedByPolicy(void)
0x180055042  test    al, al
0x180055044  jz      loc_180055218
0x18005504a  mov     [rsp+558h+var_4F8], esi
0x18005504e  mov     [rsp+558h+var_4F0], rsi
0x180055053  mov     rdi, [rdi]
0x180055056  mov     rax, [rdi]
0x180055059  mov     rbx, [rax]
0x18005505c  lea     rcx, [rsp+558h+var_4F0]
0x180055061  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180055066  lea     r8, [rsp+558h+var_4F0]
0x18005506b  lea     rdx, _GUID_6a0522b4_8e09_4aa8_985a_9e52d534977a
0x180055072  mov     rcx, rdi
0x180055075  mov     rax, rbx
0x180055078  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005507d  mov     rcx, [rsp+558h]; this
0x180055085  test    eax, eax
0x180055087  jns     short loc_1800550BD
0x180055089  mov     r9d, eax; char *
0x18005508c  lea     r8, aShellThemesThe_6; "shell\\themes\\themeui\\thememanager.cp"...
0x180055093  mov     edx, 1D6h; void *
0x180055098  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18005509d  jmp     loc_180055205
0x1800550a2  xor     edx, edx; dwMilliseconds
0x1800550a4  mov     rcx, [rbx]; hHandle
0x1800550a7  call    cs:__imp_WaitForSingleObject
0x1800550ad  test    eax, eax
0x1800550af  jnz     loc_180054F5C
0x1800550b5  mov     r14d, esi
0x1800550b8  jmp     loc_180054F6C
0x1800550bd  mov     rcx, [rsp+558h+var_4F0]
0x1800550c2  mov     rax, [rcx]
0x1800550c5  lea     rdx, [rsp+558h+var_4F8]
0x1800550ca  mov     rax, [rax+20h]
0x1800550ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800550d3  test    eax, eax
0x1800550d5  js      loc_18005518F
0x1800550db  cmp     [rsp+558h+var_4F8], 1
0x1800550e0  jnz     loc_18005518F
0x1800550e6  call    ?_ApplyDesktopSpotlight@CThemeManager2@@AEAAJXZ; CThemeManager2::_ApplyDesktopSpotlight(void)
0x1800550eb  mov     ebx, eax
0x1800550ed  mov     [rsp+558h+nSize], eax
0x1800550f1  test    eax, eax
0x1800550f3  js      short loc_180055103
0x1800550f5  or      r13d, 1
0x1800550f9  mov     [rsp+558h+var_504], r13d
0x1800550fe  jmp     loc_180055183
0x180055103  mov     dl, 1
0x180055105  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DesktopSpotlightThemeEnabledOnFirstLogon@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DesktopSpotlightThemeEnabledOnFirstLogon@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DesktopSpotlightThemeEnabledOnFirstLogon> `wil::Feature<__WilFeatureTraits_Feature_DesktopSpotlightThemeEnabledOnFirstLogon>::GetImpl(void)'::`2'::impl
0x18005510c  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_DesktopSpotlightThemeEnabledOnFirstLogon@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DesktopSpotlightThemeEnabledOnFirstLogon>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180055111  mov     rax, [rsp+558h+var_4D8]
0x180055119  cmp     [rax], sil
0x18005511c  jz      short loc_18005514F
0x18005511e  cmp     [rsp+558h+var_514], 0FFFFFFFFh
0x180055123  jnz     short loc_18005514F
0x180055125  mov     r9d, 1; unsigned int
0x18005512b  lea     r8, aEnabledstate; "EnabledState"
0x180055132  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180055139  mov     rcx, 0FFFFFFFF80000001h; HKEY
0x180055140  call    ?SHRegSetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; SHRegSetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x180055145  mov     [rsp+558h+nSize], 1
0x18005514d  jmp     short loc_180055183
0x18005514f  mov     r8d, r14d; int
0x180055152  mov     edx, ebx; int
0x180055154  lea     rcx, aFailedToApplyD_0; "Failed to apply desktop spotlight and r"...
0x18005515b  call    ?s_UpdateResultOrLogFailure@CThemeManager2@@CAJPEBGJJ@Z; CThemeManager2::s_UpdateResultOrLogFailure(ushort const *,long,long)
0x180055160  mov     [rsp+558h+var_508], esi
0x180055164  mov     r12d, [rsp+558h+var_514]
0x180055169  mov     rax, [r15]
0x18005516c  lea     r8, [rsp+558h+var_508]
0x180055171  mov     edx, r12d
0x180055174  mov     rcx, r15
0x180055177  mov     rax, [rax+50h]
0x18005517b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055180  mov     r14d, eax
0x180055183  lea     rcx, [rsp+558h+nSize]
0x180055188  call    ??$DesktopSpotlightThemeEnabled@AEAJ@ThemesTelemetry@@SAXAEAJ@Z; ThemesTelemetry::DesktopSpotlightThemeEnabled<long &>(long &)
0x18005518d  jmp     short loc_180055205
0x18005518f  mov     [rsp+558h+nSize], esi
0x180055193  lea     rcx, [rsp+558h+bstrString]; this
0x180055198  call    ??0UserProfilePersonalizationSettings@UserProfile@System@WindowsUdk@winrt@@QEAA@XZ; winrt::WindowsUdk::System::UserProfile::UserProfilePersonalizationSettings::UserProfilePersonalizationSettings(void)
0x18005519d  nop
0x18005519e  lea     rcx, [rsp+558h+bstrString]
0x1800551a3  call    ?WallpaperCount@?$consume_WindowsUdk_UI_Shell_DesktopSpotlight_IDesktopSpotlightExtension@UIDesktopSpotlightExtension@DesktopSpotlight@Shell@UI@WindowsUdk@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_WindowsUdk_UI_Shell_DesktopSpotlight_IDesktopSpotlightExtension<winrt::WindowsUdk::UI::Shell::DesktopSpotlight::IDesktopSpotlightExtension>::WallpaperCount(void)
0x1800551a8  cmp     eax, 1
0x1800551ab  jnz     short loc_1800551C1
0x1800551ad  mov     [rsp+558h+var_4E8], esi
0x1800551b1  lea     rdx, [rsp+558h+var_4E8]
0x1800551b6  lea     rcx, [rsp+558h+bstrString]
0x1800551bb  call    ?DesktopSpotlightStatus@?$consume_WindowsUdk_System_UserProfile_IUserProfilePersonalizationSettings@UIUserProfilePersonalizationSettings@UserProfile@System@WindowsUdk@winrt@@@impl@winrt@@QEBA@AEBW40UserProfile@System@WindowsUdk@3@@Z; winrt::impl::consume_WindowsUdk_System_UserProfile_IUserProfilePersonalizationSettings<winrt::WindowsUdk::System::UserProfile::IUserProfilePersonalizationSettings>::DesktopSpotlightStatus(winrt::WindowsUdk::System::UserProfile::DesktopSpotlightStatus const &)
0x1800551c0  nop
0x1800551c1  lea     rcx, [rsp+558h+bstrString]; this
0x1800551c6  call    ??1IAsyncAction@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IAsyncAction::~IAsyncAction(void)
0x1800551cb  nop
0x1800551cc  jmp     short loc_1800551FA
0x1800551ce  xor     esi, esi
0x1800551d0  mov     eax, [rsp+558h+arg_20]
0x1800551d7  mov     [rsp+558h+var_504], eax
0x1800551db  mov     r14d, [rsp+558h+var_4E4]
0x1800551e0  mov     r15, [rsp+558h+var_4D0]
0x1800551e8  mov     rax, [rsp+558h+var_4C8]
0x1800551f0  mov     [rsp+558h+hwndOwner], rax
0x1800551f5  mov     r12d, [rsp+558h+var_4E0]
0x1800551fa  lea     rcx, [rsp+558h+nSize]
0x1800551ff  call    ??$DesktopSpotlightThemeDisabled@AEAJ@ThemesTelemetry@@SAXAEAJ@Z; ThemesTelemetry::DesktopSpotlightThemeDisabled<long &>(long &)
0x180055204  nop
0x180055205  lea     rcx, [rsp+558h+var_4F0]
0x18005520a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18005520f  test    r14d, r14d
0x180055212  js      loc_1800553BA
0x180055218  mov     eax, [rsp+558h+var_508]
0x18005521c  test    eax, eax
0x18005521e  jnz     loc_1800553B4
0x180055224  lea     rdi, [r15+850h]
0x18005522b  mov     rax, [r15]
0x18005522e  mov     r8, rdi
0x180055231  mov     edx, r12d
0x180055234  mov     rcx, r15
0x180055237  mov     rax, [rax+48h]
0x18005523b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055240  mov     r14d, eax
0x180055243  test    eax, eax
0x180055245  js      loc_1800553BA
0x18005524b  mov     [rsp+558h+bstrString], rsi
0x180055250  mov     rcx, [rdi]
0x180055253  mov     rax, [rcx]
0x180055256  or      edx, 0FFFFFFFFh
0x180055259  lea     r8, [rsp+558h+bstrString]
0x18005525e  mov     rax, [rax+120h]
0x180055265  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005526a  mov     r14d, eax
0x18005526d  test    eax, eax
0x18005526f  js      loc_180055390
0x180055275  lea     r13, [r15+0Ch]
0x180055279  mov     r8, [rsp+558h+bstrString]; unsigned __int16 *
0x18005527e  mov     edx, 104h; unsigned __int64
0x180055283  mov     rcx, r13; unsigned __int16 *
0x180055286  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18005528b  mov     r14d, eax
0x18005528e  test    eax, eax
0x180055290  js      loc_180055390
0x180055296  mov     [rsp+558h+nSize], esi
0x18005529a  mov     rcx, [rdi]
0x18005529d  mov     rax, [rcx]
0x1800552a0  lea     rdx, [rsp+558h+nSize]
0x1800552a5  mov     rax, [rax+1D0h]
0x1800552ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800552b1  test    eax, eax
0x1800552b3  js      short loc_1800552BD
0x1800552b5  cmp     [rsp+558h+nSize], esi
0x1800552b9  mov     dl, 1
0x1800552bb  jg      short loc_1800552C0
0x1800552bd  mov     dl, sil; bool
0x1800552c0  mov     rcx, r15; this
0x1800552c3  call    ?_SetCurrentThemeInRegistry@CThemeManager2@@AEAAJ_N@Z; CThemeManager2::_SetCurrentThemeInRegistry(bool)
0x1800552c8  mov     r14d, eax
0x1800552cb  cmp     [rsp+558h+arg_18], esi
0x1800552d2  jz      loc_180055390
0x1800552d8  test    eax, eax
0x1800552da  js      loc_180055390
0x1800552e0  lea     rbx, [r15+848h]
0x1800552e7  mov     rax, [r15]
0x1800552ea  mov     rax, [rax+48h]
0x1800552ee  mov     edx, [rsp+558h+var_514]
0x1800552f2  mov     r8, rbx
0x1800552f5  mov     rcx, r15
0x1800552f8  cmp     edx, 0FFFFFFFFh
0x1800552fb  jnz     short loc_180055300
0x1800552fd  mov     edx, r12d
0x180055300  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055305  mov     r14d, eax
0x180055308  test    eax, eax
0x18005530a  js      loc_180055390
0x180055310  mov     rax, [rsp+558h+var_4D8]
0x180055318  movzx   eax, byte ptr [rax]
0x18005531b  mov     dword ptr [rsp+558h+pszContent], eax
0x18005531f  mov     r9d, [rsp+558h+var_514]
0x180055324  mov     r8d, r12d
0x180055327  mov     rdx, r13
0x18005532a  lea     rcx, aCthememanager2; "CThemeManager2::SetCurrentTheme path=%w"...
0x180055331  call    ?TraceLoggingInfo@ThemesTelemetry@@SAXPEBDZZ; ThemesTelemetry::TraceLoggingInfo(char const *,...)
0x180055336  mov     r9d, [rsp+558h+arg_28]
0x18005533e  mov     r8d, [rsp+558h+var_504]
0x180055343  mov     r12, [rsp+558h+hwndOwner]
0x180055348  mov     rdx, r12
0x18005534b  mov     rcx, r15
0x18005534e  call    ?_ApplyTheme@CThemeManager2@@AEAAJPEAUHWND__@@W4THEME_APPLY_FLAGS@@W4THEMEPACK_FLAGS@@@Z; CThemeManager2::_ApplyTheme(HWND__ *,THEME_APPLY_FLAGS,THEMEPACK_FLAGS)
0x180055353  mov     r14d, eax
0x180055356  test    eax, eax
0x180055358  js      short loc_18005537C
0x18005535a  test    cs:Microsoft_Windows_ThemeUIEnableBits, 1
0x180055361  jz      short loc_180055372
0x180055363  mov     r8, r13
0x180055366  lea     rdx, ThemeSelected_Info
0x18005536d  call    McTemplateU0z_EtwEventWriteTransfer
0x180055372  mov     ecx, 2; lParam
0x180055377  call    ?NotifyThemeCPLs@@YAX_J@Z; NotifyThemeCPLs(__int64)
0x18005537c  mov     rcx, [rbx]
0x18005537f  mov     rax, [rcx]
0x180055382  mov     rax, [rax+10h]
0x180055386  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
