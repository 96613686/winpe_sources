# SclpRegAddProcessItemToList

- ea: `0x18000d124`
- end: `0x18000d218`
- name: `SclpRegAddProcessItemToList`
- size: `244`
- prototype: `__int64 __fastcall(__int64, _QWORD *, _WORD *, unsigned int, int)`
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18000acec`
- `0x18000b21c`
- `0x18000b530`

## callees

- `0x18000a75c`
- `0x18000c68c`
- `0x18000d124`
- `0x180012434`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x18000d163`
- `ntdll!RtlAllocateHeap` at `0x18000d163`

## pseudocode

```c
__int64 __fastcall SclpRegAddProcessItemToList(__int64 a1, _QWORD *a2, _WORD *a3, unsigned int a4, int a5)
{
  __int64 v6; // rdi
  _QWORD *Heap; // rax
  _QWORD *v10; // rbx
  int v11; // edi
  __int64 v12; // rbp
  __int64 v13; // r9
  __int64 v15; // [rsp+48h] [rbp-50h] BYREF
  _QWORD v16[9]; // [rsp+50h] [rbp-48h] BYREF

  v6 = a4;
  v15 = 0;
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x20u);
  v10 = Heap;
  if ( Heap )
  {
    v12 = v6;
    v11 = SclCloneString(a3, v6, Heap + 2, 0);
    if ( v11 >= 0 )
    {
      v11 = SclCloneString(a3, v12, v10 + 3, &v15);
      if ( v11 >= 0 )
      {
        v13 = v10[3];
        v16[0] = v15;
        v11 = SclProcessStringAllocating(a1, v10 + 3, &v15, v13, v16);
        if ( v11 >= 0 )
        {
          *((_DWORD *)v10 + 2) = a5;
          *v10 = *a2;
          *a2 = v10;
          v10 = 0;
        }
      }
    }
  }
  else
  {
    v11 = -1073741801;
  }
  SclpFreeRenameItem(v10);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18000d124  push    rbx
0x18000d126  push    rbp
0x18000d127  push    rsi
0x18000d128  push    rdi
0x18000d129  push    r12
0x18000d12b  push    r14
0x18000d12d  push    r15
0x18000d12f  sub     rsp, 60h
0x18000d133  mov     r12, rcx
0x18000d136  mov     edi, r9d
0x18000d139  mov     rcx, gs:60h
0x18000d142  mov     rsi, rdx
0x18000d145  mov     edx, 8; Flags
0x18000d14a  mov     [rsp+98h+var_50], 0
0x18000d153  mov     r15, r8
0x18000d156  mov     [rsp+98h+var_58], 0
0x18000d15b  mov     rcx, [rcx+30h]; HeapHandle
0x18000d15f  lea     r8d, [rdx+18h]; Size
0x18000d163  call    cs:__imp_RtlAllocateHeap
0x18000d169  mov     rbx, rax
0x18000d16c  test    rax, rax
0x18000d16f  jnz     short loc_18000D17B
0x18000d171  mov     edi, 0C0000017h
0x18000d176  jmp     loc_18000D1FF
0x18000d17b  lea     r8, [rax+10h]
0x18000d17f  xor     r9d, r9d
0x18000d182  mov     rdx, rdi
0x18000d185  mov     rcx, r15
0x18000d188  mov     rbp, rdi
0x18000d18b  call    SclCloneString
0x18000d190  mov     edi, eax
0x18000d192  test    eax, eax
0x18000d194  js      short loc_18000D1FF
0x18000d196  lea     r14, [rbx+18h]
0x18000d19a  mov     rdx, rbp
0x18000d19d  mov     r8, r14
0x18000d1a0  lea     r9, [rsp+98h+var_50]
0x18000d1a5  mov     rcx, r15
0x18000d1a8  call    SclCloneString
0x18000d1ad  mov     edi, eax
0x18000d1af  test    eax, eax
0x18000d1b1  js      short loc_18000D1FF
0x18000d1b3  mov     rax, [rsp+98h+var_50]
0x18000d1b8  lea     r8, [rsp+98h+var_50]
0x18000d1bd  mov     r9, [r14]
0x18000d1c0  mov     rdx, r14
0x18000d1c3  mov     [rsp+98h+var_48], rax
0x18000d1c8  mov     rcx, r12
0x18000d1cb  lea     rax, [rsp+98h+var_58]
0x18000d1d0  mov     [rsp+98h+var_68], rax
0x18000d1d5  lea     rax, [rsp+98h+var_48]
0x18000d1da  mov     [rsp+98h+var_78], rax
0x18000d1df  call    SclProcessStringAllocating
0x18000d1e4  mov     edi, eax
0x18000d1e6  test    eax, eax
0x18000d1e8  js      short loc_18000D1FF
0x18000d1ea  mov     eax, [rsp+98h+arg_20]
0x18000d1f1  mov     [rbx+8], eax
0x18000d1f4  mov     rax, [rsi]
0x18000d1f7  mov     [rbx], rax
0x18000d1fa  mov     [rsi], rbx
0x18000d1fd  xor     ebx, ebx
0x18000d1ff  mov     rcx, rbx; P
0x18000d202  call    SclpFreeRenameItem
0x18000d207  mov     eax, edi
0x18000d209  add     rsp, 60h
0x18000d20d  pop     r15
0x18000d20f  pop     r14
0x18000d211  pop     r12
0x18000d213  pop     rdi
0x18000d214  pop     rsi
0x18000d215  pop     rbp
0x18000d216  pop     rbx
0x18000d217  retn
```
