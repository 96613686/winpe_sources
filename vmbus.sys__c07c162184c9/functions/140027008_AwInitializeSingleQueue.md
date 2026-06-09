# AwInitializeSingleQueue

- ea: `0x140027008`
- end: `0x1400271a4`
- name: `AwInitializeSingleQueue`
- size: `412`
- prototype: `__int64 __fastcall(PRKQUEUE Queue, ULONG ProcIndex)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140027250`

## callees

- `0x140017000`
- `0x140017540`
- `0x140027008`
- `0x140027214`

## import_xrefs

- `ntoskrnl!ExAcquireRundownProtection` at `0x1400270c0`
- `ntoskrnl!ExAcquireRundownProtection` at `0x1400270c0`
- `ntoskrnl!ZwClose` at `0x140027141`
- `ntoskrnl!ZwClose` at `0x140027154`
- `ntoskrnl!ZwClose` at `0x140027141`
- `ntoskrnl!ZwClose` at `0x140027154`
- `ntoskrnl!PsCreateSystemThreadEx` at `0x140027107`
- `ntoskrnl!PsCreateSystemThreadEx` at `0x140027107`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140027165`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140027165`
- `ntoskrnl!ExInitializeRundownProtection` at `0x140027072`
- `ntoskrnl!ExInitializeRundownProtection` at `0x140027072`
- `ntoskrnl!KeInitializeQueue` at `0x14002705c`
- `ntoskrnl!KeInitializeQueue` at `0x14002705c`
- `ntoskrnl!ZwSetInformationThread` at `0x14002712b`
- `ntoskrnl!ZwSetInformationThread` at `0x14002712b`
- `ntoskrnl!KeGetProcessorNumberFromIndex` at `0x140027088`
- `ntoskrnl!KeGetProcessorNumberFromIndex` at `0x140027088`

## pseudocode

```c
__int64 __fastcall AwInitializeSingleQueue(PRKQUEUE Queue, ULONG ProcIndex)
{
  unsigned int i; // edi
  NTSTATUS v5; // ebx
  struct _PROCESSOR_NUMBER ProcNumber; // [rsp+50h] [rbp-30h] BYREF
  HANDLE ThreadHandle; // [rsp+58h] [rbp-28h] BYREF
  __int128 ThreadInformation; // [rsp+60h] [rbp-20h] BYREF

  ThreadHandle = 0;
  ProcNumber = 0;
  ThreadInformation = 0;
  memset(Queue, 0, 0x58u);
  KeInitializeQueue(Queue, 1u);
  LODWORD(Queue[1].Header.WaitListHead.Flink) = ProcIndex;
  ExInitializeRundownProtection((PEX_RUNDOWN_REF)&Queue[1].Header.WaitListHead.Blink);
  BYTE4(Queue[1].Header.WaitListHead.Flink) = 1;
  KeGetProcessorNumberFromIndex(ProcIndex, &ProcNumber);
  *((_QWORD *)&ThreadInformation + 1) = ProcNumber.Group;
  *(_QWORD *)&ThreadInformation = 1LL << ProcNumber.Number;
  for ( i = 0; i < 3; ++i )
  {
    ExAcquireRundownProtection((PEX_RUNDOWN_REF)&Queue[1].Header.WaitListHead.Blink);
    v5 = PsCreateSystemThreadEx(&ThreadHandle, 0x1FFFFF, 0, 0, 0, AwWorkerThread, Queue, &ThreadInformation, 0);
    if ( v5 < 0 )
    {
      ExReleaseRundownProtection((PEX_RUNDOWN_REF)&Queue[1].Header.WaitListHead.Blink);
      goto LABEL_8;
    }
    v5 = ZwSetInformationThread(ThreadHandle, MaxThreadInfoClass|ThreadPriority, &ThreadInformation, 0x10u);
    if ( v5 < 0 )
    {
      ZwClose(ThreadHandle);
LABEL_8:
      AwRundownSingleQueue(Queue);
      return (unsigned int)v5;
    }
    ZwClose(ThreadHandle);
  }
  return 0;
}

```

## disassembly

