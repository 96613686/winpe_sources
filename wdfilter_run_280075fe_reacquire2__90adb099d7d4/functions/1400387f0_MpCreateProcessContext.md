# MpCreateProcessContext

- ea: `0x1400387f0`
- end: `0x1400393e8`
- name: `MpCreateProcessContext`
- size: `3064`
- prototype: `__int64 __fastcall(HANDLE ProcessId)`
- caller_count: `3`
- callee_count: `28`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x14002b880`
- `0x140036780`
- `0x140083f64`

## callees

- `0x1400018a4`
- `0x1400034e0`
- `0x140004530`
- `0x1400049dc`
- `0x1400051bc`
- `0x14000572c`
- `0x140005e78`
- `0x14000a51c`
- `0x14000ee90`
- `0x1400118d0`
- `0x140011bc0`
- `0x140030060`
- `0x140037cfc`
- `0x140037e2c`
- `0x140037e78`
- `0x140038370`
- `0x140038404`
- `0x1400384b4`
- `0x140038710`
- `0x1400387f0`
- `0x14003a570`
- `0x140064160`
- `0x140065d00`
- `0x140068890`
- `0x14006bfb0`
- `0x14006dd18`
- `0x14006eba0`
- `0x1400782cc`

## import_xrefs

- `ntoskrnl!ObOpenObjectByPointer` at `0x140038957`
- `ntoskrnl!ObOpenObjectByPointer` at `0x140038957`
- `ntoskrnl!PsProcessType` at `0x14003893a`
- `ntoskrnl!PsLookupProcessByProcessId` at `0x14003890a`
- `ntoskrnl!PsLookupProcessByProcessId` at `0x14003890a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140038db8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400392d5`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140038db8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400392d5`
- `ntoskrnl!ExReleaseResourceLite` at `0x140038dac`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400392c9`
- `ntoskrnl!ExReleaseResourceLite` at `0x140038dac`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400392c9`
- `ntoskrnl!ZwQueryInformationProcess` at `0x140038ab3`
- `ntoskrnl!ZwQueryInformationProcess` at `0x140038c32`
- `ntoskrnl!ZwQueryInformationProcess` at `0x140038ab3`
- `ntoskrnl!ZwQueryInformationProcess` at `0x140038c32`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140038cb7`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140038cb7`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140038ca5`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140038ca5`
- `ntoskrnl!ZwClose` at `0x140038ae2`
- `ntoskrnl!ZwClose` at `0x140038ae2`
- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x140038d1e`
- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x140038d1e`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140039035`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140039035`
- `ntoskrnl!KeBugCheck` at `0x140038d45`
- `ntoskrnl!KeBugCheck` at `0x140038d45`
- `ntoskrnl!ObfDereferenceObject` at `0x140038af7`
- `ntoskrnl!ObfDereferenceObject` at `0x140038af7`
- `FLTMGR!FltInitializePushLock` at `0x1400388cf`
- `FLTMGR!FltInitializePushLock` at `0x1400388f7`
- `FLTMGR!FltInitializePushLock` at `0x1400388cf`
- `FLTMGR!FltInitializePushLock` at `0x1400388f7`

## string_xrefs

- `0x140038de2`: `create`

## pseudocode

