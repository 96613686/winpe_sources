# OncRpcWiMgrTimerCreate

- ea: `0x1400102b4`
- end: `0x1400103ca`
- name: `OncRpcWiMgrTimerCreate`
- size: `278`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x140007060`
- `0x140011010`

## callees

- `0x1400101c8`
- `0x1400101f0`
- `0x1400102b4`
- `0x140012950`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x140010340`
- `ntoskrnl!KeInitializeEvent` at `0x140010340`
- `ntoskrnl!KeInitializeTimer` at `0x14001030e`
- `ntoskrnl!KeInitializeTimer` at `0x14001030e`
- `ntoskrnl!KeInitializeDpc` at `0x140010328`
- `ntoskrnl!KeInitializeDpc` at `0x140010328`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400102fe`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400102fe`

## pseudocode

```c
__int64 __fastcall OncRpcWiMgrTimerCreate(__int64 a1, __int64 a2, _QWORD *a3)
{
  int v6; // edi
  _QWORD *v7; // rbx
  _QWORD *v8; // rax
  PVOID DeferredContext; // [rsp+58h] [rbp+20h] BYREF

  DeferredContext = 0;
  v6 = NfsMemMgrStructureAllocateByHandle(qword_14001A450, a2, &DeferredContext);
  if ( v6 >= 0 )
  {
    v7 = DeferredContext;
    KeInitializeSpinLock((PKSPIN_LOCK)DeferredContext + 18);
    KeInitializeTimer((PKTIMER)(v7 + 2));
    KeInitializeDpc((PRKDPC)(v7 + 10), OncRpcWiMgrpTimerDpc, v7);
    KeInitializeEvent((PRKEVENT)(v7 + 22), NotificationEvent, 0);
    v7[20] = a1;
    v7[21] = a2;
    *((_DWORD *)v7 + 38) = 0;
    *((_DWORD *)v7 + 50) = 0;
    NfsLockAcquire(&qword_14001A478);
    v8 = (_QWORD *)qword_14001A470;
    if ( *(__int64 **)qword_14001A470 != &qword_14001A468 )
      __fastfail(3u);
    *v7 = &qword_14001A468;
    v7[1] = v8;
    *v8 = v7;
    qword_14001A470 = (__int64)v7;
    NfsLockRelease(&qword_14001A478);
    *a3 = v7;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1400102b4  mov     rax, rsp
0x1400102b7  mov     [rax+8], rbx
0x1400102bb  mov     [rax+10h], rbp
0x1400102bf  push    rsi
0x1400102c0  push    rdi
0x1400102c1  push    r14
0x1400102c3  sub     rsp, 20h
0x1400102c7  mov     rsi, r8
0x1400102ca  mov     qword ptr [rax+20h], 0
0x1400102d2  mov     r14, rcx
0x1400102d5  lea     r8, [rax+20h]
0x1400102d9  mov     rcx, cs:qword_14001A450
0x1400102e0  mov     rbp, rdx
0x1400102e3  call    NfsMemMgrStructureAllocateByHandle
0x1400102e8  mov     edi, eax
0x1400102ea  test    eax, eax
0x1400102ec  js      loc_1400103B4
0x1400102f2  mov     rbx, [rsp+38h+DeferredContext]
0x1400102f7  lea     rcx, [rbx+90h]; SpinLock
0x1400102fe  call    cs:__imp_KeInitializeSpinLock
0x140010305  nop     dword ptr [rax+rax+00h]
0x14001030a  lea     rcx, [rbx+10h]; Timer
0x14001030e  call    cs:__imp_KeInitializeTimer
0x140010315  nop     dword ptr [rax+rax+00h]
0x14001031a  lea     rcx, [rbx+50h]; Dpc
0x14001031e  mov     r8, rbx; DeferredContext
0x140010321  lea     rdx, OncRpcWiMgrpTimerDpc; DeferredRoutine
0x140010328  call    cs:__imp_KeInitializeDpc
0x14001032f  nop     dword ptr [rax+rax+00h]
0x140010334  lea     rcx, [rbx+0B0h]; Event
0x14001033b  xor     r8d, r8d; State
0x14001033e  xor     edx, edx; Type
0x140010340  call    cs:__imp_KeInitializeEvent
0x140010347  nop     dword ptr [rax+rax+00h]
0x14001034c  mov     [rbx+0A0h], r14
0x140010353  lea     rcx, qword_14001A478
0x14001035a  mov     [rbx+0A8h], rbp
0x140010361  mov     dword ptr [rbx+98h], 0
0x14001036b  mov     dword ptr [rbx+0C8h], 0
0x140010375  call    NfsLockAcquire
0x14001037a  mov     rax, cs:qword_14001A470
0x140010381  lea     rcx, qword_14001A468
0x140010388  cmp     [rax], rcx
0x14001038b  jz      short loc_140010394
0x14001038d  mov     ecx, 3
0x140010392  int     29h; Win8: RtlFailFast(ecx)
0x140010394  mov     [rbx], rcx
0x140010397  lea     rcx, qword_14001A478
0x14001039e  mov     [rbx+8], rax
0x1400103a2  mov     [rax], rbx
0x1400103a5  mov     cs:qword_14001A470, rbx
0x1400103ac  call    NfsLockRelease
0x1400103b1  mov     [rsi], rbx
0x1400103b4  mov     rbx, [rsp+38h+arg_0]
0x1400103b9  mov     eax, edi
0x1400103bb  mov     rbp, [rsp+38h+arg_8]
0x1400103c0  add     rsp, 20h
0x1400103c4  pop     r14
0x1400103c6  pop     rdi
0x1400103c7  pop     rsi
0x1400103c8  retn
```
