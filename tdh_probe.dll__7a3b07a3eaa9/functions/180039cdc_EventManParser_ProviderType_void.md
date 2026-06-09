# EventManParser::ProviderType(void)

- ea: `0x180039cdc`
- end: `0x18003a44c`
- name: `?ProviderType@EventManParser@@AEAA?AV?$unique_ptr@VETW_PROVIDER_ENTRY@@U?$default_delete@VETW_PROVIDER_ENTRY@@@std@@@std@@XZ`
- size: `1904`
- prototype: `__int64 __fastcall(XmlReader *this)`
- caller_count: `1`
- callee_count: `32`
- tags: `registry_config, service_task`

## callers

- `0x1800360b4`

## callees

- `0x18001cb90`
- `0x18001df64`
- `0x18001e0cc`
- `0x18001e284`
- `0x18001e4d8`
- `0x18001e550`
- `0x18001e8f0`
- `0x18001e930`
- `0x18001ed1c`
- `0x1800207c0`
- `0x1800311e4`
- `0x180033da0`
- `0x180034cbc`
- `0x180035780`
- `0x180035858`
- `0x1800358f4`
- `0x180036d30`
- `0x180037670`
- `0x180037e80`
- `0x180038228`
- `0x180038498`
- `0x180038a44`
- `0x180038c30`
- `0x180038cc4`
- `0x180038d38`
- `0x180039328`
- `0x180039494`
- `0x180039cdc`
- `0x18003b6f8`
- `0x18003bae4`
- `0x18003bec4`
- `0x18003c754`

## string_xrefs

- `0x180039fb9`: `Invalid value "%ls", expected Xml or Wbem.`
- `0x18003a14c`: `tasks`
- `0x18003a2eb`: `templates`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
struct ETW_PROVIDER_ENTRY **__fastcall EventManParser::ProviderType(XmlReader *this, struct ETW_PROVIDER_ENTRY **a2)
{
  char v4; // r15
  char v5; // r14
  bool i; // al
  unsigned __int8 AttributeId; // al
  _QWORD *Value; // rax
  __int64 v9; // rcx
  __int64 v10; // rax
  struct ETW_PROVIDER_ENTRY *v11; // rdx
  unsigned __int64 v12; // rcx
  _QWORD *v13; // rax
  const wchar_t *v14; // rsi
  int v16; // [rsp+20h] [rbp-E0h]
  __int128 v17; // [rsp+40h] [rbp-C0h] BYREF
  int v18; // [rsp+50h] [rbp-B0h]
  const wchar_t *v19; // [rsp+60h] [rbp-A0h]
  __int64 v20; // [rsp+68h] [rbp-98h]
  const wchar_t *v21; // [rsp+70h] [rbp-90h]
  __int64 v22; // [rsp+78h] [rbp-88h]
  const wchar_t *v23; // [rsp+80h] [rbp-80h]
  __int64 v24; // [rsp+88h] [rbp-78h]
  const wchar_t *v25; // [rsp+90h] [rbp-70h]
  __int64 v26; // [rsp+98h] [rbp-68h]
  const wchar_t *v27; // [rsp+A0h] [rbp-60h]
  __int64 v28; // [rsp+A8h] [rbp-58h]
  const wchar_t *v29; // [rsp+B0h] [rbp-50h]
  __int64 v30; // [rsp+B8h] [rbp-48h]
  const wchar_t *v31; // [rsp+C0h] [rbp-40h]
  __int64 v32; // [rsp+C8h] [rbp-38h]
  const wchar_t *v33; // [rsp+D0h] [rbp-30h]
  __int64 v34; // [rsp+D8h] [rbp-28h]
  struct ETW_PROVIDER_ENTRY **v35; // [rsp+F0h] [rbp-10h]
  const wchar_t *v36; // [rsp+110h] [rbp+10h]
  __int64 v37; // [rsp+118h] [rbp+18h]
  const wchar_t *v38; // [rsp+120h] [rbp+20h]
  __int64 v39; // [rsp+128h] [rbp+28h]
  _BYTE v40[32]; // [rsp+130h] [rbp+30h] BYREF

