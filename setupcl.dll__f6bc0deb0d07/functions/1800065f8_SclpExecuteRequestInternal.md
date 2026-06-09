# SclpExecuteRequestInternal

- ea: `0x1800065f8`
- end: `0x180006f1d`
- name: `SclpExecuteRequestInternal`
- size: `2341`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _OWORD *, union _LARGE_INTEGER, char)`
- caller_count: `3`
- callee_count: `26`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, installer_update`

## callers

- `0x180005a90`
- `0x180005da0`
- `0x1800061b0`

## callees

- `0x180001010`
- `0x180001970`
- `0x180001f70`
- `0x180003408`
- `0x18000438c`
- `0x180005144`
- `0x180006024`
- `0x180006484`
- `0x1800065f8`
- `0x180007cac`
- `0x180007d0c`
- `0x180009438`
- `0x180009668`
- `0x18000a4a0`
- `0x18000a524`
- `0x18000a69c`
- `0x18000b90c`
- `0x18000de94`
- `0x18000eb38`
- `0x18000f6e4`
- `0x1800108d0`
- `0x1800111bc`
- `0x1800117e4`
- `0x18001188c`
- `0x1800179c5`
- `0x1800179e0`

## import_xrefs

- `ntdll!NtClose` at `0x180006896`
- `ntdll!NtClose` at `0x180006896`
- `ntdll!RtlFreeHeap` at `0x180006887`
- `ntdll!RtlFreeHeap` at `0x180006d63`
- `ntdll!RtlFreeHeap` at `0x180006887`
- `ntdll!RtlFreeHeap` at `0x180006d63`
- `ntdll!NtQuerySystemTime` at `0x1800066cc`
- `ntdll!NtQuerySystemTime` at `0x1800069c3`
- `ntdll!NtQuerySystemTime` at `0x180006a23`
- `ntdll!NtQuerySystemTime` at `0x180006c48`
- `ntdll!NtQuerySystemTime` at `0x180006c93`
- `ntdll!NtQuerySystemTime` at `0x180006da5`
- `ntdll!NtQuerySystemTime` at `0x1800066cc`
- `ntdll!NtQuerySystemTime` at `0x1800069c3`
- `ntdll!NtQuerySystemTime` at `0x180006a23`
- `ntdll!NtQuerySystemTime` at `0x180006c48`
- `ntdll!NtQuerySystemTime` at `0x180006c93`
- `ntdll!NtQuerySystemTime` at `0x180006da5`

## string_xrefs

- `0x180006b10`: `\REGISTRY\MACHINE\SYSTEM\SETUP\SETUPCL\PendingRequest`
- `0x180006741`: `Acquiring needed privileges...`
- `0x180006785`: `(%lx): Failed to acquire needed privileges`
- `0x1800069c9`: `Marking event [&SclEvent_ProcessRegistry_Start]`
- `0x180006a07`: `Marking event [&SclEvent_ProcessRegistry_Stop]`
- `0x180006a57`: `(%lx): Failed to process registry`
- `0x180006abc`: `Upgrade hive updates ares only supported in online mode; cannot proceed...`
- `0x180006b07`: `SkipMigrateRootACL`
- `0x180006b38`: `Error retrieving ACL migration information: [0x%08X]`
- `0x180006b8f`: `Migration of root ACL: %ws`
- `0x180006bde`: `(%lx): Failed to execute upgrade hive updates`
- `0x180006cd9`: `Marking event [&SclEvent_RetargetLinks_Start]`
- `0x180006cfa`: `Marking event [&SclEvent_RetargetLinks_Stop]`
- `0x180006d16`: `(%lx): Failed to retarget links`

## pseudocode

