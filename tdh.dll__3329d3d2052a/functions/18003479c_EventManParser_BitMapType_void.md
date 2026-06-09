# EventManParser::BitMapType(void)

- ea: `0x18003479c`
- end: `0x18003496e`
- name: `?BitMapType@EventManParser@@AEAA?AV?$unique_ptr@VMAPLIST_ENTRY@@U?$default_delete@VMAPLIST_ENTRY@@@std@@@std@@XZ`
- size: `466`
- prototype: `__int64 *__fastcall(XmlReader *this, __int64 *)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config`

## callers

- `0x180038a44`

## callees

- `0x18001cb90`
- `0x18001df64`
- `0x18001e284`
- `0x18001e4d8`
- `0x18001e550`
- `0x18001e8f0`
- `0x18001e930`
- `0x18001eb04`
- `0x18001ed1c`
- `0x18002e528`
- `0x180032c1c`
- `0x18003479c`
- `0x180034974`
- `0x180035858`
- `0x180037e80`
- `0x180038cc4`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 *__fastcall EventManParser::BitMapType(XmlReader *this, __int64 *a2)
{
  bool i; // al
  _QWORD *Value; // rax
  __int64 v6; // rcx
  bool j; // al
  __int64 v8; // rsi
  __int64 *v9; // rax
  _QWORD *v10; // rdx
  __int64 v11; // rcx
  int v13; // [rsp+A0h] [rbp+30h] BYREF

  v13 = 2;
  std::make_unique<MAPLIST_ENTRY,enum _MAP_FLAGS,0>(a2, &v13);
  for ( i = XmlReader::FirstAttribute(this); i; i = XmlReader::NextAttribute(this) )
  {
    XmlReader::GetQualifiedName(this);
    if ( (unsigned __int8)std::_Traits_equal<std::char_traits<wchar_t>>(L"name", 4) )
    {
      Value = (_QWORD *)XmlReader::GetValue(this);
      v6 = *a2 + 32;
    }
    else
    {
      if ( !(unsigned __int8)std::_Traits_equal<std::char_traits<wchar_t>>(L"symbol", 6) )
        continue;
      Value = (_QWORD *)XmlReader::GetValue(this);
      v6 = *a2;
    }
    std::wstring::_Assign<wchar_t>(v6, *Value, Value[1]);
  }
  if ( !*(_QWORD *)(*a2 + 48) )
    EventManParser::ErrorWithFormatMessage(this, -1073221826, L"name");
  for ( j = XmlReader::FirstChildElement(this); j; j = XmlReader::NextChildElement(this) )
  {
    XmlReader::GetLocalName(this);
    if ( (unsigned __int8)EventManParser::ElementMatches(this) )
    {
      v8 = *a2;
      v9 = (__int64 *)EventManParser::BitMapValueType(this);
      v10 = *(_QWORD **)(v8 + 112);
      if ( v10 == *(_QWORD **)(v8 + 120) )
      {
        std::vector<std::unique_ptr<FILTER_ENTRY>>::_Emplace_reallocate<std::unique_ptr<FILTER_ENTRY>>(
          v8 + 104,
          v10,
          v9);
      }
      else
      {
        v11 = *v9;
        *v9 = 0;
        *v10 = v11;
        *(_QWORD *)(v8 + 112) += 8LL;
      }
      std::unique_ptr<FILTER_ENTRY>::~unique_ptr<FILTER_ENTRY>(&v13);
    }
  }
  if ( *(_QWORD *)(*a2 + 104) == *(_QWORD *)(*a2 + 112) )
    EventManParser::ErrorWithFormatMessage(this, -1073221829, L"map");
  return a2;
}

