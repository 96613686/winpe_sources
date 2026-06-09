# TcpCreateAndConnectTcbComplete

- ea: `0x140122ba0`
- end: `0x1401237d8`
- name: `TcpCreateAndConnectTcbComplete`
- size: `3128`
- prototype: `__int64 __fastcall(PKSPIN_LOCK SpinLock)`
- caller_count: `2`
- callee_count: `14`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14005881c`
- `0x140122b18`

## callees

- `0x140009680`
- `0x14000b6ac`
- `0x14000f330`
- `0x14001ea80`
- `0x14001eb30`
- `0x14003de94`
- `0x140040d18`
- `0x1400579c0`
- `0x14005881c`
- `0x140071ac0`
- `0x1400b0a40`
- `0x140122ba0`
- `0x1401c0fd0`
- `0x1401c1200`

## import_xrefs

- `ntoskrnl!PsGetThreadId` at `0x140122e34`
- `ntoskrnl!PsGetThreadId` at `0x140122e34`
- `ntoskrnl!ExNotifyCallback` at `0x1401230be`
- `ntoskrnl!ExNotifyCallback` at `0x1401230be`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140122c18`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1401235c7`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1401236dc`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1401237a1`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140122c18`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1401235c7`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1401236dc`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1401237a1`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140122c3c`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140123307`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1401235f1`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14012372c`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140122c3c`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140123307`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1401235f1`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14012372c`
- `ntoskrnl!PsGetProcessStartKey` at `0x140122d4b`
- `ntoskrnl!PsGetProcessStartKey` at `0x140123156`
- `ntoskrnl!PsGetProcessStartKey` at `0x14012326b`
- `ntoskrnl!PsGetProcessStartKey` at `0x14012340d`
- `ntoskrnl!PsGetProcessStartKey` at `0x14012350c`
- `ntoskrnl!PsGetProcessStartKey` at `0x140122d4b`
- `ntoskrnl!PsGetProcessStartKey` at `0x140123156`
- `ntoskrnl!PsGetProcessStartKey` at `0x14012326b`
- `ntoskrnl!PsGetProcessStartKey` at `0x14012340d`
- `ntoskrnl!PsGetProcessStartKey` at `0x14012350c`
- `ntoskrnl!PsGetProcessId` at `0x140122cc1`
- `ntoskrnl!PsGetProcessId` at `0x140122e03`
- `ntoskrnl!PsGetProcessId` at `0x140123120`
- `ntoskrnl!PsGetProcessId` at `0x14012320d`
- `ntoskrnl!PsGetProcessId` at `0x1401233ef`
- `ntoskrnl!PsGetProcessId` at `0x1401234b2`
- `ntoskrnl!PsGetProcessId` at `0x140122cc1`
- `ntoskrnl!PsGetProcessId` at `0x140122e03`
- `ntoskrnl!PsGetProcessId` at `0x140123120`
- `ntoskrnl!PsGetProcessId` at `0x14012320d`
- `ntoskrnl!PsGetProcessId` at `0x1401233ef`
- `ntoskrnl!PsGetProcessId` at `0x1401234b2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401236cd`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401236cd`
- `ntoskrnl!EtwWriteTransfer` at `0x140123015`
- `ntoskrnl!EtwWriteTransfer` at `0x140123015`
- `NETIO!RtlDeleteElementGenericTableBasicAvl` at `0x140122c2d`
- `NETIO!RtlDeleteElementGenericTableBasicAvl` at `0x140122c2d`

## pseudocode

