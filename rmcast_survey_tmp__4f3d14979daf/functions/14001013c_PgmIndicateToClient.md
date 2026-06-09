# PgmIndicateToClient

- ea: `0x14001013c`
- end: `0x140010a73`
- name: `PgmIndicateToClient`
- size: `2359`
- prototype: `__int64 __fastcall(_QWORD *, __int64, ULONG, char *, int, unsigned int, ULONG *, KIRQL *, KIRQL *)`
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000f2d8`
- `0x14000fe74`

## callees

- `0x140005068`
- `0x1400052e4`
- `0x1400054d0`
- `0x1400074c8`
- `0x140007524`
- `0x140007f1c`
- `0x14000bef8`
- `0x14001013c`
- `0x14001511c`
- `0x14001528c`
- `0x1400156d0`
- `0x14001ce30`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140010447`
- `ntoskrnl!IofCompleteRequest` at `0x140010976`
- `ntoskrnl!IofCompleteRequest` at `0x140010447`
- `ntoskrnl!IofCompleteRequest` at `0x140010976`
- `ntoskrnl!KeGetCurrentIrql` at `0x140010515`
- `ntoskrnl!KeGetCurrentIrql` at `0x140010515`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400103d3`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400103f3`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400104e9`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010509`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400106e2`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010702`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001093b`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001095b`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400103d3`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400103f3`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400104e9`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010509`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400106e2`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010702`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001093b`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001095b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001045e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001047a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140010647`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140010660`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001068f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400106a8`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001072a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001073c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001098d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400109a6`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001045e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001047a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140010647`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140010660`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001068f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400106a8`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001072a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001073c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001098d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400109a6`
- `TDI!TdiCopyBufferToMdl` at `0x140010337`
- `TDI!TdiCopyBufferToMdl` at `0x1400107e6`
- `TDI!TdiCopyBufferToMdl` at `0x140010337`
- `TDI!TdiCopyBufferToMdl` at `0x1400107e6`

## pseudocode

```c
__int64 __fastcall PgmIndicateToClient(
        _QWORD *a1,
        __int64 a2,
        ULONG a3,
        char *a4,
        int a5,
        unsigned int a6,
        ULONG *a7,
        KIRQL *a8,
        KIRQL *a9)
{
  bool v9; // zf
  char *v10; // rsi
  unsigned int v12; // edi
  __int64 v13; // r8
  __int64 result; // rax
  __int64 v15; // r14
  int v16; // r9d
  ULONG v17; // r12d
  int v18; // ebx
  _QWORD *v19; // rcx
  _QWORD *v20; // rax
  __int64 v21; // rdx
  _QWORD *v22; // rcx
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rcx
  unsigned int v24; // ecx
  ULONG v25; // r8d
  unsigned int v26; // ecx
  PKSPIN_LOCK v27; // rdx
  KIRQL *v28; // rsi
  KIRQL v29; // al
  KIRQL v30; // al
  __int64 (__fastcall *v31)(__int64, __int64, _QWORD, _QWORD, int, ULONG *, char *, PIRP *); // rsi
  __int64 v32; // rbx
  __int64 v33; // rdi
  unsigned int v34; // eax
  __int64 v35; // r8
  unsigned int v36; // ebx
  __int64 v37; // rax
  ULONG v38; // r12d
  int v39; // esi
  KIRQL v40; // al
  KSPIN_LOCK *v41; // rcx
  KIRQL v42; // al
  KIRQL v43; // al
  KSPIN_LOCK *v44; // rcx
  KIRQL v45; // al
  KIRQL *v46; // rdi
  KIRQL *v47; // rbx
  KIRQL v48; // al
  KSPIN_LOCK *v49; // rcx
  ULONG v50; // r15d
  struct _IO_STACK_LOCATION *v51; // rbx
  ULONG Length; // r8d
  int v53; // edx
  ULONG v54; // ecx
  __int64 v55; // rcx
  KIRQL *v56; // rbx
  KSPIN_LOCK *v57; // rcx
  KIRQL v58; // al
  KSPIN_LOCK *v59; // rcx
  ULONG v60; // r15d
  ULONG v61; // r15d
  int v62; // [rsp+50h] [rbp-28h]
  unsigned int v63; // [rsp+58h] [rbp-20h]
  __int64 v64; // [rsp+58h] [rbp-20h]
  PIRP Irp; // [rsp+60h] [rbp-18h] BYREF
  PKSPIN_LOCK SpinLock; // [rsp+68h] [rbp-10h]
  ULONG BytesCopied; // [rsp+D0h] [rbp+58h] BYREF
  char *v70; // [rsp+D8h] [rbp+60h]

  v70 = a4;
  v9 = (*(_DWORD *)(a2 + 32) & 0x2100) == 0;
  v10 = a4;
  Irp = 0;
  BytesCopied = 0;
  if ( !v9 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 82, WPP_9481eaf791d131fecb736b68b85870ad_Traceguids, a2);
    v12 = -1073741285;
LABEL_11:
    result = v12;
    *a7 = 0;
    return result;
  }
  v13 = a6;
  if ( a6 > ConfiguredMaxPacketSize )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 83, WPP_9481eaf791d131fecb736b68b85870ad_Traceguids, a6);
    v12 = -1073741823;
    goto LABEL_11;
  }
  v15 = *(_QWORD *)(a2 + 48);
  v16 = a5;
  v17 = a3;
  v18 = a6 - a5;
  v62 = a6 - a5;
  *(_DWORD *)(v15 + 252) = a6;
  *(_DWORD *)(v15 + 256) = v16;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
    WPP_SF_ddddd(WPP_GLOBAL_Control->AttachedDevice, 84, v13, a3, v13, v16, v13, v16);
  if ( !a3 )
  {
LABEL_84:
    if ( !v18 )
      *(_QWORD *)(v15 + 252) = 0;
    v61 = a3 - v17;
    if ( v61 )
    {
      *a7 = v61;
      *(_QWORD *)(v15 + 112) = WPP_MAIN_CB.Dpc.SystemArgument1;
    }
    return 0;
  }
  while ( 1 )
  {
    Irp = *(PIRP *)(v15 + 232);
    if ( Irp )
      goto LABEL_21;
    v19 = *(_QWORD **)(v15 + 200);
    if ( v19 == (_QWORD *)(v15 + 200) )
      break;
    Irp = (PIRP)(v19 - 21);
    v20 = v19;
    v21 = *v19;
    if ( *(_QWORD **)(*v19 + 8LL) != v19 || (v22 = (_QWORD *)v19[1], (_QWORD *)*v22 != v20) )
      __fastfail(3u);
    *v22 = v21;
    *(_QWORD *)(v21 + 8) = v22;
    CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
    *(_QWORD *)(v15 + 232) = Irp;
    *(_QWORD *)(v15 + 240) = CurrentStackLocation->Parameters.Read.Length;
LABEL_21:
    v24 = *(_DWORD *)(v15 + 240) - *(_DWORD *)(v15 + 244);
    v25 = v17;
    BytesCopied = 0;
    if ( v17 > v24 )
      v25 = v24;
    TdiCopyBufferToMdl(v10, 0, v25, *(PMDL *)(*(_QWORD *)(v15 + 232) + 8LL), *(_DWORD *)(v15 + 244), &BytesCopied);
    *(_DWORD *)(v15 + 244) += BytesCopied;
    *(_DWORD *)(v15 + 256) += BytesCopied;
    v26 = *(_DWORD *)(v15 + 244);
    v18 -= BytesCopied;
    v17 -= BytesCopied;
    v62 = v18;
    SpinLock = (PKSPIN_LOCK)BytesCopied;
    v27 = (PKSPIN_LOCK)BytesCopied;
    if ( !BytesCopied || v26 >= *(_DWORD *)(v15 + 240) || !v18 )
    {
      v28 = a9;
      Irp = *(PIRP *)(v15 + 232);
      Irp->IoStatus.Information = *(unsigned int *)(v15 + 244);
      Irp->IoStatus.Status = v18 != 0 ? 0x80000005 : 0;
      *(_QWORD *)(v15 + 232) = 0;
      *(_QWORD *)(v15 + 240) = 0;
      KeReleaseSpinLock((PKSPIN_LOCK)(a2 + 360), *v28);
      KeReleaseSpinLock(a1 + 53, *a8);
      PgmCancelCancelRoutine((__int64)Irp);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
        WPP_SF_qDD(
          WPP_GLOBAL_Control->AttachedDevice,
          85,
          WPP_9481eaf791d131fecb736b68b85870ad_Traceguids,
          Irp,
          Irp->IoStatus.Information,
          v17);
      IofCompleteRequest(Irp, 2);
      v29 = KeAcquireSpinLockRaiseToDpc(a1 + 53);
      *a8 = v29;
      v30 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a2 + 360));
      v27 = SpinLock;
      *v28 = v30;
      v10 = v70;
    }
    if ( !v17 )
      goto LABEL_84;
    v10 = &v10[(_QWORD)v27];
    v70 = v10;
  }
  Irp = 0;
  BytesCopied = 0;
  v31 = (__int64 (__fastcall *)(__int64, __int64, _QWORD, _QWORD, int, ULONG *, char *, PIRP *))a1[16];
  v32 = *(_QWORD *)(a2 + 80);
  v33 = a1[17];
  SpinLock = (PKSPIN_LOCK)(a2 + 360);
  KeReleaseSpinLock((PKSPIN_LOCK)(a2 + 360), *a9);
  KeReleaseSpinLock(a1 + 53, *a8);
  v63 = KeGetCurrentIrql() != 0 ? 3104 : 1056;
  v34 = v31(v33, v32, v63, v17, v62, &BytesCopied, v70, &Irp);
  v36 = v34;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_DDdddq(WPP_GLOBAL_Control->AttachedDevice, Irp, v35, v34, v63, BytesCopied, v17, v62, Irp);
  v37 = BytesCopied;
  if ( BytesCopied > v17 )
  {
    v37 = v17;
    BytesCopied = v17;
  }
  v38 = v17 - v37;
  v64 = v37;
  v39 = v62 - v37;
  if ( v36 == -1073741802 && Irp && (int)PgmCheckSetCancelRoutine((__int64)Irp, (__int64)PgmCancelReceiveIrp, 0) < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
      WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 87, WPP_9481eaf791d131fecb736b68b85870ad_Traceguids, a2, Irp);
    PgmIoComplete(Irp, -1073741536, 0);
    v40 = KeAcquireSpinLockRaiseToDpc(a1 + 53);
    v41 = SpinLock;
    *a8 = v40;
    v42 = KeAcquireSpinLockRaiseToDpc(v41);
    *a9 = v42;
    *(_DWORD *)(v15 + 256) += BytesCopied;
    goto LABEL_51;
  }
  v43 = KeAcquireSpinLockRaiseToDpc(a1 + 53);
  v44 = SpinLock;
  *a8 = v43;
  v45 = KeAcquireSpinLockRaiseToDpc(v44);
  v46 = a9;
  *a9 = v45;
  *(_DWORD *)(v15 + 256) += BytesCopied;
  if ( *(_QWORD *)(v15 + 24) )
  {
    if ( v36 == -1073741802 )
    {
      v51 = Irp->Tail.Overlay.CurrentStackLocation;
      BytesCopied = 0;
      Length = v38;
      if ( v51->Parameters.Read.Length < v38 )
        Length = v51->Parameters.Read.Length;
      TdiCopyBufferToMdl(&v70[v64], 0, Length, Irp->MdlAddress, *(_DWORD *)(v15 + 244), &BytesCopied);
      v39 -= BytesCopied;
      v38 -= BytesCopied;
      *(_DWORD *)(v15 + 256) += BytesCopied;
      v53 = *(_DWORD *)(v15 + 256);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
      {
        WPP_SF_qDD(
          WPP_GLOBAL_Control->AttachedDevice,
          89,
          WPP_9481eaf791d131fecb736b68b85870ad_Traceguids,
          Irp,
          v51->Parameters.Read.Length,
          BytesCopied);
        v53 = *(_DWORD *)(v15 + 256);
      }
      if ( !BytesCopied || (v54 = v51->Parameters.Read.Length, BytesCopied >= v54) || *(_DWORD *)(v15 + 252) == v53 )
      {
        v56 = a9;
        Irp->IoStatus.Information = BytesCopied;
        Irp->IoStatus.Status = *(_DWORD *)(v15 + 256) != *(_DWORD *)(v15 + 252) ? 0x80000005 : 0;
        v57 = SpinLock;
        *(_QWORD *)(v15 + 240) = 0;
        KeReleaseSpinLock(v57, *v56);
        KeReleaseSpinLock(a1 + 53, *a8);
        PgmCancelCancelRoutine((__int64)Irp);
        IofCompleteRequest(Irp, 2);
        v58 = KeAcquireSpinLockRaiseToDpc(a1 + 53);
        v59 = SpinLock;
        *a8 = v58;
        *v56 = KeAcquireSpinLockRaiseToDpc(v59);
      }
      else
      {
        *(_DWORD *)(v15 + 240) = v54;
        *(_DWORD *)(v15 + 244) = BytesCopied;
        *(_QWORD *)(v15 + 232) = Irp;
      }
    }
    else
    {
      if ( v36 != -1073741285 )
        goto LABEL_65;
      if ( !*(_QWORD *)(v15 + 232) && *(_QWORD *)(v15 + 200) == v15 + 200 )
      {
        v55 = a2;
        *(_DWORD *)(a2 + 32) |= 0x800u;
        goto LABEL_66;
      }
    }
    v36 = 0;
LABEL_65:
    v55 = a2;
LABEL_66:
    if ( *(_DWORD *)(v15 + 252) == *(_DWORD *)(v15 + 256) )
      *(_QWORD *)(v15 + 252) = 0;
    if ( (int)(v36 + 0x80000000) < 0 || v36 == -1073741285 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
        WPP_SF_Dqdd(WPP_GLOBAL_Control->AttachedDevice, WPP_GLOBAL_Control, 0, v36, v55, BytesCopied, v39);
    }
    else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 91, WPP_9481eaf791d131fecb736b68b85870ad_Traceguids, v36);
    }
    v60 = a3 - v38;
    if ( v60 )
    {
      *a7 = v60;
      *(_QWORD *)(v15 + 112) = WPP_MAIN_CB.Dpc.SystemArgument1;
    }
    return v36;
  }
  if ( v36 == -1073741802 )
  {
    KeReleaseSpinLock(SpinLock, *v46);
    v47 = a8;
    KeReleaseSpinLock(a1 + 53, *a8);
    PgmIoComplete(Irp, -1073741536, 0);
    v48 = KeAcquireSpinLockRaiseToDpc(a1 + 53);
    v49 = SpinLock;
    *v47 = v48;
    *v46 = KeAcquireSpinLockRaiseToDpc(v49);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 88, WPP_9481eaf791d131fecb736b68b85870ad_Traceguids, a2);
