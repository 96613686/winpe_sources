# NvmeCompleteSubmissionQueueRequests

- ea: `0x14010b0b0`
- end: `0x14010baf8`
- name: `NvmeCompleteSubmissionQueueRequests`
- size: `2632`
- prototype: ``
- caller_count: `3`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x140081810`
- `0x14010aa5c`
- `0x14010d8f4`

## callees

- `0x140033454`
- `0x14003348c`
- `0x140044110`
- `0x140044f10`
- `0x14005d36c`
- `0x140065dc0`
- `0x14006d1c0`
- `0x14006d298`
- `0x1400707a0`
- `0x140081d40`
- `0x1400848c4`
- `0x1400f37c8`
- `0x1401054c8`
- `0x14010b0b0`
- `0x14014b400`
- `0x14014b440`

## import_xrefs

- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14010b9f1`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14010b9f1`
- `ntoskrnl!PoFxIdleComponent` at `0x14010b671`
- `ntoskrnl!PoFxIdleComponent` at `0x14010b69e`
- `ntoskrnl!PoFxIdleComponent` at `0x14010b671`
- `ntoskrnl!PoFxIdleComponent` at `0x14010b69e`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14010b6e1`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14010b6e1`
- `ntoskrnl!KeSetEvent` at `0x14010b270`
- `ntoskrnl!KeSetEvent` at `0x14010b270`
- `ntoskrnl!KeLowerIrql` at `0x14010b484`
- `ntoskrnl!KeLowerIrql` at `0x14010b56b`
- `ntoskrnl!KeLowerIrql` at `0x14010b484`
- `ntoskrnl!KeLowerIrql` at `0x14010b56b`
- `ntoskrnl!KfRaiseIrql` at `0x14010b44c`
- `ntoskrnl!KfRaiseIrql` at `0x14010b535`
- `ntoskrnl!KfRaiseIrql` at `0x14010b44c`
- `ntoskrnl!KfRaiseIrql` at `0x14010b535`
- `ntoskrnl!IofCompleteRequest` at `0x14010b61a`
- `ntoskrnl!IofCompleteRequest` at `0x14010b9bd`
- `ntoskrnl!IofCompleteRequest` at `0x14010b61a`
- `ntoskrnl!IofCompleteRequest` at `0x14010b9bd`
- `ntoskrnl!KeDelayExecutionThread` at `0x14010ba52`
- `ntoskrnl!KeDelayExecutionThread` at `0x14010ba52`

## pseudocode

```c
__int64 __fastcall NvmeCompleteSubmissionQueueRequests(__int64 a1, char a2, int a3)
{
  int v3; // edi
  __int64 v4; // r13
  int v5; // ebx
  unsigned int v6; // ebp
  bool v8; // zf
  char v9; // al
  __int64 result; // rax
  __int64 Namespace; // r15
  __int64 v12; // r8
  __int64 v13; // r9
  __int64 v14; // r14
  __int64 v15; // rcx
  __int64 v16; // r12
  __int64 v17; // rdx
  __int64 v18; // rax
  __int64 v19; // rdi
  __int64 v20; // rbx
  __int64 v21; // rbp
  void (__fastcall *v22)(__int64, __int64, __int64, _QWORD, __int64, __int64); // r10
  __int64 v23; // r11
  __int64 v24; // rcx
  char v25; // dl
  __int64 v26; // rax
  __int64 v27; // rdx
  void (__fastcall *v28)(__int64, _QWORD, _QWORD); // rax
  __int64 v29; // rax
  __int64 v30; // rbp
  __int64 v31; // r15
  unsigned int v32; // eax
  int v33; // ecx
  _QWORD *v34; // rdi
  __int64 v35; // r8
  __int64 v36; // rax
  __int64 v37; // rdx
  __int64 v38; // r12
  int v39; // ecx
  unsigned int v40; // ebx
  __int64 v41; // rax
  __int64 v42; // r15
  __int64 v43; // r13
  char v44; // di
  __int64 v45; // rbx
  KIRQL v46; // al
  __int64 v47; // rcx
  __int64 v48; // r8
  __int64 v49; // rax
  __int64 v50; // rdx
  __int64 v51; // r15
  __int64 v52; // r12
  __int64 v53; // rbx
  char v54; // di
  KIRQL v55; // r13
  __int64 v56; // r8
  __int64 v57; // rax
  __int64 v58; // rbx
  __int64 v59; // rax
  __int64 v60; // rbx
  __int64 v61; // rcx
  unsigned __int64 v62; // rcx
  __int64 v63; // rdx
  int *v64; // rax
  int v65; // ecx
  __int64 *v66; // rdx
  __int64 v67; // rdx
  unsigned int v68; // r15d
  unsigned __int8 v69; // r10
  char *v70; // rbx
  _BYTE *v71; // r9
  __int64 v72; // rdi
  char v73; // r12
  unsigned __int64 v74; // r11
  __int64 v75; // r8
  int v76; // ecx
  char v77; // di
  char v78; // cl
  char v79; // bl
  char v80; // r11
  char v81; // r8
  _BYTE *v82; // rax
  char *v83; // r8
  unsigned int v84; // eax
  char v85; // al
  __int64 i; // rdx
  __int64 v87; // rcx
  signed __int32 v88[8]; // [rsp+0h] [rbp-108h] BYREF
  char v89; // [rsp+60h] [rbp-A8h]
  char v90; // [rsp+61h] [rbp-A7h]
  char v91; // [rsp+62h] [rbp-A6h]
  char v92; // [rsp+63h] [rbp-A5h]
  KIRQL NewIrql; // [rsp+64h] [rbp-A4h]
  int v94; // [rsp+68h] [rbp-A0h]
  _QWORD *v95; // [rsp+70h] [rbp-98h]
  unsigned int v96; // [rsp+78h] [rbp-90h]
  int v97; // [rsp+7Ch] [rbp-8Ch]
  unsigned int v98; // [rsp+80h] [rbp-88h]
  unsigned int v99; // [rsp+84h] [rbp-84h]
  int v100; // [rsp+88h] [rbp-80h]
  __int64 v101; // [rsp+90h] [rbp-78h]
  __int64 v102; // [rsp+98h] [rbp-70h]
  union _LARGE_INTEGER Interval; // [rsp+A0h] [rbp-68h] BYREF
  __int128 v104; // [rsp+A8h] [rbp-60h] BYREF

  v4 = *(_QWORD *)(a1 + 88);
  v5 = a3;
  v6 = *(_DWORD *)(a1 + 124);
  Interval.QuadPart = 0;
  v94 = a3;
  v8 = (*(_BYTE *)(v4 + 136) & 2) == 0;
  v92 = a2;
  if ( v8 )
    --v6;
  v101 = v4;
  v99 = v6;
  if ( a3 == -1073741810 || (v9 = *(_BYTE *)(v4 + 1252), v91 = 0, v9) )
    v91 = 1;
  result = IsOutstandingRequestInNvmeControllerQueue(v4, a1);
  if ( !(_BYTE)result )
    return result;
  LOBYTE(v3) = 0;
  Namespace = 0;
  v100 = v3;
  *(_QWORD *)(a1 + 112) |= 4uLL;
  v96 = 0;
  v90 = 0;
  _InterlockedOr(v88, 0);
  v12 = 0;
  v97 = 0;
  if ( !v6 )
    goto LABEL_143;
  v13 = 0;
  v102 = 0;
  do
  {
    v14 = v13 << 7;
    if ( (*(_BYTE *)(*(_QWORD *)(a1 + 32) + (v13 << 7) + 60) & 1) != 0 )
    {
      v15 = *(_QWORD *)(a1 + 32);
      v16 = *(unsigned __int16 *)(v15 + v14 + 56);
      *(_BYTE *)(v15 + v14 + 60) &= ~1u;
      if ( (*(_BYTE *)(v4 + 136) & 2) != 0 )
      {
        v17 = *(_QWORD *)(a1 + 32);
        v18 = 96;
        v19 = *(_QWORD *)(v17 + v14 + 24);
        if ( *(_BYTE *)(v19 + 2) != 40 )
          v18 = 48;
        v20 = *(_QWORD *)(v18 + v19);
        if ( v20 )
        {
          if ( *(char *)(v20 + 17) < 0 )
          {
            v25 = 1;
            v90 = 1;
            goto LABEL_22;
          }
          if ( *(_DWORD *)(v4 + 572) == 1 )
            Namespace = NvmeControllerGetNamespace(v4, *(unsigned int *)(v17 + v14 + 88));
          *(_BYTE *)(v19 + 3) = v92;
          v21 = *(_QWORD *)(v20 + 160);
          v96 = *(_DWORD *)(v20 + 20);
          NvmeAdapterDetachXrbFromSrb(v20);
          if ( v22 )
            v22(v4, v19, v21, v96, Namespace, v23);
          else
            KeSetEvent((PRKEVENT)(v20 + 664), 0, 0);
          v6 = v99;
          v24 = 2 * v16;
          LODWORD(v12) = v97;
          v13 = v102;
          *(_QWORD *)(*(_QWORD *)(a1 + 24) + 8 * v24) = 0;
          *(_WORD *)(*(_QWORD *)(a1 + 24) + 8 * v24 + 8) = -1;
          *(_QWORD *)(*(_QWORD *)(a1 + 32) + v14 + 24) = 0;
          *(_DWORD *)(*(_QWORD *)(a1 + 32) + v14 + 88) = 0;
          *(_QWORD *)(*(_QWORD *)(a1 + 32) + v14 + 32) = 0;
          *(_QWORD *)(*(_QWORD *)(a1 + 32) + v14 + 40) = 0;
        }
LABEL_21:
        v25 = v90;
LABEL_22:
        v5 = v94;
        LOBYTE(v3) = v100;
        *(_WORD *)(v14 + *(_QWORD *)(a1 + 32) + 56) = -1;
        goto LABEL_140;
      }
      v26 = *(_QWORD *)(a1 + 32);
      if ( *(_QWORD *)(v26 + v14 + 16) )
        FreeNVMePrpListBufferEntry(v4, *(unsigned __int16 *)(v26 + v14 + 52));
      v27 = *(_QWORD *)(a1 + 32);
      v28 = *(void (__fastcall **)(__int64, _QWORD, _QWORD))(v27 + v14 + 32);
      if ( v28 )
        v28(v4, *(_QWORD *)(v27 + v14 + 40), 0);
      v3 = (unsigned __int8)v3;
      v29 = *(_QWORD *)(a1 + 32);
      if ( (*(_BYTE *)(v29 + v14 + 60) & 0x20) != 0 )
        v3 = 1;
      v100 = v3;
      v30 = _InterlockedExchange64((volatile __int64 *)(v29 + v14 + 24), 0);
      if ( !v30 )
      {
LABEL_138:
        ExpInterlockedPushEntrySList((PSLIST_HEADER)(a1 + 64), (PSLIST_ENTRY)(v14 + *(_QWORD *)(a1 + 32)));
        LODWORD(v12) = v97;
        v13 = v102;
        v6 = v99;
        goto LABEL_21;
      }
      v31 = *(_QWORD *)(v30 + 184);
      v32 = (unsigned __int8)**(_DWORD **)(*(_QWORD *)(a1 + 24) + 16 * v16);
      if ( v32 > 0x19 || (v33 = 33554742, v89 = 1, !_bittest(&v33, v32)) )
        v89 = 0;
      v34 = (_QWORD *)NvmeControllerGetNamespace(v4, *(unsigned int *)(*(_QWORD *)(a1 + 32) + v14 + 88));
      v95 = v34;
      v36 = *(_QWORD *)(a1 + 32);
      if ( (*(_BYTE *)(v36 + v14 + 60) & 8) != 0 )
      {
        v37 = *(_QWORD *)(v36 + v14 + 40);
        v38 = *(_QWORD *)(v31 + 24);
        v39 = v94;
        v40 = *(unsigned __int16 *)(v38 + 32);
        _InterlockedExchange((volatile __int32 *)(v37 + 104), 5);
        *(_DWORD *)(v37 + 112) = v39;
        v41 = *(_QWORD *)(a1 + 32);
        v98 = v40;
        if ( *(char *)(v41 + v14 + 60) < 0 )
        {
          v42 = _InterlockedExchange64((volatile __int64 *)(v37 + 88), 0);
          if ( v42 )
          {
            v43 = *(_QWORD *)(v42 + 24);
            if ( v43 )
            {
              v44 = *(_BYTE *)(v42 + 126) & 1;
              v45 = *(_QWORD *)(v101 + 128);
              v46 = KfRaiseIrql(2u);
              v47 = *(_QWORD *)(v45 + 1160);
              NewIrql = v46;
              LOBYTE(v48) = v44 ^ 1;
              (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)(v47 + 8) + 96LL))(v47, v43, v48);
              if ( NewIrql < 2u )
                KeLowerIrql(NewIrql);
              v34 = v95;
              v40 = v98;
            }
            v4 = v101;
            FreeNVMeSGLBufferContext(v101, v42, 0);
          }
        }
        if ( _InterlockedIncrement((volatile signed __int32 *)(v38 + 116)) < v40 )
        {
          Namespace = (__int64)v95;
          goto LABEL_138;
        }
        v5 = v94;
        if ( v94 < 0 )
          v49 = 0;
        else
          v49 = *(unsigned int *)(v38 + 48);
        v50 = v96;
        *(_QWORD *)(v30 + 56) = v49;
        FreeNVMeChainedIoSplitContext(v4, v50, v38, v30);
LABEL_58:
        if ( v89 && !v91 && v34 )
        {
          v58 = 8LL * *(unsigned __int16 *)(*(_QWORD *)(a1 + 32) + v14 + 52);
          if ( (*(_BYTE *)(v30 + 151) & 1) != 0 )
            _InterlockedDecrement(*(volatile signed __int32 **)(v34[87]
                                                              + 8LL
                                                              * *(unsigned __int16 *)(*(_QWORD *)(a1 + 32) + v14 + 52)));
          *(_DWORD *)(v30 + 48) = v94;
          IofCompleteRequest((PIRP)v30, 0);
          v59 = v34[16];
          if ( !*(_BYTE *)v59
            && _InterlockedExchangeAdd(*(volatile signed __int32 **)(*(_QWORD *)(v59 + 24) + v58), 0xFFFFFFFF) == 1 )
          {
            v60 = *(_QWORD *)(v34[2] + 128LL);
            if ( (unsigned __int8)NvmeNamespaceCheckAndAcquirePoFx(v34) )
            {
              PoFxIdleComponent(**(_QWORD **)(v34[16] + 8LL), 0, 2);
              NvmeNamespaceReleasePoFx(v34);
            }
            v61 = *(_QWORD *)(v60 + 168);
            if ( *(_BYTE *)v61 == 1 )
              PoFxIdleComponent(**(_QWORD **)(v61 + 8), 0, 2);
          }
          goto LABEL_69;
        }
        v8 = StorEtwLoggingEnabled == 0;
        *(_BYTE *)(v30 + 141) = -84;
        *(_DWORD *)(v30 + 48) = v5;
        if ( v8 )
          goto LABEL_135;
        v104 = 0;
        IoGetActivityIdIrp(v30, &v104);
        v63 = *(_QWORD *)(v30 + 184);
        if ( *(_BYTE *)v63 == 14 )
        {
          if ( (byte_140177432 & 8) == 0 )
            goto LABEL_135;
          v66 = EventNonReadWriteRequestComplete;
          goto LABEL_83;
        }
        if ( *(_BYTE *)v63 != 15 )
        {
          if ( *(_BYTE *)v63 == 27 )
          {
            if ( *(_BYTE *)(v63 + 1) == 7 && !*(_DWORD *)(v63 + 8) )
            {
              if ( (byte_140177432 & 0x40) != 0 )
              {
                v64 = *(int **)(v30 + 56);
                if ( v64 )
                  v65 = *v64;
                else
                  v65 = 0;
                McTemplateK0pqd_EtwWriteTransfer(v65, v63, (unsigned int)&v104, v30, v65, *(_DWORD *)(v30 + 48));
              }
              goto LABEL_135;
            }
            if ( (byte_140177432 & 0x20) != 0 )
            {
              v66 = EventPnpRequestComplete;
LABEL_83:
              McTemplateK0pd_EtwWriteTransfer(v62, v66, &v104, v30, *(_DWORD *)(v30 + 48));
            }
          }
LABEL_135:
          IofCompleteRequest((PIRP)v30, 0);
LABEL_69:
          Namespace = (__int64)v95;
          goto LABEL_138;
        }
        if ( byte_140177431 >= 0 )
          goto LABEL_135;
        v67 = *(_QWORD *)(v63 + 8);
        if ( *(_BYTE *)(v67 + 2) == 40 )
        {
          if ( *(_DWORD *)(v67 + 20) )
            goto LABEL_135;
          v68 = *(_DWORD *)(v67 + 56);
          if ( !v68 )
            goto LABEL_135;
          v69 = 0;
          v70 = 0;
          v89 = 0;
          v71 = 0;
          v72 = 0;
          v73 = 0;
          do
          {
            v62 = *(unsigned int *)(v67 + 4 * v72 + 120);
            if ( (unsigned int)v62 >= 0x80 )
            {
              v74 = *(unsigned int *)(v67 + 16);
              if ( (unsigned int)v62 < (unsigned int)v74 )
              {
                v75 = (unsigned int)v62;
                v76 = *(_DWORD *)(v62 + v67) - 64;
                if ( v76 )
                {
                  LODWORD(v62) = v76 - 1;
                  if ( (_DWORD)v62 )
                  {
                    if ( (_DWORD)v62 == 1 )
                    {
                      LODWORD(v62) = v75 + 40;
                      if ( v75 + 40 <= v74 )
                      {
                        if ( *(_DWORD *)(v75 + v67 + 12) )
                          v70 = (char *)(v67 + v75 + 32);
                        v71 = *(_BYTE **)(v75 + v67 + 24);
LABEL_98:
                        v77 = *(_BYTE *)(v75 + v67 + 8);
                        v69 = *(_BYTE *)(v75 + v67 + 9);
                        goto LABEL_107;
                      }
                    }
                  }
                  else
                  {
                    LODWORD(v62) = v75 + 56;
                    if ( v75 + 56 <= v74 )
                    {
                      v73 = 1;
                      if ( *(_BYTE *)(v75 + v67 + 10) )
                        v70 = (char *)(v67 + v75 + 24);
                      v71 = *(_BYTE **)(v75 + v67 + 16);
                      v69 = *(_BYTE *)(v75 + v67 + 9);
                      v89 = *(_BYTE *)(v75 + v67 + 8);
                    }
                  }
                }
                else
                {
                  LODWORD(v62) = v75 + 40;
                  if ( v75 + 40 <= v74 )
                  {
                    if ( *(_BYTE *)(v75 + v67 + 10) )
                      v70 = (char *)(v67 + v75 + 24);
                    v71 = *(_BYTE **)(v75 + v67 + 16);
                    goto LABEL_98;
                  }
                }
                if ( v73 )
                  break;
              }
            }
            v72 = (unsigned int)(v72 + 1);
          }
          while ( (unsigned int)v72 < v68 );
          v77 = v89;
LABEL_107:
          if ( !v70 )
            goto LABEL_135;
          v78 = *v70;
        }
        else
        {
          v78 = *(_BYTE *)(v67 + 72);
          v71 = *(_BYTE **)(v67 + 32);
          v69 = *(_BYTE *)(v67 + 11);
          v77 = *(_BYTE *)(v67 + 4);
          if ( *(_BYTE *)(v67 + 2) )
            goto LABEL_135;
        }
        LOBYTE(v62) = v78 - 8;
        if ( (v62 & 0x5D) != 0 )
          goto LABEL_135;
        v79 = *(_BYTE *)(v67 + 3);
        if ( v79 == 1 || !v71 || !v69 )
          goto LABEL_131;
        LOBYTE(v67) = 0;
        v80 = 0;
        v81 = 0;
        v62 = (unsigned __int64)&v71[v69];
        v82 = v71 + 8;
        if ( (unsigned __int8)((*v71 & 0x7F) - 114) <= 1u )
        {
          if ( (unsigned __int64)v82 <= v62 )
          {
            v80 = v71[2];
            LOBYTE(v67) = v71[1] & 0xF;
            v81 = v71[3];
LABEL_128:
            v85 = 1;
            goto LABEL_130;
          }
        }
        else if ( (unsigned __int64)v82 <= v62 )
        {
          v83 = v71 + 13;
          LOBYTE(v67) = v71[2] & 0xF;
          v84 = v69;
          if ( (unsigned int)(unsigned __int8)v71[7] + 8 <= v69 )
            v84 = (unsigned __int8)v71[7] + 8;
          v62 = (unsigned __int64)&v71[v84];
          if ( (unsigned __int64)v83 <= v62 )
            v80 = v71[12];
          if ( (unsigned __int64)(v71 + 14) > v62 )
            v81 = 0;
          else
            v81 = *v83;
          goto LABEL_128;
        }
        v85 = 0;
LABEL_130:
        if ( v85 )
        {
LABEL_132:
          McTemplateK0pduuuuup_EtwWriteTransfer(
            v62,
            v67,
            (unsigned int)&v104,
            v30,
            *(_DWORD *)(v30 + 48),
            v79,
            v77,
            v67,
            v80,
            v81,
            v30);
          goto LABEL_135;
        }
LABEL_131:
        LOBYTE(v67) = 0;
        v80 = 0;
        v81 = 0;
        goto LABEL_132;
      }
      if ( *(char *)(v36 + v14 + 60) >= 0 )
      {
        if ( (*(_BYTE *)(*(_QWORD *)(a1 + 32) + v14 + 60) & 2) == 0 )
          goto LABEL_58;
      }
      else if ( *(_QWORD *)(v31 + 8) == 0xFEDCBA9000000000uLL )
      {
        v51 = *(_QWORD *)(v31 + 24);
        v52 = *(_QWORD *)(v51 + 24);
        if ( v52 )
        {
          v53 = *(_QWORD *)(v4 + 128);
          v54 = *(_BYTE *)(v51 + 126) & 1;
          v55 = KfRaiseIrql(2u);
          LOBYTE(v56) = v54 ^ 1;
          (*(void (__fastcall **)(_QWORD, __int64, __int64))(*(_QWORD *)(*(_QWORD *)(v53 + 1160) + 8LL) + 96LL))(
            *(_QWORD *)(v53 + 1160),
            v52,
            v56);
          if ( v55 < 2u )
            KeLowerIrql(v55);
          v5 = v94;
          v34 = v95;
          v4 = v101;
        }
        if ( v5 < 0 )
          v57 = 0;
        else
          v57 = *(unsigned int *)(v51 + 116);
        *(_QWORD *)(v30 + 56) = v57;
        LOBYTE(v35) = 1;
        FreeNVMeSGLBufferContext(v4, v51, v35);
        goto LABEL_58;
      }
      Namespace = (__int64)v34;
      goto LABEL_138;
    }
    v25 = v90;
