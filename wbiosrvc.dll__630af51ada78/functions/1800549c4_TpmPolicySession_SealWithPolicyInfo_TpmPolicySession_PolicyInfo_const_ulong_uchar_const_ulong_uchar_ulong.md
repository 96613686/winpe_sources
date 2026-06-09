# TpmPolicySession::SealWithPolicyInfo(TpmPolicySession::PolicyInfo const *,ulong,uchar const *,ulong,uchar * *,ulong *)

- ea: `0x1800549c4`
- end: `0x180054dfa`
- name: `?SealWithPolicyInfo@TpmPolicySession@@YAJPEBUPolicyInfo@1@KPEBEKPEAPEAEPEAK@Z`
- size: `1078`
- prototype: `int(TpmPolicySession *__hidden this, const struct TpmPolicySession::PolicyInfo *, unsigned int, const unsigned __int8 *, unsigned int, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800538d4`

## callees

- `0x1800351e0`
- `0x18003f2dc`
- `0x1800430bc`
- `0x18005388c`
- `0x1800538b0`
- `0x1800549c4`
- `0x180058680`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180054b65`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180054c71`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180054c86`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180054cfe`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180054d14`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180054d4a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180054d60`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180054db5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180054b65`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180054c71`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180054c86`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180054cfe`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180054d14`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180054d4a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180054d60`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180054db5`
- `ncrypt!NCryptEncrypt` at `0x180054c19`
- `ncrypt!NCryptEncrypt` at `0x180054cc2`
- `ncrypt!NCryptEncrypt` at `0x180054c19`
- `ncrypt!NCryptEncrypt` at `0x180054cc2`
- `ncrypt!NCryptOpenKey` at `0x180054a58`
- `ncrypt!NCryptOpenKey` at `0x180054a58`
- `ncrypt!NCryptOpenStorageProvider` at `0x180054a00`
- `ncrypt!NCryptOpenStorageProvider` at `0x180054a00`

## string_xrefs

- `0x180054a17`: `onecore\ds\security\biometrics\service\trustlet\lib\tpmpolicysession.cpp`
- `0x180054a6f`: `onecore\ds\security\biometrics\service\trustlet\lib\tpmpolicysession.cpp`
- `0x180054aca`: `onecore\ds\security\biometrics\service\trustlet\lib\tpmpolicysession.cpp`
- `0x180054b40`: `onecore\ds\security\biometrics\service\trustlet\lib\tpmpolicysession.cpp`
- `0x180054c30`: `onecore\ds\security\biometrics\service\trustlet\lib\tpmpolicysession.cpp`
- `0x180054cdd`: `onecore\ds\security\biometrics\service\trustlet\lib\tpmpolicysession.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall TpmPolicySession::SealWithPolicyInfo(
        const void *const *this,
        const struct TpmPolicySession::PolicyInfo *a2,
        BYTE *a3,
        const unsigned __int8 *a4,
        PBYTE *a5,
        unsigned __int8 **a6)
{
  DWORD v6; // r12d
  SECURITY_STATUS v9; // eax
  unsigned int v10; // edi
  __int64 result; // rax
  SECURITY_STATUS v12; // eax
  unsigned int v13; // edi
  unsigned int v14; // edi
  TpmPolicySession *v15; // r14
  const void *const *i; // rcx
  unsigned int v17; // ebx
  int v18; // r15d
  HLOCAL v19; // rcx
  const char *v20; // r9
  unsigned int v21; // esi
  SECURITY_STATUS v22; // eax
  int v23; // ebx
  BYTE **unique; // rax
  BYTE *v25; // rdx
  PBYTE v26; // rcx
  HLOCAL v27; // rcx
  SECURITY_STATUS v28; // eax
  PBYTE v29; // rcx
  HLOCAL v30; // rcx
  PBYTE v31; // rcx
  HLOCAL v32; // rcx
  int dwFlags; // [rsp+20h] [rbp-98h]
  int dwFlagsa; // [rsp+20h] [rbp-98h]
  int dwFlagsb; // [rsp+20h] [rbp-98h]
  int dwFlagsc; // [rsp+20h] [rbp-98h]
  PBYTE pbOutput; // [rsp+40h] [rbp-78h] BYREF
  HLOCAL hMem; // [rsp+48h] [rbp-70h] BYREF
  NCRYPT_KEY_HANDLE phKey; // [rsp+50h] [rbp-68h] BYREF
  NCRYPT_PROV_HANDLE hProvider; // [rsp+58h] [rbp-60h] BYREF
  HLOCAL v41; // [rsp+60h] [rbp-58h] BYREF
  _DWORD pPaddingInfo[2]; // [rsp+68h] [rbp-50h] BYREF
  _DWORD *v43; // [rsp+70h] [rbp-48h]
  _DWORD v44[2]; // [rsp+78h] [rbp-40h] BYREF
  HLOCAL v45; // [rsp+80h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]
  DWORD cbOutput; // [rsp+C8h] [rbp+10h] BYREF

  cbOutput = (unsigned int)a2;
  v6 = (unsigned int)a4;
  hProvider = 0;
  v9 = NCryptOpenStorageProvider(&hProvider, L"Microsoft Platform Crypto Provider", 0);
  v10 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xBD,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\lib\\tpmpolicysession.cpp",
      (const char *)(unsigned int)v9,
      dwFlags);
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&hProvider);
    return v10;
  }
  phKey = 0;
  v12 = NCryptOpenKey(hProvider, &phKey, L"MICROSOFT_PCP_KSP_RSA_SEAL_KEY_3BD1C4BF-004E-4E2F-8A4D-0BF633DCB074", 0, 0);
  v13 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC6,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\lib\\tpmpolicysession.cpp",
      (const char *)(unsigned int)v12,
      dwFlagsa);
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phKey);
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&hProvider);
    return v13;
  }
  v14 = 0;
  v15 = (TpmPolicySession *)(this + 2);
  for ( i = this; i != (const void *const *)v15; i += 2 )
  {
    if ( v14 + *(_DWORD *)i < v14 )
    {
      v17 = wil::details::in1diag3::Return_NtStatus(
              retaddr,
              (void *)0xCF,
              (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\lib\\tpmpolicysession.cpp",
              (const char *)0xC0000095LL,
              dwFlagsa);
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phKey);
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&hProvider);
      return v17;
    }
    v14 += *(_DWORD *)i;
  }
  try
  {
    wil::make_unique_hlocal<unsigned char [0]>(&hMem);
    v21 = 0;
    while ( this != (const void *const *)v15 )
    {
      v18 = *(_DWORD *)this;
      if ( memcpy_s_0((char *)hMem + v21, v14 - v21, this[1], *(unsigned int *)this) )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xDC,
          (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\lib\\tpmpolicysession.cpp",
          (const char *)0x8000FFFFLL,
          dwFlagsa);
        v19 = hMem;
        hMem = 0;
        if ( v19 )
          LocalFree(v19);
        wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phKey);
        wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&hProvider);
        return 2147549183LL;
      }
      v21 += v18;
      this += 2;
    }
    v44[0] = v14;
    v44[1] = 71;
    v45 = hMem;
    pPaddingInfo[0] = 0;
    pPaddingInfo[1] = 1;
    v43 = v44;
    cbOutput = 2048;
    wil::make_unique_hlocal<unsigned char [0]>(&pbOutput);
    v22 = NCryptEncrypt(phKey, a3, v6, pPaddingInfo, pbOutput, cbOutput, &cbOutput, 0x100u);
    v23 = v22;
    if ( v22 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xF5,
        (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\lib\\tpmpolicysession.cpp",
        (const char *)(unsigned int)v22,
        dwFlagsb);
    if ( v23 == -2146893784 )
    {
      unique = (BYTE **)wil::make_unique_hlocal<unsigned char [0]>(&v41);
      v25 = *unique;
      *unique = 0;
      v26 = pbOutput;
      pbOutput = v25;
      if ( v26 )
        LocalFree(v26);
      v27 = v41;
      v41 = 0;
      if ( v27 )
        LocalFree(v27);
      v28 = NCryptEncrypt(phKey, a3, v6, pPaddingInfo, pbOutput, cbOutput, &cbOutput, 0x100u);
      v23 = v28;
      if ( v28 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x102,
          (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\lib\\tpmpolicysession.cpp",
          (const char *)(unsigned int)v28,
          dwFlagsc);
        v29 = pbOutput;
        pbOutput = 0;
        if ( v29 )
          LocalFree(v29);
        v30 = hMem;
        hMem = 0;
        if ( !v30 )
          goto LABEL_28;
        goto LABEL_27;
      }
    }
    else if ( v23 < 0 )
    {
      v31 = pbOutput;
      pbOutput = 0;
      if ( v31 )
        LocalFree(v31);
      v30 = hMem;
      hMem = 0;
      if ( !v30 )
        goto LABEL_28;
LABEL_27:
      LocalFree(v30);
LABEL_28:
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phKey);
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&hProvider);
      return (unsigned int)v23;
    }
    *a5 = pbOutput;
    *(_DWORD *)a6 = cbOutput;
    pbOutput = 0;
    v32 = hMem;
    hMem = 0;
    if ( v32 )
      LocalFree(v32);
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phKey);
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&hProvider);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x10C,
                           (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\lib\\tpmpolicysession.cpp",
                           v20);
  }
  return result;
}

