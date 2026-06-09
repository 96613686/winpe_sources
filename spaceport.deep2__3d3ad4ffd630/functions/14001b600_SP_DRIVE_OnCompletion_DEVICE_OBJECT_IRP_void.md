# SP_DRIVE::OnCompletion(_DEVICE_OBJECT *,_IRP *,void *)

- ea: `0x14001b600`
- end: `0x14001c760`
- name: `?OnCompletion@SP_DRIVE@@SAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z`
- size: `4448`
- prototype: `static int(struct _DEVICE_OBJECT *, struct _IRP *, void *)`
- caller_count: `0`
- callee_count: `16`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14000200c`
- `0x1400032c4`
- `0x140008e30`
- `0x140011a30`
- `0x14001b600`
- `0x1400202d0`
- `0x140025890`
- `0x140027040`
- `0x14002e4a8`
- `0x140039844`
- `0x140039b60`
- `0x14003bfac`
- `0x14003d96c`
- `0x14006687c`
- `0x1400668f4`
- `0x1400680a0`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14001b9e3`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14001baa5`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14001bbb1`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14001c117`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14001c1d9`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14001c280`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14001c371`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14001c43a`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14001c63a`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14001b9e3`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14001baa5`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14001bbb1`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14001c117`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14001c1d9`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14001c280`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14001c371`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14001c43a`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14001c63a`
- `ntoskrnl!IoFreeIrp` at `0x14001c710`
- `ntoskrnl!IoFreeIrp` at `0x14001c710`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14001bc24`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14001c557`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14001bc24`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14001c557`
- `ntoskrnl!IoSetIoPriorityHint` at `0x14001bcad`
- `ntoskrnl!IoSetIoPriorityHint` at `0x14001bcad`
- `ntoskrnl!KeCancelTimer` at `0x14001c463`
- `ntoskrnl!KeCancelTimer` at `0x14001c69a`
- `ntoskrnl!KeCancelTimer` at `0x14001c463`
- `ntoskrnl!KeCancelTimer` at `0x14001c69a`
- `ntoskrnl!IoQueueWorkItem` at `0x14001c4a3`
- `ntoskrnl!IoQueueWorkItem` at `0x14001c6da`
- `ntoskrnl!IoQueueWorkItem` at `0x14001c4a3`
- `ntoskrnl!IoQueueWorkItem` at `0x14001c6da`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x14001c601`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x14001c601`
- `ntoskrnl!KeClearEvent` at `0x14001c44d`
- `ntoskrnl!KeClearEvent` at `0x14001c684`
- `ntoskrnl!KeClearEvent` at `0x14001c44d`
- `ntoskrnl!KeClearEvent` at `0x14001c684`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14001ba7c`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14001bac3`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14001bbf7`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14001bc16`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14001c1b0`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14001c2d6`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14001c40a`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14001c4b3`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14001c524`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14001c6ea`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14001ba7c`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14001bac3`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14001bbf7`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14001bc16`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14001c1b0`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14001c2d6`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14001c40a`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14001c4b3`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14001c524`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14001c6ea`
- `ntoskrnl!IoGetGenericIrpExtension` at `0x14001b674`
- `ntoskrnl!IoGetGenericIrpExtension` at `0x14001b6ae`
- `ntoskrnl!IoGetGenericIrpExtension` at `0x14001b6f0`
- `ntoskrnl!IoGetGenericIrpExtension` at `0x14001bcdb`
- `ntoskrnl!IoGetGenericIrpExtension` at `0x14001bd1a`
- `ntoskrnl!IoGetGenericIrpExtension` at `0x14001bd7d`
- `ntoskrnl!IoGetGenericIrpExtension` at `0x14001b674`
- `ntoskrnl!IoGetGenericIrpExtension` at `0x14001b6ae`
- `ntoskrnl!IoGetGenericIrpExtension` at `0x14001b6f0`
- `ntoskrnl!IoGetGenericIrpExtension` at `0x14001bcdb`
- `ntoskrnl!IoGetGenericIrpExtension` at `0x14001bd1a`
- `ntoskrnl!IoGetGenericIrpExtension` at `0x14001bd7d`
- `HAL!KeQueryPerformanceCounter` at `0x14001bcbb`
- `HAL!KeQueryPerformanceCounter` at `0x14001bcbb`

## pseudocode

```c
__int64 __fastcall SP_DRIVE::OnCompletion(struct _DEVICE_OBJECT *a1, struct _IRP *a2, unsigned __int64 a3)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rbx
  unsigned __int64 v4; // r12
  unsigned __int64 v5; // rdi
  unsigned int v7; // r15d
  int v8; // eax
  NTSTATUS v9; // esi
  __int64 v10; // rcx
  unsigned __int8 v11; // r12
  char v12; // r8
  unsigned __int8 v13; // bl
  __int64 v14; // r8
  int v15; // ecx
  _QWORD *v16; // rax
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 v19; // r9
  int v20; // r8d
  int v21; // r9d
  _QWORD *v22; // rdx
  __int64 v23; // rax
  int v24; // eax
  int v25; // eax
  int v26; // r12d
  char *v27; // rbx
  __int64 v28; // rax
  __int128 v29; // xmm1
  int v30; // eax
  int v31; // eax
  int v32; // ebx
  ULONG v33; // eax
  _DWORD *v34; // rdx
  LARGE_INTEGER ByteOffset; // r12
  int GenericIrpExtension; // eax
  NTSTATUS Status; // esi
  char v38; // al
  unsigned __int8 v39; // r13
  unsigned __int8 v40; // r12
  unsigned __int8 v41; // bl
  int v42; // r8d
  int v43; // r9d
  _QWORD *v44; // rax
  __int64 v45; // rcx
  __int64 v46; // rdx
  __int64 v47; // r8
  _QWORD *v48; // rcx
  struct _KSPIN_LOCK_QUEUE *v49; // rdx
  char v50; // al
  SIO_DIRTY_STATE *v51; // rcx
  int v52; // eax
  int v53; // eax
  int v54; // r13d
  char *DeviceExtension; // rbx
  int v56; // eax
  int v57; // eax
  int v58; // ebx
  int v59; // eax
  int v60; // eax
  char *v61; // rbx
  struct _IO_WORKITEM *v62; // rcx
  __int64 v63; // rax
  __int128 v64; // xmm1
  int v65; // ebx
  ULONG CurrentProcessorNumber; // eax
  _DWORD *v67; // rdx
  IRP *v68; // r14
  IRP *v69; // r13
  unsigned int v70; // ecx
  _DWORD *v71; // rbx
  _QWORD *v72; // rsi
  _QWORD *v73; // rcx
  struct _IO_WORKITEM *v74; // rcx
  unsigned __int8 v76; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int8 v77[3]; // [rsp+81h] [rbp-7Fh] BYREF
  int v78; // [rsp+84h] [rbp-7Ch]
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+88h] [rbp-78h] BYREF
  int v80; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int64 v81; // [rsp+A8h] [rbp-58h] BYREF
  _QWORD v82[2]; // [rsp+B0h] [rbp-50h] BYREF
  struct _KLOCK_QUEUE_HANDLE v83; // [rsp+C0h] [rbp-40h] BYREF
  struct _IO_STACK_LOCATION *QuadPart; // [rsp+E0h] [rbp-20h]
  __int64 v85; // [rsp+E8h] [rbp-18h] BYREF
  GUID v86; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v87; // [rsp+100h] [rbp+0h] BYREF
  __int64 v88; // [rsp+110h] [rbp+10h] BYREF
  __int64 v89; // [rsp+118h] [rbp+18h] BYREF
  int v90; // [rsp+168h] [rbp+68h] BYREF
  unsigned __int64 v91; // [rsp+170h] [rbp+70h] BYREF
  char v92; // [rsp+178h] [rbp+78h] BYREF

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  v4 = a3;
  LOBYTE(v4) = a3 & 1;
  QuadPart = CurrentStackLocation;
  v91 = v4;
  v5 = a3 & 0xFFFFFFFFFFFFFFFEuLL;
  if ( a2->PendingReturned )
    CurrentStackLocation->Control |= 1u;
  if ( CurrentStackLocation->MinorFunction != 83 )
  {
    ByteOffset = CurrentStackLocation->Parameters.Read.ByteOffset;
    QuadPart = (struct _IO_STACK_LOCATION *)ByteOffset.QuadPart;
    IoSetIoPriorityHint(a2, *(IO_PRIORITY_HINT *)(ByteOffset.QuadPart + 184));
    KeQueryPerformanceCounter(0);
    v90 = 0;
    GenericIrpExtension = IoGetGenericIrpExtension(a2, &v90, 4);
    Status = a2->IoStatus.Status;
    if ( GenericIrpExtension >= 0 )
    {
      v38 = BYTE1(v90) >> 2;
      v90 = 0;
      if ( (v38 & 1) != 0 )
      {
        if ( (int)IoGetGenericIrpExtension(a2, &v90, 4) >= 0
          && (v90 & 0x400) != 0
          && Status < 0
          && (HIWORD(v90) & 0xE00) == 0x400
          && ((unsigned __int8)(HIWORD(v90) >> 1) == 128 || (unsigned __int8)(HIWORD(v90) >> 1) == 129) )
        {
          Status = -1073740669;
        }
      }
      else if ( (int)IoGetGenericIrpExtension(a2, &v90, 4) >= 0 && (v90 & 0x400) == 0 )
      {
        if ( (v90 & 0x800) != 0 )
        {
          v39 = BYTE2(v90);
          v40 = HIBYTE(v90);
          v41 = BYTE1(v90) >> 4;
          if ( BYTE2(v90) == 93 )
          {
            switch ( HIBYTE(v90) )
            {
              case 0x10:
              case 0x11:
              case 0x12:
              case 0x13:
              case 0x14:
              case 0x15:
              case 0x16:
              case 0x17:
              case 0x18:
              case 0x19:
              case 0x1A:
              case 0x1B:
              case 0x1C:
              case 0x32:
              case 0x42:
              case 0x43:
                v82[0] = v5 + 508;
                if ( !memcmp((const void *)(v5 + 508), &GUID_NULL, 0x10u) )
                {
                  v43 = v5 + 404;
                  v82[0] = v5 + 404;
                }
                else
                {
                  v43 = v5 + 508;
                }
                if ( (Microsoft_Windows_StorageSpaces_DriverEnableBits & 4) != 0 )
                {
                  v44 = *(_QWORD **)(v5 + 672);
                  if ( v44 )
                  {
                    v45 = v44[21];
                    v46 = v44[17];
                    v47 = v44[15];
                  }
                  else
                  {
                    v45 = 0;
                    v46 = 0;
                    v47 = 0;
                  }
                  McTemplateK0juuudzzzzzzd_EtwWriteTransfer(
                    v45,
                    v46,
                    v47,
                    v43,
                    v41,
                    93,
                    v40,
                    *(_DWORD *)(v5 + 680),
                    *(_QWORD *)(v5 + 32),
                    *(_QWORD *)(v5 + 48),
                    *(_QWORD *)(v5 + 80),
                    v47,
                    v46,
                    v45,
                    *(_DWORD *)(v5 + 308));
                }
                if ( (unsigned int)dword_14007F050 > 5
                  && (qword_14007F060 & 0x400000000000LL) != 0
                  && (qword_14007F068 & 0x400000000000LL) == qword_14007F068 )
                {
                  v48 = *(_QWORD **)(v5 + 672);
                  v80 = *(_DWORD *)(v5 + 308);
                  if ( v48 )
                  {
                    v49 = (struct _KSPIN_LOCK_QUEUE *)v48[15];
                    v85 = v48[21];
                    v81 = v48[17];
                  }
                  else
                  {
                    v85 = 0;
                    v49 = 0;
                    v81 = 0;
                  }
                  *(_QWORD *)&v87 = *(_QWORD *)(v5 + 80);
                  *(_QWORD *)&v86.Data1 = *(_QWORD *)(v5 + 48);
                  v89 = *(_QWORD *)(v5 + 32);
                  v88 = v82[0];
                  v82[0] = v5 + 492;
                  v83.LockQueue.Next = v49;
                  LOBYTE(v90) = v40;
                  v92 = 93;
                  v76 = v41;
                  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
                    (_DWORD)v48,
                    (unsigned int)byte_140075D79,
                    v42,
                    v43,
                    (__int64)v82,
                    (__int64)&v88,
                    (__int64)&v76,
                    (__int64)&v92,
                    (__int64)&v90,
                    (__int64)&v89,
                    (__int64)&v86,
                    (__int64)&v87,
                    (__int64)&v83,
                    (__int64)&v81,
                    (__int64)&v85,
                    (__int64)&v80);
                }
                break;
              default:
                break;
            }
          }
        }
        else
        {
          v41 = 0;
          v39 = 0;
          v40 = 0;
        }
        if ( Status < 0 && (unsigned __int8)StRtlTotalDeviceFailure(v41, v39, v40) )
          Status = -1073740669;
        ByteOffset.QuadPart = (LONGLONG)QuadPart;
      }
    }
    if ( Status == -2147483631 && *(_BYTE *)(v5 + 567) )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
      {
        WPP_SF__guid__guid_(
          WPP_GLOBAL_Control->AttachedDevice,
          67,
          (unsigned int)WPP_c4a5d22d2cc233e7d4f9a274e892dd73_Traceguids,
          v5 + 508,
          v5 + 492);
      }
      *(_DWORD *)(v5 + 560) = 1;
      Status = -1058602981;
    }
    v50 = *(_BYTE *)(ByteOffset.QuadPart + 168);
    switch ( v50 )
    {
      case 4:
        if ( *(_DWORD *)(v5 + 744) != 1 )
          _InterlockedExchange((volatile __int32 *)(v5 + 744), 1);
        memset(&LockHandle, 0, sizeof(LockHandle));
        v59 = *(_DWORD *)(v5 + 576);
        if ( Status != -1073741670
          && Status != -2147483626
          && (v59 < 0 || Status < 0)
          && v59 != -1073740669
          && v59 != -1073740534
          && (v59 >= 0 || ((Status + 0x80000000) & 0x80000000) != 0 || Status == -1073740669) )
        {
          KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v5 + 1328), &LockHandle);
          v60 = *(_DWORD *)(v5 + 576);
          if ( (v60 < 0 || Status < 0)
            && v60 != -1073740669
            && v60 != -1073740534
            && (v60 >= 0 || ((Status + 0x80000000) & 0x80000000) != 0 || Status == -1073740669) )
          {
            v54 = *(_DWORD *)(v5 + 576);
            *(_DWORD *)(v5 + 576) = Status;
            if ( *(int *)(v5 + 576) < 0 )
            {
              if ( *(_DWORD *)(v5 + 576) == -1073740669 )
                *(_QWORD *)(v5 + 736) = MEMORY[0xFFFFF78000000008];
              else
                *(_QWORD *)(v5 + 728) = MEMORY[0xFFFFF78000000008];
            }
            else
            {
              *(_QWORD *)(v5 + 720) = MEMORY[0xFFFFF78000000008];
            }
            KeReleaseInStackQueuedSpinLock(&LockHandle);
            memset(&v83, 0, sizeof(v83));
            v61 = (char *)WPP_MAIN_CB.DeviceExtension + 1192;
            KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)WPP_MAIN_CB.DeviceExtension + 174, &v83);
            KeClearEvent((PRKEVENT)(v61 + 176));
            if ( (*(_DWORD *)v61 & 4) != 0 && KeCancelTimer((PKTIMER)(v61 + 32)) )
              *(_DWORD *)v61 &= ~4u;
            *(_DWORD *)v61 |= 2u;
            if ( (*(_DWORD *)v61 & 1) == 0 )
            {
              _InterlockedIncrement((volatile signed __int32 *)v61 + 1);
              v62 = (struct _IO_WORKITEM *)*((_QWORD *)v61 + 1);
              *(_DWORD *)v61 |= 1u;
              IoQueueWorkItem(v62, SpWorkItemWorkerRoutine, CriticalWorkQueue, v61);
            }
            goto LABEL_210;
          }
          goto LABEL_211;
        }
        break;
      case 3:
        if ( (_BYTE)v91 )
          _InterlockedAdd64((volatile signed __int64 *)(v5 + 1352), -*(_DWORD *)(ByteOffset.QuadPart + 144));
        memset(&LockHandle, 0, sizeof(LockHandle));
        v56 = *(_DWORD *)(v5 + 572);
        if ( Status != -1073741670
          && Status != -2147483626
          && (v56 < 0 || Status < 0)
          && v56 != -1073740669
          && v56 != -1073740534
          && (v56 >= 0 || ((Status + 0x80000000) & 0x80000000) != 0 || Status == -1073740669) )
        {
          KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v5 + 1328), &LockHandle);
          v57 = *(_DWORD *)(v5 + 572);
          if ( (v57 < 0 || Status < 0)
            && v57 != -1073740669
            && v57 != -1073740534
            && (v57 >= 0 || ((Status + 0x80000000) & 0x80000000) != 0 || Status == -1073740669) )
          {
            v58 = *(_DWORD *)(v5 + 572);
            *(_DWORD *)(v5 + 572) = Status;
            KeReleaseInStackQueuedSpinLock(&LockHandle);
            SP_DRIVE::LogStatusRead((SP_DRIVE *)v5, v58, Status);
            break;
          }
