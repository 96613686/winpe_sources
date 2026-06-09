# EventManParser::EventDefinitionType(void)

- ea: `0x180035aa0`
- end: `0x180035e00`
- name: `?EventDefinitionType@EventManParser@@AEAA?AV?$unique_ptr@VEVENT_ENTRY@@U?$default_delete@VEVENT_ENTRY@@@std@@@std@@XZ`
- size: `864`
- prototype: `__int64 __fastcall(XmlReader *this)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config`

## callers

- `0x180035780`

## callees

- `0x18001df64`
- `0x18001e0cc`
- `0x18001e284`
- `0x18001e4d8`
- `0x18001e550`
- `0x18001e8f0`
- `0x18001e930`
- `0x1800207c0`
- `0x1800207e4`
- `0x180031edc`
- `0x180033da0`
- `0x180035aa0`
- `0x180037670`
- `0x180039328`
- `0x180039610`
- `0x180039674`
- `0x18003b0bc`
- `0x18003c754`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 *__fastcall EventManParser::EventDefinitionType(XmlReader *this, __int64 *a2)
{
  char v4; // r14
  unsigned __int8 AttributeId; // al
  _QWORD *Value; // rax
  __int64 v7; // rcx
  __int64 v8; // rax
  __int64 v9; // rbx
  __int128 v11; // [rsp+20h] [rbp-E0h] BYREF
  int v12; // [rsp+30h] [rbp-D0h]
  __int64 *v13; // [rsp+38h] [rbp-C8h]
  __int64 v14; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v15; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v16; // [rsp+70h] [rbp-90h] BYREF
  __int64 v17; // [rsp+80h] [rbp-80h] BYREF
  __int64 v18; // [rsp+90h] [rbp-70h] BYREF
  __int64 v19; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v20; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v21; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v22; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v23; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v24; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v25; // [rsp+100h] [rbp+0h] BYREF
  __int64 v26; // [rsp+110h] [rbp+10h] BYREF
  __int64 v27; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v28[32]; // [rsp+130h] [rbp+30h] BYREF

  v13 = a2;
  *(_QWORD *)&v11 = operator new(0x190u);
  *a2 = (__int64)EVENT_ENTRY::EVENT_ENTRY((EVENT_ENTRY *)v11);
  v12 = 3;
  v4 = 0;
  if ( !XmlReader::FirstAttribute(this) )
  {
LABEL_34:
    EventManParser::ErrorWithFormatMessage(this, 3221745470LL, L"value");
    return a2;
  }
  do
  {
    v11 = *(_OWORD *)XmlReader::GetQualifiedName(this);
    AttributeId = GetAttributeId(&v11);
    if ( AttributeId > 0x1Cu )
    {
      switch ( AttributeId )
      {
        case '!':
          v11 = *(_OWORD *)XmlReader::GetValue(this, &v27);
          *(_BYTE *)(*a2 + 322) = EventManParser::ParseBool(this);
          break;
        case '"':
          Value = XmlReader::GetValue(this, &v26);
          v7 = *a2 + 232;
          goto LABEL_13;
        case '$':
          Value = XmlReader::GetValue(this, &v25);
          v7 = *a2 + 168;
          goto LABEL_13;
        case '%':
          Value = XmlReader::GetValue(this, &v24);
          v7 = *a2 + 200;
          goto LABEL_13;
        case '(':
          v11 = *(_OWORD *)XmlReader::GetValue(this, &v23);
          *(_DWORD *)*a2 = EventManParser::ParseUInt32(this);
          v4 = 1;
          break;
        case ')':
          v11 = *(_OWORD *)XmlReader::GetValue(this, &v22);
          *(_BYTE *)(*a2 + 4) = EventManParser::ParseUInt8(this);
          break;
      }
    }
    else
    {
      switch ( AttributeId )
      {
        case 0x1Cu:
          Value = XmlReader::GetValue(this, &v21);
          v7 = *a2 + 136;
          goto LABEL_13;
        case 1u:
          Value = XmlReader::GetValue(this, &v20);
          v7 = *a2 + 40;
          goto LABEL_13;
        case 2u:
          Value = XmlReader::GetValue(this, &v19);
          v7 = *a2 + 72;
          goto LABEL_13;
        case 0x11u:
          v9 = *a2;
          v11 = *(_OWORD *)XmlReader::GetValue(this, &v18);
          SplitStringToSubstrings(&v11, v9 + 296);
          break;
        case 0x13u:
          Value = XmlReader::GetValue(this, &v17);
          v7 = *a2 + 104;
          goto LABEL_13;
        case 0x16u:
          v11 = *(_OWORD *)XmlReader::GetValue(this, &v16);
          v8 = EventManParser::ParseStrTableRef(this, v28, &v11);
          std::wstring::operator=(*a2 + 264, v8);
          std::wstring::_Tidy_deallocate(v28);
          break;
        case 0x19u:
          Value = XmlReader::GetValue(this, &v15);
          v7 = *a2 + 8;
LABEL_13:
          std::wstring::_Assign<wchar_t>(v7, *Value);
          break;
        case 0x1Bu:
          v11 = *(_OWORD *)XmlReader::GetValue(this, &v14);
          *(_BYTE *)(*a2 + 321) = EventManParser::ParseBool(this);
          break;
      }
    }
  }
  while ( XmlReader::NextAttribute(this) );
  if ( !v4 )
    goto LABEL_34;
  return a2;
}

