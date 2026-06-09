# EventManParser::TaskListType(std::vector<std::unique_ptr<TASK_ENTRY,std::default_delete<TASK_ENTRY>>,std::allocator<std::unique_ptr<TASK_ENTRY,std::default_delete<TASK_ENTRY>>>> &,std::vector<std::unique_ptr<OPCODE_ENTRY,std::default_delete<OPCODE_ENTRY>>,std::allocator<std::unique_ptr<OPCODE_ENTRY,std::default_delete<OPCODE_ENTRY>>>> &)

- ea: `0x18003b6f8`
- end: `0x18003b7da`
- name: `?TaskListType@EventManParser@@AEAAXAEAV?$vector@V?$unique_ptr@VTASK_ENTRY@@U?$default_delete@VTASK_ENTRY@@@std@@@std@@V?$allocator@V?$unique_ptr@VTASK_ENTRY@@U?$default_delete@VTASK_ENTRY@@@std@@@std@@@2@@std@@AEAV?$vector@V?$unique_ptr@VOPCODE_ENTRY@@U?$default_delete@VOPCODE_ENTRY@@@std@@@std@@V?$allocator@V?$unique_ptr@VOPCODE_ENTRY@@U?$default_delete@VOPCODE_ENTRY@@@std@@@std@@@2@@3@@Z`
- size: `226`
- prototype: `__int64 __fastcall(XmlReader *this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task`

## callers

- `0x180039cdc`

## callees

- `0x18001cb90`
- `0x18002e8f4`
- `0x180032cac`
- `0x180035858`
- `0x180037e80`
- `0x180038cc4`
- `0x18003b6f8`
- `0x18003b7e0`

## pseudocode

