# ReadConfig(StateInfo *,ConfigInfo * *)

- ea: `0x180008930`
- end: `0x1800091fb`
- name: `?ReadConfig@@YAJPEAUStateInfo@@PEAPEAUConfigInfo@@@Z`
- size: `2251`
- prototype: `__int64 __fastcall(struct StateInfo *, struct ConfigInfo **)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180032ff0`
- `0x180039100`

## callees

- `0x18000709c`
- `0x1800073f0`
- `0x180008930`
- `0x180009204`
- `0x1800092a0`
- `0x180018138`
- `0x18001d9a0`
- `0x18003b940`
- `0x18004bd40`
- `0x18004f338`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000897a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000897a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800089cd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180008a7d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180008aa3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180008ac9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800089cd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180008a7d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180008aa3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180008ac9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008a00`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008a16`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008a2c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008a42`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008a00`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008a16`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008a2c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008a42`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180008dbd`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180008ea2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180008f31`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180008ff0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000913c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800091bb`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180008dbd`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180008ea2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180008f31`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180008ff0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000913c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800091bb`

## string_xrefs

- `0x180008af3`: `UpdateInterval`
- `0x180008a99`: `System\CurrentControlSet\Services\W32Time\Parameters`
- `0x180008a73`: `Software\Policies\Microsoft\W32Time\Config`
- `0x1800089c0`: `System\CurrentControlSet\Services\W32Time\Config`
- `0x180008e48`: `ReadConfig: '%s'=0x%08X (%d)\n`
- `0x180008f8d`: `ReadConfig: '%s'=0x%08X (%d)\n`
- `0x180009052`: `ReadConfig: '%s'=0x%08X (%d)\n`
- `0x1800090e2`: `ReadConfig: '%s'overridden to 0x%08X \n`

## pseudocode

