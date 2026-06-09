# InpCompletionSent

- ea: `0x1400086b0`
- end: `0x14000870e`
- name: `InpCompletionSent`
- size: `94`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140002190`
- `0x140005ae0`
- `0x140005ca0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400086db`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400086db`

## pseudocode

```c
__int64 __fastcall InpCompletionSent(__int64 a1)
{
  __int64 v1; // rsi
  unsigned int v2; // edi
  KIRQL v3; // bl
  __int64 v4; // rdx

  v1 = *(_QWORD *)(a1 - 24);
  v2 = *(_DWORD *)(a1 - 24 + 8) - *(_DWORD *)(a1 - 24 + 12);
  InpFreePacket(v1, a1 - 24);
  v3 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v1 + 1088));
  InpPacketFreedLocked(v1, v2);
  LOBYTE(v4) = v3;
  return InpReleaseLockAndPerformWork(v1, v4);
}

```

## disassembly

```asm
0x1400086b0  mov     [rsp+arg_0], rbx
0x1400086b5  mov     [rsp+arg_8], rsi
0x1400086ba  push    rdi
0x1400086bb  sub     rsp, 20h
0x1400086bf  lea     rdx, [rcx-18h]
0x1400086c3  mov     rsi, [rdx]
0x1400086c6  mov     edi, [rdx+8]
0x1400086c9  mov     rcx, rsi
0x1400086cc  sub     edi, [rdx+0Ch]
0x1400086cf  call    InpFreePacket
0x1400086d4  lea     rcx, [rsi+440h]; SpinLock
0x1400086db  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400086e2  nop     dword ptr [rax+rax+00h]
0x1400086e7  mov     edx, edi
0x1400086e9  mov     rcx, rsi
0x1400086ec  mov     bl, al
0x1400086ee  call    InpPacketFreedLocked
0x1400086f3  mov     dl, bl
0x1400086f5  mov     rcx, rsi
0x1400086f8  call    InpReleaseLockAndPerformWork
0x1400086fd  mov     rbx, [rsp+28h+arg_0]
0x140008702  mov     rsi, [rsp+28h+arg_8]
0x140008707  add     rsp, 20h
0x14000870b  pop     rdi
0x14000870c  retn
```
