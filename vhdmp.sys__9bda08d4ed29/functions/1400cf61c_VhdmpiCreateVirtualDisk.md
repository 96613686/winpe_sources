# VhdmpiCreateVirtualDisk

- ea: `0x1400cf61c`
- end: `0x1400cf9c6`
- name: `VhdmpiCreateVirtualDisk`
- size: `938`
- prototype: ``
- caller_count: `7`
- callee_count: `17`
- tags: `broker_com_uri`

## callers

- `0x1400a3cd0`
- `0x1400c5864`
- `0x1400c5920`
- `0x1400c6c58`
- `0x1400c7b2c`
- `0x1400cdea0`
- `0x1400cf9cc`

## callees

- `0x14001e7d8`
- `0x14001ed6c`
- `0x1400210e0`
- `0x1400224a8`
- `0x1400226d0`
- `0x140023980`
- `0x1400254e4`
- `0x140026e20`
- `0x140027608`
- `0x140032200`
- `0x140034054`
- `0x140035cac`
- `0x140036284`
- `0x140041f40`
- `0x1400ce1a8`
- `0x1400cf61c`
- `0x1400e9508`

## import_xrefs

- `ntoskrnl!KeInitializeSpinLock` at `0x1400cf70a`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400cf7e8`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400cf70a`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400cf7e8`
- `ntoskrnl!ExInitializeRundownProtection` at `0x1400cf80a`
- `ntoskrnl!ExInitializeRundownProtection` at `0x1400cf82f`
- `ntoskrnl!ExInitializeRundownProtection` at `0x1400cf80a`
- `ntoskrnl!ExInitializeRundownProtection` at `0x1400cf82f`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x1400cf819`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x1400cf83e`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x1400cf819`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x1400cf83e`
- `ntoskrnl!ExAllocatePool2` at `0x1400cf697`
- `ntoskrnl!ExAllocatePool2` at `0x1400cf697`
- `ntoskrnl!KeInitializeEvent` at `0x1400cf748`
- `ntoskrnl!KeInitializeEvent` at `0x1400cf748`

## string_xrefs

- `0x1400cf98f`: `VhdmpiCreateVhdVirtualDisk: leaving... 0x%08x`
- `0x1400cf650`: `VhdmpiCreateVhdVirtualDisk: enter...`
- `0x1400cf668`: `VhdmpiCreateVirtualDisk`
- `0x1400cf95f`: `VhdmpiCreateVirtualDisk`
- `0x1400cf9a7`: `VhdmpiCreateVirtualDisk`
- `0x1400cf947`: `VhdmpiCreateVhdVirtualDisk: error occured (0x%x). deleting the context`

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
  signed __int64 v13; // r9
  bool v14; // zf

  if ( (unsigned int)dword_1400876D0 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 16) )
    TraceEvents("VhdmpiCreateVirtualDisk", 0xB78u, 5u, 0x10u, "VhdmpiCreateVhdVirtualDisk: enter...");
  if ( !(unsigned __int8)VhdmpiIncrementDriverUserCount() )
  {
    Guid = -1073741436;
LABEL_17:
    if ( (unsigned int)dword_1400876D0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 16) )
      TraceEvents(
        "VhdmpiCreateVirtualDisk",
        0xC22u,
        2u,
        0x10u,
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
  v13 = _InterlockedIncrement64(&VirtualDiskNextEventIdentifier);
  v14 = (Microsoft_Windows_VHDMPEnableBits & 8) == 0;
  *(_QWORD *)(v6 + 2816) = v13;
  if ( !v14 )
    McTemplateK0p_EtwWriteTransfer(v12, VirtualDiskCreated, 0, v13);
  *a2 = v6;
  Guid = 0;
LABEL_20:
  if ( (unsigned int)dword_1400876D0 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 16) )
    TraceEvents("VhdmpiCreateVirtualDisk", 0xC28u, 5u, 0x10u, "VhdmpiCreateVhdVirtualDisk: leaving... 0x%08x", Guid);
  return (unsigned int)Guid;
}

```

## disassembly