LABEL_140:
    v12 = (unsigned int)(v12 + 1);
    ++v13;
    v97 = v12;
    v102 = v13;
  }
  while ( (unsigned int)v12 < v6 );
  if ( v25 )
  {
    Interval.QuadPart = -10000000;
    KeDelayExecutionThread(0, 0, &Interval);
  }
LABEL_143:
  for ( i = 0; (unsigned int)i < *(_DWORD *)(a1 + 124); *(_WORD *)(*(_QWORD *)(a1 + 24) + 8 * v87 + 8) = -1 )
  {
    v87 = (unsigned int)i;
    i = (unsigned int)(i + 1);
    v87 *= 2;
    *(_QWORD *)(*(_QWORD *)(a1 + 24) + 8 * v87) = 0;
  }
  result = 0;
  *(_WORD *)(a1 + 148) = 0;
  *(_DWORD *)(a1 + 140) = 0;
  if ( !v91 )
  {
    result = IsNvmeControllerGone(v4, i, v12, 0xFFFF);
    if ( !(_BYTE)result && v5 != -1073740534 )
    {
      if ( (_BYTE)v3 )
      {
        _interlockedbittestandreset((volatile signed __int32 *)(v4 + 948), 1u);
        result = NvmeControllerRestart((PVOID)v4);
      }
    }
  }
  *(_QWORD *)(a1 + 112) &= ~4uLL;
  return result;
}

