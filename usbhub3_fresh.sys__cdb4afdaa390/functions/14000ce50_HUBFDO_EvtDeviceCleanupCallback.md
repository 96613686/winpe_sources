# HUBFDO_EvtDeviceCleanupCallback

- ea: `0x14000ce50`
- end: `0x14000d115`
- name: `HUBFDO_EvtDeviceCleanupCallback`
- size: `709`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x1400024b8`
- `0x1400083b4`
- `0x14000a53c`
- `0x14000ce50`
- `0x1400336a8`
- `0x140045570`
- `0x14008fc38`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000d0a4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d0a4`
- `ntoskrnl!KeResetEvent` at `0x14000d011`
- `ntoskrnl!KeResetEvent` at `0x14000d011`
- `ntoskrnl!PoUnregisterPowerSettingCallback` at `0x14000cec8`
- `ntoskrnl!PoUnregisterPowerSettingCallback` at `0x14000cf19`
- `ntoskrnl!PoUnregisterPowerSettingCallback` at `0x14000cf6a`
- `ntoskrnl!PoUnregisterPowerSettingCallback` at `0x14000cfbb`
- `ntoskrnl!PoUnregisterPowerSettingCallback` at `0x14000cec8`
- `ntoskrnl!PoUnregisterPowerSettingCallback` at `0x14000cf19`
- `ntoskrnl!PoUnregisterPowerSettingCallback` at `0x14000cf6a`
- `ntoskrnl!PoUnregisterPowerSettingCallback` at `0x14000cfbb`
- `WppRecorder!imp_WppRecorderLogDelete` at `0x14000d0be`
- `WppRecorder!imp_WppRecorderLogDelete` at `0x14000d0be`
- `USBD!USBD_ReleaseHubNumber` at `0x14000d0d1`
- `USBD!USBD_ReleaseHubNumber` at `0x14000d0d1`

## pseudocode

