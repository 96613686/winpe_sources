# VmsQsMgmtInitializeDeferredQueue

- ea: `0x1401b08ec`
- end: `0x1401b0a74`
- name: `VmsQsMgmtInitializeDeferredQueue`
- size: `392`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, installer_update`

## callers

- `0x1401adc04`

## callees

- `0x14003a450`
- `0x1401b08ec`
- `0x1401bc2c0`

## import_xrefs

- `ntoskrnl!PsCreateSystemThread` at `0x1401b09d1`
- `ntoskrnl!PsCreateSystemThread` at `0x1401b09d1`
- `ntoskrnl!InitializeSListHead` at `0x1401b092c`
- `ntoskrnl!InitializeSListHead` at `0x1401b092c`
- `ntoskrnl!KeInitializeEvent` at `0x1401b0946`
- `ntoskrnl!KeInitializeEvent` at `0x1401b0946`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x1401b0990`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x1401b0990`
- `ntoskrnl!ZwClose` at `0x1401b0a56`
- `ntoskrnl!ZwClose` at `0x1401b0a56`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1401b0a39`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1401b0a39`

## pseudocode

```c
__int64 VmsQsMgmtInitializeDeferredQueue()
{
  NTSTATUS v0; // eax
  int v1; // edx
  unsigned int v2; // ebx
  void *ThreadHandle; // [rsp+50h] [rbp+8h] BYREF
  PVOID Object; // [rsp+58h] [rbp+10h] BYREF

  ThreadHandle = 0;
  byte_1401FA8B0 = 0;
  byte_1401FA8B1 = 0;
  byte_1401F98F9 = 0;
  dword_1401F9948 = 0;
  qword_1401FA020 = 0;
  InitializeSListHead(&SListHead);
  KeInitializeEvent(&Event, SynchronizationEvent, 0);
  memset(&Lookaside, 0, sizeof(Lookaside));
  ExInitializeNPagedLookasideList(&Lookaside, 0, 0, 0x200u, 0x50u, 0x77446D56u, 0);
  byte_1401FA8B1 = 1;
  v0 = PsCreateSystemThread(&ThreadHandle, 0x1FFFFFu, 0, 0, 0, VmsQsMgmtDeferredWorkerThread, 0);
  v2 = v0;
  if ( v0 >= 0 )
  {
    Object = 0;
    ObReferenceObjectByHandle(ThreadHandle, 0x1FFFFFu, 0, 0, &Object, 0);
    qword_1401FA020 = Object;
    ZwClose(ThreadHandle);
    v2 = 0;
    byte_1401FA8B0 = 1;
  }
  else
  {
    LOBYTE(v1) = 2;
    WPP_RECORDER_SF_d(VmsIfrLog, v1, 20, 38, (__int64)WPP_9967daa17f81308e3174d8235558202a_Traceguids, v0);
  }
  return v2;
}

