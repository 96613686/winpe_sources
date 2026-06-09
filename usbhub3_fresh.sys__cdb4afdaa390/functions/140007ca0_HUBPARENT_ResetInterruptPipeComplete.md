# HUBPARENT_ResetInterruptPipeComplete

- ea: `0x140007ca0`
- end: `0x140007e08`
- name: `HUBPARENT_ResetInterruptPipeComplete`
- size: `360`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x1400024b8`
- `0x1400025a4`
- `0x140006644`
- `0x140007ca0`
- `0x14000a53c`
- `0x140033530`
- `0x140045570`

## pseudocode

```c
__int64 __fastcall HUBPARENT_ResetInterruptPipeComplete(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  int v4; // ebx
  int v5; // esi
  int v7; // edx
  __int64 v8; // rcx
  int v9; // ebp
  __int64 v10; // r8
  __int64 v11; // r9
  __int64 v12; // rax
  int v13; // edx
  __int64 v15; // [rsp+20h] [rbp-68h]
  __int64 v16; // [rsp+28h] [rbp-60h]
  int v17; // [rsp+28h] [rbp-60h]
  __int64 v18; // [rsp+30h] [rbp-58h]
  __int64 v19; // [rsp+40h] [rbp-48h] BYREF
  int v20; // [rsp+48h] [rbp-40h]
  __int64 v21; // [rsp+4Ch] [rbp-3Ch]
  int v22; // [rsp+54h] [rbp-34h]

  v4 = *(_DWORD *)(a3 + 8);
  v5 = *(_DWORD *)(a4 + 844);
  v21 = 0;
  v22 = 0;
  v19 = 24;
  v20 = 0;
  v9 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 1992))(
         WdfDriverGlobals,
         a1,
         &v19);
  if ( v9 < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v12 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, WDFDRIVER__ *, __int64 *))(WdfFunctions_01015 + 1616))(
            WdfDriverGlobals,
            WdfDriverGlobals->Driver,
            off_14006B2C0);
    v17 = v9;
    LOBYTE(v13) = 2;
    WPP_RECORDER_SF_d(*(_QWORD *)(v12 + 64), v13, 2, 59, (__int64)WPP_dde998bf8bb3310d95d4227a99ba80b7_Traceguids, v17);
  }
  if ( v4 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v7) = 2;
      WPP_RECORDER_SF_dD(
        *(_QWORD *)(a4 + 2536),
        v7,
        3,
        16,
        (__int64)WPP_7215ce29f44d3be25ae6d82bbfc5240b_Traceguids,
        v4,
        v5);
    }
    if ( (byte_14006ED42 & 2) != 0 )
    {
      LODWORD(v18) = v4;
      LODWORD(v16) = v5;
      LODWORD(v15) = 0;
      McTemplateK0pqqq_EtwWriteTransfer(
        v8,
        (const EVENT_DESCRIPTOR *)USBHUB3_ETW_EVENT_HUB_CONTROL_TRANSFER_ERROR,
        0,
        *(_QWORD *)(a4 + 248),
        v15,
        v16,
        v18);
    }
    if ( (*(_DWORD *)(a4 + 2608) & 2) != 0 )
      HUBMISC_VerifierDbgBreak("HubHwVerifierControlTransferFailure", a4 + 1280, v10, v11);
  }
  return HUBSM_AddEvent(a4 + 1280, ((v4 >> 31) & 0xFFFFFFFC) + 2016);
}

