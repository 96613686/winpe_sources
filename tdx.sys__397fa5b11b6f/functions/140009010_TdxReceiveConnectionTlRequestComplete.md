# TdxReceiveConnectionTlRequestComplete

- ea: `0x140009010`
- end: `0x140009288`
- name: `TdxReceiveConnectionTlRequestComplete`
- size: `632`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140009ad0`

## callees

- `0x140008c50`
- `0x140009010`
- `0x140013af4`
- `0x140013ffc`

## import_xrefs

- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14000921d`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14000921d`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140009209`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140009209`
- `ntoskrnl!IofCompleteRequest` at `0x140009187`
- `ntoskrnl!IofCompleteRequest` at `0x140009187`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14000922d`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14000922d`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400091f5`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400091f5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140009035`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400090af`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140009035`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400090af`
- `ntoskrnl!RtlGetCallersAddress` at `0x140009110`
- `ntoskrnl!RtlGetCallersAddress` at `0x140009110`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000909c`
- `ntoskrnl!KeReleaseSpinLock` at `0x140009138`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000909c`
- `ntoskrnl!KeReleaseSpinLock` at `0x140009138`

## string_xrefs

- `0x1400090c8`: `TdxReceiveConnectionTlRequestComplete`
- `0x1400091c4`: `TdxReceiveConnectionTlRequestComplete`
- `0x14000924f`: `TdxReceiveConnectionTlRequestComplete`

## pseudocode

