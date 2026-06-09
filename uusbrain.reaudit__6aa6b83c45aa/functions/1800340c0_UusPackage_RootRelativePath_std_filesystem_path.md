# UusPackage::RootRelativePath(std::filesystem::path)

- ea: `0x1800340c0`
- end: `0x1800343a8`
- name: `?RootRelativePath@UusPackage@@CA?AVpath@filesystem@std@@V234@@Z`
- size: `744`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180033b4c`

## callees

- `0x18000d660`
- `0x180025aa0`
- `0x180025c5c`
- `0x180028728`
- `0x180028810`
- `0x1800295e8`
- `0x180029644`
- `0x1800340c0`
- `0x1800427d0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034363`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034363`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
std::filesystem *__fastcall UusPackage::RootRelativePath(std::filesystem *a1, std::filesystem *a2, const wchar_t *a3)
{
  std::filesystem *v5; // rcx
  const wchar_t *root_name_end; // rax
  const wchar_t *v7; // rdx
  const wchar_t *v8; // r11
  const wchar_t *v9; // rcx
  _QWORD *v10; // rax
  int v11; // edi
  _QWORD *v12; // rdx
  __int64 v13; // rcx
  const wchar_t *v14; // r8
  int v15; // edi
  __m128i si128; // xmm6
  std::filesystem *v17; // rcx
  const wchar_t *i; // rax
  const wchar_t *v19; // rdx
  int v20; // edi
  _QWORD *v21; // rax
  int v22; // ebx
  const wchar_t *v23; // r8
  std::filesystem *v24; // rcx
  const wchar_t *j; // rax
  const wchar_t *v26; // rdx
  __int128 v28; // [rsp+38h] [rbp-D0h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-C0h] BYREF
  _QWORD v30[4]; // [rsp+50h] [rbp-B8h] BYREF
  __int128 v31; // [rsp+70h] [rbp-98h] BYREF
  __m128i v32; // [rsp+80h] [rbp-88h]
  __int128 v33; // [rsp+98h] [rbp-70h]
  _QWORD *v34; // [rsp+A8h] [rbp-60h]
  __int64 v35; // [rsp+B0h] [rbp-58h]
  _OWORD v36[2]; // [rsp+B8h] [rbp-50h] BYREF
  std::filesystem *v37; // [rsp+D8h] [rbp-30h]
  std::filesystem *v38; // [rsp+E0h] [rbp-28h]
  _QWORD v39[4]; // [rsp+E8h] [rbp-20h] BYREF

  v37 = a1;
  v38 = a2;
  v5 = a2;
  if ( *((_QWORD *)a2 + 3) > 7u )
    v5 = *(std::filesystem **)a2;
  root_name_end = std::filesystem::_Find_root_name_end(v5, (const wchar_t *const)v5 + *((_QWORD *)a2 + 2), a3);
  if ( root_name_end != v8 )
  {
    do
    {
      if ( *root_name_end != 92 && *root_name_end != 47 )
        break;
      ++root_name_end;
    }
    while ( root_name_end != v7 );
  }
  if ( root_name_end == v7 )
    goto LABEL_13;
  do
  {
    v9 = v7 - 1;
    if ( *(v7 - 1) == 92 )
      break;
    if ( *v9 == 47 )
      break;
    --v7;
  }
  while ( root_name_end != v9 );
  if ( v8 == v7 )
  {
LABEL_13:
    v10 = (_QWORD *)std::filesystem::path::parent_path(a2, v36);
    v11 = 2;
  }
  else
  {
    std::wstring::wstring(v30, a2);
    v10 = v30;
    v11 = 1;
  }
  std::wstring::wstring(v39, v10);
  if ( (v11 & 2) != 0 )
  {
    v11 &= ~2u;
    std::wstring::_Tidy_deallocate(v36);
  }
  if ( (v11 & 1) != 0 )
  {
    v11 &= ~1u;
    std::wstring::_Tidy_deallocate(v30);
  }
  pv = 0;
  v12 = v39;
  if ( v39[3] > 7u )
    v12 = (_QWORD *)v39[0];
  wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,256>(
    &pv,
    v12);
  v13 = -1;
  do
    ++v13;
  while ( *((_WORD *)pv + v13) );
  *(_QWORD *)&v28 = pv;
  *((_QWORD *)&v28 + 1) = v13;
  std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(a1, &v28);
  v15 = v11 | 0x84;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  while ( 1 )
  {
    v17 = a1;
    if ( *((_QWORD *)a1 + 3) > 7u )
      v17 = *(std::filesystem **)a1;
    for ( i = std::filesystem::_Find_root_name_end(v17, (const wchar_t *const)v17 + *((_QWORD *)a1 + 2), v14);
          i != v19 && (*i == 92 || *i == 47);
          ++i )
    {
      ;
    }
    *(_QWORD *)&v33 = i;
    *((_QWORD *)&v33 + 1) = v19 - i;
    v28 = v33;
    std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(v30, &v28);
    v20 = v15 | 0x18;
    v21 = v30;
    if ( v30[3] > 7u )
      v21 = (_QWORD *)v30[0];
    v34 = v21;
    v35 = v30[2];
    v22 = std::filesystem::path::compare(a1);
    std::wstring::_Tidy_deallocate(v30);
    if ( !v22 )
      break;
    v24 = a1;
    if ( *((_QWORD *)a1 + 3) > 7u )
      v24 = *(std::filesystem **)a1;
    for ( j = std::filesystem::_Find_root_name_end(v24, (const wchar_t *const)v24 + *((_QWORD *)a1 + 2), v23);
          j != v26 && (*j == 92 || *j == 47);
          ++j )
    {
      ;
    }
    *(_QWORD *)&v36[0] = j;
    *((_QWORD *)&v36[0] + 1) = v26 - j;
    v28 = v36[0];
    std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(&v31, &v28);
    v15 = v20 | 0x60;
    if ( a1 != (std::filesystem *)&v31 )
    {
      std::wstring::_Tidy_deallocate(a1);
      *(_OWORD *)a1 = v31;
      *((__m128i *)a1 + 1) = v32;
      v32 = si128;
      LOWORD(v31) = 0;
    }
    std::wstring::_Tidy_deallocate(&v31);
  }
  if ( pv )
    CoTaskMemFree(pv);
  std::wstring::_Tidy_deallocate(v39);
  std::wstring::_Tidy_deallocate(a2);
  return a1;
}

