# CLI::detail::remove_quotes(std::vector<std::basic_string<char,std::char_traits<char>,std::allocator<char>>,std::allocator<std::basic_string<char,std::char_traits<char>,std::allocator<char>>>> &)

- ea: `0x14003de60`
- end: `0x14003e0d9`
- name: `?remove_quotes@detail@CLI@@YAXAEAV?$vector@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@std@@@Z`
- size: `633`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x140030720`
- `0x14003c120`

## callees

- `0x14000f7e0`
- `0x14000fab8`
- `0x140010620`
- `0x14003d400`
- `0x14003dd70`
- `0x14003de60`

## pseudocode

```c
void __fastcall CLI::detail::remove_quotes(char **a1)
{
  char *v1; // rbx
  char *v2; // rsi
  unsigned __int64 v3; // rcx
  char *v4; // rax
  char *v5; // rdx
  char *v6; // rdi
  unsigned __int64 v7; // rdx
  char *v8; // rcx
  char *v9; // rax
  void *v10; // rcx
  char *v11; // rax
  char *v12; // rax
  char *v13; // rax
  char *v14; // rdx
  char *v15; // rax
  __int64 v16; // r8
  char *v17; // rax
  __int64 v18; // rdi
  __int64 v19; // rdx
  char *v20; // rax
  __int64 v21; // rdi
  void *v22; // [rsp+20h] [rbp-38h] BYREF
  unsigned __int64 v23; // [rsp+38h] [rbp-20h]

  v1 = *a1;
  v2 = a1[1];
  if ( *a1 != v2 )
  {
    do
    {
      v3 = *((_QWORD *)v1 + 3);
      v4 = v1;
      if ( v3 > 0xF )
        v4 = *(char **)v1;
      if ( *v4 != 34 )
        goto LABEL_21;
      v5 = v1;
      if ( v3 > 0xF )
        v5 = *(char **)v1;
      if ( v5[*((_QWORD *)v1 + 2) - 1] == 34 )
      {
        CLI::detail::remove_quotes(v1);
        v6 = (char *)CLI::detail::remove_escaped_characters(&v22, v1);
        if ( v1 != v6 )
        {
          v7 = *((_QWORD *)v1 + 3);
          if ( v7 > 0xF )
          {
            v8 = *(char **)v1;
            if ( v7 + 1 < 0x1000 )
            {
              v9 = *(char **)v1;
            }
            else
            {
              v9 = (char *)*((_QWORD *)v8 - 1);
              if ( (unsigned __int64)(v8 - v9 - 8) > 0x1F )
                goto LABEL_46;
            }
            operator delete(v9);
          }
          *((_QWORD *)v1 + 2) = 0;
          *((_QWORD *)v1 + 3) = 15;
          *v1 = 0;
          *(_OWORD *)v1 = *(_OWORD *)v6;
          *((_OWORD *)v1 + 1) = *((_OWORD *)v6 + 1);
          *((_QWORD *)v6 + 2) = 0;
          *((_QWORD *)v6 + 3) = 15;
          *v6 = 0;
        }
        if ( v23 > 0xF )
        {
          v10 = v22;
          if ( v23 + 1 >= 0x1000 )
          {
            if ( (unsigned __int64)v22 - *((_QWORD *)v22 - 1) - 8 > 0x1F )
LABEL_46:
              __fastfail(5u);
            v10 = (void *)*((_QWORD *)v22 - 1);
          }
          operator delete(v10);
        }
      }
      else
      {
LABEL_21:
        if ( *((_QWORD *)v1 + 2) > 1u )
        {
          v11 = v1;
          if ( v3 > 0xF )
            v11 = *(char **)v1;
          if ( *v11 == 34 )
            goto LABEL_32;
          v12 = v1;
          if ( v3 > 0xF )
            v12 = *(char **)v1;
          if ( *v12 == 39 || (v3 <= 0xF ? (v13 = v1) : (v13 = *(char **)v1), *v13 == 96) )
          {
LABEL_32:
            v14 = v1;
            if ( v3 <= 0xF )
            {
              v15 = v1;
            }
            else
            {
              v15 = *(char **)v1;
              v14 = *(char **)v1;
            }
            v16 = *((_QWORD *)v1 + 2);
            if ( *v14 == v15[v16 - 1] )
            {
              v17 = v1;
              *((_QWORD *)v1 + 2) = v16 - 1;
              if ( v3 > 0xF )
                v17 = *(char **)v1;
              v17[v16 - 1] = 0;
              if ( *((_QWORD *)v1 + 3) > 0xFu )
              {
                v18 = *((_QWORD *)v1 + 2);
                v19 = 1;
                if ( !v18 )
                  v19 = *((_QWORD *)v1 + 2);
                v20 = *(char **)v1;
              }
              else
              {
                v18 = *((_QWORD *)v1 + 2);
                v19 = v18 != 0;
                v20 = v1;
              }
              v21 = v18 - v19;
              memmove_0(v20, &v20[v19], v21 + 1);
              *((_QWORD *)v1 + 2) = v21;
            }
          }
        }
      }
      v1 += 32;
    }
    while ( v1 != v2 );
  }
}

