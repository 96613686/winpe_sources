# LoadAuthrootCTL

- ea: `0x18002bba0`
- end: `0x18002bfe6`
- name: `LoadAuthrootCTL`
- size: `1094`
- prototype: `__int64 __fastcall(BYTE *pbCtlEncoded, DWORD cbCtlEncoded)`
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18002b260`
- `0x18002ba3c`

## callees

- `0x180023060`
- `0x18002ad38`
- `0x18002bba0`
- `0x18002bfec`
- `0x18002c090`
- `0x18002c104`
- `0x18002c1b4`
- `0x180040494`
- `0x1800404f0`
- `0x180043aa0`
- `0x18004de46`
- `0x18004de76`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002bc77`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002bd0f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002bd69`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002bd7c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002bec9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002bf5f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002bf72`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002bc77`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002bd0f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002bd69`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002bd7c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002bec9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002bf5f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002bf72`
- `CRYPT32!CryptVerifyMessageSignature` at `0x18002bdd6`
- `CRYPT32!CryptVerifyMessageSignature` at `0x18002bdd6`
- `CRYPT32!CertCreateCTLContext` at `0x18002bf15`
- `CRYPT32!CertCreateCTLContext` at `0x18002bf15`
- `CRYPT32!CryptMsgOpenToDecode` at `0x18002bbe4`
- `CRYPT32!CryptMsgOpenToDecode` at `0x18002bbe4`
- `CRYPT32!CryptMsgUpdate` at `0x18002bc07`
- `CRYPT32!CryptMsgUpdate` at `0x18002bc07`

## string_xrefs

- `0x18002bc52`: `onecore\ds\security\cryptoapi\pkitrust\softpub\configciprov.cpp`
- `0x18002bc8f`: `onecore\ds\security\cryptoapi\pkitrust\softpub\configciprov.cpp`
- `0x18002bcea`: `onecore\ds\security\cryptoapi\pkitrust\softpub\configciprov.cpp`
- `0x18002bd4a`: `onecore\ds\security\cryptoapi\pkitrust\softpub\configciprov.cpp`
- `0x18002bdef`: `onecore\ds\security\cryptoapi\pkitrust\softpub\configciprov.cpp`
- `0x18002be54`: `onecore\ds\security\cryptoapi\pkitrust\softpub\configciprov.cpp`
- `0x18002be9f`: `onecore\ds\security\cryptoapi\pkitrust\softpub\configciprov.cpp`
- `0x18002bee6`: `onecore\ds\security\cryptoapi\pkitrust\softpub\configciprov.cpp`
- `0x18002bf2b`: `onecore\ds\security\cryptoapi\pkitrust\softpub\configciprov.cpp`
- `0x18002bf89`: `onecore\ds\security\cryptoapi\pkitrust\softpub\configciprov.cpp`
- `0x18002bfad`: `onecore\ds\security\cryptoapi\pkitrust\softpub\configciprov.cpp`

## pseudocode

```c
__int64 __fastcall LoadAuthrootCTL(BYTE *pbCtlEncoded, DWORD cbCtlEncoded)
{
  HCRYPTMSG v4; // rax
  const char *v5; // r9
  void *v6; // rbx
  const char *v7; // r9
  int LastError; // edi
  HLOCAL v9; // rcx
  HLOCAL v10; // rcx
  HLOCAL v11; // rcx
  HLOCAL v12; // rcx
  unsigned int v14; // ebx
  int pRecipientInfo; // [rsp+20h] [rbp-89h]
  HLOCAL hMem; // [rsp+40h] [rbp-69h] BYREF
  HLOCAL Buf1; // [rsp+48h] [rbp-61h] BYREF
  HLOCAL *p_hMem; // [rsp+58h] [rbp-51h] BYREF
  PCCERT_CONTEXT v19; // [rsp+60h] [rbp-49h]
  char v20; // [rsp+68h] [rbp-41h]
  HCRYPTMSG v21; // [rsp+70h] [rbp-39h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]

  v4 = CryptMsgOpenToDecode(0x10001u, 0, 0, 0, 0, 0);
  v21 = v4;
  v6 = v4;
  if ( v4 )
  {
    if ( !CryptMsgUpdate(v4, pbCtlEncoded, cbCtlEncoded, 1) )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x34D,
                    (unsigned int)"onecore\\ds\\security\\cryptoapi\\pkitrust\\softpub\\configciprov.cpp",
                    v7);
LABEL_18:
      wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CryptMsgClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CryptMsgClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v21);
      return (unsigned int)LastError;
    }
    hMem = 0;
    p_hMem = &hMem;
    v19 = 0;
    v20 = 1;
    LastError = GetMessageParam(v6, 1u);
    wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&p_hMem);
    if ( LastError < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x354,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\pkitrust\\softpub\\configciprov.cpp",
        (const char *)(unsigned int)LastError,
        pRecipientInfo);
