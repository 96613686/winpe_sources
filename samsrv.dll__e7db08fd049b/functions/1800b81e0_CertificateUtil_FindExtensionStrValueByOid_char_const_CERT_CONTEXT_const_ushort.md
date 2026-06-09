# CertificateUtil::FindExtensionStrValueByOid(char const *,_CERT_CONTEXT const *,ushort * *)

- ea: `0x1800b81e0`
- end: `0x1800b843e`
- name: `?FindExtensionStrValueByOid@CertificateUtil@@SAJPEBDPEBU_CERT_CONTEXT@@PEAPEAG@Z`
- size: `606`
- prototype: `__int64 __fastcall(const char *, const struct _CERT_CONTEXT *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, loader_planting`

## callers

- `0x1800b78b0`

## callees

- `0x1800269d4`
- `0x180026b54`
- `0x18002d5e4`
- `0x18002d720`
- `0x18002f1c8`
- `0x1800b7fb0`
- `0x1800b81e0`
- `0x1800b8a58`
- `0x1800b8b08`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b8312`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b83d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b8312`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b83d0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b8422`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b8422`
- `CRYPT32!CryptBinaryToStringW` at `0x1800b8342`
- `CRYPT32!CryptBinaryToStringW` at `0x1800b83c6`
- `CRYPT32!CryptBinaryToStringW` at `0x1800b8342`
- `CRYPT32!CryptBinaryToStringW` at `0x1800b83c6`
- `CRYPT32!CryptDecodeObjectEx` at `0x1800b8308`
- `CRYPT32!CryptDecodeObjectEx` at `0x1800b8308`

## string_xrefs

- `0x1800b8217`: `CertificateUtil::FindExtensionStrValueByOid`
- `0x1800b8252`: `CertificateUtil::FindExtensionStrValueByOid`
- `0x1800b8282`: `CertificateUtil::FindExtensionStrValueByOid`
- `0x1800b82bd`: `CertificateUtil::FindExtensionStrValueByOid`
- `0x1800b837f`: `CertificateUtil::FindExtensionStrValueByOid`
- `0x1800b83df`: `CertificateUtil::FindExtensionStrValueByOid`
- `0x1800b82c4`: `%s: Extension was not found in the certificate. OID: %hs.`

## pseudocode

