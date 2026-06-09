# EventManParser::ValueMapValueType(void)

- ea: `0x18003c084`
- end: `0x18003c201`
- name: `?ValueMapValueType@EventManParser@@AEAA?AV?$unique_ptr@VMAP_ENTRY@@U?$default_delete@VMAP_ENTRY@@@std@@@std@@XZ`
- size: `381`
- prototype: `_QWORD *__fastcall(XmlReader *this, _QWORD *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config`

## callers

- `0x180011b30`

## callees

- `0x18001df64`
- `0x18001e0cc`
- `0x18001e284`
- `0x18001e4d8`
- `0x18001e550`
- `0x18001e8f0`
- `0x18001e930`
- `0x1800207c0`
- `0x180031310`
- `0x180033da0`
- `0x180037670`
- `0x180039610`
- `0x18003c084`
- `0x18003c754`

## pseudocode

```c
_QWORD *__fastcall EventManParser::ValueMapValueType(XmlReader *this, _QWORD *a2)
{
  char v4; // si
  char AttributeId; // al
  _QWORD *Value; // rax
  __int64 v7; // rax
  int v9; // [rsp+20h] [rbp-49h] BYREF
  int v10; // [rsp+24h] [rbp-45h]
  __int128 v11; // [rsp+30h] [rbp-39h] BYREF
  _QWORD *v12; // [rsp+40h] [rbp-29h]
  _BYTE v13[32]; // [rsp+88h] [rbp+1Fh] BYREF

  v12 = a2;
  v10 = 0;
  v9 = 1;
  std::make_unique<MAP_ENTRY,enum _MAP_FLAGS,0>(a2, &v9);
  v10 = 1;
  v4 = 0;
  if ( !XmlReader::FirstAttribute(this) )
    goto LABEL_10;
  do
  {
    v11 = *(_OWORD *)XmlReader::GetQualifiedName(this);
    AttributeId = GetAttributeId(&v11);
    switch ( AttributeId )
    {
      case 22:
        v11 = *(_OWORD *)XmlReader::GetValue(this);
        v7 = EventManParser::ParseStrTableRef(this, v13, &v11);
        std::wstring::operator=(*a2 + 32LL, v7);
        std::wstring::_Tidy_deallocate(v13);
        break;
      case 34:
        Value = (_QWORD *)XmlReader::GetValue(this);
        std::wstring::_Assign<wchar_t>(*a2, *Value, Value[1]);
        break;
      case 40:
        v11 = *(_OWORD *)XmlReader::GetValue(this);
        *(_DWORD *)(*a2 + 64LL) = EventManParser::ParseUInt32(this);
        v4 = 1;
        break;
    }
  }
  while ( XmlReader::NextAttribute(this) );
  if ( !v4 )
LABEL_10:
    EventManParser::ErrorWithFormatMessage(this, -1073221826, L"value");
  if ( !*(_QWORD *)(*a2 + 48LL) )
    EventManParser::ErrorWithFormatMessage(this, -1073221826, L"message");
  return a2;
}

```

## disassembly

