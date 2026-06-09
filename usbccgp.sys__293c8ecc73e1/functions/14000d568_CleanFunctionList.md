# CleanFunctionList

- ea: `0x14000d568`
- end: `0x14000d61c`
- name: `CleanFunctionList`
- size: `180`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x14000fb68`
- `0x140026970`
- `0x140028d78`
- `0x14002b3bc`

## callees

- `0x14000d568`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000d598`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d5d4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d5ee`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d5fe`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d60e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d598`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d5d4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d5ee`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d5fe`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d60e`

## pseudocode

```c
void __fastcall CleanFunctionList(_QWORD *P, unsigned int a2)
{
  unsigned int v2; // esi
  __int64 v5; // rbp
  __int64 v6; // rdi
  void *v7; // rcx
  void *v8; // rcx
  void *v9; // rcx
  void *v10; // rcx

  if ( P )
  {
    v2 = 0;
    if ( a2 )
    {
      v5 = 0;
      do
      {
        v6 = 11 * v5;
        v7 = (void *)P[11 * v5 + 1];
        if ( v7 )
          ExFreePoolWithTag(v7, 0x43627355u);
        v8 = (void *)P[v6 + 6];
        if ( v8 )
          ExFreePoolWithTag(v8, 0);
        v9 = (void *)P[v6 + 4];
        if ( v9 )
          ExFreePoolWithTag(v9, 0);
        v10 = (void *)P[v6 + 8];
        if ( v10 )
          ExFreePoolWithTag(v10, 0);
        ++v2;
        ++v5;
      }
      while ( v2 < a2 );
    }
    ExFreePoolWithTag(P, 0x43627355u);
  }
}

```

## disassembly

```asm
0x14000d568  test    rcx, rcx
0x14000d56b  jz      short locret_14000D5EA
0x14000d56d  push    rbx
0x14000d56e  push    rbp
0x14000d56f  push    rsi
0x14000d570  push    rdi
0x14000d571  push    r14
0x14000d573  sub     rsp, 20h
0x14000d577  xor     esi, esi
0x14000d579  mov     r14d, edx
0x14000d57c  mov     rbx, rcx
0x14000d57f  test    edx, edx
0x14000d581  jz      short loc_14000D5CC
0x14000d583  xor     ebp, ebp
0x14000d585  imul    rdi, rbp, 58h ; 'X'
0x14000d589  mov     rcx, [rdi+rbx+8]; P
0x14000d58e  test    rcx, rcx
0x14000d591  jz      short loc_14000D5A4
0x14000d593  mov     edx, 43627355h; Tag
0x14000d598  call    cs:__imp_ExFreePoolWithTag
0x14000d59f  nop     dword ptr [rax+rax+00h]
0x14000d5a4  mov     rcx, [rdi+rbx+30h]; P
0x14000d5a9  test    rcx, rcx
0x14000d5ac  jnz     short loc_14000D5EC
0x14000d5ae  mov     rcx, [rdi+rbx+20h]; P
0x14000d5b3  test    rcx, rcx
0x14000d5b6  jnz     short loc_14000D5FC
0x14000d5b8  mov     rcx, [rdi+rbx+40h]; P
0x14000d5bd  test    rcx, rcx
0x14000d5c0  jnz     short loc_14000D60C
0x14000d5c2  inc     esi
0x14000d5c4  inc     rbp
0x14000d5c7  cmp     esi, r14d
0x14000d5ca  jb      short loc_14000D585
0x14000d5cc  mov     edx, 43627355h; Tag
0x14000d5d1  mov     rcx, rbx; P
0x14000d5d4  call    cs:__imp_ExFreePoolWithTag
0x14000d5db  nop     dword ptr [rax+rax+00h]
0x14000d5e0  add     rsp, 20h
0x14000d5e4  pop     r14
0x14000d5e6  pop     rdi
0x14000d5e7  pop     rsi
0x14000d5e8  pop     rbp
0x14000d5e9  pop     rbx
0x14000d5ea  retn
0x14000d5ec  xor     edx, edx; Tag
0x14000d5ee  call    cs:__imp_ExFreePoolWithTag
0x14000d5f5  nop     dword ptr [rax+rax+00h]
0x14000d5fa  jmp     short loc_14000D5AE
0x14000d5fc  xor     edx, edx; Tag
0x14000d5fe  call    cs:__imp_ExFreePoolWithTag
0x14000d605  nop     dword ptr [rax+rax+00h]
0x14000d60a  jmp     short loc_14000D5B8
0x14000d60c  xor     edx, edx; Tag
0x14000d60e  call    cs:__imp_ExFreePoolWithTag
0x14000d615  nop     dword ptr [rax+rax+00h]
0x14000d61a  jmp     short loc_14000D5C2
```
