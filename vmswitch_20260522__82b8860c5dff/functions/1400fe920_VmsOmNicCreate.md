# VmsOmNicCreate

- ea: `0x1400fe920`
- end: `0x1400ff216`
- name: `VmsOmNicCreate`
- size: `2294`
- prototype: `__int64 __usercall@<rax>(PCUNICODE_STRING SourceString@<rcx>, PCUNICODE_STRING@<rdx>, PCUNICODE_STRING@<r8>, __int64)`
- caller_count: `4`
- callee_count: `29`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x140058c50`
- `0x1400f54cc`
- `0x1400fc724`
- `0x140117f40`

## callees

- `0x140014988`
- `0x140027a64`
- `0x14002d318`
- `0x14002d86c`
- `0x14002e0f0`
- `0x14003a450`
- `0x14003c134`
- `0x140046e5c`
- `0x14004fce8`
- `0x14005deb8`
- `0x1400693fc`
- `0x14006a330`
- `0x14006a4ac`
- `0x14006f2b8`
- `0x14006f844`
- `0x14007233c`
- `0x14007556c`
- `0x1400764b4`
- `0x140077bd0`
- `0x14008497c`
- `0x14008d698`
- `0x14009128c`
- `0x1400fe920`
- `0x140100930`
- `0x140105138`
- `0x140105de8`
- `0x140108afc`
- `0x1401b0ffc`
- `0x1401bb6a4`

## import_xrefs

- `ntoskrnl!ExInitializeRundownProtection` at `0x1400fee2d`
- `ntoskrnl!ExInitializeRundownProtection` at `0x1400fee2d`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x1400fee3c`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x1400fee3c`
- `ntoskrnl!ExRundownCompleted` at `0x1400fee4b`
- `ntoskrnl!ExRundownCompleted` at `0x1400fee4b`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400feaf1`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400feaf1`
- `ntoskrnl!KeInitializeMutex` at `0x1400feea3`
- `ntoskrnl!KeInitializeMutex` at `0x1400feea3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ff0d0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ff0d0`
- `ntoskrnl!ExAllocatePool2` at `0x1400feb11`
- `ntoskrnl!ExAllocatePool2` at `0x1400feb11`
- `NDIS!NdisReleaseRWLock` at `0x1400feee8`
- `NDIS!NdisReleaseRWLock` at `0x1400fef6a`
- `NDIS!NdisReleaseRWLock` at `0x1400feee8`
- `NDIS!NdisReleaseRWLock` at `0x1400fef6a`

## string_xrefs

- `0x1400fea41`: `((ULONG_PTR)objNic & (VmsCacheLineSizeInBytes - 1)) == 0`
- `0x1400fea93`: `((ULONG_PTR)(&objNic->Stats) & (VmsCacheLineSizeInBytes - 1)) == 0`
- `0x1400ff125`: `objNic->LinkStateWorkItem == NULL`
- `0x1400ff1a9`: `objNic->VmqIovUpdateMacFiltersWorkItem == NULL`

## pseudocode

```c
__int64 __fastcall VmsOmNicCreate(
        PCUNICODE_STRING SourceString,
        PCUNICODE_STRING a2,
        PCUNICODE_STRING a3,
        char a4,
        __int64 *a5)
{
  __int64 v5; // rdi
  unsigned __int8 v6; // r13
  int v7; // r15d
  const UNICODE_STRING *v9; // rbx
  int v11; // edx
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // r8
  int v15; // ebx
  int v16; // eax
  int v17; // edx
  int WorkItem; // eax
  int v19; // edx
  int v20; // eax
  int v21; // edx
  int v22; // eax
  int v23; // edx
  int v24; // edx
  __int64 v25; // rcx
  int v26; // edx
  __int64 *v27; // rax
  __int64 *v28; // rax
  int v29; // r8d
  int v30; // r9d
  int v31; // r8d
  int v32; // r9d
  int v33; // edx
  void *v34; // rcx
  PCUNICODE_STRING SourceStringa; // [rsp+20h] [rbp-60h]
  int SourceStringb; // [rsp+20h] [rbp-60h]
  struct _LOCK_STATE_EX LockState; // [rsp+60h] [rbp-20h] BYREF
  int NicUnsafe; // [rsp+64h] [rbp-1Ch] BYREF
  PVOID P; // [rsp+68h] [rbp-18h]
  __int64 v41[2]; // [rsp+70h] [rbp-10h] BYREF
  PCUNICODE_STRING v42; // [rsp+C8h] [rbp+48h]
  unsigned __int8 v43; // [rsp+D8h] [rbp+58h]

  v42 = a2;
  NicUnsafe = 0;
  v5 = 0;
  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  v41[0] = 0;
  v6 = a4 & 1;
  P = 0;
  v7 = a4 & 2;
  v43 = a4 & 1;
  v9 = a2;
  if ( (a4 & 1) != 0 && (unsigned __int8)VmsOmIsObjectMarkedForDeletion(0, 0, SourceString) )
  {
    VmsOmDeleteObjectRegistryKey(0, 0, SourceString);
    NicUnsafe = -1073741738;
    LOBYTE(v11) = 2;
    WPP_RECORDER_SF_Z(
      VmsIfrLog,
      v11,
      20,
      13,
      (__int64)WPP_bda91bcb57e433144f485e69e8239e42_Traceguids,
      (__int64)SourceString);
    v15 = 5;
    goto LABEL_43;
  }
  LOBYTE(a2) = 1;
  v16 = VmsOmpObjectAllocate(
          640 * VmsMaximumProcCount + 9792,
          (int)a2,
          3,
          69,
          SourceString,
          v9,
          a3,
          (__int64)VmsOmpNicDeleted,
          (__int64)v41);
  v5 = v41[0];
  NicUnsafe = v16;
  if ( v16 >= 0 )
  {
    if ( ((VmsCacheLineSizeInBytes - 1) & v41[0]) != 0 )
    {
      WPP_RECORDER_SF_s(
        VmsIfrLog,
        v12,
        19,
        14,
        (__int64)WPP_bda91bcb57e433144f485e69e8239e42_Traceguids,
        (__int64)"((ULONG_PTR)objNic & (VmsCacheLineSizeInBytes - 1)) == 0");
      if ( ((VmsCacheLineSizeInBytes - 1) & (unsigned int)v5) != 0 )
        MicrosoftTelemetryAssertTriggeredNoArgsKM();
    }
    v15 = 15;
    if ( ((unsigned int)(VmsCacheLineSizeInBytes - 1) & (unsigned __int64)(v5 + 9792)) != 0 )
    {
      WPP_RECORDER_SF_s(
        VmsIfrLog,
        v12,
        19,
        15,
        (__int64)WPP_bda91bcb57e433144f485e69e8239e42_Traceguids,
        (__int64)"((ULONG_PTR)(&objNic->Stats) & (VmsCacheLineSizeInBytes - 1)) == 0");
      if ( ((VmsCacheLineSizeInBytes - 1) & ((_DWORD)v5 + 9792)) != 0 )
        MicrosoftTelemetryAssertTriggeredNoArgsKM();
    }
    NicUnsafe = VmsOmNicHeaderInitialize(v5 + 1232);
    if ( NicUnsafe >= 0 )
    {
      *(_QWORD *)(v5 + 1232) = v5;
      if ( a3 )
        RtlCopyUnicodeString((PUNICODE_STRING)(v5 + 1288), a3);
      P = (PVOID)ExAllocatePool2(64, 2224, 1649374038);
      if ( P )
      {
        NicUnsafe = VmsOmpRscStructsAllocateAndInit(v5 + 9376);
        if ( NicUnsafe >= 0 )
        {
          if ( v7 && (NicUnsafe = NvIoAllocateWorkerQueue(v13, v5 + 1992, v5 + 2096), NicUnsafe < 0) )
          {
            v15 = 30;
          }
          else
          {
            v6 = v43;
            *(_BYTE *)(v5 + 1876) = v43;
            *(_DWORD *)(v5 + 3360) = 13;
            *(_DWORD *)(v5 + 1880) = 2;
            *(_DWORD *)(v5 + 4032) = 2;
            *(_BYTE *)(v5 + 3956) = 1;
            *(_QWORD *)(v5 + 1912) = v5 + 1904;
            *(_QWORD *)(v5 + 1904) = v5 + 1904;
            *(_QWORD *)(v5 + 1944) = v5 + 1936;
            *(_QWORD *)(v5 + 1936) = v5 + 1936;
            *(_DWORD *)(v5 + 1968) = 1;
            *(_DWORD *)(v5 + 9468) = (signed int)(5000 * stru_140223F50.LowPart) / 1000;
            *(_DWORD *)(v5 + 9472) = 60000 * stru_140223F50.QuadPart / 1000;
            if ( v7 )
            {
              WorkItem = NvIoAllocateWorkItem(*(PNPAGED_LOOKASIDE_LIST *)(v5 + 2096), 33, v5 + 1976);
              NicUnsafe = WorkItem;
              if ( WorkItem < 0 )
              {
                v15 = 35;
                LOBYTE(v19) = 2;
                WPP_RECORDER_SF_d(
                  VmsIfrLog,
                  v19,
                  20,
                  17,
                  (__int64)WPP_bda91bcb57e433144f485e69e8239e42_Traceguids,
                  WorkItem);
                goto LABEL_40;
              }
              v20 = NvIoAllocateWorkItem(*(PNPAGED_LOOKASIDE_LIST *)(v5 + 2096), 34, v5 + 4840);
              NicUnsafe = v20;
              if ( v20 < 0 )
              {
                v15 = 40;
                LOBYTE(v21) = 2;
                WPP_RECORDER_SF_d(VmsIfrLog, v21, 20, 18, (__int64)WPP_bda91bcb57e433144f485e69e8239e42_Traceguids, v20);
                goto LABEL_40;
              }
              if ( g_NVBugFixes2509SriovMacSpoofingEnabled )
              {
                *(_DWORD *)(v5 + 9756) = 0;
                *(_BYTE *)(v5 + 9753) = 0;
                v22 = NvIoAllocateWorkItem(*(PNPAGED_LOOKASIDE_LIST *)(v5 + 2096), 41, v5 + 9760);
                NicUnsafe = v22;
                if ( v22 < 0 )
                {
                  v15 = 42;
                  LOBYTE(v23) = 2;
                  WPP_RECORDER_SF_d(
                    VmsIfrLog,
                    v23,
                    20,
                    19,
                    (__int64)WPP_bda91bcb57e433144f485e69e8239e42_Traceguids,
                    v22);
                  goto LABEL_40;
                }
              }
            }
            if ( !(unsigned __int8)VmsVrssInitializeRssConfig((void *)(v5 + 5496), (void *)(v5 + 4924)) )
            {
              NicUnsafe = -1073741670;
              LOBYTE(v24) = 2;
              WPP_RECORDER_SF_(VmsIfrLog, v24, 20, 20, (__int64)WPP_bda91bcb57e433144f485e69e8239e42_Traceguids);
              v15 = 45;
              goto LABEL_40;
            }
            *(_DWORD *)(v5 + 3356) = 1514;
            *(_DWORD *)(v5 + 4064) = 0;
            *(_BYTE *)(v5 + 4072) = 0;
            *(_DWORD *)(v5 + 4188) = 0;
            *(_OWORD *)(v5 + 4768) = 0;
            *(_OWORD *)(v5 + 4784) = 0;
            *(_OWORD *)(v5 + 4800) = 0;
            *(_QWORD *)(v5 + 4816) = 0;
            *(_QWORD *)(v5 + 4832) = v5 + 4824;
            *(_QWORD *)(v5 + 4824) = v5 + 4824;
            *(_DWORD *)(v5 + 4764) = 0;
            *(_BYTE *)(v5 + 4760) = 0;
            ExInitializeRundownProtection((PEX_RUNDOWN_REF)(v5 + 4872));
            ExWaitForRundownProtectionRelease((PEX_RUNDOWN_REF)(v5 + 4872));
            ExRundownCompleted((PEX_RUNDOWN_REF)(v5 + 4872));
            *(_OWORD *)(v5 + 2112) = 0;
            *(_QWORD *)(v5 + 2120) = v5 + 2128;
            *(_WORD *)(v5 + 2114) = 512;
            *(_OWORD *)(v5 + 2640) = 0;
            *(_WORD *)(v5 + 2642) = 512;
            *(_QWORD *)(v5 + 2648) = v5 + 2656;
            KeInitializeMutex((PRKMUTEX)(v5 + 1144), 0xFFFFu);
            *(_QWORD *)(v5 + 4040) = P;
            *(_BYTE *)(v5 + 1877) = 1;
            VmsUtilLockExclusive(v25, &LockState);
            NicUnsafe = VmsOmFindNicUnsafe(SourceString, v41);
            if ( !NicUnsafe )
            {
              NdisReleaseRWLock(VmsOmObjectListLock, &LockState);
              NicUnsafe = -1073741771;
              LOBYTE(v26) = 2;
              WPP_RECORDER_SF_Z(
                VmsIfrLog,
                v26,
                20,
                21,
                (__int64)WPP_bda91bcb57e433144f485e69e8239e42_Traceguids,
                (__int64)SourceString);
              v15 = 50;
              goto LABEL_40;
            }
            v27 = (__int64 *)qword_140224D08;
            if ( *(__int64 **)qword_140224D08 != &VmsOmNicList )
              __fastfail(3u);
            *(_QWORD *)(v5 + 8) = qword_140224D08;
            v15 = 0;
            *(_QWORD *)v5 = &VmsOmNicList;
            *v27 = v5;
            qword_140224D08 = v5;
            ++VmsOmNicCount;
            NdisReleaseRWLock(VmsOmObjectListLock, &LockState);
            if ( a5 )
            {
              LOBYTE(v12) = 7;
              VmsOmpObjectReference(v5, v12);
              *a5 = v5;
              VmsTrcActivityIdStart(v5);
            }
            NicUnsafe = 0;
          }
        }
        else
        {
          v15 = 25;
        }
      }
      else
      {
        NicUnsafe = -1073741670;
        LOBYTE(v17) = 2;
        WPP_RECORDER_SF_ld(VmsIfrLog, v17, 20, 16, (__int64)WPP_bda91bcb57e433144f485e69e8239e42_Traceguids, 176, 154);
        v15 = 20;
      }
    }
    v6 = v43;
    goto LABEL_40;
  }
  v15 = 10;
LABEL_40:
  if ( v5 && (Microsoft_Windows_Hyper_V_VmSwitchEnableBits & 2) != 0 )
    McTemplateK0zzqqqqq_EtwWriteTransfer(
      *(unsigned __int8 *)(v5 + 3954),
      v12,
      v14,
      *(_QWORD *)(v5 + 80),
      *(_QWORD *)(v5 + 624),
      0,
      0,
      *(_BYTE *)(v5 + 3954),
      *(_BYTE *)(v5 + 3955),
      3);
LABEL_43:
  v28 = (__int64 *)(v5 + 1816);
  if ( NicUnsafe )
  {
    LODWORD(SourceStringa) = v15;
    VmsEtwTraceNicOperationFailure(v13, v12, v14, &NicUnsafe);
    WPP_RECORDER_SF_ZZZlld(
      v6,
      v7 != 0,
      v31,
      v32,
      (__int64)SourceStringa,
      (__int64)SourceString,
      (__int64)v42,
      (__int64)a3,
      v6,
      v7 != 0,
      NicUnsafe);
    if ( P )
      ExFreePoolWithTag(P, 0);
    if ( v5 )
    {
      VmsVrssUninitializeRssConfig((void *)(v5 + 5496), (void *)(v5 + 4924));
      if ( v7 )
      {
        v34 = *(void **)(v5 + 2096);
        if ( v34 )
        {
          NvIoShutdownWorkerQueue(v34);
          *(_QWORD *)(v5 + 2096) = 0;
        }
      }
      if ( *(_QWORD *)(v5 + 1976) )
      {
        WPP_RECORDER_SF_s(
          VmsIfrLog,
          v33,
          19,
          24,
          (__int64)WPP_bda91bcb57e433144f485e69e8239e42_Traceguids,
          (__int64)"objNic->LinkStateWorkItem == NULL");
        if ( *(_QWORD *)(v5 + 1976) )
          MicrosoftTelemetryAssertTriggeredNoArgsKM();
      }
      if ( *(_QWORD *)(v5 + 4840) )
      {
        WPP_RECORDER_SF_s(
          VmsIfrLog,
          v33,
          19,
          25,
          (__int64)WPP_bda91bcb57e433144f485e69e8239e42_Traceguids,
          (__int64)"objNic->NicNDKInfo.SendPnPEventWorkItem == NULL");
        if ( *(_QWORD *)(v5 + 4840) )
          MicrosoftTelemetryAssertTriggeredNoArgsKM();
      }
      if ( g_NVBugFixes2509SriovMacSpoofingEnabled )
      {
        if ( *(_QWORD *)(v5 + 9760) )
        {
          WPP_RECORDER_SF_s(
            VmsIfrLog,
            v33,
            19,
            26,
            (__int64)WPP_bda91bcb57e433144f485e69e8239e42_Traceguids,
            (__int64)"objNic->VmqIovUpdateMacFiltersWorkItem == NULL");
          if ( *(_QWORD *)(v5 + 9760) )
            MicrosoftTelemetryAssertTriggeredNoArgsKM();
        }
      }
      VmsOmpRscStructsFree(v5 + 9376);
      VmsOmNicHeaderUninitialize(v5 + 1232);
      VmsOmpObjectCleanup(v5);
    }
  }
  else
  {
    if ( !v5 )
      v28 = &VmsPolicyNullGuid;
    VmsEtwTraceNicOperationSuccess(v13, v12, v14, 7, (__int64)SourceString, (__int64)a3, (__int64)v28);
    WPP_RECORDER_SF_ZZZllqd(
      v6,
      v7 != 0,
      v29,
      v30,
      SourceStringb,
      (__int64)SourceString,
      (__int64)v42,
      (__int64)a3,
      v6,
      v7 != 0,
      v5,
      NicUnsafe);
  }
  return (unsigned int)NicUnsafe;
}

