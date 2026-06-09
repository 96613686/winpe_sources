# HUBPDO_EvtDeviceCleanup

- ea: `0x140014f80`
- end: `0x1400153b3`
- name: `HUBPDO_EvtDeviceCleanup`
- size: `1075`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x1400024b8`
- `0x1400083b4`
- `0x14000a53c`
- `0x140014f80`
- `0x1400336a8`
- `0x14003f5b4`
- `0x140045570`
- `0x14007ee54`

## import_xrefs

- `ntoskrnl!IoAcquireRemoveLockEx` at `0x140015012`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x140015012`
- `ntoskrnl!IoReleaseRemoveLockAndWaitEx` at `0x140015065`
- `ntoskrnl!IoReleaseRemoveLockAndWaitEx` at `0x140015065`
- `ntoskrnl!KeClearEvent` at `0x14001525f`
- `ntoskrnl!KeClearEvent` at `0x14001525f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001536c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001536c`
- `ntoskrnl!PoUnregisterPowerSettingCallback` at `0x140015084`
- `ntoskrnl!PoUnregisterPowerSettingCallback` at `0x1400150f2`
- `ntoskrnl!PoUnregisterPowerSettingCallback` at `0x140015175`
- `ntoskrnl!PoUnregisterPowerSettingCallback` at `0x140015084`
- `ntoskrnl!PoUnregisterPowerSettingCallback` at `0x1400150f2`
- `ntoskrnl!PoUnregisterPowerSettingCallback` at `0x140015175`

## pseudocode

