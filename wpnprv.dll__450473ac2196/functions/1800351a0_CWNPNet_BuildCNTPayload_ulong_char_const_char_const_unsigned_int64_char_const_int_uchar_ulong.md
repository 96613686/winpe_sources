# CWNPNet::BuildCNTPayload(ulong,char const *,char const *,unsigned __int64,char const *,int,uchar *,ulong)

- ea: `0x1800351a0`
- end: `0x180035b77`
- name: `?BuildCNTPayload@CWNPNet@@KAJKPEBD0_K0HPEAEK@Z`
- size: `2519`
- prototype: `__int64 __fastcall(unsigned int, const char *, const char *, unsigned __int64, const char *, int, char *)`
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18003c110`

## callees

- `0x180007440`
- `0x180008294`
- `0x18000fe0c`
- `0x18000fe2c`
- `0x18000fe54`
- `0x180013294`
- `0x180013308`
- `0x18001c06c`
- `0x18001c384`
- `0x18002dd40`
- `0x1800326b0`
- `0x1800351a0`
- `0x180037770`
- `0x180044698`
- `0x180044fe4`
- `0x180045028`
- `0x180045598`
- `0x180045a6c`
- `0x18008191c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__ui64toa_s` at `0x180035448`
- `api-ms-win-crt-private-l1-1-0!_o__ui64toa_s` at `0x180035448`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035594`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035594`
- `api-ms-win-core-localization-l1-2-0!GetUserGeoID` at `0x1800355c4`
- `api-ms-win-core-localization-l1-2-0!GetUserGeoID` at `0x1800355c4`
- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLocaleName` at `0x18003558c`
- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLocaleName` at `0x18003558c`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExA` at `0x1800354dc`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExA` at `0x1800354dc`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003553e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003553e`
- `api-ms-win-core-sysinfo-l1-2-0!GetNativeSystemInfo` at `0x180035474`
- `api-ms-win-core-sysinfo-l1-2-0!GetNativeSystemInfo` at `0x180035474`
- `api-ms-win-power-base-l1-1-0!CallNtPowerInformation` at `0x1800355e4`
- `api-ms-win-power-base-l1-1-0!CallNtPowerInformation` at `0x1800355e4`

## string_xrefs

- `0x1800356d0`: `%hs %hs\n\n<connect><ver>%d</ver><agent><os>Windows</os><osVer>%u.%u.%hu.%hu.%u.%u</osVer><proc>%hs</proc><lcid>%ls</lcid><geoId>%d</geoId><aoac>%d</aoac><deviceType>%d</deviceType><deviceName>%hs</deviceName><followRetry>%hs</followRetry>`
- `0x18003581e`: `</agent>`

## pseudocode

