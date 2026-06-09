# WinNatComputeSessionKeyFromSockaddr

- ea: `0x140004c40`
- end: `0x140004d11`
- name: `WinNatComputeSessionKeyFromSockaddr`
- size: `209`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140009b04`

## import_xrefs

- `NETIO!RtlComputeToeplitzHash` at `0x140004c87`
- `NETIO!RtlComputeToeplitzHash` at `0x140004ca5`
- `NETIO!RtlComputeToeplitzHash` at `0x140004ccf`
- `NETIO!RtlComputeToeplitzHash` at `0x140004cef`
- `NETIO!RtlComputeToeplitzHash` at `0x140004c87`
- `NETIO!RtlComputeToeplitzHash` at `0x140004ca5`
- `NETIO!RtlComputeToeplitzHash` at `0x140004ccf`
- `NETIO!RtlComputeToeplitzHash` at `0x140004cef`

## pseudocode

```c
int __fastcall WinNatComputeSessionKeyFromSockaddr(__int64 a1, _WORD *a2, _WORD *a3)
{
  bool v3; // zf
  __int64 v4; // rbp
  __int64 v7; // rsi
  __int64 v8; // r8
  __int64 v9; // rdx
  int v10; // ebx
  int v11; // eax
  __int64 v12; // r8
  int v13; // ebx

  v3 = *a2 == 2;
  v4 = a1 + 408;
  v7 = 2;
  v8 = 4;
  v9 = 2;
  if ( !v3 )
  {
    v9 = 4;
    v8 = 16;
  }
  v10 = RtlComputeToeplitzHash(a1 + 408, &a2[v9], v8, 0);
  v11 = RtlComputeToeplitzHash(v4, a2 + 1, 2, 0);
  v12 = 4;
  if ( *a3 != 2 )
  {
    v7 = 4;
    v12 = 16;
  }
  v13 = v10 ^ v11 ^ RtlComputeToeplitzHash(v4, &a3[v7], v12, 0);
  return v13 ^ RtlComputeToeplitzHash(v4, a3 + 1, 2, 0) | 0x80000000;
}

```

## disassembly

```asm
0x140004c40  push    rbx
0x140004c42  push    rbp
0x140004c43  push    rsi
0x140004c44  push    rdi
0x140004c45  push    r12
0x140004c47  push    r14
0x140004c49  push    r15
0x140004c4b  sub     rsp, 20h
0x140004c4f  cmp     word ptr [rdx], 2
0x140004c53  lea     rbp, [rcx+198h]
0x140004c5a  mov     rdi, rdx
0x140004c5d  mov     r14, r8
0x140004c60  mov     esi, 4
0x140004c65  mov     r15d, 8
0x140004c6b  mov     r8d, esi
0x140004c6e  mov     edx, esi
0x140004c70  cmovnz  edx, r15d
0x140004c74  mov     r12d, 10h
0x140004c7a  cmovnz  r8d, r12d
0x140004c7e  mov     rcx, rbp
0x140004c81  add     rdx, rdi
0x140004c84  xor     r9d, r9d
0x140004c87  call    cs:__imp_RtlComputeToeplitzHash
0x140004c8e  nop     dword ptr [rax+rax+00h]
0x140004c93  lea     rdx, [rdi+2]
0x140004c97  xor     r9d, r9d
0x140004c9a  mov     r8d, 2
0x140004ca0  mov     rcx, rbp
0x140004ca3  mov     ebx, eax
0x140004ca5  call    cs:__imp_RtlComputeToeplitzHash
0x140004cac  nop     dword ptr [rax+rax+00h]
0x140004cb1  mov     r8d, esi
0x140004cb4  mov     rcx, rbp
0x140004cb7  mov     edi, eax
0x140004cb9  xor     edi, ebx
0x140004cbb  cmp     word ptr [r14], 2
0x140004cc0  cmovnz  esi, r15d
0x140004cc4  cmovnz  r8d, r12d
0x140004cc8  xor     r9d, r9d
0x140004ccb  lea     rdx, [r14+rsi]
0x140004ccf  call    cs:__imp_RtlComputeToeplitzHash
0x140004cd6  nop     dword ptr [rax+rax+00h]
0x140004cdb  lea     rdx, [r14+2]
0x140004cdf  xor     r9d, r9d
0x140004ce2  mov     ebx, eax
0x140004ce4  mov     r8d, 2
0x140004cea  mov     rcx, rbp
0x140004ced  xor     ebx, edi
0x140004cef  call    cs:__imp_RtlComputeToeplitzHash
0x140004cf6  nop     dword ptr [rax+rax+00h]
0x140004cfb  xor     eax, ebx
0x140004cfd  bts     eax, 1Fh
0x140004d01  add     rsp, 20h
0x140004d05  pop     r15
0x140004d07  pop     r14
0x140004d09  pop     r12
0x140004d0b  pop     rdi
0x140004d0c  pop     rsi
0x140004d0d  pop     rbp
0x140004d0e  pop     rbx
0x140004d0f  retn
```
