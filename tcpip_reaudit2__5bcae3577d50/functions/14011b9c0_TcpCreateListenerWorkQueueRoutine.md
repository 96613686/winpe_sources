# TcpCreateListenerWorkQueueRoutine

- ea: `0x14011b9c0`
- end: `0x14011c2f5`
- name: `TcpCreateListenerWorkQueueRoutine`
- size: `2357`
- prototype: ``
- caller_count: `1`
- callee_count: `23`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140111ec8`

## callees

- `0x140017558`
- `0x140017ca0`
- `0x1400195d0`
- `0x14002f4a0`
- `0x140039b00`
- `0x14003b920`
- `0x14005bb84`
- `0x14005c758`
- `0x1400606a4`
- `0x140061350`
- `0x14006488c`
- `0x140064970`
- `0x140074ac0`
- `0x1400b7ca0`
- `0x1400b8d10`
- `0x1400b917c`
- `0x1400e8870`
- `0x1400f6be4`
- `0x140107268`
- `0x14011b9c0`
- `0x14015abec`
- `0x14016f4e8`
- `0x1401bf4d0`

## import_xrefs

- `ntoskrnl!KfRaiseIrql` at `0x14011bbcb`
- `ntoskrnl!KfRaiseIrql` at `0x14011c1d1`
- `ntoskrnl!KfRaiseIrql` at `0x14011bbcb`
- `ntoskrnl!KfRaiseIrql` at `0x14011c1d1`
- `ntoskrnl!KeLowerIrql` at `0x14011bc08`
- `ntoskrnl!KeLowerIrql` at `0x14011c2a5`
- `ntoskrnl!KeLowerIrql` at `0x14011bc08`
- `ntoskrnl!KeLowerIrql` at `0x14011c2a5`
- `ntoskrnl!ObReferenceSecurityDescriptor` at `0x14011ba09`
- `ntoskrnl!ObReferenceSecurityDescriptor` at `0x14011ba09`
- `ntoskrnl!PsGetProcessStartKey` at `0x14011bad0`
- `ntoskrnl!PsGetProcessStartKey` at `0x14011bc5d`
- `ntoskrnl!PsGetProcessStartKey` at `0x14011be1a`
- `ntoskrnl!PsGetProcessStartKey` at `0x14011bad0`
- `ntoskrnl!PsGetProcessStartKey` at `0x14011bc5d`
- `ntoskrnl!PsGetProcessStartKey` at `0x14011be1a`
- `ntoskrnl!PsGetProcessId` at `0x14011baa9`
- `ntoskrnl!PsGetProcessId` at `0x14011bc3a`
- `ntoskrnl!PsGetProcessId` at `0x14011bdec`
- `ntoskrnl!PsGetProcessId` at `0x14011baa9`
- `ntoskrnl!PsGetProcessId` at `0x14011bc3a`
- `ntoskrnl!PsGetProcessId` at `0x14011bdec`
- `ntoskrnl!ObfDereferenceObject` at `0x14011c184`
- `ntoskrnl!ObfDereferenceObject` at `0x14011c184`
- `NDIS!NdisGetProcessObjectCompartmentId` at `0x14011ba54`
- `NDIS!NdisGetProcessObjectCompartmentId` at `0x14011ba54`
- `NDIS!NdisGetThreadObjectCompartmentId` at `0x14011ba3a`
- `NDIS!NdisGetThreadObjectCompartmentId` at `0x14011ba3a`

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
          if ( qword_140224478 )
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
0x14011b9c0  push    rbp
0x14011b9c2  push    rbx
0x14011b9c3  push    rsi
0x14011b9c4  push    rdi
0x14011b9c5  push    r12
0x14011b9c7  push    r13
0x14011b9c9  push    r14
0x14011b9cb  push    r15
0x14011b9cd  lea     rbp, [rsp-1Fh]
0x14011b9d2  sub     rsp, 0A8h
0x14011b9d9  mov     rax, cs:__security_cookie
0x14011b9e0  xor     rax, rsp
0x14011b9e3  mov     [rbp+57h+var_50], rax
0x14011b9e7  mov     rax, rcx
0x14011b9ea  lea     rsi, [rax]
0x14011b9ed  mov     rcx, [rsi-58h]
0x14011b9f1  lea     r14, [rax-98h]
0x14011b9f8  mov     rax, [rax]
0x14011b9fb  mov     [rbp+57h+var_68], rax
0x14011b9ff  test    rcx, rcx
0x14011ba02  jz      short loc_14011BA15
0x14011ba04  mov     edx, 1
0x14011ba09  call    cs:__imp_ObReferenceSecurityDescriptor
0x14011ba10  nop     dword ptr [rax+rax+00h]
0x14011ba15  mov     rdx, [r14+0B0h]
0x14011ba1c  test    rdx, rdx
0x14011ba1f  jnz     loc_14011BB30
0x14011ba25  lea     rbx, [r14+0C0h]
0x14011ba2c  xor     edi, edi
0x14011ba2e  mov     rcx, [rbx]
0x14011ba31  mov     [rbp+57h+var_78], rbx
0x14011ba35  test    rcx, rcx
0x14011ba38  jz      short loc_14011BA4C
0x14011ba3a  call    cs:__imp_NdisGetThreadObjectCompartmentId
0x14011ba41  nop     dword ptr [rax+rax+00h]
0x14011ba46  lea     r13, [r14+38h]
0x14011ba4a  jmp     short loc_14011BA60
0x14011ba4c  lea     r13, [r14+38h]
0x14011ba50  mov     rcx, [r13+0]
0x14011ba54  call    cs:__imp_NdisGetProcessObjectCompartmentId
0x14011ba5b  nop     dword ptr [rax+rax+00h]
0x14011ba60  lea     r12, [r14+30h]
0x14011ba64  mov     dword ptr [rbp+57h+var_80+4], eax
0x14011ba67  mov     rcx, [r12]
0x14011ba6b  mov     edx, eax
0x14011ba6d  call    _InetFindAndReferenceCompartmentAf
0x14011ba72  mov     [r14+60h], rax
0x14011ba76  test    rax, rax
0x14011ba79  jnz     loc_14011BB23
0x14011ba7f  cmp     cs:dword_1402201D4, edi
0x14011ba85  mov     r15d, 0C0000104h
0x14011ba8b  jz      loc_14011BB26
0x14011ba91  test    byte ptr cs:WPP_MAIN_CB.Reserved+4, 40h
0x14011ba98  xorps   xmm0, xmm0
0x14011ba9b  movups  xmmword ptr [rbp+57h+var_60], xmm0
0x14011ba9f  jz      loc_14011BB26
0x14011baa5  mov     rcx, [r13+0]; Process
0x14011baa9  call    cs:__imp_PsGetProcessId
0x14011bab0  nop     dword ptr [rax+rax+00h]
0x14011bab5  mov     rcx, [r12]
0x14011bab9  mov     rdi, rax
0x14011babc  mov     [rbp+57h+var_60+8], 0
0x14011bac4  mov     [rbp+57h+var_60], r14
0x14011bac8  movzx   ebx, word ptr [rcx+18h]
0x14011bacc  mov     rcx, [r13+0]
0x14011bad0  call    cs:__imp_PsGetProcessStartKey
0x14011bad7  nop     dword ptr [rax+rax+00h]
0x14011badc  mov     qword ptr [rsp+0E0h+var_90], rax
0x14011bae1  mov     r9, r14
0x14011bae4  mov     eax, dword ptr [rbp+57h+var_80+4]
0x14011bae7  lea     r8, [rbp+57h+var_60]
0x14011baeb  mov     dword ptr [rsp+0E0h+var_98], ebx
0x14011baef  lea     rdx, TCP_LISTENER_ACTIVATION_FAILED_COMPARTMENT_V1
0x14011baf6  mov     dword ptr [rsp+0E0h+var_A0], eax
0x14011bafa  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x14011bb01  mov     dword ptr [rsp+0E0h+var_A8], edi
0x14011bb05  xor     edi, edi
0x14011bb07  mov     dword ptr [rsp+0E0h+var_B0], 0C0000104h
0x14011bb0f  mov     [rsp+0E0h+var_B8], rdi
0x14011bb14  mov     dword ptr [rsp+0E0h+a], edi
0x14011bb18  call    McTemplateK0pqbr1qqqqx_EtwWriteTransfer
0x14011bb1d  mov     rbx, [rbp+57h+var_78]
0x14011bb21  jmp     short loc_14011BB26
0x14011bb23  mov     r15d, edi
0x14011bb26  test    r15d, r15d
0x14011bb29  jns     short loc_14011BB62
0x14011bb2b  jmp     loc_14011C178
0x14011bb30  mov     rdx, [rdx+58h]
0x14011bb34  lea     r12, [r14+30h]
0x14011bb38  mov     rcx, [r12]
0x14011bb3c  mov     [r14+60h], rdx
0x14011bb40  call    _InetReferenceCompartmentAf
0x14011bb45  mov     rax, [r14+0B0h]
0x14011bb4c  lea     rbx, [r14+0C0h]
0x14011bb53  mov     [rbp+57h+var_78], rbx
0x14011bb57  lea     r13, [r14+38h]
0x14011bb5b  mov     rdi, [rax+0F8h]
0x14011bb62  mov     rcx, [r14+0B0h]
0x14011bb69  lea     rax, [rsi-40h]
0x14011bb6d  lea     rdx, [rsi+80h]
0x14011bb74  test    rcx, rcx
0x14011bb77  jnz     loc_14011BC96
0x14011bb7d  mov     r8, [r12]
0x14011bb81  lea     r9d, [rcx+1]
0x14011bb85  mov     qword ptr [rsp+0E0h+var_98], rax
0x14011bb8a  mov     rcx, r14
0x14011bb8d  mov     rax, [rbx]
0x14011bb90  mov     [rsp+0E0h+var_A0], r14
0x14011bb95  movzx   r8d, word ptr [r8+18h]
0x14011bb9a  mov     [rsp+0E0h+var_A8], rdx
0x14011bb9f  xor     edx, edx
0x14011bba1  mov     qword ptr [rsp+0E0h+var_B0], rax
0x14011bba6  mov     rax, [r13+0]
0x14011bbaa  mov     [rsp+0E0h+var_B8], rax
0x14011bbaf  mov     dword ptr [rsp+0E0h+a], 6
0x14011bbb7  call    InetInspectCreateEndpoint
0x14011bbbc  xor     ebx, ebx
0x14011bbbe  mov     r15d, eax
0x14011bbc1  test    eax, eax
0x14011bbc3  jns     loc_14011BCCE
0x14011bbc9  mov     cl, 2; NewIrql
0x14011bbcb  call    cs:__imp_KfRaiseIrql
0x14011bbd2  nop     dword ptr [rax+rax+00h]
0x14011bbd7  mov     rcx, [r13+0]
0x14011bbdb  xor     r9d, r9d
0x14011bbde  mov     dword ptr [rsp+0E0h+var_A8], 8
0x14011bbe6  xor     r8d, r8d
0x14011bbe9  mov     dword ptr [rsp+0E0h+var_B0], 0
0x14011bbf1  xor     edx, edx
0x14011bbf3  mov     dword ptr [rsp+0E0h+var_B8], r15d
0x14011bbf8  mov     bl, al
0x14011bbfa  mov     [rsp+0E0h+a], rcx
0x14011bbff  xor     ecx, ecx
0x14011bc01  call    TcpRecentFailureTrace
0x14011bc06  mov     cl, bl; NewIrql
0x14011bc08  call    cs:__imp_KeLowerIrql
0x14011bc0f  nop     dword ptr [rax+rax+00h]
0x14011bc14  xor     ebx, ebx
0x14011bc16  cmp     cs:dword_1402201D4, ebx
0x14011bc1c  jz      loc_14011C178
0x14011bc22  test    byte ptr cs:WPP_MAIN_CB.Reserved+4, 40h
0x14011bc29  xorps   xmm0, xmm0
0x14011bc2c  movups  xmmword ptr [rbp+57h+var_60], xmm0
0x14011bc30  jz      loc_14011C178
0x14011bc36  mov     rcx, [r13+0]; Process
0x14011bc3a  call    cs:__imp_PsGetProcessId
0x14011bc41  nop     dword ptr [rax+rax+00h]
0x14011bc46  mov     rcx, [r12]
0x14011bc4a  mov     rdi, rax
0x14011bc4d  mov     [rbp+57h+var_60+8], rbx
0x14011bc51  mov     [rbp+57h+var_60], r14
0x14011bc55  movzx   ebx, word ptr [rcx+18h]
0x14011bc59  mov     rcx, [r13+0]
0x14011bc5d  call    cs:__imp_PsGetProcessStartKey
0x14011bc64  nop     dword ptr [rax+rax+00h]
0x14011bc69  mov     qword ptr [rsp+0E0h+var_90], rax
0x14011bc6e  lea     rdx, TCP_LISTENER_ACTIVATION_FAILED_INSPECTION1_V1
0x14011bc75  mov     dword ptr [rsp+0E0h+var_98], ebx
0x14011bc79  xor     ebx, ebx
0x14011bc7b  mov     dword ptr [rsp+0E0h+var_A0], ebx
0x14011bc7f  mov     dword ptr [rsp+0E0h+var_A8], edi
0x14011bc83  mov     dword ptr [rsp+0E0h+var_B0], r15d
0x14011bc88  mov     [rsp+0E0h+var_B8], rbx
0x14011bc8d  mov     dword ptr [rsp+0E0h+a], ebx
0x14011bc91  jmp     loc_14011C165
0x14011bc96  mov     rcx, [rcx+50h]
0x14011bc9a  xor     ebx, ebx
0x14011bc9c  mov     [rax], rcx
0x14011bc9f  mov     rax, [rcx+258h]
0x14011bca6  mov     [r14+148h], rax
0x14011bcad  mov     [rcx+258h], rdx
0x14011bcb4  mov     [rcx+160h], r14
0x14011bcbb  mov     rax, [r14+0B0h]
0x14011bcc2  mov     [rax+50h], rbx
0x14011bcc6  mov     byte ptr [r14+140h], 1
0x14011bcce  mov     rcx, [r14+0B0h]
0x14011bcd5  test    rcx, rcx
0x14011bcd8  jz      short loc_14011BD57
0x14011bcda  mov     eax, [rcx+10h]
0x14011bcdd  test    al, 1
0x14011bcdf  jz      short loc_14011BD57
0x14011bce1  movzx   eax, word ptr [rcx+70h]
0x14011bce5  mov     [r14+78h], ax
0x14011bcea  mov     rcx, [rcx+68h]
0x14011bcee  mov     [r14+70h], rcx
0x14011bcf2  cmp     rcx, [r12]
0x14011bcf6  jz      short loc_14011BD06
0x14011bcf8  mov     rcx, [rcx+10h]
0x14011bcfc  mov     edx, 1
0x14011bd01  call    CarAcquireCacheAwareReference
0x14011bd06  mov     rax, [r14+0B0h]
0x14011bd0d  mov     rdx, [rax+60h]
0x14011bd11  mov     [r14+68h], rdx
0x14011bd15  test    rdx, rdx
0x14011bd18  jz      short loc_14011BD23
0x14011bd1a  mov     rcx, [r14+70h]
0x14011bd1e  call    InetReferenceLocalAddressAf
0x14011bd23  mov     eax, [r14+20h]
0x14011bd27  mov     edx, eax
0x14011bd29  mov     rcx, [r14+0B0h]
0x14011bd30  xor     edx, [rcx+10h]
0x14011bd33  and     edx, 8
0x14011bd36  xor     edx, eax
0x14011bd38  mov     [r14+20h], edx
0x14011bd3c  movzx   eax, word ptr [rcx+72h]
0x14011bd40  mov     [r14+7Ah], ax
0x14011bd45  mov     eax, [rcx+10h]
0x14011bd48  shl     eax, 3
0x14011bd4b  xor     eax, edx
0x14011bd4d  and     eax, 20h
0x14011bd50  xor     eax, edx
0x14011bd52  jmp     loc_14011BEFD
0x14011bd57  mov     r9b, [r14+112h]
0x14011bd5e  lea     rax, [rbp+57h+var_60]
0x14011bd62  mov     r8, [r14+60h]; int
0x14011bd66  lea     rcx, TcpInetTransport; int
0x14011bd6d  mov     rdx, [r12]; int
0x14011bd71  mov     [rsp+0E0h+var_A0], rax; __int64
0x14011bd76  lea     rax, [rbp+57h+var_70]
0x14011bd7a  mov     [rsp+0E0h+var_A8], rax; __int64
0x14011bd7f  lea     rax, [rbp+57h+var_80]
0x14011bd83  mov     qword ptr [rsp+0E0h+var_B0], rax; __int64
0x14011bd88  lea     rax, [rbp+57h+var_80+4]
0x14011bd8c  mov     [rsp+0E0h+var_B8], rax; __int64
0x14011bd91  mov     word ptr [rbp+57h+var_80+4], bx
0x14011bd95  mov     byte ptr [rbp+57h+var_80], bl
0x14011bd98  mov     [rbp+57h+var_60], rbx
0x14011bd9c  mov     [rbp+57h+var_70], rbx
0x14011bda0  lea     rbx, [r14+0D0h]
0x14011bda7  mov     rax, [rbx]
0x14011bdaa  shr     r9b, 1
0x14011bdad  and     r9b, 1; int
0x14011bdb1  mov     [rsp+0E0h+a], rax; a
0x14011bdb6  call    InetResolveSockAddrToLocalAddressAndAf
0x14011bdbb  mov     r15d, eax
0x14011bdbe  test    eax, eax
0x14011bdc0  jns     loc_14011BE5A
0x14011bdc6  xor     ebx, ebx
0x14011bdc8  cmp     cs:dword_1402201D4, ebx
0x14011bdce  jz      loc_14011C178
0x14011bdd4  test    byte ptr cs:WPP_MAIN_CB.Reserved+4, 40h
0x14011bddb  xorps   xmm0, xmm0
0x14011bdde  movups  xmmword ptr [rbp+57h+var_60], xmm0
0x14011bde2  jz      loc_14011C178
0x14011bde8  mov     rcx, [r13+0]; Process
0x14011bdec  call    cs:__imp_PsGetProcessId
0x14011bdf3  nop     dword ptr [rax+rax+00h]
0x14011bdf8  mov     rcx, [r12]
0x14011bdfc  mov     rsi, rax
0x14011bdff  mov     [rbp+57h+var_60+8], rbx
0x14011be03  mov     [rbp+57h+var_60], r14
0x14011be07  movzx   ebx, word ptr [rcx+18h]
0x14011be0b  movzx   ecx, bx; af
0x14011be0e  call    SOCKADDR_SIZE
0x14011be13  mov     rcx, [r13+0]
0x14011be17  movzx   edi, al
0x14011be1a  call    cs:__imp_PsGetProcessStartKey
0x14011be21  nop     dword ptr [rax+rax+00h]
0x14011be26  mov     qword ptr [rsp+0E0h+var_90], rax
0x14011be2b  lea     rdx, TCP_LISTENER_BIND_FAILED_RESOLUTION_V1
0x14011be32  mov     dword ptr [rsp+0E0h+var_98], ebx
0x14011be36  lea     rax, [r14+0D0h]
0x14011be3d  xor     ebx, ebx
0x14011be3f  mov     dword ptr [rsp+0E0h+var_A0], ebx
0x14011be43  mov     dword ptr [rsp+0E0h+var_A8], esi
0x14011be47  mov     dword ptr [rsp+0E0h+var_B0], r15d
0x14011be4c  mov     [rsp+0E0h+var_B8], rax
0x14011be51  mov     dword ptr [rsp+0E0h+a], edi
0x14011be55  jmp     loc_14011C165
0x14011be5a  mov     r8, [rbp+57h+var_60]
0x14011be5e  test    r8, r8
0x14011be61  jz      short loc_14011BE97
0x14011be63  mov     eax, [r8+18h]
0x14011be67  sub     eax, 3
0x14011be6a  cmp     eax, 1
0x14011be6d  ja      short loc_14011BE97
0x14011be6f  mov     rbx, [rbp+57h+var_70]
0x14011be73  mov     rdx, r8
0x14011be76  mov     rcx, rbx
0x14011be79  call    InetDereferenceLocalAddressAf
0x14011be7e  cmp     rbx, [r12]
0x14011be82  jz      short loc_14011BE8C
0x14011be84  mov     rcx, rbx
0x14011be87  call    _InetDereferenceAf
0x14011be8c  mov     r15d, 0C0000207h
0x14011be92  jmp     loc_14011C178
0x14011be97  mov     rax, [rbp+57h+var_78]
0x14011be9b  movzx   edx, word ptr [rbp+57h+var_80+4]
0x14011be9f  mov     [rbp+57h+var_78], rax
0x14011bea3  mov     rax, [r12]
0x14011bea7  mov     [r14+78h], dx
0x14011beac  cmp     dx, [rax+18h]
0x14011beb0  jz      short loc_14011BEC0
0x14011beb2  test    dx, dx
0x14011beb5  jz      short loc_14011BEC0
0x14011beb7  mov     rcx, [r14+58h]
0x14011bebb  call    WfpAleEndpointUpdateFamily
0x14011bec0  mov     rax, [rbp+57h+var_70]
0x14011bec4  movzx   edx, byte ptr [rbp+57h+var_80]
0x14011bec8  mov     [r14+70h], rax
  ... truncated ...
```
