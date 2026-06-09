# ComputeHash

- ea: `0x1400b1e00`
- end: `0x1400b1ff0`
- name: `ComputeHash`
- size: `496`
- prototype: `__int64 __fastcall(LPCWSTR pszAlgId, ULONG cbInput, PUCHAR pbInput, ULONG cbSecret, __int64, PUCHAR, PUCHAR)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1401171dc`
- `0x140117804`

## callees

- `0x1400b1e00`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400b1fb1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b1fb1`
- `ntoskrnl!ExAllocatePool2` at `0x1400b1eac`
- `ntoskrnl!ExAllocatePool2` at `0x1400b1eac`
- `ksecdd!BCryptCreateHash` at `0x1400b1f42`
- `ksecdd!BCryptCreateHash` at `0x1400b1f42`
- `ksecdd!BCryptHashData` at `0x1400b1f61`
- `ksecdd!BCryptHashData` at `0x1400b1f61`
- `ksecdd!BCryptDestroyHash` at `0x1400b1f98`
- `ksecdd!BCryptDestroyHash` at `0x1400b1f98`
- `ksecdd!BCryptCloseAlgorithmProvider` at `0x1400b1fc8`
- `ksecdd!BCryptCloseAlgorithmProvider` at `0x1400b1fc8`
- `ksecdd!BCryptFinishHash` at `0x1400b1f81`
- `ksecdd!BCryptFinishHash` at `0x1400b1f81`
- `ksecdd!BCryptOpenAlgorithmProvider` at `0x1400b1e50`
- `ksecdd!BCryptOpenAlgorithmProvider` at `0x1400b1e50`
- `ksecdd!BCryptGetProperty` at `0x1400b1e88`
- `ksecdd!BCryptGetProperty` at `0x1400b1ef0`
- `ksecdd!BCryptGetProperty` at `0x1400b1e88`
- `ksecdd!BCryptGetProperty` at `0x1400b1ef0`

## pseudocode

```c
__int64 __fastcall ComputeHash(
        LPCWSTR pszAlgId,
        ULONG cbInput,
        PUCHAR pbInput,
        ULONG cbSecret,
        __int64 a5,
        ULONG *a6,
        PUCHAR a7)
{
  UCHAR *Pool2; // rdi
  NTSTATUS Property; // ebx
  ULONG *v12; // rsi
  ULONG pcbResult; // [rsp+40h] [rbp-20h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+48h] [rbp-18h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+50h] [rbp-10h] BYREF
  ULONG pbOutput; // [rsp+A8h] [rbp+48h] BYREF

  phAlgorithm = 0;
  Pool2 = 0;
  phHash = 0;
  pbOutput = 0;
  pcbResult = 0;
  Property = BCryptOpenAlgorithmProvider(&phAlgorithm, pszAlgId, 0, cbSecret != 0 ? 8 : 0);
  if ( Property >= 0 )
  {
    Property = BCryptGetProperty(phAlgorithm, L"ObjectLength", (PUCHAR)&pbOutput, 4u, &pcbResult, 0);
    if ( Property >= 0 )
    {
      Pool2 = (UCHAR *)ExAllocatePool2(256, pbOutput, 1095655762);
      if ( Pool2 )
      {
        v12 = a6;
        Property = BCryptGetProperty(phAlgorithm, L"HashDigestLength", (PUCHAR)a6, 4u, &pcbResult, 0);
        if ( Property >= 0 )
        {
          if ( *v12 <= 0x100 )
          {
            Property = BCryptCreateHash(
                         phAlgorithm,
                         &phHash,
                         Pool2,
                         pbOutput,
                         (PUCHAR)(a5 & -(__int64)(cbSecret != 0)),
                         cbSecret,
                         0);
            if ( Property >= 0 )
            {
              Property = BCryptHashData(phHash, pbInput, cbInput, 0);
              if ( Property >= 0 )
                Property = BCryptFinishHash(phHash, a7, *v12, 0);
            }
          }
          else
          {
            Property = -1073741637;
          }
        }
      }
      else
      {
        Property = -1073741801;
      }
    }
  }
  if ( phHash )
    BCryptDestroyHash(phHash);
  if ( Pool2 )
    ExFreePoolWithTag(Pool2, 0x414E6152u);
  if ( phAlgorithm )
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  return (unsigned int)Property;
}

