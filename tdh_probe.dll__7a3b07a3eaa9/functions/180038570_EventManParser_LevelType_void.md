# EventManParser::LevelType(void)

- ea: `0x180038570`
- end: `0x1800386f6`
- name: `?LevelType@EventManParser@@AEAA?AV?$unique_ptr@VLEVEL_ENTRY@@U?$default_delete@VLEVEL_ENTRY@@@std@@@std@@XZ`
- size: `390`
- prototype: `__int64 __fastcall(XmlReader *this)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config`

## callers

- `0x180038498`

## callees

- `0x18001df64`
- `0x18001e0cc`
- `0x18001e284`
- `0x18001e4d8`
- `0x18001e550`
- `0x18001e8f0`
- `0x18001e930`
- `0x1800207c0`
- `0x180031294`
- `0x180033da0`
- `0x180037670`
- `0x180038570`
- `0x180039674`
- `0x18003c754`

## pseudocode

```c
__int64 *__fastcall EventManParser::LevelType(XmlReader *this, __int64 *a2)
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
  std::make_unique<LEVEL_ENTRY,,0>(a2);
  v4 = 0;
  for ( i = XmlReader::FirstAttribute(this); i; i = XmlReader::NextAttribute(this) )
  {
    v11 = *(_OWORD *)XmlReader::GetQualifiedName(this, &v13);
    AttributeId = GetAttributeId(&v11);
    switch ( AttributeId )
    {
      case 22:
        v11 = *(_OWORD *)XmlReader::GetValue(this, &v17);
        v9 = EventManParser::ParseStrTableRef(this, v18, &v11);
        std::wstring::operator=(*a2 + 72, v9);
        std::wstring::_Tidy_deallocate(v18);
        break;
      case 25:
        Value = XmlReader::GetValue(this, &v16);
        v8 = *a2;
        goto LABEL_9;
      case 34:
        Value = XmlReader::GetValue(this, &v15);
        v8 = *a2 + 40;
LABEL_9:
        std::wstring::_Assign<wchar_t>(v8, *Value);
        continue;
      case 40:
        v11 = *(_OWORD *)XmlReader::GetValue(this, &v14);
        *(_BYTE *)(*a2 + 32) = EventManParser::ParseUInt8(this);
        v4 = 1;
        break;
    }
  }
  if ( !*(_QWORD *)(*a2 + 16) )
    EventManParser::ErrorWithFormatMessage(this, 3221745470LL, L"name");
  if ( !v4 )
    EventManParser::ErrorWithFormatMessage(this, 3221745470LL, L"value");
  return a2;
}

```

## disassembly

