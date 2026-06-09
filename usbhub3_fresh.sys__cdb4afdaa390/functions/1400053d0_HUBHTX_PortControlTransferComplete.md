# HUBHTX_PortControlTransferComplete

- ea: `0x1400053d0`
- end: `0x140005992`
- name: `HUBHTX_PortControlTransferComplete`
- size: `1474`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x1400024b8`
- `0x1400025a4`
- `0x1400053d0`
- `0x1400065b0`
- `0x140006644`
- `0x140006958`
- `0x140006a90`
- `0x140006bd0`
- `0x140006e44`
- `0x140033530`
- `0x140045570`

## pseudocode

```c
__int64 __fastcall HUBHTX_PortControlTransferComplete(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  int v4; // esi
  __int64 v5; // rdi
  int v6; // ebx
  int v8; // eax
  int v9; // ebx
  int v10; // edx
  int v11; // r8d
  int v12; // r9d
  int v13; // edx
  int v14; // r8d
  int v15; // r9d
  __int16 v16; // ax
  char v17; // cl
  __int16 v18; // ax
  int v19; // ebx
  __int64 v20; // rax
  int v21; // edx
  const char *v23; // [rsp+20h] [rbp-98h]
  int v24; // [rsp+20h] [rbp-98h]
  int v25; // [rsp+20h] [rbp-98h]
  const char *v26; // [rsp+28h] [rbp-90h]
  __int64 v27; // [rsp+70h] [rbp-48h] BYREF
  int v28; // [rsp+78h] [rbp-40h]
  __int64 v29; // [rsp+7Ch] [rbp-3Ch]
  int v30; // [rsp+84h] [rbp-34h]

  v4 = *(_DWORD *)(a3 + 8);
  v5 = a4;
  v6 = *(_DWORD *)(a4 + 44);
  if ( v4 >= 0 )
  {
    if ( !*(_BYTE *)(a4 + 169) )
    {
      v8 = *(_DWORD *)(a4 + 1336) & 0x20;
      if ( v6 == 1 )
      {
        if ( !v8 )
        {
          v26 = "onecore\\drivers\\wdm\\usb\\usb3\\hub\\src\\hubxfer.c";
          LODWORD(v23) = 1699;
          if ( (*(int (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, _QWORD, _QWORD))(WdfFunctions_01015 + 3504))(
                 WdfDriverGlobals,
                 *(_QWORD *)(*(_QWORD *)a4 + 16LL),
                 0,
                 0) >= 0 )
            _InterlockedOr((volatile signed __int32 *)(v5 + 1336), 0x20u);
        }
      }
      else if ( v8 )
      {
        v23 = "onecore\\drivers\\wdm\\usb\\usb3\\hub\\src\\hubxfer.c";
        (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, _QWORD, __int64))(WdfFunctions_01015 + 3512))(
          WdfDriverGlobals,
          *(_QWORD *)(*(_QWORD *)a4 + 16LL),
          0,
          1707);
        _InterlockedAnd((volatile signed __int32 *)(v5 + 1336), 0xFFFFFFDF);
      }
      v9 = **(_DWORD **)(v5 + 80);
      if ( *(_DWORD *)(v5 + 1256) == 5000 )
      {
        if ( (byte_14006ED41 & 0x20) != 0 )
          McTemplateK0pqhh_EtwWriteTransfer(
            *(unsigned __int16 *)(v5 + 200),
            (unsigned int)USBHUB3_ETW_EVENT_30_PORT_STATUS,
            a3,
            *(_QWORD *)(*(_QWORD *)v5 + 248LL),
            *(_WORD *)(v5 + 200),
            *(_WORD *)(v5 + 184),
            *(_WORD *)(v5 + 186));
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(a4) = ((v9 & 8) != 0) + 48;
          WPP_RECORDER_SF_chcccc(
            *(_QWORD *)(v5 + 1432),
            ((v9 & 0x10) != 0) + 48,
            (unsigned __int8)(((v9 & 0x200) != 0) + 48),
            a4,
            (_DWORD)v23,
            (v9 & 1) + 48,
            ((unsigned __int16)v9 >> 5) & 0xF,
            ((v9 & 2) != 0) + 48,
            ((v9 & 0x10) != 0) + 48,
            ((v9 & 0x200) != 0) + 48,
            a4);
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v12) = (BYTE2(v9) >> 7) + 48;
            LOBYTE(v11) = ((v9 & 0x80000) != 0) + 48;
            LOBYTE(v10) = ((v9 & 0x200000) != 0) + 48;
            WPP_RECORDER_SF_cccccc(
              *(_QWORD *)(v5 + 1432),
              v10,
              v11,
              v12,
              v24,
              (BYTE2(v9) & 1) + 48,
              ((v9 & 0x400000) != 0) + 48,
              ((v9 & 0x100000) != 0) + 48,
              v10,
              v11,
              v12);
          }
        }
      }
      else
      {
        if ( (byte_14006ED41 & 0x20) != 0 )
          McTemplateK0pqhh_EtwWriteTransfer(
            *(unsigned __int16 *)(v5 + 200),
            (unsigned int)USBHUB3_ETW_EVENT_20_PORT_STATUS,
            a3,
            *(_QWORD *)(*(_QWORD *)v5 + 248LL),
            *(_WORD *)(v5 + 200),
            *(_WORD *)(v5 + 184),
            *(_WORD *)(v5 + 186));
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(a4) = ((v9 & 4) != 0) + 48;
          LOBYTE(a3) = ((v9 & 0x10) != 0) + 48;
          WPP_RECORDER_SF_cccccccc(
            *(_QWORD *)(v5 + 1432),
            ((v9 & 2) != 0) + 48,
            a3,
            a4,
            (_DWORD)v23,
            (v9 & 1) + 48,
            ((v9 & 0x400) != 0) + 48,
            ((v9 & 0x200) != 0) + 48,
            ((v9 & 2) != 0) + 48,
            a3,
            a4,
            (BYTE1(v9) & 1) + 48,
            ((v9 & 8) != 0) + 48);
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            v15 = HIWORD(v9);
            LOBYTE(v14) = ((v9 & 0x80000) != 0) + 48;
            LOBYTE(v13) = ((v9 & 0x40000) != 0) + 48;
            LOBYTE(v15) = (BYTE2(v9) & 1) + 48;
            WPP_RECORDER_SF_ccccc(
              *(_QWORD *)(v5 + 1432),
              v13,
              v14,
              v15,
              v25,
              v15,
              ((v9 & 0x20000) != 0) + 48,
              ((v9 & 0x100000) != 0) + 48,
              v13,
              v14);
          }
        }
      }
    }
    if ( *(_BYTE *)(v5 + 169) == 3 )
    {
      v16 = *(_WORD *)(v5 + 170);
      if ( v16 == 2 )
      {
        *(_WORD *)(v5 + 192) |= 4u;
        *(_WORD *)(v5 + 184) |= 4u;
      }
      else if ( v16 == 5 )
      {
        v17 = *(_BYTE *)(v5 + 173);
        if ( v17 == 3 )
        {
          *(_WORD *)(v5 + 192) = *(_WORD *)(v5 + 192) & 0xFE1F | 0x60;
          v18 = *(_WORD *)(v5 + 184) & 0xFE1F | 0x60;
        }
        else
        {
          if ( v17 != 4 )
            goto LABEL_35;
          *(_WORD *)(v5 + 192) = *(_WORD *)(v5 + 192) & 0xFE1F | 0x80;
          v18 = *(_WORD *)(v5 + 184) & 0xFE1F | 0x80;
        }
        *(_WORD *)(v5 + 184) = v18;
      }
    }
  }
  else
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_dD(
        *(_QWORD *)(a4 + 1432),
        2,
        4,
        34,
        (__int64)WPP_70469c384dd13630d566350a6f2705ad_Traceguids,
        v4,
        *(_DWORD *)(a4 + 44));
    if ( (*(_DWORD *)(*(_QWORD *)v5 + 2608LL) & 2) != 0 )
      HUBMISC_VerifierDbgBreak("HubHwVerifierControlTransferFailure", *(_QWORD *)v5 + 1280LL, a3, a4);
    *(_DWORD *)(*(_QWORD *)v5 + 2612LL) = 1073872897;
    if ( (byte_14006ED42 & 2) != 0 )
      McTemplateK0pqqq_EtwWriteTransfer(
        a1,
        (unsigned int)USBHUB3_ETW_EVENT_PORT_CONTROL_TRANSFER_ERROR,
        0,
        *(_QWORD *)(*(_QWORD *)v5 + 248LL),
        *(_WORD *)(v5 + 200),
        v6,
        v4);
  }
