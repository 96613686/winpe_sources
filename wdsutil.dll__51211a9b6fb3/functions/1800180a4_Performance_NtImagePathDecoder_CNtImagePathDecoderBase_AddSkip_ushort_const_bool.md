# Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddSkip(ushort const *,bool)

- ea: `0x1800180a4`
- end: `0x1800182a1`
- name: `?AddSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@IEAAXPEBG_N@Z`
- size: `509`
- prototype: `void __fastcall(Performance::NtImagePathDecoder::CNtImagePathDecoderBase *__hidden this, const unsigned __int16 *, bool)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x1800198f0`

## callees

- `0x180012b44`
- `0x180012cbc`
- `0x1800180a4`
- `0x18001d208`
- `0x18001d320`
- `0x18001d438`
- `0x1800319f0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180018268`
- `msvcrt!??3@YAXPEAX@Z` at `0x180018268`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddSkip(
        Performance::NtImagePathDecoder::CNtImagePathDecoderBase *this,
        unsigned __int16 *a2)
{
  __int64 v3; // r8
  void **v4; // rax
  unsigned __int64 v5; // rcx
  char v6; // al
  __int64 v7; // r8
  __int64 v8; // rdi
  __int64 v9; // rcx
  unsigned __int64 v10; // rcx
  unsigned __int64 v11; // r8
  unsigned __int64 v12; // rdx
  __int64 v13; // rcx
  unsigned __int64 v14; // rcx
  unsigned __int64 v15; // r8
  unsigned __int64 v16; // rdx
  _QWORD *v17; // rcx
  __int64 v18; // [rsp+20h] [rbp-30h]
  void *Src[2]; // [rsp+28h] [rbp-28h] BYREF
  __int64 v20; // [rsp+38h] [rbp-18h]
  unsigned __int64 v21; // [rsp+40h] [rbp-10h]

  HIWORD(v18) = -1;
  v21 = 7;
  v20 = 0;
  LOWORD(Src[0]) = 0;
  if ( *a2 )
  {
    v3 = -1;
    do
      ++v3;
    while ( a2[v3] );
  }
  std::wstring::assign(Src, a2);
  if ( !v20 )
    goto LABEL_8;
  v4 = Src;
  if ( v21 >= 8 )
    v4 = (void **)Src[0];
  if ( *((_WORD *)v4 + v20 - 1) != 92 )
LABEL_8:
    std::wstring::push_back(Src);
  v5 = *((_QWORD *)this + 4);
  if ( (unsigned __int64)Src >= v5 || (v6 = 1, *((_QWORD *)this + 3) > (unsigned __int64)Src) )
    v6 = 0;
  v7 = *((_QWORD *)this + 5);
  if ( v6 )
  {
    v8 = *((_QWORD *)this + 3);
    if ( v5 == v7 && !((__int64)(v7 - v5) >> 5) )
    {
      v9 = (__int64)(v5 - v8) >> 5;
      if ( v9 == 0x7FFFFFFFFFFFFFFLL )
        std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>::_Xlen(0x7FFFFFFFFFFFFFFLL);
      v10 = v9 + 1;
      v11 = (v7 - v8) >> 5;
      v12 = 0;
      if ( 0x7FFFFFFFFFFFFFFLL - (v11 >> 1) >= v11 )
        v12 = v11 + (v11 >> 1);
      if ( v12 < v10 )
        v12 = v10;
      std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip>::_Reallocate((char *)this + 24, v12);
    }
  }
  else if ( v5 == v7 && !((__int64)(v7 - v5) >> 5) )
  {
    v13 = (__int64)(v5 - *((_QWORD *)this + 3)) >> 5;
    if ( v13 == 0x7FFFFFFFFFFFFFFLL )
      std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>::_Xlen(0x7FFFFFFFFFFFFFFLL);
    v14 = v13 + 1;
    v15 = (v7 - *((_QWORD *)this + 3)) >> 5;
    v16 = 0;
    if ( 0x7FFFFFFFFFFFFFFLL - (v15 >> 1) >= v15 )
      v16 = v15 + (v15 >> 1);
    if ( v16 < v14 )
      v16 = v14;
    std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip>::_Reallocate((char *)this + 24, v16);
  }
  v17 = (_QWORD *)*((_QWORD *)this + 4);
  v17[3] = 7;
  v17[2] = 0;
  *(_WORD *)v17 = 0;
  std::wstring::assign(v17);
  *((_QWORD *)this + 4) += 32LL;
  if ( v21 >= 8 )
    operator delete(Src[0]);
}

