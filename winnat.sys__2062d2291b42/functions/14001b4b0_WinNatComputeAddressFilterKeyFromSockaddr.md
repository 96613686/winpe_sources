# WinNatComputeAddressFilterKeyFromSockaddr

- ea: `0x14001b4b0`
- end: `0x14001b586`
- name: `WinNatComputeAddressFilterKeyFromSockaddr`
- size: `214`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x14001b150`

## import_xrefs

- `NETIO!RtlComputeToeplitzHash` at `0x14001b4fe`
- `NETIO!RtlComputeToeplitzHash` at `0x14001b519`
- `NETIO!RtlComputeToeplitzHash` at `0x14001b544`
- `NETIO!RtlComputeToeplitzHash` at `0x14001b562`
- `NETIO!RtlComputeToeplitzHash` at `0x14001b4fe`
- `NETIO!RtlComputeToeplitzHash` at `0x14001b519`
- `NETIO!RtlComputeToeplitzHash` at `0x14001b544`
- `NETIO!RtlComputeToeplitzHash` at `0x14001b562`

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
0x14001b4b0  mov     [rsp+arg_8], edx
0x14001b4b4  push    rbx
0x14001b4b5  push    rbp
0x14001b4b6  push    rsi
0x14001b4b7  push    rdi
0x14001b4b8  push    r12
0x14001b4ba  push    r13
0x14001b4bc  push    r14
0x14001b4be  push    r15
0x14001b4c0  sub     rsp, 28h
0x14001b4c4  mov     r13d, 4
0x14001b4ca  lea     rbp, [rcx+198h]
0x14001b4d1  mov     rdi, r8
0x14001b4d4  mov     rsi, r9
0x14001b4d7  mov     r8d, r13d
0x14001b4da  mov     edx, r13d
0x14001b4dd  mov     rcx, rbp
0x14001b4e0  lea     r12d, [r13-2]
0x14001b4e4  cmp     [rdi], r12w
0x14001b4e8  lea     r14d, [r13+4]
0x14001b4ec  lea     r15d, [r13+0Ch]
0x14001b4f0  cmovnz  edx, r14d
0x14001b4f4  cmovnz  r8d, r15d
0x14001b4f8  add     rdx, rdi
0x14001b4fb  xor     r9d, r9d
0x14001b4fe  call    cs:__imp_RtlComputeToeplitzHash
0x14001b505  nop     dword ptr [rax+rax+00h]
0x14001b50a  lea     rdx, [rdi+2]
0x14001b50e  xor     r9d, r9d
0x14001b511  mov     r8d, r12d
0x14001b514  mov     rcx, rbp
0x14001b517  mov     ebx, eax
0x14001b519  call    cs:__imp_RtlComputeToeplitzHash
0x14001b520  nop     dword ptr [rax+rax+00h]
0x14001b525  mov     r8d, r13d
0x14001b528  mov     edx, r13d
0x14001b52b  mov     edi, eax
0x14001b52d  mov     rcx, rbp
0x14001b530  xor     edi, ebx
0x14001b532  cmp     [rsi], r12w
0x14001b536  cmovnz  edx, r14d
0x14001b53a  cmovnz  r8d, r15d
0x14001b53e  add     rdx, rsi
0x14001b541  xor     r9d, r9d
0x14001b544  call    cs:__imp_RtlComputeToeplitzHash
0x14001b54b  nop     dword ptr [rax+rax+00h]
0x14001b550  xor     r9d, r9d
0x14001b553  lea     rdx, [rsp+68h+arg_8]
0x14001b558  mov     ebx, eax
0x14001b55a  mov     r8d, r13d
0x14001b55d  mov     rcx, rbp
0x14001b560  xor     ebx, edi
0x14001b562  call    cs:__imp_RtlComputeToeplitzHash
0x14001b569  nop     dword ptr [rax+rax+00h]
0x14001b56e  xor     eax, ebx
0x14001b570  bts     eax, 1Fh
0x14001b574  add     rsp, 28h
0x14001b578  pop     r15
0x14001b57a  pop     r14
0x14001b57c  pop     r13
0x14001b57e  pop     r12
0x14001b580  pop     rdi
0x14001b581  pop     rsi
0x14001b582  pop     rbp
0x14001b583  pop     rbx
0x14001b584  retn
```
