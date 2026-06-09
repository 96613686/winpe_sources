# MarshalData(unsigned __int64,unsigned __int64 *,_MARSHAL_FUNCTION,ulong *,uchar * *,ulong,...)

- ea: `0x180015c74`
- end: `0x180015f27`
- name: `?MarshalData@@YAJ_KPEA_KW4_MARSHAL_FUNCTION@@PEAKPEAPEAEKZZ`
- size: `691`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800156a4`

## callees

- `0x180007988`
- `0x180007994`
- `0x180008c66`
- `0x180015c74`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015d74`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015d87`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015d97`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015ddc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015def`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015e02`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015d74`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015d87`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015d97`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015ddc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015def`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015e02`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x180015d64`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x180015d64`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x180015dcc`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x180015dcc`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptSignHashW` at `0x180015e4c`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptSignHashW` at `0x180015e8f`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptSignHashW` at `0x180015e4c`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptSignHashW` at `0x180015e8f`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x180015ee5`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x180015ee5`

## pseudocode

```c
__int64 __fastcall MarshalData(HCRYPTPROV a1, HCRYPTHASH *a2, int a3, DWORD *a4, BYTE **a5, int a6, char a7)
{
  int v7; // r10d
  DWORD *v8; // rcx
  DWORD v10; // esi
  int v11; // ebx
  __int64 result; // rax
  BYTE *v13; // rdi
  BYTE **v14; // r15
  BYTE *v15; // r14
  signed int LastError; // ebx
  BYTE *v17; // rsi
  int v18; // r13d
  const void **v19; // r15
  __int64 v20; // rbx
  signed int v21; // eax
  DWORD v22; // r8d
  signed int v23; // eax
  DWORD pdwSigLen; // [rsp+30h] [rbp-28h] BYREF
  HCRYPTHASH hHash; // [rsp+38h] [rbp-20h] BYREF
  BYTE *pbData; // [rsp+40h] [rbp-18h]

  v7 = a6;
  v8 = (DWORD *)&a7;
  hHash = 0;
  v10 = 0;
  pdwSigLen = 0;
  v11 = a3;
  pbData = 0;
  while ( v7 )
  {
    if ( *v8 > ~v10 )
      return 2147942487LL;
    v10 += *v8;
    --v7;
    v8 += 4;
  }
  v13 = 0;
  v14 = a5;
  v15 = (BYTE *)operator new[](v10);
  pbData = v15;
  if ( !v15 )
  {
    LastError = -2147024882;
    v17 = 0;
    goto LABEL_34;
  }
  v18 = a6;
  if ( a6 )
  {
    v19 = (const void **)&a7;
    do
    {
      v20 = *(unsigned int *)v19;
      v19 += 2;
      memcpy_0(v15, *(v19 - 1), (unsigned int)v20);
      v15 += v20;
      --v18;
    }
    while ( v18 );
    v14 = a5;
    v11 = a3;
  }
  if ( !v11 )
  {
    *a4 = v10;
    result = 0;
    *v14 = pbData;
    return result;
  }
  if ( !CryptCreateHash(a1, 0x800Cu, 0, 0, &hHash) )
  {
    if ( (GetLastError() & 0x1FFF0000) != 0 )
    {
      LastError = GetLastError();
    }
    else
    {
      v21 = GetLastError();
      LastError = v21;
      if ( v21 > 0 )
        LastError = (unsigned __int16)v21 | 0x80070000;
    }
    v17 = pbData;
    goto LABEL_34;
  }
  v22 = v10;
  v17 = pbData;
  if ( !CryptHashData(hHash, pbData, v22, 0) )
  {
LABEL_21:
    if ( (GetLastError() & 0x1FFF0000) != 0 )
    {
      LastError = GetLastError();
    }
    else
    {
      v23 = GetLastError();
      LastError = v23;
      if ( v23 > 0 )
        LastError = (unsigned __int16)v23 | 0x80070000;
    }
    goto LABEL_34;
  }
  if ( v11 != 2 )
  {
LABEL_32:
    LastError = 0;
    if ( a2 )
    {
      *a2 = hHash;
      hHash = 0;
    }
    goto LABEL_34;
  }
  if ( !CryptSignHashW(hHash, 2u, 0, 0, 0, &pdwSigLen) )
    goto LABEL_21;
  if ( *a4 )
  {
    if ( *a4 >= pdwSigLen )
    {
      v13 = *v14;
LABEL_30:
      if ( !CryptSignHashW(hHash, 2u, 0, 0, v13, &pdwSigLen) )
        goto LABEL_21;
      *a4 = pdwSigLen;
      *v14 = v13;
      goto LABEL_32;
    }
    LastError = -2147024774;
  }
  else
  {
    v13 = (BYTE *)operator new[](pdwSigLen);
    if ( v13 )
      goto LABEL_30;
    LastError = -2147024882;
  }
LABEL_34:
  operator delete(v17);
  if ( LastError < 0 && v13 != *v14 )
    operator delete(v13);
  if ( hHash )
    CryptDestroyHash(hHash);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x180015c74  mov     [rsp-40h+arg_10], r8d
0x180015c79  mov     [rsp-40h+arg_8], rdx
0x180015c7e  mov     [rsp-40h+hProv], rcx
0x180015c83  push    rbp
0x180015c84  push    rbx
0x180015c85  push    rsi
0x180015c86  push    rdi
0x180015c87  push    r12
0x180015c89  push    r13
0x180015c8b  push    r14
0x180015c8d  push    r15
0x180015c8f  mov     rbp, rsp
0x180015c92  sub     rsp, 58h
0x180015c96  mov     r10d, [rbp+arg_28]
0x180015c9a  lea     rcx, [rbp+arg_30]
0x180015c9e  xor     r13d, r13d
0x180015ca1  mov     r12, r9
0x180015ca4  mov     [rbp+hHash], r13
0x180015ca8  mov     esi, r13d
0x180015cab  mov     [rbp+var_28], r13d
0x180015caf  mov     ebx, r8d
0x180015cb2  mov     [rbp+pbData], r13
0x180015cb6  test    r10d, r10d
0x180015cb9  jz      short loc_180015CD8
0x180015cbb  mov     eax, esi
0x180015cbd  not     eax
0x180015cbf  cmp     [rcx], eax
0x180015cc1  ja      short loc_180015CCE
0x180015cc3  add     esi, [rcx]
0x180015cc5  dec     r10d
0x180015cc8  add     rcx, 10h
0x180015ccc  jmp     short loc_180015CB6
0x180015cce  mov     eax, 80070057h
0x180015cd3  jmp     loc_180015EF3
0x180015cd8  mov     ecx, esi; unsigned __int64
0x180015cda  mov     rdi, r13
0x180015cdd  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180015ce2  mov     r15, [rbp+arg_20]
0x180015ce6  mov     r14, rax
0x180015ce9  mov     [rbp+pbData], rax
0x180015ced  test    rax, rax
0x180015cf0  jnz     short loc_180015CFF
0x180015cf2  mov     ebx, 8007000Eh
0x180015cf7  mov     rsi, rax
0x180015cfa  jmp     loc_180015EC3
0x180015cff  mov     r13d, [rbp+arg_28]
0x180015d03  test    r13d, r13d
0x180015d06  jz      short loc_180015D36
0x180015d08  lea     r15, [rbp+arg_30]
0x180015d0c  lea     rax, [r15+8]
0x180015d10  mov     rcx, r14; void *
0x180015d13  mov     ebx, [rax-8]
0x180015d16  lea     r15, [rax+8]
0x180015d1a  mov     rdx, [r15-8]; Src
0x180015d1e  mov     r8d, ebx; Size
0x180015d21  call    memcpy_0
0x180015d26  add     r14, rbx
0x180015d29  add     r13d, 0FFFFFFFFh
0x180015d2d  jnz     short loc_180015D0C
0x180015d2f  mov     r15, [rbp+arg_20]
0x180015d33  mov     ebx, [rbp+arg_10]
0x180015d36  test    ebx, ebx
0x180015d38  jnz     short loc_180015D4C
0x180015d3a  mov     [r12], esi
0x180015d3e  xor     eax, eax
0x180015d40  mov     rsi, [rbp+pbData]
0x180015d44  mov     [r15], rsi
0x180015d47  jmp     loc_180015EF3
0x180015d4c  mov     rcx, [rbp+hProv]; hProv
0x180015d50  lea     rax, [rbp+hHash]
0x180015d54  xor     r9d, r9d; dwFlags
0x180015d57  mov     [rsp+58h+phHash], rax; phHash
0x180015d5c  xor     r8d, r8d; hKey
0x180015d5f  mov     edx, 800Ch; Algid
0x180015d64  call    cs:__imp_CryptCreateHash
0x180015d6b  nop     dword ptr [rax+rax+00h]
0x180015d70  test    eax, eax
0x180015d72  jnz     short loc_180015DBB
0x180015d74  call    cs:__imp_GetLastError
0x180015d7b  nop     dword ptr [rax+rax+00h]
0x180015d80  test    eax, 1FFF0000h
0x180015d85  jz      short loc_180015D97
0x180015d87  call    cs:__imp_GetLastError
0x180015d8e  nop     dword ptr [rax+rax+00h]
0x180015d93  mov     ebx, eax
0x180015d95  jmp     short loc_180015DB2
0x180015d97  call    cs:__imp_GetLastError
0x180015d9e  nop     dword ptr [rax+rax+00h]
0x180015da3  mov     ebx, eax
0x180015da5  test    eax, eax
0x180015da7  jle     short loc_180015DB2
0x180015da9  movzx   ebx, ax
0x180015dac  or      ebx, 80070000h
0x180015db2  mov     rsi, [rbp+pbData]
0x180015db6  jmp     loc_180015EC3
0x180015dbb  mov     rcx, [rbp+hHash]; hHash
0x180015dbf  mov     r8d, esi; dwDataLen
0x180015dc2  mov     rsi, [rbp+pbData]
0x180015dc6  xor     r9d, r9d; dwFlags
0x180015dc9  mov     rdx, rsi; pbData
0x180015dcc  call    cs:__imp_CryptHashData
0x180015dd3  nop     dword ptr [rax+rax+00h]
0x180015dd8  test    eax, eax
0x180015dda  jnz     short loc_180015E26
0x180015ddc  call    cs:__imp_GetLastError
0x180015de3  nop     dword ptr [rax+rax+00h]
0x180015de8  test    eax, 1FFF0000h
0x180015ded  jz      short loc_180015E02
0x180015def  call    cs:__imp_GetLastError
0x180015df6  nop     dword ptr [rax+rax+00h]
0x180015dfb  mov     ebx, eax
0x180015dfd  jmp     loc_180015EC3
0x180015e02  call    cs:__imp_GetLastError
0x180015e09  nop     dword ptr [rax+rax+00h]
0x180015e0e  mov     ebx, eax
0x180015e10  test    eax, eax
0x180015e12  jle     loc_180015EC3
0x180015e18  movzx   ebx, ax
0x180015e1b  or      ebx, 80070000h
0x180015e21  jmp     loc_180015EC3
0x180015e26  mov     r14d, 2
0x180015e2c  cmp     ebx, r14d
0x180015e2f  jnz     short loc_180015EAD
0x180015e31  mov     rcx, [rbp+hHash]; hHash
0x180015e35  lea     rax, [rbp+var_28]
0x180015e39  mov     [rsp+58h+pdwSigLen], rax; pdwSigLen
0x180015e3e  xor     r9d, r9d; dwFlags
0x180015e41  xor     r8d, r8d; szDescription
0x180015e44  mov     [rsp+58h+phHash], rdi; pbSignature
0x180015e49  mov     edx, r14d; dwKeySpec
0x180015e4c  call    cs:__imp_CryptSignHashW
0x180015e53  nop     dword ptr [rax+rax+00h]
0x180015e58  test    eax, eax
0x180015e5a  jz      short loc_180015DDC
0x180015e5c  mov     eax, [r12]
0x180015e60  test    eax, eax
0x180015e62  jz      loc_180015F0C
0x180015e68  cmp     eax, [rbp+var_28]
0x180015e6b  jb      loc_180015F05
0x180015e71  mov     rdi, [r15]
0x180015e74  mov     rcx, [rbp+hHash]; hHash
0x180015e78  lea     rax, [rbp+var_28]
0x180015e7c  mov     [rsp+58h+pdwSigLen], rax; pdwSigLen
0x180015e81  xor     r9d, r9d; dwFlags
0x180015e84  xor     r8d, r8d; szDescription
0x180015e87  mov     [rsp+58h+phHash], rdi; pbSignature
0x180015e8c  mov     edx, r14d; dwKeySpec
0x180015e8f  call    cs:__imp_CryptSignHashW
0x180015e96  nop     dword ptr [rax+rax+00h]
0x180015e9b  test    eax, eax
0x180015e9d  jz      loc_180015DDC
0x180015ea3  mov     eax, [rbp+var_28]
0x180015ea6  mov     [r12], eax
0x180015eaa  mov     [r15], rdi
0x180015ead  mov     rdx, [rbp+arg_8]
0x180015eb1  xor     ebx, ebx
0x180015eb3  test    rdx, rdx
0x180015eb6  jz      short loc_180015EC3
0x180015eb8  mov     rax, [rbp+hHash]
0x180015ebc  mov     [rdx], rax
0x180015ebf  mov     [rbp+hHash], rbx
0x180015ec3  mov     rcx, rsi; Block
0x180015ec6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180015ecb  test    ebx, ebx
0x180015ecd  jns     short loc_180015EDC
0x180015ecf  cmp     rdi, [r15]
0x180015ed2  jz      short loc_180015EDC
0x180015ed4  mov     rcx, rdi; Block
0x180015ed7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180015edc  mov     rcx, [rbp+hHash]; hHash
0x180015ee0  test    rcx, rcx
0x180015ee3  jz      short loc_180015EF1
0x180015ee5  call    cs:__imp_CryptDestroyHash
0x180015eec  nop     dword ptr [rax+rax+00h]
0x180015ef1  mov     eax, ebx
0x180015ef3  add     rsp, 58h
0x180015ef7  pop     r15
0x180015ef9  pop     r14
0x180015efb  pop     r13
0x180015efd  pop     r12
0x180015eff  pop     rdi
0x180015f00  pop     rsi
0x180015f01  pop     rbx
0x180015f02  pop     rbp
0x180015f03  retn
0x180015f05  mov     ebx, 8007007Ah
0x180015f0a  jmp     short loc_180015EC3
0x180015f0c  mov     ecx, [rbp+var_28]; unsigned __int64
0x180015f0f  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180015f14  mov     rdi, rax
0x180015f17  test    rax, rax
0x180015f1a  jnz     loc_180015E74
0x180015f20  mov     ebx, 8007000Eh
0x180015f25  jmp     short loc_180015EC3
```