  v35 = a2;
  std::make_unique<ETW_PROVIDER_ENTRY,,0>(a2);
  v18 = 1;
  v4 = 0;
  v5 = 0;
  for ( i = XmlReader::FirstAttribute(this); i; i = XmlReader::NextAttribute(this) )
  {
    v17 = *(_OWORD *)XmlReader::GetQualifiedName(this);
    AttributeId = GetAttributeId(&v17);
    if ( AttributeId > 0x1Au )
    {
      switch ( AttributeId )
      {
        case 0x1Eu:
          Value = (_QWORD *)XmlReader::GetValue(this);
          v9 = (__int64)*a2 + 176;
          goto LABEL_31;
        case 0x1Fu:
          Value = (_QWORD *)XmlReader::GetValue(this);
          v9 = (__int64)*a2 + 112;
          goto LABEL_31;
        case 0x20u:
          XmlReader::GetValue(this);
          v14 = v19;
          if ( (unsigned __int8)std::_Traits_equal<std::char_traits<wchar_t>>(L"Xml", 3, v19, v20, v16) )
          {
            *((_DWORD *)*a2 + 68) = 0;
          }
          else if ( (unsigned __int8)std::_Traits_equal<std::char_traits<wchar_t>>(L"Wbem", 4, v14, v20, v16) )
          {
            *((_DWORD *)*a2 + 68) = 1;
          }
          else
          {
            EventManParser::ErrorWithPrintf(this, -2147024809, "Invalid value \"%ls\", expected Xml or Wbem.", v14);
          }
          break;
        case 0x22u:
          v13 = (_QWORD *)XmlReader::GetValue(this);
          std::wstring::_Assign<wchar_t>((char *)*a2 + 80, *v13);
          v5 = 1;
          break;
        case 0x2Au:
          v17 = *(_OWORD *)XmlReader::GetValue(this);
          *((_BYTE *)*a2 + 279) = EventManParser::ParseBool(this);
          break;
      }
    }
    else
    {
      if ( AttributeId == 26 )
      {
        Value = (_QWORD *)XmlReader::GetValue(this);
        v9 = (__int64)*a2 + 208;
LABEL_31:
        std::wstring::_Assign<wchar_t>(v9, *Value);
        continue;
      }
      if ( AttributeId != 4 )
      {
        switch ( AttributeId )
        {
          case 0xCu:
            v17 = *(_OWORD *)XmlReader::GetValue(this);
            *(_OWORD *)*a2 = *(_OWORD *)EventManParser::ParseGuid(this);
            v4 = 1;
            continue;
          case 0x16u:
            v17 = *(_OWORD *)XmlReader::GetValue(this);
            v10 = EventManParser::ParseStrTableRef(this, v40, &v17);
            std::wstring::operator=((char *)*a2 + 48, v10);
            std::wstring::_Tidy_deallocate(v40);
            continue;
          case 0x17u:
            Value = (_QWORD *)XmlReader::GetValue(this);
            v9 = (__int64)*a2 + 144;
            break;
          case 0x19u:
            Value = (_QWORD *)XmlReader::GetValue(this);
            v9 = (__int64)*a2 + 16;
            break;
          default:
            continue;
        }
        goto LABEL_31;
      }
      v17 = *(_OWORD *)XmlReader::GetValue(this);
      *((_OWORD *)*a2 + 15) = *(_OWORD *)EventManParser::ParseGuid(this);
      v11 = *a2;
      v12 = *((_QWORD *)*a2 + 30);
      if ( !v12 )
        v12 = *((_QWORD *)v11 + 31) - _mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
      *((_BYTE *)v11 + 281) |= v12 != 0;
    }
  }
  if ( !*((_QWORD *)*a2 + 4) )
    EventManParser::ErrorWithFormatMessage(this, 3221745470LL, L"name");
  if ( !v4 )
    EventManParser::ErrorWithFormatMessage(this, 3221745470LL, L"guid");
  if ( !v5 )
    EventManParser::ErrorWithFormatMessage(this, 3221745470LL, L"symbol");
  if ( XmlReader::FirstChildElement(this) )
  {
    do
    {
      XmlReader::GetLocalName(this);
      v19 = L"channels";
      v20 = 8;
      if ( (unsigned __int8)EventManParser::ElementMatches(this) )
      {
        EventManParser::ChannelListType(this);
      }
      else
      {
        v21 = L"levels";
        v22 = 6;
        if ( (unsigned __int8)EventManParser::ElementMatches(this) )
        {
          EventManParser::LevelListType(this);
        }
        else
        {
          v23 = L"tasks";
          v24 = 5;
          if ( (unsigned __int8)EventManParser::ElementMatches(this) )
          {
            EventManParser::TaskListType(this);
          }
          else
          {
            v25 = L"opcodes";
            v26 = 7;
            if ( (unsigned __int8)EventManParser::ElementMatches(this) )
            {
              EventManParser::OpcodeListType(this);
            }
            else
            {
              v27 = L"keywords";
              v28 = 8;
              if ( (unsigned __int8)EventManParser::ElementMatches(this) )
              {
                EventManParser::KeywordListType(this);
              }
              else
              {
                v36 = L"maps";
                v37 = 4;
                if ( (unsigned __int8)EventManParser::ElementMatches(this) )
                {
                  EventManParser::MapType(this, *a2);
                }
                else
                {
                  v29 = L"namedQueries";
                  v30 = 12;
                  if ( (unsigned __int8)EventManParser::ElementMatches(this) )
                  {
                    EventManParser::NamedQueryType(this);
                  }
                  else
                  {
                    v38 = L"templates";
                    v39 = 9;
                    if ( (unsigned __int8)EventManParser::ElementMatches(this) )
                    {
                      EventManParser::TemplateListType(this);
                    }
                    else
                    {
                      v31 = L"events";
                      v32 = 6;
                      if ( (unsigned __int8)EventManParser::ElementMatches(this) )
                      {
                        EventManParser::DefinitionType(this);
                      }
                      else
                      {
                        v33 = L"filters";
                        v34 = 7;
                        if ( (unsigned __int8)EventManParser::ElementMatches(this) )
                        {
                          EventManParser::FilterListType(this, (__int64)*a2 + 464);
                        }
                        else
                        {
                          *(_QWORD *)&v17 = L"traits";
                          *((_QWORD *)&v17 + 1) = 6;
                          if ( (unsigned __int8)EventManParser::ElementMatches(this) )
                            EventManParser::TraitsType(this, *a2);
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
    while ( XmlReader::NextChildElement(this) );
  }
  return a2;
}

```

## disassembly

```asm
0x180039cdc  mov     rax, rsp
0x180039cdf  mov     [rax+18h], rbx
0x180039ce3  push    rbp
0x180039ce4  push    rsi
0x180039ce5  push    rdi
0x180039ce6  push    r14
0x180039ce8  push    r15
0x180039cea  lea     rbp, [rsp-70h]
0x180039cef  sub     rsp, 170h
0x180039cf6  movaps  xmmword ptr [rax-38h], xmm6
0x180039cfa  mov     rax, cs:__security_cookie
0x180039d01  xor     rax, rsp
0x180039d04  mov     [rbp+90h+var_40], rax
0x180039d08  mov     rdi, rdx
0x180039d0b  mov     rbx, rcx
0x180039d0e  mov     [rbp+90h+var_A0], rdx
0x180039d12  mov     [rsp+190h+var_140], 0
0x180039d1a  mov     rcx, rdx
0x180039d1d  call    ??$make_unique@VETW_PROVIDER_ENTRY@@$$V$0A@@std@@YA?AV?$unique_ptr@VETW_PROVIDER_ENTRY@@U?$default_delete@VETW_PROVIDER_ENTRY@@@std@@@0@XZ; std::make_unique<ETW_PROVIDER_ENTRY,,0>(void)
0x180039d22  mov     [rsp+190h+var_140], 1
0x180039d2a  xor     r15b, r15b
0x180039d2d  xor     r14b, r14b
0x180039d30  mov     rcx, rbx; this
0x180039d33  call    ?FirstAttribute@XmlReader@@QEAA_NXZ; XmlReader::FirstAttribute(void)
0x180039d38  jmp     loc_18003A00F
0x180039d3d  lea     rdx, [rsp+190h+var_160]
0x180039d42  mov     rcx, rbx; this
0x180039d45  call    ?GetQualifiedName@XmlReader@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; XmlReader::GetQualifiedName(void)
0x180039d4a  movups  xmm0, xmmword ptr [rax]
0x180039d4d  movdqu  [rsp+190h+var_150], xmm0
0x180039d53  lea     rcx, [rsp+190h+var_150]
0x180039d58  call    GetAttributeId
0x180039d5d  movzx   ecx, al
0x180039d60  cmp     ecx, 1Ah
0x180039d63  ja      loc_180039ECE
0x180039d69  jz      loc_180039EB3
0x180039d6f  sub     ecx, 4
0x180039d72  jz      loc_180039E43
0x180039d78  sub     ecx, 8
0x180039d7b  jz      loc_180039E0B
0x180039d81  sub     ecx, 0Ah
0x180039d84  jz      short loc_180039DC8
0x180039d86  sub     ecx, 1
0x180039d89  jz      short loc_180039DAD
0x180039d8b  cmp     ecx, 2
0x180039d8e  jnz     loc_18003A007
0x180039d94  lea     rdx, [rsp+190h+var_170]
0x180039d99  mov     rcx, rbx; this
0x180039d9c  call    ?GetValue@XmlReader@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; XmlReader::GetValue(void)
0x180039da1  mov     rcx, [rdi]
0x180039da4  add     rcx, 10h
0x180039da8  jmp     loc_180039FFB
0x180039dad  lea     rdx, [rbp+90h+var_B0]
0x180039db1  mov     rcx, rbx; this
0x180039db4  call    ?GetValue@XmlReader@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; XmlReader::GetValue(void)
0x180039db9  mov     rcx, [rdi]
0x180039dbc  add     rcx, 90h
0x180039dc3  jmp     loc_180039FFB
0x180039dc8  lea     rdx, [rbp+90h+var_C0]
0x180039dcc  mov     rcx, rbx; this
0x180039dcf  call    ?GetValue@XmlReader@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; XmlReader::GetValue(void)
0x180039dd4  movups  xmm0, xmmword ptr [rax]
0x180039dd7  movdqu  [rsp+190h+var_150], xmm0
0x180039ddd  lea     r8, [rsp+190h+var_150]
0x180039de2  lea     rdx, [rbp+90h+var_60]
0x180039de6  mov     rcx, rbx
0x180039de9  call    ?ParseStrTableRef@EventManParser@@AEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@3@@Z; EventManParser::ParseStrTableRef(std::wstring_view)
0x180039dee  mov     rcx, [rdi]
0x180039df1  add     rcx, 30h ; '0'
0x180039df5  mov     rdx, rax
0x180039df8  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180039dfd  lea     rcx, [rbp+90h+var_60]
0x180039e01  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180039e06  jmp     loc_18003A007
0x180039e0b  lea     rdx, [rbp+90h+var_D0]
0x180039e0f  mov     rcx, rbx; this
0x180039e12  call    ?GetValue@XmlReader@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; XmlReader::GetValue(void)
0x180039e17  movups  xmm0, xmmword ptr [rax]
0x180039e1a  movdqu  [rsp+190h+var_150], xmm0
0x180039e20  lea     r8, [rsp+190h+var_150]
0x180039e25  lea     rdx, [rbp+90h+var_70]
0x180039e29  mov     rcx, rbx; this
0x180039e2c  call    ?ParseGuid@EventManParser@@AEAA?AU_GUID@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; EventManParser::ParseGuid(std::wstring_view)
0x180039e31  movups  xmm0, xmmword ptr [rax]
0x180039e34  mov     rax, [rdi]
0x180039e37  movdqu  xmmword ptr [rax], xmm0
0x180039e3b  mov     r15b, 1
0x180039e3e  jmp     loc_18003A007
0x180039e43  lea     rdx, [rbp+90h+var_E0]
0x180039e47  mov     rcx, rbx; this
0x180039e4a  call    ?GetValue@XmlReader@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; XmlReader::GetValue(void)
0x180039e4f  movups  xmm0, xmmword ptr [rax]
0x180039e52  movdqu  [rsp+190h+var_150], xmm0
0x180039e58  lea     r8, [rsp+190h+var_150]
0x180039e5d  lea     rdx, [rbp+90h+var_80]
0x180039e61  mov     rcx, rbx; this
0x180039e64  call    ?ParseGuid@EventManParser@@AEAA?AU_GUID@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; EventManParser::ParseGuid(std::wstring_view)
0x180039e69  movups  xmm0, xmmword ptr [rax]
0x180039e6c  mov     rax, [rdi]
0x180039e6f  movdqu  xmmword ptr [rax+0F0h], xmm0
0x180039e77  mov     rdx, [rdi]
0x180039e7a  xorps   xmm0, xmm0
0x180039e7d  mov     rcx, [rdx+0F0h]
0x180039e84  movq    rax, xmm0
0x180039e89  sub     rcx, rax
0x180039e8c  jnz     short loc_180039EA2
0x180039e8e  mov     rcx, [rdx+0F8h]
0x180039e95  psrldq  xmm0, 8
0x180039e9a  movq    rax, xmm0
0x180039e9f  sub     rcx, rax
0x180039ea2  test    rcx, rcx
0x180039ea5  setnz   al
0x180039ea8  or      [rdx+119h], al
0x180039eae  jmp     loc_18003A007
0x180039eb3  lea     rdx, [rbp+90h+var_F0]
0x180039eb7  mov     rcx, rbx; this
0x180039eba  call    ?GetValue@XmlReader@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; XmlReader::GetValue(void)
0x180039ebf  mov     rcx, [rdi]
0x180039ec2  add     rcx, 0D0h
0x180039ec9  jmp     loc_180039FFB
0x180039ece  sub     ecx, 1Eh
0x180039ed1  jz      loc_180039FE5
0x180039ed7  sub     ecx, 1
0x180039eda  jz      loc_180039FCF
0x180039ee0  sub     ecx, 1
0x180039ee3  jz      short loc_180039F4C
0x180039ee5  sub     ecx, 2
0x180039ee8  jz      short loc_180039F25
0x180039eea  cmp     ecx, 8
0x180039eed  jnz     loc_18003A007
0x180039ef3  lea     rdx, [rbp+90h+var_100]
0x180039ef7  mov     rcx, rbx; this
0x180039efa  call    ?GetValue@XmlReader@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; XmlReader::GetValue(void)
0x180039eff  movups  xmm0, xmmword ptr [rax]
0x180039f02  movdqu  [rsp+190h+var_150], xmm0
0x180039f08  lea     rdx, [rsp+190h+var_150]
0x180039f0d  mov     rcx, rbx; this
0x180039f10  call    ?ParseBool@EventManParser@@AEAA_NV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; EventManParser::ParseBool(std::wstring_view)
0x180039f15  mov     cl, al
0x180039f17  mov     rax, [rdi]
0x180039f1a  mov     [rax+117h], cl
0x180039f20  jmp     loc_18003A007
0x180039f25  lea     rdx, [rbp+90h+var_110]
0x180039f29  mov     rcx, rbx; this
0x180039f2c  call    ?GetValue@XmlReader@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; XmlReader::GetValue(void)
0x180039f31  mov     rcx, [rdi]
0x180039f34  add     rcx, 50h ; 'P'
0x180039f38  mov     r8, [rax+8]
0x180039f3c  mov     rdx, [rax]
0x180039f3f  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x180039f44  mov     r14b, 1
0x180039f47  jmp     loc_18003A007
0x180039f4c  lea     rdx, [rsp+190h+var_130]
0x180039f51  mov     rcx, rbx; this
0x180039f54  call    ?GetValue@XmlReader@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; XmlReader::GetValue(void)
0x180039f59  mov     rsi, [rsp+190h+var_130]
0x180039f5e  mov     r9, [rsp+190h+var_128]
0x180039f63  mov     r8, rsi
0x180039f66  mov     edx, 3
0x180039f6b  lea     rcx, aXml; "Xml"
0x180039f72  call    ??$_Traits_equal@U?$char_traits@_W@std@@@std@@YA_NQEB_W_K01@Z; std::_Traits_equal<std::char_traits<wchar_t>>(wchar_t const * const,unsigned __int64,wchar_t const * const,unsigned __int64)
0x180039f77  test    al, al
0x180039f79  jz      short loc_180039F8A
0x180039f7b  mov     rax, [rdi]
0x180039f7e  mov     dword ptr [rax+110h], 0
0x180039f88  jmp     short loc_18003A007
0x180039f8a  mov     r9, [rsp+190h+var_128]
0x180039f8f  mov     r8, rsi
0x180039f92  mov     edx, 4
0x180039f97  lea     rcx, aWbem; "Wbem"
0x180039f9e  call    ??$_Traits_equal@U?$char_traits@_W@std@@@std@@YA_NQEB_W_K01@Z; std::_Traits_equal<std::char_traits<wchar_t>>(wchar_t const * const,unsigned __int64,wchar_t const * const,unsigned __int64)
0x180039fa3  test    al, al
0x180039fa5  jz      short loc_180039FB6
0x180039fa7  mov     rax, [rdi]
0x180039faa  mov     dword ptr [rax+110h], 1
0x180039fb4  jmp     short loc_18003A007
0x180039fb6  mov     r9, rsi
0x180039fb9  lea     r8, aInvalidValueLs_0; "Invalid value \"%ls\", expected Xml or "...
0x180039fc0  mov     edx, 80070057h; int
0x180039fc5  mov     rcx, rbx; this
0x180039fc8  call    ?ErrorWithPrintf@EventManParser@@AEAAXJPEBDZZ; EventManParser::ErrorWithPrintf(long,char const *,...)
0x180039fcd  jmp     short loc_18003A007
0x180039fcf  lea     rdx, [rsp+190h+var_120]
0x180039fd4  mov     rcx, rbx; this
0x180039fd7  call    ?GetValue@XmlReader@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; XmlReader::GetValue(void)
0x180039fdc  mov     rcx, [rdi]
0x180039fdf  add     rcx, 70h ; 'p'
0x180039fe3  jmp     short loc_180039FFB
0x180039fe5  lea     rdx, [rbp+90h+var_98]
0x180039fe9  mov     rcx, rbx; this
0x180039fec  call    ?GetValue@XmlReader@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; XmlReader::GetValue(void)
0x180039ff1  mov     rcx, [rdi]
0x180039ff4  add     rcx, 0B0h
0x180039ffb  mov     r8, [rax+8]
0x180039fff  mov     rdx, [rax]
0x18003a002  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x18003a007  mov     rcx, rbx; this
0x18003a00a  call    ?NextAttribute@XmlReader@@QEAA_NXZ; XmlReader::NextAttribute(void)
0x18003a00f  test    al, al
0x18003a011  jnz     loc_180039D3D
0x18003a017  mov     rax, [rdi]
0x18003a01a  mov     esi, 0C007EF3Eh
0x18003a01f  cmp     qword ptr [rax+20h], 0
0x18003a024  jnz     short loc_18003A037
0x18003a026  lea     r8, aName_0; "name"
0x18003a02d  mov     edx, esi; int
0x18003a02f  mov     rcx, rbx; this
0x18003a032  call    ?ErrorWithFormatMessage@EventManParser@@AEAAXJZZ; EventManParser::ErrorWithFormatMessage(long,...)
0x18003a037  test    r15b, r15b
0x18003a03a  jnz     short loc_18003A04D
0x18003a03c  lea     r8, aGuid_0; "guid"
0x18003a043  mov     edx, esi; int
0x18003a045  mov     rcx, rbx; this
0x18003a048  call    ?ErrorWithFormatMessage@EventManParser@@AEAAXJZZ; EventManParser::ErrorWithFormatMessage(long,...)
0x18003a04d  test    r14b, r14b
0x18003a050  jnz     short loc_18003A063
0x18003a052  lea     r8, aSymbol; "symbol"
0x18003a059  mov     edx, esi; int
0x18003a05b  mov     rcx, rbx; this
0x18003a05e  call    ?ErrorWithFormatMessage@EventManParser@@AEAAXJZZ; EventManParser::ErrorWithFormatMessage(long,...)
0x18003a063  mov     rcx, rbx; this
0x18003a066  call    ?FirstChildElement@XmlReader@@QEAA_NXZ; XmlReader::FirstChildElement(void)
0x18003a06b  test    al, al
0x18003a06d  jz      loc_18003A420
0x18003a073  mov     esi, 6
0x18003a078  lea     r14d, [rsi+1]
0x18003a07c  lea     r15d, [rsi+2]
0x18003a080  lea     rdx, [rbp+90h+var_B0]
0x18003a084  mov     rcx, rbx; this
0x18003a087  call    ?GetLocalName@XmlReader@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; XmlReader::GetLocalName(void)
0x18003a08c  movups  xmm6, [rbp+90h+var_B0]
0x18003a090  movups  xmm0, xmmword ptr cs:off_18004F7F0; "http://schemas.microsoft.com/win/2004/0"...
0x18003a097  movdqu  [rsp+190h+var_170], xmm6
0x18003a09d  movdqu  [rsp+190h+var_160], xmm0
0x18003a0a3  lea     rax, aChannels; "channels"
0x18003a0aa  mov     [rsp+190h+var_130], rax
0x18003a0af  mov     [rsp+190h+var_128], r15
0x18003a0b4  lea     r9, [rsp+190h+var_170]
0x18003a0b9  lea     r8, [rsp+190h+var_160]
0x18003a0be  lea     rdx, [rsp+190h+var_130]
0x18003a0c3  mov     rcx, rbx; this
0x18003a0c6  call    ?ElementMatches@EventManParser@@AEBA_NV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@00@Z; EventManParser::ElementMatches(std::wstring_view,std::wstring_view,std::wstring_view)
0x18003a0cb  mov     rcx, rbx; this
0x18003a0ce  test    al, al
0x18003a0d0  jz      short loc_18003A0E6
0x18003a0d2  mov     rdx, [rdi]
0x18003a0d5  add     rdx, 188h
0x18003a0dc  call    ?ChannelListType@EventManParser@@AEAAXAEAV?$vector@V?$unique_ptr@VCHANNEL_ENTRY@@U?$default_delete@VCHANNEL_ENTRY@@@std@@@std@@V?$allocator@V?$unique_ptr@VCHANNEL_ENTRY@@U?$default_delete@VCHANNEL_ENTRY@@@std@@@std@@@2@@std@@@Z; EventManParser::ChannelListType(std::vector<std::unique_ptr<CHANNEL_ENTRY>> &)
0x18003a0e1  jmp     loc_18003A410
0x18003a0e6  movups  xmm0, xmmword ptr cs:off_18004F7F0; "http://schemas.microsoft.com/win/2004/0"...
0x18003a0ed  movdqu  [rsp+190h+var_160], xmm6
0x18003a0f3  movdqu  [rsp+190h+var_170], xmm0
0x18003a0f9  lea     rax, aLevels; "levels"
0x18003a100  mov     [rsp+190h+var_120], rax
0x18003a105  mov     [rsp+190h+var_118], rsi
0x18003a10a  lea     r9, [rsp+190h+var_160]
0x18003a10f  lea     r8, [rsp+190h+var_170]
0x18003a114  lea     rdx, [rsp+190h+var_120]
0x18003a119  call    ?ElementMatches@EventManParser@@AEBA_NV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@00@Z; EventManParser::ElementMatches(std::wstring_view,std::wstring_view,std::wstring_view)
0x18003a11e  mov     rcx, rbx; this
0x18003a121  test    al, al
0x18003a123  jz      short loc_18003A139
0x18003a125  mov     rdx, [rdi]
0x18003a128  add     rdx, 128h
0x18003a12f  call    ?LevelListType@EventManParser@@AEAAXAEAV?$vector@V?$unique_ptr@VLEVEL_ENTRY@@U?$default_delete@VLEVEL_ENTRY@@@std@@@std@@V?$allocator@V?$unique_ptr@VLEVEL_ENTRY@@U?$default_delete@VLEVEL_ENTRY@@@std@@@std@@@2@@std@@@Z; EventManParser::LevelListType(std::vector<std::unique_ptr<LEVEL_ENTRY>> &)
0x18003a134  jmp     loc_18003A410
0x18003a139  movups  xmm0, xmmword ptr cs:off_18004F7F0; "http://schemas.microsoft.com/win/2004/0"...
0x18003a140  movdqu  [rsp+190h+var_160], xmm6
0x18003a146  movdqu  [rsp+190h+var_170], xmm0
0x18003a14c  lea     rax, aTasks; "tasks"
0x18003a153  mov     [rbp+90h+var_110], rax
0x18003a157  mov     [rbp+90h+var_108], 5
0x18003a15f  lea     r9, [rsp+190h+var_160]
0x18003a164  lea     r8, [rsp+190h+var_170]
0x18003a169  lea     rdx, [rbp+90h+var_110]
0x18003a16d  call    ?ElementMatches@EventManParser@@AEBA_NV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@00@Z; EventManParser::ElementMatches(std::wstring_view,std::wstring_view,std::wstring_view)
0x18003a172  mov     rcx, rbx; this
0x18003a175  test    al, al
0x18003a177  jz      short loc_18003A194
0x18003a179  mov     rdx, [rdi]
0x18003a17c  lea     r8, [rdx+158h]
0x18003a183  add     rdx, 140h
0x18003a18a  call    ?TaskListType@EventManParser@@AEAAXAEAV?$vector@V?$unique_ptr@VTASK_ENTRY@@U?$default_delete@VTASK_ENTRY@@@std@@@std@@V?$allocator@V?$unique_ptr@VTASK_ENTRY@@U?$default_delete@VTASK_ENTRY@@@std@@@std@@@2@@std@@AEAV?$vector@V?$unique_ptr@VOPCODE_ENTRY@@U?$default_delete@VOPCODE_ENTRY@@@std@@@std@@V?$allocator@V?$unique_ptr@VOPCODE_ENTRY@@U?$default_delete@VOPCODE_ENTRY@@@std@@@std@@@2@@3@@Z; EventManParser::TaskListType(std::vector<std::unique_ptr<TASK_ENTRY>> &,std::vector<std::unique_ptr<OPCODE_ENTRY>> &)
0x18003a18f  jmp     loc_18003A410
0x18003a194  movups  xmm0, xmmword ptr cs:off_18004F7F0; "http://schemas.microsoft.com/win/2004/0"...
0x18003a19b  movdqu  [rsp+190h+var_160], xmm6
0x18003a1a1  movdqu  [rsp+190h+var_170], xmm0
0x18003a1a7  lea     rax, aOpcodes; "opcodes"
0x18003a1ae  mov     [rbp+90h+var_100], rax
0x18003a1b2  mov     [rbp+90h+var_F8], r14
0x18003a1b6  lea     r9, [rsp+190h+var_160]
0x18003a1bb  lea     r8, [rsp+190h+var_170]
0x18003a1c0  lea     rdx, [rbp+90h+var_100]
0x18003a1c4  call    ?ElementMatches@EventManParser@@AEBA_NV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@00@Z; EventManParser::ElementMatches(std::wstring_view,std::wstring_view,std::wstring_view)
0x18003a1c9  mov     rcx, rbx; this
0x18003a1cc  test    al, al
0x18003a1ce  jz      short loc_18003A1E7
0x18003a1d0  mov     rdx, [rdi]
0x18003a1d3  add     rdx, 158h
0x18003a1da  xor     r8d, r8d
  ... truncated ...
```
