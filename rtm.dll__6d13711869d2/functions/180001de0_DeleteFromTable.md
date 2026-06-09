# DeleteFromTable

- ea: `0x180001de0`
- end: `0x180001eee`
- name: `DeleteFromTable`
- size: `270`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180008ba0`
- `0x18000c560`
- `0x18000d9d0`

## callees

- `0x1800018c8`
- `0x1800019bc`
- `0x180001de0`
- `0x180002560`
- `0x18000270c`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x180001ec9`
- `KERNEL32!GetProcessHeap` at `0x180001ec9`
- `KERNEL32!HeapFree` at `0x180001ed7`
- `KERNEL32!HeapFree` at `0x180001ed7`

## pseudocode

```c
__int64 __fastcall DeleteFromTable(__int64 a1, int a2, int a3, _BYTE *a4, _QWORD *a5)
{
  _BYTE *v5; // rdi
  __int64 result; // rax
  __int64 v8; // rbp
  int v9; // r15d
  _QWORD *v10; // rbx
  __int64 v11; // rcx
  HANDLE ProcessHeap; // rax
  _BYTE v13[88]; // [rsp+30h] [rbp-58h] BYREF

  v5 = a4;
  memset(v13, 0, 32);
  if ( !a4 )
  {
    result = SearchInTable(a1, a2, a3, (unsigned int)v13, (__int64)a5);
    if ( (_DWORD)result )
      return result;
    v5 = v13;
  }
  v8 = *((_QWORD *)v5 + 1);
  v9 = 100;
  v10 = *(_QWORD **)v5;
  if ( v8 )
    v9 = *((_DWORD *)v5 + 4);
  if ( v10[2] && v10[4] )
  {
    SwapWithSuccessor(a1, v5);
    v10 = *(_QWORD **)v5;
    v8 = *((_QWORD *)v5 + 1);
    v9 = *((_DWORD *)v5 + 4);
  }
  AdjustPrefixes(a1, (_DWORD)v10, *v10, (_DWORD)v10, (__int64)v5);
  v11 = v10[2];
  if ( v11 || (v11 = v10[4]) != 0 )
    *(_QWORD *)(v11 + 8) = v10[1];
  if ( v8 )
  {
    *(_QWORD *)(v8 + 8LL * v9 + 24) = v11;
    BalanceAfterDelete(a1, v8, (unsigned int)v9);
  }
  else
  {
    *(_QWORD *)a1 = v11;
  }
  *a5 = v10[3];
  *(_QWORD *)v10[3] = 0;
  --*(_DWORD *)(a1 + 12);
  ProcessHeap = GetProcessHeap();
  HeapFree(ProcessHeap, 0, v10);
  return 0;
}

```

## disassembly

```asm
0x180001de0  mov     rax, rsp
0x180001de3  push    rbx
0x180001de4  push    rbp
0x180001de5  push    rsi
0x180001de6  push    rdi
0x180001de7  push    r12
0x180001de9  push    r14
0x180001deb  push    r15
0x180001ded  sub     rsp, 50h
0x180001df1  mov     r12, [rsp+88h+arg_20]
0x180001df9  xorps   xmm0, xmm0
0x180001dfc  mov     rdi, r9
0x180001dff  mov     rsi, rcx
0x180001e02  movups  xmmword ptr [rax-58h], xmm0
0x180001e06  movups  xmmword ptr [rax-48h], xmm0
0x180001e0a  test    r9, r9
0x180001e0d  jnz     short loc_180001E29
0x180001e0f  lea     r9, [rax-58h]
0x180001e13  mov     [rax-68h], r12
0x180001e17  call    SearchInTable
0x180001e1c  test    eax, eax
0x180001e1e  jnz     loc_180001EDF
0x180001e24  lea     rdi, [rsp+88h+var_58]
0x180001e29  mov     rbp, [rdi+8]
0x180001e2d  mov     r15d, 64h ; 'd'
0x180001e33  mov     rbx, [rdi]
0x180001e36  test    rbp, rbp
0x180001e39  jz      short loc_180001E3F
0x180001e3b  mov     r15d, [rdi+10h]
0x180001e3f  cmp     qword ptr [rbx+10h], 0
0x180001e44  jz      short loc_180001E63
0x180001e46  cmp     qword ptr [rbx+20h], 0
0x180001e4b  jz      short loc_180001E63
0x180001e4d  mov     rdx, rdi
0x180001e50  mov     rcx, rsi
0x180001e53  call    SwapWithSuccessor
0x180001e58  mov     rbx, [rdi]
0x180001e5b  mov     rbp, [rdi+8]
0x180001e5f  mov     r15d, [rdi+10h]
0x180001e63  mov     r8, [rbx]
0x180001e66  mov     r9, rbx
0x180001e69  mov     rdx, rbx
0x180001e6c  mov     [rsp+88h+var_68], rdi
0x180001e71  mov     rcx, rsi
0x180001e74  call    AdjustPrefixes
0x180001e79  mov     rcx, [rbx+10h]
0x180001e7d  test    rcx, rcx
0x180001e80  jnz     short loc_180001E8B
0x180001e82  mov     rcx, [rbx+20h]
0x180001e86  test    rcx, rcx
0x180001e89  jz      short loc_180001E93
0x180001e8b  mov     rax, [rbx+8]
0x180001e8f  mov     [rcx+8], rax
0x180001e93  test    rbp, rbp
0x180001e96  jz      short loc_180001EB0
0x180001e98  movsxd  rax, r15d
0x180001e9b  mov     r8d, r15d
0x180001e9e  mov     rdx, rbp
0x180001ea1  mov     [rbp+rax*8+18h], rcx
0x180001ea6  mov     rcx, rsi
0x180001ea9  call    BalanceAfterDelete
0x180001eae  jmp     short loc_180001EB3
0x180001eb0  mov     [rsi], rcx
0x180001eb3  mov     rax, [rbx+18h]
0x180001eb7  mov     [r12], rax
0x180001ebb  mov     rax, [rbx+18h]
0x180001ebf  mov     qword ptr [rax], 0
0x180001ec6  dec     dword ptr [rsi+0Ch]
0x180001ec9  call    cs:__imp_GetProcessHeap
0x180001ecf  mov     r8, rbx; lpMem
0x180001ed2  xor     edx, edx; dwFlags
0x180001ed4  mov     rcx, rax; hHeap
0x180001ed7  call    cs:__imp_HeapFree
0x180001edd  xor     eax, eax
0x180001edf  add     rsp, 50h
0x180001ee3  pop     r15
0x180001ee5  pop     r14
0x180001ee7  pop     r12
0x180001ee9  pop     rdi
0x180001eea  pop     rsi
0x180001eeb  pop     rbp
0x180001eec  pop     rbx
0x180001eed  retn
```
