# Smb2CloseFileInternalAndReleaseSpinLock

- ea: `0x14000cdf0`
- end: `0x14000df9e`
- name: `Smb2CloseFileInternalAndReleaseSpinLock`
- size: `4526`
- prototype: `__int64 __usercall@<rax>(PVOID P@<rcx>, PKLOCK_QUEUE_HANDLE)`
- caller_count: `3`
- callee_count: `22`
- tags: `file_ops`

## callers

- `0x14000c4bc`
- `0x14000c8e0`
- `0x140017240`

## callees

- `0x140004960`
- `0x140004df4`
- `0x140005070`
- `0x14000c520`
- `0x14000cdf0`
- `0x14000e140`
- `0x14000e340`
- `0x14002143c`
- `0x140021b20`
- `0x1400222ec`
- `0x140022690`
- `0x140022958`
- `0x140022a10`
- `0x140028d34`
- `0x14002dca4`
- `0x14002dd28`
- `0x14002fc70`
- `0x140038490`
- `0x14006e6d0`
- `0x1400770c8`
- `0x1400809c0`
- `0x140091cc0`

## import_xrefs

- `ntoskrnl!KeBugCheckEx` at `0x14000ddd1`
- `ntoskrnl!KeBugCheckEx` at `0x14000ddd1`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14000dbbb`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14000dc49`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14000dcda`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14000dd68`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14000dbbb`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14000dc49`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14000dcda`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14000dd68`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000cf16`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000d436`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000d702`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000cf16`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000d436`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000d702`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000d908`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000de5c`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000df48`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000df79`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000d908`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000de5c`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000df48`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000df79`
- `ntoskrnl!KeSetEvent` at `0x14000ce70`
- `ntoskrnl!KeSetEvent` at `0x14000ce70`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000d021`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000d75b`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000d934`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000db37`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000d021`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000d75b`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000d934`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000db37`
- `ntoskrnl!RtlCaptureStackBackTrace` at `0x14003b141`
- `ntoskrnl!RtlCaptureStackBackTrace` at `0x14003b1ee`
- `ntoskrnl!RtlCaptureStackBackTrace` at `0x14003b33e`
- `ntoskrnl!RtlCaptureStackBackTrace` at `0x14003b141`
- `ntoskrnl!RtlCaptureStackBackTrace` at `0x14003b1ee`
- `ntoskrnl!RtlCaptureStackBackTrace` at `0x14003b33e`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14000dbd6`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14000dc64`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14000dcf6`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14000dd83`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14000dbd6`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14000dc64`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14000dcf6`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14000dd83`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000d947`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000d970`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000dacf`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000daf5`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000db1d`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000d947`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000d970`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000dacf`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000daf5`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000db1d`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000d678`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000d95d`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000dab9`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000dae2`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000db0a`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000d678`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000d95d`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000dab9`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000dae2`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000db0a`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000d0bb`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000d8f7`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000d0bb`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000d8f7`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000cf06`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000d0f9`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000d658`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000cf06`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000d0f9`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000d658`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x14000d135`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x14000d2b1`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x14000d5ba`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x14000d807`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x14000da51`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x14000d135`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x14000d2b1`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x14000d5ba`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x14000d807`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x14000da51`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14000d20a`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14000d306`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14000d61e`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14000d85e`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14000daa6`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14000d20a`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14000d306`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14000d61e`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14000d85e`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14000daa6`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14000cf60`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14000cf60`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14000d00d`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14000d00d`
- `srvnet!SrvLibFilePowerManagementClose` at `0x14000d3db`
- `srvnet!SrvLibFilePowerManagementClose` at `0x14000d3db`

## string_xrefs

- `0x14000db9c`: `Srv2PostToThreadPool`
- `0x14000dc2a`: `Srv2PostToThreadPool`
- `0x14000dcba`: `Srv2PostToThreadPool`
- `0x14000dd49`: `Srv2PostToThreadPool`

## pseudocode

