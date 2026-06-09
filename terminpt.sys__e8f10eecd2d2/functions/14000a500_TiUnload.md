# TiUnload

- ea: `0x14000a500`
- end: `0x14000a64b`
- name: `TiUnload`
- size: `331`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, loader_planting`

## callers

- `0x14000c1b8`

## callees

- `0x14000173c`
- `0x14000a500`
- `0x14000a654`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000a5bf`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a5bf`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x14000a552`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x14000a552`
- `ntoskrnl!IoDeleteDevice` at `0x14000a56a`
- `ntoskrnl!IoDeleteDevice` at `0x14000a56a`

## pseudocode

```c
void __fastcall TiUnload(__int64 a1, int a2, int a3)
{
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_s(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      a3,
      15,
      (__int64)WPP_a22c8264ce0a30878b50f65ec3447f16_Traceguids);
  if ( LOWORD(WPP_MAIN_CB.ActiveThreadCount) )
    IoDeleteSymbolicLink((PUNICODE_STRING)&WPP_MAIN_CB.ActiveThreadCount);
  if ( WPP_MAIN_CB.Dpc.SystemArgument2 )
  {
    IoDeleteDevice((PDEVICE_OBJECT)WPP_MAIN_CB.Dpc.SystemArgument2);
    WPP_MAIN_CB.Dpc.SystemArgument2 = 0;
  }
  if ( LOBYTE(WPP_MAIN_CB.Dpc.DpcData) )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_s(
        WPP_GLOBAL_Control->DeviceExtension,
        a2,
        a3,
        47,
        (__int64)WPP_d8869bceb4743096b6344322fa7eafaf_Traceguids);
    if ( WPP_MAIN_CB.Queue.Wcb.DeviceRoutine )
    {
      ExFreePoolWithTag(WPP_MAIN_CB.Queue.Wcb.DeviceRoutine, 0);
      WPP_MAIN_CB.Queue.Wcb.DeviceRoutine = 0;
      WPP_MAIN_CB.Queue.Wcb.WaitQueueEntry.SortKey = 0;
    }
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_s(
        WPP_GLOBAL_Control->DeviceExtension,
        a2,
        a3,
        48,
        (__int64)WPP_d8869bceb4743096b6344322fa7eafaf_Traceguids);
    LOBYTE(WPP_MAIN_CB.Dpc.DpcData) = 0;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_s(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      a3,
      16,
      (__int64)WPP_a22c8264ce0a30878b50f65ec3447f16_Traceguids);
  if ( BYTE1(WPP_MAIN_CB.Dpc.DpcData) )
  {
    WppCleanupKm(a1);
    BYTE1(WPP_MAIN_CB.Dpc.DpcData) = 0;
  }
}

```

## disassembly

```asm
0x14000a500  push    rbx
0x14000a502  push    rbp
0x14000a503  push    rsi
0x14000a504  push    rdi
0x14000a505  push    r14
0x14000a507  sub     rsp, 30h
0x14000a50b  mov     rbx, rcx
0x14000a50e  lea     rsi, WPP_RECORDER_INITIALIZED
0x14000a515  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14000a51c  lea     r14, WPP_a22c8264ce0a30878b50f65ec3447f16_Traceguids
0x14000a523  jz      short loc_14000A540
0x14000a525  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a52c  mov     r9d, 0Fh
0x14000a532  mov     [rsp+58h+var_38], r14
0x14000a537  mov     rcx, [rcx+40h]
0x14000a53b  call    WPP_RECORDER_SF_s
0x14000a540  xor     edi, edi
0x14000a542  cmp     word ptr cs:WPP_MAIN_CB.ActiveThreadCount, di
0x14000a549  jz      short loc_14000A55E
0x14000a54b  lea     rcx, WPP_MAIN_CB.ActiveThreadCount; SymbolicLinkName
0x14000a552  call    cs:__imp_IoDeleteSymbolicLink
0x14000a559  nop     dword ptr [rax+rax+00h]
0x14000a55e  mov     rcx, cs:WPP_MAIN_CB.Dpc.SystemArgument2; DeviceObject
0x14000a565  test    rcx, rcx
0x14000a568  jz      short loc_14000A57D
0x14000a56a  call    cs:__imp_IoDeleteDevice
0x14000a571  nop     dword ptr [rax+rax+00h]
0x14000a576  mov     cs:WPP_MAIN_CB.Dpc.SystemArgument2, rdi
0x14000a57d  cmp     byte ptr cs:WPP_MAIN_CB.Dpc.DpcData, dil
0x14000a584  jz      short loc_14000A603
0x14000a586  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14000a58d  lea     rbp, WPP_d8869bceb4743096b6344322fa7eafaf_Traceguids
0x14000a594  jz      short loc_14000A5B1
0x14000a596  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a59d  mov     r9d, 2Fh ; '/'
0x14000a5a3  mov     [rsp+58h+var_38], rbp
0x14000a5a8  mov     rcx, [rcx+40h]
0x14000a5ac  call    WPP_RECORDER_SF_s
0x14000a5b1  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+18h; P
0x14000a5b8  test    rcx, rcx
0x14000a5bb  jz      short loc_14000A5D8
0x14000a5bd  xor     edx, edx; Tag
0x14000a5bf  call    cs:__imp_ExFreePoolWithTag
0x14000a5c6  nop     dword ptr [rax+rax+00h]
0x14000a5cb  mov     qword ptr cs:WPP_MAIN_CB.Queue+18h, rdi
0x14000a5d2  mov     dword ptr cs:WPP_MAIN_CB.Queue+10h, edi
0x14000a5d8  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14000a5df  jz      short loc_14000A5FC
0x14000a5e1  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a5e8  mov     r9d, 30h ; '0'
0x14000a5ee  mov     [rsp+58h+var_38], rbp
0x14000a5f3  mov     rcx, [rcx+40h]
0x14000a5f7  call    WPP_RECORDER_SF_s
0x14000a5fc  mov     byte ptr cs:WPP_MAIN_CB.Dpc.DpcData, dil
0x14000a603  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14000a60a  jz      short loc_14000A627
0x14000a60c  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a613  mov     r9d, 10h
0x14000a619  mov     [rsp+58h+var_38], r14
0x14000a61e  mov     rcx, [rcx+40h]
0x14000a622  call    WPP_RECORDER_SF_s
0x14000a627  cmp     byte ptr cs:WPP_MAIN_CB.Dpc.DpcData+1, dil
0x14000a62e  jz      short loc_14000A63F
0x14000a630  mov     rcx, rbx
0x14000a633  call    WppCleanupKm
0x14000a638  mov     byte ptr cs:WPP_MAIN_CB.Dpc.DpcData+1, dil
0x14000a63f  add     rsp, 30h
0x14000a643  pop     r14
0x14000a645  pop     rdi
0x14000a646  pop     rsi
0x14000a647  pop     rbp
0x14000a648  pop     rbx
0x14000a649  retn
```
