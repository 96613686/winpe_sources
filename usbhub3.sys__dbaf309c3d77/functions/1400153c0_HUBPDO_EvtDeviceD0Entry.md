# HUBPDO_EvtDeviceD0Entry

- ea: `0x1400153c0`
- end: `0x140015600`
- name: `HUBPDO_EvtDeviceD0Entry`
- size: `576`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x1400067ac`
- `0x14000a53c`
- `0x14000f304`
- `0x14000f37c`
- `0x1400153c0`
- `0x1400336a8`
- `0x14003f5b4`
- `0x140045530`
- `0x140045570`

## import_xrefs

- `ntoskrnl!PoFxActivateComponent` at `0x14001553e`
- `ntoskrnl!PoFxActivateComponent` at `0x14001553e`
- `ntoskrnl!KeClearEvent` at `0x140015565`
- `ntoskrnl!KeClearEvent` at `0x140015565`
- `ntoskrnl!EtwActivityIdControl` at `0x140015462`
- `ntoskrnl!EtwActivityIdControl` at `0x140015462`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_ComponentActive` at `0x1400155a6`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_ComponentActive` at `0x1400155a6`

## pseudocode

```c
__int64 __fastcall HUBPDO_EvtDeviceD0Entry(__int64 a1)
{
  __int64 v2; // rbp
  __int64 v3; // rdi
  char v4; // al
  int v5; // edx
  char v6; // si
  int v7; // ecx
  __int64 v8; // rcx
  __int64 v9; // rcx
  unsigned int v10; // ebx
  __int128 v12; // [rsp+40h] [rbp-58h] BYREF

  v12 = 0;
  v2 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 1616))(
         WdfDriverGlobals,
         a1,
         off_14006B1D0);
  v3 = *(_QWORD *)(v2 + 24);
  *(_DWORD *)(v2 + 384) = 1;
  v12 = 0;
  if ( (*(_DWORD *)((*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, WDFDRIVER__ *, __int64 *))(WdfFunctions_01015 + 1616))(
                      WdfDriverGlobals,
                      WdfDriverGlobals->Driver,
                      off_14006B2C0)
                  + 4)
      & 0x1000) != 0
    && EtwActivityIdControl(3u, (LPGUID)(v3 + 2184)) >= 0 )
  {
    v12 = *(_OWORD *)(v3 + 2184);
    _InterlockedOr((volatile signed __int32 *)(v3 + 1644), 0x80u);
  }
  v4 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 3104))(WdfDriverGlobals, a1);
  v6 = v4;
  if ( (Microsoft_Windows_USB_USBHUB3EnableBits & 4) != 0 )
  {
    v7 = *(_DWORD *)(v2 + 32) >> 3;
    LOWORD(v7) = (*(_DWORD *)(v2 + 32) & 8) != 0;
    McTemplateK0pqqh_EtwWriteTransfer(
      v7,
      (unsigned int)USBHUB3_ETW_EVENT_DEVICE_D0_ENTRY_START,
      (unsigned int)&v12,
      *(_QWORD *)(v3 + 24),
      1,
      v4,
      (*(_DWORD *)(v2 + 32) & 8) != 0);
  }
  v8 = *(_QWORD *)(v3 + 8);
  if ( (*(_DWORD *)(v8 + 204) & 0x800) != 0 && ((*(_DWORD *)(v3 + 2732) - 2) & 0xFFFFFFFD) == 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v5) = 4;
      WPP_RECORDER_SF_(*(_QWORD *)(v8 + 1432), v5, 5, 74, (__int64)WPP_8beb7df92ba934db5f6899fb45b5938a_Traceguids);
    }
    PoFxActivateComponent(*(_QWORD *)(*(_QWORD *)v3 + 2624LL), 0, 1);
  }
  HUBIDLE_AddEvent(v2 + 72, 6007, 0);
  KeClearEvent((PRKEVENT)(v3 + 1592));
  HUBSM_AddEvent(v3 + 512, 4067);
  HUBMISC_WaitForSignal((PVOID)(v3 + 1592));
  v9 = *(_QWORD *)(v2 + 392);
  v10 = *(_DWORD *)(v3 + 1584);
  if ( v9 )
    SleepstudyHelper_ComponentActive();
  if ( (Microsoft_Windows_USB_USBHUB3EnableBits & 4) != 0 )
    McTemplateK0pqq_EtwWriteTransfer(
      v9,
      (unsigned int)USBHUB3_ETW_EVENT_DEVICE_D0_ENTRY_COMPLETE,
      (unsigned int)&v12,
      *(_QWORD *)(v3 + 24),
      v10,
      v6);
  _InterlockedAnd((volatile signed __int32 *)(v3 + 1644), 0xFFFFFF7F);
  return v10;
}

