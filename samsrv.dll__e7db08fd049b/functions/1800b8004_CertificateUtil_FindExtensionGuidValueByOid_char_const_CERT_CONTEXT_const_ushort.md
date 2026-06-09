# CertificateUtil::FindExtensionGuidValueByOid(char const *,_CERT_CONTEXT const *,ushort * *)

- ea: `0x1800b8004`
- end: `0x1800b81d7`
- name: `?FindExtensionGuidValueByOid@CertificateUtil@@SAJPEBDPEBU_CERT_CONTEXT@@PEAPEAG@Z`
- size: `467`
- prototype: `__int64 __fastcall(const char *, const struct _CERT_CONTEXT *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, loader_planting`

## callers

- `0x1800b78b0`
- `0x1800b94f4`

## callees

- `0x1800269d4`
- `0x180026b54`
- `0x18002d5e4`
- `0x1800b7fb0`
- `0x1800b8004`
- `0x1800b87c4`
- `0x1800b8b08`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b812f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b812f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b81c1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b81c1`
- `CRYPT32!CryptDecodeObjectEx` at `0x1800b8125`
- `CRYPT32!CryptDecodeObjectEx` at `0x1800b8125`

## string_xrefs

- `0x1800b8042`: `CertificateUtil::FindExtensionGuidValueByOid`
- `0x1800b805c`: `CertificateUtil::FindExtensionGuidValueByOid`
- `0x1800b807e`: `CertificateUtil::FindExtensionGuidValueByOid`
- `0x1800b80ab`: `CertificateUtil::FindExtensionGuidValueByOid`
- `0x1800b80d7`: `CertificateUtil::FindExtensionGuidValueByOid`
- `0x1800b8138`: `CertificateUtil::FindExtensionGuidValueByOid`
- `0x1800b818c`: `CertificateUtil::FindExtensionGuidValueByOid`
- `0x1800b80de`: `%s: Extension was not found in the certificate. OID: %hs.`

## pseudocode

```c
__int64 __fastcall CertificateUtil::FindExtensionGuidValueByOid(
        const char *a1,
        const struct _CERT_CONTEXT *a2,
        unsigned __int16 **a3)
{
  unsigned __int16 *v3; // rsi
  unsigned int v7; // ebx
  const unsigned __int16 *v8; // rdx
  PCERT_EXTENSION ExtensionByOid; // rax
  __int64 LastError; // rdi
  int v11; // eax
  HLOCAL hMem[5]; // [rsp+40h] [rbp-28h] BYREF
  DWORD pcbStructInfo; // [rsp+70h] [rbp+8h] BYREF
  unsigned __int16 *v15; // [rsp+88h] [rbp+20h] BYREF

  v3 = 0;
  hMem[0] = 0;
  pcbStructInfo = 0;
  v15 = 0;
  if ( !a1 )
  {
    v7 = -2147024809;
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"CertificateUtil::FindExtensionGuidValueByOid", L"pcszOid");
    v8 = L"pcszOid";
LABEL_3:
    Logger::WriteNullOrEmptyParameterFailureEvent(L"CertificateUtil::FindExtensionGuidValueByOid", v8);
    goto LABEL_18;
  }
  if ( !a3 )
  {
    v7 = -2147024809;
    Logger::TraceError(
      L"%s: \"%s\" should not be null.",
      L"CertificateUtil::FindExtensionGuidValueByOid",
      L"ppszOutBuffer");
    v8 = L"ppszOutBuffer";
    goto LABEL_3;
  }
  if ( !a2 )
  {
    v7 = -2147024809;
    Logger::TraceError(
      L"%s: \"%s\" should not be null.",
      L"CertificateUtil::FindExtensionGuidValueByOid",
      &stru_1800D9558);
    v8 = (const unsigned __int16 *)&stru_1800D9558;
    goto LABEL_3;
  }
  *a3 = 0;
  ExtensionByOid = CertificateUtil::FindExtensionByOid(a1, a2);
  if ( ExtensionByOid )
  {
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
      v11 = CertificateUtil::GuidStringFromByteArray(*((const unsigned __int8 **)hMem[0] + 1), *(_DWORD *)hMem[0], &v15);
      v7 = v11;
      if ( v11 >= 0 )
      {
        *a3 = v15;
      }
      else
      {
        Logger::TraceError(
          L"%s: %s failed with error code: 0x%08x.",
          L"CertificateUtil::FindExtensionGuidValueByOid",
          L"CertificateUtil::GuidStringFromByteArray",
          (unsigned int)v11);
        v3 = v15;
      }
    }
    else
    {
      LastError = GetLastError();
      Logger::TraceError(
        L"%s: CryptDecodeObjectEx failed with error code: 0x%08x",
        L"CertificateUtil::FindExtensionGuidValueByOid",
        LastError);
      v7 = 0;
      if ( (_DWORD)LastError )
      {
        if ( (int)LastError > 0 )
          v7 = (unsigned __int16)LastError | 0x80070000;
        else
          v7 = LastError;
      }
    }
  }
  else
  {
    Logger::TraceVerbose(
      L"%s: Extension was not found in the certificate. OID: %hs.",
      L"CertificateUtil::FindExtensionGuidValueByOid",
      a1);
    v7 = -2146885628;
  }
