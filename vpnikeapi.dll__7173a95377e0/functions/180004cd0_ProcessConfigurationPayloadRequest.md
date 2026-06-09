# ProcessConfigurationPayloadRequest

- ea: `0x180004cd0`
- end: `0x180004f79`
- name: `ProcessConfigurationPayloadRequest`
- size: `681`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180004420`
- `0x180004cd0`
- `0x1800063d0`
- `0x180006414`
- `0x180006aa8`
- `0x18000c330`
- `0x18000ce1c`
- `0x18000cfbe`
- `0x18000cff0`

## string_xrefs

- `0x180004d50`: `ProcessConfigurationPayloadRequest`
- `0x180004ef3`: `ProcessConfigurationPayloadRequest`

## pseudocode

```c
__int64 __fastcall ProcessConfigurationPayloadRequest(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v6; // r8
  unsigned int v7; // eax
  unsigned int v9; // [rsp+20h] [rbp-848h]
  int v10; // [rsp+30h] [rbp-838h] BYREF
  _BYTE v11[2044]; // [rsp+34h] [rbp-834h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_I(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, a3, a1);
  }
  v10 = 0;
  memset_0(v11, 0, sizeof(v11));
  if ( byte_1800167C1 < 0 )
  {
    LOWORD(v10) = 0;
    FormatRRASErrorString((wchar_t *)&v10, L"Entered: %s", L"ProcessConfigurationPayloadRequest");
    if ( byte_1800167C1 < 0 )
      McTemplateU0z_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (const EVENT_DESCRIPTOR *)RasVpnIkeApiTraceInfo,
        (const wchar_t *)&v10);
  }
  if ( a1 && a2 && a3 )
  {
    v7 = InitializeVpnIkeRpcClient();
    v9 = v7;
    if ( v7 )
    {
      if ( (byte_1800167C1 & 0x40) != 0 )
      {
        LOWORD(v10) = 0;
        FormatRRASErrorString((wchar_t *)&v10, L"InitializeVpnIkeRpcClient failed: %d", v7);
        if ( (byte_1800167C1 & 0x40) != 0 )
          McTemplateU0z_EventWriteTransfer(
            &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (const EVENT_DESCRIPTOR *)RasVpnIkeApiTraceError,
            (const wchar_t *)&v10);
      }
    }
    else
    {
      v9 = VpnikeProcessCfgPayloadRequest(Binding, a1, a2, a3);
      if ( v9 )
      {
        if ( (byte_1800167C1 & 0x40) != 0 )
        {
          LOWORD(v10) = 0;
          FormatRRASErrorString((wchar_t *)&v10, L"VpnikeProcessCfgPayloadRequest RPC failed: %d", v9);
          if ( (byte_1800167C1 & 0x40) != 0 )
            McTemplateU0z_EventWriteTransfer(
              &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (const EVENT_DESCRIPTOR *)RasVpnIkeApiTraceError,
              (const wchar_t *)&v10);
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
    v9 = 87;
  }
  if ( byte_1800167C1 < 0 )
  {
    LOWORD(v10) = 0;
    FormatRRASErrorString((wchar_t *)&v10, L"Leaving: %s", L"ProcessConfigurationPayloadRequest");
    if ( byte_1800167C1 < 0 )
      McTemplateU0z_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (const EVENT_DESCRIPTOR *)RasVpnIkeApiTraceInfo,
        (const wchar_t *)&v10);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, v6, v9);
  }
  return v9;
}

