# SkmmInitializePageEncryption

- ea: `0x140086198`
- end: `0x140086279`
- name: `SkmmInitializePageEncryption`
- size: `225`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400b86ec`

## callees

- `0x140086198`
- `0x1400bfc44`

## import_xrefs

- `cng!BCryptOpenAlgorithmProvider` at `0x1400861c9`
- `cng!BCryptOpenAlgorithmProvider` at `0x1400861c9`
- `cng!BCryptCreateHash` at `0x14008621a`
- `cng!BCryptCreateHash` at `0x14008621a`

## pseudocode

```c
NTSTATUS SkmmInitializePageEncryption()
{
  NTSTATUS result; // eax
  __int64 i; // rbx
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+50h] [rbp+8h] BYREF

  phAlgorithm = 0;
  if ( (SkmiFlags & 0x10000) != 0 )
  {
    result = BCryptOpenAlgorithmProvider(&phAlgorithm, L"SHA256", 0, 0x21u);
    if ( result >= 0 )
    {
      for ( i = 0; (unsigned int)i < (unsigned int)SkeNumberProcessors; i = (unsigned int)(i + 1) )
        BCryptCreateHash(phAlgorithm, (BCRYPT_HASH_HANDLE *)(SkeProcessorBlock[i] + 104), 0, 0, 0, 0, 0x20u);
      return 0;
    }
  }
  else
  {
    result = SkPreparePageEncryption(4, 0, SkmiPageEncryptionContext, 0, 0, 0, 0);
    if ( result >= 0 )
      _InterlockedOr(&SkmiFlags, 0x100u);
  }
  return result;
}

```

## disassembly

```asm
0x140086198  push    rbx
0x14008619a  sub     rsp, 40h
0x14008619e  test    byte ptr cs:SkmiFlags+2, 1
0x1400861a5  mov     [rsp+48h+phAlgorithm], 0
0x1400861ae  jz      loc_140086234
0x1400861b4  mov     r9d, 21h ; '!'; dwFlags
0x1400861ba  lea     rdx, pszAlgId; "SHA256"
0x1400861c1  xor     r8d, r8d; pszImplementation
0x1400861c4  lea     rcx, [rsp+48h+phAlgorithm]; phAlgorithm
0x1400861c9  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1400861d0  nop     dword ptr [rax+rax+00h]
0x1400861d5  test    eax, eax
0x1400861d7  js      loc_140086272
0x1400861dd  xor     ebx, ebx
0x1400861df  cmp     cs:SkeNumberProcessors, ebx
0x1400861e5  jbe     short loc_140086230
0x1400861e7  mov     rcx, [rsp+48h+phAlgorithm]; hAlgorithm
0x1400861ec  lea     rdx, SkeProcessorBlock
0x1400861f3  mov     rdx, [rdx+rbx*8]
0x1400861f7  xor     r9d, r9d; cbHashObject
0x1400861fa  mov     [rsp+48h+dwFlags], 20h ; ' '; dwFlags
0x140086202  add     rdx, 68h ; 'h'; phHash
0x140086206  mov     [rsp+48h+cbSecret], 0; cbSecret
0x14008620e  xor     r8d, r8d; pbHashObject
0x140086211  mov     [rsp+48h+pbSecret], 0; pbSecret
0x14008621a  call    cs:__imp_BCryptCreateHash
0x140086221  nop     dword ptr [rax+rax+00h]
0x140086226  inc     ebx
0x140086228  cmp     ebx, cs:SkeNumberProcessors
0x14008622e  jb      short loc_1400861E7
0x140086230  xor     eax, eax
0x140086232  jmp     short loc_140086272
0x140086234  xor     edx, edx
0x140086236  mov     qword ptr [rsp+48h+dwFlags], 0
0x14008623f  mov     qword ptr [rsp+48h+cbSecret], 0
0x140086248  lea     r8, SkmiPageEncryptionContext
0x14008624f  xor     r9d, r9d
0x140086252  mov     [rsp+48h+pbSecret], 0
0x14008625b  lea     ecx, [rdx+4]
0x14008625e  call    SkPreparePageEncryption
0x140086263  test    eax, eax
0x140086265  js      short loc_140086272
0x140086267  lock or cs:SkmiFlags, 100h
0x140086272  add     rsp, 40h
0x140086276  pop     rbx
0x140086277  retn
```
