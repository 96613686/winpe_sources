# TcpCreateAndConnectTcbWorkQueueRoutine

- ea: `0x140021b50`
- end: `0x14002222b`
- name: `TcpCreateAndConnectTcbWorkQueueRoutine`
- size: `1755`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140106a40`

## callees

- `0x14001ea80`
- `0x14001fdc0`
- `0x1400201e0`
- `0x140021af8`
- `0x140021b50`
- `0x140022240`
- `0x1400222a0`
- `0x140022470`
- `0x140022780`
- `0x140049000`
- `0x1400579c0`
- `0x14005d040`
- `0x140071ac0`
- `0x140071af0`
- `0x1400f00d0`
- `0x1401c0fd0`
- `0x1401c1200`

## import_xrefs

- `ntoskrnl!KfRaiseIrql` at `0x140022199`
- `ntoskrnl!KfRaiseIrql` at `0x1401c4187`
- `ntoskrnl!KfRaiseIrql` at `0x140022199`
- `ntoskrnl!KfRaiseIrql` at `0x1401c4187`
- `ntoskrnl!KeLowerIrql` at `0x1401c41ed`
- `ntoskrnl!KeLowerIrql` at `0x1401c41ed`
- `ntoskrnl!ObReferenceSecurityDescriptor` at `0x1400220fd`
- `ntoskrnl!ObReferenceSecurityDescriptor` at `0x1400220fd`
- `ntoskrnl!PsGetProcessStartKey` at `0x1401c4127`
- `ntoskrnl!PsGetProcessStartKey` at `0x1401c4127`
- `ntoskrnl!PsGetProcessId` at `0x1401c4105`
- `ntoskrnl!PsGetProcessId` at `0x1401c4105`
- `NETIO!WfpStreamEndpointCleanupBegin` at `0x140022179`
- `NETIO!WfpStreamEndpointCleanupBegin` at `0x140022179`
- `NDIS!NdisGetProcessObjectCompartmentId` at `0x1401c3ea3`
- `NDIS!NdisGetProcessObjectCompartmentId` at `0x1401c3ea3`
- `NDIS!NdisGetThreadObjectCompartmentId` at `0x140022126`
- `NDIS!NdisGetThreadObjectCompartmentId` at `0x140022126`

## pseudocode

```c
__int64 __fastcall TcpCreateAndConnectTcbWorkQueueRoutine(_QWORD *a1)
{
  __int64 v2; // rcx
  __int64 v3; // rbx
  _QWORD *v4; // rax
  _QWORD *v5; // rdi
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // rax
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // rdx
  void (__fastcall *v12)(__int128 *); // rax
  __int64 v13; // rdx
  __int64 (__fastcall *v14)(__int128 *); // rax
  int v15; // eax
  __int64 v16; // rax
  _QWORD *v17; // rcx
  __int64 v18; // rdi
  __int64 v19; // rax
  _DWORD *v20; // rdi
  unsigned int **v21; // r12
  unsigned __int16 v22; // r15
  int Endpoint; // esi
  __int64 v24; // rdx
  __int64 v25; // rax
  __int64 v26; // rax
  int v27; // ecx
  __int64 v28; // rcx
  _QWORD *v29; // r9
  _DWORD *v30; // r8
  __int16 v31; // ax
  int v32; // ecx
  __int64 v33; // rdx
  __int64 v34; // rcx
  __int64 v35; // r8
  __int16 v36; // ax
  __int64 v37; // rdx
  __int16 v38; // cx
  __int64 v39; // rax
  bool v40; // zf
  unsigned int *v41; // rdi
  __int64 result; // rax
  __int64 v43; // rcx
  _QWORD *v44; // r9
  _DWORD *v45; // r8
  __int16 v46; // ax
  int v47; // ecx
  __int64 v48; // rcx
  unsigned int ThreadObjectCompartmentId; // eax
  KIRQL v50; // al
  __int64 v51; // r8
  __int64 v52; // rcx
  __int64 v53; // rdx
  ADDRESS_FAMILY *v54; // r15
  __int64 v55; // rax
  __int64 v56; // rcx
  __int64 v57; // r8
  char v58; // si
  __int64 v59; // rdi
  __int64 v60; // rcx
  ADDRESS_FAMILY *v61; // r10
  UCHAR v62; // al
  int v63; // edx
  __int64 v64; // r8
  __int64 v65; // r10
  __int64 v66; // rax
  ADDRESS_FAMILY *v67; // r11
  UCHAR v68; // al
  _DWORD *v69; // rdx
  int v70; // r8d
  __int64 v71; // r10
  __int64 v72; // r11
  __int64 v73; // rcx
  unsigned int v74; // edx
  __int64 v75; // rdx
  ADDRESS_FAMILY *v76; // r12
  int v77; // r13d
  unsigned __int8 ProcessId; // al
  __int64 v79; // rcx
  char v80; // di
  char ProcessStartKey; // al
  KIRQL v82; // cl
  KIRQL v83; // di
  ADDRESS_FAMILY *v84; // r10
  UCHAR v85; // al
  unsigned __int8 v86; // r8
  const void *v87; // r9
  const void *v88; // r10
  __int16 v89; // dx
  UCHAR v90; // [rsp+68h] [rbp+7h]
  KIRQL v91; // [rsp+69h] [rbp+8h]
  __int128 v92; // [rsp+70h] [rbp+Fh] BYREF
  __int64 v93; // [rsp+80h] [rbp+1Fh]

  do
  {
    v2 = a1[20];
    v3 = (__int64)(a1 - 87);
    v4 = a1;
    v5 = a1;
    a1 = (_QWORD *)*a1;
    *v4 = 0;
    if ( v2 )
      ObReferenceSecurityDescriptor(v2, 1);
    v6 = *(_QWORD **)(v3 + 680);
    v7 = v6[8];
    if ( v7 || v6[9] )
    {
      v8 = v6[9];
      if ( v8 )
      {
        v6[33] = *(_QWORD *)(v8 + 48);
        *(_QWORD *)(*(v5 - 2) + 256LL) = *(_QWORD *)(*(_QWORD *)(*(v5 - 2) + 72LL) + 96LL);
        InetReferenceCompartmentAf(*(_QWORD *)(*(v5 - 2) + 264LL));
        *(_QWORD *)(*(_QWORD *)(v3 + 680) + 240LL) = 0;
      }
      else
      {
        v6[33] = *(_QWORD *)(v7 + 32);
        v9 = *(v5 - 2);
        v93 = 0;
        *(_QWORD *)(v9 + 256) = *(_QWORD *)(*(_QWORD *)(v9 + 64) + 88LL);
        v10 = *(v5 - 2);
        v11 = *(_QWORD *)(v10 + 264);
        *(_QWORD *)&v92 = *(_QWORD *)(v11 + 40);
        *((_QWORD *)&v92 + 1) = *(_QWORD *)(v10 + 256);
        v12 = *(void (__fastcall **)(__int128 *))(*(_QWORD *)(v11 + 48) + 216LL);
        if ( (char *)v12 == (char *)IpNlpReferenceCompartment )
          IpNlpReferenceCompartment(&v92);
        else
          v12(&v92);
        *(_QWORD *)(*(_QWORD *)(v3 + 680) + 240LL) = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v3 + 680) + 64LL) + 248LL);
      }
    }
    else
    {
      v48 = v6[11];
      if ( v48 )
        ThreadObjectCompartmentId = NdisGetThreadObjectCompartmentId(v48);
      else
        ThreadObjectCompartmentId = NdisGetProcessObjectCompartmentId(*(_QWORD *)(v3 + 848));
      v58 = ThreadObjectCompartmentId;
      *(_QWORD *)(*(_QWORD *)(v3 + 680) + 264LL) = *(_QWORD *)(v3 + 24);
      v59 = *(_QWORD *)(v3 + 680);
      result = InetFindAndReferenceCompartmentAf(*(_QWORD *)(v59 + 264), ThreadObjectCompartmentId);
      *(_QWORD *)(v59 + 256) = result;
      v60 = *(_QWORD *)(v3 + 680);
      if ( *(_QWORD *)(v60 + 256) )
      {
        Endpoint = 0;
      }
      else
      {
        if ( dword_1402241D4 )
        {
          if ( !TcpipTraceFiltersExist || (result = *(unsigned __int8 *)(v3 + 804), (result & 0x80u) != 0LL) )
          {
            v92 = 0;
            if ( (BYTE1(WPP_MAIN_CB.Dpc.DeferredRoutine) & 8) != 0 )
            {
              *(_QWORD *)&v92 = v3;
              SOCKADDR_SIZE(*(_WORD *)(v60 + 184));
              v62 = SOCKADDR_SIZE(*v61);
              result = McTemplateK0qbr0qbr2qqqpx_EtwWriteTransfer(
                         (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
                         (unsigned int)TCP_CONNECT_TCB_FAILED_COMPARTMENT_V1,
                         (unsigned int)&v92,
                         v62,
                         v65,
                         v63,
                         v64,
                         0,
                         0,
                         v58,
                         v3,
                         0);
              v60 = *(_QWORD *)(v3 + 680);
            }
          }
        }
        Endpoint = -1073741564;
      }
      *(_QWORD *)(v60 + 240) = 0;
      if ( Endpoint < 0 )
      {
LABEL_38:
        if ( Endpoint == 259 )
          continue;
        goto LABEL_39;
      }
    }
    v13 = *(_QWORD *)(v3 + 24);
    *((_QWORD *)&v92 + 1) = 0;
    HIDWORD(v93) = 0;
    *(_QWORD *)&v92 = *(_QWORD *)(v13 + 40);
    LODWORD(v93) = **(_DWORD **)(*(_QWORD *)(v3 + 680) + 256LL);
    v14 = *(__int64 (__fastcall **)(__int128 *))(*(_QWORD *)(v13 + 48) + 216LL);
    if ( (char *)v14 == (char *)IpNlpReferenceCompartment )
      v15 = IpNlpReferenceCompartment(&v92);
    else
      v15 = v14(&v92);
    if ( v15 < 0 )
    {
      *(_QWORD *)(v3 + 1104) = 0;
LABEL_60:
      if ( dword_1402241D4 && (!TcpipTraceFiltersExist || *(char *)(v3 + 804) < 0) )
      {
        v92 = 0;
        if ( (BYTE1(WPP_MAIN_CB.Dpc.DeferredRoutine) & 8) != 0 )
        {
          v66 = *(_QWORD *)(v3 + 680);
          *(_QWORD *)&v92 = v3;
          SOCKADDR_SIZE(*(_WORD *)(v66 + 184));
          v68 = SOCKADDR_SIZE(*v67);
          McTemplateK0qbr0qbr2qqqpx_EtwWriteTransfer(
            (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
            (unsigned int)TCP_CONNECT_TCB_FAILED_COMPARTMENT_V1,
            (unsigned int)&v92,
            v68,
            v72,
            v70,
            v71,
            0,
            0,
            *v69,
            v3,
            0);
        }
      }
      Endpoint = -1073741564;
      goto LABEL_39;
    }
    v16 = *((_QWORD *)&v92 + 1);
    *(_QWORD *)(v3 + 1104) = *((_QWORD *)&v92 + 1);
    if ( !v16 )
      goto LABEL_60;
    v17 = *(_QWORD **)(v3 + 680);
    v18 = v17[9];
    if ( v18 )
    {
      v20 = *(_DWORD **)(v18 + 88);
    }
    else
    {
      v19 = v17[8];
      if ( v19 )
        v20 = *(_DWORD **)(v19 + 80);
      else
        v20 = 0;
    }
    v21 = (unsigned int **)(v3 + 904);
    v22 = *(_WORD *)(*(_QWORD *)(v3 + 24) + 24LL);
    Endpoint = WfpAleEndpointCreationHandler(
                 v20,
                 v22,
                 1,
                 6,
                 *(_QWORD *)(v3 + 848),
                 v17[11],
                 0,
                 0,
                 (PKSPIN_LOCK *)(v3 + 904));
    if ( Endpoint >= 0 )
    {
      Endpoint = QimInspectCreateEndpoint(v20, *v21, v22, 6);
      if ( Endpoint < 0 )
      {
        WfpStreamEndpointCleanupBegin(*v21);
        WfpAleEndpointTeardownHandler(*v21);
        *v21 = 0;
      }
    }
    if ( dword_1402241D4 )
    {
      v92 = 0;
      if ( (BYTE4(WPP_MAIN_CB.Dpc.DeferredContext) & 8) != 0 )
      {
        *(_QWORD *)&v92 = v3;
        McTemplateK0ppqqq_EtwWriteTransfer(
          &MICROSOFT_TCPIP_PROVIDER_Context,
          INET_INSPECT,
          &v92,
          v3,
          v3 + 904,
          16,
          Endpoint >= 0,
          Endpoint);
      }
    }
    if ( Endpoint >= 0 )
    {
      v24 = *(_QWORD *)(v3 + 680);
      v25 = *(_QWORD *)(v24 + 72);
      if ( v25 )
      {
        if ( (*(_DWORD *)(v25 + 32) & 8) != 0 )
        {
          if ( *(_WORD *)(v24 + 184) == 23 )
          {
            v43 = v24 + 192;
            v44 = (_QWORD *)(v24 + 192);
            v45 = (_DWORD *)(v24 + 188);
          }
          else
          {
            v43 = v24 + 188;
            v45 = (_DWORD *)(v24 + 188);
            v44 = (_QWORD *)(v24 + 192);
          }
          v46 = *(_WORD *)(v24 + 186);
          v47 = *(_DWORD *)(v43 + 12);
          *(_WORD *)(v24 + 184) = 2;
          *(_WORD *)(v24 + 186) = v46;
          *v45 = v47;
          *v44 = 0;
        }
        v55 = *(_QWORD *)(v3 + 680);
        v56 = *(_QWORD *)(v55 + 72);
        v57 = *(_QWORD *)(v56 + 104);
        if ( v57 )
        {
          INETADDR_SETSOCKADDR(
            *(unsigned __int16 *)(v56 + 120),
            v55 + 156,
            **(_QWORD **)(v57 + 16),
            *(_DWORD *)(*(_QWORD *)(v57 + 16) + 8LL),
            *(_WORD *)(v56 + 122));
          goto LABEL_32;
        }
        v89 = *(_WORD *)(v56 + 120);
        if ( !v89 )
          v89 = *(_WORD *)(v55 + 184);
        *(_WORD *)(v55 + 156) = v89;
        v37 = *(_QWORD *)(v3 + 680);
        v38 = *(_WORD *)(*(_QWORD *)(v37 + 72) + 122LL);
      }
      else
      {
        v26 = *(_QWORD *)(v24 + 64);
        if ( !v26 )
          goto LABEL_32;
        v27 = *(_DWORD *)(v26 + 16);
        if ( (v27 & 1) == 0 )
          goto LABEL_32;
        if ( (v27 & 8) != 0 )
        {
          if ( *(_WORD *)(v24 + 184) == 23 )
          {
            v28 = v24 + 192;
            v29 = (_QWORD *)(v24 + 192);
            v30 = (_DWORD *)(v24 + 188);
          }
          else
          {
            v28 = v24 + 188;
            v30 = (_DWORD *)(v24 + 188);
            v29 = (_QWORD *)(v24 + 192);
          }
          v31 = *(_WORD *)(v24 + 186);
          v32 = *(_DWORD *)(v28 + 12);
          *(_WORD *)(v24 + 184) = 2;
          *(_WORD *)(v24 + 186) = v31;
          *v30 = v32;
          *v29 = 0;
        }
        v33 = *(_QWORD *)(v3 + 680);
        v34 = *(_QWORD *)(v33 + 64);
        v35 = *(_QWORD *)(v34 + 96);
        if ( v35 )
        {
          INETADDR_SETSOCKADDR(
            *(unsigned __int16 *)(v34 + 112),
            v33 + 156,
            **(_QWORD **)(v35 + 16),
            *(_DWORD *)(*(_QWORD *)(v35 + 16) + 8LL),
            *(_WORD *)(v34 + 114));
          goto LABEL_32;
        }
        v36 = *(_WORD *)(v34 + 112);
        if ( !v36 )
          v36 = *(_WORD *)(v33 + 184);
        *(_WORD *)(v33 + 156) = v36;
        v37 = *(_QWORD *)(v3 + 680);
        v38 = *(_WORD *)(*(_QWORD *)(v37 + 64) + 114LL);
      }
      *(_WORD *)(v37 + 158) = v38;
LABEL_32:
      v39 = *(_QWORD *)(v3 + 680);
      v40 = *(_WORD *)(v39 + 156) == 2;
      *(_OWORD *)(v39 + 128) = *(_OWORD *)(v39 + 156);
      if ( !v40 )
        *(_OWORD *)(v39 + 140) = *(_OWORD *)(v39 + 168);
      v41 = *v21;
      result = AleInspectConnectRequest(
                 *v21,
                 0,
                 0,
                 (__int64)TcpCreateAndConnectTcbInspectConnectRequestComplete,
                 v3,
                 6,
                 0,
                 (void *)(*(_QWORD *)(v3 + 680) + 156LL),
                 (_WORD *)(*(_QWORD *)(v3 + 680) + 184LL),
                 (_QWORD *)(*(_QWORD *)(v3 + 680) + 216LL),
                 (_BYTE *)(*(_QWORD *)(v3 + 680) + 224LL),
                 0);
      Endpoint = result;
      if ( dword_1402241D4 )
      {
        v92 = 0;
        if ( (BYTE4(WPP_MAIN_CB.Dpc.DeferredContext) & 8) != 0 )
        {
          *(_QWORD *)&v92 = v3;
          result = McTemplateK0ppqqq_EtwWriteTransfer(
                     &MICROSOFT_TCPIP_PROVIDER_Context,
                     INET_INSPECT,
                     &v92,
                     v3,
                     v41,
                     15,
                     (int)result >= 0,
                     result);
        }
      }
      if ( Endpoint >= 0 )
        goto LABEL_38;
      v83 = KfRaiseIrql(2u);
      SOCKADDR_SIZE(*(_WORD *)(*(_QWORD *)(v3 + 680) + 184LL));
      v85 = SOCKADDR_SIZE(*v84);
      TcpRecentFailureTrace(v85, v88, v86, v87, *(struct _KPROCESS **)(v3 + 848), Endpoint, 0, 0xAu);
      v82 = v83;
      goto LABEL_93;
    }
    v50 = KfRaiseIrql(2u);
    v51 = *(_QWORD *)(v3 + 680);
    v91 = v50;
    v52 = *(_QWORD *)(v51 + 72);
    if ( v52 )
    {
      v53 = *(_DWORD *)(v52 + 32) >> 3;
      LOBYTE(v53) = (*(_DWORD *)(v52 + 32) & 8) != 0;
      v54 = (ADDRESS_FAMILY *)InetFormatLocalSockAddrAtDispatchLevel(
                                *(_QWORD *)(v52 + 48),
                                v53,
                                *(_QWORD *)(v52 + 104),
                                *(unsigned __int16 *)(v52 + 122));
    }
    else
    {
      v73 = *(_QWORD *)(v51 + 64);
      if ( v73 && (v74 = *(_DWORD *)(v73 + 16), (v74 & 1) != 0) )
      {
        v75 = v74 >> 3;
        LOBYTE(v75) = v75 & 1;
        v54 = (ADDRESS_FAMILY *)InetFormatLocalSockAddrAtDispatchLevel(
                                  *(_QWORD *)(v73 + 32),
                                  v75,
                                  *(_QWORD *)(v73 + 96),
                                  *(unsigned __int16 *)(v73 + 114));
      }
      else
      {
        v54 = (ADDRESS_FAMILY *)(v51 + 156);
      }
    }
    v76 = (ADDRESS_FAMILY *)(*(_QWORD *)(v3 + 680) + 184LL);
    v77 = SOCKADDR_SIZE(*v76);
    v90 = SOCKADDR_SIZE(*v54);
    TcpRecentFailureTrace(v90, v54, v77, v76, *(struct _KPROCESS **)(v3 + 848), Endpoint, 0, 7u);
    if ( dword_1402241D4 && (!TcpipTraceFiltersExist || *(char *)(v3 + 804) < 0) )
    {
      v92 = 0;
      if ( (BYTE1(WPP_MAIN_CB.Dpc.DeferredRoutine) & 8) != 0 )
      {
        ProcessId = (unsigned __int8)PsGetProcessId(*(PEPROCESS *)(v3 + 848));
        v79 = *(_QWORD *)(v3 + 848);
        v80 = ProcessId;
        v92 = (unsigned __int64)v3;
        ProcessStartKey = PsGetProcessStartKey(v79);
        McTemplateK0qbr0qbr2qqqpx_EtwWriteTransfer(
          (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
          (unsigned int)TCP_CONNECT_TCB_FAILED_INSPECT_V1,
          (unsigned int)&v92,
          v90,
          (__int64)v54,
          v77,
          (__int64)v76,
          Endpoint,
          v80,
          0,
          v3,
          ProcessStartKey);
      }
    }
    v82 = v91;
LABEL_93:
    KeLowerIrql(v82);
LABEL_39:
    result = TcpCreateAndConnectTcbInspectConnectRequestComplete(
               v3,
               Endpoint,
               *(unsigned __int8 *)(*(_QWORD *)(v3 + 680) + 224LL),
               (unsigned int)*(_QWORD *)(v3 + 680) + 156,
               *(_QWORD *)(v3 + 680) + 184LL,
               *(_QWORD *)(*(_QWORD *)(v3 + 680) + 216LL));
  }
  while ( a1 );
  return result;
}

```

## disassembly

```asm
0x140021b50  mov     r11, rsp
0x140021b53  mov     [r11+20h], rbx
0x140021b57  push    rbp
0x140021b58  push    rdi
0x140021b59  push    r13
0x140021b5b  push    r14
0x140021b5d  push    r15
0x140021b5f  lea     rbp, [r11-5Fh]
0x140021b63  sub     rsp, 90h
0x140021b6a  mov     rax, cs:__security_cookie
0x140021b71  xor     rax, rsp
0x140021b74  mov     [rbp+57h+var_30], rax
0x140021b78  mov     [r11+10h], rsi
0x140021b7c  lea     r15, IpNlpReferenceCompartment
0x140021b83  mov     [r11+18h], r12
0x140021b87  mov     r14, rcx
0x140021b8a  xor     r13d, r13d
0x140021b8d  mov     rcx, [r14+0A0h]
0x140021b94  lea     rbx, [r14-2B8h]
0x140021b9b  mov     rax, r14
0x140021b9e  mov     rdi, r14
0x140021ba1  mov     r14, [r14]
0x140021ba4  mov     [rax], r13
0x140021ba7  test    rcx, rcx
0x140021baa  jnz     loc_1400220F8
0x140021bb0  mov     rcx, [rbx+2A8h]
0x140021bb7  mov     rdx, [rcx+40h]
0x140021bbb  test    rdx, rdx
0x140021bbe  jz      loc_14002210E
0x140021bc4  mov     rax, [rcx+48h]
0x140021bc8  test    rax, rax
0x140021bcb  jnz     loc_14002203D
0x140021bd1  mov     rax, [rdx+20h]
0x140021bd5  mov     [rcx+108h], rax
0x140021bdc  mov     rdx, [rdi-10h]
0x140021be0  mov     [rbp+57h+var_38], r13
0x140021be4  mov     rax, [rdx+40h]
0x140021be8  mov     rcx, [rax+58h]
0x140021bec  mov     [rdx+100h], rcx
0x140021bf3  mov     rcx, [rdi-10h]
0x140021bf7  mov     rdx, [rcx+108h]
0x140021bfe  mov     rax, [rdx+28h]
0x140021c02  mov     qword ptr [rbp+57h+var_48], rax
0x140021c06  mov     rax, [rcx+100h]
0x140021c0d  lea     rcx, [rbp+57h+var_48]
0x140021c11  mov     qword ptr [rbp+57h+var_48+8], rax
0x140021c15  mov     rax, [rdx+30h]
0x140021c19  mov     rax, [rax+0D8h]
0x140021c20  cmp     rax, r15
0x140021c23  jnz     loc_140022033
0x140021c29  call    IpNlpReferenceCompartment
0x140021c2e  mov     rdx, [rbx+2A8h]
0x140021c35  mov     rax, [rdx+40h]
0x140021c39  mov     rcx, [rax+0F8h]
0x140021c40  mov     [rdx+0F0h], rcx
0x140021c47  mov     rdx, [rbx+18h]
0x140021c4b  mov     qword ptr [rbp+57h+var_48+8], r13
0x140021c4f  mov     dword ptr [rbp+57h+var_38+4], r13d
0x140021c53  mov     rax, [rdx+28h]
0x140021c57  mov     qword ptr [rbp+57h+var_48], rax
0x140021c5b  mov     rax, [rbx+2A8h]
0x140021c62  mov     rcx, [rax+100h]
0x140021c69  mov     eax, [rcx]
0x140021c6b  lea     rcx, [rbp+57h+var_48]
0x140021c6f  mov     dword ptr [rbp+57h+var_38], eax
0x140021c72  mov     rax, [rdx+30h]
0x140021c76  mov     rax, [rax+0D8h]
0x140021c7d  cmp     rax, r15
0x140021c80  jnz     loc_140022085
0x140021c86  call    IpNlpReferenceCompartment
0x140021c8b  test    eax, eax
0x140021c8d  js      loc_140022138
0x140021c93  mov     rax, qword ptr [rbp+57h+var_48+8]
0x140021c97  mov     [rbx+450h], rax
0x140021c9e  test    rax, rax
0x140021ca1  jz      loc_14002213F
0x140021ca7  mov     rcx, [rbx+2A8h]
0x140021cae  mov     rdi, [rcx+48h]
0x140021cb2  test    rdi, rdi
0x140021cb5  jnz     loc_140021FC4
0x140021cbb  mov     rax, [rcx+40h]
0x140021cbf  test    rax, rax
0x140021cc2  jz      loc_14002216D
0x140021cc8  mov     rdi, [rax+50h]
0x140021ccc  mov     rax, [rbx+18h]
0x140021cd0  lea     r12, [rbx+388h]
0x140021cd7  mov     [rsp+0B0h+var_70], r12
0x140021cdc  mov     r8d, 1
0x140021ce2  mov     [rsp+0B0h+Src], r13
0x140021ce7  mov     r9d, 6
0x140021ced  mov     [rsp+0B0h+var_80], r13
0x140021cf2  movzx   r15d, word ptr [rax+18h]
0x140021cf7  mov     rax, [rcx+58h]
0x140021cfb  movzx   edx, r15w
0x140021cff  mov     qword ptr [rsp+0B0h+var_88], rax
0x140021d04  mov     rcx, rdi
0x140021d07  mov     rax, [rbx+350h]
0x140021d0e  mov     [rsp+0B0h+var_90], rax
0x140021d13  call    WfpAleEndpointCreationHandler
0x140021d18  mov     esi, eax
0x140021d1a  test    eax, eax
0x140021d1c  js      short loc_140021D3E
0x140021d1e  mov     rdx, [r12]
0x140021d22  mov     r9d, 6
0x140021d28  movzx   r8d, r15w
0x140021d2c  mov     rcx, rdi
0x140021d2f  call    QimInspectCreateEndpoint
0x140021d34  mov     esi, eax
0x140021d36  test    eax, eax
0x140021d38  js      loc_140022175
0x140021d3e  cmp     cs:dword_1402241D4, 0
0x140021d45  jnz     loc_140021F52
0x140021d4b  test    esi, esi
0x140021d4d  js      loc_140022197
0x140021d53  mov     rdx, [rbx+2A8h]
0x140021d5a  mov     rax, [rdx+48h]
0x140021d5e  test    rax, rax
0x140021d61  jnz     loc_1400221DF
0x140021d67  mov     rax, [rdx+40h]
0x140021d6b  test    rax, rax
0x140021d6e  jz      loc_140021E08
0x140021d74  mov     ecx, [rax+10h]
0x140021d77  test    cl, 1
0x140021d7a  jz      loc_140021E08
0x140021d80  test    cl, 8
0x140021d83  jz      short loc_140021DC6
0x140021d85  cmp     word ptr [rdx+0B8h], 17h
0x140021d8d  jnz     loc_140021F3C
0x140021d93  lea     rcx, [rdx+0C0h]
0x140021d9a  mov     r9, rcx
0x140021d9d  lea     r8, [rdx+0BCh]
0x140021da4  movzx   eax, word ptr [rdx+0BAh]
0x140021dab  mov     ecx, [rcx+0Ch]
0x140021dae  mov     word ptr [rdx+0B8h], 2
0x140021db7  mov     [rdx+0BAh], ax
0x140021dbe  xor     eax, eax
0x140021dc0  mov     [r8], ecx
0x140021dc3  mov     [r9], rax
0x140021dc6  mov     rdx, [rbx+2A8h]
0x140021dcd  mov     rcx, [rdx+40h]
0x140021dd1  mov     r8, [rcx+60h]
0x140021dd5  test    r8, r8
0x140021dd8  jnz     loc_14002200A
0x140021dde  movzx   eax, word ptr [rcx+70h]
0x140021de2  test    ax, ax
0x140021de5  jz      loc_140021FB8
0x140021deb  mov     [rdx+9Ch], ax
0x140021df2  mov     rdx, [rbx+2A8h]
0x140021df9  mov     rax, [rdx+40h]
0x140021dfd  movzx   ecx, word ptr [rax+72h]
0x140021e01  mov     [rdx+9Eh], cx
0x140021e08  mov     rax, [rbx+2A8h]
0x140021e0f  movups  xmm0, xmmword ptr [rax+9Ch]
0x140021e16  cmp     word ptr [rax+9Ch], 2
0x140021e1e  movups  xmmword ptr [rax+80h], xmm0
0x140021e25  jnz     loc_140021FA5
0x140021e2b  mov     rax, [rbx+2A8h]
0x140021e32  lea     r9, TcpCreateAndConnectTcbInspectConnectRequestComplete
0x140021e39  mov     rdi, [r12]
0x140021e3d  mov     [rsp+58h], r13; __int64
0x140021e42  lea     rcx, [rax+0E0h]
0x140021e49  mov     [rsp+0B0h+var_60], rcx; __int64
0x140021e4e  lea     rdx, [rax+0D8h]
0x140021e55  mov     [rsp+0B0h+var_68], rdx; __int64
0x140021e5a  lea     r8, [rax+0B8h]
0x140021e61  mov     [rsp+0B0h+var_70], r8; void *
0x140021e66  add     rax, 9Ch
0x140021e6c  mov     [rsp+0B0h+Src], rax; Src
0x140021e71  xor     r8d, r8d
0x140021e74  mov     [rsp+0B0h+var_80], r13; __int64
0x140021e79  xor     edx, edx
0x140021e7b  mov     [rsp+0B0h+var_88], 6; int
0x140021e83  mov     rcx, rdi; SpinLock
0x140021e86  mov     [rsp+0B0h+var_90], rbx; __int64
0x140021e8b  call    AleInspectConnectRequest
0x140021e90  cmp     cs:dword_1402241D4, 0
0x140021e97  mov     esi, eax
0x140021e99  jz      short loc_140021EAF
0x140021e9b  test    byte ptr cs:WPP_MAIN_CB.Dpc.DeferredContext+4, 8
0x140021ea2  xorps   xmm0, xmm0
0x140021ea5  movups  [rbp+57h+var_48], xmm0
0x140021ea9  jnz     loc_140021FCD
0x140021eaf  test    esi, esi
0x140021eb1  js      loc_1401C4185
0x140021eb7  lea     r15, IpNlpReferenceCompartment
0x140021ebe  cmp     esi, 103h
0x140021ec4  jz      short loc_140021EFE
0x140021ec6  mov     r8, [rbx+2A8h]
0x140021ecd  mov     edx, esi
0x140021ecf  mov     rax, [r8+0D8h]
0x140021ed6  lea     rcx, [r8+0B8h]
0x140021edd  mov     qword ptr [rsp+0B0h+var_88], rax
0x140021ee2  lea     r9, [r8+9Ch]
0x140021ee9  movzx   r8d, byte ptr [r8+0E0h]
0x140021ef1  mov     [rsp+0B0h+var_90], rcx
0x140021ef6  mov     rcx, rbx
0x140021ef9  call    TcpCreateAndConnectTcbInspectConnectRequestComplete
0x140021efe  test    r14, r14
0x140021f01  jnz     loc_140021B8D
0x140021f07  mov     r12, [rsp+0B0h+arg_10]
0x140021f0f  mov     rsi, [rsp+0B0h+arg_8]
0x140021f17  mov     rcx, [rbp+57h+var_30]
0x140021f1b  xor     rcx, rsp; StackCookie
0x140021f1e  call    __security_check_cookie
0x140021f23  mov     rbx, [rsp+0B0h+arg_18]
0x140021f2b  add     rsp, 90h
0x140021f32  pop     r15
0x140021f34  pop     r14
0x140021f36  pop     r13
0x140021f38  pop     rdi
0x140021f39  pop     rbp
0x140021f3a  retn
0x140021f3c  lea     rcx, [rdx+0BCh]
0x140021f43  mov     r8, rcx
0x140021f46  lea     r9, [rdx+0C0h]
0x140021f4d  jmp     loc_140021DA4
0x140021f52  test    byte ptr cs:WPP_MAIN_CB.Dpc.DeferredContext+4, 8
0x140021f59  xorps   xmm0, xmm0
0x140021f5c  movups  [rbp+57h+var_48], xmm0
0x140021f60  jz      loc_140021D4B
0x140021f66  mov     dword ptr [rsp+0B0h+Src], esi
0x140021f6a  lea     r8, [rbp+57h+var_48]
0x140021f6e  mov     eax, esi
0x140021f70  mov     qword ptr [rbp+57h+var_48], rbx
0x140021f74  not     eax
0x140021f76  lea     rdx, INET_INSPECT
0x140021f7d  shr     eax, 1Fh
0x140021f80  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x140021f87  mov     dword ptr [rsp+0B0h+var_80], eax
0x140021f8b  mov     r9, rbx
0x140021f8e  mov     [rsp+0B0h+var_88], 10h
0x140021f96  mov     [rsp+0B0h+var_90], r12
0x140021f9b  call    McTemplateK0ppqqq_EtwWriteTransfer
0x140021fa0  jmp     loc_140021D4B
0x140021fa5  movups  xmm1, xmmword ptr [rax+0A8h]
0x140021fac  movups  xmmword ptr [rax+8Ch], xmm1
0x140021fb3  jmp     loc_140021E2B
0x140021fb8  movzx   eax, word ptr [rdx+0B8h]
0x140021fbf  jmp     loc_140021DEB
0x140021fc4  mov     rdi, [rdi+58h]
0x140021fc8  jmp     loc_140021CCC
0x140021fcd  mov     dword ptr [rsp+0B0h+Src], esi
0x140021fd1  lea     r8, [rbp+57h+var_48]
0x140021fd5  not     eax
0x140021fd7  mov     qword ptr [rbp+57h+var_48], rbx
0x140021fdb  shr     eax, 1Fh
0x140021fde  lea     rdx, INET_INSPECT
0x140021fe5  mov     dword ptr [rsp+0B0h+var_80], eax
0x140021fe9  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x140021ff0  mov     [rsp+0B0h+var_88], 0Fh
0x140021ff8  mov     r9, rbx
0x140021ffb  mov     [rsp+0B0h+var_90], rdi
0x140022000  call    McTemplateK0ppqqq_EtwWriteTransfer
0x140022005  jmp     loc_140021EAF
0x14002200a  mov     r8, [r8+10h]
0x14002200e  add     rdx, 9Ch
0x140022015  movzx   eax, word ptr [rcx+72h]
0x140022019  movzx   ecx, word ptr [rcx+70h]
0x14002201d  mov     word ptr [rsp+0B0h+var_90], ax
0x140022022  mov     r9d, [r8+8]
0x140022026  mov     r8, [r8]
0x140022029  call    INETADDR_SETSOCKADDR
0x14002202e  jmp     loc_140021E08
0x140022033  call    _guard_dispatch_icall
0x140022038  jmp     loc_140021C2E
0x14002203d  mov     rax, [rax+30h]
0x140022041  mov     [rcx+108h], rax
0x140022048  mov     rdx, [rdi-10h]
0x14002204c  mov     rax, [rdx+48h]
0x140022050  mov     rcx, [rax+60h]
0x140022054  mov     [rdx+100h], rcx
0x14002205b  mov     rcx, [rdi-10h]
0x14002205f  mov     rdx, [rcx+100h]
0x140022066  mov     rcx, [rcx+108h]
0x14002206d  call    _InetReferenceCompartmentAf
0x140022072  mov     rax, [rbx+2A8h]
0x140022079  mov     [rax+0F0h], r13
0x140022080  jmp     loc_140021C47
0x140022085  call    _guard_dispatch_icall
0x14002208a  jmp     loc_140021C8B
0x14002208f  mov     [rcx+0F0h], r13
0x140022096  test    esi, esi
0x140022098  js      loc_140021EBE
0x14002209e  jmp     loc_140021C47
0x1400220a3  cmp     word ptr [rdx+0B8h], 17h
0x1400220ab  jnz     short loc_1400220E5
0x1400220ad  lea     rcx, [rdx+0C0h]
0x1400220b4  mov     r9, rcx
0x1400220b7  lea     r8, [rdx+0BCh]
0x1400220be  movzx   eax, word ptr [rdx+0BAh]
0x1400220c5  mov     ecx, [rcx+0Ch]
0x1400220c8  mov     word ptr [rdx+0B8h], 2
0x1400220d1  mov     [rdx+0BAh], ax
0x1400220d8  xor     eax, eax
0x1400220da  mov     [r8], ecx
0x1400220dd  mov     [r9], rax
0x1400220e0  jmp     loc_1400221EA
0x1400220e5  lea     rcx, [rdx+0BCh]
0x1400220ec  mov     r8, rcx
0x1400220ef  lea     r9, [rdx+0C0h]
  ... truncated ...
```
