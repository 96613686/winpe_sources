# TUNNEL_EvtWorkitemPnpInterfaceNotification

- ea: `0x140090ae0`
- end: `0x140090ef0`
- name: `TUNNEL_EvtWorkitemPnpInterfaceNotification`
- size: `1040`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1400024b8`
- `0x14000f648`
- `0x14001c704`
- `0x140041928`
- `0x140041a30`
- `0x140045530`
- `0x140045570`
- `0x140045940`
- `0x140090ae0`
- `0x140091854`

## pseudocode

```c
__int64 __fastcall TUNNEL_EvtWorkitemPnpInterfaceNotification(__int64 a1)
{
  __int64 v2; // rax
  __int64 v3; // rdi
  __int64 v4; // rax
  __int64 v5; // rbx
  NTSTATUS v6; // eax
  int v7; // edx
  int v8; // r8d
  __int64 *v9; // rsi
  int v10; // eax
  int v11; // edx
  int v12; // ecx
  char v13; // r15
  __int64 v14; // rax
  __int64 v15; // rdx
  int v16; // edx
  int v17; // ecx
  int v18; // r8d
  __int64 v20; // [rsp+28h] [rbp-D8h]
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-C0h] BYREF
  struct _UNICODE_STRING v22[9]; // [rsp+50h] [rbp-B0h] BYREF
  char v23; // [rsp+E0h] [rbp-20h] BYREF

  memset(v22, 0, 0x88u);
  DestinationString.Buffer = (wchar_t *)&v23;
  *(_QWORD *)&DestinationString.Length = 0x2000000;
  v2 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 3048))(WdfDriverGlobals, a1);
  v3 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 1616))(
         WdfDriverGlobals,
         v2,
         off_14006B270);
  v4 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 1616))(
         WdfDriverGlobals,
         a1,
         off_14006B0D0);
  v5 = *(_QWORD *)(v4 + 512);
  v6 = RtlUnicodeStringPrintf(&DestinationString, L"%sUSB-%p", v4, *(_QWORD *)(v3 + 24));
  if ( v6 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v7) = 2;
      WPP_RECORDER_SF_d(*(_QWORD *)(v3 + 2536), v7, 3, 16, (__int64)WPP_16d83da310273e0510a3edcc6c2bc223_Traceguids, v6);
    }
LABEL_11:
    *(_DWORD *)(v5 + 24) = 0;
    return (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 1664))(WdfDriverGlobals, a1);
  }
  v9 = (__int64 *)(v5 + 8);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v20 = *v9;
    WPP_RECORDER_SF_qqq(*(_QWORD *)(v3 + 2536), v7, v8, 17);
  }
  memset(v22, 0, 0x88u);
  v22[3] = DestinationString;
  *(_QWORD *)&v22[1].Length = TUNNEL_EvtIoTargetRemoveCanceled;
  v22[0].Buffer = (wchar_t *)TUNNEL_EvtIoTargetQueryRemove;
  v22[1].Buffer = (wchar_t *)TUNNEL_EvtIoTargetRemoveComplete;
  *(_QWORD *)&v22[0].Length = 0x200000088LL;
  *(_DWORD *)&v22[4].Length = 1;
  *(_DWORD *)&v22[5].Length = 64;
  HIDWORD(v22[4].Buffer) = 1;
  v10 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, struct _UNICODE_STRING *))(WdfFunctions_01015 + 1344))(
          WdfDriverGlobals,
          *v9,
          v22);
  v13 = v10;
  if ( v10 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LODWORD(v20) = v10;
      LOBYTE(v11) = 2;
      WPP_RECORDER_SF_d(
        *(_QWORD *)(v3 + 2536),
        v11,
        3,
        18,
        (__int64)WPP_16d83da310273e0510a3edcc6c2bc223_Traceguids,
        v20);
    }
    if ( byte_14006ED43 < 0 )
      McTemplateK0pqhhh_EtwWriteTransfer(
        v12,
        (unsigned int)USBHUB3_ETW_EVENT_USB4_POWER_RELATIONS_FAILURE,
        0,
        *(_QWORD *)(v3 + 248),
        v13,
        *(_WORD *)(v3 + 2480),
        *(_WORD *)(v3 + 2482),
        *(_WORD *)(v3 + 2484));
    goto LABEL_11;
  }
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, _QWORD))(WdfFunctions_01015 + 2504))(
    WdfDriverGlobals,
    *(_QWORD *)(v3 + 2760),
    0);
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, _QWORD))(WdfFunctions_01015 + 2504))(
    WdfDriverGlobals,
    *(_QWORD *)(v5 + 16),
    0);
  if ( *(_DWORD *)(v5 + 24) == 1 )
    *(_DWORD *)(v5 + 24) = 2;
  v14 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 1432))(WdfDriverGlobals, *v9);
  v15 = *v9;
  *(_QWORD *)(v5 + 32) = v14;
  *(_QWORD *)((*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 1616))(
                WdfDriverGlobals,
                v15,
                off_14006B180)
            + 8) = v5;
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01015 + 2512))(
    WdfDriverGlobals,
    *(_QWORD *)(v5 + 16));
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01015 + 2512))(
    WdfDriverGlobals,
    *(_QWORD *)(v3 + 2760));
  TUNNEL_UpdateUsb4HostPowerRelations((_QWORD *)v3, v5);
  if ( (Microsoft_Windows_USB_USBHUB3EnableBits & 4) != 0 )
    McTemplateK0ppp_EtwWriteTransfer(v17, v16, v18, *(_QWORD *)(v3 + 248), *v9, *(_QWORD *)(v5 + 32));
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_qqq(*(_QWORD *)(v3 + 2536), v16, v18, 19);
  return (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 1664))(WdfDriverGlobals, a1);
}

