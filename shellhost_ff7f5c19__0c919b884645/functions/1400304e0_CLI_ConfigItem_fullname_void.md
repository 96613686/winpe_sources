# CLI::ConfigItem::fullname(void)

- ea: `0x1400304e0`
- end: `0x140030716`
- name: `?fullname@ConfigItem@CLI@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ`
- size: `566`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `file_ops, registry_config`

## callers

- `0x140022ef0`
- `0x140023ac0`
- `0x140043c40`

## callees

- `0x140008a50`
- `0x14000f804`
- `0x14000fab8`
- `0x140012110`
- `0x1400304e0`
- `0x14004a9e0`
- `0x14005063c`
- `0x14005d2e0`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CLI::ConfigItem::fullname(__int64 *a1, __int64 a2, __int64 a3)
{
  char *v5; // rax
  unsigned __int64 v6; // rdi
  size_t v7; // rdi
  char *v8; // rbx
  void *v9; // rax
  __int64 v10; // rsi
  __int64 v11; // rdi
  char **v12; // rbx
  char **v13; // rdi
  unsigned __int64 v14; // rdx
  char *v15; // rax
  char *v16; // rcx
  char **v17; // rcx
  void *v19[2]; // [rsp+28h] [rbp-38h] BYREF
  char *v20; // [rsp+38h] [rbp-28h]
  __int128 v21; // [rsp+40h] [rbp-20h] BYREF
  __int64 v22; // [rsp+50h] [rbp-10h]
  __int64 v23; // [rsp+58h] [rbp-8h]

  *(_OWORD *)v19 = 0;
  v5 = 0;
  v20 = 0;
  v6 = (a1[1] - *a1) >> 5;
  if ( v6 )
  {
    if ( v6 > 0x7FFFFFFFFFFFFFFLL )
      std::vector<void *>::_Xlength(a1, a2, a3);
    v7 = 32 * v6;
    if ( v7 )
    {
      if ( v7 < 0x1000 )
      {
        v8 = (char *)operator new(v7);
      }
      else
      {
        if ( v7 + 39 < v7 )
          std::_Throw_bad_array_new_length();
        v9 = operator new(v7 + 39);
        if ( !v9 )
LABEL_30:
          __fastfail(5u);
        v8 = (char *)(((unsigned __int64)v9 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
        *((_QWORD *)v8 - 1) = v9;
      }
    }
    else
    {
      v8 = 0;
    }
    v19[0] = v8;
    v19[1] = v8;
    v5 = &v8[v7];
    v20 = &v8[v7];
    v10 = a1[1];
    v11 = *a1;
    *(_QWORD *)&v21 = v8;
    *((_QWORD *)&v21 + 1) = v8;
    v22 = (__int64)v19;
    if ( v11 != v10 )
    {
      do
      {
        std::string::string(v8, v11);
        v8 += 32;
        *((_QWORD *)&v21 + 1) = v8;
        v11 += 32;
      }
      while ( v11 != v10 );
      v5 = v20;
    }
    v19[1] = v8;
  }
  else
  {
    v8 = (char *)v19[1];
  }
  if ( v8 == v5 )
  {
    std::vector<std::string>::_Emplace_reallocate<std::string const &>(v19, v8, a1 + 3);
  }
  else
  {
    std::string::string(v8, a1 + 3);
    v19[1] = (char *)v19[1] + 32;
  }
  v21 = 0;
  v22 = 1;
  v23 = 15;
  LOWORD(v21) = (unsigned __int8)asc_14006CC78[0];
  CLI::detail::join<std::vector<std::string>>(a2, v19, &v21);
  v12 = (char **)v19[0];
  if ( v19[0] )
  {
    v13 = (char **)v19[1];
    if ( v19[0] != v19[1] )
    {
      do
      {
        v14 = (unsigned __int64)v12[3];
        if ( v14 > 0xF )
        {
          v15 = *v12;
          if ( v14 + 1 < 0x1000 )
          {
            v16 = *v12;
          }
          else
          {
            v16 = (char *)*((_QWORD *)v15 - 1);
            if ( (unsigned __int64)(v15 - v16 - 8) > 0x1F )
              goto LABEL_30;
          }
          operator delete(v16);
        }
        v12[2] = 0;
        v12[3] = (char *)15;
        *(_BYTE *)v12 = 0;
        v12 += 4;
      }
      while ( v12 != v13 );
      v12 = (char **)v19[0];
    }
    if ( ((v20 - (char *)v12) & 0xFFFFFFFFFFFFFFE0uLL) < 0x1000 )
    {
      v17 = v12;
    }
    else
    {
      v17 = (char **)*(v12 - 1);
      if ( (unsigned __int64)((char *)v12 - (char *)v17 - 8) > 0x1F )
        goto LABEL_30;
    }
    operator delete(v17);
  }
  return a2;
}

```

## disassembly

```asm
0x1400304e0  mov     [rsp-28h+arg_8], rbx
0x1400304e5  mov     [rsp-28h+arg_10], rsi
0x1400304ea  push    rbp
0x1400304eb  push    rdi
0x1400304ec  push    r12
0x1400304ee  push    r14
0x1400304f0  push    r15
0x1400304f2  mov     rbp, rsp
0x1400304f5  sub     rsp, 60h
0x1400304f9  mov     r15, rdx
0x1400304fc  mov     r14, rcx
0x1400304ff  xor     r12d, r12d
0x140030502  xorps   xmm0, xmm0
0x140030505  movdqu  xmmword ptr [rbp+var_38], xmm0
0x14003050a  mov     eax, r12d
0x14003050d  mov     [rbp+var_28], rax
0x140030511  mov     rdi, [rcx+8]
0x140030515  sub     rdi, [rcx]
0x140030518  sar     rdi, 5
0x14003051c  test    rdi, rdi
0x14003051f  jz      loc_1400305E6
0x140030525  mov     rax, 7FFFFFFFFFFFFFFh
0x14003052f  cmp     rdi, rax
0x140030532  ja      loc_140030710
0x140030538  shl     rdi, 5
0x14003053c  test    rdi, rdi
0x14003053f  jnz     short loc_140030546
0x140030541  mov     ebx, r12d
0x140030544  jmp     short loc_140030583
0x140030546  cmp     rdi, 1000h
0x14003054d  jb      short loc_140030578
0x14003054f  lea     rcx, [rdi+27h]; Size
0x140030553  cmp     rcx, rdi
0x140030556  jbe     loc_14003070A
0x14003055c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140030561  test    rax, rax
0x140030564  jz      loc_1400306DF
0x14003056a  lea     rbx, [rax+27h]
0x14003056e  and     rbx, 0FFFFFFFFFFFFFFE0h
0x140030572  mov     [rbx-8], rax
0x140030576  jmp     short loc_140030583
0x140030578  mov     rcx, rdi; Size
0x14003057b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140030580  mov     rbx, rax
0x140030583  mov     [rbp+var_38], rbx
0x140030587  mov     [rbp+var_38+8], rbx
0x14003058b  lea     rax, [rbx+rdi]
0x14003058f  mov     [rbp+var_28], rax
0x140030593  lea     rcx, [rbp+var_38]
0x140030597  mov     [rbp+arg_0], rcx
0x14003059b  mov     rsi, [r14+8]
0x14003059f  mov     rdi, [r14]
0x1400305a2  mov     qword ptr [rbp+var_20], rbx
0x1400305a6  mov     qword ptr [rbp+var_20+8], rbx
0x1400305aa  lea     rcx, [rbp+var_38]
0x1400305ae  mov     [rbp+var_10], rcx
0x1400305b2  cmp     rdi, rsi
0x1400305b5  jz      short loc_1400305E0
0x1400305b7  nop     word ptr [rax+rax+00000000h]
0x1400305c0  mov     rdx, rdi
0x1400305c3  mov     rcx, rbx
0x1400305c6  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@AEBV01@@Z; std::string::string(std::string const &)
0x1400305cb  add     rbx, 20h ; ' '
0x1400305cf  mov     qword ptr [rbp+var_20+8], rbx
0x1400305d3  add     rdi, 20h ; ' '
0x1400305d7  cmp     rdi, rsi
0x1400305da  jnz     short loc_1400305C0
0x1400305dc  mov     rax, [rbp+var_28]
0x1400305e0  mov     [rbp+var_38+8], rbx
0x1400305e4  jmp     short loc_1400305EA
0x1400305e6  mov     rbx, [rbp+var_38+8]
0x1400305ea  lea     r8, [r14+18h]
0x1400305ee  cmp     rbx, rax
0x1400305f1  jz      short loc_140030605
0x1400305f3  mov     rdx, r8
0x1400305f6  mov     rcx, rbx
0x1400305f9  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@AEBV01@@Z; std::string::string(std::string const &)
0x1400305fe  add     [rbp+var_38+8], 20h ; ' '
0x140030603  jmp     short loc_140030611
0x140030605  mov     rdx, rbx
0x140030608  lea     rcx, [rbp+var_38]
0x14003060c  call    ??$_Emplace_reallocate@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@?$vector@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@std@@AEAAPEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@QEAV21@AEBV21@@Z; std::vector<std::string>::_Emplace_reallocate<std::string const &>(std::string * const,std::string const &)
0x140030611  xorps   xmm0, xmm0
0x140030614  movups  [rbp+var_20], xmm0
0x140030618  mov     [rbp+var_10], 1
0x140030620  mov     [rbp+var_8], 0Fh
0x140030628  movzx   eax, word ptr cs:asc_14006CC78; "."
0x14003062f  mov     byte ptr [rbp+var_20], al
0x140030632  mov     byte ptr [rbp+var_20+1], 0
0x140030636  lea     r8, [rbp+var_20]
0x14003063a  lea     rdx, [rbp+var_38]
0x14003063e  mov     rcx, r15
0x140030641  call    ??$join@V?$vector@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@std@@@detail@CLI@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$vector@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@3@V23@@Z; CLI::detail::join<std::vector<std::string>>(std::vector<std::string> const &,std::string)
0x140030646  nop
0x140030647  mov     rbx, [rbp+var_38]
0x14003064b  test    rbx, rbx
0x14003064e  jz      loc_1400306EE
0x140030654  mov     rdi, [rbp+var_38+8]
0x140030658  cmp     rbx, rdi
0x14003065b  jz      short loc_1400306B4
0x14003065d  nop     dword ptr [rax]
0x140030660  mov     rdx, [rbx+18h]
0x140030664  cmp     rdx, 0Fh
0x140030668  jbe     short loc_140030698
0x14003066a  mov     rax, [rbx]
0x14003066d  inc     rdx; unsigned __int64
0x140030670  cmp     rdx, 1000h
0x140030677  jb      short loc_140030690
0x140030679  mov     rcx, [rax-8]
0x14003067d  sub     rax, rcx
0x140030680  sub     rax, 8
0x140030684  cmp     rax, 1Fh
0x140030688  ja      short loc_1400306DF
0x14003068a  add     rdx, 27h ; '''
0x14003068e  jmp     short loc_140030693
0x140030690  mov     rcx, rax; void *
0x140030693  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140030698  mov     [rbx+10h], r12
0x14003069c  mov     qword ptr [rbx+18h], 0Fh
0x1400306a4  mov     byte ptr [rbx], 0
0x1400306a7  add     rbx, 20h ; ' '
0x1400306ab  cmp     rbx, rdi
0x1400306ae  jnz     short loc_140030660
0x1400306b0  mov     rbx, [rbp+var_38]
0x1400306b4  mov     rdx, [rbp+var_28]
0x1400306b8  sub     rdx, rbx
0x1400306bb  and     rdx, 0FFFFFFFFFFFFFFE0h; unsigned __int64
0x1400306bf  cmp     rdx, 1000h
0x1400306c6  jb      short loc_1400306E6
0x1400306c8  mov     rcx, [rbx-8]
0x1400306cc  sub     rbx, rcx
0x1400306cf  sub     rbx, 8
0x1400306d3  cmp     rbx, 1Fh
0x1400306d7  ja      short loc_1400306DF
0x1400306d9  add     rdx, 27h ; '''
0x1400306dd  jmp     short loc_1400306E9
0x1400306df  mov     ecx, 5
0x1400306e4  int     29h; Win8: RtlFailFast(ecx)
0x1400306e6  mov     rcx, rbx; void *
0x1400306e9  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400306ee  mov     rax, r15
0x1400306f1  lea     r11, [rsp+60h+var_s0]
0x1400306f6  mov     rbx, [r11+38h]
0x1400306fa  mov     rsi, [r11+40h]
0x1400306fe  mov     rsp, r11
0x140030701  pop     r15
0x140030703  pop     r14
0x140030705  pop     r12
0x140030707  pop     rdi
0x140030708  pop     rbp
0x140030709  retn
0x14003070a  call    ?_Throw_bad_array_new_length@std@@YAXXZ; std::_Throw_bad_array_new_length(void)
0x140030710  call    ?_Xlength@?$vector@PEAXV?$allocator@PEAX@std@@@std@@CAXXZ; std::vector<void *>::_Xlength(void)
```
