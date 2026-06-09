# CreateTunnel

- ea: `0x180002b70`
- end: `0x180002de2`
- name: `CreateTunnel`
- size: `626`
- prototype: `__int64 __fastcall(__int64, __int16 *, __int64)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x180002b70`
- `0x180004420`
- `0x1800063d0`
- `0x180006414`
- `0x18000697c`
- `0x18000c330`
- `0x18000ce1c`
- `0x18000cfbe`
- `0x18000cff0`

## string_xrefs

- `0x180002bf0`: `CreateTunnel`
- `0x180002d5c`: `CreateTunnel`

## pseudocode

```c
__int64 __fastcall CreateTunnel(__int64 a1, __int16 *a2, __int64 a3)
{
  __int64 v6; // r8
  __int16 v7; // ax
  unsigned int Tunnel; // [rsp+20h] [rbp-848h]
  int v10; // [rsp+30h] [rbp-838h] BYREF
  _BYTE v11[2044]; // [rsp+34h] [rbp-834h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_I(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, a3, a1);
  }
  v10 = 0;
  memset_0(v11, 0, sizeof(v11));
  if ( byte_1800167C1 < 0 )
  {
    LOWORD(v10) = 0;
    FormatRRASErrorString(&v10, L"Entered: %s", L"CreateTunnel");
    if ( byte_1800167C1 < 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeApiTraceInfo, &v10);
  }
  if ( a1 && a2 )
  {
    v7 = *a2;
    if ( *a2 == a2[10] && (v7 == 2 || v7 == 23) )
    {
      Tunnel = InitializeVpnIkeRpcClient();
      if ( !Tunnel )
      {
        Tunnel = VpnikeCreateTunnel(Binding, a1, a2, a3);
        if ( Tunnel )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, v6, Tunnel);
          }
        }
      }
    }
    else
    {
      Tunnel = 13;
      if ( (byte_1800167C1 & 0x40) != 0 )
        McTemplateU0z_EventWriteTransfer(
          &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          RasVpnIkeApiTraceError,
          L"Invalid Data: vpnIkeTunnelParams");
    }
  }
  else
  {
    if ( (byte_1800167C1 & 0x40) != 0 )
      McTemplateU0z_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        RasVpnIkeApiTraceError,
        L"Invalid Parameter");
    Tunnel = 87;
  }
  if ( byte_1800167C1 < 0 )
  {
    LOWORD(v10) = 0;
    FormatRRASErrorString(&v10, L"Leaving: %s", L"CreateTunnel");
    if ( byte_1800167C1 < 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeApiTraceInfo, &v10);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, v6, Tunnel);
  }
  return Tunnel;
}

```

## disassembly