```c
__int64 __fastcall HUBFDO_EvtDeviceCleanupCallback(__int64 a1)
{
  __int64 v1; // rax
  __int64 v2; // rcx
  __int64 v3; // rdi
  void *v4; // rcx
  NTSTATUS v5; // eax
  int v6; // edx
  void *v7; // rcx
  NTSTATUS v8; // eax
  int v9; // edx
  void *v10; // rcx
  NTSTATUS v11; // eax
  int v12; // edx
  void *v13; // rcx
  NTSTATUS v14; // eax
  int v15; // edx
  void *v16; // rcx
  __int64 result; // rax
  __int64 v18; // rcx
  __int64 v19; // [rsp+28h] [rbp-10h]
  NTSTATUS v20; // [rsp+28h] [rbp-10h]

  v1 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 1616))(
         WdfDriverGlobals,
         a1,
         off_14006B270);
  v3 = v1;
  if ( (Microsoft_Windows_USB_USBHUB3EnableBits & 2) != 0 )
    McTemplateK0p_EtwWriteTransfer(v2, "'", 0, *(_QWORD *)(v1 + 248));
  TUNNEL_CloseAllUsb4RemoteTargets(v3);
  v4 = *(void **)(v3 + 2656);
  if ( v4 )
  {
    v5 = PoUnregisterPowerSettingCallback(v4);
    if ( v5 < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v20 = v5;
      LOBYTE(v6) = 2;
      WPP_RECORDER_SF_d(
        *(_QWORD *)(v3 + 2536),
        v6,
        3,
        53,
        (__int64)WPP_2e0dbc61611a37aa5578b122392b1411_Traceguids,
        v20);
    }
    *(_QWORD *)(v3 + 2656) = 0;
  }
  v7 = *(void **)(v3 + 2784);
  if ( v7 )
  {
    v8 = PoUnregisterPowerSettingCallback(v7);
    if ( v8 < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LODWORD(v19) = v8;
      LOBYTE(v9) = 2;
      WPP_RECORDER_SF_d(
        *(_QWORD *)(v3 + 2536),
        v9,
        3,
        54,
        (__int64)WPP_2e0dbc61611a37aa5578b122392b1411_Traceguids,
        v19);
    }
    *(_QWORD *)(v3 + 2784) = 0;
  }
  v10 = *(void **)(v3 + 2584);
  if ( v10 )
  {
    v11 = PoUnregisterPowerSettingCallback(v10);
    if ( v11 < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LODWORD(v19) = v11;
      LOBYTE(v12) = 2;
      WPP_RECORDER_SF_d(
        *(_QWORD *)(v3 + 2536),
        v12,
        3,
        55,
        (__int64)WPP_2e0dbc61611a37aa5578b122392b1411_Traceguids,
        v19);
    }
    *(_QWORD *)(v3 + 2584) = 0;
  }
  v13 = *(void **)(v3 + 2576);
  if ( v13 )
  {
    v14 = PoUnregisterPowerSettingCallback(v13);
    if ( v14 < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LODWORD(v19) = v14;
      LOBYTE(v15) = 2;
      WPP_RECORDER_SF_d(
        *(_QWORD *)(v3 + 2536),
        v15,
        3,
        56,
        (__int64)WPP_2e0dbc61611a37aa5578b122392b1411_Traceguids,
        v19);
    }
    *(_QWORD *)(v3 + 2576) = 0;
  }
  if ( (*(_DWORD *)(v3 + 40) & 0x20) != 0 )
  {
    KeResetEvent((PRKEVENT)(v3 + 1168));
    HUBSM_AddEvent(v3 + 1280, 2027);
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 1632))(WdfDriverGlobals, v3);
    HUBMISC_WaitForSignal((PVOID)(v3 + 1168));
  }
  if ( *(_QWORD *)(v3 + 2272) )
  {
    (*(void (**)(void))(v3 + 528))();
    (*(void (__fastcall **)(_QWORD))(v3 + 512))(*(_QWORD *)(v3 + 2272));
    *(_QWORD *)(v3 + 2272) = 0;
  }
  v16 = *(void **)(v3 + 1272);
  if ( v16 )
    ExFreePoolWithTag(v16, 0x68334855u);
  result = imp_WppRecorderLogDelete(WPP_GLOBAL_Control, *(_QWORD *)(v3 + 2536));
  v18 = *(unsigned int *)(v3 + 96);
  if ( (_DWORD)v18 )
  {
    result = USBD_ReleaseHubNumber();
    *(_DWORD *)(v3 + 96) = 0;
  }
  if ( (Microsoft_Windows_USB_USBHUB3EnableBits & 2) != 0 )
    return McTemplateK0p_EtwWriteTransfer(v18, USBHUB3_ETW_EVENT_HUB_CLEANUP_COMPLETE, 0, *(_QWORD *)(v3 + 248));
  return result;
}

```

## disassembly

