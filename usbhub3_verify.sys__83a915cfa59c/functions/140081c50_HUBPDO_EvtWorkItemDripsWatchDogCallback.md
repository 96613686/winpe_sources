# HUBPDO_EvtWorkItemDripsWatchDogCallback

- ea: `0x140081c50`
- end: `0x1400822c9`
- name: `HUBPDO_EvtWorkItemDripsWatchDogCallback`
- size: `1657`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x1400024b8`
- `0x1400067ac`
- `0x14001c704`
- `0x14001cff0`
- `0x14001d21c`
- `0x140045570`
- `0x140081c50`
- `0x140086ad4`

## import_xrefs

- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1400822a3`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1400822a3`
- `ntoskrnl!DbgkWerCaptureLiveKernelDump` at `0x140081f84`
- `ntoskrnl!DbgkWerCaptureLiveKernelDump` at `0x140081f84`
- `ntoskrnl!IoRequestDeviceRemovalForReset` at `0x140082071`
- `ntoskrnl!IoRequestDeviceRemovalForReset` at `0x140082071`
- `ntoskrnl!PoUnregisterPowerSettingCallback` at `0x14008208a`
- `ntoskrnl!PoUnregisterPowerSettingCallback` at `0x14008208a`
- `ntoskrnl!PoRegisterPowerSettingCallback` at `0x140081e61`
- `ntoskrnl!PoRegisterPowerSettingCallback` at `0x140081ffb`
- `ntoskrnl!PoRegisterPowerSettingCallback` at `0x140081e61`
- `ntoskrnl!PoRegisterPowerSettingCallback` at `0x140081ffb`

## pseudocode

```c
void __fastcall HUBPDO_EvtWorkItemDripsWatchDogCallback(__int64 a1)
{
  unsigned __int8 v1; // bp
  _QWORD *v2; // rsi
  __int64 v3; // r8
  __int64 v4; // rdi
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // rcx
  int v8; // ebx
  int v9; // eax
  int v10; // edx
  int v11; // edx
  __int64 v12; // rbx
  int v13; // r8d
  int v14; // r9d
  char v15; // si
  NTSTATUS v16; // edx
  __int64 v17; // rax
  __int64 v18; // rax
  NTSTATUS v19; // edx
  int v20; // eax
  char v21; // bl
  int v22; // edx
  __int64 v23; // rax
  __int64 v24; // r9
  __int64 v25; // r9
  __int64 v26; // r9
  __int64 v27; // rax
  PVOID *Handle; // [rsp+20h] [rbp-58h]
  char v29; // [rsp+28h] [rbp-50h]
  char v30; // [rsp+28h] [rbp-50h]
  int v31; // [rsp+88h] [rbp+10h] BYREF
  PVOID v32; // [rsp+90h] [rbp+18h] BYREF

  v32 = 0;
  v1 = 1;
  v31 = 0;
  v2 = (_QWORD *)(*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 1616))(
                   WdfDriverGlobals,
                   a1,
                   off_14006B298);
  v4 = *(_QWORD *)(*v2 + 64LL);
  v5 = *(_QWORD *)(v4 + 24);
  LODWORD(v6) = *(_DWORD *)(v5 + 1640);
  if ( (v6 & 2) != 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v7 = *(_QWORD *)(v5 + 8);
      LOBYTE(v5) = 4;
      WPP_RECORDER_SF_(*(_QWORD *)(v7 + 1432), v5, 2, 173, (__int64)WPP_8beb7df92ba934db5f6899fb45b5938a_Traceguids);
    }
    v8 = 1;
    goto LABEL_37;
  }
  v9 = HUBREG_OpenQueryAttemptRecoveryFromUsbPowerDrainValue(&v31, v5, v3);
  if ( v9 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_d(
        *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v4 + 24) + 8LL) + 1432LL),
        3,
        2,
        174,
        (__int64)WPP_8beb7df92ba934db5f6899fb45b5938a_Traceguids,
        v9);
    v8 = 2;
    goto LABEL_37;
  }
  if ( v31 )
  {
    v6 = *(_QWORD *)(v4 + 24);
    if ( (*(_DWORD *)(v6 + 1652) & 0x800000) != 0 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_(
          *(_QWORD *)(*(_QWORD *)(v6 + 8) + 1432LL),
          3,
          2,
          176,
          (__int64)WPP_8beb7df92ba934db5f6899fb45b5938a_Traceguids);
      v8 = 4;
      goto LABEL_37;
    }
    if ( !*(_QWORD *)(v6 + 24)
      || (v12 = MEMORY[0xFFFFF78000000014]
              - (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v6 + 592LL))(*(_QWORD *)(*(_QWORD *)v6 + 248LL)),
          v12 >= 300000000) )
    {
      if ( _InterlockedCompareExchange((volatile signed __int32 *)(v4 + 400), 1, 0) )
      {
        LODWORD(Handle) = 0;
        DbgkWerCaptureLiveKernelDump(L"UsbDripsBlockerSurpriseRemoval", 421, *v2, 0);
        v18 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 1632))(
                WdfDriverGlobals,
                v4);
        (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64))(WdfFunctions_01015 + 696))(
          WdfDriverGlobals,
          v18,
          2);
        v8 = 12;
      }
      else
      {
        v19 = PoRegisterPowerSettingCallback(
                0,
                &GUID_LOW_POWER_EPOCH,
                HUBPDO_ReEnumerationCallback,
                *(PVOID *)(v4 + 24),
                &v32);
        if ( v19 >= 0 )
        {
          *(_QWORD *)(v4 + 408) = v32;
          v20 = IoRequestDeviceRemovalForReset(*v2, 0);
          v21 = v20;
          if ( v20 >= 0 )
          {
            v1 = 0;
            v8 = 0;
          }
          else
          {
            PoUnregisterPowerSettingCallback(*(PVOID *)(v4 + 408));
            LODWORD(v6) = 0;
            *(_QWORD *)(v4 + 408) = 0;
            _InterlockedCompareExchange((volatile signed __int32 *)(v4 + 400), 0, 1);
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              LOBYTE(v22) = 2;
              WPP_RECORDER_SF_d(
                *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v4 + 24) + 8LL) + 1432LL),
                v22,
                2,
                180,
                (__int64)WPP_8beb7df92ba934db5f6899fb45b5938a_Traceguids,
                v21);
            }
            v8 = 8;
          }
        }
        else
        {
          LODWORD(v6) = 0;
          _InterlockedCompareExchange((volatile signed __int32 *)(v4 + 400), 0, 1);
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            v30 = v19;
            LOBYTE(v19) = 2;
            WPP_RECORDER_SF_d(
              *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v4 + 24) + 8LL) + 1432LL),
              v19,
              2,
              179,
              (__int64)WPP_8beb7df92ba934db5f6899fb45b5938a_Traceguids,
              v30);
          }
          v8 = 7;
        }
      }
      goto LABEL_37;
    }
    v15 = _InterlockedCompareExchange((volatile signed __int32 *)(v4 + 404), 1, 0);
    if ( !v15 )
    {
      v16 = PoRegisterPowerSettingCallback(
              0,
              &GUID_PDC_IDLE_RESILIENCY_ENGAGED,
              HUBPDO_IdleResiliencyCallback,
              *(PVOID *)(v4 + 24),
              (PVOID *)(v4 + 416));
      if ( v16 >= 0 )
      {
        v17 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 1632))(
                WdfDriverGlobals,
                v4);
        Handle = (PVOID *)"onecore\\drivers\\wdm\\usb\\usb3\\hub\\src\\hubpdo.c";
        (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, const char *, __int64))(WdfFunctions_01015 + 1640))(
          WdfDriverGlobals,
          v17,
          "DRIPS IO Tag",
          11963);
      }
      else
      {
        LODWORD(v6) = 0;
        _InterlockedCompareExchange((volatile signed __int32 *)(v4 + 404), 0, 1);
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
LABEL_25:
          v8 = v15 != 0 ? 11 : 5;
          goto LABEL_37;
        }
        v29 = v16;
        LOBYTE(v16) = 2;
        WPP_RECORDER_SF_d(
          *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v4 + 24) + 8LL) + 1432LL),
          v16,
          2,
          177,
          (__int64)WPP_8beb7df92ba934db5f6899fb45b5938a_Traceguids,
          v29);
      }
    }
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_II(
        *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v4 + 24) + 8LL) + 1432LL),
        v11,
        v13,
        v14,
        (_DWORD)Handle,
        v12);
    goto LABEL_25;
  }
  v8 = 3;
  if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    goto LABEL_39;
  LOBYTE(v10) = 3;
  WPP_RECORDER_SF_(
    *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v4 + 24) + 8LL) + 1432LL),
    v10,
    2,
    175,
    (__int64)WPP_8beb7df92ba934db5f6899fb45b5938a_Traceguids);
