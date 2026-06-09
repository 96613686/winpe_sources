# SlbNatIpsInitializeDataPathState

- ea: `0x1400344fc`
- end: `0x14003463b`
- name: `SlbNatIpsInitializeDataPathState`
- size: `319`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140036af8`

## callees

- `0x14000caa0`
- `0x14000d604`
- `0x1400343cc`
- `0x1400344fc`

## import_xrefs

- `ntoskrnl!KeInitializeDpc` at `0x1400345a5`
- `ntoskrnl!KeInitializeDpc` at `0x1400345a5`
- `ntoskrnl!ExAllocatePool2` at `0x14003455e`
- `ntoskrnl!ExAllocatePool2` at `0x1400345f9`
- `ntoskrnl!ExAllocatePool2` at `0x14003455e`
- `ntoskrnl!ExAllocatePool2` at `0x1400345f9`
- `ntoskrnl!KeSetTargetProcessorDpcEx` at `0x1400345d6`
- `ntoskrnl!KeSetTargetProcessorDpcEx` at `0x1400345d6`
- `ntoskrnl!KeGetProcessorNumberFromIndex` at `0x1400345b8`
- `ntoskrnl!KeGetProcessorNumberFromIndex` at `0x1400345b8`

## pseudocode

```c
__int64 SlbNatIpsInitializeDataPathState()
{
  __int64 v0; // rbp
  __int64 i; // rbx
  char *v2; // rsi
  __int64 v3; // rdi
  char *v4; // r14
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // r8
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // r8
  __int64 Pool2; // rax
  unsigned int v12; // ebx
  _PROCESSOR_NUMBER ProcNumber; // [rsp+60h] [rbp+8h] BYREF

  v0 = (unsigned int)dword_140027B60;
  ProcNumber = 0;
  RtlInitializeScalableMrswLock(&SlbNatIpsDataPathState);
  dword_140027840 = 1;
  qword_140027850 = (__int64)&qword_140027848;
  qword_140027848 = &qword_140027848;
  qword_140027858 = (PVOID)ExAllocatePool2(64, 96 * v0, 1668304467);
  if ( qword_140027858 )
  {
    for ( i = 0; (unsigned int)i < (unsigned int)v0; i = (unsigned int)(i + 1) )
    {
      v2 = (char *)qword_140027858;
      v3 = 96 * i;
      v4 = (char *)qword_140027858 + 96 * i;
      KeInitializeDpc((PRKDPC)(v4 + 32), SlbNatDpcWorker, 0);
      if ( KeGetProcessorNumberFromIndex(i, &ProcNumber) < 0 )
        MicrosoftTelemetryAssertTriggeredNoArgsKM(v6, v5, v7);
      if ( KeSetTargetProcessorDpcEx((PKDPC)(v4 + 32), &ProcNumber) < 0 )
        MicrosoftTelemetryAssertTriggeredNoArgsKM(v9, v8, v10);
      Pool2 = ExAllocatePool2(64, 32, 1667911251);
      *(_QWORD *)&v2[v3 + 8] = Pool2;
      if ( !Pool2 )
        goto LABEL_10;
      *(_WORD *)&v2[v3 + 2] = 1;
    }
    return 0;
  }
  else
  {
LABEL_10:
    v12 = -1073741670;
    SlbNatIpsCleanupDataPathState();
  }
  return v12;
}

```

## disassembly

```asm
0x1400344fc  push    rbx
0x1400344fe  push    rbp
0x1400344ff  push    rsi
0x140034500  push    rdi
0x140034501  push    r14
0x140034503  push    r15
0x140034505  sub     rsp, 28h
0x140034509  mov     ebp, cs:dword_140027B60
0x14003450f  lea     rcx, SlbNatIpsDataPathState
0x140034516  mov     dword ptr [rsp+58h+ProcNumber.Group], 0
0x14003451e  call    RtlInitializeScalableMrswLock
0x140034523  lea     rax, qword_140027848
0x14003452a  mov     r15d, 1
0x140034530  lea     rdx, ds:0[rbp*2]
0x140034538  mov     cs:dword_140027840, r15d
0x14003453f  add     rdx, rbp
0x140034542  mov     cs:qword_140027850, rax
0x140034549  shl     rdx, 5
0x14003454d  mov     r8d, 63704E53h
0x140034553  lea     ecx, [r15+3Fh]
0x140034557  mov     cs:qword_140027848, rax
0x14003455e  call    cs:__imp_ExAllocatePool2
0x140034565  nop     dword ptr [rax+rax+00h]
0x14003456a  mov     cs:qword_140027858, rax
0x140034571  test    rax, rax
0x140034574  jz      loc_14003461D
0x14003457a  xor     ebx, ebx
0x14003457c  cmp     ebx, ebp
0x14003457e  jnb     loc_140034629
0x140034584  mov     rsi, cs:qword_140027858
0x14003458b  lea     rdi, [rbx+rbx*2]
0x14003458f  shl     rdi, 5
0x140034593  lea     rdx, SlbNatDpcWorker; DeferredRoutine
0x14003459a  xor     r8d, r8d; DeferredContext
0x14003459d  lea     r14, [rdi+rsi]
0x1400345a1  lea     rcx, [r14+20h]; Dpc
0x1400345a5  call    cs:__imp_KeInitializeDpc
0x1400345ac  nop     dword ptr [rax+rax+00h]
0x1400345b1  lea     rdx, [rsp+58h+ProcNumber]; ProcNumber
0x1400345b6  mov     ecx, ebx; ProcIndex
0x1400345b8  call    cs:__imp_KeGetProcessorNumberFromIndex
0x1400345bf  nop     dword ptr [rax+rax+00h]
0x1400345c4  test    eax, eax
0x1400345c6  jns     short loc_1400345CD
0x1400345c8  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x1400345cd  lea     rdx, [rsp+58h+ProcNumber]; ProcNumber
0x1400345d2  lea     rcx, [r14+20h]; Dpc
0x1400345d6  call    cs:__imp_KeSetTargetProcessorDpcEx
0x1400345dd  nop     dword ptr [rax+rax+00h]
0x1400345e2  test    eax, eax
0x1400345e4  jns     short loc_1400345EB
0x1400345e6  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x1400345eb  mov     edx, 20h ; ' '
0x1400345f0  mov     r8d, 636A4E53h
0x1400345f6  lea     ecx, [rdx+20h]
0x1400345f9  call    cs:__imp_ExAllocatePool2
0x140034600  nop     dword ptr [rax+rax+00h]
0x140034605  mov     [rdi+rsi+8], rax
0x14003460a  test    rax, rax
0x14003460d  jz      short loc_14003461D
0x14003460f  mov     [rdi+rsi+2], r15w
0x140034615  add     ebx, r15d
0x140034618  jmp     loc_14003457C
0x14003461d  mov     ebx, 0C000009Ah
0x140034622  call    SlbNatIpsCleanupDataPathState
0x140034627  jmp     short loc_14003462B
0x140034629  xor     ebx, ebx
0x14003462b  mov     eax, ebx
0x14003462d  add     rsp, 28h
0x140034631  pop     r15
0x140034633  pop     r14
0x140034635  pop     rdi
0x140034636  pop     rsi
0x140034637  pop     rbp
0x140034638  pop     rbx
0x140034639  retn
```
