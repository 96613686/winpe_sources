# HUBFDO_SetupHubPostErrataQuery

- ea: `0x14000ed20`
- end: `0x14000f2c8`
- name: `HUBFDO_SetupHubPostErrataQuery`
- size: `1448`
- prototype: `__int64 __fastcall(PVOID Context)`
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140009db0`

## callees

- `0x140001f94`
- `0x1400024b8`
- `0x1400067ac`
- `0x14000ed20`
- `0x140033530`
- `0x1400430c0`
- `0x1400434e0`
- `0x140045530`
- `0x140045570`
- `0x140045940`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000eef1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000eef1`
- `ntoskrnl!PoRegisterPowerSettingCallback` at `0x14000f115`
- `ntoskrnl!PoRegisterPowerSettingCallback` at `0x14000f115`
- `ntoskrnl!DbgPrintEx` at `0x14000eecb`
- `ntoskrnl!DbgPrintEx` at `0x14000eecb`

## string_xrefs

- `0x14000eebe`: `UsbdHandleInfo->PendingDelete should be set here UsbdHandleInfo 0x%p\n`

## pseudocode

```c
__int64 __fastcall HUBFDO_SetupHubPostErrataQuery(char *Context)
{
  __int64 v2; // r14
  __int64 v3; // rax
  struct _DEVICE_OBJECT *v4; // rbx
  struct _DEVICE_OBJECT *v5; // rax
  ULONG v6; // r8d
  ULONG v7; // r9d
  NTSTATUS v8; // eax
  int v9; // edx
  NTSTATUS UsbCapability; // esi
  USBD_HANDLE v11; // rbx
  __int128 v12; // xmm0
  void (__fastcall *v13)(_QWORD); // rax
  int v14; // edx
  int v15; // r8d
  int v16; // eax
  bool v17; // zf
  int v18; // eax
  int v19; // edx
  __int64 v20; // rcx
  int v21; // ebx
  struct _DEVICE_OBJECT *v22; // rax
  NTSTATUS v23; // eax
  int v24; // edx
  int v25; // eax
  int v26; // edx
  int v27; // ebx
  int v28; // eax
  int v29; // edx
  ULONG *USBDHandle; // [rsp+20h] [rbp-99h]
  ULONG *USBDHandlea; // [rsp+20h] [rbp-99h]
  ULONG *USBDHandleb; // [rsp+20h] [rbp-99h]
  USBD_HANDLE v34; // [rsp+30h] [rbp-89h] BYREF
  _QWORD v35[10]; // [rsp+40h] [rbp-79h] BYREF
  __int128 v36; // [rsp+90h] [rbp-29h] BYREF
  int v37; // [rsp+A0h] [rbp-19h]
  __int128 v38; // [rsp+A8h] [rbp-11h] BYREF
  __int128 v39; // [rsp+B8h] [rbp-1h]
  int v40; // [rsp+C8h] [rbp+Fh]
  UCHAR OutputBuffer[16]; // [rsp+D0h] [rbp+17h] BYREF

  v34 = 0;
  v40 = 0;
  v37 = 0;
  v38 = 0;
  v39 = 0;
  v36 = 0;
  memset(v35, 0, 0x44u);
  v2 = *((_QWORD *)Context + 2);
  *(_OWORD *)OutputBuffer = 0;
  v3 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 336))(WdfDriverGlobals, v2);
  v4 = (struct _DEVICE_OBJECT *)(*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 1424))(
                                  WdfDriverGlobals,
                                  v3);
  v5 = (struct _DEVICE_OBJECT *)(*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 248))(
                                  WdfDriverGlobals,
                                  v2);
  v8 = USBD_CreateHandle(v5, v4, v6, v7, &v34);
  LOBYTE(UsbCapability) = v8;
  if ( v8 < 0 )
    goto LABEL_14;
  v11 = v34;
  if ( USBD_QueryUsbCapability(v34, &GUID_USB_CAPABILITY_HIGH_BANDWIDTH_ISOCH, 4u, (PUCHAR)Context + 156, USBDHandle) < 0 )
    *((_DWORD *)Context + 39) = 0;
  if ( USBD_QueryUsbCapability(v11, &GUID_USB_CAPABILITY_MICROSOFT_MAUSBHOST, 0x10u, OutputBuffer, USBDHandlea) >= 0 )
  {
    v12 = *(_OWORD *)OutputBuffer;
    Context[201] = 1;
    *(_OWORD *)(Context + 780) = v12;
  }
  UsbCapability = USBD_QueryUsbCapability(v11, &GUID_USB_CAPABILITY_SELECTIVE_SUSPEND, 0, 0, USBDHandleb);
  *((_BYTE *)v11 + 225) = 1;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v11 + 55, 0xFFFFFFFF) <= 1 )
  {
    if ( *((_BYTE *)v11 + 225) )
    {
      v13 = (void (__fastcall *)(_QWORD))*((_QWORD *)v11 + 14);
      if ( v13 )
        v13(*((_QWORD *)v11 + 6));
      ExFreePoolWithTag(v11, *((_DWORD *)v11 + 16));
    }
    else if ( g_EnableDbgPrints )
    {
      DbgPrintEx(0x4Du, 0, "UsbdHandleInfo->PendingDelete should be set here UsbdHandleInfo 0x%p\n", v11);
    }
  }
  if ( UsbCapability < 0 )
  {
LABEL_14:
    _InterlockedOr((volatile signed __int32 *)Context + 10, 0x80u);
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v9) = 2;
      WPP_RECORDER_SF_d(
        *((_QWORD *)Context + 317),
        v9,
        3,
        96,
        (__int64)WPP_2e0dbc61611a37aa5578b122392b1411_Traceguids,
        UsbCapability);
    }
  }
  if ( (*((_DWORD *)Context + 10) & 0x80u) != 0 )
    goto LABEL_44;
  v14 = *((_DWORD *)Context + 11);
  if ( (v14 & 1) != 0 || !Context[260] )
    goto LABEL_44;
  *(_QWORD *)&v38 = 0x200000024LL;
  *((_QWORD *)&v39 + 1) = 2;
  v40 = 2;
  v15 = (v14 & 0x400) != 0 ? 0x3E8 : 0;
  v16 = (v14 & 0x400) != 0 ? 1000 : 50;
  if ( (v14 & 0x800) != 0 )
  {
    v16 = 5000;
    v15 = 5000;
  }
  v17 = Context[240] == 0;
  HIDWORD(v38) = v16;
  *((_DWORD *)Context + 648) = v16;
  *((_DWORD *)Context + 649) = v15;
  *(_QWORD *)&v39 = 0x200000002LL;
  DWORD2(v38) = 3;
  if ( v17 || (v14 & 0x20) != 0 )
    HIDWORD(v39) = 2;
  v18 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int128 *))(WdfFunctions_01015 + 368))(
          WdfDriverGlobals,
          v2,
          &v38);
  v21 = v18;
  if ( v18 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v19) = 2;
      WPP_RECORDER_SF_d(
        *((_QWORD *)Context + 317),
        v19,
        3,
        97,
        (__int64)WPP_2e0dbc61611a37aa5578b122392b1411_Traceguids,
        v18);
    }
    if ( v21 == -1073741101 && *((_DWORD *)Context + 64) == 3 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v19) = 3;
        WPP_RECORDER_SF_(
          *((_QWORD *)Context + 317),
          v19,
          3,
          98,
          (__int64)WPP_2e0dbc61611a37aa5578b122392b1411_Traceguids);
      }
      if ( (*((_DWORD *)Context + 652) & 8) != 0 )
        HUBMISC_VerifierDbgBreak("HubHwVerifierNoSelectiveSuspendSupport", Context + 1280);
      if ( (byte_14006ED42 & 8) != 0 )
        McTemplateK0pq_EtwWriteTransfer(
          v20,
          USBHUB3_ETW_EVENT_HUB_SELECTIVE_SUSPEND_NOT_SUPPORTED,
          Context + 2428,
          *((_QWORD *)Context + 31),
          -1073741101);
    }
LABEL_44:
    v37 = 257;
    *((_DWORD *)Context + 654) = 5;
    *(_QWORD *)&v36 = 0x500000014LL;
    *((_QWORD *)&v36 + 1) = 1;
    v28 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int128 *))(WdfFunctions_01015 + 376))(
            WdfDriverGlobals,
            v2,
            &v36);
    v27 = v28;
    if ( v28 < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v29) = 2;
        WPP_RECORDER_SF_d(
          *((_QWORD *)Context + 317),
          v29,
          3,
          101,
          (__int64)WPP_2e0dbc61611a37aa5578b122392b1411_Traceguids,
          v28);
      }
      v27 = 0;
    }
    return ((v27 >> 31) & 0xFFFFFFF8) + 2053;
  }
  _InterlockedOr((volatile signed __int32 *)Context + 10, 0x4000000u);
  v22 = (struct _DEVICE_OBJECT *)(*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 248))(
                                   WdfDriverGlobals,
                                   v2);
  v23 = PoRegisterPowerSettingCallback(
          v22,
          &GUID_POWER_HUB_SELECTIVE_SUSPEND_TIMEOUT,
          (PPOWER_SETTING_CALLBACK)HUBFDO_PowerSettingCallback,
          Context,
          (PVOID *)Context + 323);
  if ( v23 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v24) = 2;
      WPP_RECORDER_SF_d(
        *((_QWORD *)Context + 317),
        v24,
        3,
        99,
        (__int64)WPP_2e0dbc61611a37aa5578b122392b1411_Traceguids,
        v23);
    }
    *((_QWORD *)Context + 323) = 0;
  }
  if ( Context[240] && (*((_DWORD *)Context + 11) & 0x20) == 0 )
    goto LABEL_44;
  memset(v35, 0, 0x48u);
  v35[1] = HUBFDO_EvtPostPoFxRegisterDevice;
  LODWORD(v35[0]) = 72;
  v35[2] = HUBFDO_EvtPrePoFxUnregisterDevice;
  v25 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD *))(WdfFunctions_01015 + 3400))(
          WdfDriverGlobals,
          v2,
          v35);
  v27 = v25;
  if ( v25 >= 0 )
    goto LABEL_44;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v26) = 2;
    WPP_RECORDER_SF_d(
      *((_QWORD *)Context + 317),
      v26,
      3,
      100,
      (__int64)WPP_2e0dbc61611a37aa5578b122392b1411_Traceguids,
      v25);
  }
  return ((v27 >> 31) & 0xFFFFFFF8) + 2053;
}

```

