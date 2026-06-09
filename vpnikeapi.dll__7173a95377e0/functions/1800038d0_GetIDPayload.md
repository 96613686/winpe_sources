# GetIDPayload

- ea: `0x1800038d0`
- end: `0x180003b70`
- name: `GetIDPayload`
- size: `672`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x1800038d0`
- `0x180004420`
- `0x1800063d0`
- `0x180006414`
- `0x18000691c`
- `0x18000c330`
- `0x18000ce1c`
- `0x18000cfbe`
- `0x18000cff0`

## string_xrefs

- `0x180003a26`: `VpnikeCreateIDPayload RPC failed: %d`
- `0x180003a6f`: `VpnikeCreateIDPayload RPC exception: %d`

## pseudocode

```c
__int64 __fastcall GetIDPayload(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v5; // r8
  unsigned int v6; // eax
  unsigned int IDPayload; // [rsp+20h] [rbp-838h]
  int v9; // [rsp+30h] [rbp-828h] BYREF
  _BYTE v10[2044]; // [rsp+34h] [rbp-824h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_I(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, a3, a1);
  }
  v9 = 0;
  memset_0(v10, 0, sizeof(v10));
  if ( byte_1800167C1 < 0 )
  {
    LOWORD(v9) = 0;
    FormatRRASErrorString((wchar_t *)&v9, L"Entered: %s", L"GetIDPayload");
    if ( byte_1800167C1 < 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeApiTraceInfo, &v9);
  }
  if ( a1 && a2 )
  {
    v6 = InitializeVpnIkeRpcClient();
    IDPayload = v6;
    if ( v6 )
    {
      if ( (byte_1800167C1 & 0x40) != 0 )
      {
        LOWORD(v9) = 0;
        FormatRRASErrorString((wchar_t *)&v9, L"InitializeVpnIkeRpcClient failed: %d", v6);
        if ( (byte_1800167C1 & 0x40) != 0 )
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeApiTraceError, &v9);
      }
    }
    else
    {
      IDPayload = VpnikeCreateIDPayload(Binding, a1, a2);
      if ( IDPayload )
      {
        if ( (byte_1800167C1 & 0x40) != 0 )
        {
          LOWORD(v9) = 0;
          FormatRRASErrorString((wchar_t *)&v9, L"VpnikeCreateIDPayload RPC failed: %d", IDPayload);
          if ( (byte_1800167C1 & 0x40) != 0 )
            McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeApiTraceError, &v9);
        }
      }
    }
  }
  else
  {
    if ( (byte_1800167C1 & 0x40) != 0 )
      McTemplateU0z_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        RasVpnIkeApiTraceError,
        L"GetIDPayload: Invalid Parameter");
    IDPayload = 87;
  }
  if ( byte_1800167C1 < 0 )
  {
    LOWORD(v9) = 0;
    FormatRRASErrorString((wchar_t *)&v9, L"Leaving: %s", L"GetIDPayload");
    if ( byte_1800167C1 < 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeApiTraceInfo, &v9);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 63, v5, IDPayload);
  }
  return IDPayload;
}

