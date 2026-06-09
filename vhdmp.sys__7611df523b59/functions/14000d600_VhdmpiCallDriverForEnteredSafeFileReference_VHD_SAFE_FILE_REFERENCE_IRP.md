# VhdmpiCallDriverForEnteredSafeFileReference(_VHD_SAFE_FILE_REFERENCE *,_IRP *)

- ea: `0x14000d600`
- end: `0x14000d90e`
- name: `?VhdmpiCallDriverForEnteredSafeFileReference@@YAJPEAU_VHD_SAFE_FILE_REFERENCE@@PEAU_IRP@@@Z`
- size: `782`
- prototype: `__int64 __fastcall(unsigned __int64, struct _IRP *)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14000cf50`
- `0x14002e0cc`

## callees

- `0x14000d600`
- `0x140012f50`
- `0x14005d7c0`

## import_xrefs

- `ntoskrnl!IofCallDriver` at `0x14000d7e7`
- `ntoskrnl!IofCallDriver` at `0x14000d7e7`
- `ntoskrnl!IoRetrievePriorityInfo` at `0x14000d832`
- `ntoskrnl!IoRetrievePriorityInfo` at `0x14000d832`
- `ntoskrnl!IoApplyPriorityInfoThread` at `0x14000d867`
- `ntoskrnl!IoApplyPriorityInfoThread` at `0x14000d8ab`
- `ntoskrnl!IoApplyPriorityInfoThread` at `0x14000d8f6`
- `ntoskrnl!IoApplyPriorityInfoThread` at `0x14000d867`
- `ntoskrnl!IoApplyPriorityInfoThread` at `0x14000d8ab`
- `ntoskrnl!IoApplyPriorityInfoThread` at `0x14000d8f6`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14000d669`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14000d669`
- `ntoskrnl!IofCompleteRequest` at `0x14000d8db`
- `ntoskrnl!IofCompleteRequest` at `0x14000d8db`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000d68a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000d68a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000d7b7`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000d890`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000d7b7`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000d890`
- `HAL!KeQueryPerformanceCounter` at `0x14000d7d1`
- `HAL!KeQueryPerformanceCounter` at `0x14000d7d1`

## pseudocode

