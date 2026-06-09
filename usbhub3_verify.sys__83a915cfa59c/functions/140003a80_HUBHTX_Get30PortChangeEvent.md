# HUBHTX_Get30PortChangeEvent

- ea: `0x140003a80`
- end: `0x1400045cf`
- name: `HUBHTX_Get30PortChangeEvent`
- size: `2895`
- prototype: ``
- caller_count: `3`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400132d0`
- `0x1400136a0`
- `0x1400136d0`

## callees

- `0x140001f94`
- `0x1400024b8`
- `0x1400025a4`
- `0x140003a80`
- `0x1400066d4`
- `0x1400067ac`
- `0x140007080`
- `0x1400072b0`
- `0x140033530`
- `0x1400347a4`
- `0x140045570`

## string_xrefs

- `0x140003fc7`: `HubHwVerifierPortLinkStateCompliance`
- `0x14000409c`: `HubHwVerifierPortLinkStateSSInactive`
- `0x140004471`: `HubHwVerifierPortLinkStateErrorResetWatchdog`

## pseudocode

```c
__int64 __fastcall HUBHTX_Get30PortChangeEvent(volatile signed __int32 *a1, int a2)
{
  _WORD *v3; // rax
  unsigned int v4; // r14d
  __int16 v5; // r9
  __int16 v6; // r13
  __int16 v7; // si
  __int16 v8; // r15
  char v9; // dl
  __int64 v10; // rax
  unsigned int v11; // edi
  __int64 v12; // rcx
  int v13; // r9d
  unsigned __int16 v14; // cx
  int v15; // r9d
  __int64 v16; // rax
  int v17; // eax
  int v18; // r9d
  int v20; // r9d
  char v21; // dl
  unsigned int v22; // r8d
  unsigned int v23; // edx
  __int64 v24; // rcx
  unsigned __int16 v25; // [rsp+B0h] [rbp+8h]
  __int16 v26; // [rsp+B8h] [rbp+10h]
  char v27; // [rsp+C0h] [rbp+18h]
  char v28; // [rsp+C8h] [rbp+20h]

  _InterlockedAnd(a1 + 334, 0xFFFFFF7F);
  if ( *((_BYTE *)a1 + 1457) )
  {
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, _QWORD, __int64, const char *))(WdfFunctions_01015 + 3512))(
      WdfDriverGlobals,
      *(_QWORD *)(*(_QWORD *)a1 + 16LL),
      0,
      3905,
      "onecore\\drivers\\wdm\\usb\\usb3\\hub\\src\\hubxfer.c");
    *((_BYTE *)a1 + 1457) = 0;
  }
  v3 = (_WORD *)*((_QWORD *)a1 + 166);
  v4 = *((unsigned __int16 *)a1 + 92);
  v5 = *((_WORD *)a1 + 97);
  v6 = *((_WORD *)a1 + 96);
  v25 = v5;
  *((_WORD *)a1 + 96) = v4;
  if ( v3 )
  {
    v7 = v3[1004];
    v8 = v3[1003];
    v26 = v3[1002];
    v27 = v7;
    v28 = v8;
  }
  else
  {
    LOBYTE(v7) = 0;
    v27 = 0;
    LOBYTE(v8) = 0;
    v28 = 0;
    LOBYTE(v26) = 0;
  }
  if ( (v4 & 8) != 0 )
  {
    HUBREG_UpdateSqmHubOvercurrentDetected(*(_QWORD *)a1);
    v10 = *(_QWORD *)a1;
    v11 = 3065;
    *((_DWORD *)a1 + 356) = 4;
    if ( _bittest((const signed __int32 *)(v10 + 2608), 9u) )
      HUBMISC_VerifierDbgBreak("HubHwVerifierPortOverCurrent", a1 + 68);
    if ( (byte_14006ED42 & 1) != 0 )
      McTemplateK0qhhhqhhh_EtwWriteTransfer(
        v25,
        v9,
        *a1 + 2428,
        *((unsigned __int16 *)a1 + 100),
        v6,
        v4,
        v25,
        249,
        v26,
        v8,
        v7);
    goto LABEL_84;
  }
  v11 = 3061;
  if ( (v5 & 8) != 0 )
  {
    HUBREG_UpdateSqmHubOvercurrentDetected(*(_QWORD *)a1);
    v12 = *(_QWORD *)a1;
    if ( (*(_DWORD *)(*(_QWORD *)a1 + 44LL) & 0x40) != 0 && (v4 & 0x200) != 0 )
    {
      *((_DWORD *)a1 + 356) = 1;
      v11 = 3017;
    }
    else if ( (v6 & 8) == 0 )
    {
      *((_DWORD *)a1 + 356) = 4;
      v11 = 3065;
    }
    if ( _bittest((const signed __int32 *)(v12 + 2608), 9u) )
      HUBMISC_VerifierDbgBreak("HubHwVerifierPortOverCurrent", a1 + 68);
    if ( (byte_14006ED42 & 1) != 0 )
      McTemplateK0qhhhqhhh_EtwWriteTransfer(
        v25,
        (_BYTE)a2,
        *a1 + 2428,
        *((unsigned __int16 *)a1 + 100),
        v6,
        v4,
        v25,
        v11,
        v26,
        v28,
        v27);
LABEL_120:
    if ( v11 != 3017 )
      goto LABEL_83;
    LOBYTE(v5) = v25;
LABEL_76:
    if ( (v4 & 1) == 0 )
      goto LABEL_77;
LABEL_84:
    *((_DWORD *)a1 + 2) = v11;
    return v11;
  }
  if ( (v4 & 0x200) == 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v13 = 86;
LABEL_133:
      WPP_RECORDER_SF_(*((_QWORD *)a1 + 179), 2, 4, v13, (__int64)WPP_70469c384dd13630d566350a6f2705ad_Traceguids);
      goto LABEL_134;
    }
    goto LABEL_134;
  }
  if ( (v4 & 0x10) == 0 )
  {
    if ( (v4 & 1) == 0 )
    {
      if ( (v4 & 0x1E0) == 0xA0 )
      {
        if ( (v6 & 0x200) != 0 && (v6 & 0x1E0) != 0xA0 )
          goto LABEL_35;
      }
      else if ( (v4 & 0x1E0) == 0xE0 && (v6 & 0x200) != 0 && (v6 & 0x1E0) != 0xE0 )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          WPP_RECORDER_SF_(*((_QWORD *)a1 + 179), 2, 4, 89, (__int64)WPP_70469c384dd13630d566350a6f2705ad_Traceguids);
          LOBYTE(v5) = v25;
        }
        goto LABEL_35;
      }
    }
    v14 = v4 & 0x1E0;
    if ( (v4 & 0x1E0) == 0x160 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_134;
      v15 = 90;
      goto LABEL_43;
    }
    a2 = 128;
    switch ( v14 )
    {
      case 0x80u:
        if ( (v6 & 0x1E0) != 0x80 )
        {
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            goto LABEL_134;
          v15 = 91;
          goto LABEL_43;
        }
LABEL_100:
        if ( (v5 & 1) == 0 && (v4 & 1) == (v6 & 1) )
        {
          if ( (v4 & 1) == 0 )
          {
            if ( (v4 & 2) != 0 )
            {
              if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              {
                v13 = 101;
                goto LABEL_133;
              }
              goto LABEL_134;
            }
            if ( v14 > 0x60u )
              return v11;
            if ( (*(_DWORD *)(*(_QWORD *)a1 + 40LL) & 0x100000) == 0 )
            {
              if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                goto LABEL_134;
              v15 = 103;
              goto LABEL_43;
            }
            if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              return v11;
            v20 = 102;
            v4 = (v4 >> 5) & 0xF;
            v21 = 2;
LABEL_91:
            WPP_RECORDER_SF_d(
              *((_QWORD *)a1 + 179),
              v21,
              4,
              v20,
              (__int64)WPP_70469c384dd13630d566350a6f2705ad_Traceguids,
              v4);
            return v11;
          }
          if ( v14 != 160 )
          {
            if ( (v4 & 2) == 0 )
            {
              if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              {
                v13 = 105;
                goto LABEL_133;
              }
              goto LABEL_134;
            }
            if ( v14 <= 0x60u || v14 == 256 )
            {
              if ( (v5 & 0x10) == 0 )
              {
                if ( (v6 & 0x1E0) == 0x60 && v14 != 96 )
                {
                  v11 = 3085;
                  goto LABEL_84;
                }
                return v11;
              }
              if ( v14 != 96 )
              {
                v11 = 3073;
                goto LABEL_84;
              }
              if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              {
                v13 = 107;
                goto LABEL_133;
              }
              goto LABEL_134;
            }
            if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              goto LABEL_134;
            v15 = 106;
LABEL_43:
            WPP_RECORDER_SF_d(
              *((_QWORD *)a1 + 179),
              2,
              4,
              v15,
              (__int64)WPP_70469c384dd13630d566350a6f2705ad_Traceguids,
              (v4 >> 5) & 0xF);
            goto LABEL_134;
          }
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            WPP_RECORDER_SF_(*((_QWORD *)a1 + 179), 2, 4, 104, (__int64)WPP_70469c384dd13630d566350a6f2705ad_Traceguids);
          goto LABEL_115;
        }
LABEL_75:
        v11 = 3017;
        goto LABEL_76;
      case 0x140u:
        v16 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01015 + 1632))(
                WdfDriverGlobals,
                *(_QWORD *)a1);
        v17 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 3104))(
                WdfDriverGlobals,
                v16);
        a2 = 0;
        if ( !v17 || *(_BYTE *)(*(_QWORD *)a1 + 240LL) )
        {
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(a2) = 2;
            WPP_RECORDER_SF_dD(
              *((_QWORD *)a1 + 179),
              a2,
              4,
              92,
              (__int64)WPP_70469c384dd13630d566350a6f2705ad_Traceguids,
              ((unsigned __int16)v4 >> 5) & 0xF,
              v4 & 1);
          }
          if ( _bittest((const signed __int32 *)(*(_QWORD *)a1 + 2608LL), 8u) )
            HUBMISC_VerifierDbgBreak("HubHwVerifierPortLinkStateCompliance", a1 + 68);
          if ( (byte_14006ED42 & 1) != 0 )
            McTemplateK0qhhhqhhh_EtwWriteTransfer(
              v25,
              (_BYTE)a2,
              *a1 + 2428,
              *((unsigned __int16 *)a1 + 100),
              v6,
              v4,
              v25,
              245,
              v26,
              v28,
              v27);
          goto LABEL_115;
        }
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
LABEL_115:
          v22 = ++*((_DWORD *)a1 + 361);
          v11 = 3053;
          v23 = v22 / 0x64;
          if ( v22 != 100 * (v22 / 0x64) )
            goto LABEL_84;
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v23) = 2;
            WPP_RECORDER_SF_qd(
              *((_QWORD *)a1 + 179),
              v23,
              4,
              108,
              (__int64)WPP_70469c384dd13630d566350a6f2705ad_Traceguids,
              (char)a1,
              v22);
          }
          if ( (*(_DWORD *)(*(_QWORD *)a1 + 2608LL) & 0x800) == 0 )
            goto LABEL_84;
          HUBMISC_VerifierDbgBreak("HubHwVerifierPortLinkStateErrorResetWatchdog", a1 + 68);
          goto LABEL_120;
        }
        v18 = 93;
        break;
      case 0xC0u:
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(a2) = 2;
          WPP_RECORDER_SF_dD(
            *((_QWORD *)a1 + 179),
            a2,
            4,
            94,
            (__int64)WPP_70469c384dd13630d566350a6f2705ad_Traceguids,
            ((unsigned __int16)v4 >> 5) & 0xF,
            v4 & 1);
        }
        if ( (*(_DWORD *)(*(_QWORD *)a1 + 2608LL) & 0x20) != 0 )
          HUBMISC_VerifierDbgBreak("HubHwVerifierPortLinkStateSSInactive", a1 + 68);
        if ( (byte_14006ED42 & 1) != 0 )
          McTemplateK0qhhhqhhh_EtwWriteTransfer(
            v25,
            (_BYTE)a2,
            *a1 + 2428,
            *((unsigned __int16 *)a1 + 100),
            v6,
            v4,
            v25,
            245,
            v26,
            v28,
            v27);
        LOBYTE(v5) = v25;
        if ( (v25 & 0x80u) != 0 )
        {
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            WPP_RECORDER_SF_(*((_QWORD *)a1 + 179), 2, 4, 95, (__int64)WPP_70469c384dd13630d566350a6f2705ad_Traceguids);
            LOBYTE(v5) = v25;
          }
          goto LABEL_75;
        }
        _InterlockedOr(a1 + 334, 0x80u);
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_SF_d(
            *((_QWORD *)a1 + 179),
            2,
            4,
            96,
            (__int64)WPP_70469c384dd13630d566350a6f2705ad_Traceguids,
            (v4 >> 5) & 0xF);
        if ( *((_DWORD *)a1 + 2) == 3053 )
        {
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            return v11;
          LOBYTE(v4) = v4 & 1;
          v20 = 97;
          v21 = 3;
          goto LABEL_91;
        }
        if ( (v4 & 2) != 0 )
        {
          if ( (*(_DWORD *)(*(_QWORD *)a1 + 40LL) & 0x200000) == 0 )
          {
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              v13 = 99;
              goto LABEL_133;
            }
            goto LABEL_134;
          }
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            goto LABEL_115;
          WPP_RECORDER_SF_(*((_QWORD *)a1 + 179), 2, 4, 98, (__int64)WPP_70469c384dd13630d566350a6f2705ad_Traceguids);
        }
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_115;
        v18 = 100;
        break;
      default:
        goto LABEL_100;
    }
    LOBYTE(a2) = 2;
    WPP_RECORDER_SF_dD(
      *((_QWORD *)a1 + 179),
      a2,
      4,
      v18,
      (__int64)WPP_70469c384dd13630d566350a6f2705ad_Traceguids,
      ((unsigned __int16)v4 >> 5) & 0xF,
      v4 & 1);
    goto LABEL_115;
  }
  if ( (v4 & 2) != 0 )
  {
    if ( (*(_DWORD *)(*(_QWORD *)a1 + 40LL) & 0x1000000) == 0 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v13 = 88;
        goto LABEL_133;
      }
LABEL_134:
      v11 = 3077;
      v24 = *(unsigned int *)(*(_QWORD *)a1 + 2608LL);
      if ( (v24 & 0x10) != 0 )
        HUBMISC_VerifierDbgBreak("HubHwVerifierInvalidPortStatus", a1 + 68);
      *(_DWORD *)(*(_QWORD *)a1 + 2612LL) = 1073872896;
      if ( (byte_14006ED41 & 0x40) != 0 )
        McTemplateK0pq_EtwWriteTransfer(
          v24,
          USBHUB3_ETW_EVENT_HUB_RESET_DUE_TO_PORT_ERROR,
          0,
          *(_QWORD *)(*(_QWORD *)a1 + 248LL),
          *((unsigned __int16 *)a1 + 100));
      *(_WORD *)(*(_QWORD *)a1 + 74LL) = v25;
      *(_WORD *)(*(_QWORD *)a1 + 72LL) = v4;
      goto LABEL_84;
    }
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      WPP_RECORDER_SF_(*((_QWORD *)a1 + 179), 2, 4, 87, (__int64)WPP_70469c384dd13630d566350a6f2705ad_Traceguids);
      LOBYTE(v5) = v25;
    }
  }
  if ( (v4 & 1) != 0 )
  {
    v11 = 3081;
    goto LABEL_84;
  }
  if ( (v5 & 1) == 0 && (v6 & 1) == 0 )
    return v11;
