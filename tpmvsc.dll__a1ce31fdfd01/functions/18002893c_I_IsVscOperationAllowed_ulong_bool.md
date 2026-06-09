# I_IsVscOperationAllowed(ulong,bool *)

- ea: `0x18002893c`
- end: `0x180028e41`
- name: `?I_IsVscOperationAllowed@@YAKKPEA_N@Z`
- size: `1285`
- prototype: `__int64 __fastcall(int, bool *)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002d830`
- `0x18002fccc`

## callees

- `0x180001ec0`
- `0x1800068dc`
- `0x18000bc48`
- `0x18000c010`
- `0x18000c198`
- `0x18001a31c`
- `0x180027154`
- `0x180027314`
- `0x180027458`
- `0x180027b3c`
- `0x18002893c`

## import_xrefs

- `ncrypt!NCryptGetProperty` at `0x180028b3a`
- `ncrypt!NCryptGetProperty` at `0x180028b6d`
- `ncrypt!NCryptGetProperty` at `0x180028bc5`
- `ncrypt!NCryptGetProperty` at `0x180028c06`
- `ncrypt!NCryptGetProperty` at `0x180028c3b`
- `ncrypt!NCryptGetProperty` at `0x180028c89`
- `ncrypt!NCryptGetProperty` at `0x180028d7e`
- `ncrypt!NCryptGetProperty` at `0x180028db5`
- `ncrypt!NCryptGetProperty` at `0x180028b3a`
- `ncrypt!NCryptGetProperty` at `0x180028b6d`
- `ncrypt!NCryptGetProperty` at `0x180028bc5`
- `ncrypt!NCryptGetProperty` at `0x180028c06`
- `ncrypt!NCryptGetProperty` at `0x180028c3b`
- `ncrypt!NCryptGetProperty` at `0x180028c89`
- `ncrypt!NCryptGetProperty` at `0x180028d7e`
- `ncrypt!NCryptGetProperty` at `0x180028db5`
- `ncrypt!NCryptOpenStorageProvider` at `0x180028a54`
- `ncrypt!NCryptOpenStorageProvider` at `0x180028a81`
- `ncrypt!NCryptOpenStorageProvider` at `0x180028ad3`
- `ncrypt!NCryptOpenStorageProvider` at `0x180028a54`
- `ncrypt!NCryptOpenStorageProvider` at `0x180028a81`
- `ncrypt!NCryptOpenStorageProvider` at `0x180028ad3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180028cff`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180028cff`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180028d37`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180028d37`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028dd6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028dfd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028dd6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028dfd`

## string_xrefs

- `0x180028ade`: `Failed to open TPM KSP`

## pseudocode