```c
// Hidden C++ exception states: #wind=22
__int64 __fastcall CWNPNet::BuildCNTPayload(
        unsigned int a1,
        const char *a2,
        const char *a3,
        unsigned __int64 a4,
        const char *a5,
        int a6,
        char *a7)
{
  PVOID v11; // rcx
  const char *v12; // r12
  unsigned int ValueW; // eax
  int UserDefaultLocaleName; // ebx
  DWORD LastError; // eax
  GEOID UserGeoID; // ebx
  NTSTATUS v17; // eax
  void *v18; // rdx
  unsigned int v19; // r8d
  unsigned int v20; // r9d
  __int64 v21; // rcx
  const char *v22; // r8
  int v23; // eax
  int SystemIdAsHexString; // eax
  __int64 v25; // rax
  int v26; // eax
  int v27; // eax
  int v28; // eax
  int v29; // eax
  int v30; // eax
  int v31; // eax
  int v32; // eax
  int v33; // eax
  int v34; // eax
  int v35; // eax
  int v36; // eax
  int v37; // eax
  int v38; // eax
  int v39; // eax
  const char *v40; // r9
  PVOID *v41; // rcx
  __int64 result; // rax
  int pdwType; // [rsp+20h] [rbp-388h]
  int pdwTypea; // [rsp+20h] [rbp-388h]
  int pdwTypeb; // [rsp+20h] [rbp-388h]
  int pdwTypec; // [rsp+20h] [rbp-388h]
  DWORD pcbData; // [rsp+A0h] [rbp-308h] BYREF
  int pvData; // [rsp+A4h] [rbp-304h] BYREF
  BOOL v49; // [rsp+A8h] [rbp-300h]
  char v50; // [rsp+ADh] [rbp-2FBh]
  char *v51[2]; // [rsp+B0h] [rbp-2F8h] BYREF
  __int64 v52; // [rsp+C0h] [rbp-2E8h]
  const char *v53; // [rsp+C8h] [rbp-2E0h]
  _SYSTEM_INFO SystemInfo; // [rsp+D0h] [rbp-2D8h] BYREF
  _BYTE v55[16]; // [rsp+100h] [rbp-2A8h] BYREF
  __int64 v56; // [rsp+110h] [rbp-298h]
  _OSVERSIONINFOA VersionInformation; // [rsp+120h] [rbp-288h] BYREF
  unsigned __int16 v58; // [rsp+1B4h] [rbp-1F4h]
  unsigned __int16 v59; // [rsp+1B6h] [rbp-1F2h]
  _BYTE OutputBuffer[80]; // [rsp+1C0h] [rbp-1E8h] BYREF
  char v61[8]; // [rsp+210h] [rbp-198h] BYREF
  char v62[8]; // [rsp+218h] [rbp-190h] BYREF
  char v63[8]; // [rsp+220h] [rbp-188h] BYREF
  char v64[16]; // [rsp+228h] [rbp-180h] BYREF
  char v65[16]; // [rsp+238h] [rbp-170h] BYREF
  char v66[16]; // [rsp+248h] [rbp-160h] BYREF
  char v67[16]; // [rsp+258h] [rbp-150h] BYREF
  char v68[16]; // [rsp+268h] [rbp-140h] BYREF
  char v69[8]; // [rsp+278h] [rbp-130h] BYREF
  char Buffer[16]; // [rsp+280h] [rbp-128h] BYREF
  char v71; // [rsp+290h] [rbp-118h]
  char v72[24]; // [rsp+298h] [rbp-110h] BYREF
  WCHAR LocaleName[88]; // [rsp+2B0h] [rbp-F8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+3A8h] [rbp+0h]

  v53 = a5;
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    pdwType = a4;
    WPP_SF_LI(*((_QWORD *)WPP_GLOBAL_Control + 2), 438, a3, a1);
  }
  try
  {
    if ( !a7 )
      MicrosoftTelemetryAssertTriggeredNoArgs(v11);
    v50 = 1;
    strcpy(v65, "<network>");
    strcpy(v67, "</network>");
    strcpy(v64, "<mobile>");
    strcpy(v66, "</mobile>");
    strcpy(v63, "<apn>");
    strcpy(v62, "</apn>");
    strcpy(v61, "<wifi>");
    strcpy(v69, "</wifi>");
    strcpy(v68, "</connect>");
    memset(&SystemInfo, 0, sizeof(SystemInfo));
    memset_0(&VersionInformation, 0, 0x9Cu);
    pvData = 0;
    pcbData = 4;
    memset_0(OutputBuffer, 0, 0x4Cu);
    memset_0(LocaleName, 0, 0xAAu);
    *(_OWORD *)Buffer = 0;
    v71 = 0;
    v49 = a2 && *a2 || a3 && *a3;
    *a7 = 0;
    if ( (unsigned int)(a6 - 2) > 1 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x130D,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\trans\\wnpnet.cpp",
        (const char *)0x8000FFFFLL,
        pdwType);
    if ( _ui64toa_s(a4, Buffer, 0x11u, 16) )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1310,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\trans\\wnpnet.cpp",
        (const char *)0x8000FFFFLL,
        pdwType);
    GetNativeSystemInfo(&SystemInfo);
    if ( LOBYTE(SystemInfo.dwOemId) )
    {
      if ( LOBYTE(SystemInfo.dwOemId) == 5 )
      {
        v12 = "ARM";
      }
      else if ( LOBYTE(SystemInfo.dwOemId) == 6 || LOBYTE(SystemInfo.dwOemId) == 9 )
      {
        v12 = "x64";
      }
      else
      {
        v12 = "Unknown";
      }
    }
    else
    {
      v12 = "x86";
    }
    VersionInformation.dwOSVersionInfoSize = 156;
    if ( !GetVersionExA(&VersionInformation) )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x132F,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\trans\\wnpnet.cpp",
        (const char *)0x80004005LL,
        pdwType);
    ValueW = RegGetValueW(
               HKEY_LOCAL_MACHINE,
               L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion",
               L"UBR",
               0x10u,
               0,
               &pvData,
               &pcbData);
    if ( ValueW
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 440, &WPP_4e47059d20e03c0ffeb37878b8bdc70f_Traceguids, ValueW);
    }
    UserDefaultLocaleName = GetUserDefaultLocaleName(LocaleName, 85);
    LastError = GetLastError();
    if ( !UserDefaultLocaleName )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x133A,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\trans\\wnpnet.cpp",
        (const char *)(LastError | 0x80040000),
        pdwTypea);
    UserGeoID = GetUserGeoID(0x10u);
    v17 = CallNtPowerInformation(SystemPowerCapabilities, 0, 0, OutputBuffer, 0x4Cu);
    if ( v17 < 0 )
      wil::details::in1diag3::_Throw_NtStatus(retaddr, v18, v19, (const char *)(unsigned int)v17, pdwTypeb);
    v20 = CWNPNet::EvaluateDeviceType();
    v21 = -1;
    v22 = v53;
    do
      ++v21;
    while ( v53[v21] );
    if ( !v21 )
      v22 = "Unknown";
    v23 = StringCchPrintfA(
            a7,
            0x400u,
            "%hs %hs\r\n"
            "\r\n"
            "<connect><ver>%d</ver><agent><os>Windows</os><osVer>%u.%u.%hu.%hu.%u.%u</osVer><proc>%hs</proc><lcid>%ls</lc"
            "id><geoId>%d</geoId><aoac>%d</aoac><deviceType>%d</deviceType><deviceName>%hs</deviceName><followRetry>%hs</followRetry>",
            "Context:",
            Buffer,
            a6,
            VersionInformation.dwMajorVersion,
            VersionInformation.dwMinorVersion,
            v58,
            v59,
            VersionInformation.dwBuildNumber,
            pvData,
            v12,
            LocaleName,
            UserGeoID,
            OutputBuffer[20] != 0,
            v20,
            v22,
            "true");
    if ( v23 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1362,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\trans\\wnpnet.cpp",
        (const char *)(unsigned int)v23,
        pdwTypec);
    if ( a6 == 3 )
    {
      std::string::string(v55);
      SystemIdAsHexString = GetSystemIdAsHexString(v55);
      if ( SystemIdAsHexString < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1368,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\trans\\wnpnet.cpp",
          (const char *)(unsigned int)SystemIdAsHexString,
          pdwTypec);
      strcpy(v72, "<clientId>%s</clientId>");
      *(_OWORD *)v51 = 0;
      v52 = 0;
      std::vector<char>::_Construct_n<>(v51, v56 + 24);
      v25 = std::_String_val<std::_Simple_types<char>>::_Myptr(v55);
      v26 = StringCchPrintfA(v51[0], v51[1] - v51[0], v72, v25);
      if ( v26 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x136C,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\trans\\wnpnet.cpp",
          (const char *)(unsigned int)v26,
          pdwTypec);
      StringCchCatA(a7, 0x400u, v51[0]);
      std::vector<char>::_Tidy(v51);
      std::string::_Tidy_deallocate(v55);
    }
    StringCchCatA(a7, 0x400u, "</agent>");
    if ( a1 - 1026 <= 1 )
    {
      v27 = StringCchCatA(a7, 0x400u, v65);
      if ( v27 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1375,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\trans\\wnpnet.cpp",
          (const char *)(unsigned int)v27,
          pdwTypec);
      if ( a1 == 1027 )
      {
        v28 = StringCchCatA(a7, 0x400u, v64);
        if ( v28 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x137A,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\trans\\wnpnet.cpp",
            (const char *)(unsigned int)v28,
            pdwTypec);
      }
      else if ( a1 == 1026 )
      {
        v29 = StringCchCatA(a7, 0x400u, v61);
        if ( v29 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x137E,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\trans\\wnpnet.cpp",
            (const char *)(unsigned int)v29,
            pdwTypec);
      }
      if ( v49 )
      {
        v30 = StringCchCatA(a7, 0x400u, v63);
        if ( v30 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x1383,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\trans\\wnpnet.cpp",
            (const char *)(unsigned int)v30,
            pdwTypec);
        v31 = 0;
        if ( a2 && *a2 )
        {
          v32 = StringCchCatA(a7, 0x400u, a2);
          if ( v32 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x1387,
              (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\trans\\wnpnet.cpp",
              (const char *)(unsigned int)v32,
              pdwTypec);
          v31 = 1;
        }
        if ( a3 && *a3 )
        {
          if ( v31 )
          {
            v33 = StringCchCatA(a7, 0x400u, "!");
            if ( v33 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x138F,
                (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\trans\\wnpnet.cpp",
                (const char *)(unsigned int)v33,
                pdwTypec);
          }
          v34 = StringCchCatA(a7, 0x400u, a3);
          if ( v34 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x1392,
              (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\trans\\wnpnet.cpp",
              (const char *)(unsigned int)v34,
              pdwTypec);
        }
        v35 = StringCchCatA(a7, 0x400u, v62);
        if ( v35 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x1395,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\trans\\wnpnet.cpp",
            (const char *)(unsigned int)v35,
            pdwTypec);
      }
      if ( a1 == 1027 )
      {
        v36 = StringCchCatA(a7, 0x400u, v66);
        if ( v36 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x139B,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\trans\\wnpnet.cpp",
            (const char *)(unsigned int)v36,
            pdwTypec);
      }
      else if ( a1 == 1026 )
      {
        v37 = StringCchCatA(a7, 0x400u, v69);
        if ( v37 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x139F,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\trans\\wnpnet.cpp",
            (const char *)(unsigned int)v37,
            pdwTypec);
      }
      v38 = StringCchCatA(a7, 0x400u, v67);
      if ( v38 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x13A2,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\trans\\wnpnet.cpp",
          (const char *)(unsigned int)v38,
          pdwTypec);
    }
    v39 = StringCchCatA(a7, 0x400u, v68);
    if ( v39 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x13A5,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\trans\\wnpnet.cpp",
        (const char *)(unsigned int)v39,
        pdwTypec);
    v41 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 441, &WPP_4e47059d20e03c0ffeb37878b8bdc70f_Traceguids, a7);
      v41 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v41 != &WPP_GLOBAL_Control && (*((_BYTE *)v41 + 28) & 4) != 0 && *((_BYTE *)v41 + 25) >= 6u )
      WPP_SF_(v41[2], 439, &WPP_4e47059d20e03c0ffeb37878b8bdc70f_Traceguids);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x13AE,
                           (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\trans\\wnpnet.cpp",
                           v40);
  }
  return result;
}

```

