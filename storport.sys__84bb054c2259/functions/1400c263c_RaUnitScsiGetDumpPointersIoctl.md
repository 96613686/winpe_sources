# RaUnitScsiGetDumpPointersIoctl

- ea: `0x1400c263c`
- end: `0x1400c360a`
- name: `RaUnitScsiGetDumpPointersIoctl`
- size: `4046`
- prototype: ``
- caller_count: `1`
- callee_count: `27`
- tags: `broker_com_uri`

## callers

- `0x140036290`

## callees

- `0x140005c50`
- `0x14000684c`
- `0x140008258`
- `0x140008348`
- `0x140008eb0`
- `0x14000e350`
- `0x14000ebfc`
- `0x14000fda0`
- `0x14000ff50`
- `0x1400290b0`
- `0x14003a150`
- `0x140044c10`
- `0x14004a0a8`
- `0x14006d1c0`
- `0x14006d298`
- `0x140070710`
- `0x1400848c4`
- `0x140093bec`
- `0x140093ca0`
- `0x140093dc0`
- `0x1400a49e0`
- `0x1400c263c`
- `0x1400cd2c0`
- `0x1400cd8f0`
- `0x14014b400`
- `0x14014b500`
- `0x14014b800`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x1400c2ee3`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400c302b`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400c3061`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400c312c`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400c2ee3`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400c302b`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400c3061`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400c312c`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1400c3312`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1400c3312`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c2f5f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c3109`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c31f0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c3210`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c3249`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c325d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c32bf`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c32db`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c2f5f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c3109`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c31f0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c3210`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c3249`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c325d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c32bf`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c32db`
- `ntoskrnl!KeInitializeEvent` at `0x1400c2bed`
- `ntoskrnl!KeInitializeEvent` at `0x1400c2bed`
- `ntoskrnl!IofCompleteRequest` at `0x1400c35d4`
- `ntoskrnl!IofCompleteRequest` at `0x1400c35d4`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400c2c89`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400c2c89`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1400c2852`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1400c2852`
- `ntoskrnl!PoFxRegisterCrashdumpDevice` at `0x1400c2826`
- `ntoskrnl!PoFxRegisterCrashdumpDevice` at `0x1400c2871`
- `ntoskrnl!PoFxRegisterCrashdumpDevice` at `0x1400c2826`
- `ntoskrnl!PoFxRegisterCrashdumpDevice` at `0x1400c2871`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1400c3078`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1400c3078`
- `ntoskrnl!IoQueryFullDriverPath` at `0x1400c2efe`
- `ntoskrnl!IoQueryFullDriverPath` at `0x1400c2efe`

## string_xrefs

- `0x1400c2ed3`: `\SystemRoot\System32\Drivers\diskdump.sys`

## pseudocode

