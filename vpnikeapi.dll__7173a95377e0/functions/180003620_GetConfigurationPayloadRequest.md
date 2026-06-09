# GetConfigurationPayloadRequest

- ea: `0x180003620`
- end: `0x1800038c0`
- name: `GetConfigurationPayloadRequest`
- size: `672`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180003620`
- `0x180004420`
- `0x1800063d0`
- `0x180006414`
- `0x1800069b0`
- `0x18000c330`
- `0x18000ce1c`
- `0x18000cfbe`
- `0x18000cff0`

## string_xrefs

- `0x18000369e`: `GetConfigurationPayloadRequest`
- `0x180003835`: `GetConfigurationPayloadRequest`

## pseudocode

```c
__int64 __fastcall GetConfigurationPayloadRequest(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v5; // r8
  unsigned int v6; // eax
  unsigned int CfgPayloadRequest; // [rsp+20h] [rbp-838h]
  int v9; // [rsp+30h] [rbp-828h] BYREF
  _BYTE v10[2044]; // [rsp+34h] [rbp-824h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_I(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, a3, a1);
  }
  v9 = 0;
  memset_0(v10, 0, sizeof(v10));
  if ( byte_1800167C1 < 0 )
  {
    LOWORD(v9) = 0;
    FormatRRASErrorString((wchar_t *)&v9, L"Entered: %s", L"GetConfigurationPayloadRequest");
    if ( byte_1800167C1 < 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeApiTraceInfo, &v9);
  }
  if ( a1 && a2 )
  {
    v6 = InitializeVpnIkeRpcClient();
    CfgPayloadRequest = v6;
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
      CfgPayloadRequest = VpnikeGetCfgPayloadRequest(Binding, a1, a2);
      if ( CfgPayloadRequest )
      {
        if ( (byte_1800167C1 & 0x40) != 0 )
        {
          LOWORD(v9) = 0;
          FormatRRASErrorString((wchar_t *)&v9, L"VpnikeGetCfgPayloadRequest RPC failed: %d", CfgPayloadRequest);
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
        L"Invalid Parameter");
    CfgPayloadRequest = 87;
  }
  if ( byte_1800167C1 < 0 )
  {
    LOWORD(v9) = 0;
    FormatRRASErrorString((wchar_t *)&v9, L"Leaving: %s", L"GetConfigurationPayloadRequest");
    if ( byte_1800167C1 < 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeApiTraceInfo, &v9);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, v5, CfgPayloadRequest);
  }
  return CfgPayloadRequest;
}

