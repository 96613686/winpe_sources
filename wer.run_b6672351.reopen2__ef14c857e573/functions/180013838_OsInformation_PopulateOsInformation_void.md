# OsInformation::PopulateOsInformation(void)

- ea: `0x180013838`
- end: `0x180013f6d`
- name: `?PopulateOsInformation@OsInformation@@QEAAJXZ`
- size: `1845`
- prototype: `__int64 __fastcall(OsInformation *__hidden this)`
- caller_count: `2`
- callee_count: `19`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18001308c`
- `0x1800a4fd8`

## callees

- `0x180008e38`
- `0x18000db80`
- `0x18000e31c`
- `0x180013838`
- `0x18001be50`
- `0x180029b70`
- `0x18002a0f4`
- `0x180040950`
- `0x180043e9c`
- `0x180046e94`
- `0x180047140`
- `0x1800494a8`
- `0x18004be40`
- `0x18004cd60`
- `0x180053300`
- `0x180053d3c`
- `0x180068b64`
- `0x18009bbd8`
- `0x18009cfac`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetUserGeoID` at `0x18001399f`
- `api-ms-win-core-localization-l1-2-0!GetUserGeoID` at `0x18001399f`
- `api-ms-win-core-localization-l1-2-0!GetSystemDefaultLCID` at `0x18001398b`
- `api-ms-win-core-localization-l1-2-0!GetSystemDefaultLCID` at `0x18001398b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180013a5b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180013a5b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013948`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013948`
- `ntdll!RtlGetVersion` at `0x180013901`
- `ntdll!RtlGetVersion` at `0x180013901`
- `api-ms-win-core-sysinfo-l1-2-0!GetNativeSystemInfo` at `0x18001396d`
- `api-ms-win-core-sysinfo-l1-2-0!GetNativeSystemInfo` at `0x18001396d`
- `api-ms-win-core-sysinfo-l1-2-0!GetProductInfo` at `0x180013938`
- `api-ms-win-core-sysinfo-l1-2-0!GetProductInfo` at `0x180013938`

## string_xrefs

- `0x1800139de`: `SOFTWARE\Microsoft\SQMClient\Windows\CommonDatapoints`
- `0x180013a20`: `TelemetryProtocolServerRoles`
- `0x180013aec`: `svcUpdateVersion`
- `0x180013d85`: `UpdateID`
- `0x180013ed1`: `SOFTWARE\Microsoft\Windows\CurrentVersion\Component Based Servicing\Interface`

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
  __int64 v16; // r8
  _WORD *v17; // rcx
  _WORD *v18; // rcx
  unsigned int DWORD; // eax
  _WORD *v20; // rcx
  _WORD *v21; // rcx
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
  bool v38; // [rsp+28h] [rbp-D8h]
  bool v39; // [rsp+40h] [rbp-C0h] BYREF
  struct _FILETIME v40; // [rsp+48h] [rbp-B8h]
  struct _FILETIME FileTime; // [rsp+50h] [rbp-B0h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v43; // [rsp+60h] [rbp-A0h] BYREF
  _WORD *v44; // [rsp+68h] [rbp-98h]
  _WORD v45[8]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v46[2]; // [rsp+80h] [rbp-80h] BYREF
  _WORD v47[8]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v48[2]; // [rsp+A0h] [rbp-60h] BYREF
  _WORD v49[8]; // [rsp+B0h] [rbp-50h] BYREF
  struct _SYSTEM_INFO SystemInfo; // [rsp+C0h] [rbp-40h] BYREF
  struct _OSVERSIONINFOW VersionInformation; // [rsp+F0h] [rbp-10h] BYREF
  unsigned __int16 v52; // [rsp+204h] [rbp+104h]
  unsigned __int8 v53; // [rsp+20Ah] [rbp+10Ah]
  unsigned int v54; // [rsp+20Ch] [rbp+10Ch]

  memset_0(&VersionInformation.dwMajorVersion, 0, 0x120u);
  memset(&SystemInfo, 0, sizeof(SystemInfo));
  SystemTimeAsFileTime = 0;
  FileTime = 0;
  v40 = 0;
  v48[0] = (__int64)v49;
  v48[1] = (__int64)v49;
  v49[0] = 0;
  v46[0] = (__int64)v47;
  v46[1] = (__int64)v47;
  v47[0] = 0;
  v43 = (__int64)v45;
  v44 = v45;
  v45[0] = 0;
  v39 = 0;
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
      *((_QWORD *)this + 6) = v54;
      if ( GetProductInfo(0xFFFFFFFF, 0xFFFFFFFF, 0xFFFFFFFF, 0xFFFFFFFF, (PDWORD)this + 9) )
      {
        GetNativeSystemInfo(&SystemInfo);
        *((_DWORD *)this + 1) = VersionInformation.dwMajorVersion;
        *((_DWORD *)this + 2) = VersionInformation.dwMinorVersion;
        *((_DWORD *)this + 3) = VersionInformation.dwBuildNumber;
        *((_DWORD *)this + 7) = GetSystemDefaultLCID();
        *((_DWORD *)this + 8) = GetUserGeoID(0x10u);
        *((_DWORD *)this + 14) = v53;
        *((_DWORD *)this + 15) = VersionInformation.dwPlatformId;
        *((_DWORD *)this + 5) = v52;
        *((_DWORD *)this + 6) = SystemInfo.wProcessorArchitecture;
        *((_DWORD *)this + 10) = UtilRegGetDWORD(
                                   HKEY_LOCAL_MACHINE,
                                   L"SOFTWARE\\Microsoft\\SQMClient\\Windows\\CommonDatapoints",
                                   L"608",
                                   0,
                                   0,
                                   v23);
        *((_DWORD *)this + 4) = UtilRegGetDWORD(
                                  HKEY_LOCAL_MACHINE,
                                  L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion",
                                  L"UBR",
                                  0,
                                  0,
                                  v24);
        *((_QWORD *)this + 8) = UtilRegGetQWORD(
                                  HKEY_LOCAL_MACHINE,
                                  L"SOFTWARE\\Microsoft\\SQMClient\\Windows",
                                  L"TelemetryProtocolServerRoles",
                                  v5,
                                  0,
                                  v25);
        v6 = v40;
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
                                   v26);
        if ( (int)UtilRegGetString(
                    HKEY_LOCAL_MACHINE,
                    L"SOFTWARE\\Microsoft\\Internet Explorer",
                    L"svcVersion",
                    (__int64)v48,
                    1,
                    1) < 0
          || (int)UtilRegGetString(
                    HKEY_LOCAL_MACHINE,
                    L"SOFTWARE\\Microsoft\\Internet Explorer",
                    L"svcUpdateVersion",
                    (__int64)v46,
                    1,
                    1) < 0
          || (int)tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
                    (char *)this + 80,
                    L"%ls-%ls",
                    v48[0],
                    v46[0]) < 0 )
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
                                   v27);
        *((_DWORD *)this + 29) = UtilRegGetDWORD(
                                   HKEY_LOCAL_MACHINE,
                                   L"SOFTWARE\\Microsoft\\SQMClient\\Windows\\CommonDatapoints",
                                   L"35",
                                   0,
                                   0,
                                   v28);
        *((_DWORD *)this + 30) = UtilRegGetDWORD(
                                   HKEY_LOCAL_MACHINE,
                                   L"SOFTWARE\\Microsoft\\SQMClient\\Windows\\CommonDatapoints",
                                   L"12729",
                                   0,
                                   0,
                                   v29);
        *((_DWORD *)this + 31) = UtilRegGetDWORD(
                                   HKEY_LOCAL_MACHINE,
                                   L"SOFTWARE\\Microsoft\\SQMClient\\Windows\\CommonDatapoints",
                                   L"12730",
                                   0,
                                   0,
                                   v30);
        *((_DWORD *)this + 32) = UtilRegGetDWORD(
                                   HKEY_LOCAL_MACHINE,
                                   L"SOFTWARE\\Microsoft\\SQMClient\\Windows\\CommonDatapoints",
                                   L"12736",
                                   0,
                                   0,
                                   v31);
        *((_DWORD *)this + 33) = UtilRegGetDWORD(
                                   HKEY_LOCAL_MACHINE,
                                   L"SOFTWARE\\Microsoft\\SQMClient\\Windows\\CommonDatapoints",
                                   L"12737",
                                   0,
                                   0,
                                   v32);
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
                    (__int64)&v43,
                    1,
                    1) >= 0
          && utl::_StringTraits<tlx::transform_traits<wchar_t,tlx::ascii_toupper_transform>>::find(
               v43,
               ((__int64)v44 - v43) >> 1,
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
                                   v33);
        *((_DWORD *)this + 44) = UtilRegGetDWORD(
                                   HKEY_LOCAL_MACHINE,
                                   L"SOFTWARE\\Microsoft\\SQMClient\\Windows\\CommonDatapoints",
                                   L"12676",
                                   0,
                                   0,
                                   v34);
        *((_DWORD *)this + 45) = UtilRegGetDWORD(
                                   HKEY_LOCAL_MACHINE,
                                   L"SOFTWARE\\Microsoft\\SQMClient\\Windows\\CommonDatapoints",
                                   L"12677",
                                   0,
                                   0,
                                   v35);
        *((_DWORD *)this + 46) = UtilRegGetDWORD(
                                   HKEY_LOCAL_MACHINE,
                                   L"SOFTWARE\\Microsoft\\SQMClient\\Windows\\CommonDatapoints",
                                   L"12678",
                                   0,
                                   0,
                                   v36);
        if ( (int)UtilGetPlatformVersion(&v43) < 0
          || (int)tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
                    (char *)this + 192,
                    L"%d.%d.%ls",
                    VersionInformation.dwMajorVersion,
                    VersionInformation.dwMinorVersion,
                    v43) < 0 )
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
          v17 = (_WORD *)*((_QWORD *)this + 41);
          *((_QWORD *)this + 42) = v17;
          *v17 = 0;
        }
        if ( (int)UtilGetFeatureConfigurations((char *)this + 360, v15, v16) < 0 )
        {
          v18 = (_WORD *)*((_QWORD *)this + 45);
          *((_QWORD *)this + 46) = v18;
          *v18 = 0;
        }
        DWORD = UtilRegGetDWORD(
                  HKEY_LOCAL_MACHINE,
                  L"SYSTEM\\CurrentControlSet\\Control",
                  L"ContainerType",
                  0,
                  &v39,
                  v37);
        if ( !v39
          && (int)tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
                    (char *)this + 456,
                    L"%u",
                    DWORD) < 0 )
        {
          v20 = (_WORD *)*((_QWORD *)this + 57);
          *((_QWORD *)this + 58) = v20;
          *v20 = 0;
        }
        if ( (int)UtilRegGetString(
                    HKEY_LOCAL_MACHINE,
                    L"SYSTEM\\CurrentControlSet\\Control",
                    L"ContainerId",
                    (__int64)this + 424,
                    0,
                    1) < 0 )
        {
          v21 = (_WORD *)*((_QWORD *)this + 53);
          *((_QWORD *)this + 54) = v21;
          *v21 = 0;
        }
        if ( (int)UtilIsEdu((unsigned int *)this + 56) < 0 )
          *((_DWORD *)this + 56) = 0;
        *((_DWORD *)this + 122) = UtilRegGetDWORD(
                                    HKEY_LOCAL_MACHINE,
                                    L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Component Based Servicing\\Interface",
                                    L"ServicingInProgress",
                                    0,
                                    0,
                                    v38);
        if ( (int)UtilIsFeatureUpdatePendingReboot((unsigned int *)this + 123) < 0 )
          *((_DWORD *)this + 123) = 0;
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_RecoveryRobustnessFeature>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_RecoveryRobustnessFeature>::GetImpl'::`2'::impl) )
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
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(&v43);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v46);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v48);
  return v2;
}

