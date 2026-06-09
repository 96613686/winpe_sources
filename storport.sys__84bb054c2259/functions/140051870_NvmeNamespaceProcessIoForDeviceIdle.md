# NvmeNamespaceProcessIoForDeviceIdle

- ea: `0x140051870`
- end: `0x140052394`
- name: `NvmeNamespaceProcessIoForDeviceIdle`
- size: `2852`
- prototype: `__int64 __fastcall(ULONG_PTR BugCheckParameter3)`
- caller_count: `1`
- callee_count: `17`
- tags: `broker_com_uri`

## callers

- `0x1400604a0`

## callees

- `0x140033454`
- `0x14003348c`
- `0x140042b60`
- `0x140043ca0`
- `0x1400479e0`
- `0x140051870`
- `0x140060e90`
- `0x140062190`
- `0x140065dc0`
- `0x140066100`
- `0x140066260`
- `0x1400707a0`
- `0x14012f040`
- `0x14012f180`
- `0x1401346e0`
- `0x14014b400`
- `0x14014b440`

## import_xrefs

- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x14005195b`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x14005195b`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140051cb3`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140051cb3`
- `ntoskrnl!PoFxIdleComponent` at `0x140052326`
- `ntoskrnl!PoFxIdleComponent` at `0x140052355`
- `ntoskrnl!PoFxIdleComponent` at `0x140052326`
- `ntoskrnl!PoFxIdleComponent` at `0x140052355`
- `ntoskrnl!KeLowerIrql` at `0x140051c7f`
- `ntoskrnl!KeLowerIrql` at `0x140051fa7`
- `ntoskrnl!KeLowerIrql` at `0x140051c7f`
- `ntoskrnl!KeLowerIrql` at `0x140051fa7`
- `ntoskrnl!KfRaiseIrql` at `0x140051c43`
- `ntoskrnl!KfRaiseIrql` at `0x140051ecd`
- `ntoskrnl!KfRaiseIrql` at `0x140051c43`
- `ntoskrnl!KfRaiseIrql` at `0x140051ecd`
- `ntoskrnl!IofCompleteRequest` at `0x1400522cb`
- `ntoskrnl!IofCompleteRequest` at `0x1400522cb`
- `ntoskrnl!KeQueryUnbiasedInterruptTimePrecise` at `0x1400518ef`
- `ntoskrnl!KeQueryUnbiasedInterruptTimePrecise` at `0x1400519b5`
- `ntoskrnl!KeQueryUnbiasedInterruptTimePrecise` at `0x1400518ef`
- `ntoskrnl!KeQueryUnbiasedInterruptTimePrecise` at `0x1400519b5`
- `ntoskrnl!IoRecordIoAttribution` at `0x140051906`
- `ntoskrnl!IoRecordIoAttribution` at `0x1400519cc`
- `ntoskrnl!IoRecordIoAttribution` at `0x140051906`
- `ntoskrnl!IoRecordIoAttribution` at `0x1400519cc`
- `ntoskrnl!IoGetIoAttributionHandle` at `0x1400518b2`
- `ntoskrnl!IoGetIoAttributionHandle` at `0x1400518b2`

## pseudocode