```c
void __fastcall TdxReceiveConnectionTlRequestComplete(_QWORD *a1, int a2, unsigned __int64 a3)
{
  __int64 v3; // rbx
  __int64 v5; // rbp
  KIRQL v7; // si
  int v8; // r8d
  unsigned __int64 v9; // rcx
  unsigned __int64 v10; // rax
  unsigned __int64 v11; // rcx
  KIRQL v12; // di
  int v13; // ecx
  __int64 v14; // r12
  int v15; // edx
  int v16; // r8d
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
      53,
      v8,
      (unsigned int)"TdxReceiveConnectionTlRequestComplete",
      v3,
      v5,
      a3);
  }
  if ( a3 )
  {
    v9 = *(_QWORD *)(v3 + 296);
    v10 = a3;
    if ( v9 < a3 )
      v10 = *(_QWORD *)(v3 + 296);
    v11 = v9 - v10;
  }
  else
  {
    v11 = 0;
  }
  *(_QWORD *)(v3 + 296) = v11;
  if ( !_InterlockedExchange64((volatile __int64 *)(v5 + 104), 0) )
  {
    Irql = 0;
    KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(v3 + 8));
    IoAcquireCancelSpinLock(&Irql);
    IoReleaseCancelSpinLock(Irql);
    KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(v3 + 8));
  }
  KeReleaseSpinLock((PKSPIN_LOCK)(v3 + 8), v7);
  v12 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v3 + 368));
  v13 = *(_DWORD *)(v3 + 16) - 1;
  v14 = v3 + 32LL * *(unsigned int *)(v3 + 632);
  CallersAddress = 0;
  *(_DWORD *)(v14 + 400) = v13;
  *(_QWORD *)(v14 + 376) = "TdxReceiveConnectionTlRequestComplete";
  *(_DWORD *)(v14 + 384) = 2782;
  RtlGetCallersAddress(&CallersAddress, (PVOID *)(v14 + 392));
  *(_DWORD *)(v3 + 632) = ((unsigned __int8)*(_DWORD *)(v3 + 632) + 1) & 7;
  KeReleaseSpinLock((PKSPIN_LOCK)(v3 + 368), v12);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
  {
    WPP_SF_qdssD(
      WPP_GLOBAL_Control->AttachedDevice,
      v15,
      v16,
      v3,
      *(_DWORD *)(v14 + 400),
      (__int64)"--",
      (__int64)"TdxReceiveConnectionTlRequestComplete",
      222);
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
0x140009010  mov     [rsp+arg_10], rbx
0x140009015  push    rbp
0x140009016  push    rsi
0x140009017  push    rdi
0x140009018  push    r12
0x14000901a  push    r13
0x14000901c  push    r14
0x14000901e  push    r15
0x140009020  sub     rsp, 40h
0x140009024  mov     rbx, [rcx]
0x140009027  mov     r14, r8
0x14000902a  mov     rbp, [rcx+8]
0x14000902e  mov     r15d, edx
0x140009031  lea     rcx, [rbx+8]; SpinLock
0x140009035  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000903c  nop     dword ptr [rax+rax+00h]
0x140009041  movzx   esi, al
0x140009044  mov     rcx, cs:WPP_GLOBAL_Control
0x14000904b  lea     r13, WPP_GLOBAL_Control
0x140009052  cmp     rcx, r13
0x140009055  jz      short loc_140009061
0x140009057  cmp     byte ptr [rcx+29h], 5
0x14000905b  jnb     loc_1400091B3
0x140009061  test    r14, r14
0x140009064  jz      loc_1400091AC
0x14000906a  mov     rcx, [rbx+128h]
0x140009071  mov     rax, r14
0x140009074  cmp     rcx, r14
0x140009077  cmovb   rax, rcx
0x14000907b  sub     rcx, rax
0x14000907e  xor     eax, eax
0x140009080  mov     [rbx+128h], rcx
0x140009087  xchg    rax, [rbp+68h]
0x14000908b  test    rax, rax
0x14000908e  jz      loc_1400091E9
0x140009094  movzx   edx, sil; NewIrql
0x140009098  lea     rcx, [rbx+8]; SpinLock
0x14000909c  call    cs:__imp_KeReleaseSpinLock
0x1400090a3  nop     dword ptr [rax+rax+00h]
0x1400090a8  lea     rcx, [rbx+170h]; SpinLock
0x1400090af  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400090b6  nop     dword ptr [rax+rax+00h]
0x1400090bb  mov     ecx, [rbx+10h]
0x1400090be  movzx   edi, al
0x1400090c1  mov     r12d, [rbx+278h]
0x1400090c8  lea     rax, aTdxreceiveconn_2; "TdxReceiveConnectionTlRequestComplete"
0x1400090cf  dec     ecx
0x1400090d1  shl     r12, 5
0x1400090d5  add     r12, rbx
0x1400090d8  mov     [rsp+78h+CallersAddress], 0
0x1400090e4  mov     [r12+190h], ecx
0x1400090ec  lea     rdx, [r12+188h]; CallersCaller
0x1400090f4  lea     rcx, [rsp+78h+CallersAddress]; CallersAddress
0x1400090fc  mov     [r12+178h], rax
0x140009104  mov     dword ptr [r12+180h], 0ADEh
0x140009110  call    cs:__imp_RtlGetCallersAddress
0x140009117  nop     dword ptr [rax+rax+00h]
0x14000911c  mov     eax, [rbx+278h]
0x140009122  lea     rcx, [rbx+170h]; SpinLock
0x140009129  inc     eax
0x14000912b  movzx   edx, dil; NewIrql
0x14000912f  and     eax, 7
0x140009132  mov     [rbx+278h], eax
0x140009138  call    cs:__imp_KeReleaseSpinLock
0x14000913f  nop     dword ptr [rax+rax+00h]
0x140009144  mov     rcx, cs:WPP_GLOBAL_Control
0x14000914b  cmp     rcx, r13
0x14000914e  jz      short loc_14000915A
0x140009150  cmp     byte ptr [rcx+29h], 5
0x140009154  jnb     loc_14000923E
0x14000915a  mov     eax, 0FFFFFFFFh
0x14000915f  lock xadd [rbx+10h], eax
0x140009164  cmp     eax, 1
0x140009167  jnz     short loc_140009171
0x140009169  mov     rcx, rbx
0x14000916c  call    TdxCleanupObjectHeader
0x140009171  xor     eax, eax
0x140009173  mov     [rbp+30h], r15d
0x140009177  test    r15d, r15d
0x14000917a  mov     dl, 2; PriorityBoost
0x14000917c  mov     rcx, rbp; Irp
0x14000917f  cmovs   r14, rax
0x140009183  mov     [rbp+38h], r14
0x140009187  call    cs:__imp_IofCompleteRequest
0x14000918e  nop     dword ptr [rax+rax+00h]
0x140009193  mov     rbx, [rsp+78h+arg_10]
0x14000919b  add     rsp, 40h
0x14000919f  pop     r15
0x1400091a1  pop     r14
0x1400091a3  pop     r13
0x1400091a5  pop     r12
0x1400091a7  pop     rdi
0x1400091a8  pop     rsi
0x1400091a9  pop     rbp
0x1400091aa  retn
0x1400091ac  xor     ecx, ecx
0x1400091ae  jmp     loc_14000907E
0x1400091b3  test    dword ptr [rcx+2Ch], 200h
0x1400091ba  jz      loc_140009061
0x1400091c0  mov     rcx, [rcx+18h]
0x1400091c4  lea     r9, aTdxreceiveconn_2; "TdxReceiveConnectionTlRequestComplete"
0x1400091cb  mov     dword ptr [rsp+78h+var_48], r14d
0x1400091d0  mov     edx, 35h ; '5'
0x1400091d5  mov     [rsp+78h+var_50], rbp
0x1400091da  mov     [rsp+78h+var_58], rbx
0x1400091df  call    WPP_SF_sqqd
0x1400091e4  jmp     loc_140009061
0x1400091e9  lea     rcx, [rbx+8]; SpinLock
0x1400091ed  mov     [rsp+78h+Irql], 0
0x1400091f5  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x1400091fc  nop     dword ptr [rax+rax+00h]
0x140009201  lea     rcx, [rsp+78h+Irql]; Irql
0x140009209  call    cs:__imp_IoAcquireCancelSpinLock
0x140009210  nop     dword ptr [rax+rax+00h]
0x140009215  movzx   ecx, [rsp+78h+Irql]; Irql
0x14000921d  call    cs:__imp_IoReleaseCancelSpinLock
0x140009224  nop     dword ptr [rax+rax+00h]
0x140009229  lea     rcx, [rbx+8]; SpinLock
0x14000922d  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x140009234  nop     dword ptr [rax+rax+00h]
0x140009239  jmp     loc_140009094
0x14000923e  test    dword ptr [rcx+2Ch], 200h
0x140009245  jz      loc_14000915A
0x14000924b  mov     rcx, [rcx+18h]
0x14000924f  lea     rax, aTdxreceiveconn_2; "TdxReceiveConnectionTlRequestComplete"
0x140009256  mov     [rsp+78h+var_40], 0ADEh
0x14000925e  mov     r9, rbx
0x140009261  mov     [rsp+78h+var_48], rax
0x140009266  lea     rax, asc_14001AAE0; "--"
0x14000926d  mov     [rsp+78h+var_50], rax
0x140009272  mov     eax, [r12+190h]
0x14000927a  mov     dword ptr [rsp+78h+var_58], eax
0x14000927e  call    WPP_SF_qdssD
0x140009283  jmp     loc_14000915A
```
