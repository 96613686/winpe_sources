# TcpTcbReceive

- ea: `0x140034280`
- end: `0x1400349e2`
- name: `TcpTcbReceive`
- size: `1890`
- prototype: ``
- caller_count: `3`
- callee_count: `13`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140032d50`
- `0x1400b0820`
- `0x14012d774`

## callees

- `0x14001d3a0`
- `0x14001fe00`
- `0x140033bcc`
- `0x140034280`
- `0x140038530`
- `0x140051650`
- `0x1400aebd8`
- `0x1400af4b0`
- `0x1400f1070`
- `0x14011e9c4`
- `0x14012dc94`
- `0x140150adc`
- `0x1401bf390`

## import_xrefs

- `ntoskrnl!PsUpdateNetworkCounters` at `0x14003497d`
- `ntoskrnl!PsUpdateNetworkCounters` at `0x14003497d`
- `ntoskrnl!KeBugCheck` at `0x1400349d5`
- `ntoskrnl!KeBugCheck` at `0x1400349d5`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14003490f`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14003490f`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140034396`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140034960`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140034396`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140034960`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14003486c`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14003486c`
- `ntoskrnl!EtwWriteTransfer` at `0x14003470b`
- `ntoskrnl!EtwWriteTransfer` at `0x14003470b`
- `NDIS!NdisNblTrackerTransferOwnership` at `0x140034452`
- `NDIS!NdisNblTrackerTransferOwnership` at `0x1400344dc`
- `NDIS!NdisNblTrackerTransferOwnership` at `0x140034452`
- `NDIS!NdisNblTrackerTransferOwnership` at `0x1400344dc`

## pseudocode

```c
__int64 __fastcall TcpTcbReceive(__int64 a1, __int64 a2, _QWORD **a3, _QWORD *a4, unsigned int *a5, _QWORD *a6)
{
  unsigned int v8; // ecx
  int v10; // eax
  __int16 v12; // ax
  __int64 v13; // rax
  __int64 v15; // rdi
  int v17; // edi
  _QWORD *v18; // rcx
  _QWORD *v19; // rdi
  __int64 v20; // r9
  unsigned __int16 v21; // dx
  char v22; // al
  __int16 v23; // ax
  __int64 v24; // rax
  __int64 v25; // rcx
  int v26; // eax
  __int64 v27; // rax
  __int64 v28; // rdx
  __int16 v29; // ax
  _QWORD *v30; // r8
  __int16 v31; // ax
  _QWORD *v32; // rcx
  ULONG CurrentProcessorNumber; // eax
  __int64 v34; // rdi
  _QWORD *v35; // rcx
  ULONG UserDataCount[2]; // [rsp+20h] [rbp-E0h]
  __int64 v37; // [rsp+38h] [rbp-C8h]
  _BYTE v38[4]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v39; // [rsp+54h] [rbp-ACh] BYREF
  unsigned int v40; // [rsp+58h] [rbp-A8h] BYREF
  int v41; // [rsp+5Ch] [rbp-A4h] BYREF
  _DWORD v42[4]; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v43; // [rsp+70h] [rbp-90h] BYREF
  __int128 v44; // [rsp+80h] [rbp-80h]
  __int128 v45; // [rsp+90h] [rbp-70h]
  __int128 v46; // [rsp+A0h] [rbp-60h]
  __int64 *v47; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v48; // [rsp+B8h] [rbp-48h]
  __int64 v49; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v50; // [rsp+C8h] [rbp-38h] BYREF
  __int128 v51; // [rsp+D8h] [rbp-28h]
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+E8h] [rbp-18h] BYREF
  __int128 v53; // [rsp+F8h] [rbp-8h] BYREF
  _OWORD v54[3]; // [rsp+108h] [rbp+8h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+140h] [rbp+40h] BYREF
  char *v56; // [rsp+150h] [rbp+50h]
  int v57; // [rsp+158h] [rbp+58h]
  int v58; // [rsp+15Ch] [rbp+5Ch]
  int *v59; // [rsp+160h] [rbp+60h]
  __int64 v60; // [rsp+168h] [rbp+68h]
  _DWORD *v61; // [rsp+170h] [rbp+70h]
  __int64 v62; // [rsp+178h] [rbp+78h]

  v38[0] = 0;
  memset(&v54[1], 0, 28);
  v8 = *a5;
  v10 = *(unsigned __int16 *)(a2 + 548);
  v39 = 0;
  v40 = 0;
  HIDWORD(v54[1]) = -1;
  v43 = 0;
  v44 = 0;
  v45 = 0;
  v46 = 0;
  v54[0] = 0;
  v50 = 0;
  v51 = 0;
  v53 = 0;
  if ( v10 != v8 )
    *(_WORD *)(a2 + 548) = v8;
  v12 = *(_WORD *)(a2 + 804);
  if ( (v12 & 8) != 0 )
  {
    if ( dword_1402201D4 && (!TcpipTraceFiltersExist || (v12 & 0x80u) != 0) && (BYTE3(WPP_MAIN_CB.Reserved) & 0x10) != 0 )
    {
      v13 = (__int64)*a3;
      EventDescriptor.Keyword = 0;
      *(_QWORD *)&EventDescriptor.Id = a2;
      McTemplateK0pqp_EtwWriteTransfer(
        (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
        (unsigned int)TCPIP_SILENTMODE,
        (unsigned int)&EventDescriptor,
        a2,
        2,
        v13);
    }
    TcpDiscardReceive(a1, (unsigned int)*a3, (_DWORD)a4, 0, 1, -536853242);
    *a3 = a4;
    KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)a2);
    return TcpDereferenceTcb(a2);
  }
  v15 = (__int64)*a3;
  v48 = (__int64)*a3;
  v49 = 0;
  v47 = &v49;
  while ( 1 )
  {
    while ( 1 )
    {
      if ( Microsoft_Windows_Networking_CorrelationEnabled
        && (*(_QWORD *)((*a3)[1] + 248LL) & 0x7FFFFFFFFFFFFFFFLL) != 0
        && Microsoft_Windows_Networking_CorrelationEnabled )
      {
        TcpipEtwTransferActivity(*(_QWORD *)((*a3)[1] + 248LL) & 0x7FFFFFFFFFFFFFFFLL, a2, 16);
      }
      if ( a6 || !(*a3)[4] )
        goto LABEL_26;
      if ( TcpipNblTrackerEnabled )
      {
        UserDataCount[0] = 1;
        NdisNblTrackerTransferOwnership(
          (*a3)[1],
          0,
          *(_QWORD *)&WPP_MAIN_CB.DeviceQueue.1,
          163,
          *(_QWORD *)UserDataCount);
      }
      LOBYTE(v37) = 0;
      LOWORD(UserDataCount[0]) = *(_WORD *)(a2 + 118);
      v17 = ((__int64 (__fastcall *)(__int64, _QWORD, _QWORD, _QWORD, _QWORD, __int64, _QWORD, __int64, int, _BYTE *))InetInspectReceiveTcpDatagram)(
              a2,
              *(_QWORD *)(a2 + 904),
              *(unsigned __int16 *)(a1 + 24),
              *(unsigned __int16 *)(a2 + 116),
              *(_QWORD *)UserDataCount,
              v15,
              *a3,
              v37,
              4 * (*(unsigned __int8 *)((*a3)[10] + 12LL) >> 4),
              v38);
      if ( v17 != 2 )
        break;
LABEL_24:
      v18 = (_QWORD *)**a3;
      *a3 = v18;
      if ( v18 == a4 )
        goto LABEL_58;
      v15 = v48;
    }
    if ( TcpipNblTrackerEnabled )
    {
      UserDataCount[0] = 1;
      NdisNblTrackerTransferOwnership((*a3)[1], 0, TcpNblTracker, 164, *(_QWORD *)UserDataCount);
    }
    if ( !v17 )
    {
      TcpDiscardReceive(a1, (unsigned int)*a3, **a3, 0, 0, -536853243);
      goto LABEL_24;
    }
LABEL_26:
    v19 = *a3;
    if ( a6 == *a3 )
      a6 = 0;
    v20 = *(_QWORD *)(v19[1] + 8LL);
    *(_QWORD *)&v43 = *a3;
    *((_QWORD *)&v44 + 1) = v19[10];
    LODWORD(v45) = _byteswap_ulong(*(_DWORD *)(*((_QWORD *)&v44 + 1) + 4LL));
    DWORD1(v45) = _byteswap_ulong(*(_DWORD *)(*((_QWORD *)&v44 + 1) + 8LL));
    LOWORD(v46) = *(unsigned __int8 *)(*((_QWORD *)&v44 + 1) + 13LL);
    DWORD2(v45) = (unsigned __int16)__ROR2__(*(_WORD *)(*((_QWORD *)&v44 + 1) + 14LL), 8) << *(_BYTE *)(a2 + 800);
    HIDWORD(v45) = (v46 & 1) + *(_DWORD *)(*(_QWORD *)(v19[1] + 8LL) + 24LL) + (((unsigned __int8)v46 >> 1) & 1);
    v21 = 1;
    v22 = *(_BYTE *)(v20 + 92) & 3;
    WORD2(v46) = 1;
    DWORD2(v46) = 0;
    BYTE2(v46) = v22 == 3;
    if ( *(_DWORD *)(v19[1] + 320LL) )
    {
      v23 = *(_WORD *)(a2 + 804);
      if ( (v23 & 2) == 0 )
      {
        *(_WORD *)(a2 + 804) = v23 | 2;
        v24 = *(_QWORD *)(a2 + 920);
        if ( v24 )
        {
          v25 = *(_QWORD *)(*(_QWORD *)(v24 + 8) + 24LL);
          if ( _InterlockedIncrement((volatile signed __int32 *)(v25 + 108)) == 1 )
          {
            v26 = *(_DWORD *)(v25 + 104);
            if ( (v26 & 4) == 0 )
            {
              *(_DWORD *)(v25 + 104) = v26 | 4;
              if ( (unsigned int)dword_1402201F8 > 5
                && (qword_140220208 & 0x200000000000LL) != 0
                && (qword_140220210 & 0x200000000000LL) == qword_140220210 )
              {
                v41 = *(_DWORD *)(v25 + 100);
                v59 = &v41;
                v42[0] = *(unsigned __int16 *)(v25 + 90);
                v61 = v42;
                *(_DWORD *)&EventDescriptor.Level = 5;
                UserData.Ptr = (ULONGLONG)off_140220200;
                EventDescriptor.Keyword = 0x200000000000LL;
                v60 = 4;
                v62 = 4;
                *(_DWORD *)&EventDescriptor.Id = 184549376;
                UserData.Size = *(unsigned __int16 *)off_140220200;
                v56 = byte_1401F214D;
                v58 = 1;
                UserData.Reserved = 2;
                v57 = 41;
                v42[1] = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
                EtwWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 4u, &UserData);
              }
            }
          }
        }
      }
      WORD2(v46) = *(_WORD *)(v19[1] + 320LL);
      v27 = *a5;
      DWORD2(v46) = *(_DWORD *)(v19[1] + 328LL);
      v28 = *(_QWORD *)(*(_QWORD *)(a2 + 24) + 128LL) + 192 * v27;
      *(_QWORD *)(v28 + 24) += HIDWORD(v45);
      ++*(_QWORD *)(192LL * *a5 + *(_QWORD *)(*(_QWORD *)(a2 + 24) + 128LL) + 32);
      v21 = WORD2(v46);
    }
    v29 = *(_WORD *)(a2 + 776);
    if ( v29 && (v29 & 1) != 0 )
    {
      *(_QWORD *)(**(_QWORD **)(a2 + 928) + 24LL) += v21;
      v21 = WORD2(v46);
    }
    *(_QWORD *)(a2 + 512) += *(unsigned int *)(*(_QWORD *)((*a3)[1] + 8LL) + 24LL);
    v30 = *a3;
    *(_QWORD *)&v53 = *(unsigned int *)(*(_QWORD *)((*a3)[1] + 8LL) + 24LL) + (_QWORD)v53;
    v31 = *(_WORD *)(a2 + 776);
    if ( v31 && (v31 & 1) != 0 && *(_DWORD *)(*(_QWORD *)(v30[1] + 8LL) + 24LL) )
      *(_QWORD *)(**(_QWORD **)(a2 + 928) + 8LL) += v21;
    TcpTcbFastDatagram((PKSPIN_LOCK)a2, (__int64)v54, (__int64)&v50);
    if ( (_QWORD)v43 )
      break;
    v32 = (_QWORD *)**a3;
    *a3 = v32;
    if ( v32 == a4 )
      goto LABEL_58;
