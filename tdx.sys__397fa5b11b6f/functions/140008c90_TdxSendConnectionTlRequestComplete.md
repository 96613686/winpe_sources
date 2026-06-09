# TdxSendConnectionTlRequestComplete

- ea: `0x140008c90`
- end: `0x140008edd`
- name: `TdxSendConnectionTlRequestComplete`
- size: `589`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140006db0`

## callees

- `0x140008c50`
- `0x140008c90`
- `0x140013af4`
- `0x140013ffc`

## import_xrefs

- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140008e72`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140008e72`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140008e5e`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140008e5e`
- `ntoskrnl!IofCompleteRequest` at `0x140008de3`
- `ntoskrnl!IofCompleteRequest` at `0x140008de3`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140008e82`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140008e82`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140008e4a`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140008e4a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140008cb5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140008d0b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140008cb5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140008d0b`
- `ntoskrnl!RtlGetCallersAddress` at `0x140008d6c`
- `ntoskrnl!RtlGetCallersAddress` at `0x140008d6c`
- `ntoskrnl!KeReleaseSpinLock` at `0x140008cf8`
- `ntoskrnl!KeReleaseSpinLock` at `0x140008d94`
- `ntoskrnl!KeReleaseSpinLock` at `0x140008cf8`
- `ntoskrnl!KeReleaseSpinLock` at `0x140008d94`

## string_xrefs

- `0x140008d24`: `TdxSendConnectionTlRequestComplete`
- `0x140008e19`: `TdxSendConnectionTlRequestComplete`
- `0x140008ea4`: `TdxSendConnectionTlRequestComplete`

## pseudocode

```c
void __fastcall TdxSendConnectionTlRequestComplete(_QWORD *a1, int a2, __int64 a3)
{
  __int64 v3; // rbx
  __int64 v5; // rbp
  KIRQL v7; // si
  int v8; // r8d
  KIRQL v9; // di
  int v10; // ecx
  __int64 v11; // r12
  int v12; // edx
  int v13; // r8d
  PVOID CallersAddress; // [rsp+80h] [rbp+8h] BYREF
  KIRQL Irql; // [rsp+88h] [rbp+10h] BYREF

  v3 = *a1;
  v5 = a1[1];
  v7 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(*a1 + 8LL));
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
  {
    WPP_SF_sqqd(
      WPP_GLOBAL_Control->AttachedDevice,
      50,
      v8,
      (unsigned int)"TdxSendConnectionTlRequestComplete",
      v3,
      v5,
      a3);
  }
  if ( !_InterlockedExchange64((volatile __int64 *)(v5 + 104), 0) )
  {
    Irql = 0;
    KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(v3 + 8));
    IoAcquireCancelSpinLock(&Irql);
    IoReleaseCancelSpinLock(Irql);
    KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(v3 + 8));
  }
  KeReleaseSpinLock((PKSPIN_LOCK)(v3 + 8), v7);
  v9 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v3 + 368));
  v10 = *(_DWORD *)(v3 + 16) - 1;
  v11 = v3 + 32LL * *(unsigned int *)(v3 + 632);
  CallersAddress = 0;
  *(_DWORD *)(v11 + 400) = v10;
  *(_QWORD *)(v11 + 376) = "TdxSendConnectionTlRequestComplete";
  *(_DWORD *)(v11 + 384) = 2537;
  RtlGetCallersAddress(&CallersAddress, (PVOID *)(v11 + 392));
  *(_DWORD *)(v3 + 632) = ((unsigned __int8)*(_DWORD *)(v3 + 632) + 1) & 7;
  KeReleaseSpinLock((PKSPIN_LOCK)(v3 + 368), v9);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
  {
    WPP_SF_qdssD(
      WPP_GLOBAL_Control->AttachedDevice,
      v12,
      v13,
      v3,
      *(_DWORD *)(v11 + 400),
      (__int64)"--",
      (__int64)"TdxSendConnectionTlRequestComplete",
      233);
  }
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v3 + 16), 0xFFFFFFFF) == 1 )
    TdxCleanupObjectHeader(v3);
  *(_DWORD *)(v5 + 48) = a2;
  if ( a2 < 0 )
    a3 = 0;
  *(_QWORD *)(v5 + 56) = a3;
  IofCompleteRequest((PIRP)v5, 2);
}

