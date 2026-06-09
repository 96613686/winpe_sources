# HUBPDO_EvtDeviceD0Exit

- ea: `0x140015610`
- end: `0x140015a72`
- name: `HUBPDO_EvtDeviceD0Exit`
- size: `1122`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1400024b8`
- `0x1400067ac`
- `0x14000a53c`
- `0x14000f304`
- `0x14000f37c`
- `0x140014580`
- `0x140015610`
- `0x1400336a8`
- `0x14003f5b4`
- `0x140045530`
- `0x140045570`
- `0x14008d9e0`
- `0x14008e0e0`

## import_xrefs

- `ntoskrnl!PoFxIdleComponent` at `0x140015a12`
- `ntoskrnl!PoFxIdleComponent` at `0x140015a12`
- `ntoskrnl!KeClearEvent` at `0x1400156e5`
- `ntoskrnl!KeClearEvent` at `0x1400156e5`
- `ntoskrnl!EtwActivityIdControl` at `0x1400156b7`
- `ntoskrnl!EtwActivityIdControl` at `0x1400156b7`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_ComponentInactive` at `0x1400159a2`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_ComponentInactive` at `0x1400159a2`

## pseudocode

```c
__int64 __fastcall HUBPDO_EvtDeviceD0Exit(unsigned __int64 a1, int a2)
{
  __int64 v4; // rdi
  __int64 v5; // rbx
  int v6; // eax
  __int64 v7; // r8
  int v8; // r14d
  int v9; // ecx
  int v10; // eax
  int v11; // edx
  int v12; // eax
  int v13; // edx
  unsigned int v14; // esi
  int v15; // edx
  int IsEnabledDeviceUsageNoInline; // eax
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v20; // [rsp+28h] [rbp-71h]
  __int64 v21; // [rsp+40h] [rbp-59h] BYREF
  __int128 v22; // [rsp+48h] [rbp-51h] BYREF
  __int64 v23; // [rsp+58h] [rbp-41h]
  __int128 v24; // [rsp+60h] [rbp-39h] BYREF
  __int128 v25; // [rsp+70h] [rbp-29h]
  __int128 v26; // [rsp+80h] [rbp-19h]
  __int64 v27; // [rsp+90h] [rbp-9h]
  __int128 v28; // [rsp+98h] [rbp-1h] BYREF

  v28 = 0;
  v4 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, unsigned __int64, __int64 *))(WdfFunctions_01015 + 1616))(
         WdfDriverGlobals,
         a1,
         off_14006B1D0);
  v5 = *(_QWORD *)(v4 + 24);
  *(_DWORD *)(v4 + 384) = a2;
  v28 = 0;
  if ( (*(_DWORD *)((*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, WDFDRIVER__ *, __int64 *))(WdfFunctions_01015 + 1616))(
                      WdfDriverGlobals,
                      WdfDriverGlobals->Driver,
                      off_14006B2C0)
                  + 4)
      & 0x1000) != 0
    && EtwActivityIdControl(3u, (LPGUID)(v5 + 2184)) >= 0 )
  {
    v28 = *(_OWORD *)(v5 + 2184);
    _InterlockedOr((volatile signed __int32 *)(v5 + 1644), 0x80u);
  }
  KeClearEvent((PRKEVENT)(v5 + 1592));
  v6 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, unsigned __int64))(WdfFunctions_01015 + 3104))(
         WdfDriverGlobals,
         a1);
  v8 = v6;
  if ( (Microsoft_Windows_USB_USBHUB3EnableBits & 4) != 0 )
  {
    v9 = *(_DWORD *)(v4 + 32) >> 3;
    LOWORD(v9) = (*(_DWORD *)(v4 + 32) & 8) != 0;
    McTemplateK0pqqh_EtwWriteTransfer(
      v9,
      (unsigned int)USBHUB3_ETW_EVENT_DEVICE_D0_EXIT_START,
      (unsigned int)&v28,
      *(_QWORD *)(v5 + 24),
      a2,
      v6,
      (*(_DWORD *)(v4 + 32) & 8) != 0);
  }
  if ( a2 == 5 )
  {
    if ( !v8 )
      goto LABEL_26;
  }
  else if ( !v8 && (*(_DWORD *)(v5 + 1640) & 0x400) == 0 )
  {
    v24 = 0;
    LODWORD(v27) = 0;
    v25 = 0;
    LODWORD(v23) = 0;
    v26 = 0;
    v21 = 0;
    v22 = 0;
    _InterlockedOr((volatile signed __int32 *)(v5 + 1640), 0x400u);
    v27 = 0;
    *(_QWORD *)&v22 = 24;
    *(_QWORD *)&v25 = 0;
    *((_QWORD *)&v22 + 1) = HUBREG_EvtWorkItemUpdateSqmDeviceSelectiveSuspended;
    v24 = 0;
    LODWORD(v24) = 56;
    *((_QWORD *)&v25 + 1) = 0x100000001LL;
    v26 = a1;
    v23 = 1;
    v10 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int128 *, __int128 *, __int64 *))(WdfFunctions_01015 + 3032))(
            WdfDriverGlobals,
            &v22,
            &v24,
            &v21);
    if ( v10 >= 0 )
    {
      (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 3040))(WdfDriverGlobals, v21);
    }
    else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LODWORD(v20) = v10;
      LOBYTE(v11) = 2;
      WPP_RECORDER_SF_d(
        *(_QWORD *)(*(_QWORD *)(v5 + 8) + 1432LL),
        v11,
        2,
        75,
        (__int64)WPP_8beb7df92ba934db5f6899fb45b5938a_Traceguids,
        v20);
    }
  }
  if ( a2 == 6 )
  {
    HUBSM_AddEvent(v5 + 512, 4079);
  }
  else
  {
    if ( a2 == 4 )
    {
      if ( (*(_DWORD *)(v4 + 32) & 4) != 0 )
      {
        v12 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, unsigned __int64, __int64))(WdfFunctions_01015 + 688))(
                WdfDriverGlobals,
                a1,
                3221226195LL);
        if ( v12 < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LODWORD(v20) = v12;
          LOBYTE(v13) = 3;
          WPP_RECORDER_SF_d(
            *(_QWORD *)(*(_QWORD *)(v5 + 8) + 1432LL),
            v13,
            5,
            76,
            (__int64)WPP_8beb7df92ba934db5f6899fb45b5938a_Traceguids,
            v20);
        }
        _InterlockedAnd((volatile signed __int32 *)(v4 + 32), 0xFFFFFFFB);
      }
      if ( (*(_DWORD *)(v5 + 1640) & 0x4000) == 0 )
        HUBIDLE_AddEvent(v4 + 72, 6008, 0);
    }
    HUBSM_AddEvent(v5 + 512, 4071);
  }
  HUBMISC_WaitForSignal((PVOID)(v5 + 1592));
