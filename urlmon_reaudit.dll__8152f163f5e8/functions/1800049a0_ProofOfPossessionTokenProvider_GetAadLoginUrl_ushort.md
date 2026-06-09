# ProofOfPossessionTokenProvider::GetAadLoginUrl(ushort * *)

- ea: `0x1800049a0`
- end: `0x18000509f`
- name: `?GetAadLoginUrl@ProofOfPossessionTokenProvider@@YAJPEAPEAG@Z`
- size: `1791`
- prototype: `__int64 __fastcall(ProofOfPossessionTokenProvider *__hidden this, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180003190`
- `0x180004384`

## callees

- `0x1800049a0`
- `0x1800050a8`
- `0x18000521c`
- `0x180078a5c`
- `0x18008180c`
- `0x1800a11c0`
- `0x1801272d4`
- `0x1801285fe`
- `0x180128660`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004b26`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004c0b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004d31`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004b26`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004c0b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004d31`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180004ac9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180004bab`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180004cc7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180004ac9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180004bab`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180004cc7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180004b00`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180004be5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180004d02`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180004b00`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180004be5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180004d02`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180004a49`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180004a49`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180004a87`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180004b6e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180004c84`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180004a87`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180004b6e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180004c84`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004b3a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004c1f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004d45`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004d6b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004d7f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004e21`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004e39`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004b3a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004c1f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004d45`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004d6b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004d7f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004e21`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004e39`

## string_xrefs

- `0x180004aee`: `LoginUri`
- `0x180004cf0`: `LoginUri`
- `0x180004fc4`: `LoginUri`
- `0x180004bd3`: `EnterpriseAuthorityUri`
- `0x180005011`: `EnterpriseAuthorityUri`
- `0x180004eeb`: `onecoreuap\inetcore\lib\proofofpossessiontokenprovider\proofofpossessiontokenprovider.cxx`

## pseudocode

