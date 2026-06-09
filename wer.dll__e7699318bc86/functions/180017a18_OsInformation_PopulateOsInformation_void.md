# OsInformation::PopulateOsInformation(void)

- ea: `0x180017a18`
- end: `0x180018112`
- name: `?PopulateOsInformation@OsInformation@@QEAAJXZ`
- size: `1786`
- prototype: `__int64 __fastcall(OsInformation *__hidden this)`
- caller_count: `2`
- callee_count: `18`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18001726c`
- `0x1800a04f8`

## callees

- `0x180006cb0`
- `0x180008174`
- `0x18000cc74`
- `0x18000dad0`
- `0x180017a18`
- `0x180028bf8`
- `0x1800293ac`
- `0x18003dc48`
- `0x18003e994`
- `0x180042130`
- `0x180042398`
- `0x180044f34`
- `0x180049c00`
- `0x18004aa70`
- `0x180050db0`
- `0x1800517cc`
- `0x180097818`
- `0x180098a4c`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetUserGeoID` at `0x180017b61`
- `api-ms-win-core-localization-l1-2-0!GetUserGeoID` at `0x180017b61`
- `api-ms-win-core-localization-l1-2-0!GetSystemDefaultLCID` at `0x180017b53`
- `api-ms-win-core-localization-l1-2-0!GetSystemDefaultLCID` at `0x180017b53`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180017c17`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180017c17`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017b1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017b1c`
- `ntdll!RtlGetVersion` at `0x180017ae1`
- `ntdll!RtlGetVersion` at `0x180017ae1`
- `api-ms-win-core-sysinfo-l1-2-0!GetNativeSystemInfo` at `0x180017b3b`
- `api-ms-win-core-sysinfo-l1-2-0!GetNativeSystemInfo` at `0x180017b3b`
- `api-ms-win-core-sysinfo-l1-2-0!GetProductInfo` at `0x180017b12`
- `api-ms-win-core-sysinfo-l1-2-0!GetProductInfo` at `0x180017b12`

## string_xrefs

- `0x180017b9a`: `SOFTWARE\Microsoft\SQMClient\Windows\CommonDatapoints`
- `0x180017bdc`: `TelemetryProtocolServerRoles`
- `0x180017ca2`: `svcUpdateVersion`
- `0x180017f3b`: `UpdateID`
- `0x180018087`: `SOFTWARE\Microsoft\Windows\CurrentVersion\Component Based Servicing\Interface`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall OsInformation::PopulateOsInformation(OsInformation *this)
{
  unsigned int v2; // ebx
  NTSTATUS Version; // eax
  int LastError; // eax
  unsigned __int64 v5; // r9
  struct _FILETIME v6; // rbx
  _WORD *v7; // rcx
  _WORD *v8; // rcx
  _WORD *v9; // rcx
  int v10; // r8d
  _WORD *v11; // rcx
  _WORD *v12; // rcx
  _WORD *v13; // rcx
  _WORD *v14; // rcx
  __int64 v15; // rdx
  _WORD *v16; // rcx
  _WORD *v17; // rcx
  unsigned int DWORD; // eax
  _WORD *v19; // rcx
  _WORD *v20; // rcx
  bool v22; // [rsp+28h] [rbp-D8h]
  bool v23; // [rsp+28h] [rbp-D8h]
  bool v24; // [rsp+28h] [rbp-D8h]
  bool v25; // [rsp+28h] [rbp-D8h]
  bool v26; // [rsp+28h] [rbp-D8h]
  bool v27; // [rsp+28h] [rbp-D8h]
  bool v28; // [rsp+28h] [rbp-D8h]
  bool v29; // [rsp+28h] [rbp-D8h]
  bool v30; // [rsp+28h] [rbp-D8h]
  bool v31; // [rsp+28h] [rbp-D8h]
  bool v32; // [rsp+28h] [rbp-D8h]
  bool v33; // [rsp+28h] [rbp-D8h]
  bool v34; // [rsp+28h] [rbp-D8h]
  bool v35; // [rsp+28h] [rbp-D8h]
  bool v36; // [rsp+28h] [rbp-D8h]
  bool v37; // [rsp+28h] [rbp-D8h]
  bool v38; // [rsp+40h] [rbp-C0h] BYREF
  struct _FILETIME v39; // [rsp+48h] [rbp-B8h]
  struct _FILETIME FileTime; // [rsp+50h] [rbp-B0h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v42; // [rsp+60h] [rbp-A0h] BYREF
  _WORD *v43; // [rsp+68h] [rbp-98h]
  _WORD v44[8]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v45[2]; // [rsp+80h] [rbp-80h] BYREF
  _WORD v46[8]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v47[2]; // [rsp+A0h] [rbp-60h] BYREF
  _WORD v48[8]; // [rsp+B0h] [rbp-50h] BYREF
  struct _SYSTEM_INFO SystemInfo; // [rsp+C0h] [rbp-40h] BYREF
  struct _OSVERSIONINFOW VersionInformation; // [rsp+F0h] [rbp-10h] BYREF
  unsigned __int16 v51; // [rsp+204h] [rbp+104h]
  unsigned __int8 v52; // [rsp+20Ah] [rbp+10Ah]
  unsigned int v53; // [rsp+20Ch] [rbp+10Ch]

  memset_0(&VersionInformation.dwMajorVersion, 0, 0x120u);
  memset(&SystemInfo, 0, sizeof(SystemInfo));
  SystemTimeAsFileTime = 0;
  FileTime = 0;
  v39 = 0;
  v47[0] = (__int64)v48;
  v47[1] = (__int64)v48;
  v48[0] = 0;
  v45[0] = (__int64)v46;
  v45[1] = (__int64)v46;
  v46[0] = 0;
  v42 = (__int64)v44;
  v43 = v44;
  v44[0] = 0;
  v38 = 0;
  if ( *(_DWORD *)this )
  {
    v2 = 1;
  }
  else
  {
    VersionInformation.dwOSVersionInfoSize = 292;
    Version = RtlGetVersion(&VersionInformation);
    if ( Version >= 0 )
    {
      *((_QWORD *)this + 6) = v53;
      if ( GetProductInfo(0xFFFFFFFF, 0xFFFFFFFF, 0xFFFFFFFF, 0xFFFFFFFF, (PDWORD)this + 9) )
      {
        GetNativeSystemInfo(&SystemInfo);
        *((_DWORD *)this + 1) = VersionInformation.dwMajorVersion;
        *((_DWORD *)this + 2) = VersionInformation.dwMinorVersion;
        *((_DWORD *)this + 3) = VersionInformation.dwBuildNumber;
        *((_DWORD *)this + 7) = GetSystemDefaultLCID();
        *((_DWORD *)this + 8) = GetUserGeoID(0x10u);
        *((_DWORD *)this + 14) = v52;
        *((_DWORD *)this + 15) = VersionInformation.dwPlatformId;
        *((_DWORD *)this + 5) = v51;
        *((_DWORD *)this + 6) = SystemInfo.wProcessorArchitecture;
        *((_DWORD *)this + 10) = UtilRegGetDWORD(
                                   HKEY_LOCAL_MACHINE,
                                   L"SOFTWARE\\Microsoft\\SQMClient\\Windows\\CommonDatapoints",
                                   L"608",
                                   0,
                                   0,
                                   v22);
        *((_DWORD *)this + 4) = UtilRegGetDWORD(
                                  HKEY_LOCAL_MACHINE,
                                  L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion",
                                  L"UBR",
                                  0,
                                  0,
                                  v23);
        *((_QWORD *)this + 8) = UtilRegGetQWORD(
                                  HKEY_LOCAL_MACHINE,
                                  L"SOFTWARE\\Microsoft\\SQMClient\\Windows",
                                  L"TelemetryProtocolServerRoles",
                                  v5,
                                  0,
                                  v24);
        v6 = v39;
        if ( (int)UtilGetInstallTime(&FileTime) >= 0 )
          v6 = FileTime;
        if ( v6 )
        {
          GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
          if ( *(_QWORD *)&SystemTimeAsFileTime > *(unsigned __int64 *)&v6 )
            *((_DWORD *)this + 18) = (*(_QWORD *)&SystemTimeAsFileTime - *(_QWORD *)&v6) / 0x23C34600uLL;
        }
        *((_DWORD *)this + 19) = UtilRegGetDWORD(
                                   HKEY_LOCAL_MACHINE,
                                   L"SOFTWARE\\Microsoft\\SQMClient\\Windows\\CommonDatapoints",
                                   L"9292",
                                   0,
                                   0,
                                   v25);
        if ( (int)UtilRegGetString(
                    HKEY_LOCAL_MACHINE,
                    L"SOFTWARE\\Microsoft\\Internet Explorer",
                    L"svcVersion",
                    (__int64)v47,
                    1,
                    1) < 0
          || (int)UtilRegGetString(
                    HKEY_LOCAL_MACHINE,
                    L"SOFTWARE\\Microsoft\\Internet Explorer",
                    L"svcUpdateVersion",
                    (__int64)v45,
                    1,
                    1) < 0
          || (int)tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
                    (_QWORD *)this + 10,
                    L"%ls-%ls",
                    v47[0],
                    v45[0]) < 0 )
        {
          v7 = (_WORD *)*((_QWORD *)this + 10);
          *((_QWORD *)this + 11) = v7;
          *v7 = 0;
        }
        if ( (int)UtilRegGetString(
                    HKEY_LOCAL_MACHINE,
                    L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion",
                    L"EditionID",
                    (__int64)this + 392,
                    0,
                    1) < 0 )
        {
          v8 = (_WORD *)*((_QWORD *)this + 49);
          *((_QWORD *)this + 50) = v8;
          *v8 = 0;
        }
        *((_DWORD *)this + 28) = UtilRegGetDWORD(
                                   HKEY_LOCAL_MACHINE,
                                   L"SOFTWARE\\Microsoft\\SQMClient\\Windows\\CommonDatapoints",
                                   L"9197",
                                   0,
                                   0,
                                   v26);
        *((_DWORD *)this + 29) = UtilRegGetDWORD(
                                   HKEY_LOCAL_MACHINE,
                                   L"SOFTWARE\\Microsoft\\SQMClient\\Windows\\CommonDatapoints",
                                   L"35",
                                   0,
                                   0,
                                   v27);
        *((_DWORD *)this + 30) = UtilRegGetDWORD(
                                   HKEY_LOCAL_MACHINE,
                                   L"SOFTWARE\\Microsoft\\SQMClient\\Windows\\CommonDatapoints",
                                   L"12729",
                                   0,
                                   0,
                                   v28);
        *((_DWORD *)this + 31) = UtilRegGetDWORD(
                                   HKEY_LOCAL_MACHINE,
                                   L"SOFTWARE\\Microsoft\\SQMClient\\Windows\\CommonDatapoints",
                                   L"12730",
                                   0,
                                   0,
                                   v29);
        *((_DWORD *)this + 32) = UtilRegGetDWORD(
                                   HKEY_LOCAL_MACHINE,
                                   L"SOFTWARE\\Microsoft\\SQMClient\\Windows\\CommonDatapoints",
                                   L"12736",
                                   0,
                                   0,
                                   v30);
        *((_DWORD *)this + 33) = UtilRegGetDWORD(
                                   HKEY_LOCAL_MACHINE,
                                   L"SOFTWARE\\Microsoft\\SQMClient\\Windows\\CommonDatapoints",
                                   L"12737",
                                   0,
                                   0,
                                   v31);
        if ( (int)UtilGetBuildBranch((char *)this + 136) < 0 )
        {
          v9 = (_WORD *)*((_QWORD *)this + 17);
          *((_QWORD *)this + 18) = v9;
          *v9 = 0;
        }
        if ( (int)UtilRegGetString(
                    HKEY_LOCAL_MACHINE,
                    L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion",
                    L"CurrentType",
                    (__int64)&v42,
                    1,
                    1) >= 0
          && utl::_StringTraits<tlx::transform_traits<wchar_t,tlx::ascii_toupper_transform>>::find(
               v42,
               ((__int64)v43 - v42) >> 1,
               v10,
               (unsigned int)L"Checked",
               7) != -1 )
        {
          *((_DWORD *)this + 42) = 1;
        }
        *((_DWORD *)this + 43) = UtilRegGetDWORD(
                                   HKEY_LOCAL_MACHINE,
                                   L"SOFTWARE\\Microsoft\\SQMClient\\Windows\\CommonDatapoints",
                                   L"12675",
                                   0,
                                   0,
                                   v32);
        *((_DWORD *)this + 44) = UtilRegGetDWORD(
                                   HKEY_LOCAL_MACHINE,
                                   L"SOFTWARE\\Microsoft\\SQMClient\\Windows\\CommonDatapoints",
                                   L"12676",
                                   0,
                                   0,
                                   v33);
        *((_DWORD *)this + 45) = UtilRegGetDWORD(
                                   HKEY_LOCAL_MACHINE,
                                   L"SOFTWARE\\Microsoft\\SQMClient\\Windows\\CommonDatapoints",
                                   L"12677",
                                   0,
                                   0,
                                   v34);
        *((_DWORD *)this + 46) = UtilRegGetDWORD(
                                   HKEY_LOCAL_MACHINE,
                                   L"SOFTWARE\\Microsoft\\SQMClient\\Windows\\CommonDatapoints",
                                   L"12678",
                                   0,
                                   0,
                                   v35);
        if ( (int)UtilGetPlatformVersion(&v42) < 0
          || (int)tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
                    (_QWORD *)this + 24,
                    L"%d.%d.%ls",
                    VersionInformation.dwMajorVersion,
                    VersionInformation.dwMinorVersion,
                    v42) < 0 )
        {
          v11 = (_WORD *)*((_QWORD *)this + 24);
          *((_QWORD *)this + 25) = v11;
          *v11 = 0;
        }
        if ( (int)UtilRegGetString(
                    HKEY_LOCAL_MACHINE,
                    L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Flighting\\Build",
                    L"UpdateID",
                    (__int64)this + 232,
                    1,
                    1) < 0 )
        {
          v12 = (_WORD *)*((_QWORD *)this + 29);
          *((_QWORD *)this + 30) = v12;
          *v12 = 0;
        }
        if ( (int)UtilGetFlightInfo((char *)this + 264, (char *)this + 296) < 0 )
        {
          v13 = (_WORD *)*((_QWORD *)this + 33);
          *((_QWORD *)this + 34) = v13;
          *v13 = 0;
          v14 = (_WORD *)*((_QWORD *)this + 37);
          *((_QWORD *)this + 38) = v14;
          *v14 = 0;
        }
        if ( (int)UtilGetFlightIdString((char *)this + 328) < 0 )
        {
          v16 = (_WORD *)*((_QWORD *)this + 41);
          *((_QWORD *)this + 42) = v16;
          *v16 = 0;
        }
        if ( (int)UtilGetFeatureConfigurations((__int64)this + 360, v15) < 0 )
        {
          v17 = (_WORD *)*((_QWORD *)this + 45);
          *((_QWORD *)this + 46) = v17;
          *v17 = 0;
        }
        DWORD = UtilRegGetDWORD(
                  HKEY_LOCAL_MACHINE,
                  L"SYSTEM\\CurrentControlSet\\Control",
                  L"ContainerType",
                  0,
                  &v38,
                  v36);
        if ( !v38
          && (int)tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
                    (_QWORD *)this + 57,
                    L"%u",
                    DWORD) < 0 )
        {
          v19 = (_WORD *)*((_QWORD *)this + 57);
          *((_QWORD *)this + 58) = v19;
          *v19 = 0;
        }
        if ( (int)UtilRegGetString(
                    HKEY_LOCAL_MACHINE,
                    L"SYSTEM\\CurrentControlSet\\Control",
                    L"ContainerId",
                    (__int64)this + 424,
                    0,
                    1) < 0 )
        {
          v20 = (_WORD *)*((_QWORD *)this + 53);
          *((_QWORD *)this + 54) = v20;
          *v20 = 0;
        }
        if ( (int)UtilIsEdu((unsigned int *)this + 56) < 0 )
          *((_DWORD *)this + 56) = 0;
        *((_DWORD *)this + 122) = UtilRegGetDWORD(
                                    HKEY_LOCAL_MACHINE,
                                    L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Component Based Servicing\\Interface",
                                    L"ServicingInProgress",
                                    0,
                                    0,
                                    v37);
        if ( (int)UtilIsFeatureUpdatePendingReboot((unsigned int *)this + 123) < 0 )
          *((_DWORD *)this + 123) = 0;
        *((_DWORD *)this + 124) = UtilIsWinRE();
        LastError = 0;
        *(_DWORD *)this = 1;
      }
      else
      {
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
      }
    }
    else
    {
      LastError = Version | 0x10000000;
    }
    v2 = LastError;
  }
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(&v42);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v45);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v47);
  return v2;
}

```