LABEL_211:
          KeReleaseInStackQueuedSpinLock(&LockHandle);
        }
        break;
      case 9:
        v51 = (SIO_DIRTY_STATE *)(v5 + 744);
        if ( Status < 0 )
          SIO_DIRTY_STATE::MarkDirty(v51);
        else
          _InterlockedCompareExchange((volatile signed __int32 *)v51, 0, 2);
        memset(&LockHandle, 0, sizeof(LockHandle));
        v52 = *(_DWORD *)(v5 + 576);
        if ( Status != -1073741670
          && Status != -2147483626
          && (v52 < 0 || Status < 0)
          && v52 != -1073740669
          && v52 != -1073740534
          && (v52 >= 0 || ((Status + 0x80000000) & 0x80000000) != 0 || Status == -1073740669) )
        {
          KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v5 + 1328), &LockHandle);
          v53 = *(_DWORD *)(v5 + 576);
          if ( (v53 < 0 || Status < 0)
            && v53 != -1073740669
            && v53 != -1073740534
            && (v53 >= 0 || ((Status + 0x80000000) & 0x80000000) != 0 || Status == -1073740669) )
          {
            v54 = *(_DWORD *)(v5 + 576);
            *(_DWORD *)(v5 + 576) = Status;
            if ( *(int *)(v5 + 576) < 0 )
            {
              if ( *(_DWORD *)(v5 + 576) == -1073740669 )
                *(_QWORD *)(v5 + 736) = MEMORY[0xFFFFF78000000008];
              else
                *(_QWORD *)(v5 + 728) = MEMORY[0xFFFFF78000000008];
            }
            else
            {
              *(_QWORD *)(v5 + 720) = MEMORY[0xFFFFF78000000008];
            }
            KeReleaseInStackQueuedSpinLock(&LockHandle);
            DeviceExtension = (char *)WPP_MAIN_CB.DeviceExtension;
            memset(&v83, 0, sizeof(v83));
            KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)WPP_MAIN_CB.DeviceExtension + 174, &v83);
            SP_WORKITEM::Schedule(DeviceExtension + 1192, 0);
