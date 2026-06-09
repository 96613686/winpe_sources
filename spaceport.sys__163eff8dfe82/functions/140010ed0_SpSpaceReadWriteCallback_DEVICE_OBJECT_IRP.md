# SpSpaceReadWriteCallback(_DEVICE_OBJECT *,_IRP *)

- ea: `0x140010ed0`
- end: `0x140011408`
- name: `?SpSpaceReadWriteCallback@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `1336`
- prototype: `int(struct _DEVICE_OBJECT *, struct _IRP *)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140010b90`
- `0x140031928`

## callees

- `0x14000e0f0`
- `0x140010ed0`
- `0x140011570`
- `0x140015700`
- `0x140015740`
- `0x14001aec0`
- `0x140068150`

## import_xrefs

- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1400110e9`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1400110e9`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14001102e`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14001102e`
- `ntoskrnl!IofCallDriver` at `0x14001138f`
- `ntoskrnl!IofCallDriver` at `0x14001138f`
- `ntoskrnl!KeCancelTimer` at `0x140011081`
- `ntoskrnl!KeCancelTimer` at `0x140011081`
- `ntoskrnl!IoQueueWorkItem` at `0x1400110c2`
- `ntoskrnl!IoQueueWorkItem` at `0x1400110c2`
- `ntoskrnl!IofCompleteRequest` at `0x1400113e3`
- `ntoskrnl!IofCompleteRequest` at `0x1400113e3`
- `ntoskrnl!KeClearEvent` at `0x14001106b`
- `ntoskrnl!KeClearEvent` at `0x14001106b`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400110d3`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400110d3`

## pseudocode

```c
__int64 __fastcall SpSpaceReadWriteCallback(struct _DEVICE_OBJECT *a1, struct _IRP *a2)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rsi
  char *DeviceExtension; // rbp
  char v5; // r12
  __int64 Length; // r9
  LARGE_INTEGER ByteOffset; // r8
  int v8; // edx
  UCHAR MinorFunction; // al
  __int64 v10; // rcx
  int v11; // ebx
  _DWORD *v12; // rbx
  struct _IO_STACK_LOCATION *v13; // rax
  struct _IRP::$::$2AD798E65616C4F7304824DBFA27E419::$665C8370128C04AB892B069E6FB086E8 *p_ListEntry; // rsi
  struct _IO_STACK_LOCATION *v15; // rax
  struct _IO_STACK_LOCATION *v16; // rax
  struct _LIST_ENTRY *v17; // rcx
  struct _IO_WORKITEM *v18; // rcx
  struct _IO_STACK_LOCATION *v19; // rax
  struct _IO_STACK_LOCATION *v20; // rax
  UCHAR v21; // al
  struct _IO_STACK_LOCATION *v22; // rbx
  __int64 v23; // rax
  unsigned __int64 v24; // r14
  unsigned __int64 QuadPart; // r15
  SIO_CACHE *v26; // rcx
  SIO_VDT *v27; // rcx
  __int64 v28; // rax
  int IsReadable; // eax
  struct _DEVICE_OBJECT *v30; // rcx
  __int64 v31; // rdx
  struct _IO_STACK_LOCATION *v32; // rcx
  bool v33; // zf
  struct _IO_STACK_LOCATION *v34; // rcx
  struct _IO_STACK_LOCATION *v35; // rax
  _BYTE LockHandle[32]; // [rsp+40h] [rbp-68h] BYREF
  LARGE_INTEGER v38; // [rsp+60h] [rbp-48h]
  __int64 v39; // [rsp+B0h] [rbp+8h] BYREF
  __int64 v40; // [rsp+B8h] [rbp+10h] BYREF

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  DeviceExtension = (char *)a1->DeviceExtension;
  v5 = 1;
  Length = CurrentStackLocation->Parameters.Read.Length;
  ByteOffset = CurrentStackLocation->Parameters.Read.ByteOffset;
  a2->IoStatus.Information = 0;
  v8 = 1;
  v39 = 0x100000000LL;
  if ( *(_BYTE *)(*(_QWORD *)(*((_QWORD *)DeviceExtension + 404) + 1160LL) + 70LL)
    && ((CurrentStackLocation->Flags & 1) == 0 || CurrentStackLocation->Parameters.Create.Options != 54945106) )
  {
    LOBYTE(v39) = 1;
  }
  if ( CurrentStackLocation->MajorFunction == 4 )
  {
    MinorFunction = CurrentStackLocation->MinorFunction;
    if ( MinorFunction != 82 && MinorFunction != 85 )
    {
      v10 = *((_QWORD *)DeviceExtension + 404);
      if ( *(_QWORD *)(v10 + 376) )
      {
        v11 = (*(__int64 (__fastcall **)(_QWORD, __int64, LARGE_INTEGER, __int64, __int64 *))(**(_QWORD **)(v10 + 392)
                                                                                            + 96LL))(
                *(_QWORD *)(v10 + 392),
                35,
                ByteOffset,
                Length,
                &v39);
        if ( v11 < 0 )
        {
LABEL_22:
          ExReleaseRundownProtectionCacheAware(*((PEX_RUNDOWN_REF_CACHE_AWARE *)DeviceExtension + 31));
          goto LABEL_54;
        }
        v8 = HIDWORD(v39);
      }
    }
  }
  if ( v8 != 1 )
  {
    CurrentStackLocation->MinorFunction = 82;
    v12 = DeviceExtension + 1768;
    v13 = a2->Tail.Overlay.CurrentStackLocation;
    p_ListEntry = (struct _IRP::$::$2AD798E65616C4F7304824DBFA27E419::$665C8370128C04AB892B069E6FB086E8 *)&a2->Tail.Overlay.ListEntry;
    *(_OWORD *)&v13[-1].MajorFunction = *(_OWORD *)&v13->MajorFunction;
    *(_OWORD *)&v13[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&v13->Parameters.NotifyDirectoryEx.CompletionFilter;
    *(_OWORD *)(&v13[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&v13->Parameters.SetQuota + 6);
    v13[-1].FileObject = v13->FileObject;
    v13[-1].Control = 0;
    v15 = a2->Tail.Overlay.CurrentStackLocation;
    *(_OWORD *)&LockHandle[8] = 0;
    v15[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)SpIoCompletionRoutine;
    v15[-1].Context = (PVOID)1;
    v15[-1].Control = -32;
    v16 = --a2->Tail.Overlay.CurrentStackLocation;
    --a2->CurrentLocation;
    v16->Control |= 1u;
    *(_QWORD *)LockHandle = 0;
    KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)DeviceExtension + 246, (PKLOCK_QUEUE_HANDLE)LockHandle);
    if ( a2 != (struct _IRP *)-168LL )
    {
      v17 = (struct _LIST_ENTRY *)*((_QWORD *)DeviceExtension + 242);
      if ( (char *)v17->Flink != DeviceExtension + 1928 )
        __fastfail(3u);
      p_ListEntry->ListEntry.Flink = (struct _LIST_ENTRY *)(DeviceExtension + 1928);
      a2->Tail.Overlay.ListEntry.Blink = v17;
      v17->Flink = &p_ListEntry->ListEntry;
      *((_QWORD *)DeviceExtension + 242) = p_ListEntry;
    }
    KeClearEvent((PRKEVENT)DeviceExtension + 81);
    if ( (*v12 & 4) != 0 && KeCancelTimer((PKTIMER)(DeviceExtension + 1800)) )
      *v12 &= ~4u;
    *v12 |= 2u;
    if ( (*v12 & 1) == 0 )
    {
      _InterlockedIncrement((volatile signed __int32 *)DeviceExtension + 443);
      v18 = (struct _IO_WORKITEM *)*((_QWORD *)DeviceExtension + 222);
      *v12 |= 1u;
      IoQueueWorkItem(v18, SpWorkItemWorkerRoutine, CriticalWorkQueue, DeviceExtension + 1768);
    }
    KeReleaseInStackQueuedSpinLock((PKLOCK_QUEUE_HANDLE)LockHandle);
    v11 = 259;
    goto LABEL_22;
  }
  v19 = a2->Tail.Overlay.CurrentStackLocation;
  *(_OWORD *)&v19[-1].MajorFunction = *(_OWORD *)&v19->MajorFunction;
  *(_OWORD *)&v19[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&v19->Parameters.NotifyDirectoryEx.CompletionFilter;
  *(_OWORD *)(&v19[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&v19->Parameters.SetQuota + 6);
  v19[-1].FileObject = v19->FileObject;
  v19[-1].Control = 0;
  v20 = a2->Tail.Overlay.CurrentStackLocation;
  v20[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)SpIoCompletionRoutine;
  v20[-1].Context = (PVOID)2;
  v20[-1].Control = -32;
  --a2->Tail.Overlay.CurrentStackLocation;
  --a2->CurrentLocation;
  v21 = CurrentStackLocation->MinorFunction;
  v22 = a2->Tail.Overlay.CurrentStackLocation;
  if ( v21 == 84 )
    goto LABEL_51;
  if ( v21 == 85 )
    goto LABEL_51;
  v38.QuadPart = 0;
  v23 = *((_QWORD *)DeviceExtension + 404);
  memset(LockHandle, 0, sizeof(LockHandle));
  v24 = v22->Parameters.Read.Length;
  QuadPart = v22->Parameters.Read.ByteOffset.QuadPart;
  v40 = 0;
  if ( *(_QWORD *)(v23 + 288) || (v22->Flags & 1) != 0 && (v22->Parameters.Create.Options & 0xFFFFFE00) == 0x52434E00 )
    goto LABEL_51;
  if ( *((_DWORD *)WPP_MAIN_CB.DeviceExtension + 122) != -1 || v22->MajorFunction == 4 && !DeviceExtension[162] )
    goto LABEL_51;
  v26 = (SIO_CACHE *)*((_QWORD *)DeviceExtension + 18);
  if ( v26 )
  {
    if ( !SIO_CACHE::CanBypass(v26, QuadPart, v24) )
      goto LABEL_51;
  }
  v27 = (SIO_VDT *)*((_QWORD *)DeviceExtension + 17);
  if ( v27 )
  {
    if ( !SIO_VDT::IsValid(v27, QuadPart, v24) )
      goto LABEL_51;
  }
  LockHandle[0] = v22->MajorFunction;
  v28 = *((_QWORD *)DeviceExtension + 404);
  *(_DWORD *)&LockHandle[12] = -1;
  if ( (*(int (__fastcall **)(_QWORD, __int64, unsigned __int64, unsigned __int64, _BYTE *, __int64 *))(**(_QWORD **)(v28 + 392) + 88LL))(
         *(_QWORD *)(v28 + 392),
         34,
         QuadPart,
         v24,
         LockHandle,
         &v40) < 0
    || *(_QWORD *)&LockHandle[24] != v24 )
  {
    goto LABEL_51;
  }
  ByteOffset = *(LARGE_INTEGER *)&LockHandle[16];
  if ( v22->MajorFunction == 3 )
  {
    IsReadable = SC_DRIVE::IsReadable(*(SC_DRIVE **)&LockHandle[16]);
LABEL_41:
    if ( IsReadable < 0 )
      goto LABEL_51;
    goto LABEL_42;
  }
  if ( v22->MajorFunction == 4 )
  {
    IsReadable = SC_DRIVE::IsWritable(*(SC_DRIVE **)&LockHandle[16]);
    goto LABEL_41;
  }
LABEL_42:
  v30 = *(struct _DEVICE_OBJECT **)(ByteOffset.QuadPart + 656);
  if ( a2->CurrentLocation > v30->StackSize )
  {
    v22->DeviceObject = v30;
    v31 = 0;
    v32 = a2->Tail.Overlay.CurrentStackLocation;
    *(_OWORD *)&v32[-1].MajorFunction = *(_OWORD *)&v32->MajorFunction;
    *(_OWORD *)&v32[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&v32->Parameters.NotifyDirectoryEx.CompletionFilter;
    *(_OWORD *)(&v32[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&v32->Parameters.SetQuota + 6);
    v32[-1].FileObject = v32->FileObject;
    v32[-1].Control = 0;
    v33 = v32[-1].MajorFunction == 3;
    v32[-1].Parameters.Read.ByteOffset = v38;
    if ( v33 && *(_DWORD *)(ByteOffset.QuadPart + 1344) )
    {
      _InterlockedAdd64((volatile signed __int64 *)(ByteOffset.QuadPart + 1352), v24);
      v31 = 1;
    }
    v32[-1].Flags |= 0x10u;
    v32[-1].MinorFunction = 0;
    v34 = a2->Tail.Overlay.CurrentStackLocation;
    v34->MinorFunction = 83;
    v34->Parameters.WMI.ProviderId = 1833528662;
    v34->Parameters.QueryDirectory.FileName = (PUNICODE_STRING)(*((_QWORD *)DeviceExtension + 404) + 24LL);
    v34->Parameters.Read.ByteOffset.QuadPart = *(unsigned int *)&LockHandle[8];
    v34->Parameters.CreatePipe.Parameters = (PNAMED_PIPE_CREATE_PARAMETERS)*(unsigned int *)&LockHandle[12];
    v35 = a2->Tail.Overlay.CurrentStackLocation;
    v35[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)SP_DRIVE::OnCompletion;
    v35[-1].Context = (PVOID)(ByteOffset.QuadPart | v31);
    v35[-1].Control = -32;
    CurrentStackLocation->MinorFunction = 83;
    if ( *(_BYTE *)(*(_QWORD *)(*((_QWORD *)DeviceExtension + 404) + 1160LL) + 66LL) )
      CurrentStackLocation[-1].Flags &= ~4u;
    v11 = IofCallDriver(CurrentStackLocation[-1].DeviceObject, a2);
    if ( v11 < 0 )
      v11 = 259;
    v5 = 0;
    goto LABEL_54;
  }
LABEL_51:
  if ( CurrentStackLocation->MinorFunction != 85 )
    CurrentStackLocation->MinorFunction = 84;
  v11 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))SP_DEVICE::Prepare)(
          DeviceExtension + 8,
          a2,
          (LARGE_INTEGER)ByteOffset.QuadPart,
          Length);
LABEL_54:
  if ( v11 != 259 && v5 )
  {
    a2->IoStatus.Status = v11;
    IofCompleteRequest(a2, 0);
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x140010ed0  mov     rax, rsp
0x140010ed3  push    rbp
0x140010ed4  push    rsi
0x140010ed5  push    rdi
0x140010ed6  push    r12
0x140010ed8  push    r13
0x140010eda  push    r14
0x140010edc  sub     rsp, 78h
0x140010ee0  mov     rsi, [rdx+0B8h]
0x140010ee7  xor     r13d, r13d
0x140010eea  mov     rbp, [rcx+40h]
0x140010eee  mov     rdi, rdx
0x140010ef1  mov     r12b, 1
0x140010ef4  mov     r9d, [rsi+8]
0x140010ef8  mov     r8, [rsi+18h]
0x140010efc  mov     [rdx+38h], r13
0x140010f00  mov     edx, 1
0x140010f05  mov     [rax+8], r13
0x140010f09  mov     [rax+0Ch], edx
0x140010f0c  mov     rax, [rbp+0CA0h]
0x140010f13  mov     rcx, [rax+488h]
0x140010f1a  cmp     [rcx+46h], r13b
0x140010f1e  jz      short loc_140010F35
0x140010f20  test    [rsi+2], dl
0x140010f23  jz      short loc_140010F2E
0x140010f25  cmp     dword ptr [rsi+10h], 3466552h
0x140010f2c  jz      short loc_140010F35
0x140010f2e  mov     [rsp+0A8h+arg_0], dl
0x140010f35  cmp     byte ptr [rsi], 4
0x140010f38  mov     r14d, 103h
0x140010f3e  mov     [rsp+0A8h+arg_10], rbx
0x140010f46  jnz     short loc_140010F9A
0x140010f48  movzx   eax, byte ptr [rsi+1]
0x140010f4c  cmp     al, 52h ; 'R'
0x140010f4e  jz      short loc_140010F9A
0x140010f50  cmp     al, 55h ; 'U'
0x140010f52  jz      short loc_140010F9A
0x140010f54  mov     rcx, [rbp+0CA0h]
0x140010f5b  cmp     [rcx+178h], r13
0x140010f62  jz      short loc_140010F9A
0x140010f64  mov     rcx, [rcx+188h]
0x140010f6b  lea     rdx, [rsp+0A8h+arg_0]
0x140010f73  mov     [rsp+0A8h+var_88], rdx
0x140010f78  mov     edx, 23h ; '#'
0x140010f7d  mov     rax, [rcx]
0x140010f80  mov     rax, [rax+60h]
0x140010f84  call    _guard_dispatch_icall
0x140010f89  mov     ebx, eax
0x140010f8b  test    eax, eax
0x140010f8d  js      loc_1400110E2
0x140010f93  mov     edx, [rsp+0A8h+arg_4]
0x140010f9a  lea     rcx, ?SpIoCompletionRoutine@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z; SpIoCompletionRoutine(_DEVICE_OBJECT *,_IRP *,void *)
0x140010fa1  cmp     edx, 1
0x140010fa4  jz      loc_1400110FA
0x140010faa  mov     byte ptr [rsi+1], 52h ; 'R'
0x140010fae  lea     rbx, [rbp+6E8h]
0x140010fb5  mov     rax, [rdi+0B8h]
0x140010fbc  lea     rdx, [rsp+0A8h+LockHandle]; LockHandle
0x140010fc1  lea     rsi, [rdi+0A8h]
0x140010fc8  movups  xmm0, xmmword ptr [rax]
0x140010fcb  movups  xmmword ptr [rax-48h], xmm0
0x140010fcf  movups  xmm1, xmmword ptr [rax+10h]
0x140010fd3  movups  xmmword ptr [rax-38h], xmm1
0x140010fd7  movups  xmm0, xmmword ptr [rax+20h]
0x140010fdb  movups  xmmword ptr [rax-28h], xmm0
0x140010fdf  movsd   xmm1, qword ptr [rax+30h]
0x140010fe4  xorps   xmm0, xmm0
0x140010fe7  movsd   qword ptr [rax-18h], xmm1
0x140010fec  mov     [rax-45h], r13b
0x140010ff0  mov     rax, [rdi+0B8h]
0x140010ff7  movups  xmmword ptr [rsp+0A8h+LockHandle+8], xmm0
0x140010ffc  mov     [rax-10h], rcx
0x140011000  lea     rcx, [rbx+0C8h]; SpinLock
0x140011007  mov     qword ptr [rax-8], 1
0x14001100f  mov     byte ptr [rax-45h], 0E0h
0x140011013  add     qword ptr [rdi+0B8h], 0FFFFFFFFFFFFFFB8h
0x14001101b  mov     rax, [rdi+0B8h]
0x140011022  dec     byte ptr [rdi+43h]
0x140011025  or      [rax+3], r12b
0x140011029  mov     qword ptr [rsp+0A8h+LockHandle], r13
0x14001102e  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140011035  nop     dword ptr [rax+rax+00h]
0x14001103a  test    rsi, rsi
0x14001103d  jz      short loc_140011064
0x14001103f  lea     rax, [rbx+0A0h]
0x140011046  mov     rcx, [rax+8]
0x14001104a  cmp     [rcx], rax
0x14001104d  jz      short loc_140011056
0x14001104f  mov     ecx, 3
0x140011054  int     29h; Win8: RtlFailFast(ecx)
0x140011056  mov     [rsi], rax
0x140011059  mov     [rsi+8], rcx
0x14001105d  mov     [rcx], rsi
0x140011060  mov     [rax+8], rsi
0x140011064  lea     rcx, [rbx+0B0h]; Event
0x14001106b  call    cs:__imp_KeClearEvent
0x140011072  nop     dword ptr [rax+rax+00h]
0x140011077  mov     eax, [rbx]
0x140011079  test    al, 4
0x14001107b  jz      short loc_140011098
0x14001107d  lea     rcx, [rbx+20h]; PKTIMER
0x140011081  call    cs:__imp_KeCancelTimer
0x140011088  nop     dword ptr [rax+rax+00h]
0x14001108d  test    al, al
0x14001108f  jz      short loc_140011098
0x140011091  mov     eax, [rbx]
0x140011093  and     eax, 0FFFFFFFBh
0x140011096  mov     [rbx], eax
0x140011098  mov     eax, [rbx]
0x14001109a  or      eax, 2
0x14001109d  mov     [rbx], eax
0x14001109f  mov     eax, [rbx]
0x1400110a1  test    r12b, al
0x1400110a4  jnz     short loc_1400110CE
0x1400110a6  lock inc dword ptr [rbx+4]
0x1400110aa  mov     eax, [rbx]
0x1400110ac  lea     rdx, ?SpWorkItemWorkerRoutine@@YAXPEAU_DEVICE_OBJECT@@PEAX@Z; WorkerRoutine
0x1400110b3  mov     rcx, [rbx+8]; IoWorkItem
0x1400110b7  or      eax, 1
0x1400110ba  mov     r9, rbx; Context
0x1400110bd  mov     [rbx], eax
0x1400110bf  xor     r8d, r8d; QueueType
0x1400110c2  call    cs:__imp_IoQueueWorkItem
0x1400110c9  nop     dword ptr [rax+rax+00h]
0x1400110ce  lea     rcx, [rsp+0A8h+LockHandle]; LockHandle
0x1400110d3  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1400110da  nop     dword ptr [rax+rax+00h]
0x1400110df  mov     ebx, r14d
0x1400110e2  mov     rcx, [rbp+0F8h]; RunRefCacheAware
0x1400110e9  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x1400110f0  nop     dword ptr [rax+rax+00h]
0x1400110f5  jmp     loc_1400113D1
0x1400110fa  mov     rax, [rdi+0B8h]
0x140011101  mov     [rsp+0A8h+var_38], r15
0x140011106  movups  xmm0, xmmword ptr [rax]
0x140011109  movups  xmmword ptr [rax-48h], xmm0
0x14001110d  movups  xmm1, xmmword ptr [rax+10h]
0x140011111  movups  xmmword ptr [rax-38h], xmm1
0x140011115  movups  xmm0, xmmword ptr [rax+20h]
0x140011119  movups  xmmword ptr [rax-28h], xmm0
0x14001111d  movsd   xmm1, qword ptr [rax+30h]
0x140011122  movsd   qword ptr [rax-18h], xmm1
0x140011127  mov     [rax-45h], r13b
0x14001112b  mov     rax, [rdi+0B8h]
0x140011132  mov     [rax-10h], rcx
0x140011136  mov     qword ptr [rax-8], 2
0x14001113e  mov     byte ptr [rax-45h], 0E0h
0x140011142  add     qword ptr [rdi+0B8h], 0FFFFFFFFFFFFFFB8h
0x14001114a  dec     byte ptr [rdi+43h]
0x14001114d  movzx   eax, byte ptr [rsi+1]
0x140011151  mov     rbx, [rdi+0B8h]
0x140011158  cmp     al, 54h ; 'T'
0x14001115a  jz      loc_1400113B4
0x140011160  cmp     al, 55h ; 'U'
0x140011162  jz      loc_1400113B4
0x140011168  xor     eax, eax
0x14001116a  xorps   xmm0, xmm0
0x14001116d  mov     [rsp+0A8h+var_48], rax
0x140011172  mov     rax, [rbp+0CA0h]
0x140011179  movups  xmmword ptr [rsp+0A8h+LockHandle], xmm0
0x14001117e  movups  xmmword ptr [rsp+0A8h+LockHandle+10h], xmm0
0x140011183  mov     r14d, [rbx+8]
0x140011187  mov     r15, [rbx+18h]
0x14001118b  mov     [rsp+0A8h+arg_8], r13
0x140011193  cmp     [rax+120h], r13
0x14001119a  jnz     loc_1400113AE
0x1400111a0  test    [rbx+2], r12b
0x1400111a4  jz      short loc_1400111B9
0x1400111a6  mov     eax, [rbx+10h]
0x1400111a9  and     eax, 0FFFFFE00h
0x1400111ae  cmp     eax, 52434E00h
0x1400111b3  jz      loc_1400113AE
0x1400111b9  mov     rax, cs:WPP_MAIN_CB.DeviceExtension
0x1400111c0  cmp     dword ptr [rax+1E8h], 0FFFFFFFFh
0x1400111c7  jnz     loc_1400113AE
0x1400111cd  cmp     byte ptr [rbx], 4
0x1400111d0  jnz     short loc_1400111DF
0x1400111d2  cmp     [rbp+0A2h], r13b
0x1400111d9  jz      loc_1400113AE
0x1400111df  mov     rcx, [rbp+90h]; this
0x1400111e6  test    rcx, rcx
0x1400111e9  jz      short loc_1400111FE
0x1400111eb  mov     r8d, r14d; unsigned int
0x1400111ee  mov     rdx, r15; unsigned __int64
0x1400111f1  call    ?CanBypass@SIO_CACHE@@QEAAE_KK@Z; SIO_CACHE::CanBypass(unsigned __int64,ulong)
0x1400111f6  test    al, al
0x1400111f8  jz      loc_1400113AE
0x1400111fe  mov     rcx, [rbp+88h]; this
0x140011205  test    rcx, rcx
0x140011208  jz      short loc_14001121D
0x14001120a  mov     r8, r14; unsigned __int64
0x14001120d  mov     rdx, r15; unsigned __int64
0x140011210  call    ?IsValid@SIO_VDT@@QEAAE_K0@Z; SIO_VDT::IsValid(unsigned __int64,unsigned __int64)
0x140011215  test    al, al
0x140011217  jz      loc_1400113AE
0x14001121d  movzx   eax, byte ptr [rbx]
0x140011220  lea     rdx, [rsp+0A8h+arg_8]
0x140011228  mov     [rsp+0A8h+LockHandle], al
0x14001122c  mov     r9, r14
0x14001122f  mov     rax, [rbp+0CA0h]
0x140011236  mov     r8, r15
0x140011239  mov     [rsp+0A8h+var_80], rdx
0x14001123e  lea     rdx, [rsp+0A8h+LockHandle]
0x140011243  mov     dword ptr [rsp+0A8h+LockHandle+0Ch], 0FFFFFFFFh
0x14001124b  mov     [rsp+0A8h+var_88], rdx
0x140011250  mov     edx, 22h ; '"'
0x140011255  mov     rcx, [rax+188h]
0x14001125c  mov     rax, [rcx]
0x14001125f  mov     rax, [rax+58h]
0x140011263  call    _guard_dispatch_icall
0x140011268  test    eax, eax
0x14001126a  js      loc_1400113AE
0x140011270  cmp     qword ptr [rsp+0A8h+LockHandle+18h], r14
0x140011275  jnz     loc_1400113AE
0x14001127b  movzx   ecx, byte ptr [rbx]
0x14001127e  mov     r8, qword ptr [rsp+0A8h+LockHandle+10h]
0x140011283  sub     ecx, 3
0x140011286  jz      short loc_140011297
0x140011288  cmp     ecx, 1
0x14001128b  jnz     short loc_1400112A7
0x14001128d  mov     rcx, r8; this
0x140011290  call    ?IsWritable@SC_DRIVE@@QEAAJXZ; SC_DRIVE::IsWritable(void)
0x140011295  jmp     short loc_14001129F
0x140011297  mov     rcx, r8; this
0x14001129a  call    ?IsReadable@SC_DRIVE@@QEAAJXZ; SC_DRIVE::IsReadable(void)
0x14001129f  test    eax, eax
0x1400112a1  js      loc_1400113AE
0x1400112a7  mov     rcx, [r8+290h]
0x1400112ae  movzx   eax, byte ptr [rcx+4Ch]
0x1400112b2  cmp     [rdi+43h], al
0x1400112b5  jle     loc_1400113AE
0x1400112bb  mov     [rbx+28h], rcx
0x1400112bf  mov     rdx, r13
0x1400112c2  mov     rcx, [rdi+0B8h]
0x1400112c9  movups  xmm0, xmmword ptr [rcx]
0x1400112cc  movups  xmmword ptr [rcx-48h], xmm0
0x1400112d0  movups  xmm1, xmmword ptr [rcx+10h]
0x1400112d4  movups  xmmword ptr [rcx-38h], xmm1
0x1400112d8  movups  xmm0, xmmword ptr [rcx+20h]
0x1400112dc  movups  xmmword ptr [rcx-28h], xmm0
0x1400112e0  movsd   xmm1, qword ptr [rcx+30h]
0x1400112e5  movsd   qword ptr [rcx-18h], xmm1
0x1400112ea  mov     [rcx-45h], r13b
0x1400112ee  cmp     byte ptr [rcx-48h], 3
0x1400112f2  mov     rax, [rsp+0A8h+var_48]
0x1400112f7  mov     [rcx-30h], rax
0x1400112fb  jnz     short loc_140011315
0x1400112fd  mov     eax, [r8+540h]
0x140011304  test    eax, eax
0x140011306  jz      short loc_140011315
0x140011308  lock add [r8+548h], r14
0x140011310  mov     edx, 1
0x140011315  or      byte ptr [rcx-46h], 10h
0x140011319  or      rdx, r8
0x14001131c  mov     [rcx-47h], r13b
0x140011320  mov     rcx, [rdi+0B8h]
0x140011327  mov     byte ptr [rcx+1], 53h ; 'S'
0x14001132b  mov     qword ptr [rcx+8], 6D496D56h
0x140011333  mov     rax, [rbp+0CA0h]
0x14001133a  add     rax, 18h
0x14001133e  mov     [rcx+10h], rax
0x140011342  mov     eax, dword ptr [rsp+0A8h+LockHandle+8]
0x140011346  mov     [rcx+18h], rax
0x14001134a  mov     eax, dword ptr [rsp+0A8h+LockHandle+0Ch]
0x14001134e  mov     [rcx+20h], rax
0x140011352  lea     rcx, ?OnCompletion@SP_DRIVE@@SAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z; SP_DRIVE::OnCompletion(_DEVICE_OBJECT *,_IRP *,void *)
0x140011359  mov     rax, [rdi+0B8h]
0x140011360  mov     [rax-10h], rcx
0x140011364  mov     [rax-8], rdx
0x140011368  mov     byte ptr [rax-45h], 0E0h
0x14001136c  mov     byte ptr [rsi+1], 53h ; 'S'
0x140011370  mov     rax, [rbp+0CA0h]
0x140011377  mov     rdx, [rax+488h]
0x14001137e  cmp     [rdx+42h], r13b
0x140011382  jz      short loc_140011388
0x140011384  and     byte ptr [rsi-46h], 0FBh
0x140011388  mov     rcx, [rsi-20h]; DeviceObject
0x14001138c  mov     rdx, rdi; Irp
0x14001138f  call    cs:__imp_IofCallDriver
0x140011396  nop     dword ptr [rax+rax+00h]
0x14001139b  test    eax, eax
0x14001139d  mov     ebx, eax
0x14001139f  mov     r14d, 103h
0x1400113a5  cmovs   ebx, r14d
0x1400113a9  xor     r12b, r12b
0x1400113ac  jmp     short loc_1400113CC
0x1400113ae  mov     r14d, 103h
0x1400113b4  cmp     byte ptr [rsi+1], 55h ; 'U'
0x1400113b8  jz      short loc_1400113BE
0x1400113ba  mov     byte ptr [rsi+1], 54h ; 'T'
0x1400113be  mov     rdx, rdi
0x1400113c1  lea     rcx, [rbp+8]
0x1400113c5  call    ?Prepare@SP_DEVICE@@QEAAJPEAU_IRP@@W4_SC_OPERATION@@@Z; SP_DEVICE::Prepare(_IRP *,_SC_OPERATION)
0x1400113ca  mov     ebx, eax
0x1400113cc  mov     r15, [rsp+0A8h+var_38]
0x1400113d1  cmp     ebx, r14d
0x1400113d4  jz      short loc_1400113EF
0x1400113d6  test    r12b, r12b
0x1400113d9  jz      short loc_1400113EF
0x1400113db  xor     edx, edx; PriorityBoost
  ... truncated ...
```
