# std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip>>::_Reallocate(unsigned __int64)

- ea: `0x18001d208`
- end: `0x18001d31a`
- name: `?_Reallocate@?$vector@UCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@V?$allocator@UCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@IEAAX_K@Z`
- size: `274`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1800180a4`

## callees

- `0x180001374`
- `0x180001518`
- `0x1800142fc`
- `0x18001d208`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18001d2a0`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001d2d3`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001d2a0`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001d2d3`

## pseudocode

```c
void __fastcall std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip>::_Reallocate(
        __int64 a1,
        unsigned __int64 a2)
{
  char *v4; // rdi
  void **v5; // r14
  __int64 v6; // rcx
  void **v7; // rbx
  void **v8; // r13
  unsigned __int64 v9; // r15
  char *v10; // [rsp+78h] [rbp+10h]

  v4 = 0;
  v10 = 0;
  if ( a2 )
  {
    if ( a2 > 0x7FFFFFFFFFFFFFFLL || (v4 = (char *)operator new(32 * a2), (v10 = v4) == 0) )
      std::_Xbad_alloc();
  }
  v5 = (void **)(a1 + 8);
  try
  {
    std::_Uninit_move<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip *,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip *,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip>,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip>();
    v7 = *(void ***)a1;
    v8 = (void **)*v5;
    v9 = (unsigned __int64)*v5 - *(_QWORD *)a1;
    if ( *(_QWORD *)a1 )
    {
      if ( v7 != v8 )
      {
        do
        {
          if ( (unsigned __int64)v7[3] >= 8 )
            operator delete(*v7);
          v7[3] = (void *)7;
          v7[2] = 0;
          *(_WORD *)v7 = 0;
          v7 += 4;
        }
        while ( v7 != v8 );
        v5 = (void **)(a1 + 8);
      }
      operator delete(*(void **)a1);
    }
    *(_QWORD *)(a1 + 16) = &v4[32 * a2];
    *v5 = &v4[v9 & 0xFFFFFFFFFFFFFFE0uLL];
    *(_QWORD *)a1 = v4;
  }
  catch ( ... )
  {
    std::_Tree_buy<unsigned short const *>::_Freenode0(v6, v10);
    throw;
  }
}

```

## disassembly

```asm
0x18001d208  mov     rax, rsp
0x18001d20b  push    rdi
0x18001d20c  push    r12
0x18001d20e  push    r13
0x18001d210  push    r14
0x18001d212  push    r15
0x18001d214  sub     rsp, 40h
0x18001d218  mov     qword ptr [rax-38h], 0FFFFFFFFFFFFFFFEh
0x18001d220  mov     [rax+8], rbx
0x18001d224  mov     [rax+18h], rsi
0x18001d228  mov     rsi, rdx
0x18001d22b  mov     r12, rcx
0x18001d22e  xor     edi, edi
0x18001d230  mov     [rsp+68h+arg_8], rdi
0x18001d235  test    rdx, rdx
0x18001d238  jz      short loc_18001D26A
0x18001d23a  mov     rax, 7FFFFFFFFFFFFFFh
0x18001d244  cmp     rdx, rax
0x18001d247  ja      loc_18001D314
0x18001d24d  mov     rcx, rdx
0x18001d250  shl     rcx, 5; Size
0x18001d254  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001d259  mov     rdi, rax
0x18001d25c  mov     [rsp+68h+arg_8], rax
0x18001d261  test    rax, rax
0x18001d264  jz      loc_18001D314
0x18001d26a  lea     r14, [r12+8]
0x18001d26f  mov     r8, rdi
0x18001d272  mov     rdx, [r14]
0x18001d275  mov     rcx, [r12]
0x18001d279  call    ??$_Uninit_move@PEAUCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@PEAU1234@V?$allocator@UCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@U1234@@std@@YAPEAUCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@PEAU1234@00AEAU?$_Wrap_alloc@V?$allocator@UCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@0@0U_Nonscalar_ptr_iterator_tag@0@@Z; std::_Uninit_move<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip *,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip *,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip>,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip>(Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip *,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip *,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip *,std::_Wrap_alloc<std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip>> &,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip *,std::_Nonscalar_ptr_iterator_tag)
0x18001d27e  nop
0x18001d27f  mov     rbx, [r12]
0x18001d283  mov     r13, [r14]
0x18001d286  mov     r15, r13
0x18001d289  sub     r15, rbx
0x18001d28c  test    rbx, rbx
0x18001d28f  jz      short loc_18001D2DF
0x18001d291  cmp     rbx, r13
0x18001d294  jz      short loc_18001D2CF
0x18001d296  cmp     qword ptr [rbx+18h], 8
0x18001d29b  jb      short loc_18001D2AC
0x18001d29d  mov     rcx, [rbx]
0x18001d2a0  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001d2a7  nop     dword ptr [rax+rax+00h]
0x18001d2ac  mov     qword ptr [rbx+18h], 7
0x18001d2b4  mov     qword ptr [rbx+10h], 0
0x18001d2bc  xor     eax, eax
0x18001d2be  mov     [rbx], ax
0x18001d2c1  add     rbx, 20h ; ' '
0x18001d2c5  cmp     rbx, r13
0x18001d2c8  jnz     short loc_18001D296
0x18001d2ca  lea     r14, [r12+8]
0x18001d2cf  mov     rcx, [r12]
0x18001d2d3  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001d2da  nop     dword ptr [rax+rax+00h]
0x18001d2df  shl     rsi, 5
0x18001d2e3  add     rsi, rdi
0x18001d2e6  mov     [r12+10h], rsi
0x18001d2eb  and     r15, 0FFFFFFFFFFFFFFE0h
0x18001d2ef  add     r15, rdi
0x18001d2f2  mov     [r14], r15
0x18001d2f5  mov     [r12], rdi
0x18001d2f9  lea     r11, [rsp+68h+var_28]
0x18001d2fe  mov     rbx, [r11+30h]
0x18001d302  mov     rsi, [r11+40h]
0x18001d306  mov     rsp, r11
0x18001d309  pop     r15
0x18001d30b  pop     r14
0x18001d30d  pop     r13
0x18001d30f  pop     r12
0x18001d311  pop     rdi
0x18001d312  retn
0x18001d314  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
