# CPerformanceManager::QueryPerformanceSettings(_BLB_PERFORMANCE_SETTINGS * *)

- ea: `0x14007b0a0`
- end: `0x14007b818`
- name: `?QueryPerformanceSettings@CPerformanceManager@@SAJPEAPEAU_BLB_PERFORMANCE_SETTINGS@@@Z`
- size: `1912`
- prototype: `__int64 __fastcall(struct _BLB_PERFORMANCE_SETTINGS **)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140055020`
- `0x14007afe0`

## callees

- `0x140006ca8`
- `0x140007ad3`
- `0x14000bb24`
- `0x14000bb4c`
- `0x140014200`
- `0x14003c54c`
- `0x14007ad7c`
- `0x14007b0a0`
- `0x14012e250`

## import_xrefs

- `ADVAPI32!RegGetValueW` at `0x14007b247`
- `ADVAPI32!RegGetValueW` at `0x14007b357`
- `ADVAPI32!RegGetValueW` at `0x14007b45c`
- `ADVAPI32!RegGetValueW` at `0x14007b247`
- `ADVAPI32!RegGetValueW` at `0x14007b357`
- `ADVAPI32!RegGetValueW` at `0x14007b45c`
- `msvcrt!wcstoul` at `0x14007b6b1`
- `msvcrt!wcstoul` at `0x14007b6b1`
- `msvcrt!wcschr` at `0x14007b668`
- `msvcrt!wcschr` at `0x14007b668`
- `ole32!CoTaskMemAlloc` at `0x14007b131`
- `ole32!CoTaskMemAlloc` at `0x14007b3c7`
- `ole32!CoTaskMemAlloc` at `0x14007b5da`
- `ole32!CoTaskMemAlloc` at `0x14007b5eb`
- `ole32!CoTaskMemAlloc` at `0x14007b131`
- `ole32!CoTaskMemAlloc` at `0x14007b3c7`
- `ole32!CoTaskMemAlloc` at `0x14007b5da`
- `ole32!CoTaskMemAlloc` at `0x14007b5eb`
- `ole32!CoTaskMemFree` at `0x14007b1b2`
- `ole32!CoTaskMemFree` at `0x14007b1b2`
- `RPCRT4!UuidFromStringW` at `0x14007b68f`
- `RPCRT4!UuidFromStringW` at `0x14007b68f`

## string_xrefs

- `0x14007b0f5`: `base\stor\blb\engine\service\performancemanager.cpp`
- `0x14007b3b8`: `base\stor\blb\engine\service\performancemanager.cpp`
- `0x14007b4d3`: `base\stor\blb\engine\service\performancemanager.cpp`
- `0x14007b570`: `base\stor\blb\engine\service\performancemanager.cpp`
- `0x14007b654`: `base\stor\blb\engine\service\performancemanager.cpp`
- `0x14007b6ea`: `base\stor\blb\engine\service\performancemanager.cpp`

## pseudocode

