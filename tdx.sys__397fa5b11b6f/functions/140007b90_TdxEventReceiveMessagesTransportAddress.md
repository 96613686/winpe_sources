# TdxEventReceiveMessagesTransportAddress

- ea: `0x140007b90`
- end: `0x140008616`
- name: `TdxEventReceiveMessagesTransportAddress`
- size: `2694`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `broker_com_uri`

## callees

- `0x140001980`
- `0x140002250`
- `0x140002850`
- `0x1400034c0`
- `0x1400054ec`
- `0x140007b90`
- `0x140008c50`
- `0x140012b8c`
- `0x140012cec`
- `0x140012ee4`
- `0x140018090`
- `0x1400184b0`
- `0x140018590`
- `0x140018600`
- `0x140018900`

## import_xrefs

- `ntoskrnl!KeLowerIrql` at `0x140007f2a`
- `ntoskrnl!KeLowerIrql` at `0x140007f2a`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140008100`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140008100`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140008205`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140008205`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x1400085db`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x1400085db`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x1400085ca`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x1400085ca`
- `ntoskrnl!IofCompleteRequest` at `0x140008235`
- `ntoskrnl!IofCompleteRequest` at `0x140008235`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140007cef`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140007cef`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140007c9f`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140007d89`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000804d`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000859e`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140007c9f`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140007d89`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000804d`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000859e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140007beb`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140007c05`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140007f63`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140007beb`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140007c05`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140007f63`
- `ntoskrnl!RtlGetCallersAddress` at `0x140007c53`
- `ntoskrnl!RtlGetCallersAddress` at `0x140007fae`
- `ntoskrnl!RtlGetCallersAddress` at `0x140007c53`
- `ntoskrnl!RtlGetCallersAddress` at `0x140007fae`
- `ntoskrnl!KeReleaseSpinLock` at `0x140007c77`
- `ntoskrnl!KeReleaseSpinLock` at `0x140007fd2`
- `ntoskrnl!KeReleaseSpinLock` at `0x140007c77`
- `ntoskrnl!KeReleaseSpinLock` at `0x140007fd2`
- `NETIO!RtlCopyMdlToKernelBuffer` at `0x140008149`
- `NETIO!RtlCopyMdlToKernelBuffer` at `0x140008149`
- `NETIO!RtlCopyMdlToMdl` at `0x1400082c2`
- `NETIO!RtlCopyMdlToMdl` at `0x14000841f`
- `NETIO!RtlCopyMdlToMdl` at `0x1400082c2`
- `NETIO!RtlCopyMdlToMdl` at `0x14000841f`

## pseudocode

```c
__int64 __fastcall TdxEventReceiveMessagesTransportAddress(_DWORD *a1, _QWORD *a2)
{
  int v2; // eax
  KSPIN_LOCK *v5; // r12
  KIRQL v6; // di
  int v7; // ecx
  _DWORD *v8; // rdx
  const char *v9; // r15
  PVOID v10; // r13
  __int64 *v11; // r14
  KSPIN_LOCK *v12; // rsi
  int v13; // r9d
  KSPIN_LOCK *v14; // rdi
  unsigned int (__fastcall *v15)(_QWORD, _QWORD, _OWORD *, __int64, __int64, _QWORD, _DWORD, int, unsigned int *, char *, KSPIN_LOCK **); // r13
  int v16; // edi
  __int16 *v17; // rdx
  KIRQL v18; // r8
  __int16 v19; // ax
  unsigned __int16 v20; // cx
  unsigned __int64 v21; // r9
  struct _MDL *v22; // r15
  unsigned __int64 i; // r13
  char *MappedSystemVa; // rax
  unsigned __int64 v25; // rdi
  char *v26; // r12
  bool v27; // cf
  int v28; // r15d
  __int64 v29; // rcx
  __int64 v30; // r9
  __int128 *v31; // rsi
  KIRQL v32; // al
  int v33; // ecx
  KIRQL v34; // di
  _DWORD *v35; // rdx
  _WORD *v37; // rax
  char v38; // al
  __int64 v39; // r9
  __int64 v40; // rax
  IRP *v41; // rcx
  __int64 v42; // rdi
  KSPIN_LOCK v43; // rdi
  __int64 v44; // r8
  _QWORD *v45; // rcx
  _QWORD *v46; // rax
  KSPIN_LOCK v47; // rdx
  KSPIN_LOCK **v48; // rcx
  ADDRESS_FAMILY *v49; // rcx
  __int64 v50; // r8
  __int64 v51; // rcx
  KSPIN_LOCK v52; // rdi
  __int64 v53; // r8
  int v54; // eax
  __int64 v55; // r8
  __int64 v56; // rcx
  __int64 v57; // rdx
  _QWORD *v58; // rcx
  _QWORD *v59; // rax
  KSPIN_LOCK *v60; // r13
  __int64 v61; // rdx
  int v62; // r8d
  __int64 ByteCount; // rax
  ADDRESS_FAMILY *v64; // rcx
  UCHAR v65; // al
  __int64 v66; // r8
  char v67; // r9
  int v68; // eax
  __int64 v69; // r8
  __int64 v70; // rcx
  ULONG BugCheckOnFailure[2]; // [rsp+20h] [rbp-E0h]
  ULONG Priority[2]; // [rsp+28h] [rbp-D8h]
  int v73; // [rsp+38h] [rbp-C8h]
  unsigned int *v74; // [rsp+40h] [rbp-C0h]
  char *v75; // [rsp+48h] [rbp-B8h]
  KSPIN_LOCK **v76; // [rsp+50h] [rbp-B0h]
  KIRQL Irql[4]; // [rsp+60h] [rbp-A0h] BYREF
  int v78; // [rsp+64h] [rbp-9Ch]
  KIRQL v79; // [rsp+68h] [rbp-98h]
  KSPIN_LOCK *v80; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v81; // [rsp+78h] [rbp-88h] BYREF
  __int128 v82; // [rsp+80h] [rbp-80h] BYREF
  __int128 v83; // [rsp+90h] [rbp-70h] BYREF
  KSPIN_LOCK v84; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int64 v85; // [rsp+A8h] [rbp-58h]
  KSPIN_LOCK v86; // [rsp+B0h] [rbp-50h] BYREF
  PVOID CallersAddress; // [rsp+B8h] [rbp-48h] BYREF
  __int128 v88; // [rsp+C0h] [rbp-40h]
  PVOID v89; // [rsp+D0h] [rbp-30h] BYREF
  unsigned int v90; // [rsp+D8h] [rbp-28h]
  __int128 v91; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v92; // [rsp+F0h] [rbp-10h] BYREF
  _OWORD v93[8]; // [rsp+100h] [rbp+0h] BYREF
  __int64 v94; // [rsp+180h] [rbp+80h]

  v2 = *(_DWORD *)a2;
  v89 = a2;
  v84 = 0;
  v80 = 0;
  v82 = 0;
  if ( (v2 & 8) == 0 )
  {
    v5 = (KSPIN_LOCK *)(a1 + 138);
    v79 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)a1 + 1);
    v6 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)a1 + 69);
    v7 = a1[4] + 1;
    v8 = &a1[8 * a1[204]];
    CallersAddress = 0;
    v9 = "minio\\netio\\session\\tdi\\address.c";
    v8[146] = v7;
    *((_QWORD *)v8 + 70) = "minio\\netio\\session\\tdi\\address.c";
    v8[142] = 1517;
    RtlGetCallersAddress(&CallersAddress, (PVOID *)v8 + 72);
    a1[204] = ((unsigned __int8)a1[204] + 1) & 7;
    KeReleaseSpinLock((PKSPIN_LOCK)a1 + 69, v6);
    _InterlockedIncrement(a1 + 4);
    v10 = (PVOID)*((_QWORD *)a1 + 63);
    CallersAddress = v10;
    if ( v10 )
      DbgTdxReferenceTransportAddress(v10, "minio\\netio\\session\\tdi\\address.c", 1520);
    KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)a1 + 1);
    v11 = (__int64 *)a2[1];
    LOBYTE(v9) = 0;
    *((_QWORD *)&v82 + 1) = &v82;
    v78 = (int)v9;
    *(_QWORD *)&v82 = &v82;
    if ( v11 )
    {
      while ( 1 )
      {
        if ( (*a1 & 0x20) != 0
          && (v37 = (_WORD *)v11[6], *v37 == 23)
          && (v37[4] || v37[5] || v37[6] || v37[7] || v37[8] || v37[9] != 0xFFFF ? (v38 = 0) : (v38 = 1), v38) )
        {
          v12 = (KSPIN_LOCK *)v10;
        }
        else
        {
          v12 = (KSPIN_LOCK *)a1;
        }
        if ( !v12 )
          goto LABEL_33;
        KeAcquireSpinLockAtDpcLevel(v12 + 1);
        if ( (*(_DWORD *)v12 & 4) == 0 )
          goto LABEL_46;
        v14 = (KSPIN_LOCK *)v12[42];
        do
        {
          if ( v14 == v12 + 42 )
          {
            if ( !v14 )
            {
              LOBYTE(v9) = v78;
              goto LABEL_46;
            }
            v15 = (unsigned int (__fastcall *)(_QWORD, _QWORD, _OWORD *, __int64, __int64, _QWORD, _DWORD, int, unsigned int *, char *, KSPIN_LOCK **))v12[44];
            *(_QWORD *)&v83 = v15;
            if ( !v15 )
            {
              KeReleaseSpinLockFromDpcLevel(v12 + 1);
              LOBYTE(v9) = v78;
              goto LABEL_33;
            }
            v16 = *(_DWORD *)v12;
            *(_QWORD *)&v88 = v12[45];
            v81 = 0;
            v86 = 0;
            v94 = 0;
            Irql[0] = (v16 & 0x40) != 0;
            memset(v93, 0, sizeof(v93));
            KeReleaseSpinLockFromDpcLevel(v12 + 1);
            v17 = (__int16 *)v11[6];
            v18 = Irql[0];
            if ( (v16 & 0x40) != 0 && !(unsigned __int8)INETADDR_ISV4MAPPED(v11[6]) )
              v18 = 0;
            v19 = *v17;
            if ( *v17 == 35 )
            {
LABEL_15:
              v20 = 14;
              goto LABEL_16;
            }
            if ( v19 == 23 )
            {
              v20 = 14;
              if ( !v18 )
                v20 = 26;
LABEL_16:
              LODWORD(v93[0]) = 1;
              v90 = v20 + 8;
              WORD2(v93[0]) = v20;
              if ( v18 )
              {
                WORD3(v93[0]) = 2;
                WORD4(v93[0]) = v17[1];
                v40 = 10;
                if ( *v17 != 23 )
                  v40 = 8;
                *(_DWORD *)((char *)v93 + 10) = *(_DWORD *)&v17[v40];
                *(_QWORD *)((char *)v93 + 14) = 0;
              }
              else
              {
                WORD3(v93[0]) = *v17;
                memmove((char *)v93 + 8, v17 + 1, v20);
              }
            }
            else
            {
              if ( v19 == 2 )
                goto LABEL_15;
              v90 = 0;
            }
            v21 = v11[3];
            v85 = v21;
            if ( v21 )
            {
              v22 = (struct _MDL *)v11[1];
              for ( i = *((unsigned int *)v11 + 4); i >= v22->ByteCount; i -= ByteCount )
              {
                ByteCount = v22->ByteCount;
                v22 = v22->Next;
              }
              if ( (v22->MdlFlags & 5) != 0 )
              {
                MappedSystemVa = (char *)v22->MappedSystemVa;
              }
              else
              {
                MappedSystemVa = (char *)MmMapLockedPagesSpecifyCache(v22, 0, MmCached, 0, 0, 0x40000000u);
                v21 = v85;
              }
              if ( MappedSystemVa )
              {
                v25 = v22->ByteCount - i;
                if ( v21 < v25 )
                  v25 = v21;
                v26 = &MappedSystemVa[i];
                if ( v25 && v21 > v25 && v25 < 0x100 )
                {
                  v26 = (char *)TdxMessageIndicationBuffer + 256 * (unsigned __int64)KeGetCurrentProcessorNumberEx(0);
                  memset(v26, 0, 0x100u);
                  v39 = v85;
                  *(_QWORD *)BugCheckOnFailure = &v86;
                  if ( v85 > 0x100 )
                    v39 = 256;
                  RtlCopyMdlToKernelBuffer(v22, i, v26, v39, *(_QWORD *)BugCheckOnFailure);
                  LODWORD(v21) = v85;
                  LODWORD(v25) = v86;
                }
                v15 = (unsigned int (__fastcall *)(_QWORD, _QWORD, _OWORD *, __int64, __int64, _QWORD, _DWORD, int, unsigned int *, char *, KSPIN_LOCK **))v83;
                goto LABEL_27;
              }
            }
            else
            {
              v26 = 0;
              LODWORD(v25) = 0;
LABEL_27:
              v27 = *((_DWORD *)v11 + 10) != 0;
              v81 = 0;
              v28 = v27 ? 0x1000 : 0;
              if ( (*(_DWORD *)v89 & 1) != 0 )
              {
                v28 |= 4u;
              }
              else if ( (*(_DWORD *)v89 & 2) != 0 )
              {
                v28 |= 8u;
              }
              v80 = 0;
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
              {
                v64 = (ADDRESS_FAMILY *)v11[6];
                v83 = (unsigned __int64)v64;
                v65 = SOCKADDR_SIZE(*v64);
                WORD4(v83) = v65;
                v92 = v83;
                WPP_SF_q_SOCKADDR_d(*(_QWORD *)(v66 + 24), v65, v66, (_DWORD)v12, (__int64)&v92, v67);
                LODWORD(v21) = v85;
              }
              v29 = v11[4];
              v76 = &v80;
              v75 = v26;
              v74 = &v81;
              v73 = v21;
              v30 = *((unsigned int *)v11 + 10);
              Priority[0] = v28;
              if ( v15(v88, v90, v93, v30, v29, *(_QWORD *)Priority, v25, v73, &v81, v26, &v80) == -1073741802 )
              {
                DbgTdxReferenceTransportAddress(v12, "minio\\netio\\session\\tdi\\address.c", 1814);
                *(_QWORD *)Priority = &v84;
                v43 = v80[23];
                RtlCopyMdlToMdl(v11[1], v81 + *((_DWORD *)v11 + 4), v80[1], 0, v11[3] - v81, &v84);
                v44 = *(_QWORD *)(v43 + 24);
                if ( v44 )
                {
                  v68 = *(_DWORD *)(v44 + 32);
                  v69 = *(_QWORD *)(v44 + 40);
                  v70 = v11[6];
                  LODWORD(v83) = v68;
                  *(_DWORD *)(*(_QWORD *)(v43 + 24) + 32LL) = SockAddrToTaList(v70, Irql[0], v69, &v83);
                }
                *((_DWORD *)v80 + 12) = 0;
                v80[7] = v84;
                v80[15] = (KSPIN_LOCK)v12;
                v45 = (_QWORD *)*((_QWORD *)&v82 + 1);
                if ( **((__int128 ***)&v82 + 1) != &v82 )
LABEL_108:
                  __fastfail(3u);
                v46 = v80 + 21;
                v80[21] = (KSPIN_LOCK)&v82;
                v46[1] = v45;
                *v45 = v46;
                *((_QWORD *)&v82 + 1) = v46;
              }
            }
            LOBYTE(v9) = v78;
            goto LABEL_33;
          }
          v60 = v14 - 21;
          v80 = v14 - 21;
          v86 = v14[2];
          v61 = *(_QWORD *)(v86 + 16);
          if ( !v61 )
            break;
          v62 = *(_DWORD *)(v61 + 32);
          if ( !v62 )
            break;
          v14 = (KSPIN_LOCK *)*v14;
        }
        while ( !(unsigned __int8)SockAddrEqualsTaList(
                                    v11[6],
                                    *(_QWORD *)(v61 + 40),
                                    v62,
                                    v13,
                                    (*(_DWORD *)v12 & 0x40) != 0) );
        v47 = v60[21];
        if ( *(KSPIN_LOCK **)(v47 + 8) != v60 + 21 )
          goto LABEL_108;
        v48 = (KSPIN_LOCK **)v60[22];
        if ( *v48 != v60 + 21 )
          goto LABEL_108;
        LOBYTE(v9) = v78;
        *v48 = (KSPIN_LOCK *)v47;
        *(_QWORD *)(v47 + 8) = v48;
        LODWORD(v9) = (unsigned __int8)v9;
        if ( !_InterlockedExchange64((volatile __int64 *)v80 + 13, 0) )
          LODWORD(v9) = 1;
        v78 = (int)v9;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
        {
          v49 = (ADDRESS_FAMILY *)v11[6];
          v88 = (unsigned __int64)v49;
          WORD4(v88) = SOCKADDR_SIZE(*v49);
          v91 = v88;
          WPP_SF_qq_SOCKADDR_(*(_QWORD *)(v50 + 24), 25, v50, (_DWORD)v12, (_DWORD)v80, (__int64)&v91);
        }
        v84 = 0;
        v51 = v11[1];
        if ( v51 )
          RtlCopyMdlToMdl(v51, *((unsigned int *)v11 + 4), v80[1], 0, v11[3], &v84);
        v52 = v86;
        v53 = *(_QWORD *)(v86 + 24);
        if ( v53 )
        {
          v54 = *(_DWORD *)(v53 + 32);
          v55 = *(_QWORD *)(v53 + 40);
          v56 = v11[6];
          v57 = *(_DWORD *)v12 >> 6;
          LOBYTE(v57) = (*(_DWORD *)v12 & 0x40) != 0;
          LODWORD(v83) = v54;
          *(_DWORD *)(*(_QWORD *)(v52 + 24) + 32LL) = SockAddrToTaList(v56, v57, v55, &v83);
        }
        v80[7] = v84;
        v80[15] = (KSPIN_LOCK)v12;
        v58 = (_QWORD *)*((_QWORD *)&v82 + 1);
        if ( **((__int128 ***)&v82 + 1) != &v82 )
          goto LABEL_108;
        v59 = v80 + 21;
        v80[21] = (KSPIN_LOCK)&v82;
        v59[1] = v58;
        *v58 = v59;
        *((_QWORD *)&v82 + 1) = v59;
LABEL_46:
        KeReleaseSpinLockFromDpcLevel(v12 + 1);
LABEL_33:
        v11 = (__int64 *)*v11;
        v10 = CallersAddress;
        if ( !v11 )
        {
          v5 = (KSPIN_LOCK *)(a1 + 138);
          break;
        }
      }
    }
    KeLowerIrql(v79);
    if ( (_BYTE)v9 )
    {
      Irql[0] = 0;
      IoAcquireCancelSpinLock(Irql);
      IoReleaseCancelSpinLock(Irql[0]);
    }
    v31 = (__int128 *)v82;
    while ( v31 != &v82 )
    {
      v41 = (IRP *)((char *)v31 - 168);
      v80 = (KSPIN_LOCK *)v31 - 21;
      v42 = *((_QWORD *)v31 - 6);
      v31 = *(__int128 **)v31;
      IofCompleteRequest(v41, 2);
      DbgTdxDereferenceTransportAddress(v42, "minio\\netio\\session\\tdi\\address.c", 1888);
    }
    if ( v10 )
      DbgTdxDereferenceTransportAddress(v10, "minio\\netio\\session\\tdi\\address.c", 1896);
    v32 = KeAcquireSpinLockRaiseToDpc(v5);
    v33 = a1[4];
    v34 = v32;
    v35 = &a1[8 * a1[204]];
    v89 = 0;
    v35[146] = v33 - 1;
    *((_QWORD *)v35 + 70) = "minio\\netio\\session\\tdi\\address.c";
    v35[142] = 1898;
    RtlGetCallersAddress(&v89, (PVOID *)v35 + 72);
    a1[204] = ((unsigned __int8)a1[204] + 1) & 7;
    KeReleaseSpinLock(v5, v34);
    if ( _InterlockedExchangeAdd(a1 + 4, 0xFFFFFFFF) == 1 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_63c55c6b4ff2326ef703f60977e9aaef_Traceguids, a1);
      }
      TdxCleanupObjectHeader(a1);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140007b90  mov     [rsp-8+arg_10], rbx