LABEL_35:
  v29 = 0;
  v30 = 0;
  v27 = 24;
  v28 = 0;
  v19 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 1992))(
          WdfDriverGlobals,
          a1,
          &v27);
  if ( v19 < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v20 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, WDFDRIVER__ *, __int64 *))(WdfFunctions_01015 + 1616))(
            WdfDriverGlobals,
            WdfDriverGlobals->Driver,
            off_14006B2C0);
    LODWORD(v26) = v19;
    LOBYTE(v21) = 2;
    WPP_RECORDER_SF_d(*(_QWORD *)(v20 + 64), v21, 2, 59, (__int64)WPP_dde998bf8bb3310d95d4227a99ba80b7_Traceguids, v26);
  }
  return (*(__int64 (__fastcall **)(__int64, _QWORD))(v5 + 1240))(v5, ((v4 >> 31) & 0xFFFFFFFC) + 3012);
}

```

## disassembly

```asm
0x1400053d0  mov     [rsp+arg_0], rbx
0x1400053d5  mov     [rsp+arg_8], rbp
0x1400053da  push    rsi
0x1400053db  push    rdi
0x1400053dc  push    r12
0x1400053de  push    r14
0x1400053e0  push    r15
0x1400053e2  sub     rsp, 90h
0x1400053e9  mov     esi, [r8+8]
0x1400053ed  mov     rdi, r9
0x1400053f0  mov     ebx, [r9+2Ch]
0x1400053f4  mov     r15, rcx
0x1400053f7  mov     ebp, 2
0x1400053fc  test    esi, esi
0x1400053fe  jns     loc_1400054AB
0x140005404  lea     r14, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000540b  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140005412  jz      short loc_14000543F
0x140005414  mov     rcx, [rdi+598h]
0x14000541b  lea     rax, WPP_70469c384dd13630d566350a6f2705ad_Traceguids
0x140005422  mov     [rsp+0B8h+var_88], ebx
0x140005426  lea     r9d, [rbp+20h]
0x14000542a  mov     dword ptr [rsp+0B8h+var_90], esi
0x14000542e  lea     r8d, [rbp+2]
0x140005432  mov     dl, bpl
0x140005435  mov     [rsp+0B8h+var_98], rax
0x14000543a  call    WPP_RECORDER_SF_dD
0x14000543f  mov     rdx, [rdi]
0x140005442  mov     eax, [rdx+0A30h]
0x140005448  test    bpl, al
0x14000544b  jz      short loc_140005460
0x14000544d  add     rdx, 500h
0x140005454  lea     rcx, aHubhwverifierc; "HubHwVerifierControlTransferFailure"
0x14000545b  call    HUBMISC_VerifierDbgBreak
0x140005460  mov     rax, [rdi]
0x140005463  mov     dword ptr [rax+0A34h], 40020001h
0x14000546d  test    cs:byte_14006ED42, bpl
0x140005474  jz      loc_1400058BB
0x14000547a  mov     r9, [rdi]
0x14000547d  lea     rdx, USBHUB3_ETW_EVENT_PORT_CONTROL_TRANSFER_ERROR
0x140005484  movzx   eax, word ptr [rdi+0C8h]
0x14000548b  xor     r8d, r8d
0x14000548e  mov     [rsp+0B8h+var_88], esi
0x140005492  mov     dword ptr [rsp+0B8h+var_90], ebx
0x140005496  mov     r9, [r9+0F8h]
0x14000549d  mov     dword ptr [rsp+0B8h+var_98], eax
0x1400054a1  call    McTemplateK0pqqq_EtwWriteTransfer
0x1400054a6  jmp     loc_1400058BB
0x1400054ab  cmp     byte ptr [r9+0A9h], 0
0x1400054b3  lea     r14, WPP_RECORDER_INITIALIZED
0x1400054ba  jnz     loc_140005817
0x1400054c0  mov     eax, [r9+538h]
0x1400054c7  mov     r12d, 1
0x1400054cd  and     eax, 20h
0x1400054d0  cmp     ebx, r12d
0x1400054d3  jnz     short loc_140005526
0x1400054d5  test    eax, eax
0x1400054d7  jnz     loc_140005568
0x1400054dd  mov     rdx, [r9]
0x1400054e0  lea     rcx, aOnecoreDrivers_7; "onecore\\drivers\\wdm\\usb\\usb3\\hub\\"...
0x1400054e7  mov     rax, cs:WdfFunctions_01015
0x1400054ee  xor     r9d, r9d
0x1400054f1  mov     [rsp+0B8h+var_90], rcx
0x1400054f6  xor     r8d, r8d
0x1400054f9  mov     rcx, cs:WdfDriverGlobals
0x140005500  mov     rdx, [rdx+10h]
0x140005504  mov     rax, [rax+0DB0h]
0x14000550b  mov     dword ptr [rsp+0B8h+var_98], 6A3h
0x140005513  call    _guard_dispatch_icall
0x140005518  test    eax, eax
0x14000551a  js      short loc_140005568
0x14000551c  lock or dword ptr [rdi+538h], 20h
0x140005524  jmp     short loc_140005568
0x140005526  test    eax, eax
0x140005528  jz      short loc_140005568
0x14000552a  mov     rdx, [r9]
0x14000552d  lea     rcx, aOnecoreDrivers_7; "onecore\\drivers\\wdm\\usb\\usb3\\hub\\"...
0x140005534  mov     rax, cs:WdfFunctions_01015
0x14000553b  mov     r9d, 6ABh
0x140005541  mov     [rsp+0B8h+var_98], rcx
0x140005546  xor     r8d, r8d
0x140005549  mov     rcx, cs:WdfDriverGlobals
0x140005550  mov     rdx, [rdx+10h]
0x140005554  mov     rax, [rax+0DB8h]
0x14000555b  call    _guard_dispatch_icall
0x140005560  lock and dword ptr [rdi+538h], 0FFFFFFDFh
0x140005568  cmp     dword ptr [rdi+4E8h], 1388h
0x140005572  mov     rbx, [rdi+50h]
0x140005576  mov     ebx, [rbx]
0x140005578  mov     [rsp+0B8h+arg_10], ebx
0x14000557f  jnz     loc_1400056C6
0x140005585  test    cs:byte_14006ED41, 20h
0x14000558c  jz      short loc_1400055C7
0x14000558e  movzx   eax, word ptr [rdi+0BAh]
0x140005595  lea     rdx, USBHUB3_ETW_EVENT_30_PORT_STATUS
0x14000559c  mov     r9, [rdi]
0x14000559f  movzx   ecx, word ptr [rdi+0C8h]
0x1400055a6  mov     word ptr [rsp+0B8h+var_88], ax
0x1400055ab  movzx   eax, word ptr [rdi+0B8h]
0x1400055b2  mov     r9, [r9+0F8h]
0x1400055b9  mov     word ptr [rsp+0B8h+var_90], ax
0x1400055be  mov     dword ptr [rsp+0B8h+var_98], ecx
0x1400055c2  call    McTemplateK0pqhh_EtwWriteTransfer
0x1400055c7  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x1400055ce  jz      loc_140005817
0x1400055d4  mov     bpl, 30h ; '0'
0x1400055d7  mov     r9b, bl
0x1400055da  movzx   r8d, bx
0x1400055de  shr     r9b, 3
0x1400055e2  mov     dl, bl
0x1400055e4  shr     r8w, 9
0x1400055e9  mov     cl, bl
0x1400055eb  shr     dl, 4
0x1400055ee  shr     cl, 1
0x1400055f0  movzx   eax, bx
0x1400055f3  and     cl, r12b
0x1400055f6  shr     ax, 5
0x1400055fa  add     cl, bpl
0x1400055fd  and     r9b, r12b
0x140005600  and     r8b, r12b
0x140005603  add     r9b, bpl
0x140005606  mov     [rsp+0B8h+var_68], r9b
0x14000560b  and     dl, r12b
0x14000560e  add     r8b, bpl
0x140005611  add     dl, bpl
0x140005614  mov     [rsp+0B8h+var_70], r8b
0x140005619  and     bl, r12b
0x14000561c  mov     [rsp+0B8h+var_78], dl
0x140005620  and     ax, 0Fh
0x140005624  mov     [rsp+0B8h+var_80], cl
0x140005628  add     bl, bpl
0x14000562b  mov     rcx, [rdi+598h]
0x140005632  mov     word ptr [rsp+0B8h+var_88], ax
0x140005637  mov     byte ptr [rsp+0B8h+var_90], bl
0x14000563b  call    WPP_RECORDER_SF_chcccc
0x140005640  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x140005647  jz      loc_140005812
0x14000564d  movzx   r10d, word ptr [rsp+0B8h+arg_10+2]
0x140005656  mov     cl, r10b
0x140005659  mov     r9b, r10b
0x14000565c  mov     r8b, r10b
0x14000565f  shr     cl, 4
0x140005662  mov     dl, r10b
0x140005665  shr     r9b, 7
0x140005669  mov     al, r10b
0x14000566c  shr     r8b, 3
0x140005670  shr     dl, 5
0x140005673  and     cl, r12b
0x140005676  shr     al, 6
0x140005679  add     cl, bpl
0x14000567c  and     r9b, r12b
0x14000567f  and     r8b, r12b
0x140005682  add     r9b, bpl
0x140005685  and     dl, r12b
0x140005688  mov     [rsp+0B8h+var_68], r9b
0x14000568d  add     r8b, bpl
0x140005690  mov     [rsp+0B8h+var_70], r8b
0x140005695  add     dl, bpl
0x140005698  mov     [rsp+0B8h+var_78], dl
0x14000569c  and     al, r12b
0x14000569f  mov     [rsp+0B8h+var_80], cl
0x1400056a3  and     r10b, r12b
0x1400056a6  mov     rcx, [rdi+598h]
0x1400056ad  add     al, bpl
0x1400056b0  add     r10b, bpl
0x1400056b3  mov     byte ptr [rsp+0B8h+var_88], al
0x1400056b7  mov     byte ptr [rsp+0B8h+var_90], r10b
0x1400056bc  call    WPP_RECORDER_SF_cccccc
0x1400056c1  jmp     loc_140005812
0x1400056c6  test    cs:byte_14006ED41, 20h
0x1400056cd  jz      short loc_140005708
0x1400056cf  movzx   eax, word ptr [rdi+0BAh]
0x1400056d6  lea     rdx, USBHUB3_ETW_EVENT_20_PORT_STATUS
0x1400056dd  mov     r9, [rdi]
0x1400056e0  movzx   ecx, word ptr [rdi+0C8h]
0x1400056e7  mov     word ptr [rsp+0B8h+var_88], ax
0x1400056ec  movzx   eax, word ptr [rdi+0B8h]
0x1400056f3  mov     r9, [r9+0F8h]
0x1400056fa  mov     word ptr [rsp+0B8h+var_90], ax
0x1400056ff  mov     dword ptr [rsp+0B8h+var_98], ecx
0x140005703  call    McTemplateK0pqhh_EtwWriteTransfer
0x140005708  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x14000570f  jz      loc_140005817
0x140005715  mov     bpl, 30h ; '0'
0x140005718  mov     r11b, bl
0x14000571b  movzx   r10d, bx
0x14000571f  shr     r11b, 3
0x140005723  mov     r9b, bl
0x140005726  shr     r10w, 8
0x14000572b  mov     r8b, bl
0x14000572e  shr     r9b, 2
0x140005732  mov     dl, bl
0x140005734  shr     r8b, 4
0x140005738  movzx   ecx, bx
0x14000573b  shr     dl, 1
0x14000573d  movzx   eax, bx
0x140005740  shr     cx, 9
0x140005744  shr     ax, 0Ah
0x140005748  and     cl, r12b
0x14000574b  add     cl, bpl
0x14000574e  and     r11b, r12b
0x140005751  and     r10b, r12b
0x140005754  add     r11b, bpl
0x140005757  mov     [rsp+0B8h+var_58], r11b
0x14000575c  and     r9b, r12b
0x14000575f  add     r10b, bpl
0x140005762  and     r8b, r12b
0x140005765  mov     [rsp+0B8h+var_60], r10b
0x14000576a  add     r9b, bpl
0x14000576d  mov     [rsp+0B8h+var_68], r9b
0x140005772  and     dl, r12b
0x140005775  add     r8b, bpl
0x140005778  add     dl, bpl
0x14000577b  mov     [rsp+0B8h+var_70], r8b
0x140005780  and     al, r12b
0x140005783  mov     [rsp+0B8h+var_78], dl
0x140005787  and     bl, r12b
0x14000578a  mov     [rsp+0B8h+var_80], cl
0x14000578e  add     al, bpl
0x140005791  mov     rcx, [rdi+598h]
0x140005798  add     bl, bpl
0x14000579b  mov     byte ptr [rsp+0B8h+var_88], al
0x14000579f  mov     byte ptr [rsp+0B8h+var_90], bl
0x1400057a3  call    WPP_RECORDER_SF_cccccccc
0x1400057a8  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x1400057af  jz      short loc_140005812
0x1400057b1  movzx   r9d, word ptr [rsp+0B8h+arg_10+2]
0x1400057ba  mov     cl, r9b
0x1400057bd  mov     r8b, r9b
0x1400057c0  mov     dl, r9b
0x1400057c3  shr     cl, 4
0x1400057c6  mov     al, r9b
0x1400057c9  shr     r8b, 3
0x1400057cd  shr     dl, 2
0x1400057d0  and     cl, r12b
0x1400057d3  shr     al, 1
0x1400057d5  add     cl, bpl
0x1400057d8  and     r8b, r12b
0x1400057db  and     dl, r12b
0x1400057de  add     r8b, bpl
0x1400057e1  add     dl, bpl
0x1400057e4  mov     [rsp+0B8h+var_70], r8b
0x1400057e9  and     al, r12b
0x1400057ec  mov     [rsp+0B8h+var_78], dl
0x1400057f0  and     r9b, r12b
0x1400057f3  mov     [rsp+0B8h+var_80], cl
0x1400057f7  add     al, bpl
0x1400057fa  mov     rcx, [rdi+598h]
0x140005801  add     r9b, bpl
0x140005804  mov     byte ptr [rsp+0B8h+var_88], al
0x140005808  mov     byte ptr [rsp+0B8h+var_90], r9b
0x14000580d  call    WPP_RECORDER_SF_ccccc
0x140005812  mov     ebp, 2
0x140005817  cmp     byte ptr [rdi+0A9h], 3
0x14000581e  jnz     loc_1400058BB
0x140005824  movzx   eax, word ptr [rdi+0AAh]
0x14000582b  cmp     ax, bp
0x14000582e  jnz     short loc_140005845
0x140005830  mov     eax, 4
0x140005835  or      [rdi+0C0h], ax
0x14000583c  or      [rdi+0B8h], ax
0x140005843  jmp     short loc_1400058BB
0x140005845  cmp     ax, 5
0x140005849  jnz     short loc_1400058BB
0x14000584b  mov     cl, [rdi+0ADh]
0x140005851  cmp     cl, 3
0x140005854  jnz     short loc_140005880
0x140005856  movzx   eax, word ptr [rdi+0C0h]
0x14000585d  mov     ecx, 0FE7Fh
0x140005862  and     ax, cx
0x140005865  or      ax, 60h
0x140005869  mov     [rdi+0C0h], ax
0x140005870  movzx   eax, word ptr [rdi+0B8h]
0x140005877  and     ax, cx
0x14000587a  or      ax, 60h
0x14000587e  jmp     short loc_1400058B4
0x140005880  mov     eax, 4
0x140005885  cmp     cl, al
0x140005887  jnz     short loc_1400058BB
0x140005889  movzx   eax, word ptr [rdi+0C0h]
0x140005890  mov     ecx, 0FE9Fh
0x140005895  and     ax, cx
0x140005898  mov     edx, 80h
0x14000589d  or      ax, dx
0x1400058a0  mov     [rdi+0C0h], ax
0x1400058a7  movzx   eax, word ptr [rdi+0B8h]
0x1400058ae  and     ax, cx
0x1400058b1  or      ax, dx
0x1400058b4  mov     [rdi+0B8h], ax
0x1400058bb  mov     rax, cs:WdfFunctions_01015
0x1400058c2  lea     r8, [rsp+0B8h+var_48]
0x1400058c7  mov     rcx, cs:WdfDriverGlobals
0x1400058ce  mov     rdx, r15
0x1400058d1  mov     [rsp+0B8h+var_3C], 0
0x1400058da  mov     [rsp+0B8h+var_34], 0
0x1400058e5  mov     [rsp+0B8h+var_48], 18h
0x1400058ee  mov     [rsp+0B8h+var_40], 0
0x1400058f6  mov     rax, [rax+7C8h]
0x1400058fd  call    _guard_dispatch_icall
0x140005902  mov     ebx, eax
  ... truncated ...
```
