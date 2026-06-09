# Smb2StartSigning

- ea: `0x14008f908`
- end: `0x14008faff`
- name: `Smb2StartSigning`
- size: `503`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140092240`

## callees

- `0x14000a9e8`
- `0x14000aab4`
- `0x140038490`
- `0x140038680`
- `0x14008f908`

## import_xrefs

- `srvnet!SmbCryptoKeyedHashGetHashAlgorithmMetadata` at `0x14008f96c`
- `srvnet!SmbCryptoKeyedHashGetHashAlgorithmMetadata` at `0x14008f96c`
- `srvnet!SmbCryptoCreateSigningKey` at `0x14008f9e6`
- `srvnet!SmbCryptoCreateSigningKey` at `0x14008f9e6`
- `ksecdd!BCryptCreateHash` at `0x14008fa28`
- `ksecdd!BCryptCreateHash` at `0x14008fa28`

## pseudocode

```c
__int64 __fastcall Smb2StartSigning(__int64 a1, const void *a2, unsigned int a3)
{
  __int64 v4; // rdi
  size_t v5; // r15
  __int64 v6; // rcx
  __int64 v7; // r13
  unsigned int v8; // esi
  __int64 HashAlgorithmMetadata; // rax
  ULONG v10; // r14d
  UCHAR *SigningHashObject; // rbp
  __int64 v12; // rbx
  NTSTATUS v13; // esi
  __int128 *p_pbSecret; // rcx
  size_t v16; // r8
  __int16 v17; // [rsp+40h] [rbp-68h]
  int v18; // [rsp+44h] [rbp-64h]
  BCRYPT_HASH_HANDLE phHash; // [rsp+48h] [rbp-60h] BYREF
  BCRYPT_ALG_HANDLE hAlgorithm; // [rsp+50h] [rbp-58h]
  __int128 pbSecret; // [rsp+58h] [rbp-50h] BYREF

  v4 = *(_QWORD *)(a1 + 560);
  v5 = a3;
  v6 = *(_QWORD *)(*(_QWORD *)(a1 + 96) + 496LL);
  v7 = *(_QWORD *)(*(_QWORD *)(v4 + 32) + 320LL);
  if ( v7 )
    v8 = *(_DWORD *)(v6 + 128);
  else
    v8 = 0;
  phHash = 0;
  HashAlgorithmMetadata = SmbCryptoKeyedHashGetHashAlgorithmMetadata(*(unsigned int *)(v6 + 140));
  v10 = *(_DWORD *)(HashAlgorithmMetadata + 12);
  hAlgorithm = *(BCRYPT_ALG_HANDLE *)HashAlgorithmMetadata;
  v17 = *(_WORD *)(HashAlgorithmMetadata + 16);
  v18 = *(_DWORD *)(HashAlgorithmMetadata + 8);
  if ( !v10 )
    __int2c();
  SigningHashObject = (UCHAR *)Smb2AllocateSigningHashObject(v10);
  if ( !SigningHashObject )
    return 3221225626LL;
  v12 = 16;
  if ( *(_WORD *)(*(_QWORD *)(v4 + 32) + 288LL) < 0x300u )
  {
    v16 = v5;
    pbSecret = 0;
    if ( (unsigned int)v5 >= 0x10 )
      v16 = 16;
    memmove(&pbSecret, a2, v16);
  }
  else
  {
    v13 = SmbCryptoCreateSigningKey(a2, (unsigned int)v5, v7, v8, &pbSecret, 16);
    if ( v13 < 0 )
      goto LABEL_9;
  }
  v13 = BCryptCreateHash(hAlgorithm, &phHash, SigningHashObject, v10, (PUCHAR)&pbSecret, 0x10u, 0);
LABEL_9:
  p_pbSecret = &pbSecret;
  do
  {
    *(_BYTE *)p_pbSecret = 0;
    p_pbSecret = (__int128 *)((char *)p_pbSecret + 1);
    --v12;
  }
  while ( v12 );
  if ( v13 >= 0 )
  {
    *(_QWORD *)(*(_QWORD *)(v4 + 144) + 184LL) = phHash;
    *(_QWORD *)(*(_QWORD *)(v4 + 144) + 200LL) = SigningHashObject;
    *(_DWORD *)(*(_QWORD *)(v4 + 144) + 192LL) = v10;
    *(_DWORD *)(*(_QWORD *)(v4 + 144) + 196LL) = v18;
    *(_WORD *)(*(_QWORD *)(v4 + 144) + 208LL) = v17;
    return 0;
  }
  else
  {
    Smb2DeallocateSigningHashObject(SigningHashObject);
    return (unsigned int)v13;
  }
}

