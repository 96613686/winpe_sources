# MpSendProcessMessage

- ea: `0x140035130`
- end: `0x140035e4f`
- name: `MpSendProcessMessage`
- size: `3359`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140036780`

## callees

- `0x1400018a4`
- `0x140003950`
- `0x140004754`
- `0x1400049dc`
- `0x1400051bc`
- `0x14000572c`
- `0x140006234`
- `0x14000e9b0`
- `0x14000ea84`
- `0x14000ebe8`
- `0x1400118d0`
- `0x140011bc0`
- `0x140034b50`
- `0x140035080`
- `0x140035130`
- `0x140035e50`
- `0x140036058`
- `0x14007c758`

## import_xrefs

- `ntoskrnl!PsDereferencePrimaryToken` at `0x140035604`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x140035604`
- `ntoskrnl!SeQueryInformationToken` at `0x14003525e`
- `ntoskrnl!SeQueryInformationToken` at `0x14003576c`
- `ntoskrnl!SeQueryInformationToken` at `0x14003578c`
- `ntoskrnl!SeQueryInformationToken` at `0x1400357ac`
- `ntoskrnl!SeQueryInformationToken` at `0x14003525e`
- `ntoskrnl!SeQueryInformationToken` at `0x14003576c`
- `ntoskrnl!SeQueryInformationToken` at `0x14003578c`
- `ntoskrnl!SeQueryInformationToken` at `0x1400357ac`
- `ntoskrnl!PsReferencePrimaryToken` at `0x14003522f`
- `ntoskrnl!PsReferencePrimaryToken` at `0x14003522f`
- `ntoskrnl!PsLookupProcessByProcessId` at `0x1400352f6`
- `ntoskrnl!PsLookupProcessByProcessId` at `0x140035358`
- `ntoskrnl!PsLookupProcessByProcessId` at `0x1400352f6`
- `ntoskrnl!PsLookupProcessByProcessId` at `0x140035358`
- `ntoskrnl!PsGetProcessCreateTimeQuadPart` at `0x14003530a`
- `ntoskrnl!PsGetProcessCreateTimeQuadPart` at `0x14003536c`
- `ntoskrnl!PsGetProcessCreateTimeQuadPart` at `0x14003530a`
- `ntoskrnl!PsGetProcessCreateTimeQuadPart` at `0x14003536c`
- `ntoskrnl!IoQueryFileDosDeviceName` at `0x140035a3b`
- `ntoskrnl!IoQueryFileDosDeviceName` at `0x140035a3b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003561b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140035632`
- `ntoskrnl!ExFreePoolWithTag` at `0x140035649`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003561b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140035632`
- `ntoskrnl!ExFreePoolWithTag` at `0x140035649`
- `ntoskrnl!ObfDereferenceObject` at `0x14003531d`
- `ntoskrnl!ObfDereferenceObject` at `0x14003537f`
- `ntoskrnl!ObfDereferenceObject` at `0x14003531d`
- `ntoskrnl!ObfDereferenceObject` at `0x14003537f`
- `HAL!KeQueryPerformanceCounter` at `0x140035494`
- `HAL!KeQueryPerformanceCounter` at `0x1400354f0`
- `HAL!KeQueryPerformanceCounter` at `0x140035494`
- `HAL!KeQueryPerformanceCounter` at `0x1400354f0`
- `FLTMGR!FltSendMessage` at `0x1400354d8`
- `FLTMGR!FltSendMessage` at `0x1400354d8`

## pseudocode

```c
__int64 __fastcall MpSendProcessMessage(
        char a1,
        struct _KPROCESS *a2,
        struct _FILE_OBJECT *a3,
        void *a4,
        int a5,
        void *a6,
        __int64 a7,
        const UNICODE_STRING *a8,
        __int64 a9,
        const UNICODE_STRING *a10,
        _BYTE *a11)
{
  unsigned int v13; // esi
  int v14; // edx
  int v15; // edi
  int v16; // r14d
  PACCESS_TOKEN v17; // rax
  void *v18; // rdi
  NTSTATUS v19; // r14d
  int v20; // ebx
  int v21; // eax
  __int64 v22; // rsi
  NTSTATUS v23; // r14d
  int v24; // r14d
  HANDLE v25; // rcx
  LONGLONG TimeQuadPart; // rbx
  LONGLONG v27; // rbx
  char v28; // al
  int v29; // eax
  int v30; // eax
  LARGE_INTEGER PerformanceCounter; // rbx
  LONGLONG Timer_high; // rdx
  int v33; // r8d
  LARGE_INTEGER v34; // r9
  LARGE_INTEGER v35; // rax
  LONGLONG v36; // r13
  bool v37; // zf
  int v38; // edx
  int v39; // r8d
  int Length; // eax
  int v42; // eax
  const char *v43; // rax
  NTSTATUS v44; // eax
  NTSTATUS v45; // eax
  NTSTATUS v46; // eax
  int v47; // eax
  __int64 v48; // rdx
  int v49; // eax
  __int64 Buffer; // rcx
  int ReplyBuffer; // [rsp+20h] [rbp-E0h]
  int v52; // [rsp+50h] [rbp-B0h]
  unsigned int v53; // [rsp+54h] [rbp-ACh]
  unsigned int v54; // [rsp+58h] [rbp-A8h]
  size_t cbDest; // [rsp+5Ch] [rbp-A4h]
  unsigned int v56; // [rsp+64h] [rbp-9Ch]
  __int64 v58; // [rsp+80h] [rbp-80h] BYREF
  PCUNICODE_STRING v59; // [rsp+88h] [rbp-78h]
  _BYTE *v60; // [rsp+90h] [rbp-70h]
  PEPROCESS Process; // [rsp+98h] [rbp-68h] BYREF
  PVOID v62; // [rsp+A0h] [rbp-60h] BYREF
  PVOID P; // [rsp+A8h] [rbp-58h] BYREF
  PVOID v64; // [rsp+B0h] [rbp-50h] BYREF
  PVOID TokenInformation; // [rsp+B8h] [rbp-48h] BYREF
  PVOID v66; // [rsp+C0h] [rbp-40h] BYREF
  HANDLE ProcessId; // [rsp+C8h] [rbp-38h] BYREF
  _QWORD v68[14]; // [rsp+D0h] [rbp-30h] BYREF

  v13 = 128;
  ProcessId = a6;
  v14 = 0;
  v15 = 0;
  v60 = a11;
  v16 = 0;
  v59 = a10;
  v52 = 128;
  LODWORD(Process) = 0;
  v58 = 0;
  v53 = 0;
  v56 = 0;
  v62 = 0;
  cbDest = 0;
  v54 = 0;
  P = 0;
  v64 = 0;
  LODWORD(v66) = 0;
  if ( a1 && a11 )
    *a11 = 0;
  if ( a4 && a9 && a2 )
  {
    if ( a8 )
    {
      Length = a8->Length;
      if ( (_WORD)Length )
      {
        v13 = Length + 130;
        v53 = 128;
        v14 = Length + 2;
        v52 = Length + 130;
        LODWORD(Process) = Length + 2;
      }
    }
    if ( a10 )
    {
      v42 = a10->Length;
      if ( (_WORD)v42 )
      {
        v15 = v42 + 2;
        v13 += v42 + 2;
        LODWORD(cbDest) = v42 + 2;
        v16 = v14 + 128;
        v52 = v13;
        v54 = v14 + 128;
      }
    }
    if ( (a5 & 4) != 0 && a3 && IoQueryFileDosDeviceName(a3, (POBJECT_NAME_INFORMATION *)&v62) >= 0 && v62 )
    {
      v49 = *(unsigned __int16 *)v62;
      v13 += v49 + 2;
      v52 = v13;
      v56 = v49 + 2;
      HIDWORD(cbDest) = v16 + v15;
    }
    v17 = PsReferencePrimaryToken(a2);
    LODWORD(TokenInformation) = 0;
    v18 = v17;
    if ( v17 )
    {
      v19 = SeQueryInformationToken(v17, TokenSessionId, &TokenInformation);
      if ( v19 >= 0 )
      {
        v20 = (int)TokenInformation;
        goto LABEL_13;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      {
        _mm_lfence();
        WPP_SF_qD(
          WPP_GLOBAL_Control->AttachedDevice,
          16,
          WPP_81cd47ed6b7c3e33e522c0360ded0121_Traceguids,
          KeGetCurrentThread(),
          v19);
      }
    }
    else
    {
      v19 = -1073741811;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      _mm_lfence();
      WPP_SF_qD(
        WPP_GLOBAL_Control->AttachedDevice,
        50,
        WPP_8ebd71c5d5f53801838f519f7d1f4ffb_Traceguids,
        KeGetCurrentThread(),
        v19);
    }
    v20 = 0;
LABEL_13:
    if ( (*(_DWORD *)(MpData + 864) & 1) != 0 )
    {
      v44 = SeQueryInformationToken(v18, TokenElevationType, &P);
      if ( v44 < 0
        && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      {
        _mm_lfence();
        WPP_SF_qD(
          WPP_GLOBAL_Control->AttachedDevice,
          51,
          WPP_8ebd71c5d5f53801838f519f7d1f4ffb_Traceguids,
          KeGetCurrentThread(),
          v44);
      }
      v45 = SeQueryInformationToken(v18, TokenElevation, &v64);
      if ( v45 < 0
        && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      {
        _mm_lfence();
        WPP_SF_qD(
          WPP_GLOBAL_Control->AttachedDevice,
          52,
          WPP_8ebd71c5d5f53801838f519f7d1f4ffb_Traceguids,
          KeGetCurrentThread(),
          v45);
      }
      v46 = SeQueryInformationToken(v18, TokenIntegrityLevel, &v66);
      if ( v46 < 0
        && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      {
        _mm_lfence();
        WPP_SF_qD(
          WPP_GLOBAL_Control->AttachedDevice,
          53,
          WPP_8ebd71c5d5f53801838f519f7d1f4ffb_Traceguids,
          KeGetCurrentThread(),
          v46);
      }
    }
    v21 = MpAsyncCreateNotification(&v58, v13);
    v22 = v58;
    v23 = v21;
    if ( v21 < 0 )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
        goto LABEL_46;
      v48 = 54;
      ReplyBuffer = v21;
    }
    else
    {
      v24 = (int)Process;
      if ( (_DWORD)Process )
      {
        _mm_lfence();
        if ( RtlStringCbCopyUnicodeString((NTSTRSAFE_PWSTR)(v58 + v53), (unsigned int)Process, a8) < 0 )
        {
          v24 = 0;
          v53 = 0;
        }
      }
      if ( (_DWORD)cbDest )
      {
        _mm_lfence();
        if ( RtlStringCbCopyUnicodeString((NTSTRSAFE_PWSTR)(v22 + v54), (unsigned int)cbDest, v59) < 0 )
        {
          LODWORD(cbDest) = 0;
          v54 = 0;
        }
      }
      if ( v56 )
      {
        if ( v62 )
        {
          _mm_lfence();
          if ( RtlStringCbCopyUnicodeString((NTSTRSAFE_PWSTR)(v22 + HIDWORD(cbDest)), v56, (PCUNICODE_STRING)v62) < 0 )
          {
            v56 = 0;
            HIDWORD(cbDest) = 0;
          }
        }
      }
      if ( a1 && a7 )
      {
        *(_QWORD *)(v22 + 104) = *(_QWORD *)a7;
        *(_DWORD *)(v22 + 112) = *(_DWORD *)(a7 + 8);
      }
      v25 = ProcessId;
      *(_DWORD *)(v22 + 68) = v20;
      TimeQuadPart = 0;
      *(_DWORD *)(v22 + 64) = v53;
      *(_DWORD *)(v22 + 24) = (_DWORD)v25;
      if ( v25 )
      {
        Process = 0;
        if ( PsLookupProcessByProcessId(v25, &Process) >= 0 )
        {
          TimeQuadPart = PsGetProcessCreateTimeQuadPart(Process);
          ObfDereferenceObject(Process);
        }
      }
      *(_QWORD *)(v22 + 28) = MpFileTimeToUlong64(TimeQuadPart);
      v27 = 0;
      v28 = *(_BYTE *)(a9 + 52) & 1;
      Process = 0;
      *(_BYTE *)(v22 + 49) = v28;
      *(_BYTE *)(v22 + 48) = a1;
      *(_DWORD *)(v22 + 36) = (_DWORD)a4;
      if ( PsLookupProcessByProcessId(a4, &Process) >= 0 )
      {
        v27 = PsGetProcessCreateTimeQuadPart(Process);
        ObfDereferenceObject(Process);
      }
      *(_QWORD *)(v22 + 40) = MpFileTimeToUlong64(v27);
      *(_DWORD *)(v22 + 8) = v52;
      *(_DWORD *)(v22 + 16) = 0;
      *(_DWORD *)(v22 + 60) = v24;
      if ( P )
        v29 = *(_DWORD *)P;
      else
        v29 = 1;
      *(_DWORD *)(v22 + 88) = v29;
      v30 = (int)v64;
      if ( v64 )
        v30 = *(_DWORD *)v64;
      *(_DWORD *)(v22 + 92) = v30;
      *(_DWORD *)(v22 + 96) = (_DWORD)v66;
      *(_DWORD *)(v22 + 76) = v54;
      *(_DWORD *)(v22 + 72) = cbDest;
      *(_DWORD *)(v22 + 100) = a5;
      *(_DWORD *)(v22 + 116) = *(_DWORD *)(a9 + 240);
      *(_DWORD *)(v22 + 120) = *(_DWORD *)(a9 + 56);
      *(_DWORD *)(v22 + 124) = *(_DWORD *)(a9 + 60);
      *(_DWORD *)(v22 + 84) = HIDWORD(cbDest);
      *(_DWORD *)(v22 + 80) = v56;
      if ( *(_QWORD *)(MpData + 432) )
      {
        _mm_lfence();
        v47 = MpAsyncSendNotification(v22, v52, 0, 2, a9);
        if ( v47 < 0
          && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        {
          _mm_lfence();
          WPP_SF_qD(
            WPP_GLOBAL_Control->AttachedDevice,
            55,
            WPP_8ebd71c5d5f53801838f519f7d1f4ffb_Traceguids,
            KeGetCurrentThread(),
            v47);
        }
      }
      if ( a1 && *(_QWORD *)(MpData + 320) )
      {
        _mm_lfence();
        TokenInformation = 0;
        memset(v68, 0, sizeof(v68));
        ProcessId = (HANDLE)(-10000LL * (unsigned int)dword_1400269CC);
        LODWORD(Process) = 112;
        *(_QWORD *)v22 = _InterlockedIncrement64((volatile signed __int64 *)(MpData + 856));
        PerformanceCounter = KeQueryPerformanceCounter((PLARGE_INTEGER)&TokenInformation);
        v23 = FltSendMessage(
                *(PFLT_FILTER *)(MpData + 16),
                (PFLT_PORT *)(MpData + 320),
                (PVOID)(v22 - 24),
                v52 + 24,
                v68,
                (PULONG)&Process,
                (PLARGE_INTEGER)&ProcessId);
        if ( TokenInformation )
        {
          v35 = KeQueryPerformanceCounter(0);
          v33 = (int)TokenInformation;
          v34 = v35;
          Timer_high = 1000 * (v35.QuadPart - PerformanceCounter.QuadPart) % (__int64)TokenInformation;
          v36 = 1000 * (v35.QuadPart - PerformanceCounter.QuadPart) / (__int64)TokenInformation;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          {
            Timer_high = HIDWORD(WPP_GLOBAL_Control->Timer);
            if ( (Timer_high & 4) != 0 )
              ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD))WPP_SF_IIIII)(
                WPP_GLOBAL_Control->AttachedDevice,
                Timer_high,
                TokenInformation,
                (LARGE_INTEGER)v35.QuadPart,
                (LARGE_INTEGER)PerformanceCounter.QuadPart,
                v35.QuadPart - PerformanceCounter.QuadPart,
                TokenInformation,
                v36);
          }
          if ( *(int *)(MpData + 3000) < 0 )
          {
            _InterlockedExchange64((volatile __int64 *)(MpData + 2992), 0);
            _InterlockedExchange((volatile __int32 *)(MpData + 3000), 0);
          }
          _InterlockedAdd64((volatile signed __int64 *)(MpData + 2992), v36);
          _InterlockedIncrement((volatile signed __int32 *)(MpData + 3000));
        }
        if ( v23 == 258 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
          {
            WPP_SF_DZD(WPP_GLOBAL_Control->AttachedDevice, Timer_high, v33, (_DWORD)a4, (__int64)a8, dword_1400269CC);
          }
          v23 = -1073741643;
          _InterlockedIncrement((volatile signed __int32 *)(MpData + 3020));
          if ( *(_BYTE *)(MpData + 4024) )
          {
            _InterlockedIncrement((volatile signed __int32 *)(MpData + 612));
            if ( *(_DWORD *)(MpData + 612) > (unsigned int)dword_1400269D0 )
            {
              LOBYTE(v34.LowPart) = 1;
              ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD))MpSendAsyncPanicModeMessage)(
                2,
                0,
                *(unsigned __int8 *)(MpData + 208),
                (LARGE_INTEGER)v34.QuadPart,
                0);
            }
          }
          *(_DWORD *)(a9 + 292) = *(_DWORD *)(a9 + 292) & 0xFFFFFFF0 | 2;
          goto LABEL_46;
        }
        if ( v23 < 0 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          {
            _mm_lfence();
            WPP_SF_d(
              WPP_GLOBAL_Control->AttachedDevice,
              58,
              WPP_8ebd71c5d5f53801838f519f7d1f4ffb_Traceguids,
              (unsigned int)v23);
          }
          _InterlockedIncrement((volatile signed __int32 *)(MpData + 3012));
          _InterlockedExchange((volatile __int32 *)(MpData + 3016), v23);
          *(_DWORD *)(a9 + 292) = *(_DWORD *)(a9 + 292) & 0xFFFFFFF0 | 3;
          goto LABEL_46;
        }
        if ( LOBYTE(v68[0]) == 0xA5 && WORD1(v68[0]) == 112 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
          {
            v43 = "TRUE";
            if ( !LOBYTE(v68[10]) )
              v43 = "FALSE";
            WPP_SF_DZDiis(
              WPP_GLOBAL_Control->AttachedDevice,
              (unsigned int)"FALSE",
              v33,
              (_DWORD)a4,
              (__int64)a8,
              SBYTE4(v68[2]),
              v68[4],
              v68[5],
              (__int64)v43);
          }
          v37 = LOBYTE(v68[10]) == 0;
          *(_DWORD *)(a9 + 292) = *(_DWORD *)(a9 + 292) & 0xFFFFFFF0 | 1;
          if ( v37 )
          {
            MpSetProcessInfoByContext(a9, &v68[1]);
            _InterlockedIncrement((volatile signed __int32 *)(MpData + 3008));
            if ( ((__int64)WPP_MAIN_CB.DeviceExtension & 0x10) != 0 )
            {
              if ( a8 )
                Buffer = (__int64)a8->Buffer;
              else
                Buffer = 0;
              McTemplateK0qzqqzxx_EtwWriteTransfer(
                Buffer,
                v38,
                v39,
                *(_DWORD *)(a9 + 24),
                (__int64)L"sync",
                *(_DWORD *)(a9 + 52),
                *(_DWORD *)(a9 + 56),
                Buffer,
                *(_QWORD *)(a9 + 64),
                *(_QWORD *)(a9 + 72));
            }
          }
          else
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
            {
              WPP_SF_DZ(
                WPP_GLOBAL_Control->AttachedDevice,
                61,
                (unsigned int)WPP_8ebd71c5d5f53801838f519f7d1f4ffb_Traceguids,
                (_DWORD)a4,
                (__int64)a8);
            }
            if ( v60 )
            {
              *v60 = 1;
            }
            else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                   && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
            {
              WPP_SF_DZ(
                WPP_GLOBAL_Control->AttachedDevice,
                62,
                (unsigned int)WPP_8ebd71c5d5f53801838f519f7d1f4ffb_Traceguids,
                (_DWORD)a4,
                (__int64)a8);
            }
          }
        }
        else
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
          {
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 59, WPP_8ebd71c5d5f53801838f519f7d1f4ffb_Traceguids);
          }
          _InterlockedIncrement((volatile signed __int32 *)(MpData + 3024));
          *(_DWORD *)(a9 + 292) = *(_DWORD *)(a9 + 292) & 0xFFFFFFF0 | 4;
        }
        goto LABEL_45;
      }
      if ( (*(_DWORD *)(MpData + 868) & 2) == 0 )
      {
        v23 = 0;
        goto LABEL_46;
      }
      _mm_lfence();
      v23 = MpAsyncSendNotification(v22, v52, 0, 1, a9);
      if ( v23 >= 0 )
      {
LABEL_45:
        v23 = 0;
LABEL_46:
        if ( v22 )
          MpAsyncDereferenceNotification(v22);
        if ( v18 )
          PsDereferencePrimaryToken(v18);
        goto LABEL_50;
      }
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
        goto LABEL_46;
      v48 = 63;
      ReplyBuffer = v23;
    }
    _mm_lfence();
    WPP_SF_qD(
      WPP_GLOBAL_Control->AttachedDevice,
      v48,
      WPP_8ebd71c5d5f53801838f519f7d1f4ffb_Traceguids,
      KeGetCurrentThread(),
      ReplyBuffer);
    goto LABEL_46;
  }
  v23 = -1073741811;
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
    return (unsigned int)v23;
  WPP_SF_qD(
    WPP_GLOBAL_Control->AttachedDevice,
    49,
    WPP_8ebd71c5d5f53801838f519f7d1f4ffb_Traceguids,
    KeGetCurrentThread(),
    -1073741811);