LABEL_210:
            KeReleaseInStackQueuedSpinLock(&v83);
            SP_DRIVE::LogStatusWrite((SP_DRIVE *)v5, v54, Status);
            v63 = *(_QWORD *)(v5 + 608);
            v64 = *(_OWORD *)(v5 + 492);
            v83.LockQueue = *(KSPIN_LOCK_QUEUE *)(v5 + 508);
            v86 = GUID_SPACEPORT_DRIVE_NOTIFICATION;
            v87 = v64;
            SpNotify(&v86, &v87, &v83, 7, 4, v63, v5);
            break;
          }
          goto LABEL_211;
        }
        break;
    }
    *(_DWORD *)(ByteOffset.QuadPart + 180) = Status;
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(ByteOffset.QuadPart + 72), 0xFFFFFFFF) != 1 )
      return (unsigned int)-1073741802;
    v65 = *(_DWORD *)(ByteOffset.QuadPart + 180);
    CurrentProcessorNumber = KeGetCurrentProcessorNumberEx(0);
    if ( CurrentProcessorNumber < *(_DWORD *)(v5 + 1240) )
    {
      v67 = (_DWORD *)(*(_QWORD *)(v5 + 1264) + *(_DWORD *)(v5 + 1248) * CurrentProcessorNumber);
      if ( v67 )
      {
        ++*v67;
        if ( v65 < 0 )
        {
          switch ( v65 )
          {
            case -1073740669:
              ++v67[2];
              break;
            case -1073741668:
              ++v67[3];
              break;
            case -2147483631:
            case -1058602981:
              ++v67[4];
              break;
            default:
              ++v67[1];
              break;
          }
        }
      }
    }
    v68 = 0;
    v69 = *(IRP **)(ByteOffset.QuadPart + 80);
    v91 = *(_QWORD *)(v5 + 1200);
    if ( v69 != *(IRP **)(*(_QWORD *)(ByteOffset.QuadPart + 8) + 80LL) )
      v68 = v69;
    if ( *((_BYTE *)WPP_MAIN_CB.DeviceExtension + 439) )
      goto LABEL_229;
    v70 = *((_DWORD *)WPP_MAIN_CB.DeviceExtension + 112);
    if ( v70 )
    {
      if ( KeExpandKernelStackAndCalloutEx(SP_DRIVE::OnCompletionCallout, (PVOID)ByteOffset.QuadPart, v70, 0, 0) < 0 )
      {
LABEL_229:
        memset(&LockHandle, 0, sizeof(LockHandle));
        v71 = (_DWORD *)(v5 + 960);
        v72 = (_QWORD *)(ByteOffset.QuadPart + 200);
        KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v5 + 1160), &LockHandle);
        if ( ByteOffset.QuadPart != -200 )
        {
          v73 = *(_QWORD **)(v5 + 1128);
          if ( *v73 != v5 + 1120 )
            __fastfail(3u);
          *v72 = v5 + 1120;
          *(_QWORD *)(ByteOffset.QuadPart + 208) = v73;
          *v73 = v72;
          *(_QWORD *)(v5 + 1128) = v72;
        }
        KeClearEvent((PRKEVENT)(v5 + 1136));
        if ( (*v71 & 4) != 0 && KeCancelTimer((PKTIMER)(v5 + 992)) )
          *v71 &= ~4u;
        *v71 |= 2u;
        if ( (*v71 & 1) == 0 )
        {
          _InterlockedIncrement((volatile signed __int32 *)(v5 + 964));
          v74 = *(struct _IO_WORKITEM **)(v5 + 968);
          *v71 |= 1u;
          IoQueueWorkItem(v74, SpWorkItemWorkerRoutine, CriticalWorkQueue, (PVOID)(v5 + 960));
        }
        KeReleaseInStackQueuedSpinLock(&LockHandle);
      }
    }
    else
    {
      SC_PACKET::OnCompletion((SC_PACKET *)ByteOffset.QuadPart);
    }
    if ( v69 == (IRP *)v91 )
    {
      SP_DRIVE::IoSequential((SP_DRIVE *)v5, 0);
    }
    else if ( v68 )
    {
      IoFreeIrp(v68);
    }
    return (unsigned int)-1073741802;
  }
  v7 = 0;
  v90 = 0;
  v8 = IoGetGenericIrpExtension(a2, &v90, 4);
  v9 = a2->IoStatus.Status;
  if ( v8 >= 0 )
  {
    if ( (v90 & 0x400) != 0 )
    {
      LODWORD(v91) = 0;
      if ( (int)IoGetGenericIrpExtension(a2, &v91, 4) >= 0
        && (v91 & 0x400) != 0
        && v9 < 0
        && (unsigned __int8)StRtlTotalNvmeDeviceFailure(WORD1(v91)) )
      {
        v9 = -1073740669;
      }
    }
    else
    {
      v90 = 0;
      if ( (int)IoGetGenericIrpExtension(a2, &v90, 4) >= 0 )
      {
        if ( (v90 & 0x400) == 0 )
        {
          v78 = v9;
          if ( (v90 & 0x800) != 0 )
          {
            v11 = BYTE2(v90);
            v12 = HIBYTE(v90);
            v13 = BYTE1(v90) >> 4;
          }
          else
          {
            v13 = 0;
            v11 = 0;
            v12 = 0;
          }
          LOBYTE(v90) = v12;
          if ( (unsigned __int8)StRtlImpendingDeviceFailure(v10, v11) )
          {
            v81 = v5 + 508;
            if ( !memcmp((const void *)(v5 + 508), &GUID_NULL, 0x10u) )
            {
              v15 = v5 + 404;
              v81 = v5 + 404;
            }
            else
            {
              v15 = v5 + 508;
            }
            if ( (Microsoft_Windows_StorageSpaces_DriverEnableBits & 4) != 0 )
            {
              v16 = *(_QWORD **)(v5 + 672);
              if ( v16 )
              {
                v17 = v16[21];
                v18 = v16[17];
                v19 = v16[15];
              }
              else
              {
                v17 = 0;
                v18 = 0;
                v19 = 0;
              }
              McTemplateK0juuudzzzzzzd_EtwWriteTransfer(
                v15,
                v17,
                v18,
                v15,
                v13,
                v11,
                v90,
                *(_DWORD *)(v5 + 680),
                *(_QWORD *)(v5 + 32),
                *(_QWORD *)(v5 + 48),
                *(_QWORD *)(v5 + 80),
                v19,
                v18,
                v17,
                *(_DWORD *)(v5 + 308));
            }
            if ( (unsigned int)dword_14007F050 > 5 && (unsigned __int8)tlgKeywordOn(&dword_14007F050, 0x400000000000LL) )
            {
              v22 = *(_QWORD **)(v5 + 672);
              v80 = *(_DWORD *)(v5 + 308);
              v78 = v9;
              if ( v22 )
              {
                v85 = v22[21];
                v82[0] = v22[17];
                v23 = v22[15];
              }
              else
              {
                v85 = 0;
                v23 = 0;
                v82[0] = 0;
              }
              v88 = v23;
              v89 = *(_QWORD *)(v5 + 80);
              *(_QWORD *)&v86.Data1 = *(_QWORD *)(v5 + 48);
              *(_QWORD *)&v87 = *(_QWORD *)(v5 + 32);
              v83.LockQueue.Next = (struct _KSPIN_LOCK_QUEUE *volatile)(v5 + 492);
              v92 = v90;
              v77[0] = v11;
              v76 = v13;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
                (unsigned __int8)v90,
                (unsigned int)byte_140075D79,
                v20,
                v21,
                (__int64)&v83,
                (__int64)&v81,
                (__int64)&v76,
                (__int64)v77,
                (__int64)&v92,
                (__int64)&v87,
                (__int64)&v86,
                (__int64)&v89,
                (__int64)&v88,
                (__int64)v82,
                (__int64)&v85,
                (__int64)&v80);
            }
            v14 = (unsigned __int8)v90;
          }
          if ( v78 < 0 && (unsigned __int8)StRtlTotalDeviceFailure(v13, v11, v14) )
            v9 = -1073740669;
          LOBYTE(v4) = v91;
        }
        CurrentStackLocation = QuadPart;
      }
    }
  }
  if ( CurrentStackLocation->MajorFunction == 3 )
  {
    if ( (_BYTE)v4 )
      _InterlockedAdd64((volatile signed __int64 *)(v5 + 1352), -CurrentStackLocation[1].Parameters.Read.Length);
    memset(&LockHandle, 0, sizeof(LockHandle));
    v30 = *(_DWORD *)(v5 + 572);
    if ( v9 != -1073741670
      && v9 != -2147483626
      && (v30 < 0 || v9 < 0)
      && v30 != -1073740669
      && v30 != -1073740534
      && (v30 >= 0 || ((v9 + 0x80000000) & 0x80000000) != 0 || v9 == -1073740669) )
    {
      KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v5 + 1328), &LockHandle);
      v31 = *(_DWORD *)(v5 + 572);
      if ( (v31 < 0 || v9 < 0)
        && v31 != -1073740669
        && v31 != -1073740534
        && (v31 >= 0 || ((v9 + 0x80000000) & 0x80000000) != 0 || v9 == -1073740669) )
      {
        v32 = *(_DWORD *)(v5 + 572);
        *(_DWORD *)(v5 + 572) = v9;
        KeReleaseInStackQueuedSpinLock(&LockHandle);
        SP_DRIVE::LogStatusRead((SP_DRIVE *)v5, v32, v9);
        goto LABEL_82;
      }
      goto LABEL_81;
    }
  }
  else if ( CurrentStackLocation->MajorFunction == 4 )
  {
    SIO_DIRTY_STATE::MarkDirty((SIO_DIRTY_STATE *)(v5 + 744));
    memset(&LockHandle, 0, sizeof(LockHandle));
    v24 = *(_DWORD *)(v5 + 576);
    if ( v9 != -1073741670
      && v9 != -2147483626
      && (v24 < 0 || v9 < 0)
      && v24 != -1073740669
      && v24 != -1073740534
      && (v24 >= 0 || ((v9 + 0x80000000) & 0x80000000) != 0 || v9 == -1073740669) )
    {
      KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v5 + 1328), &LockHandle);
      v25 = *(_DWORD *)(v5 + 576);
      if ( (v25 < 0 || v9 < 0)
        && v25 != -1073740669
        && v25 != -1073740534
        && (v25 >= 0 || ((v9 + 0x80000000) & 0x80000000) != 0 || v9 == -1073740669) )
      {
        v26 = *(_DWORD *)(v5 + 576);
        *(_DWORD *)(v5 + 576) = v9;
        if ( *(int *)(v5 + 576) < 0 )
        {
          if ( *(_DWORD *)(v5 + 576) == -1073740669 )
            *(_QWORD *)(v5 + 736) = MEMORY[0xFFFFF78000000008];
          else
            *(_QWORD *)(v5 + 728) = MEMORY[0xFFFFF78000000008];
        }
        else
        {
          *(_QWORD *)(v5 + 720) = MEMORY[0xFFFFF78000000008];
        }
        KeReleaseInStackQueuedSpinLock(&LockHandle);
        v27 = (char *)WPP_MAIN_CB.DeviceExtension;
        memset(&v83, 0, sizeof(v83));
        KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)WPP_MAIN_CB.DeviceExtension + 174, &v83);
        SP_WORKITEM::Schedule(v27 + 1192, 0);
        KeReleaseInStackQueuedSpinLock(&v83);
        SP_DRIVE::LogStatusWrite((SP_DRIVE *)v5, v26, v9);
        v28 = *(_QWORD *)(v5 + 608);
        v29 = *(_OWORD *)(v5 + 492);
        v83.LockQueue = *(KSPIN_LOCK_QUEUE *)(v5 + 508);
        v87 = v29;
        v86 = GUID_SPACEPORT_DRIVE_NOTIFICATION;
        SpNotify(&v86, &v87, &v83, 7, 4, v28, v5);
        goto LABEL_82;
      }