```c
__int64 __fastcall RaUnitScsiGetDumpPointersIoctl(__int64 a1, __int64 a2)
{
  __int64 v2; // r14
  _QWORD *Srb; // r15
  char v6; // r12
  NTSTATUS AdditionalCrashDumpArea; // ebx
  _DWORD *v8; // r13
  _DWORD *Pool; // rax
  _DWORD *v10; // rdx
  _DWORD *v11; // rbx
  _OWORD *v12; // rax
  __int128 v13; // xmm1
  __int64 v14; // rcx
  _QWORD *v15; // rcx
  __int64 v16; // rax
  __int64 v17; // rcx
  _QWORD *v18; // rdi
  __int64 v19; // rbx
  char *v20; // r8
  PVOID v21; // rax
  PVOID v22; // rcx
  __int64 v23; // r8
  PVOID v24; // rbx
  __int64 v25; // rdx
  _DWORD *v26; // rcx
  __int64 ContiguousIoResources; // rax
  __int64 v28; // rdx
  __int64 v29; // rcx
  __int64 v30; // r11
  __int64 v31; // r8
  int v32; // eax
  __int64 v33; // rcx
  __int64 v34; // rdx
  __int64 v35; // r8
  __int64 v36; // r9
  _OWORD *v37; // rcx
  int v38; // eax
  int v39; // eax
  char v40; // al
  const wchar_t *v41; // r8
  _DWORD *v42; // rax
  char v43; // r11
  _DWORD *v44; // rcx
  _OWORD *v45; // rdx
  unsigned int v46; // ecx
  unsigned int v47; // eax
  int v48; // ecx
  unsigned int v49; // ecx
  unsigned int v50; // eax
  int v51; // eax
  char *v52; // rcx
  struct _UNICODE_STRING *v53; // r13
  int FullDriverPath; // eax
  __int64 v55; // rdx
  __int64 v56; // r8
  void *v57; // rcx
  size_t v58; // rbx
  char *v59; // rdi
  void *v60; // rcx
  PVOID v61; // r13
  void *v62; // rcx
  _QWORD *v63; // rax
  bool v64; // zf
  unsigned __int64 v65; // rcx
  __int64 v66; // rdx
  int *v67; // rax
  int v68; // ecx
  __int64 *v69; // rdx
  __int64 v70; // rdx
  unsigned int v71; // r13d
  unsigned __int8 v72; // r10
  char *v73; // r11
  char v74; // di
  _BYTE *v75; // r9
  unsigned __int64 v76; // r14
  __int64 v77; // r8
  int v78; // ecx
  char v79; // cl
  char v80; // r14
  char v81; // r11
  _BYTE *v82; // rax
  char v83; // r8
  char *v84; // r8
  unsigned int v85; // eax
  char v87; // [rsp+60h] [rbp-79h]
  unsigned __int16 v88; // [rsp+60h] [rbp-79h]
  char v89; // [rsp+60h] [rbp-79h]
  __int64 v90; // [rsp+68h] [rbp-71h]
  NTSTATUS v91; // [rsp+70h] [rbp-69h]
  __int64 v92; // [rsp+78h] [rbp-61h]
  __int64 v93; // [rsp+80h] [rbp-59h]
  _QWORD *v94; // [rsp+88h] [rbp-51h]
  UNICODE_STRING String2; // [rsp+90h] [rbp-49h] BYREF
  _OWORD *v96; // [rsp+A0h] [rbp-39h]
  PVOID v97; // [rsp+A8h] [rbp-31h]
  PVOID v98; // [rsp+B0h] [rbp-29h]
  PVOID P; // [rsp+B8h] [rbp-21h]
  __int64 Length; // [rsp+C0h] [rbp-19h]
  struct _UNICODE_STRING DestinationString; // [rsp+C8h] [rbp-11h] BYREF
  WCHAR pszDest[16]; // [rsp+D8h] [rbp-1h] BYREF

  v2 = *(_QWORD *)(a1 + 24);
  Srb = 0;
  *(_QWORD *)(a2 + 56) = 0;
  String2 = 0;
  v6 = 1;
  if ( *(_BYTE *)(a2 + 64) )
  {
    AdditionalCrashDumpArea = -1073741790;
    goto LABEL_144;
  }
  if ( *(_DWORD *)(*(_QWORD *)(a2 + 184) + 8LL) < 0x68u )
  {
    AdditionalCrashDumpArea = -1073741789;
    goto LABEL_144;
  }
  v8 = *(_DWORD **)(a2 + 24);
  memset_0(v8, 0, 0x68u);
  Pool = (_DWORD *)RaidAllocatePool(64, 320, 1145266514, *(_QWORD *)(a1 + 8));
  P = Pool;
  v10 = Pool;
  if ( !Pool )
  {
    AdditionalCrashDumpArea = -1073741670;
    goto LABEL_144;
  }
  *Pool = 1;
  v11 = Pool + 62;
  Pool[1] = 248;
  Pool[2] = 1145917508;
  v12 = Pool + 4;
  v94 = 0;
  v87 = 0;
  *v12 = *(_OWORD *)(v2 + 368);
  v96 = v12;
  v13 = *(_OWORD *)(v2 + 384);
  v97 = 0;
  v93 = 0;
  v12[1] = v13;
  v92 = 0;
  v12[2] = *(_OWORD *)(v2 + 400);
  v12[3] = *(_OWORD *)(v2 + 416);
  v12[4] = *(_OWORD *)(v2 + 432);
  v12[5] = *(_OWORD *)(v2 + 448);
  v12[6] = *(_OWORD *)(v2 + 464);
  v12[7] = *(_OWORD *)(v2 + 480);
  v12[8] = *(_OWORD *)(v2 + 496);
  v12[9] = *(_OWORD *)(v2 + 512);
  v12[10] = *(_OWORD *)(v2 + 528);
  v12[11] = *(_OWORD *)(v2 + 544);
  v12[12] = *(_OWORD *)(v2 + 560);
  v12[13] = *(_OWORD *)(v2 + 576);
  v14 = *(_QWORD *)(v2 + 592);
  if ( (*(_DWORD *)(v14 + 184) & 0x80u) != 0 && (*(_DWORD *)(v14 + 188) & 2) != 0 )
    *((_WORD *)v10 + 120) = HiberFileHybridPriority;
  else
    *((_WORD *)v10 + 120) = -1;
  if ( (unsigned __int8)RaidUnitCheckAndAcquirePoFx(a1) )
  {
    if ( (int)PoFxRegisterCrashdumpDevice(**(_QWORD **)(a1 + 1872)) >= 0 )
    {
      *(_BYTE *)v11 = 1;
      v87 = 1;
      *((_QWORD *)v11 + 1) = **(_QWORD **)(a1 + 1872);
    }
    ExReleaseRundownProtectionCacheAware(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(a1 + 1864));
  }
  v15 = *(_QWORD **)(*(_QWORD *)(a1 + 24) + 5024LL);
  if ( v15 && (int)PoFxRegisterCrashdumpDevice(*v15) >= 0 )
  {
    *((_BYTE *)v11 + 32) = 1;
    v87 = 1;
    *((_QWORD *)v11 + 5) = **(_QWORD **)(*(_QWORD *)(a1 + 24) + 5024LL);
  }
  *(_WORD *)(*(_QWORD *)(a1 + 24) + 5090LL) = 1;
  *(_WORD *)(*(_QWORD *)(a1 + 24) + 5088LL) = 40;
  if ( (int)RaidQueryCrashdumpFunctions(*(PDEVICE_OBJECT *)(*(_QWORD *)(a1 + 24) + 24LL)) >= 0
    && (v16 = *(_QWORD *)(a1 + 24), (v17 = *(_QWORD *)(v16 + 5120)) != 0)
    && *(_QWORD *)(v16 + 5112) )
  {
    *((_QWORD *)v11 + 7) = v17;
    *((_QWORD *)v11 + 8) = *(_QWORD *)(*(_QWORD *)(a1 + 24) + 5096LL);
  }
  else
  {
    *(_WORD *)(*(_QWORD *)(a1 + 24) + 5090LL) = 0;
    if ( !v87 )
      goto LABEL_24;
  }
  *((_QWORD *)v8 + 12) = v11;
  *((_QWORD *)v8 + 11) = StorDumpDevicePowerOn;
LABEL_24:
  *((_QWORD *)v11 + 2) = a1 + 1862;
  *((_QWORD *)v11 + 6) = *(_QWORD *)(a1 + 24) + 4957LL;
  *((_QWORD *)v11 + 3) = a1 + 1863;
  v98 = (PVOID)RaidAllocatePool(64, 88, 1145266514, *(_QWORD *)(a1 + 8));
  if ( !v98 )
  {
    v18 = 0;
    AdditionalCrashDumpArea = -1073741670;
LABEL_127:
    v61 = v97;
    ExFreePoolWithTag(P, 0x44436152u);
    if ( v98 )
      ExFreePoolWithTag(v98, 0x44436152u);
    if ( v18 )
    {
      v62 = (void *)v18[10];
      if ( v62 )
        ExFreePoolWithTag(v62, 0);
      ExFreePoolWithTag(v18, 0x44436152u);
    }
    goto LABEL_133;
  }
  v90 = RaidAllocatePool(64, 88, 1145266514, *(_QWORD *)(a1 + 8));
  v19 = v90;
  if ( !v90 )
  {
    AdditionalCrashDumpArea = -1073741670;
    v18 = 0;
    goto LABEL_127;
  }
  RtlStringCbPrintfW((NTSTRSAFE_PWSTR)v98 + 4, 0x1Eu, L"diskdump.sys");
  RtlStringCbPrintfW((NTSTRSAFE_PWSTR)v98 + 19, 0x1Eu, L"storport.sys");
  v21 = v98;
  v22 = P;
  *(_QWORD *)v98 = v90;
  *(_QWORD *)v90 = 0;
  *((_QWORD *)v8 + 5) = v21;
  *((_QWORD *)v8 + 10) = a1 + 1863;
  *v8 = 4;
  v8[1] = 104;
  *((_QWORD *)v8 + 1) = v22;
  *((_QWORD *)v8 + 2) = 0;
  *((_BYTE *)v8 + 28) = 1;
  *((_QWORD *)v8 + 4) = 0;
  if ( (unsigned __int8)(*(_BYTE *)(v2 + 512) - 2) <= 2u )
    v8[12] |= 1u;
  if ( (*(_DWORD *)(*(_QWORD *)(v2 + 592) + 184LL) & 0x20) != 0 )
    v8[12] |= 4u;
  if ( !*(_BYTE *)(v2 + 4434) || (*(_DWORD *)(*(_QWORD *)(v2 + 592) + 184LL) & 8) != 0 )
  {
    v97 = (PVOID)RaidAllocatePool(64, 112, 1145266514, *(_QWORD *)(a1 + 8));
    v24 = v97;
    if ( !v97 )
      goto LABEL_35;
    LOBYTE(v23) = *(_BYTE *)(v2 + 466);
    Srb = (_QWORD *)RaidAllocateSrb(*(_QWORD *)(a1 + 8), 38, v23);
    if ( !Srb )
      goto LABEL_35;
    v26 = (_DWORD *)(v2 + 324);
    if ( *(_DWORD *)v2 != 1314275652 )
      v26 = (_DWORD *)(v2 + 508);
    ContiguousIoResources = StorAllocateContiguousIoResources(((*v26 + 7) & 0xFFFFFFF8) + 1200, v25, v2);
    v93 = ContiguousIoResources;
    if ( !ContiguousIoResources )
    {
LABEL_35:
      AdditionalCrashDumpArea = -1073741670;
LABEL_126:
      v18 = (_QWORD *)v90;
      goto LABEL_127;
    }
    v92 = ContiguousIoResources + 48;
    RaidZeroXrb(ContiguousIoResources + 48, v28, 0, 0);
    *(_BYTE *)(v92 + 17) |= 8u;
    *(_QWORD *)(v92 + 176) = a2;
    *(_QWORD *)(v92 + 184) = v24;
    *(_QWORD *)(v92 + 168) = Srb;
    if ( *(_BYTE *)(v2 + 466) == 1 )
    {
      Srb[8] = v24;
      Srb[12] = v92;
      Srb[10] = a2;
      *((_DWORD *)Srb + 5) = 38;
      *((_DWORD *)Srb + 15) = 112;
      *((_DWORD *)Srb + 6) = 256;
      v94 = Srb;
      if ( !*(_BYTE *)(v2 + 4434) )
        *((_DWORD *)Srb + 6) = 64;
      v29 = *((unsigned int *)Srb + 13);
      *((_DWORD *)Srb + 10) = 10;
      *((_BYTE *)Srb + v29 + 8) = *(_BYTE *)(a1 + 104);
      *((_BYTE *)Srb + v29 + 9) = *(_BYTE *)(a1 + 105);
      *((_BYTE *)Srb + v29 + 10) = *(_BYTE *)(a1 + 106);
    }
    else
    {
      Srb[3] = v24;
      Srb[6] = v92;
      *((_BYTE *)Srb + 2) = 38;
      *((_DWORD *)Srb + 4) = 112;
      *(_WORD *)Srb = 88;
      *((_DWORD *)Srb + 3) = 256;
      if ( !*(_BYTE *)(v2 + 4434) )
        *((_DWORD *)Srb + 3) = 64;
      *((_DWORD *)Srb + 5) = 10;
      *((_BYTE *)Srb + 5) = *(_BYTE *)(a1 + 104);
      *((_BYTE *)Srb + 6) = *(_BYTE *)(a1 + 105);
      *((_BYTE *)Srb + 7) = *(_BYTE *)(a1 + 106);
    }
    RaSrbSetMiniportContext(v2, Srb, v93 + 1200);
    KeInitializeEvent((PRKEVENT)(v30 + 664), NotificationEvent, 0);
    v31 = v92;
    *(_QWORD *)(v92 + 656) = RaidXrbSignalCompletion;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 27, WPP_79b784db0f1333d9a4638a6d2649ad59_Traceguids, v92, Srb);
      v31 = v92;
    }
    if ( *(_BYTE *)(v2 + 4434) )
      v32 = RaidAdapterRaiseIrqlAndExecuteXrb(v2, v31);
    else
      v32 = RaidAdapterPostScatterGatherExecute(v2, v31);
    AdditionalCrashDumpArea = v32;
    if ( v32 >= 0 )
    {
      KeWaitForSingleObject((PVOID)(v92 + 664), Executive, 0, 0, 0);
      LOBYTE(v33) = *((_BYTE *)Srb + 3);
      AdditionalCrashDumpArea = RaidSrbStatusToNtStatus(v33, v34, v35, v36);
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_DD(
        WPP_GLOBAL_Control->AttachedDevice,
        28,
        WPP_79b784db0f1333d9a4638a6d2649ad59_Traceguids,
        (unsigned int)AdditionalCrashDumpArea,
        *((unsigned __int8 *)Srb + 3));
    }
    if ( AdditionalCrashDumpArea < 0 )
    {
      if ( !*(_BYTE *)(v2 + 4434) || (*(_DWORD *)(*(_QWORD *)(v2 + 592) + 184LL) & 0x1000) != 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_qD(
            WPP_GLOBAL_Control->AttachedDevice,
            29,
            WPP_79b784db0f1333d9a4638a6d2649ad59_Traceguids,
            v92,
            AdditionalCrashDumpArea);
        }
        goto LABEL_126;
      }
    }
    else
    {
      v20 = (char *)v97;
      v37 = v96;
      v38 = *((_DWORD *)v97 + 20);
      if ( v38 )
      {
        *((_DWORD *)v96 + 6) = v38;
        v39 = *((_DWORD *)v20 + 20);
      }
      else
      {
        v39 = *((_DWORD *)v96 + 6);
      }
      v8[15] = v39;
      *((_QWORD *)v37 + 8) = *((_QWORD *)v20 + 8);
      if ( !*(_BYTE *)(v2 + 4434) )
      {
        *((_DWORD *)v37 + 1) = *((_DWORD *)v20 + 18);
        *((_DWORD *)v37 + 2) = *((_DWORD *)v20 + 19);
        *((_DWORD *)v37 + 7) = *((_DWORD *)v20 + 21);
        *((_DWORD *)v37 + 12) = *((_DWORD *)v20 + 22);
        *((_DWORD *)v37 + 13) = *((_DWORD *)v20 + 23);
        *((_QWORD *)v37 + 7) = *((_QWORD *)v20 + 12);
        *((_BYTE *)v37 + 72) = v20[104];
        *((_BYTE *)v37 + 82) = v20[105];
        *((_BYTE *)v37 + 89) = v20[106];
        v40 = v20[107];
        v41 = (const wchar_t *)(v20 + 4);
        *((_BYTE *)v37 + 97) = v40;
        if ( !*v41 )
        {
          AdditionalCrashDumpArea = -1073741637;
          goto LABEL_126;
        }
        AdditionalCrashDumpArea = RtlStringCbPrintfW((NTSTRSAFE_PWSTR)(v90 + 8), 0x1Eu, v41);
        if ( AdditionalCrashDumpArea < 0 )
          goto LABEL_126;
        v42 = v97;
        *((_QWORD *)v8 + 8) = 0;
        *((_QWORD *)v8 + 9) = 0;
        v8[6] = v42[14];
      }
      *(_BYTE *)(a1 + 1861) = 1;
    }
    v19 = v90;
  }
  RaidDriverGetName(*(_QWORD *)(v2 + 16), &String2, v20);
  if ( *(_BYTE *)(v2 + 4434) != v43 )
  {
    RtlStringCbPrintfW((NTSTRSAFE_PWSTR)(v19 + 8), 0x1Eu, L"%ws.sys", String2.Buffer);
    v44 = (_DWORD *)(v2 + 324);
    if ( *(_DWORD *)v2 != 1314275652 )
      v44 = (_DWORD *)(v2 + 508);
    v45 = v96;
    v46 = (*v44 + 7) & 0xFFFFFFF8;
    if ( !v46 )
      v46 = 16;
    v47 = v8[15];
    v8[6] = (*(_DWORD *)(v2 + 928) + 4095 + 16 * v46) & 0xFFFFF000;
    if ( !v47 )
    {
      v47 = *((_DWORD *)v45 + 6);
      v8[15] = v47;
    }
    v48 = *(_DWORD *)(v2 + 892);
    if ( v48 )
    {
      v49 = (v48 << 12) - 4096;
      if ( v47 >= v49 )
        v47 = v49;
      v8[15] = v47;
      v50 = *((_DWORD *)v45 + 6);
      if ( v50 >= v49 )
        v50 = v49;
      *((_DWORD *)v45 + 6) = v50;
    }
    *((_QWORD *)v8 + 8) = *(_QWORD *)(v2 + 880);
    *((_QWORD *)v8 + 9) = v2 + 960;
    if ( (*(_DWORD *)(v2 + 588) & 1) != 0 || (v51 = *(_DWORD *)(a1 + 3432), v51 == 10) || v51 == 1 )
      v8[12] |= 2u;
  }
  v52 = (char *)v98;
  v8[12] |= 8u;
  RtlInitUnicodeString((PUNICODE_STRING)(v52 + 72), L"\\SystemRoot\\System32\\Drivers\\diskdump.sys");
  v53 = (struct _UNICODE_STRING *)(v19 + 72);
  FullDriverPath = IoQueryFullDriverPath(*(_QWORD *)(*(_QWORD *)(v2 + 16) + 8LL), v19 + 72);
  if ( FullDriverPath >= 0 && !*(_BYTE *)(v2 + 4434) )
  {
    memset(pszDest, 0, 30);
    DestinationString = 0;
    v91 = RtlStringCbPrintfW(pszDest, 0x1Eu, L"%ws.sys", String2.Buffer);
    if ( v91 < 0
      || (RtlInitUnicodeString(&DestinationString, pszDest), v88 = v53->Length, v53->Length <= DestinationString.Length) )
    {
      v57 = *(void **)(v19 + 80);
      if ( v57 )
      {
        ExFreePoolWithTag(v57, 0);
        *v53 = 0;
      }
    }
    else
    {
      Length = DestinationString.Length;
      String2 = 0;
      RtlInitUnicodeString(&String2, (PCWSTR)(v19 + 8));
      if ( RtlCompareUnicodeString(&DestinationString, &String2, 1u) )
      {
        v58 = v88 - Length;
        if ( DestinationString.Length >= String2.Length )
        {
          v18 = (_QWORD *)v90;
          memset_0((void *)(v58 + *(_QWORD *)(v90 + 80)), 0, DestinationString.Length);
          memmove((void *)(v58 + *(_QWORD *)(v90 + 80)), String2.Buffer, String2.Length);
          v53->Length = String2.Length + v58;
          goto LABEL_96;
        }
        v59 = (char *)RaidAllocatePool(
                        64,
                        String2.Length + *(unsigned __int16 *)(v90 + 74) - DestinationString.Length + 2LL,
                        1145266514,
                        *(_QWORD *)(a1 + 8));
        if ( v59 )
        {
          memmove(v59, *(const void **)(v90 + 80), v58);
          memmove(&v59[v58], String2.Buffer, String2.Length);
        }
        v60 = *(void **)(v90 + 80);
        if ( v60 )
        {
          ExFreePoolWithTag(v60, 0);
          *v53 = 0;
        }
        if ( v59 )
          RtlInitUnicodeString(v53, (PCWSTR)v59);
      }
    }
    v18 = (_QWORD *)v90;
LABEL_96:
    FullDriverPath = v91;
    goto LABEL_97;
  }
  v18 = (_QWORD *)v90;
LABEL_97:
  AdditionalCrashDumpArea = 0;
  if ( FullDriverPath >= 0 )
    AdditionalCrashDumpArea = FullDriverPath;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    WPP_SF_S(WPP_GLOBAL_Control->AttachedDevice, v55, v56, v18 + 1);
  }
  if ( *(_DWORD *)(v2 + 560) )
    AdditionalCrashDumpArea = StorPortGetAdditionalCrashDumpArea(v2, v96);
  if ( AdditionalCrashDumpArea < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        31,
        WPP_79b784db0f1333d9a4638a6d2649ad59_Traceguids,
        (unsigned int)AdditionalCrashDumpArea);
    }
    goto LABEL_127;
  }
  v61 = v97;
  *(_QWORD *)(a2 + 56) = 104;
LABEL_133:
  if ( v93 )
  {
    RaidXrbDeallocateResources(v92, 0);
    StorFreeContiguousIoResources(v2, v93);
  }
  if ( Srb )
  {
    if ( *((_BYTE *)Srb + 2) == 40 )
    {
      v63 = v94;
      if ( !v94 )
        v63 = Srb;
      v63[10] = 0;
      v63[13] = 0;
    }
    else
    {
      Srb[6] = 0;
      Srb[7] = 0;
    }
    ExFreePoolWithTag(Srb, 0x72536152u);
  }
  LODWORD(Srb) = 0;
  if ( v61 )
    ExFreePoolWithTag(v61, 0x44436152u);
LABEL_144:
  v64 = StorEtwLoggingEnabled == 0;
  *(_BYTE *)(a2 + 141) = -84;
  *(_DWORD *)(a2 + 48) = AdditionalCrashDumpArea;
  if ( v64 )
    goto LABEL_207;
  DestinationString = 0;
  IoGetActivityIdIrp(a2, &DestinationString);
  v66 = *(_QWORD *)(a2 + 184);
  if ( *(_BYTE *)v66 == 14 )
  {
    if ( (byte_140177432 & 8) == 0 )
      goto LABEL_207;
    v69 = EventNonReadWriteRequestComplete;
    goto LABEL_206;
  }
  if ( *(_BYTE *)v66 != 15 )
  {
    if ( *(_BYTE *)v66 != 27 )
      goto LABEL_207;
    if ( *(_BYTE *)(v66 + 1) == 7 && !*(_DWORD *)(v66 + 8) )
    {
      if ( (byte_140177432 & 0x40) != 0 )
      {
        v67 = *(int **)(a2 + 56);
        if ( v67 )
          v68 = *v67;
        else
          v68 = 0;
        McTemplateK0pqd_EtwWriteTransfer(v68, v66, (unsigned int)&DestinationString, a2, v68, *(_DWORD *)(a2 + 48));
      }
      goto LABEL_207;
    }
    if ( (byte_140177432 & 0x20) == 0 )
      goto LABEL_207;
    v69 = EventPnpRequestComplete;
LABEL_206:
    McTemplateK0pd_EtwWriteTransfer(v65, v69, &DestinationString, a2, *(_DWORD *)(a2 + 48));
    goto LABEL_207;
  }
  if ( byte_140177431 >= 0 )
    goto LABEL_207;
  v70 = *(_QWORD *)(v66 + 8);
  if ( *(_BYTE *)(v70 + 2) != 40 )
  {
    v79 = *(_BYTE *)(v70 + 72);
    v75 = *(_BYTE **)(v70 + 32);
    v72 = *(_BYTE *)(v70 + 11);
    v74 = *(_BYTE *)(v70 + 4);
    if ( *(_BYTE *)(v70 + 2) )
      goto LABEL_207;
LABEL_185:
    LOBYTE(v65) = v79 - 8;
    if ( (v65 & 0x5D) != 0 )
      goto LABEL_207;
    v80 = *(_BYTE *)(v70 + 3);
    if ( v80 == 1 || !v75 || !v72 )
      goto LABEL_202;
    LOBYTE(v70) = 0;
    v65 = (unsigned __int64)&v75[v72];
    v81 = 0;
    v82 = v75 + 8;
    v83 = 0;
    if ( (unsigned __int8)((*v75 & 0x7F) - 114) <= 1u )
    {
      if ( (unsigned __int64)v82 <= v65 )
      {
        v81 = v75[2];
        LOBYTE(v70) = v75[1] & 0xF;
        v83 = v75[3];
        goto LABEL_201;
      }
    }
    else if ( (unsigned __int64)v82 <= v65 )
    {
      v84 = v75 + 13;
      LOBYTE(v70) = v75[2] & 0xF;
      v85 = v72;
      if ( (unsigned int)(unsigned __int8)v75[7] + 8 <= v72 )
        v85 = (unsigned __int8)v75[7] + 8;
      v65 = (unsigned __int64)&v75[v85];
      if ( (unsigned __int64)v84 <= v65 )
        v81 = v75[12];
      if ( (unsigned __int64)(v75 + 14) > v65 )
        v83 = 0;
      else
        v83 = *v84;
LABEL_201:
      if ( v6 )
      {
LABEL_203:
        McTemplateK0pduuuuup_EtwWriteTransfer(
          v65,
          v70,
          (unsigned int)&DestinationString,
          a2,
          *(_DWORD *)(a2 + 48),
          v80,
          v74,
          v70,
          v81,
          v83,
          a2);
        goto LABEL_207;
      }
LABEL_202:
      LOBYTE(v70) = 0;
      v81 = 0;
      v83 = 0;
      goto LABEL_203;
    }
    v6 = 0;
    goto LABEL_201;
  }
  if ( *(_DWORD *)(v70 + 20) )
    goto LABEL_207;
  v71 = *(_DWORD *)(v70 + 56);
  if ( !v71 )
    goto LABEL_207;
  v72 = 0;
  v89 = 0;
  v73 = 0;
  v74 = 0;
  v75 = 0;
  while ( 1 )
  {
    v65 = *(unsigned int *)(v70 + 4LL * (unsigned int)Srb + 120);
    if ( (unsigned int)v65 >= 0x80 )
    {
      v76 = *(unsigned int *)(v70 + 16);
      if ( (unsigned int)v65 < (unsigned int)v76 )
        break;
    }
LABEL_178:
    LODWORD(Srb) = (_DWORD)Srb + 1;
    if ( (unsigned int)Srb >= v71 )
      goto LABEL_179;
  }
  v77 = (unsigned int)v65;
  v78 = *(_DWORD *)(v65 + v70) - 64;
  if ( v78 )
  {
    LODWORD(v65) = v78 - 1;
    if ( (_DWORD)v65 )
    {
      if ( (_DWORD)v65 == 1 )
      {
        LODWORD(v65) = v77 + 40;
        if ( v77 + 40 <= v76 )
        {
          if ( *(_DWORD *)(v77 + v70 + 12) )
            v73 = (char *)(v77 + v70 + 32);
          v75 = *(_BYTE **)(v77 + v70 + 24);
          goto LABEL_171;
        }
      }
    }
    else
    {
      LODWORD(v65) = v77 + 56;
      if ( v77 + 56 <= v76 )
      {
        v89 = 1;
        if ( *(_BYTE *)(v77 + v70 + 10) )
          v73 = (char *)(v77 + v70 + 24);
        v74 = *(_BYTE *)(v77 + v70 + 8);
        v75 = *(_BYTE **)(v77 + v70 + 16);
        v72 = *(_BYTE *)(v77 + v70 + 9);
      }
    }
    goto LABEL_177;
  }
  LODWORD(v65) = v77 + 40;
  if ( v77 + 40 > v76 )
  {
LABEL_177:
    if ( v89 )
      goto LABEL_179;
    goto LABEL_178;
  }
  if ( *(_BYTE *)(v77 + v70 + 10) )
    v73 = (char *)(v77 + v70 + 24);
  v75 = *(_BYTE **)(v77 + v70 + 16);
LABEL_171:
  v74 = *(_BYTE *)(v77 + v70 + 8);
  v72 = *(_BYTE *)(v77 + v70 + 9);
LABEL_179:
  if ( v73 )
  {
    v79 = *v73;
    goto LABEL_185;
  }
LABEL_207:
  IofCompleteRequest((PIRP)a2, 0);
  return (unsigned int)AdditionalCrashDumpArea;
}

```

