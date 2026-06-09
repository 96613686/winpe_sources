# copy_and_add_argument_to_buffer_char_

- ea: `0x10041c804`
- end: `0x10041c988`
- name: `copy_and_add_argument_to_buffer_char_`
- size: `388`
- prototype: `__int64 __fastcall(char *Source, char *, rsize_t MaxCount)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x10041c5bc`
- `0x10041c990`

## callees

- `0x10041c06c`
- `0x10041c1d0`
- `0x10041c24c`
- `0x10041c804`
- `0x10041deac`
- `0x10041fda4`

## pseudocode

```c
__int64 __fastcall copy_and_add_argument_to_buffer_char_(char *Source, char *a2, rsize_t MaxCount, void **a4)
{
  __int64 v4; // rbp
  unsigned int v6; // edi
  rsize_t v10; // rbp
  size_t v12; // r15
  char *v13; // rax
  char *v14; // rbx
  char *v15; // r14
  char *v16; // rax
  unsigned __int64 v17; // r14
  char *v18; // rax

  v4 = -1;
  v6 = 0;
  do
    ++v4;
  while ( Source[v4] );
  v10 = v4 + 1;
  if ( v10 > ~MaxCount )
    return 12;
  v12 = v10 + MaxCount + 1;
  v13 = (char *)calloc_base(v12, 1u);
  v14 = v13;
  if ( MaxCount && strncpy_s(v13, v12, a2, MaxCount) || strncpy_s(&v14[MaxCount], v12 - MaxCount, Source, v10) )
    invoke_watson(0, 0, 0, 0, 0);
  v15 = (char *)a4[2];
  if ( a4[1] != v15 )
    goto LABEL_17;
  if ( *a4 )
  {
    v17 = (v15 - (_BYTE *)*a4) >> 3;
    if ( v17 <= 0x7FFFFFFFFFFFFFFFLL )
    {
      v18 = (char *)recalloc_base(*a4, 2 * v17, 8u);
      if ( v18 )
      {
        *a4 = v18;
        a4[1] = &v18[8 * v17];
        a4[2] = &v18[16 * v17];
        free_base(0);
        goto LABEL_17;
      }
      free_base(0);
    }
  }
  else
  {
    *a4 = calloc_base(4u, 8u);
    free_base(0);
    v16 = (char *)*a4;
    if ( *a4 )
    {
      a4[1] = v16;
      a4[2] = v16 + 32;
LABEL_17:
      *(_QWORD *)a4[1] = v14;
      a4[1] = (char *)a4[1] + 8;
      goto LABEL_18;
    }
  }
  v6 = 12;
  free_base(v14);
LABEL_18:
  free_base(0);
  return v6;
}

```

## disassembly

