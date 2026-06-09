# VhdmpiCreateVirtualDisk

- ea: `0x1400cf68c`
- end: `0x1400cfa36`
- name: `VhdmpiCreateVirtualDisk`
- size: `938`
- prototype: `__int64 __fastcall(_OWORD *, __int64 *)`
- caller_count: `7`
- callee_count: `17`
- tags: `broker_com_uri`

## callers

- `0x1400a3cd0`
- `0x1400c5874`
- `0x1400c5930`
- `0x1400c6c68`
- `0x1400c7b3c`
- `0x1400cdf10`
- `0x1400cfa3c`

## callees

- `0x14001e3b8`
- `0x14001e94c`
- `0x140020cc0`
- `0x140022088`
- `0x1400222b0`
- `0x140023560`
- `0x1400250c4`
- `0x140026a00`
- `0x1400270e4`
- `0x140031d40`
- `0x140033b94`
- `0x1400358bc`
- `0x140035e94`
- `0x140041b50`
- `0x1400ce218`
- `0x1400cf68c`
- `0x1400e9578`

## import_xrefs

- `ntoskrnl!KeInitializeSpinLock` at `0x1400cf77a`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400cf858`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400cf77a`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400cf858`
- `ntoskrnl!ExInitializeRundownProtection` at `0x1400cf87a`
- `ntoskrnl!ExInitializeRundownProtection` at `0x1400cf89f`
- `ntoskrnl!ExInitializeRundownProtection` at `0x1400cf87a`
- `ntoskrnl!ExInitializeRundownProtection` at `0x1400cf89f`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x1400cf889`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x1400cf8ae`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x1400cf889`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x1400cf8ae`
- `ntoskrnl!ExAllocatePool2` at `0x1400cf707`
- `ntoskrnl!ExAllocatePool2` at `0x1400cf707`
- `ntoskrnl!KeInitializeEvent` at `0x1400cf7b8`
- `ntoskrnl!KeInitializeEvent` at `0x1400cf7b8`

## string_xrefs

- `0x1400cf6c0`: `VhdmpiCreateVhdVirtualDisk: enter...`
- `0x1400cf6d8`: `VhdmpiCreateVirtualDisk`
- `0x1400cf9cf`: `VhdmpiCreateVirtualDisk`
- `0x1400cfa17`: `VhdmpiCreateVirtualDisk`
- `0x1400cf9b7`: `VhdmpiCreateVhdVirtualDisk: error occured (0x%x). deleting the context`
- `0x1400cf9ff`: `VhdmpiCreateVhdVirtualDisk: leaving... 0x%08x`

## pseudocode

```c
__int64 __fastcall VhdmpiCreateVirtualDisk(_OWORD *a1, __int64 *a2)
{
  int Guid; // ebx
  __int64 Pool2; // rax
  __int64 v6; // rdi
  __int64 v7; // rax
  char v8; // r11
  __int64 v9; // rdx
  __int64 v10; // rcx
  int v11; // r11d
  __int64 v12; // rcx
  bool v13; // zf
  char v15; // [rsp+28h] [rbp-30h]

  if ( (unsigned int)dword_140087708 > 5 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 16) )
    TraceEvents((int)"VhdmpiCreateVirtualDisk", 2936, 5, 16, "VhdmpiCreateVhdVirtualDisk: enter...", v15);
  if ( !(unsigned __int8)VhdmpiIncrementDriverUserCount() )
  {
    Guid = -1073741436;
LABEL_17:
    if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 16) )
      TraceEvents(
        (int)"VhdmpiCreateVirtualDisk",
        3106,
        2,
        16,
        "VhdmpiCreateVhdVirtualDisk: error occured (0x%x). deleting the context",
        Guid);
    goto LABEL_20;
  }
  Pool2 = ExAllocatePool2(72, 2880, 1665419350);
  v6 = Pool2;
  if ( !Pool2 )
  {
    VhdmpiDecrementDriverUserCount();
    Guid = -1073741670;
    goto LABEL_17;
  }
  if ( a1 )
    *(_OWORD *)(Pool2 + 16) = *a1;
  v7 = Pool2 + 1472;
  *(_QWORD *)(v6 + 8) = v6;
  *(_QWORD *)v6 = v6;
  *(_QWORD *)(v7 + 40) = VhdmpiSrbProcessingRoutine;
  *(_QWORD *)(v7 + 16) = VhdmpiMultiTriggerThreadPoolWorkerRoutine;
  *(_DWORD *)(v7 + 48) = 0;
  *(_DWORD *)(v7 + 32) = 1;
  *(_QWORD *)(v7 + 24) = v7;
  *(_QWORD *)v7 = 0;
  KeInitializeSpinLock((PKSPIN_LOCK)(v6 + 296));
  *(_QWORD *)(v6 + 168) = v6 + 160;
  *(_QWORD *)(v6 + 160) = v6 + 160;
  VhdmpiDequeueInitialize((PSLIST_HEADER)(v6 + 1088));
  VhdmpiDequeueInitialize((PSLIST_HEADER)(v6 + 1280));
  KeInitializeEvent((PRKEVENT)(v6 + 872), NotificationEvent, 0);
  *(_QWORD *)(v6 + 312) = v6 + 304;
  *(_QWORD *)(v6 + 304) = v6 + 304;
  *(_QWORD *)(v6 + 328) = v6 + 320;
  *(_QWORD *)(v6 + 320) = v6 + 320;
  VhdmpiInitializePassiveLock(v6 + 96);
  VhdmpiInitializePassiveLock(v6 + 112);
  VhdmpiInitializePassiveLock(v6 + 128);
  VhdmpiInitializePassiveLock(v6 + 184);
  *(_QWORD *)(v6 + 896) = 0;
  VhdmpiInitializePassiveLock(v6 + 2528);
  DvInitializeWorkQueue(v6 + 2544);
  *(_DWORD *)(v6 + 2584) = 2;
  *(_QWORD *)(v6 + 2568) = VhdmpiEnsureFirstDataWriteReadyWorkerRoutine;
  *(_QWORD *)(v6 + 2576) = v6 + 2552;
  *(_QWORD *)(v6 + 2552) = 0;
  KeInitializeSpinLock((PKSPIN_LOCK)(v6 + 232));
  VhdmpiInitializePassiveLock(v6 + 984);
  ExInitializeRundownProtection((PEX_RUNDOWN_REF)(v6 + 216));
  ExWaitForRundownProtectionRelease((PEX_RUNDOWN_REF)(v6 + 216));
  ExInitializeRundownProtection((PEX_RUNDOWN_REF)(v6 + 224));
  ExWaitForRundownProtectionRelease((PEX_RUNDOWN_REF)(v6 + 224));
  VhdmpiCTLogInitTracking((PVOID)v6);
  *(_QWORD *)(v6 + 288) = 1;
  DvInitializeRundownBarrier(v6 + 2432);
  LOBYTE(v9) = v8;
  DvReleaseRundownBarrier(v10, v9);
  *(_WORD *)(v6 + 864) = 0;
  *(_DWORD *)(v6 + 2488) = v11;
  *(_QWORD *)(v6 + 2472) = VhdmpiExecuteScsiRequestWorkItem;
  *(_QWORD *)(v6 + 2480) = v6 + 2456;
  *(_QWORD *)(v6 + 2456) = 0;
  Guid = VhdmpiInitializeLowResourcesQueue((struct VHD_LOW_RESOURCES_QUEUE *)(v6 + 904));
  if ( Guid < 0
    || (Guid = VhdmpiInitializeIoTracker((PEX_RUNDOWN_REF)(v6 + 384), (struct _VHD_VIRTUAL_DISK *)v6), Guid < 0)
    || (IoPerfInitializeEntityData((struct _IO_PERF_ENTITY_DATA *)(v6 + 2624)),
        Guid = DvGenerateGuid((PUCHAR)(v6 + 2416)),
        Guid < 0) )
  {
    VhdmpiDeleteVirtualDisk((struct _VHD_VIRTUAL_DISK *)v6);
    goto LABEL_17;
  }
  v13 = (Microsoft_Windows_VHDMPEnableBits & 8) == 0;
  *(_QWORD *)(v6 + 2816) = _InterlockedIncrement64(&VirtualDiskNextEventIdentifier);
  if ( !v13 )
    McTemplateK0p_EtwWriteTransfer(v12, VirtualDiskCreated, 0);
  *a2 = v6;
  Guid = 0;
