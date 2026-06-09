# HUBPDO_EvtDeviceResourceRequirementsQuery

- ea: `0x140081a00`
- end: `0x140081ba3`
- name: `HUBPDO_EvtDeviceResourceRequirementsQuery`
- size: `419`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1400024b8`
- `0x14000a520`
- `0x1400336a8`
- `0x140045570`
- `0x140081a00`

## import_xrefs

- `ntoskrnl!KeClearEvent` at `0x140081aec`
- `ntoskrnl!KeClearEvent` at `0x140081b21`
- `ntoskrnl!KeClearEvent` at `0x140081aec`
- `ntoskrnl!KeClearEvent` at `0x140081b21`

## string_xrefs

- `0x140081b08`: `Pre Start Completion`

## pseudocode

```c
__int64 __fastcall HUBPDO_EvtDeviceResourceRequirementsQuery(const void *a1)
{
  _QWORD *v2; // rdi
  __int64 v3; // rax
  __int64 v4; // r8
  int v5; // eax
  int v6; // edx
  __int64 v7; // rax

  v2 = *(_QWORD **)((*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, const void *, __int64 *))(WdfFunctions_01015 + 1616))(
                      WdfDriverGlobals,
                      a1,
                      off_14006B1D0)
                  + 24);
  v3 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01015 + 1632))(WdfDriverGlobals, *v2);
  LOBYTE(v4) = 1;
  v5 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64, _QWORD, int, const char *))(WdfFunctions_01015 + 3504))(
         WdfDriverGlobals,
         v3,
         v4,
         0,
         10972,
         "onecore\\drivers\\wdm\\usb\\usb3\\hub\\src\\hubpdo.c");
  if ( v5 >= 0 )
  {
    if ( (*((_DWORD *)v2 + 411) & 0x4000) == 0 )
    {
      KeClearEvent((PRKEVENT)(v2 + 202));
      HUBSM_AddDsmEvent(v2, 4095);
      HUBMISC_WaitForSignal(v2 + 202, "Pre Start Completion", a1);
    }
    KeClearEvent((PRKEVENT)(v2 + 199));
    HUBSM_AddDsmEvent(v2, 4091);
    HUBMISC_WaitForSignal(v2 + 199, "Device ResourcesQuery", a1);
    v7 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01015 + 1632))(WdfDriverGlobals, *v2);
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD, __int64, const char *))(WdfFunctions_01015 + 3512))(
      WdfDriverGlobals,
      v7,
      0,
      11011,
      "onecore\\drivers\\wdm\\usb\\usb3\\hub\\src\\hubpdo.c");
  }
  else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v6) = 2;
    WPP_RECORDER_SF_d(
      *(_QWORD *)(v2[1] + 1432LL),
      v6,
      5,
      165,
      (__int64)WPP_8beb7df92ba934db5f6899fb45b5938a_Traceguids,
      v5);
  }
  return 0;
}

