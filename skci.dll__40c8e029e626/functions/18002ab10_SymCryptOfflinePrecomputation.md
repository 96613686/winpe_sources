# SymCryptOfflinePrecomputation

- ea: `0x18002ab10`
- end: `0x18002ab6f`
- name: `SymCryptOfflinePrecomputation`
- size: `95`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180023e94`

## callees

- `0x180029364`
- `0x180029ca8`
- `0x18002ab78`

## pseudocode

```c
__int64 __fastcall SymCryptOfflinePrecomputation(__int64 a1, _BYTE *a2, __int64 a3)
{
  __int64 v6; // rbx
  unsigned int v7; // edx
  int v8; // eax

  v6 = (unsigned int)SymCryptSizeofEcpointEx(*(unsigned int *)(a1 + 36), *(_DWORD *)(a1 + 8) & 0xF);
  v8 = (unsigned int)SymCryptEcpointCreateEx(a2, v6, a1, v7);
  return SymCryptPrecomputation(a1, *(_DWORD *)(a1 + 92), (_QWORD *)(a1 + 104), v8, (__int64)&a2[v6], a3 - v6);
}

```

## disassembly

```asm
0x18002ab10  push    rbx
0x18002ab12  push    rbp
0x18002ab13  push    rsi
0x18002ab14  push    rdi
0x18002ab15  sub     rsp, 38h
0x18002ab19  mov     rdi, rdx
0x18002ab1c  mov     rbp, rcx
0x18002ab1f  mov     edx, [rcx+8]
0x18002ab22  mov     rsi, r8
0x18002ab25  mov     ecx, [rcx+24h]
0x18002ab28  and     edx, 0Fh
0x18002ab2b  call    SymCryptSizeofEcpointEx
0x18002ab30  mov     r9d, edx
0x18002ab33  mov     ebx, eax
0x18002ab35  mov     edx, eax
0x18002ab37  mov     rcx, rdi
0x18002ab3a  mov     r8, rbp
0x18002ab3d  call    SymCryptEcpointCreateEx
0x18002ab42  mov     edx, [rbp+5Ch]
0x18002ab45  lea     rcx, [rbx+rdi]
0x18002ab49  sub     rsi, rbx
0x18002ab4c  lea     r8, [rbp+68h]
0x18002ab50  mov     [rsp+58h+var_30], rsi
0x18002ab55  mov     r9, rax
0x18002ab58  mov     [rsp+58h+var_38], rcx
0x18002ab5d  mov     rcx, rbp
0x18002ab60  call    SymCryptPrecomputation
0x18002ab65  add     rsp, 38h
0x18002ab69  pop     rdi
0x18002ab6a  pop     rsi
0x18002ab6b  pop     rbp
0x18002ab6c  pop     rbx
0x18002ab6d  retn
```
