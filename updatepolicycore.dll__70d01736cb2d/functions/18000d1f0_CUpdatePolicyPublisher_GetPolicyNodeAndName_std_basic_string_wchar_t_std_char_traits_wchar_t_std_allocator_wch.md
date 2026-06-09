# CUpdatePolicyPublisher::GetPolicyNodeAndName(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &)

- ea: `0x18000d1f0`
- end: `0x18000d580`
- name: `?GetPolicyNodeAndName@CUpdatePolicyPublisher@@AEAAJV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0AEAV23@1@Z`
- size: `912`
- prototype: `__int64 __fastcall(unsigned __int64, _QWORD *, _QWORD *, void *, void *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18000d590`

## callees

- `0x18000aac0`
- `0x18000d1f0`
- `0x18000e8cc`
- `0x18000f018`
- `0x18000f27c`
- `0x18000f860`
- `0x18000fcc4`
- `0x180010260`
- `0x18002e120`
- `0x18002ffd0`
- `0x180036a90`

## string_xrefs

- `0x18000d44c`: `C:\__w\1\s\src\Client\policy\src\ComApi\UpdatePolicyApi.cpp`

## pseudocode

```c
__int64 __fastcall CUpdatePolicyPublisher::GetPolicyNodeAndName(
        unsigned __int64 a1,
        _QWORD *a2,
        _QWORD *a3,
        void *a4,
        void *a5)
{
  _QWORD *v5; // r12
  unsigned __int64 v7; // r15
  unsigned __int64 v8; // r9
  unsigned __int64 v9; // rax
  _QWORD *v10; // r13
  __int64 v11; // rdi
  char *v12; // rbx
  __int64 traits_2_unsigned_short; // rax
  __m128i si128; // xmm6
  __m128i *v15; // rdx
  unsigned __int64 v16; // r9
  _QWORD *v17; // r13
  char *v18; // rbx
  __int64 v19; // rax
  unsigned __int64 v20; // rax
  __m128i *v21; // rdx
  __int64 v22; // r8
  _QWORD *v23; // rdx
  unsigned __int64 v25; // rax
  char *v26; // rdi
  __int64 v27; // rbx
  _QWORD *v28; // r9
  unsigned __int64 v29; // rdx
  char *v30; // rdi
  __int64 v31; // rbx
  __int128 v32; // [rsp+28h] [rbp-61h] BYREF
  __m128i v33; // [rsp+38h] [rbp-51h]
  void *v34; // [rsp+50h] [rbp-39h]
  void *v35; // [rsp+58h] [rbp-31h]
  _QWORD *v36; // [rsp+60h] [rbp-29h]
  _QWORD *v37; // [rsp+68h] [rbp-21h]
  __int128 v38; // [rsp+70h] [rbp-19h] BYREF
  __int64 v39; // [rsp+80h] [rbp-9h]
  wil::details::in1diag3 *retaddr; // [rsp+E0h] [rbp+57h]

  v34 = a4;
  v5 = a3;
  v35 = a5;
  v36 = a2;
  v37 = a3;
  v7 = 0;
  v8 = a3[2];
  if ( a3[3] > 7u )
    a3 = (_QWORD *)*a3;
  v9 = a2[2];
  v10 = a2;
  if ( a2[3] > 7u )
    v10 = (_QWORD *)*a2;
  if ( v8 > v9 )
    goto LABEL_10;
  if ( v8 )
  {
    v12 = (char *)v10 + 2 * v9;
    traits_2_unsigned_short = anonymous_namespace_::__std_search_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                                v10,
                                v12,
                                a3);
    if ( (char *)traits_2_unsigned_short != v12 )
    {
      v11 = (traits_2_unsigned_short - (__int64)v10) >> 1;
      goto LABEL_11;
    }
LABEL_10:
    v11 = -1;
    goto LABEL_11;
  }
  v11 = 0;
LABEL_11:
  v38 = 0;
  v39 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  while ( 1 )
  {
    v20 = a2[2];
    v32 = 0;
    v33 = 0;
    if ( v11 == -1 )
      break;
    if ( v20 < v7 )
      goto LABEL_51;
    std::wstring::_Construct<1,wchar_t const *>(&v32);
    v15 = (__m128i *)*((_QWORD *)&v38 + 1);
    if ( *((_QWORD *)&v38 + 1) == v39 )
    {
      std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(&v38, *((_QWORD *)&v38 + 1), &v32);
    }
    else
    {
      **((_OWORD **)&v38 + 1) = v32;
      v15[1] = v33;
      v33 = si128;
      LOWORD(v32) = 0;
      *((_QWORD *)&v38 + 1) += 32LL;
    }
    std::wstring::~wstring(&v32);
    v7 = v11 + 1;
    v16 = v5[2];
    a3 = v5;
    if ( v5[3] > 7u )
      a3 = (_QWORD *)*v5;
    a1 = a2[2];
    v17 = a2;
    if ( a2[3] > 7u )
      v17 = (_QWORD *)*a2;
    if ( v16 > a1 || v7 > a1 - v16 )
    {
LABEL_26:
      v11 = -1;
    }
    else if ( v16 )
    {
      v18 = (char *)v17 + 2 * a1;
      v19 = anonymous_namespace_::__std_search_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
              (char *)v17 + 2 * v7,
              v18,
              a3);
      if ( (char *)v19 == v18 )
        goto LABEL_26;
      v11 = (v19 - (__int64)v17) >> 1;
    }
    else
    {
      ++v11;
    }
  }
  if ( v20 < v7 )
LABEL_51:
    std::_String_val<std::_Simple_types<wchar_t>>::_Xran(a1, a2, a3);
  std::wstring::_Construct<1,wchar_t const *>(&v32);
  v21 = (__m128i *)*((_QWORD *)&v38 + 1);
  if ( *((_QWORD *)&v38 + 1) == v39 )
  {
    std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(&v38, *((_QWORD *)&v38 + 1), &v32);
  }
  else
  {
    **((_OWORD **)&v38 + 1) = v32;
    v21[1] = v33;
    v33 = si128;
    LOWORD(v32) = 0;
    *((_QWORD *)&v38 + 1) += 32LL;
  }
  std::wstring::~wstring(&v32);
  v23 = (_QWORD *)v38;
  if ( *((_QWORD *)&v38 + 1) - (_QWORD)v38 == 64 )
  {
    if ( v34 != (void *)v38 )
    {
      v25 = *(_QWORD *)(v38 + 16);
      if ( *(_QWORD *)(v38 + 24) > 7u )
        v23 = *(_QWORD **)v38;
      if ( v25 > *((_QWORD *)v34 + 3) )
      {
        std::wstring::_Reallocate_for<_lambda_3fa8b2c8193a0f3144fc4b1b8f243931_,wchar_t const *>(v34, v25, v22, v23);
        v23 = (_QWORD *)v38;
      }
      else
      {
        v26 = (char *)v34;
        if ( *((_QWORD *)v34 + 3) > 7u )
          v26 = *(char **)v34;
        *((_QWORD *)v34 + 2) = v25;
        v27 = 2 * v25;
        memmove(v26, v23, 2 * v25);
        *(_WORD *)&v26[v27] = 0;
        v23 = (_QWORD *)v38;
      }
    }
    v28 = v23 + 4;
    if ( v35 != v23 + 4 )
    {
      v29 = v23[6];
      if ( v28[3] > 7u )
        v28 = (_QWORD *)*v28;
      if ( v29 > *((_QWORD *)v35 + 3) )
      {
        std::wstring::_Reallocate_for<_lambda_3fa8b2c8193a0f3144fc4b1b8f243931_,wchar_t const *>(v35, v29, v22, v28);
      }
      else
      {
        v30 = (char *)v35;
        if ( *((_QWORD *)v35 + 3) > 7u )
          v30 = *(char **)v35;
        *((_QWORD *)v35 + 2) = v29;
        v31 = 2 * v29;
        memmove(v30, v28, 2 * v29);
        *(_WORD *)&v30[v31] = 0;
      }
    }
    std::vector<std::wstring>::_Tidy(&v38);
    std::wstring::~wstring(a2);
    std::wstring::~wstring(v5);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x16B,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\policy\\src\\ComApi\\UpdatePolicyApi.cpp",
      (const char *)0x80070057LL,
      v32);
    std::vector<std::wstring>::_Tidy(&v38);
    std::wstring::~wstring(a2);
    std::wstring::~wstring(v5);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x18000d1f0  mov     rax, rsp
0x18000d1f3  mov     [rax+8], rbx
0x18000d1f7  push    rbp
0x18000d1f8  push    rsi
0x18000d1f9  push    rdi
0x18000d1fa  push    r12
0x18000d1fc  push    r13
0x18000d1fe  push    r14
0x18000d200  push    r15
0x18000d202  lea     rbp, [rax-57h]
0x18000d206  sub     rsp, 0A0h
0x18000d20d  movaps  xmmword ptr [rax-48h], xmm6
0x18000d211  mov     rax, cs:__security_cookie
0x18000d218  xor     rax, rsp
0x18000d21b  mov     [rbp+4Fh+var_50], rax
0x18000d21f  mov     [rbp+4Fh+var_88], r9
0x18000d223  mov     r12, r8
0x18000d226  mov     rsi, rdx
0x18000d229  mov     rax, [rbp+4Fh+arg_20]
0x18000d22d  mov     [rbp+4Fh+var_80], rax
0x18000d231  mov     [rbp+4Fh+var_78], rdx
0x18000d235  mov     [rbp+4Fh+var_70], r8
0x18000d239  xor     ebx, ebx
0x18000d23b  mov     r15d, ebx
0x18000d23e  mov     r9, [r8+10h]
0x18000d242  cmp     qword ptr [r8+18h], 7
0x18000d247  jbe     short loc_18000D24C
0x18000d249  mov     r8, [r8]
0x18000d24c  mov     rax, [rdx+10h]
0x18000d250  mov     r13, rsi
0x18000d253  cmp     qword ptr [rdx+18h], 7
0x18000d258  jbe     short loc_18000D25D
0x18000d25a  mov     r13, [rdx]
0x18000d25d  or      r14, 0FFFFFFFFFFFFFFFFh
0x18000d261  cmp     r9, rax
0x18000d264  ja      short loc_18000D29A
0x18000d266  test    r9, r9
0x18000d269  jnz     short loc_18000D270
0x18000d26b  mov     rdi, rbx
0x18000d26e  jmp     short loc_18000D29D
0x18000d270  lea     rbx, ds:0[rax*2]
0x18000d278  add     rbx, r13
0x18000d27b  mov     rdx, rbx
0x18000d27e  mov     rcx, r13
0x18000d281  call    _anonymous_namespace_____std_search_impl__anonymous_namespace____Find_traits_2_unsigned_short_
0x18000d286  mov     rdi, rax
0x18000d289  cmp     rax, rbx
0x18000d28c  jz      short loc_18000D298
0x18000d28e  sub     rdi, r13
0x18000d291  sar     rdi, 1
0x18000d294  xor     ebx, ebx
0x18000d296  jmp     short loc_18000D29D
0x18000d298  xor     ebx, ebx
0x18000d29a  mov     rdi, r14
0x18000d29d  xorps   xmm1, xmm1
0x18000d2a0  movdqu  [rbp+4Fh+var_68], xmm1
0x18000d2a5  mov     [rbp+4Fh+var_58], rbx
0x18000d2a9  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x18000d2b1  jmp     loc_18000D3A2
0x18000d2b6  cmp     rax, r15
0x18000d2b9  jb      loc_18000D57A
0x18000d2bf  mov     r8, rdi
0x18000d2c2  sub     r8, r15
0x18000d2c5  sub     rax, r15
0x18000d2c8  cmp     rax, r8
0x18000d2cb  cmovb   r8, rax
0x18000d2cf  mov     rax, rsi
0x18000d2d2  cmp     qword ptr [rsi+18h], 7
0x18000d2d7  jbe     short loc_18000D2DC
0x18000d2d9  mov     rax, [rsi]
0x18000d2dc  lea     rdx, [rax+r15*2]
0x18000d2e0  lea     rcx, [rbp+4Fh+var_B0]
0x18000d2e4  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18000d2e9  nop
0x18000d2ea  mov     rdx, qword ptr [rbp+4Fh+var_68+8]
0x18000d2ee  cmp     rdx, [rbp+4Fh+var_58]
0x18000d2f2  jz      short loc_18000D313
0x18000d2f4  movups  xmm0, [rbp+4Fh+var_B0]
0x18000d2f8  movups  xmmword ptr [rdx], xmm0
0x18000d2fb  movups  xmm1, [rbp+4Fh+var_A0]
0x18000d2ff  movups  xmmword ptr [rdx+10h], xmm1
0x18000d303  movdqu  [rbp+4Fh+var_A0], xmm6
0x18000d308  mov     word ptr [rbp+4Fh+var_B0], bx
0x18000d30c  add     qword ptr [rbp+4Fh+var_68+8], 20h ; ' '
0x18000d311  jmp     short loc_18000D321
0x18000d313  lea     r8, [rbp+4Fh+var_B0]
0x18000d317  lea     rcx, [rbp+4Fh+var_68]
0x18000d31b  call    ??$_Emplace_reallocate@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAPEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x18000d320  nop
0x18000d321  lea     rcx, [rbp+4Fh+var_B0]; void *
0x18000d325  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000d32a  lea     r15, [rdi+1]
0x18000d32e  mov     r9, [r12+10h]
0x18000d333  mov     r8, r12
0x18000d336  cmp     qword ptr [r12+18h], 7
0x18000d33c  jbe     short loc_18000D342
0x18000d33e  mov     r8, [r12]
0x18000d342  mov     rcx, [rsi+10h]
0x18000d346  mov     r13, rsi
0x18000d349  cmp     qword ptr [rsi+18h], 7
0x18000d34e  jbe     short loc_18000D353
0x18000d350  mov     r13, [rsi]
0x18000d353  cmp     r9, rcx
0x18000d356  ja      short loc_18000D39F
0x18000d358  mov     rax, rcx
0x18000d35b  sub     rax, r9
0x18000d35e  cmp     r15, rax
0x18000d361  ja      short loc_18000D39F
0x18000d363  test    r9, r9
0x18000d366  jnz     short loc_18000D36D
0x18000d368  mov     rdi, r15
0x18000d36b  jmp     short loc_18000D3A2
0x18000d36d  lea     rbx, ds:0[rcx*2]
0x18000d375  add     rbx, r13
0x18000d378  lea     rcx, ds:0[r15*2]
0x18000d380  add     rcx, r13
0x18000d383  mov     rdx, rbx
0x18000d386  call    _anonymous_namespace_____std_search_impl__anonymous_namespace____Find_traits_2_unsigned_short_
0x18000d38b  mov     rdi, rax
0x18000d38e  cmp     rax, rbx
0x18000d391  jz      short loc_18000D39D
0x18000d393  sub     rdi, r13
0x18000d396  sar     rdi, 1
0x18000d399  xor     ebx, ebx
0x18000d39b  jmp     short loc_18000D3A2
0x18000d39d  xor     ebx, ebx
0x18000d39f  mov     rdi, r14
0x18000d3a2  xorps   xmm0, xmm0
0x18000d3a5  xorps   xmm1, xmm1
0x18000d3a8  mov     rax, [rsi+10h]
0x18000d3ac  movups  [rbp+4Fh+var_B0], xmm0
0x18000d3b0  movdqu  [rbp+4Fh+var_A0], xmm1
0x18000d3b5  cmp     rdi, r14
0x18000d3b8  jnz     loc_18000D2B6
0x18000d3be  cmp     rax, r15
0x18000d3c1  jb      loc_18000D57A
0x18000d3c7  sub     rax, r15
0x18000d3ca  cmp     rax, r14
0x18000d3cd  cmovb   r14, rax
0x18000d3d1  mov     rax, rsi
0x18000d3d4  cmp     qword ptr [rsi+18h], 7
0x18000d3d9  jbe     short loc_18000D3DE
0x18000d3db  mov     rax, [rsi]
0x18000d3de  lea     rdx, [rax+r15*2]
0x18000d3e2  mov     r8, r14
0x18000d3e5  lea     rcx, [rbp+4Fh+var_B0]
0x18000d3e9  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18000d3ee  nop
0x18000d3ef  mov     rdx, qword ptr [rbp+4Fh+var_68+8]
0x18000d3f3  cmp     rdx, [rbp+4Fh+var_58]
0x18000d3f7  jz      short loc_18000D418
0x18000d3f9  movups  xmm0, [rbp+4Fh+var_B0]
0x18000d3fd  movups  xmmword ptr [rdx], xmm0
0x18000d400  movups  xmm1, [rbp+4Fh+var_A0]
0x18000d404  movups  xmmword ptr [rdx+10h], xmm1
0x18000d408  movdqu  [rbp+4Fh+var_A0], xmm6
0x18000d40d  mov     word ptr [rbp+4Fh+var_B0], bx
0x18000d411  add     qword ptr [rbp+4Fh+var_68+8], 20h ; ' '
0x18000d416  jmp     short loc_18000D426
0x18000d418  lea     r8, [rbp+4Fh+var_B0]
0x18000d41c  lea     rcx, [rbp+4Fh+var_68]
0x18000d420  call    ??$_Emplace_reallocate@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAPEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x18000d425  nop
0x18000d426  lea     rcx, [rbp+4Fh+var_B0]; void *
0x18000d42a  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000d42f  mov     rax, qword ptr [rbp+4Fh+var_68+8]
0x18000d433  mov     rdx, qword ptr [rbp+4Fh+var_68]
0x18000d437  sub     rax, rdx
0x18000d43a  cmp     rax, 40h ; '@'
0x18000d43e  jz      short loc_18000D480
0x18000d440  mov     rcx, [rbp+57h]; this
0x18000d444  mov     ebx, 80070057h
0x18000d449  mov     r9d, ebx; char *
0x18000d44c  lea     r8, aCW1SSrcClientP_7; "C:\\__w\\1\\s\\src\\Client\\policy\\src"...
0x18000d453  mov     edx, 16Bh; void *
0x18000d458  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d45d  nop
0x18000d45e  lea     rcx, [rbp+4Fh+var_68]
0x18000d462  call    ?_Tidy@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18000d467  nop
0x18000d468  mov     rcx, rsi; void *
0x18000d46b  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000d470  nop
0x18000d471  mov     rcx, r12; void *
0x18000d474  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000d479  mov     eax, ebx
0x18000d47b  jmp     loc_18000D54E
0x18000d480  mov     rcx, [rbp+4Fh+var_88]
0x18000d484  cmp     rcx, rdx
0x18000d487  jz      short loc_18000D4DA
0x18000d489  mov     rax, [rdx+10h]
0x18000d48d  cmp     qword ptr [rdx+18h], 7
0x18000d492  jbe     short loc_18000D497
0x18000d494  mov     rdx, [rdx]; Src
0x18000d497  cmp     rax, [rcx+18h]
0x18000d49b  ja      short loc_18000D4CB
0x18000d49d  mov     rdi, rcx
0x18000d4a0  cmp     qword ptr [rcx+18h], 7
0x18000d4a5  jbe     short loc_18000D4AA
0x18000d4a7  mov     rdi, [rcx]
0x18000d4aa  mov     [rcx+10h], rax
0x18000d4ae  lea     rbx, [rax+rax]
0x18000d4b2  mov     r8, rbx; Size
0x18000d4b5  mov     rcx, rdi; void *
0x18000d4b8  call    memmove
0x18000d4bd  xor     r14d, r14d
0x18000d4c0  mov     [rdi+rbx], r14w
0x18000d4c5  mov     rdx, qword ptr [rbp+4Fh+var_68]
0x18000d4c9  jmp     short loc_18000D4DD
0x18000d4cb  mov     r9, rdx
0x18000d4ce  mov     rdx, rax
0x18000d4d1  call    ??$_Reallocate_for@V_lambda_3fa8b2c8193a0f3144fc4b1b8f243931_@@PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_3fa8b2c8193a0f3144fc4b1b8f243931_@@PEB_W@Z; std::wstring::_Reallocate_for<_lambda_3fa8b2c8193a0f3144fc4b1b8f243931_,wchar_t const *>(unsigned __int64,_lambda_3fa8b2c8193a0f3144fc4b1b8f243931_,wchar_t const *)
0x18000d4d6  mov     rdx, qword ptr [rbp+4Fh+var_68]
0x18000d4da  xor     r14d, r14d
0x18000d4dd  lea     r9, [rdx+20h]
0x18000d4e1  mov     rax, [rbp+4Fh+var_80]
0x18000d4e5  cmp     rax, r9
0x18000d4e8  jz      short loc_18000D531
0x18000d4ea  mov     rdx, [r9+10h]
0x18000d4ee  cmp     qword ptr [r9+18h], 7
0x18000d4f3  jbe     short loc_18000D4F8
0x18000d4f5  mov     r9, [r9]
0x18000d4f8  cmp     rdx, [rax+18h]
0x18000d4fc  ja      short loc_18000D528
0x18000d4fe  mov     rdi, rax
0x18000d501  cmp     qword ptr [rax+18h], 7
0x18000d506  jbe     short loc_18000D50B
0x18000d508  mov     rdi, [rax]
0x18000d50b  mov     [rax+10h], rdx
0x18000d50f  lea     rbx, [rdx+rdx]
0x18000d513  mov     r8, rbx; Size
0x18000d516  mov     rdx, r9; Src
0x18000d519  mov     rcx, rdi; void *
0x18000d51c  call    memmove
0x18000d521  mov     [rdi+rbx], r14w
0x18000d526  jmp     short loc_18000D531
0x18000d528  mov     rcx, rax
0x18000d52b  call    ??$_Reallocate_for@V_lambda_3fa8b2c8193a0f3144fc4b1b8f243931_@@PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_3fa8b2c8193a0f3144fc4b1b8f243931_@@PEB_W@Z; std::wstring::_Reallocate_for<_lambda_3fa8b2c8193a0f3144fc4b1b8f243931_,wchar_t const *>(unsigned __int64,_lambda_3fa8b2c8193a0f3144fc4b1b8f243931_,wchar_t const *)
0x18000d530  nop
0x18000d531  lea     rcx, [rbp+4Fh+var_68]
0x18000d535  call    ?_Tidy@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18000d53a  nop
0x18000d53b  mov     rcx, rsi; void *
0x18000d53e  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000d543  nop
0x18000d544  mov     rcx, r12; void *
0x18000d547  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000d54c  xor     eax, eax
0x18000d54e  mov     rcx, [rbp+4Fh+var_50]
0x18000d552  xor     rcx, rsp; StackCookie
0x18000d555  call    __security_check_cookie
0x18000d55a  lea     r11, [rsp+0D0h+var_30]
0x18000d562  mov     rbx, [r11+40h]
0x18000d566  movaps  xmm6, xmmword ptr [r11-10h]
0x18000d56b  mov     rsp, r11
0x18000d56e  pop     r15
0x18000d570  pop     r14
0x18000d572  pop     r13
0x18000d574  pop     r12
0x18000d576  pop     rdi
0x18000d577  pop     rsi
0x18000d578  pop     rbp
0x18000d579  retn
0x18000d57a  call    ?_Xran@?$_String_val@U?$_Simple_types@_W@std@@@std@@SAXXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Xran(void)
```
