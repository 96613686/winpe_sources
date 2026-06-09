# Windows::Internal::Shell::Update::GetShellMinMaxVersion(winrt::hstring *,winrt::hstring *)

- ea: `0x180141f60`
- end: `0x180142704`
- name: `?GetShellMinMaxVersion@Update@Shell@Internal@Windows@@YA_NPEAUhstring@winrt@@0@Z`
- size: `1956`
- prototype: `bool __fastcall(Windows::Internal::Shell::Update *__hidden this, struct winrt::hstring *, struct winrt::hstring *)`
- caller_count: `1`
- callee_count: `21`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180298550`

## callees

- `0x18000dfa8`
- `0x18000fea0`
- `0x180010940`
- `0x18001ff78`
- `0x1800227a4`
- `0x180023098`
- `0x180025264`
- `0x180025348`
- `0x180025584`
- `0x1800260c0`
- `0x180026860`
- `0x180027af0`
- `0x18002ddb0`
- `0x1800a14f8`
- `0x1800e488c`
- `0x180141f60`
- `0x18014270c`
- `0x18015cb00`
- `0x1802957a0`
- `0x1802965c8`
- `0x18029774c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetProcessTimes` at `0x1801421a5`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessTimes` at `0x1801421a5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180141fc8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180142007`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180141fc8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180142007`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1801420f0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18014213f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180142203`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1801420f0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18014213f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180142203`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1801420ab`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1801420ab`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18014232a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18014232a`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180142164`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180142164`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1801421bb`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1801421bb`

## string_xrefs

- `0x180142040`: `ShellCommonDesktopBase\Internal\ShellCommonDesktopBase\Inc\Windows.Internal.Shell.UpdateClient.h`
- `0x180141fb7`: `Software\Microsoft\Windows\CurrentVersion\Shell\Update\Versions`
- `0x180141ffd`: `Software\Microsoft\Windows\CurrentVersion\Shell\Update\Versions`
- `0x180142130`: `CreateTime`

## pseudocode

