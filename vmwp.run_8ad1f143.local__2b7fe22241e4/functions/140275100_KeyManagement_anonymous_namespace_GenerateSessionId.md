# KeyManagement::_anonymous_namespace_::GenerateSessionId

- ea: `0x140275100`
- end: `0x140275262`
- name: `KeyManagement::_anonymous_namespace_::GenerateSessionId`
- size: `354`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140274a90`

## callees

- `0x140132960`
- `0x140275100`

## import_xrefs

- `bcrypt!BCryptFinishHash` at `0x14027520a`
- `bcrypt!BCryptFinishHash` at `0x14027520a`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x140275238`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x140275238`
- `bcrypt!BCryptDestroyHash` at `0x140275221`
- `bcrypt!BCryptDestroyHash` at `0x140275221`
- `bcrypt!BCryptHashData` at `0x1402751ea`
- `bcrypt!BCryptHashData` at `0x1402751ea`
- `bcrypt!BCryptCreateHash` at `0x1402751c9`
- `bcrypt!BCryptCreateHash` at `0x1402751c9`
- `bcrypt!BCryptGetProperty` at `0x140275190`
- `bcrypt!BCryptGetProperty` at `0x140275190`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x140275154`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x140275154`

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
0x140275100  push    rbp
0x140275102  push    rbx
0x140275103  push    rsi
0x140275104  push    rdi
0x140275105  push    r14
0x140275107  mov     rbp, rsp
0x14027510a  sub     rsp, 60h
0x14027510e  mov     rax, cs:__security_cookie
0x140275115  xor     rax, rsp
0x140275118  mov     [rbp+var_8], rax
0x14027511c  mov     rdi, r8
0x14027511f  mov     [rbp+phAlgorithm], 0
0x140275127  mov     r14, rdx
0x14027512a  mov     [rbp+phHash], 0
0x140275132  mov     rsi, rcx
0x140275135  mov     [rbp+var_10], 0
0x14027513c  xor     r8d, r8d; pszImplementation
0x14027513f  mov     dword ptr [rbp+pbOutput], 0
0x140275146  lea     rdx, pszAlgId; "SHA256"
0x14027514d  xor     r9d, r9d; dwFlags
0x140275150  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x140275154  call    cs:__imp_BCryptOpenAlgorithmProvider
0x14027515b  nop     dword ptr [rax+rax+00h]
0x140275160  mov     ebx, eax
0x140275162  test    eax, eax
0x140275164  js      loc_140275218
0x14027516a  mov     rcx, [rbp+phAlgorithm]; hObject
0x14027516e  lea     rax, [rbp+var_10]
0x140275172  mov     [rsp+60h+dwFlags], 0; dwFlags
0x14027517a  lea     r8, [rbp+pbOutput]; pbOutput
0x14027517e  mov     r9d, 4; cbOutput
0x140275184  mov     [rsp+60h+pcbResult], rax; pcbResult
0x140275189  lea     rdx, pszProperty; "HashDigestLength"
0x140275190  call    cs:__imp_BCryptGetProperty
0x140275197  nop     dword ptr [rax+rax+00h]
0x14027519c  mov     ebx, eax
0x14027519e  test    eax, eax
0x1402751a0  js      short loc_140275218
0x1402751a2  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x1402751a6  lea     rdx, [rbp+phHash]; phHash
0x1402751aa  mov     [rsp+60h+var_30], 0; dwFlags
0x1402751b2  xor     r9d, r9d; cbHashObject
0x1402751b5  mov     [rsp+60h+dwFlags], 0; cbSecret
0x1402751bd  xor     r8d, r8d; pbHashObject
0x1402751c0  mov     [rsp+60h+pcbResult], 0; pbSecret
0x1402751c9  call    cs:__imp_BCryptCreateHash
0x1402751d0  nop     dword ptr [rax+rax+00h]
0x1402751d5  mov     ebx, eax
0x1402751d7  test    eax, eax
0x1402751d9  js      short loc_140275218
0x1402751db  mov     rcx, [rbp+phHash]; hHash
0x1402751df  lea     r8d, [r14-4]; cbInput
0x1402751e3  lea     rdx, [rsi+4]; pbInput
0x1402751e7  xor     r9d, r9d; dwFlags
0x1402751ea  call    cs:__imp_BCryptHashData
0x1402751f1  nop     dword ptr [rax+rax+00h]
0x1402751f6  mov     ebx, eax
0x1402751f8  test    eax, eax
0x1402751fa  js      short loc_140275218
0x1402751fc  mov     rcx, [rbp+phHash]; hHash
0x140275200  xor     r9d, r9d; dwFlags
0x140275203  mov     rdx, rdi; pbOutput
0x140275206  lea     r8d, [r9+20h]; cbOutput
0x14027520a  call    cs:__imp_BCryptFinishHash
0x140275211  nop     dword ptr [rax+rax+00h]
0x140275216  mov     ebx, eax
0x140275218  mov     rcx, [rbp+phHash]; hHash
0x14027521c  test    rcx, rcx
0x14027521f  jz      short loc_14027522D
0x140275221  call    cs:__imp_BCryptDestroyHash
0x140275228  nop     dword ptr [rax+rax+00h]
0x14027522d  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x140275231  test    rcx, rcx
0x140275234  jz      short loc_140275244
0x140275236  xor     edx, edx; dwFlags
0x140275238  call    cs:__imp_BCryptCloseAlgorithmProvider
0x14027523f  nop     dword ptr [rax+rax+00h]
0x140275244  bts     ebx, 1Ch
0x140275248  mov     eax, ebx
0x14027524a  mov     rcx, [rbp+var_8]
0x14027524e  xor     rcx, rsp; StackCookie
0x140275251  call    __security_check_cookie
0x140275256  add     rsp, 60h
0x14027525a  pop     r14
0x14027525c  pop     rdi
0x14027525d  pop     rsi
0x14027525e  pop     rbx
0x14027525f  pop     rbp
0x140275260  retn
```