```

## disassembly

```asm
0x140008c90  mov     [rsp+arg_10], rbx
0x140008c95  push    rbp
0x140008c96  push    rsi
0x140008c97  push    rdi
0x140008c98  push    r12
0x140008c9a  push    r13
0x140008c9c  push    r14
0x140008c9e  push    r15
0x140008ca0  sub     rsp, 40h
0x140008ca4  mov     rbx, [rcx]
0x140008ca7  mov     r14, r8
0x140008caa  mov     rbp, [rcx+8]
0x140008cae  mov     r15d, edx
0x140008cb1  lea     rcx, [rbx+8]; SpinLock
0x140008cb5  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140008cbc  nop     dword ptr [rax+rax+00h]
0x140008cc1  movzx   esi, al
0x140008cc4  mov     rcx, cs:WPP_GLOBAL_Control
0x140008ccb  lea     r13, WPP_GLOBAL_Control
0x140008cd2  cmp     rcx, r13
0x140008cd5  jz      short loc_140008CE1
0x140008cd7  cmp     byte ptr [rcx+29h], 5
0x140008cdb  jnb     loc_140008E08
0x140008ce1  xor     eax, eax
0x140008ce3  xchg    rax, [rbp+68h]
0x140008ce7  test    rax, rax
0x140008cea  jz      loc_140008E3E
0x140008cf0  movzx   edx, sil; NewIrql
0x140008cf4  lea     rcx, [rbx+8]; SpinLock
0x140008cf8  call    cs:__imp_KeReleaseSpinLock
0x140008cff  nop     dword ptr [rax+rax+00h]
0x140008d04  lea     rcx, [rbx+170h]; SpinLock
0x140008d0b  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140008d12  nop     dword ptr [rax+rax+00h]
0x140008d17  mov     ecx, [rbx+10h]
0x140008d1a  movzx   edi, al
0x140008d1d  mov     r12d, [rbx+278h]
0x140008d24  lea     rax, aTdxsendconnect; "TdxSendConnectionTlRequestComplete"
0x140008d2b  dec     ecx
0x140008d2d  shl     r12, 5
0x140008d31  add     r12, rbx
0x140008d34  mov     [rsp+78h+CallersAddress], 0
0x140008d40  mov     [r12+190h], ecx
0x140008d48  lea     rdx, [r12+188h]; CallersCaller
0x140008d50  lea     rcx, [rsp+78h+CallersAddress]; CallersAddress
0x140008d58  mov     [r12+178h], rax
0x140008d60  mov     dword ptr [r12+180h], 9E9h
0x140008d6c  call    cs:__imp_RtlGetCallersAddress
0x140008d73  nop     dword ptr [rax+rax+00h]
0x140008d78  mov     eax, [rbx+278h]
0x140008d7e  lea     rcx, [rbx+170h]; SpinLock
0x140008d85  inc     eax
0x140008d87  movzx   edx, dil; NewIrql
0x140008d8b  and     eax, 7
0x140008d8e  mov     [rbx+278h], eax
0x140008d94  call    cs:__imp_KeReleaseSpinLock
0x140008d9b  nop     dword ptr [rax+rax+00h]
0x140008da0  mov     rcx, cs:WPP_GLOBAL_Control
0x140008da7  cmp     rcx, r13
0x140008daa  jz      short loc_140008DB6
0x140008dac  cmp     byte ptr [rcx+29h], 5
0x140008db0  jnb     loc_140008E93
0x140008db6  mov     eax, 0FFFFFFFFh
0x140008dbb  lock xadd [rbx+10h], eax
0x140008dc0  cmp     eax, 1
0x140008dc3  jnz     short loc_140008DCD
0x140008dc5  mov     rcx, rbx
0x140008dc8  call    TdxCleanupObjectHeader
0x140008dcd  xor     eax, eax
0x140008dcf  mov     [rbp+30h], r15d
0x140008dd3  test    r15d, r15d
0x140008dd6  mov     dl, 2; PriorityBoost
0x140008dd8  mov     rcx, rbp; Irp
0x140008ddb  cmovs   r14, rax
0x140008ddf  mov     [rbp+38h], r14
0x140008de3  call    cs:__imp_IofCompleteRequest
0x140008dea  nop     dword ptr [rax+rax+00h]
0x140008def  mov     rbx, [rsp+78h+arg_10]
0x140008df7  add     rsp, 40h
0x140008dfb  pop     r15
0x140008dfd  pop     r14
0x140008dff  pop     r13
0x140008e01  pop     r12
0x140008e03  pop     rdi
0x140008e04  pop     rsi
0x140008e05  pop     rbp
0x140008e06  retn
0x140008e08  test    dword ptr [rcx+2Ch], 200h
0x140008e0f  jz      loc_140008CE1
0x140008e15  mov     rcx, [rcx+18h]
0x140008e19  lea     r9, aTdxsendconnect; "TdxSendConnectionTlRequestComplete"
0x140008e20  mov     dword ptr [rsp+78h+var_48], r14d
0x140008e25  mov     edx, 32h ; '2'
0x140008e2a  mov     [rsp+78h+var_50], rbp
0x140008e2f  mov     [rsp+78h+var_58], rbx
0x140008e34  call    WPP_SF_sqqd
0x140008e39  jmp     loc_140008CE1
0x140008e3e  lea     rcx, [rbx+8]; SpinLock
0x140008e42  mov     [rsp+78h+Irql], 0
0x140008e4a  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140008e51  nop     dword ptr [rax+rax+00h]
0x140008e56  lea     rcx, [rsp+78h+Irql]; Irql
0x140008e5e  call    cs:__imp_IoAcquireCancelSpinLock
0x140008e65  nop     dword ptr [rax+rax+00h]
0x140008e6a  movzx   ecx, [rsp+78h+Irql]; Irql
0x140008e72  call    cs:__imp_IoReleaseCancelSpinLock
0x140008e79  nop     dword ptr [rax+rax+00h]
0x140008e7e  lea     rcx, [rbx+8]; SpinLock
0x140008e82  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x140008e89  nop     dword ptr [rax+rax+00h]
0x140008e8e  jmp     loc_140008CF0
0x140008e93  test    dword ptr [rcx+2Ch], 200h
0x140008e9a  jz      loc_140008DB6
0x140008ea0  mov     rcx, [rcx+18h]
0x140008ea4  lea     rax, aTdxsendconnect; "TdxSendConnectionTlRequestComplete"
0x140008eab  mov     [rsp+78h+var_40], 9E9h
0x140008eb3  mov     r9, rbx
0x140008eb6  mov     [rsp+78h+var_48], rax
0x140008ebb  lea     rax, asc_14001AAE0; "--"
0x140008ec2  mov     [rsp+78h+var_50], rax
0x140008ec7  mov     eax, [r12+190h]
0x140008ecf  mov     dword ptr [rsp+78h+var_58], eax
0x140008ed3  call    WPP_SF_qdssD
0x140008ed8  jmp     loc_140008DB6
```
