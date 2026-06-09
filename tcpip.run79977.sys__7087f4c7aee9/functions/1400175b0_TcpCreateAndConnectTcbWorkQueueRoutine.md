# TcpCreateAndConnectTcbWorkQueueRoutine

- ea: `0x1400175b0`
- end: `0x140017c8b`
- name: `TcpCreateAndConnectTcbWorkQueueRoutine`
- size: `1755`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1400fb040`

## callees

- `0x140017558`
- `0x1400175b0`
- `0x140017ca0`
- `0x140017d00`
- `0x140017ed0`
- `0x1400181e0`
- `0x140019720`
- `0x140019b40`
- `0x14002f4a0`
- `0x14002f4d0`
- `0x14003a5f0`
- `0x140095af0`
- `0x1400b7ca0`
- `0x1400b82e0`
- `0x1400e8870`
- `0x1401bf4d0`
- `0x1401bf700`

## import_xrefs

- `ntoskrnl!KfRaiseIrql` at `0x140017bf9`
- `ntoskrnl!KfRaiseIrql` at `0x1401c1eb7`
- `ntoskrnl!KfRaiseIrql` at `0x140017bf9`
- `ntoskrnl!KfRaiseIrql` at `0x1401c1eb7`
- `ntoskrnl!KeLowerIrql` at `0x1401c1f1d`
- `ntoskrnl!KeLowerIrql` at `0x1401c1f1d`
- `ntoskrnl!ObReferenceSecurityDescriptor` at `0x140017b5d`
- `ntoskrnl!ObReferenceSecurityDescriptor` at `0x140017b5d`
- `ntoskrnl!PsGetProcessStartKey` at `0x1401c1e57`
- `ntoskrnl!PsGetProcessStartKey` at `0x1401c1e57`
- `ntoskrnl!PsGetProcessId` at `0x1401c1e35`
- `ntoskrnl!PsGetProcessId` at `0x1401c1e35`
- `NETIO!WfpStreamEndpointCleanupBegin` at `0x140017bd9`
- `NETIO!WfpStreamEndpointCleanupBegin` at `0x140017bd9`
- `NDIS!NdisGetProcessObjectCompartmentId` at `0x1401c1bd3`
- `NDIS!NdisGetProcessObjectCompartmentId` at `0x1401c1bd3`
- `NDIS!NdisGetThreadObjectCompartmentId` at `0x140017b86`
- `NDIS!NdisGetThreadObjectCompartmentId` at `0x140017b86`

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
  __int64 v20; // rdi
  PKSPIN_LOCK *v21; // r12
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
  PKSPIN_LOCK v41; // rdi
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
  __int64 v86; // r8
  __int64 v87; // r9
  __int64 v88; // r10
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
        if ( dword_1402201D4 )
        {
          if ( !TcpipTraceFiltersExist || (result = *(unsigned __int8 *)(v3 + 804), (result & 0x80u) != 0LL) )
          {
            v92 = 0;
            if ( (BYTE1(WPP_MAIN_CB.Reserved) & 8) != 0 )
            {
              *(_QWORD *)&v92 = v3;
              SOCKADDR_SIZE(*(_WORD *)(v60 + 184));
              v62 = SOCKADDR_SIZE(*v61);
              result = McTemplateK0qbr0qbr2qqqpx_EtwWriteTransfer(
                         (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
                         (unsigned int)&TCP_CONNECT_TCB_FAILED_COMPARTMENT_V1,
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
      if ( dword_1402201D4 && (!TcpipTraceFiltersExist || *(char *)(v3 + 804) < 0) )
      {
        v92 = 0;
        if ( (BYTE1(WPP_MAIN_CB.Reserved) & 8) != 0 )
        {
          v66 = *(_QWORD *)(v3 + 680);
          *(_QWORD *)&v92 = v3;
          SOCKADDR_SIZE(*(_WORD *)(v66 + 184));
          v68 = SOCKADDR_SIZE(*v67);
          McTemplateK0qbr0qbr2qqqpx_EtwWriteTransfer(
            (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
            (unsigned int)&TCP_CONNECT_TCB_FAILED_COMPARTMENT_V1,
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
      v20 = *(_QWORD *)(v18 + 88);
    }
    else
    {
      v19 = v17[8];
      if ( v19 )
        v20 = *(_QWORD *)(v19 + 80);
      else
        v20 = 0;
    }
    v21 = (PKSPIN_LOCK *)(v3 + 904);
    v22 = *(_WORD *)(*(_QWORD *)(v3 + 24) + 24LL);
    Endpoint = WfpAleEndpointCreationHandler(v20, v22, 1, 6, *(_QWORD *)(v3 + 848), v17[11], 0, 0, v3 + 904);
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
    if ( dword_1402201D4 )
    {
      v92 = 0;
      if ( (*((_BYTE *)&WPP_MAIN_CB.Reserved + 12) & 8) != 0 )
      {
        *(_QWORD *)&v92 = v3;
        McTemplateK0ppqqq_EtwWriteTransfer(
          &MICROSOFT_TCPIP_PROVIDER_Context,
          &INET_INSPECT,
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
                 v3,
                 6,
                 0,
                 *(_QWORD *)(v3 + 680) + 156LL,
                 *(_QWORD *)(v3 + 680) + 184LL,
                 *(_QWORD *)(v3 + 680) + 216LL,
                 *(_QWORD *)(v3 + 680) + 224LL,
                 0);
      Endpoint = result;
      if ( dword_1402201D4 )
      {
        v92 = 0;
        if ( (*((_BYTE *)&WPP_MAIN_CB.Reserved + 12) & 8) != 0 )
        {
          *(_QWORD *)&v92 = v3;
          result = McTemplateK0ppqqq_EtwWriteTransfer(
                     &MICROSOFT_TCPIP_PROVIDER_Context,
                     &INET_INSPECT,
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
      TcpRecentFailureTrace(v85, v88, v86, v87, *(_QWORD *)(v3 + 848), Endpoint, 0, 10);
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
    TcpRecentFailureTrace(v90, v54, (unsigned __int8)v77, v76, *(_QWORD *)(v3 + 848), Endpoint, 0, 7);
    if ( dword_1402201D4 && (!TcpipTraceFiltersExist || *(char *)(v3 + 804) < 0) )
    {
      v92 = 0;
      if ( (BYTE1(WPP_MAIN_CB.Reserved) & 8) != 0 )
      {
        ProcessId = (unsigned __int8)PsGetProcessId(*(PEPROCESS *)(v3 + 848));
        v79 = *(_QWORD *)(v3 + 848);
        v80 = ProcessId;
        v92 = (unsigned __int64)v3;
        ProcessStartKey = PsGetProcessStartKey(v79);
        McTemplateK0qbr0qbr2qqqpx_EtwWriteTransfer(
          (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
          (unsigned int)&TCP_CONNECT_TCB_FAILED_INSPECT_V1,
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
0x1400175b0  mov     r11, rsp
0x1400175b3  mov     [r11+20h], rbx
0x1400175b7  push    rbp
0x1400175b8  push    rdi
0x1400175b9  push    r13
0x1400175bb  push    r14
0x1400175bd  push    r15
0x1400175bf  lea     rbp, [r11-5Fh]
0x1400175c3  sub     rsp, 90h
0x1400175ca  mov     rax, cs:__security_cookie
0x1400175d1  xor     rax, rsp
0x1400175d4  mov     [rbp+57h+var_30], rax
0x1400175d8  mov     [r11+10h], rsi
0x1400175dc  lea     r15, IpNlpReferenceCompartment
0x1400175e3  mov     [r11+18h], r12
0x1400175e7  mov     r14, rcx
0x1400175ea  xor     r13d, r13d
0x1400175ed  mov     rcx, [r14+0A0h]
0x1400175f4  lea     rbx, [r14-2B8h]
0x1400175fb  mov     rax, r14
0x1400175fe  mov     rdi, r14
0x140017601  mov     r14, [r14]
0x140017604  mov     [rax], r13
0x140017607  test    rcx, rcx
0x14001760a  jnz     loc_140017B58
0x140017610  mov     rcx, [rbx+2A8h]
0x140017617  mov     rdx, [rcx+40h]
0x14001761b  test    rdx, rdx
0x14001761e  jz      loc_140017B6E
0x140017624  mov     rax, [rcx+48h]
0x140017628  test    rax, rax
0x14001762b  jnz     loc_140017A9D
0x140017631  mov     rax, [rdx+20h]
0x140017635  mov     [rcx+108h], rax
0x14001763c  mov     rdx, [rdi-10h]
0x140017640  mov     [rbp+57h+var_38], r13
0x140017644  mov     rax, [rdx+40h]
0x140017648  mov     rcx, [rax+58h]
0x14001764c  mov     [rdx+100h], rcx
0x140017653  mov     rcx, [rdi-10h]
0x140017657  mov     rdx, [rcx+108h]
0x14001765e  mov     rax, [rdx+28h]
0x140017662  mov     qword ptr [rbp+57h+var_48], rax
0x140017666  mov     rax, [rcx+100h]
0x14001766d  lea     rcx, [rbp+57h+var_48]
0x140017671  mov     qword ptr [rbp+57h+var_48+8], rax
0x140017675  mov     rax, [rdx+30h]
0x140017679  mov     rax, [rax+0D8h]
0x140017680  cmp     rax, r15
0x140017683  jnz     loc_140017A93
0x140017689  call    IpNlpReferenceCompartment
0x14001768e  mov     rdx, [rbx+2A8h]
0x140017695  mov     rax, [rdx+40h]
0x140017699  mov     rcx, [rax+0F8h]
0x1400176a0  mov     [rdx+0F0h], rcx
0x1400176a7  mov     rdx, [rbx+18h]
0x1400176ab  mov     qword ptr [rbp+57h+var_48+8], r13
0x1400176af  mov     dword ptr [rbp+57h+var_38+4], r13d
0x1400176b3  mov     rax, [rdx+28h]
0x1400176b7  mov     qword ptr [rbp+57h+var_48], rax
0x1400176bb  mov     rax, [rbx+2A8h]
0x1400176c2  mov     rcx, [rax+100h]
0x1400176c9  mov     eax, [rcx]
0x1400176cb  lea     rcx, [rbp+57h+var_48]
0x1400176cf  mov     dword ptr [rbp+57h+var_38], eax
0x1400176d2  mov     rax, [rdx+30h]
0x1400176d6  mov     rax, [rax+0D8h]
0x1400176dd  cmp     rax, r15
0x1400176e0  jnz     loc_140017AE5
0x1400176e6  call    IpNlpReferenceCompartment
0x1400176eb  test    eax, eax
0x1400176ed  js      loc_140017B98
0x1400176f3  mov     rax, qword ptr [rbp+57h+var_48+8]
0x1400176f7  mov     [rbx+450h], rax
0x1400176fe  test    rax, rax
0x140017701  jz      loc_140017B9F
0x140017707  mov     rcx, [rbx+2A8h]
0x14001770e  mov     rdi, [rcx+48h]
0x140017712  test    rdi, rdi
0x140017715  jnz     loc_140017A24
0x14001771b  mov     rax, [rcx+40h]
0x14001771f  test    rax, rax
0x140017722  jz      loc_140017BCD
0x140017728  mov     rdi, [rax+50h]
0x14001772c  mov     rax, [rbx+18h]
0x140017730  lea     r12, [rbx+388h]
0x140017737  mov     [rsp+0B0h+var_70], r12
0x14001773c  mov     r8d, 1
0x140017742  mov     [rsp+0B0h+var_78], r13
0x140017747  mov     r9d, 6
0x14001774d  mov     [rsp+0B0h+var_80], r13
0x140017752  movzx   r15d, word ptr [rax+18h]
0x140017757  mov     rax, [rcx+58h]
0x14001775b  movzx   edx, r15w
0x14001775f  mov     [rsp+0B0h+var_88], rax
0x140017764  mov     rcx, rdi
0x140017767  mov     rax, [rbx+350h]
0x14001776e  mov     [rsp+0B0h+var_90], rax
0x140017773  call    WfpAleEndpointCreationHandler
0x140017778  mov     esi, eax
0x14001777a  test    eax, eax
0x14001777c  js      short loc_14001779E
0x14001777e  mov     rdx, [r12]
0x140017782  mov     r9d, 6
0x140017788  movzx   r8d, r15w
0x14001778c  mov     rcx, rdi
0x14001778f  call    QimInspectCreateEndpoint
0x140017794  mov     esi, eax
0x140017796  test    eax, eax
0x140017798  js      loc_140017BD5
0x14001779e  cmp     cs:dword_1402201D4, 0
0x1400177a5  jnz     loc_1400179B2
0x1400177ab  test    esi, esi
0x1400177ad  js      loc_140017BF7
0x1400177b3  mov     rdx, [rbx+2A8h]
0x1400177ba  mov     rax, [rdx+48h]
0x1400177be  test    rax, rax
0x1400177c1  jnz     loc_140017C3F
0x1400177c7  mov     rax, [rdx+40h]
0x1400177cb  test    rax, rax
0x1400177ce  jz      loc_140017868
0x1400177d4  mov     ecx, [rax+10h]
0x1400177d7  test    cl, 1
0x1400177da  jz      loc_140017868
0x1400177e0  test    cl, 8
0x1400177e3  jz      short loc_140017826
0x1400177e5  cmp     word ptr [rdx+0B8h], 17h
0x1400177ed  jnz     loc_14001799C
0x1400177f3  lea     rcx, [rdx+0C0h]
0x1400177fa  mov     r9, rcx
0x1400177fd  lea     r8, [rdx+0BCh]
0x140017804  movzx   eax, word ptr [rdx+0BAh]
0x14001780b  mov     ecx, [rcx+0Ch]
0x14001780e  mov     word ptr [rdx+0B8h], 2
0x140017817  mov     [rdx+0BAh], ax
0x14001781e  xor     eax, eax
0x140017820  mov     [r8], ecx
0x140017823  mov     [r9], rax
0x140017826  mov     rdx, [rbx+2A8h]
0x14001782d  mov     rcx, [rdx+40h]
0x140017831  mov     r8, [rcx+60h]
0x140017835  test    r8, r8
0x140017838  jnz     loc_140017A6A
0x14001783e  movzx   eax, word ptr [rcx+70h]
0x140017842  test    ax, ax
0x140017845  jz      loc_140017A18
0x14001784b  mov     [rdx+9Ch], ax
0x140017852  mov     rdx, [rbx+2A8h]
0x140017859  mov     rax, [rdx+40h]
0x14001785d  movzx   ecx, word ptr [rax+72h]
0x140017861  mov     [rdx+9Eh], cx
0x140017868  mov     rax, [rbx+2A8h]
0x14001786f  movups  xmm0, xmmword ptr [rax+9Ch]
0x140017876  cmp     word ptr [rax+9Ch], 2
0x14001787e  movups  xmmword ptr [rax+80h], xmm0
0x140017885  jnz     loc_140017A05
0x14001788b  mov     rax, [rbx+2A8h]
0x140017892  lea     r9, TcpCreateAndConnectTcbInspectConnectRequestComplete
0x140017899  mov     rdi, [r12]
0x14001789d  mov     [rsp+58h], r13
0x1400178a2  lea     rcx, [rax+0E0h]
0x1400178a9  mov     [rsp+0B0h+var_60], rcx
0x1400178ae  lea     rdx, [rax+0D8h]
0x1400178b5  mov     [rsp+0B0h+var_68], rdx
0x1400178ba  lea     r8, [rax+0B8h]
0x1400178c1  mov     [rsp+0B0h+var_70], r8
0x1400178c6  add     rax, 9Ch
0x1400178cc  mov     [rsp+0B0h+var_78], rax
0x1400178d1  xor     r8d, r8d
0x1400178d4  mov     [rsp+0B0h+var_80], r13
0x1400178d9  xor     edx, edx
0x1400178db  mov     dword ptr [rsp+0B0h+var_88], 6
0x1400178e3  mov     rcx, rdi
0x1400178e6  mov     [rsp+0B0h+var_90], rbx
0x1400178eb  call    AleInspectConnectRequest
0x1400178f0  cmp     cs:dword_1402201D4, 0
0x1400178f7  mov     esi, eax
0x1400178f9  jz      short loc_14001790F
0x1400178fb  test    byte ptr cs:WPP_MAIN_CB+14Ch, 8
0x140017902  xorps   xmm0, xmm0
0x140017905  movups  [rbp+57h+var_48], xmm0
0x140017909  jnz     loc_140017A2D
0x14001790f  test    esi, esi
0x140017911  js      loc_1401C1EB5
0x140017917  lea     r15, IpNlpReferenceCompartment
0x14001791e  cmp     esi, 103h
0x140017924  jz      short loc_14001795E
0x140017926  mov     r8, [rbx+2A8h]
0x14001792d  mov     edx, esi
0x14001792f  mov     rax, [r8+0D8h]
0x140017936  lea     rcx, [r8+0B8h]
0x14001793d  mov     [rsp+0B0h+var_88], rax
0x140017942  lea     r9, [r8+9Ch]
0x140017949  movzx   r8d, byte ptr [r8+0E0h]
0x140017951  mov     [rsp+0B0h+var_90], rcx
0x140017956  mov     rcx, rbx
0x140017959  call    TcpCreateAndConnectTcbInspectConnectRequestComplete
0x14001795e  test    r14, r14
0x140017961  jnz     loc_1400175ED
0x140017967  mov     r12, [rsp+0B0h+arg_10]
0x14001796f  mov     rsi, [rsp+0B0h+arg_8]
0x140017977  mov     rcx, [rbp+57h+var_30]
0x14001797b  xor     rcx, rsp; StackCookie
0x14001797e  call    __security_check_cookie
0x140017983  mov     rbx, [rsp+0B0h+arg_18]
0x14001798b  add     rsp, 90h
0x140017992  pop     r15
0x140017994  pop     r14
0x140017996  pop     r13
0x140017998  pop     rdi
0x140017999  pop     rbp
0x14001799a  retn
0x14001799c  lea     rcx, [rdx+0BCh]
0x1400179a3  mov     r8, rcx
0x1400179a6  lea     r9, [rdx+0C0h]
0x1400179ad  jmp     loc_140017804
0x1400179b2  test    byte ptr cs:WPP_MAIN_CB+14Ch, 8
0x1400179b9  xorps   xmm0, xmm0
0x1400179bc  movups  [rbp+57h+var_48], xmm0
0x1400179c0  jz      loc_1400177AB
0x1400179c6  mov     dword ptr [rsp+0B0h+var_78], esi
0x1400179ca  lea     r8, [rbp+57h+var_48]
0x1400179ce  mov     eax, esi
0x1400179d0  mov     qword ptr [rbp+57h+var_48], rbx
0x1400179d4  not     eax
0x1400179d6  lea     rdx, INET_INSPECT
0x1400179dd  shr     eax, 1Fh
0x1400179e0  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x1400179e7  mov     dword ptr [rsp+0B0h+var_80], eax
0x1400179eb  mov     r9, rbx
0x1400179ee  mov     dword ptr [rsp+0B0h+var_88], 10h
0x1400179f6  mov     [rsp+0B0h+var_90], r12
0x1400179fb  call    McTemplateK0ppqqq_EtwWriteTransfer
0x140017a00  jmp     loc_1400177AB
0x140017a05  movups  xmm1, xmmword ptr [rax+0A8h]
0x140017a0c  movups  xmmword ptr [rax+8Ch], xmm1
0x140017a13  jmp     loc_14001788B
0x140017a18  movzx   eax, word ptr [rdx+0B8h]
0x140017a1f  jmp     loc_14001784B
0x140017a24  mov     rdi, [rdi+58h]
0x140017a28  jmp     loc_14001772C
0x140017a2d  mov     dword ptr [rsp+0B0h+var_78], esi
0x140017a31  lea     r8, [rbp+57h+var_48]
0x140017a35  not     eax
0x140017a37  mov     qword ptr [rbp+57h+var_48], rbx
0x140017a3b  shr     eax, 1Fh
0x140017a3e  lea     rdx, INET_INSPECT
0x140017a45  mov     dword ptr [rsp+0B0h+var_80], eax
0x140017a49  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x140017a50  mov     dword ptr [rsp+0B0h+var_88], 0Fh
0x140017a58  mov     r9, rbx
0x140017a5b  mov     [rsp+0B0h+var_90], rdi
0x140017a60  call    McTemplateK0ppqqq_EtwWriteTransfer
0x140017a65  jmp     loc_14001790F
0x140017a6a  mov     r8, [r8+10h]
0x140017a6e  add     rdx, 9Ch
0x140017a75  movzx   eax, word ptr [rcx+72h]
0x140017a79  movzx   ecx, word ptr [rcx+70h]
0x140017a7d  mov     word ptr [rsp+0B0h+var_90], ax
0x140017a82  mov     r9d, [r8+8]
0x140017a86  mov     r8, [r8]
0x140017a89  call    INETADDR_SETSOCKADDR
0x140017a8e  jmp     loc_140017868
0x140017a93  call    _guard_dispatch_icall
0x140017a98  jmp     loc_14001768E
0x140017a9d  mov     rax, [rax+30h]
0x140017aa1  mov     [rcx+108h], rax
0x140017aa8  mov     rdx, [rdi-10h]
0x140017aac  mov     rax, [rdx+48h]
0x140017ab0  mov     rcx, [rax+60h]
0x140017ab4  mov     [rdx+100h], rcx
0x140017abb  mov     rcx, [rdi-10h]
0x140017abf  mov     rdx, [rcx+100h]
0x140017ac6  mov     rcx, [rcx+108h]
0x140017acd  call    _InetReferenceCompartmentAf
0x140017ad2  mov     rax, [rbx+2A8h]
0x140017ad9  mov     [rax+0F0h], r13
0x140017ae0  jmp     loc_1400176A7
0x140017ae5  call    _guard_dispatch_icall
0x140017aea  jmp     loc_1400176EB
0x140017aef  mov     [rcx+0F0h], r13
0x140017af6  test    esi, esi
0x140017af8  js      loc_14001791E
0x140017afe  jmp     loc_1400176A7
0x140017b03  cmp     word ptr [rdx+0B8h], 17h
0x140017b0b  jnz     short loc_140017B45
0x140017b0d  lea     rcx, [rdx+0C0h]
0x140017b14  mov     r9, rcx
0x140017b17  lea     r8, [rdx+0BCh]
0x140017b1e  movzx   eax, word ptr [rdx+0BAh]
0x140017b25  mov     ecx, [rcx+0Ch]
0x140017b28  mov     word ptr [rdx+0B8h], 2
0x140017b31  mov     [rdx+0BAh], ax
0x140017b38  xor     eax, eax
0x140017b3a  mov     [r8], ecx
0x140017b3d  mov     [r9], rax
0x140017b40  jmp     loc_140017C4A
0x140017b45  lea     rcx, [rdx+0BCh]
0x140017b4c  mov     r8, rcx
0x140017b4f  lea     r9, [rdx+0C0h]
  ... truncated ...
```
