# I_VerifyRfc3161CounterSignature(_CRYPT_PROVIDER_DATA *,_CRYPT_PROVIDER_SGNR *,ulong,_CRYPT_ATTRIBUTE *,Rfc3161Timestamp::Enum)

- ea: `0x180010350`
- end: `0x180010927`
- name: `?I_VerifyRfc3161CounterSignature@@YAXPEAU_CRYPT_PROVIDER_DATA@@PEAU_CRYPT_PROVIDER_SGNR@@KPEAU_CRYPT_ATTRIBUTE@@W4Enum@Rfc3161Timestamp@@@Z`
- size: `1495`
- prototype: `_UNKNOWN **__fastcall(__int64, __int64, unsigned int, __int64, int)`
- caller_count: `2`
- callee_count: `15`
- tags: `registry_config, loader_planting`

## callers

- `0x18000fbec`
- `0x1800101a4`

## callees

- `0x180010350`
- `0x180011974`
- `0x180011ae0`
- `0x18001b344`
- `0x18001b420`
- `0x18001ed58`
- `0x18002121c`
- `0x18002124c`
- `0x1800227cc`
- `0x18002285c`
- `0x180023128`
- `0x180023dd0`
- `0x180039f50`
- `0x18004de6a`
- `0x180051010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180010530`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180010530`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010581`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001059c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800105e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800105ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010649`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800106e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001073e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001080d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001081a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010581`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001059c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800105e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800105ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010649`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800106e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001073e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001080d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001081a`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryA` at `0x180010513`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryA` at `0x180010513`
- `CRYPT32!CryptMsgGetParam` at `0x1800106d6`
- `CRYPT32!CryptMsgGetParam` at `0x180010734`
- `CRYPT32!CryptMsgGetParam` at `0x1800106d6`
- `CRYPT32!CryptMsgGetParam` at `0x180010734`
- `CRYPT32!CryptDecodeObjectEx` at `0x1800104b8`
- `CRYPT32!CryptDecodeObjectEx` at `0x1800104b8`
- `CRYPT32!CertFreeCertificateChain` at `0x18001088e`
- `CRYPT32!CertFreeCertificateChain` at `0x18001088e`
- `CRYPT32!CertFreeCertificateContext` at `0x18001089c`
- `CRYPT32!CertFreeCertificateContext` at `0x18001089c`

## string_xrefs

- `0x18001050c`: `crypt32.dll`

## pseudocode

