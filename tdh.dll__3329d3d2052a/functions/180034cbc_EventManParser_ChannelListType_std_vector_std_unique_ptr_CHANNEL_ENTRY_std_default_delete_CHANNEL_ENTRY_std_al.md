# EventManParser::ChannelListType(std::vector<std::unique_ptr<CHANNEL_ENTRY,std::default_delete<CHANNEL_ENTRY>>,std::allocator<std::unique_ptr<CHANNEL_ENTRY,std::default_delete<CHANNEL_ENTRY>>>> &)

- ea: `0x180034cbc`
- end: `0x180034e12`
- name: `?ChannelListType@EventManParser@@AEAAXAEAV?$vector@V?$unique_ptr@VCHANNEL_ENTRY@@U?$default_delete@VCHANNEL_ENTRY@@@std@@@std@@V?$allocator@V?$unique_ptr@VCHANNEL_ENTRY@@U?$default_delete@VCHANNEL_ENTRY@@@std@@@std@@@2@@std@@@Z`
- size: `342`
- prototype: `__int64 __fastcall(XmlReader *this)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180039cdc`

## callees

- `0x18001cb90`
- `0x18002e15c`
- `0x180032b8c`
- `0x180034cbc`
- `0x180034e18`
- `0x180035858`
- `0x180037e80`
- `0x180037ff0`
- `0x180038cc4`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall EventManParser::ChannelListType(XmlReader *this, __int64 a2)
{
  char result; // al
  __int128 v5; // xmm6
  __int64 *v6; // rax
  _QWORD *v7; // rdx
  __int64 v8; // rcx
  __int64 *v9; // rcx
  __int64 *v10; // rax
  __int64 *v11; // rdx
  __int64 v12; // rcx
  _QWORD v13[2]; // [rsp+20h] [rbp-60h] BYREF
  _QWORD v14[2]; // [rsp+30h] [rbp-50h] BYREF
  __int128 v15; // [rsp+40h] [rbp-40h] BYREF
  __int128 v16; // [rsp+50h] [rbp-30h] BYREF
  __int128 v17; // [rsp+60h] [rbp-20h] BYREF
  char v18; // [rsp+A0h] [rbp+20h] BYREF
  __int64 v19; // [rsp+A8h] [rbp+28h] BYREF

  for ( result = XmlReader::FirstChildElement(this); result; result = XmlReader::NextChildElement((xp::XmlReader **)this) )
  {
    XmlReader::GetLocalName(this, &v15);
    v5 = v15;
    v16 = v15;
    v17 = *(_OWORD *)&off_18004F7F0;
    v13[0] = L"importChannel";
    v13[1] = 13;
    if ( EventManParser::ElementMatches(this, v13, &v17) )
    {
      v6 = (__int64 *)EventManParser::ImportChannelType(this);
      v7 = *(_QWORD **)(a2 + 8);
      if ( v7 == *(_QWORD **)(a2 + 16) )
      {
        std::vector<std::unique_ptr<CHANNEL_ENTRY>>::_Emplace_reallocate<std::unique_ptr<CHANNEL_ENTRY>>(a2, v7, v6);
      }
      else
      {
        v8 = *v6;
        *v6 = 0;
        *v7 = v8;
        *(_QWORD *)(a2 + 8) += 8LL;
      }
      v9 = (__int64 *)&v18;
    }
    else
    {
      v17 = v5;
      v16 = *(_OWORD *)&off_18004F7F0;
      v14[0] = L"channel";
      v14[1] = 7;
      if ( !EventManParser::ElementMatches(this, v14, &v16) )
        continue;
      v10 = EventManParser::ChannelType(this, &v19);
      v11 = *(__int64 **)(a2 + 8);
      if ( v11 == *(__int64 **)(a2 + 16) )
      {
        std::vector<std::unique_ptr<CHANNEL_ENTRY>>::_Emplace_reallocate<std::unique_ptr<CHANNEL_ENTRY>>(a2, v11, v10);
      }
      else
      {
        v12 = *v10;
        *v10 = 0;
        *v11 = v12;
        *(_QWORD *)(a2 + 8) += 8LL;
      }
      v9 = &v19;
    }
    std::unique_ptr<CHANNEL_ENTRY>::~unique_ptr<CHANNEL_ENTRY>(v9);
  }
  return result;
}

