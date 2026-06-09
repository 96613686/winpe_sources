# _CompareAuthKeyId(ulong,_CERT_CONTEXT const *,_CERT_CONTEXT const *)

- ea: `0x18003743c`
- end: `0x180037543`
- name: `?_CompareAuthKeyId@@YAHKPEBU_CERT_CONTEXT@@0@Z`
- size: `263`
- prototype: `__int64 __fastcall(DWORD dwCertEncodingType, const struct _CERT_CONTEXT *, const struct _CERT_CONTEXT *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800377f8`

## callees

- `0x180011550`
- `0x18001f600`
- `0x18003743c`

## import_xrefs

- `CRYPT32!CertCompareCertificateName` at `0x1800374eb`
- `CRYPT32!CertCompareCertificateName` at `0x1800374eb`
- `CRYPT32!CertFindExtension` at `0x180037486`
- `CRYPT32!CertFindExtension` at `0x180037486`
- `CRYPT32!CertCompareIntegerBlob` at `0x180037506`
- `CRYPT32!CertCompareIntegerBlob` at `0x180037506`

## pseudocode

```c
__int64 __fastcall _CompareAuthKeyId(
        DWORD dwCertEncodingType,
        const struct _CERT_CONTEXT *a2,
        const struct _CERT_CONTEXT *a3)
{
  PCERT_INFO pCertInfo; // rdx
  struct _CRYPTOAPI_BLOB *v4; // rax
  PCERT_EXTENSION Extension; // rax
  unsigned int v8; // ebx
  DWORD v10; // [rsp+68h] [rbp+10h] BYREF
  struct _CRYPTOAPI_BLOB *v11; // [rsp+78h] [rbp+20h] BYREF

  pCertInfo = a2->pCertInfo;
  v4 = 0;
  v10 = 0;
  v11 = 0;
  if ( !pCertInfo->cExtension )
    goto LABEL_10;
  Extension = CertFindExtension("2.5.29.1", pCertInfo->cExtension, pCertInfo->rgExtension);
  if ( Extension
    && (unsigned int)TrustDecode(
                       1,
                       (void **)&v11,
                       &v10,
                       0x68u,
                       dwCertEncodingType,
                       (const CHAR *)9,
                       Extension->Value.pbData,
                       Extension->Value.cbData,
                       1u) )
  {
    v4 = v11;
    if ( !v11[1].cbData || !v11[2].cbData )
      goto LABEL_10;
    if ( CertCompareCertificateName(dwCertEncodingType, v11 + 1, &a3->pCertInfo->Issuer)
      && CertCompareIntegerBlob(v11 + 2, &a3->pCertInfo->SerialNumber) )
    {
      v4 = v11;
      v8 = 1;
      goto LABEL_11;
    }
  }
  v4 = v11;
LABEL_10:
  v8 = 0;
LABEL_11:
  if ( v4 )
    TrustFreeDecode(1, &v11);
  return v8;
}

```

## disassembly

```asm
0x18003743c  mov     [rsp+arg_0], rbx
0x180037441  mov     [rsp+arg_10], rsi
0x180037446  push    rdi
0x180037447  sub     rsp, 50h
0x18003744b  mov     rdx, [rdx+18h]
0x18003744f  xor     eax, eax
0x180037451  mov     [rsp+58h+arg_8], 0
0x180037459  mov     rbx, r8
0x18003745c  mov     [rsp+58h+arg_18], rax
0x180037461  mov     edi, ecx
0x180037463  lea     esi, [rax+1]
0x180037466  cmp     [rdx+0C0h], esi
0x18003746c  jb      loc_18003751E
0x180037472  mov     r8, [rdx+0C8h]; rgExtensions
0x180037479  lea     rcx, a25291; "2.5.29.1"
0x180037480  mov     edx, [rdx+0C0h]; cExtensions
0x180037486  call    cs:__imp_CertFindExtension
0x18003748c  test    rax, rax
0x18003748f  jz      loc_180037519
0x180037495  mov     ecx, [rax+10h]
0x180037498  lea     r9d, [rsi+67h]
0x18003749c  mov     rax, [rax+18h]
0x1800374a0  lea     r8, [rsp+58h+arg_8]
0x1800374a5  mov     [rsp+58h+var_18], esi
0x1800374a9  lea     rdx, [rsp+58h+arg_18]
0x1800374ae  mov     [rsp+58h+var_20], ecx
0x1800374b2  mov     ecx, esi
0x1800374b4  mov     [rsp+58h+var_28], rax
0x1800374b9  mov     [rsp+58h+var_30], 9
0x1800374c2  mov     [rsp+58h+var_38], edi
0x1800374c6  call    TrustDecode
0x1800374cb  test    eax, eax
0x1800374cd  jz      short loc_180037519
0x1800374cf  mov     rax, [rsp+58h+arg_18]
0x1800374d4  lea     rdx, [rax+10h]; pCertName1
0x1800374d8  cmp     [rdx], esi
0x1800374da  jb      short loc_18003751E
0x1800374dc  cmp     [rax+20h], esi
0x1800374df  jb      short loc_18003751E
0x1800374e1  mov     r8, [rbx+18h]
0x1800374e5  mov     ecx, edi; dwCertEncodingType
0x1800374e7  add     r8, 30h ; '0'; pCertName2
0x1800374eb  call    cs:__imp_CertCompareCertificateName
0x1800374f1  test    eax, eax
0x1800374f3  jz      short loc_180037519
0x1800374f5  mov     rdx, [rbx+18h]
0x1800374f9  mov     rcx, [rsp+58h+arg_18]
0x1800374fe  add     rdx, 8; pInt2
0x180037502  add     rcx, 20h ; ' '; pInt1
0x180037506  call    cs:__imp_CertCompareIntegerBlob
0x18003750c  test    eax, eax
0x18003750e  jz      short loc_180037519
0x180037510  mov     rax, [rsp+58h+arg_18]
0x180037515  mov     ebx, esi
0x180037517  jmp     short loc_180037520
0x180037519  mov     rax, [rsp+58h+arg_18]
0x18003751e  xor     ebx, ebx
0x180037520  test    rax, rax
0x180037523  jz      short loc_180037531
0x180037525  lea     rdx, [rsp+58h+arg_18]
0x18003752a  mov     ecx, esi
0x18003752c  call    TrustFreeDecode
0x180037531  mov     rsi, [rsp+58h+arg_10]
0x180037536  mov     eax, ebx
0x180037538  mov     rbx, [rsp+58h+arg_0]
0x18003753d  add     rsp, 50h
0x180037541  pop     rdi
0x180037542  retn
```