```

## disassembly

```asm
0x18003479c  mov     [rsp-18h+arg_0], rbx
0x1800347a1  mov     [rsp-18h+arg_18], rsi
0x1800347a6  mov     [rsp-18h+arg_8], rdx
0x1800347ab  push    rbp
0x1800347ac  push    rdi
0x1800347ad  push    r15
0x1800347af  mov     rbp, rsp
0x1800347b2  sub     rsp, 70h
0x1800347b6  mov     rdi, rdx
0x1800347b9  mov     rbx, rcx
0x1800347bc  mov     [rbp+var_50], 0
0x1800347c3  mov     [rbp+arg_10], 2
0x1800347ca  lea     rdx, [rbp+arg_10]
0x1800347ce  mov     rcx, rdi
0x1800347d1  call    ??$make_unique@VMAPLIST_ENTRY@@W4_MAP_FLAGS@@$0A@@std@@YA?AV?$unique_ptr@VMAPLIST_ENTRY@@U?$default_delete@VMAPLIST_ENTRY@@@std@@@0@$$QEAW4_MAP_FLAGS@@@Z; std::make_unique<MAPLIST_ENTRY,_MAP_FLAGS,0>(_MAP_FLAGS &&)
0x1800347d6  mov     [rbp+var_50], 1
0x1800347dd  mov     rcx, rbx; this
0x1800347e0  call    ?FirstAttribute@XmlReader@@QEAA_NXZ; XmlReader::FirstAttribute(void)
0x1800347e5  jmp     short loc_180034865
0x1800347e7  lea     rdx, [rbp+var_40]
0x1800347eb  mov     rcx, rbx; this
0x1800347ee  call    ?GetQualifiedName@XmlReader@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; XmlReader::GetQualifiedName(void)
0x1800347f3  mov     r9, [rbp+var_38]
0x1800347f7  mov     r8, [rbp+var_40]
0x1800347fb  mov     edx, 4
0x180034800  lea     rcx, aName_0; "name"
0x180034807  call    ??$_Traits_equal@U?$char_traits@_W@std@@@std@@YA_NQEB_W_K01@Z; std::_Traits_equal<std::char_traits<wchar_t>>(wchar_t const * const,unsigned __int64,wchar_t const * const,unsigned __int64)
0x18003480c  test    al, al
0x18003480e  jz      short loc_180034825
0x180034810  lea     rdx, [rbp+var_10]
0x180034814  mov     rcx, rbx; this
0x180034817  call    ?GetValue@XmlReader@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; XmlReader::GetValue(void)
0x18003481c  mov     rcx, [rdi]
0x18003481f  add     rcx, 20h ; ' '
0x180034823  jmp     short loc_180034851
0x180034825  mov     r9, [rbp+var_38]
0x180034829  mov     r8, [rbp+var_40]
0x18003482d  mov     edx, 6
0x180034832  lea     rcx, aSymbol; "symbol"
0x180034839  call    ??$_Traits_equal@U?$char_traits@_W@std@@@std@@YA_NQEB_W_K01@Z; std::_Traits_equal<std::char_traits<wchar_t>>(wchar_t const * const,unsigned __int64,wchar_t const * const,unsigned __int64)
0x18003483e  test    al, al
0x180034840  jz      short loc_18003485D
0x180034842  lea     rdx, [rbp+var_20]
0x180034846  mov     rcx, rbx; this
0x180034849  call    ?GetValue@XmlReader@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; XmlReader::GetValue(void)
0x18003484e  mov     rcx, [rdi]
0x180034851  mov     r8, [rax+8]
0x180034855  mov     rdx, [rax]
0x180034858  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x18003485d  mov     rcx, rbx; this
0x180034860  call    ?NextAttribute@XmlReader@@QEAA_NXZ; XmlReader::NextAttribute(void)
0x180034865  test    al, al
0x180034867  jnz     loc_1800347E7
0x18003486d  mov     rax, [rdi]
0x180034870  cmp     qword ptr [rax+30h], 0
0x180034875  jnz     short loc_18003488B
0x180034877  lea     r8, aName_0; "name"
0x18003487e  mov     edx, 0C007EF3Eh; int
0x180034883  mov     rcx, rbx; this
0x180034886  call    ?ErrorWithFormatMessage@EventManParser@@AEAAXJZZ; EventManParser::ErrorWithFormatMessage(long,...)
0x18003488b  mov     rcx, rbx; this
0x18003488e  call    ?FirstChildElement@XmlReader@@QEAA_NXZ; XmlReader::FirstChildElement(void)
0x180034893  lea     r15, aMap; "map"
0x18003489a  jmp     loc_180034930
0x18003489f  lea     rdx, [rbp+var_30]
0x1800348a3  mov     rcx, rbx; this
0x1800348a6  call    ?GetLocalName@XmlReader@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; XmlReader::GetLocalName(void)
0x1800348ab  movups  xmm0, [rbp+var_30]
0x1800348af  movups  xmm1, xmmword ptr cs:off_18004F7F0; "http://schemas.microsoft.com/win/2004/0"...
0x1800348b6  movdqu  [rbp+var_20], xmm0
0x1800348bb  movdqu  [rbp+var_10], xmm1
0x1800348c0  mov     [rbp+var_40], r15
0x1800348c4  mov     [rbp+var_38], 3
0x1800348cc  lea     r9, [rbp+var_20]
0x1800348d0  lea     r8, [rbp+var_10]
0x1800348d4  lea     rdx, [rbp+var_40]
0x1800348d8  mov     rcx, rbx; this
0x1800348db  call    ?ElementMatches@EventManParser@@AEBA_NV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@00@Z; EventManParser::ElementMatches(std::wstring_view,std::wstring_view,std::wstring_view)
0x1800348e0  test    al, al
0x1800348e2  jz      short loc_180034928
0x1800348e4  mov     rsi, [rdi]
0x1800348e7  lea     rdx, [rbp+arg_10]
0x1800348eb  mov     rcx, rbx; this
0x1800348ee  call    ?BitMapValueType@EventManParser@@AEAA?AV?$unique_ptr@VMAP_ENTRY@@U?$default_delete@VMAP_ENTRY@@@std@@@std@@XZ; EventManParser::BitMapValueType(void)
0x1800348f3  nop
0x1800348f4  mov     rdx, [rsi+70h]
0x1800348f8  cmp     rdx, [rsi+78h]
0x1800348fc  jz      short loc_180034912
0x1800348fe  mov     rcx, [rax]
0x180034901  mov     qword ptr [rax], 0
0x180034908  mov     [rdx], rcx
0x18003490b  add     qword ptr [rsi+70h], 8
0x180034910  jmp     short loc_18003491F
0x180034912  mov     r8, rax
0x180034915  lea     rcx, [rsi+68h]
0x180034919  call    ??$_Emplace_reallocate@V?$unique_ptr@VFILTER_ENTRY@@U?$default_delete@VFILTER_ENTRY@@@std@@@std@@@?$vector@V?$unique_ptr@VFILTER_ENTRY@@U?$default_delete@VFILTER_ENTRY@@@std@@@std@@V?$allocator@V?$unique_ptr@VFILTER_ENTRY@@U?$default_delete@VFILTER_ENTRY@@@std@@@std@@@2@@std@@AEAAPEAV?$unique_ptr@VFILTER_ENTRY@@U?$default_delete@VFILTER_ENTRY@@@std@@@1@QEAV21@$$QEAV21@@Z; std::vector<std::unique_ptr<FILTER_ENTRY>>::_Emplace_reallocate<std::unique_ptr<FILTER_ENTRY>>(std::unique_ptr<FILTER_ENTRY> * const,std::unique_ptr<FILTER_ENTRY> &&)
0x18003491e  nop
0x18003491f  lea     rcx, [rbp+arg_10]
0x180034923  call    ??1?$unique_ptr@VFILTER_ENTRY@@U?$default_delete@VFILTER_ENTRY@@@std@@@std@@QEAA@XZ; std::unique_ptr<FILTER_ENTRY>::~unique_ptr<FILTER_ENTRY>(void)
0x180034928  mov     rcx, rbx; this
0x18003492b  call    ?NextChildElement@XmlReader@@QEAA_NXZ; XmlReader::NextChildElement(void)
0x180034930  test    al, al
0x180034932  jnz     loc_18003489F
0x180034938  mov     rcx, [rdi]
0x18003493b  mov     rax, [rcx+70h]
0x18003493f  cmp     [rcx+68h], rax
0x180034943  jnz     short loc_180034955
0x180034945  mov     r8, r15
0x180034948  mov     edx, 0C007EF3Bh; int
0x18003494d  mov     rcx, rbx; this
0x180034950  call    ?ErrorWithFormatMessage@EventManParser@@AEAAXJZZ; EventManParser::ErrorWithFormatMessage(long,...)
0x180034955  mov     rax, rdi
0x180034958  lea     r11, [rsp+70h+var_s0]
0x18003495d  mov     rbx, [r11+20h]
0x180034961  mov     rsi, [r11+38h]
0x180034965  mov     rsp, r11
0x180034968  pop     r15
0x18003496a  pop     rdi
0x18003496b  pop     rbp
0x18003496c  retn
```
