# HUBFDO_EvtDeviceD0Entry

- ea: `0x14000d120`
- end: `0x14000d572`
- name: `HUBFDO_EvtDeviceD0Entry`
- size: `1106`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x1400024b8`
- `0x14000a53c`
- `0x14000d120`
- `0x14000f304`
- `0x14000f37c`
- `0x1400336a8`
- `0x14004223c`
- `0x140045570`

## import_xrefs

- `ntoskrnl!KeResetEvent` at `0x14000d4b7`
- `ntoskrnl!KeResetEvent` at `0x14000d4d4`
- `ntoskrnl!KeResetEvent` at `0x14000d4b7`
- `ntoskrnl!KeResetEvent` at `0x14000d4d4`
- `ntoskrnl!PoUnregisterPowerSettingCallback` at `0x14000d27d`
- `ntoskrnl!PoUnregisterPowerSettingCallback` at `0x14000d27d`
- `ntoskrnl!EtwActivityIdControl` at `0x14000d3c9`
- `ntoskrnl!EtwActivityIdControl` at `0x14000d3c9`
- `ntoskrnl!PoRegisterPowerSettingCallback` at `0x14000d1ed`
- `ntoskrnl!PoRegisterPowerSettingCallback` at `0x14000d2e5`
- `ntoskrnl!PoRegisterPowerSettingCallback` at `0x14000d36a`
- `ntoskrnl!PoRegisterPowerSettingCallback` at `0x14000d1ed`
- `ntoskrnl!PoRegisterPowerSettingCallback` at `0x14000d2e5`
- `ntoskrnl!PoRegisterPowerSettingCallback` at `0x14000d36a`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_ComponentActive` at `0x14000d40c`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_ComponentActive` at `0x14000d42c`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_ComponentActive` at `0x14000d40c`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_ComponentActive` at `0x14000d42c`

## pseudocode

```c
__int64 __fastcall HUBFDO_EvtDeviceD0Entry(__int64 a1)
{
  __int64 v2; // rax
  __int64 v3; // rdi
  PVOID *Handle; // rbx
  struct _DEVICE_OBJECT *v5; // rax
  NTSTATUS v6; // eax
  int v7; // edx
  int v8; // eax
  __int64 v9; // rcx
  struct _DEVICE_OBJECT *v10; // rax
  NTSTATUS v11; // eax
  int v12; // edx
  struct _DEVICE_OBJECT *v13; // rax
  NTSTATUS v14; // eax
  int v15; // edx
  char v16; // r14
  NTSTATUS v17; // esi
  int v18; // eax
  int v19; // ebp
  int v20; // ecx
  int v21; // ecx
  void *v22; // rbx
  __int64 v23; // rdx

  v2 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 1616))(
         WdfDriverGlobals,
         a1,
         off_14006B270);
  v3 = v2;
  *(_DWORD *)(v2 + 2616) = 1;
  _InterlockedOr((volatile signed __int32 *)(v2 + 40), 0x20000u);
  if ( (*(_DWORD *)(v2 + 44) & 0x10) != 0 && !*(_BYTE *)(v2 + 240) && (*(_DWORD *)(v2 + 40) & 0x4000000) != 0 )
  {
    Handle = (PVOID *)(v2 + 2656);
    if ( !*(_QWORD *)(v2 + 2656) )
    {
      v5 = (struct _DEVICE_OBJECT *)(*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 248))(
                                      WdfDriverGlobals,
                                      a1);
      v6 = PoRegisterPowerSettingCallback(
             v5,
             &GUID_PDC_IDLE_RESILIENCY_ENGAGED,
             HUBFDO_IdleResiliencyCallback,
             (PVOID)v3,
             Handle);
      if ( v6 >= 0 )
      {
        v8 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD, POWER_SETTING_CALLBACK *, int, const char *))(WdfFunctions_01015 + 3504))(
               WdfDriverGlobals,
               a1,
               0,
               HUBFDO_IdleResiliencyCallback,
               1881,
               "onecore\\drivers\\wdm\\usb\\usb3\\hub\\src\\hubfdo.c");
        if ( v8 < 0 )
        {
          MicrosoftTelemetryAssertTriggeredArgsMsgKM(v9, (unsigned int)v8, 0, "WdfDeviceStopIdle failed");
          PoUnregisterPowerSettingCallback(*Handle);
          *Handle = 0;
        }
      }
      else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v7) = 2;
        WPP_RECORDER_SF_d(
          *(_QWORD *)(v3 + 2536),
          v7,
          3,
          49,
          (__int64)WPP_2e0dbc61611a37aa5578b122392b1411_Traceguids,
          v6);
      }
    }
  }
  if ( (!*(_BYTE *)(v3 + 240) || (*(_DWORD *)(v3 + 44) & 0x100) != 0) && !*(_QWORD *)(v3 + 2784) )
  {
    v10 = (struct _DEVICE_OBJECT *)(*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 248))(
                                     WdfDriverGlobals,
                                     a1);
    v11 = PoRegisterPowerSettingCallback(
            v10,
            &GUID_LOW_POWER_EPOCH,
            HUBFDO_LowPowerEpochCallback,
            (PVOID)v3,
            (PVOID *)(v3 + 2784));
    if ( v11 < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v12) = 2;
      WPP_RECORDER_SF_d(
        *(_QWORD *)(v3 + 2536),
        v12,
        3,
        50,
        (__int64)WPP_2e0dbc61611a37aa5578b122392b1411_Traceguids,
        v11);
    }
  }
  if ( !*(_QWORD *)(v3 + 2576) && (*(_DWORD *)(v3 + 40) & 0x4000000) != 0 )
  {
    v13 = (struct _DEVICE_OBJECT *)(*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 248))(
                                     WdfDriverGlobals,
                                     a1);
    v14 = PoRegisterPowerSettingCallback(
            v13,
            &GUID_USB_SETTING_SELECTIVE_SUSPEND,
            (PPOWER_SETTING_CALLBACK)HUBFDO_PowerSettingCallback,
            (PVOID)v3,
            (PVOID *)(v3 + 2576));
    if ( v14 < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v15) = 2;
        WPP_RECORDER_SF_d(
          *(_QWORD *)(v3 + 2536),
          v15,
          3,
          51,
          (__int64)WPP_2e0dbc61611a37aa5578b122392b1411_Traceguids,
          v14);
      }
      *(_QWORD *)(v3 + 2576) = 0;
    }
  }
  v16 = 0;
  if ( (Microsoft_Windows_USB_USBHUB3EnableBits & 4) != 0 )
  {
    v17 = EtwActivityIdControl(3u, (LPGUID)(v3 + 2292));
    if ( v17 >= 0 )
    {
      if ( g_IoSetActivityIdIrp )
        g_IoSetActivityIdIrp(*(_QWORD *)(v3 + 832), v3 + 2292);
      v16 = 1;
    }
  }
  else
  {
    v17 = 0;
  }
  if ( (*(_DWORD *)(v3 + 40) & 0x80u) != 0 && *(_QWORD *)(v3 + 2632) )
    SleepstudyHelper_ComponentActive();
  if ( (*(_DWORD *)(v3 + 44) & 1) != 0 && *(_QWORD *)(v3 + 2640) )
    SleepstudyHelper_ComponentActive();
  v18 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 3104))(WdfDriverGlobals, a1);
  v19 = v18;
  if ( (Microsoft_Windows_USB_USBHUB3EnableBits & 4) != 0 )
  {
    v20 = *(_DWORD *)(v3 + 40) >> 10;
    LOWORD(v20) = (*(_DWORD *)(v3 + 40) & 0x400) != 0;
    McTemplateK0pqqh_EtwWriteTransfer(
      v20,
      (unsigned int)USBHUB3_ETW_EVENT_HUB_D0_ENTRY_START,
      v3 + 2292,
      *(_QWORD *)(v3 + 248),
      1,
      v18,
      (*(_DWORD *)(v3 + 40) & 0x400) != 0);
  }
  if ( !v19 )
  {
    v22 = (void *)(v3 + 1168);
    KeResetEvent((PRKEVENT)(v3 + 1168));
    v23 = 2007;
    goto LABEL_43;
  }
  if ( v19 == 2 || v19 == 3 || v19 == 4 || (v21 = v19 - 5, (unsigned int)(v19 - 5) <= 1) )
  {
    v22 = (void *)(v3 + 1168);
    KeResetEvent((PRKEVENT)(v3 + 1168));
    v23 = 2011;
LABEL_43:
    HUBSM_AddEvent(v3 + 1280, v23);
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 1632))(WdfDriverGlobals, v3);
    HUBMISC_WaitForSignal(v22);
    v17 = *(_DWORD *)(v3 + 1192);
  }
  if ( (Microsoft_Windows_USB_USBHUB3EnableBits & 4) != 0 )
    McTemplateK0pqq_EtwWriteTransfer(
      v21,
      (unsigned int)USBHUB3_ETW_EVENT_HUB_D0_ENTRY_COMPLETE,
      v3 + 2292,
      *(_QWORD *)(v3 + 248),
      v17,
      v19);
  if ( v16 == 1 )
    *(_OWORD *)(v3 + 2292) = 0;
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x14000d120  push    rbx
0x14000d122  push    rbp
0x14000d123  push    rsi
0x14000d124  push    rdi
0x14000d125  push    r12
0x14000d127  push    r13
0x14000d129  push    r14
0x14000d12b  sub     rsp, 40h
0x14000d12f  mov     rax, cs:WdfFunctions_01015
0x14000d136  mov     rbp, rcx
0x14000d139  mov     r8, cs:off_14006B270
0x14000d140  mov     rdx, rcx
0x14000d143  mov     rcx, cs:WdfDriverGlobals
0x14000d14a  mov     rax, [rax+650h]
0x14000d151  call    _guard_dispatch_icall
0x14000d156  mov     r13d, 1
0x14000d15c  mov     rdi, rax
0x14000d15f  mov     [rax+0A38h], r13d
0x14000d166  lock or dword ptr [rax+28h], 20000h
0x14000d16e  mov     ecx, [rax+2Ch]
0x14000d171  lea     r14, WPP_RECORDER_INITIALIZED
0x14000d178  lea     r12, WPP_2e0dbc61611a37aa5578b122392b1411_Traceguids
0x14000d17f  lea     esi, [r13+2]
0x14000d183  test    cl, 10h
0x14000d186  jz      loc_14000D290
0x14000d18c  cmp     byte ptr [rax+0F0h], 0
0x14000d193  jnz     loc_14000D290
0x14000d199  test    dword ptr [rax+28h], 4000000h
0x14000d1a0  jz      loc_14000D290
0x14000d1a6  lea     rbx, [rax+0A60h]
0x14000d1ad  cmp     qword ptr [rbx], 0
0x14000d1b1  jnz     loc_14000D290
0x14000d1b7  mov     rax, cs:WdfFunctions_01015
0x14000d1be  mov     rdx, rbp
0x14000d1c1  mov     rcx, cs:WdfDriverGlobals
0x14000d1c8  mov     rax, [rax+0F8h]
0x14000d1cf  call    _guard_dispatch_icall
0x14000d1d4  mov     r9, rdi; Context
0x14000d1d7  mov     [rsp+78h+Handle], rbx; Handle
0x14000d1dc  lea     r8, HUBFDO_IdleResiliencyCallback; Callback
0x14000d1e3  mov     rcx, rax; DeviceObject
0x14000d1e6  lea     rdx, GUID_PDC_IDLE_RESILIENCY_ENGAGED; SettingGuid
0x14000d1ed  call    cs:__imp_PoRegisterPowerSettingCallback
0x14000d1f4  nop     dword ptr [rax+rax+00h]
0x14000d1f9  test    eax, eax
0x14000d1fb  jns     short loc_14000D22A
0x14000d1fd  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x14000d204  jz      loc_14000D290
0x14000d20a  mov     rcx, [rdi+9E8h]
0x14000d211  lea     r9d, [r13+30h]
0x14000d215  mov     dword ptr [rsp+78h+var_50], eax
0x14000d219  mov     r8d, esi
0x14000d21c  mov     dl, 2
0x14000d21e  mov     [rsp+78h+Handle], r12
0x14000d223  call    WPP_RECORDER_SF_d
0x14000d228  jmp     short loc_14000D290
0x14000d22a  mov     rax, cs:WdfFunctions_01015
0x14000d231  lea     rcx, aOnecoreDrivers; "onecore\\drivers\\wdm\\usb\\usb3\\hub\\"...
0x14000d238  mov     [rsp+78h+var_50], rcx
0x14000d23d  lea     r9, HUBFDO_IdleResiliencyCallback
0x14000d244  mov     rcx, cs:WdfDriverGlobals
0x14000d24b  xor     r8d, r8d
0x14000d24e  mov     rdx, rbp
0x14000d251  mov     dword ptr [rsp+78h+Handle], 759h
0x14000d259  mov     rax, [rax+0DB0h]
0x14000d260  call    _guard_dispatch_icall
0x14000d265  test    eax, eax
0x14000d267  jns     short loc_14000D290
0x14000d269  lea     r9, aWdfdevicestopi; __annotation("Debug", "TelemetryAssert", "FALSE", "WdfDeviceStopIdle failed")
0x14000d270  xor     r8d, r8d
0x14000d273  mov     edx, eax
0x14000d275  call    MicrosoftTelemetryAssertTriggeredArgsMsgKM
0x14000d27a  mov     rcx, [rbx]; Handle
0x14000d27d  call    cs:__imp_PoUnregisterPowerSettingCallback
0x14000d284  nop     dword ptr [rax+rax+00h]
0x14000d289  mov     qword ptr [rbx], 0
0x14000d290  cmp     byte ptr [rdi+0F0h], 0
0x14000d297  jz      short loc_14000D2A2
0x14000d299  test    dword ptr [rdi+2Ch], 100h
0x14000d2a0  jz      short loc_14000D31E
0x14000d2a2  lea     rbx, [rdi+0AE0h]
0x14000d2a9  cmp     qword ptr [rbx], 0
0x14000d2ad  jnz     short loc_14000D31E
0x14000d2af  mov     rax, cs:WdfFunctions_01015
0x14000d2b6  mov     rdx, rbp
0x14000d2b9  mov     rcx, cs:WdfDriverGlobals
0x14000d2c0  mov     rax, [rax+0F8h]
0x14000d2c7  call    _guard_dispatch_icall
0x14000d2cc  mov     r9, rdi; Context
0x14000d2cf  mov     [rsp+78h+Handle], rbx; Handle
0x14000d2d4  lea     r8, HUBFDO_LowPowerEpochCallback; Callback
0x14000d2db  mov     rcx, rax; DeviceObject
0x14000d2de  lea     rdx, GUID_LOW_POWER_EPOCH; SettingGuid
0x14000d2e5  call    cs:__imp_PoRegisterPowerSettingCallback
0x14000d2ec  nop     dword ptr [rax+rax+00h]
0x14000d2f1  test    eax, eax
0x14000d2f3  jns     short loc_14000D31E
0x14000d2f5  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x14000d2fc  jz      short loc_14000D31E
0x14000d2fe  mov     rcx, [rdi+9E8h]
0x14000d305  mov     r9d, 32h ; '2'
0x14000d30b  mov     dword ptr [rsp+78h+var_50], eax
0x14000d30f  mov     r8d, esi
0x14000d312  mov     dl, 2
0x14000d314  mov     [rsp+78h+Handle], r12
0x14000d319  call    WPP_RECORDER_SF_d
0x14000d31e  lea     rbx, [rdi+0A10h]
0x14000d325  cmp     qword ptr [rbx], 0
0x14000d329  jnz     short loc_14000D3AA
0x14000d32b  test    dword ptr [rdi+28h], 4000000h
0x14000d332  jz      short loc_14000D3AA
0x14000d334  mov     rax, cs:WdfFunctions_01015
0x14000d33b  mov     rdx, rbp
0x14000d33e  mov     rcx, cs:WdfDriverGlobals
0x14000d345  mov     rax, [rax+0F8h]
0x14000d34c  call    _guard_dispatch_icall
0x14000d351  mov     r9, rdi; Context
0x14000d354  mov     [rsp+78h+Handle], rbx; Handle
0x14000d359  lea     r8, HUBFDO_PowerSettingCallback; Callback
0x14000d360  mov     rcx, rax; DeviceObject
0x14000d363  lea     rdx, GUID_USB_SETTING_SELECTIVE_SUSPEND; SettingGuid
0x14000d36a  call    cs:__imp_PoRegisterPowerSettingCallback
0x14000d371  nop     dword ptr [rax+rax+00h]
0x14000d376  test    eax, eax
0x14000d378  jns     short loc_14000D3AA
0x14000d37a  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x14000d381  jz      short loc_14000D3A3
0x14000d383  mov     rcx, [rdi+9E8h]
0x14000d38a  mov     r9d, 33h ; '3'
0x14000d390  mov     dword ptr [rsp+78h+var_50], eax
0x14000d394  mov     r8d, esi
0x14000d397  mov     dl, 2
0x14000d399  mov     [rsp+78h+Handle], r12
0x14000d39e  call    WPP_RECORDER_SF_d
0x14000d3a3  mov     qword ptr [rbx], 0
0x14000d3aa  xor     r14b, r14b
0x14000d3ad  lea     rbx, [rdi+8F4h]
0x14000d3b4  mov     r12b, 4
0x14000d3b7  test    cs:Microsoft_Windows_USB_USBHUB3EnableBits, r12b
0x14000d3be  jnz     short loc_14000D3C4
0x14000d3c0  xor     esi, esi
0x14000d3c2  jmp     short loc_14000D3F9
0x14000d3c4  mov     rdx, rbx; ActivityId
0x14000d3c7  mov     ecx, esi; ControlCode
0x14000d3c9  call    cs:__imp_EtwActivityIdControl
0x14000d3d0  nop     dword ptr [rax+rax+00h]
0x14000d3d5  mov     esi, eax
0x14000d3d7  test    eax, eax
0x14000d3d9  js      short loc_14000D3F9
0x14000d3db  mov     rax, cs:g_IoSetActivityIdIrp
0x14000d3e2  test    rax, rax
0x14000d3e5  jz      short loc_14000D3F6
0x14000d3e7  mov     rcx, [rdi+340h]
0x14000d3ee  mov     rdx, rbx
0x14000d3f1  call    _guard_dispatch_icall
0x14000d3f6  mov     r14b, r13b
0x14000d3f9  mov     eax, [rdi+28h]
0x14000d3fc  test    al, al
0x14000d3fe  jns     short loc_14000D418
0x14000d400  mov     rcx, [rdi+0A48h]
0x14000d407  test    rcx, rcx
0x14000d40a  jz      short loc_14000D418
0x14000d40c  call    cs:__imp_SleepstudyHelper_ComponentActive
0x14000d413  nop     dword ptr [rax+rax+00h]
0x14000d418  mov     eax, [rdi+2Ch]
0x14000d41b  test    r13b, al
0x14000d41e  jz      short loc_14000D438
0x14000d420  mov     rcx, [rdi+0A50h]
0x14000d427  test    rcx, rcx
0x14000d42a  jz      short loc_14000D438
0x14000d42c  call    cs:__imp_SleepstudyHelper_ComponentActive
0x14000d433  nop     dword ptr [rax+rax+00h]
0x14000d438  mov     rax, cs:WdfFunctions_01015
0x14000d43f  mov     rdx, rbp
0x14000d442  mov     rcx, cs:WdfDriverGlobals
0x14000d449  mov     rax, [rax+0C20h]
0x14000d450  call    _guard_dispatch_icall
0x14000d455  test    cs:Microsoft_Windows_USB_USBHUB3EnableBits, r12b
0x14000d45c  mov     ebp, eax
0x14000d45e  jz      short loc_14000D48E
0x14000d460  mov     ecx, [rdi+28h]
0x14000d463  lea     rdx, USBHUB3_ETW_EVENT_HUB_D0_ENTRY_START
0x14000d46a  mov     r9, [rdi+0F8h]
0x14000d471  mov     r8, rbx
0x14000d474  shr     ecx, 0Ah
0x14000d477  and     cx, r13w
0x14000d47b  mov     [rsp+78h+var_48], cx
0x14000d480  mov     dword ptr [rsp+78h+var_50], eax
0x14000d484  mov     dword ptr [rsp+78h+Handle], r13d
0x14000d489  call    McTemplateK0pqqh_EtwWriteTransfer
0x14000d48e  mov     ecx, ebp
0x14000d490  test    ebp, ebp
0x14000d492  jz      short loc_14000D4CA
0x14000d494  sub     ecx, 2
0x14000d497  jz      short loc_14000D4AD
0x14000d499  sub     ecx, r13d
0x14000d49c  jz      short loc_14000D4AD
0x14000d49e  sub     ecx, r13d
0x14000d4a1  jz      short loc_14000D4AD
0x14000d4a3  sub     ecx, r13d
0x14000d4a6  jz      short loc_14000D4AD
0x14000d4a8  cmp     ecx, r13d
0x14000d4ab  jnz     short loc_14000D526
0x14000d4ad  lea     rbx, [rdi+490h]
0x14000d4b4  mov     rcx, rbx; Event
0x14000d4b7  call    cs:__imp_KeResetEvent
0x14000d4be  nop     dword ptr [rax+rax+00h]
0x14000d4c3  mov     edx, 7DBh
0x14000d4c8  jmp     short loc_14000D4E5
0x14000d4ca  lea     rbx, [rdi+490h]
0x14000d4d1  mov     rcx, rbx; Event
0x14000d4d4  call    cs:__imp_KeResetEvent
0x14000d4db  nop     dword ptr [rax+rax+00h]
0x14000d4e0  mov     edx, 7D7h
0x14000d4e5  lea     rcx, [rdi+500h]
0x14000d4ec  call    HUBSM_AddEvent
0x14000d4f1  mov     rax, cs:WdfFunctions_01015
0x14000d4f8  mov     rdx, rdi
0x14000d4fb  mov     rcx, cs:WdfDriverGlobals
0x14000d502  mov     rax, [rax+660h]
0x14000d509  call    _guard_dispatch_icall
0x14000d50e  mov     r8, rax
0x14000d511  lea     rdx, aHubFdoPnpcallb; "Hub FDO PnpCallback"
0x14000d518  mov     rcx, rbx; Object
0x14000d51b  call    HUBMISC_WaitForSignal
0x14000d520  mov     esi, [rdi+4A8h]
0x14000d526  test    cs:Microsoft_Windows_USB_USBHUB3EnableBits, r12b
0x14000d52d  jz      short loc_14000D551
0x14000d52f  mov     r9, [rdi+0F8h]
0x14000d536  lea     r8, [rdi+8F4h]
0x14000d53d  mov     dword ptr [rsp+78h+var_50], ebp
0x14000d541  lea     rdx, USBHUB3_ETW_EVENT_HUB_D0_ENTRY_COMPLETE
0x14000d548  mov     dword ptr [rsp+78h+Handle], esi
0x14000d54c  call    McTemplateK0pqq_EtwWriteTransfer
0x14000d551  cmp     r14b, r13b
0x14000d554  jnz     short loc_14000D560
0x14000d556  xorps   xmm0, xmm0
0x14000d559  movups  xmmword ptr [rdi+8F4h], xmm0
0x14000d560  mov     eax, esi
0x14000d562  add     rsp, 40h
0x14000d566  pop     r14
0x14000d568  pop     r13
0x14000d56a  pop     r12
0x14000d56c  pop     rdi
0x14000d56d  pop     rsi
0x14000d56e  pop     rbp
0x14000d56f  pop     rbx
0x14000d570  retn
```
