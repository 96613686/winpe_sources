# ShaInitialize(uchar *,uint,ushort const *,void * *,uchar * *)

- ea: `0x14000c340`
- end: `0x14000c4e0`
- name: `?ShaInitialize@@YAJPEAEIPEBGPEAPEAXPEAPEAE@Z`
- size: `416`
- prototype: `__int64 __usercall@<rax>(PUCHAR pbSecret@<rcx>, ULONG cbSecret@<edx>, LPCWSTR pszAlgId@<r8>, void **@<r9>, unsigned __int8 **)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14000c22c`
- `0x14002015c`

## callees

- `0x14000c340`
- `0x140039b40`
- `0x140045430`
- `0x1400454a0`

## import_xrefs

- `cng!BCryptCloseAlgorithmProvider` at `0x14000c4d2`
- `cng!BCryptCloseAlgorithmProvider` at `0x14000c4d2`
- `cng!BCryptDestroyHash` at `0x14000c4b8`
- `cng!BCryptDestroyHash` at `0x14000c4b8`
- `cng!BCryptCreateHash` at `0x14000c445`
- `cng!BCryptCreateHash` at `0x14000c445`
- `cng!BCryptGetProperty` at `0x14000c3ea`
- `cng!BCryptGetProperty` at `0x14000c3ea`
- `cng!BCryptOpenAlgorithmProvider` at `0x14000c3b4`
- `cng!BCryptOpenAlgorithmProvider` at `0x14000c3b4`

## pseudocode

```c
__int64 __fastcall ShaInitialize(PUCHAR pbSecret, ULONG cbSecret, LPCWSTR pszAlgId, void **a4, unsigned __int8 **a5)
{
  BCRYPT_HASH_HANDLE v6; // rcx
  UCHAR *v7; // rdi
  unsigned __int8 **v10; // rsi
  ULONG v11; // r9d
  NTSTATUS Property; // ebx
  unsigned __int8 *v13; // rax
  ULONG cbOutput; // [rsp+40h] [rbp-20h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+48h] [rbp-18h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+50h] [rbp-10h] BYREF
  unsigned __int64 retaddr; // [rsp+88h] [rbp+28h]
  ULONG pbOutput; // [rsp+A8h] [rbp+48h] BYREF

  phAlgorithm = 0;
  v6 = 0;
  cbOutput = 4;
  v7 = 0;
  phHash = 0;
  pbOutput = 0;
  if ( a4 && (v10 = a5) != 0 )
  {
    *a4 = 0;
    *v10 = 0;
    if ( cbSecret && pbSecret )
      v11 = 8;
    else
      v11 = 0;
    Property = BCryptOpenAlgorithmProvider(&phAlgorithm, pszAlgId, L"Microsoft Primitive Provider", v11);
    if ( Property >= 0 )
    {
      Property = BCryptGetProperty(phAlgorithm, L"ObjectLength", (PUCHAR)&pbOutput, cbOutput, &cbOutput, 0);
      if ( Property >= 0 )
      {
        v13 = TpmAlloc(1, pbOutput, retaddr);
        v7 = v13;
        if ( v13 )
        {
          memset(v13, 0, pbOutput);
          Property = BCryptCreateHash(phAlgorithm, &phHash, v7, pbOutput, pbSecret, cbSecret, 0);
          if ( Property >= 0 )
          {
            *a4 = phHash;
            *v10 = v7;
            return (unsigned int)Property;
          }
        }
        else
        {
          Property = -1073741670;
        }
      }
    }
    v6 = phHash;
  }
  else
  {
    Property = -1073741811;
  }
  if ( v6 )
    BCryptDestroyHash(v6);
  if ( v7 )
    TpmFree(v7);
  if ( phAlgorithm )
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  return (unsigned int)Property;
}

```

## disassembly

