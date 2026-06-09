# TcpSetSockOptTcb

- ea: `0x14005a740`
- end: `0x14005b87c`
- name: `TcpSetSockOptTcb`
- size: `4412`
- prototype: `__int64 __usercall@<rax>(PKSPIN_LOCK SpinLock@<rcx>, __int64, void *, __int64, __int64)`
- caller_count: `1`
- callee_count: `37`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14005a610`

## callees

- `0x140004070`
- `0x140005410`
- `0x1400090b0`
- `0x14000c800`
- `0x14000de40`
- `0x140012f00`
- `0x14003de00`
- `0x14003de94`
- `0x140042f10`
- `0x140044880`
- `0x140047710`
- `0x140057aec`
- `0x140059590`
- `0x1400599a4`
- `0x14005a740`
- `0x1400d7f90`
- `0x1400d9aa0`
- `0x1400e7280`
- `0x1400e7354`
- `0x1400e8424`
- `0x1400e8ab4`
- `0x1400e9a10`
- `0x1400ea1c0`
- `0x1400f8710`
- `0x140112da4`
- `0x14011b110`
- `0x14011cbf4`
- `0x140128560`
- `0x14012a5bc`
- `0x1401524c0`
- `0x140153538`
- `0x1401615fc`
- `0x140172a5c`
- `0x1401c0fd0`
- `0x1401c1200`
- `0x1401c1280`
- `0x1401c1580`

## import_xrefs

- `ntoskrnl!KeLowerIrql` at `0x14005b103`
- `ntoskrnl!KeLowerIrql` at `0x14005b103`
- `ntoskrnl!IoFileObjectType` at `0x1401c7fd6`
- `ntoskrnl!KeQuerySystemTimePrecise` at `0x14005a947`
- `ntoskrnl!KeQuerySystemTimePrecise` at `0x14005a947`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14005b0d0`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14005b0d0`
- `ntoskrnl!RtlCompareMemory` at `0x14005b30f`
- `ntoskrnl!RtlCompareMemory` at `0x14005b33f`
- `ntoskrnl!RtlCompareMemory` at `0x14005b3e1`
- `ntoskrnl!RtlCompareMemory` at `0x14005b521`
- `ntoskrnl!RtlCompareMemory` at `0x14005b761`
- `ntoskrnl!RtlCompareMemory` at `0x14005b30f`
- `ntoskrnl!RtlCompareMemory` at `0x14005b33f`
- `ntoskrnl!RtlCompareMemory` at `0x14005b3e1`
- `ntoskrnl!RtlCompareMemory` at `0x14005b521`
- `ntoskrnl!RtlCompareMemory` at `0x14005b761`
- `ntoskrnl!PsGetProcessId` at `0x1401c812c`
- `ntoskrnl!PsGetProcessId` at `0x1401c812c`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1401c7ffd`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1401c7ffd`
- `ntoskrnl!ObfDereferenceObject` at `0x1401c8081`
- `ntoskrnl!ObfDereferenceObject` at `0x1401c8081`
- `ntoskrnl!KeReleaseSpinLock` at `0x14005ab35`
- `ntoskrnl!KeReleaseSpinLock` at `0x14005b201`
- `ntoskrnl!KeReleaseSpinLock` at `0x14005b244`
- `ntoskrnl!KeReleaseSpinLock` at `0x14005b394`
- `ntoskrnl!KeReleaseSpinLock` at `0x14005b583`
- `ntoskrnl!KeReleaseSpinLock` at `0x14005b5fd`
- `ntoskrnl!KeReleaseSpinLock` at `0x14005b655`
- `ntoskrnl!KeReleaseSpinLock` at `0x1401c7fca`
- `ntoskrnl!KeReleaseSpinLock` at `0x14005ab35`
- `ntoskrnl!KeReleaseSpinLock` at `0x14005b201`
- `ntoskrnl!KeReleaseSpinLock` at `0x14005b244`
- `ntoskrnl!KeReleaseSpinLock` at `0x14005b394`
- `ntoskrnl!KeReleaseSpinLock` at `0x14005b583`
- `ntoskrnl!KeReleaseSpinLock` at `0x14005b5fd`
- `ntoskrnl!KeReleaseSpinLock` at `0x14005b655`
- `ntoskrnl!KeReleaseSpinLock` at `0x1401c7fca`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14005a7b0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1401c800f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14005a7b0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1401c800f`
- `NETIO!NetioNcmTlObjectRequest` at `0x14005b42e`
- `NETIO!NetioNcmTlObjectRequest` at `0x14005b42e`
- `NETIO!NetioNrtAssociateContext` at `0x1401c8050`
- `NETIO!NetioNrtAssociateContext` at `0x1401c8050`
- `NETIO!NetioNrtIsTrackerDevice` at `0x1401c802d`
- `NETIO!NetioNrtIsTrackerDevice` at `0x1401c802d`

## pseudocode