```c
__int64 __fastcall VhdmpiCallDriverForEnteredSafeFileReference(unsigned __int64 a1, struct _IRP *a2)
{
  __int64 v2; // rsi
  bool v3; // r15
  struct _KTHREAD *CurrentThread; // r13
  __int64 CurrentProcessorNumber; // r14
  __int64 v8; // rdi
  KIRQL v9; // al
  KIRQL v10; // r9
  struct _FILE_OBJECT *v11; // rcx
  struct _DEVICE_OBJECT *v12; // r12
  char *v13; // r10
  KSPIN_LOCK *v14; // r10
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  union _IO_STACK_LOCATION::$3F40624FA6BA75D391A2F4D7FEA8ACCF *p_Parameters; // rax
  struct _IO_STACK_LOCATION *v17; // rcx
  struct _IO_STACK_LOCATION *v18; // rcx
  KSPIN_LOCK **v19; // rdx
  _QWORD **FileName; // rdx
  LARGE_INTEGER *v21; // rdi
  unsigned int v22; // edi
  _IO_PRIORITY_INFO PriorityInfo; // [rsp+20h] [rbp-58h] BYREF

  v2 = *(_QWORD *)(a1 + 40);
  v3 = 0;
  PriorityInfo.Size = 16;
  *(_QWORD *)&PriorityInfo.ThreadPriority = 0xFFFF;
  PriorityInfo.IoPriority = IoPriorityNormal;
  CurrentThread = KeGetCurrentThread();
  if ( (*(_DWORD *)(v2 + 144) & 1) == 0
    && IoRetrievePriorityInfo(0, 0, CurrentThread, &PriorityInfo) >= 0
    && PriorityInfo.PagePriority != dword_14008E354 )
  {
    PriorityInfo.PagePriority = dword_14008E354;
    v3 = IoApplyPriorityInfoThread(&PriorityInfo, &PriorityInfo, CurrentThread) >= 0;
  }
  CurrentProcessorNumber = KeGetCurrentProcessorNumberEx(0);
  v8 = 192 * CurrentProcessorNumber;
  v9 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)VhdPerProcData + 24 * CurrentProcessorNumber);
  v10 = v9;
  if ( *(_DWORD *)(v2 + 672) )
  {
    KeReleaseSpinLock((PKSPIN_LOCK)((char *)VhdPerProcData + v8), v9);
    if ( v3 )
      IoApplyPriorityInfoThread(&PriorityInfo, 0, CurrentThread);
    DvExitRundownBarrierEx(a1 + 24, 1);
    --a2->CurrentLocation;
    v22 = -1073741536;
    --a2->Tail.Overlay.CurrentStackLocation;
    a2->IoStatus.Status = -1073741536;
    IofCompleteRequest(a2, 0);
  }
  else
  {
    v11 = *(struct _FILE_OBJECT **)(a1 + 8);
    v12 = *(struct _DEVICE_OBJECT **)(a1 + 16);
    v13 = (char *)VhdPerProcData;
    a2->Tail.Overlay.OriginalFileObject = v11;
    v14 = (KSPIN_LOCK *)&v13[v8];
    a2->Flags |= *(_DWORD *)(v2 + 144);
    CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
    CurrentStackLocation[-1].FileObject = v11;
    CurrentStackLocation[-1].DeviceObject = v12;
    p_Parameters = &CurrentStackLocation[-1].Parameters;
    --a2->Tail.Overlay.CurrentStackLocation;
    --a2->CurrentLocation;
    v17 = a2->Tail.Overlay.CurrentStackLocation;
    *(_OWORD *)&v17[-1].MajorFunction = *(_OWORD *)&v17->MajorFunction;
    *(_OWORD *)&v17[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&v17->Parameters.NotifyDirectoryEx.CompletionFilter;
    *(_OWORD *)(&v17[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&v17->Parameters.SetQuota + 6);
    v17[-1].FileObject = v17->FileObject;
    v17[-1].Control = 0;
    v18 = a2->Tail.Overlay.CurrentStackLocation;
    v18[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)VhdmpiCompleteIrpForEnteredSafeFileReference;
    v18[-1].Context = p_Parameters;
    v18[-1].Control = -32;
    p_Parameters->Create.FileAttributes = CurrentProcessorNumber;
    LODWORD(v18) = p_Parameters->Read.ByteOffset.LowPart;
    p_Parameters->CreatePipe.Parameters = (PNAMED_PIPE_CREATE_PARAMETERS)(a1 | 1);
    p_Parameters->Read.ByteOffset.LowPart = ((unsigned int)v18
                                           ^ ((unsigned int)v18
                                            ^ (((_DWORD)p_Parameters - (_DWORD)a2) << 16))
                                           & 0xFFFF0000)
                                          & 0x7FFFFFFF;
    v19 = (KSPIN_LOCK **)v14[2];
    if ( *v19 != v14 + 1
      || (p_Parameters->WMI.ProviderId = (ULONG_PTR)(v14 + 1),
          p_Parameters->QueryDirectory.FileName = (PUNICODE_STRING)v19,
          *v19 = (KSPIN_LOCK *)p_Parameters,
          v14[2] = (KSPIN_LOCK)p_Parameters,
          p_Parameters->WMI.ProviderId != *(_QWORD *)&p_Parameters->Create.SecurityContext->SecurityQos->ContextTrackingMode)
      || p_Parameters->WMI.ProviderId != **(_QWORD **)(p_Parameters->WMI.ProviderId + 8)
      || (FileName = (_QWORD **)p_Parameters->QueryDirectory.FileName, FileName != (_QWORD **)(*FileName)[1])
      || FileName != (_QWORD **)*FileName[1] )
    {
      __fastfail(3u);
    }
    KeReleaseSpinLock(v14, v10);
    v21 = (LARGE_INTEGER *)a2->Tail.Overlay.DriverContext[3];
    if ( v21 )
      v21[13] = KeQueryPerformanceCounter(0);
    v22 = IofCallDriver(v12, a2);
    if ( v3 )
      IoApplyPriorityInfoThread(&PriorityInfo, 0, CurrentThread);
  }
  return v22;
}

```

