# TdxEventAbortConnection

- ea: `0x1400012b0`
- end: `0x140001542`
- name: `TdxEventAbortConnection`
- size: `658`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1400010b0`

## callees

- `0x1400012b0`
- `0x140003590`
- `0x1400047d0`
- `0x14000f4f0`
- `0x14001303c`
- `0x1400130bc`

## import_xrefs

- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140001455`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140001455`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140001445`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140001445`
- `ntoskrnl!IofCompleteRequest` at `0x1400014ac`
- `ntoskrnl!IofCompleteRequest` at `0x1400014ac`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140001464`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140001464`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140001434`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140001434`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000131b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400014c0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000131b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400014c0`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001476`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001476`

## pseudocode

```c
__int64 __fastcall TdxEventAbortConnection(__int64 a1, __int64 a2, __int64 a3)
{
  KIRQL v5; // r15
  const char *v6; // rax
  int v7; // eax
  unsigned int v8; // edi
  const char *v9; // rax
  unsigned int v10; // edi
  bool v11; // di
  __int64 v12; // rdx
  KIRQL v13; // di
  __int64 Irql; // [rsp+68h] [rbp+10h] BYREF

  Irql = a2;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u
    && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 9u) )
  {
    WPP_SF_sq(
      WPP_GLOBAL_Control->AttachedDevice,
      22,
      (unsigned int)WPP_3f4cea39b6aa324a7b8e41338ba6e995_Traceguids,
      (unsigned int)"TdxEventAbortConnection",
      a1);
  }
  v5 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 8));
  if ( *(_QWORD *)(a1 + 304) == a1 + 304 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u
      && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 9u) )
    {
      v6 = "TRUE";
      if ( (*(_DWORD *)a1 & 0x1000) == 0 )
        v6 = "FALSE";
      WPP_SF_sqs(
        WPP_GLOBAL_Control->AttachedDevice,
        23,
        (unsigned int)WPP_3f4cea39b6aa324a7b8e41338ba6e995_Traceguids,
        (unsigned int)"TdxEventAbortConnection",
        a1,
        (__int64)v6);
    }
    v7 = 0;
    v8 = *(_DWORD *)a1 | 0x1000;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u
      && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 9u) )
    {
      v9 = "TRUE";
      if ( (*(_DWORD *)a1 & 0x1000) == 0 )
        v9 = "FALSE";
      WPP_SF_sqs(
        WPP_GLOBAL_Control->AttachedDevice,
        24,
        (unsigned int)WPP_3f4cea39b6aa324a7b8e41338ba6e995_Traceguids,
        (unsigned int)"TdxEventAbortConnection",
        a1,
        (__int64)v9);
    }
    v7 = 1;
    v8 = *(_DWORD *)a1 & 0xFFFFEFFF;
  }
  v10 = v8 & 0xFFFFFFF9;
  *(_DWORD *)(a1 + 76) = v7;
  *(_DWORD *)a1 = v10;
  v11 = (v10 & 0x40) != 0;
  if ( v11 )
    DbgTdxReferenceConnection(a1, "TdxEventAbortConnection", 640);
  *(_OWORD *)(a1 + 248) = 0;
  if ( a3 && !_InterlockedExchange64((volatile __int64 *)(a3 + 104), 0) )
  {
    LOBYTE(Irql) = 0;
    KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(a1 + 8));
    IoAcquireCancelSpinLock((PKIRQL)&Irql);
    IoReleaseCancelSpinLock(Irql);
    KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(a1 + 8));
  }
  KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 8), v5);
  DbgTdxDereferenceConnection(a1, (__int64)"TdxEventAbortConnection", 665);
  if ( a3 )
  {
    *(_DWORD *)(a3 + 48) = -1073741299;
    *(_QWORD *)(a3 + 56) = 0;
    IofCompleteRequest((PIRP)a3, 2);
  }
  if ( v11 )
  {
    v13 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 8));
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u
      && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 9u) )
    {
      WPP_SF_sq(
        WPP_GLOBAL_Control->AttachedDevice,
        25,
        (unsigned int)WPP_3f4cea39b6aa324a7b8e41338ba6e995_Traceguids,
        (unsigned int)"TdxEventAbortConnection",
        a1);
    }
    LOBYTE(v12) = v13;
    TdxShutdownEndpointConnection(a1, v12);
    DbgTdxDereferenceConnection(a1, (__int64)"TdxEventAbortConnection", 688);
  }
  return 0;
}

```

