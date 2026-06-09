# TdxDisconnectConnectionTlRequestComplete

- ea: `0x14000a5f0`
- end: `0x14000a8be`
- name: `TdxDisconnectConnectionTlRequestComplete`
- size: `718`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140006db0`
- `0x14000aad0`

## callees

- `0x140008620`
- `0x140008c50`
- `0x14000a5f0`
- `0x140013af4`
- `0x140013dc0`

## import_xrefs

- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14000a85b`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14000a85b`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14000a847`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14000a847`
- `ntoskrnl!IofCompleteRequest` at `0x14000a6a4`
- `ntoskrnl!IofCompleteRequest` at `0x14000a6a4`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14000a86b`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14000a86b`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000a833`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000a833`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000a638`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000a6b7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000a638`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000a6b7`
- `ntoskrnl!RtlGetCallersAddress` at `0x14000a70d`
- `ntoskrnl!RtlGetCallersAddress` at `0x14000a70d`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000a693`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000a735`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000a7da`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000a693`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000a735`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000a7da`

## string_xrefs

- `0x14000a61e`: `TdxDisconnectConnectionTlRequestComplete`

## pseudocode

```c
void __fastcall TdxDisconnectConnectionTlRequestComplete(__int64 *a1, int a2, __int64 a3)
{
  __int64 v3; // rbx
  __int64 v5; // rdi
  KIRQL v7; // al
  bool v8; // dl
  __int64 v9; // r8
  KIRQL v10; // r15
  KIRQL v11; // di
  int v12; // ecx
  __int64 v13; // r14
  int v14; // edx
  int v15; // r8d
  _QWORD *v16; // rdx
  PVOID CallersAddress; // [rsp+80h] [rbp+8h] BYREF
  KIRQL Irql; // [rsp+88h] [rbp+10h] BYREF

  v3 = *a1;
  v5 = a1[1];
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
  {
    WPP_SF_sqd(
      WPP_GLOBAL_Control->AttachedDevice,
      48,
      a3,
      (unsigned int)"TdxDisconnectConnectionTlRequestComplete",
      v3,
      a2);
  }
  v7 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v3 + 8));
  v8 = 1;
  v9 = *(unsigned int *)(v3 + 76);
  v10 = v7;
  if ( (_DWORD)v9 != 5 )
    v8 = (*(_DWORD *)v3 & 0x20) != 0;
  if ( v8 )
  {
    *(_DWORD *)(v3 + 76) = 7;
    *(_QWORD *)(v5 + 56) = a3;
    *(_DWORD *)(v5 + 48) = a2;
    v16 = *(_QWORD **)(v3 + 104);
    if ( *v16 != v3 + 96 )
      __fastfail(3u);
    *(_QWORD *)(v5 + 176) = v16;
    *(_QWORD *)(v5 + 168) = v3 + 96;
    *v16 = v5 + 168;
    *(_QWORD *)(v3 + 104) = v5 + 168;
    if ( (*(_DWORD *)v3 & 0x200) != 0 )
    {
      KeReleaseSpinLock((PKSPIN_LOCK)(v3 + 8), v7);
    }
    else
    {
      LOBYTE(v9) = 1;
      *(_DWORD *)v3 |= 0x200u;
      TdxDecrementTlEndpointReference(v3, v7, v9);
    }
  }
  else
  {
    if ( (int)v9 <= 4 )
      *(_DWORD *)(v3 + 76) = 6;
    *(_QWORD *)(v5 + 56) = a3;
    *(_DWORD *)(v5 + 48) = a2;
    if ( !_InterlockedExchange64((volatile __int64 *)(v5 + 104), 0) )
    {
      Irql = 0;
      KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(v3 + 8));
      IoAcquireCancelSpinLock(&Irql);
      IoReleaseCancelSpinLock(Irql);
      KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(v3 + 8));
    }
    KeReleaseSpinLock((PKSPIN_LOCK)(v3 + 8), v10);
    IofCompleteRequest((PIRP)v5, 2);
    v11 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v3 + 368));
    v12 = *(_DWORD *)(v3 + 16) - 1;
    v13 = v3 + 32LL * *(unsigned int *)(v3 + 632);
    CallersAddress = 0;
    *(_DWORD *)(v13 + 400) = v12;
    *(_QWORD *)(v13 + 376) = "TdxDisconnectConnectionTlRequestComplete";
    *(_DWORD *)(v13 + 384) = 2333;
    RtlGetCallersAddress(&CallersAddress, (PVOID *)(v13 + 392));
    *(_DWORD *)(v3 + 632) = ((unsigned __int8)*(_DWORD *)(v3 + 632) + 1) & 7;
    KeReleaseSpinLock((PKSPIN_LOCK)(v3 + 368), v11);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
    {
      WPP_SF_qdssD(
        WPP_GLOBAL_Control->AttachedDevice,
        v14,
        v15,
        v3,
        *(_DWORD *)(v13 + 400),
        (__int64)"--",
        (__int64)"TdxDisconnectConnectionTlRequestComplete",
        29);
    }
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v3 + 16), 0xFFFFFFFF) == 1 )
      TdxCleanupObjectHeader(v3);
  }
}

```

