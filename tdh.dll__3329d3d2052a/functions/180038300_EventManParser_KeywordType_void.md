# EventManParser::KeywordType(void)

- ea: `0x180038300`
- end: `0x180038492`
- name: `?KeywordType@EventManParser@@AEAA?AV?$unique_ptr@VKEYWORD_ENTRY@@U?$default_delete@VKEYWORD_ENTRY@@@std@@@std@@XZ`
- size: `402`
- prototype: `__int64 __fastcall(XmlReader *this)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config`

## callers

- `0x180038228`

## callees

- `0x18001df64`
- `0x18001e0cc`
- `0x18001e284`
- `0x18001e4d8`
- `0x18001e550`
- `0x18001e8f0`
- `0x18001e930`
- `0x1800207c0`
- `0x180031218`
- `0x180033da0`
- `0x180037670`
- `0x180038300`
- `0x180039500`
- `0x18003c754`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 *__fastcall EventManParser::KeywordType(XmlReader *this, __int64 *a2)
{
  char v4; // si
  bool i; // al
  char AttributeId; // al
  _QWORD *Value; // rax
  __int64 v8; // rcx
  __int64 v9; // rax
  __int128 v11; // [rsp+30h] [rbp-49h] BYREF
  __int64 *v12; // [rsp+40h] [rbp-39h]
  __int64 v13; // [rsp+48h] [rbp-31h] BYREF
  __int64 v14; // [rsp+58h] [rbp-21h] BYREF
  __int64 v15; // [rsp+68h] [rbp-11h] BYREF
  __int64 v16; // [rsp+78h] [rbp-1h] BYREF
  __int64 v17; // [rsp+88h] [rbp+Fh] BYREF
  _BYTE v18[32]; // [rsp+98h] [rbp+1Fh] BYREF

  v12 = a2;
  std::make_unique<KEYWORD_ENTRY,,0>(a2);
  v4 = 0;
  for ( i = XmlReader::FirstAttribute(this); i; i = XmlReader::NextAttribute(this) )
  {
    v11 = *(_OWORD *)XmlReader::GetQualifiedName(this, &v13);
    AttributeId = GetAttributeId(&v11);
    if ( AttributeId == 21 )
    {
      v11 = *(_OWORD *)XmlReader::GetValue(this, &v17);
      *(_QWORD *)(*a2 + 32) = EventManParser::ParseHexInt64(this);
      v4 = 1;
    }
    else if ( AttributeId == 22 )
    {
      v11 = *(_OWORD *)XmlReader::GetValue(this, &v16);
      v9 = EventManParser::ParseStrTableRef(this, v18, &v11);
      std::wstring::operator=(*a2 + 72, v9);
      std::wstring::_Tidy_deallocate(v18);
    }
    else
    {
      if ( AttributeId == 25 )
      {
        Value = XmlReader::GetValue(this, &v15);
        v8 = *a2;
      }
      else
      {
        if ( AttributeId != 34 )
          continue;
        Value = XmlReader::GetValue(this, &v14);
        v8 = *a2 + 40;
      }
      std::wstring::_Assign<wchar_t>(v8, *Value, Value[1]);
    }
  }
  if ( !*(_QWORD *)(*a2 + 16) )
    EventManParser::ErrorWithFormatMessage(this, -1073221826, L"name");
  if ( !v4 )
    EventManParser::ErrorWithFormatMessage(this, -1073221826, L"mask");
  return a2;
}