LABEL_57:
    v15 = v48;
    if ( (*(_DWORD *)(a2 + 120) & 2) == 0 )
      goto LABEL_58;
  }
  if ( !DWORD1(v51) )
    goto LABEL_51;
  if ( (*(_DWORD *)(a2 + 120) & 2) == 0 )
    goto LABEL_66;
  TcpProcessFastDatagramBatch((PKSPIN_LOCK)a2);
  if ( (*(_DWORD *)(a2 + 120) & 2) != 0 )
  {
LABEL_51:
    CurrentProcessorNumber = KeGetCurrentProcessorNumberEx(0);
    ++*((_QWORD *)TcpipGlobalCounters + 40 * CurrentProcessorNumber);
    if ( !(unsigned __int8)TcpTcbCarefulDatagram(a1, a2, &v43, &v47, a5, &v39, &v40, v54) )
    {
      if ( v39 != 34 )
        TcpLogPacketDiscard(a1, v43, v39, v40);
      v34 = v43;
      TcpNetBufferListChainDelay(*(_QWORD *)(v43 + 8), *(_QWORD *)(v43 + 8), *a5);
      *(_QWORD *)(v34 + 8) = 0;
    }
    v35 = (_QWORD *)**a3;
    *a3 = v35;
    if ( v35 == a4 )
      goto LABEL_63;
    KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)a2);
    goto LABEL_57;
  }
