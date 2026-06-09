# UpdateTunnel

- ea: `0x1800060c0`
- end: `0x18000639a`
- name: `UpdateTunnel`
- size: `730`
- prototype: `__int64 __fastcall(__int64, __int16 *, __int64)`
- caller_count: `0`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180004420`
- `0x1800060c0`
- `0x1800063d0`
- `0x180006414`
- `0x180006c28`
- `0x18000c330`
- `0x18000ce1c`
- `0x18000cfbe`
- `0x18000cff0`

## import_xrefs

- `RPCRT4!I_RpcExceptionFilter` at `0x18000d41a`
- `RPCRT4!I_RpcExceptionFilter` at `0x18000d41a`

## string_xrefs

- `0x18000613e`: `UpdateTunnel`
- `0x18000630f`: `UpdateTunnel`
- `0x180006220`: `VpnikeUpdateTunnel RPC failed: %d`
- `0x18000626c`: `VpnikeUpdateTunnel RPC exception: %d`

## pseudocode

```c
__int64 __fastcall UpdateTunnel(__int64 a1, __int16 *a2, __int64 a3)
{
  __int64 v5; // r8
  __int16 v6; // ax
  unsigned int v7; // eax
  const wchar_t *v8; // r8
  unsigned int updated; // [rsp+20h] [rbp-838h]
  int v11; // [rsp+30h] [rbp-828h] BYREF
  _BYTE v12[2044]; // [rsp+34h] [rbp-824h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_I(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, a3, a1);
  }
  v11 = 0;
  memset_0(v12, 0, sizeof(v12));
  if ( byte_1800167C1 < 0 )
  {
    LOWORD(v11) = 0;
    FormatRRASErrorString((wchar_t *)&v11, L"Entered: %s", L"UpdateTunnel");
    if ( byte_1800167C1 < 0 )
      McTemplateU0z_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (const EVENT_DESCRIPTOR *)RasVpnIkeApiTraceInfo,
        (const wchar_t *)&v11);
  }
  if ( a1 && a2 )
  {
    v6 = *a2;
    if ( *a2 == a2[10] && (v6 == 2 || v6 == 23) )
    {
      v7 = InitializeVpnIkeRpcClient();
      updated = v7;
      if ( v7 )
      {
        if ( (byte_1800167C1 & 0x40) != 0 )
        {
          LOWORD(v11) = 0;
          FormatRRASErrorString((wchar_t *)&v11, L"InitializeVpnIkeRpcClient failed: %d", v7);
          if ( (byte_1800167C1 & 0x40) != 0 )
          {
            v8 = (const wchar_t *)&v11;
LABEL_24:
            McTemplateU0z_EventWriteTransfer(
              &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (const EVENT_DESCRIPTOR *)RasVpnIkeApiTraceError,
              v8);
          }
        }
      }
      else
      {
        updated = VpnikeUpdateTunnel(Binding, a1, a2);
        if ( updated )
        {
          if ( (byte_1800167C1 & 0x40) != 0 )
          {
            LOWORD(v11) = 0;
            FormatRRASErrorString((wchar_t *)&v11, L"VpnikeUpdateTunnel RPC failed: %d", updated);
            if ( (byte_1800167C1 & 0x40) != 0 )
              McTemplateU0z_EventWriteTransfer(
                &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                (const EVENT_DESCRIPTOR *)RasVpnIkeApiTraceError,
                (const wchar_t *)&v11);
          }
        }
      }
    }
    else
    {
      updated = 13;
      if ( (byte_1800167C1 & 0x40) != 0 )
      {
        v8 = L"Invalid Data: vpnIkeTunnelParams";
        goto LABEL_24;
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
    updated = 87;
  }
  if ( byte_1800167C1 < 0 )
  {
    LOWORD(v11) = 0;
    FormatRRASErrorString((wchar_t *)&v11, L"Leaving: %s", L"UpdateTunnel");
    if ( byte_1800167C1 < 0 )
      McTemplateU0z_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (const EVENT_DESCRIPTOR *)RasVpnIkeApiTraceInfo,
        (const wchar_t *)&v11);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, v5, updated);
  }
  return updated;
}