LABEL_51:
  v50 = a3 - v38;
  if ( v50 )
  {
    *a7 = v50;
    *(_QWORD *)(v15 + 112) = WPP_MAIN_CB.Dpc.SystemArgument1;
  }
  return 3221225473LL;
}

```

## disassembly

```asm
0x14001013c  mov     [rsp-40h+arg_18], r9
0x140010141  mov     [rsp-40h+arg_8], rdx
0x140010146  mov     [rsp-40h+arg_0], rcx
0x14001014b  push    rbp
0x14001014c  push    rbx
0x14001014d  push    rsi
0x14001014e  push    rdi
0x14001014f  push    r12
0x140010151  push    r13
0x140010153  push    r14
0x140010155  push    r15
0x140010157  mov     rbp, rsp
0x14001015a  sub     rsp, 78h
0x14001015e  test    dword ptr [rdx+20h], 2100h
0x140010165  mov     rsi, r9
0x140010168  mov     r9, rdx
0x14001016b  mov     [rbp+Irp], 0
0x140010173  mov     r15d, r8d
0x140010176  mov     [rbp+arg_10], 0
0x14001017d  jz      short loc_1400101B5
0x14001017f  mov     rcx, cs:WPP_GLOBAL_Control
0x140010186  lea     r13, WPP_GLOBAL_Control
0x14001018d  cmp     rcx, r13
0x140010190  jz      short loc_1400101AE
0x140010192  mov     eax, [rcx+2Ch]
0x140010195  test    al, 2
0x140010197  jz      short loc_1400101AE
0x140010199  mov     rcx, [rcx+18h]
0x14001019d  lea     r8, WPP_9481eaf791d131fecb736b68b85870ad_Traceguids
0x1400101a4  mov     edx, 52h ; 'R'
0x1400101a9  call    WPP_SF_q
0x1400101ae  mov     edi, 0C000021Bh
0x1400101b3  jmp     short loc_1400101F9
0x1400101b5  mov     r8d, [rbp+arg_28]
0x1400101b9  cmp     r8d, cs:ConfiguredMaxPacketSize
0x1400101c0  jbe     short loc_14001020A
0x1400101c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400101c9  lea     r13, WPP_GLOBAL_Control
0x1400101d0  cmp     rcx, r13
0x1400101d3  jz      short loc_1400101F4
0x1400101d5  mov     eax, [rcx+2Ch]
0x1400101d8  test    al, 2
0x1400101da  jz      short loc_1400101F4
0x1400101dc  mov     rcx, [rcx+18h]
0x1400101e0  mov     r9d, r8d
0x1400101e3  lea     r8, WPP_9481eaf791d131fecb736b68b85870ad_Traceguids
0x1400101ea  mov     edx, 53h ; 'S'
0x1400101ef  call    WPP_SF_d
0x1400101f4  mov     edi, 0C0000001h
0x1400101f9  mov     rcx, [rbp+arg_30]
0x1400101fd  mov     eax, edi
0x1400101ff  mov     dword ptr [rcx], 0
0x140010205  jmp     loc_140010A61
0x14001020a  mov     r14, [rdx+30h]
0x14001020e  mov     ebx, r8d
0x140010211  mov     r9d, [rbp+arg_20]
0x140010215  mov     r12d, r15d
0x140010218  sub     ebx, r9d
0x14001021b  mov     [rbp+var_28], ebx
0x14001021e  mov     [r14+0FCh], r8d
0x140010225  mov     [r14+100h], r9d
0x14001022c  mov     rcx, cs:WPP_GLOBAL_Control
0x140010233  lea     r13, WPP_GLOBAL_Control
0x14001023a  cmp     rcx, r13
0x14001023d  jz      short loc_14001026B
0x14001023f  mov     eax, [rcx+2Ch]
0x140010242  test    al, 10h
0x140010244  jz      short loc_14001026B
0x140010246  mov     rcx, [rcx+18h]
0x14001024a  mov     edx, 54h ; 'T'
0x14001024f  mov     dword ptr [rsp+78h+var_40], r9d
0x140010254  mov     dword ptr [rsp+78h+var_48], r8d
0x140010259  mov     dword ptr [rsp+78h+BytesCopied], r9d
0x14001025e  mov     r9d, r15d
0x140010261  mov     [rsp+78h+DestinationOffset], r8d
0x140010266  call    WPP_SF_ddddd
0x14001026b  test    r15d, r15d
0x14001026e  jz      loc_140010A39
0x140010274  mov     rdi, [rbp+arg_8]
0x140010278  mov     rax, [r14+0E8h]
0x14001027f  mov     [rbp+Irp], rax
0x140010283  test    rax, rax
0x140010286  jnz     short loc_1400102F4
0x140010288  lea     rax, [r14+0C8h]
0x14001028f  mov     rcx, [rax]
0x140010292  cmp     rcx, rax
0x140010295  jz      loc_1400104AC
0x14001029b  lea     rax, [rcx-0A8h]
0x1400102a2  mov     [rbp+Irp], rax
0x1400102a6  add     rax, 0A8h
0x1400102ac  mov     rdx, [rax]
0x1400102af  cmp     [rdx+8], rax
0x1400102b3  jnz     loc_1400104A5
0x1400102b9  mov     rcx, [rax+8]
0x1400102bd  cmp     [rcx], rax
0x1400102c0  jnz     loc_1400104A5
0x1400102c6  mov     [rcx], rdx
0x1400102c9  mov     [rdx+8], rcx
0x1400102cd  mov     rax, [rbp+Irp]
0x1400102d1  mov     rcx, [rax+0B8h]
0x1400102d8  mov     [r14+0E8h], rax
0x1400102df  mov     eax, [rcx+8]
0x1400102e2  mov     [r14+0F0h], eax
0x1400102e9  mov     dword ptr [r14+0F4h], 0
0x1400102f4  mov     ecx, [r14+0F0h]
0x1400102fb  lea     rax, [rbp+arg_10]
0x1400102ff  sub     ecx, [r14+0F4h]
0x140010306  mov     r8d, r12d
0x140010309  mov     [rbp+arg_10], 0
0x140010310  cmp     r12d, ecx
0x140010313  mov     r9, [r14+0E8h]
0x14001031a  cmova   r8d, ecx; SourceBytesToCopy
0x14001031e  mov     [rsp+78h+BytesCopied], rax; BytesCopied
0x140010323  mov     eax, [r14+0F4h]
0x14001032a  xor     edx, edx; SourceOffset
0x14001032c  mov     rcx, rsi; SourceBuffer
0x14001032f  mov     [rsp+78h+DestinationOffset], eax; DestinationOffset
0x140010333  mov     r9, [r9+8]; DestinationMdlChain
0x140010337  call    cs:__imp_TdiCopyBufferToMdl
0x14001033e  nop     dword ptr [rax+rax+00h]
0x140010343  mov     eax, [rbp+arg_10]
0x140010346  add     [r14+0F4h], eax
0x14001034d  mov     eax, [rbp+arg_10]
0x140010350  add     [r14+100h], eax
0x140010357  mov     eax, [rbp+arg_10]
0x14001035a  mov     ecx, [r14+0F4h]
0x140010361  sub     ebx, eax
0x140010363  sub     r12d, eax
0x140010366  mov     [rbp+var_28], ebx
0x140010369  mov     [rbp+SpinLock], rax
0x14001036d  mov     edx, eax
0x14001036f  test    eax, eax
0x140010371  jz      short loc_140010384
0x140010373  cmp     ecx, [r14+0F0h]
0x14001037a  jnb     short loc_140010384
0x14001037c  test    ebx, ebx
0x14001037e  jnz     loc_140010490
0x140010384  mov     rcx, [r14+0E8h]
0x14001038b  mov     rsi, [rbp+arg_40]
0x140010392  mov     [rbp+Irp], rcx
0x140010396  mov     eax, [r14+0F4h]
0x14001039d  mov     [rcx+38h], rax
0x1400103a1  mov     eax, ebx
0x1400103a3  neg     eax
0x1400103a5  mov     rax, [rbp+Irp]
0x1400103a9  sbb     ecx, ecx
0x1400103ab  and     ecx, 80000005h
0x1400103b1  mov     [rax+30h], ecx
0x1400103b4  lea     rcx, [rdi+168h]; SpinLock
0x1400103bb  mov     qword ptr [r14+0E8h], 0
0x1400103c6  mov     qword ptr [r14+0F0h], 0
0x1400103d1  mov     dl, [rsi]; NewIrql
0x1400103d3  call    cs:__imp_KeReleaseSpinLock
0x1400103da  nop     dword ptr [rax+rax+00h]
0x1400103df  mov     rax, [rbp+arg_38]
0x1400103e6  mov     rcx, [rbp+arg_0]
0x1400103ea  add     rcx, 1A8h; SpinLock
0x1400103f1  mov     dl, [rax]; NewIrql
0x1400103f3  call    cs:__imp_KeReleaseSpinLock
0x1400103fa  nop     dword ptr [rax+rax+00h]
0x1400103ff  mov     rcx, [rbp+Irp]
0x140010403  call    PgmCancelCancelRoutine
0x140010408  mov     rcx, cs:WPP_GLOBAL_Control
0x14001040f  cmp     rcx, r13
0x140010412  jz      short loc_140010441
0x140010414  mov     eax, [rcx+2Ch]
0x140010417  test    al, 20h
0x140010419  jz      short loc_140010441
0x14001041b  mov     r9, [rbp+Irp]
0x14001041f  lea     r8, WPP_9481eaf791d131fecb736b68b85870ad_Traceguids
0x140010426  mov     rcx, [rcx+18h]
0x14001042a  mov     edx, 55h ; 'U'
0x14001042f  mov     dword ptr [rsp+78h+BytesCopied], r12d
0x140010434  mov     eax, [r9+38h]
0x140010438  mov     [rsp+78h+DestinationOffset], eax
0x14001043c  call    WPP_SF_qDD
0x140010441  mov     rcx, [rbp+Irp]; Irp
0x140010445  mov     dl, 2; PriorityBoost
0x140010447  call    cs:__imp_IofCompleteRequest
0x14001044e  nop     dword ptr [rax+rax+00h]
0x140010453  mov     rcx, [rbp+arg_0]
0x140010457  add     rcx, 1A8h; SpinLock
0x14001045e  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140010465  nop     dword ptr [rax+rax+00h]
0x14001046a  mov     rdx, [rbp+arg_38]
0x140010471  lea     rcx, [rdi+168h]; SpinLock
0x140010478  mov     [rdx], al
0x14001047a  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140010481  nop     dword ptr [rax+rax+00h]
0x140010486  mov     rdx, [rbp+SpinLock]
0x14001048a  mov     [rsi], al
0x14001048c  mov     rsi, [rbp+arg_18]
0x140010490  test    r12d, r12d
0x140010493  jz      loc_140010A39
0x140010499  add     rsi, rdx
0x14001049c  mov     [rbp+arg_18], rsi
0x1400104a0  jmp     loc_140010278
0x1400104a5  mov     ecx, 3
0x1400104aa  int     29h; Win8: RtlFailFast(ecx)
0x1400104ac  mov     rdx, [rbp+arg_0]
0x1400104b0  mov     rax, [rbp+arg_8]
0x1400104b4  mov     [rbp+Irp], 0
0x1400104bc  mov     [rbp+arg_10], 0
0x1400104c3  mov     rsi, [rdx+80h]
0x1400104ca  mov     rbx, [rax+50h]
0x1400104ce  lea     rcx, [rax+168h]; SpinLock
0x1400104d5  mov     rax, [rbp+arg_40]
0x1400104dc  mov     rdi, [rdx+88h]
0x1400104e3  mov     [rbp+SpinLock], rcx
0x1400104e7  mov     dl, [rax]; NewIrql
0x1400104e9  call    cs:__imp_KeReleaseSpinLock
0x1400104f0  nop     dword ptr [rax+rax+00h]
0x1400104f5  mov     rax, [rbp+arg_38]
0x1400104fc  mov     rcx, [rbp+arg_0]
0x140010500  add     rcx, 1A8h; SpinLock
0x140010507  mov     dl, [rax]; NewIrql
0x140010509  call    cs:__imp_KeReleaseSpinLock
0x140010510  nop     dword ptr [rax+rax+00h]
0x140010515  call    cs:__imp_KeGetCurrentIrql
0x14001051c  nop     dword ptr [rax+rax+00h]
0x140010521  mov     r9d, r12d
0x140010524  mov     rdx, rbx
0x140010527  neg     al
0x140010529  lea     rax, [rbp+Irp]
0x14001052d  mov     [rsp+78h+var_40], rax
0x140010532  sbb     ecx, ecx
0x140010534  mov     rax, [rbp+arg_18]
0x140010538  and     ecx, 800h
0x14001053e  mov     [rsp+78h+var_48], rax
0x140010543  add     ecx, 420h
0x140010549  lea     rax, [rbp+arg_10]
0x14001054d  mov     dword ptr [rbp+var_20], ecx
0x140010550  mov     [rsp+78h+BytesCopied], rax
0x140010555  mov     r8d, ecx
0x140010558  mov     eax, [rbp+var_28]
0x14001055b  mov     rcx, rdi
0x14001055e  mov     [rsp+78h+DestinationOffset], eax
0x140010562  mov     rax, rsi
0x140010565  call    _guard_dispatch_icall
0x14001056a  mov     ebx, eax
0x14001056c  mov     rcx, cs:WPP_GLOBAL_Control
0x140010573  mov     esi, [rbp+var_28]
0x140010576  cmp     rcx, r13
0x140010579  jz      short loc_1400105AF
0x14001057b  mov     edx, [rcx+2Ch]
0x14001057e  test    dl, 20h
0x140010581  jz      short loc_1400105AF
0x140010583  mov     eax, [rbp+arg_10]
0x140010586  mov     r9d, ebx
0x140010589  mov     rdx, [rbp+Irp]
0x14001058d  mov     rcx, [rcx+18h]
0x140010591  mov     [rsp+78h+var_38], rdx
0x140010596  mov     dword ptr [rsp+78h+var_40], esi
0x14001059a  mov     dword ptr [rsp+78h+var_48], r12d
0x14001059f  mov     dword ptr [rsp+78h+BytesCopied], eax
0x1400105a3  mov     eax, dword ptr [rbp+var_20]
0x1400105a6  mov     [rsp+78h+DestinationOffset], eax
0x1400105aa  call    WPP_SF_DDdddq
0x1400105af  mov     eax, [rbp+arg_10]
0x1400105b2  cmp     eax, r12d
0x1400105b5  jbe     short loc_1400105BD
0x1400105b7  mov     eax, r12d
0x1400105ba  mov     [rbp+arg_10], eax
0x1400105bd  sub     r12d, eax
0x1400105c0  mov     [rbp+var_20], rax
0x1400105c4  sub     esi, eax
0x1400105c6  cmp     ebx, 0C0000016h
0x1400105cc  jnz     loc_140010684
0x1400105d2  mov     rcx, [rbp+Irp]
0x1400105d6  test    rcx, rcx
0x1400105d9  jz      loc_140010684
0x1400105df  xor     r8d, r8d
0x1400105e2  lea     rdx, PgmCancelReceiveIrp
0x1400105e9  call    PgmCheckSetCancelRoutine
0x1400105ee  test    eax, eax
0x1400105f0  jns     loc_140010684
0x1400105f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400105fd  cmp     rcx, r13
0x140010600  jz      short loc_14001062B
0x140010602  mov     eax, [rcx+2Ch]
0x140010605  test    al, 2
0x140010607  jz      short loc_14001062B
0x140010609  mov     rax, [rbp+Irp]
0x14001060d  lea     r8, WPP_9481eaf791d131fecb736b68b85870ad_Traceguids
0x140010614  mov     r9, [rbp+arg_8]
0x140010618  mov     edx, 57h ; 'W'
0x14001061d  mov     rcx, [rcx+18h]
0x140010621  mov     qword ptr [rsp+78h+DestinationOffset], rax
0x140010626  call    WPP_SF_qq
0x14001062b  mov     rcx, [rbp+Irp]; Irp
0x14001062f  xor     r8d, r8d
0x140010632  mov     edx, 0C0000120h
0x140010637  call    PgmIoComplete
0x14001063c  mov     rcx, [rbp+arg_0]
0x140010640  add     rcx, 1A8h; SpinLock
0x140010647  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001064e  nop     dword ptr [rax+rax+00h]
0x140010653  mov     rdx, [rbp+arg_38]
0x14001065a  mov     rcx, [rbp+SpinLock]; SpinLock
0x14001065e  mov     [rdx], al
  ... truncated ...
```
