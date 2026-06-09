# VsmmWheapPageRangeInfoEnumeratePartitionPages

- ea: `0x1400c9090`
- end: `0x1400c953e`
- name: `VsmmWheapPageRangeInfoEnumeratePartitionPages`
- size: `1198`
- prototype: `__int64 __fastcall(__int64, __int64, void *)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400c7574`

## callees

- `0x1400029c0`
- `0x140006bf8`
- `0x14000a4e0`
- `0x140021650`
- `0x14002f524`
- `0x140034554`
- `0x140034584`
- `0x1400c8f38`
- `0x1400c9090`
- `0x1400c99ec`
- `0x1400f9760`

## import_xrefs

- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400c9307`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400c9307`
- `ntoskrnl!ObfDereferenceObject` at `0x1400c9370`
- `ntoskrnl!ObfDereferenceObject` at `0x1400c9370`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400c9258`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400c9360`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400c9258`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400c9360`
- `ntoskrnl!ZwClose` at `0x1400c9325`
- `ntoskrnl!ZwClose` at `0x1400c9325`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c93bf`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c93bf`
- `ntoskrnl!ExAllocatePool2` at `0x1400c9190`
- `ntoskrnl!ExAllocatePool2` at `0x1400c9190`
- `ntoskrnl!KeReleaseSemaphore` at `0x1400c92c3`
- `ntoskrnl!KeReleaseSemaphore` at `0x1400c92c3`
- `ntoskrnl!PsCreateSystemThread` at `0x1400c9287`
- `ntoskrnl!PsCreateSystemThread` at `0x1400c9287`
- `HAL!KeQueryPerformanceCounter` at `0x1400c90e1`
- `HAL!KeQueryPerformanceCounter` at `0x1400c93d8`
- `HAL!KeQueryPerformanceCounter` at `0x1400c90e1`
- `HAL!KeQueryPerformanceCounter` at `0x1400c93d8`

## pseudocode

