# EventManParser::PatternMapType(void)

- ea: `0x180039878`
- end: `0x180039a78`
- name: `?PatternMapType@EventManParser@@AEAA?AV?$unique_ptr@VMAPLIST_ENTRY@@U?$default_delete@VMAPLIST_ENTRY@@@std@@@std@@XZ`
- size: `512`
- prototype: `__int64 *__fastcall(XmlReader *this, __int64 *)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config`

## callers

- `0x180039780`

## callees

- `0x18001cb90`
- `0x18001df64`
- `0x18001e284`
- `0x18001e4d8`
- `0x18001e550`
- `0x18001e8f0`
- `0x18001e930`
- `0x18001eb04`
- `0x18002e528`
- `0x180032c1c`
- `0x180035858`
- `0x180037670`
- `0x180037e80`
- `0x180038cc4`
- `0x180039878`
- `0x180039a80`

## pseudocode

```c
__int64 *__fastcall EventManParser::PatternMapType(XmlReader *this, __int64 *a2)
{
  char v4; // si
  bool i; // al
  char AttributeId; // al
  _QWORD *v7; // rax
  __int64 v8; // rcx
  _QWORD *Value; // rax
  bool j; // al
  __int64 v11; // rsi
  __int64 *v12; // rax
  _QWORD *v13; // rdx
  __int64 v14; // rcx
  _OWORD v16[4]; // [rsp+30h] [rbp-50h] BYREF
  int v17; // [rsp+B0h] [rbp+30h] BYREF

  v17 = 4;
  std::make_unique<MAPLIST_ENTRY,enum _MAP_FLAGS,0>(a2, &v17);
  v4 = 0;
  for ( i = XmlReader::FirstAttribute(this); i; i = XmlReader::NextAttribute(this) )
  {
    v16[0] = *(_OWORD *)XmlReader::GetQualifiedName(this);
    AttributeId = GetAttributeId(v16);
    if ( AttributeId == 10 )
    {
      Value = (_QWORD *)XmlReader::GetValue(this);
      std::wstring::_Assign<wchar_t>(*a2 + 64, *Value);
      v4 = 1;
    }
    else
    {
      if ( AttributeId == 25 )
      {
        v7 = (_QWORD *)XmlReader::GetValue(this);
        v8 = *a2 + 32;
      }
      else
      {
        if ( AttributeId != 34 )
          continue;
        v7 = (_QWORD *)XmlReader::GetValue(this);
        v8 = *a2;
      }
      std::wstring::_Assign<wchar_t>(v8, *v7);
    }
  }
  if ( !*(_QWORD *)(*a2 + 48) )
    EventManParser::ErrorWithFormatMessage(this, -1073221826, L"name");
  if ( !v4 )
    EventManParser::ErrorWithFormatMessage(this, -1073221826, L"format");
  for ( j = XmlReader::FirstChildElement(this); j; j = XmlReader::NextChildElement(this) )
  {
    XmlReader::GetLocalName(this);
    v16[2] = v16[1];
    v16[3] = *(_OWORD *)&off_18004F7F0;
    *(_QWORD *)&v16[0] = L"map";
    *((_QWORD *)&v16[0] + 1) = 3;
    if ( (unsigned __int8)EventManParser::ElementMatches(this) )
    {
      v11 = *a2;
      v12 = (__int64 *)EventManParser::PatternMapValueType(this);
      v13 = *(_QWORD **)(v11 + 112);
      if ( v13 == *(_QWORD **)(v11 + 120) )
      {
        std::vector<std::unique_ptr<FILTER_ENTRY>>::_Emplace_reallocate<std::unique_ptr<FILTER_ENTRY>>(
          v11 + 104,
          v13,
          v12);
      }
      else
      {
        v14 = *v12;
        *v12 = 0;
        *v13 = v14;
        *(_QWORD *)(v11 + 112) += 8LL;
      }
      std::unique_ptr<FILTER_ENTRY>::~unique_ptr<FILTER_ENTRY>(&v17);
    }
  }
  if ( *(_QWORD *)(*a2 + 104) == *(_QWORD *)(*a2 + 112) )
    EventManParser::ErrorWithFormatMessage(this, -1073221829, L"map");
  return a2;
}

```

## disassembly

