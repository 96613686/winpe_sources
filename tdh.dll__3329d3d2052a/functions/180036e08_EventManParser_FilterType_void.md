# EventManParser::FilterType(void)

- ea: `0x180036e08`
- end: `0x18003705f`
- name: `?FilterType@EventManParser@@AEAA?AV?$unique_ptr@VFILTER_ENTRY@@U?$default_delete@VFILTER_ENTRY@@@std@@@std@@XZ`
- size: `599`
- prototype: `__int64 *__fastcall(XmlReader *this, __int64 *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config`

## callers

- `0x180036d30`

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
- `0x180033da0`
- `0x180036e08`
- `0x180037670`
- `0x180039674`
- `0x18003c754`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 *__fastcall EventManParser::FilterType(XmlReader *this, __int64 *a2)
{
  char *v4; // rax
  char v5; // si
  bool i; // al
  char AttributeId; // al
  _QWORD *Value; // rax
  __int64 v9; // rcx
  __int64 v10; // rax
  __int128 v12; // [rsp+20h] [rbp-79h] BYREF
  int v13; // [rsp+30h] [rbp-69h]
  __int64 *v14; // [rsp+38h] [rbp-61h]
  _BYTE v15[32]; // [rsp+B0h] [rbp+17h] BYREF

  v14 = a2;
  v4 = (char *)operator new(0x98u);
  *(_QWORD *)&v12 = v4;
  *(_OWORD *)v4 = 0;
  *((_QWORD *)v4 + 2) = 0;
  *((_QWORD *)v4 + 3) = 7;
  *(_WORD *)v4 = 0;
  *((_OWORD *)v4 + 2) = 0;
  *((_QWORD *)v4 + 6) = 0;
  *((_QWORD *)v4 + 7) = 7;
  *((_WORD *)v4 + 16) = 0;
  *((_WORD *)v4 + 32) = 0;
  *(_OWORD *)(v4 + 72) = 0;
  *((_QWORD *)v4 + 11) = 0;
  *((_QWORD *)v4 + 12) = 7;
  *((_WORD *)v4 + 36) = 0;
  *(_OWORD *)(v4 + 104) = 0;
  *((_QWORD *)v4 + 15) = 0;
  *((_QWORD *)v4 + 16) = 7;
  *((_WORD *)v4 + 52) = 0;
  *((_QWORD *)v4 + 17) = 0;
  *((_QWORD *)v4 + 18) = 0;
  *a2 = (__int64)v4;
  v13 = 3;
  v5 = 0;
  for ( i = XmlReader::FirstAttribute(this); i; i = XmlReader::NextAttribute(this) )
  {
    v12 = *(_OWORD *)XmlReader::GetQualifiedName(this);
    AttributeId = GetAttributeId(&v12);
    switch ( AttributeId )
    {
      case 22:
        v12 = *(_OWORD *)XmlReader::GetValue(this);
        v10 = EventManParser::ParseStrTableRef(this, v15, &v12);
        std::wstring::operator=(*a2 + 104, v10);
        std::wstring::_Tidy_deallocate(v15);
        break;
      case 25:
        Value = (_QWORD *)XmlReader::GetValue(this);
        v9 = *a2;
        goto LABEL_13;
      case 34:
        Value = (_QWORD *)XmlReader::GetValue(this);
        v9 = *a2 + 32;
        goto LABEL_13;
      case 38:
        Value = (_QWORD *)XmlReader::GetValue(this);
        v9 = *a2 + 72;
LABEL_13:
        std::wstring::_Assign<wchar_t>(v9, *Value, Value[1]);
        continue;
      case 40:
        v12 = *(_OWORD *)XmlReader::GetValue(this);
        *(_BYTE *)(*a2 + 64) = EventManParser::ParseUInt8(this);
        v5 = 1;
        break;
      case 41:
        v12 = *(_OWORD *)XmlReader::GetValue(this);
        *(_BYTE *)(*a2 + 65) = EventManParser::ParseUInt8(this);
        break;
    }
  }
  if ( !*(_QWORD *)(*a2 + 16) )
    EventManParser::ErrorWithFormatMessage(this, -1073221826, L"name");
  if ( !v5 )
    EventManParser::ErrorWithFormatMessage(this, -1073221826, L"value");
  return a2;
}

