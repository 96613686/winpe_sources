# PolarisCommonUtils::ApplyConfigOverridesFromAppProperty(IMemObj *)

- ea: `0x10044b1d0`
- end: `0x10044b734`
- name: `?ApplyConfigOverridesFromAppProperty@PolarisCommonUtils@@SAJPEAVIMemObj@@@Z`
- size: `1380`
- prototype: `__int64 __fastcall(struct IMemObj *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x10042a380`

## callees

- `0x100401580`
- `0x1004406a0`
- `0x10044b0b0`
- `0x10044b1d0`
- `0x10044b740`
- `0x10044b8b0`
- `0x10044ee50`

## import_xrefs

- `sqlmin!?GetCurrentInstance@CFeatureSwitchesMin@@SAPEBV1@XZ` at `0x10044b218`
- `sqlmin!?GetCurrentInstance@CFeatureSwitchesMin@@SAPEBV1@XZ` at `0x10044b218`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x10044b4ec`
- `sqldk!??_V@YAXPEAX@Z` at `0x10044b662`
- `sqldk!??_V@YAXPEAX@Z` at `0x10044b6fb`
- `sqldk!??_V@YAXPEAX@Z` at `0x10044b662`
- `sqldk!??_V@YAXPEAX@Z` at `0x10044b6fb`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10044b2eb`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10044b399`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10044b2eb`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10044b399`
- `api-ms-win-crt-string-l1-1-0!wcscpy_s` at `0x10044b5ee`
- `api-ms-win-crt-string-l1-1-0!wcscpy_s` at `0x10044b61a`
- `api-ms-win-crt-string-l1-1-0!wcscpy_s` at `0x10044b5ee`
- `api-ms-win-crt-string-l1-1-0!wcscpy_s` at `0x10044b61a`
- `hostregdll!HostReg_SpAlterXDBConfigHelper` at `0x10044b33c`
- `hostregdll!HostReg_SpAlterXDBConfigHelper` at `0x10044b567`
- `hostregdll!HostReg_SpAlterXDBConfigHelper` at `0x10044b33c`
- `hostregdll!HostReg_SpAlterXDBConfigHelper` at `0x10044b567`
- `sqlfabric!SpAlterXDBConfigHelper` at `0x10044b31d`
- `sqlfabric!SpAlterXDBConfigHelper` at `0x10044b548`
- `sqlfabric!SpAlterXDBConfigHelper` at `0x10044b31d`
- `sqlfabric!SpAlterXDBConfigHelper` at `0x10044b548`

## string_xrefs

- `0x10044b235`: `[App Property Config Overrides]`
- `0x10044b2f7`: `[App Property Config Overrides]`
- `0x10044b3b9`: `[App Property Config Overrides]`
- `0x10044b466`: `[App Property Config Overrides]`
- `0x10044b5a5`: `[App Property Config Overrides]`
- `0x10044b632`: `[App Property Config Overrides]`
- `0x10044b649`: `[App Property Config Overrides]`
- `0x10044b67d`: `[App Property Config Overrides]`
- `0x10044b69a`: `[App Property Config Overrides]`
- `0x10044b6b2`: `[App Property Config Overrides]`
- `0x10044b6e9`: `[App Property Config Overrides]`
- `0x10044b684`: `%ls More than %d overrides provided, which exceeds the size of the previous config store. Skipping all subsequent overrides.`
- `0x10044b46d`: `%ls Provided JSON was successfully parsed. Starting to process the overrides.`
- `0x10044b3eb`: `%ls Error reading the new overrides. Skipping.`
- `0x10044b3d6`: `AppPropertyConfigOverrides`
- `0x10044b6b9`: `%ls Invalid JSON config provided '%ls'. Will not apply any overrides.`
- `0x10044b2d8`: `"PolarisCommonUtils.cpp"`
- `0x10044b386`: `"PolarisCommonUtils.cpp"`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall PolarisCommonUtils::ApplyConfigOverridesFromAppProperty(struct IMemObj *a1)
{
  struct IMemObj *v1; // r12
  unsigned int v3; // r15d
  int v4; // eax
  __int64 v5; // rcx
  wchar_t (near **v6)[100]; // rbx
  wchar_t (near **v7)[100]; // rdi
  int v8; // ebx
  const wchar_t *v9; // rdx
  int v10; // edi
  wchar_t *v11; // rbx
  __int64 v12; // rax
  JSONParserLib::JSONNode *v13; // rdi
  __int64 v14; // rsi
  const wchar_t *v15; // r14
  __int64 v16; // rdi
  int v17; // ebx
  const wchar_t *v18; // rdx
  errno_t v19; // eax
  const wchar_t *v20; // rcx
  char v21[8]; // [rsp+30h] [rbp-D8h]
  char v22[8]; // [rsp+30h] [rbp-D8h]
  __int64 v23; // [rsp+40h] [rbp-C8h]
  wchar_t *Source; // [rsp+48h] [rbp-C0h] BYREF
  JSONParserLib::JSONNode *v25; // [rsp+50h] [rbp-B8h]
  wchar_t *v26; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v27; // [rsp+60h] [rbp-A8h]
  __int64 v28; // [rsp+68h] [rbp-A0h]
  _BYTE v29[208]; // [rsp+78h] [rbp-90h] BYREF
  _BYTE v30[208]; // [rsp+148h] [rbp+40h] BYREF
  _BYTE v31[208]; // [rsp+218h] [rbp+110h] BYREF

  v28 = -2;
  v1 = a1;
  v25 = a1;
  if ( !*(_BYTE *)(CFeatureSwitchesMin::GetCurrentInstance(a1) + 403) )
    return 0;
  SOSLogToErrorLog(
    L"%ls Starting to revert previous overrides - %d overrides found.",
    L"[App Property Config Overrides]",
    (unsigned int)PolarisCommonUtils::currentConfigOverridesCnt);
  v3 = 0;
  v4 = PolarisCommonUtils::currentConfigOverridesCnt;
  if ( PolarisCommonUtils::currentConfigOverridesCnt > 0 )
  {
    do
    {
      PolarisCommonUtils::currentConfigOverridesCnt = v4 - 1;
      v5 = 25LL * (v4 - 1);
      v6 = &(&PolarisCommonUtils::previousConfigSettingNames)[v5];
      v7 = &(&PolarisCommonUtils::previousConfigSettingValues)[v5];
      LODWORD(v23) = 100;
      *(_DWORD *)v21 = 100;
      if ( swscanf_s(
             (const wchar_t *const)&(&PolarisCommonUtils::previousConfigSettingNames)[v5],
             L"%l[^_]_%l[^_]_%l[^_]",
             v31,
             100,
             v30,
             *(_QWORD *)v21,
             v29,
             v23) != 3 )
        utassert_fail(1u, "keyNameCnt == 3", "\"PolarisCommonUtils.cpp\"", 192, 0);
      SOSLogToErrorLog(L"%ls Reverting '%ls' to '%ls'", L"[App Property Config Overrides]", v6, v7);
      v8 = SpAlterXDBConfigHelper(v31, v30, v29, v7);
      if ( !v8 )
        v8 = HostReg_SpAlterXDBConfigHelper(v31, v30, v29, v7);
      v9 = L"Failed";
      if ( !v8 )
        v9 = L"Succeeded";
      SOSLogToErrorLog(
        L"%ls applying override for package='%ls', section='%ls', setting='%ls' to value='%ls'.",
        v9,
        v31,
        v30,
        v29,
        v7);
      if ( v8 < 0 )
        utassert_fail(1u, "SUCCEEDED(hr)", "\"PolarisCommonUtils.cpp\"", 213, 0);
      v4 = PolarisCommonUtils::currentConfigOverridesCnt;
    }
    while ( PolarisCommonUtils::currentConfigOverridesCnt > 0 );
    v1 = v25;
  }
  SOSLogToErrorLog(L"%ls Finished reverting the previous overrides.", L"[App Property Config Overrides]");
  v26 = 0;
  v10 = PolarisCommonUtils::ReadWinFabProperty(v1, L"AppPropertyConfigOverrides", &v26);
  if ( v10 >= 0 )
  {
    _mm_lfence();
    v11 = v26;
    if ( v26 )
    {
      v12 = -1;
      do
        ++v12;
      while ( v26[v12] );
      if ( v12 )
      {
        LODWORD(v27) = 0;
        v25 = 0;
        v13 = 0;
        if ( (unsigned __int8)JSONParserLib::JSONParser::Parse(v1, 0, 0) && *(_DWORD *)v25 == 1 )
        {
          SOSLogToErrorLog(
            L"%ls Provided JSON was successfully parsed. Starting to process the overrides.",
            L"[App Property Config Overrides]");
          v14 = *(_QWORD *)(MEMORY[0x10] + 8LL);
          if ( v14 )
          {
            while ( PolarisCommonUtils::currentConfigOverridesCnt < 10 )
            {
              v15 = *(const wchar_t **)v14;
              v16 = *(_QWORD *)(*(_QWORD *)(v14 + 8) + 16LL);
              LODWORD(v23) = 100;
              *(_DWORD *)v22 = 100;
              swscanf_s(*(const wchar_t *const *)v14, L"%l[^_]_%l[^_]_%l[^_]", v31, 100, v30, *(_QWORD *)v22, v29, v23);
              Source = 0;
              if ( (*(unsigned __int8 (__fastcall **)(struct IServerConfiguration *, _BYTE *, _BYTE *, struct IMemObj *, wchar_t **, _BYTE *))(*(_QWORD *)s_pServerConf + 528LL))(
                     s_pServerConf,
                     v30,
                     v29,
                     v1,
                     &Source,
                     v31)
                && Source )
              {
                v17 = SpAlterXDBConfigHelper(v31, v30, v29, v16);
                if ( !v17 )
                  v17 = HostReg_SpAlterXDBConfigHelper(v31, v30, v29, v16);
                v18 = L"Failed";
                if ( !v17 )
                  v18 = L"Succeeded";
                SOSLogToErrorLog(
                  L"%ls applying override for package='%ls', section='%ls', setting='%ls' to value='%ls'.",
                  v18,
                  v31,
                  v30,
                  v29,
                  v16);
                if ( v17 >= 0 )
                {
                  _mm_lfence();
                  SOSLogToErrorLog(
                    L"%ls Successfully applied override to '%ls' with value '%ls'",
                    L"[App Property Config Overrides]",
                    v15,
                    v16);
                  if ( wcscpy_s(
                         (wchar_t *)&(&PolarisCommonUtils::previousConfigSettingNames)[25
                                                                                     * PolarisCommonUtils::currentConfigOverridesCnt],
                         0x64u,
                         v15)
                    || (v19 = wcscpy_s(
                                (wchar_t *)&(&PolarisCommonUtils::previousConfigSettingValues)[25
                                                                                             * PolarisCommonUtils::currentConfigOverridesCnt],
                                0x64u,
                                Source),
                        v20 = L"%ls Stored original value of the setting.",
                        v19) )
                  {
                    v20 = L"%ls Storing the original value of the setting failed.";
                  }
                  SOSLogToErrorLog(v20, L"[App Property Config Overrides]");
                  ++PolarisCommonUtils::currentConfigOverridesCnt;
                }
                else
                {
                  SOSLogToErrorLog(
                    L"%ls Applying the override for '%ls' failed. Skipping it.",
                    L"[App Property Config Overrides]",
                    v15);
                }
              }
              else
              {
                SOSLogToErrorLog(L"%ls Setting '%ls' not found. Skipping it.", L"[App Property Config Overrides]", v15);
              }
              operator delete[](Source);
              v14 = *(_QWORD *)(v14 + 16);
              if ( !v14 )
                goto LABEL_40;
            }
            SOSLogToErrorLog(
              L"%ls More than %d overrides provided, which exceeds the size of the previous config store. Skipping all sub"
               "sequent overrides.",
              L"[App Property Config Overrides]",
              10);
LABEL_40:
            v13 = v25;
            v11 = v26;
          }
          SOSLogToErrorLog(L"%ls Finished processing the overrides.", L"[App Property Config Overrides]");
        }
        else
        {
          SOSLogToErrorLog(
            L"%ls Invalid JSON config provided '%ls'. Will not apply any overrides.",
            L"[App Property Config Overrides]",
            v11);
          v3 = -2147024809;
        }
        if ( v13 )
          JSONParserLib::JSONNode::`scalar deleting destructor'(v13, 1u);
        goto LABEL_47;
      }
    }
    v10 = 0;
    SOSLogToErrorLog(L"%ls No overrides present. Skipping.", L"[App Property Config Overrides]");
  }
  else
  {
    v11 = v26;
    SOSLogToErrorLog(L"%ls Error reading the new overrides. Skipping.", L"[App Property Config Overrides]");
  }
  v3 = v10;
