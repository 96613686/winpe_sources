# GetOptionalIDrPayload

- ea: `0x180003b80`
- end: `0x180003e20`
- name: `GetOptionalIDrPayload`
- size: `672`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x180003b80`
- `0x180004420`
- `0x1800063d0`
- `0x180006414`
- `0x18000694c`
- `0x18000c330`
- `0x18000ce1c`
- `0x18000cfbe`
- `0x18000cff0`

## string_xrefs

- `0x180003cd6`: `VpnikeCreateOptionalIDrPayload RPC failed: %d`
- `0x180003d1f`: `VpnikeCreateOptionalIDrPayload RPC exception: %d`

## pseudocode

```c
__int64 __fastcall GetOptionalIDrPayload(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v5; // r8
  unsigned int v6; // eax
  unsigned int OptionalIDrPayload; // [rsp+20h] [rbp-838h]
  int v9; // [rsp+30h] [rbp-828h] BYREF
  _BYTE v10[2044]; // [rsp+34h] [rbp-824h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_I(*((_QWORD *)WPP_GLOBAL_Control + 2), 64, a3, a1);
  }
  v9 = 0;
  memset_0(v10, 0, sizeof(v10));
  if ( byte_1800167C1 < 0 )
  {
    LOWORD(v9) = 0;
    FormatRRASErrorString((wchar_t *)&v9, L"Entered: %s", L"GetOptionalIDrPayload");
    if ( byte_1800167C1 < 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeApiTraceInfo, &v9);
  }
  if ( a1 && a2 )
  {
    v6 = InitializeVpnIkeRpcClient();
    OptionalIDrPayload = v6;
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
      OptionalIDrPayload = VpnikeCreateOptionalIDrPayload(Binding, a1, a2);
      if ( OptionalIDrPayload )
      {
        if ( (byte_1800167C1 & 0x40) != 0 )
        {
          LOWORD(v9) = 0;
          FormatRRASErrorString((wchar_t *)&v9, L"VpnikeCreateOptionalIDrPayload RPC failed: %d", OptionalIDrPayload);
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
        L"GetOptionalIDrPayload: Invalid Parameter");
    OptionalIDrPayload = 87;
  }
  if ( byte_1800167C1 < 0 )
  {
    LOWORD(v9) = 0;
    FormatRRASErrorString((wchar_t *)&v9, L"Leaving: %s", L"GetOptionalIDrPayload");
    if ( byte_1800167C1 < 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeApiTraceInfo, &v9);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 65, v5, OptionalIDrPayload);
  }
  return OptionalIDrPayload;
}

