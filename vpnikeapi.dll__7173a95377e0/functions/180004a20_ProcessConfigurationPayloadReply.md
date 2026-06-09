# ProcessConfigurationPayloadReply

- ea: `0x180004a20`
- end: `0x180004cc0`
- name: `ProcessConfigurationPayloadReply`
- size: `672`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180004420`
- `0x180004a20`
- `0x1800063d0`
- `0x180006414`
- `0x180006a78`
- `0x18000c330`
- `0x18000ce1c`
- `0x18000cfbe`
- `0x18000cff0`

## string_xrefs

- `0x180004a9e`: `ProcessConfigurationPayloadReply`
- `0x180004c35`: `ProcessConfigurationPayloadReply`

## pseudocode

```c
__int64 __fastcall ProcessConfigurationPayloadReply(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v5; // r8
  unsigned int v6; // eax
  unsigned int v8; // [rsp+20h] [rbp-838h]
  int v9; // [rsp+30h] [rbp-828h] BYREF
  _BYTE v10[2044]; // [rsp+34h] [rbp-824h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_I(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, a3, a1);
  }
  v9 = 0;
  memset_0(v10, 0, sizeof(v10));
  if ( byte_1800167C1 < 0 )
  {
    LOWORD(v9) = 0;
    FormatRRASErrorString((wchar_t *)&v9, L"Entered: %s", L"ProcessConfigurationPayloadReply");
    if ( byte_1800167C1 < 0 )
      McTemplateU0z_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (const EVENT_DESCRIPTOR *)RasVpnIkeApiTraceInfo,
        (const wchar_t *)&v9);
  }
  if ( a1 && a2 )
  {
    v6 = InitializeVpnIkeRpcClient();
    v8 = v6;
    if ( v6 )
    {
      if ( (byte_1800167C1 & 0x40) != 0 )
      {
        LOWORD(v9) = 0;
        FormatRRASErrorString((wchar_t *)&v9, L"InitializeVpnIkeRpcClient failed: %d", v6);
        if ( (byte_1800167C1 & 0x40) != 0 )
          McTemplateU0z_EventWriteTransfer(
            &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (const EVENT_DESCRIPTOR *)RasVpnIkeApiTraceError,
            (const wchar_t *)&v9);
      }
    }
    else
    {
      v8 = VpnikeProcessCfgPayloadReply(Binding, a1, a2);
      if ( v8 )
      {
        if ( (byte_1800167C1 & 0x40) != 0 )
        {
          LOWORD(v9) = 0;
          FormatRRASErrorString((wchar_t *)&v9, L"VpnikeProcessCfgPayloadReply RPC failed: %d", v8);
          if ( (byte_1800167C1 & 0x40) != 0 )
            McTemplateU0z_EventWriteTransfer(
              &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (const EVENT_DESCRIPTOR *)RasVpnIkeApiTraceError,
              (const wchar_t *)&v9);
        }
      }
    }
  }
  else
  {
    if ( (byte_1800167C1 & 0x40) != 0 )
      McTemplateU0z_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (const EVENT_DESCRIPTOR *)RasVpnIkeApiTraceError,
        L"Invalid Parameter");
    v8 = 87;
  }
  if ( byte_1800167C1 < 0 )
  {
    LOWORD(v9) = 0;
    FormatRRASErrorString((wchar_t *)&v9, L"Leaving: %s", L"ProcessConfigurationPayloadReply");
    if ( byte_1800167C1 < 0 )
      McTemplateU0z_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (const EVENT_DESCRIPTOR *)RasVpnIkeApiTraceInfo,
        (const wchar_t *)&v9);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, v5, v8);
  }
  return v8;
}

