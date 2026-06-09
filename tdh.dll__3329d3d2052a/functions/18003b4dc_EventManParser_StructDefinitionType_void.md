# EventManParser::StructDefinitionType(void)

- ea: `0x18003b4dc`
- end: `0x18003b6ef`
- name: `?StructDefinitionType@EventManParser@@AEAA?AV?$unique_ptr@VPROPERTY_ENTRY@@U?$default_delete@VPROPERTY_ENTRY@@@std@@@std@@XZ`
- size: `531`
- prototype: `_QWORD *__fastcall(XmlReader *this, _QWORD *)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config`

## callers

- `0x18001d810`

## callees

- `0x18001cb90`
- `0x18001df64`
- `0x18001e284`
- `0x18001e4d8`
- `0x18001e550`
- `0x18001e8f0`
- `0x18001e930`
- `0x18002ea38`
- `0x1800313f8`
- `0x180032cdc`
- `0x1800355ac`
- `0x180035858`
- `0x180037670`
- `0x180037e80`
- `0x180038cc4`
- `0x18003941c`
- `0x180039610`
- `0x18003b4dc`

## pseudocode

```c
_QWORD *__fastcall EventManParser::StructDefinitionType(XmlReader *this, _QWORD *a2)
{
  bool i; // al
  char AttributeId; // al
  _QWORD *Value; // rax
  __int64 v7; // rbx
  __int64 v8; // rcx
  bool j; // al
  __int64 v10; // rbx
  __int64 *v11; // rax
  __int64 *v12; // rdx
  __int64 v13; // rcx
  int v15; // [rsp+20h] [rbp-60h]
  _OWORD v16[4]; // [rsp+30h] [rbp-50h] BYREF
  __int64 v17; // [rsp+B0h] [rbp+30h] BYREF

  LOBYTE(v17) = 1;
  std::make_unique<PROPERTY_ENTRY,bool,0>(a2, &v17);
  v15 = 1;
  for ( i = XmlReader::FirstAttribute(this); i; i = XmlReader::NextAttribute(this) )
  {
    v16[0] = *(_OWORD *)XmlReader::GetQualifiedName(this);
    AttributeId = GetAttributeId(v16);
    switch ( AttributeId )
    {
      case 5:
        v7 = *a2;
        v16[0] = *(_OWORD *)XmlReader::GetValue(this);
        EventManParser::ParseCountOrLength(v8, v16, v7 + 128, v7 + 136, v15);
        break;
      case 25:
        Value = (_QWORD *)XmlReader::GetValue(this);
        std::wstring::_Assign<wchar_t>(*a2, *Value, Value[1]);
        break;
      case 35:
        v16[0] = *(_OWORD *)XmlReader::GetValue(this);
        *(_DWORD *)(*a2 + 212LL) = EventManParser::ParseUInt32(this);
        break;
    }
  }
  if ( !*(_QWORD *)(*a2 + 16LL) )
    EventManParser::ErrorWithFormatMessage(this, -1073221826, L"name");
  for ( j = XmlReader::FirstChildElement(this); j; j = XmlReader::NextChildElement(this) )
  {
    XmlReader::GetLocalName(this);
    v16[2] = v16[1];
    v16[3] = *(_OWORD *)&off_18004F7F0;
    *(_QWORD *)&v16[0] = L"data";
    *((_QWORD *)&v16[0] + 1) = 4;
    if ( (unsigned __int8)EventManParser::ElementMatches(this) )
    {
      v10 = *a2;
      v11 = EventManParser::DataDefinitionType(this, &v17);
      v12 = *(__int64 **)(v10 + 224);
      if ( v12 == *(__int64 **)(v10 + 232) )
      {
        std::vector<std::unique_ptr<PROPERTY_ENTRY>>::_Emplace_reallocate<std::unique_ptr<PROPERTY_ENTRY>>(
          v10 + 216,
          v12,
          v11);
      }
      else
      {
        v13 = *v11;
        *v11 = 0;
        *v12 = v13;
        *(_QWORD *)(v10 + 224) += 8LL;
      }
      std::unique_ptr<PROPERTY_ENTRY>::~unique_ptr<PROPERTY_ENTRY>(&v17);
    }
  }
  if ( *(_QWORD *)(*a2 + 216LL) == *(_QWORD *)(*a2 + 224LL) )
    EventManParser::ErrorWithFormatMessage(this, -1073221829, L"data");
  return a2;
}

```

## disassembly