```

## disassembly

```asm
0x140007ca0  mov     rax, rsp
0x140007ca3  push    rbx
0x140007ca4  push    rbp
0x140007ca5  push    rsi
0x140007ca6  push    rdi
0x140007ca7  push    r15
0x140007ca9  sub     rsp, 60h
0x140007cad  mov     ebx, [r8+8]
0x140007cb1  mov     rdx, rcx
0x140007cb4  mov     rcx, cs:WdfDriverGlobals
0x140007cbb  lea     r8, [rsp+88h+var_48]
0x140007cc0  mov     esi, [r9+34Ch]
0x140007cc7  mov     rdi, r9
0x140007cca  mov     qword ptr [rax-3Ch], 0
0x140007cd2  mov     dword ptr [rax-34h], 0
0x140007cd9  mov     qword ptr [rax-48h], 18h
0x140007ce1  mov     dword ptr [rax-40h], 0
0x140007ce8  mov     rax, cs:WdfFunctions_01015
0x140007cef  mov     rax, [rax+7C8h]
0x140007cf6  call    _guard_dispatch_icall
0x140007cfb  lea     r15, WPP_RECORDER_INITIALIZED
0x140007d02  mov     ebp, eax
0x140007d04  test    eax, eax
0x140007d06  jns     short loc_140007D5B
0x140007d08  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x140007d0f  jz      short loc_140007D5B
0x140007d11  mov     rcx, cs:WdfFunctions_01015
0x140007d18  mov     r8, cs:off_14006B2C0
0x140007d1f  mov     rax, [rcx+650h]
0x140007d26  mov     rcx, cs:WdfDriverGlobals
0x140007d2d  mov     rdx, [rcx]
0x140007d30  call    _guard_dispatch_icall
0x140007d35  mov     r9d, 3Bh ; ';'
0x140007d3b  mov     dword ptr [rsp+88h+var_60], ebp
0x140007d3f  lea     rcx, WPP_dde998bf8bb3310d95d4227a99ba80b7_Traceguids
0x140007d46  mov     [rsp+88h+var_68], rcx
0x140007d4b  mov     rcx, [rax+40h]
0x140007d4f  lea     r8d, [r9-39h]
0x140007d53  mov     dl, r8b
0x140007d56  call    WPP_RECORDER_SF_d
0x140007d5b  test    ebx, ebx
0x140007d5d  jns     loc_140007DE4
0x140007d63  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x140007d6a  jz      short loc_140007D98
0x140007d6c  mov     rcx, [rdi+9E8h]
0x140007d73  lea     rax, WPP_7215ce29f44d3be25ae6d82bbfc5240b_Traceguids
0x140007d7a  mov     r9d, 10h
0x140007d80  mov     [rsp+88h+var_58], esi
0x140007d84  mov     dword ptr [rsp+88h+var_60], ebx
0x140007d88  mov     dl, 2
0x140007d8a  mov     [rsp+88h+var_68], rax
0x140007d8f  lea     r8d, [r9-0Dh]
0x140007d93  call    WPP_RECORDER_SF_dD
0x140007d98  test    cs:byte_14006ED42, 2
0x140007d9f  jz      short loc_140007DC7
0x140007da1  mov     r9, [rdi+0F8h]
0x140007da8  lea     rdx, USBHUB3_ETW_EVENT_HUB_CONTROL_TRANSFER_ERROR
0x140007daf  mov     [rsp+88h+var_58], ebx
0x140007db3  xor     r8d, r8d
0x140007db6  mov     dword ptr [rsp+88h+var_60], esi
0x140007dba  mov     dword ptr [rsp+88h+var_68], 0
0x140007dc2  call    McTemplateK0pqqq_EtwWriteTransfer
0x140007dc7  mov     eax, [rdi+0A30h]
0x140007dcd  test    al, 2
0x140007dcf  jz      short loc_140007DE4
0x140007dd1  lea     rdx, [rdi+500h]
0x140007dd8  lea     rcx, aHubhwverifierc; "HubHwVerifierControlTransferFailure"
0x140007ddf  call    HUBMISC_VerifierDbgBreak
0x140007de4  sar     ebx, 1Fh
0x140007de7  lea     rcx, [rdi+500h]
0x140007dee  and     ebx, 0FFFFFFFCh
0x140007df1  lea     edx, [rbx+7E0h]
0x140007df7  call    HUBSM_AddEvent
0x140007dfc  add     rsp, 60h
0x140007e00  pop     r15
0x140007e02  pop     rdi
0x140007e03  pop     rsi
0x140007e04  pop     rbp
0x140007e05  pop     rbx
0x140007e06  retn
```
