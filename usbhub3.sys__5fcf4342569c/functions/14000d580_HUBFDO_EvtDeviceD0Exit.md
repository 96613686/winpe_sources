# HUBFDO_EvtDeviceD0Exit

- ea: `0x14000d580`
- end: `0x14000d791`
- name: `HUBFDO_EvtDeviceD0Exit`
- size: `529`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x14000a53c`
- `0x14000d580`
- `0x14000f304`
- `0x14000f37c`
- `0x1400336a8`
- `0x140045570`

## import_xrefs

- `ntoskrnl!KeResetEvent` at `0x14000d6c8`
- `ntoskrnl!KeResetEvent` at `0x14000d6ee`
- `ntoskrnl!KeResetEvent` at `0x14000d6c8`
- `ntoskrnl!KeResetEvent` at `0x14000d6ee`
- `ntoskrnl!EtwActivityIdControl` at `0x14000d5e2`
- `ntoskrnl!EtwActivityIdControl` at `0x14000d5e2`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_ComponentInactive` at `0x14000d61e`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_ComponentInactive` at `0x14000d636`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_ComponentInactive` at `0x14000d61e`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_ComponentInactive` at `0x14000d636`

## pseudocode

```c
__int64 __fastcall HUBFDO_EvtDeviceD0Exit(__int64 a1, int a2)
{
  NTSTATUS v4; // ebx
  char v5; // r15
  __int64 v6; // rax
  __int64 v7; // rdi
  __int64 v8; // rsi
  int v9; // eax
  int v10; // esi
  int v11; // ecx
  int v12; // ecx
  void *v13; // rbx
  __int64 v14; // rcx
  __int64 v15; // rdx

  v4 = 0;
  v5 = 0;
  v6 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 1616))(
         WdfDriverGlobals,
         a1,
         off_14006B270);
  v7 = v6;
  *(_DWORD *)(v6 + 2616) = a2;
  _InterlockedAnd((volatile signed __int32 *)(v6 + 40), 0xFFFDFFFF);
  if ( (Microsoft_Windows_USB_USBHUB3EnableBits & 4) != 0 )
  {
    v8 = v6 + 2292;
    v4 = EtwActivityIdControl(3u, (LPGUID)(v6 + 2292));
    if ( v4 >= 0 )
    {
      if ( g_IoSetActivityIdIrp )
        g_IoSetActivityIdIrp(*(_QWORD *)(v7 + 832), v8);
      v5 = 1;
    }
  }
  if ( *(_QWORD *)(v7 + 2632) )
    SleepstudyHelper_ComponentInactive();
  if ( *(_QWORD *)(v7 + 2640) )
    SleepstudyHelper_ComponentInactive();
  v9 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 3104))(WdfDriverGlobals, a1);
  v10 = v9;
  if ( (Microsoft_Windows_USB_USBHUB3EnableBits & 4) != 0 )
  {
    v11 = *(_DWORD *)(v7 + 40) >> 10;
    LOWORD(v11) = (*(_DWORD *)(v7 + 40) & 0x400) != 0;
    McTemplateK0pqqh_EtwWriteTransfer(
      v11,
      (unsigned int)USBHUB3_ETW_EVENT_HUB_D0_EXIT_START,
      v7 + 2292,
      *(_QWORD *)(v7 + 248),
      a2,
      v9,
      (*(_DWORD *)(v7 + 40) & 0x400) != 0);
  }
  if ( !v10 )
  {
    v13 = (void *)(v7 + 1168);
    KeResetEvent((PRKEVENT)(v7 + 1168));
    v14 = v7 + 1280;
    v15 = 2019;
    if ( a2 == 5 )
    {
LABEL_20:
      HUBSM_AddEvent(v14, v15);
      (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 1632))(WdfDriverGlobals, v7);
      HUBMISC_WaitForSignal(v13);
      v4 = *(_DWORD *)(v7 + 1192);
      goto LABEL_21;
    }
