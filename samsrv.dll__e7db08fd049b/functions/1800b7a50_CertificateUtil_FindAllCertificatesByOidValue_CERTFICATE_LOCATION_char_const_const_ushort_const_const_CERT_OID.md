# CertificateUtil::FindAllCertificatesByOidValue(_CERTFICATE_LOCATION,char const * * const,ushort const * * const,_CERT_OID_VALUE_TYPE * const,ulong,_CERT_CONTEXT const * * const,ulong *)

- ea: `0x1800b7a50`
- end: `0x1800b7fa9`
- name: `?FindAllCertificatesByOidValue@CertificateUtil@@SAJW4_CERTFICATE_LOCATION@@QEAPEBDQEAPEBGQEAW4_CERT_OID_VALUE_TYPE@@KQEAPEBU_CERT_CONTEXT@@PEAK@Z`
- size: `1369`
- prototype: `__int64 __fastcall(int, __int64, __int64, __int64, unsigned int, struct _CERT_CONTEXT **, unsigned int *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800b91b0`

## callees

- `0x1800269d4`
- `0x180026b54`
- `0x1800b7104`
- `0x1800b719c`
- `0x1800b78b0`
- `0x1800b7a50`
- `0x1800b7fb0`
- `0x1800b8444`
- `0x1800b8a94`
- `0x1800b8acc`
- `0x1800b8b08`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b7c9e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b7f01`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b7c9e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b7f01`
- `api-ms-win-core-registry-l1-1-0!RegUnLoadKeyW` at `0x1800b7bb5`
- `api-ms-win-core-registry-l1-1-0!RegUnLoadKeyW` at `0x1800b7f65`
- `api-ms-win-core-registry-l1-1-0!RegUnLoadKeyW` at `0x1800b7bb5`
- `api-ms-win-core-registry-l1-1-0!RegUnLoadKeyW` at `0x1800b7f65`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800b7b7e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800b7c31`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800b7b7e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800b7c31`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b7f2d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b7f2d`
- `CRYPT32!CertFreeCertificateContext` at `0x1800b7ec8`
- `CRYPT32!CertFreeCertificateContext` at `0x1800b7ec8`
- `CRYPT32!CertCloseStore` at `0x1800b7ef7`
- `CRYPT32!CertCloseStore` at `0x1800b7ef7`
- `CRYPT32!CertFindCertificateInStore` at `0x1800b7ce3`
- `CRYPT32!CertFindCertificateInStore` at `0x1800b7ce3`
- `CRYPT32!CertDuplicateCertificateContext` at `0x1800b7e0d`
- `CRYPT32!CertDuplicateCertificateContext` at `0x1800b7e0d`
- `CRYPT32!CertOpenStore` at `0x1800b7c8b`
- `CRYPT32!CertOpenStore` at `0x1800b7c8b`

## string_xrefs

- `0x1800b7b9b`: `%s: Cannot open registry key "%s". RegOpenKeyExW error code: 0x%08x. Try loading the registry key...`
- `0x1800b7c44`: `%s: Cannot open registry key "%s". RegOpenKeyExW error code: 0x%08x.`
- `0x1800b7ca7`: `%s: CertOpenStore failed with error code: 0x%08x`
- `0x1800b7e2a`: `CertificateUtil::DoesExtensionWithValueExist`

## pseudocode

```c
__int64 __fastcall CertificateUtil::FindAllCertificatesByOidValue(
        int a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        unsigned int a5,
        struct _CERT_CONTEXT **a6,
        unsigned int *a7)
{
  __int64 LastError; // rsi
  void *v8; // r12
  const CERT_CONTEXT *pPrevCertContext; // rbp
  __int64 v10; // r14
  signed int v12; // edi
  const unsigned __int16 *v13; // rdx
  unsigned int v14; // eax
  unsigned int KeyW; // eax
  const unsigned __int16 *v16; // rdx
  HKEY v17; // rcx
  const unsigned __int16 *v18; // r8
  const unsigned __int16 *v19; // r9
  int KeyWinPE; // eax
  const wchar_t *p_hCertStore; // r9
  unsigned int v22; // eax
  const wchar_t *v23; // rax
  DWORD v24; // r9d
  __int64 v25; // rcx
  int v26; // ebp
  __int64 i; // r12
  __int64 v28; // rdx
  const char *v29; // rcx
  int DoesExtensionWithValueExist; // eax
  const wchar_t *v31; // r8
  signed int v32; // eax
  unsigned int v33; // eax
  unsigned int v34; // eax
  PHKEY phkResult; // [rsp+20h] [rbp-88h]
  unsigned int v37; // [rsp+30h] [rbp-78h]
  int v38; // [rsp+34h] [rbp-74h] BYREF
  int v39; // [rsp+38h] [rbp-70h]
  int v40; // [rsp+3Ch] [rbp-6Ch]
  PCCERT_CONTEXT pCertContext; // [rsp+40h] [rbp-68h]
  HCERTSTORE v42; // [rsp+48h] [rbp-60h]
  HKEY hKey[11]; // [rsp+50h] [rbp-58h] BYREF
  unsigned int v44; // [rsp+B0h] [rbp+8h]

  LODWORD(LastError) = 0;
  v8 = 0;
  v40 = 0;
  pPrevCertContext = 0;
  hKey[0] = 0;
  v10 = 0;
  v37 = 0;
  v44 = 0;
  v39 = 0;
  if ( !a2 )
  {
    v12 = -2147024809;
    Logger::TraceError(
      L"%s: \"%s\" should not be null.",
      L"CertificateUtil::FindAllCertificatesByOidValue",
      L"pcszOids");
    v13 = L"pcszOids";
LABEL_3:
    Logger::WriteNullOrEmptyParameterFailureEvent(L"CertificateUtil::FindAllCertificatesByOidValue", v13);
    goto LABEL_44;
  }
  if ( !a3 )
  {
    v12 = -2147024809;
    Logger::TraceError(
      L"%s: \"%s\" should not be null.",
      L"CertificateUtil::FindAllCertificatesByOidValue",
      L"pcszOidValues");
    v13 = L"pcszOidValues";
    goto LABEL_3;
  }
  if ( !a7 )
  {
    v12 = -2147024809;
    Logger::TraceError(
      L"%s: \"%s\" should not be null.",
      L"CertificateUtil::FindAllCertificatesByOidValue",
      L"pdwCount");
    v13 = L"pdwCount";
    goto LABEL_3;
  }
  v12 = 0;
  v37 = *a7;
  *a7 = 0;
  if ( a1 == 1 && (unsigned int)IsWinPEHost() )
  {
    Logger::TraceInformation(L"%s: System is WinPE.", L"CertificateUtil::FindAllCertificatesByOidValue");
    v14 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"TargetSoftware\\Microsoft\\SystemCertificates\\MY", 0, 0x20019u, hKey);
    LODWORD(LastError) = v14;
    if ( v14 )
    {
      Logger::TraceWarning(
        L"%s: Cannot open registry key \"%s\". RegOpenKeyExW error code: 0x%08x. Try loading the registry key...",
        L"CertificateUtil::FindAllCertificatesByOidValue",
        L"HKEY_LOCAL_MACHINE\\TargetSoftware\\Microsoft\\SystemCertificates\\MY",
        v14);
      KeyW = RegUnLoadKeyW(HKEY_LOCAL_MACHINE, L"TargetSoftware");
      if ( KeyW )
        Logger::TraceVerbose(
          L"%s: Always try unloading reg key \"%s\" first before loading it. RegUnLoadKeyW failed with error code: 0x%08x."
           " Failure ignored. Continue to load the key...",
          L"CertificateUtil::FindAllCertificatesByOidValue",
          L"HKEY_LOCAL_MACHINE\\TargetSoftware",
          KeyW);
      KeyWinPE = RegLoadKeyWinPE(v17, v16, v18, v19);
      v12 = KeyWinPE;
      if ( KeyWinPE < 0 )
      {
        Logger::TraceError(
          L"%s: %s failed with error code: 0x%08x.",
          L"CertificateUtil::FindAllCertificatesByOidValue",
          L"RegLoadKeyWinPE",
          (unsigned int)KeyWinPE);
        goto LABEL_15;
      }
      v40 = 1;
      v22 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"TargetSoftware\\Microsoft\\SystemCertificates\\MY", 0, 0x20019u, hKey);
      LODWORD(LastError) = v22;
      if ( v22 )
      {
        Logger::TraceError(
          L"%s: Cannot open registry key \"%s\". RegOpenKeyExW error code: 0x%08x.",
          L"CertificateUtil::FindAllCertificatesByOidValue",
          L"HKEY_LOCAL_MACHINE\\TargetSoftware\\Microsoft\\SystemCertificates\\MY",
          v22);
        goto LABEL_15;
      }
    }
    v23 = (const wchar_t *)hKey[0];
    v24 = 0x8000;
    v25 = 4;
  }
  else
  {
    v25 = 10;
    v23 = L"My";
    v24 = a1 != 0 ? 163840 : 98304;
  }
  v42 = CertOpenStore((LPCSTR)v25, 0, 0, v24, v23);
  v8 = v42;
  if ( v42 )
  {
LABEL_23:
    while ( 1 )
    {
      pCertContext = CertFindCertificateInStore(v8, 0x10001u, 0, 0, 0, pPrevCertContext);
      pPrevCertContext = pCertContext;
      if ( !pCertContext )
        break;
      ++v39;
      v26 = 1;
      v38 = 1;
      for ( i = 0; ; i = (unsigned int)(i + 1) )
      {
        if ( !v26 )
        {
          pPrevCertContext = pCertContext;
          v8 = v42;
          goto LABEL_23;
        }
        if ( (unsigned int)i >= a5 )
          break;
        Logger::TraceVerbose(
          L"%s: Will try to find the OID: '%hs' and value: '%.*s'",
          L"CertificateUtil::FindAllCertificatesByOidValue",
          *(_QWORD *)(a2 + 8 * i),
          1024,
          *(_QWORD *)(a3 + 8 * i));
        v28 = *(_QWORD *)(a3 + 8 * i);
        v29 = *(const char **)(a2 + 8 * i);
        if ( v28 )
        {
          pPrevCertContext = pCertContext;
          DoesExtensionWithValueExist = CertificateUtil::DoesExtensionWithValueExist(
                                          v29,
                                          v28,
                                          *(unsigned int *)(a4 + 4 * i),
                                          pCertContext,
                                          &v38);
          v12 = DoesExtensionWithValueExist;
          if ( DoesExtensionWithValueExist < 0 )
          {
            Logger::TraceError(
              L"%s: %s failed with error code: 0x%08x.",
              L"CertificateUtil::FindAllCertificatesByOidValue",
              L"CertificateUtil::DoesExtensionWithValueExist",
              (unsigned int)DoesExtensionWithValueExist);
            v8 = v42;
            goto LABEL_44;
          }
          v26 = v38;
        }
        else
        {
          if ( CertificateUtil::FindExtensionByOid(v29, pCertContext) )
            v26 = 0;
          v38 = v26;
        }
        v31 = L"TRUE";
        if ( !v26 )
          v31 = (const wchar_t *)L"FALSE";
        Logger::TraceVerbose(L"%s: Cert matching: %s", L"CertificateUtil::FindAllCertificatesByOidValue", v31);
      }
      ++v44;
      pPrevCertContext = pCertContext;
      v8 = v42;
      if ( v37 > (unsigned int)v10 && a6 )
      {
        a6[v10] = (struct _CERT_CONTEXT *)CertDuplicateCertificateContext(pCertContext);
        v10 = (unsigned int)(v10 + 1);
      }
    }
    if ( v37 >= v44 && a6 )
    {
      *a7 = v10;
    }
    else
    {
      *a7 = v44;
      LODWORD(LastError) = 122;
    }
  }
  else
  {
    LastError = GetLastError();
    Logger::TraceError(
      L"%s: CertOpenStore failed with error code: 0x%08x",
      L"CertificateUtil::FindAllCertificatesByOidValue",
      LastError);
  }