```c
NTSTATUS __fastcall VsmmWheapPageRangeInfoEnumeratePartitionPages(__int64 a1, __int64 a2, void *a3)
{
  __int64 v6; // rax
  _QWORD *i; // rbx
  PVOID *Pool2; // rax
  PVOID *v9; // rcx
  PVOID **v10; // rax
  PVOID *StartContext; // rbx
  void *v12; // rcx
  PVOID *j; // rbx
  PVOID v14; // rcx
  PVOID *v15; // rax
  NTSTATUS result; // eax
  __int64 v17; // r9
  PVOID P[2]; // [rsp+40h] [rbp-C0h] BYREF
  void *ThreadHandle; // [rsp+50h] [rbp-B0h] BYREF
  PVOID Object; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v21; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v22; // [rsp+68h] [rbp-98h] BYREF
  __int64 v23; // [rsp+70h] [rbp-90h] BYREF
  __int64 v24; // [rsp+78h] [rbp-88h] BYREF
  __int64 v25; // [rsp+80h] [rbp-80h] BYREF
  __int128 v26; // [rsp+88h] [rbp-78h]
  union _LARGE_INTEGER PerformanceFrequency; // [rsp+98h] [rbp-68h] BYREF
  char v28[32]; // [rsp+A0h] [rbp-60h] BYREF
  char v29[16]; // [rsp+C0h] [rbp-40h] BYREF
  char v30[16]; // [rsp+D0h] [rbp-30h] BYREF
  PVOID *p_Object; // [rsp+E0h] [rbp-20h]
  __int64 v32; // [rsp+E8h] [rbp-18h]
  __int64 *v33; // [rsp+F0h] [rbp-10h]
  __int64 v34; // [rsp+F8h] [rbp-8h]
  __int64 *v35; // [rsp+100h] [rbp+0h]
  __int64 v36; // [rsp+108h] [rbp+8h]
  __int64 *v37; // [rsp+110h] [rbp+10h]
  __int64 v38; // [rsp+118h] [rbp+18h]
  __int64 *v39; // [rsp+120h] [rbp+20h]
  __int64 v40; // [rsp+128h] [rbp+28h]
  void **p_ThreadHandle; // [rsp+130h] [rbp+30h]
  __int64 v42; // [rsp+138h] [rbp+38h]
  __int64 *v43; // [rsp+140h] [rbp+40h]
  __int64 v44; // [rsp+148h] [rbp+48h]

  PerformanceFrequency.QuadPart = 0;
  v26 = 0;
  ThreadHandle = 0;
  *(LARGE_INTEGER *)&v26 = KeQueryPerformanceCounter(0);
  P[1] = P;
  P[0] = P;
  VidObjectLockAcquireShared((char *)VidDeviceExtension + 104);
  while ( 1 )
  {
    v6 = VidPartitionTableEnumerateById(&ThreadHandle);
    if ( !v6 )
      break;
    if ( !a2 || a2 == *(_QWORD *)(v6 + 648) )
    {
      if ( (int)VsmmWheapPageRangeInfoAddPartition(a1, v6) >= 0 )
        ++*(_DWORD *)(a1 + 20);
      else
        VidTraceErrorStatusInternal0(
          "VsmmWheapPageRangeInfoEnumeratePartitionPages",
          "onecore\\vm\\vid\\sys\\vsmm\\vsmmwhea.c",
          4002);
    }
  }
  VidObjectLockRelease((char *)VidDeviceExtension + 104);
  for ( i = *(_QWORD **)(a1 + 24); i != (_QWORD *)(a1 + 24); i = (_QWORD *)*i )
  {
    Pool2 = (PVOID *)ExAllocatePool2(256, 64, 1833788502);
    v9 = Pool2;
    if ( Pool2 )
    {
      Pool2[1] = Pool2;
      *Pool2 = Pool2;
      Pool2[2] = i;
      Pool2[3] = (PVOID)a1;
      Pool2[4] = a3;
      Pool2[5] = (PVOID)(a1 + 40);
      v10 = (PVOID **)P[1];
      if ( *(PVOID **)P[1] != P )
LABEL_30:
        __fastfail(3u);
      v9[1] = P[1];
      *v9 = P;
      *v10 = v9;
      P[1] = v9;
    }
    else
    {
      VidTraceErrorStatusInternal0(
        "VsmmWheapPageRangeInfoEnumeratePartitionPages",
        "onecore\\vm\\vid\\sys\\vsmm\\vsmmwhea.c",
        4033);
    }
  }
  for ( StartContext = (PVOID *)P[0]; StartContext != P; StartContext = (PVOID *)*StartContext )
  {
    ThreadHandle = 0;
    if ( (unsigned __int64)_InterlockedCompareExchange64((volatile signed __int64 *)(a1 + 40), 0, 0) >= *(_QWORD *)a1 )
      break;
    KeWaitForSingleObject(&VsmmWheapPageRangeInfoEnumeratePartitionPagesConcurrentLimit, Executive, 0, 0, 0);
    if ( PsCreateSystemThread(
           &ThreadHandle,
           0x1FFFFFu,
           0,
           0,
           0,
           (PKSTART_ROUTINE)VsmmWheapPartitionInfoEnumeratePagesThreadRoutine,
           StartContext) >= 0 )
    {
      Object = 0;
      ObReferenceObjectByHandle(ThreadHandle, 0x1FFFFFu, 0, 0, &Object, 0);
      v12 = ThreadHandle;
      StartContext[6] = Object;
      *((_BYTE *)StartContext + 56) = 1;
      ZwClose(v12);
    }
    else
    {
      VidTraceErrorStatusInternal0(
        "VsmmWheapPageRangeInfoEnumeratePartitionPages",
        "onecore\\vm\\vid\\sys\\vsmm\\vsmmwhea.c",
        4101);
      KeReleaseSemaphore(&VsmmWheapPageRangeInfoEnumeratePartitionPagesConcurrentLimit, 0, 1, 0);
      VsmmWheapPartitionInfoEnumeratePages(StartContext[2], StartContext[3], StartContext[4], StartContext[5]);
    }
  }
  for ( j = (PVOID *)P[0]; j != P; j = (PVOID *)*j )
  {
    if ( *((_BYTE *)j + 56) )
    {
      KeWaitForSingleObject(j[6], Executive, 0, 0, 0);
      ObfDereferenceObject(j[6]);
    }
  }
  while ( P[0] != P )
  {
    v14 = P[1];
    if ( *(PVOID **)P[1] != P )
      goto LABEL_30;
    v15 = (PVOID *)*((_QWORD *)P[1] + 1);
    if ( *v15 != P[1] )
      goto LABEL_30;
    P[1] = *((PVOID *)P[1] + 1);
    *v15 = P;
    ExFreePoolWithTag(v14, 0x6D4D6456u);
  }
  *((LARGE_INTEGER *)&v26 + 1) = KeQueryPerformanceCounter(&PerformanceFrequency);
  result = dword_140064110;
  if ( (unsigned int)dword_140064110 > 4 )
  {
    result = tlgKeywordOn(&dword_140064110, 256);
    if ( (_BYTE)result )
    {
      tlgCreate1Sz_char(v29, "VsmmWheapPageRangeInfoEnumeratePartitionPages");
      tlgCreate1Sz_char(v30, "onecore\\vm\\vid\\sys\\vsmm\\vsmmwhea.c");
      v32 = v17;
      p_Object = &Object;
      v21 = *(_QWORD *)(a1 + 8);
      v33 = &v21;
      v22 = *(_QWORD *)a1;
      v35 = &v22;
      v37 = &v23;
      v42 = v17;
      LODWORD(Object) = 4196;
      v34 = 8;
      v24 = 1000000LL * (*((_QWORD *)&v26 + 1) - (_QWORD)v26) / PerformanceFrequency.QuadPart;
      v39 = &v24;
      LODWORD(ThreadHandle) = *(_DWORD *)(a1 + 20);
      p_ThreadHandle = &ThreadHandle;
      v25 = *(_QWORD *)(a1 + 40);
      v43 = &v25;
      v36 = 8;
      v23 = a2;
      v38 = 8;
      v40 = 8;
      v44 = 8;
      return tlgWriteTransfer_EtwWriteTransfer(
               (__int64)&dword_140064110,
               (unsigned __int8 *)byte_140052ECF,
               0,
               0,
               0xBu,
               (PEVENT_DATA_DESCRIPTOR)v28);
    }
  }
  return result;
}

```

