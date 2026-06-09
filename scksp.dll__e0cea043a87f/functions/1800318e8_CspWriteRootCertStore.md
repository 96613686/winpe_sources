# CspWriteRootCertStore

- ea: `0x1800318e8`
- end: `0x180031a8b`
- name: `CspWriteRootCertStore`
- size: `419`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800283dc`

## callees

- `0x18000d9d0`
- `0x18002b140`
- `0x18002d444`
- `0x18002d61c`
- `0x18002db88`
- `0x18002e3bc`
- `0x1800318e8`
- `0x180036ca0`
- `0x18003c240`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003194c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003194c`
- `CRYPT32!CertSaveStore` at `0x180031942`
- `CRYPT32!CertSaveStore` at `0x180031991`
- `CRYPT32!CertSaveStore` at `0x180031942`
- `CRYPT32!CertSaveStore` at `0x180031991`

## pseudocode

```c
__int64 __fastcall CspWriteRootCertStore(__int64 a1, void *a2)
{
  unsigned int LastError; // eax
  unsigned int File; // ebx
  __int64 v6; // rdx
  __int64 v7; // r8
  void *v8; // rax
  size_t v9; // rdi
  __int64 v10; // rdx
  __int64 v11; // rdx
  __int64 v12; // r9
  size_t v14; // [rsp+30h] [rbp-30h] BYREF
  size_t size[2]; // [rsp+38h] [rbp-28h] BYREF
  __int64 v16; // [rsp+48h] [rbp-18h] BYREF
  int v17; // [rsp+50h] [rbp-10h]

  LODWORD(v14) = 0;
  v16 = 0;
  v17 = 0;
  *(_OWORD *)size = 0;
  if ( !CertSaveStore(a2, 0x10001u, 2u, 2u, size, 0) )
    goto LABEL_2;
  size[1] = (size_t)MIDL_user_allocate(LODWORD(size[0]));
  if ( !size[1] )
  {
LABEL_4:
    File = 8;
    goto LABEL_15;
  }
  if ( !CertSaveStore(a2, 0x10001u, 2u, 2u, size, 0) )
  {
LABEL_2:
    LastError = GetLastError();
LABEL_14:
    File = LastError;
    goto LABEL_15;
  }
  File = CspQueryCapabilities(a1, &v16);
  if ( File )
    goto LABEL_15;
  if ( HIDWORD(v16) )
  {
LABEL_12:
    CspDeleteFile(a1, v6, v7, "msroots");
    File = CspCreateFile(a1, v10, "msroots", LODWORD(size[0]));
    if ( File )
      goto LABEL_15;
    LastError = CspWriteFile(a1, v11, "msroots", v12, (void *)size[1], size[0]);
    goto LABEL_14;
  }
  File = CompressData(LODWORD(size[0]), 0, &v14, 0);
  if ( File )
    goto LABEL_15;
  v8 = MIDL_user_allocate((unsigned int)v14);
  v9 = (size_t)v8;
  if ( !v8 )
    goto LABEL_4;
  File = CompressData(LODWORD(size[0]), size[1], &v14, v8);
  if ( !File )
  {
    CspFreeH(size[1]);
    LODWORD(size[0]) = v14;
    size[1] = v9;
    goto LABEL_12;
  }
  CspFreeH(v9);
LABEL_15:
  if ( size[1] )
    CspFreeH(size[1]);
  return File;
}

```

## disassembly

