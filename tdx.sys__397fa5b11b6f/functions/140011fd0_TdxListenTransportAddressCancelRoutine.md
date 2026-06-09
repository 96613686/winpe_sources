# TdxListenTransportAddressCancelRoutine

- ea: `0x140011fd0`
- end: `0x140012199`
- name: `TdxListenTransportAddressCancelRoutine`
- size: `457`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1400047d0`
- `0x1400054ec`
- `0x140011fd0`
- `0x140012a8c`

## import_xrefs

- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140012045`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140012045`
- `ntoskrnl!IofCompleteRequest` at `0x140012117`
- `ntoskrnl!IofCompleteRequest` at `0x140012117`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140012002`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140012028`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140012037`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140012002`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140012028`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140012037`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140012015`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400120e5`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140012159`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140012015`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400120e5`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140012159`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400120f7`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001216b`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400120f7`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001216b`

## pseudocode

```c
void __fastcall TdxListenTransportAddressCancelRoutine(__int64 a1, IRP *a2)
{
  union _IRP::$66699B8BF83DC91F51A70E4C6E3F33A6 *p_Tail; // r12
  KIRQL CancelIrql; // r13
  __int64 FsContext; // rbx
  KSPIN_LOCK *v6; // rsi
  IRP *v7; // rbp
  KSPIN_LOCK *v8; // rax
  struct _LIST_ENTRY *Flink; // rdx
  struct _LIST_ENTRY *Blink; // r8
  KSPIN_LOCK *v11; // r9
  KSPIN_LOCK **v12; // r8

  p_Tail = &a2->Tail;
  CancelIrql = a2->CancelIrql;
  FsContext = (__int64)a2->Tail.Overlay.CurrentStackLocation->FileObject->FsContext;
  KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(FsContext + 8));
  v6 = *(KSPIN_LOCK **)(FsContext + 88);
  KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(FsContext + 8));
  KeAcquireSpinLockAtDpcLevel(v6 + 1);
  KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(FsContext + 8));
  IoReleaseCancelSpinLock(2u);
  v7 = (IRP *)v6[67];
  v8 = (KSPIN_LOCK *)v6[45];
  v6[67] = 0;
  while ( 1 )
  {
    if ( v8 == v6 + 45 )
    {
      KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(FsContext + 8));
      KeReleaseSpinLock(v6 + 1, CancelIrql);
      goto LABEL_15;
    }
    if ( v8 == (KSPIN_LOCK *)p_Tail )
      break;
    v8 = (KSPIN_LOCK *)*v8;
  }
  Flink = a2->Tail.Overlay.ListEntry.Flink;
  if ( (PVOID *)Flink->Blink != &a2->Tail.CompletionKey + 6
    || (Blink = a2->Tail.Overlay.ListEntry.Blink, (PVOID *)Blink->Flink != &a2->Tail.CompletionKey + 6)
    || (Blink->Flink = Flink, Flink->Blink = Blink, v11 = (KSPIN_LOCK *)*v8, *(KSPIN_LOCK **)(*v8 + 8) != v8)
    || (v12 = (KSPIN_LOCK **)v8[1], *v12 != v8) )
  {
    __fastfail(3u);
  }
  *v12 = v11;
  v11[1] = (KSPIN_LOCK)v12;
  if ( *(_QWORD *)(FsContext + 304) == FsContext + 304 && *(_DWORD *)(FsContext + 76) == 1 )
    *(_DWORD *)(FsContext + 76) = 0;
  KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(FsContext + 8));
  KeReleaseSpinLock(v6 + 1, CancelIrql);
  a2->IoStatus.Status = -1073741536;
  a2->IoStatus.Information = 0;
  IofCompleteRequest(a2, 2);
  DbgTdxDereferenceTransportAddress(v6, "minio\\netio\\session\\tdi\\address.c", 3570);
  DbgTdxDereferenceConnection(FsContext, (__int64)"TdxListenTransportAddressCancelRoutine", 3571);
LABEL_15:
  if ( v7 )
    TdxReissueConnectWhileListenRequests(v7, (__int64)v6);
}

