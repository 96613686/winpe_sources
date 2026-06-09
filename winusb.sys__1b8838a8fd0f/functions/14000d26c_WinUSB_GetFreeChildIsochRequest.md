# WinUSB_GetFreeChildIsochRequest

- ea: `0x14000d26c`
- end: `0x14000d3a5`
- name: `WinUSB_GetFreeChildIsochRequest`
- size: `313`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x14000ea0c`

## callees

- `0x140001020`
- `0x14000d26c`
- `0x140010700`

## import_xrefs

- `ntoskrnl!ExInterlockedRemoveHeadList` at `0x14000d2f2`
- `ntoskrnl!ExInterlockedRemoveHeadList` at `0x14000d2f2`

## pseudocode

```c
PLIST_ENTRY __fastcall WinUSB_GetFreeChildIsochRequest(__int64 a1)
{
  __int64 v2; // rax
  PLIST_ENTRY result; // rax
  __int64 v4; // rbx
  _OWORD v5[2]; // [rsp+30h] [rbp-28h] BYREF

  memset(v5, 0, 24);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      5,
      1,
      107,
      (__int64)WPP_0eec754a616436344c523d073d150c9e_Traceguids);
  v2 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 1616))(
         WdfDriverGlobals,
         a1,
         off_1400150C0);
  result = ExInterlockedRemoveHeadList((PLIST_ENTRY)(v2 + 88), (PKSPIN_LOCK)(v2 + 80));
  if ( result )
  {
    BYTE4(result[4].Blink) = 0;
    *(_QWORD *)((char *)v5 + 12) = 0;
    DWORD1(v5[1]) = 0;
    *(_QWORD *)&v5[0] = 24;
    DWORD2(v5[0]) = 0;
    v4 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS))(WdfFunctions_01015 + 1632))(WdfDriverGlobals);
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _OWORD *))(WdfFunctions_01015 + 1992))(
      WdfDriverGlobals,
      v4,
      v5);
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD, __int64, const char *))(WdfFunctions_01015 + 1640))(
      WdfDriverGlobals,
      v4,
      0,
      2462,
      "onecore\\drivers\\wdm\\usb\\driver\\winusb\\sys\\isoch.c");
    return (PLIST_ENTRY)v4;
  }
  return result;
}

```

## disassembly

```asm
0x14000d26c  mov     [rsp+arg_0], rbx
0x14000d271  push    rdi
0x14000d272  sub     rsp, 50h
0x14000d276  xorps   xmm0, xmm0
0x14000d279  xor     eax, eax
0x14000d27b  movups  [rsp+58h+var_28], xmm0
0x14000d280  mov     [rsp+58h+var_18], rax
0x14000d285  mov     rbx, rcx
0x14000d288  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000d28f  xor     edi, edi
0x14000d291  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000d298  jz      short loc_14000D2C6
0x14000d29a  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d2a1  cmp     [rcx+48h], di
0x14000d2a5  jz      short loc_14000D2C6
0x14000d2a7  mov     rcx, [rcx+40h]
0x14000d2ab  lea     rax, WPP_0eec754a616436344c523d073d150c9e_Traceguids
0x14000d2b2  lea     r9d, [rdi+6Bh]
0x14000d2b6  mov     [rsp+58h+var_38], rax
0x14000d2bb  lea     r8d, [rdi+1]
0x14000d2bf  mov     dl, 5
0x14000d2c1  call    WPP_RECORDER_SF_
0x14000d2c6  mov     rax, cs:WdfFunctions_01015
0x14000d2cd  mov     rdx, rbx
0x14000d2d0  mov     r8, cs:off_1400150C0
0x14000d2d7  mov     rcx, cs:WdfDriverGlobals
0x14000d2de  mov     rax, [rax+650h]
0x14000d2e5  call    _guard_dispatch_icall
0x14000d2ea  lea     rdx, [rax+50h]; Lock
0x14000d2ee  lea     rcx, [rax+58h]; ListHead
0x14000d2f2  call    cs:__imp_ExInterlockedRemoveHeadList
0x14000d2f9  nop     dword ptr [rax+rax+00h]
0x14000d2fe  test    rax, rax
0x14000d301  jz      loc_14000D399
0x14000d307  lea     rdx, [rax-30h]
0x14000d30b  mov     [rdx+7Ch], dil
0x14000d30f  mov     rax, cs:WdfFunctions_01015
0x14000d316  mov     rcx, cs:WdfDriverGlobals
0x14000d31d  mov     qword ptr [rsp+58h+var_28+0Ch], rdi
0x14000d322  mov     dword ptr [rsp+58h+var_18+4], edi
0x14000d326  mov     qword ptr [rsp+58h+var_28], 18h
0x14000d32f  mov     dword ptr [rsp+58h+var_28+8], edi
0x14000d333  mov     rax, [rax+660h]
0x14000d33a  call    _guard_dispatch_icall
0x14000d33f  mov     rcx, cs:WdfFunctions_01015
0x14000d346  lea     r8, [rsp+58h+var_28]
0x14000d34b  mov     rbx, rax
0x14000d34e  mov     rdx, rbx
0x14000d351  mov     rax, [rcx+7C8h]
0x14000d358  mov     rcx, cs:WdfDriverGlobals
0x14000d35f  call    _guard_dispatch_icall
0x14000d364  mov     rcx, cs:WdfFunctions_01015
0x14000d36b  mov     r9d, 99Eh
0x14000d371  xor     r8d, r8d
0x14000d374  mov     rdx, rbx
0x14000d377  mov     rax, [rcx+668h]
0x14000d37e  lea     rcx, aOnecoreDrivers_1; "onecore\\drivers\\wdm\\usb\\driver\\win"...
0x14000d385  mov     [rsp+58h+var_38], rcx
0x14000d38a  mov     rcx, cs:WdfDriverGlobals
0x14000d391  call    _guard_dispatch_icall
0x14000d396  mov     rax, rbx
0x14000d399  mov     rbx, [rsp+58h+arg_0]
0x14000d39e  add     rsp, 50h
0x14000d3a2  pop     rdi
0x14000d3a3  retn
```