```

## disassembly

```asm
0x180003620  mov     [rsp+arg_10], rbx
0x180003625  push    rsi
0x180003626  push    rdi
0x180003627  push    r14
0x180003629  sub     rsp, 840h
0x180003630  mov     rax, cs:__security_cookie
0x180003637  xor     rax, rsp
0x18000363a  mov     [rsp+858h+var_28], rax
0x180003642  mov     rsi, rdx
0x180003645  mov     rdi, rcx
0x180003648  lea     r14, WPP_GLOBAL_Control
0x18000364f  mov     rcx, cs:WPP_GLOBAL_Control
0x180003656  cmp     rcx, r14
0x180003659  jz      short loc_180003678
0x18000365b  test    byte ptr [rcx+1Ch], 1
0x18000365f  jz      short loc_180003678
0x180003661  cmp     byte ptr [rcx+19h], 6
0x180003665  jb      short loc_180003678
0x180003667  mov     edx, 28h ; '('
0x18000366c  mov     r9, rdi
0x18000366f  mov     rcx, [rcx+10h]
0x180003673  call    WPP_SF_I
0x180003678  xor     ebx, ebx
0x18000367a  mov     [rsp+858h+var_828], ebx
0x18000367e  xor     edx, edx; Val
0x180003680  mov     r8d, 7FCh; Size
0x180003686  lea     rcx, [rsp+858h+var_824]; void *
0x18000368b  call    memset_0
0x180003690  test    cs:byte_1800167C1, 80h
0x180003697  jz      short loc_1800036D6
0x180003699  mov     word ptr [rsp+858h+var_828], bx
0x18000369e  lea     r8, aGetconfigurati_0; "GetConfigurationPayloadRequest"
0x1800036a5  lea     rdx, aEnteredS; "Entered: %s"
0x1800036ac  lea     rcx, [rsp+858h+var_828]
0x1800036b1  call    FormatRRASErrorString
0x1800036b6  cmp     cs:byte_1800167C1, bl
0x1800036bc  jge     short loc_1800036D6
0x1800036be  lea     r8, [rsp+858h+var_828]
0x1800036c3  lea     rdx, RasVpnIkeApiTraceInfo
0x1800036ca  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800036d1  call    McTemplateU0z_EventWriteTransfer
0x1800036d6  test    rdi, rdi
0x1800036d9  jz      loc_1800037FC
0x1800036df  test    rsi, rsi
0x1800036e2  jz      loc_1800037FC
0x1800036e8  call    InitializeVpnIkeRpcClient
0x1800036ed  mov     [rsp+858h+var_838], eax
0x1800036f1  test    eax, eax
0x1800036f3  jz      short loc_180003745
0x1800036f5  test    cs:byte_1800167C1, 40h
0x1800036fc  jz      loc_180003827
0x180003702  mov     word ptr [rsp+858h+var_828], bx
0x180003707  mov     r8d, eax
0x18000370a  lea     rdx, aInitializevpni_0; "InitializeVpnIkeRpcClient failed: %d"
0x180003711  lea     rcx, [rsp+858h+var_828]
0x180003716  call    FormatRRASErrorString
0x18000371b  test    cs:byte_1800167C1, 40h
0x180003722  jz      loc_180003827
0x180003728  lea     r8, [rsp+858h+var_828]
0x18000372d  lea     rdx, RasVpnIkeApiTraceError
0x180003734  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000373b  call    McTemplateU0z_EventWriteTransfer
0x180003740  jmp     loc_180003827
0x180003745  mov     r8, rsi
0x180003748  mov     rdx, rdi
0x18000374b  mov     rcx, cs:Binding
0x180003752  call    VpnikeGetCfgPayloadRequest
0x180003757  mov     [rsp+858h+var_838], eax
0x18000375b  mov     eax, [rsp+858h+var_838]
0x18000375f  test    eax, eax
0x180003761  jz      short loc_1800037A8
0x180003763  test    cs:byte_1800167C1, 40h
0x18000376a  jz      short loc_1800037A8
0x18000376c  mov     word ptr [rsp+858h+var_828], bx
0x180003771  mov     r8d, [rsp+858h+var_838]
0x180003776  lea     rdx, aVpnikegetcfgpa_0; "VpnikeGetCfgPayloadRequest RPC failed: "...
0x18000377d  lea     rcx, [rsp+858h+var_828]
0x180003782  call    FormatRRASErrorString
0x180003787  test    cs:byte_1800167C1, 40h
0x18000378e  jz      short loc_1800037A8
0x180003790  lea     r8, [rsp+858h+var_828]
0x180003795  lea     rdx, RasVpnIkeApiTraceError
0x18000379c  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800037a3  call    McTemplateU0z_EventWriteTransfer
0x1800037a8  jmp     short loc_180003827
0x1800037aa  test    cs:byte_1800167C1, 40h
0x1800037b1  jz      short loc_1800037F1
0x1800037b3  xor     eax, eax
0x1800037b5  mov     word ptr [rsp+858h+var_828], ax
0x1800037ba  mov     r8d, [rsp+858h+var_838]
0x1800037bf  lea     rdx, aVpnikegetcfgpa; "VpnikeGetCfgPayloadRequest RPC exceptio"...
0x1800037c6  lea     rcx, [rsp+858h+var_828]
0x1800037cb  call    FormatRRASErrorString
0x1800037d0  test    cs:byte_1800167C1, 40h
0x1800037d7  jz      short loc_1800037F1
0x1800037d9  lea     r8, [rsp+858h+var_828]
0x1800037de  lea     rdx, RasVpnIkeApiTraceError
0x1800037e5  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800037ec  call    McTemplateU0z_EventWriteTransfer
0x1800037f1  lea     r14, WPP_GLOBAL_Control
0x1800037f8  xor     ebx, ebx
0x1800037fa  jmp     short loc_180003827
0x1800037fc  test    cs:byte_1800167C1, 40h
0x180003803  jz      short loc_18000381F
0x180003805  lea     r8, aInvalidParamet; "Invalid Parameter"
0x18000380c  lea     rdx, RasVpnIkeApiTraceError
0x180003813  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000381a  call    McTemplateU0z_EventWriteTransfer
0x18000381f  mov     [rsp+858h+var_838], 57h ; 'W'
0x180003827  test    cs:byte_1800167C1, 80h
0x18000382e  jz      short loc_18000386D
0x180003830  mov     word ptr [rsp+858h+var_828], bx
0x180003835  lea     r8, aGetconfigurati_0; "GetConfigurationPayloadRequest"
0x18000383c  lea     rdx, aLeavingS; "Leaving: %s"
0x180003843  lea     rcx, [rsp+858h+var_828]
0x180003848  call    FormatRRASErrorString
0x18000384d  cmp     cs:byte_1800167C1, bl
0x180003853  jge     short loc_18000386D
0x180003855  lea     r8, [rsp+858h+var_828]
0x18000385a  lea     rdx, RasVpnIkeApiTraceInfo
0x180003861  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180003868  call    McTemplateU0z_EventWriteTransfer
0x18000386d  mov     rcx, cs:WPP_GLOBAL_Control
0x180003874  cmp     rcx, r14
0x180003877  jz      short loc_180003898
0x180003879  test    byte ptr [rcx+1Ch], 1
0x18000387d  jz      short loc_180003898
0x18000387f  cmp     byte ptr [rcx+19h], 6
0x180003883  jb      short loc_180003898
0x180003885  mov     edx, 29h ; ')'
0x18000388a  mov     r9d, [rsp+858h+var_838]
0x18000388f  mov     rcx, [rcx+10h]
0x180003893  call    WPP_SF_D
0x180003898  mov     eax, [rsp+858h+var_838]
0x18000389c  mov     rcx, [rsp+858h+var_28]
0x1800038a4  xor     rcx, rsp; StackCookie
0x1800038a7  call    __security_check_cookie
0x1800038ac  mov     rbx, [rsp+858h+arg_10]
0x1800038b4  add     rsp, 840h
0x1800038bb  pop     r14
0x1800038bd  pop     rdi
0x1800038be  pop     rsi
0x1800038bf  retn
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