## disassembly

```asm
0x1400c9090  mov     [rsp-8+arg_8], rbx
0x1400c9095  mov     [rsp-8+arg_10], rsi
0x1400c909a  push    rbp
0x1400c909b  push    rdi
0x1400c909c  push    r12
0x1400c909e  push    r14
0x1400c90a0  push    r15
0x1400c90a2  lea     rbp, [rsp-60h]
0x1400c90a7  sub     rsp, 160h
0x1400c90ae  mov     rax, cs:__security_cookie
0x1400c90b5  xor     rax, rsp
0x1400c90b8  mov     [rbp+80h+var_30], rax
0x1400c90bc  xorps   xmm0, xmm0
0x1400c90bf  mov     rdi, rcx
0x1400c90c2  xor     eax, eax
0x1400c90c4  xor     r12d, r12d
0x1400c90c7  xor     ecx, ecx; PerformanceFrequency
0x1400c90c9  mov     qword ptr [rbp+80h+PerformanceFrequency], rax
0x1400c90cd  movups  [rbp+80h+var_F8], xmm0
0x1400c90d1  mov     [rsp+180h+ThreadHandle], r12
0x1400c90d6  mov     r15, r8
0x1400c90d9  movups  xmmword ptr [rsp+180h+P], xmm0
0x1400c90de  mov     r14, rdx
0x1400c90e1  call    cs:__imp_KeQueryPerformanceCounter
0x1400c90e8  nop     dword ptr [rax+rax+00h]
0x1400c90ed  mov     rcx, cs:VidDeviceExtension
0x1400c90f4  mov     qword ptr [rbp+80h+var_F8], rax
0x1400c90f8  add     rcx, 68h ; 'h'
0x1400c90fc  lea     rax, [rsp+180h+P]
0x1400c9101  mov     [rsp+180h+P+8], rax
0x1400c9106  lea     rax, [rsp+180h+P]
0x1400c910b  mov     [rsp+180h+P], rax
0x1400c9110  call    VidObjectLockAcquireShared
0x1400c9115  jmp     short loc_1400C9155
0x1400c9117  test    r14, r14
0x1400c911a  jz      short loc_1400C9125
0x1400c911c  cmp     r14, [rax+288h]
0x1400c9123  jnz     short loc_1400C9155
0x1400c9125  mov     rdx, rax
0x1400c9128  mov     rcx, rdi
0x1400c912b  call    VsmmWheapPageRangeInfoAddPartition
0x1400c9130  test    eax, eax
0x1400c9132  jns     short loc_1400C9152
0x1400c9134  mov     r9d, eax
0x1400c9137  lea     rdx, aOnecoreVmVidSy_51; "onecore\\vm\\vid\\sys\\vsmm\\vsmmwhea.c"
0x1400c913e  mov     r8d, 0FA2h
0x1400c9144  lea     rcx, aVsmmwheappager; "VsmmWheapPageRangeInfoEnumeratePartitio"...
0x1400c914b  call    VidTraceErrorStatusInternal0
0x1400c9150  jmp     short loc_1400C9155
0x1400c9152  inc     dword ptr [rdi+14h]
0x1400c9155  lea     rcx, [rsp+180h+ThreadHandle]
0x1400c915a  call    VidPartitionTableEnumerateById
0x1400c915f  test    rax, rax
0x1400c9162  jnz     short loc_1400C9117
0x1400c9164  mov     rcx, cs:VidDeviceExtension
0x1400c916b  add     rcx, 68h ; 'h'
0x1400c916f  call    VidObjectLockRelease
0x1400c9174  lea     rsi, [rdi+18h]
0x1400c9178  mov     rbx, [rsi]
0x1400c917b  jmp     loc_1400C920A
0x1400c9180  mov     edx, 40h ; '@'
0x1400c9185  mov     ecx, 100h
0x1400c918a  mov     r8d, 6D4D6456h
0x1400c9190  call    cs:__imp_ExAllocatePool2
0x1400c9197  nop     dword ptr [rax+rax+00h]
0x1400c919c  mov     rcx, rax
0x1400c919f  test    rax, rax
0x1400c91a2  jnz     short loc_1400C91C5
0x1400c91a4  mov     r9d, 0C000009Ah
0x1400c91aa  lea     rdx, aOnecoreVmVidSy_51; "onecore\\vm\\vid\\sys\\vsmm\\vsmmwhea.c"
0x1400c91b1  mov     r8d, 0FC1h
0x1400c91b7  lea     rcx, aVsmmwheappager; "VsmmWheapPageRangeInfoEnumeratePartitio"...
0x1400c91be  call    VidTraceErrorStatusInternal0
0x1400c91c3  jmp     short loc_1400C9207
0x1400c91c5  mov     [rax+8], rcx
0x1400c91c9  lea     rdx, [rsp+180h+P]
0x1400c91ce  mov     [rax], rcx
0x1400c91d1  mov     [rax+10h], rbx
0x1400c91d5  mov     [rax+18h], rdi
0x1400c91d9  mov     [rax+20h], r15
0x1400c91dd  lea     rax, [rdi+28h]
0x1400c91e1  mov     [rcx+28h], rax
0x1400c91e5  mov     rax, [rsp+180h+P+8]
0x1400c91ea  cmp     [rax], rdx
0x1400c91ed  jnz     loc_1400C93CD
0x1400c91f3  mov     [rcx+8], rax
0x1400c91f7  lea     rdx, [rsp+180h+P]
0x1400c91fc  mov     [rcx], rdx
0x1400c91ff  mov     [rax], rcx
0x1400c9202  mov     [rsp+180h+P+8], rcx
0x1400c9207  mov     rbx, [rbx]
0x1400c920a  cmp     rbx, rsi
0x1400c920d  jnz     loc_1400C9180
0x1400c9213  mov     rbx, [rsp+180h+P]
0x1400c9218  lea     rax, [rsp+180h+P]
0x1400c921d  cmp     rbx, rax
0x1400c9220  jz      loc_1400C9342
0x1400c9226  mov     esi, 1FFFFFh
0x1400c922b  mov     [rsp+180h+ThreadHandle], r12
0x1400c9230  mov     rcx, r12
0x1400c9233  xor     eax, eax
0x1400c9235  lock cmpxchg [rdi+28h], rcx
0x1400c923b  cmp     rax, [rdi]
0x1400c923e  jnb     loc_1400C9342
0x1400c9244  xor     r9d, r9d; Alertable
0x1400c9247  mov     [rsp+180h+Timeout], r12; Timeout
0x1400c924c  xor     r8d, r8d; WaitMode
0x1400c924f  lea     rcx, VsmmWheapPageRangeInfoEnumeratePartitionPagesConcurrentLimit; Object
0x1400c9256  xor     edx, edx; WaitReason
0x1400c9258  call    cs:__imp_KeWaitForSingleObject
0x1400c925f  nop     dword ptr [rax+rax+00h]
0x1400c9264  lea     rax, VsmmWheapPartitionInfoEnumeratePagesThreadRoutine
0x1400c926b  mov     [rsp+180h+StartContext], rbx; StartContext
0x1400c9270  mov     [rsp+180h+StartRoutine], rax; StartRoutine
0x1400c9275  lea     rcx, [rsp+180h+ThreadHandle]; ThreadHandle
0x1400c927a  xor     r9d, r9d; ProcessHandle
0x1400c927d  mov     [rsp+180h+Timeout], r12; ClientId
0x1400c9282  xor     r8d, r8d; ObjectAttributes
0x1400c9285  mov     edx, esi; DesiredAccess
0x1400c9287  call    cs:__imp_PsCreateSystemThread
0x1400c928e  nop     dword ptr [rax+rax+00h]
0x1400c9293  test    eax, eax
0x1400c9295  jns     short loc_1400C92E6
0x1400c9297  mov     r9d, eax
0x1400c929a  lea     rdx, aOnecoreVmVidSy_51; "onecore\\vm\\vid\\sys\\vsmm\\vsmmwhea.c"
0x1400c92a1  mov     r8d, 1005h
0x1400c92a7  lea     rcx, aVsmmwheappager; "VsmmWheapPageRangeInfoEnumeratePartitio"...
0x1400c92ae  call    VidTraceErrorStatusInternal0
0x1400c92b3  xor     r9d, r9d; Wait
0x1400c92b6  lea     rcx, VsmmWheapPageRangeInfoEnumeratePartitionPagesConcurrentLimit; Semaphore
0x1400c92bd  xor     edx, edx; Increment
0x1400c92bf  lea     r8d, [r9+1]; Adjustment
0x1400c92c3  call    cs:__imp_KeReleaseSemaphore
0x1400c92ca  nop     dword ptr [rax+rax+00h]
0x1400c92cf  mov     r9, [rbx+28h]
0x1400c92d3  mov     r8, [rbx+20h]
0x1400c92d7  mov     rdx, [rbx+18h]
0x1400c92db  mov     rcx, [rbx+10h]
0x1400c92df  call    VsmmWheapPartitionInfoEnumeratePages
0x1400c92e4  jmp     short loc_1400C9331
0x1400c92e6  mov     rcx, [rsp+180h+ThreadHandle]; Handle
0x1400c92eb  lea     rax, [rsp+180h+Object]
0x1400c92f0  mov     [rsp+180h+StartRoutine], r12; HandleInformation
0x1400c92f5  xor     r9d, r9d; AccessMode
0x1400c92f8  xor     r8d, r8d; ObjectType
0x1400c92fb  mov     [rsp+180h+Timeout], rax; Object
0x1400c9300  mov     edx, esi; DesiredAccess
0x1400c9302  mov     [rsp+180h+Object], r12
0x1400c9307  call    cs:__imp_ObReferenceObjectByHandle
0x1400c930e  nop     dword ptr [rax+rax+00h]
0x1400c9313  mov     rax, [rsp+180h+Object]
0x1400c9318  mov     rcx, [rsp+180h+ThreadHandle]; Handle
0x1400c931d  mov     [rbx+30h], rax
0x1400c9321  mov     byte ptr [rbx+38h], 1
0x1400c9325  call    cs:__imp_ZwClose
0x1400c932c  nop     dword ptr [rax+rax+00h]
0x1400c9331  mov     rbx, [rbx]
0x1400c9334  lea     rax, [rsp+180h+P]
0x1400c9339  cmp     rbx, rax
0x1400c933c  jnz     loc_1400C922B
0x1400c9342  mov     rbx, [rsp+180h+P]
0x1400c9347  jmp     short loc_1400C937F
0x1400c9349  cmp     [rbx+38h], r12b
0x1400c934d  jz      short loc_1400C937C
0x1400c934f  mov     rcx, [rbx+30h]; Object
0x1400c9353  xor     r9d, r9d; Alertable
0x1400c9356  xor     r8d, r8d; WaitMode
0x1400c9359  mov     [rsp+180h+Timeout], r12; Timeout
0x1400c935e  xor     edx, edx; WaitReason
0x1400c9360  call    cs:__imp_KeWaitForSingleObject
0x1400c9367  nop     dword ptr [rax+rax+00h]
0x1400c936c  mov     rcx, [rbx+30h]; Object
0x1400c9370  call    cs:__imp_ObfDereferenceObject
0x1400c9377  nop     dword ptr [rax+rax+00h]
0x1400c937c  mov     rbx, [rbx]
0x1400c937f  lea     rax, [rsp+180h+P]
0x1400c9384  cmp     rbx, rax
0x1400c9387  jnz     short loc_1400C9349
0x1400c9389  lea     rax, [rsp+180h+P]
0x1400c938e  cmp     [rsp+180h+P], rax
0x1400c9393  jz      short loc_1400C93D4
0x1400c9395  mov     rcx, [rsp+180h+P+8]; P
0x1400c939a  lea     rax, [rsp+180h+P]
0x1400c939f  cmp     [rcx], rax
0x1400c93a2  jnz     short loc_1400C93CD
0x1400c93a4  mov     rax, [rcx+8]
0x1400c93a8  cmp     [rax], rcx
0x1400c93ab  jnz     short loc_1400C93CD
0x1400c93ad  lea     rdx, [rsp+180h+P]
0x1400c93b2  mov     [rsp+180h+P+8], rax
0x1400c93b7  mov     [rax], rdx
0x1400c93ba  mov     edx, 6D4D6456h; Tag
0x1400c93bf  call    cs:__imp_ExFreePoolWithTag
0x1400c93c6  nop     dword ptr [rax+rax+00h]
0x1400c93cb  jmp     short loc_1400C9389
0x1400c93cd  mov     ecx, 3
0x1400c93d2  int     29h; Win8: RtlFailFast(ecx)
0x1400c93d4  lea     rcx, [rbp+80h+PerformanceFrequency]; PerformanceFrequency
0x1400c93d8  call    cs:__imp_KeQueryPerformanceCounter
0x1400c93df  nop     dword ptr [rax+rax+00h]
0x1400c93e4  mov     qword ptr [rbp+80h+var_F8+8], rax
0x1400c93e8  mov     r9d, 4
0x1400c93ee  mov     eax, cs:dword_140064110
0x1400c93f4  cmp     eax, r9d
0x1400c93f7  jbe     loc_1400C9515
0x1400c93fd  mov     edx, 100h
0x1400c9402  lea     rcx, dword_140064110
0x1400c9409  call    _tlgKeywordOn
0x1400c940e  test    al, al
0x1400c9410  jz      loc_1400C9515
0x1400c9416  lea     rdx, aVsmmwheappager; "VsmmWheapPageRangeInfoEnumeratePartitio"...
0x1400c941d  lea     rcx, [rbp+80h+var_C0]
0x1400c9421  call    _tlgCreate1Sz_char
0x1400c9426  lea     rdx, aOnecoreVmVidSy_51; "onecore\\vm\\vid\\sys\\vsmm\\vsmmwhea.c"
0x1400c942d  lea     rcx, [rbp+80h+var_B0]
0x1400c9431  call    _tlgCreate1Sz_char
0x1400c9436  lea     rax, [rsp+180h+Object]
0x1400c943b  mov     [rbp+80h+var_98], r9
0x1400c943f  mov     [rbp+80h+var_A0], rax
0x1400c9443  lea     rcx, dword_140064110
0x1400c944a  mov     rax, [rdi+8]
0x1400c944e  xor     r8d, r8d
0x1400c9451  mov     [rsp+180h+var_120], rax
0x1400c9456  lea     rax, [rsp+180h+var_120]
0x1400c945b  mov     [rbp+80h+var_90], rax
0x1400c945f  mov     rax, [rdi]
0x1400c9462  mov     [rsp+180h+var_118], rax
0x1400c9467  lea     rax, [rsp+180h+var_118]
0x1400c946c  mov     [rbp+80h+var_80], rax
0x1400c9470  lea     rax, [rsp+180h+var_110]
0x1400c9475  mov     [rbp+80h+var_70], rax
0x1400c9479  mov     rax, qword ptr [rbp+80h+var_F8+8]
0x1400c947d  sub     rax, qword ptr [rbp+80h+var_F8]
0x1400c9481  imul    rax, 0F4240h
0x1400c9488  mov     [rbp+80h+var_48], r9
0x1400c948c  xor     r9d, r9d
0x1400c948f  cqo
0x1400c9491  mov     dword ptr [rsp+180h+Object], 1064h
0x1400c9499  idiv    qword ptr [rbp+80h+PerformanceFrequency]
0x1400c949d  lea     rdx, byte_140052ECF
0x1400c94a4  mov     [rbp+80h+var_88], 8
0x1400c94ac  mov     [rsp+180h+var_108], rax
0x1400c94b1  lea     rax, [rsp+180h+var_108]
0x1400c94b6  mov     [rbp+80h+var_60], rax
0x1400c94ba  mov     eax, [rdi+14h]
0x1400c94bd  mov     dword ptr [rsp+180h+ThreadHandle], eax
0x1400c94c1  lea     rax, [rsp+180h+ThreadHandle]
0x1400c94c6  mov     [rbp+80h+var_50], rax
0x1400c94ca  mov     rax, [rdi+28h]
0x1400c94ce  mov     [rbp+80h+var_100], rax
0x1400c94d2  lea     rax, [rbp+80h+var_100]
0x1400c94d6  mov     [rbp+80h+var_40], rax
0x1400c94da  lea     rax, [rbp+80h+var_E0]
0x1400c94de  mov     [rsp+180h+StartRoutine], rax
0x1400c94e3  mov     dword ptr [rsp+180h+Timeout], 0Bh
0x1400c94eb  mov     [rbp+80h+var_78], 8
0x1400c94f3  mov     [rsp+180h+var_110], r14
0x1400c94f8  mov     [rbp+80h+var_68], 8
0x1400c9500  mov     [rbp+80h+var_58], 8
0x1400c9508  mov     [rbp+80h+var_38], 8
0x1400c9510  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400c9515  mov     rcx, [rbp+80h+var_30]
0x1400c9519  xor     rcx, rsp; StackCookie
0x1400c951c  call    __security_check_cookie
0x1400c9521  lea     r11, [rsp+180h+var_20]
0x1400c9529  mov     rbx, [r11+38h]
0x1400c952d  mov     rsi, [r11+40h]
0x1400c9531  mov     rsp, r11
0x1400c9534  pop     r15
0x1400c9536  pop     r14
0x1400c9538  pop     r12
0x1400c953a  pop     rdi
0x1400c953b  pop     rbp
0x1400c953c  retn
```
