# EventManParser::OpcodeType(TASK_ENTRY *)

- ea: `0x180038e20`
- end: `0x180038ff9`
- name: `?OpcodeType@EventManParser@@AEAA?AV?$unique_ptr@VOPCODE_ENTRY@@U?$default_delete@VOPCODE_ENTRY@@@std@@@std@@PEAVTASK_ENTRY@@@Z`
- size: `473`
- prototype: `__int64 __fastcall(XmlReader *this)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, service_task`

## callers

- `0x180038d38`

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
- `0x180032710`
- `0x180033da0`
- `0x180037670`
- `0x180038e20`
- `0x180039674`
- `0x18003c754`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 *__fastcall EventManParser::OpcodeType(XmlReader *this, __int64 *a2, struct TASK_ENTRY *a3)
{
  char v6; // bl
  bool i; // al
  char AttributeId; // al
  _QWORD *Value; // rax
  __int64 v10; // rcx
  __int64 v11; // rax
  __int128 v13; // [rsp+20h] [rbp-69h] BYREF
  int v14; // [rsp+30h] [rbp-59h]
  __int64 *v15; // [rsp+38h] [rbp-51h]
  __int64 v16; // [rsp+40h] [rbp-49h] BYREF
  __int64 v17; // [rsp+50h] [rbp-39h] BYREF
  __int64 v18; // [rsp+60h] [rbp-29h] BYREF
  __int64 v19; // [rsp+70h] [rbp-19h] BYREF
  __int64 v20; // [rsp+80h] [rbp-9h] BYREF
  __int64 v21; // [rsp+90h] [rbp+7h] BYREF
  _BYTE v22[32]; // [rsp+A0h] [rbp+17h] BYREF

  v15 = a2;
  *(_QWORD *)&v13 = operator new(0x88u);
  *a2 = (__int64)OPCODE_ENTRY::OPCODE_ENTRY((OPCODE_ENTRY *)v13, a3);
  v14 = 3;
  v6 = 0;
  for ( i = XmlReader::FirstAttribute(this); i; i = XmlReader::NextAttribute(this) )
  {
    v13 = *(_OWORD *)XmlReader::GetQualifiedName(this, &v16);
    AttributeId = GetAttributeId(&v13);
    switch ( AttributeId )
    {
      case 22:
        v13 = *(_OWORD *)XmlReader::GetValue(this, &v21);
        v11 = EventManParser::ParseStrTableRef(this, v22, &v13);
        std::wstring::operator=(*a2 + 72, v11);
        std::wstring::_Tidy_deallocate(v22);
        break;
      case 24:
        v13 = *(_OWORD *)XmlReader::GetValue(this, &v20);
        *(_BYTE *)(*a2 + 104) = EventManParser::ParseUInt8(this);
        break;
      case 25:
        Value = XmlReader::GetValue(this, &v19);
        v10 = *a2;
        goto LABEL_10;
      case 34:
        Value = XmlReader::GetValue(this, &v18);
        v10 = *a2 + 40;
LABEL_10:
        std::wstring::_Assign<wchar_t>(v10, *Value, Value[1]);
        continue;
      case 40:
        v13 = *(_OWORD *)XmlReader::GetValue(this, &v17);
        *(_BYTE *)(*a2 + 32) = EventManParser::ParseUInt8(this);
        v6 = 1;
        break;
    }
  }
  if ( !*(_QWORD *)(*a2 + 16) )
    EventManParser::ErrorWithFormatMessage(this, -1073221826, L"name");
  if ( !v6 )
    EventManParser::ErrorWithFormatMessage(this, -1073221826, L"value");
  return a2;
}