```c
void __fastcall TcpCreateAndConnectTcbComplete(unsigned int *SpinLock, int a2)
{
  KSPIN_LOCK v2; // r12
  unsigned int *v3; // rdi
  __int64 v4; // rax
  int v5; // r13d
  KSPIN_LOCK *v6; // rbx
  int v7; // ebx
  unsigned __int16 v8; // si
  HANDLE v9; // rax
  __int64 v10; // r9
  __int64 v11; // r10
  int v12; // ecx
  __int64 v13; // r9
  int v14; // ecx
  const UCHAR *v15; // r14
  __int64 v16; // rcx
  UCHAR v17; // si
  int v18; // r14d
  __int64 v19; // rcx
  _QWORD *v20; // rbx
  char v21; // di
  __int64 v22; // rax
  struct _KTHREAD *v23; // rcx
  unsigned int ThreadId; // eax
  __int16 v25; // r10
  int v26; // r8d
  __int64 v27; // rcx
  const IN_ADDR **v28; // rax
  const IN_ADDR *v29; // rdx
  struct $::$38AB66A4EA7C49F20D686D738A108FEA::$013671E5920392F7B68C675C97F9F7D8 v30; // eax
  void *v31; // r9
  __int64 v32; // rax
  __int64 v33; // rax
  __int64 v34; // r10
  __int64 v35; // r9
  int v36; // ebx
  __int16 v37; // cx
  bool v38; // zf
  __int16 v39; // cx
  unsigned int v40; // edx
  int v41; // eax
  unsigned int v42; // edx
  __int64 v43; // rax
  __int64 v44; // rcx
  __int16 v45; // dx
  __int16 v46; // ax
  _QWORD *v47; // rbx
  __int64 *v48; // rdx
  __int64 v49; // rax
  __int64 v50; // r8
  __int64 v51; // rcx
  unsigned __int8 v52; // al
  ADDRESS_FAMILY v53; // cx
  char v54; // si
  int v55; // ebx
  char v56; // al
  int v57; // esi
  ADDRESS_FAMILY v58; // r14
  bool v59; // r12
  unsigned __int8 ProcessId; // r13
  __int64 v61; // rax
  __int64 v62; // rcx
  __int64 v63; // r15
  _QWORD *v64; // rbx
  char ProcessStartKey; // di
  int v66; // r14d
  int v67; // esi
  __int64 v68; // rax
  int v69; // esi
  unsigned __int8 v70; // al
  unsigned __int8 v71; // al
  __int64 v72; // rcx
  char v73; // bl
  char v74; // al
  int v75; // esi
  bool v76; // r12
  char v77; // r13
  __int64 v78; // rax
  __int64 v79; // rcx
  __int64 v80; // r15
  _QWORD *v81; // rbx
  char v82; // di
  int v83; // r14d
  ADDRESS_FAMILY v84; // dx
  int v85; // esi
  __int64 v86; // rax
  unsigned int v87; // r14d
  _DWORD *v88; // rbx
  __int16 v89; // cx
  bool v90; // cf
  const wchar_t *v91; // rcx
  __int64 v92; // rax
  int UserDataCount; // [rsp+20h] [rbp-E0h]
  int UserDataCounta; // [rsp+20h] [rbp-E0h]
  __int16 UserData; // [rsp+28h] [rbp-D8h]
  char v96; // [rsp+40h] [rbp-C0h]
  char v97; // [rsp+58h] [rbp-A8h]
  char v98; // [rsp+58h] [rbp-A8h]
  char v99; // [rsp+58h] [rbp-A8h]
  unsigned __int8 v100; // [rsp+60h] [rbp-A0h]
  __int16 v101; // [rsp+64h] [rbp-9Ch] BYREF
  __int64 v102; // [rsp+68h] [rbp-98h] BYREF
  unsigned int *v103; // [rsp+70h] [rbp-90h]
  int v104; // [rsp+78h] [rbp-88h]
  int v105; // [rsp+7Ch] [rbp-84h]
  HANDLE v106; // [rsp+80h] [rbp-80h]
  _WORD Argument2[2]; // [rsp+88h] [rbp-78h] BYREF
  int v108; // [rsp+8Ch] [rbp-74h]
  int v109; // [rsp+90h] [rbp-70h]
  __m256i v110; // [rsp+94h] [rbp-6Ch]
  int v111; // [rsp+B4h] [rbp-4Ch]
  __int64 v112; // [rsp+B8h] [rbp-48h] BYREF
  PVOID P; // [rsp+C0h] [rbp-40h]
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+C8h] [rbp-38h] BYREF
  __int128 v115; // [rsp+D8h] [rbp-28h] BYREF
  __int128 v116; // [rsp+E8h] [rbp-18h] BYREF
  char v117; // [rsp+F8h] [rbp-8h]
  struct _EVENT_DATA_DESCRIPTOR v118; // [rsp+100h] [rbp+0h] BYREF
  int *v119; // [rsp+110h] [rbp+10h]
  int v120; // [rsp+118h] [rbp+18h]
  int v121; // [rsp+11Ch] [rbp+1Ch]
  __int64 *v122; // [rsp+120h] [rbp+20h]
  __int64 v123; // [rsp+128h] [rbp+28h]
  __int128 *v124; // [rsp+130h] [rbp+30h]
  __int64 v125; // [rsp+138h] [rbp+38h]
  _DWORD *v126; // [rsp+140h] [rbp+40h]
  __int64 v127; // [rsp+148h] [rbp+48h]
  __int64 v128; // [rsp+150h] [rbp+50h]
  _DWORD v129[2]; // [rsp+158h] [rbp+58h] BYREF
  _DWORD *v130; // [rsp+160h] [rbp+60h]
  __int64 v131; // [rsp+168h] [rbp+68h]
  __int64 v132; // [rsp+170h] [rbp+70h]
  _DWORD v133[2]; // [rsp+178h] [rbp+78h] BYREF
  __int16 *v134; // [rsp+180h] [rbp+80h]
  __int64 v135; // [rsp+188h] [rbp+88h]
  __int64 *v136; // [rsp+190h] [rbp+90h]
  __int64 v137; // [rsp+198h] [rbp+98h]

  v2 = *((_QWORD *)SpinLock + 85);
  v117 = 0;
  v3 = SpinLock;
  v100 = 0;
  v4 = SpinLock[168];
  v116 = 0;
  v103 = SpinLock;
  v5 = a2;
  v6 = (KSPIN_LOCK *)((char *)TcpCreateAndConnectTcbCancelQueue + 120 * v4);
  *((_QWORD *)SpinLock + 85) = 0;
  v105 = a2;
  P = (PVOID)v2;
  KeAcquireSpinLockAtDpcLevel(v6);
  RtlDeleteElementGenericTableBasicAvl(v6 + 2, v2 + 16);
  KeReleaseSpinLockFromDpcLevel(v6);
  v104 = 23;
  if ( v5 < 0 )
  {
    v47 = v3 + 8;
    *(_QWORD *)&v115 = v3 + 8;
    if ( *((_QWORD *)v3 + 4) )
    {
      if ( dword_1402241D4 && (!TcpipTraceFiltersExist || *((char *)v3 + 804) < 0) )
      {
        EventDescriptor = 0;
        if ( (BYTE1(WPP_MAIN_CB.Dpc.DeferredRoutine) & 8) != 0 )
        {
          v57 = v3[30] & 8;
          if ( v57 )
          {
            v58 = 23;
            LODWORD(v102) = 23;
          }
          else
          {
            v58 = *(_WORD *)(*((_QWORD *)v3 + 3) + 24LL);
            LODWORD(v102) = v58;
          }
          v59 = v57 != 0;
          ProcessId = (unsigned __int8)PsGetProcessId(*((PEPROCESS *)v3 + 106));
          v61 = InetFormatSockAddrAtDispatchLevel(
                  *(unsigned __int16 *)(*((_QWORD *)v3 + 3) + 24LL),
                  v57 != 0,
                  1,
                  *(_QWORD *)(*v47 + 16LL),
                  *(_DWORD *)(*v47 + 8LL),
                  *((_WORD *)v3 + 59));
          v62 = *((_QWORD *)v3 + 106);
          v63 = v61;
          v64 = (_QWORD *)*v47;
          EventDescriptor.Keyword = 0;
          *(_QWORD *)&EventDescriptor.Id = v3;
          ProcessStartKey = PsGetProcessStartKey(v62);
          v66 = SOCKADDR_SIZE(v58);
          v67 = SOCKADDR_SIZE(v102);
          v68 = InetFormatLocalSockAddrAtDispatchLevel(
                  *((_QWORD *)v103 + 3),
                  v59,
                  *v64,
                  *((unsigned __int16 *)v103 + 58));
          v98 = ProcessStartKey;
          v3 = v103;
          v96 = ProcessId;
          v5 = v105;
          McTemplateK0qbr0qbr2qqqpx_EtwWriteTransfer(
            (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
            (unsigned int)TCP_CONNECT_TCB_FAILURE_V1,
            (unsigned int)&EventDescriptor,
            v67,
            v68,
            v66,
            v63,
            v105,
            v96,
            0,
            (char)v103,
            v98);
          v47 = v103 + 8;
        }
      }
    }
    else if ( dword_1402241D4 && (!TcpipTraceFiltersExist || *((char *)v3 + 804) < 0) )
    {
      EventDescriptor = 0;
      if ( (BYTE1(WPP_MAIN_CB.Dpc.DeferredRoutine) & 8) != 0 )
      {
        v52 = (unsigned __int8)PsGetProcessId(*((PEPROCESS *)v3 + 106));
        *(_QWORD *)&EventDescriptor.Id = v3;
        v53 = *(_WORD *)(v2 + 184);
        v54 = v52;
        EventDescriptor.Keyword = 0;
        v55 = SOCKADDR_SIZE(v53);
        v56 = PsGetProcessStartKey(*((_QWORD *)v103 + 106));
        McTemplateK0qbr0qbr2qqqpx_EtwWriteTransfer(
          (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
          (unsigned int)TCP_CONNECT_TCB_FAILURE_V1,
          (unsigned int)&EventDescriptor,
          0,
          0,
          v55,
          v2 + 184,
          v5,
          v54,
          0,
          (char)v103,
          v56);
        v47 = (_QWORD *)v115;
        v3 = v103;
      }
    }
  }
  else
  {
    *((_QWORD *)v3 + 13) = *(_QWORD *)(v2 + 120);
    *((_QWORD *)v3 + 12) = *(_QWORD *)(v2 + 112);
    if ( dword_1402241D4 && (!TcpipTraceFiltersExist || *((char *)v3 + 804) < 0) )
    {
      v115 = 0;
      if ( (BYTE1(WPP_MAIN_CB.Dpc.DeferredRoutine) & 4) != 0 )
      {
        v7 = v3[30] & 8;
        if ( v7 )
          v8 = 23;
        else
          v8 = *(_WORD *)(*((_QWORD *)v3 + 3) + 24LL);
        v9 = PsGetProcessId(*((PEPROCESS *)v3 + 106));
        v10 = *((_QWORD *)v3 + 4);
        v11 = *((_QWORD *)v3 + 3);
        UserData = *((_WORD *)v3 + 59);
        v12 = *(_DWORD *)(v10 + 8);
        v13 = *(_QWORD *)(v10 + 16);
        v106 = v9;
        UserDataCounta = v12;
        v14 = *(unsigned __int16 *)(v11 + 24);
        LOBYTE(v101) = v7 != 0;
        v102 = InetFormatSockAddrAtDispatchLevel(v14, v7 != 0, 1, v13, UserDataCounta, UserData);
        v15 = sockaddr_size;
        if ( v8 >= 0x23u )
        {
          v17 = sockaddr_size[0];
        }
        else
        {
          v16 = v8;
          v17 = sockaddr_size[v8];
          v15 = &sockaddr_size[v16];
        }
        v18 = *v15;
        v19 = *((_QWORD *)v3 + 106);
        v20 = (_QWORD *)*((_QWORD *)v3 + 4);
        v115 = (unsigned __int64)v3;
        v21 = PsGetProcessStartKey(v19);
        v22 = InetFormatLocalSockAddrAtDispatchLevel(
                *((_QWORD *)v103 + 3),
                (unsigned __int8)v101,
                *v20,
                *((unsigned __int16 *)v103 + 58));
        v97 = v21;
        v3 = v103;
        McTemplateK0qbr0qbr2qqqpx_EtwWriteTransfer(
          (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
          (unsigned int)TCP_CONNECT_TCB_COMPLETE_V1,
          (unsigned int)&v115,
          v18,
          v22,
          v17,
          v102,
          0,
          (char)v106,
          0,
          (char)v103,
          v97);
      }
    }
    if ( (unsigned int)dword_140224230 > 4 && (qword_140224240 & 1) != 0 && (qword_140224248 & 1) == qword_140224248 )
    {
      v112 = (unsigned int)PsGetProcessId(*((PEPROCESS *)v3 + 106));
      v23 = *(struct _KTHREAD **)(v2 + 88);
      v122 = &v112;
      v123 = 8;
      if ( v23 )
        ThreadId = (unsigned int)PsGetThreadId(v23);
      else
        ThreadId = 0;
      v25 = *((_WORD *)v3 + 58);
      v26 = v3[30] & 8;
      v27 = *((_QWORD *)v3 + 3);
      *(_QWORD *)&v115 = ThreadId;
      v124 = &v115;
      v28 = (const IN_ADDR **)*((_QWORD *)v3 + 4);
      v125 = 8;
      v29 = *v28;
      if ( *v28 )
      {
        v32 = *(_QWORD *)&v29[4].S_un.S_un_b.s_b1;
        v31 = *(void **)v32;
        v30 = *(struct $::$38AB66A4EA7C49F20D686D738A108FEA::$013671E5920392F7B68C675C97F9F7D8 *)(v32 + 8);
      }
      else
      {
        v29 = &in4addr_any;
        v30 = scopeid_unspecified.0;
        v31 = (void *)&in6addr_any;
        if ( *(_WORD *)(v27 + 24) != 23 )
          v31 = (void *)&in4addr_any;
      }
      LOBYTE(v29) = v26 != 0;
      v33 = ((__int64 (__fastcall *)(_DWORD, _DWORD, _DWORD, _DWORD, _DWORD, __int16))InetFormatSockAddrAtDispatchLevel)(
              *(unsigned __int16 *)(v27 + 24),
              (_DWORD)v29,
              0,
              (_DWORD)v31,
              v30,
              v25);
      v34 = *((_QWORD *)v3 + 3);
      v35 = *((_QWORD *)v3 + 4);
      v36 = 28;
      v37 = *(_WORD *)(v34 + 24);
      v126 = v129;
      v38 = v37 == 23;
      v39 = *((_WORD *)v3 + 59);
      v40 = v3[30];
      v128 = v33;
      v41 = 28;
      if ( !v38 )
        v41 = 16;
      v127 = 2;
      v129[0] = v41;
      v129[1] = 0;
      v42 = v40 >> 3;
      LOBYTE(v42) = v42 & 1;
      v43 = InetFormatSockAddrAtDispatchLevel(
              *(unsigned __int16 *)(v34 + 24),
              v42,
              1,
              *(_QWORD *)(v35 + 16),
              *(_DWORD *)(v35 + 8),
              v39);
      v44 = *((_QWORD *)v3 + 3);
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      EventDescriptor.Keyword = 1;
      v45 = *(_WORD *)(v44 + 24);
      v132 = v43;
      v46 = *((_WORD *)v3 + 58);
      if ( v45 != 23 )
        v36 = 16;
      v130 = v133;
      v101 = __ROR2__(v46, 8);
      v131 = 2;
      v134 = &v101;
      LOWORD(v102) = __ROR2__(*((_WORD *)v3 + 59), 8);
      v136 = &v102;
      *(_DWORD *)&EventDescriptor.Level = 4;
      v118.Ptr = (ULONGLONG)off_140224238;
      v133[0] = v36;
      v133[1] = 0;
      v135 = 2;
      v137 = 2;
      v118.Size = *(unsigned __int16 *)off_140224238;
      v119 = &dword_1401F699C;
      v118.Reserved = 2;
      v120 = 88;
      v121 = 1;
      LODWORD(v106) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EtwWriteTransfer(qword_140224250, &EventDescriptor, 0, 0, 0xAu, &v118);
    }
    v3[30] |= 0x100000u;
    *((_QWORD *)v3 + 69) = &v116;
    v47 = v3 + 8;
    v48 = (__int64 *)*((_QWORD *)v3 + 4);
    v49 = *((_QWORD *)v3 + 3);
    LOBYTE(v116) = 0;
    *(_OWORD *)&v110.m256i_u64[2] = 0;
    v50 = *v48;
    Argument2[0] = *(_WORD *)(v49 + 24);
    *(_OWORD *)v110.m256i_i8 = 0;
    v51 = *(_QWORD *)(v50 + 16);
    LOWORD(v111) = 0;
    Argument2[1] = 0;
    v108 = 3;
    v109 = 5;
    *(__int64 *)((char *)v110.m256i_i64 + 4) = *(_QWORD *)v51;
    *(__int64 *)((char *)&v110.m256i_i64[1] + 4) = v48[2];
    v110.m256i_i32[5] = v3[29];
    v110.m256i_i32[6] = *(_DWORD *)(v51 + 8);
    v110.m256i_i32[7] = *((_DWORD *)v48 + 2);
    v111 = *(_DWORD *)(*(_QWORD *)(v50 + 8) + 8LL);
    ExNotifyCallback(TcpCcbObject, (PVOID)1, Argument2);
  }
  KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)v3);
  if ( (v3[32] & 0x100) != 0 )
  {
    v69 = 0;
    v70 = BYTE1(v3[202]) & 1;
    LODWORD(v102) = 0;
    v100 = v70;
  }
  else
  {
    LOWORD(UserDataCount) = *((_WORD *)v3 + 59);
    v69 = InetInspectConnectComplete(v3, *((_QWORD *)v3 + 113), *v47, *((unsigned __int16 *)v3 + 58), UserDataCount, v5);
    LODWORD(v102) = v69;
  }
  if ( v5 < 0 )
  {
    v87 = v5;
    v69 = v5;
  }
  else
  {
    if ( v69 < 0 )
    {
      if ( *v47 )
      {
        if ( dword_1402241D4 && (!TcpipTraceFiltersExist || *((char *)v3 + 804) < 0) )
        {
          EventDescriptor = 0;
          if ( (BYTE1(WPP_MAIN_CB.Dpc.DeferredRoutine) & 8) != 0 )
          {
            v75 = v3[30] & 8;
            if ( !v75 )
              v104 = *(unsigned __int16 *)(*((_QWORD *)v3 + 3) + 24LL);
            v76 = v75 != 0;
            v77 = (unsigned __int8)PsGetProcessId(*((PEPROCESS *)v3 + 106));
            v78 = InetFormatSockAddrAtDispatchLevel(
                    *(unsigned __int16 *)(*((_QWORD *)v3 + 3) + 24LL),
                    v75 != 0,
                    1,
                    *(_QWORD *)(*v47 + 16LL),
                    *(_DWORD *)(*v47 + 8LL),
                    *((_WORD *)v3 + 59));
            v79 = *((_QWORD *)v3 + 106);
            v80 = v78;
            v81 = (_QWORD *)*v47;
            EventDescriptor.Keyword = 0;
            *(_QWORD *)&EventDescriptor.Id = v3;
            v82 = PsGetProcessStartKey(v79);
            v83 = SOCKADDR_SIZE(v104);
            v85 = SOCKADDR_SIZE(v84);
            v86 = InetFormatLocalSockAddrAtDispatchLevel(
                    *((_QWORD *)v103 + 3),
                    v76,
                    *v81,
                    *((unsigned __int16 *)v103 + 58));
            v99 = v82;
            v3 = v103;
            McTemplateK0qbr0qbr2qqqpx_EtwWriteTransfer(
              (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
              (unsigned int)TCP_CONNECT_TCB_FAILURE_V1,
              (unsigned int)&EventDescriptor,
              v85,
              v86,
              v83,
              v80,
              v102,
              v77,
              0,
              (char)v103,
              v99);
            v69 = v102;
            v5 = v105;
          }
        }
      }
      else if ( dword_1402241D4 && (!TcpipTraceFiltersExist || *((char *)v3 + 804) < 0) )
      {
        EventDescriptor = 0;
        if ( (BYTE1(WPP_MAIN_CB.Dpc.DeferredRoutine) & 8) != 0 )
        {
          v71 = (unsigned __int8)PsGetProcessId(*((PEPROCESS *)v3 + 106));
          v72 = *((_QWORD *)v3 + 106);
          v73 = v71;
          EventDescriptor.Keyword = 0;
          *(_QWORD *)&EventDescriptor.Id = v3;
          v74 = PsGetProcessStartKey(v72);
          McTemplateK0qbr0qbr2qqqpx_EtwWriteTransfer(
            (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
            (unsigned int)TCP_CONNECT_TCB_FAIL_INSPECT_CONNECT_COMPLETE_V1,
            (unsigned int)&EventDescriptor,
            0,
            0,
            0,
            0,
            v69,
            v73,
            0,
            (char)v3,
            v74);
        }
      }
    }
    TcpTraceConnectionEstablishment(v3, 1548);
    v87 = v69;
  }
  KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)v3);
  v3[202] ^= (v3[202] ^ (v100 << 8)) & 0x100;
  KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)v3);
  v88 = P;
  (*(void (__fastcall **)(_QWORD, _QWORD, unsigned int *, __int64 (__fastcall **)()))P)(
    *((_QWORD *)P + 1),
    v87,
    v3,
    TcpTlProviderConnectDispatch);
  v89 = *((_WORD *)v3 + 64);
  if ( (v89 & 0x600) != 0 )
  {
    if ( dword_1402241D4
      && (!TcpipTraceFiltersExist || *((char *)v3 + 804) < 0)
      && (BYTE2(WPP_MAIN_CB.Dpc.DeferredRoutine) & 0x40) != 0 )
    {
      *(_QWORD *)&EventDescriptor.Id = v3;
      v90 = (v89 & 0x200) != 0;
      EventDescriptor.Keyword = 0;
      v91 = L"normal-deferred";
      if ( !v90 )
        v91 = L"inspect-deferred";
      McTemplateK0pzqqp_EtwWriteTransfer(
        (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
        0,
        (unsigned int)&EventDescriptor,
        (_DWORD)v3,
        (__int64)v91,
        v88[86],
        0,
        *((_QWORD *)v88 + 42));
    }
    (*((void (__fastcall **)(_QWORD, _QWORD, _QWORD))v88 + 35))(*((_QWORD *)v88 + 37), v87, *((_QWORD *)v88 + 43));
  }
  ExFreePoolWithTag(v88, 0x52436354u);
  KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)v3);
  if ( v5 >= 0 )
  {
    v3[31] &= ~1u;
    TcpLeaveTcbDelivery((PKSPIN_LOCK)v3);
  }
  if ( v69 < 0 && (v3[31] & 2) == 0 )
  {
    TcpShutdownTcb((PKSPIN_LOCK)v3);
    KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)v3);
    if ( dword_1402241D4
      && (!TcpipTraceFiltersExist || *((char *)v3 + 804) < 0)
      && (BYTE1(WPP_MAIN_CB.Dpc.DeferredRoutine) & 4) != 0 )
    {
      v92 = *((_QWORD *)v3 + 3);
      EventDescriptor.Keyword = 0;
      *(_QWORD *)&EventDescriptor.Id = v3;
      McTemplateK0pqq_EtwWriteTransfer(
        (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
        (unsigned int)TCP_CONNECT_TCB_FAILED_ACTIVE_CONNECT,
        (unsigned int)&EventDescriptor,
        (_DWORD)v3,
        v69,
        *(_WORD *)(v92 + 24));
    }
    TcpCloseTcb((PKSPIN_LOCK)v3);
    KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)v3);
  }
}

```

