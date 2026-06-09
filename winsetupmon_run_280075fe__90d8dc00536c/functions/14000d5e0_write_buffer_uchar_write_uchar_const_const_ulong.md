# write_buffer_uchar::write(uchar const * const,ulong)

- ea: `0x14000d5e0`
- end: `0x14000d72c`
- name: `?write@write_buffer_uchar@@IEAAJQEBEK@Z`
- size: `332`
- prototype: `int(write_buffer_uchar *__hidden this, const unsigned __int8 *const, unsigned int)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x140008c90`
- `0x140008d80`
- `0x140008e70`
- `0x14000d440`
- `0x14000d734`

## callees

- `0x140009368`
- `0x14000d5e0`
- `0x14000fa40`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000d6d9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d6d9`

## pseudocode

```c
write *__fastcall write_buffer_uchar::write(write *this, const unsigned __int8 *const a2, unsigned int a3)
{
  char *v3; // r14
  size_t v5; // rbp
  const void *v6; // r8
  char *v8; // r15
  unsigned __int64 v9; // rcx
  unsigned __int64 v10; // rax
  SIZE_T v11; // rbx
  unsigned __int64 v12; // rax
  char *v13; // rax
  char *v14; // r12
  size_t v15; // rdi
  void *v16; // rcx
  char v17; // al
  char *v19; // [rsp+70h] [rbp+8h]

  v3 = (char *)*((_QWORD *)this + 1);
  v5 = a3;
  v6 = *(const void **)this;
  v8 = &v3[-*(_QWORD *)this];
  v9 = (unsigned __int64)&v8[v5];
  if ( &v8[v5] > v8 )
  {
    v10 = *((_QWORD *)this + 2) - (_QWORD)v6;
    if ( v9 <= v10 )
    {
      memmove(v3, a2, v5);
      *((_QWORD *)this + 1) += v5;
    }
    else
    {
      v11 = (SIZE_T)&v8[v5];
      v12 = 7 * (v10 >> 2) + 8;
      if ( v12 >= v9 )
        v11 = v12;
      if ( v11 > 0x7FFFFFFFFFFFFFFFLL )
        v11 = 0x7FFFFFFFFFFFFFFFLL;
      if ( v11 < v9 )
        goto LABEL_18;
      v13 = (char *)operator new(v11, (const struct std::nothrow_t *)a2);
      v14 = v13;
      if ( (unsigned __int64)(v13 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
        goto LABEL_18;
      v19 = &v13[v11];
      v15 = (size_t)&v3[-*(_QWORD *)this];
      memmove(v13, *(const void **)this, v15);
      v3 = &v14[v15];
      memmove(&v14[v15], a2, v5);
      memmove(&v14[v15 + v5], (const void *)(v15 + *(_QWORD *)this), (size_t)&v8[-v15]);
      v16 = *(void **)this;
      if ( *(_QWORD *)this != -1 )
      {
        *((_QWORD *)this + 1) = v16;
        if ( v16 )
          ExFreePoolWithTag(v16, 0x6E6D7377u);
      }
      *((_QWORD *)this + 2) = v19;
      *(_QWORD *)this = v14;
      *((_QWORD *)this + 1) = &v14[v5 + (_QWORD)v8];
    }
  }
  else if ( (char *)v9 != v8 )
  {
    v3 = 0;
  }
  if ( v3 )
  {
    v17 = 0;
    return v17 != 0 ? (write *)0xC000009ALL : 0LL;
  }
LABEL_18:
  v17 = 1;
  return v17 != 0 ? (write *)0xC000009ALL : 0LL;
}

```

## disassembly

```asm
0x14000d5e0  push    rbx
0x14000d5e2  push    rbp
0x14000d5e3  push    rsi
0x14000d5e4  push    rdi
0x14000d5e5  push    r12
0x14000d5e7  push    r13
0x14000d5e9  push    r14
0x14000d5eb  push    r15
0x14000d5ed  sub     rsp, 28h
0x14000d5f1  mov     r14, [rcx+8]
0x14000d5f5  mov     rsi, rcx
0x14000d5f8  mov     ebp, r8d
0x14000d5fb  mov     r15, r14
0x14000d5fe  mov     r8, [rcx]
0x14000d601  mov     r13, rdx
0x14000d604  sub     r15, r8
0x14000d607  lea     rcx, [r15+rbp]
0x14000d60b  cmp     rcx, r15
0x14000d60e  ja      short loc_14000D61E
0x14000d610  xor     eax, eax
0x14000d612  cmp     rcx, r15
0x14000d615  cmovnz  r14, rax
0x14000d619  jmp     loc_14000D706
0x14000d61e  mov     rax, [rsi+10h]
0x14000d622  sub     rax, r8
0x14000d625  cmp     rcx, rax
0x14000d628  jbe     loc_14000D6F7
0x14000d62e  shr     rax, 2
0x14000d632  mov     rbx, rcx
0x14000d635  imul    rax, 7
0x14000d639  add     rax, 8
0x14000d63d  cmp     rax, rcx
0x14000d640  cmovnb  rbx, rax
0x14000d644  mov     rax, 7FFFFFFFFFFFFFFFh
0x14000d64e  cmp     rbx, rax
0x14000d651  cmova   rbx, rax
0x14000d655  cmp     rbx, rcx
0x14000d658  jb      loc_14000D70B
0x14000d65e  mov     rcx, rbx; NumberOfBytes
0x14000d661  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14000d666  mov     r12, rax
0x14000d669  lea     rcx, [rax-1]
0x14000d66d  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x14000d671  ja      loc_14000D70B
0x14000d677  mov     rdx, [rsi]; Src
0x14000d67a  add     rax, rbx
0x14000d67d  sub     r14, rdx
0x14000d680  mov     [rsp+68h+arg_0], rax
0x14000d685  mov     r8, r14; Size
0x14000d688  mov     rcx, r12; void *
0x14000d68b  mov     rdi, r14
0x14000d68e  call    memmove
0x14000d693  add     r14, r12
0x14000d696  mov     r8, rbp; Size
0x14000d699  mov     rcx, r14; void *
0x14000d69c  mov     rdx, r13; Src
0x14000d69f  call    memmove
0x14000d6a4  mov     rdx, [rsi]
0x14000d6a7  lea     rbx, [r14+rbp]
0x14000d6ab  mov     r8, r15
0x14000d6ae  add     rdx, rdi; Src
0x14000d6b1  sub     r8, rdi; Size
0x14000d6b4  mov     rcx, rbx; void *
0x14000d6b7  call    memmove
0x14000d6bc  mov     rcx, [rsi]; P
0x14000d6bf  sub     r15, rdi
0x14000d6c2  add     rbx, r15
0x14000d6c5  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x14000d6c9  jz      short loc_14000D6E5
0x14000d6cb  mov     [rsi+8], rcx
0x14000d6cf  test    rcx, rcx
0x14000d6d2  jz      short loc_14000D6E5
0x14000d6d4  mov     edx, 6E6D7377h; Tag
0x14000d6d9  call    cs:__imp_ExFreePoolWithTag
0x14000d6e0  nop     dword ptr [rax+rax+00h]
0x14000d6e5  mov     rax, [rsp+68h+arg_0]
0x14000d6ea  mov     [rsi+10h], rax
0x14000d6ee  mov     [rsi], r12
0x14000d6f1  mov     [rsi+8], rbx
0x14000d6f5  jmp     short loc_14000D706
0x14000d6f7  mov     r8, rbp; Size
0x14000d6fa  mov     rcx, r14; void *
0x14000d6fd  call    memmove
0x14000d702  add     [rsi+8], rbp
0x14000d706  test    r14, r14
0x14000d709  jnz     short loc_14000D70F
0x14000d70b  mov     al, 1
0x14000d70d  jmp     short loc_14000D711
0x14000d70f  xor     al, al
0x14000d711  neg     al
0x14000d713  sbb     eax, eax
0x14000d715  and     eax, 0C000009Ah
0x14000d71a  add     rsp, 28h
0x14000d71e  pop     r15
0x14000d720  pop     r14
0x14000d722  pop     r13
0x14000d724  pop     r12
0x14000d726  pop     rdi
0x14000d727  pop     rsi
0x14000d728  pop     rbp
0x14000d729  pop     rbx
0x14000d72a  retn
```
