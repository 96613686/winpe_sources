# EventManParser::TaskType(std::vector<std::unique_ptr<OPCODE_ENTRY,std::default_delete<OPCODE_ENTRY>>,std::allocator<std::unique_ptr<OPCODE_ENTRY,std::default_delete<OPCODE_ENTRY>>>> &)

- ea: `0x18003b7e0`
- end: `0x18003ba1b`
- name: `?TaskType@EventManParser@@AEAA?AV?$unique_ptr@VTASK_ENTRY@@U?$default_delete@VTASK_ENTRY@@@std@@@std@@AEAV?$vector@V?$unique_ptr@VOPCODE_ENTRY@@U?$default_delete@VOPCODE_ENTRY@@@std@@@std@@V?$allocator@V?$unique_ptr@VOPCODE_ENTRY@@U?$default_delete@VOPCODE_ENTRY@@@std@@@std@@@2@@3@@Z`
- size: `571`
- prototype: `__int64 __fastcall(XmlReader *this)`
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, service_task`

## callers

- `0x18003b6f8`

## callees

- `0x18001cb90`
- `0x18001df64`
- `0x18001e0cc`
- `0x18001e284`
- `0x18001e4d8`
- `0x18001e550`
- `0x18001e8f0`
- `0x18001e930`
- `0x1800207c0`
- `0x1800314d0`
- `0x180033da0`
- `0x180035858`
- `0x180037670`
- `0x180037e80`
- `0x180038cc4`
- `0x180038d38`
- `0x180039494`
- `0x1800395a4`
- `0x18003b7e0`
- `0x18003c754`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 *__fastcall EventManParser::TaskType(XmlReader *this, __int64 *a2)
{
  char v4; // si
  bool i; // al
  char AttributeId; // al
  _QWORD *Value; // rax
  __int64 v8; // rcx
  __int64 v9; // rax
  char j; // al
  __int128 v12; // [rsp+20h] [rbp-89h] BYREF
  int v13; // [rsp+30h] [rbp-79h]
  __int128 v14; // [rsp+38h] [rbp-71h] BYREF
  __int128 v15; // [rsp+50h] [rbp-59h] BYREF
  __int128 v16; // [rsp+60h] [rbp-49h] BYREF
  __int64 *v17; // [rsp+70h] [rbp-39h]
  __int64 v18; // [rsp+78h] [rbp-31h] BYREF
  __int64 v19; // [rsp+88h] [rbp-21h] BYREF
  __int64 v20; // [rsp+98h] [rbp-11h] BYREF
  _BYTE v21[32]; // [rsp+B8h] [rbp+Fh] BYREF

  v17 = a2;
  std::make_unique<TASK_ENTRY,,0>(a2);
  v13 = 1;
  v4 = 0;
  for ( i = XmlReader::FirstAttribute(this); i; i = XmlReader::NextAttribute(this) )
  {
    v12 = *(_OWORD *)XmlReader::GetQualifiedName(this, &v16);
    AttributeId = GetAttributeId(&v12);
    switch ( AttributeId )
    {
      case 9:
        v12 = *(_OWORD *)XmlReader::GetValue(this, &v20);
        *(_OWORD *)(*a2 + 104) = *(_OWORD *)EventManParser::ParseGuid(this);
        break;
      case 22:
        v12 = *(_OWORD *)XmlReader::GetValue(this, &v19);
        v9 = EventManParser::ParseStrTableRef(this, v21, &v12);
        std::wstring::operator=(*a2 + 72, v9);
        std::wstring::_Tidy_deallocate(v21);
        break;
      case 25:
        Value = XmlReader::GetValue(this, &v18);
        v8 = *a2;
        goto LABEL_10;
      case 34:
        Value = XmlReader::GetValue(this, &v14);
        v8 = *a2 + 40;
LABEL_10:
        std::wstring::_Assign<wchar_t>(v8, *Value);
        continue;
      case 40:
        v12 = *(_OWORD *)XmlReader::GetValue(this, &v15);
        *(_WORD *)(*a2 + 32) = EventManParser::ParseUInt16(this);
        v4 = 1;
        break;
    }
  }
  if ( !*(_QWORD *)(*a2 + 16) )
    EventManParser::ErrorWithFormatMessage(this, 3221745470LL, L"name");
  if ( !v4 )
    EventManParser::ErrorWithFormatMessage(this, 3221745470LL, L"value");
  for ( j = XmlReader::FirstChildElement(this); j; j = XmlReader::NextChildElement((xp::XmlReader **)this) )
  {
    XmlReader::GetLocalName(this, &v14);
    v15 = v14;
    v16 = *(_OWORD *)&off_18004F7F0;
    *(_QWORD *)&v12 = L"opcodes";
    *((_QWORD *)&v12 + 1) = 7;
    if ( EventManParser::ElementMatches(this, &v12, &v16, &v15) )
      EventManParser::OpcodeListType(this);
  }
  return a2;
}

```

