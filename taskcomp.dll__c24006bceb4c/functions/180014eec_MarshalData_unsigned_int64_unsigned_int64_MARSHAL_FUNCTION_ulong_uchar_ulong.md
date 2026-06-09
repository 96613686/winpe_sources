# MarshalData(unsigned __int64,unsigned __int64 *,_MARSHAL_FUNCTION,ulong *,uchar * *,ulong,...)

- ea: `0x180014eec`
- end: `0x18001515c`
- name: `?MarshalData@@YAJ_KPEA_KW4_MARSHAL_FUNCTION@@PEAKPEAPEAEKZZ`
- size: `624`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800149a4`

## callees

- `0x1800074c8`
- `0x1800074d4`
- `0x1800087a6`
- `0x180014eec`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014fe6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014ff3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014ffd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015036`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015043`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015050`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014fe6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014ff3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014ffd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015036`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015043`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015050`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x180014fdc`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x180014fdc`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x18001502c`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x18001502c`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptSignHashW` at `0x180015094`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptSignHashW` at `0x1800150d1`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptSignHashW` at `0x180015094`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptSignHashW` at `0x1800150d1`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x180015121`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x180015121`

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
0x180014eec  mov     [rsp-40h+arg_10], r8d
0x180014ef1  mov     [rsp-40h+arg_8], rdx
0x180014ef6  mov     [rsp-40h+hProv], rcx
0x180014efb  push    rbp
0x180014efc  push    rbx
0x180014efd  push    rsi
0x180014efe  push    rdi
0x180014eff  push    r12
0x180014f01  push    r13
0x180014f03  push    r14
0x180014f05  push    r15
0x180014f07  mov     rbp, rsp
0x180014f0a  sub     rsp, 58h
0x180014f0e  mov     r10d, [rbp+arg_28]
0x180014f12  lea     rcx, [rbp+arg_30]
0x180014f16  xor     r13d, r13d
0x180014f19  mov     r12, r9
0x180014f1c  mov     [rbp+hHash], r13
0x180014f20  mov     esi, r13d
0x180014f23  mov     [rbp+var_28], r13d
0x180014f27  mov     ebx, r8d
0x180014f2a  mov     [rbp+pbData], r13
0x180014f2e  test    r10d, r10d
0x180014f31  jz      short loc_180014F50
0x180014f33  mov     eax, esi
0x180014f35  not     eax
0x180014f37  cmp     [rcx], eax
0x180014f39  ja      short loc_180014F46
0x180014f3b  add     esi, [rcx]
0x180014f3d  dec     r10d
0x180014f40  add     rcx, 10h
0x180014f44  jmp     short loc_180014F2E
0x180014f46  mov     eax, 80070057h
0x180014f4b  jmp     loc_180015129
0x180014f50  mov     ecx, esi; unsigned __int64
0x180014f52  mov     rdi, r13
0x180014f55  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180014f5a  mov     r15, [rbp+arg_20]
0x180014f5e  mov     r14, rax
0x180014f61  mov     [rbp+pbData], rax
0x180014f65  test    rax, rax
0x180014f68  jnz     short loc_180014F77
0x180014f6a  mov     ebx, 8007000Eh
0x180014f6f  mov     rsi, rax
0x180014f72  jmp     loc_1800150FF
0x180014f77  mov     r13d, [rbp+arg_28]
0x180014f7b  test    r13d, r13d
0x180014f7e  jz      short loc_180014FAE
0x180014f80  lea     r15, [rbp+arg_30]
0x180014f84  lea     rax, [r15+8]
0x180014f88  mov     rcx, r14; void *
0x180014f8b  mov     ebx, [rax-8]
0x180014f8e  lea     r15, [rax+8]
0x180014f92  mov     rdx, [r15-8]; Src
0x180014f96  mov     r8d, ebx; Size
0x180014f99  call    memcpy_0
0x180014f9e  add     r14, rbx
0x180014fa1  add     r13d, 0FFFFFFFFh
0x180014fa5  jnz     short loc_180014F84
0x180014fa7  mov     r15, [rbp+arg_20]
0x180014fab  mov     ebx, [rbp+arg_10]
0x180014fae  test    ebx, ebx
0x180014fb0  jnz     short loc_180014FC4
0x180014fb2  mov     [r12], esi
0x180014fb6  xor     eax, eax
0x180014fb8  mov     rsi, [rbp+pbData]
0x180014fbc  mov     [r15], rsi
0x180014fbf  jmp     loc_180015129
0x180014fc4  mov     rcx, [rbp+hProv]; hProv
0x180014fc8  lea     rax, [rbp+hHash]
0x180014fcc  xor     r9d, r9d; dwFlags
0x180014fcf  mov     [rsp+58h+phHash], rax; phHash
0x180014fd4  xor     r8d, r8d; hKey
0x180014fd7  mov     edx, 800Ch; Algid
0x180014fdc  call    cs:__imp_CryptCreateHash
0x180014fe2  test    eax, eax
0x180014fe4  jnz     short loc_18001501B
0x180014fe6  call    cs:__imp_GetLastError
0x180014fec  test    eax, 1FFF0000h
0x180014ff1  jz      short loc_180014FFD
0x180014ff3  call    cs:__imp_GetLastError
0x180014ff9  mov     ebx, eax
0x180014ffb  jmp     short loc_180015012
0x180014ffd  call    cs:__imp_GetLastError
0x180015003  mov     ebx, eax
0x180015005  test    eax, eax
0x180015007  jle     short loc_180015012
0x180015009  movzx   ebx, ax
0x18001500c  or      ebx, 80070000h
0x180015012  mov     rsi, [rbp+pbData]
0x180015016  jmp     loc_1800150FF
0x18001501b  mov     rcx, [rbp+hHash]; hHash
0x18001501f  mov     r8d, esi; dwDataLen
0x180015022  mov     rsi, [rbp+pbData]
0x180015026  xor     r9d, r9d; dwFlags
0x180015029  mov     rdx, rsi; pbData
0x18001502c  call    cs:__imp_CryptHashData
0x180015032  test    eax, eax
0x180015034  jnz     short loc_18001506E
0x180015036  call    cs:__imp_GetLastError
0x18001503c  test    eax, 1FFF0000h
0x180015041  jz      short loc_180015050
0x180015043  call    cs:__imp_GetLastError
0x180015049  mov     ebx, eax
0x18001504b  jmp     loc_1800150FF
0x180015050  call    cs:__imp_GetLastError
0x180015056  mov     ebx, eax
0x180015058  test    eax, eax
0x18001505a  jle     loc_1800150FF
0x180015060  movzx   ebx, ax
0x180015063  or      ebx, 80070000h
0x180015069  jmp     loc_1800150FF
0x18001506e  mov     r14d, 2
0x180015074  cmp     ebx, r14d
0x180015077  jnz     short loc_1800150E9
0x180015079  mov     rcx, [rbp+hHash]; hHash
0x18001507d  lea     rax, [rbp+var_28]
0x180015081  mov     [rsp+58h+pdwSigLen], rax; pdwSigLen
0x180015086  xor     r9d, r9d; dwFlags
0x180015089  xor     r8d, r8d; szDescription
0x18001508c  mov     [rsp+58h+phHash], rdi; pbSignature
0x180015091  mov     edx, r14d; dwKeySpec
0x180015094  call    cs:__imp_CryptSignHashW
0x18001509a  test    eax, eax
0x18001509c  jz      short loc_180015036
0x18001509e  mov     eax, [r12]
0x1800150a2  test    eax, eax
0x1800150a4  jz      loc_180015141
0x1800150aa  cmp     eax, [rbp+var_28]
0x1800150ad  jb      loc_18001513A
0x1800150b3  mov     rdi, [r15]
0x1800150b6  mov     rcx, [rbp+hHash]; hHash
0x1800150ba  lea     rax, [rbp+var_28]
0x1800150be  mov     [rsp+58h+pdwSigLen], rax; pdwSigLen
0x1800150c3  xor     r9d, r9d; dwFlags
0x1800150c6  xor     r8d, r8d; szDescription
0x1800150c9  mov     [rsp+58h+phHash], rdi; pbSignature
0x1800150ce  mov     edx, r14d; dwKeySpec
0x1800150d1  call    cs:__imp_CryptSignHashW
0x1800150d7  test    eax, eax
0x1800150d9  jz      loc_180015036
0x1800150df  mov     eax, [rbp+var_28]
0x1800150e2  mov     [r12], eax
0x1800150e6  mov     [r15], rdi
0x1800150e9  mov     rdx, [rbp+arg_8]
0x1800150ed  xor     ebx, ebx
0x1800150ef  test    rdx, rdx
0x1800150f2  jz      short loc_1800150FF
0x1800150f4  mov     rax, [rbp+hHash]
0x1800150f8  mov     [rdx], rax
0x1800150fb  mov     [rbp+hHash], rbx
0x1800150ff  mov     rcx, rsi; Block
0x180015102  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180015107  test    ebx, ebx
0x180015109  jns     short loc_180015118
0x18001510b  cmp     rdi, [r15]
0x18001510e  jz      short loc_180015118
0x180015110  mov     rcx, rdi; Block
0x180015113  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180015118  mov     rcx, [rbp+hHash]; hHash
0x18001511c  test    rcx, rcx
0x18001511f  jz      short loc_180015127
0x180015121  call    cs:__imp_CryptDestroyHash
0x180015127  mov     eax, ebx
0x180015129  add     rsp, 58h
0x18001512d  pop     r15
0x18001512f  pop     r14
0x180015131  pop     r13
0x180015133  pop     r12
0x180015135  pop     rdi
0x180015136  pop     rsi
0x180015137  pop     rbx
0x180015138  pop     rbp
0x180015139  retn
0x18001513a  mov     ebx, 8007007Ah
0x18001513f  jmp     short loc_1800150FF
0x180015141  mov     ecx, [rbp+var_28]; unsigned __int64
0x180015144  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180015149  mov     rdi, rax
0x18001514c  test    rax, rax
0x18001514f  jnz     loc_1800150B6
0x180015155  mov     ebx, 8007000Eh
0x18001515a  jmp     short loc_1800150FF
```