```c
__int64 __fastcall CertificateUtil::FindExtensionStrValueByOid(
        const char *a1,
        const struct _CERT_CONTEXT *a2,
        unsigned __int16 **a3)
{
  unsigned __int16 *v3; // r14
  unsigned int v7; // edi
  const unsigned __int16 *v8; // rdx
  PCERT_EXTENSION ExtensionByOid; // rax
  DWORD LastError; // eax
  const unsigned __int16 *v11; // rcx
  unsigned __int64 v12; // rax
  unsigned __int16 *v13; // rax
  int v14; // esi
  __int64 v15; // rdx
  HLOCAL hMem[2]; // [rsp+40h] [rbp-10h] BYREF
  DWORD pcchString; // [rsp+80h] [rbp+30h] BYREF
  DWORD pcbStructInfo; // [rsp+98h] [rbp+48h] BYREF

  v3 = 0;
  hMem[0] = 0;
  pcbStructInfo = 0;
  pcchString = 0;
  if ( !a1 )
  {
    v7 = -2147024809;
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"CertificateUtil::FindExtensionStrValueByOid", L"pcszOid");
    v8 = L"pcszOid";
LABEL_3:
    Logger::WriteNullOrEmptyParameterFailureEvent(L"CertificateUtil::FindExtensionStrValueByOid", v8);
    goto LABEL_24;
  }
  if ( !a3 )
  {
    v7 = -2147024809;
    Logger::TraceError(
      L"%s: \"%s\" should not be null.",
      L"CertificateUtil::FindExtensionStrValueByOid",
      L"ppszOutBuffer");
    v8 = L"ppszOutBuffer";
    goto LABEL_3;
  }
  if ( !a2 )
  {
    v7 = -2147024809;
    Logger::TraceError(
      L"%s: \"%s\" should not be null.",
      L"CertificateUtil::FindExtensionStrValueByOid",
      &stru_1800D9558);
    v8 = (const unsigned __int16 *)&stru_1800D9558;
    goto LABEL_3;
  }
  *a3 = 0;
  ExtensionByOid = CertificateUtil::FindExtensionByOid(a1, a2);
  if ( ExtensionByOid )
  {
    v7 = 0;
    if ( CryptDecodeObjectEx(
           a2->dwCertEncodingType,
           (LPCSTR)0x19,
           ExtensionByOid->Value.pbData,
           ExtensionByOid->Value.cbData,
           0x8000u,
           0,
           hMem,
           &pcbStructInfo) )
    {
      if ( CryptBinaryToStringW(*((const BYTE **)hMem[0] + 1), *(_DWORD *)hMem[0], 0x40000002u, 0, &pcchString) )
      {
        v12 = 2LL * (pcchString + 1);
        if ( !is_mul_ok(pcchString + 1, 2u) )
          v12 = -1;
        v13 = (unsigned __int16 *)operator new[](v12, (const struct std::nothrow_t *)&std::nothrow);
        v3 = v13;
        if ( !v13 )
        {
          v7 = -2147024882;
          Logger::TraceCritical(
            L"%s: Out of memory. Allocation failed.",
            L"CertificateUtil::FindExtensionStrValueByOid");
          goto LABEL_24;
        }
        memset_0(v13, 0, 2LL * (pcchString + 1));
        if ( CryptBinaryToStringW(*((const BYTE **)hMem[0] + 1), *(_DWORD *)hMem[0], 0x40000002u, v3, &pcchString) )
        {
          v15 = pcchString;
          *a3 = v3;
          v3[v15] = 0;
          v3 = 0;
          goto LABEL_24;
        }
      }
      LastError = GetLastError();
      v11 = L"%s: CryptBinaryToStringW with error code: 0x%08x";
    }
    else
    {
      LastError = GetLastError();
      v11 = L"%s: CryptDecodeObjectEx with error code: 0x%08x";
    }
    v14 = LastError;
    Logger::TraceError(v11, L"CertificateUtil::FindExtensionStrValueByOid", LastError);
    if ( v14 )
    {
      if ( v14 > 0 )
        v7 = (unsigned __int16)v14 | 0x80070000;
      else
        v7 = v14;
    }
  }
  else
  {
    Logger::TraceVerbose(
      L"%s: Extension was not found in the certificate. OID: %hs.",
      L"CertificateUtil::FindExtensionStrValueByOid",
      a1);
    v7 = -2146885628;
  }
LABEL_24:
  operator delete(v3);
  LocalFree(hMem[0]);
  return v7;
}

```

## disassembly

