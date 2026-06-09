# WTHelperCertIsSelfSigned

- ea: `0x180028040`
- end: `0x1800281ce`
- name: `WTHelperCertIsSelfSigned`
- size: `398`
- prototype: `BOOL __stdcall(DWORD dwEncoding, CERT_INFO *pCert)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180028040`
- `0x18004de46`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800281a3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800281b5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800281a3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800281b5`
- `CRYPT32!CryptDecodeObjectEx` at `0x1800280e8`
- `CRYPT32!CryptDecodeObjectEx` at `0x180028129`
- `CRYPT32!CryptDecodeObjectEx` at `0x1800280e8`
- `CRYPT32!CryptDecodeObjectEx` at `0x180028129`
- `CRYPT32!CertCompareCertificateName` at `0x18002817f`
- `CRYPT32!CertCompareCertificateName` at `0x18002817f`
- `CRYPT32!CertFindExtension` at `0x180028077`
- `CRYPT32!CertFindExtension` at `0x180028095`
- `CRYPT32!CertFindExtension` at `0x180028077`
- `CRYPT32!CertFindExtension` at `0x180028095`

## pseudocode

```c
BOOL __stdcall WTHelperCertIsSelfSigned(DWORD dwEncoding, CERT_INFO *pCert)
{
  CERT_EXTENSION *rgExtension; // r8
  DWORD cExtension; // edx
  BOOL v6; // esi
  PCERT_EXTENSION Extension; // rdi
  PCERT_EXTENSION v8; // rax
  PCERT_EXTENSION v9; // rbx
  DWORD cbData; // r9d
  const BYTE *pbData; // r8
  DWORD v12; // r9d
  const BYTE *v13; // r8
  const void **v14; // rbx
  HLOCAL v15; // rdi
  BOOL v16; // eax
  DWORD pcbStructInfo; // [rsp+78h] [rbp+38h] BYREF
  const void **pvStructInfo; // [rsp+80h] [rbp+40h] BYREF
  HLOCAL hMem; // [rsp+88h] [rbp+48h] BYREF

  rgExtension = pCert->rgExtension;
  cExtension = pCert->cExtension;
  v6 = 0;
  hMem = 0;
  pvStructInfo = 0;
  Extension = CertFindExtension("2.5.29.35", cExtension, rgExtension);
  v8 = CertFindExtension("2.5.29.14", pCert->cExtension, pCert->rgExtension);
  v9 = v8;
  if ( !Extension || !v8 )
    goto LABEL_15;
  cbData = Extension->Value.cbData;
  pbData = Extension->Value.pbData;
  pcbStructInfo = 0;
  if ( !CryptDecodeObjectEx(0x10001u, "2.5.29.35", pbData, cbData, 0x8005u, 0, &hMem, &pcbStructInfo) )
    hMem = 0;
  v12 = v9->Value.cbData;
  v13 = v9->Value.pbData;
  pcbStructInfo = 0;
  if ( CryptDecodeObjectEx(0x10001u, "2.5.29.14", v13, v12, 0x8005u, 0, &pvStructInfo, &pcbStructInfo) )
  {
    v14 = pvStructInfo;
  }
  else
  {
    v14 = 0;
    pvStructInfo = 0;
  }
  v15 = hMem;
  if ( hMem && *(_DWORD *)hMem && v14 && *(_DWORD *)v14 )
  {
    if ( *(_DWORD *)hMem == *(_DWORD *)v14 && !memcmp_0(*((const void **)hMem + 1), v14[1], *(unsigned int *)hMem) )
      v6 = 1;
  }
  else
  {
LABEL_15:
    v16 = CertCompareCertificateName(dwEncoding, &pCert->Issuer, &pCert->Subject);
    v15 = hMem;
    v14 = pvStructInfo;
    v6 = v16;
  }
  if ( v15 )
  {
    LocalFree(v15);
    v14 = pvStructInfo;
  }
  if ( v14 )
    LocalFree(v14);
  return v6;
}