```c
__int64 __fastcall ReadConfig(struct StateInfo *a1, struct TimeProvider ***a2)
{
  unsigned int v2; // r13d
  struct TimeProvider **v3; // rax
  struct TimeProvider **v4; // rdi
  signed int EnabledProviderList; // ebx
  LSTATUS v6; // eax
  HKEY v8; // rax
  unsigned int *pvData; // rbx
  const WCHAR *v10; // r15
  unsigned __int8 v11; // si
  unsigned int v12; // esi
  unsigned int *v13; // rax
  __int64 i; // rcx
  char *v15; // rax
  signed __int64 v16; // r9
  int v17; // edx
  int v18; // r8d
  _DWORD *v19; // rax
  LSTATUS ValueW; // eax
  HKEY v21; // r15
  unsigned int *v22; // rbx
  unsigned int *v23; // rsi
  unsigned __int8 v24; // r14
  int v25; // eax
  unsigned int *v26; // rbx
  HKEY v27; // r15
  unsigned __int8 v28; // r14
  int v29; // eax
  struct StateInfo *v30; // rcx
  int v31; // eax
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hkey; // [rsp+48h] [rbp-B8h] BYREF
  HKEY phkResult; // [rsp+50h] [rbp-B0h] BYREF
  HKEY v35; // [rsp+58h] [rbp-A8h] BYREF
  HKEY v36; // [rsp+60h] [rbp-A0h]
  unsigned int *v37; // [rsp+68h] [rbp-98h]
  _QWORD v38[4]; // [rsp+70h] [rbp-90h]
  LPCWSTR lpValue; // [rsp+90h] [rbp-70h]
  PVOID v40; // [rsp+98h] [rbp-68h]
  _QWORD v41[58]; // [rsp+A0h] [rbp-60h]
  DWORD pdwType; // [rsp+290h] [rbp+190h] BYREF
  DWORD pcbData; // [rsp+298h] [rbp+198h] BYREF

  v2 = 0;
  pdwType = 0;
  hkey = 0;
  hKey = 0;
  v35 = 0;
  phkResult = 0;
  v3 = (struct TimeProvider **)LocalAlloc(0x40u, 0xF8u);
  v4 = v3;
  if ( !v3 )
  {
    EnabledProviderList = -2147024882;
    goto LABEL_8;
  }
  EnabledProviderList = GetEnabledProviderList(v3, v3 + 1);
  if ( EnabledProviderList < 0 )
    goto LABEL_7;
  v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Services\\W32Time\\Config", 0, 0x20019u, &hKey);
  EnabledProviderList = v6;
  if ( v6 )
  {
    if ( v6 > 0 )
      EnabledProviderList = (unsigned __int16)v6 | 0x80070000;
LABEL_7:
    FreeConfigInfo((HLOCAL *)v4);
    goto LABEL_8;
  }
  RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Policies\\Microsoft\\W32Time\\Config", 0, 0x20019u, &hkey);
  RegOpenKeyExW(
    HKEY_LOCAL_MACHINE,
    L"System\\CurrentControlSet\\Services\\W32Time\\Parameters",
    0,
    0x20019u,
    &phkResult);
  RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Policies\\Microsoft\\W32Time\\Parameters", 0, 0x20019u, &v35);
  v40 = v4 + 9;
  lpValue = L"PhaseCorrectRate";
  v41[0] = (char *)v4 + 148;
  v41[1] = L"UpdateInterval";
  v41[2] = (char *)v4 + 76;
  v41[4] = L"FrequencyCorrectRate";
  v41[3] = v4 + 19;
  v41[5] = v4 + 10;
  v41[6] = (char *)v4 + 156;
  v41[7] = L"PollAdjustFactor";
  v41[8] = (char *)v4 + 84;
  v41[9] = v4 + 20;
  v41[10] = L"LargePhaseOffset";
  v41[11] = v4 + 11;
  v41[12] = (char *)v4 + 164;
  v41[13] = L"SpikeWatchPeriod";
  v41[14] = (char *)v4 + 92;
  v41[15] = v4 + 21;
  v41[16] = L"HoldPeriod";
  v41[17] = v4 + 12;
  v41[18] = (char *)v4 + 172;
  v41[19] = L"MinPollInterval";
  v41[20] = (char *)v4 + 100;
  v41[21] = v4 + 22;
  v41[22] = L"MaxPollInterval";
  v41[23] = v4 + 13;
  v41[24] = (char *)v4 + 180;
  v41[25] = L"ClockHoldoverPeriod";
  v41[26] = (char *)v4 + 108;
  v41[27] = v4 + 23;
  v38[0] = L"PhaseCorrectRate";
  v41[28] = L"AnnounceFlags";
  v41[29] = v4 + 27;
  v41[30] = v4 + 28;
  v41[31] = L"LocalClockDispersion";
  v41[32] = v4 + 14;
  v41[33] = (char *)v4 + 188;
  v41[34] = L"MaxNegPhaseCorrection";
  v41[35] = (char *)v4 + 116;
  v41[36] = v4 + 24;
  v41[37] = L"MaxPosPhaseCorrection";
  v41[38] = v4 + 15;
  v41[39] = (char *)v4 + 196;
  v41[40] = L"EventLogFlags";
  v41[41] = (char *)v4 + 220;
  v41[42] = (char *)v4 + 228;
  v41[43] = L"MaxAllowedPhaseOffset";
  v41[44] = (char *)v4 + 124;
  v41[45] = v4 + 25;
  v41[46] = L"UtilizeSslTimeData";
  v41[47] = v4 + 29;
  v41[48] = (char *)v4 + 236;
  v41[49] = L"ClockAdjustmentAuditLimit";
  v41[50] = (char *)v4 + 132;
  v41[51] = v4 + 26;
  v38[1] = L"UpdateInterval";
  v38[2] = L"FrequencyCorrectRate";
  while ( v2 < 0x12 )
  {
    v8 = hKey;
    pvData = (unsigned int *)v41[3 * v2 - 1];
    v10 = (&lpValue)[3 * v2];
    v37 = pvData;
    v36 = hKey;
    if ( hkey )
    {
      pcbData = 4;
      if ( !RegGetValueW(hkey, 0, v10, 0xFFFFu, &pdwType, pvData, &pcbData) )
      {
        v11 = 1;
LABEL_22:
        v12 = v11 + 2;
        goto LABEL_23;
      }
      v8 = v36;
    }
    pcbData = 4;
    v11 = 0;
    ValueW = RegGetValueW(v8, 0, v10, 0xFFFFu, &pdwType, pvData, &pcbData);
    EnabledProviderList = ValueW;
    if ( !ValueW )
      goto LABEL_22;
    if ( ValueW > 0 )
      EnabledProviderList = (unsigned __int16)ValueW | 0x80070000;
    v12 = 0;
    if ( EnabledProviderList < 0 )
      goto LABEL_7;
LABEL_23:
    if ( pdwType != 4 )
      goto LABEL_43;
    v13 = (unsigned int *)v41[3 * v2];
    if ( v13 )
      *v13 = v12;
    for ( i = 0; i != 3; ++i )
    {
      v15 = (char *)v38[i];
      v16 = (char *)v10 - v15;
      do
      {
        v17 = *(unsigned __int16 *)&v15[v16];
        v18 = *(unsigned __int16 *)v15 - v17;
        if ( v18 )
          break;
        v15 += 2;
      }
      while ( v17 );
      if ( !v18 )
      {
        v19 = (_DWORD *)v41[3 * v2 - 1];
        if ( !*v19 )
          *v19 = 1;
      }
    }
    if ( (unsigned __int8)FileLogAllowEntry(112) )
      FileLogAdd(L"ReadConfig: '%s'=0x%08X (%d)\n", v10, *v37, v12);
    ++v2;
  }
  v21 = hKey;
  v22 = (unsigned int *)v4 + 51;
  v23 = (unsigned int *)(v4 + 16);
  if ( hkey )
  {
    pcbData = 4;
    if ( !RegGetValueW(hkey, 0, L"TimeJumpAuditOffset", 0xFFFFu, &pdwType, v4 + 16, &pcbData) )
    {
      v24 = 1;
      goto LABEL_47;
    }
  }
  pcbData = 4;
  v24 = 0;
  v25 = RegGetValueW(v21, 0, L"TimeJumpAuditOffset", 0xFFFFu, &pdwType, v4 + 16, &pcbData);
  if ( v25 )
  {
    if ( v25 > 0 )
      v25 = (unsigned __int16)v25 | 0x80070000;
  }
  else
  {
LABEL_47:
    v25 = 0;
  }
  if ( v4 != (struct TimeProvider **)-204LL )
  {
    if ( !v25 )
    {
      *v22 = v24 + 2;
      goto LABEL_51;
    }
    *v22 = 0;
  }
  if ( v25 >= 0 )
  {
LABEL_51:
    if ( pdwType == 4 )
      goto LABEL_52;
    goto LABEL_43;
  }
  *v23 = 28800;
  *v22 = 1;
LABEL_52:
  if ( (unsigned __int8)FileLogAllowEntry(112) )
    FileLogAdd(L"ReadConfig: '%s'=0x%08X (%d)\n", L"TimeJumpAuditOffset", *v23, *v22);
  v26 = (unsigned int *)v4 + 61;
  v27 = hKey;
  if ( hkey )
  {
    pcbData = 4;
    if ( !RegGetValueW(hkey, 0, L"RpcInitFailureAction", 0xFFFFu, &pdwType, v4 + 30, &pcbData) )
    {
      v28 = 1;
      goto LABEL_57;
    }
  }
  pcbData = 4;
  v28 = 0;
  v29 = RegGetValueW(v27, 0, L"RpcInitFailureAction", 0xFFFFu, &pdwType, v4 + 30, &pcbData);
  if ( v29 )
  {
    if ( v29 > 0 )
      v29 = (unsigned __int16)v29 | 0x80070000;
  }
  else
  {
LABEL_57:
    v29 = 0;
  }
  if ( v4 != (struct TimeProvider **)-244LL )
  {
    if ( !v29 )
    {
      *v26 = v28 + 2;
      goto LABEL_61;
    }
    *v26 = 0;
  }
  if ( v29 >= 0 )
  {
LABEL_61:
    if ( pdwType == 4 )
      goto LABEL_62;
LABEL_43:
    EnabledProviderList = -2147418113;
    goto LABEL_7;
  }
  *((_DWORD *)v4 + 60) = 0;
  *v26 = 1;
LABEL_62:
  if ( (unsigned __int8)FileLogAllowEntry(112) )
    FileLogAdd(L"ReadConfig: '%s'=0x%08X (%d)\n", L"RpcInitFailureAction", *((unsigned int *)v4 + 60), *v26);
  EnabledProviderList = ReadClockSettings(v30, (struct ConfigInfo *)v4);
  if ( EnabledProviderList < 0 )
    goto LABEL_7;
  EnabledProviderList = ReadLeapSecondSettings((struct StateInfo *)((char *)a1 + 4208));
  if ( EnabledProviderList < 0 )
    goto LABEL_7;
  ClampSettingValues((struct ConfigInfo *)v4);
  IsSTSReconfirmDisabled(hKey);
  v31 = IsSTSEnabled(*((unsigned int *)v4 + 59), *((unsigned int *)v4 + 58));
  if ( v31 != (*((_DWORD *)v4 + 58) != 0) )
  {
    *((_DWORD *)v4 + 58) = v31;
    if ( (unsigned __int8)FileLogAllowEntry(112) )
      FileLogAdd(L"ReadConfig: '%s'overridden to 0x%08X \n", L"UtilizeSslTimeData", *((unsigned int *)v4 + 58));
  }
  EnabledProviderList = 0;
  *a2 = v4;
LABEL_8:
  if ( hKey )
    RegCloseKey(hKey);
  if ( hkey )
    RegCloseKey(hkey);
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( v35 )
    RegCloseKey(v35);
  return (unsigned int)EnabledProviderList;
}

```