LABEL_26:
  LOBYTE(v7) = 1;
  v14 = *(_DWORD *)(v5 + 1584);
  if ( (*(unsigned __int8 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, __int64))(WdfFunctions_01015 + 2560))(
         WdfDriverGlobals,
         *(_QWORD *)(v5 + 2424),
         v7) == 1 )
  {
    IsEnabledDeviceUsageNoInline = Feature_UH3WET__private_IsEnabledDeviceUsageNoInline();
    v17 = *(_QWORD *)(v5 + 8);
    if ( IsEnabledDeviceUsageNoInline )
      WMI_FireNotification((__int64 *)v17, 1);
    else
      WMI_FireNotificationOld(*(_QWORD *)v5, *(_WORD *)(v17 + 200), 1u);
  }
  if ( *(_QWORD *)(v4 + 392) )
    SleepstudyHelper_ComponentInactive();
  v18 = *(_QWORD *)(v5 + 8);
  if ( (*(_DWORD *)(v18 + 204) & 0x800) != 0 && ((*(_DWORD *)(v5 + 2732) - 2) & 0xFFFFFFFD) == 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v15) = 4;
      WPP_RECORDER_SF_(*(_QWORD *)(v18 + 1432), v15, 5, 77, (__int64)WPP_8beb7df92ba934db5f6899fb45b5938a_Traceguids);
    }
    PoFxIdleComponent(*(_QWORD *)(*(_QWORD *)v5 + 2624LL), 0, 2);
  }
  if ( (Microsoft_Windows_USB_USBHUB3EnableBits & 4) != 0 )
    McTemplateK0pqq_EtwWriteTransfer(
      v18,
      (unsigned int)USBHUB3_ETW_EVENT_DEVICE_D0_EXIT_COMPLETE,
      (unsigned int)&v28,
      *(_QWORD *)(v5 + 24),
      v14,
      v8);
  _InterlockedAnd((volatile signed __int32 *)(v5 + 1644), 0xFFFFFF7F);
  return v14;
}