```asm
0x14000c340  mov     [rsp-28h+arg_0], rbx
0x14000c345  mov     [rsp-28h+arg_8], rsi
0x14000c34a  push    rbp
0x14000c34b  push    rdi
0x14000c34c  push    r12
0x14000c34e  push    r14
0x14000c350  push    r15
0x14000c352  mov     rbp, rsp
0x14000c355  sub     rsp, 60h
0x14000c359  mov     r12, rcx
0x14000c35c  mov     [rbp+phAlgorithm], 0
0x14000c364  xor     ecx, ecx
0x14000c366  mov     [rbp+cbOutput], 4
0x14000c36d  xor     edi, edi
0x14000c36f  mov     [rbp+phHash], rcx
0x14000c373  mov     [rbp+pbOutput], ecx
0x14000c376  mov     r14, r9
0x14000c379  mov     rax, r8
0x14000c37c  mov     r15d, edx
0x14000c37f  test    r9, r9
0x14000c382  jz      loc_14000C4B1
0x14000c388  mov     rsi, [rbp+arg_20]
0x14000c38c  test    rsi, rsi
0x14000c38f  jz      loc_14000C4B1
0x14000c395  mov     [r9], rcx
0x14000c398  mov     [rsi], rcx
0x14000c39b  test    edx, edx
0x14000c39d  jnz     loc_14000C48A
0x14000c3a3  xor     r9d, r9d; dwFlags
0x14000c3a6  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x14000c3ad  mov     rdx, rax; pszAlgId
0x14000c3b0  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x14000c3b4  call    cs:__imp_BCryptOpenAlgorithmProvider
0x14000c3bb  nop     dword ptr [rax+rax+00h]
0x14000c3c0  mov     ebx, eax
0x14000c3c2  test    eax, eax
0x14000c3c4  js      loc_14000C457
0x14000c3ca  mov     r9d, [rbp+cbOutput]; cbOutput
0x14000c3ce  lea     rax, [rbp+cbOutput]
0x14000c3d2  mov     rcx, [rbp+phAlgorithm]; hObject
0x14000c3d6  lea     r8, [rbp+pbOutput]; pbOutput
0x14000c3da  mov     [rsp+60h+dwFlags], edi; dwFlags
0x14000c3de  lea     rdx, pszProperty; "ObjectLength"
0x14000c3e5  mov     [rsp+60h+pcbResult], rax; pcbResult
0x14000c3ea  call    cs:__imp_BCryptGetProperty
0x14000c3f1  nop     dword ptr [rax+rax+00h]
0x14000c3f6  mov     ebx, eax
0x14000c3f8  test    eax, eax
0x14000c3fa  js      short loc_14000C457
0x14000c3fc  mov     r8, [rbp+28h]; unsigned __int64
0x14000c400  mov     cl, 1; bool
0x14000c402  mov     edx, [rbp+pbOutput]; unsigned __int64
0x14000c405  call    ?TpmAlloc@@YAPEAE_N_K1@Z; TpmAlloc(bool,unsigned __int64,unsigned __int64)
0x14000c40a  mov     rdi, rax
0x14000c40d  test    rax, rax
0x14000c410  jz      loc_14000C49E
0x14000c416  mov     r8d, [rbp+pbOutput]; Size
0x14000c41a  xor     edx, edx; Val
0x14000c41c  mov     rcx, rax; void *
0x14000c41f  call    memset
0x14000c424  mov     r9d, [rbp+pbOutput]; cbHashObject
0x14000c428  lea     rdx, [rbp+phHash]; phHash
0x14000c42c  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x14000c430  mov     r8, rdi; pbHashObject
0x14000c433  mov     [rsp+60h+var_30], 0; dwFlags
0x14000c43b  mov     [rsp+60h+dwFlags], r15d; cbSecret
0x14000c440  mov     [rsp+60h+pcbResult], r12; pbSecret
0x14000c445  call    cs:__imp_BCryptCreateHash
0x14000c44c  nop     dword ptr [rax+rax+00h]
0x14000c451  mov     ebx, eax
0x14000c453  test    eax, eax
0x14000c455  jns     short loc_14000C4A5
0x14000c457  mov     rcx, [rbp+phHash]; hHash
0x14000c45b  test    rcx, rcx
0x14000c45e  jnz     short loc_14000C4B8
0x14000c460  test    rdi, rdi
0x14000c463  jnz     short loc_14000C4C6
0x14000c465  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x14000c469  test    rcx, rcx
0x14000c46c  jnz     short loc_14000C4D0
0x14000c46e  lea     r11, [rsp+60h+var_s0]
0x14000c473  mov     eax, ebx
0x14000c475  mov     rbx, [r11+30h]
0x14000c479  mov     rsi, [r11+38h]
0x14000c47d  mov     rsp, r11
0x14000c480  pop     r15
0x14000c482  pop     r14
0x14000c484  pop     r12
0x14000c486  pop     rdi
0x14000c487  pop     rbp
0x14000c488  retn
0x14000c48a  test    r12, r12
0x14000c48d  jz      loc_14000C3A3
0x14000c493  mov     r9d, 8
0x14000c499  jmp     loc_14000C3A6
0x14000c49e  mov     ebx, 0C000009Ah
0x14000c4a3  jmp     short loc_14000C457
0x14000c4a5  mov     rax, [rbp+phHash]
0x14000c4a9  mov     [r14], rax
0x14000c4ac  mov     [rsi], rdi
0x14000c4af  jmp     short loc_14000C46E
0x14000c4b1  mov     ebx, 0C000000Dh
0x14000c4b6  jmp     short loc_14000C45B
0x14000c4b8  call    cs:__imp_BCryptDestroyHash
0x14000c4bf  nop     dword ptr [rax+rax+00h]
0x14000c4c4  jmp     short loc_14000C460
0x14000c4c6  mov     rcx, rdi; void *
0x14000c4c9  call    ?TpmFree@@YAXPEAX@Z; TpmFree(void *)
0x14000c4ce  jmp     short loc_14000C465
0x14000c4d0  xor     edx, edx; dwFlags
0x14000c4d2  call    cs:__imp_BCryptCloseAlgorithmProvider
0x14000c4d9  nop     dword ptr [rax+rax+00h]
0x14000c4de  jmp     short loc_14000C46E
```
