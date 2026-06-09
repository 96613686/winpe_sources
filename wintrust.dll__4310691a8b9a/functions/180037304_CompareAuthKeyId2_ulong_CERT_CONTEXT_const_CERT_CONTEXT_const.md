# _CompareAuthKeyId2(ulong,_CERT_CONTEXT const *,_CERT_CONTEXT const *)

- ea: `0x180037304`
- end: `0x180037433`
- name: `?_CompareAuthKeyId2@@YAHKPEBU_CERT_CONTEXT@@0@Z`
- size: `303`
- prototype: `__int64 __fastcall(DWORD dwCertEncodingType, const struct _CERT_CONTEXT *, const struct _CERT_CONTEXT *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800377f8`

## callees

- `0x180011550`
- `0x18001f600`
- `0x180037304`

## import_xrefs

- `CRYPT32!CertCompareCertificateName` at `0x1800373e1`
- `CRYPT32!CertCompareCertificateName` at `0x1800373e1`
- `CRYPT32!CertFindExtension` at `0x180037346`
- `CRYPT32!CertFindExtension` at `0x180037346`
- `CRYPT32!CertCompareIntegerBlob` at `0x1800373fc`
- `CRYPT32!CertCompareIntegerBlob` at `0x1800373fc`

## pseudocode

```c
__int64 __fastcall _CompareAuthKeyId2(
        DWORD dwCertEncodingType,
        const struct _CERT_CONTEXT *a2,
        const struct _CERT_CONTEXT *a3)
{
  PCERT_INFO pCertInfo; // r8
  DWORD cExtension; // edx
  PCERT_EXTENSION Extension; // rax
  __int64 v8; // rdx
  unsigned int cbData; // r8d
  unsigned int v10; // ebx
  DWORD v12; // [rsp+68h] [rbp+10h] BYREF
  struct _CRYPTOAPI_BLOB *v13; // [rsp+78h] [rbp+20h] BYREF

  v12 = 0;
  pCertInfo = a2->pCertInfo;
  v13 = 0;
  cExtension = pCertInfo->cExtension;
  if ( !cExtension )
    goto LABEL_11;
  Extension = CertFindExtension("2.5.29.35", cExtension, pCertInfo->rgExtension);
  if ( !Extension
    || !(unsigned int)TrustDecode(
                        1,
                        (void **)&v13,
                        &v12,
                        0x67u,
                        dwCertEncodingType,
                        (const CHAR *)0x1F,
                        Extension->Value.pbData,
                        Extension->Value.cbData,
                        1u) )
  {
    goto LABEL_11;
  }
  v8 = 0;
  cbData = v13[1].cbData;
  if ( cbData )
  {
    while ( *(_DWORD *)&v13[1].pbData[24 * v8] != 5 )
    {
      v8 = (unsigned int)(v8 + 1);
      if ( (unsigned int)v8 >= cbData )
        goto LABEL_7;
    }
  }
  else
  {
LABEL_7:
    if ( (_DWORD)v8 == cbData )
      goto LABEL_11;
  }
  if ( CertCompareCertificateName(
         dwCertEncodingType,
         (PCERT_NAME_BLOB)&v13[1].pbData[24 * v8 + 8],
         &a3->pCertInfo->Issuer)
    && CertCompareIntegerBlob(v13 + 2, &a3->pCertInfo->SerialNumber) )
  {
    v10 = 1;
    goto LABEL_12;
  }
LABEL_11:
  v10 = 0;
LABEL_12:
  if ( v13 )
    TrustFreeDecode(1, &v13);
  return v10;
}

```

## disassembly

```asm
0x180037304  mov     [rsp+arg_0], rbx
0x180037309  push    rdi
0x18003730a  sub     rsp, 50h
0x18003730e  mov     rbx, r8
0x180037311  mov     [rsp+58h+arg_8], 0
0x180037319  mov     r8, [rdx+18h]
0x18003731d  mov     edi, ecx
0x18003731f  mov     [rsp+58h+arg_18], 0
0x180037328  mov     edx, [r8+0C0h]; cExtensions
0x18003732f  cmp     edx, 1
0x180037332  jb      loc_18003740D
0x180037338  mov     r8, [r8+0C8h]; rgExtensions
0x18003733f  lea     rcx, a252935; "2.5.29.35"
0x180037346  call    cs:__imp_CertFindExtension
0x18003734c  test    rax, rax
0x18003734f  jz      loc_18003740D
0x180037355  mov     ecx, [rax+10h]
0x180037358  lea     r8, [rsp+58h+arg_8]
0x18003735d  mov     rax, [rax+18h]
0x180037361  lea     rdx, [rsp+58h+arg_18]
0x180037366  mov     [rsp+58h+var_18], 1
0x18003736e  mov     r9d, 67h ; 'g'
0x180037374  mov     [rsp+58h+var_20], ecx
0x180037378  mov     [rsp+58h+var_28], rax
0x18003737d  mov     [rsp+58h+var_30], 1Fh
0x180037386  lea     ecx, [r9-66h]
0x18003738a  mov     [rsp+58h+var_38], edi
0x18003738e  call    TrustDecode
0x180037393  test    eax, eax
0x180037395  jz      short loc_18003740D
0x180037397  mov     rax, [rsp+58h+arg_18]
0x18003739c  xor     edx, edx
0x18003739e  mov     r8d, [rax+10h]
0x1800373a2  test    r8d, r8d
0x1800373a5  jz      short loc_1800373BD
0x1800373a7  mov     r9, [rax+18h]
0x1800373ab  lea     rcx, [rdx+rdx*2]
0x1800373af  cmp     dword ptr [r9+rcx*8], 5
0x1800373b4  jz      short loc_1800373C2
0x1800373b6  inc     edx
0x1800373b8  cmp     edx, r8d
0x1800373bb  jb      short loc_1800373AB
0x1800373bd  cmp     edx, r8d
0x1800373c0  jz      short loc_18003740D
0x1800373c2  mov     rax, [rsp+58h+arg_18]
0x1800373c7  lea     rdx, [rdx+rdx*2]
0x1800373cb  mov     r8, [rbx+18h]
0x1800373cf  lea     rdx, [rdx+1]
0x1800373d3  add     r8, 30h ; '0'; pCertName2
0x1800373d7  mov     rcx, [rax+18h]
0x1800373db  lea     rdx, [rcx+rdx*8]; pCertName1
0x1800373df  mov     ecx, edi; dwCertEncodingType
0x1800373e1  call    cs:__imp_CertCompareCertificateName
0x1800373e7  test    eax, eax
0x1800373e9  jz      short loc_18003740D
0x1800373eb  mov     rdx, [rbx+18h]
0x1800373ef  mov     rcx, [rsp+58h+arg_18]
0x1800373f4  add     rdx, 8; pInt2
0x1800373f8  add     rcx, 20h ; ' '; pInt1
0x1800373fc  call    cs:__imp_CertCompareIntegerBlob
0x180037402  test    eax, eax
0x180037404  jz      short loc_18003740D
0x180037406  mov     ebx, 1
0x18003740b  jmp     short loc_18003740F
0x18003740d  xor     ebx, ebx
0x18003740f  cmp     [rsp+58h+arg_18], 0
0x180037415  jz      short loc_180037426
0x180037417  lea     rdx, [rsp+58h+arg_18]
0x18003741c  mov     ecx, 1
0x180037421  call    TrustFreeDecode
0x180037426  mov     eax, ebx
0x180037428  mov     rbx, [rsp+58h+arg_0]
0x18003742d  add     rsp, 50h
0x180037431  pop     rdi
0x180037432  retn
```
