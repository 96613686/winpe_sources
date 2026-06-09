# SrvNetSendData

- ea: `0x1400010f0`
- end: `0x140001b0f`
- name: `SrvNetSendData`
- size: `2591`
- prototype: ``
- caller_count: `0`
- callee_count: `17`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1400010f0`
- `0x140001b18`
- `0x140001bcc`
- `0x140001c9c`
- `0x140001d70`
- `0x140002060`
- `0x1400022d0`
- `0x1400094e0`
- `0x140009af0`
- `0x140012d54`
- `0x140012dc8`
- `0x140012ed8`
- `0x14001389c`
- `0x14001cb80`
- `0x14002a3e0`
- `0x14002a4c0`
- `0x1400539b8`

## import_xrefs

- `ntoskrnl!IoAllocateIrp` at `0x140001905`
- `ntoskrnl!IoAllocateIrp` at `0x1400019c3`
- `ntoskrnl!IoAllocateIrp` at `0x140001905`
- `ntoskrnl!IoAllocateIrp` at `0x1400019c3`
- `ntoskrnl!IofCallDriver` at `0x1400018da`
- `ntoskrnl!IofCallDriver` at `0x1400018da`
- `ntoskrnl!IoReuseIrp` at `0x1400013c3`
- `ntoskrnl!IoReuseIrp` at `0x1400017ec`
- `ntoskrnl!IoReuseIrp` at `0x1400013c3`
- `ntoskrnl!IoReuseIrp` at `0x1400017ec`
- `ntoskrnl!EtwProviderEnabled` at `0x14000150b`
- `ntoskrnl!EtwProviderEnabled` at `0x14000155a`
- `ntoskrnl!EtwProviderEnabled` at `0x14000150b`
- `ntoskrnl!EtwProviderEnabled` at `0x14000155a`
- `ntoskrnl!IoGetActivityIdThread` at `0x140001599`
- `ntoskrnl!IoGetActivityIdThread` at `0x140001599`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140001a60`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140001a8f`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140001a60`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140001a8f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400019f6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400019f6`
- `TDI!TdiCopyMdlToBuffer` at `0x14000127e`
- `TDI!TdiCopyMdlToBuffer` at `0x14000127e`
- `ksecdd!BCryptEncrypt` at `0x14000135a`
- `ksecdd!BCryptEncrypt` at `0x14000135a`

## pseudocode

```c
NTSTATUS __fastcall SrvNetSendData(__int64 a1, unsigned int *a2)
{
  unsigned int *v2; // rbx
  __int64 v3; // rdi
  int v4; // eax
  __int64 v5; // rax
  int LockArray_high; // r12d
  __int64 v7; // rdx
  NTSTATUS v8; // r12d
  __int64 v9; // r13
  __int64 v10; // r11
  ULONG cbOutput; // r10d
  unsigned int v12; // r8d
  __int64 v13; // rax
  int v14; // edx
  int v15; // ecx
  signed __int64 v16; // r14
  void *v17; // rcx
  unsigned int v18; // eax
  IRP *v19; // rcx
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 v22; // r9
  __int64 v23; // rax
  __int64 v24; // rax
  __int64 v25; // rcx
  __int64 v26; // rax
  __int64 v28; // rsi
  unsigned __int16 v29; // ax
  ULONG v30; // r12d
  _DWORD *v31; // r13
  ULONG v32; // r15d
  ULONG v33; // r12d
  ULONG v34; // ebx
  unsigned __int64 v35; // rdx
  __int128 *v36; // rdi
  unsigned int v37; // r15d
  char *v38; // r13
  ULONG v39; // r12d
  __int128 v40; // xmm0
  __int128 v41; // xmm1
  __int64 v42; // r8
  int v43; // eax
  IRP *v44; // r15
  IRP *v45; // rcx
  __int64 v46; // rdx
  __int64 v47; // r8
  struct _IRP *MasterIrp; // rcx
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  struct _IO_STACK_LOCATION *v50; // rcx
  PIRP Irp; // rax
  int v52; // eax
  PIRP v53; // rax
  __int64 v54; // r13
  __int64 BufferFromPool; // r15
  __int16 v56; // ax
  unsigned __int64 v57; // rax
  __int64 v58; // r13
  ULONG *v59; // rcx
  PULONG BytesCopied; // [rsp+28h] [rbp-D8h]
  char v61; // [rsp+50h] [rbp-B0h]
  ULONG pcbResult; // [rsp+54h] [rbp-ACh] BYREF
  unsigned __int16 v63; // [rsp+58h] [rbp-A8h]
  ULONG v64; // [rsp+5Ch] [rbp-A4h] BYREF
  ULONG v65; // [rsp+60h] [rbp-A0h]
  __int64 v66; // [rsp+68h] [rbp-98h]
  __int128 *ActivityIdThread; // [rsp+70h] [rbp-90h]
  __int128 *v68; // [rsp+78h] [rbp-88h]
  unsigned int *v69; // [rsp+80h] [rbp-80h]
  __int64 v70; // [rsp+88h] [rbp-78h]
  __int128 pPaddingInfo; // [rsp+90h] [rbp-70h] BYREF
  __int128 v72; // [rsp+A0h] [rbp-60h]
  __int128 v73; // [rsp+B0h] [rbp-50h]
  __int128 v74; // [rsp+C0h] [rbp-40h]
  __int128 v75; // [rsp+D0h] [rbp-30h]
  __int64 v76; // [rsp+E0h] [rbp-20h]
  __int128 v77; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v78; // [rsp+100h] [rbp+0h]
  _DWORD v79[2]; // [rsp+108h] [rbp+8h] BYREF
  _BYTE v80[28]; // [rsp+110h] [rbp+10h]
  ULONG v81; // [rsp+12Ch] [rbp+2Ch]

  v77 = 0;
  v2 = a2;
  v69 = a2;
  v3 = a1;
  v70 = a1;
  if ( (WPP_MAIN_CB.Queue.Wcb.NumberOfChannels & 0x4000000) != 0 )
  {
    v28 = *((_QWORD *)a2 + 1);
    v29 = *(_WORD *)(a1 + 480);
    v30 = *a2;
    v66 = v28;
    v63 = v29;
    if ( EtwProviderEnabled(PROV_SRV2_Context, 0, 0x100000000uLL) )
    {
      v31 = (*(_BYTE *)(v28 + 10) & 5) != 0
          ? *(_DWORD **)(v28 + 24)
          : MmMapLockedPagesSpecifyCache((PMDL)v28, 0, MmCached, 0, 0, 0x40000000u);
      if ( v31 )
      {
        v68 = (__int128 *)(v3 + 128);
        v61 = 1;
        if ( EtwProviderEnabled(PROV_SRV2_Context, 0, 0x800000000000uLL) )
        {
          v32 = v30;
        }
        else
        {
          v32 = *(_DWORD *)(v28 + 40);
          if ( v32 >= 0x40 && *v31 == 1112364030 )
            v32 = v31[5] + 576;
          if ( v32 > v30 )
            v32 = v30;
        }
        v65 = v32;
        ActivityIdThread = (__int128 *)IoGetActivityIdThread();
        if ( !ActivityIdThread )
        {
          v77 = (unsigned __int64)_InterlockedIncrement64(&Correlation);
          ActivityIdThread = &v77;
        }
        pcbResult = v32;
        v33 = v32;
        if ( v32 )
        {
          v34 = v65;
          v35 = 0x140000000uLL;
          v36 = ActivityIdThread;
          while ( v28 )
          {
            v37 = v33;
            if ( *(_DWORD *)(v28 + 40) <= v33 )
              v37 = *(_DWORD *)(v28 + 40);
            if ( (*(_BYTE *)(v28 + 10) & 5) != 0 )
            {
              v38 = *(char **)(v28 + 24);
            }
            else
            {
              v38 = (char *)MmMapLockedPagesSpecifyCache((PMDL)v28, 0, MmCached, 0, 0, 0x40000000u);
              v35 = 0x140000000uLL;
            }
            if ( !v38 )
              break;
            if ( v61 && v33 == v37 && v37 < 0xF000 )
            {
              LODWORD(BytesCopied) = 28;
              a1 = (unsigned int)Template_qqbqb_ex(
                                   PROV_SRV2_Context,
                                   0x140000000uLL,
                                   0x100000000LL,
                                   v36,
                                   v63,
                                   BytesCopied,
                                   v68,
                                   v37,
                                   v38);
              goto LABEL_57;
            }
            a1 = 0;
            v39 = v37;
            if ( v61 )
            {
              v81 = v34;
              v79[1] = 28;
              v40 = *v68;
              v41 = *(__int128 *)((char *)v68 + 12);
              v79[0] = v63;
              *(_OWORD *)v80 = v40;
              *(_OWORD *)&v80[12] = v41;
              a1 = (unsigned int)Template_qqbjqb_ex(PROV_SRV2_Context, 0x140000000uLL, 0x140000000uLL, v36, 40, v79);
            }
            if ( v37 )
            {
              while ( 1 )
              {
                if ( (int)a1 < 0 )
                {
LABEL_72:
                  v28 = v66;
                  v34 = v65;
                  v36 = ActivityIdThread;
                  goto LABEL_73;
                }
                v42 = 0x100000000LL;
                if ( v39 < 0xF000 )
                  break;
                v43 = 61440;
                v64 = 61440;
                if ( v39 == 61440 )
                  goto LABEL_75;
LABEL_71:
                a1 = (unsigned int)Template_qqbjqb_ex(PROV_SRV2_Context, v35, v42, ActivityIdThread, v43, v38);
                v38 += v64;
                v39 -= v64;
                if ( !v39 )
                  goto LABEL_72;
              }
              v43 = v39;
              v64 = v39;
LABEL_75:
              if ( pcbResult == v37 )
                v42 = 0x180000000LL;
              goto LABEL_71;
            }
LABEL_73:
            v33 = pcbResult;
LABEL_57:
            if ( (int)a1 >= 0 )
            {
              v28 = *(_QWORD *)v28;
              v33 -= v37;
              pcbResult = v33;
              v35 = 0x140000000uLL;
              v66 = v28;
              v61 = 0;
              if ( v33 )
                continue;
            }
            break;
          }
          v2 = v69;
          v3 = v70;
        }
      }
    }
  }
  if ( *v2 <= 0x100 )
    *((_QWORD *)v2 + 8) = MEMORY[0xFFFFF78000000014];
  *((_QWORD *)v2 + 7) = v3;
  v4 = *(_DWORD *)(v3 + 480);
  if ( v4 == 1 )
  {
    if ( v2[23] )
      SrvNetCompressData(v3, v2);
    if ( !*((_QWORD *)v2 + 10) )
      goto LABEL_25;
    v5 = *v2 + 52;
    v64 = v5;
    LockArray_high = HIDWORD(KeGetPcr()[1].LockArray);
    pcbResult = 0;
    v7 = (unsigned int)v5;
    if ( SrvDisableNetBufferLookAsideList )
    {
      if ( (unsigned int)v5 < 0x100uLL )
      {
        v7 = 256;
LABEL_110:
        LOWORD(v54) = 0;
        pcbResult = 0;
        BufferFromPool = SrvNetAllocateBufferFromPool(a1, v7);
        v56 = 0;
LABEL_118:
        v59 = (ULONG *)(BufferFromPool + 36);
        v66 = BufferFromPool + 36;
        if ( BufferFromPool )
        {
          *(_WORD *)(BufferFromPool + 16) |= v56;
          *(_WORD *)(BufferFromPool + 18) = v54;
          *(_WORD *)(BufferFromPool + 20) = LockArray_high;
          *v59 = 0;
        }
        else
        {
          v66 = 36;
        }
        if ( !BufferFromPool )
          goto LABEL_11;
        v9 = *(_QWORD *)(BufferFromPool + 24);
        *v59 = v64;
        *(_DWORD *)v9 = 1112364029;
        *(_DWORD *)(v9 + 36) = *v2;
        *(_DWORD *)(v9 + 40) = 0x10000;
        *(_QWORD *)(v9 + 44) = *((_QWORD *)v2 + 9);
        v8 = TdiCopyMdlToBuffer(*((PMDL *)v2 + 1), 0, *(PVOID *)(BufferFromPool + 24), 0x34u, *v59, &v64);
        if ( (int)(v8 + 0x80000000) >= 0 && v8 != -2147483643 )
          goto LABEL_32;
        v10 = *((_QWORD *)v2 + 10);
        cbOutput = *v2;
        v76 = 0;
        pPaddingInfo = 0;
        v72 = 0;
        v73 = 0;
        v74 = 0;
        v75 = 0;
        v12 = HIDWORD(KeGetPcr()[1].LockArray);
        v13 = *(_QWORD *)(v10 + 8);
        v14 = *(_DWORD *)(v13 + 8);
        v15 = *(_DWORD *)(v13 + 12);
        *((_QWORD *)&v73 + 1) = v9 + 4;
        LODWORD(v72) = v14;
        *(_QWORD *)&pPaddingInfo = 0x100000058LL;
        *((_QWORD *)&v72 + 1) = v9 + 20;
        LODWORD(v73) = 32;
        LODWORD(v74) = v15;
        *((_QWORD *)&pPaddingInfo + 1) = v9 + 20;
        v16 = _InterlockedExchangeAdd64(
                (volatile signed __int64 *)SmbCryptoNonceCounter + 8 * (unsigned __int64)v12,
                1u);
        *(_QWORD *)(v9 + 28) = v12;
        *(_QWORD *)(v9 + 20) = v16 + 1;
        v17 = *(void **)v10;
        pcbResult = 0;
        v8 = BCryptEncrypt(
               v17,
               (PUCHAR)(v9 + 52),
               cbOutput,
               &pPaddingInfo,
               0,
               0,
               (PUCHAR)(v9 + 52),
               cbOutput,
               &pcbResult,
               0);
        if ( v8 < 0 )
        {
LABEL_32:
          SrvNetFreeBuffer((PVOID)BufferFromPool);
          goto LABEL_12;
        }
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_13dfc6c10cd0357b2fe0dd4f6ff3f414_Traceguids, *v2);
        }
        **(_QWORD **)(BufferFromPool + 56) = *((_QWORD *)v2 + 1);
        *((_QWORD *)v2 + 1) = *(_QWORD *)(BufferFromPool + 56);
        v18 = *(_DWORD *)v66;
        v2[12] |= 8u;
        *v2 = v18;
LABEL_25:
        v19 = (IRP *)*((_QWORD *)v2 + 5);
        if ( v19 )
        {
          v2[12] &= ~1u;
          IoReuseIrp(v19, 0);
          goto LABEL_27;
        }
        Irp = IoAllocateIrp(1, 0);
        *((_QWORD *)v2 + 5) = Irp;
        if ( Irp )
        {
          v2[12] |= 1u;
LABEL_27:
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            WPP_SF_qDqq(WPP_GLOBAL_Control->AttachedDevice, v20, v21, *((_QWORD *)v2 + 1), *v2, *((_QWORD *)v2 + 5), v3);
          }
          if ( *(_BYTE *)(v3 + 112) )
          {
            *(_BYTE *)(v3 + 112) = 0;
            return SrvNetWskResumeReceiveIndications(v3, *((_QWORD *)v2 + 5), v21, v2);
          }
          else
          {
            v22 = *((_QWORD *)v2 + 5);
            v78 = 0;
            v23 = *((_QWORD *)v2 + 1);
            v77 = 0;
            *(_QWORD *)(v23 + 24) -= 4LL;
            *(_DWORD *)(*((_QWORD *)v2 + 1) + 44LL) -= 4;
            *(_DWORD *)(*((_QWORD *)v2 + 1) + 40LL) += 4;
            **(_DWORD **)(*((_QWORD *)v2 + 1) + 24LL) = _byteswap_ulong(*v2);
            *(_QWORD *)(v22 + 112) = 0;
            *(_DWORD *)(v22 + 16) = 0;
            *(_QWORD *)(v22 + 192) = 0;
            *(_QWORD *)&v77 = *((_QWORD *)v2 + 1);
            v24 = *v2;
            DWORD2(v77) = 0;
            v78 = v24 + 4;
            v25 = **(_QWORD **)(v3 + 392);
            v26 = *(_QWORD *)(v22 + 184);
            *(_QWORD *)(v26 - 16) = SrvNetWskCompleteSendData;
            *(_QWORD *)(v26 - 8) = v2;
            *(_BYTE *)(v26 - 69) = -32;
            return (*(__int64 (__fastcall **)(_QWORD, __int128 *, __int64, _QWORD))(v25 + 48))(
                     *(_QWORD *)(v3 + 392),
                     &v77,
                     2,
                     *((_QWORD *)v2 + 5));
          }
        }
        return SrvNetCompleteSendData(3221225626LL, 0, v2);
      }
    }
    else if ( (unsigned int)v5 <= 0x100100uLL )
    {
      if ( (unsigned int)v5 > 0x1100uLL )
      {
        v57 = v5 - 256;
        _BitScanReverse64((unsigned __int64 *)&v58, v57);
        _BitScanForward64(&v57, v57);
        if ( (_DWORD)v58 == (_DWORD)v57 )
          v54 = (unsigned int)(v58 - 12);
        else
          v54 = (unsigned int)(v58 - 11);
      }
      else
      {
        v54 = 0;
      }
      BufferFromPool = PplAllocateFromLookasideListProcessor(
                         SrvNetBufferLookasides[v54],
                         (unsigned __int16)LockArray_high);
      v56 = 2;
      goto LABEL_118;
    }
    if ( (unsigned int)v5 > 0x1000100uLL )
    {
LABEL_11:
      v8 = -1073741670;
LABEL_12:
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        return SrvNetCompleteSendData((unsigned int)v8, 0, v2);
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) )
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          15,
          WPP_13dfc6c10cd0357b2fe0dd4f6ff3f414_Traceguids,
          (unsigned int)v8);
      if ( v8 < 0 )
        return SrvNetCompleteSendData((unsigned int)v8, 0, v2);
      goto LABEL_25;
    }
    goto LABEL_110;
  }
  if ( v4 )
  {
    if ( v4 == 2 )
    {
      if ( !*((_QWORD *)v2 + 10) )
        return SrvNetRdmaSendData(v3, v2);
      v52 = SrvNetEncryptData(v2);
      if ( v52 >= 0 )
        return SrvNetRdmaSendData(v3, v2);
    }
    else
    {
      if ( v4 != 4 )
        return SrvNetCompleteSendData(3221225659LL, 0, v2);
      if ( v2[23] )
        SrvNetCompressData(v3, v2);
      if ( !*((_QWORD *)v2 + 10) )
        return SrvNetQUICSendData(v3, v2);
      v52 = SrvNetEncryptData(v2);
      if ( v52 >= 0 )
        return SrvNetQUICSendData(v3, v2);
    }
    return SrvNetCompleteSendData((unsigned int)v52, 0, v2);
  }
  else
  {
    v44 = (IRP *)*((_QWORD *)v2 + 5);
    if ( v44 )
    {
      v45 = (IRP *)*((_QWORD *)v2 + 5);
      v2[12] = 0;
      IoReuseIrp(v45, 0);
    }
    else
    {
      v53 = IoAllocateIrp(*(_BYTE *)(*(_QWORD *)(v3 + 408) + 76LL), 0);
      v44 = v53;
      if ( !v53 )
        return SrvNetCompleteSendData(3221225626LL, 0, v2);
      v2[12] = 1;
      *((_QWORD *)v2 + 5) = v53;
    }
    MasterIrp = v44->AssociatedIrp.MasterIrp;
    if ( MasterIrp && (v44->Flags & 0x20) != 0 )
    {
      ExFreePoolWithTag(MasterIrp, 0);
      v44->Flags &= ~0x20u;
    }
    v44->Tail.Overlay.OriginalFileObject = *(PFILE_OBJECT *)(v3 + 400);
    v44->Tail.Overlay.Thread = KeGetCurrentThread();
    CurrentStackLocation = v44->Tail.Overlay.CurrentStackLocation;
    v44->RequestorMode = 0;
    v44->AssociatedIrp.MasterIrp = 0;
    v44->UserBuffer = 0;
    v44->Flags = 16;
    CurrentStackLocation[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)SrvNetTdiCompleteSendData;
    CurrentStackLocation[-1].Context = v2;
    CurrentStackLocation[-1].Control = -32;
    v50 = v44->Tail.Overlay.CurrentStackLocation;
    *(_WORD *)&v50[-1].MajorFunction = 1807;
    v50[-1].DeviceObject = *(PDEVICE_OBJECT *)(v3 + 408);
    v50[-1].FileObject = *(PFILE_OBJECT *)(v3 + 400);
    *(&v50[-1].Parameters.Read.Length + 1) = 0;
    v50[-1].Parameters.Read.Length = *v2;
    v44->MdlAddress = (PMDL)*((_QWORD *)v2 + 1);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qdqq(WPP_GLOBAL_Control->AttachedDevice, v46, v47, *((_QWORD *)v2 + 1), *v2, v44, v3);
    }
    return IofCallDriver(*(PDEVICE_OBJECT *)(v3 + 408), v44);
  }
}