```c
_UNKNOWN **__fastcall I_VerifyRfc3161CounterSignature(__int64 a1, __int64 a2, unsigned int a3, __int64 a4, int a5)
{
  _UNKNOWN **result; // rax
  int v8; // r13d
  unsigned __int8 *v9; // rdx
  unsigned __int8 *v10; // rbx
  unsigned int v11; // r15d
  __int64 v12; // rdi
  __int64 v13; // rax
  __int64 v14; // rax
  unsigned int v15; // esi
  unsigned __int8 *v16; // r12
  __int64 v17; // r8
  DWORD v18; // ecx
  unsigned __int8 *v19; // rsi
  unsigned __int8 *v20; // rdx
  HMODULE LibraryA; // rax
  FARPROC ProcAddress; // rax
  const CERT_CONTEXT *v23; // rbx
  unsigned int v24; // ecx
  const CERT_CHAIN_CONTEXT *v25; // rdi
  HCRYPTMSG v26; // rcx
  int LastError; // eax
  _QWORD *v28; // r15
  __int64 v29; // rsi
  __int64 v30; // r13
  __int64 v31; // rax
  unsigned int v32; // esi
  __int64 v33; // rcx
  __int64 v34; // rax
  HCRYPTMSG *pcbStructInfo; // [rsp+58h] [rbp-81h] BYREF
  unsigned __int8 *v36; // [rsp+60h] [rbp-79h] BYREF
  __int64 v37; // [rsp+68h] [rbp-71h] BYREF
  unsigned __int8 *pvStructInfo; // [rsp+70h] [rbp-69h] BYREF
  PCCERT_CONTEXT pCertContext; // [rsp+78h] [rbp-61h] BYREF
  __int64 v40; // [rsp+80h] [rbp-59h] BYREF
  __int64 v41; // [rsp+88h] [rbp-51h] BYREF
  HCRYPTMSG hCryptMsg; // [rsp+90h] [rbp-49h] BYREF
  __int64 v43; // [rsp+98h] [rbp-41h] BYREF
  __int64 v44; // [rsp+A0h] [rbp-39h] BYREF
  __int64 *v45; // [rsp+A8h] [rbp-31h] BYREF
  int v46; // [rsp+B8h] [rbp-21h] BYREF
  __int64 v47; // [rsp+BCh] [rbp-1Dh]
  int v48; // [rsp+D0h] [rbp-9h]
  _QWORD *v49; // [rsp+D8h] [rbp-1h]
  _UNKNOWN *retaddr; // [rsp+130h] [rbp+57h] BYREF
  DWORD pcbData; // [rsp+138h] [rbp+5Fh] BYREF
  __int64 v52; // [rsp+140h] [rbp+67h]
  unsigned int v53; // [rsp+148h] [rbp+6Fh]

  result = &retaddr;
  v53 = a3;
  v52 = a2;
  if ( *(_DWORD *)a1 <= 0xB0u || !*(_DWORD *)(a1 + 176) )
  {
    if ( *(_DWORD *)(a4 + 8) != 1 )
    {
      *(_DWORD *)(*(_QWORD *)(a1 + 80) + 132LL) = 87;
      result = *(_UNKNOWN ***)(a1 + 80);
      *((_DWORD *)result + 16) = -2146869243;
      *(_DWORD *)(a1 + 48) = 87;
      return result;
    }
    v8 = a5;
    v9 = 0;
    pvStructInfo = 0;
    v10 = 0;
    v36 = 0;
    v11 = 0;
    LODWORD(pcbStructInfo) = 0;
    v12 = 0;
    v41 = 0;
    v40 = 0;
    pCertContext = 0;
    v37 = 0;
    if ( a5 )
    {
      v17 = *(_QWORD *)(a4 + 16);
      v11 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 224) + 56LL) + 32LL);
      v18 = *(_DWORD *)(a1 + 104);
      pvStructInfo = 0;
      LODWORD(pcbStructInfo) = 0;
      if ( !CryptDecodeObjectEx(
              v18,
              "1.3.6.1.4.1.311.2.4.4",
              *(const BYTE **)(v17 + 8),
              *(_DWORD *)v17,
              0x8000u,
              0,
              &pvStructInfo,
              (DWORD *)&pcbStructInfo) )
        goto LABEL_53;
      v19 = pvStructInfo;
      v20 = 0;
      if ( pvStructInfo )
      {
        std::unique_ptr<_CRYPT_ATTRIBUTES,deleter<release::heapfree::tag>>::_Delete(&v36);
        v10 = v19;
        v20 = v19;
        v36 = v19;
      }
      if ( *(_DWORD *)v10 || *((_DWORD *)v20 + 1) != *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 224) + 56LL) + 4LL) )
      {
LABEL_53:
        *(_DWORD *)(*(_QWORD *)(a1 + 80) + 132LL) = -2146869243;
        *(_DWORD *)(*(_QWORD *)(a1 + 80) + 64LL) = -2146869243;
        *(_DWORD *)(a1 + 48) = -2146869243;
        goto LABEL_54;
      }
      v15 = *((_DWORD *)v20 + 2);
      v16 = (unsigned __int8 *)*((_QWORD *)v20 + 2);
    }
    else
    {
      v13 = *(_QWORD *)(a1 + 160);
      if ( v13 && *(_QWORD *)(v13 + 40) )
      {
        if ( (int)I_GetParamFromMessage(
                    *(HCRYPTMSG *)(a1 + 112),
                    a5 + 27,
                    0,
                    &pvStructInfo,
                    (unsigned int *)&pcbStructInfo) < 0 )
        {
          *(_DWORD *)(*(_QWORD *)(a1 + 80) + 132LL) = v8 + 87;
          *(_DWORD *)(*(_QWORD *)(a1 + 80) + 64LL) = -2146869243;
          *(_DWORD *)(a1 + 48) = v8 + 87;
LABEL_54:
          std::unique_ptr<_CRYPT_ATTRIBUTES,deleter<release::heapfree::tag>>::_Delete(&v36);
          return (_UNKNOWN **)std::unique_ptr<_CRYPT_ATTRIBUTES,deleter<release::heapfree::tag>>::_Delete(&v37);
        }
        v9 = pvStructInfo;
        v11 = (unsigned int)pcbStructInfo;
      }
      std::unique_ptr<unsigned char,deleter<release::heapfree::tag>>::reset(&v37, v9);
      v14 = *(_QWORD *)(a4 + 16);
      v12 = v37;
      v15 = *(_DWORD *)v14;
      v16 = *(unsigned __int8 **)(v14 + 8);
    }
    LibraryA = LoadLibraryA("crypt32.dll");
    if ( !LibraryA )
      goto LABEL_54;
    pvStructInfo = (unsigned __int8 *)LibraryA;
    ProcAddress = GetProcAddress(LibraryA, "CryptVerifyTimeStampSignature");
    if ( !ProcAddress )
    {
LABEL_20:
      wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&pvStructInfo);
      goto LABEL_54;
    }
    if ( !((unsigned int (__fastcall *)(unsigned __int8 *, _QWORD, __int64, _QWORD, _QWORD, __int64 *, PCCERT_CONTEXT *, __int64 *))ProcAddress)(
            v16,
            v15,
            v12,
            v11,
            0,
            &v40,
            &pCertContext,
            &v41) )
    {
      *(_DWORD *)(*(_QWORD *)(a1 + 80) + 132LL) = GetLastError();
      *(_DWORD *)(*(_QWORD *)(a1 + 80) + 64LL) = -2146869243;
      *(_DWORD *)(a1 + 48) = GetLastError();
      goto LABEL_20;
    }
    v23 = pCertContext;
    v45 = &v41;
    v44 = v40;
    if ( !(*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)(a1 + 64) + 24LL))(a1, v41) )
      goto LABEL_24;
    if ( !(unsigned int)_IsValidTimeStampCert(pCertContext) )
      goto LABEL_49;
    pcbStructInfo = 0;
    if ( !_BuildChainForPubKeyParaInheritance(
            (struct _CRYPT_PROVIDER_DATA *)a1,
            pCertContext,
            (const struct _CERT_CHAIN_CONTEXT **)&pcbStructInfo) )
    {
LABEL_24:
      *(_DWORD *)(*(_QWORD *)(a1 + 80) + 132LL) = -2146869243;
      *(_DWORD *)(*(_QWORD *)(a1 + 80) + 64LL) = GetLastError();
      *(_DWORD *)(a1 + 48) = GetLastError();
LABEL_49:
      if ( v23 )
        CertFreeCertificateContext(v23);
      CryptMemFreer::~CryptMemFreer((CryptMemFreer *)&v44);
      std::unique_ptr<void *,deleter<release::hcertstore::tag>>::_Delete(&v45);
      goto LABEL_20;
    }
    v25 = (const CERT_CHAIN_CONTEXT *)pcbStructInfo;
    hCryptMsg = I_OpenBlob(v24, v16, v15);
    v26 = hCryptMsg;
    if ( !hCryptMsg )
    {
      *(_DWORD *)(a1 + 48) = GetLastError();
      *(_DWORD *)(*(_QWORD *)(a1 + 80) + 132LL) = -2146869247;
      goto LABEL_47;
    }
    pcbStructInfo = &hCryptMsg;
    if ( v8 == 1 )
    {
      LastError = I_ProcessSealingTimestamp(v40, hCryptMsg, v16, v15, *(_DWORD *)(a1 + 104), (__int64)v25);
      if ( LastError < 0 )
      {
        *(_DWORD *)(*(_QWORD *)(a1 + 80) + 132LL) = -2146869243;
        *(_DWORD *)(*(_QWORD *)(a1 + 80) + 64LL) = LastError;
LABEL_32:
        *(_DWORD *)(a1 + 48) = LastError;
LABEL_46:
        std::unique_ptr<void *,deleter<release::hcryptmsg::tag>>::_Delete(&pcbStructInfo);
LABEL_47:
        if ( v25 )
          CertFreeCertificateChain(v25);
        goto LABEL_49;
      }
      v26 = hCryptMsg;
    }
    pcbData = 0;
    if ( CryptMsgGetParam(v26, 6u, 0, 0, &pcbData) )
    {
      v28 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)(a1 + 64) + 8LL))(pcbData);
      if ( v28 )
      {
        if ( !CryptMsgGetParam(hCryptMsg, 6u, 0, v28, &pcbData) )
          goto LABEL_40;
        v29 = v40;
        v30 = v52;
        *(_QWORD *)(v52 + 4) = *(_QWORD *)(*(_QWORD *)(v40 + 16) + 72LL);
        memset_0(&v46, 0, 0x40u);
        v46 = 64;
        v31 = *(_QWORD *)(v29 + 16);
        v32 = v53;
        v33 = *(_QWORD *)(v31 + 72);
        v34 = *(_QWORD *)(a1 + 64);
        v47 = v33;
        v49 = v28;
        v48 = 16;
        if ( !(*(unsigned int (__fastcall **)(__int64, __int64, _QWORD, int *))(v34 + 32))(a1, 1, v53, &v46) )
        {
LABEL_40:
          *(_DWORD *)(a1 + 48) = GetLastError();
          *(_DWORD *)(*(_QWORD *)(a1 + 80) + 132LL) = -2146869247;
          (*(void (__fastcall **)(_QWORD *))(*(_QWORD *)(a1 + 64) + 16LL))(v28);
          goto LABEL_46;
        }
        if ( (*(unsigned int (__fastcall **)(__int64, _QWORD, __int64, _QWORD, PCCERT_CONTEXT))(*(_QWORD *)(a1 + 64)
                                                                                              + 40LL))(
               a1,
               v32,
               1,
               0,
               pCertContext) )
        {
          v43 = 0;
          if ( (unsigned int)IsWeakHashObjectIdentifier(2, *(_QWORD *)(*(_QWORD *)(v40 + 16) + 16LL), a1, v30, 0, &v43)
            || (unsigned int)IsWeakHashObjectIdentifier(2, v28[5], a1, v30, 0, &v43) )
          {
            *(_DWORD *)(*(_QWORD *)(a1 + 80) + 132LL) = -2146869243;
            *(_DWORD *)(*(_QWORD *)(a1 + 80) + 64LL) = -2146893822;
            *(_DWORD *)(a1 + 48) = -2146893822;
          }
          goto LABEL_46;
        }
        *(_DWORD *)(*(_QWORD *)(a1 + 80) + 132LL) = -2146869243;
        *(_DWORD *)(*(_QWORD *)(a1 + 80) + 64LL) = GetLastError();
        LastError = GetLastError();
        goto LABEL_32;
      }
      *(_DWORD *)(a1 + 48) = 8;
    }
    else
    {
      *(_DWORD *)(a1 + 48) = GetLastError();
    }
    *(_DWORD *)(*(_QWORD *)(a1 + 80) + 132LL) = -2146869247;
    goto LABEL_46;
  }
  return result;
}

```

