# HUBHTX_HubControlTransferComplete

- ea: `0x140005200`
- end: `0x140005372`
- name: `HUBHTX_HubControlTransferComplete`
- size: `370`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x1400024b8`
- `0x1400025a4`
- `0x140005200`
- `0x140006644`
- `0x14000a53c`
- `0x140033530`
- `0x140045570`

## pseudocode

```c
__int64 __fastcall HUBHTX_HubControlTransferComplete(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
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
        10,
        (__int64)WPP_70469c384dd13630d566350a6f2705ad_Traceguids,
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
    *(_DWORD *)(a4 + 2612) = 1073872897;
  }
  return HUBSM_AddEvent(a4 + 1280, ((v4 >> 31) & 0xFFFFFFFC) + 2008);
}

```

## disassembly

```asm
0x140005200  mov     rax, rsp
0x140005203  push    rbx
0x140005204  push    rbp
0x140005205  push    rsi
0x140005206  push    rdi
0x140005207  push    r15
0x140005209  sub     rsp, 60h
0x14000520d  mov     ebx, [r8+8]
0x140005211  mov     rdx, rcx
0x140005214  mov     rcx, cs:WdfDriverGlobals
0x14000521b  lea     r8, [rsp+88h+var_48]
0x140005220  mov     esi, [r9+34Ch]
0x140005227  mov     rdi, r9
0x14000522a  mov     qword ptr [rax-3Ch], 0
0x140005232  mov     dword ptr [rax-34h], 0
0x140005239  mov     qword ptr [rax-48h], 18h
0x140005241  mov     dword ptr [rax-40h], 0
0x140005248  mov     rax, cs:WdfFunctions_01015
0x14000524f  mov     rax, [rax+7C8h]
0x140005256  call    _guard_dispatch_icall
0x14000525b  lea     r15, WPP_RECORDER_INITIALIZED
0x140005262  mov     ebp, eax
0x140005264  test    eax, eax
0x140005266  jns     short loc_1400052BB
0x140005268  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x14000526f  jz      short loc_1400052BB
0x140005271  mov     rcx, cs:WdfFunctions_01015
0x140005278  mov     r8, cs:off_14006B2C0
0x14000527f  mov     rax, [rcx+650h]
0x140005286  mov     rcx, cs:WdfDriverGlobals
0x14000528d  mov     rdx, [rcx]
0x140005290  call    _guard_dispatch_icall
0x140005295  mov     r9d, 3Bh ; ';'
0x14000529b  mov     dword ptr [rsp+88h+var_60], ebp
0x14000529f  lea     rcx, WPP_dde998bf8bb3310d95d4227a99ba80b7_Traceguids
0x1400052a6  mov     [rsp+88h+var_68], rcx
0x1400052ab  mov     rcx, [rax+40h]
0x1400052af  lea     r8d, [r9-39h]
0x1400052b3  mov     dl, r8b
0x1400052b6  call    WPP_RECORDER_SF_d
0x1400052bb  test    ebx, ebx
0x1400052bd  jns     loc_14000534E
0x1400052c3  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x1400052ca  jz      short loc_1400052F8
0x1400052cc  mov     rcx, [rdi+9E8h]
0x1400052d3  lea     rax, WPP_70469c384dd13630d566350a6f2705ad_Traceguids
0x1400052da  mov     r9d, 0Ah
0x1400052e0  mov     [rsp+88h+var_58], esi
0x1400052e4  mov     dword ptr [rsp+88h+var_60], ebx
0x1400052e8  mov     dl, 2
0x1400052ea  mov     [rsp+88h+var_68], rax
0x1400052ef  lea     r8d, [r9-7]
0x1400052f3  call    WPP_RECORDER_SF_dD
0x1400052f8  test    cs:byte_14006ED42, 2
0x1400052ff  jz      short loc_140005327
0x140005301  mov     r9, [rdi+0F8h]
0x140005308  lea     rdx, USBHUB3_ETW_EVENT_HUB_CONTROL_TRANSFER_ERROR
0x14000530f  mov     [rsp+88h+var_58], ebx
0x140005313  xor     r8d, r8d
0x140005316  mov     dword ptr [rsp+88h+var_60], esi
0x14000531a  mov     dword ptr [rsp+88h+var_68], 0
0x140005322  call    McTemplateK0pqqq_EtwWriteTransfer
0x140005327  mov     eax, [rdi+0A30h]
0x14000532d  test    al, 2
0x14000532f  jz      short loc_140005344
0x140005331  lea     rdx, [rdi+500h]
0x140005338  lea     rcx, aHubhwverifierc; "HubHwVerifierControlTransferFailure"
0x14000533f  call    HUBMISC_VerifierDbgBreak
0x140005344  mov     dword ptr [rdi+0A34h], 40020001h
0x14000534e  sar     ebx, 1Fh
0x140005351  lea     rcx, [rdi+500h]
0x140005358  and     ebx, 0FFFFFFFCh
0x14000535b  lea     edx, [rbx+7D8h]
0x140005361  call    HUBSM_AddEvent
0x140005366  add     rsp, 60h
0x14000536a  pop     r15
0x14000536c  pop     rdi
0x14000536d  pop     rsi
0x14000536e  pop     rbp
0x14000536f  pop     rbx
0x140005370  retn
```
