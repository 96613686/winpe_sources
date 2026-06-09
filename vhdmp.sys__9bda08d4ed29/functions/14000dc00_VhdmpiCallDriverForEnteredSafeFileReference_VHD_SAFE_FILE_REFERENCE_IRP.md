# VhdmpiCallDriverForEnteredSafeFileReference(_VHD_SAFE_FILE_REFERENCE *,_IRP *)

- ea: `0x14000dc00`
- end: `0x14000df0e`
- name: `?VhdmpiCallDriverForEnteredSafeFileReference@@YAJPEAU_VHD_SAFE_FILE_REFERENCE@@PEAU_IRP@@@Z`
- size: `782`
- prototype: `int(struct _VHD_SAFE_FILE_REFERENCE *, struct _IRP *)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14000d550`
- `0x14002e58c`

## callees

- `0x14000dc00`
- `0x1400109d0`
- `0x14005dbb0`

## import_xrefs

- `ntoskrnl!IofCallDriver` at `0x14000dde7`
- `ntoskrnl!IofCallDriver` at `0x14000dde7`
- `ntoskrnl!IoRetrievePriorityInfo` at `0x14000de32`
- `ntoskrnl!IoRetrievePriorityInfo` at `0x14000de32`
- `ntoskrnl!IoApplyPriorityInfoThread` at `0x14000de67`
- `ntoskrnl!IoApplyPriorityInfoThread` at `0x14000deab`
- `ntoskrnl!IoApplyPriorityInfoThread` at `0x14000def6`
- `ntoskrnl!IoApplyPriorityInfoThread` at `0x14000de67`
- `ntoskrnl!IoApplyPriorityInfoThread` at `0x14000deab`
- `ntoskrnl!IoApplyPriorityInfoThread` at `0x14000def6`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14000dc69`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14000dc69`
- `ntoskrnl!IofCompleteRequest` at `0x14000dedb`
- `ntoskrnl!IofCompleteRequest` at `0x14000dedb`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000dc8a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000dc8a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000ddb7`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000de90`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000ddb7`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000de90`
- `HAL!KeQueryPerformanceCounter` at `0x14000ddd1`
- `HAL!KeQueryPerformanceCounter` at `0x14000ddd1`

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
0x14000dc00  mov     [rsp+arg_10], rbx
0x14000dc05  push    rbp
0x14000dc06  push    rsi
0x14000dc07  push    rdi
0x14000dc08  push    r12
0x14000dc0a  push    r13
0x14000dc0c  push    r14
0x14000dc0e  push    r15
0x14000dc10  sub     rsp, 40h
0x14000dc14  mov     rax, cs:__security_cookie
0x14000dc1b  xor     rax, rsp
0x14000dc1e  mov     [rsp+78h+var_48], rax
0x14000dc23  mov     rsi, [rcx+28h]
0x14000dc27  xor     r15b, r15b
0x14000dc2a  mov     [rsp+78h+PriorityInfo.Size], 10h
0x14000dc32  mov     r12d, 1
0x14000dc38  mov     qword ptr [rsp+78h+PriorityInfo.ThreadPriority], 0FFFFh
0x14000dc41  mov     rbx, rdx
0x14000dc44  mov     [rsp+78h+PriorityInfo.IoPriority], 2
0x14000dc4c  mov     rbp, rcx
0x14000dc4f  mov     r13, gs:188h
0x14000dc58  mov     eax, [rsi+90h]
0x14000dc5e  test    r12b, al
0x14000dc61  jz      loc_14000DE26
0x14000dc67  xor     ecx, ecx; ProcNumber
0x14000dc69  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14000dc70  nop     dword ptr [rax+rax+00h]
0x14000dc75  mov     rcx, cs:VhdPerProcData
0x14000dc7c  mov     r14d, eax
0x14000dc7f  lea     rdi, [r14+r14*2]
0x14000dc83  shl     rdi, 6
0x14000dc87  add     rcx, rdi; SpinLock
0x14000dc8a  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000dc91  nop     dword ptr [rax+rax+00h]
0x14000dc96  mov     ecx, [rsi+2A0h]
0x14000dc9c  movzx   r9d, al
0x14000dca0  test    ecx, ecx
0x14000dca2  jnz     loc_14000DE82
0x14000dca8  mov     rcx, [rbp+8]
0x14000dcac  lea     rdx, ?VhdmpiCompleteIrpForEnteredSafeFileReference@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z; VhdmpiCompleteIrpForEnteredSafeFileReference(_DEVICE_OBJECT *,_IRP *,void *)
0x14000dcb3  mov     r12, [rbp+10h]
0x14000dcb7  or      rbp, 1
0x14000dcbb  mov     r10, cs:VhdPerProcData
0x14000dcc2  mov     [rbx+0C0h], rcx
0x14000dcc9  add     r10, rdi
0x14000dccc  mov     eax, [rsi+90h]
0x14000dcd2  or      [rbx+10h], eax
0x14000dcd5  mov     rax, [rbx+0B8h]
0x14000dcdc  mov     [rax-18h], rcx
0x14000dce0  mov     [rax-20h], r12
0x14000dce4  add     rax, 0FFFFFFFFFFFFFFC0h
0x14000dce8  add     qword ptr [rbx+0B8h], 0FFFFFFFFFFFFFFB8h
0x14000dcf0  dec     byte ptr [rbx+43h]
0x14000dcf3  mov     rcx, [rbx+0B8h]
0x14000dcfa  movups  xmm0, xmmword ptr [rcx]
0x14000dcfd  movups  xmmword ptr [rcx-48h], xmm0
0x14000dd01  movups  xmm1, xmmword ptr [rcx+10h]
0x14000dd05  movups  xmmword ptr [rcx-38h], xmm1
0x14000dd09  movups  xmm0, xmmword ptr [rcx+20h]
0x14000dd0d  movups  xmmword ptr [rcx-28h], xmm0
0x14000dd11  movsd   xmm1, qword ptr [rcx+30h]
0x14000dd16  movsd   qword ptr [rcx-18h], xmm1
0x14000dd1b  mov     byte ptr [rcx-45h], 0
0x14000dd1f  mov     rcx, [rbx+0B8h]
0x14000dd26  mov     [rcx-10h], rdx
0x14000dd2a  mov     edx, eax
0x14000dd2c  sub     edx, ebx
0x14000dd2e  mov     [rcx-8], rax
0x14000dd32  mov     byte ptr [rcx-45h], 0E0h
0x14000dd36  shl     edx, 10h
0x14000dd39  mov     [rax+10h], r14w
0x14000dd3e  mov     ecx, [rax+10h]
0x14000dd41  xor     edx, ecx
0x14000dd43  and     edx, 0FFFF0000h
0x14000dd49  mov     [rax+18h], rbp
0x14000dd4d  xor     edx, ecx
0x14000dd4f  lea     rcx, [r10+8]
0x14000dd53  btr     edx, 1Fh
0x14000dd57  mov     [rax+10h], edx
0x14000dd5a  mov     rdx, [rcx+8]
0x14000dd5e  cmp     [rdx], rcx
0x14000dd61  jnz     loc_14000DF07
0x14000dd67  mov     [rax], rcx
0x14000dd6a  mov     [rax+8], rdx
0x14000dd6e  mov     [rdx], rax
0x14000dd71  mov     [rcx+8], rax
0x14000dd75  mov     r8, [rax]
0x14000dd78  mov     rcx, [r8]
0x14000dd7b  cmp     r8, [rcx+8]
0x14000dd7f  jnz     loc_14000DF07
0x14000dd85  mov     rdx, [r8+8]
0x14000dd89  cmp     r8, [rdx]
0x14000dd8c  jnz     loc_14000DF07
0x14000dd92  mov     rdx, [rax+8]
0x14000dd96  mov     rax, [rdx]
0x14000dd99  cmp     rdx, [rax+8]
0x14000dd9d  jnz     loc_14000DF07
0x14000dda3  mov     rax, [rdx+8]
0x14000dda7  cmp     rdx, [rax]
0x14000ddaa  jnz     loc_14000DF07
0x14000ddb0  movzx   edx, r9b; NewIrql
0x14000ddb4  mov     rcx, r10; SpinLock
0x14000ddb7  call    cs:__imp_KeReleaseSpinLock
0x14000ddbe  nop     dword ptr [rax+rax+00h]
0x14000ddc3  mov     rdi, [rbx+90h]
0x14000ddca  test    rdi, rdi
0x14000ddcd  jz      short loc_14000DDE1
0x14000ddcf  xor     ecx, ecx; PerformanceFrequency
0x14000ddd1  call    cs:__imp_KeQueryPerformanceCounter
0x14000ddd8  nop     dword ptr [rax+rax+00h]
0x14000dddd  mov     [rdi+68h], rax
0x14000dde1  mov     rdx, rbx; Irp
0x14000dde4  mov     rcx, r12; DeviceObject
0x14000dde7  call    cs:__imp_IofCallDriver
0x14000ddee  nop     dword ptr [rax+rax+00h]
0x14000ddf3  mov     edi, eax
0x14000ddf5  test    r15b, r15b
0x14000ddf8  jnz     loc_14000DEEC
0x14000ddfe  mov     eax, edi
0x14000de00  mov     rcx, [rsp+78h+var_48]
0x14000de05  xor     rcx, rsp; StackCookie
0x14000de08  call    __security_check_cookie
0x14000de0d  mov     rbx, [rsp+78h+arg_10]
0x14000de15  add     rsp, 40h
0x14000de19  pop     r15
0x14000de1b  pop     r14
0x14000de1d  pop     r13
0x14000de1f  pop     r12
0x14000de21  pop     rdi
0x14000de22  pop     rsi
0x14000de23  pop     rbp
0x14000de24  retn
0x14000de26  lea     r9, [rsp+78h+PriorityInfo]; PriorityInfo
0x14000de2b  mov     r8, r13; Thread
0x14000de2e  xor     edx, edx; FileObject
0x14000de30  xor     ecx, ecx; Irp
0x14000de32  call    cs:__imp_IoRetrievePriorityInfo
0x14000de39  nop     dword ptr [rax+rax+00h]
0x14000de3e  test    eax, eax
0x14000de40  js      loc_14000DC67
0x14000de46  mov     eax, cs:dword_14008E354
0x14000de4c  cmp     [rsp+78h+PriorityInfo.PagePriority], eax
0x14000de50  jz      loc_14000DC67
0x14000de56  mov     r8, r13; Thread
0x14000de59  mov     [rsp+78h+PriorityInfo.PagePriority], eax
0x14000de5d  lea     rdx, [rsp+78h+PriorityInfo]; OutputPriorityInfo
0x14000de62  lea     rcx, [rsp+78h+PriorityInfo]; InputPriorityInfo
0x14000de67  call    cs:__imp_IoApplyPriorityInfoThread
0x14000de6e  nop     dword ptr [rax+rax+00h]
0x14000de73  test    eax, eax
0x14000de75  movzx   r15d, r15b
0x14000de79  cmovns  r15d, r12d
0x14000de7d  jmp     loc_14000DC67
0x14000de82  mov     rcx, cs:VhdPerProcData
0x14000de89  movzx   edx, r9b; NewIrql
0x14000de8d  add     rcx, rdi; SpinLock
0x14000de90  call    cs:__imp_KeReleaseSpinLock
0x14000de97  nop     dword ptr [rax+rax+00h]
0x14000de9c  test    r15b, r15b
0x14000de9f  jz      short loc_14000DEB7
0x14000dea1  mov     r8, r13; Thread
0x14000dea4  lea     rcx, [rsp+78h+PriorityInfo]; InputPriorityInfo
0x14000dea9  xor     edx, edx; OutputPriorityInfo
0x14000deab  call    cs:__imp_IoApplyPriorityInfoThread
0x14000deb2  nop     dword ptr [rax+rax+00h]
0x14000deb7  lea     rcx, [rbp+18h]
0x14000debb  mov     rdx, r12
0x14000debe  call    DvExitRundownBarrierEx
0x14000dec3  dec     byte ptr [rbx+43h]
0x14000dec6  mov     edi, 0C0000120h
0x14000decb  add     qword ptr [rbx+0B8h], 0FFFFFFFFFFFFFFB8h
0x14000ded3  xor     edx, edx; PriorityBoost
0x14000ded5  mov     rcx, rbx; Irp
0x14000ded8  mov     [rbx+30h], edi
0x14000dedb  call    cs:__imp_IofCompleteRequest
0x14000dee2  nop     dword ptr [rax+rax+00h]
0x14000dee7  jmp     loc_14000DDFE
0x14000deec  mov     r8, r13; Thread
0x14000deef  lea     rcx, [rsp+78h+PriorityInfo]; InputPriorityInfo
0x14000def4  xor     edx, edx; OutputPriorityInfo
0x14000def6  call    cs:__imp_IoApplyPriorityInfoThread
0x14000defd  nop     dword ptr [rax+rax+00h]
0x14000df02  jmp     loc_14000DDFE
0x14000df07  mov     ecx, 3
0x14000df0c  int     29h; Win8: RtlFailFast(ecx)
```
