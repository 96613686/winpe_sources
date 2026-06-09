# ChOfferCacheInit

- ea: `0x14002daf4`
- end: `0x14002dbe8`
- name: `ChOfferCacheInit`
- size: `244`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14002a740`

## callees

- `0x140016e7c`
- `0x14002daf4`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x14002dbc1`
- `ntoskrnl!ZwClose` at `0x14002dbc1`
- `ntoskrnl!KeInitializeEvent` at `0x14002db1f`
- `ntoskrnl!KeInitializeEvent` at `0x14002db1f`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14002dba2`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14002dba2`
- `ntoskrnl!PsThreadType` at `0x14002db6b`
- `ntoskrnl!PsCreateSystemThread` at `0x14002db59`
- `ntoskrnl!PsCreateSystemThread` at `0x14002db59`

## pseudocode

```c
__int64 ChOfferCacheInit()
{
  NTSTATUS v0; // ebx
  void *ThreadHandle; // [rsp+50h] [rbp+8h] BYREF
  PVOID Object; // [rsp+58h] [rbp+10h] BYREF

  ThreadHandle = 0;
  ChLocalOfferRemoveThreadTerminate = 0;
  ChLocalOfferRemoveThreadStarted = 0;
  KeInitializeEvent(&ChLocalOfferRemoveThreadWake, SynchronizationEvent, 0);
  v0 = PsCreateSystemThread(&ThreadHandle, 0x1FFFFFu, 0, 0, 0, ChLocalOfferRemoveThreadEntry, 0);
  if ( v0 >= 0 )
  {
    ChLocalOfferRemoveThreadStarted = 1;
    Object = 0;
    v0 = ObReferenceObjectByHandle(ThreadHandle, 0, (POBJECT_TYPE)PsThreadType, 0, &Object, 0);
    ChLocalOfferRemoveThread = Object;
    ZwClose(ThreadHandle);
    if ( v0 >= 0 )
    {
      DvInitializeWorkQueue(&ChLocalOfferRemoveWorkQueue);
      return 0;
    }
  }
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x14002daf4  push    rbx
0x14002daf6  sub     rsp, 40h
0x14002dafa  xor     r8d, r8d; State
0x14002dafd  mov     [rsp+48h+ThreadHandle], 0
0x14002db06  lea     rcx, ChLocalOfferRemoveThreadWake; Event
0x14002db0d  mov     cs:ChLocalOfferRemoveThreadTerminate, 0
0x14002db14  mov     cs:ChLocalOfferRemoveThreadStarted, 0
0x14002db1b  lea     edx, [r8+1]; Type
0x14002db1f  call    cs:__imp_KeInitializeEvent
0x14002db26  nop     dword ptr [rax+rax+00h]
0x14002db2b  lea     rax, ChLocalOfferRemoveThreadEntry
0x14002db32  mov     [rsp+48h+StartContext], 0; StartContext
0x14002db3b  mov     [rsp+48h+StartRoutine], rax; StartRoutine
0x14002db40  lea     rcx, [rsp+48h+ThreadHandle]; ThreadHandle
0x14002db45  xor     r9d, r9d; ProcessHandle
0x14002db48  mov     [rsp+48h+ClientId], 0; ClientId
0x14002db51  xor     r8d, r8d; ObjectAttributes
0x14002db54  mov     edx, 1FFFFFh; DesiredAccess
0x14002db59  call    cs:__imp_PsCreateSystemThread
0x14002db60  nop     dword ptr [rax+rax+00h]
0x14002db65  mov     ebx, eax
0x14002db67  test    eax, eax
0x14002db69  js      short loc_14002DBDF
0x14002db6b  mov     r8, cs:__imp_PsThreadType
0x14002db72  lea     rax, [rsp+48h+Object]
0x14002db77  mov     rcx, [rsp+48h+ThreadHandle]; Handle
0x14002db7c  xor     r9d, r9d; AccessMode
0x14002db7f  mov     [rsp+48h+StartRoutine], 0; HandleInformation
0x14002db88  xor     edx, edx; DesiredAccess
0x14002db8a  mov     cs:ChLocalOfferRemoveThreadStarted, 1
0x14002db91  mov     r8, [r8]; ObjectType
0x14002db94  mov     [rsp+48h+Object], 0
0x14002db9d  mov     [rsp+48h+ClientId], rax; Object
0x14002dba2  call    cs:__imp_ObReferenceObjectByHandle
0x14002dba9  nop     dword ptr [rax+rax+00h]
0x14002dbae  mov     rcx, [rsp+48h+ThreadHandle]; Handle
0x14002dbb3  mov     ebx, eax
0x14002dbb5  mov     rax, [rsp+48h+Object]
0x14002dbba  mov     cs:ChLocalOfferRemoveThread, rax
0x14002dbc1  call    cs:__imp_ZwClose
0x14002dbc8  nop     dword ptr [rax+rax+00h]
0x14002dbcd  test    ebx, ebx
0x14002dbcf  js      short loc_14002DBDF
0x14002dbd1  lea     rcx, ChLocalOfferRemoveWorkQueue
0x14002dbd8  call    DvInitializeWorkQueue
0x14002dbdd  xor     ebx, ebx
0x14002dbdf  mov     eax, ebx
0x14002dbe1  add     rsp, 40h
0x14002dbe5  pop     rbx
0x14002dbe6  retn
```
