# MgmNewPacketReceived

- ea: `0x180018070`
- end: `0x180018bfc`
- name: `MgmNewPacketReceived`
- size: `2956`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, int@<edx>, int, __int64)`
- caller_count: `0`
- callee_count: `25`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800070d0`
- `0x180007220`
- `0x180014bfc`
- `0x180014d2c`
- `0x180014f98`
- `0x180015040`
- `0x180015100`
- `0x180015178`
- `0x1800151ec`
- `0x18001740c`
- `0x18001765c`
- `0x1800176bc`
- `0x180017a44`
- `0x180017f48`
- `0x180018070`
- `0x18001b668`
- `0x18001ca9c`
- `0x18001cf18`
- `0x18001dc28`
- `0x18001dd8c`
- `0x18001f11c`
- `0x18001f7e8`
- `0x18001f952`
- `0x18001f980`
- `0x180020010`

## import_xrefs

- `ntdll!RtlCreateTimer` at `0x180018a50`
- `ntdll!RtlCreateTimer` at `0x180018a50`
- `ntdll!NtQuerySystemTime` at `0x180018875`
- `ntdll!NtQuerySystemTime` at `0x180018875`
- `KERNEL32!HeapAlloc` at `0x180018948`
- `KERNEL32!HeapAlloc` at `0x180018948`
- `KERNEL32!HeapFree` at `0x1800188e6`
- `KERNEL32!HeapFree` at `0x180018a69`
- `KERNEL32!HeapFree` at `0x1800188e6`
- `KERNEL32!HeapFree` at `0x180018a69`
- `rtutils!RouterLogEventA` at `0x1800189d4`
- `rtutils!RouterLogEventA` at `0x1800189d4`
- `WS2_32!__imp_htonl` at `0x180018846`
- `WS2_32!__imp_htonl` at `0x180018846`

## string_xrefs

- `0x1800186a3`: `Invoked Prune Alert for protocol %x, %x`

## pseudocode