LABEL_50:
  if ( P )
    ExFreePoolWithTag(P, 0);
  if ( v64 )
    ExFreePoolWithTag(v64, 0);
  if ( v62 )
    ExFreePoolWithTag(v62, 0);
  return (unsigned int)v23;
}

```

## disassembly

```asm
0x140035130  mov     [rsp-8+arg_0], rbx
0x140035135  push    rbp
0x140035136  push    rsi
0x140035137  push    rdi
0x140035138  push    r12
0x14003513a  push    r13
0x14003513c  push    r14
0x14003513e  push    r15
0x140035140  lea     rbp, [rsp-50h]
0x140035145  sub     rsp, 150h
0x14003514c  mov     rax, cs:__security_cookie
0x140035153  xor     rax, rsp
0x140035156  mov     [rbp+80h+var_40], rax
0x14003515a  mov     rax, [rbp+80h+arg_28]
0x140035161  xor     r12d, r12d
0x140035164  mov     r10, [rbp+80h+arg_38]
0x14003516b  movzx   r13d, cl
0x14003516f  mov     rcx, [rbp+80h+arg_48]
0x140035176  mov     rbx, rdx
0x140035179  mov     r15, [rbp+80h+arg_40]
0x140035180  mov     esi, 80h
0x140035185  mov     [rbp+80h+ProcessId], rax
0x140035189  mov     edx, r12d
0x14003518c  mov     rax, [rbp+80h+arg_50]
0x140035193  mov     edi, r12d
0x140035196  mov     [rbp+80h+var_F0], rax
0x14003519a  mov     r14d, r12d
0x14003519d  mov     [rsp+180h+var_110], r9
0x1400351a2  mov     [rbp+80h+var_F8], rcx
0x1400351a6  mov     [rsp+180h+SourceString], r10
0x1400351ab  mov     [rsp+180h+var_130], esi
0x1400351af  mov     dword ptr [rbp+80h+Process], edx
0x1400351b2  mov     [rbp+80h+var_100], r12
0x1400351b6  mov     [rsp+180h+var_12C], r12d
0x1400351bb  mov     [rsp+180h+var_11C], r12d
0x1400351c0  mov     dword ptr [rsp+180h+cbDest+4], r12d
0x1400351c5  mov     [rbp+80h+var_E0], r12
0x1400351c9  mov     [rsp+180h+var_11C+4], r12d
0x1400351ce  mov     dword ptr [rsp+180h+cbDest], r12d
0x1400351d3  mov     [rsp+180h+var_128], r12d
0x1400351d8  mov     [rbp+80h+P], r12
0x1400351dc  mov     [rbp+80h+var_D0], r12
0x1400351e0  mov     dword ptr [rbp+80h+var_C0], r12d
0x1400351e4  test    r13b, r13b
0x1400351e7  jz      short loc_1400351F2
0x1400351e9  test    rax, rax
0x1400351ec  jnz     loc_14003569F
0x1400351f2  test    r9, r9
0x1400351f5  jz      loc_140035657
0x1400351fb  test    r15, r15
0x1400351fe  jz      loc_140035657
0x140035204  test    rbx, rbx
0x140035207  jz      loc_140035657
0x14003520d  test    r10, r10
0x140035210  jnz     loc_1400356AD
0x140035216  test    rcx, rcx
0x140035219  jnz     loc_1400356D8
0x14003521f  test    byte ptr [rbp+80h+arg_20], 4
0x140035226  jnz     loc_140035A2B
0x14003522c  mov     rcx, rbx; Process
0x14003522f  call    cs:__imp_PsReferencePrimaryToken
0x140035236  nop     dword ptr [rax+rax+00h]
0x14003523b  mov     dword ptr [rbp+80h+TokenInformation], r12d
0x14003523f  lea     r12, WPP_GLOBAL_Control
0x140035246  mov     rdi, rax
0x140035249  test    rax, rax
0x14003524c  jz      loc_140035B05
0x140035252  lea     r8, [rbp+80h+TokenInformation]; TokenInformation
0x140035256  mov     edx, 0Ch; TokenInformationClass
0x14003525b  mov     rcx, rax; Token
0x14003525e  call    cs:__imp_SeQueryInformationToken
0x140035265  nop     dword ptr [rax+rax+00h]
0x14003526a  mov     r14d, eax
0x14003526d  test    eax, eax
0x14003526f  js      loc_140035AC3
0x140035275  mov     ebx, dword ptr [rbp+80h+TokenInformation]
0x140035278  mov     rax, cs:MpData
0x14003527f  mov     ecx, [rax+360h]
0x140035285  test    cl, 1
0x140035288  jnz     loc_140035760
0x14003528e  mov     edx, esi
0x140035290  lea     rcx, [rbp+80h+var_100]
0x140035294  call    MpAsyncCreateNotification
0x140035299  mov     rsi, [rbp+80h+var_100]
0x14003529d  mov     r14d, eax
0x1400352a0  test    eax, eax
0x1400352a2  js      loc_1400358B5
0x1400352a8  mov     r14d, dword ptr [rbp+80h+Process]
0x1400352ac  test    r14d, r14d
0x1400352af  jnz     loc_14003585C
0x1400352b5  mov     eax, dword ptr [rsp+180h+cbDest]
0x1400352b9  test    eax, eax
0x1400352bb  jnz     loc_140035888
0x1400352c1  mov     eax, [rsp+180h+var_11C]
0x1400352c5  test    eax, eax
0x1400352c7  jnz     loc_14003594A
0x1400352cd  test    r13b, r13b
0x1400352d0  jnz     loc_14003580D
0x1400352d6  mov     rcx, [rbp+80h+ProcessId]; ProcessId
0x1400352da  mov     eax, [rsp+180h+var_12C]
0x1400352de  mov     [rsi+44h], ebx
0x1400352e1  xor     ebx, ebx
0x1400352e3  mov     [rsi+40h], eax
0x1400352e6  mov     [rsi+18h], ecx
0x1400352e9  test    rcx, rcx
0x1400352ec  jz      short loc_140035329
0x1400352ee  lea     rdx, [rbp+80h+Process]; Process
0x1400352f2  mov     [rbp+80h+Process], rbx
0x1400352f6  call    cs:__imp_PsLookupProcessByProcessId
0x1400352fd  nop     dword ptr [rax+rax+00h]
0x140035302  test    eax, eax
0x140035304  js      short loc_140035329
0x140035306  mov     rcx, [rbp+80h+Process]; Process
0x14003530a  call    cs:__imp_PsGetProcessCreateTimeQuadPart
0x140035311  nop     dword ptr [rax+rax+00h]
0x140035316  mov     rcx, [rbp+80h+Process]; Object
0x14003531a  mov     rbx, rax
0x14003531d  call    cs:__imp_ObfDereferenceObject
0x140035324  nop     dword ptr [rax+rax+00h]
0x140035329  mov     rcx, rbx
0x14003532c  call    MpFileTimeToUlong64
0x140035331  mov     [rsi+1Ch], rax
0x140035335  lea     rdx, [rbp+80h+Process]; Process
0x140035339  movzx   eax, byte ptr [r15+34h]
0x14003533e  xor     ebx, ebx
0x140035340  and     al, 1
0x140035342  mov     [rbp+80h+Process], rbx
0x140035346  mov     [rsi+31h], al
0x140035349  mov     rax, [rsp+180h+var_110]
0x14003534e  mov     [rsi+30h], r13b
0x140035352  mov     rcx, rax; ProcessId
0x140035355  mov     [rsi+24h], eax
0x140035358  call    cs:__imp_PsLookupProcessByProcessId
0x14003535f  nop     dword ptr [rax+rax+00h]
0x140035364  test    eax, eax
0x140035366  js      short loc_14003538B
0x140035368  mov     rcx, [rbp+80h+Process]; Process
0x14003536c  call    cs:__imp_PsGetProcessCreateTimeQuadPart
0x140035373  nop     dword ptr [rax+rax+00h]
0x140035378  mov     rcx, [rbp+80h+Process]; Object
0x14003537c  mov     rbx, rax
0x14003537f  call    cs:__imp_ObfDereferenceObject
0x140035386  nop     dword ptr [rax+rax+00h]
0x14003538b  mov     rcx, rbx
0x14003538e  call    MpFileTimeToUlong64
0x140035393  mov     [rsi+28h], rax
0x140035397  xor     edx, edx
0x140035399  mov     eax, [rsp+180h+var_130]
0x14003539d  mov     ebx, 1
0x1400353a2  mov     [rsi+8], eax
0x1400353a5  mov     [rsi+10h], edx
0x1400353a8  mov     [rsi+3Ch], r14d
0x1400353ac  mov     rax, [rbp+80h+P]
0x1400353b0  test    rax, rax
0x1400353b3  jz      loc_1400356A6
0x1400353b9  mov     eax, [rax]
0x1400353bb  mov     [rsi+58h], eax
0x1400353be  mov     rax, [rbp+80h+var_D0]
0x1400353c2  test    rax, rax
0x1400353c5  jz      loc_140035706
0x1400353cb  mov     eax, [rax]
0x1400353cd  mov     r14d, [rsp+180h+var_130]
0x1400353d2  mov     [rsi+5Ch], eax
0x1400353d5  mov     eax, dword ptr [rbp+80h+var_C0]
0x1400353d8  mov     [rsi+60h], eax
0x1400353db  mov     eax, [rsp+180h+var_128]
0x1400353df  mov     [rsi+4Ch], eax
0x1400353e2  mov     eax, dword ptr [rsp+180h+cbDest]
0x1400353e6  mov     [rsi+48h], eax
0x1400353e9  mov     eax, [rbp+80h+arg_20]
0x1400353ef  mov     [rsi+64h], eax
0x1400353f2  mov     eax, [r15+0F0h]
0x1400353f9  mov     [rsi+74h], eax
0x1400353fc  mov     eax, [r15+38h]
0x140035400  mov     [rsi+78h], eax
0x140035403  mov     eax, [r15+3Ch]
0x140035407  mov     [rsi+7Ch], eax
0x14003540a  mov     eax, dword ptr [rsp+180h+cbDest+4]
0x14003540e  mov     [rsi+54h], eax
0x140035411  mov     eax, [rsp+180h+var_11C]
0x140035415  mov     [rsi+50h], eax
0x140035418  mov     rax, cs:MpData
0x14003541f  cmp     [rax+1B0h], rdx
0x140035426  jnz     loc_140035831
0x14003542c  test    r13b, r13b
0x14003542f  jz      loc_140035930
0x140035435  mov     rax, cs:MpData
0x14003543c  cmp     qword ptr [rax+140h], 0
0x140035444  jz      loc_140035930
0x14003544a  lfence
0x14003544d  mov     [rbp+80h+TokenInformation], rdx
0x140035451  lea     rcx, [rbp+80h+var_B0]; void *
0x140035455  xor     edx, edx; Val
0x140035457  mov     r8d, 70h ; 'p'; Size
0x14003545d  call    memset
0x140035462  mov     eax, cs:dword_1400269CC
0x140035468  imul    rcx, rax, 0FFFFFFFFFFFFD8F0h
0x14003546f  mov     rax, cs:MpData
0x140035476  mov     [rbp+80h+ProcessId], rcx
0x14003547a  mov     dword ptr [rbp+80h+Process], 70h ; 'p'
0x140035481  lock xadd [rax+358h], rbx
0x14003548a  inc     rbx
0x14003548d  lea     rcx, [rbp+80h+TokenInformation]; PerformanceFrequency
0x140035491  mov     [rsi], rbx
0x140035494  call    cs:__imp_KeQueryPerformanceCounter
0x14003549b  nop     dword ptr [rax+rax+00h]
0x1400354a0  mov     rcx, cs:MpData
0x1400354a7  lea     r9d, [r14+18h]; SenderBufferLength
0x1400354ab  mov     rbx, rax
0x1400354ae  lea     r8, [rsi-18h]; SenderBuffer
0x1400354b2  lea     rax, [rbp+80h+ProcessId]
0x1400354b6  mov     [rsp+180h+Timeout], rax; Timeout
0x1400354bb  lea     rax, [rbp+80h+Process]
0x1400354bf  mov     [rsp+180h+ReplyLength], rax; ReplyLength
0x1400354c4  lea     rdx, [rcx+140h]; ClientPort
0x1400354cb  mov     rcx, [rcx+10h]; Filter
0x1400354cf  lea     rax, [rbp+80h+var_B0]
0x1400354d3  mov     [rsp+180h+ReplyBuffer], rax; ReplyBuffer
0x1400354d8  call    cs:__imp_FltSendMessage
0x1400354df  nop     dword ptr [rax+rax+00h]
0x1400354e4  cmp     [rbp+80h+TokenInformation], 0
0x1400354e9  mov     r14d, eax
0x1400354ec  jz      short loc_140035562
0x1400354ee  xor     ecx, ecx; PerformanceFrequency
0x1400354f0  call    cs:__imp_KeQueryPerformanceCounter
0x1400354f7  nop     dword ptr [rax+rax+00h]
0x1400354fc  mov     r8, [rbp+80h+TokenInformation]
0x140035500  mov     r10, rax
0x140035503  mov     r9, rax
0x140035506  sub     r10, rbx
0x140035509  imul    rax, r10, 3E8h
0x140035510  cqo
0x140035512  idiv    r8
0x140035515  mov     r13, rax
0x140035518  mov     rcx, cs:WPP_GLOBAL_Control
0x14003551f  cmp     rcx, r12
0x140035522  jz      short loc_140035530
0x140035524  mov     edx, [rcx+2Ch]
0x140035527  test    dl, 4
0x14003552a  jnz     loc_140035C3A
0x140035530  mov     rax, cs:MpData
0x140035537  mov     ecx, [rax+0BB8h]
0x14003553d  test    ecx, ecx
0x14003553f  js      loc_140035C5C
0x140035545  mov     rax, cs:MpData
0x14003554c  lock add [rax+0BB0h], r13
0x140035554  mov     rax, cs:MpData
0x14003555b  lock inc dword ptr [rax+0BB8h]
0x140035562  cmp     r14d, 102h
0x140035569  jz      loc_1400358DF
0x14003556f  test    r14d, r14d
0x140035572  js      loc_140035A7C
0x140035578  cmp     [rbp+80h+var_B0], 0A5h
0x14003557c  jnz     loc_140035DC3
0x140035582  cmp     [rbp+80h+var_AE], 70h ; 'p'
0x140035587  jnz     loc_140035DC3
0x14003558d  mov     rcx, cs:WPP_GLOBAL_Control
0x140035594  mov     r14, [rsp+180h+SourceString]
0x140035599  mov     rbx, [rsp+180h+var_110]
0x14003559e  cmp     rcx, r12
0x1400355a1  jnz     loc_14003570B
0x1400355a7  mov     eax, [r15+124h]
0x1400355ae  and     eax, 0FFFFFFF1h
0x1400355b1  or      eax, 1
0x1400355b4  cmp     [rbp+80h+var_60], 0
0x1400355b8  mov     [r15+124h], eax
0x1400355bf  jnz     loc_140035CF7
0x1400355c5  lea     rdx, [rbp+80h+var_A8]
0x1400355c9  mov     rcx, r15
0x1400355cc  call    MpSetProcessInfoByContext
0x1400355d1  mov     rax, cs:MpData
0x1400355d8  lock inc dword ptr [rax+0BC0h]
0x1400355df  test    byte ptr cs:WPP_MAIN_CB.DeviceExtension, 10h
0x1400355e6  jnz     loc_140035D75
0x1400355ec  xor     r14d, r14d
0x1400355ef  test    rsi, rsi
0x1400355f2  jz      short loc_1400355FC
0x1400355f4  mov     rcx, rsi
0x1400355f7  call    MpAsyncDereferenceNotification
0x1400355fc  test    rdi, rdi
0x1400355ff  jz      short loc_140035610
0x140035601  mov     rcx, rdi; PrimaryToken
0x140035604  call    cs:__imp_PsDereferencePrimaryToken
0x14003560b  nop     dword ptr [rax+rax+00h]
0x140035610  mov     rcx, [rbp+80h+P]; P
0x140035614  test    rcx, rcx
0x140035617  jz      short loc_140035627
0x140035619  xor     edx, edx; Tag
0x14003561b  call    cs:__imp_ExFreePoolWithTag
0x140035622  nop     dword ptr [rax+rax+00h]
0x140035627  mov     rcx, [rbp+80h+var_D0]; P
0x14003562b  test    rcx, rcx
0x14003562e  jz      short loc_14003563E
0x140035630  xor     edx, edx; Tag
0x140035632  call    cs:__imp_ExFreePoolWithTag
0x140035639  nop     dword ptr [rax+rax+00h]
0x14003563e  mov     rcx, [rbp+80h+var_E0]; P
0x140035642  test    rcx, rcx
0x140035645  jz      short loc_140035674
0x140035647  xor     edx, edx; Tag
  ... truncated ...
```