```c
__int64 __fastcall CPerformanceManager::QueryPerformanceSettings(struct _BLB_PERFORMANCE_SETTINGS **a1)
{
  struct _BLB_PERFORMANCE_SETTINGS **v1; // r13
  struct _BLB_PERFORMANCE_SETTINGS *v2; // rax
  struct _BLB_PERFORMANCE_SETTINGS *v3; // rsi
  PVOID *v4; // rcx
  int ValueW; // ebx
  LSTATUS v7; // edi
  char *v8; // rax
  char *v9; // r14
  __int64 v10; // rdx
  LSTATUS v11; // edi
  PVOID *v12; // r10
  __int64 v13; // rdi
  int v14; // r15d
  __int64 v15; // r15
  LPVOID v16; // rax
  void *v17; // rcx
  unsigned int i; // r12d
  __int64 v19; // rdi
  wchar_t *v20; // rax
  wchar_t *v21; // rbx
  DWORD v22; // eax
  __int64 v23; // rcx
  DWORD pcbData[2]; // [rsp+40h] [rbp-28h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-20h]
  wchar_t *EndPtr; // [rsp+50h] [rbp-18h] BYREF
  DWORD pdwType; // [rsp+B8h] [rbp+50h] BYREF
  DWORD v29; // [rsp+C0h] [rbp+58h] BYREF
  unsigned int pvData; // [rsp+C8h] [rbp+60h] BYREF

  v1 = a1;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_9793dd91b374347cf06074f3d6f4ba29_Traceguids);
  }
  if ( !v1 )
    BlbAssert("base\\stor\\blb\\engine\\service\\performancemanager.cpp", 0x11Au, "ppPerformanceSettings");
  pdwType = 0;
  v29 = 0;
  pv = 0;
  pcbData[0] = 4;
  *v1 = 0;
  v2 = (struct _BLB_PERFORMANCE_SETTINGS *)CoTaskMemAlloc(0x18u);
  v3 = v2;
  if ( !v2 )
  {
    v4 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_9793dd91b374347cf06074f3d6f4ba29_Traceguids);
      v4 = (PVOID *)WPP_GLOBAL_Control;
    }
    ValueW = -2147024882;
    goto LABEL_13;
  }
  *(_QWORD *)v2 = 0;
  *((_QWORD *)v2 + 2) = 0;
  *((_QWORD *)v2 + 1) = 0;
  pvData = -1;
  ValueW = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"Software\\Microsoft\\Windows\\CurrentVersion\\Windows Block Level Backup",
             L"OverallPerformanceSetting",
             0x10u,
             &pdwType,
             &pvData,
             pcbData);
  if ( ValueW )
  {
    v4 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_9793dd91b374347cf06074f3d6f4ba29_Traceguids);
      v4 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( ValueW > 0 )
    {
      ValueW = (unsigned __int16)ValueW;
LABEL_30:
      ValueW |= 0x80070000;
    }
LABEL_13:
    if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 1) != 0 && *((_BYTE *)v4 + 25) >= 2u )
      WPP_SF_d(v4[2], 39, WPP_9793dd91b374347cf06074f3d6f4ba29_Traceguids);
LABEL_17:
    FreePerformanceSettings(v3);
    goto LABEL_18;
  }
  if ( pdwType != 4 )
    BlbAssert("base\\stor\\blb\\engine\\service\\performancemanager.cpp", 0x143u, "dwType == REG_DWORD");
  ValueW = CPerformanceManager::DWORDToPerformanceType(pvData, v3);
  if ( ValueW < 0 )
  {
    v4 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_9793dd91b374347cf06074f3d6f4ba29_Traceguids);
      v4 = (PVOID *)WPP_GLOBAL_Control;
    }
    goto LABEL_13;
  }
  if ( (unsigned int)(*(_DWORD *)v3 - 1) > 2 )
    BlbAssert(
      "base\\stor\\blb\\engine\\service\\performancemanager.cpp",
      0x14Eu,
      "(pPerformanceSettings->m_eOverallPerformanceSettingType == BLB_PST_ALWAYS_FULL) || (pPerformanceSettings->m_eOvera"
      "llPerformanceSettingType == BLB_PST_ALWAYS_INCREMENTAL) || (pPerformanceSettings->m_eOverallPerformanceSettingType"
      " == BLB_PST_CUSTOM)");
  v7 = RegGetValueW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\Windows Block Level Backup",
         L"CustomPerformanceSettings",
         0x20u,
         &pdwType,
         0,
         &v29);
  if ( v7 )
  {
    v4 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_9793dd91b374347cf06074f3d6f4ba29_Traceguids);
      v4 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v7 <= 0 )
    {
      ValueW = v7;
      goto LABEL_13;
    }
    ValueW = (unsigned __int16)v7;
    goto LABEL_30;
  }
  if ( pdwType != 7 )
    BlbAssert("base\\stor\\blb\\engine\\service\\performancemanager.cpp", 0x15Eu, "dwType == REG_MULTI_SZ");
  v8 = (char *)CoTaskMemAlloc(v29);
  pv = v8;
  v9 = v8;
  if ( !v8 )
  {
    v4 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_57;
    }
    v10 = 30;
LABEL_56:
    WPP_SF_(v4[2], v10, WPP_9793dd91b374347cf06074f3d6f4ba29_Traceguids);
    v4 = (PVOID *)WPP_GLOBAL_Control;
LABEL_57:
    ValueW = -2147024882;
    goto LABEL_13;
  }
  memset_0(v8, 0, v29);
  v11 = RegGetValueW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Windows\\CurrentVersion\\Windows Block Level Backup",
          L"CustomPerformanceSettings",
          0x20u,
          &pdwType,
          v9,
          &v29);
  if ( v11 )
  {
    v4 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_9793dd91b374347cf06074f3d6f4ba29_Traceguids);
      v4 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v11 > 0 )
      ValueW = (unsigned __int16)v11 | 0x80070000;
    else
      ValueW = v11;
    goto LABEL_13;
  }
  if ( pdwType != 7 )
    BlbAssert("base\\stor\\blb\\engine\\service\\performancemanager.cpp", 0x17Au, "dwType == REG_MULTI_SZ");
  v12 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_dS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      32,
      (unsigned int)WPP_9793dd91b374347cf06074f3d6f4ba29_Traceguids,
      v29,
      (__int64)v9);
    v12 = (PVOID *)WPP_GLOBAL_Control;
  }
  LODWORD(v13) = v29 >> 1;
  if ( v29 >> 1 != 2 )
  {
    v14 = 0;
    if ( *(_DWORD *)v3 != 3 )
    {
      BlbAssert(
        "base\\stor\\blb\\engine\\service\\performancemanager.cpp",
        0x18Au,
        "pPerformanceSettings->m_eOverallPerformanceSettingType == BLB_PST_CUSTOM");
      v12 = (PVOID *)WPP_GLOBAL_Control;
    }
    while ( (_DWORD)v13 )
    {
      v13 = (unsigned int)(v13 - 1);
      v14 += *(_WORD *)&v9[2 * v13] == 0;
    }
    v15 = (unsigned int)(v14 - 1);
    if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 1) != 0 && *((_BYTE *)v12 + 25) >= 4u )
      WPP_SF_d(v12[2], 34, WPP_9793dd91b374347cf06074f3d6f4ba29_Traceguids);
    *((_QWORD *)v3 + 2) = CoTaskMemAlloc(4 * v15);
    v16 = CoTaskMemAlloc(16LL * (unsigned int)v15);
    v17 = (void *)*((_QWORD *)v3 + 2);
    *((_QWORD *)v3 + 1) = v16;
    if ( v17 && v16 )
    {
      memset_0(v17, 0, 4 * v15);
      memset_0(*((void **)v3 + 1), 0, 16LL * (unsigned int)v15);
      *((_DWORD *)v3 + 1) = v15;
      for ( i = 0; ; ++i )
      {
        if ( i >= (unsigned int)v15 )
        {
          v1 = a1;
          goto LABEL_115;
        }
        v19 = -1;
        do
          ++v19;
        while ( *(_WORD *)&v9[2 * v19] );
        if ( !(_DWORD)v19 )
          BlbAssert("base\\stor\\blb\\engine\\service\\performancemanager.cpp", 0x1B0u, "dwLengthOfCurrentLine > 0");
        v20 = wcschr((const wchar_t *)v9, 0x2Cu);
        v21 = v20;
        if ( !v20 )
        {
          v4 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_9793dd91b374347cf06074f3d6f4ba29_Traceguids);
LABEL_112:
            v4 = (PVOID *)WPP_GLOBAL_Control;
          }
LABEL_113:
          ValueW = -2139619176;
          goto LABEL_13;
        }
        *v20 = 0;
        if ( UuidFromStringW((RPC_WSTR)v9, (UUID *)(*((_QWORD *)v3 + 1) + 16LL * i)) )
        {
          v4 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, WPP_9793dd91b374347cf06074f3d6f4ba29_Traceguids, v9);
            goto LABEL_112;
          }
          goto LABEL_113;
        }
        EndPtr = 0;
        v22 = wcstoul(v21 + 1, &EndPtr, 10);
        v23 = *((_QWORD *)v3 + 2);
        pcbData[1] = v22;
        ValueW = CPerformanceManager::DWORDToPerformanceType(v22, (enum _BLB_PERFORMANCE_SETTING_TYPE *)(v23 + 4LL * i));
        if ( ValueW < 0 )
          break;
        if ( (unsigned int)(*(_DWORD *)(*((_QWORD *)v3 + 2) + 4LL * i) - 1) > 1 )
          BlbAssert(
            "base\\stor\\blb\\engine\\service\\performancemanager.cpp",
            0x1D2u,
            "(pPerformanceSettings->m_rgePerformanceSettingType[i] == BLB_PST_ALWAYS_FULL) || (pPerformanceSettings->m_rg"
            "ePerformanceSettingType[i] == BLB_PST_ALWAYS_INCREMENTAL)");
        v9 += 2 * (unsigned int)(v19 + 1);
      }
      v4 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        goto LABEL_17;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, WPP_9793dd91b374347cf06074f3d6f4ba29_Traceguids);
        v4 = (PVOID *)WPP_GLOBAL_Control;
      }
      goto LABEL_13;
    }
    v4 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_57;
    }
    v10 = 35;
    goto LABEL_56;
  }
  if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 1) != 0 && *((_BYTE *)v12 + 25) >= 4u )
    WPP_SF_(v12[2], 33, WPP_9793dd91b374347cf06074f3d6f4ba29_Traceguids);
  ValueW = 0;
LABEL_115:
  *v1 = v3;
LABEL_18:
  CoTaskMemFree(pv);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, WPP_9793dd91b374347cf06074f3d6f4ba29_Traceguids);
  }
  return (unsigned int)ValueW;
}

```