```c
__int64 __fastcall TcpSetSockOptTcb(
        char *SpinLock,
        int a2,
        unsigned int a3,
        _BYTE *a4,
        unsigned __int64 a5,
        int *a6,
        unsigned __int64 a7,
        void *a8)
{
  unsigned __int64 v12; // rsi
  char v13; // al
  NTSTATUS v14; // r14d
  __int64 v15; // rax
  size_t v16; // rdi
  __int64 v17; // rcx
  int v18; // r15d
  int v19; // r12d
  int v20; // esi
  __int64 v21; // rdx
  __int64 v22; // rcx
  bool v23; // al
  unsigned __int64 v24; // rcx
  int v25; // eax
  unsigned __int64 v26; // rcx
  unsigned __int8 v27; // cf
  KIRQL v28; // r12
  KIRQL v29; // dl
  int v31; // eax
  int v32; // r9d
  unsigned int v33; // r8d
  PKSPIN_LOCK v34; // rsi
  int v35; // edx
  unsigned int v36; // edi
  unsigned __int64 v37; // rax
  unsigned int LockArray_high; // edi
  unsigned __int64 MicrosecondCount; // rax
  PKSPIN_LOCK v40; // rax
  KSPIN_LOCK v41; // r10
  __int64 *v42; // rdx
  KSPIN_LOCK v43; // r8
  KSPIN_LOCK v44; // r9
  __int64 v45; // rcx
  _QWORD *v46; // r11
  __int64 v47; // rax
  __int64 (__fastcall *v48)(_BYTE *); // rax
  int v49; // eax
  char v50; // al
  __int64 v51; // rdx
  unsigned int v52; // ecx
  __int16 v53; // r13
  unsigned int v54; // r12d
  int v55; // ecx
  _QWORD *v56; // rcx
  unsigned int v57; // r15d
  __int64 v58; // rax
  char v59; // cl
  unsigned __int64 v60; // rdi
  unsigned int v61; // eax
  int v62; // r13d
  bool v63; // cc
  __int16 *v64; // rcx
  unsigned int v65; // eax
  KSPIN_LOCK v66; // rax
  int v67; // eax
  KSPIN_LOCK v68; // rcx
  NTSTATUS v69; // eax
  int v70; // ecx
  __int64 inserted; // rax
  _QWORD *v72; // rcx
  __int64 v73; // rsi
  void *v74; // rcx
  int v75; // edx
  _QWORD *v76; // rdi
  __int64 v77; // rdx
  char ProcessId; // al
  __int16 v79; // dx
  char v80; // r9
  __int16 v81; // r10
  char v82; // di
  char v83; // r11
  __int16 v84; // ax
  int v85; // r8d
  int v86; // ecx
  int v87; // esi
  int v88; // eax
  char v89; // dl
  bool v90; // r8
  int SessionInformationAf; // eax
  int v92; // ecx
  __int64 v93; // rdx
  char Object; // [rsp+20h] [rbp-E0h]
  char v95; // [rsp+40h] [rbp-C0h]
  KIRQL v96; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v97[7]; // [rsp+71h] [rbp-8Fh] BYREF
  PVOID v98; // [rsp+78h] [rbp-88h] BYREF
  __int64 v99; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v100; // [rsp+88h] [rbp-78h]
  _QWORD v101[2]; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v102; // [rsp+B0h] [rbp-50h]
  __int128 v103; // [rsp+C0h] [rbp-40h]
  __int128 v104; // [rsp+D0h] [rbp-30h]
  _BYTE Src[144]; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v106; // [rsp+170h] [rbp+70h]
  size_t Size[2]; // [rsp+180h] [rbp+80h] BYREF

  v98 = a8;
  v97[0] = 0;
  if ( dword_1402241D4 && (BYTE4(WPP_MAIN_CB.Dpc.DeferredContext) & 8) != 0 )
  {
    Size[1] = 0;
    v55 = a5;
    Size[0] = (size_t)SpinLock;
    if ( !a4 )
      v55 = 0;
    McTemplateK0pqqqbr3_EtwWriteTransfer(
      (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
      (unsigned int)TCPIP_SETSOCKOPT,
      (unsigned int)Size,
      (_DWORD)SpinLock,
      a2,
      a3,
      v55,
      (__int64)a4);
  }
  v96 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)SpinLock);
  if ( a2 == 6 )
  {
    if ( dword_1402241D4
      && (!TcpipTraceFiltersExist || SpinLock[804] < 0)
      && (BYTE3(WPP_MAIN_CB.Dpc.DeferredRoutine) & 0x20) != 0 )
    {
      Size[1] = 0;
      Size[0] = (size_t)SpinLock;
      McTemplateK0pqq_EtwWriteTransfer(
        (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
        (unsigned int)TCP_SET_TCP_OPTION,
        (unsigned int)Size,
        (_DWORD)SpinLock,
        a3,
        0);
    }
    if ( ((a3 - 2) & 0xFFFFFFFA) != 0
      || a3 == 3
      || !(unsigned __int8)TcpHasUrgentTcbInput(SpinLock) && (*((_DWORD *)SpinLock + 30) & 0x800) == 0 )
    {
      if ( a3 > 0xF || (v31 = 37888, !_bittest(&v31, a3)) )
      {
        v14 = TcpSetTcpLevelOption((int)SpinLock + 760, a3, (_DWORD)a4, a5, (__int64)v97);
        if ( v14 < 0 || !v97[0] || (*((_DWORD *)SpinLock + 31) & 2) != 0 )
          goto LABEL_66;
        if ( a3 != 3 )
        {
          if ( a3 == 5 || a3 == 14 )
          {
            v29 = v96;
            *((_DWORD *)SpinLock + 187) = 0;
            goto LABEL_36;
          }
          goto LABEL_66;
        }
LABEL_79:
        if ( (SpinLock[794] & 4) != 0 )
        {
          SpinLock[754] = 0;
          LockArray_high = HIDWORD(KeGetPcr()[1].LockArray);
          MicrosecondCount = TcpQueryMicrosecondCount(LockArray_high, 0);
          TcpStartTimerTcbInternal(
            (_DWORD)SpinLock,
            4,
            *((_DWORD *)SpinLock + 191),
            MicrosecondCount / 0x3E8,
            LockArray_high,
            4);
          v29 = v96;
          goto LABEL_36;
        }
        if ( (*((_DWORD *)SpinLock + 202) & 0x40) == 0 )
          TcpStopTimerTcbInternal(SpinLock, 4, 4);
        goto LABEL_66;
      }
    }
    goto LABEL_83;
  }
  if ( a2 == 0xFFFF )
  {
    if ( ((a3 - 12293) & 0xFFFFFFFD) == 0 )
      goto LABEL_155;
    if ( dword_1402241D4
      && (!TcpipTraceFiltersExist || SpinLock[804] < 0)
      && (BYTE3(WPP_MAIN_CB.Dpc.DeferredRoutine) & 0x20) != 0 )
    {
      Size[1] = 0;
      Size[0] = (size_t)SpinLock;
      McTemplateK0pqq_EtwWriteTransfer(
        (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
        (unsigned int)TCP_SET_TCP_SO_OPTION,
        (unsigned int)Size,
        (_DWORD)SpinLock,
        0,
        a3);
    }
    if ( a3 != 256 )
    {
      if ( a3 == 4098 )
      {
        if ( a5 >= 4 )
        {
          v32 = *((_DWORD *)SpinLock + 28);
          v33 = *(_DWORD *)a4;
          if ( v32 >= 2 && v33 > 0xFFFF << SpinLock[801] )
          {
            KeReleaseSpinLock((PKSPIN_LOCK)SpinLock, v96);
            return (unsigned int)-1073741436;
          }
          v34 = (PKSPIN_LOCK)(SpinLock + 760);
          if ( v32 >= 4 && v33 < *(_DWORD *)v34 && SpinLock[795] >= 0 )
          {
            v29 = v96;
            v14 = 0;
            v97[0] = 0;
            goto LABEL_36;
          }
          v35 = 4098;
          goto LABEL_65;
        }
        v14 = -1073741306;
LABEL_84:
        v29 = v96;
        v97[0] = 0;
        goto LABEL_36;
      }
LABEL_87:
      v34 = (PKSPIN_LOCK)(SpinLock + 760);
      v35 = a3;
LABEL_65:
      v14 = TcpSetSoLevelOption((_DWORD)v34, v35, (_DWORD)a4, a5, (__int64)v97);
      if ( v14 < 0 || !v97[0] || (*((_DWORD *)SpinLock + 31) & 2) != 0 )
        goto LABEL_66;
      if ( a3 != 8 )
      {
        if ( a3 == 4098 )
        {
          *((_DWORD *)SpinLock + 30) |= 0x400u;
          v57 = HIDWORD(KeGetPcr()[1].LockArray);
          v58 = TcpQueryMicrosecondCount(v57, 0);
          v59 = SpinLock[801];
          v60 = v58;
          v61 = *(_DWORD *)v34;
          if ( *(_DWORD *)v34 >= (unsigned int)(0xFFFF << v59) )
            v61 = 0xFFFF << v59;
          v62 = 1 << v59;
          if ( v61 > 1 << v59 )
            v62 = v61;
          v63 = *((_DWORD *)SpinLock + 28) < 4;
          *(_DWORD *)v34 = v62;
          if ( !v63 )
          {
            if ( (unsigned __int8)TcpTryToIncreaseTcbRcvWnd(SpinLock, v57, 0) )
            {
              KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)SpinLock);
              TcpFlushDelay(v57, v60 / 0x3E8);
              KeLowerIrql(v96);
              return (unsigned int)v14;
            }
          }
        }
        goto LABEL_66;
      }
      goto LABEL_79;
    }
    if ( !(unsigned __int8)TcpHasUrgentTcbInput(SpinLock) && (*((_DWORD *)SpinLock + 30) & 0x800) == 0 )
      goto LABEL_87;
LABEL_83:
    v14 = -1073741436;
    goto LABEL_84;
  }
  if ( a2 != 65532 )
  {
    if ( a2 != 41 || a3 != 27 )
      goto LABEL_89;
LABEL_155:
    KeReleaseSpinLock((PKSPIN_LOCK)SpinLock, v96);
    return (unsigned int)-1073741256;
  }
  switch ( a3 )
  {
    case 0x98000004:
    case 0x9800012C:
      goto LABEL_20;
    case 0x98000010:
      goto LABEL_132;
    case 0x98000011:
      goto LABEL_18;
  }
  if ( a3 + 1744830445 <= 1 )
    goto LABEL_20;
  if ( a3 == -1744830446 )
  {
LABEL_132:
    v12 = a7;
    v13 = 0;
    v97[0] = 0;
    v14 = -1073741637;
LABEL_21:
    if ( a3 == -671088601 )
    {
      v99 = 0;
      *(_WORD *)&Src[17] = 0;
      Src[19] = 0;
      *(_WORD *)&Src[85] = 0;
      Src[87] = 0;
      *(_WORD *)&Src[141] = 0;
      Src[143] = 0;
      Size[0] = 0x8800000058LL;
      LODWORD(Size[1]) = 152;
      if ( a4 )
      {
        if ( a5 == 4 )
        {
          v15 = *(unsigned int *)a4;
          if ( (unsigned int)v15 < 3 )
          {
            if ( a6 )
            {
              v16 = *((unsigned int *)Size + v15);
              if ( v12 >= v16 )
              {
                KeQuerySystemTimePrecise(&v99);
                v17 = v99 - *((_QWORD *)SpinLock + 109);
                v18 = *((_DWORD *)SpinLock + 103);
                v19 = *((_DWORD *)SpinLock + 107);
                v20 = *((_DWORD *)SpinLock + 99);
                *(_DWORD *)Src = *((_DWORD *)SpinLock + 28);
                *(_DWORD *)&Src[4] = *((_DWORD *)SpinLock + 44);
                v21 = (unsigned __int128)(v17 * (__int128)0x346DC5D63886594BLL) >> 64;
                *(_DWORD *)&Src[28] = *((_DWORD *)SpinLock + 36) - *((_DWORD *)SpinLock + 34);
                v22 = *(unsigned int *)&Src[28];
                LODWORD(v22) = HIDWORD(KeGetPcr()[1].LockArray);
                *(_DWORD *)&Src[92] = v18;
                v23 = (SpinLock[793] & 4) != 0;
                *(_QWORD *)&Src[8] = ((unsigned __int64)v21 >> 63) + (v21 >> 11);
                Src[16] = v23;
                *(_DWORD *)&Src[20] = *((_DWORD *)SpinLock + 178) >> 3;
                *(_DWORD *)&Src[24] = *((_DWORD *)SpinLock + 180);
                *(_DWORD *)&Src[32] = *((_DWORD *)SpinLock + 49);
                *(_DWORD *)&Src[36] = *((_DWORD *)SpinLock + 40);
                *(_DWORD *)&Src[40] = *((_DWORD *)SpinLock + 136);
                *(_DWORD *)&Src[44] = *((_DWORD *)SpinLock + 190);
                *(_QWORD *)&Src[48] = *((_QWORD *)SpinLock + 48);
                *(_QWORD *)&Src[56] = *((_QWORD *)SpinLock + 64);
                *(_DWORD *)&Src[64] = *((_DWORD *)SpinLock + 286);
                *(_DWORD *)&Src[68] = *((_DWORD *)SpinLock + 280);
                *(_DWORD *)&Src[72] = *((_DWORD *)SpinLock + 281);
                *(_DWORD *)&Src[76] = *((_DWORD *)SpinLock + 282);
                *(_DWORD *)&Src[80] = *((_DWORD *)SpinLock + 283);
                Src[84] = SpinLock[1140];
                *(_DWORD *)&Src[88] = *((_DWORD *)SpinLock + 102);
                *(_QWORD *)&Src[96] = *((_QWORD *)SpinLock + 52);
                *(_DWORD *)&Src[104] = *((_DWORD *)SpinLock + 106);
                *(_QWORD *)&Src[112] = *((_QWORD *)SpinLock + 54);
                *(_DWORD *)&Src[120] = *((_DWORD *)SpinLock + 98);
                *(_QWORD *)&Src[128] = *((_QWORD *)SpinLock + 50);
                *(_DWORD *)&Src[108] = v19;
                *(_DWORD *)&Src[124] = v20;
                v24 = TcpQueryMicrosecondCount(v22, 0);
                v25 = *((_DWORD *)SpinLock + 125);
                v26 = v24 / 0x3E8;
                if ( v25 )
                {
                  if ( v25 == 1 )
                  {
                    *(_DWORD *)&Src[92] = v18 + v26 - *((_DWORD *)SpinLock + 110);
                  }
                  else if ( v25 == 2 )
                  {
                    *(_DWORD *)&Src[108] = v19 + v26 - *((_DWORD *)SpinLock + 110);
                  }
                }
                else
                {
                  *(_DWORD *)&Src[124] = v20 + v26 - *((_DWORD *)SpinLock + 110);
                }
                v27 = _bittest16((const signed __int16 *)SpinLock + 64, 0xDu);
                *(_DWORD *)&Src[136] = *((_DWORD *)SpinLock + 288);
                Src[140] = v27 && (*((_DWORD *)SpinLock + 202) & 0x400) != 0;
                LODWORD(v106) = *((_DWORD *)SpinLock + 289);
                HIDWORD(v106) = *((_DWORD *)SpinLock + 284);
                memmove(a6, Src, v16);
                v28 = v96;
                if ( v98 )
                  *(_QWORD *)v98 = v16;
                goto LABEL_35;
              }
              goto LABEL_131;
            }
            goto LABEL_185;
          }
        }
      }
      goto LABEL_183;
    }
    if ( a3 > 0x98000014 )
    {
      switch ( a3 )
      {
        case 0x98000016:
          if ( v14 < 0 || !v13 || (*((_DWORD *)SpinLock + 31) & 2) != 0 )
            goto LABEL_75;
          if ( SpinLock[786] )
          {
            v64 = (__int16 *)(SpinLock + 782);
            v65 = *((_DWORD *)SpinLock + 44) * *((unsigned __int16 *)SpinLock + 391);
            if ( *((_DWORD *)SpinLock + 49) < v65 )
              *((_DWORD *)SpinLock + 49) = v65;
          }
          else
          {
            if ( ((((int)(*((_DWORD *)SpinLock + 189) << 8) >> 8) - 5) & 0xFFFFFFFD) != 0 )
              *((_WORD *)SpinLock + 391) = *((_WORD *)&TcpTemplates
                                           + 10 * ((__int64)(int)(*((_DWORD *)SpinLock + 189) << 8) >> 8)
                                           + 2);
            v64 = (__int16 *)(SpinLock + 782);
          }
          if ( !dword_1402241D4
            || TcpipTraceFiltersExist && SpinLock[804] >= 0
            || (BYTE3(WPP_MAIN_CB.Dpc.DeferredRoutine) & 0x10) == 0 )
          {
            goto LABEL_75;
          }
          v79 = *v64;
          break;
        case 0x98000017:
          if ( v14 < 0 || !v13 || (*((_DWORD *)SpinLock + 31) & 2) != 0 )
            goto LABEL_75;
          if ( !*((_WORD *)SpinLock + 406) )
            TcpTcbSelectDelAckParameters(SpinLock);
          if ( !dword_1402241D4
            || TcpipTraceFiltersExist && SpinLock[804] >= 0
            || (BYTE3(WPP_MAIN_CB.Dpc.DeferredRoutine) & 0x10) == 0 )
          {
            goto LABEL_75;
          }
          v79 = *((_WORD *)SpinLock + 391);
          break;
        case 0x98000018:
          if ( v12 >= 8 )
          {
            v14 = 0;
            v56 = v98;
            v28 = v96;
            *a6 = (unsigned __int8)SpinLock[796] >> 5;
            a6[1] = ((unsigned __int8)~SpinLock[798] >> 4) & 2;
            if ( v56 )
              *v56 = 8;
            goto LABEL_35;
          }
LABEL_131:
          v28 = v96;
          v14 = -1073741789;
          goto LABEL_35;
        default:
          goto LABEL_75;
      }
      v80 = SpinLock[787];
      v81 = *((_WORD *)SpinLock + 392);
      v82 = SpinLock[792] & 7;
      v83 = SpinLock[788];
      v84 = *((_WORD *)SpinLock + 389);
      v85 = ((unsigned __int8)SpinLock[796] >> 1) & 1;
      v86 = (int)(*((_DWORD *)SpinLock + 189) << 8) >> 8;
      v87 = ((unsigned __int8)SpinLock[797] >> 3) & 1;
      Size[0] = (size_t)SpinLock;
      Size[1] = 0;
      McTemplateK0pqqqqqqqqqq_EtwWriteTransfer(
        (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
        (unsigned int)TCP_TEMPLATE_PARAMETERS,
        (unsigned int)Size,
        (_DWORD)SpinLock,
        v86,
        v84,
        v85,
        v79,
        v82,
        v83,
        v81,
        v80,
        1,
        v87);
      goto LABEL_75;
    }
    if ( a3 != -1744830444 )
    {
      switch ( a3 )
      {
        case 0x98000004:
          if ( v14 >= 0 && v13 && (*((_DWORD *)SpinLock + 31) & 2) == 0 )
          {
            if ( (SpinLock[794] & 4) != 0 )
            {
              SpinLock[754] = 0;
              v36 = HIDWORD(KeGetPcr()[1].LockArray);
              v37 = TcpQueryMicrosecondCount(v36, 0);
              TcpStartTimerTcbInternal((_DWORD)SpinLock, 4, *((_DWORD *)SpinLock + 191), v37 / 0x3E8, v36, 4);
            }
            else if ( (*((_DWORD *)SpinLock + 202) & 0x40) == 0 )
            {
              TcpStopTimerTcbInternal(SpinLock, 4, 4);
              v28 = v96;
              goto LABEL_35;
            }
          }
          break;
        case 0x58000028u:
          v28 = v96;
          if ( v12 >= 4 )
            *a6 = *((_DWORD *)SpinLock + 287);
          else
            v14 = -1073741789;
          goto LABEL_35;
        case 0x98000013:
          if ( !a4 || a5 < 0x10 )
            goto LABEL_185;
          if ( RtlCompareMemory(&ASSOCIATE_NAMERES_CONTEXT, a4, 0x10u) == 16 )
          {
            if ( a5 >= 0x18 )
            {
              LOBYTE(v73) = 0;
              KeReleaseSpinLock((PKSPIN_LOCK)SpinLock, v96);
              v74 = (void *)*((_QWORD *)a4 + 2);
              v98 = 0;
              v14 = ObReferenceObjectByHandle(v74, 0, (POBJECT_TYPE)IoFileObjectType, 1, &v98, 0);
              v28 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)SpinLock);
              if ( v14 >= 0 )
              {
                v76 = v98;
                if ( (unsigned __int8)NetioNrtIsTrackerDevice(*((_QWORD *)v98 + 1)) )
                {
                  v73 = v76[3];
                  LOBYTE(v77) = 1;
                  v14 = NetioNrtAssociateContext(SpinLock, v77, v73, SpinLock + 1112);
                  if ( v14 >= 0 )
                    WfpAleOnProxyHandleChanged(*((_QWORD *)SpinLock + 113), *((_QWORD *)SpinLock + 139));
                }
                else
                {
                  v14 = -1073741816;
                }
                ObfDereferenceObject(v76);
              }
              if ( dword_1402241D4
                && (!TcpipTraceFiltersExist || SpinLock[804] < 0)
                && (BYTE2(WPP_MAIN_CB.Dpc.DeferredContext) & 0x20) != 0 )
              {
                Size[1] = 0;
                Size[0] = (size_t)SpinLock;
                McTemplateK0pqpq_EtwWriteTransfer(
                  (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
                  v75,
                  (unsigned int)Size,
                  (_DWORD)SpinLock,
                  1,
                  v73,
                  v14);
              }
              goto LABEL_35;
            }
            goto LABEL_185;
          }
          if ( a5 < 0x20 )
          {
LABEL_185:
            v28 = v96;
            v14 = -1073741306;
            goto LABEL_35;
          }
          if ( RtlCompareMemory(&REAL_TIME_NOTIFICATION_CAPABILITY_EX, a4, 0x10u) == 16 )
          {
            if ( a5 < 0x24 )
              goto LABEL_185;
            if ( a4[32] )
            {
              v28 = v96;
              v14 = TcpTcbProcessNotificationChannelUnmarkRequest((PKSPIN_LOCK)SpinLock);
              goto LABEL_35;
            }
LABEL_216:
            v28 = v96;
            v14 = TcpTcbProcessNotificationChannelSetupRequest((PKSPIN_LOCK)SpinLock);
            goto LABEL_35;
          }
          if ( RtlCompareMemory(&REAL_TIME_NOTIFICATION_CAPABILITY, a4, 0x10u) == 16 )
            goto LABEL_216;
LABEL_183:
          v14 = -1073741811;
          break;
      }
LABEL_75:
      v28 = v96;
LABEL_35:
      v29 = v28;
LABEL_36:
      KeReleaseSpinLock((PKSPIN_LOCK)SpinLock, v29);
      return (unsigned int)v14;
    }
    if ( !a4 || !a6 || a5 < 0x10 || v12 < 4 )
      goto LABEL_185;
    if ( RtlCompareMemory(&REAL_TIME_NOTIFICATION_CAPABILITY, a4, 0x10u) != 16
      && RtlCompareMemory(&REAL_TIME_NOTIFICATION_CAPABILITY_EX, a4, 0x10u) != 16 )
    {
      goto LABEL_183;
    }
    v66 = *((_QWORD *)SpinLock + 5);
    if ( v66 )
    {
      v101[1] = 0;
      v102 = 0;
      v103 = 0;
      v104 = 0;
      v101[0] = v66;
      NetioNcmTlObjectRequest(v101, 2);
      v67 = DWORD2(v103);
      *a6 = DWORD2(v103);
      if ( (unsigned int)(v67 - 1) > 1 )
      {
LABEL_166:
        if ( v14 >= 0 && v98 )
          *(_QWORD *)v98 = 4;
        goto LABEL_169;
      }
      if ( *((_DWORD *)SpinLock + 28) == 4 )
      {
        if ( (*((_DWORD *)SpinLock + 202) & 0xE0000) != 0 )
          TcpTcbSignalNotificationChannelEvent(SpinLock, 0, 0, 0);
        goto LABEL_166;
      }
    }
    else if ( *((_DWORD *)SpinLock + 28) == 4 )
    {
      v14 = -1073741637;
LABEL_169:
      if ( dword_1402241D4 && (!TcpipTraceFiltersExist || SpinLock[804] < 0) )
      {
        *(_OWORD *)Size = 0;
        if ( ((__int64)WPP_MAIN_CB.Dpc.DeferredContext & 1) != 0 )
        {
          ProcessId = (unsigned __int8)PsGetProcessId(*((PEPROCESS *)SpinLock + 106));
          v95 = *a6;
          Object = *((_QWORD *)SpinLock + 5);
          Size[1] = 0;
          Size[0] = (size_t)SpinLock;
          McTemplateK0ppqqqqq_EtwWriteTransfer(
            (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
            (unsigned int)TCP_QUERY_NOTIFICATION_CHANNEL_STATUS_REQUEST,
            (unsigned int)Size,
            (_DWORD)SpinLock,
            Object,
            0,
            ProcessId,
            0,
            v95,
            v14);
        }
      }
      goto LABEL_75;
    }
    *a6 = 5;
    goto LABEL_166;
  }
  if ( a3 == -671088601 || a3 == 1476395048 || a3 + 1744830442 <= 1 )
    goto LABEL_20;
  switch ( a3 )
  {
    case 0x8800000B:
    case 0x8800001A:
      if ( !*((_QWORD *)SpinLock + 113) )
      {
        v29 = v96;
        v14 = -1073741808;
        goto LABEL_36;
      }
      if ( _InterlockedIncrement64((volatile signed __int64 *)SpinLock + 1) <= 1 )
        __fastfail(0xEu);
      KeReleaseSpinLock((PKSPIN_LOCK)SpinLock, v96);
      v68 = *((_QWORD *)SpinLock + 113);
      if ( a3 == -2013265909 )
        v69 = QimInspectSetQoS(v68, a4, a5);
      else
        v69 = QimInspectAssociateQoS(v68, a4, a5);
      v14 = v69;
      TcpDereferenceTcb(SpinLock);
      return (unsigned int)v14;
    case 0x98000018:
LABEL_18:
      if ( *((int *)SpinLock + 28) >= 2 )
      {
        v12 = a7;
        v13 = 0;
        v97[0] = 0;
        v14 = -1073741436;
        goto LABEL_21;
      }
      goto LABEL_20;
    case 0x980000E6:
LABEL_20:
      v12 = a7;
      v14 = TcpSetSioLevelOption((int)SpinLock + 760, a3, (_DWORD)a4, a5, (__int64)a6, a7, (__int64)v97);
      v13 = v97[0];
      goto LABEL_21;
  }
  if ( a3 + 1744830264 <= 0x15 && (v70 = 3145757, _bittest(&v70, a3 + 1744830264)) || a3 == -671088439 )
  {
    KeReleaseSpinLock((PKSPIN_LOCK)SpinLock, v96);
    return (unsigned int)InetInspectSocketOption(SpinLock, *((_QWORD *)SpinLock + 113), a3, a4, a5, a6, a7, v98);
  }
  if ( a3 == 1476395213 )
  {
    KeReleaseSpinLock((PKSPIN_LOCK)SpinLock, v96);
    if ( *((_QWORD *)SpinLock + 113) && a7 >= 8 && a6 )
    {
      v14 = 0;
      inserted = WfpAleQueryOrInsertEndpointHandle();
      v72 = v98;
      *(_QWORD *)a6 = inserted;
      if ( v72 )
        *v72 = 8;
    }
    else
    {
      return (unsigned int)-1073741823;
    }
    return (unsigned int)v14;
  }
  if ( a3 == 1207959589 )
    return (unsigned int)TcpFindReceiveProcessorTcb((_DWORD)SpinLock, v96, (_DWORD)a6, a7, (__int64)v98);
LABEL_89:
  v40 = (PKSPIN_LOCK)(SpinLock + 912);
  if ( !*((_QWORD *)SpinLock + 114) )
  {
    v14 = InetInitializeSessionInformationAf(*((_QWORD *)SpinLock + 3), SpinLock + 912);
    if ( v14 < 0 )
      goto LABEL_66;
    v40 = (PKSPIN_LOCK)(SpinLock + 912);
  }
  v41 = *v40;
  v42 = (__int64 *)*((_QWORD *)SpinLock + 4);
  v43 = *((_QWORD *)SpinLock + 3);
  v44 = *((_QWORD *)SpinLock + 113);
  *(_DWORD *)&Src[28] = 0;
  v45 = *v42;
  *(_QWORD *)&Src[40] = 0;
  *(_DWORD *)&Src[76] = 0;
  *(_DWORD *)&Src[92] = 0;
  v46 = *(_QWORD **)(v45 + 8);
  *(_QWORD *)&Src[112] = 0;
  v106 = 0;
  *(_QWORD *)Src = *(_QWORD *)(v43 + 40);
  *(_QWORD *)&Src[16] = *v46;
  v100 = 0;
  LODWORD(v99) = 0;
  *(_DWORD *)&Src[24] = **(_DWORD **)&Src[16];
  *(_OWORD *)&Src[128] = 0;
  if ( v45 )
    *(_QWORD *)&Src[32] = v46;
  else
    *(_QWORD *)&Src[32] = 0;
  *(_DWORD *)&Src[88] = a7;
  v47 = *(_QWORD *)(v43 + 48);
  *(_QWORD *)&Src[48] = v41;
  *(_QWORD *)&Src[104] = 0;
  *(_QWORD *)&Src[96] = 0;
  *(_DWORD *)&Src[56] = a2;
  *(_DWORD *)&Src[60] = a3;
  *(_QWORD *)&Src[64] = a4;
  *(_DWORD *)&Src[72] = a5;
  *(_QWORD *)&Src[80] = a6;
  *(_QWORD *)&Src[120] = v44;
  *(_QWORD *)&Src[8] = v42;
  v48 = *(__int64 (__fastcall **)(_BYTE *))(v47 + 256);
  if ( (char *)v48 == (char *)IpNlpSetSessionInfo )
    v49 = IpNlpSetSessionInfo(Src);
  else
    v49 = v48(Src);
  v14 = v49;
  if ( v49 < 0 )
  {
    v50 = 0;
  }
  else
  {
    if ( v98 )
      *(_QWORD *)v98 = *(unsigned int *)&Src[88];
    v50 = Src[129];
    if ( Src[129] == 1 )
    {
      v51 = *(unsigned int *)&Src[132];
      v52 = *(_DWORD *)&Src[136];
      v53 = *(_WORD *)&Src[140];
      v54 = v106;
      goto LABEL_256;
    }
  }
  if ( v14 < 0 )
  {
LABEL_66:
    v29 = v96;
    goto LABEL_36;
  }
  if ( v50 != 1 )
    goto LABEL_137;
  v51 = v100;
  v54 = v100;
  v53 = v99;
  v52 = v100;
LABEL_256:
  if ( (*((_DWORD *)SpinLock + 31) & 0x200) != 0 )
    v51 = v52;
  TcpRecomputeMss(SpinLock, v51, v54);
  v88 = *((_DWORD *)SpinLock + 202);
  *((_WORD *)SpinLock + 408) = v53;
  *((_DWORD *)SpinLock + 202) = v88 & 0xFFFF7FFF | (v54 != 0 ? 0x8000 : 0);
LABEL_137:
  if ( (!a2 || a2 == 41) && a3 == 71 )
  {
    v89 = SpinLock[795];
    SpinLock[795] = v89 | 4;
    v90 = *a4 < 2u;
    SpinLock[795] = v89 & 0xF9 | 4 | (2 * v90);
    if ( v90 != ((v89 & 2) != 0) )
    {
      if ( v90 )
      {
        memset(Src, 0, 0x88u);
        if ( (int)InetQueryPathInfoAf(
                    *((_QWORD *)SpinLock + 3),
                    *((_QWORD *)SpinLock + 4),
                    *((_QWORD *)SpinLock + 114),
                    (unsigned int)Src,
                    0) >= 0 )
          TcpRefreshMssForTcb(SpinLock, *(unsigned int *)&Src[20]);
        if ( *(_QWORD *)&Src[112] )
          InetDereferenceNextHopAf(*((_QWORD *)SpinLock + 3));
      }
      else
      {
        TcpRefreshMssForTcb(SpinLock, 0);
      }
    }
  }
  KeReleaseSpinLock((PKSPIN_LOCK)SpinLock, v96);
  if ( (!a2 || a2 == 41) && a3 == 14 )
  {
    v96 = 0;
    memset(Src, 0, 0x88u);
    SessionInformationAf = InetQuerySessionInformationAf(
                             *((_QWORD *)SpinLock + 3),
                             *((_QWORD *)SpinLock + 114),
                             **(_QWORD **)(**((_QWORD **)SpinLock + 4) + 8LL),
                             a2,
                             14,
                             (__int64)&v96,
                             1,
                             (__int64)&v98);
    if ( SessionInformationAf < 0 )
      v96 = 0;
    if ( (int)InetQueryPathInfoAf(
                *((_QWORD *)SpinLock + 3),
                *((_QWORD *)SpinLock + 4),
                *((_QWORD *)SpinLock + 114),
                (unsigned int)Src,
                0) >= 0 )
    {
      if ( !Src[121] && v96 )
      {
        v92 = 0;
LABEL_271:
        v93 = *(_QWORD *)&Src[112];
        *((_DWORD *)SpinLock + 202) = v92 | *((_DWORD *)SpinLock + 202) & 0xFFFFBFFF;
        if ( v93 )
          InetDereferenceNextHopAf(*((_QWORD *)SpinLock + 3));
        return (unsigned int)v14;
      }
    }
    else
    {
      Src[121] = 1;
    }
    v92 = 0x4000;
    goto LABEL_271;
  }
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x14005a740  push    rbp
0x14005a742  push    rbx
0x14005a743  push    rsi
0x14005a744  push    rdi
0x14005a745  push    r12
0x14005a747  push    r13
0x14005a749  push    r14
0x14005a74b  push    r15
0x14005a74d  lea     rbp, [rsp-0A8h]
0x14005a755  sub     rsp, 1A8h
0x14005a75c  mov     rax, cs:__security_cookie
0x14005a763  xor     rax, rsp
0x14005a766  mov     [rbp+0E0h+var_50], rax
0x14005a76d  cmp     cs:dword_1402241D4, 0
0x14005a774  mov     r15, r9
0x14005a777  mov     rax, [rbp+0E0h+arg_38]
0x14005a77e  mov     edi, r8d
0x14005a781  mov     r13, [rbp+0E0h+arg_28]
0x14005a788  mov     esi, edx
0x14005a78a  mov     r12, [rbp+0E0h+arg_20]
0x14005a791  mov     rbx, rcx
0x14005a794  mov     [rsp+1E0h+var_168], rax
0x14005a799  mov     [rsp+1E0h+var_16F], 0
0x14005a79e  jz      short loc_14005A7AD
0x14005a7a0  test    byte ptr cs:WPP_MAIN_CB.Dpc.DeferredContext+4, 8
0x14005a7a7  jnz     loc_14005AF7B
0x14005a7ad  mov     rcx, rbx; SpinLock
0x14005a7b0  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14005a7b7  nop     dword ptr [rax+rax+00h]
0x14005a7bc  mov     [rsp+1E0h+var_170], al
0x14005a7c0  movzx   r14d, al
0x14005a7c4  cmp     esi, 6
0x14005a7c7  jz      loc_14005AB68
0x14005a7cd  mov     edx, 0FFFFh
0x14005a7d2  cmp     esi, edx
0x14005a7d4  jz      loc_14005AC17
0x14005a7da  cmp     esi, 0FFFCh
0x14005a7e0  jnz     loc_14005AE4B
0x14005a7e6  cmp     edi, 98000004h
0x14005a7ec  jz      loc_14005A883
0x14005a7f2  cmp     edi, 9800012Ch
0x14005a7f8  jz      loc_14005A883
0x14005a7fe  cmp     edi, 98000010h
0x14005a804  jz      loc_14005B1A2
0x14005a80a  cmp     edi, 98000011h
0x14005a810  jz      short loc_14005A868
0x14005a812  lea     eax, [rdi+67FFFFEDh]
0x14005a818  cmp     eax, 1
0x14005a81b  jbe     short loc_14005A88B
0x14005a81d  cmp     edi, 98000012h
0x14005a823  jz      loc_14005B1A2
0x14005a829  lea     eax, [rdi+67FFFFEAh]
0x14005a82f  cmp     edi, 0D8000027h
0x14005a835  jz      short loc_14005A88B
0x14005a837  cmp     edi, 58000028h
0x14005a83d  jz      short loc_14005A88B
0x14005a83f  cmp     eax, 1
0x14005a842  jbe     short loc_14005A88B
0x14005a844  cmp     edi, 8800000Bh
0x14005a84a  jz      loc_14005B55D
0x14005a850  cmp     edi, 8800001Ah
0x14005a856  jz      loc_14005B55D
0x14005a85c  cmp     edi, 98000018h
0x14005a862  jnz     loc_14005B6E2
0x14005a868  cmp     dword ptr [rbx+70h], 2
0x14005a86c  jl      short loc_14005A88B
0x14005a86e  mov     rsi, [rbp+0E0h+arg_30]
0x14005a875  xor     al, al
0x14005a877  mov     [rsp+1E0h+var_16F], al
0x14005a87b  mov     r14d, 0C0000184h
0x14005a881  jmp     short loc_14005A8C2
0x14005a883  cmp     edi, 98000018h
0x14005a889  jz      short loc_14005A868
0x14005a88b  mov     rsi, [rbp+0E0h+arg_30]
0x14005a892  lea     rax, [rsp+1E0h+var_16F]
0x14005a897  mov     [rsp+1E0h+var_1B0], rax
0x14005a89c  lea     rcx, [rbx+2F8h]
0x14005a8a3  mov     [rsp+1E0h+HandleInformation], rsi
0x14005a8a8  mov     r9, r12
0x14005a8ab  mov     r8, r15
0x14005a8ae  mov     [rsp+1E0h+Object], r13
0x14005a8b3  mov     edx, edi
0x14005a8b5  call    TcpSetSioLevelOption
0x14005a8ba  mov     r14d, eax
0x14005a8bd  movzx   eax, [rsp+1E0h+var_16F]
0x14005a8c2  cmp     edi, 0D8000027h
0x14005a8c8  jnz     loc_14005ACD4
0x14005a8ce  xor     eax, eax
0x14005a8d0  mov     [rbp+0E0h+var_160], 0
0x14005a8d8  mov     word ptr [rbp+0E0h+var_F0+1], ax
0x14005a8dc  mov     byte ptr [rbp+0E0h+var_F0+3], al
0x14005a8df  mov     word ptr [rbp+0E0h+var_B0+5], ax
0x14005a8e3  mov     byte ptr [rbp+0E0h+var_B0+7], al
0x14005a8e6  mov     word ptr [rbp+0E0h+var_80+0Dh], ax
0x14005a8ea  mov     byte ptr [rbp+0E0h+var_80+0Fh], al
0x14005a8ed  mov     dword ptr [rbp+0E0h+Size], 58h ; 'X'
0x14005a8f7  mov     dword ptr [rbp+0E0h+Size+4], 88h
0x14005a901  mov     dword ptr [rbp+0E0h+Size+8], 98h
0x14005a90b  test    r15, r15
0x14005a90e  jz      loc_14005B537
0x14005a914  cmp     r12, 4
0x14005a918  jnz     loc_14005B537
0x14005a91e  mov     eax, [r15]
0x14005a921  cmp     eax, 3
0x14005a924  jnb     loc_14005B537
0x14005a92a  test    r13, r13
0x14005a92d  jz      loc_14005B54C
0x14005a933  mov     edi, dword ptr [rbp+rax*4+0E0h+Size]
0x14005a93a  cmp     rsi, rdi
0x14005a93d  jb      loc_14005B191
0x14005a943  lea     rcx, [rbp+0E0h+var_160]
0x14005a947  call    cs:__imp_KeQuerySystemTimePrecise
0x14005a94e  nop     dword ptr [rax+rax+00h]
0x14005a953  mov     eax, [rbx+70h]
0x14005a956  mov     rcx, [rbp+0E0h+var_160]
0x14005a95a  sub     rcx, [rbx+368h]
0x14005a961  mov     r15d, [rbx+19Ch]
0x14005a968  mov     r12d, [rbx+1ACh]
0x14005a96f  mov     esi, [rbx+18Ch]
0x14005a975  mov     dword ptr [rbp+0E0h+Src], eax
0x14005a978  mov     eax, [rbx+0B0h]
0x14005a97e  mov     dword ptr [rbp+0E0h+Src+4], eax
0x14005a981  mov     rax, 346DC5D63886594Bh
0x14005a98b  imul    rcx
0x14005a98e  mov     ecx, [rbx+90h]
0x14005a994  sub     ecx, [rbx+88h]
0x14005a99a  sar     rdx, 0Bh
0x14005a99e  mov     rax, rdx
0x14005a9a1  mov     [rbp+0E0h+var_E4], ecx
0x14005a9a4  mov     ecx, gs:1A4h
0x14005a9ac  shr     rax, 3Fh
0x14005a9b0  add     rdx, rax
0x14005a9b3  mov     [rbp+0E0h+var_A4], r15d
0x14005a9b7  movzx   eax, byte ptr [rbx+319h]
0x14005a9be  shr     al, 2
0x14005a9c1  and     al, 1
0x14005a9c3  mov     [rbp+0E0h+var_F8], rdx
0x14005a9c7  mov     byte ptr [rbp+0E0h+var_F0], al
0x14005a9ca  xor     edx, edx
0x14005a9cc  mov     eax, [rbx+2C8h]
0x14005a9d2  shr     eax, 3
0x14005a9d5  mov     dword ptr [rbp+0E0h+var_F0+4], eax
0x14005a9d8  mov     eax, [rbx+2D0h]
0x14005a9de  mov     [rbp+0E0h+var_E8], eax
0x14005a9e1  mov     eax, [rbx+0C4h]
0x14005a9e7  mov     dword ptr [rbp+0E0h+var_E0], eax
0x14005a9ea  mov     eax, [rbx+0A0h]
0x14005a9f0  mov     dword ptr [rbp+0E0h+var_E0+4], eax
0x14005a9f3  mov     eax, [rbx+220h]
0x14005a9f9  mov     dword ptr [rbp+0E0h+var_D8], eax
0x14005a9fc  mov     eax, [rbx+2F8h]
0x14005aa02  mov     dword ptr [rbp+0E0h+var_D8+4], eax
0x14005aa05  mov     rax, [rbx+180h]
0x14005aa0c  mov     [rbp+0E0h+var_D0], rax
0x14005aa10  mov     rax, [rbx+200h]
0x14005aa17  mov     [rbp+0E0h+var_C8], rax
0x14005aa1b  mov     eax, [rbx+478h]
0x14005aa21  mov     dword ptr [rbp+0E0h+var_C0], eax
0x14005aa24  mov     eax, [rbx+460h]
0x14005aa2a  mov     dword ptr [rbp+0E0h+var_C0+4], eax
0x14005aa2d  mov     eax, [rbx+464h]
0x14005aa33  mov     [rbp+0E0h+var_B8], eax
0x14005aa36  mov     eax, [rbx+468h]
0x14005aa3c  mov     [rbp+0E0h+var_B4], eax
0x14005aa3f  mov     eax, [rbx+46Ch]
0x14005aa45  mov     dword ptr [rbp+0E0h+var_B0], eax
0x14005aa48  movzx   eax, byte ptr [rbx+474h]
0x14005aa4f  mov     byte ptr [rbp+0E0h+var_B0+4], al
0x14005aa52  mov     eax, [rbx+198h]
0x14005aa58  mov     [rbp+0E0h+var_A8], eax
0x14005aa5b  mov     rax, [rbx+1A0h]
0x14005aa62  mov     [rbp+0E0h+var_A0], rax
0x14005aa66  mov     eax, [rbx+1A8h]
0x14005aa6c  mov     dword ptr [rbp+0E0h+var_98], eax
0x14005aa6f  mov     rax, [rbx+1B0h]
0x14005aa76  mov     [rbp+0E0h+var_90], rax
0x14005aa7a  mov     eax, [rbx+188h]
0x14005aa80  mov     dword ptr [rbp+0E0h+var_88], eax
0x14005aa83  mov     rax, [rbx+190h]
0x14005aa8a  mov     qword ptr [rbp+0E0h+var_80], rax
0x14005aa8e  mov     dword ptr [rbp+0E0h+var_98+4], r12d
0x14005aa92  mov     dword ptr [rbp+0E0h+var_88+4], esi
0x14005aa95  call    TcpQueryMicrosecondCount
0x14005aa9a  mov     rcx, rax
0x14005aa9d  mov     rax, 624DD2F1A9FBE77h
0x14005aaa7  mul     rcx
0x14005aaaa  mov     eax, [rbx+1F4h]
0x14005aab0  sub     rcx, rdx
0x14005aab3  shr     rcx, 1
0x14005aab6  add     rcx, rdx
0x14005aab9  shr     rcx, 9
0x14005aabd  test    eax, eax
0x14005aabf  jnz     loc_14005B4B2
0x14005aac5  sub     ecx, [rbx+1B8h]
0x14005aacb  add     ecx, esi
0x14005aacd  mov     dword ptr [rbp+0E0h+var_88+4], ecx
0x14005aad0  bt      word ptr [rbx+80h], 0Dh
0x14005aad9  mov     eax, [rbx+480h]
0x14005aadf  mov     dword ptr [rbp+0E0h+var_80+8], eax
0x14005aae2  jnb     short loc_14005AAF6
0x14005aae4  test    dword ptr [rbx+328h], 400h
0x14005aaee  jz      short loc_14005AAF6
0x14005aaf0  mov     byte ptr [rbp+0E0h+var_80+0Ch], 1
0x14005aaf4  jmp     short loc_14005AAFA
0x14005aaf6  mov     byte ptr [rbp+0E0h+var_80+0Ch], 0
0x14005aafa  mov     eax, [rbx+484h]
0x14005ab00  lea     rdx, [rbp+0E0h+Src]; Src
0x14005ab04  mov     dword ptr [rbp+0E0h+var_70], eax
0x14005ab07  mov     r8, rdi; Size
0x14005ab0a  mov     eax, [rbx+470h]
0x14005ab10  mov     rcx, r13; void *
0x14005ab13  mov     dword ptr [rbp+0E0h+var_70+4], eax
0x14005ab16  call    memmove
0x14005ab1b  mov     rcx, [rsp+1E0h+var_168]
0x14005ab20  movzx   r12d, [rsp+1E0h+var_170]
0x14005ab26  test    rcx, rcx
0x14005ab29  jz      short loc_14005AB2E
0x14005ab2b  mov     [rcx], rdi
0x14005ab2e  movzx   edx, r12b; NewIrql
0x14005ab32  mov     rcx, rbx; SpinLock
0x14005ab35  call    cs:__imp_KeReleaseSpinLock
0x14005ab3c  nop     dword ptr [rax+rax+00h]
0x14005ab41  mov     eax, r14d
0x14005ab44  mov     rcx, [rbp+0E0h+var_50]
0x14005ab4b  xor     rcx, rsp; StackCookie
0x14005ab4e  call    __security_check_cookie
0x14005ab53  add     rsp, 1A8h
0x14005ab5a  pop     r15
0x14005ab5c  pop     r14
0x14005ab5e  pop     r13
0x14005ab60  pop     r12
0x14005ab62  pop     rdi
0x14005ab63  pop     rsi
0x14005ab64  pop     rbx
0x14005ab65  pop     rbp
0x14005ab66  retn
0x14005ab68  cmp     cs:dword_1402241D4, 0
0x14005ab6f  jz      short loc_14005AB8B
0x14005ab71  cmp     cs:TcpipTraceFiltersExist, 0
0x14005ab78  jnz     loc_14005B6F3
0x14005ab7e  test    byte ptr cs:WPP_MAIN_CB.Dpc.DeferredRoutine+3, 20h
0x14005ab85  jnz     loc_14005B1BA
0x14005ab8b  lea     eax, [rdi-2]
0x14005ab8e  test    eax, 0FFFFFFFAh
0x14005ab93  jz      loc_14005ADFA
0x14005ab99  cmp     edi, 0Fh
0x14005ab9c  ja      short loc_14005ABAC
0x14005ab9e  mov     eax, 9400h
0x14005aba3  bt      eax, edi
0x14005aba6  jb      loc_14005AE13
0x14005abac  lea     rax, [rsp+1E0h+var_16F]
0x14005abb1  mov     r9, r12
0x14005abb4  lea     rcx, [rbx+2F8h]
0x14005abbb  mov     [rsp+1E0h+Object], rax
0x14005abc0  mov     r8, r15
0x14005abc3  mov     edx, edi
0x14005abc5  call    TcpSetTcpLevelOption
0x14005abca  mov     r14d, eax
0x14005abcd  test    eax, eax
0x14005abcf  js      loc_14005ACCA
0x14005abd5  cmp     [rsp+1E0h+var_16F], 0
0x14005abda  jz      loc_14005ACCA
0x14005abe0  mov     ecx, [rbx+7Ch]
0x14005abe3  test    cl, 2
0x14005abe6  jnz     loc_14005ACCA
0x14005abec  cmp     edi, 3
0x14005abef  jz      loc_14005AD8E
0x14005abf5  cmp     edi, 5
0x14005abf8  jz      short loc_14005AC03
0x14005abfa  cmp     edi, 0Eh
0x14005abfd  jnz     loc_14005ACCA
0x14005ac03  movzx   edx, [rsp+1E0h+var_170]
0x14005ac08  mov     dword ptr [rbx+2ECh], 0
0x14005ac12  jmp     loc_14005AB32
0x14005ac17  lea     eax, [rdi-3005h]
0x14005ac1d  test    eax, 0FFFFFFFDh
0x14005ac22  jz      loc_14005B38D
0x14005ac28  cmp     cs:dword_1402241D4, 0
0x14005ac2f  jz      short loc_14005AC4B
0x14005ac31  cmp     cs:TcpipTraceFiltersExist, 0
0x14005ac38  jnz     loc_14005B4C8
0x14005ac3e  test    byte ptr cs:WPP_MAIN_CB.Dpc.DeferredRoutine+3, 20h
0x14005ac45  jnz     loc_14005B28F
0x14005ac4b  cmp     edi, 100h
0x14005ac51  jz      loc_14005AE28
0x14005ac57  cmp     edi, 1002h
0x14005ac5d  jnz     loc_14005AE3D
0x14005ac63  cmp     r12, 4
0x14005ac67  jb      loc_14005B72A
0x14005ac6d  mov     r9d, [rbx+70h]
0x14005ac71  mov     r8d, [r15]
0x14005ac74  cmp     r9d, 2
0x14005ac78  jl      short loc_14005AC8C
0x14005ac7a  movzx   ecx, byte ptr [rbx+321h]
0x14005ac81  shl     edx, cl
0x14005ac83  cmp     r8d, edx
0x14005ac86  ja      loc_14005B1FA
0x14005ac8c  lea     rsi, [rbx+2F8h]
0x14005ac93  cmp     r9d, 4
0x14005ac97  jl      short loc_14005ACA2
  ... truncated ...
```