```

## disassembly

```asm
0x140011fd0  push    rbx
0x140011fd2  push    rbp
0x140011fd3  push    rsi
0x140011fd4  push    rdi
0x140011fd5  push    r12
0x140011fd7  push    r13
0x140011fd9  push    r14
0x140011fdb  push    r15
0x140011fdd  sub     rsp, 28h
0x140011fe1  mov     rax, [rdx+0B8h]
0x140011fe8  lea     r12, [rdx+78h]
0x140011fec  mov     r13b, [rdx+45h]
0x140011ff0  mov     rdi, rdx
0x140011ff3  mov     rcx, [rax+30h]
0x140011ff7  mov     rbx, [rcx+18h]
0x140011ffb  lea     r14, [rbx+8]
0x140011fff  mov     rcx, r14; SpinLock
0x140012002  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x140012009  nop     dword ptr [rax+rax+00h]
0x14001200e  mov     rsi, [rbx+58h]
0x140012012  mov     rcx, r14; SpinLock
0x140012015  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x14001201c  nop     dword ptr [rax+rax+00h]
0x140012021  lea     r15, [rsi+8]
0x140012025  mov     rcx, r15; SpinLock
0x140012028  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x14001202f  nop     dword ptr [rax+rax+00h]
0x140012034  mov     rcx, r14; SpinLock
0x140012037  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x14001203e  nop     dword ptr [rax+rax+00h]
0x140012043  mov     cl, 2; Irql
0x140012045  call    cs:__imp_IoReleaseCancelSpinLock
0x14001204c  nop     dword ptr [rax+rax+00h]
0x140012051  mov     rbp, [rsi+218h]
0x140012058  lea     rcx, [rsi+168h]
0x14001205f  mov     rax, [rcx]
0x140012062  mov     qword ptr [rsi+218h], 0
0x14001206d  cmp     rax, rcx
0x140012070  jz      loc_140012156
0x140012076  cmp     rax, r12
0x140012079  jz      short loc_140012080
0x14001207b  mov     rax, [rax]
0x14001207e  jmp     short loc_14001206D
0x140012080  lea     rcx, [rdi+0A8h]
0x140012087  mov     rdx, [rcx]
0x14001208a  cmp     [rdx+8], rcx
0x14001208e  jnz     loc_14001214F
0x140012094  mov     r8, [rcx+8]
0x140012098  cmp     [r8], rcx
0x14001209b  jnz     loc_14001214F
0x1400120a1  mov     [r8], rdx
0x1400120a4  mov     [rdx+8], r8
0x1400120a8  mov     r9, [rax]
0x1400120ab  cmp     [r9+8], rax
0x1400120af  jnz     loc_14001214F
0x1400120b5  mov     r8, [rax+8]
0x1400120b9  cmp     [r8], rax
0x1400120bc  jnz     loc_14001214F
0x1400120c2  mov     [r8], r9
0x1400120c5  lea     rax, [rbx+130h]
0x1400120cc  mov     [r9+8], r8
0x1400120d0  cmp     [rax], rax
0x1400120d3  jnz     short loc_1400120E2
0x1400120d5  cmp     dword ptr [rbx+4Ch], 1
0x1400120d9  jnz     short loc_1400120E2
0x1400120db  mov     dword ptr [rbx+4Ch], 0
0x1400120e2  mov     rcx, r14; SpinLock
0x1400120e5  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x1400120ec  nop     dword ptr [rax+rax+00h]
0x1400120f1  mov     dl, r13b; NewIrql
0x1400120f4  mov     rcx, r15; SpinLock
0x1400120f7  call    cs:__imp_KeReleaseSpinLock
0x1400120fe  nop     dword ptr [rax+rax+00h]
0x140012103  mov     dl, 2; PriorityBoost
0x140012105  mov     dword ptr [rdi+30h], 0C0000120h
0x14001210c  mov     rcx, rdi; Irp
0x14001210f  mov     qword ptr [rdi+38h], 0
0x140012117  call    cs:__imp_IofCompleteRequest
0x14001211e  nop     dword ptr [rax+rax+00h]
0x140012123  mov     r8d, 0DF2h
0x140012129  lea     rdx, aMinioNetioSess_2; "minio\\netio\\session\\tdi\\address.c"
0x140012130  mov     rcx, rsi
0x140012133  call    DbgTdxDereferenceTransportAddress
0x140012138  mov     r8d, 0DF3h
0x14001213e  lea     rdx, aTdxlistentrans; "TdxListenTransportAddressCancelRoutine"
0x140012145  mov     rcx, rbx
0x140012148  call    DbgTdxDereferenceConnection
0x14001214d  jmp     short loc_140012177
0x14001214f  mov     ecx, 3
0x140012154  int     29h; Win8: RtlFailFast(ecx)
0x140012156  mov     rcx, r14; SpinLock
0x140012159  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140012160  nop     dword ptr [rax+rax+00h]
0x140012165  mov     dl, r13b; NewIrql
0x140012168  mov     rcx, r15; SpinLock
0x14001216b  call    cs:__imp_KeReleaseSpinLock
0x140012172  nop     dword ptr [rax+rax+00h]
0x140012177  test    rbp, rbp
0x14001217a  jz      short loc_140012187
0x14001217c  mov     rdx, rsi
0x14001217f  mov     rcx, rbp; Irp
0x140012182  call    TdxReissueConnectWhileListenRequests
0x140012187  add     rsp, 28h
0x14001218b  pop     r15
0x14001218d  pop     r14
0x14001218f  pop     r13
0x140012191  pop     r12
0x140012193  pop     rdi
0x140012194  pop     rsi
0x140012195  pop     rbp
0x140012196  pop     rbx
0x140012197  retn
```
