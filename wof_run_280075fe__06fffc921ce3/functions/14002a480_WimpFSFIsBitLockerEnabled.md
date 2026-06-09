# WimpFSFIsBitLockerEnabled

- ea: `0x14002a480`
- end: `0x14002a6f7`
- name: `WimpFSFIsBitLockerEnabled`
- size: `631`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140028488`

## callees

- `0x1400119c0`
- `0x14002a480`

## import_xrefs

- `ntoskrnl!ExQueueWorkItem` at `0x14002a656`
- `ntoskrnl!ExQueueWorkItem` at `0x14002a656`
- `ntoskrnl!KeWaitForSingleObject` at `0x14002a677`
- `ntoskrnl!KeWaitForSingleObject` at `0x14002a677`
- `ntoskrnl!swprintf_s` at `0x14002a5fb`
- `ntoskrnl!swprintf_s` at `0x14002a5fb`
- `ntoskrnl!KeInitializeEvent` at `0x14002a63d`
- `ntoskrnl!KeInitializeEvent` at `0x14002a63d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002a698`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002a6b3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002a698`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002a6b3`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002a4e4`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002a5b2`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002a4e4`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002a5b2`
- `ntoskrnl!ObfDereferenceObject` at `0x14002a6c8`
- `ntoskrnl!ObfDereferenceObject` at `0x14002a6c8`
- `FLTMGR!FltDeviceIoControlFile` at `0x14002a52d`
- `FLTMGR!FltDeviceIoControlFile` at `0x14002a52d`
- `FLTMGR!FltOpenVolume` at `0x14002a4bc`
- `FLTMGR!FltOpenVolume` at `0x14002a4bc`
- `FLTMGR!FltClose` at `0x14002a6dd`
- `FLTMGR!FltClose` at `0x14002a6dd`

## pseudocode

```c
__int64 __fastcall WimpFSFIsBitLockerEnabled(__int64 a1, _BYTE *a2)
{
  struct _FLT_INSTANCE *v4; // rcx
  NTSTATUS v5; // ebx
  _WORD *OutputBuffer; // rdi
  NTSTATUS v7; // eax
  unsigned __int16 v8; // ax
  __int64 v9; // rax
  unsigned __int64 v10; // rbx
  char *PoolWithTag; // rax
  char *v12; // rsi
  int v13; // eax
  __int16 v14; // ax
  struct _KEVENT Event; // [rsp+40h] [rbp-20h] BYREF
  ULONG LengthReturned; // [rsp+90h] [rbp+30h] BYREF
  PFILE_OBJECT VolumeFileObject; // [rsp+A0h] [rbp+40h] BYREF
  void *VolumeHandle; // [rsp+A8h] [rbp+48h] BYREF

  LengthReturned = 0;
  VolumeFileObject = 0;
  v4 = *(struct _FLT_INSTANCE **)(a1 + 120);
  VolumeHandle = 0;
  memset(&Event, 0, sizeof(Event));
  v5 = FltOpenVolume(v4, &VolumeHandle, &VolumeFileObject);
  if ( v5 >= 0 )
  {
    OutputBuffer = ExAllocatePoolWithTag(PagedPool, 0x218u, 0x69637077u);
    if ( OutputBuffer )
    {
      v7 = FltDeviceIoControlFile(
             *(PFLT_INSTANCE *)(a1 + 120),
             VolumeFileObject,
             0x455610D4u,
             0,
             0,
             OutputBuffer,
             0x218u,
             &LengthReturned);
      if ( v7 >= 0 )
      {
        if ( LengthReturned >= 0x10
          && (v8 = *OutputBuffer, *OutputBuffer >= 0x10u)
          && OutputBuffer[1] > v8
          && OutputBuffer[2] >= v8
          && (v9 = (unsigned __int16)OutputBuffer[3], (unsigned __int16)v9 >= 2u)
          && *((_DWORD *)OutputBuffer + 2) <= 2u
          && *((_DWORD *)OutputBuffer + 3) )
        {
          v10 = v9 + 40;
          PoolWithTag = (char *)ExAllocatePoolWithTag((POOL_TYPE)512, v9 + 104, 0x69637077u);
          v12 = PoolWithTag;
          if ( PoolWithTag )
          {
            memset(PoolWithTag, 0, 0x40u);
            *((_QWORD *)v12 + 7) = v12 + 64;
            v13 = swprintf_s(
                    (wchar_t *)v12 + 32,
                    v10 >> 1,
                    L"\\Device\\BitLocker\\%s",
                    (char *)OutputBuffer + (unsigned __int16)OutputBuffer[2]);
            if ( v13 >= 1 )
            {
              v14 = 2 * v13;
              *((_WORD *)v12 + 24) = v14;
              *((_WORD *)v12 + 25) = v14;
              *((_QWORD *)v12 + 3) = v12;
              *((_QWORD *)v12 + 2) = WimpFSFBitLockerCheckWorker;
              *(_QWORD *)v12 = 0;
              KeInitializeEvent(&Event, NotificationEvent, 0);
              *((_QWORD *)v12 + 4) = &Event;
              ExQueueWorkItem((PWORK_QUEUE_ITEM)v12, CriticalWorkQueue);
              KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
              v5 = *((_DWORD *)v12 + 10);
              if ( v5 >= 0 )
                *a2 = v12[44];
            }
            else
            {
              v5 = -1073741675;
            }
            ExFreePoolWithTag(v12, 0x69637077u);
          }
          else
          {
            v5 = -1073741801;
          }
        }
        else
        {
          v5 = -1073741811;
        }
      }
      else
      {
        v5 = 0;
        if ( v7 != -1073741808 )
          v5 = v7;
      }
      ExFreePoolWithTag(OutputBuffer, 0x69637077u);
    }
    else
    {
      v5 = -1073741801;
    }
  }
  if ( VolumeFileObject )
    ObfDereferenceObject(VolumeFileObject);
  if ( VolumeHandle )
    FltClose(VolumeHandle);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x14002a480  push    rbp
0x14002a482  push    rbx
0x14002a483  push    rsi
0x14002a484  push    rdi
0x14002a485  push    r14
0x14002a487  mov     rbp, rsp
0x14002a48a  sub     rsp, 60h
0x14002a48e  xor     eax, eax
0x14002a490  mov     [rbp+arg_0], 0
0x14002a497  mov     r14, rdx
0x14002a49a  mov     [rbp+Event.Header.WaitListHead.Blink], rax
0x14002a49e  mov     rsi, rcx
0x14002a4a1  mov     [rbp+VolumeFileObject], rax
0x14002a4a5  mov     rcx, [rcx+78h]; Instance
0x14002a4a9  lea     rdx, [rbp+VolumeHandle]; VolumeHandle
0x14002a4ad  xorps   xmm0, xmm0
0x14002a4b0  mov     [rbp+VolumeHandle], rax
0x14002a4b4  lea     r8, [rbp+VolumeFileObject]; VolumeFileObject
0x14002a4b8  movups  xmmword ptr [rbp+Event.Header], xmm0
0x14002a4bc  call    cs:__imp_FltOpenVolume
0x14002a4c3  nop     dword ptr [rax+rax+00h]
0x14002a4c8  mov     ebx, eax
0x14002a4ca  test    eax, eax
0x14002a4cc  js      loc_14002A6BF
0x14002a4d2  mov     ebx, 218h
0x14002a4d7  mov     r8d, 69637077h; Tag
0x14002a4dd  mov     edx, ebx; NumberOfBytes
0x14002a4df  mov     ecx, 1; PoolType
0x14002a4e4  call    cs:__imp_ExAllocatePoolWithTag
0x14002a4eb  nop     dword ptr [rax+rax+00h]
0x14002a4f0  mov     rdi, rax
0x14002a4f3  test    rax, rax
0x14002a4f6  jnz     short loc_14002A502
0x14002a4f8  mov     ebx, 0C0000017h
0x14002a4fd  jmp     loc_14002A6BF
0x14002a502  mov     rdx, [rbp+VolumeFileObject]; FileObject
0x14002a506  lea     rax, [rbp+arg_0]
0x14002a50a  mov     rcx, [rsi+78h]; Instance
0x14002a50e  xor     r9d, r9d; InputBuffer
0x14002a511  mov     [rsp+60h+LengthReturned], rax; LengthReturned
0x14002a516  mov     r8d, 455610D4h; IoControlCode
0x14002a51c  mov     [rsp+60h+OutputBufferLength], ebx; OutputBufferLength
0x14002a520  mov     [rsp+60h+OutputBuffer], rdi; OutputBuffer
0x14002a525  mov     [rsp+60h+InputBufferLength], 0; InputBufferLength
0x14002a52d  call    cs:__imp_FltDeviceIoControlFile
0x14002a534  nop     dword ptr [rax+rax+00h]
0x14002a539  test    eax, eax
0x14002a53b  jns     short loc_14002A54C
0x14002a53d  xor     ebx, ebx
0x14002a53f  cmp     eax, 0C0000010h
0x14002a544  cmovnz  ebx, eax
0x14002a547  jmp     loc_14002A6AB
0x14002a54c  mov     ecx, 10h
0x14002a551  cmp     [rbp+arg_0], ecx
0x14002a554  jb      loc_14002A6A6
0x14002a55a  movzx   eax, word ptr [rdi]
0x14002a55d  cmp     ax, cx
0x14002a560  jb      loc_14002A6A6
0x14002a566  cmp     [rdi+2], ax
0x14002a56a  jbe     loc_14002A6A6
0x14002a570  cmp     [rdi+4], ax
0x14002a574  jb      loc_14002A6A6
0x14002a57a  movzx   eax, word ptr [rdi+6]
0x14002a57e  mov     ecx, 2
0x14002a583  cmp     ax, cx
0x14002a586  jb      loc_14002A6A6
0x14002a58c  cmp     [rdi+8], ecx
0x14002a58f  ja      loc_14002A6A6
0x14002a595  cmp     dword ptr [rdi+0Ch], 0
0x14002a599  jz      loc_14002A6A6
0x14002a59f  lea     rbx, [rax+28h]
0x14002a5a3  mov     ecx, 200h; PoolType
0x14002a5a8  lea     rdx, [rbx+40h]; NumberOfBytes
0x14002a5ac  mov     r8d, 69637077h; Tag
0x14002a5b2  call    cs:__imp_ExAllocatePoolWithTag
0x14002a5b9  nop     dword ptr [rax+rax+00h]
0x14002a5be  mov     rsi, rax
0x14002a5c1  test    rax, rax
0x14002a5c4  jnz     short loc_14002A5D0
0x14002a5c6  mov     ebx, 0C0000017h
0x14002a5cb  jmp     loc_14002A6AB
0x14002a5d0  xor     edx, edx; Val
0x14002a5d2  mov     rcx, rsi; void *
0x14002a5d5  lea     r8d, [rdx+40h]; Size
0x14002a5d9  call    memset
0x14002a5de  lea     rcx, [rsi+40h]; Dst
0x14002a5e2  shr     rbx, 1
0x14002a5e5  mov     [rsi+38h], rcx
0x14002a5e9  lea     r8, aDeviceBitlocke; "\\Device\\BitLocker\\%s"
0x14002a5f0  movzx   r9d, word ptr [rdi+4]
0x14002a5f5  mov     rdx, rbx; SizeInWords
0x14002a5f8  add     r9, rdi
0x14002a5fb  call    cs:__imp_swprintf_s
0x14002a602  nop     dword ptr [rax+rax+00h]
0x14002a607  cmp     eax, 1
0x14002a60a  jge     short loc_14002A613
0x14002a60c  mov     ebx, 0C0000095h
0x14002a611  jmp     short loc_14002A690
0x14002a613  add     ax, ax
0x14002a616  lea     rcx, [rbp+Event]; Event
0x14002a61a  mov     [rsi+30h], ax
0x14002a61e  xor     r8d, r8d; State
0x14002a621  mov     [rsi+32h], ax
0x14002a625  xor     edx, edx; Type
0x14002a627  lea     rax, WimpFSFBitLockerCheckWorker
0x14002a62e  mov     [rsi+18h], rsi
0x14002a632  mov     [rsi+10h], rax
0x14002a636  mov     qword ptr [rsi], 0
0x14002a63d  call    cs:__imp_KeInitializeEvent
0x14002a644  nop     dword ptr [rax+rax+00h]
0x14002a649  lea     rax, [rbp+Event]
0x14002a64d  xor     edx, edx; QueueType
0x14002a64f  mov     rcx, rsi; WorkItem
0x14002a652  mov     [rsi+20h], rax
0x14002a656  call    cs:__imp_ExQueueWorkItem
0x14002a65d  nop     dword ptr [rax+rax+00h]
0x14002a662  xor     r9d, r9d; Alertable
0x14002a665  mov     qword ptr [rsp+60h+InputBufferLength], 0; Timeout
0x14002a66e  xor     r8d, r8d; WaitMode
0x14002a671  lea     rcx, [rbp+Event]; Object
0x14002a675  xor     edx, edx; WaitReason
0x14002a677  call    cs:__imp_KeWaitForSingleObject
0x14002a67e  nop     dword ptr [rax+rax+00h]
0x14002a683  mov     ebx, [rsi+28h]
0x14002a686  test    ebx, ebx
0x14002a688  js      short loc_14002A690
0x14002a68a  mov     al, [rsi+2Ch]
0x14002a68d  mov     [r14], al
0x14002a690  mov     edx, 69637077h; Tag
0x14002a695  mov     rcx, rsi; P
0x14002a698  call    cs:__imp_ExFreePoolWithTag
0x14002a69f  nop     dword ptr [rax+rax+00h]
0x14002a6a4  jmp     short loc_14002A6AB
0x14002a6a6  mov     ebx, 0C000000Dh
0x14002a6ab  mov     edx, 69637077h; Tag
0x14002a6b0  mov     rcx, rdi; P
0x14002a6b3  call    cs:__imp_ExFreePoolWithTag
0x14002a6ba  nop     dword ptr [rax+rax+00h]
0x14002a6bf  mov     rcx, [rbp+VolumeFileObject]; Object
0x14002a6c3  test    rcx, rcx
0x14002a6c6  jz      short loc_14002A6D4
0x14002a6c8  call    cs:__imp_ObfDereferenceObject
0x14002a6cf  nop     dword ptr [rax+rax+00h]
0x14002a6d4  mov     rcx, [rbp+VolumeHandle]; FileHandle
0x14002a6d8  test    rcx, rcx
0x14002a6db  jz      short loc_14002A6E9
0x14002a6dd  call    cs:__imp_FltClose
0x14002a6e4  nop     dword ptr [rax+rax+00h]
0x14002a6e9  mov     eax, ebx
0x14002a6eb  add     rsp, 60h
0x14002a6ef  pop     r14
0x14002a6f1  pop     rdi
0x14002a6f2  pop     rsi
0x14002a6f3  pop     rbx
0x14002a6f4  pop     rbp
0x14002a6f5  retn
```