## disassembly

```asm
0x18003b7e0  push    rbp
0x18003b7e2  push    rbx
0x18003b7e3  push    rsi
0x18003b7e4  push    rdi
0x18003b7e5  push    r14
0x18003b7e7  lea     rbp, [rsp-37h]
0x18003b7ec  sub     rsp, 0E0h
0x18003b7f3  mov     rax, cs:__security_cookie
0x18003b7fa  xor     rax, rsp
0x18003b7fd  mov     [rbp+57h+var_28], rax
0x18003b801  mov     r14, r8
0x18003b804  mov     rdi, rdx
0x18003b807  mov     rbx, rcx
0x18003b80a  mov     [rbp+57h+var_90], rdx
0x18003b80e  mov     [rbp+57h+var_D0], 0
0x18003b815  mov     rcx, rdx
0x18003b818  call    ??$make_unique@VTASK_ENTRY@@$$V$0A@@std@@YA?AV?$unique_ptr@VTASK_ENTRY@@U?$default_delete@VTASK_ENTRY@@@std@@@0@XZ; std::make_unique<TASK_ENTRY,,0>(void)
0x18003b81d  mov     [rbp+57h+var_D0], 1
0x18003b824  xor     sil, sil
0x18003b827  mov     rcx, rbx; this
0x18003b82a  call    ?FirstAttribute@XmlReader@@QEAA_NXZ; XmlReader::FirstAttribute(void)
0x18003b82f  jmp     loc_18003B94B
0x18003b834  lea     rdx, [rbp+57h+var_A0]
0x18003b838  mov     rcx, rbx; this
0x18003b83b  call    ?GetQualifiedName@XmlReader@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; XmlReader::GetQualifiedName(void)
0x18003b840  movups  xmm0, xmmword ptr [rax]
0x18003b843  movdqu  [rsp+100h+var_E0], xmm0
0x18003b849  lea     rcx, [rsp+100h+var_E0]
0x18003b84e  call    GetAttributeId
0x18003b853  cmp     al, 9
0x18003b855  jz      loc_18003B912
0x18003b85b  cmp     al, 16h
0x18003b85d  jz      short loc_18003B8D2
0x18003b85f  cmp     al, 19h
0x18003b861  jz      short loc_18003B8B5
0x18003b863  cmp     al, 22h ; '"'
0x18003b865  jz      short loc_18003B8A0
0x18003b867  cmp     al, 28h ; '('
0x18003b869  jnz     loc_18003B943
0x18003b86f  lea     rdx, [rbp+57h+var_B0]
0x18003b873  mov     rcx, rbx; this
0x18003b876  call    ?GetValue@XmlReader@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; XmlReader::GetValue(void)
0x18003b87b  movups  xmm0, xmmword ptr [rax]
0x18003b87e  movdqu  [rsp+100h+var_E0], xmm0
0x18003b884  lea     rdx, [rsp+100h+var_E0]
0x18003b889  mov     rcx, rbx; this
0x18003b88c  call    ?ParseUInt16@EventManParser@@AEAAGV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; EventManParser::ParseUInt16(std::wstring_view)
0x18003b891  mov     rcx, [rdi]
0x18003b894  mov     [rcx+20h], ax
0x18003b898  mov     sil, 1
0x18003b89b  jmp     loc_18003B943
0x18003b8a0  lea     rdx, [rbp+57h+var_C8]
0x18003b8a4  mov     rcx, rbx; this
0x18003b8a7  call    ?GetValue@XmlReader@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; XmlReader::GetValue(void)
0x18003b8ac  mov     rcx, [rdi]
0x18003b8af  add     rcx, 28h ; '('
0x18003b8b3  jmp     short loc_18003B8C4
0x18003b8b5  lea     rdx, [rbp+57h+var_88]
0x18003b8b9  mov     rcx, rbx; this
0x18003b8bc  call    ?GetValue@XmlReader@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; XmlReader::GetValue(void)
0x18003b8c1  mov     rcx, [rdi]
0x18003b8c4  mov     rdx, [rax]
0x18003b8c7  mov     r8, [rax+8]
0x18003b8cb  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x18003b8d0  jmp     short loc_18003B943
0x18003b8d2  lea     rdx, [rbp+57h+var_78]
0x18003b8d6  mov     rcx, rbx; this
0x18003b8d9  call    ?GetValue@XmlReader@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; XmlReader::GetValue(void)
0x18003b8de  movups  xmm0, xmmword ptr [rax]
0x18003b8e1  movdqu  [rsp+100h+var_E0], xmm0
0x18003b8e7  lea     r8, [rsp+100h+var_E0]
0x18003b8ec  lea     rdx, [rbp+57h+var_48]
0x18003b8f0  mov     rcx, rbx
0x18003b8f3  call    ?ParseStrTableRef@EventManParser@@AEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@3@@Z; EventManParser::ParseStrTableRef(std::wstring_view)
0x18003b8f8  mov     rcx, [rdi]
0x18003b8fb  add     rcx, 48h ; 'H'
0x18003b8ff  mov     rdx, rax
0x18003b902  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18003b907  lea     rcx, [rbp+57h+var_48]
0x18003b90b  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003b910  jmp     short loc_18003B943
0x18003b912  lea     rdx, [rbp+57h+var_68]
0x18003b916  mov     rcx, rbx; this
0x18003b919  call    ?GetValue@XmlReader@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; XmlReader::GetValue(void)
0x18003b91e  movups  xmm0, xmmword ptr [rax]
0x18003b921  movdqu  [rsp+100h+var_E0], xmm0
0x18003b927  lea     r8, [rsp+100h+var_E0]
0x18003b92c  lea     rdx, [rbp+57h+var_58]
0x18003b930  mov     rcx, rbx; this
0x18003b933  call    ?ParseGuid@EventManParser@@AEAA?AU_GUID@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; EventManParser::ParseGuid(std::wstring_view)
0x18003b938  movups  xmm0, xmmword ptr [rax]
0x18003b93b  mov     rax, [rdi]
0x18003b93e  movdqu  xmmword ptr [rax+68h], xmm0
0x18003b943  mov     rcx, rbx; this
0x18003b946  call    ?NextAttribute@XmlReader@@QEAA_NXZ; XmlReader::NextAttribute(void)
0x18003b94b  test    al, al
0x18003b94d  jnz     loc_18003B834
0x18003b953  mov     rax, [rdi]
0x18003b956  cmp     qword ptr [rax+10h], 0
0x18003b95b  jnz     short loc_18003B971
0x18003b95d  lea     r8, aName_0; "name"
0x18003b964  mov     edx, 0C007EF3Eh; int
0x18003b969  mov     rcx, rbx; this
0x18003b96c  call    ?ErrorWithFormatMessage@EventManParser@@AEAAXJZZ; EventManParser::ErrorWithFormatMessage(long,...)
0x18003b971  test    sil, sil
0x18003b974  jnz     short loc_18003B98A
0x18003b976  lea     r8, aValue; "value"
0x18003b97d  mov     edx, 0C007EF3Eh; int
0x18003b982  mov     rcx, rbx; this
0x18003b985  call    ?ErrorWithFormatMessage@EventManParser@@AEAAXJZZ; EventManParser::ErrorWithFormatMessage(long,...)
0x18003b98a  mov     rcx, rbx; this
0x18003b98d  call    ?FirstChildElement@XmlReader@@QEAA_NXZ; XmlReader::FirstChildElement(void)
0x18003b992  jmp     short loc_18003B9F9
0x18003b994  lea     rdx, [rbp+57h+var_C8]
0x18003b998  mov     rcx, rbx; this
0x18003b99b  call    ?GetLocalName@XmlReader@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; XmlReader::GetLocalName(void)
0x18003b9a0  movups  xmm0, [rbp+57h+var_C8]
0x18003b9a4  movups  xmm1, xmmword ptr cs:off_18004F7F0; "http://schemas.microsoft.com/win/2004/0"...
0x18003b9ab  movdqu  [rbp+57h+var_B0], xmm0
0x18003b9b0  movdqu  [rbp+57h+var_A0], xmm1
0x18003b9b5  lea     rax, aOpcodes; "opcodes"
0x18003b9bc  mov     qword ptr [rsp+100h+var_E0], rax
0x18003b9c1  mov     qword ptr [rsp+100h+var_E0+8], 7
0x18003b9ca  lea     r9, [rbp+57h+var_B0]
0x18003b9ce  lea     r8, [rbp+57h+var_A0]
0x18003b9d2  lea     rdx, [rsp+100h+var_E0]
0x18003b9d7  mov     rcx, rbx; this
0x18003b9da  call    ?ElementMatches@EventManParser@@AEBA_NV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@00@Z; EventManParser::ElementMatches(std::wstring_view,std::wstring_view,std::wstring_view)
0x18003b9df  test    al, al
0x18003b9e1  jz      short loc_18003B9F1
0x18003b9e3  mov     r8, [rdi]
0x18003b9e6  mov     rdx, r14
0x18003b9e9  mov     rcx, rbx; this
0x18003b9ec  call    ?OpcodeListType@EventManParser@@AEAAXAEAV?$vector@V?$unique_ptr@VOPCODE_ENTRY@@U?$default_delete@VOPCODE_ENTRY@@@std@@@std@@V?$allocator@V?$unique_ptr@VOPCODE_ENTRY@@U?$default_delete@VOPCODE_ENTRY@@@std@@@std@@@2@@std@@PEAVTASK_ENTRY@@@Z; EventManParser::OpcodeListType(std::vector<std::unique_ptr<OPCODE_ENTRY>> &,TASK_ENTRY *)
0x18003b9f1  mov     rcx, rbx; this
0x18003b9f4  call    ?NextChildElement@XmlReader@@QEAA_NXZ; XmlReader::NextChildElement(void)
0x18003b9f9  test    al, al
0x18003b9fb  jnz     short loc_18003B994
0x18003b9fd  mov     rax, rdi
0x18003ba00  mov     rcx, [rbp+57h+var_28]
0x18003ba04  xor     rcx, rsp; StackCookie
0x18003ba07  call    __security_check_cookie
0x18003ba0c  add     rsp, 0E0h
0x18003ba13  pop     r14
0x18003ba15  pop     rdi
0x18003ba16  pop     rsi
0x18003ba17  pop     rbx
0x18003ba18  pop     rbp
0x18003ba19  retn
```