```asm
0x180038570  mov     [rsp-8+arg_10], rbx
0x180038575  push    rbp
0x180038576  push    rsi
0x180038577  push    rdi
0x180038578  lea     rbp, [rsp-47h]
0x18003857d  sub     rsp, 0C0h
0x180038584  mov     rax, cs:__security_cookie
0x18003858b  xor     rax, rsp
0x18003858e  mov     [rbp+57h+var_18], rax
0x180038592  mov     rdi, rdx
0x180038595  mov     rbx, rcx
0x180038598  mov     [rbp+57h+var_90], rdx
0x18003859c  mov     [rbp+57h+var_B0], 0
0x1800385a3  mov     rcx, rdx
0x1800385a6  call    ??$make_unique@VLEVEL_ENTRY@@$$V$0A@@std@@YA?AV?$unique_ptr@VLEVEL_ENTRY@@U?$default_delete@VLEVEL_ENTRY@@@std@@@0@XZ; std::make_unique<LEVEL_ENTRY,,0>(void)
0x1800385ab  mov     [rbp+57h+var_B0], 1
0x1800385b2  xor     sil, sil
0x1800385b5  mov     rcx, rbx; this
0x1800385b8  call    ?FirstAttribute@XmlReader@@QEAA_NXZ; XmlReader::FirstAttribute(void)
0x1800385bd  jmp     loc_180038694
0x1800385c2  lea     rdx, [rbp+57h+var_88]
0x1800385c6  mov     rcx, rbx; this
0x1800385c9  call    ?GetQualifiedName@XmlReader@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; XmlReader::GetQualifiedName(void)
0x1800385ce  movups  xmm0, xmmword ptr [rax]
0x1800385d1  movdqu  [rbp+57h+var_A0], xmm0
0x1800385d6  lea     rcx, [rbp+57h+var_A0]
0x1800385da  call    GetAttributeId
0x1800385df  cmp     al, 16h
0x1800385e1  jz      short loc_180038650
0x1800385e3  cmp     al, 19h
0x1800385e5  jz      short loc_180038633
0x1800385e7  cmp     al, 22h ; '"'
0x1800385e9  jz      short loc_18003861E
0x1800385eb  cmp     al, 28h ; '('
0x1800385ed  jnz     loc_18003868C
0x1800385f3  lea     rdx, [rbp+57h+var_78]
0x1800385f7  mov     rcx, rbx; this
0x1800385fa  call    ?GetValue@XmlReader@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; XmlReader::GetValue(void)
0x1800385ff  movups  xmm0, xmmword ptr [rax]
0x180038602  movdqu  [rbp+57h+var_A0], xmm0
0x180038607  lea     rdx, [rbp+57h+var_A0]
0x18003860b  mov     rcx, rbx; this
0x18003860e  call    ?ParseUInt8@EventManParser@@AEAAEV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; EventManParser::ParseUInt8(std::wstring_view)
0x180038613  mov     rcx, [rdi]
0x180038616  mov     [rcx+20h], al
0x180038619  mov     sil, 1
0x18003861c  jmp     short loc_18003868C
0x18003861e  lea     rdx, [rbp+57h+var_68]
0x180038622  mov     rcx, rbx; this
0x180038625  call    ?GetValue@XmlReader@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; XmlReader::GetValue(void)
0x18003862a  mov     rcx, [rdi]
0x18003862d  add     rcx, 28h ; '('
0x180038631  jmp     short loc_180038642
0x180038633  lea     rdx, [rbp+57h+var_58]
0x180038637  mov     rcx, rbx; this
0x18003863a  call    ?GetValue@XmlReader@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; XmlReader::GetValue(void)
0x18003863f  mov     rcx, [rdi]
0x180038642  mov     rdx, [rax]
0x180038645  mov     r8, [rax+8]
0x180038649  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x18003864e  jmp     short loc_18003868C
0x180038650  lea     rdx, [rbp+57h+var_48]
0x180038654  mov     rcx, rbx; this
0x180038657  call    ?GetValue@XmlReader@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; XmlReader::GetValue(void)
0x18003865c  movups  xmm0, xmmword ptr [rax]
0x18003865f  movdqu  [rbp+57h+var_A0], xmm0
0x180038664  lea     r8, [rbp+57h+var_A0]
0x180038668  lea     rdx, [rbp+57h+var_38]
0x18003866c  mov     rcx, rbx
0x18003866f  call    ?ParseStrTableRef@EventManParser@@AEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@3@@Z; EventManParser::ParseStrTableRef(std::wstring_view)
0x180038674  mov     rcx, [rdi]
0x180038677  add     rcx, 48h ; 'H'
0x18003867b  mov     rdx, rax
0x18003867e  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180038683  lea     rcx, [rbp+57h+var_38]
0x180038687  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003868c  mov     rcx, rbx; this
0x18003868f  call    ?NextAttribute@XmlReader@@QEAA_NXZ; XmlReader::NextAttribute(void)
0x180038694  test    al, al
0x180038696  jnz     loc_1800385C2
0x18003869c  mov     rax, [rdi]
0x18003869f  cmp     qword ptr [rax+10h], 0
0x1800386a4  jnz     short loc_1800386BA
0x1800386a6  lea     r8, aName_0; "name"
0x1800386ad  mov     edx, 0C007EF3Eh; int
0x1800386b2  mov     rcx, rbx; this
0x1800386b5  call    ?ErrorWithFormatMessage@EventManParser@@AEAAXJZZ; EventManParser::ErrorWithFormatMessage(long,...)
0x1800386ba  test    sil, sil
0x1800386bd  jnz     short loc_1800386D3
0x1800386bf  lea     r8, aValue; "value"
0x1800386c6  mov     edx, 0C007EF3Eh; int
0x1800386cb  mov     rcx, rbx; this
0x1800386ce  call    ?ErrorWithFormatMessage@EventManParser@@AEAAXJZZ; EventManParser::ErrorWithFormatMessage(long,...)
0x1800386d3  mov     rax, rdi
0x1800386d6  mov     rcx, [rbp+57h+var_18]
0x1800386da  xor     rcx, rsp; StackCookie
0x1800386dd  call    __security_check_cookie
0x1800386e2  mov     rbx, [rsp+0D0h+arg_10]
0x1800386ea  add     rsp, 0C0h
0x1800386f1  pop     rdi
0x1800386f2  pop     rsi
0x1800386f3  pop     rbp
0x1800386f4  retn
```