```c
__int64 __fastcall MgmNewPacketReceived(unsigned int a1, unsigned int a2, int a3, int a4, int a5, __int64 a6)
{
  int v6; // r12d
  unsigned int v7; // r13d
  __int64 v9; // rsi
  __int64 v10; // rdx
  unsigned int v12; // r14d
  DWORD v13; // edi
  DWORD v14; // r14d
  __int64 v15; // rbx
  char *v16; // r14
  int v17; // r8d
  int GroupEntry; // eax
  _DWORD *v19; // rbx
  int v20; // r8d
  DWORD v21; // edx
  int SourceEntry; // eax
  int v23; // r8d
  int v24; // ebx
  int v25; // r8d
  __int64 v26; // rdx
  __int64 v27; // r14
  __int64 v28; // r14
  int v29; // r8d
  int v30; // eax
  int v31; // r8d
  int v32; // r8d
  __int64 v33; // rdx
  unsigned int v34; // edx
  int v35; // eax
  __int64 v36; // rdx
  __int128 *v37; // rcx
  __int128 *v38; // rdx
  __int64 v39; // rbx
  int v40; // edx
  int v41; // r9d
  DWORD v42; // edx
  int v43; // eax
  unsigned int v44; // eax
  __int64 v45; // rcx
  DWORD v46; // eax
  ULONG EntityProtocolId; // ecx
  u_long v48; // eax
  _WORD *v49; // rax
  __int64 v50; // r13
  _QWORD *v51; // rcx
  _DWORD *v52; // rax
  void *v53; // r12
  DWORD dwErrorCode; // esi
  int v55; // edx
  int v56; // r9d
  int plpszSubStringArray; // [rsp+20h] [rbp-E0h]
  int Flags; // [rsp+30h] [rbp-D0h]
  __int64 v59; // [rsp+70h] [rbp-90h] BYREF
  int v60; // [rsp+78h] [rbp-88h]
  __int64 v61; // [rsp+80h] [rbp-80h] BYREF
  NTSTATUS Timer; // [rsp+88h] [rbp-78h] BYREF
  __int128 v63; // [rsp+90h] [rbp-70h] BYREF
  ULONG DueTime; // [rsp+A0h] [rbp-60h] BYREF
  DWORD v65; // [rsp+A4h] [rbp-5Ch]
  int v66; // [rsp+A8h] [rbp-58h]
  __int128 v67; // [rsp+B0h] [rbp-50h] BYREF
  int v68; // [rsp+C0h] [rbp-40h] BYREF
  int v69; // [rsp+C4h] [rbp-3Ch]
  int v70; // [rsp+C8h] [rbp-38h] BYREF
  int v71; // [rsp+CCh] [rbp-34h]
  _DWORD *v72; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v73; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v74; // [rsp+E0h] [rbp-20h] BYREF
  int v75[2]; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v76; // [rsp+F0h] [rbp-10h] BYREF
  unsigned int v77; // [rsp+F8h] [rbp-8h]
  _DWORD *v78; // [rsp+100h] [rbp+0h]
  __int64 v79; // [rsp+108h] [rbp+8h] BYREF
  char *v80; // [rsp+110h] [rbp+10h]
  _DWORD *v81; // [rsp+118h] [rbp+18h] BYREF
  int v82[2]; // [rsp+120h] [rbp+20h] BYREF
  __int64 v83; // [rsp+128h] [rbp+28h] BYREF
  struct _RTM_ENTITY_INFO EntityInfo; // [rsp+130h] [rbp+30h] BYREF
  struct _RTM_DEST_INFO DestInfo; // [rsp+140h] [rbp+40h] BYREF
  int v86; // [rsp+1A0h] [rbp+A0h] BYREF
  char v87[2044]; // [rsp+1A4h] [rbp+A4h] BYREF

  v6 = 0;
  v77 = a2;
  v7 = a2;
  LODWORD(v59) = a3;
  LODWORD(v61) = a4;
  v68 = 0;
  v70 = 0;
  DueTime = 900000;
  Timer = 0;
  *(_QWORD *)v75 = 0;
  *(_QWORD *)v82 = 0;
  v9 = 0;
  v72 = 0;
  v76 = 0;
  v81 = 0;
  v74 = 0;
  v73 = 0;
  v79 = 0;
  v67 = 0;
  v63 = 0;
  EntityInfo = 0;
  memset_0(&DestInfo, 0, sizeof(DestInfo));
  v83 = 0;
  v86 = 0;
  memset_0(v87, 0, sizeof(v87));
  if ( !(unsigned int)EnterMgmAPI() )
    return 1003;
  if ( qword_18002B8A8 )
  {
    Flags = v59;
    plpszSubStringArray = v7;
    LOWORD(v86) = 0;
    FormatRRASErrorString(
      &v86,
      L"ENTERED MgmNewPacketReceived : Source %x, %x : Group %x, %x : In Interface : %x, %x",
      a1,
      0xFFFFFFFFLL);
    ((void (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(gMgmEtwContext, qword_18002B8A8, &v86);
  }
  if ( (unsigned int)IsMFEPresent(a1, v10, v7) )
  {
    if ( qword_18002B8A8 )
    {
      LOWORD(v86) = 0;
      FormatRRASErrorString(&v86, L"LEAVING MgmNewPacketReceived %x\n", 0);
      ((void (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(gMgmEtwContext, qword_18002B8A8, &v86);
    }
    LeaveMgmWorker();
    return 0;
  }
  AcquireReadLock(&qword_18002B9B8);
  memset_0(&DestInfo, 0, sizeof(DestInfo));
  v12 = InvokeRPFCallbacks(
          (int)v75,
          (int)v82,
          (int)&v68,
          a1,
          plpszSubStringArray,
          v7,
          Flags,
          (__int64)&v59,
          (__int64)&v61,
          (__int64)&v70,
          a5,
          a6,
          (__int64)&v83,
          &DestInfo);
  if ( !v12 )
  {
    v60 = 0;
    *((_QWORD *)&v67 + 1) = &v67;
    *(_QWORD *)&v67 = &v67;
    *((_QWORD *)&v63 + 1) = &v63;
    *(_QWORD *)&v63 = &v63;
    v66 = 0;
    v78 = 0;
    if ( qword_18002B950 && (unsigned int)qword_18002B950((unsigned int)v59, v7) )
    {
      v71 = 0;
      v13 = v12 + 1;
      if ( v7 )
        v14 = v13 + v7 % (dword_18002B930 - 1);
      else
        v14 = 0;
      v15 = 32LL * v14;
      v65 = v14;
      AcquireWriteLock((char *)qword_18002BA40 + v15 + 16);
      v16 = (char *)qword_18002BA40 + v15;
      GroupEntry = FindGroupEntry((int)v15 + (int)qword_18002BA40, v7, v17, (unsigned int)&v72, v13);
      v19 = v72;
      v69 = GroupEntry;
      if ( GroupEntry )
      {
        AcquireWriteLock(v72 + 10);
        v60 = v13;
        if ( a1 )
          v21 = v13 + a1 % (dword_18002B934 - 1);
        else
          v21 = 0;
        v78 = &v19[4 * v21 + 22];
        SourceEntry = FindSourceEntry((_DWORD)v78, a1, v20, (unsigned int)&v74, v13);
        v9 = v74;
        v6 = SourceEntry;
      }
LABEL_49:
      if ( (__int128 *)v63 != &v63 )
      {
LABEL_56:
        if ( v69 )
        {
          v43 = (int)v78;
        }
        else
        {
          if ( v19 )
            v16 = (char *)(v19 + 4);
          v12 = CreateGroupEntry(v16, v7, 0, &v81);
          if ( v12 )
            goto LABEL_96;
          v19 = v81;
          AcquireWriteLock(v81 + 10);
          v60 = v13;
          if ( a1 )
            v42 = v13 + a1 % (dword_18002B934 - 1);
          else
            v42 = 0;
          v43 = (_DWORD)v19 + 16 * v42 + 88;
        }
        if ( !v6 )
        {
          if ( v9 )
            v44 = CreateSourceEntry((_DWORD)v19, (int)v9 + 16, a1, -1, (__int64)&v79);
          else
            v44 = CreateSourceEntry((_DWORD)v19, v43, a1, -1, (__int64)&v79);
          v12 = v44;
          if ( v44 )
          {
LABEL_96:
            if ( v60 )
              ReleaseWriteLock(v19 + 10);
            ReleaseWriteLock((char *)qword_18002BA40 + 32 * v65 + 16);
            if ( v66 )
              ReleaseReadLock(v76 + 40);
            if ( v71 )
              ReleaseReadLock((char *)qword_18002BA40 + 16);
            ReleaseReadLock((char *)qword_18002B9E8 + 32 * (unsigned int)v68 + 16);
            if ( !v12 )
              AddSourceGroupToRouteRefList(a1, v55, v7, v56, v83, (__int64)&DestInfo);
            RtmReleaseDestInfo(g_hRtmHandle, &DestInfo);
            goto LABEL_105;
          }
          v9 = v79;
          v19[12] += v13;
        }
        v45 = *(_QWORD *)v75;
        *(_DWORD *)(v9 + 112) = v59;
        *(_DWORD *)(v9 + 116) = v61;
        *(_DWORD *)(v9 + 120) = v70;
        *(_DWORD *)(v9 + 136) = *(_DWORD *)(v45 + 16);
        *(_DWORD *)(v9 + 140) = *(_DWORD *)(v45 + 20);
        v46 = RtmGetEntityInfo(g_hRtmHandle, DestInfo.ViewInfo[0].Owner, &EntityInfo);
        EntityProtocolId = EntityInfo.EntityId.EntityProtocolId;
        v12 = v46;
        if ( v46 )
          EntityProtocolId = 0;
        *(_DWORD *)(v9 + 124) = EntityProtocolId;
        *(_DWORD *)(v9 + 128) = *(_DWORD *)DestInfo.DestAddress.AddrBits;
        if ( DestInfo.DestAddress.NumBits )
          v48 = htonl(-1 << (32 - LOBYTE(DestInfo.DestAddress.NumBits)));
        else
          v48 = 0;
        *(_DWORD *)(v9 + 132) = v48;
        *(_DWORD *)(v9 + 144) = v13;
        *(_DWORD *)(v9 + 168) = DueTime / 0x3E8;
        NtQuerySystemTime((PLARGE_INTEGER)(v9 + 176));
        if ( (__int128 *)v63 != &v63 )
        {
          *(_DWORD *)(v9 + 80) = Timer;
          *(_OWORD *)(v9 + 88) = v63;
          *(_QWORD *)(v63 + 8) = v9 + 88;
          **((_QWORD **)&v63 + 1) = v9 + 88;
          v49 = *(_WORD **)(v9 + 88);
          if ( v49 != (_WORD *)(v9 + 88) )
          {
            do
            {
              v50 = *(_QWORD *)v49;
              if ( !v49[16] )
              {
                if ( *(_WORD **)(v50 + 8) != v49 || (v51 = (_QWORD *)*((_QWORD *)v49 + 1), (_WORD *)*v51 != v49) )
                  __fastfail(3u);
                *v51 = v50;
                *(_QWORD *)(v50 + 8) = v51;
                HeapFree(hHeap, 0, v49);
              }
              v49 = (_WORD *)v50;
            }
            while ( v50 != v9 + 88 );
            v7 = v77;
          }
        }
        AddSourceToRefList(v82[0] + 56, a1, -1, v7, 0, *(_DWORD *)(*(_QWORD *)v75 + 16LL) == 10);
        AddMfeToForwarder(v19, v9, DueTime);
        v52 = HeapAlloc(hHeap, 0, 0x18u);
        v53 = v52;
        if ( v52 )
        {
          *v52 = *(_DWORD *)(v9 + 104);
          v52[1] = *(_DWORD *)(v9 + 108);
          v52[2] = v19[8];
          v52[3] = v19[9];
          v52[4] = *(_DWORD *)(v9 + 112);
          v52[5] = *(_DWORD *)(v9 + 116);
          Timer = RtlCreateTimer(
                    *((HANDLE *)qword_18002BA48 + v19[8] % (unsigned int)dword_18002B95C),
                    (PHANDLE)(v9 + 152),
                    MFETimerProc,
                    v52,
                    DueTime,
                    0,
                    0);
          if ( Timer >= 0 )
          {
            *(_QWORD *)(v9 + 160) = v53;
          }
          else
          {
            HeapFree(hHeap, 0, v53);
            dwErrorCode = Timer;
            if ( qword_18002B8A8 )
            {
              LOWORD(v86) = 0;
              FormatRRASErrorString(&v86, L"Timer set failed with status %lx", (unsigned int)Timer);
              ((void (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(gMgmEtwContext, qword_18002B8A8, &v86);
            }
            if ( dword_18002BA54 >= v13 )
              RouterLogEventA(qword_18002BA58, v13, 0xC365u, 0, 0, dwErrorCode);
          }
        }
        else
        {
          if ( qword_18002B8A8 )
          {
            LOWORD(v86) = 0;
            FormatRRASErrorString(&v86, L"Failed to allocate timer context of size : %d", 24);
            ((void (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(gMgmEtwContext, qword_18002B8A8, &v86);
          }
          v12 = 8;
          if ( dword_18002BA54 >= v13 )
            RouterLogEventA(qword_18002BA58, v13, 0xC353u, 0, 0, 8u);
        }
        goto LABEL_96;
      }
    }
    else
    {
      v13 = 1;
      while ( 1 )
      {
        AcquireReadLock((char *)qword_18002BA40 + 16);
        v71 = 1;
        if ( (unsigned int)FindGroupEntry((_DWORD)qword_18002BA40, 0, v23, (unsigned int)&v76, 1) )
        {
          v24 = v76;
          AcquireReadLock(v76 + 40);
          v66 = 1;
          if ( (unsigned int)FindSourceEntry(v24 + 88, 0, v25, (unsigned int)&v73, 1) )
          {
            v26 = v73;
            _InterlockedExchange((volatile __int32 *)(v73 + 32), 1);
            CopyAndMergeIfLists(&v67, v26 + 48);
          }
        }
        if ( v7 )
          v27 = v7 % (dword_18002B930 - 1) + 1;
        else
          v27 = 0;
        v65 = v27;
        v28 = 32 * v27;
        AcquireWriteLock((char *)qword_18002BA40 + v28 + 16);
        v80 = (char *)qword_18002BA40 + v28;
        v30 = FindGroupEntry((int)v28 + (int)qword_18002BA40, v7, v29, (unsigned int)&v72, 1);
        v19 = v72;
        v69 = v30;
        if ( v30 )
        {
          v73 = 0;
          AcquireWriteLock(v72 + 10);
          v60 = 1;
          if ( (unsigned int)FindSourceEntry((int)v19 + 88, 0, v31, (unsigned int)&v73, 1) )
          {
            v33 = v73;
            *(_DWORD *)(v73 + 32) = 1;
            CopyAndMergeIfLists(&v67, v33 + 48);
          }
          if ( a1 )
            v34 = a1 % (dword_18002B934 - 1) + 1;
          else
            v34 = 0;
          v78 = &v19[4 * v34 + 22];
          v35 = FindSourceEntry((_DWORD)v78, a1, v32, (unsigned int)&v74, 1);
          v9 = v74;
          v6 = v35;
          if ( v35 )
          {
            v36 = v74 + 48;
            *(_DWORD *)(v74 + 32) = 1;
            CopyAndMergeIfLists(&v67, v36);
          }
        }
        v37 = (__int128 *)v67;
        if ( (__int128 *)v67 == &v67 )
          break;
        v38 = (__int128 *)v63;
        if ( (__int128 *)v63 != &v63 )
        {
          while ( *((_DWORD *)v38 + 4) == *((_DWORD *)v37 + 4) && *((_DWORD *)v38 + 5) == *((_DWORD *)v37 + 5) )
          {
            v38 = *(__int128 **)v38;
            v37 = *(__int128 **)v37;
            if ( v38 == &v63 )
            {
              if ( v37 != &v67 )
                break;
              FreeList(&v67);
              v16 = v80;
              goto LABEL_49;
            }
            if ( v37 == &v67 )
              break;
          }
        }
        v6 = 0;
        if ( v60 )
        {
          ReleaseWriteLock(v19 + 10);
          v60 = 0;
        }
        ReleaseWriteLock((char *)qword_18002BA40 + v28 + 16);
        if ( v66 )
        {
          ReleaseReadLock(v76 + 40);
          v66 = 0;
        }
        ReleaseReadLock((char *)qword_18002BA40 + 16);
        v39 = 32LL * (unsigned int)v68;
        ReleaseReadLock((char *)qword_18002B9E8 + v39 + 16);
        InvokeCreationAlert(a1, v40, v7, v41, v59, v61, (__int64)&v67, (__int64)&Timer);
        FreeList(&v63);
        v63 = v67;
        *(_QWORD *)(v67 + 8) = &v63;
        **((_QWORD **)&v67 + 1) = &v63;
        *((_QWORD *)&v67 + 1) = &v67;
        *(_QWORD *)&v67 = &v67;
        AcquireReadLock((char *)qword_18002B9E8 + v39 + 16);
      }
      FreeList(&v63);
      v16 = v80;
      *((_QWORD *)&v63 + 1) = &v63;
      *(_QWORD *)&v63 = &v63;
    }
    if ( *(_QWORD *)(*(_QWORD *)v75 + 56LL) )
    {
      if ( qword_18002B8A8 )
      {
        LOWORD(v86) = 0;
        FormatRRASErrorString(
          &v86,
          L"Invoked Prune Alert for protocol %x, %x",
          *(unsigned int *)(*(_QWORD *)v75 + 16LL),
          *(unsigned int *)(*(_QWORD *)v75 + 20LL));
        ((void (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(gMgmEtwContext, qword_18002B8A8, &v86);
      }
      (*(void (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD, _DWORD, _DWORD, _DWORD, ULONG *))(*(_QWORD *)v75 + 56LL))(
        a1,
        0xFFFFFFFFLL,
        v7,
        0,
        v59,
        v61,
        0,
        &DueTime);
    }
    goto LABEL_56;
  }
LABEL_105:
  ReleaseReadLock(&qword_18002B9B8);
  if ( qword_18002B8A8 )
  {
    LOWORD(v86) = 0;
    FormatRRASErrorString(&v86, L"LEAVING MgmNewPacketReceived %x\n", v12);
    ((void (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(gMgmEtwContext, qword_18002B8A8, &v86);
  }
  LeaveMgmWorker();
  return v12;
}

```

