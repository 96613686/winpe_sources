# TdxDetachObjectFromTransport

- ea: `0x1400036b0`
- end: `0x140003831`
- name: `TdxDetachObjectFromTransport`
- size: `385`
- prototype: ``
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x1400042e0`
- `0x1400075b0`
- `0x14000b330`
- `0x140010b90`
- `0x140017ad0`

## callees

- `0x1400036b0`
- `0x140003840`
- `0x14001798c`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140003700`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140003700`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400036f0`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400036f0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400036c6`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003755`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400036c6`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003755`
- `ntoskrnl!RtlGetCallersAddress` at `0x14000379c`
- `ntoskrnl!RtlGetCallersAddress` at `0x14000379c`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000373a`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400037d4`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003806`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000373a`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400037d4`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003806`

## pseudocode

```c
void __fastcall TdxDetachObjectFromTransport(__int64 a1, KSPIN_LOCK *a2)
{
  KIRQL v4; // al
  KSPIN_LOCK *v5; // rcx
  KIRQL v6; // bp
  KSPIN_LOCK v7; // r8
  KSPIN_LOCK **v8; // rdx
  KIRQL v9; // al
  int v10; // ecx
  KIRQL v11; // bl
  __int64 v12; // rdx
  __int64 v13; // rdx
  PVOID CallersAddress; // [rsp+48h] [rbp+10h] BYREF

  v4 = KeAcquireSpinLockRaiseToDpc(a2 + 1);
  v5 = a2 + 1;
  v6 = v4;
  if ( a2[5] )
  {
    a2[5] = 0;
    KeReleaseSpinLockFromDpcLevel(v5);
    KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(a1 + 16));
    v7 = a2[3];
    if ( *(KSPIN_LOCK **)(v7 + 8) != a2 + 3 || (v8 = (KSPIN_LOCK **)a2[4], *v8 != a2 + 3) )
      __fastfail(3u);
    *v8 = (KSPIN_LOCK *)v7;
    *(_QWORD *)(v7 + 8) = v8;
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 16), v6);
    TdxDereferenceObjectHeader(a2);
    v9 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 216));
    v10 = *(_DWORD *)(a1 + 24);
    v11 = v9;
    v12 = *(unsigned int *)(a1 + 1184) + 7LL;
    CallersAddress = 0;
    v13 = a1 + 32 * v12;
    *(_DWORD *)(v13 + 24) = v10 - 1;
    *(_QWORD *)v13 = "minio\\netio\\session\\tdi\\transport.c";
    *(_DWORD *)(v13 + 8) = 572;
    RtlGetCallersAddress(&CallersAddress, (PVOID *)(v13 + 16));
    *(_DWORD *)(a1 + 1184) = (*(_DWORD *)(a1 + 1184) + 1) % 0x1Eu;
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 216), v11);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 24), 0xFFFFFFFF) == 1 )
      TdxCleanupTransport(a1);
  }
  else
  {
    KeReleaseSpinLock(v5, v4);
  }
}

```

## disassembly

