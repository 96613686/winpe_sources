# TlsGetBCryptHashProvider(_eTlsHashAlgorithm,void * *,ulong *)

- ea: `0x18003a440`
- end: `0x18003a530`
- name: `?TlsGetBCryptHashProvider@@YAKW4_eTlsHashAlgorithm@@PEAPEAXPEAK@Z`
- size: `240`
- prototype: `unsigned int __fastcall(enum _eTlsHashAlgorithm, void **, unsigned int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180055510`

## callees

- `0x18003a440`

## import_xrefs

- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18008ecdf`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18008ecdf`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18008eca7`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18008eca7`

## pseudocode

```c
__int64 __fastcall TlsGetBCryptHashProvider(enum _eTlsHashAlgorithm a1, void **a2, unsigned int *a3)
{
  int v3; // edi
  __int64 i; // rax
  __int64 v8; // rcx
  BCRYPT_ALG_HANDLE v9; // rax
  __int64 v10; // rcx
  unsigned int v11; // ebx
  unsigned int v12; // ecx
  BCRYPT_ALG_HANDLE v13; // rax
  void *v15; // rdi
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+48h] [rbp+10h] BYREF

  v3 = g_dwHashInfoTotalCount;
  phAlgorithm = 0;
  for ( i = 0; (unsigned int)i < g_dwHashInfoTotalCount; i = (unsigned int)(i + 1) )
  {
    v8 = g_pHashInfo[i];
    if ( v8 && *(_DWORD *)(v8 + 20) == a1 )
    {
      v3 = i;
      break;
    }
  }
  if ( v3 < 0 || v3 >= g_dwHashInfoTotalCount )
  {
    v3 = 0;
  }
  else
  {
    if ( v3 == 1 )
    {
      v9 = g_hMD5Provider;
      goto LABEL_12;
    }
    if ( v3 == 2 )
    {
      v9 = g_hSHAProvider;
      goto LABEL_12;
    }
  }
  v9 = (BCRYPT_ALG_HANDLE)qword_1800AE610[v3];
LABEL_12:
  phAlgorithm = v9;
  if ( v3 < (unsigned int)g_dwHashInfoTotalCount && (_mm_lfence(), (v10 = g_pHashInfo[v3]) != 0) )
  {
    v11 = *(_DWORD *)(v10 + 8);
    if ( !phAlgorithm )
    {
      if ( !*(_QWORD *)v10 )
      {
        v12 = 1359;
        goto LABEL_16;
      }
      v12 = BCryptOpenAlgorithmProvider(&phAlgorithm, *(LPCWSTR *)v10, 0, 0);
      if ( v12 )
        goto LABEL_16;
      v15 = (void *)_InterlockedCompareExchange64(
                      (volatile signed __int64 *)&_ImageBase[4 * v3 + 357128],
                      (signed __int64)phAlgorithm,
                      0);
      if ( v15 )
      {
        BCryptCloseAlgorithmProvider(phAlgorithm, 0);
        phAlgorithm = v15;
      }
    }
    v12 = 0;
  }
  else
  {
    v11 = 0;
    v12 = 1168;
  }
LABEL_16:
  v13 = phAlgorithm;
  *a3 = v11;
  *a2 = v13;
  return v12;
}

```

## disassembly