```asm
0x14000ce50  mov     [rsp+arg_0], rbx
0x14000ce55  mov     [rsp+arg_8], rdi
0x14000ce5a  push    r14
0x14000ce5c  sub     rsp, 30h
0x14000ce60  mov     rax, cs:WdfFunctions_01015
0x14000ce67  mov     rdx, rcx
0x14000ce6a  mov     r8, cs:off_14006B270
0x14000ce71  mov     rcx, cs:WdfDriverGlobals
0x14000ce78  mov     rax, [rax+650h]
0x14000ce7f  call    _guard_dispatch_icall
0x14000ce84  test    cs:Microsoft_Windows_USB_USBHUB3EnableBits, 2
0x14000ce8b  mov     rdi, rax
0x14000ce8e  jz      short loc_14000CEA6
0x14000ce90  mov     r9, [rax+0F8h]
0x14000ce97  lea     rdx, USBHUB3_ETW_EVENT_HUB_CLEANUP_START; "'"
0x14000ce9e  xor     r8d, r8d
0x14000cea1  call    McTemplateK0p_EtwWriteTransfer
0x14000cea6  mov     rcx, rdi
0x14000cea9  call    TUNNEL_CloseAllUsb4RemoteTargets
0x14000ceae  mov     rcx, [rdi+0A60h]; Handle
0x14000ceb5  lea     rbx, WPP_RECORDER_INITIALIZED
0x14000cebc  lea     r14, WPP_2e0dbc61611a37aa5578b122392b1411_Traceguids
0x14000cec3  test    rcx, rcx
0x14000cec6  jz      short loc_14000CF0D
0x14000cec8  call    cs:__imp_PoUnregisterPowerSettingCallback
0x14000cecf  nop     dword ptr [rax+rax+00h]
0x14000ced4  test    eax, eax
0x14000ced6  jns     short loc_14000CF02
0x14000ced8  cmp     cs:WPP_RECORDER_INITIALIZED, rbx; __annotation("TMF:",
0x14000cedf  jz      short loc_14000CF02
0x14000cee1  mov     rcx, [rdi+9E8h]
0x14000cee8  mov     r9d, 35h ; '5'
0x14000ceee  mov     [rsp+38h+var_10], eax
0x14000cef2  mov     dl, 2
0x14000cef4  mov     [rsp+38h+var_18], r14
0x14000cef9  lea     r8d, [r9-32h]
0x14000cefd  call    WPP_RECORDER_SF_d
0x14000cf02  mov     qword ptr [rdi+0A60h], 0
0x14000cf0d  mov     rcx, [rdi+0AE0h]; Handle
0x14000cf14  test    rcx, rcx
0x14000cf17  jz      short loc_14000CF5E
0x14000cf19  call    cs:__imp_PoUnregisterPowerSettingCallback
0x14000cf20  nop     dword ptr [rax+rax+00h]
0x14000cf25  test    eax, eax
0x14000cf27  jns     short loc_14000CF53
0x14000cf29  cmp     cs:WPP_RECORDER_INITIALIZED, rbx; __annotation("TMF:",
0x14000cf30  jz      short loc_14000CF53
0x14000cf32  mov     rcx, [rdi+9E8h]
0x14000cf39  mov     r9d, 36h ; '6'
0x14000cf3f  mov     [rsp+38h+var_10], eax
0x14000cf43  mov     dl, 2
0x14000cf45  mov     [rsp+38h+var_18], r14
0x14000cf4a  lea     r8d, [r9-33h]
0x14000cf4e  call    WPP_RECORDER_SF_d
0x14000cf53  mov     qword ptr [rdi+0AE0h], 0
0x14000cf5e  mov     rcx, [rdi+0A18h]; Handle
0x14000cf65  test    rcx, rcx
0x14000cf68  jz      short loc_14000CFAF
0x14000cf6a  call    cs:__imp_PoUnregisterPowerSettingCallback
0x14000cf71  nop     dword ptr [rax+rax+00h]
0x14000cf76  test    eax, eax
0x14000cf78  jns     short loc_14000CFA4
0x14000cf7a  cmp     cs:WPP_RECORDER_INITIALIZED, rbx; __annotation("TMF:",
0x14000cf81  jz      short loc_14000CFA4
0x14000cf83  mov     rcx, [rdi+9E8h]
0x14000cf8a  mov     r9d, 37h ; '7'
0x14000cf90  mov     [rsp+38h+var_10], eax
0x14000cf94  mov     dl, 2
0x14000cf96  mov     [rsp+38h+var_18], r14
0x14000cf9b  lea     r8d, [r9-34h]
0x14000cf9f  call    WPP_RECORDER_SF_d
0x14000cfa4  mov     qword ptr [rdi+0A18h], 0
0x14000cfaf  mov     rcx, [rdi+0A10h]; Handle
0x14000cfb6  test    rcx, rcx
0x14000cfb9  jz      short loc_14000D000
0x14000cfbb  call    cs:__imp_PoUnregisterPowerSettingCallback
0x14000cfc2  nop     dword ptr [rax+rax+00h]
0x14000cfc7  test    eax, eax
0x14000cfc9  jns     short loc_14000CFF5
0x14000cfcb  cmp     cs:WPP_RECORDER_INITIALIZED, rbx; __annotation("TMF:",
0x14000cfd2  jz      short loc_14000CFF5
0x14000cfd4  mov     rcx, [rdi+9E8h]
0x14000cfdb  mov     r9d, 38h ; '8'
0x14000cfe1  mov     [rsp+38h+var_10], eax
0x14000cfe5  mov     dl, 2
0x14000cfe7  mov     [rsp+38h+var_18], r14
0x14000cfec  lea     r8d, [r9-35h]
0x14000cff0  call    WPP_RECORDER_SF_d
0x14000cff5  mov     qword ptr [rdi+0A10h], 0
0x14000d000  mov     eax, [rdi+28h]
0x14000d003  test    al, 20h
0x14000d005  jz      short loc_14000D05D
0x14000d007  lea     rbx, [rdi+490h]
0x14000d00e  mov     rcx, rbx; Event
0x14000d011  call    cs:__imp_KeResetEvent
0x14000d018  nop     dword ptr [rax+rax+00h]
0x14000d01d  lea     rcx, [rdi+500h]
0x14000d024  mov     edx, 7EBh
0x14000d029  call    HUBSM_AddEvent
0x14000d02e  mov     rax, cs:WdfFunctions_01015
0x14000d035  mov     rdx, rdi
0x14000d038  mov     rcx, cs:WdfDriverGlobals
0x14000d03f  mov     rax, [rax+660h]
0x14000d046  call    _guard_dispatch_icall
0x14000d04b  mov     r8, rax
0x14000d04e  lea     rdx, aHubFdoPnpcallb; "Hub FDO PnpCallback"
0x14000d055  mov     rcx, rbx; Object
0x14000d058  call    HUBMISC_WaitForSignal
0x14000d05d  mov     rcx, [rdi+8E0h]
0x14000d064  test    rcx, rcx
0x14000d067  jz      short loc_14000D093
0x14000d069  mov     rax, [rdi+210h]
0x14000d070  call    _guard_dispatch_icall
0x14000d075  mov     rax, [rdi+200h]
0x14000d07c  mov     rcx, [rdi+8E0h]
0x14000d083  call    _guard_dispatch_icall
0x14000d088  mov     qword ptr [rdi+8E0h], 0
0x14000d093  mov     rcx, [rdi+4F8h]; P
0x14000d09a  test    rcx, rcx
0x14000d09d  jz      short loc_14000D0B0
0x14000d09f  mov     edx, 68334855h; Tag
0x14000d0a4  call    cs:__imp_ExFreePoolWithTag
0x14000d0ab  nop     dword ptr [rax+rax+00h]
0x14000d0b0  mov     rdx, [rdi+9E8h]
0x14000d0b7  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d0be  call    cs:__imp_imp_WppRecorderLogDelete
0x14000d0c5  nop     dword ptr [rax+rax+00h]
0x14000d0ca  mov     ecx, [rdi+60h]
0x14000d0cd  test    ecx, ecx
0x14000d0cf  jz      short loc_14000D0E4
0x14000d0d1  call    cs:__imp_USBD_ReleaseHubNumber
0x14000d0d8  nop     dword ptr [rax+rax+00h]
0x14000d0dd  mov     dword ptr [rdi+60h], 0
0x14000d0e4  test    cs:Microsoft_Windows_USB_USBHUB3EnableBits, 2
0x14000d0eb  jz      short loc_14000D103
0x14000d0ed  mov     r9, [rdi+0F8h]
0x14000d0f4  lea     rdx, USBHUB3_ETW_EVENT_HUB_CLEANUP_COMPLETE
0x14000d0fb  xor     r8d, r8d
0x14000d0fe  call    McTemplateK0p_EtwWriteTransfer
0x14000d103  mov     rbx, [rsp+38h+arg_0]
0x14000d108  mov     rdi, [rsp+38h+arg_8]
0x14000d10d  add     rsp, 30h
0x14000d111  pop     r14
0x14000d113  retn
```
