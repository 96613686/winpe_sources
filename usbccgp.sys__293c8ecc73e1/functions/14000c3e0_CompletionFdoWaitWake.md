# CompletionFdoWaitWake

- ea: `0x14000c3e0`
- end: `0x14000c4c8`
- name: `CompletionFdoWaitWake`
- size: `232`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x14000c3e0`
- `0x14000c4d0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000c435`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000c435`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000c45b`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000c45b`
- `ntoskrnl!KeResetEvent` at `0x14000c44a`
- `ntoskrnl!KeResetEvent` at `0x14000c44a`

## pseudocode

```c
__int64 __fastcall CompletionFdoWaitWake(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v4; // rbx
  unsigned int v5; // ebp
  KIRQL v6; // bl
  int v8; // eax

  v4 = a2;
  v5 = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v8 = *(_DWORD *)(a2 + 48);
    LOBYTE(a2) = 4;
    WPP_RECORDER_SF_qqd(
      *(_QWORD *)(a3 + 1368),
      a2,
      3,
      35,
      (__int64)WPP_6d8a51a08a9b3edb1d37cbc5358a5e6d_Traceguids,
      *(_QWORD *)(a3 + 32),
      v4,
      v8);
  }
  if ( !_InterlockedExchange64((volatile __int64 *)(a3 + 376), 0)
    && !_InterlockedExchange((volatile __int32 *)(a3 + 396), 1) )
  {
    v5 = -1073741802;
  }
  if ( *(_BYTE *)(v4 + 65) )
    *(_BYTE *)(*(_QWORD *)(v4 + 184) + 3LL) |= 1u;
  *(_QWORD *)(a3 + 384) = v4;
  v6 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a3 + 344));
  KeResetEvent((PRKEVENT)(a3 + 416));
  KeReleaseSpinLock((PKSPIN_LOCK)(a3 + 344), v6);
  return v5;
}

```

## disassembly

```asm
0x14000c3e0  push    rbx
0x14000c3e2  push    rbp
0x14000c3e3  push    rsi
0x14000c3e4  push    rdi
0x14000c3e5  sub     rsp, 48h
0x14000c3e9  mov     rsi, r8
0x14000c3ec  mov     rbx, rdx
0x14000c3ef  xor     ebp, ebp
0x14000c3f1  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000c3f8  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000c3ff  jnz     loc_14000C48A
0x14000c405  xor     eax, eax
0x14000c407  xchg    rax, [rsi+178h]
0x14000c40e  test    rax, rax
0x14000c411  jz      short loc_14000C473
0x14000c413  cmp     byte ptr [rbx+41h], 0
0x14000c417  jz      short loc_14000C424
0x14000c419  mov     rcx, [rbx+0B8h]
0x14000c420  or      byte ptr [rcx+3], 1
0x14000c424  lea     rdi, [rsi+158h]
0x14000c42b  mov     [rsi+180h], rbx
0x14000c432  mov     rcx, rdi; SpinLock
0x14000c435  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000c43c  nop     dword ptr [rax+rax+00h]
0x14000c441  lea     rcx, [rsi+1A0h]; Event
0x14000c448  mov     bl, al
0x14000c44a  call    cs:__imp_KeResetEvent
0x14000c451  nop     dword ptr [rax+rax+00h]
0x14000c456  mov     dl, bl; NewIrql
0x14000c458  mov     rcx, rdi; SpinLock
0x14000c45b  call    cs:__imp_KeReleaseSpinLock
0x14000c462  nop     dword ptr [rax+rax+00h]
0x14000c467  mov     eax, ebp
0x14000c469  add     rsp, 48h
0x14000c46d  pop     rdi
0x14000c46e  pop     rsi
0x14000c46f  pop     rbp
0x14000c470  pop     rbx
0x14000c471  retn
0x14000c473  mov     eax, 1
0x14000c478  mov     ecx, 0C0000016h
0x14000c47d  xchg    eax, [rsi+18Ch]
0x14000c483  test    eax, eax
0x14000c485  cmovz   ebp, ecx
0x14000c488  jmp     short loc_14000C413
0x14000c48a  mov     eax, [rdx+30h]
0x14000c48d  mov     r9d, 23h ; '#'
0x14000c493  mov     rcx, [rsi+558h]
0x14000c49a  mov     dl, 4
0x14000c49c  mov     [rsp+68h+var_30], eax
0x14000c4a0  mov     rax, [r8+20h]
0x14000c4a4  mov     [rsp+68h+var_38], rbx
0x14000c4a9  lea     r8d, [r9-20h]
0x14000c4ad  mov     [rsp+68h+var_40], rax
0x14000c4b2  lea     rax, WPP_6d8a51a08a9b3edb1d37cbc5358a5e6d_Traceguids
0x14000c4b9  mov     [rsp+68h+var_48], rax
0x14000c4be  call    WPP_RECORDER_SF_qqd
0x14000c4c3  jmp     loc_14000C405
```
