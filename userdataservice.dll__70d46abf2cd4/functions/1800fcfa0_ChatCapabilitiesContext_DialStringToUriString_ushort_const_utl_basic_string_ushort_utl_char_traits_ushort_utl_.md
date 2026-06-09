# ChatCapabilitiesContext::DialStringToUriString(ushort const *,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *)

- ea: `0x1800fcfa0`
- end: `0x1800fd0fc`
- name: `?DialStringToUriString@ChatCapabilitiesContext@@SAJPEBGPEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z`
- size: `348`
- prototype: ``
- caller_count: `4`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800efd60`
- `0x1800f274c`
- `0x1800fd150`
- `0x1800fd3bc`

## callees

- `0x180008f0c`
- `0x180035c40`
- `0x1800fcd44`
- `0x1800fcfa0`
- `0x18012c76a`
- `0x18012c7b0`

## import_xrefs

- `PhoneUtil!GetTelUriFromDialString` at `0x1800fd090`
- `PhoneUtil!GetTelUriFromDialString` at `0x1800fd090`
- `PhoneOm!PhoneGetProviderLineServiceInfo` at `0x1800fd03b`
- `PhoneOm!PhoneGetProviderLineServiceInfo` at `0x1800fd03b`
- `PhoneOm!PhoneAPIInitialize` at `0x1800fcfca`
- `PhoneOm!PhoneAPIInitialize` at `0x1800fcfca`
- `PhoneOm!PhoneGetDefaultOutgoingLine` at `0x1800fd00b`
- `PhoneOm!PhoneGetDefaultOutgoingLine` at `0x1800fd00b`

## string_xrefs

- `0x1800fcfdc`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\chatcapabilitiescontext.cpp`
- `0x1800fd054`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\chatcapabilitiescontext.cpp`

## pseudocode

```c
__int64 __fastcall ChatCapabilitiesContext::DialStringToUriString(const unsigned __int16 *a1, __int64 a2)
{
  int v4; // eax
  unsigned int v5; // ebx
  int DefaultOutgoingLine; // eax
  __int64 v7; // r9
  __int64 v8; // rdx
  __int64 v9; // rcx
  _BYTE v11[8]; // [rsp+30h] [rbp-1F8h] BYREF
  GUID v12; // [rsp+38h] [rbp-1F0h] BYREF
  _BYTE v13[128]; // [rsp+50h] [rbp-1D8h] BYREF
  unsigned __int16 v14[96]; // [rsp+D0h] [rbp-158h] BYREF
  unsigned __int16 v15[64]; // [rsp+190h] [rbp-98h] BYREF

  v4 = PhoneAPIInitialize();
  v5 = v4;
  if ( v4 >= 0 )
  {
    v11[1] = 1;
    v12 = GUID_NULL;
    DefaultOutgoingLine = PhoneGetDefaultOutgoingLine(&v12);
    v5 = DefaultOutgoingLine;
    if ( DefaultOutgoingLine >= 0 )
    {
      memset_0(v13, 0, 0x13Cu);
      DefaultOutgoingLine = PhoneGetProviderLineServiceInfo(&v12, v13);
      v5 = DefaultOutgoingLine;
      if ( DefaultOutgoingLine >= 0 )
      {
        memset_0(v15, 0, sizeof(v15));
        DefaultOutgoingLine = GetTelUriFromDialString(a1, v14, v15, 0x40u);
        v5 = DefaultOutgoingLine;
        if ( DefaultOutgoingLine >= 0 )
        {
          if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                                  a2,
                                  v15) )
          {
            v5 = 0;
            goto LABEL_14;
          }
          v5 = -2147024882;
          v7 = 494;
          v9 = 2147942414LL;
          v8 = 0;
LABEL_8:
          Log_HREvent(
            v9,
            v8,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\chatcapabilitiescontext.cpp",
            v7);
LABEL_14:
          tlx::_UndoSolo__lambda_45fdd2623d3e5011e17e16ee60884cc5___::__UndoSolo__lambda_45fdd2623d3e5011e17e16ee60884cc5___(v11);
          return v5;
        }
        v7 = 492;
      }
      else
      {
        v7 = 488;
      }
    }
    else
    {
      v7 = 485;
    }
    v8 = 1;
    v9 = (unsigned int)DefaultOutgoingLine;
    goto LABEL_8;
  }
  Log_HREvent(
    (unsigned int)v4,
    1,
    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\chatcapabilitiescontext.cpp",
    479);
  return v5;
}

