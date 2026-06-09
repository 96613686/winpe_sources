# UbpmUtilsInitialize(void)

- ea: `0x18002a0cc`
- end: `0x18002a519`
- name: `?UbpmUtilsInitialize@@YAKXZ`
- size: `1101`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002a7f0`

## callees

- `0x18000f9a0`
- `0x180019d90`
- `0x18002a0cc`
- `0x18002be80`
- `0x18002e220`
- `0x180032e38`
- `0x180034034`
- `0x180035c10`
- `0x18003d7de`
- `0x18003d810`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18002a21f`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18002a269`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18002a21f`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18002a269`
- `ntdll!RtlInitializeSRWLock` at `0x18002a343`
- `ntdll!RtlInitializeSRWLock` at `0x18002a343`
- `ntdll!NtPowerInformation` at `0x18002a327`
- `ntdll!NtPowerInformation` at `0x18002a327`
- `ntdll!RtlNtStatusToDosError` at `0x18002a1b1`
- `ntdll!RtlNtStatusToDosError` at `0x18002a1b1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002a131`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002a131`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18002a14a`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18002a14a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x18002a406`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x18002a406`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x18002a450`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x18002a450`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x18002a34b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x18002a34b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMinimum` at `0x18002a3d0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMinimum` at `0x18002a3d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a154`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a22d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a273`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a35d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a3da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a418`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a154`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a22d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a273`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a35d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a3da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a418`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a4e5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a4e5`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupOpenLocalPolicy` at `0x18002a1a5`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupOpenLocalPolicy` at `0x18002a1a5`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupGetDomainInfo` at `0x18002a1ca`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupGetDomainInfo` at `0x18002a1ca`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupClose` at `0x18002a4f4`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupClose` at `0x18002a4f4`

## pseudocode