LABEL_5:
      v9 = hMem;
      hMem = 0;
      if ( v9 )
        LocalFree(v9);
      goto LABEL_18;
    }
    if ( *(_DWORD *)hMem == 2 )
    {
      Buf1 = 0;
      p_hMem = &Buf1;
      v19 = 0;
      v20 = 1;
      LastError = GetMessageParam(v6, 4u);
      wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&p_hMem);
      if ( LastError < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x35C,
          (unsigned int)"onecore\\ds\\security\\cryptoapi\\pkitrust\\softpub\\configciprov.cpp",
          (const char *)(unsigned int)LastError,
          pRecipientInfo);
        v10 = Buf1;
        Buf1 = 0;
        if ( v10 )
          LocalFree(v10);
        goto LABEL_5;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x35D,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\pkitrust\\softpub\\configciprov.cpp",
        (const char *)0x80070057LL,
        pRecipientInfo);
      v11 = Buf1;
      Buf1 = 0;
      if ( v11 )
        LocalFree(v11);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x355,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\pkitrust\\softpub\\configciprov.cpp",
        (const char *)0x80070057LL,
        pRecipientInfo);
    }
    v12 = hMem;
    hMem = 0;
    if ( v12 )
      LocalFree(v12);
    LastError = -2147024809;
    goto LABEL_18;
  }
  v14 = wil::details::in1diag3::Return_GetLastError(
          retaddr,
          (void *)0x34C,
          (unsigned int)"onecore\\ds\\security\\cryptoapi\\pkitrust\\softpub\\configciprov.cpp",
          v5);
  wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CryptMsgClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CryptMsgClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v21);
  return v14;
}

