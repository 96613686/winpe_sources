# FindSignerInAllowCTL

- ea: `0x18002b648`
- end: `0x18002b858`
- name: `FindSignerInAllowCTL`
- size: `528`
- prototype: `__int64 __fastcall(PCCTL_CONTEXT pCtlContext, PCCERT_CONTEXT pCertContext)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180041fe0`

## callees

- `0x18002ac3c`
- `0x18002b648`
- `0x18002c090`
- `0x18002c1b4`
- `0x1800404f0`
- `0x18004de46`
- `0x18004de76`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002b75f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002b83c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002b75f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002b83c`
- `CRYPT32!CertFindSubjectInCTL` at `0x18002b6ed`
- `CRYPT32!CertFindSubjectInCTL` at `0x18002b6ed`
- `CRYPT32!CryptDecodeObjectEx` at `0x18002b7d1`
- `CRYPT32!CryptDecodeObjectEx` at `0x18002b7d1`
- `CRYPT32!CertFindAttribute` at `0x18002b778`
- `CRYPT32!CertFindAttribute` at `0x18002b778`

## string_xrefs

- `0x18002b69f`: `onecore\ds\security\cryptoapi\pkitrust\softpub\configciprov.cpp`
- `0x18002b73f`: `onecore\ds\security\cryptoapi\pkitrust\softpub\configciprov.cpp`
- `0x18002b7df`: `onecore\ds\security\cryptoapi\pkitrust\softpub\configciprov.cpp`

## pseudocode

```c
__int64 __fastcall FindSignerInAllowCTL(PCCTL_CONTEXT pCtlContext, CERT_CONTEXT *pCertContext, _BYTE *a3)
{
  PCTL_INFO pCtlInfo; // rsi
  unsigned __int64 cUsageIdentifier; // rdi
  LPSTR *rgpszUsageIdentifier; // r13
  __int64 v9; // rbx
  unsigned int CertCtxProperty; // ebx
  PCTL_ENTRY SubjectInCTL; // rdi
  __int64 v13; // rdx
  HLOCAL v14; // rcx
  PCRYPT_ATTRIBUTE Attribute; // rax
  const char *v16; // r9
  unsigned __int64 cCTLEntry; // rsi
  unsigned __int64 v18; // rdi
  HLOCAL v19; // rbx
  int v20; // r15d
  DWORD dwFlags; // [rsp+20h] [rbp-50h]
  DWORD dwFlagsa; // [rsp+20h] [rbp-50h]
  void *Buf1[2]; // [rsp+40h] [rbp-30h] BYREF
  _QWORD v24[2]; // [rsp+50h] [rbp-20h] BYREF
  char v25; // [rsp+60h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]
  DWORD pcbStructInfo; // [rsp+C0h] [rbp+50h] BYREF
  HLOCAL hMem; // [rsp+C8h] [rbp+58h] BYREF

  pCtlInfo = pCtlContext->pCtlInfo;
  *a3 = 0;
  cUsageIdentifier = pCtlInfo->SubjectUsage.cUsageIdentifier;
  if ( !pCtlInfo->SubjectUsage.cUsageIdentifier )
  {
LABEL_5:
    CertCtxProperty = -2146762480;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3FE,
      (unsigned int)"onecore\\ds\\security\\cryptoapi\\pkitrust\\softpub\\configciprov.cpp",
      (const char *)0x800B0110LL,
      dwFlags);
    return CertCtxProperty;
  }
  rgpszUsageIdentifier = pCtlInfo->SubjectUsage.rgpszUsageIdentifier;
  v9 = 0;
  while ( strcmp_0(rgpszUsageIdentifier[v9], "1.3.6.1.4.1.311.10.3.9") )
  {
    if ( ++v9 >= cUsageIdentifier )
      goto LABEL_5;
  }
  SubjectInCTL = CertFindSubjectInCTL(0x10001u, 2u, pCertContext, pCtlContext, 0);
  if ( SubjectInCTL )
  {
    v24[0] = &hMem;
    hMem = 0;
    v24[1] = 0;
    v25 = 1;
    CertCtxProperty = GetCertCtxProperty(pCertContext);
    wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(v24);
    if ( (CertCtxProperty & 0x80000000) != 0 )
    {
      v13 = 1044;
LABEL_10:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v13,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\pkitrust\\softpub\\configciprov.cpp",
        (const char *)CertCtxProperty,
        dwFlagsa);
      goto LABEL_11;
    }
    Attribute = CertFindAttribute("1.3.6.1.4.1.311.10.11.98", SubjectInCTL->cAttribute, SubjectInCTL->rgAttribute);
    if ( !Attribute || Attribute->cValue != 1 )
    {
      CertCtxProperty = -2147418113;
      v13 = 1050;
      goto LABEL_10;
    }
    pcbStructInfo = 16;
    *(_OWORD *)Buf1 = 0;
    if ( !CryptDecodeObjectEx(
            0x10001u,
            (LPCSTR)0x19,
            Attribute->rgValue->pbData,
            Attribute->rgValue->cbData,
            1u,
            0,
            Buf1,
            &pcbStructInfo) )
    {
      CertCtxProperty = wil::details::in1diag3::Return_GetLastError(
                          retaddr,
                          (void *)0x426,
                          (unsigned int)"onecore\\ds\\security\\cryptoapi\\pkitrust\\softpub\\configciprov.cpp",
                          v16);
LABEL_11:
      v14 = hMem;
      hMem = 0;
      if ( v14 )
        LocalFree(v14);
      return CertCtxProperty;
    }
    cCTLEntry = pCtlInfo->cCTLEntry;
    v18 = 0;
    v19 = hMem;
    v20 = (int)Buf1[0];
    while ( v18 < cCTLEntry )
    {
      if ( !v20 && !memcmp_0(Buf1[1], v19, 0) )
      {
        *a3 = 1;
        break;
      }
      *a3 = 0;
      ++v18;
    }
    hMem = 0;
    if ( v19 )
      LocalFree(v19);
  }
  return 0;
}

