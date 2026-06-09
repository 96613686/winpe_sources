# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Reallocate_grow_by<_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,ushort const *,unsigned __int64>(unsigned __int64,_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,ushort const *,unsigned __int64)

- ea: `0x140007ab8`
- end: `0x140007bef`
- name: `??$_Reallocate_grow_by@V_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_@@PEBG_K@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_@@PEBG_K@Z`
- size: `311`
- prototype: `void **__fastcall(void **Src, unsigned __int64, __int64, const void *, __int64)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x140008c78`
- `0x14000a6a8`

## callees

- `0x1400023c4`
- `0x140007000`
- `0x140007ab8`
- `0x14000a2dc`
- `0x14000ac74`

## pseudocode

```c
void **__fastcall std::wstring::_Reallocate_grow_by<_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,unsigned short const *,unsigned __int64>(
        void **Src,
        unsigned __int64 a2,
        __int64 a3,
        const void *a4,
        __int64 a5)
{
  void *v5; // rbx
  __int64 v6; // r8
  unsigned __int64 v9; // r14
  char *v10; // rbp
  unsigned __int64 v11; // rcx
  unsigned __int64 v12; // rdx
  _QWORD *v13; // rax
  __int64 v14; // rdx
  size_t v15; // r8
  void *v16; // rcx
  _QWORD *v17; // rsi
  char *v18; // r15
  size_t v19; // rbp
  __int64 v20; // r12
  _BYTE *v21; // rbx
  unsigned __int64 v22; // rdx
  _BYTE *v23; // rcx
  void **result; // rax
  __int64 v25; // [rsp+70h] [rbp+8h] BYREF

  v5 = Src[2];
  v6 = 0x7FFFFFFFFFFFFFFELL;
  if ( 0x7FFFFFFFFFFFFFFELL - (__int64)v5 < a2 )
    std::_Xlen_string();
  v9 = (unsigned __int64)Src[3];
  v10 = (char *)v5 + a2;
  v11 = ((unsigned __int64)v5 + a2) | 7;
  if ( v11 <= 0x7FFFFFFFFFFFFFFELL )
  {
    v12 = v9 >> 1;
    if ( v9 <= 0x7FFFFFFFFFFFFFFELL - (v9 >> 1) )
    {
      v6 = v9 + v12;
      if ( v11 >= v9 + v12 )
        v6 = v11;
    }
  }
  v25 = v6;
  v13 = std::wstring::_Allocate_for_capacity<0>(v11, &v25);
  v14 = a5;
  v15 = 2LL * (_QWORD)v5;
  v16 = (void *)v25;
  v17 = v13;
  Src[2] = v10;
  Src[3] = v16;
  v18 = (char *)v13 + 2 * (_QWORD)v5;
  v19 = 2 * v14;
  v20 = (__int64)v5 + v14;
  if ( v9 <= 7 )
  {
    memcpy_0(v13, Src, v15);
    memcpy_0(v18, a4, v19);
    *((_WORD *)v17 + v20) = 0;
  }
  else
  {
    v21 = *Src;
    memcpy_0(v13, *Src, v15);
    memcpy_0(v18, a4, v19);
    v22 = 2 * v9 + 2;
    *((_WORD *)v17 + v20) = 0;
    if ( v22 < 0x1000 )
    {
      v23 = v21;
    }
    else
    {
      v23 = (_BYTE *)*((_QWORD *)v21 - 1);
      if ( (unsigned __int64)(v21 - v23 - 8) > 0x1F )
        __fastfail(5u);
      v22 = 2 * v9 + 41;
    }
    operator delete(v23, v22);
  }
  result = Src;
  *Src = v17;
  return result;
}

```

## disassembly

