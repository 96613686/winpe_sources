# TcpCreateListenerWorkQueueRoutine

- ea: `0x14011b880`
- end: `0x14011c1b5`
- name: `TcpCreateListenerWorkQueueRoutine`
- size: `2357`
- prototype: ``
- caller_count: `1`
- callee_count: `23`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140111d88`

## callees

- `0x140017558`
- `0x140017ca0`
- `0x140019330`
- `0x14002f200`
- `0x140039860`
- `0x14003b680`
- `0x14005b8e4`
- `0x14005c4b8`
- `0x140060404`
- `0x1400610b0`
- `0x1400645ec`
- `0x1400646d0`
- `0x140074820`
- `0x1400b8080`
- `0x1400b90f0`
- `0x1400b955c`
- `0x1400e8980`
- `0x1400f6cf4`
- `0x140107248`
- `0x14011b880`
- `0x14015aaac`
- `0x14016f3a8`
- `0x1401bf390`

## import_xrefs

- `ntoskrnl!KfRaiseIrql` at `0x14011ba8b`
- `ntoskrnl!KfRaiseIrql` at `0x14011c091`
- `ntoskrnl!KfRaiseIrql` at `0x14011ba8b`
- `ntoskrnl!KfRaiseIrql` at `0x14011c091`
- `ntoskrnl!KeLowerIrql` at `0x14011bac8`
- `ntoskrnl!KeLowerIrql` at `0x14011c165`
- `ntoskrnl!KeLowerIrql` at `0x14011bac8`
- `ntoskrnl!KeLowerIrql` at `0x14011c165`
- `ntoskrnl!ObReferenceSecurityDescriptor` at `0x14011b8c9`
- `ntoskrnl!ObReferenceSecurityDescriptor` at `0x14011b8c9`
- `ntoskrnl!PsGetProcessStartKey` at `0x14011b990`
- `ntoskrnl!PsGetProcessStartKey` at `0x14011bb1d`
- `ntoskrnl!PsGetProcessStartKey` at `0x14011bcda`
- `ntoskrnl!PsGetProcessStartKey` at `0x14011b990`
- `ntoskrnl!PsGetProcessStartKey` at `0x14011bb1d`
- `ntoskrnl!PsGetProcessStartKey` at `0x14011bcda`
- `ntoskrnl!PsGetProcessId` at `0x14011b969`
- `ntoskrnl!PsGetProcessId` at `0x14011bafa`
- `ntoskrnl!PsGetProcessId` at `0x14011bcac`
- `ntoskrnl!PsGetProcessId` at `0x14011b969`
- `ntoskrnl!PsGetProcessId` at `0x14011bafa`
- `ntoskrnl!PsGetProcessId` at `0x14011bcac`
- `ntoskrnl!ObfDereferenceObject` at `0x14011c044`
- `ntoskrnl!ObfDereferenceObject` at `0x14011c044`
- `NDIS!NdisGetProcessObjectCompartmentId` at `0x14011b914`
- `NDIS!NdisGetProcessObjectCompartmentId` at `0x14011b914`
- `NDIS!NdisGetThreadObjectCompartmentId` at `0x14011b8fa`
- `NDIS!NdisGetThreadObjectCompartmentId` at `0x14011b8fa`

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
        if ( dword_1402201D4 )
        {
          *(_OWORD *)v81 = 0;
          if ( (BYTE4(WPP_MAIN_CB.Reserved) & 0x40) != 0 )
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
        if ( dword_1402201D4 )
        {
          *(_OWORD *)v81 = 0;
          if ( (BYTE4(WPP_MAIN_CB.Reserved) & 0x40) != 0 )
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
        if ( dword_1402201D4 )
        {
          *(_OWORD *)v81 = 0;
          if ( (BYTE6(WPP_MAIN_CB.Reserved) & 0x10) != 0 )
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
          if ( qword_1402244B8 )
            InetTraceFailDataCore(&TcpInetTransport, 1553, (unsigned int)v57);
          if ( dword_1402201D4 )
          {
            *(_OWORD *)v81 = 0;
            if ( (BYTE4(WPP_MAIN_CB.Reserved) & 0x40) != 0 )
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
          if ( dword_1402201D4 )
          {
            *(_OWORD *)v81 = 0;
            if ( (BYTE6(WPP_MAIN_CB.Reserved) & 0x10) != 0 )
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
    else if ( dword_1402201D4 )
    {
      *(_OWORD *)v81 = 0;
      if ( (BYTE4(WPP_MAIN_CB.Reserved) & 0x40) != 0 )
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
      if ( dword_1402201D4 )
      {
        *(_OWORD *)v81 = 0;
        if ( (BYTE4(WPP_MAIN_CB.Reserved) & 0x40) != 0 )
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
0x14011b880  push    rbp
0x14011b882  push    rbx
0x14011b883  push    rsi
0x14011b884  push    rdi
0x14011b885  push    r12
0x14011b887  push    r13
0x14011b889  push    r14
0x14011b88b  push    r15
0x14011b88d  lea     rbp, [rsp-1Fh]
0x14011b892  sub     rsp, 0A8h
0x14011b899  mov     rax, cs:__security_cookie
0x14011b8a0  xor     rax, rsp
0x14011b8a3  mov     [rbp+57h+var_50], rax
0x14011b8a7  mov     rax, rcx
0x14011b8aa  lea     rsi, [rax]
0x14011b8ad  mov     rcx, [rsi-58h]
0x14011b8b1  lea     r14, [rax-98h]
0x14011b8b8  mov     rax, [rax]
0x14011b8bb  mov     [rbp+57h+var_68], rax
0x14011b8bf  test    rcx, rcx
0x14011b8c2  jz      short loc_14011B8D5
0x14011b8c4  mov     edx, 1
0x14011b8c9  call    cs:__imp_ObReferenceSecurityDescriptor
0x14011b8d0  nop     dword ptr [rax+rax+00h]
0x14011b8d5  mov     rdx, [r14+0B0h]
0x14011b8dc  test    rdx, rdx
0x14011b8df  jnz     loc_14011B9F0
0x14011b8e5  lea     rbx, [r14+0C0h]
0x14011b8ec  xor     edi, edi
0x14011b8ee  mov     rcx, [rbx]
0x14011b8f1  mov     [rbp+57h+var_78], rbx
0x14011b8f5  test    rcx, rcx
0x14011b8f8  jz      short loc_14011B90C
0x14011b8fa  call    cs:__imp_NdisGetThreadObjectCompartmentId
0x14011b901  nop     dword ptr [rax+rax+00h]
0x14011b906  lea     r13, [r14+38h]
0x14011b90a  jmp     short loc_14011B920
0x14011b90c  lea     r13, [r14+38h]
0x14011b910  mov     rcx, [r13+0]
0x14011b914  call    cs:__imp_NdisGetProcessObjectCompartmentId
0x14011b91b  nop     dword ptr [rax+rax+00h]
0x14011b920  lea     r12, [r14+30h]
0x14011b924  mov     dword ptr [rbp+57h+var_80+4], eax
0x14011b927  mov     rcx, [r12]
0x14011b92b  mov     edx, eax
0x14011b92d  call    _InetFindAndReferenceCompartmentAf
0x14011b932  mov     [r14+60h], rax
0x14011b936  test    rax, rax
0x14011b939  jnz     loc_14011B9E3
0x14011b93f  cmp     cs:dword_1402201D4, edi
0x14011b945  mov     r15d, 0C0000104h
0x14011b94b  jz      loc_14011B9E6
0x14011b951  test    byte ptr cs:WPP_MAIN_CB.Reserved+4, 40h
0x14011b958  xorps   xmm0, xmm0
0x14011b95b  movups  xmmword ptr [rbp+57h+var_60], xmm0
0x14011b95f  jz      loc_14011B9E6
0x14011b965  mov     rcx, [r13+0]; Process
0x14011b969  call    cs:__imp_PsGetProcessId
0x14011b970  nop     dword ptr [rax+rax+00h]
0x14011b975  mov     rcx, [r12]
0x14011b979  mov     rdi, rax
0x14011b97c  mov     [rbp+57h+var_60+8], 0
0x14011b984  mov     [rbp+57h+var_60], r14
0x14011b988  movzx   ebx, word ptr [rcx+18h]
0x14011b98c  mov     rcx, [r13+0]
0x14011b990  call    cs:__imp_PsGetProcessStartKey
0x14011b997  nop     dword ptr [rax+rax+00h]
0x14011b99c  mov     qword ptr [rsp+0E0h+var_90], rax
0x14011b9a1  mov     r9, r14
0x14011b9a4  mov     eax, dword ptr [rbp+57h+var_80+4]
0x14011b9a7  lea     r8, [rbp+57h+var_60]
0x14011b9ab  mov     dword ptr [rsp+0E0h+var_98], ebx
0x14011b9af  lea     rdx, TCP_LISTENER_ACTIVATION_FAILED_COMPARTMENT_V1
0x14011b9b6  mov     dword ptr [rsp+0E0h+var_A0], eax
0x14011b9ba  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x14011b9c1  mov     dword ptr [rsp+0E0h+var_A8], edi
0x14011b9c5  xor     edi, edi
0x14011b9c7  mov     dword ptr [rsp+0E0h+var_B0], 0C0000104h
0x14011b9cf  mov     [rsp+0E0h+var_B8], rdi
0x14011b9d4  mov     dword ptr [rsp+0E0h+a], edi
0x14011b9d8  call    McTemplateK0pqbr1qqqqx_EtwWriteTransfer
0x14011b9dd  mov     rbx, [rbp+57h+var_78]
0x14011b9e1  jmp     short loc_14011B9E6
0x14011b9e3  mov     r15d, edi
0x14011b9e6  test    r15d, r15d
0x14011b9e9  jns     short loc_14011BA22
0x14011b9eb  jmp     loc_14011C038
0x14011b9f0  mov     rdx, [rdx+58h]
0x14011b9f4  lea     r12, [r14+30h]
0x14011b9f8  mov     rcx, [r12]
0x14011b9fc  mov     [r14+60h], rdx
0x14011ba00  call    _InetReferenceCompartmentAf
0x14011ba05  mov     rax, [r14+0B0h]
0x14011ba0c  lea     rbx, [r14+0C0h]
0x14011ba13  mov     [rbp+57h+var_78], rbx
0x14011ba17  lea     r13, [r14+38h]
0x14011ba1b  mov     rdi, [rax+0F8h]
0x14011ba22  mov     rcx, [r14+0B0h]
0x14011ba29  lea     rax, [rsi-40h]
0x14011ba2d  lea     rdx, [rsi+80h]
0x14011ba34  test    rcx, rcx
0x14011ba37  jnz     loc_14011BB56
0x14011ba3d  mov     r8, [r12]
0x14011ba41  lea     r9d, [rcx+1]
0x14011ba45  mov     qword ptr [rsp+0E0h+var_98], rax
0x14011ba4a  mov     rcx, r14
0x14011ba4d  mov     rax, [rbx]
0x14011ba50  mov     [rsp+0E0h+var_A0], r14
0x14011ba55  movzx   r8d, word ptr [r8+18h]
0x14011ba5a  mov     [rsp+0E0h+var_A8], rdx
0x14011ba5f  xor     edx, edx
0x14011ba61  mov     qword ptr [rsp+0E0h+var_B0], rax
0x14011ba66  mov     rax, [r13+0]
0x14011ba6a  mov     [rsp+0E0h+var_B8], rax
0x14011ba6f  mov     dword ptr [rsp+0E0h+a], 6
0x14011ba77  call    InetInspectCreateEndpoint
0x14011ba7c  xor     ebx, ebx
0x14011ba7e  mov     r15d, eax
0x14011ba81  test    eax, eax
0x14011ba83  jns     loc_14011BB8E
0x14011ba89  mov     cl, 2; NewIrql
0x14011ba8b  call    cs:__imp_KfRaiseIrql
0x14011ba92  nop     dword ptr [rax+rax+00h]
0x14011ba97  mov     rcx, [r13+0]
0x14011ba9b  xor     r9d, r9d
0x14011ba9e  mov     dword ptr [rsp+0E0h+var_A8], 8
0x14011baa6  xor     r8d, r8d
0x14011baa9  mov     dword ptr [rsp+0E0h+var_B0], 0
0x14011bab1  xor     edx, edx
0x14011bab3  mov     dword ptr [rsp+0E0h+var_B8], r15d
0x14011bab8  mov     bl, al
0x14011baba  mov     [rsp+0E0h+a], rcx
0x14011babf  xor     ecx, ecx
0x14011bac1  call    TcpRecentFailureTrace
0x14011bac6  mov     cl, bl; NewIrql
0x14011bac8  call    cs:__imp_KeLowerIrql
0x14011bacf  nop     dword ptr [rax+rax+00h]
0x14011bad4  xor     ebx, ebx
0x14011bad6  cmp     cs:dword_1402201D4, ebx
0x14011badc  jz      loc_14011C038
0x14011bae2  test    byte ptr cs:WPP_MAIN_CB.Reserved+4, 40h
0x14011bae9  xorps   xmm0, xmm0
0x14011baec  movups  xmmword ptr [rbp+57h+var_60], xmm0
0x14011baf0  jz      loc_14011C038
0x14011baf6  mov     rcx, [r13+0]; Process
0x14011bafa  call    cs:__imp_PsGetProcessId
0x14011bb01  nop     dword ptr [rax+rax+00h]
0x14011bb06  mov     rcx, [r12]
0x14011bb0a  mov     rdi, rax
0x14011bb0d  mov     [rbp+57h+var_60+8], rbx
0x14011bb11  mov     [rbp+57h+var_60], r14
0x14011bb15  movzx   ebx, word ptr [rcx+18h]
0x14011bb19  mov     rcx, [r13+0]
0x14011bb1d  call    cs:__imp_PsGetProcessStartKey
0x14011bb24  nop     dword ptr [rax+rax+00h]
0x14011bb29  mov     qword ptr [rsp+0E0h+var_90], rax
0x14011bb2e  lea     rdx, TCP_LISTENER_ACTIVATION_FAILED_INSPECTION1_V1
0x14011bb35  mov     dword ptr [rsp+0E0h+var_98], ebx
0x14011bb39  xor     ebx, ebx
0x14011bb3b  mov     dword ptr [rsp+0E0h+var_A0], ebx
0x14011bb3f  mov     dword ptr [rsp+0E0h+var_A8], edi
0x14011bb43  mov     dword ptr [rsp+0E0h+var_B0], r15d
0x14011bb48  mov     [rsp+0E0h+var_B8], rbx
0x14011bb4d  mov     dword ptr [rsp+0E0h+a], ebx
0x14011bb51  jmp     loc_14011C025
0x14011bb56  mov     rcx, [rcx+50h]
0x14011bb5a  xor     ebx, ebx
0x14011bb5c  mov     [rax], rcx
0x14011bb5f  mov     rax, [rcx+258h]
0x14011bb66  mov     [r14+148h], rax
0x14011bb6d  mov     [rcx+258h], rdx
0x14011bb74  mov     [rcx+160h], r14
0x14011bb7b  mov     rax, [r14+0B0h]
0x14011bb82  mov     [rax+50h], rbx
0x14011bb86  mov     byte ptr [r14+140h], 1
0x14011bb8e  mov     rcx, [r14+0B0h]
0x14011bb95  test    rcx, rcx
0x14011bb98  jz      short loc_14011BC17
0x14011bb9a  mov     eax, [rcx+10h]
0x14011bb9d  test    al, 1
0x14011bb9f  jz      short loc_14011BC17
0x14011bba1  movzx   eax, word ptr [rcx+70h]
0x14011bba5  mov     [r14+78h], ax
0x14011bbaa  mov     rcx, [rcx+68h]
0x14011bbae  mov     [r14+70h], rcx
0x14011bbb2  cmp     rcx, [r12]
0x14011bbb6  jz      short loc_14011BBC6
0x14011bbb8  mov     rcx, [rcx+10h]
0x14011bbbc  mov     edx, 1
0x14011bbc1  call    CarAcquireCacheAwareReference
0x14011bbc6  mov     rax, [r14+0B0h]
0x14011bbcd  mov     rdx, [rax+60h]
0x14011bbd1  mov     [r14+68h], rdx
0x14011bbd5  test    rdx, rdx
0x14011bbd8  jz      short loc_14011BBE3
0x14011bbda  mov     rcx, [r14+70h]
0x14011bbde  call    InetReferenceLocalAddressAf
0x14011bbe3  mov     eax, [r14+20h]
0x14011bbe7  mov     edx, eax
0x14011bbe9  mov     rcx, [r14+0B0h]
0x14011bbf0  xor     edx, [rcx+10h]
0x14011bbf3  and     edx, 8
0x14011bbf6  xor     edx, eax
0x14011bbf8  mov     [r14+20h], edx
0x14011bbfc  movzx   eax, word ptr [rcx+72h]
0x14011bc00  mov     [r14+7Ah], ax
0x14011bc05  mov     eax, [rcx+10h]
0x14011bc08  shl     eax, 3
0x14011bc0b  xor     eax, edx
0x14011bc0d  and     eax, 20h
0x14011bc10  xor     eax, edx
0x14011bc12  jmp     loc_14011BDBD
0x14011bc17  mov     r9b, [r14+112h]
0x14011bc1e  lea     rax, [rbp+57h+var_60]
0x14011bc22  mov     r8, [r14+60h]; int
0x14011bc26  lea     rcx, TcpInetTransport; int
0x14011bc2d  mov     rdx, [r12]; int
0x14011bc31  mov     [rsp+0E0h+var_A0], rax; __int64
0x14011bc36  lea     rax, [rbp+57h+var_70]
0x14011bc3a  mov     [rsp+0E0h+var_A8], rax; __int64
0x14011bc3f  lea     rax, [rbp+57h+var_80]
0x14011bc43  mov     qword ptr [rsp+0E0h+var_B0], rax; __int64
0x14011bc48  lea     rax, [rbp+57h+var_80+4]
0x14011bc4c  mov     [rsp+0E0h+var_B8], rax; __int64
0x14011bc51  mov     word ptr [rbp+57h+var_80+4], bx
0x14011bc55  mov     byte ptr [rbp+57h+var_80], bl
0x14011bc58  mov     [rbp+57h+var_60], rbx
0x14011bc5c  mov     [rbp+57h+var_70], rbx
0x14011bc60  lea     rbx, [r14+0D0h]
0x14011bc67  mov     rax, [rbx]
0x14011bc6a  shr     r9b, 1
0x14011bc6d  and     r9b, 1; int
0x14011bc71  mov     [rsp+0E0h+a], rax; a
0x14011bc76  call    InetResolveSockAddrToLocalAddressAndAf
0x14011bc7b  mov     r15d, eax
0x14011bc7e  test    eax, eax
0x14011bc80  jns     loc_14011BD1A
0x14011bc86  xor     ebx, ebx
0x14011bc88  cmp     cs:dword_1402201D4, ebx
0x14011bc8e  jz      loc_14011C038
0x14011bc94  test    byte ptr cs:WPP_MAIN_CB.Reserved+4, 40h
0x14011bc9b  xorps   xmm0, xmm0
0x14011bc9e  movups  xmmword ptr [rbp+57h+var_60], xmm0
0x14011bca2  jz      loc_14011C038
0x14011bca8  mov     rcx, [r13+0]; Process
0x14011bcac  call    cs:__imp_PsGetProcessId
0x14011bcb3  nop     dword ptr [rax+rax+00h]
0x14011bcb8  mov     rcx, [r12]
0x14011bcbc  mov     rsi, rax
0x14011bcbf  mov     [rbp+57h+var_60+8], rbx
0x14011bcc3  mov     [rbp+57h+var_60], r14
0x14011bcc7  movzx   ebx, word ptr [rcx+18h]
0x14011bccb  movzx   ecx, bx; af
0x14011bcce  call    SOCKADDR_SIZE
0x14011bcd3  mov     rcx, [r13+0]
0x14011bcd7  movzx   edi, al
0x14011bcda  call    cs:__imp_PsGetProcessStartKey
0x14011bce1  nop     dword ptr [rax+rax+00h]
0x14011bce6  mov     qword ptr [rsp+0E0h+var_90], rax
0x14011bceb  lea     rdx, TCP_LISTENER_BIND_FAILED_RESOLUTION_V1
0x14011bcf2  mov     dword ptr [rsp+0E0h+var_98], ebx
0x14011bcf6  lea     rax, [r14+0D0h]
0x14011bcfd  xor     ebx, ebx
0x14011bcff  mov     dword ptr [rsp+0E0h+var_A0], ebx
0x14011bd03  mov     dword ptr [rsp+0E0h+var_A8], esi
0x14011bd07  mov     dword ptr [rsp+0E0h+var_B0], r15d
0x14011bd0c  mov     [rsp+0E0h+var_B8], rax
0x14011bd11  mov     dword ptr [rsp+0E0h+a], edi
0x14011bd15  jmp     loc_14011C025
0x14011bd1a  mov     r8, [rbp+57h+var_60]
0x14011bd1e  test    r8, r8
0x14011bd21  jz      short loc_14011BD57
0x14011bd23  mov     eax, [r8+18h]
0x14011bd27  sub     eax, 3
0x14011bd2a  cmp     eax, 1
0x14011bd2d  ja      short loc_14011BD57
0x14011bd2f  mov     rbx, [rbp+57h+var_70]
0x14011bd33  mov     rdx, r8
0x14011bd36  mov     rcx, rbx
0x14011bd39  call    InetDereferenceLocalAddressAf
0x14011bd3e  cmp     rbx, [r12]
0x14011bd42  jz      short loc_14011BD4C
0x14011bd44  mov     rcx, rbx
0x14011bd47  call    _InetDereferenceAf
0x14011bd4c  mov     r15d, 0C0000207h
0x14011bd52  jmp     loc_14011C038
0x14011bd57  mov     rax, [rbp+57h+var_78]
0x14011bd5b  movzx   edx, word ptr [rbp+57h+var_80+4]
0x14011bd5f  mov     [rbp+57h+var_78], rax
0x14011bd63  mov     rax, [r12]
0x14011bd67  mov     [r14+78h], dx
0x14011bd6c  cmp     dx, [rax+18h]
0x14011bd70  jz      short loc_14011BD80
0x14011bd72  test    dx, dx
0x14011bd75  jz      short loc_14011BD80
0x14011bd77  mov     rcx, [r14+58h]
0x14011bd7b  call    WfpAleEndpointUpdateFamily
0x14011bd80  mov     rax, [rbp+57h+var_70]
0x14011bd84  movzx   edx, byte ptr [rbp+57h+var_80]
0x14011bd88  mov     [r14+70h], rax
  ... truncated ...
```
