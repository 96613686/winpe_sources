# CLI::App::_find_subcommand(std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &,bool,bool)

- ea: `0x140020fd0`
- end: `0x1400211b7`
- name: `?_find_subcommand@App@CLI@@IEBAPEAV12@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@_N1@Z`
- size: `487`
- prototype: ``
- caller_count: `7`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140020fd0`
- `0x1400215f0`
- `0x140022fb0`
- `0x140023ac0`
- `0x1400246d0`
- `0x140026b00`
- `0x140027710`

## callees

- `0x14000f804`
- `0x140010614`
- `0x140020fd0`
- `0x14002a0c0`
- `0x14004a9e0`
- `0x14004aaac`

## pseudocode

```c
__int64 __fastcall CLI::App::_find_subcommand(__int64 a1, __int64 a2, unsigned __int8 a3, char a4)
{
  __int64 *v7; // rsi
  __int64 *v8; // r13
  __int64 v9; // rcx
  __int64 result; // rax
  __int128 *v11; // rbp
  unsigned __int64 v12; // rdi
  unsigned __int64 v13; // rbx
  size_t v14; // rax
  size_t v15; // rcx
  _QWORD *v16; // rax
  void *v17; // rax
  void *v18; // rcx
  __int128 v19; // [rsp+20h] [rbp-68h] BYREF
  unsigned __int64 v20; // [rsp+30h] [rbp-58h]
  __int64 v21; // [rsp+38h] [rbp-50h]

  v7 = *(__int64 **)(a1 + 768);
  v8 = *(__int64 **)(a1 + 776);
  if ( v7 != v8 )
  {
    while ( 1 )
    {
      v9 = *v7;
      if ( *(_BYTE *)(*v7 + 77) && a3 )
        goto LABEL_27;
      if ( !*(_QWORD *)(v9 + 24) )
      {
        result = CLI::App::_find_subcommand(v9, a2, a3);
        if ( result )
          return result;
      }
      v19 = 0;
      v20 = 0;
      v21 = 0;
      if ( *(_QWORD *)(a2 + 24) <= 0xFu )
        v11 = (__int128 *)a2;
      else
        v11 = *(__int128 **)a2;
      v12 = *(_QWORD *)(a2 + 16);
      if ( v12 > 0x7FFFFFFFFFFFFFFFLL )
        std::_Xlen_string();
      if ( v12 > 0xF )
        break;
      v20 = *(_QWORD *)(a2 + 16);
      v21 = 15;
      v19 = *v11;
LABEL_24:
      if ( (unsigned __int8)CLI::App::check_name(*v7, &v19) )
      {
        result = *v7;
        if ( !*(_DWORD *)(*v7 + 804) || !a4 )
          return result;
      }
LABEL_27:
      v7 += 2;
      if ( v7 == v8 )
        return 0;
    }
    v13 = v12 | 0xF;
    if ( (v12 | 0xF) > 0x7FFFFFFFFFFFFFFFLL )
    {
      v13 = 0x7FFFFFFFFFFFFFFFLL;
      v14 = 0x8000000000000027uLL;
LABEL_20:
      v17 = operator new(v14);
      v18 = v17;
      if ( !v17 )
        __fastfail(5u);
      v16 = (_QWORD *)(((unsigned __int64)v17 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
      *(v16 - 1) = v18;
      goto LABEL_23;
    }
    if ( v13 < 0x16 )
      v13 = 22;
    v15 = v13 + 1;
    if ( v13 == -1 )
    {
      v16 = 0;
    }
    else
    {
      if ( v15 >= 0x1000 )
      {
        v14 = v13 + 40;
        if ( v13 + 40 < v13 + 1 )
          std::_Throw_bad_array_new_length();
        goto LABEL_20;
      }
      v16 = operator new(v15);
    }
LABEL_23:
    *(_QWORD *)&v19 = v16;
    v20 = v12;
    v21 = v13;
    memcpy_0(v16, v11, v12 + 1);
    goto LABEL_24;
  }
  return 0;
}

```

## disassembly

```asm
0x140020fd0  push    rbx
0x140020fd2  push    rbp
0x140020fd3  push    rsi
0x140020fd4  push    rdi
0x140020fd5  push    r12
0x140020fd7  push    r13
0x140020fd9  push    r14
0x140020fdb  push    r15
0x140020fdd  sub     rsp, 48h
0x140020fe1  movzx   r15d, r9b
0x140020fe5  movzx   r12d, r8b
0x140020fe9  mov     r14, rdx
0x140020fec  mov     rsi, [rcx+300h]
0x140020ff3  mov     r13, [rcx+308h]
0x140020ffa  cmp     rsi, r13
0x140020ffd  jz      loc_140021191
0x140021003  mov     rax, 7FFFFFFFFFFFFFFFh
0x14002100d  mov     rdx, 8000000000000027h
0x140021017  mov     r8d, 16h
0x14002101d  nop     dword ptr [rax]
0x140021020  mov     rcx, [rsi]
0x140021023  cmp     byte ptr [rcx+4Dh], 0
0x140021027  jz      short loc_140021032
0x140021029  test    r12b, r12b
0x14002102c  jnz     loc_140021184
0x140021032  cmp     qword ptr [rcx+18h], 0
0x140021037  jnz     short loc_14002106C
0x140021039  movzx   r9d, r15b
0x14002103d  movzx   r8d, r12b
0x140021041  mov     rdx, r14
0x140021044  call    ?_find_subcommand@App@CLI@@IEBAPEAV12@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@_N1@Z; CLI::App::_find_subcommand(std::string const &,bool,bool)
0x140021049  test    rax, rax
0x14002104c  jnz     loc_140021193
0x140021052  mov     rax, 7FFFFFFFFFFFFFFFh
0x14002105c  mov     rdx, 8000000000000027h
0x140021066  mov     r8d, 16h
0x14002106c  xorps   xmm0, xmm0
0x14002106f  movups  [rsp+88h+var_68], xmm0
0x140021074  mov     [rsp+88h+var_58], 0
0x14002107d  mov     [rsp+88h+var_50], 0
0x140021086  cmp     qword ptr [r14+18h], 0Fh
0x14002108b  jbe     short loc_140021092
0x14002108d  mov     rbp, [r14]
0x140021090  jmp     short loc_140021095
0x140021092  mov     rbp, r14
0x140021095  mov     rdi, [r14+10h]
0x140021099  cmp     rdi, rax
0x14002109c  ja      loc_1400211B1
0x1400210a2  cmp     rdi, 0Fh
0x1400210a6  ja      short loc_1400210C4
0x1400210a8  mov     [rsp+88h+var_58], rdi
0x1400210ad  mov     [rsp+88h+var_50], 0Fh
0x1400210b6  movups  xmm0, xmmword ptr [rbp+0]
0x1400210ba  movups  [rsp+88h+var_68], xmm0
0x1400210bf  jmp     loc_140021148
0x1400210c4  mov     rbx, rdi
0x1400210c7  or      rbx, 0Fh
0x1400210cb  cmp     rbx, rax
0x1400210ce  jbe     short loc_1400210D8
0x1400210d0  mov     rbx, rax
0x1400210d3  mov     rax, rdx
0x1400210d6  jmp     short loc_140021103
0x1400210d8  cmp     rbx, 16h
0x1400210dc  cmovb   rbx, r8
0x1400210e0  lea     rcx, [rbx+1]; Size
0x1400210e4  test    rcx, rcx
0x1400210e7  jnz     short loc_1400210ED
0x1400210e9  xor     eax, eax
0x1400210eb  jmp     short loc_14002112A
0x1400210ed  cmp     rcx, 1000h
0x1400210f4  jb      short loc_140021125
0x1400210f6  lea     rax, [rcx+27h]
0x1400210fa  cmp     rax, rcx
0x1400210fd  jbe     loc_1400211AB
0x140021103  mov     rcx, rax; Size
0x140021106  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14002110b  mov     rcx, rax
0x14002110e  test    rax, rax
0x140021111  jz      loc_1400211A4
0x140021117  add     rax, 27h ; '''
0x14002111b  and     rax, 0FFFFFFFFFFFFFFE0h
0x14002111f  mov     [rax-8], rcx
0x140021123  jmp     short loc_14002112A
0x140021125  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14002112a  mov     qword ptr [rsp+88h+var_68], rax
0x14002112f  mov     [rsp+88h+var_58], rdi
0x140021134  mov     [rsp+88h+var_50], rbx
0x140021139  lea     r8, [rdi+1]; Size
0x14002113d  mov     rdx, rbp; Src
0x140021140  mov     rcx, rax; void *
0x140021143  call    memcpy_0
0x140021148  lea     rdx, [rsp+88h+var_68]
0x14002114d  mov     rcx, [rsi]
0x140021150  call    ?check_name@App@CLI@@QEBA_NV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; CLI::App::check_name(std::string)
0x140021155  test    al, al
0x140021157  jz      short loc_14002116A
0x140021159  mov     rax, [rsi]
0x14002115c  cmp     dword ptr [rax+324h], 0
0x140021163  jbe     short loc_140021193
0x140021165  test    r15b, r15b
0x140021168  jz      short loc_140021193
0x14002116a  mov     r8d, 16h
0x140021170  mov     rdx, 8000000000000027h
0x14002117a  mov     rax, 7FFFFFFFFFFFFFFFh
0x140021184  add     rsi, 10h
0x140021188  cmp     rsi, r13
0x14002118b  jnz     loc_140021020
0x140021191  xor     eax, eax
0x140021193  add     rsp, 48h
0x140021197  pop     r15
0x140021199  pop     r14
0x14002119b  pop     r13
0x14002119d  pop     r12
0x14002119f  pop     rdi
0x1400211a0  pop     rsi
0x1400211a1  pop     rbp
0x1400211a2  pop     rbx
0x1400211a3  retn
0x1400211a4  mov     ecx, 5
0x1400211a9  int     29h; Win8: RtlFailFast(ecx)
0x1400211ab  call    ?_Throw_bad_array_new_length@std@@YAXXZ; std::_Throw_bad_array_new_length(void)
0x1400211b1  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
```