```

## disassembly

```asm
0x140081a00  push    rbx
0x140081a02  push    rbp
0x140081a03  push    rsi
0x140081a04  push    rdi
0x140081a05  sub     rsp, 48h
0x140081a09  mov     rax, cs:WdfFunctions_01015
0x140081a10  mov     rsi, rcx
0x140081a13  mov     r8, cs:off_14006B1D0
0x140081a1a  mov     rdx, rcx
0x140081a1d  mov     rcx, cs:WdfDriverGlobals
0x140081a24  mov     rax, [rax+650h]
0x140081a2b  call    _guard_dispatch_icall
0x140081a30  mov     rcx, cs:WdfDriverGlobals
0x140081a37  mov     rdi, [rax+18h]
0x140081a3b  mov     rax, cs:WdfFunctions_01015
0x140081a42  mov     rdx, [rdi]
0x140081a45  mov     rax, [rax+660h]
0x140081a4c  call    _guard_dispatch_icall
0x140081a51  mov     rcx, cs:WdfFunctions_01015
0x140081a58  lea     rbp, aOnecoreDrivers_1; "onecore\\drivers\\wdm\\usb\\usb3\\hub\\"...
0x140081a5f  mov     rdx, rax
0x140081a62  mov     [rsp+68h+var_40], rbp
0x140081a67  xor     r9d, r9d
0x140081a6a  mov     dword ptr [rsp+68h+var_48], 2ADCh
0x140081a72  mov     r8b, 1
0x140081a75  mov     r10, [rcx+0DB0h]
0x140081a7c  mov     rcx, cs:WdfDriverGlobals
0x140081a83  mov     rax, r10
0x140081a86  call    _guard_dispatch_icall
0x140081a8b  test    eax, eax
0x140081a8d  jns     short loc_140081AD6
0x140081a8f  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140081a96  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140081a9d  jz      loc_140081B97
0x140081aa3  mov     rcx, [rdi+8]
0x140081aa7  mov     r9d, 0A5h
0x140081aad  mov     dword ptr [rsp+68h+var_40], eax
0x140081ab1  mov     r8d, 5
0x140081ab7  lea     rax, WPP_8beb7df92ba934db5f6899fb45b5938a_Traceguids
0x140081abe  mov     dl, 2
0x140081ac0  mov     [rsp+68h+var_48], rax
0x140081ac5  mov     rcx, [rcx+598h]
0x140081acc  call    WPP_RECORDER_SF_d
0x140081ad1  jmp     loc_140081B97
0x140081ad6  test    dword ptr [rdi+66Ch], 4000h
0x140081ae0  jnz     short loc_140081B17
0x140081ae2  lea     rbx, [rdi+650h]
0x140081ae9  mov     rcx, rbx; Event
0x140081aec  call    cs:__imp_KeClearEvent
0x140081af3  nop     dword ptr [rax+rax+00h]
0x140081af8  mov     edx, 0FFFh
0x140081afd  mov     rcx, rdi
0x140081b00  call    HUBSM_AddDsmEvent
0x140081b05  mov     r8, rsi
0x140081b08  lea     rdx, aPreStartComple; "Pre Start Completion"
0x140081b0f  mov     rcx, rbx; Object
0x140081b12  call    HUBMISC_WaitForSignal
0x140081b17  lea     rbx, [rdi+638h]
0x140081b1e  mov     rcx, rbx; Event
0x140081b21  call    cs:__imp_KeClearEvent
0x140081b28  nop     dword ptr [rax+rax+00h]
0x140081b2d  mov     edx, 0FFBh
0x140081b32  mov     rcx, rdi
0x140081b35  call    HUBSM_AddDsmEvent
0x140081b3a  mov     r8, rsi
0x140081b3d  lea     rdx, aDeviceResource; "Device ResourcesQuery"
0x140081b44  mov     rcx, rbx; Object
0x140081b47  call    HUBMISC_WaitForSignal
0x140081b4c  mov     rax, cs:WdfFunctions_01015
0x140081b53  mov     rdx, [rdi]
0x140081b56  mov     rcx, cs:WdfDriverGlobals
0x140081b5d  mov     rax, [rax+660h]
0x140081b64  call    _guard_dispatch_icall
0x140081b69  mov     rcx, cs:WdfFunctions_01015
0x140081b70  mov     rdx, rax
0x140081b73  mov     r9d, 2B03h
0x140081b79  mov     [rsp+68h+var_48], rbp
0x140081b7e  xor     r8d, r8d
0x140081b81  mov     r10, [rcx+0DB8h]
0x140081b88  mov     rcx, cs:WdfDriverGlobals
0x140081b8f  mov     rax, r10
0x140081b92  call    _guard_dispatch_icall
0x140081b97  xor     eax, eax
0x140081b99  add     rsp, 48h
0x140081b9d  pop     rdi
0x140081b9e  pop     rsi
0x140081b9f  pop     rbp
0x140081ba0  pop     rbx
0x140081ba1  retn
```
