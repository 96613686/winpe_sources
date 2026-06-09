# Sha256Hash(utl::span<utl::byte const,-1>,utl::span<utl::byte,32>)

- ea: `0x180043fc4`
- end: `0x18004417f`
- name: `?Sha256Hash@@YAJV?$span@$$CBW4byte@utl@@$0?0@utl@@V?$span@W4byte@utl@@$0CA@@2@@Z`
- size: `443`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180044188`
- `0x18007f1ec`

## callees

- `0x180043fc4`
- `0x18009aee0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180044174`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180044174`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180044118`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180044118`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004410a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180044166`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004410a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180044166`
- `bcrypt!BCryptGetProperty` at `0x1800440fa`
- `bcrypt!BCryptGetProperty` at `0x1800440fa`
- `bcrypt!BCryptHashData` at `0x18004404c`
- `bcrypt!BCryptHashData` at `0x180044067`
- `bcrypt!BCryptHashData` at `0x18004404c`
- `bcrypt!BCryptHashData` at `0x180044067`
- `bcrypt!BCryptDestroyHash` at `0x18004409b`
- `bcrypt!BCryptDestroyHash` at `0x18004409b`
- `bcrypt!BCryptFinishHash` at `0x180044082`
- `bcrypt!BCryptFinishHash` at `0x180044082`
- `bcrypt!BCryptCreateHash` at `0x180044022`
- `bcrypt!BCryptCreateHash` at `0x180044159`
- `bcrypt!BCryptCreateHash` at `0x180044022`
- `bcrypt!BCryptCreateHash` at `0x180044159`

## pseudocode

```c
__int64 __fastcall Sha256Hash(__int64 a1, UCHAR *a2)
{
  UCHAR *v2; // rsi
  NTSTATUS Property; // edi
  unsigned int v7; // edi
  HANDLE ProcessHeap; // rax
  UCHAR *v9; // rax
  HANDLE v10; // rax
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
      goto LABEL_7;
    v7 = *(_DWORD *)pbOutput;
    ProcessHeap = GetProcessHeap();
    v9 = (UCHAR *)HeapAlloc(ProcessHeap, 0, v7);
    v2 = v9;
    if ( !v9 )
    {
      Property = -1073741801;
      goto LABEL_7;
    }
    Property = BCryptCreateHash((BCRYPT_ALG_HANDLE)0x41, &phHash, v9, *(ULONG *)pbOutput, 0, 0, 0);
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
LABEL_7:
  if ( phHash )
    BCryptDestroyHash(phHash);
  if ( v2 )
  {
    v10 = GetProcessHeap();
    HeapFree(v10, 0, v2);
  }
  return Property | 0x10000000u;
}

```

## disassembly