```

## disassembly

```asm
0x1400fe920  mov     [rsp-38h+arg_0], rbx
0x1400fe925  mov     [rsp-38h+arg_8], rdx
0x1400fe92a  push    rbp
0x1400fe92b  push    rsi
0x1400fe92c  push    rdi
0x1400fe92d  push    r12
0x1400fe92f  push    r13
0x1400fe931  push    r14
0x1400fe933  push    r15
0x1400fe935  mov     rbp, rsp
0x1400fe938  sub     rsp, 80h
0x1400fe93f  xor     eax, eax
0x1400fe941  mov     [rbp+var_1C], 0
0x1400fe948  xor     edi, edi
0x1400fe94a  mov     word ptr [rbp+LockState.OldIrql], ax
0x1400fe94e  mov     r15d, r9d
0x1400fe951  mov     [rbp+LockState.Flags], al
0x1400fe954  mov     r13b, r9b
0x1400fe957  mov     [rbp+var_10], rdi
0x1400fe95b  and     r13b, 1
0x1400fe95f  mov     [rbp+P], rax
0x1400fe963  and     r15d, 2
0x1400fe967  mov     [rbp+arg_18], r13b
0x1400fe96b  mov     r12, r8
0x1400fe96e  mov     rbx, rdx
0x1400fe971  mov     r14, rcx
0x1400fe974  test    r13b, r13b
0x1400fe977  jz      short loc_1400FE9CB
0x1400fe979  mov     r8, rcx
0x1400fe97c  xor     edx, edx
0x1400fe97e  xor     ecx, ecx
0x1400fe980  call    VmsOmIsObjectMarkedForDeletion
0x1400fe985  test    al, al
0x1400fe987  jz      short loc_1400FE9CB
0x1400fe989  mov     r8, r14
0x1400fe98c  xor     edx, edx
0x1400fe98e  xor     ecx, ecx
0x1400fe990  call    VmsOmDeleteObjectRegistryKey
0x1400fe995  mov     [rbp+var_1C], 0C0000056h
0x1400fe99c  mov     rcx, cs:VmsIfrLog
0x1400fe9a3  lea     rsi, WPP_bda91bcb57e433144f485e69e8239e42_Traceguids
0x1400fe9aa  lea     r9d, [rdi+0Dh]
0x1400fe9ae  mov     [rsp+80h+var_58], r14
0x1400fe9b3  lea     r8d, [rdi+14h]
0x1400fe9b7  mov     [rsp+80h+SourceString], rsi
0x1400fe9bc  mov     dl, 2
0x1400fe9be  call    WPP_RECORDER_SF_Z
0x1400fe9c3  lea     ebx, [rdi+5]
0x1400fe9c6  jmp     loc_1400FEFED
0x1400fe9cb  mov     eax, cs:VmsMaximumProcCount
0x1400fe9d1  mov     r9b, 45h ; 'E'; int
0x1400fe9d4  mov     r8d, 3; int
0x1400fe9da  mov     dl, 1; int
0x1400fe9dc  lea     ecx, [rax+rax*4]
0x1400fe9df  lea     rax, [rbp+var_10]
0x1400fe9e3  shl     ecx, 7
0x1400fe9e6  mov     [rsp+80h+var_40], rax; __int64
0x1400fe9eb  add     ecx, 2640h; int
0x1400fe9f1  lea     rax, VmsOmpNicDeleted
0x1400fe9f8  mov     [rsp+80h+var_48], rax; __int64
0x1400fe9fd  mov     [rsp+80h+var_50], r12; PCUNICODE_STRING
0x1400fea02  mov     [rsp+80h+var_58], rbx; PCUNICODE_STRING
0x1400fea07  mov     [rsp+80h+SourceString], r14; SourceString
0x1400fea0c  call    VmsOmpObjectAllocate
0x1400fea11  mov     rdi, [rbp+var_10]
0x1400fea15  lea     rsi, WPP_bda91bcb57e433144f485e69e8239e42_Traceguids
0x1400fea1c  mov     [rbp+var_1C], eax
0x1400fea1f  test    eax, eax
0x1400fea21  jns     short loc_1400FEA2D
0x1400fea23  mov     ebx, 0Ah
0x1400fea28  jmp     loc_1400FEF9C
0x1400fea2d  mov     ecx, cs:VmsCacheLineSizeInBytes
0x1400fea33  dec     ecx
0x1400fea35  test    rdi, rcx
0x1400fea38  jz      short loc_1400FEA73
0x1400fea3a  mov     rcx, cs:VmsIfrLog
0x1400fea41  lea     rax, aUlongPtrObjnic; "((ULONG_PTR)objNic & (VmsCacheLineSizeI"...
0x1400fea48  mov     r9d, 0Eh
0x1400fea4e  mov     [rsp+80h+var_58], rax
0x1400fea53  mov     [rsp+80h+SourceString], rsi
0x1400fea58  lea     r8d, [r9+5]
0x1400fea5c  call    WPP_RECORDER_SF_s
0x1400fea61  mov     ecx, cs:VmsCacheLineSizeInBytes
0x1400fea67  dec     ecx
0x1400fea69  test    rdi, rcx
0x1400fea6c  jz      short loc_1400FEA73
0x1400fea6e  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "((ULONG_PTR)objNic & (VmsCacheLineSizeInBytes - 1)) == 0")
0x1400fea73  mov     ecx, cs:VmsCacheLineSizeInBytes
0x1400fea79  lea     r13, [rdi+2640h]
0x1400fea80  dec     ecx
0x1400fea82  mov     ebx, 0Fh
0x1400fea87  test    r13, rcx
0x1400fea8a  jz      short loc_1400FEAC2
0x1400fea8c  mov     rcx, cs:VmsIfrLog
0x1400fea93  lea     rax, aUlongPtrObjnic_0; "((ULONG_PTR)(&objNic->Stats) & (VmsCach"...
0x1400fea9a  mov     [rsp+80h+var_58], rax
0x1400fea9f  lea     r8d, [rbx+4]
0x1400feaa3  mov     r9d, ebx
0x1400feaa6  mov     [rsp+80h+SourceString], rsi
0x1400feaab  call    WPP_RECORDER_SF_s
0x1400feab0  mov     ecx, cs:VmsCacheLineSizeInBytes
0x1400feab6  dec     ecx
0x1400feab8  test    r13, rcx
0x1400feabb  jz      short loc_1400FEAC2
0x1400feabd  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "((ULONG_PTR)(&objNic->Stats) & (VmsCacheLineSizeInBytes - 1)) == 0")
0x1400feac2  lea     r13, [rdi+4D0h]
0x1400feac9  mov     rcx, r13
0x1400feacc  call    VmsOmNicHeaderInitialize
0x1400fead1  mov     [rbp+var_1C], eax
0x1400fead4  test    eax, eax
0x1400fead6  js      loc_1400FEF98
0x1400feadc  xor     ebx, ebx
0x1400feade  mov     [r13+0], rdi
0x1400feae2  test    r12, r12
0x1400feae5  jz      short loc_1400FEAFD
0x1400feae7  lea     rcx, [rdi+508h]; DestinationString
0x1400feaee  mov     rdx, r12; SourceString
0x1400feaf1  call    cs:__imp_RtlCopyUnicodeString
0x1400feaf8  nop     dword ptr [rax+rax+00h]
0x1400feafd  mov     r13d, 8B0h
0x1400feb03  mov     r8d, 624F7356h
0x1400feb09  mov     edx, r13d
0x1400feb0c  mov     ecx, 40h ; '@'
0x1400feb11  call    cs:__imp_ExAllocatePool2
0x1400feb18  nop     dword ptr [rax+rax+00h]
0x1400feb1d  mov     [rbp+P], rax
0x1400feb21  test    rax, rax
0x1400feb24  jnz     short loc_1400FEB5F
0x1400feb26  mov     [rbp+var_1C], 0C000009Ah
0x1400feb2d  mov     rcx, cs:VmsIfrLog
0x1400feb34  lea     r9d, [rax+10h]
0x1400feb38  mov     dword ptr [rsp+80h+var_50], 0C000009Ah
0x1400feb40  lea     r8d, [rax+14h]
0x1400feb44  mov     dword ptr [rsp+80h+var_58], r13d
0x1400feb49  mov     dl, 2
0x1400feb4b  mov     [rsp+80h+SourceString], rsi
0x1400feb50  call    WPP_RECORDER_SF_ld
0x1400feb55  mov     ebx, 14h
0x1400feb5a  jmp     loc_1400FEF98
0x1400feb5f  lea     rcx, [rdi+24A0h]
0x1400feb66  call    VmsOmpRscStructsAllocateAndInit
0x1400feb6b  mov     [rbp+var_1C], eax
0x1400feb6e  test    eax, eax
0x1400feb70  jns     short loc_1400FEB7C
0x1400feb72  mov     ebx, 19h
0x1400feb77  jmp     loc_1400FEF98
0x1400feb7c  test    r15d, r15d
0x1400feb7f  jz      short loc_1400FEBA5
0x1400feb81  lea     r8, [rdi+830h]
0x1400feb88  lea     rdx, [rdi+7C8h]
0x1400feb8f  call    NvIoAllocateWorkerQueue
0x1400feb94  mov     [rbp+var_1C], eax
0x1400feb97  test    eax, eax
0x1400feb99  jns     short loc_1400FEBA5
0x1400feb9b  mov     ebx, 1Eh
0x1400feba0  jmp     loc_1400FEF98
0x1400feba5  mov     r13b, [rbp+arg_18]
0x1400feba9  mov     eax, 2
0x1400febae  mov     [rdi+754h], r13b
0x1400febb5  mov     r8, 20C49BA5E353F7CFh
0x1400febbf  mov     dword ptr [rdi+0D20h], 0Dh
0x1400febc9  mov     [rdi+758h], eax
0x1400febcf  mov     [rdi+0FC0h], eax
0x1400febd5  lea     r10d, [rax-1]
0x1400febd9  mov     [rdi+0F74h], r10b
0x1400febe0  lea     rax, [rdi+770h]
0x1400febe7  mov     [rax+8], rax
0x1400febeb  mov     [rax], rax
0x1400febee  lea     rax, [rdi+790h]
0x1400febf5  mov     [rax+8], rax
0x1400febf9  mov     [rax], rax
0x1400febfc  mov     rax, r8
0x1400febff  mov     [rdi+7B0h], r10d
0x1400fec06  imul    rcx, qword ptr cs:stru_140223F50, 1388h
0x1400fec11  imul    rcx
0x1400fec14  mov     rax, r8
0x1400fec17  sar     rdx, 7
0x1400fec1b  mov     rcx, rdx
0x1400fec1e  shr     rcx, 3Fh
0x1400fec22  add     rdx, rcx
0x1400fec25  mov     [rdi+24FCh], edx
0x1400fec2b  imul    rcx, qword ptr cs:stru_140223F50, 0EA60h
0x1400fec36  imul    rcx
0x1400fec39  sar     rdx, 7
0x1400fec3d  mov     rax, rdx
0x1400fec40  shr     rax, 3Fh
0x1400fec44  add     rdx, rax
0x1400fec47  mov     [rdi+2500h], edx
0x1400fec4d  test    r15d, r15d
0x1400fec50  jz      loc_1400FED88
0x1400fec56  mov     rcx, [rdi+830h]; Lookaside
0x1400fec5d  lea     rax, [rdi+7B8h]
0x1400fec64  mov     [rsp+80h+var_58], rax; __int64
0x1400fec69  lea     r8, VmsOmNicPvtCompleteLinkChangeIrp
0x1400fec70  mov     r9, rdi
0x1400fec73  mov     [rsp+80h+SourceString], 21h ; '!'; __int64
0x1400fec7c  mov     edx, r10d
0x1400fec7f  call    NvIoAllocateWorkItem
0x1400fec84  mov     [rbp+var_1C], eax
0x1400fec87  test    eax, eax
0x1400fec89  jns     short loc_1400FECB4
0x1400fec8b  mov     ebx, 23h ; '#'
0x1400fec90  mov     rcx, cs:VmsIfrLog
0x1400fec97  lea     r9d, [rbx-12h]
0x1400fec9b  mov     dword ptr [rsp+80h+var_58], eax
0x1400fec9f  lea     r8d, [rbx-0Fh]
0x1400feca3  mov     dl, 2
0x1400feca5  mov     [rsp+80h+SourceString], rsi
0x1400fecaa  call    WPP_RECORDER_SF_d
0x1400fecaf  jmp     loc_1400FEF9C
0x1400fecb4  mov     rcx, [rdi+830h]; Lookaside
0x1400fecbb  lea     rax, [rdi+12E8h]
0x1400fecc2  mov     [rsp+80h+var_58], rax; __int64
0x1400fecc7  lea     r8, VmsNdkSendPnPEventWorkerRoutine
0x1400fecce  mov     r9, rdi
0x1400fecd1  mov     [rsp+80h+SourceString], 22h ; '"'; __int64
0x1400fecda  mov     edx, 1
0x1400fecdf  call    NvIoAllocateWorkItem
0x1400fece4  mov     [rbp+var_1C], eax
0x1400fece7  test    eax, eax
0x1400fece9  jns     short loc_1400FED14
0x1400feceb  mov     ebx, 28h ; '('
0x1400fecf0  mov     rcx, cs:VmsIfrLog
0x1400fecf7  lea     r9d, [rbx-16h]
0x1400fecfb  mov     dword ptr [rsp+80h+var_58], eax
0x1400fecff  lea     r8d, [rbx-14h]
0x1400fed03  mov     dl, 2
0x1400fed05  mov     [rsp+80h+SourceString], rsi
0x1400fed0a  call    WPP_RECORDER_SF_d
0x1400fed0f  jmp     loc_1400FEF9C
0x1400fed14  cmp     cs:g_NVBugFixes2509SriovMacSpoofingEnabled, ebx
0x1400fed1a  jz      short loc_1400FED88
0x1400fed1c  mov     [rdi+261Ch], ebx
0x1400fed22  lea     rax, [rdi+2620h]
0x1400fed29  mov     [rdi+2619h], bl
0x1400fed2f  lea     r8, VmsVmVmqIovUpdateMacFiltersWorkItem
0x1400fed36  mov     rcx, [rdi+830h]; Lookaside
0x1400fed3d  mov     r9, rdi
0x1400fed40  mov     [rsp+80h+var_58], rax; __int64
0x1400fed45  mov     edx, 1
0x1400fed4a  mov     [rsp+80h+SourceString], 29h ; ')'; __int64
0x1400fed53  call    NvIoAllocateWorkItem
0x1400fed58  mov     [rbp+var_1C], eax
0x1400fed5b  test    eax, eax
0x1400fed5d  jns     short loc_1400FED88
0x1400fed5f  mov     ebx, 2Ah ; '*'
0x1400fed64  mov     rcx, cs:VmsIfrLog
0x1400fed6b  lea     r9d, [rbx-17h]
0x1400fed6f  mov     dword ptr [rsp+80h+var_58], eax
0x1400fed73  lea     r8d, [rbx-16h]
0x1400fed77  mov     dl, 2
0x1400fed79  mov     [rsp+80h+SourceString], rsi
0x1400fed7e  call    WPP_RECORDER_SF_d
0x1400fed83  jmp     loc_1400FEF9C
0x1400fed88  lea     rdx, [rdi+133Ch]; void *
0x1400fed8f  lea     rcx, [rdi+1578h]; void *
0x1400fed96  call    VmsVrssInitializeRssConfig
0x1400fed9b  test    al, al
0x1400fed9d  jnz     short loc_1400FEDCC
0x1400fed9f  mov     [rbp+var_1C], 0C000009Ah
0x1400feda6  mov     rcx, cs:VmsIfrLog
0x1400fedad  mov     r9d, 14h
0x1400fedb3  mov     r8d, r9d
0x1400fedb6  mov     [rsp+80h+SourceString], rsi
0x1400fedbb  mov     dl, 2
0x1400fedbd  call    WPP_RECORDER_SF_
0x1400fedc2  mov     ebx, 2Dh ; '-'
0x1400fedc7  jmp     loc_1400FEF9C
0x1400fedcc  mov     dword ptr [rdi+0D1Ch], 5EAh
0x1400fedd6  xorps   xmm0, xmm0
0x1400fedd9  mov     [rdi+0FE0h], ebx
0x1400feddf  xor     eax, eax
0x1400fede1  mov     [rdi+0FE8h], bl
0x1400fede7  mov     [rdi+105Ch], ebx
0x1400feded  movups  xmmword ptr [rdi+12A0h], xmm0
0x1400fedf4  movups  xmmword ptr [rdi+12B0h], xmm0
0x1400fedfb  movups  xmmword ptr [rdi+12C0h], xmm0
0x1400fee02  mov     [rdi+12D0h], rax
0x1400fee09  lea     rax, [rdi+12D8h]
0x1400fee10  mov     [rax+8], rax
0x1400fee14  mov     [rax], rax
0x1400fee17  mov     [rdi+129Ch], ebx
0x1400fee1d  mov     [rdi+1298h], bl
0x1400fee23  lea     rbx, [rdi+1308h]
0x1400fee2a  mov     rcx, rbx; RunRef
0x1400fee2d  call    cs:__imp_ExInitializeRundownProtection
0x1400fee34  nop     dword ptr [rax+rax+00h]
0x1400fee39  mov     rcx, rbx; RunRef
0x1400fee3c  call    cs:__imp_ExWaitForRundownProtectionRelease
0x1400fee43  nop     dword ptr [rax+rax+00h]
0x1400fee48  mov     rcx, rbx; RunRef
0x1400fee4b  call    cs:__imp_ExRundownCompleted
0x1400fee52  nop     dword ptr [rax+rax+00h]
0x1400fee57  xorps   xmm0, xmm0
0x1400fee5a  lea     rax, [rdi+850h]
0x1400fee61  movups  xmmword ptr [rdi+840h], xmm0
0x1400fee68  mov     [rdi+848h], rax
0x1400fee6f  mov     ecx, 200h
0x1400fee74  mov     [rdi+842h], cx
0x1400fee7b  lea     rax, [rdi+0A60h]
  ... truncated ...
```
