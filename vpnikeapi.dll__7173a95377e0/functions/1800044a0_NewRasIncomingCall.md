# NewRasIncomingCall

- ea: `0x1800044a0`
- end: `0x180004777`
- name: `NewRasIncomingCall`
- size: `727`
- prototype: `__int64 __fastcall(__int16 *, __int64)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x180004420`
- `0x1800044a0`
- `0x1800063a0`
- `0x1800063d0`
- `0x180006a48`
- `0x18000c330`
- `0x18000ce1c`
- `0x18000cfbe`
- `0x18000cff0`

## string_xrefs

- `0x18000451b`: `NewRasIncomingCall`
- `0x1800046ec`: `NewRasIncomingCall`
- `0x1800045fd`: `VpnikeNewRasIncomingCall RPC failed: %d`
- `0x180004649`: `VpnikeNewRasIncomingCall RPC exception: %d`

## pseudocode

```c
__int64 __fastcall NewRasIncomingCall(__int16 *a1, __int64 a2)
{
  __int64 v4; // r8
  __int16 v5; // ax
  unsigned int v6; // eax
  const wchar_t *v7; // r8
  unsigned int v9; // [rsp+20h] [rbp-838h]
  int v10; // [rsp+30h] [rbp-828h] BYREF
  _BYTE v11[2044]; // [rsp+34h] [rbp-824h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 60);
  }
  v10 = 0;
  memset_0(v11, 0, sizeof(v11));
  if ( byte_1800167C1 < 0 )
  {
    LOWORD(v10) = 0;
    FormatRRASErrorString((wchar_t *)&v10, L"Entered: %s", L"NewRasIncomingCall");
    if ( byte_1800167C1 < 0 )
      McTemplateU0z_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (const EVENT_DESCRIPTOR *)RasVpnIkeApiTraceInfo,
        (const wchar_t *)&v10);
  }
  if ( a2 && a1 )
  {
    v5 = *a1;
    if ( *a1 == a1[10] && (v5 == 2 || v5 == 23) )
    {
      v6 = InitializeVpnIkeRpcClient();
      v9 = v6;
      if ( v6 )
      {
        if ( (byte_1800167C1 & 0x40) != 0 )
        {
          LOWORD(v10) = 0;
          FormatRRASErrorString((wchar_t *)&v10, L"InitializeVpnIkeRpcClient failed: %d", v6);
          if ( (byte_1800167C1 & 0x40) != 0 )
          {
            v7 = (const wchar_t *)&v10;
LABEL_24:
            McTemplateU0z_EventWriteTransfer(
              &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (const EVENT_DESCRIPTOR *)RasVpnIkeApiTraceError,
              v7);
          }
        }
      }
      else
      {
        v9 = VpnikeNewRasIncomingCall(Binding, a1, a2);
        if ( v9 )
        {
          if ( (byte_1800167C1 & 0x40) != 0 )
          {
            LOWORD(v10) = 0;
            FormatRRASErrorString((wchar_t *)&v10, L"VpnikeNewRasIncomingCall RPC failed: %d", v9);
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
      v9 = 13;
      if ( (byte_1800167C1 & 0x40) != 0 )
      {
        v7 = L"Invalid Data: vpnIkeTunnelParams";
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
    v9 = 87;
  }
  if ( byte_1800167C1 < 0 )
  {
    LOWORD(v10) = 0;
    FormatRRASErrorString((wchar_t *)&v10, L"Leaving: %s", L"NewRasIncomingCall");
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
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, v4, v9);
  }
  return v9;
}

```

## disassembly

