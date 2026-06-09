# CLI::App::App(std::basic_string<char,std::char_traits<char>,std::allocator<char>>,std::basic_string<char,std::char_traits<char>,std::allocator<char>>,CLI::App *)

- ea: `0x1400162d0`
- end: `0x140016bc7`
- name: `??0App@CLI@@IEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@0PEAV01@@Z`
- size: `2295`
- prototype: `__int64 __fastcall(CLI::App *this)`
- caller_count: `2`
- callee_count: `14`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x140006820`
- `0x140028cd0`

## callees

- `0x1400083f0`
- `0x140008a50`
- `0x14000f7e0`
- `0x14000f804`
- `0x14000fab8`
- `0x140010a50`
- `0x140013ba0`
- `0x1400162d0`
- `0x14001abf0`
- `0x140032850`
- `0x14003dad0`
- `0x14003eb20`
- `0x1400455d0`
- `0x140067010`

## string_xrefs

- `0x1400166b4`: `Subcommands`

## pseudocode

```c
// Hidden C++ exception states: #wind=31
CLI::App *__fastcall CLI::App::App(CLI::App *this, __int64 *a2, __int64 *a3, __int64 a4)
{
  char *v8; // r14
  __int64 *v9; // r13
  _QWORD *v10; // rax
  _QWORD *v11; // rsi
  _QWORD *v12; // rax
  _DWORD *v13; // rax
  _QWORD *v14; // rax
  _QWORD *v15; // rax
  _QWORD *v16; // rax
  _QWORD *v17; // rax
  _DWORD *v18; // rax
  __int64 v19; // r9
  __int64 v20; // rax
  __int64 v21; // rcx
  __int64 name; // rax
  __int64 v23; // rcx
  _QWORD *v24; // rbx
  __int64 v25; // r13
  struct CLI::Option *v26; // rdx
  __int64 v27; // rax
  __int64 v28; // rax
  __int64 v29; // rbx
  __int64 v30; // rdx
  _BYTE *v31; // rcx
  __int64 v32; // rcx
  __int64 v33; // rdx
  __int64 *v34; // r8
  __int64 v35; // rdx
  CLI::App *v36; // r8
  __int64 v37; // rdx
  __int64 v38; // rdx
  __int64 v39; // rax
  __int64 v40; // rcx
  volatile signed __int32 *v41; // rbx
  __int64 v42; // rdx
  __int64 v43; // rax
  __int64 v44; // rcx
  volatile signed __int32 *v45; // rbx
  unsigned __int64 v46; // rdx
  __int64 v47; // rax
  unsigned __int64 v48; // rdx
  void *v49; // rcx
  unsigned __int64 v50; // rdx
  __int64 v51; // rax
  unsigned __int64 v52; // rdx
  void *v53; // rcx
  _DWORD *v55; // [rsp+20h] [rbp-A8h]
  _QWORD *v56; // [rsp+28h] [rbp-A0h]
  CLI::App *v57; // [rsp+30h] [rbp-98h]
  _BYTE v58[32]; // [rsp+38h] [rbp-90h] BYREF
  _BYTE v59[32]; // [rsp+58h] [rbp-70h] BYREF
  __int64 *v60; // [rsp+78h] [rbp-50h]
  __int64 *v61; // [rsp+80h] [rbp-48h]

  v57 = this;
  v60 = a2;
  v61 = a3;
  *(_QWORD *)this = &CLI::App::`vftable';
  *(_OWORD *)((char *)this + 8) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 0;
  *(_OWORD *)((char *)this + 8) = *(_OWORD *)a3;
  *(_OWORD *)((char *)this + 24) = *((_OWORD *)a3 + 1);
  a3[2] = 0;
  a3[3] = 15;
  *(_BYTE *)a3 = 0;
  *(_OWORD *)((char *)this + 40) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_QWORD *)this + 8) = 0;
  *(_OWORD *)((char *)this + 40) = *(_OWORD *)a2;
  *(_OWORD *)((char *)this + 56) = *((_OWORD *)a2 + 1);
  a2[2] = 0;
  a2[3] = 15;
  *(_BYTE *)a2 = 0;
  *((_QWORD *)this + 9) = 256;
  *((_QWORD *)this + 17) = 0;
  *((_QWORD *)this + 25) = 0;
  *((_QWORD *)this + 33) = 0;
  v8 = (char *)this + 272;
  *((_QWORD *)this + 38) = 0;
  *((_OWORD *)this + 17) = 0;
  *((_QWORD *)this + 36) = 7;
  *((_QWORD *)this + 37) = 15;
  strcpy((char *)this + 272, "Options");
  *((_QWORD *)this + 38) = 0x1000000;
  *((_QWORD *)this + 39) = 0;
  *((_QWORD *)this + 40) = 0;
  *((_QWORD *)this + 41) = 0;
  v9 = (__int64 *)((char *)this + 336);
  *((_OWORD *)this + 21) = 0;
  *((_QWORD *)this + 44) = 0;
  *((_QWORD *)this + 45) = 15;
  *((_BYTE *)this + 336) = 0;
  *((_QWORD *)this + 53) = 0;
  *((_OWORD *)this + 27) = 0;
  *((_QWORD *)this + 56) = 0;
  *((_QWORD *)this + 57) = 15;
  *((_BYTE *)this + 432) = 0;
  *((_QWORD *)this + 65) = 0;
  *((_QWORD *)this + 66) = 0;
  *((_QWORD *)this + 67) = 0;
  *((_QWORD *)this + 68) = 0;
  v10 = operator new(0x20u);
  v11 = v10;
  v56 = v10;
  if ( v10 )
  {
    *(_OWORD *)v10 = 0;
    *((_OWORD *)v10 + 1) = 0;
    *v10 = &CLI::FormatterBase::`vftable';
    v10[1] = 30;
    v10[2] = 0;
    v10[3] = 0;
    v12 = operator new(0x60u);
    *v12 = v12;
    v12[1] = v12;
    v12[2] = v12;
    *((_WORD *)v12 + 12) = 257;
    v11[2] = v12;
    *v11 = &CLI::Formatter::`vftable';
  }
  else
  {
    v11 = 0;
  }
  *((_QWORD *)this + 69) = 0;
  *((_QWORD *)this + 70) = 0;
  v13 = operator new(0x18u);
  v55 = v13;
  if ( v13 )
  {
    *(_OWORD *)v13 = 0;
    v13[2] = 1;
    v13[3] = 1;
    *(_QWORD *)v13 = &std::_Ref_count<CLI::Formatter>::`vftable';
    *((_QWORD *)v13 + 2) = v11;
  }
  else
  {
    v13 = 0;
  }
  *((_QWORD *)this + 69) = v11;
  *((_QWORD *)this + 70) = v13;
  *((_QWORD *)this + 71) = &std::_Func_impl_no_alloc<std::string (*)(CLI::App const *,CLI::Error const &),std::string,CLI::App const *,CLI::Error const &>::`vftable';
  *((_QWORD *)this + 72) = CLI::FailureMessage::simple;
  *((_QWORD *)this + 78) = (char *)this + 568;
  *((_QWORD *)this + 79) = 0;
  *((_QWORD *)this + 80) = 0;
  *((_QWORD *)this + 81) = 0;
  *((_QWORD *)this + 82) = 0;
  *((_QWORD *)this + 83) = 0;
  *((_QWORD *)this + 84) = 0;
  *((_QWORD *)this + 85) = 0;
  *((_QWORD *)this + 86) = 0;
  *((_QWORD *)this + 87) = 0;
  *((_QWORD *)this + 88) = 0;
  *((_QWORD *)this + 89) = 0;
  v14 = operator new(0x28u);
  *v14 = v14;
  v14[1] = v14;
  v14[2] = v14;
  *((_WORD *)v14 + 12) = 257;
  *((_QWORD *)this + 88) = v14;
  *((_QWORD *)this + 90) = 0;
  *((_QWORD *)this + 91) = 0;
  v15 = operator new(0x28u);
  *v15 = v15;
  v15[1] = v15;
  v15[2] = v15;
  *((_WORD *)v15 + 12) = 257;
  *((_QWORD *)this + 90) = v15;
  *((_QWORD *)this + 92) = 0;
  *((_QWORD *)this + 93) = 0;
  v16 = operator new(0x28u);
  *v16 = v16;
  v16[1] = v16;
  v16[2] = v16;
  *((_WORD *)v16 + 12) = 257;
  *((_QWORD *)this + 92) = v16;
  *((_QWORD *)this + 94) = 0;
  *((_QWORD *)this + 95) = 0;
  v17 = operator new(0x28u);
  *v17 = v17;
  v17[1] = v17;
  v17[2] = v17;
  *((_WORD *)v17 + 12) = 257;
  *((_QWORD *)this + 94) = v17;
  *((_QWORD *)this + 96) = 0;
  *((_QWORD *)this + 97) = 0;
  *((_QWORD *)this + 98) = 0;
  *((_QWORD *)this + 99) = 0x1000000;
  *((_WORD *)this + 400) = 0;
  *((_DWORD *)this + 201) = 0;
  *((_QWORD *)this + 101) = 0;
  *((_QWORD *)this + 102) = 0;
  *((_QWORD *)this + 103) = 0;
  *((_QWORD *)this + 104) = 0;
  *((_QWORD *)this + 105) = a4;
  *((_OWORD *)this + 53) = 0;
  *((_QWORD *)this + 108) = 11;
  *((_QWORD *)this + 109) = 15;
  strcpy((char *)this + 848, "Subcommands");
  *((_QWORD *)this + 110) = 0;
  *((_QWORD *)this + 111) = 0;
  *((_QWORD *)this + 112) = 0;
  *((_QWORD *)this + 113) = 0;
  v18 = operator new(0x50u);
  if ( v18 )
  {
    v18[10] = -65490;
    v18[11] = 0;
    *((_QWORD *)v18 + 1) = 0;
    *((_QWORD *)v18 + 2) = 0;
    *((_QWORD *)v18 + 3) = 0;
    *(_QWORD *)v18 = &CLI::ConfigBase::`vftable';
    v18[8] = 744315683;
    v18[9] = -14212547;
    *((_OWORD *)v18 + 3) = 0;
    *((_QWORD *)v18 + 8) = 0;
    *((_QWORD *)v18 + 9) = 15;
    *((_BYTE *)v18 + 48) = 0;
  }
  else
  {
    v18 = 0;
  }
  std::shared_ptr<CLI::Config>::shared_ptr<CLI::Config>((char *)this + 912, v18);
  *((_QWORD *)this + 116) = 0;
  *((_QWORD *)this + 117) = 0;
  *((_QWORD *)this + 118) = 0;
  *((_QWORD *)this + 119) = 0;
  *((_QWORD *)this + 120) = 0;
  *((_QWORD *)this + 121) = 0;
  v20 = *((_QWORD *)this + 105);
  if ( v20 )
  {
    v21 = *(_QWORD *)(v20 + 528);
    if ( v21 )
    {
      LOBYTE(v19) = 1;
      name = CLI::Option::get_name(v21, v58, 0, v19, v55, v56, v57);
      CLI::App::set_help_flag(this, name, *(_QWORD *)(*((_QWORD *)this + 105) + 528LL) + 200LL);
    }
    v23 = *(_QWORD *)(*((_QWORD *)this + 105) + 536LL);
    if ( v23 )
    {
      LOBYTE(v19) = 1;
      v24 = (_QWORD *)CLI::Option::get_name(v23, v58, 0, v19, v55, v56, v57);
      v25 = *(_QWORD *)(*((_QWORD *)this + 105) + 536LL);
      v26 = (struct CLI::Option *)*((_QWORD *)this + 67);
      if ( v26 )
      {
        CLI::App::remove_option(this, v26);
        *((_QWORD *)this + 67) = 0;
      }
      if ( v24[2] )
      {
        v27 = std::string::string(v59, v24);
        v28 = CLI::App::add_flag<std::string const,0>(this, v27, v25 + 200);
        *((_QWORD *)this + 67) = v28;
        *(_BYTE *)(v28 + 35) = 0;
      }
      std::string::_Tidy_deallocate(v24);
      v9 = (__int64 *)((char *)this + 336);
    }
    v29 = *((_QWORD *)this + 105) + 272LL;
    if ( v8 != (char *)v29 )
    {
      if ( *(_QWORD *)(*((_QWORD *)this + 105) + 296LL) <= 0xFu )
        v30 = *((_QWORD *)this + 105) + 272LL;
      else
        v30 = *(_QWORD *)v29;
      std::string::_Assign<char>(v8, v30, *(_QWORD *)(*((_QWORD *)this + 105) + 288LL));
    }
    v8[32] = *(_BYTE *)(v29 + 32);
    v8[33] = *(_BYTE *)(v29 + 33);
    v8[34] = *(_BYTE *)(v29 + 34);
    v8[35] = *(_BYTE *)(v29 + 35);
    v8[36] = *(_BYTE *)(v29 + 36);
    v8[37] = *(_BYTE *)(v29 + 37);
    v8[38] = *(_BYTE *)(v29 + 38);
    v8[39] = *(_BYTE *)(v29 + 39);
    std::function<std::string (CLI::App const *,CLI::Error const &)>::operator=(
      (char *)this + 568,
      *((_QWORD *)this + 105) + 568LL);
    v31 = (_BYTE *)*((_QWORD *)this + 105);
    *((_BYTE *)this + 72) = v31[72];
    *((_BYTE *)this + 73) = v31[73];
    *((_BYTE *)this + 74) = v31[74];
    *((_BYTE *)this + 79) = v31[79];
    *((_BYTE *)this + 792) = v31[792];
    *((_BYTE *)this + 793) = v31[793];
    *((_BYTE *)this + 794) = v31[794];
    *((_BYTE *)this + 799) = v31[799];
    *((_BYTE *)this + 800) = v31[800];
    v32 = *((_QWORD *)this + 105);
    *((_BYTE *)this + 798) = *(_BYTE *)(v32 + 798);
    *((_BYTE *)this + 795) = *(_BYTE *)(v32 + 795);
    if ( (CLI::App *)((char *)this + 848) != (CLI::App *)(v32 + 848) )
    {
      if ( *(_QWORD *)(v32 + 872) <= 0xFu )
        v33 = v32 + 848;
      else
        v33 = *(_QWORD *)(v32 + 848);
      std::string::_Assign<char>((char *)this + 848, v33, *(_QWORD *)(v32 + 864));
    }
    v34 = (__int64 *)(*((_QWORD *)this + 105) + 336LL);
    if ( v9 != v34 )
    {
      if ( *(_QWORD *)(*((_QWORD *)this + 105) + 360LL) <= 0xFu )
        v35 = *((_QWORD *)this + 105) + 336LL;
      else
        v35 = *v34;
      std::string::_Assign<char>(v9, v35, *(_QWORD *)(*((_QWORD *)this + 105) + 352LL));
    }
    v36 = (CLI::App *)(*((_QWORD *)this + 105) + 432LL);
    if ( (CLI::App *)((char *)this + 432) != v36 )
    {
      if ( *(_QWORD *)(*((_QWORD *)this + 105) + 456LL) <= 0xFu )
        v37 = *((_QWORD *)this + 105) + 432LL;
      else
        v37 = *(_QWORD *)v36;
      std::string::_Assign<char>((char *)this + 432, v37, *(_QWORD *)(*((_QWORD *)this + 105) + 448LL));
    }
    v38 = *((_QWORD *)this + 105);
    v39 = *(_QWORD *)(v38 + 560);
    if ( v39 )
      _InterlockedIncrement((volatile signed __int32 *)(v39 + 8));
    v40 = *(_QWORD *)(v38 + 560);
    *((_QWORD *)this + 69) = *(_QWORD *)(v38 + 552);
    v41 = (volatile signed __int32 *)*((_QWORD *)this + 70);
    *((_QWORD *)this + 70) = v40;
    if ( v41 )
    {
      if ( _InterlockedExchangeAdd(v41 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v41)(v41);
        if ( _InterlockedExchangeAdd(v41 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v41 + 8LL))(v41);
      }
    }
    v42 = *((_QWORD *)this + 105);
    v43 = *(_QWORD *)(v42 + 920);
    if ( v43 )
      _InterlockedIncrement((volatile signed __int32 *)(v43 + 8));
    v44 = *(_QWORD *)(v42 + 920);
    *((_QWORD *)this + 114) = *(_QWORD *)(v42 + 912);
    v45 = (volatile signed __int32 *)*((_QWORD *)this + 115);
    *((_QWORD *)this + 115) = v44;
    if ( v45 )
    {
      if ( _InterlockedExchangeAdd(v45 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v45)(v45);
        if ( _InterlockedExchangeAdd(v45 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v45 + 8LL))(v45);
      }
    }
    *((_QWORD *)this + 102) = *(_QWORD *)(*((_QWORD *)this + 105) + 816LL);
  }
  v46 = a2[3];
  if ( v46 > 0xF )
  {
    v47 = *a2;
    v48 = v46 + 1;
    if ( v48 < 0x1000 )
    {
      v49 = (void *)*a2;
    }
    else
    {
      v49 = *(void **)(v47 - 8);
      if ( (unsigned __int64)(v47 - (_QWORD)v49 - 8) > 0x1F )
        __fastfail(5u);
      v48 += 39LL;
    }
    operator delete(v49, v48);
  }
  a2[2] = 0;
  a2[3] = 15;
  *(_BYTE *)a2 = 0;
  v50 = a3[3];
  if ( v50 > 0xF )
  {
    v51 = *a3;
    v52 = v50 + 1;
    if ( v52 < 0x1000 )
    {
      v53 = (void *)*a3;
    }
    else
    {
      v53 = *(void **)(v51 - 8);
      if ( (unsigned __int64)(v51 - (_QWORD)v53 - 8) > 0x1F )
        __fastfail(5u);
      v52 += 39LL;
    }
    operator delete(v53, v52);
  }
  a3[2] = 0;
  a3[3] = 15;
  *(_BYTE *)a3 = 0;
  return this;
}