## disassembly

```asm
0x1400012b0  mov     rax, rsp
0x1400012b3  mov     [rax+8], rbx
0x1400012b7  mov     [rax+18h], rbp
0x1400012bb  mov     [rax+10h], rdx
0x1400012bf  push    rsi
0x1400012c0  push    rdi
0x1400012c1  push    r12
0x1400012c3  push    r13
0x1400012c5  push    r15
0x1400012c7  sub     rsp, 30h
0x1400012cb  mov     rsi, r8
0x1400012ce  mov     rbx, rcx
0x1400012d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400012d8  lea     rdi, WPP_GLOBAL_Control
0x1400012df  lea     r12, aTdxeventabortc; "TdxEventAbortConnection"
0x1400012e6  cmp     rcx, rdi
0x1400012e9  jz      short loc_140001314
0x1400012eb  cmp     byte ptr [rcx+29h], 4
0x1400012ef  jb      short loc_140001314
0x1400012f1  bt      dword ptr [rcx+2Ch], 9
0x1400012f6  jnb     short loc_140001314
0x1400012f8  mov     rcx, [rcx+18h]
0x1400012fc  lea     r8, WPP_3f4cea39b6aa324a7b8e41338ba6e995_Traceguids
0x140001303  mov     edx, 16h
0x140001308  mov     [rax-38h], rbx
0x14000130c  mov     r9, r12
0x14000130f  call    WPP_SF_sq
0x140001314  lea     rbp, [rbx+8]
0x140001318  mov     rcx, rbp; SpinLock
0x14000131b  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140001322  nop     dword ptr [rax+rax+00h]
0x140001327  lea     rcx, [rbx+130h]
0x14000132e  mov     r15b, al
0x140001331  cmp     [rcx], rcx
0x140001334  jnz     short loc_140001393
0x140001336  mov     rcx, cs:WPP_GLOBAL_Control
0x14000133d  cmp     rcx, rdi
0x140001340  jz      short loc_140001389
0x140001342  cmp     byte ptr [rcx+29h], 5
0x140001346  jb      short loc_140001389
0x140001348  bt      dword ptr [rcx+2Ch], 9
0x14000134d  jnb     short loc_140001389
0x14000134f  test    dword ptr [rbx], 1000h
0x140001355  lea     rdx, aFalse; "FALSE"
0x14000135c  mov     rcx, [rcx+18h]
0x140001360  lea     rax, aTrue; "TRUE"
0x140001367  cmovz   rax, rdx
0x14000136b  lea     r8, WPP_3f4cea39b6aa324a7b8e41338ba6e995_Traceguids
0x140001372  mov     [rsp+58h+var_30], rax
0x140001377  mov     edx, 17h
0x14000137c  mov     r9, r12
0x14000137f  mov     [rsp+58h+var_38], rbx
0x140001384  call    WPP_SF_sqs
0x140001389  mov     edi, [rbx]
0x14000138b  xor     eax, eax
0x14000138d  bts     edi, 0Ch
0x140001391  jmp     short loc_1400013F1
0x140001393  mov     rcx, cs:WPP_GLOBAL_Control
0x14000139a  cmp     rcx, rdi
0x14000139d  jz      short loc_1400013E6
0x14000139f  cmp     byte ptr [rcx+29h], 5
0x1400013a3  jb      short loc_1400013E6
0x1400013a5  bt      dword ptr [rcx+2Ch], 9
0x1400013aa  jnb     short loc_1400013E6
0x1400013ac  test    dword ptr [rbx], 1000h
0x1400013b2  lea     rdx, aFalse; "FALSE"
0x1400013b9  mov     rcx, [rcx+18h]
0x1400013bd  lea     rax, aTrue; "TRUE"
0x1400013c4  cmovz   rax, rdx
0x1400013c8  lea     r8, WPP_3f4cea39b6aa324a7b8e41338ba6e995_Traceguids
0x1400013cf  mov     [rsp+58h+var_30], rax
0x1400013d4  mov     edx, 18h
0x1400013d9  mov     r9, r12
0x1400013dc  mov     [rsp+58h+var_38], rbx
0x1400013e1  call    WPP_SF_sqs
0x1400013e6  mov     edi, [rbx]
0x1400013e8  mov     eax, 1
0x1400013ed  btr     edi, 0Ch
0x1400013f1  and     edi, 0FFFFFFF9h
0x1400013f4  mov     [rbx+4Ch], eax
0x1400013f7  mov     [rbx], edi
0x1400013f9  shr     edi, 6
0x1400013fc  and     dil, 1
0x140001400  jz      short loc_140001413
0x140001402  mov     r8d, 280h
0x140001408  mov     rdx, r12
0x14000140b  mov     rcx, rbx
0x14000140e  call    DbgTdxReferenceConnection
0x140001413  xorps   xmm0, xmm0
0x140001416  movups  xmmword ptr [rbx+0F8h], xmm0
0x14000141d  test    rsi, rsi
0x140001420  jz      short loc_140001470
0x140001422  xor     eax, eax
0x140001424  xchg    rax, [rsi+68h]
0x140001428  test    rax, rax
0x14000142b  jnz     short loc_140001470
0x14000142d  mov     rcx, rbp; SpinLock
0x140001430  mov     byte ptr [rsp+58h+Irql], al
0x140001434  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x14000143b  nop     dword ptr [rax+rax+00h]
0x140001440  lea     rcx, [rsp+58h+Irql]; Irql
0x140001445  call    cs:__imp_IoAcquireCancelSpinLock
0x14000144c  nop     dword ptr [rax+rax+00h]
0x140001451  mov     cl, byte ptr [rsp+58h+Irql]; Irql
0x140001455  call    cs:__imp_IoReleaseCancelSpinLock
0x14000145c  nop     dword ptr [rax+rax+00h]
0x140001461  mov     rcx, rbp; SpinLock
0x140001464  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x14000146b  nop     dword ptr [rax+rax+00h]
0x140001470  mov     dl, r15b; NewIrql
0x140001473  mov     rcx, rbp; SpinLock
0x140001476  call    cs:__imp_KeReleaseSpinLock
0x14000147d  nop     dword ptr [rax+rax+00h]
0x140001482  mov     r8d, 299h
0x140001488  mov     rdx, r12
0x14000148b  mov     rcx, rbx
0x14000148e  call    DbgTdxDereferenceConnection
0x140001493  test    rsi, rsi
0x140001496  jz      short loc_1400014B8
0x140001498  mov     dl, 2; PriorityBoost
0x14000149a  mov     dword ptr [rsi+30h], 0C000020Dh
0x1400014a1  mov     rcx, rsi; Irp
0x1400014a4  mov     qword ptr [rsi+38h], 0
0x1400014ac  call    cs:__imp_IofCompleteRequest
0x1400014b3  nop     dword ptr [rax+rax+00h]
0x1400014b8  test    dil, dil
0x1400014bb  jz      short loc_140001528
0x1400014bd  mov     rcx, rbp; SpinLock
0x1400014c0  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400014c7  nop     dword ptr [rax+rax+00h]
0x1400014cc  mov     dil, al
0x1400014cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1400014d6  lea     rax, WPP_GLOBAL_Control
0x1400014dd  cmp     rcx, rax
0x1400014e0  jz      short loc_14000150C
0x1400014e2  cmp     byte ptr [rcx+29h], 4
0x1400014e6  jb      short loc_14000150C
0x1400014e8  bt      dword ptr [rcx+2Ch], 9
0x1400014ed  jnb     short loc_14000150C
0x1400014ef  mov     rcx, [rcx+18h]
0x1400014f3  lea     r8, WPP_3f4cea39b6aa324a7b8e41338ba6e995_Traceguids
0x1400014fa  mov     edx, 19h
0x1400014ff  mov     [rsp+58h+var_38], rbx
0x140001504  mov     r9, r12
0x140001507  call    WPP_SF_sq
0x14000150c  mov     dl, dil
0x14000150f  mov     rcx, rbx
0x140001512  call    TdxShutdownEndpointConnection
0x140001517  mov     r8d, 2B0h
0x14000151d  mov     rdx, r12
0x140001520  mov     rcx, rbx
0x140001523  call    DbgTdxDereferenceConnection
0x140001528  mov     rbx, [rsp+58h+arg_0]
0x14000152d  xor     eax, eax
0x14000152f  mov     rbp, [rsp+58h+arg_10]
0x140001534  add     rsp, 30h
0x140001538  pop     r15
0x14000153a  pop     r13
0x14000153c  pop     r12
0x14000153e  pop     rdi
0x14000153f  pop     rsi
0x140001540  retn
```
