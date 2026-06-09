# CUVHDProfileTelemetryLogging::LogSessionUsage(_RD_TELEMETRY_SESSION_EVENT_CODE,ulong)

- ea: `0x180004620`
- end: `0x180004a49`
- name: `?LogSessionUsage@CUVHDProfileTelemetryLogging@@SAXW4_RD_TELEMETRY_SESSION_EVENT_CODE@@K@Z`
- size: `1065`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180002da0`
- `0x180031ee0`
- `0x180032370`

## callees

- `0x180002bb0`
- `0x180003040`
- `0x180003f30`
- `0x180004620`
- `0x180017564`
- `0x18001a280`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004704`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004704`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180004a06`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180004a06`
- `WTSAPI32!WTSFreeMemory` at `0x180004a2e`
- `WTSAPI32!WTSFreeMemory` at `0x180004a2e`
- `WTSAPI32!WTSEnumerateSessionsW` at `0x1800046fa`
- `WTSAPI32!WTSEnumerateSessionsW` at `0x1800046fa`

## pseudocode

```c
void __fastcall CUVHDProfileTelemetryLogging::LogSessionUsage(int a1, int a2)
{
  int RoleStatus; // eax
  int LicensingMode; // eax
  signed int LastError; // eax
  bool v7; // sf
  int v8; // r8d
  int v9; // r9d
  DWORD v10; // edx
  DWORD SessionId; // r10d
  WTS_CONNECTSTATE_CLASS State; // ecx
  __int32 v13; // ecx
  __int32 v14; // ecx
  WTS_CONNECTSTATE_CLASS v15; // ecx
  __int32 v16; // ecx
  __int32 v17; // ecx
  unsigned __int32 v18; // ecx
  unsigned __int32 v19; // eax
  __int64 v20; // rcx
  __int64 v21; // rax
  bool v22; // zf
  unsigned int v23; // [rsp+38h] [rbp-D0h] BYREF
  unsigned int v24; // [rsp+3Ch] [rbp-CCh] BYREF
  DWORD pCount[2]; // [rsp+40h] [rbp-C8h] BYREF
  PWTS_SESSION_INFOW ppSessionInfo; // [rsp+48h] [rbp-C0h] BYREF
  int v27; // [rsp+50h] [rbp-B8h] BYREF
  int v28; // [rsp+54h] [rbp-B4h] BYREF
  int v29; // [rsp+58h] [rbp-B0h] BYREF
  _DWORD v30[2]; // [rsp+5Ch] [rbp-ACh] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+68h] [rbp-A0h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+78h] [rbp-90h] BYREF
  char *v33; // [rsp+88h] [rbp-80h]
  int v34; // [rsp+90h] [rbp-78h]
  int v35; // [rsp+94h] [rbp-74h]
  BYTE *v36; // [rsp+98h] [rbp-70h]
  int v37; // [rsp+A0h] [rbp-68h]
  int v38; // [rsp+A4h] [rbp-64h]
  BYTE *v39; // [rsp+A8h] [rbp-60h]
  int v40; // [rsp+B0h] [rbp-58h]
  int v41; // [rsp+B4h] [rbp-54h]
  _DWORD *v42; // [rsp+B8h] [rbp-50h]
  __int64 v43; // [rsp+C0h] [rbp-48h]
  DWORD *v44; // [rsp+C8h] [rbp-40h]
  __int64 v45; // [rsp+D0h] [rbp-38h]
  unsigned int *v46; // [rsp+D8h] [rbp-30h]
  __int64 v47; // [rsp+E0h] [rbp-28h]
  int *v48; // [rsp+E8h] [rbp-20h]
  __int64 v49; // [rsp+F0h] [rbp-18h]
  int *v50; // [rsp+F8h] [rbp-10h]
  __int64 v51; // [rsp+100h] [rbp-8h]
  int *v52; // [rsp+108h] [rbp+0h]
  __int64 v53; // [rsp+110h] [rbp+8h]
  unsigned int *v54; // [rsp+118h] [rbp+10h]
  __int64 v55; // [rsp+120h] [rbp+18h]

  pCount[0] = 0;
  v23 = 0;
  ppSessionInfo = 0;
  v24 = 0;
  pCount[1] = 0;
  CUVHDProfileTelemetryLogging::InitOnceCallbackFn(0, 0, 0);
  RoleStatus = CUVHDProfileTelemetryLogging::GetRoleStatus(pCount, &v23);
  if ( RoleStatus >= 0 )
  {
    if ( v23 == 1 )
    {
      LicensingMode = CUVHDProfileTelemetryLogging::GetLicensingMode(&v24);
      if ( LicensingMode >= 0 )
      {
        if ( WTSEnumerateSessionsW(0, 0, 1u, &ppSessionInfo, &pCount[1]) )
          goto LABEL_11;
        LastError = GetLastError();
        v7 = LastError < 0;
        if ( LastError > 0 )
        {
          LastError = (unsigned __int16)LastError | 0x80070000;
          v7 = LastError < 0;
        }
        if ( !v7 )
        {
LABEL_11:
          v8 = 0;
          v9 = 0;
          v10 = 0;
          if ( a1 == 1 )
          {
            if ( pCount[1] )
            {
              do
              {
                SessionId = ppSessionInfo[v10].SessionId;
                if ( SessionId - 1 <= 0xFFFE && a2 != SessionId )
                {
                  State = ppSessionInfo[v10].State;
                  if ( State && (v13 = State - 1) != 0 && (v14 = v13 - 2) != 0 )
                  {
                    if ( v14 == 1 )
                      ++v9;
                  }
                  else
                  {
                    ++v8;
                  }
                }
                ++v10;
              }
              while ( v10 < pCount[1] );
            }
          }
          else if ( pCount[1] )
          {
            do
            {
              if ( ppSessionInfo[v10].SessionId - 1 <= 0xFFFE )
              {
                v15 = ppSessionInfo[v10].State;
                if ( v15 && (v16 = v15 - 1) != 0 && (v17 = v16 - 2) != 0 )
                {
                  if ( v17 == 1 )
                    ++v9;
                }
                else
                {
                  ++v8;
                }
              }
              ++v10;
            }
            while ( v10 < pCount[1] );
          }
          v18 = v9 + v8;
          v19 = _InterlockedExchangeAdd(&CUVHDProfileTelemetryLogging::m_dwMaxSessions, 0);
          if ( v19 < v9 + v8 )
          {
            do
            {
              _InterlockedCompareExchange(&CUVHDProfileTelemetryLogging::m_dwMaxSessions, v18, v19);
              v19 = _InterlockedExchangeAdd(&CUVHDProfileTelemetryLogging::m_dwMaxSessions, 0);
            }
            while ( v19 < v18 );
          }
          if ( (unsigned int)dword_1800842C0 > 5
            && (qword_1800842D0 & 0x400000000000LL) != 0
            && (qword_1800842D8 & 0x400000000000LL) == qword_1800842D8 )
          {
            v54 = &v23;
            v52 = &v27;
            v50 = &v28;
            v48 = &v29;
            v46 = &v24;
            v44 = pCount;
            v29 = v9 + v8;
            v20 = -1;
            v42 = v30;
            v21 = -1;
            v23 = CUVHDProfileTelemetryLogging::m_dwMaxSessions;
            v27 = v9;
            v28 = v8;
            v30[0] = a1;
            v55 = 4;
            v53 = 4;
            v51 = 4;
            v49 = 4;
            v47 = 4;
            v45 = 4;
            v43 = 4;
            do
              v22 = *((_WORD *)&CUVHDProfileTelemetryLogging::m_FarmId + ++v21) == 0;
            while ( !v22 );
            v39 = &CUVHDProfileTelemetryLogging::m_FarmId;
            v40 = 2 * v21 + 2;
            v41 = 0;
            do
              v22 = *((_WORD *)&CUVHDProfileTelemetryLogging::m_DeploymentId + ++v20) == 0;
            while ( !v22 );
            v36 = &CUVHDProfileTelemetryLogging::m_DeploymentId;
            v38 = 0;
            v37 = 2 * v20 + 2;
            *(_DWORD *)&EventDescriptor.Level = 5;
            UserData.Ptr = (ULONGLONG)off_1800842C8;
            *(_DWORD *)&EventDescriptor.Id = 184549376;
            EventDescriptor.Keyword = 0x400000000000LL;
            UserData.Size = *(unsigned __int16 *)off_1800842C8;
            v33 = byte_18007A6D9;
            UserData.Reserved = 2;
            v34 = 180;
            v35 = 1;
            v30[1] = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
            EventWriteTransfer(qword_1800842E0, &EventDescriptor, 0, 0, 0xBu, &UserData);
          }
        }
        else
        {
          _DbgPrintMessage(
            8,
            "WTSEnumarateSessions failed: 0x%x in %s",
            LastError,
            "CUVHDProfileTelemetryLogging::LogSessionUsage");
        }
      }
      else
      {
        _DbgPrintMessage(
          8,
          "GetLicensingMode failed: 0x%x in %s",
          LicensingMode,
          "CUVHDProfileTelemetryLogging::LogSessionUsage");
      }
    }
  }
  else
  {
    _DbgPrintMessage(8, "GetRoleStatus failed: 0x%x in %s", RoleStatus, "CUVHDProfileTelemetryLogging::LogSessionUsage");
  }
  if ( ppSessionInfo )
    WTSFreeMemory(ppSessionInfo);
}

