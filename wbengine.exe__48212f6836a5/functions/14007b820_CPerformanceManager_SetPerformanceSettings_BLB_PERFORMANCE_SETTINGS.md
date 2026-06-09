# CPerformanceManager::SetPerformanceSettings(_BLB_PERFORMANCE_SETTINGS *)

- ea: `0x14007b820`
- end: `0x14007bef8`
- name: `?SetPerformanceSettings@CPerformanceManager@@SAJPEAU_BLB_PERFORMANCE_SETTINGS@@@Z`
- size: `1752`
- prototype: `__int64 __fastcall(struct _BLB_PERFORMANCE_SETTINGS *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1400559a0`

## callees

- `0x1400063b4`
- `0x140006ca8`
- `0x140007ad3`
- `0x14000bb24`
- `0x14000bb4c`
- `0x14001358c`
- `0x140014260`
- `0x14003c434`
- `0x14007b820`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x14007b948`
- `ADVAPI32!RegOpenKeyExW` at `0x14007b948`
- `ADVAPI32!RegSetValueExW` at `0x14007bd2e`
- `ADVAPI32!RegSetValueExW` at `0x14007bdb3`
- `ADVAPI32!RegSetValueExW` at `0x14007bd2e`
- `ADVAPI32!RegSetValueExW` at `0x14007bdb3`
- `ADVAPI32!RegCloseKey` at `0x14007baf4`
- `ADVAPI32!RegCloseKey` at `0x14007baf4`
- `msvcrt!_scwprintf` at `0x14007ba08`
- `msvcrt!_scwprintf` at `0x14007ba08`
- `ole32!CoTaskMemAlloc` at `0x14007b897`
- `ole32!CoTaskMemAlloc` at `0x14007b8ab`
- `ole32!CoTaskMemAlloc` at `0x14007ba1b`
- `ole32!CoTaskMemAlloc` at `0x14007bbb5`
- `ole32!CoTaskMemAlloc` at `0x14007b897`
- `ole32!CoTaskMemAlloc` at `0x14007b8ab`
- `ole32!CoTaskMemAlloc` at `0x14007ba1b`
- `ole32!CoTaskMemAlloc` at `0x14007bbb5`
- `ole32!CoTaskMemFree` at `0x14007bacb`
- `ole32!CoTaskMemFree` at `0x14007badd`
- `ole32!CoTaskMemFree` at `0x14007be76`
- `ole32!CoTaskMemFree` at `0x14007be7f`
- `ole32!CoTaskMemFree` at `0x14007bacb`
- `ole32!CoTaskMemFree` at `0x14007badd`
- `ole32!CoTaskMemFree` at `0x14007be76`
- `ole32!CoTaskMemFree` at `0x14007be7f`
- `RPCRT4!UuidToStringW` at `0x14007b9c0`
- `RPCRT4!UuidToStringW` at `0x14007b9c0`

## string_xrefs

- `0x14007b87c`: `base\stor\blb\engine\service\performancemanager.cpp`
- `0x14007b9e9`: `base\stor\blb\engine\service\performancemanager.cpp`
- `0x14007bcf3`: `base\stor\blb\engine\service\performancemanager.cpp`
- `0x14007bdd1`: `base\stor\blb\engine\service\performancemanager.cpp`
- `0x14007bce7`: `wszTempCustomPerformanceSetting == (wszCustomPerformanceSetting + dwcCustomPerformanceSetting -1)`

## pseudocode

```c
__int64 __fastcall CPerformanceManager::SetPerformanceSettings(struct _BLB_PERFORMANCE_SETTINGS *a1)
{
  SIZE_T v2; // rcx
  _QWORD *v3; // r15
  SIZE_T v4; // rcx
  void *v5; // rax
  void *v6; // r14
  BYTE *v7; // r12
  size_t v8; // r8
  int v9; // ebx
  int v10; // r13d
  __int64 i; // r15
  const UUID *v12; // rcx
  int v13; // r12d
  unsigned __int64 v14; // rbx
  void *v15; // rax
  _QWORD *v16; // rcx
  __int64 v17; // rdx
  __int64 j; // r14
  LSTATUS v19; // esi
  _QWORD *v20; // rcx
  __int64 v21; // rdx
  unsigned int v22; // r13d
  BYTE *v23; // rax
  BYTE *v24; // r14
  BYTE *v25; // r15
  __int64 v26; // r14
  __int64 v27; // rax
  LSTATUS v28; // r14d
  _QWORD *v29; // rcx
  __int64 v30; // rdx
  PVOID *v31; // rcx
  PHKEY phkResult; // [rsp+20h] [rbp-20h]
  HKEY hKey; // [rsp+30h] [rbp-10h] BYREF
  RPC_WSTR StringUuid; // [rsp+38h] [rbp-8h] BYREF
  int Data; // [rsp+80h] [rbp+40h] BYREF
  _QWORD *v37; // [rsp+88h] [rbp+48h]
  BYTE *lpData; // [rsp+90h] [rbp+50h]
  LPVOID pv; // [rsp+98h] [rbp+58h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_9793dd91b374347cf06074f3d6f4ba29_Traceguids);
  }
  if ( !a1 )
    BlbAssert("base\\stor\\blb\\engine\\service\\performancemanager.cpp", 0x53u, "pPerformanceSettings");
  v2 = 8LL * *((unsigned int *)a1 + 1);
  hKey = 0;
  v3 = CoTaskMemAlloc(v2);
  v4 = 4LL * *((unsigned int *)a1 + 1);
  v37 = v3;
  v5 = CoTaskMemAlloc(v4);
  pv = v5;
  v6 = v5;
  if ( !v3 || !v5 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_9793dd91b374347cf06074f3d6f4ba29_Traceguids);
    }
    v7 = 0;
    v9 = -2147024882;
    if ( v3 )
      goto LABEL_35;
    goto LABEL_38;
  }
  v7 = 0;
  v8 = 8LL * *((unsigned int *)a1 + 1);
  lpData = 0;
  memset_0(v3, 0, v8);
  memset_0(v6, 0, 4LL * *((unsigned int *)a1 + 1));
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_9793dd91b374347cf06074f3d6f4ba29_Traceguids);
  }
  v9 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\Windows Block Level Backup",
         0,
         2u,
         &hKey);
  if ( v9 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_9793dd91b374347cf06074f3d6f4ba29_Traceguids);
    }
    if ( v9 > 0 )
      v9 = (unsigned __int16)v9 | 0x80070000;
    goto LABEL_35;
  }
  v9 = 0;
  v10 = 0;
  for ( i = 0; (unsigned int)i < *((_DWORD *)a1 + 1); i = (unsigned int)(i + 1) )
  {
    v12 = (const UUID *)(*((_QWORD *)a1 + 1) + 16LL * (unsigned int)i);
    StringUuid = 0;
    if ( UuidToStringW(v12, &StringUuid) )
    {
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v21 = 14;
LABEL_50:
        WPP_SF_(v20[2], v21, WPP_9793dd91b374347cf06074f3d6f4ba29_Traceguids);
      }
LABEL_51:
      v9 = -2147024882;
      goto LABEL_33;
    }
    if ( (unsigned int)(*(_DWORD *)(*((_QWORD *)a1 + 2) + 4 * i) - 1) > 1 )
      BlbAssert(
        "base\\stor\\blb\\engine\\service\\performancemanager.cpp",
        0x85u,
        "(pPerformanceSettings->m_rgePerformanceSettingType[i] == BLB_PST_ALWAYS_FULL) || (pPerformanceSettings->m_rgePer"
        "formanceSettingType[i] == BLB_PST_ALWAYS_INCREMENTAL)");
    v13 = _scwprintf(L"%s,%u", StringUuid, *(unsigned int *)(*((_QWORD *)a1 + 2) + 4 * i));
    v14 = v13 + 1;
    v15 = CoTaskMemAlloc(2 * v14);
    v37[i] = v15;
    if ( !v15 )
    {
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v21 = 15;
        goto LABEL_50;
      }
      goto LABEL_51;
    }
    memset_0(v15, 0, 2 * v14);
    LODWORD(phkResult) = *(_DWORD *)(*((_QWORD *)a1 + 2) + 4 * i);
    v9 = StringCchPrintfW((unsigned __int16 *)v37[i], v14, L"%s,%u", StringUuid, phkResult);
    if ( v9 < 0 )
    {
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v17 = 16;
LABEL_32:
        WPP_SF_(v16[2], v17, WPP_9793dd91b374347cf06074f3d6f4ba29_Traceguids);
      }
      goto LABEL_33;
    }
    v10 += v13 + 1;
    *((_DWORD *)v6 + i) = v13;
  }
  v22 = v10 + 1;
  v23 = (BYTE *)CoTaskMemAlloc(2LL * v22);
  lpData = v23;
  v24 = v23;
  if ( !v23 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_9793dd91b374347cf06074f3d6f4ba29_Traceguids);
    }
    v9 = -2147024882;
    v7 = 0;
    goto LABEL_34;
  }
  memset_0(v23, 0, 2LL * v22);
  v25 = v24;
  v26 = 0;
  while ( 1 )
  {
    if ( (unsigned int)v26 >= *((_DWORD *)a1 + 1) )
    {
      if ( v25 != &lpData[2 * v22 - 2] )
        BlbAssert(
          "base\\stor\\blb\\engine\\service\\performancemanager.cpp",
          0xBAu,
          "wszTempCustomPerformanceSetting == (wszCustomPerformanceSetting + dwcCustomPerformanceSetting -1)");
      v7 = lpData;
      *(_WORD *)v25 = 0;
      v28 = RegSetValueExW(hKey, L"CustomPerformanceSettings", 0, 7u, v7, 2 * v22);
      if ( v28 )
      {
        v29 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_82;
        }
        v30 = 20;
      }
      else
      {
        Data = *(_DWORD *)a1;
        v28 = RegSetValueExW(hKey, L"OverallPerformanceSetting", 0, 4u, (const BYTE *)&Data, 4u);
        if ( (unsigned int)(*(_DWORD *)a1 - 1) > 2 )
          BlbAssert(
            "base\\stor\\blb\\engine\\service\\performancemanager.cpp",
            0xDAu,
            "(pPerformanceSettings->m_eOverallPerformanceSettingType == BLB_PST_ALWAYS_FULL) || (pPerformanceSettings->m_"
            "eOverallPerformanceSettingType == BLB_PST_ALWAYS_INCREMENTAL) || (pPerformanceSettings->m_eOverallPerformanc"
            "eSettingType == BLB_PST_CUSTOM)");
        if ( !v28 )
          goto LABEL_34;
        v29 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
LABEL_82:
          if ( v28 > 0 )
            v9 = (unsigned __int16)v28 | 0x80070000;
          else
            v9 = v28;
          goto LABEL_34;
        }
        v30 = 21;
      }
      WPP_SF_(v29[2], v30, WPP_9793dd91b374347cf06074f3d6f4ba29_Traceguids);
      goto LABEL_82;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        18,
        (unsigned int)WPP_9793dd91b374347cf06074f3d6f4ba29_Traceguids,
        v37[v26],
        *((_DWORD *)pv + v26));
    }
    v9 = StringCchCopyW((unsigned __int16 *)v25, *((unsigned int *)pv + v26) + 1LL, (unsigned __int16 *)v37[v26]);
    if ( v9 < 0 )
      break;
    v27 = (unsigned int)(*((_DWORD *)pv + v26) + 1);
    v26 = (unsigned int)(v26 + 1);
    v25 += 2 * v27;
  }
  v16 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v17 = 19;
    goto LABEL_32;
  }
