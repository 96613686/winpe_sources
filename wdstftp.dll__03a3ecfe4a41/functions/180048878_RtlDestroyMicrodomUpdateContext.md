# RtlDestroyMicrodomUpdateContext

- ea: `0x180048878`
- end: `0x1800488e6`
- name: `RtlDestroyMicrodomUpdateContext`
- size: `110`
- prototype: ``
- caller_count: `7`
- callee_count: `4`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180014890`
- `0x180016178`
- `0x180040da0`
- `0x180040e74`
- `0x18004129c`
- `0x180041360`
- `0x180045abc`

## callees

- `0x1800370f4`
- `0x180038834`
- `0x180048878`
- `0x1800497e4`

## import_xrefs

- `ntdll!RtlRaiseStatus` at `0x1800488d0`
- `ntdll!RtlRaiseStatus` at `0x1800488d0`

## string_xrefs

- `0x180048884`: `onecore\base\xml\udom_modify.cpp`
- `0x18004889b`: `Windows::uDom::Rtl::RtlDestroyMicrodomUpdateContext`
- `0x1800488ac`: `RtlIsMicrodomUpdateContextValid(TheContext)`

## pseudocode

```c
__int64 __fastcall RtlDestroyMicrodomUpdateContext(void *a1, __int64 a2)
{
  NTSTATUS NtStatus; // eax
  _QWORD v4[2]; // [rsp+20h] [rbp-28h] BYREF
  int v5; // [rsp+30h] [rbp-18h]
  const char *v6; // [rsp+38h] [rbp-10h]
  int v7; // [rsp+50h] [rbp+8h] BYREF

  if ( !a1 )
  {
    v7 = -1073741811;
    v4[0] = "onecore\\base\\xml\\udom_modify.cpp";
    v4[1] = "Windows::uDom::Rtl::RtlDestroyMicrodomUpdateContext";
    v5 = 1448;
    v6 = "RtlIsMicrodomUpdateContextValid(TheContext)";
    RtlReportErrorOrigination(v4, a2, 3221225485LL);
    NtStatus = Windows::ErrorHandling::Rtl::CBaseNtStatusCarryingFrame<Windows::ErrorHandling::Rtl::CVoidRaiseFrame,void>::GetNtStatus(&v7);
    RtlRaiseStatus(NtStatus);
  }
  return Windows::AutoNewPtr<CMicrodomUpdateContext>::DeleteInstance(a1);
}

```

## disassembly

```asm
0x180048878  mov     r11, rsp
0x18004887b  sub     rsp, 48h
0x18004887f  test    rcx, rcx
0x180048882  jnz     short loc_1800488DD
0x180048884  lea     rax, aOnecoreBaseXml; "onecore\\base\\xml\\udom_modify.cpp"
0x18004888b  mov     [rsp+48h+arg_0], 0C000000Dh
0x180048893  mov     [r11-28h], rax
0x180048897  lea     rcx, [r11-28h]
0x18004889b  lea     rax, aWindowsUdomRtl_3; "Windows::uDom::Rtl::RtlDestroyMicrodomU"...
0x1800488a2  mov     r8d, 0C000000Dh
0x1800488a8  mov     [r11-20h], rax
0x1800488ac  lea     rax, aRtlismicrodomu; "RtlIsMicrodomUpdateContextValid(TheCont"...
0x1800488b3  mov     [rsp+48h+var_18], 5A8h
0x1800488bb  mov     [r11-10h], rax
0x1800488bf  call    RtlReportErrorOrigination
0x1800488c4  lea     rcx, [rsp+48h+arg_0]
0x1800488c9  call    ?GetNtStatus@?$CBaseNtStatusCarryingFrame@UCVoidRaiseFrame@Rtl@ErrorHandling@Windows@@X@Rtl@ErrorHandling@Windows@@QEBAJXZ; Windows::ErrorHandling::Rtl::CBaseNtStatusCarryingFrame<Windows::ErrorHandling::Rtl::CVoidRaiseFrame,void>::GetNtStatus(void)
0x1800488ce  mov     ecx, eax; Status
0x1800488d0  call    cs:__imp_RtlRaiseStatus
0x1800488d7  nop     dword ptr [rax+rax+00h]
0x1800488dc  int     3; Trap to Debugger
0x1800488dd  add     rsp, 48h
0x1800488e1  jmp     ?DeleteInstance@?$AutoNewPtr@VCMicrodomUpdateContext@@@Windows@@SAXPEAVCMicrodomUpdateContext@@@Z; Windows::AutoNewPtr<CMicrodomUpdateContext>::DeleteInstance(CMicrodomUpdateContext *)
```
