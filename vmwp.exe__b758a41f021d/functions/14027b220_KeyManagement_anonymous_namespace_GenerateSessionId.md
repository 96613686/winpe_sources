# KeyManagement::_anonymous_namespace_::GenerateSessionId

- ea: `0x14027b220`
- end: `0x14027b382`
- name: `KeyManagement::_anonymous_namespace_::GenerateSessionId`
- size: `354`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14027abb0`

## callees

- `0x14011ea40`
- `0x14027b220`

## import_xrefs

- `bcrypt!BCryptOpenAlgorithmProvider` at `0x14027b274`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x14027b274`
- `bcrypt!BCryptFinishHash` at `0x14027b32a`
- `bcrypt!BCryptFinishHash` at `0x14027b32a`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x14027b358`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x14027b358`
- `bcrypt!BCryptDestroyHash` at `0x14027b341`
- `bcrypt!BCryptDestroyHash` at `0x14027b341`
- `bcrypt!BCryptHashData` at `0x14027b30a`
- `bcrypt!BCryptHashData` at `0x14027b30a`
- `bcrypt!BCryptCreateHash` at `0x14027b2e9`
- `bcrypt!BCryptCreateHash` at `0x14027b2e9`
- `bcrypt!BCryptGetProperty` at `0x14027b2b0`
- `bcrypt!BCryptGetProperty` at `0x14027b2b0`

## pseudocode

```c
__int64 __fastcall KeyManagement::_anonymous_namespace_::GenerateSessionId(__int64 a1, int a2, UCHAR *a3)
{
  NTSTATUS Property; // ebx
  BCRYPT_HASH_HANDLE phHash; // [rsp+40h] [rbp-20h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+48h] [rbp-18h] BYREF
  ULONG pcbResult; // [rsp+50h] [rbp-10h] BYREF
  UCHAR pbOutput[4]; // [rsp+54h] [rbp-Ch] BYREF

  phAlgorithm = 0;
  phHash = 0;
  pcbResult = 0;
  *(_DWORD *)pbOutput = 0;
  Property = BCryptOpenAlgorithmProvider(&phAlgorithm, L"SHA256", 0, 0);
  if ( Property >= 0 )
  {
    Property = BCryptGetProperty(phAlgorithm, L"HashDigestLength", pbOutput, 4u, &pcbResult, 0);
    if ( Property >= 0 )
    {
      Property = BCryptCreateHash(phAlgorithm, &phHash, 0, 0, 0, 0, 0);
      if ( Property >= 0 )
      {
        Property = BCryptHashData(phHash, (PUCHAR)(a1 + 4), a2 - 4, 0);
        if ( Property >= 0 )
          Property = BCryptFinishHash(phHash, a3, 0x20u, 0);
      }
    }
  }
  if ( phHash )
    BCryptDestroyHash(phHash);
  if ( phAlgorithm )
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  return Property | 0x10000000u;
}

```

## disassembly