```c
// Hidden C++ exception states: #wind=40
char __fastcall Windows::Internal::Shell::Update::GetShellMinMaxVersion(
        Windows::Internal::Shell::Update *this,
        struct winrt::hstring *a2,
        struct winrt::hstring *a3)
{
  char v3; // r14
  HKEY *v4; // rax
  int v5; // eax
  char v6; // r15
  HKEY *v7; // rax
  DWORD v9; // esi
  char v10; // r12
  char v11; // r13
  __int64 v12; // rbx
  __int64 v13; // rdi
  LSTATUS v14; // eax
  LSTATUS ValueW; // eax
  bool v16; // sf
  LSTATUS v17; // eax
  bool v18; // sf
  char *v19; // rax
  LSTATUS v20; // eax
  bool v21; // sf
  Windows::Internal::Shell::Update *v22; // rax
  const wchar_t *v23; // rdx
  struct winrt::Windows::ApplicationModel::PackageVersion *v24; // r9
  const struct winrt::Windows::ApplicationModel::PackageVersion *v25; // r8
  const struct winrt::Windows::ApplicationModel::PackageVersion *v26; // r8
  __int64 v27; // rax
  LPCWSTR v28; // rbx
  LPCWSTR v29; // rdi
  const WCHAR *v30; // rdx
  __int64 v31; // rax
  __int64 v32; // rax
  __int64 v33; // rax
  __int64 v34; // rax
  __int64 v35; // rax
  Windows::Internal::Shell::Update *v36; // rax
  Windows::Internal::Shell::Update *v37; // r14
  __int64 v38; // rdx
  __int64 v39; // rax
  __int64 v40; // rax
  __int64 v41; // rax
  __int64 v42; // rax
  __int64 v43; // rax
  struct winrt::hstring *v44; // rax
  struct winrt::hstring *v45; // rcx
  __int64 v46; // rdx
  int phkResult; // [rsp+20h] [rbp-E0h]
  wchar_t v48[4]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v49; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v50; // [rsp+50h] [rbp-B0h] BYREF
  char *v51; // [rsp+58h] [rbp-A8h] BYREF
  Windows::Internal::Shell::Update *v52; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v53[8]; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v54[8]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v55[8]; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v56[8]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v57[8]; // [rsp+88h] [rbp-78h] BYREF
  struct winrt::hstring *v58; // [rsp+90h] [rbp-70h]
  _BYTE v59[32]; // [rsp+98h] [rbp-68h] BYREF
  DWORD v60; // [rsp+B8h] [rbp-48h] BYREF
  DWORD pvData; // [rsp+C0h] [rbp-40h] BYREF
  HKEY hKey; // [rsp+C8h] [rbp-38h] BYREF
  struct _FILETIME ExitTime; // [rsp+D0h] [rbp-30h] BYREF
  DWORD v64; // [rsp+D8h] [rbp-28h] BYREF
  struct _FILETIME CreationTime; // [rsp+E0h] [rbp-20h] BYREF
  FILETIME FileTime1; // [rsp+E8h] [rbp-18h] BYREF
  _BYTE v67[8]; // [rsp+F0h] [rbp-10h] BYREF
  DWORD cchName; // [rsp+F8h] [rbp-8h] BYREF
  DWORD pcbData; // [rsp+100h] [rbp+0h] BYREF
  LPCWSTR lpSubKey[2]; // [rsp+108h] [rbp+8h] BYREF
  __int64 v71; // [rsp+118h] [rbp+18h]
  WCHAR Name[264]; // [rsp+120h] [rbp+20h] BYREF
  wchar_t v73[264]; // [rsp+330h] [rbp+230h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+588h] [rbp+488h]

  v58 = a2;
  v52 = this;
  v3 = 0;
  hKey = 0;
  v4 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hKey);
  v5 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\Shell\\Update\\Versions",
         0,
         0xF003Fu,
         v4);
  if ( v5 > 0 )
    v5 = (unsigned __int16)v5 | 0x80070000;
  if ( v5 == -2147024891 )
  {
    v6 = 0;
    v7 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hKey);
    v5 = RegOpenKeyExW(
           HKEY_LOCAL_MACHINE,
           L"Software\\Microsoft\\Windows\\CurrentVersion\\Shell\\Update\\Versions",
           0,
           0x20019u,
           v7);
    if ( v5 > 0 )
      v5 = (unsigned __int16)v5 | 0x80070000;
  }
  else
  {
    v6 = 1;
  }
  if ( v5 == -2147024894 )
  {
LABEL_8:
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    return 0;
  }
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x7E,
      (unsigned int)"ShellCommonDesktopBase\\Internal\\ShellCommonDesktopBase\\Inc\\Windows.Internal.Shell.UpdateClient.h",
      (const char *)(unsigned int)v5,
      phkResult);
  v9 = 0;
  v49 = 0;
  v50 = 0;
  v10 = 0;
  v11 = 1;
  *(_OWORD *)lpSubKey = 0;
  v71 = 0;
  std::vector<winrt::com_ptr<winrt::WindowsUdk::ApplicationModel::OnScreenInput::implementation::TextInputCandidateWindowState>>::vector<winrt::com_ptr<winrt::WindowsUdk::ApplicationModel::OnScreenInput::implementation::TextInputCandidateWindowState>>(lpSubKey);
  v12 = 0;
  v13 = 0;
  while ( 1 )
  {
    cchName = 260;
    v14 = RegEnumKeyExW(hKey, v9, Name, &cchName, 0, 0, 0, 0);
    if ( v14 )
      break;
    pvData = 0;
    pcbData = 4;
    ValueW = RegGetValueW(hKey, Name, L"PID", 0x10u, 0, &pvData, &pcbData);
    v16 = ValueW < 0;
    if ( ValueW > 0 )
      v16 = 1;
    if ( v16 )
      goto LABEL_35;
    FileTime1 = 0;
    v64 = 8;
    v17 = RegGetValueW(hKey, Name, L"CreateTime", 8u, 0, &FileTime1, &v64);
    v18 = v17 < 0;
    if ( v17 > 0 )
      v18 = 1;
    if ( v18 )
      goto LABEL_35;
    v19 = (char *)OpenProcess(0x1000u, 0, pvData);
    v51 = v19;
    CreationTime = 0;
    ExitTime = 0;
    if ( (unsigned __int64)(v19 - 1) <= 0xFFFFFFFFFFFFFFFDuLL
      && GetProcessTimes(v19, &CreationTime, &ExitTime, &ExitTime, &ExitTime)
      && !CompareFileTime(&FileTime1, &CreationTime) )
    {
      v60 = 260;
      v20 = RegGetValueW(hKey, Name, L"Version", 2u, 0, v73, &v60);
      v21 = v20 < 0;
      if ( v20 > 0 )
        v21 = 1;
      if ( !v21 )
      {
        winrt::hstring::hstring((winrt::hstring *)v67, v73, (v60 >> 1) - 1);
        *(_QWORD *)v48 = 0;
        v22 = (Windows::Internal::Shell::Update *)winrt::hstring::c_str((winrt::hstring *)v67);
        if ( Windows::Internal::Shell::Update::ParsePackageVersion(v22, v23, (wchar_t)v48, v24) )
        {
          v10 = 1;
          v3 = 1;
          if ( v11 )
          {
            v12 = *(_QWORD *)v48;
            v49 = *(_QWORD *)v48;
            v13 = *(_QWORD *)v48;
            v50 = *(_QWORD *)v48;
            v11 = 0;
          }
          else
          {
            if ( (int)Windows::Internal::Shell::Update::ComparePackageVersion(
                        (Windows::Internal::Shell::Update *)&v49,
                        (const struct winrt::Windows::ApplicationModel::PackageVersion *)v48,
                        v25) > 0 )
              v12 = *(_QWORD *)v48;
            v49 = v12;
            if ( (int)Windows::Internal::Shell::Update::ComparePackageVersion(
                        (Windows::Internal::Shell::Update *)&v50,
                        (const struct winrt::Windows::ApplicationModel::PackageVersion *)v48,
                        v26) < 0 )
              v13 = *(_QWORD *)v48;
            v50 = v13;
          }
        }
        winrt::handle_type<winrt::impl::hstring_traits>::close(v67);
      }
    }
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v51);
    if ( !v3 )
    {
LABEL_35:
      v27 = std::wstring::wstring(v59, Name);
      std::vector<std::wstring>::_Emplace_one_at_back<std::wstring>(lpSubKey, v27);
      std::filesystem::path::~path((std::filesystem::path *)v59);
    }
LABEL_37:
    ++v9;
    v3 = 0;
  }
  if ( v14 != 259 )
    goto LABEL_37;
  if ( v6 )
  {
    v28 = lpSubKey[0];
    v29 = lpSubKey[1];
    while ( v28 != v29 )
    {
      if ( *((_QWORD *)v28 + 3) <= 7u )
        v30 = v28;
      else
        v30 = *(const WCHAR **)v28;
      RegDeleteKeyExW(hKey, v30, 0, 0);
      v28 += 16;
    }
  }
  if ( !v10 )
  {
    std::vector<std::wstring>::_Tidy(lpSubKey);
    goto LABEL_8;
  }
  winrt::impl::hstring_convert<unsigned short>(&pvData, HIWORD(v49));
  winrt::hstring::hstring((winrt::hstring *)&v60, L".");
  winrt::hstring::hstring((winrt::hstring *)&cchName, (const struct winrt::hstring *)&v60);
  winrt::impl::hstring_convert<unsigned short>(&pcbData, WORD2(v49));
  winrt::hstring::hstring((winrt::hstring *)&v64, L".");
  winrt::hstring::hstring((winrt::hstring *)v48, (const struct winrt::hstring *)&v64);
  winrt::impl::hstring_convert<unsigned short>(&ExitTime, WORD1(v49));
  winrt::hstring::hstring((winrt::hstring *)&CreationTime, L".");
  winrt::hstring::hstring((winrt::hstring *)&FileTime1, (const struct winrt::hstring *)&CreationTime);
  winrt::impl::hstring_convert<unsigned short>(v67, (unsigned __int16)v49);
  v31 = winrt::operator+(v57, v67, &FileTime1);
  v32 = winrt::operator+(v56, v31, &ExitTime);
  v33 = winrt::operator+(v55, v32, v48);
  v34 = winrt::operator+(v54, v33, &pcbData);
  v35 = winrt::operator+(v53, v34, &cchName);
  v36 = (Windows::Internal::Shell::Update *)winrt::operator+(&v51, v35, &pvData);
  v37 = v52;
  if ( v52 != v36 )
  {
    v38 = *(_QWORD *)v36;
    *(_QWORD *)v36 = 0;
    winrt::handle_type<winrt::impl::hstring_traits>::attach(v37, v38);
  }
  winrt::handle_type<winrt::impl::hstring_traits>::close(&v51);
  winrt::handle_type<winrt::impl::hstring_traits>::close(v53);
  winrt::handle_type<winrt::impl::hstring_traits>::close(v54);
  winrt::handle_type<winrt::impl::hstring_traits>::close(v55);
  winrt::handle_type<winrt::impl::hstring_traits>::close(v56);
  winrt::handle_type<winrt::impl::hstring_traits>::close(v57);
  winrt::handle_type<winrt::impl::hstring_traits>::close(v67);
  winrt::handle_type<winrt::impl::hstring_traits>::close(&FileTime1);
  winrt::handle_type<winrt::impl::hstring_traits>::close(&CreationTime);
  winrt::handle_type<winrt::impl::hstring_traits>::close(&ExitTime);
  winrt::handle_type<winrt::impl::hstring_traits>::close(v48);
  winrt::handle_type<winrt::impl::hstring_traits>::close(&v64);
  winrt::handle_type<winrt::impl::hstring_traits>::close(&pcbData);
  winrt::handle_type<winrt::impl::hstring_traits>::close(&cchName);
  winrt::handle_type<winrt::impl::hstring_traits>::close(&v60);
  winrt::handle_type<winrt::impl::hstring_traits>::close(&pvData);
  winrt::impl::hstring_convert<unsigned short>(&v60, HIWORD(v50));
  winrt::hstring::hstring((winrt::hstring *)&cchName, L".");
  winrt::hstring::hstring((winrt::hstring *)&pcbData, (const struct winrt::hstring *)&cchName);
  winrt::impl::hstring_convert<unsigned short>(&v64, WORD2(v50));
  winrt::hstring::hstring((winrt::hstring *)&v49, L".");
  winrt::hstring::hstring((winrt::hstring *)v48, (const struct winrt::hstring *)&v49);
  winrt::impl::hstring_convert<unsigned short>(&ExitTime, WORD1(v50));
  winrt::hstring::hstring((winrt::hstring *)&CreationTime, L".");
  winrt::hstring::hstring((winrt::hstring *)&FileTime1, (const struct winrt::hstring *)&CreationTime);
  winrt::impl::hstring_convert<unsigned short>(v67, (unsigned __int16)v50);
  v39 = winrt::operator+(&v52, v67, &FileTime1);
  v40 = winrt::operator+(v53, v39, &ExitTime);
  v41 = winrt::operator+(v54, v40, v48);
  v42 = winrt::operator+(v55, v41, &v64);
  v43 = winrt::operator+(v56, v42, &pcbData);
  v44 = (struct winrt::hstring *)winrt::operator+(v57, v43, &v60);
  v45 = v58;
  if ( v58 != v44 )
  {
    v46 = *(_QWORD *)v44;
    *(_QWORD *)v44 = 0;
    winrt::handle_type<winrt::impl::hstring_traits>::attach(v45, v46);
  }
  winrt::handle_type<winrt::impl::hstring_traits>::close(v57);
  winrt::handle_type<winrt::impl::hstring_traits>::close(v56);
  winrt::handle_type<winrt::impl::hstring_traits>::close(v55);
  winrt::handle_type<winrt::impl::hstring_traits>::close(v54);
  winrt::handle_type<winrt::impl::hstring_traits>::close(v53);
  winrt::handle_type<winrt::impl::hstring_traits>::close(&v52);
  winrt::handle_type<winrt::impl::hstring_traits>::close(v67);
  winrt::handle_type<winrt::impl::hstring_traits>::close(&FileTime1);
  winrt::handle_type<winrt::impl::hstring_traits>::close(&CreationTime);
  winrt::handle_type<winrt::impl::hstring_traits>::close(&ExitTime);
  winrt::handle_type<winrt::impl::hstring_traits>::close(v48);
  winrt::handle_type<winrt::impl::hstring_traits>::close(&v49);
  winrt::handle_type<winrt::impl::hstring_traits>::close(&v64);
  winrt::handle_type<winrt::impl::hstring_traits>::close(&pcbData);
  winrt::handle_type<winrt::impl::hstring_traits>::close(&cchName);
  winrt::handle_type<winrt::impl::hstring_traits>::close(&v60);
  std::vector<std::wstring>::_Tidy(lpSubKey);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return 1;
}

```