```asm
0x140027008  mov     [rsp-18h+arg_10], rbx
0x14002700d  mov     [rsp-18h+arg_18], rsi
0x140027012  push    rbp
0x140027013  push    rdi
0x140027014  push    r14
0x140027016  mov     rbp, rsp
0x140027019  sub     rsp, 80h
0x140027020  mov     rax, cs:__security_cookie
0x140027027  xor     rax, rsp
0x14002702a  mov     [rbp+var_10], rax
0x14002702e  mov     ebx, edx
0x140027030  mov     [rbp+ThreadHandle], 0
0x140027038  xor     edx, edx; Val
0x14002703a  mov     dword ptr [rbp+ProcNumber.Group], 0
0x140027041  xorps   xmm0, xmm0
0x140027044  mov     rsi, rcx
0x140027047  movups  [rbp+ThreadInformation], xmm0
0x14002704b  lea     r8d, [rdx+58h]; Size
0x14002704f  call    memset
0x140027054  mov     edx, 1; Count
0x140027059  mov     rcx, rsi; Queue
0x14002705c  call    cs:__imp_KeInitializeQueue
0x140027063  nop     dword ptr [rax+rax+00h]
0x140027068  lea     r14, [rsi+50h]
0x14002706c  mov     [rsi+48h], ebx
0x14002706f  mov     rcx, r14; RunRef
0x140027072  call    cs:__imp_ExInitializeRundownProtection
0x140027079  nop     dword ptr [rax+rax+00h]
0x14002707e  lea     rdx, [rbp+ProcNumber]; ProcNumber
0x140027082  mov     byte ptr [rsi+4Ch], 1
0x140027086  mov     ecx, ebx; ProcIndex
0x140027088  call    cs:__imp_KeGetProcessorNumberFromIndex
0x14002708f  nop     dword ptr [rax+rax+00h]
0x140027094  movzx   eax, [rbp+ProcNumber.Group]
0x140027098  xorps   xmm0, xmm0
0x14002709b  mov     cl, [rbp+ProcNumber.Number]
0x14002709e  movups  [rbp+ThreadInformation], xmm0
0x1400270a2  mov     word ptr [rbp+ThreadInformation+8], ax
0x1400270a6  mov     eax, 1
0x1400270ab  shl     rax, cl
0x1400270ae  mov     qword ptr [rbp+ThreadInformation], rax
0x1400270b2  xor     edi, edi
0x1400270b4  cmp     edi, 3
0x1400270b7  jnb     loc_14002717B
0x1400270bd  mov     rcx, r14; RunRef
0x1400270c0  call    cs:__imp_ExAcquireRundownProtection
0x1400270c7  nop     dword ptr [rax+rax+00h]
0x1400270cc  mov     [rsp+80h+var_40], 0
0x1400270d5  lea     rax, [rbp+ThreadInformation]
0x1400270d9  mov     [rsp+80h+var_48], rax
0x1400270de  lea     rcx, [rbp+ThreadHandle]
0x1400270e2  lea     rax, AwWorkerThread
0x1400270e9  mov     [rsp+80h+var_50], rsi
0x1400270ee  mov     [rsp+80h+var_58], rax
0x1400270f3  xor     r9d, r9d
0x1400270f6  xor     r8d, r8d
0x1400270f9  mov     [rsp+80h+var_60], 0
0x140027102  mov     edx, 1FFFFFh
0x140027107  call    cs:__imp_PsCreateSystemThreadEx
0x14002710e  nop     dword ptr [rax+rax+00h]
0x140027113  mov     ebx, eax
0x140027115  test    eax, eax
0x140027117  js      short loc_140027162
0x140027119  mov     rcx, [rbp+ThreadHandle]; ThreadHandle
0x14002711d  lea     r8, [rbp+ThreadInformation]; ThreadInformation
0x140027121  mov     r9d, 10h; ThreadInformationLength
0x140027127  lea     edx, [r9+0Eh]; ThreadInformationClass
0x14002712b  call    cs:__imp_ZwSetInformationThread
0x140027132  nop     dword ptr [rax+rax+00h]
0x140027137  mov     rcx, [rbp+ThreadHandle]; Handle
0x14002713b  mov     ebx, eax
0x14002713d  test    eax, eax
0x14002713f  js      short loc_140027154
0x140027141  call    cs:__imp_ZwClose
0x140027148  nop     dword ptr [rax+rax+00h]
0x14002714d  inc     edi
0x14002714f  jmp     loc_1400270B4
0x140027154  call    cs:__imp_ZwClose
0x14002715b  nop     dword ptr [rax+rax+00h]
0x140027160  jmp     short loc_140027171
0x140027162  mov     rcx, r14; RunRef
0x140027165  call    cs:__imp_ExReleaseRundownProtection
0x14002716c  nop     dword ptr [rax+rax+00h]
0x140027171  mov     rcx, rsi
0x140027174  call    AwRundownSingleQueue
0x140027179  jmp     short loc_14002717D
0x14002717b  xor     ebx, ebx
0x14002717d  mov     eax, ebx
0x14002717f  mov     rcx, [rbp+var_10]
0x140027183  xor     rcx, rsp; StackCookie
0x140027186  call    __security_check_cookie
0x14002718b  lea     r11, [rsp+80h+var_s0]
0x140027193  mov     rbx, [r11+30h]
0x140027197  mov     rsi, [r11+38h]
0x14002719b  mov     rsp, r11
0x14002719e  pop     r14
0x1400271a0  pop     rdi
0x1400271a1  pop     rbp
0x1400271a2  retn
```