```

## disassembly

```asm
0x180038300  mov     [rsp-8+arg_10], rbx
0x180038305  push    rbp
0x180038306  push    rsi
0x180038307  push    rdi
0x180038308  lea     rbp, [rsp-47h]
0x18003830d  sub     rsp, 0C0h
0x180038314  mov     rax, cs:__security_cookie
0x18003831b  xor     rax, rsp
0x18003831e  mov     [rbp+57h+var_18], rax
0x180038322  mov     rdi, rdx
0x180038325  mov     rbx, rcx
0x180038328  mov     [rbp+57h+var_90], rdx
0x18003832c  mov     [rbp+57h+var_B0], 0
0x180038333  mov     rcx, rdx
0x180038336  call    ??$make_unique@VKEYWORD_ENTRY@@$$V$0A@@std@@YA?AV?$unique_ptr@VKEYWORD_ENTRY@@U?$default_delete@VKEYWORD_ENTRY@@@std@@@0@XZ; std::make_unique<KEYWORD_ENTRY,,0>(void)
0x18003833b  mov     [rbp+57h+var_B0], 1
0x180038342  xor     sil, sil
0x180038345  mov     rcx, rbx; this
0x180038348  call    ?FirstAttribute@XmlReader@@QEAA_NXZ; XmlReader::FirstAttribute(void)
0x18003834d  jmp     loc_180038430
0x180038352  lea     rdx, [rbp+57h+var_88]
0x180038356  mov     rcx, rbx; this
0x180038359  call    ?GetQualifiedName@XmlReader@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; XmlReader::GetQualifiedName(void)
0x18003835e  movups  xmm0, xmmword ptr [rax]
0x180038361  movdqu  [rbp+57h+var_A0], xmm0
0x180038366  lea     rcx, [rbp+57h+var_A0]
0x18003836a  call    GetAttributeId
0x18003836f  movzx   ecx, al
0x180038372  sub     ecx, 15h
0x180038375  jz      loc_1800383FE
0x18003837b  sub     ecx, 1
0x18003837e  jz      short loc_1800383C0
0x180038380  sub     ecx, 3
0x180038383  jz      short loc_1800383A3
0x180038385  cmp     ecx, 9
0x180038388  jnz     loc_180038428
0x18003838e  lea     rdx, [rbp+57h+var_78]
0x180038392  mov     rcx, rbx; this
0x180038395  call    ?GetValue@XmlReader@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; XmlReader::GetValue(void)
0x18003839a  mov     rcx, [rdi]
0x18003839d  add     rcx, 28h ; '('
0x1800383a1  jmp     short loc_1800383B2
0x1800383a3  lea     rdx, [rbp+57h+var_68]
0x1800383a7  mov     rcx, rbx; this
0x1800383aa  call    ?GetValue@XmlReader@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; XmlReader::GetValue(void)
0x1800383af  mov     rcx, [rdi]
0x1800383b2  mov     rdx, [rax]
0x1800383b5  mov     r8, [rax+8]
0x1800383b9  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x1800383be  jmp     short loc_180038428
0x1800383c0  lea     rdx, [rbp+57h+var_58]
0x1800383c4  mov     rcx, rbx; this
0x1800383c7  call    ?GetValue@XmlReader@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; XmlReader::GetValue(void)
0x1800383cc  movups  xmm0, xmmword ptr [rax]
0x1800383cf  movdqu  [rbp+57h+var_A0], xmm0
0x1800383d4  lea     r8, [rbp+57h+var_A0]
0x1800383d8  lea     rdx, [rbp+57h+var_38]
0x1800383dc  mov     rcx, rbx
0x1800383df  call    ?ParseStrTableRef@EventManParser@@AEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@3@@Z; EventManParser::ParseStrTableRef(std::wstring_view)
0x1800383e4  mov     rcx, [rdi]
0x1800383e7  add     rcx, 48h ; 'H'
0x1800383eb  mov     rdx, rax
0x1800383ee  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800383f3  lea     rcx, [rbp+57h+var_38]
0x1800383f7  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800383fc  jmp     short loc_180038428
0x1800383fe  lea     rdx, [rbp+57h+var_48]
0x180038402  mov     rcx, rbx; this
0x180038405  call    ?GetValue@XmlReader@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; XmlReader::GetValue(void)
0x18003840a  movups  xmm0, xmmword ptr [rax]
0x18003840d  movdqu  [rbp+57h+var_A0], xmm0
0x180038412  lea     rdx, [rbp+57h+var_A0]
0x180038416  mov     rcx, rbx; this
0x180038419  call    ?ParseHexInt64@EventManParser@@AEAA_KV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; EventManParser::ParseHexInt64(std::wstring_view)
0x18003841e  mov     rcx, [rdi]
0x180038421  mov     [rcx+20h], rax
0x180038425  mov     sil, 1
0x180038428  mov     rcx, rbx; this
0x18003842b  call    ?NextAttribute@XmlReader@@QEAA_NXZ; XmlReader::NextAttribute(void)
0x180038430  test    al, al
0x180038432  jnz     loc_180038352
0x180038438  mov     rax, [rdi]
0x18003843b  cmp     qword ptr [rax+10h], 0
0x180038440  jnz     short loc_180038456
0x180038442  lea     r8, aName_0; "name"
0x180038449  mov     edx, 0C007EF3Eh; int
0x18003844e  mov     rcx, rbx; this
0x180038451  call    ?ErrorWithFormatMessage@EventManParser@@AEAAXJZZ; EventManParser::ErrorWithFormatMessage(long,...)
0x180038456  test    sil, sil
0x180038459  jnz     short loc_18003846F
0x18003845b  lea     r8, aMask; "mask"
0x180038462  mov     edx, 0C007EF3Eh; int
0x180038467  mov     rcx, rbx; this
0x18003846a  call    ?ErrorWithFormatMessage@EventManParser@@AEAAXJZZ; EventManParser::ErrorWithFormatMessage(long,...)
0x18003846f  mov     rax, rdi
0x180038472  mov     rcx, [rbp+57h+var_18]
0x180038476  xor     rcx, rsp; StackCookie
0x180038479  call    __security_check_cookie
0x18003847e  mov     rbx, [rsp+0D0h+arg_10]
0x180038486  add     rsp, 0C0h
0x18003848d  pop     rdi
0x18003848e  pop     rsi
0x18003848f  pop     rbp
0x180038490  retn
```
