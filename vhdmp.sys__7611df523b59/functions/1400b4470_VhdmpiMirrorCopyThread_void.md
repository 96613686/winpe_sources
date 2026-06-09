# VhdmpiMirrorCopyThread(void *)

- ea: `0x1400b4470`
- end: `0x1400b480f`
- name: `?VhdmpiMirrorCopyThread@@YAXPEAX@Z`
- size: `927`
- prototype: `KSTART_ROUTINE`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x140014550`
- `0x140023560`
- `0x140035e94`
- `0x1400b3208`
- `0x1400b4470`
- `0x1400b4818`
- `0x1400e0a14`

## import_xrefs

- `ntoskrnl!KeReleaseSemaphore` at `0x1400b466c`
- `ntoskrnl!KeReleaseSemaphore` at `0x1400b466c`
- `ntoskrnl!PsTerminateSystemThread` at `0x1400b46fd`
- `ntoskrnl!PsTerminateSystemThread` at `0x1400b46fd`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400b44b6`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400b4531`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400b4623`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400b44b6`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400b4531`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400b4623`
- `ntoskrnl!ExReleaseRundownProtection` at `0x1400b46ef`
- `ntoskrnl!ExReleaseRundownProtection` at `0x1400b46ef`

## string_xrefs

- `0x1400b47e2`: `Mirror WorkerThread (context %p) AsyncOp cancelled`
- `0x1400b4754`: `Mirror WorkerThread (context %p) CopyVirtualBlock at offset %llx length %lx failed with status 0x%08x`
- `0x1400b44e2`: `Mirror WorkerThread (context %p) starting work`
- `0x1400b4502`: `VhdmpiMirrorCopyThread`
- `0x1400b46b6`: `VhdmpiMirrorCopyThread`
- `0x1400b4760`: `VhdmpiMirrorCopyThread`
- `0x1400b47fe`: `VhdmpiMirrorCopyThread`
- `0x1400b46aa`: `Mirror WorkerThread (context %p) copied %ld blocks, status 0x%08x`

## pseudocode

```c
void __fastcall VhdmpiMirrorCopyThread(char *StartContext)
{
  __int64 v1; // rdi
  int v3; // r14d
  signed __int32 AsyncOpOverrideStatus; // ebx
  int NextCopyRangeAndHold; // eax
  struct _EX_RUNDOWN_REF **v6; // r14
  unsigned __int64 v7; // r8
  int *v8; // r15
  unsigned int v9; // r13d
  unsigned __int8 v10; // r8
  unsigned __int8 v11; // r8
  int v12; // [rsp+90h] [rbp+8h]
  unsigned int v13; // [rsp+98h] [rbp+10h] BYREF
  unsigned __int64 v14; // [rsp+A0h] [rbp+18h] BYREF

  v1 = *(_QWORD *)StartContext;
  v3 = 0;
  v14 = 0;
  v12 = 0;
  v13 = 0;
  KeWaitForSingleObject(StartContext + 16, Executive, 0, 0, 0);
  if ( (unsigned int)dword_140087708 > 5 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 0x40000) )
    TraceEvents(
      "VhdmpiMirrorCopyThread",
      0x5C2u,
      5u,
      0x40000u,
      "Mirror WorkerThread (context %p) starting work",
      StartContext);
  AsyncOpOverrideStatus = *(_DWORD *)(v1 + 760);
  if ( AsyncOpOverrideStatus >= 0 )
  {
    KeWaitForSingleObject((PVOID)(v1 + 792), Executive, 0, 0, 0);
    NextCopyRangeAndHold = VhdmpiMirrorGetNextCopyRangeAndHold(
                             (struct _VHD_INTERNAL_ASYNC_MIRROR_COPY_CONTEXT *)(v1 + 720),
                             (struct _VHD_MIRROR_COPY_THREAD_CONTEXT *)StartContext,
                             &v14,
                             &v13);
    if ( NextCopyRangeAndHold < 0 )
    {
LABEL_13:
      AsyncOpOverrideStatus = 0;
      if ( NextCopyRangeAndHold != -1073741807 )
        AsyncOpOverrideStatus = NextCopyRangeAndHold;
    }
    else
    {
      v6 = (struct _EX_RUNDOWN_REF **)(v1 + 136);
      while ( 1 )
      {
        AsyncOpOverrideStatus = VhdmpiGetAsyncOpOverrideStatus((struct _VHD_ASYNC_OP_CONTEXT *)v1);
        if ( AsyncOpOverrideStatus < 0 )
          break;
        if ( *(int *)(v1 + 760) < 0 )
        {
          VhdmpiProcessEventComplete(*v6 + 48);
          goto LABEL_15;
        }
        v7 = *(_QWORD *)(v1 + 104);
        v8 = (int *)v14;
        do
          v7 = _InterlockedCompareExchange64(
                 (volatile signed __int64 *)(v1 + 104),
                 (signed __int64)v8 - *(unsigned int *)(v1 + 192),
                 v7);
        while ( v7 < (unsigned __int64)v8 - *(unsigned int *)(v1 + 192) );
        v9 = v13;
        v6 = (struct _EX_RUNDOWN_REF **)(v1 + 136);
        AsyncOpOverrideStatus = VhdmpiCopyVirtualBlock(
                                  (struct _VHD_MIRROR_CONTEXT *)v1,
                                  (struct _VHD_INTERNAL_IO_CONTEXT *)(StartContext + 48),
                                  v8,
                                  v13,
                                  1u);
        VhdmpiProcessEventComplete((PEX_RUNDOWN_REF)(*(_QWORD *)(v1 + 136) + 384LL));
        if ( AsyncOpOverrideStatus < 0 )
        {
          if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 0x40000) )
            TraceEvents(
              "VhdmpiMirrorCopyThread",
              0x62Bu,
              v10,
              0x40000u,
              "Mirror WorkerThread (context %p) CopyVirtualBlock at offset %llx length %lx failed with status 0x%08x",
              StartContext,
              v8,
              v9,
              AsyncOpOverrideStatus);
          goto LABEL_16;
        }
        ++v12;
        KeWaitForSingleObject((PVOID)(v1 + 792), Executive, 0, 0, 0);
        NextCopyRangeAndHold = VhdmpiMirrorGetNextCopyRangeAndHold(
                                 (struct _VHD_INTERNAL_ASYNC_MIRROR_COPY_CONTEXT *)(v1 + 720),
                                 (struct _VHD_MIRROR_COPY_THREAD_CONTEXT *)StartContext,
                                 &v14,
                                 &v13);
        if ( NextCopyRangeAndHold < 0 )
          goto LABEL_13;
      }
      VhdmpiProcessEventComplete(*v6 + 48);
      if ( (unsigned int)dword_140087708 > 3 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 0x40000) )
        TraceEvents(
          "VhdmpiMirrorCopyThread",
          0x5FBu,
          v11,
          0x40000u,
          "Mirror WorkerThread (context %p) AsyncOp cancelled",
          StartContext);
    }
