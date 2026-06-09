# SsCheckRegistry

- ea: `0x180001764`
- end: `0x180001cb0`
- name: `SsCheckRegistry`
- size: `1356`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180015500`

## callees

- `0x180001764`
- `0x180002038`
- `0x18001deb0`
- `0x180020dc0`
- `0x180020de8`
- `0x180025e94`
- `0x18002ebf8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180001a82`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180001a82`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180001a42`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180001a42`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180001a95`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180001a95`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180001a2d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180001a2d`
- `ntdll!RtlCheckRegistryKey` at `0x18000179f`
- `ntdll!RtlCheckRegistryKey` at `0x180001803`
- `ntdll!RtlCheckRegistryKey` at `0x18000187c`
- `ntdll!RtlCheckRegistryKey` at `0x18000190d`
- `ntdll!RtlCheckRegistryKey` at `0x180001995`
- `ntdll!RtlCheckRegistryKey` at `0x180001ab9`
- `ntdll!RtlCheckRegistryKey` at `0x180001b29`
- `ntdll!RtlCheckRegistryKey` at `0x180001ba3`
- `ntdll!RtlCheckRegistryKey` at `0x180001c1d`
- `ntdll!RtlCheckRegistryKey` at `0x18000179f`
- `ntdll!RtlCheckRegistryKey` at `0x180001803`
- `ntdll!RtlCheckRegistryKey` at `0x18000187c`
- `ntdll!RtlCheckRegistryKey` at `0x18000190d`
- `ntdll!RtlCheckRegistryKey` at `0x180001995`
- `ntdll!RtlCheckRegistryKey` at `0x180001ab9`
- `ntdll!RtlCheckRegistryKey` at `0x180001b29`
- `ntdll!RtlCheckRegistryKey` at `0x180001ba3`
- `ntdll!RtlCheckRegistryKey` at `0x180001c1d`
- `ntdll!RtlCreateRegistryKey` at `0x18000188c`
- `ntdll!RtlCreateRegistryKey` at `0x18000192f`
- `ntdll!RtlCreateRegistryKey` at `0x1800019a5`
- `ntdll!RtlCreateRegistryKey` at `0x180001ac9`
- `ntdll!RtlCreateRegistryKey` at `0x180001b3c`
- `ntdll!RtlCreateRegistryKey` at `0x180001bb6`
- `ntdll!RtlCreateRegistryKey` at `0x180001c30`
- `ntdll!RtlCreateRegistryKey` at `0x18000188c`
- `ntdll!RtlCreateRegistryKey` at `0x18000192f`
- `ntdll!RtlCreateRegistryKey` at `0x1800019a5`
- `ntdll!RtlCreateRegistryKey` at `0x180001ac9`
- `ntdll!RtlCreateRegistryKey` at `0x180001b3c`
- `ntdll!RtlCreateRegistryKey` at `0x180001bb6`
- `ntdll!RtlCreateRegistryKey` at `0x180001c30`
- `ntdll!RtlNtStatusToDosError` at `0x1800017af`
- `ntdll!RtlNtStatusToDosError` at `0x180001813`
- `ntdll!RtlNtStatusToDosError` at `0x18000189e`
- `ntdll!RtlNtStatusToDosError` at `0x1800018f5`
- `ntdll!RtlNtStatusToDosError` at `0x180001941`
- `ntdll!RtlNtStatusToDosError` at `0x1800019b7`
- `ntdll!RtlNtStatusToDosError` at `0x180001adb`
- `ntdll!RtlNtStatusToDosError` at `0x180001b55`
- `ntdll!RtlNtStatusToDosError` at `0x180001bcf`
- `ntdll!RtlNtStatusToDosError` at `0x180001c49`
- `ntdll!RtlNtStatusToDosError` at `0x1800017af`
- `ntdll!RtlNtStatusToDosError` at `0x180001813`
- `ntdll!RtlNtStatusToDosError` at `0x18000189e`
- `ntdll!RtlNtStatusToDosError` at `0x1800018f5`
- `ntdll!RtlNtStatusToDosError` at `0x180001941`
- `ntdll!RtlNtStatusToDosError` at `0x1800019b7`
- `ntdll!RtlNtStatusToDosError` at `0x180001adb`
- `ntdll!RtlNtStatusToDosError` at `0x180001b55`
- `ntdll!RtlNtStatusToDosError` at `0x180001bcf`
- `ntdll!RtlNtStatusToDosError` at `0x180001c49`
- `RPCRT4!UuidCreate` at `0x180001a4c`
- `RPCRT4!UuidCreate` at `0x180001a4c`

## string_xrefs

- `0x1800017f6`: `LanmanServer\Linkage`
- `0x180001a1b`: `SYSTEM\CurrentControlSet\Services\LanmanServer\Parameters`
- `0x180001988`: `LanmanServer\DefaultSecurity`
- `0x180001bc2`: `Shares\Security`

## pseudocode

```c
ULONG SsCheckRegistry()
{
  int v0; // eax
  _QWORD *v1; // rcx
  __int64 v2; // rdx
  int v3; // eax
  int RegistryKey; // eax
  int v6; // edi
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  int v9; // eax
  unsigned int v10; // edi
  int v11; // eax
  unsigned int v12; // edi
  RPC_STATUS v13; // eax
  UUID v14; // xmm0
  int v15; // eax
  LPCWSTR Strings; // [rsp+30h] [rbp-30h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-28h] BYREF
  UUID Uuid; // [rsp+40h] [rbp-20h] BYREF

  Strings = 0;
  v0 = RtlCheckRegistryKey(1u, (PWSTR)L"LanmanServer");
  if ( v0 < 0 )
  {
    Strings = L"LanmanServer";
    RtlNtStatusToDosError(v0);
    SsLogEvent(0xC00009C5, 1u, &Strings);
    v1 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      return 87;
    }
    v2 = 34;
LABEL_11:
    WPP_SF_(v1[2], v2, WPP_6c51fa01af1134468f88fcdefbc326dc_Traceguids);
    return 87;
  }
  v3 = RtlCheckRegistryKey(1u, (PWSTR)L"LanmanServer\\Linkage");
  if ( v3 < 0 )
  {
    Strings = L"LanmanServer\\Linkage";
    RtlNtStatusToDosError(v3);
    SsLogEvent(0xC00009C5, 1u, &Strings);
    v1 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      return 87;
    }
    v2 = 35;
    goto LABEL_11;
  }
  if ( RtlCheckRegistryKey(1u, (PWSTR)L"LanmanServer\\Parameters") < 0 )
  {
    RegistryKey = RtlCreateRegistryKey(1u, (PWSTR)L"LanmanServer\\Parameters");
    v6 = RegistryKey;
    if ( RegistryKey < 0 )
    {
      Strings = L"LanmanServer\\Parameters";
      RtlNtStatusToDosError(RegistryKey);
      SsLogEvent(0xC00009C6, 1u, &Strings);
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0
        || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        return RtlNtStatusToDosError(v6);
      }
      v8 = 36;
LABEL_19:
      WPP_SF_d(v7[2], v8, WPP_6c51fa01af1134468f88fcdefbc326dc_Traceguids, (unsigned int)v6);
      return RtlNtStatusToDosError(v6);
    }
  }
  if ( RtlCheckRegistryKey(1u, (PWSTR)L"LanmanServer\\ShareProviders") < 0 )
  {
    v9 = RtlCreateRegistryKey(1u, (PWSTR)L"LanmanServer\\ShareProviders");
    v10 = v9;
    if ( v9 < 0 )
    {
      Strings = L"LanmanServer\\ShareProviders";
      RtlNtStatusToDosError(v9);
      SsLogEvent(0xC00009C6, 1u, &Strings);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, WPP_6c51fa01af1134468f88fcdefbc326dc_Traceguids, v10);
      }
    }
  }
  if ( RtlCheckRegistryKey(1u, (PWSTR)L"LanmanServer\\DefaultSecurity") < 0 )
  {
    v11 = RtlCreateRegistryKey(1u, (PWSTR)L"LanmanServer\\DefaultSecurity");
    v12 = v11;
    if ( v11 < 0 )
    {
      Strings = L"LanmanServer\\DefaultSecurity";
      RtlNtStatusToDosError(v11);
      SsLogEvent(0xC00009C6, 1u, &Strings);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, WPP_6c51fa01af1134468f88fcdefbc326dc_Traceguids, v12);
      }
    }
  }
  hKey = 0;
  Uuid = 0;
  if ( RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SYSTEM\\CurrentControlSet\\Services\\LanmanServer\\Parameters",
         0,
         0xF003Fu,
         &hKey) )
  {
    v14 = 0;
  }
  else
  {
    RegDeleteValueW(hKey, L"Guid");
    v13 = UuidCreate(&Uuid);
    if ( !v13 || v13 == 1824 )
      RegSetValueExW(hKey, L"Guid", 0, 3u, (const BYTE *)&Uuid, 0x10u);
    SsNotifyRdrOfGuid(&Uuid);
    RegCloseKey(hKey);
    v14 = Uuid;
  }
  xmmword_18005CD78 = (__int128)v14;
  if ( RtlCheckRegistryKey(1u, (PWSTR)L"LanmanServer\\AutotunedParameters") < 0 )
  {
    v15 = RtlCreateRegistryKey(1u, (PWSTR)L"LanmanServer\\AutotunedParameters");
    v6 = v15;
    if ( v15 < 0 )
    {
      Strings = L"LanmanServer\\AutotunedParameters";
      RtlNtStatusToDosError(v15);
      SsLogEvent(0xC00009C6, 1u, &Strings);
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0
        || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        return RtlNtStatusToDosError(v6);
      }
      v8 = 39;
      goto LABEL_19;
    }
  }
  if ( RtlCheckRegistryKey(0, &word_18005DDBC) < 0 )
  {
    v6 = RtlCreateRegistryKey(0, &word_18005DDBC);
    if ( v6 < 0 )
    {
      Strings = L"Shares";
      RtlNtStatusToDosError(v6);
      SsLogEvent(0xC00009C6, 1u, &Strings);
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0
        || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        return RtlNtStatusToDosError(v6);
      }
      v8 = 40;
      goto LABEL_19;
    }
  }
  if ( RtlCheckRegistryKey(0, &word_18005DFC4) < 0 )
  {
    v6 = RtlCreateRegistryKey(0, &word_18005DFC4);
    if ( v6 < 0 )
    {
      Strings = L"Shares\\Security";
      RtlNtStatusToDosError(v6);
      SsLogEvent(0xC00009C6, 1u, &Strings);
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0
        || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        return RtlNtStatusToDosError(v6);
      }
      v8 = 41;
      goto LABEL_19;
    }
  }
  if ( RtlCheckRegistryKey(0, &word_18005E1CC) < 0 )
  {
    v6 = RtlCreateRegistryKey(0, &word_18005E1CC);
    if ( v6 < 0 )
    {
      Strings = L"Certs";
      RtlNtStatusToDosError(v6);
      SsLogEvent(0xC00009C6, 1u, &Strings);
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0
        || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        return RtlNtStatusToDosError(v6);
      }
      v8 = 42;
      goto LABEL_19;
    }
  }
  SsRefreshParameters();
  return 0;
}