```asm
0x180002b70  push    rbx
0x180002b72  push    rsi
0x180002b73  push    rdi
0x180002b74  push    r14
0x180002b76  push    r15
0x180002b78  sub     rsp, 840h
0x180002b7f  mov     rax, cs:__security_cookie
0x180002b86  xor     rax, rsp
0x180002b89  mov     [rsp+868h+var_38], rax
0x180002b91  mov     r15, r8
0x180002b94  mov     rdi, rdx
0x180002b97  mov     r14, rcx
0x180002b9a  lea     rsi, WPP_GLOBAL_Control
0x180002ba1  mov     rcx, cs:WPP_GLOBAL_Control
0x180002ba8  cmp     rcx, rsi
0x180002bab  jz      short loc_180002BCA
0x180002bad  test    byte ptr [rcx+1Ch], 1
0x180002bb1  jz      short loc_180002BCA
0x180002bb3  cmp     byte ptr [rcx+19h], 6
0x180002bb7  jb      short loc_180002BCA
0x180002bb9  mov     edx, 10h
0x180002bbe  mov     r9, r14
0x180002bc1  mov     rcx, [rcx+10h]
0x180002bc5  call    WPP_SF_I
0x180002bca  xor     ebx, ebx
0x180002bcc  mov     [rsp+868h+var_838], ebx
0x180002bd0  xor     edx, edx; Val
0x180002bd2  mov     r8d, 7FCh; Size
0x180002bd8  lea     rcx, [rsp+868h+var_834]; void *
0x180002bdd  call    memset_0
0x180002be2  test    cs:byte_1800167C1, 80h
0x180002be9  jz      short loc_180002C28
0x180002beb  mov     word ptr [rsp+868h+var_838], bx
0x180002bf0  lea     r8, aCreatetunnel_0; "CreateTunnel"
0x180002bf7  lea     rdx, aEnteredS; "Entered: %s"
0x180002bfe  lea     rcx, [rsp+868h+var_838]
0x180002c03  call    FormatRRASErrorString
0x180002c08  cmp     cs:byte_1800167C1, bl
0x180002c0e  jge     short loc_180002C28
0x180002c10  lea     r8, [rsp+868h+var_838]
0x180002c15  lea     rdx, RasVpnIkeApiTraceInfo
0x180002c1c  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180002c23  call    McTemplateU0z_EventWriteTransfer
0x180002c28  test    r14, r14
0x180002c2b  jz      loc_180002D23
0x180002c31  test    rdi, rdi
0x180002c34  jz      loc_180002D23
0x180002c3a  movzx   eax, word ptr [rdi]
0x180002c3d  cmp     ax, [rdi+14h]
0x180002c41  jnz     loc_180002CF6
0x180002c47  cmp     ax, 2
0x180002c4b  jz      short loc_180002C57
0x180002c4d  cmp     ax, 17h
0x180002c51  jnz     loc_180002CF6
0x180002c57  call    InitializeVpnIkeRpcClient
0x180002c5c  mov     [rsp+868h+var_848], eax
0x180002c60  test    eax, eax
0x180002c62  jnz     loc_180002D4E
0x180002c68  mov     r9, r15
0x180002c6b  mov     r8, rdi
0x180002c6e  mov     rdx, r14
0x180002c71  mov     rcx, cs:Binding
0x180002c78  call    VpnikeCreateTunnel
0x180002c7d  mov     [rsp+868h+var_848], eax
0x180002c81  mov     eax, [rsp+868h+var_848]
0x180002c85  test    eax, eax
0x180002c87  jz      short loc_180002CB4
0x180002c89  mov     rcx, cs:WPP_GLOBAL_Control
0x180002c90  cmp     rcx, rsi
0x180002c93  jz      short loc_180002CB4
0x180002c95  test    byte ptr [rcx+1Ch], 1
0x180002c99  jz      short loc_180002CB4
0x180002c9b  cmp     byte ptr [rcx+19h], 2
0x180002c9f  jb      short loc_180002CB4
0x180002ca1  mov     rcx, [rcx+10h]
0x180002ca5  mov     edx, 11h
0x180002caa  mov     r9d, [rsp+868h+var_848]
0x180002caf  call    WPP_SF_D
0x180002cb4  jmp     loc_180002D4E
0x180002cb9  lea     rax, WPP_GLOBAL_Control
0x180002cc0  mov     rcx, cs:WPP_GLOBAL_Control
0x180002cc7  cmp     rcx, rax
0x180002cca  jz      short loc_180002CEB
0x180002ccc  test    byte ptr [rcx+1Ch], 1
0x180002cd0  jz      short loc_180002CEB
0x180002cd2  cmp     byte ptr [rcx+19h], 2
0x180002cd6  jb      short loc_180002CEB
0x180002cd8  mov     edx, 12h
0x180002cdd  mov     r9d, [rsp+868h+var_848]
0x180002ce2  mov     rcx, [rcx+10h]
0x180002ce6  call    WPP_SF_D
0x180002ceb  lea     rsi, WPP_GLOBAL_Control
0x180002cf2  xor     ebx, ebx
0x180002cf4  jmp     short loc_180002D4E
0x180002cf6  mov     [rsp+868h+var_848], 0Dh
0x180002cfe  test    cs:byte_1800167C1, 40h
0x180002d05  jz      short loc_180002D4E
0x180002d07  lea     r8, aInvalidDataVpn; "Invalid Data: vpnIkeTunnelParams"
0x180002d0e  lea     rdx, RasVpnIkeApiTraceError
0x180002d15  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180002d1c  call    McTemplateU0z_EventWriteTransfer
0x180002d21  jmp     short loc_180002D4E
0x180002d23  test    cs:byte_1800167C1, 40h
0x180002d2a  jz      short loc_180002D46
0x180002d2c  lea     r8, aInvalidParamet; "Invalid Parameter"
0x180002d33  lea     rdx, RasVpnIkeApiTraceError
0x180002d3a  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180002d41  call    McTemplateU0z_EventWriteTransfer
0x180002d46  mov     [rsp+868h+var_848], 57h ; 'W'
0x180002d4e  test    cs:byte_1800167C1, 80h
0x180002d55  jz      short loc_180002D94
0x180002d57  mov     word ptr [rsp+868h+var_838], bx
0x180002d5c  lea     r8, aCreatetunnel_0; "CreateTunnel"
0x180002d63  lea     rdx, aLeavingS; "Leaving: %s"
0x180002d6a  lea     rcx, [rsp+868h+var_838]
0x180002d6f  call    FormatRRASErrorString
0x180002d74  cmp     cs:byte_1800167C1, bl
0x180002d7a  jge     short loc_180002D94
0x180002d7c  lea     r8, [rsp+868h+var_838]
0x180002d81  lea     rdx, RasVpnIkeApiTraceInfo
0x180002d88  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180002d8f  call    McTemplateU0z_EventWriteTransfer
0x180002d94  mov     rcx, cs:WPP_GLOBAL_Control
0x180002d9b  cmp     rcx, rsi
0x180002d9e  jz      short loc_180002DBF
0x180002da0  test    byte ptr [rcx+1Ch], 1
0x180002da4  jz      short loc_180002DBF
0x180002da6  cmp     byte ptr [rcx+19h], 6
0x180002daa  jb      short loc_180002DBF
0x180002dac  mov     edx, 13h
0x180002db1  mov     r9d, [rsp+868h+var_848]
0x180002db6  mov     rcx, [rcx+10h]
0x180002dba  call    WPP_SF_D
0x180002dbf  mov     eax, [rsp+868h+var_848]
0x180002dc3  mov     rcx, [rsp+868h+var_38]
0x180002dcb  xor     rcx, rsp; StackCookie
0x180002dce  call    __security_check_cookie
0x180002dd3  add     rsp, 840h
0x180002dda  pop     r15
0x180002ddc  pop     r14
0x180002dde  pop     rdi
0x180002ddf  pop     rsi
0x180002de0  pop     rbx
0x180002de1  retn
0x18000d406  push    rbp
0x18000d408  sub     rsp, 20h
0x18000d40c  mov     rbp, rdx
0x18000d40f  mov     rax, [rcx]
0x18000d412  mov     ecx, [rax]
0x18000d414  mov     [rbp+20h], ecx
0x18000d417  mov     ecx, [rbp+20h]; ExceptionCode
0x18000d41a  call    cs:__imp_I_RpcExceptionFilter
0x18000d420  nop
0x18000d421  add     rsp, 20h
0x18000d425  pop     rbp
0x18000d426  retn
```