## disassembly

```asm
0x1400c263c  mov     [rsp-8+arg_10], rbx
0x1400c2641  push    rbp
0x1400c2642  push    rsi
0x1400c2643  push    rdi
0x1400c2644  push    r12
0x1400c2646  push    r13
0x1400c2648  push    r14
0x1400c264a  push    r15
0x1400c264c  lea     rbp, [rsp-27h]
0x1400c2651  sub     rsp, 100h
0x1400c2658  mov     rax, cs:__security_cookie
0x1400c265f  xor     rax, rsp
0x1400c2662  mov     [rbp+57h+var_38], rax
0x1400c2666  mov     r14, [rcx+18h]
0x1400c266a  xor     r15d, r15d
0x1400c266d  xorps   xmm0, xmm0
0x1400c2670  mov     rsi, rdx
0x1400c2673  mov     rdi, rcx
0x1400c2676  mov     [rdx+38h], r15
0x1400c267a  movups  xmmword ptr [rbp+57h+String2.Length], xmm0
0x1400c267e  lea     r12d, [r15+1]
0x1400c2682  lea     r13d, [r15+28h]
0x1400c2686  cmp     [rdx+40h], r15b
0x1400c268a  jz      short loc_1400C2696
0x1400c268c  mov     ebx, 0C0000022h
0x1400c2691  jmp     loc_1400C32ED
0x1400c2696  mov     rax, [rdx+0B8h]
0x1400c269d  cmp     dword ptr [rax+8], 68h ; 'h'
0x1400c26a1  jnb     short loc_1400C26AD
0x1400c26a3  mov     ebx, 0C0000023h
0x1400c26a8  jmp     loc_1400C32ED
0x1400c26ad  mov     r13, [rdx+18h]
0x1400c26b1  xor     edx, edx; Val
0x1400c26b3  mov     rcx, r13; void *
0x1400c26b6  lea     r8d, [rdx+68h]; Size
0x1400c26ba  call    memset_0
0x1400c26bf  mov     r9, [rdi+8]
0x1400c26c3  mov     edx, 140h
0x1400c26c8  mov     ecx, 40h ; '@'
0x1400c26cd  mov     r8d, 44436152h
0x1400c26d3  call    RaidAllocatePool
0x1400c26d8  mov     [rbp+57h+P], rax
0x1400c26dc  mov     rdx, rax
0x1400c26df  test    rax, rax
0x1400c26e2  jnz     short loc_1400C26EE
0x1400c26e4  mov     ebx, 0C000009Ah
0x1400c26e9  jmp     loc_1400C32E7
0x1400c26ee  mov     [rax], r12d
0x1400c26f1  lea     rbx, [rax+0F8h]
0x1400c26f8  mov     dword ptr [rax+4], 0F8h
0x1400c26ff  xor     ecx, ecx
0x1400c2701  mov     dword ptr [rax+8], 444D5044h
0x1400c2708  add     rax, 10h
0x1400c270c  movups  xmm0, xmmword ptr [r14+170h]
0x1400c2714  mov     [rbp+57h+var_A8], rcx
0x1400c2718  mov     byte ptr [rbp+57h+var_D0], cl
0x1400c271b  movups  xmmword ptr [rax], xmm0
0x1400c271e  mov     [rbp+57h+var_90], rax
0x1400c2722  movups  xmm1, xmmword ptr [r14+180h]
0x1400c272a  mov     [rbp+57h+var_88], r15
0x1400c272e  mov     [rbp+57h+var_B0], r15
0x1400c2732  movups  xmmword ptr [rax+10h], xmm1
0x1400c2736  mov     [rbp+57h+var_B8], r15
0x1400c273a  movups  xmm0, xmmword ptr [r14+190h]
0x1400c2742  movups  xmmword ptr [rax+20h], xmm0
0x1400c2746  movups  xmm1, xmmword ptr [r14+1A0h]
0x1400c274e  movups  xmmword ptr [rax+30h], xmm1
0x1400c2752  movups  xmm0, xmmword ptr [r14+1B0h]
0x1400c275a  movups  xmmword ptr [rax+40h], xmm0
0x1400c275e  movups  xmm1, xmmword ptr [r14+1C0h]
0x1400c2766  movups  xmmword ptr [rax+50h], xmm1
0x1400c276a  movups  xmm0, xmmword ptr [r14+1D0h]
0x1400c2772  movups  xmmword ptr [rax+60h], xmm0
0x1400c2776  movups  xmm1, xmmword ptr [r14+1E0h]
0x1400c277e  movups  xmmword ptr [rax+70h], xmm1
0x1400c2782  movups  xmm0, xmmword ptr [r14+1F0h]
0x1400c278a  movups  xmmword ptr [rax+80h], xmm0
0x1400c2791  movups  xmm1, xmmword ptr [r14+200h]
0x1400c2799  movups  xmmword ptr [rax+90h], xmm1
0x1400c27a0  movups  xmm0, xmmword ptr [r14+210h]
0x1400c27a8  movups  xmmword ptr [rax+0A0h], xmm0
0x1400c27af  movups  xmm1, xmmword ptr [r14+220h]
0x1400c27b7  movups  xmmword ptr [rax+0B0h], xmm1
0x1400c27be  movups  xmm0, xmmword ptr [r14+230h]
0x1400c27c6  movups  xmmword ptr [rax+0C0h], xmm0
0x1400c27cd  movups  xmm1, xmmword ptr [r14+240h]
0x1400c27d5  movups  xmmword ptr [rax+0D0h], xmm1
0x1400c27dc  mov     rcx, [r14+250h]
0x1400c27e3  mov     eax, [rcx+0B8h]
0x1400c27e9  test    al, al
0x1400c27eb  jns     short loc_1400C2807
0x1400c27ed  mov     eax, [rcx+0BCh]
0x1400c27f3  test    al, 2
0x1400c27f5  jz      short loc_1400C2807
0x1400c27f7  movzx   eax, cs:HiberFileHybridPriority
0x1400c27fe  mov     [rdx+0F0h], ax
0x1400c2805  jmp     short loc_1400C2810
0x1400c2807  mov     word ptr [rdx+0F0h], 0FFFFh
0x1400c2810  mov     rcx, rdi
0x1400c2813  call    RaidUnitCheckAndAcquirePoFx
0x1400c2818  test    al, al
0x1400c281a  jz      short loc_1400C285E
0x1400c281c  mov     rcx, [rdi+750h]
0x1400c2823  mov     rcx, [rcx]
0x1400c2826  call    cs:__imp_PoFxRegisterCrashdumpDevice
0x1400c282d  nop     dword ptr [rax+rax+00h]
0x1400c2832  test    eax, eax
0x1400c2834  js      short loc_1400C284B
0x1400c2836  mov     [rbx], r12b
0x1400c2839  mov     rax, [rdi+750h]
0x1400c2840  mov     byte ptr [rbp+57h+var_D0], r12b
0x1400c2844  mov     rcx, [rax]
0x1400c2847  mov     [rbx+8], rcx
0x1400c284b  mov     rcx, [rdi+748h]; RunRefCacheAware
0x1400c2852  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x1400c2859  nop     dword ptr [rax+rax+00h]
0x1400c285e  mov     rax, [rdi+18h]
0x1400c2862  mov     rcx, [rax+13A0h]
0x1400c2869  test    rcx, rcx
0x1400c286c  jz      short loc_1400C289B
0x1400c286e  mov     rcx, [rcx]
0x1400c2871  call    cs:__imp_PoFxRegisterCrashdumpDevice
0x1400c2878  nop     dword ptr [rax+rax+00h]
0x1400c287d  test    eax, eax
0x1400c287f  js      short loc_1400C289B
0x1400c2881  mov     [rbx+20h], r12b
0x1400c2885  mov     rax, [rdi+18h]
0x1400c2889  mov     byte ptr [rbp+57h+var_D0], r12b
0x1400c288d  mov     rcx, [rax+13A0h]
0x1400c2894  mov     rax, [rcx]
0x1400c2897  mov     [rbx+28h], rax
0x1400c289b  mov     rax, [rdi+18h]
0x1400c289f  mov     [rax+13E2h], r12w
0x1400c28a7  mov     rax, [rdi+18h]
0x1400c28ab  mov     word ptr [rax+13E0h], 28h ; '('
0x1400c28b4  mov     rcx, [rdi+18h]
0x1400c28b8  lea     rdx, [rcx+13E0h]
0x1400c28bf  mov     rcx, [rcx+18h]; DeviceObject
0x1400c28c3  call    RaidQueryCrashdumpFunctions
0x1400c28c8  xor     edx, edx
0x1400c28ca  test    eax, eax
0x1400c28cc  js      short loc_1400C28FC
0x1400c28ce  mov     rax, [rdi+18h]
0x1400c28d2  mov     rcx, [rax+1400h]
0x1400c28d9  test    rcx, rcx
0x1400c28dc  jz      short loc_1400C28FC
0x1400c28de  cmp     [rax+13F8h], rdx
0x1400c28e5  jz      short loc_1400C28FC
0x1400c28e7  mov     [rbx+38h], rcx
0x1400c28eb  mov     rax, [rdi+18h]
0x1400c28ef  mov     rcx, [rax+13E8h]
0x1400c28f6  mov     [rbx+40h], rcx
0x1400c28fa  jmp     short loc_1400C290C
0x1400c28fc  mov     rcx, [rdi+18h]
0x1400c2900  mov     [rcx+13E2h], dx
0x1400c2907  cmp     byte ptr [rbp+57h+var_D0], dl
0x1400c290a  jz      short loc_1400C291B
0x1400c290c  lea     rax, StorDumpDevicePowerOn
0x1400c2913  mov     [r13+60h], rbx
0x1400c2917  mov     [r13+58h], rax
0x1400c291b  lea     rax, [rdi+746h]
0x1400c2922  mov     r8d, 44436152h
0x1400c2928  mov     [rbx+10h], rax
0x1400c292c  mov     rax, [rdi+18h]
0x1400c2930  add     rax, 135Dh
0x1400c2936  mov     [rbx+30h], rax
0x1400c293a  lea     rax, [rdi+747h]
0x1400c2941  mov     [rbx+18h], rax
0x1400c2945  mov     ebx, 58h ; 'X'
0x1400c294a  mov     r9, [rdi+8]
0x1400c294e  mov     edx, ebx
0x1400c2950  lea     ecx, [rbx-18h]
0x1400c2953  call    RaidAllocatePool
0x1400c2958  xor     ecx, ecx
0x1400c295a  mov     [rbp+57h+var_80], rax
0x1400c295e  test    rax, rax
0x1400c2961  jnz     short loc_1400C296F
0x1400c2963  mov     edi, ecx
0x1400c2965  mov     ebx, 0C000009Ah
0x1400c296a  jmp     loc_1400C31CB
0x1400c296f  mov     r9, [rdi+8]
0x1400c2973  mov     r8d, 44436152h
0x1400c2979  mov     rdx, rbx
0x1400c297c  mov     ecx, 40h ; '@'
0x1400c2981  call    RaidAllocatePool
0x1400c2986  mov     [rbp+57h+var_C8], rax
0x1400c298a  mov     rbx, rax
0x1400c298d  test    rax, rax
0x1400c2990  jnz     short loc_1400C299F
0x1400c2992  mov     ebx, 0C000009Ah
0x1400c2997  mov     rdi, rax
0x1400c299a  jmp     loc_1400C31CB
0x1400c299f  mov     rcx, [rbp+57h+var_80]
0x1400c29a3  lea     r8, aDiskdumpSys; "diskdump.sys"
0x1400c29aa  add     rcx, 8; pszDest
0x1400c29ae  mov     edx, 1Eh; cbDest
0x1400c29b3  call    RtlStringCbPrintfW
0x1400c29b8  mov     rcx, [rbp+57h+var_80]
0x1400c29bc  lea     r8, aStorportSys_0; "storport.sys"
0x1400c29c3  add     rcx, 26h ; '&'; pszDest
0x1400c29c7  mov     edx, 1Eh; cbDest
0x1400c29cc  call    RtlStringCbPrintfW
0x1400c29d1  mov     rax, [rbp+57h+var_80]
0x1400c29d5  xor     r11d, r11d
0x1400c29d8  mov     rcx, [rbp+57h+P]
0x1400c29dc  mov     [rax], rbx
0x1400c29df  mov     [rbx], r11
0x1400c29e2  mov     [r13+28h], rax
0x1400c29e6  lea     rax, [rdi+747h]
0x1400c29ed  mov     [r13+50h], rax
0x1400c29f1  mov     dword ptr [r13+0], 4
0x1400c29f9  mov     dword ptr [r13+4], 68h ; 'h'
0x1400c2a01  mov     [r13+8], rcx
0x1400c2a05  mov     [r13+10h], r11
0x1400c2a09  mov     [r13+1Ch], r12b
0x1400c2a0d  mov     [r13+20h], r11
0x1400c2a11  mov     al, [r14+200h]
0x1400c2a18  sub     al, 2
0x1400c2a1a  cmp     al, 2
0x1400c2a1c  ja      short loc_1400C2A22
0x1400c2a1e  or      [r13+30h], r12d
0x1400c2a22  mov     rax, [r14+250h]
0x1400c2a29  mov     ecx, [rax+0B8h]
0x1400c2a2f  test    cl, 20h
0x1400c2a32  jz      short loc_1400C2A39
0x1400c2a34  or      dword ptr [r13+30h], 4
0x1400c2a39  cmp     [r14+1152h], r11b
0x1400c2a40  jz      short loc_1400C2A58
0x1400c2a42  mov     rax, [r14+250h]
0x1400c2a49  mov     ecx, [rax+0B8h]
0x1400c2a4f  test    cl, 8
0x1400c2a52  jz      loc_1400C2DE8
0x1400c2a58  mov     r9, [rdi+8]
0x1400c2a5c  mov     edx, 70h ; 'p'
0x1400c2a61  mov     r8d, 44436152h
0x1400c2a67  lea     ecx, [rdx-30h]
0x1400c2a6a  call    RaidAllocatePool
0x1400c2a6f  mov     [rbp+57h+var_88], rax
0x1400c2a73  mov     rbx, rax
0x1400c2a76  test    rax, rax
0x1400c2a79  jnz     short loc_1400C2A85
0x1400c2a7b  mov     ebx, 0C000009Ah
0x1400c2a80  jmp     loc_1400C31C7
0x1400c2a85  mov     r8b, [r14+1D2h]
0x1400c2a8c  xor     r9d, r9d
0x1400c2a8f  mov     rcx, [rdi+8]
0x1400c2a93  lea     edx, [r9+26h]
0x1400c2a97  call    RaidAllocateSrb
0x1400c2a9c  mov     r15, rax
0x1400c2a9f  test    rax, rax
0x1400c2aa2  jz      short loc_1400C2A7B
0x1400c2aa4  cmp     dword ptr [r14], 4E564144h
0x1400c2aab  lea     rcx, [r14+144h]
0x1400c2ab2  jz      short loc_1400C2ABB
0x1400c2ab4  lea     rcx, [r14+1FCh]
0x1400c2abb  mov     ecx, [rcx]
0x1400c2abd  mov     r8, r14
0x1400c2ac0  add     ecx, 7
0x1400c2ac3  and     ecx, 0FFFFFFF8h
0x1400c2ac6  add     ecx, 4B0h
0x1400c2acc  call    StorAllocateContiguousIoResources
0x1400c2ad1  mov     [rbp+57h+var_B0], rax
0x1400c2ad5  test    rax, rax
0x1400c2ad8  jz      short loc_1400C2A7B
0x1400c2ada  add     rax, 30h ; '0'
0x1400c2ade  xor     r9d, r9d
0x1400c2ae1  mov     rcx, rax
0x1400c2ae4  mov     [rbp+57h+var_B8], rax
0x1400c2ae8  xor     r8d, r8d
0x1400c2aeb  call    RaidZeroXrb
0x1400c2af0  mov     r11, [rbp+57h+var_B8]
0x1400c2af4  or      byte ptr [r11+11h], 8
0x1400c2af9  mov     [r11+0B0h], rsi
0x1400c2b00  mov     [r11+0B8h], rbx
0x1400c2b07  mov     [r11+0A8h], r15
0x1400c2b0e  cmp     [r14+1D2h], r12b
0x1400c2b15  jnz     short loc_1400C2B78
0x1400c2b17  mov     [r15+40h], rbx
0x1400c2b1b  xor     ebx, ebx
0x1400c2b1d  mov     [r15+60h], r11
0x1400c2b21  mov     [r15+50h], rsi
0x1400c2b25  mov     dword ptr [r15+14h], 26h ; '&'
0x1400c2b2d  mov     dword ptr [r15+3Ch], 70h ; 'p'
0x1400c2b35  mov     dword ptr [r15+18h], 100h
0x1400c2b3d  mov     [rbp+57h+var_A8], r15
0x1400c2b41  cmp     [r14+1152h], bl
0x1400c2b48  jnz     short loc_1400C2B52
0x1400c2b4a  mov     dword ptr [r15+18h], 40h ; '@'
0x1400c2b52  mov     ecx, [r15+34h]
0x1400c2b56  mov     dword ptr [r15+28h], 0Ah
0x1400c2b5e  mov     al, [rdi+68h]
0x1400c2b61  mov     [rcx+r15+8], al
0x1400c2b66  mov     al, [rdi+69h]
0x1400c2b69  mov     [rcx+r15+9], al
0x1400c2b6e  mov     al, [rdi+6Ah]
0x1400c2b71  mov     [rcx+r15+0Ah], al
0x1400c2b76  jmp     short loc_1400C2BCB
0x1400c2b78  mov     [r15+18h], rbx
0x1400c2b7c  xor     ebx, ebx
0x1400c2b7e  mov     [r15+30h], r11
  ... truncated ...
```
