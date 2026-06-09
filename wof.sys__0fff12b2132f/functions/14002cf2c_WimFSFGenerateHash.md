# WimFSFGenerateHash

- ea: `0x14002cf2c`
- end: `0x14002cffc`
- name: `WimFSFGenerateHash`
- size: `208`
- prototype: `__int64 __fastcall(PUCHAR pbInput, ULONG cbInput, PUCHAR pbOutput)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x14002c53c`
- `0x14002d5f4`

## callees

- `0x14002cf2c`

## import_xrefs

- `cng!BCryptCreateHash` at `0x14002cf6c`
- `cng!BCryptCreateHash` at `0x14002cf6c`
- `cng!BCryptHashData` at `0x14002cfa0`
- `cng!BCryptHashData` at `0x14002cfa0`
- `cng!BCryptDestroyHash` at `0x14002cfe3`
- `cng!BCryptDestroyHash` at `0x14002cfe3`
- `cng!BCryptFinishHash` at `0x14002cfc9`
- `cng!BCryptFinishHash` at `0x14002cfc9`

## pseudocode

```c
__int64 __fastcall WimFSFGenerateHash(PUCHAR pbInput, ULONG cbInput, UCHAR *pbOutput)
{
  BCRYPT_HASH_HANDLE v6; // rcx
  BCRYPT_HASH_HANDLE hHash; // [rsp+40h] [rbp-38h] BYREF

  hHash = 0;
  if ( BCryptCreateHash((BCRYPT_ALG_HANDLE)0x31, &hHash, 0, 0, 0, 0, 0) < 0 )
    __fastfail(7u);
  v6 = hHash;
  *(_OWORD *)pbOutput = 0;
  *((_DWORD *)pbOutput + 4) = 0;
  if ( BCryptHashData(v6, pbInput, cbInput, 0) < 0 )
    __fastfail(7u);
  if ( pbOutput && BCryptFinishHash(hHash, pbOutput, 0x14u, 0) < 0 )
    __fastfail(7u);
  BCryptDestroyHash(hHash);
  return 0;
}

```

## disassembly

```asm
0x14002cf2c  mov     rax, rsp
0x14002cf2f  push    rbx
0x14002cf30  push    rsi
0x14002cf31  push    rdi
0x14002cf32  push    r14
0x14002cf34  sub     rsp, 58h
0x14002cf38  mov     dword ptr [rax-48h], 0
0x14002cf3f  xor     r9d, r9d; cbHashObject
0x14002cf42  mov     rbx, r8
0x14002cf45  mov     dword ptr [rax-50h], 0
0x14002cf4c  mov     edi, edx
0x14002cf4e  mov     qword ptr [rax-38h], 0
0x14002cf56  mov     rsi, rcx
0x14002cf59  mov     qword ptr [rax-58h], 0
0x14002cf61  lea     ecx, [r9+31h]; hAlgorithm
0x14002cf65  xor     r8d, r8d; pbHashObject
0x14002cf68  lea     rdx, [rax-38h]; phHash
0x14002cf6c  call    cs:__imp_BCryptCreateHash
0x14002cf73  nop     dword ptr [rax+rax+00h]
0x14002cf78  mov     r14d, 7
0x14002cf7e  test    eax, eax
0x14002cf80  jns     short loc_14002CF87
0x14002cf82  mov     ecx, r14d
0x14002cf85  int     29h; Win8: RtlFailFast(ecx)
0x14002cf87  mov     rcx, [rsp+78h+hHash]; hHash
0x14002cf8c  xorps   xmm0, xmm0
0x14002cf8f  xor     eax, eax
0x14002cf91  xor     r9d, r9d; dwFlags
0x14002cf94  movups  xmmword ptr [rbx], xmm0
0x14002cf97  mov     r8d, edi; cbInput
0x14002cf9a  mov     [rbx+10h], eax
0x14002cf9d  mov     rdx, rsi; pbInput
0x14002cfa0  call    cs:__imp_BCryptHashData
0x14002cfa7  nop     dword ptr [rax+rax+00h]
0x14002cfac  test    eax, eax
0x14002cfae  jns     short loc_14002CFB5
0x14002cfb0  mov     rcx, r14
0x14002cfb3  int     29h; Win8: RtlFailFast(ecx)
0x14002cfb5  test    rbx, rbx
0x14002cfb8  jz      short loc_14002CFDE
0x14002cfba  mov     rcx, [rsp+78h+hHash]; hHash
0x14002cfbf  xor     r9d, r9d; dwFlags
0x14002cfc2  mov     rdx, rbx; pbOutput
0x14002cfc5  lea     r8d, [r9+14h]; cbOutput
0x14002cfc9  call    cs:__imp_BCryptFinishHash
0x14002cfd0  nop     dword ptr [rax+rax+00h]
0x14002cfd5  test    eax, eax
0x14002cfd7  jns     short loc_14002CFDE
0x14002cfd9  mov     rcx, r14
0x14002cfdc  int     29h; Win8: RtlFailFast(ecx)
0x14002cfde  mov     rcx, [rsp+78h+hHash]; hHash
0x14002cfe3  call    cs:__imp_BCryptDestroyHash
0x14002cfea  nop     dword ptr [rax+rax+00h]
0x14002cfef  xor     eax, eax
0x14002cff1  add     rsp, 58h
0x14002cff5  pop     r14
0x14002cff7  pop     rdi
0x14002cff8  pop     rsi
0x14002cff9  pop     rbx
0x14002cffa  retn
```