```c
__int64 __fastcall SclpExecuteRequestInternal(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        _OWORD *a4,
        union _LARGE_INTEGER a5,
        char a6)
{
  int v10; // r12d
  int inited; // ebx
  __int64 v12; // r9
  int v13; // r9d
  __int64 v14; // rcx
  int v15; // eax
  __int64 v16; // rcx
  int Dword; // eax
  int v18; // r14d
  __int64 v19; // rdx
  HANDLE v20; // r14
  int OnlineOSVolumeNtPath; // eax
  HANDLE v22; // r12
  int v23; // r9d
  char v25[8]; // [rsp+40h] [rbp-49h] BYREF
  HANDLE Handle; // [rsp+48h] [rbp-41h] BYREF
  PVOID v27; // [rsp+50h] [rbp-39h] BYREF
  PVOID P[2]; // [rsp+58h] [rbp-31h] BYREF
  union _LARGE_INTEGER v29[2]; // [rsp+68h] [rbp-21h] BYREF
  union _LARGE_INTEGER SystemTime[2]; // [rsp+78h] [rbp-11h] BYREF

  v29[0] = a5;
  *(_OWORD *)&SystemTime[0].LowPart = 0;
  if ( (unsigned __int8)SclRequestIsValid(a2, a1) && (unsigned __int8)SclOSIsValid(a2) && a3 )
  {
    v27 = 0;
    v10 = 1;
    SclLogGenericMessage(a3 + 1152, 1, (unsigned int)SclEvent_Generic_Info, 450, (__int64)"SclpExecuteRequestInternal");
    NtQuerySystemTime(SystemTime);
    SystemTime[1].QuadPart = 0;
    SclLogTimingEvent(a3 + 1152, SclEvent_ExecuteRequest_Start, "Marking event [&SclEvent_ExecuteRequest_Start]");
    if ( a2 )
      v10 = *(_DWORD *)a2;
    SclLogGenericMessage(a3 + 1152, 1, (unsigned int)SclEvent_Generic_Info, 465, (__int64)"SclpExecuteRequestInternal");
    SclLogGenericMessage(a3 + 1152, 1, (unsigned int)SclEvent_Generic_Info, 469, (__int64)"SclpExecuteRequestInternal");
    inited = SclAcquireRequiredPrivileges(&v27);
    if ( inited < 0 )
    {
      v13 = 471;
LABEL_10:
      SclLogGenericMessage(
        a3 + 1152,
        3,
        (unsigned int)SclEvent_Generic_Error,
        v13,
        (__int64)"SclpExecuteRequestInternal");
      goto LABEL_65;
    }
    LOBYTE(v12) = a6;
    inited = SclInitRequestContext(a2, a1, a3, v12);
    if ( inited < 0 )
    {
      v13 = 484;
      goto LABEL_10;
    }
    Handle = 0;
    v25[0] = 0;
    if ( (unsigned __int8)SclOSIsValid(a2) )
    {
      inited = SclpStateOpenStatusKey(v14, &Handle);
      if ( inited >= 0 )
        inited = SclRegValueExists(Handle);
      if ( Handle )
        NtClose(Handle);
      if ( inited >= 0 )
      {
        if ( (*(_DWORD *)(a3 + 8) & 0x8000) == 0 && *(int *)(a3 + 8) >= 0 )
        {
          v25[0] = 1;
          inited = SclStateSetStatus(a2, v25);
          if ( inited < 0 )
            goto LABEL_65;
        }
        if ( (*(_DWORD *)(a3 + 8) & 1) != 0 )
        {
          SclLogTimingEvent(
            a3 + 1152,
            SclEvent_ResetDiskSignatures_Start,
            "Marking event [&SclEvent_ResetDiskSignatures_Start]");
          inited = SclResetDiskGuids(a3);
          SclLogTimingEvent(
            a3 + 1152,
            SclEvent_ResetDiskSignatures_Stop,
            "Marking event [&SclEvent_ResetDiskSignatures_Stop]");
          if ( inited < 0 )
          {
            v13 = 529;
            goto LABEL_10;
          }
        }
        if ( (*(_DWORD *)(a3 + 8) & 0x10) != 0 )
        {
          SclLogTimingEvent(
            a3 + 1152,
            SclEvent_ExtendPartition_Start,
            "Marking event [&SclEvent_ExtendPartition_Start]");
          inited = SclGrowPartition(a3);
          SclLogTimingEvent(a3 + 1152, SclEvent_ExtendPartition_Stop, "Marking event [&SclEvent_ExtendPartition_Stop]");
          if ( inited < 0 )
          {
            v13 = 542;
            goto LABEL_10;
          }
        }
        if ( (*(_DWORD *)(a3 + 8) & 0x1F00) != 0 && (*(_BYTE *)(a3 + 8) & 6) != 0 )
        {
          *(_OWORD *)P = 0;
          NtQuerySystemTime((PLARGE_INTEGER)P);
          P[1] = 0;
          SclLogTimingEvent(
            a3 + 1152,
            SclEvent_ProcessRegistry_Start,
            "Marking event [&SclEvent_ProcessRegistry_Start]");
          if ( v10 == 1 )
            v15 = ((__int64 (__fastcall *)(_QWORD, _QWORD))SclRegProcessOnlineRegistry)(
                    a3,
                    (union _LARGE_INTEGER)v29[0].QuadPart);
          else
            v15 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))SclRegProcessOfflineRegistry)(
                    a3,
                    a2,
                    (union _LARGE_INTEGER)v29[0].QuadPart);
          inited = v15;
          SclLogTimingEvent(a3 + 1152, SclEvent_ProcessRegistry_Stop, "Marking event [&SclEvent_ProcessRegistry_Stop]");
          NtQuerySystemTime((PLARGE_INTEGER)&P[1]);
          if ( a3 != -1312 )
            *(_QWORD *)(a3 + 1312) += SclGetTimerTimeInMS(P);
          if ( inited < 0 )
          {
            v13 = 572;
            goto LABEL_10;
          }
        }
        if ( (*(_DWORD *)(a3 + 8) & 0x20) != 0 )
        {
          SclLogGenericMessage(
            a3 + 1152,
            1,
            (unsigned int)SclEvent_Generic_Info,
            582,
            (__int64)"SclpExecuteRequestInternal");
          v16 = a3 + 1152;
          if ( v10 != 1 )
          {
            inited = -1073741808;
            SclLogGenericMessage(
              v16,
              3,
              (unsigned int)SclEvent_Generic_Error,
              589,
              (__int64)"SclpExecuteRequestInternal");
            goto LABEL_65;
          }
          SclLogTimingEvent(v16, SclEvent_ExecuteUpgHives_Start, "Marking event [&SclEvent_ExecuteUpgHives_Start]");
          LODWORD(Handle) = 0;
          Dword = SclRegGetDword(
                    0,
                    L"\\REGISTRY\\MACHINE\\SYSTEM\\SETUP\\SETUPCL\\PendingRequest",
                    L"SkipMigrateRootACL",
                    &Handle);
          inited = Dword;
          if ( Dword < 0 )
          {
            if ( Dword == -1073741772 )
              inited = 0;
            else
              SclLogGenericMessage(
                a3 + 1152,
                3,
                (unsigned int)SclEvent_Generic_Error,
                612,
                (__int64)"SclpExecuteRequestInternal");
          }
          v18 = (int)Handle;
          SclLogGenericMessage(
            a3 + 1152,
            1,
            (unsigned int)SclEvent_Generic_Info,
            615,
            (__int64)"SclpExecuteRequestInternal");
          if ( inited >= 0 )
          {
            LOBYTE(v19) = v18 == 0;
            inited = SclRegProcessUpgradeRegistryOnline(a3, v19);
          }
          SclLogTimingEvent(a3 + 1152, SclEvent_ExecuteUpgHives_Stop, "Marking event [&SclEvent_ExecuteUpgHives_Stop]");
          if ( inited < 0 )
          {
            v13 = 620;
            goto LABEL_10;
          }
        }
        if ( (*(_DWORD *)(a3 + 8) & 0x4000) == 0 )
          goto LABEL_63;
        v20 = 0;
        Handle = 0;
        if ( v10 == 1 )
        {
          OnlineOSVolumeNtPath = SclGetOnlineOSVolumeNtPath(&Handle);
          v20 = Handle;
          inited = OnlineOSVolumeNtPath;
          if ( OnlineOSVolumeNtPath < 0 )
            goto LABEL_60;
          v22 = Handle;
        }
        else
        {
          v22 = *(HANDLE *)(a2 + 16);
        }
        if ( (*(_DWORD *)(a3 + 8) & 4) == 0 )
          goto LABEL_83;
        *(_OWORD *)&v29[0].LowPart = 0;
        NtQuerySystemTime(v29);
        v29[1].QuadPart = 0;
        SclLogTimingEvent(a3 + 1152, SclEvent_ProcessVolumes_Start, "Marking event [&SclEvent_ProcessVolumes_Start]");
        inited = SclFsProcessVolume(a3, v22);
        SclLogTimingEvent(a3 + 1152, SclEvent_ProcessVolumes_Stop, "Marking event [&SclEvent_ProcessVolumes_Stop]");
        NtQuerySystemTime(&v29[1]);
        if ( a3 != -1320 )
          *(_QWORD *)(a3 + 1320) += SclGetTimerTimeInMS(v29);
        if ( inited < 0 )
        {
          v23 = 669;
        }
        else
        {
LABEL_83:
          if ( (*(_DWORD *)(a3 + 8) & 8) == 0
            || (SclLogTimingEvent(
                  a3 + 1152,
                  SclEvent_RetargetLinks_Start,
                  "Marking event [&SclEvent_RetargetLinks_Start]"),
                inited = SclLinkProcessVolume(a3, v22),
                SclLogTimingEvent(
                  a3 + 1152,
                  SclEvent_RetargetLinks_Stop,
                  "Marking event [&SclEvent_RetargetLinks_Stop]"),
                inited >= 0) )
          {
LABEL_60:
            if ( v20 )
              RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v20);
            if ( inited < 0 )
            {
LABEL_65:
              SclLogTimingEvent(
                a3 + 1152,
                SclEvent_ExecuteRequest_Stop,
                "Marking event [&SclEvent_ExecuteRequest_Stop]");
              NtQuerySystemTime(&SystemTime[1]);
              if ( a3 != -1328 )
                *(_QWORD *)(a3 + 1328) += SclGetTimerTimeInMS(SystemTime);
              if ( inited < 0 )
                SclStateRecordResults((unsigned int)inited, a3, a2);
              else
                inited = SclStateRecordResults((unsigned int)inited, a3, a2);
              if ( a4 )
              {
                *a4 = *(_OWORD *)(a3 + 1192);
                a4[1] = *(_OWORD *)(a3 + 1208);
                a4[2] = *(_OWORD *)(a3 + 1224);
                a4[3] = *(_OWORD *)(a3 + 1240);
                a4[4] = *(_OWORD *)(a3 + 1256);
                a4[5] = *(_OWORD *)(a3 + 1272);
                a4[6] = *(_OWORD *)(a3 + 1288);
                a4[7] = *(_OWORD *)(a3 + 1304);
                a4[8] = *(_OWORD *)(a3 + 1320);
              }
              if ( inited < 0 )
              {
                SclReleasePrivileges(v27);
              }
              else
              {
                inited = SclReleasePrivileges(v27);
                if ( inited >= 0 )
                {
LABEL_79:
                  g_WdsNativeLibLog = 0;
                  qword_180023590 = 0;
                  SclFreeRequest((void *)(a3 + 8));
                  memset_0((void *)a3, 0, 0x958u);
                  return (unsigned int)inited;
                }
              }
              SclLogGenericMessage(
                a3 + 1152,
                3,
                (unsigned int)SclEvent_Generic_Error,
                719,
                (__int64)"SclpExecuteRequestInternal");
              goto LABEL_79;
            }
LABEL_63:
            if ( *(_BYTE *)a3 )
            {
              v25[0] = 0;
              inited = SclStateSetStatus(a2, v25);
            }
            goto LABEL_65;
          }
          v23 = 682;
        }
        SclLogGenericMessage(
          a3 + 1152,
          3,
          (unsigned int)SclEvent_Generic_Error,
          v23,
          (__int64)"SclpExecuteRequestInternal");
        goto LABEL_60;
      }
    }
    else
    {
      inited = -1073741811;
    }
    v13 = 491;
    goto LABEL_10;
  }
  return 3221225485LL;
}

```

