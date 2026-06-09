# utl::vector<uchar,utl::allocator<uchar>>::resize(unsigned __int64)

- ea: `0x14000cfa0`
- end: `0x14000d0a2`
- name: `?resize@?$vector@EV?$allocator@E@utl@@@utl@@QEAA_N_K@Z`
- size: `258`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x140008c90`
- `0x140008d80`
- `0x140008e70`
- `0x14000d734`

## callees

- `0x140009368`
- `0x14000cfa0`
- `0x14000fa40`
- `0x14000fd40`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000d05a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d05a`

## pseudocode

```c
char __fastcall utl::vector<unsigned char,utl::allocator<unsigned char>>::resize(
        __int64 a1,
        const struct std::nothrow_t *a2)
{
  _BYTE *v4; // rcx
  char *v5; // r9
  signed __int64 v6; // rbp
  unsigned __int64 v7; // rax
  SIZE_T v8; // rsi
  char *v9; // rax
  char *v10; // r14
  char *v11; // rsi
  void *v12; // rcx
  char *v13; // r15

  v4 = *(_BYTE **)a1;
  v5 = *(char **)(a1 + 8);
  v6 = v5 - v4;
  if ( (unsigned __int64)a2 <= v5 - v4 )
  {
    *(_QWORD *)(a1 + 8) = (char *)a2 + (_QWORD)v4;
    return 1;
  }
  v7 = *(_QWORD *)(a1 + 16) - (_QWORD)v4;
  if ( (unsigned __int64)a2 <= v7 )
  {
LABEL_14:
    memset(v5, 0, (size_t)a2 - v6);
    *(_QWORD *)(a1 + 8) = (char *)a2 + *(_QWORD *)a1;
    return 1;
  }
  v8 = 7 * (v7 >> 2) + 8;
  if ( v8 < (unsigned __int64)a2 )
    v8 = (SIZE_T)a2;
  if ( v8 > 0x7FFFFFFFFFFFFFFFLL )
    v8 = 0x7FFFFFFFFFFFFFFFLL;
  if ( (unsigned __int64)a2 <= v8 )
  {
    v9 = (char *)operator new(v8, a2);
    v10 = v9;
    if ( (unsigned __int64)(v9 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      v11 = &v9[v8];
      memmove(v9, *(const void **)a1, *(_QWORD *)(a1 + 8) - *(_QWORD *)a1);
      v12 = *(void **)a1;
      v13 = &v10[*(_QWORD *)(a1 + 8) - *(_QWORD *)a1];
      if ( *(_QWORD *)a1 != -1 )
      {
        *(_QWORD *)(a1 + 8) = v12;
        if ( v12 )
          ExFreePoolWithTag(v12, 0x6E6D7377u);
      }
      *(_QWORD *)a1 = v10;
      v5 = v13;
      *(_QWORD *)(a1 + 8) = v13;
      *(_QWORD *)(a1 + 16) = v11;
      goto LABEL_14;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x14000cfa0  push    rbx
0x14000cfa2  push    rbp
0x14000cfa3  push    rsi
0x14000cfa4  push    rdi
0x14000cfa5  push    r14
0x14000cfa7  push    r15
0x14000cfa9  sub     rsp, 28h
0x14000cfad  mov     rbx, rcx
0x14000cfb0  mov     rdi, rdx
0x14000cfb3  mov     rcx, [rcx]
0x14000cfb6  mov     r9, [rbx+8]
0x14000cfba  mov     rbp, r9
0x14000cfbd  sub     rbp, rcx
0x14000cfc0  cmp     rdx, rbp
0x14000cfc3  ja      short loc_14000CFD2
0x14000cfc5  lea     rax, [rcx+rdx]
0x14000cfc9  mov     [rbx+8], rax
0x14000cfcd  jmp     loc_14000D08E
0x14000cfd2  mov     rax, [rbx+10h]
0x14000cfd6  sub     rax, rcx
0x14000cfd9  cmp     rdi, rax
0x14000cfdc  jbe     loc_14000D074
0x14000cfe2  shr     rax, 2
0x14000cfe6  imul    rsi, rax, 7
0x14000cfea  mov     rax, 7FFFFFFFFFFFFFFFh
0x14000cff4  add     rsi, 8
0x14000cff8  cmp     rsi, rdi
0x14000cffb  cmovb   rsi, rdi
0x14000cfff  cmp     rsi, rax
0x14000d002  cmova   rsi, rax
0x14000d006  cmp     rdi, rsi
0x14000d009  ja      loc_14000D09E
0x14000d00f  mov     rcx, rsi; NumberOfBytes
0x14000d012  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14000d017  mov     r14, rax
0x14000d01a  lea     rcx, [rax-1]
0x14000d01e  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x14000d022  ja      short loc_14000D09E
0x14000d024  mov     rdx, [rbx]; Src
0x14000d027  mov     rcx, rax; void *
0x14000d02a  mov     r8, [rbx+8]
0x14000d02e  add     rsi, rax
0x14000d031  sub     r8, rdx; Size
0x14000d034  call    memmove
0x14000d039  mov     rcx, [rbx]; P
0x14000d03c  mov     r15, [rbx+8]
0x14000d040  sub     r15, rcx
0x14000d043  add     r15, r14
0x14000d046  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x14000d04a  jz      short loc_14000D066
0x14000d04c  mov     [rbx+8], rcx
0x14000d050  test    rcx, rcx
0x14000d053  jz      short loc_14000D066
0x14000d055  mov     edx, 6E6D7377h; Tag
0x14000d05a  call    cs:__imp_ExFreePoolWithTag
0x14000d061  nop     dword ptr [rax+rax+00h]
0x14000d066  mov     [rbx], r14
0x14000d069  mov     r9, r15
0x14000d06c  mov     [rbx+8], r15
0x14000d070  mov     [rbx+10h], rsi
0x14000d074  mov     r8, rdi
0x14000d077  xor     edx, edx; Val
0x14000d079  sub     r8, rbp; Size
0x14000d07c  mov     rcx, r9; void *
0x14000d07f  call    memset
0x14000d084  mov     rcx, [rbx]
0x14000d087  add     rcx, rdi
0x14000d08a  mov     [rbx+8], rcx
0x14000d08e  mov     al, 1
0x14000d090  add     rsp, 28h
0x14000d094  pop     r15
0x14000d096  pop     r14
0x14000d098  pop     rdi
0x14000d099  pop     rsi
0x14000d09a  pop     rbp
0x14000d09b  pop     rbx
0x14000d09c  retn
0x14000d09e  xor     eax, eax
0x14000d0a0  jmp     short loc_14000D090
```
