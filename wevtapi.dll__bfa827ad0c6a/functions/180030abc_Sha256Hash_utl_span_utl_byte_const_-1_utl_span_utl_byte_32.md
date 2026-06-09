# Sha256Hash(utl::span<utl::byte const,-1>,utl::span<utl::byte,32>)

- ea: `0x180030abc`
- end: `0x180030c6b`
- name: `?Sha256Hash@@YAJV?$span@$$CBW4byte@utl@@$0?0@utl@@V?$span@W4byte@utl@@$0CA@@2@@Z`
- size: `431`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000dff8`
- `0x180030c74`

## callees

- `0x180024a50`
- `0x180030abc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180030b6a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180030c32`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180030b6a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180030c32`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180030b78`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180030b78`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180030c40`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180030c40`
- `bcrypt!BCryptDestroyHash` at `0x180030c27`
- `bcrypt!BCryptDestroyHash` at `0x180030c27`
- `bcrypt!BCryptHashData` at `0x180030bd8`
- `bcrypt!BCryptHashData` at `0x180030bf3`
- `bcrypt!BCryptHashData` at `0x180030bd8`
- `bcrypt!BCryptHashData` at `0x180030bf3`
- `bcrypt!BCryptCreateHash` at `0x180030b1a`
- `bcrypt!BCryptCreateHash` at `0x180030bb9`
- `bcrypt!BCryptCreateHash` at `0x180030b1a`
- `bcrypt!BCryptCreateHash` at `0x180030bb9`
- `bcrypt!BCryptGetProperty` at `0x180030b56`
- `bcrypt!BCryptGetProperty` at `0x180030b56`
- `bcrypt!BCryptFinishHash` at `0x180030c0e`
- `bcrypt!BCryptFinishHash` at `0x180030c0e`

## pseudocode

```c
__int64 __fastcall Sha256Hash(__int64 a1, UCHAR *a2)
{
  UCHAR *v2; // rsi
  NTSTATUS Property; // edi
  unsigned int v6; // edi
  HANDLE ProcessHeap; // rax
  UCHAR *v8; // rax
  HANDLE v9; // rax
  UCHAR pbOutput[4]; // [rsp+40h] [rbp-C0h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+48h] [rbp-B8h] BYREF
  ULONG pcbResult[4]; // [rsp+50h] [rbp-B0h] BYREF
  UCHAR pbHashObject[384]; // [rsp+60h] [rbp-A0h] BYREF

  v2 = 0;
  phHash = 0;
  Property = BCryptCreateHash((BCRYPT_ALG_HANDLE)0x41, &phHash, pbHashObject, 0x180u, 0, 0, 0);
  if ( Property == -1073741789 )
  {
    *(_DWORD *)pbOutput = 0;
    pcbResult[0] = 0;
    Property = BCryptGetProperty((BCRYPT_HANDLE)0x41, L"ObjectLength", pbOutput, 4u, pcbResult, 0);
    if ( Property < 0 )
      goto LABEL_11;
    v6 = *(_DWORD *)pbOutput;
    ProcessHeap = GetProcessHeap();
    v8 = (UCHAR *)HeapAlloc(ProcessHeap, 0, v6);
    v2 = v8;
    if ( !v8 )
    {
      Property = -1073741801;
      goto LABEL_11;
    }
    Property = BCryptCreateHash((BCRYPT_ALG_HANDLE)0x41, &phHash, v8, *(ULONG *)pbOutput, 0, 0, 0);
  }
  if ( Property >= 0 )
  {
    Property = BCryptHashData(phHash, (PUCHAR)"MS-WEVT", 8u, 0);
    if ( Property >= 0 )
    {
      Property = BCryptHashData(phHash, *(PUCHAR *)a1, *(_DWORD *)(a1 + 8), 0);
      if ( Property >= 0 )
      {
        Property = BCryptFinishHash(phHash, a2, 0x20u, 0);
        if ( Property >= 0 )
          Property = 0;
      }
    }
  }
LABEL_11:
  if ( phHash )
    BCryptDestroyHash(phHash);
  if ( v2 )
  {
    v9 = GetProcessHeap();
    HeapFree(v9, 0, v2);
  }
  return Property | 0x10000000u;
}

```

## disassembly