LABEL_47:
  operator delete[](v11);
  return v3;
}

```

## disassembly

```asm
0x10044b1d0  mov     rax, rsp
0x10044b1d3  push    rbp
0x10044b1d4  push    r12
0x10044b1d6  push    r13
0x10044b1d8  push    r14
0x10044b1da  push    r15
0x10044b1dc  lea     rbp, [rax-218h]
0x10044b1e3  sub     rsp, 2F0h
0x10044b1ea  mov     [rsp+310h+var_2B0], 0FFFFFFFFFFFFFFFEh
0x10044b1f3  mov     [rax+10h], rbx
0x10044b1f7  mov     [rax+18h], rsi
0x10044b1fb  mov     [rax+20h], rdi
0x10044b1ff  mov     rax, cs:__security_cookie
0x10044b206  xor     rax, rsp
0x10044b209  mov     [rbp+210h+var_30], rax
0x10044b210  mov     r12, rcx
0x10044b213  mov     [rsp+310h+var_2C8], rcx
0x10044b218  call    cs:__imp_?GetCurrentInstance@CFeatureSwitchesMin@@SAPEBV1@XZ; CFeatureSwitchesMin::GetCurrentInstance(void)
0x10044b21e  cmp     byte ptr [rax+193h], 0
0x10044b225  jnz     short loc_10044B22E
0x10044b227  xor     eax, eax
0x10044b229  jmp     loc_10044B704
0x10044b22e  mov     r8d, cs:?currentConfigOverridesCnt@PolarisCommonUtils@@0HA; int PolarisCommonUtils::currentConfigOverridesCnt
0x10044b235  lea     rdx, aAppPropertyCon; "[App Property Config Overrides]"
0x10044b23c  lea     rcx, aLsStartingToRe; "%ls Starting to revert previous overrid"...
0x10044b243  call    ?SOSLogToErrorLog@@YAXPEB_WZZ; SOSLogToErrorLog(wchar_t const *,...)
0x10044b248  lea     rdx, ?previousConfigSettingNames@PolarisCommonUtils@@0PAY0GE@_WA; wchar_t (near * PolarisCommonUtils::previousConfigSettingNames)[100]
0x10044b24f  xor     r15d, r15d
0x10044b252  lea     r13, aSucceeded; "Succeeded"
0x10044b259  mov     eax, cs:?currentConfigOverridesCnt@PolarisCommonUtils@@0HA; int PolarisCommonUtils::currentConfigOverridesCnt
0x10044b25f  test    eax, eax
0x10044b261  jle     loc_10044B3B9
0x10044b267  lea     r12, ?previousConfigSettingValues@PolarisCommonUtils@@0PAY0GE@_WA; wchar_t (near * PolarisCommonUtils::previousConfigSettingValues)[100]
0x10044b26e  xchg    ax, ax
0x10044b270  dec     eax
0x10044b272  mov     cs:?currentConfigOverridesCnt@PolarisCommonUtils@@0HA, eax; int PolarisCommonUtils::currentConfigOverridesCnt
0x10044b278  cdqe
0x10044b27a  imul    rcx, rax, 0C8h
0x10044b281  lea     rbx, [rcx+rdx]
0x10044b285  lea     rdi, [rcx+r12]
0x10044b289  mov     dword ptr [rsp+310h+var_2D8], 64h ; 'd'
0x10044b291  lea     rax, [rsp+310h+var_2A0]
0x10044b296  mov     qword ptr [rsp+310h+var_2E0], rax
0x10044b29b  mov     dword ptr [rsp+310h+var_2E8], 64h ; 'd'
0x10044b2a3  lea     rax, [rbp+210h+var_1D0]
0x10044b2a7  mov     [rsp+310h+var_2F0], rax
0x10044b2ac  mov     r9d, 64h ; 'd'
0x10044b2b2  lea     r8, [rbp+210h+var_100]
0x10044b2b9  lea     rdx, aLLL; "%l[^_]_%l[^_]_%l[^_]"
0x10044b2c0  mov     rcx, rbx; Buffer
0x10044b2c3  call    swscanf_s
0x10044b2c8  cmp     eax, 3
0x10044b2cb  jz      short loc_10044B2F1
0x10044b2cd  mov     [rsp+310h+var_2F0], r15
0x10044b2d2  mov     r9d, 0C0h
0x10044b2d8  lea     r8, aPolariscommonu; "\"PolarisCommonUtils.cpp\""
0x10044b2df  lea     rdx, aKeynamecnt3; "keyNameCnt == 3"
0x10044b2e6  mov     ecx, 1
0x10044b2eb  call    cs:__imp_?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x10044b2f1  mov     r9, rdi
0x10044b2f4  mov     r8, rbx
0x10044b2f7  lea     rdx, aAppPropertyCon; "[App Property Config Overrides]"
0x10044b2fe  lea     rcx, aLsRevertingLsT; "%ls Reverting '%ls' to '%ls'"
0x10044b305  call    ?SOSLogToErrorLog@@YAXPEB_WZZ; SOSLogToErrorLog(wchar_t const *,...)
0x10044b30a  mov     r9, rdi
0x10044b30d  lea     r8, [rsp+310h+var_2A0]
0x10044b312  lea     rdx, [rbp+210h+var_1D0]
0x10044b316  lea     rcx, [rbp+210h+var_100]
0x10044b31d  call    cs:__imp_SpAlterXDBConfigHelper
0x10044b323  mov     ebx, eax
0x10044b325  test    eax, eax
0x10044b327  jnz     short loc_10044B344
0x10044b329  mov     r9, rdi
0x10044b32c  lea     r8, [rsp+310h+var_2A0]
0x10044b331  lea     rdx, [rbp+210h+var_1D0]
0x10044b335  lea     rcx, [rbp+210h+var_100]
0x10044b33c  call    cs:__imp_HostReg_SpAlterXDBConfigHelper
0x10044b342  mov     ebx, eax
0x10044b344  lea     rdx, aFailed; "Failed"
0x10044b34b  test    ebx, ebx
0x10044b34d  cmovz   rdx, r13
0x10044b351  mov     qword ptr [rsp+310h+var_2E8], rdi
0x10044b356  lea     rax, [rsp+310h+var_2A0]
0x10044b35b  mov     [rsp+310h+var_2F0], rax
0x10044b360  lea     r9, [rbp+210h+var_1D0]
0x10044b364  lea     r8, [rbp+210h+var_100]
0x10044b36b  lea     rcx, aLsApplyingOver; "%ls applying override for package='%ls'"...
0x10044b372  call    ?SOSLogToErrorLog@@YAXPEB_WZZ; SOSLogToErrorLog(wchar_t const *,...)
0x10044b377  test    ebx, ebx
0x10044b379  jns     short loc_10044B39F
0x10044b37b  mov     [rsp+310h+var_2F0], r15
0x10044b380  mov     r9d, 0D5h
0x10044b386  lea     r8, aPolariscommonu; "\"PolarisCommonUtils.cpp\""
0x10044b38d  lea     rdx, aSucceededHr; "SUCCEEDED(hr)"
0x10044b394  mov     ecx, 1
0x10044b399  call    cs:__imp_?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x10044b39f  mov     eax, cs:?currentConfigOverridesCnt@PolarisCommonUtils@@0HA; int PolarisCommonUtils::currentConfigOverridesCnt
0x10044b3a5  test    eax, eax
0x10044b3a7  lea     rdx, ?previousConfigSettingNames@PolarisCommonUtils@@0PAY0GE@_WA; wchar_t (near * PolarisCommonUtils::previousConfigSettingNames)[100]
0x10044b3ae  jg      loc_10044B270
0x10044b3b4  mov     r12, [rsp+310h+var_2C8]
0x10044b3b9  lea     rdx, aAppPropertyCon; "[App Property Config Overrides]"
0x10044b3c0  lea     rcx, aLsFinishedReve; "%ls Finished reverting the previous ove"...
0x10044b3c7  call    ?SOSLogToErrorLog@@YAXPEB_WZZ; SOSLogToErrorLog(wchar_t const *,...)
0x10044b3cc  mov     [rsp+310h+var_2C0], r15
0x10044b3d1  lea     r8, [rsp+310h+var_2C0]; wchar_t **
0x10044b3d6  lea     rdx, aApppropertycon; "AppPropertyConfigOverrides"
0x10044b3dd  mov     rcx, r12; struct IMemObj *
0x10044b3e0  call    ?ReadWinFabProperty@PolarisCommonUtils@@SAJPEAVIMemObj@@PEB_WPEAPEA_W@Z; PolarisCommonUtils::ReadWinFabProperty(IMemObj *,wchar_t const *,wchar_t * *)
0x10044b3e5  mov     edi, eax
0x10044b3e7  test    eax, eax
0x10044b3e9  jns     short loc_10044B3FC
0x10044b3eb  lea     rcx, aLsErrorReading; "%ls Error reading the new overrides. Sk"...
0x10044b3f2  mov     rbx, [rsp+310h+var_2C0]
0x10044b3f7  jmp     loc_10044B6E9
0x10044b3fc  lfence
0x10044b3ff  mov     rbx, [rsp+310h+var_2C0]
0x10044b404  test    rbx, rbx
0x10044b407  jz      loc_10044B6DF
0x10044b40d  mov     rax, 0FFFFFFFFFFFFFFFFh
0x10044b414  inc     rax
0x10044b417  cmp     word ptr [rbx+rax*2], 0
0x10044b41c  jnz     short loc_10044B414
0x10044b41e  test    rax, rax
0x10044b421  jz      loc_10044B6DF
0x10044b427  mov     dword ptr [rsp+310h+var_2B8], r15d
0x10044b42c  mov     [rsp+310h+var_2C8], r15
0x10044b431  mov     [rsp+310h+var_2E8], 0; char
0x10044b436  mov     [rsp+310h+var_2F0], r15; unsigned __int64
0x10044b43b  lea     r9, [rsp+310h+var_2B8]
0x10044b440  lea     r8, [rsp+310h+var_2C8]
0x10044b445  mov     rdx, rbx
0x10044b448  mov     rcx, r12; struct IMemObj *
0x10044b44b  call    ?Parse@JSONParser@JSONParserLib@@SA_NPEAVIMemObj@@PEB_WAEAV?$CAutoP@VJSONNode@JSONParserLib@@@@AEAK_K_N@Z; JSONParserLib::JSONParser::Parse(IMemObj *,wchar_t const *,CAutoP<JSONParserLib::JSONNode> &,ulong &,unsigned __int64,bool)
0x10044b450  mov     rdi, [rsp+310h+var_2C8]
0x10044b455  test    al, al
0x10044b457  jz      loc_10044B6AF
0x10044b45d  cmp     dword ptr [rdi], 1
0x10044b460  jnz     loc_10044B6AF
0x10044b466  lea     rdx, aAppPropertyCon; "[App Property Config Overrides]"
0x10044b46d  lea     rcx, aLsProvidedJson; "%ls Provided JSON was successfully pars"...
0x10044b474  call    ?SOSLogToErrorLog@@YAXPEB_WZZ; SOSLogToErrorLog(wchar_t const *,...)
0x10044b479  mov     rax, [rdi+10h]
0x10044b47d  mov     rsi, [rax+8]
0x10044b481  test    rsi, rsi
0x10044b484  jz      loc_10044B69A
0x10044b48a  nop     word ptr [rax+rax]
0x10044b48f  nop
0x10044b490  cmp     cs:?currentConfigOverridesCnt@PolarisCommonUtils@@0HA, 0Ah; int PolarisCommonUtils::currentConfigOverridesCnt
0x10044b497  jge     loc_10044B677
0x10044b49d  mov     r14, [rsi]
0x10044b4a0  mov     rax, [rsi+8]
0x10044b4a4  mov     rdi, [rax+10h]
0x10044b4a8  mov     dword ptr [rsp+310h+var_2D8], 64h ; 'd'
0x10044b4b0  lea     rax, [rsp+310h+var_2A0]
0x10044b4b5  mov     qword ptr [rsp+310h+var_2E0], rax
0x10044b4ba  mov     dword ptr [rsp+310h+var_2E8], 64h ; 'd'
0x10044b4c2  lea     rax, [rbp+210h+var_1D0]
0x10044b4c6  mov     [rsp+310h+var_2F0], rax
0x10044b4cb  mov     r9d, 64h ; 'd'
0x10044b4d1  lea     r8, [rbp+210h+var_100]
0x10044b4d8  lea     rdx, aLLL; "%l[^_]_%l[^_]_%l[^_]"
0x10044b4df  mov     rcx, r14; Buffer
0x10044b4e2  call    swscanf_s
0x10044b4e7  mov     [rsp+310h+Source], r15
0x10044b4ec  mov     rax, cs:__imp_?s_pServerConf@@3PEAVIServerConfiguration@@EA; IServerConfiguration * s_pServerConf
0x10044b4f3  mov     rcx, [rax]
0x10044b4f6  mov     rax, [rcx]
0x10044b4f9  lea     rdx, [rbp+210h+var_100]
0x10044b500  mov     qword ptr [rsp+310h+var_2E8], rdx
0x10044b505  lea     rdx, [rsp+310h+Source]
0x10044b50a  mov     [rsp+310h+var_2F0], rdx
0x10044b50f  mov     r9, r12
0x10044b512  lea     r8, [rsp+310h+var_2A0]
0x10044b517  lea     rdx, [rbp+210h+var_1D0]
0x10044b51b  call    qword ptr [rax+210h]
0x10044b521  test    al, al
0x10044b523  jz      loc_10044B646
0x10044b529  cmp     [rsp+310h+Source], 0
0x10044b52f  jz      loc_10044B646
0x10044b535  mov     r9, rdi
0x10044b538  lea     r8, [rsp+310h+var_2A0]
0x10044b53d  lea     rdx, [rbp+210h+var_1D0]
0x10044b541  lea     rcx, [rbp+210h+var_100]
0x10044b548  call    cs:__imp_SpAlterXDBConfigHelper
0x10044b54e  mov     ebx, eax
0x10044b550  test    eax, eax
0x10044b552  jnz     short loc_10044B56F
0x10044b554  mov     r9, rdi
0x10044b557  lea     r8, [rsp+310h+var_2A0]
0x10044b55c  lea     rdx, [rbp+210h+var_1D0]
0x10044b560  lea     rcx, [rbp+210h+var_100]
0x10044b567  call    cs:__imp_HostReg_SpAlterXDBConfigHelper
0x10044b56d  mov     ebx, eax
0x10044b56f  lea     rdx, aFailed; "Failed"
0x10044b576  test    ebx, ebx
0x10044b578  cmovz   rdx, r13
0x10044b57c  mov     qword ptr [rsp+310h+var_2E8], rdi
0x10044b581  lea     rax, [rsp+310h+var_2A0]
0x10044b586  mov     [rsp+310h+var_2F0], rax
0x10044b58b  lea     r9, [rbp+210h+var_1D0]
0x10044b58f  lea     r8, [rbp+210h+var_100]
0x10044b596  lea     rcx, aLsApplyingOver; "%ls applying override for package='%ls'"...
0x10044b59d  call    ?SOSLogToErrorLog@@YAXPEB_WZZ; SOSLogToErrorLog(wchar_t const *,...)
0x10044b5a2  mov     r8, r14
0x10044b5a5  lea     rdx, aAppPropertyCon; "[App Property Config Overrides]"
0x10044b5ac  test    ebx, ebx
0x10044b5ae  jns     short loc_10044B5BC
0x10044b5b0  lea     rcx, aLsApplyingTheO; "%ls Applying the override for '%ls' fai"...
0x10044b5b7  jmp     loc_10044B657
0x10044b5bc  lfence
0x10044b5bf  mov     r9, rdi
0x10044b5c2  lea     rcx, aLsSuccessfully; "%ls Successfully applied override to '%"...
0x10044b5c9  call    ?SOSLogToErrorLog@@YAXPEB_WZZ; SOSLogToErrorLog(wchar_t const *,...)
0x10044b5ce  movsxd  rax, cs:?currentConfigOverridesCnt@PolarisCommonUtils@@0HA; int PolarisCommonUtils::currentConfigOverridesCnt
0x10044b5d5  imul    rcx, rax, 0C8h
0x10044b5dc  lea     rax, ?previousConfigSettingNames@PolarisCommonUtils@@0PAY0GE@_WA; wchar_t (near * PolarisCommonUtils::previousConfigSettingNames)[100]
0x10044b5e3  add     rcx, rax; Destination
0x10044b5e6  mov     r8, r14; Source
0x10044b5e9  mov     edx, 64h ; 'd'; SizeInWords
0x10044b5ee  call    cs:__imp_wcscpy_s
0x10044b5f4  test    eax, eax
0x10044b5f6  jnz     short loc_10044B62B
0x10044b5f8  movsxd  rax, cs:?currentConfigOverridesCnt@PolarisCommonUtils@@0HA; int PolarisCommonUtils::currentConfigOverridesCnt
0x10044b5ff  imul    rcx, rax, 0C8h
0x10044b606  lea     rax, ?previousConfigSettingValues@PolarisCommonUtils@@0PAY0GE@_WA; wchar_t (near * PolarisCommonUtils::previousConfigSettingValues)[100]
0x10044b60d  add     rcx, rax; Destination
0x10044b610  mov     r8, [rsp+310h+Source]; Source
0x10044b615  mov     edx, 64h ; 'd'; SizeInWords
0x10044b61a  call    cs:__imp_wcscpy_s
0x10044b620  test    eax, eax
0x10044b622  lea     rcx, aLsStoredOrigin; "%ls Stored original value of the settin"...
0x10044b629  jz      short loc_10044B632
0x10044b62b  lea     rcx, aLsStoringTheOr; "%ls Storing the original value of the s"...
0x10044b632  lea     rdx, aAppPropertyCon; "[App Property Config Overrides]"
0x10044b639  call    ?SOSLogToErrorLog@@YAXPEB_WZZ; SOSLogToErrorLog(wchar_t const *,...)
0x10044b63e  inc     cs:?currentConfigOverridesCnt@PolarisCommonUtils@@0HA; int PolarisCommonUtils::currentConfigOverridesCnt
0x10044b644  jmp     short loc_10044B65D
0x10044b646  mov     r8, r14
0x10044b649  lea     rdx, aAppPropertyCon; "[App Property Config Overrides]"
0x10044b650  lea     rcx, aLsSettingLsNot; "%ls Setting '%ls' not found. Skipping i"...
0x10044b657  call    ?SOSLogToErrorLog@@YAXPEB_WZZ; SOSLogToErrorLog(wchar_t const *,...)
0x10044b65c  nop
0x10044b65d  mov     rcx, [rsp+310h+Source]
0x10044b662  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10044b668  mov     rsi, [rsi+10h]
0x10044b66c  test    rsi, rsi
0x10044b66f  jnz     loc_10044B490
0x10044b675  jmp     short loc_10044B690
0x10044b677  mov     r8d, 0Ah
0x10044b67d  lea     rdx, aAppPropertyCon; "[App Property Config Overrides]"
0x10044b684  lea     rcx, aLsMoreThanDOve; "%ls More than %d overrides provided, wh"...
0x10044b68b  call    ?SOSLogToErrorLog@@YAXPEB_WZZ; SOSLogToErrorLog(wchar_t const *,...)
0x10044b690  mov     rdi, [rsp+310h+var_2C8]
0x10044b695  mov     rbx, [rsp+310h+var_2C0]
0x10044b69a  lea     rdx, aAppPropertyCon; "[App Property Config Overrides]"
0x10044b6a1  lea     rcx, aLsFinishedProc; "%ls Finished processing the overrides."
0x10044b6a8  call    ?SOSLogToErrorLog@@YAXPEB_WZZ; SOSLogToErrorLog(wchar_t const *,...)
0x10044b6ad  jmp     short loc_10044B6CB
0x10044b6af  mov     r8, rbx
0x10044b6b2  lea     rdx, aAppPropertyCon; "[App Property Config Overrides]"
0x10044b6b9  lea     rcx, aLsInvalidJsonC; "%ls Invalid JSON config provided '%ls'."...
0x10044b6c0  call    ?SOSLogToErrorLog@@YAXPEB_WZZ; SOSLogToErrorLog(wchar_t const *,...)
0x10044b6c5  mov     r15d, 80070057h
0x10044b6cb  test    rdi, rdi
0x10044b6ce  jz      short loc_10044B6F8
0x10044b6d0  mov     edx, 1; unsigned int
0x10044b6d5  mov     rcx, rdi; this
0x10044b6d8  call    ??_GJSONNode@JSONParserLib@@QEAAPEAXI@Z; JSONParserLib::JSONNode::`scalar deleting destructor'(uint)
0x10044b6dd  jmp     short loc_10044B6F8
0x10044b6df  mov     edi, r15d
0x10044b6e2  lea     rcx, aLsNoOverridesP; "%ls No overrides present. Skipping."
0x10044b6e9  lea     rdx, aAppPropertyCon; "[App Property Config Overrides]"
0x10044b6f0  call    ?SOSLogToErrorLog@@YAXPEB_WZZ; SOSLogToErrorLog(wchar_t const *,...)
0x10044b6f5  mov     r15d, edi
0x10044b6f8  mov     rcx, rbx
0x10044b6fb  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10044b701  mov     eax, r15d
0x10044b704  mov     rcx, [rbp+210h+var_30]
0x10044b70b  xor     rcx, rsp; StackCookie
0x10044b70e  call    __security_check_cookie
0x10044b713  lea     r11, [rsp+310h+var_20]
0x10044b71b  mov     rbx, [r11+38h]
0x10044b71f  mov     rsi, [r11+40h]
0x10044b723  mov     rdi, [r11+48h]
0x10044b727  mov     rsp, r11
0x10044b72a  pop     r15
0x10044b72c  pop     r14
0x10044b72e  pop     r13
0x10044b730  pop     r12
0x10044b732  pop     rbp
0x10044b733  retn
```