```

## disassembly

```asm
0x1800180a4  mov     rax, rsp
0x1800180a7  push    rbp
0x1800180a8  push    rsi
0x1800180a9  push    rdi
0x1800180aa  push    r14
0x1800180ac  push    r15
0x1800180ae  mov     rbp, rsp
0x1800180b1  sub     rsp, 50h
0x1800180b5  mov     [rbp+var_30], 0FFFFFFFFFFFFFFFEh
0x1800180bd  mov     [rax+18h], rbx
0x1800180c1  mov     rax, cs:__security_cookie
0x1800180c8  xor     rax, rsp
0x1800180cb  mov     [rbp+var_8], rax
0x1800180cf  mov     rbx, rcx
0x1800180d2  mov     r15d, 7
0x1800180d8  mov     [rbp+var_10], r15
0x1800180dc  xor     esi, esi
0x1800180de  mov     [rbp+var_18], rsi
0x1800180e2  mov     word ptr [rbp+Src], si
0x1800180e6  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800180ea  cmp     [rdx], si
0x1800180ed  jnz     short loc_1800180F4
0x1800180ef  mov     r8d, esi
0x1800180f2  jmp     short loc_180018101
0x1800180f4  mov     r8, r14
0x1800180f7  inc     r8
0x1800180fa  cmp     [rdx+r8*2], si
0x1800180ff  jnz     short loc_1800180F7
0x180018101  lea     rcx, [rbp+Src]; void *
0x180018105  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x18001810a  nop
0x18001810b  mov     rcx, [rbp+var_18]
0x18001810f  test    rcx, rcx
0x180018112  jz      short loc_18001812A
0x180018114  lea     rax, [rbp+Src]
0x180018118  cmp     [rbp+var_10], 8
0x18001811d  cmovnb  rax, [rbp+Src]
0x180018122  cmp     word ptr [rax+rcx*2-2], 5Ch ; '\'
0x180018128  jz      short loc_180018133
0x18001812a  lea     rcx, [rbp+Src]; Src
0x18001812e  call    ?push_back@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXG@Z; std::wstring::push_back(ushort)
0x180018133  mov     rcx, [rbx+20h]
0x180018137  lea     rax, [rbp+Src]
0x18001813b  cmp     rax, rcx
0x18001813e  jnb     short loc_18001814C
0x180018140  lea     rax, [rbp+Src]
0x180018144  cmp     [rbx+18h], rax
0x180018148  mov     al, 1
0x18001814a  jbe     short loc_18001814F
0x18001814c  mov     al, sil
0x18001814f  mov     r8, [rbx+28h]
0x180018153  test    al, al
0x180018155  jz      short loc_1800181D2
0x180018157  mov     rdi, [rbx+18h]
0x18001815b  cmp     rcx, r8
0x18001815e  jnz     short loc_1800181C1
0x180018160  mov     rax, r8
0x180018163  sub     rax, rcx
0x180018166  sar     rax, 5
0x18001816a  cmp     rax, 1
0x18001816e  jnb     short loc_1800181C1
0x180018170  sub     rcx, rdi
0x180018173  sar     rcx, 5
0x180018177  mov     r9, 7FFFFFFFFFFFFFFh
0x180018181  mov     rax, r9
0x180018184  sub     rax, rcx
0x180018187  cmp     rax, 1
0x18001818b  jb      loc_18001829B
0x180018191  inc     rcx
0x180018194  sub     r8, rdi
0x180018197  sar     r8, 5
0x18001819b  mov     rax, r8
0x18001819e  shr     rax, 1
0x1800181a1  sub     r9, rax
0x1800181a4  add     rax, r8
0x1800181a7  mov     rdx, rsi
0x1800181aa  cmp     r9, r8
0x1800181ad  cmovnb  rdx, rax
0x1800181b1  cmp     rdx, rcx
0x1800181b4  cmovb   rdx, rcx
0x1800181b8  lea     rcx, [rbx+18h]
0x1800181bc  call    ?_Reallocate@?$vector@UCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@V?$allocator@UCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@IEAAX_K@Z; std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip>::_Reallocate(unsigned __int64)
0x1800181c1  lea     rdx, [rbp+Src]
0x1800181c5  sub     rdx, rdi
0x1800181c8  and     rdx, 0FFFFFFFFFFFFFFE0h
0x1800181cc  add     rdx, [rbx+18h]
0x1800181d0  jmp     short loc_18001823E
0x1800181d2  cmp     rcx, r8
0x1800181d5  jnz     short loc_18001823A
0x1800181d7  mov     rax, r8
0x1800181da  sub     rax, rcx
0x1800181dd  sar     rax, 5
0x1800181e1  cmp     rax, 1
0x1800181e5  jnb     short loc_18001823A
0x1800181e7  sub     rcx, [rbx+18h]
0x1800181eb  sar     rcx, 5
0x1800181ef  mov     r9, 7FFFFFFFFFFFFFFh
0x1800181f9  mov     rax, r9
0x1800181fc  sub     rax, rcx
0x1800181ff  cmp     rax, 1
0x180018203  jb      loc_180018295
0x180018209  inc     rcx
0x18001820c  sub     r8, [rbx+18h]
0x180018210  sar     r8, 5
0x180018214  mov     rax, r8
0x180018217  shr     rax, 1
0x18001821a  sub     r9, rax
0x18001821d  add     rax, r8
0x180018220  mov     rdx, rsi
0x180018223  cmp     r9, r8
0x180018226  cmovnb  rdx, rax
0x18001822a  cmp     rdx, rcx
0x18001822d  cmovb   rdx, rcx
0x180018231  lea     rcx, [rbx+18h]
0x180018235  call    ?_Reallocate@?$vector@UCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@V?$allocator@UCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@IEAAX_K@Z; std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip>::_Reallocate(unsigned __int64)
0x18001823a  lea     rdx, [rbp+Src]
0x18001823e  mov     rcx, [rbx+20h]; void *
0x180018242  mov     [rcx+18h], r15
0x180018246  mov     [rcx+10h], rsi
0x18001824a  mov     [rcx], si
0x18001824d  mov     r9, r14
0x180018250  xor     r8d, r8d
0x180018253  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x180018258  add     qword ptr [rbx+20h], 20h ; ' '
0x18001825d  cmp     [rbp+var_10], 8
0x180018262  jb      short loc_180018274
0x180018264  mov     rcx, [rbp+Src]
0x180018268  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001826f  nop     dword ptr [rax+rax+00h]
0x180018274  mov     rcx, [rbp+var_8]
0x180018278  xor     rcx, rsp; StackCookie
0x18001827b  call    __security_check_cookie
0x180018280  mov     rbx, [rsp+50h+arg_10]
0x180018288  add     rsp, 50h
0x18001828c  pop     r15
0x18001828e  pop     r14
0x180018290  pop     rdi
0x180018291  pop     rsi
0x180018292  pop     rbp
0x180018293  retn
0x180018295  call    ?_Xlen@?$vector@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@V?$allocator@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@IEBAXXZ; std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>::_Xlen(void)
0x18001829b  call    ?_Xlen@?$vector@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@V?$allocator@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@IEBAXXZ; std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>::_Xlen(void)
```