```c
__int64 __fastcall MpCreateProcessContext(__int64 ProcessId, __int64 a2, __int64 a3, _QWORD *a4)
{
  char *v8; // rbx
  char *v9; // rax
  int v10; // eax
  NTSTATUS ProcessNameByHandle; // edi
  PUNICODE_STRING *v12; // r14
  int v13; // eax
  const UNICODE_STRING *v14; // rcx
  int ProcessCommandLineByHandle; // eax
  int SessionIdFromProcess; // eax
  const UNICODE_STRING *v18; // rcx
  __int64 v19; // rdx
  _QWORD *v20; // rsi
  char *v21; // rdi
  unsigned __int64 v22; // rax
  __int64 v23; // rcx
  _DWORD *v24; // rax
  int v25; // edi
  int v26; // esi
  int v27; // edx
  int v28; // ecx
  int v29; // r8d
  HANDLE v30; // rdi
  __int64 v31; // rdi
  int v32; // eax
  __int64 v33; // rdx
  const wchar_t *v34; // rax
  __int64 v35; // [rsp+60h] [rbp-19h] BYREF
  __int64 v36; // [rsp+68h] [rbp-11h] BYREF
  _QWORD *v37; // [rsp+70h] [rbp-9h]
  PEPROCESS Process; // [rsp+78h] [rbp-1h] BYREF
  HANDLE ProcessHandle; // [rsp+80h] [rbp+7h] BYREF

  v37 = a4;
  v35 = 0;
  ProcessHandle = 0;
  Process = 0;
  v8 = 0;
  if ( !a2
    && (unsigned int)ProcessId > 0xA
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
  {
    _mm_lfence();
    WPP_SF_qD(
      WPP_GLOBAL_Control->AttachedDevice,
      20,
      WPP_9c9a40995a6d306ff00b675dc6e33d78_Traceguids,
      KeGetCurrentThread(),
      ProcessId);
  }
  *a4 = 0;
  if ( (int)MpGetProcessContextByIdAndCreationTime(ProcessId, a2, &v35) >= 0 && v35 )
  {
    *a4 = v35;
    ProcessNameByHandle = 0;
    goto LABEL_25;
  }
  v9 = (char *)ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)MpProcessTable + 1);
  v8 = v9;
  if ( !v9 )
  {
    ProcessNameByHandle = -1073741670;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_qqD(
        WPP_GLOBAL_Control->AttachedDevice,
        21,
        (unsigned int)WPP_9c9a40995a6d306ff00b675dc6e33d78_Traceguids,
        (unsigned int)KeGetCurrentThread(),
        ProcessId);
    goto LABEL_25;
  }
  memset(v9, 0, 0x130u);
  v10 = *((_DWORD *)v8 + 72);
  *(_DWORD *)v8 = 19978767;
  *((_QWORD *)v8 + 3) = ProcessId;
  *((_QWORD *)v8 + 4) = a2;
  *((_DWORD *)v8 + 72) = v10 & 0xFFFFFFC5 | 0x38;
  *((_DWORD *)v8 + 12) = 1;
  *((_QWORD *)v8 + 9) = -1;
  *((_DWORD *)v8 + 48) = 0;
  FltInitializePushLock((PULONG_PTR)v8 + 25);
  *((_QWORD *)v8 + 27) = v8 + 208;
  *((_QWORD *)v8 + 26) = v8 + 208;
  v8[232] = 0;
  FltInitializePushLock((PULONG_PTR)v8 + 34);
  ProcessNameByHandle = PsLookupProcessByProcessId((HANDLE)ProcessId, &Process);
  if ( ProcessNameByHandle < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      v19 = 22;
      goto LABEL_135;
    }
    goto LABEL_25;
  }
  _InterlockedIncrement64(&ObTotalReferences);
  ProcessNameByHandle = ObOpenObjectByPointer(
                          Process,
                          0x200u,
                          0,
                          0x1FFFFFu,
                          (POBJECT_TYPE)PsProcessType,
                          0,
                          &ProcessHandle);
  if ( ProcessNameByHandle < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      v19 = 23;
      goto LABEL_135;
    }
    goto LABEL_25;
  }
  if ( (int)MpIsAppContainerProcess(Process, v8 + 224) < 0
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
  {
    _mm_lfence();
    WPP_SF_qqD(
      WPP_GLOBAL_Control->AttachedDevice,
      24,
      (unsigned int)WPP_9c9a40995a6d306ff00b675dc6e33d78_Traceguids,
      (unsigned int)KeGetCurrentThread(),
      ProcessId);
  }
  if ( a3 && (v18 = *(const UNICODE_STRING **)a3) != 0 && v18->Length )
  {
    v12 = (PUNICODE_STRING *)(v8 + 128);
    ProcessNameByHandle = MpDuplicateString(v18);
    if ( ProcessNameByHandle < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      {
        v19 = 25;
LABEL_135:
        _mm_lfence();
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          v19,
          WPP_9c9a40995a6d306ff00b675dc6e33d78_Traceguids,
          (unsigned int)ProcessNameByHandle);
        goto LABEL_25;
      }
      goto LABEL_25;
    }
  }
  else
  {
    v12 = (PUNICODE_STRING *)(v8 + 128);
    ProcessNameByHandle = MpGetProcessNameByHandle(ProcessHandle);
    if ( ProcessNameByHandle < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      {
        v19 = 26;
        goto LABEL_135;
      }
      goto LABEL_25;
    }
  }
  if ( (int)MpGetKnownProcessType(*v12) < 0 )
    *((_DWORD *)v8 + 60) = 0;
  if ( *(_BYTE *)(MpData + 4049) )
    *((_DWORD *)v8 + 72) ^= ((unsigned __int8)*((_DWORD *)v8 + 72)
                           ^ (unsigned __int8)((unsigned __int8)MpIsDllHostProcess(*v12) << 6))
                          & 0x40;
  else
    *((_DWORD *)v8 + 72) &= ~0x40u;
  if ( *((_DWORD *)v8 + 60) == 20 && (int)MpDlpLoadProcessModuleNotifyRoutine(v8, *v12) < 0 )
    *((_DWORD *)v8 + 57) = 0;
  v13 = *((_DWORD *)v8 + 60);
  if ( (v13 == 17 || v13 == 18) && !MpMatchPerServiceSidByObj(Process, *(PSID *)(MpData + 2400)) )
    *((_DWORD *)v8 + 60) = 0;
  if ( !*((_DWORD *)v8 + 60) )
  {
    if ( a3 )
    {
      if ( *(_QWORD *)(a3 + 16) )
      {
        if ( MpMatchPerServiceSidByObj(Process, *(PSID *)(MpData + 2400)) )
        {
          v30 = *(HANDLE *)(a3 + 16);
          if ( v30 == PsGetCurrentProcessId() )
          {
            v36 = 0;
            if ( (int)MpGetProcessContextById(v30, &v36) >= 0 )
            {
              v31 = v36;
              v32 = *(_DWORD *)(v36 + 240);
              if ( (v32 == 17 || v32 == 18)
                && (!(unsigned int)MpFcKernelGetValue(285)
                 || (unsigned __int8)MpSuffixUnicodeString(&qword_140013218, *((_QWORD *)v8 + 16))
                 || (unsigned __int8)MpSuffixUnicodeString(L"&(", *((_QWORD *)v8 + 16))) )
              {
                *((_DWORD *)v8 + 60) = 18;
              }
              MpReleaseProcessContext(v31);
            }
          }
        }
      }
    }
    if ( !*((_DWORD *)v8 + 60)
      && (*(_DWORD *)(MpData + 864) & 0x4000) != 0
      && MpMatchPerServiceSidByObj(Process, *(PSID *)(MpData + 2400)) )
    {
      *((_DWORD *)v8 + 60) = 18;
    }
  }
  if ( a3 && (v14 = *(const UNICODE_STRING **)(a3 + 8)) != 0 && v14->Length )
  {
    ProcessCommandLineByHandle = MpDuplicateString(v14);
    if ( ProcessCommandLineByHandle >= 0
      || WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
    {
      goto LABEL_21;
    }
    v33 = 27;
  }
  else
  {
    ProcessCommandLineByHandle = MpGetProcessCommandLineByHandle(ProcessHandle);
    if ( ProcessCommandLineByHandle >= 0
      || WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
    {
      goto LABEL_21;
    }
    v33 = 28;
  }
  _mm_lfence();
  WPP_SF_d(
    WPP_GLOBAL_Control->AttachedDevice,
    v33,
    WPP_9c9a40995a6d306ff00b675dc6e33d78_Traceguids,
    (unsigned int)ProcessCommandLineByHandle);
LABEL_21:
  SessionIdFromProcess = MpQuerySessionIdFromProcess(Process, (void *)ProcessId, (_DWORD *)v8 + 64);
  if ( SessionIdFromProcess < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      _mm_lfence();
      WPP_SF_qD(
        WPP_GLOBAL_Control->AttachedDevice,
        29,
        WPP_9c9a40995a6d306ff00b675dc6e33d78_Traceguids,
        KeGetCurrentThread(),
        SessionIdFromProcess);
    }
    *((_DWORD *)v8 + 64) = -1;
  }
  if ( (*(_DWORD *)(MpData + 864) & 0x80u) == 0
    || (ProcessNameByHandle = ZwQueryInformationProcess(ProcessHandle, ProcessLdtSize|0x40, v8 + 120, 4u, 0),
        ProcessNameByHandle >= 0) )
  {
    ProcessNameByHandle = ZwQueryInformationProcess(
                            ProcessHandle,
                            ProcessAffinityUpdateMode|ProcessUserModeIOPL,
                            v8 + 184,
                            1u,
                            0);
    *((_DWORD *)v8 + 72) = *((_DWORD *)v8 + 72) & 0xFFFFFFFE | (ProcessNameByHandle >= 0);
    if ( ProcessNameByHandle < 0 )
    {
      if ( (*(_DWORD *)(MpData + 864) & 0x100) != 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        {
          v19 = 31;
          goto LABEL_135;
        }
        goto LABEL_25;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
      {
        _mm_lfence();
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          32,
          WPP_9c9a40995a6d306ff00b675dc6e33d78_Traceguids,
          (unsigned int)ProcessNameByHandle);
      }
    }
    if ( ProcessId == 4 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 33, WPP_9c9a40995a6d306ff00b675dc6e33d78_Traceguids);
      *((_DWORD *)v8 + 13) |= 0x4040u;
      *((_DWORD *)v8 + 60) = 30;
    }
    v20 = v8 + 8;
    *((_QWORD *)v8 + 2) = v8 + 8;
    *((_QWORD *)v8 + 1) = v8 + 8;
    ProcessNameByHandle = MpCreateCopyCache(v8);
    if ( ProcessNameByHandle < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      {
        v19 = 34;
        goto LABEL_135;
      }
    }
    else
    {
      _mm_lfence();
      if ( (unsigned __int8)MpIsCryptServiceProcess(v8, Process) )
        *((_DWORD *)v8 + 60) = 29;
      v21 = (char *)MpProcessTable;
      KeEnterCriticalRegion();
      ExAcquireResourceExclusiveLite((PERESOURCE)(v21 + 8), 1u);
      if ( (int)MpGetProcessContextByIdAndCreationTime(ProcessId, a2, &v35) >= 0 && v35 )
      {
        ProcessNameByHandle = 0;
        *v37 = v35;
        ExReleaseResourceLite((PERESOURCE)((char *)MpProcessTable + 8));
        KeLeaveCriticalRegion();
      }
      else
      {
        v22 = 16 * (((unsigned __int64)ProcessId >> 2) & 0x7F) + *((_QWORD *)MpProcessTable + 48);
        v23 = *(_QWORD *)v22;
        if ( *(_QWORD *)(*(_QWORD *)v22 + 8LL) != v22 )
          __fastfail(3u);
        _mm_lfence();
        *v20 = v23;
        *((_QWORD *)v8 + 2) = v22;
        *(_QWORD *)(v23 + 8) = v20;
        *(_QWORD *)v22 = v20;
        _InterlockedIncrement((volatile signed __int32 *)v8 + 12);
        v24 = MpProcessTable;
        if ( (*((_DWORD *)v8 + 13) & 0x40) != 0 )
          ++*((_DWORD *)MpProcessTable + 105);
        else
          ++*((_DWORD *)MpProcessTable + 106);
        v25 = v24[105];
        v26 = *((_DWORD *)MpProcessTable + 106);
        ExReleaseResourceLite((PERESOURCE)((char *)MpProcessTable + 8));
        KeLeaveCriticalRegion();
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
        {
          _mm_lfence();
          v34 = L"trusted";
          if ( (*((_DWORD *)v8 + 13) & 0x40) == 0 )
            v34 = L"untrusted";
          WPP_SF_ZdddiSdd(
            WPP_GLOBAL_Control->AttachedDevice,
            v27,
            v29,
            *((_QWORD *)v8 + 16),
            *((_DWORD *)v8 + 64),
            v8[224],
            ProcessId,
            a2,
            (__int64)v34,
            v25,
            v26);
        }
        if ( ((__int64)WPP_MAIN_CB.DeviceExtension & 8) != 0 )
          McTemplateK0qzqqqz_EtwWriteTransfer(
            v28,
            v27,
            v29,
            ProcessId,
            (__int64)L"create",
            (*((_DWORD *)v8 + 13) & 0x40) != 0,
            v25,
            v26,
            0);
        if ( ((__int64)WPP_MAIN_CB.DeviceExtension & 0x10) != 0 )
        {
          _mm_lfence();
          McTemplateK0qzqqzxx_EtwWriteTransfer(
            v28,
            v27,
            v29,
            ProcessId,
            (__int64)L"create",
            *((_DWORD *)v8 + 13),
            *((_DWORD *)v8 + 14),
            0,
            *((_QWORD *)v8 + 8),
            *((_QWORD *)v8 + 9));
        }
        *v37 = v8;
        v8 = 0;
        ProcessNameByHandle = 0;
      }
    }
    goto LABEL_25;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
  {
    v19 = 30;
    goto LABEL_135;
  }
LABEL_25:
  if ( ProcessHandle )
    ZwClose(ProcessHandle);
  if ( Process )
  {
    ObfDereferenceObject(Process);
    if ( _InterlockedDecrement64(&ObTotalReferences) < 0 && *(int *)(MpData + 868) < 0 )
    {
      if ( KdRefreshDebuggerNotPresent() )
        KeBugCheck(1u);
      __debugbreak();
    }
  }
  if ( v8 )
    MpFreeProcessContext(v8);
  return (unsigned int)ProcessNameByHandle;
}

```