```c
unsigned __int64 __fastcall NvmeNamespaceProcessIoForDeviceIdle(
        ULONG_PTR BugCheckParameter3,
        __int64 a2,
        unsigned int a3)
{
  __int64 v3; // r15
  unsigned __int8 *v6; // rax
  __int64 v7; // rbx
  __int64 v8; // rax
  unsigned __int64 result; // rax
  ULONGLONG *v10; // rbx
  __int64 v11; // r9
  unsigned __int64 v12; // r13
  __int64 v13; // rdi
  unsigned __int8 *v14; // rax
  unsigned __int64 v15; // r8
  __int64 v16; // rcx
  __int64 v17; // rdi
  char v18; // r10
  __int64 v19; // rbx
  unsigned __int64 v20; // rdx
  unsigned int v21; // r14d
  __int64 v22; // r12
  int v23; // r14d
  char v24; // cl
  __int16 v25; // di
  __int64 v26; // rbx
  signed __int32 v27; // eax
  int v28; // r9d
  unsigned int v29; // edx
  __int64 v30; // r12
  unsigned __int8 v31; // di
  __int64 v32; // rbx
  KIRQL v33; // al
  __int64 v34; // r9
  __int64 v35; // rdx
  __int64 v36; // rcx
  unsigned int v37; // r10d
  unsigned __int64 v38; // r14
  unsigned __int64 v39; // r8
  unsigned __int64 v40; // rbx
  unsigned __int64 v41; // r9
  unsigned __int64 v42; // rcx
  unsigned int v43; // ecx
  char v44; // al
  unsigned int v45; // eax
  __int64 NVMeSGLBufferContext; // rax
  __int64 v47; // rdx
  bool v48; // zf
  char v49; // al
  __int64 v50; // rcx
  __int64 v51; // rax
  int v52; // ebx
  __int64 v53; // rdi
  KIRQL v54; // al
  __int64 v55; // rbx
  __int64 v56; // rdx
  __int64 v57; // r10
  __int64 v58; // rdx
  unsigned __int64 v59; // rdi
  unsigned __int64 v60; // rcx
  __int64 v61; // r8
  unsigned int v62; // edx
  char v63; // al
  unsigned int v64; // eax
  __int64 NVMePrpListBufferEntry; // r9
  __int64 v66; // r10
  __int64 v67; // r8
  __int64 v68; // rbx
  __int64 v69; // rcx
  signed __int32 v70[8]; // [rsp+0h] [rbp-C9h] BYREF
  int v71[2]; // [rsp+28h] [rbp-A1h]
  int v72[2]; // [rsp+30h] [rbp-99h]
  __int64 v73; // [rsp+38h] [rbp-91h]
  __int64 v74; // [rsp+40h] [rbp-89h]
  __int64 v75; // [rsp+48h] [rbp-81h]
  unsigned __int8 v76; // [rsp+60h] [rbp-69h]
  char v77; // [rsp+61h] [rbp-68h]
  char v78; // [rsp+62h] [rbp-67h] BYREF
  __int16 v79; // [rsp+64h] [rbp-65h]
  int v80; // [rsp+68h] [rbp-61h]
  __int64 v81; // [rsp+70h] [rbp-59h]
  unsigned __int64 v82; // [rsp+78h] [rbp-51h]
  unsigned __int16 v83; // [rsp+80h] [rbp-49h] BYREF
  unsigned __int64 v84; // [rsp+88h] [rbp-41h]
  __int64 v85; // [rsp+90h] [rbp-39h]
  int v86; // [rsp+98h] [rbp-31h] BYREF
  __int64 v87; // [rsp+A0h] [rbp-29h] BYREF
  unsigned __int64 v88; // [rsp+A8h] [rbp-21h]
  __int64 v89; // [rsp+B0h] [rbp-19h] BYREF
  unsigned __int64 v90; // [rsp+B8h] [rbp-11h]
  __int128 v91; // [rsp+C0h] [rbp-9h] BYREF
  unsigned __int64 QpcTimeStamp[2]; // [rsp+D0h] [rbp+7h] BYREF

  v3 = a3;
  v87 = 0;
  *(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) |= 1u;
  if ( (int)IoGetIoAttributionHandle(a2, &v87) >= 0 )
  {
    v6 = *(unsigned __int8 **)(a2 + 184);
    v7 = v87;
    v91 = 0;
    LODWORD(v91) = 1;
    *(_OWORD *)QpcTimeStamp = 0;
    DWORD1(v91) = *v6 | 0x300;
    QpcTimeStamp[1] = KeQueryUnbiasedInterruptTimePrecise(&QpcTimeStamp[1]);
    IoRecordIoAttribution(v7, &v91);
  }
  StorPushRequestToDeviceQueue(*(_QWORD *)(BugCheckParameter3 + 256), (unsigned int)v3, a2);
  _InterlockedOr(v70, 0);
  v8 = *(_QWORD *)(BugCheckParameter3 + 128);
  if ( *(_BYTE *)(v8 + 1) == 1 )
  {
    result = *(_QWORD *)(v8 + 8);
    if ( !*(_BYTE *)(result + 64) )
      return result;
  }
  v10 = *(ULONGLONG **)(*(_QWORD *)(*(_QWORD *)(BugCheckParameter3 + 16) + 1312LL) + 40LL);
  *v10 = KeQueryUnbiasedInterruptTime();
  result = StorPopRequestFromDeviceQueue(*(_QWORD *)(BugCheckParameter3 + 256), (unsigned int)v3);
  v12 = result;
  if ( !result )
    return result;
  v13 = v87;
  if ( v87 )
  {
    v14 = *(unsigned __int8 **)(result + 184);
    v91 = 0;
    LODWORD(v91) = 1;
    *(_OWORD *)QpcTimeStamp = 0;
    DWORD1(v91) = *v14 | 0x200;
    QpcTimeStamp[1] = KeQueryUnbiasedInterruptTimePrecise(&QpcTimeStamp[1]);
    IoRecordIoAttribution(v13, &v91);
  }
  v15 = *(_QWORD *)(BugCheckParameter3 + 16);
  v16 = *(_QWORD *)(v12 + 184);
  v17 = 0;
  v83 = 0;
  v18 = 0;
  v89 = 0;
  LOBYTE(v11) = 0;
  v86 = 0;
  v78 = 0;
  v19 = *(_QWORD *)(v16 + 8);
  v20 = HIDWORD(*(_QWORD *)(v15 + 136));
  LOBYTE(v20) = v20 & 1;
  v21 = v19;
  v85 = v16;
  v81 = 0;
  v90 = v15;
  v82 = v20;
  v77 = 0;
  v80 = v19;
  if ( v19 == 0x8765432100000003uLL )
  {
    v22 = *(_QWORD *)(v16 + 24);
  }
  else
  {
    v22 = 0;
    if ( v19 == 0xFEDCBA9000000000uLL )
    {
      v17 = *(_QWORD *)(v16 + 24);
      v81 = v17;
    }
    else
    {
      v80 = v19;
    }
  }
  result = (unsigned int)(*(_DWORD *)(BugCheckParameter3 + 96) - 5);
  if ( (unsigned int)result <= 1 )
  {
    v78 = 1;
    v23 = -1073741810;
    goto LABEL_40;
  }
  LOBYTE(v79) = *(_BYTE *)v16;
  v11 = (unsigned __int8)v79;
  v76 = (_BYTE)v79 == 3;
  if ( !v22 )
  {
    v37 = *(_DWORD *)(*(_QWORD *)(v15 + 128) + 208LL);
    LODWORD(v84) = v37;
    if ( (_BYTE)v20 )
    {
      v38 = *(_QWORD *)(v16 + 24);
      goto LABEL_84;
    }
    if ( v17 )
    {
      v38 = *(_QWORD *)(v17 + 96);
      LODWORD(v19) = *(_DWORD *)(v17 + 116);
      *(_QWORD *)(v17 + 64) = 0;
      *(_QWORD *)(v17 + 72) = 0;
LABEL_84:
      v15 = *(unsigned int *)(BugCheckParameter3 + 64);
      result = (unsigned int)v19 / (unsigned int)v15;
      if ( (unsigned int)v19 % (unsigned int)v15
        || (result = v38 / v15, v59 = v38 / v15, v38 % v15)
        || (v60 = *(_QWORD *)(BugCheckParameter3 + 432), result >= v60)
        || (result = (unsigned int)v19 / (unsigned int)v15, v88 = result, v60 - v59 < (unsigned int)result) )
      {
        LOBYTE(v11) = 0;
        v23 = -1073741811;
        v18 = 0;
        goto LABEL_40;
      }
      v61 = *(_QWORD *)(BugCheckParameter3 + 16);
      v85 = v61;
      if ( (unsigned int)v19 <= *(_DWORD *)(*(_QWORD *)(v61 + 128) + 208LL) )
      {
        v62 = *(_DWORD *)(BugCheckParameter3 + 428);
        if ( !v62 )
        {
LABEL_96:
          NVMePrpListBufferEntry = 0;
          if ( (((unsigned int)v19
               + ((*(_DWORD *)(*(_QWORD *)(v12 + 8) + 32LL) + *(_DWORD *)(*(_QWORD *)(v12 + 8) + 44LL)) & 0xFFF)
               + 4095LL)
              & 0xFFFFFFFFFFFFF000uLL) <= 0x2000
            || (NVMePrpListBufferEntry = GetNVMePrpListBufferEntry(v61, (unsigned int)v3, v61, 0)) != 0
            || (NVMePrpListBufferEntry = AllocateNewNVMePrpListBufferEntry(
                                           *(_QWORD *)(BugCheckParameter3 + 16),
                                           (unsigned int)v3)) != 0 )
          {
            v66 = *(_QWORD *)(BugCheckParameter3 + 16);
            if ( (*(_BYTE *)(v66 + 136) & 2) != 0 )
              v67 = *(_QWORD *)(v66 + 728) + 192 * v3;
            else
              v67 = 192LL * *(unsigned __int16 *)(*(_QWORD *)(v66 + 872) + 2 * v3) + *(_QWORD *)(v66 + 728) - 192LL;
            LOBYTE(v71[0]) = 0;
            result = NvmeSubmitIoToSQ(
                       BugCheckParameter3,
                       v12,
                       v67,
                       NVMePrpListBufferEntry,
                       v3,
                       v71[0],
                       v19,
                       v38,
                       v59,
                       v88,
                       v76,
                       0);
            LOBYTE(v11) = 0;
            v23 = result;
            v18 = 0;
          }
          else
          {
            result = NvmeNamespaceQueueIo(BugCheckParameter3, v12, (unsigned int)v3);
            LOBYTE(v11) = 0;
            v23 = -2147483631;
            v18 = 0;
          }
          goto LABEL_40;
        }
        if ( (unsigned int)v19 <= v62 )
        {
          v63 = *(_BYTE *)(BugCheckParameter3 + 427);
          if ( v63 )
            v64 = ((unsigned __int64)(unsigned int)v19 >> v63)
                + ((((v62 - 1) & (unsigned int)v19) + ((v62 - 1) & (unsigned int)v38) + (unsigned __int64)v62 - 1) >> v63);
          else
            v64 = (unsigned int)v19 / v62 + ((unsigned int)v19 % v62 - 1LL + v62 + v38 % v62) / v62;
          if ( v64 <= 1 )
          {
            v61 = v85;
            goto LABEL_96;
          }
          v37 = v84;
        }
      }
      result = NvmeSplitIoParallel(BugCheckParameter3, v12, v38, v37, v3, 0, 0, 0);
      LOBYTE(v11) = 0;
      v23 = result;
      v18 = 0;
      goto LABEL_40;
    }
    v39 = *(unsigned int *)(BugCheckParameter3 + 64);
    if ( (unsigned int)v19 % (unsigned int)v39
      || (v40 = *(_QWORD *)(v16 + 24), v82 = v40 / v39, v41 = v40 / v39, v40 % v39)
      || (v42 = *(_QWORD *)(BugCheckParameter3 + 432), v40 / v39 >= v42)
      || (v88 = v21 / (unsigned int)v39, v42 - v82 < v88) )
    {
      v23 = -1073741811;
      goto LABEL_111;
    }
    if ( v21 <= v37 )
    {
      v43 = *(_DWORD *)(BugCheckParameter3 + 428);
      if ( !v43 )
        goto LABEL_71;
      if ( v21 <= v43 )
      {
        v44 = *(_BYTE *)(BugCheckParameter3 + 427);
        if ( v44 )
        {
          v41 = *(unsigned __int8 *)(BugCheckParameter3 + 427);
          v39 = (v43 - 1) & (unsigned int)v40;
          v45 = ((unsigned __int64)v21 >> v44) + (((v21 & (v43 - 1)) + v39 + v43 - 1LL) >> v44);
        }
        else
        {
          v41 = v21 / (unsigned __int64)v43;
          v39 = v21 % (unsigned __int64)v43;
          v45 = v21 / v43 + (v21 % v43 + v43 + v40 % v43 - 1) / v43;
        }
        if ( v45 <= 1 )
        {
LABEL_71:
          NVMeSGLBufferContext = GetNVMeSGLBufferContext(v90, (unsigned int)v3, v39, v41);
          v81 = NVMeSGLBufferContext;
          v47 = NVMeSGLBufferContext;
          if ( NVMeSGLBufferContext )
          {
            v48 = (_BYTE)v79 == 3;
            *(_QWORD *)(NVMeSGLBufferContext + 40) = v12;
            v49 = *(_BYTE *)(NVMeSGLBufferContext + 126) & 0xFE;
            *(_QWORD *)(v47 + 96) = v40;
            *(_QWORD *)(v47 + 32) = BugCheckParameter3;
            *(_QWORD *)(v47 + 104) = v82;
            *(_DWORD *)(v47 + 112) = v88;
            *(_BYTE *)(v47 + 126) = v49 | v48;
            v50 = v85;
            *(_QWORD *)(v47 + 64) = 0;
            *(_QWORD *)(v47 + 72) = 0;
            *(_DWORD *)(v47 + 116) = v21;
            *(_QWORD *)(v47 + 56) = *(_QWORD *)(v50 + 24);
            v51 = *(_QWORD *)(v50 + 8);
            *(_QWORD *)(v50 + 24) = v47;
            *(_QWORD *)(v47 + 48) = v51;
            *(_QWORD *)(v50 + 8) = 0xFEDCBA9000000000uLL;
            v52 = *(unsigned __int16 *)(v47 + 124);
            v53 = *(_QWORD *)(v47 + 16);
            v85 = *(unsigned int *)(*(_QWORD *)(v12 + 8) + 44LL) + *(_QWORD *)(*(_QWORD *)(v12 + 8) + 32LL);
            *(_QWORD *)(v47 + 80) = v85;
            v84 = *(_QWORD *)(v12 + 8);
            v82 = *(_QWORD *)(BugCheckParameter3 + 16);
            v54 = KfRaiseIrql(2u);
            LODWORD(v75) = v52;
            v55 = v85;
            v74 = v53;
            v56 = *(_QWORD *)(v82 + 128);
            v17 = v81;
            LOBYTE(v73) = (_BYTE)v79 != 3;
            v76 = v54;
            v57 = *(_QWORD *)(v56 + 1160);
            v58 = *(_QWORD *)(v56 + 8);
            *(_QWORD *)v72 = v81;
            LOBYTE(v79) = (_BYTE)v79 != 3;
            v23 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned __int64, __int64, unsigned int, __int64 (__fastcall *)(__int64, __int64, __int64, __int64), __int64, _DWORD, __int64, _DWORD))(*(_QWORD *)(v57 + 8) + 112LL))(
                    v57,
                    v58,
                    v84,
                    v85,
                    v21,
                    NvmeContinueScatterGatherProcessIO,
                    v81,
                    v73,
                    v74,
                    v75);
            if ( v23 == -1073741789 )
            {
              LOBYTE(v73) = v79;
              v23 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, unsigned __int64, __int64, int, __int64 (__fastcall *)(__int64, __int64, __int64, __int64), __int64, _DWORD))(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v82 + 128) + 1160LL) + 8LL) + 88LL))(
                      *(_QWORD *)(*(_QWORD *)(v82 + 128) + 1160LL),
                      *(_QWORD *)(*(_QWORD *)(v82 + 128) + 8LL),
                      v84,
                      v55,
                      v80,
                      NvmeContinueScatterGatherProcessIO,
                      v17,
                      v73);
            }
            if ( v76 < 2u )
              KeLowerIrql(v76);
            result = 259;
            if ( v23 >= 0 )
              v23 = 259;
            goto LABEL_46;
          }
          v23 = -1073741670;
LABEL_111:
          if ( (*(_BYTE *)(v12 + 151) & 1) != 0 )
            _InterlockedDecrement(*(volatile signed __int32 **)(*(_QWORD *)(BugCheckParameter3 + 696) + 8 * v3));
          *(_DWORD *)(v12 + 48) = v23;
          IofCompleteRequest((PIRP)v12, 0);
          result = *(_QWORD *)(BugCheckParameter3 + 128);
          if ( !*(_BYTE *)result )
          {
            result = (unsigned int)_InterlockedExchangeAdd(
                                     *(volatile signed __int32 **)(*(_QWORD *)(result + 24) + 8 * v3),
                                     0xFFFFFFFF);
            if ( (_DWORD)result == 1 )
            {
              v68 = *(_QWORD *)(*(_QWORD *)(BugCheckParameter3 + 16) + 128LL);
              result = NvmeNamespaceCheckAndAcquirePoFx(BugCheckParameter3);
              if ( (_BYTE)result )
              {
                PoFxIdleComponent(**(_QWORD **)(*(_QWORD *)(BugCheckParameter3 + 128) + 8LL), 0, 2);
                result = NvmeNamespaceReleasePoFx(BugCheckParameter3);
              }
              v69 = *(_QWORD *)(v68 + 168);
              if ( *(_BYTE *)v69 == 1 )
                return PoFxIdleComponent(**(_QWORD **)(v69 + 8), 0, 2);
            }
          }
          return result;
        }
        v37 = v84;
      }
    }
    result = NvmeSplitIoParallel(BugCheckParameter3, v12, v40, v37, v3, 0, 0, 0);
    v23 = result;
    goto LABEL_46;
  }
  v23 = 0;
  v24 = 0;
  v25 = 0;
  v76 = 0;
  v80 = 0;
  if ( !(_BYTE)v20 )
  {
    _InterlockedIncrement16((volatile signed __int16 *)(v22 + 120));
    v77 = 1;
  }
  v15 = 4;
  v11 = 3;
LABEL_18:
  v26 = v22;
  while ( 1 )
  {
    v84 = *(_QWORD *)(v26 + 96);
    v79 = *(_WORD *)(v26 + 34);
    v27 = _InterlockedCompareExchange((volatile signed __int32 *)(v26 + 104), 4, 3);
    if ( (_BYTE)v20 )
    {
      if ( v27 != 3 && _InterlockedCompareExchange((volatile signed __int32 *)(v26 + 104), 4, 1) != 1 )
        goto LABEL_32;
    }
    else if ( v27 != 3 )
    {
      if ( *(_DWORD *)(v26 + 104) == 1 )
        ++v25;
      goto LABEL_32;
    }
    result = NvmeSendSplitIo(v26, v3, 0, 0, (bool *)&v78, &v89, &v86, &v83, v24);
    v23 = result;
    if ( (_DWORD)result != 259 )
      break;
    HIWORD(v28) = HIWORD(v80);
    LOWORD(v28) = v80 + 1;
    v29 = (unsigned __int16)(v80 + 1)
        % (unsigned int)*(unsigned __int8 *)(*(_QWORD *)(BugCheckParameter3 + 16) + 1730LL);
    v80 = v28;
    v24 = v29 == 0;
    v76 = v29 == 0;
LABEL_31:
    LOBYTE(v20) = v82;
    v11 = 3;
    v15 = 4;
LABEL_32:
    result = v84;
    v26 = v84;
    if ( v25 )
    {
      if ( !v84 )
      {
        v25 = 0;
        goto LABEL_18;
      }
    }
    else if ( !v84 )
    {
      LOBYTE(v11) = 1;
      goto LABEL_39;
    }
  }
  if ( (_DWORD)result != -2147483631 )
  {
    if ( !v79 )
    {
      v78 = 1;
LABEL_38:
      LOBYTE(v11) = 0;
      goto LABEL_39;
    }
    if ( v78 )
      goto LABEL_38;
    v24 = v76;
    goto LABEL_31;
  }
  _InterlockedCompareExchange((volatile signed __int32 *)(v26 + 104), 3, 4);
  result = NvmeNamespaceQueueIo(BugCheckParameter3, *(_QWORD *)(v26 + 24), (unsigned int)v3);
  LOBYTE(v11) = 1;
LABEL_39:
  v18 = v77;
LABEL_40:
  if ( !(_BYTE)v82 && v18 )
    _InterlockedDecrement16((volatile signed __int16 *)(v22 + 120));
  v17 = v81;
  if ( !(_BYTE)v11 && v22 )
    _interlockedbittestandreset((volatile signed __int32 *)(v22 + 108), 0);
LABEL_46:
  if ( v23 != -2147483631 && v23 < 1 )
  {
    if ( v17 )
    {
      v30 = *(_QWORD *)(v17 + 24);
      if ( v30 )
      {
        v31 = *(_BYTE *)(v17 + 126) & 1;
        v32 = *(_QWORD *)(*(_QWORD *)(BugCheckParameter3 + 16) + 128LL);
        v33 = KfRaiseIrql(2u);
        v34 = *(_QWORD *)(v32 + 1160);
        LOBYTE(v79) = v33;
        (*(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)(v34 + 8) + 96LL))(v34, v30, v31 ^ 1u);
        if ( (unsigned __int8)v79 < 2u )
          KeLowerIrql(v79);
        v17 = v81;
      }
      v35 = *(_QWORD *)(v17 + 88);
      if ( v35 )
      {
        v36 = *(_QWORD *)(BugCheckParameter3 + 16);
        *(_QWORD *)(v35 + 88) = 0;
        *(_DWORD *)(v35 + 108) = 0;
        *(_DWORD *)(v35 + 104) = 0;
        ExpInterlockedPushEntrySList(*(PSLIST_HEADER *)(*(_QWORD *)(v36 + 888) + 8 * v3), (PSLIST_ENTRY)v35);
      }
      LOBYTE(v15) = 1;
      FreeNVMeSGLBufferContext(*(_QWORD *)(BugCheckParameter3 + 16), v17, v15);
      goto LABEL_111;
    }
    if ( !v22 )
      goto LABEL_111;
    if ( v78 )
    {
      FreeAllSglAndContextInChainedSplitIoContext(*(_QWORD *)(BugCheckParameter3 + 16), v22, v15, v11);
      FreeNVMeChainedIoSplitContext(*(_QWORD *)(BugCheckParameter3 + 16), (unsigned int)v3, v22, v12);
      goto LABEL_111;
    }
  }
  return result;
}

```