```c
__int64 __fastcall I_IsVscOperationAllowed(int a1, bool *a2)
{
  __int64 v4; // rcx
  unsigned int v5; // ebx
  __int64 v6; // rcx
  SECURITY_STATUS v7; // eax
  char v8; // al
  int v9; // edx
  const char *v10; // rcx
  __int64 v11; // rcx
  SECURITY_STATUS v12; // eax
  __int64 v13; // rcx
  SECURITY_STATUS Property; // eax
  char v15; // al
  PBYTE v16; // rcx
  bool v17; // bl
  SECURITY_STATUS v18; // eax
  PBYTE v19; // rcx
  DWORD cbOutput; // [rsp+30h] [rbp-49h] BYREF
  int v22; // [rsp+34h] [rbp-45h] BYREF
  NCRYPT_PROV_HANDLE phProvider; // [rsp+38h] [rbp-41h] BYREF
  BYTE Data[4]; // [rsp+40h] [rbp-39h] BYREF
  PBYTE pbOutput; // [rsp+48h] [rbp-31h] BYREF
  int v26; // [rsp+50h] [rbp-29h] BYREF
  DWORD cbData[2]; // [rsp+58h] [rbp-21h] BYREF
  HKEY phkResult; // [rsp+60h] [rbp-19h] BYREF
  _QWORD *v29; // [rsp+68h] [rbp-11h] BYREF
  _QWORD v30[3]; // [rsp+70h] [rbp-9h] BYREF
  char v31[24]; // [rsp+88h] [rbp+Fh] BYREF

  v22 = 0;
  v26 = 0;
  strcpy(v31, "I_IsVscOperationAllowed");
  v30[0] = v31;
  v30[1] = &v26;
  v30[2] = &v22;
  lambda_7c90d9368c5f299828ad7f8fa9a5505a_::operator()(v30);
  v26 = 1;
  v29 = v30;
  if ( (a1 & 3) != 0 )
  {
    phProvider = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(
      &phProvider,
      0);
    if ( NCryptOpenStorageProvider(&phProvider, L"Microsoft Platform Crypto Provider", 0) )
    {
      WppTraceIndent(v6, 2);
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(
        &phProvider,
        0);
      v7 = NCryptOpenStorageProvider(&phProvider, L"Microsoft Platform Crypto Provider", 0);
      v5 = I_MapSecurityStatusToWinError(v7);
      v22 = v5;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_39;
      }
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(
        &phProvider,
        0);
      v8 = NCryptOpenStorageProvider(&phProvider, L"Microsoft Platform Crypto Provider", 0);
      v9 = 49;
      v10 = "Failed to open TPM KSP";
    }
    else
    {
      cbOutput = 0;
      if ( !NCryptGetProperty(phProvider, L"PCP_TPM_IFX_RSA_KEYGEN_VULNERABILITY", 0, 0, &cbOutput, 0) )
      {
        wil::make_unique_hlocal<unsigned char [0]>(&pbOutput);
        if ( NCryptGetProperty(phProvider, L"PCP_TPM_IFX_RSA_KEYGEN_VULNERABILITY", pbOutput, cbOutput, &cbOutput, 0) )
        {
          WppTraceIndent(v13, 2);
          Property = NCryptGetProperty(
                       phProvider,
                       L"PCP_TPM_IFX_RSA_KEYGEN_VULNERABILITY",
                       pbOutput,
                       cbOutput,
                       &cbOutput,
                       0);
          v5 = I_MapSecurityStatusToWinError(Property);
          v22 = v5;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v15 = NCryptGetProperty(
                    phProvider,
                    L"PCP_TPM_IFX_RSA_KEYGEN_VULNERABILITY",
                    pbOutput,
                    cbOutput,
                    &cbOutput,
                    0);
            WPP_SF_sDs(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              51,
              (unsigned int)WPP_0b864d11e5aa35941b658d08f6a7e9ca_Traceguids,
              (_DWORD)WPP_pszIndent,
              v15,
              (__int64)"Failed to get vulnerability property");
            v5 = v22;
          }
          v16 = pbOutput;
        }
        else
        {
          v16 = pbOutput;
          if ( *pbOutput )
          {
            phkResult = 0;
            if ( RegOpenKeyExW(
                   HKEY_LOCAL_MACHINE,
                   L"Software\\Policies\\Microsoft\\Windows\\SmartCard",
                   0,
                   0x20019u,
                   &phkResult)
              || (*(_DWORD *)Data = 0,
                  cbData[0] = 4,
                  RegQueryValueExW(phkResult, L"BlockVscUsageOnVulnerableTPM", 0, 0, Data, cbData))
              || !*(_DWORD *)Data )
            {
              v17 = 1;
              if ( a1 == 2 )
              {
                *(_DWORD *)Data = 0;
                if ( NCryptGetProperty(phProvider, L"PCP_TPM_IFX_RSA_KEYGEN_PROHIBITED", 0, 0, (DWORD *)Data, 0) >= 0 )
                {
                  wil::make_unique_hlocal<unsigned char [0]>(cbData);
                  v18 = NCryptGetProperty(
                          phProvider,
                          L"PCP_TPM_IFX_RSA_KEYGEN_PROHIBITED",
                          *(PBYTE *)cbData,
                          *(DWORD *)Data,
                          (DWORD *)Data,
                          0);
                  v19 = *(PBYTE *)cbData;
                  if ( v18 >= 0 )
                    v17 = **(_BYTE **)cbData == 0;
                  *(_QWORD *)cbData = 0;
                  if ( v19 )
                    LocalFree(v19);
                }
              }
            }
            else
            {
              v17 = 0;
            }
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
            v16 = pbOutput;
          }
          else
          {
            v17 = 1;
          }
          *a2 = v17;
          v5 = v22;
        }
        pbOutput = 0;
        if ( v16 )
          LocalFree(v16);
        goto LABEL_39;
      }
      WppTraceIndent(v11, 2);
      v12 = NCryptGetProperty(phProvider, L"PCP_TPM_IFX_RSA_KEYGEN_VULNERABILITY", 0, 0, &cbOutput, 0);
      v5 = I_MapSecurityStatusToWinError(v12);
      v22 = v5;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
LABEL_39:
        wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phProvider);
        goto LABEL_40;
      }
      v8 = NCryptGetProperty(phProvider, L"PCP_TPM_IFX_RSA_KEYGEN_VULNERABILITY", 0, 0, &cbOutput, 0);
      v9 = 50;
      v10 = "Failed to query vulnerability property size";
    }
    WPP_SF_sDs(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v9,
      (unsigned int)WPP_0b864d11e5aa35941b658d08f6a7e9ca_Traceguids,
      (_DWORD)WPP_pszIndent,
      v8,
      (__int64)v10);
    v5 = v22;
    goto LABEL_39;
  }
  WppTraceIndent(v4, 2);
  v5 = 87;
  v22 = 87;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_sDs(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      48,
      (unsigned int)WPP_0b864d11e5aa35941b658d08f6a7e9ca_Traceguids,
      (_DWORD)WPP_pszIndent,
      87,
      (__int64)"Invalid flags");
    v5 = v22;
  }
LABEL_40:
  WppTraceUnwinder__lambda_7c90d9368c5f299828ad7f8fa9a5505a____::_WppTraceUnwinder__lambda_7c90d9368c5f299828ad7f8fa9a5505a____(&v29);
  return v5;
}

```

