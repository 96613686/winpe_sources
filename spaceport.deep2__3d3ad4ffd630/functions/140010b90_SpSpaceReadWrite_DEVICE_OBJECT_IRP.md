# SpSpaceReadWrite(_DEVICE_OBJECT *,_IRP *)

- ea: `0x140010b90`
- end: `0x140010dfd`
- name: `?SpSpaceReadWrite@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `621`
- prototype: `int(struct _DEVICE_OBJECT *, struct _IRP *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140010a80`

## callees

- `0x140010b90`
- `0x140010e10`
- `0x140010ed0`
- `0x140031c40`

## import_xrefs

- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140010ca3`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140010de7`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140010ca3`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140010de7`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140010da3`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140010da3`
- `ntoskrnl!IofCompleteRequest` at `0x140010cdb`
- `ntoskrnl!IofCompleteRequest` at `0x140010cdb`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x140010c2d`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x140010db6`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x140010c2d`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x140010db6`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140010d7a`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140010dcf`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140010d7a`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140010dcf`

## pseudocode

```c
NTSTATUS __fastcall SpSpaceReadWrite(struct _DEVICE_OBJECT *a1, struct _IRP *a2)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  char *DeviceExtension; // rsi
  __int64 Length; // r9
  LARGE_INTEGER ByteOffset; // r10
  PMDL MdlAddress; // rax
  struct _EX_RUNDOWN_REF_CACHE_AWARE *v9; // rcx
  SP_QOS_CONTEXT *v10; // rcx
  NTSTATUS v12; // eax
  NTSTATUS v13; // ebx
  struct _LIST_ENTRY *v14; // rsi
  struct _IO_STACK_LOCATION *v15; // rax
  struct _IO_STACK_LOCATION *v16; // rax
  struct _LIST_ENTRY *Blink; // rcx
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+20h] [rbp-48h] BYREF

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  DeviceExtension = (char *)a1->DeviceExtension;
  Length = CurrentStackLocation->Parameters.Read.Length;
  ByteOffset = CurrentStackLocation->Parameters.Read.ByteOffset;
  a2->IoStatus.Information = 0;
  if ( ((a1->SectorSize - 1LL) & ByteOffset.QuadPart) != 0
    || ((a1->SectorSize - 1) & (unsigned int)Length) != 0
    || (MdlAddress = a2->MdlAddress) == 0
    || (unsigned int)Length > MdlAddress->ByteCount
    || (unsigned __int64)(ByteOffset.QuadPart + Length) < ByteOffset.QuadPart
    || (unsigned __int64)(ByteOffset.QuadPart + Length) > *((_QWORD *)DeviceExtension + 396) )
  {
    v13 = -1073741811;
    goto LABEL_18;
  }
  SpIoCountersInitialize(a2);
  v9 = (struct _EX_RUNDOWN_REF_CACHE_AWARE *)*((_QWORD *)DeviceExtension + 31);
  memset(&LockHandle, 0, sizeof(LockHandle));
  if ( ExAcquireRundownProtectionCacheAware(v9) )
  {
LABEL_7:
    if ( *((_QWORD *)DeviceExtension + 404) )
    {
      v10 = (SP_QOS_CONTEXT *)*((_QWORD *)DeviceExtension + 412);
      if ( !v10 || !*((_QWORD *)v10 + 54) && !*((_QWORD *)v10 + 55) )
        return SpSpaceReadWriteCallback(a1, a2);
      v12 = SpLimiterProcessIrp(v10, a2);
      v13 = v12;
      if ( !v12 )
        return SpSpaceReadWriteCallback(a1, a2);
      if ( v12 != 259 )
        ExReleaseRundownProtectionCacheAware(*((PEX_RUNDOWN_REF_CACHE_AWARE *)DeviceExtension + 31));
      if ( v13 == 259 )
        return v13;
    }
    else
    {
      ExReleaseRundownProtectionCacheAware(*((PEX_RUNDOWN_REF_CACHE_AWARE *)DeviceExtension + 31));
      v13 = -1073741810;
    }
LABEL_18:
    a2->IoStatus.Status = v13;
    IofCompleteRequest(a2, 0);
    return v13;
  }
  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)DeviceExtension + 38, &LockHandle);
  if ( ExAcquireRundownProtectionCacheAware(*((PEX_RUNDOWN_REF_CACHE_AWARE *)DeviceExtension + 31)) )
  {
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    goto LABEL_7;
  }
  v14 = (struct _LIST_ENTRY *)(DeviceExtension + 288);
  a2->Tail.Overlay.CurrentStackLocation->Control |= 1u;
  v15 = a2->Tail.Overlay.CurrentStackLocation;
  *(_OWORD *)&v15[-1].MajorFunction = *(_OWORD *)&v15->MajorFunction;
  *(_OWORD *)&v15[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&v15->Parameters.NotifyDirectoryEx.CompletionFilter;
  *(_OWORD *)(&v15[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&v15->Parameters.SetQuota + 6);
  v15[-1].FileObject = v15->FileObject;
  v15[-1].Control = 0;
  v16 = a2->Tail.Overlay.CurrentStackLocation;
  v16[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)SpIoCompletionRoutine;
  v16[-1].Context = (PVOID)1;
  v16[-1].Control = -32;
  --a2->CurrentLocation;
  --a2->Tail.Overlay.CurrentStackLocation;
  Blink = v14->Blink;
  if ( Blink->Flink != v14 )
    __fastfail(3u);
  a2->Tail.Overlay.ListEntry.Blink = Blink;
  a2->Tail.Overlay.ListEntry.Flink = v14;
  Blink->Flink = &a2->Tail.Overlay.ListEntry;
  v14->Blink = &a2->Tail.Overlay.ListEntry;
  KeReleaseInStackQueuedSpinLock(&LockHandle);
  return 259;
}

```

## disassembly

```asm
0x140010b90  push    rbx
0x140010b92  push    rbp
0x140010b93  push    rsi
0x140010b94  push    rdi
0x140010b95  sub     rsp, 48h
0x140010b99  mov     rax, [rdx+0B8h]
0x140010ba0  mov     rdi, rdx
0x140010ba3  mov     rsi, [rcx+40h]
0x140010ba7  mov     rbp, rcx
0x140010baa  mov     r9d, [rax+8]
0x140010bae  mov     r10, [rax+18h]
0x140010bb2  mov     qword ptr [rdx+38h], 0
0x140010bba  movzx   r8d, word ptr [rcx+130h]
0x140010bc2  lea     rax, [r8-1]
0x140010bc6  test    r10, rax
0x140010bc9  lea     eax, [r8-1]
0x140010bcd  setz    dl
0x140010bd0  test    r9d, eax
0x140010bd3  setz    al
0x140010bd6  test    al, dl
0x140010bd8  jz      loc_140010CCE
0x140010bde  mov     rax, [rdi+8]
0x140010be2  test    rax, rax
0x140010be5  jz      loc_140010CCE
0x140010beb  cmp     r9d, [rax+28h]
0x140010bef  ja      loc_140010CCE
0x140010bf5  lea     rcx, [r10+r9]
0x140010bf9  cmp     rcx, r10
0x140010bfc  jb      loc_140010CCE
0x140010c02  cmp     rcx, [rsi+0C60h]
0x140010c09  ja      loc_140010CCE
0x140010c0f  mov     rcx, rdi; struct _IRP *
0x140010c12  call    ?SpIoCountersInitialize@@YAXPEAU_IRP@@@Z; SpIoCountersInitialize(_IRP *)
0x140010c17  mov     rcx, [rsi+0F8h]; RunRefCacheAware
0x140010c1e  xorps   xmm0, xmm0
0x140010c21  xor     eax, eax
0x140010c23  movups  xmmword ptr [rsp+68h+LockHandle.LockQueue.Next], xmm0
0x140010c28  mov     qword ptr [rsp+68h+LockHandle.OldIrql], rax
0x140010c2d  call    cs:__imp_ExAcquireRundownProtectionCacheAware
0x140010c34  nop     dword ptr [rax+rax+00h]
0x140010c39  test    al, al
0x140010c3b  jz      loc_140010D97
0x140010c41  cmp     qword ptr [rsi+0CA0h], 0
0x140010c49  jz      loc_140010DE0
0x140010c4f  mov     rcx, [rsi+0CE0h]; this
0x140010c56  test    rcx, rcx
0x140010c59  jz      short loc_140010C6F
0x140010c5b  cmp     qword ptr [rcx+1B0h], 0
0x140010c63  jnz     short loc_140010C84
0x140010c65  cmp     qword ptr [rcx+1B8h], 0
0x140010c6d  jnz     short loc_140010C84
0x140010c6f  mov     rdx, rdi; struct _IRP *
0x140010c72  mov     rcx, rbp; struct _DEVICE_OBJECT *
0x140010c75  call    ?SpSpaceReadWriteCallback@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; SpSpaceReadWriteCallback(_DEVICE_OBJECT *,_IRP *)
0x140010c7a  add     rsp, 48h
0x140010c7e  pop     rdi
0x140010c7f  pop     rsi
0x140010c80  pop     rbp
0x140010c81  pop     rbx
0x140010c82  retn
0x140010c84  mov     rdx, rdi; struct _IRP *
0x140010c87  call    ?SpLimiterProcessIrp@@YAJPEAXPEAU_IRP@@@Z; SpLimiterProcessIrp(void *,_IRP *)
0x140010c8c  mov     ebx, eax
0x140010c8e  test    eax, eax
0x140010c90  jz      short loc_140010C6F
0x140010c92  mov     bpl, 1
0x140010c95  cmp     eax, 103h
0x140010c9a  jz      short loc_140010CAF
0x140010c9c  mov     rcx, [rsi+0F8h]; RunRefCacheAware
0x140010ca3  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x140010caa  nop     dword ptr [rax+rax+00h]
0x140010caf  xor     ecx, ecx
0x140010cb1  movzx   eax, bpl
0x140010cb5  cmp     ebx, 103h
0x140010cbb  cmovnz  ecx, eax
0x140010cbe  test    cl, cl
0x140010cc0  jnz     short loc_140010CD3
0x140010cc2  mov     eax, ebx
0x140010cc4  add     rsp, 48h
0x140010cc8  pop     rdi
0x140010cc9  pop     rsi
0x140010cca  pop     rbp
0x140010ccb  pop     rbx
0x140010ccc  retn
0x140010cce  mov     ebx, 0C000000Dh
0x140010cd3  xor     edx, edx; PriorityBoost
0x140010cd5  mov     [rdi+30h], ebx
0x140010cd8  mov     rcx, rdi; Irp
0x140010cdb  call    cs:__imp_IofCompleteRequest
0x140010ce2  nop     dword ptr [rax+rax+00h]
0x140010ce7  jmp     short loc_140010CC2
0x140010ce9  mov     rax, [rdi+0B8h]
0x140010cf0  lea     rcx, ?SpIoCompletionRoutine@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z; SpIoCompletionRoutine(_DEVICE_OBJECT *,_IRP *,void *)
0x140010cf7  add     rsi, 120h
0x140010cfe  or      byte ptr [rax+3], 1
0x140010d02  mov     rax, [rdi+0B8h]
0x140010d09  movups  xmm0, xmmword ptr [rax]
0x140010d0c  movups  xmmword ptr [rax-48h], xmm0
0x140010d10  movups  xmm1, xmmword ptr [rax+10h]
0x140010d14  movups  xmmword ptr [rax-38h], xmm1
0x140010d18  movups  xmm0, xmmword ptr [rax+20h]
0x140010d1c  movups  xmmword ptr [rax-28h], xmm0
0x140010d20  movsd   xmm1, qword ptr [rax+30h]
0x140010d25  movsd   qword ptr [rax-18h], xmm1
0x140010d2a  mov     byte ptr [rax-45h], 0
0x140010d2e  mov     rax, [rdi+0B8h]
0x140010d35  mov     [rax-10h], rcx
0x140010d39  mov     qword ptr [rax-8], 1
0x140010d41  mov     byte ptr [rax-45h], 0E0h
0x140010d45  dec     byte ptr [rdi+43h]
0x140010d48  add     qword ptr [rdi+0B8h], 0FFFFFFFFFFFFFFB8h
0x140010d50  mov     rcx, [rsi+8]
0x140010d54  cmp     [rcx], rsi
0x140010d57  jz      short loc_140010D60
0x140010d59  mov     ecx, 3
0x140010d5e  int     29h; Win8: RtlFailFast(ecx)
0x140010d60  lea     rax, [rdi+0A8h]
0x140010d67  mov     [rax+8], rcx
0x140010d6b  mov     [rax], rsi
0x140010d6e  mov     [rcx], rax
0x140010d71  lea     rcx, [rsp+68h+LockHandle]; LockHandle
0x140010d76  mov     [rsi+8], rax
0x140010d7a  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140010d81  nop     dword ptr [rax+rax+00h]
0x140010d86  mov     ebx, 103h
0x140010d8b  mov     eax, ebx
0x140010d8d  add     rsp, 48h
0x140010d91  pop     rdi
0x140010d92  pop     rsi
0x140010d93  pop     rbp
0x140010d94  pop     rbx
0x140010d95  retn
0x140010d97  lea     rcx, [rsi+130h]; SpinLock
0x140010d9e  lea     rdx, [rsp+68h+LockHandle]; LockHandle
0x140010da3  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140010daa  nop     dword ptr [rax+rax+00h]
0x140010daf  mov     rcx, [rsi+0F8h]; RunRefCacheAware
0x140010db6  call    cs:__imp_ExAcquireRundownProtectionCacheAware
0x140010dbd  nop     dword ptr [rax+rax+00h]
0x140010dc2  test    al, al
0x140010dc4  jz      loc_140010CE9
0x140010dca  lea     rcx, [rsp+68h+LockHandle]; LockHandle
0x140010dcf  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140010dd6  nop     dword ptr [rax+rax+00h]
0x140010ddb  jmp     loc_140010C41
0x140010de0  mov     rcx, [rsi+0F8h]; RunRefCacheAware
0x140010de7  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x140010dee  nop     dword ptr [rax+rax+00h]
0x140010df3  mov     ebx, 0C000000Eh
0x140010df8  jmp     loc_140010CD3
```
