# EventManParser::DataDefinitionType(void)

- ea: `0x1800355ac`
- end: `0x180035778`
- name: `?DataDefinitionType@EventManParser@@AEAA?AV?$unique_ptr@VPROPERTY_ENTRY@@U?$default_delete@VPROPERTY_ENTRY@@@std@@@std@@XZ`
- size: `460`
- prototype: `__int64 *__fastcall(XmlReader *this, __int64 *)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x18001d810`
- `0x18003b4dc`

## callees

- `0x18001df64`
- `0x18001e284`
- `0x18001e4d8`
- `0x18001e550`
- `0x18001e8f0`
- `0x18001e930`
- `0x1800313f8`
- `0x1800355ac`
- `0x180037670`
- `0x18003941c`
- `0x180039610`

## pseudocode

```c
__int64 *__fastcall EventManParser::DataDefinitionType(XmlReader *this, __int64 *a2)
{
  bool i; // al
  char AttributeId; // al
  _QWORD *v6; // rax
  __int64 v7; // rcx
  __int64 v8; // rbx
  __int128 *Value; // rax
  __int64 v10; // rcx
  __int64 v11; // r9
  __int64 v12; // r8
  __int64 v13; // rbx
  int v15; // [rsp+20h] [rbp-59h]
  __int128 v16; // [rsp+30h] [rbp-49h] BYREF
  char v17; // [rsp+F0h] [rbp+77h] BYREF

  v17 = 0;
  std::make_unique<PROPERTY_ENTRY,bool,0>(a2, &v17);
  v15 = 1;
  for ( i = XmlReader::FirstAttribute(this); i; i = XmlReader::NextAttribute(this) )
  {
    v16 = *(_OWORD *)XmlReader::GetQualifiedName(this);
    AttributeId = GetAttributeId(&v16);
    switch ( AttributeId )
    {
      case 5:
        v13 = *a2;
        Value = (__int128 *)XmlReader::GetValue(this);
        v11 = v13 + 136;
        v12 = v13 + 128;
        goto LABEL_17;
      case 14:
        v6 = (_QWORD *)XmlReader::GetValue(this);
        v7 = *a2 + 32;
        goto LABEL_12;
      case 18:
        v8 = *a2;
        Value = (__int128 *)XmlReader::GetValue(this);
        v11 = v8 + 176;
        v12 = v8 + 168;
LABEL_17:
        v16 = *Value;
        EventManParser::ParseCountOrLength(v10, &v16, v12, v11, v15);
        continue;
      case 20:
        v6 = (_QWORD *)XmlReader::GetValue(this);
        v7 = *a2 + 96;
        goto LABEL_12;
      case 25:
        v6 = (_QWORD *)XmlReader::GetValue(this);
        v7 = *a2;
        goto LABEL_12;
      case 29:
        v6 = (_QWORD *)XmlReader::GetValue(this);
        v7 = *a2 + 64;
LABEL_12:
        std::wstring::_Assign<wchar_t>(v7, *v6, v6[1]);
        continue;
      case 35:
        v16 = *(_OWORD *)XmlReader::GetValue(this);
        *(_DWORD *)(*a2 + 212) = EventManParser::ParseUInt32(this);
        break;
    }
  }
  if ( !*(_QWORD *)(*a2 + 16) )
    EventManParser::ErrorWithFormatMessage(this, -1073221826, L"name");
  if ( !*(_QWORD *)(*a2 + 48) )
    EventManParser::ErrorWithFormatMessage(this, -1073221826, L"inType");
  return a2;
}

```

## disassembly

