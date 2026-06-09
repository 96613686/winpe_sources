# WinNatComputeSessionKeyFromTransportAddr

- ea: `0x14000bf78`
- end: `0x14000c034`
- name: `WinNatComputeSessionKeyFromTransportAddr`
- size: `188`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140009b04`

## import_xrefs

- `NETIO!RtlComputeToeplitzHash` at `0x14000bfb5`
- `NETIO!RtlComputeToeplitzHash` at `0x14000bfd0`
- `NETIO!RtlComputeToeplitzHash` at `0x14000bff5`
- `NETIO!RtlComputeToeplitzHash` at `0x14000c012`
- `NETIO!RtlComputeToeplitzHash` at `0x14000bfb5`
- `NETIO!RtlComputeToeplitzHash` at `0x14000bfd0`
- `NETIO!RtlComputeToeplitzHash` at `0x14000bff5`
- `NETIO!RtlComputeToeplitzHash` at `0x14000c012`

## pseudocode

```c
int __fastcall WinNatComputeSessionKeyFromTransportAddr(__int64 a1, _WORD *a2, _WORD *a3)
{
  unsigned int v3; // esi
  __int64 v4; // rbp
  __int64 v7; // r8
  __int64 v8; // rcx
  int v9; // ebx
  int v10; // eax
  int v11; // ebx

  v3 = 4;
  v4 = a1 + 408;
  v7 = 4;
  v8 = a1 + 408;
  if ( *a2 != 2 )
    v7 = 16;
  v9 = RtlComputeToeplitzHash(v8, a2 + 2, v7, 0);
  v10 = RtlComputeToeplitzHash(v4, a2 + 1, 2, 0);
  if ( *a3 != 2 )
    v3 = 16;
  v11 = v9 ^ v10 ^ RtlComputeToeplitzHash(v4, a3 + 2, v3, 0);
  return v11 ^ RtlComputeToeplitzHash(v4, a3 + 1, 2, 0) | 0x80000000;
}

```

## disassembly

```asm
0x14000bf78  push    rbx
0x14000bf7a  push    rbp
0x14000bf7b  push    rsi
0x14000bf7c  push    rdi
0x14000bf7d  push    r12
0x14000bf7f  push    r14
0x14000bf81  push    r15
0x14000bf83  sub     rsp, 20h
0x14000bf87  mov     esi, 4
0x14000bf8c  lea     rbp, [rcx+198h]
0x14000bf93  mov     r14, r8
0x14000bf96  mov     rdi, rdx
0x14000bf99  mov     r8d, esi
0x14000bf9c  mov     rcx, rbp
0x14000bf9f  lea     r12d, [rsi-2]
0x14000bfa3  cmp     [rdx], r12w
0x14000bfa7  lea     r15d, [rsi+0Ch]
0x14000bfab  cmovnz  r8d, r15d
0x14000bfaf  add     rdx, rsi
0x14000bfb2  xor     r9d, r9d
0x14000bfb5  call    cs:__imp_RtlComputeToeplitzHash
0x14000bfbc  nop     dword ptr [rax+rax+00h]
0x14000bfc1  lea     rdx, [rdi+2]
0x14000bfc5  xor     r9d, r9d
0x14000bfc8  mov     r8d, r12d
0x14000bfcb  mov     rcx, rbp
0x14000bfce  mov     ebx, eax
0x14000bfd0  call    cs:__imp_RtlComputeToeplitzHash
0x14000bfd7  nop     dword ptr [rax+rax+00h]
0x14000bfdc  lea     rdx, [r14+4]
0x14000bfe0  mov     rcx, rbp
0x14000bfe3  mov     edi, eax
0x14000bfe5  xor     edi, ebx
0x14000bfe7  cmp     [r14], r12w
0x14000bfeb  cmovnz  esi, r15d
0x14000bfef  xor     r9d, r9d
0x14000bff2  mov     r8d, esi
0x14000bff5  call    cs:__imp_RtlComputeToeplitzHash
0x14000bffc  nop     dword ptr [rax+rax+00h]
0x14000c001  lea     rdx, [r14+2]
0x14000c005  xor     r9d, r9d
0x14000c008  mov     ebx, eax
0x14000c00a  mov     r8d, r12d
0x14000c00d  mov     rcx, rbp
0x14000c010  xor     ebx, edi
0x14000c012  call    cs:__imp_RtlComputeToeplitzHash
0x14000c019  nop     dword ptr [rax+rax+00h]
0x14000c01e  xor     eax, ebx
0x14000c020  bts     eax, 1Fh
0x14000c024  add     rsp, 20h
0x14000c028  pop     r15
0x14000c02a  pop     r14
0x14000c02c  pop     r12
0x14000c02e  pop     rdi
0x14000c02f  pop     rsi
0x14000c030  pop     rbp
0x14000c031  pop     rbx
0x14000c032  retn
```
