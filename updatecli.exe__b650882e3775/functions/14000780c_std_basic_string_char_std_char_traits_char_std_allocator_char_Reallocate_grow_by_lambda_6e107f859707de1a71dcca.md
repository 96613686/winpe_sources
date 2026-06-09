# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Reallocate_grow_by<_lambda_6e107f859707de1a71dcca60860853b1_,char const *,unsigned __int64>(unsigned __int64,_lambda_6e107f859707de1a71dcca60860853b1_,char const *,unsigned __int64)

- ea: `0x14000780c`
- end: `0x14000797a`
- name: `??$_Reallocate_grow_by@V_lambda_6e107f859707de1a71dcca60860853b1_@@PEBD_K@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_6e107f859707de1a71dcca60860853b1_@@PEBD_K@Z`
- size: `366`
- prototype: `void **__fastcall(void **Src, unsigned __int64, __int64, const void *, size_t Size)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x140008038`
- `0x140009dcc`

## callees

- `0x1400023c4`
- `0x1400023fc`
- `0x14000780c`
- `0x14000a1d8`
- `0x14000a2dc`
- `0x14000ac74`

## pseudocode

```c
void **__fastcall std::string::_Reallocate_grow_by<_lambda_6e107f859707de1a71dcca60860853b1_,char const *,unsigned __int64>(
        void **Src,
        unsigned __int64 a2,
        __int64 a3,
        const void *a4,
        size_t Size)
{
  size_t v5; // r14
  __int64 v6; // rbx
  unsigned __int64 v9; // r12
  size_t v10; // rbp
  unsigned __int64 v11; // rcx
  size_t v12; // rcx
  void *v13; // rax
  _QWORD *v14; // rdi
  unsigned __int64 v15; // rdx
  char *v16; // r15
  _BYTE *v17; // rbx
  unsigned __int64 v18; // rdx
  _BYTE *v19; // rcx
  void **result; // rax

  v5 = (size_t)Src[2];
  v6 = 0x7FFFFFFFFFFFFFFFLL;
  if ( 0x7FFFFFFFFFFFFFFFLL - v5 < a2 )
    std::_Xlen_string();
  v9 = (unsigned __int64)Src[3];
  v10 = v5 + a2;
  v11 = (v5 + a2) | 0xF;
  if ( v11 > 0x7FFFFFFFFFFFFFFFLL || (v15 = v9 >> 1, v9 > 0x7FFFFFFFFFFFFFFFLL - (v9 >> 1)) )
  {
    v12 = 0x8000000000000027uLL;
  }
  else
  {
    v6 = v11;
    if ( v11 < v9 + v15 )
      v6 = v9 + v15;
    if ( v6 == -1 )
    {
      v14 = 0;
      goto LABEL_15;
    }
    if ( (unsigned __int64)(v6 + 1) < 0x1000 )
    {
      v14 = operator new(v6 + 1);
      goto LABEL_15;
    }
    v12 = v6 + 40;
    if ( v6 + 40 < (unsigned __int64)(v6 + 1) )
      __scrt_throw_std_bad_array_new_length();
  }
  v13 = operator new(v12);
  if ( !v13 )
    goto LABEL_19;
  v14 = (_QWORD *)(((unsigned __int64)v13 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
  *(v14 - 1) = v13;
LABEL_15:
  Src[2] = (void *)v10;
  v16 = (char *)v14 + v5;
  Src[3] = (void *)v6;
  if ( v9 <= 0xF )
  {
    memcpy_0(v14, Src, v5);
    memcpy_0((char *)v14 + v5, a4, Size);
    v16[Size] = 0;
    goto LABEL_23;
  }
  v17 = *Src;
  memcpy_0(v14, *Src, v5);
  memcpy_0((char *)v14 + v5, a4, Size);
  v18 = v9 + 1;
  v16[Size] = 0;
  if ( v9 + 1 < 0x1000 )
  {
    v19 = v17;
    goto LABEL_21;
  }
  v19 = (_BYTE *)*((_QWORD *)v17 - 1);
  if ( (unsigned __int64)(v17 - v19 - 8) > 0x1F )
LABEL_19:
    __fastfail(5u);
  v18 = v9 + 40;
LABEL_21:
  operator delete(v19, v18);
LABEL_23:
  result = Src;
  *Src = v14;
  return result;
}

```

## disassembly

