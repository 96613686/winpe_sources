# VerifyCertificate

- ea: `0x180034e60`
- end: `0x1800350a3`
- name: `VerifyCertificate`
- size: `579`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180034e50`

## callees

- `0x18000af14`
- `0x18000cb6c`
- `0x18000cc9c`
- `0x180029788`
- `0x180034e60`
- `0x180050304`
- `0x1800530e4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034fcb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034fcb`
- `CRYPT32!CertCreateCertificateContext` at `0x180034fbd`
- `CRYPT32!CertCreateCertificateContext` at `0x180034fbd`
- `CRYPT32!CertFreeCertificateContext` at `0x180035051`
- `CRYPT32!CertFreeCertificateContext` at `0x180035051`

## string_xrefs

- `0x180034fe5`: `VerifyCertificate: failed to CertCreateCertificateContext 0x%X`

## pseudocode

```c
__int64 __fastcall VerifyCertificate(__int64 a1, unsigned int *a2, unsigned __int8 *a3, int a4, PCCERT_CONTEXT *a5)
{
  int v9; // eax
  PCCERT_CONTEXT CertificateContext; // rax
  signed int LastError; // eax
  bool v12; // zf
  unsigned int v13; // ebx
  unsigned __int8 *v15; // [rsp+20h] [rbp-C8h]
  int v17; // [rsp+60h] [rbp-88h] BYREF
  unsigned int v18; // [rsp+64h] [rbp-84h] BYREF
  DWORD cbCertEncoded; // [rsp+68h] [rbp-80h] BYREF
  BYTE *pbCertEncoded; // [rsp+70h] [rbp-78h] BYREF
  unsigned __int16 *v21[5]; // [rsp+78h] [rbp-70h] BYREF
  char *v22[9]; // [rsp+A0h] [rbp-48h] BYREF

  v17 = 0;
  v18 = 0;
  v21[0] = 0;
  cbCertEncoded = 0;
  pbCertEncoded = 0;
  CTraceFuncW<unsigned long>::CTraceFuncW<unsigned long>(
    v22,
    (MsaTracingInternal *)"clientcore\\ds\\ext\\live\\identity\\api\\classic\\ppcrl.cpp",
    0xEFDu,
    (char *)&v17,
    "IDCRL::VerifyCertificate",
    L"pCertContext=0x%p, pdwTTL=0x%p, pbPOP=0x%p, cbPOP=%d, ppCACertContext=0x%p",
    a1,
    a2,
    a3,
    a4,
    a5);
  v17 = VerifyInitialized();
  if ( v17 >= 0 )
  {
    if ( a1 && a2 && *a2 )
    {
      v18 = *a2;
      *a2 = 0;
      if ( a5 )
        *a5 = 0;
      v9 = WLIDCVerifyAssertion(
             *(_DWORD *)(a1 + 16),
             *(const unsigned __int8 **)(a1 + 8),
             &v18,
             a4,
             a3,
             v21,
             &cbCertEncoded,
             &pbCertEncoded);
      v17 = v9;
      if ( v9 >= 0 )
      {
        *a2 = v18;
        if ( a5 )
        {
          CertificateContext = CertCreateCertificateContext(0x10001u, pbCertEncoded, cbCertEncoded);
          *a5 = CertificateContext;
          if ( !CertificateContext )
          {
            LastError = GetLastError();
            if ( LastError > 0 )
              LastError = (unsigned __int16)LastError | 0x80070000;
            v17 = LastError;
            LODWORD(v15) = LastError;
            TracePrintW(
              5u,
              "clientcore\\ds\\ext\\live\\identity\\api\\classic\\ppcrl.cpp",
              0xF34u,
              L"VerifyCertificate: failed to CertCreateCertificateContext 0x%X",
              v15);
          }
        }
      }
      else
      {
        LODWORD(v15) = v9;
        TracePrintW(
          5u,
          "clientcore\\ds\\ext\\live\\identity\\api\\classic\\ppcrl.cpp",
          0xF25u,
          L"VerifyCertificate: WLIDVerifyAssertion failed with hr=0x%x",
          v15);
      }
    }
    else
    {
      v17 = -2147024809;
      TracePrintW(
        5u,
        "clientcore\\ds\\ext\\live\\identity\\api\\classic\\ppcrl.cpp",
        0xF0Du,
        L"pCert context passed to VerifyCertificate is NULL, or pdwTTL is NULL or 0.");
    }
  }
  v12 = v17 == 0;
  if ( v17 < 0 )
  {
    if ( a5 )
    {
      CertFreeCertificateContext(*a5);
      *a5 = 0;
    }
    v12 = v17 == 0;
  }
  if ( v12 )
    v17 = 0;
  v13 = v17;
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v22);
  CMIDLStringT<char *,char const *>::~CMIDLStringT<char *,char const *>((void **)&pbCertEncoded);
  CMIDLStringT<char *,char const *>::~CMIDLStringT<char *,char const *>((void **)v21);
  return v13;
}