```asm
0x1800b81e0  mov     [rsp-28h+arg_8], rbx
0x1800b81e5  push    rbp
0x1800b81e6  push    rsi
0x1800b81e7  push    rdi
0x1800b81e8  push    r14
0x1800b81ea  push    r15
0x1800b81ec  mov     rbp, rsp
0x1800b81ef  sub     rsp, 50h
0x1800b81f3  xor     r14d, r14d
0x1800b81f6  mov     [rbp+hMem], 0
0x1800b81fe  mov     [rbp+arg_18], 0
0x1800b8205  mov     r15, r8
0x1800b8208  mov     [rbp+pcchString], r14d
0x1800b820c  mov     rsi, rdx
0x1800b820f  mov     rbx, rcx
0x1800b8212  test    rcx, rcx
0x1800b8215  jnz     short loc_1800B824D
0x1800b8217  lea     rbx, aCertificateuti_5; "CertificateUtil::FindExtensionStrValueB"...
0x1800b821e  mov     edi, 80070057h
0x1800b8223  mov     rdx, rbx
0x1800b8226  lea     r8, aPcszoid; "pcszOid"
0x1800b822d  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x1800b8234  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800b8239  lea     rdx, aPcszoid; "pcszOid"
0x1800b8240  mov     rcx, rbx; unsigned __int16 *
0x1800b8243  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x1800b8248  jmp     loc_1800B8416
0x1800b824d  test    r15, r15
0x1800b8250  jnz     short loc_1800B827D
0x1800b8252  lea     rbx, aCertificateuti_5; "CertificateUtil::FindExtensionStrValueB"...
0x1800b8259  mov     edi, 80070057h
0x1800b825e  mov     rdx, rbx
0x1800b8261  lea     r8, aPpszoutbuffer; "ppszOutBuffer"
0x1800b8268  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x1800b826f  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800b8274  lea     rdx, aPpszoutbuffer; "ppszOutBuffer"
0x1800b827b  jmp     short loc_1800B8240
0x1800b827d  test    rsi, rsi
0x1800b8280  jnz     short loc_1800B82AD
0x1800b8282  lea     rbx, aCertificateuti_5; "CertificateUtil::FindExtensionStrValueB"...
0x1800b8289  mov     edi, 80070057h
0x1800b828e  mov     rdx, rbx
0x1800b8291  lea     r8, stru_1800D9558
0x1800b8298  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x1800b829f  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800b82a4  lea     rdx, stru_1800D9558; struct _CERT_CONTEXT *
0x1800b82ab  jmp     short loc_1800B8240
0x1800b82ad  mov     [r8], r14
0x1800b82b0  call    ?FindExtensionByOid@CertificateUtil@@SAPEAU_CERT_EXTENSION@@PEBDPEBU_CERT_CONTEXT@@@Z; CertificateUtil::FindExtensionByOid(char const *,_CERT_CONTEXT const *)
0x1800b82b5  test    rax, rax
0x1800b82b8  jnz     short loc_1800B82DA
0x1800b82ba  mov     r8, rbx
0x1800b82bd  lea     rdx, aCertificateuti_5; "CertificateUtil::FindExtensionStrValueB"...
0x1800b82c4  lea     rcx, aSExtensionWasN; "%s: Extension was not found in the cert"...
0x1800b82cb  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x1800b82d0  mov     edi, 80092004h
0x1800b82d5  jmp     loc_1800B8416
0x1800b82da  mov     r9d, [rax+10h]; cbEncoded
0x1800b82de  lea     rcx, [rbp+arg_18]
0x1800b82e2  mov     r8, [rax+18h]; pbEncoded
0x1800b82e6  xor     edi, edi
0x1800b82e8  mov     [rsp+50h+pcbStructInfo], rcx; pcbStructInfo
0x1800b82ed  lea     rcx, [rbp+hMem]
0x1800b82f1  mov     [rsp+50h+pvStructInfo], rcx; pvStructInfo
0x1800b82f6  mov     ecx, [rsi]; dwCertEncodingType
0x1800b82f8  mov     [rsp+50h+pDecodePara], rdi; pDecodePara
0x1800b82fd  lea     edx, [rdi+19h]; lpszStructType
0x1800b8300  mov     [rsp+50h+dwFlags], 8000h; dwFlags
0x1800b8308  call    cs:__imp_CryptDecodeObjectEx
0x1800b830e  test    eax, eax
0x1800b8310  jnz     short loc_1800B8324
0x1800b8312  call    cs:__imp_GetLastError
0x1800b8318  lea     rcx, aSCryptdecodeob; "%s: CryptDecodeObjectEx with error code"...
0x1800b831f  jmp     loc_1800B83DD
0x1800b8324  mov     rcx, [rbp+hMem]
0x1800b8328  lea     rax, [rbp+pcchString]
0x1800b832c  mov     ebx, 40000002h
0x1800b8331  mov     qword ptr [rsp+50h+dwFlags], rax; pcchString
0x1800b8336  xor     r9d, r9d; pszString
0x1800b8339  mov     r8d, ebx; dwFlags
0x1800b833c  mov     edx, [rcx]; cbBinary
0x1800b833e  mov     rcx, [rcx+8]; pbBinary
0x1800b8342  call    cs:__imp_CryptBinaryToStringW
0x1800b8348  test    eax, eax
0x1800b834a  jz      loc_1800B83D0
0x1800b8350  mov     ecx, [rbp+pcchString]
0x1800b8353  mov     eax, 2
0x1800b8358  inc     ecx
0x1800b835a  mul     rcx
0x1800b835d  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800b8364  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800b836b  cmovb   rax, rcx
0x1800b836f  mov     rcx, rax; unsigned __int64
0x1800b8372  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800b8377  mov     r14, rax
0x1800b837a  test    rax, rax
0x1800b837d  jnz     short loc_1800B8399
0x1800b837f  lea     rdx, aCertificateuti_5; "CertificateUtil::FindExtensionStrValueB"...
0x1800b8386  mov     edi, 8007000Eh
0x1800b838b  lea     rcx, aSOutOfMemoryAl; "%s: Out of memory. Allocation failed."
0x1800b8392  call    ?TraceCritical@Logger@@SAJPEBGZZ; Logger::TraceCritical(ushort const *,...)
0x1800b8397  jmp     short loc_1800B8416
0x1800b8399  mov     r8d, [rbp+pcchString]
0x1800b839d  xor     edx, edx; Val
0x1800b839f  inc     r8d
0x1800b83a2  mov     rcx, r14; void *
0x1800b83a5  add     r8, r8; Size
0x1800b83a8  call    memset_0
0x1800b83ad  mov     rcx, [rbp+hMem]
0x1800b83b1  lea     rax, [rbp+pcchString]
0x1800b83b5  mov     r9, r14; pszString
0x1800b83b8  mov     qword ptr [rsp+50h+dwFlags], rax; pcchString
0x1800b83bd  mov     r8d, ebx; dwFlags
0x1800b83c0  mov     edx, [rcx]; cbBinary
0x1800b83c2  mov     rcx, [rcx+8]; pbBinary
0x1800b83c6  call    cs:__imp_CryptBinaryToStringW
0x1800b83cc  test    eax, eax
0x1800b83ce  jnz     short loc_1800B8406
0x1800b83d0  call    cs:__imp_GetLastError
0x1800b83d6  lea     rcx, aSCryptbinaryto; "%s: CryptBinaryToStringW with error cod"...
0x1800b83dd  mov     esi, eax
0x1800b83df  lea     rbx, aCertificateuti_5; "CertificateUtil::FindExtensionStrValueB"...
0x1800b83e6  mov     r8d, eax
0x1800b83e9  mov     rdx, rbx
0x1800b83ec  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800b83f1  test    esi, esi
0x1800b83f3  jz      short loc_1800B8416
0x1800b83f5  jg      short loc_1800B83FB
0x1800b83f7  mov     edi, esi
0x1800b83f9  jmp     short loc_1800B8416
0x1800b83fb  movzx   edi, si
0x1800b83fe  or      edi, 80070000h
0x1800b8404  jmp     short loc_1800B8416
0x1800b8406  mov     edx, [rbp+pcchString]
0x1800b8409  xor     ecx, ecx
0x1800b840b  mov     [r15], r14
0x1800b840e  mov     [r14+rdx*2], cx
0x1800b8413  xor     r14d, r14d
0x1800b8416  mov     rcx, r14; Block
0x1800b8419  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800b841e  mov     rcx, [rbp+hMem]; hMem
0x1800b8422  call    cs:__imp_LocalFree
0x1800b8428  mov     rbx, [rsp+50h+arg_8]
0x1800b8430  mov     eax, edi
0x1800b8432  add     rsp, 50h
0x1800b8436  pop     r15
0x1800b8438  pop     r14
0x1800b843a  pop     rdi
0x1800b843b  pop     rsi
0x1800b843c  pop     rbp
0x1800b843d  retn
```