```asm
0x14000780c  push    rbx
0x14000780e  push    rbp
0x14000780f  push    rsi
0x140007810  push    rdi
0x140007811  push    r12
0x140007813  push    r13
0x140007815  push    r14
0x140007817  push    r15
0x140007819  sub     rsp, 28h
0x14000781d  mov     r14, [rcx+10h]
0x140007821  mov     rbx, 7FFFFFFFFFFFFFFFh
0x14000782b  mov     rax, rbx
0x14000782e  mov     r13, r9
0x140007831  sub     rax, r14
0x140007834  mov     rsi, rcx
0x140007837  cmp     rax, rdx
0x14000783a  jb      loc_14000796E
0x140007840  mov     r12, [rcx+18h]
0x140007844  lea     rbp, [r14+rdx]
0x140007848  mov     rcx, rbp
0x14000784b  or      rcx, 0Fh
0x14000784f  cmp     rcx, rbx
0x140007852  jbe     short loc_14000787A
0x140007854  mov     rcx, 8000000000000027h; Size
0x14000785e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140007863  test    rax, rax
0x140007866  jz      loc_14000792B
0x14000786c  lea     rdi, [rax+27h]
0x140007870  and     rdi, 0FFFFFFFFFFFFFFE0h
0x140007874  mov     [rdi-8], rax
0x140007878  jmp     short loc_1400078C8
0x14000787a  mov     rdx, r12
0x14000787d  mov     rax, rbx
0x140007880  shr     rdx, 1
0x140007883  sub     rax, rdx
0x140007886  cmp     r12, rax
0x140007889  ja      short loc_140007854
0x14000788b  lea     rax, [r12+rdx]
0x14000788f  mov     rbx, rcx
0x140007892  cmp     rcx, rax
0x140007895  cmovb   rbx, rax
0x140007899  lea     rax, [rbx+1]
0x14000789d  test    rax, rax
0x1400078a0  jnz     short loc_1400078A6
0x1400078a2  xor     edi, edi
0x1400078a4  jmp     short loc_1400078C8
0x1400078a6  cmp     rax, 1000h
0x1400078ac  jb      short loc_1400078BD
0x1400078ae  lea     rcx, [rax+27h]
0x1400078b2  cmp     rcx, rax
0x1400078b5  jbe     loc_140007974
0x1400078bb  jmp     short loc_14000785E
0x1400078bd  mov     rcx, rax; Size
0x1400078c0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400078c5  mov     rdi, rax
0x1400078c8  mov     [rsi+10h], rbp
0x1400078cc  lea     r15, [r14+rdi]
0x1400078d0  mov     rbp, [rsp+68h+Size]
0x1400078d8  mov     r8, r14; Size
0x1400078db  mov     [rsi+18h], rbx
0x1400078df  mov     rcx, rdi; void *
0x1400078e2  cmp     r12, 0Fh
0x1400078e6  jbe     short loc_14000793C
0x1400078e8  mov     rbx, [rsi]
0x1400078eb  mov     rdx, rbx; Src
0x1400078ee  call    memcpy_0
0x1400078f3  mov     r8, rbp; Size
0x1400078f6  mov     rdx, r13; Src
0x1400078f9  mov     rcx, r15; void *
0x1400078fc  call    memcpy_0
0x140007901  lea     rdx, [r12+1]; unsigned __int64
0x140007906  mov     byte ptr [r15+rbp], 0
0x14000790b  cmp     rdx, 1000h
0x140007912  jb      short loc_140007932
0x140007914  mov     rcx, [rbx-8]
0x140007918  sub     rbx, rcx
0x14000791b  sub     rbx, 8
0x14000791f  cmp     rbx, 1Fh
0x140007923  ja      short loc_14000792B
0x140007925  add     rdx, 27h ; '''
0x140007929  jmp     short loc_140007935
0x14000792b  mov     ecx, 5
0x140007930  int     29h; Win8: RtlFailFast(ecx)
0x140007932  mov     rcx, rbx; void *
0x140007935  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000793a  jmp     short loc_140007957
0x14000793c  mov     rdx, rsi; Src
0x14000793f  call    memcpy_0
0x140007944  mov     r8, rbp; Size
0x140007947  mov     rdx, r13; Src
0x14000794a  mov     rcx, r15; void *
0x14000794d  call    memcpy_0
0x140007952  mov     byte ptr [r15+rbp], 0
0x140007957  mov     rax, rsi
0x14000795a  mov     [rax], rdi
0x14000795d  add     rsp, 28h
0x140007961  pop     r15
0x140007963  pop     r14
0x140007965  pop     r13
0x140007967  pop     r12
0x140007969  pop     rdi
0x14000796a  pop     rsi
0x14000796b  pop     rbp
0x14000796c  pop     rbx
0x14000796d  retn
0x14000796e  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
0x140007974  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