## disassembly

```asm
0x180017a18  mov     [rsp-8+arg_8], rbx
0x180017a1d  mov     [rsp-8+arg_10], rsi
0x180017a22  push    rbp
0x180017a23  push    rdi
0x180017a24  push    r12
0x180017a26  push    r14
0x180017a28  push    r15
0x180017a2a  lea     rbp, [rsp-130h]
0x180017a32  sub     rsp, 230h
0x180017a39  mov     rax, cs:__security_cookie
0x180017a40  xor     rax, rsp
0x180017a43  mov     [rbp+150h+var_30], rax
0x180017a4a  mov     rdi, rcx
0x180017a4d  xor     edx, edx; Val
0x180017a4f  mov     r8d, 120h; Size
0x180017a55  lea     rcx, [rbp+150h+VersionInformation.dwMajorVersion]; void *
0x180017a59  call    memset_0
0x180017a5e  xorps   xmm0, xmm0
0x180017a61  movups  xmmword ptr [rbp+150h+SystemInfo], xmm0
0x180017a65  movups  xmmword ptr [rbp+150h+SystemInfo.lpMaximumApplicationAddress], xmm0
0x180017a69  movups  xmmword ptr [rbp+150h+SystemInfo.dwNumberOfProcessors], xmm0
0x180017a6d  xor     r15d, r15d
0x180017a70  mov     qword ptr [rsp+250h+SystemTimeAsFileTime.dwLowDateTime], r15
0x180017a75  mov     qword ptr [rsp+250h+FileTime.dwLowDateTime], r15
0x180017a7a  mov     [rsp+250h+var_208], r15
0x180017a7f  lea     rax, [rbp+150h+var_1A0]
0x180017a83  mov     [rbp+150h+var_1B0], rax
0x180017a87  lea     rax, [rbp+150h+var_1A0]
0x180017a8b  mov     [rbp+150h+var_1A8], rax
0x180017a8f  mov     [rbp+150h+var_1A0], r15w
0x180017a94  lea     rax, [rbp+150h+var_1C0]
0x180017a98  mov     [rbp+150h+var_1D0], rax
0x180017a9c  lea     rax, [rbp+150h+var_1C0]
0x180017aa0  mov     [rbp+150h+var_1C8], rax
0x180017aa4  mov     [rbp+150h+var_1C0], r15w
0x180017aa9  lea     rax, [rsp+250h+var_1E0]
0x180017aae  mov     [rsp+250h+var_1F0], rax
0x180017ab3  lea     rax, [rsp+250h+var_1E0]
0x180017ab8  mov     [rsp+250h+var_1E8], rax
0x180017abd  mov     [rsp+250h+var_1E0], r15w
0x180017ac3  mov     [rsp+250h+var_210], r15b
0x180017ac8  cmp     [rdi], r15d
0x180017acb  jz      short loc_180017AD6
0x180017acd  lea     ebx, [r15+1]
0x180017ad1  jmp     loc_1800180C7
0x180017ad6  mov     [rbp+150h+VersionInformation.dwOSVersionInfoSize], 124h
0x180017add  lea     rcx, [rbp+150h+VersionInformation]; lpVersionInformation
0x180017ae1  call    cs:__imp_RtlGetVersion
0x180017ae7  test    eax, eax
0x180017ae9  jns     short loc_180017AF4
0x180017aeb  bts     eax, 1Ch
0x180017aef  jmp     loc_1800180C5
0x180017af4  mov     eax, [rbp+150h+var_44]
0x180017afa  mov     [rdi+30h], rax
0x180017afe  lea     rax, [rdi+24h]
0x180017b02  mov     [rsp+250h+pdwReturnedProductType], rax; pdwReturnedProductType
0x180017b07  or      ecx, 0FFFFFFFFh; dwOSMajorVersion
0x180017b0a  mov     r9d, ecx; dwSpMinorVersion
0x180017b0d  mov     r8d, ecx; dwSpMajorVersion
0x180017b10  mov     edx, ecx; dwOSMinorVersion
0x180017b12  call    cs:__imp_GetProductInfo
0x180017b18  test    eax, eax
0x180017b1a  jnz     short loc_180017B37
0x180017b1c  call    cs:__imp_GetLastError
0x180017b22  test    eax, eax
0x180017b24  jle     loc_1800180C5
0x180017b2a  movzx   eax, ax
0x180017b2d  or      eax, 80070000h
0x180017b32  jmp     loc_1800180C5
0x180017b37  lea     rcx, [rbp+150h+SystemInfo]; lpSystemInfo
0x180017b3b  call    cs:__imp_GetNativeSystemInfo
0x180017b41  mov     eax, [rbp+150h+VersionInformation.dwMajorVersion]
0x180017b44  mov     [rdi+4], eax
0x180017b47  mov     eax, [rbp+150h+VersionInformation.dwMinorVersion]
0x180017b4a  mov     [rdi+8], eax
0x180017b4d  mov     eax, [rbp+150h+VersionInformation.dwBuildNumber]
0x180017b50  mov     [rdi+0Ch], eax
0x180017b53  call    cs:__imp_GetSystemDefaultLCID
0x180017b59  mov     [rdi+1Ch], eax
0x180017b5c  mov     ecx, 10h; GeoClass
0x180017b61  call    cs:__imp_GetUserGeoID
0x180017b67  mov     [rdi+20h], eax
0x180017b6a  movzx   eax, [rbp+150h+var_46]
0x180017b71  mov     [rdi+38h], eax
0x180017b74  mov     eax, [rbp+150h+VersionInformation.dwPlatformId]
0x180017b77  mov     [rdi+3Ch], eax
0x180017b7a  movzx   eax, [rbp+150h+var_4C]
0x180017b81  mov     [rdi+14h], eax
0x180017b84  movzx   eax, word ptr [rbp+150h+SystemInfo]
0x180017b88  mov     [rdi+18h], eax
0x180017b8b  mov     [rsp+250h+pdwReturnedProductType], r15; bool *
0x180017b90  xor     r9d, r9d; unsigned int
0x180017b93  lea     r8, a608; "608"
0x180017b9a  lea     r14, aSoftwareMicros_31; "SOFTWARE\\Microsoft\\SQMClient\\Windows"...
0x180017ba1  mov     rdx, r14; wchar_t *
0x180017ba4  mov     r12, 0FFFFFFFF80000002h
0x180017bab  mov     rcx, r12; HKEY
0x180017bae  call    ?UtilRegGetDWORD@@YAKPEAUHKEY__@@PEB_W1KPEA_N_N@Z; UtilRegGetDWORD(HKEY__ *,wchar_t const *,wchar_t const *,ulong,bool *,bool)
0x180017bb3  mov     [rdi+28h], eax
0x180017bb6  mov     [rsp+250h+pdwReturnedProductType], r15; bool *
0x180017bbb  xor     r9d, r9d; unsigned int
0x180017bbe  lea     r8, aUbr_0; "UBR"
0x180017bc5  lea     rdx, aSoftwareMicros_33; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180017bcc  mov     rcx, r12; HKEY
0x180017bcf  call    ?UtilRegGetDWORD@@YAKPEAUHKEY__@@PEB_W1KPEA_N_N@Z; UtilRegGetDWORD(HKEY__ *,wchar_t const *,wchar_t const *,ulong,bool *,bool)
0x180017bd4  mov     [rdi+10h], eax
0x180017bd7  mov     [rsp+250h+pdwReturnedProductType], r15; bool *
0x180017bdc  lea     r8, aTelemetryproto; "TelemetryProtocolServerRoles"
0x180017be3  lea     rdx, aSoftwareMicros_15; "SOFTWARE\\Microsoft\\SQMClient\\Windows"
0x180017bea  mov     rcx, r12; HKEY
0x180017bed  call    ?UtilRegGetQWORD@@YA_KPEAUHKEY__@@PEB_W1_KPEA_N_N@Z; UtilRegGetQWORD(HKEY__ *,wchar_t const *,wchar_t const *,unsigned __int64,bool *,bool)
0x180017bf2  mov     [rdi+40h], rax
0x180017bf6  lea     rcx, [rsp+250h+FileTime]; lpFileTime
0x180017bfb  call    ?UtilGetInstallTime@@YAJPEAU_FILETIME@@@Z; UtilGetInstallTime(_FILETIME *)
0x180017c00  mov     rbx, [rsp+250h+var_208]
0x180017c05  test    eax, eax
0x180017c07  cmovns  rbx, qword ptr [rsp+250h+FileTime.dwLowDateTime]
0x180017c0d  test    rbx, rbx
0x180017c10  jz      short loc_180017C3E
0x180017c12  lea     rcx, [rsp+250h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180017c17  call    cs:__imp_GetSystemTimeAsFileTime
0x180017c1d  mov     rcx, qword ptr [rsp+250h+SystemTimeAsFileTime.dwLowDateTime]
0x180017c22  cmp     rcx, rbx
0x180017c25  jbe     short loc_180017C3E
0x180017c27  sub     rcx, rbx
0x180017c2a  mov     rax, 0E5109EC205D7BEA7h
0x180017c34  mul     rcx
0x180017c37  shr     rdx, 1Dh
0x180017c3b  mov     [rdi+48h], edx
0x180017c3e  mov     [rsp+250h+pdwReturnedProductType], r15; bool *
0x180017c43  xor     r9d, r9d; unsigned int
0x180017c46  lea     r8, a9292; "9292"
0x180017c4d  mov     rdx, r14; wchar_t *
0x180017c50  mov     rcx, r12; HKEY
0x180017c53  call    ?UtilRegGetDWORD@@YAKPEAUHKEY__@@PEB_W1KPEA_N_N@Z; UtilRegGetDWORD(HKEY__ *,wchar_t const *,wchar_t const *,ulong,bool *,bool)
0x180017c58  mov     [rdi+4Ch], eax
0x180017c5b  mov     ebx, 1
0x180017c60  mov     [rsp+250h+var_220], bl; char
0x180017c64  mov     [rsp+250h+var_228], bl; char
0x180017c68  lea     rax, [rbp+150h+var_1B0]
0x180017c6c  mov     [rsp+250h+pdwReturnedProductType], rax; __int64
0x180017c71  xor     r9d, r9d
0x180017c74  lea     r8, aSvcversion; "svcVersion"
0x180017c7b  lea     rdx, aSoftwareMicros_13; "SOFTWARE\\Microsoft\\Internet Explorer"
0x180017c82  mov     rcx, r12; hkey
0x180017c85  call    ?UtilRegGetString@@YAJPEAUHKEY__@@PEB_W11PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@_N3@Z; UtilRegGetString(HKEY__ *,wchar_t const *,wchar_t const *,wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,bool,bool)
0x180017c8a  test    eax, eax
0x180017c8c  js      short loc_180017CD8
0x180017c8e  mov     [rsp+250h+var_220], bl; char
0x180017c92  mov     [rsp+250h+var_228], bl; char
0x180017c96  lea     rax, [rbp+150h+var_1D0]
0x180017c9a  mov     [rsp+250h+pdwReturnedProductType], rax; __int64
0x180017c9f  xor     r9d, r9d
0x180017ca2  lea     r8, aSvcupdateversi; "svcUpdateVersion"
0x180017ca9  lea     rdx, aSoftwareMicros_13; "SOFTWARE\\Microsoft\\Internet Explorer"
0x180017cb0  mov     rcx, r12; hkey
0x180017cb3  call    ?UtilRegGetString@@YAJPEAUHKEY__@@PEB_W11PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@_N3@Z; UtilRegGetString(HKEY__ *,wchar_t const *,wchar_t const *,wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,bool,bool)
0x180017cb8  test    eax, eax
0x180017cba  js      short loc_180017CD8
0x180017cbc  lea     rcx, [rdi+50h]
0x180017cc0  mov     r9, [rbp+150h+var_1D0]
0x180017cc4  mov     r8, [rbp+150h+var_1B0]
0x180017cc8  lea     rdx, aLsLs; "%ls-%ls"
0x180017ccf  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x180017cd4  test    eax, eax
0x180017cd6  jns     short loc_180017CE4
0x180017cd8  mov     rcx, [rdi+50h]
0x180017cdc  mov     [rdi+58h], rcx
0x180017ce0  mov     [rcx], r15w
0x180017ce4  lea     rsi, [rdi+188h]
0x180017ceb  mov     [rsp+250h+var_220], bl; char
0x180017cef  mov     [rsp+250h+var_228], r15b; bool
0x180017cf4  mov     [rsp+250h+pdwReturnedProductType], rsi; __int64
0x180017cf9  lea     r9, aUnknown_0; "Unknown"
0x180017d00  lea     r8, aEditionid; "EditionID"
0x180017d07  lea     rdx, aSoftwareMicros_33; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180017d0e  mov     rcx, r12; hkey
0x180017d11  call    ?UtilRegGetString@@YAJPEAUHKEY__@@PEB_W11PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@_N3@Z; UtilRegGetString(HKEY__ *,wchar_t const *,wchar_t const *,wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,bool,bool)
0x180017d16  test    eax, eax
0x180017d18  jns     short loc_180017D25
0x180017d1a  mov     rcx, [rsi]
0x180017d1d  mov     [rsi+8], rcx
0x180017d21  mov     [rcx], r15w
0x180017d25  mov     [rsp+250h+pdwReturnedProductType], r15; bool *
0x180017d2a  xor     r9d, r9d; unsigned int
0x180017d2d  lea     r8, a9197; "9197"
0x180017d34  mov     rdx, r14; wchar_t *
0x180017d37  mov     rcx, r12; HKEY
0x180017d3a  call    ?UtilRegGetDWORD@@YAKPEAUHKEY__@@PEB_W1KPEA_N_N@Z; UtilRegGetDWORD(HKEY__ *,wchar_t const *,wchar_t const *,ulong,bool *,bool)
0x180017d3f  mov     [rdi+70h], eax
0x180017d42  mov     [rsp+250h+pdwReturnedProductType], r15; bool *
0x180017d47  xor     r9d, r9d; unsigned int
0x180017d4a  lea     r8, a35; "35"
0x180017d51  mov     rdx, r14; wchar_t *
0x180017d54  mov     rcx, r12; HKEY
0x180017d57  call    ?UtilRegGetDWORD@@YAKPEAUHKEY__@@PEB_W1KPEA_N_N@Z; UtilRegGetDWORD(HKEY__ *,wchar_t const *,wchar_t const *,ulong,bool *,bool)
0x180017d5c  mov     [rdi+74h], eax
0x180017d5f  mov     [rsp+250h+pdwReturnedProductType], r15; bool *
0x180017d64  xor     r9d, r9d; unsigned int
0x180017d67  lea     r8, a12729; "12729"
0x180017d6e  mov     rdx, r14; wchar_t *
0x180017d71  mov     rcx, r12; HKEY
0x180017d74  call    ?UtilRegGetDWORD@@YAKPEAUHKEY__@@PEB_W1KPEA_N_N@Z; UtilRegGetDWORD(HKEY__ *,wchar_t const *,wchar_t const *,ulong,bool *,bool)
0x180017d79  mov     [rdi+78h], eax
0x180017d7c  mov     [rsp+250h+pdwReturnedProductType], r15; bool *
0x180017d81  xor     r9d, r9d; unsigned int
0x180017d84  lea     r8, a12730; "12730"
0x180017d8b  mov     rdx, r14; wchar_t *
0x180017d8e  mov     rcx, r12; HKEY
0x180017d91  call    ?UtilRegGetDWORD@@YAKPEAUHKEY__@@PEB_W1KPEA_N_N@Z; UtilRegGetDWORD(HKEY__ *,wchar_t const *,wchar_t const *,ulong,bool *,bool)
0x180017d96  mov     [rdi+7Ch], eax
0x180017d99  mov     [rsp+250h+pdwReturnedProductType], r15; bool *
0x180017d9e  xor     r9d, r9d; unsigned int
0x180017da1  lea     r8, a12736; "12736"
0x180017da8  mov     rdx, r14; wchar_t *
0x180017dab  mov     rcx, r12; HKEY
0x180017dae  call    ?UtilRegGetDWORD@@YAKPEAUHKEY__@@PEB_W1KPEA_N_N@Z; UtilRegGetDWORD(HKEY__ *,wchar_t const *,wchar_t const *,ulong,bool *,bool)
0x180017db3  mov     [rdi+80h], eax
0x180017db9  mov     [rsp+250h+pdwReturnedProductType], r15; bool *
0x180017dbe  xor     r9d, r9d; unsigned int
0x180017dc1  lea     r8, a12737; "12737"
0x180017dc8  mov     rdx, r14; wchar_t *
0x180017dcb  mov     rcx, r12; HKEY
0x180017dce  call    ?UtilRegGetDWORD@@YAKPEAUHKEY__@@PEB_W1KPEA_N_N@Z; UtilRegGetDWORD(HKEY__ *,wchar_t const *,wchar_t const *,ulong,bool *,bool)
0x180017dd3  mov     [rdi+84h], eax
0x180017dd9  lea     rsi, [rdi+88h]
0x180017de0  mov     rcx, rsi
0x180017de3  call    ?UtilGetBuildBranch@@YAJPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; UtilGetBuildBranch(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x180017de8  test    eax, eax
0x180017dea  jns     short loc_180017DF7
0x180017dec  mov     rcx, [rsi]
0x180017def  mov     [rsi+8], rcx
0x180017df3  mov     [rcx], r15w
0x180017df7  mov     [rsp+250h+var_220], bl; char
0x180017dfb  mov     [rsp+250h+var_228], bl; bool
0x180017dff  lea     rax, [rsp+250h+var_1F0]
0x180017e04  mov     [rsp+250h+pdwReturnedProductType], rax; __int64
0x180017e09  lea     r9, Src
0x180017e10  lea     r8, aCurrenttype; "CurrentType"
0x180017e17  lea     rdx, aSoftwareMicros_33; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180017e1e  mov     rcx, r12; hkey
0x180017e21  call    ?UtilRegGetString@@YAJPEAUHKEY__@@PEB_W11PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@_N3@Z; UtilRegGetString(HKEY__ *,wchar_t const *,wchar_t const *,wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,bool,bool)
0x180017e26  test    eax, eax
0x180017e28  js      short loc_180017E5B
0x180017e2a  mov     rcx, [rsp+250h+var_1F0]
0x180017e2f  mov     rdx, [rsp+250h+var_1E8]
0x180017e34  sub     rdx, rcx
0x180017e37  sar     rdx, 1
0x180017e3a  mov     [rsp+250h+pdwReturnedProductType], 7
0x180017e43  lea     r9, aChecked; "Checked"
0x180017e4a  call    ?find@?$_StringTraits@U?$transform_traits@_WUascii_toupper_transform@tlx@@@tlx@@@utl@@SA_KPEB_W_K101@Z; utl::_StringTraits<tlx::transform_traits<wchar_t,tlx::ascii_toupper_transform>>::find(wchar_t const *,unsigned __int64,unsigned __int64,wchar_t const *,unsigned __int64)
0x180017e4f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180017e53  jz      short loc_180017E5B
0x180017e55  mov     [rdi+0A8h], ebx
0x180017e5b  mov     [rsp+250h+pdwReturnedProductType], r15; bool *
0x180017e60  xor     r9d, r9d; unsigned int
0x180017e63  lea     r8, a12675; "12675"
0x180017e6a  mov     rdx, r14; wchar_t *
0x180017e6d  mov     rcx, r12; HKEY
0x180017e70  call    ?UtilRegGetDWORD@@YAKPEAUHKEY__@@PEB_W1KPEA_N_N@Z; UtilRegGetDWORD(HKEY__ *,wchar_t const *,wchar_t const *,ulong,bool *,bool)
0x180017e75  mov     [rdi+0ACh], eax
0x180017e7b  mov     [rsp+250h+pdwReturnedProductType], r15; bool *
0x180017e80  xor     r9d, r9d; unsigned int
0x180017e83  lea     r8, a12676; "12676"
0x180017e8a  mov     rdx, r14; wchar_t *
0x180017e8d  mov     rcx, r12; HKEY
0x180017e90  call    ?UtilRegGetDWORD@@YAKPEAUHKEY__@@PEB_W1KPEA_N_N@Z; UtilRegGetDWORD(HKEY__ *,wchar_t const *,wchar_t const *,ulong,bool *,bool)
0x180017e95  mov     [rdi+0B0h], eax
0x180017e9b  mov     [rsp+250h+pdwReturnedProductType], r15; bool *
0x180017ea0  xor     r9d, r9d; unsigned int
0x180017ea3  lea     r8, a12677; "12677"
0x180017eaa  mov     rdx, r14; wchar_t *
0x180017ead  mov     rcx, r12; HKEY
0x180017eb0  call    ?UtilRegGetDWORD@@YAKPEAUHKEY__@@PEB_W1KPEA_N_N@Z; UtilRegGetDWORD(HKEY__ *,wchar_t const *,wchar_t const *,ulong,bool *,bool)
0x180017eb5  mov     [rdi+0B4h], eax
0x180017ebb  mov     [rsp+250h+pdwReturnedProductType], r15; bool *
0x180017ec0  xor     r9d, r9d; unsigned int
0x180017ec3  lea     r8, a12678; "12678"
0x180017eca  mov     rdx, r14; wchar_t *
0x180017ecd  mov     rcx, r12; HKEY
0x180017ed0  call    ?UtilRegGetDWORD@@YAKPEAUHKEY__@@PEB_W1KPEA_N_N@Z; UtilRegGetDWORD(HKEY__ *,wchar_t const *,wchar_t const *,ulong,bool *,bool)
0x180017ed5  mov     [rdi+0B8h], eax
0x180017edb  lea     rsi, [rdi+0C0h]
0x180017ee2  lea     rcx, [rsp+250h+var_1F0]
0x180017ee7  call    ?UtilGetPlatformVersion@@YAJPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; UtilGetPlatformVersion(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x180017eec  test    eax, eax
0x180017eee  js      short loc_180017F15
0x180017ef0  mov     rax, [rsp+250h+var_1F0]
0x180017ef5  mov     [rsp+250h+pdwReturnedProductType], rax
0x180017efa  mov     r9d, [rbp+150h+VersionInformation.dwMinorVersion]
0x180017efe  mov     r8d, [rbp+150h+VersionInformation.dwMajorVersion]
0x180017f02  lea     rdx, aDDLs; "%d.%d.%ls"
0x180017f09  mov     rcx, rsi
0x180017f0c  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x180017f11  test    eax, eax
0x180017f13  jns     short loc_180017F20
0x180017f15  mov     rcx, [rsi]
0x180017f18  mov     [rsi+8], rcx
0x180017f1c  mov     [rcx], r15w
0x180017f20  lea     rsi, [rdi+0E8h]
  ... truncated ...
```
