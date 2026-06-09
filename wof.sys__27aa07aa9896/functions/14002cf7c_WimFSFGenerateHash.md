# WimFSFGenerateHash

- ea: `0x14002cf7c`
- end: `0x14002d04c`
- name: `WimFSFGenerateHash`
- size: `208`
- prototype: `__int64 __fastcall(PUCHAR pbInput, ULONG cbInput, PUCHAR pbOutput)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x14002c58c`
- `0x14002d644`

## callees

- `0x14002cf7c`

## import_xrefs

- `cng!BCryptCreateHash` at `0x14002cfbc`
- `cng!BCryptCreateHash` at `0x14002cfbc`
- `cng!BCryptHashData` at `0x14002cff0`
- `cng!BCryptHashData` at `0x14002cff0`
- `cng!BCryptDestroyHash` at `0x14002d033`
- `cng!BCryptDestroyHash` at `0x14002d033`
- `cng!BCryptFinishHash` at `0x14002d019`
- `cng!BCryptFinishHash` at `0x14002d019`

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
0x14002cf7c  mov     rax, rsp
0x14002cf7f  push    rbx
0x14002cf80  push    rsi
0x14002cf81  push    rdi
0x14002cf82  push    r14
0x14002cf84  sub     rsp, 58h
0x14002cf88  mov     dword ptr [rax-48h], 0
0x14002cf8f  xor     r9d, r9d; cbHashObject
0x14002cf92  mov     rbx, r8
0x14002cf95  mov     dword ptr [rax-50h], 0
0x14002cf9c  mov     edi, edx
0x14002cf9e  mov     qword ptr [rax-38h], 0
0x14002cfa6  mov     rsi, rcx
0x14002cfa9  mov     qword ptr [rax-58h], 0
0x14002cfb1  lea     ecx, [r9+31h]; hAlgorithm
0x14002cfb5  xor     r8d, r8d; pbHashObject
0x14002cfb8  lea     rdx, [rax-38h]; phHash
0x14002cfbc  call    cs:__imp_BCryptCreateHash
0x14002cfc3  nop     dword ptr [rax+rax+00h]
0x14002cfc8  mov     r14d, 7
0x14002cfce  test    eax, eax
0x14002cfd0  jns     short loc_14002CFD7
0x14002cfd2  mov     ecx, r14d
0x14002cfd5  int     29h; Win8: RtlFailFast(ecx)
0x14002cfd7  mov     rcx, [rsp+78h+hHash]; hHash
0x14002cfdc  xorps   xmm0, xmm0
0x14002cfdf  xor     eax, eax
0x14002cfe1  xor     r9d, r9d; dwFlags
0x14002cfe4  movups  xmmword ptr [rbx], xmm0
0x14002cfe7  mov     r8d, edi; cbInput
0x14002cfea  mov     [rbx+10h], eax
0x14002cfed  mov     rdx, rsi; pbInput
0x14002cff0  call    cs:__imp_BCryptHashData
0x14002cff7  nop     dword ptr [rax+rax+00h]
0x14002cffc  test    eax, eax
0x14002cffe  jns     short loc_14002D005
0x14002d000  mov     rcx, r14
0x14002d003  int     29h; Win8: RtlFailFast(ecx)
0x14002d005  test    rbx, rbx
0x14002d008  jz      short loc_14002D02E
0x14002d00a  mov     rcx, [rsp+78h+hHash]; hHash
0x14002d00f  xor     r9d, r9d; dwFlags
0x14002d012  mov     rdx, rbx; pbOutput
0x14002d015  lea     r8d, [r9+14h]; cbOutput
0x14002d019  call    cs:__imp_BCryptFinishHash
0x14002d020  nop     dword ptr [rax+rax+00h]
0x14002d025  test    eax, eax
0x14002d027  jns     short loc_14002D02E
0x14002d029  mov     rcx, r14
0x14002d02c  int     29h; Win8: RtlFailFast(ecx)
0x14002d02e  mov     rcx, [rsp+78h+hHash]; hHash
0x14002d033  call    cs:__imp_BCryptDestroyHash
0x14002d03a  nop     dword ptr [rax+rax+00h]
0x14002d03f  xor     eax, eax
0x14002d041  add     rsp, 58h
0x14002d045  pop     r14
0x14002d047  pop     rdi
0x14002d048  pop     rsi
0x14002d049  pop     rbx
0x14002d04a  retn
```