```

## disassembly

```asm
0x1400010f0  mov     [rsp-8+arg_10], rbx
0x1400010f5  push    rbp
0x1400010f6  push    rsi
0x1400010f7  push    rdi
0x1400010f8  push    r12
0x1400010fa  push    r13
0x1400010fc  push    r14
0x1400010fe  push    r15
0x140001100  lea     rbp, [rsp-40h]
0x140001105  sub     rsp, 140h
0x14000110c  mov     rax, cs:__security_cookie
0x140001113  xor     rax, rsp
0x140001116  mov     [rbp+70h+var_40], rax
0x14000111a  test    byte ptr cs:WPP_MAIN_CB.Queue+13h, 4
0x140001121  xorps   xmm0, xmm0
0x140001124  movups  [rbp+70h+var_80], xmm0
0x140001128  mov     rbx, rdx
0x14000112b  mov     [rbp+70h+var_F0], rdx
0x14000112f  mov     rdi, rcx
0x140001132  mov     [rbp+70h+var_E8], rcx
0x140001136  mov     r14d, 1
0x14000113c  jnz     loc_1400014E0
0x140001142  cmp     dword ptr [rbx], 100h
0x140001148  ja      short loc_14000115B
0x14000114a  mov     rax, 0FFFFF78000000014h
0x140001154  mov     rax, [rax]
0x140001157  mov     [rbx+40h], rax
0x14000115b  mov     [rbx+38h], rdi
0x14000115f  mov     eax, [rdi+1E0h]
0x140001165  cmp     eax, 1
0x140001168  jnz     loc_1400016BC
0x14000116e  cmp     dword ptr [rbx+5Ch], 0
0x140001172  jnz     loc_1400014D0
0x140001178  cmp     qword ptr [rbx+50h], 0
0x14000117d  lea     rsi, WPP_GLOBAL_Control
0x140001184  mov     r15d, 2
0x14000118a  jz      loc_140001229
0x140001190  mov     eax, [rbx]
0x140001192  add     eax, 34h ; '4'
0x140001195  mov     [rsp+170h+var_114], eax
0x140001199  mov     r12d, gs:1A4h
0x1400011a2  cmp     cs:SrvDisableNetBufferLookAsideList, 0
0x1400011a9  mov     [rsp+170h+var_11C], 0
0x1400011b1  mov     [rsp+170h+var_11C], 0
0x1400011b9  mov     edx, eax
0x1400011bb  jnz     loc_140001ABE
0x1400011c1  cmp     rdx, 100100h
0x1400011c8  jbe     loc_140001AE8
0x1400011ce  cmp     rdx, 1000100h
0x1400011d5  jbe     loc_140001AD0
0x1400011db  mov     r12d, 0C000009Ah
0x1400011e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400011e8  cmp     rcx, rsi
0x1400011eb  jz      loc_140001AFD
0x1400011f1  test    dword ptr [rcx+2Ch], 100000h
0x1400011f8  jz      short loc_140001218
0x1400011fa  cmp     byte ptr [rcx+29h], 1
0x1400011fe  jb      short loc_140001218
0x140001200  mov     rcx, [rcx+18h]
0x140001204  lea     r8, WPP_13dfc6c10cd0357b2fe0dd4f6ff3f414_Traceguids
0x14000120b  mov     edx, 0Fh
0x140001210  mov     r9d, r12d
0x140001213  call    WPP_SF_d
0x140001218  test    r12d, r12d
0x14000121b  js      loc_140001AFD
0x140001221  xor     r14d, r14d
0x140001224  jmp     loc_1400013AA
0x140001229  xor     r14d, r14d
0x14000122c  jmp     loc_1400013B0
0x140001231  test    r15, r15
0x140001234  jz      short loc_1400011DB
0x140001236  mov     eax, [rsp+170h+var_114]
0x14000123a  mov     r9d, 34h ; '4'; DestinationOffset
0x140001240  mov     r13, [r15+18h]
0x140001244  xor     edx, edx; SourceOffset
0x140001246  mov     [rcx], eax
0x140001248  mov     dword ptr [r13+0], 424D53FDh
0x140001250  mov     eax, [rbx]
0x140001252  mov     [r13+24h], eax
0x140001256  mov     dword ptr [r13+28h], 10000h
0x14000125e  mov     rax, [rbx+48h]
0x140001262  mov     [r13+2Ch], rax
0x140001266  lea     rax, [rsp+170h+var_114]
0x14000126b  mov     r8, [r15+18h]; DestinationBuffer
0x14000126f  mov     [rsp+170h+BytesCopied], rax; BytesCopied
0x140001274  mov     eax, [rcx]
0x140001276  mov     rcx, [rbx+8]; SourceMdlChain
0x14000127a  mov     [rsp+170h+DestinationBufferSize], eax; DestinationBufferSize
0x14000127e  call    cs:__imp_TdiCopyMdlToBuffer
0x140001285  nop     dword ptr [rax+rax+00h]
0x14000128a  mov     r12d, eax
0x14000128d  mov     eax, 80000000h
0x140001292  lea     ecx, [r12+rax]
0x140001296  test    eax, ecx
0x140001298  jz      loc_1400014B6
0x14000129e  mov     r11, [rbx+50h]
0x1400012a2  lea     r9, [r13+14h]
0x1400012a6  mov     r10d, [rbx]
0x1400012a9  xor     eax, eax
0x1400012ab  mov     [rbp+70h+var_90], rax
0x1400012af  xorps   xmm0, xmm0
0x1400012b2  movups  [rbp+70h+pPaddingInfo], xmm0
0x1400012b6  movups  [rbp+70h+var_D0], xmm0
0x1400012ba  movups  [rbp+70h+var_C0], xmm0
0x1400012be  movups  [rbp+70h+var_B0], xmm0
0x1400012c2  movups  [rbp+70h+var_A0], xmm0
0x1400012c6  mov     r8d, gs:1A4h
0x1400012cf  mov     rax, [r11+8]
0x1400012d3  mov     edx, [rax+8]
0x1400012d6  mov     ecx, [rax+0Ch]
0x1400012d9  lea     rax, [r13+4]
0x1400012dd  mov     qword ptr [rbp+70h+var_C0+8], rax
0x1400012e1  mov     eax, r8d
0x1400012e4  shl     rax, 6
0x1400012e8  add     rax, cs:SmbCryptoNonceCounter
0x1400012ef  mov     dword ptr [rbp+70h+var_D0], edx
0x1400012f2  mov     dword ptr [rbp+70h+pPaddingInfo], 58h ; 'X'
0x1400012f9  mov     dword ptr [rbp+70h+pPaddingInfo+4], r14d
0x1400012fd  mov     qword ptr [rbp+70h+var_D0+8], r9
0x140001301  mov     dword ptr [rbp+70h+var_C0], 20h ; ' '
0x140001308  mov     dword ptr [rbp+70h+var_B0], ecx
0x14000130b  mov     qword ptr [rbp+70h+pPaddingInfo+8], r9
0x14000130f  mov     edx, r8d
0x140001312  lock xadd [rax], r14
0x140001317  mov     [r13+1Ch], rdx
0x14000131b  lea     rax, [rsp+170h+var_11C]
0x140001320  inc     r14
0x140001323  lea     rdx, [r13+34h]; pbInput
0x140001327  mov     [r9], r14
0x14000132a  mov     r8d, r10d; cbInput
0x14000132d  mov     rcx, [r11]; hKey
0x140001330  lea     r9, [rbp+70h+pPaddingInfo]; pPaddingInfo
0x140001334  xor     r14d, r14d
0x140001337  mov     [rsp+170h+dwFlags], r14d; dwFlags
0x14000133c  mov     [rsp+170h+pcbResult], rax; pcbResult
0x140001341  mov     [rsp+170h+cbOutput], r10d; cbOutput
0x140001346  mov     [rsp+170h+pbOutput], rdx; pbOutput
0x14000134b  mov     dword ptr [rsp+170h+BytesCopied], r14d; cbIV
0x140001350  mov     qword ptr [rsp+170h+DestinationBufferSize], r14; pbIV
0x140001355  mov     [rsp+170h+var_11C], r14d
0x14000135a  call    cs:__imp_BCryptEncrypt
0x140001361  nop     dword ptr [rax+rax+00h]
0x140001366  mov     r12d, eax
0x140001369  test    eax, eax
0x14000136b  js      loc_1400014C3
0x140001371  mov     rcx, cs:WPP_GLOBAL_Control
0x140001378  cmp     rcx, rsi
0x14000137b  jz      short loc_14000138A
0x14000137d  test    dword ptr [rcx+2Ch], 100000h
0x140001384  jnz     loc_140001932
0x14000138a  mov     rcx, [r15+38h]
0x14000138e  mov     rax, [rbx+8]
0x140001392  mov     [rcx], rax
0x140001395  mov     rax, [r15+38h]
0x140001399  mov     [rbx+8], rax
0x14000139d  mov     rax, [rsp+170h+var_108]
0x1400013a2  mov     eax, [rax]
0x1400013a4  or      dword ptr [rbx+30h], 8
0x1400013a8  mov     [rbx], eax
0x1400013aa  mov     r15d, 2
0x1400013b0  mov     rcx, [rbx+28h]; Irp
0x1400013b4  xor     edx, edx; ChargeQuota
0x1400013b6  test    rcx, rcx
0x1400013b9  jz      loc_140001903
0x1400013bf  and     dword ptr [rbx+30h], 0FFFFFFFEh
0x1400013c3  call    cs:__imp_IoReuseIrp
0x1400013ca  nop     dword ptr [rax+rax+00h]
0x1400013cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1400013d6  cmp     rcx, rsi
0x1400013d9  jz      short loc_1400013E8
0x1400013db  test    dword ptr [rcx+2Ch], 2000h
0x1400013e2  jnz     loc_140001A15
0x1400013e8  cmp     byte ptr [rdi+70h], 0
0x1400013ec  jnz     loc_1400018EB
0x1400013f2  mov     r9, [rbx+28h]
0x1400013f6  xor     eax, eax
0x1400013f8  mov     [rbp+70h+var_70], rax
0x1400013fc  xorps   xmm0, xmm0
0x1400013ff  mov     rax, [rbx+8]
0x140001403  mov     r8d, r15d
0x140001406  movups  [rbp+70h+var_80], xmm0
0x14000140a  add     qword ptr [rax+18h], 0FFFFFFFFFFFFFFFCh
0x14000140f  mov     rax, [rbx+8]
0x140001413  add     dword ptr [rax+2Ch], 0FFFFFFFCh
0x140001417  mov     rax, [rbx+8]
0x14000141b  add     dword ptr [rax+28h], 4
0x14000141f  mov     rax, [rbx+8]
0x140001423  mov     edx, [rbx]
0x140001425  bswap   edx
0x140001427  mov     rcx, [rax+18h]
0x14000142b  mov     [rcx], edx
0x14000142d  lea     rdx, SrvNetWskCompleteSendData
0x140001434  mov     [r9+70h], r14
0x140001438  mov     [r9+10h], r14d
0x14000143c  mov     [r9+0C0h], r14
0x140001443  mov     rax, [rbx+8]
0x140001447  mov     qword ptr [rbp+70h+var_80], rax
0x14000144b  mov     eax, [rbx]
0x14000144d  mov     dword ptr [rbp+70h+var_80+8], r14d
0x140001451  add     rax, 4
0x140001455  mov     [rbp+70h+var_70], rax
0x140001459  mov     rax, [rdi+188h]
0x140001460  mov     rcx, [rax]
0x140001463  mov     rax, [r9+0B8h]
0x14000146a  mov     [rax-10h], rdx
0x14000146e  lea     rdx, [rbp+70h+var_80]
0x140001472  mov     [rax-8], rbx
0x140001476  mov     byte ptr [rax-45h], 0E0h
0x14000147a  mov     rax, [rcx+30h]
0x14000147e  mov     rcx, [rdi+188h]
0x140001485  mov     r9, [rbx+28h]
0x140001489  call    _guard_dispatch_icall
0x14000148e  mov     rcx, [rbp+70h+var_40]
0x140001492  xor     rcx, rsp; StackCookie
0x140001495  call    __security_check_cookie
0x14000149a  mov     rbx, [rsp+170h+arg_10]
0x1400014a2  add     rsp, 140h
0x1400014a9  pop     r15
0x1400014ab  pop     r14
0x1400014ad  pop     r13
0x1400014af  pop     r12
0x1400014b1  pop     rdi
0x1400014b2  pop     rsi
0x1400014b3  pop     rbp
0x1400014b4  retn
0x1400014b6  cmp     r12d, 80000005h
0x1400014bd  jz      loc_14000129E
0x1400014c3  mov     rcx, r15; Entry
0x1400014c6  call    SrvNetFreeBuffer
0x1400014cb  jmp     loc_1400011E1
0x1400014d0  mov     rdx, rbx
0x1400014d3  mov     rcx, rdi
0x1400014d6  call    SrvNetCompressData
0x1400014db  jmp     loc_140001178
0x1400014e0  mov     rsi, [rdx+8]
0x1400014e4  mov     r8, 100000000h; Keyword
0x1400014ee  movzx   eax, word ptr [rcx+1E0h]
0x1400014f5  mov     r12d, [rdx]
0x1400014f8  xor     edx, edx; Level
0x1400014fa  mov     rcx, cs:PROV_SRV2_Context; RegHandle
0x140001501  mov     [rsp+170h+var_108], rsi
0x140001506  mov     [rsp+170h+var_118], ax
0x14000150b  call    cs:__imp_EtwProviderEnabled
0x140001512  nop     dword ptr [rax+rax+00h]
0x140001517  test    al, al
0x140001519  jz      loc_140001142
0x14000151f  test    byte ptr [rsi+0Ah], 5
0x140001523  jz      loc_140001A45
0x140001529  mov     r13, [rsi+18h]
0x14000152d  test    r13, r13
0x140001530  jz      loc_140001142
0x140001536  mov     rcx, cs:PROV_SRV2_Context; RegHandle
0x14000153d  lea     rax, [rdi+80h]
0x140001544  xor     edx, edx; Level
0x140001546  mov     [rsp+170h+var_F8], rax
0x14000154b  mov     r8, 800000000000h; Keyword
0x140001555  mov     [rsp+170h+var_120], r14b
0x14000155a  call    cs:__imp_EtwProviderEnabled
0x140001561  nop     dword ptr [rax+rax+00h]
0x140001566  test    al, al
0x140001568  jnz     loc_1400016EA
0x14000156e  mov     r15d, [rsi+28h]
0x140001572  cmp     r15d, 40h ; '@'
0x140001576  jb      short loc_14000158D
0x140001578  cmp     dword ptr [r13+0], 424D53FEh
0x140001580  jnz     short loc_14000158D
0x140001582  mov     r15d, [r13+14h]
0x140001586  add     r15d, 240h
0x14000158d  cmp     r15d, r12d
0x140001590  cmova   r15d, r12d
0x140001594  mov     [rsp+170h+var_110], r15d
0x140001599  call    cs:__imp_IoGetActivityIdThread
0x1400015a0  nop     dword ptr [rax+rax+00h]
0x1400015a5  mov     [rsp+170h+var_100], rax
0x1400015aa  test    rax, rax
0x1400015ad  jnz     short loc_1400015D2
0x1400015af  xorps   xmm0, xmm0
0x1400015b2  mov     rax, r14
0x1400015b5  movups  [rbp+70h+var_80], xmm0
0x1400015b9  lock xadd cs:Correlation, rax
0x1400015c2  inc     rax
0x1400015c5  mov     qword ptr [rbp+70h+var_80], rax
0x1400015c9  lea     rax, [rbp+70h+var_80]
0x1400015cd  mov     [rsp+170h+var_100], rax
0x1400015d2  mov     [rsp+170h+var_11C], r15d
0x1400015d7  mov     r12d, r15d
0x1400015da  test    r15d, r15d
0x1400015dd  jz      loc_140001142
0x1400015e3  mov     ebx, [rsp+170h+var_110]
0x1400015e7  mov     rdx, 140000000h
0x1400015f1  mov     rdi, [rsp+170h+var_100]
0x1400015f6  test    rsi, rsi
0x1400015f9  jz      loc_1400016AF
0x1400015ff  mov     eax, [rsi+28h]
0x140001602  mov     r15d, r12d
0x140001605  cmp     eax, r12d
0x140001608  cmovbe  r15d, eax
0x14000160c  test    byte ptr [rsi+0Ah], 5
0x140001610  jz      loc_140001A74
0x140001616  mov     r13, [rsi+18h]
  ... truncated ...
```
