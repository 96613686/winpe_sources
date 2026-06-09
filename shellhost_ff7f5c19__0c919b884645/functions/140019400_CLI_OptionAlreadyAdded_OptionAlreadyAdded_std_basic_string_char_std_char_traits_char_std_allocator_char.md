# CLI::OptionAlreadyAdded::OptionAlreadyAdded(std::basic_string<char,std::char_traits<char>,std::allocator<char>>)

- ea: `0x140019400`
- end: `0x140019592`
- name: `??0OptionAlreadyAdded@CLI@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z`
- size: `402`
- prototype: ``
- caller_count: `4`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x140013d40`
- `0x1400280c0`
- `0x140028cd0`
- `0x1400355b0`

## callees

- `0x1400083f0`
- `0x14000ba3c`
- `0x14000f7e0`
- `0x14000f804`
- `0x14000fab8`
- `0x1400174e0`
- `0x140019400`
- `0x14004aaac`

## string_xrefs

- `0x1400194e6`: `OptionAlreadyAdded`
- `0x140019465`: ` is already added`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_QWORD *__fastcall CLI::OptionAlreadyAdded::OptionAlreadyAdded(_QWORD *a1, _QWORD *a2)
{
  __int64 v4; // rcx
  _QWORD *v5; // r9
  unsigned __int64 v6; // rdx
  void *v7; // rcx
  unsigned __int8 v9; // [rsp+40h] [rbp-49h]
  void *v10[2]; // [rsp+50h] [rbp-39h] BYREF
  __int128 v11; // [rsp+60h] [rbp-29h]
  __int128 v12; // [rsp+70h] [rbp-19h] BYREF
  __int64 v13; // [rsp+80h] [rbp-9h]
  __int64 v14; // [rsp+88h] [rbp-1h]
  _OWORD *v15; // [rsp+90h] [rbp+7h]
  _OWORD v16[2]; // [rsp+A0h] [rbp+17h] BYREF
  _QWORD *v17; // [rsp+C0h] [rbp+37h]

  v17 = a2;
  v4 = a2[2];
  if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFFLL - v4) < 0x11 )
    std::_Xlen_string();
  if ( a2[3] <= 0xFu )
    v5 = a2;
  else
    v5 = (_QWORD *)*a2;
  std::string::string(v10, v9, a2, v5, v4, " is already added", 17);
  v15 = v16;
  v16[0] = *(_OWORD *)v10;
  v16[1] = v11;
  *(_QWORD *)&v11 = 0;
  *((_QWORD *)&v11 + 1) = 15;
  LOBYTE(v10[0]) = 0;
  v12 = 0;
  v13 = 0;
  v14 = 0;
  *(_QWORD *)&v12 = operator new(0x20u);
  v13 = 18;
  v14 = 31;
  strcpy((char *)v12, "OptionAlreadyAdded");
  CLI::ConstructionError::ConstructionError(a1, &v12, v16, 102);
  *a1 = &CLI::OptionAlreadyAdded::`vftable';
  if ( *((_QWORD *)&v11 + 1) > 0xFu )
  {
    v6 = *((_QWORD *)&v11 + 1) + 1LL;
    if ( (unsigned __int64)(*((_QWORD *)&v11 + 1) + 1LL) < 0x1000 )
    {
      v7 = v10[0];
    }
    else
    {
      v7 = (void *)*((_QWORD *)v10[0] - 1);
      if ( (unsigned __int64)((char *)v10[0] - (char *)v7 - 8) > 0x1F )
        __fastfail(5u);
      v6 = *((_QWORD *)&v11 + 1) + 40LL;
    }
    operator delete(v7, v6);
  }
  *a1 = &CLI::OptionAlreadyAdded::`vftable';
  std::string::_Tidy_deallocate(a2);
  return a1;
}

```

## disassembly

