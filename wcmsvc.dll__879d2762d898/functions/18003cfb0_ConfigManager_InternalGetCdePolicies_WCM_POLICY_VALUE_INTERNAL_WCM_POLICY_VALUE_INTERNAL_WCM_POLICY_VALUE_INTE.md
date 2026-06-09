# ConfigManager::InternalGetCdePolicies(WCM_POLICY_VALUE_INTERNAL *,WCM_POLICY_VALUE_INTERNAL *,WCM_POLICY_VALUE_INTERNAL *,WCM_POLICY_VALUE_INTERNAL *)

- ea: `0x18003cfb0`
- end: `0x18003d732`
- name: `?InternalGetCdePolicies@ConfigManager@@AEAAXPEAUWCM_POLICY_VALUE_INTERNAL@@000@Z`
- size: `1922`
- prototype: `void __fastcall(ConfigManager *__hidden this, struct WCM_POLICY_VALUE_INTERNAL *, struct WCM_POLICY_VALUE_INTERNAL *, struct WCM_POLICY_VALUE_INTERNAL *, struct WCM_POLICY_VALUE_INTERNAL *)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002ec10`
- `0x18003cf28`

## callees

- `0x1800137a0`
- `0x180019434`
- `0x18001b970`
- `0x18001c11c`
- `0x180024df0`
- `0x1800277c0`
- `0x18003cfb0`
- `0x180084f50`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003d026`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003d026`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003d6f2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003d6f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d169`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d33f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d169`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d33f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003d17c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003d352`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003d17c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003d352`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003d134`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003d1da`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003d4f8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003d134`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003d1da`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003d4f8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003d174`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003d34a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003d174`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003d34a`
- `api-ms-win-core-state-helpers-l1-1-0!GetRegistryValueWithFallbackW` at `0x18003d30a`
- `api-ms-win-core-state-helpers-l1-1-0!GetRegistryValueWithFallbackW` at `0x18003d3b7`
- `api-ms-win-core-state-helpers-l1-1-0!GetRegistryValueWithFallbackW` at `0x18003d30a`
- `api-ms-win-core-state-helpers-l1-1-0!GetRegistryValueWithFallbackW` at `0x18003d3b7`

## string_xrefs

- `0x18003d71f`: `onecore\private\net\inc\wcm\wcm_registry_key.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ConfigManager::InternalGetCdePolicies(
        ConfigManager *this,
        struct WCM_POLICY_VALUE_INTERNAL *a2,
        struct WCM_POLICY_VALUE_INTERNAL *a3,
        struct WCM_POLICY_VALUE_INTERNAL *a4,
        struct WCM_POLICY_VALUE_INTERNAL *a5)
{
  ConfigManager *v8; // rcx
  unsigned __int64 v9; // r13
  unsigned int *v10; // r12
  const WCHAR **v11; // rbx
  const WCHAR *v12; // r15
  LSTATUS ValueW; // eax
  ConfigManager *v14; // rcx
  signed int v15; // edi
  HKEY v16; // rsi
  DWORD LastError; // ebx
  LSTATUS v18; // eax
  __int64 v19; // rax
  unsigned int v20; // ecx
  int v21; // edx
  const WCHAR *v22; // r9
  int RegistryValueWithFallbackW; // eax
  ConfigManager *v24; // rcx
  signed int v25; // edi
  HKEY v26; // rsi
  DWORD v27; // ebx
  int v28; // eax
  int v29; // eax
  __int64 v30; // r9
  DWORD *v31; // rbx
  struct WCM_POLICY_VALUE_INTERNAL *v32; // rdx
  struct WCM_POLICY_VALUE_INTERNAL *v33; // r8
  unsigned int *v34; // r9
  __int64 *v35; // rbp
  __int64 v36; // rcx
  __int64 *v37; // rdx
  __int64 v38; // [rsp+0h] [rbp-178h] BYREF
  LPDWORD pdwType; // [rsp+20h] [rbp-158h]
  struct WCM_POLICY_VALUE_INTERNAL *v40; // [rsp+50h] [rbp-128h] BYREF
  struct WCM_POLICY_VALUE_INTERNAL *v41; // [rsp+58h] [rbp-120h] BYREF
  struct WCM_POLICY_VALUE_INTERNAL *v42; // [rsp+60h] [rbp-118h]
  struct WCM_POLICY_VALUE_INTERNAL *v43; // [rsp+68h] [rbp-110h]
  __int64 v44; // [rsp+70h] [rbp-108h] BYREF
  __int64 v45; // [rsp+78h] [rbp-100h] BYREF
  __int64 v46; // [rsp+80h] [rbp-F8h]
  struct WCM_POLICY_VALUE_INTERNAL *v47; // [rsp+88h] [rbp-F0h]
  struct WCM_POLICY_VALUE_INTERNAL *v48; // [rsp+90h] [rbp-E8h]
  struct WCM_POLICY_VALUE_INTERNAL *v49; // [rsp+98h] [rbp-E0h]
  struct _RTL_CRITICAL_SECTION *v50; // [rsp+A0h] [rbp-D8h]
  unsigned int pvData; // [rsp+A8h] [rbp-D0h] BYREF
  DWORD pcbData; // [rsp+ACh] [rbp-CCh] BYREF
  struct _EVENT_DATA_DESCRIPTOR v53; // [rsp+B0h] [rbp-C8h] BYREF
  _QWORD v54[2]; // [rsp+C0h] [rbp-B8h]
  __int64 *v55; // [rsp+D0h] [rbp-A8h]
  __int64 v56; // [rsp+D8h] [rbp-A0h]
  struct WCM_POLICY_VALUE_INTERNAL **v57; // [rsp+E0h] [rbp-98h]
  __int64 v58; // [rsp+E8h] [rbp-90h]
  struct WCM_POLICY_VALUE_INTERNAL **v59; // [rsp+F0h] [rbp-88h]
  __int64 v60; // [rsp+F8h] [rbp-80h]
  unsigned int *p_pvData; // [rsp+100h] [rbp-78h]
  __int64 v62; // [rsp+108h] [rbp-70h]
  DWORD *p_pcbData; // [rsp+110h] [rbp-68h]
  __int64 v64; // [rsp+118h] [rbp-60h]
  __int64 *v65; // [rsp+120h] [rbp-58h]
  __int64 v66; // [rsp+128h] [rbp-50h]
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+0h]

  v43 = a4;
  v42 = a3;
  v40 = a2;
  v48 = a2;
  v49 = a3;
  v44 = (__int64)a4;
  v41 = a5;
  v45 = (__int64)a5;
  v47 = a5;
  EnterCriticalSection(&s_keyLock);
  v50 = &s_keyLock;
  ConfigManager::InternalInit(v8);
  v53.Ptr = (ULONGLONG)L"fMinimizeConnections";
  v53.Size = 2;
  v54[0] = a2;
  v54[1] = L"fBlockRoaming";
  LODWORD(v55) = 0;
  v56 = (__int64)a3;
  v57 = (struct WCM_POLICY_VALUE_INTERNAL **)L"fDisablePowerManagement";
  LODWORD(v58) = 0;
  v59 = (struct WCM_POLICY_VALUE_INTERNAL **)a4;
  *(_QWORD *)a5 = 0;
  v46 = 0;
  v9 = 0;
  do
  {
    v10 = (unsigned int *)v54[v9 / 8];
    *v10 = *(ULONG *)((char *)&v53.Size + v9);
    v10[1] = 0;
    v11 = (const WCHAR **)((char *)&v53 + v9);
    if ( s_wcmGroupPolicyKey )
    {
      pvData = 0;
      v12 = *v11;
      pcbData = 4;
      ValueW = RegGetValueW(s_wcmGroupPolicyKey, 0, v12, 0x10u, 0, &pvData, &pcbData);
      v15 = ValueW;
      if ( ValueW > 0 )
        v15 = (unsigned __int16)ValueW | 0x80070000;
      if ( v15 >= 0 )
        goto LABEL_18;
      if ( v15 != -2147024894 )
      {
        v16 = s_wcmGroupPolicyKey;
        if ( s_wcmGroupPolicyKey )
        {
          LastError = GetLastError();
          RegCloseKey(v16);
          SetLastError(LastError);
          v11 = (const WCHAR **)((char *)&v53 + v9);
        }
        s_wcmGroupPolicyKey = 0;
        ConfigManager::InternalInit(v14);
        if ( s_wcmGroupPolicyKey )
        {
          pcbData = 4;
          v18 = RegGetValueW(s_wcmGroupPolicyKey, 0, v12, 0x10u, 0, &pvData, &pcbData);
          v15 = v18;
          if ( v18 > 0 )
            v15 = (unsigned __int16)v18 | 0x80070000;
          if ( v15 >= 0 )
          {
LABEL_18:
            *v10 = pvData;
            LOBYTE(v20) = pvData;
            v10[1] = 1;
            v19 = WPP_GLOBAL_Control;
            if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 4u
              && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
            {
              v21 = 21;
              goto LABEL_22;
            }
            goto LABEL_48;
          }
        }
      }
      v19 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 4u
        && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        WPP_SF_Sd(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          20,
          (unsigned int)WPP_d1926522bc273c8e7056db3405527a30_Traceguids,
          (_DWORD)v12,
          v15);
        v19 = WPP_GLOBAL_Control;
      }
    }
    else
    {
      v19 = WPP_GLOBAL_Control;
    }
    if ( !s_wcmLocalPolicyKey )
      goto LABEL_40;
    pvData = 0;
    v12 = *v11;
    RegistryValueWithFallbackW = GetRegistryValueWithFallbackW(
                                   s_wcmLocalPolicyKey,
                                   0,
                                   -2147483646,
                                   L"Software\\Policies\\Microsoft\\Windows\\WcmSvc\\Local",
                                   *v11,
                                   16,
                                   0,
                                   &pvData,
                                   4,
                                   0);
    v25 = RegistryValueWithFallbackW;
    if ( RegistryValueWithFallbackW > 0 )
      v25 = (unsigned __int16)RegistryValueWithFallbackW | 0x80070000;
    if ( v25 < 0 )
    {
      if ( v25 == -2147024894 )
        goto LABEL_36;
      v26 = s_wcmLocalPolicyKey;
      if ( s_wcmLocalPolicyKey )
      {
        v27 = GetLastError();
        RegCloseKey(v26);
        SetLastError(v27);
        v11 = (const WCHAR **)((char *)&v53 + v9);
      }
      s_wcmLocalPolicyKey = 0;
      ConfigManager::InternalInit(v24);
      if ( !s_wcmLocalPolicyKey )
        goto LABEL_36;
      v28 = GetRegistryValueWithFallbackW(
              s_wcmLocalPolicyKey,
              0,
              -2147483646,
              L"Software\\Policies\\Microsoft\\Windows\\WcmSvc\\Local",
              v12,
              16,
              0,
              &pvData,
              4,
              0);
      v25 = v28;
      if ( v28 > 0 )
        v25 = (unsigned __int16)v28 | 0x80070000;
      if ( v25 < 0 )
      {
LABEL_36:
        v19 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
          goto LABEL_48;
        if ( *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 4u && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        {
          WPP_SF_Sd(
            *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
            22,
            (unsigned int)WPP_d1926522bc273c8e7056db3405527a30_Traceguids,
            (_DWORD)v12,
            v25);
          v19 = WPP_GLOBAL_Control;
        }
LABEL_40:
        if ( (_UNKNOWN *)v19 != &WPP_GLOBAL_Control && *(_BYTE *)(v19 + 25) >= 4u && (*(_BYTE *)(v19 + 28) & 1) != 0 )
        {
          v21 = 24;
          v20 = *v10;
          v22 = *v11;
          goto LABEL_23;
        }
        goto LABEL_48;
      }
    }
    *v10 = pvData;
    LOBYTE(v20) = pvData;
    v10[1] = 0;
    v19 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 4u
      && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v21 = 23;
LABEL_22:
      LODWORD(v22) = (_DWORD)v12;
LABEL_23:
      WPP_SF_Sd(
        *(_QWORD *)(v19 + 16),
        v21,
        (unsigned int)WPP_d1926522bc273c8e7056db3405527a30_Traceguids,
        (_DWORD)v22,
        v20);
      v19 = WPP_GLOBAL_Control;
    }