## disassembly

```asm
0x140051870  push    rbp
0x140051872  push    rbx
0x140051873  push    rsi
0x140051874  push    rdi
0x140051875  push    r15
0x140051877  lea     rbp, [rsp-37h]
0x14005187c  sub     rsp, 100h
0x140051883  mov     rax, cs:__security_cookie
0x14005188a  xor     rax, rsp
0x14005188d  mov     [rbp+57h+var_40], rax
0x140051891  xor     eax, eax
0x140051893  mov     r15d, r8d
0x140051896  mov     [rbp+57h+var_80], rax
0x14005189a  mov     rdi, rdx
0x14005189d  mov     rax, [rdx+0B8h]
0x1400518a4  mov     rsi, rcx
0x1400518a7  lea     rdx, [rbp+57h+var_80]
0x1400518ab  mov     rcx, rdi
0x1400518ae  or      byte ptr [rax+3], 1
0x1400518b2  call    cs:__imp_IoGetIoAttributionHandle
0x1400518b9  nop     dword ptr [rax+rax+00h]
0x1400518be  test    eax, eax
0x1400518c0  js      short loc_140051912
0x1400518c2  mov     rax, [rdi+0B8h]
0x1400518c9  xorps   xmm0, xmm0
0x1400518cc  mov     rbx, [rbp+57h+var_80]
0x1400518d0  movups  [rbp+57h+var_60], xmm0
0x1400518d4  mov     dword ptr [rbp+57h+var_60], 1
0x1400518db  movups  xmmword ptr [rbp+57h+QpcTimeStamp], xmm0
0x1400518df  movzx   ecx, byte ptr [rax]
0x1400518e2  or      ecx, 300h
0x1400518e8  mov     dword ptr [rbp+57h+var_60+4], ecx
0x1400518eb  lea     rcx, [rbp+57h+QpcTimeStamp+8]; QpcTimeStamp
0x1400518ef  call    cs:__imp_KeQueryUnbiasedInterruptTimePrecise
0x1400518f6  nop     dword ptr [rax+rax+00h]
0x1400518fb  lea     rdx, [rbp+57h+var_60]
0x1400518ff  mov     rcx, rbx
0x140051902  mov     [rbp+57h+QpcTimeStamp+8], rax
0x140051906  call    cs:__imp_IoRecordIoAttribution
0x14005190d  nop     dword ptr [rax+rax+00h]
0x140051912  mov     rcx, [rsi+100h]
0x140051919  mov     r8, rdi
0x14005191c  mov     edx, r15d
0x14005191f  call    StorPushRequestToDeviceQueue
0x140051924  lock or [rsp+120h+var_120], 0
0x140051929  mov     rax, [rsi+80h]
0x140051930  cmp     byte ptr [rax+1], 1
0x140051934  jnz     short loc_140051944
0x140051936  mov     rax, [rax+8]
0x14005193a  cmp     byte ptr [rax+40h], 0
0x14005193e  jz      loc_140052379
0x140051944  mov     rax, [rsi+10h]
0x140051948  mov     [rsp+120h+var_28], r13
0x140051950  mov     rcx, [rax+520h]
0x140051957  mov     rbx, [rcx+28h]
0x14005195b  call    cs:__imp_KeQueryUnbiasedInterruptTime
0x140051962  nop     dword ptr [rax+rax+00h]
0x140051967  mov     [rbx], rax
0x14005196a  mov     edx, r15d
0x14005196d  mov     rcx, [rsi+100h]
0x140051974  call    StorPopRequestFromDeviceQueue
0x140051979  mov     r13, rax
0x14005197c  test    rax, rax
0x14005197f  jz      loc_140052371
0x140051985  mov     rdi, [rbp+57h+var_80]
0x140051989  test    rdi, rdi
0x14005198c  jz      short loc_1400519D8
0x14005198e  mov     rax, [rax+0B8h]
0x140051995  xorps   xmm0, xmm0
0x140051998  movups  [rbp+57h+var_60], xmm0
0x14005199c  mov     dword ptr [rbp+57h+var_60], 1
0x1400519a3  movups  xmmword ptr [rbp+57h+QpcTimeStamp], xmm0
0x1400519a7  movzx   ecx, byte ptr [rax]
0x1400519aa  bts     ecx, 9
0x1400519ae  mov     dword ptr [rbp+57h+var_60+4], ecx
0x1400519b1  lea     rcx, [rbp+57h+QpcTimeStamp+8]; QpcTimeStamp
0x1400519b5  call    cs:__imp_KeQueryUnbiasedInterruptTimePrecise
0x1400519bc  nop     dword ptr [rax+rax+00h]
0x1400519c1  lea     rdx, [rbp+57h+var_60]
0x1400519c5  mov     rcx, rdi
0x1400519c8  mov     [rbp+57h+QpcTimeStamp+8], rax
0x1400519cc  call    cs:__imp_IoRecordIoAttribution
0x1400519d3  nop     dword ptr [rax+rax+00h]
0x1400519d8  mov     r8, [rsi+10h]
0x1400519dc  xor     eax, eax
0x1400519de  mov     rcx, [r13+0B8h]
0x1400519e5  xor     edi, edi
0x1400519e7  mov     [rbp+57h+var_A0], ax
0x1400519eb  xor     r10b, r10b
0x1400519ee  mov     [rbp+57h+var_70], rax
0x1400519f2  xor     r9b, r9b
0x1400519f5  mov     [rbp+57h+var_88], eax
0x1400519f8  mov     r11, 0FEDCBA9000000000h
0x140051a02  mov     [rbp+57h+var_BE], dil
0x140051a06  mov     rax, 8765432100000003h
0x140051a10  mov     rbx, [rcx+8]
0x140051a14  mov     rdx, [r8+88h]
0x140051a1b  shr     rdx, 20h
0x140051a1f  and     dl, 1
0x140051a22  mov     [rsp+120h+arg_18], r12
0x140051a2a  mov     [rsp+120h+var_30], r14
0x140051a32  mov     r14d, ebx
0x140051a35  mov     [rbp+57h+var_90], rcx
0x140051a39  mov     [rbp+57h+var_B0], rdi
0x140051a3d  mov     [rbp+57h+var_68], r8
0x140051a41  mov     [rbp+57h+var_A8], rdx
0x140051a45  mov     [rbp+57h+var_BF], r10b
0x140051a49  mov     [rbp+57h+var_B8], ebx
0x140051a4c  cmp     rbx, rax
0x140051a4f  jnz     short loc_140051A57
0x140051a51  mov     r12, [rcx+18h]
0x140051a55  jmp     short loc_140051A6C
0x140051a57  xor     r12d, r12d
0x140051a5a  cmp     rbx, r11
0x140051a5d  jnz     short loc_140051A69
0x140051a5f  mov     rdi, [rcx+18h]
0x140051a63  mov     [rbp+57h+var_B0], rdi
0x140051a67  jmp     short loc_140051A6C
0x140051a69  mov     [rbp+57h+var_B8], ebx
0x140051a6c  mov     eax, [rsi+60h]
0x140051a6f  sub     eax, 5
0x140051a72  cmp     eax, 1
0x140051a75  jbe     loc_14005226E
0x140051a7b  movzx   r9d, byte ptr [rcx]
0x140051a7f  cmp     r9b, 3
0x140051a83  mov     byte ptr [rbp+57h+var_BC], r9b
0x140051a87  setz    [rbp+57h+var_C0]
0x140051a8b  test    r12, r12
0x140051a8e  jz      loc_140051CF9
0x140051a94  xor     r14d, r14d
0x140051a97  xor     cl, cl
0x140051a99  xor     edi, edi
0x140051a9b  mov     [rbp+57h+var_C0], cl
0x140051a9e  mov     [rbp+57h+var_B8], r14d
0x140051aa2  test    dl, dl
0x140051aa4  jnz     short loc_140051AB1
0x140051aa6  lock inc word ptr [r12+78h]
0x140051aad  mov     [rbp+57h+var_BF], 1
0x140051ab1  mov     r8d, 4
0x140051ab7  mov     r9d, 3
0x140051abd  mov     rbx, r12
0x140051ac0  mov     rax, [rbx+60h]
0x140051ac4  mov     [rbp+57h+var_98], rax
0x140051ac8  movzx   eax, word ptr [rbx+22h]
0x140051acc  mov     [rbp+57h+var_BC], ax
0x140051ad0  mov     eax, r9d
0x140051ad3  lock cmpxchg [rbx+68h], r8d
0x140051ad9  test    dl, dl
0x140051adb  jnz     short loc_140051AF6
0x140051add  cmp     eax, 3
0x140051ae0  jz      short loc_140051B0C
0x140051ae2  mov     eax, [rbx+68h]
0x140051ae5  cmp     eax, 1
0x140051ae8  jnz     loc_140051BA6
0x140051aee  inc     di
0x140051af1  jmp     loc_140051BA6
0x140051af6  cmp     eax, 3
0x140051af9  jz      short loc_140051B0C
0x140051afb  mov     eax, 1
0x140051b00  lock cmpxchg [rbx+68h], r8d
0x140051b06  jnz     loc_140051BA6
0x140051b0c  mov     byte ptr [rsp+120h+var_E0], cl
0x140051b10  lea     rax, [rbp+57h+var_A0]
0x140051b14  mov     [rsp+120h+var_E8], rax
0x140051b19  xor     r9d, r9d
0x140051b1c  lea     rax, [rbp+57h+var_88]
0x140051b20  xor     r8d, r8d
0x140051b23  mov     qword ptr [rsp+120h+var_F0], rax
0x140051b28  mov     edx, r15d
0x140051b2b  lea     rax, [rbp+57h+var_70]
0x140051b2f  mov     rcx, rbx
0x140051b32  mov     qword ptr [rsp+120h+var_F8], rax
0x140051b37  lea     rax, [rbp+57h+var_BE]
0x140051b3b  mov     [rsp+120h+var_100], rax
0x140051b40  call    NvmeSendSplitIo
0x140051b45  mov     r14d, eax
0x140051b48  cmp     eax, 103h
0x140051b4d  jnz     short loc_140051B7A
0x140051b4f  mov     rcx, [rsi+10h]
0x140051b53  xor     edx, edx
0x140051b55  mov     r9d, [rbp+57h+var_B8]
0x140051b59  inc     r9w
0x140051b5d  movzx   eax, r9w
0x140051b61  movzx   r8d, byte ptr [rcx+6C2h]
0x140051b69  div     r8d
0x140051b6c  mov     [rbp+57h+var_B8], r9d
0x140051b70  test    edx, edx
0x140051b72  setz    cl
0x140051b75  mov     [rbp+57h+var_C0], cl
0x140051b78  jmp     short loc_140051B96
0x140051b7a  cmp     eax, 80000011h
0x140051b7f  jz      loc_140051CD3
0x140051b85  cmp     [rbp+57h+var_BC], 0
0x140051b8a  jz      short loc_140051BD1
0x140051b8c  cmp     [rbp+57h+var_BE], 0
0x140051b90  jnz     short loc_140051BD5
0x140051b92  movzx   ecx, [rbp+57h+var_C0]
0x140051b96  mov     rdx, [rbp+57h+var_A8]
0x140051b9a  mov     r9d, 3
0x140051ba0  mov     r8d, 4
0x140051ba6  mov     rax, [rbp+57h+var_98]
0x140051baa  mov     rbx, rax
0x140051bad  test    di, di
0x140051bb0  jz      short loc_140051BC3
0x140051bb2  test    rax, rax
0x140051bb5  jnz     loc_140051AC0
0x140051bbb  movzx   edi, ax
0x140051bbe  jmp     loc_140051ABD
0x140051bc3  test    rax, rax
0x140051bc6  jnz     loc_140051AC0
0x140051bcc  mov     r9b, 1
0x140051bcf  jmp     short loc_140051BD8
0x140051bd1  mov     [rbp+57h+var_BE], 1
0x140051bd5  xor     r9b, r9b
0x140051bd8  movzx   r10d, [rbp+57h+var_BF]
0x140051bdd  cmp     byte ptr [rbp+57h+var_A8], 0
0x140051be1  jnz     short loc_140051BEF
0x140051be3  test    r10b, r10b
0x140051be6  jz      short loc_140051BEF
0x140051be8  lock dec word ptr [r12+78h]
0x140051bef  mov     rdi, [rbp+57h+var_B0]
0x140051bf3  test    r9b, r9b
0x140051bf6  jnz     short loc_140051C05
0x140051bf8  test    r12, r12
0x140051bfb  jz      short loc_140051C05
0x140051bfd  lock btr dword ptr [r12+6Ch], 0
0x140051c05  cmp     r14d, 80000011h
0x140051c0c  jz      loc_140052361
0x140051c12  cmp     r14d, 1
0x140051c16  jge     loc_140052361
0x140051c1c  test    rdi, rdi
0x140051c1f  jz      loc_14005227D
0x140051c25  mov     r12, [rdi+18h]
0x140051c29  test    r12, r12
0x140051c2c  jz      short loc_140051C8F
0x140051c2e  mov     rax, [rsi+10h]
0x140051c32  mov     cl, 2; NewIrql
0x140051c34  movzx   edi, byte ptr [rdi+7Eh]
0x140051c38  and     dil, 1
0x140051c3c  mov     rbx, [rax+80h]
0x140051c43  call    cs:__imp_KfRaiseIrql
0x140051c4a  nop     dword ptr [rax+rax+00h]
0x140051c4f  mov     r9, [rbx+488h]
0x140051c56  xor     dil, 1
0x140051c5a  mov     byte ptr [rbp+57h+var_BC], al
0x140051c5d  movzx   r8d, dil
0x140051c61  mov     rdx, r12
0x140051c64  mov     rcx, [r9+8]
0x140051c68  mov     rax, [rcx+60h]
0x140051c6c  mov     rcx, r9
0x140051c6f  call    _guard_dispatch_icall
0x140051c74  movzx   eax, byte ptr [rbp+57h+var_BC]
0x140051c78  cmp     al, 2
0x140051c7a  jnb     short loc_140051C8B
0x140051c7c  movzx   ecx, al; NewIrql
0x140051c7f  call    cs:__imp_KeLowerIrql
0x140051c86  nop     dword ptr [rax+rax+00h]
0x140051c8b  mov     rdi, [rbp+57h+var_B0]
0x140051c8f  mov     rdx, [rdi+58h]; ListEntry
0x140051c93  test    rdx, rdx
0x140051c96  jz      short loc_140051CBF
0x140051c98  mov     rcx, [rsi+10h]
0x140051c9c  xor     eax, eax
0x140051c9e  mov     [rdx+58h], rax
0x140051ca2  mov     [rdx+6Ch], eax
0x140051ca5  mov     [rdx+68h], eax
0x140051ca8  mov     rcx, [rcx+378h]
0x140051caf  mov     rcx, [rcx+r15*8]; ListHead
0x140051cb3  call    cs:__imp_ExpInterlockedPushEntrySList
0x140051cba  nop     dword ptr [rax+rax+00h]
0x140051cbf  mov     rcx, [rsi+10h]
0x140051cc3  mov     r8b, 1
0x140051cc6  mov     rdx, rdi
0x140051cc9  call    FreeNVMeSGLBufferContext
0x140051cce  jmp     loc_1400522AA
0x140051cd3  mov     eax, 4
0x140051cd8  mov     ecx, 3
0x140051cdd  lock cmpxchg [rbx+68h], ecx
0x140051ce2  mov     rdx, [rbx+18h]
0x140051ce6  mov     r8d, r15d
0x140051ce9  mov     rcx, rsi
0x140051cec  call    NvmeNamespaceQueueIo
0x140051cf1  mov     r9b, 1
0x140051cf4  jmp     loc_140051BD8
0x140051cf9  mov     rax, [r8+80h]
0x140051d00  mov     r10d, [rax+0D0h]
0x140051d07  mov     dword ptr [rbp+57h+var_98], r10d
0x140051d0b  test    dl, dl
0x140051d0d  jnz     loc_140052018
0x140051d13  test    rdi, rdi
0x140051d16  jz      short loc_140051D34
0x140051d18  mov     r14, [rdi+60h]
0x140051d1c  mov     ebx, [rdi+74h]
0x140051d1f  mov     qword ptr [rdi+40h], 0
0x140051d27  mov     qword ptr [rdi+48h], 0
0x140051d2f  jmp     loc_14005201C
0x140051d34  mov     r8d, [rsi+40h]
0x140051d38  xor     edx, edx
0x140051d3a  mov     eax, r14d
0x140051d3d  div     r8d
  ... truncated ...
```