```

## disassembly

```asm
0x18002bba0  mov     [rsp-8+arg_0], rbx
0x18002bba5  mov     [rsp-8+arg_10], r8
0x18002bbaa  push    rbp
0x18002bbab  push    rsi
0x18002bbac  push    rdi
0x18002bbad  push    r12
0x18002bbaf  push    r13
0x18002bbb1  push    r14
0x18002bbb3  push    r15
0x18002bbb5  lea     rbp, [rsp-27h]
0x18002bbba  sub     rsp, 0D0h
0x18002bbc1  xor     esi, esi
0x18002bbc3  mov     r15d, edx
0x18002bbc6  mov     r12, rcx
0x18002bbc9  mov     [rsp+100h+pStreamInfo], rsi; pStreamInfo
0x18002bbce  mov     r14d, 10001h
0x18002bbd4  mov     [rsp+100h+pRecipientInfo], rsi; int
0x18002bbd9  mov     ecx, r14d; dwMsgEncodingType
0x18002bbdc  xor     r9d, r9d; hCryptProv
0x18002bbdf  xor     r8d, r8d; dwMsgType
0x18002bbe2  xor     edx, edx; dwFlags
0x18002bbe4  call    cs:__imp_CryptMsgOpenToDecode
0x18002bbea  mov     [rbp+57h+var_90], rax
0x18002bbee  mov     rbx, rax
0x18002bbf1  test    rax, rax
0x18002bbf4  jz      loc_18002BFA9
0x18002bbfa  lea     r9d, [rsi+1]; fFinal
0x18002bbfe  mov     r8d, r15d; cbData
0x18002bc01  mov     rdx, r12; pbData
0x18002bc04  mov     rcx, rax; hCryptMsg
0x18002bc07  call    cs:__imp_CryptMsgUpdate
0x18002bc0d  test    eax, eax
0x18002bc0f  jz      loc_18002BF85
0x18002bc15  lea     rax, [rbp+57h+hMem]
0x18002bc19  mov     [rbp+57h+hMem], rsi
0x18002bc1d  lea     r9, [rbp+57h+arg_18]
0x18002bc21  mov     [rbp+57h+var_A8], rax
0x18002bc25  lea     r8, [rbp+57h+var_A0]
0x18002bc29  mov     [rbp+57h+arg_18], esi
0x18002bc2c  lea     edx, [rsi+1]; dwParamType
0x18002bc2f  mov     [rbp+57h+var_A0], rsi
0x18002bc33  mov     rcx, rbx; hCryptMsg
0x18002bc36  mov     [rbp+57h+var_98], 1
0x18002bc3a  call    GetMessageParam
0x18002bc3f  lea     rcx, [rbp+57h+var_A8]
0x18002bc43  mov     edi, eax
0x18002bc45  call    ??1?$out_param_t@V?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x18002bc4a  test    edi, edi
0x18002bc4c  jns     short loc_18002BC82
0x18002bc4e  mov     rcx, [rbp+5Fh]; this
0x18002bc52  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\pkitr"...
0x18002bc59  mov     r9d, edi; char *
0x18002bc5c  mov     edx, 354h; void *
0x18002bc61  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002bc66  mov     rcx, [rbp+57h+hMem]; hMem
0x18002bc6a  mov     [rbp+57h+hMem], rsi
0x18002bc6e  test    rcx, rcx
0x18002bc71  jz      loc_18002BF9C
0x18002bc77  call    cs:__imp_LocalFree
0x18002bc7d  jmp     loc_18002BF9C
0x18002bc82  mov     rax, [rbp+57h+hMem]
0x18002bc86  cmp     dword ptr [rax], 2
0x18002bc89  jz      short loc_18002BCAB
0x18002bc8b  mov     rcx, [rbp+5Fh]; this
0x18002bc8f  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\pkitr"...
0x18002bc96  mov     r9d, 80070057h; char *
0x18002bc9c  mov     edx, 355h; void *
0x18002bca1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002bca6  jmp     loc_18002BD6F
0x18002bcab  lea     rax, [rbp+57h+Buf1]
0x18002bcaf  mov     [rbp+57h+Buf1], rsi
0x18002bcb3  lea     r9, [rbp+57h+arg_18]
0x18002bcb7  mov     [rbp+57h+var_A8], rax
0x18002bcbb  lea     r8, [rbp+57h+var_A0]
0x18002bcbf  mov     [rbp+57h+arg_18], esi
0x18002bcc2  mov     edx, 4; dwParamType
0x18002bcc7  mov     [rbp+57h+var_A0], rsi
0x18002bccb  mov     rcx, rbx; hCryptMsg
0x18002bcce  mov     [rbp+57h+var_98], 1
0x18002bcd2  call    GetMessageParam
0x18002bcd7  lea     rcx, [rbp+57h+var_A8]
0x18002bcdb  mov     edi, eax
0x18002bcdd  call    ??1?$out_param_t@V?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x18002bce2  test    edi, edi
0x18002bce4  jns     short loc_18002BD1A
0x18002bce6  mov     rcx, [rbp+5Fh]; this
0x18002bcea  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\pkitr"...
0x18002bcf1  mov     r9d, edi; char *
0x18002bcf4  mov     edx, 35Ch; void *
0x18002bcf9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002bcfe  mov     rcx, [rbp+57h+Buf1]; hMem
0x18002bd02  mov     [rbp+57h+Buf1], rsi
0x18002bd06  test    rcx, rcx
0x18002bd09  jz      loc_18002BC66
0x18002bd0f  call    cs:__imp_LocalFree
0x18002bd15  jmp     loc_18002BC66
0x18002bd1a  mov     r8d, 15h; Size
0x18002bd20  cmp     [rbp+57h+arg_18], r8d
0x18002bd24  jz      short loc_18002BD2D
0x18002bd26  mov     edx, 35Dh
0x18002bd2b  jmp     short loc_18002BD46
0x18002bd2d  mov     rcx, [rbp+57h+Buf1]; Buf1
0x18002bd31  lea     rdx, a136141311101; "1.3.6.1.4.1.311.10.1"
0x18002bd38  call    memcmp_0
0x18002bd3d  test    eax, eax
0x18002bd3f  jz      short loc_18002BD8C
0x18002bd41  mov     edx, 35Eh; void *
0x18002bd46  mov     rcx, [rbp+5Fh]; this
0x18002bd4a  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\pkitr"...
0x18002bd51  mov     r9d, 80070057h; char *
0x18002bd57  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002bd5c  mov     rcx, [rbp+57h+Buf1]; hMem
0x18002bd60  mov     [rbp+57h+Buf1], rsi
0x18002bd64  test    rcx, rcx
0x18002bd67  jz      short loc_18002BD6F
0x18002bd69  call    cs:__imp_LocalFree
0x18002bd6f  mov     rcx, [rbp+57h+hMem]; hMem
0x18002bd73  mov     [rbp+57h+hMem], rsi
0x18002bd77  test    rcx, rcx
0x18002bd7a  jz      short loc_18002BD82
0x18002bd7c  call    cs:__imp_LocalFree
0x18002bd82  mov     edi, 80070057h
0x18002bd87  jmp     loc_18002BF9C
0x18002bd8c  lea     rax, [rbp+57h+pCertContext]
0x18002bd90  mov     [rbp+57h+pVerifyPara.pvGetArg], rsi
0x18002bd94  mov     [rbp+57h+var_A8], rax
0x18002bd98  lea     rcx, [rbp+57h+pVerifyPara]; pVerifyPara
0x18002bd9c  lea     rax, [rbp+57h+var_A0]
0x18002bda0  mov     [rbp+57h+pVerifyPara.cbSize], 20h ; ' '
0x18002bda7  mov     [rsp+100h+ppSignerCert], rax; ppSignerCert
0x18002bdac  xorps   xmm0, xmm0
0x18002bdaf  mov     [rsp+100h+pStreamInfo], rsi; pcbDecoded
0x18002bdb4  mov     r9d, r15d; cbSignedBlob
0x18002bdb7  mov     r8, r12; pbSignedBlob
0x18002bdba  mov     [rsp+100h+pRecipientInfo], rsi; int
0x18002bdbf  xor     edx, edx; dwSignerIndex
0x18002bdc1  mov     [rbp+57h+pVerifyPara.dwMsgAndCertEncodingType], r14d
0x18002bdc5  movdqu  xmmword ptr [rbp+57h+pVerifyPara.hCryptProv], xmm0
0x18002bdca  mov     [rbp+57h+pCertContext], rsi
0x18002bdce  mov     [rbp+57h+var_A0], rsi
0x18002bdd2  mov     [rbp+57h+var_98], 1
0x18002bdd6  call    cs:__imp_CryptVerifyMessageSignature
0x18002bddc  lea     rcx, [rbp+57h+var_A8]
0x18002bde0  mov     edi, eax
0x18002bde2  call    ??1?$out_param_t@V?$unique_any_t@Ucert_context_t@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::cert_context_t>>::~out_param_t<wil::unique_any_t<wil::cert_context_t>>(void)
0x18002bde7  test    edi, edi
0x18002bde9  jnz     short loc_18002BE10
0x18002bdeb  mov     rcx, [rbp+5Fh]; this
0x18002bdef  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\pkitr"...
0x18002bdf6  mov     edx, 36Dh; void *
0x18002bdfb  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002be00  mov     edi, eax
0x18002be02  lea     rcx, [rbp+57h+pCertContext]
0x18002be06  call    ??1?$unique_storage@U?$resource_policy@PEBU_CERT_CONTEXT@@P6AHPEBU1@@Z$1?CertFreeCertificateContext@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEBU1@PEBU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>(void)
0x18002be0b  jmp     loc_18002BCFE
0x18002be10  mov     rdi, [rbp+57h+pCertContext]
0x18002be14  mov     rax, [rdi+18h]
0x18002be18  mov     r14d, [rax+0C0h]
0x18002be1f  test    r14, r14
0x18002be22  jz      short loc_18002BE50
0x18002be24  mov     r13, [rax+0C8h]
0x18002be2b  mov     rcx, rsi
0x18002be2e  lea     rdx, a1361413111039; "1.3.6.1.4.1.311.10.3.9"
0x18002be35  shl     rcx, 5
0x18002be39  mov     rcx, [rcx+r13]; Str1
0x18002be3d  call    strcmp_0
0x18002be42  test    eax, eax
0x18002be44  jnz     short loc_18002BE6F
0x18002be46  inc     rsi
0x18002be49  cmp     rsi, r14
0x18002be4c  jb      short loc_18002BE2B
0x18002be4e  xor     esi, esi
0x18002be50  mov     rcx, [rbp+5Fh]; this
0x18002be54  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\pkitr"...
0x18002be5b  mov     edi, 800B0110h
0x18002be60  mov     edx, 37Ch; void *
0x18002be65  mov     r9d, edi; char *
0x18002be68  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002be6d  jmp     short loc_18002BE02
0x18002be6f  xorps   xmm0, xmm0
0x18002be72  lea     r8, [rbp+57h+var_88]; struct _SI_CHAIN_INFOW *
0x18002be76  xor     eax, eax
0x18002be78  mov     rdx, rdi; pCertContext
0x18002be7b  mov     rcx, rbx; pvPara
0x18002be7e  mov     [rbp+57h+var_58], rax
0x18002be82  movups  [rbp+57h+var_88], xmm0
0x18002be86  movups  [rbp+57h+var_78], xmm0
0x18002be8a  movups  [rbp+57h+var_68], xmm0
0x18002be8e  call    WTConvertCertCtxToChainInfo
0x18002be93  xor     ebx, ebx
0x18002be95  mov     edi, eax
0x18002be97  test    eax, eax
0x18002be99  jns     short loc_18002BEDC
0x18002be9b  mov     rcx, [rbp+5Fh]; this
0x18002be9f  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\pkitr"...
0x18002bea6  mov     r9d, eax; char *
0x18002bea9  mov     edx, 382h; void *
0x18002beae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002beb3  lea     rcx, [rbp+57h+pCertContext]
0x18002beb7  call    ??1?$unique_storage@U?$resource_policy@PEBU_CERT_CONTEXT@@P6AHPEBU1@@Z$1?CertFreeCertificateContext@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEBU1@PEBU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>(void)
0x18002bebc  mov     rcx, [rbp+57h+Buf1]; hMem
0x18002bec0  mov     [rbp+57h+Buf1], rbx
0x18002bec4  test    rcx, rcx
0x18002bec7  jz      short loc_18002BECF
0x18002bec9  call    cs:__imp_LocalFree
0x18002becf  mov     rcx, [rbp+57h+hMem]
0x18002bed3  mov     [rbp+57h+hMem], rbx
0x18002bed7  jmp     loc_18002BC6E
0x18002bedc  cmp     dword ptr [rbp+57h+var_68+4], 6
0x18002bee0  jz      short loc_18002BF0A
0x18002bee2  mov     rcx, [rbp+5Fh]; this
0x18002bee6  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\pkitr"...
0x18002beed  mov     edi, 800B0109h
0x18002bef2  mov     edx, 384h; void *
0x18002bef7  mov     r9d, edi; char *
0x18002befa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002beff  lea     rcx, [rbp+57h+var_88]
0x18002bf03  call    SIPolicyFreeSIChainInfo
0x18002bf08  jmp     short loc_18002BEB3
0x18002bf0a  mov     r8d, r15d; cbCtlEncoded
0x18002bf0d  mov     rdx, r12; pbCtlEncoded
0x18002bf10  mov     ecx, 10001h; dwMsgAndCertEncodingType
0x18002bf15  call    cs:__imp_CertCreateCTLContext
0x18002bf1b  mov     rcx, [rbp+57h+arg_10]
0x18002bf1f  mov     [rcx], rax
0x18002bf22  test    rax, rax
0x18002bf25  jnz     short loc_18002BF40
0x18002bf27  mov     rcx, [rbp+5Fh]; this
0x18002bf2b  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\pkitr"...
0x18002bf32  mov     edx, 38Ch; void *
0x18002bf37  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002bf3c  mov     edi, eax
0x18002bf3e  jmp     short loc_18002BEFF
0x18002bf40  lea     rcx, [rbp+57h+var_88]
0x18002bf44  call    SIPolicyFreeSIChainInfo
0x18002bf49  lea     rcx, [rbp+57h+pCertContext]
0x18002bf4d  call    ??1?$unique_storage@U?$resource_policy@PEBU_CERT_CONTEXT@@P6AHPEBU1@@Z$1?CertFreeCertificateContext@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEBU1@PEBU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>(void)
0x18002bf52  mov     rcx, [rbp+57h+Buf1]; hMem
0x18002bf56  mov     [rbp+57h+Buf1], rbx
0x18002bf5a  test    rcx, rcx
0x18002bf5d  jz      short loc_18002BF65
0x18002bf5f  call    cs:__imp_LocalFree
0x18002bf65  mov     rcx, [rbp+57h+hMem]; hMem
0x18002bf69  mov     [rbp+57h+hMem], rbx
0x18002bf6d  test    rcx, rcx
0x18002bf70  jz      short loc_18002BF78
0x18002bf72  call    cs:__imp_LocalFree
0x18002bf78  lea     rcx, [rbp+57h+var_90]
0x18002bf7c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?CryptMsgClose@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&CryptMsgClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&CryptMsgClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18002bf81  xor     eax, eax
0x18002bf83  jmp     short loc_18002BFCB
0x18002bf85  mov     rcx, [rbp+5Fh]; this
0x18002bf89  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\pkitr"...
0x18002bf90  mov     edx, 34Dh; void *
0x18002bf95  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002bf9a  mov     edi, eax
0x18002bf9c  lea     rcx, [rbp+57h+var_90]
0x18002bfa0  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?CryptMsgClose@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&CryptMsgClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&CryptMsgClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18002bfa5  mov     eax, edi
0x18002bfa7  jmp     short loc_18002BFCB
0x18002bfa9  mov     rcx, [rbp+5Fh]; this
0x18002bfad  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\pkitr"...
0x18002bfb4  mov     edx, 34Ch; void *
0x18002bfb9  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002bfbe  lea     rcx, [rbp+57h+var_90]
0x18002bfc2  mov     ebx, eax
0x18002bfc4  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?CryptMsgClose@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&CryptMsgClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&CryptMsgClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18002bfc9  mov     eax, ebx
0x18002bfcb  mov     rbx, [rsp+100h+arg_0]
0x18002bfd3  add     rsp, 0D0h
0x18002bfda  pop     r15
0x18002bfdc  pop     r14
0x18002bfde  pop     r13
0x18002bfe0  pop     r12
0x18002bfe2  pop     rdi
0x18002bfe3  pop     rsi
0x18002bfe4  pop     rbp
0x18002bfe5  retn
```