```

## disassembly

```asm
0x180034cbc  mov     [rsp-8+arg_0], rbx
0x180034cc1  mov     [rsp-8+arg_8], rdi
0x180034cc6  push    rbp
0x180034cc7  mov     rbp, rsp
0x180034cca  sub     rsp, 80h
0x180034cd1  movaps  [rsp+80h+var_10], xmm6
0x180034cd6  mov     rbx, rdx
0x180034cd9  mov     rdi, rcx
0x180034cdc  call    ?FirstChildElement@XmlReader@@QEAA_NXZ; XmlReader::FirstChildElement(void)
0x180034ce1  jmp     loc_180034DF0
0x180034ce6  lea     rdx, [rbp+var_40]
0x180034cea  mov     rcx, rdi; this
0x180034ced  call    ?GetLocalName@XmlReader@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; XmlReader::GetLocalName(void)
0x180034cf2  movups  xmm6, [rbp+var_40]
0x180034cf6  movups  xmm0, xmmword ptr cs:off_18004F7F0; "http://schemas.microsoft.com/win/2004/0"...
0x180034cfd  movdqu  [rbp+var_30], xmm6
0x180034d02  movdqu  [rbp+var_20], xmm0
0x180034d07  lea     rax, aImportchannel; "importChannel"
0x180034d0e  mov     [rbp+var_60], rax
0x180034d12  mov     [rbp+var_58], 0Dh
0x180034d1a  lea     r9, [rbp+var_30]
0x180034d1e  lea     r8, [rbp+var_20]
0x180034d22  lea     rdx, [rbp+var_60]
0x180034d26  mov     rcx, rdi; this
0x180034d29  call    ?ElementMatches@EventManParser@@AEBA_NV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@00@Z; EventManParser::ElementMatches(std::wstring_view,std::wstring_view,std::wstring_view)
0x180034d2e  mov     rcx, rdi; this
0x180034d31  test    al, al
0x180034d33  jz      short loc_180034D6F
0x180034d35  lea     rdx, [rbp+arg_10]
0x180034d39  call    ?ImportChannelType@EventManParser@@AEAA?AV?$unique_ptr@VCHANNEL_ENTRY@@U?$default_delete@VCHANNEL_ENTRY@@@std@@@std@@XZ; EventManParser::ImportChannelType(void)
0x180034d3e  nop
0x180034d3f  mov     rdx, [rbx+8]
0x180034d43  cmp     rdx, [rbx+10h]
0x180034d47  jz      short loc_180034D5D
0x180034d49  mov     rcx, [rax]
0x180034d4c  mov     qword ptr [rax], 0
0x180034d53  mov     [rdx], rcx
0x180034d56  add     qword ptr [rbx+8], 8
0x180034d5b  jmp     short loc_180034D69
0x180034d5d  mov     r8, rax
0x180034d60  mov     rcx, rbx
0x180034d63  call    ??$_Emplace_reallocate@V?$unique_ptr@VCHANNEL_ENTRY@@U?$default_delete@VCHANNEL_ENTRY@@@std@@@std@@@?$vector@V?$unique_ptr@VCHANNEL_ENTRY@@U?$default_delete@VCHANNEL_ENTRY@@@std@@@std@@V?$allocator@V?$unique_ptr@VCHANNEL_ENTRY@@U?$default_delete@VCHANNEL_ENTRY@@@std@@@std@@@2@@std@@AEAAPEAV?$unique_ptr@VCHANNEL_ENTRY@@U?$default_delete@VCHANNEL_ENTRY@@@std@@@1@QEAV21@$$QEAV21@@Z; std::vector<std::unique_ptr<CHANNEL_ENTRY>>::_Emplace_reallocate<std::unique_ptr<CHANNEL_ENTRY>>(std::unique_ptr<CHANNEL_ENTRY> * const,std::unique_ptr<CHANNEL_ENTRY> &&)
0x180034d68  nop
0x180034d69  lea     rcx, [rbp+arg_10]
0x180034d6d  jmp     short loc_180034DE3
0x180034d6f  movups  xmm0, xmmword ptr cs:off_18004F7F0; "http://schemas.microsoft.com/win/2004/0"...
0x180034d76  movdqu  [rbp+var_20], xmm6
0x180034d7b  movdqu  [rbp+var_30], xmm0
0x180034d80  lea     rax, aChannel; "channel"
0x180034d87  mov     [rbp+var_50], rax
0x180034d8b  mov     [rbp+var_48], 7
0x180034d93  lea     r9, [rbp+var_20]
0x180034d97  lea     r8, [rbp+var_30]
0x180034d9b  lea     rdx, [rbp+var_50]
0x180034d9f  call    ?ElementMatches@EventManParser@@AEBA_NV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@00@Z; EventManParser::ElementMatches(std::wstring_view,std::wstring_view,std::wstring_view)
0x180034da4  test    al, al
0x180034da6  jz      short loc_180034DE8
0x180034da8  lea     rdx, [rbp+arg_18]
0x180034dac  mov     rcx, rdi; this
0x180034daf  call    ?ChannelType@EventManParser@@AEAA?AV?$unique_ptr@VCHANNEL_ENTRY@@U?$default_delete@VCHANNEL_ENTRY@@@std@@@std@@XZ; EventManParser::ChannelType(void)
0x180034db4  nop
0x180034db5  mov     rdx, [rbx+8]
0x180034db9  cmp     rdx, [rbx+10h]
0x180034dbd  jz      short loc_180034DD3
0x180034dbf  mov     rcx, [rax]
0x180034dc2  mov     qword ptr [rax], 0
0x180034dc9  mov     [rdx], rcx
0x180034dcc  add     qword ptr [rbx+8], 8
0x180034dd1  jmp     short loc_180034DDF
0x180034dd3  mov     r8, rax
0x180034dd6  mov     rcx, rbx
0x180034dd9  call    ??$_Emplace_reallocate@V?$unique_ptr@VCHANNEL_ENTRY@@U?$default_delete@VCHANNEL_ENTRY@@@std@@@std@@@?$vector@V?$unique_ptr@VCHANNEL_ENTRY@@U?$default_delete@VCHANNEL_ENTRY@@@std@@@std@@V?$allocator@V?$unique_ptr@VCHANNEL_ENTRY@@U?$default_delete@VCHANNEL_ENTRY@@@std@@@std@@@2@@std@@AEAAPEAV?$unique_ptr@VCHANNEL_ENTRY@@U?$default_delete@VCHANNEL_ENTRY@@@std@@@1@QEAV21@$$QEAV21@@Z; std::vector<std::unique_ptr<CHANNEL_ENTRY>>::_Emplace_reallocate<std::unique_ptr<CHANNEL_ENTRY>>(std::unique_ptr<CHANNEL_ENTRY> * const,std::unique_ptr<CHANNEL_ENTRY> &&)
0x180034dde  nop
0x180034ddf  lea     rcx, [rbp+arg_18]
0x180034de3  call    ??1?$unique_ptr@VCHANNEL_ENTRY@@U?$default_delete@VCHANNEL_ENTRY@@@std@@@std@@QEAA@XZ; std::unique_ptr<CHANNEL_ENTRY>::~unique_ptr<CHANNEL_ENTRY>(void)
0x180034de8  mov     rcx, rdi; this
0x180034deb  call    ?NextChildElement@XmlReader@@QEAA_NXZ; XmlReader::NextChildElement(void)
0x180034df0  test    al, al
0x180034df2  jnz     loc_180034CE6
0x180034df8  lea     r11, [rsp+80h+var_s0]
0x180034e00  mov     rbx, [r11+10h]
0x180034e04  mov     rdi, [r11+18h]
0x180034e08  movaps  xmm6, [rsp+80h+var_10]
0x180034e0d  mov     rsp, r11
0x180034e10  pop     rbp
0x180034e11  retn
```