```

## disassembly

```asm
0x180028040  mov     [rsp-28h+arg_0], rbx
0x180028045  push    rbp
0x180028046  push    rsi
0x180028047  push    rdi
0x180028048  push    r14
0x18002804a  push    r15
0x18002804c  mov     rbp, rsp
0x18002804f  sub     rsp, 40h
0x180028053  mov     r8, [rdx+0C8h]; rgExtensions
0x18002805a  mov     r14, rdx
0x18002805d  mov     edx, [rdx+0C0h]; cExtensions
0x180028063  mov     r15d, ecx
0x180028066  xor     esi, esi
0x180028068  lea     rcx, a252935; "2.5.29.35"
0x18002806f  mov     [rbp+hMem], rsi
0x180028073  mov     [rbp+arg_10], rsi
0x180028077  call    cs:__imp_CertFindExtension
0x18002807d  mov     r8, [r14+0C8h]; rgExtensions
0x180028084  lea     rcx, a252914; "2.5.29.14"
0x18002808b  mov     edx, [r14+0C0h]; cExtensions
0x180028092  mov     rdi, rax
0x180028095  call    cs:__imp_CertFindExtension
0x18002809b  mov     rbx, rax
0x18002809e  test    rdi, rdi
0x1800280a1  jz      loc_180028174
0x1800280a7  test    rax, rax
0x1800280aa  jz      loc_180028174
0x1800280b0  mov     r9d, [rdi+10h]; cbEncoded
0x1800280b4  lea     rax, [rbp+arg_8]
0x1800280b8  mov     r8, [rdi+18h]; pbEncoded
0x1800280bc  lea     rdx, a252935; "2.5.29.35"
0x1800280c3  mov     [rsp+40h+pcbStructInfo], rax; pcbStructInfo
0x1800280c8  mov     edi, 10001h
0x1800280cd  lea     rax, [rbp+hMem]
0x1800280d1  mov     [rbp+arg_8], esi
0x1800280d4  mov     [rsp+40h+pvStructInfo], rax; pvStructInfo
0x1800280d9  mov     ecx, edi; dwCertEncodingType
0x1800280db  mov     [rsp+40h+pDecodePara], rsi; pDecodePara
0x1800280e0  mov     [rsp+40h+dwFlags], 8005h; dwFlags
0x1800280e8  call    cs:__imp_CryptDecodeObjectEx
0x1800280ee  test    eax, eax
0x1800280f0  jnz     short loc_1800280F6
0x1800280f2  mov     [rbp+hMem], rsi
0x1800280f6  mov     r9d, [rbx+10h]; cbEncoded
0x1800280fa  lea     rax, [rbp+arg_8]
0x1800280fe  mov     r8, [rbx+18h]; pbEncoded
0x180028102  lea     rdx, a252914; "2.5.29.14"
0x180028109  mov     [rsp+40h+pcbStructInfo], rax; pcbStructInfo
0x18002810e  mov     ecx, edi; dwCertEncodingType
0x180028110  lea     rax, [rbp+arg_10]
0x180028114  mov     [rbp+arg_8], esi
0x180028117  mov     [rsp+40h+pvStructInfo], rax; pvStructInfo
0x18002811c  mov     [rsp+40h+pDecodePara], rsi; pDecodePara
0x180028121  mov     [rsp+40h+dwFlags], 8005h; dwFlags
0x180028129  call    cs:__imp_CryptDecodeObjectEx
0x18002812f  test    eax, eax
0x180028131  jnz     short loc_18002813B
0x180028133  xor     ebx, ebx
0x180028135  mov     [rbp+arg_10], rbx
0x180028139  jmp     short loc_18002813F
0x18002813b  mov     rbx, [rbp+arg_10]
0x18002813f  mov     rdi, [rbp+hMem]
0x180028143  test    rdi, rdi
0x180028146  jz      short loc_180028174
0x180028148  cmp     [rdi], esi
0x18002814a  jz      short loc_180028174
0x18002814c  test    rbx, rbx
0x18002814f  jz      short loc_180028174
0x180028151  mov     eax, [rbx]
0x180028153  test    eax, eax
0x180028155  jz      short loc_180028174
0x180028157  cmp     [rdi], eax
0x180028159  jnz     short loc_18002819B
0x18002815b  mov     r8d, [rdi]; Size
0x18002815e  mov     rdx, [rbx+8]; Buf2
0x180028162  mov     rcx, [rdi+8]; Buf1
0x180028166  call    memcmp_0
0x18002816b  test    eax, eax
0x18002816d  jnz     short loc_18002819B
0x18002816f  lea     esi, [rax+1]
0x180028172  jmp     short loc_18002819B
0x180028174  lea     r8, [r14+50h]; pCertName2
0x180028178  mov     ecx, r15d; dwCertEncodingType
0x18002817b  lea     rdx, [r14+30h]; pCertName1
0x18002817f  call    cs:__imp_CertCompareCertificateName
0x180028185  mov     rdi, [rbp+hMem]
0x180028189  mov     ecx, esi
0x18002818b  mov     rbx, [rbp+arg_10]
0x18002818f  mov     esi, 1
0x180028194  test    eax, eax
0x180028196  cmovnz  ecx, esi
0x180028199  mov     esi, ecx
0x18002819b  test    rdi, rdi
0x18002819e  jz      short loc_1800281AD
0x1800281a0  mov     rcx, rdi; hMem
0x1800281a3  call    cs:__imp_LocalFree
0x1800281a9  mov     rbx, [rbp+arg_10]
0x1800281ad  test    rbx, rbx
0x1800281b0  jz      short loc_1800281BB
0x1800281b2  mov     rcx, rbx; hMem
0x1800281b5  call    cs:__imp_LocalFree
0x1800281bb  mov     rbx, [rsp+40h+arg_0]
0x1800281c0  mov     eax, esi
0x1800281c2  add     rsp, 40h
0x1800281c6  pop     r15
0x1800281c8  pop     r14
0x1800281ca  pop     rdi
0x1800281cb  pop     rsi
0x1800281cc  pop     rbp
0x1800281cd  retn
```