LABEL_58:
  if ( DWORD1(v51) )
  {
    if ( (*(_DWORD *)(a2 + 120) & 2) == 0 || *a3 != a4 )
LABEL_66:
      KeBugCheck(0x4Fu);
    TcpProcessFastDatagramBatch((PKSPIN_LOCK)a2);
  }
  KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)a2);
LABEL_63:
  PsUpdateNetworkCounters(*(_QWORD *)(a2 + 848), &v53, 16);
  if ( v49 )
    TcpCompleteTcbSend();
  return TcpDereferenceTcb(a2);
}

```

## disassembly

```asm
0x140034280  push    rbp
0x140034282  push    rbx
0x140034283  push    rsi
0x140034284  push    r13
0x140034286  push    r14
0x140034288  push    r15
0x14003428a  lea     rbp, [rsp-98h]
0x140034292  sub     rsp, 198h
0x140034299  mov     rax, cs:__security_cookie
0x1400342a0  xor     rax, rsp
0x1400342a3  mov     [rbp+0C0h+var_40], rax
0x1400342aa  mov     r14, [rbp+0C0h+arg_20]
0x1400342b1  xorps   xmm0, xmm0
0x1400342b4  mov     rbx, rdx
0x1400342b7  mov     [rsp+1C0h+var_170], 0
0x1400342bc  xor     edx, edx
0x1400342be  mov     r13, rcx
0x1400342c1  movups  xmmword ptr [rbp+0C0h+var_A8], xmm0
0x1400342c5  mov     ecx, [r14]
0x1400342c8  mov     r15, r9
0x1400342cb  movzx   eax, word ptr [rbx+224h]
0x1400342d2  mov     rsi, r8
0x1400342d5  mov     [rsp+1C0h+var_16C], edx
0x1400342d9  mov     [rsp+1C0h+var_168], edx
0x1400342dd  movups  xmmword ptr [rbp+0C0h+var_A8+0Ch], xmm0
0x1400342e1  mov     dword ptr [rbp+0C0h+var_A8+0Ch], 0FFFFFFFFh
0x1400342e8  movups  [rsp+1C0h+var_150], xmm0
0x1400342ed  movups  [rbp+0C0h+var_140], xmm0
0x1400342f1  movups  [rbp+0C0h+var_130], xmm0
0x1400342f5  movups  [rbp+0C0h+var_120], xmm0
0x1400342f9  movups  [rbp+0C0h+var_B8], xmm0
0x1400342fd  movups  [rbp+0C0h+var_F8], xmm0
0x140034301  movups  [rbp+0C0h+var_E8], xmm0
0x140034305  movups  [rbp+0C0h+var_C8], xmm0
0x140034309  cmp     eax, ecx
0x14003430b  jz      short loc_140034314
0x14003430d  mov     [rbx+224h], cx
0x140034314  movzx   eax, word ptr [rbx+324h]
0x14003431b  test    al, 8
0x14003431d  jz      loc_1400343AF
0x140034323  cmp     cs:dword_1402201D4, edx
0x140034329  jz      short loc_140034372
0x14003432b  cmp     cs:TcpipTraceFiltersExist, dl
0x140034331  jz      short loc_140034337
0x140034333  test    al, al
0x140034335  jns     short loc_140034372
0x140034337  test    byte ptr cs:WPP_MAIN_CB.Reserved+3, 10h
0x14003433e  jz      short loc_140034372
0x140034340  mov     rax, [r8]
0x140034343  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x14003434a  mov     [rbp+0C0h+EventDescriptor.Keyword], rdx
0x14003434e  lea     r8, [rbp+0C0h+EventDescriptor]
0x140034352  mov     [rsp+1C0h+UserData], rax
0x140034357  lea     rdx, TCPIP_SILENTMODE
0x14003435e  mov     r9, rbx
0x140034361  mov     [rsp+1C0h+UserDataCount], 2
0x140034369  mov     qword ptr [rbp+0C0h+EventDescriptor.Id], rbx
0x14003436d  call    McTemplateK0pqp_EtwWriteTransfer
0x140034372  mov     rdx, [rsi]
0x140034375  xor     r9d, r9d
0x140034378  mov     dword ptr [rsp+1C0h+UserData], 0E0004506h
0x140034380  mov     r8, r15
0x140034383  mov     rcx, r13
0x140034386  mov     byte ptr [rsp+1C0h+UserDataCount], 1
0x14003438b  call    TcpDiscardReceive
0x140034390  mov     rcx, rbx; SpinLock
0x140034393  mov     [rsi], r15
0x140034396  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x14003439d  nop     dword ptr [rax+rax+00h]
0x1400343a2  mov     rcx, rbx
0x1400343a5  call    TcpDereferenceTcb
0x1400343aa  jmp     loc_1400349AF
0x1400343af  mov     [rsp+1C0h+arg_18], rdi
0x1400343b7  lea     rax, [rbp+0C0h+var_100]
0x1400343bb  mov     rdi, [r8]
0x1400343be  mov     [rsp+1C0h+var_30], r12
0x1400343c6  mov     r12, [rbp+0C0h+arg_28]
0x1400343cd  mov     [rbp+0C0h+var_108], rdi
0x1400343d1  mov     [rbp+0C0h+var_100], rdx
0x1400343d5  mov     [rbp+0C0h+var_110], rax
0x1400343d9  mov     rdx, 7FFFFFFFFFFFFFFFh
0x1400343e3  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x1400343e9  test    eax, eax
0x1400343eb  jz      short loc_140034418
0x1400343ed  mov     rax, [rsi]
0x1400343f0  mov     rcx, [rax+8]
0x1400343f4  mov     rcx, [rcx+0F8h]
0x1400343fb  and     rcx, rdx
0x1400343fe  jz      short loc_140034418
0x140034400  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x140034406  test    eax, eax
0x140034408  jz      short loc_140034418
0x14003440a  mov     r8d, 10h
0x140034410  mov     rdx, rbx
0x140034413  call    TcpipEtwTransferActivity
0x140034418  test    r12, r12
0x14003441b  jnz     loc_140034525
0x140034421  mov     rcx, [rsi]
0x140034424  cmp     [rcx+20h], r12
0x140034428  jz      loc_140034525
0x14003442e  cmp     cs:TcpipNblTrackerEnabled, r12b
0x140034435  jz      short loc_14003445E
0x140034437  mov     r8, qword ptr cs:WPP_MAIN_CB.DeviceQueue.20h
0x14003443e  mov     r9d, 0A3h
0x140034444  mov     rcx, [rcx+8]
0x140034448  xor     edx, edx
0x14003444a  mov     [rsp+1C0h+UserDataCount], 1
0x140034452  call    cs:__imp_NdisNblTrackerTransferOwnership
0x140034459  nop     dword ptr [rax+rax+00h]
0x14003445e  mov     rdx, [rsi]
0x140034461  movzx   r9d, word ptr [rbx+74h]
0x140034466  movzx   r8d, word ptr [r13+18h]
0x14003446b  mov     rax, [rdx+50h]
0x14003446f  movzx   ecx, byte ptr [rax+0Ch]
0x140034473  lea     rax, [rsp+1C0h+var_170]
0x140034478  mov     [rsp+1C0h+var_178], rax
0x14003447d  movzx   eax, word ptr [rbx+76h]
0x140034481  shr     ecx, 4
0x140034484  shl     ecx, 2
0x140034487  mov     [rsp+1C0h+var_180], ecx
0x14003448b  mov     rcx, rbx
0x14003448e  mov     byte ptr [rsp+1C0h+var_188], 0
0x140034493  mov     [rsp+1C0h+var_190], rdx
0x140034498  mov     rdx, [rbx+388h]
0x14003449f  mov     [rsp+1C0h+UserData], rdi
0x1400344a4  mov     word ptr [rsp+1C0h+UserDataCount], ax
0x1400344a9  call    InetInspectReceiveTcpDatagram
0x1400344ae  mov     edi, eax
0x1400344b0  cmp     eax, 2
0x1400344b3  jz      short loc_14003450A
0x1400344b5  cmp     cs:TcpipNblTrackerEnabled, 0
0x1400344bc  jz      short loc_1400344E8
0x1400344be  mov     rcx, [rsi]
0x1400344c1  mov     r9d, 0A4h
0x1400344c7  mov     r8, cs:TcpNblTracker
0x1400344ce  xor     edx, edx
0x1400344d0  mov     [rsp+1C0h+UserDataCount], 1
0x1400344d8  mov     rcx, [rcx+8]
0x1400344dc  call    cs:__imp_NdisNblTrackerTransferOwnership
0x1400344e3  nop     dword ptr [rax+rax+00h]
0x1400344e8  test    edi, edi
0x1400344ea  jnz     short loc_140034525
0x1400344ec  mov     rdx, [rsi]
0x1400344ef  xor     r9d, r9d
0x1400344f2  mov     dword ptr [rsp+1C0h+UserData], 0E0004505h
0x1400344fa  mov     rcx, r13
0x1400344fd  mov     byte ptr [rsp+1C0h+UserDataCount], dil
0x140034502  mov     r8, [rdx]
0x140034505  call    TcpDiscardReceive
0x14003450a  mov     rax, [rsi]
0x14003450d  mov     rcx, [rax]
0x140034510  mov     [rsi], rcx
0x140034513  cmp     rcx, r15
0x140034516  jz      loc_140034934
0x14003451c  mov     rdi, [rbp+0C0h+var_108]
0x140034520  jmp     loc_1400343D9
0x140034525  mov     rdi, [rsi]
0x140034528  xor     r10d, r10d
0x14003452b  cmp     r12, rdi
0x14003452e  cmovz   r12, r10
0x140034532  mov     rax, [rdi+8]
0x140034536  mov     r9, [rax+8]
0x14003453a  mov     qword ptr [rsp+1C0h+var_150], rdi
0x14003453f  mov     rcx, [rdi+50h]
0x140034543  mov     qword ptr [rbp+0C0h+var_140+8], rcx
0x140034547  mov     eax, [rcx+4]
0x14003454a  bswap   eax
0x14003454c  mov     dword ptr [rbp+0C0h+var_130], eax
0x14003454f  mov     eax, [rcx+8]
0x140034552  bswap   eax
0x140034554  mov     dword ptr [rbp+0C0h+var_130+4], eax
0x140034557  movzx   r8d, byte ptr [rcx+0Dh]
0x14003455c  mov     byte ptr [rbp+0C0h+var_120], r8b
0x140034560  movzx   eax, word ptr [rcx+0Eh]
0x140034564  movzx   ecx, byte ptr [rbx+320h]
0x14003456b  ror     ax, 8
0x14003456f  movzx   edx, ax
0x140034572  shl     edx, cl
0x140034574  mov     dword ptr [rbp+0C0h+var_130+8], edx
0x140034577  mov     edx, r8d
0x14003457a  mov     rax, [rdi+8]
0x14003457e  and     r8d, 1
0x140034582  shr     edx, 1
0x140034584  and     edx, 1
0x140034587  mov     rcx, [rax+8]
0x14003458b  add     edx, [rcx+18h]
0x14003458e  add     edx, r8d
0x140034591  mov     byte ptr [rbp+0C0h+var_120+1], r10b
0x140034595  mov     dword ptr [rbp+0C0h+var_130+0Ch], edx
0x140034598  mov     r8d, 1
0x14003459e  movzx   eax, byte ptr [r9+5Ch]
0x1400345a3  movzx   edx, r8w
0x1400345a7  and     al, 3
0x1400345a9  mov     word ptr [rbp+0C0h+var_120+4], dx
0x1400345ad  cmp     al, 3
0x1400345af  mov     dword ptr [rbp+0C0h+var_120+8], r10d
0x1400345b3  setz    byte ptr [rbp+0C0h+var_120+2]
0x1400345b7  mov     rax, [rdi+8]
0x1400345bb  cmp     [rax+140h], r10d
0x1400345c2  jz      loc_14003477F
0x1400345c8  movzx   eax, word ptr [rbx+324h]
0x1400345cf  test    al, 2
0x1400345d1  jnz     loc_140034717
0x1400345d7  or      ax, 2
0x1400345db  mov     [rbx+324h], ax
0x1400345e2  mov     rax, [rbx+398h]
0x1400345e9  test    rax, rax
0x1400345ec  jz      loc_140034717
0x1400345f2  mov     rax, [rax+8]
0x1400345f6  mov     rcx, [rax+18h]
0x1400345fa  mov     eax, r8d
0x1400345fd  lock xadd [rcx+6Ch], eax
0x140034602  inc     eax
0x140034604  cmp     eax, r8d
0x140034607  jnz     loc_140034717
0x14003460d  mov     eax, [rcx+68h]
0x140034610  test    al, 4
0x140034612  jnz     loc_140034717
0x140034618  or      eax, 4
0x14003461b  mov     [rcx+68h], eax
0x14003461e  mov     eax, cs:dword_1402201F8
0x140034624  cmp     eax, 5
0x140034627  jbe     loc_140034717
0x14003462d  mov     rdx, cs:qword_140220210
0x140034634  mov     r9, 200000000000h
0x14003463e  mov     rax, cs:qword_140220208
0x140034645  test    r9, rax
0x140034648  jz      loc_140034717
0x14003464e  mov     rax, rdx
0x140034651  and     rax, r9
0x140034654  cmp     rax, rdx
0x140034657  jnz     loc_140034717
0x14003465d  mov     eax, [rcx+64h]
0x140034660  lea     rdx, [rbp+0C0h+EventDescriptor]; EventDescriptor
0x140034664  mov     [rsp+1C0h+var_164], eax
0x140034668  lea     rax, [rsp+1C0h+var_164]
0x14003466d  mov     [rbp+0C0h+var_60], rax
0x140034671  movzx   eax, word ptr [rcx+5Ah]
0x140034675  lea     rcx, _TraceLoggingMetadata
0x14003467c  mov     [rsp+1C0h+var_160], eax
0x140034680  lea     rax, [rsp+1C0h+var_160]
0x140034685  mov     [rbp+0C0h+var_50], rax
0x140034689  movzx   eax, cs:word_1401F2143
0x140034690  mov     dword ptr [rbp+0C0h+EventDescriptor.Level], eax
0x140034693  mov     rax, cs:off_140220200
0x14003469a  mov     [rbp+0C0h+var_80.Ptr], rax
0x14003469e  mov     [rbp+0C0h+EventDescriptor.Keyword], r9
0x1400346a2  xor     r9d, r9d; RelatedActivityId
0x1400346a5  mov     [rbp+0C0h+var_58], 4
0x1400346ad  mov     [rbp+0C0h+var_48], 4
0x1400346b5  mov     dword ptr [rbp+0C0h+EventDescriptor.Id], 0B000000h
0x1400346bc  movzx   eax, word ptr [rax]
0x1400346bf  mov     [rbp+0C0h+var_80.Size], eax
0x1400346c2  lea     rax, byte_1401F214D
0x1400346c9  mov     [rbp+0C0h+var_70], rax
0x1400346cd  lea     rax, _TraceLoggingMetadataEnd
0x1400346d4  sub     eax, ecx
0x1400346d6  mov     [rbp+0C0h+var_64], r8d
0x1400346da  mov     dword ptr [rbp+0C0h+var_80.0Ch], 2
0x1400346e1  xor     r8d, r8d; ActivityId
0x1400346e4  mov     [rbp+0C0h+var_68], 29h ; ')'
0x1400346eb  mov     [rsp+1C0h+var_15C], eax
0x1400346ef  mov     eax, [rsp+1C0h+var_15C]
0x1400346f3  mov     rcx, cs:RegHandle; RegHandle
0x1400346fa  lea     rax, [rbp+0C0h+var_80]
0x1400346fe  mov     [rsp+1C0h+UserData], rax; UserData
0x140034703  mov     [rsp+1C0h+UserDataCount], 4; UserDataCount
0x14003470b  call    cs:__imp_EtwWriteTransfer
0x140034712  nop     dword ptr [rax+rax+00h]
0x140034717  mov     rax, [rdi+8]
0x14003471b  mov     r8d, dword ptr [rbp+0C0h+var_130+0Ch]
0x14003471f  movzx   ecx, word ptr [rax+140h]
0x140034726  mov     word ptr [rbp+0C0h+var_120+4], cx
0x14003472a  mov     rax, [rdi+8]
0x14003472e  mov     ecx, [rax+148h]
0x140034734  mov     eax, [r14]
0x140034737  mov     dword ptr [rbp+0C0h+var_120+8], ecx
0x14003473a  lea     rdx, [rax+rax*2]
0x14003473e  mov     rax, [rbx+18h]
0x140034742  shl     rdx, 6
0x140034746  add     rdx, [rax+80h]
0x14003474d  mov     rcx, [rdx+18h]
0x140034751  add     rcx, r8
0x140034754  mov     [rdx+18h], rcx
0x140034758  mov     eax, [r14]
0x14003475b  lea     rdx, [rax+rax*2]
0x14003475f  mov     rax, [rbx+18h]
0x140034763  shl     rdx, 6
0x140034767  mov     rcx, [rax+80h]
0x14003476e  mov     rax, [rdx+rcx+20h]
0x140034773  inc     rax
0x140034776  mov     [rdx+rcx+20h], rax
0x14003477b  movzx   edx, word ptr [rbp+0C0h+var_120+4]
0x14003477f  movzx   eax, word ptr [rbx+308h]
0x140034786  test    ax, ax
0x140034789  jz      short loc_1400347A4
0x14003478b  test    al, 1
0x14003478d  jz      short loc_1400347A4
0x14003478f  mov     rax, [rbx+3A0h]
0x140034796  mov     rcx, [rax]
  ... truncated ...
```
