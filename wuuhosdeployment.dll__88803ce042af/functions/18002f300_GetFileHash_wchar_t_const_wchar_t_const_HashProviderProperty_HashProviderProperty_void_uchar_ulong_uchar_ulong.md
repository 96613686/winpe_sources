# GetFileHash(wchar_t const *,wchar_t const *,HashProviderProperty,HashProviderProperty *,void *,uchar * *,ulong *,uchar * *,ulong *)

- ea: `0x18002f300`
- end: `0x18002f6a5`
- name: `?GetFileHash@@YAJPEB_W0UHashProviderProperty@@PEAU1@PEAXPEAPEAEPEAK45@Z`
- size: `933`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18002f6ac`

## callees

- `0x180003950`
- `0x180003974`
- `0x180005f64`
- `0x18000a6d0`
- `0x18002f194`
- `0x18002f300`
- `0x180042630`

## import_xrefs

- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x18002f3de`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x18002f459`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x18002f630`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x18002f660`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x18002f3de`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x18002f459`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x18002f630`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x18002f660`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x18002f422`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x18002f649`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x18002f679`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x18002f422`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x18002f649`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x18002f679`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptAcquireContextW` at `0x18002f3c1`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptAcquireContextW` at `0x18002f43c`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptAcquireContextW` at `0x18002f3c1`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptAcquireContextW` at `0x18002f43c`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x18002f3fb`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x18002f477`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x18002f3fb`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x18002f477`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x18002f4c6`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x18002f51f`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x18002f552`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x18002f5bc`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x18002f4c6`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x18002f51f`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x18002f552`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x18002f5bc`

## pseudocode

```c
__int64 __fastcall GetFileHash(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        BYTE **a6,
        DWORD *a7,
        BYTE **a8,
        DWORD *a9)
{
  BYTE *v11; // rdi
  BYTE *v12; // rbx
  __int64 v13; // rdx
  unsigned int LastError; // esi
  const char *v15; // r9
  __int64 v16; // rdx
  DWORD v17; // esi
  int v18; // eax
  unsigned __int64 v19; // r9
  HCRYPTHASH v20; // rcx
  HCRYPTHASH v21; // rcx
  BYTE *v22; // rax
  BYTE *v23; // rax
  int dwFlags; // [rsp+20h] [rbp-50h]
  DWORD pdwDataLen; // [rsp+40h] [rbp-30h] BYREF
  DWORD v28; // [rsp+44h] [rbp-2Ch] BYREF
  HCRYPTHASH phHash; // [rsp+48h] [rbp-28h] BYREF
  HCRYPTHASH hHash; // [rsp+50h] [rbp-20h] BYREF
  HCRYPTPROV hProv; // [rsp+58h] [rbp-18h] BYREF
  HCRYPTPROV phProv; // [rsp+60h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]

  v11 = 0;
  phProv = 0;
  v12 = 0;
  hHash = 0;
  hProv = 0;
  phHash = 0;
  pdwDataLen = 0;
  v28 = 0;
  if ( !a6 )
  {
    v13 = 330;
LABEL_10:
    LastError = -2147467261;
LABEL_42:
    v19 = LastError;
    goto LABEL_43;
  }
  if ( !a7 )
  {
    v13 = 331;
    goto LABEL_10;
  }
  *a6 = 0;
  *a7 = 0;
  if ( a4 )
  {
    if ( !a8 )
    {
      v13 = 338;
      goto LABEL_10;
    }
    if ( !a9 )
    {
      v13 = 339;
      goto LABEL_10;
    }
    *a8 = 0;
    *a9 = 0;
  }
  if ( !CryptAcquireContextW(&phProv, 0, 0, *(_DWORD *)a3, 0xF0000040) )
  {
    v16 = 349;
LABEL_46:
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v16,
                  (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\FileCheck.cpp",
                  v15);
    goto LABEL_52;
  }
  if ( hHash )
    CryptDestroyHash(hHash);
  if ( !CryptCreateHash(phProv, *(_DWORD *)(a3 + 4), *(_QWORD *)(a3 + 8), 0, &hHash) )
  {
    v16 = 356;
    goto LABEL_46;
  }
  if ( a4 )
  {
    v17 = *(_DWORD *)a4;
    if ( hProv )
      CryptReleaseContext(hProv, 0);
    if ( !CryptAcquireContextW(&hProv, 0, 0, v17, 0xF0000040) )
    {
      v16 = 365;
      goto LABEL_46;
    }
    if ( phHash )
      CryptDestroyHash(phHash);
    if ( !CryptCreateHash(hProv, *(_DWORD *)(a4 + 4), *(_QWORD *)(a4 + 8), 0, &phHash) )
    {
      v16 = 372;
      goto LABEL_46;
    }
  }
  v18 = HashFileData(a1, hHash, phHash);
  LastError = v18;
  if ( v18 < 0 )
  {
    v19 = (unsigned int)v18;
    v13 = 376;
LABEL_43:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\FileCheck.cpp",
      (const char *)v19,
      dwFlags);
    goto LABEL_52;
  }
  v20 = hHash;
  *a7 = 0;
  if ( !CryptGetHashParam(v20, 2u, 0, &pdwDataLen, 0) )
  {
    v16 = 380;
    goto LABEL_46;
  }
  if ( pdwDataLen )
  {
    v11 = (BYTE *)SafeSusAllocArray(pdwDataLen, 1u);
    LastError = v11 == 0 ? 0x8007000E : 0;
    if ( !v11 )
    {
      v13 = 382;
      goto LABEL_42;
    }
  }
  if ( !CryptGetHashParam(hHash, 2u, v11, &pdwDataLen, 0) )
  {
    v16 = 384;
    goto LABEL_46;
  }
  if ( a4 )
  {
    v21 = phHash;
    *a9 = 0;
    if ( !CryptGetHashParam(v21, 2u, 0, &v28, 0) )
    {
      v16 = 391;
      goto LABEL_46;
    }
    if ( v28 )
    {
      v12 = (BYTE *)SafeSusAllocArray(v28, 1u);
      LastError = v12 == 0 ? 0x8007000E : 0;
      if ( !v12 )
      {
        v13 = 393;
        goto LABEL_42;
      }
    }
    if ( !CryptGetHashParam(phHash, 2u, v12, &v28, 0) )
    {
      v16 = 396;
      goto LABEL_46;
    }
  }
  v22 = v11;
  v11 = 0;
  *a6 = v22;
  *a7 = pdwDataLen;
  if ( a8 )
  {
    v23 = v12;
    v12 = 0;
    *a8 = v23;
  }
  if ( a9 )
    *a9 = v28;
  LastError = 0;
