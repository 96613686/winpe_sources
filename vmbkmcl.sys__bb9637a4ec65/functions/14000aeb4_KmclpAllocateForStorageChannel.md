# KmclpAllocateForStorageChannel

- ea: `0x14000aeb4`
- end: `0x14000af7d`
- name: `KmclpAllocateForStorageChannel`
- size: `201`
- prototype: `__int64 __fastcall(PVOID StartContext)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14000fad0`

## callees

- `0x14000aeb4`

## import_xrefs

- `ntoskrnl!IoFreeWorkItem` at `0x14000af5d`
- `ntoskrnl!IoFreeWorkItem` at `0x14000af5d`
- `ntoskrnl!KeInitializeEvent` at `0x14000aedb`
- `ntoskrnl!KeInitializeEvent` at `0x14000aef3`
- `ntoskrnl!KeInitializeEvent` at `0x14000aedb`
- `ntoskrnl!KeInitializeEvent` at `0x14000aef3`
- `ntoskrnl!PsCreateSystemThread` at `0x14000af29`
- `ntoskrnl!PsCreateSystemThread` at `0x14000af29`
- `ntoskrnl!ZwClose` at `0x14000af45`
- `ntoskrnl!ZwClose` at `0x14000af45`

## pseudocode

```c
NTSTATUS __fastcall KmclpAllocateForStorageChannel(struct _KEVENT *StartContext)
{
  NTSTATUS result; // eax
  void *v3; // rcx
  struct _IO_WORKITEM *Blink; // rcx
  void *ThreadHandle; // [rsp+50h] [rbp+8h] BYREF

  StartContext[95].Header.Signalling = 0;
  ThreadHandle = 0;
  KeInitializeEvent(StartContext + 93, SynchronizationEvent, 0);
  KeInitializeEvent(StartContext + 94, NotificationEvent, 0);
  result = PsCreateSystemThread(&ThreadHandle, 0x1FFFFFu, 0, 0, 0, KmclpRundownCountZeroThread, StartContext);
  if ( result >= 0 )
  {
    v3 = ThreadHandle;
    StartContext[95].Header.Type = 1;
    ZwClose(v3);
    Blink = (struct _IO_WORKITEM *)StartContext[92].Header.WaitListHead.Blink;
    if ( Blink )
    {
      IoFreeWorkItem(Blink);
      StartContext[92].Header.WaitListHead.Blink = 0;
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x14000aeb4  push    rbx
0x14000aeb6  sub     rsp, 40h
0x14000aeba  xor     r8d, r8d; State
0x14000aebd  mov     byte ptr [rcx+8E9h], 0
0x14000aec4  mov     rbx, rcx
0x14000aec7  mov     [rsp+48h+ThreadHandle], 0
0x14000aed0  add     rcx, 8B8h; Event
0x14000aed7  lea     edx, [r8+1]; Type
0x14000aedb  call    cs:__imp_KeInitializeEvent
0x14000aee2  nop     dword ptr [rax+rax+00h]
0x14000aee7  lea     rcx, [rbx+8D0h]; Event
0x14000aeee  xor     r8d, r8d; State
0x14000aef1  xor     edx, edx; Type
0x14000aef3  call    cs:__imp_KeInitializeEvent
0x14000aefa  nop     dword ptr [rax+rax+00h]
0x14000aeff  lea     rax, KmclpRundownCountZeroThread
0x14000af06  mov     [rsp+48h+StartContext], rbx; StartContext
0x14000af0b  mov     [rsp+48h+StartRoutine], rax; StartRoutine
0x14000af10  lea     rcx, [rsp+48h+ThreadHandle]; ThreadHandle
0x14000af15  xor     r9d, r9d; ProcessHandle
0x14000af18  mov     [rsp+48h+ClientId], 0; ClientId
0x14000af21  xor     r8d, r8d; ObjectAttributes
0x14000af24  mov     edx, 1FFFFFh; DesiredAccess
0x14000af29  call    cs:__imp_PsCreateSystemThread
0x14000af30  nop     dword ptr [rax+rax+00h]
0x14000af35  test    eax, eax
0x14000af37  js      short loc_14000AF76
0x14000af39  mov     rcx, [rsp+48h+ThreadHandle]; Handle
0x14000af3e  mov     byte ptr [rbx+8E8h], 1
0x14000af45  call    cs:__imp_ZwClose
0x14000af4c  nop     dword ptr [rax+rax+00h]
0x14000af51  mov     rcx, [rbx+8B0h]; IoWorkItem
0x14000af58  test    rcx, rcx
0x14000af5b  jz      short loc_14000AF74
0x14000af5d  call    cs:__imp_IoFreeWorkItem
0x14000af64  nop     dword ptr [rax+rax+00h]
0x14000af69  mov     qword ptr [rbx+8B0h], 0
0x14000af74  xor     eax, eax
0x14000af76  add     rsp, 40h
0x14000af7a  pop     rbx
0x14000af7b  retn
```
