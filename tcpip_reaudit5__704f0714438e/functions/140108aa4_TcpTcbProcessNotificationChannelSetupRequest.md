# TcpTcbProcessNotificationChannelSetupRequest

- ea: `0x140108aa4`
- end: `0x140108f80`
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
- `0x1400387d0`
- `0x140039b00`
- `0x1400fef24`
- `0x140108aa4`
- `0x140108f88`
- `0x1401090cc`
- `0x140124628`
- `0x14015bb98`
- `0x1401bf4d0`
- `0x1401bfa80`

## import_xrefs

- `ntoskrnl!PsGetProcessId` at `0x140108ea3`
- `ntoskrnl!PsGetProcessId` at `0x1401d2840`
- `ntoskrnl!PsGetProcessId` at `0x140108ea3`
- `ntoskrnl!PsGetProcessId` at `0x1401d2840`
- `ntoskrnl!KeWaitForSingleObject` at `0x140108c9b`
- `ntoskrnl!KeWaitForSingleObject` at `0x1401d24af`
- `ntoskrnl!KeWaitForSingleObject` at `0x140108c9b`
- `ntoskrnl!KeWaitForSingleObject` at `0x1401d24af`
- `ntoskrnl!KeInitializeEvent` at `0x140108b4d`
- `ntoskrnl!KeInitializeEvent` at `0x140108c1d`
- `ntoskrnl!KeInitializeEvent` at `0x140108b4d`
- `ntoskrnl!KeInitializeEvent` at `0x140108c1d`
- `ntoskrnl!KeReleaseSpinLock` at `0x140108b87`
- `ntoskrnl!KeReleaseSpinLock` at `0x140108c7e`
- `ntoskrnl!KeReleaseSpinLock` at `0x140108b87`
- `ntoskrnl!KeReleaseSpinLock` at `0x140108c7e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140108bd5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140108caa`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140108bd5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140108caa`
- `fwpkclnt!FwpsProxiedEndpointWasRedirectedToProxy` at `0x140108b9e`
- `fwpkclnt!FwpsProxiedEndpointWasRedirectedToProxy` at `0x140108b9e`
- `fwpkclnt!FwpsProxiedEndpointRegisterForExitingEndpoint` at `0x140108e58`
- `fwpkclnt!FwpsProxiedEndpointRegisterForExitingEndpoint` at `0x140108e58`
- `fwpkclnt!FwpsProxiedEndpointMetadataValueGet` at `0x1401d246b`
- `fwpkclnt!FwpsProxiedEndpointMetadataValueGet` at `0x1401d24e6`
- `fwpkclnt!FwpsProxiedEndpointMetadataValueGet` at `0x1401d246b`
- `fwpkclnt!FwpsProxiedEndpointMetadataValueGet` at `0x1401d24e6`
- `fwpkclnt!FwpsProxiedEndpointClassifiableFieldGet` at `0x1401d257d`
- `fwpkclnt!FwpsProxiedEndpointClassifiableFieldGet` at `0x1401d25e4`
- `fwpkclnt!FwpsProxiedEndpointClassifiableFieldGet` at `0x1401d263c`
- `fwpkclnt!FwpsProxiedEndpointClassifiableFieldGet` at `0x1401d26a6`
- `fwpkclnt!FwpsProxiedEndpointClassifiableFieldGet` at `0x1401d257d`
- `fwpkclnt!FwpsProxiedEndpointClassifiableFieldGet` at `0x1401d25e4`
- `fwpkclnt!FwpsProxiedEndpointClassifiableFieldGet` at `0x1401d263c`
- `fwpkclnt!FwpsProxiedEndpointClassifiableFieldGet` at `0x1401d26a6`
- `fwpkclnt!FwpsProxiedEndpointUnRegisterForExitingEndpoint` at `0x1401d2701`
- `fwpkclnt!FwpsProxiedEndpointUnRegisterForExitingEndpoint` at `0x1401d2701`

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
0x140108aa4  mov     [rsp-8+arg_18], rbx
0x140108aa9  push    rbp
0x140108aaa  push    rsi
0x140108aab  push    rdi
0x140108aac  push    r12
0x140108aae  push    r13
0x140108ab0  push    r14
0x140108ab2  push    r15
0x140108ab4  lea     rbp, [rsp-60h]
0x140108ab9  sub     rsp, 160h
0x140108ac0  mov     rax, cs:__security_cookie
0x140108ac7  xor     rax, rsp
0x140108aca  mov     [rbp+90h+var_38], rax
0x140108ace  xor     eax, eax
0x140108ad0  mov     [rbp+90h+var_F8], rdx
0x140108ad4  mov     dil, r8b
0x140108ad7  mov     qword ptr [rbp+90h+var_108+4], rax
0x140108adb  mov     rsi, rdx
0x140108ade  mov     [rbp+90h+Object.Header.WaitListHead.Blink], rax
0x140108ae2  mov     rbx, rcx
0x140108ae5  mov     [rbp+90h+Event.Header.WaitListHead.Blink], rax
0x140108ae9  xorps   xmm0, xmm0
0x140108aec  mov     [rbp-78h], rax
0x140108af0  xorps   xmm1, xmm1
0x140108af3  lea     r8d, [rax+40h]; Size
0x140108af7  xor     r15d, r15d
0x140108afa  lea     rcx, [rbp+90h+var_F0]; void *
0x140108afe  xor     edx, edx; Val
0x140108b00  mov     [rbp+90h+var_110], r15d
0x140108b04  movups  xmmword ptr [rbp+90h+Object.Header], xmm0
0x140108b08  movups  xmmword ptr [rbp+90h+Event.Header], xmm1
0x140108b0c  call    memset
0x140108b11  cmp     cs:dword_1402201D4, r15d
0x140108b18  lea     r14d, [r15+1]
0x140108b1c  movzx   r12d, r15b
0x140108b20  jnz     loc_140108E7B
0x140108b26  cmp     [rbx+28h], r15
0x140108b2a  jnz     loc_140108DF3
0x140108b30  cmp     dword ptr [rbx+70h], 4
0x140108b34  jnz     loc_140108F37
0x140108b3a  or      dword ptr [rbx+328h], 4
0x140108b41  lea     rcx, [rbp+90h+Event]; Event
0x140108b45  xor     r8d, r8d; State
0x140108b48  xor     edx, edx; Type
0x140108b4a  mov     r13d, r15d
0x140108b4d  call    cs:__imp_KeInitializeEvent
0x140108b54  nop     dword ptr [rax+rax+00h]
0x140108b59  or      word ptr [rbx+324h], 10h
0x140108b61  lea     rax, [rbp+90h+Event]
0x140108b65  mov     [rbx+448h], rax
0x140108b6c  mov     rax, r14
0x140108b6f  lock xadd [rbx+8], rax
0x140108b75  add     rax, r14
0x140108b78  cmp     rax, r14
0x140108b7b  jle     loc_140108EFF
0x140108b81  mov     dl, dil; NewIrql
0x140108b84  mov     rcx, rbx; SpinLock
0x140108b87  call    cs:__imp_KeReleaseSpinLock
0x140108b8e  nop     dword ptr [rax+rax+00h]
0x140108b93  mov     rcx, [rbx+388h]
0x140108b9a  lea     rdx, [rbp+90h+var_110]
0x140108b9e  call    cs:__imp_FwpsProxiedEndpointWasRedirectedToProxy
0x140108ba5  nop     dword ptr [rax+rax+00h]
0x140108baa  mov     ecx, 2
0x140108baf  mov     edi, 0C0000140h
0x140108bb4  mov     esi, eax
0x140108bb6  test    eax, eax
0x140108bb8  jns     loc_140108E3D
0x140108bbe  mov     r8d, r15d
0x140108bc1  mov     [rbp+90h+var_110], r15d
0x140108bc5  cmp     cs:dword_1402201D4, r15d
0x140108bcc  jnz     loc_140108D17
0x140108bd2  mov     rcx, rbx; SpinLock
0x140108bd5  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140108bdc  nop     dword ptr [rax+rax+00h]
0x140108be1  mov     rcx, rbx
0x140108be4  mov     r14b, al
0x140108be7  call    TcpDereferenceTcb
0x140108bec  mov     eax, 0FFEFh
0x140108bf1  and     [rbx+324h], ax
0x140108bf8  cmp     dword ptr [rbx+70h], 4
0x140108bfc  jnz     loc_140108DE1
0x140108c02  test    esi, esi
0x140108c04  js      loc_140108DE4
0x140108c0a  cmp     [rbp+90h+var_110], r15d
0x140108c0e  jz      loc_140108DCC
0x140108c14  xor     r8d, r8d; State
0x140108c17  lea     rcx, [rbp+90h+Object]; Event
0x140108c1b  xor     edx, edx; Type
0x140108c1d  call    cs:__imp_KeInitializeEvent
0x140108c24  nop     dword ptr [rax+rax+00h]
0x140108c29  mov     rsi, [rbp+90h+var_F8]
0x140108c2d  lea     rcx, [rbp+90h+var_F0]
0x140108c31  mov     r13d, 1
0x140108c37  lea     r9, [rbp+90h+Object]
0x140108c3b  cmp     [rbp+90h+var_110], r13d
0x140108c3f  mov     rdx, rsi
0x140108c42  cmovnz  rcx, r15
0x140108c46  xor     r8d, r8d
0x140108c49  mov     [rsp+190h+Timeout], rcx
0x140108c4e  mov     rcx, rbx
0x140108c51  call    TcpScheduleNotificationChannelWorkItemTcb
0x140108c56  mov     edi, eax
0x140108c58  cmp     eax, 103h
0x140108c5d  jnz     loc_140108F17
0x140108c63  mov     eax, r13d
0x140108c66  lock xadd [rbx+8], rax
0x140108c6c  add     rax, r13
0x140108c6f  cmp     rax, r13
0x140108c72  jle     loc_140108F0B
0x140108c78  mov     dl, r14b; NewIrql
0x140108c7b  mov     rcx, rbx; SpinLock
0x140108c7e  call    cs:__imp_KeReleaseSpinLock
0x140108c85  nop     dword ptr [rax+rax+00h]
0x140108c8a  xor     r9d, r9d; Alertable
0x140108c8d  mov     [rsp+190h+Timeout], r15; Timeout
0x140108c92  xor     r8d, r8d; WaitMode
0x140108c95  lea     rcx, [rbp+90h+Object]; Object
0x140108c99  xor     edx, edx; WaitReason
0x140108c9b  call    cs:__imp_KeWaitForSingleObject
0x140108ca2  nop     dword ptr [rax+rax+00h]
0x140108ca7  mov     rcx, rbx; SpinLock
0x140108caa  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140108cb1  nop     dword ptr [rax+rax+00h]
0x140108cb6  mov     rcx, rbx
0x140108cb9  call    TcpDereferenceTcb
0x140108cbe  mov     edi, r15d
0x140108cc1  cmp     [rbx+28h], r15
0x140108cc5  mov     eax, edi
0x140108cc7  mov     edi, 0C00000BBh
0x140108ccc  mov     r12b, r15b
0x140108ccf  cmovz   eax, edi
0x140108cd2  mov     edi, eax
0x140108cd4  mov     r14, r13
0x140108cd7  cmp     cs:dword_1402201D4, r15d
0x140108cde  jnz     loc_140108E17
0x140108ce4  test    r12b, r12b
0x140108ce7  jnz     loc_140108F65
0x140108ced  mov     eax, edi
0x140108cef  mov     rcx, [rbp+90h+var_38]
0x140108cf3  xor     rcx, rsp; StackCookie
0x140108cf6  call    __security_check_cookie
0x140108cfb  mov     rbx, [rsp+190h+arg_18]
0x140108d03  add     rsp, 160h
0x140108d0a  pop     r15
0x140108d0c  pop     r14
0x140108d0e  pop     r13
0x140108d10  pop     r12
0x140108d12  pop     rdi
0x140108d13  pop     rsi
0x140108d14  pop     rbp
0x140108d15  retn
0x140108d17  cmp     cs:TcpipTraceFiltersExist, r15b
0x140108d1e  jnz     loc_140108F3F
0x140108d24  test    byte ptr cs:WPP_MAIN_CB+148h, 1
0x140108d2b  xorps   xmm0, xmm0
0x140108d2e  movups  xmmword ptr [rbp+90h+var_48], xmm0
0x140108d32  jz      loc_140108BD2
0x140108d38  mov     rdx, [rbx+18h]
0x140108d3c  cmp     [rdx+18h], cx
0x140108d40  jnz     loc_140108DFD
0x140108d46  mov     rcx, [rbx+20h]
0x140108d4a  mov     r9, r15
0x140108d4d  mov     r11, r15
0x140108d50  mov     rax, [rcx+10h]
0x140108d54  mov     r10d, [rax]
0x140108d57  mov     rax, [rcx]
0x140108d5a  mov     rcx, [rax+10h]
0x140108d5e  mov     rax, [rcx]
0x140108d61  mov     r15d, [rax]
0x140108d64  movzx   ecx, word ptr [rbx+76h]
0x140108d68  movzx   eax, word ptr [rbx+74h]
0x140108d6c  mov     qword ptr [rbp+90h+var_48], rbx
0x140108d70  movzx   edx, word ptr [rdx+18h]
0x140108d74  ror     cx, 8
0x140108d78  mov     [rsp+190h+var_118], cx
0x140108d7d  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x140108d84  ror     ax, 8
0x140108d88  mov     [rsp+190h+var_120], ax
0x140108d8d  mov     [rsp+190h+var_128], r9
0x140108d92  mov     r9, rbx
0x140108d95  mov     [rsp+190h+var_130], r10d
0x140108d9a  mov     [rsp+190h+var_138], edx
0x140108d9e  mov     [rsp+190h+var_140], r11
0x140108da3  mov     [rsp+190h+var_148], r15d
0x140108da8  mov     dword ptr [rsp+190h+var_158], r13d
0x140108dad  mov     [rsp+190h+var_160], esi
0x140108db1  mov     [rsp+190h+var_168], r14d
0x140108db6  mov     dword ptr [rsp+190h+Timeout], r8d
0x140108dbb  lea     r8, [rbp+90h+var_48]
0x140108dbf  call    McTemplateK0pqqqqqqbr5qqbr5hh_EtwWriteTransfer
0x140108dc4  xor     r15d, r15d
0x140108dc7  jmp     loc_140108BD2
0x140108dcc  cmp     [rbx+32Ch], r15w
0x140108dd4  jz      loc_140108C14
0x140108dda  mov     edi, 0C00000BBh
0x140108ddf  jmp     short loc_140108DE4
0x140108de1  mov     edi, r15d
0x140108de4  mov     rsi, [rbp+90h+var_F8]
0x140108de8  mov     r14d, 1
0x140108dee  jmp     loc_140108CD7
0x140108df3  mov     edi, 0C00000BBh
0x140108df8  jmp     loc_140108CD7
0x140108dfd  mov     rax, [rbx+20h]
0x140108e01  mov     r10d, r15d
0x140108e04  mov     r9, [rax+10h]
0x140108e08  mov     rax, [rax]
0x140108e0b  mov     rcx, [rax+10h]
0x140108e0f  mov     r11, [rcx]
0x140108e12  jmp     loc_140108D64
0x140108e17  cmp     cs:TcpipTraceFiltersExist, r15b
0x140108e1e  jnz     loc_140108F52
0x140108e24  test    byte ptr cs:WPP_MAIN_CB+148h, r14b
0x140108e2b  xorps   xmm0, xmm0
0x140108e2e  movups  xmmword ptr [rbp+90h+var_48], xmm0
0x140108e32  jz      loc_140108CE4
0x140108e38  jmp     loc_1401D2839
0x140108e3d  mov     r8d, [rbp+90h+var_110]
0x140108e41  mov     r14d, r15d
0x140108e44  test    r8d, r8d
0x140108e47  jz      loc_140108BC5
0x140108e4d  mov     rcx, [rbx+388h]
0x140108e54  lea     rdx, [rbp+90h+Event]
0x140108e58  call    cs:__imp_FwpsProxiedEndpointRegisterForExitingEndpoint
0x140108e5f  nop     dword ptr [rax+rax+00h]
0x140108e64  mov     esi, eax
0x140108e66  test    eax, eax
0x140108e68  jns     loc_1401D244A
0x140108e6e  mov     ecx, 2
0x140108e73  mov     r14d, ecx
0x140108e76  jmp     loc_140108BBE
0x140108e7b  cmp     cs:TcpipTraceFiltersExist, r15b
0x140108e82  jnz     loc_140108F24
0x140108e88  test    byte ptr cs:WPP_MAIN_CB+148h, r14b
0x140108e8f  xorps   xmm0, xmm0
0x140108e92  movups  xmmword ptr [rbp+90h+var_48], xmm0
0x140108e96  jz      loc_140108B26
0x140108e9c  mov     rcx, [rbx+350h]; Process
0x140108ea3  call    cs:__imp_PsGetProcessId
0x140108eaa  nop     dword ptr [rax+rax+00h]
0x140108eaf  movzx   ecx, word ptr [rbx+32Ch]
0x140108eb6  lea     r8, [rbp+90h+var_48]
0x140108eba  mov     [rsp+190h+var_148], r15d
0x140108ebf  lea     rdx, TCP_CREATE_NOTIFICATION_CHANNEL_REQUEST
0x140108ec6  mov     [rsp+190h+var_150], r15d
0x140108ecb  mov     r9, rbx
0x140108ece  mov     dword ptr [rsp+190h+var_158], ecx
0x140108ed2  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x140108ed9  mov     [rsp+190h+var_160], eax
0x140108edd  mov     eax, [rbx+70h]
0x140108ee0  mov     [rsp+190h+var_168], eax
0x140108ee4  mov     rax, [rbx+28h]
0x140108ee8  mov     [rsp+190h+Timeout], rax
0x140108eed  mov     qword ptr [rbp+90h+var_48+8], r15
0x140108ef1  mov     qword ptr [rbp+90h+var_48], rbx
0x140108ef5  call    McTemplateK0ppqqqqq_EtwWriteTransfer
0x140108efa  jmp     loc_140108B26
0x140108eff  mov     ecx, 0Eh
0x140108f04  int     29h; Win8: RtlFailFast(ecx)
0x140108f06  jmp     loc_140108B81
0x140108f0b  mov     ecx, 0Eh
0x140108f10  int     29h; Win8: RtlFailFast(ecx)
0x140108f12  jmp     loc_140108C78
0x140108f17  test    eax, eax
0x140108f19  js      loc_140108CD4
0x140108f1f  jmp     loc_140108CC1
0x140108f24  mov     al, [rbx+324h]
0x140108f2a  test    al, al
0x140108f2c  jns     loc_140108B26
0x140108f32  jmp     loc_140108E88
0x140108f37  mov     edi, r15d
0x140108f3a  jmp     loc_140108CD7
0x140108f3f  mov     al, [rbx+324h]
0x140108f45  test    al, al
0x140108f47  jns     loc_140108BD2
0x140108f4d  jmp     loc_140108D24
0x140108f52  mov     al, [rbx+324h]
0x140108f58  test    al, al
0x140108f5a  jns     loc_140108CE4
0x140108f60  jmp     loc_140108E24
0x140108f65  mov     rdx, qword ptr [rbp+90h+var_C0+8]
0x140108f69  mov     rcx, qword ptr [rbp+90h+var_C0]
0x140108f6d  call    InetDereferenceNlInterfaceAf
0x140108f72  mov     rcx, qword ptr [rbp+90h+var_C0]
0x140108f76  call    _InetDereferenceAf
0x140108f7b  jmp     loc_140108CED
0x1401d244a  mov     rdx, [rbx+388h]
0x1401d2451  lea     r9, [rbp+90h+var_108]
0x1401d2455  xorps   xmm0, xmm0
0x1401d2458  mov     r8, 200000000h
0x1401d2462  mov     ecx, 1
0x1401d2467  movups  [rbp+90h+var_108], xmm0
0x1401d246b  call    cs:__imp_FwpsProxiedEndpointMetadataValueGet
0x1401d2472  nop     dword ptr [rax+rax+00h]
0x1401d2477  mov     esi, eax
0x1401d2479  test    eax, eax
0x1401d247b  jns     short loc_1401D248B
0x1401d247d  mov     ecx, 2
0x1401d2482  lea     r14d, [rcx+1]
0x1401d2486  jmp     loc_1401D26E9
  ... truncated ...
```
