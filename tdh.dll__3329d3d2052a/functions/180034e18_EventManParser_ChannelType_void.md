# EventManParser::ChannelType(void)

- ea: `0x180034e18`
- end: `0x1800351e2`
- name: `?ChannelType@EventManParser@@AEAA?AV?$unique_ptr@VCHANNEL_ENTRY@@U?$default_delete@VCHANNEL_ENTRY@@@std@@@std@@XZ`
- size: `970`
- prototype: `__int64 __fastcall(XmlReader *this)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config`

## callers

- `0x180034cbc`

## callees

- `0x18001df64`
- `0x18001e0cc`
- `0x18001e284`
- `0x18001e4d8`
- `0x18001e550`
- `0x18001e8f0`
- `0x18001e930`
- `0x18001ed1c`
- `0x1800207c0`
- `0x18003110c`
- `0x180033da0`
- `0x180034e18`
- `0x1800358f4`
- `0x180037670`
- `0x180039328`
- `0x180039674`
- `0x18003c754`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 *__fastcall EventManParser::ChannelType(XmlReader *this, __int64 *a2)
{
  char v4; // r15
  bool i; // al
  char AttributeId; // al
  const wchar_t *v7; // rsi
  _QWORD *Value; // rax
  __int64 v9; // rcx
  __int64 v10; // rax
  const wchar_t *v11; // rsi
  char v13[4]; // [rsp+20h] [rbp-E0h] BYREF
  int v14; // [rsp+24h] [rbp-DCh]
  __int128 v15; // [rsp+30h] [rbp-D0h] BYREF
  const wchar_t *v16; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v17[3]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v18; // [rsp+78h] [rbp-88h] BYREF
  __int64 v19; // [rsp+88h] [rbp-78h] BYREF
  __int64 v20; // [rsp+98h] [rbp-68h] BYREF
  __int64 v21; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v22; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v23; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v24; // [rsp+D8h] [rbp-28h] BYREF
  _BYTE v25[32]; // [rsp+E8h] [rbp-18h] BYREF

  v17[2] = a2;
  v14 = 0;
  v13[0] = 0;
  std::make_unique<CHANNEL_ENTRY,bool,0>(a2, v13);
  v14 = 1;
  v4 = 0;
  for ( i = XmlReader::FirstAttribute(this); i; i = XmlReader::NextAttribute(this) )
  {
    v15 = *(_OWORD *)XmlReader::GetQualifiedName(this);
    AttributeId = GetAttributeId(&v15);
    switch ( AttributeId )
    {
      case 0:
        Value = XmlReader::GetValue(this, &v24);
        v9 = *a2 + 152;
        goto LABEL_35;
      case 3:
        Value = XmlReader::GetValue(this, &v23);
        v9 = *a2 + 64;
        goto LABEL_35;
      case 8:
        v15 = *(_OWORD *)XmlReader::GetValue(this, &v22);
        *(_BYTE *)(*a2 + 112) = EventManParser::ParseBool(this);
        continue;
      case 16:
        XmlReader::GetValue(this, v17);
        v11 = (const wchar_t *)v17[0];
        if ( (unsigned __int8)std::_Traits_equal<std::char_traits<wchar_t>>(L"Application", 11) )
        {
          *(_DWORD *)(*a2 + 100) = 0;
        }
        else if ( (unsigned __int8)std::_Traits_equal<std::char_traits<wchar_t>>(L"System", 6) )
        {
          *(_DWORD *)(*a2 + 100) = 1;
        }
        else if ( (unsigned __int8)std::_Traits_equal<std::char_traits<wchar_t>>(L"Custom", 6) )
        {
          *(_DWORD *)(*a2 + 100) = 2;
        }
        else
        {
          EventManParser::ErrorWithPrintf(this, -2147024809, "Invalid value \"%ls\", expected System or Custom.", v11);
        }
        break;
      case 22:
        v15 = *(_OWORD *)XmlReader::GetValue(this, &v21);
        v10 = EventManParser::ParseStrTableRef(this, v25, &v15);
        std::wstring::operator=(*a2 + 120, v10);
        std::wstring::_Tidy_deallocate(v25);
        continue;
      case 25:
        Value = XmlReader::GetValue(this, &v20);
        v9 = *a2;
        goto LABEL_35;
      case 34:
        Value = XmlReader::GetValue(this, &v19);
        v9 = *a2 + 32;
LABEL_35:
        std::wstring::_Assign<wchar_t>(v9, *Value, Value[1]);
        continue;
      case 39:
        XmlReader::GetValue(this, &v16);
        v7 = v16;
        if ( (unsigned __int8)std::_Traits_equal<std::char_traits<wchar_t>>(L"Admin", 5) )
        {
          *(_DWORD *)(*a2 + 96) = 0;
        }
        else if ( (unsigned __int8)std::_Traits_equal<std::char_traits<wchar_t>>(L"Operational", 11) )
        {
          *(_DWORD *)(*a2 + 96) = 1;
        }
        else if ( (unsigned __int8)std::_Traits_equal<std::char_traits<wchar_t>>(L"Analytic", 8) )
        {
          *(_DWORD *)(*a2 + 96) = 2;
        }
        else if ( (unsigned __int8)std::_Traits_equal<std::char_traits<wchar_t>>(L"Debug", 5) )
        {
          *(_DWORD *)(*a2 + 96) = 3;
        }
        else
        {
          EventManParser::ErrorWithPrintf(
            this,
            -2147024809,
            "Invalid value \"%ls\", expected Admin, Operational, Analytic, or Debug.",
            v7);
        }
        v4 = 1;
        break;
      case 40:
        v15 = *(_OWORD *)XmlReader::GetValue(this, &v18);
        *(_WORD *)(*a2 + 104) = (unsigned __int8)EventManParser::ParseUInt8(this);
        break;
    }
  }
  if ( !*(_QWORD *)(*a2 + 16) )
    EventManParser::ErrorWithFormatMessage(this, -1073221826, L"name");
  if ( !v4 )
    EventManParser::ErrorWithFormatMessage(this, -1073221826, L"type");
  return a2;
}

