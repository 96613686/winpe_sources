# OncRpcWiMgrpTimerWorkerThreadCallback

- ea: `0x1400105d0`
- end: `0x1400106b9`
- name: `OncRpcWiMgrpTimerWorkerThreadCallback`
- size: `233`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x1400059a4`
- `0x1400105d0`
- `0x140012a60`
- `0x140015680`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14001060f`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14001060f`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140010692`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140010692`
- `ntoskrnl!KeSetEvent` at `0x140010643`
- `ntoskrnl!KeSetEvent` at `0x140010643`

## pseudocode

```c
__int64 __fastcall OncRpcWiMgrpTimerWorkerThreadCallback(__int64 a1)
{
  __int64 v1; // rbx
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+30h] [rbp-28h] BYREF

  v1 = *(_QWORD *)(a1 + 48);
  memset(&LockHandle, 0, sizeof(LockHandle));
  (*(void (__fastcall **)(_QWORD))(v1 + 160))(*(_QWORD *)(v1 + 168));
  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v1 + 144), &LockHandle);
  --*(_DWORD *)(v1 + 152);
  if ( (*(_DWORD *)(v1 + 200) & 1) != 0 && !*(_DWORD *)(v1 + 152) )
    KeSetEvent((PRKEVENT)(v1 + 176), 2, 0);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
    WPP_SF_qd(
      WPP_GLOBAL_Control->AttachedDevice,
      10,
      WPP_c7b79a1d0d4b33f99a0c8fcd19876b42_Traceguids,
      v1,
      *(_DWORD *)(v1 + 152));
  KeReleaseInStackQueuedSpinLock(&LockHandle);
  return NfsMemMgrStructureFreeByHandle(qword_14001A458, a1);
}

```

## disassembly

```asm
0x1400105d0  mov     [rsp+arg_0], rbx
0x1400105d5  push    rdi
0x1400105d6  sub     rsp, 50h
0x1400105da  mov     rbx, [rcx+30h]
0x1400105de  xor     eax, eax
0x1400105e0  mov     qword ptr [rsp+58h+LockHandle.OldIrql], rax
0x1400105e5  xorps   xmm0, xmm0
0x1400105e8  movups  xmmword ptr [rsp+58h+LockHandle.LockQueue.Next], xmm0
0x1400105ed  mov     rdi, rcx
0x1400105f0  mov     rax, [rbx+0A0h]
0x1400105f7  mov     rcx, [rbx+0A8h]
0x1400105fe  call    _guard_dispatch_icall
0x140010603  lea     rcx, [rbx+90h]; SpinLock
0x14001060a  lea     rdx, [rsp+58h+LockHandle]; LockHandle
0x14001060f  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140010616  nop     dword ptr [rax+rax+00h]
0x14001061b  dec     dword ptr [rbx+98h]
0x140010621  mov     eax, [rbx+0C8h]
0x140010627  mov     ecx, [rbx+98h]
0x14001062d  test    al, 1
0x14001062f  jz      short loc_14001064F
0x140010631  test    ecx, ecx
0x140010633  jnz     short loc_14001064F
0x140010635  xor     r8d, r8d; Wait
0x140010638  lea     rcx, [rbx+0B0h]; Event
0x14001063f  lea     edx, [r8+2]; Increment
0x140010643  call    cs:__imp_KeSetEvent
0x14001064a  nop     dword ptr [rax+rax+00h]
0x14001064f  mov     rcx, cs:WPP_GLOBAL_Control
0x140010656  lea     rax, WPP_GLOBAL_Control
0x14001065d  cmp     rcx, rax
0x140010660  jz      short loc_14001068D
0x140010662  test    dword ptr [rcx+2Ch], 200h
0x140010669  jz      short loc_14001068D
0x14001066b  mov     eax, [rbx+98h]
0x140010671  lea     r8, WPP_c7b79a1d0d4b33f99a0c8fcd19876b42_Traceguids
0x140010678  mov     rcx, [rcx+18h]
0x14001067c  mov     edx, 0Ah
0x140010681  mov     r9, rbx
0x140010684  mov     [rsp+58h+var_38], eax
0x140010688  call    WPP_SF_qd
0x14001068d  lea     rcx, [rsp+58h+LockHandle]; LockHandle
0x140010692  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140010699  nop     dword ptr [rax+rax+00h]
0x14001069e  mov     rcx, cs:qword_14001A458
0x1400106a5  mov     rdx, rdi
0x1400106a8  call    NfsMemMgrStructureFreeByHandle
0x1400106ad  mov     rbx, [rsp+58h+arg_0]
0x1400106b2  add     rsp, 50h
0x1400106b6  pop     rdi
0x1400106b7  retn
```
