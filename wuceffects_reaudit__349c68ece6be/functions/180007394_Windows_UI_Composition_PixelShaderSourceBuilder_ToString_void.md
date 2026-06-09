# Windows::UI::Composition::PixelShaderSourceBuilder::ToString(void)

- ea: `0x180007394`
- end: `0x1800077fe`
- name: `?ToString@PixelShaderSourceBuilder@Composition@UI@Windows@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ`
- size: `1130`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180008a30`

## callees

- `0x1800061b0`
- `0x180007394`
- `0x180007810`
- `0x180007920`
- `0x180007ee4`
- `0x180007f00`
- `0x180008670`
- `0x18000ad40`
- `0x18000ba94`
- `0x18001aca0`

## string_xrefs

- `0x1800073e9`: `// Copyright (C) Microsoft. All rights reserved.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::UI::Composition::PixelShaderSourceBuilder::ToString(_QWORD *a1, __int64 a2)
{
  _QWORD *v4; // rax
  __int64 v5; // r14
  __int64 i; // rdi
  __int64 v7; // rcx
  _QWORD *v8; // rcx
  __int64 v9; // r9
  __int64 v10; // r10
  _QWORD *v11; // rcx
  _QWORD *v12; // rdx
  _QWORD *v13; // rdx
  __int64 v14; // rdi
  __int64 v15; // r14
  bool v16; // zf
  _QWORD *v17; // rbx
  __int64 v18; // r9
  __int64 v19; // r10
  _QWORD *v20; // rcx
  _QWORD *v21; // rdx
  __int64 v22; // r8
  __int64 v23; // rcx
  __int64 v24; // r9
  _QWORD *v25; // rax
  _QWORD *v27; // rax
  _QWORD *v28; // rdx
  _QWORD *v29; // rax
  __int64 v30; // r9
  _QWORD *v31; // rdx
  _QWORD *v32; // [rsp+40h] [rbp-19h] BYREF
  __int64 v33; // [rsp+48h] [rbp-11h]
  _QWORD *v34; // [rsp+50h] [rbp-9h] BYREF
  __int64 v35; // [rsp+58h] [rbp-1h]
  _BYTE v36[24]; // [rsp+60h] [rbp+7h] BYREF
  __int128 v37; // [rsp+78h] [rbp+1Fh] BYREF
  __int128 v38; // [rsp+88h] [rbp+2Fh]
  __int64 v39; // [rsp+98h] [rbp+3Fh]
  char v40; // [rsp+D0h] [rbp+77h] BYREF

  v37 = 0;
  v38 = 0;
  v39 = 0;
  v4 = (_QWORD *)std::_Allocate<16,std::_Default_allocate_traits>(0x10u);
  v4[1] = 0;
  *(_QWORD *)&v37 = v4;
  *v4 = &v37;
  Windows::UI::Composition::StringBuilder::Append(
    (Windows::UI::Composition::StringBuilder *)&v37,
    "// Copyright (C) Microsoft. All rights reserved.");
  v40 = 10;
  std::deque<char>::_Emplace_back_internal<char const &>(&v37, &v40);
  Windows::UI::Composition::StringBuilder::Append(
    (Windows::UI::Composition::StringBuilder *)&v37,
    "// Generated file, do not edit.");
  v40 = 10;
  std::deque<char>::_Emplace_back_internal<char const &>(&v37, &v40);
  v40 = 10;
  std::deque<char>::_Emplace_back_internal<char const &>(&v37, &v40);
  v5 = a1[2];
  for ( i = a1[1]; i != v5; i += 32 )
  {
    Windows::UI::Composition::StringBuilder::Append((Windows::UI::Composition::StringBuilder *)&v37, "#include \"");
    Windows::UI::Composition::StringBuilder::Append(&v37, i);
    v40 = 34;
    std::deque<char>::_Emplace_back_internal<char const &>(&v37, &v40);
    v40 = 10;
    std::deque<char>::_Emplace_back_internal<char const &>(&v37, &v40);
  }
  if ( a1[1] != a1[2] )
  {
    v40 = 10;
    std::deque<char>::_Emplace_back_internal<char const &>(&v37, &v40);
  }
  v7 = a1[8];
  if ( v7 )
  {
    v29 = a1 + 4;
    v30 = a1[7];
    if ( a1 == (_QWORD *)-32LL || (v31 = (_QWORD *)*v29) == 0 )
    {
      v27 = 0;
      v28 = 0;
    }
    else
    {
      v27 = (_QWORD *)*v31;
      v28 = (_QWORD *)*v31;
    }
    v32 = v28;
    v33 = v30 + v7;
    v34 = v27;
    v35 = v30;
    std::deque<char>::_Insert_range<1,std::_Deque_unchecked_const_iterator<std::_Deque_val<std::_Deque_simple_types<char>>>,std::_Deque_unchecked_const_iterator<std::_Deque_val<std::_Deque_simple_types<char>>>>(
      (unsigned int)&v37,
      (unsigned int)v36,
      v39,
      (unsigned int)&v34,
      (__int64)&v32);
    v40 = 10;
    std::deque<char>::push_back(&v37, &v40);
  }
  if ( a1[13] )
  {
    Windows::UI::Composition::StringBuilder::Append((Windows::UI::Composition::StringBuilder *)&v37, "cbuffer ");
    Windows::UI::Composition::StringBuilder::Append((Windows::UI::Composition::StringBuilder *)&v37, "PSConstants");
    Windows::UI::Composition::StringBuilder::Append((Windows::UI::Composition::StringBuilder *)&v37, " : register(b0)");
    v40 = 10;
    std::deque<char>::_Emplace_back_internal<char const &>(&v37, &v40);
    v40 = 123;
    std::deque<char>::_Emplace_back_internal<char const &>(&v37, &v40);
    v40 = 10;
    std::deque<char>::_Emplace_back_internal<char const &>(&v37, &v40);
    v8 = a1 + 9;
    v9 = a1[12];
    v10 = v9 + a1[13];
    if ( a1 == (_QWORD *)-72LL || (v13 = (_QWORD *)*v8) == 0 )
    {
      v11 = 0;
      v12 = 0;
    }
    else
    {
      v11 = (_QWORD *)*v13;
      v12 = (_QWORD *)*v13;
    }
    v34 = v12;
    v35 = v10;
    v32 = v11;
    v33 = v9;
    std::deque<char>::_Insert_range<1,std::_Deque_unchecked_const_iterator<std::_Deque_val<std::_Deque_simple_types<char>>>,std::_Deque_unchecked_const_iterator<std::_Deque_val<std::_Deque_simple_types<char>>>>(
      (unsigned int)&v37,
      (unsigned int)v36,
      v39,
      (unsigned int)&v32,
      (__int64)&v34);
    v40 = 125;
    std::deque<char>::_Emplace_back_internal<char const &>(&v37, &v40);
    v40 = 10;
    std::deque<char>::_Emplace_back_internal<char const &>(&v37, &v40);
    v40 = 10;
    std::deque<char>::_Emplace_back_internal<char const &>(&v37, &v40);
  }
  Windows::UI::Composition::StringBuilder::Append((Windows::UI::Composition::StringBuilder *)&v37, "export minfloat4 ");
  Windows::UI::Composition::StringBuilder::Append((Windows::UI::Composition::StringBuilder *)&v37, "PSBody");
  v40 = 40;
  std::deque<char>::_Emplace_back_internal<char const &>(&v37, &v40);
  v40 = 10;
  std::deque<char>::_Emplace_back_internal<char const &>(&v37, &v40);
  v14 = a1[14];
  v15 = a1[15];
  if ( v14 != v15 )
  {
    while ( 1 )
    {
      Windows::UI::Composition::StringBuilder::Append((Windows::UI::Composition::StringBuilder *)&v37, "    ");
      Windows::UI::Composition::StringBuilder::Append(&v37, v14);
      v14 += 32;
      if ( v14 == v15 )
        break;
      v40 = 44;
      std::deque<char>::push_back(&v37, &v40);
      v40 = 10;
      std::deque<char>::push_back(&v37, &v40);
    }
  }
  Windows::UI::Composition::StringBuilder::Append((Windows::UI::Composition::StringBuilder *)&v37, ")");
  v40 = 10;
  std::deque<char>::_Emplace_back_internal<char const &>(&v37, &v40);
  v40 = 123;
  std::deque<char>::_Emplace_back_internal<char const &>(&v37, &v40);
  v40 = 10;
  std::deque<char>::_Emplace_back_internal<char const &>(&v37, &v40);
  v16 = a1 + 17 == 0;
  v17 = a1 + 17;
  v18 = v17[3];
  v19 = v17[4] + v18;
  if ( v16 || !*v17 )
  {
    v20 = 0;
    v21 = 0;
  }
  else
  {
    v20 = *(_QWORD **)*v17;
    v21 = v20;
  }
  v34 = v21;
  v35 = v19;
  v32 = v20;
  v33 = v18;
  std::deque<char>::_Insert_range<1,std::_Deque_unchecked_const_iterator<std::_Deque_val<std::_Deque_simple_types<char>>>,std::_Deque_unchecked_const_iterator<std::_Deque_val<std::_Deque_simple_types<char>>>>(
    (unsigned int)&v37,
    (unsigned int)v36,
    v39,
    (unsigned int)&v32,
    (__int64)&v34);
  v40 = 125;
  std::deque<char>::_Emplace_back_internal<char const &>(&v37, &v40);
  v40 = 10;
  std::deque<char>::_Emplace_back_internal<char const &>(&v37, &v40);
  v23 = *((_QWORD *)&v38 + 1);
  v24 = *((_QWORD *)&v38 + 1) + v39;
  v25 = (_QWORD *)v37;
  *(_OWORD *)a2 = 0;
  *(_QWORD *)(a2 + 16) = 0;
  *(_QWORD *)(a2 + 24) = 0;
  if ( v25 )
    v25 = (_QWORD *)*v25;
  if ( v23 == v24 )
  {
    std::string::_Construct_empty(a2);
  }
  else
  {
    v34 = v25;
    v35 = v23;
    std::string::_Construct_from_iter<std::_Deque_unchecked_const_iterator<std::_Deque_val<std::_Deque_simple_types<char>>>,std::_Deque_unchecked_const_iterator<std::_Deque_val<std::_Deque_simple_types<char>>>,unsigned __int64>(
      a2,
      &v34,
      v22,
      v24 - v23);
  }
  Windows::UI::Composition::StringBuilder::~StringBuilder((Windows::UI::Composition::StringBuilder *)&v37);
  return a2;
}

