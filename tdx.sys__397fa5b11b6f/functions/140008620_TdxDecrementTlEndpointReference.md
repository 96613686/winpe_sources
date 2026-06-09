# TdxDecrementTlEndpointReference

- ea: `0x140008620`
- end: `0x140008792`
- name: `TdxDecrementTlEndpointReference`
- size: `370`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `11`
- callee_count: `4`
- tags: ``

## callers

- `0x1400023b0`
- `0x140002920`
- `0x140002fb0`
- `0x140003c9c`
- `0x140005688`
- `0x14000a5f0`
- `0x140010100`
- `0x140013460`
- `0x140013760`
- `0x1400139b0`
- `0x140017ad0`

## callees

- `0x140008620`
- `0x140008c50`
- `0x14000f4f0`
- `0x140013af4`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140008664`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140008738`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140008664`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140008738`
- `ntoskrnl!RtlGetCallersAddress` at `0x1400086bb`
- `ntoskrnl!RtlGetCallersAddress` at `0x1400086bb`
- `ntoskrnl!KeReleaseSpinLock` at `0x140008651`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400086e3`
- `ntoskrnl!KeReleaseSpinLock` at `0x140008651`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400086e3`

## pseudocode

```c
void __fastcall TdxDecrementTlEndpointReference(__int64 a1, __int64 a2, char a3)
{
  KIRQL v4; // al
  int v5; // ecx
  KIRQL v6; // di
  __int64 v7; // r14
  __int64 v8; // rdx
  __int64 v9; // r8
  int v10; // [rsp+20h] [rbp-48h]
  int v11; // [rsp+38h] [rbp-30h]
  PVOID CallersAddress; // [rsp+70h] [rbp+8h] BYREF

  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 72), 0xFFFFFFFF) == 1 )
  {
    if ( !a3 )
      a2 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 8));
    TdxShutdownEndpointConnection(a1, a2);
  }
  else if ( a3 )
  {
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 8), a2);
  }
  v4 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 368));
  v5 = *(_DWORD *)(a1 + 16) - 1;
  v6 = v4;
  v7 = a1 + 32LL * *(unsigned int *)(a1 + 632);
  CallersAddress = 0;
  *(_DWORD *)(v7 + 400) = v5;
  *(_QWORD *)(v7 + 376) = "TdxDecrementTlEndpointReference";
  *(_DWORD *)(v7 + 384) = 368;
  RtlGetCallersAddress(&CallersAddress, (PVOID *)(v7 + 392));
  *(_DWORD *)(a1 + 632) = ((unsigned __int8)*(_DWORD *)(a1 + 632) + 1) & 7;
  KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 368), v6);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
  {
    v11 = 368;
    v10 = *(_DWORD *)(v7 + 400);
    WPP_SF_qdssD(
      (__int64)WPP_GLOBAL_Control->AttachedDevice,
      v8,
      v9,
      a1,
      v10,
      "--",
      "TdxDecrementTlEndpointReference",
      v11);
  }
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 16), 0xFFFFFFFF) == 1 )
    TdxCleanupObjectHeader(a1);
}

```

## disassembly

```asm
0x140008620  mov     [rsp+arg_10], rbx
0x140008625  push    rbp
0x140008626  push    rsi
0x140008627  push    rdi
0x140008628  push    r14
0x14000862a  push    r15
0x14000862c  sub     rsp, 40h
0x140008630  mov     ebp, 0FFFFFFFFh
0x140008635  mov     rbx, rcx
0x140008638  mov     eax, ebp
0x14000863a  lock xadd [rcx+48h], eax
0x14000863f  cmp     eax, 1
0x140008642  jz      loc_14000872F
0x140008648  test    r8b, r8b
0x14000864b  jz      short loc_14000865D
0x14000864d  add     rcx, 8; SpinLock
0x140008651  call    cs:__imp_KeReleaseSpinLock
0x140008658  nop     dword ptr [rax+rax+00h]
0x14000865d  lea     rcx, [rbx+170h]; SpinLock
0x140008664  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000866b  nop     dword ptr [rax+rax+00h]
0x140008670  mov     ecx, [rbx+10h]
0x140008673  lea     r15, aTdxdecrementtl; "TdxDecrementTlEndpointReference"
0x14000867a  mov     r14d, [rbx+278h]
0x140008681  dec     ecx
0x140008683  shl     r14, 5
0x140008687  movzx   edi, al
0x14000868a  add     r14, rbx
0x14000868d  mov     [rsp+68h+CallersAddress], 0
0x140008696  mov     [r14+190h], ecx
0x14000869d  lea     rdx, [r14+188h]; CallersCaller
0x1400086a4  lea     rcx, [rsp+68h+CallersAddress]; CallersAddress
0x1400086a9  mov     [r14+178h], r15
0x1400086b0  mov     dword ptr [r14+180h], 170h
0x1400086bb  call    cs:__imp_RtlGetCallersAddress
0x1400086c2  nop     dword ptr [rax+rax+00h]
0x1400086c7  mov     eax, [rbx+278h]
0x1400086cd  lea     rcx, [rbx+170h]; SpinLock
0x1400086d4  inc     eax
0x1400086d6  movzx   edx, dil; NewIrql
0x1400086da  and     eax, 7
0x1400086dd  mov     [rbx+278h], eax
0x1400086e3  call    cs:__imp_KeReleaseSpinLock
0x1400086ea  nop     dword ptr [rax+rax+00h]
0x1400086ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1400086f6  lea     rax, WPP_GLOBAL_Control
0x1400086fd  cmp     rcx, rax
0x140008700  jz      short loc_140008708
0x140008702  cmp     byte ptr [rcx+29h], 5
0x140008706  jnb     short loc_140008754
0x140008708  lock xadd [rbx+10h], ebp
0x14000870d  cmp     ebp, 1
0x140008710  jnz     short loc_14000871A
0x140008712  mov     rcx, rbx
0x140008715  call    TdxCleanupObjectHeader
0x14000871a  mov     rbx, [rsp+68h+arg_10]
0x140008722  add     rsp, 40h
0x140008726  pop     r15
0x140008728  pop     r14
0x14000872a  pop     rdi
0x14000872b  pop     rsi
0x14000872c  pop     rbp
0x14000872d  retn
0x14000872f  test    r8b, r8b
0x140008732  jnz     short loc_140008747
0x140008734  add     rcx, 8; SpinLock
0x140008738  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000873f  nop     dword ptr [rax+rax+00h]
0x140008744  movzx   edx, al
0x140008747  mov     rcx, rbx
0x14000874a  call    TdxShutdownEndpointConnection
0x14000874f  jmp     loc_14000865D
0x140008754  test    dword ptr [rcx+2Ch], 200h
0x14000875b  jz      short loc_140008708
0x14000875d  mov     rcx, [rcx+18h]
0x140008761  lea     rax, asc_14001AAE0; "--"
0x140008768  mov     [rsp+68h+var_30], 170h
0x140008770  mov     r9, rbx
0x140008773  mov     [rsp+68h+var_38], r15
0x140008778  mov     [rsp+68h+var_40], rax
0x14000877d  mov     eax, [r14+190h]
0x140008784  mov     [rsp+68h+var_48], eax
0x140008788  call    WPP_SF_qdssD
0x14000878d  jmp     loc_140008708
```