```c
void __fastcall Smb2CloseFileInternalAndReleaseSpinLock(
        char *P,
        char a2,
        __int64 a3,
        __int64 a4,
        PKLOCK_QUEUE_HANDLE a5)
{
  bool v5; // zf
  struct _KLOCK_QUEUE_HANDLE *v7; // rdi
  __int64 v9; // rcx
  char v10; // r12
  __int64 v11; // r14
  __int64 v12; // rdi
  signed __int64 v13; // r15
  struct _KLOCK_QUEUE_HANDLE *v14; // r15
  _QWORD *v15; // rax
  __int64 v16; // rdx
  _QWORD *v17; // rcx
  __int64 v18; // r15
  _QWORD *v19; // rdx
  signed __int64 v20; // rax
  __int64 v21; // r14
  unsigned int v22; // r12d
  __int64 v23; // rdi
  KIRQL v24; // r11
  unsigned __int64 v25; // r8
  unsigned int i; // r9d
  unsigned int v27; // eax
  __int64 v28; // rdx
  int v29; // eax
  _DWORD **v30; // rdx
  int v31; // eax
  int v32; // ecx
  int v33; // r9d
  int v34; // r10d
  int v35; // r8d
  int v36; // eax
  int *v37; // rcx
  _QWORD *v38; // rdi
  __int64 v39; // r12
  __int64 v40; // r13
  KIRQL v41; // dl
  _QWORD *v42; // rax
  _QWORD *v43; // rcx
  signed __int64 v44; // rcx
  volatile signed __int64 *v45; // rcx
  signed __int64 v46; // rax
  signed __int64 v47; // rdi
  __int64 v48; // rdi
  KIRQL v49; // al
  KIRQL v50; // bl
  int v51; // ecx
  signed __int64 v52; // rsi
  signed __int64 v53; // rdi
  __int64 v54; // r14
  __m128i v55; // xmm2
  __m128i v56; // xmm2
  __int64 v57; // rdi
  KIRQL v58; // r15
  unsigned int v59; // ecx
  char **v60; // rdx
  __int64 v61; // r8
  char *v62; // rcx
  __int64 *v63; // rdx
  _QWORD *v64; // rcx
  __int64 v65; // r14
  __int64 v66; // r12
  KIRQL v67; // al
  _QWORD *v68; // rdx
  KIRQL v69; // r9
  __int64 v70; // r8
  _QWORD *v71; // rax
  _QWORD *v72; // rbx
  __int64 v73; // r14
  KIRQL v74; // dl
  _QWORD *v75; // rax
  _QWORD *v76; // rcx
  __int64 v77; // rax
  signed __int64 v78; // rax
  __int64 v79; // rdx
  __int64 v80; // rdx
  __int64 v81; // r8
  _QWORD *v82; // rdi
  __int64 v83; // r12
  KIRQL v84; // dl
  _QWORD *v85; // rax
  _QWORD *v86; // rcx
  __int64 v87; // rax
  _QWORD *v88; // rcx
  __int64 v89; // rdi
  __int64 v90; // rdi
  __int64 v91; // rdi
  __int64 v92; // rdi
  __int64 v93; // rbx
  __int64 v94; // rbx
  __int64 v95; // rbx
  __int64 v96; // rbx
  int v97; // eax
  __int64 v98; // rdx
  __int64 v99; // rdx
  __int64 v100; // rdx
  struct _FILE_OBJECT *v101; // rdx
  __int64 v102; // rcx
  int v103; // eax
  ULONG_PTR BugCheckParameter4; // [rsp+28h] [rbp-81h]
  bool v105; // [rsp+68h] [rbp-41h]
  KIRQL v106; // [rsp+69h] [rbp-40h]
  char v107; // [rsp+6Ah] [rbp-3Fh]
  int v108; // [rsp+6Ch] [rbp-3Dh]
  int v109; // [rsp+70h] [rbp-39h] BYREF
  __int64 v110; // [rsp+78h] [rbp-31h]
  __int64 v111; // [rsp+80h] [rbp-29h]
  _BYTE LockHandle[12]; // [rsp+88h] [rbp-21h] BYREF
  _BYTE v113[32]; // [rsp+98h] [rbp-11h] BYREF
  __int64 v114; // [rsp+B8h] [rbp+Fh]

  v5 = *((_DWORD *)P + 3) == 221;
  v7 = a5;
  *(_QWORD *)LockHandle = a5;
  v111 = a4;
  v107 = a3;
  if ( !v5 )
    KeBugCheckEx(0x54u, (ULONG_PTR)"onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\smb2file.c", 0x8EDu, 0, 0);
  if ( *((_DWORD *)P + 217) || *((_DWORD *)P + 218) )
  {
    v53 = _InterlockedIncrement64((volatile signed __int64 *)P);
    if ( ((v53 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
      __int2c();
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0 )
    {
      memset(v113, 0, 24);
      RtlCaptureStackBackTrace(0, 3u, (PVOID *)v113, 0);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_qPPqqq(
          WPP_GLOBAL_Control->AttachedDevice,
          34,
          WPP_1eeac08a4da9393ddade0ba3ac297e5e_Traceguids,
          P,
          v53 - 1,
          v53,
          *(_QWORD *)v113,
          *(_QWORD *)&v113[8],
          *(_QWORD *)&v113[16]);
      }
    }
    *((_QWORD *)P + 115) = *((_QWORD *)P + 10);
    v9 = *(_QWORD *)(*((_QWORD *)P + 8) + 160LL);
    v54 = *(_QWORD *)(v9 + 2184);
    if ( v54 && P != (char *)-920LL )
    {
      v55 = _mm_add_epi32(
              _mm_unpacklo_epi16(_mm_unpacklo_epi8(_mm_cvtsi32_si128(*((_DWORD *)P + 231)), (__m128i)0LL), (__m128i)0LL),
              _mm_unpacklo_epi16(_mm_unpacklo_epi8(_mm_cvtsi32_si128(*((_DWORD *)P + 230)), (__m128i)0LL), (__m128i)0LL));
      v56 = _mm_add_epi32(v55, _mm_srli_si128(v55, 8));
      v57 = *(_QWORD *)(v54 + 56)
          + 32LL * ((unsigned int)_mm_cvtsi128_si32(_mm_add_epi32(v56, _mm_srli_si128(v56, 4))) % *(_DWORD *)v54);
      if ( (*(_DWORD *)(v57 + 12) & 1) != 0 )
      {
        v58 = ExAcquireSpinLockExclusive((PEX_SPIN_LOCK)v57);
      }
      else
      {
        v58 = 0;
        ExAcquirePushLockExclusiveEx(v57, 0);
      }
      v59 = *(_DWORD *)(v54 + 16);
      if ( _InterlockedIncrement((volatile signed __int32 *)(v54 + 8)) > v59 )
      {
        _InterlockedDecrement((volatile signed __int32 *)(v54 + 8));
      }
      else
      {
        ++*(_DWORD *)(v57 + 8);
        v60 = (char **)(v57 + 16);
        v61 = *(_QWORD *)(v57 + 16);
        if ( *(_QWORD *)(v61 + 8) != v57 + 16 )
          goto LABEL_215;
        v62 = &P[*(unsigned int *)(v54 + 4)];
        *(_QWORD *)v62 = v61;
        *((_QWORD *)v62 + 1) = v60;
        *(_QWORD *)(v61 + 8) = v62;
        *v60 = v62;
      }
      if ( (*(_DWORD *)(v57 + 12) & 1) != 0 )
        ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)v57, v58);
      else
        ExReleasePushLockExclusiveEx(v57, 0);
    }
    v7 = *(struct _KLOCK_QUEUE_HANDLE **)LockHandle;
  }
  else
  {
    KeSetEvent((PRKEVENT)(P + 880), 0, 0);
  }
  v108 = -1073741823;
  v110 = 0;
  v10 = 0;
  v106 = 0;
  v11 = 0;
  if ( !*((_QWORD *)P + 21) && (unsigned int)(*((_DWORD *)P + 70) - 3) <= 1 )
  {
    v79 = *((_QWORD *)P + 15);
    if ( v79 )
    {
      if ( !*(_BYTE *)(v79 + 104) )
      {
        if ( ((_InterlockedExchangeAdd64((volatile signed __int64 *)v79, 1u) + 2) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
          __int2c();
        Smb2AcknowledgeOplockBreakInternal(P, (PVOID)v79, v7);
        KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)P + 14, v7);
      }
    }
  }
  if ( a2 )
  {
    if ( (byte_14004C339 & 8) == 0 )
      goto LABEL_8;
    v63 = SMB2_EVENT_FILE_CLOSE;
  }
  else
  {
    if ( (byte_14004C339 & 8) == 0 )
      goto LABEL_8;
    v63 = SMB2_EVENT_FILE_SUSPEND;
  }
  McTemplateK0j_EtwWriteTransfer(v9, v63, a3, P + 96);
LABEL_8:
  v12 = *((_QWORD *)P + 21);
  if ( v12 )
  {
    v11 = *((_QWORD *)P + 21);
    v110 = v11;
    v13 = _InterlockedIncrement64((volatile signed __int64 *)v12);
    if ( ((v13 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
      __int2c();
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000000) != 0 )
    {
      v114 = 0;
      memset(v113, 0, sizeof(v113));
      RtlCaptureStackBackTrace(1u, 5u, (PVOID *)v113, 0);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_qPPqqqqq(
          WPP_GLOBAL_Control->AttachedDevice,
          13,
          WPP_3d8eb6e120b9357e636b6f5c4c47d988_Traceguids,
          v12,
          v13 - 1,
          v13,
          *(_QWORD *)v113,
          *(_QWORD *)&v113[8],
          *(_QWORD *)&v113[16],
          *(_QWORD *)&v113[24],
          v114);
      }
    }
    v14 = *(struct _KLOCK_QUEUE_HANDLE **)LockHandle;
    KeReleaseInStackQueuedSpinLock(*(PKLOCK_QUEUE_HANDLE *)LockHandle);
    v10 = 1;
    v106 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v12 + 96));
    v105 = *(_BYTE *)(v12 + 129) != 0;
    if ( *(_BYTE *)(v12 + 128) )
    {
      v108 = -1073741528;
    }
    else
    {
      ++*(_DWORD *)(v12 + 172);
      v108 = 0;
    }
    if ( P[242] )
    {
      v5 = (*(_DWORD *)(v12 + 252))-- == 1;
      if ( v5 )
      {
        v97 = 10000000 * Smb2OplockBreakTimeoutInSec;
        *(_BYTE *)(v12 + 133) = 0;
        *(_DWORD *)(v12 + 248) = v97;
      }
    }
    KeAcquireInStackQueuedSpinLockAtDpcLevel((PKSPIN_LOCK)P + 14, v14);
    if ( *((_QWORD *)P + 21) == v12 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        BugCheckParameter4 = *((_QWORD *)P + 21);
        WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 48, WPP_3d8eb6e120b9357e636b6f5c4c47d988_Traceguids);
      }
      Smb2DereferenceLease(*((PVOID *)P + 21));
      v15 = P + 416;
      *((_QWORD *)P + 21) = 0;
      v16 = *((_QWORD *)P + 52);
      if ( *(char **)(v16 + 8) != P + 416 )
        goto LABEL_215;
      v17 = (_QWORD *)*((_QWORD *)P + 53);
      if ( (_QWORD *)*v17 != v15 )
        goto LABEL_215;
      *v17 = v16;
      *(_QWORD *)(v16 + 8) = v17;
      *((_QWORD *)P + 53) = P + 416;
      *v15 = v15;
    }
    LOBYTE(v12) = v105;
  }
  v18 = *((_QWORD *)P + 15);
  *((_QWORD *)P + 15) = 0;
  if ( !P[237] || (v64 = P + 392, (_QWORD *)*v64 == v64) )
  {
    if ( P[241] )
    {
      v88 = P + 392;
      if ( (_QWORD *)*v88 != v88 )
      {
        Smb2RemoveFileFromResilientHandleList(v88, 0);
        if ( v11 )
          --*(_DWORD *)(v11 + 176);
      }
    }
  }
  else
  {
    Smb2RemoveFileFromDurableHandleList(v64, 0);
  }
  if ( v10 )
  {
    KeReleaseInStackQueuedSpinLockFromDpcLevel(*(PKLOCK_QUEUE_HANDLE *)LockHandle);
    KeReleaseSpinLock((PKSPIN_LOCK)(v11 + 96), v106);
  }
  else
  {
    KeReleaseInStackQueuedSpinLock(*(PKLOCK_QUEUE_HANDLE *)LockHandle);
  }
  v19 = P + 656;
  if ( (_QWORD *)*v19 != v19 )
    RfsHashTableRemove(*(_QWORD *)(*((_QWORD *)P + 22) + 144LL), v19, P + 672, 16);
  if ( a2 )
  {
    if ( P[242] )
    {
      v101 = *(struct _FILE_OBJECT **)(v18 + 96);
      v102 = *((_QWORD *)P + 8);
      *(_QWORD *)&LockHandle[4] = 5;
      v109 = 0;
      *(_DWORD *)LockHandle = 1;
      v103 = Smb2RkfFsctl(v102, v101, (struct _NAMED_PIPE_CREATE_PARAMETERS *)LockHandle, 0xCu, 0, 0, &v109);
      if ( v103 < 0
        && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 36, WPP_1eeac08a4da9393ddade0ba3ac297e5e_Traceguids, v18, v103);
      }
    }
  }
  *(_BYTE *)(v18 + 104) = 1;
  if ( !(_BYTE)v12 )
  {
    v20 = _InterlockedDecrement64((volatile signed __int64 *)v18);
    if ( v20 == -1 )
    {
      __int2c();
    }
    else if ( !v20 )
    {
      if ( KeGetCurrentIrql() )
      {
        v5 = *(_DWORD *)(v18 + 8) == 5;
        *(_QWORD *)(v18 + 48) = Smb2DereferenceHandleCallback;
        *(_DWORD *)(v18 + 72) = 0;
        if ( v5 )
        {
          LOBYTE(BugCheckParameter4) = 1;
          LOBYTE(v98) = 1;
          SRV2_PERF_ENTER_EX(v18 + 584, v98, 391, "Srv2PostToThreadPool", BugCheckParameter4);
        }
        v89 = *(_QWORD *)(*(_QWORD *)(v18 + 64) + 136LL);
        v90 = *(_QWORD *)(v89 + 8LL * KeGetCurrentNodeNumber() + 8);
        if ( !ExpInterlockedPushEntrySList((PSLIST_HEADER)v90, (PSLIST_ENTRY)(v18 + 32)) && *(_WORD *)(v90 + 66) )
          RfspThreadPoolNodeWakeIdleWorker((struct _KEVENT *)v90);
      }
      else
      {
        Smb2DereferenceHandleCleanup((PVOID)v18, v111);
      }
    }
    v18 = 0;
  }
  memset(v113, 0, 24);
  v21 = 0;
  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)P + 14, (PKLOCK_QUEUE_HANDLE)v113);
  if ( *((_QWORD *)P + 18) )
  {
    v21 = *((_QWORD *)P + 18);
    if ( ((_InterlockedExchangeAdd64(*((volatile signed __int64 **)P + 19), 1u) + 2) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
      __int2c();
  }
  KeReleaseInStackQueuedSpinLock((PKLOCK_QUEUE_HANDLE)v113);
  v22 = *((_DWORD *)P + 22);
  if ( v22 != -1 && v21 )
  {
    v23 = *(_QWORD *)(v21 + 104);
    v5 = (*(_BYTE *)(v23 + 88) & 0x40) == 0;
    *(_QWORD *)LockHandle = *(_QWORD *)(v23 + 16);
    if ( v5 )
    {
      ExAcquirePushLockExclusiveEx(v23, 0);
      v24 = 0;
    }
    else
    {
      v24 = ExAcquireSpinLockExclusive((PEX_SPIN_LOCK)v23);
    }
    if ( (v22 & 3) == 1 )
    {
      v25 = *(_QWORD *)LockHandle;
      for ( i = 0; ; ++i )
      {
        v27 = *(_DWORD *)(v23 + 4LL * i + 24);
        v28 = v27 & (v22 >> *(_DWORD *)(v23 + 4LL * i + 48));
        if ( (unsigned int)v28 > v27 )
          break;
        v29 = *(_DWORD *)(v25 + 8 * v28);
        v30 = (_DWORD **)(v25 + 8 * v28);
        v31 = v29 & 3;
        if ( v31 != 2 )
        {
          if ( v31 || **v30 != v22 )
            break;
          *(_DWORD *)v30 = -1;
          v32 = *(_DWORD *)(v23 + 68);
          v33 = *(_DWORD *)(v23 + 44);
          v34 = v33 & (v22 >> v32);
          v35 = ~(v33 << v32);
          v36 = v35 & v22 | ((v33 & (v34 + 1)) << v32);
          if ( v36 == -1 )
            v36 = v35 | ((v33 & (v34 + 2)) << v32);
          --*(_DWORD *)(v23 + 8);
          v37 = *(int **)(v23 + 80);
          if ( v37 )
            *v37 = v36;
          v5 = *(_DWORD *)(v23 + 76) == -1;
          *(_QWORD *)(v23 + 80) = v30;
          if ( v5 )
            *(_DWORD *)(v23 + 76) = v36;
          if ( (*(_BYTE *)(v23 + 88) & 0x40) == 0 )
            goto LABEL_122;
          goto LABEL_54;
        }
        v25 = (unsigned __int64)*v30 & 0xFFFFFFFFFFFFFFFCuLL;
      }
    }
    if ( (*(_BYTE *)(v23 + 88) & 0x40) != 0 )
LABEL_54:
      ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)v23, v24);
    else
LABEL_122:
      ExReleasePushLockExclusiveEx(v23, 0);
    *((_DWORD *)P + 22) = -1;
    _InterlockedDecrement((volatile signed __int32 *)(v21 + 112));
  }
  if ( P[793] )
  {
    v82 = P + 848;
    *(_QWORD *)LockHandle = Smb2AppInstanceFileTableForCA;
    _mm_lfence();
    v83 = *(_QWORD *)(*(_QWORD *)LockHandle + 56LL)
        + 32LL
        * (((unsigned __int8)P[672]
          + (unsigned __int8)P[673]
          + (unsigned __int8)P[674]
          + (unsigned __int8)P[675]
          + (unsigned __int8)P[676]
          + (unsigned __int8)P[678]
          + (unsigned __int8)P[679]
          + (unsigned __int8)P[680]
          + (unsigned __int8)P[681]
          + (unsigned __int8)P[682]
          + (unsigned __int8)P[683]
          + (unsigned __int8)P[684]
          + (unsigned __int8)P[685]
          + (unsigned __int8)P[686]
          + (unsigned __int8)P[687]
          + (unsigned int)(unsigned __int8)P[677])
         % **(_DWORD **)LockHandle);
    if ( (*(_DWORD *)(v83 + 12) & 1) != 0 )
    {
      v84 = ExAcquireSpinLockExclusive((PEX_SPIN_LOCK)v83);
    }
    else
    {
      ExAcquirePushLockExclusiveEx(v83, 0);
      v84 = 0;
    }
    v85 = (_QWORD *)*v82;
    if ( (_QWORD *)*v82 != v82 )
    {
      if ( (_QWORD *)v85[1] != v82 )
        goto LABEL_215;
      v86 = (_QWORD *)*((_QWORD *)P + 107);
      if ( (_QWORD *)*v86 != v82 )
        goto LABEL_215;
      *v86 = v85;
      v85[1] = v86;
      v87 = *(_QWORD *)LockHandle;
      *((_QWORD *)P + 107) = P + 848;
      *v82 = v82;
      _InterlockedDecrement((volatile signed __int32 *)(v87 + 8));
      --*(_DWORD *)(v83 + 8);
    }
    if ( (*(_DWORD *)(v83 + 12) & 1) != 0 )
      ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)v83, v84);
    else
      ExReleasePushLockExclusiveEx(v83, 0);
  }
  else if ( P[794] )
  {
    RfsHashTableRemove(Smb2AppInstanceFileTableForNonCA, P + 848, P + 796, 16);
  }
  if ( *((_QWORD *)P + 10) != -1 )
  {
    v38 = P + 288;
    v39 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)P + 8) + 160LL) + 8LL);
    _mm_lfence();
    v40 = *(_QWORD *)(v39 + 56)
        + 32LL
        * (((unsigned __int8)P[80]
          + (unsigned __int8)P[81]
          + (unsigned __int8)P[82]
          + (unsigned __int8)P[83]
          + (unsigned __int8)P[84]
          + (unsigned __int8)P[86]
          + (unsigned __int8)P[87]
          + (unsigned int)(unsigned __int8)P[85])
         % *(_DWORD *)v39);
    if ( (*(_DWORD *)(v40 + 12) & 1) != 0 )
    {
      v41 = ExAcquireSpinLockExclusive((PEX_SPIN_LOCK)v40);
    }
    else
    {
      ExAcquirePushLockExclusiveEx(v40, 0);
      v41 = 0;
    }
    v42 = (_QWORD *)*v38;
    if ( (_QWORD *)*v38 != v38 )
    {
      if ( (_QWORD *)v42[1] != v38 )
        goto LABEL_215;
      v43 = (_QWORD *)*((_QWORD *)P + 37);
      if ( (_QWORD *)*v43 != v38 )
        goto LABEL_215;
      *v43 = v42;
      v42[1] = v43;
      *((_QWORD *)P + 37) = P + 288;
      *v38 = v38;
      _InterlockedDecrement((volatile signed __int32 *)(v39 + 8));
      --*(_DWORD *)(v40 + 8);
    }
    if ( (*(_DWORD *)(v40 + 12) & 1) != 0 )
      ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)v40, v41);
    else
      ExReleasePushLockExclusiveEx(v40, 0);
    *((_QWORD *)P + 10) = -1;
  }
  if ( *((_QWORD *)P + 40) == -1 )
  {
    if ( !v21 )
      goto LABEL_81;
    goto LABEL_78;
  }
  _InterlockedDecrement64((volatile signed __int64 *)(*((_QWORD *)P + 17) + 440LL));
  if ( P[237] )
    _InterlockedDecrement64((volatile signed __int64 *)(*((_QWORD *)P + 17) + 456LL));
  if ( P[245] )
    _InterlockedDecrement64((volatile signed __int64 *)(*((_QWORD *)P + 17) + 528LL));
  if ( v21 )
  {
    _InterlockedDecrement64((volatile signed __int64 *)(*(_QWORD *)(v21 + 24) + 272LL));
    if ( P[237] )
      _InterlockedDecrement64((volatile signed __int64 *)(*(_QWORD *)(v21 + 24) + 288LL));
LABEL_78:
    v44 = _InterlockedDecrement64(*(volatile signed __int64 **)(v21 + 24));
    if ( v44 == -1 )
    {
      __int2c();
    }
    else if ( !v44 )
    {
      Smb2FreeSession((PVOID)v21);
    }
  }
LABEL_81:
  v45 = (volatile signed __int64 *)*((_QWORD *)P + 22);
  if ( v45 )
  {
    v46 = _InterlockedDecrement64(v45);
    if ( v46 == -1 )
    {
      __int2c();
    }
    else if ( !v46 )
    {
      Smb2FreeClient((PVOID)v45);
    }
    *((_QWORD *)P + 22) = 0;
  }
  SrvLibFilePowerManagementClose(P + 256);
  v47 = _InterlockedDecrement64((volatile signed __int64 *)P);
  if ( v47 == -1 )
    __int2c();
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0 )
  {
    memset(v113, 0, 24);
    RtlCaptureStackBackTrace(0, 3u, (PVOID *)v113, 0);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qPPqqq(
        WPP_GLOBAL_Control->AttachedDevice,
        35,
        WPP_1eeac08a4da9393ddade0ba3ac297e5e_Traceguids,
        P,
        v47 + 1,
        v47,
        *(_QWORD *)v113,
        *(_QWORD *)&v113[8],
        *(_QWORD *)&v113[16]);
    }
  }
  if ( !v47 )
  {
    if ( KeGetCurrentIrql() )
    {
      v5 = *((_DWORD *)P + 2) == 5;
      *((_QWORD *)P + 6) = Smb2FreeFile;
      *((_DWORD *)P + 18) = 1;
      if ( v5 )
      {
        LOBYTE(BugCheckParameter4) = 1;
        LOBYTE(v80) = 1;
        SRV2_PERF_ENTER_EX(P + 584, v80, 391, "Srv2PostToThreadPool", BugCheckParameter4);
      }
      v91 = *(_QWORD *)(*((_QWORD *)P + 8) + 144LL);
      v92 = *(_QWORD *)(v91 + 8LL * KeGetCurrentNodeNumber() + 8);
      if ( !ExpInterlockedPushEntrySList((PSLIST_HEADER)v92, (PSLIST_ENTRY)P + 2) && *(_WORD *)(v92 + 66) )
        RfspThreadPoolNodeWakeIdleWorker((struct _KEVENT *)v92);
    }
    else
    {
      Smb2FreeFile(P, v80, v81);
    }
  }
  v48 = v110;
  if ( v110 )
  {
    if ( v108 < 0 )
      goto LABEL_98;
    v49 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v110 + 96));
    v5 = (*(_DWORD *)(v48 + 172))-- == 1;
    v50 = v49;
    if ( !v5 )
    {
      KeReleaseSpinLock((PKSPIN_LOCK)(v48 + 96), v49);
      goto LABEL_98;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_3d8eb6e120b9357e636b6f5c4c47d988_Traceguids, v48);
    }
    v51 = *(_DWORD *)(v48 + 12);
    if ( v51 == 221 || *(_QWORD *)(v48 + 152) != v48 + 152 || *(_DWORD *)(v48 + 172) )
    {
      Smb2LeaseProcessPendingLeaseOperationsAndReleaseSpinLock(v48, v50);
      goto LABEL_98;
    }
    if ( v51 == 224 )
      Smb2CancelQueuedDelayedLease(v48);
    *(_DWORD *)(v48 + 12) = 221;
    *(_BYTE *)(v48 + 128) = 1;
    if ( v107 )
      *(_DWORD *)(v48 + 140) |= 4u;
    v65 = *(_QWORD *)(v48 + 200);
    v66 = *(_QWORD *)(v48 + 112);
    v110 = v65;
    *(_QWORD *)(v48 + 112) = 0;
    _InterlockedIncrement(&dword_14004B384);
    Smb2LeaseProcessPendingLeaseOperationsAndReleaseSpinLock(v48, v50);
    v67 = KeAcquireSpinLockRaiseToDpc(&qword_14004B500);
    v68 = (_QWORD *)(v48 + 216);
    v69 = v67;
    v70 = *(_QWORD *)(v48 + 216);
    if ( v70 == v48 + 216 )
    {
      KeReleaseSpinLock(&qword_14004B500, v67);
    }
    else
    {
      if ( *(_QWORD **)(v70 + 8) != v68 )
        goto LABEL_215;
      v71 = *(_QWORD **)(v48 + 224);
      if ( (_QWORD *)*v71 != v68 )
        goto LABEL_215;
      *v71 = v70;
      *(_QWORD *)(v70 + 8) = v71;
      *(_QWORD *)(v48 + 224) = v48 + 216;
      *v68 = v68;
      --dword_14004B530;
      KeReleaseSpinLock(&qword_14004B500, v69);
      Smb2DereferenceLease((PVOID)v48);
      v110 = v65;
    }
    v72 = (_QWORD *)(v48 + 184);
    _mm_lfence();
    v73 = 32LL
        * ((*(unsigned __int8 *)(v48 + 80)
          + *(unsigned __int8 *)(v48 + 81)
          + *(unsigned __int8 *)(v48 + 82)
          + *(unsigned __int8 *)(v48 + 83)
          + *(unsigned __int8 *)(v48 + 84)
          + *(unsigned __int8 *)(v48 + 86)
          + *(unsigned __int8 *)(v48 + 87)
          + *(unsigned __int8 *)(v48 + 88)
          + *(unsigned __int8 *)(v48 + 89)
          + *(unsigned __int8 *)(v48 + 90)
          + *(unsigned __int8 *)(v48 + 91)
          + *(unsigned __int8 *)(v48 + 92)
          + *(unsigned __int8 *)(v48 + 93)
          + *(unsigned __int8 *)(v48 + 94)
          + *(unsigned __int8 *)(v48 + 95)
          + (unsigned int)*(unsigned __int8 *)(v48 + 85))
         % *(_DWORD *)v65)
        + *(_QWORD *)(v65 + 56);
    if ( (*(_DWORD *)(v73 + 12) & 1) != 0 )
    {
      v74 = ExAcquireSpinLockExclusive((PEX_SPIN_LOCK)v73);
    }
    else
    {
      ExAcquirePushLockExclusiveEx(v73, 0);
      v74 = 0;
    }
    v75 = (_QWORD *)*v72;
    if ( (_QWORD *)*v72 == v72 )
      goto LABEL_140;
    if ( (_QWORD *)v75[1] == v72 )
    {
      v76 = *(_QWORD **)(v48 + 192);
      if ( (_QWORD *)*v76 == v72 )
      {
        *v76 = v75;
        v75[1] = v76;
        v77 = v110;
        *(_QWORD *)(v48 + 192) = v48 + 184;
        *v72 = v72;
        _InterlockedDecrement((volatile signed __int32 *)(v77 + 8));
        --*(_DWORD *)(v73 + 8);
LABEL_140:
        if ( (*(_DWORD *)(v73 + 12) & 1) != 0 )
          ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)v73, v74);
        else
          ExReleasePushLockExclusiveEx(v73, 0);
        if ( v66 )
        {
          v78 = _InterlockedDecrement64((volatile signed __int64 *)v66);
          if ( v78 == -1 )
          {
            __int2c();
          }
          else if ( !v78 )
          {
            if ( KeGetCurrentIrql() )
            {
              v5 = *(_DWORD *)(v66 + 8) == 5;
              *(_QWORD *)(v66 + 48) = Smb2DereferenceHandleCallback;
              *(_DWORD *)(v66 + 72) = 0;
              if ( v5 )
              {
                LOBYTE(BugCheckParameter4) = 1;
                LOBYTE(v99) = 1;
                SRV2_PERF_ENTER_EX(v66 + 584, v99, 391, "Srv2PostToThreadPool", BugCheckParameter4);
              }
              v93 = *(_QWORD *)(*(_QWORD *)(v66 + 64) + 136LL);
              v94 = *(_QWORD *)(v93 + 8LL * KeGetCurrentNodeNumber() + 8);
              if ( !ExpInterlockedPushEntrySList((PSLIST_HEADER)v94, (PSLIST_ENTRY)(v66 + 32)) && *(_WORD *)(v94 + 66) )
              {
                RfspThreadPoolNodeWakeIdleWorker((struct _KEVENT *)v94);
                Smb2DereferenceLease((PVOID)v48);
                goto LABEL_98;
              }
            }
            else
            {
              Smb2DereferenceHandleCleanup((PVOID)v66, 0);
            }
          }
        }
        Smb2DereferenceLease((PVOID)v48);
LABEL_98:
        Smb2DereferenceLease((PVOID)v48);
        goto LABEL_99;
      }
    }
LABEL_215:
    __fastfail(3u);
  }
LABEL_99:
  if ( v18 )
  {
    v52 = _InterlockedDecrement64((volatile signed __int64 *)v18);
    if ( v52 == -1 )
    {
      __int2c();
    }
    else if ( !v52 )
    {
      if ( KeGetCurrentIrql() )
      {
        v5 = *(_DWORD *)(v18 + 8) == 5;
        *(_QWORD *)(v18 + 48) = Smb2DereferenceHandleCallback;
        *(_DWORD *)(v18 + 72) = 0;
        if ( v5 )
        {
          LOBYTE(BugCheckParameter4) = 1;
          LOBYTE(v100) = 1;
          SRV2_PERF_ENTER_EX(v18 + 584, v100, 391, "Srv2PostToThreadPool", BugCheckParameter4);
        }
        v95 = *(_QWORD *)(*(_QWORD *)(v18 + 64) + 136LL);
        v96 = *(_QWORD *)(v95 + 8LL * KeGetCurrentNodeNumber() + 8);
        if ( !ExpInterlockedPushEntrySList((PSLIST_HEADER)v96, (PSLIST_ENTRY)(v18 + 32)) )
        {
          if ( *(_WORD *)(v96 + 66) )
            RfspThreadPoolNodeWakeIdleWorker((struct _KEVENT *)v96);
        }
      }
      else
      {
        Smb2DereferenceHandleCleanup((PVOID)v18, v111);
      }
    }
  }
}

```