```

## disassembly

```asm
0x1400b1e00  mov     [rsp-28h+arg_0], rbx
0x1400b1e05  mov     [rsp-28h+arg_8], rsi
0x1400b1e0a  push    rbp
0x1400b1e0b  push    rdi
0x1400b1e0c  push    r12
0x1400b1e0e  push    r14
0x1400b1e10  push    r15
0x1400b1e12  mov     rbp, rsp
0x1400b1e15  sub     rsp, 60h
0x1400b1e19  mov     eax, r9d
0x1400b1e1c  mov     [rbp+phAlgorithm], 0
0x1400b1e24  xor     edi, edi
0x1400b1e26  mov     [rbp+phHash], 0
0x1400b1e2e  mov     r14d, r9d
0x1400b1e31  mov     [rbp+pbOutput], edi
0x1400b1e34  neg     eax
0x1400b1e36  mov     [rbp+var_20], edi
0x1400b1e39  mov     r12d, edx
0x1400b1e3c  mov     r15, r8
0x1400b1e3f  sbb     r9d, r9d
0x1400b1e42  mov     rdx, rcx; pszAlgId
0x1400b1e45  and     r9d, 8; dwFlags
0x1400b1e49  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x1400b1e4d  xor     r8d, r8d; pszImplementation
0x1400b1e50  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1400b1e57  nop     dword ptr [rax+rax+00h]
0x1400b1e5c  mov     ebx, eax
0x1400b1e5e  test    eax, eax
0x1400b1e60  js      loc_1400B1F8F
0x1400b1e66  mov     rcx, [rbp+phAlgorithm]; hObject
0x1400b1e6a  lea     rax, [rbp+var_20]
0x1400b1e6e  lea     esi, [rdi+4]
0x1400b1e71  mov     [rsp+60h+dwFlags], edi; dwFlags
0x1400b1e75  mov     r9d, esi; cbOutput
0x1400b1e78  mov     [rsp+60h+pcbResult], rax; pcbResult
0x1400b1e7d  lea     r8, [rbp+pbOutput]; pbOutput
0x1400b1e81  lea     rdx, pszProperty; "ObjectLength"
0x1400b1e88  call    cs:__imp_BCryptGetProperty
0x1400b1e8f  nop     dword ptr [rax+rax+00h]
0x1400b1e94  mov     ebx, eax
0x1400b1e96  test    eax, eax
0x1400b1e98  js      loc_1400B1F8F
0x1400b1e9e  mov     edx, [rbp+pbOutput]
0x1400b1ea1  mov     ecx, 100h
0x1400b1ea6  mov     r8d, 414E6152h
0x1400b1eac  call    cs:__imp_ExAllocatePool2
0x1400b1eb3  nop     dword ptr [rax+rax+00h]
0x1400b1eb8  mov     rdi, rax
0x1400b1ebb  test    rax, rax
0x1400b1ebe  jnz     short loc_1400B1ECA
0x1400b1ec0  mov     ebx, 0C0000017h
0x1400b1ec5  jmp     loc_1400B1F8F
0x1400b1eca  mov     rcx, [rbp+phAlgorithm]; hObject
0x1400b1ece  lea     rax, [rbp+var_20]
0x1400b1ed2  mov     r9d, esi; cbOutput
0x1400b1ed5  mov     [rsp+60h+dwFlags], 0; dwFlags
0x1400b1edd  mov     rsi, [rbp+arg_28]
0x1400b1ee1  lea     rdx, aHashdigestleng; "HashDigestLength"
0x1400b1ee8  mov     r8, rsi; pbOutput
0x1400b1eeb  mov     [rsp+60h+pcbResult], rax; pcbResult
0x1400b1ef0  call    cs:__imp_BCryptGetProperty
0x1400b1ef7  nop     dword ptr [rax+rax+00h]
0x1400b1efc  mov     ebx, eax
0x1400b1efe  test    eax, eax
0x1400b1f00  js      loc_1400B1F8F
0x1400b1f06  cmp     dword ptr [rsi], 100h
0x1400b1f0c  jbe     short loc_1400B1F15
0x1400b1f0e  mov     ebx, 0C00000BBh
0x1400b1f13  jmp     short loc_1400B1F8F
0x1400b1f15  mov     r9d, [rbp+pbOutput]; cbHashObject
0x1400b1f19  lea     rdx, [rbp+phHash]; phHash
0x1400b1f1d  mov     eax, r14d
0x1400b1f20  mov     [rsp+60h+var_30], 0; dwFlags
0x1400b1f28  neg     eax
0x1400b1f2a  mov     [rsp+60h+dwFlags], r14d; cbSecret
0x1400b1f2f  mov     r8, rdi; pbHashObject
0x1400b1f32  sbb     rcx, rcx
0x1400b1f35  and     rcx, [rbp+arg_20]
0x1400b1f39  mov     [rsp+60h+pcbResult], rcx; pbSecret
0x1400b1f3e  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x1400b1f42  call    cs:__imp_BCryptCreateHash
0x1400b1f49  nop     dword ptr [rax+rax+00h]
0x1400b1f4e  mov     ebx, eax
0x1400b1f50  test    eax, eax
0x1400b1f52  js      short loc_1400B1F8F
0x1400b1f54  mov     rcx, [rbp+phHash]; hHash
0x1400b1f58  xor     r9d, r9d; dwFlags
0x1400b1f5b  mov     r8d, r12d; cbInput
0x1400b1f5e  mov     rdx, r15; pbInput
0x1400b1f61  call    cs:__imp_BCryptHashData
0x1400b1f68  nop     dword ptr [rax+rax+00h]
0x1400b1f6d  mov     ebx, eax
0x1400b1f6f  test    eax, eax
0x1400b1f71  js      short loc_1400B1F8F
0x1400b1f73  mov     r8d, [rsi]; cbOutput
0x1400b1f76  xor     r9d, r9d; dwFlags
0x1400b1f79  mov     rdx, [rbp+arg_30]; pbOutput
0x1400b1f7d  mov     rcx, [rbp+phHash]; hHash
0x1400b1f81  call    cs:__imp_BCryptFinishHash
0x1400b1f88  nop     dword ptr [rax+rax+00h]
0x1400b1f8d  mov     ebx, eax
0x1400b1f8f  mov     rcx, [rbp+phHash]; hHash
0x1400b1f93  test    rcx, rcx
0x1400b1f96  jz      short loc_1400B1FA4
0x1400b1f98  call    cs:__imp_BCryptDestroyHash
0x1400b1f9f  nop     dword ptr [rax+rax+00h]
0x1400b1fa4  test    rdi, rdi
0x1400b1fa7  jz      short loc_1400B1FBD
0x1400b1fa9  mov     edx, 414E6152h; Tag
0x1400b1fae  mov     rcx, rdi; P
0x1400b1fb1  call    cs:__imp_ExFreePoolWithTag
0x1400b1fb8  nop     dword ptr [rax+rax+00h]
0x1400b1fbd  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x1400b1fc1  test    rcx, rcx
0x1400b1fc4  jz      short loc_1400B1FD4
0x1400b1fc6  xor     edx, edx; dwFlags
0x1400b1fc8  call    cs:__imp_BCryptCloseAlgorithmProvider
0x1400b1fcf  nop     dword ptr [rax+rax+00h]
0x1400b1fd4  lea     r11, [rsp+60h+var_s0]
0x1400b1fd9  mov     eax, ebx
0x1400b1fdb  mov     rbx, [r11+30h]
0x1400b1fdf  mov     rsi, [r11+38h]
0x1400b1fe3  mov     rsp, r11
0x1400b1fe6  pop     r15
0x1400b1fe8  pop     r14
0x1400b1fea  pop     r12
0x1400b1fec  pop     rdi
0x1400b1fed  pop     rbp
0x1400b1fee  retn
```