LABEL_15:
    KeReleaseSemaphore((PRKSEMAPHORE)(v1 + 792), 0, 1, 0);
LABEL_16:
    v3 = v12;
  }
  *((_DWORD *)StartContext + 84) = AsyncOpOverrideStatus;
  if ( (unsigned int)dword_140087708 > 5 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 0x40000) )
    TraceEvents(
      "VhdmpiMirrorCopyThread",
      0x63Du,
      5u,
      0x40000u,
      "Mirror WorkerThread (context %p) copied %ld blocks, status 0x%08x",
      StartContext,
      v3,
      AsyncOpOverrideStatus);
  if ( AsyncOpOverrideStatus < 0 )
    _InterlockedCompareExchange((volatile signed __int32 *)(v1 + 760), AsyncOpOverrideStatus, 0);
  ExReleaseRundownProtection((PEX_RUNDOWN_REF)(v1 + 776));
  PsTerminateSystemThread(0);
}

```

## disassembly

```asm
0x1400b4470  mov     rax, rsp
0x1400b4473  mov     [rax+20h], rbx
0x1400b4477  push    rbp
0x1400b4478  push    rsi
0x1400b4479  push    rdi
0x1400b447a  push    r12
0x1400b447c  push    r13
0x1400b447e  push    r14
0x1400b4480  push    r15
0x1400b4482  sub     rsp, 50h
0x1400b4486  mov     rdi, [rcx]
0x1400b4489  mov     rsi, rcx
0x1400b448c  xor     r14d, r14d
0x1400b448f  mov     qword ptr [rax+18h], 0
0x1400b4497  add     rcx, 10h; Object
0x1400b449b  mov     [rsp+88h+arg_0], r14d
0x1400b44a3  xor     r9d, r9d; Alertable
0x1400b44a6  mov     [rax-68h], r14
0x1400b44aa  xor     r8d, r8d; WaitMode
0x1400b44ad  mov     dword ptr [rax+10h], 0
0x1400b44b4  xor     edx, edx; WaitReason
0x1400b44b6  call    cs:__imp_KeWaitForSingleObject
0x1400b44bd  nop     dword ptr [rax+rax+00h]
0x1400b44c2  mov     eax, cs:dword_140087708
0x1400b44c8  cmp     eax, 5
0x1400b44cb  jbe     short loc_1400B450E
0x1400b44cd  mov     edx, 40000h
0x1400b44d2  lea     rcx, dword_140087708
0x1400b44d9  call    _tlgKeywordOn
0x1400b44de  test    al, al
0x1400b44e0  jz      short loc_1400B450E
0x1400b44e2  lea     rax, aMirrorWorkerth_0; "Mirror WorkerThread (context %p) starti"...
0x1400b44e9  mov     qword ptr [rsp+88h+var_60], rsi; char
0x1400b44ee  mov     edx, 5C2h; int
0x1400b44f3  mov     [rsp+88h+Timeout], rax; char *
0x1400b44f8  mov     r9d, 40000h; int
0x1400b44fe  lea     r8d, [r14+5]; int
0x1400b4502  lea     rcx, aVhdmpimirrorco; "VhdmpiMirrorCopyThread"
0x1400b4509  call    TraceEvents
0x1400b450e  lea     rbp, [rdi+2D0h]
0x1400b4515  mov     ebx, [rbp+28h]
0x1400b4518  test    ebx, ebx
0x1400b451a  js      loc_1400B4680
0x1400b4520  lea     rcx, [rbp+48h]; Object
0x1400b4524  mov     [rsp+88h+Timeout], r14; Timeout
0x1400b4529  xor     r9d, r9d; Alertable
0x1400b452c  xor     r8d, r8d; WaitMode
0x1400b452f  xor     edx, edx; WaitReason
0x1400b4531  call    cs:__imp_KeWaitForSingleObject
0x1400b4538  nop     dword ptr [rax+rax+00h]
0x1400b453d  lea     r9, [rsp+88h+arg_8]; unsigned int *
0x1400b4545  mov     rdx, rsi; struct _VHD_MIRROR_COPY_THREAD_CONTEXT *
0x1400b4548  lea     r8, [rsp+88h+arg_10]; unsigned __int64 *
0x1400b4550  mov     rcx, rbp; struct _VHD_INTERNAL_ASYNC_MIRROR_COPY_CONTEXT *
0x1400b4553  call    ?VhdmpiMirrorGetNextCopyRangeAndHold@@YAJPEAU_VHD_INTERNAL_ASYNC_MIRROR_COPY_CONTEXT@@PEAU_VHD_MIRROR_COPY_THREAD_CONTEXT@@PEA_KPEAK@Z; VhdmpiMirrorGetNextCopyRangeAndHold(_VHD_INTERNAL_ASYNC_MIRROR_COPY_CONTEXT *,_VHD_MIRROR_COPY_THREAD_CONTEXT *,unsigned __int64 *,ulong *)
0x1400b4558  test    eax, eax
0x1400b455a  js      loc_1400B4652
0x1400b4560  lea     r12, [rsi+158h]
0x1400b4567  lea     r14, [rdi+88h]
0x1400b456e  mov     rcx, rdi; struct _VHD_ASYNC_OP_CONTEXT *
0x1400b4571  call    ?VhdmpiGetAsyncOpOverrideStatus@@YAJPEAU_VHD_ASYNC_OP_CONTEXT@@@Z; VhdmpiGetAsyncOpOverrideStatus(_VHD_ASYNC_OP_CONTEXT *)
0x1400b4576  mov     ebx, eax
0x1400b4578  test    eax, eax
0x1400b457a  js      loc_1400B47A2
0x1400b4580  cmp     dword ptr [rdi+2F8h], 0
0x1400b4587  jl      loc_1400B478B
0x1400b458d  mov     r8, [rdi+68h]
0x1400b4591  mov     r15, [rsp+88h+arg_10]
0x1400b4599  mov     ecx, [rdi+0C0h]
0x1400b459f  mov     rdx, r15
0x1400b45a2  sub     rdx, rcx
0x1400b45a5  mov     rax, r8
0x1400b45a8  lock cmpxchg [rdi+68h], rdx
0x1400b45ae  mov     r8, rax
0x1400b45b1  mov     rcx, r15
0x1400b45b4  mov     eax, [rdi+0C0h]
0x1400b45ba  sub     rcx, rax
0x1400b45bd  cmp     r8, rcx
0x1400b45c0  jb      short loc_1400B4599
0x1400b45c2  mov     r13d, [rsp+88h+arg_8]
0x1400b45ca  lea     rdx, [rsi+30h]; struct _VHD_INTERNAL_IO_CONTEXT *
0x1400b45ce  mov     r9d, r13d; unsigned int
0x1400b45d1  mov     byte ptr [rsp+88h+Timeout], 1; unsigned __int8
0x1400b45d6  mov     r8, r15; unsigned __int64
0x1400b45d9  mov     rcx, rdi; struct _VHD_MIRROR_CONTEXT *
0x1400b45dc  call    ?VhdmpiCopyVirtualBlock@@YAJPEAU_VHD_MIRROR_CONTEXT@@PEAU_VHD_INTERNAL_IO_CONTEXT@@_KKE@Z; VhdmpiCopyVirtualBlock(_VHD_MIRROR_CONTEXT *,_VHD_INTERNAL_IO_CONTEXT *,unsigned __int64,ulong,uchar)
0x1400b45e1  lea     r14, [rdi+88h]
0x1400b45e8  mov     rdx, r12
0x1400b45eb  mov     rcx, [r14]
0x1400b45ee  mov     ebx, eax
0x1400b45f0  add     rcx, 180h; RunRef
0x1400b45f7  call    VhdmpiProcessEventComplete
0x1400b45fc  test    ebx, ebx
0x1400b45fe  js      loc_1400B4722
0x1400b4604  inc     [rsp+88h+arg_0]
0x1400b460b  lea     rcx, [rdi+318h]; Object
0x1400b4612  xor     r9d, r9d; Alertable
0x1400b4615  mov     [rsp+88h+Timeout], 0; Timeout
0x1400b461e  xor     r8d, r8d; WaitMode
0x1400b4621  xor     edx, edx; WaitReason
0x1400b4623  call    cs:__imp_KeWaitForSingleObject
0x1400b462a  nop     dword ptr [rax+rax+00h]
0x1400b462f  lea     r9, [rsp+88h+arg_8]; unsigned int *
0x1400b4637  mov     rdx, rsi; struct _VHD_MIRROR_COPY_THREAD_CONTEXT *
0x1400b463a  lea     r8, [rsp+88h+arg_10]; unsigned __int64 *
0x1400b4642  mov     rcx, rbp; struct _VHD_INTERNAL_ASYNC_MIRROR_COPY_CONTEXT *
0x1400b4645  call    ?VhdmpiMirrorGetNextCopyRangeAndHold@@YAJPEAU_VHD_INTERNAL_ASYNC_MIRROR_COPY_CONTEXT@@PEAU_VHD_MIRROR_COPY_THREAD_CONTEXT@@PEA_KPEAK@Z; VhdmpiMirrorGetNextCopyRangeAndHold(_VHD_INTERNAL_ASYNC_MIRROR_COPY_CONTEXT *,_VHD_MIRROR_COPY_THREAD_CONTEXT *,unsigned __int64 *,ulong *)
0x1400b464a  test    eax, eax
0x1400b464c  jns     loc_1400B456E
0x1400b4652  xor     ebx, ebx
0x1400b4654  cmp     eax, 0C0000011h
0x1400b4659  cmovnz  ebx, eax
0x1400b465c  xor     r9d, r9d; Wait
0x1400b465f  lea     rcx, [rdi+318h]; Semaphore
0x1400b4666  xor     edx, edx; Increment
0x1400b4668  lea     r8d, [r9+1]; Adjustment
0x1400b466c  call    cs:__imp_KeReleaseSemaphore
0x1400b4673  nop     dword ptr [rax+rax+00h]
0x1400b4678  mov     r14d, [rsp+88h+arg_0]
0x1400b4680  mov     [rsi+150h], ebx
0x1400b4686  mov     eax, cs:dword_140087708
0x1400b468c  cmp     eax, 5
0x1400b468f  jbe     short loc_1400B46DD
0x1400b4691  mov     edx, 40000h
0x1400b4696  lea     rcx, dword_140087708
0x1400b469d  call    _tlgKeywordOn
0x1400b46a2  test    al, al
0x1400b46a4  jz      short loc_1400B46DD
0x1400b46a6  mov     [rsp+88h+var_50], ebx
0x1400b46aa  lea     rax, aMirrorWorkerth; "Mirror WorkerThread (context %p) copied"...
0x1400b46b1  mov     dword ptr [rsp+88h+var_58], r14d
0x1400b46b6  lea     rcx, aVhdmpimirrorco; "VhdmpiMirrorCopyThread"
0x1400b46bd  mov     qword ptr [rsp+88h+var_60], rsi; char
0x1400b46c2  mov     edx, 63Dh; int
0x1400b46c7  mov     r9d, 40000h; int
0x1400b46cd  mov     [rsp+88h+Timeout], rax; char *
0x1400b46d2  mov     r8d, 5; int
0x1400b46d8  call    TraceEvents
0x1400b46dd  test    ebx, ebx
0x1400b46df  jns     short loc_1400B46E8
0x1400b46e1  xor     eax, eax
0x1400b46e3  lock cmpxchg [rbp+28h], ebx
0x1400b46e8  lea     rcx, [rdi+308h]; RunRef
0x1400b46ef  call    cs:__imp_ExReleaseRundownProtection
0x1400b46f6  nop     dword ptr [rax+rax+00h]
0x1400b46fb  xor     ecx, ecx; ExitStatus
0x1400b46fd  call    cs:__imp_PsTerminateSystemThread
0x1400b4704  nop     dword ptr [rax+rax+00h]
0x1400b4709  mov     rbx, [rsp+88h+arg_18]
0x1400b4711  add     rsp, 50h
0x1400b4715  pop     r15
0x1400b4717  pop     r14
0x1400b4719  pop     r13
0x1400b471b  pop     r12
0x1400b471d  pop     rdi
0x1400b471e  pop     rsi
0x1400b471f  pop     rbp
0x1400b4720  retn
0x1400b4722  mov     eax, cs:dword_140087708
0x1400b4728  mov     r8d, 2
0x1400b472e  cmp     eax, r8d
0x1400b4731  jbe     loc_1400B4678
0x1400b4737  mov     edx, 40000h
0x1400b473c  lea     rcx, dword_140087708
0x1400b4743  call    _tlgKeywordOn
0x1400b4748  test    al, al
0x1400b474a  jz      loc_1400B4678
0x1400b4750  mov     [rsp+88h+var_48], ebx
0x1400b4754  lea     rax, aMirrorWorkerth_1; "Mirror WorkerThread (context %p) CopyVi"...
0x1400b475b  mov     [rsp+88h+var_50], r13d
0x1400b4760  lea     rcx, aVhdmpimirrorco; "VhdmpiMirrorCopyThread"
0x1400b4767  mov     [rsp+88h+var_58], r15
0x1400b476c  mov     edx, 62Bh; int
0x1400b4771  mov     qword ptr [rsp+88h+var_60], rsi; char
0x1400b4776  mov     r9d, 40000h; int
0x1400b477c  mov     [rsp+88h+Timeout], rax; char *
0x1400b4781  call    TraceEvents
0x1400b4786  jmp     loc_1400B4678
0x1400b478b  mov     rcx, [r14]
0x1400b478e  mov     rdx, r12
0x1400b4791  add     rcx, 180h; RunRef
0x1400b4798  call    VhdmpiProcessEventComplete
0x1400b479d  jmp     loc_1400B465C
0x1400b47a2  mov     rcx, [r14]
0x1400b47a5  mov     rdx, r12
0x1400b47a8  add     rcx, 180h; RunRef
0x1400b47af  call    VhdmpiProcessEventComplete
0x1400b47b4  mov     eax, cs:dword_140087708
0x1400b47ba  mov     r8d, 3
0x1400b47c0  cmp     eax, r8d
0x1400b47c3  jbe     loc_1400B465C
0x1400b47c9  mov     edx, 40000h
0x1400b47ce  lea     rcx, dword_140087708
0x1400b47d5  call    _tlgKeywordOn
0x1400b47da  test    al, al
0x1400b47dc  jz      loc_1400B465C
0x1400b47e2  lea     rax, aMirrorWorkerth_2; "Mirror WorkerThread (context %p) AsyncO"...
0x1400b47e9  mov     qword ptr [rsp+88h+var_60], rsi; char
0x1400b47ee  mov     edx, 5FBh; int
0x1400b47f3  mov     [rsp+88h+Timeout], rax; char *
0x1400b47f8  mov     r9d, 40000h; int
0x1400b47fe  lea     rcx, aVhdmpimirrorco; "VhdmpiMirrorCopyThread"
0x1400b4805  call    TraceEvents
0x1400b480a  jmp     loc_1400B465C
```
