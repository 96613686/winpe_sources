# TcpTcbProcessNotificationChannelSetupRequest

- ea: `0x140112da4`
- end: `0x140113280`
- name: `TcpTcbProcessNotificationChannelSetupRequest`
- size: `1244`
- prototype: `__int64 __fastcall(PKSPIN_LOCK SpinLock)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14005a740`

## callees

- `0x14000de40`
- `0x140049760`
- `0x1400599a4`
- `0x14010a2a4`
- `0x140112da4`
- `0x140113288`
- `0x1401133cc`
- `0x14012e360`
- `0x14015d928`
- `0x1401c0fd0`
- `0x1401c1580`

## import_xrefs

- `ntoskrnl!PsGetProcessId` at `0x1401131a3`
- `ntoskrnl!PsGetProcessId` at `0x1401d659c`
- `ntoskrnl!PsGetProcessId` at `0x1401131a3`
- `ntoskrnl!PsGetProcessId` at `0x1401d659c`
- `ntoskrnl!KeWaitForSingleObject` at `0x140112f9b`
- `ntoskrnl!KeWaitForSingleObject` at `0x1401d620b`
- `ntoskrnl!KeWaitForSingleObject` at `0x140112f9b`
- `ntoskrnl!KeWaitForSingleObject` at `0x1401d620b`
- `ntoskrnl!KeInitializeEvent` at `0x140112e4d`
- `ntoskrnl!KeInitializeEvent` at `0x140112f1d`
- `ntoskrnl!KeInitializeEvent` at `0x140112e4d`
- `ntoskrnl!KeInitializeEvent` at `0x140112f1d`
- `ntoskrnl!KeReleaseSpinLock` at `0x140112e87`
- `ntoskrnl!KeReleaseSpinLock` at `0x140112f7e`
- `ntoskrnl!KeReleaseSpinLock` at `0x140112e87`
- `ntoskrnl!KeReleaseSpinLock` at `0x140112f7e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140112ed5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140112faa`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140112ed5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140112faa`
- `fwpkclnt!FwpsProxiedEndpointWasRedirectedToProxy` at `0x140112e9e`
- `fwpkclnt!FwpsProxiedEndpointWasRedirectedToProxy` at `0x140112e9e`
- `fwpkclnt!FwpsProxiedEndpointRegisterForExitingEndpoint` at `0x140113158`
- `fwpkclnt!FwpsProxiedEndpointRegisterForExitingEndpoint` at `0x140113158`
- `fwpkclnt!FwpsProxiedEndpointMetadataValueGet` at `0x1401d61c7`
- `fwpkclnt!FwpsProxiedEndpointMetadataValueGet` at `0x1401d6242`
- `fwpkclnt!FwpsProxiedEndpointMetadataValueGet` at `0x1401d61c7`
- `fwpkclnt!FwpsProxiedEndpointMetadataValueGet` at `0x1401d6242`
- `fwpkclnt!FwpsProxiedEndpointClassifiableFieldGet` at `0x1401d62d9`
- `fwpkclnt!FwpsProxiedEndpointClassifiableFieldGet` at `0x1401d6340`
- `fwpkclnt!FwpsProxiedEndpointClassifiableFieldGet` at `0x1401d6398`
- `fwpkclnt!FwpsProxiedEndpointClassifiableFieldGet` at `0x1401d6402`
- `fwpkclnt!FwpsProxiedEndpointClassifiableFieldGet` at `0x1401d62d9`
- `fwpkclnt!FwpsProxiedEndpointClassifiableFieldGet` at `0x1401d6340`
- `fwpkclnt!FwpsProxiedEndpointClassifiableFieldGet` at `0x1401d6398`
- `fwpkclnt!FwpsProxiedEndpointClassifiableFieldGet` at `0x1401d6402`
- `fwpkclnt!FwpsProxiedEndpointUnRegisterForExitingEndpoint` at `0x1401d645d`
- `fwpkclnt!FwpsProxiedEndpointUnRegisterForExitingEndpoint` at `0x1401d645d`

## pseudocode

```c
__int64 __fastcall TcpTcbProcessNotificationChannelSetupRequest(PKSPIN_LOCK SpinLock, __int64 a2, KIRQL a3)
{
  __int64 v4; // rsi
  unsigned int v6; // r15d
  char v7; // r14
  char v8; // r12
  char v9; // r13
  unsigned int v10; // edi
  int TcbConnectionParameters; // esi
  char v12; // r8
  KIRQL v13; // r14
  _OWORD *v14; // rcx
  int v15; // eax
  int v16; // eax
  KSPIN_LOCK v18; // rdx
  _DWORD **v19; // rcx
  char *v20; // r9
  char *v21; // r11
  int v22; // r10d
  __int16 v23; // cx
  __int16 v24; // ax
  int v25; // edx
  _QWORD *v26; // rax
  char ProcessId; // al
  KSPIN_LOCK v28; // rdx
  int v29; // eax
  NTSTATUS v30; // eax
  KSPIN_LOCK v31; // rdx
  int v32; // eax
  KSPIN_LOCK v33; // rax
  __int64 v34; // r8
  KSPIN_LOCK v35; // rdx
  __int64 v36; // r8
  KSPIN_LOCK v37; // rax
  KSPIN_LOCK v38; // rdx
  __int64 v39; // r8
  KSPIN_LOCK v40; // rax
  KSPIN_LOCK v41; // rax
  KSPIN_LOCK v42; // rdx
  int v43; // eax
  char v44; // al
  PLARGE_INTEGER Timeouta; // [rsp+20h] [rbp-E0h]
  PLARGE_INTEGER Timeout; // [rsp+20h] [rbp-E0h]
  int v47; // [rsp+28h] [rbp-D8h]
  __int16 v48; // [rsp+38h] [rbp-C8h]
  int v49; // [rsp+40h] [rbp-C0h]
  int v50; // [rsp+80h] [rbp-80h] BYREF
  __int128 v51; // [rsp+88h] [rbp-78h] BYREF
  __int64 v52; // [rsp+98h] [rbp-68h]
  _OWORD v53[4]; // [rsp+A0h] [rbp-60h] BYREF
  SOCKADDR_IN6 a[2]; // [rsp+E0h] [rbp-20h] BYREF
  struct _KEVENT Event; // [rsp+118h] [rbp+18h] BYREF
  struct _KEVENT Object; // [rsp+130h] [rbp+30h] BYREF
  union _LARGE_INTEGER v57[2]; // [rsp+148h] [rbp+48h] BYREF

  v52 = a2;
  DWORD2(v51) = 0;
  v4 = a2;
  *(_QWORD *)&v51 = 0;
  LOBYTE(v6) = 0;
  v50 = 0;
  memset(&Object, 0, sizeof(Object));
  memset(&Event, 0, sizeof(Event));
  memset(v53, 0, sizeof(v53));
  v7 = 1;
  v8 = 0;
  if ( dword_1402241D4 && (!TcpipTraceFiltersExist || *((char *)SpinLock + 804) < 0) )
  {
    *(_OWORD *)&v57[0].LowPart = 0;
    if ( ((__int64)WPP_MAIN_CB.Dpc.DeferredContext & 1) != 0 )
    {
      ProcessId = (unsigned __int8)PsGetProcessId((PEPROCESS)SpinLock[106]);
      v48 = *((_WORD *)SpinLock + 406);
      v47 = *((_DWORD *)SpinLock + 28);
      Timeouta = (PLARGE_INTEGER)SpinLock[5];
      v57[1].QuadPart = 0;
      v57[0].QuadPart = (LONGLONG)SpinLock;
      McTemplateK0ppqqqqq_EtwWriteTransfer(
        (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
        (unsigned int)TCP_CREATE_NOTIFICATION_CHANNEL_REQUEST,
        (unsigned int)v57,
        (_DWORD)SpinLock,
        (char)Timeouta,
        v47,
        ProcessId,
        v48,
        0);
    }
  }
  if ( SpinLock[5] )
  {
    v10 = -1073741637;
    goto LABEL_19;
  }
  if ( *((_DWORD *)SpinLock + 28) != 4 )
  {
    v10 = 0;
    goto LABEL_19;
  }
  *((_DWORD *)SpinLock + 202) |= 4u;
  v9 = 0;
  KeInitializeEvent(&Event, NotificationEvent, 0);
  *((_WORD *)SpinLock + 402) |= 0x10u;
  SpinLock[137] = (KSPIN_LOCK)&Event;
  if ( _InterlockedIncrement64((volatile signed __int64 *)SpinLock + 1) <= 1 )
    __fastfail(0xEu);
  KeReleaseSpinLock(SpinLock, a3);
  v10 = -1073741504;
  TcbConnectionParameters = FwpsProxiedEndpointWasRedirectedToProxy(SpinLock[113], &v50);
  if ( TcbConnectionParameters < 0 )
    goto LABEL_6;
  v12 = v50;
  v7 = 0;
  if ( !v50 )
    goto LABEL_7;
  TcbConnectionParameters = FwpsProxiedEndpointRegisterForExitingEndpoint(SpinLock[113], &Event);
  if ( TcbConnectionParameters < 0 )
  {
    v7 = 2;
LABEL_6:
    v12 = 0;
    v50 = 0;
    goto LABEL_7;
  }
  v28 = SpinLock[113];
  v51 = 0;
  v29 = FwpsProxiedEndpointMetadataValueGet(1, v28, 0x200000000LL, &v51);
  TcbConnectionParameters = v29;
  if ( v29 < 0 )
  {
    v7 = 3;
    goto LABEL_93;
  }
  if ( v29 == 259 )
  {
    v57[0].QuadPart = -189000000;
    v30 = KeWaitForSingleObject(&Event, Executive, 0, 0, v57);
    v9 = v30;
    if ( v30 == 258 )
      goto LABEL_92;
    v31 = SpinLock[113];
    v51 = 0;
    v32 = FwpsProxiedEndpointMetadataValueGet(1, v31, 0x200000000LL, &v51);
    TcbConnectionParameters = v32;
    if ( v32 < 0 || v32 == 259 )
    {
      v7 = 4;
      if ( v32 != 259 )
        goto LABEL_93;
      goto LABEL_92;
    }
  }
  if ( DWORD2(v51) == 2 )
  {
    LOWORD(v53[0]) = 2;
    goto LABEL_68;
  }
  if ( DWORD2(v51) != 23 )
  {
    v7 = 4;
LABEL_92:
    TcbConnectionParameters = -1073741504;
    goto LABEL_93;
  }
  LOWORD(v53[0]) = 23;
LABEL_68:
  v33 = SpinLock[3];
  v6 = 48;
  v34 = 48;
  v51 = 0;
  if ( *(_WORD *)(v33 + 24) != 2 )
    v34 = 50;
  TcbConnectionParameters = FwpsProxiedEndpointClassifiableFieldGet(1, SpinLock[113], v34, 4, &v51);
  if ( TcbConnectionParameters < 0 )
  {
    v7 = 5;
LABEL_73:
    LOBYTE(v6) = 0;
    goto LABEL_93;
  }
  v35 = SpinLock[113];
  WORD2(v53[2]) = WORD4(v51);
  v36 = 48;
  v37 = SpinLock[3];
  v51 = 0;
  if ( *(_WORD *)(v37 + 24) != 2 )
    v36 = 50;
  TcbConnectionParameters = FwpsProxiedEndpointClassifiableFieldGet(1, v35, v36, 7, &v51);
  if ( TcbConnectionParameters < 0 )
  {
    v7 = 6;
    goto LABEL_73;
  }
  v38 = SpinLock[113];
  v39 = 48;
  WORD3(v53[2]) = WORD4(v51);
  v40 = SpinLock[3];
  v51 = 0;
  if ( *(_WORD *)(v40 + 24) != 2 )
    v39 = 50;
  TcbConnectionParameters = FwpsProxiedEndpointClassifiableFieldGet(1, v38, v39, 2, &v51);
  if ( TcbConnectionParameters < 0 )
  {
    v7 = 7;
    goto LABEL_73;
  }
  if ( LOWORD(v53[0]) == 2 )
    DWORD1(v53[0]) = DWORD2(v51);
  else
    *(_OWORD *)((char *)v53 + 4) = **((_OWORD **)&v51 + 1);
  v41 = SpinLock[3];
  v42 = SpinLock[113];
  v51 = 0;
  if ( *(_WORD *)(v41 + 24) != 2 )
    v6 = 50;
  v43 = FwpsProxiedEndpointClassifiableFieldGet(1, v42, v6, 6, &v51);
  LOBYTE(v6) = 0;
  TcbConnectionParameters = v43;
  if ( v43 >= 0 )
  {
    if ( LOWORD(v53[0]) == 2 )
      DWORD1(v53[1]) = DWORD2(v51);
    else
      *(_OWORD *)((char *)&v53[1] + 4) = **((_OWORD **)&v51 + 1);
  }
  else
  {
    v7 = 8;
  }
LABEL_93:
  v12 = v50;
  if ( v50 )
  {
    FwpsProxiedEndpointUnRegisterForExitingEndpoint(SpinLock[113], &Event);
    if ( TcbConnectionParameters >= 0 )
    {
      memset(a, 0, sizeof(a));
      if ( LOWORD(v53[0]) == 2 )
      {
        a[0].sin6_flowinfo = DWORD1(v53[0]);
        a[0].sin6_port = WORD2(v53[2]);
        a[1].sin6_flowinfo = DWORD1(v53[1]);
        a[0].sin6_family = 2;
        a[1].sin6_family = 2;
      }
      else
      {
        a[0].sin6_port = WORD2(v53[2]);
        a[0].sin6_addr = *(IN6_ADDR *)((char *)v53 + 4);
        a[0].sin6_family = v53[0];
        a[0].sin6_scope_id = 0;
        a[1].sin6_family = v53[0];
        a[1].sin6_addr = *(IN6_ADDR *)((char *)&v53[1] + 4);
        a[1].sin6_scope_id = 0;
      }
      a[1].sin6_port = WORD3(v53[2]);
      v53[3] = 0;
      TcbConnectionParameters = TcpGetTcbConnectionParameters(a);
      if ( TcbConnectionParameters >= 0 )
        v8 = 1;
    }
    v12 = v50;
    if ( v50 )
    {
      if ( !dword_1402241D4
        || TcpipTraceFiltersExist && *((char *)SpinLock + 804) >= 0
        || ((__int64)WPP_MAIN_CB.Dpc.DeferredContext & 1) == 0 )
      {
        goto LABEL_8;
      }
      if ( LOWORD(v53[0]) == 2 )
      {
        LOBYTE(v22) = BYTE4(v53[1]);
        v20 = 0;
        v21 = 0;
        LOBYTE(v6) = BYTE4(v53[0]);
      }
      else
      {
        v20 = (char *)&v53[1] + 4;
        LOBYTE(v22) = 0;
        v21 = (char *)v53 + 4;
      }
      v23 = WORD3(v53[2]);
      v24 = WORD2(v53[2]);
      v25 = LOWORD(v53[0]);
      v57[1].QuadPart = 0;
      v57[0].QuadPart = (LONGLONG)SpinLock;
      goto LABEL_28;
    }
  }
LABEL_7:
  if ( !dword_1402241D4 || TcpipTraceFiltersExist && *((char *)SpinLock + 804) >= 0 )
    goto LABEL_8;
  *(_OWORD *)&v57[0].LowPart = 0;
  if ( ((__int64)WPP_MAIN_CB.Dpc.DeferredContext & 1) == 0 )
    goto LABEL_8;
  v18 = SpinLock[3];
  if ( *(_WORD *)(v18 + 24) == 2 )
  {
    v19 = (_DWORD **)SpinLock[4];
    v20 = 0;
    v21 = 0;
    v22 = *v19[2];
    v6 = ***((_DWORD ***)*v19 + 2);
  }
  else
  {
    v26 = (_QWORD *)SpinLock[4];
    LOBYTE(v22) = 0;
    v20 = (char *)v26[2];
    v21 = **(char ***)(*v26 + 16LL);
  }
  v23 = *((_WORD *)SpinLock + 59);
  v24 = *((_WORD *)SpinLock + 58);
  v57[0].QuadPart = (LONGLONG)SpinLock;
  v25 = *(unsigned __int16 *)(v18 + 24);
LABEL_28:
  McTemplateK0pqqqqqqbr5qqbr5hh_EtwWriteTransfer(
    (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
    v25,
    (unsigned int)v57,
    (_DWORD)SpinLock,
    v12,
    v7,
    TcbConnectionParameters,
    v9,
    v49,
    v6,
    (__int64)v21,
    v25,
    v22,
    (__int64)v20,
    __ROR2__(v24, 8),
    __ROR2__(v23, 8));
LABEL_8:
  v13 = KeAcquireSpinLockRaiseToDpc(SpinLock);
  TcpDereferenceTcb(SpinLock);
  *((_WORD *)SpinLock + 402) &= ~0x10u;
  if ( *((_DWORD *)SpinLock + 28) != 4 )
  {
    v10 = 0;
    goto LABEL_32;
  }
  if ( TcbConnectionParameters < 0 )
  {
LABEL_32:
    v4 = v52;
    goto LABEL_19;
  }
  if ( !v50 && *((_WORD *)SpinLock + 406) )
  {
    v10 = -1073741637;
    goto LABEL_32;
  }
  KeInitializeEvent(&Object, NotificationEvent, 0);
  v4 = v52;
  v14 = v53;
  if ( v50 != 1 )
    v14 = 0;
  v15 = TcpScheduleNotificationChannelWorkItemTcb((_DWORD)SpinLock, v52, 0, (unsigned int)&Object, (__int64)v14);
  v10 = v15;
  if ( v15 == 259 )
  {
    if ( _InterlockedIncrement64((volatile signed __int64 *)SpinLock + 1) <= 1 )
      __fastfail(0xEu);
    KeReleaseSpinLock(SpinLock, v13);
    KeWaitForSingleObject(&Object, Executive, 0, 0, 0);
    KeAcquireSpinLockRaiseToDpc(SpinLock);
    TcpDereferenceTcb(SpinLock);
    v10 = 0;
  }
  else if ( v15 < 0 )
  {
    goto LABEL_19;
  }
  v16 = v10;
  v8 = 0;
  if ( !SpinLock[5] )
    v16 = -1073741637;
  v10 = v16;
LABEL_19:
  if ( dword_1402241D4 && (!TcpipTraceFiltersExist || *((char *)SpinLock + 804) < 0) )
  {
    *(_OWORD *)&v57[0].LowPart = 0;
    if ( ((__int64)WPP_MAIN_CB.Dpc.DeferredContext & 1) != 0 )
    {
      v44 = (unsigned __int8)PsGetProcessId((PEPROCESS)SpinLock[106]);
      Timeout = (PLARGE_INTEGER)SpinLock[5];
      v57[1].QuadPart = 0;
      v57[0].QuadPart = (LONGLONG)SpinLock;
      McTemplateK0ppqqj_EtwWriteTransfer(
        (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
        (unsigned int)TCP_CREATE_NOTIFICATION_CHANNEL_REQUEST_PROCESSED,
        (unsigned int)v57,
        (_DWORD)SpinLock,
        (char)Timeout,
        v44,
        v10,
        v4);
    }
  }
  if ( v8 )
  {
    InetDereferenceNlInterfaceAf(*(_QWORD *)&v53[3], *((_QWORD *)&v53[3] + 1));
    InetDereferenceAf(*(_QWORD *)&v53[3]);
  }
  return v10;
}

```

## disassembly

```asm
0x140112da4  mov     [rsp-8+arg_18], rbx
0x140112da9  push    rbp
0x140112daa  push    rsi
0x140112dab  push    rdi
0x140112dac  push    r12
0x140112dae  push    r13
0x140112db0  push    r14
0x140112db2  push    r15
0x140112db4  lea     rbp, [rsp-60h]
0x140112db9  sub     rsp, 160h
0x140112dc0  mov     rax, cs:__security_cookie
0x140112dc7  xor     rax, rsp
0x140112dca  mov     [rbp+90h+var_38], rax
0x140112dce  xor     eax, eax
0x140112dd0  mov     [rbp+90h+var_F8], rdx
0x140112dd4  mov     dil, r8b
0x140112dd7  mov     qword ptr [rbp+90h+var_108+4], rax
0x140112ddb  mov     rsi, rdx
0x140112dde  mov     [rbp+90h+Object.Header.WaitListHead.Blink], rax
0x140112de2  mov     rbx, rcx
0x140112de5  mov     [rbp+90h+Event.Header.WaitListHead.Blink], rax
0x140112de9  xorps   xmm0, xmm0
0x140112dec  mov     [rbp-78h], rax
0x140112df0  xorps   xmm1, xmm1
0x140112df3  lea     r8d, [rax+40h]; Size
0x140112df7  xor     r15d, r15d
0x140112dfa  lea     rcx, [rbp+90h+var_F0]; void *
0x140112dfe  xor     edx, edx; Val
0x140112e00  mov     [rbp+90h+var_110], r15d
0x140112e04  movups  xmmword ptr [rbp+90h+Object.Header], xmm0
0x140112e08  movups  xmmword ptr [rbp+90h+Event.Header], xmm1
0x140112e0c  call    memset
0x140112e11  cmp     cs:dword_1402241D4, r15d
0x140112e18  lea     r14d, [r15+1]
0x140112e1c  movzx   r12d, r15b
0x140112e20  jnz     loc_14011317B
0x140112e26  cmp     [rbx+28h], r15
0x140112e2a  jnz     loc_1401130F3
0x140112e30  cmp     dword ptr [rbx+70h], 4
0x140112e34  jnz     loc_140113237
0x140112e3a  or      dword ptr [rbx+328h], 4
0x140112e41  lea     rcx, [rbp+90h+Event]; Event
0x140112e45  xor     r8d, r8d; State
0x140112e48  xor     edx, edx; Type
0x140112e4a  mov     r13d, r15d
0x140112e4d  call    cs:__imp_KeInitializeEvent
0x140112e54  nop     dword ptr [rax+rax+00h]
0x140112e59  or      word ptr [rbx+324h], 10h
0x140112e61  lea     rax, [rbp+90h+Event]
0x140112e65  mov     [rbx+448h], rax
0x140112e6c  mov     rax, r14
0x140112e6f  lock xadd [rbx+8], rax
0x140112e75  add     rax, r14
0x140112e78  cmp     rax, r14
0x140112e7b  jle     loc_1401131FF
0x140112e81  mov     dl, dil; NewIrql
0x140112e84  mov     rcx, rbx; SpinLock
0x140112e87  call    cs:__imp_KeReleaseSpinLock
0x140112e8e  nop     dword ptr [rax+rax+00h]
0x140112e93  mov     rcx, [rbx+388h]
0x140112e9a  lea     rdx, [rbp+90h+var_110]
0x140112e9e  call    cs:__imp_FwpsProxiedEndpointWasRedirectedToProxy
0x140112ea5  nop     dword ptr [rax+rax+00h]
0x140112eaa  mov     ecx, 2
0x140112eaf  mov     edi, 0C0000140h
0x140112eb4  mov     esi, eax
0x140112eb6  test    eax, eax
0x140112eb8  jns     loc_14011313D
0x140112ebe  mov     r8d, r15d
0x140112ec1  mov     [rbp+90h+var_110], r15d
0x140112ec5  cmp     cs:dword_1402241D4, r15d
0x140112ecc  jnz     loc_140113017
0x140112ed2  mov     rcx, rbx; SpinLock
0x140112ed5  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140112edc  nop     dword ptr [rax+rax+00h]
0x140112ee1  mov     rcx, rbx
0x140112ee4  mov     r14b, al
0x140112ee7  call    TcpDereferenceTcb
0x140112eec  mov     eax, 0FFEFh
0x140112ef1  and     [rbx+324h], ax
0x140112ef8  cmp     dword ptr [rbx+70h], 4
0x140112efc  jnz     loc_1401130E1
0x140112f02  test    esi, esi
0x140112f04  js      loc_1401130E4
0x140112f0a  cmp     [rbp+90h+var_110], r15d
0x140112f0e  jz      loc_1401130CC
0x140112f14  xor     r8d, r8d; State
0x140112f17  lea     rcx, [rbp+90h+Object]; Event
0x140112f1b  xor     edx, edx; Type
0x140112f1d  call    cs:__imp_KeInitializeEvent
0x140112f24  nop     dword ptr [rax+rax+00h]
0x140112f29  mov     rsi, [rbp+90h+var_F8]
0x140112f2d  lea     rcx, [rbp+90h+var_F0]
0x140112f31  mov     r13d, 1
0x140112f37  lea     r9, [rbp+90h+Object]
0x140112f3b  cmp     [rbp+90h+var_110], r13d
0x140112f3f  mov     rdx, rsi
0x140112f42  cmovnz  rcx, r15
0x140112f46  xor     r8d, r8d
0x140112f49  mov     [rsp+190h+Timeout], rcx
0x140112f4e  mov     rcx, rbx
0x140112f51  call    TcpScheduleNotificationChannelWorkItemTcb
0x140112f56  mov     edi, eax
0x140112f58  cmp     eax, 103h
0x140112f5d  jnz     loc_140113217
0x140112f63  mov     eax, r13d
0x140112f66  lock xadd [rbx+8], rax
0x140112f6c  add     rax, r13
0x140112f6f  cmp     rax, r13
0x140112f72  jle     loc_14011320B
0x140112f78  mov     dl, r14b; NewIrql
0x140112f7b  mov     rcx, rbx; SpinLock
0x140112f7e  call    cs:__imp_KeReleaseSpinLock
0x140112f85  nop     dword ptr [rax+rax+00h]
0x140112f8a  xor     r9d, r9d; Alertable
0x140112f8d  mov     [rsp+190h+Timeout], r15; Timeout
0x140112f92  xor     r8d, r8d; WaitMode
0x140112f95  lea     rcx, [rbp+90h+Object]; Object
0x140112f99  xor     edx, edx; WaitReason
0x140112f9b  call    cs:__imp_KeWaitForSingleObject
0x140112fa2  nop     dword ptr [rax+rax+00h]
0x140112fa7  mov     rcx, rbx; SpinLock
0x140112faa  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140112fb1  nop     dword ptr [rax+rax+00h]
0x140112fb6  mov     rcx, rbx
0x140112fb9  call    TcpDereferenceTcb
0x140112fbe  mov     edi, r15d
0x140112fc1  cmp     [rbx+28h], r15
0x140112fc5  mov     eax, edi
0x140112fc7  mov     edi, 0C00000BBh
0x140112fcc  mov     r12b, r15b
0x140112fcf  cmovz   eax, edi
0x140112fd2  mov     edi, eax
0x140112fd4  mov     r14, r13
0x140112fd7  cmp     cs:dword_1402241D4, r15d
0x140112fde  jnz     loc_140113117
0x140112fe4  test    r12b, r12b
0x140112fe7  jnz     loc_140113265
0x140112fed  mov     eax, edi
0x140112fef  mov     rcx, [rbp+90h+var_38]
0x140112ff3  xor     rcx, rsp; StackCookie
0x140112ff6  call    __security_check_cookie
0x140112ffb  mov     rbx, [rsp+190h+arg_18]
0x140113003  add     rsp, 160h
0x14011300a  pop     r15
0x14011300c  pop     r14
0x14011300e  pop     r13
0x140113010  pop     r12
0x140113012  pop     rdi
0x140113013  pop     rsi
0x140113014  pop     rbp
0x140113015  retn
0x140113017  cmp     cs:TcpipTraceFiltersExist, r15b
0x14011301e  jnz     loc_14011323F
0x140113024  test    byte ptr cs:WPP_MAIN_CB.Dpc.DeferredContext, 1
0x14011302b  xorps   xmm0, xmm0
0x14011302e  movups  xmmword ptr [rbp+90h+var_48], xmm0
0x140113032  jz      loc_140112ED2
0x140113038  mov     rdx, [rbx+18h]
0x14011303c  cmp     [rdx+18h], cx
0x140113040  jnz     loc_1401130FD
0x140113046  mov     rcx, [rbx+20h]
0x14011304a  mov     r9, r15
0x14011304d  mov     r11, r15
0x140113050  mov     rax, [rcx+10h]
0x140113054  mov     r10d, [rax]
0x140113057  mov     rax, [rcx]
0x14011305a  mov     rcx, [rax+10h]
0x14011305e  mov     rax, [rcx]
0x140113061  mov     r15d, [rax]
0x140113064  movzx   ecx, word ptr [rbx+76h]
0x140113068  movzx   eax, word ptr [rbx+74h]
0x14011306c  mov     qword ptr [rbp+90h+var_48], rbx
0x140113070  movzx   edx, word ptr [rdx+18h]
0x140113074  ror     cx, 8
0x140113078  mov     [rsp+190h+var_118], cx
0x14011307d  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x140113084  ror     ax, 8
0x140113088  mov     [rsp+190h+var_120], ax
0x14011308d  mov     [rsp+190h+var_128], r9
0x140113092  mov     r9, rbx
0x140113095  mov     [rsp+190h+var_130], r10d
0x14011309a  mov     [rsp+190h+var_138], edx
0x14011309e  mov     [rsp+190h+var_140], r11
0x1401130a3  mov     [rsp+190h+var_148], r15d
0x1401130a8  mov     dword ptr [rsp+190h+var_158], r13d
0x1401130ad  mov     [rsp+190h+var_160], esi
0x1401130b1  mov     [rsp+190h+var_168], r14d
0x1401130b6  mov     dword ptr [rsp+190h+Timeout], r8d
0x1401130bb  lea     r8, [rbp+90h+var_48]
0x1401130bf  call    McTemplateK0pqqqqqqbr5qqbr5hh_EtwWriteTransfer
0x1401130c4  xor     r15d, r15d
0x1401130c7  jmp     loc_140112ED2
0x1401130cc  cmp     [rbx+32Ch], r15w
0x1401130d4  jz      loc_140112F14
0x1401130da  mov     edi, 0C00000BBh
0x1401130df  jmp     short loc_1401130E4
0x1401130e1  mov     edi, r15d
0x1401130e4  mov     rsi, [rbp+90h+var_F8]
0x1401130e8  mov     r14d, 1
0x1401130ee  jmp     loc_140112FD7
0x1401130f3  mov     edi, 0C00000BBh
0x1401130f8  jmp     loc_140112FD7
0x1401130fd  mov     rax, [rbx+20h]
0x140113101  mov     r10d, r15d
0x140113104  mov     r9, [rax+10h]
0x140113108  mov     rax, [rax]
0x14011310b  mov     rcx, [rax+10h]
0x14011310f  mov     r11, [rcx]
0x140113112  jmp     loc_140113064
0x140113117  cmp     cs:TcpipTraceFiltersExist, r15b
0x14011311e  jnz     loc_140113252
0x140113124  test    byte ptr cs:WPP_MAIN_CB.Dpc.DeferredContext, r14b
0x14011312b  xorps   xmm0, xmm0
0x14011312e  movups  xmmword ptr [rbp+90h+var_48], xmm0
0x140113132  jz      loc_140112FE4
0x140113138  jmp     loc_1401D6595
0x14011313d  mov     r8d, [rbp+90h+var_110]
0x140113141  mov     r14d, r15d
0x140113144  test    r8d, r8d
0x140113147  jz      loc_140112EC5
0x14011314d  mov     rcx, [rbx+388h]
0x140113154  lea     rdx, [rbp+90h+Event]
0x140113158  call    cs:__imp_FwpsProxiedEndpointRegisterForExitingEndpoint
0x14011315f  nop     dword ptr [rax+rax+00h]
0x140113164  mov     esi, eax
0x140113166  test    eax, eax
0x140113168  jns     loc_1401D61A6
0x14011316e  mov     ecx, 2
0x140113173  mov     r14d, ecx
0x140113176  jmp     loc_140112EBE
0x14011317b  cmp     cs:TcpipTraceFiltersExist, r15b
0x140113182  jnz     loc_140113224
0x140113188  test    byte ptr cs:WPP_MAIN_CB.Dpc.DeferredContext, r14b
0x14011318f  xorps   xmm0, xmm0
0x140113192  movups  xmmword ptr [rbp+90h+var_48], xmm0
0x140113196  jz      loc_140112E26
0x14011319c  mov     rcx, [rbx+350h]; Process
0x1401131a3  call    cs:__imp_PsGetProcessId
0x1401131aa  nop     dword ptr [rax+rax+00h]
0x1401131af  movzx   ecx, word ptr [rbx+32Ch]
0x1401131b6  lea     r8, [rbp+90h+var_48]
0x1401131ba  mov     [rsp+190h+var_148], r15d
0x1401131bf  lea     rdx, TCP_CREATE_NOTIFICATION_CHANNEL_REQUEST
0x1401131c6  mov     [rsp+190h+var_150], r15d
0x1401131cb  mov     r9, rbx
0x1401131ce  mov     dword ptr [rsp+190h+var_158], ecx
0x1401131d2  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x1401131d9  mov     [rsp+190h+var_160], eax
0x1401131dd  mov     eax, [rbx+70h]
0x1401131e0  mov     [rsp+190h+var_168], eax
0x1401131e4  mov     rax, [rbx+28h]
0x1401131e8  mov     [rsp+190h+Timeout], rax
0x1401131ed  mov     qword ptr [rbp+90h+var_48+8], r15
0x1401131f1  mov     qword ptr [rbp+90h+var_48], rbx
0x1401131f5  call    McTemplateK0ppqqqqq_EtwWriteTransfer
0x1401131fa  jmp     loc_140112E26
0x1401131ff  mov     ecx, 0Eh
0x140113204  int     29h; Win8: RtlFailFast(ecx)
0x140113206  jmp     loc_140112E81
0x14011320b  mov     ecx, 0Eh
0x140113210  int     29h; Win8: RtlFailFast(ecx)
0x140113212  jmp     loc_140112F78
0x140113217  test    eax, eax
0x140113219  js      loc_140112FD4
0x14011321f  jmp     loc_140112FC1
0x140113224  mov     al, [rbx+324h]
0x14011322a  test    al, al
0x14011322c  jns     loc_140112E26
0x140113232  jmp     loc_140113188
0x140113237  mov     edi, r15d
0x14011323a  jmp     loc_140112FD7
0x14011323f  mov     al, [rbx+324h]
0x140113245  test    al, al
0x140113247  jns     loc_140112ED2
0x14011324d  jmp     loc_140113024
0x140113252  mov     al, [rbx+324h]
0x140113258  test    al, al
0x14011325a  jns     loc_140112FE4
0x140113260  jmp     loc_140113124
0x140113265  mov     rdx, qword ptr [rbp+90h+var_C0+8]
0x140113269  mov     rcx, qword ptr [rbp+90h+var_C0]
0x14011326d  call    InetDereferenceNlInterfaceAf
0x140113272  mov     rcx, qword ptr [rbp+90h+var_C0]
0x140113276  call    _InetDereferenceAf
0x14011327b  jmp     loc_140112FED
0x1401d61a6  mov     rdx, [rbx+388h]
0x1401d61ad  lea     r9, [rbp+90h+var_108]
0x1401d61b1  xorps   xmm0, xmm0
0x1401d61b4  mov     r8, 200000000h
0x1401d61be  mov     ecx, 1
0x1401d61c3  movups  [rbp+90h+var_108], xmm0
0x1401d61c7  call    cs:__imp_FwpsProxiedEndpointMetadataValueGet
0x1401d61ce  nop     dword ptr [rax+rax+00h]
0x1401d61d3  mov     esi, eax
0x1401d61d5  test    eax, eax
0x1401d61d7  jns     short loc_1401D61E7
0x1401d61d9  mov     ecx, 2
0x1401d61de  lea     r14d, [rcx+1]
0x1401d61e2  jmp     loc_1401D6445
  ... truncated ...
```