```

## disassembly

```asm
0x180013838  mov     [rsp-8+arg_8], rbx
0x18001383d  mov     [rsp-8+arg_10], rsi
0x180013842  push    rbp
0x180013843  push    rdi
0x180013844  push    r12
0x180013846  push    r14
0x180013848  push    r15
0x18001384a  lea     rbp, [rsp-130h]
0x180013852  sub     rsp, 230h
0x180013859  mov     rax, cs:__security_cookie
0x180013860  xor     rax, rsp
0x180013863  mov     [rbp+150h+var_30], rax
0x18001386a  mov     rdi, rcx
0x18001386d  xor     edx, edx; Val
0x18001386f  mov     r8d, 120h; Size
0x180013875  lea     rcx, [rbp+150h+VersionInformation.dwMajorVersion]; void *
0x180013879  call    memset_0
0x18001387e  xorps   xmm0, xmm0
0x180013881  movups  xmmword ptr [rbp+150h+SystemInfo], xmm0
0x180013885  movups  xmmword ptr [rbp+150h+SystemInfo.lpMaximumApplicationAddress], xmm0
0x180013889  movups  xmmword ptr [rbp+150h+SystemInfo.dwNumberOfProcessors], xmm0
0x18001388d  xor     r15d, r15d
0x180013890  mov     qword ptr [rsp+250h+SystemTimeAsFileTime.dwLowDateTime], r15
0x180013895  mov     qword ptr [rsp+250h+FileTime.dwLowDateTime], r15
0x18001389a  mov     [rsp+250h+var_208], r15
0x18001389f  lea     rax, [rbp+150h+var_1A0]
0x1800138a3  mov     [rbp+150h+var_1B0], rax
0x1800138a7  lea     rax, [rbp+150h+var_1A0]
0x1800138ab  mov     [rbp+150h+var_1A8], rax
0x1800138af  mov     [rbp+150h+var_1A0], r15w
0x1800138b4  lea     rax, [rbp+150h+var_1C0]
0x1800138b8  mov     [rbp+150h+var_1D0], rax
0x1800138bc  lea     rax, [rbp+150h+var_1C0]
0x1800138c0  mov     [rbp+150h+var_1C8], rax
0x1800138c4  mov     [rbp+150h+var_1C0], r15w
0x1800138c9  lea     rax, [rsp+250h+var_1E0]
0x1800138ce  mov     [rsp+250h+var_1F0], rax
0x1800138d3  lea     rax, [rsp+250h+var_1E0]
0x1800138d8  mov     [rsp+250h+var_1E8], rax
0x1800138dd  mov     [rsp+250h+var_1E0], r15w
0x1800138e3  mov     [rsp+250h+var_210], r15b
0x1800138e8  cmp     [rdi], r15d
0x1800138eb  jz      short loc_1800138F6
0x1800138ed  lea     ebx, [r15+1]
0x1800138f1  jmp     loc_180013F21
0x1800138f6  mov     [rbp+150h+VersionInformation.dwOSVersionInfoSize], 124h
0x1800138fd  lea     rcx, [rbp+150h+VersionInformation]; lpVersionInformation
0x180013901  call    cs:__imp_RtlGetVersion
0x180013908  nop     dword ptr [rax+rax+00h]
0x18001390d  test    eax, eax
0x18001390f  jns     short loc_18001391A
0x180013911  bts     eax, 1Ch
0x180013915  jmp     loc_180013F1F
0x18001391a  mov     eax, [rbp+150h+var_44]
0x180013920  mov     [rdi+30h], rax
0x180013924  lea     rax, [rdi+24h]
0x180013928  mov     [rsp+250h+pdwReturnedProductType], rax; pdwReturnedProductType
0x18001392d  or      ecx, 0FFFFFFFFh; dwOSMajorVersion
0x180013930  mov     r9d, ecx; dwSpMinorVersion
0x180013933  mov     r8d, ecx; dwSpMajorVersion
0x180013936  mov     edx, ecx; dwOSMinorVersion
0x180013938  call    cs:__imp_GetProductInfo
0x18001393f  nop     dword ptr [rax+rax+00h]
0x180013944  test    eax, eax
0x180013946  jnz     short loc_180013969
0x180013948  call    cs:__imp_GetLastError
0x18001394f  nop     dword ptr [rax+rax+00h]
0x180013954  test    eax, eax
0x180013956  jle     loc_180013F1F
0x18001395c  movzx   eax, ax
0x18001395f  or      eax, 80070000h
0x180013964  jmp     loc_180013F1F
0x180013969  lea     rcx, [rbp+150h+SystemInfo]; lpSystemInfo
0x18001396d  call    cs:__imp_GetNativeSystemInfo
0x180013974  nop     dword ptr [rax+rax+00h]
0x180013979  mov     eax, [rbp+150h+VersionInformation.dwMajorVersion]
0x18001397c  mov     [rdi+4], eax
0x18001397f  mov     eax, [rbp+150h+VersionInformation.dwMinorVersion]
0x180013982  mov     [rdi+8], eax
0x180013985  mov     eax, [rbp+150h+VersionInformation.dwBuildNumber]
0x180013988  mov     [rdi+0Ch], eax
0x18001398b  call    cs:__imp_GetSystemDefaultLCID
0x180013992  nop     dword ptr [rax+rax+00h]
0x180013997  mov     [rdi+1Ch], eax
0x18001399a  mov     ecx, 10h; GeoClass
0x18001399f  call    cs:__imp_GetUserGeoID
0x1800139a6  nop     dword ptr [rax+rax+00h]
0x1800139ab  mov     [rdi+20h], eax
0x1800139ae  movzx   eax, [rbp+150h+var_46]
0x1800139b5  mov     [rdi+38h], eax
0x1800139b8  mov     eax, [rbp+150h+VersionInformation.dwPlatformId]
0x1800139bb  mov     [rdi+3Ch], eax
0x1800139be  movzx   eax, [rbp+150h+var_4C]
0x1800139c5  mov     [rdi+14h], eax
0x1800139c8  movzx   eax, word ptr [rbp+150h+SystemInfo]
0x1800139cc  mov     [rdi+18h], eax
0x1800139cf  mov     [rsp+250h+pdwReturnedProductType], r15; bool *
0x1800139d4  xor     r9d, r9d; unsigned int
0x1800139d7  lea     r8, a608; "608"
0x1800139de  lea     r14, aSoftwareMicros_32; "SOFTWARE\\Microsoft\\SQMClient\\Windows"...
0x1800139e5  mov     rdx, r14; wchar_t *
0x1800139e8  mov     r12, 0FFFFFFFF80000002h
0x1800139ef  mov     rcx, r12; HKEY
0x1800139f2  call    ?UtilRegGetDWORD@@YAKPEAUHKEY__@@PEB_W1KPEA_N_N@Z; UtilRegGetDWORD(HKEY__ *,wchar_t const *,wchar_t const *,ulong,bool *,bool)
0x1800139f7  mov     [rdi+28h], eax
0x1800139fa  mov     [rsp+250h+pdwReturnedProductType], r15; bool *
0x1800139ff  xor     r9d, r9d; unsigned int
0x180013a02  lea     r8, aUbr_0; "UBR"
0x180013a09  lea     rdx, aSoftwareMicros_36; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180013a10  mov     rcx, r12; HKEY
0x180013a13  call    ?UtilRegGetDWORD@@YAKPEAUHKEY__@@PEB_W1KPEA_N_N@Z; UtilRegGetDWORD(HKEY__ *,wchar_t const *,wchar_t const *,ulong,bool *,bool)
0x180013a18  mov     [rdi+10h], eax
0x180013a1b  mov     [rsp+250h+pdwReturnedProductType], r15; bool *
0x180013a20  lea     r8, aTelemetryproto; "TelemetryProtocolServerRoles"
0x180013a27  lea     rdx, aSoftwareMicros_16; "SOFTWARE\\Microsoft\\SQMClient\\Windows"
0x180013a2e  mov     rcx, r12; HKEY
0x180013a31  call    ?UtilRegGetQWORD@@YA_KPEAUHKEY__@@PEB_W1_KPEA_N_N@Z; UtilRegGetQWORD(HKEY__ *,wchar_t const *,wchar_t const *,unsigned __int64,bool *,bool)
0x180013a36  mov     [rdi+40h], rax
0x180013a3a  lea     rcx, [rsp+250h+FileTime]; lpFileTime
0x180013a3f  call    ?UtilGetInstallTime@@YAJPEAU_FILETIME@@@Z; UtilGetInstallTime(_FILETIME *)
0x180013a44  mov     rbx, [rsp+250h+var_208]
0x180013a49  test    eax, eax
0x180013a4b  cmovns  rbx, qword ptr [rsp+250h+FileTime.dwLowDateTime]
0x180013a51  test    rbx, rbx
0x180013a54  jz      short loc_180013A88
0x180013a56  lea     rcx, [rsp+250h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180013a5b  call    cs:__imp_GetSystemTimeAsFileTime
0x180013a62  nop     dword ptr [rax+rax+00h]
0x180013a67  mov     rcx, qword ptr [rsp+250h+SystemTimeAsFileTime.dwLowDateTime]
0x180013a6c  cmp     rcx, rbx
0x180013a6f  jbe     short loc_180013A88
0x180013a71  sub     rcx, rbx
0x180013a74  mov     rax, 0E5109EC205D7BEA7h
0x180013a7e  mul     rcx
0x180013a81  shr     rdx, 1Dh
0x180013a85  mov     [rdi+48h], edx
0x180013a88  mov     [rsp+250h+pdwReturnedProductType], r15; bool *
0x180013a8d  xor     r9d, r9d; unsigned int
0x180013a90  lea     r8, a9292; "9292"
0x180013a97  mov     rdx, r14; wchar_t *
0x180013a9a  mov     rcx, r12; HKEY
0x180013a9d  call    ?UtilRegGetDWORD@@YAKPEAUHKEY__@@PEB_W1KPEA_N_N@Z; UtilRegGetDWORD(HKEY__ *,wchar_t const *,wchar_t const *,ulong,bool *,bool)
0x180013aa2  mov     [rdi+4Ch], eax
0x180013aa5  mov     ebx, 1
0x180013aaa  mov     [rsp+250h+var_220], bl; char
0x180013aae  mov     [rsp+250h+var_228], bl; char
0x180013ab2  lea     rax, [rbp+150h+var_1B0]
0x180013ab6  mov     [rsp+250h+pdwReturnedProductType], rax; __int64
0x180013abb  xor     r9d, r9d
0x180013abe  lea     r8, aSvcversion; "svcVersion"
0x180013ac5  lea     rdx, aSoftwareMicros_13; "SOFTWARE\\Microsoft\\Internet Explorer"
0x180013acc  mov     rcx, r12; hkey
0x180013acf  call    ?UtilRegGetString@@YAJPEAUHKEY__@@PEB_W11PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@_N3@Z; UtilRegGetString(HKEY__ *,wchar_t const *,wchar_t const *,wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,bool,bool)
0x180013ad4  test    eax, eax
0x180013ad6  js      short loc_180013B22
0x180013ad8  mov     [rsp+250h+var_220], bl; char
0x180013adc  mov     [rsp+250h+var_228], bl; char
0x180013ae0  lea     rax, [rbp+150h+var_1D0]
0x180013ae4  mov     [rsp+250h+pdwReturnedProductType], rax; __int64
0x180013ae9  xor     r9d, r9d
0x180013aec  lea     r8, aSvcupdateversi; "svcUpdateVersion"
0x180013af3  lea     rdx, aSoftwareMicros_13; "SOFTWARE\\Microsoft\\Internet Explorer"
0x180013afa  mov     rcx, r12; hkey
0x180013afd  call    ?UtilRegGetString@@YAJPEAUHKEY__@@PEB_W11PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@_N3@Z; UtilRegGetString(HKEY__ *,wchar_t const *,wchar_t const *,wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,bool,bool)
0x180013b02  test    eax, eax
0x180013b04  js      short loc_180013B22
0x180013b06  lea     rcx, [rdi+50h]
0x180013b0a  mov     r9, [rbp+150h+var_1D0]
0x180013b0e  mov     r8, [rbp+150h+var_1B0]
0x180013b12  lea     rdx, aLsLs; "%ls-%ls"
0x180013b19  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x180013b1e  test    eax, eax
0x180013b20  jns     short loc_180013B2E
0x180013b22  mov     rcx, [rdi+50h]
0x180013b26  mov     [rdi+58h], rcx
0x180013b2a  mov     [rcx], r15w
0x180013b2e  lea     rsi, [rdi+188h]
0x180013b35  mov     [rsp+250h+var_220], bl; char
0x180013b39  mov     [rsp+250h+var_228], r15b; bool
0x180013b3e  mov     [rsp+250h+pdwReturnedProductType], rsi; __int64
0x180013b43  lea     r9, aUnknown_0; "Unknown"
0x180013b4a  lea     r8, aEditionid; "EditionID"
0x180013b51  lea     rdx, aSoftwareMicros_36; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180013b58  mov     rcx, r12; hkey
0x180013b5b  call    ?UtilRegGetString@@YAJPEAUHKEY__@@PEB_W11PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@_N3@Z; UtilRegGetString(HKEY__ *,wchar_t const *,wchar_t const *,wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,bool,bool)
0x180013b60  test    eax, eax
0x180013b62  jns     short loc_180013B6F
0x180013b64  mov     rcx, [rsi]
0x180013b67  mov     [rsi+8], rcx
0x180013b6b  mov     [rcx], r15w
0x180013b6f  mov     [rsp+250h+pdwReturnedProductType], r15; bool *
0x180013b74  xor     r9d, r9d; unsigned int
0x180013b77  lea     r8, a9197; "9197"
0x180013b7e  mov     rdx, r14; wchar_t *
0x180013b81  mov     rcx, r12; HKEY
0x180013b84  call    ?UtilRegGetDWORD@@YAKPEAUHKEY__@@PEB_W1KPEA_N_N@Z; UtilRegGetDWORD(HKEY__ *,wchar_t const *,wchar_t const *,ulong,bool *,bool)
0x180013b89  mov     [rdi+70h], eax
0x180013b8c  mov     [rsp+250h+pdwReturnedProductType], r15; bool *
0x180013b91  xor     r9d, r9d; unsigned int
0x180013b94  lea     r8, a35; "35"
0x180013b9b  mov     rdx, r14; wchar_t *
0x180013b9e  mov     rcx, r12; HKEY
0x180013ba1  call    ?UtilRegGetDWORD@@YAKPEAUHKEY__@@PEB_W1KPEA_N_N@Z; UtilRegGetDWORD(HKEY__ *,wchar_t const *,wchar_t const *,ulong,bool *,bool)
0x180013ba6  mov     [rdi+74h], eax
0x180013ba9  mov     [rsp+250h+pdwReturnedProductType], r15; bool *
0x180013bae  xor     r9d, r9d; unsigned int
0x180013bb1  lea     r8, a12729; "12729"
0x180013bb8  mov     rdx, r14; wchar_t *
0x180013bbb  mov     rcx, r12; HKEY
0x180013bbe  call    ?UtilRegGetDWORD@@YAKPEAUHKEY__@@PEB_W1KPEA_N_N@Z; UtilRegGetDWORD(HKEY__ *,wchar_t const *,wchar_t const *,ulong,bool *,bool)
0x180013bc3  mov     [rdi+78h], eax
0x180013bc6  mov     [rsp+250h+pdwReturnedProductType], r15; bool *
0x180013bcb  xor     r9d, r9d; unsigned int
0x180013bce  lea     r8, a12730; "12730"
0x180013bd5  mov     rdx, r14; wchar_t *
0x180013bd8  mov     rcx, r12; HKEY
0x180013bdb  call    ?UtilRegGetDWORD@@YAKPEAUHKEY__@@PEB_W1KPEA_N_N@Z; UtilRegGetDWORD(HKEY__ *,wchar_t const *,wchar_t const *,ulong,bool *,bool)
0x180013be0  mov     [rdi+7Ch], eax
0x180013be3  mov     [rsp+250h+pdwReturnedProductType], r15; bool *
0x180013be8  xor     r9d, r9d; unsigned int
0x180013beb  lea     r8, a12736; "12736"
0x180013bf2  mov     rdx, r14; wchar_t *
0x180013bf5  mov     rcx, r12; HKEY
0x180013bf8  call    ?UtilRegGetDWORD@@YAKPEAUHKEY__@@PEB_W1KPEA_N_N@Z; UtilRegGetDWORD(HKEY__ *,wchar_t const *,wchar_t const *,ulong,bool *,bool)
0x180013bfd  mov     [rdi+80h], eax
0x180013c03  mov     [rsp+250h+pdwReturnedProductType], r15; bool *
0x180013c08  xor     r9d, r9d; unsigned int
0x180013c0b  lea     r8, a12737; "12737"
0x180013c12  mov     rdx, r14; wchar_t *
0x180013c15  mov     rcx, r12; HKEY
0x180013c18  call    ?UtilRegGetDWORD@@YAKPEAUHKEY__@@PEB_W1KPEA_N_N@Z; UtilRegGetDWORD(HKEY__ *,wchar_t const *,wchar_t const *,ulong,bool *,bool)
0x180013c1d  mov     [rdi+84h], eax
0x180013c23  lea     rsi, [rdi+88h]
0x180013c2a  mov     rcx, rsi
0x180013c2d  call    ?UtilGetBuildBranch@@YAJPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; UtilGetBuildBranch(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x180013c32  test    eax, eax
0x180013c34  jns     short loc_180013C41
0x180013c36  mov     rcx, [rsi]
0x180013c39  mov     [rsi+8], rcx
0x180013c3d  mov     [rcx], r15w
0x180013c41  mov     [rsp+250h+var_220], bl; char
0x180013c45  mov     [rsp+250h+var_228], bl; bool
0x180013c49  lea     rax, [rsp+250h+var_1F0]
0x180013c4e  mov     [rsp+250h+pdwReturnedProductType], rax; __int64
0x180013c53  lea     r9, Src
0x180013c5a  lea     r8, aCurrenttype; "CurrentType"
0x180013c61  lea     rdx, aSoftwareMicros_36; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180013c68  mov     rcx, r12; hkey
0x180013c6b  call    ?UtilRegGetString@@YAJPEAUHKEY__@@PEB_W11PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@_N3@Z; UtilRegGetString(HKEY__ *,wchar_t const *,wchar_t const *,wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,bool,bool)
0x180013c70  test    eax, eax
0x180013c72  js      short loc_180013CA5
0x180013c74  mov     rcx, [rsp+250h+var_1F0]
0x180013c79  mov     rdx, [rsp+250h+var_1E8]
0x180013c7e  sub     rdx, rcx
0x180013c81  sar     rdx, 1
0x180013c84  mov     [rsp+250h+pdwReturnedProductType], 7
0x180013c8d  lea     r9, aChecked; "Checked"
0x180013c94  call    ?find@?$_StringTraits@U?$transform_traits@_WUascii_toupper_transform@tlx@@@tlx@@@utl@@SA_KPEB_W_K101@Z; utl::_StringTraits<tlx::transform_traits<wchar_t,tlx::ascii_toupper_transform>>::find(wchar_t const *,unsigned __int64,unsigned __int64,wchar_t const *,unsigned __int64)
0x180013c99  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180013c9d  jz      short loc_180013CA5
0x180013c9f  mov     [rdi+0A8h], ebx
0x180013ca5  mov     [rsp+250h+pdwReturnedProductType], r15; bool *
0x180013caa  xor     r9d, r9d; unsigned int
0x180013cad  lea     r8, a12675; "12675"
0x180013cb4  mov     rdx, r14; wchar_t *
0x180013cb7  mov     rcx, r12; HKEY
0x180013cba  call    ?UtilRegGetDWORD@@YAKPEAUHKEY__@@PEB_W1KPEA_N_N@Z; UtilRegGetDWORD(HKEY__ *,wchar_t const *,wchar_t const *,ulong,bool *,bool)
0x180013cbf  mov     [rdi+0ACh], eax
0x180013cc5  mov     [rsp+250h+pdwReturnedProductType], r15; bool *
0x180013cca  xor     r9d, r9d; unsigned int
0x180013ccd  lea     r8, a12676; "12676"
0x180013cd4  mov     rdx, r14; wchar_t *
0x180013cd7  mov     rcx, r12; HKEY
0x180013cda  call    ?UtilRegGetDWORD@@YAKPEAUHKEY__@@PEB_W1KPEA_N_N@Z; UtilRegGetDWORD(HKEY__ *,wchar_t const *,wchar_t const *,ulong,bool *,bool)
0x180013cdf  mov     [rdi+0B0h], eax
0x180013ce5  mov     [rsp+250h+pdwReturnedProductType], r15; bool *
0x180013cea  xor     r9d, r9d; unsigned int
0x180013ced  lea     r8, a12677; "12677"
0x180013cf4  mov     rdx, r14; wchar_t *
0x180013cf7  mov     rcx, r12; HKEY
0x180013cfa  call    ?UtilRegGetDWORD@@YAKPEAUHKEY__@@PEB_W1KPEA_N_N@Z; UtilRegGetDWORD(HKEY__ *,wchar_t const *,wchar_t const *,ulong,bool *,bool)
0x180013cff  mov     [rdi+0B4h], eax
0x180013d05  mov     [rsp+250h+pdwReturnedProductType], r15; bool *
0x180013d0a  xor     r9d, r9d; unsigned int
0x180013d0d  lea     r8, a12678; "12678"
0x180013d14  mov     rdx, r14; wchar_t *
0x180013d17  mov     rcx, r12; HKEY
0x180013d1a  call    ?UtilRegGetDWORD@@YAKPEAUHKEY__@@PEB_W1KPEA_N_N@Z; UtilRegGetDWORD(HKEY__ *,wchar_t const *,wchar_t const *,ulong,bool *,bool)
0x180013d1f  mov     [rdi+0B8h], eax
0x180013d25  lea     rsi, [rdi+0C0h]
0x180013d2c  lea     rcx, [rsp+250h+var_1F0]
0x180013d31  call    ?UtilGetPlatformVersion@@YAJPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; UtilGetPlatformVersion(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x180013d36  test    eax, eax
0x180013d38  js      short loc_180013D5F
0x180013d3a  mov     rax, [rsp+250h+var_1F0]
0x180013d3f  mov     [rsp+250h+pdwReturnedProductType], rax
0x180013d44  mov     r9d, [rbp+150h+VersionInformation.dwMinorVersion]
0x180013d48  mov     r8d, [rbp+150h+VersionInformation.dwMajorVersion]
0x180013d4c  lea     rdx, aDDLs; "%d.%d.%ls"
0x180013d53  mov     rcx, rsi
  ... truncated ...
```