```

## disassembly

```asm
0x14003de60  mov     [rsp+arg_18], rbx
0x14003de65  push    rsi
0x14003de66  sub     rsp, 50h
0x14003de6a  mov     rax, cs:__security_cookie
0x14003de71  xor     rax, rsp
0x14003de74  mov     [rsp+58h+var_18], rax
0x14003de79  mov     rbx, [rcx]
0x14003de7c  mov     rsi, [rcx+8]
0x14003de80  cmp     rbx, rsi
0x14003de83  jz      loc_14003E0BA
0x14003de89  mov     [rsp+58h+arg_8], rbp
0x14003de8e  xor     ebp, ebp
0x14003de90  mov     [rsp+58h+arg_10], rdi
0x14003de95  nop     word ptr [rax+rax+00000000h]
0x14003dea0  mov     rcx, [rbx+18h]
0x14003dea4  mov     rax, rbx
0x14003dea7  cmp     rcx, 0Fh
0x14003deab  jbe     short loc_14003DEB0
0x14003dead  mov     rax, [rbx]
0x14003deb0  cmp     byte ptr [rax], 22h ; '"'
0x14003deb3  jnz     loc_14003DFA2
0x14003deb9  mov     rdx, rbx
0x14003debc  cmp     rcx, 0Fh
0x14003dec0  jbe     short loc_14003DEC5
0x14003dec2  mov     rdx, [rbx]
0x14003dec5  mov     rax, [rbx+10h]
0x14003dec9  cmp     byte ptr [rax+rdx-1], 22h ; '"'
0x14003dece  jnz     loc_14003DFA2
0x14003ded4  mov     rcx, rbx
0x14003ded7  call    ?remove_quotes@detail@CLI@@YAAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAV34@@Z; CLI::detail::remove_quotes(std::string &)
0x14003dedc  mov     rdx, rbx
0x14003dedf  lea     rcx, [rsp+58h+var_38]
0x14003dee4  call    ?remove_escaped_characters@detail@CLI@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV34@@Z; CLI::detail::remove_escaped_characters(std::string const &)
0x14003dee9  mov     rdi, rax
0x14003deec  cmp     rbx, rax
0x14003deef  jz      short loc_14003DF5C
0x14003def1  mov     rdx, [rbx+18h]
0x14003def5  cmp     rdx, 0Fh
0x14003def9  jbe     short loc_14003DF30
0x14003defb  mov     rcx, [rbx]
0x14003defe  inc     rdx; unsigned __int64
0x14003df01  cmp     rdx, 1000h
0x14003df08  jb      short loc_14003DF25
0x14003df0a  mov     rax, [rcx-8]
0x14003df0e  sub     rcx, rax
0x14003df11  sub     rcx, 8
0x14003df15  cmp     rcx, 1Fh
0x14003df19  ja      loc_14003E0D2
0x14003df1f  add     rdx, 27h ; '''
0x14003df23  jmp     short loc_14003DF28
0x14003df25  mov     rax, rcx
0x14003df28  mov     rcx, rax; void *
0x14003df2b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14003df30  mov     [rbx+10h], rbp
0x14003df34  mov     qword ptr [rbx+18h], 0Fh
0x14003df3c  mov     [rbx], bpl
0x14003df3f  movups  xmm0, xmmword ptr [rdi]
0x14003df42  movups  xmmword ptr [rbx], xmm0
0x14003df45  movups  xmm1, xmmword ptr [rdi+10h]
0x14003df49  movups  xmmword ptr [rbx+10h], xmm1
0x14003df4d  mov     [rdi+10h], rbp
0x14003df51  mov     qword ptr [rdi+18h], 0Fh
0x14003df59  mov     [rdi], bpl
0x14003df5c  mov     rdx, [rsp+58h+var_20]
0x14003df61  cmp     rdx, 0Fh
0x14003df65  jbe     loc_14003E0A3
0x14003df6b  mov     rcx, [rsp+58h+var_38]
0x14003df70  inc     rdx
0x14003df73  cmp     rdx, 1000h
0x14003df7a  jb      short loc_14003DF98
0x14003df7c  mov     rax, [rcx-8]
0x14003df80  sub     rcx, rax
0x14003df83  sub     rcx, 8
0x14003df87  cmp     rcx, 1Fh
0x14003df8b  ja      loc_14003E0D2
0x14003df91  add     rdx, 27h ; '''; unsigned __int64
0x14003df95  mov     rcx, rax; void *
0x14003df98  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14003df9d  jmp     loc_14003E0A3
0x14003dfa2  cmp     qword ptr [rbx+10h], 1
0x14003dfa7  jbe     loc_14003E0A3
0x14003dfad  mov     rax, rbx
0x14003dfb0  cmp     rcx, 0Fh
0x14003dfb4  jbe     short loc_14003DFB9
0x14003dfb6  mov     rax, [rbx]
0x14003dfb9  cmp     byte ptr [rax], 22h ; '"'
0x14003dfbc  jz      short loc_14003DFE6
0x14003dfbe  mov     rax, rbx
0x14003dfc1  cmp     rcx, 0Fh
0x14003dfc5  jbe     short loc_14003DFCA
0x14003dfc7  mov     rax, [rbx]
0x14003dfca  cmp     byte ptr [rax], 27h ; '''
0x14003dfcd  jz      short loc_14003DFE6
0x14003dfcf  cmp     rcx, 0Fh
0x14003dfd3  jbe     short loc_14003DFDA
0x14003dfd5  mov     rax, [rbx]
0x14003dfd8  jmp     short loc_14003DFDD
0x14003dfda  mov     rax, rbx
0x14003dfdd  cmp     byte ptr [rax], 60h ; '`'
0x14003dfe0  jnz     loc_14003E0A3
0x14003dfe6  mov     rdx, rbx
0x14003dfe9  cmp     rcx, 0Fh
0x14003dfed  jbe     short loc_14003DFF7
0x14003dfef  mov     rax, [rbx]
0x14003dff2  mov     rdx, rax
0x14003dff5  jmp     short loc_14003DFFA
0x14003dff7  mov     rax, rbx
0x14003dffa  mov     r8, [rbx+10h]
0x14003dffe  movzx   eax, byte ptr [rax+r8-1]
0x14003e004  cmp     [rdx], al
0x14003e006  jnz     loc_14003E0A3
0x14003e00c  lea     rdx, [r8-1]
0x14003e010  mov     rax, rbx
0x14003e013  mov     [rbx+10h], rdx
0x14003e017  cmp     rcx, 0Fh
0x14003e01b  jbe     short loc_14003E020
0x14003e01d  mov     rax, [rbx]
0x14003e020  mov     [rdx+rax], bpl
0x14003e024  mov     rcx, [rbx+18h]
0x14003e028  cmp     rcx, 0Fh
0x14003e02c  jbe     short loc_14003E037
0x14003e02e  mov     rax, [rbx]
0x14003e031  lea     rdx, [rax+1]
0x14003e035  jmp     short loc_14003E040
0x14003e037  lea     rdx, [rbx+1]
0x14003e03b  mov     rax, rbx
0x14003e03e  jbe     short loc_14003E05F
0x14003e040  mov     rdi, [rbx+10h]
0x14003e044  sub     rdx, rax
0x14003e047  mov     r9, rax
0x14003e04a  mov     rax, rdi
0x14003e04d  sub     r9, [rbx]
0x14003e050  sub     rax, r9
0x14003e053  cmp     rax, rdx
0x14003e056  cmovb   rdx, rax
0x14003e05a  mov     rax, [rbx]
0x14003e05d  jmp     short loc_14003E087
0x14003e05f  mov     rdi, [rbx+10h]
0x14003e063  sub     rdx, rax
0x14003e066  mov     r9, rax
0x14003e069  mov     rax, rdi
0x14003e06c  sub     r9, rbx
0x14003e06f  sub     rax, r9
0x14003e072  cmp     rax, rdx
0x14003e075  cmovb   rdx, rax
0x14003e079  cmp     rcx, 0Fh
0x14003e07d  jbe     short loc_14003E084
0x14003e07f  mov     rax, [rbx]
0x14003e082  jmp     short loc_14003E087
0x14003e084  mov     rax, rbx
0x14003e087  sub     rdi, rdx
0x14003e08a  lea     rcx, [r9+rax]; void *
0x14003e08e  mov     r8, rdi
0x14003e091  add     rdx, rcx; Src
0x14003e094  sub     r8, r9
0x14003e097  inc     r8; Size
0x14003e09a  call    memmove_0
0x14003e09f  mov     [rbx+10h], rdi
0x14003e0a3  add     rbx, 20h ; ' '
0x14003e0a7  cmp     rbx, rsi
0x14003e0aa  jnz     loc_14003DEA0
0x14003e0b0  mov     rdi, [rsp+58h+arg_10]
0x14003e0b5  mov     rbp, [rsp+58h+arg_8]
0x14003e0ba  mov     rcx, [rsp+58h+var_18]
0x14003e0bf  xor     rcx, rsp; StackCookie
0x14003e0c2  call    __security_check_cookie
0x14003e0c7  mov     rbx, [rsp+58h+arg_18]
0x14003e0cc  add     rsp, 50h
0x14003e0d0  pop     rsi
0x14003e0d1  retn
0x14003e0d2  mov     ecx, 5
0x14003e0d7  int     29h; Win8: RtlFailFast(ecx)
```
