# SclRegProcessOnlineRegistry

- ea: `0x1800117e4`
- end: `0x180011884`
- name: `SclRegProcessOnlineRegistry`
- size: `160`
- prototype: `__int64 __fastcall(__int64, __int64 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800065f8`

## callees

- `0x18000a69c`
- `0x18000bc68`
- `0x180010f44`
- `0x1800117e4`

## string_xrefs

- `0x180011830`: `\REGISTRY\MACHINE\SOFTWARE\MICROSOFT\WINDOWS NT\CURRENTVERSION`
- `0x180011840`: `\REGISTRY\MACHINE\SOFTWARE\MICROSOFT\WINDOWS NT\CURRENTVERSION\PROFILELIST`

## pseudocode

```c
__int64 __fastcall SclRegProcessOnlineRegistry(__int64 a1, __int64 *a2)
{
  int v3; // esi
  __int64 v4; // rbx

  v3 = ProcessOnlineRegistryHives(a1, a2);
  if ( v3 >= 0 && (*(_DWORD *)(a1 + 8) & 0x2000) != 0 )
  {
    v4 = a1 + 1152;
    if ( !a1 )
      v4 = 0;
    SclLogTimingEvent(v4, SclEvent_ProcessUserProfiles_Start, "Marking event [&SclEvent_ProcessUserProfiles_Start]");
    v3 = SclRegProcessUserProfileHives(
           a1,
           0,
           (unsigned int)L"\\REGISTRY\\MACHINE\\SOFTWARE\\MICROSOFT\\WINDOWS NT\\CURRENTVERSION\\PROFILELIST",
           (unsigned int)L"\\REGISTRY\\MACHINE\\SOFTWARE\\MICROSOFT\\WINDOWS NT\\CURRENTVERSION",
           0,
           0);
    SclLogTimingEvent(v4, SclEvent_ProcessUserProfiles_Stop, "Marking event [&SclEvent_ProcessUserProfiles_Stop]");
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800117e4  mov     [rsp+arg_0], rbx
0x1800117e9  mov     [rsp+arg_8], rsi
0x1800117ee  push    rdi
0x1800117ef  sub     rsp, 30h
0x1800117f3  mov     rdi, rcx
0x1800117f6  call    ProcessOnlineRegistryHives
0x1800117fb  mov     esi, eax
0x1800117fd  test    eax, eax
0x1800117ff  js      short loc_180011872
0x180011801  test    dword ptr [rdi+8], 2000h
0x180011808  jz      short loc_180011872
0x18001180a  xor     eax, eax
0x18001180c  lea     rbx, [rdi+480h]
0x180011813  test    rdi, rdi
0x180011816  lea     r8, aMarkingEventSc_1; "Marking event [&SclEvent_ProcessUserPro"...
0x18001181d  lea     rdx, SclEvent_ProcessUserProfiles_Start
0x180011824  cmovz   rbx, rax
0x180011828  mov     rcx, rbx
0x18001182b  call    SclLogTimingEvent
0x180011830  lea     r9, aRegistryMachin_11; "\\REGISTRY\\MACHINE\\SOFTWARE\\MICROSOF"...
0x180011837  mov     [rsp+38h+var_10], 0
0x180011840  lea     r8, aRegistryMachin; "\\REGISTRY\\MACHINE\\SOFTWARE\\MICROSOF"...
0x180011847  mov     [rsp+38h+var_18], 0
0x180011850  xor     edx, edx
0x180011852  mov     rcx, rdi
0x180011855  call    SclRegProcessUserProfileHives
0x18001185a  lea     r8, aMarkingEventSc_15; "Marking event [&SclEvent_ProcessUserPro"...
0x180011861  mov     rcx, rbx
0x180011864  lea     rdx, SclEvent_ProcessUserProfiles_Stop
0x18001186b  mov     esi, eax
0x18001186d  call    SclLogTimingEvent
0x180011872  mov     rbx, [rsp+38h+arg_0]
0x180011877  mov     eax, esi
0x180011879  mov     rsi, [rsp+38h+arg_8]
0x18001187e  add     rsp, 30h
0x180011882  pop     rdi
0x180011883  retn
```