```

## disassembly

```asm
0x1800fcfa0  mov     [rsp+arg_10], rbx
0x1800fcfa5  mov     [rsp+arg_18], rbp
0x1800fcfaa  push    rsi
0x1800fcfab  sub     rsp, 220h
0x1800fcfb2  mov     rax, cs:__security_cookie
0x1800fcfb9  xor     rax, rsp
0x1800fcfbc  mov     [rsp+228h+var_18], rax
0x1800fcfc4  mov     rsi, rdx
0x1800fcfc7  mov     rbp, rcx
0x1800fcfca  call    cs:__imp_PhoneAPIInitialize
0x1800fcfd0  mov     ebx, eax
0x1800fcfd2  test    eax, eax
0x1800fcfd4  jns     short loc_1800FCFF4
0x1800fcfd6  mov     r9d, 1DFh
0x1800fcfdc  lea     r8, aOnecoreuapBase_3; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800fcfe3  mov     edx, 1
0x1800fcfe8  mov     ecx, eax
0x1800fcfea  call    Log_HREvent
0x1800fcfef  jmp     loc_1800FD0D5
0x1800fcff4  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800fcffb  lea     rcx, [rsp+228h+var_1F0]
0x1800fd000  mov     [rsp+228h+var_1F7], 1
0x1800fd005  movdqu  xmmword ptr [rsp+228h+var_1F0.Data1], xmm0
0x1800fd00b  call    cs:__imp_PhoneGetDefaultOutgoingLine
0x1800fd011  mov     ebx, eax
0x1800fd013  test    eax, eax
0x1800fd015  jns     short loc_1800FD01F
0x1800fd017  mov     r9d, 1E5h
0x1800fd01d  jmp     short loc_1800FD04D
0x1800fd01f  xor     edx, edx; Val
0x1800fd021  lea     rcx, [rsp+228h+var_1D8]; void *
0x1800fd026  mov     r8d, 13Ch; Size
0x1800fd02c  call    memset_0
0x1800fd031  lea     rdx, [rsp+228h+var_1D8]
0x1800fd036  lea     rcx, [rsp+228h+var_1F0]
0x1800fd03b  call    cs:__imp_PhoneGetProviderLineServiceInfo
0x1800fd041  mov     ebx, eax
0x1800fd043  test    eax, eax
0x1800fd045  jns     short loc_1800FD062
0x1800fd047  mov     r9d, 1E8h
0x1800fd04d  mov     edx, 1
0x1800fd052  mov     ecx, eax
0x1800fd054  lea     r8, aOnecoreuapBase_3; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800fd05b  call    Log_HREvent
0x1800fd060  jmp     short loc_1800FD0CB
0x1800fd062  xor     edx, edx; Val
0x1800fd064  lea     rcx, [rsp+228h+var_98]; void *
0x1800fd06c  mov     r8d, 80h; Size
0x1800fd072  call    memset_0
0x1800fd077  mov     r9d, 40h ; '@'
0x1800fd07d  lea     r8, [rsp+228h+var_98]
0x1800fd085  lea     rdx, [rsp+228h+var_158]
0x1800fd08d  mov     rcx, rbp
0x1800fd090  call    cs:__imp_?GetTelUriFromDialString@@YAJPEBG0PEAGI@Z; GetTelUriFromDialString(ushort const *,ushort const *,ushort *,uint)
0x1800fd096  mov     ebx, eax
0x1800fd098  test    eax, eax
0x1800fd09a  jns     short loc_1800FD0A4
0x1800fd09c  mov     r9d, 1ECh
0x1800fd0a2  jmp     short loc_1800FD04D
0x1800fd0a4  lea     rdx, [rsp+228h+var_98]
0x1800fd0ac  mov     rcx, rsi
0x1800fd0af  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x1800fd0b4  test    al, al
0x1800fd0b6  jnz     short loc_1800FD0C9
0x1800fd0b8  mov     ebx, 8007000Eh
0x1800fd0bd  mov     r9d, 1EEh
0x1800fd0c3  mov     ecx, ebx
0x1800fd0c5  xor     edx, edx
0x1800fd0c7  jmp     short loc_1800FD054
0x1800fd0c9  xor     ebx, ebx
0x1800fd0cb  lea     rcx, [rsp+228h+var_1F8]
0x1800fd0d0  call    tlx___UndoSolo__lambda_45fdd2623d3e5011e17e16ee60884cc5_______UndoSolo__lambda_45fdd2623d3e5011e17e16ee60884cc5___
0x1800fd0d5  mov     eax, ebx
0x1800fd0d7  mov     rcx, [rsp+228h+var_18]
0x1800fd0df  xor     rcx, rsp; StackCookie
0x1800fd0e2  call    __security_check_cookie
0x1800fd0e7  lea     r11, [rsp+228h+var_8]
0x1800fd0ef  mov     rbx, [r11+20h]
0x1800fd0f3  mov     rbp, [r11+28h]
0x1800fd0f7  mov     rsp, r11
0x1800fd0fa  pop     rsi
0x1800fd0fb  retn
```