```

## disassembly

```asm
0x180003b80  mov     [rsp+arg_10], rbx
0x180003b85  push    rsi
0x180003b86  push    rdi
0x180003b87  push    r14
0x180003b89  sub     rsp, 840h
0x180003b90  mov     rax, cs:__security_cookie
0x180003b97  xor     rax, rsp
0x180003b9a  mov     [rsp+858h+var_28], rax
0x180003ba2  mov     r14, rdx
0x180003ba5  mov     rdi, rcx
0x180003ba8  lea     rsi, WPP_GLOBAL_Control
0x180003baf  mov     rcx, cs:WPP_GLOBAL_Control
0x180003bb6  cmp     rcx, rsi
0x180003bb9  jz      short loc_180003BD8
0x180003bbb  test    byte ptr [rcx+1Ch], 1
0x180003bbf  jz      short loc_180003BD8
0x180003bc1  cmp     byte ptr [rcx+19h], 6
0x180003bc5  jb      short loc_180003BD8
0x180003bc7  mov     edx, 40h ; '@'
0x180003bcc  mov     r9, rdi
0x180003bcf  mov     rcx, [rcx+10h]
0x180003bd3  call    WPP_SF_I
0x180003bd8  xor     ebx, ebx
0x180003bda  mov     [rsp+858h+var_828], ebx
0x180003bde  xor     edx, edx; Val
0x180003be0  mov     r8d, 7FCh; Size
0x180003be6  lea     rcx, [rsp+858h+var_824]; void *
0x180003beb  call    memset_0
0x180003bf0  test    cs:byte_1800167C1, 80h
0x180003bf7  jz      short loc_180003C36
0x180003bf9  mov     word ptr [rsp+858h+var_828], bx
0x180003bfe  lea     r8, aGetoptionalidr_1; "GetOptionalIDrPayload"
0x180003c05  lea     rdx, aEnteredS; "Entered: %s"
0x180003c0c  lea     rcx, [rsp+858h+var_828]
0x180003c11  call    FormatRRASErrorString
0x180003c16  cmp     cs:byte_1800167C1, bl
0x180003c1c  jge     short loc_180003C36
0x180003c1e  lea     r8, [rsp+858h+var_828]
0x180003c23  lea     rdx, RasVpnIkeApiTraceInfo
0x180003c2a  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180003c31  call    McTemplateU0z_EventWriteTransfer
0x180003c36  test    rdi, rdi
0x180003c39  jz      loc_180003D5C
0x180003c3f  test    r14, r14
0x180003c42  jz      loc_180003D5C
0x180003c48  call    InitializeVpnIkeRpcClient
0x180003c4d  mov     [rsp+858h+var_838], eax
0x180003c51  test    eax, eax
0x180003c53  jz      short loc_180003CA5
0x180003c55  test    cs:byte_1800167C1, 40h
0x180003c5c  jz      loc_180003D87
0x180003c62  mov     word ptr [rsp+858h+var_828], bx
0x180003c67  mov     r8d, eax
0x180003c6a  lea     rdx, aInitializevpni_0; "InitializeVpnIkeRpcClient failed: %d"
0x180003c71  lea     rcx, [rsp+858h+var_828]
0x180003c76  call    FormatRRASErrorString
0x180003c7b  test    cs:byte_1800167C1, 40h
0x180003c82  jz      loc_180003D87
0x180003c88  lea     r8, [rsp+858h+var_828]
0x180003c8d  lea     rdx, RasVpnIkeApiTraceError
0x180003c94  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180003c9b  call    McTemplateU0z_EventWriteTransfer
0x180003ca0  jmp     loc_180003D87
0x180003ca5  mov     r8, r14
0x180003ca8  mov     rdx, rdi
0x180003cab  mov     rcx, cs:Binding
0x180003cb2  call    VpnikeCreateOptionalIDrPayload
0x180003cb7  mov     [rsp+858h+var_838], eax
0x180003cbb  mov     eax, [rsp+858h+var_838]
0x180003cbf  test    eax, eax
0x180003cc1  jz      short loc_180003D08
0x180003cc3  test    cs:byte_1800167C1, 40h
0x180003cca  jz      short loc_180003D08
0x180003ccc  mov     word ptr [rsp+858h+var_828], bx
0x180003cd1  mov     r8d, [rsp+858h+var_838]
0x180003cd6  lea     rdx, aVpnikecreateop; "VpnikeCreateOptionalIDrPayload RPC fail"...
0x180003cdd  lea     rcx, [rsp+858h+var_828]
0x180003ce2  call    FormatRRASErrorString
0x180003ce7  test    cs:byte_1800167C1, 40h
0x180003cee  jz      short loc_180003D08
0x180003cf0  lea     r8, [rsp+858h+var_828]
0x180003cf5  lea     rdx, RasVpnIkeApiTraceError
0x180003cfc  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180003d03  call    McTemplateU0z_EventWriteTransfer
0x180003d08  jmp     short loc_180003D87
0x180003d0a  test    cs:byte_1800167C1, 40h
0x180003d11  jz      short loc_180003D51
0x180003d13  xor     eax, eax
0x180003d15  mov     word ptr [rsp+858h+var_828], ax
0x180003d1a  mov     r8d, [rsp+858h+var_838]
0x180003d1f  lea     rdx, aVpnikecreateop_0; "VpnikeCreateOptionalIDrPayload RPC exce"...
0x180003d26  lea     rcx, [rsp+858h+var_828]
0x180003d2b  call    FormatRRASErrorString
0x180003d30  test    cs:byte_1800167C1, 40h
0x180003d37  jz      short loc_180003D51
0x180003d39  lea     r8, [rsp+858h+var_828]
0x180003d3e  lea     rdx, RasVpnIkeApiTraceError
0x180003d45  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180003d4c  call    McTemplateU0z_EventWriteTransfer
0x180003d51  lea     rsi, WPP_GLOBAL_Control
0x180003d58  xor     ebx, ebx
0x180003d5a  jmp     short loc_180003D87
0x180003d5c  test    cs:byte_1800167C1, 40h
0x180003d63  jz      short loc_180003D7F
0x180003d65  lea     r8, aGetoptionalidr_0; "GetOptionalIDrPayload: Invalid Paramete"...
0x180003d6c  lea     rdx, RasVpnIkeApiTraceError
0x180003d73  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180003d7a  call    McTemplateU0z_EventWriteTransfer
0x180003d7f  mov     [rsp+858h+var_838], 57h ; 'W'
0x180003d87  test    cs:byte_1800167C1, 80h
0x180003d8e  jz      short loc_180003DCD
0x180003d90  mov     word ptr [rsp+858h+var_828], bx
0x180003d95  lea     r8, aGetoptionalidr_1; "GetOptionalIDrPayload"
0x180003d9c  lea     rdx, aLeavingS; "Leaving: %s"
0x180003da3  lea     rcx, [rsp+858h+var_828]
0x180003da8  call    FormatRRASErrorString
0x180003dad  cmp     cs:byte_1800167C1, bl
0x180003db3  jge     short loc_180003DCD
0x180003db5  lea     r8, [rsp+858h+var_828]
0x180003dba  lea     rdx, RasVpnIkeApiTraceInfo
0x180003dc1  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180003dc8  call    McTemplateU0z_EventWriteTransfer
0x180003dcd  mov     rcx, cs:WPP_GLOBAL_Control
0x180003dd4  cmp     rcx, rsi
0x180003dd7  jz      short loc_180003DF8
0x180003dd9  test    byte ptr [rcx+1Ch], 1
0x180003ddd  jz      short loc_180003DF8
0x180003ddf  cmp     byte ptr [rcx+19h], 6
0x180003de3  jb      short loc_180003DF8
0x180003de5  mov     edx, 41h ; 'A'
0x180003dea  mov     r9d, [rsp+858h+var_838]
0x180003def  mov     rcx, [rcx+10h]
0x180003df3  call    WPP_SF_D
0x180003df8  mov     eax, [rsp+858h+var_838]
0x180003dfc  mov     rcx, [rsp+858h+var_28]
0x180003e04  xor     rcx, rsp; StackCookie
0x180003e07  call    __security_check_cookie
0x180003e0c  mov     rbx, [rsp+858h+arg_10]
0x180003e14  add     rsp, 840h
0x180003e1b  pop     r14
0x180003e1d  pop     rdi
0x180003e1e  pop     rsi
0x180003e1f  retn
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
