# DbgTdxDereferenceTransport

- ea: `0x14000ccfc`
- end: `0x14000cdd3`
- name: `DbgTdxDereferenceTransport`
- size: `215`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `13`
- callee_count: `2`
- tags: ``

## callers

- `0x140004df4`
- `0x140006608`
- `0x14000aad0`
- `0x14000bab0`
- `0x14000cb10`
- `0x14000cde0`
- `0x1400112e0`
- `0x1400157cc`
- `0x140015c20`
- `0x14001606c`
- `0x1400174d0`
- `0x140017cdc`
- `0x140017dcc`

## callees

- `0x14000ccfc`
- `0x14001798c`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000cd21`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000cd21`
- `ntoskrnl!RtlGetCallersAddress` at `0x14000cd69`
- `ntoskrnl!RtlGetCallersAddress` at `0x14000cd69`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000cd9d`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000cd9d`

## pseudocode

```c
void __fastcall DbgTdxDereferenceTransport(__int64 a1, __int64 a2, int a3)
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
  *(_DWORD *)(v9 + a1 + 24) = v8 - 1;
  *(_QWORD *)(v9 + a1) = a2;
  *(_DWORD *)(v9 + a1 + 8) = a3;
  RtlGetCallersAddress(&CallersAddress, (PVOID *)(v9 + a1 + 16));
  *(_DWORD *)(a1 + 1184) = (*(_DWORD *)(a1 + 1184) + 1) % 0x1Eu;
  KeReleaseSpinLock(v3, v10);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 24), 0xFFFFFFFF) == 1 )
    TdxCleanupTransport(a1);
}

```

## disassembly

```asm
0x14000ccfc  mov     [rsp+arg_8], rbx
0x14000cd01  mov     [rsp+arg_10], rbp
0x14000cd06  push    rsi
0x14000cd07  push    rdi
0x14000cd08  push    r14
0x14000cd0a  sub     rsp, 20h
0x14000cd0e  lea     rbp, [rcx+0D8h]
0x14000cd15  mov     r14, rcx
0x14000cd18  mov     rcx, rbp; SpinLock
0x14000cd1b  mov     edi, r8d
0x14000cd1e  mov     rbx, rdx
0x14000cd21  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000cd28  nop     dword ptr [rax+rax+00h]
0x14000cd2d  mov     r8d, [r14+18h]
0x14000cd31  lea     rdx, [r14+10h]
0x14000cd35  mov     r9d, [r14+4A0h]
0x14000cd3c  lea     rcx, [rsp+38h+CallersAddress]; CallersAddress
0x14000cd41  add     r9, 7
0x14000cd45  mov     [rsp+38h+CallersAddress], 0
0x14000cd4e  shl     r9, 5
0x14000cd52  mov     sil, al
0x14000cd55  dec     r8d
0x14000cd58  add     rdx, r9; CallersCaller
0x14000cd5b  mov     [r9+r14+18h], r8d
0x14000cd60  mov     [r9+r14], rbx
0x14000cd64  mov     [r9+r14+8], edi
0x14000cd69  call    cs:__imp_RtlGetCallersAddress
0x14000cd70  nop     dword ptr [rax+rax+00h]
0x14000cd75  mov     r8d, [r14+4A0h]
0x14000cd7c  mov     eax, 88888889h
0x14000cd81  inc     r8d
0x14000cd84  mov     rcx, rbp; SpinLock
0x14000cd87  mul     r8d
0x14000cd8a  shr     edx, 4
0x14000cd8d  imul    eax, edx, 1Eh
0x14000cd90  mov     dl, sil; NewIrql
0x14000cd93  sub     r8d, eax
0x14000cd96  mov     [r14+4A0h], r8d
0x14000cd9d  call    cs:__imp_KeReleaseSpinLock
0x14000cda4  nop     dword ptr [rax+rax+00h]
0x14000cda9  or      eax, 0FFFFFFFFh
0x14000cdac  lock xadd [r14+18h], eax
0x14000cdb2  cmp     eax, 1
0x14000cdb5  jnz     short loc_14000CDBF
0x14000cdb7  mov     rcx, r14
0x14000cdba  call    TdxCleanupTransport
0x14000cdbf  mov     rbx, [rsp+38h+arg_8]
0x14000cdc4  mov     rbp, [rsp+38h+arg_10]
0x14000cdc9  add     rsp, 20h
0x14000cdcd  pop     r14
0x14000cdcf  pop     rdi
0x14000cdd0  pop     rsi
0x14000cdd1  retn
```
