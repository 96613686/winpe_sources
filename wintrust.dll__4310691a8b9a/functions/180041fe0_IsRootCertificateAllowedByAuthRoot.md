# IsRootCertificateAllowedByAuthRoot

- ea: `0x180041fe0`
- end: `0x18004209f`
- name: `IsRootCertificateAllowedByAuthRoot`
- size: `191`
- prototype: `__int64 __fastcall(PCCERT_CONTEXT pCertContext)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800246f0`

## callees

- `0x18002b260`
- `0x18002b648`
- `0x18002ba3c`
- `0x18002c090`
- `0x180041fe0`

## import_xrefs

- `CRYPT32!CertFreeCTLContext` at `0x180042087`
- `CRYPT32!CertFreeCTLContext` at `0x180042087`

## string_xrefs

- `0x180042029`: `onecore\ds\security\cryptoapi\pkitrust\softpub\configciprov.cpp`
- `0x18004205c`: `onecore\ds\security\cryptoapi\pkitrust\softpub\configciprov.cpp`

## pseudocode

```c
__int64 __fastcall IsRootCertificateAllowedByAuthRoot(CERT_CONTEXT *pCertContext, _BYTE *a2)
{
  int EncodedCertificateListFromRegistry; // ebx
  int SignerInAllowCTL; // eax
  int v7; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  char v9; // [rsp+40h] [rbp+18h] BYREF
  PCCTL_CONTEXT pCtlContext; // [rsp+48h] [rbp+20h]

  v9 = 0;
  pCtlContext = 0;
  EncodedCertificateListFromRegistry = LoadEncodedCertificateListFromRegistry(pCertContext, (__int64)a2);
  if ( EncodedCertificateListFromRegistry == -2147024894 )
    EncodedCertificateListFromRegistry = LoadAuthrootFromResource();
  if ( EncodedCertificateListFromRegistry >= 0 )
  {
    SignerInAllowCTL = FindSignerInAllowCTL(pCtlContext, pCertContext, &v9);
    EncodedCertificateListFromRegistry = SignerInAllowCTL;
    if ( SignerInAllowCTL >= 0 )
    {
      EncodedCertificateListFromRegistry = 0;
      if ( v9 )
        *a2 = 1;
      else
        *a2 = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x452,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\pkitrust\\softpub\\configciprov.cpp",
        (const char *)(unsigned int)SignerInAllowCTL,
        v7);
    }
    CertFreeCTLContext(pCtlContext);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x44E,
      (unsigned int)"onecore\\ds\\security\\cryptoapi\\pkitrust\\softpub\\configciprov.cpp",
      (const char *)(unsigned int)EncodedCertificateListFromRegistry,
      v7);
  }
  return (unsigned int)EncodedCertificateListFromRegistry;
}

```

## disassembly

```asm
0x180041fe0  mov     rax, rsp
0x180041fe3  mov     [rax+8], rbx
0x180041fe7  mov     [rax+10h], rsi
0x180041feb  push    rdi; int
0x180041fec  sub     rsp, 20h
0x180041ff0  lea     r8, [rax+20h]
0x180041ff4  mov     byte ptr [rax+18h], 0
0x180041ff8  mov     rdi, rdx
0x180041ffb  mov     qword ptr [rax+20h], 0
0x180042003  mov     rsi, rcx
0x180042006  call    LoadEncodedCertificateListFromRegistry
0x18004200b  mov     ebx, eax
0x18004200d  cmp     eax, 80070002h
0x180042012  jnz     short loc_180042020
0x180042014  lea     rcx, [rsp+28h+pCtlContext]
0x180042019  call    LoadAuthrootFromResource
0x18004201e  mov     ebx, eax
0x180042020  test    ebx, ebx
0x180042022  jns     short loc_18004203F
0x180042024  mov     rcx, [rsp+28h]; this
0x180042029  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\pkitr"...
0x180042030  mov     r9d, ebx; char *
0x180042033  mov     edx, 44Eh; void *
0x180042038  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004203d  jmp     short loc_18004208D
0x18004203f  mov     rcx, [rsp+28h+pCtlContext]; pCtlContext
0x180042044  lea     r8, [rsp+28h+arg_10]
0x180042049  mov     rdx, rsi; pCertContext
0x18004204c  call    FindSignerInAllowCTL
0x180042051  mov     ebx, eax
0x180042053  test    eax, eax
0x180042055  jns     short loc_180042072
0x180042057  mov     rcx, [rsp+28h]; this
0x18004205c  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\pkitr"...
0x180042063  mov     r9d, eax; char *
0x180042066  mov     edx, 452h; void *
0x18004206b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180042070  jmp     short loc_180042082
0x180042072  xor     ebx, ebx
0x180042074  cmp     [rsp+28h+arg_10], bl
0x180042078  jz      short loc_18004207F
0x18004207a  mov     byte ptr [rdi], 1
0x18004207d  jmp     short loc_180042082
0x18004207f  mov     byte ptr [rdi], 0
0x180042082  mov     rcx, [rsp+28h+pCtlContext]; pCtlContext
0x180042087  call    cs:__imp_CertFreeCTLContext
0x18004208d  mov     rsi, [rsp+28h+arg_8]
0x180042092  mov     eax, ebx
0x180042094  mov     rbx, [rsp+28h+arg_0]
0x180042099  add     rsp, 20h
0x18004209d  pop     rdi
0x18004209e  retn
```
