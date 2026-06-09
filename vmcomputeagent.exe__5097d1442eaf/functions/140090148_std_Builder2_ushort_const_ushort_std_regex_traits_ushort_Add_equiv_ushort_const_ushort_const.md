# std::_Builder2<ushort const *,ushort,std::regex_traits<ushort>>::_Add_equiv(ushort const *,ushort const *)

- ea: `0x140090148`
- end: `0x1400904d3`
- name: `?_Add_equiv@?$_Builder2@PEBGGV?$regex_traits@G@std@@@std@@QEAAXPEBG0@Z`
- size: `907`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x140092520`

## callees

- `0x140005360`
- `0x1400056fc`
- `0x140005e70`
- `0x140006788`
- `0x140008760`
- `0x14001e4f4`
- `0x14003ab90`
- `0x14003bc74`
- `0x140090148`
- `0x140091738`

## import_xrefs

- `msvcp_win!?_Xregex_error@std@@YAXW4error_type@regex_constants@1@@Z` at `0x1400904cc`
- `msvcp_win!?_Xregex_error@std@@YAXW4error_type@regex_constants@1@@Z` at `0x1400904cc`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x1400901e0`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x140090308`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x1400901e0`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x140090308`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x1400901f4`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x140090208`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x14009031c`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x140090330`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x1400901f4`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x140090208`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x14009031c`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x140090330`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall std::_Builder2<unsigned short const *,unsigned short,std::regex_traits<unsigned short>>::_Add_equiv(
        char *a1,
        _BYTE *a2,
        _BYTE *a3)
{
  _QWORD *v6; // rdi
  unsigned int v7; // r14d
  __int64 v8; // r15
  __int64 v9; // rbx
  __int64 v10; // r15
  wchar_t **v11; // rcx
  unsigned __int64 v12; // rax
  unsigned int v13; // esi
  char *v14; // r12
  _QWORD *v15; // rcx
  int v16; // r14d
  __int64 v17; // r13
  __int64 v18; // rbx
  __int128 *v19; // r15
  __int64 v20; // r13
  wchar_t **v21; // rcx
  size_t v22; // rax
  const wchar_t *v23; // rdx
  const wchar_t *v24; // rcx
  bool v25; // bl
  __int64 v26; // rcx
  _OWORD *v27; // rdx
  unsigned __int64 v28; // r9
  __int16 v29[2]; // [rsp+30h] [rbp-69h] BYREF
  int v30; // [rsp+34h] [rbp-65h]
  char *v31; // [rsp+38h] [rbp-61h]
  _BYTE *v32; // [rsp+40h] [rbp-59h]
  const void *v33; // [rsp+48h] [rbp-51h]
  wchar_t *S1[2]; // [rsp+50h] [rbp-49h] BYREF
  size_t N; // [rsp+60h] [rbp-39h]
  unsigned __int64 v36; // [rsp+68h] [rbp-31h]
  wchar_t *S2[2]; // [rsp+70h] [rbp-29h] BYREF
  size_t v38; // [rsp+80h] [rbp-19h]
  unsigned __int64 v39; // [rsp+88h] [rbp-11h]
  __int128 v40; // [rsp+90h] [rbp-9h] BYREF
  size_t v41; // [rsp+A0h] [rbp+7h]
  unsigned __int64 v42; // [rsp+A8h] [rbp+Fh]

  v32 = a3;
  v33 = a2;
  v31 = a1;
  v30 = 0;
  v6 = (_QWORD *)*((_QWORD *)a1 + 1);
  if ( v6 )
    _castguard_slow_path_check_fastfail(*v6, 168, 0);
  *(_OWORD *)S2 = 0;
  v38 = 0;
  v39 = 7;
  LOWORD(S2[0]) = 0;
  v7 = 1;
  v30 = 1;
  if ( a2 == a3 )
    goto LABEL_41;
  v8 = **((_QWORD **)a1 + 3);
  v9 = __RTtypeid(v8) + 8;
  if ( !(unsigned int)__std_type_info_compare(v9, &qword_140157C08)
    || !(unsigned int)__std_type_info_compare(v9, &qword_140157C38) )
  {
    *(_OWORD *)S1 = 0;
    N = 0;
    v36 = 0;
    std::wstring::_Construct<1,unsigned short const *>((__int64)S1, a2, (a3 - a2) >> 1);
    if ( v38 < N )
    {
      v10 = v8 + 16;
      do
      {
        std::wstring::resize(S2);
        v11 = S2;
        if ( v39 > 7 )
          v11 = (wchar_t **)S2[0];
        v12 = _std_regex_transform_primary_wchar_t(v11, v10);
      }
      while ( v12 != -1 && v38 < v12 );
    }
    std::wstring::resize(S2);
    std::wstring::~wstring(S1);
  }
  if ( !v38 )
  {
LABEL_41:
    std::_Xregex_error(0);
    JUMPOUT(0x1400904D2LL);
  }
  v13 = 0;
  v14 = v31;
  do
  {
    v29[0] = v13;
    v15 = (_QWORD *)*((_QWORD *)v14 + 3);
    *(_OWORD *)S1 = 0;
    N = 0;
    v36 = 7;
    LOWORD(S1[0]) = 0;
    v16 = v7 | 2;
    v30 = v16;
    v17 = *v15;
    v18 = __RTtypeid(*v15) + 8;
    if ( !(unsigned int)__std_type_info_compare(v18, &qword_140157C08)
      || !(unsigned int)__std_type_info_compare(v18, &qword_140157C38) )
    {
      v40 = 0;
      v41 = 0;
      v42 = 0;
      std::wstring::_Construct<1,unsigned short const *>((__int64)&v40, v29, 1u);
      v19 = &v40;
      if ( v42 > 7 )
        v19 = (__int128 *)v40;
      v31 = (char *)v19 + 2 * v41;
      if ( N < v41 )
      {
        v20 = v17 + 16;
        do
        {
          std::wstring::resize(S1);
          v21 = S1;
          if ( v36 > 7 )
            v21 = (wchar_t **)S1[0];
          v22 = _std_regex_transform_primary_wchar_t(v21, v20);
        }
        while ( v22 != -1 && N < v22 );
      }
      std::wstring::resize(S1);
      std::wstring::~wstring(&v40);
    }
    v23 = (const wchar_t *)S2;
    if ( v39 > 7 )
      v23 = S2[0];
    v24 = (const wchar_t *)S1;
    if ( v36 > 7 )
      v24 = S1[0];
    if ( N == v38 )
    {
      if ( N )
        v25 = wmemcmp(v24, v23, N) == 0;
      else
        v25 = 1;
    }
    else
    {
      v25 = 0;
    }
    v7 = v16 & 0xFFFFFFFD;
    v30 = v7;
    std::wstring::~wstring(S1);
    if ( v25 )
    {
      v27 = (_OWORD *)v6[5];
      if ( !v27 )
      {
        v27 = operator new(0x20u);
        *v27 = 0;
        v27[1] = 0;
        v6[5] = v27;
      }
      v28 = (unsigned __int64)v13 >> 3;
      v26 = *((unsigned __int8 *)v27 + v28);
      LODWORD(v26) = v26 | (1 << (v13 & 7));
      *((_BYTE *)v27 + v28) = v26;
    }
    ++v13;
  }
  while ( v13 < 0x100 );
  std::_Builder2<unsigned short const *,unsigned short,std::regex_traits<unsigned short>>::_Char_to_elts(
    v26,
    v33,
    v32,
    v6 + 9);
  std::wstring::~wstring(S2);
}

```