## disassembly

```asm
0x1800351a0  push    rbx
0x1800351a2  push    rsi
0x1800351a3  push    rdi
0x1800351a4  push    r12
0x1800351a6  push    r13
0x1800351a8  push    r14
0x1800351aa  push    r15
0x1800351ac  sub     rsp, 370h
0x1800351b3  mov     rax, cs:__security_cookie
0x1800351ba  xor     rax, rsp
0x1800351bd  mov     [rsp+3A8h+var_48], rax
0x1800351c5  mov     rbx, r9
0x1800351c8  mov     r15, r8
0x1800351cb  mov     r13, rdx
0x1800351ce  mov     esi, ecx
0x1800351d0  mov     rax, [rsp+3A8h+arg_20]
0x1800351d8  mov     [rsp+3A8h+var_2E0], rax
0x1800351e0  mov     rdi, [rsp+3A8h+arg_30]
0x1800351e8  lea     rax, WPP_GLOBAL_Control
0x1800351ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1800351f6  cmp     rcx, rax
0x1800351f9  jz      short loc_18003521D
0x1800351fb  test    byte ptr [rcx+1Ch], 4
0x1800351ff  jz      short loc_18003521D
0x180035201  cmp     byte ptr [rcx+19h], 6
0x180035205  jb      short loc_18003521D
0x180035207  mov     edx, 1B6h
0x18003520c  mov     [rsp+3A8h+pdwType], rbx; int
0x180035211  mov     r9d, esi
0x180035214  mov     rcx, [rcx+10h]
0x180035218  call    WPP_SF_LI
0x18003521d  xor     r12d, r12d
0x180035220  test    rdi, rdi
0x180035223  jnz     short loc_18003522A
0x180035225  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18003522a  mov     [rsp+3A8h+var_2FB], 1
0x180035232  movsd   xmm0, qword ptr cs:aNetwork; "<network>"
0x18003523a  movsd   qword ptr [rsp+3A8h+var_170], xmm0
0x180035243  movzx   eax, word ptr cs:aNetwork+8; ">"
0x18003524a  mov     word ptr [rsp+3A8h+var_170+8], ax
0x180035252  movsd   xmm0, qword ptr cs:aNetwork_0; "</network>"
0x18003525a  movsd   qword ptr [rsp+3A8h+var_150], xmm0
0x180035263  mov     eax, dword ptr cs:aNetwork_0+7; "rk>"
0x180035269  mov     dword ptr [rsp+3A8h+var_150+7], eax
0x180035270  movsd   xmm0, qword ptr cs:aMobile_0; "<mobile>"
0x180035278  movsd   qword ptr [rsp+3A8h+var_180], xmm0
0x180035281  mov     al, byte ptr cs:aMobile_0+8; ""
0x180035287  mov     [rsp+3A8h+var_180+8], al
0x18003528e  movsd   xmm0, qword ptr cs:aMobile; "</mobile>"
0x180035296  movsd   qword ptr [rsp+3A8h+var_160], xmm0
0x18003529f  movzx   eax, word ptr cs:aMobile+8; ">"
0x1800352a6  mov     word ptr [rsp+3A8h+var_160+8], ax
0x1800352ae  mov     eax, dword ptr cs:aApn_0; "<apn>"
0x1800352b4  mov     dword ptr [rsp+3A8h+var_188], eax
0x1800352bb  movzx   eax, word ptr cs:aApn_0+4; ">"
0x1800352c2  mov     word ptr [rsp+3A8h+var_188+4], ax
0x1800352ca  mov     eax, dword ptr cs:aApn; "</apn>"
0x1800352d0  mov     dword ptr [rsp+3A8h+var_190], eax
0x1800352d7  movzx   eax, word ptr cs:aApn+4; "n>"
0x1800352de  mov     word ptr [rsp+3A8h+var_190+4], ax
0x1800352e6  mov     al, byte ptr cs:aApn+6; ""
0x1800352ec  mov     [rsp+3A8h+var_190+6], al
0x1800352f3  mov     eax, dword ptr cs:aWifi; "<wifi>"
0x1800352f9  mov     dword ptr [rsp+3A8h+var_198], eax
0x180035300  movzx   eax, word ptr cs:aWifi+4; "i>"
0x180035307  mov     word ptr [rsp+3A8h+var_198+4], ax
0x18003530f  mov     al, byte ptr cs:aWifi+6; ""
0x180035315  mov     [rsp+3A8h+var_198+6], al
0x18003531c  mov     rax, 3E696669772F3Ch
0x180035326  mov     qword ptr [rsp+3A8h+var_130], rax
0x18003532e  movsd   xmm0, qword ptr cs:aConnect; "</connect>"
0x180035336  movsd   qword ptr [rsp+3A8h+var_140], xmm0
0x18003533f  mov     eax, dword ptr cs:aConnect+7; "ct>"
0x180035345  mov     dword ptr [rsp+3A8h+var_140+7], eax
0x18003534c  xorps   xmm0, xmm0
0x18003534f  movups  xmmword ptr [rsp+3A8h+SystemInfo], xmm0
0x180035357  movups  xmmword ptr [rsp+3A8h+SystemInfo.lpMaximumApplicationAddress], xmm0
0x18003535f  movups  xmmword ptr [rsp+3A8h+SystemInfo.dwNumberOfProcessors], xmm0
0x180035367  xor     edx, edx; Val
0x180035369  mov     r8d, 9Ch; Size
0x18003536f  lea     rcx, [rsp+3A8h+VersionInformation]; void *
0x180035377  call    memset_0
0x18003537c  mov     [rsp+3A8h+var_304], r12d
0x180035384  mov     [rsp+3A8h+var_308], 4
0x18003538f  xor     edx, edx; Val
0x180035391  lea     r8d, [rdx+4Ch]; Size
0x180035395  lea     rcx, [rsp+3A8h+OutputBuffer]; void *
0x18003539d  call    memset_0
0x1800353a2  xor     edx, edx; Val
0x1800353a4  mov     r8d, 0AAh; Size
0x1800353aa  lea     rcx, [rsp+3A8h+LocaleName]; void *
0x1800353b2  call    memset_0
0x1800353b7  xorps   xmm0, xmm0
0x1800353ba  xor     eax, eax
0x1800353bc  movups  xmmword ptr [rsp+3A8h+Buffer], xmm0
0x1800353c4  mov     [rsp+3A8h+var_118], al
0x1800353cb  test    r13, r13
0x1800353ce  jz      short loc_1800353D6
0x1800353d0  cmp     [r13+0], r12b
0x1800353d4  jnz     short loc_1800353E0
0x1800353d6  test    r15, r15
0x1800353d9  jz      short loc_1800353ED
0x1800353db  cmp     [r15], r12b
0x1800353de  jz      short loc_1800353ED
0x1800353e0  mov     [rsp+3A8h+var_300], 1
0x1800353eb  jmp     short loc_1800353F5
0x1800353ed  mov     [rsp+3A8h+var_300], r12d
0x1800353f5  mov     [rdi], r12b
0x1800353f8  mov     eax, [rsp+3A8h+arg_28]
0x1800353ff  add     eax, 0FFFFFFFEh
0x180035402  cmp     eax, 1
0x180035405  setnbe  al
0x180035408  mov     rcx, [rsp+3A8h]; this
0x180035410  test    al, al
0x180035412  jz      short loc_18003542B
0x180035414  mov     r9d, 8000FFFFh; char *
0x18003541a  lea     r8, aOnecoreuapBase_10; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180035421  mov     edx, 130Dh; void *
0x180035426  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003542b  mov     r14, [rsp+3A8h]
0x180035433  mov     r9d, 10h; Radix
0x180035439  lea     r8d, [r9+1]; BufferCount
0x18003543d  lea     rdx, [rsp+3A8h+Buffer]; Buffer
0x180035445  mov     rcx, rbx; Value
0x180035448  call    cs:__imp__ui64toa_s
0x18003544e  test    eax, eax
0x180035450  jz      short loc_18003546C
0x180035452  mov     r9d, 8000FFFFh; char *
0x180035458  lea     r8, aOnecoreuapBase_10; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18003545f  mov     edx, 1310h; void *
0x180035464  mov     rcx, r14; this
0x180035467  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003546c  lea     rcx, [rsp+3A8h+SystemInfo]; lpSystemInfo
0x180035474  call    cs:__imp_GetNativeSystemInfo
0x18003547a  movzx   ecx, byte ptr [rsp+3A8h+SystemInfo]
0x180035482  test    ecx, ecx
0x180035484  jz      short loc_1800354B3
0x180035486  sub     ecx, 5
0x180035489  jz      short loc_1800354AA
0x18003548b  sub     ecx, 1
0x18003548e  jz      short loc_1800354A1
0x180035490  cmp     ecx, 3
0x180035493  jz      short loc_1800354A1
0x180035495  lea     r14, aUnknown; "Unknown"
0x18003549c  mov     r12, r14
0x18003549f  jmp     short loc_1800354C1
0x1800354a1  lea     r12, aX64; "x64"
0x1800354a8  jmp     short loc_1800354BA
0x1800354aa  lea     r12, aArm; "ARM"
0x1800354b1  jmp     short loc_1800354BA
0x1800354b3  lea     r12, aX86; "x86"
0x1800354ba  lea     r14, aUnknown; "Unknown"
0x1800354c1  mov     [rsp+3A8h+VersionInformation.dwOSVersionInfoSize], 9Ch
0x1800354cc  mov     rbx, [rsp+3A8h]
0x1800354d4  lea     rcx, [rsp+3A8h+VersionInformation]; lpVersionInformation
0x1800354dc  call    cs:__imp_GetVersionExA
0x1800354e2  test    eax, eax
0x1800354e4  jnz     short loc_180035500
0x1800354e6  mov     r9d, 80004005h; char *
0x1800354ec  lea     r8, aOnecoreuapBase_10; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800354f3  mov     edx, 132Fh; void *
0x1800354f8  mov     rcx, rbx; this
0x1800354fb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180035500  lea     rax, [rsp+3A8h+var_308]
0x180035508  mov     [rsp+3A8h+pcbData], rax; pcbData
0x18003550d  lea     rax, [rsp+3A8h+var_304]
0x180035515  mov     [rsp+3A8h+pvData], rax; pvData
0x18003551a  mov     [rsp+3A8h+pdwType], 0; int
0x180035523  mov     r9d, 10h; dwFlags
0x180035529  lea     r8, Value; "UBR"
0x180035530  lea     rdx, aSoftwareMicros_4; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180035537  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18003553e  call    cs:__imp_RegGetValueW
0x180035544  test    eax, eax
0x180035546  jz      short loc_18003557F
0x180035548  mov     rcx, cs:WPP_GLOBAL_Control
0x18003554f  lea     rdx, WPP_GLOBAL_Control
0x180035556  cmp     rcx, rdx
0x180035559  jz      short loc_18003557F
0x18003555b  test    byte ptr [rcx+1Ch], 4
0x18003555f  jz      short loc_18003557F
0x180035561  cmp     byte ptr [rcx+19h], 2
0x180035565  jb      short loc_18003557F
0x180035567  mov     edx, 1B8h
0x18003556c  mov     r9d, eax
0x18003556f  lea     r8, WPP_4e47059d20e03c0ffeb37878b8bdc70f_Traceguids
0x180035576  mov     rcx, [rcx+10h]
0x18003557a  call    WPP_SF_d
0x18003557f  mov     edx, 55h ; 'U'; cchLocaleName
0x180035584  lea     rcx, [rsp+3A8h+LocaleName]; lpLocaleName
0x18003558c  call    cs:__imp_GetUserDefaultLocaleName
0x180035592  mov     ebx, eax
0x180035594  call    cs:__imp_GetLastError
0x18003559a  mov     rcx, [rsp+3A8h]; this
0x1800355a2  test    ebx, ebx
0x1800355a4  jnz     short loc_1800355BF
0x1800355a6  or      eax, 80040000h
0x1800355ab  mov     r9d, eax; char *
0x1800355ae  lea     r8, aOnecoreuapBase_10; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800355b5  mov     edx, 133Ah; void *
0x1800355ba  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800355bf  mov     ecx, 10h; GeoClass
0x1800355c4  call    cs:__imp_GetUserGeoID
0x1800355ca  mov     ebx, eax
0x1800355cc  mov     dword ptr [rsp+3A8h+pdwType], 4Ch ; 'L'; int
0x1800355d4  lea     r9, [rsp+3A8h+OutputBuffer]; OutputBuffer
0x1800355dc  xor     r8d, r8d; InputBufferLength
0x1800355df  xor     edx, edx; InputBuffer
0x1800355e1  lea     ecx, [rdx+4]; InformationLevel
0x1800355e4  call    cs:__imp_CallNtPowerInformation
0x1800355ea  mov     rcx, [rsp+3A8h]; this
0x1800355f2  test    eax, eax
0x1800355f4  jns     short loc_1800355FE
0x1800355f6  mov     r9d, eax; char *
0x1800355f9  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x1800355fe  call    ?EvaluateDeviceType@CWNPNet@@KAKXZ; CWNPNet::EvaluateDeviceType(void)
0x180035603  mov     r9d, eax
0x180035606  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18003560a  mov     r8, [rsp+3A8h+var_2E0]
0x180035612  inc     rcx
0x180035615  cmp     byte ptr [r8+rcx], 0
0x18003561a  jnz     short loc_180035612
0x18003561c  test    rcx, rcx
0x18003561f  cmovz   r8, r14
0x180035623  xor     r14d, r14d
0x180035626  mov     eax, r14d
0x180035629  cmp     [rsp+3A8h+var_1D4], r14b
0x180035631  setnz   al
0x180035634  movzx   ecx, [rsp+3A8h+var_1F2]
0x18003563c  movzx   edx, [rsp+3A8h+var_1F4]
0x180035644  lea     r10, aTrue; "true"
0x18003564b  mov     [rsp+3A8h+var_318], r10
0x180035653  mov     [rsp+3A8h+var_320], r8
0x18003565b  mov     [rsp+3A8h+var_328], r9d
0x180035663  mov     [rsp+3A8h+var_330], eax
0x180035667  mov     [rsp+3A8h+var_338], ebx
0x18003566b  lea     rax, [rsp+3A8h+LocaleName]
0x180035673  mov     [rsp+3A8h+var_340], rax
0x180035678  mov     [rsp+3A8h+var_348], r12
0x18003567d  mov     eax, [rsp+3A8h+var_304]
0x180035684  mov     [rsp+3A8h+var_350], eax
0x180035688  mov     eax, [rsp+3A8h+VersionInformation.dwBuildNumber]
0x18003568f  mov     [rsp+3A8h+var_358], eax
0x180035693  mov     [rsp+3A8h+var_360], ecx
0x180035697  mov     [rsp+3A8h+var_368], edx
0x18003569b  mov     eax, [rsp+3A8h+VersionInformation.dwMinorVersion]
0x1800356a2  mov     [rsp+3A8h+var_370], eax
0x1800356a6  mov     eax, [rsp+3A8h+VersionInformation.dwMajorVersion]
0x1800356ad  mov     dword ptr [rsp+3A8h+pcbData], eax
0x1800356b1  mov     ebx, [rsp+3A8h+arg_28]
0x1800356b8  mov     dword ptr [rsp+3A8h+pvData], ebx
0x1800356bc  lea     rax, [rsp+3A8h+Buffer]
0x1800356c4  mov     [rsp+3A8h+pdwType], rax; int
0x1800356c9  lea     r9, aContext_0; "Context:"
0x1800356d0  lea     r8, aHsHsConnectVer; "%hs %hs\r\n\r\n<connect><ver>%d</ver><a"...
0x1800356d7  mov     r12d, 400h
0x1800356dd  mov     edx, r12d; unsigned __int64
0x1800356e0  mov     rcx, rdi; char *
0x1800356e3  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x1800356e8  mov     rcx, [rsp+3A8h]; this
0x1800356f0  test    eax, eax
0x1800356f2  jns     short loc_180035708
0x1800356f4  mov     r9d, eax; char *
0x1800356f7  lea     r8, aOnecoreuapBase_10; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800356fe  mov     edx, 1362h; void *
0x180035703  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180035708  cmp     ebx, 3
0x18003570b  jnz     loc_18003581E
0x180035711  lea     rcx, [rsp+3A8h+var_2A8]
0x180035719  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::string(void)
0x18003571e  nop
0x18003571f  lea     rcx, [rsp+3A8h+var_2A8]
0x180035727  call    ?GetSystemIdAsHexString@@YAJAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; GetSystemIdAsHexString(std::string &)
0x18003572c  mov     rcx, [rsp+3A8h]; this
0x180035734  test    eax, eax
0x180035736  jns     short loc_18003574C
0x180035738  mov     r9d, eax; char *
0x18003573b  lea     r8, aOnecoreuapBase_10; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180035742  mov     edx, 1368h; void *
0x180035747  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003574c  movups  xmm0, xmmword ptr cs:aClientidSClien; "<clientId>%s</clientId>"
0x180035753  movups  xmmword ptr [rsp+3A8h+var_110], xmm0
0x18003575b  movsd   xmm1, qword ptr cs:aClientidSClien+10h; "ientId>"
0x180035763  movsd   qword ptr [rsp+3A8h+var_110+10h], xmm1
0x18003576c  xorps   xmm0, xmm0
0x18003576f  movdqu  xmmword ptr [rsp+3A8h+var_2F8], xmm0
0x180035778  mov     [rsp+3A8h+var_2E8], r14
0x180035780  mov     rdx, [rsp+3A8h+var_298]
0x180035788  add     rdx, 18h
0x18003578c  lea     rcx, [rsp+3A8h+var_2F8]
0x180035794  call    ??$_Construct_n@$$V@?$vector@DV?$allocator@D@std@@@std@@AEAAX_K@Z; std::vector<char>::_Construct_n<>(unsigned __int64)
0x180035799  nop
0x18003579a  lea     rcx, [rsp+3A8h+var_2A8]
0x1800357a2  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x1800357a7  mov     r9, rax
0x1800357aa  mov     rdx, [rsp+3A8h+var_2F8+8]
0x1800357b2  sub     rdx, [rsp+3A8h+var_2F8]; unsigned __int64
0x1800357ba  lea     r8, [rsp+3A8h+var_110]; char *
0x1800357c2  mov     rcx, [rsp+3A8h+var_2F8]; char *
0x1800357ca  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
  ... truncated ...
```