```

## disassembly

```asm
0x1800549c4  mov     rax, rsp
0x1800549c7  mov     [rax+8], rbx
0x1800549cb  mov     [rax+18h], rsi
0x1800549cf  mov     [rax+10h], edx
0x1800549d2  push    rdi
0x1800549d3  push    r12
0x1800549d5  push    r13
0x1800549d7  push    r14
0x1800549d9  push    r15
0x1800549db  sub     rsp, 90h
0x1800549e2  mov     r12d, r9d
0x1800549e5  mov     r13, r8
0x1800549e8  mov     rbx, rcx
0x1800549eb  xor     r15d, r15d
0x1800549ee  mov     [rax-60h], r15
0x1800549f2  xor     r8d, r8d; dwFlags
0x1800549f5  lea     rdx, pszProviderName; "Microsoft Platform Crypto Provider"
0x1800549fc  lea     rcx, [rax-60h]; phProvider
0x180054a00  call    cs:__imp_NCryptOpenStorageProvider
0x180054a06  mov     edi, eax
0x180054a08  test    eax, eax
0x180054a0a  jns     short loc_180054A3A
0x180054a0c  mov     rcx, [rsp+0B8h]; this
0x180054a14  mov     r9d, eax; char *
0x180054a17  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\biometrics\\serv"...
0x180054a1e  mov     edx, 0BDh; void *
0x180054a23  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180054a28  nop
0x180054a29  lea     rcx, [rsp+0B8h+hProvider]
0x180054a2e  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x180054a33  mov     eax, edi
0x180054a35  jmp     loc_180054DDD
0x180054a3a  mov     [rsp+0B8h+phKey], r15
0x180054a3f  mov     [rsp+0B8h+dwFlags], r15d; int
0x180054a44  xor     r9d, r9d; dwLegacyKeySpec
0x180054a47  lea     r8, pszKeyName; "MICROSOFT_PCP_KSP_RSA_SEAL_KEY_3BD1C4BF"...
0x180054a4e  lea     rdx, [rsp+0B8h+phKey]; phKey
0x180054a53  mov     rcx, [rsp+0B8h+hProvider]; hProvider
0x180054a58  call    cs:__imp_NCryptOpenKey
0x180054a5e  mov     edi, eax
0x180054a60  test    eax, eax
0x180054a62  jns     short loc_180054A9D
0x180054a64  mov     rcx, [rsp+0B8h]; this
0x180054a6c  mov     r9d, eax; char *
0x180054a6f  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\biometrics\\serv"...
0x180054a76  mov     edx, 0C6h; void *
0x180054a7b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180054a80  nop
0x180054a81  lea     rcx, [rsp+0B8h+phKey]
0x180054a86  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x180054a8b  nop
0x180054a8c  lea     rcx, [rsp+0B8h+hProvider]
0x180054a91  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x180054a96  mov     eax, edi
0x180054a98  jmp     loc_180054DDD
0x180054a9d  mov     edi, r15d
0x180054aa0  lea     r14, [rbx+10h]
0x180054aa4  mov     rcx, rbx
0x180054aa7  cmp     rcx, r14
0x180054aaa  jz      short loc_180054AF9
0x180054aac  mov     edx, [rcx]
0x180054aae  add     edx, edi
0x180054ab0  cmp     edx, edi
0x180054ab2  jb      short loc_180054ABC
0x180054ab4  mov     edi, edx
0x180054ab6  add     rcx, 10h
0x180054aba  jmp     short loc_180054AA7
0x180054abc  mov     rcx, [rsp+0B8h]; this
0x180054ac4  mov     r9d, 0C0000095h; char *
0x180054aca  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\biometrics\\serv"...
0x180054ad1  mov     edx, 0CFh; void *
0x180054ad6  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180054adb  mov     ebx, eax
0x180054add  lea     rcx, [rsp+0B8h+phKey]
0x180054ae2  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x180054ae7  nop
0x180054ae8  lea     rcx, [rsp+0B8h+hProvider]
0x180054aed  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x180054af2  mov     eax, ebx
0x180054af4  jmp     loc_180054DDD
0x180054af9  mov     edx, edi
0x180054afb  lea     rcx, [rsp+0B8h+hMem]
0x180054b00  call    ??$make_unique_hlocal@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal<uchar [0]>(unsigned __int64)
0x180054b05  nop
0x180054b06  mov     esi, r15d
0x180054b09  cmp     rbx, r14
0x180054b0c  jz      loc_180054B94
0x180054b12  mov     r15d, [rbx]
0x180054b15  mov     r9d, r15d; SourceSize
0x180054b18  mov     edx, edi
0x180054b1a  sub     edx, esi; DestinationSize
0x180054b1c  mov     ecx, esi
0x180054b1e  add     rcx, [rsp+0B8h+hMem]; Destination
0x180054b23  mov     r8, [rbx+8]; Source
0x180054b27  call    memcpy_s_0
0x180054b2c  test    eax, eax
0x180054b2e  jz      short loc_180054B88
0x180054b30  mov     rcx, [rsp+0B8h]; this
0x180054b38  mov     ebx, 8000FFFFh
0x180054b3d  mov     r9d, ebx; char *
0x180054b40  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\biometrics\\serv"...
0x180054b47  mov     edx, 0DCh; void *
0x180054b4c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180054b51  nop
0x180054b52  mov     rcx, [rsp+0B8h+hMem]; hMem
0x180054b57  mov     [rsp+0B8h+hMem], 0
0x180054b60  test    rcx, rcx
0x180054b63  jz      short loc_180054B6C
0x180054b65  call    cs:__imp_LocalFree
0x180054b6b  nop
0x180054b6c  lea     rcx, [rsp+0B8h+phKey]
0x180054b71  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x180054b76  nop
0x180054b77  lea     rcx, [rsp+0B8h+hProvider]
0x180054b7c  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x180054b81  mov     eax, ebx
0x180054b83  jmp     loc_180054DDD
0x180054b88  add     esi, r15d
0x180054b8b  add     rbx, 10h
0x180054b8f  jmp     loc_180054B09
0x180054b94  mov     [rsp+0B8h+var_40], edi
0x180054b98  mov     [rsp+0B8h+var_3C], 47h ; 'G'
0x180054ba0  mov     rax, [rsp+0B8h+hMem]
0x180054ba5  mov     [rsp+0B8h+var_38], rax
0x180054bad  xor     r15d, r15d
0x180054bb0  mov     [rsp+0B8h+pPaddingInfo], r15d
0x180054bb5  mov     [rsp+0B8h+var_4C], 1
0x180054bbd  lea     rax, [rsp+0B8h+var_40]
0x180054bc2  mov     [rsp+0B8h+var_48], rax
0x180054bc7  mov     edx, 800h
0x180054bcc  mov     [rsp+0B8h+arg_8], edx
0x180054bd3  lea     rcx, [rsp+0B8h+pbOutput]
0x180054bd8  call    ??$make_unique_hlocal@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal<uchar [0]>(unsigned __int64)
0x180054bdd  nop
0x180054bde  mov     eax, [rsp+0B8h+arg_8]
0x180054be5  mov     rdx, [rsp+0B8h+pbOutput]
0x180054bea  mov     edi, 100h
0x180054bef  mov     [rsp+0B8h+var_80], edi; dwFlags
0x180054bf3  lea     rcx, [rsp+0B8h+arg_8]
0x180054bfb  mov     [rsp+0B8h+pcbResult], rcx; pcbResult
0x180054c00  mov     [rsp+0B8h+cbOutput], eax; cbOutput
0x180054c04  mov     qword ptr [rsp+0B8h+dwFlags], rdx; int
0x180054c09  lea     r9, [rsp+0B8h+pPaddingInfo]; pPaddingInfo
0x180054c0e  mov     r8d, r12d; cbInput
0x180054c11  mov     rdx, r13; pbInput
0x180054c14  mov     rcx, [rsp+0B8h+phKey]; hKey
0x180054c19  call    cs:__imp_NCryptEncrypt
0x180054c1f  mov     ebx, eax
0x180054c21  mov     rcx, [rsp+0B8h]; this
0x180054c29  test    eax, eax
0x180054c2b  jns     short loc_180054C3F
0x180054c2d  mov     r9d, eax; char *
0x180054c30  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\biometrics\\serv"...
0x180054c37  lea     edx, [rdi-0Bh]; void *
0x180054c3a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180054c3f  cmp     ebx, 80090028h
0x180054c45  jnz     loc_180054D37
0x180054c4b  mov     edx, [rsp+0B8h+arg_8]
0x180054c52  lea     rcx, [rsp+0B8h+var_58]
0x180054c57  call    ??$make_unique_hlocal@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal<uchar [0]>(unsigned __int64)
0x180054c5c  mov     rdx, [rax]
0x180054c5f  mov     [rax], r15
0x180054c62  mov     rcx, [rsp+0B8h+pbOutput]; hMem
0x180054c67  mov     [rsp+0B8h+pbOutput], rdx
0x180054c6c  test    rcx, rcx
0x180054c6f  jz      short loc_180054C77
0x180054c71  call    cs:__imp_LocalFree
0x180054c77  mov     rcx, [rsp+0B8h+var_58]; hMem
0x180054c7c  mov     [rsp+0B8h+var_58], r15
0x180054c81  test    rcx, rcx
0x180054c84  jz      short loc_180054C8C
0x180054c86  call    cs:__imp_LocalFree
0x180054c8c  mov     eax, [rsp+0B8h+arg_8]
0x180054c93  mov     rdx, [rsp+0B8h+pbOutput]
0x180054c98  mov     [rsp+0B8h+var_80], edi; dwFlags
0x180054c9c  lea     rcx, [rsp+0B8h+arg_8]
0x180054ca4  mov     [rsp+0B8h+pcbResult], rcx; pcbResult
0x180054ca9  mov     [rsp+0B8h+cbOutput], eax; cbOutput
0x180054cad  mov     qword ptr [rsp+0B8h+dwFlags], rdx; int
0x180054cb2  lea     r9, [rsp+0B8h+pPaddingInfo]; pPaddingInfo
0x180054cb7  mov     r8d, r12d; cbInput
0x180054cba  mov     rdx, r13; pbInput
0x180054cbd  mov     rcx, [rsp+0B8h+phKey]; hKey
0x180054cc2  call    cs:__imp_NCryptEncrypt
0x180054cc8  mov     ebx, eax
0x180054cca  test    eax, eax
0x180054ccc  jns     loc_180054D80
0x180054cd2  mov     rcx, [rsp+0B8h]; this
0x180054cda  mov     r9d, eax; char *
0x180054cdd  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\biometrics\\serv"...
0x180054ce4  mov     edx, 102h; void *
0x180054ce9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180054cee  nop
0x180054cef  mov     rcx, [rsp+0B8h+pbOutput]; hMem
0x180054cf4  mov     [rsp+0B8h+pbOutput], r15
0x180054cf9  test    rcx, rcx
0x180054cfc  jz      short loc_180054D05
0x180054cfe  call    cs:__imp_LocalFree
0x180054d04  nop
0x180054d05  mov     rcx, [rsp+0B8h+hMem]; hMem
0x180054d0a  mov     [rsp+0B8h+hMem], r15
0x180054d0f  test    rcx, rcx
0x180054d12  jz      short loc_180054D1B
0x180054d14  call    cs:__imp_LocalFree
0x180054d1a  nop
0x180054d1b  lea     rcx, [rsp+0B8h+phKey]
0x180054d20  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x180054d25  nop
0x180054d26  lea     rcx, [rsp+0B8h+hProvider]
0x180054d2b  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x180054d30  mov     eax, ebx
0x180054d32  jmp     loc_180054DDD
0x180054d37  test    ebx, ebx
0x180054d39  jns     short loc_180054D80
0x180054d3b  mov     rcx, [rsp+0B8h+pbOutput]; hMem
0x180054d40  mov     [rsp+0B8h+pbOutput], r15
0x180054d45  test    rcx, rcx
0x180054d48  jz      short loc_180054D51
0x180054d4a  call    cs:__imp_LocalFree
0x180054d50  nop
0x180054d51  mov     rcx, [rsp+0B8h+hMem]; hMem
0x180054d56  mov     [rsp+0B8h+hMem], r15
0x180054d5b  test    rcx, rcx
0x180054d5e  jz      short loc_180054D67
0x180054d60  call    cs:__imp_LocalFree
0x180054d66  nop
0x180054d67  lea     rcx, [rsp+0B8h+phKey]
0x180054d6c  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x180054d71  nop
0x180054d72  lea     rcx, [rsp+0B8h+hProvider]
0x180054d77  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x180054d7c  mov     eax, ebx
0x180054d7e  jmp     short loc_180054DDD
0x180054d80  mov     rcx, [rsp+0B8h+arg_20]
0x180054d88  mov     rax, [rsp+0B8h+pbOutput]
0x180054d8d  mov     [rcx], rax
0x180054d90  mov     rcx, [rsp+0B8h+arg_28]
0x180054d98  mov     eax, [rsp+0B8h+arg_8]
0x180054d9f  mov     [rcx], eax
0x180054da1  mov     [rsp+0B8h+pbOutput], r15
0x180054da6  mov     rcx, [rsp+0B8h+hMem]; hMem
0x180054dab  mov     [rsp+0B8h+hMem], r15
0x180054db0  test    rcx, rcx
0x180054db3  jz      short loc_180054DBC
0x180054db5  call    cs:__imp_LocalFree
0x180054dbb  nop
0x180054dbc  lea     rcx, [rsp+0B8h+phKey]
0x180054dc1  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x180054dc6  nop
0x180054dc7  lea     rcx, [rsp+0B8h+hProvider]
0x180054dcc  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x180054dd1  nop
0x180054dd2  xor     eax, eax
0x180054dd4  jmp     short loc_180054DDD
0x180054dd6  mov     eax, [rsp+0B8h+arg_8]
0x180054ddd  lea     r11, [rsp+0B8h+var_28]
0x180054de5  mov     rbx, [r11+30h]
0x180054de9  mov     rsi, [r11+40h]
0x180054ded  mov     rsp, r11
0x180054df0  pop     r15
0x180054df2  pop     r14
0x180054df4  pop     r13
0x180054df6  pop     r12
0x180054df8  pop     rdi
0x180054df9  retn
```
