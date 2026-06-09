# EventManParser::StringTableType(std::map<std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,std::unique_ptr<STRING_ENTRY,std::default_delete<STRING_ENTRY>>,std::less<std::basic_string_view<wchar_t,std::char_traits<wchar_t>>>,std::allocator<std::pair<std::basic_string_view<wchar_t,std::char_traits<wchar_t>> const,std::unique_ptr<STRING_ENTRY,std::default_delete<STRING_ENTRY>>>>> &,bool,std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,bool)

- ea: `0x18003b29c`
- end: `0x18003b4d6`
- name: `?StringTableType@EventManParser@@AEAAXAEAV?$map@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@V?$unique_ptr@VSTRING_ENTRY@@U?$default_delete@VSTRING_ENTRY@@@std@@@2@U?$less@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@V?$unique_ptr@VSTRING_ENTRY@@U?$default_delete@VSTRING_ENTRY@@@std@@@2@@std@@@2@@std@@_NV?$basic_string_view@_WU?$char_traits@_W@std@@@3@21@Z`
- size: `570`
- prototype: `__int64 __usercall@<rax>(XmlReader *this@<rcx>, __int64, char)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config`

## callers

- `0x1800386fc`

## callees

- `0x18001cb90`
- `0x18001d638`
- `0x18001df64`
- `0x18001ed1c`
- `0x1800207c0`
- `0x180031438`
- `0x1800319f0`
- `0x180032cf8`
- `0x180033df0`
- `0x1800344c0`
- `0x180035858`
- `0x180037e80`
- `0x180038cc4`
- `0x18003b29c`
- `0x18003c754`
- `0x18003c8dc`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall EventManParser::StringTableType(
        XmlReader *this,
        _QWORD *a2,
        __int64 a3,
        __int128 *a4,
        _QWORD *a5,
        char a6)
{
  char i; // al
  _QWORD *v10; // rbx
  _QWORD *v11; // rax
  bool v12; // al
  __int128 *v13; // r8
  int v14; // eax
  __int128 *v15; // r8
  _QWORD v17[2]; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v18; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD *v19; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v20[2]; // [rsp+60h] [rbp-A0h] BYREF
  char v21; // [rsp+70h] [rbp-90h] BYREF
  __int128 v22; // [rsp+80h] [rbp-80h] BYREF
  __int128 v23; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v24[16]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v25[16]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v26[16]; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v27; // [rsp+D0h] [rbp-30h] BYREF
  __m128i si128; // [rsp+E0h] [rbp-20h]
  _OWORD v29[2]; // [rsp+F0h] [rbp-10h] BYREF

  v27 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v27) = 0;
  v29[0] = 0;
  v29[1] = si128;
  LOWORD(v29[0]) = 0;
  for ( i = XmlReader::FirstChildElement(this); i; i = XmlReader::NextChildElement((xp::XmlReader **)this) )
  {
    XmlReader::GetLocalName(this, &v22);
    v23 = v22;
    v18 = *a4;
    v20[0] = L"string";
    v20[1] = 6;
    if ( EventManParser::ElementMatches(this, v20, &v18, &v23) )
    {
      EventManParser::StringTableStringType(this);
      std::wstring::operator std::wstring_view(&v27, v24);
      std::_Tree<std::_Tmap_traits<std::wstring_view,std::unique_ptr<STRING_ENTRY>,std::less<std::wstring_view>,std::allocator<std::pair<std::wstring_view const,std::unique_ptr<STRING_ENTRY>>>,0>>::lower_bound(
        a2,
        &v19,
        v24);
      v10 = v19;
      v12 = 0;
      if ( v19 != (_QWORD *)*a2 )
      {
        v11 = (_QWORD *)std::wstring::operator std::wstring_view(&v27, v25);
        if ( (unsigned __int8)std::_Traits_equal<std::char_traits<wchar_t>>(v10[4], v10[5], *v11, v11[1]) )
          v12 = 1;
      }
      if ( a6 )
      {
        if ( v12 )
        {
          v13 = &v27;
          if ( si128.m128i_i64[1] > 7uLL )
            v13 = (__int128 *)v27;
          EventManParser::ErrorWithFormatMessage(this, 3221745411LL, v13);
        }
        else
        {
          std::make_unique<STRING_ENTRY,std::wstring,0>(v17, &v27);
          v18 = *(_OWORD *)a5;
          STRING_ENTRY::AddTranslation(v17[0], &v18, v29);
          v14 = std::wstring::operator std::wstring_view(v17[0] + 32LL, v26);
          std::map<std::wstring_view,std::unique_ptr<STRING_ENTRY>>::try_emplace<std::unique_ptr<STRING_ENTRY>>(
            (_DWORD)a2,
            (unsigned int)&v21,
            (_DWORD)v10,
            v14,
            (__int64)v17);
          std::unique_ptr<STRING_ENTRY>::~unique_ptr<STRING_ENTRY>(v17);
        }
      }
      else if ( v12 )
      {
        v18 = *(_OWORD *)a5;
        STRING_ENTRY::AddTranslation(v10[6], &v18, v29);
      }
      else
      {
        v15 = &v27;
        if ( si128.m128i_i64[1] > 7uLL )
          v15 = (__int128 *)v27;
        EventManParser::ErrorWithFormatMessage(this, 3221745581LL, v15, *a5);
      }
    }
  }
  std::wstring::_Tidy_deallocate(v29);
  return std::wstring::_Tidy_deallocate(&v27);
}

