# GetCACertFromSvc(_CERT_CONTEXT const *,_CERT_CONTEXT const * *)

- ea: `0x180025ec0`
- end: `0x180025fb5`
- name: `?GetCACertFromSvc@@YAJPEBU_CERT_CONTEXT@@PEAPEBU1@@Z`
- size: `245`
- prototype: `__int64 __fastcall(const struct _CERT_CONTEXT *, const struct _CERT_CONTEXT **)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18002cf70`

## callees

- `0x18000af14`
- `0x180025ec0`
- `0x180029788`
- `0x180050304`
- `0x1800530e4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025f5a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025f5a`
- `CRYPT32!CertCreateCertificateContext` at `0x180025f4c`
- `CRYPT32!CertCreateCertificateContext` at `0x180025f4c`

## string_xrefs

- `0x180025f6f`: `GetCACertFromSvc: failed to CertCreateCertificateContext 0x%X`

## pseudocode

```c
__int64 __fastcall GetCACertFromSvc(const struct _CERT_CONTEXT *a1, const struct _CERT_CONTEXT **a2)
{
  __int64 v3; // rcx
  int v4; // ebx
  const struct _CERT_CONTEXT *CertificateContext; // rax
  signed int LastError; // eax
  unsigned __int8 *v8; // [rsp+20h] [rbp-30h]
  BYTE *pbCertEncoded; // [rsp+40h] [rbp-10h] BYREF
  unsigned __int16 *v10; // [rsp+48h] [rbp-8h] BYREF
  DWORD cbCertEncoded; // [rsp+70h] [rbp+20h] BYREF
  unsigned int v12; // [rsp+78h] [rbp+28h] BYREF

  v12 = 1;
  v10 = 0;
  cbCertEncoded = 0;
  pbCertEncoded = 0;
  v4 = VerifyInitialized();
  if ( v4 >= 0 )
  {
    v4 = WLIDCVerifyAssertion(
           *(_DWORD *)(v3 + 16),
           *(const unsigned __int8 **)(v3 + 8),
           &v12,
           0,
           0,
           &v10,
           &cbCertEncoded,
           &pbCertEncoded);
    if ( v4 >= 0 )
    {
      CertificateContext = CertCreateCertificateContext(0x10001u, pbCertEncoded, cbCertEncoded);
      *a2 = CertificateContext;
      if ( !CertificateContext )
      {
        LastError = GetLastError();
        v4 = LastError;
        if ( LastError > 0 )
          v4 = (unsigned __int16)LastError | 0x80070000;
        LODWORD(v8) = v4;
        TracePrintW(
          5u,
          "clientcore\\ds\\ext\\live\\identity\\api\\classic\\ppcrl.cpp",
          0x1921u,
          L"GetCACertFromSvc: failed to CertCreateCertificateContext 0x%X",
          v8);
      }
    }
  }
  CMIDLStringT<char *,char const *>::~CMIDLStringT<char *,char const *>((void **)&pbCertEncoded);
  CMIDLStringT<char *,char const *>::~CMIDLStringT<char *,char const *>((void **)&v10);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180025ec0  mov     [rsp-8+arg_0], rbx
0x180025ec5  mov     [rsp-8+arg_8], rdi
0x180025eca  push    rbp
0x180025ecb  mov     rbp, rsp
0x180025ece  sub     rsp, 50h
0x180025ed2  mov     rdi, rdx
0x180025ed5  mov     [rbp+arg_18], 1
0x180025edc  mov     [rbp+var_8], 0
0x180025ee4  mov     [rbp+cbCertEncoded], 0
0x180025eeb  mov     [rbp+pbCertEncoded], 0
0x180025ef3  call    ?VerifyInitialized@@YAJXZ; VerifyInitialized(void)
0x180025ef8  mov     ebx, eax
0x180025efa  test    eax, eax
0x180025efc  js      loc_180025F91
0x180025f02  mov     rdx, [rcx+8]; unsigned __int8 *
0x180025f06  lea     rax, [rbp+pbCertEncoded]
0x180025f0a  mov     ecx, [rcx+10h]; unsigned int
0x180025f0d  lea     r8, [rbp+arg_18]; unsigned int *
0x180025f11  mov     [rsp+50h+var_18], rax; unsigned __int8 **
0x180025f16  xor     r9d, r9d; unsigned int
0x180025f19  lea     rax, [rbp+cbCertEncoded]
0x180025f1d  mov     [rsp+50h+var_20], rax; unsigned int *
0x180025f22  lea     rax, [rbp+var_8]
0x180025f26  mov     [rsp+50h+var_28], rax; unsigned __int16 **
0x180025f2b  mov     [rsp+50h+var_30], 0; unsigned __int8 *
0x180025f34  call    ?WLIDCVerifyAssertion@@YAJKPEBEPEAKKPEAEPEAPEAG1PEAPEAE@Z; WLIDCVerifyAssertion(ulong,uchar const *,ulong *,ulong,uchar *,ushort * *,ulong *,uchar * *)
0x180025f39  mov     ebx, eax
0x180025f3b  test    eax, eax
0x180025f3d  js      short loc_180025F91
0x180025f3f  mov     r8d, [rbp+cbCertEncoded]; cbCertEncoded
0x180025f43  mov     ecx, 10001h; dwCertEncodingType
0x180025f48  mov     rdx, [rbp+pbCertEncoded]; pbCertEncoded
0x180025f4c  call    cs:__imp_CertCreateCertificateContext
0x180025f52  mov     [rdi], rax
0x180025f55  test    rax, rax
0x180025f58  jnz     short loc_180025F91
0x180025f5a  call    cs:__imp_GetLastError
0x180025f60  mov     ebx, eax
0x180025f62  test    eax, eax
0x180025f64  jle     short loc_180025F6F
0x180025f66  movzx   ebx, ax
0x180025f69  or      ebx, 80070000h
0x180025f6f  lea     r9, aGetcacertfroms; "GetCACertFromSvc: failed to CertCreateC"...
0x180025f76  mov     dword ptr [rsp+50h+var_30], ebx
0x180025f7a  mov     r8d, 1921h; unsigned int
0x180025f80  lea     rdx, aClientcoreDsEx_1; "clientcore\\ds\\ext\\live\\identity\\ap"...
0x180025f87  mov     ecx, 5; unsigned __int8
0x180025f8c  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180025f91  lea     rcx, [rbp+pbCertEncoded]
0x180025f95  call    ??1?$CMIDLStringT@PEADPEBD@@QEAA@XZ; CMIDLStringT<char *,char const *>::~CMIDLStringT<char *,char const *>(void)
0x180025f9a  lea     rcx, [rbp+var_8]
0x180025f9e  call    ??1?$CMIDLStringT@PEADPEBD@@QEAA@XZ; CMIDLStringT<char *,char const *>::~CMIDLStringT<char *,char const *>(void)
0x180025fa3  mov     rdi, [rsp+50h+arg_8]
0x180025fa8  mov     eax, ebx
0x180025faa  mov     rbx, [rsp+50h+arg_0]
0x180025faf  add     rsp, 50h
0x180025fb3  pop     rbp
0x180025fb4  retn
```