LABEL_48:
    ++v46;
    v9 += 24LL;
  }
  while ( v46 != 3 );
  if ( s_wcmRootKey )
  {
    pvData = 0;
    pcbData = 4;
    v29 = RegGetValueW(s_wcmRootKey, 0, L"fDisableMinimizePolicy", 0x10u, 0, &pvData, &pcbData);
    if ( v29 > 0 )
      v29 = (unsigned __int16)v29 | 0x80070000;
    if ( v29 < 0 )
    {
      try
      {
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x174,
          (unsigned int)"onecore\\private\\net\\inc\\wcm\\wcm_registry_key.h",
          (const char *)(unsigned int)v29,
          (int)pdwType);
      }
      catch ( std::exception )
      {
        v37 = &v38;
        v35 = v37;
        v36 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *(_BYTE *)(v36 + 25) >= 4u
          && (*(_BYTE *)(v36 + 28) & 1) != 0 )
        {
          WPP_SF_d(*(_QWORD *)(v36 + 16), 26, WPP_d1926522bc273c8e7056db3405527a30_Traceguids, *(unsigned int *)v35[17]);
        }
        v32 = v48;
        v33 = v49;
        v34 = (unsigned int *)v44;
        v31 = (DWORD *)v45;
        goto LABEL_64;
      }
    }
    v30 = pvData;
    v31 = (DWORD *)v41;
    *(_DWORD *)v41 = pvData;
    v31[1] = 0;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 4u
      && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 25, WPP_d1926522bc273c8e7056db3405527a30_Traceguids, v30);
    }
  }
  else
  {
    if ( (_UNKNOWN *)v19 != &WPP_GLOBAL_Control && *(_BYTE *)(v19 + 25) >= 2u && (*(_BYTE *)(v19 + 28) & 1) != 0 )
      WPP_SF_(*(_QWORD *)(v19 + 16), 27, WPP_d1926522bc273c8e7056db3405527a30_Traceguids);
    v31 = (DWORD *)v41;
  }
  v32 = v40;
  v33 = v42;
  v34 = (unsigned int *)v43;
