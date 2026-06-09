# HUBPDO_EvtDeviceWdmIrpQueryIdPreprocess

- ea: `0x140017be0`
- end: `0x140017d7c`
- name: `HUBPDO_EvtDeviceWdmIrpQueryIdPreprocess`
- size: `412`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140016160`

## callees

- `0x1400024b8`
- `0x14000a53c`
- `0x140017be0`
- `0x1400336a8`
- `0x140045570`

## import_xrefs

- `ntoskrnl!KeClearEvent` at `0x140017cf6`
- `ntoskrnl!KeClearEvent` at `0x140017cf6`
- `ntoskrnl!KeGetCurrentIrql` at `0x140017c38`
- `ntoskrnl!KeGetCurrentIrql` at `0x140017c38`

## string_xrefs

- `0x140017d16`: `Pre Start Completion`

## pseudocode

```c
__int64 __fastcall HUBPDO_EvtDeviceWdmIrpQueryIdPreprocess(const void *a1, __int64 a2)
{
  _QWORD *v4; // rdi
  __int64 v5; // rax
  __int64 v6; // r8
  int v7; // eax
  int v8; // edx
  __int64 v9; // rax
  __int64 v11; // [rsp+28h] [rbp-40h]

  v4 = *(_QWORD **)((*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, const void *, __int64 *))(WdfFunctions_01015 + 1616))(
                      WdfDriverGlobals,
                      a1,
                      off_14006B1D0)
                  + 24);
  if ( (*((_DWORD *)v4 + 411) & 0x4000) == 0 && !*(_DWORD *)(*(_QWORD *)(a2 + 184) + 8LL) && !KeGetCurrentIrql() )
  {
    v5 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01015 + 1632))(WdfDriverGlobals, *v4);
    LOBYTE(v6) = 1;
    v7 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64, _QWORD, int, const char *))(WdfFunctions_01015 + 3504))(
           WdfDriverGlobals,
           v5,
           v6,
           0,
           4032,
           "onecore\\drivers\\wdm\\usb\\usb3\\hub\\src\\hubpdo.c");
    if ( v7 >= 0 )
    {
      KeClearEvent((PRKEVENT)(v4 + 202));
      HUBSM_AddEvent((__int64)(v4 + 64), 4095);
      HUBMISC_WaitForSignal(v4 + 202, "Pre Start Completion", a1);
      v9 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01015 + 1632))(WdfDriverGlobals, *v4);
      (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD, __int64, const char *))(WdfFunctions_01015 + 3512))(
        WdfDriverGlobals,
        v9,
        0,
        4054,
        "onecore\\drivers\\wdm\\usb\\usb3\\hub\\src\\hubpdo.c");
    }
    else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LODWORD(v11) = v7;
      LOBYTE(v8) = 2;
      WPP_RECORDER_SF_d(
        *(_QWORD *)(v4[1] + 1432LL),
        v8,
        5,
        56,
        (__int64)WPP_8beb7df92ba934db5f6899fb45b5938a_Traceguids,
        v11);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140017be0  push    rbx
