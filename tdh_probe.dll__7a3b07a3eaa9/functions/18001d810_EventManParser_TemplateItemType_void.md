# EventManParser::TemplateItemType(void)

- ea: `0x18001d810`
- end: `0x18001dc50`
- name: `?TemplateItemType@EventManParser@@AEAA?AV?$unique_ptr@VTEMPLATE_ENTRY@@U?$default_delete@VTEMPLATE_ENTRY@@@std@@@std@@XZ`
- size: `1088`
- prototype: `__int64 *__fastcall(XmlReader *this, __int64 *)`
- caller_count: `1`
- callee_count: `21`
- tags: `registry_config`

## callers

- `0x18003bae4`

## callees

- `0x18001cb90`
- `0x18001d810`
- `0x18001dc58`
- `0x18001df64`
- `0x18001e284`
- `0x18001e4d8`
- `0x18001e550`
- `0x18001e8f0`
- `0x18001e930`
- `0x18002ea38`
- `0x1800313f8`
- `0x180031550`
- `0x180032cdc`
- `0x1800355ac`
- `0x180035858`
- `0x180037670`
- `0x180037e80`
- `0x180038cc4`
- `0x180039610`
- `0x18003b4dc`
- `0x18003ba24`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 *__fastcall EventManParser::TemplateItemType(XmlReader *this, __int64 *a2)
{
  char v4; // r15
  __int64 v5; // rsi
  bool i; // al
  char AttributeId; // al
  _QWORD *Value; // rax
  __int64 v9; // rcx
  __int128 v10; // xmm6
  __int64 v11; // r14
  __int64 *v12; // rax
  _QWORD *v13; // rdx
  __int64 v14; // rcx
  char *v15; // rcx
  __int64 v16; // r14
  __int64 *v17; // rax
  _QWORD *v18; // rdx
  __int64 v19; // rcx
  __int64 *v20; // rax
  __int64 v21; // rbx
  __int64 v22; // rcx
  _QWORD *v23; // rdx
  __int64 v24; // rcx
  _QWORD *v25; // rdx
  _QWORD v27[2]; // [rsp+28h] [rbp-89h] BYREF
  __int128 v28; // [rsp+38h] [rbp-79h]
  __int128 v29; // [rsp+48h] [rbp-69h]
  int v30; // [rsp+58h] [rbp-59h]
  __int128 v31; // [rsp+68h] [rbp-49h] BYREF
  char v32; // [rsp+78h] [rbp-39h] BYREF
  char v33[8]; // [rsp+80h] [rbp-31h] BYREF
  const wchar_t *v34; // [rsp+88h] [rbp-29h]
  __int64 v35; // [rsp+90h] [rbp-21h]
  const wchar_t *v36; // [rsp+98h] [rbp-19h]
  __int64 v37; // [rsp+A0h] [rbp-11h]
  const wchar_t *v38; // [rsp+A8h] [rbp-9h]
  __int64 v39; // [rsp+B0h] [rbp-1h]
  const wchar_t *v40; // [rsp+B8h] [rbp+7h]
  __int64 v41; // [rsp+C0h] [rbp+Fh]
  __int128 v42; // [rsp+C8h] [rbp+17h]
  char v43; // [rsp+128h] [rbp+77h] BYREF
  __int64 v44; // [rsp+130h] [rbp+7Fh] BYREF

  std::make_unique<TEMPLATE_ENTRY,,0>(a2);
  v30 = 1;
  v4 = 0;
  v5 = 0;
  v44 = 0;
  for ( i = XmlReader::FirstAttribute(this); i; i = XmlReader::NextAttribute(this) )
  {
    v31 = *(_OWORD *)XmlReader::GetQualifiedName(this);
    AttributeId = GetAttributeId(&v31);
    switch ( AttributeId )
    {
      case 25:
        Value = (_QWORD *)XmlReader::GetValue(this);
        v9 = *a2 + 32;
        break;
      case 35:
        v31 = *(_OWORD *)XmlReader::GetValue(this);
        *(_DWORD *)(*a2 + 168) = EventManParser::ParseUInt32(this);
        continue;
      case 38:
        Value = (_QWORD *)XmlReader::GetValue(this);
        v9 = *a2;
        break;
      default:
        continue;
    }
    std::wstring::_Assign<wchar_t>(v9, *Value);
  }
  if ( !*(_QWORD *)(*a2 + 16) )
    EventManParser::ErrorWithFormatMessage(this, 3221745470LL, L"tid");
  if ( XmlReader::FirstChildElement(this) )
  {
    while ( 1 )
    {
      XmlReader::GetLocalName(this);
      v10 = v42;
      v28 = v42;
      v29 = *(_OWORD *)&off_18004F7F0;
      v36 = L"data";
      v37 = 4;
      if ( (unsigned __int8)EventManParser::ElementMatches(this) )
      {
        v11 = *a2;
        v12 = (__int64 *)EventManParser::DataDefinitionType(this);
        v13 = *(_QWORD **)(v11 + 112);
        if ( v13 == *(_QWORD **)(v11 + 120) )
        {
          std::vector<std::unique_ptr<PROPERTY_ENTRY>>::_Emplace_reallocate<std::unique_ptr<PROPERTY_ENTRY>>(
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
          v5 = v44;
        }
        v15 = &v43;
      }
      else
      {
        v29 = v10;
        v28 = *(_OWORD *)&off_18004F7F0;
        v38 = L"struct";
        v39 = 6;
        if ( !(unsigned __int8)EventManParser::ElementMatches(this) )
        {
          v29 = v10;
          v28 = *(_OWORD *)&off_18004F7F0;
          v40 = L"binary";
          v41 = 6;
          if ( (unsigned __int8)EventManParser::ElementMatches(this) )
          {
            if ( v5 )
            {
              EventManParser::ErrorWithFormatMessage(this, 3221745495LL);
            }
            else
            {
              v20 = (__int64 *)EventManParser::TemplateItemBinaryType(this);
              v5 = *v20;
              *v20 = 0;
              v44 = v5;
              std::unique_ptr<PROPERTY_ENTRY>::~unique_ptr<PROPERTY_ENTRY>(v33);
              std::wstring::_Assign<wchar_t>(v5 + 32, L"win:Binary");
              std::wstring::_Assign<wchar_t>(v5 + 176, L"__binLength");
            }
          }
          else
          {
            v29 = v10;
            v28 = *(_OWORD *)&off_18004F7F0;
            v34 = L"UserData";
            v35 = 8;
            if ( (unsigned __int8)EventManParser::ElementMatches(this) && !v4 )
            {
              XmlReader::ReadInnerXml(this);
              std::wstring::_Assign<wchar_t>(*a2 + 64, v31);
              if ( *(_QWORD *)(*a2 + 80) )
                *(_DWORD *)(*a2 + 96) = 2;
              v4 = 1;
            }
          }
          goto LABEL_34;
        }
        v16 = *a2;
        v17 = (__int64 *)EventManParser::StructDefinitionType(this);
        v18 = *(_QWORD **)(v16 + 112);
        if ( v18 == *(_QWORD **)(v16 + 120) )
        {
          std::vector<std::unique_ptr<PROPERTY_ENTRY>>::_Emplace_reallocate<std::unique_ptr<PROPERTY_ENTRY>>(
            v16 + 104,
            v18,
            v17);
        }
        else
        {
          v19 = *v17;
          *v17 = 0;
          *v18 = v19;
          *(_QWORD *)(v16 + 112) += 8LL;
          v5 = v44;
        }
        v15 = &v32;
      }
      std::unique_ptr<PROPERTY_ENTRY>::~unique_ptr<PROPERTY_ENTRY>(v15);
LABEL_34:
      if ( !XmlReader::NextChildElement(this) )
      {
        if ( v5 )
        {
          v43 = 0;
          std::make_unique<PROPERTY_ENTRY,bool,0>(v27, &v43);
          v21 = v27[0];
          std::wstring::_Assign<wchar_t>(v27[0], L"__binLength");
          std::wstring::_Assign<wchar_t>(v21 + 32, L"win:UInt32");
          v22 = *a2 + 104;
          v23 = *(_QWORD **)(*a2 + 112);
          if ( v23 == *(_QWORD **)(*a2 + 120) )
          {
            std::vector<std::unique_ptr<PROPERTY_ENTRY>>::_Emplace_reallocate<std::unique_ptr<PROPERTY_ENTRY>>(
              v22,
              v23,
              v27);
          }
          else
          {
            v27[0] = 0;
            *v23 = v21;
            *(_QWORD *)(v22 + 8) += 8LL;
            v5 = v44;
          }
          v24 = *a2 + 104;
          v25 = *(_QWORD **)(*a2 + 112);
          if ( v25 == *(_QWORD **)(*a2 + 120) )
          {
            std::vector<std::unique_ptr<PROPERTY_ENTRY>>::_Emplace_reallocate<std::unique_ptr<PROPERTY_ENTRY>>(
              v24,
              v25,
              &v44);
          }
          else
          {
            v44 = 0;
            *v25 = v5;
            *(_QWORD *)(v24 + 8) += 8LL;
          }
          std::unique_ptr<PROPERTY_ENTRY>::~unique_ptr<PROPERTY_ENTRY>(v27);
        }
        break;
      }
    }
  }
  std::unique_ptr<PROPERTY_ENTRY>::~unique_ptr<PROPERTY_ENTRY>(&v44);
  return a2;
}

```

## disassembly

```asm
0x18001d810  mov     rax, rsp
0x18001d813  mov     [rax+8], rbx
0x18001d817  mov     [rax+10h], rdx
0x18001d81b  push    rbp
0x18001d81c  push    rsi
0x18001d81d  push    rdi
0x18001d81e  push    r14
0x18001d820  push    r15
0x18001d822  lea     rbp, [rax-5Fh]
0x18001d826  sub     rsp, 0E0h
0x18001d82d  movaps  xmmword ptr [rax-38h], xmm6
0x18001d831  mov     rdi, rdx
0x18001d834  mov     rbx, rcx
0x18001d837  mov     [rbp+57h+var_B0], 0
0x18001d83e  mov     rcx, rdx
0x18001d841  call    ??$make_unique@VTEMPLATE_ENTRY@@$$V$0A@@std@@YA?AV?$unique_ptr@VTEMPLATE_ENTRY@@U?$default_delete@VTEMPLATE_ENTRY@@@std@@@0@XZ; std::make_unique<TEMPLATE_ENTRY,,0>(void)
0x18001d846  mov     [rbp+57h+var_B0], 1
0x18001d84d  xor     r15b, r15b
0x18001d850  xor     esi, esi
0x18001d852  mov     [rbp+57h+arg_18], rsi
0x18001d856  mov     rcx, rbx; this
0x18001d859  call    ?FirstAttribute@XmlReader@@QEAA_NXZ; XmlReader::FirstAttribute(void)
0x18001d85e  jmp     loc_18001D8EF
0x18001d863  lea     rdx, [rbp+57h+var_C0]
0x18001d867  mov     rcx, rbx; this
0x18001d86a  call    ?GetQualifiedName@XmlReader@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; XmlReader::GetQualifiedName(void)
0x18001d86f  movups  xmm0, xmmword ptr [rax]
0x18001d872  movdqu  [rbp+57h+var_A0], xmm0
0x18001d877  lea     rcx, [rbp+57h+var_A0]
0x18001d87b  call    GetAttributeId
0x18001d880  cmp     al, 19h
0x18001d882  jz      short loc_18001D8C8
0x18001d884  cmp     al, 23h ; '#'
0x18001d886  jz      short loc_18001D89D
0x18001d888  cmp     al, 26h ; '&'
0x18001d88a  jnz     short loc_18001D8E7
0x18001d88c  lea     rdx, [rbp+57h+var_D0]
0x18001d890  mov     rcx, rbx; this
0x18001d893  call    ?GetValue@XmlReader@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; XmlReader::GetValue(void)
0x18001d898  mov     rcx, [rdi]
0x18001d89b  jmp     short loc_18001D8DB
0x18001d89d  lea     rdx, [rbp+57h+var_40]
0x18001d8a1  mov     rcx, rbx; this
0x18001d8a4  call    ?GetValue@XmlReader@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; XmlReader::GetValue(void)
0x18001d8a9  movups  xmm0, xmmword ptr [rax]
0x18001d8ac  movdqu  [rbp+57h+var_A0], xmm0
0x18001d8b1  lea     rdx, [rbp+57h+var_A0]
0x18001d8b5  mov     rcx, rbx; this
0x18001d8b8  call    ?ParseUInt32@EventManParser@@AEAAIV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; EventManParser::ParseUInt32(std::wstring_view)
0x18001d8bd  mov     rcx, [rdi]
0x18001d8c0  mov     [rcx+0A8h], eax
0x18001d8c6  jmp     short loc_18001D8E7
0x18001d8c8  lea     rdx, [rbp+57h+var_80]
0x18001d8cc  mov     rcx, rbx; this
0x18001d8cf  call    ?GetValue@XmlReader@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; XmlReader::GetValue(void)
0x18001d8d4  mov     rcx, [rdi]
0x18001d8d7  add     rcx, 20h ; ' '
0x18001d8db  mov     r8, [rax+8]
0x18001d8df  mov     rdx, [rax]
0x18001d8e2  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x18001d8e7  mov     rcx, rbx; this
0x18001d8ea  call    ?NextAttribute@XmlReader@@QEAA_NXZ; XmlReader::NextAttribute(void)
0x18001d8ef  test    al, al
0x18001d8f1  jnz     loc_18001D863
0x18001d8f7  mov     rax, [rdi]
0x18001d8fa  cmp     qword ptr [rax+10h], 0
0x18001d8ff  jnz     short loc_18001D915
0x18001d901  lea     r8, aTid; "tid"
0x18001d908  mov     edx, 0C007EF3Eh; int
0x18001d90d  mov     rcx, rbx; this
0x18001d910  call    ?ErrorWithFormatMessage@EventManParser@@AEAAXJZZ; EventManParser::ErrorWithFormatMessage(long,...)
0x18001d915  mov     rcx, rbx; this
0x18001d918  call    ?FirstChildElement@XmlReader@@QEAA_NXZ; XmlReader::FirstChildElement(void)
0x18001d91d  test    al, al
0x18001d91f  jz      loc_18001DC27
0x18001d925  lea     rdx, [rbp+57h+var_40]
0x18001d929  mov     rcx, rbx; this
0x18001d92c  call    ?GetLocalName@XmlReader@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; XmlReader::GetLocalName(void)
0x18001d931  movups  xmm6, [rbp+57h+var_40]
0x18001d935  movups  xmm0, xmmword ptr cs:off_18004F7F0; "http://schemas.microsoft.com/win/2004/0"...
0x18001d93c  movdqu  [rbp+57h+var_D0], xmm6
0x18001d941  movdqu  [rbp+57h+var_C0], xmm0
0x18001d946  lea     rax, aData_0; "data"
0x18001d94d  mov     [rbp+57h+var_70], rax
0x18001d951  mov     [rbp+57h+var_68], 4
0x18001d959  lea     r9, [rbp+57h+var_D0]
0x18001d95d  lea     r8, [rbp+57h+var_C0]
0x18001d961  lea     rdx, [rbp+57h+var_70]
0x18001d965  mov     rcx, rbx; this
0x18001d968  call    ?ElementMatches@EventManParser@@AEBA_NV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@00@Z; EventManParser::ElementMatches(std::wstring_view,std::wstring_view,std::wstring_view)
0x18001d96d  mov     rcx, rbx; this
0x18001d970  test    al, al
0x18001d972  jz      short loc_18001D9B6
0x18001d974  mov     r14, [rdi]
0x18001d977  lea     rdx, [rbp+57h+arg_10]
0x18001d97b  call    ?DataDefinitionType@EventManParser@@AEAA?AV?$unique_ptr@VPROPERTY_ENTRY@@U?$default_delete@VPROPERTY_ENTRY@@@std@@@std@@XZ; EventManParser::DataDefinitionType(void)
0x18001d980  nop
0x18001d981  mov     rdx, [r14+70h]
0x18001d985  cmp     rdx, [r14+78h]
0x18001d989  jz      short loc_18001D9A3
0x18001d98b  mov     rcx, [rax]
0x18001d98e  mov     qword ptr [rax], 0
0x18001d995  mov     [rdx], rcx
0x18001d998  add     qword ptr [r14+70h], 8
0x18001d99d  mov     rsi, [rbp+57h+arg_18]
0x18001d9a1  jmp     short loc_18001D9B0
0x18001d9a3  mov     r8, rax
0x18001d9a6  lea     rcx, [r14+68h]
0x18001d9aa  call    ??$_Emplace_reallocate@V?$unique_ptr@VPROPERTY_ENTRY@@U?$default_delete@VPROPERTY_ENTRY@@@std@@@std@@@?$vector@V?$unique_ptr@VPROPERTY_ENTRY@@U?$default_delete@VPROPERTY_ENTRY@@@std@@@std@@V?$allocator@V?$unique_ptr@VPROPERTY_ENTRY@@U?$default_delete@VPROPERTY_ENTRY@@@std@@@std@@@2@@std@@AEAAPEAV?$unique_ptr@VPROPERTY_ENTRY@@U?$default_delete@VPROPERTY_ENTRY@@@std@@@1@QEAV21@$$QEAV21@@Z; std::vector<std::unique_ptr<PROPERTY_ENTRY>>::_Emplace_reallocate<std::unique_ptr<PROPERTY_ENTRY>>(std::unique_ptr<PROPERTY_ENTRY> * const,std::unique_ptr<PROPERTY_ENTRY> &&)
0x18001d9af  nop
0x18001d9b0  lea     rcx, [rbp+57h+arg_10]
0x18001d9b4  jmp     short loc_18001DA32
0x18001d9b6  movups  xmm0, xmmword ptr cs:off_18004F7F0; "http://schemas.microsoft.com/win/2004/0"...
0x18001d9bd  movdqu  [rbp+57h+var_C0], xmm6
0x18001d9c2  movdqu  [rbp+57h+var_D0], xmm0
0x18001d9c7  lea     rax, aStruct; "struct"
0x18001d9ce  mov     [rbp+57h+var_60], rax
0x18001d9d2  mov     [rbp+57h+var_58], 6
0x18001d9da  lea     r9, [rbp+57h+var_C0]
0x18001d9de  lea     r8, [rbp+57h+var_D0]
0x18001d9e2  lea     rdx, [rbp+57h+var_60]
0x18001d9e6  call    ?ElementMatches@EventManParser@@AEBA_NV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@00@Z; EventManParser::ElementMatches(std::wstring_view,std::wstring_view,std::wstring_view)
0x18001d9eb  mov     rcx, rbx; this
0x18001d9ee  test    al, al
0x18001d9f0  jz      short loc_18001DA3C
0x18001d9f2  mov     r14, [rdi]
0x18001d9f5  lea     rdx, [rbp+57h+var_90]
0x18001d9f9  call    ?StructDefinitionType@EventManParser@@AEAA?AV?$unique_ptr@VPROPERTY_ENTRY@@U?$default_delete@VPROPERTY_ENTRY@@@std@@@std@@XZ; EventManParser::StructDefinitionType(void)
0x18001d9fe  nop
0x18001d9ff  mov     rdx, [r14+70h]
0x18001da03  cmp     rdx, [r14+78h]
0x18001da07  jz      short loc_18001DA21
0x18001da09  mov     rcx, [rax]
0x18001da0c  mov     qword ptr [rax], 0
0x18001da13  mov     [rdx], rcx
0x18001da16  add     qword ptr [r14+70h], 8
0x18001da1b  mov     rsi, [rbp+57h+arg_18]
0x18001da1f  jmp     short loc_18001DA2E
0x18001da21  mov     r8, rax
0x18001da24  lea     rcx, [r14+68h]
0x18001da28  call    ??$_Emplace_reallocate@V?$unique_ptr@VPROPERTY_ENTRY@@U?$default_delete@VPROPERTY_ENTRY@@@std@@@std@@@?$vector@V?$unique_ptr@VPROPERTY_ENTRY@@U?$default_delete@VPROPERTY_ENTRY@@@std@@@std@@V?$allocator@V?$unique_ptr@VPROPERTY_ENTRY@@U?$default_delete@VPROPERTY_ENTRY@@@std@@@std@@@2@@std@@AEAAPEAV?$unique_ptr@VPROPERTY_ENTRY@@U?$default_delete@VPROPERTY_ENTRY@@@std@@@1@QEAV21@$$QEAV21@@Z; std::vector<std::unique_ptr<PROPERTY_ENTRY>>::_Emplace_reallocate<std::unique_ptr<PROPERTY_ENTRY>>(std::unique_ptr<PROPERTY_ENTRY> * const,std::unique_ptr<PROPERTY_ENTRY> &&)
0x18001da2d  nop
0x18001da2e  lea     rcx, [rbp+57h+var_90]
0x18001da32  call    ??1?$unique_ptr@VPROPERTY_ENTRY@@U?$default_delete@VPROPERTY_ENTRY@@@std@@@std@@QEAA@XZ; std::unique_ptr<PROPERTY_ENTRY>::~unique_ptr<PROPERTY_ENTRY>(void)
0x18001da37  jmp     loc_18001DB62
0x18001da3c  movups  xmm0, xmmword ptr cs:off_18004F7F0; "http://schemas.microsoft.com/win/2004/0"...
0x18001da43  movdqu  [rbp+57h+var_C0], xmm6
0x18001da48  movdqu  [rbp+57h+var_D0], xmm0
0x18001da4d  lea     rax, aBinary; "binary"
0x18001da54  mov     [rbp+57h+var_50], rax
0x18001da58  mov     [rbp+57h+var_48], 6
0x18001da60  lea     r9, [rbp+57h+var_C0]
0x18001da64  lea     r8, [rbp+57h+var_D0]
0x18001da68  lea     rdx, [rbp+57h+var_50]
0x18001da6c  call    ?ElementMatches@EventManParser@@AEBA_NV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@00@Z; EventManParser::ElementMatches(std::wstring_view,std::wstring_view,std::wstring_view)
0x18001da71  test    al, al
0x18001da73  jz      short loc_18001DAED
0x18001da75  test    rsi, rsi
0x18001da78  jz      short loc_18001DA99
0x18001da7a  mov     r8, [rdi]
0x18001da7d  cmp     qword ptr [r8+18h], 7
0x18001da82  jbe     short loc_18001DA87
0x18001da84  mov     r8, [r8]
0x18001da87  mov     edx, 0C007EF57h; int
0x18001da8c  mov     rcx, rbx; this
0x18001da8f  call    ?ErrorWithFormatMessage@EventManParser@@AEAAXJZZ; EventManParser::ErrorWithFormatMessage(long,...)
0x18001da94  jmp     loc_18001DB62
0x18001da99  lea     rdx, [rbp+57h+var_88]
0x18001da9d  mov     rcx, rbx; this
0x18001daa0  call    ?TemplateItemBinaryType@EventManParser@@AEAA?AV?$unique_ptr@VPROPERTY_ENTRY@@U?$default_delete@VPROPERTY_ENTRY@@@std@@@std@@XZ; EventManParser::TemplateItemBinaryType(void)
0x18001daa5  mov     rsi, [rax]
0x18001daa8  mov     qword ptr [rax], 0
0x18001daaf  mov     [rbp+57h+arg_18], rsi
0x18001dab3  lea     rcx, [rbp+57h+var_88]
0x18001dab7  call    ??1?$unique_ptr@VPROPERTY_ENTRY@@U?$default_delete@VPROPERTY_ENTRY@@@std@@@std@@QEAA@XZ; std::unique_ptr<PROPERTY_ENTRY>::~unique_ptr<PROPERTY_ENTRY>(void)
0x18001dabc  lea     rcx, [rsi+20h]
0x18001dac0  mov     r8d, 0Ah
0x18001dac6  lea     rdx, aWinBinary; "win:Binary"
0x18001dacd  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x18001dad2  lea     rcx, [rsi+0B0h]
0x18001dad9  mov     r8d, 0Bh
0x18001dadf  lea     rdx, aBinlength; "__binLength"
0x18001dae6  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x18001daeb  jmp     short loc_18001DB62
0x18001daed  movups  xmm0, xmmword ptr cs:off_18004F7F0; "http://schemas.microsoft.com/win/2004/0"...
0x18001daf4  movdqu  [rbp+57h+var_C0], xmm6
0x18001daf9  movdqu  [rbp+57h+var_D0], xmm0
0x18001dafe  lea     rax, aUserdata; "UserData"
0x18001db05  mov     [rbp+57h+var_80], rax
0x18001db09  mov     [rbp+57h+var_78], 8
0x18001db11  lea     r9, [rbp+57h+var_C0]
0x18001db15  lea     r8, [rbp+57h+var_D0]
0x18001db19  lea     rdx, [rbp+57h+var_80]
0x18001db1d  mov     rcx, rbx; this
0x18001db20  call    ?ElementMatches@EventManParser@@AEBA_NV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@00@Z; EventManParser::ElementMatches(std::wstring_view,std::wstring_view,std::wstring_view)
0x18001db25  test    al, al
0x18001db27  jz      short loc_18001DB62
0x18001db29  test    r15b, r15b
0x18001db2c  jnz     short loc_18001DB62
0x18001db2e  lea     rdx, [rbp+57h+var_A0]
0x18001db32  mov     rcx, rbx; this
0x18001db35  call    ?ReadInnerXml@XmlReader@@QEAA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; XmlReader::ReadInnerXml(void)
0x18001db3a  mov     rcx, [rdi]
0x18001db3d  add     rcx, 40h ; '@'
0x18001db41  mov     r8, qword ptr [rbp+57h+var_A0+8]
0x18001db45  mov     rdx, qword ptr [rbp+57h+var_A0]
0x18001db49  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x18001db4e  mov     rax, [rdi]
0x18001db51  cmp     qword ptr [rax+50h], 0
0x18001db56  jz      short loc_18001DB5F
0x18001db58  mov     dword ptr [rax+60h], 2
0x18001db5f  mov     r15b, 1
0x18001db62  mov     rcx, rbx; this
0x18001db65  call    ?NextChildElement@XmlReader@@QEAA_NXZ; XmlReader::NextChildElement(void)
0x18001db6a  test    al, al
0x18001db6c  jnz     loc_18001D925
0x18001db72  test    rsi, rsi
0x18001db75  jz      loc_18001DC27
0x18001db7b  mov     [rbp+57h+arg_10], al
0x18001db7e  lea     rdx, [rbp+57h+arg_10]
0x18001db82  lea     rcx, [rsp+100h+var_E0]
0x18001db87  call    ??$make_unique@VPROPERTY_ENTRY@@_N$0A@@std@@YA?AV?$unique_ptr@VPROPERTY_ENTRY@@U?$default_delete@VPROPERTY_ENTRY@@@std@@@0@$$QEA_N@Z; std::make_unique<PROPERTY_ENTRY,bool,0>(bool &&)
0x18001db8c  nop
0x18001db8d  mov     rbx, [rsp+100h+var_E0]
0x18001db92  mov     r8d, 0Bh
0x18001db98  lea     rdx, aBinlength; "__binLength"
0x18001db9f  mov     rcx, rbx
0x18001dba2  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x18001dba7  lea     rcx, [rbx+20h]
0x18001dbab  mov     r8d, 0Ah
0x18001dbb1  lea     rdx, aWinUint32; "win:UInt32"
0x18001dbb8  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x18001dbbd  mov     rcx, [rdi]
0x18001dbc0  add     rcx, 68h ; 'h'
0x18001dbc4  mov     rdx, [rcx+8]
0x18001dbc8  cmp     rdx, [rcx+10h]
0x18001dbcc  jz      short loc_18001DBE5
0x18001dbce  mov     [rsp+100h+var_E0], 0
0x18001dbd7  mov     [rdx], rbx
0x18001dbda  add     qword ptr [rcx+8], 8
0x18001dbdf  mov     rsi, [rbp+57h+arg_18]
0x18001dbe3  jmp     short loc_18001DBEF
0x18001dbe5  lea     r8, [rsp+100h+var_E0]
0x18001dbea  call    ??$_Emplace_reallocate@V?$unique_ptr@VPROPERTY_ENTRY@@U?$default_delete@VPROPERTY_ENTRY@@@std@@@std@@@?$vector@V?$unique_ptr@VPROPERTY_ENTRY@@U?$default_delete@VPROPERTY_ENTRY@@@std@@@std@@V?$allocator@V?$unique_ptr@VPROPERTY_ENTRY@@U?$default_delete@VPROPERTY_ENTRY@@@std@@@std@@@2@@std@@AEAAPEAV?$unique_ptr@VPROPERTY_ENTRY@@U?$default_delete@VPROPERTY_ENTRY@@@std@@@1@QEAV21@$$QEAV21@@Z; std::vector<std::unique_ptr<PROPERTY_ENTRY>>::_Emplace_reallocate<std::unique_ptr<PROPERTY_ENTRY>>(std::unique_ptr<PROPERTY_ENTRY> * const,std::unique_ptr<PROPERTY_ENTRY> &&)
0x18001dbef  mov     rcx, [rdi]
0x18001dbf2  add     rcx, 68h ; 'h'
0x18001dbf6  mov     rdx, [rcx+8]
0x18001dbfa  cmp     rdx, [rcx+10h]
0x18001dbfe  jz      short loc_18001DC12
0x18001dc00  mov     [rbp+57h+arg_18], 0
0x18001dc08  mov     [rdx], rsi
0x18001dc0b  add     qword ptr [rcx+8], 8
0x18001dc10  jmp     short loc_18001DC1C
0x18001dc12  lea     r8, [rbp+57h+arg_18]
0x18001dc16  call    ??$_Emplace_reallocate@V?$unique_ptr@VPROPERTY_ENTRY@@U?$default_delete@VPROPERTY_ENTRY@@@std@@@std@@@?$vector@V?$unique_ptr@VPROPERTY_ENTRY@@U?$default_delete@VPROPERTY_ENTRY@@@std@@@std@@V?$allocator@V?$unique_ptr@VPROPERTY_ENTRY@@U?$default_delete@VPROPERTY_ENTRY@@@std@@@std@@@2@@std@@AEAAPEAV?$unique_ptr@VPROPERTY_ENTRY@@U?$default_delete@VPROPERTY_ENTRY@@@std@@@1@QEAV21@$$QEAV21@@Z; std::vector<std::unique_ptr<PROPERTY_ENTRY>>::_Emplace_reallocate<std::unique_ptr<PROPERTY_ENTRY>>(std::unique_ptr<PROPERTY_ENTRY> * const,std::unique_ptr<PROPERTY_ENTRY> &&)
0x18001dc1b  nop
0x18001dc1c  lea     rcx, [rsp+100h+var_E0]
0x18001dc21  call    ??1?$unique_ptr@VPROPERTY_ENTRY@@U?$default_delete@VPROPERTY_ENTRY@@@std@@@std@@QEAA@XZ; std::unique_ptr<PROPERTY_ENTRY>::~unique_ptr<PROPERTY_ENTRY>(void)
0x18001dc26  nop
0x18001dc27  lea     rcx, [rbp+57h+arg_18]
0x18001dc2b  call    ??1?$unique_ptr@VPROPERTY_ENTRY@@U?$default_delete@VPROPERTY_ENTRY@@@std@@@std@@QEAA@XZ; std::unique_ptr<PROPERTY_ENTRY>::~unique_ptr<PROPERTY_ENTRY>(void)
0x18001dc30  mov     rax, rdi
0x18001dc33  lea     r11, [rsp+100h+var_20]
0x18001dc3b  mov     rbx, [r11+30h]
0x18001dc3f  movaps  xmm6, xmmword ptr [r11-10h]
0x18001dc44  mov     rsp, r11
0x18001dc47  pop     r15
0x18001dc49  pop     r14
0x18001dc4b  pop     rdi
0x18001dc4c  pop     rsi
0x18001dc4d  pop     rbp
0x18001dc4e  retn
```
