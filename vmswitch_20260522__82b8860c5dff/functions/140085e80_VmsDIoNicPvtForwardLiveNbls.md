# VmsDIoNicPvtForwardLiveNbls

- ea: `0x140085e80`
- end: `0x14008679a`
- name: `VmsDIoNicPvtForwardLiveNbls`
- size: `2330`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400ea360`

## callees

- `0x1400025a0`
- `0x140006620`
- `0x140006b00`
- `0x140017ca8`
- `0x1400247dc`
- `0x140027a64`
- `0x140033fa0`
- `0x140034130`
- `0x1400341b4`
- `0x14003a450`
- `0x140046e5c`
- `0x140046f1c`
- `0x1400478b0`
- `0x1400762cc`
- `0x14008497c`
- `0x140085e80`
- `0x1400867a0`
- `0x14009dd6c`
- `0x1401bbb52`
- `0x1401bbc40`
- `0x1401bc2c0`

## import_xrefs

- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140086027`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400860e6`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140086027`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400860e6`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400861fd`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400861fd`
- `ntoskrnl!IofCompleteRequest` at `0x1400864e0`
- `ntoskrnl!IofCompleteRequest` at `0x1400864e0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008671c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008671c`
- `ntoskrnl!ExAllocatePool2` at `0x140086604`
- `ntoskrnl!ExAllocatePool2` at `0x140086604`
- `NDIS!NdisReleaseRWLock` at `0x140086764`
- `NDIS!NdisReleaseRWLock` at `0x140086764`
- `NDIS!NdisAcquireRWLockWrite` at `0x1400860fd`
- `NDIS!NdisAcquireRWLockWrite` at `0x1400860fd`

## string_xrefs

- `0x14008616c`: `IsListEmpty(&DIoNicExt->ReadPacketQueue)`
- `0x14008619f`: `ReadPacketQueue is expected to be empty`

## pseudocode

```c
void __fastcall VmsDIoNicPvtForwardLiveNbls(__int64 a1, __int64 *a2, char a3)
{
  int v5; // edx
  __int64 v6; // rax
  __int64 v7; // rax
  __int64 v8; // rsi
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  bool v12; // di
  __int64 v13; // rax
  __int64 v14; // rax
  unsigned __int64 v15; // rax
  void *v16; // rsp
  _QWORD *v17; // rdx
  _QWORD *v18; // r8
  _QWORD *i; // rcx
  IRP *v20; // rsi
  __int64 v21; // rax
  _QWORD *v22; // rax
  _QWORD *v23; // rdi
  __int64 v24; // rcx
  int v25; // r10d
  char v26; // r13
  _MDL *MdlAddress; // rcx
  unsigned int Length; // edx
  bool v29; // zf
  char *MappedSystemVa; // r15
  char *v31; // rax
  int v32; // edi
  unsigned int v33; // r15d
  char *v34; // r11
  char v35; // di
  int LsoHint; // eax
  int v37; // edx
  int v38; // eax
  char inserted; // al
  int v40; // edx
  unsigned __int64 v41; // rcx
  char v42; // di
  int v43; // eax
  char v44; // si
  int v45; // eax
  int v46; // edx
  unsigned int v47; // esi
  __int64 Pool2; // rax
  int v49; // edx
  _QWORD *v50; // rdi
  int v51; // eax
  __int64 v52; // r8
  char v53; // si
  _QWORD *v54; // rcx
  int v55; // edx
  char v56; // [rsp+40h] [rbp+0h] BYREF
  char v57; // [rsp+41h] [rbp+1h]
  unsigned int v58; // [rsp+44h] [rbp+4h]
  struct _LOCK_STATE_EX LockState; // [rsp+48h] [rbp+8h] BYREF
  unsigned int v60; // [rsp+4Ch] [rbp+Ch] BYREF
  int v61; // [rsp+50h] [rbp+10h] BYREF
  _OWORD v62[2]; // [rsp+58h] [rbp+18h] BYREF
  char *v63; // [rsp+78h] [rbp+38h]
  char *v64; // [rsp+80h] [rbp+40h] BYREF
  _IO_STACK_LOCATION *CurrentStackLocation; // [rsp+88h] [rbp+48h]
  int v66[24]; // [rsp+90h] [rbp+50h] BYREF
  _QWORD v67[16]; // [rsp+F0h] [rbp+B0h] BYREF
  _UNKNOWN *retaddr; // [rsp+1B8h] [rbp+178h]

  v57 = a3;
  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  memset(v67, 0, sizeof(v67));
  memset(v66, 0, sizeof(v66));
  v61 = 0;
  memset(v62, 0, 26);
  if ( (VmsDiagnosticFlags & 1) == 0 )
  {
    if ( a2 )
      goto LABEL_6;
LABEL_24:
    LOBYTE(v5) = 2;
    WPP_RECORDER_SF_(VmsIfrNicLog, v5, 20, 48, (__int64)&WPP_e044bfdd865730b064bcaf57c723b6ba_Traceguids);
    return;
  }
  if ( !a2 )
    goto LABEL_24;
  v6 = a2[36];
  if ( v6 )
  {
    v7 = *(_QWORD *)(v6 + 16);
    if ( v7 )
    {
      *(_DWORD *)(v7 + 184) = 1668;
      *(_QWORD *)(v7 + 176) = "VmsDIoNicPvtForwardLiveNbls";
      *(_QWORD *)(v7 + 168) = retaddr;
    }
  }
LABEL_6:
  v8 = 4;
  if ( byte_1401F96F0 )
    v8 = HIDWORD(qword_1401F96CC);
  if ( (VmsDiagnosticFlags & 1) != 0 )
  {
    v9 = a2[36];
    if ( v9 )
    {
      v10 = *(_QWORD *)(v9 + 16);
      if ( v10 )
      {
        *(_DWORD *)(v10 + 184) = 75;
        *(_QWORD *)(v10 + 176) = "VmsNblIsSourceNicUntrusted";
        *(_QWORD *)(v10 + 168) = retaddr;
      }
    }
  }
  v11 = a2[36];
  v12 = 0;
  if ( v11 )
  {
    v13 = *(_QWORD *)(v11 + 16);
    if ( v13 )
    {
      v14 = *(_QWORD *)(v13 + 24);
      if ( v14 )
      {
        if ( *(_DWORD *)(v14 + 1872) == 3 )
          v12 = *(_BYTE *)(v14 + 1877) == 0;
      }
    }
  }
  v15 = 24 * v8 + 15;
  if ( v15 <= 24 * v8 )
    v15 = 0xFFFFFFFFFFFFFF0LL;
  v16 = alloca(v15 & 0xFFFFFFFFFFFFFFF0uLL);
  if ( !v12 || qword_1401F96E0 )
  {
    v66[0] = -267522035;
    v66[3] = KeGetCurrentProcessorNumberEx(0);
    LOBYTE(v66[1]) = 0;
    *(_QWORD *)&v66[6] = 0;
    *(_QWORD *)&v66[4] = 1;
    v66[2] = (qword_1401F96E0 != 0 ? 4 : 0) | v12;
    memset(&v66[11], 0, 24);
    LOBYTE(v66[10]) = 0;
    *(_QWORD *)&v66[8] = &v66[14];
    if ( &v56 )
    {
      v66[17] = v8;
      *(_QWORD *)&v66[18] = &v56;
    }
    else
    {
      v66[17] = 0;
      *(_QWORD *)&v66[18] = 0;
    }
    *(_QWORD *)&v66[20] = &g_BatchLibContext;
  }
  KeGetCurrentProcessorNumberEx(0);
  NdisAcquireRWLockWrite(*(PNDIS_RW_LOCK_EX *)(a1 + 48), &LockState, 0);
  v18 = (_QWORD *)(a1 + 8);
  for ( i = *(_QWORD **)(a1 + 8); ; i = (_QWORD *)*i )
  {
    v20 = 0;
    if ( i == v18 )
      break;
    v20 = (IRP *)(i - 21);
    v21 = _InterlockedExchange64(i - 8, 0);
    v17 = (_QWORD *)*i;
    if ( v21 )
    {
      if ( (_QWORD *)v17[1] != i || (v22 = (_QWORD *)i[1], (_QWORD *)*v22 != i) )
LABEL_97:
        __fastfail(3u);
      *v22 = v17;
      v23 = (_QWORD *)(a1 + 24);
      v17[1] = v22;
      if ( (_QWORD *)*v23 != v23 )
      {
        WPP_RECORDER_SF_s(
          VmsIfrLog,
          (_DWORD)v17,
          19,
          49,
          (__int64)&WPP_e044bfdd865730b064bcaf57c723b6ba_Traceguids,
          (__int64)"IsListEmpty(&DIoNicExt->ReadPacketQueue)");
        if ( (_QWORD *)*v23 != v23 )
        {
          MicrosoftTelemetryAssertTriggeredNoArgsKM();
          if ( (_QWORD *)*v23 != v23 )
            MicrosoftTelemetryAssertTriggeredArgsMsgKM(
              v24,
              *(unsigned int *)(a1 + 40),
              0,
              "ReadPacketQueue is expected to be empty");
        }
      }
      break;
    }
  }
  v25 = 0;
  v26 = 1;
  if ( !v20 )
    goto LABEL_77;
  MdlAddress = v20->MdlAddress;
  CurrentStackLocation = v20->Tail.Overlay.CurrentStackLocation;
  Length = CurrentStackLocation->Parameters.Read.Length;
  v29 = (MdlAddress->MdlFlags & 5) == 0;
  v58 = Length;
  v60 = Length;
  if ( v29 )
  {
    v31 = (char *)MmMapLockedPagesSpecifyCache(MdlAddress, 0, MmCached, 0, 0, 0x40000010u);
    Length = v58;
    v25 = 0;
    MappedSystemVa = v31;
  }
  else
  {
    MappedSystemVa = (char *)MdlAddress->MappedSystemVa;
  }
  v64 = MappedSystemVa;
  if ( MappedSystemVa )
  {
    v34 = 0;
    while ( 1 )
    {
      v63 = v34;
      if ( !Length )
        break;
      if ( v26 )
      {
        if ( !a2 )
          break;
        v35 = 14;
        v56 = 14;
        memset(v62, 0, sizeof(v62));
        if ( *((_WORD *)a2 + 160) > (unsigned __int16)v25 )
        {
          LsoHint = NvLibRscGetLsoHint((_DWORD)a2, Length, (unsigned int)v62 + 8, (unsigned int)&v56, (__int64)&v62[1]);
          v25 = 0;
          v32 = LsoHint;
          if ( LsoHint < 0 )
          {
            VmsPktReportDroppedPacketEx(*(_QWORD *)a1, (_DWORD)a2, 1, 0, LsoHint, -536862680);
            goto LABEL_44;
          }
          v35 = v56;
          LOWORD(v62[0]) |= 1u;
        }
        if ( v57 == (_BYTE)v25 )
        {
          VncGetTxChecksumOffloadInfo(a2, (char *)&v62[1] + 8, v62);
          v25 = 0;
          HIDWORD(v62[1]) = 2;
        }
        else
        {
          HIDWORD(v62[1]) = 1;
        }
        LOBYTE(v18) = v35;
        v32 = SegLibOffloadIteratorInitialize(
                (unsigned int)v67,
                (_DWORD)a2,
                (_DWORD)v18,
                (unsigned int)v62,
                v25,
                (__int64)&v61);
        if ( v32 < 0 )
        {
          LOBYTE(v37) = 2;
          WPP_RECORDER_SF_qdd(
            VmsIfrNicLog,
            v37,
            20,
            51,
            (__int64)&WPP_e044bfdd865730b064bcaf57c723b6ba_Traceguids,
            (char)a2,
            v57,
            v32);
          VmsPktReportDroppedPacketEx(*(_QWORD *)a1, (_DWORD)a2, 1, 0, v32, -536862679);
          goto LABEL_44;
        }
        if ( (v61 & 2) != 0 )
          VmsNblHelperIncrementSuccessCsoStats(a2, ((unsigned __int64)v62 + 8) & -(__int64)((v62[0] & 1) != 0), 0, 0);
        v26 = 0;
      }
      v38 = SegLibOffloadIteratorPacketSize(v67);
      inserted = VmsDIoNicPvtInsertPacket((_DWORD)MappedSystemVa, v58, (unsigned int)&v64, (unsigned int)&v60, v38);
      v25 = 0;
      if ( !inserted )
      {
        v33 = v60;
        goto LABEL_69;
      }
      v32 = SegLibDeferredOffloadIteratorCopyPacket(
              (__int64)v66,
              (__int64)v67,
              *(unsigned int *)MappedSystemVa,
              MappedSystemVa + 8);
      if ( v32 < 0 )
      {
        LOBYTE(v40) = 2;
        WPP_RECORDER_SF_id(
          VmsIfrNicLog,
          v40,
          20,
          52,
          (__int64)&WPP_e044bfdd865730b064bcaf57c723b6ba_Traceguids,
          (char)v67,
          v32);
        VmsPktReportDroppedPacketEx(*(_QWORD *)a1, (_DWORD)a2, 1, 0, v32, -536862678);
        v33 = v60;
        goto LABEL_72;
      }
      if ( !(unsigned __int8)SegLibOffloadIteratorNext(v67, 0) )
      {
        a2 = (__int64 *)*a2;
        v26 = 1;
      }
      Length = v60;
      v34 = MappedSystemVa;
      MappedSystemVa = v64;
      v58 = v60;
    }
    v33 = v58;
LABEL_69:
    if ( v34 )
    {
      *((_DWORD *)v34 + 1) = v25;
      v32 = v25;
    }
    else
    {
      LOBYTE(Length) = 2;
      WPP_RECORDER_SF_(VmsIfrNicLog, Length, 20, 53, (__int64)&WPP_e044bfdd865730b064bcaf57c723b6ba_Traceguids);
      v32 = -2147483643;
    }
  }
  else
  {
    LOBYTE(Length) = 2;
    WPP_RECORDER_SF_id(
      VmsIfrNicLog,
      Length,
      20,
      50,
      (__int64)&WPP_e044bfdd865730b064bcaf57c723b6ba_Traceguids,
      (char)v20->MdlAddress,
      16);
    v32 = -1073741670;
    VmsPktReportDroppedPacketEx(*(_QWORD *)a1, (_DWORD)a2, 1, 0, -1073741670, -536862681);
LABEL_44:
    v33 = v58;
  }
LABEL_72:
  LOBYTE(v18) = 1;
  BLFlushBatchOpContextEx(v66, 0, v18);
  if ( v32 < 0 )
    v41 = 0;
  else
    v41 = CurrentStackLocation->Parameters.Read.Length - v33;
  v20->IoStatus.Information = v41;
  v20->IoStatus.Status = v32;
  IofCompleteRequest(v20, 0);
  v25 = 0;
  if ( !v26 )
    v67[7] = 0;
LABEL_77:
  while ( *(int *)(a1 + 40) < 64 )
  {
    if ( v26 )
    {
      if ( !a2 )
        break;
      v42 = 14;
      v56 = 14;
      memset(v62, 0, sizeof(v62));
      if ( *((_WORD *)a2 + 160) > (unsigned __int16)v25 )
      {
        v43 = NvLibRscGetLsoHint((_DWORD)a2, (_DWORD)v17, (unsigned int)v62 + 8, (unsigned int)&v56, (__int64)&v62[1]);
        v25 = 0;
        if ( v43 < 0 )
        {
          VmsPktReportDroppedPacketEx(*(_QWORD *)a1, (_DWORD)a2, 1, 0, v43, -536862677);
          break;
        }
        LOWORD(v62[0]) |= 1u;
        v42 = v56;
      }
      v44 = v57;
      if ( v57 )
      {
        HIDWORD(v62[1]) = 1;
      }
      else
      {
        VncGetTxChecksumOffloadInfo(a2, (char *)&v62[1] + 8, v62);
        v25 = 0;
        HIDWORD(v62[1]) = 2;
      }
      LOBYTE(v18) = v42;
      v45 = SegLibOffloadIteratorInitialize(
              (unsigned int)v67,
              (_DWORD)a2,
              (_DWORD)v18,
              (unsigned int)v62,
              v25,
              (__int64)&v61);
      if ( v45 < 0 )
      {
        LOBYTE(v46) = 2;
        WPP_RECORDER_SF_qdd(
          VmsIfrNicLog,
          v46,
          20,
          54,
          (__int64)&WPP_e044bfdd865730b064bcaf57c723b6ba_Traceguids,
          (char)a2,
          v44,
          v45);
        break;
      }
      if ( (v61 & 2) != 0 )
        VmsNblHelperIncrementSuccessCsoStats(a2, ((unsigned __int64)v62 + 8) & -(__int64)((v62[0] & 1) != 0), 0, 0);
      v26 = 0;
    }
    v47 = SegLibOffloadIteratorPacketSize(v67);
    Pool2 = ExAllocatePool2(64, v47 + 24LL, 1229222742);
    v50 = (_QWORD *)Pool2;
    if ( !Pool2 )
    {
      LOBYTE(v49) = 2;
      WPP_RECORDER_SF_d(VmsIfrNicLog, v49, 20, 55, (__int64)&WPP_e044bfdd865730b064bcaf57c723b6ba_Traceguids, v47 + 24);
      break;
    }
    *(_DWORD *)(Pool2 + 16) = v47;
    v51 = SegLibDeferredOffloadIteratorCopyPacket((__int64)v66, (__int64)v67, v47, (char *)(Pool2 + 20));
    v53 = v51;
    if ( v51 < 0 )
    {
      LOBYTE(v52) = 1;
      BLFlushBatchOpContextEx(v66, 0, v52);
      LOBYTE(v55) = 2;
      WPP_RECORDER_SF_id(
        VmsIfrNicLog,
        v55,
        20,
        56,
        (__int64)&WPP_e044bfdd865730b064bcaf57c723b6ba_Traceguids,
        (char)v67,
        v53);
      ExFreePoolWithTag(v50, 0);
      break;
    }
    v54 = *(_QWORD **)(a1 + 32);
    if ( *v54 != a1 + 24 )
      goto LABEL_97;
    v50[1] = v54;
    *v50 = a1 + 24;
    *v54 = v50;
    *(_QWORD *)(a1 + 32) = v50;
    ++*(_DWORD *)(a1 + 40);
    if ( !(unsigned __int8)SegLibOffloadIteratorNext(v67, 0) )
    {
      a2 = (__int64 *)*a2;
      v26 = 1;
    }
  }
  LOBYTE(v18) = 1;
  BLFlushBatchOpContextEx(v66, 0, v18);
  NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(a1 + 48), &LockState);
}