LABEL_37:
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v23 = *(_QWORD *)(v4 + 24);
    WPP_RECORDER_SF_DDDLd(
      *(_QWORD *)(*(_QWORD *)(v23 + 8) + 1432LL),
      v1,
      *(unsigned __int16 *)(v23 + 2008),
      *(unsigned __int16 *)(v23 + 2006),
      (_DWORD)Handle,
      *(_WORD *)(v23 + 2004),
      *(_WORD *)(v23 + 2006),
      *(_WORD *)(v23 + 2008),
      v8,
      v1);
  }
LABEL_39:
  if ( (byte_14006ED43 & 2) != 0 )
  {
    v24 = *(_QWORD *)(v4 + 24);
    McTemplateK0pqhhh_EtwWriteTransfer(
      v6,
      (unsigned int)USBHUB3_ETW_EVENT_DEVICE_DRIPS_WATCHDOG_COMPLETE,
      v24 + 1524,
      *(_QWORD *)(v24 + 24),
      v8,
      *(_WORD *)(v24 + 2004),
      *(_WORD *)(v24 + 2006),
      *(_WORD *)(v24 + 2008));
  }
  if ( v8 != 1 )
  {
    if ( v8 == 12 )
    {
      if ( (byte_14006ED43 & 4) != 0 )
      {
        v25 = *(_QWORD *)(v4 + 24);
        McTemplateK0pqhhh_EtwWriteTransfer(
          v6,
          (unsigned int)USBHUB3_ETW_EVENT_DEVICE_DRIPS_WATCHDOG_COMPLETE_PUBLISH_INFO,
          v25 + 1524,
          *(_QWORD *)(v25 + 24),
          12,
          *(_WORD *)(v25 + 2004),
          *(_WORD *)(v25 + 2006),
          *(_WORD *)(v25 + 2008));
      }
    }
    else if ( (byte_14006ED43 & 8) != 0 )
    {
      v26 = *(_QWORD *)(v4 + 24);
      McTemplateK0pqhhh_EtwWriteTransfer(
        v6,
        (unsigned int)USBHUB3_ETW_EVENT_DEVICE_DRIPS_WATCHDOG_COMPLETE_PUBLISH_WARNING,
        v26 + 1524,
        *(_QWORD *)(v26 + 24),
        v8,
        *(_WORD *)(v26 + 2004),
        *(_WORD *)(v26 + 2006),
        *(_WORD *)(v26 + 2008));
    }
  }
  if ( v1 )
  {
    v27 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 1632))(WdfDriverGlobals, v4);
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, const char *, __int64, const char *))(WdfFunctions_01015 + 1648))(
      WdfDriverGlobals,
      v27,
      "DRIPS SR Tag",
      12101,
      "onecore\\drivers\\wdm\\usb\\usb3\\hub\\src\\hubpdo.c");
  }
  IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(v4 + 424), "DRIPS SR Tag", 0x20u);
}