LABEL_18:
  operator delete(v3);
  LocalFree(hMem[0]);
  return v7;
}

```

## disassembly

```asm
0x1800b8004  mov     rax, rsp
0x1800b8007  mov     [rax+10h], rbx
0x1800b800b  push    rsi
0x1800b800c  push    rdi
0x1800b800d  push    r14
0x1800b800f  sub     rsp, 50h
0x1800b8013  xor     esi, esi
0x1800b8015  mov     qword ptr [rax-28h], 0
0x1800b801d  mov     dword ptr [rax+8], 0
0x1800b8024  mov     rdi, r8
0x1800b8027  mov     [rax+20h], rsi
0x1800b802b  mov     r14, rdx
0x1800b802e  mov     rbx, rcx
0x1800b8031  test    rcx, rcx
0x1800b8034  jnz     short loc_1800B806D
0x1800b8036  lea     r8, aPcszoid; "pcszOid"
0x1800b803d  mov     ebx, 80070057h
0x1800b8042  lea     rdx, aCertificateuti_4; "CertificateUtil::FindExtensionGuidValue"...
0x1800b8049  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x1800b8050  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800b8055  lea     rdx, aPcszoid; "pcszOid"
0x1800b805c  lea     rcx, aCertificateuti_4; "CertificateUtil::FindExtensionGuidValue"...
0x1800b8063  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x1800b8068  jmp     loc_1800B81B4
0x1800b806d  test    rdi, rdi
0x1800b8070  jnz     short loc_1800B809A
0x1800b8072  lea     r8, aPpszoutbuffer; "ppszOutBuffer"
0x1800b8079  mov     ebx, 80070057h
0x1800b807e  lea     rdx, aCertificateuti_4; "CertificateUtil::FindExtensionGuidValue"...
0x1800b8085  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x1800b808c  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800b8091  lea     rdx, aPpszoutbuffer; "ppszOutBuffer"
0x1800b8098  jmp     short loc_1800B805C
0x1800b809a  test    r14, r14
0x1800b809d  jnz     short loc_1800B80C7
0x1800b809f  lea     r8, stru_1800D9558
0x1800b80a6  mov     ebx, 80070057h
0x1800b80ab  lea     rdx, aCertificateuti_4; "CertificateUtil::FindExtensionGuidValue"...
0x1800b80b2  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x1800b80b9  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800b80be  lea     rdx, stru_1800D9558; struct _CERT_CONTEXT *
0x1800b80c5  jmp     short loc_1800B805C
0x1800b80c7  mov     [r8], rsi
0x1800b80ca  call    ?FindExtensionByOid@CertificateUtil@@SAPEAU_CERT_EXTENSION@@PEBDPEBU_CERT_CONTEXT@@@Z; CertificateUtil::FindExtensionByOid(char const *,_CERT_CONTEXT const *)
0x1800b80cf  test    rax, rax
0x1800b80d2  jnz     short loc_1800B80F4
0x1800b80d4  mov     r8, rbx
0x1800b80d7  lea     rdx, aCertificateuti_4; "CertificateUtil::FindExtensionGuidValue"...
0x1800b80de  lea     rcx, aSExtensionWasN; "%s: Extension was not found in the cert"...
0x1800b80e5  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x1800b80ea  mov     ebx, 80092004h
0x1800b80ef  jmp     loc_1800B81B4
0x1800b80f4  mov     r9d, [rax+10h]; cbEncoded
0x1800b80f8  lea     rcx, [rsp+68h+arg_0]
0x1800b80fd  mov     r8, [rax+18h]; pbEncoded
0x1800b8101  mov     edx, 19h; lpszStructType
0x1800b8106  mov     [rsp+68h+pcbStructInfo], rcx; pcbStructInfo
0x1800b810b  lea     rcx, [rsp+68h+hMem]
0x1800b8110  mov     [rsp+68h+pvStructInfo], rcx; pvStructInfo
0x1800b8115  mov     ecx, [r14]; dwCertEncodingType
0x1800b8118  mov     [rsp+68h+pDecodePara], rsi; pDecodePara
0x1800b811d  mov     [rsp+68h+dwFlags], 8000h; dwFlags
0x1800b8125  call    cs:__imp_CryptDecodeObjectEx
0x1800b812b  test    eax, eax
0x1800b812d  jnz     short loc_1800B8164
0x1800b812f  call    cs:__imp_GetLastError
0x1800b8135  mov     r8d, eax
0x1800b8138  lea     rdx, aCertificateuti_4; "CertificateUtil::FindExtensionGuidValue"...
0x1800b813f  lea     rcx, aSCryptdecodeob_0; "%s: CryptDecodeObjectEx failed with err"...
0x1800b8146  mov     edi, eax
0x1800b8148  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800b814d  xor     ebx, ebx
0x1800b814f  test    edi, edi
0x1800b8151  jz      short loc_1800B81B4
0x1800b8153  jg      short loc_1800B8159
0x1800b8155  mov     ebx, edi
0x1800b8157  jmp     short loc_1800B81B4
0x1800b8159  movzx   ebx, di
0x1800b815c  or      ebx, 80070000h
0x1800b8162  jmp     short loc_1800B81B4
0x1800b8164  mov     rcx, [rsp+68h+hMem]
0x1800b8169  lea     r8, [rsp+68h+arg_18]; unsigned __int16 **
0x1800b8171  mov     edx, [rcx]; unsigned int
0x1800b8173  mov     rcx, [rcx+8]; unsigned __int8 *
0x1800b8177  call    ?GuidStringFromByteArray@CertificateUtil@@CAJPEBEKPEAPEAG@Z; CertificateUtil::GuidStringFromByteArray(uchar const *,ulong,ushort * *)
0x1800b817c  mov     ebx, eax
0x1800b817e  test    eax, eax
0x1800b8180  jns     short loc_1800B81A9
0x1800b8182  mov     r9d, eax
0x1800b8185  lea     r8, aCertificateuti_3; "CertificateUtil::GuidStringFromByteArra"...
0x1800b818c  lea     rdx, aCertificateuti_4; "CertificateUtil::FindExtensionGuidValue"...
0x1800b8193  lea     rcx, aSSFailedWithEr_0; "%s: %s failed with error code: 0x%08x."
0x1800b819a  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800b819f  mov     rsi, [rsp+68h+arg_18]
0x1800b81a7  jmp     short loc_1800B81B4
0x1800b81a9  mov     rax, [rsp+68h+arg_18]
0x1800b81b1  mov     [rdi], rax
0x1800b81b4  mov     rcx, rsi; Block
0x1800b81b7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800b81bc  mov     rcx, [rsp+68h+hMem]; hMem
0x1800b81c1  call    cs:__imp_LocalFree
0x1800b81c7  mov     eax, ebx
0x1800b81c9  mov     rbx, [rsp+68h+arg_8]
0x1800b81ce  add     rsp, 50h
0x1800b81d2  pop     r14
0x1800b81d4  pop     rdi
0x1800b81d5  pop     rsi
0x1800b81d6  retn
```