LABEL_35:
  v11 = 3017;
LABEL_77:
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_dDDD(
      *((_QWORD *)a1 + 179),
      (_BYTE)a2,
      4,
      109,
      (__int64)WPP_70469c384dd13630d566350a6f2705ad_Traceguids,
      *((_WORD *)a1 + 100),
      v6,
      v4,
      v5);
  if ( (*(_DWORD *)(*(_QWORD *)a1 + 2608LL) & 0x400) != 0 )
    HUBMISC_VerifierDbgBreak("HubHwVerifierPortDeviceDisconnected", a1 + 68);
  if ( (byte_14006ED42 & 1) == 0 )
    goto LABEL_84;
  McTemplateK0qhhhqhhh_EtwWriteTransfer(
    v25,
    (_BYTE)a2,
    0,
    *((unsigned __int16 *)a1 + 100),
    v6,
    v4,
    v25,
    201,
    v26,
    v28,
    v27);
LABEL_83:
  if ( v11 != 3061 )
    goto LABEL_84;
  return v11;
}

```

## disassembly

```asm
0x140003a80  push    rbx
0x140003a82  push    rbp
0x140003a83  push    rsi
0x140003a84  push    rdi
0x140003a85  push    r12
0x140003a87  push    r13
0x140003a89  push    r14
0x140003a8b  push    r15
0x140003a8d  sub     rsp, 68h
0x140003a91  mov     rbx, rcx
0x140003a94  lock and dword ptr [rcx+538h], 0FFFFFF7Fh
0x140003a9f  xor     edi, edi
0x140003aa1  cmp     [rcx+5B1h], dil
0x140003aa8  jz      short loc_140003AE7
0x140003aaa  mov     rdx, [rcx]
0x140003aad  mov     r9d, 0F41h
0x140003ab3  mov     rax, cs:WdfFunctions_01015
0x140003aba  lea     rcx, aOnecoreDrivers_7; "onecore\\drivers\\wdm\\usb\\usb3\\hub\\"...
0x140003ac1  mov     [rsp+0A8h+var_88], rcx
0x140003ac6  xor     r8d, r8d
0x140003ac9  mov     rcx, cs:WdfDriverGlobals
0x140003ad0  mov     rdx, [rdx+10h]
0x140003ad4  mov     rax, [rax+0DB8h]
0x140003adb  call    _guard_dispatch_icall
0x140003ae0  mov     [rbx+5B1h], dil
0x140003ae7  mov     rax, [rbx+530h]
0x140003aee  movzx   r14d, word ptr [rbx+0B8h]
0x140003af6  movzx   r9d, word ptr [rbx+0C2h]
0x140003afe  movzx   r13d, word ptr [rbx+0C0h]
0x140003b06  mov     [rsp+0A8h+arg_0], r9w
0x140003b0f  mov     [rbx+0C0h], r14w
0x140003b17  test    rax, rax
0x140003b1a  jz      short loc_140003B4A
0x140003b1c  movzx   esi, word ptr [rax+7D8h]
0x140003b23  movzx   r15d, word ptr [rax+7D6h]
0x140003b2b  movzx   eax, word ptr [rax+7D4h]
0x140003b32  mov     [rsp+0A8h+arg_8], eax
0x140003b39  mov     [rsp+0A8h+arg_10], esi
0x140003b40  mov     [rsp+0A8h+arg_18], r15d
0x140003b48  jmp     short loc_140003B64
0x140003b4a  mov     esi, edi
0x140003b4c  mov     [rsp+0A8h+arg_10], edi
0x140003b53  mov     r15d, edi
0x140003b56  mov     [rsp+0A8h+arg_18], edi
0x140003b5d  mov     [rsp+0A8h+arg_8], edi
0x140003b64  test    r14b, 8
0x140003b68  jz      loc_140003C08
0x140003b6e  mov     rcx, [rbx]
0x140003b71  call    HUBREG_UpdateSqmHubOvercurrentDetected
0x140003b76  mov     rax, [rbx]
0x140003b79  mov     edi, 0BF9h
0x140003b7e  mov     dword ptr [rbx+590h], 4
0x140003b88  bt      dword ptr [rax+0A30h], 9
0x140003b90  jnb     short loc_140003BA5
0x140003b92  lea     rdx, [rbx+110h]
0x140003b99  lea     rcx, aHubhwverifierp_4; "HubHwVerifierPortOverCurrent"
0x140003ba0  call    HUBMISC_VerifierDbgBreak
0x140003ba5  mov     r12d, 1
0x140003bab  test    cs:byte_14006ED42, r12b
0x140003bb2  jz      loc_140004224
0x140003bb8  mov     eax, [rsp+0A8h+arg_8]
0x140003bbf  movzx   ecx, [rsp+0A8h+arg_0]
0x140003bc7  mov     r8, [rbx]
0x140003bca  movzx   r9d, word ptr [rbx+0C8h]
0x140003bd2  add     r8, 97Ch
0x140003bd9  mov     [rsp+0A8h+var_58], si
0x140003bde  mov     [rsp+0A8h+var_60], r15w
0x140003be4  mov     word ptr [rsp+0A8h+var_68], ax
0x140003be9  mov     [rsp+0A8h+var_70], edi
0x140003bed  mov     word ptr [rsp+0A8h+var_78], cx
0x140003bf2  mov     word ptr [rsp+0A8h+var_80], r14w
0x140003bf8  mov     word ptr [rsp+0A8h+var_88], r13w
0x140003bfe  call    McTemplateK0qhhhqhhh_EtwWriteTransfer
0x140003c03  jmp     loc_140004224
0x140003c08  lea     rsi, WPP_RECORDER_INITIALIZED
0x140003c0f  mov     edi, 0BF5h
0x140003c14  lea     r15, WPP_70469c384dd13630d566350a6f2705ad_Traceguids
0x140003c1b  mov     ebp, 4
0x140003c20  test    r9b, 8
0x140003c24  jz      loc_140003CEE
0x140003c2a  mov     rcx, [rbx]
0x140003c2d  call    HUBREG_UpdateSqmHubOvercurrentDetected
0x140003c32  mov     rcx, [rbx]
0x140003c35  lea     r12d, [rbp-3]
0x140003c39  mov     eax, [rcx+2Ch]
0x140003c3c  test    al, 40h
0x140003c3e  jz      short loc_140003C56
0x140003c40  bt      r14w, 9
0x140003c46  jnb     short loc_140003C56
0x140003c48  mov     [rbx+590h], r12d
0x140003c4f  mov     edi, 0BC9h
0x140003c54  jmp     short loc_140003C67
0x140003c56  test    r13b, 8
0x140003c5a  jnz     short loc_140003C67
0x140003c5c  mov     [rbx+590h], ebp
0x140003c62  mov     edi, 0BF9h
0x140003c67  bt      dword ptr [rcx+0A30h], 9
0x140003c6f  jnb     short loc_140003C84
0x140003c71  lea     rdx, [rbx+110h]
0x140003c78  lea     rcx, aHubhwverifierp_4; "HubHwVerifierPortOverCurrent"
0x140003c7f  call    HUBMISC_VerifierDbgBreak
0x140003c84  test    cs:byte_14006ED42, r12b
0x140003c8b  jz      loc_14000447D
0x140003c91  mov     eax, [rsp+0A8h+arg_10]
0x140003c98  movzx   ecx, [rsp+0A8h+arg_0]
0x140003ca0  mov     r8, [rbx]
0x140003ca3  movzx   r9d, word ptr [rbx+0C8h]
0x140003cab  add     r8, 97Ch
0x140003cb2  mov     [rsp+0A8h+var_58], ax
0x140003cb7  mov     eax, [rsp+0A8h+arg_18]
0x140003cbe  mov     [rsp+0A8h+var_60], ax
0x140003cc3  mov     eax, [rsp+0A8h+arg_8]
0x140003cca  mov     word ptr [rsp+0A8h+var_68], ax
0x140003ccf  mov     [rsp+0A8h+var_70], edi
0x140003cd3  mov     word ptr [rsp+0A8h+var_78], cx
0x140003cd8  mov     word ptr [rsp+0A8h+var_80], r14w
0x140003cde  mov     word ptr [rsp+0A8h+var_88], r13w
0x140003ce4  call    McTemplateK0qhhhqhhh_EtwWriteTransfer
0x140003ce9  jmp     loc_14000447D
0x140003cee  bt      r14w, 9
0x140003cf4  jb      short loc_140003D15
0x140003cf6  lea     rsi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140003cfd  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140003d04  jz      loc_140004528
0x140003d0a  mov     r9d, 56h ; 'V'
0x140003d10  jmp     loc_14000450B
0x140003d15  test    r14b, 10h
0x140003d19  jz      loc_140003DAB
0x140003d1f  test    r14b, 2
0x140003d23  jz      short loc_140003D5F
0x140003d25  mov     rax, [rbx]
0x140003d28  test    dword ptr [rax+28h], 1000000h
0x140003d2f  jz      short loc_140003D74
0x140003d31  cmp     cs:WPP_RECORDER_INITIALIZED, rsi; __annotation("TMF:",
0x140003d38  jz      short loc_140003D5F
0x140003d3a  mov     rcx, [rbx+598h]
0x140003d41  mov     r9d, 57h ; 'W'
0x140003d47  mov     r8d, ebp
0x140003d4a  mov     [rsp+0A8h+var_88], r15
0x140003d4f  mov     dl, 2
0x140003d51  call    WPP_RECORDER_SF_
0x140003d56  movzx   r9d, [rsp+0A8h+arg_0]
0x140003d5f  mov     r12d, 1
0x140003d65  test    r12b, r14b
0x140003d68  jz      short loc_140003D93
0x140003d6a  mov     edi, 0C09h
0x140003d6f  jmp     loc_140004224
0x140003d74  lea     rsi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140003d7b  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140003d82  jz      loc_140004528
0x140003d88  mov     r9d, 58h ; 'X'
0x140003d8e  jmp     loc_14000450B
0x140003d93  test    r12b, r9b
0x140003d96  jnz     short loc_140003DA1
0x140003d98  test    r12b, r13b
0x140003d9b  jz      loc_140004227
0x140003da1  mov     edi, 0BC9h
0x140003da6  jmp     loc_140004157
0x140003dab  movzx   r8d, r14w
0x140003daf  mov     r12d, 1
0x140003db5  mov     r10d, 1E0h
0x140003dbb  mov     r11d, 0A0h
0x140003dc1  and     r8w, r12w
0x140003dc5  jnz     short loc_140003DEB
0x140003dc7  movzx   eax, r14w
0x140003dcb  and     ax, r10w
0x140003dcf  cmp     ax, r11w
0x140003dd3  jnz     short loc_140003E4A
0x140003dd5  bt      r13w, 9
0x140003ddb  jnb     short loc_140003DEB
0x140003ddd  movzx   eax, r13w
0x140003de1  and     ax, r10w
0x140003de5  cmp     ax, r11w
0x140003de9  jnz     short loc_140003DA1
0x140003deb  movzx   ecx, r14w
0x140003def  mov     eax, 160h
0x140003df4  and     cx, r10w
0x140003df8  cmp     cx, ax
0x140003dfb  jnz     loc_140003EA0
0x140003e01  lea     rsi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140003e08  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140003e0f  jz      loc_140004528
0x140003e15  mov     r9d, 5Ah ; 'Z'
0x140003e1b  mov     rcx, [rbx+598h]
0x140003e22  lea     r15, WPP_70469c384dd13630d566350a6f2705ad_Traceguids
0x140003e29  mov     eax, r14d
0x140003e2c  mov     r8d, ebp
0x140003e2f  shr     eax, 5
0x140003e32  mov     dl, 2
0x140003e34  and     eax, 0Fh
0x140003e37  mov     dword ptr [rsp+0A8h+var_80], eax
0x140003e3b  mov     [rsp+0A8h+var_88], r15
0x140003e40  call    WPP_RECORDER_SF_d
0x140003e45  jmp     loc_140004528
0x140003e4a  mov     ecx, 0E0h
0x140003e4f  cmp     ax, cx
0x140003e52  jnz     short loc_140003DEB
0x140003e54  bt      r13w, 9
0x140003e5a  jnb     short loc_140003DEB
0x140003e5c  movzx   eax, r13w
0x140003e60  and     ax, r10w
0x140003e64  cmp     ax, cx
0x140003e67  jz      short loc_140003DEB
0x140003e69  cmp     cs:WPP_RECORDER_INITIALIZED, rsi; __annotation("TMF:",
0x140003e70  jz      loc_140003DA1
0x140003e76  mov     rcx, [rbx+598h]
0x140003e7d  mov     r9d, 59h ; 'Y'
0x140003e83  mov     r8d, ebp
0x140003e86  mov     [rsp+0A8h+var_88], r15
0x140003e8b  mov     dl, 2
0x140003e8d  call    WPP_RECORDER_SF_
0x140003e92  movzx   r9d, [rsp+0A8h+arg_0]
0x140003e9b  jmp     loc_140003DA1
0x140003ea0  mov     edx, 80h
0x140003ea5  cmp     cx, dx
0x140003ea8  jnz     short loc_140003ED8
0x140003eaa  movzx   eax, r13w
0x140003eae  and     ax, r10w
0x140003eb2  cmp     ax, dx
0x140003eb5  jz      loc_14000431E
0x140003ebb  lea     rsi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140003ec2  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140003ec9  jz      loc_140004528
0x140003ecf  lea     r9d, [rdx-25h]
0x140003ed3  jmp     loc_140003E1B
0x140003ed8  mov     eax, 140h
0x140003edd  cmp     cx, ax
0x140003ee0  jnz     loc_14000403D
0x140003ee6  mov     rax, cs:WdfFunctions_01015
0x140003eed  mov     rdx, [rbx]
0x140003ef0  mov     rcx, cs:WdfDriverGlobals
0x140003ef7  mov     rax, [rax+660h]
0x140003efe  call    _guard_dispatch_icall
0x140003f03  mov     rcx, cs:WdfFunctions_01015
0x140003f0a  mov     rdx, rax
0x140003f0d  mov     r8, [rcx+0C20h]
0x140003f14  mov     rcx, cs:WdfDriverGlobals
0x140003f1b  mov     rax, r8
0x140003f1e  call    _guard_dispatch_icall
0x140003f23  xor     edx, edx
0x140003f25  test    eax, eax
0x140003f27  jz      short loc_140003F77
0x140003f29  mov     rax, [rbx]
0x140003f2c  cmp     [rax+0F0h], dl
0x140003f32  ja      short loc_140003F77
0x140003f34  cmp     cs:WPP_RECORDER_INITIALIZED, rsi; __annotation("TMF:",
0x140003f3b  jz      loc_1400043FE
0x140003f41  lea     r9d, [rdx+5Dh]
0x140003f45  movzx   ecx, r14w
0x140003f49  mov     r8d, ebp
0x140003f4c  mov     eax, ecx
0x140003f4e  mov     dl, 2
0x140003f50  shr     ecx, 5
0x140003f53  and     eax, r12d
0x140003f56  and     ecx, 0Fh
0x140003f59  mov     [rsp+0A8h+var_78], eax
0x140003f5d  mov     dword ptr [rsp+0A8h+var_80], ecx
0x140003f61  mov     rcx, [rbx+598h]
0x140003f68  mov     [rsp+0A8h+var_88], r15
0x140003f6d  call    WPP_RECORDER_SF_dD
0x140003f72  jmp     loc_1400043FE
0x140003f77  cmp     cs:WPP_RECORDER_INITIALIZED, rsi; __annotation("TMF:",
0x140003f7e  jz      short loc_140003FB3
0x140003f80  movzx   ecx, r14w
0x140003f84  mov     r9d, 5Ch ; '\'
0x140003f8a  mov     eax, ecx
0x140003f8c  mov     r8d, ebp
0x140003f8f  shr     ecx, 5
0x140003f92  and     eax, r12d
0x140003f95  and     ecx, 0Fh
0x140003f98  mov     [rsp+0A8h+var_78], eax
0x140003f9c  mov     dword ptr [rsp+0A8h+var_80], ecx
0x140003fa0  mov     dl, 2
0x140003fa2  mov     rcx, [rbx+598h]
0x140003fa9  mov     [rsp+0A8h+var_88], r15
0x140003fae  call    WPP_RECORDER_SF_dD
0x140003fb3  mov     rax, [rbx]
0x140003fb6  bt      dword ptr [rax+0A30h], 8
0x140003fbe  jnb     short loc_140003FD3
0x140003fc0  lea     rdx, [rbx+110h]
0x140003fc7  lea     rcx, aHubhwverifierp_0; "HubHwVerifierPortLinkStateCompliance"
0x140003fce  call    HUBMISC_VerifierDbgBreak
0x140003fd3  test    cs:byte_14006ED42, r12b
0x140003fda  jz      loc_1400043FE
0x140003fe0  mov     eax, [rsp+0A8h+arg_10]
0x140003fe7  movzx   ecx, [rsp+0A8h+arg_0]
0x140003fef  mov     r8, [rbx]
0x140003ff2  movzx   r9d, word ptr [rbx+0C8h]
0x140003ffa  add     r8, 97Ch
0x140004001  mov     [rsp+0A8h+var_58], ax
0x140004006  mov     eax, [rsp+0A8h+arg_18]
0x14000400d  mov     [rsp+0A8h+var_60], ax
0x140004012  mov     eax, [rsp+0A8h+arg_8]
0x140004019  mov     word ptr [rsp+0A8h+var_68], ax
0x14000401e  mov     [rsp+0A8h+var_70], edi
0x140004022  mov     word ptr [rsp+0A8h+var_78], cx
0x140004027  mov     word ptr [rsp+0A8h+var_80], r14w
0x14000402d  mov     word ptr [rsp+0A8h+var_88], r13w
0x140004033  call    McTemplateK0qhhhqhhh_EtwWriteTransfer
0x140004038  jmp     loc_1400043FE
  ... truncated ...
```
