# UdpSetSockOptEndpoint

- ea: `0x1400d4fb0`
- end: `0x1400d6341`
- name: `UdpSetSockOptEndpoint`
- size: `5009`
- prototype: `__int64 __fastcall(unsigned int *SpinLock, struct _KSPIN_LOCK_QUEUE *, KSPIN_LOCK *, int, unsigned int, struct _KSPIN_LOCK_QUEUE *Source2, KSPIN_LOCK *, _QWORD *, unsigned __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `23`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1400d4a50`

## callees

- `0x1400029e0`
- `0x140003490`
- `0x140003be8`
- `0x140012f00`
- `0x1400474d0`
- `0x1400599a4`
- `0x14007b5e4`
- `0x1400b1c00`
- `0x1400d4fb0`
- `0x1400d9aa0`
- `0x1400e8424`
- `0x1400ff2b0`
- `0x14011cbf4`
- `0x14011faf0`
- `0x14012296c`
- `0x14012950c`
- `0x140131174`
- `0x140154e94`
- `0x1401696fc`
- `0x1401814d4`
- `0x1401befe0`
- `0x1401c0fd0`
- `0x1401c1200`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x1400d5aff`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400d5aff`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400d508a`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400d58fd`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400d5d04`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400d5d52`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400d5ead`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400d5f0d`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400d508a`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400d58fd`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400d5d04`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400d5d52`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400d5ead`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400d5f0d`
- `ntoskrnl!RtlCompareMemory` at `0x1400d561b`
- `ntoskrnl!RtlCompareMemory` at `0x1400d568e`
- `ntoskrnl!RtlCompareMemory` at `0x1400d561b`
- `ntoskrnl!RtlCompareMemory` at `0x1400d568e`
- `ntoskrnl!PsGetProcessId` at `0x1400d575e`
- `ntoskrnl!PsGetProcessId` at `0x1400d575e`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400d54ad`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400d5528`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400d554f`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400d5582`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400d5860`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400d5966`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400d5a68`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400d5ac9`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400d5b43`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400d5bbb`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400d5d28`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400d5d96`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400d5ddd`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400d5ed5`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400d5f4b`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400d5fa5`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400d5ff9`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400d6035`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400d6158`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400d54ad`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400d5528`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400d554f`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400d5582`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400d5860`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400d5966`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400d5a68`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400d5ac9`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400d5b43`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400d5bbb`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400d5d28`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400d5d96`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400d5ddd`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400d5ed5`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400d5f4b`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400d5fa5`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400d5ff9`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400d6035`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400d6158`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d5a39`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d5f92`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d5a39`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d5f92`
- `ntoskrnl!ExAllocatePool2` at `0x1400d53a7`
- `ntoskrnl!ExAllocatePool2` at `0x1400d5a89`
- `ntoskrnl!ExAllocatePool2` at `0x1400d5d7d`
- `ntoskrnl!ExAllocatePool2` at `0x1400d5fde`
- `ntoskrnl!ExAllocatePool2` at `0x1400d617c`
- `ntoskrnl!ExAllocatePool2` at `0x1400d53a7`
- `ntoskrnl!ExAllocatePool2` at `0x1400d5a89`
- `ntoskrnl!ExAllocatePool2` at `0x1400d5d7d`
- `ntoskrnl!ExAllocatePool2` at `0x1400d5fde`
- `ntoskrnl!ExAllocatePool2` at `0x1400d617c`
- `NETIO!NetioInsertWorkQueue` at `0x1400d5b2d`
- `NETIO!NetioInsertWorkQueue` at `0x1400d5b2d`
- `NETIO!NetioNcmTlObjectRequest` at `0x1400d56e8`
- `NETIO!NetioNcmTlObjectRequest` at `0x1400d56e8`
- `NETIO!NmrClientDetachProviderComplete` at `0x1400d5d37`
- `NETIO!NmrClientDetachProviderComplete` at `0x1400d5ee4`
- `NETIO!NmrClientDetachProviderComplete` at `0x1400d5d37`
- `NETIO!NmrClientDetachProviderComplete` at `0x1400d5ee4`

## pseudocode