LABEL_33:
  v7 = lpData;
LABEL_34:
  v3 = v37;
LABEL_35:
  for ( j = 0; (unsigned int)j < *((_DWORD *)a1 + 1); j = (unsigned int)(j + 1) )
    CoTaskMemFree((LPVOID)v3[j]);
  CoTaskMemFree(v3);
  v6 = pv;
LABEL_38:
  if ( hKey )
  {
    v19 = RegCloseKey(hKey);
    if ( v19 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_9793dd91b374347cf06074f3d6f4ba29_Traceguids);
      }
      if ( v19 > 0 )
        v9 = (unsigned __int16)v19 | 0x80070000;
      else
        v9 = v19;
    }
    hKey = 0;
  }
  CoTaskMemFree(v6);
  CoTaskMemFree(v7);
  if ( v9 >= 0 )
  {
LABEL_106:
    v31 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_107;
  }
  v31 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_9793dd91b374347cf06074f3d6f4ba29_Traceguids);
      goto LABEL_106;
    }
LABEL_107:
    if ( v31 != &WPP_GLOBAL_Control && (*((_BYTE *)v31 + 28) & 1) != 0 && *((_BYTE *)v31 + 25) >= 4u )
      WPP_SF_(v31[2], 24, WPP_9793dd91b374347cf06074f3d6f4ba29_Traceguids);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x14007b820  push    rbp