```c
char __fastcall EventManParser::TaskListType(XmlReader *this, __int64 *a2)
{
  char result; // al
  __int64 *v5; // rax
  __int64 *v6; // rdx
  __int64 v7; // rcx
  _QWORD v8[2]; // [rsp+20h] [rbp-48h] BYREF
  __int128 v9; // [rsp+30h] [rbp-38h] BYREF
  __int128 v10; // [rsp+40h] [rbp-28h] BYREF
  __int128 v11; // [rsp+50h] [rbp-18h] BYREF
  KEYWORD_ENTRY *v12; // [rsp+88h] [rbp+20h] BYREF

  for ( result = XmlReader::FirstChildElement(this); result; result = XmlReader::NextChildElement((xp::XmlReader **)this) )
  {
    XmlReader::GetLocalName(this, &v9);
    v10 = v9;
    v11 = *(_OWORD *)&off_18004F7F0;
    v8[0] = L"task";
    v8[1] = 4;
    if ( EventManParser::ElementMatches(this, v8, &v11, &v10) )
    {
      v5 = EventManParser::TaskType(this, (__int64 *)&v12);
      v6 = (__int64 *)a2[1];
      if ( v6 == (__int64 *)a2[2] )
      {
        std::vector<std::unique_ptr<OPCODE_ENTRY>>::_Emplace_reallocate<std::unique_ptr<OPCODE_ENTRY>>(
          a2,
          (__int64)v6,
          v5);
      }
      else
      {
        v7 = *v5;
        *v5 = 0;
        *v6 = v7;
        a2[1] += 8;
      }
      std::unique_ptr<OPCODE_ENTRY>::~unique_ptr<OPCODE_ENTRY>(&v12);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18003b6f8  mov     [rsp+arg_0], rbx
0x18003b6fd  mov     [rsp+arg_8], rsi
0x18003b702  push    rdi
0x18003b703  sub     rsp, 60h
0x18003b707  mov     rsi, r8
0x18003b70a  mov     rbx, rdx
0x18003b70d  mov     rdi, rcx
0x18003b710  call    ?FirstChildElement@XmlReader@@QEAA_NXZ; XmlReader::FirstChildElement(void)
0x18003b715  jmp     loc_18003B7C2
0x18003b71a  lea     rdx, [rsp+68h+var_38]
0x18003b71f  mov     rcx, rdi; this
0x18003b722  call    ?GetLocalName@XmlReader@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; XmlReader::GetLocalName(void)
0x18003b727  movups  xmm0, [rsp+68h+var_38]
0x18003b72c  movups  xmm1, xmmword ptr cs:off_18004F7F0; "http://schemas.microsoft.com/win/2004/0"...
0x18003b733  movdqu  [rsp+68h+var_28], xmm0
0x18003b739  movdqu  [rsp+68h+var_18], xmm1
0x18003b73f  lea     rax, aTask; "task"
0x18003b746  mov     [rsp+68h+var_48], rax
0x18003b74b  mov     [rsp+68h+var_40], 4
0x18003b754  lea     r9, [rsp+68h+var_28]
0x18003b759  lea     r8, [rsp+68h+var_18]
0x18003b75e  lea     rdx, [rsp+68h+var_48]
0x18003b763  mov     rcx, rdi; this
0x18003b766  call    ?ElementMatches@EventManParser@@AEBA_NV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@00@Z; EventManParser::ElementMatches(std::wstring_view,std::wstring_view,std::wstring_view)
0x18003b76b  test    al, al
0x18003b76d  jz      short loc_18003B7BA
0x18003b76f  mov     r8, rsi
0x18003b772  lea     rdx, [rsp+68h+arg_18]
0x18003b77a  mov     rcx, rdi; this
0x18003b77d  call    ?TaskType@EventManParser@@AEAA?AV?$unique_ptr@VTASK_ENTRY@@U?$default_delete@VTASK_ENTRY@@@std@@@std@@AEAV?$vector@V?$unique_ptr@VOPCODE_ENTRY@@U?$default_delete@VOPCODE_ENTRY@@@std@@@std@@V?$allocator@V?$unique_ptr@VOPCODE_ENTRY@@U?$default_delete@VOPCODE_ENTRY@@@std@@@std@@@2@@3@@Z; EventManParser::TaskType(std::vector<std::unique_ptr<OPCODE_ENTRY>> &)
0x18003b782  nop
0x18003b783  mov     rdx, [rbx+8]
0x18003b787  cmp     rdx, [rbx+10h]
0x18003b78b  jz      short loc_18003B7A1
0x18003b78d  mov     rcx, [rax]
0x18003b790  mov     qword ptr [rax], 0
0x18003b797  mov     [rdx], rcx
0x18003b79a  add     qword ptr [rbx+8], 8
0x18003b79f  jmp     short loc_18003B7AD
0x18003b7a1  mov     r8, rax
0x18003b7a4  mov     rcx, rbx
0x18003b7a7  call    ??$_Emplace_reallocate@V?$unique_ptr@VOPCODE_ENTRY@@U?$default_delete@VOPCODE_ENTRY@@@std@@@std@@@?$vector@V?$unique_ptr@VOPCODE_ENTRY@@U?$default_delete@VOPCODE_ENTRY@@@std@@@std@@V?$allocator@V?$unique_ptr@VOPCODE_ENTRY@@U?$default_delete@VOPCODE_ENTRY@@@std@@@std@@@2@@std@@AEAAPEAV?$unique_ptr@VOPCODE_ENTRY@@U?$default_delete@VOPCODE_ENTRY@@@std@@@1@QEAV21@$$QEAV21@@Z; std::vector<std::unique_ptr<OPCODE_ENTRY>>::_Emplace_reallocate<std::unique_ptr<OPCODE_ENTRY>>(std::unique_ptr<OPCODE_ENTRY> * const,std::unique_ptr<OPCODE_ENTRY> &&)
0x18003b7ac  nop
0x18003b7ad  lea     rcx, [rsp+68h+arg_18]
0x18003b7b5  call    ??1?$unique_ptr@VOPCODE_ENTRY@@U?$default_delete@VOPCODE_ENTRY@@@std@@@std@@QEAA@XZ; std::unique_ptr<OPCODE_ENTRY>::~unique_ptr<OPCODE_ENTRY>(void)
0x18003b7ba  mov     rcx, rdi; this
0x18003b7bd  call    ?NextChildElement@XmlReader@@QEAA_NXZ; XmlReader::NextChildElement(void)
0x18003b7c2  test    al, al
0x18003b7c4  jnz     loc_18003B71A
0x18003b7ca  mov     rbx, [rsp+68h+arg_0]
0x18003b7cf  mov     rsi, [rsp+68h+arg_8]
0x18003b7d4  add     rsp, 60h
0x18003b7d8  pop     rdi
0x18003b7d9  retn
```