```c
__int64 __fastcall UdpSetSockOptEndpoint(
        unsigned int *SpinLock,
        struct _KSPIN_LOCK_QUEUE *a2,
        KSPIN_LOCK *a3,
        int a4,
        unsigned int a5,
        struct _KSPIN_LOCK_QUEUE *Source2,
        KSPIN_LOCK *a7,
        _QWORD *a8,
        unsigned __int64 a9,
        _QWORD *a10)
{
  int v10; // ebx
  int v13; // ecx
  KSPIN_LOCK v14; // r8
  unsigned int v15; // edx
  unsigned int v16; // edx
  unsigned int v17; // edx
  unsigned int v18; // edx
  unsigned int v19; // edx
  int Next; // ecx
  bool v21; // zf
  __int16 v22; // ax
  KSPIN_LOCK v23; // rax
  __int16 v24; // bx
  __int64 Pool2; // rax
  unsigned int v26; // eax
  int v27; // ecx
  KSPIN_LOCK v28; // rcx
  KSPIN_LOCK v29; // rdi
  __int64 v30; // rax
  unsigned int v31; // edi
  int v32; // esi
  __int16 v33; // bx
  __int64 v34; // r9
  __int64 v35; // rdx
  KSPIN_LOCK v36; // rax
  int v37; // eax
  unsigned __int8 ProcessId; // al
  KSPIN_LOCK v39; // rax
  int v40; // r8d
  unsigned int v41; // edx
  int v42; // r8d
  int v43; // ecx
  bool v44; // si
  KSPIN_LOCK v45; // rcx
  int v46; // eax
  __int64 v47; // r13
  PVOID v48; // r12
  KSPIN_LOCK v49; // r15
  KSPIN_LOCK v50; // rbx
  int v51; // ecx
  unsigned int v52; // ecx
  KSPIN_LOCK v53; // r8
  char v54; // cl
  KSPIN_LOCK v55; // rdx
  _DWORD *v56; // rcx
  _DWORD **v57; // rax
  void **v58; // r8
  __int64 v59; // rdi
  _QWORD *v60; // rcx
  __int64 v61; // rax
  _QWORD *v62; // rbx
  KSPIN_LOCK v63; // r13
  int v64; // ecx
  int v65; // edx
  int v66; // eax
  __int64 v67; // rax
  void *v68; // rdi
  __int64 v69; // rax
  __int64 *v70; // rdx
  __int64 v71; // rbx
  __int64 v72; // rsi
  int v73; // eax
  __int64 v74; // rcx
  void *v75; // rdi
  __int64 *v76; // rcx
  __int64 v77; // rdi
  _QWORD *v78; // rdx
  __int64 v79; // rax
  unsigned int v80; // r8d
  unsigned __int16 v81; // ax
  __int64 v82; // rdx
  int *v83; // rax
  int *v84; // rcx
  struct _KSPIN_LOCK_QUEUE *v85; // rax
  struct _KSPIN_LOCK_QUEUE *v86; // rdx
  __int64 v87; // rcx
  __int64 v88; // r10
  KSPIN_LOCK v89; // r8
  KSPIN_LOCK v90; // r9
  int v91; // r12d
  __int64 v92; // rax
  __int64 (__fastcall *v93)(__int64); // rax
  int v94; // eax
  _DWORD *v95; // r9
  _DWORD *v96; // rcx
  char v98; // [rsp+30h] [rbp-D0h]
  char v99; // [rsp+40h] [rbp-C0h]
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD *v101; // [rsp+68h] [rbp-98h] BYREF
  int v102; // [rsp+70h] [rbp-90h]
  int v103; // [rsp+74h] [rbp-8Ch]
  __int64 v104; // [rsp+78h] [rbp-88h] BYREF
  struct _KLOCK_QUEUE_HANDLE v105; // [rsp+80h] [rbp-80h] BYREF
  struct _KSPIN_LOCK_QUEUE *v106; // [rsp+98h] [rbp-68h]
  KSPIN_LOCK *v107; // [rsp+A0h] [rbp-60h]
  __int64 v108; // [rsp+A8h] [rbp-58h] BYREF
  int *v109; // [rsp+B0h] [rbp-50h]
  _DWORD *v110; // [rsp+B8h] [rbp-48h] BYREF
  _DWORD *v111; // [rsp+C0h] [rbp-40h] BYREF
  _QWORD v112[3]; // [rsp+D0h] [rbp-30h] BYREF
  int v113; // [rsp+E8h] [rbp-18h]
  int v114; // [rsp+ECh] [rbp-14h]
  __int64 v115; // [rsp+F0h] [rbp-10h]
  __int64 v116; // [rsp+F8h] [rbp-8h]
  __int64 v117; // [rsp+100h] [rbp+0h]
  int v118; // [rsp+108h] [rbp+8h]
  unsigned int v119; // [rsp+10Ch] [rbp+Ch]
  struct _KSPIN_LOCK_QUEUE *v120; // [rsp+110h] [rbp+10h]
  int v121; // [rsp+118h] [rbp+18h]
  int v122; // [rsp+11Ch] [rbp+1Ch]
  _QWORD *v123; // [rsp+120h] [rbp+20h]
  unsigned int v124; // [rsp+128h] [rbp+28h]
  int v125; // [rsp+12Ch] [rbp+2Ch]
  struct _KSPIN_LOCK_QUEUE *v126; // [rsp+130h] [rbp+30h]
  __int64 (__fastcall *v127)(PVOID); // [rsp+138h] [rbp+38h]
  __int64 v128; // [rsp+140h] [rbp+40h]
  KSPIN_LOCK v129; // [rsp+148h] [rbp+48h]
  __int128 v130; // [rsp+150h] [rbp+50h]
  __int64 v131; // [rsp+160h] [rbp+60h]
  struct _KLOCK_QUEUE_HANDLE v132; // [rsp+170h] [rbp+70h] BYREF
  unsigned __int128 v133; // [rsp+190h] [rbp+90h] BYREF
  __int128 v134; // [rsp+1A0h] [rbp+A0h]
  _OWORD v135[2]; // [rsp+1B0h] [rbp+B0h] BYREF
  struct _KLOCK_QUEUE_HANDLE v136; // [rsp+1D0h] [rbp+D0h] BYREF

  v10 = 0;
  v101 = a10;
  v103 = a4;
  v107 = a3;
  v106 = a2;
  memset(&LockHandle, 0, sizeof(LockHandle));
  if ( dword_1402241D4 )
  {
    v136.LockQueue = 0;
    if ( (BYTE4(WPP_MAIN_CB.Dpc.DeferredContext) & 8) != 0 )
    {
      v136.LockQueue.Next = (struct _KSPIN_LOCK_QUEUE *volatile)SpinLock;
      v13 = (int)a7;
      if ( !Source2 )
        v13 = 0;
      McTemplateK0pqqqbr3_EtwWriteTransfer(
        (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
        (unsigned int)TCPIP_SETSOCKOPT,
        (unsigned int)&v136,
        (_DWORD)SpinLock,
        a4,
        a5,
        v13,
        (__int64)Source2);
    }
  }
  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)SpinLock, &LockHandle);
  while ( SpinLock[2] )
    ;
  if ( a4 == 17 )
  {
    switch ( a5 )
    {
      case 1u:
        if ( a7 )
        {
          SpinLock[6] = SpinLock[6] & 0xFFFFFFBF | (LOBYTE(Source2->Next) != 0 ? 0x40 : 0);
LABEL_170:
          KeReleaseInStackQueuedSpinLock(&LockHandle);
          return (unsigned int)v10;
        }
        goto LABEL_169;
      case 2u:
        if ( (unsigned __int64)a7 >= 4 )
        {
          SpinLock[92] = (unsigned int)Source2->Next;
          UdpCacheDefaultUsoInformation(SpinLock);
          goto LABEL_170;
        }
LABEL_169:
        v10 = -1073741306;
        goto LABEL_170;
      case 3u:
        if ( (unsigned __int64)a7 >= 4 )
        {
          SpinLock[96] = (unsigned int)Source2->Next;
          goto LABEL_170;
        }
        goto LABEL_169;
    }
LABEL_59:
    v10 = -1073741811;
    goto LABEL_170;
  }
  if ( a4 != 41 )
  {
    if ( a4 != 0xFFFF )
      goto LABEL_53;
    switch ( a5 )
    {
      case 0x20u:
        if ( a7 )
        {
          SpinLock[6] = SpinLock[6] & 0xFFFFFF7F | (LOBYTE(Source2->Next) != 0 ? 0x80 : 0);
          goto LABEL_170;
        }
        goto LABEL_169;
      case 4u:
        if ( !a7 )
          goto LABEL_169;
        v16 = SpinLock[6];
        if ( (v16 & 1) != 0 )
          goto LABEL_72;
        if ( (v16 & 0x6000) == 0 )
        {
          SpinLock[6] = v16 & 0xFFFFFEFF | (LOBYTE(Source2->Next) != 0 ? 0x100 : 0);
          goto LABEL_170;
        }
        break;
      case 0x3008u:
        if ( !a7 )
          goto LABEL_169;
        v17 = SpinLock[6];
        if ( (v17 & 1) != 0 )
          goto LABEL_72;
        if ( (v17 & 0x2300) == 0 )
        {
          SpinLock[6] = v17 & 0xFFFFBFFF | (LOBYTE(Source2->Next) != 0 ? 0x4000 : 0);
          goto LABEL_170;
        }
        break;
      case 0xFFFFFFFB:
        if ( !a7 )
          goto LABEL_169;
        v18 = SpinLock[6];
        if ( (v18 & 1) != 0 )
          goto LABEL_72;
        if ( (v18 & 0x4000) == 0 )
        {
          SpinLock[6] = v18 & 0xFFFFFDFF | (LOBYTE(Source2->Next) != 0 ? 0x200 : 0);
          goto LABEL_170;
        }
        break;
      case 0x3005u:
        if ( !a7 )
          goto LABEL_169;
        v19 = SpinLock[6];
        if ( (v19 & 1) == 0 )
        {
          SpinLock[6] = v19 & 0xFFFFFBFF | (LOBYTE(Source2->Next) != 0 ? 0x400 : 0);
          goto LABEL_170;
        }
        goto LABEL_72;
      case 0x3004u:
        goto LABEL_170;
      case 0x10u:
        if ( a7 )
        {
          SpinLock[6] = SpinLock[6] & 0xFFFFEFFF | (LOBYTE(Source2->Next) != 0 ? 0x1000 : 0);
          goto LABEL_170;
        }
        goto LABEL_169;
      case 0x3011u:
        if ( a7 )
        {
          SpinLock[6] = (LOBYTE(Source2->Next) != 0 ? 0x80000 : 0) | SpinLock[6] & 0xFFF7FFFF;
          goto LABEL_170;
        }
        goto LABEL_169;
      default:
        goto LABEL_53;
    }
LABEL_160:
    v10 = -1073741637;
    goto LABEL_170;
  }
  if ( a5 == 27 )
  {
    if ( !a7 )
      goto LABEL_169;
    v15 = SpinLock[6];
    if ( (v15 & 1) == 0 )
    {
      SpinLock[6] = v15 & 0xFFFFFFEF | (LOBYTE(Source2->Next) != 0 ? 0x10 : 0);
      goto LABEL_170;
    }
LABEL_72:
    v10 = -1073741256;
    goto LABEL_170;
  }
LABEL_53:
  if ( a4 != 65532 )
    goto LABEL_244;
  switch ( a5 )
  {
    case 0x980000EB:
      if ( (unsigned __int64)a7 < 8 )
        goto LABEL_169;
      Next = (int)Source2->Next;
      v21 = ((__int64)Source2->Next & 0xFFFFFFFC) == 0;
      LODWORD(Source2->Next) &= 0xFFFFFFFC;
      if ( !v21 )
        goto LABEL_59;
      if ( (Next & 2) == 0 )
        goto LABEL_62;
      v22 = WORD2(Source2->Next);
      if ( !v22 )
        goto LABEL_59;
      v14 = *((_QWORD *)SpinLock + 45);
      if ( !v14 || v22 == *(_WORD *)(v14 + 18) )
      {
LABEL_62:
        v23 = *((_QWORD *)SpinLock + 45);
        SpinLock[6] ^= (SpinLock[6] ^ (Next << 18)) & 0x40000;
        if ( (Next & 2) != 0 )
        {
          if ( !v23 )
          {
            v24 = WORD2(Source2->Next);
            Pool2 = ExAllocatePool2(64, 24, 1416651861);
            if ( Pool2 )
            {
              *(_QWORD *)(Pool2 + 8) = Pool2;
              *(_QWORD *)Pool2 = Pool2;
              *(_WORD *)(Pool2 + 18) = v24;
              v10 = 0;
              *(_WORD *)(Pool2 + 16) = 0;
              *((_QWORD *)SpinLock + 45) = Pool2;
            }
            else
            {
              v10 = -1073741670;
            }
          }
        }
        else if ( v23 )
        {
          UdpUninitTimestampQueue(SpinLock + 90, Next & 2, v14, 0xFFFF);
        }
        goto LABEL_170;
      }
      goto LABEL_160;
    case 0x98000015:
      if ( (unsigned __int64)a7 < 2 )
        goto LABEL_169;
      v26 = SpinLock[6];
      if ( (v26 & 1) != 0 )
        goto LABEL_72;
      if ( (v26 & 0x4100) == 0 )
      {
        SpinLock[6] = v26 | 0x2000;
        *((_WORD *)SpinLock + 85) = Source2->Next;
        goto LABEL_170;
      }
      goto LABEL_160;
    case 0x8800000B:
    case 0x8800001A:
      if ( !*((_QWORD *)SpinLock + 9) )
      {
        v10 = -1073741808;
        goto LABEL_170;
      }
      if ( _InterlockedIncrement64((volatile signed __int64 *)SpinLock + 2) <= 1 )
        __fastfail(0xEu);
      KeReleaseInStackQueuedSpinLock(&LockHandle);
      v63 = *((_QWORD *)SpinLock + 9);
      if ( a5 == -2013265909 )
      {
        v64 = *(_DWORD *)(v63 + 648);
        v65 = 0;
        memset(&v105, 0, sizeof(v105));
        if ( (v64 & 1) != 0 )
        {
          if ( (v64 & 0x200) != 0 )
          {
            v65 = 1;
          }
          else if ( (v64 & 0x400) != 0 )
          {
            v65 = 2;
          }
        }
        else if ( (v64 & 2) != 0 )
        {
          if ( (v64 & 0x200) != 0 )
          {
            v65 = 3;
          }
          else if ( (v64 & 0x400) != 0 )
          {
            v65 = 4;
          }
        }
        v133 = 0;
        v134 = 0;
        v101 = 0;
        memset(v135, 0, 24);
        while ( 1 )
        {
          v66 = dword_14022AFA0;
          if ( (dword_14022AFA0 & 1) != 0 )
            break;
          if ( v66 == _InterlockedCompareExchange(&dword_14022AFA0, dword_14022AFA0 + 2, dword_14022AFA0) )
          {
            v67 = *(_QWORD *)(qword_14022AF98 + 8);
            *((_QWORD *)&v134 + 1) = &v101;
            *(_QWORD *)&v134 = 0;
            memset((char *)v135 + 4, 0, 20);
            v133 = __PAIR128__((unsigned __int64)a7, (unsigned __int64)Source2);
            LODWORD(v135[0]) = v65;
            v10 = (*(__int64 (__fastcall **)(unsigned __int128 *))(v67 + 8))(&v133);
            if ( _InterlockedExchangeAdd(&dword_14022AFA0, 0xFFFFFFFE) == 3 )
            {
              memset(&v136, 0, sizeof(v136));
              v68 = *(void **)(qword_14022AF98 + 24);
              *(_QWORD *)(qword_14022AF98 + 24) = 0;
              KeAcquireInStackQueuedSpinLock(&qword_14022AFA8, &v136);
              while ( dword_14022AFB0 )
                ;
              qword_14022AF98 = 0;
              KeReleaseInStackQueuedSpinLock(&v136);
              NmrClientDetachProviderComplete(v68);
            }
            if ( v10 < 0 )
              goto LABEL_243;
            KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v63 + 632), &v105);
            while ( *(_DWORD *)(v63 + 640) )
              ;
            if ( !*(_QWORD *)(v63 + 656) )
            {
              v69 = ExAllocatePool2(64, 24, 1699959109);
              *(_QWORD *)(v63 + 656) = v69;
              if ( !v69 )
              {
                KeReleaseInStackQueuedSpinLock(&v105);
                EQoSDeleteQoSFlow(v101);
                v10 = -1073741801;
                UdpDereferenceEndpoint(SpinLock);
                return (unsigned int)v10;
              }
              *(_OWORD *)v69 = 0;
              *(_QWORD *)(v69 + 16) = 0;
            }
            v70 = *(__int64 **)(v63 + 656);
            v71 = *v70;
            *v70 = (__int64)v101;
            KeReleaseInStackQueuedSpinLock(&v105);
            if ( v71 )
              EQoSDereferenceQoSFlow(v71);
            goto LABEL_210;
          }
        }
      }
      else
      {
        memset(&v136, 0, sizeof(v136));
        if ( !a7 )
        {
          v72 = 0;
LABEL_222:
          KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v63 + 632), &v136);
          while ( *(_DWORD *)(v63 + 640) )
            ;
          v76 = *(__int64 **)(v63 + 656);
          v77 = 0;
          if ( v76 )
            v77 = *v76;
          if ( v72 )
          {
            if ( !v76 )
            {
              v79 = ExAllocatePool2(64, 24, 1699959109);
              v76 = (__int64 *)v79;
              if ( !v79 )
              {
                KeReleaseInStackQueuedSpinLock(&v136);
                EQoSDereferenceQoSFlow(v72);
                v10 = -1073741801;
                UdpDereferenceEndpoint(SpinLock);
                return (unsigned int)v10;
              }
              *(_QWORD *)(v79 + 8) = 0;
              *(_QWORD *)(v79 + 16) = 0;
              *(_QWORD *)(v63 + 656) = v79;
            }
            *v76 = v72;
            KeReleaseInStackQueuedSpinLock(&v136);
            if ( v77 )
              EQoSDereferenceQoSFlow(v77);
LABEL_210:
            v10 = 0;
            UdpDereferenceEndpoint(SpinLock);
          }
          else if ( v77 )
          {
            *v76 = 0;
            v78 = *(_QWORD **)(v63 + 656);
            if ( !*v78 && !v78[1] && ((*(_DWORD *)(v63 + 648) & 0x20) != 0 || !v78[2]) )
            {
              *(_QWORD *)(v63 + 656) = 0;
              ExFreePoolWithTag(v76, 0x65535145u);
            }
            KeReleaseInStackQueuedSpinLock(&v136);
            EQoSDereferenceQoSFlow(v77);
            v10 = 0;
            UdpDereferenceEndpoint(SpinLock);
          }
          else
          {
            KeReleaseInStackQueuedSpinLock(&v136);
            v10 = 0;
            UdpDereferenceEndpoint(SpinLock);
          }
          return (unsigned int)v10;
        }
        memset(&v105, 0, sizeof(v105));
        while ( 1 )
        {
          v73 = dword_14022AFA0;
          if ( (dword_14022AFA0 & 1) != 0 )
            break;
          if ( v73 == _InterlockedCompareExchange(&dword_14022AFA0, dword_14022AFA0 + 2, dword_14022AFA0) )
          {
            v74 = *(_QWORD *)(qword_14022AF98 + 8);
            v105.LockQueue.Next = Source2;
            v105.LockQueue.Lock = a7;
            v10 = (*(__int64 (__fastcall **)(struct _KLOCK_QUEUE_HANDLE *))(v74 + 72))(&v105);
            if ( _InterlockedExchangeAdd(&dword_14022AFA0, 0xFFFFFFFE) == 3 )
            {
              memset(&v132, 0, sizeof(v132));
              v75 = *(void **)(qword_14022AF98 + 24);
              *(_QWORD *)(qword_14022AF98 + 24) = 0;
              KeAcquireInStackQueuedSpinLock(&qword_14022AFA8, &v132);
              while ( dword_14022AFB0 )
                ;
              qword_14022AF98 = 0;
              KeReleaseInStackQueuedSpinLock(&v132);
              NmrClientDetachProviderComplete(v75);
            }
            if ( v10 >= 0 )
            {
              v72 = *(_QWORD *)&v105.OldIrql;
              goto LABEL_222;
            }
            goto LABEL_243;
          }
        }
      }
      v10 = -1073741738;
LABEL_243:
      UdpDereferenceEndpoint(SpinLock);
      return (unsigned int)v10;
    case 0x98000022:
      v10 = InetInspectFirewallSystemPort(*((_QWORD *)SpinLock + 9), Source2, a7);
      goto LABEL_170;
  }
  if ( a5 + 1744830264 <= 0x16 && (v27 = 4194317, _bittest(&v27, a5 + 1744830264)) || a5 == -671088439 )
  {
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    return (unsigned int)InetInspectSocketOption(SpinLock, *((_QWORD *)SpinLock + 9), a5, Source2, a7, a8, a9, v101);
  }
  if ( a5 == 1476395213 )
  {
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    v28 = *((_QWORD *)SpinLock + 9);
    if ( v28 && a9 >= 8 && a8 )
    {
      *a8 = WfpAleQueryOrInsertEndpointHandle(v28);
      if ( v101 )
        *v101 = 8;
    }
    else
    {
      return (unsigned int)-1073741823;
    }
    return (unsigned int)v10;
  }
  if ( a5 + 1744830364 <= 2 )
  {
    v61 = ExAllocatePool2(64, 80, 1464165461);
    v62 = (_QWORD *)v61;
    if ( !v61 )
    {
      v10 = -1073741801;
      goto LABEL_170;
    }
    *(_QWORD *)(v61 + 8) = SpinLock;
    if ( _InterlockedIncrement64((volatile signed __int64 *)SpinLock + 2) <= 1 )
      __fastfail(0xEu);
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    v62[2] = v106;
    v62[3] = v107;
    v62[8] = a9;
    *((_DWORD *)v62 + 8) = a5;
    v62[5] = Source2;
    v62[6] = a7;
    v62[7] = a8;
    if ( KeGetCurrentIrql() )
    {
      NetioInsertWorkQueue(UdpPortReservationWorkQueue, v62);
    }
    else
    {
      *v62 = 0;
      UdpPortReservationWorkQueueRoutine(v62);
    }
    return 259;
  }
  if ( a5 == 1207959589 )
  {
    if ( a9 >= 8 )
    {
      v29 = *((_QWORD *)SpinLock + 37);
      if ( v29 )
      {
        v30 = *(_QWORD *)v29;
        v31 = *(_DWORD *)(v29 + 12);
        v32 = *(_DWORD *)(*(_QWORD *)(v30 + 8) + 8LL);
        v33 = *(_WORD *)(*((_QWORD *)SpinLock + 39) + 24LL);
        KeReleaseInStackQueuedSpinLock(&LockHandle);
        v34 = 1024;
        if ( v33 != 23 )
          v34 = 256;
        v35 = 0x8000;
        if ( v33 != 23 )
          v35 = 0x4000;
        v10 = (*((__int64 (__fastcall **)(_QWORD, __int64, _QWORD, __int64, int, _QWORD *))UdpRssHash + 3))(
                SpinLock[71],
                v35,
                v31,
                v34,
                v32,
                a8);
        *v101 = (((__int64)v10 >> 63) & 0xFFFFFFFFFFFFFFF8uLL) + 8;
      }
      else
      {
        KeReleaseInStackQueuedSpinLock(&LockHandle);
        return (unsigned int)-1073741634;
      }
    }
    else
    {
      KeReleaseInStackQueuedSpinLock(&LockHandle);
      return (unsigned int)-1073741306;
    }
    return (unsigned int)v10;
  }
  if ( a5 != -1744830445 )
  {
    switch ( a5 )
    {
      case 0x98000014:
        if ( !Source2 || !a8 || (unsigned __int64)a7 < 0x10 || a9 < 4 )
          goto LABEL_169;
        if ( RtlCompareMemory(&REAL_TIME_NOTIFICATION_CAPABILITY, Source2, 0x10u) != 16 )
          goto LABEL_59;
        v36 = *((_QWORD *)SpinLock + 23);
        if ( v36 )
        {
          v134 = 0;
          memset(v135, 0, sizeof(v135));
          v133 = v36;
          NetioNcmTlObjectRequest(&v133, 2);
          v37 = DWORD2(v135[0]);
          *(_DWORD *)a8 = DWORD2(v135[0]);
          if ( v37 != 1 || (SpinLock[6] & 4) != 0 )
          {
LABEL_117:
            if ( v101 )
              *v101 = 4;
            goto LABEL_120;
          }
        }
        else if ( (SpinLock[6] & 4) != 0 )
        {
          v10 = -1073741637;
LABEL_120:
          if ( dword_1402241D4 )
          {
            v136.LockQueue = 0;
            if ( (BYTE3(WPP_MAIN_CB.Dpc.DeferredRoutine) & 0x10) != 0 )
            {
              ProcessId = (unsigned __int8)PsGetProcessId(*((PEPROCESS *)SpinLock + 6));
              v99 = *(_DWORD *)a8;
              v98 = ProcessId;
              v39 = *((_QWORD *)SpinLock + 23);
              v40 = (SpinLock[6] >> 2) & 1;
              v136.LockQueue.Lock = 0;
              v136.LockQueue.Next = (struct _KSPIN_LOCK_QUEUE *volatile)SpinLock;
              McTemplateK0ppqqqqq_EtwWriteTransfer(
                (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
                (unsigned int)UDP_QUERY_NOTIFICATION_CHANNEL_STATUS_REQUEST,
                (unsigned int)&v136,
                (_DWORD)SpinLock,
                v39,
                v40,
                v98,
                0,
                v99,
                v10,
                LockHandle.LockQueue.Next,
                LockHandle.LockQueue.Lock,
                *(_QWORD *)&LockHandle.OldIrql);
            }
          }
          goto LABEL_170;
        }
        *(_DWORD *)a8 = 5;
        goto LABEL_117;
      case 0x980000E8:
        if ( (unsigned __int64)a7 < 4 )
          goto LABEL_169;
        v41 = SpinLock[6];
        v42 = (int)Source2->Next;
        if ( ((v41 >> 15) & 1) == (LODWORD(Source2->Next) == 1) )
        {
LABEL_126:
          v43 = 0;
          if ( v42 == 1 )
            v43 = 0x8000;
          SpinLock[6] = SpinLock[6] & 0xFFFF7FFF | v43;
          goto LABEL_170;
        }
        if ( v42 == 1 )
        {
          if ( (v41 & 1) == 0 )
            goto LABEL_126;
          if ( !*((_QWORD *)SpinLock + 13) )
          {
            v10 = -1073741255;
            goto LABEL_170;
          }
          if ( (v41 & 2) == 0 )
            goto LABEL_160;
          v44 = 1;
        }
        else
        {
          v44 = (v41 & 0x10000) != 0;
          if ( (v41 & 0x10000) == 0 )
          {
LABEL_146:
            v51 = 0;
            if ( LODWORD(Source2->Next) == 1 )
              v51 = 0x8000;
            v52 = SpinLock[6] & 0xFFFF7FFF | v51;
            SpinLock[6] = v52;
            if ( v44 )
              SpinLock[6] = v52 ^ (v52 ^ (2 * v52)) & 0x10000;
            goto LABEL_170;
          }
        }
        KeReleaseInStackQueuedSpinLock(&LockHandle);
        v45 = *((_QWORD *)SpinLock + 13);
        if ( LODWORD(Source2->Next) == 1 )
        {
          v46 = InetWakeAcquirePort(
                  *((unsigned __int16 *)SpinLock + 84),
                  *((_QWORD *)SpinLock + 5),
                  *((_QWORD *)SpinLock + 14),
                  *(_QWORD *)(v45 + 8),
                  (__int64)UdpWakePortPool);
        }
        else
        {
          v47 = *(_QWORD *)(v45 + 8);
          v48 = UdpWakePortPool;
          v49 = *((_QWORD *)SpinLock + 5);
          v50 = *((_QWORD *)SpinLock + 14);
          LOWORD(v102) = *((_WORD *)SpinLock + 84);
          v46 = InetWakeReleasePortAf((unsigned __int16)v102, v49, v47, UdpWakePortPool);
          if ( v46 >= 0 && v50 != v49 )
            v46 = InetWakeReleasePortAf((unsigned __int16)v102, v50, v47, v48);
        }
        if ( v46 < 0 )
          v46 = -1073741637;
        v10 = v46;
        KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)SpinLock, &LockHandle);
        while ( SpinLock[2] )
          ;
        if ( v10 < 0 )
          goto LABEL_170;
        goto LABEL_146;
      case 0x980000E9:
        KeReleaseInStackQueuedSpinLock(&LockHandle);
        v53 = *((_QWORD *)SpinLock + 5);
        v54 = *(_WORD *)(v53 + 24) == 23 && (SpinLock[6] & 0x10) == 0;
        return (unsigned int)InetHandleSockOptSioWakeIf(
                               (_DWORD)Source2,
                               (_DWORD)a7,
                               v53,
                               *((_QWORD *)SpinLock + 14),
                               *((_QWORD *)SpinLock + 10),
                               v54,
                               (__int64)UdpWakePortPool);
      case 0x980000EA:
        if ( a9 < 8 || (unsigned __int64)a7 < 4 )
          goto LABEL_169;
        v55 = *((_QWORD *)SpinLock + 45);
        if ( v55 )
        {
          v56 = *(_DWORD **)v55;
          if ( *(_QWORD *)v55 == v55 )
          {
LABEL_164:
            v10 = -1073741661;
          }
          else
          {
            while ( 1 )
            {
              v57 = *(_DWORD ***)v56;
              if ( v56[6] == LODWORD(Source2->Next) )
                break;
              v56 = *(_DWORD **)v56;
              if ( v57 == (_DWORD **)v55 )
                goto LABEL_164;
            }
            if ( v57[1] != v56 || (v58 = (void **)*((_QWORD *)v56 + 1), *v58 != v56) )
              __fastfail(3u);
            *v58 = v57;
            v57[1] = v58;
            --*(_WORD *)(v55 + 16);
            v59 = *((_QWORD *)v56 + 2);
            ExFreePoolWithTag(v56, 0);
            v60 = v101;
            *a8 = v59;
            *v60 = 8;
          }
          goto LABEL_170;
        }
        goto LABEL_160;
    }
LABEL_244:
    v80 = SpinLock[6];
    v111 = 0;
    v110 = 0;
    v108 = 0;
    v104 = 0;
    if ( (v80 & 1) != 0 )
    {
      v81 = *((_WORD *)SpinLock + 87);
    }
    else
    {
      v82 = v80 >> 4;
      LOBYTE(v82) = (v80 & 0x10) != 0;
      v81 = InetResolveEffectiveFamilyAf(*((_QWORD *)SpinLock + 5), v82);
    }
    v10 = InetResolveSetSockOptSs(
            (int)SpinLock + 232,
            *((_QWORD *)SpinLock + 5),
            (unsigned int)&UdpInetTransport,
            v81,
            (v80 & 0x20) != 0,
            a4,
            (__int64)&v104,
            (__int64)&v108,
            (__int64)&v111,
            (__int64)&v110);
    if ( v10 >= 0 && (!a4 || a4 == 41) && a5 == 23 )
      v10 = InetInspectSocketPropertyValue(*((_QWORD *)SpinLock + 9), Source2, a7);
    v83 = (int *)*((_QWORD *)SpinLock + 10);
    if ( v83 )
    {
      v102 = *v83;
      v84 = 0;
      if ( v104 == *((_QWORD *)SpinLock + 5) )
        v84 = v83;
      v109 = v84;
    }
    else
    {
      v109 = 0;
      v102 = 1;
    }
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    if ( v10 < 0 )
      return (unsigned int)v10;
    v85 = (struct _KSPIN_LOCK_QUEUE *)ExAllocatePool2(64, 80, 1464165461);
    v136.LockQueue.Next = v85;
    v86 = v85;
    if ( !v85 )
      return (unsigned int)-1073741801;
    v85->Lock = (volatile PKSPIN_LOCK)SpinLock;
    if ( _InterlockedIncrement64((volatile signed __int64 *)SpinLock + 2) <= 1 )
      __fastfail(0xEu);
    v87 = v104;
    v88 = v108;
    v85[1].Next = v106;
    v85[1].Lock = v107;
    v89 = *((_QWORD *)SpinLock + 13);
    v90 = *((_QWORD *)SpinLock + 9);
    v114 = 0;
    v116 = 0;
    v122 = 0;
    v125 = 0;
    v128 = 0;
    v131 = 0;
    v112[0] = *(_QWORD *)(v87 + 40);
    v112[2] = v109;
    v113 = v102;
    v130 = 0;
    if ( v89 )
      v115 = *(_QWORD *)(v89 + 8);
    else
      v115 = 0;
    v91 = v103;
    v127 = UdpSetSockOptEndpointSetSessionInfoComplete;
    v124 = a9;
    v92 = *(_QWORD *)(v87 + 48);
    v117 = v88;
    v126 = v86;
    v118 = v103;
    v119 = a5;
    v120 = Source2;
    v121 = (int)a7;
    v123 = a8;
    v129 = v90;
    v112[1] = 0;
    v93 = *(__int64 (__fastcall **)(__int64))(v92 + 256);
    if ( v93 == IpNlpSetSessionInfo )
      v94 = IpNlpSetSessionInfo((__int64)v112);
    else
      v94 = v93((__int64)v112);
    if ( v94 < 0 )
      goto LABEL_275;
    v95 = v110;
    v96 = v111;
    if ( v101 )
      *v101 = v124;
    if ( v96 )
      *v96 = v128;
    if ( v95 )
    {
      v10 = v94;
      *v95 = HIDWORD(v128);
    }
    else
    {
LABEL_275:
      v10 = v94;
      if ( v94 < 0 )
      {
LABEL_280:
        if ( v94 == 259 )
          return (unsigned int)v10;
        UdpSetSockOptEndpointSetSessionInfoComplete(v136.LockQueue.Next);
        return 259;
      }
    }
    if ( (!v91 || v91 == 41) && a5 == 75 )
      SpinLock[6] = SpinLock[6] & 0xFFFDFFFF | (LOBYTE(Source2->Next) != 0 ? 0x20000 : 0);
    goto LABEL_280;
  }
  if ( !Source2 || (unsigned __int64)a7 < 0x20 )
    goto LABEL_169;
  if ( RtlCompareMemory(&REAL_TIME_NOTIFICATION_CAPABILITY, Source2, 0x10u) != 16 )
    goto LABEL_59;
  return (unsigned int)UdpScheduleNotificationChannelSetupRequest(SpinLock, Source2, &LockHandle);
}

```