LABEL_52:
  if ( v12 )
    CSusBaseAllocTag<942762101>::operator delete(v12);
  if ( v11 )
    CSusBaseAllocTag<942762101>::operator delete(v11);
  if ( phHash )
  {
    CryptDestroyHash(phHash);
    phHash = 0;
  }
  if ( hProv )
  {
    CryptReleaseContext(hProv, 0);
    hProv = 0;
  }
  if ( hHash )
  {
    CryptDestroyHash(hHash);
    hHash = 0;
  }
  if ( phProv )
    CryptReleaseContext(phProv, 0);
  return LastError;
}

```

## disassembly

```asm
0x18002f300  mov     [rsp-38h+arg_8], rbx
0x18002f305  push    rbp
0x18002f306  push    rsi
0x18002f307  push    rdi
0x18002f308  push    r12
0x18002f30a  push    r13
0x18002f30c  push    r14
0x18002f30e  push    r15
0x18002f310  mov     rbp, rsp
0x18002f313  sub     rsp, 70h
0x18002f317  mov     rax, cs:__security_cookie
0x18002f31e  xor     rax, rsp
0x18002f321  mov     [rbp+var_8], rax
0x18002f325  mov     rax, [rbp+arg_28]
0x18002f329  mov     r14, r9
0x18002f32c  mov     r13, [rbp+arg_30]
0x18002f330  mov     rsi, r8
0x18002f333  mov     r12, [rbp+arg_38]
0x18002f337  mov     r15, [rbp+arg_40]
0x18002f33e  mov     [rbp+var_40], rcx
0x18002f342  xor     ecx, ecx
0x18002f344  mov     [rbp+var_38], rax
0x18002f348  mov     edi, ecx
0x18002f34a  mov     [rbp+phProv], rcx
0x18002f34e  mov     ebx, ecx
0x18002f350  mov     [rbp+hHash], rcx
0x18002f354  mov     [rbp+hProv], rcx
0x18002f358  mov     [rbp+phHash], rcx
0x18002f35c  mov     [rbp+pdwDataLen], ecx
0x18002f35f  mov     [rbp+var_2C], ecx
0x18002f362  test    rax, rax
0x18002f365  jnz     short loc_18002F36E
0x18002f367  mov     edx, 14Ah
0x18002f36c  jmp     short loc_18002F39C
0x18002f36e  test    r13, r13
0x18002f371  jnz     short loc_18002F37A
0x18002f373  mov     edx, 14Bh
0x18002f378  jmp     short loc_18002F39C
0x18002f37a  mov     [rax], rcx
0x18002f37d  mov     [r13+0], ecx
0x18002f381  test    r14, r14
0x18002f384  jz      short loc_18002F3AD
0x18002f386  test    r12, r12
0x18002f389  jnz     short loc_18002F392
0x18002f38b  mov     edx, 152h
0x18002f390  jmp     short loc_18002F39C
0x18002f392  test    r15, r15
0x18002f395  jnz     short loc_18002F3A6
0x18002f397  mov     edx, 153h
0x18002f39c  mov     esi, 80004003h
0x18002f3a1  jmp     loc_18002F58F
0x18002f3a6  mov     [r12], rcx
0x18002f3aa  mov     [r15], ecx
0x18002f3ad  mov     r9d, [r8]; dwProvType
0x18002f3b0  lea     rcx, [rbp+phProv]; phProv
0x18002f3b4  xor     r8d, r8d; szProvider
0x18002f3b7  mov     [rsp+70h+dwFlags], 0F0000040h; dwFlags
0x18002f3bf  xor     edx, edx; szContainer
0x18002f3c1  call    cs:__imp_CryptAcquireContextW
0x18002f3c7  test    eax, eax
0x18002f3c9  jnz     short loc_18002F3D5
0x18002f3cb  mov     edx, 15Dh
0x18002f3d0  jmp     loc_18002F5CB
0x18002f3d5  mov     rcx, [rbp+hHash]; hHash
0x18002f3d9  test    rcx, rcx
0x18002f3dc  jz      short loc_18002F3E4
0x18002f3de  call    cs:__imp_CryptDestroyHash
0x18002f3e4  mov     r8, [rsi+8]; hKey
0x18002f3e8  lea     rax, [rbp+hHash]
0x18002f3ec  mov     edx, [rsi+4]; Algid
0x18002f3ef  xor     r9d, r9d; dwFlags
0x18002f3f2  mov     rcx, [rbp+phProv]; hProv
0x18002f3f6  mov     qword ptr [rsp+70h+dwFlags], rax; phHash
0x18002f3fb  call    cs:__imp_CryptCreateHash
0x18002f401  test    eax, eax
0x18002f403  jnz     short loc_18002F40F
0x18002f405  mov     edx, 164h
0x18002f40a  jmp     loc_18002F5CB
0x18002f40f  test    r14, r14
0x18002f412  jz      short loc_18002F48B
0x18002f414  mov     rcx, [rbp+hProv]; hProv
0x18002f418  mov     esi, [r14]
0x18002f41b  test    rcx, rcx
0x18002f41e  jz      short loc_18002F428
0x18002f420  xor     edx, edx; dwFlags
0x18002f422  call    cs:__imp_CryptReleaseContext
0x18002f428  mov     r9d, esi; dwProvType
0x18002f42b  mov     [rsp+70h+dwFlags], 0F0000040h; dwFlags
0x18002f433  xor     r8d, r8d; szProvider
0x18002f436  lea     rcx, [rbp+hProv]; phProv
0x18002f43a  xor     edx, edx; szContainer
0x18002f43c  call    cs:__imp_CryptAcquireContextW
0x18002f442  test    eax, eax
0x18002f444  jnz     short loc_18002F450
0x18002f446  mov     edx, 16Dh
0x18002f44b  jmp     loc_18002F5CB
0x18002f450  mov     rcx, [rbp+phHash]; hHash
0x18002f454  test    rcx, rcx
0x18002f457  jz      short loc_18002F45F
0x18002f459  call    cs:__imp_CryptDestroyHash
0x18002f45f  mov     r8, [r14+8]; hKey
0x18002f463  lea     rax, [rbp+phHash]
0x18002f467  mov     edx, [r14+4]; Algid
0x18002f46b  xor     r9d, r9d; dwFlags
0x18002f46e  mov     rcx, [rbp+hProv]; hProv
0x18002f472  mov     qword ptr [rsp+70h+dwFlags], rax; phHash
0x18002f477  call    cs:__imp_CryptCreateHash
0x18002f47d  test    eax, eax
0x18002f47f  jnz     short loc_18002F48B
0x18002f481  mov     edx, 174h
0x18002f486  jmp     loc_18002F5CB
0x18002f48b  mov     r8, [rbp+phHash]
0x18002f48f  mov     rdx, [rbp+hHash]
0x18002f493  mov     rcx, [rbp+var_40]
0x18002f497  call    HashFileData
0x18002f49c  mov     esi, eax
0x18002f49e  test    eax, eax
0x18002f4a0  jns     short loc_18002F4AF
0x18002f4a2  mov     r9d, eax
0x18002f4a5  mov     edx, 178h
0x18002f4aa  jmp     loc_18002F592
0x18002f4af  mov     rcx, [rbp+hHash]; hHash
0x18002f4b3  lea     r9, [rbp+pdwDataLen]; pdwDataLen
0x18002f4b7  xor     r8d, r8d; pbData
0x18002f4ba  mov     [r13+0], ebx
0x18002f4be  mov     [rsp+70h+dwFlags], ebx; dwFlags
0x18002f4c2  lea     edx, [r8+2]; dwParam
0x18002f4c6  call    cs:__imp_CryptGetHashParam
0x18002f4cc  test    eax, eax
0x18002f4ce  jnz     short loc_18002F4DA
0x18002f4d0  mov     edx, 17Ch
0x18002f4d5  jmp     loc_18002F5CB
0x18002f4da  mov     ecx, [rbp+pdwDataLen]; unsigned __int64
0x18002f4dd  test    rcx, rcx
0x18002f4e0  jz      short loc_18002F50B
0x18002f4e2  mov     edx, 1; unsigned __int64
0x18002f4e7  call    ?SafeSusAllocArray@@YAPEAX_K0@Z; SafeSusAllocArray(unsigned __int64,unsigned __int64)
0x18002f4ec  mov     rdi, rax
0x18002f4ef  neg     rax
0x18002f4f2  sbb     esi, esi
0x18002f4f4  not     esi
0x18002f4f6  and     esi, 8007000Eh
0x18002f4fc  test    rdi, rdi
0x18002f4ff  jnz     short loc_18002F50B
0x18002f501  mov     edx, 17Eh
0x18002f506  jmp     loc_18002F58F
0x18002f50b  mov     rcx, [rbp+hHash]; hHash
0x18002f50f  lea     r9, [rbp+pdwDataLen]; pdwDataLen
0x18002f513  mov     r8, rdi; pbData
0x18002f516  mov     [rsp+70h+dwFlags], ebx; dwFlags
0x18002f51a  mov     edx, 2; dwParam
0x18002f51f  call    cs:__imp_CryptGetHashParam
0x18002f525  test    eax, eax
0x18002f527  jnz     short loc_18002F533
0x18002f529  mov     edx, 180h
0x18002f52e  jmp     loc_18002F5CB
0x18002f533  test    r14, r14
0x18002f536  jz      loc_18002F5DF
0x18002f53c  mov     rcx, [rbp+phHash]; hHash
0x18002f540  lea     r9, [rbp+var_2C]; pdwDataLen
0x18002f544  xor     r8d, r8d; pbData
0x18002f547  mov     [r15], ebx
0x18002f54a  mov     [rsp+70h+dwFlags], ebx; int
0x18002f54e  lea     edx, [r8+2]; dwParam
0x18002f552  call    cs:__imp_CryptGetHashParam
0x18002f558  test    eax, eax
0x18002f55a  jnz     short loc_18002F563
0x18002f55c  mov     edx, 187h
0x18002f561  jmp     short loc_18002F5CB
0x18002f563  mov     ecx, [rbp+var_2C]; unsigned __int64
0x18002f566  test    rcx, rcx
0x18002f569  jz      short loc_18002F5A4
0x18002f56b  mov     edx, 1; unsigned __int64
0x18002f570  call    ?SafeSusAllocArray@@YAPEAX_K0@Z; SafeSusAllocArray(unsigned __int64,unsigned __int64)
0x18002f575  mov     rbx, rax
0x18002f578  neg     rax
0x18002f57b  sbb     esi, esi
0x18002f57d  not     esi
0x18002f57f  and     esi, 8007000Eh
0x18002f585  test    rbx, rbx
0x18002f588  jnz     short loc_18002F5A4
0x18002f58a  mov     edx, 189h; void *
0x18002f58f  mov     r9d, esi; char *
0x18002f592  mov     rcx, [rbp+38h]; this
0x18002f596  lea     r8, aCW1SSrcClientL_21; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18002f59d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002f5a2  jmp     short loc_18002F60D
0x18002f5a4  mov     rcx, [rbp+phHash]; hHash
0x18002f5a8  lea     r9, [rbp+var_2C]; pdwDataLen
0x18002f5ac  mov     r8, rbx; pbData
0x18002f5af  mov     [rsp+70h+dwFlags], 0; dwFlags
0x18002f5b7  mov     edx, 2; dwParam
0x18002f5bc  call    cs:__imp_CryptGetHashParam
0x18002f5c2  test    eax, eax
0x18002f5c4  jnz     short loc_18002F5DF
0x18002f5c6  mov     edx, 18Ch; void *
0x18002f5cb  mov     rcx, [rbp+38h]; this
0x18002f5cf  lea     r8, aCW1SSrcClientL_21; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18002f5d6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002f5db  mov     esi, eax
0x18002f5dd  jmp     short loc_18002F60D
0x18002f5df  mov     rcx, [rbp+var_38]
0x18002f5e3  mov     rax, rdi
0x18002f5e6  xor     edi, edi
0x18002f5e8  mov     [rcx], rax
0x18002f5eb  mov     eax, [rbp+pdwDataLen]
0x18002f5ee  mov     [r13+0], eax
0x18002f5f2  test    r12, r12
0x18002f5f5  jz      short loc_18002F600
0x18002f5f7  mov     rax, rbx
0x18002f5fa  xor     ebx, ebx
0x18002f5fc  mov     [r12], rax
0x18002f600  test    r15, r15
0x18002f603  jz      short loc_18002F60B
0x18002f605  mov     eax, [rbp+var_2C]
0x18002f608  mov     [r15], eax
0x18002f60b  xor     esi, esi
0x18002f60d  test    rbx, rbx
0x18002f610  jz      short loc_18002F61A
0x18002f612  mov     rcx, rbx; lpMem
0x18002f615  call    ??3?$CSusBaseAllocTag@$0DIDBGIHF@@@SAXPEAX@Z; CSusBaseAllocTag<942762101>::operator delete(void *)
0x18002f61a  test    rdi, rdi
0x18002f61d  jz      short loc_18002F627
0x18002f61f  mov     rcx, rdi; lpMem
0x18002f622  call    ??3?$CSusBaseAllocTag@$0DIDBGIHF@@@SAXPEAX@Z; CSusBaseAllocTag<942762101>::operator delete(void *)
0x18002f627  mov     rcx, [rbp+phHash]; hHash
0x18002f62b  test    rcx, rcx
0x18002f62e  jz      short loc_18002F63E
0x18002f630  call    cs:__imp_CryptDestroyHash
0x18002f636  mov     [rbp+phHash], 0
0x18002f63e  mov     rcx, [rbp+hProv]; hProv
0x18002f642  test    rcx, rcx
0x18002f645  jz      short loc_18002F657
0x18002f647  xor     edx, edx; dwFlags
0x18002f649  call    cs:__imp_CryptReleaseContext
0x18002f64f  mov     [rbp+hProv], 0
0x18002f657  mov     rcx, [rbp+hHash]; hHash
0x18002f65b  test    rcx, rcx
0x18002f65e  jz      short loc_18002F66E
0x18002f660  call    cs:__imp_CryptDestroyHash
0x18002f666  mov     [rbp+hHash], 0
0x18002f66e  mov     rcx, [rbp+phProv]; hProv
0x18002f672  test    rcx, rcx
0x18002f675  jz      short loc_18002F67F
0x18002f677  xor     edx, edx; dwFlags
0x18002f679  call    cs:__imp_CryptReleaseContext
0x18002f67f  mov     eax, esi
0x18002f681  mov     rcx, [rbp+var_8]
0x18002f685  xor     rcx, rsp; StackCookie
0x18002f688  call    __security_check_cookie
0x18002f68d  mov     rbx, [rsp+70h+arg_8]
0x18002f695  add     rsp, 70h
0x18002f699  pop     r15
0x18002f69b  pop     r14
0x18002f69d  pop     r13
0x18002f69f  pop     r12
0x18002f6a1  pop     rdi
0x18002f6a2  pop     rsi
0x18002f6a3  pop     rbp
0x18002f6a4  retn
```