```

## disassembly

```asm
0x180034e60  mov     r11, rsp
0x180034e63  push    rbx
0x180034e64  push    rsi
0x180034e65  push    rdi
0x180034e66  push    r14
0x180034e68  push    r15
0x180034e6a  sub     rsp, 0C0h
0x180034e71  mov     r14d, r9d
0x180034e74  mov     r15, r8
0x180034e77  mov     rdi, rdx
0x180034e7a  mov     rsi, rcx
0x180034e7d  mov     [rsp+0E8h+var_88], 0
0x180034e85  mov     [rsp+0E8h+var_84], 0
0x180034e8d  mov     qword ptr [r11-70h], 0
0x180034e95  mov     [rsp+0E8h+cbCertEncoded], 0
0x180034e9d  mov     qword ptr [r11-78h], 0
0x180034ea5  mov     rbx, [rsp+0E8h+arg_20]
0x180034ead  mov     [rsp+0E8h+var_98], rbx
0x180034eb2  mov     [rsp+0E8h+var_A0], r9d
0x180034eb7  mov     [rsp+0E8h+var_A8], r8
0x180034ebc  mov     [rsp+0E8h+var_B0], rdx
0x180034ec1  mov     [rsp+0E8h+var_B8], rcx
0x180034ec6  lea     rax, aPcertcontext0x; "pCertContext=0x%p, pdwTTL=0x%p, pbPOP=0"...
0x180034ecd  mov     [rsp+0E8h+var_C0], rax
0x180034ed2  lea     rax, aIdcrlVerifycer; "IDCRL::VerifyCertificate"
0x180034ed9  mov     [rsp+0E8h+var_C8], rax
0x180034ede  lea     r9, [rsp+0E8h+var_88]
0x180034ee3  mov     r8d, 0EFDh
0x180034ee9  lea     rdx, aClientcoreDsEx_1; "clientcore\\ds\\ext\\live\\identity\\ap"...
0x180034ef0  lea     rcx, [r11-48h]
0x180034ef4  call    ??0?$CTraceFuncW@K@@QEAA@PEBDKAEAK0PEBGZZ; CTraceFuncW<ulong>::CTraceFuncW<ulong>(char const *,ulong,ulong &,char const *,ushort const *,...)
0x180034ef9  call    ?VerifyInitialized@@YAJXZ; VerifyInitialized(void)
0x180034efe  mov     [rsp+0E8h+var_88], eax
0x180034f02  test    eax, eax
0x180034f04  js      loc_180035042
0x180034f0a  test    rsi, rsi
0x180034f0d  jz      loc_18003501C
0x180034f13  test    rdi, rdi
0x180034f16  jz      loc_18003501C
0x180034f1c  mov     eax, [rdi]
0x180034f1e  test    eax, eax
0x180034f20  jz      loc_18003501C
0x180034f26  mov     [rsp+0E8h+var_84], eax
0x180034f2a  mov     dword ptr [rdi], 0
0x180034f30  test    rbx, rbx
0x180034f33  jz      short loc_180034F3C
0x180034f35  mov     qword ptr [rbx], 0
0x180034f3c  lea     rax, [rsp+0E8h+pbCertEncoded]
0x180034f41  mov     [rsp+0E8h+var_B0], rax; unsigned __int8 **
0x180034f46  lea     rax, [rsp+0E8h+cbCertEncoded]
0x180034f4b  mov     [rsp+0E8h+var_B8], rax; unsigned int *
0x180034f50  lea     rax, [rsp+0E8h+var_70]
0x180034f55  mov     [rsp+0E8h+var_C0], rax; unsigned __int16 **
0x180034f5a  mov     [rsp+0E8h+var_C8], r15; unsigned __int8 *
0x180034f5f  mov     r9d, r14d; unsigned int
0x180034f62  lea     r8, [rsp+0E8h+var_84]; unsigned int *
0x180034f67  mov     rdx, [rsi+8]; unsigned __int8 *
0x180034f6b  mov     ecx, [rsi+10h]; unsigned int
0x180034f6e  call    ?WLIDCVerifyAssertion@@YAJKPEBEPEAKKPEAEPEAPEAG1PEAPEAE@Z; WLIDCVerifyAssertion(ulong,uchar const *,ulong *,ulong,uchar *,ushort * *,ulong *,uchar * *)
0x180034f73  mov     [rsp+0E8h+var_88], eax
0x180034f77  test    eax, eax
0x180034f79  jns     short loc_180034FA3
0x180034f7b  mov     dword ptr [rsp+0E8h+var_C8], eax
0x180034f7f  lea     r9, aVerifycertific_0; "VerifyCertificate: WLIDVerifyAssertion "...
0x180034f86  mov     r8d, 0F25h; unsigned int
0x180034f8c  lea     rdx, aClientcoreDsEx_1; "clientcore\\ds\\ext\\live\\identity\\ap"...
0x180034f93  mov     ecx, 5; unsigned __int8
0x180034f98  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180034f9d  nop
0x180034f9e  jmp     loc_180035042
0x180034fa3  mov     eax, [rsp+0E8h+var_84]
0x180034fa7  mov     [rdi], eax
0x180034fa9  test    rbx, rbx
0x180034fac  jz      short loc_180035006
0x180034fae  mov     r8d, [rsp+0E8h+cbCertEncoded]; cbCertEncoded
0x180034fb3  mov     rdx, [rsp+0E8h+pbCertEncoded]; pbCertEncoded
0x180034fb8  mov     ecx, 10001h; dwCertEncodingType
0x180034fbd  call    cs:__imp_CertCreateCertificateContext
0x180034fc3  mov     [rbx], rax
0x180034fc6  test    rax, rax
0x180034fc9  jnz     short loc_180035006
0x180034fcb  call    cs:__imp_GetLastError
0x180034fd1  test    eax, eax
0x180034fd3  jle     short loc_180034FDD
0x180034fd5  movzx   eax, ax
0x180034fd8  or      eax, 80070000h
0x180034fdd  mov     [rsp+0E8h+var_88], eax
0x180034fe1  mov     dword ptr [rsp+0E8h+var_C8], eax
0x180034fe5  lea     r9, aVerifycertific_1; "VerifyCertificate: failed to CertCreate"...
0x180034fec  mov     r8d, 0F34h; unsigned int
0x180034ff2  lea     rdx, aClientcoreDsEx_1; "clientcore\\ds\\ext\\live\\identity\\ap"...
0x180034ff9  mov     ecx, 5; unsigned __int8
0x180034ffe  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180035003  nop
0x180035004  jmp     short loc_180035042
0x180035006  jmp     short loc_180035042
0x180035008  mov     rbx, [rsp+0E8h+arg_20]
0x180035010  jmp     short loc_180035049
0x180035012  mov     rbx, [rsp+0E8h+arg_20]
0x18003501a  jmp     short loc_180035042
0x18003501c  mov     [rsp+0E8h+var_88], 80070057h
0x180035024  lea     r9, aPcertContextPa; "pCert context passed to VerifyCertifica"...
0x18003502b  mov     r8d, 0F0Dh; unsigned int
0x180035031  lea     rdx, aClientcoreDsEx_1; "clientcore\\ds\\ext\\live\\identity\\ap"...
0x180035038  mov     ecx, 5; unsigned __int8
0x18003503d  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180035042  cmp     [rsp+0E8h+var_88], 0
0x180035047  jge     short loc_180035063
0x180035049  test    rbx, rbx
0x18003504c  jz      short loc_18003505E
0x18003504e  mov     rcx, [rbx]; pCertContext
0x180035051  call    cs:__imp_CertFreeCertificateContext
0x180035057  mov     qword ptr [rbx], 0
0x18003505e  cmp     [rsp+0E8h+var_88], 0
0x180035063  jnz     short loc_18003506D
0x180035065  mov     [rsp+0E8h+var_88], 0
0x18003506d  mov     ebx, [rsp+0E8h+var_88]
0x180035071  lea     rcx, [rsp+0E8h+var_48]
0x180035079  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x18003507e  lea     rcx, [rsp+0E8h+pbCertEncoded]
0x180035083  call    ??1?$CMIDLStringT@PEADPEBD@@QEAA@XZ; CMIDLStringT<char *,char const *>::~CMIDLStringT<char *,char const *>(void)
0x180035088  lea     rcx, [rsp+0E8h+var_70]
0x18003508d  call    ??1?$CMIDLStringT@PEADPEBD@@QEAA@XZ; CMIDLStringT<char *,char const *>::~CMIDLStringT<char *,char const *>(void)
0x180035092  mov     eax, ebx
0x180035094  add     rsp, 0C0h
0x18003509b  pop     r15
0x18003509d  pop     r14
0x18003509f  pop     rdi
0x1800350a0  pop     rsi
0x1800350a1  pop     rbx
0x1800350a2  retn
```