## disassembly

```asm
0x14007b0a0  mov     [rsp-40h+arg_0], rcx
0x14007b0a5  push    rbp
0x14007b0a6  push    rbx
0x14007b0a7  push    rsi
0x14007b0a8  push    rdi
0x14007b0a9  push    r12
0x14007b0ab  push    r13
0x14007b0ad  push    r14
0x14007b0af  push    r15
0x14007b0b1  mov     rbp, rsp
0x14007b0b4  sub     rsp, 68h
0x14007b0b8  mov     r13, rcx
0x14007b0bb  mov     rcx, cs:WPP_GLOBAL_Control
0x14007b0c2  lea     r14, WPP_GLOBAL_Control
0x14007b0c9  lea     r15, WPP_9793dd91b374347cf06074f3d6f4ba29_Traceguids
0x14007b0d0  cmp     rcx, r14
0x14007b0d3  jz      short loc_14007B0F2
0x14007b0d5  test    byte ptr [rcx+1Ch], 1
0x14007b0d9  jz      short loc_14007B0F2
0x14007b0db  cmp     byte ptr [rcx+19h], 4
0x14007b0df  jb      short loc_14007B0F2
0x14007b0e1  mov     rcx, [rcx+10h]
0x14007b0e5  mov     edx, 19h
0x14007b0ea  mov     r8, r15
0x14007b0ed  call    WPP_SF_
0x14007b0f2  xor     r12d, r12d
0x14007b0f5  lea     rdi, aBaseStorBlbEng_34; "base\\stor\\blb\\engine\\service\\perfo"...
0x14007b0fc  test    r13, r13
0x14007b0ff  jnz     short loc_14007B115
0x14007b101  lea     r8, aPpperformances; "ppPerformanceSettings"
0x14007b108  mov     edx, 11Ah; unsigned int
0x14007b10d  mov     rcx, rdi; char *
0x14007b110  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x14007b115  mov     ecx, 18h; cb
0x14007b11a  mov     [rbp+arg_8], r12d
0x14007b11e  mov     [rbp+arg_10], r12d
0x14007b122  mov     [rbp+pv], r12
0x14007b126  mov     [rbp+var_28], 4
0x14007b12d  mov     [r13+0], r12
0x14007b131  call    cs:__imp_CoTaskMemAlloc
0x14007b137  mov     rsi, rax
0x14007b13a  test    rax, rax
0x14007b13d  jnz     loc_14007B1FF
0x14007b143  mov     rcx, cs:WPP_GLOBAL_Control
0x14007b14a  cmp     rcx, r14
0x14007b14d  jz      short loc_14007B171
0x14007b14f  test    byte ptr [rcx+1Ch], 1
0x14007b153  jz      short loc_14007B171
0x14007b155  cmp     byte ptr [rcx+19h], 2
0x14007b159  jb      short loc_14007B171
0x14007b15b  mov     rcx, [rcx+10h]
0x14007b15f  lea     edx, [rax+1Ah]
0x14007b162  mov     r8, r15
0x14007b165  call    WPP_SF_
0x14007b16a  mov     rcx, cs:WPP_GLOBAL_Control
0x14007b171  mov     ebx, 8007000Eh
0x14007b176  lea     r15, WPP_GLOBAL_Control
0x14007b17d  cmp     rcx, r15
0x14007b180  jz      short loc_14007B1A6
0x14007b182  test    byte ptr [rcx+1Ch], 1
0x14007b186  jz      short loc_14007B1A6
0x14007b188  cmp     byte ptr [rcx+19h], 2
0x14007b18c  jb      short loc_14007B1A6
0x14007b18e  mov     rcx, [rcx+10h]
0x14007b192  lea     r8, WPP_9793dd91b374347cf06074f3d6f4ba29_Traceguids
0x14007b199  mov     edx, 27h ; '''
0x14007b19e  mov     r9d, ebx
0x14007b1a1  call    WPP_SF_d
0x14007b1a6  mov     rcx, rsi; pv
0x14007b1a9  call    ?FreePerformanceSettings@@YAXPEAU_BLB_PERFORMANCE_SETTINGS@@@Z; FreePerformanceSettings(_BLB_PERFORMANCE_SETTINGS *)
0x14007b1ae  mov     rcx, [rbp+pv]; pv
0x14007b1b2  call    cs:__imp_CoTaskMemFree
0x14007b1b8  mov     rcx, cs:WPP_GLOBAL_Control
0x14007b1bf  lea     rax, WPP_GLOBAL_Control
0x14007b1c6  cmp     rcx, rax
0x14007b1c9  jz      short loc_14007B1EC
0x14007b1cb  test    byte ptr [rcx+1Ch], 1
0x14007b1cf  jz      short loc_14007B1EC
0x14007b1d1  cmp     byte ptr [rcx+19h], 4
0x14007b1d5  jb      short loc_14007B1EC
0x14007b1d7  mov     rcx, [rcx+10h]
0x14007b1db  lea     r8, WPP_9793dd91b374347cf06074f3d6f4ba29_Traceguids
0x14007b1e2  mov     edx, 28h ; '('
0x14007b1e7  call    WPP_SF_
0x14007b1ec  mov     eax, ebx
0x14007b1ee  add     rsp, 68h
0x14007b1f2  pop     r15
0x14007b1f4  pop     r14
0x14007b1f6  pop     r13
0x14007b1f8  pop     r12
0x14007b1fa  pop     rdi
0x14007b1fb  pop     rsi
0x14007b1fc  pop     rbx
0x14007b1fd  pop     rbp
0x14007b1fe  retn
0x14007b1ff  mov     [rax], r12
0x14007b202  lea     r8, Value; "OverallPerformanceSetting"
0x14007b209  mov     [rax+10h], r12
0x14007b20d  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Windows\\CurrentVe"...
0x14007b214  mov     [rax+8], r12
0x14007b218  mov     r9d, 10h; dwFlags
0x14007b21e  lea     rax, [rbp+var_28]
0x14007b222  mov     [rbp+arg_18], 0FFFFFFFFh
0x14007b229  mov     [rsp+68h+pcbData], rax; pcbData
0x14007b22e  mov     rcx, 0FFFFFFFF80000002h; hkey
0x14007b235  lea     rax, [rbp+arg_18]
0x14007b239  mov     [rsp+68h+pvData], rax; pvData
0x14007b23e  lea     rax, [rbp+arg_8]
0x14007b242  mov     [rsp+68h+pdwType], rax; pdwType
0x14007b247  call    cs:__imp_RegGetValueW
0x14007b24d  mov     ebx, eax
0x14007b24f  test    eax, eax
0x14007b251  jz      short loc_14007B29C
0x14007b253  mov     rcx, cs:WPP_GLOBAL_Control
0x14007b25a  cmp     rcx, r14
0x14007b25d  jz      short loc_14007B283
0x14007b25f  test    byte ptr [rcx+1Ch], 1
0x14007b263  jz      short loc_14007B283
0x14007b265  cmp     byte ptr [rcx+19h], 2
0x14007b269  jb      short loc_14007B283
0x14007b26b  mov     rcx, [rcx+10h]
0x14007b26f  mov     edx, 1Bh
0x14007b274  mov     r8, r15
0x14007b277  call    WPP_SF_
0x14007b27c  mov     rcx, cs:WPP_GLOBAL_Control
0x14007b283  test    ebx, ebx
0x14007b285  jle     short loc_14007B290
0x14007b287  movzx   ebx, bx
0x14007b28a  or      ebx, 80070000h
0x14007b290  lea     r15, WPP_GLOBAL_Control
0x14007b297  jmp     loc_14007B4B4
0x14007b29c  cmp     [rbp+arg_8], 4
0x14007b2a0  jz      short loc_14007B2B6
0x14007b2a2  lea     r8, aDwtypeRegDword; "dwType == REG_DWORD"
0x14007b2a9  mov     edx, 143h; unsigned int
0x14007b2ae  mov     rcx, rdi; char *
0x14007b2b1  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x14007b2b6  mov     ecx, [rbp+arg_18]; unsigned int
0x14007b2b9  mov     rdx, rsi; enum _BLB_PERFORMANCE_SETTING_TYPE *
0x14007b2bc  call    ?DWORDToPerformanceType@CPerformanceManager@@SAJKPEAW4_BLB_PERFORMANCE_SETTING_TYPE@@@Z; CPerformanceManager::DWORDToPerformanceType(ulong,_BLB_PERFORMANCE_SETTING_TYPE *)
0x14007b2c1  mov     ebx, eax
0x14007b2c3  test    eax, eax
0x14007b2c5  jns     short loc_14007B308
0x14007b2c7  mov     rcx, cs:WPP_GLOBAL_Control
0x14007b2ce  cmp     rcx, r14
0x14007b2d1  jz      loc_14007B176
0x14007b2d7  test    byte ptr [rcx+1Ch], 1
0x14007b2db  jz      loc_14007B176
0x14007b2e1  cmp     byte ptr [rcx+19h], 2
0x14007b2e5  jb      loc_14007B176
0x14007b2eb  mov     rcx, [rcx+10h]
0x14007b2ef  mov     edx, 1Ch
0x14007b2f4  mov     r8, r15
0x14007b2f7  call    WPP_SF_
0x14007b2fc  mov     rcx, cs:WPP_GLOBAL_Control
0x14007b303  jmp     loc_14007B176
0x14007b308  mov     eax, [rsi]
0x14007b30a  dec     eax
0x14007b30c  cmp     eax, 2
0x14007b30f  jbe     short loc_14007B325
0x14007b311  lea     r8, aPperformancese; "(pPerformanceSettings->m_eOverallPerfor"...
0x14007b318  mov     edx, 14Eh; unsigned int
0x14007b31d  mov     rcx, rdi; char *
0x14007b320  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x14007b325  lea     rax, [rbp+arg_10]
0x14007b329  mov     r9d, 20h ; ' '; dwFlags
0x14007b32f  mov     [rsp+68h+pcbData], rax; pcbData
0x14007b334  lea     r8, aCustomperforma; "CustomPerformanceSettings"
0x14007b33b  lea     rax, [rbp+arg_8]
0x14007b33f  mov     [rsp+68h+pvData], r12; pvData
0x14007b344  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Windows\\CurrentVe"...
0x14007b34b  mov     [rsp+68h+pdwType], rax; pdwType
0x14007b350  mov     rcx, 0FFFFFFFF80000002h; hkey
0x14007b357  call    cs:__imp_RegGetValueW
0x14007b35d  mov     edi, eax
0x14007b35f  test    eax, eax
0x14007b361  jz      short loc_14007B3A6
0x14007b363  mov     rcx, cs:WPP_GLOBAL_Control
0x14007b36a  cmp     rcx, r14
0x14007b36d  jz      short loc_14007B393
0x14007b36f  test    byte ptr [rcx+1Ch], 1
0x14007b373  jz      short loc_14007B393
0x14007b375  cmp     byte ptr [rcx+19h], 2
0x14007b379  jb      short loc_14007B393
0x14007b37b  mov     rcx, [rcx+10h]
0x14007b37f  mov     edx, 1Dh
0x14007b384  mov     r8, r15
0x14007b387  call    WPP_SF_
0x14007b38c  mov     rcx, cs:WPP_GLOBAL_Control
0x14007b393  test    edi, edi
0x14007b395  jg      short loc_14007B39E
0x14007b397  mov     ebx, edi
0x14007b399  jmp     loc_14007B290
0x14007b39e  movzx   ebx, di
0x14007b3a1  jmp     loc_14007B28A
0x14007b3a6  cmp     [rbp+arg_8], 7
0x14007b3aa  jz      short loc_14007B3C4
0x14007b3ac  lea     r8, aDwtypeRegMulti; "dwType == REG_MULTI_SZ"
0x14007b3b3  mov     edx, 15Eh; unsigned int
0x14007b3b8  lea     rcx, aBaseStorBlbEng_34; "base\\stor\\blb\\engine\\service\\perfo"...
0x14007b3bf  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x14007b3c4  mov     ecx, [rbp+arg_10]; cb
0x14007b3c7  call    cs:__imp_CoTaskMemAlloc
0x14007b3cd  mov     [rbp+pv], rax
0x14007b3d1  mov     r14, rax
0x14007b3d4  test    rax, rax
0x14007b3d7  jnz     short loc_14007B41C
0x14007b3d9  mov     rcx, cs:WPP_GLOBAL_Control
0x14007b3e0  lea     r15, WPP_GLOBAL_Control
0x14007b3e7  cmp     rcx, r15
0x14007b3ea  jz      short loc_14007B412
0x14007b3ec  test    byte ptr [rcx+1Ch], 1
0x14007b3f0  jz      short loc_14007B412
0x14007b3f2  cmp     byte ptr [rcx+19h], 2
0x14007b3f6  jb      short loc_14007B412
0x14007b3f8  lea     edx, [rax+1Eh]
0x14007b3fb  mov     rcx, [rcx+10h]
0x14007b3ff  lea     r8, WPP_9793dd91b374347cf06074f3d6f4ba29_Traceguids
0x14007b406  call    WPP_SF_
0x14007b40b  mov     rcx, cs:WPP_GLOBAL_Control
0x14007b412  mov     ebx, 8007000Eh
0x14007b417  jmp     loc_14007B17D
0x14007b41c  mov     r8d, [rbp+arg_10]; Size
0x14007b420  xor     edx, edx; Val
0x14007b422  mov     rcx, r14; void *
0x14007b425  call    memset_0
0x14007b42a  lea     rax, [rbp+arg_10]
0x14007b42e  mov     r9d, 20h ; ' '; dwFlags
0x14007b434  mov     [rsp+68h+pcbData], rax; pcbData
0x14007b439  lea     r8, aCustomperforma; "CustomPerformanceSettings"
0x14007b440  lea     rax, [rbp+arg_8]
0x14007b444  mov     [rsp+68h+pvData], r14; pvData
0x14007b449  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Windows\\CurrentVe"...
0x14007b450  mov     [rsp+68h+pdwType], rax; pdwType
0x14007b455  mov     rcx, 0FFFFFFFF80000002h; hkey
0x14007b45c  call    cs:__imp_RegGetValueW
0x14007b462  mov     edi, eax
0x14007b464  test    eax, eax
0x14007b466  jz      short loc_14007B4C1
0x14007b468  mov     rcx, cs:WPP_GLOBAL_Control
0x14007b46f  lea     r15, WPP_GLOBAL_Control
0x14007b476  cmp     rcx, r15
0x14007b479  jz      short loc_14007B4A3
0x14007b47b  test    byte ptr [rcx+1Ch], 1
0x14007b47f  jz      short loc_14007B4A3
0x14007b481  cmp     byte ptr [rcx+19h], 2
0x14007b485  jb      short loc_14007B4A3
0x14007b487  mov     rcx, [rcx+10h]
0x14007b48b  lea     r8, WPP_9793dd91b374347cf06074f3d6f4ba29_Traceguids
0x14007b492  mov     edx, 1Fh
0x14007b497  call    WPP_SF_
0x14007b49c  mov     rcx, cs:WPP_GLOBAL_Control
0x14007b4a3  test    edi, edi
0x14007b4a5  jg      short loc_14007B4AB
0x14007b4a7  mov     ebx, edi
0x14007b4a9  jmp     short loc_14007B4B4
0x14007b4ab  movzx   ebx, di
0x14007b4ae  or      ebx, 80070000h
0x14007b4b4  test    ebx, ebx
0x14007b4b6  jns     loc_14007B7DA
0x14007b4bc  jmp     loc_14007B17D
0x14007b4c1  cmp     [rbp+arg_8], 7
0x14007b4c5  jz      short loc_14007B4DF
0x14007b4c7  lea     r8, aDwtypeRegMulti; "dwType == REG_MULTI_SZ"
0x14007b4ce  mov     edx, 17Ah; unsigned int
0x14007b4d3  lea     rcx, aBaseStorBlbEng_34; "base\\stor\\blb\\engine\\service\\perfo"...
0x14007b4da  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x14007b4df  mov     r10, cs:WPP_GLOBAL_Control
0x14007b4e6  lea     rax, WPP_GLOBAL_Control
0x14007b4ed  cmp     r10, rax
0x14007b4f0  jz      short loc_14007B528
0x14007b4f2  test    byte ptr [r10+1Ch], 1
0x14007b4f7  jz      short loc_14007B528
0x14007b4f9  cmp     byte ptr [r10+19h], 4
0x14007b4fe  jb      short loc_14007B528
0x14007b500  mov     r9d, [rbp+arg_10]
0x14007b504  mov     edx, 20h ; ' '
0x14007b509  mov     rcx, [r10+10h]
0x14007b50d  mov     r8, r15
0x14007b510  mov     [rsp+68h+pdwType], r14
0x14007b515  call    WPP_SF_dS
0x14007b51a  mov     r10, cs:WPP_GLOBAL_Control
0x14007b521  lea     rax, WPP_GLOBAL_Control
0x14007b528  mov     edi, [rbp+arg_10]
0x14007b52b  shr     edi, 1
0x14007b52d  cmp     edi, 2
0x14007b530  jnz     short loc_14007B55C
0x14007b532  cmp     r10, rax
0x14007b535  jz      short loc_14007B554
0x14007b537  test    byte ptr [r10+1Ch], 1
0x14007b53c  jz      short loc_14007B554
0x14007b53e  cmp     byte ptr [r10+19h], 4
0x14007b543  jb      short loc_14007B554
0x14007b545  mov     rcx, [r10+10h]
0x14007b549  lea     edx, [rdi+1Fh]
0x14007b54c  mov     r8, r15
0x14007b54f  call    WPP_SF_
0x14007b554  mov     ebx, r12d
0x14007b557  jmp     loc_14007B7DA
0x14007b55c  cmp     dword ptr [rsi], 3
  ... truncated ...
```
