# SmpStartCsr

- ea: `0x1400036d0`
- end: `0x1400041be`
- name: `SmpStartCsr`
- size: `2798`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140017c70`

## callees

- `0x1400010ec`
- `0x140001e40`
- `0x1400031b0`
- `0x1400036d0`
- `0x1400041d0`
- `0x140004610`
- `0x140004e30`
- `0x140004ec0`
- `0x140005030`
- `0x1400050a0`
- `0x1400053e0`
- `0x140005998`
- `0x140005ac4`
- `0x14000d4c0`
- `0x140014fc4`
- `0x1400151e0`
- `0x14001cc29`
- `0x14001cc40`

## import_xrefs

- `ntdll!NtQueryInformationProcess` at `0x140003907`
- `ntdll!NtQueryInformationProcess` at `0x140003907`
- `ntdll!NtClose` at `0x140003923`
- `ntdll!NtClose` at `0x14000392d`
- `ntdll!NtClose` at `0x140003a51`
- `ntdll!NtClose` at `0x140003bf5`
- `ntdll!NtClose` at `0x140003bff`
- `ntdll!NtClose` at `0x140003c1a`
- `ntdll!NtClose` at `0x1400041b3`
- `ntdll!NtClose` at `0x140003923`
- `ntdll!NtClose` at `0x14000392d`
- `ntdll!NtClose` at `0x140003a51`
- `ntdll!NtClose` at `0x140003bf5`
- `ntdll!NtClose` at `0x140003bff`
- `ntdll!NtClose` at `0x140003c1a`
- `ntdll!NtClose` at `0x1400041b3`
- `ntdll!RtlAllocateHeap` at `0x1400037de`
- `ntdll!RtlAllocateHeap` at `0x1400037de`
- `ntdll!RtlFreeHeap` at `0x140003c32`
- `ntdll!RtlFreeHeap` at `0x140003c32`
- `ntdll!RtlFreeUnicodeString` at `0x1400038ca`
- `ntdll!RtlFreeUnicodeString` at `0x1400038d5`
- `ntdll!RtlFreeUnicodeString` at `0x1400038e8`
- `ntdll!RtlFreeUnicodeString` at `0x140003e6b`
- `ntdll!RtlFreeUnicodeString` at `0x1400040b9`
- `ntdll!RtlFreeUnicodeString` at `0x1400040c4`
- `ntdll!RtlFreeUnicodeString` at `0x1400038ca`
- `ntdll!RtlFreeUnicodeString` at `0x1400038d5`
- `ntdll!RtlFreeUnicodeString` at `0x1400038e8`
- `ntdll!RtlFreeUnicodeString` at `0x140003e6b`
- `ntdll!RtlFreeUnicodeString` at `0x1400040b9`
- `ntdll!RtlFreeUnicodeString` at `0x1400040c4`
- `ntdll!RtlAppendUnicodeToString` at `0x140003842`
- `ntdll!RtlAppendUnicodeToString` at `0x140003842`
- `ntdll!RtlAppendUnicodeStringToString` at `0x14000380b`
- `ntdll!RtlAppendUnicodeStringToString` at `0x140003852`
- `ntdll!RtlAppendUnicodeStringToString` at `0x14000380b`
- `ntdll!RtlAppendUnicodeStringToString` at `0x140003852`
- `ntdll!NtResumeThread` at `0x140003a45`
- `ntdll!NtResumeThread` at `0x140003a45`
- `ntdll!NtWaitForSingleObject` at `0x14000375b`
- `ntdll!NtWaitForSingleObject` at `0x14000375b`
- `ntdll!NtTerminateProcess` at `0x140003919`
- `ntdll!NtTerminateProcess` at `0x140003919`
- `ntdll!NtUnmapViewOfSection` at `0x140003c10`
- `ntdll!NtUnmapViewOfSection` at `0x140003c10`
- `ntdll!RtlReleaseSRWLockShared` at `0x140003e95`
- `ntdll!RtlReleaseSRWLockShared` at `0x140003e95`
- `ntdll!RtlAcquireSRWLockShared` at `0x140003dd3`
- `ntdll!RtlAcquireSRWLockShared` at `0x140003dd3`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x140003a12`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x14000418c`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x140003a12`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x14000418c`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x140003a39`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1400041aa`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x140003a39`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1400041aa`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x14000417f`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x14000417f`
- `ntdll!RtlDeleteNoSplay` at `0x14000419d`
- `ntdll!RtlDeleteNoSplay` at `0x14000419d`
- `ntdll!RtlSleepConditionVariableSRW` at `0x140003dec`
- `ntdll!RtlSleepConditionVariableSRW` at `0x140003dec`
- `ntdll!NtWaitForMultipleObjects` at `0x140003a83`
- `ntdll!NtWaitForMultipleObjects` at `0x140003a83`
- `ntdll!NtClearEvent` at `0x140003f23`
- `ntdll!NtClearEvent` at `0x140003f23`
- `ntdll!NtQueryEvent` at `0x140003ee3`
- `ntdll!NtQueryEvent` at `0x140003ee3`

## string_xrefs

- `0x140003fe5`: `SmpAllocateInitialCommandBuffer`
- `0x140003e5a`: `SmpExecuteCommand`
- `0x14000409b`: `SmpExecuteCommand`
- `0x1400040cf`: `SmpExecuteCommand`

## pseudocode

```c
__int64 __fastcall SmpStartCsr(__int64 a1)
{
  __int64 v1; // r13
  __int64 v2; // rax
  char *ControlBlock; // rbx
  unsigned __int16 v5; // ax
  unsigned __int64 v6; // rsi
  __int64 v7; // r12
  WCHAR *Heap; // rax
  int v9; // esi
  __int64 v10; // r9
  int v11; // eax
  _QWORD *v13; // rcx
  unsigned int v14; // eax
  const char *v15; // r8
  __int64 v16; // rax
  __int128 *v17; // rcx
  __int64 v18; // rdx
  __int128 *v19; // rax
  __int128 v20; // xmm1
  __int64 v21; // rcx
  __int128 v22; // xmm0
  __int128 v23; // xmm1
  __int128 v24; // xmm0
  __int128 v25; // xmm1
  __int128 v26; // xmm0
  __int128 v27; // xmm1
  __int128 v28; // xmm0
  __int128 v29; // xmm1
  __int128 v30; // xmm0
  __int128 v31; // xmm1
  __int128 v32; // xmm0
  __int128 v33; // xmm1
  void *v34; // rdi
  int SubSystem; // eax
  __int64 v36; // rax
  __int64 v37; // rdx
  __int128 *v38; // rcx
  const char *v39; // rdi
  __int128 *v40; // rax
  __int128 v41; // xmm1
  __int64 v42; // rcx
  __int128 v43; // xmm0
  __int128 v44; // xmm1
  __int128 v45; // xmm0
  __int128 v46; // xmm1
  __int128 v47; // xmm0
  __int128 v48; // xmm1
  __int128 v49; // xmm0
  __int128 v50; // xmm1
  __int128 v51; // xmm0
  __int128 v52; // xmm1
  __int128 v53; // xmm0
  __int128 v54; // xmm1
  __int64 v55; // rbx
  __int64 v56; // rsi
  int v57; // r15d
  __int64 v58; // rbx
  PWSTR Buffer; // rdi
  __int64 v60; // rdx
  void *v61; // rcx
  __int64 v62; // rax
  __int128 *v63; // r8
  __int64 v64; // rdx
  __int128 *v65; // rcx
  int v66; // eax
  __int128 v67; // xmm1
  int ReturnLength; // [rsp+20h] [rbp-E0h]
  struct _UNICODE_STRING Destination; // [rsp+40h] [rbp-C0h] BYREF
  __int64 ProcessInformation; // [rsp+50h] [rbp-B0h] BYREF
  __int64 EventInformation; // [rsp+58h] [rbp-A8h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+60h] [rbp-A0h] BYREF
  UNICODE_STRING Source; // [rsp+70h] [rbp-90h] BYREF
  HANDLE Object[2]; // [rsp+80h] [rbp-80h] BYREF
  HANDLE ProcessHandle[2]; // [rsp+90h] [rbp-70h] BYREF
  HANDLE Handle[2]; // [rsp+A0h] [rbp-60h]
  __int128 v77; // [rsp+B0h] [rbp-50h]
  __int128 v78; // [rsp+C0h] [rbp-40h]
  __int128 v79; // [rsp+D0h] [rbp-30h]
  __int128 v80; // [rsp+E0h] [rbp-20h]
  __int64 v81; // [rsp+F0h] [rbp-10h]
  __int128 v82; // [rsp+100h] [rbp+0h]
  __int128 v83; // [rsp+110h] [rbp+10h] BYREF
  __int128 v84; // [rsp+120h] [rbp+20h]
  __int128 v85; // [rsp+130h] [rbp+30h]
  __int128 v86; // [rsp+140h] [rbp+40h]
  __int128 v87; // [rsp+150h] [rbp+50h] BYREF
  __int128 v88; // [rsp+160h] [rbp+60h]
  __int128 v89; // [rsp+170h] [rbp+70h]
  __int128 v90; // [rsp+180h] [rbp+80h]
  __int128 v91; // [rsp+190h] [rbp+90h]
  __int128 v92; // [rsp+1A0h] [rbp+A0h]
  __int128 v93; // [rsp+1B0h] [rbp+B0h]
  __int128 v94; // [rsp+1C0h] [rbp+C0h]
  __int128 v95; // [rsp+1D0h] [rbp+D0h]
  __int128 v96; // [rsp+1E0h] [rbp+E0h]
  wchar_t pszDest[20]; // [rsp+260h] [rbp+160h] BYREF

  v1 = 0;
  v81 = 0;
  v2 = *(unsigned int *)(a1 + 48);
  *(_OWORD *)Object = 0;
  LODWORD(ProcessInformation) = 0;
  Destination = 0;
  *(_OWORD *)ProcessHandle = 0;
  *(_OWORD *)Handle = 0;
  v77 = 0;
  v78 = 0;
  v79 = 0;
  v80 = 0;
  if ( (unsigned int)v2 < SmpNumberInitialSessions )
  {
    v55 = SmpCoreProcessIds + 40 * v2;
    v56 = v55 + 8;
    RtlAcquireSRWLockShared(v55 + 8);
    while ( !*(_DWORD *)(v55 + 4) )
      RtlSleepConditionVariableSRW(v55 + 16, v55 + 8, 0, 1);
    if ( *(_QWORD *)(v55 + 32) )
    {
      v57 = 0;
      v1 = *(_QWORD *)(v55 + 24);
      if ( v1 )
        _InterlockedIncrement((volatile signed __int32 *)v1);
      v58 = *(_QWORD *)(v55 + 32);
    }
    else
    {
      v58 = 0;
      v57 = -1073741823;
    }
    RtlReleaseSRWLockShared(v56);
    *(_DWORD *)(a1 + 48) = *(_DWORD *)(SmpCoreProcessIds + 40LL * *(unsigned int *)(a1 + 48));
    if ( v57 >= 0 )
    {
      memset_0(&v83, 0, 0x148u);
      if ( v1 && *(_DWORD *)(v1 + 24) == 2 )
      {
        *(_QWORD *)(a1 + 320) = *(_QWORD *)(v1 + 48);
      }
      else
      {
        v57 = -1073741823;
        if ( !v1 )
        {
LABEL_72:
          LODWORD(v86) = *(_DWORD *)(a1 + 48);
          DWORD2(v85) = 6;
          SmpStopCsr(&v83, 0, 0);
          return (unsigned int)v57;
        }
      }
      SmpDereferenceKnownSubSys((PVOID)v1);
      if ( v57 >= 0 )
      {
        *(_QWORD *)(a1 + 312) = v58;
        return 0;
      }
      goto LABEL_72;
    }
  }
  NtWaitForSingleObject(SmpSessionCreateBlockEvent, 0, 0);
  Destination.Length = *(_WORD *)(a1 + 52);
  Destination.MaximumLength = Destination.Length;
  Destination.Buffer = (PWSTR)(a1 + 56);
  ControlBlock = (char *)SmpAllocateControlBlock();
  if ( ControlBlock )
  {
    v5 = _mm_cvtsi128_si32((__m128i)Destination);
    Source = Destination;
    v6 = SmpHelperCmd.Length + 40LL + v5;
    if ( v6 > 0xFFFF )
    {
      v9 = -1073741811;
    }
    else
    {
      v7 = *((_QWORD *)ControlBlock + 3);
      Heap = (WCHAR *)RtlAllocateHeap(
                        *(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL),
                        SmBaseTag + 0x80000,
                        SmpHelperCmd.Length + 40LL + v5);
      if ( Heap )
      {
        *(_QWORD *)&Destination.Length = 0;
        Destination.MaximumLength = v6;
        Destination.Buffer = Heap;
        RtlAppendUnicodeStringToString(&Destination, &SmpHelperCmd);
        RtlStringCbPrintfW(pszDest, 0x28u, L" %08x %08x ", (unsigned int)v7, (_DWORD)SmpSharedSection);
        RtlAppendUnicodeToString(&Destination, pszDest);
        RtlAppendUnicodeStringToString(&Destination, &Source);
        LODWORD(EventInformation) = 5152;
        UnicodeString = 0;
        v82 = 0;
        Source = 0;
        v9 = SmpParseCommandLine((__int64)&Destination, &EventInformation, &UnicodeString, 0, &Source);
        if ( v9 < 0 )
        {
          Buffer = Destination.Buffer;
          memset_0(&v83, 0, 0xE0u);
          if ( Buffer )
          {
            v62 = 2147483646;
            v63 = &v87;
            v64 = 64;
            do
            {
              if ( !v62 )
                break;
              if ( !*Buffer )
                break;
              *(_WORD *)v63 = *Buffer++;
              v63 = (__int128 *)((char *)v63 + 2);
              --v62;
              --v64;
            }
            while ( v64 );
            v65 = (__int128 *)((char *)v63 - 2);
            if ( v64 )
              v65 = v63;
            *(_WORD *)v65 = 0;
          }
          SmpInternalLogFailure("SmpExecuteCommand", 10151, (unsigned int)v9, &v83);
          goto LABEL_50;
        }
        if ( (EventInformation & 4) != 0 )
        {
          if ( SmpSoftBoot && !SmpBugcheckRecovery )
          {
LABEL_9:
            RtlFreeUnicodeString(&UnicodeString);
            RtlFreeUnicodeString(&Source);
            if ( v9 >= 0 )
            {
              RtlFreeUnicodeString(&Destination);
              v11 = NtQueryInformationProcess(ProcessHandle[1], ProcessSessionInformation, &ProcessInformation, 4u, 0);
              v9 = v11;
              if ( v11 < 0 )
              {
                NtTerminateProcess(ProcessHandle[1], v11);
                NtClose(ProcessHandle[1]);
                NtClose(Handle[0]);
LABEL_12:
                memset_0(&v83, 0, 0x148u);
                if ( _InterlockedExchangeAdd((volatile signed __int32 *)ControlBlock + 1, 0xFFFFFFFF) <= 1 )
                {
                  v34 = (void *)*((_QWORD *)ControlBlock + 6);
                  if ( v34 )
                  {
                    if ( (*ControlBlock & 1) == 0 && *((_QWORD *)ControlBlock + 9) != SmpUniqueProcessId )
                    {
                      v66 = *((_DWORD *)ControlBlock + 2);
                      v67 = *((_OWORD *)ControlBlock + 5);
                      v83 = *((_OWORD *)ControlBlock + 4);
                      *(_QWORD *)&v85 = *((_QWORD *)ControlBlock + 12);
                      v84 = v67;
                      *((_QWORD *)&v85 + 1) = 0xC000000100000005uLL;
                      LODWORD(v86) = v66;
                      NtAlpcSendWaitReceivePort(
                        SmpApiConnectionPort,
                        0x10000,
                        &v83,
                        0,
                        0,
                        0,
                        0,
                        0,
                        *(_QWORD *)&Destination.Length,
                        Destination.Buffer,
                        ProcessInformation);
                    }
                    RtlAcquireSRWLockExclusive(&SmpControlLock);
                    RtlDeleteNoSplay((PRTL_SPLAY_LINKS)(ControlBlock + 104), &SmpControlBlockRoot);
                    RtlReleaseSRWLockExclusive(&SmpControlLock);
                    NtClose(v34);
                  }
                  NtClose(*((HANDLE *)ControlBlock + 4));
                  NtClose(*((HANDLE *)ControlBlock + 5));
                  NtUnmapViewOfSection((HANDLE)0xFFFFFFFFFFFFFFFFLL, *((PVOID *)ControlBlock + 2));
                  NtClose(*((HANDLE *)ControlBlock + 3));
                  RtlFreeHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), 0, ControlBlock);
                }
                return (unsigned int)v9;
              }
              v13 = (_QWORD *)*((_QWORD *)ControlBlock + 2);
              *v13 = *((_QWORD *)ControlBlock + 4);
              v13[1] = *((_QWORD *)ControlBlock + 5);
              *((HANDLE *)ControlBlock + 6) = ProcessHandle[1];
              *((HANDLE *)ControlBlock + 7) = Handle[1];
              *((_DWORD *)ControlBlock + 2) = ProcessInformation;
              v14 = _InterlockedIncrement(&dword_140030338);
              if ( v14 <= SmpNumberInitialSessions )
                *(_DWORD *)(SmpCoreProcessIds + 40LL * (v14 - 1)) = ProcessInformation;
              else
                _InterlockedDecrement(&dword_140030338);
              *((_OWORD *)ControlBlock + 4) = *(_OWORD *)a1;
              *((_OWORD *)ControlBlock + 5) = *(_OWORD *)(a1 + 16);
              *((_QWORD *)ControlBlock + 12) = *(_QWORD *)(a1 + 32);
              *((_QWORD *)ControlBlock + 13) = ControlBlock + 104;
              *((_QWORD *)ControlBlock + 14) = 0;
              *((_QWORD *)ControlBlock + 15) = 0;
              ++*((_DWORD *)ControlBlock + 1);
              RtlAcquireSRWLockExclusive(&SmpControlLock);
              if ( (unsigned int)SmpInsertControlBlock(SmpControlBlockRoot, ControlBlock) )
                SmpControlBlockRoot = (PRTL_SPLAY_LINKS)(ControlBlock + 104);
              RtlReleaseSRWLockExclusive(&SmpControlLock);
              v9 = NtResumeThread(Handle[0], 0);
              NtClose(Handle[0]);
              if ( v9 < 0 )
              {
                if ( (*ControlBlock & 1) == 0 )
                  _InterlockedOr((volatile signed __int32 *)ControlBlock, 1u);
                SmpDestroyControlBlock(ControlBlock);
                goto LABEL_12;
              }
              Object[0] = *((HANDLE *)ControlBlock + 6);
              Object[1] = *((HANDLE *)ControlBlock + 4);
              v9 = NtWaitForMultipleObjects(2u, Object, WaitAny, 0, 0);
              if ( v9 < 0 )
              {
                memset_0(&v83, 0, 0xE0u);
                LODWORD(v95) = v9;
                v15 = "SmpStartCsr";
                DWORD2(v96) = 595;
                v16 = 2147483646;
                v17 = &v83;
                v18 = 64;
                do
                {
                  if ( !v16 )
                    break;
                  if ( !*v15 )
                    break;
                  *(_BYTE *)v17 = *v15++;
                  v17 = (__int128 *)((char *)v17 + 1);
                  --v16;
                  --v18;
                }
                while ( v18 );
                v19 = (__int128 *)((char *)v17 - 1);
                if ( v18 )
                  v19 = v17;
                *(_BYTE *)v19 = 0;
                v20 = v84;
                v21 = 224LL * (_InterlockedIncrement(&dword_14002EE94) % 16);
                *(_OWORD *)&SmpBlackboxBuffer[v21 + 8] = v83;
                v22 = v85;
                *(_OWORD *)&SmpBlackboxBuffer[v21 + 24] = v20;
                v23 = v86;
                *(_OWORD *)&SmpBlackboxBuffer[v21 + 40] = v22;
                v24 = v87;
                *(_OWORD *)&SmpBlackboxBuffer[v21 + 56] = v23;
                v25 = v88;
                *(_OWORD *)&SmpBlackboxBuffer[v21 + 72] = v24;
                v26 = v89;
                *(_OWORD *)&SmpBlackboxBuffer[v21 + 88] = v25;
                v27 = v90;
                *(_OWORD *)&SmpBlackboxBuffer[v21 + 104] = v26;
                v28 = v91;
                *(_OWORD *)&SmpBlackboxBuffer[v21 + 120] = v27;
                v29 = v92;
                *(_OWORD *)&SmpBlackboxBuffer[v21 + 136] = v28;
                v30 = v93;
                *(_OWORD *)&SmpBlackboxBuffer[v21 + 152] = v29;
                v31 = v94;
                *(_OWORD *)&SmpBlackboxBuffer[v21 + 168] = v30;
                v32 = v95;
                *(_OWORD *)&SmpBlackboxBuffer[v21 + 184] = v31;
                v33 = v96;
                *(_OWORD *)&SmpBlackboxBuffer[v21 + 200] = v32;
                *(_OWORD *)&SmpBlackboxBuffer[v21 + 216] = v33;
                if ( (*ControlBlock & 1) != 0 )
                  goto LABEL_27;
                _m_prefetchw(ControlBlock);
                if ( (_InterlockedOr((volatile signed __int32 *)ControlBlock, 1u) & 1) != 0 )
                  goto LABEL_27;
                goto LABEL_60;
              }
              if ( !v9 )
              {
                v61 = (void *)*((_QWORD *)ControlBlock + 4);
                EventInformation = 0;
                NtQueryEvent(v61, EventBasicInformation, &EventInformation, 8u, 0);
                if ( !HIDWORD(EventInformation) )
                {
                  if ( (*ControlBlock & 1) == 0 )
                    _InterlockedOr((volatile signed __int32 *)ControlBlock, 1u);
                  v9 = -1073741823;
                  goto LABEL_60;
                }
                v9 = NtClearEvent(*((HANDLE *)ControlBlock + 4));
                if ( v9 < 0 )
                {
LABEL_60:
                  SmpDestroyControlBlock(ControlBlock);
                  v60 = 646;
                  goto LABEL_51;
                }
              }
LABEL_27:
              SmpReleaseControlBlock(ControlBlock);
              return 259;
            }
            goto LABEL_88;
          }
          SubSystem = SmpInvokeAutoChk(&UnicodeString);
        }
        else if ( (EventInformation & 8) != 0 )
        {
          if ( SmpPrimarySmss )
            SubSystem = SmpLoadSubSystem(
                          (unsigned int)&UnicodeString,
                          0,
                          (unsigned int)&Destination,
                          0,
                          ReturnLength,
                          EventInformation);
          else
            SubSystem = SmscpLoadSubSystem(&UnicodeString.Length, 0, (__int64)&Destination, 0, EventInformation);
        }
        else
        {
          if ( (EventInformation & 0x10) != 0 )
          {
            v9 = -1073741772;
            SmpLogFailureString("SmpExecuteCommand", 10189, UnicodeString.Buffer, 3221225524LL);
            RtlFreeUnicodeString(&UnicodeString);
            RtlFreeUnicodeString(&Source);
LABEL_88:
            SmpLogFailureString("SmpExecuteCommand", 10217, Destination.Buffer, (unsigned int)v9);
LABEL_50:
            RtlFreeUnicodeString(&Destination);
            v60 = 491;
LABEL_51:
            SmpLogFailure("SmpStartCsr", v60, (unsigned int)v9);
            goto LABEL_12;
          }
          SubSystem = SmpExecuteImage(
                        (__int64)&UnicodeString,
                        0,
                        (__int64)&Destination,
                        v10,
                        0,
                        EventInformation,
                        ProcessHandle);
        }
        v9 = SubSystem;
        goto LABEL_9;
      }
      memset_0(&v83, 0, 0xE0u);
      v9 = -1073741801;
      SmpInternalLogFailure("SmpAllocateInitialCommandBuffer", 285, 3221225495LL, &v83);
    }
    v60 = 471;
    goto LABEL_51;
  }
  memset_0(&v83, 0, 0xE0u);
  v36 = 2147483646;
  LODWORD(v95) = -1073741670;
  v37 = 64;
  DWORD2(v96) = 460;
  v38 = &v83;
  v39 = "SmpStartCsr";
  do
  {
    if ( !v36 )
      break;
    if ( !*v39 )
      break;
    *(_BYTE *)v38 = *v39++;
    v38 = (__int128 *)((char *)v38 + 1);
    --v36;
    --v37;
  }
  while ( v37 );
  v40 = (__int128 *)((char *)v38 - 1);
  if ( v37 )
    v40 = v38;
  *(_BYTE *)v40 = 0;
  v41 = v84;
  v42 = 224LL * (_InterlockedIncrement(&dword_14002EE94) % 16);
  *(_OWORD *)&SmpBlackboxBuffer[v42 + 8] = v83;
  v43 = v85;
  *(_OWORD *)&SmpBlackboxBuffer[v42 + 24] = v41;
  v44 = v86;
  *(_OWORD *)&SmpBlackboxBuffer[v42 + 40] = v43;
  v45 = v87;
  *(_OWORD *)&SmpBlackboxBuffer[v42 + 56] = v44;
  v46 = v88;
  *(_OWORD *)&SmpBlackboxBuffer[v42 + 72] = v45;
  v47 = v89;
  *(_OWORD *)&SmpBlackboxBuffer[v42 + 88] = v46;
  v48 = v90;
  *(_OWORD *)&SmpBlackboxBuffer[v42 + 104] = v47;
  v49 = v91;
  *(_OWORD *)&SmpBlackboxBuffer[v42 + 120] = v48;
  v50 = v92;
  *(_OWORD *)&SmpBlackboxBuffer[v42 + 136] = v49;
  v51 = v93;
  *(_OWORD *)&SmpBlackboxBuffer[v42 + 152] = v50;
  v52 = v94;
  *(_OWORD *)&SmpBlackboxBuffer[v42 + 168] = v51;
  v53 = v95;
  *(_OWORD *)&SmpBlackboxBuffer[v42 + 184] = v52;
  v54 = v96;
  *(_OWORD *)&SmpBlackboxBuffer[v42 + 200] = v53;
  *(_OWORD *)&SmpBlackboxBuffer[v42 + 216] = v54;
  return 3221225626LL;
}

