# WinNatComputeAddressFilterKeyFromSockaddr

- ea: `0x14001afd0`
- end: `0x14001b0a6`
- name: `WinNatComputeAddressFilterKeyFromSockaddr`
- size: `214`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x14001ac70`

## import_xrefs

- `NETIO!RtlComputeToeplitzHash` at `0x14001b01e`
- `NETIO!RtlComputeToeplitzHash` at `0x14001b039`
- `NETIO!RtlComputeToeplitzHash` at `0x14001b064`
- `NETIO!RtlComputeToeplitzHash` at `0x14001b082`
- `NETIO!RtlComputeToeplitzHash` at `0x14001b01e`
- `NETIO!RtlComputeToeplitzHash` at `0x14001b039`
- `NETIO!RtlComputeToeplitzHash` at `0x14001b064`
- `NETIO!RtlComputeToeplitzHash` at `0x14001b082`

## pseudocode

```c
int __fastcall WinNatComputeAddressFilterKeyFromSockaddr(__int64 a1, int a2, _WORD *a3, _WORD *a4)
{
  __int64 v4; // rbp
  __int64 v7; // r8
  __int64 v8; // rdx
  __int64 v9; // rcx
  int v10; // ebx
  int v11; // eax
  __int64 v12; // r8
  __int64 v13; // rdx
  int v14; // ebx
  int v16; // [rsp+78h] [rbp+10h] BYREF

  v16 = a2;
  v4 = a1 + 408;
  v7 = 4;
  v8 = 2;
  v9 = a1 + 408;
  if ( *a3 != 2 )
  {
    v8 = 4;
    v7 = 16;
  }
  v10 = RtlComputeToeplitzHash(v9, &a3[v8], v7, 0);
  v11 = RtlComputeToeplitzHash(v4, a3 + 1, 2, 0);
  v12 = 4;
  v13 = 2;
  if ( *a4 != 2 )
  {
    v13 = 4;
    v12 = 16;
  }
  v14 = v10 ^ v11 ^ RtlComputeToeplitzHash(v4, &a4[v13], v12, 0);
  return v14 ^ RtlComputeToeplitzHash(v4, &v16, 4, 0) | 0x80000000;
}

```

## disassembly

```asm
0x14001afd0  mov     [rsp+arg_8], edx
0x14001afd4  push    rbx
0x14001afd5  push    rbp
0x14001afd6  push    rsi
0x14001afd7  push    rdi
0x14001afd8  push    r12
0x14001afda  push    r13
0x14001afdc  push    r14
0x14001afde  push    r15
0x14001afe0  sub     rsp, 28h
0x14001afe4  mov     r13d, 4
0x14001afea  lea     rbp, [rcx+198h]
0x14001aff1  mov     rdi, r8
0x14001aff4  mov     rsi, r9
0x14001aff7  mov     r8d, r13d
0x14001affa  mov     edx, r13d
0x14001affd  mov     rcx, rbp
0x14001b000  lea     r12d, [r13-2]
0x14001b004  cmp     [rdi], r12w
0x14001b008  lea     r14d, [r13+4]
0x14001b00c  lea     r15d, [r13+0Ch]
0x14001b010  cmovnz  edx, r14d
0x14001b014  cmovnz  r8d, r15d
0x14001b018  add     rdx, rdi
0x14001b01b  xor     r9d, r9d
0x14001b01e  call    cs:__imp_RtlComputeToeplitzHash
0x14001b025  nop     dword ptr [rax+rax+00h]
0x14001b02a  lea     rdx, [rdi+2]
0x14001b02e  xor     r9d, r9d
0x14001b031  mov     r8d, r12d
0x14001b034  mov     rcx, rbp
0x14001b037  mov     ebx, eax
0x14001b039  call    cs:__imp_RtlComputeToeplitzHash
0x14001b040  nop     dword ptr [rax+rax+00h]
0x14001b045  mov     r8d, r13d
0x14001b048  mov     edx, r13d
0x14001b04b  mov     edi, eax
0x14001b04d  mov     rcx, rbp
0x14001b050  xor     edi, ebx
0x14001b052  cmp     [rsi], r12w
0x14001b056  cmovnz  edx, r14d
0x14001b05a  cmovnz  r8d, r15d
0x14001b05e  add     rdx, rsi
0x14001b061  xor     r9d, r9d
0x14001b064  call    cs:__imp_RtlComputeToeplitzHash
0x14001b06b  nop     dword ptr [rax+rax+00h]
0x14001b070  xor     r9d, r9d
0x14001b073  lea     rdx, [rsp+68h+arg_8]
0x14001b078  mov     ebx, eax
0x14001b07a  mov     r8d, r13d
0x14001b07d  mov     rcx, rbp
0x14001b080  xor     ebx, edi
0x14001b082  call    cs:__imp_RtlComputeToeplitzHash
0x14001b089  nop     dword ptr [rax+rax+00h]
0x14001b08e  xor     eax, ebx
0x14001b090  bts     eax, 1Fh
0x14001b094  add     rsp, 28h
0x14001b098  pop     r15
0x14001b09a  pop     r14
0x14001b09c  pop     r13
0x14001b09e  pop     r12
0x14001b0a0  pop     rdi
0x14001b0a1  pop     rsi
0x14001b0a2  pop     rbp
0x14001b0a3  pop     rbx
0x14001b0a4  retn
```