```

## disassembly

```asm
0x1800038d0  mov     [rsp+arg_10], rbx
0x1800038d5  push    rsi
0x1800038d6  push    rdi
0x1800038d7  push    r14
0x1800038d9  sub     rsp, 840h
0x1800038e0  mov     rax, cs:__security_cookie
0x1800038e7  xor     rax, rsp
0x1800038ea  mov     [rsp+858h+var_28], rax
0x1800038f2  mov     rsi, rdx
0x1800038f5  mov     rdi, rcx
0x1800038f8  lea     r14, WPP_GLOBAL_Control
0x1800038ff  mov     rcx, cs:WPP_GLOBAL_Control
0x180003906  cmp     rcx, r14
0x180003909  jz      short loc_180003928
0x18000390b  test    byte ptr [rcx+1Ch], 1
0x18000390f  jz      short loc_180003928
0x180003911  cmp     byte ptr [rcx+19h], 6
0x180003915  jb      short loc_180003928
0x180003917  mov     edx, 3Eh ; '>'
0x18000391c  mov     r9, rdi
0x18000391f  mov     rcx, [rcx+10h]
0x180003923  call    WPP_SF_I
0x180003928  xor     ebx, ebx
0x18000392a  mov     [rsp+858h+var_828], ebx
0x18000392e  xor     edx, edx; Val
0x180003930  mov     r8d, 7FCh; Size
0x180003936  lea     rcx, [rsp+858h+var_824]; void *
0x18000393b  call    memset_0
0x180003940  test    cs:byte_1800167C1, 80h
0x180003947  jz      short loc_180003986
0x180003949  mov     word ptr [rsp+858h+var_828], bx
0x18000394e  lea     r8, aGetidpayload_0; "GetIDPayload"
0x180003955  lea     rdx, aEnteredS; "Entered: %s"
0x18000395c  lea     rcx, [rsp+858h+var_828]
0x180003961  call    FormatRRASErrorString
0x180003966  cmp     cs:byte_1800167C1, bl
0x18000396c  jge     short loc_180003986
0x18000396e  lea     r8, [rsp+858h+var_828]
0x180003973  lea     rdx, RasVpnIkeApiTraceInfo
0x18000397a  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180003981  call    McTemplateU0z_EventWriteTransfer
0x180003986  test    rdi, rdi
0x180003989  jz      loc_180003AAC
0x18000398f  test    rsi, rsi
0x180003992  jz      loc_180003AAC
0x180003998  call    InitializeVpnIkeRpcClient
0x18000399d  mov     [rsp+858h+var_838], eax
0x1800039a1  test    eax, eax
0x1800039a3  jz      short loc_1800039F5
0x1800039a5  test    cs:byte_1800167C1, 40h
0x1800039ac  jz      loc_180003AD7
0x1800039b2  mov     word ptr [rsp+858h+var_828], bx
0x1800039b7  mov     r8d, eax
0x1800039ba  lea     rdx, aInitializevpni_0; "InitializeVpnIkeRpcClient failed: %d"
0x1800039c1  lea     rcx, [rsp+858h+var_828]
0x1800039c6  call    FormatRRASErrorString
0x1800039cb  test    cs:byte_1800167C1, 40h
0x1800039d2  jz      loc_180003AD7
0x1800039d8  lea     r8, [rsp+858h+var_828]
0x1800039dd  lea     rdx, RasVpnIkeApiTraceError
0x1800039e4  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800039eb  call    McTemplateU0z_EventWriteTransfer
0x1800039f0  jmp     loc_180003AD7
0x1800039f5  mov     r8, rsi
0x1800039f8  mov     rdx, rdi
0x1800039fb  mov     rcx, cs:Binding
0x180003a02  call    VpnikeCreateIDPayload
0x180003a07  mov     [rsp+858h+var_838], eax
0x180003a0b  mov     eax, [rsp+858h+var_838]
0x180003a0f  test    eax, eax
0x180003a11  jz      short loc_180003A58
0x180003a13  test    cs:byte_1800167C1, 40h
0x180003a1a  jz      short loc_180003A58
0x180003a1c  mov     word ptr [rsp+858h+var_828], bx
0x180003a21  mov     r8d, [rsp+858h+var_838]
0x180003a26  lea     rdx, aVpnikecreateid_0; "VpnikeCreateIDPayload RPC failed: %d"
0x180003a2d  lea     rcx, [rsp+858h+var_828]
0x180003a32  call    FormatRRASErrorString
0x180003a37  test    cs:byte_1800167C1, 40h
0x180003a3e  jz      short loc_180003A58
0x180003a40  lea     r8, [rsp+858h+var_828]
0x180003a45  lea     rdx, RasVpnIkeApiTraceError
0x180003a4c  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180003a53  call    McTemplateU0z_EventWriteTransfer
0x180003a58  jmp     short loc_180003AD7
0x180003a5a  test    cs:byte_1800167C1, 40h
0x180003a61  jz      short loc_180003AA1
0x180003a63  xor     eax, eax
0x180003a65  mov     word ptr [rsp+858h+var_828], ax
0x180003a6a  mov     r8d, [rsp+858h+var_838]
0x180003a6f  lea     rdx, aVpnikecreateid; "VpnikeCreateIDPayload RPC exception: %d"
0x180003a76  lea     rcx, [rsp+858h+var_828]
0x180003a7b  call    FormatRRASErrorString
0x180003a80  test    cs:byte_1800167C1, 40h
0x180003a87  jz      short loc_180003AA1
0x180003a89  lea     r8, [rsp+858h+var_828]
0x180003a8e  lea     rdx, RasVpnIkeApiTraceError
0x180003a95  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180003a9c  call    McTemplateU0z_EventWriteTransfer
0x180003aa1  lea     r14, WPP_GLOBAL_Control
0x180003aa8  xor     ebx, ebx
0x180003aaa  jmp     short loc_180003AD7
0x180003aac  test    cs:byte_1800167C1, 40h
0x180003ab3  jz      short loc_180003ACF
0x180003ab5  lea     r8, aGetidpayloadIn; "GetIDPayload: Invalid Parameter"
0x180003abc  lea     rdx, RasVpnIkeApiTraceError
0x180003ac3  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180003aca  call    McTemplateU0z_EventWriteTransfer
0x180003acf  mov     [rsp+858h+var_838], 57h ; 'W'
0x180003ad7  test    cs:byte_1800167C1, 80h
0x180003ade  jz      short loc_180003B1D
0x180003ae0  mov     word ptr [rsp+858h+var_828], bx
0x180003ae5  lea     r8, aGetidpayload_0; "GetIDPayload"
0x180003aec  lea     rdx, aLeavingS; "Leaving: %s"
0x180003af3  lea     rcx, [rsp+858h+var_828]
0x180003af8  call    FormatRRASErrorString
0x180003afd  cmp     cs:byte_1800167C1, bl
0x180003b03  jge     short loc_180003B1D
0x180003b05  lea     r8, [rsp+858h+var_828]
0x180003b0a  lea     rdx, RasVpnIkeApiTraceInfo
0x180003b11  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180003b18  call    McTemplateU0z_EventWriteTransfer
0x180003b1d  mov     rcx, cs:WPP_GLOBAL_Control
0x180003b24  cmp     rcx, r14
0x180003b27  jz      short loc_180003B48
0x180003b29  test    byte ptr [rcx+1Ch], 1
0x180003b2d  jz      short loc_180003B48
0x180003b2f  cmp     byte ptr [rcx+19h], 6
0x180003b33  jb      short loc_180003B48
0x180003b35  mov     edx, 3Fh ; '?'
0x180003b3a  mov     r9d, [rsp+858h+var_838]
0x180003b3f  mov     rcx, [rcx+10h]
0x180003b43  call    WPP_SF_D
0x180003b48  mov     eax, [rsp+858h+var_838]
0x180003b4c  mov     rcx, [rsp+858h+var_28]
0x180003b54  xor     rcx, rsp; StackCookie
0x180003b57  call    __security_check_cookie
0x180003b5c  mov     rbx, [rsp+858h+arg_10]
0x180003b64  add     rsp, 840h
0x180003b6b  pop     r14
0x180003b6d  pop     rdi
0x180003b6e  pop     rsi
0x180003b6f  retn
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
