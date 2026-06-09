# CLI::App::add_subcommand(std::basic_string<char,std::char_traits<char>,std::allocator<char>>,std::basic_string<char,std::char_traits<char>,std::allocator<char>>)

- ea: `0x140028cd0`
- end: `0x1400290b9`
- name: `?add_subcommand@App@CLI@@QEAAPEAV12@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@0@Z`
- size: `1001`
- prototype: `__int64 __fastcall(CLI::App *this, void *, void *)`
- caller_count: `1`
- callee_count: `17`
- tags: `broker_com_uri`

## callers

- `0x140058bec`

## callees

- `0x1400083f0`
- `0x140008810`
- `0x1400088d0`
- `0x140008a50`
- `0x14000f7e0`
- `0x14000f804`
- `0x140010668`
- `0x140010db0`
- `0x140012590`
- `0x1400162d0`
- `0x140018a40`
- `0x140019400`
- `0x140020a80`
- `0x1400211c0`
- `0x140028cd0`
- `0x140044efc`
- `0x140067010`

## string_xrefs

- `0x14002905e`: `Subcommand name starts with invalid character, '!' and '-' and control characters`
- `0x14002900b`: `Subcommand name contains invalid character ('`
- `0x140028fde`: `subcommand name or alias matches existing subcommand: `

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CLI::App::add_subcommand(CLI::App *this, _QWORD *a2, _OWORD *a3)
{
  __int64 v6; // r9
  _BYTE *v7; // rax
  unsigned __int64 v8; // r8
  _QWORD *v9; // rax
  char *v10; // rcx
  char *v11; // rax
  unsigned __int8 v12; // dl
  CLI::App *v13; // rbx
  __int64 v14; // rbx
  _BYTE *v15; // rax
  unsigned __int8 *v16; // rdx
  _QWORD *v17; // rcx
  unsigned __int8 *v18; // rax
  unsigned __int8 *v19; // rcx
  unsigned __int8 v20; // bl
  _DWORD *v21; // rax
  struct CLI::App *fallthrough_parent; // rax
  __int64 v23; // rax
  _QWORD *v24; // rdx
  __int64 v25; // r14
  volatile signed __int32 *v26; // rbx
  __int64 v28; // rax
  __int64 v29; // rax
  __int64 v30; // rax
  __int64 v31; // rax
  __int64 v32; // rax
  __int64 v33; // rax
  _OWORD v34[2]; // [rsp+30h] [rbp-89h] BYREF
  _QWORD *v35; // [rsp+50h] [rbp-69h]
  _OWORD *v36; // [rsp+58h] [rbp-61h]
  _OWORD v37[2]; // [rsp+60h] [rbp-59h] BYREF
  _BYTE v38[32]; // [rsp+80h] [rbp-39h] BYREF
  _BYTE pExceptionObject[64]; // [rsp+A0h] [rbp-19h] BYREF

  v35 = a2;
  v36 = a3;
  v6 = a2[2];
  if ( !v6 )
    goto LABEL_16;
  v7 = a2;
  v8 = a2[3];
  if ( v8 > 0xF )
    v7 = (_BYTE *)*a2;
  if ( *v7 != 45 && *v7 > 0x21u )
  {
    if ( v8 <= 0xF )
    {
      v10 = (char *)a2 + v6;
      v9 = a2;
    }
    else
    {
      v9 = (_QWORD *)*a2;
      v10 = (char *)(v6 + *a2);
    }
    v11 = (char *)v9 + 1;
    if ( v11 == v10 )
      goto LABEL_16;
    while ( 1 )
    {
      v12 = *v11;
      if ( *v11 == 61 || v12 == 58 || v12 == 123 || v12 <= 0x20u && v12 != 9 )
        break;
      if ( ++v11 == v10 )
        goto LABEL_16;
    }
  }
  v15 = a2;
  if ( v8 > 0xF )
    v15 = (_BYTE *)*a2;
  if ( *v15 == 45 || *v15 <= 0x21u )
  {
    v32 = std::string::string(v34, "Subcommand name starts with invalid character, '!' and '-' and control characters");
    CLI::IncorrectConstruction::IncorrectConstruction(pExceptionObject, v32);
    throw (CLI::IncorrectConstruction *)pExceptionObject;
  }
  if ( v8 <= 0xF )
  {
    v17 = a2;
    v16 = (unsigned __int8 *)a2;
    v18 = (unsigned __int8 *)a2;
  }
  else
  {
    v16 = (unsigned __int8 *)*a2;
    v17 = (_QWORD *)*a2;
    v18 = (unsigned __int8 *)*a2;
  }
  v19 = (unsigned __int8 *)v17 + v6;
  if ( v16 != v19 )
  {
    do
    {
      v20 = *v18;
      if ( *v18 == 61 || v20 == 58 || v20 == 123 || v20 <= 0x20u && v20 != 9 )
      {
        v29 = std::string::string(v38, "Subcommand name contains invalid character ('");
        v30 = std::operator+<char>(v37, v29, v20);
        v31 = std::operator+<char>(
                v34,
                v30,
                "'), all characters are allowed except'=',':','{','}', ' ', and control characters");
        CLI::IncorrectConstruction::IncorrectConstruction(pExceptionObject, v31);
        throw (CLI::IncorrectConstruction *)pExceptionObject;
      }
      ++v18;
    }
    while ( v18 != v19 );
  }
LABEL_16:
  v13 = (CLI::App *)operator new(0x3D0u);
  if ( v13 )
  {
    std::string::string(v37, a2);
    v34[0] = *a3;
    v34[1] = a3[1];
    *((_QWORD *)a3 + 2) = 0;
    *((_QWORD *)a3 + 3) = 15;
    *(_BYTE *)a3 = 0;
    v14 = CLI::App::App(v13);
  }
  else
  {
    v14 = 0;
  }
  v21 = operator new(0x18u);
  if ( v21 )
  {
    *(_OWORD *)v21 = 0;
    v21[2] = 1;
    v21[3] = 1;
    *(_QWORD *)v21 = &std::_Ref_count<CLI::App>::`vftable';
    *((_QWORD *)v21 + 2) = v14;
  }
  else
  {
    v21 = 0;
  }
  *(_QWORD *)&v37[0] = v14;
  *((_QWORD *)&v37[0] + 1) = v21;
  v34[0] = 0;
  if ( !v14 )
  {
    v33 = std::string::string(v38, "passed App is not valid");
    CLI::IncorrectConstruction::IncorrectConstruction(pExceptionObject, v33);
    throw (CLI::IncorrectConstruction *)pExceptionObject;
  }
  if ( *((_QWORD *)this + 3) || !*((_QWORD *)this + 105) )
  {
    fallthrough_parent = this;
  }
  else
  {
    fallthrough_parent = CLI::App::_get_fallthrough_parent(this);
    v14 = *(_QWORD *)&v37[0];
  }
  v23 = CLI::App::_compare_subcommand_names(this, v14, fallthrough_parent);
  if ( *(_QWORD *)(v23 + 16) )
  {
    v28 = std::operator+<char>(v38, "subcommand name or alias matches existing subcommand: ", v23);
    CLI::OptionAlreadyAdded::OptionAlreadyAdded(pExceptionObject, v28);
    throw (CLI::OptionAlreadyAdded *)pExceptionObject;
  }
  *(_QWORD *)(*(_QWORD *)&v37[0] + 840LL) = this;
  v24 = (_QWORD *)*((_QWORD *)this + 97);
  if ( v24 == *((_QWORD **)this + 98) )
  {
    std::vector<std::shared_ptr<CLI::App>>::_Emplace_reallocate<std::shared_ptr<CLI::App>>((char *)this + 768, v24, v37);
  }
  else
  {
    *v24 = 0;
    v24[1] = 0;
    *(_OWORD *)v24 = v37[0];
    v37[0] = 0;
    *((_QWORD *)this + 97) += 16LL;
  }
  v25 = *(_QWORD *)(*((_QWORD *)this + 97) - 16LL);
  v26 = (volatile signed __int32 *)*((_QWORD *)&v37[0] + 1);
  if ( *((_QWORD *)&v37[0] + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v37[0] + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v26)(v26);
      if ( _InterlockedExchangeAdd(v26 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v26 + 8LL))(v26);
    }
  }
  std::string::_Tidy_deallocate(a2);
  std::string::_Tidy_deallocate(a3);
  return v25;
}

```

## disassembly

```asm
0x140028cd0  mov     [rsp-8+arg_18], rbx
0x140028cd5  push    rbp
0x140028cd6  push    rsi
0x140028cd7  push    rdi
0x140028cd8  push    r14
0x140028cda  push    r15
0x140028cdc  lea     rbp, [rsp-37h]
0x140028ce1  sub     rsp, 0F0h
0x140028ce8  mov     rax, cs:__security_cookie
0x140028cef  xor     rax, rsp
0x140028cf2  mov     [rbp+57h+var_30], rax
0x140028cf6  mov     r15, r8
0x140028cf9  mov     rdi, rdx
0x140028cfc  mov     rsi, rcx
0x140028cff  mov     [rbp+57h+var_C0], rdx
0x140028d03  mov     [rbp+57h+var_B8], r8
0x140028d07  mov     r9, [rdx+10h]
0x140028d0b  test    r9, r9
0x140028d0e  jz      short loc_140028D7B
0x140028d10  mov     rax, rdx
0x140028d13  mov     r8, [rdx+18h]
0x140028d17  cmp     r8, 0Fh
0x140028d1b  jbe     short loc_140028D20
0x140028d1d  mov     rax, [rdx]
0x140028d20  movzx   ecx, byte ptr [rax]
0x140028d23  cmp     cl, 2Dh ; '-'
0x140028d26  jz      loc_140028DE1
0x140028d2c  cmp     cl, 21h ; '!'
0x140028d2f  jbe     loc_140028DE1
0x140028d35  cmp     r8, 0Fh
0x140028d39  jbe     short loc_140028D44
0x140028d3b  mov     rax, [rdx]
0x140028d3e  lea     rcx, [r9+rax]
0x140028d42  jmp     short loc_140028D4B
0x140028d44  lea     rcx, [rdx+r9]
0x140028d48  mov     rax, rdi
0x140028d4b  inc     rax
0x140028d4e  cmp     rax, rcx
0x140028d51  jz      short loc_140028D7B
0x140028d53  movzx   edx, byte ptr [rax]
0x140028d56  cmp     dl, 3Dh ; '='
0x140028d59  jz      loc_140028DE1
0x140028d5f  cmp     dl, 3Ah ; ':'
0x140028d62  jz      short loc_140028DE1
0x140028d64  cmp     dl, 7Bh ; '{'
0x140028d67  jz      short loc_140028DE1
0x140028d69  cmp     dl, 20h ; ' '
0x140028d6c  ja      short loc_140028D73
0x140028d6e  cmp     dl, 9
0x140028d71  jnz     short loc_140028DE1
0x140028d73  inc     rax
0x140028d76  cmp     rax, rcx
0x140028d79  jnz     short loc_140028D53
0x140028d7b  mov     ecx, 3D0h; Size
0x140028d80  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140028d85  mov     rbx, rax
0x140028d88  mov     [rsp+110h+var_E8], rax
0x140028d8d  test    rax, rax
0x140028d90  jz      loc_140028E69
0x140028d96  mov     rdx, rdi
0x140028d99  lea     rcx, [rbp+57h+var_B0]
0x140028d9d  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@AEBV01@@Z; std::string::string(std::string const &)
0x140028da2  movups  xmm0, xmmword ptr [r15]
0x140028da6  movups  [rsp+110h+var_E0], xmm0
0x140028dab  movups  xmm1, xmmword ptr [r15+10h]
0x140028db0  movups  [rbp+57h+var_D0], xmm1
0x140028db4  xor     r14d, r14d
0x140028db7  mov     [r15+10h], r14
0x140028dbb  mov     qword ptr [r15+18h], 0Fh
0x140028dc3  mov     [r15], r14b
0x140028dc6  mov     r9, rsi
0x140028dc9  mov     r8, rax
0x140028dcc  lea     rdx, [rsp+110h+var_E0]
0x140028dd1  mov     rcx, rbx; this
0x140028dd4  call    ??0App@CLI@@IEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@0PEAV01@@Z; CLI::App::App(std::string,std::string,CLI::App *)
0x140028dd9  mov     rbx, rax
0x140028ddc  jmp     loc_140028E6F
0x140028de1  mov     rax, rdi
0x140028de4  cmp     r8, 0Fh
0x140028de8  jbe     short loc_140028DED
0x140028dea  mov     rax, [rdi]
0x140028ded  movzx   ecx, byte ptr [rax]
0x140028df0  cmp     cl, 2Dh ; '-'
0x140028df3  jz      loc_14002905E
0x140028df9  cmp     cl, 21h ; '!'
0x140028dfc  jbe     loc_14002905E
0x140028e02  cmp     r8, 0Fh
0x140028e06  jbe     short loc_140028E13
0x140028e08  mov     rdx, [rdi]
0x140028e0b  mov     rcx, rdx
0x140028e0e  mov     rax, rdx
0x140028e11  jmp     short loc_140028E1C
0x140028e13  mov     rcx, rdi
0x140028e16  mov     rdx, rdi
0x140028e19  mov     rax, rdi
0x140028e1c  add     rcx, r9
0x140028e1f  cmp     rdx, rcx
0x140028e22  jz      loc_140028D7B
0x140028e28  nop     dword ptr [rax+rax+00000000h]
0x140028e30  movzx   ebx, byte ptr [rax]
0x140028e33  cmp     bl, 3Dh ; '='
0x140028e36  jz      loc_14002900B
0x140028e3c  cmp     bl, 3Ah ; ':'
0x140028e3f  jz      loc_14002900B
0x140028e45  cmp     bl, 7Bh ; '{'
0x140028e48  jz      loc_14002900B
0x140028e4e  cmp     bl, 20h ; ' '
0x140028e51  ja      short loc_140028E5C
0x140028e53  cmp     bl, 9
0x140028e56  jnz     loc_14002900B
0x140028e5c  inc     rax
0x140028e5f  cmp     rax, rcx
0x140028e62  jnz     short loc_140028E30
0x140028e64  jmp     loc_140028D7B
0x140028e69  xor     r14d, r14d
0x140028e6c  mov     ebx, r14d
0x140028e6f  mov     [rsp+110h+var_F0], rbx
0x140028e74  mov     ecx, 18h; Size
0x140028e79  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140028e7e  mov     [rsp+110h+var_F0], rax
0x140028e83  test    rax, rax
0x140028e86  jz      short loc_140028EAC
0x140028e88  xorps   xmm0, xmm0
0x140028e8b  movups  xmmword ptr [rax], xmm0
0x140028e8e  mov     dword ptr [rax+8], 1
0x140028e95  mov     dword ptr [rax+0Ch], 1
0x140028e9c  lea     rcx, ??_7?$_Ref_count@VApp@CLI@@@std@@6B@; const std::_Ref_count<CLI::App>::`vftable'
0x140028ea3  mov     [rax], rcx
0x140028ea6  mov     [rax+10h], rbx
0x140028eaa  jmp     short loc_140028EAF
0x140028eac  mov     rax, r14
0x140028eaf  mov     qword ptr [rbp+57h+var_B0], rbx
0x140028eb3  mov     qword ptr [rbp+57h+var_B0+8], rax
0x140028eb7  xorps   xmm0, xmm0
0x140028eba  movdqu  [rsp+110h+var_E0], xmm0
0x140028ec0  lea     rax, [rbp+57h+var_B0]
0x140028ec4  mov     [rsp+110h+var_F0], rax
0x140028ec9  test    rbx, rbx
0x140028ecc  jz      loc_14002908C
0x140028ed2  cmp     qword ptr [rsi+18h], 0
0x140028ed7  jnz     short loc_140028EF1
0x140028ed9  cmp     qword ptr [rsi+348h], 0
0x140028ee1  jz      short loc_140028EF1
0x140028ee3  mov     rcx, rsi; this
0x140028ee6  call    ?_get_fallthrough_parent@App@CLI@@IEAAPEAV12@XZ; CLI::App::_get_fallthrough_parent(void)
0x140028eeb  mov     rbx, qword ptr [rbp+57h+var_B0]
0x140028eef  jmp     short loc_140028EF4
0x140028ef1  mov     rax, rsi
0x140028ef4  mov     r8, rax
0x140028ef7  mov     rdx, rbx
0x140028efa  mov     rcx, rsi
0x140028efd  call    ?_compare_subcommand_names@App@CLI@@IEBAAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV12@0@Z; CLI::App::_compare_subcommand_names(CLI::App const &,CLI::App const &)
0x140028f02  cmp     qword ptr [rax+10h], 0
0x140028f07  jnz     loc_140028FDB
0x140028f0d  mov     rax, qword ptr [rbp+57h+var_B0]
0x140028f11  mov     [rax+348h], rsi
0x140028f18  lea     rcx, [rsi+300h]
0x140028f1f  mov     rdx, [rcx+8]
0x140028f23  cmp     rdx, [rcx+10h]
0x140028f27  jz      short loc_140028F4E
0x140028f29  mov     [rdx], r14
0x140028f2c  mov     [rdx+8], r14
0x140028f30  mov     rax, qword ptr [rbp+57h+var_B0]
0x140028f34  mov     [rdx], rax
0x140028f37  mov     rax, qword ptr [rbp+57h+var_B0+8]
0x140028f3b  mov     [rdx+8], rax
0x140028f3f  xorps   xmm0, xmm0
0x140028f42  movdqu  [rbp+57h+var_B0], xmm0
0x140028f47  add     qword ptr [rcx+8], 10h
0x140028f4c  jmp     short loc_140028F57
0x140028f4e  lea     r8, [rbp+57h+var_B0]
0x140028f52  call    ??$_Emplace_reallocate@V?$shared_ptr@VApp@CLI@@@std@@@?$vector@V?$shared_ptr@VApp@CLI@@@std@@V?$allocator@V?$shared_ptr@VApp@CLI@@@std@@@2@@std@@AEAAPEAV?$shared_ptr@VApp@CLI@@@1@QEAV21@$$QEAV21@@Z; std::vector<std::shared_ptr<CLI::App>>::_Emplace_reallocate<std::shared_ptr<CLI::App>>(std::shared_ptr<CLI::App> * const,std::shared_ptr<CLI::App> &&)
0x140028f57  mov     rax, [rsi+308h]
0x140028f5e  mov     r14, [rax-10h]
0x140028f62  mov     rbx, qword ptr [rbp+57h+var_B0+8]
0x140028f66  test    rbx, rbx
0x140028f69  jz      short loc_140028FA4
0x140028f6b  mov     esi, 0FFFFFFFFh
0x140028f70  mov     eax, esi
0x140028f72  lock xadd [rbx+8], eax
0x140028f77  cmp     eax, 1
0x140028f7a  jnz     short loc_140028FA4
0x140028f7c  mov     rax, [rbx]
0x140028f7f  mov     rcx, rbx
0x140028f82  mov     rax, [rax]
0x140028f85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140028f8a  lock xadd [rbx+0Ch], esi
0x140028f8f  cmp     esi, 1
0x140028f92  jnz     short loc_140028FA4
0x140028f94  mov     rdx, [rbx]
0x140028f97  mov     rcx, rbx
0x140028f9a  mov     rax, [rdx+8]
0x140028f9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140028fa3  nop
0x140028fa4  mov     rcx, rdi; void *
0x140028fa7  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x140028fac  nop
0x140028fad  mov     rcx, r15; void *
0x140028fb0  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x140028fb5  mov     rax, r14
0x140028fb8  mov     rcx, [rbp+57h+var_30]
0x140028fbc  xor     rcx, rsp; StackCookie
0x140028fbf  call    __security_check_cookie
0x140028fc4  mov     rbx, [rsp+110h+arg_18]
0x140028fcc  add     rsp, 0F0h
0x140028fd3  pop     r15
0x140028fd5  pop     r14
0x140028fd7  pop     rdi
0x140028fd8  pop     rsi
0x140028fd9  pop     rbp
0x140028fda  retn
0x140028fdb  mov     r8, rax
0x140028fde  lea     rdx, aSubcommandName_1; "subcommand name or alias matches existi"...
0x140028fe5  lea     rcx, [rbp+57h+var_90]
0x140028fe9  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@QEBDAEBV10@@Z; std::operator+<char>(char const * const,std::string const &)
0x140028fee  mov     rdx, rax
0x140028ff1  lea     rcx, [rbp+57h+pExceptionObject]
0x140028ff5  call    ??0OptionAlreadyAdded@CLI@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; CLI::OptionAlreadyAdded::OptionAlreadyAdded(std::string)
0x140028ffa  lea     rdx, _TI5?AVOptionAlreadyAdded@CLI@@; pThrowInfo
0x140029001  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x140029005  call    _CxxThrowException_0
0x14002900b  lea     rdx, aSubcommandName_0; "Subcommand name contains invalid charac"...
0x140029012  lea     rcx, [rbp+57h+var_90]
0x140029016  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002901b  nop
0x14002901c  movzx   r8d, bl
0x140029020  mov     rdx, rax
0x140029023  lea     rcx, [rbp+57h+var_B0]
0x140029027  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@D@Z; std::operator+<char>(std::string &&,char)
0x14002902c  nop
0x14002902d  lea     r8, aAllCharactersA; "'), all characters are allowed except'="...
0x140029034  mov     rdx, rax
0x140029037  lea     rcx, [rsp+110h+var_E0]
0x14002903c  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@QEBD@Z; std::operator+<char>(std::string &&,char const * const)
0x140029041  mov     rdx, rax
0x140029044  lea     rcx, [rbp+57h+pExceptionObject]
0x140029048  call    ??0IncorrectConstruction@CLI@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; CLI::IncorrectConstruction::IncorrectConstruction(std::string)
0x14002904d  lea     rdx, _TI5?AVIncorrectConstruction@CLI@@; pThrowInfo
0x140029054  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x140029058  call    _CxxThrowException_0
0x14002905e  lea     rdx, aSubcommandName; "Subcommand name starts with invalid cha"...
0x140029065  lea     rcx, [rsp+110h+var_E0]
0x14002906a  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002906f  mov     rdx, rax
0x140029072  lea     rcx, [rbp+57h+pExceptionObject]
0x140029076  call    ??0IncorrectConstruction@CLI@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; CLI::IncorrectConstruction::IncorrectConstruction(std::string)
0x14002907b  lea     rdx, _TI5?AVIncorrectConstruction@CLI@@; pThrowInfo
0x140029082  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x140029086  call    _CxxThrowException_0
0x14002908c  lea     rdx, aPassedAppIsNot; "passed App is not valid"
0x140029093  lea     rcx, [rbp+57h+var_90]
0x140029097  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002909c  mov     rdx, rax
0x14002909f  lea     rcx, [rbp+57h+pExceptionObject]
0x1400290a3  call    ??0IncorrectConstruction@CLI@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; CLI::IncorrectConstruction::IncorrectConstruction(std::string)
0x1400290a8  lea     rdx, _TI5?AVIncorrectConstruction@CLI@@; pThrowInfo
0x1400290af  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1400290b3  call    _CxxThrowException_0
```
