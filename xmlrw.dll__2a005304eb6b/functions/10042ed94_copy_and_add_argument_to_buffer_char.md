# copy_and_add_argument_to_buffer_char_

- ea: `0x10042ed94`
- end: `0x10042ef18`
- name: `copy_and_add_argument_to_buffer_char_`
- size: `388`
- prototype: `__int64 __fastcall(char *Source, char *, rsize_t MaxCount)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x10042eb4c`
- `0x10042ef20`

## callees

- `0x10042e5fc`
- `0x10042e760`
- `0x10042e7dc`
- `0x10042ed94`
- `0x10043043c`
- `0x100433354`

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
0x10042ed94  mov     [rsp+arg_0], rbx
0x10042ed99  mov     [rsp+arg_8], rbp
0x10042ed9e  mov     [rsp+arg_10], rsi
0x10042eda3  push    rdi
0x10042eda4  push    r12
0x10042eda6  push    r13
0x10042eda8  push    r14
0x10042edaa  push    r15
0x10042edac  sub     rsp, 30h
0x10042edb0  or      rbp, 0FFFFFFFFFFFFFFFFh
0x10042edb4  mov     rsi, r9
0x10042edb7  xor     edi, edi
0x10042edb9  mov     r14, r8
0x10042edbc  mov     r13, rdx
0x10042edbf  mov     r12, rcx
0x10042edc2  inc     rbp
0x10042edc5  cmp     [rcx+rbp], dil
0x10042edc9  jnz     short loc_10042EDC2
0x10042edcb  mov     edx, 1; Size
0x10042edd0  mov     rax, r14
0x10042edd3  add     rbp, rdx
0x10042edd6  not     rax
0x10042edd9  cmp     rbp, rax
0x10042eddc  jbe     short loc_10042EDFE
0x10042edde  lea     eax, [rdx+0Bh]
0x10042ede1  mov     rbx, [rsp+58h+arg_0]
0x10042ede6  mov     rbp, [rsp+58h+arg_8]
0x10042edeb  mov     rsi, [rsp+58h+arg_10]
0x10042edf0  add     rsp, 30h
0x10042edf4  pop     r15
0x10042edf6  pop     r14
0x10042edf8  pop     r13
0x10042edfa  pop     r12
0x10042edfc  pop     rdi
0x10042edfd  retn
0x10042edfe  lea     r15, [r8+1]
0x10042ee02  add     r15, rbp
0x10042ee05  mov     rcx, r15; Count
0x10042ee08  call    _calloc_base
0x10042ee0d  mov     rbx, rax
0x10042ee10  test    r14, r14
0x10042ee13  jz      short loc_10042EE2E
0x10042ee15  mov     r9, r14; MaxCount
0x10042ee18  mov     r8, r13; Source
0x10042ee1b  mov     rdx, r15; SizeInBytes
0x10042ee1e  mov     rcx, rax; Destination
0x10042ee21  call    strncpy_s
0x10042ee26  test    eax, eax
0x10042ee28  jnz     loc_10042EF03
0x10042ee2e  sub     r15, r14
0x10042ee31  lea     rcx, [rbx+r14]; Destination
0x10042ee35  mov     rdx, r15; SizeInBytes
0x10042ee38  mov     r9, rbp; MaxCount
0x10042ee3b  mov     r8, r12; Source
0x10042ee3e  call    strncpy_s
0x10042ee43  test    eax, eax
0x10042ee45  jnz     loc_10042EF03
0x10042ee4b  mov     r14, [rsi+10h]
0x10042ee4f  lea     r15d, [rax+8]
0x10042ee53  cmp     [rsi+8], r14
0x10042ee57  jnz     loc_10042EEEA
0x10042ee5d  cmp     [rsi], rdi
0x10042ee60  jnz     short loc_10042EE8D
0x10042ee62  mov     edx, r15d; Size
0x10042ee65  lea     ecx, [rax+4]; Count
0x10042ee68  call    _calloc_base
0x10042ee6d  xor     ecx, ecx; Block
0x10042ee6f  mov     [rsi], rax
0x10042ee72  call    _free_base
0x10042ee77  mov     rax, [rsi]
0x10042ee7a  test    rax, rax
0x10042ee7d  jz      short loc_10042EEC1
0x10042ee7f  mov     [rsi+8], rax
0x10042ee83  add     rax, 20h ; ' '
0x10042ee87  mov     [rsi+10h], rax
0x10042ee8b  jmp     short loc_10042EEEA
0x10042ee8d  sub     r14, [rsi]
0x10042ee90  mov     rax, 7FFFFFFFFFFFFFFFh
0x10042ee9a  sar     r14, 3
0x10042ee9e  cmp     r14, rax
0x10042eea1  ja      short loc_10042EEC1
0x10042eea3  mov     rcx, [rsi]; Block
0x10042eea6  lea     rbp, [r14+r14]
0x10042eeaa  mov     rdx, rbp; Count
0x10042eead  mov     r8, r15; Size
0x10042eeb0  call    _recalloc_base
0x10042eeb5  test    rax, rax
0x10042eeb8  jnz     short loc_10042EED0
0x10042eeba  xor     ecx, ecx; Block
0x10042eebc  call    _free_base
0x10042eec1  mov     rcx, rbx; Block
0x10042eec4  mov     edi, 0Ch
0x10042eec9  call    _free_base
0x10042eece  jmp     short loc_10042EEF5
0x10042eed0  lea     rcx, [rax+r14*8]
0x10042eed4  mov     [rsi], rax
0x10042eed7  mov     [rsi+8], rcx
0x10042eedb  lea     rcx, [rax+rbp*8]
0x10042eedf  mov     [rsi+10h], rcx
0x10042eee3  xor     ecx, ecx; Block
0x10042eee5  call    _free_base
0x10042eeea  mov     rcx, [rsi+8]
0x10042eeee  mov     [rcx], rbx
0x10042eef1  add     [rsi+8], r15
0x10042eef5  xor     ecx, ecx; Block
0x10042eef7  call    _free_base
0x10042eefc  mov     eax, edi
0x10042eefe  jmp     loc_10042EDE1
0x10042ef03  xor     r9d, r9d; LineNo
0x10042ef06  mov     [rsp+58h+Reserved], rdi; Reserved
0x10042ef0b  xor     r8d, r8d; FileName
0x10042ef0e  xor     edx, edx; FunctionName
0x10042ef10  xor     ecx, ecx; Expression
0x10042ef12  call    _invoke_watson
```
