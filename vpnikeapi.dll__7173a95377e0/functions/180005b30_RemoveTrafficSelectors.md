# RemoveTrafficSelectors

- ea: `0x180005b30`
- end: `0x180005dd5`
- name: `RemoveTrafficSelectors`
- size: `677`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x180004420`
- `0x180005b30`
- `0x1800063d0`
- `0x180006458`
- `0x180006bc8`
- `0x18000c330`
- `0x18000ce1c`
- `0x18000cfbe`
- `0x18000cff0`

## import_xrefs

- `RPCRT4!I_RpcExceptionFilter` at `0x18000d442`
- `RPCRT4!I_RpcExceptionFilter` at `0x18000d442`

## string_xrefs

- `0x180005bb3`: `RemoveTrafficSelectors`
- `0x180005d4a`: `RemoveTrafficSelectors`
- `0x180005c8b`: `VpnikeRemoveTs RPC failed: %d`
- `0x180005cd4`: `VpnikeRemoveTs RPC exception: %d`

## pseudocode

```c
__int64 __fastcall RemoveTrafficSelectors(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v5; // r8
  unsigned int v6; // eax
  unsigned int v8; // [rsp+30h] [rbp-838h]
  int v9; // [rsp+40h] [rbp-828h] BYREF
  _BYTE v10[2044]; // [rsp+44h] [rbp-824h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_II(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, a3, a1, a2);
  }
  v9 = 0;
  memset_0(v10, 0, sizeof(v10));
  if ( byte_1800167C1 < 0 )
  {
    LOWORD(v9) = 0;
    FormatRRASErrorString((wchar_t *)&v9, L"Entered: %s", L"RemoveTrafficSelectors");
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
      v8 = VpnikeRemoveTs(Binding, a1, a2);
      if ( v8 )
      {
        if ( (byte_1800167C1 & 0x40) != 0 )
        {
          LOWORD(v9) = 0;
          FormatRRASErrorString((wchar_t *)&v9, L"VpnikeRemoveTs RPC failed: %d", v8);
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
    FormatRRASErrorString((wchar_t *)&v9, L"Leaving: %s", L"RemoveTrafficSelectors");
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
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, v5, v8);
  }
  return v8;
}