```

## disassembly

```asm
0x1400153c0  push    rbx
0x1400153c2  push    rbp
0x1400153c3  push    rsi
0x1400153c4  push    rdi
0x1400153c5  push    r14
0x1400153c7  push    r15
0x1400153c9  sub     rsp, 68h
0x1400153cd  mov     rax, cs:__security_cookie
0x1400153d4  xor     rax, rsp
0x1400153d7  mov     [rsp+98h+var_48], rax
0x1400153dc  mov     rax, cs:WdfFunctions_01015
0x1400153e3  xorps   xmm0, xmm0
0x1400153e6  mov     r8, cs:off_14006B1D0
0x1400153ed  mov     r14, rcx
0x1400153f0  movups  [rsp+98h+var_58], xmm0
0x1400153f5  mov     rdx, rcx
0x1400153f8  mov     rcx, cs:WdfDriverGlobals
0x1400153ff  mov     rax, [rax+650h]
0x140015406  call    _guard_dispatch_icall
0x14001540b  xorps   xmm0, xmm0
0x14001540e  mov     rbp, rax
0x140015411  mov     r15d, 1
0x140015417  mov     rdi, [rax+18h]
0x14001541b  mov     [rax+180h], r15d
0x140015422  mov     rcx, cs:WdfFunctions_01015
0x140015429  mov     r8, cs:off_14006B2C0
0x140015430  movups  [rsp+98h+var_58], xmm0
0x140015435  mov     rax, [rcx+650h]
0x14001543c  mov     rcx, cs:WdfDriverGlobals
0x140015443  mov     rdx, [rcx]
0x140015446  call    _guard_dispatch_icall
0x14001544b  test    dword ptr [rax+4], 1000h
0x140015452  jz      short loc_140015486
0x140015454  lea     rbx, [rdi+888h]
0x14001545b  mov     rdx, rbx; ActivityId
0x14001545e  lea     ecx, [r15+2]; ControlCode
0x140015462  call    cs:__imp_EtwActivityIdControl
0x140015469  nop     dword ptr [rax+rax+00h]
0x14001546e  test    eax, eax
0x140015470  js      short loc_140015486
0x140015472  movups  xmm0, xmmword ptr [rbx]
0x140015475  movdqu  [rsp+98h+var_58], xmm0
0x14001547b  lock or dword ptr [rdi+66Ch], 80h
0x140015486  mov     rax, cs:WdfFunctions_01015
0x14001548d  mov     rdx, r14
0x140015490  mov     rcx, cs:WdfDriverGlobals
0x140015497  mov     rax, [rax+0C20h]
0x14001549e  call    _guard_dispatch_icall
0x1400154a3  test    cs:Microsoft_Windows_USB_USBHUB3EnableBits, 4
0x1400154aa  mov     esi, eax
0x1400154ac  jz      short loc_1400154DB
0x1400154ae  mov     ecx, [rbp+20h]
0x1400154b1  lea     r8, [rsp+98h+var_58]
0x1400154b6  mov     r9, [rdi+18h]
0x1400154ba  lea     rdx, USBHUB3_ETW_EVENT_DEVICE_D0_ENTRY_START
0x1400154c1  shr     ecx, 3
0x1400154c4  and     cx, r15w
0x1400154c8  mov     [rsp+98h+var_68], cx
0x1400154cd  mov     [rsp+98h+var_70], eax
0x1400154d1  mov     dword ptr [rsp+98h+var_78], r15d
0x1400154d6  call    McTemplateK0pqqh_EtwWriteTransfer
0x1400154db  mov     rcx, [rdi+8]
0x1400154df  test    dword ptr [rcx+0CCh], 800h
0x1400154e9  jz      short loc_14001554A
0x1400154eb  mov     eax, [rdi+0AACh]
0x1400154f1  sub     eax, 2
0x1400154f4  test    eax, 0FFFFFFFDh
0x1400154f9  jnz     short loc_14001554A
0x1400154fb  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140015502  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140015509  jz      short loc_14001552F
0x14001550b  mov     rcx, [rcx+598h]
0x140015512  lea     rax, WPP_8beb7df92ba934db5f6899fb45b5938a_Traceguids
0x140015519  mov     r9d, 4Ah ; 'J'
0x14001551f  mov     [rsp+98h+var_78], rax
0x140015524  mov     dl, 4
0x140015526  lea     r8d, [r9-45h]
0x14001552a  call    WPP_RECORDER_SF_
0x14001552f  mov     rcx, [rdi]
0x140015532  mov     r8d, r15d
0x140015535  xor     edx, edx
0x140015537  mov     rcx, [rcx+0A40h]
0x14001553e  call    cs:__imp_PoFxActivateComponent
0x140015545  nop     dword ptr [rax+rax+00h]
0x14001554a  lea     rcx, [rbp+48h]
0x14001554e  xor     r8d, r8d
0x140015551  mov     edx, 1777h
0x140015556  call    HUBIDLE_AddEvent
0x14001555b  lea     rbx, [rdi+638h]
0x140015562  mov     rcx, rbx; Event
0x140015565  call    cs:__imp_KeClearEvent
0x14001556c  nop     dword ptr [rax+rax+00h]
0x140015571  lea     rcx, [rdi+200h]
0x140015578  mov     edx, 0FE3h
0x14001557d  call    HUBSM_AddEvent
0x140015582  mov     r8, r14
0x140015585  lea     rdx, aDeviceD0entry; "Device D0Entry"
0x14001558c  mov     rcx, rbx; Object
0x14001558f  call    HUBMISC_WaitForSignal
0x140015594  mov     rcx, [rbp+188h]
0x14001559b  mov     ebx, [rdi+630h]
0x1400155a1  test    rcx, rcx
0x1400155a4  jz      short loc_1400155B2
0x1400155a6  call    cs:__imp_SleepstudyHelper_ComponentActive
0x1400155ad  nop     dword ptr [rax+rax+00h]
0x1400155b2  test    cs:Microsoft_Windows_USB_USBHUB3EnableBits, 4
0x1400155b9  jz      short loc_1400155D8
0x1400155bb  mov     r9, [rdi+18h]
0x1400155bf  lea     r8, [rsp+98h+var_58]
0x1400155c4  mov     [rsp+98h+var_70], esi
0x1400155c8  lea     rdx, USBHUB3_ETW_EVENT_DEVICE_D0_ENTRY_COMPLETE
0x1400155cf  mov     dword ptr [rsp+98h+var_78], ebx
0x1400155d3  call    McTemplateK0pqq_EtwWriteTransfer
0x1400155d8  lock and dword ptr [rdi+66Ch], 0FFFFFF7Fh
0x1400155e3  mov     eax, ebx
0x1400155e5  mov     rcx, [rsp+98h+var_48]
0x1400155ea  xor     rcx, rsp; StackCookie
0x1400155ed  call    __security_check_cookie
0x1400155f2  add     rsp, 68h
0x1400155f6  pop     r15
0x1400155f8  pop     r14
0x1400155fa  pop     rdi
0x1400155fb  pop     rsi
0x1400155fc  pop     rbp
0x1400155fd  pop     rbx
0x1400155fe  retn
```
