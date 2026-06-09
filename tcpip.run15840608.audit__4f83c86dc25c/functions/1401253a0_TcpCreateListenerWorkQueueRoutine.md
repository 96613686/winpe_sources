# TcpCreateListenerWorkQueueRoutine

- ea: `0x1401253a0`
- end: `0x140125cd5`
- name: `TcpCreateListenerWorkQueueRoutine`
- size: `2357`
- prototype: ``
- caller_count: `1`
- callee_count: `23`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14011bdb8`

## callees

- `0x14001ea80`
- `0x14001fc70`
- `0x140021af8`
- `0x140022240`
- `0x1400238e0`
- `0x140049760`
- `0x140057040`
- `0x140057768`
- `0x140071ac0`
- `0x14007cf70`
- `0x14009f0f0`
- `0x1400b1824`
- `0x1400b23f8`
- `0x1400b6bc4`
- `0x1400f00d0`
- `0x1400f4050`
- `0x1400f44bc`
- `0x1400fed94`
- `0x1401117e8`
- `0x1401253a0`
- `0x14015c97c`
- `0x140170fe8`
- `0x1401c0fd0`

## import_xrefs

- `ntoskrnl!KfRaiseIrql` at `0x1401255ab`
- `ntoskrnl!KfRaiseIrql` at `0x140125bb1`
- `ntoskrnl!KfRaiseIrql` at `0x1401255ab`
- `ntoskrnl!KfRaiseIrql` at `0x140125bb1`
- `ntoskrnl!KeLowerIrql` at `0x1401255e8`
- `ntoskrnl!KeLowerIrql` at `0x140125c85`
- `ntoskrnl!KeLowerIrql` at `0x1401255e8`
- `ntoskrnl!KeLowerIrql` at `0x140125c85`
- `ntoskrnl!ObReferenceSecurityDescriptor` at `0x1401253e9`
- `ntoskrnl!ObReferenceSecurityDescriptor` at `0x1401253e9`
- `ntoskrnl!PsGetProcessStartKey` at `0x1401254b0`
- `ntoskrnl!PsGetProcessStartKey` at `0x14012563d`
- `ntoskrnl!PsGetProcessStartKey` at `0x1401257fa`
- `ntoskrnl!PsGetProcessStartKey` at `0x1401254b0`
- `ntoskrnl!PsGetProcessStartKey` at `0x14012563d`
- `ntoskrnl!PsGetProcessStartKey` at `0x1401257fa`
- `ntoskrnl!PsGetProcessId` at `0x140125489`
- `ntoskrnl!PsGetProcessId` at `0x14012561a`
- `ntoskrnl!PsGetProcessId` at `0x1401257cc`
- `ntoskrnl!PsGetProcessId` at `0x140125489`
- `ntoskrnl!PsGetProcessId` at `0x14012561a`
- `ntoskrnl!PsGetProcessId` at `0x1401257cc`
- `ntoskrnl!ObfDereferenceObject` at `0x140125b64`
- `ntoskrnl!ObfDereferenceObject` at `0x140125b64`
- `NDIS!NdisGetProcessObjectCompartmentId` at `0x140125434`
- `NDIS!NdisGetProcessObjectCompartmentId` at `0x140125434`
- `NDIS!NdisGetThreadObjectCompartmentId` at `0x14012541a`
- `NDIS!NdisGetThreadObjectCompartmentId` at `0x14012541a`

## pseudocode

```c
_QWORD *__fastcall TcpCreateListenerWorkQueueRoutine(_QWORD *a1)
{
  _QWORD *result; // rax
  _QWORD *v2; // rsi
  __int64 v3; // rcx
  __int64 v4; // r14
  __int64 v5; // rdx
  __int64 *v6; // rbx
  __int64 v7; // rdi
  __int64 v8; // rcx
  unsigned int ThreadObjectCompartmentId; // eax
  PEPROCESS *v10; // r13
  _QWORD *v11; // r12
  __int64 v12; // rax
  int v13; // edx
  int v14; // r9d
  int Endpoint; // r15d
  unsigned __int8 ProcessId; // al
  __int64 v17; // rcx
  char v18; // di
  __int16 v19; // bx
  char ProcessStartKey; // al
  __int64 v21; // rcx
  __int64 v22; // rax
  __int64 v23; // rcx
  KIRQL v24; // bl
  unsigned __int8 v25; // al
  __int64 v26; // rcx
  char v27; // di
  __int16 v28; // bx
  __int64 v29; // rcx
  __int64 v30; // rcx
  __int64 v31; // rcx
  __int64 v32; // rdx
  __int64 v33; // rcx
  int v34; // edx
  unsigned int v35; // eax
  __int64 v36; // r8
  __int64 v37; // rdx
  unsigned __int8 v38; // al
  __int64 v39; // rcx
  char v40; // si
  __int16 v41; // bx
  int v42; // edi
  __int64 v43; // r8
  __int64 v44; // rbx
  __int16 v45; // dx
  __int64 v46; // rax
  char v47; // dl
  int v48; // eax
  int v49; // edx
  __int64 v50; // rax
  __int16 v51; // cx
  __int64 v52; // rax
  _QWORD *CompartmentContext; // rax
  __int64 v54; // rax
  PERESOURCE *v55; // rax
  __int64 v56; // rcx
  int v57; // eax
  __int64 v58; // rcx
  UCHAR v59; // al
  __int64 v60; // r8
  __int64 v61; // r9
  KIRQL v62; // si
  ADDRESS_FAMILY v63; // cx
  UCHAR v64; // al
  __int64 v65; // rdx
  int v66; // ebx
  __int64 v67; // rax
  PEPROCESS v68; // rcx
  __int64 v69; // rdi
  char a; // [rsp+20h] [rbp-69h]
  char aa; // [rsp+20h] [rbp-69h]
  __int16 v72[4]; // [rsp+30h] [rbp-59h]
  char v73; // [rsp+38h] [rbp-51h]
  char v74; // [rsp+50h] [rbp-39h]
  char v75; // [rsp+50h] [rbp-39h]
  char v76; // [rsp+60h] [rbp-29h] BYREF
  unsigned int v77; // [rsp+64h] [rbp-25h] BYREF
  PVOID *v78; // [rsp+68h] [rbp-21h]
  __int64 v79; // [rsp+70h] [rbp-19h] BYREF
  _QWORD *v80; // [rsp+78h] [rbp-11h]
  __int64 v81[2]; // [rsp+80h] [rbp-9h] BYREF

  result = a1;
  do
  {
    v2 = result;
    v3 = *(result - 11);
    v4 = (__int64)(result - 19);
    v80 = (_QWORD *)*result;
    if ( v3 )
      ObReferenceSecurityDescriptor(v3, 1);
    v5 = *(_QWORD *)(v4 + 176);
    if ( v5 )
    {
      v11 = (_QWORD *)(v4 + 48);
      v21 = *(_QWORD *)(v4 + 48);
      *(_QWORD *)(v4 + 96) = *(_QWORD *)(v5 + 88);
      InetReferenceCompartmentAf(v21);
      v22 = *(_QWORD *)(v4 + 176);
      v6 = (__int64 *)(v4 + 192);
      v78 = (PVOID *)(v4 + 192);
      v10 = (PEPROCESS *)(v4 + 56);
      v7 = *(_QWORD *)(v22 + 248);
    }
    else
    {
      v6 = (__int64 *)(v4 + 192);
      v7 = 0;
      v8 = *(_QWORD *)(v4 + 192);
      v78 = (PVOID *)(v4 + 192);
      if ( v8 )
      {
        ThreadObjectCompartmentId = NdisGetThreadObjectCompartmentId(v8);
        v10 = (PEPROCESS *)(v4 + 56);
      }
      else
      {
        v10 = (PEPROCESS *)(v4 + 56);
        ThreadObjectCompartmentId = NdisGetProcessObjectCompartmentId(*(_QWORD *)(v4 + 56));
      }
      v11 = (_QWORD *)(v4 + 48);
      v77 = ThreadObjectCompartmentId;
      v12 = InetFindAndReferenceCompartmentAf(*(_QWORD *)(v4 + 48), ThreadObjectCompartmentId);
      *(_QWORD *)(v4 + 96) = v12;
      if ( v12 )
      {
        Endpoint = 0;
      }
      else
      {
        Endpoint = -1073741564;
        if ( dword_1402241D4 )
        {
          *(_OWORD *)v81 = 0;
          if ( (BYTE4(WPP_MAIN_CB.Dpc.DeferredRoutine) & 0x40) != 0 )
          {
            ProcessId = (unsigned __int8)PsGetProcessId(*v10);
            v17 = *v11;
            v18 = ProcessId;
            v81[1] = 0;
            v81[0] = v4;
            v19 = *(_WORD *)(v17 + 24);
            ProcessStartKey = PsGetProcessStartKey(*v10);
            v73 = v18;
            v7 = 0;
            McTemplateK0pqbr1qqqqx_EtwWriteTransfer(
              (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
              (unsigned int)TCP_LISTENER_ACTIVATION_FAILED_COMPARTMENT_V1,
              (unsigned int)v81,
              v4,
              0,
              0,
              4,
              v73,
              v77,
              v19,
              ProcessStartKey);
            v6 = (__int64 *)v78;
          }
        }
      }
      if ( Endpoint < 0 )
        goto LABEL_61;
    }
    v23 = *(_QWORD *)(v4 + 176);
    if ( v23 )
    {
      v29 = *(_QWORD *)(v23 + 80);
      *(v2 - 8) = v29;
      *(_QWORD *)(v4 + 328) = *(_QWORD *)(v29 + 600);
      *(_QWORD *)(v29 + 600) = v2 + 16;
      *(_QWORD *)(v29 + 352) = v4;
      *(_QWORD *)(*(_QWORD *)(v4 + 176) + 80LL) = 0;
      *(_BYTE *)(v4 + 320) = 1;
    }
    else
    {
      Endpoint = InetInspectCreateEndpoint(
                   v4,
                   0,
                   *(unsigned __int16 *)(*v11 + 24LL),
                   1,
                   6,
                   (__int64)*v10,
                   *v6,
                   (__int64)(v2 + 16),
                   v4,
                   (__int64)(v2 - 8));
      if ( Endpoint < 0 )
      {
        v24 = KfRaiseIrql(2u);
        TcpRecentFailureTrace(0, 0, 0, 0, *v10, Endpoint, 0, 8);
        KeLowerIrql(v24);
        if ( dword_1402241D4 )
        {
          *(_OWORD *)v81 = 0;
          if ( (BYTE4(WPP_MAIN_CB.Dpc.DeferredRoutine) & 0x40) != 0 )
          {
            v25 = (unsigned __int8)PsGetProcessId(*v10);
            v26 = *v11;
            v27 = v25;
            v81[1] = 0;
            v81[0] = v4;
            v28 = *(_WORD *)(v26 + 24);
            v74 = PsGetProcessStartKey(*v10);
            McTemplateK0pqbr1qqqqx_EtwWriteTransfer(
              (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
              (unsigned int)TCP_LISTENER_ACTIVATION_FAILED_INSPECTION1_V1,
              (unsigned int)v81,
              v4,
              0,
              0,
              Endpoint,
              v27,
              0,
              v28,
              v74);
          }
        }
        goto LABEL_61;
      }
    }
    v30 = *(_QWORD *)(v4 + 176);
    if ( v30 && (*(_DWORD *)(v30 + 16) & 1) != 0 )
    {
      *(_WORD *)(v4 + 120) = *(_WORD *)(v30 + 112);
      v31 = *(_QWORD *)(v30 + 104);
      *(_QWORD *)(v4 + 112) = v31;
      if ( v31 != *v11 )
        CarAcquireCacheAwareReference(*(_QWORD *)(v31 + 16), 1);
      v32 = *(_QWORD *)(*(_QWORD *)(v4 + 176) + 96LL);
      *(_QWORD *)(v4 + 104) = v32;
      if ( v32 )
        InetReferenceLocalAddressAf(*(_QWORD *)(v4 + 112));
      v33 = *(_QWORD *)(v4 + 176);
      v34 = *(_DWORD *)(v4 + 32) ^ (*(_DWORD *)(v33 + 16) ^ *(_DWORD *)(v4 + 32)) & 8;
      *(_DWORD *)(v4 + 32) = v34;
      *(_WORD *)(v4 + 122) = *(_WORD *)(v33 + 114);
      v35 = v34 ^ ((unsigned __int8)v34 ^ (unsigned __int8)(8 * *(_DWORD *)(v33 + 16))) & 0x20;
LABEL_42:
      *(_DWORD *)(v4 + 32) = v35;
      v52 = *(_QWORD *)(v4 + 176);
      if ( v52 && (*(_DWORD *)(v52 + 16) & 1) != 0 )
      {
        CompartmentContext = (_QWORD *)InetGetCompartmentContext(TcpCompartmentSet, **(unsigned int **)(v4 + 96));
        InetReplacePortEndpoint(
          *CompartmentContext,
          *(unsigned __int16 *)(v4 + 122),
          *(_QWORD *)(v4 + 176) + 120,
          v4 + 128,
          2);
        if ( dword_1402241D4 )
        {
          *(_OWORD *)v81 = 0;
          if ( (BYTE6(WPP_MAIN_CB.Dpc.DeferredRoutine) & 0x10) != 0 )
          {
            *(_QWORD *)v72 = *(_QWORD *)(v4 + 176);
            a = __ROR2__(*(_WORD *)(v4 + 122), 8);
            v81[0] = v4;
            McTemplateK0phqp_EtwWriteTransfer(
              (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
              (unsigned int)TCP_REPLACE_PORT,
              (unsigned int)v81,
              v4,
              a,
              0,
              v72[0]);
          }
        }
        v54 = *(_QWORD *)(v4 + 176);
        Endpoint = 0;
        *(_BYTE *)(v4 + 185) = 1;
        *(_DWORD *)(v54 + 16) &= ~1u;
        *(_DWORD *)(v4 + 32) |= 1u;
      }
      else
      {
        v55 = (PERESOURCE *)InetGetCompartmentContext(TcpCompartmentSet, *(unsigned int *)*(v2 - 7));
        v56 = *(v2 - 6);
        if ( v7 )
          v57 = InetAcquirePortFromReservation(
                  *v55,
                  v2[5],
                  (__int64)v2 - 30,
                  *((_WORD *)v2 - 16),
                  v56,
                  (__int64)(v2 - 3),
                  2);
        else
          v57 = InetAcquirePort((int)*v55, v2[5], (__int64)v2 - 30, *((_WORD *)v2 - 16), v56, (__int64)(v2 - 3), 2, 0);
        Endpoint = v57;
        if ( v57 < 0 )
        {
          if ( qword_1402284F8 )
            InetTraceFailDataCore(&TcpInetTransport, 1553, (unsigned int)v57);
          if ( dword_1402241D4 )
          {
            *(_OWORD *)v81 = 0;
            if ( (BYTE4(WPP_MAIN_CB.Dpc.DeferredRoutine) & 0x40) != 0 )
            {
              v58 = *v11;
              v81[0] = v4;
              v59 = SOCKADDR_SIZE(*(_WORD *)(v58 + 24));
              McTemplateK0pqbr1qqqqx_EtwWriteTransfer(
                (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
                (unsigned int)TCP_LISTENER_BIND_FAILED_PORT_V1,
                (unsigned int)v81,
                v4,
                v59,
                v60,
                Endpoint,
                0,
                0,
                0,
                0);
            }
          }
        }
        else
        {
          if ( dword_1402241D4 )
          {
            *(_OWORD *)v81 = 0;
            if ( (BYTE6(WPP_MAIN_CB.Dpc.DeferredRoutine) & 0x10) != 0 )
            {
              aa = __ROR2__(*(_WORD *)(v4 + 122), 8);
              v81[0] = v4;
              McTemplateK0phqp_EtwWriteTransfer(
                (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
                (unsigned int)TCP_ACQUIRE_PORT,
                (unsigned int)v81,
                v4,
                aa,
                0,
                0);
            }
          }
          *(_DWORD *)(v4 + 32) |= 1u;
        }
      }
      goto LABEL_61;
    }
    LOBYTE(v14) = *(_BYTE *)(v4 + 274);
    v36 = *(_QWORD *)(v4 + 96);
    v37 = *v11;
    LOWORD(v77) = 0;
    v76 = 0;
    v81[0] = 0;
    v79 = 0;
    LOBYTE(v14) = (v14 & 2) != 0;
    Endpoint = InetResolveSockAddrToLocalAddressAndAf(
                 (int)&TcpInetTransport,
                 v37,
                 v36,
                 v14,
                 *(SOCKADDR_IN6 **)(v4 + 208),
                 (__int64)&v77,
                 (__int64)&v76,
                 (__int64)&v79,
                 (__int64)v81);
    if ( Endpoint >= 0 )
    {
      v43 = v81[0];
      if ( !v81[0] || (unsigned int)(*(_DWORD *)(v81[0] + 24) - 3) > 1 )
      {
        v45 = v77;
        v46 = *v11;
        *(_WORD *)(v4 + 120) = v77;
        if ( v45 != *(_WORD *)(v46 + 24) && v45 )
          WfpAleEndpointUpdateFamily(*(_QWORD *)(v4 + 88));
        v47 = v76;
        *(_QWORD *)(v4 + 112) = v79;
        v48 = *(_DWORD *)(v4 + 32);
        *(_QWORD *)(v4 + 104) = v43;
        v49 = v48 ^ ((unsigned __int8)v48 ^ (unsigned __int8)(8 * v47)) & 8;
        v50 = *(_QWORD *)(v4 + 208);
        *(_DWORD *)(v4 + 32) = v49;
        v51 = *(_WORD *)(v50 + 2);
        *(_WORD *)(v4 + 122) = v51;
        v35 = v49 & 0xFFFFFFDF | (v51 != 0 ? 0x20 : 0);
        goto LABEL_42;
      }
      v44 = v79;
      InetDereferenceLocalAddressAf(v79, v81[0]);
      if ( v44 != *v11 )
        InetDereferenceAf(v44);
      Endpoint = -1073741305;
    }
    else if ( dword_1402241D4 )
    {
      *(_OWORD *)v81 = 0;
      if ( (BYTE4(WPP_MAIN_CB.Dpc.DeferredRoutine) & 0x40) != 0 )
      {
        v38 = (unsigned __int8)PsGetProcessId(*v10);
        v39 = *v11;
        v40 = v38;
        v81[1] = 0;
        v81[0] = v4;
        v41 = *(_WORD *)(v39 + 24);
        v42 = SOCKADDR_SIZE(v41);
        v75 = PsGetProcessStartKey(*v10);
        McTemplateK0pqbr1qqqqx_EtwWriteTransfer(
          (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
          (unsigned int)TCP_LISTENER_BIND_FAILED_RESOLUTION_V1,
          (unsigned int)v81,
          v4,
          v42,
          v4 + 208,
          Endpoint,
          v40,
          0,
          v41,
          v75);
      }
    }
LABEL_61:
    if ( *v78 )
      ObfDereferenceObject(*v78);
    if ( Endpoint >= 0
      && (v61 = *(_QWORD *)(v4 + 88)) != 0
      && (Endpoint = InetInspectListen(v4, v13, v4, v61, *(_QWORD *)(v4 + 104), *(_WORD *)(v4 + 122)), Endpoint < 0) )
    {
      v62 = KfRaiseIrql(2u);
      if ( (*(_DWORD *)(v4 + 32) & 8) != 0 )
        v63 = 23;
      else
        v63 = *(_WORD *)(*v11 + 24LL);
      v64 = SOCKADDR_SIZE(v63);
      LOBYTE(v65) = (_DWORD)v65 != 0;
      v66 = v64;
      v67 = InetFormatLocalSockAddrAtDispatchLevel(*v11, v65, *(_QWORD *)(v4 + 104), *(unsigned __int16 *)(v4 + 122));
      v68 = *v10;
      v69 = v67;
      LOBYTE(v68) = v66;
      TcpRecentFailureTrace(v68, v67, 0, 0, *v10, Endpoint, 0, 3);
      if ( dword_1402241D4 )
      {
        *(_OWORD *)v81 = 0;
        if ( (BYTE4(WPP_MAIN_CB.Dpc.DeferredRoutine) & 0x40) != 0 )
        {
          v81[0] = v4;
          McTemplateK0pqbr1qqqqx_EtwWriteTransfer(
            (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
            (unsigned int)TCP_LISTENER_ACTIVATION_FAILED_INSPECTION2_V1,
            (unsigned int)v81,
            v4,
            v66,
            v69,
            Endpoint,
            0,
            0,
            0,
            0);
        }
      }
      KeLowerIrql(v62);
    }
    else if ( Endpoint == 259 )
    {
      goto LABEL_75;
    }
    TcpCreateListenerInspectComplete(v4, (unsigned int)Endpoint);
LABEL_75:
    result = v80;
  }
  while ( v80 );
  return result;
}

```

## disassembly

```asm
0x1401253a0  push    rbp
0x1401253a2  push    rbx
0x1401253a3  push    rsi
0x1401253a4  push    rdi
0x1401253a5  push    r12
0x1401253a7  push    r13
0x1401253a9  push    r14
0x1401253ab  push    r15
0x1401253ad  lea     rbp, [rsp-1Fh]
0x1401253b2  sub     rsp, 0A8h
0x1401253b9  mov     rax, cs:__security_cookie
0x1401253c0  xor     rax, rsp
0x1401253c3  mov     [rbp+57h+var_50], rax
0x1401253c7  mov     rax, rcx
0x1401253ca  lea     rsi, [rax]
0x1401253cd  mov     rcx, [rsi-58h]
0x1401253d1  lea     r14, [rax-98h]
0x1401253d8  mov     rax, [rax]
0x1401253db  mov     [rbp+57h+var_68], rax
0x1401253df  test    rcx, rcx
0x1401253e2  jz      short loc_1401253F5
0x1401253e4  mov     edx, 1
0x1401253e9  call    cs:__imp_ObReferenceSecurityDescriptor
0x1401253f0  nop     dword ptr [rax+rax+00h]
0x1401253f5  mov     rdx, [r14+0B0h]
0x1401253fc  test    rdx, rdx
0x1401253ff  jnz     loc_140125510
0x140125405  lea     rbx, [r14+0C0h]
0x14012540c  xor     edi, edi
0x14012540e  mov     rcx, [rbx]
0x140125411  mov     [rbp+57h+var_78], rbx
0x140125415  test    rcx, rcx
0x140125418  jz      short loc_14012542C
0x14012541a  call    cs:__imp_NdisGetThreadObjectCompartmentId
0x140125421  nop     dword ptr [rax+rax+00h]
0x140125426  lea     r13, [r14+38h]
0x14012542a  jmp     short loc_140125440
0x14012542c  lea     r13, [r14+38h]
0x140125430  mov     rcx, [r13+0]
0x140125434  call    cs:__imp_NdisGetProcessObjectCompartmentId
0x14012543b  nop     dword ptr [rax+rax+00h]
0x140125440  lea     r12, [r14+30h]
0x140125444  mov     dword ptr [rbp+57h+var_80+4], eax
0x140125447  mov     rcx, [r12]
0x14012544b  mov     edx, eax
0x14012544d  call    _InetFindAndReferenceCompartmentAf
0x140125452  mov     [r14+60h], rax
0x140125456  test    rax, rax
0x140125459  jnz     loc_140125503
0x14012545f  cmp     cs:dword_1402241D4, edi
0x140125465  mov     r15d, 0C0000104h
0x14012546b  jz      loc_140125506
0x140125471  test    byte ptr cs:WPP_MAIN_CB.Dpc.DeferredRoutine+4, 40h
0x140125478  xorps   xmm0, xmm0
0x14012547b  movups  xmmword ptr [rbp+57h+var_60], xmm0
0x14012547f  jz      loc_140125506
0x140125485  mov     rcx, [r13+0]; Process
0x140125489  call    cs:__imp_PsGetProcessId
0x140125490  nop     dword ptr [rax+rax+00h]
0x140125495  mov     rcx, [r12]
0x140125499  mov     rdi, rax
0x14012549c  mov     [rbp+57h+var_60+8], 0
0x1401254a4  mov     [rbp+57h+var_60], r14
0x1401254a8  movzx   ebx, word ptr [rcx+18h]
0x1401254ac  mov     rcx, [r13+0]
0x1401254b0  call    cs:__imp_PsGetProcessStartKey
0x1401254b7  nop     dword ptr [rax+rax+00h]
0x1401254bc  mov     qword ptr [rsp+0E0h+var_90], rax
0x1401254c1  mov     r9, r14
0x1401254c4  mov     eax, dword ptr [rbp+57h+var_80+4]
0x1401254c7  lea     r8, [rbp+57h+var_60]
0x1401254cb  mov     dword ptr [rsp+0E0h+var_98], ebx
0x1401254cf  lea     rdx, TCP_LISTENER_ACTIVATION_FAILED_COMPARTMENT_V1
0x1401254d6  mov     dword ptr [rsp+0E0h+var_A0], eax
0x1401254da  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x1401254e1  mov     dword ptr [rsp+0E0h+var_A8], edi
0x1401254e5  xor     edi, edi
0x1401254e7  mov     dword ptr [rsp+0E0h+var_B0], 0C0000104h
0x1401254ef  mov     [rsp+0E0h+var_B8], rdi
0x1401254f4  mov     dword ptr [rsp+0E0h+a], edi
0x1401254f8  call    McTemplateK0pqbr1qqqqx_EtwWriteTransfer
0x1401254fd  mov     rbx, [rbp+57h+var_78]
0x140125501  jmp     short loc_140125506
0x140125503  mov     r15d, edi
0x140125506  test    r15d, r15d
0x140125509  jns     short loc_140125542
0x14012550b  jmp     loc_140125B58
0x140125510  mov     rdx, [rdx+58h]
0x140125514  lea     r12, [r14+30h]
0x140125518  mov     rcx, [r12]
0x14012551c  mov     [r14+60h], rdx
0x140125520  call    _InetReferenceCompartmentAf
0x140125525  mov     rax, [r14+0B0h]
0x14012552c  lea     rbx, [r14+0C0h]
0x140125533  mov     [rbp+57h+var_78], rbx
0x140125537  lea     r13, [r14+38h]
0x14012553b  mov     rdi, [rax+0F8h]
0x140125542  mov     rcx, [r14+0B0h]
0x140125549  lea     rax, [rsi-40h]
0x14012554d  lea     rdx, [rsi+80h]
0x140125554  test    rcx, rcx
0x140125557  jnz     loc_140125676
0x14012555d  mov     r8, [r12]
0x140125561  lea     r9d, [rcx+1]
0x140125565  mov     qword ptr [rsp+0E0h+var_98], rax
0x14012556a  mov     rcx, r14
0x14012556d  mov     rax, [rbx]
0x140125570  mov     [rsp+0E0h+var_A0], r14
0x140125575  movzx   r8d, word ptr [r8+18h]
0x14012557a  mov     [rsp+0E0h+var_A8], rdx
0x14012557f  xor     edx, edx
0x140125581  mov     qword ptr [rsp+0E0h+var_B0], rax
0x140125586  mov     rax, [r13+0]
0x14012558a  mov     [rsp+0E0h+var_B8], rax
0x14012558f  mov     dword ptr [rsp+0E0h+a], 6
0x140125597  call    InetInspectCreateEndpoint
0x14012559c  xor     ebx, ebx
0x14012559e  mov     r15d, eax
0x1401255a1  test    eax, eax
0x1401255a3  jns     loc_1401256AE
0x1401255a9  mov     cl, 2; NewIrql
0x1401255ab  call    cs:__imp_KfRaiseIrql
0x1401255b2  nop     dword ptr [rax+rax+00h]
0x1401255b7  mov     rcx, [r13+0]
0x1401255bb  xor     r9d, r9d
0x1401255be  mov     dword ptr [rsp+0E0h+var_A8], 8
0x1401255c6  xor     r8d, r8d
0x1401255c9  mov     dword ptr [rsp+0E0h+var_B0], 0
0x1401255d1  xor     edx, edx
0x1401255d3  mov     dword ptr [rsp+0E0h+var_B8], r15d
0x1401255d8  mov     bl, al
0x1401255da  mov     [rsp+0E0h+a], rcx
0x1401255df  xor     ecx, ecx
0x1401255e1  call    TcpRecentFailureTrace
0x1401255e6  mov     cl, bl; NewIrql
0x1401255e8  call    cs:__imp_KeLowerIrql
0x1401255ef  nop     dword ptr [rax+rax+00h]
0x1401255f4  xor     ebx, ebx
0x1401255f6  cmp     cs:dword_1402241D4, ebx
0x1401255fc  jz      loc_140125B58
0x140125602  test    byte ptr cs:WPP_MAIN_CB.Dpc.DeferredRoutine+4, 40h
0x140125609  xorps   xmm0, xmm0
0x14012560c  movups  xmmword ptr [rbp+57h+var_60], xmm0
0x140125610  jz      loc_140125B58
0x140125616  mov     rcx, [r13+0]; Process
0x14012561a  call    cs:__imp_PsGetProcessId
0x140125621  nop     dword ptr [rax+rax+00h]
0x140125626  mov     rcx, [r12]
0x14012562a  mov     rdi, rax
0x14012562d  mov     [rbp+57h+var_60+8], rbx
0x140125631  mov     [rbp+57h+var_60], r14
0x140125635  movzx   ebx, word ptr [rcx+18h]
0x140125639  mov     rcx, [r13+0]
0x14012563d  call    cs:__imp_PsGetProcessStartKey
0x140125644  nop     dword ptr [rax+rax+00h]
0x140125649  mov     qword ptr [rsp+0E0h+var_90], rax
0x14012564e  lea     rdx, TCP_LISTENER_ACTIVATION_FAILED_INSPECTION1_V1
0x140125655  mov     dword ptr [rsp+0E0h+var_98], ebx
0x140125659  xor     ebx, ebx
0x14012565b  mov     dword ptr [rsp+0E0h+var_A0], ebx
0x14012565f  mov     dword ptr [rsp+0E0h+var_A8], edi
0x140125663  mov     dword ptr [rsp+0E0h+var_B0], r15d
0x140125668  mov     [rsp+0E0h+var_B8], rbx
0x14012566d  mov     dword ptr [rsp+0E0h+a], ebx
0x140125671  jmp     loc_140125B45
0x140125676  mov     rcx, [rcx+50h]
0x14012567a  xor     ebx, ebx
0x14012567c  mov     [rax], rcx
0x14012567f  mov     rax, [rcx+258h]
0x140125686  mov     [r14+148h], rax
0x14012568d  mov     [rcx+258h], rdx
0x140125694  mov     [rcx+160h], r14
0x14012569b  mov     rax, [r14+0B0h]
0x1401256a2  mov     [rax+50h], rbx
0x1401256a6  mov     byte ptr [r14+140h], 1
0x1401256ae  mov     rcx, [r14+0B0h]
0x1401256b5  test    rcx, rcx
0x1401256b8  jz      short loc_140125737
0x1401256ba  mov     eax, [rcx+10h]
0x1401256bd  test    al, 1
0x1401256bf  jz      short loc_140125737
0x1401256c1  movzx   eax, word ptr [rcx+70h]
0x1401256c5  mov     [r14+78h], ax
0x1401256ca  mov     rcx, [rcx+68h]
0x1401256ce  mov     [r14+70h], rcx
0x1401256d2  cmp     rcx, [r12]
0x1401256d6  jz      short loc_1401256E6
0x1401256d8  mov     rcx, [rcx+10h]
0x1401256dc  mov     edx, 1
0x1401256e1  call    CarAcquireCacheAwareReference
0x1401256e6  mov     rax, [r14+0B0h]
0x1401256ed  mov     rdx, [rax+60h]
0x1401256f1  mov     [r14+68h], rdx
0x1401256f5  test    rdx, rdx
0x1401256f8  jz      short loc_140125703
0x1401256fa  mov     rcx, [r14+70h]
0x1401256fe  call    InetReferenceLocalAddressAf
0x140125703  mov     eax, [r14+20h]
0x140125707  mov     edx, eax
0x140125709  mov     rcx, [r14+0B0h]
0x140125710  xor     edx, [rcx+10h]
0x140125713  and     edx, 8
0x140125716  xor     edx, eax
0x140125718  mov     [r14+20h], edx
0x14012571c  movzx   eax, word ptr [rcx+72h]
0x140125720  mov     [r14+7Ah], ax
0x140125725  mov     eax, [rcx+10h]
0x140125728  shl     eax, 3
0x14012572b  xor     eax, edx
0x14012572d  and     eax, 20h
0x140125730  xor     eax, edx
0x140125732  jmp     loc_1401258DD
0x140125737  mov     r9b, [r14+112h]
0x14012573e  lea     rax, [rbp+57h+var_60]
0x140125742  mov     r8, [r14+60h]; int
0x140125746  lea     rcx, TcpInetTransport; int
0x14012574d  mov     rdx, [r12]; int
0x140125751  mov     [rsp+0E0h+var_A0], rax; __int64
0x140125756  lea     rax, [rbp+57h+var_70]
0x14012575a  mov     [rsp+0E0h+var_A8], rax; __int64
0x14012575f  lea     rax, [rbp+57h+var_80]
0x140125763  mov     qword ptr [rsp+0E0h+var_B0], rax; __int64
0x140125768  lea     rax, [rbp+57h+var_80+4]
0x14012576c  mov     [rsp+0E0h+var_B8], rax; __int64
0x140125771  mov     word ptr [rbp+57h+var_80+4], bx
0x140125775  mov     byte ptr [rbp+57h+var_80], bl
0x140125778  mov     [rbp+57h+var_60], rbx
0x14012577c  mov     [rbp+57h+var_70], rbx
0x140125780  lea     rbx, [r14+0D0h]
0x140125787  mov     rax, [rbx]
0x14012578a  shr     r9b, 1
0x14012578d  and     r9b, 1; int
0x140125791  mov     [rsp+0E0h+a], rax; a
0x140125796  call    InetResolveSockAddrToLocalAddressAndAf
0x14012579b  mov     r15d, eax
0x14012579e  test    eax, eax
0x1401257a0  jns     loc_14012583A
0x1401257a6  xor     ebx, ebx
0x1401257a8  cmp     cs:dword_1402241D4, ebx
0x1401257ae  jz      loc_140125B58
0x1401257b4  test    byte ptr cs:WPP_MAIN_CB.Dpc.DeferredRoutine+4, 40h
0x1401257bb  xorps   xmm0, xmm0
0x1401257be  movups  xmmword ptr [rbp+57h+var_60], xmm0
0x1401257c2  jz      loc_140125B58
0x1401257c8  mov     rcx, [r13+0]; Process
0x1401257cc  call    cs:__imp_PsGetProcessId
0x1401257d3  nop     dword ptr [rax+rax+00h]
0x1401257d8  mov     rcx, [r12]
0x1401257dc  mov     rsi, rax
0x1401257df  mov     [rbp+57h+var_60+8], rbx
0x1401257e3  mov     [rbp+57h+var_60], r14
0x1401257e7  movzx   ebx, word ptr [rcx+18h]
0x1401257eb  movzx   ecx, bx; af
0x1401257ee  call    SOCKADDR_SIZE
0x1401257f3  mov     rcx, [r13+0]
0x1401257f7  movzx   edi, al
0x1401257fa  call    cs:__imp_PsGetProcessStartKey
0x140125801  nop     dword ptr [rax+rax+00h]
0x140125806  mov     qword ptr [rsp+0E0h+var_90], rax
0x14012580b  lea     rdx, TCP_LISTENER_BIND_FAILED_RESOLUTION_V1
0x140125812  mov     dword ptr [rsp+0E0h+var_98], ebx
0x140125816  lea     rax, [r14+0D0h]
0x14012581d  xor     ebx, ebx
0x14012581f  mov     dword ptr [rsp+0E0h+var_A0], ebx
0x140125823  mov     dword ptr [rsp+0E0h+var_A8], esi
0x140125827  mov     dword ptr [rsp+0E0h+var_B0], r15d
0x14012582c  mov     [rsp+0E0h+var_B8], rax
0x140125831  mov     dword ptr [rsp+0E0h+a], edi
0x140125835  jmp     loc_140125B45
0x14012583a  mov     r8, [rbp+57h+var_60]
0x14012583e  test    r8, r8
0x140125841  jz      short loc_140125877
0x140125843  mov     eax, [r8+18h]
0x140125847  sub     eax, 3
0x14012584a  cmp     eax, 1
0x14012584d  ja      short loc_140125877
0x14012584f  mov     rbx, [rbp+57h+var_70]
0x140125853  mov     rdx, r8
0x140125856  mov     rcx, rbx
0x140125859  call    InetDereferenceLocalAddressAf
0x14012585e  cmp     rbx, [r12]
0x140125862  jz      short loc_14012586C
0x140125864  mov     rcx, rbx
0x140125867  call    _InetDereferenceAf
0x14012586c  mov     r15d, 0C0000207h
0x140125872  jmp     loc_140125B58
0x140125877  mov     rax, [rbp+57h+var_78]
0x14012587b  movzx   edx, word ptr [rbp+57h+var_80+4]
0x14012587f  mov     [rbp+57h+var_78], rax
0x140125883  mov     rax, [r12]
0x140125887  mov     [r14+78h], dx
0x14012588c  cmp     dx, [rax+18h]
0x140125890  jz      short loc_1401258A0
0x140125892  test    dx, dx
0x140125895  jz      short loc_1401258A0
0x140125897  mov     rcx, [r14+58h]
0x14012589b  call    WfpAleEndpointUpdateFamily
0x1401258a0  mov     rax, [rbp+57h+var_70]
0x1401258a4  movzx   edx, byte ptr [rbp+57h+var_80]
0x1401258a8  mov     [r14+70h], rax
  ... truncated ...
```