```

## disassembly

```asm
0x1400036d0  mov     [rsp-8+arg_10], rbx
0x1400036d5  mov     [rsp-8+arg_18], rsi
0x1400036da  push    rbp
0x1400036db  push    rdi
0x1400036dc  push    r13
0x1400036de  push    r14
0x1400036e0  push    r15
0x1400036e2  lea     rbp, [rsp-190h]
0x1400036ea  sub     rsp, 290h
0x1400036f1  mov     rax, cs:__security_cookie
0x1400036f8  xor     rax, rsp
0x1400036fb  mov     [rbp+1B0h+var_28], rax
0x140003702  xorps   xmm0, xmm0
0x140003705  xor     eax, eax
0x140003707  xor     r13d, r13d
0x14000370a  mov     [rbp+1B0h+var_1C0], rax
0x14000370e  mov     eax, [rcx+30h]
0x140003711  xorps   xmm1, xmm1
0x140003714  cmp     eax, cs:SmpNumberInitialSessions
0x14000371a  mov     rdi, rcx
0x14000371d  movups  xmmword ptr [rbp+1B0h+Object], xmm0
0x140003721  mov     dword ptr [rsp+2B0h+ProcessInformation], r13d
0x140003726  mov     r14d, 1
0x14000372c  movups  xmmword ptr [rsp+2B0h+Destination.Length], xmm1
0x140003731  movups  xmmword ptr [rbp+1B0h+ProcessHandle], xmm0
0x140003735  movups  xmmword ptr [rbp+1B0h+Handle], xmm0
0x140003739  movups  [rbp+1B0h+var_200], xmm0
0x14000373d  movups  [rbp+1B0h+var_1F0], xmm0
0x140003741  movups  [rbp+1B0h+var_1E0], xmm0
0x140003745  movups  [rbp+1B0h+var_1D0], xmm0
0x140003749  jb      loc_140003DBD
0x14000374f  mov     rcx, cs:SmpSessionCreateBlockEvent; Object
0x140003756  xor     r8d, r8d; Timeout
0x140003759  xor     edx, edx; Alertable
0x14000375b  call    cs:__imp_NtWaitForSingleObject
0x140003761  movzx   eax, word ptr [rdi+34h]
0x140003765  mov     [rsp+2B0h+Destination.Length], ax
0x14000376a  mov     [rsp+2B0h+Destination.MaximumLength], ax
0x14000376f  lea     rax, [rdi+38h]
0x140003773  mov     [rsp+2B0h+Destination.Buffer], rax
0x140003778  call    SmpAllocateControlBlock
0x14000377d  mov     rbx, rax
0x140003780  test    rax, rax
0x140003783  jz      loc_140003C77
0x140003789  movaps  xmm0, xmmword ptr [rsp+2B0h+Destination.Length]
0x14000378e  movzx   ecx, cs:SmpHelperCmd.Length
0x140003795  add     rcx, 28h ; '('
0x140003799  movd    eax, xmm0
0x14000379d  mov     [rsp+2B0h+arg_8], r12
0x1400037a5  movdqa  xmmword ptr [rsp+2B0h+Source.Length], xmm0
0x1400037ab  movzx   esi, ax
0x1400037ae  add     rsi, rcx
0x1400037b1  cmp     rsi, 0FFFFh
0x1400037b8  ja      loc_140003FC1
0x1400037be  mov     rcx, gs:60h
0x1400037c7  mov     r8, rsi; Size
0x1400037ca  mov     edx, cs:SmBaseTag
0x1400037d0  mov     r12, [rbx+18h]
0x1400037d4  add     edx, 80000h; Flags
0x1400037da  mov     rcx, [rcx+30h]; HeapHandle
0x1400037de  call    cs:__imp_RtlAllocateHeap
0x1400037e4  test    rax, rax
0x1400037e7  jz      loc_140003FC8
0x1400037ed  xorps   xmm0, xmm0
0x1400037f0  lea     rdx, SmpHelperCmd; Source
0x1400037f7  movups  xmmword ptr [rsp+2B0h+Destination.Length], xmm0
0x1400037fc  lea     rcx, [rsp+2B0h+Destination]; Destination
0x140003801  mov     [rsp+2B0h+Destination.MaximumLength], si
0x140003806  mov     [rsp+2B0h+Destination.Buffer], rax
0x14000380b  call    cs:__imp_RtlAppendUnicodeStringToString
0x140003811  mov     eax, dword ptr cs:SmpSharedSection
0x140003817  lea     r8, a08x08x; " %08x %08x "
0x14000381e  mov     r9d, r12d
0x140003821  mov     dword ptr [rsp+2B0h+ReturnLength], eax
0x140003825  mov     edx, 28h ; '('; cbDest
0x14000382a  lea     rcx, [rbp+1B0h+pszDest]; pszDest
0x140003831  call    RtlStringCbPrintfW
0x140003836  lea     rdx, [rbp+1B0h+pszDest]; Source
0x14000383d  lea     rcx, [rsp+2B0h+Destination]; Destination
0x140003842  call    cs:__imp_RtlAppendUnicodeToString
0x140003848  lea     rdx, [rsp+2B0h+Source]; Source
0x14000384d  lea     rcx, [rsp+2B0h+Destination]; Destination
0x140003852  call    cs:__imp_RtlAppendUnicodeStringToString
0x140003858  xorps   xmm0, xmm0
0x14000385b  mov     dword ptr [rsp+2B0h+EventInformation], 1420h
0x140003863  xorps   xmm1, xmm1
0x140003866  lea     rax, [rsp+2B0h+Source]
0x14000386b  xor     r9d, r9d
0x14000386e  mov     [rsp+2B0h+ReturnLength], rax
0x140003873  lea     r8, [rsp+2B0h+UnicodeString]
0x140003878  lea     rdx, [rsp+2B0h+EventInformation]
0x14000387d  lea     rcx, [rsp+2B0h+Destination]
0x140003882  movups  xmmword ptr [rsp+2B0h+UnicodeString.Length], xmm0
0x140003887  movups  [rbp+1B0h+var_1B0], xmm1
0x14000388b  movups  xmmword ptr [rsp+2B0h+Source.Length], xmm0
0x140003890  call    SmpParseCommandLine
0x140003895  mov     esi, eax
0x140003897  test    eax, eax
0x140003899  js      loc_140003E2F
0x14000389f  mov     eax, dword ptr [rsp+2B0h+EventInformation]
0x1400038a3  test    al, 4
0x1400038a5  jz      loc_140003C3D
0x1400038ab  cmp     cs:SmpSoftBoot, 0
0x1400038b2  jz      loc_14000404A
0x1400038b8  cmp     cs:SmpBugcheckRecovery, 0
0x1400038bf  jnz     loc_14000404A
0x1400038c5  lea     rcx, [rsp+2B0h+UnicodeString]; UnicodeString
0x1400038ca  call    cs:__imp_RtlFreeUnicodeString
0x1400038d0  lea     rcx, [rsp+2B0h+Source]; UnicodeString
0x1400038d5  call    cs:__imp_RtlFreeUnicodeString
0x1400038db  test    esi, esi
0x1400038dd  js      loc_1400040CA
0x1400038e3  lea     rcx, [rsp+2B0h+Destination]; UnicodeString
0x1400038e8  call    cs:__imp_RtlFreeUnicodeString
0x1400038ee  mov     rcx, [rbp+1B0h+ProcessHandle+8]; ProcessHandle
0x1400038f2  lea     r8, [rsp+2B0h+ProcessInformation]; ProcessInformation
0x1400038f7  mov     r9d, 4; ProcessInformationLength
0x1400038fd  mov     [rsp+2B0h+ReturnLength], r13; ReturnLength
0x140003902  mov     edx, 18h; ProcessInformationClass
0x140003907  call    cs:__imp_NtQueryInformationProcess
0x14000390d  mov     esi, eax
0x14000390f  test    eax, eax
0x140003911  jns     short loc_14000398C
0x140003913  mov     rcx, [rbp+1B0h+ProcessHandle+8]; ProcessHandle
0x140003917  mov     edx, eax; ExitStatus
0x140003919  call    cs:__imp_NtTerminateProcess
0x14000391f  mov     rcx, [rbp+1B0h+ProcessHandle+8]; Handle
0x140003923  call    cs:__imp_NtClose
0x140003929  mov     rcx, [rbp+1B0h+Handle]; Handle
0x14000392d  call    cs:__imp_NtClose
0x140003933  xor     edx, edx; Val
0x140003935  lea     rcx, [rbp+1B0h+var_1A0]; void *
0x140003939  mov     r8d, 148h; Size
0x14000393f  call    memset_0
0x140003944  mov     eax, 0FFFFFFFFh
0x140003949  lock xadd [rbx+4], eax
0x14000394e  sub     eax, 1
0x140003951  jle     loc_140003BE4
0x140003957  mov     eax, esi
0x140003959  mov     r12, [rsp+2B0h+arg_8]
0x140003961  mov     rcx, [rbp+1B0h+var_28]
0x140003968  xor     rcx, rsp; StackCookie
0x14000396b  call    __security_check_cookie
0x140003970  lea     r11, [rsp+2B0h+var_20]
0x140003978  mov     rbx, [r11+40h]
0x14000397c  mov     rsi, [r11+48h]
0x140003980  mov     rsp, r11
0x140003983  pop     r15
0x140003985  pop     r14
0x140003987  pop     r13
0x140003989  pop     rdi
0x14000398a  pop     rbp
0x14000398b  retn
0x14000398c  mov     rax, [rbx+20h]
0x140003990  mov     rcx, [rbx+10h]
0x140003994  mov     [rcx], rax
0x140003997  mov     rax, [rbx+28h]
0x14000399b  mov     [rcx+8], rax
0x14000399f  mov     rax, [rbp+1B0h+ProcessHandle+8]
0x1400039a3  mov     [rbx+30h], rax
0x1400039a7  mov     rax, [rbp+1B0h+Handle+8]
0x1400039ab  mov     [rbx+38h], rax
0x1400039af  mov     eax, dword ptr [rsp+2B0h+ProcessInformation]
0x1400039b3  mov     [rbx+8], eax
0x1400039b6  mov     eax, r14d
0x1400039b9  mov     r8d, dword ptr [rsp+2B0h+ProcessInformation]
0x1400039be  lock xadd cs:dword_140030338, eax
0x1400039c6  inc     eax
0x1400039c8  cmp     eax, cs:SmpNumberInitialSessions
0x1400039ce  jbe     loc_140003E19
0x1400039d4  lock dec cs:dword_140030338
0x1400039db  movups  xmm0, xmmword ptr [rdi]
0x1400039de  lea     rcx, SmpControlLock
0x1400039e5  movups  xmmword ptr [rbx+40h], xmm0
0x1400039e9  movups  xmm1, xmmword ptr [rdi+10h]
0x1400039ed  movups  xmmword ptr [rbx+50h], xmm1
0x1400039f1  movsd   xmm0, qword ptr [rdi+20h]
0x1400039f6  lea     rdi, [rbx+68h]
0x1400039fa  movsd   qword ptr [rbx+60h], xmm0
0x1400039ff  mov     [rdi], rdi
0x140003a02  mov     [rdi+8], r13
0x140003a06  mov     [rdi+10h], r13
0x140003a0a  mov     eax, [rbx+4]
0x140003a0d  inc     eax
0x140003a0f  mov     [rbx+4], eax
0x140003a12  call    cs:__imp_RtlAcquireSRWLockExclusive
0x140003a18  mov     rcx, cs:SmpControlBlockRoot
0x140003a1f  mov     rdx, rbx
0x140003a22  call    SmpInsertControlBlock
0x140003a27  test    eax, eax
0x140003a29  jz      short loc_140003A32
0x140003a2b  mov     cs:SmpControlBlockRoot, rdi
0x140003a32  lea     rcx, SmpControlLock
0x140003a39  call    cs:__imp_RtlReleaseSRWLockExclusive
0x140003a3f  mov     rcx, [rbp+1B0h+Handle]; ThreadHandle
0x140003a43  xor     edx, edx; SuspendCount
0x140003a45  call    cs:__imp_NtResumeThread
0x140003a4b  mov     rcx, [rbp+1B0h+Handle]; Handle
0x140003a4f  mov     esi, eax
0x140003a51  call    cs:__imp_NtClose
0x140003a57  test    esi, esi
0x140003a59  js      loc_140003F35
0x140003a5f  mov     rax, [rbx+30h]
0x140003a63  lea     rdx, [rbp+1B0h+Object]; Object
0x140003a67  mov     [rbp+1B0h+Object], rax
0x140003a6b  xor     r9d, r9d; Alertable
0x140003a6e  mov     rax, [rbx+20h]
0x140003a72  mov     r8d, r14d; WaitType
0x140003a75  mov     ecx, 2; Count
0x140003a7a  mov     [rbp+1B0h+Object+8], rax
0x140003a7e  mov     [rsp+2B0h+ReturnLength], r13; Time
0x140003a83  call    cs:__imp_NtWaitForMultipleObjects
0x140003a89  mov     esi, eax
0x140003a8b  test    eax, eax
0x140003a8d  jns     loc_140003EC0
0x140003a93  xor     edx, edx; Val
0x140003a95  lea     rcx, [rbp+1B0h+var_1A0]; void *
0x140003a99  mov     r8d, 0E0h; Size
0x140003a9f  call    memset_0
0x140003aa4  lea     rdi, aSmpstartcsr; "SmpStartCsr"
0x140003aab  mov     dword ptr [rbp+1B0h+var_E0], esi
0x140003ab1  mov     r8, rdi
0x140003ab4  mov     [rbp+1B0h+var_C8], 253h
0x140003abe  mov     eax, 7FFFFFFEh
0x140003ac3  lea     rcx, [rbp+1B0h+var_1A0]
0x140003ac7  mov     edx, 40h ; '@'
0x140003acc  test    rax, rax
0x140003acf  jz      short loc_140003AEB
0x140003ad1  movzx   r9d, byte ptr [r8]
0x140003ad5  test    r9b, r9b
0x140003ad8  jz      short loc_140003AEB
0x140003ada  mov     [rcx], r9b
0x140003add  inc     r8
0x140003ae0  inc     rcx
0x140003ae3  dec     rax
0x140003ae6  sub     rdx, r14
0x140003ae9  jnz     short loc_140003ACC
0x140003aeb  test    rdx, rdx
0x140003aee  lea     rax, [rcx-1]
0x140003af2  cmovnz  rax, rcx
0x140003af6  mov     byte ptr [rax], 0
0x140003af9  mov     eax, r14d
0x140003afc  lock xadd cs:dword_14002EE94, eax
0x140003b04  inc     eax
0x140003b06  and     eax, 8000000Fh
0x140003b0b  jge     short loc_140003B14
0x140003b0d  dec     eax
0x140003b0f  or      eax, 0FFFFFFF0h
0x140003b12  inc     eax
0x140003b14  movaps  xmm0, [rbp+1B0h+var_1A0]
0x140003b18  movaps  xmm1, [rbp+1B0h+var_190]
0x140003b1c  cdqe
0x140003b1e  imul    rcx, rax, 0E0h
0x140003b25  lea     rax, SmpBlackboxBuffer
0x140003b2c  movups  xmmword ptr [rcx+rax+8], xmm0
0x140003b31  movaps  xmm0, [rbp+1B0h+var_180]
0x140003b35  movups  xmmword ptr [rcx+rax+18h], xmm1
0x140003b3a  movaps  xmm1, [rbp+1B0h+var_170]
0x140003b3e  movups  xmmword ptr [rcx+rax+28h], xmm0
0x140003b43  movaps  xmm0, [rbp+1B0h+var_160]
0x140003b47  movups  xmmword ptr [rcx+rax+38h], xmm1
0x140003b4c  movaps  xmm1, [rbp+1B0h+var_150]
0x140003b50  movups  xmmword ptr [rcx+rax+48h], xmm0
0x140003b55  movaps  xmm0, [rbp+1B0h+var_140]
0x140003b59  movups  xmmword ptr [rcx+rax+58h], xmm1
0x140003b5e  movaps  xmm1, [rbp+1B0h+var_130]
0x140003b65  movups  xmmword ptr [rcx+rax+68h], xmm0
0x140003b6a  movaps  xmm0, [rbp+1B0h+var_120]
0x140003b71  movups  xmmword ptr [rcx+rax+78h], xmm1
0x140003b76  movaps  xmm1, [rbp+1B0h+var_110]
0x140003b7d  movups  xmmword ptr [rcx+rax+88h], xmm0
0x140003b85  movaps  xmm0, [rbp+1B0h+var_100]
0x140003b8c  movups  xmmword ptr [rcx+rax+98h], xmm1
0x140003b94  movaps  xmm1, [rbp+1B0h+var_F0]
0x140003b9b  movups  xmmword ptr [rcx+rax+0A8h], xmm0
0x140003ba3  movaps  xmm0, [rbp+1B0h+var_E0]
0x140003baa  movups  xmmword ptr [rcx+rax+0B8h], xmm1
0x140003bb2  movaps  xmm1, xmmword ptr [rbp+0E0h]
0x140003bb9  movups  xmmword ptr [rcx+rax+0C8h], xmm0
0x140003bc1  movups  xmmword ptr [rcx+rax+0D8h], xmm1
0x140003bc9  test    [rbx], r14b
0x140003bcc  jz      loc_1400040F1
0x140003bd2  mov     rcx, rbx; BaseAddress
0x140003bd5  call    SmpReleaseControlBlock
0x140003bda  mov     eax, 103h
0x140003bdf  jmp     loc_140003959
0x140003be4  mov     rdi, [rbx+30h]
0x140003be8  test    rdi, rdi
0x140003beb  jnz     loc_140004118
0x140003bf1  mov     rcx, [rbx+20h]; Handle
0x140003bf5  call    cs:__imp_NtClose
0x140003bfb  mov     rcx, [rbx+28h]; Handle
0x140003bff  call    cs:__imp_NtClose
0x140003c05  mov     rdx, [rbx+10h]; BaseAddress
0x140003c09  mov     rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x140003c10  call    cs:__imp_NtUnmapViewOfSection
0x140003c16  mov     rcx, [rbx+18h]; Handle
0x140003c1a  call    cs:__imp_NtClose
0x140003c20  mov     rcx, gs:60h
0x140003c29  mov     r8, rbx; BaseAddress
  ... truncated ...
```