LABEL_81:
      KeReleaseInStackQueuedSpinLock(&LockHandle);
    }
  }
LABEL_82:
  v33 = KeGetCurrentProcessorNumberEx(0);
  if ( v33 >= *(_DWORD *)(v5 + 1240) )
    goto LABEL_93;
  v34 = (_DWORD *)(*(_QWORD *)(v5 + 1264) + *(_DWORD *)(v5 + 1248) * v33);
  if ( !v34 )
    goto LABEL_93;
  ++*v34;
  if ( v9 >= 0 )
    goto LABEL_93;
  if ( v9 != -1073740669 )
  {
    if ( v9 == -1073741668 )
    {
      ++v34[3];
      a2->IoStatus.Status = -1073741668;
      return v7;
    }
    if ( v9 != -2147483631 && v9 != -1058602981 )
    {
      ++v34[1];
      a2->IoStatus.Status = v9;
      return v7;
    }
    ++v34[4];
LABEL_93:
    a2->IoStatus.Status = v9;
    return v7;
  }
  ++v34[2];
  a2->IoStatus.Status = -1073740669;
  return v7;
}

```

## disassembly

```asm
0x14001b600  push    rbp
0x14001b602  push    rbx
0x14001b603  push    rdi
0x14001b604  push    r12
0x14001b606  push    r13
0x14001b608  lea     rbp, [rsp-30h]
0x14001b60d  sub     rsp, 130h
0x14001b614  mov     rbx, [rdx+0B8h]
0x14001b61b  mov     r12, r8
0x14001b61e  and     r12b, 1
0x14001b622  mov     [rbp+50h+var_70], rbx
0x14001b626  mov     rdi, r8
0x14001b629  mov     [rbp+50h+arg_10], r12
0x14001b62d  and     rdi, 0FFFFFFFFFFFFFFFEh
0x14001b631  mov     r13, rdx
0x14001b634  cmp     byte ptr [rdx+41h], 0
0x14001b638  jz      short loc_14001B63E
0x14001b63a  or      byte ptr [rbx+3], 1
0x14001b63e  cmp     byte ptr [rbx+1], 53h ; 'S'
0x14001b642  mov     rcx, r13; Irp
0x14001b645  mov     [rsp+150h+arg_0], rsi
0x14001b64d  mov     [rsp+150h+var_28], r14
0x14001b655  mov     [rsp+150h+var_30], r15
0x14001b65d  jnz     loc_14001BC9D
0x14001b663  xor     r15d, r15d
0x14001b666  lea     rdx, [rbp+50h+arg_8]
0x14001b66a  mov     r8d, 4
0x14001b670  mov     [rbp+50h+arg_8], r15d
0x14001b674  call    cs:__imp_IoGetGenericIrpExtension
0x14001b67b  nop     dword ptr [rax+rax+00h]
0x14001b680  mov     esi, [r13+30h]
0x14001b684  mov     r14d, 0C0000483h
0x14001b68a  test    eax, eax
0x14001b68c  js      loc_14001B955
0x14001b692  movzx   eax, byte ptr [rbp+50h+arg_8+1]
0x14001b696  mov     r8d, 4
0x14001b69c  shr     al, 2
0x14001b69f  mov     rcx, r13
0x14001b6a2  and     al, 1
0x14001b6a4  jz      short loc_14001B6E8
0x14001b6a6  lea     rdx, [rbp+50h+arg_10]
0x14001b6aa  mov     dword ptr [rbp+50h+arg_10], r15d
0x14001b6ae  call    cs:__imp_IoGetGenericIrpExtension
0x14001b6b5  nop     dword ptr [rax+rax+00h]
0x14001b6ba  test    eax, eax
0x14001b6bc  js      loc_14001B955
0x14001b6c2  test    byte ptr [rbp+50h+arg_10+1], 4
0x14001b6c6  jz      loc_14001B955
0x14001b6cc  test    esi, esi
0x14001b6ce  jns     loc_14001B955
0x14001b6d4  movzx   ecx, word ptr [rbp+50h+arg_10+2]
0x14001b6d8  call    StRtlTotalNvmeDeviceFailure
0x14001b6dd  test    al, al
0x14001b6df  cmovnz  esi, r14d
0x14001b6e3  jmp     loc_14001B955
0x14001b6e8  lea     rdx, [rbp+50h+arg_8]
0x14001b6ec  mov     [rbp+50h+arg_8], r15d
0x14001b6f0  call    cs:__imp_IoGetGenericIrpExtension
0x14001b6f7  nop     dword ptr [rax+rax+00h]
0x14001b6fc  test    eax, eax
0x14001b6fe  js      loc_14001B955
0x14001b704  movzx   ebx, byte ptr [rbp+50h+arg_8+1]
0x14001b708  test    bl, 4
0x14001b70b  jnz     loc_14001B951
0x14001b711  mov     [rbp+50h+var_CC], esi
0x14001b714  test    bl, 8
0x14001b717  jz      short loc_14001B728
0x14001b719  movzx   r12d, byte ptr [rbp+50h+arg_8+2]
0x14001b71e  movzx   r8d, byte ptr [rbp+50h+arg_8+3]
0x14001b723  shr     bl, 4
0x14001b726  jmp     short loc_14001B730
0x14001b728  xor     bl, bl
0x14001b72a  xor     r12b, r12b
0x14001b72d  xor     r8b, r8b
0x14001b730  movzx   edx, r12b
0x14001b734  mov     byte ptr [rbp+50h+arg_8], r8b
0x14001b738  call    StRtlImpendingDeviceFailure
0x14001b73d  test    al, al
0x14001b73f  jz      loc_14001B935
0x14001b745  lea     rax, [rdi+1FCh]
0x14001b74c  mov     r8d, 10h; Size
0x14001b752  mov     rcx, rax; Buf1
0x14001b755  mov     [rbp+50h+var_A8], rax
0x14001b759  lea     rdx, GUID_NULL; Buf2
0x14001b760  call    memcmp
0x14001b765  test    eax, eax
0x14001b767  jz      short loc_14001B772
0x14001b769  lea     rcx, [rdi+1FCh]
0x14001b770  jmp     short loc_14001B77D
0x14001b772  lea     rcx, [rdi+194h]
0x14001b779  mov     [rbp+50h+var_A8], rcx
0x14001b77d  test    cs:Microsoft_Windows_StorageSpaces_DriverEnableBits, 4
0x14001b784  jz      loc_14001B80C
0x14001b78a  mov     rax, [rdi+2A0h]
0x14001b791  mov     r10d, [rdi+134h]
0x14001b798  test    rax, rax
0x14001b79b  jz      short loc_14001B7B1
0x14001b79d  mov     rdx, [rax+0A8h]
0x14001b7a4  mov     r8, [rax+88h]
0x14001b7ab  mov     r9, [rax+78h]
0x14001b7af  jmp     short loc_14001B7BA
0x14001b7b1  mov     rdx, r15
0x14001b7b4  mov     r8, r15
0x14001b7b7  mov     r9, r15
0x14001b7ba  mov     rax, [rdi+50h]
0x14001b7be  mov     dword ptr [rsp+150h+var_E0], r10d
0x14001b7c3  mov     [rsp+150h+var_E8], rdx
0x14001b7c8  mov     [rsp+150h+var_F0], r8
0x14001b7cd  mov     [rsp+150h+var_F8], r9
0x14001b7d2  mov     r9, rcx
0x14001b7d5  mov     [rsp+150h+var_100], rax
0x14001b7da  mov     rax, [rdi+30h]
0x14001b7de  mov     [rsp+150h+var_108], rax
0x14001b7e3  mov     rax, [rdi+20h]
0x14001b7e7  mov     [rsp+150h+var_110], rax
0x14001b7ec  mov     eax, [rdi+2A8h]
0x14001b7f2  mov     dword ptr [rsp+150h+var_118], eax
0x14001b7f6  movzx   eax, byte ptr [rbp+50h+arg_8]
0x14001b7fa  mov     byte ptr [rsp+150h+var_120], al
0x14001b7fe  mov     byte ptr [rsp+150h+var_128], r12b
0x14001b803  mov     byte ptr [rsp+150h+Context], bl
0x14001b807  call    McTemplateK0juuudzzzzzzd_EtwWriteTransfer
0x14001b80c  mov     eax, cs:dword_14007F050
0x14001b812  cmp     eax, 5
0x14001b815  jbe     loc_14001B930
0x14001b81b  mov     rdx, 400000000000h
0x14001b825  lea     rcx, dword_14007F050
0x14001b82c  call    _tlgKeywordOn
0x14001b831  test    al, al
0x14001b833  jz      loc_14001B930
0x14001b839  mov     rdx, [rdi+2A0h]
0x14001b840  movzx   ecx, byte ptr [rbp+50h+arg_8]
0x14001b844  mov     eax, [rdi+134h]
0x14001b84a  mov     [rbp+50h+var_B0], eax
0x14001b84d  mov     [rbp+50h+var_CC], esi
0x14001b850  mov     byte ptr [rbp+50h+arg_8], cl
0x14001b853  test    rdx, rdx
0x14001b856  jz      short loc_14001B874
0x14001b858  mov     rax, [rdx+0A8h]
0x14001b85f  mov     [rbp+50h+var_68], rax
0x14001b863  mov     rax, [rdx+88h]
0x14001b86a  mov     [rbp+50h+var_A0], rax
0x14001b86e  mov     rax, [rdx+78h]
0x14001b872  jmp     short loc_14001B87F
0x14001b874  mov     [rbp+50h+var_68], r15
0x14001b878  mov     rax, r15
0x14001b87b  mov     [rbp+50h+var_A0], r15
0x14001b87f  mov     [rbp+50h+var_40], rax
0x14001b883  lea     rdx, byte_140075D79
0x14001b88a  mov     rax, [rdi+50h]
0x14001b88e  mov     [rbp+50h+var_38], rax
0x14001b892  mov     rax, [rdi+30h]
0x14001b896  mov     qword ptr [rbp+50h+var_60], rax
0x14001b89a  mov     rax, [rdi+20h]
0x14001b89e  mov     qword ptr [rbp+50h+var_50], rax
0x14001b8a2  mov     rax, [rbp+50h+var_A8]
0x14001b8a6  mov     [rbp+50h+var_A8], rax
0x14001b8aa  lea     rax, [rdi+1ECh]
0x14001b8b1  mov     [rbp+50h+var_90.LockQueue.Next], rax
0x14001b8b5  lea     rax, [rbp+50h+var_B0]
0x14001b8b9  mov     [rsp+150h+var_D8], rax
0x14001b8be  lea     rax, [rbp+50h+var_68]
0x14001b8c2  mov     [rsp+150h+var_E0], rax
0x14001b8c7  lea     rax, [rbp+50h+var_A0]
0x14001b8cb  mov     [rsp+150h+var_E8], rax
0x14001b8d0  lea     rax, [rbp+50h+var_40]
0x14001b8d4  mov     [rsp+150h+var_F0], rax
0x14001b8d9  lea     rax, [rbp+50h+var_38]
0x14001b8dd  mov     [rsp+150h+var_F8], rax
0x14001b8e2  lea     rax, [rbp+50h+var_60]
0x14001b8e6  mov     [rsp+150h+var_100], rax
0x14001b8eb  lea     rax, [rbp+50h+var_50]
0x14001b8ef  mov     [rsp+150h+var_108], rax
0x14001b8f4  lea     rax, [rbp+50h+arg_18]
0x14001b8f8  mov     [rsp+150h+var_110], rax
0x14001b8fd  lea     rax, [rbp+50h+var_CF]
0x14001b901  mov     [rsp+150h+var_118], rax
0x14001b906  lea     rax, [rbp+50h+var_D0]
0x14001b90a  mov     [rsp+150h+var_120], rax
0x14001b90f  lea     rax, [rbp+50h+var_A8]
0x14001b913  mov     [rsp+150h+var_128], rax
0x14001b918  lea     rax, [rbp+50h+var_90]
0x14001b91c  mov     [rsp+150h+Context], rax
0x14001b921  mov     [rbp+50h+arg_18], cl
0x14001b924  mov     [rbp+50h+var_CF], r12b
0x14001b928  mov     [rbp+50h+var_D0], bl
0x14001b92b  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$00@@U2@U2@U?$_tlgWrapSz@G@@U3@U3@U3@U3@U3@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$00@@44AEBU?$_tlgWrapSz@G@@55555AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x14001b930  movzx   r8d, byte ptr [rbp+50h+arg_8]
0x14001b935  cmp     [rbp+50h+var_CC], r15d
0x14001b939  jge     short loc_14001B94D
0x14001b93b  movzx   edx, r12b
0x14001b93f  movzx   ecx, bl
0x14001b942  call    StRtlTotalDeviceFailure
0x14001b947  test    al, al
0x14001b949  cmovnz  esi, r14d
0x14001b94d  mov     r12, [rbp+50h+arg_10]
0x14001b951  mov     rbx, [rbp+50h+var_70]
0x14001b955  movzx   ecx, byte ptr [rbx]
0x14001b958  sub     ecx, 3
0x14001b95b  jz      loc_14001BB33
0x14001b961  cmp     ecx, 1
0x14001b964  jnz     loc_14001BC22
0x14001b96a  lea     rcx, [rdi+2E8h]; this
0x14001b971  call    ?MarkDirty@SIO_DIRTY_STATE@@QEAAXXZ; SIO_DIRTY_STATE::MarkDirty(void)
0x14001b976  mov     [rbp+50h+LockHandle.LockQueue.Next], r15
0x14001b97a  xorps   xmm0, xmm0
0x14001b97d  mov     eax, [rdi+240h]
0x14001b983  movups  xmmword ptr [rbp+50h+LockHandle.LockQueue.Lock], xmm0
0x14001b987  cmp     esi, 0C000009Ah
0x14001b98d  jz      loc_14001BC22
0x14001b993  cmp     esi, 80000016h
0x14001b999  jz      loc_14001BC22
0x14001b99f  test    eax, eax
0x14001b9a1  js      short loc_14001B9AB
0x14001b9a3  test    esi, esi
0x14001b9a5  jns     loc_14001BC22
0x14001b9ab  cmp     eax, r14d
0x14001b9ae  jz      loc_14001BC22
0x14001b9b4  cmp     eax, 0C000050Ah
0x14001b9b9  jz      loc_14001BC22
0x14001b9bf  mov     ebx, 80000000h
0x14001b9c4  test    eax, eax
0x14001b9c6  jns     short loc_14001B9D8
0x14001b9c8  lea     eax, [rsi+rbx]
0x14001b9cb  test    ebx, eax
0x14001b9cd  jnz     short loc_14001B9D8
0x14001b9cf  cmp     esi, r14d
0x14001b9d2  jnz     loc_14001BC22
0x14001b9d8  lea     rcx, [rdi+530h]; SpinLock
0x14001b9df  lea     rdx, [rbp+50h+LockHandle]; LockHandle
0x14001b9e3  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14001b9ea  nop     dword ptr [rax+rax+00h]
0x14001b9ef  mov     eax, [rdi+240h]
0x14001b9f5  test    eax, eax
0x14001b9f7  js      short loc_14001BA01
0x14001b9f9  test    esi, esi
0x14001b9fb  jns     loc_14001BC12
0x14001ba01  cmp     eax, r14d
0x14001ba04  jz      loc_14001BC12
0x14001ba0a  cmp     eax, 0C000050Ah
0x14001ba0f  jz      loc_14001BC12
0x14001ba15  test    eax, eax
0x14001ba17  jns     short loc_14001BA29
0x14001ba19  lea     eax, [rsi+rbx]
0x14001ba1c  test    ebx, eax
0x14001ba1e  jnz     short loc_14001BA29
0x14001ba20  cmp     esi, r14d
0x14001ba23  jnz     loc_14001BC12
0x14001ba29  mov     r12d, [rdi+240h]
0x14001ba30  mov     [rdi+240h], esi
0x14001ba36  mov     eax, [rdi+240h]
0x14001ba3c  test    eax, eax
0x14001ba3e  js      short loc_14001BA53
0x14001ba40  mov     rax, ds:0FFFFF78000000008h
0x14001ba4a  mov     [rdi+2D0h], rax
0x14001ba51  jmp     short loc_14001BA78
0x14001ba53  mov     eax, [rdi+240h]
0x14001ba59  cmp     eax, r14d
0x14001ba5c  mov     rax, ds:0FFFFF78000000008h
0x14001ba66  jnz     short loc_14001BA71
0x14001ba68  mov     [rdi+2E0h], rax
0x14001ba6f  jmp     short loc_14001BA78
0x14001ba71  mov     [rdi+2D8h], rax
0x14001ba78  lea     rcx, [rbp+50h+LockHandle]; LockHandle
0x14001ba7c  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14001ba83  nop     dword ptr [rax+rax+00h]
0x14001ba88  mov     rbx, cs:WPP_MAIN_CB.DeviceExtension
0x14001ba8f  lea     rdx, [rbp+50h+var_90]; LockHandle
0x14001ba93  xorps   xmm0, xmm0
0x14001ba96  mov     [rbp+50h+var_90.LockQueue.Next], r15
0x14001ba9a  movups  xmmword ptr [rbp+50h+var_90.LockQueue.Lock], xmm0
0x14001ba9e  lea     rcx, [rbx+570h]; SpinLock
0x14001baa5  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14001baac  nop     dword ptr [rax+rax+00h]
0x14001bab1  xor     edx, edx; unsigned int
0x14001bab3  lea     rcx, [rbx+4A8h]; Context
0x14001baba  call    ?Schedule@SP_WORKITEM@@QEAAXK@Z; SP_WORKITEM::Schedule(ulong)
0x14001babf  lea     rcx, [rbp+50h+var_90]; LockHandle
0x14001bac3  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14001baca  nop     dword ptr [rax+rax+00h]
0x14001bacf  mov     r8d, esi; int
0x14001bad2  mov     edx, r12d; int
0x14001bad5  mov     rcx, rdi; this
0x14001bad8  call    ?LogStatusWrite@SP_DRIVE@@QEAAXJJ@Z; SP_DRIVE::LogStatusWrite(long,long)
0x14001badd  movups  xmm0, xmmword ptr [rdi+1FCh]
0x14001bae4  mov     rax, [rdi+260h]
0x14001baeb  mov     r9d, 7
0x14001baf1  movups  xmm1, xmmword ptr [rdi+1ECh]
0x14001baf8  lea     r8, [rbp+50h+var_90]
0x14001bafc  mov     [rsp+150h+var_120], rdi
0x14001bb01  movaps  xmmword ptr [rbp+50h+var_90.LockQueue.Next], xmm0
0x14001bb05  lea     rdx, [rbp+50h+var_50]
0x14001bb09  movups  xmm0, xmmword ptr cs:GUID_SPACEPORT_DRIVE_NOTIFICATION.Data1
0x14001bb10  mov     [rsp+150h+var_128], rax
0x14001bb15  lea     rcx, [rbp+50h+var_60]
0x14001bb19  movaps  [rbp+50h+var_50], xmm1
0x14001bb1d  movaps  [rbp+50h+var_60], xmm0
0x14001bb21  mov     dword ptr [rsp+150h+Context], 4
0x14001bb29  call    ?SpNotify@@YAXU_GUID@@00W4_SP_NOTIFICATION_TYPE@@KPEAVSP_POOL@@PEAX@Z; SpNotify(_GUID,_GUID,_GUID,_SP_NOTIFICATION_TYPE,ulong,SP_POOL *,void *)
0x14001bb2e  jmp     loc_14001BC22
  ... truncated ...
```
