# KEGenerateHashWithSHA256

- ea: `0x1800b6bbc`
- end: `0x1800b6d7b`
- name: `KEGenerateHashWithSHA256`
- size: `447`
- prototype: `__int64 __fastcall(PUCHAR pbInput, ULONG cbInput)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800b6248`
- `0x1800b67c4`

## callees

- `0x1800b6bbc`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800b6c5a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800b6c9d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800b6c5a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800b6c9d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b6d26`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b6d5a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b6d26`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b6d5a`
- `bcrypt!BCryptCreateHash` at `0x1800b6ccd`
- `bcrypt!BCryptCreateHash` at `0x1800b6ccd`
- `bcrypt!BCryptHashData` at `0x1800b6ce8`
- `bcrypt!BCryptHashData` at `0x1800b6ce8`
- `bcrypt!BCryptDestroyHash` at `0x1800b6d3b`
- `bcrypt!BCryptDestroyHash` at `0x1800b6d3b`
- `bcrypt!BCryptFinishHash` at `0x1800b6d04`
- `bcrypt!BCryptFinishHash` at `0x1800b6d04`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800b6c11`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800b6c11`
- `bcrypt!BCryptGetProperty` at `0x1800b6c48`
- `bcrypt!BCryptGetProperty` at `0x1800b6c8b`
- `bcrypt!BCryptGetProperty` at `0x1800b6c48`
- `bcrypt!BCryptGetProperty` at `0x1800b6c8b`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800b6d4c`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800b6d4c`

## pseudocode

```c
__int64 __fastcall KEGenerateHashWithSHA256(PUCHAR pbInput, ULONG cbInput, PUCHAR *a3, _DWORD *a4)
{
  UCHAR *v8; // rdi
  NTSTATUS v9; // ebx
  UCHAR *v10; // rax
  ULONG pcbResult; // [rsp+40h] [rbp-20h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+48h] [rbp-18h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+50h] [rbp-10h] BYREF
  ULONG v15; // [rsp+A0h] [rbp+40h] BYREF
  ULONG pbOutput; // [rsp+A8h] [rbp+48h] BYREF

  *a3 = 0;
  *a4 = 0;
  phAlgorithm = 0;
  phHash = 0;
  pcbResult = 0;
  v15 = 0;
  pbOutput = 0;
  v8 = 0;
  if ( BCryptOpenAlgorithmProvider(&phAlgorithm, L"SHA256", 0, 0) >= 0
    && BCryptGetProperty(phAlgorithm, L"ObjectLength", (PUCHAR)&pbOutput, 4u, &pcbResult, 0) >= 0
    && (v8 = (UCHAR *)LocalAlloc(0x40u, pbOutput)) != 0
    && BCryptGetProperty(phAlgorithm, L"HashDigestLength", (PUCHAR)&v15, 4u, &pcbResult, 0) >= 0
    && (v10 = (UCHAR *)LocalAlloc(0x40u, v15), (*a3 = v10) != 0)
    && BCryptCreateHash(phAlgorithm, &phHash, v8, pbOutput, 0, 0, 0) >= 0
    && BCryptHashData(phHash, pbInput, cbInput, 0) >= 0
    && (v9 = BCryptFinishHash(phHash, *a3, v15, 0), v9 >= 0) )
  {
    *a4 = v15;
    if ( !v9 )
      goto LABEL_14;
  }
  else
  {
    v9 = 1;
  }
  if ( *a3 )
  {
    LocalFree(*a3);
    *a3 = 0;
  }
  *a4 = 0;
LABEL_14:
  if ( phHash )
    BCryptDestroyHash(phHash);
  if ( phAlgorithm )
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  if ( v8 )
    LocalFree(v8);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800b6bbc  mov     [rsp-28h+arg_0], rbx
0x1800b6bc1  mov     [rsp-28h+arg_8], rsi
0x1800b6bc6  push    rbp
0x1800b6bc7  push    rdi
0x1800b6bc8  push    r12
0x1800b6bca  push    r14
0x1800b6bcc  push    r15
0x1800b6bce  mov     rbp, rsp
0x1800b6bd1  sub     rsp, 60h
0x1800b6bd5  xor     r12d, r12d
0x1800b6bd8  mov     r14, r9
0x1800b6bdb  mov     [r8], r12
0x1800b6bde  mov     rsi, r8
0x1800b6be1  mov     [r9], r12d
0x1800b6be4  mov     ebx, edx
0x1800b6be6  mov     r15, rcx
0x1800b6be9  mov     [rbp+phAlgorithm], r12
0x1800b6bed  xor     r9d, r9d; dwFlags
0x1800b6bf0  mov     [rbp+phHash], r12
0x1800b6bf4  xor     r8d, r8d; pszImplementation
0x1800b6bf7  mov     [rbp+var_20], r12d
0x1800b6bfb  lea     rdx, aSha256; "SHA256"
0x1800b6c02  mov     [rbp+arg_10], r12d
0x1800b6c06  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x1800b6c0a  mov     [rbp+pbOutput], r12d
0x1800b6c0e  mov     edi, r12d
0x1800b6c11  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1800b6c17  test    eax, eax
0x1800b6c19  jns     short loc_1800B6C25
0x1800b6c1b  mov     ebx, 1
0x1800b6c20  jmp     loc_1800B6D1E
0x1800b6c25  mov     rcx, [rbp+phAlgorithm]; hObject
0x1800b6c29  lea     rax, [rbp+var_20]
0x1800b6c2d  mov     [rsp+60h+dwFlags], r12d; dwFlags
0x1800b6c32  lea     r8, [rbp+pbOutput]; pbOutput
0x1800b6c36  mov     r9d, 4; cbOutput
0x1800b6c3c  mov     [rsp+60h+pcbResult], rax; pcbResult
0x1800b6c41  lea     rdx, aObjectlength; "ObjectLength"
0x1800b6c48  call    cs:__imp_BCryptGetProperty
0x1800b6c4e  test    eax, eax
0x1800b6c50  js      short loc_1800B6C1B
0x1800b6c52  mov     edx, [rbp+pbOutput]; uBytes
0x1800b6c55  mov     ecx, 40h ; '@'; uFlags
0x1800b6c5a  call    cs:__imp_LocalAlloc
0x1800b6c60  mov     rdi, rax
0x1800b6c63  test    rax, rax
0x1800b6c66  jz      short loc_1800B6C1B
0x1800b6c68  mov     rcx, [rbp+phAlgorithm]; hObject
0x1800b6c6c  lea     rax, [rbp+var_20]
0x1800b6c70  mov     [rsp+60h+dwFlags], r12d; dwFlags
0x1800b6c75  lea     r8, [rbp+arg_10]; pbOutput
0x1800b6c79  mov     r9d, 4; cbOutput
0x1800b6c7f  mov     [rsp+60h+pcbResult], rax; pcbResult
0x1800b6c84  lea     rdx, aHashdigestleng; "HashDigestLength"
0x1800b6c8b  call    cs:__imp_BCryptGetProperty
0x1800b6c91  test    eax, eax
0x1800b6c93  js      short loc_1800B6C1B
0x1800b6c95  mov     edx, [rbp+arg_10]; uBytes
0x1800b6c98  mov     ecx, 40h ; '@'; uFlags
0x1800b6c9d  call    cs:__imp_LocalAlloc
0x1800b6ca3  mov     [rsi], rax
0x1800b6ca6  test    rax, rax
0x1800b6ca9  jz      loc_1800B6C1B
0x1800b6caf  mov     r9d, [rbp+pbOutput]; cbHashObject
0x1800b6cb3  lea     rdx, [rbp+phHash]; phHash
0x1800b6cb7  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x1800b6cbb  mov     r8, rdi; pbHashObject
0x1800b6cbe  mov     [rsp+60h+var_30], r12d; dwFlags
0x1800b6cc3  mov     [rsp+60h+dwFlags], r12d; cbSecret
0x1800b6cc8  mov     [rsp+60h+pcbResult], r12; pbSecret
0x1800b6ccd  call    cs:__imp_BCryptCreateHash
0x1800b6cd3  test    eax, eax
0x1800b6cd5  js      loc_1800B6C1B
0x1800b6cdb  mov     rcx, [rbp+phHash]; hHash
0x1800b6cdf  xor     r9d, r9d; dwFlags
0x1800b6ce2  mov     r8d, ebx; cbInput
0x1800b6ce5  mov     rdx, r15; pbInput
0x1800b6ce8  call    cs:__imp_BCryptHashData
0x1800b6cee  test    eax, eax
0x1800b6cf0  js      loc_1800B6C1B
0x1800b6cf6  mov     r8d, [rbp+arg_10]; cbOutput
0x1800b6cfa  xor     r9d, r9d; dwFlags
0x1800b6cfd  mov     rdx, [rsi]; pbOutput
0x1800b6d00  mov     rcx, [rbp+phHash]; hHash
0x1800b6d04  call    cs:__imp_BCryptFinishHash
0x1800b6d0a  mov     ebx, eax
0x1800b6d0c  test    eax, eax
0x1800b6d0e  js      loc_1800B6C1B
0x1800b6d14  mov     eax, [rbp+arg_10]
0x1800b6d17  mov     [r14], eax
0x1800b6d1a  test    ebx, ebx
0x1800b6d1c  jz      short loc_1800B6D32
0x1800b6d1e  mov     rcx, [rsi]; hMem
0x1800b6d21  test    rcx, rcx
0x1800b6d24  jz      short loc_1800B6D2F
0x1800b6d26  call    cs:__imp_LocalFree
0x1800b6d2c  mov     [rsi], r12
0x1800b6d2f  mov     [r14], r12d
0x1800b6d32  mov     rcx, [rbp+phHash]; hHash
0x1800b6d36  test    rcx, rcx
0x1800b6d39  jz      short loc_1800B6D41
0x1800b6d3b  call    cs:__imp_BCryptDestroyHash
0x1800b6d41  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x1800b6d45  test    rcx, rcx
0x1800b6d48  jz      short loc_1800B6D52
0x1800b6d4a  xor     edx, edx; dwFlags
0x1800b6d4c  call    cs:__imp_BCryptCloseAlgorithmProvider
0x1800b6d52  test    rdi, rdi
0x1800b6d55  jz      short loc_1800B6D60
0x1800b6d57  mov     rcx, rdi; hMem
0x1800b6d5a  call    cs:__imp_LocalFree
0x1800b6d60  lea     r11, [rsp+60h+var_s0]
0x1800b6d65  mov     eax, ebx
0x1800b6d67  mov     rbx, [r11+30h]
0x1800b6d6b  mov     rsi, [r11+38h]
0x1800b6d6f  mov     rsp, r11
0x1800b6d72  pop     r15
0x1800b6d74  pop     r14
0x1800b6d76  pop     r12
0x1800b6d78  pop     rdi
0x1800b6d79  pop     rbp
0x1800b6d7a  retn
```