```

## disassembly

```asm
0x180004cd0  push    rbx
0x180004cd2  push    rsi
0x180004cd3  push    rdi
0x180004cd4  push    r14
0x180004cd6  push    r15
0x180004cd8  sub     rsp, 840h
0x180004cdf  mov     rax, cs:__security_cookie
0x180004ce6  xor     rax, rsp
0x180004ce9  mov     [rsp+868h+var_38], rax
0x180004cf1  mov     r15, r8
0x180004cf4  mov     r14, rdx
0x180004cf7  mov     rdi, rcx
0x180004cfa  lea     rsi, WPP_GLOBAL_Control
0x180004d01  mov     rcx, cs:WPP_GLOBAL_Control
0x180004d08  cmp     rcx, rsi
0x180004d0b  jz      short loc_180004D2A
0x180004d0d  test    byte ptr [rcx+1Ch], 1
0x180004d11  jz      short loc_180004D2A
0x180004d13  cmp     byte ptr [rcx+19h], 6
0x180004d17  jb      short loc_180004D2A
0x180004d19  mov     edx, 2Ch ; ','
0x180004d1e  mov     r9, rdi
0x180004d21  mov     rcx, [rcx+10h]
0x180004d25  call    WPP_SF_I
0x180004d2a  xor     ebx, ebx
0x180004d2c  mov     [rsp+868h+var_838], ebx
0x180004d30  xor     edx, edx; Val
0x180004d32  mov     r8d, 7FCh; Size
0x180004d38  lea     rcx, [rsp+868h+var_834]; void *
0x180004d3d  call    memset_0
0x180004d42  test    cs:byte_1800167C1, 80h
0x180004d49  jz      short loc_180004D88
0x180004d4b  mov     word ptr [rsp+868h+var_838], bx
0x180004d50  lea     r8, aProcessconfigu_1; "ProcessConfigurationPayloadRequest"
0x180004d57  lea     rdx, aEnteredS; "Entered: %s"
0x180004d5e  lea     rcx, [rsp+868h+var_838]
0x180004d63  call    FormatRRASErrorString
0x180004d68  cmp     cs:byte_1800167C1, bl
0x180004d6e  jge     short loc_180004D88
0x180004d70  lea     r8, [rsp+868h+var_838]
0x180004d75  lea     rdx, RasVpnIkeApiTraceInfo
0x180004d7c  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180004d83  call    McTemplateU0z_EventWriteTransfer
0x180004d88  test    rdi, rdi
0x180004d8b  jz      loc_180004EBA
0x180004d91  test    r14, r14
0x180004d94  jz      loc_180004EBA
0x180004d9a  test    r15, r15
0x180004d9d  jz      loc_180004EBA
0x180004da3  call    InitializeVpnIkeRpcClient
0x180004da8  mov     [rsp+868h+var_848], eax
0x180004dac  test    eax, eax
0x180004dae  jz      short loc_180004E00
0x180004db0  test    cs:byte_1800167C1, 40h
0x180004db7  jz      loc_180004EE5
0x180004dbd  mov     word ptr [rsp+868h+var_838], bx
0x180004dc2  mov     r8d, eax
0x180004dc5  lea     rdx, aInitializevpni_0; "InitializeVpnIkeRpcClient failed: %d"
0x180004dcc  lea     rcx, [rsp+868h+var_838]
0x180004dd1  call    FormatRRASErrorString
0x180004dd6  test    cs:byte_1800167C1, 40h
0x180004ddd  jz      loc_180004EE5
0x180004de3  lea     r8, [rsp+868h+var_838]
0x180004de8  lea     rdx, RasVpnIkeApiTraceError
0x180004def  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180004df6  call    McTemplateU0z_EventWriteTransfer
0x180004dfb  jmp     loc_180004EE5
0x180004e00  mov     r9, r15
0x180004e03  mov     r8, r14
0x180004e06  mov     rdx, rdi
0x180004e09  mov     rcx, cs:Binding
0x180004e10  call    VpnikeProcessCfgPayloadRequest
0x180004e15  mov     [rsp+868h+var_848], eax
0x180004e19  mov     eax, [rsp+868h+var_848]
0x180004e1d  test    eax, eax
0x180004e1f  jz      short loc_180004E66
0x180004e21  test    cs:byte_1800167C1, 40h
0x180004e28  jz      short loc_180004E66
0x180004e2a  mov     word ptr [rsp+868h+var_838], bx
0x180004e2f  mov     r8d, [rsp+868h+var_848]
0x180004e34  lea     rdx, aVpnikeprocessc_1; "VpnikeProcessCfgPayloadRequest RPC fail"...
0x180004e3b  lea     rcx, [rsp+868h+var_838]
0x180004e40  call    FormatRRASErrorString
0x180004e45  test    cs:byte_1800167C1, 40h
0x180004e4c  jz      short loc_180004E66
0x180004e4e  lea     r8, [rsp+868h+var_838]
0x180004e53  lea     rdx, RasVpnIkeApiTraceError
0x180004e5a  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180004e61  call    McTemplateU0z_EventWriteTransfer
0x180004e66  jmp     short loc_180004EE5
0x180004e68  test    cs:byte_1800167C1, 40h
0x180004e6f  jz      short loc_180004EAF
0x180004e71  xor     eax, eax
0x180004e73  mov     word ptr [rsp+868h+var_838], ax
0x180004e78  mov     r8d, [rsp+868h+var_848]
0x180004e7d  lea     rdx, aVpnikeprocessc_0; "VpnikeProcessCfgPayloadRequest RPC exce"...
0x180004e84  lea     rcx, [rsp+868h+var_838]
0x180004e89  call    FormatRRASErrorString
0x180004e8e  test    cs:byte_1800167C1, 40h
0x180004e95  jz      short loc_180004EAF
0x180004e97  lea     r8, [rsp+868h+var_838]
0x180004e9c  lea     rdx, RasVpnIkeApiTraceError
0x180004ea3  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180004eaa  call    McTemplateU0z_EventWriteTransfer
0x180004eaf  lea     rsi, WPP_GLOBAL_Control
0x180004eb6  xor     ebx, ebx
0x180004eb8  jmp     short loc_180004EE5
0x180004eba  test    cs:byte_1800167C1, 40h
0x180004ec1  jz      short loc_180004EDD
0x180004ec3  lea     r8, aInvalidParamet; "Invalid Parameter"
0x180004eca  lea     rdx, RasVpnIkeApiTraceError
0x180004ed1  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180004ed8  call    McTemplateU0z_EventWriteTransfer
0x180004edd  mov     [rsp+868h+var_848], 57h ; 'W'
0x180004ee5  test    cs:byte_1800167C1, 80h
0x180004eec  jz      short loc_180004F2B
0x180004eee  mov     word ptr [rsp+868h+var_838], bx
0x180004ef3  lea     r8, aProcessconfigu_1; "ProcessConfigurationPayloadRequest"
0x180004efa  lea     rdx, aLeavingS; "Leaving: %s"
0x180004f01  lea     rcx, [rsp+868h+var_838]
0x180004f06  call    FormatRRASErrorString
0x180004f0b  cmp     cs:byte_1800167C1, bl
0x180004f11  jge     short loc_180004F2B
0x180004f13  lea     r8, [rsp+868h+var_838]
0x180004f18  lea     rdx, RasVpnIkeApiTraceInfo
0x180004f1f  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180004f26  call    McTemplateU0z_EventWriteTransfer
0x180004f2b  mov     rcx, cs:WPP_GLOBAL_Control
0x180004f32  cmp     rcx, rsi
0x180004f35  jz      short loc_180004F56
0x180004f37  test    byte ptr [rcx+1Ch], 1
0x180004f3b  jz      short loc_180004F56
0x180004f3d  cmp     byte ptr [rcx+19h], 6
0x180004f41  jb      short loc_180004F56
0x180004f43  mov     edx, 2Dh ; '-'
0x180004f48  mov     r9d, [rsp+868h+var_848]
0x180004f4d  mov     rcx, [rcx+10h]
0x180004f51  call    WPP_SF_D
0x180004f56  mov     eax, [rsp+868h+var_848]
0x180004f5a  mov     rcx, [rsp+868h+var_38]
0x180004f62  xor     rcx, rsp; StackCookie
0x180004f65  call    __security_check_cookie
0x180004f6a  add     rsp, 840h
0x180004f71  pop     r15
0x180004f73  pop     r14
0x180004f75  pop     rdi
0x180004f76  pop     rsi
0x180004f77  pop     rbx
0x180004f78  retn
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