## disassembly

```asm
0x14000ed20  mov     [rsp-8+arg_8], rbx
0x14000ed25  mov     [rsp-8+arg_10], rsi
0x14000ed2a  push    rbp
0x14000ed2b  push    rdi
0x14000ed2c  push    r12
0x14000ed2e  push    r13
0x14000ed30  push    r14
0x14000ed32  lea     rbp, [rsp-37h]
0x14000ed37  sub     rsp, 0F0h
0x14000ed3e  mov     rax, cs:__security_cookie
0x14000ed45  xor     rax, rsp
0x14000ed48  mov     [rbp+57h+var_30], rax
0x14000ed4c  xor     eax, eax
0x14000ed4e  mov     [rsp+110h+var_E0], 0
0x14000ed57  xorps   xmm0, xmm0
0x14000ed5a  mov     [rbp+57h+var_48], eax
0x14000ed5d  mov     rdi, rcx
0x14000ed60  mov     [rbp+57h+var_70], eax
0x14000ed63  xor     edx, edx; Val
0x14000ed65  mov     [rbp+57h+var_CC], eax
0x14000ed68  lea     r8d, [rax+44h]; Size
0x14000ed6c  lea     rcx, [rbp+57h+var_D0]; void *
0x14000ed70  movups  [rbp+57h+var_68], xmm0
0x14000ed74  movups  [rbp+57h+var_58], xmm0
0x14000ed78  movups  [rbp+57h+var_80], xmm0
0x14000ed7c  call    memset
0x14000ed81  mov     rax, cs:WdfFunctions_01015
0x14000ed88  xorps   xmm0, xmm0
0x14000ed8b  mov     r14, [rdi+10h]
0x14000ed8f  mov     rcx, cs:WdfDriverGlobals
0x14000ed96  mov     rdx, r14
0x14000ed99  movups  xmmword ptr [rbp+57h+OutputBuffer], xmm0
0x14000ed9d  mov     rax, [rax+150h]
0x14000eda4  call    _guard_dispatch_icall
0x14000eda9  mov     rcx, cs:WdfFunctions_01015
0x14000edb0  mov     rdx, rax
0x14000edb3  mov     r8, [rcx+590h]
0x14000edba  mov     rcx, cs:WdfDriverGlobals
0x14000edc1  mov     rax, r8
0x14000edc4  call    _guard_dispatch_icall
0x14000edc9  mov     rcx, cs:WdfFunctions_01015
0x14000edd0  mov     rbx, rax
0x14000edd3  mov     rdx, r14
0x14000edd6  mov     rax, [rcx+0F8h]
0x14000eddd  mov     rcx, cs:WdfDriverGlobals
0x14000ede4  call    _guard_dispatch_icall
0x14000ede9  lea     rcx, [rsp+110h+var_E0]
0x14000edee  mov     rdx, rbx; TargetDeviceObject
0x14000edf1  mov     [rsp+110h+USBDHandle], rcx; ResultLength
0x14000edf6  mov     rcx, rax; DeviceObject
0x14000edf9  call    USBD_CreateHandle
0x14000edfe  mov     esi, eax
0x14000ee00  lea     rcx, WPP_2e0dbc61611a37aa5578b122392b1411_Traceguids
0x14000ee07  lea     rax, WPP_RECORDER_INITIALIZED
0x14000ee0e  mov     r13d, 3
0x14000ee14  lea     r12d, [r13-1]
0x14000ee18  test    esi, esi
0x14000ee1a  js      loc_14000EF0F
0x14000ee20  mov     rbx, [rsp+110h+var_E0]
0x14000ee25  lea     rsi, [rdi+9Ch]
0x14000ee2c  mov     r9, rsi; OutputBuffer
0x14000ee2f  lea     r8d, [r13+1]; OutputBufferLength
0x14000ee33  mov     rcx, rbx; USBDHandle
0x14000ee36  lea     rdx, GUID_USB_CAPABILITY_HIGH_BANDWIDTH_ISOCH; CapabilityType
0x14000ee3d  call    USBD_QueryUsbCapability
0x14000ee42  test    eax, eax
0x14000ee44  jns     short loc_14000EE4C
0x14000ee46  mov     dword ptr [rsi], 0
0x14000ee4c  lea     r9, [rbp+57h+OutputBuffer]; OutputBuffer
0x14000ee50  mov     r8d, 10h; OutputBufferLength
0x14000ee56  lea     rdx, GUID_USB_CAPABILITY_MICROSOFT_MAUSBHOST; CapabilityType
0x14000ee5d  mov     rcx, rbx; USBDHandle
0x14000ee60  call    USBD_QueryUsbCapability
0x14000ee65  test    eax, eax
0x14000ee67  js      short loc_14000EE7C
0x14000ee69  movups  xmm0, xmmword ptr [rbp+57h+OutputBuffer]
0x14000ee6d  mov     byte ptr [rdi+0C9h], 1
0x14000ee74  movdqu  xmmword ptr [rdi+30Ch], xmm0
0x14000ee7c  xor     r9d, r9d; OutputBuffer
0x14000ee7f  lea     rdx, GUID_USB_CAPABILITY_SELECTIVE_SUSPEND; CapabilityType
0x14000ee86  xor     r8d, r8d; OutputBufferLength
0x14000ee89  mov     rcx, rbx; USBDHandle
0x14000ee8c  call    USBD_QueryUsbCapability
0x14000ee91  mov     esi, eax
0x14000ee93  mov     byte ptr [rbx+0E1h], 1
0x14000ee9a  or      eax, 0FFFFFFFFh
0x14000ee9d  lock xadd [rbx+0DCh], eax
0x14000eea5  sub     eax, 1
0x14000eea8  jg      short loc_14000EEFD
0x14000eeaa  cmp     byte ptr [rbx+0E1h], 0
0x14000eeb1  jnz     short loc_14000EED9
0x14000eeb3  cmp     cs:g_EnableDbgPrints, 0
0x14000eeba  jz      short loc_14000EEFD
0x14000eebc  xor     edx, edx; Level
0x14000eebe  lea     r8, Format; "UsbdHandleInfo->PendingDelete should be"...
0x14000eec5  mov     r9, rbx
0x14000eec8  lea     ecx, [rdx+4Dh]; ComponentId
0x14000eecb  call    cs:__imp_DbgPrintEx
0x14000eed2  nop     dword ptr [rax+rax+00h]
0x14000eed7  jmp     short loc_14000EEFD
0x14000eed9  mov     rax, [rbx+70h]
0x14000eedd  test    rax, rax
0x14000eee0  jz      short loc_14000EEEB
0x14000eee2  mov     rcx, [rbx+30h]
0x14000eee6  call    _guard_dispatch_icall
0x14000eeeb  mov     edx, [rbx+40h]; Tag
0x14000eeee  mov     rcx, rbx; P
0x14000eef1  call    cs:__imp_ExFreePoolWithTag
0x14000eef8  nop     dword ptr [rax+rax+00h]
0x14000eefd  test    esi, esi
0x14000eeff  jns     short loc_14000EF41
0x14000ef01  lea     rax, WPP_RECORDER_INITIALIZED
0x14000ef08  lea     rcx, WPP_2e0dbc61611a37aa5578b122392b1411_Traceguids
0x14000ef0f  lock or dword ptr [rdi+28h], 80h
0x14000ef17  cmp     cs:WPP_RECORDER_INITIALIZED, rax; __annotation("TMF:",
0x14000ef1e  jz      short loc_14000EF41
0x14000ef20  mov     [rsp+110h+var_E8], esi
0x14000ef24  mov     r9d, 60h ; '`'
0x14000ef2a  mov     [rsp+110h+USBDHandle], rcx
0x14000ef2f  mov     r8d, r13d
0x14000ef32  mov     rcx, [rdi+9E8h]
0x14000ef39  mov     dl, r12b
0x14000ef3c  call    WPP_RECORDER_SF_d
0x14000ef41  mov     eax, [rdi+28h]
0x14000ef44  test    al, al
0x14000ef46  js      loc_14000F20E
0x14000ef4c  mov     edx, [rdi+2Ch]
0x14000ef4f  test    dl, 1
0x14000ef52  jnz     loc_14000F20E
0x14000ef58  cmp     byte ptr [rdi+104h], 0
0x14000ef5f  jz      loc_14000F20E
0x14000ef65  mov     ecx, edx
0x14000ef67  mov     dword ptr [rbp+57h+var_68], 24h ; '$'
0x14000ef6e  and     ecx, 400h
0x14000ef74  mov     qword ptr [rbp+57h+var_58+8], r12
0x14000ef78  mov     eax, ecx
0x14000ef7a  mov     [rbp+57h+var_48], r12d
0x14000ef7e  neg     eax
0x14000ef80  mov     dword ptr [rbp+57h+var_68+4], r12d
0x14000ef84  sbb     r8d, r8d
0x14000ef87  and     r8d, 3E8h
0x14000ef8e  neg     ecx
0x14000ef90  sbb     eax, eax
0x14000ef92  and     eax, 3B6h
0x14000ef97  add     eax, 32h ; '2'
0x14000ef9a  bt      edx, 0Bh
0x14000ef9e  jnb     short loc_14000EFA8
0x14000efa0  mov     eax, 1388h
0x14000efa5  mov     r8d, eax
0x14000efa8  cmp     byte ptr [rdi+0F0h], 0
0x14000efaf  mov     dword ptr [rbp+57h+var_68+0Ch], eax
0x14000efb2  mov     [rdi+0A20h], eax
0x14000efb8  mov     [rdi+0A24h], r8d
0x14000efbf  mov     dword ptr [rbp+57h+var_58], r12d
0x14000efc3  mov     dword ptr [rbp+57h+var_58+4], r12d
0x14000efc7  mov     dword ptr [rbp+57h+var_68+8], r13d
0x14000efcb  jz      short loc_14000EFD2
0x14000efcd  test    dl, 20h
0x14000efd0  jz      short loc_14000EFD6
0x14000efd2  mov     dword ptr [rbp+57h+var_58+0Ch], r12d
0x14000efd6  mov     rax, cs:WdfFunctions_01015
0x14000efdd  lea     r8, [rbp+57h+var_68]
0x14000efe1  mov     rcx, cs:WdfDriverGlobals
0x14000efe8  mov     rdx, r14
0x14000efeb  mov     rax, [rax+170h]
0x14000eff2  call    _guard_dispatch_icall
0x14000eff7  mov     ebx, eax
0x14000eff9  test    eax, eax
0x14000effb  jns     loc_14000F0D0
0x14000f001  lea     rsi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000f008  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14000f00f  jz      short loc_14000F039
0x14000f011  mov     rcx, [rdi+9E8h]
0x14000f018  mov     r9d, 61h ; 'a'
0x14000f01e  mov     [rsp+110h+var_E8], eax
0x14000f022  mov     r8d, r13d
0x14000f025  lea     rax, WPP_2e0dbc61611a37aa5578b122392b1411_Traceguids
0x14000f02c  mov     dl, r12b
0x14000f02f  mov     [rsp+110h+USBDHandle], rax
0x14000f034  call    WPP_RECORDER_SF_d
0x14000f039  cmp     ebx, 0C00002D3h
0x14000f03f  jnz     loc_14000F215
0x14000f045  cmp     [rdi+100h], r13d
0x14000f04c  jnz     loc_14000F215
0x14000f052  cmp     cs:WPP_RECORDER_INITIALIZED, rsi; __annotation("TMF:",
0x14000f059  jz      short loc_14000F07F
0x14000f05b  mov     rcx, [rdi+9E8h]
0x14000f062  lea     rax, WPP_2e0dbc61611a37aa5578b122392b1411_Traceguids
0x14000f069  mov     r9d, 62h ; 'b'
0x14000f06f  mov     [rsp+110h+USBDHandle], rax
0x14000f074  mov     r8d, r13d
0x14000f077  mov     dl, r13b
0x14000f07a  call    WPP_RECORDER_SF_
0x14000f07f  mov     eax, [rdi+0A30h]
0x14000f085  test    al, 8
0x14000f087  jz      short loc_14000F09C
0x14000f089  lea     rdx, [rdi+500h]
0x14000f090  lea     rcx, aHubhwverifiern; "HubHwVerifierNoSelectiveSuspendSupport"
0x14000f097  call    HUBMISC_VerifierDbgBreak
0x14000f09c  test    cs:byte_14006ED42, 8
0x14000f0a3  jz      loc_14000F215
0x14000f0a9  mov     r9, [rdi+0F8h]
0x14000f0b0  lea     r8, [rdi+97Ch]
0x14000f0b7  lea     rdx, USBHUB3_ETW_EVENT_HUB_SELECTIVE_SUSPEND_NOT_SUPPORTED
0x14000f0be  mov     dword ptr [rsp+110h+USBDHandle], 0C00002D3h
0x14000f0c6  call    McTemplateK0pq_EtwWriteTransfer
0x14000f0cb  jmp     loc_14000F215
0x14000f0d0  lock or dword ptr [rdi+28h], 4000000h
0x14000f0d8  mov     rax, cs:WdfFunctions_01015
0x14000f0df  mov     rdx, r14
0x14000f0e2  mov     rcx, cs:WdfDriverGlobals
0x14000f0e9  mov     rax, [rax+0F8h]
0x14000f0f0  call    _guard_dispatch_icall
0x14000f0f5  lea     rbx, [rdi+0A18h]
0x14000f0fc  mov     r9, rdi; Context
0x14000f0ff  lea     r8, HUBFDO_PowerSettingCallback; Callback
0x14000f106  mov     [rsp+110h+USBDHandle], rbx; Handle
0x14000f10b  lea     rdx, GUID_POWER_HUB_SELECTIVE_SUSPEND_TIMEOUT; SettingGuid
0x14000f112  mov     rcx, rax; DeviceObject
0x14000f115  call    cs:__imp_PoRegisterPowerSettingCallback
0x14000f11c  nop     dword ptr [rax+rax+00h]
0x14000f121  test    eax, eax
0x14000f123  jns     short loc_14000F166
0x14000f125  lea     rsi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000f12c  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14000f133  jz      short loc_14000F15D
0x14000f135  mov     rcx, [rdi+9E8h]
0x14000f13c  mov     r9d, 63h ; 'c'
0x14000f142  mov     [rsp+110h+var_E8], eax
0x14000f146  mov     r8d, r13d
0x14000f149  lea     rax, WPP_2e0dbc61611a37aa5578b122392b1411_Traceguids
0x14000f150  mov     dl, r12b
0x14000f153  mov     [rsp+110h+USBDHandle], rax
0x14000f158  call    WPP_RECORDER_SF_d
0x14000f15d  mov     qword ptr [rbx], 0
0x14000f164  jmp     short loc_14000F16D
0x14000f166  lea     rsi, WPP_RECORDER_INITIALIZED
0x14000f16d  cmp     byte ptr [rdi+0F0h], 0
0x14000f174  jz      short loc_14000F181
0x14000f176  mov     eax, [rdi+2Ch]
0x14000f179  test    al, 20h
0x14000f17b  jz      loc_14000F215
0x14000f181  mov     ebx, 48h ; 'H'
0x14000f186  lea     rcx, [rbp+57h+var_D0]; void *
0x14000f18a  mov     r8d, ebx; Size
0x14000f18d  xor     edx, edx; Val
0x14000f18f  call    memset
0x14000f194  mov     rcx, cs:WdfDriverGlobals
0x14000f19b  lea     rax, HUBFDO_EvtPostPoFxRegisterDevice
0x14000f1a2  mov     [rbp+57h+var_C8], rax
0x14000f1a6  lea     r8, [rbp+57h+var_D0]
0x14000f1aa  lea     rax, HUBFDO_EvtPrePoFxUnregisterDevice
0x14000f1b1  mov     [rbp+57h+var_D0], ebx
0x14000f1b4  mov     [rbp+57h+var_C0], rax
0x14000f1b8  mov     rdx, r14
0x14000f1bb  mov     rax, cs:WdfFunctions_01015
0x14000f1c2  mov     rax, [rax+0D48h]
0x14000f1c9  call    _guard_dispatch_icall
0x14000f1ce  mov     ebx, eax
0x14000f1d0  test    eax, eax
0x14000f1d2  jns     short loc_14000F215
0x14000f1d4  cmp     cs:WPP_RECORDER_INITIALIZED, rsi; __annotation("TMF:",
0x14000f1db  jz      loc_14000F293
0x14000f1e1  mov     rcx, [rdi+9E8h]
0x14000f1e8  mov     r9d, 64h ; 'd'
0x14000f1ee  mov     [rsp+110h+var_E8], eax
0x14000f1f2  mov     r8d, r13d
0x14000f1f5  lea     rax, WPP_2e0dbc61611a37aa5578b122392b1411_Traceguids
0x14000f1fc  mov     dl, r12b
0x14000f1ff  mov     [rsp+110h+USBDHandle], rax
0x14000f204  call    WPP_RECORDER_SF_d
0x14000f209  jmp     loc_14000F293
0x14000f20e  lea     rsi, WPP_RECORDER_INITIALIZED
0x14000f215  mov     ecx, 5
0x14000f21a  mov     [rbp+57h+var_70], 101h
0x14000f221  mov     [rdi+0A38h], ecx
0x14000f227  lea     r8, [rbp+57h+var_80]
0x14000f22b  mov     rax, cs:WdfFunctions_01015
0x14000f232  mov     rdx, r14
0x14000f235  mov     dword ptr [rbp+57h+var_80+4], ecx
0x14000f238  mov     rcx, cs:WdfDriverGlobals
0x14000f23f  mov     dword ptr [rbp+57h+var_80], 14h
0x14000f246  mov     qword ptr [rbp+57h+var_80+8], 1
0x14000f24e  mov     rax, [rax+178h]
0x14000f255  call    _guard_dispatch_icall
0x14000f25a  mov     ebx, eax
0x14000f25c  test    eax, eax
0x14000f25e  jns     short loc_14000F293
0x14000f260  cmp     cs:WPP_RECORDER_INITIALIZED, rsi; __annotation("TMF:",
0x14000f267  jz      short loc_14000F291
0x14000f269  mov     rcx, [rdi+9E8h]
0x14000f270  mov     r9d, 65h ; 'e'
0x14000f276  mov     [rsp+110h+var_E8], eax
0x14000f27a  mov     r8d, r13d
0x14000f27d  lea     rax, WPP_2e0dbc61611a37aa5578b122392b1411_Traceguids
0x14000f284  mov     dl, r12b
0x14000f287  mov     [rsp+110h+USBDHandle], rax
0x14000f28c  call    WPP_RECORDER_SF_d
0x14000f291  xor     ebx, ebx
0x14000f293  sar     ebx, 1Fh
  ... truncated ...
```