LABEL_64:
  if ( (unsigned int)dword_18013A120 > 5
    && (qword_18013A130 & 0x400000000000LL) != 0
    && (qword_18013A138 & 0x400000000000LL) == qword_18013A138 )
  {
    v45 = 2048;
    pcbData = *v31;
    pvData = *v34;
    LODWORD(v40) = *(_DWORD *)v33;
    LODWORD(v41) = *(_DWORD *)v32;
    v44 = 1;
    v65 = &v45;
    v66 = 8;
    p_pcbData = &pcbData;
    v64 = 4;
    p_pvData = &pvData;
    v62 = 4;
    v59 = &v40;
    v60 = 4;
    v57 = &v41;
    v58 = 4;
    v55 = &v44;
    v56 = 8;
    tlgWriteAgg((int)&dword_18013A120, (int)&byte_18011DECF, 0, 8, &v53);
  }
  LeaveCriticalSection(&s_keyLock);
}

```

## disassembly

```asm
0x18003cfb0  push    rbx
0x18003cfb2  push    rsi
0x18003cfb3  push    rdi
0x18003cfb4  push    r12
0x18003cfb6  push    r13
0x18003cfb8  push    r14
0x18003cfba  push    r15
0x18003cfbc  sub     rsp, 140h
0x18003cfc3  mov     rax, cs:__security_cookie
0x18003cfca  xor     rax, rsp
0x18003cfcd  mov     [rsp+178h+var_48], rax
0x18003cfd5  mov     r12, r9
0x18003cfd8  mov     [rsp+178h+var_110], r9
0x18003cfdd  mov     r15, r8
0x18003cfe0  mov     [rsp+178h+var_118], r8
0x18003cfe5  mov     rsi, rdx
0x18003cfe8  mov     [rsp+178h+var_128], rdx
0x18003cfed  mov     [rsp+178h+var_E8], rdx
0x18003cff5  mov     [rsp+178h+var_E0], r8
0x18003cffd  mov     [rsp+178h+var_108], r9
0x18003d002  mov     rbx, [rsp+178h+arg_20]
0x18003d00a  mov     [rsp+178h+var_120], rbx
0x18003d00f  mov     [rsp+178h+var_100], rbx
0x18003d014  mov     [rsp+178h+var_F0], rbx
0x18003d01c  lea     rdi, ?s_keyLock@@3Vcritical_section@wil@@A; wil::critical_section s_keyLock
0x18003d023  mov     rcx, rdi; lpCriticalSection
0x18003d026  call    cs:__imp_EnterCriticalSection
0x18003d02c  mov     [rsp+178h+var_D8], rdi
0x18003d034  call    ?InternalInit@ConfigManager@@AEAAXXZ; ConfigManager::InternalInit(void)
0x18003d039  lea     rax, aFminimizeconne; "fMinimizeConnections"
0x18003d040  mov     [rsp+178h+var_C8.Ptr], rax
0x18003d048  mov     [rsp+178h+var_C8.Size], 2
0x18003d053  mov     [rsp+178h+var_B8], rsi
0x18003d05b  lea     rax, aFblockroaming; "fBlockRoaming"
0x18003d062  mov     [rsp+178h+var_B0], rax
0x18003d06a  xor     r14d, r14d
0x18003d06d  mov     dword ptr [rsp+178h+var_A8], r14d
0x18003d075  mov     [rsp+178h+var_A0], r15
0x18003d07d  lea     rax, aFdisablepowerm; "fDisablePowerManagement"
0x18003d084  mov     [rsp+178h+var_98], rax
0x18003d08c  mov     dword ptr [rsp+178h+var_90], r14d
0x18003d094  mov     [rsp+178h+var_88], r12
0x18003d09c  xor     eax, eax
0x18003d09e  mov     [rbx], rax
0x18003d0a1  mov     [rsp+178h+var_F8], r14
0x18003d0a9  mov     r13d, r14d
0x18003d0ac  lea     rdi, WPP_GLOBAL_Control
0x18003d0b3  nop     dword ptr [rax+00h]
0x18003d0b7  nop     word ptr [rax+rax+00000000h]
0x18003d0c0  mov     r12, [rsp+r13+178h+var_B8]
0x18003d0c8  mov     eax, [rsp+r13+178h+var_C8.Size]
0x18003d0d0  mov     [r12], eax
0x18003d0d4  mov     [r12+4], r14d
0x18003d0d9  mov     rcx, cs:?s_wcmGroupPolicyKey@@3VKey@Registry@WcmCommon@@A; hkey
0x18003d0e0  lea     rbx, [rsp+178h+var_C8]
0x18003d0e8  add     rbx, r13
0x18003d0eb  test    rcx, rcx
0x18003d0ee  jz      loc_18003D2AC
0x18003d0f4  mov     [rsp+178h+var_D0], r14d
0x18003d0fc  mov     r15, [rbx]
0x18003d0ff  mov     [rsp+178h+var_CC], 4
0x18003d10a  lea     rax, [rsp+178h+var_CC]
0x18003d112  mov     [rsp+178h+pcbData], rax; pcbData
0x18003d117  lea     rax, [rsp+178h+var_D0]
0x18003d11f  mov     [rsp+178h+pvData], rax; pvData
0x18003d124  mov     [rsp+178h+pdwType], r14; pdwType
0x18003d129  mov     r9d, 10h; dwFlags
0x18003d12f  mov     r8, r15; lpValue
0x18003d132  xor     edx, edx; lpSubKey
0x18003d134  call    cs:__imp_RegGetValueW
0x18003d13a  mov     edi, eax
0x18003d13c  test    eax, eax
0x18003d13e  jle     short loc_18003D149
0x18003d140  movzx   edi, ax
0x18003d143  or      edi, 80070000h
0x18003d149  test    edi, edi
0x18003d14b  jns     loc_18003D23E
0x18003d151  cmp     edi, 80070002h
0x18003d157  jz      loc_18003D1F3
0x18003d15d  mov     rsi, cs:?s_wcmGroupPolicyKey@@3VKey@Registry@WcmCommon@@A; WcmCommon::Registry::Key s_wcmGroupPolicyKey
0x18003d164  test    rsi, rsi
0x18003d167  jz      short loc_18003D18D
0x18003d169  call    cs:__imp_GetLastError
0x18003d16f  mov     ebx, eax
0x18003d171  mov     rcx, rsi; hKey
0x18003d174  call    cs:__imp_RegCloseKey
0x18003d17a  mov     ecx, ebx; dwErrCode
0x18003d17c  call    cs:__imp_SetLastError
0x18003d182  lea     rbx, [rsp+178h+var_C8]
0x18003d18a  add     rbx, r13
0x18003d18d  mov     cs:?s_wcmGroupPolicyKey@@3VKey@Registry@WcmCommon@@A, r14; WcmCommon::Registry::Key s_wcmGroupPolicyKey
0x18003d194  call    ?InternalInit@ConfigManager@@AEAAXXZ; ConfigManager::InternalInit(void)
0x18003d199  mov     rcx, cs:?s_wcmGroupPolicyKey@@3VKey@Registry@WcmCommon@@A; hkey
0x18003d1a0  test    rcx, rcx
0x18003d1a3  jz      short loc_18003D1F3
0x18003d1a5  mov     [rsp+178h+var_CC], 4
0x18003d1b0  lea     rax, [rsp+178h+var_CC]
0x18003d1b8  mov     [rsp+178h+pcbData], rax; pcbData
0x18003d1bd  lea     rax, [rsp+178h+var_D0]
0x18003d1c5  mov     [rsp+178h+pvData], rax; pvData
0x18003d1ca  mov     [rsp+178h+pdwType], r14; pdwType
0x18003d1cf  mov     r9d, 10h; dwFlags
0x18003d1d5  mov     r8, r15; lpValue
0x18003d1d8  xor     edx, edx; lpSubKey
0x18003d1da  call    cs:__imp_RegGetValueW
0x18003d1e0  mov     edi, eax
0x18003d1e2  test    eax, eax
0x18003d1e4  jle     short loc_18003D1EF
0x18003d1e6  movzx   edi, ax
0x18003d1e9  or      edi, 80070000h
0x18003d1ef  test    edi, edi
0x18003d1f1  jns     short loc_18003D23E
0x18003d1f3  mov     rax, cs:WPP_GLOBAL_Control
0x18003d1fa  lea     rcx, WPP_GLOBAL_Control
0x18003d201  cmp     rax, rcx
0x18003d204  jz      short loc_18003D235
0x18003d206  cmp     byte ptr [rax+19h], 4
0x18003d20a  jb      short loc_18003D235
0x18003d20c  test    byte ptr [rax+1Ch], 1
0x18003d210  jz      short loc_18003D235
0x18003d212  mov     edx, 14h
0x18003d217  mov     dword ptr [rsp+178h+pdwType], edi
0x18003d21b  mov     r9, r15
0x18003d21e  lea     r8, WPP_d1926522bc273c8e7056db3405527a30_Traceguids
0x18003d225  mov     rcx, [rax+10h]
0x18003d229  call    WPP_SF_Sd
0x18003d22e  mov     rax, cs:WPP_GLOBAL_Control
0x18003d235  lea     rdi, WPP_GLOBAL_Control
0x18003d23c  jmp     short loc_18003D2B3
0x18003d23e  mov     eax, [rsp+178h+var_D0]
0x18003d245  mov     [r12], eax
0x18003d249  mov     ecx, [rsp+178h+var_D0]
0x18003d250  mov     dword ptr [r12+4], 1
0x18003d259  mov     rax, cs:WPP_GLOBAL_Control
0x18003d260  lea     rdi, WPP_GLOBAL_Control
0x18003d267  cmp     rax, rdi
0x18003d26a  jz      loc_18003D486
0x18003d270  cmp     byte ptr [rax+19h], 4
0x18003d274  jb      loc_18003D486
0x18003d27a  test    byte ptr [rax+1Ch], 1
0x18003d27e  jz      loc_18003D486
0x18003d284  mov     edx, 15h
0x18003d289  mov     r9, r15
0x18003d28c  mov     dword ptr [rsp+178h+pdwType], ecx
0x18003d290  lea     r8, WPP_d1926522bc273c8e7056db3405527a30_Traceguids
0x18003d297  mov     rcx, [rax+10h]
0x18003d29b  call    WPP_SF_Sd
0x18003d2a0  mov     rax, cs:WPP_GLOBAL_Control
0x18003d2a7  jmp     loc_18003D486
0x18003d2ac  mov     rax, cs:WPP_GLOBAL_Control
0x18003d2b3  mov     rcx, cs:?s_wcmLocalPolicyKey@@3VKey@Registry@WcmCommon@@A; WcmCommon::Registry::Key s_wcmLocalPolicyKey
0x18003d2ba  test    rcx, rcx
0x18003d2bd  jz      loc_18003D41D
0x18003d2c3  mov     [rsp+178h+var_D0], r14d
0x18003d2cb  mov     r15, [rbx]
0x18003d2ce  mov     [rsp+178h+var_130], r14
0x18003d2d3  mov     [rsp+178h+var_138], 4
0x18003d2db  lea     rax, [rsp+178h+var_D0]
0x18003d2e3  mov     [rsp+178h+var_140], rax
0x18003d2e8  mov     [rsp+178h+pcbData], r14
0x18003d2ed  mov     dword ptr [rsp+178h+pvData], 10h
0x18003d2f5  mov     [rsp+178h+pdwType], r15
0x18003d2fa  lea     r9, aSoftwarePolici_0; "Software\\Policies\\Microsoft\\Windows"...
0x18003d301  xor     edx, edx
0x18003d303  mov     r8, 0FFFFFFFF80000002h
0x18003d30a  call    cs:__imp_GetRegistryValueWithFallbackW
0x18003d310  mov     edi, eax
0x18003d312  test    eax, eax
0x18003d314  jle     short loc_18003D31F
0x18003d316  movzx   edi, ax
0x18003d319  or      edi, 80070000h
0x18003d31f  test    edi, edi
0x18003d321  jns     loc_18003D43F
0x18003d327  cmp     edi, 80070002h
0x18003d32d  jz      loc_18003D3D0
0x18003d333  mov     rsi, cs:?s_wcmLocalPolicyKey@@3VKey@Registry@WcmCommon@@A; WcmCommon::Registry::Key s_wcmLocalPolicyKey
0x18003d33a  test    rsi, rsi
0x18003d33d  jz      short loc_18003D363
0x18003d33f  call    cs:__imp_GetLastError
0x18003d345  mov     ebx, eax
0x18003d347  mov     rcx, rsi; hKey
0x18003d34a  call    cs:__imp_RegCloseKey
0x18003d350  mov     ecx, ebx; dwErrCode
0x18003d352  call    cs:__imp_SetLastError
0x18003d358  lea     rbx, [rsp+178h+var_C8]
0x18003d360  add     rbx, r13
0x18003d363  mov     cs:?s_wcmLocalPolicyKey@@3VKey@Registry@WcmCommon@@A, r14; WcmCommon::Registry::Key s_wcmLocalPolicyKey
0x18003d36a  call    ?InternalInit@ConfigManager@@AEAAXXZ; ConfigManager::InternalInit(void)
0x18003d36f  mov     rcx, cs:?s_wcmLocalPolicyKey@@3VKey@Registry@WcmCommon@@A; WcmCommon::Registry::Key s_wcmLocalPolicyKey
0x18003d376  test    rcx, rcx
0x18003d379  jz      short loc_18003D3D0
0x18003d37b  mov     [rsp+178h+var_130], r14
0x18003d380  mov     [rsp+178h+var_138], 4
0x18003d388  lea     rax, [rsp+178h+var_D0]
0x18003d390  mov     [rsp+178h+var_140], rax
0x18003d395  mov     [rsp+178h+pcbData], r14
0x18003d39a  mov     dword ptr [rsp+178h+pvData], 10h
0x18003d3a2  mov     [rsp+178h+pdwType], r15
0x18003d3a7  lea     r9, aSoftwarePolici_0; "Software\\Policies\\Microsoft\\Windows"...
0x18003d3ae  xor     edx, edx
0x18003d3b0  mov     r8, 0FFFFFFFF80000002h
0x18003d3b7  call    cs:__imp_GetRegistryValueWithFallbackW
0x18003d3bd  mov     edi, eax
0x18003d3bf  test    eax, eax
0x18003d3c1  jle     short loc_18003D3CC
0x18003d3c3  movzx   edi, ax
0x18003d3c6  or      edi, 80070000h
0x18003d3cc  test    edi, edi
0x18003d3ce  jns     short loc_18003D43F
0x18003d3d0  mov     rax, cs:WPP_GLOBAL_Control
0x18003d3d7  lea     rcx, WPP_GLOBAL_Control
0x18003d3de  cmp     rax, rcx
0x18003d3e1  jz      loc_18003D47F
0x18003d3e7  cmp     byte ptr [rax+19h], 4
0x18003d3eb  jb      short loc_18003D416
0x18003d3ed  test    byte ptr [rax+1Ch], 1
0x18003d3f1  jz      short loc_18003D416
0x18003d3f3  mov     edx, 16h
0x18003d3f8  mov     dword ptr [rsp+178h+pdwType], edi
0x18003d3fc  mov     r9, r15
0x18003d3ff  lea     r8, WPP_d1926522bc273c8e7056db3405527a30_Traceguids
0x18003d406  mov     rcx, [rax+10h]
0x18003d40a  call    WPP_SF_Sd
0x18003d40f  mov     rax, cs:WPP_GLOBAL_Control
0x18003d416  lea     rdi, WPP_GLOBAL_Control
0x18003d41d  cmp     rax, rdi
0x18003d420  jz      short loc_18003D486
0x18003d422  cmp     byte ptr [rax+19h], 4
0x18003d426  jb      short loc_18003D486
0x18003d428  test    byte ptr [rax+1Ch], 1
0x18003d42c  jz      short loc_18003D486
0x18003d42e  mov     edx, 18h
0x18003d433  mov     ecx, [r12]
0x18003d437  mov     r9, [rbx]
0x18003d43a  jmp     loc_18003D28C
0x18003d43f  mov     eax, [rsp+178h+var_D0]
0x18003d446  mov     [r12], eax
0x18003d44a  mov     ecx, [rsp+178h+var_D0]
0x18003d451  mov     [r12+4], r14d
0x18003d456  mov     rax, cs:WPP_GLOBAL_Control
0x18003d45d  lea     rdi, WPP_GLOBAL_Control
0x18003d464  cmp     rax, rdi
0x18003d467  jz      short loc_18003D486
0x18003d469  cmp     byte ptr [rax+19h], 4
0x18003d46d  jb      short loc_18003D486
0x18003d46f  test    byte ptr [rax+1Ch], 1
0x18003d473  jz      short loc_18003D486
0x18003d475  mov     edx, 17h
0x18003d47a  jmp     loc_18003D289
0x18003d47f  lea     rdi, WPP_GLOBAL_Control
0x18003d486  mov     rdx, [rsp+178h+var_F8]
0x18003d48e  inc     rdx
0x18003d491  mov     [rsp+178h+var_F8], rdx
0x18003d499  add     r13, 18h
0x18003d49d  cmp     rdx, 3
0x18003d4a1  jnz     loc_18003D0C0
0x18003d4a7  mov     rcx, cs:?s_wcmRootKey@@3VKey@Registry@WcmCommon@@A; hkey
0x18003d4ae  test    rcx, rcx
0x18003d4b1  jz      loc_18003D57A
0x18003d4b7  mov     [rsp+178h+var_D0], r14d
0x18003d4bf  mov     [rsp+178h+var_CC], 4
0x18003d4ca  lea     rax, [rsp+178h+var_CC]
0x18003d4d2  mov     [rsp+178h+pcbData], rax; pcbData
0x18003d4d7  lea     rax, [rsp+178h+var_D0]
0x18003d4df  mov     [rsp+178h+pvData], rax; pvData
0x18003d4e4  mov     [rsp+178h+pdwType], r14; int
0x18003d4e9  mov     r9d, 10h; dwFlags
0x18003d4ef  lea     r8, Value; "fDisableMinimizePolicy"
0x18003d4f6  xor     edx, edx; lpSubKey
0x18003d4f8  call    cs:__imp_RegGetValueW
0x18003d4fe  test    eax, eax
0x18003d500  jle     short loc_18003D50A
0x18003d502  movzx   eax, ax
0x18003d505  or      eax, 80070000h
0x18003d50a  mov     rcx, [rsp+178h]; this
0x18003d512  test    eax, eax
0x18003d514  js      loc_18003D71C
0x18003d51a  mov     r9d, [rsp+178h+var_D0]
0x18003d522  mov     rbx, [rsp+178h+var_120]
0x18003d527  mov     [rbx], r9d
0x18003d52a  mov     [rbx+4], r14d
0x18003d52e  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d535  cmp     rcx, rdi
0x18003d538  jz      short loc_18003D55C
0x18003d53a  cmp     byte ptr [rcx+19h], 4
0x18003d53e  jb      short loc_18003D55C
0x18003d540  test    byte ptr [rcx+1Ch], 1
0x18003d544  jz      short loc_18003D55C
0x18003d546  mov     edx, 19h
0x18003d54b  lea     r8, WPP_d1926522bc273c8e7056db3405527a30_Traceguids
0x18003d552  mov     rcx, [rcx+10h]
0x18003d556  call    WPP_SF_d
0x18003d55b  nop
0x18003d55c  jmp     short loc_18003D5A5
0x18003d55e  mov     rdx, [rsp+178h+var_E8]
0x18003d566  mov     r8, [rsp+178h+var_E0]
0x18003d56e  mov     r9, [rsp+178h+var_108]
0x18003d573  mov     rbx, [rsp+178h+var_100]
0x18003d578  jmp     short loc_18003D5B4
0x18003d57a  cmp     rax, rdi
  ... truncated ...
```