0x140007b95  push    rbp
0x140007b96  push    rsi
0x140007b97  push    rdi
0x140007b98  push    r12
0x140007b9a  push    r13
0x140007b9c  push    r14
0x140007b9e  push    r15
0x140007ba0  lea     rbp, [rsp-0A0h]
0x140007ba8  sub     rsp, 1A0h
0x140007baf  mov     rax, cs:__security_cookie
0x140007bb6  xor     rax, rsp
0x140007bb9  mov     [rbp+0D0h+var_40], rax
0x140007bc0  mov     eax, [rdx]
0x140007bc2  xor     r15d, r15d
0x140007bc5  mov     [rbp+0D0h+var_100], rdx
0x140007bc9  xorps   xmm0, xmm0
0x140007bcc  mov     [rbp+0D0h+var_130], r15
0x140007bd0  mov     r14, rdx
0x140007bd3  mov     [rsp+1D0h+var_160], r15
0x140007bd8  mov     rbx, rcx
0x140007bdb  movups  [rbp+0D0h+var_150], xmm0
0x140007bdf  test    al, 8
0x140007be1  jnz     loc_140008012
0x140007be7  add     rcx, 8; SpinLock
0x140007beb  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140007bf2  nop     dword ptr [rax+rax+00h]
0x140007bf7  lea     r12, [rbx+228h]
0x140007bfe  mov     [rsp+1D0h+var_168], al
0x140007c02  mov     rcx, r12; SpinLock
0x140007c05  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140007c0c  nop     dword ptr [rax+rax+00h]
0x140007c11  mov     ecx, [rbx+10h]
0x140007c14  movzx   edi, al
0x140007c17  mov     edx, [rbx+330h]
0x140007c1d  inc     ecx
0x140007c1f  shl     rdx, 5
0x140007c23  add     rdx, rbx
0x140007c26  mov     [rbp+0D0h+CallersAddress], r15
0x140007c2a  lea     r15, aMinioNetioSess_2; "minio\\netio\\session\\tdi\\address.c"
0x140007c31  mov     [rdx+248h], ecx
0x140007c37  lea     rcx, [rbp+0D0h+CallersAddress]; CallersAddress
0x140007c3b  mov     [rdx+230h], r15
0x140007c42  mov     dword ptr [rdx+238h], 5EDh
0x140007c4c  add     rdx, 240h; CallersCaller
0x140007c53  call    cs:__imp_RtlGetCallersAddress
0x140007c5a  nop     dword ptr [rax+rax+00h]
0x140007c5f  mov     eax, [rbx+330h]
0x140007c65  movzx   edx, dil; NewIrql
0x140007c69  inc     eax
0x140007c6b  mov     rcx, r12; SpinLock
0x140007c6e  and     eax, 7
0x140007c71  mov     [rbx+330h], eax
0x140007c77  call    cs:__imp_KeReleaseSpinLock
0x140007c7e  nop     dword ptr [rax+rax+00h]
0x140007c83  lock inc dword ptr [rbx+10h]
0x140007c87  mov     r13, [rbx+1F8h]
0x140007c8e  mov     [rbp+0D0h+CallersAddress], r13
0x140007c92  test    r13, r13
0x140007c95  jnz     loc_140008261
0x140007c9b  lea     rcx, [rbx+8]; SpinLock
0x140007c9f  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140007ca6  nop     dword ptr [rax+rax+00h]
0x140007cab  mov     r14, [r14+8]
0x140007caf  lea     rax, [rbp+0D0h+var_150]
0x140007cb3  xor     r15b, r15b
0x140007cb6  mov     qword ptr [rbp+0D0h+var_150+8], rax
0x140007cba  mov     [rsp+1D0h+var_16C], r15d
0x140007cbf  lea     rax, [rbp+0D0h+var_150]
0x140007cc3  mov     qword ptr [rbp+0D0h+var_150], rax
0x140007cc7  test    r14, r14
0x140007cca  jz      loc_140007F25
0x140007cd0  mov     ecx, 0FFFFh
0x140007cd5  mov     eax, [rbx]
0x140007cd7  test    al, 20h
0x140007cd9  jnz     loc_1400080A1
0x140007cdf  mov     rsi, rbx
0x140007ce2  test    rsi, rsi
0x140007ce5  jz      loc_140007F0E
0x140007ceb  lea     rcx, [rsi+8]; SpinLock
0x140007cef  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x140007cf6  nop     dword ptr [rax+rax+00h]
0x140007cfb  mov     eax, [rsi]
0x140007cfd  test    al, 4
0x140007cff  jz      loc_140008049
0x140007d05  lea     r15, [rsi+150h]
0x140007d0c  mov     rdi, [r15]
0x140007d0f  cmp     rdi, r15
0x140007d12  jnz     loc_1400084A8
0x140007d18  test    rdi, rdi
0x140007d1b  jz      loc_14000803F
0x140007d21  mov     r13, [rsi+160h]
0x140007d28  mov     qword ptr [rbp+0D0h+var_140], r13
0x140007d2c  test    r13, r13
0x140007d2f  jz      loc_14000859A
0x140007d35  mov     rax, [rsi+168h]
0x140007d3c  xorps   xmm0, xmm0
0x140007d3f  mov     edi, [rsi]
0x140007d41  xor     ecx, ecx
0x140007d43  mov     qword ptr [rbp+0D0h+var_110], rax
0x140007d47  xor     eax, eax
0x140007d49  mov     [rsp+1D0h+var_158], ecx
0x140007d4d  bt      edi, 6
0x140007d51  mov     [rbp+0D0h+var_120], rcx
0x140007d55  lea     rcx, [rsi+8]; SpinLock
0x140007d59  setb    r15b
0x140007d5d  mov     [rbp+0D0h+var_50], rax
0x140007d64  mov     [rsp+1D0h+Irql], r15b
0x140007d69  movups  [rbp+0D0h+var_D0], xmm0
0x140007d6d  movups  [rbp+0D0h+var_C0], xmm0
0x140007d71  movups  [rbp+0D0h+var_B0], xmm0
0x140007d75  movups  [rbp+0D0h+var_A0], xmm0
0x140007d79  movups  [rbp+0D0h+var_90], xmm0
0x140007d7d  movups  [rbp+0D0h+var_80], xmm0
0x140007d81  movups  [rbp+0D0h+var_70], xmm0
0x140007d85  movups  [rbp+0D0h+var_60], xmm0
0x140007d89  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140007d90  nop     dword ptr [rax+rax+00h]
0x140007d95  mov     rdx, [r14+30h]
0x140007d99  movzx   r8d, r15b
0x140007d9d  bt      edi, 6
0x140007da1  jb      loc_140008178
0x140007da7  movzx   eax, word ptr [rdx]
0x140007daa  cmp     ax, 23h ; '#'
0x140007dae  jnz     loc_140008070
0x140007db4  mov     ecx, 0Eh
0x140007db9  movzx   eax, cx
0x140007dbc  add     eax, 8
0x140007dbf  mov     dword ptr [rbp+0D0h+var_D0], 1
0x140007dc6  mov     [rbp+0D0h+var_F8], eax
0x140007dc9  mov     word ptr [rbp+0D0h+var_D0+4], cx
0x140007dcd  test    r8b, r8b
0x140007dd0  jnz     loc_14000818D
0x140007dd6  movzx   eax, word ptr [rdx]
0x140007dd9  add     rdx, 2; Src
0x140007ddd  movzx   r8d, cx; Size
0x140007de1  lea     rcx, [rbp+0D0h+var_D0+8]; void *
0x140007de5  mov     word ptr [rbp+0D0h+var_D0+6], ax
0x140007de9  call    memmove
0x140007dee  mov     r9, [r14+18h]
0x140007df2  mov     [rbp+0D0h+var_128], r9
0x140007df6  test    r9, r9
0x140007df9  jz      loc_14000805E
0x140007dff  mov     r15, [r14+8]
0x140007e03  mov     r13d, [r14+10h]
0x140007e07  mov     eax, [r15+28h]
0x140007e0b  cmp     r13, rax
0x140007e0e  mov     eax, [rsp+1D0h+var_16C]
0x140007e12  mov     [rsp+1D0h+var_16C], eax
0x140007e16  jnb     loc_140008501
0x140007e1c  test    byte ptr [r15+0Ah], 5
0x140007e21  jz      loc_1400081E7
0x140007e27  mov     rax, [r15+18h]
0x140007e2b  test    rax, rax
0x140007e2e  jz      loc_140007F04
0x140007e34  mov     rcx, qword ptr [rbp+0D0h+var_140]
0x140007e38  mov     edi, [r15+28h]
0x140007e3c  mov     qword ptr [rbp+0D0h+var_140], rcx
0x140007e40  sub     rdi, r13
0x140007e43  mov     rcx, qword ptr [rbp+0D0h+var_110]
0x140007e47  mov     qword ptr [rbp+0D0h+var_110], rcx
0x140007e4b  mov     rcx, r13
0x140007e4e  cmp     r9, rdi
0x140007e51  jnb     short loc_140007E56
0x140007e53  mov     rdi, r9
0x140007e56  lea     r12, [rcx+rax]
0x140007e5a  test    rdi, rdi
0x140007e5d  jnz     loc_1400080E8
0x140007e63  mov     r13, qword ptr [rbp+0D0h+var_140]
0x140007e67  mov     eax, [r14+28h]
0x140007e6b  xor     ecx, ecx
0x140007e6d  neg     eax
0x140007e6f  mov     [rsp+1D0h+var_158], ecx
0x140007e73  mov     rax, [rbp+0D0h+var_100]
0x140007e77  sbb     r15d, r15d
0x140007e7a  and     r15d, 1000h
0x140007e81  mov     eax, [rax]
0x140007e83  test    al, 1
0x140007e85  jz      loc_140008090
0x140007e8b  or      r15d, 4
0x140007e8f  mov     [rsp+1D0h+var_160], rcx
0x140007e94  mov     r8, cs:WPP_GLOBAL_Control
0x140007e9b  lea     rax, WPP_GLOBAL_Control
0x140007ea2  cmp     r8, rax
0x140007ea5  jz      short loc_140007EB2
0x140007ea7  cmp     byte ptr [r8+29h], 6
0x140007eac  jnb     loc_140008519
0x140007eb2  mov     rcx, [r14+20h]
0x140007eb6  lea     rax, [rsp+1D0h+var_160]
0x140007ebb  mov     edx, [rbp+0D0h+var_F8]
0x140007ebe  lea     r8, [rbp+0D0h+var_D0]
0x140007ec2  mov     [rsp+1D0h+var_180], rax
0x140007ec7  lea     rax, [rsp+1D0h+var_158]
0x140007ecc  mov     [rsp+1D0h+var_188], r12
0x140007ed1  mov     [rsp+1D0h+var_190], rax
0x140007ed6  mov     rax, r13
0x140007ed9  mov     [rsp+1D0h+var_198], r9d
0x140007ede  mov     r9d, [r14+28h]
0x140007ee2  mov     [rsp+1D0h+var_1A0], edi
0x140007ee6  mov     [rsp+1D0h+Priority], r15d
0x140007eeb  mov     qword ptr [rsp+1D0h+BugCheckOnFailure], rcx
0x140007ef0  mov     rcx, qword ptr [rbp+0D0h+var_110]
0x140007ef4  call    _guard_dispatch_icall
0x140007ef9  cmp     eax, 0C0000016h
0x140007efe  jz      loc_140008277
0x140007f04  mov     r15d, [rsp+1D0h+var_16C]
0x140007f09  mov     ecx, 0FFFFh
0x140007f0e  mov     r14, [r14]
0x140007f11  mov     r13, [rbp+0D0h+CallersAddress]
0x140007f15  test    r14, r14
0x140007f18  jnz     loc_140007CD5
0x140007f1e  lea     r12, [rbx+228h]
0x140007f25  movzx   ecx, [rsp+1D0h+var_168]; NewIrql
0x140007f2a  call    cs:__imp_KeLowerIrql
0x140007f31  nop     dword ptr [rax+rax+00h]
0x140007f36  test    r15b, r15b
0x140007f39  jnz     loc_1400085C0
0x140007f3f  mov     rsi, qword ptr [rbp+0D0h+var_150]
0x140007f43  lea     rax, [rbp+0D0h+var_150]
0x140007f47  lea     r14, aMinioNetioSess_2; "minio\\netio\\session\\tdi\\address.c"
0x140007f4e  cmp     rsi, rax
0x140007f51  jnz     loc_140008220
0x140007f57  test    r13, r13
0x140007f5a  jnz     loc_1400081D1
0x140007f60  mov     rcx, r12; SpinLock
0x140007f63  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140007f6a  nop     dword ptr [rax+rax+00h]
0x140007f6f  mov     ecx, [rbx+10h]
0x140007f72  movzx   edi, al
0x140007f75  mov     edx, [rbx+330h]
0x140007f7b  shl     rdx, 5
0x140007f7f  add     rdx, rbx
0x140007f82  mov     [rbp+0D0h+var_100], 0
0x140007f8a  dec     ecx
0x140007f8c  mov     [rdx+248h], ecx
0x140007f92  lea     rcx, [rbp+0D0h+var_100]; CallersAddress
0x140007f96  mov     [rdx+230h], r14
0x140007f9d  mov     dword ptr [rdx+238h], 76Ah
0x140007fa7  add     rdx, 240h; CallersCaller
0x140007fae  call    cs:__imp_RtlGetCallersAddress
0x140007fb5  nop     dword ptr [rax+rax+00h]
0x140007fba  mov     ecx, [rbx+330h]
0x140007fc0  movzx   edx, dil; NewIrql
0x140007fc4  inc     ecx
0x140007fc6  and     ecx, 7
0x140007fc9  mov     [rbx+330h], ecx
0x140007fcf  mov     rcx, r12; SpinLock
0x140007fd2  call    cs:__imp_KeReleaseSpinLock
0x140007fd9  nop     dword ptr [rax+rax+00h]
0x140007fde  mov     eax, 0FFFFFFFFh
0x140007fe3  lock xadd [rbx+10h], eax
0x140007fe8  cmp     eax, 1
0x140007feb  jnz     short loc_140008012
0x140007fed  mov     rcx, cs:WPP_GLOBAL_Control
0x140007ff4  lea     rax, WPP_GLOBAL_Control
0x140007ffb  cmp     rcx, rax
0x140007ffe  jz      short loc_14000800A
0x140008000  cmp     byte ptr [rcx+29h], 5
0x140008004  jnb     loc_1400085EC
0x14000800a  mov     rcx, rbx
0x14000800d  call    TdxCleanupObjectHeader
0x140008012  xor     eax, eax
0x140008014  mov     rcx, [rbp+0D0h+var_40]
0x14000801b  xor     rcx, rsp; StackCookie
0x14000801e  call    __security_check_cookie
0x140008023  mov     rbx, [rsp+1D0h+arg_10]
0x14000802b  add     rsp, 1A0h
0x140008032  pop     r15
0x140008034  pop     r14
0x140008036  pop     r13
0x140008038  pop     r12
0x14000803a  pop     rdi
0x14000803b  pop     rsi
0x14000803c  pop     rbp
0x14000803d  retn
0x14000803f  mov     r15d, [rsp+1D0h+var_16C]
0x140008044  mov     [rsp+1D0h+var_16C], r15d
0x140008049  lea     rcx, [rsi+8]; SpinLock
0x14000804d  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140008054  nop     dword ptr [rax+rax+00h]
0x140008059  jmp     loc_140007F09
0x14000805e  mov     eax, [rsp+1D0h+var_16C]
0x140008062  xor     r12d, r12d
0x140008065  xor     edi, edi
0x140008067  mov     [rsp+1D0h+var_16C], eax
0x14000806b  jmp     loc_140007E67
0x140008070  cmp     ax, 17h
0x140008074  jz      loc_140008162
0x14000807a  cmp     ax, 2
0x14000807e  jz      loc_140007DB4
0x140008084  mov     [rbp+0D0h+var_F8], 0
0x14000808b  jmp     loc_140007DEE
0x140008090  test    al, 2
0x140008092  jz      loc_140007E8F
0x140008098  or      r15d, 8
0x14000809c  jmp     loc_140007E8F
0x1400080a1  mov     rax, [r14+30h]
0x1400080a5  cmp     word ptr [rax], 17h
0x1400080a9  jnz     loc_140007CDF
0x1400080af  cmp     word ptr [rax+8], 0
  ... truncated ...
```