```

## disassembly

```asm
0x140085e80  push    rbp
0x140085e82  push    rsi
0x140085e83  push    rdi
0x140085e84  push    r12
0x140085e86  push    r13
0x140085e88  push    r14
0x140085e8a  push    r15
0x140085e8c  sub     rsp, 180h
0x140085e93  lea     rbp, [rsp+40h]
0x140085e98  mov     [rbp+170h+arg_10], rbx
0x140085e9f  mov     rax, cs:__security_cookie
0x140085ea6  xor     rax, rbp
0x140085ea9  mov     [rbp+170h+var_40], rax
0x140085eb0  xor     eax, eax
0x140085eb2  mov     [rbp+170h+var_16F], r8b
0x140085eb6  mov     rbx, rdx
0x140085eb9  mov     word ptr [rbp+170h+LockState.OldIrql], ax
0x140085ebd  mov     r14, rcx
0x140085ec0  mov     [rbp+170h+LockState.Flags], al
0x140085ec3  xor     edx, edx; Val
0x140085ec5  lea     rcx, [rbp+170h+var_C0]; void *
0x140085ecc  mov     r8d, 80h; Size
0x140085ed2  call    memset
0x140085ed7  xor     edx, edx; Val
0x140085ed9  lea     rcx, [rbp+170h+var_120]; void *
0x140085edd  lea     r8d, [rdx+60h]; Size
0x140085ee1  call    memset
0x140085ee6  mov     rcx, [rbp+178h]
0x140085eed  xor     r13d, r13d
0x140085ef0  xor     eax, eax
0x140085ef2  mov     [rbp+170h+var_160], r13d
0x140085ef6  mov     eax, cs:VmsDiagnosticFlags
0x140085efc  xorps   xmm0, xmm0
0x140085eff  movups  [rbp+170h+var_158], xmm0
0x140085f03  lea     r12d, [r13+1]
0x140085f07  movups  [rbp+170h+var_158+0Ah], xmm0
0x140085f0b  test    r12b, al
0x140085f0e  jz      loc_140086096
0x140085f14  test    rbx, rbx
0x140085f17  jz      loc_14008609F
0x140085f1d  mov     rax, [rbx+120h]
0x140085f24  test    rax, rax
0x140085f27  jz      short loc_140085F51
0x140085f29  mov     rax, [rax+10h]
0x140085f2d  test    rax, rax
0x140085f30  jz      short loc_140085F51
0x140085f32  lea     rdx, aVmsdionicpvtfo; "VmsDIoNicPvtForwardLiveNbls"
0x140085f39  mov     dword ptr [rax+0B8h], 684h
0x140085f43  mov     [rax+0B0h], rdx
0x140085f4a  mov     [rax+0A8h], rcx
0x140085f51  cmp     cs:byte_1401F96F0, r13b
0x140085f58  mov     esi, 4
0x140085f5d  mov     eax, cs:VmsDiagnosticFlags
0x140085f63  cmovnz  esi, dword ptr cs:qword_1401F96CC+4
0x140085f6a  mov     rcx, [rbp+178h]
0x140085f71  test    r12b, al
0x140085f74  jz      short loc_140085FAA
0x140085f76  mov     rax, [rbx+120h]
0x140085f7d  test    rax, rax
0x140085f80  jz      short loc_140085FAA
0x140085f82  mov     rax, [rax+10h]
0x140085f86  test    rax, rax
0x140085f89  jz      short loc_140085FAA
0x140085f8b  lea     rdx, aVmsnblissource; "VmsNblIsSourceNicUntrusted"
0x140085f92  mov     dword ptr [rax+0B8h], 4Bh ; 'K'
0x140085f9c  mov     [rax+0B0h], rdx
0x140085fa3  mov     [rax+0A8h], rcx
0x140085faa  mov     rax, [rbx+120h]
0x140085fb1  mov     dil, r13b
0x140085fb4  test    rax, rax
0x140085fb7  jz      short loc_140085FE0
0x140085fb9  mov     rax, [rax+10h]
0x140085fbd  test    rax, rax
0x140085fc0  jz      short loc_140085FE0
0x140085fc2  mov     rax, [rax+18h]
0x140085fc6  test    rax, rax
0x140085fc9  jz      short loc_140085FE0
0x140085fcb  cmp     dword ptr [rax+750h], 3
0x140085fd2  jnz     short loc_140085FE0
0x140085fd4  cmp     [rax+755h], r13b
0x140085fdb  jnz     short loc_140085FE0
0x140085fdd  mov     dil, r12b
0x140085fe0  lea     rcx, [rsi+rsi*2]
0x140085fe4  shl     rcx, 3
0x140085fe8  lea     rax, [rcx+0Fh]
0x140085fec  cmp     rax, rcx
0x140085fef  ja      short loc_140085FFB
0x140085ff1  mov     rax, 0FFFFFFFFFFFFFF0h
0x140085ffb  and     rax, 0FFFFFFFFFFFFFFF0h
0x140085fff  call    __chkstk_0
0x140086004  sub     rsp, rax
0x140086007  lea     r15, [rsp+1B0h+var_170]
0x14008600c  cmp     dil, r12b
0x14008600f  jnz     short loc_14008601E
0x140086011  cmp     cs:qword_1401F96E0, r13
0x140086018  jz      loc_1400860E4
0x14008601e  xor     ecx, ecx; ProcNumber
0x140086020  mov     [rbp+170h+var_120], 0F00DF00Dh
0x140086027  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14008602e  nop     dword ptr [rax+rax+00h]
0x140086033  mov     [rbp+170h+var_114], eax
0x140086036  mov     rax, cs:qword_1401F96E0
0x14008603d  neg     rax
0x140086040  movzx   edx, dil
0x140086044  lea     rax, [rbp+170h+var_E8]
0x14008604b  mov     [rbp+170h+var_11C], r13b
0x14008604f  sbb     ecx, ecx
0x140086051  mov     [rbp+170h+var_108], r13
0x140086055  and     ecx, 4
0x140086058  mov     [rbp+170h+var_110], r12
0x14008605c  or      edx, ecx
0x14008605e  mov     [rbp+170h+var_F0], r13
0x140086065  mov     [rbp+170h+var_118], edx
0x140086068  mov     [rbp+170h+var_F4], r13d
0x14008606c  mov     [rbp+170h+var_F8], r13b
0x140086070  mov     [rbp+170h+var_E8], r13
0x140086077  mov     [rbp+170h+var_E0], r13d
0x14008607e  mov     [rbp+170h+var_100], rax
0x140086082  test    r15, r15
0x140086085  jz      short loc_1400860C8
0x140086087  mov     [rbp+170h+var_DC], esi
0x14008608d  mov     [rbp+170h+var_D8], r15
0x140086094  jmp     short loc_1400860D6
0x140086096  test    rbx, rbx
0x140086099  jnz     loc_140085F51
0x14008609f  mov     rcx, cs:VmsIfrNicLog
0x1400860a6  lea     r12, WPP_e044bfdd865730b064bcaf57c723b6ba_Traceguids
0x1400860ad  mov     r9d, 30h ; '0'
0x1400860b3  mov     qword ptr [rsp+1B0h+BugCheckOnFailure], r12
0x1400860b8  mov     dl, 2
0x1400860ba  lea     r8d, [r9-1Ch]
0x1400860be  call    WPP_RECORDER_SF_
0x1400860c3  jmp     loc_140086770
0x1400860c8  mov     [rbp+170h+var_DC], r13d
0x1400860cf  mov     [rbp+170h+var_D8], r13
0x1400860d6  lea     rax, g_BatchLibContext
0x1400860dd  mov     [rbp+170h+var_D0], rax
0x1400860e4  xor     ecx, ecx; ProcNumber
0x1400860e6  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x1400860ed  nop     dword ptr [rax+rax+00h]
0x1400860f2  mov     rcx, [r14+30h]; Lock
0x1400860f6  lea     rdx, [rbp+170h+LockState]; LockState
0x1400860fa  xor     r8d, r8d; Flags
0x1400860fd  call    cs:__imp_NdisAcquireRWLockWrite
0x140086104  nop     dword ptr [rax+rax+00h]
0x140086109  lea     r8, [r14+8]
0x14008610d  mov     rcx, [r8]
0x140086110  lea     r12, WPP_e044bfdd865730b064bcaf57c723b6ba_Traceguids
0x140086117  mov     rsi, r13
0x14008611a  cmp     rcx, r8
0x14008611d  jz      loc_1400861AE
0x140086123  lea     rsi, [rcx-0A8h]
0x14008612a  mov     rax, r13
0x14008612d  xchg    rax, [rsi+68h]
0x140086131  mov     rdx, [rcx]
0x140086134  test    rax, rax
0x140086137  jnz     short loc_14008613E
0x140086139  mov     rcx, rdx
0x14008613c  jmp     short loc_140086110
0x14008613e  cmp     [rdx+8], rcx
0x140086142  jnz     loc_1400866D5
0x140086148  mov     rax, [rcx+8]
0x14008614c  cmp     [rax], rcx
0x14008614f  jnz     loc_1400866D5
0x140086155  mov     [rax], rdx
0x140086158  lea     rdi, [r14+18h]
0x14008615c  mov     [rdx+8], rax
0x140086160  cmp     [rdi], rdi
0x140086163  jz      short loc_1400861AE
0x140086165  mov     rcx, cs:VmsIfrLog
0x14008616c  lea     rax, aIslistemptyDio; "IsListEmpty(&DIoNicExt->ReadPacketQueue"...
0x140086173  mov     r9d, 31h ; '1'
0x140086179  mov     qword ptr [rsp+1B0h+Priority], rax
0x14008617e  mov     qword ptr [rsp+1B0h+BugCheckOnFailure], r12
0x140086183  lea     r8d, [r9-1Eh]
0x140086187  call    WPP_RECORDER_SF_s
0x14008618c  cmp     [rdi], rdi
0x14008618f  jz      short loc_1400861AE
0x140086191  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "IsListEmpty(&DIoNicExt->ReadPacketQueue)")
0x140086196  cmp     [rdi], rdi
0x140086199  jz      short loc_1400861AE
0x14008619b  mov     edx, [r14+28h]; __annotation("Debug", "TelemetryAssert", "IsListEmpty(&DIoNicExt->ReadPacketQueue)", "ReadPacketQueue is expected to be empty")
0x14008619f  lea     r9, aReadpacketqueu; "ReadPacketQueue is expected to be empty"
0x1400861a6  xor     r8d, r8d
0x1400861a9  call    MicrosoftTelemetryAssertTriggeredArgsMsgKM
0x1400861ae  xor     r10d, r10d
0x1400861b1  mov     r15d, 1
0x1400861b7  mov     r13b, r15b
0x1400861ba  test    rsi, rsi
0x1400861bd  jz      loc_1400864FF
0x1400861c3  mov     rax, [rsi+0B8h]
0x1400861ca  mov     edi, 40000010h
0x1400861cf  mov     rcx, [rsi+8]; MemoryDescriptorList
0x1400861d3  mov     [rbp+170h+var_128], rax
0x1400861d7  mov     edx, [rax+8]
0x1400861da  test    byte ptr [rcx+0Ah], 5
0x1400861de  mov     [rbp+170h+var_16C], edx
0x1400861e1  mov     [rbp+170h+var_164], edx
0x1400861e4  jz      short loc_1400861EC
0x1400861e6  mov     r15, [rcx+18h]
0x1400861ea  jmp     short loc_140086212
0x1400861ec  mov     [rsp+1B0h+Priority], edi; Priority
0x1400861f0  xor     r9d, r9d; RequestedAddress
0x1400861f3  mov     r8d, r15d; CacheType
0x1400861f6  mov     [rsp+1B0h+BugCheckOnFailure], r10d; BugCheckOnFailure
0x1400861fb  xor     edx, edx; AccessMode
0x1400861fd  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140086204  nop     dword ptr [rax+rax+00h]
0x140086209  mov     edx, [rbp+170h+var_16C]
0x14008620c  xor     r10d, r10d
0x14008620f  mov     r15, rax
0x140086212  mov     [rbp+170h+var_130], r15
0x140086216  test    r15, r15
0x140086219  jnz     short loc_14008626F
0x14008621b  mov     rax, [rsi+8]
0x14008621f  lea     r9d, [r15+32h]
0x140086223  mov     rcx, cs:VmsIfrNicLog
0x14008622a  lea     r8d, [r15+14h]
0x14008622e  mov     [rsp+1B0h+var_180], edi
0x140086232  mov     dl, 2
0x140086234  mov     qword ptr [rsp+1B0h+Priority], rax
0x140086239  mov     qword ptr [rsp+1B0h+BugCheckOnFailure], r12
0x14008623e  call    WPP_RECORDER_SF_id
0x140086243  mov     edi, 0C000009Ah
0x140086248  mov     [rsp+1B0h+Priority], 0E0002027h
0x140086250  mov     [rsp+1B0h+BugCheckOnFailure], edi
0x140086254  mov     rcx, [r14]
0x140086257  xor     r9d, r9d
0x14008625a  mov     rdx, rbx
0x14008625d  lea     r8d, [r9+1]
0x140086261  call    VmsPktReportDroppedPacketEx
0x140086266  mov     r15d, [rbp+170h+var_16C]
0x14008626a  jmp     loc_1400864B1
0x14008626f  mov     r11, r10
0x140086272  mov     [rbp+170h+var_138], r11
0x140086276  test    edx, edx
0x140086278  jz      loc_14008647F
0x14008627e  test    r13b, r13b
0x140086281  jz      loc_140086364
0x140086287  test    rbx, rbx
0x14008628a  jz      loc_14008647F
0x140086290  xorps   xmm0, xmm0
0x140086293  mov     dil, 0Eh
0x140086296  mov     [rbp+170h+var_170], dil
0x14008629a  movups  [rbp+170h+var_158], xmm0
0x14008629e  movups  [rbp+170h+var_148], xmm0
0x1400862a2  cmp     [rbx+140h], r10w
0x1400862aa  jbe     short loc_1400862E0
0x1400862ac  lea     rax, [rbp+170h+var_148]
0x1400862b0  mov     rcx, rbx
0x1400862b3  lea     r9, [rbp+170h+var_170]
0x1400862b7  mov     qword ptr [rsp+1B0h+BugCheckOnFailure], rax
0x1400862bc  lea     r8, [rbp+170h+var_158+8]
0x1400862c0  call    NvLibRscGetLsoHint
0x1400862c5  xor     r10d, r10d
0x1400862c8  mov     edi, eax
0x1400862ca  test    eax, eax
0x1400862cc  js      loc_1400863DC
0x1400862d2  mov     dil, [rbp+170h+var_170]
0x1400862d6  lea     eax, [r10+1]
0x1400862da  or      word ptr [rbp+170h+var_158], ax
0x1400862de  jmp     short loc_1400862E5
0x1400862e0  mov     eax, 1
0x1400862e5  cmp     [rbp+170h+var_16F], r10b
0x1400862e9  jnz     short loc_140086307
0x1400862eb  lea     r8, [rbp+170h+var_158]
0x1400862ef  mov     rcx, rbx
0x1400862f2  lea     rdx, [rbp+170h+var_148+8]
0x1400862f6  call    VncGetTxChecksumOffloadInfo
0x1400862fb  xor     r10d, r10d
0x1400862fe  mov     dword ptr [rbp+170h+var_148+0Ch], 2
0x140086305  jmp     short loc_14008630A
0x140086307  mov     dword ptr [rbp+170h+var_148+0Ch], eax
0x14008630a  lea     rax, [rbp+170h+var_160]
0x14008630e  mov     r8b, dil
0x140086311  mov     qword ptr [rsp+1B0h+Priority], rax
0x140086316  lea     r9, [rbp+170h+var_158]
0x14008631a  mov     rdx, rbx
0x14008631d  mov     [rsp+1B0h+BugCheckOnFailure], r10d
0x140086322  lea     rcx, [rbp+170h+var_C0]
0x140086329  call    SegLibOffloadIteratorInitialize
0x14008632e  mov     edi, eax
0x140086330  test    eax, eax
0x140086332  js      loc_1400863ED
0x140086338  test    byte ptr [rbp+170h+var_160], 2
0x14008633c  jz      short loc_14008635D
0x14008633e  mov     al, byte ptr [rbp+170h+var_158]
0x140086341  mov     rcx, rbx
0x140086344  and     al, 1
0x140086346  neg     al
0x140086348  lea     rax, [rbp+170h+var_158+8]
0x14008634c  sbb     rdx, rdx
0x14008634f  xor     r9d, r9d
0x140086352  and     rdx, rax
0x140086355  xor     r8d, r8d
0x140086358  call    VmsNblHelperIncrementSuccessCsoStats
0x14008635d  mov     r11, [rbp+170h+var_138]
0x140086361  xor     r13b, r13b
0x140086364  lea     rcx, [rbp+170h+var_C0]
0x14008636b  call    SegLibOffloadIteratorPacketSize
  ... truncated ...
```