```

## disassembly

```asm
0x1800060c0  mov     [rsp+arg_10], rbx
0x1800060c5  push    rsi
0x1800060c6  push    rdi
0x1800060c7  push    r14
0x1800060c9  sub     rsp, 840h
0x1800060d0  mov     rax, cs:__security_cookie
0x1800060d7  xor     rax, rsp
0x1800060da  mov     [rsp+858h+var_28], rax
0x1800060e2  mov     rdi, rdx
0x1800060e5  mov     rsi, rcx
0x1800060e8  lea     r14, WPP_GLOBAL_Control
0x1800060ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1800060f6  cmp     rcx, r14
0x1800060f9  jz      short loc_180006118
0x1800060fb  test    byte ptr [rcx+1Ch], 1
0x1800060ff  jz      short loc_180006118
0x180006101  cmp     byte ptr [rcx+19h], 6
0x180006105  jb      short loc_180006118
0x180006107  mov     edx, 14h
0x18000610c  mov     r9, rsi
0x18000610f  mov     rcx, [rcx+10h]
0x180006113  call    WPP_SF_I
0x180006118  xor     ebx, ebx
0x18000611a  mov     [rsp+858h+var_828], ebx
0x18000611e  xor     edx, edx; Val
0x180006120  mov     r8d, 7FCh; Size
0x180006126  lea     rcx, [rsp+858h+var_824]; void *
0x18000612b  call    memset_0
0x180006130  test    cs:byte_1800167C1, 80h
0x180006137  jz      short loc_180006176
0x180006139  mov     word ptr [rsp+858h+var_828], bx
0x18000613e  lea     r8, aUpdatetunnel_0; "UpdateTunnel"
0x180006145  lea     rdx, aEnteredS; "Entered: %s"
0x18000614c  lea     rcx, [rsp+858h+var_828]
0x180006151  call    FormatRRASErrorString
0x180006156  cmp     cs:byte_1800167C1, bl
0x18000615c  jge     short loc_180006176
0x18000615e  lea     r8, [rsp+858h+var_828]
0x180006163  lea     rdx, RasVpnIkeApiTraceInfo
0x18000616a  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180006171  call    McTemplateU0z_EventWriteTransfer
0x180006176  test    rsi, rsi
0x180006179  jz      loc_1800062D6
0x18000617f  test    rdi, rdi
0x180006182  jz      loc_1800062D6
0x180006188  movzx   eax, word ptr [rdi]
0x18000618b  cmp     ax, [rdi+14h]
0x18000618f  jnz     loc_1800062A9
0x180006195  cmp     ax, 2
0x180006199  jz      short loc_1800061A5
0x18000619b  cmp     ax, 17h
0x18000619f  jnz     loc_1800062A9
0x1800061a5  call    InitializeVpnIkeRpcClient
0x1800061aa  mov     [rsp+858h+var_838], eax
0x1800061ae  test    eax, eax
0x1800061b0  jz      short loc_1800061EF
0x1800061b2  test    cs:byte_1800167C1, 40h
0x1800061b9  jz      loc_180006301
0x1800061bf  mov     word ptr [rsp+858h+var_828], bx
0x1800061c4  mov     r8d, eax
0x1800061c7  lea     rdx, aInitializevpni_0; "InitializeVpnIkeRpcClient failed: %d"
0x1800061ce  lea     rcx, [rsp+858h+var_828]
0x1800061d3  call    FormatRRASErrorString
0x1800061d8  test    cs:byte_1800167C1, 40h
0x1800061df  jz      loc_180006301
0x1800061e5  lea     r8, [rsp+858h+var_828]
0x1800061ea  jmp     loc_1800062C1
0x1800061ef  mov     r8, rdi
0x1800061f2  mov     rdx, rsi
0x1800061f5  mov     rcx, cs:Binding
0x1800061fc  call    VpnikeUpdateTunnel
0x180006201  mov     [rsp+858h+var_838], eax
0x180006205  mov     eax, [rsp+858h+var_838]
0x180006209  test    eax, eax
0x18000620b  jz      short loc_180006252
0x18000620d  test    cs:byte_1800167C1, 40h
0x180006214  jz      short loc_180006252
0x180006216  mov     word ptr [rsp+858h+var_828], bx
0x18000621b  mov     r8d, [rsp+858h+var_838]
0x180006220  lea     rdx, aVpnikeupdatetu_0; "VpnikeUpdateTunnel RPC failed: %d"
0x180006227  lea     rcx, [rsp+858h+var_828]
0x18000622c  call    FormatRRASErrorString
0x180006231  test    cs:byte_1800167C1, 40h
0x180006238  jz      short loc_180006252
0x18000623a  lea     r8, [rsp+858h+var_828]
0x18000623f  lea     rdx, RasVpnIkeApiTraceError
0x180006246  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000624d  call    McTemplateU0z_EventWriteTransfer
0x180006252  jmp     loc_180006301
0x180006257  test    cs:byte_1800167C1, 40h
0x18000625e  jz      short loc_18000629E
0x180006260  xor     eax, eax
0x180006262  mov     word ptr [rsp+858h+var_828], ax
0x180006267  mov     r8d, [rsp+858h+var_838]
0x18000626c  lea     rdx, aVpnikeupdatetu; "VpnikeUpdateTunnel RPC exception: %d"
0x180006273  lea     rcx, [rsp+858h+var_828]
0x180006278  call    FormatRRASErrorString
0x18000627d  test    cs:byte_1800167C1, 40h
0x180006284  jz      short loc_18000629E
0x180006286  lea     r8, [rsp+858h+var_828]
0x18000628b  lea     rdx, RasVpnIkeApiTraceError
0x180006292  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180006299  call    McTemplateU0z_EventWriteTransfer
0x18000629e  lea     r14, WPP_GLOBAL_Control
0x1800062a5  xor     ebx, ebx
0x1800062a7  jmp     short loc_180006301
0x1800062a9  mov     [rsp+858h+var_838], 0Dh
0x1800062b1  test    cs:byte_1800167C1, 40h
0x1800062b8  jz      short loc_180006301
0x1800062ba  lea     r8, aInvalidDataVpn; "Invalid Data: vpnIkeTunnelParams"
0x1800062c1  lea     rdx, RasVpnIkeApiTraceError
0x1800062c8  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800062cf  call    McTemplateU0z_EventWriteTransfer
0x1800062d4  jmp     short loc_180006301
0x1800062d6  test    cs:byte_1800167C1, 40h
0x1800062dd  jz      short loc_1800062F9
0x1800062df  lea     r8, aInvalidParamet; "Invalid Parameter"
0x1800062e6  lea     rdx, RasVpnIkeApiTraceError
0x1800062ed  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800062f4  call    McTemplateU0z_EventWriteTransfer
0x1800062f9  mov     [rsp+858h+var_838], 57h ; 'W'
0x180006301  test    cs:byte_1800167C1, 80h
0x180006308  jz      short loc_180006347
0x18000630a  mov     word ptr [rsp+858h+var_828], bx
0x18000630f  lea     r8, aUpdatetunnel_0; "UpdateTunnel"
0x180006316  lea     rdx, aLeavingS; "Leaving: %s"
0x18000631d  lea     rcx, [rsp+858h+var_828]
0x180006322  call    FormatRRASErrorString
0x180006327  cmp     cs:byte_1800167C1, bl
0x18000632d  jge     short loc_180006347
0x18000632f  lea     r8, [rsp+858h+var_828]
0x180006334  lea     rdx, RasVpnIkeApiTraceInfo
0x18000633b  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180006342  call    McTemplateU0z_EventWriteTransfer
0x180006347  mov     rcx, cs:WPP_GLOBAL_Control
0x18000634e  cmp     rcx, r14
0x180006351  jz      short loc_180006372
0x180006353  test    byte ptr [rcx+1Ch], 1
0x180006357  jz      short loc_180006372
0x180006359  cmp     byte ptr [rcx+19h], 6
0x18000635d  jb      short loc_180006372
0x18000635f  mov     edx, 15h
0x180006364  mov     r9d, [rsp+858h+var_838]
0x180006369  mov     rcx, [rcx+10h]
0x18000636d  call    WPP_SF_D
0x180006372  mov     eax, [rsp+858h+var_838]
0x180006376  mov     rcx, [rsp+858h+var_28]
0x18000637e  xor     rcx, rsp; StackCookie
0x180006381  call    __security_check_cookie
0x180006386  mov     rbx, [rsp+858h+arg_10]
0x18000638e  add     rsp, 840h
0x180006395  pop     r14
0x180006397  pop     rdi
0x180006398  pop     rsi
0x180006399  retn
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
