# FWUPDATE_HubVendorControlTransferComplete

- ea: `0x140041400`
- end: `0x140041568`
- name: `FWUPDATE_HubVendorControlTransferComplete`
- size: `360`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1400024b8`
- `0x1400025a4`
- `0x140006644`
- `0x14000a53c`
- `0x140033530`
- `0x140041400`
- `0x140045570`

## pseudocode

```c
__int64 __fastcall FWUPDATE_HubVendorControlTransferComplete(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  int v4; // ebx
  int v5; // esi
  int v7; // edx
  __int64 v8; // rcx
  int v9; // ebp
  __int64 v10; // rax
  int v11; // edx
  __int64 v13; // [rsp+20h] [rbp-68h]
  __int64 v14; // [rsp+28h] [rbp-60h]
  int v15; // [rsp+28h] [rbp-60h]
  __int64 v16; // [rsp+30h] [rbp-58h]
  __int64 v17; // [rsp+40h] [rbp-48h] BYREF
  int v18; // [rsp+48h] [rbp-40h]
  __int64 v19; // [rsp+4Ch] [rbp-3Ch]
  int v20; // [rsp+54h] [rbp-34h]

  v4 = *(_DWORD *)(a3 + 8);
  v5 = *(_DWORD *)(a4 + 844);
  v19 = 0;
  v20 = 0;
  v17 = 24;
  v18 = 0;
  v9 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 1992))(
         WdfDriverGlobals,
         a1,
         &v17);
  if ( v9 < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v10 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, WDFDRIVER__ *, __int64 *))(WdfFunctions_01015 + 1616))(
            WdfDriverGlobals,
            WdfDriverGlobals->Driver,
            off_14006B2C0);
    v15 = v9;
    LOBYTE(v11) = 2;
    WPP_RECORDER_SF_d(*(_QWORD *)(v10 + 64), v11, 2, 59, (__int64)WPP_dde998bf8bb3310d95d4227a99ba80b7_Traceguids, v15);
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
        48,
        (__int64)WPP_2fd11ae104fa34a9334eddada324a17a_Traceguids,
        v4,
        v5);
    }
    if ( (byte_14006ED42 & 2) != 0 )
    {
      LODWORD(v16) = v4;
      LODWORD(v14) = v5;
      LODWORD(v13) = 0;
      McTemplateK0pqqq_EtwWriteTransfer(
        v8,
        (const EVENT_DESCRIPTOR *)USBHUB3_ETW_EVENT_HUB_CONTROL_TRANSFER_ERROR,
        0,
        *(_QWORD *)(a4 + 248),
        v13,
        v14,
        v16);
    }
    if ( (*(_DWORD *)(a4 + 2608) & 2) != 0 )
      HUBMISC_VerifierDbgBreak("HubHwVerifierControlTransferFailure", a4 + 1280);
  }
  return HUBSM_AddEvent(a4 + 1280, ((v4 >> 31) & 0xFFFFFFFC) + 2008);
}

```

## disassembly

```asm
0x140041400  mov     rax, rsp
0x140041403  push    rbx
0x140041404  push    rbp
0x140041405  push    rsi
0x140041406  push    rdi
0x140041407  push    r15
0x140041409  sub     rsp, 60h
0x14004140d  mov     ebx, [r8+8]
0x140041411  mov     rdx, rcx
0x140041414  mov     rcx, cs:WdfDriverGlobals
0x14004141b  lea     r8, [rsp+88h+var_48]
0x140041420  mov     esi, [r9+34Ch]
0x140041427  mov     rdi, r9
0x14004142a  mov     qword ptr [rax-3Ch], 0
0x140041432  mov     dword ptr [rax-34h], 0
0x140041439  mov     qword ptr [rax-48h], 18h
0x140041441  mov     dword ptr [rax-40h], 0
0x140041448  mov     rax, cs:WdfFunctions_01015
0x14004144f  mov     rax, [rax+7C8h]
0x140041456  call    _guard_dispatch_icall
0x14004145b  lea     r15, WPP_RECORDER_INITIALIZED
0x140041462  mov     ebp, eax
0x140041464  test    eax, eax
0x140041466  jns     short loc_1400414BB
0x140041468  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x14004146f  jz      short loc_1400414BB
0x140041471  mov     rcx, cs:WdfFunctions_01015
0x140041478  mov     r8, cs:off_14006B2C0
0x14004147f  mov     rax, [rcx+650h]
0x140041486  mov     rcx, cs:WdfDriverGlobals
0x14004148d  mov     rdx, [rcx]
0x140041490  call    _guard_dispatch_icall
0x140041495  mov     r9d, 3Bh ; ';'
0x14004149b  mov     dword ptr [rsp+88h+var_60], ebp
0x14004149f  lea     rcx, WPP_dde998bf8bb3310d95d4227a99ba80b7_Traceguids
0x1400414a6  mov     [rsp+88h+var_68], rcx
0x1400414ab  mov     rcx, [rax+40h]
0x1400414af  lea     r8d, [r9-39h]
0x1400414b3  mov     dl, r8b
0x1400414b6  call    WPP_RECORDER_SF_d
0x1400414bb  test    ebx, ebx
0x1400414bd  jns     loc_140041544
0x1400414c3  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x1400414ca  jz      short loc_1400414F8
0x1400414cc  mov     rcx, [rdi+9E8h]
0x1400414d3  lea     rax, WPP_2fd11ae104fa34a9334eddada324a17a_Traceguids
0x1400414da  mov     r9d, 30h ; '0'
0x1400414e0  mov     [rsp+88h+var_58], esi
0x1400414e4  mov     dword ptr [rsp+88h+var_60], ebx
0x1400414e8  mov     dl, 2
0x1400414ea  mov     [rsp+88h+var_68], rax
0x1400414ef  lea     r8d, [r9-2Dh]
0x1400414f3  call    WPP_RECORDER_SF_dD
0x1400414f8  test    cs:byte_14006ED42, 2
0x1400414ff  jz      short loc_140041527
0x140041501  mov     r9, [rdi+0F8h]
0x140041508  lea     rdx, USBHUB3_ETW_EVENT_HUB_CONTROL_TRANSFER_ERROR
0x14004150f  mov     [rsp+88h+var_58], ebx
0x140041513  xor     r8d, r8d
0x140041516  mov     dword ptr [rsp+88h+var_60], esi
0x14004151a  mov     dword ptr [rsp+88h+var_68], 0
0x140041522  call    McTemplateK0pqqq_EtwWriteTransfer
0x140041527  mov     eax, [rdi+0A30h]
0x14004152d  test    al, 2
0x14004152f  jz      short loc_140041544
0x140041531  lea     rdx, [rdi+500h]
0x140041538  lea     rcx, aHubhwverifierc; "HubHwVerifierControlTransferFailure"
0x14004153f  call    HUBMISC_VerifierDbgBreak
0x140041544  sar     ebx, 1Fh
0x140041547  lea     rcx, [rdi+500h]
0x14004154e  and     ebx, 0FFFFFFFCh
0x140041551  lea     edx, [rbx+7D8h]
0x140041557  call    HUBSM_AddEvent
0x14004155c  add     rsp, 60h
0x140041560  pop     r15
0x140041562  pop     rdi
0x140041563  pop     rsi
0x140041564  pop     rbp
0x140041565  pop     rbx
0x140041566  retn
```