```

## disassembly

```asm
0x1400162d0  mov     [rsp+arg_18], rbx
0x1400162d5  push    rbp
0x1400162d6  push    rsi
0x1400162d7  push    rdi
0x1400162d8  push    r12
0x1400162da  push    r13
0x1400162dc  push    r14
0x1400162de  push    r15
0x1400162e0  sub     rsp, 90h
0x1400162e7  mov     rax, cs:__security_cookie
0x1400162ee  xor     rax, rsp
0x1400162f1  mov     [rsp+0C8h+var_40], rax
0x1400162f9  mov     r12, r9
0x1400162fc  mov     r15, r8
0x1400162ff  mov     rbp, rdx
0x140016302  mov     rdi, rcx
0x140016305  mov     [rsp+0C8h+var_98], rcx
0x14001630a  mov     [rsp+0C8h+var_50], rdx
0x14001630f  mov     [rsp+0C8h+var_48], r8
0x140016317  lea     rax, ??_7App@CLI@@6B@; const CLI::App::`vftable'
0x14001631e  mov     [rcx], rax
0x140016321  xorps   xmm0, xmm0
0x140016324  movups  xmmword ptr [rcx+8], xmm0
0x140016328  xor     ebx, ebx
0x14001632a  mov     [rcx+18h], rbx
0x14001632e  mov     [rcx+20h], rbx
0x140016332  movups  xmm0, xmmword ptr [r8]
0x140016336  movups  xmmword ptr [rcx+8], xmm0
0x14001633a  movups  xmm1, xmmword ptr [r8+10h]
0x14001633f  movups  xmmword ptr [rcx+18h], xmm1
0x140016343  mov     [r8+10h], rbx
0x140016347  mov     qword ptr [r8+18h], 0Fh
0x14001634f  mov     [r8], bl
0x140016352  xorps   xmm0, xmm0
0x140016355  movups  xmmword ptr [rcx+28h], xmm0
0x140016359  mov     [rcx+38h], rbx
0x14001635d  mov     [rcx+40h], rbx
0x140016361  movups  xmm0, xmmword ptr [rdx]
0x140016364  movups  xmmword ptr [rcx+28h], xmm0
0x140016368  movups  xmm1, xmmword ptr [rdx+10h]
0x14001636c  movups  xmmword ptr [rcx+38h], xmm1
0x140016370  mov     [rdx+10h], rbx
0x140016374  mov     qword ptr [rdx+18h], 0Fh
0x14001637c  mov     [rdx], bl
0x14001637e  mov     qword ptr [rcx+48h], 100h
0x140016386  mov     [rcx+88h], rbx
0x14001638d  mov     [rcx+0C8h], rbx
0x140016394  mov     [rcx+108h], rbx
0x14001639b  lea     r14, [rcx+110h]
0x1400163a2  mov     [r14+20h], rbx
0x1400163a6  xorps   xmm0, xmm0
0x1400163a9  movups  xmmword ptr [r14], xmm0
0x1400163ad  mov     qword ptr [r14+10h], 7
0x1400163b5  mov     qword ptr [r14+18h], 0Fh
0x1400163bd  mov     rax, qword ptr cs:aOptions; "Options"
0x1400163c4  mov     [r14], eax
0x1400163c7  movzx   eax, word ptr cs:aOptions+4; "ons"
0x1400163ce  mov     [r14+4], ax
0x1400163d3  movzx   eax, byte ptr cs:aOptions+6; "s"
0x1400163da  mov     [r14+6], al
0x1400163de  mov     [r14+7], bl
0x1400163e2  mov     qword ptr [r14+20h], 1000000h
0x1400163ea  mov     [rcx+138h], rbx
0x1400163f1  mov     [rcx+140h], rbx
0x1400163f8  mov     [rcx+148h], rbx
0x1400163ff  lea     r13, [rcx+150h]
0x140016406  movups  xmmword ptr [r13+0], xmm0
0x14001640b  mov     [r13+10h], rbx
0x14001640f  mov     qword ptr [r13+18h], 0Fh
0x140016417  mov     [r13+0], bl
0x14001641b  mov     [rcx+1A8h], rbx
0x140016422  movups  xmmword ptr [rcx+1B0h], xmm0
0x140016429  mov     [rcx+1C0h], rbx
0x140016430  mov     qword ptr [rcx+1C8h], 0Fh
0x14001643b  mov     [rcx+1B0h], bl
0x140016441  mov     [rcx+208h], rbx
0x140016448  mov     [rcx+210h], rbx
0x14001644f  mov     [rcx+218h], rbx
0x140016456  mov     [rcx+220h], rbx
0x14001645d  mov     ecx, 20h ; ' '; Size
0x140016462  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140016467  mov     rsi, rax
0x14001646a  mov     [rsp+0C8h+var_A0], rax
0x14001646f  test    rax, rax
0x140016472  jz      short loc_1400164C5
0x140016474  xorps   xmm0, xmm0
0x140016477  movups  xmmword ptr [rax], xmm0
0x14001647a  movups  xmmword ptr [rax+10h], xmm0
0x14001647e  lea     rax, ??_7FormatterBase@CLI@@6B@; const CLI::FormatterBase::`vftable'
0x140016485  mov     [rsi], rax
0x140016488  mov     qword ptr [rsi+8], 1Eh
0x140016490  xor     eax, eax
0x140016492  mov     [rsi+10h], rax
0x140016496  mov     [rsi+18h], rax
0x14001649a  mov     ecx, 60h ; '`'; Size
0x14001649f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400164a4  mov     [rax], rax
0x1400164a7  mov     [rax+8], rax
0x1400164ab  mov     [rax+10h], rax
0x1400164af  mov     word ptr [rax+18h], 101h
0x1400164b5  mov     [rsi+10h], rax
0x1400164b9  lea     rax, ??_7Formatter@CLI@@6B@; const CLI::Formatter::`vftable'
0x1400164c0  mov     [rsi], rax
0x1400164c3  jmp     short loc_1400164C8
0x1400164c5  mov     rsi, rbx
0x1400164c8  mov     [rdi+228h], rbx
0x1400164cf  mov     [rdi+230h], rbx
0x1400164d6  mov     [rsp+0C8h+var_A8], rsi
0x1400164db  mov     ecx, 18h; Size
0x1400164e0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400164e5  mov     [rsp+0C8h+var_A8], rax
0x1400164ea  test    rax, rax
0x1400164ed  jz      short loc_140016513
0x1400164ef  xorps   xmm0, xmm0
0x1400164f2  movups  xmmword ptr [rax], xmm0
0x1400164f5  mov     dword ptr [rax+8], 1
0x1400164fc  mov     dword ptr [rax+0Ch], 1
0x140016503  lea     rcx, ??_7?$_Ref_count@VFormatter@CLI@@@std@@6B@; const std::_Ref_count<CLI::Formatter>::`vftable'
0x14001650a  mov     [rax], rcx
0x14001650d  mov     [rax+10h], rsi
0x140016511  jmp     short loc_140016516
0x140016513  mov     rax, rbx
0x140016516  mov     [rdi+228h], rsi
0x14001651d  mov     [rdi+230h], rax
0x140016524  lea     rax, [rdi+238h]
0x14001652b  lea     rcx, ??_7?$_Func_impl_no_alloc@P6A?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBVApp@CLI@@AEBVError@4@@ZV12@PEBV34@AEBV54@@std@@6B@; const std::_Func_impl_no_alloc<std::string (*)(CLI::App const *,CLI::Error const &),std::string,CLI::App const *,CLI::Error const &>::`vftable'
0x140016532  mov     [rax], rcx
0x140016535  lea     rcx, ?simple@FailureMessage@CLI@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBVApp@2@AEBVError@2@@Z; CLI::FailureMessage::simple(CLI::App const *,CLI::Error const &)
0x14001653c  mov     [rax+8], rcx
0x140016540  mov     [rax+38h], rax
0x140016544  mov     [rdi+278h], rbx
0x14001654b  mov     [rdi+280h], rbx
0x140016552  mov     [rdi+288h], rbx
0x140016559  mov     [rdi+290h], rbx
0x140016560  mov     [rdi+298h], rbx
0x140016567  mov     [rdi+2A0h], rbx
0x14001656e  mov     [rdi+2A8h], rbx
0x140016575  mov     [rdi+2B0h], rbx
0x14001657c  mov     [rdi+2B8h], rbx
0x140016583  xor     esi, esi
0x140016585  mov     [rdi+2C0h], rsi
0x14001658c  mov     [rdi+2C8h], rsi
0x140016593  mov     ecx, 28h ; '('; Size
0x140016598  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14001659d  mov     [rax], rax
0x1400165a0  mov     [rax+8], rax
0x1400165a4  mov     [rax+10h], rax
0x1400165a8  mov     word ptr [rax+18h], 101h
0x1400165ae  mov     [rdi+2C0h], rax
0x1400165b5  mov     [rdi+2D0h], rsi
0x1400165bc  mov     [rdi+2D8h], rsi
0x1400165c3  mov     ecx, 28h ; '('; Size
0x1400165c8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400165cd  mov     [rax], rax
0x1400165d0  mov     [rax+8], rax
0x1400165d4  mov     [rax+10h], rax
0x1400165d8  mov     word ptr [rax+18h], 101h
0x1400165de  mov     [rdi+2D0h], rax
0x1400165e5  mov     [rdi+2E0h], rsi
0x1400165ec  mov     [rdi+2E8h], rsi
0x1400165f3  mov     ecx, 28h ; '('; Size
0x1400165f8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400165fd  mov     [rax], rax
0x140016600  mov     [rax+8], rax
0x140016604  mov     [rax+10h], rax
0x140016608  mov     word ptr [rax+18h], 101h
0x14001660e  mov     [rdi+2E0h], rax
0x140016615  mov     [rdi+2F0h], rsi
0x14001661c  mov     [rdi+2F8h], rsi
0x140016623  mov     ecx, 28h ; '('; Size
0x140016628  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14001662d  mov     [rax], rax
0x140016630  mov     [rax+8], rax
0x140016634  mov     [rax+10h], rax
0x140016638  mov     word ptr [rax+18h], 101h
0x14001663e  mov     [rdi+2F0h], rax
0x140016645  xor     ebx, ebx
0x140016647  mov     [rdi+300h], rbx
0x14001664e  mov     [rdi+308h], rbx
0x140016655  mov     [rdi+310h], rbx
0x14001665c  mov     qword ptr [rdi+318h], 1000000h
0x140016667  mov     [rdi+320h], bx
0x14001666e  mov     [rdi+324h], ebx
0x140016674  mov     [rdi+328h], rbx
0x14001667b  mov     [rdi+330h], rbx
0x140016682  mov     [rdi+338h], rbx
0x140016689  mov     [rdi+340h], rbx
0x140016690  mov     [rdi+348h], r12
0x140016697  lea     rcx, [rdi+350h]
0x14001669e  xorps   xmm0, xmm0
0x1400166a1  movups  xmmword ptr [rcx], xmm0
0x1400166a4  mov     qword ptr [rcx+10h], 0Bh
0x1400166ac  mov     qword ptr [rcx+18h], 0Fh
0x1400166b4  movsd   xmm0, qword ptr cs:aSubcommands_0; "Subcommands"
0x1400166bc  movsd   qword ptr [rcx], xmm0
0x1400166c0  mov     eax, dword ptr cs:aSubcommands_0+7; "ands"
0x1400166c6  mov     [rcx+7], eax
0x1400166c9  mov     [rcx+0Bh], bl
0x1400166cc  mov     [rdi+370h], rbx
0x1400166d3  mov     [rdi+378h], rbx
0x1400166da  mov     [rdi+380h], rbx
0x1400166e1  mov     [rdi+388h], rbx
0x1400166e8  mov     ecx, 50h ; 'P'; Size
0x1400166ed  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400166f2  mov     esi, 0FFFFFFFFh
0x1400166f7  test    rax, rax
0x1400166fa  jz      short loc_140016742
0x1400166fc  mov     dword ptr [rax+28h], 0FFFF002Eh
0x140016703  mov     [rax+2Ch], ebx
0x140016706  mov     [rax+8], rbx
0x14001670a  mov     [rax+10h], rbx
0x14001670e  mov     [rax+18h], rbx
0x140016712  lea     rcx, ??_7ConfigBase@CLI@@6B@; const CLI::ConfigBase::`vftable'
0x140016719  mov     [rax], rcx
0x14001671c  mov     dword ptr [rax+20h], 2C5D5B23h
0x140016723  mov     dword ptr [rax+24h], 0FF27223Dh
0x14001672a  xorps   xmm0, xmm0
0x14001672d  movups  xmmword ptr [rax+30h], xmm0
0x140016731  mov     [rax+40h], rbx
0x140016735  mov     qword ptr [rax+48h], 0Fh
0x14001673d  mov     [rax+30h], bl
0x140016740  jmp     short loc_140016745
0x140016742  mov     rax, rbx
0x140016745  mov     rdx, rax
0x140016748  lea     rcx, [rdi+390h]
0x14001674f  call    ??$?0VConfigBase@CLI@@$0A@@?$shared_ptr@VConfig@CLI@@@std@@QEAA@PEAVConfigBase@CLI@@@Z; std::shared_ptr<CLI::Config>::shared_ptr<CLI::Config>(CLI::ConfigBase *)
0x140016754  nop
0x140016755  mov     [rdi+3A0h], rbx
0x14001675c  mov     [rdi+3A8h], rbx
0x140016763  mov     [rdi+3B0h], rbx
0x14001676a  mov     [rdi+3B8h], rbx
0x140016771  mov     [rdi+3C0h], rbx
0x140016778  mov     [rdi+3C8h], rbx
0x14001677f  mov     rax, [rdi+348h]
0x140016786  test    rax, rax
0x140016789  jz      loc_140016AFA
0x14001678f  mov     rcx, [rax+210h]
0x140016796  test    rcx, rcx
0x140016799  jz      short loc_1400167CB
0x14001679b  mov     r9b, 1
0x14001679e  xor     r8d, r8d
0x1400167a1  lea     rdx, [rsp+0C8h+var_90]
0x1400167a6  call    ?get_name@Option@CLI@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@_N0@Z; CLI::Option::get_name(bool,bool)
0x1400167ab  mov     rdx, rax
0x1400167ae  mov     rax, [rdi+348h]
0x1400167b5  mov     r8, [rax+210h]
0x1400167bc  add     r8, 0C8h
0x1400167c3  mov     rcx, rdi
0x1400167c6  call    ?set_help_flag@App@CLI@@QEAAPEAVOption@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV45@@Z; CLI::App::set_help_flag(std::string,std::string const &)
0x1400167cb  mov     rax, [rdi+348h]
0x1400167d2  mov     rcx, [rax+218h]
0x1400167d9  test    rcx, rcx
0x1400167dc  jz      loc_140016865
0x1400167e2  mov     r9b, 1
0x1400167e5  xor     r8d, r8d
0x1400167e8  lea     rdx, [rsp+0C8h+var_90]
0x1400167ed  call    ?get_name@Option@CLI@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@_N0@Z; CLI::Option::get_name(bool,bool)
0x1400167f2  mov     rbx, rax
0x1400167f5  mov     [rsp+0C8h+var_A8], rax
0x1400167fa  mov     rax, [rdi+348h]
0x140016801  mov     r13, [rax+218h]
0x140016808  mov     rdx, [rdi+218h]; struct CLI::Option *
0x14001680f  test    rdx, rdx
0x140016812  jz      short loc_140016825
0x140016814  mov     rcx, rdi; this
0x140016817  call    ?remove_option@App@CLI@@QEAA_NPEAVOption@2@@Z; CLI::App::remove_option(CLI::Option *)
0x14001681c  xor     eax, eax
0x14001681e  mov     [rdi+218h], rax
0x140016825  cmp     qword ptr [rbx+10h], 0
0x14001682a  jz      short loc_140016856
0x14001682c  mov     rdx, rbx
0x14001682f  lea     rcx, [rsp+0C8h+var_70]
0x140016834  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@AEBV01@@Z; std::string::string(std::string const &)
0x140016839  lea     r8, [r13+0C8h]
0x140016840  mov     rdx, rax
0x140016843  mov     rcx, rdi
0x140016846  call    ??$add_flag@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@$0A@@App@CLI@@QEAAPEAVOption@1@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV34@@Z; CLI::App::add_flag<std::string const,0>(std::string,std::string const &)
0x14001684b  mov     [rdi+218h], rax
0x140016852  mov     byte ptr [rax+23h], 0
0x140016856  mov     rcx, rbx; void *
0x140016859  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x14001685e  lea     r13, [rdi+150h]
0x140016865  mov     rbx, [rdi+348h]
0x14001686c  add     rbx, 110h
0x140016873  cmp     r14, rbx
0x140016876  jz      short loc_140016893
0x140016878  cmp     qword ptr [rbx+18h], 0Fh
0x14001687d  jbe     short loc_140016884
0x14001687f  mov     rdx, [rbx]
0x140016882  jmp     short loc_140016887
0x140016884  mov     rdx, rbx
0x140016887  mov     r8, [rbx+10h]
0x14001688b  mov     rcx, r14
0x14001688e  call    ??$_Assign@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@QEBD_K@Z; std::string::_Assign<char>(char const * const,unsigned __int64)
0x140016893  movzx   eax, byte ptr [rbx+20h]
0x140016897  mov     [r14+20h], al
0x14001689b  movzx   eax, byte ptr [rbx+21h]
0x14001689f  mov     [r14+21h], al
0x1400168a3  movzx   eax, byte ptr [rbx+22h]
0x1400168a7  mov     [r14+22h], al
  ... truncated ...
```