## disassembly

```asm
0x180010350  mov     rax, rsp
0x180010353  mov     [rax+20h], rbx
0x180010357  mov     [rax+18h], r8d
0x18001035b  mov     [rax+10h], rdx
0x18001035f  push    rbp
0x180010360  push    rsi
0x180010361  push    rdi
0x180010362  push    r12
0x180010364  push    r13
0x180010366  push    r14
0x180010368  push    r15
0x18001036a  lea     rbp, [rax-57h]
0x18001036e  sub     rsp, 0F0h
0x180010375  xor     r12d, r12d
0x180010378  mov     rsi, r9
0x18001037b  cmp     dword ptr [rcx], 0B0h
0x180010381  mov     r14, rcx
0x180010384  jbe     short loc_180010393
0x180010386  cmp     [rcx+0B0h], r12d
0x18001038d  jnz     loc_18001090C
0x180010393  cmp     dword ptr [r9+8], 1
0x180010398  jz      short loc_1800103BD
0x18001039a  mov     rax, [rcx+50h]
0x18001039e  mov     ecx, 57h ; 'W'
0x1800103a3  mov     [rax+84h], ecx
0x1800103a9  mov     rax, [r14+50h]
0x1800103ad  mov     dword ptr [rax+40h], 80096005h
0x1800103b4  mov     [r14+30h], ecx
0x1800103b8  jmp     loc_18001090C
0x1800103bd  mov     r13d, [rbp+4Fh+arg_20]
0x1800103c1  mov     rdx, r12
0x1800103c4  mov     [rbp+4Fh+var_B8], rdx
0x1800103c8  mov     rbx, r12
0x1800103cb  mov     [rbp+4Fh+var_C8], rbx
0x1800103cf  mov     r15d, r12d
0x1800103d2  mov     dword ptr [rsp+120h+pcbStructInfo], r12d
0x1800103d7  mov     rdi, r12
0x1800103da  mov     [rbp+4Fh+var_A0], r12
0x1800103de  mov     [rbp+4Fh+var_A8], r12
0x1800103e2  mov     [rbp+4Fh+pCertContext], r12
0x1800103e6  mov     [rbp+4Fh+var_C0], r12
0x1800103ea  test    r13d, r13d
0x1800103ed  jnz     short loc_18001046A
0x1800103ef  mov     rax, [rcx+0A0h]
0x1800103f6  test    rax, rax
0x1800103f9  jz      short loc_18001044E
0x1800103fb  cmp     [rax+28h], r12
0x1800103ff  jz      short loc_18001044E
0x180010401  mov     rcx, [rcx+70h]; hCryptMsg
0x180010405  lea     rax, [rsp+120h+pcbStructInfo]
0x18001040a  lea     r9, [rbp+4Fh+var_B8]; unsigned __int8 **
0x18001040e  mov     qword ptr [rsp+120h+dwFlags], rax; unsigned int *
0x180010413  xor     r8d, r8d; dwIndex
0x180010416  lea     edx, [r13+1Bh]; dwParamType
0x18001041a  call    ?I_GetParamFromMessage@@YAJPEAXKKPEAPEAEPEAK@Z; I_GetParamFromMessage(void *,ulong,ulong,uchar * *,ulong *)
0x18001041f  test    eax, eax
0x180010421  jns     short loc_180010445
0x180010423  mov     rax, [r14+50h]
0x180010427  lea     ecx, [r13+57h]
0x18001042b  mov     [rax+84h], ecx
0x180010431  mov     rax, [r14+50h]
0x180010435  mov     dword ptr [rax+40h], 80096005h
0x18001043c  mov     [r14+30h], ecx
0x180010440  jmp     loc_1800108FA
0x180010445  mov     rdx, [rbp+4Fh+var_B8]
0x180010449  mov     r15d, dword ptr [rsp+120h+pcbStructInfo]
0x18001044e  lea     rcx, [rbp+4Fh+var_C0]
0x180010452  call    ?reset@?$unique_ptr@EU?$deleter@Utag@heapfree@release@@@@@std@@QEAAXPEAE@Z; std::unique_ptr<uchar,deleter<release::heapfree::tag>>::reset(uchar *)
0x180010457  mov     rax, [rsi+10h]
0x18001045b  mov     rdi, [rbp+4Fh+var_C0]
0x18001045f  mov     esi, [rax]
0x180010461  mov     r12, [rax+8]
0x180010465  jmp     loc_18001050C
0x18001046a  mov     rax, [rcx+0E0h]
0x180010471  lea     rdx, a136141311244; "1.3.6.1.4.1.311.2.4.4"
0x180010478  mov     r8, [r9+10h]
0x18001047c  mov     rcx, [rax+38h]
0x180010480  lea     rax, [rsp+120h+pcbStructInfo]
0x180010485  mov     [rsp+38h], rax; pcbStructInfo
0x18001048a  lea     rax, [rbp+4Fh+var_B8]
0x18001048e  mov     [rsp+120h+pvStructInfo], rax; pvStructInfo
0x180010493  mov     [rsp+120h+pDecodePara], r12; pDecodePara
0x180010498  mov     r15d, [rcx+20h]
0x18001049c  mov     ecx, [r14+68h]; dwCertEncodingType
0x1800104a0  mov     [rbp+4Fh+var_B8], r12
0x1800104a4  mov     dword ptr [rsp+120h+pcbStructInfo], r12d
0x1800104a9  mov     r9d, [r8]; cbEncoded
0x1800104ac  mov     r8, [r8+8]; pbEncoded
0x1800104b0  mov     [rsp+120h+dwFlags], 8000h; dwFlags
0x1800104b8  call    cs:__imp_CryptDecodeObjectEx
0x1800104be  test    eax, eax
0x1800104c0  jz      loc_1800108D9
0x1800104c6  mov     rsi, [rbp+4Fh+var_B8]
0x1800104ca  mov     rdx, r12
0x1800104cd  test    rsi, rsi
0x1800104d0  jz      short loc_1800104E5
0x1800104d2  lea     rcx, [rbp+4Fh+var_C8]
0x1800104d6  call    ?_Delete@?$unique_ptr@U_CRYPT_ATTRIBUTES@@U?$deleter@Utag@heapfree@release@@@@@std@@AEAAXXZ; std::unique_ptr<_CRYPT_ATTRIBUTES,deleter<release::heapfree::tag>>::_Delete(void)
0x1800104db  mov     rbx, rsi
0x1800104de  mov     rdx, rsi
0x1800104e1  mov     [rbp+4Fh+var_C8], rbx
0x1800104e5  cmp     [rbx], r12d
0x1800104e8  ja      loc_1800108D9
0x1800104ee  mov     rax, [r14+0E0h]
0x1800104f5  mov     rcx, [rax+38h]
0x1800104f9  mov     eax, [rcx+4]
0x1800104fc  cmp     [rdx+4], eax
0x1800104ff  jnz     loc_1800108D9
0x180010505  mov     esi, [rdx+8]
0x180010508  mov     r12, [rdx+10h]
0x18001050c  lea     rcx, LibFileName; "crypt32.dll"
0x180010513  call    cs:__imp_LoadLibraryA
0x180010519  test    rax, rax
0x18001051c  jz      loc_1800108FA
0x180010522  lea     rdx, ProcName; "CryptVerifyTimeStampSignature"
0x180010529  mov     [rbp+4Fh+var_B8], rax
0x18001052d  mov     rcx, rax; hModule
0x180010530  call    cs:__imp_GetProcAddress
0x180010536  test    rax, rax
0x180010539  jnz     short loc_180010549
0x18001053b  lea     rcx, [rbp+4Fh+var_B8]
0x18001053f  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x180010544  jmp     loc_1800108FA
0x180010549  lea     rcx, [rbp+4Fh+var_A0]
0x18001054d  mov     r9d, r15d
0x180010550  mov     [rsp+38h], rcx
0x180010555  mov     r8, rdi
0x180010558  lea     rcx, [rbp+4Fh+pCertContext]
0x18001055c  mov     edx, esi
0x18001055e  mov     [rsp+120h+pvStructInfo], rcx
0x180010563  lea     rcx, [rbp+4Fh+var_A8]
0x180010567  mov     [rsp+120h+pDecodePara], rcx
0x18001056c  mov     rcx, r12
0x18001056f  mov     qword ptr [rsp+120h+dwFlags], 0
0x180010578  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001057d  test    eax, eax
0x18001057f  jnz     short loc_1800105A8
0x180010581  call    cs:__imp_GetLastError
0x180010587  mov     rcx, [r14+50h]
0x18001058b  mov     [rcx+84h], eax
0x180010591  mov     rax, [r14+50h]
0x180010595  mov     dword ptr [rax+40h], 80096005h
0x18001059c  call    cs:__imp_GetLastError
0x1800105a2  mov     [r14+30h], eax
0x1800105a6  jmp     short loc_18001053B
0x1800105a8  mov     rdx, [rbp+4Fh+var_A0]
0x1800105ac  lea     rax, [rbp+4Fh+var_A0]
0x1800105b0  mov     rbx, [rbp+4Fh+pCertContext]
0x1800105b4  mov     rcx, r14
0x1800105b7  mov     [rbp+4Fh+var_80], rax
0x1800105bb  mov     rax, [rbp+4Fh+var_A8]
0x1800105bf  mov     [rbp+4Fh+var_88], rax
0x1800105c3  mov     rax, [r14+40h]
0x1800105c7  mov     rax, [rax+18h]
0x1800105cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800105d0  test    eax, eax
0x1800105d2  jnz     short loc_1800105FE
0x1800105d4  mov     rax, [r14+50h]
0x1800105d8  mov     dword ptr [rax+84h], 80096005h
0x1800105e2  call    cs:__imp_GetLastError
0x1800105e8  mov     rcx, [r14+50h]
0x1800105ec  mov     [rcx+40h], eax
0x1800105ef  call    cs:__imp_GetLastError
0x1800105f5  mov     [r14+30h], eax
0x1800105f9  jmp     loc_180010894
0x1800105fe  mov     rcx, [rbp+4Fh+pCertContext]; pCertContext
0x180010602  call    ?_IsValidTimeStampCert@@YAHPEBU_CERT_CONTEXT@@@Z; _IsValidTimeStampCert(_CERT_CONTEXT const *)
0x180010607  test    eax, eax
0x180010609  jz      loc_180010894
0x18001060f  mov     rdx, [rbp+4Fh+pCertContext]; struct _CERT_CONTEXT *
0x180010613  lea     r8, [rsp+120h+pcbStructInfo]; struct _CERT_CHAIN_CONTEXT **
0x180010618  mov     rcx, r14; struct _CRYPT_PROVIDER_DATA *
0x18001061b  mov     [rsp+120h+pcbStructInfo], 0
0x180010624  call    ?_BuildChainForPubKeyParaInheritance@@YAHPEAU_CRYPT_PROVIDER_DATA@@PEBU_CERT_CONTEXT@@PEAPEBU_CERT_CHAIN_CONTEXT@@@Z; _BuildChainForPubKeyParaInheritance(_CRYPT_PROVIDER_DATA *,_CERT_CONTEXT const *,_CERT_CHAIN_CONTEXT const * *)
0x180010629  test    eax, eax
0x18001062b  jz      short loc_1800105D4
0x18001062d  mov     rdi, [rsp+120h+pcbStructInfo]
0x180010632  mov     r8d, esi; unsigned int
0x180010635  mov     rdx, r12; unsigned __int8 *
0x180010638  call    ?I_OpenBlob@@YAPEAXKPEAEK@Z; I_OpenBlob(ulong,uchar *,ulong)
0x18001063d  mov     [rbp+4Fh+hCryptMsg], rax
0x180010641  mov     rcx, rax
0x180010644  test    rax, rax
0x180010647  jnz     short loc_180010666
0x180010649  call    cs:__imp_GetLastError
0x18001064f  mov     [r14+30h], eax
0x180010653  mov     rax, [r14+50h]
0x180010657  mov     dword ptr [rax+84h], 80096001h
0x180010661  jmp     loc_180010886
0x180010666  lea     rax, [rbp+4Fh+hCryptMsg]
0x18001066a  mov     [rsp+120h+pcbStructInfo], rax
0x18001066f  cmp     r13d, 1
0x180010673  jnz     short loc_1800106BA
0x180010675  mov     eax, [r14+68h]
0x180010679  mov     rdx, rcx
0x18001067c  mov     rcx, [rbp+4Fh+var_A8]
0x180010680  mov     r9d, esi
0x180010683  mov     [rsp+120h+pDecodePara], rdi
0x180010688  mov     r8, r12
0x18001068b  mov     [rsp+120h+dwFlags], eax
0x18001068f  call    ?I_ProcessSealingTimestamp@@YAJPEAU_CRYPT_TIMESTAMP_CONTEXT@@PEAXPEBEKKPEBU_CERT_CHAIN_CONTEXT@@W4Enum@SealTimestampAction@@@Z; I_ProcessSealingTimestamp(_CRYPT_TIMESTAMP_CONTEXT *,void *,uchar const *,ulong,ulong,_CERT_CHAIN_CONTEXT const *,SealTimestampAction::Enum)
0x180010694  test    eax, eax
0x180010696  jns     short loc_1800106B6
0x180010698  mov     rcx, [r14+50h]
0x18001069c  mov     dword ptr [rcx+84h], 80096005h
0x1800106a6  mov     rcx, [r14+50h]
0x1800106aa  mov     [rcx+40h], eax
0x1800106ad  mov     [r14+30h], eax
0x1800106b1  jmp     loc_18001087C
0x1800106b6  mov     rcx, [rbp+4Fh+hCryptMsg]; hCryptMsg
0x1800106ba  xor     r9d, r9d; pvData
0x1800106bd  mov     [rbp+4Fh+pcbData], 0
0x1800106c4  lea     rax, [rbp+4Fh+pcbData]
0x1800106c8  xor     r8d, r8d; dwIndex
0x1800106cb  mov     qword ptr [rsp+120h+dwFlags], rax; pcbData
0x1800106d0  lea     esi, [r9+6]
0x1800106d4  mov     edx, esi; dwParamType
0x1800106d6  call    cs:__imp_CryptMsgGetParam
0x1800106dc  test    eax, eax
0x1800106de  jnz     short loc_1800106FD
0x1800106e0  call    cs:__imp_GetLastError
0x1800106e6  mov     [r14+30h], eax
0x1800106ea  mov     rax, [r14+50h]
0x1800106ee  mov     dword ptr [rax+84h], 80096001h
0x1800106f8  jmp     loc_18001087C
0x1800106fd  mov     rax, [r14+40h]
0x180010701  mov     ecx, [rbp+4Fh+pcbData]
0x180010704  mov     rax, [rax+8]
0x180010708  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001070d  mov     r15, rax
0x180010710  test    rax, rax
0x180010713  jnz     short loc_18001071F
0x180010715  mov     dword ptr [r14+30h], 8
0x18001071d  jmp     short loc_1800106EA
0x18001071f  mov     rcx, [rbp+4Fh+hCryptMsg]; hCryptMsg
0x180010723  lea     rax, [rbp+4Fh+pcbData]
0x180010727  mov     r9, r15; pvData
0x18001072a  mov     qword ptr [rsp+120h+dwFlags], rax; pcbData
0x18001072f  xor     r8d, r8d; dwIndex
0x180010732  mov     edx, esi; dwParamType
0x180010734  call    cs:__imp_CryptMsgGetParam
0x18001073a  test    eax, eax
0x18001073c  jnz     short loc_18001076B
0x18001073e  call    cs:__imp_GetLastError
0x180010744  mov     [r14+30h], eax
0x180010748  mov     rcx, r15
0x18001074b  mov     rax, [r14+50h]
0x18001074f  mov     dword ptr [rax+84h], 80096001h
0x180010759  mov     rax, [r14+40h]
0x18001075d  mov     rax, [rax+10h]
0x180010761  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010766  jmp     loc_18001087C
0x18001076b  mov     rsi, [rbp+4Fh+var_A8]
0x18001076f  mov     r12d, 40h ; '@'
0x180010775  mov     r13, [rbp+4Fh+arg_8]
0x180010779  mov     r8d, r12d; Size
0x18001077c  xor     edx, edx; Val
0x18001077e  mov     rax, [rsi+10h]
0x180010782  mov     rcx, [rax+48h]
0x180010786  mov     [r13+4], rcx
0x18001078a  lea     rcx, [rbp+4Fh+var_70]; void *
0x18001078e  call    memset_0
0x180010793  mov     [rbp+4Fh+var_70], r12d
0x180010797  lea     r9, [rbp+4Fh+var_70]
0x18001079b  mov     rax, [rsi+10h]
0x18001079f  lea     edx, [r12-3Fh]
0x1800107a4  mov     esi, [rbp+4Fh+arg_10]
0x1800107a7  mov     r8d, esi
0x1800107aa  mov     rcx, [rax+48h]
0x1800107ae  mov     rax, [r14+40h]
0x1800107b2  mov     [rbp+4Fh+var_6C], rcx
0x1800107b6  mov     rcx, r14
0x1800107b9  mov     [rbp+4Fh+var_50], r15
0x1800107bd  mov     [rbp+4Fh+var_58], 10h
0x1800107c4  mov     rax, [rax+20h]
0x1800107c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800107cd  xor     r12d, r12d
0x1800107d0  test    eax, eax
0x1800107d2  jz      loc_18001073E
0x1800107d8  mov     rcx, [rbp+4Fh+pCertContext]
0x1800107dc  lea     r8d, [r12+1]
0x1800107e1  mov     rax, [r14+40h]
0x1800107e5  xor     r9d, r9d
0x1800107e8  mov     qword ptr [rsp+120h+dwFlags], rcx
0x1800107ed  mov     edx, esi
0x1800107ef  mov     rcx, r14
0x1800107f2  mov     rax, [rax+28h]
0x1800107f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800107fb  test    eax, eax
0x1800107fd  jnz     short loc_180010825
0x1800107ff  mov     rax, [r14+50h]
0x180010803  mov     dword ptr [rax+84h], 80096005h
0x18001080d  call    cs:__imp_GetLastError
0x180010813  mov     rcx, [r14+50h]
0x180010817  mov     [rcx+40h], eax
0x18001081a  call    cs:__imp_GetLastError
0x180010820  jmp     loc_1800106AD
0x180010825  mov     rax, [rbp+4Fh+var_A8]
0x180010829  mov     esi, 2
0x18001082e  mov     r9, r13
  ... truncated ...
```