```

## disassembly

```asm
0x180038e20  mov     [rsp-8+arg_10], rbx
0x180038e25  push    rbp
0x180038e26  push    rsi
0x180038e27  push    rdi
0x180038e28  lea     rbp, [rsp-47h]
0x180038e2d  sub     rsp, 0D0h
0x180038e34  mov     rax, cs:__security_cookie
0x180038e3b  xor     rax, rsp
0x180038e3e  mov     [rbp+57h+var_20], rax
0x180038e42  mov     rbx, r8
0x180038e45  mov     rsi, rdx
0x180038e48  mov     rdi, rcx
0x180038e4b  mov     [rbp+57h+var_A8], rdx
0x180038e4f  mov     [rbp+57h+var_B0], 0
0x180038e56  mov     ecx, 88h; Size
0x180038e5b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180038e60  mov     qword ptr [rbp+57h+var_C0], rax
0x180038e64  mov     rdx, rbx; struct TASK_ENTRY *
0x180038e67  mov     rcx, rax; this
0x180038e6a  call    ??0OPCODE_ENTRY@@QEAA@PEAVTASK_ENTRY@@@Z; OPCODE_ENTRY::OPCODE_ENTRY(TASK_ENTRY *)
0x180038e6f  mov     [rsi], rax
0x180038e72  mov     [rbp+57h+var_B0], 3
0x180038e79  xor     bl, bl
0x180038e7b  mov     rcx, rdi; this
0x180038e7e  call    ?FirstAttribute@XmlReader@@QEAA_NXZ; XmlReader::FirstAttribute(void)
0x180038e83  jmp     loc_180038F98
0x180038e88  lea     rdx, [rbp+57h+var_A0]
0x180038e8c  mov     rcx, rdi; this
0x180038e8f  call    ?GetQualifiedName@XmlReader@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; XmlReader::GetQualifiedName(void)
0x180038e94  movups  xmm0, xmmword ptr [rax]
0x180038e97  movdqu  [rbp+57h+var_C0], xmm0
0x180038e9c  lea     rcx, [rbp+57h+var_C0]
0x180038ea0  call    GetAttributeId
0x180038ea5  movzx   ecx, al
0x180038ea8  sub     ecx, 16h
0x180038eab  jz      loc_180038F54
0x180038eb1  sub     ecx, 2
0x180038eb4  jz      short loc_180038F2A
0x180038eb6  sub     ecx, 1
0x180038eb9  jz      short loc_180038F0D
0x180038ebb  sub     ecx, 9
0x180038ebe  jz      short loc_180038EF8
0x180038ec0  cmp     ecx, 6
0x180038ec3  jnz     loc_180038F90
0x180038ec9  lea     rdx, [rbp+57h+var_90]
0x180038ecd  mov     rcx, rdi; this
0x180038ed0  call    ?GetValue@XmlReader@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; XmlReader::GetValue(void)
0x180038ed5  movups  xmm0, xmmword ptr [rax]
0x180038ed8  movdqu  [rbp+57h+var_C0], xmm0
0x180038edd  lea     rdx, [rbp+57h+var_C0]
0x180038ee1  mov     rcx, rdi; this
0x180038ee4  call    ?ParseUInt8@EventManParser@@AEAAEV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; EventManParser::ParseUInt8(std::wstring_view)
0x180038ee9  mov     cl, al
0x180038eeb  mov     rax, [rsi]
0x180038eee  mov     [rax+20h], cl
0x180038ef1  mov     bl, 1
0x180038ef3  jmp     loc_180038F90
0x180038ef8  lea     rdx, [rbp+57h+var_80]
0x180038efc  mov     rcx, rdi; this
0x180038eff  call    ?GetValue@XmlReader@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; XmlReader::GetValue(void)
0x180038f04  mov     rcx, [rsi]
0x180038f07  add     rcx, 28h ; '('
0x180038f0b  jmp     short loc_180038F1C
0x180038f0d  lea     rdx, [rbp+57h+var_70]
0x180038f11  mov     rcx, rdi; this
0x180038f14  call    ?GetValue@XmlReader@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; XmlReader::GetValue(void)
0x180038f19  mov     rcx, [rsi]
0x180038f1c  mov     rdx, [rax]
0x180038f1f  mov     r8, [rax+8]
0x180038f23  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x180038f28  jmp     short loc_180038F90
0x180038f2a  lea     rdx, [rbp+57h+var_60]
0x180038f2e  mov     rcx, rdi; this
0x180038f31  call    ?GetValue@XmlReader@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; XmlReader::GetValue(void)
0x180038f36  movups  xmm0, xmmword ptr [rax]
0x180038f39  movdqu  [rbp+57h+var_C0], xmm0
0x180038f3e  lea     rdx, [rbp+57h+var_C0]
0x180038f42  mov     rcx, rdi; this
0x180038f45  call    ?ParseUInt8@EventManParser@@AEAAEV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; EventManParser::ParseUInt8(std::wstring_view)
0x180038f4a  mov     cl, al
0x180038f4c  mov     rax, [rsi]
0x180038f4f  mov     [rax+68h], cl
0x180038f52  jmp     short loc_180038F90
0x180038f54  lea     rdx, [rbp+57h+var_50]
0x180038f58  mov     rcx, rdi; this
0x180038f5b  call    ?GetValue@XmlReader@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; XmlReader::GetValue(void)
0x180038f60  movups  xmm0, xmmword ptr [rax]
0x180038f63  movdqu  [rbp+57h+var_C0], xmm0
0x180038f68  lea     r8, [rbp+57h+var_C0]
0x180038f6c  lea     rdx, [rbp+57h+var_40]
0x180038f70  mov     rcx, rdi
0x180038f73  call    ?ParseStrTableRef@EventManParser@@AEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@3@@Z; EventManParser::ParseStrTableRef(std::wstring_view)
0x180038f78  mov     rcx, [rsi]
0x180038f7b  add     rcx, 48h ; 'H'
0x180038f7f  mov     rdx, rax
0x180038f82  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180038f87  lea     rcx, [rbp+57h+var_40]
0x180038f8b  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180038f90  mov     rcx, rdi; this
0x180038f93  call    ?NextAttribute@XmlReader@@QEAA_NXZ; XmlReader::NextAttribute(void)
0x180038f98  test    al, al
0x180038f9a  jnz     loc_180038E88
0x180038fa0  mov     rax, [rsi]
0x180038fa3  cmp     qword ptr [rax+10h], 0
0x180038fa8  jnz     short loc_180038FBE
0x180038faa  lea     r8, aName_0; "name"
0x180038fb1  mov     edx, 0C007EF3Eh; int
0x180038fb6  mov     rcx, rdi; this
0x180038fb9  call    ?ErrorWithFormatMessage@EventManParser@@AEAAXJZZ; EventManParser::ErrorWithFormatMessage(long,...)
0x180038fbe  test    bl, bl
0x180038fc0  jnz     short loc_180038FD6
0x180038fc2  lea     r8, aValue; "value"
0x180038fc9  mov     edx, 0C007EF3Eh; int
0x180038fce  mov     rcx, rdi; this
0x180038fd1  call    ?ErrorWithFormatMessage@EventManParser@@AEAAXJZZ; EventManParser::ErrorWithFormatMessage(long,...)
0x180038fd6  mov     rax, rsi
0x180038fd9  mov     rcx, [rbp+57h+var_20]
0x180038fdd  xor     rcx, rsp; StackCookie
0x180038fe0  call    __security_check_cookie
0x180038fe5  mov     rbx, [rsp+0E0h+arg_10]
0x180038fed  add     rsp, 0D0h
0x180038ff4  pop     rdi
0x180038ff5  pop     rsi
0x180038ff6  pop     rbp
0x180038ff7  retn
```