```

## disassembly

```asm
0x180035aa0  mov     [rsp-8+arg_10], rbx
0x180035aa5  mov     [rsp-8+arg_18], rsi
0x180035aaa  push    rbp
0x180035aab  push    rdi
0x180035aac  push    r14
0x180035aae  lea     rbp, [rsp-60h]
0x180035ab3  sub     rsp, 160h
0x180035aba  mov     rax, cs:__security_cookie
0x180035ac1  xor     rax, rsp
0x180035ac4  mov     [rbp+70h+var_20], rax
0x180035ac8  mov     rsi, rdx
0x180035acb  mov     rdi, rcx
0x180035ace  mov     [rsp+170h+var_138], rdx
0x180035ad3  mov     [rsp+170h+var_140], 0
0x180035adb  mov     ecx, 190h; Size
0x180035ae0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180035ae5  mov     qword ptr [rsp+170h+var_150], rax
0x180035aea  mov     rcx, rax; this
0x180035aed  call    ??0EVENT_ENTRY@@QEAA@XZ; EVENT_ENTRY::EVENT_ENTRY(void)
0x180035af2  mov     [rsi], rax
0x180035af5  mov     [rsp+170h+var_140], 3
0x180035afd  xor     r14b, r14b
0x180035b00  mov     rcx, rdi; this
0x180035b03  call    ?FirstAttribute@XmlReader@@QEAA_NXZ; XmlReader::FirstAttribute(void)
0x180035b08  test    al, al
0x180035b0a  jz      loc_180035DC4
0x180035b10  lea     rdx, [rsp+170h+var_130]
0x180035b15  mov     rcx, rdi; this
0x180035b18  call    ?GetQualifiedName@XmlReader@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; XmlReader::GetQualifiedName(void)
0x180035b1d  movups  xmm0, xmmword ptr [rax]
0x180035b20  movdqu  [rsp+170h+var_150], xmm0
0x180035b26  lea     rcx, [rsp+170h+var_150]
0x180035b2b  call    GetAttributeId
0x180035b30  movzx   ecx, al
0x180035b33  cmp     ecx, 1Ch
0x180035b36  ja      loc_180035CA6
0x180035b3c  jz      loc_180035C8B
0x180035b42  sub     ecx, 1
0x180035b45  jz      loc_180035C73
0x180035b4b  sub     ecx, 1
0x180035b4e  jz      loc_180035C5B
0x180035b54  sub     ecx, 0Fh
0x180035b57  jz      loc_180035C2D
0x180035b5d  sub     ecx, 2
0x180035b60  jz      loc_180035C18
0x180035b66  sub     ecx, 3
0x180035b69  jz      short loc_180035BD1
0x180035b6b  sub     ecx, 3
0x180035b6e  jz      short loc_180035BAC
0x180035b70  cmp     ecx, 2
0x180035b73  jnz     loc_180035DAF
0x180035b79  lea     rdx, [rsp+170h+var_120]
0x180035b7e  mov     rcx, rdi; this
0x180035b81  call    ?GetValue@XmlReader@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; XmlReader::GetValue(void)
0x180035b86  movups  xmm0, xmmword ptr [rax]
0x180035b89  movdqu  [rsp+170h+var_150], xmm0
0x180035b8f  lea     rdx, [rsp+170h+var_150]
0x180035b94  mov     rcx, rdi; this
0x180035b97  call    ?ParseBool@EventManParser@@AEAA_NV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; EventManParser::ParseBool(std::wstring_view)
0x180035b9c  mov     cl, al
0x180035b9e  mov     rax, [rsi]
0x180035ba1  mov     [rax+141h], cl
0x180035ba7  jmp     loc_180035DAF
0x180035bac  lea     rdx, [rsp+170h+var_110]
0x180035bb1  mov     rcx, rdi; this
0x180035bb4  call    ?GetValue@XmlReader@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; XmlReader::GetValue(void)
0x180035bb9  mov     rcx, [rsi]
0x180035bbc  add     rcx, 8
0x180035bc0  mov     r8, [rax+8]
0x180035bc4  mov     rdx, [rax]
0x180035bc7  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x180035bcc  jmp     loc_180035DAF
0x180035bd1  lea     rdx, [rsp+170h+var_100]
0x180035bd6  mov     rcx, rdi; this
0x180035bd9  call    ?GetValue@XmlReader@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; XmlReader::GetValue(void)
0x180035bde  movups  xmm0, xmmword ptr [rax]
0x180035be1  movdqu  [rsp+170h+var_150], xmm0
0x180035be7  lea     r8, [rsp+170h+var_150]
0x180035bec  lea     rdx, [rbp+70h+var_40]
0x180035bf0  mov     rcx, rdi
0x180035bf3  call    ?ParseStrTableRef@EventManParser@@AEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@3@@Z; EventManParser::ParseStrTableRef(std::wstring_view)
0x180035bf8  mov     rcx, [rsi]
0x180035bfb  add     rcx, 108h
0x180035c02  mov     rdx, rax
0x180035c05  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180035c0a  lea     rcx, [rbp+70h+var_40]
0x180035c0e  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180035c13  jmp     loc_180035DAF
0x180035c18  lea     rdx, [rbp+70h+var_F0]
0x180035c1c  mov     rcx, rdi; this
0x180035c1f  call    ?GetValue@XmlReader@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; XmlReader::GetValue(void)
0x180035c24  mov     rcx, [rsi]
0x180035c27  add     rcx, 68h ; 'h'
0x180035c2b  jmp     short loc_180035BC0
0x180035c2d  mov     rbx, [rsi]
0x180035c30  lea     rdx, [rbp+70h+var_E0]
0x180035c34  mov     rcx, rdi; this
0x180035c37  call    ?GetValue@XmlReader@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; XmlReader::GetValue(void)
0x180035c3c  movups  xmm0, xmmword ptr [rax]
0x180035c3f  movdqu  [rsp+170h+var_150], xmm0
0x180035c45  lea     rdx, [rbx+128h]
0x180035c4c  lea     rcx, [rsp+170h+var_150]
0x180035c51  call    SplitStringToSubstrings
0x180035c56  jmp     loc_180035DAF
0x180035c5b  lea     rdx, [rbp+70h+var_D0]
0x180035c5f  mov     rcx, rdi; this
0x180035c62  call    ?GetValue@XmlReader@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; XmlReader::GetValue(void)
0x180035c67  mov     rcx, [rsi]
0x180035c6a  add     rcx, 48h ; 'H'
0x180035c6e  jmp     loc_180035BC0
0x180035c73  lea     rdx, [rbp+70h+var_C0]
0x180035c77  mov     rcx, rdi; this
0x180035c7a  call    ?GetValue@XmlReader@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; XmlReader::GetValue(void)
0x180035c7f  mov     rcx, [rsi]
0x180035c82  add     rcx, 28h ; '('
0x180035c86  jmp     loc_180035BC0
0x180035c8b  lea     rdx, [rbp+70h+var_B0]
0x180035c8f  mov     rcx, rdi; this
0x180035c92  call    ?GetValue@XmlReader@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; XmlReader::GetValue(void)
0x180035c97  mov     rcx, [rsi]
0x180035c9a  add     rcx, 88h
0x180035ca1  jmp     loc_180035BC0
0x180035ca6  sub     ecx, 21h ; '!'
0x180035ca9  jz      loc_180035D82
0x180035caf  sub     ecx, 1
0x180035cb2  jz      loc_180035D67
0x180035cb8  sub     ecx, 2
0x180035cbb  jz      loc_180035D4C
0x180035cc1  sub     ecx, 1
0x180035cc4  jz      short loc_180035D31
0x180035cc6  sub     ecx, 3
0x180035cc9  jz      short loc_180035D03
0x180035ccb  cmp     ecx, 1
0x180035cce  jnz     loc_180035DAF
0x180035cd4  lea     rdx, [rbp+70h+var_A0]
0x180035cd8  mov     rcx, rdi; this
0x180035cdb  call    ?GetValue@XmlReader@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; XmlReader::GetValue(void)
0x180035ce0  movups  xmm0, xmmword ptr [rax]
0x180035ce3  movdqu  [rsp+170h+var_150], xmm0
0x180035ce9  lea     rdx, [rsp+170h+var_150]
0x180035cee  mov     rcx, rdi; this
0x180035cf1  call    ?ParseUInt8@EventManParser@@AEAAEV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; EventManParser::ParseUInt8(std::wstring_view)
0x180035cf6  mov     cl, al
0x180035cf8  mov     rax, [rsi]
0x180035cfb  mov     [rax+4], cl
0x180035cfe  jmp     loc_180035DAF
0x180035d03  lea     rdx, [rbp+70h+var_90]
0x180035d07  mov     rcx, rdi; this
0x180035d0a  call    ?GetValue@XmlReader@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; XmlReader::GetValue(void)
0x180035d0f  movups  xmm0, xmmword ptr [rax]
0x180035d12  movdqu  [rsp+170h+var_150], xmm0
0x180035d18  lea     rdx, [rsp+170h+var_150]
0x180035d1d  mov     rcx, rdi; this
0x180035d20  call    ?ParseUInt32@EventManParser@@AEAAIV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; EventManParser::ParseUInt32(std::wstring_view)
0x180035d25  mov     ecx, eax
0x180035d27  mov     rax, [rsi]
0x180035d2a  mov     [rax], ecx
0x180035d2c  mov     r14b, 1
0x180035d2f  jmp     short loc_180035DAF
0x180035d31  lea     rdx, [rbp+70h+var_80]
0x180035d35  mov     rcx, rdi; this
0x180035d38  call    ?GetValue@XmlReader@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; XmlReader::GetValue(void)
0x180035d3d  mov     rcx, [rsi]
0x180035d40  add     rcx, 0C8h
0x180035d47  jmp     loc_180035BC0
0x180035d4c  lea     rdx, [rbp+70h+var_70]
0x180035d50  mov     rcx, rdi; this
0x180035d53  call    ?GetValue@XmlReader@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; XmlReader::GetValue(void)
0x180035d58  mov     rcx, [rsi]
0x180035d5b  add     rcx, 0A8h
0x180035d62  jmp     loc_180035BC0
0x180035d67  lea     rdx, [rbp+70h+var_60]
0x180035d6b  mov     rcx, rdi; this
0x180035d6e  call    ?GetValue@XmlReader@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; XmlReader::GetValue(void)
0x180035d73  mov     rcx, [rsi]
0x180035d76  add     rcx, 0E8h
0x180035d7d  jmp     loc_180035BC0
0x180035d82  lea     rdx, [rbp+70h+var_50]
0x180035d86  mov     rcx, rdi; this
0x180035d89  call    ?GetValue@XmlReader@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; XmlReader::GetValue(void)
0x180035d8e  movups  xmm0, xmmword ptr [rax]
0x180035d91  movdqu  [rsp+170h+var_150], xmm0
0x180035d97  lea     rdx, [rsp+170h+var_150]
0x180035d9c  mov     rcx, rdi; this
0x180035d9f  call    ?ParseBool@EventManParser@@AEAA_NV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; EventManParser::ParseBool(std::wstring_view)
0x180035da4  mov     cl, al
0x180035da6  mov     rax, [rsi]
0x180035da9  mov     [rax+142h], cl
0x180035daf  mov     rcx, rdi; this
0x180035db2  call    ?NextAttribute@XmlReader@@QEAA_NXZ; XmlReader::NextAttribute(void)
0x180035db7  test    al, al
0x180035db9  jnz     loc_180035B10
0x180035dbf  test    r14b, r14b
0x180035dc2  jnz     short loc_180035DD8
0x180035dc4  lea     r8, aValue; "value"
0x180035dcb  mov     edx, 0C007EF3Eh; int
0x180035dd0  mov     rcx, rdi; this
0x180035dd3  call    ?ErrorWithFormatMessage@EventManParser@@AEAAXJZZ; EventManParser::ErrorWithFormatMessage(long,...)
0x180035dd8  mov     rax, rsi
0x180035ddb  mov     rcx, [rbp+70h+var_20]
0x180035ddf  xor     rcx, rsp; StackCookie
0x180035de2  call    __security_check_cookie
0x180035de7  lea     r11, [rsp+170h+var_10]
0x180035def  mov     rbx, [r11+30h]
0x180035df3  mov     rsi, [r11+38h]
0x180035df7  mov     rsp, r11
0x180035dfa  pop     r14
0x180035dfc  pop     rdi
0x180035dfd  pop     rbp
0x180035dfe  retn
```
