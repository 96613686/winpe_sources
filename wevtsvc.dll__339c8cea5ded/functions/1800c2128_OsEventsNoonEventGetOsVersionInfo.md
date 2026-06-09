# OsEventsNoonEventGetOsVersionInfo

- ea: `0x1800c2128`
- end: `0x1800c2350`
- name: `OsEventsNoonEventGetOsVersionInfo`
- size: `552`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800945d0`

## callees

- `0x180006770`
- `0x180017b98`
- `0x18006c144`
- `0x18009aee0`
- `0x18009bb88`
- `0x1800c1f28`
- `0x1800c2128`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800c2237`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800c227d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800c22f3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800c2237`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800c227d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800c22f3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c21fa`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c21fa`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x1800c216c`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x1800c216c`
- `api-ms-win-core-localization-l1-2-0!GetSystemDefaultLangID` at `0x1800c231d`
- `api-ms-win-core-localization-l1-2-0!GetSystemDefaultLangID` at `0x1800c231d`

## string_xrefs

- `0x1800c22a8`: `InstallDate`

## pseudocode

```c
__int64 __fastcall OsEventsNoonEventGetOsVersionInfo(__int64 a1)
{
  WCHAR *szCSDVersion; // rax
  _WORD *v3; // rdi
  HKEY *phkResult; // rax
  DWORD cbData; // [rsp+40h] [rbp-C0h] BYREF
  DWORD Type; // [rsp+44h] [rbp-BCh] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  struct _OSVERSIONINFOW VersionInformation; // [rsp+50h] [rbp-B0h] BYREF

  memset_0(&VersionInformation.dwMajorVersion, 0, 0x118u);
  VersionInformation.dwOSVersionInfoSize = 284;
  if ( GetVersionExW(&VersionInformation) )
  {
    szCSDVersion = VersionInformation.szCSDVersion;
    if ( !VersionInformation.szCSDVersion[0] )
      szCSDVersion = L" ";
    _snwprintf_s<192>(
      a1 + 144,
      -1,
      L"%d.%d.%d Build %d %s",
      VersionInformation.dwMajorVersion,
      VersionInformation.dwMinorVersion,
      VersionInformation.dwBuildNumber,
      VersionInformation.dwBuildNumber,
      szCSDVersion);
  }
  else
  {
    *(_WORD *)(a1 + 144) = 0;
  }
  hKey = 0;
  v3 = (_WORD *)(a1 + 16);
  phkResult = tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Windows NT\\CurrentVersion", 0, 0x20019u, phkResult) )
  {
    *(_WORD *)(a1 + 528) = 0;
    *(_DWORD *)(a1 + 784) = 0;
    *(_WORD *)(a1 + 656) = 0;
LABEL_19:
    *v3 = 0;
    goto LABEL_20;
  }
  Type = 0;
  cbData = 128;
  if ( RegQueryValueExW(hKey, L"ProductName", 0, &Type, (LPBYTE)(a1 + 16), &cbData) || Type != 1 )
    *v3 = 0;
  cbData = 128;
  if ( RegQueryValueExW(hKey, L"CurrentType", 0, &Type, (LPBYTE)(a1 + 528), &cbData) || Type != 1 )
    *(_WORD *)(a1 + 528) = 0;
  cbData = 4;
  if ( (unsigned int)RegReadDWORDValueNoThrow(hKey, &pszFormat, L"InstallDate", (unsigned int *)(a1 + 784)) )
    *(_DWORD *)(a1 + 784) = 0;
  v3 = (_WORD *)(a1 + 656);
  cbData = 128;
  if ( RegQueryValueExW(hKey, L"BuildLab", 0, &Type, (LPBYTE)(a1 + 656), &cbData) || Type != 1 )
    goto LABEL_19;
LABEL_20:
  *(_DWORD *)(a1 + 1312) = GetSystemDefaultLangID();
  tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
  return 0;
}