```asm
0x18003a440  mov     [rsp+arg_0], rbx
0x18003a445  mov     [rsp+arg_10], rsi
0x18003a44a  push    rdi
0x18003a44b  push    r14
0x18003a44d  push    r15
0x18003a44f  sub     rsp, 20h
0x18003a453  mov     r9d, cs:g_dwHashInfoTotalCount
0x18003a45a  lea     r15, __ImageBase
0x18003a461  mov     edi, r9d
0x18003a464  mov     [rsp+38h+phAlgorithm], 0
0x18003a46d  mov     rsi, r8
0x18003a470  mov     r14, rdx
0x18003a473  mov     r10d, ecx
0x18003a476  xor     eax, eax
0x18003a478  cmp     eax, r9d
0x18003a47b  jnb     short loc_18003A496
0x18003a47d  mov     rcx, rva g_pHashInfo[r15+rax*8]
0x18003a485  test    rcx, rcx
0x18003a488  jz      short loc_18003A490
0x18003a48a  cmp     [rcx+14h], r10d
0x18003a48e  jz      short loc_18003A494
0x18003a490  inc     eax
0x18003a492  jmp     short loc_18003A478
0x18003a494  mov     edi, eax
0x18003a496  test    edi, edi
0x18003a498  js      short loc_18003A519
0x18003a49a  cmp     edi, r9d
0x18003a49d  jge     short loc_18003A519
0x18003a49f  mov     ecx, edi
0x18003a4a1  sub     ecx, 1
0x18003a4a4  jz      short loc_18003A4FE
0x18003a4a6  cmp     ecx, 1
0x18003a4a9  jz      short loc_18003A510
0x18003a4ab  mov     eax, edi
0x18003a4ad  mov     rax, rva qword_1800AE610[r15+rax*8]
0x18003a4b5  mov     [rsp+38h+phAlgorithm], rax
0x18003a4ba  cmp     edi, r9d
0x18003a4bd  jnb     short loc_18003A507
0x18003a4bf  lfence
0x18003a4c2  mov     eax, edi
0x18003a4c4  mov     rcx, rva g_pHashInfo[r15+rax*8]
0x18003a4cc  test    rcx, rcx
0x18003a4cf  jz      short loc_18003A507
0x18003a4d1  cmp     [rsp+38h+phAlgorithm], 0
0x18003a4d7  mov     ebx, [rcx+8]
0x18003a4da  jz      short loc_18003A51D
0x18003a4dc  xor     ecx, ecx
0x18003a4de  mov     rax, [rsp+38h+phAlgorithm]
0x18003a4e3  mov     [rsi], ebx
0x18003a4e5  mov     rbx, [rsp+38h+arg_0]
0x18003a4ea  mov     rsi, [rsp+38h+arg_10]
0x18003a4ef  mov     [r14], rax
0x18003a4f2  mov     eax, ecx
0x18003a4f4  add     rsp, 20h
0x18003a4f8  pop     r15
0x18003a4fa  pop     r14
0x18003a4fc  pop     rdi
0x18003a4fd  retn
0x18003a4fe  mov     rax, cs:?g_hMD5Provider@@3PEAXEA; void * g_hMD5Provider
0x18003a505  jmp     short loc_18003A4B5
0x18003a507  xor     ebx, ebx
0x18003a509  mov     ecx, 490h
0x18003a50e  jmp     short loc_18003A4DE
0x18003a510  mov     rax, cs:?g_hSHAProvider@@3PEAXEA; void * g_hSHAProvider
0x18003a517  jmp     short loc_18003A4B5
0x18003a519  xor     edi, edi
0x18003a51b  jmp     short loc_18003A4AB
0x18003a51d  mov     rdx, [rcx]; pszAlgId
0x18003a520  test    rdx, rdx
0x18003a523  jnz     loc_18008EC9C
0x18003a529  mov     ecx, 54Fh
0x18003a52e  jmp     short loc_18003A4DE
0x18008ec9c  xor     r9d, r9d; dwFlags
0x18008ec9f  lea     rcx, [rsp+38h+phAlgorithm]; phAlgorithm
0x18008eca4  xor     r8d, r8d; pszImplementation
0x18008eca7  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18008ecad  mov     ecx, eax
0x18008ecaf  test    eax, eax
0x18008ecb1  jnz     loc_18003A4DE
0x18008ecb7  mov     rcx, [rsp+38h+phAlgorithm]
0x18008ecbc  movsxd  rax, edi
0x18008ecbf  lea     rdx, ds:0AE610h[rax*8]
0x18008ecc7  xor     eax, eax
0x18008ecc9  lock cmpxchg [rdx+r15], rcx
0x18008eccf  mov     rdi, rax
0x18008ecd2  jz      loc_18003A4DC
0x18008ecd8  mov     rcx, [rsp+38h+phAlgorithm]; hAlgorithm
0x18008ecdd  xor     edx, edx; dwFlags
0x18008ecdf  call    cs:__imp_BCryptCloseAlgorithmProvider
0x18008ece5  mov     [rsp+38h+phAlgorithm], rdi
0x18008ecea  jmp     loc_18003A4DC
```
