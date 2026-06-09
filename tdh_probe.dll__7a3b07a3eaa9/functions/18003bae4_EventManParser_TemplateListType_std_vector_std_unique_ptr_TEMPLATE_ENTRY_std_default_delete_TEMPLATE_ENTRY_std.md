# EventManParser::TemplateListType(std::vector<std::unique_ptr<TEMPLATE_ENTRY,std::default_delete<TEMPLATE_ENTRY>>,std::allocator<std::unique_ptr<TEMPLATE_ENTRY,std::default_delete<TEMPLATE_ENTRY>>>> &)

- ea: `0x18003bae4`
- end: `0x18003bbb6`
- name: `?TemplateListType@EventManParser@@AEAAXAEAV?$vector@V?$unique_ptr@VTEMPLATE_ENTRY@@U?$default_delete@VTEMPLATE_ENTRY@@@std@@@std@@V?$allocator@V?$unique_ptr@VTEMPLATE_ENTRY@@U?$default_delete@VTEMPLATE_ENTRY@@@std@@@std@@@2@@std@@@Z`
- size: `210`
- prototype: `__int64 __fastcall(XmlReader *this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180039cdc`

## callees

- `0x18001cb90`
- `0x18001d810`
- `0x18002eb7c`
- `0x180032d28`
- `0x180035858`
- `0x180037e80`
- `0x180038cc4`
- `0x18003bae4`

## string_xrefs

