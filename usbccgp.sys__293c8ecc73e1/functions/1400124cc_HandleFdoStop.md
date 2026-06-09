# HandleFdoStop

- ea: `0x1400124cc`
- end: `0x140012576`
- name: `HandleFdoStop`
- size: `170`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140028800`

## callees

- `0x14000a6ac`
- `0x1400114d8`
- `0x1400124cc`
- `0x14002a0b0`

## import_xrefs

- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140012521`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140012521`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400124fb`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400124fb`

## string_xrefs

- `0x140012548`: `stopEvent (wait for all I/O to complete)`

## pseudocode

```c
__int64 __fastcall HandleFdoStop(__int64 a1, __int64 a2)
{
  char v4; // di
  __int64 result; // rax
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+20h] [rbp-28h] BYREF

  memset(&LockHandle, 0, sizeof(LockHandle));
  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(a1 + 256), &LockHandle);
  if ( *(_DWORD *)(a1 + 12) == 4 )
  {
    v4 = 0;
    *(_DWORD *)(a1 + 12) = 5;
  }
  else
  {
    v4 = 1;
  }
  KeReleaseInStackQueuedSpinLock(&LockHandle);
  if ( !v4 )
  {
    CancelParentWaitWake(a1);
    WaitForSignal((PVOID)(a1 + 288), "stopEvent (wait for all I/O to complete)", *(_QWORD *)(a1 + 1368));
    ParentCloseConfiguration(a1);
  }
  result = 0;
  *(_DWORD *)(a2 + 48) = 0;
  return result;
}

```

## disassembly

```asm
0x1400124cc  mov     r11, rsp
0x1400124cf  mov     [r11+8], rbx
0x1400124d3  mov     [r11+10h], rsi
0x1400124d7  push    rdi
0x1400124d8  sub     rsp, 40h
0x1400124dc  xorps   xmm0, xmm0
0x1400124df  mov     rsi, rdx
0x1400124e2  mov     rbx, rcx
0x1400124e5  lea     rdx, [r11-28h]; LockHandle
0x1400124e9  xor     eax, eax
0x1400124eb  add     rcx, 100h; SpinLock
0x1400124f2  movups  xmmword ptr [rsp+48h+LockHandle.LockQueue.Next], xmm0
0x1400124f7  mov     [r11-18h], rax
0x1400124fb  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140012502  nop     dword ptr [rax+rax+00h]
0x140012507  cmp     dword ptr [rbx+0Ch], 4
0x14001250b  jnz     short loc_140012519
0x14001250d  xor     dil, dil
0x140012510  mov     dword ptr [rbx+0Ch], 5
0x140012517  jmp     short loc_14001251C
0x140012519  mov     dil, 1
0x14001251c  lea     rcx, [rsp+48h+LockHandle]; LockHandle
0x140012521  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140012528  nop     dword ptr [rax+rax+00h]
0x14001252d  test    dil, dil
0x140012530  jnz     short loc_14001255C
0x140012532  mov     rcx, rbx
0x140012535  call    CancelParentWaitWake
0x14001253a  mov     r8, [rbx+558h]
0x140012541  lea     rcx, [rbx+120h]; Object
0x140012548  lea     rdx, aStopeventWaitF; "stopEvent (wait for all I/O to complete"...
0x14001254f  call    WaitForSignal
0x140012554  mov     rcx, rbx
0x140012557  call    ParentCloseConfiguration
0x14001255c  mov     rbx, [rsp+48h+arg_0]
0x140012561  xor     eax, eax
0x140012563  mov     dword ptr [rsi+30h], 0
0x14001256a  mov     rsi, [rsp+48h+arg_8]
0x14001256f  add     rsp, 40h
0x140012573  pop     rdi
0x140012574  retn
```