## disassembly

```asm
0x14000d600  mov     [rsp+arg_10], rbx
0x14000d605  push    rbp
0x14000d606  push    rsi
0x14000d607  push    rdi
0x14000d608  push    r12
0x14000d60a  push    r13
0x14000d60c  push    r14
0x14000d60e  push    r15
0x14000d610  sub     rsp, 40h
0x14000d614  mov     rax, cs:__security_cookie
0x14000d61b  xor     rax, rsp
0x14000d61e  mov     [rsp+78h+var_48], rax
0x14000d623  mov     rsi, [rcx+28h]
0x14000d627  xor     r15b, r15b
0x14000d62a  mov     [rsp+78h+PriorityInfo.Size], 10h
0x14000d632  mov     r12d, 1
0x14000d638  mov     qword ptr [rsp+78h+PriorityInfo.ThreadPriority], 0FFFFh
0x14000d641  mov     rbx, rdx
0x14000d644  mov     [rsp+78h+PriorityInfo.IoPriority], 2
0x14000d64c  mov     rbp, rcx
0x14000d64f  mov     r13, gs:188h
0x14000d658  mov     eax, [rsi+90h]
0x14000d65e  test    r12b, al
0x14000d661  jz      loc_14000D826
0x14000d667  xor     ecx, ecx; ProcNumber
0x14000d669  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14000d670  nop     dword ptr [rax+rax+00h]
0x14000d675  mov     rcx, cs:VhdPerProcData
0x14000d67c  mov     r14d, eax
0x14000d67f  lea     rdi, [r14+r14*2]
0x14000d683  shl     rdi, 6
0x14000d687  add     rcx, rdi; SpinLock
0x14000d68a  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000d691  nop     dword ptr [rax+rax+00h]
0x14000d696  mov     ecx, [rsi+2A0h]
0x14000d69c  movzx   r9d, al
0x14000d6a0  test    ecx, ecx
0x14000d6a2  jnz     loc_14000D882
0x14000d6a8  mov     rcx, [rbp+8]
0x14000d6ac  lea     rdx, ?VhdmpiCompleteIrpForEnteredSafeFileReference@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z; VhdmpiCompleteIrpForEnteredSafeFileReference(_DEVICE_OBJECT *,_IRP *,void *)
0x14000d6b3  mov     r12, [rbp+10h]
0x14000d6b7  or      rbp, 1
0x14000d6bb  mov     r10, cs:VhdPerProcData
0x14000d6c2  mov     [rbx+0C0h], rcx
0x14000d6c9  add     r10, rdi
0x14000d6cc  mov     eax, [rsi+90h]
0x14000d6d2  or      [rbx+10h], eax
0x14000d6d5  mov     rax, [rbx+0B8h]
0x14000d6dc  mov     [rax-18h], rcx
0x14000d6e0  mov     [rax-20h], r12
0x14000d6e4  add     rax, 0FFFFFFFFFFFFFFC0h
0x14000d6e8  add     qword ptr [rbx+0B8h], 0FFFFFFFFFFFFFFB8h
0x14000d6f0  dec     byte ptr [rbx+43h]
0x14000d6f3  mov     rcx, [rbx+0B8h]
0x14000d6fa  movups  xmm0, xmmword ptr [rcx]
0x14000d6fd  movups  xmmword ptr [rcx-48h], xmm0
0x14000d701  movups  xmm1, xmmword ptr [rcx+10h]
0x14000d705  movups  xmmword ptr [rcx-38h], xmm1
0x14000d709  movups  xmm0, xmmword ptr [rcx+20h]
0x14000d70d  movups  xmmword ptr [rcx-28h], xmm0
0x14000d711  movsd   xmm1, qword ptr [rcx+30h]
0x14000d716  movsd   qword ptr [rcx-18h], xmm1
0x14000d71b  mov     byte ptr [rcx-45h], 0
0x14000d71f  mov     rcx, [rbx+0B8h]
0x14000d726  mov     [rcx-10h], rdx
0x14000d72a  mov     edx, eax
0x14000d72c  sub     edx, ebx
0x14000d72e  mov     [rcx-8], rax
0x14000d732  mov     byte ptr [rcx-45h], 0E0h
0x14000d736  shl     edx, 10h
0x14000d739  mov     [rax+10h], r14w
0x14000d73e  mov     ecx, [rax+10h]
0x14000d741  xor     edx, ecx
0x14000d743  and     edx, 0FFFF0000h
0x14000d749  mov     [rax+18h], rbp
0x14000d74d  xor     edx, ecx
0x14000d74f  lea     rcx, [r10+8]
0x14000d753  btr     edx, 1Fh
0x14000d757  mov     [rax+10h], edx
0x14000d75a  mov     rdx, [rcx+8]
0x14000d75e  cmp     [rdx], rcx
0x14000d761  jnz     loc_14000D907
0x14000d767  mov     [rax], rcx
0x14000d76a  mov     [rax+8], rdx
0x14000d76e  mov     [rdx], rax
0x14000d771  mov     [rcx+8], rax
0x14000d775  mov     r8, [rax]
0x14000d778  mov     rcx, [r8]
0x14000d77b  cmp     r8, [rcx+8]
0x14000d77f  jnz     loc_14000D907
0x14000d785  mov     rdx, [r8+8]
0x14000d789  cmp     r8, [rdx]
0x14000d78c  jnz     loc_14000D907
0x14000d792  mov     rdx, [rax+8]
0x14000d796  mov     rax, [rdx]
0x14000d799  cmp     rdx, [rax+8]
0x14000d79d  jnz     loc_14000D907
0x14000d7a3  mov     rax, [rdx+8]
0x14000d7a7  cmp     rdx, [rax]
0x14000d7aa  jnz     loc_14000D907
0x14000d7b0  movzx   edx, r9b; NewIrql
0x14000d7b4  mov     rcx, r10; SpinLock
0x14000d7b7  call    cs:__imp_KeReleaseSpinLock
0x14000d7be  nop     dword ptr [rax+rax+00h]
0x14000d7c3  mov     rdi, [rbx+90h]
0x14000d7ca  test    rdi, rdi
0x14000d7cd  jz      short loc_14000D7E1
0x14000d7cf  xor     ecx, ecx; PerformanceFrequency
0x14000d7d1  call    cs:__imp_KeQueryPerformanceCounter
0x14000d7d8  nop     dword ptr [rax+rax+00h]
0x14000d7dd  mov     [rdi+68h], rax
0x14000d7e1  mov     rdx, rbx; Irp
0x14000d7e4  mov     rcx, r12; DeviceObject
0x14000d7e7  call    cs:__imp_IofCallDriver
0x14000d7ee  nop     dword ptr [rax+rax+00h]
0x14000d7f3  mov     edi, eax
0x14000d7f5  test    r15b, r15b
0x14000d7f8  jnz     loc_14000D8EC
0x14000d7fe  mov     eax, edi
0x14000d800  mov     rcx, [rsp+78h+var_48]
0x14000d805  xor     rcx, rsp; StackCookie
0x14000d808  call    __security_check_cookie
0x14000d80d  mov     rbx, [rsp+78h+arg_10]
0x14000d815  add     rsp, 40h
0x14000d819  pop     r15
0x14000d81b  pop     r14
0x14000d81d  pop     r13
0x14000d81f  pop     r12
0x14000d821  pop     rdi
0x14000d822  pop     rsi
0x14000d823  pop     rbp
0x14000d824  retn
0x14000d826  lea     r9, [rsp+78h+PriorityInfo]; PriorityInfo
0x14000d82b  mov     r8, r13; Thread
0x14000d82e  xor     edx, edx; FileObject
0x14000d830  xor     ecx, ecx; Irp
0x14000d832  call    cs:__imp_IoRetrievePriorityInfo
0x14000d839  nop     dword ptr [rax+rax+00h]
0x14000d83e  test    eax, eax
0x14000d840  js      loc_14000D667
0x14000d846  mov     eax, cs:dword_14008E354
0x14000d84c  cmp     [rsp+78h+PriorityInfo.PagePriority], eax
0x14000d850  jz      loc_14000D667
0x14000d856  mov     r8, r13; Thread
0x14000d859  mov     [rsp+78h+PriorityInfo.PagePriority], eax
0x14000d85d  lea     rdx, [rsp+78h+PriorityInfo]; OutputPriorityInfo
0x14000d862  lea     rcx, [rsp+78h+PriorityInfo]; InputPriorityInfo
0x14000d867  call    cs:__imp_IoApplyPriorityInfoThread
0x14000d86e  nop     dword ptr [rax+rax+00h]
0x14000d873  test    eax, eax
0x14000d875  movzx   r15d, r15b
0x14000d879  cmovns  r15d, r12d
0x14000d87d  jmp     loc_14000D667
0x14000d882  mov     rcx, cs:VhdPerProcData
0x14000d889  movzx   edx, r9b; NewIrql
0x14000d88d  add     rcx, rdi; SpinLock
0x14000d890  call    cs:__imp_KeReleaseSpinLock
0x14000d897  nop     dword ptr [rax+rax+00h]
0x14000d89c  test    r15b, r15b
0x14000d89f  jz      short loc_14000D8B7
0x14000d8a1  mov     r8, r13; Thread
0x14000d8a4  lea     rcx, [rsp+78h+PriorityInfo]; InputPriorityInfo
0x14000d8a9  xor     edx, edx; OutputPriorityInfo
0x14000d8ab  call    cs:__imp_IoApplyPriorityInfoThread
0x14000d8b2  nop     dword ptr [rax+rax+00h]
0x14000d8b7  lea     rcx, [rbp+18h]
0x14000d8bb  mov     rdx, r12
0x14000d8be  call    DvExitRundownBarrierEx
0x14000d8c3  dec     byte ptr [rbx+43h]
0x14000d8c6  mov     edi, 0C0000120h
0x14000d8cb  add     qword ptr [rbx+0B8h], 0FFFFFFFFFFFFFFB8h
0x14000d8d3  xor     edx, edx; PriorityBoost
0x14000d8d5  mov     rcx, rbx; Irp
0x14000d8d8  mov     [rbx+30h], edi
0x14000d8db  call    cs:__imp_IofCompleteRequest
0x14000d8e2  nop     dword ptr [rax+rax+00h]
0x14000d8e7  jmp     loc_14000D7FE
0x14000d8ec  mov     r8, r13; Thread
0x14000d8ef  lea     rcx, [rsp+78h+PriorityInfo]; InputPriorityInfo
0x14000d8f4  xor     edx, edx; OutputPriorityInfo
0x14000d8f6  call    cs:__imp_IoApplyPriorityInfoThread
0x14000d8fd  nop     dword ptr [rax+rax+00h]
0x14000d902  jmp     loc_14000D7FE
0x14000d907  mov     ecx, 3
0x14000d90c  int     29h; Win8: RtlFailFast(ecx)
```