```

## disassembly

```asm
0x1800340c0  mov     rax, rsp
0x1800340c3  mov     [rax+18h], rbx
0x1800340c7  push    rbp
0x1800340c8  push    rsi
0x1800340c9  push    rdi
0x1800340ca  push    r14
0x1800340cc  push    r15
0x1800340ce  lea     rbp, [rax-48h]
0x1800340d2  sub     rsp, 120h
0x1800340d9  movaps  xmmword ptr [rax-38h], xmm6
0x1800340dd  mov     rax, cs:__security_cookie
0x1800340e4  xor     rax, rsp
0x1800340e7  mov     [rbp+40h+var_40], rax
0x1800340eb  mov     r14, rdx
0x1800340ee  mov     rsi, rcx
0x1800340f1  mov     [rbp+40h+var_70], rcx
0x1800340f5  mov     [rbp+40h+var_68], rdx
0x1800340f9  xor     r15d, r15d
0x1800340fc  mov     [rsp+140h+var_120], r15d
0x180034101  mov     rcx, rdx
0x180034104  cmp     qword ptr [rdx+18h], 7
0x180034109  jbe     short loc_18003410E
0x18003410b  mov     rcx, [rdx]; this
0x18003410e  mov     rax, [rdx+10h]
0x180034112  lea     r11, [rcx+rax*2]
0x180034116  mov     rdx, r11; wchar_t *
0x180034119  call    ?_Find_root_name_end@filesystem@std@@YAPEB_WQEB_W0@Z; std::filesystem::_Find_root_name_end(wchar_t const * const,wchar_t const * const)
0x18003411e  cmp     rax, r11
0x180034121  jz      short loc_180034138
0x180034123  cmp     word ptr [rax], 5Ch ; '\'
0x180034127  jz      short loc_18003412F
0x180034129  cmp     word ptr [rax], 2Fh ; '/'
0x18003412d  jnz     short loc_180034138
0x18003412f  add     rax, 2
0x180034133  cmp     rax, rdx
0x180034136  jnz     short loc_180034123
0x180034138  cmp     rax, rdx
0x18003413b  jz      short loc_180034173
0x18003413d  lea     rcx, [rdx-2]
0x180034141  cmp     word ptr [rcx], 5Ch ; '\'
0x180034145  jz      short loc_180034155
0x180034147  cmp     word ptr [rcx], 2Fh ; '/'
0x18003414b  jz      short loc_180034155
0x18003414d  mov     rdx, rcx
0x180034150  cmp     rax, rcx
0x180034153  jnz     short loc_18003413D
0x180034155  cmp     r11, rdx
0x180034158  jz      short loc_180034173
0x18003415a  mov     rdx, r14
0x18003415d  lea     rcx, [rsp+140h+var_F8]
0x180034162  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180034167  lea     rax, [rsp+140h+var_F8]
0x18003416c  mov     edi, 1
0x180034171  jmp     short loc_180034185
0x180034173  lea     rdx, [rbp+40h+var_90]
0x180034177  mov     rcx, r14
0x18003417a  call    ?parent_path@path@filesystem@std@@QEBA?AV123@XZ; std::filesystem::path::parent_path(void)
0x18003417f  nop
0x180034180  mov     edi, 2
0x180034185  mov     [rsp+140h+var_120], edi
0x180034189  mov     rdx, rax
0x18003418c  lea     rcx, [rbp+40h+var_60]
0x180034190  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180034195  nop
0x180034196  test    dil, 2
0x18003419a  jz      short loc_1800341AD
0x18003419c  and     edi, 0FFFFFFFDh
0x18003419f  mov     [rsp+140h+var_120], edi
0x1800341a3  lea     rcx, [rbp+40h+var_90]
0x1800341a7  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800341ac  nop
0x1800341ad  test    dil, 1
0x1800341b1  jz      short loc_1800341C4
0x1800341b3  and     edi, 0FFFFFFFEh
0x1800341b6  mov     [rsp+140h+var_120], edi
0x1800341ba  lea     rcx, [rsp+140h+var_F8]
0x1800341bf  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800341c4  mov     [rsp+140h+pv], r15
0x1800341c9  lea     rdx, [rbp+40h+var_60]
0x1800341cd  cmp     [rbp+40h+var_48], 7
0x1800341d2  cmova   rdx, [rbp+40h+var_60]
0x1800341d7  lea     rcx, [rsp+140h+pv]
0x1800341dc  call    ??$ExpandEnvironmentStringsW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@PEB_W@Z; wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,256>(wchar_t const *)
0x1800341e1  nop
0x1800341e2  mov     rax, [rsp+140h+pv]
0x1800341e7  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800341eb  inc     rcx
0x1800341ee  cmp     [rax+rcx*2], r15w
0x1800341f3  jnz     short loc_1800341EB
0x1800341f5  mov     qword ptr [rsp+140h+var_118+8], rax
0x1800341fa  mov     [rsp+140h+var_108], rcx
0x1800341ff  lea     rdx, [rsp+140h+var_118+8]
0x180034204  mov     rcx, rsi
0x180034207  call    ??$_Convert_stringoid_to_wide@U_Normal_conversion@filesystem@std@@@filesystem@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@V?$basic_string_view@_WU?$char_traits@_W@std@@@1@U_Normal_conversion@01@@Z; std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(std::wstring_view,std::filesystem::_Normal_conversion)
0x18003420c  bts     edi, 7
0x180034210  or      edi, 4
0x180034213  mov     [rsp+140h+var_120], edi
0x180034217  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x18003421f  mov     rcx, rsi
0x180034222  cmp     qword ptr [rsi+18h], 7
0x180034227  jbe     short loc_18003422C
0x180034229  mov     rcx, [rsi]; this
0x18003422c  mov     rax, [rsi+10h]
0x180034230  lea     rdx, [rcx+rax*2]; wchar_t *
0x180034234  call    ?_Find_root_name_end@filesystem@std@@YAPEB_WQEB_W0@Z; std::filesystem::_Find_root_name_end(wchar_t const * const,wchar_t const * const)
0x180034239  jmp     short loc_18003424B
0x18003423b  cmp     word ptr [rax], 5Ch ; '\'
0x18003423f  jz      short loc_180034247
0x180034241  cmp     word ptr [rax], 2Fh ; '/'
0x180034245  jnz     short loc_180034250
0x180034247  add     rax, 2
0x18003424b  cmp     rax, rdx
0x18003424e  jnz     short loc_18003423B
0x180034250  mov     qword ptr [rbp+40h+var_B0], rax
0x180034254  sub     rdx, rax
0x180034257  sar     rdx, 1
0x18003425a  mov     qword ptr [rbp+40h+var_B0+8], rdx
0x18003425e  movaps  xmm0, [rbp+40h+var_B0]
0x180034262  movdqa  [rsp+140h+var_118+8], xmm0
0x180034268  lea     rdx, [rsp+140h+var_118+8]
0x18003426d  lea     rcx, [rsp+140h+var_F8]
0x180034272  call    ??$_Convert_stringoid_to_wide@U_Normal_conversion@filesystem@std@@@filesystem@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@V?$basic_string_view@_WU?$char_traits@_W@std@@@1@U_Normal_conversion@01@@Z; std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(std::wstring_view,std::filesystem::_Normal_conversion)
0x180034277  or      edi, 18h
0x18003427a  mov     [rsp+140h+var_120], edi
0x18003427e  lea     rax, [rsp+140h+var_F8]
0x180034283  cmp     qword ptr [rsp+140h+var_E0], 7
0x180034289  cmova   rax, [rsp+140h+var_F8]
0x18003428f  mov     [rbp+40h+var_A0], rax
0x180034293  mov     rax, [rsp+140h+var_E8]
0x180034298  mov     [rbp+40h+var_98], rax
0x18003429c  lea     rdx, [rbp+40h+var_A0]
0x1800342a0  mov     rcx, rsi; this
0x1800342a3  call    ?compare@path@filesystem@std@@QEBAHV?$basic_string_view@_WU?$char_traits@_W@std@@@3@@Z; std::filesystem::path::compare(std::wstring_view)
0x1800342a8  mov     ebx, eax
0x1800342aa  lea     rcx, [rsp+140h+var_F8]
0x1800342af  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800342b4  test    ebx, ebx
0x1800342b6  jz      loc_180034359
0x1800342bc  mov     rcx, rsi
0x1800342bf  cmp     qword ptr [rsi+18h], 7
0x1800342c4  jbe     short loc_1800342C9
0x1800342c6  mov     rcx, [rsi]; this
0x1800342c9  mov     rax, [rsi+10h]
0x1800342cd  lea     rdx, [rcx+rax*2]; wchar_t *
0x1800342d1  call    ?_Find_root_name_end@filesystem@std@@YAPEB_WQEB_W0@Z; std::filesystem::_Find_root_name_end(wchar_t const * const,wchar_t const * const)
0x1800342d6  jmp     short loc_1800342E8
0x1800342d8  cmp     word ptr [rax], 5Ch ; '\'
0x1800342dc  jz      short loc_1800342E4
0x1800342de  cmp     word ptr [rax], 2Fh ; '/'
0x1800342e2  jnz     short loc_1800342ED
0x1800342e4  add     rax, 2
0x1800342e8  cmp     rax, rdx
0x1800342eb  jnz     short loc_1800342D8
0x1800342ed  mov     qword ptr [rbp+40h+var_90], rax
0x1800342f1  sub     rdx, rax
0x1800342f4  sar     rdx, 1
0x1800342f7  mov     qword ptr [rbp+40h+var_90+8], rdx
0x1800342fb  movaps  xmm0, [rbp+40h+var_90]
0x1800342ff  movdqa  [rsp+140h+var_118+8], xmm0
0x180034305  lea     rdx, [rsp+140h+var_118+8]
0x18003430a  lea     rcx, [rsp+140h+var_E0+8]
0x18003430f  call    ??$_Convert_stringoid_to_wide@U_Normal_conversion@filesystem@std@@@filesystem@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@V?$basic_string_view@_WU?$char_traits@_W@std@@@1@U_Normal_conversion@01@@Z; std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(std::wstring_view,std::filesystem::_Normal_conversion)
0x180034314  or      edi, 60h
0x180034317  mov     [rsp+140h+var_120], edi
0x18003431b  lea     rax, [rsp+140h+var_E0+8]
0x180034320  cmp     rsi, rax
0x180034323  jz      short loc_18003434A
0x180034325  mov     rcx, rsi
0x180034328  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003432d  movups  xmm0, [rsp+140h+var_E0+8]
0x180034332  movups  xmmword ptr [rsi], xmm0
0x180034335  movups  xmm1, xmmword ptr [rsp+140h+var_D0+8]
0x18003433a  movups  xmmword ptr [rsi+10h], xmm1
0x18003433e  movdqu  xmmword ptr [rsp+140h+var_D0+8], xmm6
0x180034344  mov     word ptr [rsp+140h+var_E0+8], r15w
0x18003434a  lea     rcx, [rsp+140h+var_E0+8]
0x18003434f  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180034354  jmp     loc_18003421F
0x180034359  mov     rcx, [rsp+140h+pv]; pv
0x18003435e  test    rcx, rcx
0x180034361  jz      short loc_18003436A
0x180034363  call    cs:__imp_CoTaskMemFree
0x180034369  nop
0x18003436a  lea     rcx, [rbp+40h+var_60]
0x18003436e  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180034373  nop
0x180034374  mov     rcx, r14
0x180034377  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003437c  mov     rax, rsi
0x18003437f  mov     rcx, [rbp+40h+var_40]
0x180034383  xor     rcx, rsp; StackCookie
0x180034386  call    __security_check_cookie
0x18003438b  lea     r11, [rsp+140h+var_20]
0x180034393  mov     rbx, [r11+40h]
0x180034397  movaps  xmm6, xmmword ptr [r11-10h]
0x18003439c  mov     rsp, r11
0x18003439f  pop     r15
0x1800343a1  pop     r14
0x1800343a3  pop     rdi
0x1800343a4  pop     rsi
0x1800343a5  pop     rbp
0x1800343a6  retn
```
