# WinNatComputeAddressFilterKeyFromTransportAddr

- ea: `0x14000b80c`
- end: `0x14000b8c9`
- name: `WinNatComputeAddressFilterKeyFromTransportAddr`
- size: `189`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140009b04`

## import_xrefs

- `NETIO!RtlComputeToeplitzHash` at `0x14000b849`
- `NETIO!RtlComputeToeplitzHash` at `0x14000b864`
- `NETIO!RtlComputeToeplitzHash` at `0x14000b88a`
- `NETIO!RtlComputeToeplitzHash` at `0x14000b8a9`
- `NETIO!RtlComputeToeplitzHash` at `0x14000b849`
- `NETIO!RtlComputeToeplitzHash` at `0x14000b864`
- `NETIO!RtlComputeToeplitzHash` at `0x14000b88a`
- `NETIO!RtlComputeToeplitzHash` at `0x14000b8a9`

## pseudocode

```c
int __fastcall WinNatComputeAddressFilterKeyFromTransportAddr(__int64 a1, int a2, _WORD *a3, _WORD *a4)
{
  __int64 v5; // rbp
  __int64 v6; // r8
  __int64 v8; // rcx
  int v9; // ebx
  int v10; // eax
  __int64 v11; // r8
  int v12; // ebx
  int v14; // [rsp+68h] [rbp+10h] BYREF

  v14 = a2;
  v5 = a1 + 408;
  v6 = 4;
  v8 = a1 + 408;
  if ( *a3 != 2 )
    v6 = 16;
  v9 = RtlComputeToeplitzHash(v8, a3 + 2, v6, 0);
  v10 = RtlComputeToeplitzHash(v5, a3 + 1, 2, 0);
  v11 = 4;
  if ( *a4 != 2 )
    v11 = 16;
  v12 = v9 ^ v10 ^ RtlComputeToeplitzHash(v5, a4 + 2, v11, 0);
  return v12 ^ RtlComputeToeplitzHash(v5, &v14, 4, 0) | 0x80000000;
}

```

## disassembly

```asm
0x14000b80c  mov     [rsp+arg_8], edx
0x14000b810  push    rbx
0x14000b811  push    rbp
0x14000b812  push    rsi
0x14000b813  push    rdi
0x14000b814  push    r14
0x14000b816  push    r15
0x14000b818  sub     rsp, 28h
0x14000b81c  mov     rdi, r8
0x14000b81f  lea     rbp, [rcx+198h]
0x14000b826  mov     r8d, 4
0x14000b82c  mov     rsi, r9
0x14000b82f  mov     rcx, rbp
0x14000b832  lea     rdx, [rdi+4]
0x14000b836  lea     r14d, [r8-2]
0x14000b83a  cmp     [rdi], r14w
0x14000b83e  lea     r15d, [r8+0Ch]
0x14000b842  cmovnz  r8d, r15d
0x14000b846  xor     r9d, r9d
0x14000b849  call    cs:__imp_RtlComputeToeplitzHash
0x14000b850  nop     dword ptr [rax+rax+00h]
0x14000b855  lea     rdx, [rdi+2]
0x14000b859  xor     r9d, r9d
0x14000b85c  mov     r8d, r14d
0x14000b85f  mov     rcx, rbp
0x14000b862  mov     ebx, eax
0x14000b864  call    cs:__imp_RtlComputeToeplitzHash
0x14000b86b  nop     dword ptr [rax+rax+00h]
0x14000b870  lea     r8d, [r15-0Ch]
0x14000b874  mov     rcx, rbp
0x14000b877  mov     edi, eax
0x14000b879  lea     rdx, [rsi+4]
0x14000b87d  xor     edi, ebx
0x14000b87f  cmp     [rsi], r14w
0x14000b883  cmovnz  r8d, r15d
0x14000b887  xor     r9d, r9d
0x14000b88a  call    cs:__imp_RtlComputeToeplitzHash
0x14000b891  nop     dword ptr [rax+rax+00h]
0x14000b896  xor     r9d, r9d
0x14000b899  lea     r8d, [r15-0Ch]
0x14000b89d  mov     ebx, eax
0x14000b89f  lea     rdx, [rsp+58h+arg_8]
0x14000b8a4  mov     rcx, rbp
0x14000b8a7  xor     ebx, edi
0x14000b8a9  call    cs:__imp_RtlComputeToeplitzHash
0x14000b8b0  nop     dword ptr [rax+rax+00h]
0x14000b8b5  xor     eax, ebx
0x14000b8b7  bts     eax, 1Fh
0x14000b8bb  add     rsp, 28h
0x14000b8bf  pop     r15
0x14000b8c1  pop     r14
0x14000b8c3  pop     rdi
0x14000b8c4  pop     rsi
0x14000b8c5  pop     rbp
0x14000b8c6  pop     rbx
0x14000b8c7  retn
```