0x140017be2  push    rbp
0x140017be3  push    rsi
0x140017be4  push    rdi
0x140017be5  sub     rsp, 48h
0x140017be9  mov     rax, cs:WdfFunctions_01015
0x140017bf0  mov     rbx, rdx
0x140017bf3  mov     r8, cs:off_14006B1D0
0x140017bfa  mov     rsi, rcx
0x140017bfd  mov     rdx, rcx
0x140017c00  mov     rcx, cs:WdfDriverGlobals
0x140017c07  mov     rax, [rax+650h]
0x140017c0e  call    _guard_dispatch_icall
0x140017c13  mov     rdi, [rax+18h]
0x140017c17  test    dword ptr [rdi+66Ch], 4000h
0x140017c21  jnz     loc_140017D70
0x140017c27  mov     rax, [rbx+0B8h]
0x140017c2e  cmp     dword ptr [rax+8], 0
0x140017c32  jnz     loc_140017D70
0x140017c38  call    cs:__imp_KeGetCurrentIrql
0x140017c3f  nop     dword ptr [rax+rax+00h]
0x140017c44  test    al, al
0x140017c46  jnz     loc_140017D70
0x140017c4c  mov     rax, cs:WdfFunctions_01015
0x140017c53  mov     rdx, [rdi]
0x140017c56  mov     rcx, cs:WdfDriverGlobals
0x140017c5d  mov     rax, [rax+660h]
0x140017c64  call    _guard_dispatch_icall
0x140017c69  mov     rcx, cs:WdfFunctions_01015
0x140017c70  lea     rbp, aOnecoreDrivers_1; "onecore\\drivers\\wdm\\usb\\usb3\\hub\\"...
0x140017c77  mov     rdx, rax
0x140017c7a  mov     [rsp+68h+var_40], rbp
0x140017c7f  xor     r9d, r9d
0x140017c82  mov     dword ptr [rsp+68h+var_48], 0FC0h
0x140017c8a  mov     r8b, 1
0x140017c8d  mov     r10, [rcx+0DB0h]
0x140017c94  mov     rcx, cs:WdfDriverGlobals
0x140017c9b  mov     rax, r10
0x140017c9e  call    _guard_dispatch_icall
0x140017ca3  test    eax, eax
0x140017ca5  jns     short loc_140017CEC
0x140017ca7  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140017cae  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140017cb5  jz      loc_140017D70
0x140017cbb  mov     rcx, [rdi+8]
0x140017cbf  mov     r9d, 38h ; '8'
0x140017cc5  mov     dword ptr [rsp+68h+var_40], eax
0x140017cc9  mov     dl, 2
0x140017ccb  lea     rax, WPP_8beb7df92ba934db5f6899fb45b5938a_Traceguids
0x140017cd2  mov     [rsp+68h+var_48], rax
0x140017cd7  mov     rcx, [rcx+598h]
0x140017cde  lea     r8d, [r9-33h]
0x140017ce2  call    WPP_RECORDER_SF_d
0x140017ce7  jmp     loc_140017D70
0x140017cec  lea     rbx, [rdi+650h]
0x140017cf3  mov     rcx, rbx; Event
0x140017cf6  call    cs:__imp_KeClearEvent
0x140017cfd  nop     dword ptr [rax+rax+00h]
0x140017d02  lea     rcx, [rdi+200h]
0x140017d09  mov     edx, 0FFFh
0x140017d0e  call    HUBSM_AddEvent
0x140017d13  mov     r8, rsi
0x140017d16  lea     rdx, aPreStartComple; "Pre Start Completion"
0x140017d1d  mov     rcx, rbx; Object
0x140017d20  call    HUBMISC_WaitForSignal
0x140017d25  mov     rax, cs:WdfFunctions_01015
0x140017d2c  mov     rdx, [rdi]
0x140017d2f  mov     rcx, cs:WdfDriverGlobals
0x140017d36  mov     rax, [rax+660h]
0x140017d3d  call    _guard_dispatch_icall
0x140017d42  mov     rcx, cs:WdfFunctions_01015
0x140017d49  mov     rdx, rax
0x140017d4c  mov     r9d, 0FD6h
0x140017d52  mov     [rsp+68h+var_48], rbp
0x140017d57  xor     r8d, r8d
0x140017d5a  mov     r10, [rcx+0DB8h]
0x140017d61  mov     rcx, cs:WdfDriverGlobals
0x140017d68  mov     rax, r10
0x140017d6b  call    _guard_dispatch_icall
0x140017d70  xor     eax, eax
0x140017d72  add     rsp, 48h
0x140017d76  pop     rdi
0x140017d77  pop     rsi
0x140017d78  pop     rbp
0x140017d79  pop     rbx
0x140017d7a  retn
```