```

## disassembly

```asm
0x18002b648  mov     [rsp-38h+arg_8], rbx
0x18002b64d  push    rbp
0x18002b64e  push    rsi
0x18002b64f  push    rdi
0x18002b650  push    r12
0x18002b652  push    r13
0x18002b654  push    r14
0x18002b656  push    r15
0x18002b658  mov     rbp, rsp
0x18002b65b  sub     rsp, 70h
0x18002b65f  mov     rsi, [rcx+18h]
0x18002b663  mov     r14, r8
0x18002b666  mov     r12, rdx
0x18002b669  mov     byte ptr [r8], 0
0x18002b66d  mov     r15, rcx
0x18002b670  mov     edi, [rsi+8]
0x18002b673  test    rdi, rdi
0x18002b676  jz      short loc_18002B69B
0x18002b678  mov     r13, [rsi+10h]
0x18002b67c  xor     ebx, ebx
0x18002b67e  mov     rcx, [r13+rbx*8+0]; Str1
0x18002b683  lea     rdx, a1361413111039; "1.3.6.1.4.1.311.10.3.9"
0x18002b68a  call    strcmp_0
0x18002b68f  test    eax, eax
0x18002b691  jz      short loc_18002B6D2
0x18002b693  inc     rbx
0x18002b696  cmp     rbx, rdi
0x18002b699  jb      short loc_18002B67E
0x18002b69b  mov     rcx, [rbp+38h]; this
0x18002b69f  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\pkitr"...
0x18002b6a6  mov     ebx, 800B0110h
0x18002b6ab  mov     edx, 3FEh; void *
0x18002b6b0  mov     r9d, ebx; char *
0x18002b6b3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002b6b8  mov     eax, ebx
0x18002b6ba  mov     rbx, [rsp+70h+arg_8]
0x18002b6c2  add     rsp, 70h
0x18002b6c6  pop     r15
0x18002b6c8  pop     r14
0x18002b6ca  pop     r13
0x18002b6cc  pop     r12
0x18002b6ce  pop     rdi
0x18002b6cf  pop     rsi
0x18002b6d0  pop     rbp
0x18002b6d1  retn
0x18002b6d2  xor     r13d, r13d
0x18002b6d5  mov     r9, r15; pCtlContext
0x18002b6d8  mov     r15d, 10001h
0x18002b6de  mov     [rsp+70h+dwFlags], r13d; int
0x18002b6e3  mov     r8, r12; pvSubject
0x18002b6e6  mov     ecx, r15d; dwEncodingType
0x18002b6e9  lea     edx, [r13+2]; dwSubjectType
0x18002b6ed  call    cs:__imp_CertFindSubjectInCTL
0x18002b6f3  mov     rdi, rax
0x18002b6f6  test    rax, rax
0x18002b6f9  jz      loc_18002B842
0x18002b6ff  lea     rax, [rbp+hMem]
0x18002b703  mov     dword ptr [rbp+Size], r13d
0x18002b707  lea     r9, [rbp+Size]
0x18002b70b  mov     [rbp+var_20], rax
0x18002b70f  lea     r8, [rbp+var_18]
0x18002b713  mov     [rbp+hMem], r13
0x18002b717  mov     rcx, r12; pCertContext
0x18002b71a  mov     [rbp+var_18], r13
0x18002b71e  mov     [rbp+var_10], 1
0x18002b722  call    GetCertCtxProperty
0x18002b727  lea     rcx, [rbp+var_20]
0x18002b72b  mov     ebx, eax
0x18002b72d  call    ??1?$out_param_t@V?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x18002b732  test    ebx, ebx
0x18002b734  jns     short loc_18002B76A
0x18002b736  mov     edx, 414h; void *
0x18002b73b  mov     rcx, [rbp+38h]; this
0x18002b73f  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\pkitr"...
0x18002b746  mov     r9d, ebx; char *
0x18002b749  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002b74e  mov     rcx, [rbp+hMem]; hMem
0x18002b752  mov     [rbp+hMem], r13
0x18002b756  test    rcx, rcx
0x18002b759  jz      loc_18002B6B8
0x18002b75f  call    cs:__imp_LocalFree
0x18002b765  jmp     loc_18002B6B8
0x18002b76a  mov     r8, [rdi+18h]; rgAttr
0x18002b76e  lea     rcx, a13614131110119; "1.3.6.1.4.1.311.10.11.98"
0x18002b775  mov     edx, [rdi+10h]; cAttr
0x18002b778  call    cs:__imp_CertFindAttribute
0x18002b77e  test    rax, rax
0x18002b781  jz      loc_18002B849
0x18002b787  cmp     dword ptr [rax+8], 1
0x18002b78b  jnz     loc_18002B849
0x18002b791  mov     [rbp+arg_10], 10h
0x18002b798  xorps   xmm0, xmm0
0x18002b79b  movups  xmmword ptr [rbp+Buf1], xmm0
0x18002b79f  mov     r8, [rax+10h]
0x18002b7a3  mov     edx, 19h; lpszStructType
0x18002b7a8  lea     rax, [rbp+arg_10]
0x18002b7ac  mov     ecx, r15d; dwCertEncodingType
0x18002b7af  mov     [rsp+70h+pcbStructInfo], rax; pcbStructInfo
0x18002b7b4  lea     rax, [rbp+Buf1]
0x18002b7b8  mov     [rsp+70h+pvStructInfo], rax; pvStructInfo
0x18002b7bd  mov     r9d, [r8]; cbEncoded
0x18002b7c0  mov     r8, [r8+8]; pbEncoded
0x18002b7c4  mov     [rsp+70h+pDecodePara], r13; pDecodePara
0x18002b7c9  mov     [rsp+70h+dwFlags], 1; dwFlags
0x18002b7d1  call    cs:__imp_CryptDecodeObjectEx
0x18002b7d7  test    eax, eax
0x18002b7d9  jnz     short loc_18002B7F7
0x18002b7db  mov     rcx, [rbp+38h]; this
0x18002b7df  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\pkitr"...
0x18002b7e6  mov     edx, 426h; void *
0x18002b7eb  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002b7f0  mov     ebx, eax
0x18002b7f2  jmp     loc_18002B74E
0x18002b7f7  mov     esi, [rsi+60h]
0x18002b7fa  mov     rdi, r13
0x18002b7fd  mov     rbx, [rbp+hMem]
0x18002b801  mov     r15d, dword ptr [rbp+Buf1]
0x18002b805  cmp     rdi, rsi
0x18002b808  jnb     short loc_18002B830
0x18002b80a  cmp     r15d, dword ptr [rbp+Size]
0x18002b80e  jnz     short loc_18002B824
0x18002b810  mov     r8d, dword ptr [rbp+Size]; Size
0x18002b814  mov     rdx, rbx; Buf2
0x18002b817  mov     rcx, [rbp+Buf1+8]; Buf1
0x18002b81b  call    memcmp_0
0x18002b820  test    eax, eax
0x18002b822  jz      short loc_18002B82C
0x18002b824  mov     [r14], r13b
0x18002b827  inc     rdi
0x18002b82a  jmp     short loc_18002B805
0x18002b82c  mov     byte ptr [r14], 1
0x18002b830  mov     [rbp+hMem], r13
0x18002b834  test    rbx, rbx
0x18002b837  jz      short loc_18002B842
0x18002b839  mov     rcx, rbx; hMem
0x18002b83c  call    cs:__imp_LocalFree
0x18002b842  xor     eax, eax
0x18002b844  jmp     loc_18002B6BA
0x18002b849  mov     ebx, 8000FFFFh
0x18002b84e  mov     edx, 41Ah
0x18002b853  jmp     loc_18002B73B
```