```

## disassembly

```asm
0x180036e08  mov     [rsp-8+arg_10], rbx
0x180036e0d  push    rbp
0x180036e0e  push    rsi
0x180036e0f  push    rdi
0x180036e10  lea     rbp, [rsp-47h]
0x180036e15  sub     rsp, 0E0h
0x180036e1c  mov     rax, cs:__security_cookie
0x180036e23  xor     rax, rsp
0x180036e26  mov     [rbp+57h+var_20], rax
0x180036e2a  mov     rdi, rdx
0x180036e2d  mov     rbx, rcx
0x180036e30  mov     [rbp+57h+var_B8], rdx
0x180036e34  mov     [rbp+57h+var_C0], 0
0x180036e3b  mov     ecx, 98h; Size
0x180036e40  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180036e45  mov     rcx, rax
0x180036e48  mov     qword ptr [rbp+57h+var_D0], rax
0x180036e4c  xorps   xmm0, xmm0
0x180036e4f  movups  xmmword ptr [rax], xmm0
0x180036e52  mov     qword ptr [rax+10h], 0
0x180036e5a  mov     edx, 7
0x180036e5f  mov     [rax+18h], rdx
0x180036e63  xor     eax, eax
0x180036e65  mov     [rcx], ax
0x180036e68  movups  xmmword ptr [rcx+20h], xmm0
0x180036e6c  mov     [rcx+30h], rax
0x180036e70  mov     [rcx+38h], rdx
0x180036e74  mov     [rcx+20h], ax
0x180036e78  mov     [rcx+40h], ax
0x180036e7c  movups  xmmword ptr [rcx+48h], xmm0
0x180036e80  mov     [rcx+58h], rax
0x180036e84  mov     [rcx+60h], rdx
0x180036e88  mov     [rcx+48h], ax
0x180036e8c  movups  xmmword ptr [rcx+68h], xmm0
0x180036e90  mov     [rcx+78h], rax
0x180036e94  mov     [rcx+80h], rdx
0x180036e9b  mov     [rcx+68h], ax
0x180036e9f  mov     [rcx+88h], rax
0x180036ea6  mov     [rcx+90h], rax
0x180036ead  mov     [rdi], rcx
0x180036eb0  mov     [rbp+57h+var_C0], 3
0x180036eb7  xor     sil, sil
0x180036eba  mov     rcx, rbx; this
0x180036ebd  call    ?FirstAttribute@XmlReader@@QEAA_NXZ; XmlReader::FirstAttribute(void)
0x180036ec2  jmp     loc_180036FFD
0x180036ec7  lea     rdx, [rbp+57h+var_B0]
0x180036ecb  mov     rcx, rbx; this
0x180036ece  call    ?GetQualifiedName@XmlReader@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; XmlReader::GetQualifiedName(void)
0x180036ed3  movups  xmm0, xmmword ptr [rax]
0x180036ed6  movdqu  [rbp+57h+var_D0], xmm0
0x180036edb  lea     rcx, [rbp+57h+var_D0]
0x180036edf  call    GetAttributeId
0x180036ee4  movzx   ecx, al
0x180036ee7  sub     ecx, 16h
0x180036eea  jz      loc_180036FB9
0x180036ef0  sub     ecx, 3
0x180036ef3  jz      loc_180036F9C
0x180036ef9  sub     ecx, 9
0x180036efc  jz      loc_180036F87
0x180036f02  sub     ecx, 4
0x180036f05  jz      short loc_180036F72
0x180036f07  sub     ecx, 2
0x180036f0a  jz      short loc_180036F42
0x180036f0c  cmp     ecx, 1
0x180036f0f  jnz     loc_180036FF5
0x180036f15  lea     rdx, [rbp+57h+var_A0]
0x180036f19  mov     rcx, rbx; this
0x180036f1c  call    ?GetValue@XmlReader@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; XmlReader::GetValue(void)
0x180036f21  movups  xmm0, xmmword ptr [rax]
0x180036f24  movdqu  [rbp+57h+var_D0], xmm0
0x180036f29  lea     rdx, [rbp+57h+var_D0]
0x180036f2d  mov     rcx, rbx; this
0x180036f30  call    ?ParseUInt8@EventManParser@@AEAAEV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; EventManParser::ParseUInt8(std::wstring_view)
0x180036f35  mov     cl, al
0x180036f37  mov     rax, [rdi]
0x180036f3a  mov     [rax+41h], cl
0x180036f3d  jmp     loc_180036FF5
0x180036f42  lea     rdx, [rbp+57h+var_90]
0x180036f46  mov     rcx, rbx; this
0x180036f49  call    ?GetValue@XmlReader@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; XmlReader::GetValue(void)
0x180036f4e  movups  xmm0, xmmword ptr [rax]
0x180036f51  movdqu  [rbp+57h+var_D0], xmm0
0x180036f56  lea     rdx, [rbp+57h+var_D0]
0x180036f5a  mov     rcx, rbx; this
0x180036f5d  call    ?ParseUInt8@EventManParser@@AEAAEV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; EventManParser::ParseUInt8(std::wstring_view)
0x180036f62  mov     cl, al
0x180036f64  mov     rax, [rdi]
0x180036f67  mov     [rax+40h], cl
0x180036f6a  mov     sil, 1
0x180036f6d  jmp     loc_180036FF5
0x180036f72  lea     rdx, [rbp+57h+var_80]
0x180036f76  mov     rcx, rbx; this
0x180036f79  call    ?GetValue@XmlReader@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; XmlReader::GetValue(void)
0x180036f7e  mov     rcx, [rdi]
0x180036f81  add     rcx, 48h ; 'H'
0x180036f85  jmp     short loc_180036FAB
0x180036f87  lea     rdx, [rbp+57h+var_70]
0x180036f8b  mov     rcx, rbx; this
0x180036f8e  call    ?GetValue@XmlReader@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; XmlReader::GetValue(void)
0x180036f93  mov     rcx, [rdi]
0x180036f96  add     rcx, 20h ; ' '
0x180036f9a  jmp     short loc_180036FAB
0x180036f9c  lea     rdx, [rbp+57h+var_60]
0x180036fa0  mov     rcx, rbx; this
0x180036fa3  call    ?GetValue@XmlReader@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; XmlReader::GetValue(void)
0x180036fa8  mov     rcx, [rdi]
0x180036fab  mov     r8, [rax+8]
0x180036faf  mov     rdx, [rax]
0x180036fb2  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x180036fb7  jmp     short loc_180036FF5
0x180036fb9  lea     rdx, [rbp+57h+var_50]
0x180036fbd  mov     rcx, rbx; this
0x180036fc0  call    ?GetValue@XmlReader@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; XmlReader::GetValue(void)
0x180036fc5  movups  xmm0, xmmword ptr [rax]
0x180036fc8  movdqu  [rbp+57h+var_D0], xmm0
0x180036fcd  lea     r8, [rbp+57h+var_D0]
0x180036fd1  lea     rdx, [rbp+57h+var_40]
0x180036fd5  mov     rcx, rbx
0x180036fd8  call    ?ParseStrTableRef@EventManParser@@AEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@3@@Z; EventManParser::ParseStrTableRef(std::wstring_view)
0x180036fdd  mov     rcx, [rdi]
0x180036fe0  add     rcx, 68h ; 'h'
0x180036fe4  mov     rdx, rax
0x180036fe7  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180036fec  lea     rcx, [rbp+57h+var_40]
0x180036ff0  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180036ff5  mov     rcx, rbx; this
0x180036ff8  call    ?NextAttribute@XmlReader@@QEAA_NXZ; XmlReader::NextAttribute(void)
0x180036ffd  test    al, al
0x180036fff  jnz     loc_180036EC7
0x180037005  mov     rax, [rdi]
0x180037008  cmp     qword ptr [rax+10h], 0
0x18003700d  jnz     short loc_180037023
0x18003700f  lea     r8, aName_0; "name"
0x180037016  mov     edx, 0C007EF3Eh; int
0x18003701b  mov     rcx, rbx; this
0x18003701e  call    ?ErrorWithFormatMessage@EventManParser@@AEAAXJZZ; EventManParser::ErrorWithFormatMessage(long,...)
0x180037023  test    sil, sil
0x180037026  jnz     short loc_18003703C
0x180037028  lea     r8, aValue; "value"
0x18003702f  mov     edx, 0C007EF3Eh; int
0x180037034  mov     rcx, rbx; this
0x180037037  call    ?ErrorWithFormatMessage@EventManParser@@AEAAXJZZ; EventManParser::ErrorWithFormatMessage(long,...)
0x18003703c  mov     rax, rdi
0x18003703f  mov     rcx, [rbp+57h+var_20]
0x180037043  xor     rcx, rsp; StackCookie
0x180037046  call    __security_check_cookie
0x18003704b  mov     rbx, [rsp+0F0h+arg_10]
0x180037053  add     rsp, 0E0h
0x18003705a  pop     rdi
0x18003705b  pop     rsi
0x18003705c  pop     rbp
0x18003705d  retn
```