## disassembly

```asm
0x1400387f0  push    rbp
0x1400387f2  push    rbx
0x1400387f3  push    rsi
0x1400387f4  push    rdi
0x1400387f5  push    r12
0x1400387f7  push    r13
0x1400387f9  push    r14
0x1400387fb  push    r15
0x1400387fd  lea     rbp, [rsp-1Fh]
0x140038802  sub     rsp, 98h
0x140038809  mov     rax, cs:__security_cookie
0x140038810  xor     rax, rsp
0x140038813  mov     [rbp+57h+var_48], rax
0x140038817  xor     r14d, r14d
0x14003881a  mov     [rbp+57h+var_60], r9
0x14003881e  mov     [rbp+57h+var_70], r14
0x140038822  mov     r15, rcx
0x140038825  mov     [rbp+57h+ProcessHandle], r14
0x140038829  mov     rdi, r9
0x14003882c  mov     [rbp+57h+Process], r14
0x140038830  mov     rsi, r8
0x140038833  lea     rcx, WPP_GLOBAL_Control
0x14003883a  mov     r12, rdx
0x14003883d  mov     ebx, r14d
0x140038840  test    rdx, rdx
0x140038843  jz      loc_140038E43
0x140038849  lea     r8, [rbp+57h+var_70]
0x14003884d  mov     [rdi], r14
0x140038850  mov     rdx, r12
0x140038853  mov     rcx, r15
0x140038856  call    MpGetProcessContextByIdAndCreationTime
0x14003885b  mov     r13, 0FFFFFFFFFFFFFFFFh
0x140038862  test    eax, eax
0x140038864  jns     loc_140038E9A
0x14003886a  mov     rcx, cs:MpProcessTable
0x140038871  sub     rcx, 0FFFFFFFFFFFFFF80h; Lookaside
0x140038875  call    ExAllocateFromPagedLookasideList
0x14003887a  mov     rbx, rax
0x14003887d  test    rax, rax
0x140038880  jz      loc_140038EB2
0x140038886  xor     edx, edx; Val
0x140038888  mov     r8d, 130h; Size
0x14003888e  mov     rcx, rax; void *
0x140038891  call    memset
0x140038896  mov     eax, [rbx+120h]
0x14003889c  lea     rcx, [rbx+0C8h]; PushLock
0x1400388a3  mov     dword ptr [rbx], 130DA0Fh
0x1400388a9  and     eax, 0FFFFFFFDh
0x1400388ac  mov     [rbx+18h], r15
0x1400388b0  or      eax, 38h
0x1400388b3  mov     [rbx+20h], r12
0x1400388b7  mov     [rbx+120h], eax
0x1400388bd  mov     dword ptr [rbx+30h], 1
0x1400388c4  mov     [rbx+48h], r13
0x1400388c8  mov     [rbx+0C0h], r14d
0x1400388cf  call    cs:__imp_FltInitializePushLock
0x1400388d6  nop     dword ptr [rax+rax+00h]
0x1400388db  lea     rax, [rbx+0D0h]
0x1400388e2  mov     [rax+8], rax
0x1400388e6  lea     rcx, [rbx+110h]; PushLock
0x1400388ed  mov     [rax], rax
0x1400388f0  mov     [rbx+0E8h], r14b
0x1400388f7  call    cs:__imp_FltInitializePushLock
0x1400388fe  nop     dword ptr [rax+rax+00h]
0x140038903  lea     rdx, [rbp+57h+Process]; Process
0x140038907  mov     rcx, r15; ProcessId
0x14003890a  call    cs:__imp_PsLookupProcessByProcessId
0x140038911  nop     dword ptr [rax+rax+00h]
0x140038916  mov     edi, eax
0x140038918  test    eax, eax
0x14003891a  js      loc_140039392
0x140038920  lock inc cs:ObTotalReferences
0x140038928  lea     rax, [rbp+57h+ProcessHandle]
0x14003892c  mov     r9d, 1FFFFFh; DesiredAccess
0x140038932  mov     [rsp+0D0h+Handle], rax; Handle
0x140038937  xor     r8d, r8d; PassedAccessState
0x14003893a  mov     rax, cs:__imp_PsProcessType
0x140038941  mov     edx, 200h; HandleAttributes
0x140038946  mov     [rsp+0D0h+AccessMode], r14b; AccessMode
0x14003894b  mov     rcx, [rax]
0x14003894e  mov     [rsp+0D0h+ObjectType], rcx; ObjectType
0x140038953  mov     rcx, [rbp+57h+Process]; Object
0x140038957  call    cs:__imp_ObOpenObjectByPointer
0x14003895e  nop     dword ptr [rax+rax+00h]
0x140038963  mov     edi, eax
0x140038965  test    eax, eax
0x140038967  js      loc_140038F10
0x14003896d  mov     rcx, [rbp+57h+Process]
0x140038971  lea     rdx, [rbx+0E0h]
0x140038978  call    MpIsAppContainerProcess
0x14003897d  test    eax, eax
0x14003897f  js      loc_140038F3D
0x140038985  test    rsi, rsi
0x140038988  jnz     loc_140038B42
0x14003898e  mov     rcx, [rbp+57h+ProcessHandle]; ProcessHandle
0x140038992  lea     r14, [rbx+80h]
0x140038999  mov     rdx, r14
0x14003899c  call    MpGetProcessNameByHandle
0x1400389a1  mov     edi, eax
0x1400389a3  test    eax, eax
0x1400389a5  js      loc_140038FBD
0x1400389ab  mov     rcx, [r14]; Name
0x1400389ae  lea     rdx, [rbx+0F0h]
0x1400389b5  call    MpGetKnownProcessType
0x1400389ba  test    eax, eax
0x1400389bc  jns     short loc_1400389C8
0x1400389be  mov     dword ptr [rbx+0F0h], 0
0x1400389c8  mov     rax, cs:MpData
0x1400389cf  cmp     byte ptr [rax+0FD1h], 0
0x1400389d6  jz      loc_140038D34
0x1400389dc  mov     rcx, [r14]
0x1400389df  call    MpIsDllHostProcess
0x1400389e4  movzx   ecx, al
0x1400389e7  mov     eax, [rbx+120h]
0x1400389ed  shl     ecx, 6
0x1400389f0  xor     ecx, eax
0x1400389f2  and     ecx, 40h
0x1400389f5  xor     ecx, eax
0x1400389f7  mov     [rbx+120h], ecx
0x1400389fd  cmp     dword ptr [rbx+0F0h], 14h
0x140038a04  jz      loc_140038FE1
0x140038a0a  mov     eax, [rbx+0F0h]
0x140038a10  cmp     eax, 11h
0x140038a13  jz      loc_140039003
0x140038a19  cmp     eax, 12h
0x140038a1c  jz      loc_140039003
0x140038a22  cmp     dword ptr [rbx+0F0h], 0
0x140038a29  jz      loc_140038B9D
0x140038a2f  test    rsi, rsi
0x140038a32  jz      loc_14003911E
0x140038a38  mov     rcx, [rsi+8]; SourceString
0x140038a3c  test    rcx, rcx
0x140038a3f  jz      loc_14003911E
0x140038a45  cmp     word ptr [rcx], 0
0x140038a49  jz      loc_14003911E
0x140038a4f  lea     rdx, [rbx+28h]
0x140038a53  call    MpDuplicateString
0x140038a58  test    eax, eax
0x140038a5a  js      loc_1400390CD
0x140038a60  lea     r14, WPP_GLOBAL_Control
0x140038a67  mov     rcx, [rbp+57h+Process]
0x140038a6b  lea     r8, [rbx+100h]
0x140038a72  mov     rdx, r15
0x140038a75  call    MpQuerySessionIdFromProcess
0x140038a7a  test    eax, eax
0x140038a7c  js      loc_140039158
0x140038a82  mov     rax, cs:MpData
0x140038a89  mov     ecx, [rax+360h]
0x140038a8f  test    cl, cl
0x140038a91  jns     loc_140038C13
0x140038a97  mov     rcx, [rbp+57h+ProcessHandle]; ProcessHandle
0x140038a9b  lea     r8, [rbx+78h]; ProcessInformation
0x140038a9f  mov     edx, 4Bh ; 'K'; ProcessInformationClass
0x140038aa4  mov     [rsp+0D0h+ObjectType], 0; ReturnLength
0x140038aad  mov     r9d, 4; ProcessInformationLength
0x140038ab3  call    cs:__imp_ZwQueryInformationProcess
0x140038aba  nop     dword ptr [rax+rax+00h]
0x140038abf  mov     edi, eax
0x140038ac1  test    eax, eax
0x140038ac3  jns     loc_140038C13
0x140038ac9  mov     rax, cs:WPP_GLOBAL_Control
0x140038ad0  cmp     rax, r14
0x140038ad3  jnz     loc_1400391A7
0x140038ad9  mov     rcx, [rbp+57h+ProcessHandle]; Handle
0x140038add  test    rcx, rcx
0x140038ae0  jz      short loc_140038AEE
0x140038ae2  call    cs:__imp_ZwClose
0x140038ae9  nop     dword ptr [rax+rax+00h]
0x140038aee  mov     rcx, [rbp+57h+Process]; Object
0x140038af2  test    rcx, rcx
0x140038af5  jz      short loc_140038B16
0x140038af7  call    cs:__imp_ObfDereferenceObject
0x140038afe  nop     dword ptr [rax+rax+00h]
0x140038b03  lock xadd cs:ObTotalReferences, r13
0x140038b0c  cmp     r13, 1
0x140038b10  js      loc_140038D09
0x140038b16  test    rbx, rbx
0x140038b19  jnz     loc_1400393DB
0x140038b1f  mov     eax, edi
0x140038b21  mov     rcx, [rbp+57h+var_48]
0x140038b25  xor     rcx, rsp; StackCookie
0x140038b28  call    __security_check_cookie
0x140038b2d  add     rsp, 98h
0x140038b34  pop     r15
0x140038b36  pop     r14
0x140038b38  pop     r13
0x140038b3a  pop     r12
0x140038b3c  pop     rdi
0x140038b3d  pop     rsi
0x140038b3e  pop     rbx
0x140038b3f  pop     rbp
0x140038b40  retn
0x140038b42  mov     rcx, [rsi]; SourceString
0x140038b45  test    rcx, rcx
0x140038b48  jz      loc_14003898E
0x140038b4e  cmp     [rcx], r14w
0x140038b52  jz      loc_14003898E
0x140038b58  lea     r14, [rbx+80h]
0x140038b5f  mov     rdx, r14
0x140038b62  call    MpDuplicateString
0x140038b67  mov     edi, eax
0x140038b69  test    eax, eax
0x140038b6b  jns     loc_1400389AB
0x140038b71  mov     rax, cs:WPP_GLOBAL_Control
0x140038b78  lea     rcx, WPP_GLOBAL_Control
0x140038b7f  cmp     rax, rcx
0x140038b82  jz      loc_140038AD9
0x140038b88  mov     eax, [rax+2Ch]
0x140038b8b  test    al, 1
0x140038b8d  jz      loc_140038AD9
0x140038b93  mov     edx, 19h
0x140038b98  jmp     loc_140038F9B
0x140038b9d  test    rsi, rsi
0x140038ba0  jz      short loc_140038BC8
0x140038ba2  cmp     qword ptr [rsi+10h], 0
0x140038ba7  jz      short loc_140038BC8
0x140038ba9  mov     rdx, cs:MpData
0x140038bb0  mov     rcx, [rbp+57h+Process]; Process
0x140038bb4  mov     rdx, [rdx+960h]; Sid
0x140038bbb  call    MpMatchPerServiceSidByObj
0x140038bc0  test    al, al
0x140038bc2  jnz     loc_140039031
0x140038bc8  cmp     dword ptr [rbx+0F0h], 0
0x140038bcf  jnz     loc_140038A2F
0x140038bd5  mov     rdx, cs:MpData
0x140038bdc  test    dword ptr [rdx+360h], 4000h
0x140038be6  jz      loc_140038A2F
0x140038bec  mov     rdx, [rdx+960h]; Sid
0x140038bf3  mov     rcx, [rbp+57h+Process]; Process
0x140038bf7  call    MpMatchPerServiceSidByObj
0x140038bfc  test    al, al
0x140038bfe  jz      loc_140038A2F
0x140038c04  mov     dword ptr [rbx+0F0h], 12h
0x140038c0e  jmp     loc_140038A2F
0x140038c13  mov     rcx, [rbp+57h+ProcessHandle]; ProcessHandle
0x140038c17  lea     r8, [rbx+0B8h]; ProcessInformation
0x140038c1e  mov     edx, 3Dh ; '='; ProcessInformationClass
0x140038c23  mov     [rsp+0D0h+ObjectType], 0; ReturnLength
0x140038c2c  mov     r9d, 1; ProcessInformationLength
0x140038c32  call    cs:__imp_ZwQueryInformationProcess
0x140038c39  nop     dword ptr [rax+rax+00h]
0x140038c3e  mov     ecx, eax
0x140038c40  mov     edi, eax
0x140038c42  mov     eax, [rbx+120h]
0x140038c48  not     ecx
0x140038c4a  shr     ecx, 1Fh
0x140038c4d  and     eax, 0FFFFFFFEh
0x140038c50  or      ecx, eax
0x140038c52  mov     [rbx+120h], ecx
0x140038c58  test    edi, edi
0x140038c5a  js      loc_1400391BC
0x140038c60  cmp     r15, 4
0x140038c64  jz      loc_140039236
0x140038c6a  lea     rsi, [rbx+8]
0x140038c6e  mov     rcx, rbx
0x140038c71  mov     [rsi+8], rsi
0x140038c75  mov     [rsi], rsi
0x140038c78  call    MpCreateCopyCache
0x140038c7d  mov     edi, eax
0x140038c7f  test    eax, eax
0x140038c81  js      loc_140039274
0x140038c87  lfence
0x140038c8a  mov     rdx, [rbp+57h+Process]
0x140038c8e  mov     rcx, rbx
0x140038c91  call    MpIsCryptServiceProcess
0x140038c96  test    al, al
0x140038c98  jnz     loc_140039299
0x140038c9e  mov     rdi, cs:MpProcessTable
0x140038ca5  call    cs:__imp_KeEnterCriticalRegion
0x140038cac  nop     dword ptr [rax+rax+00h]
0x140038cb1  mov     dl, 1; Wait
0x140038cb3  lea     rcx, [rdi+8]; Resource
0x140038cb7  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140038cbe  nop     dword ptr [rax+rax+00h]
0x140038cc3  lea     r8, [rbp+57h+var_70]
0x140038cc7  mov     rdx, r12
0x140038cca  mov     rcx, r15
0x140038ccd  call    MpGetProcessContextByIdAndCreationTime
0x140038cd2  test    eax, eax
0x140038cd4  jns     loc_1400392A8
0x140038cda  mov     rax, cs:MpProcessTable
0x140038ce1  mov     rdx, r15
0x140038ce4  shr     rdx, 2
0x140038ce8  and     edx, 7Fh
0x140038ceb  shl     rdx, 4
0x140038cef  mov     rax, [rax+180h]
0x140038cf6  add     rax, rdx
0x140038cf9  mov     rcx, [rax]
0x140038cfc  cmp     [rcx+8], rax
0x140038d00  jz      short loc_140038D52
0x140038d02  mov     ecx, 3
0x140038d07  int     29h; Win8: RtlFailFast(ecx)
0x140038d09  mov     rax, cs:MpData
0x140038d10  mov     ecx, [rax+364h]
0x140038d16  test    ecx, ecx
0x140038d18  jns     loc_140038B16
0x140038d1e  call    cs:__imp_KdRefreshDebuggerNotPresent
0x140038d25  nop     dword ptr [rax+rax+00h]
0x140038d2a  test    al, al
0x140038d2c  jnz     short loc_140038D40
  ... truncated ...
```