```asm
0x1400036b0  mov     [rsp+arg_10], rbx
0x1400036b5  push    rbp
0x1400036b6  push    rsi
0x1400036b7  push    rdi
0x1400036b8  sub     rsp, 20h
0x1400036bc  mov     rsi, rcx
0x1400036bf  mov     rbx, rdx
0x1400036c2  lea     rcx, [rdx+8]; SpinLock
0x1400036c6  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400036cd  nop     dword ptr [rax+rax+00h]
0x1400036d2  cmp     qword ptr [rbx+28h], 0
0x1400036d7  lea     rcx, [rbx+8]; SpinLock
0x1400036db  movzx   ebp, al
0x1400036de  jz      loc_140003802
0x1400036e4  mov     [rsp+38h+arg_0], r14
0x1400036e9  xor     r14d, r14d
0x1400036ec  mov     [rbx+28h], r14
0x1400036f0  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x1400036f7  nop     dword ptr [rax+rax+00h]
0x1400036fc  lea     rcx, [rsi+10h]; SpinLock
0x140003700  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x140003707  nop     dword ptr [rax+rax+00h]
0x14000370c  mov     r8, [rbx+18h]
0x140003710  lea     rax, [rbx+18h]
0x140003714  cmp     [r8+8], rax
0x140003718  jnz     loc_14000382A
0x14000371e  mov     rdx, [rax+8]
0x140003722  cmp     [rdx], rax
0x140003725  jnz     loc_14000382A
0x14000372b  mov     [rdx], r8
0x14000372e  lea     rcx, [rsi+10h]; SpinLock
0x140003732  mov     [r8+8], rdx
0x140003736  movzx   edx, bpl; NewIrql
0x14000373a  call    cs:__imp_KeReleaseSpinLock
0x140003741  nop     dword ptr [rax+rax+00h]
0x140003746  mov     rcx, rbx
0x140003749  call    TdxDereferenceObjectHeader
0x14000374e  lea     rcx, [rsi+0D8h]; SpinLock
0x140003755  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000375c  nop     dword ptr [rax+rax+00h]
0x140003761  mov     ecx, [rsi+18h]
0x140003764  movzx   ebx, al
0x140003767  mov     edx, [rsi+4A0h]
0x14000376d  lea     rax, aMinioNetioSess_4; "minio\\netio\\session\\tdi\\transport.c"
0x140003774  add     rdx, 7
0x140003778  mov     [rsp+38h+CallersAddress], r14
0x14000377d  shl     rdx, 5
0x140003781  add     rdx, rsi
0x140003784  dec     ecx
0x140003786  mov     [rdx+18h], ecx
0x140003789  lea     rcx, [rsp+38h+CallersAddress]; CallersAddress
0x14000378e  mov     [rdx], rax
0x140003791  mov     dword ptr [rdx+8], 23Ch
0x140003798  add     rdx, 10h; CallersCaller
0x14000379c  call    cs:__imp_RtlGetCallersAddress
0x1400037a3  nop     dword ptr [rax+rax+00h]
0x1400037a8  mov     r8d, [rsi+4A0h]
0x1400037af  lea     rcx, [rsi+0D8h]; SpinLock
0x1400037b6  inc     r8d
0x1400037b9  mov     eax, 88888889h
0x1400037be  mul     r8d
0x1400037c1  shr     edx, 4
0x1400037c4  imul    eax, edx, 1Eh
0x1400037c7  movzx   edx, bl; NewIrql
0x1400037ca  sub     r8d, eax
0x1400037cd  mov     [rsi+4A0h], r8d
0x1400037d4  call    cs:__imp_KeReleaseSpinLock
0x1400037db  nop     dword ptr [rax+rax+00h]
0x1400037e0  mov     eax, 0FFFFFFFFh
0x1400037e5  lock xadd [rsi+18h], eax
0x1400037ea  cmp     eax, 1
0x1400037ed  jz      short loc_140003820
0x1400037ef  mov     r14, [rsp+38h+arg_0]
0x1400037f4  mov     rbx, [rsp+38h+arg_10]
0x1400037f9  add     rsp, 20h
0x1400037fd  pop     rdi
0x1400037fe  pop     rsi
0x1400037ff  pop     rbp
0x140003800  retn
0x140003802  movzx   edx, bpl; NewIrql
0x140003806  call    cs:__imp_KeReleaseSpinLock
0x14000380d  nop     dword ptr [rax+rax+00h]
0x140003812  mov     rbx, [rsp+38h+arg_10]
0x140003817  add     rsp, 20h
0x14000381b  pop     rdi
0x14000381c  pop     rsi
0x14000381d  pop     rbp
0x14000381e  retn
0x140003820  mov     rcx, rsi
0x140003823  call    TdxCleanupTransport
0x140003828  jmp     short loc_1400037EF
0x14000382a  mov     ecx, 3
0x14000382f  int     29h; Win8: RtlFailFast(ecx)
```
