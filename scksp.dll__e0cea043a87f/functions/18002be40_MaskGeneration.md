# MaskGeneration

- ea: `0x18002be40`
- end: `0x18002c041`
- name: `MaskGeneration`
- size: `513`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18002b5a8`
- `0x18002bb90`

## callees

- `0x180009e76`
- `0x18002be40`
- `0x18002c048`
- `0x18002c068`
- `0x18002c428`

## import_xrefs

- `bcrypt!BCryptFinishHash` at `0x18002bf7b`
- `bcrypt!BCryptFinishHash` at `0x18002bfbf`
- `bcrypt!BCryptFinishHash` at `0x18002bf7b`
- `bcrypt!BCryptFinishHash` at `0x18002bfbf`
- `bcrypt!BCryptDestroyHash` at `0x18002bf91`
- `bcrypt!BCryptDestroyHash` at `0x18002bfe5`
- `bcrypt!BCryptDestroyHash` at `0x18002bffe`
- `bcrypt!BCryptDestroyHash` at `0x18002bf91`
- `bcrypt!BCryptDestroyHash` at `0x18002bfe5`
- `bcrypt!BCryptDestroyHash` at `0x18002bffe`
- `bcrypt!BCryptHashData` at `0x18002bf13`
- `bcrypt!BCryptHashData` at `0x18002bf59`
- `bcrypt!BCryptHashData` at `0x18002bf13`
- `bcrypt!BCryptHashData` at `0x18002bf59`
- `bcrypt!BCryptCreateHash` at `0x18002bef4`
- `bcrypt!BCryptCreateHash` at `0x18002bef4`

## pseudocode

```c
__int64 MaskGeneration(void *a1, unsigned int a2, ULONG a3, UCHAR *a4, ULONG cbInput, PUCHAR pbOutput, ...)
{
  unsigned int v6; // r15d
  __int64 v7; // rdi
  ULONG v8; // ebx
  unsigned int v9; // r13d
  __int64 v10; // rdx
  UCHAR *v11; // rsi
  __int64 v12; // r8
  unsigned int v13; // ebx
  __int64 v14; // rcx
  __int64 v15; // r9
  UCHAR *v16; // r12
  unsigned int i; // r14d
  NTSTATUS v18; // eax
  __int64 j; // rcx
  UCHAR *v20; // r14
  BCRYPT_HASH_HANDLE phHash; // [rsp+40h] [rbp-18h] BYREF
  int v24; // [rsp+A8h] [rbp+50h]
  ULONG v25; // [rsp+B0h] [rbp+58h]
  PUCHAR pbInput; // [rsp+B8h] [rbp+60h]
  __int64 v27; // [rsp+D0h] [rbp+78h] BYREF
  va_list va; // [rsp+D0h] [rbp+78h]
  va_list va1; // [rsp+D8h] [rbp+80h] BYREF

  va_start(va1, pbOutput);
  va_start(va, pbOutput);
  v27 = va_arg(va1, _QWORD);
  pbInput = a4;
  v25 = a3;
  v6 = v27;
  v7 = a2;
  phHash = 0;
  v8 = a3;
  v9 = ((unsigned int)v27 + a2 - 1) / a2;
  if ( v9 < 0x100 )
    LODWORD(v27) = 0;
  v11 = (UCHAR *)MSCryptAlloc(a2 + a3);
  if ( v11 )
  {
    v16 = pbOutput;
    for ( i = 0; ; ++i )
    {
      HIBYTE(v24) = HIBYTE(i);
      if ( i >= v9 )
        goto LABEL_22;
      v18 = BCryptCreateHash(a1, &phHash, v11, v8, 0, 0, 0);
      v13 = v18;
      if ( v18 < 0 )
      {
        v15 = 326;
        goto LABEL_31;
      }
      v18 = BCryptHashData(phHash, pbInput, cbInput, 0);
      v13 = v18;
      if ( v18 < 0 )
      {
        v15 = 337;
        goto LABEL_31;
      }
      if ( v9 >= 0x100 )
      {
        for ( j = 0; j != 4; ++j )
          va[j] = ((_BYTE *)&v24 - j)[3];
      }
      else
      {
        BYTE3(v27) = i;
      }
      v18 = BCryptHashData(phHash, (PUCHAR)va, 4u, 0);
      v13 = v18;
      if ( v18 < 0 )
      {
        v15 = 362;
        goto LABEL_31;
      }
      if ( v6 < (unsigned int)v7 )
        break;
      v18 = BCryptFinishHash(phHash, v16, v7, 0);
      v13 = v18;
      if ( v18 < 0 )
      {
        v15 = 375;
        goto LABEL_31;
      }
      v6 -= v7;
      v16 += v7;
      BCryptDestroyHash(phHash);
      v8 = v25;
      phHash = 0;
    }
    v20 = &v11[v25];
    v18 = BCryptFinishHash(phHash, v20, v7, 0);
    v13 = v18;
    if ( v18 >= 0 )
    {
      memcpy_0(v16, v20, v6);
      BCryptDestroyHash(phHash);
      phHash = 0;
LABEL_22:
      v13 = 0;
      goto LABEL_23;
    }
    v15 = 391;
LABEL_31:
    v14 = (unsigned int)v18;
  }
  else
  {
    v13 = -1073741801;
    v14 = 3221225495LL;
    v15 = 309;
  }
  DebugTraceError(v14, v10, v12, v15);
LABEL_23:
  if ( phHash )
    BCryptDestroyHash(phHash);
  if ( v11 )
    MSCryptFree(v11);
  return v13;
}