```c
void __fastcall HUBPDO_EvtDeviceCleanup(__int64 a1)
{
  __int64 v1; // rcx
  __int64 v2; // rdi
  _QWORD *v3; // rsi
  __int64 v4; // rbp
  NTSTATUS v5; // eax
  __int64 *v6; // rdx
  void *v7; // rcx
  __int64 v8; // rax
  void *v9; // rcx
  __int64 v10; // rax
  __int64 i; // rbx
  void *v12; // rcx
  NTSTATUS v13; // eax
  int v14; // edx
  __int64 v15; // rbx
  __int64 v16; // rax
  __int64 v17; // rbx
  __int64 v18; // rax
  __int64 v19; // rax
  void *v20; // rcx
  char v21; // [rsp+68h] [rbp+10h] BYREF

  v21 = 0;
  v2 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 1616))(
         WdfDriverGlobals,
         a1,
         off_14006B1D0);
  v3 = *(_QWORD **)(v2 + 24);
  v4 = v3[3];
  if ( (Microsoft_Windows_USB_USBHUB3EnableBits & 2) != 0 )
    McTemplateK0p_EtwWriteTransfer(v1, USBHUB3_ETW_EVENT_DEVICE_CLEANUP_START, 0, v3[3]);
  v5 = IoAcquireRemoveLockEx((PIO_REMOVE_LOCK)(v2 + 424), "DRIPS SR Tag", File, 1u, 0x20u);
  v6 = WPP_8beb7df92ba934db5f6899fb45b5938a_Traceguids;
  if ( v5 < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v6) = 2;
    WPP_RECORDER_SF_d(
      *(_QWORD *)(v3[1] + 1432LL),
      (_DWORD)v6,
      5,
      93,
      (__int64)WPP_8beb7df92ba934db5f6899fb45b5938a_Traceguids,
      v5);
  }
  IoReleaseRemoveLockAndWaitEx((PIO_REMOVE_LOCK)(v2 + 424), "DRIPS SR Tag", 0x20u);
  v7 = *(void **)(v2 + 408);
  if ( v7 )
  {
    PoUnregisterPowerSettingCallback(v7);
    *(_QWORD *)(v2 + 408) = 0;
    v8 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 1632))(WdfDriverGlobals, v2);
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, const char *, __int64, const char *))(WdfFunctions_01015 + 1648))(
      WdfDriverGlobals,
      v8,
      "DRIPS SR Tag",
      6778,
      "onecore\\drivers\\wdm\\usb\\usb3\\hub\\src\\hubpdo.c");
  }
  v9 = *(void **)(v2 + 416);
  if ( v9 )
  {
    PoUnregisterPowerSettingCallback(v9);
    *(_QWORD *)(v2 + 416) = 0;
    v10 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 1632))(WdfDriverGlobals, v2);
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, const char *, __int64, const char *))(WdfFunctions_01015 + 1648))(
      WdfDriverGlobals,
      v10,
      "DRIPS IO Tag",
      6785,
      "onecore\\drivers\\wdm\\usb\\usb3\\hub\\src\\hubpdo.c");
  }
  for ( i = 0; i != 5; ++i )
  {
    v12 = *(void **)(v2 + 8 * i + 272);
    if ( v12 )
    {
      v13 = PoUnregisterPowerSettingCallback(v12);
      if ( v13 < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v14) = 2;
        WPP_RECORDER_SF_d(
          *(_QWORD *)(*(_QWORD *)(v2 + 24) + 8LL),
          v14,
          5,
          92,
          (__int64)WPP_8beb7df92ba934db5f6899fb45b5938a_Traceguids,
          v13);
      }
      *(_QWORD *)(v2 + 8 * i + 272) = 0;
    }
  }
  if ( (*(_DWORD *)(v2 + 32) & 0x1000) != 0 )
    HUBIDLE_AddEvent(v2 + 72, 6006, 0);
  v21 = 0;
  v15 = *v3;
  v16 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01015 + 1632))(WdfDriverGlobals, *v3);
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, const char *, __int64, const char *))(WdfFunctions_01015 + 1640))(
    WdfDriverGlobals,
    v16,
    "ControllerPowerReference Tag",
    94,
    "onecore\\drivers\\wdm\\usb\\usb3\\hub\\src\\ucx.h");
  (*(void (__fastcall **)(_QWORD, char *))(v15 + 568))(*(_QWORD *)(v15 + 248), &v21);
  KeClearEvent((PRKEVENT)(v3 + 199));
  HUBSM_AddEvent(v3 + 64, 4063);
  HUBMISC_WaitForSignal(v3 + 199);
  HUBPDO_BillboardCleanup(v3);
  v17 = *v3;
  (*(void (__fastcall **)(_QWORD, char *))(*v3 + 576LL))(*(_QWORD *)(*v3 + 248LL), &v21);
  v18 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 1632))(WdfDriverGlobals, v17);
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, const char *, __int64, const char *))(WdfFunctions_01015 + 1648))(
    WdfDriverGlobals,
    v18,
    "ControllerPowerReference Tag",
    130,
    "onecore\\drivers\\wdm\\usb\\usb3\\hub\\src\\ucx.h");
  v3[2] = 0;
  v19 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD *))(WdfFunctions_01015 + 1632))(WdfDriverGlobals, v3);
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, const char *, __int64, const char *))(WdfFunctions_01015 + 1648))(
    WdfDriverGlobals,
    v19,
    "DSM PDO Tag",
    6845,
    "onecore\\drivers\\wdm\\usb\\usb3\\hub\\src\\hubpdo.c");
  v20 = *(void **)(v2 + 56);
  if ( v20 )
  {
    ExFreePoolWithTag(v20, 0x64334855u);
    *(_QWORD *)(v2 + 56) = 0;
  }
  if ( (Microsoft_Windows_USB_USBHUB3EnableBits & 2) != 0 )
    McTemplateK0p_EtwWriteTransfer(v20, USBHUB3_ETW_EVENT_DEVICE_CLEANUP_COMPLETE, 0, v4);
}

```

## disassembly