```asm
0x14027b220  push    rbp
0x14027b222  push    rbx
0x14027b223  push    rsi
0x14027b224  push    rdi
0x14027b225  push    r14
0x14027b227  mov     rbp, rsp
0x14027b22a  sub     rsp, 60h
0x14027b22e  mov     rax, cs:__security_cookie
0x14027b235  xor     rax, rsp
0x14027b238  mov     [rbp+var_8], rax
0x14027b23c  mov     rdi, r8
0x14027b23f  mov     [rbp+phAlgorithm], 0
0x14027b247  mov     r14, rdx
0x14027b24a  mov     [rbp+phHash], 0
0x14027b252  mov     rsi, rcx
0x14027b255  mov     [rbp+var_10], 0
0x14027b25c  xor     r8d, r8d; pszImplementation
0x14027b25f  mov     dword ptr [rbp+pbOutput], 0
0x14027b266  lea     rdx, pszAlgId; "SHA256"
0x14027b26d  xor     r9d, r9d; dwFlags
0x14027b270  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x14027b274  call    cs:__imp_BCryptOpenAlgorithmProvider
0x14027b27b  nop     dword ptr [rax+rax+00h]
0x14027b280  mov     ebx, eax
0x14027b282  test    eax, eax
0x14027b284  js      loc_14027B338
0x14027b28a  mov     rcx, [rbp+phAlgorithm]; hObject
0x14027b28e  lea     rax, [rbp+var_10]
0x14027b292  mov     [rsp+60h+dwFlags], 0; dwFlags
0x14027b29a  lea     r8, [rbp+pbOutput]; pbOutput
0x14027b29e  mov     r9d, 4; cbOutput
0x14027b2a4  mov     [rsp+60h+pcbResult], rax; pcbResult
0x14027b2a9  lea     rdx, pszProperty; "HashDigestLength"
0x14027b2b0  call    cs:__imp_BCryptGetProperty
0x14027b2b7  nop     dword ptr [rax+rax+00h]
0x14027b2bc  mov     ebx, eax
0x14027b2be  test    eax, eax
0x14027b2c0  js      short loc_14027B338
0x14027b2c2  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x14027b2c6  lea     rdx, [rbp+phHash]; phHash
0x14027b2ca  mov     [rsp+60h+var_30], 0; dwFlags
0x14027b2d2  xor     r9d, r9d; cbHashObject
0x14027b2d5  mov     [rsp+60h+dwFlags], 0; cbSecret
0x14027b2dd  xor     r8d, r8d; pbHashObject
0x14027b2e0  mov     [rsp+60h+pcbResult], 0; pbSecret
0x14027b2e9  call    cs:__imp_BCryptCreateHash
0x14027b2f0  nop     dword ptr [rax+rax+00h]
0x14027b2f5  mov     ebx, eax
0x14027b2f7  test    eax, eax
0x14027b2f9  js      short loc_14027B338
0x14027b2fb  mov     rcx, [rbp+phHash]; hHash
0x14027b2ff  lea     r8d, [r14-4]; cbInput
0x14027b303  lea     rdx, [rsi+4]; pbInput
0x14027b307  xor     r9d, r9d; dwFlags
0x14027b30a  call    cs:__imp_BCryptHashData
0x14027b311  nop     dword ptr [rax+rax+00h]
0x14027b316  mov     ebx, eax
0x14027b318  test    eax, eax
0x14027b31a  js      short loc_14027B338
0x14027b31c  mov     rcx, [rbp+phHash]; hHash
0x14027b320  xor     r9d, r9d; dwFlags
0x14027b323  mov     rdx, rdi; pbOutput
0x14027b326  lea     r8d, [r9+20h]; cbOutput
0x14027b32a  call    cs:__imp_BCryptFinishHash
0x14027b331  nop     dword ptr [rax+rax+00h]
0x14027b336  mov     ebx, eax
0x14027b338  mov     rcx, [rbp+phHash]; hHash
0x14027b33c  test    rcx, rcx
0x14027b33f  jz      short loc_14027B34D
0x14027b341  call    cs:__imp_BCryptDestroyHash
0x14027b348  nop     dword ptr [rax+rax+00h]
0x14027b34d  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x14027b351  test    rcx, rcx
0x14027b354  jz      short loc_14027B364
0x14027b356  xor     edx, edx; dwFlags
0x14027b358  call    cs:__imp_BCryptCloseAlgorithmProvider
0x14027b35f  nop     dword ptr [rax+rax+00h]
0x14027b364  bts     ebx, 1Ch
0x14027b368  mov     eax, ebx
0x14027b36a  mov     rcx, [rbp+var_8]
0x14027b36e  xor     rcx, rsp; StackCookie
0x14027b371  call    __security_check_cookie
0x14027b376  add     rsp, 60h
0x14027b37a  pop     r14
0x14027b37c  pop     rdi
0x14027b37d  pop     rsi
0x14027b37e  pop     rbx
0x14027b37f  pop     rbp
0x14027b380  retn
```
