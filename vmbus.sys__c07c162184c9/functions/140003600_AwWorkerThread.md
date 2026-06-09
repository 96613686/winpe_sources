# AwWorkerThread

- ea: `0x140003600`
- end: `0x14000370e`
- name: `AwWorkerThread`
- size: `270`
- prototype: `void __fastcall __noreturn(PRKQUEUE Queue)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140003600`
- `0x140017190`

## import_xrefs

- `ntoskrnl!KeSetActualBasePriorityThread` at `0x140003687`
- `ntoskrnl!KeSetActualBasePriorityThread` at `0x140003687`
- `ntoskrnl!ObfReferenceObject` at `0x1400036df`
- `ntoskrnl!ObfReferenceObject` at `0x1400036df`
- `ntoskrnl!PsTerminateSystemThread` at `0x1400036c4`
- `ntoskrnl!PsTerminateSystemThread` at `0x1400036c4`
- `ntoskrnl!ExReleaseRundownProtection` at `0x1400036b6`
- `ntoskrnl!ExReleaseRundownProtection` at `0x1400036b6`
- `ntoskrnl!KeSetSystemGroupAffinityThread` at `0x14000366d`
- `ntoskrnl!KeSetSystemGroupAffinityThread` at `0x14000366d`
- `ntoskrnl!ObfDereferenceObject` at `0x140003700`
- `ntoskrnl!ObfDereferenceObject` at `0x140003700`
- `ntoskrnl!KeRemoveQueue` at `0x14000369b`
- `ntoskrnl!KeRemoveQueue` at `0x14000369b`
- `ntoskrnl!KeGetProcessorNumberFromIndex` at `0x140003637`
- `ntoskrnl!KeGetProcessorNumberFromIndex` at `0x140003637`

## pseudocode

```c
void __fastcall __noreturn AwWorkerThread(PRKQUEUE Queue)
{
  ULONG Flink; // ecx
  PLIST_ENTRY v3; // rbp
  struct _LIST_ENTRY *v4; // rsi
  struct _LIST_ENTRY *Blink; // rbx
  struct _LIST_ENTRY *v6; // rdi
  _PROCESSOR_NUMBER ProcNumber; // [rsp+20h] [rbp-58h] BYREF
  _GROUP_AFFINITY Affinity; // [rsp+28h] [rbp-50h] BYREF

  ProcNumber = 0;
  Flink = (ULONG)Queue[1].Header.WaitListHead.Flink;
  Affinity = 0;
  KeGetProcessorNumberFromIndex(Flink, &ProcNumber);
  *(_QWORD *)&Affinity.Group = ProcNumber.Group;
  Affinity.Mask = 1LL << ProcNumber.Number;
  KeSetSystemGroupAffinityThread(&Affinity, 0);
  KeSetActualBasePriorityThread(KeGetCurrentThread(), 12);
  while ( 1 )
  {
    v3 = KeRemoveQueue(Queue, 0, 0);
    if ( v3 == (PLIST_ENTRY)128 )
    {
      ExReleaseRundownProtection((PEX_RUNDOWN_REF)&Queue[1].Header.WaitListHead.Blink);
      PsTerminateSystemThread(0);
    }
    v4 = v3[2].Flink;
    Blink = v3[1].Blink;
    v6 = v3[1].Flink;
    ObfReferenceObject(v4);
    LODWORD(v3[3].Flink) = -1;
    ((void (__fastcall *)(struct _LIST_ENTRY *))v6)(Blink);
    ObfDereferenceObject(v4);
  }
}

```

## disassembly

```asm
0x140003600  push    rbx
0x140003602  push    rbp
0x140003603  push    rsi
0x140003604  push    rdi
0x140003605  push    r14
0x140003607  push    r15
0x140003609  sub     rsp, 48h
0x14000360d  mov     rax, cs:__security_cookie
0x140003614  xor     rax, rsp
0x140003617  mov     [rsp+78h+var_40], rax
0x14000361c  mov     r14, rcx
0x14000361f  mov     dword ptr [rsp+78h+ProcNumber.Group], 0
0x140003627  mov     ecx, [rcx+48h]; ProcIndex
0x14000362a  lea     rdx, [rsp+78h+ProcNumber]; ProcNumber
0x14000362f  xorps   xmm0, xmm0
0x140003632  movups  xmmword ptr [rsp+78h+Affinity.Mask], xmm0
0x140003637  call    cs:__imp_KeGetProcessorNumberFromIndex
0x14000363e  nop     dword ptr [rax+rax+00h]
0x140003643  movzx   eax, [rsp+78h+ProcNumber.Group]
0x140003648  xorps   xmm0, xmm0
0x14000364b  mov     cl, [rsp+78h+ProcNumber.Number]
0x14000364f  xor     edx, edx; PreviousAffinity
0x140003651  movups  xmmword ptr [rsp+78h+Affinity.Mask], xmm0
0x140003656  mov     [rsp+78h+Affinity.Group], ax
0x14000365b  mov     eax, 1
0x140003660  shl     rax, cl
0x140003663  lea     rcx, [rsp+78h+Affinity]; Affinity
0x140003668  mov     [rsp+78h+Affinity.Mask], rax
0x14000366d  call    cs:__imp_KeSetSystemGroupAffinityThread
0x140003674  nop     dword ptr [rax+rax+00h]
0x140003679  mov     rcx, gs:188h
0x140003682  mov     edx, 0Ch
0x140003687  call    cs:__imp_KeSetActualBasePriorityThread
0x14000368e  nop     dword ptr [rax+rax+00h]
0x140003693  xor     r8d, r8d; Timeout
0x140003696  xor     edx, edx; WaitMode
0x140003698  mov     rcx, r14; Queue
0x14000369b  call    cs:__imp_KeRemoveQueue
0x1400036a2  nop     dword ptr [rax+rax+00h]
0x1400036a7  mov     rbp, rax
0x1400036aa  cmp     rax, 80h
0x1400036b0  jnz     short loc_1400036D0
0x1400036b2  lea     rcx, [r14+50h]; RunRef
0x1400036b6  call    cs:__imp_ExReleaseRundownProtection
0x1400036bd  nop     dword ptr [rax+rax+00h]
0x1400036c2  xor     ecx, ecx; ExitStatus
0x1400036c4  call    cs:__imp_PsTerminateSystemThread
0x1400036cb  nop     dword ptr [rax+rax+00h]
0x1400036d0  mov     rsi, [rbp+20h]
0x1400036d4  mov     rbx, [rbp+18h]
0x1400036d8  mov     rcx, rsi; Object
0x1400036db  mov     rdi, [rbp+10h]
0x1400036df  call    cs:__imp_ObfReferenceObject
0x1400036e6  nop     dword ptr [rax+rax+00h]
0x1400036eb  mov     rcx, rbx
0x1400036ee  mov     dword ptr [rbp+30h], 0FFFFFFFFh
0x1400036f5  mov     rax, rdi
0x1400036f8  call    _guard_dispatch_icall
0x1400036fd  mov     rcx, rsi; Object
0x140003700  call    cs:__imp_ObfDereferenceObject
0x140003707  nop     dword ptr [rax+rax+00h]
0x14000370c  jmp     short loc_140003693
```