```

## disassembly

```asm
0x14008f908  mov     [rsp+arg_18], rbx
0x14008f90d  push    rbp
0x14008f90e  push    rsi
0x14008f90f  push    rdi
0x14008f910  push    r12
0x14008f912  push    r13
0x14008f914  push    r14
0x14008f916  push    r15
0x14008f918  sub     rsp, 70h
0x14008f91c  mov     rax, cs:__security_cookie
0x14008f923  xor     rax, rsp
0x14008f926  mov     [rsp+0A8h+var_40], rax
0x14008f92b  mov     rax, [rcx+60h]
0x14008f92f  mov     r12, rdx
0x14008f932  mov     rdi, [rcx+230h]
0x14008f939  mov     r15d, r8d
0x14008f93c  mov     rcx, [rax+1F0h]
0x14008f943  mov     rax, [rdi+20h]
0x14008f947  mov     r13, [rax+140h]
0x14008f94e  test    r13, r13
0x14008f951  jz      loc_14008FA40
0x14008f957  mov     esi, [rcx+80h]
0x14008f95d  mov     [rsp+0A8h+phHash], 0
0x14008f966  mov     ecx, [rcx+8Ch]
0x14008f96c  call    cs:__imp_SmbCryptoKeyedHashGetHashAlgorithmMetadata
0x14008f973  nop     dword ptr [rax+rax+00h]
0x14008f978  mov     rcx, [rax]
0x14008f97b  mov     r14d, [rax+0Ch]
0x14008f97f  mov     [rsp+0A8h+hAlgorithm], rcx
0x14008f984  mov     ecx, [rax+8]
0x14008f987  movzx   eax, word ptr [rax+10h]
0x14008f98b  mov     [rsp+0A8h+var_68], ax
0x14008f990  mov     [rsp+0A8h+var_64], ecx
0x14008f994  test    r14d, r14d
0x14008f997  jz      loc_14008FA82
0x14008f99d  mov     ecx, r14d
0x14008f9a0  call    Smb2AllocateSigningHashObject
0x14008f9a5  mov     rbp, rax
0x14008f9a8  test    rax, rax
0x14008f9ab  jz      loc_14008FA47
0x14008f9b1  mov     rax, [rdi+20h]
0x14008f9b5  mov     ecx, 300h
0x14008f9ba  mov     ebx, 10h
0x14008f9bf  cmp     [rax+120h], cx
0x14008f9c6  jb      loc_14008FA89
0x14008f9cc  lea     rax, [rsp+0A8h+var_50]
0x14008f9d1  mov     [rsp+0A8h+cbSecret], ebx
0x14008f9d5  mov     r9d, esi
0x14008f9d8  mov     [rsp+0A8h+pbSecret], rax
0x14008f9dd  mov     r8, r13
0x14008f9e0  mov     edx, r15d
0x14008f9e3  mov     rcx, r12
0x14008f9e6  call    cs:__imp_SmbCryptoCreateSigningKey
0x14008f9ed  nop     dword ptr [rax+rax+00h]
0x14008f9f2  mov     esi, eax
0x14008f9f4  lea     rcx, [rsp+0A8h+var_50]
0x14008f9f9  test    esi, esi
0x14008f9fb  mov     eax, ebx
0x14008f9fd  cmovs   eax, r15d
0x14008fa01  cmovs   rcx, r12
0x14008fa05  js      short loc_14008FA36
0x14008fa07  mov     [rsp+0A8h+dwFlags], 0; dwFlags
0x14008fa0f  lea     rdx, [rsp+0A8h+phHash]; phHash
0x14008fa14  mov     [rsp+0A8h+cbSecret], eax; cbSecret
0x14008fa18  mov     r9d, r14d; cbHashObject
0x14008fa1b  mov     [rsp+0A8h+pbSecret], rcx; pbSecret
0x14008fa20  mov     r8, rbp; pbHashObject
0x14008fa23  mov     rcx, [rsp+0A8h+hAlgorithm]; hAlgorithm
0x14008fa28  call    cs:__imp_BCryptCreateHash
0x14008fa2f  nop     dword ptr [rax+rax+00h]
0x14008fa34  mov     esi, eax
0x14008fa36  lea     rcx, [rsp+0A8h+var_50]
0x14008fa3b  jmp     loc_14009BBE9
0x14008fa40  xor     esi, esi
0x14008fa42  jmp     loc_14008F95D
0x14008fa47  mov     eax, 0C000009Ah
0x14008fa4c  jmp     short loc_14008FA5C
0x14008fa4e  test    esi, esi
0x14008fa50  jns     short loc_14008FAA5
0x14008fa52  mov     rcx, rbp
0x14008fa55  call    Smb2DeallocateSigningHashObject
0x14008fa5a  mov     eax, esi
0x14008fa5c  mov     rcx, [rsp+0A8h+var_40]
0x14008fa61  xor     rcx, rsp; StackCookie
0x14008fa64  call    __security_check_cookie
0x14008fa69  mov     rbx, [rsp+0A8h+arg_18]
0x14008fa71  add     rsp, 70h
0x14008fa75  pop     r15
0x14008fa77  pop     r14
0x14008fa79  pop     r13
0x14008fa7b  pop     r12
0x14008fa7d  pop     rdi
0x14008fa7e  pop     rsi
0x14008fa7f  pop     rbp
0x14008fa80  retn
0x14008fa82  int     2Ch; Windows NT - assertion failure
0x14008fa84  jmp     loc_14008F99D
0x14008fa89  xorps   xmm0, xmm0
0x14008fa8c  mov     r8, r15; Size
0x14008fa8f  movups  [rsp+0A8h+var_50], xmm0
0x14008fa94  cmp     r15d, ebx
0x14008fa97  jb      loc_14009BBD0
0x14008fa9d  mov     r8, rbx
0x14008faa0  jmp     loc_14009BBD0
0x14008faa5  mov     rcx, [rdi+90h]
0x14008faac  mov     rax, [rsp+0A8h+phHash]
0x14008fab1  mov     [rcx+0B8h], rax
0x14008fab8  mov     rax, [rdi+90h]
0x14008fabf  mov     ecx, [rsp+0A8h+var_64]
0x14008fac3  mov     [rax+0C8h], rbp
0x14008faca  mov     rax, [rdi+90h]
0x14008fad1  mov     [rax+0C0h], r14d
0x14008fad8  mov     rax, [rdi+90h]
0x14008fadf  mov     [rax+0C4h], ecx
0x14008fae5  mov     rax, [rdi+90h]
0x14008faec  movzx   ecx, [rsp+0A8h+var_68]
0x14008faf1  mov     [rax+0D0h], cx
0x14008faf8  xor     eax, eax
0x14008fafa  jmp     loc_14008FA5C
0x14009bbd0  mov     rdx, r12; Src
0x14009bbd3  lea     rcx, [rsp+0A8h+var_50]; void *
0x14009bbd8  call    memmove
0x14009bbdd  lea     rcx, [rsp+0A8h+var_50]
0x14009bbe2  mov     eax, ebx
0x14009bbe4  jmp     loc_14008FA07
0x14009bbe9  mov     byte ptr [rcx], 0
0x14009bbec  inc     rcx
0x14009bbef  sub     rbx, 1
0x14009bbf3  jnz     short loc_14009BBE9
0x14009bbf5  jmp     loc_14008FA4E
```