## disassembly

```asm
0x180008930  mov     [rsp-8+arg_8], rdx
0x180008935  mov     [rsp-8+arg_0], rcx
0x18000893a  push    rbp
0x18000893b  push    rbx
0x18000893c  push    rsi
0x18000893d  push    rdi
0x18000893e  push    r13
0x180008940  push    r14
0x180008942  push    r15
0x180008944  lea     rbp, [rsp-140h]
0x18000894c  sub     rsp, 240h
0x180008953  xor     r13d, r13d
0x180008956  mov     edx, 0F8h; uBytes
0x18000895b  mov     [rbp+170h+pdwType], r13d
0x180008962  mov     [rsp+270h+hkey], r13
0x180008967  mov     [rsp+270h+hKey], r13
0x18000896c  lea     ecx, [r13+40h]; uFlags
0x180008970  mov     [rsp+270h+var_218], r13
0x180008975  mov     [rsp+270h+var_220], r13
0x18000897a  call    cs:__imp_LocalAlloc
0x180008981  nop     dword ptr [rax+rax+00h]
0x180008986  mov     rdi, rax
0x180008989  test    rax, rax
0x18000898c  jnz     short loc_180008995
0x18000898e  mov     ebx, 8007000Eh
0x180008993  jmp     short loc_1800089F6
0x180008995  lea     rdx, [rax+8]; struct TimeProvider **
0x180008999  mov     rcx, rdi; struct TimeProvider **
0x18000899c  call    ?GetEnabledProviderList@@YAJPEAPEAUTimeProvider@@0@Z; GetEnabledProviderList(TimeProvider * *,TimeProvider * *)
0x1800089a1  mov     ebx, eax
0x1800089a3  test    eax, eax
0x1800089a5  js      short loc_1800089EE
0x1800089a7  lea     rax, [rsp+270h+hKey]
0x1800089ac  mov     esi, 20019h
0x1800089b1  mov     r14, 0FFFFFFFF80000002h
0x1800089b8  mov     [rsp+270h+phkResult], rax; phkResult
0x1800089bd  mov     r9d, esi; samDesired
0x1800089c0  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Services\\W3"...
0x1800089c7  mov     rcx, r14; hKey
0x1800089ca  xor     r8d, r8d; ulOptions
0x1800089cd  call    cs:__imp_RegOpenKeyExW
0x1800089d4  nop     dword ptr [rax+rax+00h]
0x1800089d9  mov     ebx, eax
0x1800089db  test    eax, eax
0x1800089dd  jz      loc_180008A63
0x1800089e3  jle     short loc_1800089EE
0x1800089e5  movzx   ebx, ax
0x1800089e8  or      ebx, 80070000h
0x1800089ee  mov     rcx, rdi; struct ConfigInfo *
0x1800089f1  call    ?FreeConfigInfo@@YAXPEAUConfigInfo@@@Z; FreeConfigInfo(ConfigInfo *)
0x1800089f6  mov     rcx, [rsp+270h+hKey]; hKey
0x1800089fb  test    rcx, rcx
0x1800089fe  jz      short loc_180008A0C
0x180008a00  call    cs:__imp_RegCloseKey
0x180008a07  nop     dword ptr [rax+rax+00h]
0x180008a0c  mov     rcx, [rsp+270h+hkey]; hKey
0x180008a11  test    rcx, rcx
0x180008a14  jz      short loc_180008A22
0x180008a16  call    cs:__imp_RegCloseKey
0x180008a1d  nop     dword ptr [rax+rax+00h]
0x180008a22  mov     rcx, [rsp+270h+var_220]; hKey
0x180008a27  test    rcx, rcx
0x180008a2a  jz      short loc_180008A38
0x180008a2c  call    cs:__imp_RegCloseKey
0x180008a33  nop     dword ptr [rax+rax+00h]
0x180008a38  mov     rcx, [rsp+270h+var_218]; hKey
0x180008a3d  test    rcx, rcx
0x180008a40  jz      short loc_180008A4E
0x180008a42  call    cs:__imp_RegCloseKey
0x180008a49  nop     dword ptr [rax+rax+00h]
0x180008a4e  mov     eax, ebx
0x180008a50  add     rsp, 240h
0x180008a57  pop     r15
0x180008a59  pop     r14
0x180008a5b  pop     r13
0x180008a5d  pop     rdi
0x180008a5e  pop     rsi
0x180008a5f  pop     rbx
0x180008a60  pop     rbp
0x180008a61  retn
0x180008a63  lea     rax, [rsp+270h+hkey]
0x180008a68  mov     r9d, esi; samDesired
0x180008a6b  xor     r8d, r8d; ulOptions
0x180008a6e  mov     [rsp+270h+phkResult], rax; phkResult
0x180008a73  lea     rdx, aSoftwarePolici_0; "Software\\Policies\\Microsoft\\W32Time"...
0x180008a7a  mov     rcx, r14; hKey
0x180008a7d  call    cs:__imp_RegOpenKeyExW
0x180008a84  nop     dword ptr [rax+rax+00h]
0x180008a89  lea     rax, [rsp+270h+var_220]
0x180008a8e  mov     r9d, esi; samDesired
0x180008a91  xor     r8d, r8d; ulOptions
0x180008a94  mov     [rsp+270h+phkResult], rax; phkResult
0x180008a99  lea     rdx, aSystemCurrentc_7; "System\\CurrentControlSet\\Services\\W3"...
0x180008aa0  mov     rcx, r14; hKey
0x180008aa3  call    cs:__imp_RegOpenKeyExW
0x180008aaa  nop     dword ptr [rax+rax+00h]
0x180008aaf  lea     rax, [rsp+270h+var_218]
0x180008ab4  mov     r9d, esi; samDesired
0x180008ab7  xor     r8d, r8d; ulOptions
0x180008aba  mov     [rsp+270h+phkResult], rax; phkResult
0x180008abf  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\W32Time"...
0x180008ac6  mov     rcx, r14; hKey
0x180008ac9  call    cs:__imp_RegOpenKeyExW
0x180008ad0  nop     dword ptr [rax+rax+00h]
0x180008ad5  lea     rax, [rdi+48h]
0x180008ad9  mov     [rbp+170h+var_1D8], rax
0x180008add  lea     r8, aPhasecorrectra; "PhaseCorrectRate"
0x180008ae4  lea     rax, [rdi+94h]
0x180008aeb  mov     [rbp+170h+lpValue], r8
0x180008aef  mov     [rbp+170h+var_1D0], rax
0x180008af3  lea     rdx, aUpdateinterval; "UpdateInterval"
0x180008afa  lea     rax, [rdi+4Ch]
0x180008afe  mov     [rbp+170h+var_1C8], rdx
0x180008b02  mov     [rbp+170h+var_1C0], rax
0x180008b06  lea     rcx, aFrequencycorre; "FrequencyCorrectRate"
0x180008b0d  lea     rax, [rdi+98h]
0x180008b14  mov     [rbp+170h+var_1B0], rcx
0x180008b18  mov     [rbp+170h+var_1B8], rax
0x180008b1c  lea     rax, [rdi+50h]
0x180008b20  mov     [rbp+170h+var_1A8], rax
0x180008b24  lea     rax, [rdi+9Ch]
0x180008b2b  mov     [rbp+170h+var_1A0], rax
0x180008b2f  lea     rax, aPolladjustfact; "PollAdjustFactor"
0x180008b36  mov     [rbp+170h+var_198], rax
0x180008b3a  lea     rax, [rdi+54h]
0x180008b3e  mov     [rbp+170h+var_190], rax
0x180008b42  lea     rax, [rdi+0A0h]
0x180008b49  mov     [rbp+170h+var_188], rax
0x180008b4d  lea     rax, aLargephaseoffs; "LargePhaseOffset"
0x180008b54  mov     [rbp+170h+var_180], rax
0x180008b58  lea     rax, [rdi+58h]
0x180008b5c  mov     [rbp+170h+var_178], rax
0x180008b60  lea     rax, [rdi+0A4h]
0x180008b67  mov     [rbp+170h+var_170], rax
0x180008b6b  lea     rax, aSpikewatchperi; "SpikeWatchPeriod"
0x180008b72  mov     [rbp+170h+var_168], rax
0x180008b76  lea     rax, [rdi+5Ch]
0x180008b7a  mov     [rbp+170h+var_160], rax
0x180008b7e  lea     rax, [rdi+0A8h]
0x180008b85  mov     [rbp+170h+var_158], rax
0x180008b89  lea     rax, aHoldperiod; "HoldPeriod"
0x180008b90  mov     [rbp+170h+var_150], rax
0x180008b94  lea     rax, [rdi+60h]
0x180008b98  mov     [rbp+170h+var_148], rax
0x180008b9c  lea     rax, [rdi+0ACh]
0x180008ba3  mov     [rbp+170h+var_140], rax
0x180008ba7  lea     rax, aMinpollinterva; "MinPollInterval"
0x180008bae  mov     [rbp+170h+var_138], rax
0x180008bb2  lea     rax, [rdi+64h]
0x180008bb6  mov     [rbp+170h+var_130], rax
0x180008bba  lea     rax, [rdi+0B0h]
0x180008bc1  mov     [rbp+170h+var_128], rax
0x180008bc5  lea     rax, aMaxpollinterva; "MaxPollInterval"
0x180008bcc  mov     [rbp+170h+var_120], rax
0x180008bd0  lea     rax, [rdi+68h]
0x180008bd4  mov     [rbp+170h+var_118], rax
0x180008bd8  lea     rax, [rdi+0B4h]
0x180008bdf  mov     [rbp+170h+var_110], rax
0x180008be3  lea     rax, aClockholdoverp; "ClockHoldoverPeriod"
0x180008bea  mov     [rbp+170h+var_108], rax
0x180008bee  lea     rax, [rdi+6Ch]
0x180008bf2  mov     [rbp+170h+var_100], rax
0x180008bf6  lea     rax, [rdi+0B8h]
0x180008bfd  mov     [rbp+170h+var_F8], rax
0x180008c01  lea     rax, aAnnounceflags; "AnnounceFlags"
0x180008c08  mov     [rsp+270h+var_200], r8
0x180008c0d  mov     [rbp+170h+var_F0], rax
0x180008c14  lea     rax, [rdi+0D8h]
0x180008c1b  mov     [rbp+170h+var_E8], rax
0x180008c22  lea     rax, [rdi+0E0h]
0x180008c29  mov     [rbp+170h+var_E0], rax
0x180008c30  lea     rax, aLocalclockdisp; "LocalClockDispersion"
0x180008c37  mov     [rbp+170h+var_D8], rax
0x180008c3e  lea     rax, [rdi+70h]
0x180008c42  mov     [rbp+170h+var_D0], rax
0x180008c49  lea     rax, [rdi+0BCh]
0x180008c50  mov     [rbp+170h+var_C8], rax
0x180008c57  lea     rax, aMaxnegphasecor; "MaxNegPhaseCorrection"
0x180008c5e  mov     [rbp+170h+var_C0], rax
0x180008c65  lea     rax, [rdi+74h]
0x180008c69  mov     [rbp+170h+var_B8], rax
0x180008c70  lea     rax, [rdi+0C0h]
0x180008c77  mov     [rbp+170h+var_B0], rax
0x180008c7e  lea     rax, aMaxposphasecor; "MaxPosPhaseCorrection"
0x180008c85  mov     [rbp+170h+var_A8], rax
0x180008c8c  lea     rax, [rdi+78h]
0x180008c90  mov     [rbp+170h+var_A0], rax
0x180008c97  lea     rax, [rdi+0C4h]
0x180008c9e  mov     [rbp+170h+var_98], rax
0x180008ca5  lea     rax, aEventlogflags; "EventLogFlags"
0x180008cac  mov     [rbp+170h+var_90], rax
0x180008cb3  lea     rax, [rdi+0DCh]
0x180008cba  mov     [rbp+170h+var_88], rax
0x180008cc1  lea     rax, [rdi+0E4h]
0x180008cc8  mov     [rbp+170h+var_80], rax
0x180008ccf  lea     rax, aMaxallowedphas; "MaxAllowedPhaseOffset"
0x180008cd6  mov     [rbp+170h+var_78], rax
0x180008cdd  lea     rax, [rdi+7Ch]
0x180008ce1  mov     [rbp+170h+var_70], rax
0x180008ce8  lea     rax, [rdi+0C8h]
0x180008cef  mov     [rbp+170h+var_68], rax
0x180008cf6  lea     rax, aUtilizessltime_0; "UtilizeSslTimeData"
0x180008cfd  mov     [rbp+170h+var_60], rax
0x180008d04  lea     rax, [rdi+0E8h]
0x180008d0b  mov     [rbp+170h+var_58], rax
0x180008d12  lea     rax, [rdi+0ECh]
0x180008d19  mov     [rbp+170h+var_50], rax
0x180008d20  lea     rax, aClockadjustmen; "ClockAdjustmentAuditLimit"
0x180008d27  mov     [rbp+170h+var_48], rax
0x180008d2e  lea     rax, [rdi+84h]
0x180008d35  mov     [rbp+170h+var_40], rax
0x180008d3c  lea     rax, [rdi+0D0h]
0x180008d43  mov     [rbp+170h+var_38], rax
0x180008d4a  mov     [rsp+270h+var_1F8], rdx
0x180008d4f  mov     [rbp+170h+var_1F0], rcx
0x180008d53  mov     rcx, [rsp+270h+hkey]; hkey
0x180008d58  cmp     r13d, 12h
0x180008d5c  jnb     loc_180008EDC
0x180008d62  mov     eax, r13d
0x180008d65  lea     r14, [rax+rax*2]
0x180008d69  mov     rax, [rsp+270h+hKey]
0x180008d6e  mov     rbx, [rbp+r14*8+170h+var_1D8]
0x180008d73  mov     r15, [rbp+r14*8+170h+lpValue]
0x180008d78  mov     [rsp+270h+var_208], rbx
0x180008d7d  mov     [rsp+270h+var_210], rax
0x180008d82  test    rcx, rcx
0x180008d85  jz      loc_180008E6A
0x180008d8b  lea     rax, [rbp+170h+arg_18]
0x180008d92  mov     [rbp+170h+arg_18], 4
0x180008d9c  mov     [rsp+270h+pcbData], rax; pcbData
0x180008da1  mov     r9d, 0FFFFh; dwFlags
0x180008da7  lea     rax, [rbp+170h+pdwType]
0x180008dae  mov     [rsp+270h+pvData], rbx; pvData
0x180008db3  mov     r8, r15; lpValue
0x180008db6  mov     [rsp+270h+phkResult], rax; pdwType
0x180008dbb  xor     edx, edx; lpSubKey
0x180008dbd  call    cs:__imp_RegGetValueW
0x180008dc4  nop     dword ptr [rax+rax+00h]
0x180008dc9  test    eax, eax
0x180008dcb  jnz     loc_180008E65
0x180008dd1  mov     sil, 1
0x180008dd4  movzx   esi, sil
0x180008dd8  add     esi, 2
0x180008ddb  cmp     [rbp+170h+pdwType], 4
0x180008de2  jnz     loc_180008ED2
0x180008de8  mov     rax, [rbp+r14*8+170h+var_1D0]
0x180008ded  test    rax, rax
0x180008df0  jz      short loc_180008DF4
0x180008df2  mov     [rax], esi
0x180008df4  xor     ecx, ecx
0x180008df6  mov     rax, [rsp+rcx*8+270h+var_200]
0x180008dfb  mov     r9, r15
0x180008dfe  sub     r9, rax
0x180008e01  movzx   r8d, word ptr [rax]
0x180008e05  movzx   edx, word ptr [rax+r9]
0x180008e0a  sub     r8d, edx
0x180008e0d  jnz     short loc_180008E17
0x180008e0f  add     rax, 2
0x180008e13  test    edx, edx
0x180008e15  jnz     short loc_180008E01
0x180008e17  test    r8d, r8d
0x180008e1a  jnz     short loc_180008E2C
0x180008e1c  mov     rax, [rbp+r14*8+170h+var_1D8]
0x180008e21  cmp     [rax], r8d
0x180008e24  jnz     short loc_180008E2C
0x180008e26  mov     dword ptr [rax], 1
0x180008e2c  inc     rcx
0x180008e2f  cmp     rcx, 3
0x180008e33  jnz     short loc_180008DF6
0x180008e35  mov     ecx, 70h ; 'p'
0x180008e3a  call    FileLogAllowEntry
0x180008e3f  test    al, al
0x180008e41  jz      short loc_180008E5D
0x180008e43  mov     r8, [rsp+270h+var_208]
0x180008e48  lea     rcx, aReadconfigS0x0; "ReadConfig: '%s'=0x%08X (%d)\n"
0x180008e4f  mov     r9d, esi
0x180008e52  mov     rdx, r15
0x180008e55  mov     r8d, [r8]
0x180008e58  call    FileLogAdd
0x180008e5d  inc     r13d
0x180008e60  jmp     loc_180008D53
0x180008e65  mov     rax, [rsp+270h+var_210]
0x180008e6a  lea     rcx, [rbp+170h+arg_18]
0x180008e71  mov     [rbp+170h+arg_18], 4
0x180008e7b  mov     [rsp+270h+pcbData], rcx; pcbData
0x180008e80  mov     r9d, 0FFFFh; dwFlags
0x180008e86  lea     rcx, [rbp+170h+pdwType]
0x180008e8d  mov     [rsp+270h+pvData], rbx; pvData
0x180008e92  mov     [rsp+270h+phkResult], rcx; pdwType
0x180008e97  mov     r8, r15; lpValue
0x180008e9a  mov     rcx, rax; hkey
0x180008e9d  xor     edx, edx; lpSubKey
0x180008e9f  xor     sil, sil
0x180008ea2  call    cs:__imp_RegGetValueW
0x180008ea9  nop     dword ptr [rax+rax+00h]
0x180008eae  mov     ebx, eax
0x180008eb0  test    eax, eax
0x180008eb2  jz      loc_180008DD4
0x180008eb8  jle     short loc_180008EC3
0x180008eba  movzx   ebx, ax
  ... truncated ...
```