```asm
0x180030abc  push    rbp
0x180030abe  push    rbx
0x180030abf  push    rsi
0x180030ac0  push    rdi
0x180030ac1  push    r12
0x180030ac3  push    r14
0x180030ac5  lea     rbp, [rsp-0F8h]
0x180030acd  sub     rsp, 1F8h
0x180030ad4  mov     rax, cs:__security_cookie
0x180030adb  xor     rax, rsp
0x180030ade  mov     [rbp+120h+var_40], rax
0x180030ae5  xor     esi, esi
0x180030ae7  mov     [rsp+220h+phHash], 0
0x180030af0  mov     rbx, rdx
0x180030af3  mov     [rsp+220h+dwFlags], esi; dwFlags
0x180030af7  mov     r14, rcx
0x180030afa  mov     [rsp+220h+cbSecret], esi; cbSecret
0x180030afe  mov     r9d, 180h; cbHashObject
0x180030b04  mov     [rsp+220h+pbSecret], rsi; pbSecret
0x180030b09  lea     r12d, [rsi+41h]
0x180030b0d  mov     ecx, r12d; hAlgorithm
0x180030b10  lea     r8, [rsp+220h+pbHashObject]; pbHashObject
0x180030b15  lea     rdx, [rsp+220h+phHash]; phHash
0x180030b1a  call    cs:__imp_BCryptCreateHash
0x180030b20  mov     edi, eax
0x180030b22  cmp     eax, 0C0000023h
0x180030b27  jnz     loc_180030BC1
0x180030b2d  lea     rax, [rsp+220h+pcbResult]
0x180030b32  mov     [rsp+220h+cbSecret], esi; dwFlags
0x180030b36  lea     r9d, [rsi+4]; cbOutput
0x180030b3a  mov     [rsp+220h+pbSecret], rax; pcbResult
0x180030b3f  lea     r8, [rsp+220h+pbOutput]; pbOutput
0x180030b44  mov     dword ptr [rsp+220h+pbOutput], esi
0x180030b48  lea     rdx, pszProperty; "ObjectLength"
0x180030b4f  mov     [rsp+220h+pcbResult], esi
0x180030b53  mov     ecx, r12d; hObject
0x180030b56  call    cs:__imp_BCryptGetProperty
0x180030b5c  mov     edi, eax
0x180030b5e  test    eax, eax
0x180030b60  js      loc_180030C1D
0x180030b66  mov     edi, dword ptr [rsp+220h+pbOutput]
0x180030b6a  call    cs:__imp_GetProcessHeap
0x180030b70  mov     r8d, edi; dwBytes
0x180030b73  xor     edx, edx; dwFlags
0x180030b75  mov     rcx, rax; hHeap
0x180030b78  call    cs:__imp_HeapAlloc
0x180030b7e  mov     rsi, rax
0x180030b81  test    rax, rax
0x180030b84  jnz     short loc_180030B90
0x180030b86  mov     edi, 0C0000017h
0x180030b8b  jmp     loc_180030C1D
0x180030b90  mov     r9d, dword ptr [rsp+220h+pbOutput]; cbHashObject
0x180030b95  lea     rdx, [rsp+220h+phHash]; phHash
0x180030b9a  mov     [rsp+220h+dwFlags], 0; dwFlags
0x180030ba2  mov     r8, rax; pbHashObject
0x180030ba5  mov     [rsp+220h+cbSecret], 0; cbSecret
0x180030bad  mov     rcx, r12; hAlgorithm
0x180030bb0  mov     [rsp+220h+pbSecret], 0; pbSecret
0x180030bb9  call    cs:__imp_BCryptCreateHash
0x180030bbf  mov     edi, eax
0x180030bc1  test    edi, edi
0x180030bc3  js      short loc_180030C1D
0x180030bc5  mov     rcx, [rsp+220h+phHash]; hHash
0x180030bca  lea     rdx, pbInput; "MS-WEVT"
0x180030bd1  xor     r9d, r9d; dwFlags
0x180030bd4  lea     r8d, [r9+8]; cbInput
0x180030bd8  call    cs:__imp_BCryptHashData
0x180030bde  mov     edi, eax
0x180030be0  test    eax, eax
0x180030be2  js      short loc_180030C1D
0x180030be4  mov     r8d, [r14+8]; cbInput
0x180030be8  xor     r9d, r9d; dwFlags
0x180030beb  mov     rdx, [r14]; pbInput
0x180030bee  mov     rcx, [rsp+220h+phHash]; hHash
0x180030bf3  call    cs:__imp_BCryptHashData
0x180030bf9  mov     edi, eax
0x180030bfb  test    eax, eax
0x180030bfd  js      short loc_180030C1D
0x180030bff  mov     rcx, [rsp+220h+phHash]; hHash
0x180030c04  xor     r9d, r9d; dwFlags
0x180030c07  mov     rdx, rbx; pbOutput
0x180030c0a  lea     r8d, [r9+20h]; cbOutput
0x180030c0e  call    cs:__imp_BCryptFinishHash
0x180030c14  mov     edi, eax
0x180030c16  xor     eax, eax
0x180030c18  test    edi, edi
0x180030c1a  cmovns  edi, eax
0x180030c1d  mov     rcx, [rsp+220h+phHash]; hHash
0x180030c22  test    rcx, rcx
0x180030c25  jz      short loc_180030C2D
0x180030c27  call    cs:__imp_BCryptDestroyHash
0x180030c2d  test    rsi, rsi
0x180030c30  jz      short loc_180030C46
0x180030c32  call    cs:__imp_GetProcessHeap
0x180030c38  mov     r8, rsi; lpMem
0x180030c3b  xor     edx, edx; dwFlags
0x180030c3d  mov     rcx, rax; hHeap
0x180030c40  call    cs:__imp_HeapFree
0x180030c46  bts     edi, 1Ch
0x180030c4a  mov     eax, edi
0x180030c4c  mov     rcx, [rbp+120h+var_40]
0x180030c53  xor     rcx, rsp; StackCookie
0x180030c56  call    __security_check_cookie
0x180030c5b  add     rsp, 1F8h
0x180030c62  pop     r14
0x180030c64  pop     r12
0x180030c66  pop     rdi
0x180030c67  pop     rsi
0x180030c68  pop     rbx
0x180030c69  pop     rbp
0x180030c6a  retn
```
