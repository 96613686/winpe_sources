# SymCryptPrecomputation

- ea: `0x18002ab78`
- end: `0x18002abf9`
- name: `SymCryptPrecomputation`
- size: `129`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180029fa0`
- `0x18002a4b0`
- `0x18002ab10`

## callees

- `0x180029d18`
- `0x180029d58`
- `0x18002ab78`

## pseudocode

```c
__int64 __fastcall SymCryptPrecomputation(int a1, unsigned int a2, _QWORD *a3, int a4, __int64 a5, __int64 a6)
{
  __int64 result; // rax
  unsigned int i; // ebx

  result = SymCryptEcpointDouble(a1, *a3, a4, a4, a5, a6);
  for ( i = 1; i < a2; ++i )
    result = SymCryptEcpointAddDiffNonZero(a1, a4, a3[i - 1], a3[i], a5, a6);
  return result;
}

```

## disassembly

```asm
0x18002ab78  push    rbx
0x18002ab7a  push    rbp
0x18002ab7b  push    rsi
0x18002ab7c  push    rdi
0x18002ab7d  push    r12
0x18002ab7f  push    r14
0x18002ab81  push    r15
0x18002ab83  sub     rsp, 30h
0x18002ab87  mov     r15, [rsp+68h+arg_28]
0x18002ab8f  mov     rdi, r8
0x18002ab92  mov     r12, [rsp+68h+arg_20]
0x18002ab9a  mov     ebp, edx
0x18002ab9c  mov     [rsp+68h+var_40], r15
0x18002aba1  mov     r8, r9
0x18002aba4  mov     rsi, r9
0x18002aba7  mov     [rsp+68h+var_48], r12
0x18002abac  mov     rdx, [rdi]
0x18002abaf  mov     r14, rcx
0x18002abb2  call    SymCryptEcpointDouble
0x18002abb7  mov     ebx, 1
0x18002abbc  cmp     ebp, ebx
0x18002abbe  jbe     short loc_18002ABE9
0x18002abc0  lea     eax, [rbx-1]
0x18002abc3  mov     r9d, ebx
0x18002abc6  mov     r8, [rdi+rax*8]
0x18002abca  mov     rdx, rsi
0x18002abcd  mov     [rsp+68h+var_40], r15
0x18002abd2  mov     rcx, r14
0x18002abd5  mov     [rsp+68h+var_48], r12
0x18002abda  mov     r9, [rdi+r9*8]
0x18002abde  call    SymCryptEcpointAddDiffNonZero
0x18002abe3  inc     ebx
0x18002abe5  cmp     ebx, ebp
0x18002abe7  jb      short loc_18002ABC0
0x18002abe9  add     rsp, 30h
0x18002abed  pop     r15
0x18002abef  pop     r14
0x18002abf1  pop     r12
0x18002abf3  pop     rdi
0x18002abf4  pop     rsi
0x18002abf5  pop     rbp
0x18002abf6  pop     rbx
0x18002abf7  retn
```
