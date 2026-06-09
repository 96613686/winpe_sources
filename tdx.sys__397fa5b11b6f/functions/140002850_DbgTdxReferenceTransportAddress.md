# DbgTdxReferenceTransportAddress

- ea: `0x140002850`
- end: `0x14000290e`
- name: `DbgTdxReferenceTransportAddress`
- size: `190`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `21`
- callee_count: `0`
- tags: ``

## callers

- `0x1400010b0`
- `0x140001c5c`
- `0x140001ce0`
- `0x140002920`
- `0x1400043b0`
- `0x140004920`
- `0x140004df4`
- `0x140005688`
- `0x140005b00`
- `0x140006608`
- `0x1400075b0`
- `0x140007b90`
- `0x14000aad0`
- `0x14000bab0`
- `0x140010100`
- `0x140012400`
- `0x1400126e4`
- `0x140012894`
- `0x140013174`
- `0x1400157cc`
- `0x140015c20`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002872`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002872`
- `ntoskrnl!RtlGetCallersAddress` at `0x1400028bf`
- `ntoskrnl!RtlGetCallersAddress` at `0x1400028bf`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400028e9`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400028e9`

## pseudocode

```c
void __fastcall DbgTdxReferenceTransportAddress(__int64 a1, __int64 a2, int a3)
{
  KIRQL v6; // si
  int v7; // r9d
  __int64 v8; // rdx
  PVOID CallersAddress; // [rsp+40h] [rbp+8h] BYREF

  v6 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 552));
  v7 = *(_DWORD *)(a1 + 16) + 1;
  v8 = a1 + 32LL * *(unsigned int *)(a1 + 816);
  CallersAddress = 0;
  *(_DWORD *)(v8 + 584) = v7;
  *(_QWORD *)(v8 + 560) = a2;
  *(_DWORD *)(v8 + 568) = a3;
  RtlGetCallersAddress(&CallersAddress, (PVOID *)(v8 + 576));
  *(_DWORD *)(a1 + 816) = ((unsigned __int8)*(_DWORD *)(a1 + 816) + 1) & 7;
  KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 552), v6);
  _InterlockedIncrement((volatile signed __int32 *)(a1 + 16));
}

```

## disassembly

```asm
0x140002850  mov     [rsp+arg_8], rbx
0x140002855  mov     [rsp+arg_10], rbp
0x14000285a  push    rsi
0x14000285b  push    rdi
0x14000285c  push    r14
0x14000285e  sub     rsp, 20h
0x140002862  mov     r14, rcx
0x140002865  mov     edi, r8d
0x140002868  add     rcx, 228h; SpinLock
0x14000286f  mov     rbx, rdx
0x140002872  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140002879  nop     dword ptr [rax+rax+00h]
0x14000287e  mov     edx, [r14+330h]
0x140002885  lea     rcx, [rsp+38h+CallersAddress]; CallersAddress
0x14000288a  mov     r9d, [r14+10h]
0x14000288e  movzx   esi, al
0x140002891  shl     rdx, 5
0x140002895  inc     r9d
0x140002898  add     rdx, r14
0x14000289b  mov     [rsp+38h+CallersAddress], 0
0x1400028a4  mov     [rdx+248h], r9d
0x1400028ab  mov     [rdx+230h], rbx
0x1400028b2  mov     [rdx+238h], edi
0x1400028b8  add     rdx, 240h; CallersCaller
0x1400028bf  call    cs:__imp_RtlGetCallersAddress
0x1400028c6  nop     dword ptr [rax+rax+00h]
0x1400028cb  mov     eax, [r14+330h]
0x1400028d2  lea     rcx, [r14+228h]; SpinLock
0x1400028d9  inc     eax
0x1400028db  movzx   edx, sil; NewIrql
0x1400028df  and     eax, 7
0x1400028e2  mov     [r14+330h], eax
0x1400028e9  call    cs:__imp_KeReleaseSpinLock
0x1400028f0  nop     dword ptr [rax+rax+00h]
0x1400028f5  lock inc dword ptr [r14+10h]
0x1400028fa  mov     rbx, [rsp+38h+arg_8]
0x1400028ff  mov     rbp, [rsp+38h+arg_10]
0x140002904  add     rsp, 20h
0x140002908  pop     r14
0x14000290a  pop     rdi
0x14000290b  pop     rsi
0x14000290c  retn
```