```

## disassembly

```asm
0x14010b0b0  mov     r11, rsp
0x14010b0b3  push    rbx
0x14010b0b4  push    rbp
0x14010b0b5  push    rsi
0x14010b0b6  push    rdi
0x14010b0b7  push    r12
0x14010b0b9  push    r13
0x14010b0bb  push    r14
0x14010b0bd  push    r15
0x14010b0bf  sub     rsp, 0C8h
0x14010b0c6  mov     rax, cs:__security_cookie
0x14010b0cd  xor     rax, rsp
0x14010b0d0  mov     [rsp+108h+var_50], rax
0x14010b0d8  mov     r13, [rcx+58h]
0x14010b0dc  mov     ebx, r8d
0x14010b0df  mov     ebp, [rcx+7Ch]
0x14010b0e2  mov     rsi, rcx
0x14010b0e5  mov     qword ptr [r11-68h], 0
0x14010b0ed  mov     r12d, 1
0x14010b0f3  mov     [rsp+108h+var_A0], ebx
0x14010b0f7  test    byte ptr [r13+88h], 2
0x14010b0ff  lea     eax, [rbp-1]
0x14010b102  mov     [rsp+108h+var_A5], dl
0x14010b106  cmovz   ebp, eax
0x14010b109  mov     [rsp+108h+var_78], r13
0x14010b111  mov     [rsp+108h+var_84], ebp
0x14010b118  cmp     r8d, 0C000000Eh
0x14010b11f  jz      short loc_14010B131
0x14010b121  mov     al, [r13+4E4h]
0x14010b128  mov     [rsp+108h+var_A6], 0
0x14010b12d  test    al, al
0x14010b12f  jz      short loc_14010B136
0x14010b131  mov     [rsp+108h+var_A6], r12b
0x14010b136  mov     rdx, rsi
0x14010b139  mov     rcx, r13
0x14010b13c  call    IsOutstandingRequestInNvmeControllerQueue
0x14010b141  test    al, al
0x14010b143  jz      loc_14010BAD3
0x14010b149  xor     dil, dil
0x14010b14c  xor     r15d, r15d
0x14010b14f  xor     dl, dl
0x14010b151  mov     [rsp+108h+var_80], edi
0x14010b158  or      qword ptr [rsi+70h], 4
0x14010b15d  mov     [rsp+108h+var_90], r15d
0x14010b162  mov     [rsp+108h+var_A7], dl
0x14010b166  lock or [rsp+108h+var_108], r15d
0x14010b16b  xor     r8d, r8d
0x14010b16e  mov     r9d, 0FFFFh
0x14010b174  mov     [rsp+108h+var_8C], r8d
0x14010b179  test    ebp, ebp
0x14010b17b  jz      loc_14010BA64
0x14010b181  xor     r9d, r9d
0x14010b184  mov     [rsp+108h+var_70], r9
0x14010b18c  mov     rax, [rsi+20h]
0x14010b190  mov     r14, r9
0x14010b193  shl     r14, 7
0x14010b197  mov     cl, [rax+r14+3Ch]
0x14010b19c  test    r12b, cl
0x14010b19f  jz      loc_14010BA16
0x14010b1a5  mov     rcx, [rsi+20h]
0x14010b1a9  mov     al, [rcx+r14+3Ch]
0x14010b1ae  movzx   r12d, word ptr [rcx+r14+38h]
0x14010b1b4  and     al, 0FEh
0x14010b1b6  mov     [rcx+r14+3Ch], al
0x14010b1bb  test    byte ptr [r13+88h], 2
0x14010b1c3  jz      loc_14010B316
0x14010b1c9  mov     rdx, [rsi+20h]
0x14010b1cd  mov     eax, 60h ; '`'
0x14010b1d2  mov     rdi, [rdx+r14+18h]
0x14010b1d7  lea     ecx, [rax-30h]
0x14010b1da  cmp     byte ptr [rdi+2], 28h ; '('
0x14010b1de  cmovnz  eax, ecx
0x14010b1e1  mov     rbx, [rax+rdi]
0x14010b1e5  test    rbx, rbx
0x14010b1e8  jz      loc_14010B2E1
0x14010b1ee  cmp     byte ptr [rbx+11h], 0
0x14010b1f2  jl      loc_14010B307
0x14010b1f8  cmp     dword ptr [r13+23Ch], 1
0x14010b200  jnz     short loc_14010B212
0x14010b202  mov     edx, [rdx+r14+58h]
0x14010b207  mov     rcx, r13
0x14010b20a  call    NvmeControllerGetNamespace
0x14010b20f  mov     r15, rax
0x14010b212  mov     rcx, [rsi+20h]
0x14010b216  mov     al, [rsp+108h+var_A5]
0x14010b21a  mov     r10, [rcx+r14+20h]
0x14010b21f  mov     r11, [rcx+r14+28h]
0x14010b224  mov     rcx, rbx
0x14010b227  mov     [rdi+3], al
0x14010b22a  mov     eax, [rbx+14h]
0x14010b22d  mov     rbp, [rbx+0A0h]
0x14010b234  mov     [rsp+108h+var_90], eax
0x14010b238  call    NvmeAdapterDetachXrbFromSrb
0x14010b23d  test    r10, r10
0x14010b240  jz      short loc_14010B264
0x14010b242  mov     r9d, [rsp+108h+var_90]
0x14010b247  mov     r8, rbp
0x14010b24a  mov     [rsp+108h+var_E0], r11
0x14010b24f  mov     rdx, rdi
0x14010b252  mov     rcx, r13
0x14010b255  mov     [rsp+108h+var_E8], r15
0x14010b25a  mov     rax, r10
0x14010b25d  call    _guard_dispatch_icall
0x14010b262  jmp     short loc_14010B27C
0x14010b264  lea     rcx, [rbx+298h]; Event
0x14010b26b  xor     r8d, r8d; Wait
0x14010b26e  xor     edx, edx; Increment
0x14010b270  call    cs:__imp_KeSetEvent
0x14010b277  nop     dword ptr [rax+rax+00h]
0x14010b27c  mov     rax, [rsi+18h]
0x14010b280  mov     rcx, r12
0x14010b283  mov     ebp, [rsp+108h+var_84]
0x14010b28a  add     rcx, rcx
0x14010b28d  mov     r8d, [rsp+108h+var_8C]
0x14010b292  mov     r9, [rsp+108h+var_70]
0x14010b29a  mov     qword ptr [rax+rcx*8], 0
0x14010b2a2  mov     rax, [rsi+18h]
0x14010b2a6  mov     word ptr [rax+rcx*8+8], 0FFFFh
0x14010b2ad  mov     rax, [rsi+20h]
0x14010b2b1  mov     qword ptr [rax+r14+18h], 0
0x14010b2ba  mov     rax, [rsi+20h]
0x14010b2be  mov     dword ptr [rax+r14+58h], 0
0x14010b2c7  mov     rax, [rsi+20h]
0x14010b2cb  mov     qword ptr [rax+r14+20h], 0
0x14010b2d4  mov     rax, [rsi+20h]
0x14010b2d8  mov     qword ptr [rax+r14+28h], 0
0x14010b2e1  mov     r12d, 1
0x14010b2e7  mov     dl, [rsp+108h+var_A7]
0x14010b2eb  mov     rax, [rsi+20h]
0x14010b2ef  mov     ebx, [rsp+108h+var_A0]
0x14010b2f3  mov     edi, [rsp+108h+var_80]
0x14010b2fa  mov     word ptr [r14+rax+38h], 0FFFFh
0x14010b302  jmp     loc_14010BA1A
0x14010b307  mov     r12d, 1
0x14010b30d  mov     dl, r12b
0x14010b310  mov     [rsp+108h+var_A7], dl
0x14010b314  jmp     short loc_14010B2EB
0x14010b316  mov     rax, [rsi+20h]
0x14010b31a  mov     r8, [rax+r14+10h]
0x14010b31f  test    r8, r8
0x14010b322  jz      short loc_14010B332
0x14010b324  movzx   edx, word ptr [rax+r14+34h]
0x14010b32a  mov     rcx, r13
0x14010b32d  call    FreeNVMePrpListBufferEntry
0x14010b332  mov     rdx, [rsi+20h]
0x14010b336  mov     rax, [rdx+r14+20h]
0x14010b33b  test    rax, rax
0x14010b33e  jz      short loc_14010B350
0x14010b340  mov     rdx, [rdx+r14+28h]
0x14010b345  xor     r8d, r8d
0x14010b348  mov     rcx, r13
0x14010b34b  call    _guard_dispatch_icall
0x14010b350  mov     rax, [rsi+20h]
0x14010b354  mov     edx, 1
0x14010b359  movzx   edi, dil
0x14010b35d  mov     cl, [rax+r14+3Ch]
0x14010b362  mov     rax, [rsi+20h]
0x14010b366  test    cl, 20h
0x14010b369  cmovnz  edi, edx
0x14010b36c  xor     ebp, ebp
0x14010b36e  mov     [rsp+108h+var_80], edi
0x14010b375  xchg    rbp, [rax+r14+18h]
0x14010b37a  test    rbp, rbp
0x14010b37d  jz      loc_14010B9E3
0x14010b383  mov     rax, [rsi+18h]
0x14010b387  mov     rcx, r12
0x14010b38a  mov     r15, [rbp+0B8h]
0x14010b391  add     rcx, rcx
0x14010b394  mov     rcx, [rax+rcx*8]
0x14010b398  mov     eax, [rcx]
0x14010b39a  movzx   eax, al
0x14010b39d  cmp     eax, 19h
0x14010b3a0  ja      short loc_14010B3B0
0x14010b3a2  mov     ecx, 2000136h
0x14010b3a7  mov     [rsp+108h+var_A8], dl
0x14010b3ab  bt      ecx, eax
0x14010b3ae  jb      short loc_14010B3B5
0x14010b3b0  mov     [rsp+108h+var_A8], 0
0x14010b3b5  mov     rdx, [rsi+20h]
0x14010b3b9  mov     rcx, r13
0x14010b3bc  mov     edx, [rdx+r14+58h]
0x14010b3c1  call    NvmeControllerGetNamespace
0x14010b3c6  mov     rdi, rax
0x14010b3c9  mov     [rsp+108h+var_98], rax
0x14010b3ce  mov     rax, [rsi+20h]
0x14010b3d2  mov     cl, [rax+r14+3Ch]
0x14010b3d7  mov     rax, [rsi+20h]
0x14010b3db  test    cl, 8
0x14010b3de  jz      loc_14010B4F6
0x14010b3e4  mov     rdx, [rax+r14+28h]
0x14010b3e9  mov     eax, 5
0x14010b3ee  mov     r12, [r15+18h]
0x14010b3f2  mov     ecx, [rsp+108h+var_A0]
0x14010b3f6  movzx   ebx, word ptr [r12+20h]
0x14010b3fc  xchg    eax, [rdx+68h]
0x14010b3ff  mov     [rdx+70h], ecx
0x14010b402  mov     rax, [rsi+20h]
0x14010b406  mov     [rsp+108h+var_88], ebx
0x14010b40d  mov     cl, [rax+r14+3Ch]
0x14010b412  test    cl, cl
0x14010b414  jns     loc_14010B4B2
0x14010b41a  xor     r15d, r15d
0x14010b41d  xchg    r15, [rdx+58h]
0x14010b421  test    r15, r15
0x14010b424  jz      loc_14010B4B2
0x14010b42a  mov     r13, [r15+18h]
0x14010b42e  test    r13, r13
0x14010b431  jz      short loc_14010B49C
0x14010b433  mov     dil, [r15+7Eh]
0x14010b437  mov     cl, 2; NewIrql
0x14010b439  mov     rbx, [rsp+108h+var_78]
0x14010b441  and     dil, 1
0x14010b445  mov     rbx, [rbx+80h]
0x14010b44c  call    cs:__imp_KfRaiseIrql
0x14010b453  nop     dword ptr [rax+rax+00h]
0x14010b458  mov     rcx, [rbx+488h]
0x14010b45f  xor     dil, 1
0x14010b463  mov     [rsp+108h+NewIrql], al
0x14010b467  mov     r8b, dil
0x14010b46a  mov     rdx, r13
0x14010b46d  mov     r9, [rcx+8]
0x14010b471  mov     rax, [r9+60h]
0x14010b475  call    _guard_dispatch_icall
0x14010b47a  mov     al, [rsp+108h+NewIrql]
0x14010b47e  cmp     al, 2
0x14010b480  jnb     short loc_14010B490
0x14010b482  mov     cl, al; NewIrql
0x14010b484  call    cs:__imp_KeLowerIrql
0x14010b48b  nop     dword ptr [rax+rax+00h]
0x14010b490  mov     rdi, [rsp+108h+var_98]
0x14010b495  mov     ebx, [rsp+108h+var_88]
0x14010b49c  mov     r13, [rsp+108h+var_78]
0x14010b4a4  xor     r8d, r8d
0x14010b4a7  mov     rcx, r13
0x14010b4aa  mov     rdx, r15
0x14010b4ad  call    FreeNVMeSGLBufferContext
0x14010b4b2  mov     ecx, 1
0x14010b4b7  mov     eax, ecx
0x14010b4b9  lock xadd [r12+74h], eax
0x14010b4c0  add     eax, ecx
0x14010b4c2  cmp     eax, ebx
0x14010b4c4  jb      loc_14010B9D9
0x14010b4ca  mov     ebx, [rsp+108h+var_A0]
0x14010b4ce  test    ebx, ebx
0x14010b4d0  js      short loc_14010B4D9
0x14010b4d2  mov     eax, [r12+30h]
0x14010b4d7  jmp     short loc_14010B4DB
0x14010b4d9  xor     eax, eax
0x14010b4db  mov     edx, [rsp+108h+var_90]
0x14010b4df  mov     r9, rbp
0x14010b4e2  mov     r8, r12
0x14010b4e5  mov     [rbp+38h], rax
0x14010b4e9  mov     rcx, r13
0x14010b4ec  call    FreeNVMeChainedIoSplitContext
0x14010b4f1  jmp     loc_14010B5C0
0x14010b4f6  mov     cl, [rax+r14+3Ch]
0x14010b4fb  test    cl, cl
0x14010b4fd  jns     loc_14010B5AE
0x14010b503  mov     rax, 0FEDCBA9000000000h
0x14010b50d  cmp     [r15+8], rax
0x14010b511  jnz     loc_14010B9CE
0x14010b517  mov     r15, [r15+18h]
0x14010b51b  mov     r12, [r15+18h]
0x14010b51f  test    r12, r12
0x14010b522  jz      short loc_14010B588
0x14010b524  mov     dil, [r15+7Eh]
0x14010b528  mov     cl, 2; NewIrql
0x14010b52a  mov     rbx, [r13+80h]
0x14010b531  and     dil, 1
0x14010b535  call    cs:__imp_KfRaiseIrql
0x14010b53c  nop     dword ptr [rax+rax+00h]
0x14010b541  mov     rcx, [rbx+488h]
0x14010b548  xor     dil, 1
0x14010b54c  mov     r13b, al
0x14010b54f  mov     r8b, dil
0x14010b552  mov     rdx, r12
0x14010b555  mov     r9, [rcx+8]
0x14010b559  mov     rax, [r9+60h]
0x14010b55d  call    _guard_dispatch_icall
0x14010b562  cmp     r13b, 2
0x14010b566  jnb     short loc_14010B577
0x14010b568  mov     cl, r13b; NewIrql
0x14010b56b  call    cs:__imp_KeLowerIrql
0x14010b572  nop     dword ptr [rax+rax+00h]
0x14010b577  mov     ebx, [rsp+108h+var_A0]
0x14010b57b  mov     rdi, [rsp+108h+var_98]
0x14010b580  mov     r13, [rsp+108h+var_78]
0x14010b588  test    ebx, ebx
0x14010b58a  js      short loc_14010B592
0x14010b58c  mov     eax, [r15+74h]
0x14010b590  jmp     short loc_14010B594
0x14010b592  xor     eax, eax
0x14010b594  mov     r12d, 1
0x14010b59a  mov     [rbp+38h], rax
0x14010b59e  mov     r8b, r12b
0x14010b5a1  mov     rdx, r15
0x14010b5a4  mov     rcx, r13
0x14010b5a7  call    FreeNVMeSGLBufferContext
0x14010b5ac  jmp     short loc_14010B5C6
0x14010b5ae  mov     rax, [rsi+20h]
  ... truncated ...
```
