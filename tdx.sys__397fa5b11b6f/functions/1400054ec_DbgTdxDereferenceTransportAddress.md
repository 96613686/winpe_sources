# DbgTdxDereferenceTransportAddress

- ea: `0x1400054ec`
- end: `0x1400055f7`
- name: `DbgTdxDereferenceTransportAddress`
- size: `267`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `33`
- callee_count: `3`
- tags: ``

## callers

- `0x1400010b0`
- `0x140001a70`
- `0x140001ce0`
- `0x140002920`
- `0x140002fb0`
- `0x140003840`
- `0x1400039c0`
- `0x140003c9c`
- `0x1400042e0`
- `0x1400043b0`
- `0x140004920`
- `0x140004df4`
- `0x140005688`
- `0x140005b00`
- `0x140006608`
- `0x1400075b0`
- `0x140007b90`
- `0x1400087a0`
- `0x140009290`
- `0x14000aad0`
- `0x14000b330`
- `0x14000bab0`
- `0x14000fcf0`
- `0x140010100`
- `0x1400106c0`
- `0x140010748`
- `0x140011fd0`
- `0x140012400`
- `0x1400129a0`
- `0x140012a8c`
- `0x140013174`
- `0x140015780`
- `0x1400159f0`

## callees

- `0x1400054ec`
- `0x140008c50`
- `0x140012b8c`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140005511`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140005511`
- `ntoskrnl!RtlGetCallersAddress` at `0x140005562`
- `ntoskrnl!RtlGetCallersAddress` at `0x140005562`
- `ntoskrnl!KeReleaseSpinLock` at `0x140005587`
- `ntoskrnl!KeReleaseSpinLock` at `0x140005587`

## pseudocode

```c
void __fastcall DbgTdxDereferenceTransportAddress(__int64 a1, __int64 a2, int a3)
{
  KSPIN_LOCK *v3; // rbp
  KIRQL v7; // al
  __int64 v8; // r10
  KIRQL v9; // si
  int v10; // r9d
  PVOID CallersAddress; // [rsp+40h] [rbp+8h] BYREF

  v3 = (KSPIN_LOCK *)(a1 + 552);
  v7 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 552));
  v8 = 32LL * *(unsigned int *)(a1 + 816);
  v9 = v7;
  v10 = *(_DWORD *)(a1 + 16) - 1;
  CallersAddress = 0;
  *(_DWORD *)(v8 + a1 + 584) = v10;
  *(_QWORD *)(v8 + a1 + 560) = a2;
  *(_DWORD *)(v8 + a1 + 568) = a3;
  RtlGetCallersAddress(&CallersAddress, (PVOID *)(v8 + a1 + 576));
  *(_DWORD *)(a1 + 816) = ((unsigned __int8)*(_DWORD *)(a1 + 816) + 1) & 7;
  KeReleaseSpinLock(v3, v9);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 16), 0xFFFFFFFF) == 1 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_63c55c6b4ff2326ef703f60977e9aaef_Traceguids, a1);
    }
    TdxCleanupObjectHeader(a1);
  }
}

```

## disassembly

```asm
0x1400054ec  mov     [rsp+arg_8], rbx
0x1400054f1  mov     [rsp+arg_10], rbp
0x1400054f6  push    rsi
0x1400054f7  push    rdi
0x1400054f8  push    r14
0x1400054fa  sub     rsp, 20h
0x1400054fe  lea     rbp, [rcx+228h]
0x140005505  mov     r14, rcx
0x140005508  mov     rcx, rbp; SpinLock
0x14000550b  mov     edi, r8d
0x14000550e  mov     rbx, rdx
0x140005511  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140005518  nop     dword ptr [rax+rax+00h]
0x14000551d  mov     r9d, [r14+10h]
0x140005521  lea     rdx, [r14+240h]
0x140005528  mov     r10d, [r14+330h]
0x14000552f  lea     rcx, [rsp+38h+CallersAddress]; CallersAddress
0x140005534  shl     r10, 5
0x140005538  mov     sil, al
0x14000553b  dec     r9d
0x14000553e  mov     [rsp+38h+CallersAddress], 0
0x140005547  add     rdx, r10; CallersCaller
0x14000554a  mov     [r10+r14+248h], r9d
0x140005552  mov     [r10+r14+230h], rbx
0x14000555a  mov     [r10+r14+238h], edi
0x140005562  call    cs:__imp_RtlGetCallersAddress
0x140005569  nop     dword ptr [rax+rax+00h]
0x14000556e  mov     eax, [r14+330h]
0x140005575  mov     dl, sil; NewIrql
0x140005578  inc     eax
0x14000557a  mov     rcx, rbp; SpinLock
0x14000557d  and     eax, 7
0x140005580  mov     [r14+330h], eax
0x140005587  call    cs:__imp_KeReleaseSpinLock
0x14000558e  nop     dword ptr [rax+rax+00h]
0x140005593  or      eax, 0FFFFFFFFh
0x140005596  lock xadd [r14+10h], eax
0x14000559c  cmp     eax, 1
0x14000559f  jnz     short loc_1400055E3
0x1400055a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400055a8  lea     rax, WPP_GLOBAL_Control
0x1400055af  cmp     rcx, rax
0x1400055b2  jz      short loc_1400055DB
0x1400055b4  cmp     byte ptr [rcx+29h], 5
0x1400055b8  jb      short loc_1400055DB
0x1400055ba  test    dword ptr [rcx+2Ch], 200h
0x1400055c1  jz      short loc_1400055DB
0x1400055c3  mov     rcx, [rcx+18h]
0x1400055c7  lea     r8, WPP_63c55c6b4ff2326ef703f60977e9aaef_Traceguids
0x1400055ce  mov     edx, 11h
0x1400055d3  mov     r9, r14
0x1400055d6  call    WPP_SF_q
0x1400055db  mov     rcx, r14
0x1400055de  call    TdxCleanupObjectHeader
0x1400055e3  mov     rbx, [rsp+38h+arg_8]
0x1400055e8  mov     rbp, [rsp+38h+arg_10]
0x1400055ed  add     rsp, 20h
0x1400055f1  pop     r14
0x1400055f3  pop     rdi
0x1400055f4  pop     rsi
0x1400055f5  retn
```