```asm
0x18003c084  mov     [rsp-8+arg_10], rbx
0x18003c089  push    rbp
0x18003c08a  push    rsi
0x18003c08b  push    rdi
0x18003c08c  lea     rbp, [rsp-47h]
0x18003c091  sub     rsp, 0B0h
0x18003c098  mov     rax, cs:__security_cookie
0x18003c09f  xor     rax, rsp
0x18003c0a2  mov     [rbp+57h+var_18], rax
0x18003c0a6  mov     rdi, rdx
0x18003c0a9  mov     rbx, rcx
0x18003c0ac  mov     [rbp+57h+var_80], rdx
0x18003c0b0  mov     [rbp+57h+var_9C], 0
0x18003c0b7  mov     [rbp+57h+var_A0], 1
0x18003c0be  lea     rdx, [rbp+57h+var_A0]
0x18003c0c2  mov     rcx, rdi
0x18003c0c5  call    ??$make_unique@VMAP_ENTRY@@W4_MAP_FLAGS@@$0A@@std@@YA?AV?$unique_ptr@VMAP_ENTRY@@U?$default_delete@VMAP_ENTRY@@@std@@@0@$$QEAW4_MAP_FLAGS@@@Z; std::make_unique<MAP_ENTRY,_MAP_FLAGS,0>(_MAP_FLAGS &&)
0x18003c0ca  mov     [rbp+57h+var_9C], 1
0x18003c0d1  xor     sil, sil
0x18003c0d4  mov     rcx, rbx; this
0x18003c0d7  call    ?FirstAttribute@XmlReader@@QEAA_NXZ; XmlReader::FirstAttribute(void)
0x18003c0dc  test    al, al
0x18003c0de  jz      loc_18003C1AC
0x18003c0e4  lea     rdx, [rbp+57h+var_78]
0x18003c0e8  mov     rcx, rbx; this
0x18003c0eb  call    ?GetQualifiedName@XmlReader@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; XmlReader::GetQualifiedName(void)
0x18003c0f0  movups  xmm0, xmmword ptr [rax]
0x18003c0f3  movdqu  [rbp+57h+var_90], xmm0
0x18003c0f8  lea     rcx, [rbp+57h+var_90]
0x18003c0fc  call    GetAttributeId
0x18003c101  cmp     al, 16h
0x18003c103  jz      short loc_18003C15B
0x18003c105  cmp     al, 22h ; '"'
0x18003c107  jz      short loc_18003C13E
0x18003c109  cmp     al, 28h ; '('
0x18003c10b  jnz     loc_18003C197
0x18003c111  lea     rdx, [rbp+57h+var_68]
0x18003c115  mov     rcx, rbx; this
0x18003c118  call    ?GetValue@XmlReader@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; XmlReader::GetValue(void)
0x18003c11d  movups  xmm0, xmmword ptr [rax]
0x18003c120  movdqu  [rbp+57h+var_90], xmm0
0x18003c125  lea     rdx, [rbp+57h+var_90]
0x18003c129  mov     rcx, rbx; this
0x18003c12c  call    ?ParseUInt32@EventManParser@@AEAAIV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; EventManParser::ParseUInt32(std::wstring_view)
0x18003c131  mov     ecx, eax
0x18003c133  mov     rax, [rdi]
0x18003c136  mov     [rax+40h], ecx
0x18003c139  mov     sil, 1
0x18003c13c  jmp     short loc_18003C197
0x18003c13e  lea     rdx, [rbp+57h+var_58]
0x18003c142  mov     rcx, rbx; this
0x18003c145  call    ?GetValue@XmlReader@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; XmlReader::GetValue(void)
0x18003c14a  mov     r8, [rax+8]
0x18003c14e  mov     rdx, [rax]
0x18003c151  mov     rcx, [rdi]
0x18003c154  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x18003c159  jmp     short loc_18003C197
0x18003c15b  lea     rdx, [rbp+57h+var_48]
0x18003c15f  mov     rcx, rbx; this
0x18003c162  call    ?GetValue@XmlReader@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; XmlReader::GetValue(void)
0x18003c167  movups  xmm0, xmmword ptr [rax]
0x18003c16a  movdqu  [rbp+57h+var_90], xmm0
0x18003c16f  lea     r8, [rbp+57h+var_90]
0x18003c173  lea     rdx, [rbp+57h+var_38]
0x18003c177  mov     rcx, rbx
0x18003c17a  call    ?ParseStrTableRef@EventManParser@@AEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@3@@Z; EventManParser::ParseStrTableRef(std::wstring_view)
0x18003c17f  mov     rcx, [rdi]
0x18003c182  add     rcx, 20h ; ' '
0x18003c186  mov     rdx, rax
0x18003c189  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18003c18e  lea     rcx, [rbp+57h+var_38]
0x18003c192  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003c197  mov     rcx, rbx; this
0x18003c19a  call    ?NextAttribute@XmlReader@@QEAA_NXZ; XmlReader::NextAttribute(void)
0x18003c19f  test    al, al
0x18003c1a1  jnz     loc_18003C0E4
0x18003c1a7  test    sil, sil
0x18003c1aa  jnz     short loc_18003C1C0
0x18003c1ac  lea     r8, aValue; "value"
0x18003c1b3  mov     edx, 0C007EF3Eh; int
0x18003c1b8  mov     rcx, rbx; this
0x18003c1bb  call    ?ErrorWithFormatMessage@EventManParser@@AEAAXJZZ; EventManParser::ErrorWithFormatMessage(long,...)
0x18003c1c0  mov     r8, [rdi]
0x18003c1c3  cmp     qword ptr [r8+30h], 0
0x18003c1c8  jnz     short loc_18003C1DE
0x18003c1ca  lea     r8, aMessage; "message"
0x18003c1d1  mov     edx, 0C007EF3Eh; int
0x18003c1d6  mov     rcx, rbx; this
0x18003c1d9  call    ?ErrorWithFormatMessage@EventManParser@@AEAAXJZZ; EventManParser::ErrorWithFormatMessage(long,...)
0x18003c1de  mov     rax, rdi
0x18003c1e1  mov     rcx, [rbp+57h+var_18]
0x18003c1e5  xor     rcx, rsp; StackCookie
0x18003c1e8  call    __security_check_cookie
0x18003c1ed  mov     rbx, [rsp+0C0h+arg_10]
0x18003c1f5  add     rsp, 0B0h
0x18003c1fc  pop     rdi
0x18003c1fd  pop     rsi
0x18003c1fe  pop     rbp
0x18003c1ff  retn
```
