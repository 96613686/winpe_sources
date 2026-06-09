# TcpTcbProcessNotificationChannelSetupRequest

- ea: `0x140108a84`
- end: `0x140108f60`
- name: `TcpTcbProcessNotificationChannelSetupRequest`
- size: `1244`
- prototype: `__int64 __fastcall(PKSPIN_LOCK SpinLock)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140002d40`

## callees

- `0x140006384`
- `0x140038530`
- `0x140039860`
- `0x1400fede4`
- `0x140108a84`
- `0x140108f68`
- `0x1401090ac`
- `0x1401244e8`
- `0x14015ba58`
- `0x1401bf390`
- `0x1401bf940`

## import_xrefs

- `ntoskrnl!PsGetProcessId` at `0x140108e83`
- `ntoskrnl!PsGetProcessId` at `0x1401d2700`
- `ntoskrnl!PsGetProcessId` at `0x140108e83`
- `ntoskrnl!PsGetProcessId` at `0x1401d2700`
- `ntoskrnl!KeWaitForSingleObject` at `0x140108c7b`
- `ntoskrnl!KeWaitForSingleObject` at `0x1401d236f`
- `ntoskrnl!KeWaitForSingleObject` at `0x140108c7b`
- `ntoskrnl!KeWaitForSingleObject` at `0x1401d236f`
- `ntoskrnl!KeInitializeEvent` at `0x140108b2d`
- `ntoskrnl!KeInitializeEvent` at `0x140108bfd`
- `ntoskrnl!KeInitializeEvent` at `0x140108b2d`
- `ntoskrnl!KeInitializeEvent` at `0x140108bfd`
- `ntoskrnl!KeReleaseSpinLock` at `0x140108b67`
- `ntoskrnl!KeReleaseSpinLock` at `0x140108c5e`
- `ntoskrnl!KeReleaseSpinLock` at `0x140108b67`
- `ntoskrnl!KeReleaseSpinLock` at `0x140108c5e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140108bb5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140108c8a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140108bb5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140108c8a`
- `fwpkclnt!FwpsProxiedEndpointWasRedirectedToProxy` at `0x140108b7e`
- `fwpkclnt!FwpsProxiedEndpointWasRedirectedToProxy` at `0x140108b7e`
- `fwpkclnt!FwpsProxiedEndpointRegisterForExitingEndpoint` at `0x140108e38`
- `fwpkclnt!FwpsProxiedEndpointRegisterForExitingEndpoint` at `0x140108e38`
- `fwpkclnt!FwpsProxiedEndpointMetadataValueGet` at `0x1401d232b`
- `fwpkclnt!FwpsProxiedEndpointMetadataValueGet` at `0x1401d23a6`
- `fwpkclnt!FwpsProxiedEndpointMetadataValueGet` at `0x1401d232b`
- `fwpkclnt!FwpsProxiedEndpointMetadataValueGet` at `0x1401d23a6`
- `fwpkclnt!FwpsProxiedEndpointClassifiableFieldGet` at `0x1401d243d`
- `fwpkclnt!FwpsProxiedEndpointClassifiableFieldGet` at `0x1401d24a4`
- `fwpkclnt!FwpsProxiedEndpointClassifiableFieldGet` at `0x1401d24fc`
- `fwpkclnt!FwpsProxiedEndpointClassifiableFieldGet` at `0x1401d2566`
- `fwpkclnt!FwpsProxiedEndpointClassifiableFieldGet` at `0x1401d243d`
- `fwpkclnt!FwpsProxiedEndpointClassifiableFieldGet` at `0x1401d24a4`
- `fwpkclnt!FwpsProxiedEndpointClassifiableFieldGet` at `0x1401d24fc`
- `fwpkclnt!FwpsProxiedEndpointClassifiableFieldGet` at `0x1401d2566`
- `fwpkclnt!FwpsProxiedEndpointUnRegisterForExitingEndpoint` at `0x1401d25c1`
- `fwpkclnt!FwpsProxiedEndpointUnRegisterForExitingEndpoint` at `0x1401d25c1`

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
  if ( dword_1402201D4 && (!TcpipTraceFiltersExist || *((char *)SpinLock + 804) < 0) )
  {
    *(_OWORD *)&v57[0].LowPart = 0;
    if ( (*(_BYTE *)(&WPP_MAIN_CB.Reserved + 1) & 1) != 0 )
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
      if ( !dword_1402201D4
        || TcpipTraceFiltersExist && *((char *)SpinLock + 804) >= 0
        || (*(_BYTE *)(&WPP_MAIN_CB.Reserved + 1) & 1) == 0 )
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
  if ( !dword_1402201D4 || TcpipTraceFiltersExist && *((char *)SpinLock + 804) >= 0 )
    goto LABEL_8;
  *(_OWORD *)&v57[0].LowPart = 0;
  if ( (*(_BYTE *)(&WPP_MAIN_CB.Reserved + 1) & 1) == 0 )
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
  if ( dword_1402201D4 && (!TcpipTraceFiltersExist || *((char *)SpinLock + 804) < 0) )
  {
    *(_OWORD *)&v57[0].LowPart = 0;
    if ( (*(_BYTE *)(&WPP_MAIN_CB.Reserved + 1) & 1) != 0 )
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
0x140108a84  mov     [rsp-8+arg_18], rbx
0x140108a89  push    rbp
0x140108a8a  push    rsi
0x140108a8b  push    rdi
0x140108a8c  push    r12
0x140108a8e  push    r13
0x140108a90  push    r14
0x140108a92  push    r15
0x140108a94  lea     rbp, [rsp-60h]
0x140108a99  sub     rsp, 160h
0x140108aa0  mov     rax, cs:__security_cookie
0x140108aa7  xor     rax, rsp
0x140108aaa  mov     [rbp+90h+var_38], rax
0x140108aae  xor     eax, eax
0x140108ab0  mov     [rbp+90h+var_F8], rdx
0x140108ab4  mov     dil, r8b
0x140108ab7  mov     qword ptr [rbp+90h+var_108+4], rax
0x140108abb  mov     rsi, rdx
0x140108abe  mov     [rbp+90h+Object.Header.WaitListHead.Blink], rax
0x140108ac2  mov     rbx, rcx
0x140108ac5  mov     [rbp+90h+Event.Header.WaitListHead.Blink], rax
0x140108ac9  xorps   xmm0, xmm0
0x140108acc  mov     [rbp-78h], rax
0x140108ad0  xorps   xmm1, xmm1
0x140108ad3  lea     r8d, [rax+40h]; Size
0x140108ad7  xor     r15d, r15d
0x140108ada  lea     rcx, [rbp+90h+var_F0]; void *
0x140108ade  xor     edx, edx; Val
0x140108ae0  mov     [rbp+90h+var_110], r15d
0x140108ae4  movups  xmmword ptr [rbp+90h+Object.Header], xmm0
0x140108ae8  movups  xmmword ptr [rbp+90h+Event.Header], xmm1
0x140108aec  call    memset
0x140108af1  cmp     cs:dword_1402201D4, r15d
0x140108af8  lea     r14d, [r15+1]
0x140108afc  movzx   r12d, r15b
0x140108b00  jnz     loc_140108E5B
0x140108b06  cmp     [rbx+28h], r15
0x140108b0a  jnz     loc_140108DD3
0x140108b10  cmp     dword ptr [rbx+70h], 4
0x140108b14  jnz     loc_140108F17
0x140108b1a  or      dword ptr [rbx+328h], 4
0x140108b21  lea     rcx, [rbp+90h+Event]; Event
0x140108b25  xor     r8d, r8d; State
0x140108b28  xor     edx, edx; Type
0x140108b2a  mov     r13d, r15d
0x140108b2d  call    cs:__imp_KeInitializeEvent
0x140108b34  nop     dword ptr [rax+rax+00h]
0x140108b39  or      word ptr [rbx+324h], 10h
0x140108b41  lea     rax, [rbp+90h+Event]
0x140108b45  mov     [rbx+448h], rax
0x140108b4c  mov     rax, r14
0x140108b4f  lock xadd [rbx+8], rax
0x140108b55  add     rax, r14
0x140108b58  cmp     rax, r14
0x140108b5b  jle     loc_140108EDF
0x140108b61  mov     dl, dil; NewIrql
0x140108b64  mov     rcx, rbx; SpinLock
0x140108b67  call    cs:__imp_KeReleaseSpinLock
0x140108b6e  nop     dword ptr [rax+rax+00h]
0x140108b73  mov     rcx, [rbx+388h]
0x140108b7a  lea     rdx, [rbp+90h+var_110]
0x140108b7e  call    cs:__imp_FwpsProxiedEndpointWasRedirectedToProxy
0x140108b85  nop     dword ptr [rax+rax+00h]
0x140108b8a  mov     ecx, 2
0x140108b8f  mov     edi, 0C0000140h
0x140108b94  mov     esi, eax
0x140108b96  test    eax, eax
0x140108b98  jns     loc_140108E1D
0x140108b9e  mov     r8d, r15d
0x140108ba1  mov     [rbp+90h+var_110], r15d
0x140108ba5  cmp     cs:dword_1402201D4, r15d
0x140108bac  jnz     loc_140108CF7
0x140108bb2  mov     rcx, rbx; SpinLock
0x140108bb5  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140108bbc  nop     dword ptr [rax+rax+00h]
0x140108bc1  mov     rcx, rbx
0x140108bc4  mov     r14b, al
0x140108bc7  call    TcpDereferenceTcb
0x140108bcc  mov     eax, 0FFEFh
0x140108bd1  and     [rbx+324h], ax
0x140108bd8  cmp     dword ptr [rbx+70h], 4
0x140108bdc  jnz     loc_140108DC1
0x140108be2  test    esi, esi
0x140108be4  js      loc_140108DC4
0x140108bea  cmp     [rbp+90h+var_110], r15d
0x140108bee  jz      loc_140108DAC
0x140108bf4  xor     r8d, r8d; State
0x140108bf7  lea     rcx, [rbp+90h+Object]; Event
0x140108bfb  xor     edx, edx; Type
0x140108bfd  call    cs:__imp_KeInitializeEvent
0x140108c04  nop     dword ptr [rax+rax+00h]
0x140108c09  mov     rsi, [rbp+90h+var_F8]
0x140108c0d  lea     rcx, [rbp+90h+var_F0]
0x140108c11  mov     r13d, 1
0x140108c17  lea     r9, [rbp+90h+Object]
0x140108c1b  cmp     [rbp+90h+var_110], r13d
0x140108c1f  mov     rdx, rsi
0x140108c22  cmovnz  rcx, r15
0x140108c26  xor     r8d, r8d
0x140108c29  mov     [rsp+190h+Timeout], rcx
0x140108c2e  mov     rcx, rbx
0x140108c31  call    TcpScheduleNotificationChannelWorkItemTcb
0x140108c36  mov     edi, eax
0x140108c38  cmp     eax, 103h
0x140108c3d  jnz     loc_140108EF7
0x140108c43  mov     eax, r13d
0x140108c46  lock xadd [rbx+8], rax
0x140108c4c  add     rax, r13
0x140108c4f  cmp     rax, r13
0x140108c52  jle     loc_140108EEB
0x140108c58  mov     dl, r14b; NewIrql
0x140108c5b  mov     rcx, rbx; SpinLock
0x140108c5e  call    cs:__imp_KeReleaseSpinLock
0x140108c65  nop     dword ptr [rax+rax+00h]
0x140108c6a  xor     r9d, r9d; Alertable
0x140108c6d  mov     [rsp+190h+Timeout], r15; Timeout
0x140108c72  xor     r8d, r8d; WaitMode
0x140108c75  lea     rcx, [rbp+90h+Object]; Object
0x140108c79  xor     edx, edx; WaitReason
0x140108c7b  call    cs:__imp_KeWaitForSingleObject
0x140108c82  nop     dword ptr [rax+rax+00h]
0x140108c87  mov     rcx, rbx; SpinLock
0x140108c8a  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140108c91  nop     dword ptr [rax+rax+00h]
0x140108c96  mov     rcx, rbx
0x140108c99  call    TcpDereferenceTcb
0x140108c9e  mov     edi, r15d
0x140108ca1  cmp     [rbx+28h], r15
0x140108ca5  mov     eax, edi
0x140108ca7  mov     edi, 0C00000BBh
0x140108cac  mov     r12b, r15b
0x140108caf  cmovz   eax, edi
0x140108cb2  mov     edi, eax
0x140108cb4  mov     r14, r13
0x140108cb7  cmp     cs:dword_1402201D4, r15d
0x140108cbe  jnz     loc_140108DF7
0x140108cc4  test    r12b, r12b
0x140108cc7  jnz     loc_140108F45
0x140108ccd  mov     eax, edi
0x140108ccf  mov     rcx, [rbp+90h+var_38]
0x140108cd3  xor     rcx, rsp; StackCookie
0x140108cd6  call    __security_check_cookie
0x140108cdb  mov     rbx, [rsp+190h+arg_18]
0x140108ce3  add     rsp, 160h
0x140108cea  pop     r15
0x140108cec  pop     r14
0x140108cee  pop     r13
0x140108cf0  pop     r12
0x140108cf2  pop     rdi
0x140108cf3  pop     rsi
0x140108cf4  pop     rbp
0x140108cf5  retn
0x140108cf7  cmp     cs:TcpipTraceFiltersExist, r15b
0x140108cfe  jnz     loc_140108F1F
0x140108d04  test    byte ptr cs:WPP_MAIN_CB+148h, 1
0x140108d0b  xorps   xmm0, xmm0
0x140108d0e  movups  xmmword ptr [rbp+90h+var_48], xmm0
0x140108d12  jz      loc_140108BB2
0x140108d18  mov     rdx, [rbx+18h]
0x140108d1c  cmp     [rdx+18h], cx
0x140108d20  jnz     loc_140108DDD
0x140108d26  mov     rcx, [rbx+20h]
0x140108d2a  mov     r9, r15
0x140108d2d  mov     r11, r15
0x140108d30  mov     rax, [rcx+10h]
0x140108d34  mov     r10d, [rax]
0x140108d37  mov     rax, [rcx]
0x140108d3a  mov     rcx, [rax+10h]
0x140108d3e  mov     rax, [rcx]
0x140108d41  mov     r15d, [rax]
0x140108d44  movzx   ecx, word ptr [rbx+76h]
0x140108d48  movzx   eax, word ptr [rbx+74h]
0x140108d4c  mov     qword ptr [rbp+90h+var_48], rbx
0x140108d50  movzx   edx, word ptr [rdx+18h]
0x140108d54  ror     cx, 8
0x140108d58  mov     [rsp+190h+var_118], cx
0x140108d5d  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x140108d64  ror     ax, 8
0x140108d68  mov     [rsp+190h+var_120], ax
0x140108d6d  mov     [rsp+190h+var_128], r9
0x140108d72  mov     r9, rbx
0x140108d75  mov     [rsp+190h+var_130], r10d
0x140108d7a  mov     [rsp+190h+var_138], edx
0x140108d7e  mov     [rsp+190h+var_140], r11
0x140108d83  mov     [rsp+190h+var_148], r15d
0x140108d88  mov     dword ptr [rsp+190h+var_158], r13d
0x140108d8d  mov     [rsp+190h+var_160], esi
0x140108d91  mov     [rsp+190h+var_168], r14d
0x140108d96  mov     dword ptr [rsp+190h+Timeout], r8d
0x140108d9b  lea     r8, [rbp+90h+var_48]
0x140108d9f  call    McTemplateK0pqqqqqqbr5qqbr5hh_EtwWriteTransfer
0x140108da4  xor     r15d, r15d
0x140108da7  jmp     loc_140108BB2
0x140108dac  cmp     [rbx+32Ch], r15w
0x140108db4  jz      loc_140108BF4
0x140108dba  mov     edi, 0C00000BBh
0x140108dbf  jmp     short loc_140108DC4
0x140108dc1  mov     edi, r15d
0x140108dc4  mov     rsi, [rbp+90h+var_F8]
0x140108dc8  mov     r14d, 1
0x140108dce  jmp     loc_140108CB7
0x140108dd3  mov     edi, 0C00000BBh
0x140108dd8  jmp     loc_140108CB7
0x140108ddd  mov     rax, [rbx+20h]
0x140108de1  mov     r10d, r15d
0x140108de4  mov     r9, [rax+10h]
0x140108de8  mov     rax, [rax]
0x140108deb  mov     rcx, [rax+10h]
0x140108def  mov     r11, [rcx]
0x140108df2  jmp     loc_140108D44
0x140108df7  cmp     cs:TcpipTraceFiltersExist, r15b
0x140108dfe  jnz     loc_140108F32
0x140108e04  test    byte ptr cs:WPP_MAIN_CB+148h, r14b
0x140108e0b  xorps   xmm0, xmm0
0x140108e0e  movups  xmmword ptr [rbp+90h+var_48], xmm0
0x140108e12  jz      loc_140108CC4
0x140108e18  jmp     loc_1401D26F9
0x140108e1d  mov     r8d, [rbp+90h+var_110]
0x140108e21  mov     r14d, r15d
0x140108e24  test    r8d, r8d
0x140108e27  jz      loc_140108BA5
0x140108e2d  mov     rcx, [rbx+388h]
0x140108e34  lea     rdx, [rbp+90h+Event]
0x140108e38  call    cs:__imp_FwpsProxiedEndpointRegisterForExitingEndpoint
0x140108e3f  nop     dword ptr [rax+rax+00h]
0x140108e44  mov     esi, eax
0x140108e46  test    eax, eax
0x140108e48  jns     loc_1401D230A
0x140108e4e  mov     ecx, 2
0x140108e53  mov     r14d, ecx
0x140108e56  jmp     loc_140108B9E
0x140108e5b  cmp     cs:TcpipTraceFiltersExist, r15b
0x140108e62  jnz     loc_140108F04
0x140108e68  test    byte ptr cs:WPP_MAIN_CB+148h, r14b
0x140108e6f  xorps   xmm0, xmm0
0x140108e72  movups  xmmword ptr [rbp+90h+var_48], xmm0
0x140108e76  jz      loc_140108B06
0x140108e7c  mov     rcx, [rbx+350h]; Process
0x140108e83  call    cs:__imp_PsGetProcessId
0x140108e8a  nop     dword ptr [rax+rax+00h]
0x140108e8f  movzx   ecx, word ptr [rbx+32Ch]
0x140108e96  lea     r8, [rbp+90h+var_48]
0x140108e9a  mov     [rsp+190h+var_148], r15d
0x140108e9f  lea     rdx, TCP_CREATE_NOTIFICATION_CHANNEL_REQUEST
0x140108ea6  mov     [rsp+190h+var_150], r15d
0x140108eab  mov     r9, rbx
0x140108eae  mov     dword ptr [rsp+190h+var_158], ecx
0x140108eb2  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x140108eb9  mov     [rsp+190h+var_160], eax
0x140108ebd  mov     eax, [rbx+70h]
0x140108ec0  mov     [rsp+190h+var_168], eax
0x140108ec4  mov     rax, [rbx+28h]
0x140108ec8  mov     [rsp+190h+Timeout], rax
0x140108ecd  mov     qword ptr [rbp+90h+var_48+8], r15
0x140108ed1  mov     qword ptr [rbp+90h+var_48], rbx
0x140108ed5  call    McTemplateK0ppqqqqq_EtwWriteTransfer
0x140108eda  jmp     loc_140108B06
0x140108edf  mov     ecx, 0Eh
0x140108ee4  int     29h; Win8: RtlFailFast(ecx)
0x140108ee6  jmp     loc_140108B61
0x140108eeb  mov     ecx, 0Eh
0x140108ef0  int     29h; Win8: RtlFailFast(ecx)
0x140108ef2  jmp     loc_140108C58
0x140108ef7  test    eax, eax
0x140108ef9  js      loc_140108CB4
0x140108eff  jmp     loc_140108CA1
0x140108f04  mov     al, [rbx+324h]
0x140108f0a  test    al, al
0x140108f0c  jns     loc_140108B06
0x140108f12  jmp     loc_140108E68
0x140108f17  mov     edi, r15d
0x140108f1a  jmp     loc_140108CB7
0x140108f1f  mov     al, [rbx+324h]
0x140108f25  test    al, al
0x140108f27  jns     loc_140108BB2
0x140108f2d  jmp     loc_140108D04
0x140108f32  mov     al, [rbx+324h]
0x140108f38  test    al, al
0x140108f3a  jns     loc_140108CC4
0x140108f40  jmp     loc_140108E04
0x140108f45  mov     rdx, qword ptr [rbp+90h+var_C0+8]
0x140108f49  mov     rcx, qword ptr [rbp+90h+var_C0]
0x140108f4d  call    InetDereferenceNlInterfaceAf
0x140108f52  mov     rcx, qword ptr [rbp+90h+var_C0]
0x140108f56  call    _InetDereferenceAf
0x140108f5b  jmp     loc_140108CCD
0x1401d230a  mov     rdx, [rbx+388h]
0x1401d2311  lea     r9, [rbp+90h+var_108]
0x1401d2315  xorps   xmm0, xmm0
0x1401d2318  mov     r8, 200000000h
0x1401d2322  mov     ecx, 1
0x1401d2327  movups  [rbp+90h+var_108], xmm0
0x1401d232b  call    cs:__imp_FwpsProxiedEndpointMetadataValueGet
0x1401d2332  nop     dword ptr [rax+rax+00h]
0x1401d2337  mov     esi, eax
0x1401d2339  test    eax, eax
0x1401d233b  jns     short loc_1401D234B
0x1401d233d  mov     ecx, 2
0x1401d2342  lea     r14d, [rcx+1]
0x1401d2346  jmp     loc_1401D25A9
  ... truncated ...
```
