# VmsOmNicCreate

- ea: `0x1400fe990`
- end: `0x1400ff286`
- name: `VmsOmNicCreate`
- size: `2294`
- prototype: `__int64 __usercall@<rax>(PCUNICODE_STRING SourceString@<rcx>, PCUNICODE_STRING@<rdx>, PCUNICODE_STRING@<r8>, __int64)`
- caller_count: `4`
- callee_count: `29`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x140058c50`
- `0x1400f553c`
- `0x1400fc794`
- `0x140117fb0`

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
- `0x1400fe990`
- `0x1401009a0`
- `0x1401051a8`
- `0x140105e58`
- `0x140108b6c`
- `0x1401b106c`
- `0x1401bb714`

## import_xrefs

- `ntoskrnl!ExInitializeRundownProtection` at `0x1400fee9d`
- `ntoskrnl!ExInitializeRundownProtection` at `0x1400fee9d`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x1400feeac`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x1400feeac`
- `ntoskrnl!ExRundownCompleted` at `0x1400feebb`
- `ntoskrnl!ExRundownCompleted` at `0x1400feebb`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400feb61`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400feb61`
- `ntoskrnl!KeInitializeMutex` at `0x1400fef13`
- `ntoskrnl!KeInitializeMutex` at `0x1400fef13`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ff140`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ff140`
- `ntoskrnl!ExAllocatePool2` at `0x1400feb81`
- `ntoskrnl!ExAllocatePool2` at `0x1400feb81`
- `NDIS!NdisReleaseRWLock` at `0x1400fef58`
- `NDIS!NdisReleaseRWLock` at `0x1400fefda`
- `NDIS!NdisReleaseRWLock` at `0x1400fef58`
- `NDIS!NdisReleaseRWLock` at `0x1400fefda`

## string_xrefs

- `0x1400feab1`: `((ULONG_PTR)objNic & (VmsCacheLineSizeInBytes - 1)) == 0`
- `0x1400feb03`: `((ULONG_PTR)(&objNic->Stats) & (VmsCacheLineSizeInBytes - 1)) == 0`
- `0x1400ff195`: `objNic->LinkStateWorkItem == NULL`
- `0x1400ff219`: `objNic->VmqIovUpdateMacFiltersWorkItem == NULL`

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
0x1400fe990  mov     [rsp-38h+arg_0], rbx
0x1400fe995  mov     [rsp-38h+arg_8], rdx
0x1400fe99a  push    rbp
0x1400fe99b  push    rsi
0x1400fe99c  push    rdi
0x1400fe99d  push    r12
0x1400fe99f  push    r13
0x1400fe9a1  push    r14
0x1400fe9a3  push    r15
0x1400fe9a5  mov     rbp, rsp
0x1400fe9a8  sub     rsp, 80h
0x1400fe9af  xor     eax, eax
0x1400fe9b1  mov     [rbp+var_1C], 0
0x1400fe9b8  xor     edi, edi
0x1400fe9ba  mov     word ptr [rbp+LockState.OldIrql], ax
0x1400fe9be  mov     r15d, r9d
0x1400fe9c1  mov     [rbp+LockState.Flags], al
0x1400fe9c4  mov     r13b, r9b
0x1400fe9c7  mov     [rbp+var_10], rdi
0x1400fe9cb  and     r13b, 1
0x1400fe9cf  mov     [rbp+P], rax
0x1400fe9d3  and     r15d, 2
0x1400fe9d7  mov     [rbp+arg_18], r13b
0x1400fe9db  mov     r12, r8
0x1400fe9de  mov     rbx, rdx
0x1400fe9e1  mov     r14, rcx
0x1400fe9e4  test    r13b, r13b
0x1400fe9e7  jz      short loc_1400FEA3B
0x1400fe9e9  mov     r8, rcx
0x1400fe9ec  xor     edx, edx
0x1400fe9ee  xor     ecx, ecx
0x1400fe9f0  call    VmsOmIsObjectMarkedForDeletion
0x1400fe9f5  test    al, al
0x1400fe9f7  jz      short loc_1400FEA3B
0x1400fe9f9  mov     r8, r14
0x1400fe9fc  xor     edx, edx
0x1400fe9fe  xor     ecx, ecx
0x1400fea00  call    VmsOmDeleteObjectRegistryKey
0x1400fea05  mov     [rbp+var_1C], 0C0000056h
0x1400fea0c  mov     rcx, cs:VmsIfrLog
0x1400fea13  lea     rsi, WPP_bda91bcb57e433144f485e69e8239e42_Traceguids
0x1400fea1a  lea     r9d, [rdi+0Dh]
0x1400fea1e  mov     [rsp+80h+var_58], r14
0x1400fea23  lea     r8d, [rdi+14h]
0x1400fea27  mov     [rsp+80h+SourceString], rsi
0x1400fea2c  mov     dl, 2
0x1400fea2e  call    WPP_RECORDER_SF_Z
0x1400fea33  lea     ebx, [rdi+5]
0x1400fea36  jmp     loc_1400FF05D
0x1400fea3b  mov     eax, cs:VmsMaximumProcCount
0x1400fea41  mov     r9b, 45h ; 'E'; int
0x1400fea44  mov     r8d, 3; int
0x1400fea4a  mov     dl, 1; int
0x1400fea4c  lea     ecx, [rax+rax*4]
0x1400fea4f  lea     rax, [rbp+var_10]
0x1400fea53  shl     ecx, 7
0x1400fea56  mov     [rsp+80h+var_40], rax; __int64
0x1400fea5b  add     ecx, 2640h; int
0x1400fea61  lea     rax, VmsOmpNicDeleted
0x1400fea68  mov     [rsp+80h+var_48], rax; __int64
0x1400fea6d  mov     [rsp+80h+var_50], r12; PCUNICODE_STRING
0x1400fea72  mov     [rsp+80h+var_58], rbx; PCUNICODE_STRING
0x1400fea77  mov     [rsp+80h+SourceString], r14; SourceString
0x1400fea7c  call    VmsOmpObjectAllocate
0x1400fea81  mov     rdi, [rbp+var_10]
0x1400fea85  lea     rsi, WPP_bda91bcb57e433144f485e69e8239e42_Traceguids
0x1400fea8c  mov     [rbp+var_1C], eax
0x1400fea8f  test    eax, eax
0x1400fea91  jns     short loc_1400FEA9D
0x1400fea93  mov     ebx, 0Ah
0x1400fea98  jmp     loc_1400FF00C
0x1400fea9d  mov     ecx, cs:VmsCacheLineSizeInBytes
0x1400feaa3  dec     ecx
0x1400feaa5  test    rdi, rcx
0x1400feaa8  jz      short loc_1400FEAE3
0x1400feaaa  mov     rcx, cs:VmsIfrLog
0x1400feab1  lea     rax, aUlongPtrObjnic; "((ULONG_PTR)objNic & (VmsCacheLineSizeI"...
0x1400feab8  mov     r9d, 0Eh
0x1400feabe  mov     [rsp+80h+var_58], rax
0x1400feac3  mov     [rsp+80h+SourceString], rsi
0x1400feac8  lea     r8d, [r9+5]
0x1400feacc  call    WPP_RECORDER_SF_s
0x1400fead1  mov     ecx, cs:VmsCacheLineSizeInBytes
0x1400fead7  dec     ecx
0x1400fead9  test    rdi, rcx
0x1400feadc  jz      short loc_1400FEAE3
0x1400feade  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "((ULONG_PTR)objNic & (VmsCacheLineSizeInBytes - 1)) == 0")
0x1400feae3  mov     ecx, cs:VmsCacheLineSizeInBytes
0x1400feae9  lea     r13, [rdi+2640h]
0x1400feaf0  dec     ecx
0x1400feaf2  mov     ebx, 0Fh
0x1400feaf7  test    r13, rcx
0x1400feafa  jz      short loc_1400FEB32
0x1400feafc  mov     rcx, cs:VmsIfrLog
0x1400feb03  lea     rax, aUlongPtrObjnic_0; "((ULONG_PTR)(&objNic->Stats) & (VmsCach"...
0x1400feb0a  mov     [rsp+80h+var_58], rax
0x1400feb0f  lea     r8d, [rbx+4]
0x1400feb13  mov     r9d, ebx
0x1400feb16  mov     [rsp+80h+SourceString], rsi
0x1400feb1b  call    WPP_RECORDER_SF_s
0x1400feb20  mov     ecx, cs:VmsCacheLineSizeInBytes
0x1400feb26  dec     ecx
0x1400feb28  test    r13, rcx
0x1400feb2b  jz      short loc_1400FEB32
0x1400feb2d  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "((ULONG_PTR)(&objNic->Stats) & (VmsCacheLineSizeInBytes - 1)) == 0")
0x1400feb32  lea     r13, [rdi+4D0h]
0x1400feb39  mov     rcx, r13
0x1400feb3c  call    VmsOmNicHeaderInitialize
0x1400feb41  mov     [rbp+var_1C], eax
0x1400feb44  test    eax, eax
0x1400feb46  js      loc_1400FF008
0x1400feb4c  xor     ebx, ebx
0x1400feb4e  mov     [r13+0], rdi
0x1400feb52  test    r12, r12
0x1400feb55  jz      short loc_1400FEB6D
0x1400feb57  lea     rcx, [rdi+508h]; DestinationString
0x1400feb5e  mov     rdx, r12; SourceString
0x1400feb61  call    cs:__imp_RtlCopyUnicodeString
0x1400feb68  nop     dword ptr [rax+rax+00h]
0x1400feb6d  mov     r13d, 8B0h
0x1400feb73  mov     r8d, 624F7356h
0x1400feb79  mov     edx, r13d
0x1400feb7c  mov     ecx, 40h ; '@'
0x1400feb81  call    cs:__imp_ExAllocatePool2
0x1400feb88  nop     dword ptr [rax+rax+00h]
0x1400feb8d  mov     [rbp+P], rax
0x1400feb91  test    rax, rax
0x1400feb94  jnz     short loc_1400FEBCF
0x1400feb96  mov     [rbp+var_1C], 0C000009Ah
0x1400feb9d  mov     rcx, cs:VmsIfrLog
0x1400feba4  lea     r9d, [rax+10h]
0x1400feba8  mov     dword ptr [rsp+80h+var_50], 0C000009Ah
0x1400febb0  lea     r8d, [rax+14h]
0x1400febb4  mov     dword ptr [rsp+80h+var_58], r13d
0x1400febb9  mov     dl, 2
0x1400febbb  mov     [rsp+80h+SourceString], rsi
0x1400febc0  call    WPP_RECORDER_SF_ld
0x1400febc5  mov     ebx, 14h
0x1400febca  jmp     loc_1400FF008
0x1400febcf  lea     rcx, [rdi+24A0h]
0x1400febd6  call    VmsOmpRscStructsAllocateAndInit
0x1400febdb  mov     [rbp+var_1C], eax
0x1400febde  test    eax, eax
0x1400febe0  jns     short loc_1400FEBEC
0x1400febe2  mov     ebx, 19h
0x1400febe7  jmp     loc_1400FF008
0x1400febec  test    r15d, r15d
0x1400febef  jz      short loc_1400FEC15
0x1400febf1  lea     r8, [rdi+830h]
0x1400febf8  lea     rdx, [rdi+7C8h]
0x1400febff  call    NvIoAllocateWorkerQueue
0x1400fec04  mov     [rbp+var_1C], eax
0x1400fec07  test    eax, eax
0x1400fec09  jns     short loc_1400FEC15
0x1400fec0b  mov     ebx, 1Eh
0x1400fec10  jmp     loc_1400FF008
0x1400fec15  mov     r13b, [rbp+arg_18]
0x1400fec19  mov     eax, 2
0x1400fec1e  mov     [rdi+754h], r13b
0x1400fec25  mov     r8, 20C49BA5E353F7CFh
0x1400fec2f  mov     dword ptr [rdi+0D20h], 0Dh
0x1400fec39  mov     [rdi+758h], eax
0x1400fec3f  mov     [rdi+0FC0h], eax
0x1400fec45  lea     r10d, [rax-1]
0x1400fec49  mov     [rdi+0F74h], r10b
0x1400fec50  lea     rax, [rdi+770h]
0x1400fec57  mov     [rax+8], rax
0x1400fec5b  mov     [rax], rax
0x1400fec5e  lea     rax, [rdi+790h]
0x1400fec65  mov     [rax+8], rax
0x1400fec69  mov     [rax], rax
0x1400fec6c  mov     rax, r8
0x1400fec6f  mov     [rdi+7B0h], r10d
0x1400fec76  imul    rcx, qword ptr cs:stru_140223F50, 1388h
0x1400fec81  imul    rcx
0x1400fec84  mov     rax, r8
0x1400fec87  sar     rdx, 7
0x1400fec8b  mov     rcx, rdx
0x1400fec8e  shr     rcx, 3Fh
0x1400fec92  add     rdx, rcx
0x1400fec95  mov     [rdi+24FCh], edx
0x1400fec9b  imul    rcx, qword ptr cs:stru_140223F50, 0EA60h
0x1400feca6  imul    rcx
0x1400feca9  sar     rdx, 7
0x1400fecad  mov     rax, rdx
0x1400fecb0  shr     rax, 3Fh
0x1400fecb4  add     rdx, rax
0x1400fecb7  mov     [rdi+2500h], edx
0x1400fecbd  test    r15d, r15d
0x1400fecc0  jz      loc_1400FEDF8
0x1400fecc6  mov     rcx, [rdi+830h]; Lookaside
0x1400feccd  lea     rax, [rdi+7B8h]
0x1400fecd4  mov     [rsp+80h+var_58], rax; __int64
0x1400fecd9  lea     r8, VmsOmNicPvtCompleteLinkChangeIrp
0x1400fece0  mov     r9, rdi
0x1400fece3  mov     [rsp+80h+SourceString], 21h ; '!'; __int64
0x1400fecec  mov     edx, r10d
0x1400fecef  call    NvIoAllocateWorkItem
0x1400fecf4  mov     [rbp+var_1C], eax
0x1400fecf7  test    eax, eax
0x1400fecf9  jns     short loc_1400FED24
0x1400fecfb  mov     ebx, 23h ; '#'
0x1400fed00  mov     rcx, cs:VmsIfrLog
0x1400fed07  lea     r9d, [rbx-12h]
0x1400fed0b  mov     dword ptr [rsp+80h+var_58], eax
0x1400fed0f  lea     r8d, [rbx-0Fh]
0x1400fed13  mov     dl, 2
0x1400fed15  mov     [rsp+80h+SourceString], rsi
0x1400fed1a  call    WPP_RECORDER_SF_d
0x1400fed1f  jmp     loc_1400FF00C
0x1400fed24  mov     rcx, [rdi+830h]; Lookaside
0x1400fed2b  lea     rax, [rdi+12E8h]
0x1400fed32  mov     [rsp+80h+var_58], rax; __int64
0x1400fed37  lea     r8, VmsNdkSendPnPEventWorkerRoutine
0x1400fed3e  mov     r9, rdi
0x1400fed41  mov     [rsp+80h+SourceString], 22h ; '"'; __int64
0x1400fed4a  mov     edx, 1
0x1400fed4f  call    NvIoAllocateWorkItem
0x1400fed54  mov     [rbp+var_1C], eax
0x1400fed57  test    eax, eax
0x1400fed59  jns     short loc_1400FED84
0x1400fed5b  mov     ebx, 28h ; '('
0x1400fed60  mov     rcx, cs:VmsIfrLog
0x1400fed67  lea     r9d, [rbx-16h]
0x1400fed6b  mov     dword ptr [rsp+80h+var_58], eax
0x1400fed6f  lea     r8d, [rbx-14h]
0x1400fed73  mov     dl, 2
0x1400fed75  mov     [rsp+80h+SourceString], rsi
0x1400fed7a  call    WPP_RECORDER_SF_d
0x1400fed7f  jmp     loc_1400FF00C
0x1400fed84  cmp     cs:g_NVBugFixes2509SriovMacSpoofingEnabled, ebx
0x1400fed8a  jz      short loc_1400FEDF8
0x1400fed8c  mov     [rdi+261Ch], ebx
0x1400fed92  lea     rax, [rdi+2620h]
0x1400fed99  mov     [rdi+2619h], bl
0x1400fed9f  lea     r8, VmsVmVmqIovUpdateMacFiltersWorkItem
0x1400feda6  mov     rcx, [rdi+830h]; Lookaside
0x1400fedad  mov     r9, rdi
0x1400fedb0  mov     [rsp+80h+var_58], rax; __int64
0x1400fedb5  mov     edx, 1
0x1400fedba  mov     [rsp+80h+SourceString], 29h ; ')'; __int64
0x1400fedc3  call    NvIoAllocateWorkItem
0x1400fedc8  mov     [rbp+var_1C], eax
0x1400fedcb  test    eax, eax
0x1400fedcd  jns     short loc_1400FEDF8
0x1400fedcf  mov     ebx, 2Ah ; '*'
0x1400fedd4  mov     rcx, cs:VmsIfrLog
0x1400feddb  lea     r9d, [rbx-17h]
0x1400feddf  mov     dword ptr [rsp+80h+var_58], eax
0x1400fede3  lea     r8d, [rbx-16h]
0x1400fede7  mov     dl, 2
0x1400fede9  mov     [rsp+80h+SourceString], rsi
0x1400fedee  call    WPP_RECORDER_SF_d
0x1400fedf3  jmp     loc_1400FF00C
0x1400fedf8  lea     rdx, [rdi+133Ch]; void *
0x1400fedff  lea     rcx, [rdi+1578h]; void *
0x1400fee06  call    VmsVrssInitializeRssConfig
0x1400fee0b  test    al, al
0x1400fee0d  jnz     short loc_1400FEE3C
0x1400fee0f  mov     [rbp+var_1C], 0C000009Ah
0x1400fee16  mov     rcx, cs:VmsIfrLog
0x1400fee1d  mov     r9d, 14h
0x1400fee23  mov     r8d, r9d
0x1400fee26  mov     [rsp+80h+SourceString], rsi
0x1400fee2b  mov     dl, 2
0x1400fee2d  call    WPP_RECORDER_SF_
0x1400fee32  mov     ebx, 2Dh ; '-'
0x1400fee37  jmp     loc_1400FF00C
0x1400fee3c  mov     dword ptr [rdi+0D1Ch], 5EAh
0x1400fee46  xorps   xmm0, xmm0
0x1400fee49  mov     [rdi+0FE0h], ebx
0x1400fee4f  xor     eax, eax
0x1400fee51  mov     [rdi+0FE8h], bl
0x1400fee57  mov     [rdi+105Ch], ebx
0x1400fee5d  movups  xmmword ptr [rdi+12A0h], xmm0
0x1400fee64  movups  xmmword ptr [rdi+12B0h], xmm0
0x1400fee6b  movups  xmmword ptr [rdi+12C0h], xmm0
0x1400fee72  mov     [rdi+12D0h], rax
0x1400fee79  lea     rax, [rdi+12D8h]
0x1400fee80  mov     [rax+8], rax
0x1400fee84  mov     [rax], rax
0x1400fee87  mov     [rdi+129Ch], ebx
0x1400fee8d  mov     [rdi+1298h], bl
0x1400fee93  lea     rbx, [rdi+1308h]
0x1400fee9a  mov     rcx, rbx; RunRef
0x1400fee9d  call    cs:__imp_ExInitializeRundownProtection
0x1400feea4  nop     dword ptr [rax+rax+00h]
0x1400feea9  mov     rcx, rbx; RunRef
0x1400feeac  call    cs:__imp_ExWaitForRundownProtectionRelease
0x1400feeb3  nop     dword ptr [rax+rax+00h]
0x1400feeb8  mov     rcx, rbx; RunRef
0x1400feebb  call    cs:__imp_ExRundownCompleted
0x1400feec2  nop     dword ptr [rax+rax+00h]
0x1400feec7  xorps   xmm0, xmm0
0x1400feeca  lea     rax, [rdi+850h]
0x1400feed1  movups  xmmword ptr [rdi+840h], xmm0
0x1400feed8  mov     [rdi+848h], rax
0x1400feedf  mov     ecx, 200h
0x1400feee4  mov     [rdi+842h], cx
0x1400feeeb  lea     rax, [rdi+0A60h]
  ... truncated ...
```