```

## disassembly

```asm
0x180007394  mov     [rsp-8+arg_0], rbx
0x180007399  mov     [rsp-8+arg_8], rsi
0x18000739e  push    rbp
0x18000739f  push    rdi
0x1800073a0  push    r14
0x1800073a2  lea     rbp, [rsp-47h]
0x1800073a7  sub     rsp, 0A0h
0x1800073ae  mov     rsi, rdx
0x1800073b1  mov     rbx, rcx
0x1800073b4  xorps   xmm0, xmm0
0x1800073b7  movdqu  [rbp+57h+var_38], xmm0
0x1800073bc  xorps   xmm1, xmm1
0x1800073bf  movdqu  [rbp+57h+var_28], xmm1
0x1800073c4  mov     [rbp+57h+var_18], 0
0x1800073cc  mov     ecx, 10h; dwBytes
0x1800073d1  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x1800073d6  mov     qword ptr [rax+8], 0
0x1800073de  mov     qword ptr [rbp+57h+var_38], rax
0x1800073e2  lea     rcx, [rbp+57h+var_38]
0x1800073e6  mov     [rax], rcx
0x1800073e9  lea     rdx, aCopyrightCMicr; "// Copyright (C) Microsoft. All rights "...
0x1800073f0  lea     rcx, [rbp+57h+var_38]; this
0x1800073f4  call    ?Append@StringBuilder@Composition@UI@Windows@@QEAAXPEBD@Z; Windows::UI::Composition::StringBuilder::Append(char const *)
0x1800073f9  mov     [rbp+57h+arg_10], 0Ah
0x1800073fd  lea     rdx, [rbp+57h+arg_10]
0x180007401  lea     rcx, [rbp+57h+var_38]
0x180007405  call    ??$_Emplace_back_internal@AEBD@?$deque@DV?$allocator@D@std@@@std@@AEAAXAEBD@Z; std::deque<char>::_Emplace_back_internal<char const &>(char const &)
0x18000740a  lea     rdx, aGeneratedFileD; "// Generated file, do not edit."
0x180007411  lea     rcx, [rbp+57h+var_38]; this
0x180007415  call    ?Append@StringBuilder@Composition@UI@Windows@@QEAAXPEBD@Z; Windows::UI::Composition::StringBuilder::Append(char const *)
0x18000741a  mov     [rbp+57h+arg_10], 0Ah
0x18000741e  lea     rdx, [rbp+57h+arg_10]
0x180007422  lea     rcx, [rbp+57h+var_38]
0x180007426  call    ??$_Emplace_back_internal@AEBD@?$deque@DV?$allocator@D@std@@@std@@AEAAXAEBD@Z; std::deque<char>::_Emplace_back_internal<char const &>(char const &)
0x18000742b  mov     [rbp+57h+arg_10], 0Ah
0x18000742f  lea     rdx, [rbp+57h+arg_10]
0x180007433  lea     rcx, [rbp+57h+var_38]
0x180007437  call    ??$_Emplace_back_internal@AEBD@?$deque@DV?$allocator@D@std@@@std@@AEAAXAEBD@Z; std::deque<char>::_Emplace_back_internal<char const &>(char const &)
0x18000743c  mov     r14, [rbx+10h]
0x180007440  mov     rdi, [rbx+8]
0x180007444  cmp     rdi, r14
0x180007447  jnz     loc_180007501
0x18000744d  mov     rax, [rbx+10h]
0x180007451  cmp     [rbx+8], rax
0x180007455  jz      short loc_180007468
0x180007457  mov     [rbp+57h+arg_10], 0Ah
0x18000745b  lea     rdx, [rbp+57h+arg_10]
0x18000745f  lea     rcx, [rbp+57h+var_38]
0x180007463  call    ??$_Emplace_back_internal@AEBD@?$deque@DV?$allocator@D@std@@@std@@AEAAXAEBD@Z; std::deque<char>::_Emplace_back_internal<char const &>(char const &)
0x180007468  mov     rcx, [rbx+40h]
0x18000746c  test    rcx, rcx
0x18000746f  jnz     loc_1800077B1
0x180007475  cmp     qword ptr [rbx+68h], 0
0x18000747a  jbe     loc_1800075B3
0x180007480  lea     rdx, aCbuffer; "cbuffer "
0x180007487  lea     rcx, [rbp+57h+var_38]; this
0x18000748b  call    ?Append@StringBuilder@Composition@UI@Windows@@QEAAXPEBD@Z; Windows::UI::Composition::StringBuilder::Append(char const *)
0x180007490  lea     rdx, aPsconstants; "PSConstants"
0x180007497  lea     rcx, [rbp+57h+var_38]; this
0x18000749b  call    ?Append@StringBuilder@Composition@UI@Windows@@QEAAXPEBD@Z; Windows::UI::Composition::StringBuilder::Append(char const *)
0x1800074a0  lea     rdx, aRegisterB0; " : register(b0)"
0x1800074a7  lea     rcx, [rbp+57h+var_38]; this
0x1800074ab  call    ?Append@StringBuilder@Composition@UI@Windows@@QEAAXPEBD@Z; Windows::UI::Composition::StringBuilder::Append(char const *)
0x1800074b0  mov     [rbp+57h+arg_10], 0Ah
0x1800074b4  lea     rdx, [rbp+57h+arg_10]
0x1800074b8  lea     rcx, [rbp+57h+var_38]
0x1800074bc  call    ??$_Emplace_back_internal@AEBD@?$deque@DV?$allocator@D@std@@@std@@AEAAXAEBD@Z; std::deque<char>::_Emplace_back_internal<char const &>(char const &)
0x1800074c1  mov     [rbp+57h+arg_10], 7Bh ; '{'
0x1800074c5  lea     rdx, [rbp+57h+arg_10]
0x1800074c9  lea     rcx, [rbp+57h+var_38]
0x1800074cd  call    ??$_Emplace_back_internal@AEBD@?$deque@DV?$allocator@D@std@@@std@@AEAAXAEBD@Z; std::deque<char>::_Emplace_back_internal<char const &>(char const &)
0x1800074d2  mov     [rbp+57h+arg_10], 0Ah
0x1800074d6  lea     rdx, [rbp+57h+arg_10]
0x1800074da  lea     rcx, [rbp+57h+var_38]
0x1800074de  call    ??$_Emplace_back_internal@AEBD@?$deque@DV?$allocator@D@std@@@std@@AEAAXAEBD@Z; std::deque<char>::_Emplace_back_internal<char const &>(char const &)
0x1800074e3  lea     rcx, [rbx+48h]
0x1800074e7  mov     r9, [rcx+18h]
0x1800074eb  mov     r10, [rcx+20h]
0x1800074ef  add     r10, r9
0x1800074f2  mov     r8, [rbp+57h+var_18]
0x1800074f6  test    rcx, rcx
0x1800074f9  jnz     short loc_180007548
0x1800074fb  xor     ecx, ecx
0x1800074fd  xor     edx, edx
0x1800074ff  jmp     short loc_180007556
0x180007501  lea     rdx, aInclude; "#include \""
0x180007508  lea     rcx, [rbp+57h+var_38]; this
0x18000750c  call    ?Append@StringBuilder@Composition@UI@Windows@@QEAAXPEBD@Z; Windows::UI::Composition::StringBuilder::Append(char const *)
0x180007511  mov     rdx, rdi
0x180007514  lea     rcx, [rbp+57h+var_38]
0x180007518  call    ?Append@StringBuilder@Composition@UI@Windows@@QEAAXAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; Windows::UI::Composition::StringBuilder::Append(std::string const &)
0x18000751d  mov     [rbp+57h+arg_10], 22h ; '"'
0x180007521  lea     rdx, [rbp+57h+arg_10]
0x180007525  lea     rcx, [rbp+57h+var_38]
0x180007529  call    ??$_Emplace_back_internal@AEBD@?$deque@DV?$allocator@D@std@@@std@@AEAAXAEBD@Z; std::deque<char>::_Emplace_back_internal<char const &>(char const &)
0x18000752e  mov     [rbp+57h+arg_10], 0Ah
0x180007532  lea     rdx, [rbp+57h+arg_10]
0x180007536  lea     rcx, [rbp+57h+var_38]
0x18000753a  call    ??$_Emplace_back_internal@AEBD@?$deque@DV?$allocator@D@std@@@std@@AEAAXAEBD@Z; std::deque<char>::_Emplace_back_internal<char const &>(char const &)
0x18000753f  add     rdi, 20h ; ' '
0x180007543  jmp     loc_180007444
0x180007548  mov     rdx, [rcx]
0x18000754b  test    rdx, rdx
0x18000754e  jz      short loc_1800074FB
0x180007550  mov     rcx, [rdx]
0x180007553  mov     rdx, rcx
0x180007556  mov     [rbp+57h+var_60], rdx
0x18000755a  mov     [rbp+57h+var_58], r10
0x18000755e  mov     [rbp+57h+var_70], rcx
0x180007562  mov     [rbp+57h+var_68], r9
0x180007566  lea     rax, [rbp+57h+var_60]
0x18000756a  mov     [rsp+0B0h+var_90], rax
0x18000756f  lea     r9, [rbp+57h+var_70]
0x180007573  lea     rdx, [rbp+57h+var_50]
0x180007577  lea     rcx, [rbp+57h+var_38]
0x18000757b  call    ??$_Insert_range@$00V?$_Deque_unchecked_const_iterator@V?$_Deque_val@U?$_Deque_simple_types@D@std@@@std@@@std@@V12@@?$deque@DV?$allocator@D@std@@@std@@AEAA?AV?$_Deque_iterator@V?$_Deque_val@U?$_Deque_simple_types@D@std@@@std@@@1@_KV?$_Deque_unchecked_const_iterator@V?$_Deque_val@U?$_Deque_simple_types@D@std@@@std@@@1@1@Z; std::deque<char>::_Insert_range<1,std::_Deque_unchecked_const_iterator<std::_Deque_val<std::_Deque_simple_types<char>>>,std::_Deque_unchecked_const_iterator<std::_Deque_val<std::_Deque_simple_types<char>>>>(unsigned __int64,std::_Deque_unchecked_const_iterator<std::_Deque_val<std::_Deque_simple_types<char>>>,std::_Deque_unchecked_const_iterator<std::_Deque_val<std::_Deque_simple_types<char>>>)
0x180007580  mov     [rbp+57h+arg_10], 7Dh ; '}'
0x180007584  lea     rdx, [rbp+57h+arg_10]
0x180007588  lea     rcx, [rbp+57h+var_38]
0x18000758c  call    ??$_Emplace_back_internal@AEBD@?$deque@DV?$allocator@D@std@@@std@@AEAAXAEBD@Z; std::deque<char>::_Emplace_back_internal<char const &>(char const &)
0x180007591  mov     [rbp+57h+arg_10], 0Ah
0x180007595  lea     rdx, [rbp+57h+arg_10]
0x180007599  lea     rcx, [rbp+57h+var_38]
0x18000759d  call    ??$_Emplace_back_internal@AEBD@?$deque@DV?$allocator@D@std@@@std@@AEAAXAEBD@Z; std::deque<char>::_Emplace_back_internal<char const &>(char const &)
0x1800075a2  mov     [rbp+57h+arg_10], 0Ah
0x1800075a6  lea     rdx, [rbp+57h+arg_10]
0x1800075aa  lea     rcx, [rbp+57h+var_38]
0x1800075ae  call    ??$_Emplace_back_internal@AEBD@?$deque@DV?$allocator@D@std@@@std@@AEAAXAEBD@Z; std::deque<char>::_Emplace_back_internal<char const &>(char const &)
0x1800075b3  lea     rdx, aExportMinfloat; "export minfloat4 "
0x1800075ba  lea     rcx, [rbp+57h+var_38]; this
0x1800075be  call    ?Append@StringBuilder@Composition@UI@Windows@@QEAAXPEBD@Z; Windows::UI::Composition::StringBuilder::Append(char const *)
0x1800075c3  lea     rdx, Str2; "PSBody"
0x1800075ca  lea     rcx, [rbp+57h+var_38]; this
0x1800075ce  call    ?Append@StringBuilder@Composition@UI@Windows@@QEAAXPEBD@Z; Windows::UI::Composition::StringBuilder::Append(char const *)
0x1800075d3  mov     [rbp+57h+arg_10], 28h ; '('
0x1800075d7  lea     rdx, [rbp+57h+arg_10]
0x1800075db  lea     rcx, [rbp+57h+var_38]
0x1800075df  call    ??$_Emplace_back_internal@AEBD@?$deque@DV?$allocator@D@std@@@std@@AEAAXAEBD@Z; std::deque<char>::_Emplace_back_internal<char const &>(char const &)
0x1800075e4  mov     [rbp+57h+arg_10], 0Ah
0x1800075e8  lea     rdx, [rbp+57h+arg_10]
0x1800075ec  lea     rcx, [rbp+57h+var_38]
0x1800075f0  call    ??$_Emplace_back_internal@AEBD@?$deque@DV?$allocator@D@std@@@std@@AEAAXAEBD@Z; std::deque<char>::_Emplace_back_internal<char const &>(char const &)
0x1800075f5  mov     rdi, [rbx+70h]
0x1800075f9  mov     r14, [rbx+78h]
0x1800075fd  cmp     rdi, r14
0x180007600  jz      short loc_18000762B
0x180007602  lea     rdx, asc_18003403C; "    "
0x180007609  lea     rcx, [rbp+57h+var_38]; this
0x18000760d  call    ?Append@StringBuilder@Composition@UI@Windows@@QEAAXPEBD@Z; Windows::UI::Composition::StringBuilder::Append(char const *)
0x180007612  mov     rdx, rdi
0x180007615  lea     rcx, [rbp+57h+var_38]
0x180007619  call    ?Append@StringBuilder@Composition@UI@Windows@@QEAAXAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; Windows::UI::Composition::StringBuilder::Append(std::string const &)
0x18000761e  add     rdi, 20h ; ' '
0x180007622  cmp     rdi, r14
0x180007625  jnz     loc_1800077D6
0x18000762b  lea     rdx, asc_180034140; ")"
0x180007632  lea     rcx, [rbp+57h+var_38]; this
0x180007636  call    ?Append@StringBuilder@Composition@UI@Windows@@QEAAXPEBD@Z; Windows::UI::Composition::StringBuilder::Append(char const *)
0x18000763b  mov     [rbp+57h+arg_10], 0Ah
0x18000763f  lea     rdx, [rbp+57h+arg_10]
0x180007643  lea     rcx, [rbp+57h+var_38]
0x180007647  call    ??$_Emplace_back_internal@AEBD@?$deque@DV?$allocator@D@std@@@std@@AEAAXAEBD@Z; std::deque<char>::_Emplace_back_internal<char const &>(char const &)
0x18000764c  mov     [rbp+57h+arg_10], 7Bh ; '{'
0x180007650  lea     rdx, [rbp+57h+arg_10]
0x180007654  lea     rcx, [rbp+57h+var_38]
0x180007658  call    ??$_Emplace_back_internal@AEBD@?$deque@DV?$allocator@D@std@@@std@@AEAAXAEBD@Z; std::deque<char>::_Emplace_back_internal<char const &>(char const &)
0x18000765d  mov     [rbp+57h+arg_10], 0Ah
0x180007661  lea     rdx, [rbp+57h+arg_10]
0x180007665  lea     rcx, [rbp+57h+var_38]
0x180007669  call    ??$_Emplace_back_internal@AEBD@?$deque@DV?$allocator@D@std@@@std@@AEAAXAEBD@Z; std::deque<char>::_Emplace_back_internal<char const &>(char const &)
0x18000766e  add     rbx, 88h
0x180007675  mov     r9, [rbx+18h]
0x180007679  mov     r10, [rbx+20h]
0x18000767d  lea     r10, [r10+r9]
0x180007681  mov     r8, [rbp+57h+var_18]
0x180007685  jz      loc_18000775A
0x18000768b  mov     rcx, [rbx]
0x18000768e  mov     rax, rcx
0x180007691  test    rcx, rcx
0x180007694  jz      loc_18000775A
0x18000769a  mov     rcx, [rcx]
0x18000769d  mov     rdx, [rax]
0x1800076a0  mov     [rbp+57h+var_60], rdx
0x1800076a4  mov     [rbp+57h+var_58], r10
0x1800076a8  mov     [rbp+57h+var_70], rcx
0x1800076ac  mov     [rbp+57h+var_68], r9
0x1800076b0  lea     rax, [rbp+57h+var_60]
0x1800076b4  mov     [rsp+0B0h+var_90], rax
0x1800076b9  lea     r9, [rbp+57h+var_70]
0x1800076bd  lea     rdx, [rbp+57h+var_50]
0x1800076c1  lea     rcx, [rbp+57h+var_38]
0x1800076c5  call    ??$_Insert_range@$00V?$_Deque_unchecked_const_iterator@V?$_Deque_val@U?$_Deque_simple_types@D@std@@@std@@@std@@V12@@?$deque@DV?$allocator@D@std@@@std@@AEAA?AV?$_Deque_iterator@V?$_Deque_val@U?$_Deque_simple_types@D@std@@@std@@@1@_KV?$_Deque_unchecked_const_iterator@V?$_Deque_val@U?$_Deque_simple_types@D@std@@@std@@@1@1@Z; std::deque<char>::_Insert_range<1,std::_Deque_unchecked_const_iterator<std::_Deque_val<std::_Deque_simple_types<char>>>,std::_Deque_unchecked_const_iterator<std::_Deque_val<std::_Deque_simple_types<char>>>>(unsigned __int64,std::_Deque_unchecked_const_iterator<std::_Deque_val<std::_Deque_simple_types<char>>>,std::_Deque_unchecked_const_iterator<std::_Deque_val<std::_Deque_simple_types<char>>>)
0x1800076ca  mov     [rbp+57h+arg_10], 7Dh ; '}'
0x1800076ce  lea     rdx, [rbp+57h+arg_10]
0x1800076d2  lea     rcx, [rbp+57h+var_38]
0x1800076d6  call    ??$_Emplace_back_internal@AEBD@?$deque@DV?$allocator@D@std@@@std@@AEAAXAEBD@Z; std::deque<char>::_Emplace_back_internal<char const &>(char const &)
0x1800076db  mov     [rbp+57h+arg_10], 0Ah
0x1800076df  lea     rdx, [rbp+57h+arg_10]
0x1800076e3  lea     rcx, [rbp+57h+var_38]
0x1800076e7  call    ??$_Emplace_back_internal@AEBD@?$deque@DV?$allocator@D@std@@@std@@AEAAXAEBD@Z; std::deque<char>::_Emplace_back_internal<char const &>(char const &)
0x1800076ec  mov     rcx, qword ptr [rbp+57h+var_28+8]
0x1800076f0  mov     r9, [rbp+57h+var_18]
0x1800076f4  add     r9, rcx
0x1800076f7  mov     rax, qword ptr [rbp+57h+var_38]
0x1800076fb  xorps   xmm0, xmm0
0x1800076fe  movups  xmmword ptr [rsi], xmm0
0x180007701  mov     qword ptr [rsi+10h], 0
0x180007709  mov     qword ptr [rsi+18h], 0
0x180007711  test    rax, rax
0x180007714  jz      short loc_180007719
0x180007716  mov     rax, [rax]
0x180007719  cmp     rcx, r9
0x18000771c  jz      short loc_180007763
0x18000771e  mov     [rbp+57h+var_60], rax
0x180007722  mov     [rbp+57h+var_58], rcx
0x180007726  sub     r9, rcx
0x180007729  lea     rdx, [rbp+57h+var_60]
0x18000772d  mov     rcx, rsi
0x180007730  call    ??$_Construct_from_iter@V?$_Deque_unchecked_const_iterator@V?$_Deque_val@U?$_Deque_simple_types@D@std@@@std@@@std@@V12@_K@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXV?$_Deque_unchecked_const_iterator@V?$_Deque_val@U?$_Deque_simple_types@D@std@@@std@@@1@V21@_K@Z; std::string::_Construct_from_iter<std::_Deque_unchecked_const_iterator<std::_Deque_val<std::_Deque_simple_types<char>>>,std::_Deque_unchecked_const_iterator<std::_Deque_val<std::_Deque_simple_types<char>>>,unsigned __int64>(std::_Deque_unchecked_const_iterator<std::_Deque_val<std::_Deque_simple_types<char>>>,std::_Deque_unchecked_const_iterator<std::_Deque_val<std::_Deque_simple_types<char>>>,unsigned __int64)
0x180007735  nop
0x180007736  lea     rcx, [rbp+57h+var_38]; this
0x18000773a  call    ??1StringBuilder@Composition@UI@Windows@@QEAA@XZ; Windows::UI::Composition::StringBuilder::~StringBuilder(void)
0x18000773f  mov     rax, rsi
0x180007742  lea     r11, [rsp+0B0h+var_10]
0x18000774a  mov     rbx, [r11+20h]
0x18000774e  mov     rsi, [r11+28h]
0x180007752  mov     rsp, r11
0x180007755  pop     r14
0x180007757  pop     rdi
0x180007758  pop     rbp
0x180007759  retn
0x18000775a  xor     ecx, ecx
0x18000775c  xor     edx, edx
0x18000775e  jmp     loc_1800076A0
0x180007763  mov     rcx, rsi
0x180007766  call    ?_Construct_empty@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Construct_empty(void)
0x18000776b  jmp     short loc_180007736
0x18000776d  xor     eax, eax
0x18000776f  xor     edx, edx
0x180007771  mov     [rbp+57h+var_70], rdx
0x180007775  mov     [rbp+57h+var_68], r10
0x180007779  mov     [rbp+57h+var_60], rax
0x18000777d  mov     [rbp+57h+var_58], r9
0x180007781  lea     rax, [rbp+57h+var_70]
0x180007785  mov     [rsp+0B0h+var_90], rax
0x18000778a  lea     r9, [rbp+57h+var_60]
0x18000778e  lea     rdx, [rbp+57h+var_50]
0x180007792  lea     rcx, [rbp+57h+var_38]
0x180007796  call    ??$_Insert_range@$00V?$_Deque_unchecked_const_iterator@V?$_Deque_val@U?$_Deque_simple_types@D@std@@@std@@@std@@V12@@?$deque@DV?$allocator@D@std@@@std@@AEAA?AV?$_Deque_iterator@V?$_Deque_val@U?$_Deque_simple_types@D@std@@@std@@@1@_KV?$_Deque_unchecked_const_iterator@V?$_Deque_val@U?$_Deque_simple_types@D@std@@@std@@@1@1@Z; std::deque<char>::_Insert_range<1,std::_Deque_unchecked_const_iterator<std::_Deque_val<std::_Deque_simple_types<char>>>,std::_Deque_unchecked_const_iterator<std::_Deque_val<std::_Deque_simple_types<char>>>>(unsigned __int64,std::_Deque_unchecked_const_iterator<std::_Deque_val<std::_Deque_simple_types<char>>>,std::_Deque_unchecked_const_iterator<std::_Deque_val<std::_Deque_simple_types<char>>>)
0x18000779b  mov     [rbp+57h+arg_10], 0Ah
0x18000779f  lea     rdx, [rbp+57h+arg_10]
0x1800077a3  lea     rcx, [rbp+57h+var_38]
0x1800077a7  call    ?push_back@?$deque@DV?$allocator@D@std@@@std@@QEAAXAEBD@Z; std::deque<char>::push_back(char const &)
0x1800077ac  jmp     loc_180007475
0x1800077b1  lea     rax, [rbx+20h]
0x1800077b5  mov     r9, [rax+18h]
0x1800077b9  lea     r10, [r9+rcx]
0x1800077bd  mov     r8, [rbp+57h+var_18]
0x1800077c1  test    rax, rax
0x1800077c4  jz      short loc_18000776D
0x1800077c6  mov     rdx, [rax]
0x1800077c9  test    rdx, rdx
0x1800077cc  jz      short loc_18000776D
0x1800077ce  mov     rax, [rdx]
0x1800077d1  mov     rdx, rax
0x1800077d4  jmp     short loc_180007771
0x1800077d6  mov     [rbp+57h+arg_10], 2Ch ; ','
0x1800077da  lea     rdx, [rbp+57h+arg_10]
0x1800077de  lea     rcx, [rbp+57h+var_38]
0x1800077e2  call    ?push_back@?$deque@DV?$allocator@D@std@@@std@@QEAAXAEBD@Z; std::deque<char>::push_back(char const &)
0x1800077e7  mov     [rbp+57h+arg_10], 0Ah
0x1800077eb  lea     rdx, [rbp+57h+arg_10]
0x1800077ef  lea     rcx, [rbp+57h+var_38]
0x1800077f3  call    ?push_back@?$deque@DV?$allocator@D@std@@@std@@QEAAXAEBD@Z; std::deque<char>::push_back(char const &)
0x1800077f8  jmp     loc_180007602
```
