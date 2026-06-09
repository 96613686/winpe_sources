# WimpFSFIsBitLockerEnabled

- ea: `0x14002a4d0`
- end: `0x14002a747`
- name: `WimpFSFIsBitLockerEnabled`
- size: `631`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400284d8`

## callees

- `0x1400119c0`
- `0x14002a4d0`

## import_xrefs

- `ntoskrnl!ExQueueWorkItem` at `0x14002a6a6`
- `ntoskrnl!ExQueueWorkItem` at `0x14002a6a6`
- `ntoskrnl!KeWaitForSingleObject` at `0x14002a6c7`
- `ntoskrnl!KeWaitForSingleObject` at `0x14002a6c7`
- `ntoskrnl!swprintf_s` at `0x14002a64b`
- `ntoskrnl!swprintf_s` at `0x14002a64b`
- `ntoskrnl!KeInitializeEvent` at `0x14002a68d`
- `ntoskrnl!KeInitializeEvent` at `0x14002a68d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002a6e8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002a703`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002a6e8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002a703`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002a534`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002a602`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002a534`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002a602`
- `ntoskrnl!ObfDereferenceObject` at `0x14002a718`
- `ntoskrnl!ObfDereferenceObject` at `0x14002a718`
- `FLTMGR!FltDeviceIoControlFile` at `0x14002a57d`
- `FLTMGR!FltDeviceIoControlFile` at `0x14002a57d`
- `FLTMGR!FltOpenVolume` at `0x14002a50c`
- `FLTMGR!FltOpenVolume` at `0x14002a50c`
- `FLTMGR!FltClose` at `0x14002a72d`
- `FLTMGR!FltClose` at `0x14002a72d`

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
0x14002a4d0  push    rbp
0x14002a4d2  push    rbx
0x14002a4d3  push    rsi
0x14002a4d4  push    rdi
0x14002a4d5  push    r14
0x14002a4d7  mov     rbp, rsp
0x14002a4da  sub     rsp, 60h
0x14002a4de  xor     eax, eax
0x14002a4e0  mov     [rbp+arg_0], 0
0x14002a4e7  mov     r14, rdx
0x14002a4ea  mov     [rbp+Event.Header.WaitListHead.Blink], rax
0x14002a4ee  mov     rsi, rcx
0x14002a4f1  mov     [rbp+VolumeFileObject], rax
0x14002a4f5  mov     rcx, [rcx+78h]; Instance
0x14002a4f9  lea     rdx, [rbp+VolumeHandle]; VolumeHandle
0x14002a4fd  xorps   xmm0, xmm0
0x14002a500  mov     [rbp+VolumeHandle], rax
0x14002a504  lea     r8, [rbp+VolumeFileObject]; VolumeFileObject
0x14002a508  movups  xmmword ptr [rbp+Event.Header], xmm0
0x14002a50c  call    cs:__imp_FltOpenVolume
0x14002a513  nop     dword ptr [rax+rax+00h]
0x14002a518  mov     ebx, eax
0x14002a51a  test    eax, eax
0x14002a51c  js      loc_14002A70F
0x14002a522  mov     ebx, 218h
0x14002a527  mov     r8d, 69637077h; Tag
0x14002a52d  mov     edx, ebx; NumberOfBytes
0x14002a52f  mov     ecx, 1; PoolType
0x14002a534  call    cs:__imp_ExAllocatePoolWithTag
0x14002a53b  nop     dword ptr [rax+rax+00h]
0x14002a540  mov     rdi, rax
0x14002a543  test    rax, rax
0x14002a546  jnz     short loc_14002A552
0x14002a548  mov     ebx, 0C0000017h
0x14002a54d  jmp     loc_14002A70F
0x14002a552  mov     rdx, [rbp+VolumeFileObject]; FileObject
0x14002a556  lea     rax, [rbp+arg_0]
0x14002a55a  mov     rcx, [rsi+78h]; Instance
0x14002a55e  xor     r9d, r9d; InputBuffer
0x14002a561  mov     [rsp+60h+LengthReturned], rax; LengthReturned
0x14002a566  mov     r8d, 455610D4h; IoControlCode
0x14002a56c  mov     [rsp+60h+OutputBufferLength], ebx; OutputBufferLength
0x14002a570  mov     [rsp+60h+OutputBuffer], rdi; OutputBuffer
0x14002a575  mov     [rsp+60h+InputBufferLength], 0; InputBufferLength
0x14002a57d  call    cs:__imp_FltDeviceIoControlFile
0x14002a584  nop     dword ptr [rax+rax+00h]
0x14002a589  test    eax, eax
0x14002a58b  jns     short loc_14002A59C
0x14002a58d  xor     ebx, ebx
0x14002a58f  cmp     eax, 0C0000010h
0x14002a594  cmovnz  ebx, eax
0x14002a597  jmp     loc_14002A6FB
0x14002a59c  mov     ecx, 10h
0x14002a5a1  cmp     [rbp+arg_0], ecx
0x14002a5a4  jb      loc_14002A6F6
0x14002a5aa  movzx   eax, word ptr [rdi]
0x14002a5ad  cmp     ax, cx
0x14002a5b0  jb      loc_14002A6F6
0x14002a5b6  cmp     [rdi+2], ax
0x14002a5ba  jbe     loc_14002A6F6
0x14002a5c0  cmp     [rdi+4], ax
0x14002a5c4  jb      loc_14002A6F6
0x14002a5ca  movzx   eax, word ptr [rdi+6]
0x14002a5ce  mov     ecx, 2
0x14002a5d3  cmp     ax, cx
0x14002a5d6  jb      loc_14002A6F6
0x14002a5dc  cmp     [rdi+8], ecx
0x14002a5df  ja      loc_14002A6F6
0x14002a5e5  cmp     dword ptr [rdi+0Ch], 0
0x14002a5e9  jz      loc_14002A6F6
0x14002a5ef  lea     rbx, [rax+28h]
0x14002a5f3  mov     ecx, 200h; PoolType
0x14002a5f8  lea     rdx, [rbx+40h]; NumberOfBytes
0x14002a5fc  mov     r8d, 69637077h; Tag
0x14002a602  call    cs:__imp_ExAllocatePoolWithTag
0x14002a609  nop     dword ptr [rax+rax+00h]
0x14002a60e  mov     rsi, rax
0x14002a611  test    rax, rax
0x14002a614  jnz     short loc_14002A620
0x14002a616  mov     ebx, 0C0000017h
0x14002a61b  jmp     loc_14002A6FB
0x14002a620  xor     edx, edx; Val
0x14002a622  mov     rcx, rsi; void *
0x14002a625  lea     r8d, [rdx+40h]; Size
0x14002a629  call    memset
0x14002a62e  lea     rcx, [rsi+40h]; Dst
0x14002a632  shr     rbx, 1
0x14002a635  mov     [rsi+38h], rcx
0x14002a639  lea     r8, aDeviceBitlocke; "\\Device\\BitLocker\\%s"
0x14002a640  movzx   r9d, word ptr [rdi+4]
0x14002a645  mov     rdx, rbx; SizeInWords
0x14002a648  add     r9, rdi
0x14002a64b  call    cs:__imp_swprintf_s
0x14002a652  nop     dword ptr [rax+rax+00h]
0x14002a657  cmp     eax, 1
0x14002a65a  jge     short loc_14002A663
0x14002a65c  mov     ebx, 0C0000095h
0x14002a661  jmp     short loc_14002A6E0
0x14002a663  add     ax, ax
0x14002a666  lea     rcx, [rbp+Event]; Event
0x14002a66a  mov     [rsi+30h], ax
0x14002a66e  xor     r8d, r8d; State
0x14002a671  mov     [rsi+32h], ax
0x14002a675  xor     edx, edx; Type
0x14002a677  lea     rax, WimpFSFBitLockerCheckWorker
0x14002a67e  mov     [rsi+18h], rsi
0x14002a682  mov     [rsi+10h], rax
0x14002a686  mov     qword ptr [rsi], 0
0x14002a68d  call    cs:__imp_KeInitializeEvent
0x14002a694  nop     dword ptr [rax+rax+00h]
0x14002a699  lea     rax, [rbp+Event]
0x14002a69d  xor     edx, edx; QueueType
0x14002a69f  mov     rcx, rsi; WorkItem
0x14002a6a2  mov     [rsi+20h], rax
0x14002a6a6  call    cs:__imp_ExQueueWorkItem
0x14002a6ad  nop     dword ptr [rax+rax+00h]
0x14002a6b2  xor     r9d, r9d; Alertable
0x14002a6b5  mov     qword ptr [rsp+60h+InputBufferLength], 0; Timeout
0x14002a6be  xor     r8d, r8d; WaitMode
0x14002a6c1  lea     rcx, [rbp+Event]; Object
0x14002a6c5  xor     edx, edx; WaitReason
0x14002a6c7  call    cs:__imp_KeWaitForSingleObject
0x14002a6ce  nop     dword ptr [rax+rax+00h]
0x14002a6d3  mov     ebx, [rsi+28h]
0x14002a6d6  test    ebx, ebx
0x14002a6d8  js      short loc_14002A6E0
0x14002a6da  mov     al, [rsi+2Ch]
0x14002a6dd  mov     [r14], al
0x14002a6e0  mov     edx, 69637077h; Tag
0x14002a6e5  mov     rcx, rsi; P
0x14002a6e8  call    cs:__imp_ExFreePoolWithTag
0x14002a6ef  nop     dword ptr [rax+rax+00h]
0x14002a6f4  jmp     short loc_14002A6FB
0x14002a6f6  mov     ebx, 0C000000Dh
0x14002a6fb  mov     edx, 69637077h; Tag
0x14002a700  mov     rcx, rdi; P
0x14002a703  call    cs:__imp_ExFreePoolWithTag
0x14002a70a  nop     dword ptr [rax+rax+00h]
0x14002a70f  mov     rcx, [rbp+VolumeFileObject]; Object
0x14002a713  test    rcx, rcx
0x14002a716  jz      short loc_14002A724
0x14002a718  call    cs:__imp_ObfDereferenceObject
0x14002a71f  nop     dword ptr [rax+rax+00h]
0x14002a724  mov     rcx, [rbp+VolumeHandle]; FileHandle
0x14002a728  test    rcx, rcx
0x14002a72b  jz      short loc_14002A739
0x14002a72d  call    cs:__imp_FltClose
0x14002a734  nop     dword ptr [rax+rax+00h]
0x14002a739  mov     eax, ebx
0x14002a73b  add     rsp, 60h
0x14002a73f  pop     r14
0x14002a741  pop     rdi
0x14002a742  pop     rsi
0x14002a743  pop     rbx
0x14002a744  pop     rbp
0x14002a745  retn
```
