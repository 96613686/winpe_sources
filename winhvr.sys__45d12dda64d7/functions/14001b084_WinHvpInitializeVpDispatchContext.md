# WinHvpInitializeVpDispatchContext

- ea: `0x14001b084`
- end: `0x14001b194`
- name: `WinHvpInitializeVpDispatchContext`
- size: `272`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1400226bc`

## callees

- `0x140004870`
- `0x140007d0c`
- `0x14001b084`

## import_xrefs

- `ntoskrnl!KeInitializeSpinLock` at `0x14001b09c`
- `ntoskrnl!KeInitializeSpinLock` at `0x14001b09c`
- `ntoskrnl!KeInitializeEvent` at `0x14001b0c6`
- `ntoskrnl!KeInitializeEvent` at `0x14001b0e5`
- `ntoskrnl!KeInitializeEvent` at `0x14001b0c6`
- `ntoskrnl!KeInitializeEvent` at `0x14001b0e5`
- `ntoskrnl!ExInitializeRundownProtection` at `0x14001b0fb`
- `ntoskrnl!ExInitializeRundownProtection` at `0x14001b0fb`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x14001b10a`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x14001b10a`
- `ntoskrnl!ExRundownCompleted` at `0x14001b119`
- `ntoskrnl!ExRundownCompleted` at `0x14001b119`
- `ntoskrnl!ExAllocateTimer` at `0x14001b16d`
- `ntoskrnl!ExAllocateTimer` at `0x14001b16d`

## pseudocode

```c
__int64 __fastcall WinHvpInitializeVpDispatchContext(__int64 a1)
{
  int PartitionSchedulingProperties; // ebx
  __int64 Timer; // rax

  *(_QWORD *)(a1 + 24) = 0;
  KeInitializeSpinLock((PKSPIN_LOCK)(a1 + 40));
  *(_DWORD *)(a1 + 48) = 2;
  *(_DWORD *)(a1 + 32) = 1;
  KeInitializeEvent((PRKEVENT)(a1 + 128), SynchronizationEvent, 0);
  *(_QWORD *)(a1 + 152) = a1 + 128;
  KeInitializeEvent((PRKEVENT)(a1 + 160), SynchronizationEvent, 0);
  ExInitializeRundownProtection((PEX_RUNDOWN_REF)(a1 + 184));
  ExWaitForRundownProtectionRelease((PEX_RUNDOWN_REF)(a1 + 184));
  ExRundownCompleted((PEX_RUNDOWN_REF)(a1 + 184));
  PartitionSchedulingProperties = WinHvpGetPartitionSchedulingProperties(*(_QWORD *)a1, a1 + 36, a1 + 38);
  if ( PartitionSchedulingProperties >= 0 )
  {
    PartitionSchedulingProperties = WinHvpReferencePartitionData(*(_QWORD *)a1, a1 + 208);
    if ( PartitionSchedulingProperties >= 0 )
    {
      if ( *(_BYTE *)(a1 + 36) )
      {
        *(_QWORD *)(a1 + 104) = -1;
        Timer = ExAllocateTimer(WinHvpVpDispatchDeadlineTimerCallback, a1 + 24, 4);
        *(_QWORD *)(a1 + 72) = Timer;
        if ( !Timer )
          return (unsigned int)-1073741670;
      }
    }
  }
  return (unsigned int)PartitionSchedulingProperties;
}

```

## disassembly

```asm
0x14001b084  push    rbx
0x14001b086  push    rbp
0x14001b087  push    rsi
0x14001b088  push    rdi
0x14001b089  sub     rsp, 28h
0x14001b08d  mov     rsi, rcx
0x14001b090  mov     qword ptr [rcx+18h], 0
0x14001b098  add     rcx, 28h ; '('; SpinLock
0x14001b09c  call    cs:__imp_KeInitializeSpinLock
0x14001b0a3  nop     dword ptr [rax+rax+00h]
0x14001b0a8  mov     ebp, 1
0x14001b0ad  mov     dword ptr [rsi+30h], 2
0x14001b0b4  lea     rbx, [rsi+80h]
0x14001b0bb  mov     [rsi+20h], ebp
0x14001b0be  mov     edx, ebp; Type
0x14001b0c0  mov     rcx, rbx; Event
0x14001b0c3  xor     r8d, r8d; State
0x14001b0c6  call    cs:__imp_KeInitializeEvent
0x14001b0cd  nop     dword ptr [rax+rax+00h]
0x14001b0d2  lea     rcx, [rsi+0A0h]; Event
0x14001b0d9  mov     [rsi+98h], rbx
0x14001b0e0  xor     r8d, r8d; State
0x14001b0e3  mov     edx, ebp; Type
0x14001b0e5  call    cs:__imp_KeInitializeEvent
0x14001b0ec  nop     dword ptr [rax+rax+00h]
0x14001b0f1  lea     rbx, [rsi+0B8h]
0x14001b0f8  mov     rcx, rbx; RunRef
0x14001b0fb  call    cs:__imp_ExInitializeRundownProtection
0x14001b102  nop     dword ptr [rax+rax+00h]
0x14001b107  mov     rcx, rbx; RunRef
0x14001b10a  call    cs:__imp_ExWaitForRundownProtectionRelease
0x14001b111  nop     dword ptr [rax+rax+00h]
0x14001b116  mov     rcx, rbx; RunRef
0x14001b119  call    cs:__imp_ExRundownCompleted
0x14001b120  nop     dword ptr [rax+rax+00h]
0x14001b125  mov     rcx, [rsi]
0x14001b128  lea     r8, [rsi+26h]
0x14001b12c  lea     rdx, [rsi+24h]
0x14001b130  call    WinHvpGetPartitionSchedulingProperties
0x14001b135  mov     ebx, eax
0x14001b137  test    eax, eax
0x14001b139  js      short loc_14001B188
0x14001b13b  mov     rcx, [rsi]
0x14001b13e  lea     rdx, [rsi+0D0h]
0x14001b145  call    WinHvpReferencePartitionData
0x14001b14a  mov     ebx, eax
0x14001b14c  test    eax, eax
0x14001b14e  js      short loc_14001B188
0x14001b150  cmp     byte ptr [rsi+24h], 0
0x14001b154  jz      short loc_14001B188
0x14001b156  lea     r8d, [rbp+3]
0x14001b15a  mov     qword ptr [rsi+68h], 0FFFFFFFFFFFFFFFFh
0x14001b162  lea     rdx, [rsi+18h]
0x14001b166  lea     rcx, WinHvpVpDispatchDeadlineTimerCallback
0x14001b16d  call    cs:__imp_ExAllocateTimer
0x14001b174  nop     dword ptr [rax+rax+00h]
0x14001b179  test    rax, rax
0x14001b17c  mov     [rsi+48h], rax
0x14001b180  mov     ecx, 0C000009Ah
0x14001b185  cmovz   ebx, ecx
0x14001b188  mov     eax, ebx
0x14001b18a  add     rsp, 28h
0x14001b18e  pop     rdi
0x14001b18f  pop     rsi
0x14001b190  pop     rbp
0x14001b191  pop     rbx
0x14001b192  retn
```