LABEL_19:
    v15 = 2015;
    goto LABEL_20;
  }
  if ( v10 == 2 || v10 == 3 || v10 == 4 || (v12 = v10 - 5, (unsigned int)(v10 - 5) <= 1) )
  {
    v13 = (void *)(v7 + 1168);
    KeResetEvent((PRKEVENT)(v7 + 1168));
    v14 = v7 + 1280;
    goto LABEL_19;
  }
LABEL_21:
  if ( (Microsoft_Windows_USB_USBHUB3EnableBits & 4) != 0 )
    McTemplateK0pqq_EtwWriteTransfer(
      v12,
      (unsigned int)USBHUB3_ETW_EVENT_HUB_D0_EXIT_COMPLETE,
      v7 + 2292,
      *(_QWORD *)(v7 + 248),
      v4,
      v10);
  if ( v5 == 1 )
    *(_OWORD *)(v7 + 2292) = 0;
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x14000d580  push    rbx
0x14000d582  push    rbp
0x14000d583  push    rsi
0x14000d584  push    rdi
0x14000d585  push    r14
0x14000d587  push    r15
0x14000d589  sub     rsp, 48h
0x14000d58d  mov     rax, cs:WdfFunctions_01015
0x14000d594  mov     ebp, edx
0x14000d596  mov     r8, cs:off_14006B270
0x14000d59d  mov     r14, rcx
0x14000d5a0  mov     rdx, rcx
0x14000d5a3  xor     ebx, ebx
0x14000d5a5  mov     rcx, cs:WdfDriverGlobals
0x14000d5ac  xor     r15b, r15b
0x14000d5af  mov     rax, [rax+650h]
0x14000d5b6  call    _guard_dispatch_icall
0x14000d5bb  mov     rdi, rax
0x14000d5be  mov     [rax+0A38h], ebp
0x14000d5c4  lock and dword ptr [rax+28h], 0FFFDFFFFh
0x14000d5cc  test    cs:Microsoft_Windows_USB_USBHUB3EnableBits, 4
0x14000d5d3  jz      short loc_14000D612
0x14000d5d5  lea     rsi, [rax+8F4h]
0x14000d5dc  mov     rdx, rsi; ActivityId
0x14000d5df  lea     ecx, [rbx+3]; ControlCode
0x14000d5e2  call    cs:__imp_EtwActivityIdControl
0x14000d5e9  nop     dword ptr [rax+rax+00h]
0x14000d5ee  mov     ebx, eax
0x14000d5f0  test    eax, eax
0x14000d5f2  js      short loc_14000D612
0x14000d5f4  mov     rax, cs:g_IoSetActivityIdIrp
0x14000d5fb  test    rax, rax
0x14000d5fe  jz      short loc_14000D60F
0x14000d600  mov     rcx, [rdi+340h]
0x14000d607  mov     rdx, rsi
0x14000d60a  call    _guard_dispatch_icall
0x14000d60f  mov     r15b, 1
0x14000d612  mov     rcx, [rdi+0A48h]
0x14000d619  test    rcx, rcx
0x14000d61c  jz      short loc_14000D62A
0x14000d61e  call    cs:__imp_SleepstudyHelper_ComponentInactive
0x14000d625  nop     dword ptr [rax+rax+00h]
0x14000d62a  mov     rcx, [rdi+0A50h]
0x14000d631  test    rcx, rcx
0x14000d634  jz      short loc_14000D642
0x14000d636  call    cs:__imp_SleepstudyHelper_ComponentInactive
0x14000d63d  nop     dword ptr [rax+rax+00h]
0x14000d642  mov     rax, cs:WdfFunctions_01015
0x14000d649  mov     rdx, r14
0x14000d64c  mov     rcx, cs:WdfDriverGlobals
0x14000d653  mov     rax, [rax+0C20h]
0x14000d65a  call    _guard_dispatch_icall
0x14000d65f  test    cs:Microsoft_Windows_USB_USBHUB3EnableBits, 4
0x14000d666  mov     esi, eax
0x14000d668  jz      short loc_14000D69B
0x14000d66a  mov     ecx, [rdi+28h]
0x14000d66d  lea     r8, [rdi+8F4h]
0x14000d674  mov     r9, [rdi+0F8h]
0x14000d67b  lea     rdx, USBHUB3_ETW_EVENT_HUB_D0_EXIT_START
0x14000d682  shr     ecx, 0Ah
0x14000d685  and     cx, 1
0x14000d689  mov     [rsp+78h+var_48], cx
0x14000d68e  mov     [rsp+78h+var_50], eax
0x14000d692  mov     [rsp+78h+var_58], ebp
0x14000d696  call    McTemplateK0pqqh_EtwWriteTransfer
0x14000d69b  mov     ecx, esi
0x14000d69d  test    esi, esi
0x14000d69f  jz      short loc_14000D6DD
0x14000d6a1  sub     ecx, 2
0x14000d6a4  jz      short loc_14000D6BE
0x14000d6a6  sub     ecx, 1
0x14000d6a9  jz      short loc_14000D6BE
0x14000d6ab  sub     ecx, 1
0x14000d6ae  jz      short loc_14000D6BE
0x14000d6b0  sub     ecx, 1
0x14000d6b3  jz      short loc_14000D6BE
0x14000d6b5  cmp     ecx, 1
0x14000d6b8  jnz     loc_14000D746
0x14000d6be  lea     rbx, [rdi+490h]
0x14000d6c5  mov     rcx, rbx; Event
0x14000d6c8  call    cs:__imp_KeResetEvent
0x14000d6cf  nop     dword ptr [rax+rax+00h]
0x14000d6d4  lea     rcx, [rdi+500h]
0x14000d6db  jmp     short loc_14000D707
0x14000d6dd  lea     rbx, [rdi+490h]
0x14000d6e4  mov     rcx, rbx; Event
0x14000d6e7  lea     r14, [rdi+500h]
0x14000d6ee  call    cs:__imp_KeResetEvent
0x14000d6f5  nop     dword ptr [rax+rax+00h]
0x14000d6fa  mov     rcx, r14
0x14000d6fd  mov     edx, 7E3h
0x14000d702  cmp     ebp, 5
0x14000d705  jz      short loc_14000D70C
0x14000d707  mov     edx, 7DFh
0x14000d70c  call    HUBSM_AddEvent
0x14000d711  mov     rax, cs:WdfFunctions_01015
0x14000d718  mov     rdx, rdi
0x14000d71b  mov     rcx, cs:WdfDriverGlobals
0x14000d722  mov     rax, [rax+660h]
0x14000d729  call    _guard_dispatch_icall
0x14000d72e  mov     r8, rax
0x14000d731  lea     rdx, aHubFdoPnpcallb; "Hub FDO PnpCallback"
0x14000d738  mov     rcx, rbx; Object
0x14000d73b  call    HUBMISC_WaitForSignal
0x14000d740  mov     ebx, [rdi+4A8h]
0x14000d746  test    cs:Microsoft_Windows_USB_USBHUB3EnableBits, 4
0x14000d74d  jz      short loc_14000D771
0x14000d74f  mov     r9, [rdi+0F8h]
0x14000d756  lea     r8, [rdi+8F4h]
0x14000d75d  mov     [rsp+78h+var_50], esi
0x14000d761  lea     rdx, USBHUB3_ETW_EVENT_HUB_D0_EXIT_COMPLETE
0x14000d768  mov     [rsp+78h+var_58], ebx
0x14000d76c  call    McTemplateK0pqq_EtwWriteTransfer
0x14000d771  cmp     r15b, 1
0x14000d775  jnz     short loc_14000D781
0x14000d777  xorps   xmm0, xmm0
0x14000d77a  movups  xmmword ptr [rdi+8F4h], xmm0
0x14000d781  mov     eax, ebx
0x14000d783  add     rsp, 48h
0x14000d787  pop     r15
0x14000d789  pop     r14
0x14000d78b  pop     rdi
0x14000d78c  pop     rsi
0x14000d78d  pop     rbp
0x14000d78e  pop     rbx
0x14000d78f  retn
```