```

## disassembly

```asm
0x18003b29c  push    rbp
0x18003b29e  push    rbx
0x18003b29f  push    rsi
0x18003b2a0  push    rdi
0x18003b2a1  push    r12
0x18003b2a3  push    r14
0x18003b2a5  push    r15
0x18003b2a7  lea     rbp, [rsp-20h]
0x18003b2ac  sub     rsp, 120h
0x18003b2b3  mov     rax, cs:__security_cookie
0x18003b2ba  xor     rax, rsp
0x18003b2bd  mov     [rbp+50h+var_40], rax
0x18003b2c1  mov     r12, r9
0x18003b2c4  mov     r15b, r8b
0x18003b2c7  mov     r14, rdx
0x18003b2ca  mov     rdi, rcx
0x18003b2cd  mov     rsi, [rbp+50h+arg_20]
0x18003b2d4  xorps   xmm0, xmm0
0x18003b2d7  movups  [rbp+50h+var_80], xmm0
0x18003b2db  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18003b2e3  movdqu  [rbp+50h+var_70], xmm1
0x18003b2e8  xor     eax, eax
0x18003b2ea  mov     word ptr [rbp+50h+var_80], ax
0x18003b2ee  movups  [rbp+50h+var_60], xmm0
0x18003b2f2  movdqu  [rbp+50h+var_50], xmm1
0x18003b2f7  mov     word ptr [rbp+50h+var_60], ax
0x18003b2fb  call    ?FirstChildElement@XmlReader@@QEAA_NXZ; XmlReader::FirstChildElement(void)
0x18003b300  jmp     loc_18003B49D
0x18003b305  lea     rdx, [rbp+50h+var_D0]
0x18003b309  mov     rcx, rdi; this
0x18003b30c  call    ?GetLocalName@XmlReader@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; XmlReader::GetLocalName(void)
0x18003b311  movaps  xmm0, [rbp+50h+var_D0]
0x18003b315  movdqa  [rbp+50h+var_C0], xmm0
0x18003b31a  movaps  xmm1, xmmword ptr [r12]
0x18003b31f  movdqa  [rsp+150h+var_110], xmm1
0x18003b325  lea     rax, aString_0; "string"
0x18003b32c  mov     [rsp+150h+var_F0], rax
0x18003b331  mov     [rsp+150h+var_E8], 6
0x18003b33a  lea     r9, [rbp+50h+var_C0]
0x18003b33e  lea     r8, [rsp+150h+var_110]
0x18003b343  lea     rdx, [rsp+150h+var_F0]
0x18003b348  mov     rcx, rdi; this
0x18003b34b  call    ?ElementMatches@EventManParser@@AEBA_NV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@00@Z; EventManParser::ElementMatches(std::wstring_view,std::wstring_view,std::wstring_view)
0x18003b350  test    al, al
0x18003b352  jz      loc_18003B495
0x18003b358  lea     r9, [rbp+50h+var_60]
0x18003b35c  lea     r8, [rbp+50h+var_80]
0x18003b360  mov     dl, r15b
0x18003b363  mov     rcx, rdi; this
0x18003b366  call    ?StringTableStringType@EventManParser@@AEAAX_NPEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@1@Z; EventManParser::StringTableStringType(bool,std::wstring *,std::wstring *)
0x18003b36b  lea     rdx, [rbp+50h+var_B0]
0x18003b36f  lea     rcx, [rbp+50h+var_80]
0x18003b373  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x18003b378  lea     r8, [rbp+50h+var_B0]
0x18003b37c  lea     rdx, [rsp+150h+var_100]
0x18003b381  mov     rcx, r14
0x18003b384  call    ?lower_bound@?$_Tree@V?$_Tmap_traits@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@V?$unique_ptr@VSTRING_ENTRY@@U?$default_delete@VSTRING_ENTRY@@@std@@@2@U?$less@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@V?$unique_ptr@VSTRING_ENTRY@@U?$default_delete@VSTRING_ENTRY@@@std@@@2@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@V?$unique_ptr@VSTRING_ENTRY@@U?$default_delete@VSTRING_ENTRY@@@std@@@2@@std@@@std@@@std@@@2@AEBV?$basic_string_view@_WU?$char_traits@_W@std@@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring_view,std::unique_ptr<STRING_ENTRY>,std::less<std::wstring_view>,std::allocator<std::pair<std::wstring_view const,std::unique_ptr<STRING_ENTRY>>>,0>>::lower_bound(std::wstring_view const &)
0x18003b389  mov     rbx, [rsp+150h+var_100]
0x18003b38e  cmp     rbx, [r14]
0x18003b391  jz      short loc_18003B3BC
0x18003b393  lea     rdx, [rbp+50h+var_A0]
0x18003b397  lea     rcx, [rbp+50h+var_80]
0x18003b39b  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x18003b3a0  mov     r9, [rax+8]
0x18003b3a4  mov     r8, [rax]
0x18003b3a7  mov     rdx, [rbx+28h]
0x18003b3ab  mov     rcx, [rbx+20h]
0x18003b3af  call    ??$_Traits_equal@U?$char_traits@_W@std@@@std@@YA_NQEB_W_K01@Z; std::_Traits_equal<std::char_traits<wchar_t>>(wchar_t const * const,unsigned __int64,wchar_t const * const,unsigned __int64)
0x18003b3b4  test    al, al
0x18003b3b6  jz      short loc_18003B3BC
0x18003b3b8  mov     al, 1
0x18003b3ba  jmp     short loc_18003B3BE
0x18003b3bc  xor     al, al
0x18003b3be  cmp     [rbp+50h+arg_28], 0
0x18003b3c5  jz      loc_18003B456
0x18003b3cb  test    al, al
0x18003b3cd  jz      short loc_18003B3EF
0x18003b3cf  lea     r8, [rbp+50h+var_80]
0x18003b3d3  cmp     qword ptr [rbp+50h+var_70+8], 7
0x18003b3d8  cmova   r8, qword ptr [rbp+50h+var_80]
0x18003b3dd  mov     edx, 0C007EF03h; int
0x18003b3e2  mov     rcx, rdi; this
0x18003b3e5  call    ?ErrorWithFormatMessage@EventManParser@@AEAAXJZZ; EventManParser::ErrorWithFormatMessage(long,...)
0x18003b3ea  jmp     loc_18003B495
0x18003b3ef  lea     rdx, [rbp+50h+var_80]
0x18003b3f3  lea     rcx, [rsp+150h+var_120]
0x18003b3f8  call    ??$make_unique@VSTRING_ENTRY@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$0A@@std@@YA?AV?$unique_ptr@VSTRING_ENTRY@@U?$default_delete@VSTRING_ENTRY@@@std@@@0@$$QEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@@Z; std::make_unique<STRING_ENTRY,std::wstring,0>(std::wstring &&)
0x18003b3fd  nop
0x18003b3fe  movaps  xmm0, xmmword ptr [rsi]
0x18003b401  movdqa  [rsp+150h+var_110], xmm0
0x18003b407  lea     r8, [rbp+50h+var_60]
0x18003b40b  lea     rdx, [rsp+150h+var_110]
0x18003b410  mov     rcx, [rsp+150h+var_120]
0x18003b415  call    ?AddTranslation@STRING_ENTRY@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@$$QEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@3@@Z; STRING_ENTRY::AddTranslation(std::wstring_view,std::wstring &&)
0x18003b41a  mov     rcx, [rsp+150h+var_120]
0x18003b41f  add     rcx, 20h ; ' '
0x18003b423  lea     rdx, [rbp+50h+var_90]
0x18003b427  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x18003b42c  lea     rcx, [rsp+150h+var_120]
0x18003b431  mov     [rsp+150h+var_130], rcx
0x18003b436  mov     r9, rax
0x18003b439  mov     r8, rbx
0x18003b43c  lea     rdx, [rsp+150h+var_E0]
0x18003b441  mov     rcx, r14
0x18003b444  call    ??$try_emplace@V?$unique_ptr@VSTRING_ENTRY@@U?$default_delete@VSTRING_ENTRY@@@std@@@std@@@?$map@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@V?$unique_ptr@VSTRING_ENTRY@@U?$default_delete@VSTRING_ENTRY@@@std@@@2@U?$less@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@V?$unique_ptr@VSTRING_ENTRY@@U?$default_delete@VSTRING_ENTRY@@@std@@@2@@std@@@2@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@V?$unique_ptr@VSTRING_ENTRY@@U?$default_delete@VSTRING_ENTRY@@@std@@@2@@std@@@std@@@std@@@1@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@V?$unique_ptr@VSTRING_ENTRY@@U?$default_delete@VSTRING_ENTRY@@@std@@@2@@std@@@std@@@std@@@1@$$QEAV?$basic_string_view@_WU?$char_traits@_W@std@@@1@$$QEAV?$unique_ptr@VSTRING_ENTRY@@U?$default_delete@VSTRING_ENTRY@@@std@@@1@@Z; std::map<std::wstring_view,std::unique_ptr<STRING_ENTRY>>::try_emplace<std::unique_ptr<STRING_ENTRY>>(std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring_view const,std::unique_ptr<STRING_ENTRY>>>>>,std::wstring_view &&,std::unique_ptr<STRING_ENTRY> &&)
0x18003b449  nop
0x18003b44a  lea     rcx, [rsp+150h+var_120]
0x18003b44f  call    ??1?$unique_ptr@VSTRING_ENTRY@@U?$default_delete@VSTRING_ENTRY@@@std@@@std@@QEAA@XZ; std::unique_ptr<STRING_ENTRY>::~unique_ptr<STRING_ENTRY>(void)
0x18003b454  jmp     short loc_18003B495
0x18003b456  test    al, al
0x18003b458  jz      short loc_18003B477
0x18003b45a  movaps  xmm0, xmmword ptr [rsi]
0x18003b45d  movdqa  [rsp+150h+var_110], xmm0
0x18003b463  lea     r8, [rbp+50h+var_60]
0x18003b467  lea     rdx, [rsp+150h+var_110]
0x18003b46c  mov     rcx, [rbx+30h]
0x18003b470  call    ?AddTranslation@STRING_ENTRY@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@$$QEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@3@@Z; STRING_ENTRY::AddTranslation(std::wstring_view,std::wstring &&)
0x18003b475  jmp     short loc_18003B495
0x18003b477  lea     r8, [rbp+50h+var_80]
0x18003b47b  cmp     qword ptr [rbp+50h+var_70+8], 7
0x18003b480  cmova   r8, qword ptr [rbp+50h+var_80]
0x18003b485  mov     r9, [rsi]
0x18003b488  mov     edx, 0C007EFADh; int
0x18003b48d  mov     rcx, rdi; this
0x18003b490  call    ?ErrorWithFormatMessage@EventManParser@@AEAAXJZZ; EventManParser::ErrorWithFormatMessage(long,...)
0x18003b495  mov     rcx, rdi; this
0x18003b498  call    ?NextChildElement@XmlReader@@QEAA_NXZ; XmlReader::NextChildElement(void)
0x18003b49d  test    al, al
0x18003b49f  jnz     loc_18003B305
0x18003b4a5  lea     rcx, [rbp+50h+var_60]
0x18003b4a9  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003b4ae  nop
0x18003b4af  lea     rcx, [rbp+50h+var_80]
0x18003b4b3  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003b4b8  mov     rcx, [rbp+50h+var_40]
0x18003b4bc  xor     rcx, rsp; StackCookie
0x18003b4bf  call    __security_check_cookie
0x18003b4c4  add     rsp, 120h
0x18003b4cb  pop     r15
0x18003b4cd  pop     r14
0x18003b4cf  pop     r12
0x18003b4d1  pop     rdi
0x18003b4d2  pop     rsi
0x18003b4d3  pop     rbx
0x18003b4d4  pop     rbp
0x18003b4d5  retn
```