```

## disassembly

```asm
0x140081c50  mov     rax, rsp
0x140081c53  mov     [rax+8], rbx
0x140081c57  mov     [rax+20h], rbp
0x140081c5b  push    rsi
0x140081c5c  push    rdi
0x140081c5d  push    r12
0x140081c5f  push    r13
0x140081c61  push    r15
0x140081c63  sub     rsp, 50h
0x140081c67  mov     r8, cs:off_14006B298
0x140081c6e  mov     rdx, rcx
0x140081c71  mov     rcx, cs:WdfDriverGlobals
0x140081c78  mov     r13d, 1
0x140081c7e  mov     qword ptr [rax+18h], 0
0x140081c86  mov     bpl, r13b
0x140081c89  mov     dword ptr [rax+10h], 0
0x140081c90  mov     rax, cs:WdfFunctions_01015
0x140081c97  mov     rax, [rax+650h]
0x140081c9e  call    _guard_dispatch_icall
0x140081ca3  lea     r15d, [r13+1]
0x140081ca7  mov     rsi, rax
0x140081caa  lea     r12, WPP_RECORDER_INITIALIZED
0x140081cb1  mov     rcx, [rax]
0x140081cb4  mov     rdi, [rcx+40h]
0x140081cb8  mov     rdx, [rdi+18h]
0x140081cbc  mov     ecx, [rdx+668h]
0x140081cc2  test    r15b, cl
0x140081cc5  jz      short loc_140081CFF
0x140081cc7  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x140081cce  jz      short loc_140081CF7
0x140081cd0  mov     rcx, [rdx+8]
0x140081cd4  lea     rax, WPP_8beb7df92ba934db5f6899fb45b5938a_Traceguids
0x140081cdb  mov     r9d, 0ADh
0x140081ce1  mov     [rsp+78h+Handle], rax
0x140081ce6  mov     r8d, r15d
0x140081ce9  mov     dl, 4
0x140081ceb  mov     rcx, [rcx+598h]
0x140081cf2  call    WPP_RECORDER_SF_
0x140081cf7  mov     ebx, r13d
0x140081cfa  jmp     loc_1400820F3
0x140081cff  lea     rcx, [rsp+78h+arg_8]
0x140081d07  call    HUBREG_OpenQueryAttemptRecoveryFromUsbPowerDrainValue
0x140081d0c  test    eax, eax
0x140081d0e  jns     short loc_140081D53
0x140081d10  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x140081d17  jz      short loc_140081D4B
0x140081d19  mov     rcx, [rdi+18h]
0x140081d1d  mov     r9d, 0AEh
0x140081d23  mov     dword ptr [rsp+78h+var_50], eax
0x140081d27  mov     r8d, r15d
0x140081d2a  lea     rax, WPP_8beb7df92ba934db5f6899fb45b5938a_Traceguids
0x140081d31  mov     edx, 3
0x140081d36  mov     [rsp+78h+Handle], rax
0x140081d3b  mov     rcx, [rcx+8]
0x140081d3f  mov     rcx, [rcx+598h]
0x140081d46  call    WPP_RECORDER_SF_d
0x140081d4b  mov     ebx, r15d
0x140081d4e  jmp     loc_1400820F3
0x140081d53  cmp     [rsp+78h+arg_8], 0
0x140081d5b  jnz     short loc_140081D9F
0x140081d5d  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x140081d64  mov     ebx, 3
0x140081d69  jz      loc_140082143
0x140081d6f  mov     rax, [rdi+18h]
0x140081d73  mov     r9d, 0AFh
0x140081d79  mov     r8d, r15d
0x140081d7c  mov     dl, bl
0x140081d7e  mov     rcx, [rax+8]
0x140081d82  lea     rax, WPP_8beb7df92ba934db5f6899fb45b5938a_Traceguids
0x140081d89  mov     [rsp+78h+Handle], rax
0x140081d8e  mov     rcx, [rcx+598h]
0x140081d95  call    WPP_RECORDER_SF_
0x140081d9a  jmp     loc_1400820F3
0x140081d9f  mov     rcx, [rdi+18h]
0x140081da3  test    dword ptr [rcx+674h], 800000h
0x140081dad  jz      short loc_140081DEC
0x140081daf  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x140081db6  jz      short loc_140081DE2
0x140081db8  mov     rcx, [rcx+8]
0x140081dbc  lea     rax, WPP_8beb7df92ba934db5f6899fb45b5938a_Traceguids
0x140081dc3  mov     r9d, 0B0h
0x140081dc9  mov     [rsp+78h+Handle], rax
0x140081dce  mov     r8d, r15d
0x140081dd1  mov     edx, 3
0x140081dd6  mov     rcx, [rcx+598h]
0x140081ddd  call    WPP_RECORDER_SF_
0x140081de2  mov     ebx, 4
0x140081de7  jmp     loc_1400820F3
0x140081dec  mov     rdx, [rcx+18h]
0x140081df0  test    rdx, rdx
0x140081df3  jz      loc_140081F47
0x140081df9  mov     rcx, [rcx]
0x140081dfc  mov     rax, [rcx+250h]
0x140081e03  mov     rcx, [rcx+0F8h]
0x140081e0a  call    _guard_dispatch_icall
0x140081e0f  mov     rbx, 0FFFFF78000000014h
0x140081e19  mov     rbx, [rbx]
0x140081e1c  sub     rbx, rax
0x140081e1f  cmp     rbx, 11E1A300h
0x140081e26  jge     loc_140081F47
0x140081e2c  xor     eax, eax
0x140081e2e  lock cmpxchg [rdi+194h], r13d
0x140081e37  mov     esi, eax
0x140081e39  test    al, al
0x140081e3b  jnz     loc_140081F15
0x140081e41  mov     r9, [rdi+18h]; Context
0x140081e45  lea     rcx, [rdi+1A0h]
0x140081e4c  mov     [rsp+78h+Handle], rcx; Handle
0x140081e51  lea     r8, HUBPDO_IdleResiliencyCallback; Callback
0x140081e58  xor     ecx, ecx; DeviceObject
0x140081e5a  lea     rdx, GUID_PDC_IDLE_RESILIENCY_ENGAGED; SettingGuid
0x140081e61  call    cs:__imp_PoRegisterPowerSettingCallback
0x140081e68  nop     dword ptr [rax+rax+00h]
0x140081e6d  mov     edx, eax
0x140081e6f  test    eax, eax
0x140081e71  jns     short loc_140081EBF
0x140081e73  xor     ecx, ecx
0x140081e75  mov     eax, r13d
0x140081e78  lock cmpxchg [rdi+194h], ecx
0x140081e80  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x140081e87  jz      loc_140081F37
0x140081e8d  mov     rcx, [rdi+18h]
0x140081e91  lea     rax, WPP_8beb7df92ba934db5f6899fb45b5938a_Traceguids
0x140081e98  mov     dword ptr [rsp+78h+var_50], edx
0x140081e9c  mov     r9d, 0B1h
0x140081ea2  mov     r8d, r15d
0x140081ea5  mov     [rsp+78h+Handle], rax
0x140081eaa  mov     dl, r15b
0x140081ead  mov     rcx, [rcx+8]
0x140081eb1  mov     rcx, [rcx+598h]
0x140081eb8  call    WPP_RECORDER_SF_d
0x140081ebd  jmp     short loc_140081F15
0x140081ebf  mov     rax, cs:WdfFunctions_01015
0x140081ec6  mov     rdx, rdi
0x140081ec9  mov     rcx, cs:WdfDriverGlobals
0x140081ed0  mov     rax, [rax+660h]
0x140081ed7  call    _guard_dispatch_icall
0x140081edc  mov     rcx, cs:WdfFunctions_01015
0x140081ee3  lea     r8, DripsWatchdogIoTag; "DRIPS IO Tag"
0x140081eea  mov     rdx, rax
0x140081eed  mov     r9d, 2EBBh
0x140081ef3  mov     r10, [rcx+668h]
0x140081efa  lea     rcx, aOnecoreDrivers_1; "onecore\\drivers\\wdm\\usb\\usb3\\hub\\"...
0x140081f01  mov     [rsp+78h+Handle], rcx
0x140081f06  mov     rax, r10
0x140081f09  mov     rcx, cs:WdfDriverGlobals
0x140081f10  call    _guard_dispatch_icall
0x140081f15  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x140081f1c  jz      short loc_140081F37
0x140081f1e  mov     rax, [rdi+18h]
0x140081f22  mov     [rsp+78h+var_50], rbx
0x140081f27  mov     rcx, [rax+8]
0x140081f2b  mov     rcx, [rcx+598h]
0x140081f32  call    WPP_RECORDER_SF_II
0x140081f37  neg     sil
0x140081f3a  sbb     ebx, ebx
0x140081f3c  and     ebx, 6
0x140081f3f  add     ebx, 5
0x140081f42  jmp     loc_1400820F3
0x140081f47  xor     eax, eax
0x140081f49  lock cmpxchg [rdi+190h], r13d
0x140081f52  jz      loc_140081FDA
0x140081f58  mov     r8, [rsi]
0x140081f5b  lea     rcx, aUsbdripsblocke; "UsbDripsBlockerSurpriseRemoval"
0x140081f62  xor     eax, eax
0x140081f64  xor     r9d, r9d
0x140081f67  mov     [rsp+78h+var_38], eax
0x140081f6b  mov     edx, 1A5h
0x140081f70  mov     [rsp+78h+var_40], rax
0x140081f75  mov     [rsp+78h+var_48], rax
0x140081f7a  mov     [rsp+78h+var_50], rax
0x140081f7f  mov     [rsp+78h+Handle], rax
0x140081f84  call    cs:__imp_DbgkWerCaptureLiveKernelDump
0x140081f8b  nop     dword ptr [rax+rax+00h]
0x140081f90  mov     rax, cs:WdfFunctions_01015
0x140081f97  mov     rdx, rdi
0x140081f9a  mov     rcx, cs:WdfDriverGlobals
0x140081fa1  mov     rax, [rax+660h]
0x140081fa8  call    _guard_dispatch_icall
0x140081fad  mov     rcx, cs:WdfFunctions_01015
0x140081fb4  mov     rdx, rax
0x140081fb7  mov     r8d, r15d
0x140081fba  mov     r9, [rcx+2B8h]
0x140081fc1  mov     rcx, cs:WdfDriverGlobals
0x140081fc8  mov     rax, r9
0x140081fcb  call    _guard_dispatch_icall
0x140081fd0  mov     ebx, 0Ch
0x140081fd5  jmp     loc_1400820F3
0x140081fda  mov     r9, [rdi+18h]; Context
0x140081fde  lea     rax, [rsp+78h+arg_10]
0x140081fe6  lea     r8, HUBPDO_ReEnumerationCallback; Callback
0x140081fed  mov     [rsp+78h+Handle], rax; Handle
0x140081ff2  lea     rdx, GUID_LOW_POWER_EPOCH; SettingGuid
0x140081ff9  xor     ecx, ecx; DeviceObject
0x140081ffb  call    cs:__imp_PoRegisterPowerSettingCallback
0x140082002  nop     dword ptr [rax+rax+00h]
0x140082007  mov     edx, eax
0x140082009  test    eax, eax
0x14008200b  jns     short loc_14008205D
0x14008200d  xor     ecx, ecx
0x14008200f  mov     eax, r13d
0x140082012  lock cmpxchg [rdi+190h], ecx
0x14008201a  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x140082021  jz      short loc_140082053
0x140082023  mov     rcx, [rdi+18h]
0x140082027  lea     rax, WPP_8beb7df92ba934db5f6899fb45b5938a_Traceguids
0x14008202e  mov     dword ptr [rsp+78h+var_50], edx
0x140082032  mov     r9d, 0B3h
0x140082038  mov     r8d, r15d
0x14008203b  mov     [rsp+78h+Handle], rax
0x140082040  mov     dl, r15b
0x140082043  mov     rcx, [rcx+8]
0x140082047  mov     rcx, [rcx+598h]
0x14008204e  call    WPP_RECORDER_SF_d
0x140082053  mov     ebx, 7
0x140082058  jmp     loc_1400820F3
0x14008205d  mov     rax, [rsp+78h+arg_10]
0x140082065  xor     edx, edx
0x140082067  mov     [rdi+198h], rax
0x14008206e  mov     rcx, [rsi]
0x140082071  call    cs:__imp_IoRequestDeviceRemovalForReset
0x140082078  nop     dword ptr [rax+rax+00h]
0x14008207d  mov     ebx, eax
0x14008207f  test    eax, eax
0x140082081  jns     short loc_1400820EE
0x140082083  mov     rcx, [rdi+198h]; Handle
0x14008208a  call    cs:__imp_PoUnregisterPowerSettingCallback
0x140082091  nop     dword ptr [rax+rax+00h]
0x140082096  xor     ecx, ecx
0x140082098  mov     qword ptr [rdi+198h], 0
0x1400820a3  mov     eax, r13d
0x1400820a6  lock cmpxchg [rdi+190h], ecx
0x1400820ae  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x1400820b5  jz      short loc_1400820E7
0x1400820b7  mov     rax, [rdi+18h]
0x1400820bb  mov     r9d, 0B4h
0x1400820c1  mov     dword ptr [rsp+78h+var_50], ebx
0x1400820c5  mov     r8d, r15d
0x1400820c8  mov     dl, r15b
0x1400820cb  mov     rcx, [rax+8]
0x1400820cf  lea     rax, WPP_8beb7df92ba934db5f6899fb45b5938a_Traceguids
0x1400820d6  mov     [rsp+78h+Handle], rax
0x1400820db  mov     rcx, [rcx+598h]
0x1400820e2  call    WPP_RECORDER_SF_d
0x1400820e7  mov     ebx, 8
0x1400820ec  jmp     short loc_1400820F3
0x1400820ee  xor     bpl, bpl
0x1400820f1  xor     ebx, ebx
0x1400820f3  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x1400820fa  jz      short loc_140082143
0x1400820fc  mov     rax, [rdi+18h]
0x140082100  movzx   edx, bpl
0x140082104  mov     [rsp+78h+var_30], edx
0x140082108  mov     [rsp+78h+var_38], ebx
0x14008210c  mov     rcx, [rax+8]
0x140082110  movzx   r8d, word ptr [rax+7D8h]
0x140082118  movzx   r9d, word ptr [rax+7D6h]
0x140082120  movzx   r10d, word ptr [rax+7D4h]
0x140082128  mov     rcx, [rcx+598h]
0x14008212f  mov     dword ptr [rsp+78h+var_40], r8d
0x140082134  mov     dword ptr [rsp+78h+var_48], r9d
0x140082139  mov     dword ptr [rsp+78h+var_50], r10d
0x14008213e  call    WPP_RECORDER_SF_DDDLd
0x140082143  test    cs:byte_14006ED43, r15b
0x14008214a  jz      short loc_140082192
0x14008214c  mov     r9, [rdi+18h]
0x140082150  lea     rdx, USBHUB3_ETW_EVENT_DEVICE_DRIPS_WATCHDOG_COMPLETE
0x140082157  movzx   eax, word ptr [r9+7D8h]
0x14008215f  lea     r8, [r9+5F4h]
0x140082166  mov     word ptr [rsp+78h+var_40], ax
0x14008216b  movzx   eax, word ptr [r9+7D6h]
0x140082173  mov     word ptr [rsp+78h+var_48], ax
0x140082178  movzx   eax, word ptr [r9+7D4h]
0x140082180  mov     r9, [r9+18h]
0x140082184  mov     word ptr [rsp+78h+var_50], ax
0x140082189  mov     dword ptr [rsp+78h+Handle], ebx
0x14008218d  call    McTemplateK0pqhhh_EtwWriteTransfer
0x140082192  cmp     ebx, r13d
0x140082195  jz      loc_140082234
0x14008219b  cmp     ebx, 0Ch
0x14008219e  jnz     short loc_1400821E5
0x1400821a0  test    cs:byte_14006ED43, 4
0x1400821a7  jz      loc_140082234
0x1400821ad  mov     r9, [rdi+18h]
0x1400821b1  lea     rdx, USBHUB3_ETW_EVENT_DEVICE_DRIPS_WATCHDOG_COMPLETE_PUBLISH_INFO
0x1400821b8  movzx   eax, word ptr [r9+7D8h]
0x1400821c0  mov     word ptr [rsp+78h+var_40], ax
0x1400821c5  movzx   eax, word ptr [r9+7D6h]
0x1400821cd  mov     word ptr [rsp+78h+var_48], ax
0x1400821d2  movzx   eax, word ptr [r9+7D4h]
0x1400821da  mov     word ptr [rsp+78h+var_50], ax
0x1400821df  mov     dword ptr [rsp+78h+Handle], ebx
0x1400821e3  jmp     short loc_140082224
0x1400821e5  test    cs:byte_14006ED43, 8
0x1400821ec  jz      short loc_140082234
0x1400821ee  mov     r9, [rdi+18h]
0x1400821f2  lea     rdx, USBHUB3_ETW_EVENT_DEVICE_DRIPS_WATCHDOG_COMPLETE_PUBLISH_WARNING
0x1400821f9  movzx   eax, word ptr [r9+7D8h]
0x140082201  mov     word ptr [rsp+78h+var_40], ax
0x140082206  movzx   eax, word ptr [r9+7D6h]
  ... truncated ...
```
