# SP_DEVICE::AcquireRundownShared(_IRP *)

- ea: `0x1400108f0`
- end: `0x140010a6d`
- name: `?AcquireRundownShared@SP_DEVICE@@QEAAJPEAU_IRP@@@Z`
- size: `381`
- prototype: `__int64 __fastcall(SP_DEVICE *__hidden this, struct _IRP *)`
- caller_count: `14`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140010730`
- `0x140033d00`
- `0x140034898`
- `0x140034a6c`
- `0x140034cac`
- `0x140034d80`
- `0x1400a66ac`
- `0x1400a6760`
- `0x1400a68e0`
- `0x1400a6b08`
- `0x1400b6dc0`
- `0x1400b8d60`
- `0x1400b9340`
- `0x1400b95b0`

## callees

- `0x1400108f0`

## import_xrefs

- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140010a57`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140010a57`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140010a13`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140010a13`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x14001091d`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x140010a26`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x14001091d`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x140010a26`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400109e8`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140010a3f`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400109e8`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140010a3f`

## pseudocode

```c
__int64 __fastcall SP_DEVICE::AcquireRundownShared(SP_DEVICE *this, struct _IRP *a2)
{
  struct _EX_RUNDOWN_REF_CACHE_AWARE *v3; // rcx
  unsigned int v5; // edi
  struct _LIST_ENTRY *v7; // rbx
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  struct _IO_STACK_LOCATION *v9; // rax
  struct _LIST_ENTRY *Blink; // rcx
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+20h] [rbp-28h] BYREF

  v3 = (struct _EX_RUNDOWN_REF_CACHE_AWARE *)*((_QWORD *)this + 30);
  memset(&LockHandle, 0, sizeof(LockHandle));
  v5 = 0;
  if ( ExAcquireRundownProtectionCacheAware(v3) )
  {
LABEL_2:
    if ( !*((_QWORD *)this + 403) )
    {
      ExReleaseRundownProtectionCacheAware(*((PEX_RUNDOWN_REF_CACHE_AWARE *)this + 30));
      return (unsigned int)-1073741810;
    }
    return v5;
  }
  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)this + 37, &LockHandle);
  if ( ExAcquireRundownProtectionCacheAware(*((PEX_RUNDOWN_REF_CACHE_AWARE *)this + 30)) )
  {
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    goto LABEL_2;
  }
  v7 = (struct _LIST_ENTRY *)((char *)this + 280);
  a2->Tail.Overlay.CurrentStackLocation->Control |= 1u;
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  *(_OWORD *)&CurrentStackLocation[-1].MajorFunction = *(_OWORD *)&CurrentStackLocation->MajorFunction;
  *(_OWORD *)&CurrentStackLocation[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&CurrentStackLocation->Parameters.NotifyDirectoryEx.CompletionFilter;
  *(_OWORD *)(&CurrentStackLocation[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&CurrentStackLocation->Parameters.SetQuota
                                                                             + 6);
  CurrentStackLocation[-1].FileObject = CurrentStackLocation->FileObject;
  CurrentStackLocation[-1].Control = 0;
  v9 = a2->Tail.Overlay.CurrentStackLocation;
  v9[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)SpIoCompletionRoutine;
  v9[-1].Context = (PVOID)1;
  v9[-1].Control = -32;
  --a2->CurrentLocation;
  --a2->Tail.Overlay.CurrentStackLocation;
  Blink = v7->Blink;
  if ( Blink->Flink != v7 )
    __fastfail(3u);
  a2->Tail.Overlay.ListEntry.Blink = Blink;
  a2->Tail.Overlay.ListEntry.Flink = v7;
  Blink->Flink = &a2->Tail.Overlay.ListEntry;
  v7->Blink = &a2->Tail.Overlay.ListEntry;
  KeReleaseInStackQueuedSpinLock(&LockHandle);
  return 259;
}

```

## disassembly

```asm
0x1400108f0  mov     [rsp+arg_0], rbx
0x1400108f5  mov     [rsp+arg_8], rsi
0x1400108fa  push    rdi
0x1400108fb  sub     rsp, 40h
0x1400108ff  mov     rbx, rcx
0x140010902  xorps   xmm0, xmm0
0x140010905  mov     rcx, [rcx+0F0h]; RunRefCacheAware
0x14001090c  xor     eax, eax
0x14001090e  movups  xmmword ptr [rsp+48h+LockHandle.LockQueue.Next], xmm0
0x140010913  mov     qword ptr [rsp+48h+LockHandle.OldIrql], rax
0x140010918  mov     rsi, rdx
0x14001091b  xor     edi, edi
0x14001091d  call    cs:__imp_ExAcquireRundownProtectionCacheAware
0x140010924  nop     dword ptr [rax+rax+00h]
0x140010929  test    al, al
0x14001092b  jz      loc_140010A07
0x140010931  cmp     qword ptr [rbx+0C98h], 0
0x140010939  jz      loc_140010A50
0x14001093f  mov     eax, edi
0x140010941  mov     rbx, [rsp+48h+arg_0]
0x140010946  mov     rsi, [rsp+48h+arg_8]
0x14001094b  add     rsp, 40h
0x14001094f  pop     rdi
0x140010950  retn
0x140010952  mov     rax, [rsi+0B8h]
0x140010959  lea     rcx, ?SpIoCompletionRoutine@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z; SpIoCompletionRoutine(_DEVICE_OBJECT *,_IRP *,void *)
0x140010960  add     rbx, 118h
0x140010967  or      byte ptr [rax+3], 1
0x14001096b  mov     rax, [rsi+0B8h]
0x140010972  movups  xmm0, xmmword ptr [rax]
0x140010975  movups  xmmword ptr [rax-48h], xmm0
0x140010979  movups  xmm1, xmmword ptr [rax+10h]
0x14001097d  movups  xmmword ptr [rax-38h], xmm1
0x140010981  movups  xmm0, xmmword ptr [rax+20h]
0x140010985  movups  xmmword ptr [rax-28h], xmm0
0x140010989  movsd   xmm1, qword ptr [rax+30h]
0x14001098e  movsd   qword ptr [rax-18h], xmm1
0x140010993  mov     [rax-45h], dil
0x140010997  mov     rax, [rsi+0B8h]
0x14001099e  mov     [rax-10h], rcx
0x1400109a2  mov     qword ptr [rax-8], 1
0x1400109aa  mov     byte ptr [rax-45h], 0E0h
0x1400109ae  dec     byte ptr [rsi+43h]
0x1400109b1  add     qword ptr [rsi+0B8h], 0FFFFFFFFFFFFFFB8h
0x1400109b9  mov     rcx, [rbx+8]
0x1400109bd  cmp     [rcx], rbx
0x1400109c0  jz      short loc_1400109C9
0x1400109c2  mov     ecx, 3
0x1400109c7  int     29h; Win8: RtlFailFast(ecx)
0x1400109c9  lea     rax, [rsi+0A8h]
0x1400109d0  mov     edi, 103h
0x1400109d5  mov     [rax+8], rcx
0x1400109d9  mov     [rax], rbx
0x1400109dc  mov     [rcx], rax
0x1400109df  lea     rcx, [rsp+48h+LockHandle]; LockHandle
0x1400109e4  mov     [rbx+8], rax
0x1400109e8  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1400109ef  nop     dword ptr [rax+rax+00h]
0x1400109f4  mov     rbx, [rsp+48h+arg_0]
0x1400109f9  mov     eax, edi
0x1400109fb  mov     rsi, [rsp+48h+arg_8]
0x140010a00  add     rsp, 40h
0x140010a04  pop     rdi
0x140010a05  retn
0x140010a07  lea     rcx, [rbx+128h]; SpinLock
0x140010a0e  lea     rdx, [rsp+48h+LockHandle]; LockHandle
0x140010a13  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140010a1a  nop     dword ptr [rax+rax+00h]
0x140010a1f  mov     rcx, [rbx+0F0h]; RunRefCacheAware
0x140010a26  call    cs:__imp_ExAcquireRundownProtectionCacheAware
0x140010a2d  nop     dword ptr [rax+rax+00h]
0x140010a32  test    al, al
0x140010a34  jz      loc_140010952
0x140010a3a  lea     rcx, [rsp+48h+LockHandle]; LockHandle
0x140010a3f  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140010a46  nop     dword ptr [rax+rax+00h]
0x140010a4b  jmp     loc_140010931
0x140010a50  mov     rcx, [rbx+0F0h]; RunRefCacheAware
0x140010a57  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x140010a5e  nop     dword ptr [rax+rax+00h]
0x140010a63  mov     edi, 0C000000Eh
0x140010a68  jmp     loc_14001093F
```