```c
__int64 UbpmUtilsInitialize(void)
{
  HANDLE CurrentProcess; // rax
  DWORD LastError; // eax
  unsigned int CriticalActionsGuids; // ebx
  _QWORD *v3; // rcx
  __int64 v4; // rdx
  int v5; // eax
  ULONG v6; // eax
  unsigned int i; // r14d
  WELL_KNOWN_SID_TYPE v8; // ecx
  void *v9; // r12
  void *v10; // r15
  void *v11; // rax
  DWORD v12; // eax
  struct _TP_POOL *Threadpool; // rax
  DWORD cbSid; // [rsp+30h] [rbp-89h] BYREF
  PVOID DomainInfo; // [rsp+38h] [rbp-81h] BYREF
  PVOID PolicyHandle; // [rsp+40h] [rbp-79h] BYREF
  struct _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+48h] [rbp-71h] BYREF
  _BYTE OutputBuffer[80]; // [rsp+80h] [rbp-39h] BYREF

  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  memset_0(OutputBuffer, 0, 0x4Cu);
  PolicyHandle = 0;
  DomainInfo = 0;
  cbSid = 0;
  if ( g_Globals || (CurrentProcess = GetCurrentProcess(), OpenProcessToken(CurrentProcess, 0xAu, &g_Globals)) )
  {
    v5 = LsaLookupOpenLocalPolicy(&ObjectAttributes, 1u, &PolicyHandle);
    if ( v5 < 0 || (v5 = LsaLookupGetDomainInfo(PolicyHandle, AccountDomainInformation, &DomainInfo), v5 < 0) )
    {
      v6 = RtlNtStatusToDosError(v5);
LABEL_49:
      CriticalActionsGuids = v6;
    }
    else
    {
      for ( i = 0; i < 5; ++i )
      {
        if ( !**((_QWORD **)&g_SidData.Revision + 2 * (int)i) )
        {
          v8 = g_SidData.SubAuthority[4 * i];
          v9 = 0;
          if ( v8 == (WinLocalAccountAndAdministratorSid|WinCreatorGroupSid) )
            v9 = (void *)*((_QWORD *)DomainInfo + 2);
          v10 = 0;
          if ( !CreateWellKnownSid(v8, v9, 0, &cbSid) )
          {
            LastError = GetLastError();
            CriticalActionsGuids = LastError;
            if ( LastError != 122 )
            {
              v3 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                v4 = 11;
                goto LABEL_6;
              }
              goto LABEL_50;
            }
            v11 = UbpmAlloc(cbSid);
            v10 = v11;
            if ( !v11 )
            {
              CriticalActionsGuids = 14;
              goto LABEL_50;
            }
            if ( !CreateWellKnownSid((WELL_KNOWN_SID_TYPE)g_SidData.SubAuthority[4 * i], v9, v11, &cbSid) )
            {
              v12 = GetLastError();
              CriticalActionsGuids = v12;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_53cebd00d02b39c67ce9f6460dbe4812_Traceguids, v12);
              UBPM_MIDL_user_free(v10);
              goto LABEL_50;
            }
          }
          **((_QWORD **)&g_SidData.Revision + 2 * (int)i) = v10;
          cbSid = 0;
        }
      }
      if ( NtPowerInformation(SystemPowerCapabilities, 0, 0, OutputBuffer, 0x4Cu) >= 0 )
        g_pCriticalActions.Data4[0] = OutputBuffer[20] != 0;
      RtlInitializeSRWLock(&g_TpSubmitLock);
      Threadpool = CreateThreadpool(0);
      g_pThreadpool = Threadpool;
      if ( Threadpool )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_53cebd00d02b39c67ce9f6460dbe4812_Traceguids);
          Threadpool = g_pThreadpool;
        }
        if ( SetThreadpoolThreadMinimum(Threadpool, 1u) )
        {
          g_pCleanupGroup = CreateThreadpoolCleanupGroup();
          if ( g_pCleanupGroup )
          {
            SetThreadpoolThreadMaximum(g_pThreadpool, 0x3E8u);
            g_CallbackEnv.Pool = g_pThreadpool;
            g_CallbackEnv.CleanupGroup = g_pCleanupGroup;
            g_CallbackEnv.CleanupGroupCancelCallback = (PTP_CLEANUP_GROUP_CANCEL_CALLBACK)UbpmUtilsThreadPoolCancelCallback;
            g_CallbackEnv.Version = 3;
            *(_OWORD *)&g_CallbackEnv.RaceDll = 0;
            g_CallbackEnv.FinalizationCallback = 0;
            g_CallbackEnv.u.Flags = 0;
            g_CallbackEnv.CallbackPriority = TP_CALLBACK_PRIORITY_NORMAL;
            g_CallbackEnv.Size = 72;
            CriticalActionsGuids = UbpmpGetCriticalActionsGuids();
            if ( !CriticalActionsGuids )
            {
              CriticalActionsGuids = UbpmInitializeMaintenance();
              if ( !CriticalActionsGuids )
              {
                v6 = UbpmSystemInterfaceStart();
                goto LABEL_49;
              }
            }
          }
          else
          {
            LastError = GetLastError();
            CriticalActionsGuids = LastError;
            v3 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v4 = 16;
              goto LABEL_6;
            }
          }
        }
        else
        {
          LastError = GetLastError();
          CriticalActionsGuids = LastError;
          v3 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v4 = 15;
            goto LABEL_6;
          }
        }
      }
      else
      {
        LastError = GetLastError();
        CriticalActionsGuids = LastError;
        v3 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v4 = 13;
          goto LABEL_6;
        }
      }
    }
  }
  else
  {
    LastError = GetLastError();
    CriticalActionsGuids = LastError;
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v4 = 10;
LABEL_6:
      WPP_SF_d(v3[2], v4, WPP_53cebd00d02b39c67ce9f6460dbe4812_Traceguids, LastError);
    }
  }
LABEL_50:
  if ( DomainInfo )
    LocalFree(DomainInfo);
  if ( PolicyHandle )
    LsaLookupClose(PolicyHandle);
  return CriticalActionsGuids;
}

```

## disassembly