```

## disassembly

```asm
0x180001764  push    rbp
0x180001766  push    rbx
0x180001767  push    rsi
0x180001768  push    rdi
0x180001769  push    r12
0x18000176b  push    r14
0x18000176d  push    r15
0x18000176f  mov     rbp, rsp
0x180001772  sub     rsp, 60h
0x180001776  mov     rax, cs:__security_cookie
0x18000177d  xor     rax, rsp
0x180001780  mov     [rbp+var_10], rax
0x180001784  lea     rbx, Path; "LanmanServer"
0x18000178b  mov     [rbp+Strings], 0
0x180001793  mov     r15d, 1
0x180001799  mov     rdx, rbx; Path
0x18000179c  mov     ecx, r15d; RelativeTo
0x18000179f  call    cs:__imp_RtlCheckRegistryKey
0x1800017a5  test    eax, eax
0x1800017a7  jns     short loc_1800017F6
0x1800017a9  mov     ecx, eax; Status
0x1800017ab  mov     [rbp+Strings], rbx
0x1800017af  call    cs:__imp_RtlNtStatusToDosError
0x1800017b5  lea     r8, [rbp+Strings]; lpStrings
0x1800017b9  mov     edx, r15d; wNumStrings
0x1800017bc  mov     r9d, eax
0x1800017bf  mov     ecx, 0C00009C5h; dwEventID
0x1800017c4  call    SsLogEvent
0x1800017c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800017d0  lea     rsi, WPP_GLOBAL_Control
0x1800017d7  cmp     rcx, rsi
0x1800017da  jz      loc_180001865
0x1800017e0  mov     ebx, 100h
0x1800017e5  test    [rcx+1Ch], ebx
0x1800017e8  jz      short loc_180001865
0x1800017ea  cmp     [rcx+19h], r15b
0x1800017ee  jb      short loc_180001865
0x1800017f0  lea     edx, [r15+21h]
0x1800017f4  jmp     short loc_180001855
0x1800017f6  lea     rbx, aLanmanserverLi; "LanmanServer\\Linkage"
0x1800017fd  mov     ecx, r15d; RelativeTo
0x180001800  mov     rdx, rbx; Path
0x180001803  call    cs:__imp_RtlCheckRegistryKey
0x180001809  test    eax, eax
0x18000180b  jns     short loc_18000186F
0x18000180d  mov     ecx, eax; Status
0x18000180f  mov     [rbp+Strings], rbx
0x180001813  call    cs:__imp_RtlNtStatusToDosError
0x180001819  lea     r8, [rbp+Strings]; lpStrings
0x18000181d  mov     edx, r15d; wNumStrings
0x180001820  mov     r9d, eax
0x180001823  mov     ecx, 0C00009C5h; dwEventID
0x180001828  call    SsLogEvent
0x18000182d  mov     rcx, cs:WPP_GLOBAL_Control
0x180001834  lea     rsi, WPP_GLOBAL_Control
0x18000183b  cmp     rcx, rsi
0x18000183e  jz      short loc_180001865
0x180001840  mov     ebx, 100h
0x180001845  test    [rcx+1Ch], ebx
0x180001848  jz      short loc_180001865
0x18000184a  cmp     [rcx+19h], r15b
0x18000184e  jb      short loc_180001865
0x180001850  mov     edx, 23h ; '#'
0x180001855  mov     rcx, [rcx+10h]
0x180001859  lea     r8, WPP_6c51fa01af1134468f88fcdefbc326dc_Traceguids
0x180001860  call    WPP_SF_
0x180001865  mov     eax, 57h ; 'W'
0x18000186a  jmp     loc_180001C95
0x18000186f  lea     rbx, aLanmanserverPa; "LanmanServer\\Parameters"
0x180001876  mov     ecx, r15d; RelativeTo
0x180001879  mov     rdx, rbx; Path
0x18000187c  call    cs:__imp_RtlCheckRegistryKey
0x180001882  test    eax, eax
0x180001884  jns     short loc_180001900
0x180001886  mov     rdx, rbx; Path
0x180001889  mov     ecx, r15d; RelativeTo
0x18000188c  call    cs:__imp_RtlCreateRegistryKey
0x180001892  mov     edi, eax
0x180001894  test    eax, eax
0x180001896  jns     short loc_180001900
0x180001898  mov     ecx, eax; Status
0x18000189a  mov     [rbp+Strings], rbx
0x18000189e  call    cs:__imp_RtlNtStatusToDosError
0x1800018a4  lea     r8, [rbp+Strings]; lpStrings
0x1800018a8  mov     edx, r15d; wNumStrings
0x1800018ab  mov     r9d, eax
0x1800018ae  mov     ecx, 0C00009C6h; dwEventID
0x1800018b3  call    SsLogEvent
0x1800018b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800018bf  lea     rsi, WPP_GLOBAL_Control
0x1800018c6  cmp     rcx, rsi
0x1800018c9  jz      short loc_1800018F3
0x1800018cb  mov     ebx, 100h
0x1800018d0  test    [rcx+1Ch], ebx
0x1800018d3  jz      short loc_1800018F3
0x1800018d5  cmp     [rcx+19h], r15b
0x1800018d9  jb      short loc_1800018F3
0x1800018db  mov     edx, 24h ; '$'
0x1800018e0  mov     rcx, [rcx+10h]
0x1800018e4  lea     r8, WPP_6c51fa01af1134468f88fcdefbc326dc_Traceguids
0x1800018eb  mov     r9d, edi
0x1800018ee  call    WPP_SF_d
0x1800018f3  mov     ecx, edi; Status
0x1800018f5  call    cs:__imp_RtlNtStatusToDosError
0x1800018fb  jmp     loc_180001C95
0x180001900  lea     r12, aLanmanserverSh; "LanmanServer\\ShareProviders"
0x180001907  mov     ecx, r15d; RelativeTo
0x18000190a  mov     rdx, r12; Path
0x18000190d  call    cs:__imp_RtlCheckRegistryKey
0x180001913  mov     ebx, 100h
0x180001918  lea     rsi, WPP_GLOBAL_Control
0x18000191f  mov     r14d, 0C00009C6h
0x180001925  test    eax, eax
0x180001927  jns     short loc_180001988
0x180001929  mov     rdx, r12; Path
0x18000192c  mov     ecx, r15d; RelativeTo
0x18000192f  call    cs:__imp_RtlCreateRegistryKey
0x180001935  mov     edi, eax
0x180001937  test    eax, eax
0x180001939  jns     short loc_180001988
0x18000193b  mov     ecx, eax; Status
0x18000193d  mov     [rbp+Strings], r12
0x180001941  call    cs:__imp_RtlNtStatusToDosError
0x180001947  lea     r8, [rbp+Strings]; lpStrings
0x18000194b  mov     edx, r15d; wNumStrings
0x18000194e  mov     r9d, eax
0x180001951  mov     ecx, r14d; dwEventID
0x180001954  call    SsLogEvent
0x180001959  mov     rcx, cs:WPP_GLOBAL_Control
0x180001960  cmp     rcx, rsi
0x180001963  jz      short loc_180001988
0x180001965  test    [rcx+1Ch], ebx
0x180001968  jz      short loc_180001988
0x18000196a  cmp     [rcx+19h], r15b
0x18000196e  jb      short loc_180001988
0x180001970  mov     rcx, [rcx+10h]
0x180001974  lea     r8, WPP_6c51fa01af1134468f88fcdefbc326dc_Traceguids
0x18000197b  mov     edx, 25h ; '%'
0x180001980  mov     r9d, edi
0x180001983  call    WPP_SF_d
0x180001988  lea     r12, aLanmanserverDe; "LanmanServer\\DefaultSecurity"
0x18000198f  mov     ecx, r15d; RelativeTo
0x180001992  mov     rdx, r12; Path
0x180001995  call    cs:__imp_RtlCheckRegistryKey
0x18000199b  test    eax, eax
0x18000199d  jns     short loc_1800019FE
0x18000199f  mov     rdx, r12; Path
0x1800019a2  mov     ecx, r15d; RelativeTo
0x1800019a5  call    cs:__imp_RtlCreateRegistryKey
0x1800019ab  mov     edi, eax
0x1800019ad  test    eax, eax
0x1800019af  jns     short loc_1800019FE
0x1800019b1  mov     ecx, eax; Status
0x1800019b3  mov     [rbp+Strings], r12
0x1800019b7  call    cs:__imp_RtlNtStatusToDosError
0x1800019bd  lea     r8, [rbp+Strings]; lpStrings
0x1800019c1  mov     edx, r15d; wNumStrings
0x1800019c4  mov     r9d, eax
0x1800019c7  mov     ecx, r14d; dwEventID
0x1800019ca  call    SsLogEvent
0x1800019cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800019d6  cmp     rcx, rsi
0x1800019d9  jz      short loc_1800019FE
0x1800019db  test    [rcx+1Ch], ebx
0x1800019de  jz      short loc_1800019FE
0x1800019e0  cmp     [rcx+19h], r15b
0x1800019e4  jb      short loc_1800019FE
0x1800019e6  mov     rcx, [rcx+10h]
0x1800019ea  lea     r8, WPP_6c51fa01af1134468f88fcdefbc326dc_Traceguids
0x1800019f1  mov     edx, 26h ; '&'
0x1800019f6  mov     r9d, edi
0x1800019f9  call    WPP_SF_d
0x1800019fe  xorps   xmm0, xmm0
0x180001a01  mov     [rbp+hKey], 0
0x180001a09  lea     rax, [rbp+hKey]
0x180001a0d  mov     r9d, 0F003Fh; samDesired
0x180001a13  xor     r8d, r8d; ulOptions
0x180001a16  mov     [rsp+60h+phkResult], rax; phkResult
0x180001a1b  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Services\\La"...
0x180001a22  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180001a29  movups  xmmword ptr [rbp+Uuid.Data1], xmm0
0x180001a2d  call    cs:__imp_RegOpenKeyExW
0x180001a33  test    eax, eax
0x180001a35  jnz     short loc_180001AA1
0x180001a37  mov     rcx, [rbp+hKey]; hKey
0x180001a3b  lea     rdx, ValueName; "Guid"
0x180001a42  call    cs:__imp_RegDeleteValueW
0x180001a48  lea     rcx, [rbp+Uuid]; Uuid
0x180001a4c  call    cs:__imp_UuidCreate
0x180001a52  test    eax, eax
0x180001a54  jz      short loc_180001A5D
0x180001a56  cmp     eax, 720h
0x180001a5b  jnz     short loc_180001A88
0x180001a5d  mov     rcx, [rbp+hKey]; hKey
0x180001a61  lea     rax, [rbp+Uuid]
0x180001a65  mov     [rsp+60h+cbData], 10h; cbData
0x180001a6d  lea     rdx, ValueName; "Guid"
0x180001a74  mov     r9d, 3; dwType
0x180001a7a  mov     [rsp+60h+phkResult], rax; lpData
0x180001a7f  xor     r8d, r8d; Reserved
0x180001a82  call    cs:__imp_RegSetValueExW
0x180001a88  lea     rcx, [rbp+Uuid]; InputBuffer
0x180001a8c  call    SsNotifyRdrOfGuid
0x180001a91  mov     rcx, [rbp+hKey]; hKey
0x180001a95  call    cs:__imp_RegCloseKey
0x180001a9b  movups  xmm0, xmmword ptr [rbp+Uuid.Data1]
0x180001a9f  jmp     short loc_180001AA4
0x180001aa1  xorps   xmm0, xmm0
0x180001aa4  lea     r12, aLanmanserverAu; "LanmanServer\\AutotunedParameters"
0x180001aab  mov     ecx, r15d; RelativeTo
0x180001aae  mov     rdx, r12; Path
0x180001ab1  movdqu  cs:xmmword_18005CD78, xmm0
0x180001ab9  call    cs:__imp_RtlCheckRegistryKey
0x180001abf  test    eax, eax
0x180001ac1  jns     short loc_180001B20
0x180001ac3  mov     rdx, r12; Path
0x180001ac6  mov     ecx, r15d; RelativeTo
0x180001ac9  call    cs:__imp_RtlCreateRegistryKey
0x180001acf  mov     edi, eax
0x180001ad1  test    eax, eax
0x180001ad3  jns     short loc_180001B20
0x180001ad5  mov     ecx, eax; Status
0x180001ad7  mov     [rbp+Strings], r12
0x180001adb  call    cs:__imp_RtlNtStatusToDosError
0x180001ae1  lea     r8, [rbp+Strings]; lpStrings
0x180001ae5  mov     edx, r15d; wNumStrings
0x180001ae8  mov     r9d, eax
0x180001aeb  mov     ecx, r14d; dwEventID
0x180001aee  call    SsLogEvent
0x180001af3  mov     rcx, cs:WPP_GLOBAL_Control
0x180001afa  cmp     rcx, rsi
0x180001afd  jz      loc_1800018F3
0x180001b03  test    [rcx+1Ch], ebx
0x180001b06  jz      loc_1800018F3
0x180001b0c  cmp     [rcx+19h], r15b
0x180001b10  jb      loc_1800018F3
0x180001b16  mov     edx, 27h ; '''
0x180001b1b  jmp     loc_1800018E0
0x180001b20  lea     rdx, word_18005DDBC; Path
0x180001b27  xor     ecx, ecx; RelativeTo
0x180001b29  call    cs:__imp_RtlCheckRegistryKey
0x180001b2f  test    eax, eax
0x180001b31  jns     short loc_180001B9A
0x180001b33  lea     rdx, word_18005DDBC; Path
0x180001b3a  xor     ecx, ecx; RelativeTo
0x180001b3c  call    cs:__imp_RtlCreateRegistryKey
0x180001b42  mov     edi, eax
0x180001b44  test    eax, eax
0x180001b46  jns     short loc_180001B9A
0x180001b48  lea     rax, aShares; "Shares"
0x180001b4f  mov     ecx, edi; Status
0x180001b51  mov     [rbp+Strings], rax
0x180001b55  call    cs:__imp_RtlNtStatusToDosError
0x180001b5b  lea     r8, [rbp+Strings]; lpStrings
0x180001b5f  mov     edx, r15d; wNumStrings
0x180001b62  mov     r9d, eax
0x180001b65  mov     ecx, r14d; dwEventID
0x180001b68  call    SsLogEvent
0x180001b6d  mov     rcx, cs:WPP_GLOBAL_Control
0x180001b74  cmp     rcx, rsi
0x180001b77  jz      loc_1800018F3
0x180001b7d  test    [rcx+1Ch], ebx
0x180001b80  jz      loc_1800018F3
0x180001b86  cmp     [rcx+19h], r15b
0x180001b8a  jb      loc_1800018F3
0x180001b90  mov     edx, 28h ; '('
0x180001b95  jmp     loc_1800018E0
0x180001b9a  lea     rdx, word_18005DFC4; Path
0x180001ba1  xor     ecx, ecx; RelativeTo
0x180001ba3  call    cs:__imp_RtlCheckRegistryKey
0x180001ba9  test    eax, eax
0x180001bab  jns     short loc_180001C14
0x180001bad  lea     rdx, word_18005DFC4; Path
0x180001bb4  xor     ecx, ecx; RelativeTo
0x180001bb6  call    cs:__imp_RtlCreateRegistryKey
0x180001bbc  mov     edi, eax
0x180001bbe  test    eax, eax
0x180001bc0  jns     short loc_180001C14
0x180001bc2  lea     rax, aSharesSecurity; "Shares\\Security"
0x180001bc9  mov     ecx, edi; Status
0x180001bcb  mov     [rbp+Strings], rax
0x180001bcf  call    cs:__imp_RtlNtStatusToDosError
0x180001bd5  lea     r8, [rbp+Strings]; lpStrings
0x180001bd9  mov     edx, r15d; wNumStrings
0x180001bdc  mov     r9d, eax
0x180001bdf  mov     ecx, r14d; dwEventID
0x180001be2  call    SsLogEvent
0x180001be7  mov     rcx, cs:WPP_GLOBAL_Control
0x180001bee  cmp     rcx, rsi
0x180001bf1  jz      loc_1800018F3
0x180001bf7  test    [rcx+1Ch], ebx
0x180001bfa  jz      loc_1800018F3
0x180001c00  cmp     [rcx+19h], r15b
0x180001c04  jb      loc_1800018F3
0x180001c0a  mov     edx, 29h ; ')'
0x180001c0f  jmp     loc_1800018E0
0x180001c14  lea     rdx, word_18005E1CC; Path
0x180001c1b  xor     ecx, ecx; RelativeTo
0x180001c1d  call    cs:__imp_RtlCheckRegistryKey
0x180001c23  test    eax, eax
  ... truncated ...
```
