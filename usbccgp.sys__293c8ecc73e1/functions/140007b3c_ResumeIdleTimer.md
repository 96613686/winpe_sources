# ResumeIdleTimer

- ea: `0x140007b3c`
- end: `0x140007c2f`
- name: `ResumeIdleTimer`
- size: `243`
- prototype: ``
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x140005fc4`
- `0x140007844`
- `0x14000e360`
- `0x14000ead0`
- `0x14002ced0`

## callees

- `0x14000476c`
- `0x140007b3c`
- `0x1400083c8`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140007b6a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140007b6a`
- `ntoskrnl!KeReleaseSpinLock` at `0x140007bac`
- `ntoskrnl!KeReleaseSpinLock` at `0x140007bac`

## pseudocode

```c
__int64 __fastcall ResumeIdleTimer(__int64 a1)
{
  char v1; // di
  KSPIN_LOCK *v3; // rsi
  KIRQL v4; // al
  _DWORD *v5; // r9
  __int64 i; // r8
  int WorkerIfNeeded; // edi

  v1 = 1;
  if ( *(_BYTE *)(a1 + 1376) == 1 )
    return 3221225473LL;
  v3 = (KSPIN_LOCK *)(a1 + 696);
  v4 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 696));
  v5 = *(_DWORD **)(a1 + 128);
  for ( i = 0; (unsigned int)i < *v5; i = (unsigned int)(i + 1) )
  {
    if ( (*(_DWORD *)(*(_QWORD *)(*(_QWORD *)&v5[2 * i + 2] + 64LL) + 304LL) & 0x17) == 0 )
    {
      v1 = 0;
      break;
    }
  }
  KeReleaseSpinLock(v3, v4);
  if ( !v1 )
    return 0;
  WorkerIfNeeded = AllocateWorkerIfNeeded(a1, ResumeIdleTimerWorker);
  if ( WorkerIfNeeded < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_q(
      *(_QWORD *)(a1 + 1368),
      2u,
      7u,
      0x40u,
      (__int64)WPP_dd1e712d547938a03f2007c63d036cf9_Traceguids,
      *(_QWORD *)(a1 + 32));
  return (unsigned int)WorkerIfNeeded;
}

```

## disassembly

```asm
0x140007b3c  mov     [rsp+arg_0], rbx
0x140007b41  mov     [rsp+arg_8], rsi
0x140007b46  push    rdi
0x140007b47  sub     rsp, 30h
0x140007b4b  mov     edi, 1
0x140007b50  mov     rbx, rcx
0x140007b53  cmp     [rcx+560h], dil
0x140007b5a  jz      loc_140007BE9
0x140007b60  lea     rsi, [rcx+2B8h]
0x140007b67  mov     rcx, rsi; SpinLock
0x140007b6a  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140007b71  nop     dword ptr [rax+rax+00h]
0x140007b76  mov     r9, [rbx+80h]
0x140007b7d  xor     r8d, r8d
0x140007b80  mov     r10b, al
0x140007b83  mov     r11d, [r9]
0x140007b86  cmp     r8d, r11d
0x140007b89  jnb     short loc_140007BA6
0x140007b8b  mov     rdx, [r9+r8*8+8]
0x140007b90  mov     rcx, [rdx+40h]
0x140007b94  mov     eax, [rcx+130h]
0x140007b9a  test    al, 17h
0x140007b9c  jz      short loc_140007BA3
0x140007b9e  add     r8d, edi
0x140007ba1  jmp     short loc_140007B86
0x140007ba3  xor     dil, dil
0x140007ba6  mov     dl, r10b; NewIrql
0x140007ba9  mov     rcx, rsi; SpinLock
0x140007bac  call    cs:__imp_KeReleaseSpinLock
0x140007bb3  nop     dword ptr [rax+rax+00h]
0x140007bb8  test    dil, dil
0x140007bbb  jnz     short loc_140007BD0
0x140007bbd  xor     eax, eax
0x140007bbf  mov     rbx, [rsp+38h+arg_0]
0x140007bc4  mov     rsi, [rsp+38h+arg_8]
0x140007bc9  add     rsp, 30h
0x140007bcd  pop     rdi
0x140007bce  retn
0x140007bd0  lea     rdx, ResumeIdleTimerWorker
0x140007bd7  mov     rcx, rbx
0x140007bda  call    AllocateWorkerIfNeeded
0x140007bdf  mov     edi, eax
0x140007be1  test    eax, eax
0x140007be3  js      short loc_140007BF0
0x140007be5  mov     eax, edi
0x140007be7  jmp     short loc_140007BBF
0x140007be9  mov     eax, 0C0000001h
0x140007bee  jmp     short loc_140007BBF
0x140007bf0  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140007bf7  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140007bfe  jz      short loc_140007BE5
0x140007c00  mov     rcx, [rbx+20h]
0x140007c04  lea     rax, WPP_dd1e712d547938a03f2007c63d036cf9_Traceguids
0x140007c0b  mov     [rsp+38h+var_10], rcx
0x140007c10  mov     r9d, 40h ; '@'
0x140007c16  mov     rcx, [rbx+558h]
0x140007c1d  mov     dl, 2
0x140007c1f  mov     [rsp+38h+var_18], rax
0x140007c24  lea     r8d, [r9-39h]
0x140007c28  call    WPP_RECORDER_SF_q
0x140007c2d  jmp     short loc_140007BE5
```