## disassembly

```asm
0x140090148  mov     [rsp-8+arg_18], rbx
0x14009014d  push    rbp
0x14009014e  push    rsi
0x14009014f  push    rdi
0x140090150  push    r12
0x140090152  push    r13
0x140090154  push    r14
0x140090156  push    r15
0x140090158  lea     rbp, [rsp-27h]
0x14009015d  sub     rsp, 0C0h
0x140090164  mov     rax, cs:__security_cookie
0x14009016b  xor     rax, rsp
0x14009016e  mov     [rbp+57h+var_40], rax
0x140090172  mov     rsi, r8
0x140090175  mov     [rbp+57h+var_B0], r8
0x140090179  mov     r12, rdx
0x14009017c  mov     [rbp+57h+var_A8], rdx
0x140090180  mov     rbx, rcx
0x140090183  mov     [rbp+57h+var_B8], rcx
0x140090187  mov     [rbp+57h+var_BC], 0
0x14009018e  mov     rdi, [rcx+8]
0x140090192  test    rdi, rdi
0x140090195  jz      short loc_1400901A8
0x140090197  xor     r8d, r8d
0x14009019a  mov     edx, 0A8h
0x14009019f  mov     rcx, [rdi]
0x1400901a2  call    __castguard_slow_path_check_fastfail
0x1400901a7  nop
0x1400901a8  xorps   xmm0, xmm0
0x1400901ab  movups  xmmword ptr [rbp+57h+S2], xmm0
0x1400901af  mov     [rbp+57h+var_70], 0
0x1400901b7  mov     [rbp+57h+var_68], 7
0x1400901bf  xor     eax, eax
0x1400901c1  mov     word ptr [rbp+57h+S2], ax
0x1400901c5  lea     r14d, [rax+1]
0x1400901c9  mov     [rbp+57h+var_BC], r14d
0x1400901cd  cmp     r12, rsi
0x1400901d0  jz      loc_1400904CA
0x1400901d6  mov     rax, [rbx+18h]
0x1400901da  mov     r15, [rax]
0x1400901dd  mov     rcx, r15
0x1400901e0  call    cs:__imp___RTtypeid
0x1400901e6  lea     rbx, [rax+8]
0x1400901ea  lea     rdx, qword_140157C08
0x1400901f1  mov     rcx, rbx
0x1400901f4  call    cs:__imp___std_type_info_compare
0x1400901fa  test    eax, eax
0x1400901fc  jz      short loc_140090216
0x1400901fe  lea     rdx, qword_140157C38
0x140090205  mov     rcx, rbx
0x140090208  call    cs:__imp___std_type_info_compare
0x14009020e  test    eax, eax
0x140090210  jnz     loc_1400902C3
0x140090216  xorps   xmm0, xmm0
0x140090219  movups  xmmword ptr [rbp+57h+S1], xmm0
0x14009021d  mov     [rbp+57h+N], 0
0x140090225  mov     [rbp+57h+var_88], 0
0x14009022d  mov     r8, rsi
0x140090230  sub     r8, r12
0x140090233  sar     r8, 1
0x140090236  mov     rdx, r12
0x140090239  lea     rcx, [rbp+57h+S1]
0x14009023d  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x140090242  nop
0x140090243  lea     rsi, [rbp+57h+S1]
0x140090247  cmp     [rbp+57h+var_88], 7
0x14009024c  cmova   rsi, [rbp+57h+S1]
0x140090251  mov     rbx, [rbp+57h+N]
0x140090255  lea     r13, [rsi+rbx*2]
0x140090259  cmp     [rbp+57h+var_70], rbx
0x14009025d  jnb     short loc_1400902AD
0x14009025f  add     r15, 10h
0x140090263  mov     rdx, rbx
0x140090266  lea     rcx, [rbp+57h+S2]; Src
0x14009026a  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x14009026f  lea     rax, [rbp+57h+S2]
0x140090273  cmp     [rbp+57h+var_68], 7
0x140090278  cmova   rax, [rbp+57h+S2]
0x14009027d  lea     rdx, [rax+rbx*2]
0x140090281  lea     rcx, [rbp+57h+S2]
0x140090285  cmova   rcx, [rbp+57h+S2]; void *
0x14009028a  mov     [rsp+0F0h+var_D0], r15; __int64
0x14009028f  mov     r9, r13
0x140090292  mov     r8, rsi
0x140090295  call    __std_regex_transform_primary_wchar_t
0x14009029a  mov     rbx, rax
0x14009029d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1400902a1  jz      short loc_1400902AB
0x1400902a3  cmp     [rbp+57h+var_70], rax
0x1400902a7  jb      short loc_140090263
0x1400902a9  jmp     short loc_1400902AD
0x1400902ab  xor     ebx, ebx
0x1400902ad  mov     rdx, rbx
0x1400902b0  lea     rcx, [rbp+57h+S2]; Src
0x1400902b4  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x1400902b9  nop
0x1400902ba  lea     rcx, [rbp+57h+S1]; void *
0x1400902be  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400902c3  cmp     [rbp+57h+var_70], 0
0x1400902c8  jz      loc_1400904CA
0x1400902ce  xor     esi, esi
0x1400902d0  mov     r12, [rbp+57h+var_B8]
0x1400902d4  mov     [rbp+57h+var_C0], si
0x1400902d8  mov     rcx, [r12+18h]
0x1400902dd  xorps   xmm0, xmm0
0x1400902e0  movups  xmmword ptr [rbp+57h+S1], xmm0
0x1400902e4  mov     [rbp+57h+N], 0
0x1400902ec  mov     [rbp+57h+var_88], 7
0x1400902f4  xor     eax, eax
0x1400902f6  mov     word ptr [rbp+57h+S1], ax
0x1400902fa  or      r14d, 2
0x1400902fe  mov     [rbp+57h+var_BC], r14d
0x140090302  mov     r13, [rcx]
0x140090305  mov     rcx, r13
0x140090308  call    cs:__imp___RTtypeid
0x14009030e  lea     rbx, [rax+8]
0x140090312  lea     rdx, qword_140157C08
0x140090319  mov     rcx, rbx
0x14009031c  call    cs:__imp___std_type_info_compare
0x140090322  test    eax, eax
0x140090324  jz      short loc_14009033E
0x140090326  lea     rdx, qword_140157C38
0x14009032d  mov     rcx, rbx
0x140090330  call    cs:__imp___std_type_info_compare
0x140090336  test    eax, eax
0x140090338  jnz     loc_1400903EE
0x14009033e  xorps   xmm0, xmm0
0x140090341  movups  [rbp+57h+var_60], xmm0
0x140090345  mov     [rbp+57h+var_50], 0
0x14009034d  mov     [rbp+57h+var_48], 0
0x140090355  mov     r8d, 1
0x14009035b  lea     rdx, [rbp+57h+var_C0]
0x14009035f  lea     rcx, [rbp+57h+var_60]
0x140090363  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x140090368  nop
0x140090369  lea     r15, [rbp+57h+var_60]
0x14009036d  cmp     [rbp+57h+var_48], 7
0x140090372  cmova   r15, qword ptr [rbp+57h+var_60]
0x140090377  mov     rbx, [rbp+57h+var_50]
0x14009037b  lea     rax, [r15+rbx*2]
0x14009037f  mov     [rbp+57h+var_B8], rax
0x140090383  cmp     [rbp+57h+N], rbx
0x140090387  jnb     short loc_1400903D8
0x140090389  add     r13, 10h
0x14009038d  mov     rdx, rbx
0x140090390  lea     rcx, [rbp+57h+S1]; Src
0x140090394  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x140090399  lea     rax, [rbp+57h+S1]
0x14009039d  cmp     [rbp+57h+var_88], 7
0x1400903a2  cmova   rax, [rbp+57h+S1]
0x1400903a7  lea     rdx, [rax+rbx*2]
0x1400903ab  lea     rcx, [rbp+57h+S1]
0x1400903af  cmova   rcx, [rbp+57h+S1]; void *
0x1400903b4  mov     [rsp+0F0h+var_D0], r13; __int64
0x1400903b9  mov     r9, [rbp+57h+var_B8]
0x1400903bd  mov     r8, r15
0x1400903c0  call    __std_regex_transform_primary_wchar_t
0x1400903c5  mov     rbx, rax
0x1400903c8  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1400903cc  jz      short loc_1400903D6
0x1400903ce  cmp     [rbp+57h+N], rax
0x1400903d2  jb      short loc_14009038D
0x1400903d4  jmp     short loc_1400903D8
0x1400903d6  xor     ebx, ebx
0x1400903d8  mov     rdx, rbx
0x1400903db  lea     rcx, [rbp+57h+S1]; Src
0x1400903df  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x1400903e4  nop
0x1400903e5  lea     rcx, [rbp+57h+var_60]; void *
0x1400903e9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400903ee  lea     rdx, [rbp+57h+S2]
0x1400903f2  cmp     [rbp+57h+var_68], 7
0x1400903f7  cmova   rdx, [rbp+57h+S2]; S2
0x1400903fc  mov     r8, [rbp+57h+N]; N
0x140090400  lea     rcx, [rbp+57h+S1]
0x140090404  cmp     [rbp+57h+var_88], 7
0x140090409  cmova   rcx, [rbp+57h+S1]; S1
0x14009040e  cmp     r8, [rbp+57h+var_70]
0x140090412  jz      short loc_140090418
0x140090414  xor     bl, bl
0x140090416  jmp     short loc_14009042B
0x140090418  test    r8, r8
0x14009041b  jnz     short loc_140090421
0x14009041d  mov     bl, 1
0x14009041f  jmp     short loc_14009042B
0x140090421  call    wmemcmp
0x140090426  test    eax, eax
0x140090428  setz    bl
0x14009042b  and     r14d, 0FFFFFFFDh
0x14009042f  mov     [rbp+57h+var_BC], r14d
0x140090433  lea     rcx, [rbp+57h+S1]; void *
0x140090437  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14009043c  test    bl, bl
0x14009043e  jz      short loc_14009047A
0x140090440  mov     rdx, [rdi+28h]
0x140090444  test    rdx, rdx
0x140090447  jnz     short loc_140090462
0x140090449  lea     ecx, [rdx+20h]; Size
0x14009044c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140090451  mov     rdx, rax
0x140090454  xorps   xmm0, xmm0
0x140090457  movups  xmmword ptr [rax], xmm0
0x14009045a  movups  xmmword ptr [rax+10h], xmm0
0x14009045e  mov     [rdi+28h], rax
0x140090462  mov     r9d, esi
0x140090465  shr     r9, 3
0x140090469  movzx   ecx, byte ptr [r9+rdx]
0x14009046e  mov     eax, esi
0x140090470  and     eax, 7
0x140090473  bts     ecx, eax
0x140090476  mov     [r9+rdx], cl
0x14009047a  inc     esi
0x14009047c  cmp     esi, 100h
0x140090482  jb      loc_1400902D4
0x140090488  lea     r9, [rdi+48h]
0x14009048c  mov     r8, [rbp+57h+var_B0]
0x140090490  mov     rdx, [rbp+57h+var_A8]
0x140090494  call    ?_Char_to_elts@?$_Builder2@PEBGGV?$regex_traits@G@std@@@std@@AEAAXPEBG0PEAPEAU?$_Sequence@G@2@@Z; std::_Builder2<ushort const *,ushort,std::regex_traits<ushort>>::_Char_to_elts(ushort const *,ushort const *,std::_Sequence<ushort> * *)
0x140090499  nop
0x14009049a  lea     rcx, [rbp+57h+S2]; void *
0x14009049e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400904a3  mov     rcx, [rbp+57h+var_40]
0x1400904a7  xor     rcx, rsp; StackCookie
0x1400904aa  call    __security_check_cookie
0x1400904af  mov     rbx, [rsp+0F0h+arg_18]
0x1400904b7  add     rsp, 0C0h
0x1400904be  pop     r15
0x1400904c0  pop     r14
0x1400904c2  pop     r13
0x1400904c4  pop     r12
0x1400904c6  pop     rdi
0x1400904c7  pop     rsi
0x1400904c8  pop     rbp
0x1400904c9  retn
0x1400904ca  xor     ecx, ecx
0x1400904cc  call    cs:__imp_?_Xregex_error@std@@YAXW4error_type@regex_constants@1@@Z; std::_Xregex_error(std::regex_constants::error_type)
```