```

## disassembly

```asm
0x180005b30  mov     [rsp+arg_10], rbx
0x180005b35  push    rsi
0x180005b36  push    rdi
0x180005b37  push    r14
0x180005b39  sub     rsp, 850h
0x180005b40  mov     rax, cs:__security_cookie
0x180005b47  xor     rax, rsp
0x180005b4a  mov     [rsp+868h+var_28], rax
0x180005b52  mov     rsi, rdx
0x180005b55  mov     rdi, rcx
0x180005b58  lea     r14, WPP_GLOBAL_Control
0x180005b5f  mov     rcx, cs:WPP_GLOBAL_Control
0x180005b66  cmp     rcx, r14
0x180005b69  jz      short loc_180005B8D
0x180005b6b  test    byte ptr [rcx+1Ch], 1
0x180005b6f  jz      short loc_180005B8D
0x180005b71  cmp     byte ptr [rcx+19h], 6
0x180005b75  jb      short loc_180005B8D
0x180005b77  mov     edx, 37h ; '7'
0x180005b7c  mov     [rsp+868h+var_848], rsi
0x180005b81  mov     r9, rdi
0x180005b84  mov     rcx, [rcx+10h]
0x180005b88  call    WPP_SF_II
0x180005b8d  xor     ebx, ebx
0x180005b8f  mov     [rsp+868h+var_828], ebx
0x180005b93  xor     edx, edx; Val
0x180005b95  mov     r8d, 7FCh; Size
0x180005b9b  lea     rcx, [rsp+868h+var_824]; void *
0x180005ba0  call    memset_0
0x180005ba5  test    cs:byte_1800167C1, 80h
0x180005bac  jz      short loc_180005BEB
0x180005bae  mov     word ptr [rsp+868h+var_828], bx
0x180005bb3  lea     r8, aRemovetraffics_0; "RemoveTrafficSelectors"
0x180005bba  lea     rdx, aEnteredS; "Entered: %s"
0x180005bc1  lea     rcx, [rsp+868h+var_828]
0x180005bc6  call    FormatRRASErrorString
0x180005bcb  cmp     cs:byte_1800167C1, bl
0x180005bd1  jge     short loc_180005BEB
0x180005bd3  lea     r8, [rsp+868h+var_828]
0x180005bd8  lea     rdx, RasVpnIkeApiTraceInfo
0x180005bdf  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180005be6  call    McTemplateU0z_EventWriteTransfer
0x180005beb  test    rdi, rdi
0x180005bee  jz      loc_180005D11
0x180005bf4  test    rsi, rsi
0x180005bf7  jz      loc_180005D11
0x180005bfd  call    InitializeVpnIkeRpcClient
0x180005c02  mov     [rsp+868h+var_838], eax
0x180005c06  test    eax, eax
0x180005c08  jz      short loc_180005C5A
0x180005c0a  test    cs:byte_1800167C1, 40h
0x180005c11  jz      loc_180005D3C
0x180005c17  mov     word ptr [rsp+868h+var_828], bx
0x180005c1c  mov     r8d, eax
0x180005c1f  lea     rdx, aInitializevpni_0; "InitializeVpnIkeRpcClient failed: %d"
0x180005c26  lea     rcx, [rsp+868h+var_828]
0x180005c2b  call    FormatRRASErrorString
0x180005c30  test    cs:byte_1800167C1, 40h
0x180005c37  jz      loc_180005D3C
0x180005c3d  lea     r8, [rsp+868h+var_828]
0x180005c42  lea     rdx, RasVpnIkeApiTraceError
0x180005c49  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180005c50  call    McTemplateU0z_EventWriteTransfer
0x180005c55  jmp     loc_180005D3C
0x180005c5a  mov     r8, rsi
0x180005c5d  mov     rdx, rdi
0x180005c60  mov     rcx, cs:Binding
0x180005c67  call    VpnikeRemoveTs
0x180005c6c  mov     [rsp+868h+var_838], eax
0x180005c70  mov     eax, [rsp+868h+var_838]
0x180005c74  test    eax, eax
0x180005c76  jz      short loc_180005CBD
0x180005c78  test    cs:byte_1800167C1, 40h
0x180005c7f  jz      short loc_180005CBD
0x180005c81  mov     word ptr [rsp+868h+var_828], bx
0x180005c86  mov     r8d, [rsp+868h+var_838]
0x180005c8b  lea     rdx, aVpnikeremovets_0; "VpnikeRemoveTs RPC failed: %d"
0x180005c92  lea     rcx, [rsp+868h+var_828]
0x180005c97  call    FormatRRASErrorString
0x180005c9c  test    cs:byte_1800167C1, 40h
0x180005ca3  jz      short loc_180005CBD
0x180005ca5  lea     r8, [rsp+868h+var_828]
0x180005caa  lea     rdx, RasVpnIkeApiTraceError
0x180005cb1  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180005cb8  call    McTemplateU0z_EventWriteTransfer
0x180005cbd  jmp     short loc_180005D3C
0x180005cbf  test    cs:byte_1800167C1, 40h
0x180005cc6  jz      short loc_180005D06
0x180005cc8  xor     eax, eax
0x180005cca  mov     word ptr [rsp+868h+var_828], ax
0x180005ccf  mov     r8d, [rsp+868h+var_838]
0x180005cd4  lea     rdx, aVpnikeremovets; "VpnikeRemoveTs RPC exception: %d"
0x180005cdb  lea     rcx, [rsp+868h+var_828]
0x180005ce0  call    FormatRRASErrorString
0x180005ce5  test    cs:byte_1800167C1, 40h
0x180005cec  jz      short loc_180005D06
0x180005cee  lea     r8, [rsp+868h+var_828]
0x180005cf3  lea     rdx, RasVpnIkeApiTraceError
0x180005cfa  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180005d01  call    McTemplateU0z_EventWriteTransfer
0x180005d06  lea     r14, WPP_GLOBAL_Control
0x180005d0d  xor     ebx, ebx
0x180005d0f  jmp     short loc_180005D3C
0x180005d11  test    cs:byte_1800167C1, 40h
0x180005d18  jz      short loc_180005D34
0x180005d1a  lea     r8, aInvalidParamet; "Invalid Parameter"
0x180005d21  lea     rdx, RasVpnIkeApiTraceError
0x180005d28  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180005d2f  call    McTemplateU0z_EventWriteTransfer
0x180005d34  mov     [rsp+868h+var_838], 57h ; 'W'
0x180005d3c  test    cs:byte_1800167C1, 80h
0x180005d43  jz      short loc_180005D82
0x180005d45  mov     word ptr [rsp+868h+var_828], bx
0x180005d4a  lea     r8, aRemovetraffics_0; "RemoveTrafficSelectors"
0x180005d51  lea     rdx, aLeavingS; "Leaving: %s"
0x180005d58  lea     rcx, [rsp+868h+var_828]
0x180005d5d  call    FormatRRASErrorString
0x180005d62  cmp     cs:byte_1800167C1, bl
0x180005d68  jge     short loc_180005D82
0x180005d6a  lea     r8, [rsp+868h+var_828]
0x180005d6f  lea     rdx, RasVpnIkeApiTraceInfo
0x180005d76  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180005d7d  call    McTemplateU0z_EventWriteTransfer
0x180005d82  mov     rcx, cs:WPP_GLOBAL_Control
0x180005d89  cmp     rcx, r14
0x180005d8c  jz      short loc_180005DAD
0x180005d8e  test    byte ptr [rcx+1Ch], 1
0x180005d92  jz      short loc_180005DAD
0x180005d94  cmp     byte ptr [rcx+19h], 6
0x180005d98  jb      short loc_180005DAD
0x180005d9a  mov     edx, 38h ; '8'
0x180005d9f  mov     r9d, [rsp+868h+var_838]
0x180005da4  mov     rcx, [rcx+10h]
0x180005da8  call    WPP_SF_D
0x180005dad  mov     eax, [rsp+868h+var_838]
0x180005db1  mov     rcx, [rsp+868h+var_28]
0x180005db9  xor     rcx, rsp; StackCookie
0x180005dbc  call    __security_check_cookie
0x180005dc1  mov     rbx, [rsp+868h+arg_10]
0x180005dc9  add     rsp, 850h
0x180005dd0  pop     r14
0x180005dd2  pop     rdi
0x180005dd3  pop     rsi
0x180005dd4  retn
0x18000d42e  push    rbp
0x18000d430  sub     rsp, 30h
0x18000d434  mov     rbp, rdx
0x18000d437  mov     rax, [rcx]
0x18000d43a  mov     ecx, [rax]
0x18000d43c  mov     [rbp+30h], ecx
0x18000d43f  mov     ecx, [rbp+30h]; ExceptionCode
0x18000d442  call    cs:__imp_I_RpcExceptionFilter
0x18000d448  nop
0x18000d449  add     rsp, 30h
0x18000d44d  pop     rbp
0x18000d44e  retn
```