```

## disassembly

```asm
0x18002be40  mov     [rsp-40h+pbInput], r9
0x18002be45  mov     [rsp-40h+arg_10], r8d
0x18002be4a  mov     [rsp-40h+hAlgorithm], rcx
0x18002be4f  push    rbp
0x18002be50  push    rbx
0x18002be51  push    rsi
0x18002be52  push    rdi
0x18002be53  push    r12
0x18002be55  push    r13
0x18002be57  push    r14
0x18002be59  push    r15
0x18002be5b  mov     rbp, rsp
0x18002be5e  sub     rsp, 58h
0x18002be62  mov     r15d, dword ptr [rbp+arg_30]
0x18002be66  lea     eax, [rdx-1]
0x18002be69  mov     edi, edx
0x18002be6b  add     eax, r15d
0x18002be6e  xor     edx, edx
0x18002be70  mov     [rbp+phHash], 0
0x18002be78  div     edi
0x18002be7a  mov     ebx, r8d
0x18002be7d  mov     r13d, eax
0x18002be80  cmp     eax, 100h
0x18002be85  jnb     short loc_18002BE8E
0x18002be87  mov     dword ptr [rbp+arg_30], 0
0x18002be8e  lea     ecx, [rdi+r8]
0x18002be92  call    MSCryptAlloc
0x18002be97  mov     rsi, rax
0x18002be9a  test    rax, rax
0x18002be9d  jnz     short loc_18002BEB9
0x18002be9f  mov     ebx, 0C0000017h
0x18002bea4  mov     ecx, 0C0000017h
0x18002bea9  mov     r9d, 135h
0x18002beaf  call    DebugTraceError
0x18002beb4  jmp     loc_18002BFF5
0x18002beb9  mov     r12, [rbp+pbOutput]
0x18002bebd  xor     r14d, r14d
0x18002bec0  mov     [rbp+arg_8], r14d
0x18002bec4  cmp     r14d, r13d
0x18002bec7  jnb     loc_18002BFF3
0x18002becd  mov     rcx, [rbp+hAlgorithm]; hAlgorithm
0x18002bed1  lea     rdx, [rbp+phHash]; phHash
0x18002bed5  mov     [rsp+58h+dwFlags], 0; dwFlags
0x18002bedd  mov     r9d, ebx; cbHashObject
0x18002bee0  mov     [rsp+58h+cbSecret], 0; cbSecret
0x18002bee8  mov     r8, rsi; pbHashObject
0x18002beeb  mov     [rsp+58h+pbSecret], 0; pbSecret
0x18002bef4  call    cs:__imp_BCryptCreateHash
0x18002befa  mov     ebx, eax
0x18002befc  test    eax, eax
0x18002befe  js      loc_18002C034
0x18002bf04  mov     r8d, [rbp+cbInput]; cbInput
0x18002bf08  xor     r9d, r9d; dwFlags
0x18002bf0b  mov     rdx, [rbp+pbInput]; pbInput
0x18002bf0f  mov     rcx, [rbp+phHash]; hHash
0x18002bf13  call    cs:__imp_BCryptHashData
0x18002bf19  mov     ebx, eax
0x18002bf1b  test    eax, eax
0x18002bf1d  js      loc_18002C02C
0x18002bf23  cmp     r13d, 100h
0x18002bf2a  jnb     short loc_18002BF32
0x18002bf2c  mov     byte ptr [rbp+arg_30+3], r14b
0x18002bf30  jmp     short loc_18002BF4A
0x18002bf32  xor     ecx, ecx
0x18002bf34  lea     rax, [rbp+arg_8+3]
0x18002bf38  sub     rax, rcx
0x18002bf3b  mov     al, [rax]
0x18002bf3d  mov     byte ptr [rbp+rcx+arg_30], al
0x18002bf41  inc     rcx
0x18002bf44  cmp     rcx, 4
0x18002bf48  jnz     short loc_18002BF34
0x18002bf4a  mov     rcx, [rbp+phHash]; hHash
0x18002bf4e  lea     rdx, [rbp+arg_30]; pbInput
0x18002bf52  xor     r9d, r9d; dwFlags
0x18002bf55  lea     r8d, [r9+4]; cbInput
0x18002bf59  call    cs:__imp_BCryptHashData
0x18002bf5f  mov     ebx, eax
0x18002bf61  test    eax, eax
0x18002bf63  js      loc_18002C024
0x18002bf69  mov     rcx, [rbp+phHash]; hHash
0x18002bf6d  xor     r9d, r9d; dwFlags
0x18002bf70  mov     r8d, edi; cbOutput
0x18002bf73  cmp     r15d, edi
0x18002bf76  jb      short loc_18002BFB5
0x18002bf78  mov     rdx, r12; pbOutput
0x18002bf7b  call    cs:__imp_BCryptFinishHash
0x18002bf81  mov     ebx, eax
0x18002bf83  test    eax, eax
0x18002bf85  js      short loc_18002BFAA
0x18002bf87  mov     rcx, [rbp+phHash]; hHash
0x18002bf8b  sub     r15d, edi
0x18002bf8e  add     r12, rdi
0x18002bf91  call    cs:__imp_BCryptDestroyHash
0x18002bf97  mov     ebx, [rbp+arg_10]
0x18002bf9a  inc     r14d
0x18002bf9d  mov     [rbp+phHash], 0
0x18002bfa5  jmp     loc_18002BEC0
0x18002bfaa  mov     r9d, 177h
0x18002bfb0  jmp     loc_18002C03A
0x18002bfb5  mov     r14d, [rbp+arg_10]
0x18002bfb9  add     r14, rsi
0x18002bfbc  mov     rdx, r14; pbOutput
0x18002bfbf  call    cs:__imp_BCryptFinishHash
0x18002bfc5  mov     ebx, eax
0x18002bfc7  test    eax, eax
0x18002bfc9  jns     short loc_18002BFD3
0x18002bfcb  mov     r9d, 187h
0x18002bfd1  jmp     short loc_18002C03A
0x18002bfd3  mov     r8d, r15d; Size
0x18002bfd6  mov     rdx, r14; Src
0x18002bfd9  mov     rcx, r12; void *
0x18002bfdc  call    memcpy_0
0x18002bfe1  mov     rcx, [rbp+phHash]; hHash
0x18002bfe5  call    cs:__imp_BCryptDestroyHash
0x18002bfeb  mov     [rbp+phHash], 0
0x18002bff3  xor     ebx, ebx
0x18002bff5  mov     rcx, [rbp+phHash]; hHash
0x18002bff9  test    rcx, rcx
0x18002bffc  jz      short loc_18002C004
0x18002bffe  call    cs:__imp_BCryptDestroyHash
0x18002c004  test    rsi, rsi
0x18002c007  jz      short loc_18002C011
0x18002c009  mov     rcx, rsi
0x18002c00c  call    MSCryptFree
0x18002c011  mov     eax, ebx
0x18002c013  add     rsp, 58h
0x18002c017  pop     r15
0x18002c019  pop     r14
0x18002c01b  pop     r13
0x18002c01d  pop     r12
0x18002c01f  pop     rdi
0x18002c020  pop     rsi
0x18002c021  pop     rbx
0x18002c022  pop     rbp
0x18002c023  retn
0x18002c024  mov     r9d, 16Ah
0x18002c02a  jmp     short loc_18002C03A
0x18002c02c  mov     r9d, 151h
0x18002c032  jmp     short loc_18002C03A
0x18002c034  mov     r9d, 146h
0x18002c03a  mov     ecx, eax
0x18002c03c  jmp     loc_18002BEAF
```