## disassembly

```asm
0x1800065f8  push    rbp
0x1800065fa  push    rbx
0x1800065fb  push    rsi
0x1800065fc  push    rdi
0x1800065fd  push    r12
0x1800065ff  push    r13
0x180006601  push    r14
0x180006603  push    r15
0x180006605  lea     rbp, [rsp-0Fh]
0x18000660a  sub     rsp, 98h
0x180006611  mov     rax, cs:__security_cookie
0x180006618  xor     rax, rsp
0x18000661b  mov     [rbp+47h+var_48], rax
0x18000661f  mov     rax, [rbp+47h+arg_20]
0x180006623  mov     r15, rdx
0x180006626  mov     rdx, rcx
0x180006629  mov     qword ptr [rbp+47h+var_68], rax
0x18000662d  mov     r14, rcx
0x180006630  xorps   xmm0, xmm0
0x180006633  mov     rcx, r15
0x180006636  mov     r13, r9
0x180006639  mov     rdi, r8
0x18000663c  movups  xmmword ptr [rbp+47h+SystemTime], xmm0
0x180006640  call    SclRequestIsValid
0x180006645  xor     ebx, ebx
0x180006647  test    al, al
0x180006649  jz      loc_180006EF8
0x18000664f  mov     rcx, r15
0x180006652  call    SclOSIsValid
0x180006657  test    al, al
0x180006659  jz      loc_180006EF8
0x18000665f  test    rdi, rdi
0x180006662  jz      loc_180006EF8
0x180006668  lea     rsi, [rdi+480h]
0x18000666f  mov     [rbp+47h+var_80], rbx
0x180006673  cmp     [rsi], rbx
0x180006676  lea     rcx, aNotPresent; "not present"
0x18000667d  lea     rax, aPresent; "present"
0x180006684  mov     r9d, 1C2h
0x18000668a  cmovz   rax, rcx
0x18000668e  lea     r12d, [rbx+1]
0x180006692  mov     [rsp+0D0h+var_98], rax
0x180006697  lea     r8, SclEvent_Generic_Info
0x18000669e  mov     eax, [r14]
0x1800066a1  mov     edx, r12d
0x1800066a4  mov     dword ptr [rsp+0D0h+var_A0], eax
0x1800066a8  mov     rcx, rsi
0x1800066ab  lea     rax, aSawRequestPOpe; "Saw request(P): operation flags = 0x%X,"...
0x1800066b2  mov     [rsp+0D0h+var_A8], rax
0x1800066b7  lea     rax, aSclpexecutereq; "SclpExecuteRequestInternal"
0x1800066be  mov     qword ptr [rsp+0D0h+var_B0], rax
0x1800066c3  call    SclLogGenericMessage
0x1800066c8  lea     rcx, [rbp+47h+SystemTime]; SystemTime
0x1800066cc  call    cs:__imp_NtQuerySystemTime
0x1800066d2  lea     r8, aMarkingEventSc_14; "Marking event [&SclEvent_ExecuteRequest"...
0x1800066d9  mov     qword ptr [rbp+47h+SystemTime+8], rbx
0x1800066dd  lea     rdx, SclEvent_ExecuteRequest_Start
0x1800066e4  mov     rcx, rsi
0x1800066e7  call    SclLogTimingEvent
0x1800066ec  test    r15, r15
0x1800066ef  jz      short loc_1800066F4
0x1800066f1  mov     r12d, [r15]
0x1800066f4  lea     rcx, aOffline; "offline"
0x1800066fb  cmp     r12d, 1
0x1800066ff  lea     rax, aOnline; "online"
0x180006706  mov     r9d, 1D1h
0x18000670c  cmovnz  rax, rcx
0x180006710  lea     rbx, aSclpexecutereq; "SclpExecuteRequestInternal"
0x180006717  mov     [rsp+0D0h+var_A0], rax
0x18000671c  lea     r8, SclEvent_Generic_Info
0x180006723  lea     rax, aRunningInSMode; "Running in [%s] mode."
0x18000672a  mov     edx, 1
0x18000672f  mov     [rsp+0D0h+var_A8], rax
0x180006734  mov     rcx, rsi
0x180006737  mov     qword ptr [rsp+0D0h+var_B0], rbx
0x18000673c  call    SclLogGenericMessage
0x180006741  lea     rax, aAcquiringNeede; "Acquiring needed privileges..."
0x180006748  mov     r9d, 1D5h
0x18000674e  mov     [rsp+0D0h+var_A8], rax
0x180006753  lea     r8, SclEvent_Generic_Info
0x18000675a  mov     edx, 1
0x18000675f  mov     qword ptr [rsp+0D0h+var_B0], rbx; ULONG
0x180006764  mov     rcx, rsi
0x180006767  call    SclLogGenericMessage
0x18000676c  lea     rcx, [rbp+47h+var_80]
0x180006770  call    SclAcquireRequiredPrivileges
0x180006775  mov     ebx, eax
0x180006777  test    eax, eax
0x180006779  jns     short loc_18000678E
0x18000677b  mov     dword ptr [rsp+0D0h+var_A0], eax
0x18000677f  mov     r9d, 1D7h
0x180006785  lea     rax, aLxFailedToAcqu; "(%lx): Failed to acquire needed privile"...
0x18000678c  jmp     short loc_1800067B7
0x18000678e  mov     r9b, [rbp+47h+arg_28]
0x180006792  mov     r8, rdi
0x180006795  mov     rdx, r14
0x180006798  mov     rcx, r15
0x18000679b  call    SclInitRequestContext
0x1800067a0  mov     ebx, eax
0x1800067a2  test    eax, eax
0x1800067a4  jns     short loc_1800067E1
0x1800067a6  mov     dword ptr [rsp+0D0h+var_A0], eax
0x1800067aa  mov     r9d, 1E4h
0x1800067b0  lea     rax, aLxFailedToInit; "(%lx): Failed to initialize SetupCl con"...
0x1800067b7  mov     [rsp+0D0h+var_A8], rax
0x1800067bc  lea     r14, aSclpexecutereq; "SclpExecuteRequestInternal"
0x1800067c3  lea     r8, SclEvent_Generic_Error
0x1800067ca  mov     qword ptr [rsp+0D0h+var_B0], r14
0x1800067cf  mov     edx, 3
0x1800067d4  mov     rcx, rsi
0x1800067d7  call    SclLogGenericMessage
0x1800067dc  jmp     loc_180006D8B
0x1800067e1  mov     rcx, r15
0x1800067e4  mov     [rbp+47h+Handle], 0
0x1800067ec  mov     [rbp+47h+var_90], 0
0x1800067f0  call    SclOSIsValid
0x1800067f5  test    al, al
0x1800067f7  jz      loc_180006DE6
0x1800067fd  lea     rdx, [rbp+47h+Handle]
0x180006801  xor     r14d, r14d
0x180006804  call    SclpStateOpenStatusKey
0x180006809  mov     ebx, eax
0x18000680b  test    eax, eax
0x18000680d  js      short loc_18000688D
0x18000680f  mov     rcx, [rbp+47h+Handle]; KeyHandle
0x180006813  lea     r8, [rbp+47h+var_90]
0x180006817  lea     rdx, aBlockoperation; "BlockOperations"
0x18000681e  call    SclRegValueExists
0x180006823  mov     ebx, eax
0x180006825  test    eax, eax
0x180006827  js      short loc_18000688D
0x180006829  cmp     [rbp+47h+var_90], r14b
0x18000682d  jz      short loc_18000688D
0x18000682f  mov     rcx, [rbp+47h+Handle]; KeyHandle
0x180006833  lea     r9, [rbp+47h+P]
0x180006837  xor     r8d, r8d
0x18000683a  mov     [rbp+47h+P], r14
0x18000683e  lea     rdx, aBlockoperation; "BlockOperations"
0x180006845  call    SclRegGetValue
0x18000684a  mov     ebx, eax
0x18000684c  test    eax, eax
0x18000684e  js      short loc_18000688D
0x180006850  mov     r8, [rbp+47h+P]; P
0x180006854  cmp     dword ptr [r8+4], 4
0x180006859  jz      short loc_180006862
0x18000685b  mov     ebx, 0C0000024h
0x180006860  jmp     short loc_180006878
0x180006862  cmp     dword ptr [r8+8], 4
0x180006867  jz      short loc_180006870
0x180006869  mov     ebx, 0C0000004h
0x18000686e  jmp     short loc_180006878
0x180006870  cmp     [r8+0Ch], r14d
0x180006874  setnz   r14b
0x180006878  mov     rcx, gs:60h
0x180006881  xor     edx, edx; Flags
0x180006883  mov     rcx, [rcx+30h]; HeapHandle
0x180006887  call    cs:__imp_RtlFreeHeap
0x18000688d  mov     rcx, [rbp+47h+Handle]; Handle
0x180006891  test    rcx, rcx
0x180006894  jz      short loc_18000689C
0x180006896  call    cs:__imp_NtClose
0x18000689c  test    ebx, ebx
0x18000689e  js      loc_180006DEB
0x1800068a4  test    r14b, r14b
0x1800068a7  jz      short loc_1800068CA
0x1800068a9  mov     ebx, 0C0000229h
0x1800068ae  lea     rax, aTargetOsIsInAF; "Target OS is in a failed state from a p"...
0x1800068b5  lea     r14, aSclpexecutereq; "SclpExecuteRequestInternal"
0x1800068bc  mov     r9d, 1F5h
0x1800068c2  mov     rcx, rsi
0x1800068c5  jmp     loc_180006AC9
0x1800068ca  test    dword ptr [rdi+8], 8000h
0x1800068d1  jnz     short loc_1800068F3
0x1800068d3  cmp     dword ptr [rdi+8], 0
0x1800068d7  jl      short loc_1800068F3
0x1800068d9  lea     rdx, [rbp+47h+var_90]
0x1800068dd  mov     [rbp+47h+var_90], 1
0x1800068e1  mov     rcx, r15
0x1800068e4  call    SclStateSetStatus
0x1800068e9  mov     ebx, eax
0x1800068eb  test    eax, eax
0x1800068ed  js      loc_180006D84
0x1800068f3  mov     eax, [rdi+8]
0x1800068f6  test    al, 1
0x1800068f8  jz      short loc_18000694A
0x1800068fa  lea     r8, aMarkingEventSc_16; "Marking event [&SclEvent_ResetDiskSigna"...
0x180006901  mov     rcx, rsi
0x180006904  lea     rdx, SclEvent_ResetDiskSignatures_Start
0x18000690b  call    SclLogTimingEvent
0x180006910  mov     rcx, rdi
0x180006913  call    SclResetDiskGuids
0x180006918  lea     r8, aMarkingEventSc_4; "Marking event [&SclEvent_ResetDiskSigna"...
0x18000691f  mov     rcx, rsi
0x180006922  lea     rdx, SclEvent_ResetDiskSignatures_Stop
0x180006929  mov     ebx, eax
0x18000692b  call    SclLogTimingEvent
0x180006930  test    ebx, ebx
0x180006932  jns     short loc_18000694A
0x180006934  mov     dword ptr [rsp+0D0h+var_A0], ebx
0x180006938  lea     rax, aLxFailedToRese; "(%lx): Failed to reset disk GUIDs."
0x18000693f  mov     r9d, 211h
0x180006945  jmp     loc_1800067B7
0x18000694a  mov     eax, [rdi+8]
0x18000694d  test    al, 10h
0x18000694f  jz      short loc_1800069A1
0x180006951  lea     r8, aMarkingEventSc; "Marking event [&SclEvent_ExtendPartitio"...
0x180006958  mov     rcx, rsi
0x18000695b  lea     rdx, SclEvent_ExtendPartition_Start
0x180006962  call    SclLogTimingEvent
0x180006967  mov     rcx, rdi
0x18000696a  call    SclGrowPartition
0x18000696f  lea     r8, aMarkingEventSc_13; "Marking event [&SclEvent_ExtendPartitio"...
0x180006976  mov     rcx, rsi
0x180006979  lea     rdx, SclEvent_ExtendPartition_Stop
0x180006980  mov     ebx, eax
0x180006982  call    SclLogTimingEvent
0x180006987  test    ebx, ebx
0x180006989  jns     short loc_1800069A1
0x18000698b  mov     dword ptr [rsp+0D0h+var_A0], ebx
0x18000698f  lea     rax, aLxFailedToExte; "(%lx): Failed to extend partition."
0x180006996  mov     r9d, 21Eh
0x18000699c  jmp     loc_1800067B7
0x1800069a1  test    dword ptr [rdi+8], 1F00h
0x1800069a8  jz      loc_180006A71
0x1800069ae  test    byte ptr [rdi+8], 6
0x1800069b2  jz      loc_180006A69
0x1800069b8  xorps   xmm0, xmm0
0x1800069bb  lea     rcx, [rbp+47h+P]; SystemTime
0x1800069bf  movups  xmmword ptr [rbp+47h+P], xmm0
0x1800069c3  call    cs:__imp_NtQuerySystemTime
0x1800069c9  lea     r8, aMarkingEventSc_7; "Marking event [&SclEvent_ProcessRegistr"...
0x1800069d0  mov     [rbp+47h+P+8], 0
0x1800069d8  lea     rdx, SclEvent_ProcessRegistry_Start
0x1800069df  mov     rcx, rsi
0x1800069e2  call    SclLogTimingEvent
0x1800069e7  mov     rcx, rdi
0x1800069ea  cmp     r12d, 1
0x1800069ee  jnz     short loc_1800069FB
0x1800069f0  mov     rdx, qword ptr [rbp+47h+var_68]
0x1800069f4  call    SclRegProcessOnlineRegistry
0x1800069f9  jmp     short loc_180006A07
0x1800069fb  mov     r8, qword ptr [rbp+47h+var_68]
0x1800069ff  mov     rdx, r15
0x180006a02  call    SclRegProcessOfflineRegistry
0x180006a07  lea     r8, aMarkingEventSc_8; "Marking event [&SclEvent_ProcessRegistr"...
0x180006a0e  mov     rcx, rsi
0x180006a11  lea     rdx, SclEvent_ProcessRegistry_Stop
0x180006a18  mov     ebx, eax
0x180006a1a  call    SclLogTimingEvent
0x180006a1f  lea     rcx, [rbp+47h+P+8]; SystemTime
0x180006a23  call    cs:__imp_NtQuerySystemTime
0x180006a29  lea     rax, [rdi+520h]
0x180006a30  test    rax, rax
0x180006a33  jz      short loc_180006A4F
0x180006a35  lea     rcx, [rbp+47h+P]
0x180006a39  call    SclGetTimerTimeInMS
0x180006a3e  mov     rcx, [rdi+520h]
0x180006a45  add     rax, rcx
0x180006a48  mov     [rdi+520h], rax
0x180006a4f  test    ebx, ebx
0x180006a51  jns     short loc_180006A71
0x180006a53  mov     dword ptr [rsp+0D0h+var_A0], ebx
0x180006a57  lea     rax, aLxFailedToProc_7; "(%lx): Failed to process registry"
0x180006a5e  mov     r9d, 23Ch
0x180006a64  jmp     loc_1800067B7
0x180006a69  test    ebx, ebx
0x180006a6b  js      loc_180006D84
0x180006a71  mov     eax, [rdi+8]
0x180006a74  test    al, 20h
0x180006a76  jz      loc_180006BF0
0x180006a7c  lea     rax, aReExecutingUpg; "Re-Executing upgrade migration actions."...
0x180006a83  mov     r9d, 246h
0x180006a89  mov     [rsp+0D0h+var_A8], rax
0x180006a8e  lea     r14, aSclpexecutereq; "SclpExecuteRequestInternal"
0x180006a95  lea     r8, SclEvent_Generic_Info
0x180006a9c  mov     qword ptr [rsp+0D0h+var_B0], r14
0x180006aa1  mov     edx, 1
0x180006aa6  mov     rcx, rsi
0x180006aa9  call    SclLogGenericMessage
0x180006aae  mov     rcx, rsi
0x180006ab1  cmp     r12d, 1
0x180006ab5  jz      short loc_180006AE9
0x180006ab7  mov     ebx, 0C0000010h
0x180006abc  lea     rax, aUpgradeHiveUpd; "Upgrade hive updates ares only supporte"...
0x180006ac3  mov     r9d, 24Dh
0x180006ac9  mov     [rsp+0D0h+var_A8], rax
0x180006ace  lea     r8, SclEvent_Generic_Error
0x180006ad5  mov     edx, 3
0x180006ada  mov     qword ptr [rsp+0D0h+var_B0], r14
0x180006adf  call    SclLogGenericMessage
0x180006ae4  jmp     loc_180006D8B
0x180006ae9  lea     r8, aMarkingEventSc_12; "Marking event [&SclEvent_ExecuteUpgHive"...
0x180006af0  lea     rdx, SclEvent_ExecuteUpgHives_Start
0x180006af7  call    SclLogTimingEvent
0x180006afc  lea     r9, [rbp+47h+Handle]
0x180006b00  mov     dword ptr [rbp+47h+Handle], 0
0x180006b07  lea     r8, aSkipmigrateroo; "SkipMigrateRootACL"
0x180006b0e  xor     ecx, ecx
0x180006b10  lea     rdx, aRegistryMachin_8; "\\REGISTRY\\MACHINE\\SYSTEM\\SETUP\\SET"...
0x180006b17  call    SclRegGetDword
  ... truncated ...
```
