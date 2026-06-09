# ChOfferCacheInit

- ea: `0x14002db44`
- end: `0x14002dc38`
- name: `ChOfferCacheInit`
- size: `244`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14002a790`

## callees

- `0x140016e7c`
- `0x14002db44`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x14002dc11`
- `ntoskrnl!ZwClose` at `0x14002dc11`
- `ntoskrnl!KeInitializeEvent` at `0x14002db6f`
- `ntoskrnl!KeInitializeEvent` at `0x14002db6f`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14002dbf2`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14002dbf2`
- `ntoskrnl!PsThreadType` at `0x14002dbbb`
- `ntoskrnl!PsCreateSystemThread` at `0x14002dba9`
- `ntoskrnl!PsCreateSystemThread` at `0x14002dba9`

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
0x14002db44  push    rbx
0x14002db46  sub     rsp, 40h
0x14002db4a  xor     r8d, r8d; State
0x14002db4d  mov     [rsp+48h+ThreadHandle], 0
0x14002db56  lea     rcx, ChLocalOfferRemoveThreadWake; Event
0x14002db5d  mov     cs:ChLocalOfferRemoveThreadTerminate, 0
0x14002db64  mov     cs:ChLocalOfferRemoveThreadStarted, 0
0x14002db6b  lea     edx, [r8+1]; Type
0x14002db6f  call    cs:__imp_KeInitializeEvent
0x14002db76  nop     dword ptr [rax+rax+00h]
0x14002db7b  lea     rax, ChLocalOfferRemoveThreadEntry
0x14002db82  mov     [rsp+48h+StartContext], 0; StartContext
0x14002db8b  mov     [rsp+48h+StartRoutine], rax; StartRoutine
0x14002db90  lea     rcx, [rsp+48h+ThreadHandle]; ThreadHandle
0x14002db95  xor     r9d, r9d; ProcessHandle
0x14002db98  mov     [rsp+48h+ClientId], 0; ClientId
0x14002dba1  xor     r8d, r8d; ObjectAttributes
0x14002dba4  mov     edx, 1FFFFFh; DesiredAccess
0x14002dba9  call    cs:__imp_PsCreateSystemThread
0x14002dbb0  nop     dword ptr [rax+rax+00h]
0x14002dbb5  mov     ebx, eax
0x14002dbb7  test    eax, eax
0x14002dbb9  js      short loc_14002DC2F
0x14002dbbb  mov     r8, cs:__imp_PsThreadType
0x14002dbc2  lea     rax, [rsp+48h+Object]
0x14002dbc7  mov     rcx, [rsp+48h+ThreadHandle]; Handle
0x14002dbcc  xor     r9d, r9d; AccessMode
0x14002dbcf  mov     [rsp+48h+StartRoutine], 0; HandleInformation
0x14002dbd8  xor     edx, edx; DesiredAccess
0x14002dbda  mov     cs:ChLocalOfferRemoveThreadStarted, 1
0x14002dbe1  mov     r8, [r8]; ObjectType
0x14002dbe4  mov     [rsp+48h+Object], 0
0x14002dbed  mov     [rsp+48h+ClientId], rax; Object
0x14002dbf2  call    cs:__imp_ObReferenceObjectByHandle
0x14002dbf9  nop     dword ptr [rax+rax+00h]
0x14002dbfe  mov     rcx, [rsp+48h+ThreadHandle]; Handle
0x14002dc03  mov     ebx, eax
0x14002dc05  mov     rax, [rsp+48h+Object]
0x14002dc0a  mov     cs:ChLocalOfferRemoveThread, rax
0x14002dc11  call    cs:__imp_ZwClose
0x14002dc18  nop     dword ptr [rax+rax+00h]
0x14002dc1d  test    ebx, ebx
0x14002dc1f  js      short loc_14002DC2F
0x14002dc21  lea     rcx, ChLocalOfferRemoveWorkQueue
0x14002dc28  call    DvInitializeWorkQueue
0x14002dc2d  xor     ebx, ebx
0x14002dc2f  mov     eax, ebx
0x14002dc31  add     rsp, 40h
0x14002dc35  pop     rbx
0x14002dc36  retn
```
