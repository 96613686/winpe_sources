# CallbackFdoDeviceSetD0

- ea: `0x1400046c0`
- end: `0x140004763`
- name: `CallbackFdoDeviceSetD0`
- size: `163`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1400046c0`
- `0x14000476c`
- `0x1400054a0`
- `0x140005bb0`
- `0x1400083c8`

## import_xrefs

- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14000471e`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14000471e`

## pseudocode

```c
void __fastcall CallbackFdoDeviceSetD0(__int64 a1)
{
  __int64 v1; // rbx

  v1 = *(_QWORD *)(a1 + 64) + 8LL;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_q(
      *(_QWORD *)(*(_QWORD *)(a1 + 64) + 1376LL),
      4,
      3,
      36,
      (__int64)WPP_6d8a51a08a9b3edb1d37cbc5358a5e6d_Traceguids,
      *(_QWORD *)(*(_QWORD *)(a1 + 64) + 40LL));
  if ( (int)AllocateWorkerIfNeeded(v1, UnblockWorkBlockedOnPendingParentD0) < 0 )
    UnblockWorkBlockedOnPendingParentD0((char *)v1);
  UsbcReleaseRemoveLock(v1, gSetD0Tag);
  IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(v1 + 200), gSetD0Tag, 0x20u);
}

```

## disassembly

```asm
0x1400046c0  push    rbx
0x1400046c2  sub     rsp, 30h
0x1400046c6  mov     rbx, [rcx+40h]
0x1400046ca  add     rbx, 8
0x1400046ce  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400046d5  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400046dc  jnz     short loc_140004731
0x1400046de  lea     rdx, UnblockWorkBlockedOnPendingParentD0
0x1400046e5  mov     rcx, rbx
0x1400046e8  call    AllocateWorkerIfNeeded
0x1400046ed  test    eax, eax
0x1400046ef  jns     short loc_1400046FB
0x1400046f1  xor     edx, edx
0x1400046f3  mov     rcx, rbx
0x1400046f6  call    UnblockWorkBlockedOnPendingParentD0
0x1400046fb  lea     rdx, gSetD0Tag; "T0DS"
0x140004702  mov     rcx, rbx
0x140004705  call    UsbcReleaseRemoveLock
0x14000470a  lea     rcx, [rbx+0C8h]; RemoveLock
0x140004711  mov     r8d, 20h ; ' '; RemlockSize
0x140004717  lea     rdx, gSetD0Tag; "T0DS"
0x14000471e  call    cs:__imp_IoReleaseRemoveLockEx
0x140004725  nop     dword ptr [rax+rax+00h]
0x14000472a  add     rsp, 30h
0x14000472e  pop     rbx
0x14000472f  retn
0x140004731  mov     rax, [rbx+20h]
0x140004735  mov     r9d, 24h ; '$'
0x14000473b  mov     rcx, [rbx+558h]
0x140004742  mov     dl, 4
0x140004744  mov     [rsp+38h+var_10], rax
0x140004749  lea     rax, WPP_6d8a51a08a9b3edb1d37cbc5358a5e6d_Traceguids
0x140004750  mov     [rsp+38h+var_18], rax
0x140004755  lea     r8d, [r9-21h]
0x140004759  call    WPP_RECORDER_SF_q
0x14000475e  jmp     loc_1400046DE
```