```asm
0x18003b4dc  mov     [rsp-18h+arg_0], rbx
0x18003b4e1  mov     [rsp-18h+arg_18], rsi
0x18003b4e6  mov     [rsp-18h+arg_8], rdx
0x18003b4eb  push    rbp
0x18003b4ec  push    rdi
0x18003b4ed  push    r15
0x18003b4ef  mov     rbp, rsp
0x18003b4f2  sub     rsp, 80h
0x18003b4f9  mov     rsi, rdx
0x18003b4fc  mov     rdi, rcx
0x18003b4ff  mov     [rbp+var_60], 0
0x18003b506  mov     byte ptr [rbp+arg_10], 1
0x18003b50a  lea     rdx, [rbp+arg_10]
0x18003b50e  mov     rcx, rsi
0x18003b511  call    ??$make_unique@VPROPERTY_ENTRY@@_N$0A@@std@@YA?AV?$unique_ptr@VPROPERTY_ENTRY@@U?$default_delete@VPROPERTY_ENTRY@@@std@@@0@$$QEA_N@Z; std::make_unique<PROPERTY_ENTRY,bool,0>(bool &&)
0x18003b516  mov     [rbp+var_60], 1
0x18003b51d  mov     rcx, rdi; this
0x18003b520  call    ?FirstAttribute@XmlReader@@QEAA_NXZ; XmlReader::FirstAttribute(void)
0x18003b525  jmp     loc_18003B5D1
0x18003b52a  lea     rdx, [rbp+var_20]
0x18003b52e  mov     rcx, rdi; this
0x18003b531  call    ?GetQualifiedName@XmlReader@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; XmlReader::GetQualifiedName(void)
0x18003b536  movups  xmm0, xmmword ptr [rax]
0x18003b539  movdqu  [rbp+var_50], xmm0
0x18003b53e  lea     rcx, [rbp+var_50]
0x18003b542  call    GetAttributeId
0x18003b547  cmp     al, 5
0x18003b549  jz      short loc_18003B59B
0x18003b54b  cmp     al, 19h
0x18003b54d  jz      short loc_18003B57E
0x18003b54f  cmp     al, 23h ; '#'
0x18003b551  jnz     short loc_18003B5C9
0x18003b553  lea     rdx, [rbp+var_30]
0x18003b557  mov     rcx, rdi; this
0x18003b55a  call    ?GetValue@XmlReader@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; XmlReader::GetValue(void)
0x18003b55f  movups  xmm0, xmmword ptr [rax]
0x18003b562  movdqu  [rbp+var_50], xmm0
0x18003b567  lea     rdx, [rbp+var_50]
0x18003b56b  mov     rcx, rdi; this
0x18003b56e  call    ?ParseUInt32@EventManParser@@AEAAIV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; EventManParser::ParseUInt32(std::wstring_view)
0x18003b573  mov     rcx, [rsi]
0x18003b576  mov     [rcx+0D4h], eax
0x18003b57c  jmp     short loc_18003B5C9
0x18003b57e  lea     rdx, [rbp+var_40]
0x18003b582  mov     rcx, rdi; this
0x18003b585  call    ?GetValue@XmlReader@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; XmlReader::GetValue(void)
0x18003b58a  mov     r8, [rax+8]
0x18003b58e  mov     rdx, [rax]
0x18003b591  mov     rcx, [rsi]
0x18003b594  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x18003b599  jmp     short loc_18003B5C9
0x18003b59b  mov     rbx, [rsi]
0x18003b59e  lea     rdx, [rbp+var_10]
0x18003b5a2  mov     rcx, rdi; this
0x18003b5a5  call    ?GetValue@XmlReader@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; XmlReader::GetValue(void)
0x18003b5aa  movups  xmm0, xmmword ptr [rax]
0x18003b5ad  movdqu  [rbp+var_50], xmm0
0x18003b5b2  lea     r9, [rbx+88h]
0x18003b5b9  lea     r8, [rbx+80h]
0x18003b5c0  lea     rdx, [rbp+var_50]
0x18003b5c4  call    ?ParseCountOrLength@EventManParser@@AEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@PEAGPEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@3@@Z; EventManParser::ParseCountOrLength(std::wstring_view,ushort *,std::wstring *)
0x18003b5c9  mov     rcx, rdi; this
0x18003b5cc  call    ?NextAttribute@XmlReader@@QEAA_NXZ; XmlReader::NextAttribute(void)
0x18003b5d1  test    al, al
0x18003b5d3  jnz     loc_18003B52A
0x18003b5d9  mov     rax, [rsi]
0x18003b5dc  cmp     qword ptr [rax+10h], 0
0x18003b5e1  jnz     short loc_18003B5F7
0x18003b5e3  lea     r8, aName_0; "name"
0x18003b5ea  mov     edx, 0C007EF3Eh; int
0x18003b5ef  mov     rcx, rdi; this
0x18003b5f2  call    ?ErrorWithFormatMessage@EventManParser@@AEAAXJZZ; EventManParser::ErrorWithFormatMessage(long,...)
0x18003b5f7  mov     rcx, rdi; this
0x18003b5fa  call    ?FirstChildElement@XmlReader@@QEAA_NXZ; XmlReader::FirstChildElement(void)
0x18003b5ff  lea     r15, aData_0; "data"
0x18003b606  jmp     loc_18003B6A8
0x18003b60b  lea     rdx, [rbp+var_40]
0x18003b60f  mov     rcx, rdi; this
0x18003b612  call    ?GetLocalName@XmlReader@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; XmlReader::GetLocalName(void)
0x18003b617  movups  xmm0, [rbp+var_40]
0x18003b61b  movups  xmm1, xmmword ptr cs:off_18004F7F0; "http://schemas.microsoft.com/win/2004/0"...
0x18003b622  movdqu  [rbp+var_30], xmm0
0x18003b627  movdqu  [rbp+var_20], xmm1
0x18003b62c  mov     qword ptr [rbp+var_50], r15
0x18003b630  mov     qword ptr [rbp+var_50+8], 4
0x18003b638  lea     r9, [rbp+var_30]
0x18003b63c  lea     r8, [rbp+var_20]
0x18003b640  lea     rdx, [rbp+var_50]
0x18003b644  mov     rcx, rdi; this
0x18003b647  call    ?ElementMatches@EventManParser@@AEBA_NV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@00@Z; EventManParser::ElementMatches(std::wstring_view,std::wstring_view,std::wstring_view)
0x18003b64c  test    al, al
0x18003b64e  jz      short loc_18003B6A0
0x18003b650  mov     rbx, [rsi]
0x18003b653  lea     rdx, [rbp+arg_10]
0x18003b657  mov     rcx, rdi; this
0x18003b65a  call    ?DataDefinitionType@EventManParser@@AEAA?AV?$unique_ptr@VPROPERTY_ENTRY@@U?$default_delete@VPROPERTY_ENTRY@@@std@@@std@@XZ; EventManParser::DataDefinitionType(void)
0x18003b65f  nop
0x18003b660  mov     rdx, [rbx+0E0h]
0x18003b667  cmp     rdx, [rbx+0E8h]
0x18003b66e  jz      short loc_18003B687
0x18003b670  mov     rcx, [rax]
0x18003b673  mov     qword ptr [rax], 0
0x18003b67a  mov     [rdx], rcx
0x18003b67d  add     qword ptr [rbx+0E0h], 8
0x18003b685  jmp     short loc_18003B697
0x18003b687  mov     r8, rax
0x18003b68a  lea     rcx, [rbx+0D8h]
0x18003b691  call    ??$_Emplace_reallocate@V?$unique_ptr@VPROPERTY_ENTRY@@U?$default_delete@VPROPERTY_ENTRY@@@std@@@std@@@?$vector@V?$unique_ptr@VPROPERTY_ENTRY@@U?$default_delete@VPROPERTY_ENTRY@@@std@@@std@@V?$allocator@V?$unique_ptr@VPROPERTY_ENTRY@@U?$default_delete@VPROPERTY_ENTRY@@@std@@@std@@@2@@std@@AEAAPEAV?$unique_ptr@VPROPERTY_ENTRY@@U?$default_delete@VPROPERTY_ENTRY@@@std@@@1@QEAV21@$$QEAV21@@Z; std::vector<std::unique_ptr<PROPERTY_ENTRY>>::_Emplace_reallocate<std::unique_ptr<PROPERTY_ENTRY>>(std::unique_ptr<PROPERTY_ENTRY> * const,std::unique_ptr<PROPERTY_ENTRY> &&)
0x18003b696  nop
0x18003b697  lea     rcx, [rbp+arg_10]
0x18003b69b  call    ??1?$unique_ptr@VPROPERTY_ENTRY@@U?$default_delete@VPROPERTY_ENTRY@@@std@@@std@@QEAA@XZ; std::unique_ptr<PROPERTY_ENTRY>::~unique_ptr<PROPERTY_ENTRY>(void)
0x18003b6a0  mov     rcx, rdi; this
0x18003b6a3  call    ?NextChildElement@XmlReader@@QEAA_NXZ; XmlReader::NextChildElement(void)
0x18003b6a8  test    al, al
0x18003b6aa  jnz     loc_18003B60B
0x18003b6b0  mov     rcx, [rsi]
0x18003b6b3  mov     rax, [rcx+0E0h]
0x18003b6ba  cmp     [rcx+0D8h], rax
0x18003b6c1  jnz     short loc_18003B6D3
0x18003b6c3  mov     r8, r15
0x18003b6c6  mov     edx, 0C007EF3Bh; int
0x18003b6cb  mov     rcx, rdi; this
0x18003b6ce  call    ?ErrorWithFormatMessage@EventManParser@@AEAAXJZZ; EventManParser::ErrorWithFormatMessage(long,...)
0x18003b6d3  mov     rax, rsi
0x18003b6d6  lea     r11, [rsp+80h+var_s0]
0x18003b6de  mov     rbx, [r11+20h]
0x18003b6e2  mov     rsi, [r11+38h]
0x18003b6e6  mov     rsp, r11
0x18003b6e9  pop     r15
0x18003b6eb  pop     rdi
0x18003b6ec  pop     rbp
0x18003b6ed  retn
```