```

## disassembly

```asm
0x180034e18  mov     [rsp-8+arg_10], rbx
0x180034e1d  mov     [rsp-8+arg_18], rsi
0x180034e22  push    rbp
0x180034e23  push    rdi
0x180034e24  push    r15
0x180034e26  lea     rbp, [rsp-10h]
0x180034e2b  sub     rsp, 110h
0x180034e32  mov     rax, cs:__security_cookie
0x180034e39  xor     rax, rsp
0x180034e3c  mov     [rbp+20h+var_18], rax
0x180034e40  mov     rbx, rdx
0x180034e43  mov     rdi, rcx
0x180034e46  mov     [rsp+120h+var_C0], rdx
0x180034e4b  mov     [rsp+120h+var_FC], 0
0x180034e53  mov     [rsp+120h+var_100], 0
0x180034e58  lea     rdx, [rsp+120h+var_100]
0x180034e5d  mov     rcx, rbx
0x180034e60  call    ??$make_unique@VCHANNEL_ENTRY@@_N$0A@@std@@YA?AV?$unique_ptr@VCHANNEL_ENTRY@@U?$default_delete@VCHANNEL_ENTRY@@@std@@@0@$$QEA_N@Z; std::make_unique<CHANNEL_ENTRY,bool,0>(bool &&)
0x180034e65  mov     [rsp+120h+var_FC], 1
0x180034e6d  xor     r15b, r15b
0x180034e70  mov     rcx, rdi; this
0x180034e73  call    ?FirstAttribute@XmlReader@@QEAA_NXZ; XmlReader::FirstAttribute(void)
0x180034e78  jmp     loc_18003517C
0x180034e7d  lea     rdx, [rsp+120h+var_B8]
0x180034e82  mov     rcx, rdi; this
0x180034e85  call    ?GetQualifiedName@XmlReader@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; XmlReader::GetQualifiedName(void)
0x180034e8a  movups  xmm0, xmmword ptr [rax]
0x180034e8d  movdqu  [rsp+120h+var_F0], xmm0
0x180034e93  lea     rcx, [rsp+120h+var_F0]
0x180034e98  call    GetAttributeId
0x180034e9d  movzx   ecx, al
0x180034ea0  test    al, al
0x180034ea2  jz      loc_180035152
0x180034ea8  sub     ecx, 3
0x180034eab  jz      loc_18003513D
0x180034eb1  sub     ecx, 5
0x180034eb4  jz      loc_180035113
0x180034eba  sub     ecx, 8
0x180034ebd  jz      loc_180035067
0x180034ec3  sub     ecx, 6
0x180034ec6  jz      loc_180035024
0x180034ecc  sub     ecx, 3
0x180034ecf  jz      loc_180035010
0x180034ed5  sub     ecx, 9
0x180034ed8  jz      loc_180034FF8
0x180034ede  sub     ecx, 5
0x180034ee1  jz      short loc_180034F1E
0x180034ee3  cmp     ecx, 1
0x180034ee6  jnz     loc_180035174
0x180034eec  lea     rdx, [rsp+120h+var_A8]
0x180034ef1  mov     rcx, rdi; this
0x180034ef4  call    ?GetValue@XmlReader@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; XmlReader::GetValue(void)
0x180034ef9  movups  xmm0, xmmword ptr [rax]
0x180034efc  movdqu  [rsp+120h+var_F0], xmm0
0x180034f02  lea     rdx, [rsp+120h+var_F0]
0x180034f07  mov     rcx, rdi; this
0x180034f0a  call    ?ParseUInt8@EventManParser@@AEAAEV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; EventManParser::ParseUInt8(std::wstring_view)
0x180034f0f  movzx   ecx, al
0x180034f12  mov     rax, [rbx]
0x180034f15  mov     [rax+68h], cx
0x180034f19  jmp     loc_180035174
0x180034f1e  lea     rdx, [rsp+120h+var_E0]
0x180034f23  mov     rcx, rdi; this
0x180034f26  call    ?GetValue@XmlReader@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; XmlReader::GetValue(void)
0x180034f2b  mov     rsi, [rsp+120h+var_E0]
0x180034f30  mov     r9, [rsp+120h+var_D8]
0x180034f35  mov     r8, rsi
0x180034f38  mov     r15d, 5
0x180034f3e  mov     edx, r15d
0x180034f41  lea     rcx, aAdmin; "Admin"
0x180034f48  call    ??$_Traits_equal@U?$char_traits@_W@std@@@std@@YA_NQEB_W_K01@Z; std::_Traits_equal<std::char_traits<wchar_t>>(wchar_t const * const,unsigned __int64,wchar_t const * const,unsigned __int64)
0x180034f4d  test    al, al
0x180034f4f  jz      short loc_180034F60
0x180034f51  mov     rax, [rbx]
0x180034f54  mov     dword ptr [rax+60h], 0
0x180034f5b  jmp     loc_180034FF0
0x180034f60  mov     r9, [rsp+120h+var_D8]
0x180034f65  mov     r8, rsi
0x180034f68  mov     edx, 0Bh
0x180034f6d  lea     rcx, aOperational; "Operational"
0x180034f74  call    ??$_Traits_equal@U?$char_traits@_W@std@@@std@@YA_NQEB_W_K01@Z; std::_Traits_equal<std::char_traits<wchar_t>>(wchar_t const * const,unsigned __int64,wchar_t const * const,unsigned __int64)
0x180034f79  test    al, al
0x180034f7b  jz      short loc_180034F89
0x180034f7d  mov     rax, [rbx]
0x180034f80  mov     dword ptr [rax+60h], 1
0x180034f87  jmp     short loc_180034FF0
0x180034f89  mov     r9, [rsp+120h+var_D8]
0x180034f8e  mov     r8, rsi
0x180034f91  mov     edx, 8
0x180034f96  lea     rcx, aAnalytic; "Analytic"
0x180034f9d  call    ??$_Traits_equal@U?$char_traits@_W@std@@@std@@YA_NQEB_W_K01@Z; std::_Traits_equal<std::char_traits<wchar_t>>(wchar_t const * const,unsigned __int64,wchar_t const * const,unsigned __int64)
0x180034fa2  test    al, al
0x180034fa4  jz      short loc_180034FB2
0x180034fa6  mov     rax, [rbx]
0x180034fa9  mov     dword ptr [rax+60h], 2
0x180034fb0  jmp     short loc_180034FF0
0x180034fb2  mov     r9, [rsp+120h+var_D8]
0x180034fb7  mov     r8, rsi
0x180034fba  mov     rdx, r15
0x180034fbd  lea     rcx, aDebug; "Debug"
0x180034fc4  call    ??$_Traits_equal@U?$char_traits@_W@std@@@std@@YA_NQEB_W_K01@Z; std::_Traits_equal<std::char_traits<wchar_t>>(wchar_t const * const,unsigned __int64,wchar_t const * const,unsigned __int64)
0x180034fc9  test    al, al
0x180034fcb  jz      short loc_180034FD9
0x180034fcd  mov     rax, [rbx]
0x180034fd0  mov     dword ptr [rax+60h], 3
0x180034fd7  jmp     short loc_180034FF0
0x180034fd9  mov     r9, rsi
0x180034fdc  lea     r8, aInvalidValueLs_3; "Invalid value \"%ls\", expected Admin, "...
0x180034fe3  mov     edx, 80070057h; int
0x180034fe8  mov     rcx, rdi; this
0x180034feb  call    ?ErrorWithPrintf@EventManParser@@AEAAXJPEBDZZ; EventManParser::ErrorWithPrintf(long,char const *,...)
0x180034ff0  mov     r15b, 1
0x180034ff3  jmp     loc_180035174
0x180034ff8  lea     rdx, [rbp+20h+var_98]
0x180034ffc  mov     rcx, rdi; this
0x180034fff  call    ?GetValue@XmlReader@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; XmlReader::GetValue(void)
0x180035004  mov     rcx, [rbx]
0x180035007  add     rcx, 20h ; ' '
0x18003500b  jmp     loc_180035168
0x180035010  lea     rdx, [rbp+20h+var_88]
0x180035014  mov     rcx, rdi; this
0x180035017  call    ?GetValue@XmlReader@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; XmlReader::GetValue(void)
0x18003501c  mov     rcx, [rbx]
0x18003501f  jmp     loc_180035168
0x180035024  lea     rdx, [rbp+20h+var_78]
0x180035028  mov     rcx, rdi; this
0x18003502b  call    ?GetValue@XmlReader@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; XmlReader::GetValue(void)
0x180035030  movups  xmm0, xmmword ptr [rax]
0x180035033  movdqu  [rsp+120h+var_F0], xmm0
0x180035039  lea     r8, [rsp+120h+var_F0]
0x18003503e  lea     rdx, [rbp+20h+var_38]
0x180035042  mov     rcx, rdi
0x180035045  call    ?ParseStrTableRef@EventManParser@@AEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@3@@Z; EventManParser::ParseStrTableRef(std::wstring_view)
0x18003504a  mov     rcx, [rbx]
0x18003504d  add     rcx, 78h ; 'x'
0x180035051  mov     rdx, rax
0x180035054  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180035059  lea     rcx, [rbp+20h+var_38]
0x18003505d  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180035062  jmp     loc_180035174
0x180035067  lea     rdx, [rsp+120h+var_D0]
0x18003506c  mov     rcx, rdi; this
0x18003506f  call    ?GetValue@XmlReader@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; XmlReader::GetValue(void)
0x180035074  mov     rsi, [rsp+120h+var_D0]
0x180035079  mov     r9, [rsp+120h+var_C8]
0x18003507e  mov     r8, rsi
0x180035081  mov     edx, 0Bh
0x180035086  lea     rcx, aApplication_0; "Application"
0x18003508d  call    ??$_Traits_equal@U?$char_traits@_W@std@@@std@@YA_NQEB_W_K01@Z; std::_Traits_equal<std::char_traits<wchar_t>>(wchar_t const * const,unsigned __int64,wchar_t const * const,unsigned __int64)
0x180035092  test    al, al
0x180035094  jz      short loc_1800350A5
0x180035096  mov     rax, [rbx]
0x180035099  mov     dword ptr [rax+64h], 0
0x1800350a0  jmp     loc_180035174
0x1800350a5  mov     r9, [rsp+120h+var_C8]
0x1800350aa  mov     r8, rsi
0x1800350ad  mov     edx, 6
0x1800350b2  lea     rcx, aSystem_0; "System"
0x1800350b9  call    ??$_Traits_equal@U?$char_traits@_W@std@@@std@@YA_NQEB_W_K01@Z; std::_Traits_equal<std::char_traits<wchar_t>>(wchar_t const * const,unsigned __int64,wchar_t const * const,unsigned __int64)
0x1800350be  test    al, al
0x1800350c0  jz      short loc_1800350D1
0x1800350c2  mov     rax, [rbx]
0x1800350c5  mov     dword ptr [rax+64h], 1
0x1800350cc  jmp     loc_180035174
0x1800350d1  mov     r9, [rsp+120h+var_C8]
0x1800350d6  mov     r8, rsi
0x1800350d9  mov     edx, 6
0x1800350de  lea     rcx, aCustom; "Custom"
0x1800350e5  call    ??$_Traits_equal@U?$char_traits@_W@std@@@std@@YA_NQEB_W_K01@Z; std::_Traits_equal<std::char_traits<wchar_t>>(wchar_t const * const,unsigned __int64,wchar_t const * const,unsigned __int64)
0x1800350ea  test    al, al
0x1800350ec  jz      short loc_1800350FA
0x1800350ee  mov     rax, [rbx]
0x1800350f1  mov     dword ptr [rax+64h], 2
0x1800350f8  jmp     short loc_180035174
0x1800350fa  mov     r9, rsi
0x1800350fd  lea     r8, aInvalidValueLs_9; "Invalid value \"%ls\", expected System "...
0x180035104  mov     edx, 80070057h; int
0x180035109  mov     rcx, rdi; this
0x18003510c  call    ?ErrorWithPrintf@EventManParser@@AEAAXJPEBDZZ; EventManParser::ErrorWithPrintf(long,char const *,...)
0x180035111  jmp     short loc_180035174
0x180035113  lea     rdx, [rbp+20h+var_68]
0x180035117  mov     rcx, rdi; this
0x18003511a  call    ?GetValue@XmlReader@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; XmlReader::GetValue(void)
0x18003511f  movups  xmm0, xmmword ptr [rax]
0x180035122  movdqu  [rsp+120h+var_F0], xmm0
0x180035128  lea     rdx, [rsp+120h+var_F0]
0x18003512d  mov     rcx, rdi; this
0x180035130  call    ?ParseBool@EventManParser@@AEAA_NV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; EventManParser::ParseBool(std::wstring_view)
0x180035135  mov     rcx, [rbx]
0x180035138  mov     [rcx+70h], al
0x18003513b  jmp     short loc_180035174
0x18003513d  lea     rdx, [rbp+20h+var_58]
0x180035141  mov     rcx, rdi; this
0x180035144  call    ?GetValue@XmlReader@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; XmlReader::GetValue(void)
0x180035149  mov     rcx, [rbx]
0x18003514c  add     rcx, 40h ; '@'
0x180035150  jmp     short loc_180035168
0x180035152  lea     rdx, [rbp+20h+var_48]
0x180035156  mov     rcx, rdi; this
0x180035159  call    ?GetValue@XmlReader@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; XmlReader::GetValue(void)
0x18003515e  mov     rcx, [rbx]
0x180035161  add     rcx, 98h
0x180035168  mov     r8, [rax+8]
0x18003516c  mov     rdx, [rax]
0x18003516f  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x180035174  mov     rcx, rdi; this
0x180035177  call    ?NextAttribute@XmlReader@@QEAA_NXZ; XmlReader::NextAttribute(void)
0x18003517c  test    al, al
0x18003517e  jnz     loc_180034E7D
0x180035184  mov     rax, [rbx]
0x180035187  mov     esi, 0C007EF3Eh
0x18003518c  cmp     qword ptr [rax+10h], 0
0x180035191  jnz     short loc_1800351A4
0x180035193  lea     r8, aName_0; "name"
0x18003519a  mov     edx, esi; int
0x18003519c  mov     rcx, rdi; this
0x18003519f  call    ?ErrorWithFormatMessage@EventManParser@@AEAAXJZZ; EventManParser::ErrorWithFormatMessage(long,...)
0x1800351a4  test    r15b, r15b
0x1800351a7  jnz     short loc_1800351BA
0x1800351a9  lea     r8, aType; "type"
0x1800351b0  mov     edx, esi; int
0x1800351b2  mov     rcx, rdi; this
0x1800351b5  call    ?ErrorWithFormatMessage@EventManParser@@AEAAXJZZ; EventManParser::ErrorWithFormatMessage(long,...)
0x1800351ba  mov     rax, rbx
0x1800351bd  mov     rcx, [rbp+20h+var_18]
0x1800351c1  xor     rcx, rsp; StackCookie
0x1800351c4  call    __security_check_cookie
0x1800351c9  lea     r11, [rsp+120h+var_10]
0x1800351d1  mov     rbx, [r11+30h]
0x1800351d5  mov     rsi, [r11+38h]
0x1800351d9  mov     rsp, r11
0x1800351dc  pop     r15
0x1800351de  pop     rdi
0x1800351df  pop     rbp
0x1800351e0  retn
```