## disassembly

```asm
0x180141f60  mov     [rsp-8+arg_10], rbx
0x180141f65  push    rbp
0x180141f66  push    rsi
0x180141f67  push    rdi
0x180141f68  push    r12
0x180141f6a  push    r13
0x180141f6c  push    r14
0x180141f6e  push    r15
0x180141f70  lea     rbp, [rsp-450h]
0x180141f78  sub     rsp, 550h
0x180141f7f  mov     rax, cs:__security_cookie
0x180141f86  xor     rax, rsp
0x180141f89  mov     [rbp+480h+var_40], rax
0x180141f90  mov     [rbp+480h+var_4F0], rdx
0x180141f94  mov     [rsp+580h+var_520], rcx
0x180141f99  xor     r14d, r14d
0x180141f9c  mov     [rbp+480h+hKey], r14
0x180141fa0  lea     rcx, [rbp+480h+hKey]
0x180141fa4  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x180141fa9  mov     [rsp+580h+phkResult], rax; int
0x180141fae  mov     r9d, 0F003Fh; samDesired
0x180141fb4  xor     r8d, r8d; ulOptions
0x180141fb7  lea     rdx, ?c_shellUpdateVersionsRegKey@Update@Shell@Internal@Windows@@3QB_WB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180141fbe  mov     rdi, 0FFFFFFFF80000002h
0x180141fc5  mov     rcx, rdi; hKey
0x180141fc8  call    cs:__imp_RegOpenKeyExW
0x180141fce  mov     ebx, 80070000h
0x180141fd3  test    eax, eax
0x180141fd5  jle     short loc_180141FDC
0x180141fd7  movzx   eax, ax
0x180141fda  or      eax, ebx
0x180141fdc  cmp     eax, 80070005h
0x180141fe1  jnz     short loc_180142018
0x180141fe3  mov     r15b, r14b
0x180141fe6  lea     rcx, [rbp+480h+hKey]
0x180141fea  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x180141fef  mov     [rsp+580h+phkResult], rax; phkResult
0x180141ff4  mov     r9d, 20019h; samDesired
0x180141ffa  xor     r8d, r8d; ulOptions
0x180141ffd  lea     rdx, ?c_shellUpdateVersionsRegKey@Update@Shell@Internal@Windows@@3QB_WB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180142004  mov     rcx, rdi; hKey
0x180142007  call    cs:__imp_RegOpenKeyExW
0x18014200d  test    eax, eax
0x18014200f  jle     short loc_18014201B
0x180142011  movzx   eax, ax
0x180142014  or      eax, ebx
0x180142016  jmp     short loc_18014201B
0x180142018  mov     r15b, 1
0x18014201b  cmp     eax, 80070002h
0x180142020  jnz     short loc_180142032
0x180142022  lea     rcx, [rbp+480h+hKey]
0x180142026  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18014202b  xor     al, al
0x18014202d  jmp     loc_1801426DA
0x180142032  mov     rcx, [rbp+488h]; this
0x180142039  test    eax, eax
0x18014203b  jns     short loc_180142052
0x18014203d  mov     r9d, eax; char *
0x180142040  lea     r8, aShellcommondes_5; "ShellCommonDesktopBase\\Internal\\Shell"...
0x180142047  mov     edx, 7Eh ; '~'; void *
0x18014204c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180142052  mov     esi, r14d
0x180142055  mov     [rsp+580h+var_538], r14
0x18014205a  mov     [rsp+580h+var_530], r14
0x18014205f  mov     r12b, r14b
0x180142062  mov     r13b, 1
0x180142065  xorps   xmm0, xmm0
0x180142068  xor     eax, eax
0x18014206a  movups  xmmword ptr [rbp+480h+lpSubKey], xmm0
0x18014206e  mov     [rbp+480h+var_468], rax
0x180142072  lea     rcx, [rbp+480h+lpSubKey]
0x180142076  call    ??0?$vector@U?$com_ptr@UTextInputCandidateWindowState@implementation@OnScreenInput@ApplicationModel@WindowsUdk@winrt@@@winrt@@V?$allocator@U?$com_ptr@UTextInputCandidateWindowState@implementation@OnScreenInput@ApplicationModel@WindowsUdk@winrt@@@winrt@@@std@@@std@@QEAA@XZ; std::vector<winrt::com_ptr<winrt::WindowsUdk::ApplicationModel::OnScreenInput::implementation::TextInputCandidateWindowState>>::vector<winrt::com_ptr<winrt::WindowsUdk::ApplicationModel::OnScreenInput::implementation::TextInputCandidateWindowState>>(void)
0x18014207b  nop
0x18014207c  mov     rbx, r14
0x18014207f  mov     rdi, r14
0x180142082  mov     [rbp+480h+cchName], 104h
0x180142089  mov     [rsp+580h+lpftLastWriteTime], r14; lpftLastWriteTime
0x18014208e  mov     [rsp+580h+lpcchClass], r14; lpcchClass
0x180142093  mov     [rsp+580h+lpClass], r14; lpClass
0x180142098  mov     [rsp+580h+phkResult], r14; lpReserved
0x18014209d  lea     r9, [rbp+480h+cchName]; lpcchName
0x1801420a1  lea     r8, [rbp+480h+Name]; lpName
0x1801420a5  mov     edx, esi; dwIndex
0x1801420a7  mov     rcx, [rbp+480h+hKey]; hKey
0x1801420ab  call    cs:__imp_RegEnumKeyExW
0x1801420b1  test    eax, eax
0x1801420b3  jnz     loc_1801422F1
0x1801420b9  mov     [rbp+480h+pvData], r14d
0x1801420bd  mov     [rbp+480h+pcbData], 4
0x1801420c4  lea     rax, [rbp+480h+pcbData]
0x1801420c8  mov     [rsp+580h+lpcchClass], rax; pcbData
0x1801420cd  lea     rax, [rbp+480h+pvData]
0x1801420d1  mov     [rsp+580h+lpClass], rax; pvData
0x1801420d6  mov     [rsp+580h+phkResult], r14; pdwType
0x1801420db  mov     r9d, 10h; dwFlags
0x1801420e1  lea     r8, aPid; "PID"
0x1801420e8  lea     rdx, [rbp+480h+Name]; lpSubKey
0x1801420ec  mov     rcx, [rbp+480h+hKey]; hkey
0x1801420f0  call    cs:__imp_RegGetValueW
0x1801420f6  test    eax, eax
0x1801420f8  jle     short loc_180142104
0x1801420fa  movzx   eax, ax
0x1801420fd  or      eax, 80070000h
0x180142102  test    eax, eax
0x180142104  js      loc_1801422CB
0x18014210a  mov     qword ptr [rbp+480h+FileTime1.dwLowDateTime], r14
0x18014210e  mov     ecx, 8
0x180142113  mov     [rbp+480h+var_4A8], ecx
0x180142116  lea     rax, [rbp+480h+var_4A8]
0x18014211a  mov     [rsp+580h+lpcchClass], rax; pcbData
0x18014211f  lea     rax, [rbp+480h+FileTime1]
0x180142123  mov     [rsp+580h+lpClass], rax; pvData
0x180142128  mov     [rsp+580h+phkResult], r14; pdwType
0x18014212d  mov     r9d, ecx; dwFlags
0x180142130  lea     r8, aCreatetime; "CreateTime"
0x180142137  lea     rdx, [rbp+480h+Name]; lpSubKey
0x18014213b  mov     rcx, [rbp+480h+hKey]; hkey
0x18014213f  call    cs:__imp_RegGetValueW
0x180142145  test    eax, eax
0x180142147  jle     short loc_180142153
0x180142149  movzx   eax, ax
0x18014214c  or      eax, 80070000h
0x180142151  test    eax, eax
0x180142153  js      loc_1801422CB
0x180142159  mov     r8d, [rbp+480h+pvData]; dwProcessId
0x18014215d  xor     edx, edx; bInheritHandle
0x18014215f  mov     ecx, 1000h; dwDesiredAccess
0x180142164  call    cs:__imp_OpenProcess
0x18014216a  mov     [rsp+580h+var_528], rax
0x18014216f  mov     qword ptr [rbp+480h+CreationTime.dwLowDateTime], 0
0x180142177  mov     qword ptr [rbp+480h+ExitTime.dwLowDateTime], 0
0x18014217f  lea     rcx, [rax-1]
0x180142183  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180142187  ja      loc_1801422BC
0x18014218d  lea     rcx, [rbp+480h+ExitTime]
0x180142191  mov     [rsp+580h+phkResult], rcx; lpUserTime
0x180142196  lea     r9, [rbp+480h+ExitTime]; lpKernelTime
0x18014219a  lea     r8, [rbp+480h+ExitTime]; lpExitTime
0x18014219e  lea     rdx, [rbp+480h+CreationTime]; lpCreationTime
0x1801421a2  mov     rcx, rax; hProcess
0x1801421a5  call    cs:__imp_GetProcessTimes
0x1801421ab  test    eax, eax
0x1801421ad  jz      loc_1801422BC
0x1801421b3  lea     rdx, [rbp+480h+CreationTime]; lpFileTime2
0x1801421b7  lea     rcx, [rbp+480h+FileTime1]; lpFileTime1
0x1801421bb  call    cs:__imp_CompareFileTime
0x1801421c1  test    eax, eax
0x1801421c3  jnz     loc_1801422BC
0x1801421c9  mov     [rbp+480h+var_4C8], 104h
0x1801421d0  lea     rax, [rbp+480h+var_4C8]
0x1801421d4  mov     [rsp+580h+lpcchClass], rax; pcbData
0x1801421d9  lea     rax, [rbp+480h+var_250]
0x1801421e0  mov     [rsp+580h+lpClass], rax; pvData
0x1801421e5  mov     [rsp+580h+phkResult], 0; pdwType
0x1801421ee  mov     r9d, 2; dwFlags
0x1801421f4  lea     r8, aVersion_0; "Version"
0x1801421fb  lea     rdx, [rbp+480h+Name]; lpSubKey
0x1801421ff  mov     rcx, [rbp+480h+hKey]; hkey
0x180142203  call    cs:__imp_RegGetValueW
0x180142209  test    eax, eax
0x18014220b  jle     short loc_180142217
0x18014220d  movzx   eax, ax
0x180142210  or      eax, 80070000h
0x180142215  test    eax, eax
0x180142217  js      loc_1801422BC
0x18014221d  mov     r8d, [rbp+480h+var_4C8]
0x180142221  shr     r8d, 1
0x180142224  dec     r8d; unsigned int
0x180142227  lea     rdx, [rbp+480h+var_250]; wchar_t *
0x18014222e  lea     rcx, [rbp+480h+var_490]; this
0x180142232  call    ??0hstring@winrt@@QEAA@PEB_WI@Z; winrt::hstring::hstring(wchar_t const *,uint)
0x180142237  xor     eax, eax
0x180142239  mov     qword ptr [rsp+580h+var_540], rax
0x18014223e  lea     rcx, [rbp+480h+var_490]; this
0x180142242  call    ?c_str@hstring@winrt@@QEBAPEB_WXZ; winrt::hstring::c_str(void)
0x180142247  mov     rcx, rax; this
0x18014224a  lea     r8, [rsp+580h+var_540]; wchar_t
0x18014224f  call    ?ParsePackageVersion@Update@Shell@Internal@Windows@@YA_NPEB_W_WPEAUPackageVersion@ApplicationModel@4winrt@@@Z; Windows::Internal::Shell::Update::ParsePackageVersion(wchar_t const *,wchar_t,winrt::Windows::ApplicationModel::PackageVersion *)
0x180142254  test    al, al
0x180142256  jz      short loc_1801422B2
0x180142258  mov     r12b, 1
0x18014225b  mov     r14b, r12b
0x18014225e  test    r13b, r13b
0x180142261  jz      short loc_18014227A
0x180142263  mov     rbx, qword ptr [rsp+580h+var_540]
0x180142268  mov     [rsp+580h+var_538], rbx
0x18014226d  mov     rdi, rbx
0x180142270  mov     [rsp+580h+var_530], rbx
0x180142275  xor     r13b, r13b
0x180142278  jmp     short loc_1801422B2
0x18014227a  lea     rdx, [rsp+580h+var_540]; struct winrt::Windows::ApplicationModel::PackageVersion *
0x18014227f  lea     rcx, [rsp+580h+var_538]; this
0x180142284  call    ?ComparePackageVersion@Update@Shell@Internal@Windows@@YAHAEBUPackageVersion@ApplicationModel@4winrt@@0@Z; Windows::Internal::Shell::Update::ComparePackageVersion(winrt::Windows::ApplicationModel::PackageVersion const &,winrt::Windows::ApplicationModel::PackageVersion const &)
0x180142289  test    eax, eax
0x18014228b  cmovg   rbx, qword ptr [rsp+580h+var_540]
0x180142291  mov     [rsp+580h+var_538], rbx
0x180142296  lea     rdx, [rsp+580h+var_540]; struct winrt::Windows::ApplicationModel::PackageVersion *
0x18014229b  lea     rcx, [rsp+580h+var_530]; this
0x1801422a0  call    ?ComparePackageVersion@Update@Shell@Internal@Windows@@YAHAEBUPackageVersion@ApplicationModel@4winrt@@0@Z; Windows::Internal::Shell::Update::ComparePackageVersion(winrt::Windows::ApplicationModel::PackageVersion const &,winrt::Windows::ApplicationModel::PackageVersion const &)
0x1801422a5  test    eax, eax
0x1801422a7  cmovs   rdi, qword ptr [rsp+580h+var_540]
0x1801422ad  mov     [rsp+580h+var_530], rdi
0x1801422b2  lea     rcx, [rbp+480h+var_490]
0x1801422b6  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1801422bb  nop
0x1801422bc  lea     rcx, [rsp+580h+var_528]
0x1801422c1  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1801422c6  test    r14b, r14b
0x1801422c9  jnz     short loc_1801422F8
0x1801422cb  lea     rdx, [rbp+480h+Name]
0x1801422cf  lea     rcx, [rbp+480h+var_4E8]
0x1801422d3  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1801422d8  nop
0x1801422d9  mov     rdx, rax
0x1801422dc  lea     rcx, [rbp+480h+lpSubKey]
0x1801422e0  call    ??$_Emplace_one_at_back@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_one_at_back<std::wstring>(std::wstring &&)
0x1801422e5  nop
0x1801422e6  lea     rcx, [rbp+480h+var_4E8]; this
0x1801422ea  call    ??1path@filesystem@std@@QEAA@XZ; std::filesystem::path::~path(void)
0x1801422ef  jmp     short loc_1801422F8
0x1801422f1  cmp     eax, 103h
0x1801422f6  jz      short loc_180142302
0x1801422f8  inc     esi
0x1801422fa  xor     r14d, r14d
0x1801422fd  jmp     loc_180142082
0x180142302  test    r15b, r15b
0x180142305  jz      short loc_180142339
0x180142307  mov     rbx, [rbp+480h+lpSubKey]
0x18014230b  mov     rdi, [rbp+480h+lpSubKey+8]
0x18014230f  jmp     short loc_180142334
0x180142311  cmp     qword ptr [rbx+18h], 7
0x180142316  jbe     short loc_18014231D
0x180142318  mov     rdx, [rbx]
0x18014231b  jmp     short loc_180142320
0x18014231d  mov     rdx, rbx; lpSubKey
0x180142320  xor     r9d, r9d; Reserved
0x180142323  xor     r8d, r8d; samDesired
0x180142326  mov     rcx, [rbp+480h+hKey]; hKey
0x18014232a  call    cs:__imp_RegDeleteKeyExW
0x180142330  add     rbx, 20h ; ' '
0x180142334  cmp     rbx, rdi
0x180142337  jnz     short loc_180142311
0x180142339  test    r12b, r12b
0x18014233c  jnz     short loc_18014234C
0x18014233e  lea     rcx, [rbp+480h+lpSubKey]
0x180142342  call    ?_Tidy@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180142347  jmp     loc_180142022
0x18014234c  movzx   edx, word ptr [rsp+580h+var_538+6]
0x180142351  lea     rcx, [rbp+480h+pvData]
0x180142355  call    ??$hstring_convert@G@impl@winrt@@YA?AUhstring@1@G@Z; winrt::impl::hstring_convert<ushort>(ushort)
0x18014235a  nop
0x18014235b  lea     rbx, asc_180502FF4; "."
0x180142362  mov     rdx, rbx; wchar_t *
0x180142365  lea     rcx, [rbp+480h+var_4C8]; this
0x180142369  call    ??0hstring@winrt@@QEAA@PEB_W@Z; winrt::hstring::hstring(wchar_t const *)
0x18014236e  nop
0x18014236f  lea     rdx, [rbp+480h+var_4C8]; struct winrt::hstring *
0x180142373  lea     rcx, [rbp+480h+cchName]; this
0x180142377  call    ??0hstring@winrt@@QEAA@AEBU01@@Z; winrt::hstring::hstring(winrt::hstring const &)
0x18014237c  nop
0x18014237d  movzx   edx, word ptr [rsp+580h+var_538+4]
0x180142382  lea     rcx, [rbp+480h+pcbData]
0x180142386  call    ??$hstring_convert@G@impl@winrt@@YA?AUhstring@1@G@Z; winrt::impl::hstring_convert<ushort>(ushort)
0x18014238b  nop
0x18014238c  mov     rdx, rbx; wchar_t *
0x18014238f  lea     rcx, [rbp+480h+var_4A8]; this
0x180142393  call    ??0hstring@winrt@@QEAA@PEB_W@Z; winrt::hstring::hstring(wchar_t const *)
0x180142398  nop
0x180142399  lea     rdx, [rbp+480h+var_4A8]; struct winrt::hstring *
0x18014239d  lea     rcx, [rsp+580h+var_540]; this
0x1801423a2  call    ??0hstring@winrt@@QEAA@AEBU01@@Z; winrt::hstring::hstring(winrt::hstring const &)
0x1801423a7  nop
0x1801423a8  movzx   edx, word ptr [rsp+580h+var_538+2]
0x1801423ad  lea     rcx, [rbp+480h+ExitTime]
0x1801423b1  call    ??$hstring_convert@G@impl@winrt@@YA?AUhstring@1@G@Z; winrt::impl::hstring_convert<ushort>(ushort)
0x1801423b6  nop
0x1801423b7  mov     rdx, rbx; wchar_t *
0x1801423ba  lea     rcx, [rbp+480h+CreationTime]; this
0x1801423be  call    ??0hstring@winrt@@QEAA@PEB_W@Z; winrt::hstring::hstring(wchar_t const *)
0x1801423c3  nop
0x1801423c4  lea     rdx, [rbp+480h+CreationTime]; struct winrt::hstring *
0x1801423c8  lea     rcx, [rbp+480h+FileTime1]; this
0x1801423cc  call    ??0hstring@winrt@@QEAA@AEBU01@@Z; winrt::hstring::hstring(winrt::hstring const &)
0x1801423d1  nop
0x1801423d2  movzx   edx, word ptr [rsp+580h+var_538]
0x1801423d7  lea     rcx, [rbp+480h+var_490]
0x1801423db  call    ??$hstring_convert@G@impl@winrt@@YA?AUhstring@1@G@Z; winrt::impl::hstring_convert<ushort>(ushort)
0x1801423e0  nop
0x1801423e1  lea     r8, [rbp+480h+FileTime1]
0x1801423e5  lea     rdx, [rbp+480h+var_490]
0x1801423e9  lea     rcx, [rbp+480h+var_4F8]
0x1801423ed  call    ??Hwinrt@@YA?AUhstring@0@AEBU10@0@Z; winrt::operator+(winrt::hstring const &,winrt::hstring const &)
0x1801423f2  nop
0x1801423f3  lea     r8, [rbp+480h+ExitTime]
0x1801423f7  mov     rdx, rax
0x1801423fa  lea     rcx, [rbp+480h+var_500]
0x1801423fe  call    ??Hwinrt@@YA?AUhstring@0@AEBU10@0@Z; winrt::operator+(winrt::hstring const &,winrt::hstring const &)
0x180142403  nop
0x180142404  lea     r8, [rsp+580h+var_540]
0x180142409  mov     rdx, rax
  ... truncated ...
```