```c
__int64 __fastcall ProofOfPossessionTokenProvider::GetAadLoginUrl(
        ProofOfPossessionTokenProvider *this,
        unsigned __int16 **a2)
{
  HKEY v2; // rbx
  HKEY v3; // r14
  unsigned __int16 *v4; // r15
  int PersistedRegistryLocationW; // eax
  int v6; // edi
  signed int v7; // ebx
  bool v8; // sf
  bool v9; // sf
  BYTE *v10; // rax
  HKEY v11; // rsi
  BYTE *v12; // rbx
  LSTATUS v13; // eax
  unsigned int v14; // edi
  LSTATUS Value; // eax
  BYTE *v16; // rax
  unsigned __int16 *v17; // rsi
  BYTE *v18; // rbx
  LSTATUS v19; // eax
  LSTATUS v20; // eax
  unsigned __int64 *v21; // rax
  int v22; // r12d
  unsigned __int64 *v23; // rdi
  BYTE *v24; // rbx
  BYTE *v25; // r13
  BYTE *v26; // rsi
  LSTATUS v27; // eax
  rsize_t v28; // r13
  unsigned __int64 v30; // rcx
  char *v31; // rdx
  unsigned __int64 v32; // rcx
  BYTE *v33; // rdx
  unsigned __int64 v34; // rcx
  unsigned __int16 *v35; // rdx
  int MergedAadLoginUrl; // eax
  unsigned int TokenProviderLoginUrls; // eax
  unsigned int v38; // eax
  DWORD cbData[2]; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  HKEY phkResult; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 *v42; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 *v43; // [rsp+50h] [rbp-B0h] BYREF
  SIZE_T cb; // [rsp+58h] [rbp-A8h]
  unsigned __int64 v45; // [rsp+60h] [rbp-A0h]
  WCHAR SubKey[264]; // [rsp+70h] [rbp-90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2D8h] [rbp+1D8h]

  v45 = (unsigned __int64)this;
  if ( !this )
    return (unsigned int)-2147024809;
  hKey = 0;
  v2 = 0;
  cb = 0;
  *(_QWORD *)cbData = 0;
  v3 = 0;
  phkResult = 0;
  v4 = 0;
  v42 = 0;
  v43 = 0;
  if ( (unsigned int)IsInternetExplorerApp() )
  {
    TokenProviderLoginUrls = GetTokenProviderLoginUrls(
                               HKEY_LOCAL_MACHINE,
                               L"Software\\Microsoft\\IdentityStore\\LoadParameters\\{B16898C6-A148-4967-9171-64D755DA8520}",
                               L"LoginUri",
                               (unsigned __int16 **)&hKey,
                               (unsigned __int64 *)cbData);
    v14 = TokenProviderLoginUrls;
    if ( (int)(TokenProviderLoginUrls + 0x80000000) < 0 || TokenProviderLoginUrls == -2147024894 )
    {
      v38 = GetTokenProviderLoginUrls(
              HKEY_LOCAL_MACHINE,
              L"Software\\Microsoft\\IdentityStore\\LoadParameters\\{B16898C6-A148-4967-9171-64D755DA8520}",
              L"EnterpriseAuthorityUri",
              &v43,
              (unsigned __int64 *)&v42);
      v3 = hKey;
      v14 = v38;
      v21 = *(unsigned __int64 **)cbData;
      v4 = v43;
      v2 = (HKEY)v42;
    }
    else
    {
      v3 = hKey;
      v21 = *(unsigned __int64 **)cbData;
    }
    goto LABEL_29;
  }
  memset_0(SubKey, 0, 0x208u);
  PersistedRegistryLocationW = GetPersistedRegistryLocationW(
                                 L"IDStoreLoadParametersAad",
                                 L"Software\\Microsoft\\IdentityStore\\LoadParameters\\{B16898C6-A148-4967-9171-64D755DA8520}",
                                 SubKey,
                                 520);
  v6 = (unsigned __int16)PersistedRegistryLocationW;
  v7 = PersistedRegistryLocationW;
  v8 = PersistedRegistryLocationW < 0;
  if ( PersistedRegistryLocationW > 0 )
    v8 = 1;
  if ( v8 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  v9 = v7 < 0;
  if ( v7 > 0 )
  {
    v7 = v6 | 0x80070000;
    v9 = 1;
  }
  if ( !v9 )
  {
    cbData[0] = 4168;
    v10 = (BYTE *)CoTaskMemAlloc(0x104Cu);
    v11 = (HKEY)v10;
    if ( !v10 )
    {
      v22 = -2147024882;
LABEL_46:
      if ( v4 )
        CoTaskMemFree(v4);
      if ( v3 )
        CoTaskMemFree(v3);
      return (unsigned int)v22;
    }
    v12 = v10;
    hKey = 0;
    v13 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x101u, &hKey);
    v14 = v13;
    if ( v13 )
    {
      if ( v13 > 0 )
        v14 = (unsigned __int16)v13 | 0x80070000;
    }
    else
    {
      Value = RegQueryValueExW(hKey, L"LoginUri", 0, 0, v12, cbData);
      v14 = Value;
      if ( Value )
      {
        if ( Value > 0 )
          v14 = (unsigned __int16)Value | 0x80070000;
      }
      else
      {
        v30 = (unsigned __int64)cbData[0] >> 1;
        *((_WORD *)v11 + v30) = 0;
        v31 = (char *)v11 + 2 * v30 + 2;
        *(_WORD *)v31 = 0;
        while ( v31 >= (char *)v11 && !*(_WORD *)v31 )
          v31 -= 2;
        v12 = 0;
        v3 = v11;
        v14 = 0;
        cb = 2 * ((v31 - (char *)v11) >> 1) + 6;
      }
      RegCloseKey(hKey);
    }
    if ( v12 )
      CoTaskMemFree(v12);
    if ( (int)(v14 + 0x80000000) < 0 || v14 == -2147024894 )
    {
      cbData[0] = 4168;
      v16 = (BYTE *)CoTaskMemAlloc(0x104Cu);
      v17 = (unsigned __int16 *)v16;
      if ( v16 )
      {
        v18 = v16;
        hKey = 0;
        v19 = RegOpenKeyExW(
                HKEY_LOCAL_MACHINE,
                L"Software\\Microsoft\\IdentityStore\\LoadParameters\\{B16898C6-A148-4967-9171-64D755DA8520}",
                0,
                0x101u,
                &hKey);
        v14 = v19;
        if ( v19 )
        {
          if ( v19 > 0 )
            v14 = (unsigned __int16)v19 | 0x80070000;
        }
        else
        {
          v20 = RegQueryValueExW(hKey, L"EnterpriseAuthorityUri", 0, 0, v18, cbData);
          v14 = v20;
          if ( v20 )
          {
            if ( v20 > 0 )
              v14 = (unsigned __int16)v20 | 0x80070000;
          }
          else
          {
            v34 = (unsigned __int64)cbData[0] >> 1;
            v17[v34] = 0;
            v35 = &v17[v34 + 1];
            *v35 = 0;
            while ( v35 >= v17 && !*v35 )
              --v35;
            v18 = 0;
            v4 = v17;
            v14 = 0;
            phkResult = (HKEY)(2 * (v35 - v17) + 6);
          }
          RegCloseKey(hKey);
        }
        if ( v18 )
          CoTaskMemFree(v18);
      }
      else
      {
        v14 = -2147024882;
      }
    }
    v2 = phkResult;
    v21 = (unsigned __int64 *)cb;
LABEL_29:
    v22 = 0;
    if ( v14 != -2147024894 )
      v22 = v14;
    if ( v22 < 0 )
      goto LABEL_46;
    *(_QWORD *)cbData = 0;
    v23 = 0;
    hKey = 0;
    v42 = 0;
    if ( v3 )
    {
      if ( v4 )
      {
        MergedAadLoginUrl = ProofOfPossessionTokenProvider::GetMergedAadLoginUrl(
                              (ProofOfPossessionTokenProvider *)v3,
                              (SIZE_T)v21,
                              v4,
                              (rsize_t)v2,
                              (unsigned __int64)cbData,
                              &v42,
                              *(unsigned __int64 **)cbData);
        v23 = *(unsigned __int64 **)cbData;
        v22 = MergedAadLoginUrl;
        if ( MergedAadLoginUrl < 0 )
        {
LABEL_60:
          if ( v23 )
            CoTaskMemFree(v23);
          goto LABEL_46;
        }
        hKey = (HKEY)v42;
      }
      else
      {
        v23 = (unsigned __int64 *)v3;
        hKey = (HKEY)v21;
        v3 = 0;
      }
    }
    else if ( v4 )
    {
      v23 = (unsigned __int64 *)v4;
      v4 = 0;
      Auto<unsigned short *,CoTaskMemAllocFunctor<unsigned short *>>::Clear(cbData);
      hKey = v2;
    }
    v43 = 0;
    v24 = 0;
    cbData[0] = 4168;
    v25 = (BYTE *)CoTaskMemAlloc(0x104Cu);
    if ( v25 )
    {
      phkResult = 0;
      v26 = v25;
      v22 = RegOpenKeyExW(
              HKEY_CURRENT_USER,
              L"Software\\Microsoft\\Windows\\CurrentVersion\\AAD\\Package",
              0,
              0x101u,
              &phkResult);
      if ( v22 )
      {
        if ( v22 > 0 )
          v22 = (unsigned __int16)v22 | 0x80070000;
        v28 = 0;
      }
      else
      {
        v27 = RegQueryValueExW(phkResult, L"LoginUri", 0, 0, v25, cbData);
        v22 = v27;
        if ( v27 )
        {
          if ( v27 > 0 )
            v22 = (unsigned __int16)v27 | 0x80070000;
          v28 = 0;
        }
        else
        {
          v32 = (unsigned __int64)cbData[0] >> 1;
          *(_WORD *)&v25[2 * v32] = 0;
          v33 = &v25[2 * v32 + 2];
          *(_WORD *)v33 = 0;
          while ( v33 >= v25 && !*(_WORD *)v33 )
            v33 -= 2;
          v24 = v25;
          v26 = 0;
          v22 = 0;
          v28 = 2 * ((v33 - v25) >> 1) + 6;
        }
        RegCloseKey(phkResult);
      }
      if ( v26 )
        CoTaskMemFree(v26);
    }
    else
    {
      v22 = -2147024882;
      v28 = 0;
    }
    if ( !v23 && !v24 )
      goto LABEL_46;
    v22 = ProofOfPossessionTokenProvider::GetMergedAadLoginUrl(
            (ProofOfPossessionTokenProvider *)v23,
            (SIZE_T)hKey,
            v24,
            v28,
            v45,
            &v43,
            *(unsigned __int64 **)cbData);
    if ( v24 )
      CoTaskMemFree(v24);
    goto LABEL_60;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x18A,
    (unsigned int)"onecoreuap\\inetcore\\lib\\proofofpossessiontokenprovider\\proofofpossessiontokenprovider.cxx",
    (const char *)(unsigned int)v7,
    0);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800049a0  push    rbp
0x1800049a2  push    rbx
0x1800049a3  push    rsi
0x1800049a4  push    rdi
0x1800049a5  push    r12
0x1800049a7  push    r13
0x1800049a9  push    r14
0x1800049ab  push    r15
0x1800049ad  lea     rbp, [rsp-198h]
0x1800049b5  sub     rsp, 298h
0x1800049bc  mov     rax, cs:__security_cookie
0x1800049c3  xor     rax, rsp
0x1800049c6  mov     [rbp+1D0h+var_50], rax
0x1800049cd  xor     r13d, r13d
0x1800049d0  mov     [rsp+2D0h+var_270], rcx
0x1800049d5  test    rcx, rcx
0x1800049d8  jz      loc_180004E4A
0x1800049de  mov     edx, r13d
0x1800049e1  mov     [rsp+2D0h+hKey], r13
0x1800049e6  mov     ebx, r13d
0x1800049e9  mov     [rsp+2D0h+cb], rdx
0x1800049ee  mov     qword ptr [rsp+2D0h+cbData], rdx
0x1800049f3  mov     r14d, r13d
0x1800049f6  mov     [rsp+2D0h+var_290], rbx
0x1800049fb  mov     r15d, r13d
0x1800049fe  mov     [rsp+2D0h+var_288], rbx
0x180004a03  mov     [rsp+2D0h+var_280], r13
0x180004a08  call    ?IsInternetExplorerApp@@YAHXZ; IsInternetExplorerApp(void)
0x180004a0d  mov     esi, 80070000h
0x180004a12  test    eax, eax
0x180004a14  jnz     loc_180004FAB
0x180004a1a  mov     ebx, 208h
0x180004a1f  lea     rcx, [rsp+2D0h+SubKey]; void *
0x180004a24  mov     r8d, ebx; Size
0x180004a27  xor     edx, edx; Val
0x180004a29  call    memset_0
0x180004a2e  mov     r9d, ebx
0x180004a31  mov     [rsp+2D0h+phkResult], r13; int
0x180004a36  lea     r8, [rsp+2D0h+SubKey]
0x180004a3b  lea     rdx, aSoftwareMicros_72; "Software\\Microsoft\\IdentityStore\\Loa"...
0x180004a42  lea     rcx, aIdstoreloadpar; "IDStoreLoadParametersAad"
0x180004a49  call    cs:__imp_GetPersistedRegistryLocationW
0x180004a50  nop     dword ptr [rax+rax+00h]
0x180004a55  movzx   edi, ax
0x180004a58  mov     ebx, eax
0x180004a5a  test    eax, eax
0x180004a5c  jle     short loc_180004A64
0x180004a5e  mov     eax, edi
0x180004a60  or      eax, esi
0x180004a62  test    eax, eax
0x180004a64  js      loc_18000503F
0x180004a6a  test    ebx, ebx
0x180004a6c  jle     short loc_180004A74
0x180004a6e  mov     ebx, edi
0x180004a70  or      ebx, esi
0x180004a72  test    ebx, ebx
0x180004a74  js      loc_180004EE4
0x180004a7a  mov     ecx, 104Ch; cb
0x180004a7f  mov     [rsp+2D0h+cbData], 1048h
0x180004a87  call    cs:__imp_CoTaskMemAlloc
0x180004a8e  nop     dword ptr [rax+rax+00h]
0x180004a93  mov     rsi, rax
0x180004a96  test    rax, rax
0x180004a99  jz      loc_180005094
0x180004a9f  mov     rbx, rax
0x180004aa2  mov     [rsp+2D0h+hKey], r13
0x180004aa7  lea     rax, [rsp+2D0h+hKey]
0x180004aac  mov     r12, 0FFFFFFFF80000002h
0x180004ab3  mov     rcx, r12; hKey
0x180004ab6  mov     [rsp+2D0h+phkResult], rax; phkResult
0x180004abb  mov     r9d, 101h; samDesired
0x180004ac1  lea     rdx, [rsp+2D0h+SubKey]; lpSubKey
0x180004ac6  xor     r8d, r8d; ulOptions
0x180004ac9  call    cs:__imp_RegOpenKeyExW
0x180004ad0  nop     dword ptr [rax+rax+00h]
0x180004ad5  mov     edi, eax
0x180004ad7  test    eax, eax
0x180004ad9  jnz     loc_180004DB2
0x180004adf  mov     rcx, [rsp+2D0h+hKey]; hKey
0x180004ae4  lea     rax, [rsp+2D0h+cbData]
0x180004ae9  mov     [rsp+2D0h+lpcbData], rax; lpcbData
0x180004aee  lea     rdx, aLoginuri; "LoginUri"
0x180004af5  xor     r9d, r9d; lpType
0x180004af8  mov     [rsp+2D0h+phkResult], rbx; lpData
0x180004afd  xor     r8d, r8d; lpReserved
0x180004b00  call    cs:__imp_RegQueryValueExW
0x180004b07  nop     dword ptr [rax+rax+00h]
0x180004b0c  mov     edi, eax
0x180004b0e  test    eax, eax
0x180004b10  jz      loc_180004E55
0x180004b16  jle     short loc_180004B21
0x180004b18  movzx   edi, ax
0x180004b1b  or      edi, 80070000h
0x180004b21  mov     rcx, [rsp+2D0h+hKey]; hKey
0x180004b26  call    cs:__imp_RegCloseKey
0x180004b2d  nop     dword ptr [rax+rax+00h]
0x180004b32  test    rbx, rbx
0x180004b35  jz      short loc_180004B46
0x180004b37  mov     rcx, rbx; pv
0x180004b3a  call    cs:__imp_CoTaskMemFree
0x180004b41  nop     dword ptr [rax+rax+00h]
0x180004b46  mov     edx, 80000000h
0x180004b4b  mov     r13d, 80070002h
0x180004b51  lea     eax, [rdi+rdx]
0x180004b54  test    edx, eax
0x180004b56  jnz     short loc_180004B61
0x180004b58  cmp     edi, r13d
0x180004b5b  jnz     loc_180004C2B
0x180004b61  mov     ecx, 104Ch; cb
0x180004b66  mov     [rsp+2D0h+cbData], 1048h
0x180004b6e  call    cs:__imp_CoTaskMemAlloc
0x180004b75  nop     dword ptr [rax+rax+00h]
0x180004b7a  mov     rsi, rax
0x180004b7d  test    rax, rax
0x180004b80  jz      loc_180005049
0x180004b86  mov     rbx, rax
0x180004b89  mov     [rsp+2D0h+hKey], r15
0x180004b8e  lea     rax, [rsp+2D0h+hKey]
0x180004b93  mov     r9d, 101h; samDesired
0x180004b99  xor     r8d, r8d; ulOptions
0x180004b9c  mov     [rsp+2D0h+phkResult], rax; phkResult
0x180004ba1  lea     rdx, aSoftwareMicros_72; "Software\\Microsoft\\IdentityStore\\Loa"...
0x180004ba8  mov     rcx, r12; hKey
0x180004bab  call    cs:__imp_RegOpenKeyExW
0x180004bb2  nop     dword ptr [rax+rax+00h]
0x180004bb7  xor     r12d, r12d
0x180004bba  mov     edi, eax
0x180004bbc  test    eax, eax
0x180004bbe  jnz     loc_180004DDB
0x180004bc4  mov     rcx, [rsp+2D0h+hKey]; hKey
0x180004bc9  lea     rax, [rsp+2D0h+cbData]
0x180004bce  mov     [rsp+2D0h+lpcbData], rax; lpcbData
0x180004bd3  lea     rdx, aEnterpriseauth; "EnterpriseAuthorityUri"
0x180004bda  xor     r9d, r9d; lpType
0x180004bdd  mov     [rsp+2D0h+phkResult], rbx; lpData
0x180004be2  xor     r8d, r8d; lpReserved
0x180004be5  call    cs:__imp_RegQueryValueExW
0x180004bec  nop     dword ptr [rax+rax+00h]
0x180004bf1  mov     edi, eax
0x180004bf3  test    eax, eax
0x180004bf5  jz      loc_180004EBB
0x180004bfb  jle     short loc_180004C06
0x180004bfd  movzx   edi, ax
0x180004c00  or      edi, 80070000h
0x180004c06  mov     rcx, [rsp+2D0h+hKey]; hKey
0x180004c0b  call    cs:__imp_RegCloseKey
0x180004c12  nop     dword ptr [rax+rax+00h]
0x180004c17  test    rbx, rbx
0x180004c1a  jz      short loc_180004C2B
0x180004c1c  mov     rcx, rbx; pv
0x180004c1f  call    cs:__imp_CoTaskMemFree
0x180004c26  nop     dword ptr [rax+rax+00h]
0x180004c2b  mov     rbx, [rsp+2D0h+var_290]
0x180004c30  mov     rax, [rsp+2D0h+cb]
0x180004c35  xor     r12d, r12d
0x180004c38  cmp     edi, r13d
0x180004c3b  cmovnz  r12d, edi
0x180004c3f  xor     r13d, r13d
0x180004c42  test    r12d, r12d
0x180004c45  js      loc_180004D63
0x180004c4b  mov     qword ptr [rsp+2D0h+cbData], r13; unsigned __int64 *
0x180004c50  mov     edi, r13d
0x180004c53  mov     [rsp+2D0h+hKey], r13
0x180004c58  mov     [rsp+2D0h+var_288], r13
0x180004c5d  test    r14, r14
0x180004c60  jnz     loc_180005053
0x180004c66  test    r15, r15
0x180004c69  jnz     loc_18000506C
0x180004c6f  mov     ecx, 104Ch; cb
0x180004c74  mov     [rsp+2D0h+var_280], r13
0x180004c79  mov     rbx, r13
0x180004c7c  mov     [rsp+2D0h+cbData], 1048h; unsigned __int64 *
0x180004c84  call    cs:__imp_CoTaskMemAlloc
0x180004c8b  nop     dword ptr [rax+rax+00h]
0x180004c90  mov     r13, rax
0x180004c93  xor     eax, eax
0x180004c95  test    r13, r13
0x180004c98  jz      loc_180005086
0x180004c9e  mov     [rsp+2D0h+var_290], rax
0x180004ca3  lea     rdx, aSoftwareMicros_14; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180004caa  lea     rax, [rsp+2D0h+var_290]
0x180004caf  mov     r9d, 101h; samDesired
0x180004cb5  xor     r8d, r8d; ulOptions
0x180004cb8  mov     [rsp+2D0h+phkResult], rax; phkResult
0x180004cbd  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180004cc4  mov     rsi, r13
0x180004cc7  call    cs:__imp_RegOpenKeyExW
0x180004cce  nop     dword ptr [rax+rax+00h]
0x180004cd3  mov     r12d, eax
0x180004cd6  xor     eax, eax
0x180004cd8  test    r12d, r12d
0x180004cdb  jnz     loc_180004DC6
0x180004ce1  mov     rcx, [rsp+2D0h+var_290]; hKey
0x180004ce6  lea     rax, [rsp+2D0h+cbData]
0x180004ceb  mov     [rsp+2D0h+lpcbData], rax; lpcbData
0x180004cf0  lea     rdx, aLoginuri; "LoginUri"
0x180004cf7  xor     r9d, r9d; lpType
0x180004cfa  mov     [rsp+2D0h+phkResult], r13; lpData
0x180004cff  xor     r8d, r8d; lpReserved
0x180004d02  call    cs:__imp_RegQueryValueExW
0x180004d09  nop     dword ptr [rax+rax+00h]
0x180004d0e  xor     r8d, r8d
0x180004d11  mov     r12d, eax
0x180004d14  test    eax, eax
0x180004d16  jz      loc_180004E86
0x180004d1c  jle     short loc_180004D29
0x180004d1e  movzx   r12d, ax
0x180004d22  or      r12d, 80070000h
0x180004d29  mov     r13, r8
0x180004d2c  mov     rcx, [rsp+2D0h+var_290]; hKey
0x180004d31  call    cs:__imp_RegCloseKey
0x180004d38  nop     dword ptr [rax+rax+00h]
0x180004d3d  test    rsi, rsi
0x180004d40  jz      short loc_180004D51
0x180004d42  mov     rcx, rsi; pv
0x180004d45  call    cs:__imp_CoTaskMemFree
0x180004d4c  nop     dword ptr [rax+rax+00h]
0x180004d51  test    rdi, rdi
0x180004d54  jnz     loc_180004DEF
0x180004d5a  test    rbx, rbx
0x180004d5d  jnz     loc_180004DEF
0x180004d63  test    r15, r15
0x180004d66  jz      short loc_180004D77
0x180004d68  mov     rcx, r15; pv
0x180004d6b  call    cs:__imp_CoTaskMemFree
0x180004d72  nop     dword ptr [rax+rax+00h]
0x180004d77  test    r14, r14
0x180004d7a  jz      short loc_180004D8B
0x180004d7c  mov     rcx, r14; pv
0x180004d7f  call    cs:__imp_CoTaskMemFree
0x180004d86  nop     dword ptr [rax+rax+00h]
0x180004d8b  mov     eax, r12d
0x180004d8e  mov     rcx, [rbp+1D0h+var_50]
0x180004d95  xor     rcx, rsp; StackCookie
0x180004d98  call    __security_check_cookie
0x180004d9d  add     rsp, 298h
0x180004da4  pop     r15
0x180004da6  pop     r14
0x180004da8  pop     r13
0x180004daa  pop     r12
0x180004dac  pop     rdi
0x180004dad  pop     rsi
0x180004dae  pop     rbx
0x180004daf  pop     rbp
0x180004db0  retn
0x180004db2  jle     loc_180004B32
0x180004db8  movzx   edi, ax
0x180004dbb  or      edi, 80070000h
0x180004dc1  jmp     loc_180004B32
0x180004dc6  jle     short loc_180004DD3
0x180004dc8  movzx   r12d, r12w
0x180004dcc  or      r12d, 80070000h
0x180004dd3  mov     r13, rax
0x180004dd6  jmp     loc_180004D3D
0x180004ddb  jle     loc_180004C17
0x180004de1  movzx   edi, ax
0x180004de4  or      edi, 80070000h
0x180004dea  jmp     loc_180004C17
0x180004def  mov     rdx, [rsp+2D0h+hKey]; cb
0x180004df4  lea     rax, [rsp+2D0h+var_280]
0x180004df9  mov     [rsp+2D0h+lpcbData], rax; unsigned __int16 **
0x180004dfe  mov     r9, r13; SourceSize
0x180004e01  mov     rax, [rsp+2D0h+var_270]
0x180004e06  mov     r8, rbx; void *
0x180004e09  mov     rcx, rdi; this
0x180004e0c  mov     [rsp+2D0h+phkResult], rax; unsigned __int64
0x180004e11  call    ?GetMergedAadLoginUrl@ProofOfPossessionTokenProvider@@YAJPEBG_K01PEAPEAGPEA_K@Z; ProofOfPossessionTokenProvider::GetMergedAadLoginUrl(ushort const *,unsigned __int64,ushort const *,unsigned __int64,ushort * *,unsigned __int64 *)
0x180004e16  mov     r12d, eax
0x180004e19  test    rbx, rbx
0x180004e1c  jz      short loc_180004E2D
0x180004e1e  mov     rcx, rbx; pv
0x180004e21  call    cs:__imp_CoTaskMemFree
0x180004e28  nop     dword ptr [rax+rax+00h]
0x180004e2d  test    rdi, rdi
0x180004e30  jz      loc_180004D63
0x180004e36  mov     rcx, rdi; pv
0x180004e39  call    cs:__imp_CoTaskMemFree
0x180004e40  nop     dword ptr [rax+rax+00h]
0x180004e45  jmp     loc_180004D63
0x180004e4a  mov     r12d, 80070057h
0x180004e50  jmp     loc_180004D8B
0x180004e55  mov     ecx, [rsp+2D0h+cbData]
0x180004e59  shr     rcx, 1
0x180004e5c  lea     rdx, [rcx+1]
0x180004e60  mov     [rsi+rcx*2], r13w
0x180004e65  lea     rdx, [rsi+rdx*2]
0x180004e69  mov     [rdx], r13w
0x180004e6d  cmp     rdx, rsi
0x180004e70  jb      loc_180004F06
0x180004e76  cmp     [rdx], r13w
0x180004e7a  jnz     loc_180004F06
0x180004e80  sub     rdx, 2
0x180004e84  jmp     short loc_180004E6D
0x180004e86  mov     ecx, [rsp+2D0h+cbData]
0x180004e8a  shr     rcx, 1
0x180004e8d  lea     rdx, ds:2[rcx*2]
0x180004e95  mov     [r13+rcx*2+0], r8w
0x180004e9b  add     rdx, r13
0x180004e9e  mov     [rdx], r8w
0x180004ea2  cmp     rdx, r13
  ... truncated ...
```