0x14007b822  push    rbx
0x14007b823  push    rsi
0x14007b824  push    r12
0x14007b826  push    r13
0x14007b828  push    r14
0x14007b82a  push    r15
0x14007b82c  mov     rbp, rsp
0x14007b82f  sub     rsp, 40h
0x14007b833  mov     rsi, rcx
0x14007b836  mov     rcx, cs:WPP_GLOBAL_Control
0x14007b83d  lea     r13, WPP_GLOBAL_Control
0x14007b844  lea     rbx, WPP_9793dd91b374347cf06074f3d6f4ba29_Traceguids
0x14007b84b  cmp     rcx, r13
0x14007b84e  jz      short loc_14007B86D
0x14007b850  test    byte ptr [rcx+1Ch], 1
0x14007b854  jz      short loc_14007B86D
0x14007b856  cmp     byte ptr [rcx+19h], 4
0x14007b85a  jb      short loc_14007B86D
0x14007b85c  mov     rcx, [rcx+10h]
0x14007b860  mov     edx, 0Ah
0x14007b865  mov     r8, rbx
0x14007b868  call    WPP_SF_
0x14007b86d  test    rsi, rsi
0x14007b870  jnz     short loc_14007B888
0x14007b872  lea     r8, aPperformancese_0; "pPerformanceSettings"
0x14007b879  lea     edx, [rsi+53h]; unsigned int
0x14007b87c  lea     rcx, aBaseStorBlbEng_34; "base\\stor\\blb\\engine\\service\\perfo"...
0x14007b883  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x14007b888  mov     ecx, [rsi+4]
0x14007b88b  shl     rcx, 3; cb
0x14007b88f  mov     [rbp+hKey], 0
0x14007b897  call    cs:__imp_CoTaskMemAlloc
0x14007b89d  mov     ecx, [rsi+4]
0x14007b8a0  mov     r15, rax
0x14007b8a3  shl     rcx, 2; cb
0x14007b8a7  mov     [rbp+arg_8], rax
0x14007b8ab  call    cs:__imp_CoTaskMemAlloc
0x14007b8b1  mov     [rbp+pv], rax
0x14007b8b5  mov     r14, rax
0x14007b8b8  test    r15, r15
0x14007b8bb  jz      loc_14007BE17
0x14007b8c1  test    rax, rax
0x14007b8c4  jz      loc_14007BE17
0x14007b8ca  mov     r8d, [rsi+4]
0x14007b8ce  xor     r12d, r12d
0x14007b8d1  shl     r8, 3; Size
0x14007b8d5  xor     edx, edx; Val
0x14007b8d7  mov     rcx, r15; void *
0x14007b8da  mov     [rbp+lpData], r12
0x14007b8de  call    memset_0
0x14007b8e3  mov     r8d, [rsi+4]
0x14007b8e7  xor     edx, edx; Val
0x14007b8e9  shl     r8, 2; Size
0x14007b8ed  mov     rcx, r14; void *
0x14007b8f0  call    memset_0
0x14007b8f5  mov     rcx, cs:WPP_GLOBAL_Control
0x14007b8fc  cmp     rcx, r13
0x14007b8ff  jz      short loc_14007B928
0x14007b901  test    byte ptr [rcx+1Ch], 1
0x14007b905  jz      short loc_14007B928
0x14007b907  cmp     byte ptr [rcx+19h], 4
0x14007b90b  jb      short loc_14007B928
0x14007b90d  mov     eax, [rsi+4]
0x14007b910  lea     edx, [r12+0Ch]
0x14007b915  mov     r9d, [rsi]
0x14007b918  mov     r8, rbx
0x14007b91b  mov     rcx, [rcx+10h]
0x14007b91f  mov     dword ptr [rsp+40h+phkResult], eax
0x14007b923  call    WPP_SF_dd
0x14007b928  lea     rax, [rbp+hKey]
0x14007b92c  mov     r9d, 2; samDesired
0x14007b932  xor     r8d, r8d; ulOptions
0x14007b935  mov     [rsp+40h+phkResult], rax; phkResult
0x14007b93a  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Windows\\CurrentVe"...
0x14007b941  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14007b948  call    cs:__imp_RegOpenKeyExW
0x14007b94e  mov     ebx, eax
0x14007b950  test    eax, eax
0x14007b952  jz      short loc_14007B997
0x14007b954  mov     rcx, cs:WPP_GLOBAL_Control
0x14007b95b  cmp     rcx, r13
0x14007b95e  jz      short loc_14007B981
0x14007b960  test    byte ptr [rcx+1Ch], 1
0x14007b964  jz      short loc_14007B981
0x14007b966  cmp     byte ptr [rcx+19h], 2
0x14007b96a  jb      short loc_14007B981
0x14007b96c  mov     rcx, [rcx+10h]
0x14007b970  lea     r8, WPP_9793dd91b374347cf06074f3d6f4ba29_Traceguids
0x14007b977  mov     edx, 0Dh
0x14007b97c  call    WPP_SF_
0x14007b981  test    ebx, ebx
0x14007b983  jle     loc_14007BABE
0x14007b989  movzx   ebx, bx
0x14007b98c  or      ebx, 80070000h
0x14007b992  jmp     loc_14007BABE
0x14007b997  xor     ebx, ebx
0x14007b999  xor     r13d, r13d
0x14007b99c  xor     r15d, r15d
0x14007b99f  cmp     r15d, [rsi+4]
0x14007b9a3  jnb     loc_14007BBA7
0x14007b9a9  mov     ecx, r15d
0x14007b9ac  lea     rdx, [rbp+StringUuid]; StringUuid
0x14007b9b0  shl     rcx, 4
0x14007b9b4  add     rcx, [rsi+8]; Uuid
0x14007b9b8  mov     [rbp+StringUuid], 0
0x14007b9c0  call    cs:__imp_UuidToStringW
0x14007b9c6  test    eax, eax
0x14007b9c8  jnz     loc_14007BB81
0x14007b9ce  mov     rax, [rsi+10h]
0x14007b9d2  mov     ecx, [rax+r15*4]
0x14007b9d6  dec     ecx
0x14007b9d8  cmp     ecx, 1
0x14007b9db  jbe     short loc_14007B9F5
0x14007b9dd  lea     r8, aPperformancese_1; "(pPerformanceSettings->m_rgePerformance"...
0x14007b9e4  mov     edx, 85h; unsigned int
0x14007b9e9  lea     rcx, aBaseStorBlbEng_34; "base\\stor\\blb\\engine\\service\\perfo"...
0x14007b9f0  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x14007b9f5  mov     r8, [rsi+10h]
0x14007b9f9  lea     rcx, aSU; "%s,%u"
0x14007ba00  mov     rdx, [rbp+StringUuid]
0x14007ba04  mov     r8d, [r8+r15*4]
0x14007ba08  call    cs:__imp__scwprintf
0x14007ba0e  mov     r12d, eax
0x14007ba11  lea     ecx, [rax+1]
0x14007ba14  movsxd  rbx, ecx
0x14007ba17  lea     rcx, [rbx+rbx]; cb
0x14007ba1b  call    cs:__imp_CoTaskMemAlloc
0x14007ba21  mov     rcx, [rbp+arg_8]
0x14007ba25  mov     [rcx+r15*8], rax
0x14007ba29  test    rax, rax
0x14007ba2c  jz      loc_14007BB43
0x14007ba32  lea     r8, [rbx+rbx]; Size
0x14007ba36  xor     edx, edx; Val
0x14007ba38  mov     rcx, rax; void *
0x14007ba3b  call    memset_0
0x14007ba40  mov     rax, [rsi+10h]
0x14007ba44  lea     r8, aSU; "%s,%u"
0x14007ba4b  mov     r9, [rbp+StringUuid]
0x14007ba4f  mov     rdx, rbx; unsigned __int64
0x14007ba52  mov     ecx, [rax+r15*4]
0x14007ba56  mov     rax, [rbp+arg_8]
0x14007ba5a  mov     dword ptr [rsp+40h+phkResult], ecx
0x14007ba5e  mov     rcx, [rax+r15*8]; unsigned __int16 *
0x14007ba62  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14007ba67  mov     ebx, eax
0x14007ba69  test    eax, eax
0x14007ba6b  js      short loc_14007BA82
0x14007ba6d  inc     r13d
0x14007ba70  mov     rax, r14
0x14007ba73  add     r13d, r12d
0x14007ba76  mov     [rax+r15*4], r12d
0x14007ba7a  inc     r15d
0x14007ba7d  jmp     loc_14007B99F
0x14007ba82  mov     rcx, cs:WPP_GLOBAL_Control
0x14007ba89  lea     r13, WPP_GLOBAL_Control
0x14007ba90  cmp     rcx, r13
0x14007ba93  jz      short loc_14007BAB6
0x14007ba95  test    byte ptr [rcx+1Ch], 1
0x14007ba99  jz      short loc_14007BAB6
0x14007ba9b  cmp     byte ptr [rcx+19h], 2
0x14007ba9f  jb      short loc_14007BAB6
0x14007baa1  mov     edx, 10h
0x14007baa6  mov     rcx, [rcx+10h]
0x14007baaa  lea     r8, WPP_9793dd91b374347cf06074f3d6f4ba29_Traceguids
0x14007bab1  call    WPP_SF_
0x14007bab6  mov     r12, [rbp+lpData]
0x14007baba  mov     r15, [rbp+arg_8]
0x14007babe  xor     r14d, r14d
0x14007bac1  cmp     [rsi+4], r14d
0x14007bac5  jbe     short loc_14007BADA
0x14007bac7  mov     rcx, [r15+r14*8]; pv
0x14007bacb  call    cs:__imp_CoTaskMemFree
0x14007bad1  inc     r14d
0x14007bad4  cmp     r14d, [rsi+4]
0x14007bad8  jb      short loc_14007BAC7
0x14007bada  mov     rcx, r15; pv
0x14007badd  call    cs:__imp_CoTaskMemFree
0x14007bae3  mov     r14, [rbp+pv]
0x14007bae7  mov     rcx, [rbp+hKey]; hKey
0x14007baeb  test    rcx, rcx
0x14007baee  jz      loc_14007BE73
0x14007baf4  call    cs:__imp_RegCloseKey
0x14007bafa  mov     esi, eax
0x14007bafc  test    eax, eax
0x14007bafe  jz      loc_14007BE6B
0x14007bb04  mov     rcx, cs:WPP_GLOBAL_Control
0x14007bb0b  cmp     rcx, r13
0x14007bb0e  jz      short loc_14007BB34
0x14007bb10  test    byte ptr [rcx+1Ch], 1
0x14007bb14  jz      short loc_14007BB34
0x14007bb16  cmp     byte ptr [rcx+19h], 2
0x14007bb1a  jb      short loc_14007BB34
0x14007bb1c  mov     rcx, [rcx+10h]
0x14007bb20  lea     r8, WPP_9793dd91b374347cf06074f3d6f4ba29_Traceguids
0x14007bb27  mov     edx, 16h
0x14007bb2c  mov     r9d, eax
0x14007bb2f  call    WPP_SF_d
0x14007bb34  test    esi, esi
0x14007bb36  jg      loc_14007BE62
0x14007bb3c  mov     ebx, esi
0x14007bb3e  jmp     loc_14007BE6B
0x14007bb43  mov     rcx, cs:WPP_GLOBAL_Control
0x14007bb4a  lea     r13, WPP_GLOBAL_Control
0x14007bb51  cmp     rcx, r13
0x14007bb54  jz      short loc_14007BB77
0x14007bb56  test    byte ptr [rcx+1Ch], 1
0x14007bb5a  jz      short loc_14007BB77
0x14007bb5c  cmp     byte ptr [rcx+19h], 2
0x14007bb60  jb      short loc_14007BB77
0x14007bb62  mov     edx, 0Fh
0x14007bb67  mov     rcx, [rcx+10h]
0x14007bb6b  lea     r8, WPP_9793dd91b374347cf06074f3d6f4ba29_Traceguids
0x14007bb72  call    WPP_SF_
0x14007bb77  mov     ebx, 8007000Eh
0x14007bb7c  jmp     loc_14007BAB6
0x14007bb81  mov     rcx, cs:WPP_GLOBAL_Control
0x14007bb88  lea     r13, WPP_GLOBAL_Control
0x14007bb8f  cmp     rcx, r13
0x14007bb92  jz      short loc_14007BB77
0x14007bb94  test    byte ptr [rcx+1Ch], 1
0x14007bb98  jz      short loc_14007BB77
0x14007bb9a  cmp     byte ptr [rcx+19h], 2
0x14007bb9e  jb      short loc_14007BB77
0x14007bba0  mov     edx, 0Eh
0x14007bba5  jmp     short loc_14007BB67
0x14007bba7  inc     r13d
0x14007bbaa  lea     r12, ds:0[r13*2]
0x14007bbb2  mov     rcx, r12; cb
0x14007bbb5  call    cs:__imp_CoTaskMemAlloc
0x14007bbbb  mov     [rbp+lpData], rax
0x14007bbbf  mov     r14, rax
0x14007bbc2  test    rax, rax
0x14007bbc5  jnz     short loc_14007BC06
0x14007bbc7  mov     rcx, cs:WPP_GLOBAL_Control
0x14007bbce  lea     r13, WPP_GLOBAL_Control
0x14007bbd5  cmp     rcx, r13
0x14007bbd8  jz      short loc_14007BBF9
0x14007bbda  test    byte ptr [rcx+1Ch], 1
0x14007bbde  jz      short loc_14007BBF9
0x14007bbe0  cmp     byte ptr [rcx+19h], 2
0x14007bbe4  jb      short loc_14007BBF9
0x14007bbe6  mov     rcx, [rcx+10h]
0x14007bbea  lea     edx, [rax+11h]
0x14007bbed  lea     r8, WPP_9793dd91b374347cf06074f3d6f4ba29_Traceguids
0x14007bbf4  call    WPP_SF_
0x14007bbf9  mov     ebx, 8007000Eh
0x14007bbfe  mov     r12, r14
0x14007bc01  jmp     loc_14007BABA
0x14007bc06  mov     r8, r12; Size
0x14007bc09  xor     edx, edx; Val
0x14007bc0b  mov     rcx, r14; void *
0x14007bc0e  call    memset_0
0x14007bc13  mov     r15, r14
0x14007bc16  xor     r14d, r14d
0x14007bc19  cmp     r14d, [rsi+4]
0x14007bc1d  jnb     loc_14007BCD7
0x14007bc23  mov     rcx, cs:WPP_GLOBAL_Control
0x14007bc2a  lea     rax, WPP_GLOBAL_Control
0x14007bc31  cmp     rcx, rax
0x14007bc34  jz      short loc_14007BC6B
0x14007bc36  test    byte ptr [rcx+1Ch], 1
0x14007bc3a  jz      short loc_14007BC6B
0x14007bc3c  cmp     byte ptr [rcx+19h], 4
0x14007bc40  jb      short loc_14007BC6B
0x14007bc42  mov     rax, [rbp+pv]
0x14007bc46  lea     r8, WPP_9793dd91b374347cf06074f3d6f4ba29_Traceguids
0x14007bc4d  mov     rcx, [rcx+10h]
0x14007bc51  mov     edx, 12h
0x14007bc56  mov     eax, [rax+r14*4]
0x14007bc5a  mov     dword ptr [rsp+40h+phkResult], eax
0x14007bc5e  mov     rax, [rbp+arg_8]
0x14007bc62  mov     r9, [rax+r14*8]
0x14007bc66  call    WPP_SF_Sd
0x14007bc6b  mov     rax, [rbp+pv]
0x14007bc6f  mov     rcx, r15; unsigned __int16 *
0x14007bc72  mov     edx, [rax+r14*4]
0x14007bc76  mov     rax, [rbp+arg_8]
0x14007bc7a  inc     rdx; unsigned __int64
0x14007bc7d  mov     r8, [rax+r14*8]; unsigned __int16 *
0x14007bc81  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14007bc86  mov     ebx, eax
0x14007bc88  test    eax, eax
0x14007bc8a  js      short loc_14007BCA2
0x14007bc8c  mov     rax, [rbp+pv]
0x14007bc90  mov     eax, [rax+r14*4]
0x14007bc94  inc     eax
0x14007bc96  inc     r14d
0x14007bc99  lea     r15, [r15+rax*2]
0x14007bc9d  jmp     loc_14007BC19
0x14007bca2  mov     rcx, cs:WPP_GLOBAL_Control
0x14007bca9  lea     r13, WPP_GLOBAL_Control
0x14007bcb0  cmp     rcx, r13
0x14007bcb3  jz      loc_14007BAB6
0x14007bcb9  test    byte ptr [rcx+1Ch], 1
0x14007bcbd  jz      loc_14007BAB6
0x14007bcc3  cmp     byte ptr [rcx+19h], 2
0x14007bcc7  jb      loc_14007BAB6
0x14007bccd  mov     edx, 13h
0x14007bcd2  jmp     loc_14007BAA6
  ... truncated ...
```