```asm
0x140007ab8  push    rbx
0x140007aba  push    rbp
0x140007abb  push    rsi
0x140007abc  push    rdi
0x140007abd  push    r12
0x140007abf  push    r13
0x140007ac1  push    r14
0x140007ac3  push    r15
0x140007ac5  sub     rsp, 28h
0x140007ac9  mov     rbx, [rcx+10h]
0x140007acd  mov     r8, 7FFFFFFFFFFFFFFEh
0x140007ad7  mov     rax, r8
0x140007ada  mov     r13, r9
0x140007add  sub     rax, rbx
0x140007ae0  mov     rdi, rcx
0x140007ae3  cmp     rax, rdx
0x140007ae6  jb      loc_140007BE9
0x140007aec  mov     r14, [rcx+18h]
0x140007af0  lea     rbp, [rbx+rdx]
0x140007af4  mov     rcx, rbp
0x140007af7  or      rcx, 7
0x140007afb  cmp     rcx, r8
0x140007afe  ja      short loc_140007B1C
0x140007b00  mov     rdx, r14
0x140007b03  mov     rax, r8
0x140007b06  shr     rdx, 1
0x140007b09  sub     rax, rdx
0x140007b0c  cmp     r14, rax
0x140007b0f  ja      short loc_140007B1C
0x140007b11  lea     r8, [r14+rdx]
0x140007b15  cmp     rcx, r8
0x140007b18  cmovnb  r8, rcx
0x140007b1c  lea     rdx, [rsp+68h+arg_0]
0x140007b21  mov     [rsp+68h+arg_0], r8
0x140007b26  call    ??$_Allocate_for_capacity@$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@CAPEAGAEAV?$allocator@G@1@AEA_K@Z; std::wstring::_Allocate_for_capacity<0>(std::allocator<ushort> &,unsigned __int64 &)
0x140007b2b  mov     rdx, [rsp+68h+arg_20]
0x140007b33  lea     r8, [rbx+rbx]; Size
0x140007b37  mov     rcx, [rsp+68h+arg_0]
0x140007b3c  mov     rsi, rax
0x140007b3f  mov     [rdi+10h], rbp
0x140007b43  mov     [rdi+18h], rcx
0x140007b47  lea     r15, [r8+rax]
0x140007b4b  lea     rbp, [rdx+rdx]
0x140007b4f  mov     rcx, rax; void *
0x140007b52  lea     r12, [rbx+rdx]
0x140007b56  cmp     r14, 7
0x140007b5a  jbe     short loc_140007BB5
0x140007b5c  mov     rbx, [rdi]
0x140007b5f  mov     rdx, rbx; Src
0x140007b62  call    memcpy_0
0x140007b67  mov     r8, rbp; Size
0x140007b6a  mov     rdx, r13; Src
0x140007b6d  mov     rcx, r15; void *
0x140007b70  call    memcpy_0
0x140007b75  xor     eax, eax
0x140007b77  lea     rdx, ds:2[r14*2]; unsigned __int64
0x140007b7f  mov     [rsi+r12*2], ax
0x140007b84  cmp     rdx, 1000h
0x140007b8b  jb      short loc_140007BAB
0x140007b8d  mov     rcx, [rbx-8]
0x140007b91  sub     rbx, rcx
0x140007b94  sub     rbx, 8
0x140007b98  cmp     rbx, 1Fh
0x140007b9c  ja      short loc_140007BA4
0x140007b9e  add     rdx, 27h ; '''
0x140007ba2  jmp     short loc_140007BAE
0x140007ba4  mov     ecx, 5
0x140007ba9  int     29h; Win8: RtlFailFast(ecx)
0x140007bab  mov     rcx, rbx; void *
0x140007bae  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140007bb3  jmp     short loc_140007BD2
0x140007bb5  mov     rdx, rdi; Src
0x140007bb8  call    memcpy_0
0x140007bbd  mov     r8, rbp; Size
0x140007bc0  mov     rdx, r13; Src
0x140007bc3  mov     rcx, r15; void *
0x140007bc6  call    memcpy_0
0x140007bcb  xor     eax, eax
0x140007bcd  mov     [rsi+r12*2], ax
0x140007bd2  mov     rax, rdi
0x140007bd5  mov     [rax], rsi
0x140007bd8  add     rsp, 28h
0x140007bdc  pop     r15
0x140007bde  pop     r14
0x140007be0  pop     r13
0x140007be2  pop     r12
0x140007be4  pop     rdi
0x140007be5  pop     rsi
0x140007be6  pop     rbp
0x140007be7  pop     rbx
0x140007be8  retn
0x140007be9  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
```