## disassembly

```asm
0x14000cdf0  mov     r11, rsp
0x14000cdf3  push    rbp
0x14000cdf4  push    rbx
0x14000cdf5  push    rsi
0x14000cdf6  push    rdi
0x14000cdf7  lea     rbp, [r11-57h]
0x14000cdfb  sub     rsp, 0D8h
0x14000ce02  mov     rax, cs:__security_cookie
0x14000ce09  xor     rax, rsp
0x14000ce0c  mov     [rbp+4Fh+var_38], rax
0x14000ce10  cmp     dword ptr [rcx+0Ch], 0DDh
0x14000ce17  movzx   esi, dl
0x14000ce1a  mov     rdi, [rbp+4Fh+arg_20]
0x14000ce1e  mov     rbx, rcx
0x14000ce21  mov     [rbp+4Fh+LockHandle], rdi
0x14000ce25  mov     [rbp+4Fh+var_78], r9
0x14000ce29  mov     [rbp+4Fh+var_8E], r8b
0x14000ce2d  jnz     loc_14000DDB3
0x14000ce33  cmp     dword ptr [rcx+364h], 0
0x14000ce3a  mov     [r11+10h], r12
0x14000ce3e  mov     [r11-28h], r13
0x14000ce42  mov     [r11-30h], r14
0x14000ce46  lea     r14, WPP_GLOBAL_Control
0x14000ce4d  mov     [r11-38h], r15
0x14000ce51  jnz     loc_14000D4FE
0x14000ce57  cmp     dword ptr [rcx+368h], 0
0x14000ce5e  jnz     loc_14000D4FE
0x14000ce64  add     rcx, 370h; Event
0x14000ce6b  xor     r8d, r8d; Wait
0x14000ce6e  xor     edx, edx; Increment
0x14000ce70  call    cs:__imp_KeSetEvent
0x14000ce77  nop     dword ptr [rax+rax+00h]
0x14000ce7c  xor     r13d, r13d
0x14000ce7f  mov     [rbp+4Fh+var_8C], 0C0000001h
0x14000ce86  xor     al, al
0x14000ce88  mov     [rbp+4Fh+var_80], r13
0x14000ce8c  xor     r12b, r12b
0x14000ce8f  mov     [rbp+4Fh+var_8F], al
0x14000ce92  mov     r14d, r13d
0x14000ce95  cmp     [rbx+0A8h], r13
0x14000ce9c  jz      loc_14000D8A1
0x14000cea2  test    sil, sil
0x14000cea5  jz      loc_14000D63F
0x14000ceab  test    cs:byte_14004C339, 8
0x14000ceb2  jnz     loc_14000DDE8
0x14000ceb8  mov     rdi, [rbx+0A8h]
0x14000cebf  test    rdi, rdi
0x14000cec2  jz      loc_14000D4F9
0x14000cec8  mov     r14, rdi
0x14000cecb  mov     [rbp+4Fh+var_80], rdi
0x14000cecf  mov     r15d, 1
0x14000ced5  lock xadd [rdi], r15
0x14000ceda  inc     r15
0x14000cedd  lea     rax, [r15+1]
0x14000cee1  test    rax, 0FFFFFFFFFFFFFFFEh
0x14000cee7  jnz     short loc_14000CEEB
0x14000cee9  int     2Ch; Windows NT - assertion failure
0x14000ceeb  mov     rax, cs:WPP_GLOBAL_Control
0x14000cef2  test    dword ptr [rax+2Ch], 40000000h
0x14000cef9  jnz     loc_14003B1CC
0x14000ceff  mov     r15, [rbp+4Fh+LockHandle]
0x14000cf03  mov     rcx, r15; LockHandle
0x14000cf06  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14000cf0d  nop     dword ptr [rax+rax+00h]
0x14000cf12  lea     rcx, [rdi+60h]; SpinLock
0x14000cf16  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000cf1d  nop     dword ptr [rax+rax+00h]
0x14000cf22  cmp     [rdi+81h], r12b
0x14000cf29  mov     r12b, 1
0x14000cf2c  mov     [rbp+4Fh+var_8F], al
0x14000cf2f  setnz   al
0x14000cf32  mov     [rbp+4Fh+var_90], al
0x14000cf35  cmp     [rdi+80h], r13b
0x14000cf3c  jnz     loc_14000DDF4
0x14000cf42  inc     dword ptr [rdi+0ACh]
0x14000cf48  mov     [rbp+4Fh+var_8C], r13d
0x14000cf4c  cmp     [rbx+0F2h], r13b
0x14000cf53  jnz     loc_14000DE00
0x14000cf59  lea     rcx, [rbx+70h]; SpinLock
0x14000cf5d  mov     rdx, r15; LockHandle
0x14000cf60  call    cs:__imp_KeAcquireInStackQueuedSpinLockAtDpcLevel
0x14000cf67  nop     dword ptr [rax+rax+00h]
0x14000cf6c  mov     r8, [rbx+0A8h]
0x14000cf73  cmp     r8, rdi
0x14000cf76  jnz     short loc_14000CFDA
0x14000cf78  mov     rcx, cs:WPP_GLOBAL_Control
0x14000cf7f  lea     rax, WPP_GLOBAL_Control
0x14000cf86  cmp     rcx, rax
0x14000cf89  jz      short loc_14000CF98
0x14000cf8b  test    dword ptr [rcx+2Ch], 40000000h
0x14000cf92  jnz     loc_14000DE29
0x14000cf98  mov     rcx, [rbx+0A8h]
0x14000cf9f  call    Smb2DereferenceLease
0x14000cfa4  lea     rax, [rbx+1A0h]
0x14000cfab  mov     [rbx+0A8h], r13
0x14000cfb2  mov     rdx, [rax]
0x14000cfb5  cmp     [rdx+8], rax
0x14000cfb9  jnz     loc_14000DF6B
0x14000cfbf  mov     rcx, [rax+8]
0x14000cfc3  cmp     [rcx], rax
0x14000cfc6  jnz     loc_14000DF6B
0x14000cfcc  mov     [rcx], rdx
0x14000cfcf  mov     [rdx+8], rcx
0x14000cfd3  mov     [rax+8], rax
0x14000cfd7  mov     [rax], rax
0x14000cfda  movzx   edi, [rbp+4Fh+var_90]
0x14000cfde  mov     r15, [rbx+78h]
0x14000cfe2  mov     [rbx+78h], r13
0x14000cfe6  cmp     [rbx+0EDh], r13b
0x14000cfed  jnz     loc_14000D689
0x14000cff3  cmp     [rbx+0F1h], r13b
0x14000cffa  jnz     loc_14000DB55
0x14000d000  mov     rcx, [rbp+4Fh+LockHandle]; LockHandle
0x14000d004  test    r12b, r12b
0x14000d007  jz      loc_14000D658
0x14000d00d  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x14000d014  nop     dword ptr [rax+rax+00h]
0x14000d019  movzx   edx, [rbp+4Fh+var_8F]; NewIrql
0x14000d01d  lea     rcx, [r14+60h]; SpinLock
0x14000d021  call    cs:__imp_KeReleaseSpinLock
0x14000d028  nop     dword ptr [rax+rax+00h]
0x14000d02d  lea     rdx, [rbx+290h]
0x14000d034  cmp     [rdx], rdx
0x14000d037  jz      short loc_14000D059
0x14000d039  mov     rcx, [rbx+0B0h]
0x14000d040  lea     r8, [rbx+2A0h]
0x14000d047  mov     r9d, 10h
0x14000d04d  mov     rcx, [rcx+90h]
0x14000d054  call    RfsHashTableRemove
0x14000d059  test    sil, sil
0x14000d05c  jz      short loc_14000D06B
0x14000d05e  cmp     [rbx+0F2h], r13b
0x14000d065  jnz     loc_14003B283
0x14000d06b  mov     byte ptr [r15+68h], 1
0x14000d070  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x14000d077  lea     r14, Smb2DereferenceHandleCallback
0x14000d07e  test    dil, dil
0x14000d081  jnz     short loc_14000D0A3
0x14000d083  mov     rax, rsi
0x14000d086  lock xadd [r15], rax
0x14000d08b  dec     rax
0x14000d08e  cmp     rax, rsi
0x14000d091  jnb     loc_14000DE55
0x14000d097  test    rax, rax
0x14000d09a  jz      loc_14000DE5C
0x14000d0a0  mov     r15, r13
0x14000d0a3  xorps   xmm0, xmm0
0x14000d0a6  lea     rcx, [rbx+70h]; SpinLock
0x14000d0aa  xor     eax, eax
0x14000d0ac  lea     rdx, [rbp+4Fh+var_60]; LockHandle
0x14000d0b0  movups  xmmword ptr [rbp+4Fh+var_60], xmm0
0x14000d0b4  mov     qword ptr [rbp+4Fh+var_60+10h], rax
0x14000d0b8  mov     r14, r13
0x14000d0bb  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14000d0c2  nop     dword ptr [rax+rax+00h]
0x14000d0c7  mov     rax, [rbx+90h]
0x14000d0ce  test    rax, rax
0x14000d0d1  jz      short loc_14000D0F5
0x14000d0d3  mov     r14, rax
0x14000d0d6  mov     ecx, 1
0x14000d0db  mov     rax, [rbx+98h]
0x14000d0e2  lock xadd [rax], rcx
0x14000d0e7  lea     rax, [rcx+2]
0x14000d0eb  test    rax, 0FFFFFFFFFFFFFFFEh
0x14000d0f1  jnz     short loc_14000D0F5
0x14000d0f3  int     2Ch; Windows NT - assertion failure
0x14000d0f5  lea     rcx, [rbp+4Fh+var_60]; LockHandle
0x14000d0f9  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14000d100  nop     dword ptr [rax+rax+00h]
0x14000d105  mov     r12d, [rbx+58h]
0x14000d109  cmp     r12d, 0FFFFFFFFh
0x14000d10d  jz      loc_14000D222
0x14000d113  test    r14, r14
0x14000d116  jz      loc_14000D222
0x14000d11c  mov     rdi, [r14+68h]
0x14000d120  mov     rcx, rdi; SpinLock
0x14000d123  test    byte ptr [rdi+58h], 40h
0x14000d127  mov     rax, [rdi+10h]
0x14000d12b  mov     [rbp+4Fh+LockHandle], rax
0x14000d12f  jz      loc_14000D945
0x14000d135  call    cs:__imp_ExAcquireSpinLockExclusive
0x14000d13c  nop     dword ptr [rax+rax+00h]
0x14000d141  movzx   r11d, al
0x14000d145  nop     word ptr [rax+rax+00000000h]
0x14000d150  mov     eax, r12d
0x14000d153  and     al, 3
0x14000d155  cmp     al, 1
0x14000d157  jnz     loc_14000D669
0x14000d15d  mov     r8, [rbp+4Fh+LockHandle]
0x14000d161  mov     r9d, r13d
0x14000d164  mov     ecx, r9d
0x14000d167  mov     edx, r12d
0x14000d16a  mov     eax, [rdi+rcx*4+18h]
0x14000d16e  mov     ecx, [rdi+rcx*4+30h]
0x14000d172  shr     edx, cl
0x14000d174  and     edx, eax
0x14000d176  cmp     edx, eax
0x14000d178  ja      loc_14000D669
0x14000d17e  mov     eax, [r8+rdx*8]
0x14000d182  lea     rdx, [r8+rdx*8]
0x14000d186  and     eax, 3
0x14000d189  cmp     eax, 2
0x14000d18c  jz      loc_14000DE81
0x14000d192  test    eax, eax
0x14000d194  jnz     loc_14000D669
0x14000d19a  mov     rax, [rdx]
0x14000d19d  cmp     [rax], r12d
0x14000d1a0  jnz     loc_14000D669
0x14000d1a6  mov     r10d, r12d
0x14000d1a9  mov     dword ptr [rdx], 0FFFFFFFFh
0x14000d1af  mov     ecx, [rdi+44h]
0x14000d1b2  mov     r9d, [rdi+2Ch]
0x14000d1b6  mov     r8d, r9d
0x14000d1b9  shr     r10d, cl
0x14000d1bc  and     r10d, r9d
0x14000d1bf  shl     r8d, cl
0x14000d1c2  not     r8d
0x14000d1c5  and     r12d, r8d
0x14000d1c8  lea     eax, [r10+1]
0x14000d1cc  and     eax, r9d
0x14000d1cf  shl     eax, cl
0x14000d1d1  or      eax, r12d
0x14000d1d4  cmp     eax, 0FFFFFFFFh
0x14000d1d7  jz      loc_14000DE90
0x14000d1dd  dec     dword ptr [rdi+8]
0x14000d1e0  mov     rcx, [rdi+50h]
0x14000d1e4  test    rcx, rcx
0x14000d1e7  jz      short loc_14000D1EB
0x14000d1e9  mov     [rcx], eax
0x14000d1eb  cmp     dword ptr [rdi+4Ch], 0FFFFFFFFh
0x14000d1ef  mov     [rdi+50h], rdx
0x14000d1f3  jz      loc_14000DEA1
0x14000d1f9  test    byte ptr [rdi+58h], 40h
0x14000d1fd  jz      loc_14000D673
0x14000d203  movzx   edx, r11b; OldIrql
0x14000d207  mov     rcx, rdi; SpinLock
0x14000d20a  call    cs:__imp_ExReleaseSpinLockExclusive
0x14000d211  nop     dword ptr [rax+rax+00h]
0x14000d216  mov     dword ptr [rbx+58h], 0FFFFFFFFh
0x14000d21d  lock dec dword ptr [r14+70h]
0x14000d222  cmp     [rbx+319h], r13b
0x14000d229  jnz     loc_14000D983
0x14000d22f  cmp     [rbx+31Ah], r13b
0x14000d236  jnz     loc_14000DEA9
0x14000d23c  cmp     [rbx+50h], rsi
0x14000d240  jz      loc_14000D319
0x14000d246  mov     rax, [rbx+40h]
0x14000d24a  lea     rdi, [rbx+120h]
0x14000d251  mov     rcx, [rax+0A0h]
0x14000d258  mov     r12, [rcx+8]
0x14000d25c  lfence
0x14000d25f  movzx   ecx, byte ptr [rbx+54h]
0x14000d263  xor     edx, edx
0x14000d265  movzx   eax, byte ptr [rbx+56h]
0x14000d269  movzx   r8d, byte ptr [rbx+57h]
0x14000d26e  add     r8d, eax
0x14000d271  movzx   eax, byte ptr [rbx+55h]
0x14000d275  add     eax, r8d
0x14000d278  add     eax, ecx
0x14000d27a  movzx   ecx, byte ptr [rbx+53h]
0x14000d27e  add     eax, ecx
0x14000d280  movzx   ecx, byte ptr [rbx+52h]
0x14000d284  add     eax, ecx
0x14000d286  movzx   ecx, byte ptr [rbx+51h]
0x14000d28a  add     eax, ecx
0x14000d28c  movzx   ecx, byte ptr [rbx+50h]
0x14000d290  add     eax, ecx
0x14000d292  div     dword ptr [r12]
0x14000d296  mov     r13d, edx
0x14000d299  shl     r13, 5
0x14000d29d  add     r13, [r12+38h]
0x14000d2a2  mov     rcx, r13; SpinLock
0x14000d2a5  mov     eax, [r13+0Ch]
0x14000d2a9  test    al, 1
0x14000d2ab  jz      loc_14000D96E
0x14000d2b1  call    cs:__imp_ExAcquireSpinLockExclusive
0x14000d2b8  nop     dword ptr [rax+rax+00h]
0x14000d2bd  movzx   edx, al; OldIrql
0x14000d2c0  mov     rax, [rdi]
0x14000d2c3  cmp     rax, rdi
0x14000d2c6  jz      short loc_14000D2F7
0x14000d2c8  cmp     [rax+8], rdi
0x14000d2cc  jnz     loc_14000DF6B
0x14000d2d2  mov     rcx, [rdi+8]
0x14000d2d6  cmp     [rcx], rdi
0x14000d2d9  jnz     loc_14000DF6B
0x14000d2df  mov     [rcx], rax
0x14000d2e2  mov     [rax+8], rcx
0x14000d2e6  mov     [rdi+8], rdi
0x14000d2ea  mov     [rdi], rdi
0x14000d2ed  lock dec dword ptr [r12+8]
0x14000d2f3  dec     dword ptr [r13+8]
0x14000d2f7  mov     eax, [r13+0Ch]
0x14000d2fb  mov     rcx, r13; SpinLock
0x14000d2fe  test    al, 1
0x14000d300  jz      loc_14000D95B
0x14000d306  call    cs:__imp_ExReleaseSpinLockExclusive
0x14000d30d  nop     dword ptr [rax+rax+00h]
0x14000d312  mov     [rbx+50h], rsi
0x14000d316  xor     r13d, r13d
  ... truncated ...
```