- `0x18003bb23`: `template`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
bool __fastcall EventManParser::TemplateListType(XmlReader *this, __int64 a2)
{
  bool result; // al
  __int64 *v5; // rax
  __int64 *v6; // rdx
  __int64 v7; // rcx
  _QWORD v8[2]; // [rsp+20h] [rbp-48h] BYREF
  __int128 v9; // [rsp+30h] [rbp-38h]
  __int128 v10; // [rsp+40h] [rbp-28h] BYREF
  __int128 v11; // [rsp+50h] [rbp-18h] BYREF
  __int64 v12; // [rsp+80h] [rbp+18h] BYREF

  for ( result = XmlReader::FirstChildElement(this); result; result = XmlReader::NextChildElement(this) )
  {
    XmlReader::GetLocalName(this);
    v10 = v9;
    v11 = *(_OWORD *)&off_18004F7F0;
    v8[0] = L"template";
    v8[1] = 8;
    if ( EventManParser::ElementMatches(this, v8, &v11, &v10) )
    {
      v5 = EventManParser::TemplateItemType(this, &v12);
      v6 = *(__int64 **)(a2 + 8);
      if ( v6 == *(__int64 **)(a2 + 16) )
      {
        std::vector<std::unique_ptr<TEMPLATE_ENTRY>>::_Emplace_reallocate<std::unique_ptr<TEMPLATE_ENTRY>>(a2, v6, v5);
      }
      else
      {
        v7 = *v5;
        *v5 = 0;
        *v6 = v7;
        *(_QWORD *)(a2 + 8) += 8LL;
      }
      std::unique_ptr<TEMPLATE_ENTRY>::~unique_ptr<TEMPLATE_ENTRY>(&v12);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18003bae4  mov     [rsp+arg_0], rbx
0x18003bae9  push    rdi
0x18003baea  sub     rsp, 60h
0x18003baee  mov     rbx, rdx
0x18003baf1  mov     rdi, rcx
0x18003baf4  call    ?FirstChildElement@XmlReader@@QEAA_NXZ; XmlReader::FirstChildElement(void)
0x18003baf9  jmp     loc_18003BBA3
0x18003bafe  lea     rdx, [rsp+68h+var_38]
0x18003bb03  mov     rcx, rdi; this
0x18003bb06  call    ?GetLocalName@XmlReader@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; XmlReader::GetLocalName(void)
0x18003bb0b  movups  xmm0, [rsp+68h+var_38]
0x18003bb10  movups  xmm1, xmmword ptr cs:off_18004F7F0; "http://schemas.microsoft.com/win/2004/0"...
0x18003bb17  movdqu  [rsp+68h+var_28], xmm0
0x18003bb1d  movdqu  [rsp+68h+var_18], xmm1
0x18003bb23  lea     rax, aTemplate; "template"
0x18003bb2a  mov     [rsp+68h+var_48], rax
0x18003bb2f  mov     [rsp+68h+var_40], 8
0x18003bb38  lea     r9, [rsp+68h+var_28]
0x18003bb3d  lea     r8, [rsp+68h+var_18]
0x18003bb42  lea     rdx, [rsp+68h+var_48]
0x18003bb47  mov     rcx, rdi; this
0x18003bb4a  call    ?ElementMatches@EventManParser@@AEBA_NV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@00@Z; EventManParser::ElementMatches(std::wstring_view,std::wstring_view,std::wstring_view)
0x18003bb4f  test    al, al
0x18003bb51  jz      short loc_18003BB9B
0x18003bb53  lea     rdx, [rsp+68h+arg_10]
0x18003bb5b  mov     rcx, rdi; this
0x18003bb5e  call    ?TemplateItemType@EventManParser@@AEAA?AV?$unique_ptr@VTEMPLATE_ENTRY@@U?$default_delete@VTEMPLATE_ENTRY@@@std@@@std@@XZ; EventManParser::TemplateItemType(void)
0x18003bb63  nop
0x18003bb64  mov     rdx, [rbx+8]
0x18003bb68  cmp     rdx, [rbx+10h]
0x18003bb6c  jz      short loc_18003BB82
0x18003bb6e  mov     rcx, [rax]
0x18003bb71  mov     qword ptr [rax], 0
0x18003bb78  mov     [rdx], rcx
0x18003bb7b  add     qword ptr [rbx+8], 8
0x18003bb80  jmp     short loc_18003BB8E
0x18003bb82  mov     r8, rax
0x18003bb85  mov     rcx, rbx
0x18003bb88  call    ??$_Emplace_reallocate@V?$unique_ptr@VTEMPLATE_ENTRY@@U?$default_delete@VTEMPLATE_ENTRY@@@std@@@std@@@?$vector@V?$unique_ptr@VTEMPLATE_ENTRY@@U?$default_delete@VTEMPLATE_ENTRY@@@std@@@std@@V?$allocator@V?$unique_ptr@VTEMPLATE_ENTRY@@U?$default_delete@VTEMPLATE_ENTRY@@@std@@@std@@@2@@std@@AEAAPEAV?$unique_ptr@VTEMPLATE_ENTRY@@U?$default_delete@VTEMPLATE_ENTRY@@@std@@@1@QEAV21@$$QEAV21@@Z; std::vector<std::unique_ptr<TEMPLATE_ENTRY>>::_Emplace_reallocate<std::unique_ptr<TEMPLATE_ENTRY>>(std::unique_ptr<TEMPLATE_ENTRY> * const,std::unique_ptr<TEMPLATE_ENTRY> &&)
0x18003bb8d  nop
0x18003bb8e  lea     rcx, [rsp+68h+arg_10]
0x18003bb96  call    ??1?$unique_ptr@VTEMPLATE_ENTRY@@U?$default_delete@VTEMPLATE_ENTRY@@@std@@@std@@QEAA@XZ; std::unique_ptr<TEMPLATE_ENTRY>::~unique_ptr<TEMPLATE_ENTRY>(void)
0x18003bb9b  mov     rcx, rdi; this
0x18003bb9e  call    ?NextChildElement@XmlReader@@QEAA_NXZ; XmlReader::NextChildElement(void)
0x18003bba3  test    al, al
0x18003bba5  jnz     loc_18003BAFE
0x18003bbab  mov     rbx, [rsp+68h+arg_0]
0x18003bbb0  add     rsp, 60h
0x18003bbb4  pop     rdi
0x18003bbb5  retn
```
