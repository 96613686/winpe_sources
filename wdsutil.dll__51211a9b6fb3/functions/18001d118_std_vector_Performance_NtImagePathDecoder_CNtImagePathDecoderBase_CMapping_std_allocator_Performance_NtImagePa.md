# std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>>::_Reallocate(unsigned __int64)

- ea: `0x18001d118`
- end: `0x18001d200`
- name: `?_Reallocate@?$vector@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@V?$allocator@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@IEAAX_K@Z`
- size: `232`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18001d55c`

## callees

- `0x180001374`
- `0x180001518`
- `0x180014284`
- `0x1800157d4`
- `0x18001d118`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18001d1bb`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001d1bb`

## pseudocode

```c
void __fastcall std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>::_Reallocate(
        __int64 a1,
        unsigned __int64 a2)
{
  char *v4; // rbx
  void ***v5; // r15
  __int64 v6; // rcx
  void **v7; // r14
  void **v8; // r13
  unsigned __int64 v9; // r12
  char *v10; // [rsp+78h] [rbp+10h]

  v4 = 0;
  v10 = 0;
  if ( a2 )
  {
    if ( a2 > 0x3FFFFFFFFFFFFFFLL || (v4 = (char *)operator new(a2 << 6), (v10 = v4) == 0) )
      std::_Xbad_alloc();
  }
  v5 = (void ***)(a1 + 8);
  try
  {
    std::_Uninit_move<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>();
    v7 = *(void ***)a1;
    v8 = *v5;
    v9 = (unsigned __int64)*v5 - *(_QWORD *)a1;
    if ( *(_QWORD *)a1 )
    {
      if ( v7 != v8 )
      {
        do
        {
          Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping::~CMapping(v7);
          v7 += 8;
        }
        while ( v7 != v8 );
        v5 = (void ***)(a1 + 8);
      }
      operator delete(*(void **)a1);
    }
    *(_QWORD *)(a1 + 16) = &v4[64 * a2];
    *v5 = (void **)&v4[v9 & 0xFFFFFFFFFFFFFFC0uLL];
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
0x18001d118  mov     rax, rsp
0x18001d11b  push    rdi
0x18001d11c  push    r12
0x18001d11e  push    r13
0x18001d120  push    r14
0x18001d122  push    r15
0x18001d124  sub     rsp, 40h
0x18001d128  mov     qword ptr [rax-38h], 0FFFFFFFFFFFFFFFEh
0x18001d130  mov     [rax+8], rbx
0x18001d134  mov     [rax+18h], rsi
0x18001d138  mov     rdi, rdx
0x18001d13b  mov     rsi, rcx
0x18001d13e  xor     ebx, ebx
0x18001d140  mov     [rsp+68h+arg_8], rbx
0x18001d145  test    rdx, rdx
0x18001d148  jz      short loc_18001D17A
0x18001d14a  mov     rax, 3FFFFFFFFFFFFFFh
0x18001d154  cmp     rdx, rax
0x18001d157  ja      loc_18001D1FA
0x18001d15d  mov     rcx, rdx
0x18001d160  shl     rcx, 6; Size
0x18001d164  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001d169  mov     rbx, rax
0x18001d16c  mov     [rsp+68h+arg_8], rax
0x18001d171  test    rax, rax
0x18001d174  jz      loc_18001D1FA
0x18001d17a  lea     r15, [rsi+8]
0x18001d17e  mov     r8, rbx
0x18001d181  mov     rdx, [r15]
0x18001d184  mov     rcx, [rsi]
0x18001d187  call    ??$_Uninit_move@PEAUCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@PEAU1234@V?$allocator@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@U1234@@std@@YAPEAUCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@PEAU1234@00AEAU?$_Wrap_alloc@V?$allocator@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@0@0U_Nonscalar_ptr_iterator_tag@0@@Z; std::_Uninit_move<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>(Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *,std::_Wrap_alloc<std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>> &,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *,std::_Nonscalar_ptr_iterator_tag)
0x18001d18c  nop
0x18001d18d  mov     r14, [rsi]
0x18001d190  mov     r13, [r15]
0x18001d193  mov     r12, r13
0x18001d196  sub     r12, r14
0x18001d199  test    r14, r14
0x18001d19c  jz      short loc_18001D1C7
0x18001d19e  cmp     r14, r13
0x18001d1a1  jz      short loc_18001D1B8
0x18001d1a3  mov     rcx, r14; this
0x18001d1a6  call    ??1CMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@QEAA@XZ; Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping::~CMapping(void)
0x18001d1ab  add     r14, 40h ; '@'
0x18001d1af  cmp     r14, r13
0x18001d1b2  jnz     short loc_18001D1A3
0x18001d1b4  lea     r15, [rsi+8]
0x18001d1b8  mov     rcx, [rsi]
0x18001d1bb  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001d1c2  nop     dword ptr [rax+rax+00h]
0x18001d1c7  shl     rdi, 6
0x18001d1cb  add     rdi, rbx
0x18001d1ce  mov     [rsi+10h], rdi
0x18001d1d2  and     r12, 0FFFFFFFFFFFFFFC0h
0x18001d1d6  add     r12, rbx
0x18001d1d9  mov     [r15], r12
0x18001d1dc  mov     [rsi], rbx
0x18001d1df  lea     r11, [rsp+68h+var_28]
0x18001d1e4  mov     rbx, [r11+30h]
0x18001d1e8  mov     rsi, [r11+40h]
0x18001d1ec  mov     rsp, r11
0x18001d1ef  pop     r15
0x18001d1f1  pop     r14
0x18001d1f3  pop     r13
0x18001d1f5  pop     r12
0x18001d1f7  pop     rdi
0x18001d1f8  retn
0x18001d1fa  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