## disassembly

```asm
0x140122ba0  mov     [rsp-8+arg_10], rbx
0x140122ba5  push    rbp
0x140122ba6  push    rsi
0x140122ba7  push    rdi
0x140122ba8  push    r12
0x140122baa  push    r13
0x140122bac  push    r14
0x140122bae  push    r15
0x140122bb0  lea     rbp, [rsp-0B0h]
0x140122bb8  sub     rsp, 1B0h
0x140122bbf  mov     rax, cs:__security_cookie
0x140122bc6  xor     rax, rsp
0x140122bc9  mov     [rbp+0E0h+var_40], rax
0x140122bd0  mov     r12, [rcx+2A8h]
0x140122bd7  xor     eax, eax
0x140122bd9  mov     [rbp+0E0h+var_E8], al
0x140122bdc  mov     rdi, rcx
0x140122bdf  mov     [rsp+1E0h+var_180], al
0x140122be3  xorps   xmm0, xmm0
0x140122be6  mov     eax, [rcx+2A0h]
0x140122bec  xor     r14d, r14d
0x140122bef  imul    rbx, rax, 78h ; 'x'
0x140122bf3  movups  [rbp+0E0h+var_F8], xmm0
0x140122bf7  mov     [rsp+1E0h+var_170], rcx
0x140122bfc  mov     r13d, edx
0x140122bff  add     rbx, cs:TcpCreateAndConnectTcbCancelQueue
0x140122c06  mov     [rcx+2A8h], r14
0x140122c0d  mov     rcx, rbx; SpinLock
0x140122c10  mov     [rsp+1E0h+var_164], edx
0x140122c14  mov     [rbp+0E0h+P], r12
0x140122c18  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x140122c1f  nop     dword ptr [rax+rax+00h]
0x140122c24  lea     rdx, [r12+10h]
0x140122c29  lea     rcx, [rbx+10h]
0x140122c2d  call    cs:__imp_RtlDeleteElementGenericTableBasicAvl
0x140122c34  nop     dword ptr [rax+rax+00h]
0x140122c39  mov     rcx, rbx; SpinLock
0x140122c3c  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140122c43  nop     dword ptr [rax+rax+00h]
0x140122c48  mov     ecx, 17h
0x140122c4d  mov     [rsp+1E0h+var_168], ecx
0x140122c51  test    r13d, r13d
0x140122c54  js      loc_1401230CF
0x140122c5a  mov     rax, [r12+78h]
0x140122c5f  mov     [rdi+68h], rax
0x140122c63  mov     rax, [r12+70h]
0x140122c68  mov     [rdi+60h], rax
0x140122c6c  cmp     cs:dword_1402241D4, r14d
0x140122c73  jz      loc_140122DC8
0x140122c79  cmp     cs:TcpipTraceFiltersExist, r14b
0x140122c80  jz      short loc_140122C91
0x140122c82  movzx   eax, byte ptr [rdi+324h]
0x140122c89  test    al, al
0x140122c8b  jns     loc_140122DC8
0x140122c91  test    byte ptr cs:WPP_MAIN_CB.Dpc.DeferredRoutine+1, 4
0x140122c98  xorps   xmm0, xmm0
0x140122c9b  movups  [rbp+0E0h+var_108], xmm0
0x140122c9f  jz      loc_140122DC8
0x140122ca5  mov     ebx, [rdi+78h]
0x140122ca8  and     ebx, 8
0x140122cab  jz      short loc_140122CB2
0x140122cad  movzx   esi, cx
0x140122cb0  jmp     short loc_140122CBA
0x140122cb2  mov     rax, [rdi+18h]
0x140122cb6  movzx   esi, word ptr [rax+18h]
0x140122cba  mov     rcx, [rdi+350h]; Process
0x140122cc1  call    cs:__imp_PsGetProcessId
0x140122cc8  nop     dword ptr [rax+rax+00h]
0x140122ccd  mov     r9, [rdi+20h]
0x140122cd1  test    ebx, ebx
0x140122cd3  movzx   edx, word ptr [rdi+76h]
0x140122cd7  mov     r8d, 1
0x140122cdd  mov     r10, [rdi+18h]
0x140122ce1  mov     word ptr [rsp+1E0h+UserData], dx
0x140122ce6  mov     ecx, [r9+8]
0x140122cea  mov     r9, [r9+10h]
0x140122cee  mov     [rbp+0E0h+var_160], rax
0x140122cf2  setnz   al
0x140122cf5  mov     [rsp+1E0h+UserDataCount], ecx
0x140122cf9  movzx   edx, al
0x140122cfc  movzx   ecx, word ptr [r10+18h]
0x140122d01  mov     byte ptr [rsp+1E0h+var_17C], al
0x140122d05  call    InetFormatSockAddrAtDispatchLevel
0x140122d0a  mov     [rsp+1E0h+var_178], rax
0x140122d0f  lea     r14, sockaddr_size
0x140122d16  cmp     si, 23h ; '#'
0x140122d1a  jnb     short loc_140122D29
0x140122d1c  movzx   ecx, si
0x140122d1f  movzx   esi, byte ptr [rcx+r14]
0x140122d24  add     r14, rcx
0x140122d27  jmp     short loc_140122D30
0x140122d29  movzx   esi, cs:sockaddr_size
0x140122d30  movzx   r14d, byte ptr [r14]
0x140122d34  mov     rcx, [rdi+350h]
0x140122d3b  mov     rbx, [rdi+20h]
0x140122d3f  mov     qword ptr [rbp+0E0h+var_108+8], 0
0x140122d47  mov     qword ptr [rbp+0E0h+var_108], rdi
0x140122d4b  call    cs:__imp_PsGetProcessStartKey
0x140122d52  nop     dword ptr [rax+rax+00h]
0x140122d57  mov     r15, [rsp+1E0h+var_170]
0x140122d5c  mov     rdi, rax
0x140122d5f  mov     r8, [rbx]
0x140122d62  movzx   edx, byte ptr [rsp+1E0h+var_17C]
0x140122d67  movzx   esi, sil
0x140122d6b  movzx   r9d, word ptr [r15+74h]
0x140122d70  mov     rcx, [r15+18h]
0x140122d74  call    InetFormatLocalSockAddrAtDispatchLevel
0x140122d79  mov     rcx, [rbp+0E0h+var_160]
0x140122d7d  lea     r8, [rbp+0E0h+var_108]
0x140122d81  mov     [rsp+1E0h+var_188], rdi
0x140122d86  lea     rdx, TCP_CONNECT_TCB_COMPLETE_V1
0x140122d8d  mov     [rsp+1E0h+var_190], r15
0x140122d92  mov     r9d, r14d
0x140122d95  xor     r14d, r14d
0x140122d98  mov     rdi, r15
0x140122d9b  mov     dword ptr [rsp+1E0h+var_198], r14d
0x140122da0  mov     dword ptr [rsp+1E0h+var_1A0], ecx
0x140122da4  mov     rcx, [rsp+1E0h+var_178]
0x140122da9  mov     dword ptr [rsp+1E0h+var_1A8], r14d
0x140122dae  mov     [rsp+1E0h+var_1B0], rcx
0x140122db3  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x140122dba  mov     dword ptr [rsp+1E0h+UserData], esi
0x140122dbe  mov     qword ptr [rsp+1E0h+UserDataCount], rax
0x140122dc3  call    McTemplateK0qbr0qbr2qqqpx_EtwWriteTransfer
0x140122dc8  mov     eax, cs:dword_140224230
0x140122dce  cmp     eax, 4
0x140122dd1  jbe     loc_140123021
0x140122dd7  mov     rcx, cs:qword_140224248
0x140122dde  mov     rax, cs:qword_140224240
0x140122de5  test    al, 1
0x140122de7  jz      loc_140123021
0x140122ded  mov     rax, rcx
0x140122df0  and     eax, 1
0x140122df3  cmp     rax, rcx
0x140122df6  jnz     loc_140123021
0x140122dfc  mov     rcx, [rdi+350h]; Process
0x140122e03  call    cs:__imp_PsGetProcessId
0x140122e0a  nop     dword ptr [rax+rax+00h]
0x140122e0f  mov     ecx, eax
0x140122e11  lea     rax, [rbp+0E0h+var_128]
0x140122e15  mov     [rbp+0E0h+var_128], rcx
0x140122e19  mov     rcx, [r12+58h]; Thread
0x140122e1e  mov     [rbp+0E0h+var_C0], rax
0x140122e22  mov     [rbp+0E0h+var_B8], 8
0x140122e2a  test    rcx, rcx
0x140122e2d  jnz     short loc_140122E34
0x140122e2f  mov     eax, r14d
0x140122e32  jmp     short loc_140122E40
0x140122e34  call    cs:__imp_PsGetThreadId
0x140122e3b  nop     dword ptr [rax+rax+00h]
0x140122e40  mov     r8d, [rdi+78h]
0x140122e44  movzx   r10d, word ptr [rdi+74h]
0x140122e49  and     r8d, 8
0x140122e4d  mov     rcx, [rdi+18h]
0x140122e51  mov     eax, eax
0x140122e53  mov     qword ptr [rbp+0E0h+var_108], rax
0x140122e57  lea     rax, [rbp+0E0h+var_108]
0x140122e5b  mov     [rbp+0E0h+var_B0], rax
0x140122e5f  mov     rax, [rdi+20h]
0x140122e63  mov     [rbp+0E0h+var_A8], 8
0x140122e6b  mov     rdx, [rax]
0x140122e6e  test    rdx, rdx
0x140122e71  jnz     short loc_140122E92
0x140122e73  cmp     word ptr [rcx+18h], 17h
0x140122e78  lea     rdx, in4addr_any
0x140122e7f  mov     eax, dword ptr cs:scopeid_unspecified
0x140122e85  lea     r9, in6addr_any
0x140122e8c  cmovnz  r9, rdx
0x140122e90  jmp     short loc_140122E9C
0x140122e92  mov     rax, [rdx+10h]
0x140122e96  mov     r9, [rax]
0x140122e99  mov     eax, [rax+8]
0x140122e9c  movzx   ecx, word ptr [rcx+18h]
0x140122ea0  test    r8d, r8d
0x140122ea3  mov     word ptr [rsp+1E0h+UserData], r10w
0x140122ea9  setnz   dl
0x140122eac  mov     [rsp+1E0h+UserDataCount], eax
0x140122eb0  xor     r8d, r8d
0x140122eb3  call    InetFormatSockAddrAtDispatchLevel
0x140122eb8  mov     r10, [rdi+18h]
0x140122ebc  lea     rdx, [rbp+0E0h+var_88]
0x140122ec0  mov     r9, [rdi+20h]
0x140122ec4  mov     ebx, 1Ch
0x140122ec9  mov     esi, 10h
0x140122ece  mov     r8d, 1
0x140122ed4  movzx   ecx, word ptr [r10+18h]
0x140122ed9  mov     [rbp+0E0h+var_A0], rdx
0x140122edd  cmp     cx, 17h
0x140122ee1  movzx   ecx, word ptr [rdi+76h]
0x140122ee5  mov     edx, [rdi+78h]
0x140122ee8  mov     [rbp+0E0h+var_90], rax
0x140122eec  mov     eax, ebx
0x140122eee  cmovnz  eax, esi
0x140122ef1  mov     [rbp+0E0h+var_98], 2
0x140122ef9  mov     [rbp+0E0h+var_88], eax
0x140122efc  mov     [rbp+0E0h+var_84], r14d
0x140122f00  mov     eax, [r9+8]
0x140122f04  mov     r9, [r9+10h]
0x140122f08  mov     word ptr [rsp+1E0h+UserData], cx
0x140122f0d  movzx   ecx, word ptr [r10+18h]
0x140122f12  shr     edx, 3
0x140122f15  and     dl, 1
0x140122f18  mov     [rsp+1E0h+UserDataCount], eax
0x140122f1c  call    InetFormatSockAddrAtDispatchLevel
0x140122f21  mov     rcx, [rdi+18h]
0x140122f25  mov     dword ptr [rbp+0E0h+EventDescriptor.Id], 0B000000h
0x140122f2c  mov     [rbp+0E0h+EventDescriptor.Keyword], 1
0x140122f34  movzx   edx, word ptr [rcx+18h]
0x140122f38  lea     rcx, [rbp+0E0h+var_68]
0x140122f3c  mov     [rbp+0E0h+var_70], rax
0x140122f40  cmp     dx, 17h
0x140122f44  movzx   eax, word ptr [rdi+74h]
0x140122f48  lea     rdx, [rbp+0E0h+EventDescriptor]; EventDescriptor
0x140122f4c  cmovnz  ebx, esi
0x140122f4f  mov     [rbp+0E0h+var_80], rcx
0x140122f53  ror     ax, 8
0x140122f57  lea     rcx, _TraceLoggingMetadata
0x140122f5e  mov     [rsp+1E0h+var_17C], ax
0x140122f63  xor     r9d, r9d; RelatedActivityId
0x140122f66  lea     rax, [rsp+1E0h+var_17C]
0x140122f6b  mov     [rbp+0E0h+var_78], 2
0x140122f73  mov     [rbp+0E0h+var_60], rax
0x140122f7a  xor     r8d, r8d; ActivityId
0x140122f7d  movzx   eax, word ptr [rdi+76h]
0x140122f81  ror     ax, 8
0x140122f85  mov     word ptr [rsp+1E0h+var_178], ax
0x140122f8a  lea     rax, [rsp+1E0h+var_178]
0x140122f8f  mov     [rbp+0E0h+var_50], rax
0x140122f96  movzx   eax, cs:word_1401F6992
0x140122f9d  mov     dword ptr [rbp+0E0h+EventDescriptor.Level], eax
0x140122fa0  mov     rax, cs:off_140224238
0x140122fa7  mov     [rbp+0E0h+var_E0.Ptr], rax
0x140122fab  mov     [rbp+0E0h+var_68], ebx
0x140122fae  mov     [rbp+0E0h+var_64], r14d
0x140122fb2  mov     [rbp+0E0h+var_58], 2
0x140122fbd  mov     [rbp+0E0h+var_48], 2
0x140122fc8  movzx   eax, word ptr [rax]
0x140122fcb  mov     [rbp+0E0h+var_E0.Size], eax
0x140122fce  lea     rax, dword_1401F699C
0x140122fd5  mov     [rbp+0E0h+var_D0], rax
0x140122fd9  lea     rax, _TraceLoggingMetadataEnd
0x140122fe0  sub     eax, ecx
0x140122fe2  mov     dword ptr [rbp+0E0h+var_E0.0Ch], 2
0x140122fe9  mov     [rbp+0E0h+var_C8], 58h ; 'X'
0x140122ff0  mov     [rbp+0E0h+var_C4], 1
0x140122ff7  mov     dword ptr [rbp+0E0h+var_160], eax
0x140122ffa  mov     eax, dword ptr [rbp+0E0h+var_160]
0x140122ffd  mov     rcx, cs:qword_140224250; RegHandle
0x140123004  lea     rax, [rbp+0E0h+var_E0]
0x140123008  mov     [rsp+1E0h+UserData], rax; UserData
0x14012300d  mov     [rsp+1E0h+UserDataCount], 0Ah; UserDataCount
0x140123015  call    cs:__imp_EtwWriteTransfer
0x14012301c  nop     dword ptr [rax+rax+00h]
0x140123021  or      dword ptr [rdi+78h], 100000h
0x140123028  lea     rax, [rbp+0E0h+var_F8]
0x14012302c  mov     [rdi+228h], rax
0x140123033  lea     rbx, [rdi+20h]
0x140123037  mov     rdx, [rbx]
0x14012303a  xorps   xmm0, xmm0
0x14012303d  mov     rax, [rdi+18h]
0x140123041  xorps   xmm1, xmm1
0x140123044  mov     byte ptr [rbp+0E0h+var_F8], 0
0x140123048  movdqu  [rbp+0E0h+var_13C], xmm1
0x14012304d  mov     r8, [rdx]
0x140123050  movzx   ecx, word ptr [rax+18h]
0x140123054  mov     [rbp+0E0h+Argument2], cx
0x140123058  movdqu  [rbp+0E0h+var_14C], xmm0
0x14012305d  mov     rcx, [r8+10h]
0x140123061  mov     word ptr [rbp+0E0h+var_12C], r14w
0x140123066  mov     [rbp+0E0h+var_156], r14w
0x14012306b  mov     [rbp+0E0h+var_154], 3
0x140123072  mov     [rbp+0E0h+var_150], 5
0x140123079  mov     rax, [rcx]
0x14012307c  mov     qword ptr [rbp+0E0h+var_14C+4], rax
0x140123080  mov     rax, [rdx+10h]
0x140123084  mov     qword ptr [rbp+0E0h+var_14C+0Ch], rax
0x140123088  movzx   eax, word ptr [rdi+74h]
0x14012308c  mov     word ptr [rbp+0E0h+var_13C+4], ax
0x140123090  movzx   eax, word ptr [rdi+76h]
0x140123094  mov     word ptr [rbp+0E0h+var_13C+6], ax
0x140123098  mov     eax, [rcx+8]
0x14012309b  mov     dword ptr [rbp+0E0h+var_13C+8], eax
0x14012309e  mov     eax, [rdx+8]
0x1401230a1  mov     edx, 1; Argument1
0x1401230a6  mov     dword ptr [rbp+0E0h+var_13C+0Ch], eax
0x1401230a9  mov     rax, [r8+8]
0x1401230ad  lea     r8, [rbp+0E0h+Argument2]; Argument2
0x1401230b1  mov     ecx, [rax+8]
0x1401230b4  mov     [rbp+0E0h+var_12C], ecx
0x1401230b7  mov     rcx, cs:TcpCcbObject; CallbackObject
0x1401230be  call    cs:__imp_ExNotifyCallback
0x1401230c5  nop     dword ptr [rax+rax+00h]
0x1401230ca  jmp     loc_140123304
0x1401230cf  lea     rbx, [rdi+20h]
0x1401230d3  mov     qword ptr [rbp+0E0h+var_108], rbx
0x1401230d7  cmp     [rbx], r14
0x1401230da  jnz     loc_1401231AE
0x1401230e0  cmp     cs:dword_1402241D4, r14d
0x1401230e7  jz      loc_140123304
0x1401230ed  cmp     cs:TcpipTraceFiltersExist, r14b
  ... truncated ...
```
