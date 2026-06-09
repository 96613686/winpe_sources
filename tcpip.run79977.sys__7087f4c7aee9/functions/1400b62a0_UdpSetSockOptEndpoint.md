# UdpSetSockOptEndpoint

- ea: `0x1400b62a0`
- end: `0x1400b7631`
- name: `UdpSetSockOptEndpoint`
- size: `5009`
- prototype: `__int64 __usercall@<rax>(PKSPIN_LOCK SpinLock@<rcx>, int, void *Source2, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `23`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1400b5d40`

## callees

- `0x140006384`
- `0x140011b00`
- `0x140012560`
- `0x140012cb8`
- `0x14003d080`
- `0x14004e23c`
- `0x140052630`
- `0x14005bf60`
- `0x140082c10`
- `0x1400951fc`
- `0x1400b62a0`
- `0x1400f7100`
- `0x140112d24`
- `0x140115880`
- `0x14011882c`
- `0x14011ef6c`
- `0x140127674`
- `0x140152fb4`
- `0x140167b3c`
- `0x14017f924`
- `0x1401bd420`
- `0x1401bf4d0`
- `0x1401bf700`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x1400b6def`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400b6def`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400b637a`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400b6bed`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400b6ff4`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400b7042`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400b719d`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400b71fd`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400b637a`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400b6bed`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400b6ff4`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400b7042`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400b719d`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400b71fd`
- `ntoskrnl!RtlCompareMemory` at `0x1400b690b`
- `ntoskrnl!RtlCompareMemory` at `0x1400b697e`
- `ntoskrnl!RtlCompareMemory` at `0x1400b690b`
- `ntoskrnl!RtlCompareMemory` at `0x1400b697e`
- `ntoskrnl!PsGetProcessId` at `0x1400b6a4e`
- `ntoskrnl!PsGetProcessId` at `0x1400b6a4e`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400b679d`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400b6818`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400b683f`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400b6872`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400b6b50`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400b6c56`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400b6d58`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400b6db9`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400b6e33`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400b6eab`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400b7018`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400b7086`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400b70cd`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400b71c5`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400b723b`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400b7295`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400b72e9`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400b7325`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400b7448`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400b679d`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400b6818`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400b683f`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400b6872`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400b6b50`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400b6c56`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400b6d58`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400b6db9`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400b6e33`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400b6eab`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400b7018`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400b7086`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400b70cd`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400b71c5`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400b723b`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400b7295`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400b72e9`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400b7325`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400b7448`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b6d29`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b7282`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b6d29`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b7282`
- `ntoskrnl!ExAllocatePool2` at `0x1400b6697`
- `ntoskrnl!ExAllocatePool2` at `0x1400b6d79`
- `ntoskrnl!ExAllocatePool2` at `0x1400b706d`
- `ntoskrnl!ExAllocatePool2` at `0x1400b72ce`
- `ntoskrnl!ExAllocatePool2` at `0x1400b746c`
- `ntoskrnl!ExAllocatePool2` at `0x1400b6697`
- `ntoskrnl!ExAllocatePool2` at `0x1400b6d79`
- `ntoskrnl!ExAllocatePool2` at `0x1400b706d`
- `ntoskrnl!ExAllocatePool2` at `0x1400b72ce`
- `ntoskrnl!ExAllocatePool2` at `0x1400b746c`
- `NETIO!NetioInsertWorkQueue` at `0x1400b6e1d`
- `NETIO!NetioInsertWorkQueue` at `0x1400b6e1d`
- `NETIO!NetioNcmTlObjectRequest` at `0x1400b69d8`
- `NETIO!NetioNcmTlObjectRequest` at `0x1400b69d8`
- `NETIO!NmrClientDetachProviderComplete` at `0x1400b7027`
- `NETIO!NmrClientDetachProviderComplete` at `0x1400b71d4`
- `NETIO!NmrClientDetachProviderComplete` at `0x1400b7027`
- `NETIO!NmrClientDetachProviderComplete` at `0x1400b71d4`

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
  KSPIN_LOCK v28; // rdi
  __int64 v29; // rax
  unsigned int v30; // edi
  int v31; // esi
  __int16 v32; // bx
  __int64 v33; // r9
  __int64 v34; // rdx
  KSPIN_LOCK v35; // rax
  int v36; // eax
  unsigned __int8 ProcessId; // al
  KSPIN_LOCK v38; // rax
  int v39; // r8d
  unsigned int v40; // edx
  int v41; // r8d
  int v42; // ecx
  bool v43; // si
  KSPIN_LOCK v44; // rcx
  int v45; // eax
  __int64 v46; // r13
  PVOID v47; // r12
  KSPIN_LOCK v48; // r15
  KSPIN_LOCK v49; // rbx
  int v50; // ecx
  unsigned int v51; // ecx
  KSPIN_LOCK v52; // r8
  char v53; // cl
  KSPIN_LOCK v54; // rdx
  _DWORD *v55; // rcx
  _DWORD **v56; // rax
  void **v57; // r8
  __int64 v58; // rdi
  _QWORD *v59; // rcx
  __int64 v60; // rax
  _QWORD *v61; // rbx
  KSPIN_LOCK v62; // r13
  int v63; // ecx
  int v64; // edx
  int v65; // eax
  __int64 v66; // rax
  void *v67; // rdi
  __int64 v68; // rax
  __int64 *v69; // rdx
  __int64 v70; // rbx
  __int64 v71; // rsi
  int v72; // eax
  __int64 v73; // rcx
  void *v74; // rdi
  __int64 *v75; // rcx
  __int64 v76; // rdi
  _QWORD *v77; // rdx
  __int64 v78; // rax
  unsigned int v79; // r8d
  unsigned __int16 v80; // ax
  __int64 v81; // rdx
  int *v82; // rax
  int *v83; // rcx
  struct _KSPIN_LOCK_QUEUE *v84; // rax
  struct _KSPIN_LOCK_QUEUE *v85; // rdx
  __int64 v86; // rcx
  __int64 v87; // r10
  KSPIN_LOCK v88; // r8
  KSPIN_LOCK v89; // r9
  int v90; // r12d
  __int64 v91; // rax
  __int64 (__fastcall *v92)(_QWORD *); // rax
  int v93; // eax
  _DWORD *v94; // r9
  _DWORD *v95; // rcx
  char v97; // [rsp+30h] [rbp-D0h]
  char v98; // [rsp+40h] [rbp-C0h]
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD *v100; // [rsp+68h] [rbp-98h] BYREF
  int v101; // [rsp+70h] [rbp-90h]
  int v102; // [rsp+74h] [rbp-8Ch]
  __int64 v103; // [rsp+78h] [rbp-88h] BYREF
  struct _KLOCK_QUEUE_HANDLE v104; // [rsp+80h] [rbp-80h] BYREF
  struct _KSPIN_LOCK_QUEUE *v105; // [rsp+98h] [rbp-68h]
  KSPIN_LOCK *v106; // [rsp+A0h] [rbp-60h]
  __int64 v107; // [rsp+A8h] [rbp-58h] BYREF
  int *v108; // [rsp+B0h] [rbp-50h]
  _DWORD *v109; // [rsp+B8h] [rbp-48h] BYREF
  _DWORD *v110; // [rsp+C0h] [rbp-40h] BYREF
  _QWORD v111[3]; // [rsp+D0h] [rbp-30h] BYREF
  int v112; // [rsp+E8h] [rbp-18h]
  int v113; // [rsp+ECh] [rbp-14h]
  __int64 v114; // [rsp+F0h] [rbp-10h]
  __int64 v115; // [rsp+F8h] [rbp-8h]
  __int64 v116; // [rsp+100h] [rbp+0h]
  int v117; // [rsp+108h] [rbp+8h]
  unsigned int v118; // [rsp+10Ch] [rbp+Ch]
  struct _KSPIN_LOCK_QUEUE *v119; // [rsp+110h] [rbp+10h]
  int v120; // [rsp+118h] [rbp+18h]
  int v121; // [rsp+11Ch] [rbp+1Ch]
  _QWORD *v122; // [rsp+120h] [rbp+20h]
  unsigned int v123; // [rsp+128h] [rbp+28h]
  int v124; // [rsp+12Ch] [rbp+2Ch]
  struct _KSPIN_LOCK_QUEUE *v125; // [rsp+130h] [rbp+30h]
  __int64 (__fastcall *v126)(PVOID); // [rsp+138h] [rbp+38h]
  __int64 v127; // [rsp+140h] [rbp+40h]
  KSPIN_LOCK v128; // [rsp+148h] [rbp+48h]
  __int128 v129; // [rsp+150h] [rbp+50h]
  __int64 v130; // [rsp+160h] [rbp+60h]
  struct _KLOCK_QUEUE_HANDLE v131; // [rsp+170h] [rbp+70h] BYREF
  unsigned __int128 v132; // [rsp+190h] [rbp+90h] BYREF
  __int128 v133; // [rsp+1A0h] [rbp+A0h]
  _OWORD v134[2]; // [rsp+1B0h] [rbp+B0h] BYREF
  struct _KLOCK_QUEUE_HANDLE v135; // [rsp+1D0h] [rbp+D0h] BYREF

  v10 = 0;
  v100 = a10;
  v102 = a4;
  v106 = a3;
  v105 = a2;
  memset(&LockHandle, 0, sizeof(LockHandle));
  if ( dword_1402201D4 )
  {
    v135.LockQueue = 0;
    if ( (*((_BYTE *)&WPP_MAIN_CB.Reserved + 12) & 8) != 0 )
    {
      v135.LockQueue.Next = (struct _KSPIN_LOCK_QUEUE *volatile)SpinLock;
      v13 = (int)a7;
      if ( !Source2 )
        v13 = 0;
      McTemplateK0pqqqbr3_EtwWriteTransfer(
        (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
        (unsigned int)&TCPIP_SETSOCKOPT,
        (unsigned int)&v135,
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
      v62 = *((_QWORD *)SpinLock + 9);
      if ( a5 == -2013265909 )
      {
        v63 = *(_DWORD *)(v62 + 648);
        v64 = 0;
        memset(&v104, 0, sizeof(v104));
        if ( (v63 & 1) != 0 )
        {
          if ( (v63 & 0x200) != 0 )
          {
            v64 = 1;
          }
          else if ( (v63 & 0x400) != 0 )
          {
            v64 = 2;
          }
        }
        else if ( (v63 & 2) != 0 )
        {
          if ( (v63 & 0x200) != 0 )
          {
            v64 = 3;
          }
          else if ( (v63 & 0x400) != 0 )
          {
            v64 = 4;
          }
        }
        v132 = 0;
        v133 = 0;
        v100 = 0;
        memset(v134, 0, 24);
        while ( 1 )
        {
          v65 = dword_140226F40;
          if ( (dword_140226F40 & 1) != 0 )
            break;
          if ( v65 == _InterlockedCompareExchange(&dword_140226F40, dword_140226F40 + 2, dword_140226F40) )
          {
            v66 = *(_QWORD *)(qword_140226F38 + 8);
            *((_QWORD *)&v133 + 1) = &v100;
            *(_QWORD *)&v133 = 0;
            memset((char *)v134 + 4, 0, 20);
            v132 = __PAIR128__((unsigned __int64)a7, (unsigned __int64)Source2);
            LODWORD(v134[0]) = v64;
            v10 = (*(__int64 (__fastcall **)(unsigned __int128 *))(v66 + 8))(&v132);
            if ( _InterlockedExchangeAdd(&dword_140226F40, 0xFFFFFFFE) == 3 )
            {
              memset(&v135, 0, sizeof(v135));
              v67 = *(void **)(qword_140226F38 + 24);
              *(_QWORD *)(qword_140226F38 + 24) = 0;
              KeAcquireInStackQueuedSpinLock(&::SpinLock, &v135);
              while ( dword_140226F50 )
                ;
              qword_140226F38 = 0;
              KeReleaseInStackQueuedSpinLock(&v135);
              NmrClientDetachProviderComplete(v67);
            }
            if ( v10 < 0 )
              goto LABEL_243;
            KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v62 + 632), &v104);
            while ( *(_DWORD *)(v62 + 640) )
              ;
            if ( !*(_QWORD *)(v62 + 656) )
            {
              v68 = ExAllocatePool2(64, 24, 1699959109);
              *(_QWORD *)(v62 + 656) = v68;
              if ( !v68 )
              {
                KeReleaseInStackQueuedSpinLock(&v104);
                EQoSDeleteQoSFlow(v100);
                v10 = -1073741801;
                UdpDereferenceEndpoint(SpinLock);
                return (unsigned int)v10;
              }
              *(_OWORD *)v68 = 0;
              *(_QWORD *)(v68 + 16) = 0;
            }
            v69 = *(__int64 **)(v62 + 656);
            v70 = *v69;
            *v69 = (__int64)v100;
            KeReleaseInStackQueuedSpinLock(&v104);
            if ( v70 )
              EQoSDereferenceQoSFlow(v70);
            goto LABEL_210;
          }
        }
      }
      else
      {
        memset(&v135, 0, sizeof(v135));
        if ( !a7 )
        {
          v71 = 0;
LABEL_222:
          KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v62 + 632), &v135);
          while ( *(_DWORD *)(v62 + 640) )
            ;
          v75 = *(__int64 **)(v62 + 656);
          v76 = 0;
          if ( v75 )
            v76 = *v75;
          if ( v71 )
          {
            if ( !v75 )
            {
              v78 = ExAllocatePool2(64, 24, 1699959109);
              v75 = (__int64 *)v78;
              if ( !v78 )
              {
                KeReleaseInStackQueuedSpinLock(&v135);
                EQoSDereferenceQoSFlow(v71);
                v10 = -1073741801;
                UdpDereferenceEndpoint(SpinLock);
                return (unsigned int)v10;
              }
              *(_QWORD *)(v78 + 8) = 0;
              *(_QWORD *)(v78 + 16) = 0;
              *(_QWORD *)(v62 + 656) = v78;
            }
            *v75 = v71;
            KeReleaseInStackQueuedSpinLock(&v135);
            if ( v76 )
              EQoSDereferenceQoSFlow(v76);
LABEL_210:
            v10 = 0;
            UdpDereferenceEndpoint(SpinLock);
          }
          else if ( v76 )
          {
            *v75 = 0;
            v77 = *(_QWORD **)(v62 + 656);
            if ( !*v77 && !v77[1] && ((*(_DWORD *)(v62 + 648) & 0x20) != 0 || !v77[2]) )
            {
              *(_QWORD *)(v62 + 656) = 0;
              ExFreePoolWithTag(v75, 0x65535145u);
            }
            KeReleaseInStackQueuedSpinLock(&v135);
            EQoSDereferenceQoSFlow(v76);
            v10 = 0;
            UdpDereferenceEndpoint(SpinLock);
          }
          else
          {
            KeReleaseInStackQueuedSpinLock(&v135);
            v10 = 0;
            UdpDereferenceEndpoint(SpinLock);
          }
          return (unsigned int)v10;
        }
        memset(&v104, 0, sizeof(v104));
        while ( 1 )
        {
          v72 = dword_140226F40;
          if ( (dword_140226F40 & 1) != 0 )
            break;
          if ( v72 == _InterlockedCompareExchange(&dword_140226F40, dword_140226F40 + 2, dword_140226F40) )
          {
            v73 = *(_QWORD *)(qword_140226F38 + 8);
            v104.LockQueue.Next = Source2;
            v104.LockQueue.Lock = a7;
            v10 = (*(__int64 (__fastcall **)(struct _KLOCK_QUEUE_HANDLE *))(v73 + 72))(&v104);
            if ( _InterlockedExchangeAdd(&dword_140226F40, 0xFFFFFFFE) == 3 )
            {
              memset(&v131, 0, sizeof(v131));
              v74 = *(void **)(qword_140226F38 + 24);
              *(_QWORD *)(qword_140226F38 + 24) = 0;
              KeAcquireInStackQueuedSpinLock(&::SpinLock, &v131);
              while ( dword_140226F50 )
                ;
              qword_140226F38 = 0;
              KeReleaseInStackQueuedSpinLock(&v131);
              NmrClientDetachProviderComplete(v74);
            }
            if ( v10 >= 0 )
            {
              v71 = *(_QWORD *)&v104.OldIrql;
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
    return (unsigned int)InetInspectSocketOption(SpinLock, *((_QWORD *)SpinLock + 9), a5, Source2, a7, a8, a9, v100);
  }
  if ( a5 == 1476395213 )
  {
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    if ( *((_QWORD *)SpinLock + 9) && a9 >= 8 && a8 )
    {
      *a8 = WfpAleQueryOrInsertEndpointHandle();
      if ( v100 )
        *v100 = 8;
    }
    else
    {
      return (unsigned int)-1073741823;
    }
    return (unsigned int)v10;
  }
  if ( a5 + 1744830364 <= 2 )
  {
    v60 = ExAllocatePool2(64, 80, 1464165461);
    v61 = (_QWORD *)v60;
    if ( !v60 )
    {
      v10 = -1073741801;
      goto LABEL_170;
    }
    *(_QWORD *)(v60 + 8) = SpinLock;
    if ( _InterlockedIncrement64((volatile signed __int64 *)SpinLock + 2) <= 1 )
      __fastfail(0xEu);
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    v61[2] = v105;
    v61[3] = v106;
    v61[8] = a9;
    *((_DWORD *)v61 + 8) = a5;
    v61[5] = Source2;
    v61[6] = a7;
    v61[7] = a8;
    if ( KeGetCurrentIrql() )
    {
      NetioInsertWorkQueue(&UdpPortReservationWorkQueue, v61);
    }
    else
    {
      *v61 = 0;
      UdpPortReservationWorkQueueRoutine(v61);
    }
    return 259;
  }
  if ( a5 == 1207959589 )
  {
    if ( a9 >= 8 )
    {
      v28 = *((_QWORD *)SpinLock + 37);
      if ( v28 )
      {
        v29 = *(_QWORD *)v28;
        v30 = *(_DWORD *)(v28 + 12);
        v31 = *(_DWORD *)(*(_QWORD *)(v29 + 8) + 8LL);
        v32 = *(_WORD *)(*((_QWORD *)SpinLock + 39) + 24LL);
        KeReleaseInStackQueuedSpinLock(&LockHandle);
        v33 = 1024;
        if ( v32 != 23 )
          v33 = 256;
        v34 = 0x8000;
        if ( v32 != 23 )
          v34 = 0x4000;
        v10 = (*((__int64 (__fastcall **)(_QWORD, __int64, _QWORD, __int64, int, _QWORD *))UdpRssHash + 3))(
                SpinLock[71],
                v34,
                v30,
                v33,
                v31,
                a8);
        *v100 = (((__int64)v10 >> 63) & 0xFFFFFFFFFFFFFFF8uLL) + 8;
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
        v35 = *((_QWORD *)SpinLock + 23);
        if ( v35 )
        {
          v133 = 0;
          memset(v134, 0, sizeof(v134));
          v132 = v35;
          NetioNcmTlObjectRequest(&v132, 2);
          v36 = DWORD2(v134[0]);
          *(_DWORD *)a8 = DWORD2(v134[0]);
          if ( v36 != 1 || (SpinLock[6] & 4) != 0 )
          {
LABEL_117:
            if ( v100 )
              *v100 = 4;
            goto LABEL_120;
          }
        }
        else if ( (SpinLock[6] & 4) != 0 )
        {
          v10 = -1073741637;
LABEL_120:
          if ( dword_1402201D4 )
          {
            v135.LockQueue = 0;
            if ( (BYTE3(WPP_MAIN_CB.Reserved) & 0x10) != 0 )
            {
              ProcessId = (unsigned __int8)PsGetProcessId(*((PEPROCESS *)SpinLock + 6));
              v98 = *(_DWORD *)a8;
              v97 = ProcessId;
              v38 = *((_QWORD *)SpinLock + 23);
              v39 = (SpinLock[6] >> 2) & 1;
              v135.LockQueue.Lock = 0;
              v135.LockQueue.Next = (struct _KSPIN_LOCK_QUEUE *volatile)SpinLock;
              McTemplateK0ppqqqqq_EtwWriteTransfer(
                (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
                (unsigned int)&UDP_QUERY_NOTIFICATION_CHANNEL_STATUS_REQUEST,
                (unsigned int)&v135,
                (_DWORD)SpinLock,
                v38,
                v39,
                v97,
                0,
                v98,
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
        v40 = SpinLock[6];
        v41 = (int)Source2->Next;
        if ( ((v40 >> 15) & 1) == (LODWORD(Source2->Next) == 1) )
        {
LABEL_126:
          v42 = 0;
          if ( v41 == 1 )
            v42 = 0x8000;
          SpinLock[6] = SpinLock[6] & 0xFFFF7FFF | v42;
          goto LABEL_170;
        }
        if ( v41 == 1 )
        {
          if ( (v40 & 1) == 0 )
            goto LABEL_126;
          if ( !*((_QWORD *)SpinLock + 13) )
          {
            v10 = -1073741255;
            goto LABEL_170;
          }
          if ( (v40 & 2) == 0 )
            goto LABEL_160;
          v43 = 1;
        }
        else
        {
          v43 = (v40 & 0x10000) != 0;
          if ( (v40 & 0x10000) == 0 )
          {
LABEL_146:
            v50 = 0;
            if ( LODWORD(Source2->Next) == 1 )
              v50 = 0x8000;
            v51 = SpinLock[6] & 0xFFFF7FFF | v50;
            SpinLock[6] = v51;
            if ( v43 )
              SpinLock[6] = v51 ^ (v51 ^ (2 * v51)) & 0x10000;
            goto LABEL_170;
          }
        }
        KeReleaseInStackQueuedSpinLock(&LockHandle);
        v44 = *((_QWORD *)SpinLock + 13);
        if ( LODWORD(Source2->Next) == 1 )
        {
          v45 = InetWakeAcquirePort(
                  *((unsigned __int16 *)SpinLock + 84),
                  *((_QWORD *)SpinLock + 5),
                  *((_QWORD *)SpinLock + 14),
                  *(_QWORD *)(v44 + 8),
                  (__int64)UdpWakePortPool);
        }
        else
        {
          v46 = *(_QWORD *)(v44 + 8);
          v47 = UdpWakePortPool;
          v48 = *((_QWORD *)SpinLock + 5);
          v49 = *((_QWORD *)SpinLock + 14);
          LOWORD(v101) = *((_WORD *)SpinLock + 84);
          v45 = InetWakeReleasePortAf((unsigned __int16)v101, v48, v46, UdpWakePortPool);
          if ( v45 >= 0 && v49 != v48 )
            v45 = InetWakeReleasePortAf((unsigned __int16)v101, v49, v46, v47);
        }
        if ( v45 < 0 )
          v45 = -1073741637;
        v10 = v45;
        KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)SpinLock, &LockHandle);
        while ( SpinLock[2] )
          ;
        if ( v10 < 0 )
          goto LABEL_170;
        goto LABEL_146;
      case 0x980000E9:
        KeReleaseInStackQueuedSpinLock(&LockHandle);
        v52 = *((_QWORD *)SpinLock + 5);
        v53 = *(_WORD *)(v52 + 24) == 23 && (SpinLock[6] & 0x10) == 0;
        return (unsigned int)InetHandleSockOptSioWakeIf(
                               (_DWORD)Source2,
                               (_DWORD)a7,
                               v52,
                               *((_QWORD *)SpinLock + 14),
                               *((_QWORD *)SpinLock + 10),
                               v53,
                               (__int64)UdpWakePortPool);
      case 0x980000EA:
        if ( a9 < 8 || (unsigned __int64)a7 < 4 )
          goto LABEL_169;
        v54 = *((_QWORD *)SpinLock + 45);
        if ( v54 )
        {
          v55 = *(_DWORD **)v54;
          if ( *(_QWORD *)v54 == v54 )
          {
LABEL_164:
            v10 = -1073741661;
          }
          else
          {
            while ( 1 )
            {
              v56 = *(_DWORD ***)v55;
              if ( v55[6] == LODWORD(Source2->Next) )
                break;
              v55 = *(_DWORD **)v55;
              if ( v56 == (_DWORD **)v54 )
                goto LABEL_164;
            }
            if ( v56[1] != v55 || (v57 = (void **)*((_QWORD *)v55 + 1), *v57 != v55) )
              __fastfail(3u);
            *v57 = v56;
            v56[1] = v57;
            --*(_WORD *)(v54 + 16);
            v58 = *((_QWORD *)v55 + 2);
            ExFreePoolWithTag(v55, 0);
            v59 = v100;
            *a8 = v58;
            *v59 = 8;
          }
          goto LABEL_170;
        }
        goto LABEL_160;
    }
LABEL_244:
    v79 = SpinLock[6];
    v110 = 0;
    v109 = 0;
    v107 = 0;
    v103 = 0;
    if ( (v79 & 1) != 0 )
    {
      v80 = *((_WORD *)SpinLock + 87);
    }
    else
    {
      v81 = v79 >> 4;
      LOBYTE(v81) = (v79 & 0x10) != 0;
      v80 = InetResolveEffectiveFamilyAf(*((_QWORD *)SpinLock + 5), v81);
    }
    v10 = InetResolveSetSockOptSs(
            (int)SpinLock + 232,
            *((_QWORD *)SpinLock + 5),
            (unsigned int)&UdpInetTransport,
            v80,
            (v79 & 0x20) != 0,
            a4,
            (__int64)&v103,
            (__int64)&v107,
            (__int64)&v110,
            (__int64)&v109);
    if ( v10 >= 0 && (!a4 || a4 == 41) && a5 == 23 )
      v10 = InetInspectSocketPropertyValue(*((_QWORD *)SpinLock + 9), Source2, a7);
    v82 = (int *)*((_QWORD *)SpinLock + 10);
    if ( v82 )
    {
      v101 = *v82;
      v83 = 0;
      if ( v103 == *((_QWORD *)SpinLock + 5) )
        v83 = v82;
      v108 = v83;
    }
    else
    {
      v108 = 0;
      v101 = 1;
    }
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    if ( v10 < 0 )
      return (unsigned int)v10;
    v84 = (struct _KSPIN_LOCK_QUEUE *)ExAllocatePool2(64, 80, 1464165461);
    v135.LockQueue.Next = v84;
    v85 = v84;
    if ( !v84 )
      return (unsigned int)-1073741801;
    v84->Lock = (volatile PKSPIN_LOCK)SpinLock;
    if ( _InterlockedIncrement64((volatile signed __int64 *)SpinLock + 2) <= 1 )
      __fastfail(0xEu);
    v86 = v103;
    v87 = v107;
    v84[1].Next = v105;
    v84[1].Lock = v106;
    v88 = *((_QWORD *)SpinLock + 13);
    v89 = *((_QWORD *)SpinLock + 9);
    v113 = 0;
    v115 = 0;
    v121 = 0;
    v124 = 0;
    v127 = 0;
    v130 = 0;
    v111[0] = *(_QWORD *)(v86 + 40);
    v111[2] = v108;
    v112 = v101;
    v129 = 0;
    if ( v88 )
      v114 = *(_QWORD *)(v88 + 8);
    else
      v114 = 0;
    v90 = v102;
    v126 = UdpSetSockOptEndpointSetSessionInfoComplete;
    v123 = a9;
    v91 = *(_QWORD *)(v86 + 48);
    v116 = v87;
    v125 = v85;
    v117 = v102;
    v118 = a5;
    v119 = Source2;
    v120 = (int)a7;
    v122 = a8;
    v128 = v89;
    v111[1] = 0;
    v92 = *(__int64 (__fastcall **)(_QWORD *))(v91 + 256);
    if ( (char *)v92 == (char *)IpNlpSetSessionInfo )
      v93 = IpNlpSetSessionInfo(v111);
    else
      v93 = v92(v111);
    if ( v93 < 0 )
      goto LABEL_275;
    v94 = v109;
    v95 = v110;
    if ( v100 )
      *v100 = v123;
    if ( v95 )
      *v95 = v127;
    if ( v94 )
    {
      v10 = v93;
      *v94 = HIDWORD(v127);
    }
    else
    {
LABEL_275:
      v10 = v93;
      if ( v93 < 0 )
      {
LABEL_280:
        if ( v93 == 259 )
          return (unsigned int)v10;
        UdpSetSockOptEndpointSetSessionInfoComplete(v135.LockQueue.Next);
        return 259;
      }
    }
    if ( (!v90 || v90 == 41) && a5 == 75 )
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
0x1400b62a0  mov     [rsp-8+arg_8], rbx
0x1400b62a5  push    rbp
0x1400b62a6  push    rsi
0x1400b62a7  push    rdi
0x1400b62a8  push    r12
0x1400b62aa  push    r13
0x1400b62ac  push    r14
0x1400b62ae  push    r15
0x1400b62b0  lea     rbp, [rsp-0F0h]
0x1400b62b8  sub     rsp, 1F0h
0x1400b62bf  mov     rax, cs:__security_cookie
0x1400b62c6  xor     rax, rsp
0x1400b62c9  mov     [rbp+120h+var_38], rax
0x1400b62d0  mov     rax, [rbp+120h+arg_48]
0x1400b62d7  xor     ebx, ebx
0x1400b62d9  mov     r13, [rbp+120h+arg_38]
0x1400b62e0  xorps   xmm0, xmm0
0x1400b62e3  mov     rdi, [rbp+120h+Source2]
0x1400b62ea  mov     r12d, r9d
0x1400b62ed  mov     r15, [rbp+120h+arg_30]
0x1400b62f4  mov     r14, rcx
0x1400b62f7  mov     esi, [rbp+120h+arg_20]
0x1400b62fd  mov     [rsp+220h+var_1B8], rax
0x1400b6302  xor     eax, eax
0x1400b6304  cmp     cs:dword_1402201D4, eax
0x1400b630a  mov     [rsp+220h+var_1AC], r9d
0x1400b630f  mov     [rbp+120h+var_180], r8
0x1400b6313  mov     [rbp+120h+var_188], rdx
0x1400b6317  movups  xmmword ptr [rsp+220h+LockHandle.LockQueue.Next], xmm0
0x1400b631c  mov     qword ptr [rsp+220h+LockHandle.OldIrql], rax
0x1400b6321  jz      short loc_1400B6372
0x1400b6323  test    byte ptr cs:WPP_MAIN_CB+14Ch, 8
0x1400b632a  movups  xmmword ptr [rbp+120h+var_50.LockQueue.Next], xmm0
0x1400b6331  jz      short loc_1400B6372
0x1400b6333  mov     [rbp+120h+var_50.LockQueue.Next], rcx
0x1400b633a  lea     r8, [rbp+120h+var_50]
0x1400b6341  mov     [rsp+220h+var_1E8], rdi
0x1400b6346  lea     rdx, TCPIP_SETSOCKOPT
0x1400b634d  test    rdi, rdi
0x1400b6350  mov     ecx, r15d
0x1400b6353  cmovz   ecx, ebx
0x1400b6356  mov     dword ptr [rsp+220h+var_1F0], ecx
0x1400b635a  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x1400b6361  mov     dword ptr [rsp+220h+var_1F8], esi
0x1400b6365  mov     dword ptr [rsp+220h+var_200], r9d
0x1400b636a  mov     r9, r14
0x1400b636d  call    McTemplateK0pqqqbr3_EtwWriteTransfer
0x1400b6372  lea     rdx, [rsp+220h+LockHandle]; LockHandle
0x1400b6377  mov     rcx, r14; SpinLock
0x1400b637a  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x1400b6381  nop     dword ptr [rax+rax+00h]
0x1400b6386  mov     eax, [r14+8]
0x1400b638a  test    eax, eax
0x1400b638c  jnz     short loc_1400B6386
0x1400b638e  cmp     r12d, 11h
0x1400b6392  jnz     short loc_1400B6405
0x1400b6394  cmp     esi, 1
0x1400b6397  jnz     short loc_1400B63BF
0x1400b6399  cmp     r15, 1
0x1400b639d  jb      loc_1400B6D4E
0x1400b63a3  movzx   eax, byte ptr [rdi]
0x1400b63a6  neg     al
0x1400b63a8  mov     eax, [r14+18h]
0x1400b63ac  sbb     ecx, ecx
0x1400b63ae  and     eax, 0FFFFFFBFh
0x1400b63b1  and     ecx, 40h
0x1400b63b4  or      ecx, eax
0x1400b63b6  mov     [r14+18h], ecx
0x1400b63ba  jmp     loc_1400B6D53
0x1400b63bf  cmp     esi, 2
0x1400b63c2  jnz     short loc_1400B63E4
0x1400b63c4  cmp     r15, 4
0x1400b63c8  jb      loc_1400B6D4E
0x1400b63ce  mov     eax, [rdi]
0x1400b63d0  mov     rcx, r14
0x1400b63d3  mov     [r14+170h], eax
0x1400b63da  call    UdpCacheDefaultUsoInformation
0x1400b63df  jmp     loc_1400B6D53
0x1400b63e4  cmp     esi, 3
0x1400b63e7  jnz     loc_1400B6639
0x1400b63ed  cmp     r15, 4
0x1400b63f1  jb      loc_1400B6D4E
0x1400b63f7  mov     eax, [rdi]
0x1400b63f9  mov     [r14+180h], eax
0x1400b6400  jmp     loc_1400B6D53
0x1400b6405  mov     r9d, 0FFFFh
0x1400b640b  cmp     r12d, 29h ; ')'
0x1400b640f  jnz     short loc_1400B6449
0x1400b6411  cmp     esi, 1Bh
0x1400b6414  jnz     loc_1400B65FB
0x1400b641a  cmp     r15, 1
0x1400b641e  jb      loc_1400B6D4E
0x1400b6424  mov     edx, [r14+18h]
0x1400b6428  test    dl, 1
0x1400b642b  jnz     loc_1400B6708
0x1400b6431  movzx   eax, byte ptr [rdi]
0x1400b6434  neg     al
0x1400b6436  sbb     ecx, ecx
0x1400b6438  and     edx, 0FFFFFFEFh
0x1400b643b  and     ecx, 10h
0x1400b643e  or      ecx, edx
0x1400b6440  mov     [r14+18h], ecx
0x1400b6444  jmp     loc_1400B6D53
0x1400b6449  cmp     r12d, r9d
0x1400b644c  jnz     loc_1400B65FB
0x1400b6452  cmp     esi, 20h ; ' '
0x1400b6455  jnz     short loc_1400B6481
0x1400b6457  cmp     r15, 1
0x1400b645b  jb      loc_1400B6D4E
0x1400b6461  movzx   eax, byte ptr [rdi]
0x1400b6464  neg     al
0x1400b6466  mov     eax, [r14+18h]
0x1400b646a  sbb     ecx, ecx
0x1400b646c  btr     eax, 7
0x1400b6470  and     ecx, 80h
0x1400b6476  or      ecx, eax
0x1400b6478  mov     [r14+18h], ecx
0x1400b647c  jmp     loc_1400B6D53
0x1400b6481  cmp     esi, 4
0x1400b6484  jnz     short loc_1400B64C6
0x1400b6486  cmp     r15, 1
0x1400b648a  jb      loc_1400B6D4E
0x1400b6490  mov     edx, [r14+18h]
0x1400b6494  test    dl, 1
0x1400b6497  jnz     loc_1400B6708
0x1400b649d  test    edx, 6000h
0x1400b64a3  jnz     loc_1400B6CDB
0x1400b64a9  movzx   eax, byte ptr [rdi]
0x1400b64ac  neg     al
0x1400b64ae  mov     eax, 100h
0x1400b64b3  sbb     ecx, ecx
0x1400b64b5  btr     edx, 8
0x1400b64b9  and     ecx, eax
0x1400b64bb  or      ecx, edx
0x1400b64bd  mov     [r14+18h], ecx
0x1400b64c1  jmp     loc_1400B6D53
0x1400b64c6  cmp     esi, 3008h
0x1400b64cc  jnz     short loc_1400B650E
0x1400b64ce  cmp     r15, 1
0x1400b64d2  jb      loc_1400B6D4E
0x1400b64d8  mov     edx, [r14+18h]
0x1400b64dc  test    dl, 1
0x1400b64df  jnz     loc_1400B6708
0x1400b64e5  test    edx, 2300h
0x1400b64eb  jnz     loc_1400B6CDB
0x1400b64f1  movzx   eax, byte ptr [rdi]
0x1400b64f4  neg     al
0x1400b64f6  mov     eax, 4000h
0x1400b64fb  sbb     ecx, ecx
0x1400b64fd  btr     edx, 0Eh
0x1400b6501  and     ecx, eax
0x1400b6503  or      ecx, edx
0x1400b6505  mov     [r14+18h], ecx
0x1400b6509  jmp     loc_1400B6D53
0x1400b650e  cmp     esi, 0FFFFFFFBh
0x1400b6511  jnz     short loc_1400B6550
0x1400b6513  cmp     r15, 1
0x1400b6517  jb      loc_1400B6D4E
0x1400b651d  mov     edx, [r14+18h]
0x1400b6521  test    dl, 1
0x1400b6524  jnz     loc_1400B6708
0x1400b652a  bt      edx, 0Eh
0x1400b652e  jb      loc_1400B6CDB
0x1400b6534  movzx   eax, byte ptr [rdi]
0x1400b6537  neg     al
0x1400b6539  sbb     ecx, ecx
0x1400b653b  btr     edx, 9
0x1400b653f  and     ecx, 200h
0x1400b6545  or      ecx, edx
0x1400b6547  mov     [r14+18h], ecx
0x1400b654b  jmp     loc_1400B6D53
0x1400b6550  cmp     esi, 3005h
0x1400b6556  jnz     short loc_1400B658E
0x1400b6558  cmp     r15, 1
0x1400b655c  jb      loc_1400B6D4E
0x1400b6562  mov     edx, [r14+18h]
0x1400b6566  test    dl, 1
0x1400b6569  jnz     loc_1400B6708
0x1400b656f  movzx   eax, byte ptr [rdi]
0x1400b6572  mov     r8d, 400h
0x1400b6578  neg     al
0x1400b657a  sbb     ecx, ecx
0x1400b657c  btr     edx, 0Ah
0x1400b6580  and     ecx, r8d
0x1400b6583  or      ecx, edx
0x1400b6585  mov     [r14+18h], ecx
0x1400b6589  jmp     loc_1400B6D53
0x1400b658e  cmp     esi, 3004h
0x1400b6594  jz      loc_1400B6D53
0x1400b659a  cmp     esi, 10h
0x1400b659d  jnz     short loc_1400B65C9
0x1400b659f  cmp     r15, 1
0x1400b65a3  jb      loc_1400B6D4E
0x1400b65a9  movzx   eax, byte ptr [rdi]
0x1400b65ac  neg     al
0x1400b65ae  mov     eax, [r14+18h]
0x1400b65b2  sbb     ecx, ecx
0x1400b65b4  btr     eax, 0Ch
0x1400b65b8  and     ecx, 1000h
0x1400b65be  or      ecx, eax
0x1400b65c0  mov     [r14+18h], ecx
0x1400b65c4  jmp     loc_1400B6D53
0x1400b65c9  cmp     esi, 3011h
0x1400b65cf  jnz     short loc_1400B65FB
0x1400b65d1  cmp     r15, 1
0x1400b65d5  jb      loc_1400B6D4E
0x1400b65db  mov     edx, [r14+18h]
0x1400b65df  movzx   eax, byte ptr [rdi]
0x1400b65e2  btr     edx, 13h
0x1400b65e6  neg     al
0x1400b65e8  sbb     ecx, ecx
0x1400b65ea  and     ecx, 80000h
0x1400b65f0  or      edx, ecx
0x1400b65f2  mov     [r14+18h], edx
0x1400b65f6  jmp     loc_1400B6D53
0x1400b65fb  cmp     r12d, 0FFFCh
0x1400b6602  jnz     loc_1400B7360
0x1400b6608  cmp     esi, 980000EBh
0x1400b660e  jnz     loc_1400B66EE
0x1400b6614  cmp     r15, 8
0x1400b6618  jb      loc_1400B6D4E
0x1400b661e  mov     ecx, [rdi]
0x1400b6620  mov     eax, ecx
0x1400b6622  and     eax, 0FFFFFFFCh
0x1400b6625  mov     [rdi], eax
0x1400b6627  jnz     short loc_1400B6639
0x1400b6629  mov     edx, ecx
0x1400b662b  and     edx, 2
0x1400b662e  jz      short loc_1400B665A
0x1400b6630  movzx   eax, word ptr [rdi+4]
0x1400b6634  test    ax, ax
0x1400b6637  jnz     short loc_1400B6643
0x1400b6639  mov     ebx, 0C000000Dh
0x1400b663e  jmp     loc_1400B6D53
0x1400b6643  mov     r8, [r14+168h]
0x1400b664a  test    r8, r8
0x1400b664d  jz      short loc_1400B665A
0x1400b664f  cmp     ax, [r8+12h]
0x1400b6654  jnz     loc_1400B6CDB
0x1400b665a  mov     eax, [r14+18h]
0x1400b665e  shl     ecx, 12h
0x1400b6661  xor     ecx, eax
0x1400b6663  and     ecx, 40000h
0x1400b6669  xor     ecx, eax
0x1400b666b  mov     rax, [r14+168h]
0x1400b6672  mov     [r14+18h], ecx
0x1400b6676  test    edx, edx
0x1400b6678  jz      short loc_1400B66D4
0x1400b667a  test    rax, rax
0x1400b667d  jnz     loc_1400B6D53
0x1400b6683  movzx   ebx, word ptr [rdi+4]
0x1400b6687  mov     edx, 18h
0x1400b668c  mov     ecx, 40h ; '@'
0x1400b6691  mov     r8d, 54706455h
0x1400b6697  call    cs:__imp_ExAllocatePool2
0x1400b669e  nop     dword ptr [rax+rax+00h]
0x1400b66a3  mov     rcx, rax
0x1400b66a6  test    rax, rax
0x1400b66a9  jnz     short loc_1400B66B5
0x1400b66ab  mov     ebx, 0C000009Ah
0x1400b66b0  jmp     loc_1400B6D53
0x1400b66b5  mov     [rax+8], rcx
0x1400b66b9  mov     [rax], rcx
0x1400b66bc  xor     eax, eax
0x1400b66be  mov     [rcx+12h], bx
0x1400b66c2  xor     ebx, ebx
0x1400b66c4  mov     [rcx+10h], ax
0x1400b66c8  mov     [r14+168h], rcx
0x1400b66cf  jmp     loc_1400B6D53
0x1400b66d4  test    rax, rax
0x1400b66d7  jz      loc_1400B6D53
0x1400b66dd  lea     rcx, [r14+168h]
0x1400b66e4  call    UdpUninitTimestampQueue
0x1400b66e9  jmp     loc_1400B6D53
0x1400b66ee  cmp     esi, 98000015h
0x1400b66f4  jnz     short loc_1400B6735
0x1400b66f6  cmp     r15, 2
0x1400b66fa  jb      loc_1400B6D4E
0x1400b6700  mov     eax, [r14+18h]
0x1400b6704  test    al, 1
0x1400b6706  jz      short loc_1400B6712
0x1400b6708  mov     ebx, 0C0000238h
0x1400b670d  jmp     loc_1400B6D53
0x1400b6712  test    eax, 4100h
0x1400b6717  jnz     loc_1400B6CDB
0x1400b671d  bts     eax, 0Dh
0x1400b6721  mov     [r14+18h], eax
0x1400b6725  movzx   eax, word ptr [rdi]
0x1400b6728  mov     [r14+0AAh], ax
0x1400b6730  jmp     loc_1400B6D53
0x1400b6735  cmp     esi, 8800000Bh
0x1400b673b  jz      loc_1400B6E78
0x1400b6741  cmp     esi, 8800001Ah
0x1400b6747  jz      loc_1400B6E78
0x1400b674d  cmp     esi, 98000022h
0x1400b6753  jnz     short loc_1400B676B
0x1400b6755  mov     rcx, [r14+48h]
0x1400b6759  mov     r8, r15
0x1400b675c  mov     rdx, rdi
0x1400b675f  call    InetInspectFirewallSystemPort
  ... truncated ...
```