```

## disassembly

```asm
0x1401b08ec  push    rbx
0x1401b08ee  sub     rsp, 40h
0x1401b08f2  lea     rcx, SListHead; SListHead
0x1401b08f9  mov     [rsp+48h+ThreadHandle], 0
0x1401b0902  mov     cs:byte_1401FA8B0, 0
0x1401b0909  mov     cs:byte_1401FA8B1, 0
0x1401b0910  mov     cs:byte_1401F98F9, 0
0x1401b0917  mov     cs:dword_1401F9948, 0
0x1401b0921  mov     cs:qword_1401FA020, 0
0x1401b092c  call    cs:__imp_InitializeSListHead
0x1401b0933  nop     dword ptr [rax+rax+00h]
0x1401b0938  xor     r8d, r8d; State
0x1401b093b  lea     rcx, Event; Event
0x1401b0942  lea     edx, [r8+1]; Type
0x1401b0946  call    cs:__imp_KeInitializeEvent
0x1401b094d  nop     dword ptr [rax+rax+00h]
0x1401b0952  xor     edx, edx; Val
0x1401b0954  lea     rcx, Lookaside; void *
0x1401b095b  mov     r8d, 80h; Size
0x1401b0961  call    memset
0x1401b0966  xor     eax, eax
0x1401b0968  lea     rcx, Lookaside; Lookaside
0x1401b096f  mov     [rsp+48h+Depth], ax; Depth
0x1401b0974  mov     r9d, 200h; Flags
0x1401b097a  mov     [rsp+48h+Tag], 77446D56h; Tag
0x1401b0982  xor     r8d, r8d; Free
0x1401b0985  xor     edx, edx; Allocate
0x1401b0987  mov     [rsp+48h+Size], 50h ; 'P'; Size
0x1401b0990  call    cs:__imp_ExInitializeNPagedLookasideList
0x1401b0997  nop     dword ptr [rax+rax+00h]
0x1401b099c  lea     rax, VmsQsMgmtDeferredWorkerThread
0x1401b09a3  mov     qword ptr [rsp+48h+Depth], 0; StartContext
0x1401b09ac  mov     qword ptr [rsp+48h+Tag], rax; StartRoutine
0x1401b09b1  lea     rcx, [rsp+48h+ThreadHandle]; ThreadHandle
0x1401b09b6  xor     r9d, r9d; ProcessHandle
0x1401b09b9  mov     [rsp+48h+Size], 0; ClientId
0x1401b09c2  xor     r8d, r8d; ObjectAttributes
0x1401b09c5  mov     cs:byte_1401FA8B1, 1
0x1401b09cc  mov     edx, 1FFFFFh; DesiredAccess
0x1401b09d1  call    cs:__imp_PsCreateSystemThread
0x1401b09d8  nop     dword ptr [rax+rax+00h]
0x1401b09dd  mov     ebx, eax
0x1401b09df  test    eax, eax
0x1401b09e1  jns     short loc_1401B0A0D
0x1401b09e3  mov     rcx, cs:VmsIfrLog
0x1401b09ea  mov     r9d, 26h ; '&'
0x1401b09f0  mov     [rsp+48h+Tag], eax
0x1401b09f4  mov     dl, 2
0x1401b09f6  lea     rax, WPP_9967daa17f81308e3174d8235558202a_Traceguids
0x1401b09fd  mov     [rsp+48h+Size], rax
0x1401b0a02  lea     r8d, [r9-12h]
0x1401b0a06  call    WPP_RECORDER_SF_d
0x1401b0a0b  jmp     short loc_1401B0A6B
0x1401b0a0d  mov     rcx, [rsp+48h+ThreadHandle]; Handle
0x1401b0a12  lea     rax, [rsp+48h+Object]
0x1401b0a17  mov     qword ptr [rsp+48h+Tag], 0; HandleInformation
0x1401b0a20  xor     r9d, r9d; AccessMode
0x1401b0a23  xor     r8d, r8d; ObjectType
0x1401b0a26  mov     [rsp+48h+Size], rax; Object
0x1401b0a2b  mov     edx, 1FFFFFh; DesiredAccess
0x1401b0a30  mov     [rsp+48h+Object], 0
0x1401b0a39  call    cs:__imp_ObReferenceObjectByHandle
0x1401b0a40  nop     dword ptr [rax+rax+00h]
0x1401b0a45  mov     rax, [rsp+48h+Object]
0x1401b0a4a  mov     rcx, [rsp+48h+ThreadHandle]; Handle
0x1401b0a4f  mov     cs:qword_1401FA020, rax
0x1401b0a56  call    cs:__imp_ZwClose
0x1401b0a5d  nop     dword ptr [rax+rax+00h]
0x1401b0a62  xor     ebx, ebx
0x1401b0a64  mov     cs:byte_1401FA8B0, 1
0x1401b0a6b  mov     eax, ebx
0x1401b0a6d  add     rsp, 40h
0x1401b0a71  pop     rbx
0x1401b0a72  retn
```