```asm
0x180043fc4  push    rbp
0x180043fc6  push    rbx
0x180043fc7  push    rsi
0x180043fc8  push    rdi
0x180043fc9  push    r12
0x180043fcb  push    r14
0x180043fcd  lea     rbp, [rsp-0F8h]
0x180043fd5  sub     rsp, 1F8h
0x180043fdc  mov     rax, cs:__security_cookie
0x180043fe3  xor     rax, rsp
0x180043fe6  mov     [rbp+120h+var_40], rax
0x180043fed  xor     esi, esi
0x180043fef  mov     [rsp+220h+phHash], 0
0x180043ff8  mov     rbx, rdx
0x180043ffb  mov     [rsp+220h+dwFlags], esi; dwFlags
0x180043fff  mov     r14, rcx
0x180044002  mov     [rsp+220h+cbSecret], esi; cbSecret
0x180044006  mov     r9d, 180h; cbHashObject
0x18004400c  mov     [rsp+220h+pbSecret], rsi; pbSecret
0x180044011  lea     r12d, [rsi+41h]
0x180044015  mov     ecx, r12d; hAlgorithm
0x180044018  lea     r8, [rsp+220h+pbHashObject]; pbHashObject
0x18004401d  lea     rdx, [rsp+220h+phHash]; phHash
0x180044022  call    cs:__imp_BCryptCreateHash
0x180044028  mov     edi, eax
0x18004402a  cmp     eax, 0C0000023h
0x18004402f  jz      loc_1800440CF
0x180044035  test    edi, edi
0x180044037  js      short loc_180044091
0x180044039  mov     rcx, [rsp+220h+phHash]; hHash
0x18004403e  lea     rdx, pbInput; "MS-WEVT"
0x180044045  xor     r9d, r9d; dwFlags
0x180044048  lea     r8d, [r9+8]; cbInput
0x18004404c  call    cs:__imp_BCryptHashData
0x180044052  mov     edi, eax
0x180044054  test    eax, eax
0x180044056  js      short loc_180044091
0x180044058  mov     r8d, [r14+8]; cbInput
0x18004405c  xor     r9d, r9d; dwFlags
0x18004405f  mov     rdx, [r14]; pbInput
0x180044062  mov     rcx, [rsp+220h+phHash]; hHash
0x180044067  call    cs:__imp_BCryptHashData
0x18004406d  mov     edi, eax
0x18004406f  test    eax, eax
0x180044071  js      short loc_180044091
0x180044073  mov     rcx, [rsp+220h+phHash]; hHash
0x180044078  xor     r9d, r9d; dwFlags
0x18004407b  mov     rdx, rbx; pbOutput
0x18004407e  lea     r8d, [r9+20h]; cbOutput
0x180044082  call    cs:__imp_BCryptFinishHash
0x180044088  mov     edi, eax
0x18004408a  xor     eax, eax
0x18004408c  test    edi, edi
0x18004408e  cmovns  edi, eax
0x180044091  mov     rcx, [rsp+220h+phHash]; hHash
0x180044096  test    rcx, rcx
0x180044099  jz      short loc_1800440A1
0x18004409b  call    cs:__imp_BCryptDestroyHash
0x1800440a1  test    rsi, rsi
0x1800440a4  jnz     loc_180044166
0x1800440aa  bts     edi, 1Ch
0x1800440ae  mov     eax, edi
0x1800440b0  mov     rcx, [rbp+120h+var_40]
0x1800440b7  xor     rcx, rsp; StackCookie
0x1800440ba  call    __security_check_cookie
0x1800440bf  add     rsp, 1F8h
0x1800440c6  pop     r14
0x1800440c8  pop     r12
0x1800440ca  pop     rdi
0x1800440cb  pop     rsi
0x1800440cc  pop     rbx
0x1800440cd  pop     rbp
0x1800440ce  retn
0x1800440cf  lea     rax, [rsp+220h+pcbResult]
0x1800440d4  mov     [rsp+220h+cbSecret], esi; dwFlags
0x1800440d8  mov     r9d, 4; cbOutput
0x1800440de  mov     [rsp+220h+pbSecret], rax; pcbResult
0x1800440e3  lea     r8, [rsp+220h+pbOutput]; pbOutput
0x1800440e8  mov     dword ptr [rsp+220h+pbOutput], esi
0x1800440ec  lea     rdx, pszProperty; "ObjectLength"
0x1800440f3  mov     [rsp+220h+pcbResult], esi
0x1800440f7  mov     rcx, r12; hObject
0x1800440fa  call    cs:__imp_BCryptGetProperty
0x180044100  mov     edi, eax
0x180044102  test    eax, eax
0x180044104  js      short loc_180044091
0x180044106  mov     edi, dword ptr [rsp+220h+pbOutput]
0x18004410a  call    cs:__imp_GetProcessHeap
0x180044110  mov     r8d, edi; dwBytes
0x180044113  xor     edx, edx; dwFlags
0x180044115  mov     rcx, rax; hHeap
0x180044118  call    cs:__imp_HeapAlloc
0x18004411e  mov     rsi, rax
0x180044121  test    rax, rax
0x180044124  jnz     short loc_180044130
0x180044126  mov     edi, 0C0000017h
0x18004412b  jmp     loc_180044091
0x180044130  mov     r9d, dword ptr [rsp+220h+pbOutput]; cbHashObject
0x180044135  lea     rdx, [rsp+220h+phHash]; phHash
0x18004413a  mov     [rsp+220h+dwFlags], 0; dwFlags
0x180044142  mov     r8, rax; pbHashObject
0x180044145  mov     [rsp+220h+cbSecret], 0; cbSecret
0x18004414d  mov     rcx, r12; hAlgorithm
0x180044150  mov     [rsp+220h+pbSecret], 0; pbSecret
0x180044159  call    cs:__imp_BCryptCreateHash
0x18004415f  mov     edi, eax
0x180044161  jmp     loc_180044035
0x180044166  call    cs:__imp_GetProcessHeap
0x18004416c  mov     r8, rsi; lpMem
0x18004416f  xor     edx, edx; dwFlags
0x180044171  mov     rcx, rax; hHeap
0x180044174  call    cs:__imp_HeapFree
0x18004417a  jmp     loc_1800440AA
```
