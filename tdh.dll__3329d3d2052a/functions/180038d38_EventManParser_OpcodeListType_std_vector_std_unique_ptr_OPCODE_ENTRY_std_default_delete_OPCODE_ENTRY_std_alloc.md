# EventManParser::OpcodeListType(std::vector<std::unique_ptr<OPCODE_ENTRY,std::default_delete<OPCODE_ENTRY>>,std::allocator<std::unique_ptr<OPCODE_ENTRY,std::default_delete<OPCODE_ENTRY>>>> &,TASK_ENTRY *)

- ea: `0x180038d38`
- end: `0x180038e1a`
- name: `?OpcodeListType@EventManParser@@AEAAXAEAV?$vector@V?$unique_ptr@VOPCODE_ENTRY@@U?$default_delete@VOPCODE_ENTRY@@@std@@@std@@V?$allocator@V?$unique_ptr@VOPCODE_ENTRY@@U?$default_delete@VOPCODE_ENTRY@@@std@@@std@@@2@@std@@PEAVTASK_ENTRY@@@Z`
- size: `226`
- prototype: `__int64 __fastcall(XmlReader *this)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, service_task`

## callers

- `0x180039cdc`
- `0x18003b7e0`

## callees

- `0x18001cb90`
- `0x18002e8f4`
- `0x180032cac`
- `0x180035858`
- `0x180037e80`
- `0x180038cc4`
- `0x180038d38`
- `0x180038e20`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall EventManParser::OpcodeListType(XmlReader *this, __int64 *a2, struct TASK_ENTRY *a3)
{
  char result; // al
  __int64 *v7; // rax
  __int64 *v8; // rdx
  __int64 v9; // rcx
  _QWORD v10[2]; // [rsp+20h] [rbp-48h] BYREF
  _OWORD v11[2]; // [rsp+30h] [rbp-38h] BYREF
  __int128 v12; // [rsp+50h] [rbp-18h] BYREF
  KEYWORD_ENTRY *v13; // [rsp+88h] [rbp+20h] BYREF

  for ( result = XmlReader::FirstChildElement(this); result; result = XmlReader::NextChildElement((xp::XmlReader **)this) )
  {
    XmlReader::GetLocalName(this, v11);
    v11[1] = v11[0];
    v12 = *(_OWORD *)&off_18004F7F0;
    v10[0] = L"opcode";
    v10[1] = 6;
    if ( EventManParser::ElementMatches(this, v10, &v12) )
    {
      v7 = EventManParser::OpcodeType(this, (__int64 *)&v13, a3);
      v8 = (__int64 *)a2[1];
      if ( v8 == (__int64 *)a2[2] )
      {
        std::vector<std::unique_ptr<OPCODE_ENTRY>>::_Emplace_reallocate<std::unique_ptr<OPCODE_ENTRY>>(
          a2,
          (__int64)v8,
          v7);
      }
      else
      {
        v9 = *v7;
        *v7 = 0;
        *v8 = v9;
        a2[1] += 8;
      }
      std::unique_ptr<OPCODE_ENTRY>::~unique_ptr<OPCODE_ENTRY>(&v13);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180038d38  mov     [rsp+arg_0], rbx
0x180038d3d  mov     [rsp+arg_8], rsi
0x180038d42  push    rdi
0x180038d43  sub     rsp, 60h
0x180038d47  mov     rsi, r8
0x180038d4a  mov     rbx, rdx
0x180038d4d  mov     rdi, rcx
0x180038d50  call    ?FirstChildElement@XmlReader@@QEAA_NXZ; XmlReader::FirstChildElement(void)
0x180038d55  jmp     loc_180038E02
0x180038d5a  lea     rdx, [rsp+68h+var_38]
0x180038d5f  mov     rcx, rdi; this
0x180038d62  call    ?GetLocalName@XmlReader@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; XmlReader::GetLocalName(void)
0x180038d67  movups  xmm0, [rsp+68h+var_38]
0x180038d6c  movups  xmm1, xmmword ptr cs:off_18004F7F0; "http://schemas.microsoft.com/win/2004/0"...
0x180038d73  movdqu  [rsp+68h+var_28], xmm0
0x180038d79  movdqu  [rsp+68h+var_18], xmm1
0x180038d7f  lea     rax, aOpcode; "opcode"
0x180038d86  mov     [rsp+68h+var_48], rax
0x180038d8b  mov     [rsp+68h+var_40], 6
0x180038d94  lea     r9, [rsp+68h+var_28]
0x180038d99  lea     r8, [rsp+68h+var_18]
0x180038d9e  lea     rdx, [rsp+68h+var_48]
0x180038da3  mov     rcx, rdi; this
0x180038da6  call    ?ElementMatches@EventManParser@@AEBA_NV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@00@Z; EventManParser::ElementMatches(std::wstring_view,std::wstring_view,std::wstring_view)
0x180038dab  test    al, al
0x180038dad  jz      short loc_180038DFA
0x180038daf  mov     r8, rsi
0x180038db2  lea     rdx, [rsp+68h+arg_18]
0x180038dba  mov     rcx, rdi; this
0x180038dbd  call    ?OpcodeType@EventManParser@@AEAA?AV?$unique_ptr@VOPCODE_ENTRY@@U?$default_delete@VOPCODE_ENTRY@@@std@@@std@@PEAVTASK_ENTRY@@@Z; EventManParser::OpcodeType(TASK_ENTRY *)
0x180038dc2  nop
0x180038dc3  mov     rdx, [rbx+8]
0x180038dc7  cmp     rdx, [rbx+10h]
0x180038dcb  jz      short loc_180038DE1
0x180038dcd  mov     rcx, [rax]
0x180038dd0  mov     qword ptr [rax], 0
0x180038dd7  mov     [rdx], rcx
0x180038dda  add     qword ptr [rbx+8], 8
0x180038ddf  jmp     short loc_180038DED
0x180038de1  mov     r8, rax
0x180038de4  mov     rcx, rbx
0x180038de7  call    ??$_Emplace_reallocate@V?$unique_ptr@VOPCODE_ENTRY@@U?$default_delete@VOPCODE_ENTRY@@@std@@@std@@@?$vector@V?$unique_ptr@VOPCODE_ENTRY@@U?$default_delete@VOPCODE_ENTRY@@@std@@@std@@V?$allocator@V?$unique_ptr@VOPCODE_ENTRY@@U?$default_delete@VOPCODE_ENTRY@@@std@@@std@@@2@@std@@AEAAPEAV?$unique_ptr@VOPCODE_ENTRY@@U?$default_delete@VOPCODE_ENTRY@@@std@@@1@QEAV21@$$QEAV21@@Z; std::vector<std::unique_ptr<OPCODE_ENTRY>>::_Emplace_reallocate<std::unique_ptr<OPCODE_ENTRY>>(std::unique_ptr<OPCODE_ENTRY> * const,std::unique_ptr<OPCODE_ENTRY> &&)
0x180038dec  nop
0x180038ded  lea     rcx, [rsp+68h+arg_18]
0x180038df5  call    ??1?$unique_ptr@VOPCODE_ENTRY@@U?$default_delete@VOPCODE_ENTRY@@@std@@@std@@QEAA@XZ; std::unique_ptr<OPCODE_ENTRY>::~unique_ptr<OPCODE_ENTRY>(void)
0x180038dfa  mov     rcx, rdi; this
0x180038dfd  call    ?NextChildElement@XmlReader@@QEAA_NXZ; XmlReader::NextChildElement(void)
0x180038e02  test    al, al
0x180038e04  jnz     loc_180038D5A
0x180038e0a  mov     rbx, [rsp+68h+arg_0]
0x180038e0f  mov     rsi, [rsp+68h+arg_8]
0x180038e14  add     rsp, 60h
0x180038e18  pop     rdi
0x180038e19  retn
```
