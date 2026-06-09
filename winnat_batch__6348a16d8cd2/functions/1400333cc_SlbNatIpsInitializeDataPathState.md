# SlbNatIpsInitializeDataPathState

- ea: `0x1400333cc`
- end: `0x14003350b`
- name: `SlbNatIpsInitializeDataPathState`
- size: `319`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140035af8`

## callees

- `0x14000caa0`
- `0x14000d634`
- `0x14003329c`
- `0x1400333cc`

## import_xrefs

- `ntoskrnl!KeInitializeDpc` at `0x140033475`
- `ntoskrnl!KeInitializeDpc` at `0x140033475`
- `ntoskrnl!ExAllocatePool2` at `0x14003342e`
- `ntoskrnl!ExAllocatePool2` at `0x1400334c9`
- `ntoskrnl!ExAllocatePool2` at `0x14003342e`
- `ntoskrnl!ExAllocatePool2` at `0x1400334c9`
- `ntoskrnl!KeSetTargetProcessorDpcEx` at `0x1400334a6`
- `ntoskrnl!KeSetTargetProcessorDpcEx` at `0x1400334a6`
- `ntoskrnl!KeGetProcessorNumberFromIndex` at `0x140033488`
- `ntoskrnl!KeGetProcessorNumberFromIndex` at `0x140033488`

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
  __int64 v8; // r9
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // r8
  __int64 v12; // r9
  __int64 Pool2; // rax
  unsigned int v14; // ebx
  _PROCESSOR_NUMBER ProcNumber; // [rsp+60h] [rbp+8h] BYREF

  v0 = (unsigned int)dword_140026B60;
  ProcNumber = 0;
  RtlInitializeScalableMrswLock(&SlbNatIpsDataPathState);
  dword_140026840 = 1;
  qword_140026850 = (__int64)&qword_140026848;
  qword_140026848 = &qword_140026848;
  qword_140026858 = (PVOID)ExAllocatePool2(64, 96 * v0, 1668304467);
  if ( qword_140026858 )
  {
    for ( i = 0; (unsigned int)i < (unsigned int)v0; i = (unsigned int)(i + 1) )
    {
      v2 = (char *)qword_140026858;
      v3 = 96 * i;
      v4 = (char *)qword_140026858 + 96 * i;
      KeInitializeDpc((PRKDPC)(v4 + 32), SlbNatDpcWorker, 0);
      if ( KeGetProcessorNumberFromIndex(i, &ProcNumber) < 0 )
        MicrosoftTelemetryAssertTriggeredNoArgsKM(v6, v5, v7, v8);
      if ( KeSetTargetProcessorDpcEx((PKDPC)(v4 + 32), &ProcNumber) < 0 )
        MicrosoftTelemetryAssertTriggeredNoArgsKM(v10, v9, v11, v12);
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
    v14 = -1073741670;
    SlbNatIpsCleanupDataPathState();
  }
  return v14;
}

```

## disassembly

```asm
0x1400333cc  push    rbx
0x1400333ce  push    rbp
0x1400333cf  push    rsi
0x1400333d0  push    rdi
0x1400333d1  push    r14
0x1400333d3  push    r15
0x1400333d5  sub     rsp, 28h
0x1400333d9  mov     ebp, cs:dword_140026B60
0x1400333df  lea     rcx, SlbNatIpsDataPathState
0x1400333e6  mov     dword ptr [rsp+58h+ProcNumber.Group], 0
0x1400333ee  call    RtlInitializeScalableMrswLock
0x1400333f3  lea     rax, qword_140026848
0x1400333fa  mov     r15d, 1
0x140033400  lea     rdx, ds:0[rbp*2]
0x140033408  mov     cs:dword_140026840, r15d
0x14003340f  add     rdx, rbp
0x140033412  mov     cs:qword_140026850, rax
0x140033419  shl     rdx, 5
0x14003341d  mov     r8d, 63704E53h
0x140033423  lea     ecx, [r15+3Fh]
0x140033427  mov     cs:qword_140026848, rax
0x14003342e  call    cs:__imp_ExAllocatePool2
0x140033435  nop     dword ptr [rax+rax+00h]
0x14003343a  mov     cs:qword_140026858, rax
0x140033441  test    rax, rax
0x140033444  jz      loc_1400334ED
0x14003344a  xor     ebx, ebx
0x14003344c  cmp     ebx, ebp
0x14003344e  jnb     loc_1400334F9
0x140033454  mov     rsi, cs:qword_140026858
0x14003345b  lea     rdi, [rbx+rbx*2]
0x14003345f  shl     rdi, 5
0x140033463  lea     rdx, SlbNatDpcWorker; DeferredRoutine
0x14003346a  xor     r8d, r8d; DeferredContext
0x14003346d  lea     r14, [rdi+rsi]
0x140033471  lea     rcx, [r14+20h]; Dpc
0x140033475  call    cs:__imp_KeInitializeDpc
0x14003347c  nop     dword ptr [rax+rax+00h]
0x140033481  lea     rdx, [rsp+58h+ProcNumber]; ProcNumber
0x140033486  mov     ecx, ebx; ProcIndex
0x140033488  call    cs:__imp_KeGetProcessorNumberFromIndex
0x14003348f  nop     dword ptr [rax+rax+00h]
0x140033494  test    eax, eax
0x140033496  jns     short loc_14003349D
0x140033498  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14003349d  lea     rdx, [rsp+58h+ProcNumber]; ProcNumber
0x1400334a2  lea     rcx, [r14+20h]; Dpc
0x1400334a6  call    cs:__imp_KeSetTargetProcessorDpcEx
0x1400334ad  nop     dword ptr [rax+rax+00h]
0x1400334b2  test    eax, eax
0x1400334b4  jns     short loc_1400334BB
0x1400334b6  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x1400334bb  mov     edx, 20h ; ' '
0x1400334c0  mov     r8d, 636A4E53h
0x1400334c6  lea     ecx, [rdx+20h]
0x1400334c9  call    cs:__imp_ExAllocatePool2
0x1400334d0  nop     dword ptr [rax+rax+00h]
0x1400334d5  mov     [rdi+rsi+8], rax
0x1400334da  test    rax, rax
0x1400334dd  jz      short loc_1400334ED
0x1400334df  mov     [rdi+rsi+2], r15w
0x1400334e5  add     ebx, r15d
0x1400334e8  jmp     loc_14003344C
0x1400334ed  mov     ebx, 0C000009Ah
0x1400334f2  call    SlbNatIpsCleanupDataPathState
0x1400334f7  jmp     short loc_1400334FB
0x1400334f9  xor     ebx, ebx
0x1400334fb  mov     eax, ebx
0x1400334fd  add     rsp, 28h
0x140033501  pop     r15
0x140033503  pop     r14
0x140033505  pop     rdi
0x140033506  pop     rsi
0x140033507  pop     rbp
0x140033508  pop     rbx
0x140033509  retn
```
