# Sha256Hash(utl::span<utl::byte const,-1>,utl::span<utl::byte,32>)

- ea: `0x140030d14`
- end: `0x140030ec3`
- name: `?Sha256Hash@@YAJV?$span@$$CBW4byte@utl@@$0?0@utl@@V?$span@W4byte@utl@@$0CA@@2@@Z`
- size: `431`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140030ecc`

## callees

- `0x140021b00`
- `0x140030d14`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140030e98`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140030e98`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140030dc2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140030e8a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140030dc2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140030e8a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140030dd0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140030dd0`
- `bcrypt!BCryptGetProperty` at `0x140030dae`
- `bcrypt!BCryptGetProperty` at `0x140030dae`
- `bcrypt!BCryptHashData` at `0x140030e30`
- `bcrypt!BCryptHashData` at `0x140030e4b`
- `bcrypt!BCryptHashData` at `0x140030e30`
- `bcrypt!BCryptHashData` at `0x140030e4b`
- `bcrypt!BCryptFinishHash` at `0x140030e66`
- `bcrypt!BCryptFinishHash` at `0x140030e66`
- `bcrypt!BCryptCreateHash` at `0x140030d72`
- `bcrypt!BCryptCreateHash` at `0x140030e11`
- `bcrypt!BCryptCreateHash` at `0x140030d72`
- `bcrypt!BCryptCreateHash` at `0x140030e11`
- `bcrypt!BCryptDestroyHash` at `0x140030e7f`
- `bcrypt!BCryptDestroyHash` at `0x140030e7f`

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
0x140030d14  push    rbp
0x140030d16  push    rbx
0x140030d17  push    rsi
0x140030d18  push    rdi
0x140030d19  push    r12
0x140030d1b  push    r14
0x140030d1d  lea     rbp, [rsp-0F8h]
0x140030d25  sub     rsp, 1F8h
0x140030d2c  mov     rax, cs:__security_cookie
0x140030d33  xor     rax, rsp
0x140030d36  mov     [rbp+120h+var_40], rax
0x140030d3d  xor     esi, esi
0x140030d3f  mov     [rsp+220h+phHash], 0
0x140030d48  mov     rbx, rdx
0x140030d4b  mov     [rsp+220h+dwFlags], esi; dwFlags
0x140030d4f  mov     r14, rcx
0x140030d52  mov     [rsp+220h+cbSecret], esi; cbSecret
0x140030d56  mov     r9d, 180h; cbHashObject
0x140030d5c  mov     [rsp+220h+pbSecret], rsi; pbSecret
0x140030d61  lea     r12d, [rsi+41h]
0x140030d65  mov     ecx, r12d; hAlgorithm
0x140030d68  lea     r8, [rsp+220h+pbHashObject]; pbHashObject
0x140030d6d  lea     rdx, [rsp+220h+phHash]; phHash
0x140030d72  call    cs:__imp_BCryptCreateHash
0x140030d78  mov     edi, eax
0x140030d7a  cmp     eax, 0C0000023h
0x140030d7f  jnz     loc_140030E19
0x140030d85  lea     rax, [rsp+220h+pcbResult]
0x140030d8a  mov     [rsp+220h+cbSecret], esi; dwFlags
0x140030d8e  lea     r9d, [rsi+4]; cbOutput
0x140030d92  mov     [rsp+220h+pbSecret], rax; pcbResult
0x140030d97  lea     r8, [rsp+220h+pbOutput]; pbOutput
0x140030d9c  mov     dword ptr [rsp+220h+pbOutput], esi
0x140030da0  lea     rdx, pszProperty; "ObjectLength"
0x140030da7  mov     [rsp+220h+pcbResult], esi
0x140030dab  mov     ecx, r12d; hObject
0x140030dae  call    cs:__imp_BCryptGetProperty
0x140030db4  mov     edi, eax
0x140030db6  test    eax, eax
0x140030db8  js      loc_140030E75
0x140030dbe  mov     edi, dword ptr [rsp+220h+pbOutput]
0x140030dc2  call    cs:__imp_GetProcessHeap
0x140030dc8  mov     r8d, edi; dwBytes
0x140030dcb  xor     edx, edx; dwFlags
0x140030dcd  mov     rcx, rax; hHeap
0x140030dd0  call    cs:__imp_HeapAlloc
0x140030dd6  mov     rsi, rax
0x140030dd9  test    rax, rax
0x140030ddc  jnz     short loc_140030DE8
0x140030dde  mov     edi, 0C0000017h
0x140030de3  jmp     loc_140030E75
0x140030de8  mov     r9d, dword ptr [rsp+220h+pbOutput]; cbHashObject
0x140030ded  lea     rdx, [rsp+220h+phHash]; phHash
0x140030df2  mov     [rsp+220h+dwFlags], 0; dwFlags
0x140030dfa  mov     r8, rax; pbHashObject
0x140030dfd  mov     [rsp+220h+cbSecret], 0; cbSecret
0x140030e05  mov     rcx, r12; hAlgorithm
0x140030e08  mov     [rsp+220h+pbSecret], 0; pbSecret
0x140030e11  call    cs:__imp_BCryptCreateHash
0x140030e17  mov     edi, eax
0x140030e19  test    edi, edi
0x140030e1b  js      short loc_140030E75
0x140030e1d  mov     rcx, [rsp+220h+phHash]; hHash
0x140030e22  lea     rdx, pbInput; "MS-WEVT"
0x140030e29  xor     r9d, r9d; dwFlags
0x140030e2c  lea     r8d, [r9+8]; cbInput
0x140030e30  call    cs:__imp_BCryptHashData
0x140030e36  mov     edi, eax
0x140030e38  test    eax, eax
0x140030e3a  js      short loc_140030E75
0x140030e3c  mov     r8d, [r14+8]; cbInput
0x140030e40  xor     r9d, r9d; dwFlags
0x140030e43  mov     rdx, [r14]; pbInput
0x140030e46  mov     rcx, [rsp+220h+phHash]; hHash
0x140030e4b  call    cs:__imp_BCryptHashData
0x140030e51  mov     edi, eax
0x140030e53  test    eax, eax
0x140030e55  js      short loc_140030E75
0x140030e57  mov     rcx, [rsp+220h+phHash]; hHash
0x140030e5c  xor     r9d, r9d; dwFlags
0x140030e5f  mov     rdx, rbx; pbOutput
0x140030e62  lea     r8d, [r9+20h]; cbOutput
0x140030e66  call    cs:__imp_BCryptFinishHash
0x140030e6c  mov     edi, eax
0x140030e6e  xor     eax, eax
0x140030e70  test    edi, edi
0x140030e72  cmovns  edi, eax
0x140030e75  mov     rcx, [rsp+220h+phHash]; hHash
0x140030e7a  test    rcx, rcx
0x140030e7d  jz      short loc_140030E85
0x140030e7f  call    cs:__imp_BCryptDestroyHash
0x140030e85  test    rsi, rsi
0x140030e88  jz      short loc_140030E9E
0x140030e8a  call    cs:__imp_GetProcessHeap
0x140030e90  mov     r8, rsi; lpMem
0x140030e93  xor     edx, edx; dwFlags
0x140030e95  mov     rcx, rax; hHeap
0x140030e98  call    cs:__imp_HeapFree
0x140030e9e  bts     edi, 1Ch
0x140030ea2  mov     eax, edi
0x140030ea4  mov     rcx, [rbp+120h+var_40]
0x140030eab  xor     rcx, rsp; StackCookie
0x140030eae  call    __security_check_cookie
0x140030eb3  add     rsp, 1F8h
0x140030eba  pop     r14
0x140030ebc  pop     r12
0x140030ebe  pop     rdi
0x140030ebf  pop     rsi
0x140030ec0  pop     rbx
0x140030ec1  pop     rbp
0x140030ec2  retn
```