```

## disassembly

```asm
0x1800c2128  push    rbp
0x1800c212a  push    rbx
0x1800c212b  push    rsi
0x1800c212c  push    rdi
0x1800c212d  lea     rbp, [rsp-88h]
0x1800c2135  sub     rsp, 188h
0x1800c213c  mov     rax, cs:__security_cookie
0x1800c2143  xor     rax, rsp
0x1800c2146  mov     [rbp+0A0h+var_30], rax
0x1800c214a  mov     rbx, rcx
0x1800c214d  xor     edx, edx; Val
0x1800c214f  lea     rcx, [rsp+1A0h+VersionInformation.dwMajorVersion]; void *
0x1800c2154  mov     r8d, 118h; Size
0x1800c215a  call    memset_0
0x1800c215f  lea     rcx, [rsp+1A0h+VersionInformation]; lpVersionInformation
0x1800c2164  mov     [rsp+1A0h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x1800c216c  call    cs:__imp_GetVersionExW
0x1800c2172  xor     esi, esi
0x1800c2174  test    eax, eax
0x1800c2176  jz      short loc_1800C21C4
0x1800c2178  cmp     [rsp+1A0h+VersionInformation.szCSDVersion], si
0x1800c217d  lea     rcx, asc_1800F21EC; " "
0x1800c2184  mov     r9d, [rsp+1A0h+VersionInformation.dwMajorVersion]
0x1800c2189  lea     rax, [rsp+1A0h+VersionInformation.szCSDVersion]
0x1800c218e  cmovz   rax, rcx
0x1800c2192  lea     r8, aDDDBuildDS; "%d.%d.%d Build %d %s"
0x1800c2199  mov     [rsp+1A0h+var_168], rax
0x1800c219e  lea     rcx, [rbx+90h]
0x1800c21a5  mov     eax, [rsp+1A0h+VersionInformation.dwBuildNumber]
0x1800c21a9  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800c21ad  mov     [rsp+1A0h+var_170], eax
0x1800c21b1  mov     dword ptr [rsp+1A0h+lpcbData], eax
0x1800c21b5  mov     eax, [rsp+1A0h+VersionInformation.dwMinorVersion]
0x1800c21b9  mov     dword ptr [rsp+1A0h+phkResult], eax
0x1800c21bd  call    ??$_snwprintf_s@$0MA@@@YAHAEAY0MA@_W_KPEB_WZZ; _snwprintf_s<192>(wchar_t (&)[192],unsigned __int64,wchar_t const *,...)
0x1800c21c2  jmp     short loc_1800C21CB
0x1800c21c4  mov     [rbx+90h], si
0x1800c21cb  lea     rcx, [rsp+1A0h+hKey]
0x1800c21d0  mov     [rsp+1A0h+hKey], rsi
0x1800c21d5  lea     rdi, [rbx+10h]
0x1800c21d9  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x1800c21de  mov     r9d, 20019h; samDesired
0x1800c21e4  mov     [rsp+1A0h+phkResult], rax; phkResult
0x1800c21e9  xor     r8d, r8d; ulOptions
0x1800c21ec  lea     rdx, aSoftwareMicros_5; "Software\\Microsoft\\Windows NT\\Curren"...
0x1800c21f3  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800c21fa  call    cs:__imp_RegOpenKeyExW
0x1800c2200  test    eax, eax
0x1800c2202  jnz     loc_1800C2306
0x1800c2208  mov     rcx, [rsp+1A0h+hKey]; hKey
0x1800c220d  lea     rax, [rsp+1A0h+cbData]
0x1800c2212  mov     [rsp+1A0h+lpcbData], rax; lpcbData
0x1800c2217  lea     r9, [rsp+1A0h+Type]; lpType
0x1800c221c  xor     r8d, r8d; lpReserved
0x1800c221f  mov     [rsp+1A0h+phkResult], rdi; lpData
0x1800c2224  lea     rdx, aProductname; "ProductName"
0x1800c222b  mov     [rsp+1A0h+Type], esi
0x1800c222f  mov     [rsp+1A0h+cbData], 80h
0x1800c2237  call    cs:__imp_RegQueryValueExW
0x1800c223d  test    eax, eax
0x1800c223f  jnz     short loc_1800C2248
0x1800c2241  cmp     [rsp+1A0h+Type], 1
0x1800c2246  jz      short loc_1800C224B
0x1800c2248  mov     [rdi], si
0x1800c224b  mov     rcx, [rsp+1A0h+hKey]; hKey
0x1800c2250  lea     rax, [rsp+1A0h+cbData]
0x1800c2255  mov     [rsp+1A0h+lpcbData], rax; lpcbData
0x1800c225a  lea     rdi, [rbx+210h]
0x1800c2261  lea     r9, [rsp+1A0h+Type]; lpType
0x1800c2266  mov     [rsp+1A0h+phkResult], rdi; lpData
0x1800c226b  xor     r8d, r8d; lpReserved
0x1800c226e  mov     [rsp+1A0h+cbData], 80h
0x1800c2276  lea     rdx, aCurrenttype; "CurrentType"
0x1800c227d  call    cs:__imp_RegQueryValueExW
0x1800c2283  test    eax, eax
0x1800c2285  jnz     short loc_1800C228E
0x1800c2287  cmp     [rsp+1A0h+Type], 1
0x1800c228c  jz      short loc_1800C2291
0x1800c228e  mov     [rdi], si
0x1800c2291  mov     rcx, [rsp+1A0h+hKey]; HKEY
0x1800c2296  lea     rdi, [rbx+310h]
0x1800c229d  mov     r9, rdi; unsigned int *
0x1800c22a0  mov     [rsp+1A0h+cbData], 4
0x1800c22a8  lea     r8, aInstalldate; "InstallDate"
0x1800c22af  lea     rdx, pszFormat; wchar_t *
0x1800c22b6  call    ?RegReadDWORDValueNoThrow@@YAJPEAUHKEY__@@PEB_W1AEAK@Z; RegReadDWORDValueNoThrow(HKEY__ *,wchar_t const *,wchar_t const *,ulong &)
0x1800c22bb  test    eax, eax
0x1800c22bd  jz      short loc_1800C22C1
0x1800c22bf  mov     [rdi], esi
0x1800c22c1  mov     rcx, [rsp+1A0h+hKey]; hKey
0x1800c22c6  lea     rax, [rsp+1A0h+cbData]
0x1800c22cb  mov     [rsp+1A0h+lpcbData], rax; lpcbData
0x1800c22d0  lea     rdi, [rbx+290h]
0x1800c22d7  lea     r9, [rsp+1A0h+Type]; lpType
0x1800c22dc  mov     [rsp+1A0h+phkResult], rdi; lpData
0x1800c22e1  xor     r8d, r8d; lpReserved
0x1800c22e4  mov     [rsp+1A0h+cbData], 80h
0x1800c22ec  lea     rdx, aBuildlab; "BuildLab"
0x1800c22f3  call    cs:__imp_RegQueryValueExW
0x1800c22f9  test    eax, eax
0x1800c22fb  jnz     short loc_1800C231A
0x1800c22fd  cmp     [rsp+1A0h+Type], 1
0x1800c2302  jz      short loc_1800C231D
0x1800c2304  jmp     short loc_1800C231A
0x1800c2306  mov     [rbx+210h], si
0x1800c230d  mov     [rbx+310h], esi
0x1800c2313  mov     [rbx+290h], si
0x1800c231a  mov     [rdi], si
0x1800c231d  call    cs:__imp_GetSystemDefaultLangID
0x1800c2323  movzx   eax, ax
0x1800c2326  lea     rcx, [rsp+1A0h+hKey]
0x1800c232b  mov     [rbx+520h], eax
0x1800c2331  call    ??1?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(void)
0x1800c2336  xor     eax, eax
0x1800c2338  mov     rcx, [rbp+0A0h+var_30]
0x1800c233c  xor     rcx, rsp; StackCookie
0x1800c233f  call    __security_check_cookie
0x1800c2344  add     rsp, 188h
0x1800c234b  pop     rdi
0x1800c234c  pop     rsi
0x1800c234d  pop     rbx
0x1800c234e  pop     rbp
0x1800c234f  retn
```