```asm
0x140014f80  mov     [rsp+arg_0], rbx
0x140014f85  mov     [rsp+arg_10], rbp
0x140014f8a  push    rsi
0x140014f8b  push    rdi
0x140014f8c  push    r13
0x140014f8e  push    r14
0x140014f90  push    r15
0x140014f92  sub     rsp, 30h
0x140014f96  mov     rax, cs:WdfFunctions_01015
0x140014f9d  mov     r14, rcx
0x140014fa0  mov     r8, cs:off_14006B1D0
0x140014fa7  mov     rdx, rcx
0x140014faa  mov     rcx, cs:WdfDriverGlobals
0x140014fb1  mov     [rsp+58h+arg_8], 0
0x140014fb6  mov     rax, [rax+650h]
0x140014fbd  call    _guard_dispatch_icall
0x140014fc2  test    cs:Microsoft_Windows_USB_USBHUB3EnableBits, 2
0x140014fc9  mov     rdi, rax
0x140014fcc  mov     rsi, [rax+18h]
0x140014fd0  mov     rbp, [rsi+18h]
0x140014fd4  jz      short loc_140014FE8
0x140014fd6  mov     r9, rbp
0x140014fd9  lea     rdx, USBHUB3_ETW_EVENT_DEVICE_CLEANUP_START
0x140014fe0  xor     r8d, r8d
0x140014fe3  call    McTemplateK0p_EtwWriteTransfer
0x140014fe8  mov     r13d, 20h ; ' '
0x140014fee  lea     rbx, [rdi+1A8h]
0x140014ff5  lea     r15, DripsWatchDogTag; "DRIPS SR Tag"
0x140014ffc  mov     [rsp+58h+RemlockSize], r13d; RemlockSize
0x140015001  lea     r8, File; File
0x140015008  mov     rdx, r15; Tag
0x14001500b  mov     rcx, rbx; RemoveLock
0x14001500e  lea     r9d, [r13-1Fh]; Line
0x140015012  call    cs:__imp_IoAcquireRemoveLockEx
0x140015019  nop     dword ptr [rax+rax+00h]
0x14001501e  lea     rdx, WPP_8beb7df92ba934db5f6899fb45b5938a_Traceguids
0x140015025  lea     rcx, WPP_RECORDER_INITIALIZED
0x14001502c  test    eax, eax
0x14001502e  jns     short loc_14001505C
0x140015030  cmp     cs:WPP_RECORDER_INITIALIZED, rcx; __annotation("TMF:",
0x140015037  jz      short loc_14001505C
0x140015039  mov     rcx, [rsi+8]
0x14001503d  lea     r9d, [r13+3Dh]
0x140015041  mov     [rsp+58h+var_30], eax
0x140015045  lea     r8d, [r13-1Bh]
0x140015049  mov     qword ptr [rsp+58h+RemlockSize], rdx
0x14001504e  mov     dl, 2
0x140015050  mov     rcx, [rcx+598h]
0x140015057  call    WPP_RECORDER_SF_d
0x14001505c  mov     r8d, r13d; RemlockSize
0x14001505f  mov     rdx, r15; Tag
0x140015062  mov     rcx, rbx; RemoveLock
0x140015065  call    cs:__imp_IoReleaseRemoveLockAndWaitEx
0x14001506c  nop     dword ptr [rax+rax+00h]
0x140015071  mov     rcx, [rdi+198h]; Handle
0x140015078  lea     rbx, aOnecoreDrivers_1; "onecore\\drivers\\wdm\\usb\\usb3\\hub\\"...
0x14001507f  test    rcx, rcx
0x140015082  jz      short loc_1400150E6
0x140015084  call    cs:__imp_PoUnregisterPowerSettingCallback
0x14001508b  nop     dword ptr [rax+rax+00h]
0x140015090  mov     qword ptr [rdi+198h], 0
0x14001509b  mov     rdx, rdi
0x14001509e  mov     rax, cs:WdfFunctions_01015
0x1400150a5  mov     rcx, cs:WdfDriverGlobals
0x1400150ac  mov     rax, [rax+660h]
0x1400150b3  call    _guard_dispatch_icall
0x1400150b8  mov     rcx, cs:WdfFunctions_01015
0x1400150bf  mov     rdx, rax
0x1400150c2  mov     r9d, 1A7Ah
0x1400150c8  mov     qword ptr [rsp+58h+RemlockSize], rbx
0x1400150cd  mov     r8, r15
0x1400150d0  mov     r10, [rcx+670h]
0x1400150d7  mov     rcx, cs:WdfDriverGlobals
0x1400150de  mov     rax, r10
0x1400150e1  call    _guard_dispatch_icall
0x1400150e6  mov     rcx, [rdi+1A0h]; Handle
0x1400150ed  test    rcx, rcx
0x1400150f0  jz      short loc_140015158
0x1400150f2  call    cs:__imp_PoUnregisterPowerSettingCallback
0x1400150f9  nop     dword ptr [rax+rax+00h]
0x1400150fe  mov     qword ptr [rdi+1A0h], 0
0x140015109  mov     rdx, rdi
0x14001510c  mov     rax, cs:WdfFunctions_01015
0x140015113  mov     rcx, cs:WdfDriverGlobals
0x14001511a  mov     rax, [rax+660h]
0x140015121  call    _guard_dispatch_icall
0x140015126  mov     rcx, cs:WdfFunctions_01015
0x14001512d  lea     r8, DripsWatchdogIoTag; "DRIPS IO Tag"
0x140015134  mov     rdx, rax
0x140015137  mov     qword ptr [rsp+58h+RemlockSize], rbx
0x14001513c  mov     r9d, 1A81h
0x140015142  mov     r10, [rcx+670h]
0x140015149  mov     rcx, cs:WdfDriverGlobals
0x140015150  mov     rax, r10
0x140015153  call    _guard_dispatch_icall
0x140015158  xor     ebx, ebx
0x14001515a  lea     r15, WPP_RECORDER_INITIALIZED
0x140015161  lea     r13, WPP_8beb7df92ba934db5f6899fb45b5938a_Traceguids
0x140015168  mov     rcx, [rdi+rbx*8+110h]; Handle
0x140015170  test    rcx, rcx
0x140015173  jz      short loc_1400151BC
0x140015175  call    cs:__imp_PoUnregisterPowerSettingCallback
0x14001517c  nop     dword ptr [rax+rax+00h]
0x140015181  test    eax, eax
0x140015183  jns     short loc_1400151B0
0x140015185  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x14001518c  jz      short loc_1400151B0
0x14001518e  mov     rcx, [rdi+18h]
0x140015192  mov     r9d, 5Ch ; '\'
0x140015198  mov     [rsp+58h+var_30], eax
0x14001519c  mov     dl, 2
0x14001519e  mov     qword ptr [rsp+58h+RemlockSize], r13
0x1400151a3  mov     rcx, [rcx+8]
0x1400151a7  lea     r8d, [r9-57h]
0x1400151ab  call    WPP_RECORDER_SF_d
0x1400151b0  mov     qword ptr [rdi+rbx*8+110h], 0
0x1400151bc  inc     rbx
0x1400151bf  cmp     rbx, 5
0x1400151c3  jnz     short loc_140015168
0x1400151c5  test    dword ptr [rdi+20h], 1000h
0x1400151cc  jz      short loc_1400151DF
0x1400151ce  lea     rcx, [rdi+48h]
0x1400151d2  xor     r8d, r8d
0x1400151d5  mov     edx, 1776h
0x1400151da  call    HUBIDLE_AddEvent
0x1400151df  mov     rax, cs:WdfFunctions_01015
0x1400151e6  mov     rcx, cs:WdfDriverGlobals
0x1400151ed  mov     [rsp+58h+arg_8], 0
0x1400151f2  mov     rbx, [rsi]
0x1400151f5  mov     rax, [rax+660h]
0x1400151fc  mov     rdx, rbx
0x1400151ff  call    _guard_dispatch_icall
0x140015204  mov     rcx, cs:WdfFunctions_01015
0x14001520b  lea     r15, aOnecoreDrivers_2; "onecore\\drivers\\wdm\\usb\\usb3\\hub\\"...
0x140015212  mov     rdx, rax
0x140015215  mov     qword ptr [rsp+58h+RemlockSize], r15
0x14001521a  mov     r9d, 5Eh ; '^'
0x140015220  lea     r8, ControllerPowerReferenceTag; "ControllerPowerReference Tag"
0x140015227  mov     r10, [rcx+668h]
0x14001522e  mov     rcx, cs:WdfDriverGlobals
0x140015235  mov     rax, r10
0x140015238  call    _guard_dispatch_icall
0x14001523d  mov     rax, [rbx+238h]
0x140015244  lea     rdx, [rsp+58h+arg_8]
0x140015249  mov     rcx, [rbx+0F8h]
0x140015250  call    _guard_dispatch_icall
0x140015255  lea     rbx, [rsi+638h]
0x14001525c  mov     rcx, rbx; Event
0x14001525f  call    cs:__imp_KeClearEvent
0x140015266  nop     dword ptr [rax+rax+00h]
0x14001526b  lea     rcx, [rsi+200h]
0x140015272  mov     edx, 0FDFh
0x140015277  call    HUBSM_AddEvent
0x14001527c  mov     r8, r14
0x14001527f  lea     rdx, aDeviceCleanup; "Device Cleanup"
0x140015286  mov     rcx, rbx; Object
0x140015289  call    HUBMISC_WaitForSignal
0x14001528e  mov     rcx, rsi
0x140015291  call    HUBPDO_BillboardCleanup
0x140015296  mov     rbx, [rsi]
0x140015299  lea     rdx, [rsp+58h+arg_8]
0x14001529e  mov     rax, [rbx+240h]
0x1400152a5  mov     rcx, [rbx+0F8h]
0x1400152ac  call    _guard_dispatch_icall
0x1400152b1  mov     rax, cs:WdfFunctions_01015
0x1400152b8  mov     rdx, rbx
0x1400152bb  mov     rcx, cs:WdfDriverGlobals
0x1400152c2  mov     rax, [rax+660h]
0x1400152c9  call    _guard_dispatch_icall
0x1400152ce  mov     rcx, cs:WdfFunctions_01015
0x1400152d5  lea     r8, ControllerPowerReferenceTag; "ControllerPowerReference Tag"
0x1400152dc  mov     rdx, rax
0x1400152df  mov     qword ptr [rsp+58h+RemlockSize], r15
0x1400152e4  mov     r9d, 82h
0x1400152ea  mov     r10, [rcx+670h]
0x1400152f1  mov     rcx, cs:WdfDriverGlobals
0x1400152f8  mov     rax, r10
0x1400152fb  call    _guard_dispatch_icall
0x140015300  mov     qword ptr [rsi+10h], 0
0x140015308  mov     rdx, rsi
0x14001530b  mov     rax, cs:WdfFunctions_01015
0x140015312  mov     rcx, cs:WdfDriverGlobals
0x140015319  mov     rax, [rax+660h]
0x140015320  call    _guard_dispatch_icall
0x140015325  mov     rcx, cs:WdfFunctions_01015
0x14001532c  lea     r8, PDOTag; "DSM PDO Tag"
0x140015333  mov     rdx, rax
0x140015336  mov     r9d, 1ABDh
0x14001533c  mov     r10, [rcx+670h]
0x140015343  lea     rcx, aOnecoreDrivers_1; "onecore\\drivers\\wdm\\usb\\usb3\\hub\\"...
0x14001534a  mov     qword ptr [rsp+58h+RemlockSize], rcx
0x14001534f  mov     rax, r10
0x140015352  mov     rcx, cs:WdfDriverGlobals
0x140015359  call    _guard_dispatch_icall
0x14001535e  mov     rcx, [rdi+38h]; P
0x140015362  test    rcx, rcx
0x140015365  jz      short loc_140015380
0x140015367  mov     edx, 64334855h; Tag
0x14001536c  call    cs:__imp_ExFreePoolWithTag
0x140015373  nop     dword ptr [rax+rax+00h]
0x140015378  mov     qword ptr [rdi+38h], 0
0x140015380  test    cs:Microsoft_Windows_USB_USBHUB3EnableBits, 2
0x140015387  jz      short loc_14001539B
0x140015389  mov     r9, rbp
0x14001538c  lea     rdx, USBHUB3_ETW_EVENT_DEVICE_CLEANUP_COMPLETE
0x140015393  xor     r8d, r8d
0x140015396  call    McTemplateK0p_EtwWriteTransfer
0x14001539b  mov     rbx, [rsp+58h+arg_0]
0x1400153a0  mov     rbp, [rsp+58h+arg_10]
0x1400153a5  add     rsp, 30h
0x1400153a9  pop     r15
0x1400153ab  pop     r14
0x1400153ad  pop     r13
0x1400153af  pop     rdi
0x1400153b0  pop     rsi
0x1400153b1  retn
```