```asm
0x1800355ac  mov     [rsp-8+arg_0], rbx
0x1800355b1  mov     [rsp-8+arg_8], rdx
0x1800355b6  push    rbp
0x1800355b7  push    rsi
0x1800355b8  push    rdi
0x1800355b9  lea     rbp, [rsp-47h]
0x1800355be  sub     rsp, 0C0h
0x1800355c5  mov     rdi, rdx
0x1800355c8  mov     rsi, rcx
0x1800355cb  mov     [rbp+57h+var_B0], 0
0x1800355d2  mov     [rbp+57h+arg_10], 0
0x1800355d6  lea     rdx, [rbp+57h+arg_10]
0x1800355da  mov     rcx, rdi
0x1800355dd  call    ??$make_unique@VPROPERTY_ENTRY@@_N$0A@@std@@YA?AV?$unique_ptr@VPROPERTY_ENTRY@@U?$default_delete@VPROPERTY_ENTRY@@@std@@@0@$$QEA_N@Z; std::make_unique<PROPERTY_ENTRY,bool,0>(bool &&)
0x1800355e2  mov     [rbp+57h+var_B0], 1
0x1800355e9  mov     rcx, rsi; this
0x1800355ec  call    ?FirstAttribute@XmlReader@@QEAA_NXZ; XmlReader::FirstAttribute(void)
0x1800355f1  jmp     loc_18003571E
0x1800355f6  lea     rdx, [rbp+57h+var_90]
0x1800355fa  mov     rcx, rsi; this
0x1800355fd  call    ?GetQualifiedName@XmlReader@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; XmlReader::GetQualifiedName(void)
0x180035602  movups  xmm0, xmmword ptr [rax]
0x180035605  movdqu  [rbp+57h+var_A0], xmm0
0x18003560a  lea     rcx, [rbp+57h+var_A0]
0x18003560e  call    GetAttributeId
0x180035613  cmp     al, 5
0x180035615  jz      loc_1800356E8
0x18003561b  cmp     al, 0Eh
0x18003561d  jz      loc_1800356D3
0x180035623  cmp     al, 12h
0x180035625  jz      loc_1800356B4
0x18003562b  cmp     al, 14h
0x18003562d  jz      short loc_18003569F
0x18003562f  cmp     al, 19h
0x180035631  jz      short loc_180035682
0x180035633  cmp     al, 1Dh
0x180035635  jz      short loc_18003566D
0x180035637  cmp     al, 23h ; '#'
0x180035639  jnz     loc_180035716
0x18003563f  lea     rdx, [rbp+57h+var_80]
0x180035643  mov     rcx, rsi; this
0x180035646  call    ?GetValue@XmlReader@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; XmlReader::GetValue(void)
0x18003564b  movups  xmm0, xmmword ptr [rax]
0x18003564e  movdqu  [rbp+57h+var_A0], xmm0
0x180035653  lea     rdx, [rbp+57h+var_A0]
0x180035657  mov     rcx, rsi; this
0x18003565a  call    ?ParseUInt32@EventManParser@@AEAAIV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; EventManParser::ParseUInt32(std::wstring_view)
0x18003565f  mov     rcx, [rdi]
0x180035662  mov     [rcx+0D4h], eax
0x180035668  jmp     loc_180035716
0x18003566d  lea     rdx, [rbp+57h+var_70]
0x180035671  mov     rcx, rsi; this
0x180035674  call    ?GetValue@XmlReader@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; XmlReader::GetValue(void)
0x180035679  mov     rcx, [rdi]
0x18003567c  add     rcx, 40h ; '@'
0x180035680  jmp     short loc_180035691
0x180035682  lea     rdx, [rbp+57h+var_60]
0x180035686  mov     rcx, rsi; this
0x180035689  call    ?GetValue@XmlReader@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; XmlReader::GetValue(void)
0x18003568e  mov     rcx, [rdi]
0x180035691  mov     r8, [rax+8]
0x180035695  mov     rdx, [rax]
0x180035698  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x18003569d  jmp     short loc_180035716
0x18003569f  lea     rdx, [rbp+57h+var_50]
0x1800356a3  mov     rcx, rsi; this
0x1800356a6  call    ?GetValue@XmlReader@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; XmlReader::GetValue(void)
0x1800356ab  mov     rcx, [rdi]
0x1800356ae  add     rcx, 60h ; '`'
0x1800356b2  jmp     short loc_180035691
0x1800356b4  mov     rbx, [rdi]
0x1800356b7  lea     rdx, [rbp+57h+var_40]
0x1800356bb  mov     rcx, rsi; this
0x1800356be  call    ?GetValue@XmlReader@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; XmlReader::GetValue(void)
0x1800356c3  lea     r9, [rbx+0B0h]
0x1800356ca  lea     r8, [rbx+0A8h]
0x1800356d1  jmp     short loc_180035705
0x1800356d3  lea     rdx, [rbp+57h+var_30]
0x1800356d7  mov     rcx, rsi; this
0x1800356da  call    ?GetValue@XmlReader@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; XmlReader::GetValue(void)
0x1800356df  mov     rcx, [rdi]
0x1800356e2  add     rcx, 20h ; ' '
0x1800356e6  jmp     short loc_180035691
0x1800356e8  mov     rbx, [rdi]
0x1800356eb  lea     rdx, [rbp+57h+var_20]
0x1800356ef  mov     rcx, rsi; this
0x1800356f2  call    ?GetValue@XmlReader@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; XmlReader::GetValue(void)
0x1800356f7  lea     r9, [rbx+88h]
0x1800356fe  lea     r8, [rbx+80h]
0x180035705  movups  xmm0, xmmword ptr [rax]
0x180035708  movdqu  [rbp+57h+var_A0], xmm0
0x18003570d  lea     rdx, [rbp+57h+var_A0]
0x180035711  call    ?ParseCountOrLength@EventManParser@@AEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@PEAGPEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@3@@Z; EventManParser::ParseCountOrLength(std::wstring_view,ushort *,std::wstring *)
0x180035716  mov     rcx, rsi; this
0x180035719  call    ?NextAttribute@XmlReader@@QEAA_NXZ; XmlReader::NextAttribute(void)
0x18003571e  test    al, al
0x180035720  jnz     loc_1800355F6
0x180035726  mov     rax, [rdi]
0x180035729  mov     ebx, 0C007EF3Eh
0x18003572e  cmp     qword ptr [rax+10h], 0
0x180035733  jnz     short loc_180035746
0x180035735  lea     r8, aName_0; "name"
0x18003573c  mov     edx, ebx; int
0x18003573e  mov     rcx, rsi; this
0x180035741  call    ?ErrorWithFormatMessage@EventManParser@@AEAAXJZZ; EventManParser::ErrorWithFormatMessage(long,...)
0x180035746  mov     rax, [rdi]
0x180035749  cmp     qword ptr [rax+30h], 0
0x18003574e  jnz     short loc_180035761
0x180035750  lea     r8, aIntype; "inType"
0x180035757  mov     edx, ebx; int
0x180035759  mov     rcx, rsi; this
0x18003575c  call    ?ErrorWithFormatMessage@EventManParser@@AEAAXJZZ; EventManParser::ErrorWithFormatMessage(long,...)
0x180035761  mov     rax, rdi
0x180035764  mov     rbx, [rsp+0D0h+arg_0]
0x18003576c  add     rsp, 0C0h
0x180035773  pop     rdi
0x180035774  pop     rsi
0x180035775  pop     rbp
0x180035776  retn
```
