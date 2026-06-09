# WinUSB_FreeChildIsochRequest

- ea: `0x14000ced8`
- end: `0x14000cfc8`
- name: `WinUSB_FreeChildIsochRequest`
- size: `240`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x14000c500`
- `0x14000ea0c`

## callees

- `0x140001020`
- `0x14000ced8`
- `0x140010700`

## import_xrefs

- `ntoskrnl!ExInterlockedInsertHeadList` at `0x14000cf7e`
- `ntoskrnl!ExInterlockedInsertHeadList` at `0x14000cf7e`

## pseudocode

```c
__int64 __fastcall WinUSB_FreeChildIsochRequest(__int64 a1, __int64 a2)
{
  __int64 v4; // rbx
  struct _LIST_ENTRY *v5; // rax

  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    WPP_RECORDER_SF_(
      (__int64)WPP_GLOBAL_Control->DeviceExtension,
      5u,
      1u,
      0x6Cu,
      (__int64)WPP_0eec754a616436344c523d073d150c9e_Traceguids);
  v4 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 1616))(
         WdfDriverGlobals,
         a1,
         off_1400150C0);
  v5 = (struct _LIST_ENTRY *)(*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015
                                                                                                + 1616))(
                               WdfDriverGlobals,
                               a2,
                               off_140015068);
  ExInterlockedInsertHeadList((PLIST_ENTRY)(v4 + 88), v5 + 3, (PKSPIN_LOCK)(v4 + 80));
  return (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD, __int64, const char *))(WdfFunctions_01015
                                                                                                + 1648))(
           WdfDriverGlobals,
           a2,
           0,
           2510,
           "onecore\\drivers\\wdm\\usb\\driver\\winusb\\sys\\isoch.c");
}

```

## disassembly

```asm
0x14000ced8  mov     [rsp+arg_0], rbx
0x14000cedd  push    rdi
0x14000cede  sub     rsp, 30h
0x14000cee2  mov     rdi, rdx
0x14000cee5  mov     rbx, rcx
0x14000cee8  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000ceef  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000cef6  jz      short loc_14000CF27
0x14000cef8  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ceff  cmp     word ptr [rcx+48h], 0
0x14000cf04  jz      short loc_14000CF27
0x14000cf06  mov     rcx, [rcx+40h]
0x14000cf0a  lea     rax, WPP_0eec754a616436344c523d073d150c9e_Traceguids
0x14000cf11  mov     r9d, 6Ch ; 'l'
0x14000cf17  mov     [rsp+38h+var_18], rax
0x14000cf1c  mov     dl, 5
0x14000cf1e  lea     r8d, [r9-6Bh]
0x14000cf22  call    WPP_RECORDER_SF_
0x14000cf27  mov     rax, cs:WdfFunctions_01015
0x14000cf2e  mov     rdx, rbx
0x14000cf31  mov     r8, cs:off_1400150C0
0x14000cf38  mov     rcx, cs:WdfDriverGlobals
0x14000cf3f  mov     rax, [rax+650h]
0x14000cf46  call    _guard_dispatch_icall
0x14000cf4b  mov     rcx, cs:WdfFunctions_01015
0x14000cf52  mov     rbx, rax
0x14000cf55  mov     r8, cs:off_140015068
0x14000cf5c  mov     rdx, rdi
0x14000cf5f  mov     rax, [rcx+650h]
0x14000cf66  mov     rcx, cs:WdfDriverGlobals
0x14000cf6d  call    _guard_dispatch_icall
0x14000cf72  lea     r8, [rbx+50h]; Lock
0x14000cf76  lea     rcx, [rbx+58h]; ListHead
0x14000cf7a  lea     rdx, [rax+30h]; ListEntry
0x14000cf7e  call    cs:__imp_ExInterlockedInsertHeadList
0x14000cf85  nop     dword ptr [rax+rax+00h]
0x14000cf8a  mov     rax, cs:WdfFunctions_01015
0x14000cf91  lea     rcx, aOnecoreDrivers_1; "onecore\\drivers\\wdm\\usb\\driver\\win"...
0x14000cf98  mov     [rsp+38h+var_18], rcx
0x14000cf9d  mov     r9d, 9CEh
0x14000cfa3  mov     rcx, cs:WdfDriverGlobals
0x14000cfaa  xor     r8d, r8d
0x14000cfad  mov     rdx, rdi
0x14000cfb0  mov     rax, [rax+670h]
0x14000cfb7  call    _guard_dispatch_icall
0x14000cfbc  mov     rbx, [rsp+38h+arg_0]
0x14000cfc1  add     rsp, 30h
0x14000cfc5  pop     rdi
0x14000cfc6  retn
```