```

## disassembly

```asm
0x140015610  push    rbp
0x140015612  push    rbx
0x140015613  push    rsi
0x140015614  push    rdi
0x140015615  push    r12
0x140015617  push    r13
0x140015619  push    r14
0x14001561b  push    r15
0x14001561d  lea     rbp, [rsp-1Fh]
0x140015622  sub     rsp, 0B8h
0x140015629  mov     rax, cs:__security_cookie
0x140015630  xor     rax, rsp
0x140015633  mov     [rbp+57h+var_48], rax
0x140015637  mov     rax, cs:WdfFunctions_01015
0x14001563e  xorps   xmm0, xmm0
0x140015641  mov     r8, cs:off_14006B1D0
0x140015648  mov     esi, edx
0x14001564a  mov     r15, rcx
0x14001564d  mov     rdx, rcx
0x140015650  mov     rcx, cs:WdfDriverGlobals
0x140015657  movups  [rbp+57h+var_58], xmm0
0x14001565b  mov     rax, [rax+650h]
0x140015662  call    _guard_dispatch_icall
0x140015667  xorps   xmm0, xmm0
0x14001566a  mov     rdi, rax
0x14001566d  mov     rbx, [rax+18h]
0x140015671  mov     [rax+180h], esi
0x140015677  mov     rcx, cs:WdfFunctions_01015
0x14001567e  mov     r8, cs:off_14006B2C0
0x140015685  movups  [rbp+57h+var_58], xmm0
0x140015689  mov     rax, [rcx+650h]
0x140015690  mov     rcx, cs:WdfDriverGlobals
0x140015697  mov     rdx, [rcx]
0x14001569a  call    _guard_dispatch_icall
0x14001569f  test    dword ptr [rax+4], 1000h
0x1400156a6  jz      short loc_1400156DB
0x1400156a8  lea     r14, [rbx+888h]
0x1400156af  mov     ecx, 3; ControlCode
0x1400156b4  mov     rdx, r14; ActivityId
0x1400156b7  call    cs:__imp_EtwActivityIdControl
0x1400156be  nop     dword ptr [rax+rax+00h]
0x1400156c3  test    eax, eax
0x1400156c5  js      short loc_1400156DB
0x1400156c7  movups  xmm0, xmmword ptr [r14]
0x1400156cb  movdqu  [rbp+57h+var_58], xmm0
0x1400156d0  lock or dword ptr [rbx+66Ch], 80h
0x1400156db  lea     r12, [rbx+638h]
0x1400156e2  mov     rcx, r12; Event
0x1400156e5  call    cs:__imp_KeClearEvent
0x1400156ec  nop     dword ptr [rax+rax+00h]
0x1400156f1  mov     rax, cs:WdfFunctions_01015
0x1400156f8  mov     rdx, r15
0x1400156fb  mov     rcx, cs:WdfDriverGlobals
0x140015702  mov     rax, [rax+0C20h]
0x140015709  call    _guard_dispatch_icall
0x14001570e  test    cs:Microsoft_Windows_USB_USBHUB3EnableBits, 4
0x140015715  mov     r14d, eax
0x140015718  mov     r13d, 1
0x14001571e  jz      short loc_14001574B
0x140015720  mov     ecx, [rdi+20h]
0x140015723  lea     r8, [rbp+57h+var_58]
0x140015727  mov     r9, [rbx+18h]
0x14001572b  lea     rdx, USBHUB3_ETW_EVENT_DEVICE_D0_EXIT_START
0x140015732  shr     ecx, 3
0x140015735  and     cx, r13w
0x140015739  mov     [rsp+0F0h+var_C0], cx
0x14001573e  mov     dword ptr [rsp+0F0h+var_C8], eax
0x140015742  mov     dword ptr [rsp+0F0h+var_D0], esi
0x140015746  call    McTemplateK0pqqh_EtwWriteTransfer
0x14001574b  cmp     esi, 5
0x14001574e  jz      loc_14001585C
0x140015754  test    r14d, r14d
0x140015757  jnz     loc_140015865
0x14001575d  mov     ecx, 400h
0x140015762  test    [rbx+668h], ecx
0x140015768  jnz     loc_140015865
0x14001576e  xorps   xmm0, xmm0
0x140015771  xor     eax, eax
0x140015773  movups  [rbp+57h+var_90], xmm0
0x140015777  mov     dword ptr [rbp+57h+var_60], eax
0x14001577a  movups  [rbp+57h+var_80], xmm0
0x14001577e  mov     dword ptr [rbp+57h+var_98], eax
0x140015781  movups  [rbp+57h+var_70], xmm0
0x140015785  mov     [rbp+57h+var_B0], rax
0x140015789  movups  [rbp+57h+var_A8], xmm0
0x14001578d  lock or [rbx+668h], ecx
0x140015794  mov     rcx, cs:WdfDriverGlobals
0x14001579b  lea     r9, [rbp+57h+var_B0]
0x14001579f  mov     [rbp+57h+var_98], rax
0x1400157a3  lea     r8, [rbp+57h+var_90]
0x1400157a7  mov     [rbp+57h+var_60], rax
0x1400157ab  lea     rdx, [rbp+57h+var_A8]
0x1400157af  movups  [rbp+57h+var_A8], xmm0
0x1400157b3  lea     rax, HUBREG_EvtWorkItemUpdateSqmDeviceSelectiveSuspended
0x1400157ba  mov     dword ptr [rbp+57h+var_A8], 18h
0x1400157c1  movups  [rbp+57h+var_80], xmm0
0x1400157c5  mov     qword ptr [rbp+57h+var_A8+8], rax
0x1400157c9  mov     rax, cs:WdfFunctions_01015
0x1400157d0  movups  [rbp+57h+var_90], xmm0
0x1400157d4  mov     dword ptr [rbp+57h+var_90], 38h ; '8'
0x1400157db  movups  [rbp+57h+var_70], xmm0
0x1400157df  mov     dword ptr [rbp+57h+var_80+8], r13d
0x1400157e3  mov     dword ptr [rbp+57h+var_80+0Ch], r13d
0x1400157e7  mov     qword ptr [rbp+57h+var_70], r15
0x1400157eb  mov     byte ptr [rbp+57h+var_98], r13b
0x1400157ef  mov     rax, [rax+0BD8h]
0x1400157f6  call    _guard_dispatch_icall
0x1400157fb  test    eax, eax
0x1400157fd  jns     short loc_14001583C
0x1400157ff  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140015806  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14001580d  jz      short loc_140015865
0x14001580f  mov     rcx, [rbx+8]
0x140015813  lea     r8d, [r14+2]
0x140015817  mov     dword ptr [rsp+0F0h+var_C8], eax
0x14001581b  lea     r9d, [r14+4Bh]
0x14001581f  lea     rax, WPP_8beb7df92ba934db5f6899fb45b5938a_Traceguids
0x140015826  mov     dl, r8b
0x140015829  mov     [rsp+0F0h+var_D0], rax
0x14001582e  mov     rcx, [rcx+598h]
0x140015835  call    WPP_RECORDER_SF_d
0x14001583a  jmp     short loc_140015865
0x14001583c  mov     rax, cs:WdfFunctions_01015
0x140015843  mov     rdx, [rbp+57h+var_B0]
0x140015847  mov     rcx, cs:WdfDriverGlobals
0x14001584e  mov     rax, [rax+0BE0h]
0x140015855  call    _guard_dispatch_icall
0x14001585a  jmp     short loc_140015865
0x14001585c  test    r14d, r14d
0x14001585f  jz      loc_14001593E
0x140015865  cmp     esi, 6
0x140015868  jnz     short loc_140015887
0x14001586a  lea     rcx, [rbx+200h]
0x140015871  mov     edx, 0FEFh
0x140015876  call    HUBSM_AddEvent
0x14001587b  lea     rdx, aDeviceD0exitPr; "Device D0Exit Prepare For Hibernation"
0x140015882  jmp     loc_140015933
0x140015887  cmp     esi, 4
0x14001588a  jnz     loc_14001591B
0x140015890  mov     eax, [rdi+20h]
0x140015893  test    sil, al
0x140015896  jz      short loc_1400158FE
0x140015898  mov     rax, cs:WdfFunctions_01015
0x14001589f  mov     r8d, 0C00002D3h
0x1400158a5  mov     rcx, cs:WdfDriverGlobals
0x1400158ac  mov     rdx, r15
0x1400158af  mov     rax, [rax+2B0h]
0x1400158b6  call    _guard_dispatch_icall
0x1400158bb  test    eax, eax
0x1400158bd  jns     short loc_1400158F9
0x1400158bf  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400158c6  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x1400158cd  jz      short loc_1400158F9
0x1400158cf  mov     rcx, [rbx+8]
0x1400158d3  lea     r9d, [rsi+48h]
0x1400158d7  mov     dword ptr [rsp+0F0h+var_C8], eax
0x1400158db  lea     r8d, [rsi+1]
0x1400158df  lea     rax, WPP_8beb7df92ba934db5f6899fb45b5938a_Traceguids
0x1400158e6  mov     dl, 3
0x1400158e8  mov     [rsp+0F0h+var_D0], rax
0x1400158ed  mov     rcx, [rcx+598h]
0x1400158f4  call    WPP_RECORDER_SF_d
0x1400158f9  lock and dword ptr [rdi+20h], 0FFFFFFFBh
0x1400158fe  test    dword ptr [rbx+668h], 4000h
0x140015908  jnz     short loc_14001591B
0x14001590a  lea     rcx, [rdi+48h]
0x14001590e  xor     r8d, r8d
0x140015911  mov     edx, 1778h
0x140015916  call    HUBIDLE_AddEvent
0x14001591b  lea     rcx, [rbx+200h]
0x140015922  mov     edx, 0FE7h
0x140015927  call    HUBSM_AddEvent
0x14001592c  lea     rdx, aDeviceD0exit; "Device D0Exit"
0x140015933  mov     r8, r15
0x140015936  mov     rcx, r12; Object
0x140015939  call    HUBMISC_WaitForSignal
0x14001593e  mov     rax, cs:WdfFunctions_01015
0x140015945  mov     r8b, r13b
0x140015948  mov     rdx, [rbx+978h]
0x14001594f  mov     rcx, cs:WdfDriverGlobals
0x140015956  mov     esi, [rbx+630h]
0x14001595c  mov     rax, [rax+0A00h]
0x140015963  call    _guard_dispatch_icall
0x140015968  cmp     al, r13b
0x14001596b  jnz     short loc_140015996
0x14001596d  call    Feature_UH3WET__private_IsEnabledDeviceUsageNoInline
0x140015972  mov     rcx, [rbx+8]
0x140015976  test    eax, eax
0x140015978  jz      short loc_140015984
0x14001597a  mov     edx, r13d
0x14001597d  call    WMI_FireNotification
0x140015982  jmp     short loc_140015996
0x140015984  movzx   edx, word ptr [rcx+0C8h]
0x14001598b  mov     r8d, r13d
0x14001598e  mov     rcx, [rbx]
0x140015991  call    WMI_FireNotificationOld
0x140015996  mov     rcx, [rdi+188h]
0x14001599d  test    rcx, rcx
0x1400159a0  jz      short loc_1400159AE
0x1400159a2  call    cs:__imp_SleepstudyHelper_ComponentInactive
0x1400159a9  nop     dword ptr [rax+rax+00h]
0x1400159ae  mov     rcx, [rbx+8]
0x1400159b2  test    dword ptr [rcx+0CCh], 800h
0x1400159bc  jz      short loc_140015A1E
0x1400159be  mov     eax, [rbx+0AACh]
0x1400159c4  sub     eax, 2
0x1400159c7  test    eax, 0FFFFFFFDh
0x1400159cc  jnz     short loc_140015A1E
0x1400159ce  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400159d5  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400159dc  jz      short loc_140015A02
0x1400159de  mov     rcx, [rcx+598h]
0x1400159e5  lea     rax, WPP_8beb7df92ba934db5f6899fb45b5938a_Traceguids
0x1400159ec  mov     r9d, 4Dh ; 'M'
0x1400159f2  mov     [rsp+0F0h+var_D0], rax
0x1400159f7  mov     dl, 4
0x1400159f9  lea     r8d, [r9-48h]
0x1400159fd  call    WPP_RECORDER_SF_
0x140015a02  mov     rcx, [rbx]
0x140015a05  xor     edx, edx
0x140015a07  mov     rcx, [rcx+0A40h]
0x140015a0e  lea     r8d, [rdx+2]
0x140015a12  call    cs:__imp_PoFxIdleComponent
0x140015a19  nop     dword ptr [rax+rax+00h]
0x140015a1e  test    cs:Microsoft_Windows_USB_USBHUB3EnableBits, 4
0x140015a25  jz      short loc_140015A44
0x140015a27  mov     r9, [rbx+18h]
0x140015a2b  lea     r8, [rbp+57h+var_58]
0x140015a2f  mov     dword ptr [rsp+0F0h+var_C8], r14d
0x140015a34  lea     rdx, USBHUB3_ETW_EVENT_DEVICE_D0_EXIT_COMPLETE
0x140015a3b  mov     dword ptr [rsp+0F0h+var_D0], esi
0x140015a3f  call    McTemplateK0pqq_EtwWriteTransfer
0x140015a44  lock and dword ptr [rbx+66Ch], 0FFFFFF7Fh
0x140015a4f  mov     eax, esi
0x140015a51  mov     rcx, [rbp+57h+var_48]
0x140015a55  xor     rcx, rsp; StackCookie
0x140015a58  call    __security_check_cookie
0x140015a5d  add     rsp, 0B8h
0x140015a64  pop     r15
0x140015a66  pop     r14
0x140015a68  pop     r13
0x140015a6a  pop     r12
0x140015a6c  pop     rdi
0x140015a6d  pop     rsi
0x140015a6e  pop     rbx
0x140015a6f  pop     rbp
0x140015a70  retn
```