```asm
0x1400cf61c  push    rbx
0x1400cf61e  push    rsi
0x1400cf61f  push    rdi
0x1400cf620  push    r14
0x1400cf622  sub     rsp, 38h
0x1400cf626  mov     eax, cs:dword_1400876D0
0x1400cf62c  mov     rsi, rdx
0x1400cf62f  mov     rbx, rcx
0x1400cf632  mov     r14d, 10h
0x1400cf638  cmp     eax, 5
0x1400cf63b  jbe     short loc_1400CF674
0x1400cf63d  mov     edx, r14d
0x1400cf640  lea     rcx, dword_1400876D0
0x1400cf647  call    _tlgKeywordOn
0x1400cf64c  test    al, al
0x1400cf64e  jz      short loc_1400CF674
0x1400cf650  lea     rax, aVhdmpicreatevh_1; "VhdmpiCreateVhdVirtualDisk: enter..."
0x1400cf657  mov     edx, 0B78h; int
0x1400cf65c  mov     r9d, r14d; int
0x1400cf65f  mov     [rsp+58h+var_38], rax; char *
0x1400cf664  lea     r8d, [r14-0Bh]; int
0x1400cf668  lea     rcx, aVhdmpicreatevi; "VhdmpiCreateVirtualDisk"
0x1400cf66f  call    TraceEvents
0x1400cf674  call    VhdmpiIncrementDriverUserCount
0x1400cf679  test    al, al
0x1400cf67b  jnz     short loc_1400CF687
0x1400cf67d  mov     ebx, 0C0000184h
0x1400cf682  jmp     loc_1400CF929
0x1400cf687  mov     edx, 0B40h
0x1400cf68c  mov     ecx, 48h ; 'H'
0x1400cf691  mov     r8d, 63444856h
0x1400cf697  call    cs:__imp_ExAllocatePool2
0x1400cf69e  nop     dword ptr [rax+rax+00h]
0x1400cf6a3  mov     rdi, rax
0x1400cf6a6  test    rax, rax
0x1400cf6a9  jnz     short loc_1400CF6BA
0x1400cf6ab  call    VhdmpiDecrementDriverUserCount
0x1400cf6b0  mov     ebx, 0C000009Ah
0x1400cf6b5  jmp     loc_1400CF929
0x1400cf6ba  test    rbx, rbx
0x1400cf6bd  jz      short loc_1400CF6C7
0x1400cf6bf  movups  xmm0, xmmword ptr [rbx]
0x1400cf6c2  movdqu  xmmword ptr [rax+10h], xmm0
0x1400cf6c7  add     rax, 5C0h
0x1400cf6cd  mov     [rdi+8], rdi
0x1400cf6d1  lea     rcx, VhdmpiSrbProcessingRoutine
0x1400cf6d8  mov     [rdi], rdi
0x1400cf6db  mov     [rax+28h], rcx
0x1400cf6df  lea     rcx, ?VhdmpiMultiTriggerThreadPoolWorkerRoutine@@YAXPEAU_VHD_THREAD_POOL_WORK_ITEM@@@Z; VhdmpiMultiTriggerThreadPoolWorkerRoutine(_VHD_THREAD_POOL_WORK_ITEM *)
0x1400cf6e6  mov     [rax+10h], rcx
0x1400cf6ea  lea     rcx, [rdi+128h]; SpinLock
0x1400cf6f1  mov     dword ptr [rax+30h], 0
0x1400cf6f8  mov     dword ptr [rax+20h], 1
0x1400cf6ff  mov     [rax+18h], rax
0x1400cf703  mov     qword ptr [rax], 0
0x1400cf70a  call    cs:__imp_KeInitializeSpinLock
0x1400cf711  nop     dword ptr [rax+rax+00h]
0x1400cf716  lea     rax, [rdi+0A0h]
0x1400cf71d  lea     rcx, [rdi+440h]; SListHead
0x1400cf724  mov     [rax+8], rax
0x1400cf728  mov     [rax], rax
0x1400cf72b  call    VhdmpiDequeueInitialize
0x1400cf730  lea     rcx, [rdi+500h]; SListHead
0x1400cf737  call    VhdmpiDequeueInitialize
0x1400cf73c  lea     rcx, [rdi+368h]; Event
0x1400cf743  xor     r8d, r8d; State
0x1400cf746  xor     edx, edx; Type
0x1400cf748  call    cs:__imp_KeInitializeEvent
0x1400cf74f  nop     dword ptr [rax+rax+00h]
0x1400cf754  lea     rax, [rdi+130h]
0x1400cf75b  mov     [rax+8], rax
0x1400cf75f  lea     rcx, [rdi+60h]
0x1400cf763  mov     [rax], rax
0x1400cf766  lea     rax, [rdi+140h]
0x1400cf76d  mov     [rax+8], rax
0x1400cf771  mov     [rax], rax
0x1400cf774  call    VhdmpiInitializePassiveLock
0x1400cf779  lea     rcx, [rdi+70h]
0x1400cf77d  call    VhdmpiInitializePassiveLock
0x1400cf782  lea     rcx, [rdi+80h]
0x1400cf789  call    VhdmpiInitializePassiveLock
0x1400cf78e  lea     rcx, [rdi+0B8h]
0x1400cf795  call    VhdmpiInitializePassiveLock
0x1400cf79a  lea     rcx, [rdi+9E0h]
0x1400cf7a1  mov     qword ptr [rdi+380h], 0
0x1400cf7ac  call    VhdmpiInitializePassiveLock
0x1400cf7b1  lea     rcx, [rdi+9F0h]
0x1400cf7b8  call    DvInitializeWorkQueue
0x1400cf7bd  lea     rax, [rdi+9F8h]
0x1400cf7c4  lea     rcx, VhdmpiEnsureFirstDataWriteReadyWorkerRoutine
0x1400cf7cb  mov     dword ptr [rax+20h], 2
0x1400cf7d2  mov     [rax+10h], rcx
0x1400cf7d6  lea     rcx, [rdi+0E8h]; SpinLock
0x1400cf7dd  mov     [rax+18h], rax
0x1400cf7e1  mov     qword ptr [rax], 0
0x1400cf7e8  call    cs:__imp_KeInitializeSpinLock
0x1400cf7ef  nop     dword ptr [rax+rax+00h]
0x1400cf7f4  lea     rcx, [rdi+3D8h]
0x1400cf7fb  call    VhdmpiInitializePassiveLock
0x1400cf800  lea     rbx, [rdi+0D8h]
0x1400cf807  mov     rcx, rbx; RunRef
0x1400cf80a  call    cs:__imp_ExInitializeRundownProtection
0x1400cf811  nop     dword ptr [rax+rax+00h]
0x1400cf816  mov     rcx, rbx; RunRef
0x1400cf819  call    cs:__imp_ExWaitForRundownProtectionRelease
0x1400cf820  nop     dword ptr [rax+rax+00h]
0x1400cf825  lea     rbx, [rdi+0E0h]
0x1400cf82c  mov     rcx, rbx; RunRef
0x1400cf82f  call    cs:__imp_ExInitializeRundownProtection
0x1400cf836  nop     dword ptr [rax+rax+00h]
0x1400cf83b  mov     rcx, rbx; RunRef
0x1400cf83e  call    cs:__imp_ExWaitForRundownProtectionRelease
0x1400cf845  nop     dword ptr [rax+rax+00h]
0x1400cf84a  mov     rcx, rdi; DeferredContext
0x1400cf84d  call    VhdmpiCTLogInitTracking
0x1400cf852  mov     r11d, 1
0x1400cf858  lea     rcx, [rdi+980h]
0x1400cf85f  mov     [rdi+120h], r11
0x1400cf866  call    DvInitializeRundownBarrier
0x1400cf86b  mov     dl, r11b
0x1400cf86e  call    DvReleaseRundownBarrier
0x1400cf873  lea     r10, [rdi+998h]
0x1400cf87a  mov     word ptr [rdi+360h], 0
0x1400cf883  lea     rax, VhdmpiExecuteScsiRequestWorkItem
0x1400cf88a  mov     [r10+20h], r11d
0x1400cf88e  lea     rcx, [rdi+388h]; struct VHD_LOW_RESOURCES_QUEUE *
0x1400cf895  mov     [r10+10h], rax
0x1400cf899  mov     [r10+18h], r10
0x1400cf89d  mov     qword ptr [r10], 0
0x1400cf8a4  call    ?VhdmpiInitializeLowResourcesQueue@@YAJPEAUVHD_LOW_RESOURCES_QUEUE@@@Z; VhdmpiInitializeLowResourcesQueue(VHD_LOW_RESOURCES_QUEUE *)
0x1400cf8a9  mov     ebx, eax
0x1400cf8ab  test    eax, eax
0x1400cf8ad  js      short loc_1400CF91D
0x1400cf8af  lea     rcx, [rdi+180h]; RunRef
0x1400cf8b6  mov     rdx, rdi; struct _VHD_VIRTUAL_DISK *
0x1400cf8b9  call    VhdmpiInitializeIoTracker
0x1400cf8be  mov     ebx, eax
0x1400cf8c0  test    eax, eax
0x1400cf8c2  js      short loc_1400CF91D
0x1400cf8c4  lea     rcx, [rdi+0A40h]; struct _IO_PERF_ENTITY_DATA *
0x1400cf8cb  mov     rdx, rdi
0x1400cf8ce  call    IoPerfInitializeEntityData
0x1400cf8d3  lea     rcx, [rdi+970h]; pbBuffer
0x1400cf8da  call    DvGenerateGuid
0x1400cf8df  mov     ebx, eax
0x1400cf8e1  test    eax, eax
0x1400cf8e3  js      short loc_1400CF91D
0x1400cf8e5  mov     r9d, 1
0x1400cf8eb  lock xadd cs:VirtualDiskNextEventIdentifier, r9
0x1400cf8f4  inc     r9
0x1400cf8f7  test    byte ptr cs:Microsoft_Windows_VHDMPEnableBits, 8
0x1400cf8fe  mov     [rdi+0B00h], r9
0x1400cf905  jz      short loc_1400CF916
0x1400cf907  xor     r8d, r8d
0x1400cf90a  lea     rdx, VirtualDiskCreated
0x1400cf911  call    McTemplateK0p_EtwWriteTransfer
0x1400cf916  mov     [rsi], rdi
0x1400cf919  xor     ebx, ebx
0x1400cf91b  jmp     short loc_1400CF971
0x1400cf91d  mov     rcx, rdi; struct _VHD_VIRTUAL_DISK *
0x1400cf920  call    VhdmpiDeleteVirtualDisk
0x1400cf925  test    ebx, ebx
0x1400cf927  jns     short loc_1400CF971
0x1400cf929  mov     eax, cs:dword_1400876D0
0x1400cf92f  cmp     eax, 2
0x1400cf932  jbe     short loc_1400CF971
0x1400cf934  mov     rdx, r14
0x1400cf937  lea     rcx, dword_1400876D0
0x1400cf93e  call    _tlgKeywordOn
0x1400cf943  test    al, al
0x1400cf945  jz      short loc_1400CF971
0x1400cf947  lea     rax, aVhdmpicreatevh; "VhdmpiCreateVhdVirtualDisk: error occur"...
0x1400cf94e  mov     dword ptr [rsp+58h+var_30], ebx; char
0x1400cf952  mov     edx, 0C22h; int
0x1400cf957  mov     [rsp+58h+var_38], rax; char *
0x1400cf95c  mov     r9d, r14d; int
0x1400cf95f  lea     rcx, aVhdmpicreatevi; "VhdmpiCreateVirtualDisk"
0x1400cf966  mov     r8d, 2; int
0x1400cf96c  call    TraceEvents
0x1400cf971  mov     eax, cs:dword_1400876D0
0x1400cf977  cmp     eax, 5
0x1400cf97a  jbe     short loc_1400CF9B9
0x1400cf97c  mov     rdx, r14
0x1400cf97f  lea     rcx, dword_1400876D0
0x1400cf986  call    _tlgKeywordOn
0x1400cf98b  test    al, al
0x1400cf98d  jz      short loc_1400CF9B9
0x1400cf98f  lea     rax, aVhdmpicreatevh_0; "VhdmpiCreateVhdVirtualDisk: leaving... "...
0x1400cf996  mov     dword ptr [rsp+58h+var_30], ebx; char
0x1400cf99a  mov     edx, 0C28h; int
0x1400cf99f  mov     [rsp+58h+var_38], rax; char *
0x1400cf9a4  mov     r9d, r14d; int
0x1400cf9a7  lea     rcx, aVhdmpicreatevi; "VhdmpiCreateVirtualDisk"
0x1400cf9ae  mov     r8d, 5; int
0x1400cf9b4  call    TraceEvents
0x1400cf9b9  mov     eax, ebx
0x1400cf9bb  add     rsp, 38h
0x1400cf9bf  pop     r14
0x1400cf9c1  pop     rdi
0x1400cf9c2  pop     rsi
0x1400cf9c3  pop     rbx
0x1400cf9c4  retn
```