## disassembly

```asm
0x18002893c  mov     [rsp-8+arg_0], rbx
0x180028941  mov     [rsp-8+arg_10], rsi
0x180028946  push    rbp
0x180028947  push    rdi
0x180028948  push    r12
0x18002894a  push    r14
0x18002894c  push    r15
0x18002894e  lea     rbp, [rsp-37h]
0x180028953  sub     rsp, 0B0h
0x18002895a  mov     rax, cs:__security_cookie
0x180028961  xor     rax, rsp
0x180028964  mov     [rbp+57h+var_30], rax
0x180028968  mov     rsi, rdx
0x18002896b  mov     edi, ecx
0x18002896d  xor     r14d, r14d
0x180028970  mov     [rbp+57h+var_9C], r14d
0x180028974  mov     [rbp+57h+var_80], r14d
0x180028978  movups  xmm0, xmmword ptr cs:aIIsvscoperatio; "I_IsVscOperationAllowed"
0x18002897f  movups  xmmword ptr [rbp+57h+var_48], xmm0
0x180028983  movsd   xmm1, qword ptr cs:aIIsvscoperatio+10h; "Allowed"
0x18002898b  movsd   qword ptr [rbp+57h+var_48+10h], xmm1
0x180028990  lea     rax, [rbp+57h+var_48]
0x180028994  mov     [rbp+57h+var_60], rax
0x180028998  lea     rax, [rbp+57h+var_80]
0x18002899c  mov     [rbp+57h+var_58], rax
0x1800289a0  lea     rax, [rbp+57h+var_9C]
0x1800289a4  mov     [rbp+57h+var_50], rax
0x1800289a8  lea     rcx, [rbp+57h+var_60]
0x1800289ac  call    _lambda_7c90d9368c5f299828ad7f8fa9a5505a___operator__
0x1800289b1  lea     r15d, [r14+1]
0x1800289b5  mov     [rbp+57h+var_80], r15d
0x1800289b9  lea     rax, [rbp+57h+var_60]
0x1800289bd  mov     [rbp+57h+var_68], rax
0x1800289c1  test    dil, 3
0x1800289c5  jnz     short loc_180028A34
0x1800289c7  lea     edx, [r14+2]
0x1800289cb  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800289d0  lea     ebx, [r14+57h]
0x1800289d4  mov     [rbp+57h+var_9C], ebx
0x1800289d7  lea     rax, WPP_GLOBAL_Control
0x1800289de  mov     rcx, cs:WPP_GLOBAL_Control
0x1800289e5  cmp     rcx, rax
0x1800289e8  jz      loc_180028E0E
0x1800289ee  test    [rcx+1Ch], r15b
0x1800289f2  jz      loc_180028E0E
0x1800289f8  cmp     byte ptr [rcx+19h], 2
0x1800289fc  jb      loc_180028E0E
0x180028a02  lea     edx, [rbx-27h]
0x180028a05  lea     rax, aInvalidFlags; "Invalid flags"
0x180028a0c  mov     qword ptr [rsp+0D0h+dwFlags], rax
0x180028a11  mov     dword ptr [rsp+0D0h+pcbResult], ebx
0x180028a15  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180028a1c  lea     r8, WPP_0b864d11e5aa35941b658d08f6a7e9ca_Traceguids
0x180028a23  mov     rcx, [rcx+10h]
0x180028a27  call    WPP_SF_sDs
0x180028a2c  mov     ebx, [rbp+57h+var_9C]
0x180028a2f  jmp     loc_180028E0E
0x180028a34  mov     [rbp+57h+phProvider], r14
0x180028a38  xor     edx, edx
0x180028a3a  lea     rcx, [rbp+57h+phProvider]
0x180028a3e  call    ?reset@?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAAX_K@Z; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(unsigned __int64)
0x180028a43  xor     r8d, r8d; dwFlags
0x180028a46  lea     r12, pszProviderName; "Microsoft Platform Crypto Provider"
0x180028a4d  mov     rdx, r12; pszProviderName
0x180028a50  lea     rcx, [rbp+57h+phProvider]; phProvider
0x180028a54  call    cs:__imp_NCryptOpenStorageProvider
0x180028a5a  test    eax, eax
0x180028a5c  jz      loc_180028B14
0x180028a62  mov     edx, 2
0x180028a67  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180028a6c  xor     edx, edx
0x180028a6e  lea     rcx, [rbp+57h+phProvider]
0x180028a72  call    ?reset@?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAAX_K@Z; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(unsigned __int64)
0x180028a77  xor     r8d, r8d; dwFlags
0x180028a7a  mov     rdx, r12; pszProviderName
0x180028a7d  lea     rcx, [rbp+57h+phProvider]; phProvider
0x180028a81  call    cs:__imp_NCryptOpenStorageProvider
0x180028a87  mov     ecx, eax; int
0x180028a89  call    ?I_MapSecurityStatusToWinError@@YAKJ@Z; I_MapSecurityStatusToWinError(long)
0x180028a8e  mov     ebx, eax
0x180028a90  mov     [rbp+57h+var_9C], eax
0x180028a93  lea     rax, WPP_GLOBAL_Control
0x180028a9a  mov     rcx, cs:WPP_GLOBAL_Control
0x180028aa1  cmp     rcx, rax
0x180028aa4  jz      loc_180028E04
0x180028aaa  test    [rcx+1Ch], r15b
0x180028aae  jz      loc_180028E04
0x180028ab4  cmp     byte ptr [rcx+19h], 2
0x180028ab8  jb      loc_180028E04
0x180028abe  xor     edx, edx
0x180028ac0  lea     rcx, [rbp+57h+phProvider]
0x180028ac4  call    ?reset@?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAAX_K@Z; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(unsigned __int64)
0x180028ac9  xor     r8d, r8d; dwFlags
0x180028acc  mov     rdx, r12; pszProviderName
0x180028acf  lea     rcx, [rbp+57h+phProvider]; phProvider
0x180028ad3  call    cs:__imp_NCryptOpenStorageProvider
0x180028ad9  mov     edx, 31h ; '1'
0x180028ade  lea     rcx, aFailedToOpenTp; "Failed to open TPM KSP"
0x180028ae5  mov     qword ptr [rsp+0D0h+dwFlags], rcx
0x180028aea  mov     dword ptr [rsp+0D0h+pcbResult], eax
0x180028aee  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180028af5  lea     r8, WPP_0b864d11e5aa35941b658d08f6a7e9ca_Traceguids
0x180028afc  mov     rcx, cs:WPP_GLOBAL_Control
0x180028b03  mov     rcx, [rcx+10h]
0x180028b07  call    WPP_SF_sDs
0x180028b0c  mov     ebx, [rbp+57h+var_9C]
0x180028b0f  jmp     loc_180028E04
0x180028b14  mov     [rbp+57h+cbOutput], r14d
0x180028b18  mov     [rsp+0D0h+dwFlags], r14d; dwFlags
0x180028b1d  lea     rax, [rbp+57h+cbOutput]
0x180028b21  mov     [rsp+0D0h+pcbResult], rax; pcbResult
0x180028b26  xor     r9d, r9d; cbOutput
0x180028b29  xor     r8d, r8d; pbOutput
0x180028b2c  lea     r12, aPcpTpmIfxRsaKe_0; "PCP_TPM_IFX_RSA_KEYGEN_VULNERABILITY"
0x180028b33  mov     rdx, r12; pszProperty
0x180028b36  mov     rcx, [rbp+57h+phProvider]; hObject
0x180028b3a  call    cs:__imp_NCryptGetProperty
0x180028b40  test    eax, eax
0x180028b42  jz      loc_180028BDC
0x180028b48  mov     edx, 2
0x180028b4d  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180028b52  mov     [rsp+0D0h+dwFlags], r14d; dwFlags
0x180028b57  lea     rax, [rbp+57h+cbOutput]
0x180028b5b  mov     [rsp+0D0h+pcbResult], rax; pcbResult
0x180028b60  xor     r9d, r9d; cbOutput
0x180028b63  xor     r8d, r8d; pbOutput
0x180028b66  mov     rdx, r12; pszProperty
0x180028b69  mov     rcx, [rbp+57h+phProvider]; hObject
0x180028b6d  call    cs:__imp_NCryptGetProperty
0x180028b73  mov     ecx, eax; int
0x180028b75  call    ?I_MapSecurityStatusToWinError@@YAKJ@Z; I_MapSecurityStatusToWinError(long)
0x180028b7a  mov     ebx, eax
0x180028b7c  mov     [rbp+57h+var_9C], eax
0x180028b7f  lea     rax, WPP_GLOBAL_Control
0x180028b86  mov     rcx, cs:WPP_GLOBAL_Control
0x180028b8d  cmp     rcx, rax
0x180028b90  jz      loc_180028E04
0x180028b96  test    [rcx+1Ch], r15b
0x180028b9a  jz      loc_180028E04
0x180028ba0  cmp     byte ptr [rcx+19h], 2
0x180028ba4  jb      loc_180028E04
0x180028baa  mov     [rsp+0D0h+dwFlags], r14d; dwFlags
0x180028baf  lea     rax, [rbp+57h+cbOutput]
0x180028bb3  mov     [rsp+0D0h+pcbResult], rax; pcbResult
0x180028bb8  xor     r9d, r9d; cbOutput
0x180028bbb  xor     r8d, r8d; pbOutput
0x180028bbe  mov     rdx, r12; pszProperty
0x180028bc1  mov     rcx, [rbp+57h+phProvider]; hObject
0x180028bc5  call    cs:__imp_NCryptGetProperty
0x180028bcb  mov     edx, 32h ; '2'
0x180028bd0  lea     rcx, aFailedToQueryV; "Failed to query vulnerability property "...
0x180028bd7  jmp     loc_180028AE5
0x180028bdc  mov     edx, [rbp+57h+cbOutput]
0x180028bdf  lea     rcx, [rbp+57h+pbOutput]
0x180028be3  call    ??$make_unique_hlocal@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal<uchar [0]>(unsigned __int64)
0x180028be8  nop
0x180028be9  mov     [rsp+0D0h+dwFlags], r14d; dwFlags
0x180028bee  lea     rax, [rbp+57h+cbOutput]
0x180028bf2  mov     [rsp+0D0h+pcbResult], rax; pcbResult
0x180028bf7  mov     r9d, [rbp+57h+cbOutput]; cbOutput
0x180028bfb  mov     r8, [rbp+57h+pbOutput]; pbOutput
0x180028bff  mov     rdx, r12; pszProperty
0x180028c02  mov     rcx, [rbp+57h+phProvider]; hObject
0x180028c06  call    cs:__imp_NCryptGetProperty
0x180028c0c  test    eax, eax
0x180028c0e  jz      loc_180028CCE
0x180028c14  mov     edx, 2
0x180028c19  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180028c1e  mov     [rsp+0D0h+dwFlags], r14d; dwFlags
0x180028c23  lea     rax, [rbp+57h+cbOutput]
0x180028c27  mov     [rsp+0D0h+pcbResult], rax; pcbResult
0x180028c2c  mov     r9d, [rbp+57h+cbOutput]; cbOutput
0x180028c30  mov     r8, [rbp+57h+pbOutput]; pbOutput
0x180028c34  mov     rdx, r12; pszProperty
0x180028c37  mov     rcx, [rbp+57h+phProvider]; hObject
0x180028c3b  call    cs:__imp_NCryptGetProperty
0x180028c41  mov     ecx, eax; int
0x180028c43  call    ?I_MapSecurityStatusToWinError@@YAKJ@Z; I_MapSecurityStatusToWinError(long)
0x180028c48  mov     ebx, eax
0x180028c4a  mov     [rbp+57h+var_9C], eax
0x180028c4d  lea     rax, WPP_GLOBAL_Control
0x180028c54  mov     rcx, cs:WPP_GLOBAL_Control
0x180028c5b  cmp     rcx, rax
0x180028c5e  jz      short loc_180028CC5
0x180028c60  test    [rcx+1Ch], r15b
0x180028c64  jz      short loc_180028CC5
0x180028c66  cmp     byte ptr [rcx+19h], 2
0x180028c6a  jb      short loc_180028CC5
0x180028c6c  mov     [rsp+0D0h+dwFlags], r14d; dwFlags
0x180028c71  lea     rax, [rbp+57h+cbOutput]
0x180028c75  mov     [rsp+0D0h+pcbResult], rax; pcbResult
0x180028c7a  mov     r9d, [rbp+57h+cbOutput]; cbOutput
0x180028c7e  mov     r8, [rbp+57h+pbOutput]; pbOutput
0x180028c82  mov     rdx, r12; pszProperty
0x180028c85  mov     rcx, [rbp+57h+phProvider]; hObject
0x180028c89  call    cs:__imp_NCryptGetProperty
0x180028c8f  mov     edx, 33h ; '3'
0x180028c94  lea     rcx, aFailedToGetVul; "Failed to get vulnerability property"
0x180028c9b  mov     qword ptr [rsp+0D0h+dwFlags], rcx
0x180028ca0  mov     dword ptr [rsp+0D0h+pcbResult], eax
0x180028ca4  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180028cab  lea     r8, WPP_0b864d11e5aa35941b658d08f6a7e9ca_Traceguids
0x180028cb2  mov     rcx, cs:WPP_GLOBAL_Control
0x180028cb9  mov     rcx, [rcx+10h]
0x180028cbd  call    WPP_SF_sDs
0x180028cc2  mov     ebx, [rbp+57h+var_9C]
0x180028cc5  mov     rcx, [rbp+57h+pbOutput]
0x180028cc9  jmp     loc_180028DF4
0x180028cce  mov     rcx, [rbp+57h+pbOutput]; hMem
0x180028cd2  cmp     [rcx], r14b
0x180028cd5  jz      loc_180028DEC
0x180028cdb  mov     [rbp+57h+phkResult], r14
0x180028cdf  lea     rax, [rbp+57h+phkResult]
0x180028ce3  mov     [rsp+0D0h+pcbResult], rax; phkResult
0x180028ce8  mov     r9d, 20019h; samDesired
0x180028cee  xor     r8d, r8d; ulOptions
0x180028cf1  lea     rdx, SubKey; "Software\\Policies\\Microsoft\\Windows"...
0x180028cf8  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180028cff  call    cs:__imp_RegOpenKeyExW
0x180028d05  test    eax, eax
0x180028d07  jnz     short loc_180028D4F
0x180028d09  mov     dword ptr [rbp+57h+Data], r14d
0x180028d0d  mov     [rbp+57h+cbData], 4
0x180028d14  lea     rax, [rbp+57h+cbData]
0x180028d18  mov     qword ptr [rsp+0D0h+dwFlags], rax; lpcbData
0x180028d1d  lea     rax, [rbp+57h+Data]
0x180028d21  mov     [rsp+0D0h+pcbResult], rax; lpData
0x180028d26  xor     r9d, r9d; lpType
0x180028d29  xor     r8d, r8d; lpReserved
0x180028d2c  lea     rdx, ValueName; "BlockVscUsageOnVulnerableTPM"
0x180028d33  mov     rcx, [rbp+57h+phkResult]; hKey
0x180028d37  call    cs:__imp_RegQueryValueExW
0x180028d3d  test    eax, eax
0x180028d3f  jnz     short loc_180028D4F
0x180028d41  cmp     dword ptr [rbp+57h+Data], r14d
0x180028d45  jz      short loc_180028D4F
0x180028d47  mov     bl, r14b
0x180028d4a  jmp     loc_180028DDD
0x180028d4f  mov     bl, r15b
0x180028d52  cmp     edi, 2
0x180028d55  jnz     loc_180028DDD
0x180028d5b  mov     dword ptr [rbp+57h+Data], r14d
0x180028d5f  mov     [rsp+0D0h+dwFlags], r14d; dwFlags
0x180028d64  lea     rax, [rbp+57h+Data]
0x180028d68  mov     [rsp+0D0h+pcbResult], rax; pcbResult
0x180028d6d  xor     r9d, r9d; cbOutput
0x180028d70  xor     r8d, r8d; pbOutput
0x180028d73  lea     rdx, aPcpTpmIfxRsaKe; "PCP_TPM_IFX_RSA_KEYGEN_PROHIBITED"
0x180028d7a  mov     rcx, [rbp+57h+phProvider]; hObject
0x180028d7e  call    cs:__imp_NCryptGetProperty
0x180028d84  test    eax, eax
0x180028d86  js      short loc_180028DDD
0x180028d88  mov     edx, dword ptr [rbp+57h+Data]
0x180028d8b  lea     rcx, [rbp+57h+cbData]
0x180028d8f  call    ??$make_unique_hlocal@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal<uchar [0]>(unsigned __int64)
0x180028d94  mov     [rsp+0D0h+dwFlags], r14d; dwFlags
0x180028d99  lea     rax, [rbp+57h+Data]
0x180028d9d  mov     [rsp+0D0h+pcbResult], rax; pcbResult
0x180028da2  mov     r9d, dword ptr [rbp+57h+Data]; cbOutput
0x180028da6  mov     r8, qword ptr [rbp+57h+cbData]; pbOutput
0x180028daa  lea     rdx, aPcpTpmIfxRsaKe; "PCP_TPM_IFX_RSA_KEYGEN_PROHIBITED"
0x180028db1  mov     rcx, [rbp+57h+phProvider]; hObject
0x180028db5  call    cs:__imp_NCryptGetProperty
0x180028dbb  mov     rcx, qword ptr [rbp+57h+cbData]; hMem
0x180028dbf  test    eax, eax
0x180028dc1  js      short loc_180028DCD
0x180028dc3  mov     ebx, r15d
0x180028dc6  cmp     [rcx], r14b
0x180028dc9  cmovnz  ebx, r14d
0x180028dcd  mov     qword ptr [rbp+57h+cbData], r14
0x180028dd1  test    rcx, rcx
0x180028dd4  jz      short loc_180028DDD
0x180028dd6  call    cs:__imp_LocalFree
0x180028ddc  nop
0x180028ddd  lea     rcx, [rbp+57h+phkResult]
0x180028de1  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180028de6  mov     rcx, [rbp+57h+pbOutput]
0x180028dea  jmp     short loc_180028DEF
0x180028dec  mov     bl, r15b
0x180028def  mov     [rsi], bl
0x180028df1  mov     ebx, [rbp+57h+var_9C]
0x180028df4  test    rcx, rcx
0x180028df7  mov     [rbp+57h+pbOutput], r14
0x180028dfb  jz      short loc_180028E04
0x180028dfd  call    cs:__imp_LocalFree
0x180028e03  nop
0x180028e04  lea     rcx, [rbp+57h+phProvider]
0x180028e08  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x180028e0d  nop
0x180028e0e  lea     rcx, [rbp+57h+var_68]
0x180028e12  call    WppTraceUnwinder__lambda_7c90d9368c5f299828ad7f8fa9a5505a_______WppTraceUnwinder__lambda_7c90d9368c5f299828ad7f8fa9a5505a____
0x180028e17  mov     eax, ebx
0x180028e19  mov     rcx, [rbp+57h+var_30]
0x180028e1d  xor     rcx, rsp; StackCookie
0x180028e20  call    __security_check_cookie
0x180028e25  lea     r11, [rsp+0D0h+var_20]
0x180028e2d  mov     rbx, [r11+30h]
0x180028e31  mov     rsi, [r11+40h]
0x180028e35  mov     rsp, r11
0x180028e38  pop     r15
  ... truncated ...
```