```asm
0x10041c804  mov     [rsp+arg_0], rbx
0x10041c809  mov     [rsp+arg_8], rbp
0x10041c80e  mov     [rsp+arg_10], rsi
0x10041c813  push    rdi
0x10041c814  push    r12
0x10041c816  push    r13
0x10041c818  push    r14
0x10041c81a  push    r15
0x10041c81c  sub     rsp, 30h
0x10041c820  or      rbp, 0FFFFFFFFFFFFFFFFh
0x10041c824  mov     rsi, r9
0x10041c827  xor     edi, edi
0x10041c829  mov     r14, r8
0x10041c82c  mov     r13, rdx
0x10041c82f  mov     r12, rcx
0x10041c832  inc     rbp
0x10041c835  cmp     [rcx+rbp], dil
0x10041c839  jnz     short loc_10041C832
0x10041c83b  mov     edx, 1; Size
0x10041c840  mov     rax, r14
0x10041c843  add     rbp, rdx
0x10041c846  not     rax
0x10041c849  cmp     rbp, rax
0x10041c84c  jbe     short loc_10041C86E
0x10041c84e  lea     eax, [rdx+0Bh]
0x10041c851  mov     rbx, [rsp+58h+arg_0]
0x10041c856  mov     rbp, [rsp+58h+arg_8]
0x10041c85b  mov     rsi, [rsp+58h+arg_10]
0x10041c860  add     rsp, 30h
0x10041c864  pop     r15
0x10041c866  pop     r14
0x10041c868  pop     r13
0x10041c86a  pop     r12
0x10041c86c  pop     rdi
0x10041c86d  retn
0x10041c86e  lea     r15, [r8+1]
0x10041c872  add     r15, rbp
0x10041c875  mov     rcx, r15; Count
0x10041c878  call    _calloc_base
0x10041c87d  mov     rbx, rax
0x10041c880  test    r14, r14
0x10041c883  jz      short loc_10041C89E
0x10041c885  mov     r9, r14; MaxCount
0x10041c888  mov     r8, r13; Source
0x10041c88b  mov     rdx, r15; SizeInBytes
0x10041c88e  mov     rcx, rax; Destination
0x10041c891  call    strncpy_s
0x10041c896  test    eax, eax
0x10041c898  jnz     loc_10041C973
0x10041c89e  sub     r15, r14
0x10041c8a1  lea     rcx, [rbx+r14]; Destination
0x10041c8a5  mov     rdx, r15; SizeInBytes
0x10041c8a8  mov     r9, rbp; MaxCount
0x10041c8ab  mov     r8, r12; Source
0x10041c8ae  call    strncpy_s
0x10041c8b3  test    eax, eax
0x10041c8b5  jnz     loc_10041C973
0x10041c8bb  mov     r14, [rsi+10h]
0x10041c8bf  lea     r15d, [rax+8]
0x10041c8c3  cmp     [rsi+8], r14
0x10041c8c7  jnz     loc_10041C95A
0x10041c8cd  cmp     [rsi], rdi
0x10041c8d0  jnz     short loc_10041C8FD
0x10041c8d2  mov     edx, r15d; Size
0x10041c8d5  lea     ecx, [rax+4]; Count
0x10041c8d8  call    _calloc_base
0x10041c8dd  xor     ecx, ecx; Block
0x10041c8df  mov     [rsi], rax
0x10041c8e2  call    _free_base
0x10041c8e7  mov     rax, [rsi]
0x10041c8ea  test    rax, rax
0x10041c8ed  jz      short loc_10041C931
0x10041c8ef  mov     [rsi+8], rax
0x10041c8f3  add     rax, 20h ; ' '
0x10041c8f7  mov     [rsi+10h], rax
0x10041c8fb  jmp     short loc_10041C95A
0x10041c8fd  sub     r14, [rsi]
0x10041c900  mov     rax, 7FFFFFFFFFFFFFFFh
0x10041c90a  sar     r14, 3
0x10041c90e  cmp     r14, rax
0x10041c911  ja      short loc_10041C931
0x10041c913  mov     rcx, [rsi]; Block
0x10041c916  lea     rbp, [r14+r14]
0x10041c91a  mov     rdx, rbp; Count
0x10041c91d  mov     r8, r15; Size
0x10041c920  call    _recalloc_base
0x10041c925  test    rax, rax
0x10041c928  jnz     short loc_10041C940
0x10041c92a  xor     ecx, ecx; Block
0x10041c92c  call    _free_base
0x10041c931  mov     rcx, rbx; Block
0x10041c934  mov     edi, 0Ch
0x10041c939  call    _free_base
0x10041c93e  jmp     short loc_10041C965
0x10041c940  lea     rcx, [rax+r14*8]
0x10041c944  mov     [rsi], rax
0x10041c947  mov     [rsi+8], rcx
0x10041c94b  lea     rcx, [rax+rbp*8]
0x10041c94f  mov     [rsi+10h], rcx
0x10041c953  xor     ecx, ecx; Block
0x10041c955  call    _free_base
0x10041c95a  mov     rcx, [rsi+8]
0x10041c95e  mov     [rcx], rbx
0x10041c961  add     [rsi+8], r15
0x10041c965  xor     ecx, ecx; Block
0x10041c967  call    _free_base
0x10041c96c  mov     eax, edi
0x10041c96e  jmp     loc_10041C851
0x10041c973  xor     r9d, r9d; LineNo
0x10041c976  mov     [rsp+58h+Reserved], rdi; Reserved
0x10041c97b  xor     r8d, r8d; FileName
0x10041c97e  xor     edx, edx; FunctionName
0x10041c980  xor     ecx, ecx; Expression
0x10041c982  call    _invoke_watson
```