```

## disassembly

```asm
0x180004620  mov     r11, rsp
0x180004623  push    rbp
0x180004624  lea     rbp, [r11-38h]
0x180004628  sub     rsp, 130h
0x18000462f  mov     rax, cs:__security_cookie
0x180004636  xor     rax, rsp
0x180004639  mov     [rbp+30h+var_10], rax
0x18000463d  mov     [r11+10h], rsi
0x180004641  xor     r8d, r8d; Context
0x180004644  mov     [r11+18h], rdi
0x180004648  mov     esi, ecx
0x18000464a  mov     [r11+20h], r14
0x18000464e  mov     edi, edx
0x180004650  xor     r14d, r14d
0x180004653  xor     edx, edx; Parameter
0x180004655  xor     ecx, ecx; InitOnce
0x180004657  mov     [rsp+130h+var_F8], r14d
0x18000465c  mov     [rsp+130h+var_100], r14d
0x180004661  mov     [rsp+130h+ppSessionInfo], r14
0x180004666  mov     [rsp+130h+var_FC], r14d
0x18000466b  mov     [rsp+130h+var_F8+4], r14d
0x180004670  call    ?InitOnceCallbackFn@CUVHDProfileTelemetryLogging@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; CUVHDProfileTelemetryLogging::InitOnceCallbackFn(_RTL_RUN_ONCE *,void *,void * *)
0x180004675  lea     rdx, [rsp+130h+var_100]; unsigned int *
0x18000467a  lea     rcx, [rsp+130h+var_F8]; unsigned int *
0x18000467f  call    ?GetRoleStatus@CUVHDProfileTelemetryLogging@@CAJPEAK0@Z; CUVHDProfileTelemetryLogging::GetRoleStatus(ulong *,ulong *)
0x180004684  test    eax, eax
0x180004686  jns     short loc_1800046A8
0x180004688  lea     r9, aCuvhdprofilete_3; "CUVHDProfileTelemetryLogging::LogSessio"...
0x18000468f  mov     r8d, eax
0x180004692  lea     rdx, aGetrolestatusF; "GetRoleStatus failed: 0x%x in %s"
0x180004699  mov     ecx, 8; int
0x18000469e  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800046a3  jmp     loc_180004A0C
0x1800046a8  cmp     [rsp+130h+var_100], 1
0x1800046ad  jnz     loc_180004A0C
0x1800046b3  lea     rcx, [rsp+130h+var_FC]; unsigned int *
0x1800046b8  call    ?GetLicensingMode@CUVHDProfileTelemetryLogging@@CAJPEAK@Z; CUVHDProfileTelemetryLogging::GetLicensingMode(ulong *)
0x1800046bd  test    eax, eax
0x1800046bf  jns     short loc_1800046E1
0x1800046c1  lea     r9, aCuvhdprofilete_3; "CUVHDProfileTelemetryLogging::LogSessio"...
0x1800046c8  mov     r8d, eax
0x1800046cb  lea     rdx, aGetlicensingmo; "GetLicensingMode failed: 0x%x in %s"
0x1800046d2  mov     ecx, 8; int
0x1800046d7  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800046dc  jmp     loc_180004A0C
0x1800046e1  lea     rax, [rsp+130h+var_F8+4]
0x1800046e6  xor     edx, edx; Reserved
0x1800046e8  lea     r9, [rsp+130h+ppSessionInfo]; ppSessionInfo
0x1800046ed  mov     [rsp+130h+pCount], rax; pCount
0x1800046f2  xor     ecx, ecx; hServer
0x1800046f4  mov     r8d, 1; Version
0x1800046fa  call    cs:__imp_WTSEnumerateSessionsW
0x180004700  test    eax, eax
0x180004702  jnz     short loc_18000473A
0x180004704  call    cs:__imp_GetLastError
0x18000470a  test    eax, eax
0x18000470c  jle     short loc_180004718
0x18000470e  movzx   eax, ax
0x180004711  or      eax, 80070000h
0x180004716  test    eax, eax
0x180004718  jns     short loc_18000473A
0x18000471a  lea     r9, aCuvhdprofilete_3; "CUVHDProfileTelemetryLogging::LogSessio"...
0x180004721  mov     r8d, eax
0x180004724  lea     rdx, aWtsenumaratese; "WTSEnumarateSessions failed: 0x%x in %s"
0x18000472b  mov     ecx, 8; int
0x180004730  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180004735  jmp     loc_180004A0C
0x18000473a  mov     r8d, r14d
0x18000473d  mov     r9d, r14d
0x180004740  mov     edx, r14d
0x180004743  cmp     esi, 1
0x180004746  jnz     short loc_1800047BA
0x180004748  mov     r11d, [rsp+130h+var_F8+4]
0x18000474d  test    r11d, r11d
0x180004750  jz      loc_18000480A
0x180004756  mov     [rsp+130h+arg_0], rbx
0x18000475e  mov     rbx, [rsp+130h+ppSessionInfo]
0x180004763  nop     dword ptr [rax+00h]
0x180004767  nop     word ptr [rax+rax+00000000h]
0x180004770  mov     eax, edx
0x180004772  lea     rcx, [rax+rax*2]
0x180004776  mov     r10d, [rbx+rcx*8]
0x18000477a  lea     eax, [r10-1]
0x18000477e  cmp     eax, 0FFFEh
0x180004783  ja      short loc_1800047A9
0x180004785  cmp     edi, r10d
0x180004788  jz      short loc_1800047A9
0x18000478a  mov     ecx, [rbx+rcx*8+10h]
0x18000478e  test    ecx, ecx
0x180004790  jz      short loc_1800047A6
0x180004792  sub     ecx, 1
0x180004795  jz      short loc_1800047A6
0x180004797  sub     ecx, 2
0x18000479a  jz      short loc_1800047A6
0x18000479c  cmp     ecx, 1
0x18000479f  jnz     short loc_1800047A9
0x1800047a1  inc     r9d
0x1800047a4  jmp     short loc_1800047A9
0x1800047a6  inc     r8d
0x1800047a9  inc     edx
0x1800047ab  cmp     edx, r11d
0x1800047ae  jb      short loc_180004770
0x1800047b0  mov     rbx, [rsp+130h+arg_0]
0x1800047b8  jmp     short loc_18000480A
0x1800047ba  mov     r10d, [rsp+130h+var_F8+4]
0x1800047bf  test    r10d, r10d
0x1800047c2  jz      short loc_18000480A
0x1800047c4  mov     r11, [rsp+130h+ppSessionInfo]
0x1800047c9  nop     dword ptr [rax+00000000h]
0x1800047d0  mov     eax, edx
0x1800047d2  lea     rcx, [rax+rax*2]
0x1800047d6  mov     eax, [r11+rcx*8]
0x1800047da  dec     eax
0x1800047dc  cmp     eax, 0FFFEh
0x1800047e1  ja      short loc_180004803
0x1800047e3  mov     ecx, [r11+rcx*8+10h]
0x1800047e8  test    ecx, ecx
0x1800047ea  jz      short loc_180004800
0x1800047ec  sub     ecx, 1
0x1800047ef  jz      short loc_180004800
0x1800047f1  sub     ecx, 2
0x1800047f4  jz      short loc_180004800
0x1800047f6  cmp     ecx, 1
0x1800047f9  jnz     short loc_180004803
0x1800047fb  inc     r9d
0x1800047fe  jmp     short loc_180004803
0x180004800  inc     r8d
0x180004803  inc     edx
0x180004805  cmp     edx, r10d
0x180004808  jb      short loc_1800047D0
0x18000480a  lea     ecx, [r9+r8]
0x18000480e  mov     eax, r14d
0x180004811  lock xadd cs:?m_dwMaxSessions@CUVHDProfileTelemetryLogging@@0JC, eax; long volatile CUVHDProfileTelemetryLogging::m_dwMaxSessions
0x180004819  cmp     eax, ecx
0x18000481b  jnb     short loc_180004837
0x18000481d  nop     dword ptr [rax]
0x180004820  lock cmpxchg cs:?m_dwMaxSessions@CUVHDProfileTelemetryLogging@@0JC, ecx; long volatile CUVHDProfileTelemetryLogging::m_dwMaxSessions
0x180004828  mov     eax, r14d
0x18000482b  lock xadd cs:?m_dwMaxSessions@CUVHDProfileTelemetryLogging@@0JC, eax; long volatile CUVHDProfileTelemetryLogging::m_dwMaxSessions
0x180004833  cmp     eax, ecx
0x180004835  jb      short loc_180004820
0x180004837  mov     r10d, cs:?m_dwMaxSessions@CUVHDProfileTelemetryLogging@@0JC; long volatile CUVHDProfileTelemetryLogging::m_dwMaxSessions
0x18000483e  mov     eax, cs:dword_1800842C0
0x180004844  cmp     eax, 5
0x180004847  jbe     loc_180004A0C
0x18000484d  mov     rdx, cs:qword_1800842D8
0x180004854  mov     r11, 400000000000h
0x18000485e  mov     rax, cs:qword_1800842D0
0x180004865  test    r11, rax
0x180004868  jz      loc_180004A0C
0x18000486e  mov     rax, rdx
0x180004871  and     rax, r11
0x180004874  cmp     rax, rdx
0x180004877  jnz     loc_180004A0C
0x18000487d  mov     eax, [rsp+130h+var_FC]
0x180004881  lea     rdx, ?m_FarmId@CUVHDProfileTelemetryLogging@@0PAGA; ushort near * CUVHDProfileTelemetryLogging::m_FarmId
0x180004888  mov     [rsp+130h+var_FC], eax
0x18000488c  mov     eax, [rsp+130h+var_F8]
0x180004890  mov     [rsp+130h+var_F8], eax
0x180004894  lea     rax, [rsp+130h+var_100]
0x180004899  mov     [rbp+30h+var_20], rax
0x18000489d  lea     rax, [rsp+130h+var_E8]
0x1800048a2  mov     [rbp+30h+var_30], rax
0x1800048a6  lea     rax, [rsp+130h+var_E4]
0x1800048ab  mov     [rbp+30h+var_40], rax
0x1800048af  lea     rax, [rsp+130h+var_E0]
0x1800048b4  mov     [rbp+30h+var_50], rax
0x1800048b8  lea     rax, [rsp+130h+var_FC]
0x1800048bd  mov     [rbp+30h+var_60], rax
0x1800048c1  lea     rax, [rsp+130h+var_F8]
0x1800048c6  mov     [rbp+30h+var_70], rax
0x1800048ca  lea     rax, [rsp+54h]
0x1800048cf  mov     [rsp+130h+var_E0], ecx
0x1800048d3  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800048da  mov     [rbp+30h+var_80], rax
0x1800048de  mov     rax, rcx
0x1800048e1  mov     [rsp+130h+var_100], r10d
0x1800048e6  mov     [rsp+130h+var_E8], r9d
0x1800048eb  mov     [rsp+130h+var_E4], r8d
0x1800048f0  mov     [rsp+54h], esi
0x1800048f4  mov     [rbp+30h+var_18], 4
0x1800048fc  mov     [rbp+30h+var_28], 4
0x180004904  mov     [rbp+30h+var_38], 4
0x18000490c  mov     [rbp+30h+var_48], 4
0x180004914  mov     [rbp+30h+var_58], 4
0x18000491c  mov     [rbp+30h+var_68], 4
0x180004924  mov     [rbp+30h+var_78], 4
0x18000492c  nop     dword ptr [rax+00h]
0x180004930  cmp     [rdx+rax*2+2], r14w
0x180004936  lea     rax, [rax+1]
0x18000493a  jnz     short loc_180004930
0x18000493c  lea     eax, ds:2[rax*2]
0x180004943  mov     [rbp+30h+var_90], rdx
0x180004947  mov     [rbp+30h+var_88], eax
0x18000494a  lea     rax, ?m_DeploymentId@CUVHDProfileTelemetryLogging@@0PAGA; ushort near * CUVHDProfileTelemetryLogging::m_DeploymentId
0x180004951  mov     [rbp+30h+var_84], r14d
0x180004955  nop     word ptr [rax+rax+00000000h]
0x180004960  cmp     [rax+rcx*2+2], r14w
0x180004966  lea     rcx, [rcx+1]
0x18000496a  jnz     short loc_180004960
0x18000496c  mov     [rbp+30h+var_A0], rax
0x180004970  lea     rdx, [rsp+130h+EventDescriptor]; EventDescriptor
0x180004975  lea     eax, ds:2[rcx*2]
0x18000497c  mov     [rbp+30h+var_94], r14d
0x180004980  mov     [rbp+30h+var_98], eax
0x180004983  lea     rcx, _TraceLoggingMetadata
0x18000498a  movzx   eax, cs:word_18007A6CF
0x180004991  xor     r9d, r9d; RelatedActivityId
0x180004994  mov     dword ptr [rsp+130h+EventDescriptor.Level], eax
0x180004998  xor     r8d, r8d; ActivityId
0x18000499b  mov     rax, cs:off_1800842C8
0x1800049a2  mov     [rsp+130h+var_C0.Ptr], rax
0x1800049a7  mov     dword ptr [rsp+130h+EventDescriptor.Id], 0B000000h
0x1800049af  mov     [rsp+130h+EventDescriptor.Keyword], r11
0x1800049b4  movzx   eax, word ptr [rax]
0x1800049b7  mov     [rsp+130h+var_C0.Size], eax
0x1800049bb  lea     rax, byte_18007A6D9
0x1800049c2  mov     [rbp+30h+var_B0], rax
0x1800049c6  lea     rax, _TraceLoggingMetadataEnd
0x1800049cd  sub     eax, ecx
0x1800049cf  mov     dword ptr [rsp+130h+var_C0.0Ch], 2
0x1800049d7  mov     [rbp+30h+var_A8], 0B4h
0x1800049de  mov     [rbp+30h+var_A4], 1
0x1800049e5  mov     [rsp+130h+var_D8], eax
0x1800049e9  mov     eax, [rsp+130h+var_D8]
0x1800049ed  mov     rcx, cs:qword_1800842E0; RegHandle
0x1800049f4  lea     rax, [rsp+130h+var_C0]
0x1800049f9  mov     [rsp+130h+UserData], rax; UserData
0x1800049fe  mov     dword ptr [rsp+130h+pCount], 0Bh; UserDataCount
0x180004a06  call    cs:__imp_EventWriteTransfer
0x180004a0c  mov     rcx, [rsp+130h+ppSessionInfo]; pMemory
0x180004a11  mov     r14, [rsp+130h+arg_18]
0x180004a19  mov     rdi, [rsp+130h+arg_10]
0x180004a21  mov     rsi, [rsp+130h+arg_8]
0x180004a29  test    rcx, rcx
0x180004a2c  jz      short loc_180004A34
0x180004a2e  call    cs:__imp_WTSFreeMemory
0x180004a34  mov     rcx, [rbp+30h+var_10]
0x180004a38  xor     rcx, rsp; StackCookie
0x180004a3b  call    __security_check_cookie
0x180004a40  add     rsp, 130h
0x180004a47  pop     rbp
0x180004a48  retn
```
