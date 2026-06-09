# TcpTcbReceive

- ea: `0x140034520`
- end: `0x140034c82`
- name: `TcpTcbReceive`
- size: `1890`
- prototype: ``
- caller_count: `3`
- callee_count: `13`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x140032ff0`
- `0x1400b0440`
- `0x14012d8b4`

## callees

- `0x14001d640`
- `0x1400200a0`
- `0x140033e6c`
- `0x140034520`
- `0x1400387d0`
- `0x1400518f0`
- `0x1400ae7f8`
- `0x1400af0d0`
- `0x1400f0f60`
- `0x14011eb04`
- `0x14012ddd4`
- `0x140150c1c`
- `0x1401bf4d0`

## import_xrefs

- `ntoskrnl!PsUpdateNetworkCounters` at `0x140034c1d`
- `ntoskrnl!PsUpdateNetworkCounters` at `0x140034c1d`
- `ntoskrnl!KeBugCheck` at `0x140034c75`
- `ntoskrnl!KeBugCheck` at `0x140034c75`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140034baf`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140034baf`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140034636`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140034c00`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140034636`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140034c00`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140034b0c`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140034b0c`
- `ntoskrnl!EtwWriteTransfer` at `0x1400349ab`
- `ntoskrnl!EtwWriteTransfer` at `0x1400349ab`
- `NDIS!NdisNblTrackerTransferOwnership` at `0x1400346f2`
- `NDIS!NdisNblTrackerTransferOwnership` at `0x14003477c`
- `NDIS!NdisNblTrackerTransferOwnership` at `0x1400346f2`
- `NDIS!NdisNblTrackerTransferOwnership` at `0x14003477c`

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
  void *v56; // [rsp+150h] [rbp+50h]
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
        (unsigned int)&TCPIP_SILENTMODE,
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
      if ( LOBYTE(WPP_MAIN_CB.DeviceExtension) )
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
    if ( LOBYTE(WPP_MAIN_CB.DeviceExtension) )
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
                v56 = &unk_1401F214D;
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
0x140034520  push    rbp
0x140034522  push    rbx
0x140034523  push    rsi
0x140034524  push    r13
0x140034526  push    r14
0x140034528  push    r15
0x14003452a  lea     rbp, [rsp-98h]
0x140034532  sub     rsp, 198h
0x140034539  mov     rax, cs:__security_cookie
0x140034540  xor     rax, rsp
0x140034543  mov     [rbp+0C0h+var_40], rax
0x14003454a  mov     r14, [rbp+0C0h+arg_20]
0x140034551  xorps   xmm0, xmm0
0x140034554  mov     rbx, rdx
0x140034557  mov     [rsp+1C0h+var_170], 0
0x14003455c  xor     edx, edx
0x14003455e  mov     r13, rcx
0x140034561  movups  xmmword ptr [rbp+0C0h+var_A8], xmm0
0x140034565  mov     ecx, [r14]
0x140034568  mov     r15, r9
0x14003456b  movzx   eax, word ptr [rbx+224h]
0x140034572  mov     rsi, r8
0x140034575  mov     [rsp+1C0h+var_16C], edx
0x140034579  mov     [rsp+1C0h+var_168], edx
0x14003457d  movups  xmmword ptr [rbp+0C0h+var_A8+0Ch], xmm0
0x140034581  mov     dword ptr [rbp+0C0h+var_A8+0Ch], 0FFFFFFFFh
0x140034588  movups  [rsp+1C0h+var_150], xmm0
0x14003458d  movups  [rbp+0C0h+var_140], xmm0
0x140034591  movups  [rbp+0C0h+var_130], xmm0
0x140034595  movups  [rbp+0C0h+var_120], xmm0
0x140034599  movups  [rbp+0C0h+var_B8], xmm0
0x14003459d  movups  [rbp+0C0h+var_F8], xmm0
0x1400345a1  movups  [rbp+0C0h+var_E8], xmm0
0x1400345a5  movups  [rbp+0C0h+var_C8], xmm0
0x1400345a9  cmp     eax, ecx
0x1400345ab  jz      short loc_1400345B4
0x1400345ad  mov     [rbx+224h], cx
0x1400345b4  movzx   eax, word ptr [rbx+324h]
0x1400345bb  test    al, 8
0x1400345bd  jz      loc_14003464F
0x1400345c3  cmp     cs:dword_1402201D4, edx
0x1400345c9  jz      short loc_140034612
0x1400345cb  cmp     cs:TcpipTraceFiltersExist, dl
0x1400345d1  jz      short loc_1400345D7
0x1400345d3  test    al, al
0x1400345d5  jns     short loc_140034612
0x1400345d7  test    byte ptr cs:WPP_MAIN_CB.Reserved+3, 10h
0x1400345de  jz      short loc_140034612
0x1400345e0  mov     rax, [r8]
0x1400345e3  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x1400345ea  mov     [rbp+0C0h+EventDescriptor.Keyword], rdx
0x1400345ee  lea     r8, [rbp+0C0h+EventDescriptor]
0x1400345f2  mov     [rsp+1C0h+UserData], rax
0x1400345f7  lea     rdx, TCPIP_SILENTMODE
0x1400345fe  mov     r9, rbx
0x140034601  mov     [rsp+1C0h+UserDataCount], 2
0x140034609  mov     qword ptr [rbp+0C0h+EventDescriptor.Id], rbx
0x14003460d  call    McTemplateK0pqp_EtwWriteTransfer
0x140034612  mov     rdx, [rsi]
0x140034615  xor     r9d, r9d
0x140034618  mov     dword ptr [rsp+1C0h+UserData], 0E0004506h
0x140034620  mov     r8, r15
0x140034623  mov     rcx, r13
0x140034626  mov     byte ptr [rsp+1C0h+UserDataCount], 1
0x14003462b  call    TcpDiscardReceive
0x140034630  mov     rcx, rbx; SpinLock
0x140034633  mov     [rsi], r15
0x140034636  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x14003463d  nop     dword ptr [rax+rax+00h]
0x140034642  mov     rcx, rbx
0x140034645  call    TcpDereferenceTcb
0x14003464a  jmp     loc_140034C4F
0x14003464f  mov     [rsp+1C0h+arg_18], rdi
0x140034657  lea     rax, [rbp+0C0h+var_100]
0x14003465b  mov     rdi, [r8]
0x14003465e  mov     [rsp+1C0h+var_30], r12
0x140034666  mov     r12, [rbp+0C0h+arg_28]
0x14003466d  mov     [rbp+0C0h+var_108], rdi
0x140034671  mov     [rbp+0C0h+var_100], rdx
0x140034675  mov     [rbp+0C0h+var_110], rax
0x140034679  mov     rdx, 7FFFFFFFFFFFFFFFh
0x140034683  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x140034689  test    eax, eax
0x14003468b  jz      short loc_1400346B8
0x14003468d  mov     rax, [rsi]
0x140034690  mov     rcx, [rax+8]
0x140034694  mov     rcx, [rcx+0F8h]
0x14003469b  and     rcx, rdx
0x14003469e  jz      short loc_1400346B8
0x1400346a0  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x1400346a6  test    eax, eax
0x1400346a8  jz      short loc_1400346B8
0x1400346aa  mov     r8d, 10h
0x1400346b0  mov     rdx, rbx
0x1400346b3  call    TcpipEtwTransferActivity
0x1400346b8  test    r12, r12
0x1400346bb  jnz     loc_1400347C5
0x1400346c1  mov     rcx, [rsi]
0x1400346c4  cmp     [rcx+20h], r12
0x1400346c8  jz      loc_1400347C5
0x1400346ce  cmp     byte ptr cs:WPP_MAIN_CB.DeviceExtension, r12b
0x1400346d5  jz      short loc_1400346FE
0x1400346d7  mov     r8, qword ptr cs:WPP_MAIN_CB.DeviceQueue.20h
0x1400346de  mov     r9d, 0A3h
0x1400346e4  mov     rcx, [rcx+8]
0x1400346e8  xor     edx, edx
0x1400346ea  mov     [rsp+1C0h+UserDataCount], 1
0x1400346f2  call    cs:__imp_NdisNblTrackerTransferOwnership
0x1400346f9  nop     dword ptr [rax+rax+00h]
0x1400346fe  mov     rdx, [rsi]
0x140034701  movzx   r9d, word ptr [rbx+74h]
0x140034706  movzx   r8d, word ptr [r13+18h]
0x14003470b  mov     rax, [rdx+50h]
0x14003470f  movzx   ecx, byte ptr [rax+0Ch]
0x140034713  lea     rax, [rsp+1C0h+var_170]
0x140034718  mov     [rsp+1C0h+var_178], rax
0x14003471d  movzx   eax, word ptr [rbx+76h]
0x140034721  shr     ecx, 4
0x140034724  shl     ecx, 2
0x140034727  mov     [rsp+1C0h+var_180], ecx
0x14003472b  mov     rcx, rbx
0x14003472e  mov     byte ptr [rsp+1C0h+var_188], 0
0x140034733  mov     [rsp+1C0h+var_190], rdx
0x140034738  mov     rdx, [rbx+388h]
0x14003473f  mov     [rsp+1C0h+UserData], rdi
0x140034744  mov     word ptr [rsp+1C0h+UserDataCount], ax
0x140034749  call    InetInspectReceiveTcpDatagram
0x14003474e  mov     edi, eax
0x140034750  cmp     eax, 2
0x140034753  jz      short loc_1400347AA
0x140034755  cmp     byte ptr cs:WPP_MAIN_CB.DeviceExtension, 0
0x14003475c  jz      short loc_140034788
0x14003475e  mov     rcx, [rsi]
0x140034761  mov     r9d, 0A4h
0x140034767  mov     r8, cs:TcpNblTracker
0x14003476e  xor     edx, edx
0x140034770  mov     [rsp+1C0h+UserDataCount], 1
0x140034778  mov     rcx, [rcx+8]
0x14003477c  call    cs:__imp_NdisNblTrackerTransferOwnership
0x140034783  nop     dword ptr [rax+rax+00h]
0x140034788  test    edi, edi
0x14003478a  jnz     short loc_1400347C5
0x14003478c  mov     rdx, [rsi]
0x14003478f  xor     r9d, r9d
0x140034792  mov     dword ptr [rsp+1C0h+UserData], 0E0004505h
0x14003479a  mov     rcx, r13
0x14003479d  mov     byte ptr [rsp+1C0h+UserDataCount], dil
0x1400347a2  mov     r8, [rdx]
0x1400347a5  call    TcpDiscardReceive
0x1400347aa  mov     rax, [rsi]
0x1400347ad  mov     rcx, [rax]
0x1400347b0  mov     [rsi], rcx
0x1400347b3  cmp     rcx, r15
0x1400347b6  jz      loc_140034BD4
0x1400347bc  mov     rdi, [rbp+0C0h+var_108]
0x1400347c0  jmp     loc_140034679
0x1400347c5  mov     rdi, [rsi]
0x1400347c8  xor     r10d, r10d
0x1400347cb  cmp     r12, rdi
0x1400347ce  cmovz   r12, r10
0x1400347d2  mov     rax, [rdi+8]
0x1400347d6  mov     r9, [rax+8]
0x1400347da  mov     qword ptr [rsp+1C0h+var_150], rdi
0x1400347df  mov     rcx, [rdi+50h]
0x1400347e3  mov     qword ptr [rbp+0C0h+var_140+8], rcx
0x1400347e7  mov     eax, [rcx+4]
0x1400347ea  bswap   eax
0x1400347ec  mov     dword ptr [rbp+0C0h+var_130], eax
0x1400347ef  mov     eax, [rcx+8]
0x1400347f2  bswap   eax
0x1400347f4  mov     dword ptr [rbp+0C0h+var_130+4], eax
0x1400347f7  movzx   r8d, byte ptr [rcx+0Dh]
0x1400347fc  mov     byte ptr [rbp+0C0h+var_120], r8b
0x140034800  movzx   eax, word ptr [rcx+0Eh]
0x140034804  movzx   ecx, byte ptr [rbx+320h]
0x14003480b  ror     ax, 8
0x14003480f  movzx   edx, ax
0x140034812  shl     edx, cl
0x140034814  mov     dword ptr [rbp+0C0h+var_130+8], edx
0x140034817  mov     edx, r8d
0x14003481a  mov     rax, [rdi+8]
0x14003481e  and     r8d, 1
0x140034822  shr     edx, 1
0x140034824  and     edx, 1
0x140034827  mov     rcx, [rax+8]
0x14003482b  add     edx, [rcx+18h]
0x14003482e  add     edx, r8d
0x140034831  mov     byte ptr [rbp+0C0h+var_120+1], r10b
0x140034835  mov     dword ptr [rbp+0C0h+var_130+0Ch], edx
0x140034838  mov     r8d, 1
0x14003483e  movzx   eax, byte ptr [r9+5Ch]
0x140034843  movzx   edx, r8w
0x140034847  and     al, 3
0x140034849  mov     word ptr [rbp+0C0h+var_120+4], dx
0x14003484d  cmp     al, 3
0x14003484f  mov     dword ptr [rbp+0C0h+var_120+8], r10d
0x140034853  setz    byte ptr [rbp+0C0h+var_120+2]
0x140034857  mov     rax, [rdi+8]
0x14003485b  cmp     [rax+140h], r10d
0x140034862  jz      loc_140034A1F
0x140034868  movzx   eax, word ptr [rbx+324h]
0x14003486f  test    al, 2
0x140034871  jnz     loc_1400349B7
0x140034877  or      ax, 2
0x14003487b  mov     [rbx+324h], ax
0x140034882  mov     rax, [rbx+398h]
0x140034889  test    rax, rax
0x14003488c  jz      loc_1400349B7
0x140034892  mov     rax, [rax+8]
0x140034896  mov     rcx, [rax+18h]
0x14003489a  mov     eax, r8d
0x14003489d  lock xadd [rcx+6Ch], eax
0x1400348a2  inc     eax
0x1400348a4  cmp     eax, r8d
0x1400348a7  jnz     loc_1400349B7
0x1400348ad  mov     eax, [rcx+68h]
0x1400348b0  test    al, 4
0x1400348b2  jnz     loc_1400349B7
0x1400348b8  or      eax, 4
0x1400348bb  mov     [rcx+68h], eax
0x1400348be  mov     eax, cs:dword_1402201F8
0x1400348c4  cmp     eax, 5
0x1400348c7  jbe     loc_1400349B7
0x1400348cd  mov     rdx, cs:qword_140220210
0x1400348d4  mov     r9, 200000000000h
0x1400348de  mov     rax, cs:qword_140220208
0x1400348e5  test    r9, rax
0x1400348e8  jz      loc_1400349B7
0x1400348ee  mov     rax, rdx
0x1400348f1  and     rax, r9
0x1400348f4  cmp     rax, rdx
0x1400348f7  jnz     loc_1400349B7
0x1400348fd  mov     eax, [rcx+64h]
0x140034900  lea     rdx, [rbp+0C0h+EventDescriptor]; EventDescriptor
0x140034904  mov     [rsp+1C0h+var_164], eax
0x140034908  lea     rax, [rsp+1C0h+var_164]
0x14003490d  mov     [rbp+0C0h+var_60], rax
0x140034911  movzx   eax, word ptr [rcx+5Ah]
0x140034915  lea     rcx, _TraceLoggingMetadata
0x14003491c  mov     [rsp+1C0h+var_160], eax
0x140034920  lea     rax, [rsp+1C0h+var_160]
0x140034925  mov     [rbp+0C0h+var_50], rax
0x140034929  movzx   eax, cs:word_1401F2143
0x140034930  mov     dword ptr [rbp+0C0h+EventDescriptor.Level], eax
0x140034933  mov     rax, cs:off_140220200
0x14003493a  mov     [rbp+0C0h+var_80.Ptr], rax
0x14003493e  mov     [rbp+0C0h+EventDescriptor.Keyword], r9
0x140034942  xor     r9d, r9d; RelatedActivityId
0x140034945  mov     [rbp+0C0h+var_58], 4
0x14003494d  mov     [rbp+0C0h+var_48], 4
0x140034955  mov     dword ptr [rbp+0C0h+EventDescriptor.Id], 0B000000h
0x14003495c  movzx   eax, word ptr [rax]
0x14003495f  mov     [rbp+0C0h+var_80.Size], eax
0x140034962  lea     rax, unk_1401F214D
0x140034969  mov     [rbp+0C0h+var_70], rax
0x14003496d  lea     rax, _TraceLoggingMetadataEnd
0x140034974  sub     eax, ecx
0x140034976  mov     [rbp+0C0h+var_64], r8d
0x14003497a  mov     dword ptr [rbp+0C0h+var_80.0Ch], 2
0x140034981  xor     r8d, r8d; ActivityId
0x140034984  mov     [rbp+0C0h+var_68], 29h ; ')'
0x14003498b  mov     [rsp+1C0h+var_15C], eax
0x14003498f  mov     eax, [rsp+1C0h+var_15C]
0x140034993  mov     rcx, cs:RegHandle; RegHandle
0x14003499a  lea     rax, [rbp+0C0h+var_80]
0x14003499e  mov     [rsp+1C0h+UserData], rax; UserData
0x1400349a3  mov     [rsp+1C0h+UserDataCount], 4; UserDataCount
0x1400349ab  call    cs:__imp_EtwWriteTransfer
0x1400349b2  nop     dword ptr [rax+rax+00h]
0x1400349b7  mov     rax, [rdi+8]
0x1400349bb  mov     r8d, dword ptr [rbp+0C0h+var_130+0Ch]
0x1400349bf  movzx   ecx, word ptr [rax+140h]
0x1400349c6  mov     word ptr [rbp+0C0h+var_120+4], cx
0x1400349ca  mov     rax, [rdi+8]
0x1400349ce  mov     ecx, [rax+148h]
0x1400349d4  mov     eax, [r14]
0x1400349d7  mov     dword ptr [rbp+0C0h+var_120+8], ecx
0x1400349da  lea     rdx, [rax+rax*2]
0x1400349de  mov     rax, [rbx+18h]
0x1400349e2  shl     rdx, 6
0x1400349e6  add     rdx, [rax+80h]
0x1400349ed  mov     rcx, [rdx+18h]
0x1400349f1  add     rcx, r8
0x1400349f4  mov     [rdx+18h], rcx
0x1400349f8  mov     eax, [r14]
0x1400349fb  lea     rdx, [rax+rax*2]
0x1400349ff  mov     rax, [rbx+18h]
0x140034a03  shl     rdx, 6
0x140034a07  mov     rcx, [rax+80h]
0x140034a0e  mov     rax, [rdx+rcx+20h]
0x140034a13  inc     rax
0x140034a16  mov     [rdx+rcx+20h], rax
0x140034a1b  movzx   edx, word ptr [rbp+0C0h+var_120+4]
0x140034a1f  movzx   eax, word ptr [rbx+308h]
0x140034a26  test    ax, ax
0x140034a29  jz      short loc_140034A44
0x140034a2b  test    al, 1
0x140034a2d  jz      short loc_140034A44
0x140034a2f  mov     rax, [rbx+3A0h]
0x140034a36  mov     rcx, [rax]
  ... truncated ...
```