```

## disassembly

```asm
0x140090ae0  mov     [rsp-8+arg_8], rbx
0x140090ae5  mov     [rsp-8+arg_10], rsi
0x140090aea  push    rbp
0x140090aeb  push    rdi
0x140090aec  push    r12
0x140090aee  push    r14
0x140090af0  push    r15
0x140090af2  lea     rbp, [rsp-1F0h]
0x140090afa  sub     rsp, 2F0h
0x140090b01  mov     rax, cs:__security_cookie
0x140090b08  xor     rax, rsp
0x140090b0b  mov     [rbp+210h+var_30], rax
0x140090b12  mov     r12, rcx
0x140090b15  mov     r15d, 88h
0x140090b1b  mov     r8d, r15d; Size
0x140090b1e  lea     rcx, [rsp+310h+var_2C0]; void *
0x140090b23  xor     edx, edx; Val
0x140090b25  call    memset
0x140090b2a  mov     rcx, cs:WdfDriverGlobals
0x140090b31  lea     rax, [rbp+210h+var_230]
0x140090b35  mov     [rsp+310h+DestinationString.Buffer], rax
0x140090b3a  mov     rdx, r12
0x140090b3d  mov     rax, cs:WdfFunctions_01015
0x140090b44  mov     qword ptr [rsp+310h+DestinationString.Length], 2000000h
0x140090b4d  mov     rax, [rax+0BE8h]
0x140090b54  call    _guard_dispatch_icall
0x140090b59  mov     rcx, cs:WdfFunctions_01015
0x140090b60  mov     rdx, rax
0x140090b63  mov     r8, cs:off_14006B270
0x140090b6a  mov     rax, [rcx+650h]
0x140090b71  mov     rcx, cs:WdfDriverGlobals
0x140090b78  call    _guard_dispatch_icall
0x140090b7d  mov     rcx, cs:WdfFunctions_01015
0x140090b84  mov     rdi, rax
0x140090b87  mov     r8, cs:off_14006B0D0
0x140090b8e  mov     rdx, r12
0x140090b91  mov     rax, [rcx+650h]
0x140090b98  mov     rcx, cs:WdfDriverGlobals
0x140090b9f  call    _guard_dispatch_icall
0x140090ba4  mov     r9, [rdi+18h]
0x140090ba8  lea     rdx, aSusbP; "%sUSB-%p"
0x140090baf  mov     r8, rax
0x140090bb2  lea     rcx, [rsp+310h+DestinationString]; DestinationString
0x140090bb7  mov     rbx, [rax+200h]
0x140090bbe  call    RtlUnicodeStringPrintf
0x140090bc3  test    eax, eax
0x140090bc5  jns     short loc_140090C06
0x140090bc7  lea     r14, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140090bce  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140090bd5  jz      loc_140090D5F
0x140090bdb  mov     rcx, [rdi+9E8h]
0x140090be2  lea     r9d, [r15-78h]
0x140090be6  mov     dword ptr [rsp+310h+var_2E8], eax
0x140090bea  lea     r8d, [r9-0Dh]
0x140090bee  lea     rax, WPP_16d83da310273e0510a3edcc6c2bc223_Traceguids
0x140090bf5  mov     dl, 2
0x140090bf7  mov     [rsp+310h+var_2F0], rax
0x140090bfc  call    WPP_RECORDER_SF_d
0x140090c01  jmp     loc_140090D5F
0x140090c06  lea     r14, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140090c0d  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140090c14  lea     rsi, [rbx+8]
0x140090c18  jz      short loc_140090C42
0x140090c1a  mov     rax, [rbx+20h]
0x140090c1e  mov     r9d, 11h
0x140090c24  mov     rcx, [rdi+9E8h]
0x140090c2b  mov     [rsp+310h+var_2D8], rbx
0x140090c30  mov     [rsp+310h+var_2E0], rax
0x140090c35  mov     rax, [rsi]
0x140090c38  mov     [rsp+310h+var_2E8], rax
0x140090c3d  call    WPP_RECORDER_SF_qqq
0x140090c42  mov     r8, r15; Size
0x140090c45  lea     rcx, [rsp+310h+var_2C0]; void *
0x140090c4a  xor     edx, edx; Val
0x140090c4c  call    memset
0x140090c51  movzx   eax, [rsp+310h+DestinationString.Length]
0x140090c56  lea     r8, [rsp+310h+var_2C0]
0x140090c5b  mov     rcx, cs:WdfDriverGlobals
0x140090c62  mov     [rbp+210h+var_290], ax
0x140090c66  movzx   eax, [rsp+310h+DestinationString.MaximumLength]
0x140090c6b  mov     [rbp+210h+var_28E], ax
0x140090c6f  mov     eax, dword ptr [rsp+310h+DestinationString+4]
0x140090c73  mov     [rbp+210h+var_28C], eax
0x140090c76  mov     rax, [rsp+310h+DestinationString.Buffer]
0x140090c7b  mov     [rbp+210h+var_288], rax
0x140090c7f  lea     rax, TUNNEL_EvtIoTargetRemoveCanceled
0x140090c86  mov     [rsp+310h+var_2B0], rax
0x140090c8b  lea     rax, TUNNEL_EvtIoTargetQueryRemove
0x140090c92  mov     [rsp+310h+var_2B8], rax
0x140090c97  lea     rax, TUNNEL_EvtIoTargetRemoveComplete
0x140090c9e  mov     [rsp+310h+var_2A8], rax
0x140090ca3  mov     rax, cs:WdfFunctions_01015
0x140090caa  mov     [rsp+310h+var_2C0], r15d
0x140090caf  mov     [rsp+310h+var_2BC], 2
0x140090cb7  mov     [rbp+210h+var_280], 1
0x140090cbe  mov     [rbp+210h+var_270], 40h ; '@'
0x140090cc5  mov     [rbp+210h+var_274], 1
0x140090ccc  mov     rax, [rax+540h]
0x140090cd3  mov     rdx, [rsi]
0x140090cd6  call    _guard_dispatch_icall
0x140090cdb  mov     r15d, eax
0x140090cde  test    eax, eax
0x140090ce0  jns     loc_140090D6B
0x140090ce6  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x140090ced  jz      short loc_140090D17
0x140090cef  mov     rcx, [rdi+9E8h]
0x140090cf6  mov     r9d, 12h
0x140090cfc  mov     dword ptr [rsp+310h+var_2E8], eax
0x140090d00  mov     dl, 2
0x140090d02  lea     rax, WPP_16d83da310273e0510a3edcc6c2bc223_Traceguids
0x140090d09  mov     [rsp+310h+var_2F0], rax
0x140090d0e  lea     r8d, [r9-0Fh]
0x140090d12  call    WPP_RECORDER_SF_d
0x140090d17  cmp     cs:byte_14006ED43, 0
0x140090d1e  jge     short loc_140090D5F
0x140090d20  movzx   eax, word ptr [rdi+9B4h]
0x140090d27  lea     rdx, USBHUB3_ETW_EVENT_USB4_POWER_RELATIONS_FAILURE
0x140090d2e  mov     r9, [rdi+0F8h]
0x140090d35  xor     r8d, r8d
0x140090d38  mov     word ptr [rsp+310h+var_2D8], ax
0x140090d3d  movzx   eax, word ptr [rdi+9B2h]
0x140090d44  mov     word ptr [rsp+310h+var_2E0], ax
0x140090d49  movzx   eax, word ptr [rdi+9B0h]
0x140090d50  mov     word ptr [rsp+310h+var_2E8], ax
0x140090d55  mov     dword ptr [rsp+310h+var_2F0], r15d
0x140090d5a  call    McTemplateK0pqhhh_EtwWriteTransfer
0x140090d5f  mov     dword ptr [rbx+18h], 0
0x140090d66  jmp     loc_140090EA7
0x140090d6b  mov     rax, cs:WdfFunctions_01015
0x140090d72  xor     r8d, r8d
0x140090d75  mov     rdx, [rdi+0AC8h]
0x140090d7c  mov     rcx, cs:WdfDriverGlobals
0x140090d83  mov     rax, [rax+9C8h]
0x140090d8a  call    _guard_dispatch_icall
0x140090d8f  mov     rax, cs:WdfFunctions_01015
0x140090d96  xor     r8d, r8d
0x140090d99  mov     rdx, [rbx+10h]
0x140090d9d  mov     rcx, cs:WdfDriverGlobals
0x140090da4  mov     rax, [rax+9C8h]
0x140090dab  call    _guard_dispatch_icall
0x140090db0  cmp     dword ptr [rbx+18h], 1
0x140090db4  jnz     short loc_140090DBD
0x140090db6  mov     dword ptr [rbx+18h], 2
0x140090dbd  mov     rax, cs:WdfFunctions_01015
0x140090dc4  mov     rdx, [rsi]
0x140090dc7  mov     rcx, cs:WdfDriverGlobals
0x140090dce  mov     rax, [rax+598h]
0x140090dd5  call    _guard_dispatch_icall
0x140090dda  mov     rdx, [rsi]
0x140090ddd  mov     [rbx+20h], rax
0x140090de1  mov     rax, cs:WdfFunctions_01015
0x140090de8  mov     r8, cs:off_14006B180
0x140090def  mov     rcx, cs:WdfDriverGlobals
0x140090df6  mov     rax, [rax+650h]
0x140090dfd  call    _guard_dispatch_icall
0x140090e02  mov     [rax+8], rbx
0x140090e06  mov     rax, cs:WdfFunctions_01015
0x140090e0d  mov     rdx, [rbx+10h]
0x140090e11  mov     rcx, cs:WdfDriverGlobals
0x140090e18  mov     rax, [rax+9D0h]
0x140090e1f  call    _guard_dispatch_icall
0x140090e24  mov     rax, cs:WdfFunctions_01015
0x140090e2b  mov     rdx, [rdi+0AC8h]
0x140090e32  mov     rcx, cs:WdfDriverGlobals
0x140090e39  mov     rax, [rax+9D0h]
0x140090e40  call    _guard_dispatch_icall
0x140090e45  mov     rdx, rbx
0x140090e48  mov     rcx, rdi
0x140090e4b  call    TUNNEL_UpdateUsb4HostPowerRelations
0x140090e50  test    cs:Microsoft_Windows_USB_USBHUB3EnableBits, 4
0x140090e57  jz      short loc_140090E76
0x140090e59  mov     rax, [rbx+20h]
0x140090e5d  mov     r9, [rdi+0F8h]
0x140090e64  mov     [rsp+310h+var_2E8], rax
0x140090e69  mov     rax, [rsi]
0x140090e6c  mov     [rsp+310h+var_2F0], rax
0x140090e71  call    McTemplateK0ppp_EtwWriteTransfer
0x140090e76  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x140090e7d  jz      short loc_140090EA7
0x140090e7f  mov     rax, [rbx+20h]
0x140090e83  mov     r9d, 13h
0x140090e89  mov     rcx, [rdi+9E8h]
0x140090e90  mov     [rsp+310h+var_2D8], rbx
0x140090e95  mov     [rsp+310h+var_2E0], rax
0x140090e9a  mov     rax, [rsi]
0x140090e9d  mov     [rsp+310h+var_2E8], rax
0x140090ea2  call    WPP_RECORDER_SF_qqq
0x140090ea7  mov     rax, cs:WdfFunctions_01015
0x140090eae  mov     rdx, r12
0x140090eb1  mov     rcx, cs:WdfDriverGlobals
0x140090eb8  mov     rax, [rax+680h]
0x140090ebf  call    _guard_dispatch_icall
0x140090ec4  mov     rcx, [rbp+210h+var_30]
0x140090ecb  xor     rcx, rsp; StackCookie
0x140090ece  call    __security_check_cookie
0x140090ed3  lea     r11, [rsp+310h+var_20]
0x140090edb  mov     rbx, [r11+38h]
0x140090edf  mov     rsi, [r11+40h]
0x140090ee3  mov     rsp, r11
0x140090ee6  pop     r15
0x140090ee8  pop     r14
0x140090eea  pop     r12
0x140090eec  pop     rdi
0x140090eed  pop     rbp
0x140090eee  retn
```