```asm
0x1800044a0  mov     [rsp+arg_10], rbx
0x1800044a5  push    rsi
0x1800044a6  push    rdi
0x1800044a7  push    r14
0x1800044a9  sub     rsp, 840h
0x1800044b0  mov     rax, cs:__security_cookie
0x1800044b7  xor     rax, rsp
0x1800044ba  mov     [rsp+858h+var_28], rax
0x1800044c2  mov     rsi, rdx
0x1800044c5  mov     rdi, rcx
0x1800044c8  lea     r14, WPP_GLOBAL_Control
0x1800044cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800044d6  cmp     rcx, r14
0x1800044d9  jz      short loc_1800044F5
0x1800044db  test    byte ptr [rcx+1Ch], 1
0x1800044df  jz      short loc_1800044F5
0x1800044e1  cmp     byte ptr [rcx+19h], 6
0x1800044e5  jb      short loc_1800044F5
0x1800044e7  mov     edx, 3Ch ; '<'
0x1800044ec  mov     rcx, [rcx+10h]
0x1800044f0  call    WPP_SF_
0x1800044f5  xor     ebx, ebx
0x1800044f7  mov     [rsp+858h+var_828], ebx
0x1800044fb  xor     edx, edx; Val
0x1800044fd  mov     r8d, 7FCh; Size
0x180004503  lea     rcx, [rsp+858h+var_824]; void *
0x180004508  call    memset_0
0x18000450d  test    cs:byte_1800167C1, 80h
0x180004514  jz      short loc_180004553
0x180004516  mov     word ptr [rsp+858h+var_828], bx
0x18000451b  lea     r8, aNewrasincoming_0; "NewRasIncomingCall"
0x180004522  lea     rdx, aEnteredS; "Entered: %s"
0x180004529  lea     rcx, [rsp+858h+var_828]
0x18000452e  call    FormatRRASErrorString
0x180004533  cmp     cs:byte_1800167C1, bl
0x180004539  jge     short loc_180004553
0x18000453b  lea     r8, [rsp+858h+var_828]
0x180004540  lea     rdx, RasVpnIkeApiTraceInfo
0x180004547  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000454e  call    McTemplateU0z_EventWriteTransfer
0x180004553  test    rsi, rsi
0x180004556  jz      loc_1800046B3
0x18000455c  test    rdi, rdi
0x18000455f  jz      loc_1800046B3
0x180004565  movzx   eax, word ptr [rdi]
0x180004568  cmp     ax, [rdi+14h]
0x18000456c  jnz     loc_180004686
0x180004572  cmp     ax, 2
0x180004576  jz      short loc_180004582
0x180004578  cmp     ax, 17h
0x18000457c  jnz     loc_180004686
0x180004582  call    InitializeVpnIkeRpcClient
0x180004587  mov     [rsp+858h+var_838], eax
0x18000458b  test    eax, eax
0x18000458d  jz      short loc_1800045CC
0x18000458f  test    cs:byte_1800167C1, 40h
0x180004596  jz      loc_1800046DE
0x18000459c  mov     word ptr [rsp+858h+var_828], bx
0x1800045a1  mov     r8d, eax
0x1800045a4  lea     rdx, aInitializevpni_0; "InitializeVpnIkeRpcClient failed: %d"
0x1800045ab  lea     rcx, [rsp+858h+var_828]
0x1800045b0  call    FormatRRASErrorString
0x1800045b5  test    cs:byte_1800167C1, 40h
0x1800045bc  jz      loc_1800046DE
0x1800045c2  lea     r8, [rsp+858h+var_828]
0x1800045c7  jmp     loc_18000469E
0x1800045cc  mov     r8, rsi
0x1800045cf  mov     rdx, rdi
0x1800045d2  mov     rcx, cs:Binding
0x1800045d9  call    VpnikeNewRasIncomingCall
0x1800045de  mov     [rsp+858h+var_838], eax
0x1800045e2  mov     eax, [rsp+858h+var_838]
0x1800045e6  test    eax, eax
0x1800045e8  jz      short loc_18000462F
0x1800045ea  test    cs:byte_1800167C1, 40h
0x1800045f1  jz      short loc_18000462F
0x1800045f3  mov     word ptr [rsp+858h+var_828], bx
0x1800045f8  mov     r8d, [rsp+858h+var_838]
0x1800045fd  lea     rdx, aVpnikenewrasin_0; "VpnikeNewRasIncomingCall RPC failed: %d"
0x180004604  lea     rcx, [rsp+858h+var_828]
0x180004609  call    FormatRRASErrorString
0x18000460e  test    cs:byte_1800167C1, 40h
0x180004615  jz      short loc_18000462F
0x180004617  lea     r8, [rsp+858h+var_828]
0x18000461c  lea     rdx, RasVpnIkeApiTraceError
0x180004623  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000462a  call    McTemplateU0z_EventWriteTransfer
0x18000462f  jmp     loc_1800046DE
0x180004634  test    cs:byte_1800167C1, 40h
0x18000463b  jz      short loc_18000467B
0x18000463d  xor     eax, eax
0x18000463f  mov     word ptr [rsp+858h+var_828], ax
0x180004644  mov     r8d, [rsp+858h+var_838]
0x180004649  lea     rdx, aVpnikenewrasin; "VpnikeNewRasIncomingCall RPC exception:"...
0x180004650  lea     rcx, [rsp+858h+var_828]
0x180004655  call    FormatRRASErrorString
0x18000465a  test    cs:byte_1800167C1, 40h
0x180004661  jz      short loc_18000467B
0x180004663  lea     r8, [rsp+858h+var_828]
0x180004668  lea     rdx, RasVpnIkeApiTraceError
0x18000466f  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180004676  call    McTemplateU0z_EventWriteTransfer
0x18000467b  lea     r14, WPP_GLOBAL_Control
0x180004682  xor     ebx, ebx
0x180004684  jmp     short loc_1800046DE
0x180004686  mov     [rsp+858h+var_838], 0Dh
0x18000468e  test    cs:byte_1800167C1, 40h
0x180004695  jz      short loc_1800046DE
0x180004697  lea     r8, aInvalidDataVpn; "Invalid Data: vpnIkeTunnelParams"
0x18000469e  lea     rdx, RasVpnIkeApiTraceError
0x1800046a5  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800046ac  call    McTemplateU0z_EventWriteTransfer
0x1800046b1  jmp     short loc_1800046DE
0x1800046b3  test    cs:byte_1800167C1, 40h
0x1800046ba  jz      short loc_1800046D6
0x1800046bc  lea     r8, aInvalidParamet; "Invalid Parameter"
0x1800046c3  lea     rdx, RasVpnIkeApiTraceError
0x1800046ca  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800046d1  call    McTemplateU0z_EventWriteTransfer
0x1800046d6  mov     [rsp+858h+var_838], 57h ; 'W'
0x1800046de  test    cs:byte_1800167C1, 80h
0x1800046e5  jz      short loc_180004724
0x1800046e7  mov     word ptr [rsp+858h+var_828], bx
0x1800046ec  lea     r8, aNewrasincoming_0; "NewRasIncomingCall"
0x1800046f3  lea     rdx, aLeavingS; "Leaving: %s"
0x1800046fa  lea     rcx, [rsp+858h+var_828]
0x1800046ff  call    FormatRRASErrorString
0x180004704  cmp     cs:byte_1800167C1, bl
0x18000470a  jge     short loc_180004724
0x18000470c  lea     r8, [rsp+858h+var_828]
0x180004711  lea     rdx, RasVpnIkeApiTraceInfo
0x180004718  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000471f  call    McTemplateU0z_EventWriteTransfer
0x180004724  mov     rcx, cs:WPP_GLOBAL_Control
0x18000472b  cmp     rcx, r14
0x18000472e  jz      short loc_18000474F
0x180004730  test    byte ptr [rcx+1Ch], 1
0x180004734  jz      short loc_18000474F
0x180004736  cmp     byte ptr [rcx+19h], 6
0x18000473a  jb      short loc_18000474F
0x18000473c  mov     edx, 3Dh ; '='
0x180004741  mov     r9d, [rsp+858h+var_838]
0x180004746  mov     rcx, [rcx+10h]
0x18000474a  call    WPP_SF_D
0x18000474f  mov     eax, [rsp+858h+var_838]
0x180004753  mov     rcx, [rsp+858h+var_28]
0x18000475b  xor     rcx, rsp; StackCookie
0x18000475e  call    __security_check_cookie
0x180004763  mov     rbx, [rsp+858h+arg_10]
0x18000476b  add     rsp, 840h
0x180004772  pop     r14
0x180004774  pop     rdi
0x180004775  pop     rsi
0x180004776  retn
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