```asm
0x140019400  mov     [rsp-8+arg_10], rbx
0x140019405  push    rbp
0x140019406  push    rsi
0x140019407  push    rdi
0x140019408  lea     rbp, [rsp-47h]
0x14001940d  sub     rsp, 0D0h
0x140019414  mov     rax, cs:__security_cookie
0x14001941b  xor     rax, rsp
0x14001941e  mov     [rbp+57h+var_18], rax
0x140019422  mov     rbx, rdx
0x140019425  mov     rdi, rcx
0x140019428  mov     [rbp+57h+var_98], rcx
0x14001942c  mov     [rbp+57h+var_20], rdx
0x140019430  xor     esi, esi
0x140019432  mov     rcx, [rdx+10h]
0x140019436  mov     rax, 7FFFFFFFFFFFFFFFh
0x140019440  sub     rax, rcx
0x140019443  cmp     rax, 11h
0x140019447  jb      loc_14001958C
0x14001944d  cmp     qword ptr [rdx+18h], 0Fh
0x140019452  jbe     short loc_140019459
0x140019454  mov     r9, [rdx]
0x140019457  jmp     short loc_14001945C
0x140019459  mov     r9, rbx
0x14001945c  mov     [rsp+0E0h+var_B0], 11h
0x140019465  lea     rax, aIsAlreadyAdded; " is already added"
0x14001946c  mov     [rsp+0E0h+var_B8], rax
0x140019471  mov     [rsp+0E0h+var_C0], rcx
0x140019476  mov     r8, rbx
0x140019479  movzx   edx, [rbp+57h+var_A0]
0x14001947d  lea     rcx, [rbp+57h+var_90]
0x140019481  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBD_K23@Z; std::string::string(std::_String_constructor_concat_tag,std::string const &,char const * const,unsigned __int64,char const * const,unsigned __int64)
0x140019486  lea     rax, [rbp+57h+var_90]
0x14001948a  mov     [rbp+57h+var_98], rax
0x14001948e  lea     rax, [rbp+57h+var_40]
0x140019492  mov     [rbp+57h+var_50], rax
0x140019496  movups  xmm0, xmmword ptr [rbp+57h+var_90]
0x14001949a  movups  [rbp+57h+var_40], xmm0
0x14001949e  movups  xmm1, [rbp+57h+var_80]
0x1400194a2  movups  [rbp+57h+var_30], xmm1
0x1400194a6  mov     qword ptr [rbp+57h+var_80], rsi
0x1400194aa  mov     qword ptr [rbp+57h+var_80+8], 0Fh
0x1400194b2  mov     byte ptr [rbp+57h+var_90], 0
0x1400194b6  xorps   xmm0, xmm0
0x1400194b9  movups  [rbp+57h+var_70], xmm0
0x1400194bd  mov     [rbp+57h+var_60], rsi
0x1400194c1  mov     [rbp+57h+var_58], rsi
0x1400194c5  mov     ecx, 20h ; ' '; Size
0x1400194ca  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400194cf  mov     rcx, rax
0x1400194d2  mov     qword ptr [rbp+57h+var_70], rax
0x1400194d6  mov     [rbp+57h+var_60], 12h
0x1400194de  mov     [rbp+57h+var_58], 1Fh
0x1400194e6  movups  xmm0, xmmword ptr cs:aOptionalreadya; "OptionAlreadyAdded"
0x1400194ed  movups  xmmword ptr [rax], xmm0
0x1400194f0  movzx   eax, word ptr cs:aOptionalreadya+10h; "ed"
0x1400194f7  mov     [rcx+10h], ax
0x1400194fb  mov     byte ptr [rcx+12h], 0
0x1400194ff  mov     r9d, 66h ; 'f'
0x140019505  lea     r8, [rbp+57h+var_40]
0x140019509  lea     rdx, [rbp+57h+var_70]
0x14001950d  mov     rcx, rdi
0x140019510  call    ??0ConstructionError@CLI@@IEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@0W4ExitCodes@1@@Z; CLI::ConstructionError::ConstructionError(std::string,std::string,CLI::ExitCodes)
0x140019515  lea     rsi, ??_7OptionAlreadyAdded@CLI@@6B@; const CLI::OptionAlreadyAdded::`vftable'
0x14001951c  mov     [rdi], rsi
0x14001951f  mov     rdx, qword ptr [rbp+57h+var_80+8]
0x140019523  cmp     rdx, 0Fh
0x140019527  jbe     short loc_14001955F
0x140019529  mov     rax, [rbp+57h+var_90]
0x14001952d  inc     rdx; unsigned __int64
0x140019530  cmp     rdx, 1000h
0x140019537  jb      short loc_140019557
0x140019539  mov     rcx, [rax-8]
0x14001953d  sub     rax, rcx
0x140019540  sub     rax, 8
0x140019544  cmp     rax, 1Fh
0x140019548  ja      short loc_140019550
0x14001954a  add     rdx, 27h ; '''
0x14001954e  jmp     short loc_14001955A
0x140019550  mov     ecx, 5
0x140019555  int     29h; Win8: RtlFailFast(ecx)
0x140019557  mov     rcx, rax; void *
0x14001955a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14001955f  mov     [rdi], rsi
0x140019562  mov     rcx, rbx; void *
0x140019565  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x14001956a  mov     rax, rdi
0x14001956d  mov     rcx, [rbp+57h+var_18]
0x140019571  xor     rcx, rsp; StackCookie
0x140019574  call    __security_check_cookie
0x140019579  mov     rbx, [rsp+0E0h+arg_10]
0x140019581  add     rsp, 0D0h
0x140019588  pop     rdi
0x140019589  pop     rsi
0x14001958a  pop     rbp
0x14001958b  retn
0x14001958c  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
```