## disassembly

```asm
0x180018070  push    rbp
0x180018072  push    rbx
0x180018073  push    rsi
0x180018074  push    rdi
0x180018075  push    r12
0x180018077  push    r13
0x180018079  push    r14
0x18001807b  push    r15
0x18001807d  lea     rbp, [rsp-8B8h]
0x180018085  sub     rsp, 9B8h
0x18001808c  mov     rax, cs:__security_cookie
0x180018093  xor     rax, rsp
0x180018096  mov     [rbp+8F0h+var_50], rax
0x18001809d  mov     rbx, [rbp+8F0h+arg_28]
0x1800180a4  xor     r12d, r12d
0x1800180a7  xorps   xmm0, xmm0
0x1800180aa  mov     [rbp+8F0h+var_8F8], edx
0x1800180ad  mov     r13d, edx
0x1800180b0  mov     dword ptr [rsp+9F0h+var_980], r8d
0x1800180b5  mov     r15d, ecx
0x1800180b8  mov     dword ptr [rbp+8F0h+var_970], r9d
0x1800180bc  xorps   xmm1, xmm1
0x1800180bf  mov     [rbp+8F0h+var_930], r12d
0x1800180c3  lea     edi, [r12+58h]
0x1800180c8  mov     dword ptr [rbp+8F0h+var_928], r12d
0x1800180cc  mov     r8d, edi; Size
0x1800180cf  mov     [rbp+8F0h+DueTime], 0DBBA0h
0x1800180d6  xor     edx, edx; Val
0x1800180d8  mov     [rbp+8F0h+var_968], r12d
0x1800180dc  lea     rcx, [rbp+8F0h+DestInfo]; void *
0x1800180e0  mov     qword ptr [rbp+8F0h+var_908], r12
0x1800180e4  mov     qword ptr [rbp+8F0h+var_8D0], r12
0x1800180e8  mov     esi, r12d
0x1800180eb  mov     [rbp+8F0h+var_920], r12
0x1800180ef  mov     [rbp+8F0h+var_900], r12
0x1800180f3  mov     [rbp+8F0h+var_8D8], r12
0x1800180f7  mov     [rbp+8F0h+var_910], r12
0x1800180fb  mov     [rbp+8F0h+var_918], r12
0x1800180ff  mov     [rbp+8F0h+var_8E8], r12
0x180018103  movups  [rbp+8F0h+var_940], xmm0
0x180018107  movups  [rbp+8F0h+var_960], xmm1
0x18001810b  movups  xmmword ptr [rbp+8F0h+EntityInfo.RtmInstanceId], xmm0
0x18001810f  call    memset_0
0x180018114  xor     edx, edx; Val
0x180018116  mov     [rbp+8F0h+var_8C8], r12
0x18001811a  mov     r8d, 7FCh; Size
0x180018120  mov     [rbp+8F0h+var_850], r12d
0x180018127  lea     rcx, [rbp+8F0h+var_84C]; void *
0x18001812e  call    memset_0
0x180018133  call    EnterMgmAPI
0x180018138  test    eax, eax
0x18001813a  jnz     short loc_180018146
0x18001813c  mov     eax, 3EBh
0x180018141  jmp     loc_180018BD9
0x180018146  cmp     cs:qword_18002B8A8, r12
0x18001814d  jz      short loc_1800181AB
0x18001814f  mov     eax, dword ptr [rbp+8F0h+var_970]
0x180018152  lea     rdx, aEnteredMgmnewp; "ENTERED MgmNewPacketReceived : Source %"...
0x180018159  mov     dword ptr [rsp+9F0h+var_9B8], eax
0x18001815d  lea     rcx, [rbp+8F0h+var_850]
0x180018164  mov     eax, dword ptr [rsp+9F0h+var_980]
0x180018168  or      r9d, 0FFFFFFFFh
0x18001816c  mov     [rsp+9F0h+Flags], eax; int
0x180018170  mov     r8d, r15d
0x180018173  mov     [rsp+9F0h+dwErrorCode], r12d
0x180018178  mov     dword ptr [rsp+9F0h+plpszSubStringArray], r13d; int
0x18001817d  mov     word ptr [rbp+8F0h+var_850], r12w
0x180018185  call    FormatRRASErrorString
0x18001818a  mov     rdx, cs:qword_18002B8A8
0x180018191  lea     r8, [rbp+8F0h+var_850]
0x180018198  mov     rcx, cs:gMgmEtwContext
0x18001819f  mov     rax, cs:gMgmTemplateFunc
0x1800181a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800181ab  mov     r8d, r13d
0x1800181ae  mov     ecx, r15d
0x1800181b1  call    IsMFEPresent
0x1800181b6  test    eax, eax
0x1800181b8  jz      short loc_18001820E
0x1800181ba  cmp     cs:qword_18002B8A8, r12
0x1800181c1  jz      short loc_180018202
0x1800181c3  xor     r8d, r8d
0x1800181c6  mov     word ptr [rbp+8F0h+var_850], r12w
0x1800181ce  lea     rdx, aLeavingMgmnewp; "LEAVING MgmNewPacketReceived %x\n"
0x1800181d5  lea     rcx, [rbp+8F0h+var_850]
0x1800181dc  call    FormatRRASErrorString
0x1800181e1  mov     rdx, cs:qword_18002B8A8
0x1800181e8  lea     r8, [rbp+8F0h+var_850]
0x1800181ef  mov     rcx, cs:gMgmEtwContext
0x1800181f6  mov     rax, cs:gMgmTemplateFunc
0x1800181fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018202  call    LeaveMgmWorker
0x180018207  xor     eax, eax
0x180018209  jmp     loc_180018BD9
0x18001820e  lea     rcx, qword_18002B9B8
0x180018215  call    AcquireReadLock
0x18001821a  mov     r8, rdi; Size
0x18001821d  lea     rcx, [rbp+8F0h+DestInfo]; void *
0x180018221  xor     edx, edx; Val
0x180018223  call    memset_0
0x180018228  lea     rax, [rbp+8F0h+DestInfo]
0x18001822c  mov     r9d, r15d; int
0x18001822f  mov     [rsp+9F0h+var_988], rax; PRTM_DEST_INFO
0x180018234  lea     r8, [rbp+8F0h+var_930]; int
0x180018238  lea     rax, [rbp+8F0h+var_8C8]
0x18001823c  mov     [rsp+9F0h+var_990], rax; __int64
0x180018241  lea     rdx, [rbp+8F0h+var_8D0]; int
0x180018245  mov     eax, [rbp+8F0h+arg_20]
0x18001824b  lea     rcx, [rbp+8F0h+var_908]; int
0x18001824f  mov     [rsp+9F0h+var_998], rbx; __int64
0x180018254  mov     [rsp+9F0h+var_9A0], eax; int
0x180018258  lea     rax, [rbp+8F0h+var_928]
0x18001825c  mov     [rsp+9F0h+var_9A8], rax; __int64
0x180018261  lea     rax, [rbp+8F0h+var_970]
0x180018265  mov     [rsp+9F0h+var_9B0], rax; __int64
0x18001826a  lea     rax, [rsp+9F0h+var_980]
0x18001826f  mov     [rsp+9F0h+var_9B8], rax; __int64
0x180018274  mov     [rsp+9F0h+dwErrorCode], r13d; int
0x180018279  call    InvokeRPFCallbacks
0x18001827e  mov     r14d, eax
0x180018281  test    eax, eax
0x180018283  jnz     loc_180018B7D
0x180018289  lea     rax, [rbp+8F0h+var_940]
0x18001828d  mov     [rsp+9F0h+var_978], r12d
0x180018292  mov     qword ptr [rbp+8F0h+var_940+8], rax
0x180018296  lea     rax, [rbp+8F0h+var_940]
0x18001829a  mov     qword ptr [rbp+8F0h+var_940], rax
0x18001829e  lea     rax, [rbp+8F0h+var_960]
0x1800182a2  mov     qword ptr [rbp+8F0h+var_960+8], rax
0x1800182a6  lea     rax, [rbp+8F0h+var_960]
0x1800182aa  mov     qword ptr [rbp+8F0h+var_960], rax
0x1800182ae  mov     rax, cs:qword_18002B950
0x1800182b5  mov     [rbp+8F0h+var_948], r12d
0x1800182b9  mov     [rbp+8F0h+var_8F0], r12
0x1800182bd  test    rax, rax
0x1800182c0  jz      loc_1800183A1
0x1800182c6  mov     ecx, dword ptr [rsp+9F0h+var_980]
0x1800182ca  mov     edx, r13d
0x1800182cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800182d2  test    eax, eax
0x1800182d4  jz      loc_1800183A1
0x1800182da  xor     eax, eax
0x1800182dc  mov     dword ptr [rbp+8F0h+var_928+4], r12d
0x1800182e0  lea     edi, [r14+1]
0x1800182e4  test    r13d, r13d
0x1800182e7  jz      short loc_1800182FE
0x1800182e9  mov     ecx, cs:dword_18002B930
0x1800182ef  xor     edx, edx
0x1800182f1  dec     ecx
0x1800182f3  mov     eax, r13d
0x1800182f6  div     ecx
0x1800182f8  lea     r14d, [rdi+rdx]
0x1800182fc  jmp     short loc_180018301
0x1800182fe  mov     r14d, eax
0x180018301  mov     rcx, cs:qword_18002BA40
0x180018308  add     rcx, 10h
0x18001830c  mov     ebx, r14d
0x18001830f  shl     rbx, 5
0x180018313  add     rcx, rbx
0x180018316  mov     [rbp+8F0h+var_94C], r14d
0x18001831a  call    AcquireWriteLock
0x18001831f  mov     r14, cs:qword_18002BA40
0x180018326  lea     r9, [rbp+8F0h+var_920]
0x18001832a  add     r14, rbx
0x18001832d  mov     dword ptr [rsp+9F0h+plpszSubStringArray], edi
0x180018331  mov     rcx, r14
0x180018334  mov     edx, r13d
0x180018337  call    FindGroupEntry
0x18001833c  mov     rbx, [rbp+8F0h+var_920]
0x180018340  mov     [rbp+8F0h+var_92C], eax
0x180018343  test    eax, eax
0x180018345  jz      loc_180018654
0x18001834b  lea     rcx, [rbx+28h]
0x18001834f  call    AcquireWriteLock
0x180018354  xor     eax, eax
0x180018356  mov     [rsp+9F0h+var_978], edi
0x18001835a  test    r15d, r15d
0x18001835d  jz      short loc_180018372
0x18001835f  mov     ecx, cs:dword_18002B934
0x180018365  xor     edx, edx
0x180018367  dec     ecx
0x180018369  mov     eax, r15d
0x18001836c  div     ecx
0x18001836e  add     edx, edi
0x180018370  jmp     short loc_180018374
0x180018372  mov     edx, eax
0x180018374  mov     ecx, edx
0x180018376  lea     r9, [rbp+8F0h+var_910]
0x18001837a  shl     rcx, 4
0x18001837e  mov     edx, r15d
0x180018381  add     rcx, 58h ; 'X'
0x180018385  mov     dword ptr [rsp+9F0h+plpszSubStringArray], edi
0x180018389  add     rcx, rbx
0x18001838c  mov     [rbp+8F0h+var_8F0], rcx
0x180018390  call    FindSourceEntry
0x180018395  mov     rsi, [rbp+8F0h+var_910]
0x180018399  mov     r12d, eax
0x18001839c  jmp     loc_180018654
0x1800183a1  mov     edi, 1
0x1800183a6  mov     rcx, cs:qword_18002BA40
0x1800183ad  add     rcx, 10h
0x1800183b1  call    AcquireReadLock
0x1800183b6  mov     rcx, cs:qword_18002BA40
0x1800183bd  lea     r9, [rbp+8F0h+var_900]
0x1800183c1  xor     edx, edx
0x1800183c3  mov     dword ptr [rbp+8F0h+var_928+4], edi
0x1800183c6  mov     dword ptr [rsp+9F0h+plpszSubStringArray], edi
0x1800183ca  call    FindGroupEntry
0x1800183cf  test    eax, eax
0x1800183d1  jz      short loc_180018410
0x1800183d3  mov     rbx, [rbp+8F0h+var_900]
0x1800183d7  lea     rcx, [rbx+28h]
0x1800183db  call    AcquireReadLock
0x1800183e0  lea     rcx, [rbx+58h]
0x1800183e4  mov     [rbp+8F0h+var_948], edi
0x1800183e7  lea     r9, [rbp+8F0h+var_918]
0x1800183eb  mov     dword ptr [rsp+9F0h+plpszSubStringArray], edi
0x1800183ef  xor     edx, edx
0x1800183f1  call    FindSourceEntry
0x1800183f6  test    eax, eax
0x1800183f8  jz      short loc_180018410
0x1800183fa  mov     rdx, [rbp+8F0h+var_918]
0x1800183fe  lea     rcx, [rbp+8F0h+var_940]
0x180018402  mov     eax, edi
0x180018404  xchg    eax, [rdx+20h]
0x180018407  add     rdx, 30h ; '0'
0x18001840b  call    CopyAndMergeIfLists
0x180018410  test    r13d, r13d
0x180018413  jz      short loc_18001842A
0x180018415  mov     ecx, cs:dword_18002B930
0x18001841b  xor     edx, edx
0x18001841d  dec     ecx
0x18001841f  mov     eax, r13d
0x180018422  div     ecx
0x180018424  lea     r14d, [rdi+rdx]
0x180018428  jmp     short loc_18001842D
0x18001842a  mov     r14d, r12d
0x18001842d  mov     rcx, cs:qword_18002BA40
0x180018434  add     rcx, 10h
0x180018438  mov     [rbp+8F0h+var_94C], r14d
0x18001843c  shl     r14, 5
0x180018440  add     rcx, r14
0x180018443  call    AcquireWriteLock
0x180018448  mov     rax, cs:qword_18002BA40
0x18001844f  lea     r9, [rbp+8F0h+var_920]
0x180018453  add     rax, r14
0x180018456  mov     dword ptr [rsp+9F0h+plpszSubStringArray], edi
0x18001845a  mov     rcx, rax
0x18001845d  mov     [rbp+8F0h+var_8E0], rax
0x180018461  mov     edx, r13d
0x180018464  call    FindGroupEntry
0x180018469  mov     rbx, [rbp+8F0h+var_920]
0x18001846d  mov     [rbp+8F0h+var_92C], eax
0x180018470  test    eax, eax
0x180018472  jz      loc_18001850C
0x180018478  xor     esi, esi
0x18001847a  lea     rcx, [rbx+28h]
0x18001847e  mov     [rbp+8F0h+var_918], rsi
0x180018482  call    AcquireWriteLock
0x180018487  lea     rcx, [rbx+58h]
0x18001848b  mov     [rsp+9F0h+var_978], edi
0x18001848f  lea     r9, [rbp+8F0h+var_918]
0x180018493  mov     dword ptr [rsp+9F0h+plpszSubStringArray], edi
0x180018497  xor     edx, edx
0x180018499  call    FindSourceEntry
0x18001849e  test    eax, eax
0x1800184a0  jz      short loc_1800184B6
0x1800184a2  mov     rdx, [rbp+8F0h+var_918]
0x1800184a6  lea     rcx, [rbp+8F0h+var_940]
0x1800184aa  mov     [rdx+20h], edi
0x1800184ad  add     rdx, 30h ; '0'
0x1800184b1  call    CopyAndMergeIfLists
0x1800184b6  test    r15d, r15d
0x1800184b9  jz      short loc_1800184CE
0x1800184bb  mov     ecx, cs:dword_18002B934
0x1800184c1  xor     edx, edx
0x1800184c3  dec     ecx
0x1800184c5  mov     eax, r15d
0x1800184c8  div     ecx
0x1800184ca  add     edx, edi
0x1800184cc  jmp     short loc_1800184D0
0x1800184ce  mov     edx, esi
0x1800184d0  mov     ecx, edx
0x1800184d2  lea     r9, [rbp+8F0h+var_910]
0x1800184d6  shl     rcx, 4
0x1800184da  mov     edx, r15d
0x1800184dd  add     rcx, 58h ; 'X'
0x1800184e1  mov     dword ptr [rsp+9F0h+plpszSubStringArray], edi
0x1800184e5  add     rcx, rbx
0x1800184e8  mov     [rbp+8F0h+var_8F0], rcx
0x1800184ec  call    FindSourceEntry
0x1800184f1  mov     rsi, [rbp+8F0h+var_910]
0x1800184f5  mov     r12d, eax
0x1800184f8  test    eax, eax
0x1800184fa  jz      short loc_18001850C
0x1800184fc  lea     rdx, [rsi+30h]
0x180018500  mov     [rsi+20h], edi
0x180018503  lea     rcx, [rbp+8F0h+var_940]
0x180018507  call    CopyAndMergeIfLists
0x18001850c  mov     rcx, qword ptr [rbp+8F0h+var_940]
0x180018510  lea     rax, [rbp+8F0h+var_940]
  ... truncated ...
```
