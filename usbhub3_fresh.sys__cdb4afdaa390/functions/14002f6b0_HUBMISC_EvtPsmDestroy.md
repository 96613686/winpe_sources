# HUBMISC_EvtPsmDestroy

- ea: `0x14002f6b0`
- end: `0x14002f77f`
- name: `HUBMISC_EvtPsmDestroy`
- size: `207`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x14002f6b0`
- `0x140045570`

## import_xrefs

- `ntoskrnl!ExDeleteTimer` at `0x14002f6f1`
- `ntoskrnl!ExDeleteTimer` at `0x14002f6f1`
- `WppRecorder!imp_WppRecorderLogDelete` at `0x14002f716`
- `WppRecorder!imp_WppRecorderLogDelete` at `0x14002f716`

## pseudocode

```c
__int64 __fastcall HUBMISC_EvtPsmDestroy(__int64 a1)
{
  __int64 v1; // rdx
  _QWORD *v2; // rbx
  __int64 v3; // rcx
  __int64 v4; // rax

  v2 = (_QWORD *)(*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 1616))(
                   WdfDriverGlobals,
                   a1,
                   off_14006B158);
  v3 = v2[164];
  if ( v3 )
  {
    LOBYTE(v1) = 1;
    ExDeleteTimer(v3, v1, 0, 0);
    v2[164] = 0;
  }
  imp_WppRecorderLogDelete(WPP_GLOBAL_Control, v2[179]);
  v4 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01015 + 1632))(WdfDriverGlobals, *v2);
  return (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, const char *, __int64, const char *))(WdfFunctions_01015 + 1648))(
           WdfDriverGlobals,
           v4,
           "PSM Tag",
           7525,
           "onecore\\drivers\\wdm\\usb\\usb3\\hub\\src\\hubmisc.c");
}

```

## disassembly

```asm
0x14002f6b0  push    rbx
0x14002f6b2  sub     rsp, 30h
0x14002f6b6  mov     rax, cs:WdfFunctions_01015
0x14002f6bd  mov     rdx, rcx
0x14002f6c0  mov     r8, cs:off_14006B158
0x14002f6c7  mov     rcx, cs:WdfDriverGlobals
0x14002f6ce  mov     rax, [rax+650h]
0x14002f6d5  call    _guard_dispatch_icall
0x14002f6da  mov     rbx, rax
0x14002f6dd  mov     rcx, [rax+520h]
0x14002f6e4  test    rcx, rcx
0x14002f6e7  jz      short loc_14002F708
0x14002f6e9  xor     r9d, r9d
0x14002f6ec  xor     r8d, r8d
0x14002f6ef  mov     dl, 1
0x14002f6f1  call    cs:__imp_ExDeleteTimer
0x14002f6f8  nop     dword ptr [rax+rax+00h]
0x14002f6fd  mov     qword ptr [rbx+520h], 0
0x14002f708  mov     rdx, [rbx+598h]
0x14002f70f  mov     rcx, cs:WPP_GLOBAL_Control
0x14002f716  call    cs:__imp_imp_WppRecorderLogDelete
0x14002f71d  nop     dword ptr [rax+rax+00h]
0x14002f722  mov     rax, cs:WdfFunctions_01015
0x14002f729  mov     rdx, [rbx]
0x14002f72c  mov     rcx, cs:WdfDriverGlobals
0x14002f733  mov     rax, [rax+660h]
0x14002f73a  call    _guard_dispatch_icall
0x14002f73f  mov     rcx, cs:WdfFunctions_01015
0x14002f746  lea     r8, PsmTag; "PSM Tag"
0x14002f74d  mov     rdx, rax
0x14002f750  mov     r9d, 1D65h
0x14002f756  mov     r10, [rcx+670h]
0x14002f75d  lea     rcx, aOnecoreDrivers_4; "onecore\\drivers\\wdm\\usb\\usb3\\hub\\"...
0x14002f764  mov     [rsp+38h+var_18], rcx
0x14002f769  mov     rax, r10
0x14002f76c  mov     rcx, cs:WdfDriverGlobals
0x14002f773  call    _guard_dispatch_icall
0x14002f778  add     rsp, 30h
0x14002f77c  pop     rbx
0x14002f77d  retn
```