LABEL_44:
  if ( a1 )
  {
    if ( a1 != 1 )
    {
      p_hCertStore = L"Unknown";
      goto LABEL_48;
    }
LABEL_15:
    p_hCertStore = L"LocalMachine";
    goto LABEL_48;
  }
  p_hCertStore = (const wchar_t *)&stru_1800D9558.hCertStore;
LABEL_48:
  LODWORD(phkResult) = v39;
  Logger::TraceVerbose(
    L"%s: %u total %s certificate(s) found. %u certificate(s) checked.",
    L"CertificateUtil::FindAllCertificatesByOidValue",
    v44,
    p_hCertStore,
    phkResult);
  if ( (_DWORD)LastError )
  {
    if ( (int)LastError > 0 )
      v12 = (unsigned __int16)LastError | 0x80070000;
    else
      v12 = LastError;
  }
  if ( pPrevCertContext )
    CertFreeCertificateContext(pPrevCertContext);
  if ( v12 < 0 )
  {
    if ( v37 < (unsigned int)v10 )
      LODWORD(v10) = v37;
    CertificateUtil::FreeCertificates((const struct _CERT_CONTEXT **const)a6, v10);
  }
  if ( v8 && !CertCloseStore(v8, 0) )
  {
    v32 = GetLastError();
    if ( v32 > 0 )
      v32 = (unsigned __int16)v32 | 0x80070000;
    Logger::TraceWarning(
      L"%s: CertCloseStore failed with error code: 0x%08x",
      L"CertificateUtil::FindAllCertificatesByOidValue",
      (unsigned int)v32);
  }
  if ( hKey[0] )
  {
    v33 = RegCloseKey(hKey[0]);
    if ( v33 )
      Logger::TraceWarning(
        L"%s: Cannot close reg key %s. RegCloseKey failed with error code: 0x%08x.",
        L"CertificateUtil::FindAllCertificatesByOidValue",
        L"HKEY_LOCAL_MACHINE\\TargetSoftware\\Microsoft\\SystemCertificates\\MY",
        v33);
  }
  if ( v40 )
  {
    v34 = RegUnLoadKeyW(HKEY_LOCAL_MACHINE, L"TargetSoftware");
    if ( v34 )
      Logger::TraceWarning(
        L"%s: Cannot unload reg key %s. RegUnLoadKeyW failed with error code: 0x%08x.",
        L"CertificateUtil::FindAllCertificatesByOidValue",
        L"HKEY_LOCAL_MACHINE\\TargetSoftware",
        v34);
    else
      Logger::TraceVerbose(
        L"%s: reg key \"%s\" unloaded.",
        L"CertificateUtil::FindAllCertificatesByOidValue",
        L"HKEY_LOCAL_MACHINE\\TargetSoftware");
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1800b7a50  mov     r11, rsp
0x1800b7a53  mov     [r11+20h], r9
0x1800b7a57  mov     [r11+18h], r8
0x1800b7a5b  mov     [r11+10h], rdx
0x1800b7a5f  push    rbx
0x1800b7a60  push    rbp
0x1800b7a61  push    rsi
0x1800b7a62  push    rdi
0x1800b7a63  push    r12
0x1800b7a65  push    r13
0x1800b7a67  push    r14
0x1800b7a69  push    r15
0x1800b7a6b  sub     rsp, 68h
0x1800b7a6f  xor     esi, esi
0x1800b7a71  lea     rbx, aCertificateuti; "CertificateUtil::FindAllCertificatesByO"...
0x1800b7a78  xor     r12d, r12d
0x1800b7a7b  mov     [rsp+0A8h+var_6C], esi
0x1800b7a7f  xor     ebp, ebp
0x1800b7a81  mov     [r11-58h], rsi
0x1800b7a85  xor     r14d, r14d
0x1800b7a88  mov     [rsp+0A8h+var_78], esi
0x1800b7a8c  mov     [rsp+0A8h+arg_0], esi
0x1800b7a93  mov     rax, r8
0x1800b7a96  mov     [rsp+0A8h+var_70], esi
0x1800b7a9a  mov     r13d, ecx
0x1800b7a9d  test    rdx, rdx
0x1800b7aa0  jnz     short loc_1800B7AD1
0x1800b7aa2  lea     r8, aPcszoids; "pcszOids"
0x1800b7aa9  mov     rdx, rbx
0x1800b7aac  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x1800b7ab3  mov     edi, 80070057h
0x1800b7ab8  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800b7abd  lea     rdx, aPcszoids; "pcszOids"
0x1800b7ac4  mov     rcx, rbx; unsigned __int16 *
0x1800b7ac7  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x1800b7acc  jmp     loc_1800B7E6C
0x1800b7ad1  test    rax, rax
0x1800b7ad4  jnz     short loc_1800B7AFA
0x1800b7ad6  lea     r8, aPcszoidvalues; "pcszOidValues"
0x1800b7add  mov     rdx, rbx
0x1800b7ae0  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x1800b7ae7  mov     edi, 80070057h
0x1800b7aec  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800b7af1  lea     rdx, aPcszoidvalues; "pcszOidValues"
0x1800b7af8  jmp     short loc_1800B7AC4
0x1800b7afa  mov     r15, [rsp+0A8h+arg_30]
0x1800b7b02  test    r15, r15
0x1800b7b05  jnz     short loc_1800B7B2B
0x1800b7b07  lea     r8, aPdwcount; "pdwCount"
0x1800b7b0e  mov     rdx, rbx
0x1800b7b11  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x1800b7b18  mov     edi, 80070057h
0x1800b7b1d  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800b7b22  lea     rdx, aPdwcount; "pdwCount"
0x1800b7b29  jmp     short loc_1800B7AC4
0x1800b7b2b  mov     eax, [r15]
0x1800b7b2e  xor     edi, edi
0x1800b7b30  mov     [rsp+0A8h+var_78], eax
0x1800b7b34  mov     [r15], esi
0x1800b7b37  cmp     r13d, 1
0x1800b7b3b  jnz     loc_1800B7C5F
0x1800b7b41  call    ?IsWinPEHost@@YAHXZ; IsWinPEHost(void)
0x1800b7b46  test    eax, eax
0x1800b7b48  jz      loc_1800B7C5F
0x1800b7b4e  mov     rdx, rbx
0x1800b7b51  lea     rcx, aSSystemIsWinpe; "%s: System is WinPE."
0x1800b7b58  call    ?TraceInformation@Logger@@SAJPEBGZZ; Logger::TraceInformation(ushort const *,...)
0x1800b7b5d  lea     rax, [rsp+0A8h+hKey]
0x1800b7b62  mov     r9d, 20019h; samDesired
0x1800b7b68  xor     r8d, r8d; ulOptions
0x1800b7b6b  mov     [rsp+0A8h+phkResult], rax; phkResult
0x1800b7b70  lea     rdx, aTargetsoftware; "TargetSoftware\\Microsoft\\SystemCertif"...
0x1800b7b77  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800b7b7e  call    cs:__imp_RegOpenKeyExW
0x1800b7b84  mov     esi, eax
0x1800b7b86  test    eax, eax
0x1800b7b88  jz      loc_1800B7C4D
0x1800b7b8e  mov     r9d, eax
0x1800b7b91  lea     r8, aHkeyLocalMachi; "HKEY_LOCAL_MACHINE\\TargetSoftware\\Mic"...
0x1800b7b98  mov     rdx, rbx
0x1800b7b9b  lea     rcx, aSCannotOpenReg; "%s: Cannot open registry key \"%s\". Re"...
0x1800b7ba2  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x1800b7ba7  lea     rdx, aTargetsoftware_0; "TargetSoftware"
0x1800b7bae  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800b7bb5  call    cs:__imp_RegUnLoadKeyW
0x1800b7bbb  test    eax, eax
0x1800b7bbd  jz      short loc_1800B7BD8
0x1800b7bbf  mov     r9d, eax
0x1800b7bc2  lea     r8, aHkeyLocalMachi_2; "HKEY_LOCAL_MACHINE\\TargetSoftware"
0x1800b7bc9  mov     rdx, rbx
0x1800b7bcc  lea     rcx, aSAlwaysTryUnlo; "%s: Always try unloading reg key \"%s\""...
0x1800b7bd3  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x1800b7bd8  call    ?RegLoadKeyWinPE@@YAJPEAUHKEY__@@PEBG11@Z; RegLoadKeyWinPE(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x1800b7bdd  mov     edi, eax
0x1800b7bdf  test    eax, eax
0x1800b7be1  jns     short loc_1800B7C08
0x1800b7be3  lea     r8, aRegloadkeywinp; "RegLoadKeyWinPE"
0x1800b7bea  lea     rcx, aSSFailedWithEr_0; "%s: %s failed with error code: 0x%08x."
0x1800b7bf1  mov     rdx, rbx
0x1800b7bf4  mov     r9d, eax
0x1800b7bf7  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800b7bfc  lea     r9, aLocalmachine; "LocalMachine"
0x1800b7c03  jmp     loc_1800B7E8B
0x1800b7c08  lea     rax, [rsp+0A8h+hKey]
0x1800b7c0d  mov     [rsp+0A8h+var_6C], 1
0x1800b7c15  mov     r9d, 20019h; samDesired
0x1800b7c1b  mov     [rsp+0A8h+phkResult], rax; phkResult
0x1800b7c20  xor     r8d, r8d; ulOptions
0x1800b7c23  lea     rdx, aTargetsoftware; "TargetSoftware\\Microsoft\\SystemCertif"...
0x1800b7c2a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800b7c31  call    cs:__imp_RegOpenKeyExW
0x1800b7c37  mov     esi, eax
0x1800b7c39  test    eax, eax
0x1800b7c3b  jz      short loc_1800B7C4D
0x1800b7c3d  lea     r8, aHkeyLocalMachi; "HKEY_LOCAL_MACHINE\\TargetSoftware\\Mic"...
0x1800b7c44  lea     rcx, aSCannotOpenReg_0; "%s: Cannot open registry key \"%s\". Re"...
0x1800b7c4b  jmp     short loc_1800B7BF1
0x1800b7c4d  mov     rax, [rsp+0A8h+hKey]
0x1800b7c52  mov     r9d, 8000h
0x1800b7c58  mov     ecx, 4
0x1800b7c5d  jmp     short loc_1800B7C81
0x1800b7c5f  mov     eax, r13d
0x1800b7c62  mov     ecx, 0Ah; lpszStoreProvider
0x1800b7c67  neg     eax
0x1800b7c69  lea     rax, aMy; "My"
0x1800b7c70  sbb     r9d, r9d
0x1800b7c73  and     r9d, 10000h
0x1800b7c7a  add     r9d, 18000h; dwFlags
0x1800b7c81  xor     r8d, r8d; hCryptProv
0x1800b7c84  mov     [rsp+0A8h+phkResult], rax; pvPara
0x1800b7c89  xor     edx, edx; dwEncodingType
0x1800b7c8b  call    cs:__imp_CertOpenStore
0x1800b7c91  mov     [rsp+0A8h+var_60], rax
0x1800b7c96  mov     r12, rax
0x1800b7c99  test    rax, rax
0x1800b7c9c  jnz     short loc_1800B7CC7
0x1800b7c9e  call    cs:__imp_GetLastError
0x1800b7ca4  mov     rdx, rbx
0x1800b7ca7  lea     rcx, aSCertopenstore; "%s: CertOpenStore failed with error cod"...
0x1800b7cae  mov     r8d, eax
0x1800b7cb1  mov     esi, eax
0x1800b7cb3  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800b7cb8  jmp     loc_1800B7E6C
0x1800b7cbd  mov     rbp, [rsp+0A8h+pCertContext]
0x1800b7cc2  mov     r12, [rsp+0A8h+var_60]
0x1800b7cc7  mov     [rsp+0A8h+pPrevCertContext], rbp; pPrevCertContext
0x1800b7ccc  xor     r9d, r9d; dwFindType
0x1800b7ccf  xor     r8d, r8d; dwFindFlags
0x1800b7cd2  mov     [rsp+0A8h+phkResult], 0; pvFindPara
0x1800b7cdb  mov     edx, 10001h; dwCertEncodingType
0x1800b7ce0  mov     rcx, r12; hCertStore
0x1800b7ce3  call    cs:__imp_CertFindCertificateInStore
0x1800b7ce9  mov     [rsp+0A8h+pCertContext], rax
0x1800b7cee  mov     rbp, rax
0x1800b7cf1  test    rax, rax
0x1800b7cf4  jz      loc_1800B7E47
0x1800b7cfa  inc     [rsp+0A8h+var_70]
0x1800b7cfe  mov     ebp, 1
0x1800b7d03  mov     [rsp+0A8h+var_74], ebp
0x1800b7d07  xor     r12d, r12d
0x1800b7d0a  test    ebp, ebp
0x1800b7d0c  jz      short loc_1800B7CBD
0x1800b7d0e  cmp     r12d, [rsp+0A8h+arg_20]
0x1800b7d16  jnb     loc_1800B7DDF
0x1800b7d1c  mov     rax, [rsp+0A8h+arg_10]
0x1800b7d24  lea     rcx, aSWillTryToFind; "%s: Will try to find the OID: '%hs' and"...
0x1800b7d2b  mov     r8, [rsp+0A8h+arg_8]
0x1800b7d33  mov     r9d, 400h
0x1800b7d39  mov     rdx, rbx
0x1800b7d3c  mov     rax, [rax+r12*8]
0x1800b7d40  mov     r8, [r8+r12*8]
0x1800b7d44  mov     [rsp+0A8h+phkResult], rax
0x1800b7d49  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x1800b7d4e  mov     rax, [rsp+0A8h+arg_10]
0x1800b7d56  mov     rdx, [rax+r12*8]
0x1800b7d5a  mov     rax, [rsp+0A8h+arg_8]
0x1800b7d62  mov     rcx, [rax+r12*8]; char *
0x1800b7d66  test    rdx, rdx
0x1800b7d69  jz      short loc_1800B7D9E
0x1800b7d6b  mov     rbp, [rsp+0A8h+pCertContext]
0x1800b7d70  lea     rax, [rsp+0A8h+var_74]
0x1800b7d75  mov     [rsp+0A8h+phkResult], rax
0x1800b7d7a  mov     r9, rbp
0x1800b7d7d  mov     rax, [rsp+0A8h+arg_18]
0x1800b7d85  mov     r8d, [rax+r12*4]
0x1800b7d89  call    ?DoesExtensionWithValueExist@CertificateUtil@@SAJPEBDPEBGW4_CERT_OID_VALUE_TYPE@@PEBU_CERT_CONTEXT@@PEAH@Z; CertificateUtil::DoesExtensionWithValueExist(char const *,ushort const *,_CERT_OID_VALUE_TYPE,_CERT_CONTEXT const *,int *)
0x1800b7d8e  mov     edi, eax
0x1800b7d90  test    eax, eax
0x1800b7d92  js      loc_1800B7E27
0x1800b7d98  mov     ebp, [rsp+0A8h+var_74]
0x1800b7d9c  jmp     short loc_1800B7DB4
0x1800b7d9e  mov     rdx, [rsp+0A8h+pCertContext]; struct _CERT_CONTEXT *
0x1800b7da3  call    ?FindExtensionByOid@CertificateUtil@@SAPEAU_CERT_EXTENSION@@PEBDPEBU_CERT_CONTEXT@@@Z; CertificateUtil::FindExtensionByOid(char const *,_CERT_CONTEXT const *)
0x1800b7da8  xor     ecx, ecx
0x1800b7daa  test    rax, rax
0x1800b7dad  cmovnz  ebp, ecx
0x1800b7db0  mov     [rsp+0A8h+var_74], ebp
0x1800b7db4  lea     rax, aFalse_0; "FALSE"
0x1800b7dbb  test    ebp, ebp
0x1800b7dbd  lea     r8, aTrue_0; "TRUE"
0x1800b7dc4  mov     rdx, rbx
0x1800b7dc7  cmovz   r8, rax
0x1800b7dcb  lea     rcx, aSCertMatchingS; "%s: Cert matching: %s"
0x1800b7dd2  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x1800b7dd7  inc     r12d
0x1800b7dda  jmp     loc_1800B7D0A
0x1800b7ddf  inc     [rsp+0A8h+arg_0]
0x1800b7de6  mov     rbp, [rsp+0A8h+pCertContext]
0x1800b7deb  mov     r12, [rsp+0A8h+var_60]
0x1800b7df0  cmp     [rsp+0A8h+var_78], r14d
0x1800b7df5  jbe     loc_1800B7CC7
0x1800b7dfb  cmp     [rsp+0A8h+arg_28], 0
0x1800b7e04  jz      loc_1800B7CC7
0x1800b7e0a  mov     rcx, rbp; pCertContext
0x1800b7e0d  call    cs:__imp_CertDuplicateCertificateContext
0x1800b7e13  mov     rdx, [rsp+0A8h+arg_28]
0x1800b7e1b  mov     [rdx+r14*8], rax
0x1800b7e1f  inc     r14d
0x1800b7e22  jmp     loc_1800B7CC7
0x1800b7e27  mov     r9d, eax
0x1800b7e2a  lea     r8, aCertificateuti_6; "CertificateUtil::DoesExtensionWithValue"...
0x1800b7e31  mov     rdx, rbx
0x1800b7e34  lea     rcx, aSSFailedWithEr_0; "%s: %s failed with error code: 0x%08x."
0x1800b7e3b  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800b7e40  mov     r12, [rsp+0A8h+var_60]
0x1800b7e45  jmp     short loc_1800B7E6C
0x1800b7e47  mov     eax, [rsp+0A8h+arg_0]
0x1800b7e4e  cmp     [rsp+0A8h+var_78], eax
0x1800b7e52  jb      short loc_1800B7E64
0x1800b7e54  cmp     [rsp+0A8h+arg_28], 0
0x1800b7e5d  jz      short loc_1800B7E64
0x1800b7e5f  mov     [r15], r14d
0x1800b7e62  jmp     short loc_1800B7E6C
0x1800b7e64  mov     [r15], eax
0x1800b7e67  mov     esi, 7Ah ; 'z'
0x1800b7e6c  test    r13d, r13d
0x1800b7e6f  jz      short loc_1800B7E84
0x1800b7e71  cmp     r13d, 1
0x1800b7e75  jz      loc_1800B7BFC
0x1800b7e7b  lea     r9, aUnknown_0; "Unknown"
0x1800b7e82  jmp     short loc_1800B7E8B
0x1800b7e84  lea     r9, stru_1800D9558.hCertStore
0x1800b7e8b  mov     eax, [rsp+0A8h+var_70]
0x1800b7e8f  lea     rcx, aSUTotalSCertif; "%s: %u total %s certificate(s) found. %"...
0x1800b7e96  mov     r8d, [rsp+0A8h+arg_0]
0x1800b7e9e  mov     rdx, rbx
0x1800b7ea1  mov     dword ptr [rsp+0A8h+phkResult], eax
0x1800b7ea5  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x1800b7eaa  mov     r15d, 80070000h
0x1800b7eb0  test    esi, esi
0x1800b7eb2  jz      short loc_1800B7EC0
0x1800b7eb4  jg      short loc_1800B7EBA
0x1800b7eb6  mov     edi, esi
0x1800b7eb8  jmp     short loc_1800B7EC0
0x1800b7eba  movzx   edi, si
0x1800b7ebd  or      edi, r15d
0x1800b7ec0  test    rbp, rbp
0x1800b7ec3  jz      short loc_1800B7ECE
0x1800b7ec5  mov     rcx, rbp; pCertContext
0x1800b7ec8  call    cs:__imp_CertFreeCertificateContext
0x1800b7ece  test    edi, edi
0x1800b7ed0  jns     short loc_1800B7EED
0x1800b7ed2  cmp     [rsp+0A8h+var_78], r14d
0x1800b7ed7  mov     rcx, [rsp+0A8h+arg_28]; struct _CERT_CONTEXT **
0x1800b7edf  cmovb   r14d, [rsp+0A8h+var_78]
0x1800b7ee5  mov     edx, r14d; unsigned int
0x1800b7ee8  call    ?FreeCertificates@CertificateUtil@@SAXQEAPEBU_CERT_CONTEXT@@K@Z; CertificateUtil::FreeCertificates(_CERT_CONTEXT const * * const,ulong)
0x1800b7eed  test    r12, r12
0x1800b7ef0  jz      short loc_1800B7F23
0x1800b7ef2  xor     edx, edx; dwFlags
0x1800b7ef4  mov     rcx, r12; hCertStore
0x1800b7ef7  call    cs:__imp_CertCloseStore
0x1800b7efd  test    eax, eax
0x1800b7eff  jnz     short loc_1800B7F23
0x1800b7f01  call    cs:__imp_GetLastError
0x1800b7f07  test    eax, eax
0x1800b7f09  jle     short loc_1800B7F11
0x1800b7f0b  movzx   eax, ax
0x1800b7f0e  or      eax, r15d
0x1800b7f11  mov     r8d, eax
0x1800b7f14  lea     rcx, aSCertclosestor; "%s: CertCloseStore failed with error co"...
0x1800b7f1b  mov     rdx, rbx
0x1800b7f1e  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x1800b7f23  mov     rcx, [rsp+0A8h+hKey]; hKey
0x1800b7f28  test    rcx, rcx
0x1800b7f2b  jz      short loc_1800B7F50
0x1800b7f2d  call    cs:__imp_RegCloseKey
0x1800b7f33  test    eax, eax
0x1800b7f35  jz      short loc_1800B7F50
0x1800b7f37  mov     r9d, eax
0x1800b7f3a  lea     r8, aHkeyLocalMachi; "HKEY_LOCAL_MACHINE\\TargetSoftware\\Mic"...
0x1800b7f41  mov     rdx, rbx
0x1800b7f44  lea     rcx, aSCannotCloseRe; "%s: Cannot close reg key %s. RegCloseKe"...
0x1800b7f4b  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x1800b7f50  cmp     [rsp+0A8h+var_6C], 0
0x1800b7f55  jz      short loc_1800B7F96
0x1800b7f57  lea     rdx, aTargetsoftware_0; "TargetSoftware"
0x1800b7f5e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800b7f65  call    cs:__imp_RegUnLoadKeyW
0x1800b7f6b  lea     r8, aHkeyLocalMachi_2; "HKEY_LOCAL_MACHINE\\TargetSoftware"
  ... truncated ...
```