```

## disassembly

```asm
0x180004a20  mov     [rsp+arg_10], rbx
0x180004a25  push    rsi
0x180004a26  push    rdi
0x180004a27  push    r14
0x180004a29  sub     rsp, 840h
0x180004a30  mov     rax, cs:__security_cookie
0x180004a37  xor     rax, rsp
0x180004a3a  mov     [rsp+858h+var_28], rax
0x180004a42  mov     rsi, rdx
0x180004a45  mov     rdi, rcx
0x180004a48  lea     r14, WPP_GLOBAL_Control
0x180004a4f  mov     rcx, cs:WPP_GLOBAL_Control
0x180004a56  cmp     rcx, r14
0x180004a59  jz      short loc_180004A78
0x180004a5b  test    byte ptr [rcx+1Ch], 1
0x180004a5f  jz      short loc_180004A78
0x180004a61  cmp     byte ptr [rcx+19h], 6
0x180004a65  jb      short loc_180004A78
0x180004a67  mov     edx, 2Ah ; '*'
0x180004a6c  mov     r9, rdi
0x180004a6f  mov     rcx, [rcx+10h]
0x180004a73  call    WPP_SF_I
0x180004a78  xor     ebx, ebx
0x180004a7a  mov     [rsp+858h+var_828], ebx
0x180004a7e  xor     edx, edx; Val
0x180004a80  mov     r8d, 7FCh; Size
0x180004a86  lea     rcx, [rsp+858h+var_824]; void *
0x180004a8b  call    memset_0
0x180004a90  test    cs:byte_1800167C1, 80h
0x180004a97  jz      short loc_180004AD6
0x180004a99  mov     word ptr [rsp+858h+var_828], bx
0x180004a9e  lea     r8, aProcessconfigu_2; "ProcessConfigurationPayloadReply"
0x180004aa5  lea     rdx, aEnteredS; "Entered: %s"
0x180004aac  lea     rcx, [rsp+858h+var_828]
0x180004ab1  call    FormatRRASErrorString
0x180004ab6  cmp     cs:byte_1800167C1, bl
0x180004abc  jge     short loc_180004AD6
0x180004abe  lea     r8, [rsp+858h+var_828]
0x180004ac3  lea     rdx, RasVpnIkeApiTraceInfo
0x180004aca  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180004ad1  call    McTemplateU0z_EventWriteTransfer
0x180004ad6  test    rdi, rdi
0x180004ad9  jz      loc_180004BFC
0x180004adf  test    rsi, rsi
0x180004ae2  jz      loc_180004BFC
0x180004ae8  call    InitializeVpnIkeRpcClient
0x180004aed  mov     [rsp+858h+var_838], eax
0x180004af1  test    eax, eax
0x180004af3  jz      short loc_180004B45
0x180004af5  test    cs:byte_1800167C1, 40h
0x180004afc  jz      loc_180004C27
0x180004b02  mov     word ptr [rsp+858h+var_828], bx
0x180004b07  mov     r8d, eax
0x180004b0a  lea     rdx, aInitializevpni_0; "InitializeVpnIkeRpcClient failed: %d"
0x180004b11  lea     rcx, [rsp+858h+var_828]
0x180004b16  call    FormatRRASErrorString
0x180004b1b  test    cs:byte_1800167C1, 40h
0x180004b22  jz      loc_180004C27
0x180004b28  lea     r8, [rsp+858h+var_828]
0x180004b2d  lea     rdx, RasVpnIkeApiTraceError
0x180004b34  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180004b3b  call    McTemplateU0z_EventWriteTransfer
0x180004b40  jmp     loc_180004C27
0x180004b45  mov     r8, rsi
0x180004b48  mov     rdx, rdi
0x180004b4b  mov     rcx, cs:Binding
0x180004b52  call    VpnikeProcessCfgPayloadReply
0x180004b57  mov     [rsp+858h+var_838], eax
0x180004b5b  mov     eax, [rsp+858h+var_838]
0x180004b5f  test    eax, eax
0x180004b61  jz      short loc_180004BA8
0x180004b63  test    cs:byte_1800167C1, 40h
0x180004b6a  jz      short loc_180004BA8
0x180004b6c  mov     word ptr [rsp+858h+var_828], bx
0x180004b71  mov     r8d, [rsp+858h+var_838]
0x180004b76  lea     rdx, aVpnikeprocessc; "VpnikeProcessCfgPayloadReply RPC failed"...
0x180004b7d  lea     rcx, [rsp+858h+var_828]
0x180004b82  call    FormatRRASErrorString
0x180004b87  test    cs:byte_1800167C1, 40h
0x180004b8e  jz      short loc_180004BA8
0x180004b90  lea     r8, [rsp+858h+var_828]
0x180004b95  lea     rdx, RasVpnIkeApiTraceError
0x180004b9c  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180004ba3  call    McTemplateU0z_EventWriteTransfer
0x180004ba8  jmp     short loc_180004C27
0x180004baa  test    cs:byte_1800167C1, 40h
0x180004bb1  jz      short loc_180004BF1
0x180004bb3  xor     eax, eax
0x180004bb5  mov     word ptr [rsp+858h+var_828], ax
0x180004bba  mov     r8d, [rsp+858h+var_838]
0x180004bbf  lea     rdx, aVpnikeprocessc_2; "VpnikeProcessCfgPayloadReply RPC except"...
0x180004bc6  lea     rcx, [rsp+858h+var_828]
0x180004bcb  call    FormatRRASErrorString
0x180004bd0  test    cs:byte_1800167C1, 40h
0x180004bd7  jz      short loc_180004BF1
0x180004bd9  lea     r8, [rsp+858h+var_828]
0x180004bde  lea     rdx, RasVpnIkeApiTraceError
0x180004be5  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180004bec  call    McTemplateU0z_EventWriteTransfer
0x180004bf1  lea     r14, WPP_GLOBAL_Control
0x180004bf8  xor     ebx, ebx
0x180004bfa  jmp     short loc_180004C27
0x180004bfc  test    cs:byte_1800167C1, 40h
0x180004c03  jz      short loc_180004C1F
0x180004c05  lea     r8, aInvalidParamet; "Invalid Parameter"
0x180004c0c  lea     rdx, RasVpnIkeApiTraceError
0x180004c13  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180004c1a  call    McTemplateU0z_EventWriteTransfer
0x180004c1f  mov     [rsp+858h+var_838], 57h ; 'W'
0x180004c27  test    cs:byte_1800167C1, 80h
0x180004c2e  jz      short loc_180004C6D
0x180004c30  mov     word ptr [rsp+858h+var_828], bx
0x180004c35  lea     r8, aProcessconfigu_2; "ProcessConfigurationPayloadReply"
0x180004c3c  lea     rdx, aLeavingS; "Leaving: %s"
0x180004c43  lea     rcx, [rsp+858h+var_828]
0x180004c48  call    FormatRRASErrorString
0x180004c4d  cmp     cs:byte_1800167C1, bl
0x180004c53  jge     short loc_180004C6D
0x180004c55  lea     r8, [rsp+858h+var_828]
0x180004c5a  lea     rdx, RasVpnIkeApiTraceInfo
0x180004c61  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180004c68  call    McTemplateU0z_EventWriteTransfer
0x180004c6d  mov     rcx, cs:WPP_GLOBAL_Control
0x180004c74  cmp     rcx, r14
0x180004c77  jz      short loc_180004C98
0x180004c79  test    byte ptr [rcx+1Ch], 1
0x180004c7d  jz      short loc_180004C98
0x180004c7f  cmp     byte ptr [rcx+19h], 6
0x180004c83  jb      short loc_180004C98
0x180004c85  mov     edx, 2Bh ; '+'
0x180004c8a  mov     r9d, [rsp+858h+var_838]
0x180004c8f  mov     rcx, [rcx+10h]
0x180004c93  call    WPP_SF_D
0x180004c98  mov     eax, [rsp+858h+var_838]
0x180004c9c  mov     rcx, [rsp+858h+var_28]
0x180004ca4  xor     rcx, rsp; StackCookie
0x180004ca7  call    __security_check_cookie
0x180004cac  mov     rbx, [rsp+858h+arg_10]
0x180004cb4  add     rsp, 840h
0x180004cbb  pop     r14
0x180004cbd  pop     rdi
0x180004cbe  pop     rsi
0x180004cbf  retn
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