LABEL_20:
  if ( (unsigned int)dword_140087708 > 5 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 16) )
    TraceEvents((int)"VhdmpiCreateVirtualDisk", 3112, 5, 16, "VhdmpiCreateVhdVirtualDisk: leaving... 0x%08x", Guid);
  return (unsigned int)Guid;
}

```

## disassembly

```asm
0x1400cf68c  push    rbx
0x1400cf68e  push    rsi
0x1400cf68f  push    rdi
0x1400cf690  push    r14
0x1400cf692  sub     rsp, 38h
0x1400cf696  mov     eax, cs:dword_140087708
0x1400cf69c  mov     rsi, rdx
0x1400cf69f  mov     rbx, rcx
0x1400cf6a2  mov     r14d, 10h
0x1400cf6a8  cmp     eax, 5
0x1400cf6ab  jbe     short loc_1400CF6E4
0x1400cf6ad  mov     edx, r14d
0x1400cf6b0  lea     rcx, dword_140087708
0x1400cf6b7  call    _tlgKeywordOn
0x1400cf6bc  test    al, al
0x1400cf6be  jz      short loc_1400CF6E4
0x1400cf6c0  lea     rax, aVhdmpicreatevh_1; "VhdmpiCreateVhdVirtualDisk: enter..."
0x1400cf6c7  mov     edx, 0B78h; int
0x1400cf6cc  mov     r9d, r14d; int
0x1400cf6cf  mov     [rsp+58h+var_38], rax; char *
0x1400cf6d4  lea     r8d, [r14-0Bh]; int
0x1400cf6d8  lea     rcx, aVhdmpicreatevi; "VhdmpiCreateVirtualDisk"
0x1400cf6df  call    TraceEvents
0x1400cf6e4  call    VhdmpiIncrementDriverUserCount
0x1400cf6e9  test    al, al
0x1400cf6eb  jnz     short loc_1400CF6F7
0x1400cf6ed  mov     ebx, 0C0000184h
0x1400cf6f2  jmp     loc_1400CF999
0x1400cf6f7  mov     edx, 0B40h
0x1400cf6fc  mov     ecx, 48h ; 'H'
0x1400cf701  mov     r8d, 63444856h
0x1400cf707  call    cs:__imp_ExAllocatePool2
0x1400cf70e  nop     dword ptr [rax+rax+00h]
0x1400cf713  mov     rdi, rax
0x1400cf716  test    rax, rax
0x1400cf719  jnz     short loc_1400CF72A
0x1400cf71b  call    VhdmpiDecrementDriverUserCount
0x1400cf720  mov     ebx, 0C000009Ah
0x1400cf725  jmp     loc_1400CF999
0x1400cf72a  test    rbx, rbx
0x1400cf72d  jz      short loc_1400CF737
0x1400cf72f  movups  xmm0, xmmword ptr [rbx]
0x1400cf732  movdqu  xmmword ptr [rax+10h], xmm0
0x1400cf737  add     rax, 5C0h
0x1400cf73d  mov     [rdi+8], rdi
0x1400cf741  lea     rcx, VhdmpiSrbProcessingRoutine
0x1400cf748  mov     [rdi], rdi
0x1400cf74b  mov     [rax+28h], rcx
0x1400cf74f  lea     rcx, ?VhdmpiMultiTriggerThreadPoolWorkerRoutine@@YAXPEAU_VHD_THREAD_POOL_WORK_ITEM@@@Z; VhdmpiMultiTriggerThreadPoolWorkerRoutine(_VHD_THREAD_POOL_WORK_ITEM *)
0x1400cf756  mov     [rax+10h], rcx
0x1400cf75a  lea     rcx, [rdi+128h]; SpinLock
0x1400cf761  mov     dword ptr [rax+30h], 0
0x1400cf768  mov     dword ptr [rax+20h], 1
0x1400cf76f  mov     [rax+18h], rax
0x1400cf773  mov     qword ptr [rax], 0
0x1400cf77a  call    cs:__imp_KeInitializeSpinLock
0x1400cf781  nop     dword ptr [rax+rax+00h]
0x1400cf786  lea     rax, [rdi+0A0h]
0x1400cf78d  lea     rcx, [rdi+440h]; SListHead
0x1400cf794  mov     [rax+8], rax
0x1400cf798  mov     [rax], rax
0x1400cf79b  call    VhdmpiDequeueInitialize
0x1400cf7a0  lea     rcx, [rdi+500h]; SListHead
0x1400cf7a7  call    VhdmpiDequeueInitialize
0x1400cf7ac  lea     rcx, [rdi+368h]; Event
0x1400cf7b3  xor     r8d, r8d; State
0x1400cf7b6  xor     edx, edx; Type
0x1400cf7b8  call    cs:__imp_KeInitializeEvent
0x1400cf7bf  nop     dword ptr [rax+rax+00h]
0x1400cf7c4  lea     rax, [rdi+130h]
0x1400cf7cb  mov     [rax+8], rax
0x1400cf7cf  lea     rcx, [rdi+60h]
0x1400cf7d3  mov     [rax], rax
0x1400cf7d6  lea     rax, [rdi+140h]
0x1400cf7dd  mov     [rax+8], rax
0x1400cf7e1  mov     [rax], rax
0x1400cf7e4  call    VhdmpiInitializePassiveLock
0x1400cf7e9  lea     rcx, [rdi+70h]
0x1400cf7ed  call    VhdmpiInitializePassiveLock
0x1400cf7f2  lea     rcx, [rdi+80h]
0x1400cf7f9  call    VhdmpiInitializePassiveLock
0x1400cf7fe  lea     rcx, [rdi+0B8h]
0x1400cf805  call    VhdmpiInitializePassiveLock
0x1400cf80a  lea     rcx, [rdi+9E0h]
0x1400cf811  mov     qword ptr [rdi+380h], 0
0x1400cf81c  call    VhdmpiInitializePassiveLock
0x1400cf821  lea     rcx, [rdi+9F0h]
0x1400cf828  call    DvInitializeWorkQueue
0x1400cf82d  lea     rax, [rdi+9F8h]
0x1400cf834  lea     rcx, VhdmpiEnsureFirstDataWriteReadyWorkerRoutine
0x1400cf83b  mov     dword ptr [rax+20h], 2
0x1400cf842  mov     [rax+10h], rcx
0x1400cf846  lea     rcx, [rdi+0E8h]; SpinLock
0x1400cf84d  mov     [rax+18h], rax
0x1400cf851  mov     qword ptr [rax], 0
0x1400cf858  call    cs:__imp_KeInitializeSpinLock
0x1400cf85f  nop     dword ptr [rax+rax+00h]
0x1400cf864  lea     rcx, [rdi+3D8h]
0x1400cf86b  call    VhdmpiInitializePassiveLock
0x1400cf870  lea     rbx, [rdi+0D8h]
0x1400cf877  mov     rcx, rbx; RunRef
0x1400cf87a  call    cs:__imp_ExInitializeRundownProtection
0x1400cf881  nop     dword ptr [rax+rax+00h]
0x1400cf886  mov     rcx, rbx; RunRef
0x1400cf889  call    cs:__imp_ExWaitForRundownProtectionRelease
0x1400cf890  nop     dword ptr [rax+rax+00h]
0x1400cf895  lea     rbx, [rdi+0E0h]
0x1400cf89c  mov     rcx, rbx; RunRef
0x1400cf89f  call    cs:__imp_ExInitializeRundownProtection
0x1400cf8a6  nop     dword ptr [rax+rax+00h]
0x1400cf8ab  mov     rcx, rbx; RunRef
0x1400cf8ae  call    cs:__imp_ExWaitForRundownProtectionRelease
0x1400cf8b5  nop     dword ptr [rax+rax+00h]
0x1400cf8ba  mov     rcx, rdi; DeferredContext
0x1400cf8bd  call    VhdmpiCTLogInitTracking
0x1400cf8c2  mov     r11d, 1
0x1400cf8c8  lea     rcx, [rdi+980h]
0x1400cf8cf  mov     [rdi+120h], r11
0x1400cf8d6  call    DvInitializeRundownBarrier
0x1400cf8db  mov     dl, r11b
0x1400cf8de  call    DvReleaseRundownBarrier
0x1400cf8e3  lea     r10, [rdi+998h]
0x1400cf8ea  mov     word ptr [rdi+360h], 0
0x1400cf8f3  lea     rax, VhdmpiExecuteScsiRequestWorkItem
0x1400cf8fa  mov     [r10+20h], r11d
0x1400cf8fe  lea     rcx, [rdi+388h]; struct VHD_LOW_RESOURCES_QUEUE *
0x1400cf905  mov     [r10+10h], rax
0x1400cf909  mov     [r10+18h], r10
0x1400cf90d  mov     qword ptr [r10], 0
0x1400cf914  call    ?VhdmpiInitializeLowResourcesQueue@@YAJPEAUVHD_LOW_RESOURCES_QUEUE@@@Z; VhdmpiInitializeLowResourcesQueue(VHD_LOW_RESOURCES_QUEUE *)
0x1400cf919  mov     ebx, eax
0x1400cf91b  test    eax, eax
0x1400cf91d  js      short loc_1400CF98D
0x1400cf91f  lea     rcx, [rdi+180h]; RunRef
0x1400cf926  mov     rdx, rdi; struct _VHD_VIRTUAL_DISK *
0x1400cf929  call    VhdmpiInitializeIoTracker
0x1400cf92e  mov     ebx, eax
0x1400cf930  test    eax, eax
0x1400cf932  js      short loc_1400CF98D
0x1400cf934  lea     rcx, [rdi+0A40h]; struct _IO_PERF_ENTITY_DATA *
0x1400cf93b  mov     rdx, rdi
0x1400cf93e  call    IoPerfInitializeEntityData
0x1400cf943  lea     rcx, [rdi+970h]; pbBuffer
0x1400cf94a  call    DvGenerateGuid
0x1400cf94f  mov     ebx, eax
0x1400cf951  test    eax, eax
0x1400cf953  js      short loc_1400CF98D
0x1400cf955  mov     r9d, 1
0x1400cf95b  lock xadd cs:VirtualDiskNextEventIdentifier, r9
0x1400cf964  inc     r9
0x1400cf967  test    byte ptr cs:Microsoft_Windows_VHDMPEnableBits, 8
0x1400cf96e  mov     [rdi+0B00h], r9
0x1400cf975  jz      short loc_1400CF986
0x1400cf977  xor     r8d, r8d
0x1400cf97a  lea     rdx, VirtualDiskCreated
0x1400cf981  call    McTemplateK0p_EtwWriteTransfer
0x1400cf986  mov     [rsi], rdi
0x1400cf989  xor     ebx, ebx
0x1400cf98b  jmp     short loc_1400CF9E1
0x1400cf98d  mov     rcx, rdi; struct _VHD_VIRTUAL_DISK *
0x1400cf990  call    VhdmpiDeleteVirtualDisk
0x1400cf995  test    ebx, ebx
0x1400cf997  jns     short loc_1400CF9E1
0x1400cf999  mov     eax, cs:dword_140087708
0x1400cf99f  cmp     eax, 2
0x1400cf9a2  jbe     short loc_1400CF9E1
0x1400cf9a4  mov     rdx, r14
0x1400cf9a7  lea     rcx, dword_140087708
0x1400cf9ae  call    _tlgKeywordOn
0x1400cf9b3  test    al, al
0x1400cf9b5  jz      short loc_1400CF9E1
0x1400cf9b7  lea     rax, aVhdmpicreatevh; "VhdmpiCreateVhdVirtualDisk: error occur"...
0x1400cf9be  mov     dword ptr [rsp+58h+var_30], ebx; char
0x1400cf9c2  mov     edx, 0C22h; int
0x1400cf9c7  mov     [rsp+58h+var_38], rax; char *
0x1400cf9cc  mov     r9d, r14d; int
0x1400cf9cf  lea     rcx, aVhdmpicreatevi; "VhdmpiCreateVirtualDisk"
0x1400cf9d6  mov     r8d, 2; int
0x1400cf9dc  call    TraceEvents
0x1400cf9e1  mov     eax, cs:dword_140087708
0x1400cf9e7  cmp     eax, 5
0x1400cf9ea  jbe     short loc_1400CFA29
0x1400cf9ec  mov     rdx, r14
0x1400cf9ef  lea     rcx, dword_140087708
0x1400cf9f6  call    _tlgKeywordOn
0x1400cf9fb  test    al, al
0x1400cf9fd  jz      short loc_1400CFA29
0x1400cf9ff  lea     rax, aVhdmpicreatevh_0; "VhdmpiCreateVhdVirtualDisk: leaving... "...
0x1400cfa06  mov     dword ptr [rsp+58h+var_30], ebx; char
0x1400cfa0a  mov     edx, 0C28h; int
0x1400cfa0f  mov     [rsp+58h+var_38], rax; char *
0x1400cfa14  mov     r9d, r14d; int
0x1400cfa17  lea     rcx, aVhdmpicreatevi; "VhdmpiCreateVirtualDisk"
0x1400cfa1e  mov     r8d, 5; int
0x1400cfa24  call    TraceEvents
0x1400cfa29  mov     eax, ebx
0x1400cfa2b  add     rsp, 38h
0x1400cfa2f  pop     r14
0x1400cfa31  pop     rdi
0x1400cfa32  pop     rsi
0x1400cfa33  pop     rbx
0x1400cfa34  retn
```
