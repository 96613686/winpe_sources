# DbgTdxReferenceTransport

- ea: `0x14000c9cc`
- end: `0x14000ca92`
- name: `DbgTdxReferenceTransport`
- size: `198`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x14000bab0`
- `0x14000cc70`
- `0x140010af0`
- `0x140017dcc`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000c9f1`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000c9f1`
- `ntoskrnl!RtlGetCallersAddress` at `0x14000ca39`
- `ntoskrnl!RtlGetCallersAddress` at `0x14000ca39`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000ca6d`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000ca6d`

## pseudocode

```c
void __fastcall DbgTdxReferenceTransport(__int64 a1, __int64 a2, int a3)
{
  KSPIN_LOCK *v3; // rbp
  KIRQL v7; // al
  int v8; // r8d
  __int64 v9; // r9
  KIRQL v10; // si
  PVOID CallersAddress; // [rsp+40h] [rbp+8h] BYREF

  v3 = (KSPIN_LOCK *)(a1 + 216);
  v7 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 216));
  v8 = *(_DWORD *)(a1 + 24);
  v9 = *(unsigned int *)(a1 + 1184) + 7LL;
  CallersAddress = 0;
  v9 *= 32;
  v10 = v7;
  *(_DWORD *)(v9 + a1 + 24) = v8 + 1;
  *(_QWORD *)(v9 + a1) = a2;
  *(_DWORD *)(v9 + a1 + 8) = a3;
  RtlGetCallersAddress(&CallersAddress, (PVOID *)(v9 + a1 + 16));
  *(_DWORD *)(a1 + 1184) = (*(_DWORD *)(a1 + 1184) + 1) % 0x1Eu;
  KeReleaseSpinLock(v3, v10);
  _InterlockedIncrement((volatile signed __int32 *)(a1 + 24));
}

```

## disassembly

```asm
0x14000c9cc  mov     [rsp+arg_8], rbx
0x14000c9d1  mov     [rsp+arg_10], rbp
0x14000c9d6  push    rsi
0x14000c9d7  push    rdi
0x14000c9d8  push    r14
0x14000c9da  sub     rsp, 20h
0x14000c9de  lea     rbp, [rcx+0D8h]
0x14000c9e5  mov     r14, rcx
0x14000c9e8  mov     rcx, rbp; SpinLock
0x14000c9eb  mov     edi, r8d
0x14000c9ee  mov     rbx, rdx
0x14000c9f1  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000c9f8  nop     dword ptr [rax+rax+00h]
0x14000c9fd  mov     r8d, [r14+18h]
0x14000ca01  lea     rdx, [r14+10h]
0x14000ca05  mov     r9d, [r14+4A0h]
0x14000ca0c  lea     rcx, [rsp+38h+CallersAddress]; CallersAddress
0x14000ca11  add     r9, 7
0x14000ca15  mov     [rsp+38h+CallersAddress], 0
0x14000ca1e  shl     r9, 5
0x14000ca22  mov     sil, al
0x14000ca25  inc     r8d
0x14000ca28  add     rdx, r9; CallersCaller
0x14000ca2b  mov     [r9+r14+18h], r8d
0x14000ca30  mov     [r9+r14], rbx
0x14000ca34  mov     [r9+r14+8], edi
0x14000ca39  call    cs:__imp_RtlGetCallersAddress
0x14000ca40  nop     dword ptr [rax+rax+00h]
0x14000ca45  mov     r8d, [r14+4A0h]
0x14000ca4c  mov     eax, 88888889h
0x14000ca51  inc     r8d
0x14000ca54  mov     rcx, rbp; SpinLock
0x14000ca57  mul     r8d
0x14000ca5a  shr     edx, 4
0x14000ca5d  imul    eax, edx, 1Eh
0x14000ca60  mov     dl, sil; NewIrql
0x14000ca63  sub     r8d, eax
0x14000ca66  mov     [r14+4A0h], r8d
0x14000ca6d  call    cs:__imp_KeReleaseSpinLock
0x14000ca74  nop     dword ptr [rax+rax+00h]
0x14000ca79  lock inc dword ptr [r14+18h]
0x14000ca7e  mov     rbx, [rsp+38h+arg_8]
0x14000ca83  mov     rbp, [rsp+38h+arg_10]
0x14000ca88  add     rsp, 20h
0x14000ca8c  pop     r14
0x14000ca8e  pop     rdi
0x14000ca8f  pop     rsi
0x14000ca90  retn
```