```asm
0x180039878  mov     [rsp-18h+arg_0], rbx
0x18003987d  mov     [rsp-18h+arg_18], rsi
0x180039882  mov     [rsp-18h+arg_8], rdx
0x180039887  push    rbp
0x180039888  push    rdi
0x180039889  push    r15
0x18003988b  mov     rbp, rsp
0x18003988e  sub     rsp, 80h
0x180039895  mov     rdi, rdx
0x180039898  mov     rbx, rcx
0x18003989b  mov     [rbp+var_60], 0
0x1800398a2  mov     [rbp+arg_10], 4
0x1800398a9  lea     rdx, [rbp+arg_10]
0x1800398ad  mov     rcx, rdi
0x1800398b0  call    ??$make_unique@VMAPLIST_ENTRY@@W4_MAP_FLAGS@@$0A@@std@@YA?AV?$unique_ptr@VMAPLIST_ENTRY@@U?$default_delete@VMAPLIST_ENTRY@@@std@@@0@$$QEAW4_MAP_FLAGS@@@Z; std::make_unique<MAPLIST_ENTRY,_MAP_FLAGS,0>(_MAP_FLAGS &&)
0x1800398b5  mov     [rbp+var_60], 1
0x1800398bc  xor     sil, sil
0x1800398bf  mov     rcx, rbx; this
0x1800398c2  call    ?FirstAttribute@XmlReader@@QEAA_NXZ; XmlReader::FirstAttribute(void)
0x1800398c7  jmp     loc_180039951
0x1800398cc  lea     rdx, [rbp+var_20]
0x1800398d0  mov     rcx, rbx; this
0x1800398d3  call    ?GetQualifiedName@XmlReader@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; XmlReader::GetQualifiedName(void)
0x1800398d8  movups  xmm0, xmmword ptr [rax]
0x1800398db  movdqu  [rbp+var_50], xmm0
0x1800398e0  lea     rcx, [rbp+var_50]
0x1800398e4  call    GetAttributeId
0x1800398e9  cmp     al, 0Ah
0x1800398eb  jz      short loc_180039927
0x1800398ed  cmp     al, 19h
0x1800398ef  jz      short loc_180039906
0x1800398f1  cmp     al, 22h ; '"'
0x1800398f3  jnz     short loc_180039949
0x1800398f5  lea     rdx, [rbp+var_30]
0x1800398f9  mov     rcx, rbx; this
0x1800398fc  call    ?GetValue@XmlReader@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; XmlReader::GetValue(void)
0x180039901  mov     rcx, [rdi]
0x180039904  jmp     short loc_180039919
0x180039906  lea     rdx, [rbp+var_40]
0x18003990a  mov     rcx, rbx; this
0x18003990d  call    ?GetValue@XmlReader@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; XmlReader::GetValue(void)
0x180039912  mov     rcx, [rdi]
0x180039915  add     rcx, 20h ; ' '
0x180039919  mov     rdx, [rax]
0x18003991c  mov     r8, [rax+8]
0x180039920  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x180039925  jmp     short loc_180039949
0x180039927  lea     rdx, [rbp+var_10]
0x18003992b  mov     rcx, rbx; this
0x18003992e  call    ?GetValue@XmlReader@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; XmlReader::GetValue(void)
0x180039933  mov     rcx, [rdi]
0x180039936  add     rcx, 40h ; '@'
0x18003993a  mov     r8, [rax+8]
0x18003993e  mov     rdx, [rax]
0x180039941  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x180039946  mov     sil, 1
0x180039949  mov     rcx, rbx; this
0x18003994c  call    ?NextAttribute@XmlReader@@QEAA_NXZ; XmlReader::NextAttribute(void)
0x180039951  test    al, al
0x180039953  jnz     loc_1800398CC
0x180039959  mov     rax, [rdi]
0x18003995c  mov     r15d, 0C007EF3Eh
0x180039962  cmp     qword ptr [rax+30h], 0
0x180039967  jnz     short loc_18003997B
0x180039969  lea     r8, aName_0; "name"
0x180039970  mov     edx, r15d; int
0x180039973  mov     rcx, rbx; this
0x180039976  call    ?ErrorWithFormatMessage@EventManParser@@AEAAXJZZ; EventManParser::ErrorWithFormatMessage(long,...)
0x18003997b  test    sil, sil
0x18003997e  jnz     short loc_180039992
0x180039980  lea     r8, aFormat; "format"
0x180039987  mov     edx, r15d; int
0x18003998a  mov     rcx, rbx; this
0x18003998d  call    ?ErrorWithFormatMessage@EventManParser@@AEAAXJZZ; EventManParser::ErrorWithFormatMessage(long,...)
0x180039992  mov     rcx, rbx; this
0x180039995  call    ?FirstChildElement@XmlReader@@QEAA_NXZ; XmlReader::FirstChildElement(void)
0x18003999a  lea     r15, aMap; "map"
0x1800399a1  jmp     loc_180039A37
0x1800399a6  lea     rdx, [rbp+var_40]
0x1800399aa  mov     rcx, rbx; this
0x1800399ad  call    ?GetLocalName@XmlReader@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; XmlReader::GetLocalName(void)
0x1800399b2  movups  xmm0, [rbp+var_40]
0x1800399b6  movups  xmm1, xmmword ptr cs:off_18004F7F0; "http://schemas.microsoft.com/win/2004/0"...
0x1800399bd  movdqu  [rbp+var_30], xmm0
0x1800399c2  movdqu  [rbp+var_20], xmm1
0x1800399c7  mov     qword ptr [rbp+var_50], r15
0x1800399cb  mov     qword ptr [rbp+var_50+8], 3
0x1800399d3  lea     r9, [rbp+var_30]
0x1800399d7  lea     r8, [rbp+var_20]
0x1800399db  lea     rdx, [rbp+var_50]
0x1800399df  mov     rcx, rbx; this
0x1800399e2  call    ?ElementMatches@EventManParser@@AEBA_NV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@00@Z; EventManParser::ElementMatches(std::wstring_view,std::wstring_view,std::wstring_view)
0x1800399e7  test    al, al
0x1800399e9  jz      short loc_180039A2F
0x1800399eb  mov     rsi, [rdi]
0x1800399ee  lea     rdx, [rbp+arg_10]
0x1800399f2  mov     rcx, rbx; this
0x1800399f5  call    ?PatternMapValueType@EventManParser@@AEAA?AV?$unique_ptr@VMAP_ENTRY@@U?$default_delete@VMAP_ENTRY@@@std@@@std@@XZ; EventManParser::PatternMapValueType(void)
0x1800399fa  nop
0x1800399fb  mov     rdx, [rsi+70h]
0x1800399ff  cmp     rdx, [rsi+78h]
0x180039a03  jz      short loc_180039A19
0x180039a05  mov     rcx, [rax]
0x180039a08  mov     qword ptr [rax], 0
0x180039a0f  mov     [rdx], rcx
0x180039a12  add     qword ptr [rsi+70h], 8
0x180039a17  jmp     short loc_180039A26
0x180039a19  mov     r8, rax
0x180039a1c  lea     rcx, [rsi+68h]
0x180039a20  call    ??$_Emplace_reallocate@V?$unique_ptr@VFILTER_ENTRY@@U?$default_delete@VFILTER_ENTRY@@@std@@@std@@@?$vector@V?$unique_ptr@VFILTER_ENTRY@@U?$default_delete@VFILTER_ENTRY@@@std@@@std@@V?$allocator@V?$unique_ptr@VFILTER_ENTRY@@U?$default_delete@VFILTER_ENTRY@@@std@@@std@@@2@@std@@AEAAPEAV?$unique_ptr@VFILTER_ENTRY@@U?$default_delete@VFILTER_ENTRY@@@std@@@1@QEAV21@$$QEAV21@@Z; std::vector<std::unique_ptr<FILTER_ENTRY>>::_Emplace_reallocate<std::unique_ptr<FILTER_ENTRY>>(std::unique_ptr<FILTER_ENTRY> * const,std::unique_ptr<FILTER_ENTRY> &&)
0x180039a25  nop
0x180039a26  lea     rcx, [rbp+arg_10]
0x180039a2a  call    ??1?$unique_ptr@VFILTER_ENTRY@@U?$default_delete@VFILTER_ENTRY@@@std@@@std@@QEAA@XZ; std::unique_ptr<FILTER_ENTRY>::~unique_ptr<FILTER_ENTRY>(void)
0x180039a2f  mov     rcx, rbx; this
0x180039a32  call    ?NextChildElement@XmlReader@@QEAA_NXZ; XmlReader::NextChildElement(void)
0x180039a37  test    al, al
0x180039a39  jnz     loc_1800399A6
0x180039a3f  mov     rcx, [rdi]
0x180039a42  mov     rax, [rcx+70h]
0x180039a46  cmp     [rcx+68h], rax
0x180039a4a  jnz     short loc_180039A5C
0x180039a4c  mov     r8, r15
0x180039a4f  mov     edx, 0C007EF3Bh; int
0x180039a54  mov     rcx, rbx; this
0x180039a57  call    ?ErrorWithFormatMessage@EventManParser@@AEAAXJZZ; EventManParser::ErrorWithFormatMessage(long,...)
0x180039a5c  mov     rax, rdi
0x180039a5f  lea     r11, [rsp+80h+var_s0]
0x180039a67  mov     rbx, [r11+20h]
0x180039a6b  mov     rsi, [r11+38h]
0x180039a6f  mov     rsp, r11
0x180039a72  pop     r15
0x180039a74  pop     rdi
0x180039a75  pop     rbp
0x180039a76  retn
```