## disassembly

```asm
0x14000a5f0  mov     [rsp+arg_10], rbx
0x14000a5f5  push    rbp
0x14000a5f6  push    rsi
0x14000a5f7  push    rdi
0x14000a5f8  push    r12
0x14000a5fa  push    r13
0x14000a5fc  push    r14
0x14000a5fe  push    r15
0x14000a600  sub     rsp, 40h
0x14000a604  mov     rbx, [rcx]
0x14000a607  mov     rbp, r8
0x14000a60a  mov     rdi, [rcx+8]
0x14000a60e  mov     esi, edx
0x14000a610  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a617  lea     r12, WPP_GLOBAL_Control
0x14000a61e  lea     r13, aTdxdisconnectc; "TdxDisconnectConnectionTlRequestComplet"...
0x14000a625  cmp     rcx, r12
0x14000a628  jz      short loc_14000A634
0x14000a62a  cmp     byte ptr [rcx+29h], 4
0x14000a62e  jnb     loc_14000A7E8
0x14000a634  lea     rcx, [rbx+8]; SpinLock
0x14000a638  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000a63f  nop     dword ptr [rax+rax+00h]
0x14000a644  mov     ecx, [rbx]
0x14000a646  mov     edx, 1
0x14000a64b  mov     r8d, [rbx+4Ch]
0x14000a64f  movzx   r15d, al
0x14000a653  shr     ecx, 5
0x14000a656  and     cl, 1
0x14000a659  cmp     r8d, 5
0x14000a65d  movzx   ecx, cl
0x14000a660  cmovnz  edx, ecx
0x14000a663  test    dl, dl
0x14000a665  jnz     loc_14000A787
0x14000a66b  cmp     r8d, 4
0x14000a66f  jle     loc_14000A81B
0x14000a675  mov     [rdi+38h], rbp
0x14000a679  xor     eax, eax
0x14000a67b  mov     [rdi+30h], esi
0x14000a67e  xchg    rax, [rdi+68h]
0x14000a682  test    rax, rax
0x14000a685  jz      loc_14000A827
0x14000a68b  movzx   edx, r15b; NewIrql
0x14000a68f  lea     rcx, [rbx+8]; SpinLock
0x14000a693  call    cs:__imp_KeReleaseSpinLock
0x14000a69a  nop     dword ptr [rax+rax+00h]
0x14000a69f  mov     dl, 2; PriorityBoost
0x14000a6a1  mov     rcx, rdi; Irp
0x14000a6a4  call    cs:__imp_IofCompleteRequest
0x14000a6ab  nop     dword ptr [rax+rax+00h]
0x14000a6b0  lea     rcx, [rbx+170h]; SpinLock
0x14000a6b7  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000a6be  nop     dword ptr [rax+rax+00h]
0x14000a6c3  mov     ecx, [rbx+10h]
0x14000a6c6  movzx   edi, al
0x14000a6c9  mov     r14d, [rbx+278h]
0x14000a6d0  dec     ecx
0x14000a6d2  shl     r14, 5
0x14000a6d6  add     r14, rbx
0x14000a6d9  mov     [rsp+78h+CallersAddress], 0
0x14000a6e5  mov     [r14+190h], ecx
0x14000a6ec  lea     rdx, [r14+188h]; CallersCaller
0x14000a6f3  lea     rcx, [rsp+78h+CallersAddress]; CallersAddress
0x14000a6fb  mov     [r14+178h], r13
0x14000a702  mov     dword ptr [r14+180h], 91Dh
0x14000a70d  call    cs:__imp_RtlGetCallersAddress
0x14000a714  nop     dword ptr [rax+rax+00h]
0x14000a719  mov     eax, [rbx+278h]
0x14000a71f  lea     rcx, [rbx+170h]; SpinLock
0x14000a726  inc     eax
0x14000a728  movzx   edx, dil; NewIrql
0x14000a72c  and     eax, 7
0x14000a72f  mov     [rbx+278h], eax
0x14000a735  call    cs:__imp_KeReleaseSpinLock
0x14000a73c  nop     dword ptr [rax+rax+00h]
0x14000a741  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a748  cmp     rcx, r12
0x14000a74b  jz      short loc_14000A757
0x14000a74d  cmp     byte ptr [rcx+29h], 5
0x14000a751  jnb     loc_14000A87C
0x14000a757  mov     eax, 0FFFFFFFFh
0x14000a75c  lock xadd [rbx+10h], eax
0x14000a761  cmp     eax, 1
0x14000a764  jnz     short loc_14000A76E
0x14000a766  mov     rcx, rbx
0x14000a769  call    TdxCleanupObjectHeader
0x14000a76e  mov     rbx, [rsp+78h+arg_10]
0x14000a776  add     rsp, 40h
0x14000a77a  pop     r15
0x14000a77c  pop     r14
0x14000a77e  pop     r13
0x14000a780  pop     r12
0x14000a782  pop     rdi
0x14000a783  pop     rsi
0x14000a784  pop     rbp
0x14000a785  retn
0x14000a787  mov     dword ptr [rbx+4Ch], 7
0x14000a78e  lea     rcx, [rbx+60h]
0x14000a792  mov     [rdi+38h], rbp
0x14000a796  mov     [rdi+30h], esi
0x14000a799  mov     rdx, [rcx+8]
0x14000a79d  cmp     [rdx], rcx
0x14000a7a0  jnz     short loc_14000A814
0x14000a7a2  lea     rax, [rdi+0A8h]
0x14000a7a9  mov     [rax+8], rdx
0x14000a7ad  mov     [rax], rcx
0x14000a7b0  mov     [rdx], rax
0x14000a7b3  movzx   edx, r15b; NewIrql
0x14000a7b7  mov     [rcx+8], rax
0x14000a7bb  mov     eax, [rbx]
0x14000a7bd  bt      eax, 9
0x14000a7c1  jb      short loc_14000A7D6
0x14000a7c3  bts     eax, 9
0x14000a7c7  mov     r8b, 1
0x14000a7ca  mov     rcx, rbx
0x14000a7cd  mov     [rbx], eax
0x14000a7cf  call    TdxDecrementTlEndpointReference
0x14000a7d4  jmp     short loc_14000A76E
0x14000a7d6  lea     rcx, [rbx+8]; SpinLock
0x14000a7da  call    cs:__imp_KeReleaseSpinLock
0x14000a7e1  nop     dword ptr [rax+rax+00h]
0x14000a7e6  jmp     short loc_14000A76E
0x14000a7e8  test    dword ptr [rcx+2Ch], 200h
0x14000a7ef  jz      loc_14000A634
0x14000a7f5  mov     rcx, [rcx+18h]
0x14000a7f9  mov     edx, 30h ; '0'
0x14000a7fe  mov     dword ptr [rsp+78h+var_50], esi
0x14000a802  mov     r9, r13
0x14000a805  mov     [rsp+78h+var_58], rbx
0x14000a80a  call    WPP_SF_sqd
0x14000a80f  jmp     loc_14000A634
0x14000a814  mov     ecx, 3
0x14000a819  int     29h; Win8: RtlFailFast(ecx)
0x14000a81b  mov     dword ptr [rbx+4Ch], 6
0x14000a822  jmp     loc_14000A675
0x14000a827  lea     rcx, [rbx+8]; SpinLock
0x14000a82b  mov     [rsp+78h+Irql], 0
0x14000a833  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x14000a83a  nop     dword ptr [rax+rax+00h]
0x14000a83f  lea     rcx, [rsp+78h+Irql]; Irql
0x14000a847  call    cs:__imp_IoAcquireCancelSpinLock
0x14000a84e  nop     dword ptr [rax+rax+00h]
0x14000a853  movzx   ecx, [rsp+78h+Irql]; Irql
0x14000a85b  call    cs:__imp_IoReleaseCancelSpinLock
0x14000a862  nop     dword ptr [rax+rax+00h]
0x14000a867  lea     rcx, [rbx+8]; SpinLock
0x14000a86b  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x14000a872  nop     dword ptr [rax+rax+00h]
0x14000a877  jmp     loc_14000A68B
0x14000a87c  test    dword ptr [rcx+2Ch], 200h
0x14000a883  jz      loc_14000A757
0x14000a889  mov     rcx, [rcx+18h]
0x14000a88d  lea     rax, asc_14001AAE0; "--"
0x14000a894  mov     [rsp+78h+var_40], 91Dh
0x14000a89c  mov     r9, rbx
0x14000a89f  mov     [rsp+78h+var_48], r13
0x14000a8a4  mov     [rsp+78h+var_50], rax
0x14000a8a9  mov     eax, [r14+190h]
0x14000a8b0  mov     dword ptr [rsp+78h+var_58], eax
0x14000a8b4  call    WPP_SF_qdssD
0x14000a8b9  jmp     loc_14000A757
```