```asm
0x1800318e8  mov     [rsp-18h+arg_10], rbx
0x1800318ed  push    rbp
0x1800318ee  push    rsi
0x1800318ef  push    rdi
0x1800318f0  mov     rbp, rsp
0x1800318f3  sub     rsp, 60h
0x1800318f7  mov     rax, cs:__security_cookie
0x1800318fe  xor     rax, rsp
0x180031901  mov     [rbp+var_8], rax
0x180031905  xor     eax, eax
0x180031907  mov     dword ptr [rbp+var_30], 0
0x18003190e  mov     [rsp+60h+dwFlags], eax; dwFlags
0x180031912  mov     rbx, rdx
0x180031915  mov     [rbp+var_18], rax
0x180031919  mov     edi, 2
0x18003191e  mov     [rbp+var_10], eax
0x180031921  mov     rsi, rcx
0x180031924  lea     rax, [rbp+size]
0x180031928  xorps   xmm0, xmm0
0x18003192b  mov     r9d, edi; dwSaveTo
0x18003192e  mov     [rsp+60h+pvSaveToPara], rax; pvSaveToPara
0x180031933  mov     r8d, edi; dwSaveAs
0x180031936  mov     edx, 10001h; dwEncodingType
0x18003193b  mov     rcx, rbx; hCertStore
0x18003193e  movups  xmmword ptr [rbp+size], xmm0
0x180031942  call    cs:__imp_CertSaveStore
0x180031948  test    eax, eax
0x18003194a  jnz     short loc_180031957
0x18003194c  call    cs:__imp_GetLastError
0x180031952  jmp     loc_180031A53
0x180031957  mov     ecx, dword ptr [rbp+size]; size
0x18003195a  call    MIDL_user_allocate
0x18003195f  mov     [rbp+size+8], rax
0x180031963  test    rax, rax
0x180031966  jnz     short loc_180031972
0x180031968  mov     ebx, 8
0x18003196d  jmp     loc_180031A55
0x180031972  lea     rax, [rbp+size]
0x180031976  mov     [rsp+60h+dwFlags], 0; dwFlags
0x18003197e  mov     r9d, edi; dwSaveTo
0x180031981  mov     [rsp+60h+pvSaveToPara], rax; pvSaveToPara
0x180031986  mov     r8d, edi; dwSaveAs
0x180031989  mov     edx, 10001h; dwEncodingType
0x18003198e  mov     rcx, rbx; hCertStore
0x180031991  call    cs:__imp_CertSaveStore
0x180031997  test    eax, eax
0x180031999  jz      short loc_18003194C
0x18003199b  lea     rdx, [rbp+var_18]
0x18003199f  mov     rcx, rsi
0x1800319a2  call    CspQueryCapabilities
0x1800319a7  mov     ebx, eax
0x1800319a9  test    eax, eax
0x1800319ab  jnz     loc_180031A55
0x1800319b1  cmp     dword ptr [rbp+var_18+4], eax
0x1800319b4  jnz     short loc_180031A11
0x1800319b6  mov     ecx, dword ptr [rbp+size]
0x1800319b9  lea     r8, [rbp+var_30]
0x1800319bd  xor     r9d, r9d
0x1800319c0  xor     edx, edx
0x1800319c2  call    CompressData
0x1800319c7  mov     ebx, eax
0x1800319c9  test    eax, eax
0x1800319cb  jnz     loc_180031A55
0x1800319d1  mov     ecx, dword ptr [rbp+var_30]; size
0x1800319d4  call    MIDL_user_allocate
0x1800319d9  mov     rdi, rax
0x1800319dc  test    rax, rax
0x1800319df  jz      short loc_180031968
0x1800319e1  mov     rdx, [rbp+size+8]
0x1800319e5  lea     r8, [rbp+var_30]
0x1800319e9  mov     ecx, dword ptr [rbp+size]
0x1800319ec  mov     r9, rax
0x1800319ef  call    CompressData
0x1800319f4  mov     ebx, eax
0x1800319f6  test    eax, eax
0x1800319f8  jnz     loc_180031A81
0x1800319fe  mov     rcx, [rbp+size+8]
0x180031a02  call    CspFreeH
0x180031a07  mov     eax, dword ptr [rbp+var_30]
0x180031a0a  mov     dword ptr [rbp+size], eax
0x180031a0d  mov     [rbp+size+8], rdi
0x180031a11  lea     rdi, aMsroots; "msroots"
0x180031a18  mov     rcx, rsi
0x180031a1b  mov     r9, rdi
0x180031a1e  call    CspDeleteFile
0x180031a23  mov     r9d, dword ptr [rbp+size]
0x180031a27  mov     r8, rdi
0x180031a2a  mov     rcx, rsi
0x180031a2d  call    CspCreateFile
0x180031a32  mov     ebx, eax
0x180031a34  test    eax, eax
0x180031a36  jnz     short loc_180031A55
0x180031a38  mov     eax, dword ptr [rbp+size]
0x180031a3b  mov     r8, rdi
0x180031a3e  mov     [rsp+60h+dwFlags], eax
0x180031a42  mov     rcx, rsi
0x180031a45  mov     rax, [rbp+size+8]
0x180031a49  mov     [rsp+60h+pvSaveToPara], rax
0x180031a4e  call    CspWriteFile
0x180031a53  mov     ebx, eax
0x180031a55  mov     rcx, [rbp+size+8]
0x180031a59  test    rcx, rcx
0x180031a5c  jz      short loc_180031A63
0x180031a5e  call    CspFreeH
0x180031a63  mov     eax, ebx
0x180031a65  mov     rcx, [rbp+var_8]
0x180031a69  xor     rcx, rsp; StackCookie
0x180031a6c  call    __security_check_cookie
0x180031a71  mov     rbx, [rsp+60h+arg_10]
0x180031a79  add     rsp, 60h
0x180031a7d  pop     rdi
0x180031a7e  pop     rsi
0x180031a7f  pop     rbp
0x180031a80  retn
0x180031a81  mov     rcx, rdi
0x180031a84  call    CspFreeH
0x180031a89  jmp     short loc_180031A55
```