## disassembly

```asm
0x1400d4fb0  mov     [rsp-8+arg_8], rbx
0x1400d4fb5  push    rbp
0x1400d4fb6  push    rsi
0x1400d4fb7  push    rdi
0x1400d4fb8  push    r12
0x1400d4fba  push    r13
0x1400d4fbc  push    r14
0x1400d4fbe  push    r15
0x1400d4fc0  lea     rbp, [rsp-0F0h]
0x1400d4fc8  sub     rsp, 1F0h
0x1400d4fcf  mov     rax, cs:__security_cookie
0x1400d4fd6  xor     rax, rsp
0x1400d4fd9  mov     [rbp+120h+var_38], rax
0x1400d4fe0  mov     rax, [rbp+120h+arg_48]
0x1400d4fe7  xor     ebx, ebx
0x1400d4fe9  mov     r13, [rbp+120h+arg_38]
0x1400d4ff0  xorps   xmm0, xmm0
0x1400d4ff3  mov     rdi, [rbp+120h+Source2]
0x1400d4ffa  mov     r12d, r9d
0x1400d4ffd  mov     r15, [rbp+120h+arg_30]
0x1400d5004  mov     r14, rcx
0x1400d5007  mov     esi, [rbp+120h+arg_20]
0x1400d500d  mov     [rsp+220h+var_1B8], rax
0x1400d5012  xor     eax, eax
0x1400d5014  cmp     cs:dword_1402241D4, eax
0x1400d501a  mov     [rsp+220h+var_1AC], r9d
0x1400d501f  mov     [rbp+120h+var_180], r8
0x1400d5023  mov     [rbp+120h+var_188], rdx
0x1400d5027  movups  xmmword ptr [rsp+220h+LockHandle.LockQueue.Next], xmm0
0x1400d502c  mov     qword ptr [rsp+220h+LockHandle.OldIrql], rax
0x1400d5031  jz      short loc_1400D5082
0x1400d5033  test    byte ptr cs:WPP_MAIN_CB.Dpc.DeferredContext+4, 8
0x1400d503a  movups  xmmword ptr [rbp+120h+var_50.LockQueue.Next], xmm0
0x1400d5041  jz      short loc_1400D5082
0x1400d5043  mov     [rbp+120h+var_50.LockQueue.Next], rcx
0x1400d504a  lea     r8, [rbp+120h+var_50]
0x1400d5051  mov     [rsp+220h+var_1E8], rdi
0x1400d5056  lea     rdx, TCPIP_SETSOCKOPT
0x1400d505d  test    rdi, rdi
0x1400d5060  mov     ecx, r15d
0x1400d5063  cmovz   ecx, ebx
0x1400d5066  mov     dword ptr [rsp+220h+var_1F0], ecx
0x1400d506a  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x1400d5071  mov     dword ptr [rsp+220h+var_1F8], esi
0x1400d5075  mov     dword ptr [rsp+220h+var_200], r9d
0x1400d507a  mov     r9, r14
0x1400d507d  call    McTemplateK0pqqqbr3_EtwWriteTransfer
0x1400d5082  lea     rdx, [rsp+220h+LockHandle]; LockHandle
0x1400d5087  mov     rcx, r14; SpinLock
0x1400d508a  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x1400d5091  nop     dword ptr [rax+rax+00h]
0x1400d5096  mov     eax, [r14+8]
0x1400d509a  test    eax, eax
0x1400d509c  jnz     short loc_1400D5096
0x1400d509e  cmp     r12d, 11h
0x1400d50a2  jnz     short loc_1400D5115
0x1400d50a4  cmp     esi, 1
0x1400d50a7  jnz     short loc_1400D50CF
0x1400d50a9  cmp     r15, 1
0x1400d50ad  jb      loc_1400D5A5E
0x1400d50b3  movzx   eax, byte ptr [rdi]
0x1400d50b6  neg     al
0x1400d50b8  mov     eax, [r14+18h]
0x1400d50bc  sbb     ecx, ecx
0x1400d50be  and     eax, 0FFFFFFBFh
0x1400d50c1  and     ecx, 40h
0x1400d50c4  or      ecx, eax
0x1400d50c6  mov     [r14+18h], ecx
0x1400d50ca  jmp     loc_1400D5A63
0x1400d50cf  cmp     esi, 2
0x1400d50d2  jnz     short loc_1400D50F4
0x1400d50d4  cmp     r15, 4
0x1400d50d8  jb      loc_1400D5A5E
0x1400d50de  mov     eax, [rdi]
0x1400d50e0  mov     rcx, r14
0x1400d50e3  mov     [r14+170h], eax
0x1400d50ea  call    UdpCacheDefaultUsoInformation
0x1400d50ef  jmp     loc_1400D5A63
0x1400d50f4  cmp     esi, 3
0x1400d50f7  jnz     loc_1400D5349
0x1400d50fd  cmp     r15, 4
0x1400d5101  jb      loc_1400D5A5E
0x1400d5107  mov     eax, [rdi]
0x1400d5109  mov     [r14+180h], eax
0x1400d5110  jmp     loc_1400D5A63
0x1400d5115  mov     r9d, 0FFFFh
0x1400d511b  cmp     r12d, 29h ; ')'
0x1400d511f  jnz     short loc_1400D5159
0x1400d5121  cmp     esi, 1Bh
0x1400d5124  jnz     loc_1400D530B
0x1400d512a  cmp     r15, 1
0x1400d512e  jb      loc_1400D5A5E
0x1400d5134  mov     edx, [r14+18h]
0x1400d5138  test    dl, 1
0x1400d513b  jnz     loc_1400D5418
0x1400d5141  movzx   eax, byte ptr [rdi]
0x1400d5144  neg     al
0x1400d5146  sbb     ecx, ecx
0x1400d5148  and     edx, 0FFFFFFEFh
0x1400d514b  and     ecx, 10h
0x1400d514e  or      ecx, edx
0x1400d5150  mov     [r14+18h], ecx
0x1400d5154  jmp     loc_1400D5A63
0x1400d5159  cmp     r12d, r9d
0x1400d515c  jnz     loc_1400D530B
0x1400d5162  cmp     esi, 20h ; ' '
0x1400d5165  jnz     short loc_1400D5191
0x1400d5167  cmp     r15, 1
0x1400d516b  jb      loc_1400D5A5E
0x1400d5171  movzx   eax, byte ptr [rdi]
0x1400d5174  neg     al
0x1400d5176  mov     eax, [r14+18h]
0x1400d517a  sbb     ecx, ecx
0x1400d517c  btr     eax, 7
0x1400d5180  and     ecx, 80h
0x1400d5186  or      ecx, eax
0x1400d5188  mov     [r14+18h], ecx
0x1400d518c  jmp     loc_1400D5A63
0x1400d5191  cmp     esi, 4
0x1400d5194  jnz     short loc_1400D51D6
0x1400d5196  cmp     r15, 1
0x1400d519a  jb      loc_1400D5A5E
0x1400d51a0  mov     edx, [r14+18h]
0x1400d51a4  test    dl, 1
0x1400d51a7  jnz     loc_1400D5418
0x1400d51ad  test    edx, 6000h
0x1400d51b3  jnz     loc_1400D59EB
0x1400d51b9  movzx   eax, byte ptr [rdi]
0x1400d51bc  neg     al
0x1400d51be  mov     eax, 100h
0x1400d51c3  sbb     ecx, ecx
0x1400d51c5  btr     edx, 8
0x1400d51c9  and     ecx, eax
0x1400d51cb  or      ecx, edx
0x1400d51cd  mov     [r14+18h], ecx
0x1400d51d1  jmp     loc_1400D5A63
0x1400d51d6  cmp     esi, 3008h
0x1400d51dc  jnz     short loc_1400D521E
0x1400d51de  cmp     r15, 1
0x1400d51e2  jb      loc_1400D5A5E
0x1400d51e8  mov     edx, [r14+18h]
0x1400d51ec  test    dl, 1
0x1400d51ef  jnz     loc_1400D5418
0x1400d51f5  test    edx, 2300h
0x1400d51fb  jnz     loc_1400D59EB
0x1400d5201  movzx   eax, byte ptr [rdi]
0x1400d5204  neg     al
0x1400d5206  mov     eax, 4000h
0x1400d520b  sbb     ecx, ecx
0x1400d520d  btr     edx, 0Eh
0x1400d5211  and     ecx, eax
0x1400d5213  or      ecx, edx
0x1400d5215  mov     [r14+18h], ecx
0x1400d5219  jmp     loc_1400D5A63
0x1400d521e  cmp     esi, 0FFFFFFFBh
0x1400d5221  jnz     short loc_1400D5260
0x1400d5223  cmp     r15, 1
0x1400d5227  jb      loc_1400D5A5E
0x1400d522d  mov     edx, [r14+18h]
0x1400d5231  test    dl, 1
0x1400d5234  jnz     loc_1400D5418
0x1400d523a  bt      edx, 0Eh
0x1400d523e  jb      loc_1400D59EB
0x1400d5244  movzx   eax, byte ptr [rdi]
0x1400d5247  neg     al
0x1400d5249  sbb     ecx, ecx
0x1400d524b  btr     edx, 9
0x1400d524f  and     ecx, 200h
0x1400d5255  or      ecx, edx
0x1400d5257  mov     [r14+18h], ecx
0x1400d525b  jmp     loc_1400D5A63
0x1400d5260  cmp     esi, 3005h
0x1400d5266  jnz     short loc_1400D529E
0x1400d5268  cmp     r15, 1
0x1400d526c  jb      loc_1400D5A5E
0x1400d5272  mov     edx, [r14+18h]
0x1400d5276  test    dl, 1
0x1400d5279  jnz     loc_1400D5418
0x1400d527f  movzx   eax, byte ptr [rdi]
0x1400d5282  mov     r8d, 400h
0x1400d5288  neg     al
0x1400d528a  sbb     ecx, ecx
0x1400d528c  btr     edx, 0Ah
0x1400d5290  and     ecx, r8d
0x1400d5293  or      ecx, edx
0x1400d5295  mov     [r14+18h], ecx
0x1400d5299  jmp     loc_1400D5A63
0x1400d529e  cmp     esi, 3004h
0x1400d52a4  jz      loc_1400D5A63
0x1400d52aa  cmp     esi, 10h
0x1400d52ad  jnz     short loc_1400D52D9
0x1400d52af  cmp     r15, 1
0x1400d52b3  jb      loc_1400D5A5E
0x1400d52b9  movzx   eax, byte ptr [rdi]
0x1400d52bc  neg     al
0x1400d52be  mov     eax, [r14+18h]
0x1400d52c2  sbb     ecx, ecx
0x1400d52c4  btr     eax, 0Ch
0x1400d52c8  and     ecx, 1000h
0x1400d52ce  or      ecx, eax
0x1400d52d0  mov     [r14+18h], ecx
0x1400d52d4  jmp     loc_1400D5A63
0x1400d52d9  cmp     esi, 3011h
0x1400d52df  jnz     short loc_1400D530B
0x1400d52e1  cmp     r15, 1
0x1400d52e5  jb      loc_1400D5A5E
0x1400d52eb  mov     edx, [r14+18h]
0x1400d52ef  movzx   eax, byte ptr [rdi]
0x1400d52f2  btr     edx, 13h
0x1400d52f6  neg     al
0x1400d52f8  sbb     ecx, ecx
0x1400d52fa  and     ecx, 80000h
0x1400d5300  or      edx, ecx
0x1400d5302  mov     [r14+18h], edx
0x1400d5306  jmp     loc_1400D5A63
0x1400d530b  cmp     r12d, 0FFFCh
0x1400d5312  jnz     loc_1400D6070
0x1400d5318  cmp     esi, 980000EBh
0x1400d531e  jnz     loc_1400D53FE
0x1400d5324  cmp     r15, 8
0x1400d5328  jb      loc_1400D5A5E
0x1400d532e  mov     ecx, [rdi]
0x1400d5330  mov     eax, ecx
0x1400d5332  and     eax, 0FFFFFFFCh
0x1400d5335  mov     [rdi], eax
0x1400d5337  jnz     short loc_1400D5349
0x1400d5339  mov     edx, ecx
0x1400d533b  and     edx, 2
0x1400d533e  jz      short loc_1400D536A
0x1400d5340  movzx   eax, word ptr [rdi+4]
0x1400d5344  test    ax, ax
0x1400d5347  jnz     short loc_1400D5353
0x1400d5349  mov     ebx, 0C000000Dh
0x1400d534e  jmp     loc_1400D5A63
0x1400d5353  mov     r8, [r14+168h]
0x1400d535a  test    r8, r8
0x1400d535d  jz      short loc_1400D536A
0x1400d535f  cmp     ax, [r8+12h]
0x1400d5364  jnz     loc_1400D59EB
0x1400d536a  mov     eax, [r14+18h]
0x1400d536e  shl     ecx, 12h
0x1400d5371  xor     ecx, eax
0x1400d5373  and     ecx, 40000h
0x1400d5379  xor     ecx, eax
0x1400d537b  mov     rax, [r14+168h]
0x1400d5382  mov     [r14+18h], ecx
0x1400d5386  test    edx, edx
0x1400d5388  jz      short loc_1400D53E4
0x1400d538a  test    rax, rax
0x1400d538d  jnz     loc_1400D5A63
0x1400d5393  movzx   ebx, word ptr [rdi+4]
0x1400d5397  mov     edx, 18h
0x1400d539c  mov     ecx, 40h ; '@'
0x1400d53a1  mov     r8d, 54706455h
0x1400d53a7  call    cs:__imp_ExAllocatePool2
0x1400d53ae  nop     dword ptr [rax+rax+00h]
0x1400d53b3  mov     rcx, rax
0x1400d53b6  test    rax, rax
0x1400d53b9  jnz     short loc_1400D53C5
0x1400d53bb  mov     ebx, 0C000009Ah
0x1400d53c0  jmp     loc_1400D5A63
0x1400d53c5  mov     [rax+8], rcx
0x1400d53c9  mov     [rax], rcx
0x1400d53cc  xor     eax, eax
0x1400d53ce  mov     [rcx+12h], bx
0x1400d53d2  xor     ebx, ebx
0x1400d53d4  mov     [rcx+10h], ax
0x1400d53d8  mov     [r14+168h], rcx
0x1400d53df  jmp     loc_1400D5A63
0x1400d53e4  test    rax, rax
0x1400d53e7  jz      loc_1400D5A63
0x1400d53ed  lea     rcx, [r14+168h]
0x1400d53f4  call    UdpUninitTimestampQueue
0x1400d53f9  jmp     loc_1400D5A63
0x1400d53fe  cmp     esi, 98000015h
0x1400d5404  jnz     short loc_1400D5445
0x1400d5406  cmp     r15, 2
0x1400d540a  jb      loc_1400D5A5E
0x1400d5410  mov     eax, [r14+18h]
0x1400d5414  test    al, 1
0x1400d5416  jz      short loc_1400D5422
0x1400d5418  mov     ebx, 0C0000238h
0x1400d541d  jmp     loc_1400D5A63
0x1400d5422  test    eax, 4100h
0x1400d5427  jnz     loc_1400D59EB
0x1400d542d  bts     eax, 0Dh
0x1400d5431  mov     [r14+18h], eax
0x1400d5435  movzx   eax, word ptr [rdi]
0x1400d5438  mov     [r14+0AAh], ax
0x1400d5440  jmp     loc_1400D5A63
0x1400d5445  cmp     esi, 8800000Bh
0x1400d544b  jz      loc_1400D5B88
0x1400d5451  cmp     esi, 8800001Ah
0x1400d5457  jz      loc_1400D5B88
0x1400d545d  cmp     esi, 98000022h
0x1400d5463  jnz     short loc_1400D547B
0x1400d5465  mov     rcx, [r14+48h]
0x1400d5469  mov     r8, r15
0x1400d546c  mov     rdx, rdi
0x1400d546f  call    InetInspectFirewallSystemPort
  ... truncated ...
```