```asm
0x18002a0cc  push    rbp
0x18002a0ce  push    rbx
0x18002a0cf  push    rdi
0x18002a0d0  push    r12
0x18002a0d2  push    r14
0x18002a0d4  push    r15
0x18002a0d6  lea     rbp, [rsp-2Fh]
0x18002a0db  sub     rsp, 0E8h
0x18002a0e2  mov     rax, cs:__security_cookie
0x18002a0e9  xor     rax, rsp
0x18002a0ec  mov     [rbp+57h+var_40], rax
0x18002a0f0  xorps   xmm0, xmm0
0x18002a0f3  lea     rcx, [rbp+57h+OutputBuffer]; void *
0x18002a0f7  xor     edx, edx; Val
0x18002a0f9  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x18002a0fd  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x18002a101  lea     r8d, [rdx+4Ch]; Size
0x18002a105  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18002a109  call    memset_0
0x18002a10e  cmp     cs:?g_Globals@@3U_UBPM_GLOBAL_DATA@@A, 0; _UBPM_GLOBAL_DATA g_Globals
0x18002a116  mov     [rbp+57h+PolicyHandle], 0
0x18002a11e  mov     [rsp+110h+DomainInfo], 0
0x18002a127  mov     [rsp+110h+cbSid], 0
0x18002a12f  jnz     short loc_18002A198
0x18002a131  call    cs:__imp_GetCurrentProcess
0x18002a137  mov     r14d, 0Ah
0x18002a13d  lea     r8, ?g_Globals@@3U_UBPM_GLOBAL_DATA@@A; TokenHandle
0x18002a144  mov     rcx, rax; ProcessHandle
0x18002a147  mov     edx, r14d; DesiredAccess
0x18002a14a  call    cs:__imp_OpenProcessToken
0x18002a150  test    eax, eax
0x18002a152  jnz     short loc_18002A198
0x18002a154  call    cs:__imp_GetLastError
0x18002a15a  mov     ebx, eax
0x18002a15c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a163  lea     rdi, WPP_GLOBAL_Control
0x18002a16a  cmp     rcx, rdi
0x18002a16d  jz      loc_18002A4DB
0x18002a173  test    byte ptr [rcx+1Ch], 1
0x18002a177  jz      loc_18002A4DB
0x18002a17d  mov     edx, r14d
0x18002a180  mov     rcx, [rcx+10h]
0x18002a184  lea     r8, WPP_53cebd00d02b39c67ce9f6460dbe4812_Traceguids
0x18002a18b  mov     r9d, eax
0x18002a18e  call    WPP_SF_d
0x18002a193  jmp     loc_18002A4DB
0x18002a198  lea     r8, [rbp+57h+PolicyHandle]; PolicyHandle
0x18002a19c  mov     edx, 1; AccessMask
0x18002a1a1  lea     rcx, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18002a1a5  call    cs:__imp_LsaLookupOpenLocalPolicy
0x18002a1ab  test    eax, eax
0x18002a1ad  jns     short loc_18002A1BC
0x18002a1af  mov     ecx, eax; Status
0x18002a1b1  call    cs:__imp_RtlNtStatusToDosError
0x18002a1b7  jmp     loc_18002A4D9
0x18002a1bc  mov     rcx, [rbp+57h+PolicyHandle]; PolicyHandle
0x18002a1c0  lea     r8, [rsp+110h+DomainInfo]; DomainInfo
0x18002a1c5  mov     edx, 5; DomainInfoClass
0x18002a1ca  call    cs:__imp_LsaLookupGetDomainInfo
0x18002a1d0  test    eax, eax
0x18002a1d2  js      short loc_18002A1AF
0x18002a1d4  xor     r14d, r14d
0x18002a1d7  lea     rcx, ?g_SidData@@3PAU_SID_DATA@@A; _SID_DATA near * g_SidData
0x18002a1de  cmp     r14d, 5
0x18002a1e2  jnb     loc_18002A313
0x18002a1e8  movsxd  rdi, r14d
0x18002a1eb  add     rdi, rdi
0x18002a1ee  mov     rax, [rcx+rdi*8]
0x18002a1f2  cmp     qword ptr [rax], 0
0x18002a1f6  jnz     loc_18002A2D6
0x18002a1fc  mov     ecx, [rcx+rdi*8+8]; WellKnownSidType
0x18002a200  xor     r12d, r12d
0x18002a203  cmp     ecx, 6Eh ; 'n'
0x18002a206  jnz     short loc_18002A211
0x18002a208  mov     rax, [rsp+110h+DomainInfo]
0x18002a20d  mov     r12, [rax+10h]
0x18002a211  lea     r9, [rsp+110h+cbSid]; cbSid
0x18002a216  xor     r8d, r8d; pSid
0x18002a219  mov     rdx, r12; DomainSid
0x18002a21c  xor     r15d, r15d
0x18002a21f  call    cs:__imp_CreateWellKnownSid
0x18002a225  test    eax, eax
0x18002a227  jnz     loc_18002A2B9
0x18002a22d  call    cs:__imp_GetLastError
0x18002a233  mov     ebx, eax
0x18002a235  cmp     eax, 7Ah ; 'z'
0x18002a238  jnz     loc_18002A2E8
0x18002a23e  mov     ecx, [rsp+110h+cbSid]; Size
0x18002a242  call    ?UbpmAlloc@@YAPEAXK@Z; UbpmAlloc(ulong)
0x18002a247  mov     r15, rax
0x18002a24a  test    rax, rax
0x18002a24d  jz      loc_18002A2DE
0x18002a253  lea     rbx, ?g_SidData@@3PAU_SID_DATA@@A; _SID_DATA near * g_SidData
0x18002a25a  mov     r8, rax; pSid
0x18002a25d  mov     ecx, [rbx+rdi*8+8]; WellKnownSidType
0x18002a261  lea     r9, [rsp+110h+cbSid]; cbSid
0x18002a266  mov     rdx, r12; DomainSid
0x18002a269  call    cs:__imp_CreateWellKnownSid
0x18002a26f  test    eax, eax
0x18002a271  jnz     short loc_18002A2C0
0x18002a273  call    cs:__imp_GetLastError
0x18002a279  mov     ebx, eax
0x18002a27b  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a282  lea     rdi, WPP_GLOBAL_Control
0x18002a289  cmp     rcx, rdi
0x18002a28c  jz      short loc_18002A2AC
0x18002a28e  test    byte ptr [rcx+1Ch], 1
0x18002a292  jz      short loc_18002A2AC
0x18002a294  mov     rcx, [rcx+10h]
0x18002a298  lea     r8, WPP_53cebd00d02b39c67ce9f6460dbe4812_Traceguids
0x18002a29f  mov     edx, 0Ch
0x18002a2a4  mov     r9d, eax
0x18002a2a7  call    WPP_SF_d
0x18002a2ac  mov     rcx, r15
0x18002a2af  call    UBPM_MIDL_user_free
0x18002a2b4  jmp     loc_18002A4DB
0x18002a2b9  lea     rbx, ?g_SidData@@3PAU_SID_DATA@@A; _SID_DATA near * g_SidData
0x18002a2c0  mov     rcx, [rbx+rdi*8]
0x18002a2c4  mov     [rcx], r15
0x18002a2c7  lea     rcx, ?g_SidData@@3PAU_SID_DATA@@A; _SID_DATA near * g_SidData
0x18002a2ce  mov     [rsp+110h+cbSid], 0
0x18002a2d6  inc     r14d
0x18002a2d9  jmp     loc_18002A1DE
0x18002a2de  mov     ebx, 0Eh
0x18002a2e3  jmp     loc_18002A4DB
0x18002a2e8  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a2ef  lea     rdi, WPP_GLOBAL_Control
0x18002a2f6  cmp     rcx, rdi
0x18002a2f9  jz      loc_18002A4DB
0x18002a2ff  test    byte ptr [rcx+1Ch], 1
0x18002a303  jz      loc_18002A4DB
0x18002a309  mov     edx, 0Bh
0x18002a30e  jmp     loc_18002A180
0x18002a313  xor     edx, edx; InputBuffer
0x18002a315  mov     [rsp+110h+OutputBufferLength], 4Ch ; 'L'; OutputBufferLength
0x18002a31d  lea     r9, [rbp+57h+OutputBuffer]; OutputBuffer
0x18002a321  xor     r8d, r8d; InputBufferLength
0x18002a324  lea     ecx, [rdx+4]; PowerInformationLevel
0x18002a327  call    cs:__imp_NtPowerInformation
0x18002a32d  test    eax, eax
0x18002a32f  js      short loc_18002A33C
0x18002a331  cmp     [rbp+57h+var_7C], 0
0x18002a335  setnz   cs:?g_pCriticalActions@@3PEAU_GUID@@EA.Data4; _GUID * g_pCriticalActions ...
0x18002a33c  lea     rcx, ?g_TpSubmitLock@@3U_UBPM_SRWLOCK@@A; _UBPM_SRWLOCK g_TpSubmitLock
0x18002a343  call    cs:__imp_RtlInitializeSRWLock
0x18002a349  xor     ecx, ecx; reserved
0x18002a34b  call    cs:__imp_CreateThreadpool
0x18002a351  mov     cs:?g_pThreadpool@@3PEAU_TP_POOL@@EA, rax; _TP_POOL * g_pThreadpool
0x18002a358  test    rax, rax
0x18002a35b  jnz     short loc_18002A390
0x18002a35d  call    cs:__imp_GetLastError
0x18002a363  mov     ebx, eax
0x18002a365  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a36c  lea     rdi, WPP_GLOBAL_Control
0x18002a373  cmp     rcx, rdi
0x18002a376  jz      loc_18002A4DB
0x18002a37c  test    byte ptr [rcx+1Ch], 1
0x18002a380  jz      loc_18002A4DB
0x18002a386  mov     edx, 0Dh
0x18002a38b  jmp     loc_18002A180
0x18002a390  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a397  lea     rdi, WPP_GLOBAL_Control
0x18002a39e  cmp     rcx, rdi
0x18002a3a1  jz      short loc_18002A3C8
0x18002a3a3  test    byte ptr [rcx+1Ch], 4
0x18002a3a7  jz      short loc_18002A3C8
0x18002a3a9  mov     rcx, [rcx+10h]
0x18002a3ad  lea     r8, WPP_53cebd00d02b39c67ce9f6460dbe4812_Traceguids
0x18002a3b4  mov     edx, 0Eh
0x18002a3b9  mov     r9, rax
0x18002a3bc  call    WPP_SF_q
0x18002a3c1  mov     rax, cs:?g_pThreadpool@@3PEAU_TP_POOL@@EA; _TP_POOL * g_pThreadpool
0x18002a3c8  mov     edx, 1; cthrdMic
0x18002a3cd  mov     rcx, rax; ptpp
0x18002a3d0  call    cs:__imp_SetThreadpoolThreadMinimum
0x18002a3d6  test    eax, eax
0x18002a3d8  jnz     short loc_18002A406
0x18002a3da  call    cs:__imp_GetLastError
0x18002a3e0  mov     ebx, eax
0x18002a3e2  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a3e9  cmp     rcx, rdi
0x18002a3ec  jz      loc_18002A4DB
0x18002a3f2  test    byte ptr [rcx+1Ch], 1
0x18002a3f6  jz      loc_18002A4DB
0x18002a3fc  mov     edx, 0Fh
0x18002a401  jmp     loc_18002A180
0x18002a406  call    cs:__imp_CreateThreadpoolCleanupGroup
0x18002a40c  mov     cs:?g_pCleanupGroup@@3PEAU_TP_CLEANUP_GROUP@@EA, rax; _TP_CLEANUP_GROUP * g_pCleanupGroup
0x18002a413  test    rax, rax
0x18002a416  jnz     short loc_18002A444
0x18002a418  call    cs:__imp_GetLastError
0x18002a41e  mov     ebx, eax
0x18002a420  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a427  cmp     rcx, rdi
0x18002a42a  jz      loc_18002A4DB
0x18002a430  test    byte ptr [rcx+1Ch], 1
0x18002a434  jz      loc_18002A4DB
0x18002a43a  mov     edx, 10h
0x18002a43f  jmp     loc_18002A180
0x18002a444  mov     rcx, cs:?g_pThreadpool@@3PEAU_TP_POOL@@EA; ptpp
0x18002a44b  mov     edx, 3E8h; cthrdMost
0x18002a450  call    cs:__imp_SetThreadpoolThreadMaximum
0x18002a456  mov     rax, cs:?g_pThreadpool@@3PEAU_TP_POOL@@EA; _TP_POOL * g_pThreadpool
0x18002a45d  xorps   xmm0, xmm0
0x18002a460  mov     cs:?g_CallbackEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A.Pool, rax; _TP_CALLBACK_ENVIRON_V3 g_CallbackEnv ...
0x18002a467  mov     rax, cs:?g_pCleanupGroup@@3PEAU_TP_CLEANUP_GROUP@@EA; _TP_CLEANUP_GROUP * g_pCleanupGroup
0x18002a46e  mov     cs:?g_CallbackEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A.CleanupGroup, rax; _TP_CALLBACK_ENVIRON_V3 g_CallbackEnv ...
0x18002a475  lea     rax, ?UbpmUtilsThreadPoolCancelCallback@@YAXPEAX0@Z; UbpmUtilsThreadPoolCancelCallback(void *,void *)
0x18002a47c  mov     cs:?g_CallbackEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A.CleanupGroupCancelCallback, rax; _TP_CALLBACK_ENVIRON_V3 g_CallbackEnv ...
0x18002a483  mov     cs:?g_CallbackEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A.Version, 3; _TP_CALLBACK_ENVIRON_V3 g_CallbackEnv ...
0x18002a48d  movdqa  xmmword ptr cs:?g_CallbackEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A.RaceDll, xmm0; _TP_CALLBACK_ENVIRON_V3 g_CallbackEnv ...
0x18002a495  mov     cs:?g_CallbackEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A.FinalizationCallback, 0; _TP_CALLBACK_ENVIRON_V3 g_CallbackEnv ...
0x18002a4a0  mov     dword ptr cs:?g_CallbackEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A.u, 0; _TP_CALLBACK_ENVIRON_V3 g_CallbackEnv ...
0x18002a4aa  mov     cs:?g_CallbackEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A.CallbackPriority, 1; _TP_CALLBACK_ENVIRON_V3 g_CallbackEnv ...
0x18002a4b4  mov     cs:?g_CallbackEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A.Size, 48h ; 'H'; _TP_CALLBACK_ENVIRON_V3 g_CallbackEnv ...
0x18002a4be  call    ?UbpmpGetCriticalActionsGuids@@YAKXZ; UbpmpGetCriticalActionsGuids(void)
0x18002a4c3  mov     ebx, eax
0x18002a4c5  test    eax, eax
0x18002a4c7  jnz     short loc_18002A4DB
0x18002a4c9  call    UbpmInitializeMaintenance
0x18002a4ce  mov     ebx, eax
0x18002a4d0  test    eax, eax
0x18002a4d2  jnz     short loc_18002A4DB
0x18002a4d4  call    ?UbpmSystemInterfaceStart@@YAKXZ; UbpmSystemInterfaceStart(void)
0x18002a4d9  mov     ebx, eax
0x18002a4db  mov     rcx, [rsp+110h+DomainInfo]; hMem
0x18002a4e0  test    rcx, rcx
0x18002a4e3  jz      short loc_18002A4EB
0x18002a4e5  call    cs:__imp_LocalFree
0x18002a4eb  mov     rcx, [rbp+57h+PolicyHandle]; ObjectHandle
0x18002a4ef  test    rcx, rcx
0x18002a4f2  jz      short loc_18002A4FA
0x18002a4f4  call    cs:__imp_LsaLookupClose
0x18002a4fa  mov     eax, ebx
0x18002a4fc  mov     rcx, [rbp+57h+var_40]
0x18002a500  xor     rcx, rsp; StackCookie
0x18002a503  call    __security_check_cookie
0x18002a508  add     rsp, 0E8h
0x18002a50f  pop     r15
0x18002a511  pop     r14
0x18002a513  pop     r12
0x18002a515  pop     rdi
0x18002a516  pop     rbx
0x18002a517  pop     rbp
0x18002a518  retn
```
