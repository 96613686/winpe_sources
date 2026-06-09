# RefreshProcessAffinity(void)

- ea: `0x1004187d0`
- end: `0x100418d0d`
- name: `?RefreshProcessAffinity@@YAXXZ`
- size: `1341`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x100413d90`

## callees

- `0x100401580`
- `0x1004187d0`
- `0x1004403d0`
- `0x100440760`
- `0x100440860`
- `0x1004534f8`

## import_xrefs

- `KERNEL32!GetCurrentThread` at `0x100418cad`
- `KERNEL32!GetCurrentThread` at `0x100418cad`
- `KERNEL32!GetLastError` at `0x100418cc6`
- `KERNEL32!GetLastError` at `0x100418cc6`
- `sqlmin!?MarkComplete@AffinityAutoConfiguration@@QEAAXXZ` at `0x100418b41`
- `sqlmin!?MarkComplete@AffinityAutoConfiguration@@QEAAXXZ` at `0x100418b41`
- `sqlmin!?ApplyConfigChangesNoX@AffinityAutoConfiguration@@QEAAHXZ` at `0x100418b37`
- `sqlmin!?ApplyConfigChangesNoX@AffinityAutoConfiguration@@QEAAHXZ` at `0x100418b37`
- `sqlmin!??1AffinityAutoConfiguration@@QEAA@XZ` at `0x100418cdf`
- `sqlmin!??1AffinityAutoConfiguration@@QEAA@XZ` at `0x100418cdf`
- `sqlmin!??0AffinityAutoConfiguration@@QEAA@AEBVSystemAffinity@@W4OS_AFFINITY@SOS_OS@@@Z` at `0x100418b2c`
- `sqlmin!??0AffinityAutoConfiguration@@QEAA@AEBVSystemAffinity@@W4OS_AFFINITY@SOS_OS@@@Z` at `0x100418b2c`
- `sqlmin!?ValidateProcessorAffinityNoX@AffinityAutoConfiguration@@SAHAEBVSystemAffinity@@PEAVSysConfigPagePtr@@@Z` at `0x100418a90`
- `sqlmin!?ValidateProcessorAffinityNoX@AffinityAutoConfiguration@@SAHAEBVSystemAffinity@@PEAVSysConfigPagePtr@@@Z` at `0x100418a90`
- `sqlmin!?FUseReplicatedServerContext@@YA_NXZ` at `0x1004188c5`
- `sqlmin!?FUseReplicatedServerContext@@YA_NXZ` at `0x1004189ef`
- `sqlmin!?FUseReplicatedServerContext@@YA_NXZ` at `0x100418a6a`
- `sqlmin!?FUseReplicatedServerContext@@YA_NXZ` at `0x100418aa4`
- `sqlmin!?FUseReplicatedServerContext@@YA_NXZ` at `0x100418acb`
- `sqlmin!?FUseReplicatedServerContext@@YA_NXZ` at `0x1004188c5`
- `sqlmin!?FUseReplicatedServerContext@@YA_NXZ` at `0x1004189ef`
- `sqlmin!?FUseReplicatedServerContext@@YA_NXZ` at `0x100418a6a`
- `sqlmin!?FUseReplicatedServerContext@@YA_NXZ` at `0x100418aa4`
- `sqlmin!?FUseReplicatedServerContext@@YA_NXZ` at `0x100418acb`
- `sqlmin!GetXdbServerGlobals` at `0x100418818`
- `sqlmin!GetXdbServerGlobals` at `0x100418818`
- `sqlmin!?CalculateMaxLogicalProcessors@StartUp@@SAXXZ` at `0x1004188af`
- `sqlmin!?CalculateMaxLogicalProcessors@StartUp@@SAXXZ` at `0x1004188af`
- `sqldk!?SOS_OS_LPPerCore@@3KA` at `0x100418c1a`
- `sqldk!?sm_AffinityMask@SOS_PublicGlobals@@2VSystemAffinity@@A` at `0x100418c8c`
- `sqldk!?SOS_OS_AffinityType@@3W4OS_AFFINITY@SOS_OS@@A` at `0x100418b47`
- `sqldk!?SOS_OS_InitialAffinityType@@3W4OS_AFFINITY@SOS_OS@@A` at `0x100418b50`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x100418892`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x100418c5b`
- `sqldk!??0SystemAffinity@@QEAA@XZ` at `0x100418846`
- `sqldk!??0SystemAffinity@@QEAA@XZ` at `0x100418853`
- `sqldk!??0SystemAffinity@@QEAA@XZ` at `0x100418860`
- `sqldk!??0SystemAffinity@@QEAA@XZ` at `0x10041888c`
- `sqldk!??0SystemAffinity@@QEAA@XZ` at `0x100418846`
- `sqldk!??0SystemAffinity@@QEAA@XZ` at `0x100418853`
- `sqldk!??0SystemAffinity@@QEAA@XZ` at `0x100418860`
- `sqldk!??0SystemAffinity@@QEAA@XZ` at `0x10041888c`
- `sqldk!?GetCPUCount@SystemAffinity@@QEBAIXZ` at `0x100418c75`
- `sqldk!?GetCPUCount@SystemAffinity@@QEBAIXZ` at `0x100418c75`
- `sqldk!?TurnOn@CGlobalTraceFlags@@SA_NGW4FlagUsage@1@@Z` at `0x1004188a9`
- `sqldk!?TurnOn@CGlobalTraceFlags@@SA_NGW4FlagUsage@1@@Z` at `0x1004188a9`
- `sqldk!??0GroupAffinity@@QEAA@XZ` at `0x100418878`
- `sqldk!??0GroupAffinity@@QEAA@XZ` at `0x100418878`
- `sqldk!?GetOsProcessAffinity@SOS_OS@@SAHPEAVSystemAffinity@@@Z` at `0x100418918`
- `sqldk!?GetOsProcessAffinity@SOS_OS@@SAHPEAVSystemAffinity@@@Z` at `0x100418918`
- `sqldk!?IsEmpty@SystemAffinity@@QEBAHXZ` at `0x100418923`
- `sqldk!?IsEmpty@SystemAffinity@@QEBAHXZ` at `0x100418afd`
- `sqldk!?IsEmpty@SystemAffinity@@QEBAHXZ` at `0x100418923`
- `sqldk!?IsEmpty@SystemAffinity@@QEBAHXZ` at `0x100418afd`
- `sqldk!?GetGroup@GroupAffinity@@QEBAGXZ` at `0x10041896d`
- `sqldk!?GetGroup@GroupAffinity@@QEBAGXZ` at `0x100418988`
- `sqldk!?GetGroup@GroupAffinity@@QEBAGXZ` at `0x10041896d`
- `sqldk!?GetGroup@GroupAffinity@@QEBAGXZ` at `0x100418988`
- `sqldk!?GetFirstGroupSet@SystemAffinity@@QEBA?BVGroupAffinity@@XZ` at `0x10041897f`
- `sqldk!?GetFirstGroupSet@SystemAffinity@@QEBA?BVGroupAffinity@@XZ` at `0x100418ca4`
- `sqldk!?GetFirstGroupSet@SystemAffinity@@QEBA?BVGroupAffinity@@XZ` at `0x10041897f`
- `sqldk!?GetFirstGroupSet@SystemAffinity@@QEBA?BVGroupAffinity@@XZ` at `0x100418ca4`
- `sqldk!?GetLastGroupSet@SystemAffinity@@QEBA?BVGroupAffinity@@XZ` at `0x100418964`
- `sqldk!?GetLastGroupSet@SystemAffinity@@QEBA?BVGroupAffinity@@XZ` at `0x100418964`
- `sqldk!?LoadHardwareConfig@SOS_OS@@SAXAEBVSystemAffinity@@@Z` at `0x10041894b`
- `sqldk!?LoadHardwareConfig@SOS_OS@@SAXAEBVSystemAffinity@@@Z` at `0x10041894b`
- `sqldk!?Instance@OsNumaConfig@@SAPEAV1@XZ` at `0x100418c7f`
- `sqldk!?Instance@OsNumaConfig@@SAPEAV1@XZ` at `0x100418c7f`
- `sqldk!?sm_cpuCount@SOS_PublicGlobals@@2KA` at `0x100418b74`
- `sqldk!?sm_cpuCount@SOS_PublicGlobals@@2KA` at `0x100418b96`
- `sqldk!?sm_cpuCount@SOS_PublicGlobals@@2KA` at `0x100418bbd`
- `sqldk!?sm_cpuCount@SOS_PublicGlobals@@2KA` at `0x100418bd6`
- `sqldk!?sm_cpuCount@SOS_PublicGlobals@@2KA` at `0x100418bf7`
- `sqldk!?sm_cpuCount@SOS_PublicGlobals@@2KA` at `0x100418c07`
- `sqldk!?sm_cpuCount@SOS_PublicGlobals@@2KA` at `0x100418c24`
- `sqldk!?sm_osOptions@SOS_PublicGlobals@@2KA` at `0x100418942`
- `sqldk!?SafeCopy@SystemAffinity@@QEBA?AV1@XZ` at `0x100418c93`
- `sqldk!?SafeCopy@SystemAffinity@@QEBA?AV1@XZ` at `0x100418c93`
- `sqldk!?SOS_OS_LPperPP@@3KA` at `0x100418c10`
- `sqldk!?SOS_OS_LPperPP@@3KA` at `0x100418c2d`
- `sqldk!?sm_osStatus@SOS_PublicGlobals@@2KA` at `0x100418931`
- `hostregdll!HostReg_IsFeatureSwitchOn` at `0x1004189af`
- `hostregdll!HostReg_IsFeatureSwitchOn` at `0x1004189af`

## string_xrefs

- `0x1004189a8`: `SQL.Config`
- `0x1004189da`: `SqlServer is starting with Hard-Affinity(MANUAL) configuration`
- `0x1004189c2`: `SqlServer is starting with Soft-Affinity(AUTO) configuration`
- `0x100418cce`: `SetThreadAffinity failed: %d\n`

## pseudocode

```c
// write access to const memory has been detected, the output may be wrong!
// Hidden C++ exception states: #wind=1
void __fastcall RefreshProcessAffinity(__int64 a1, __int64 a2)
{
  unsigned int v2; // esi
  GroupAffinity *v3; // rbx
  __int64 v4; // rdi
  RESOURCE *v5; // rax
  char *v6; // rcx
  unsigned int v7; // edi
  GroupAffinity *LastGroupSet; // rax
  unsigned __int16 Group; // bx
  GroupAffinity *FirstGroupSet; // rax
  char IsFeatureSwitchOn; // al
  char *v12; // rax
  struct SysConfigPagePtr *v13; // rdx
  char *v14; // rax
  char *v15; // rax
  RESOURCE *v16; // rdx
  int v17; // eax
  unsigned int v18; // r9d
  unsigned int v19; // r11d
  __int64 v20; // rax
  __int64 *v21; // rsi
  __int64 v22; // rdi
  __int64 v23; // rbx
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  _QWORD v26[2]; // [rsp+38h] [rbp-D0h] BYREF
  _OWORD v27[8]; // [rsp+48h] [rbp-C0h] BYREF
  _BYTE v28[16]; // [rsp+C8h] [rbp-40h] BYREF
  _BYTE v29[16]; // [rsp+D8h] [rbp-30h] BYREF
  _BYTE v30[128]; // [rsp+E8h] [rbp-20h] BYREF
  _BYTE v31[288]; // [rsp+168h] [rbp+60h] BYREF
  _BYTE v32[128]; // [rsp+288h] [rbp+180h] BYREF
  _BYTE v33[128]; // [rsp+308h] [rbp+200h] BYREF
  _BYTE v34[128]; // [rsp+388h] [rbp+280h] BYREF
  char v35; // [rsp+408h] [rbp+300h] BYREF

  v26[1] = -2;
  if ( *((_DWORD *)qword_10049F360 + 3626) && *(_DWORD *)(GetXdbServerGlobals(a1, a2) + 12000) )
  {
    LogSystemMetadataNotSentToClient(L"%ls", L"Skipping affinity refresh due to running in sqlpal.\n");
    return;
  }
  SystemAffinity::SystemAffinity((SystemAffinity *)v32);
  SystemAffinity::SystemAffinity((SystemAffinity *)v33);
  SystemAffinity::SystemAffinity((SystemAffinity *)v34);
  v2 = 1;
  v3 = (GroupAffinity *)&v35;
  v4 = 64;
  do
  {
    GroupAffinity::GroupAffinity(v3);
    v3 = (GroupAffinity *)((char *)v3 + 16);
    --v4;
  }
  while ( v4 );
  SystemAffinity::SystemAffinity((SystemAffinity *)v27);
  if ( *((_DWORD *)s_pServerConf + 2) == 3 )
    CGlobalTraceFlags::TurnOn(8017, 0);
  StartUp::CalculateMaxLogicalProcessors();
  v5 = qword_10049F360;
  if ( (*((_BYTE *)qword_10049F360 + 48508) & 0x81) != 0 )
  {
    if ( FUseReplicatedServerContext() )
      v6 = (char *)qword_10049F360 + 28520;
    else
      v6 = (char *)qword_10049F360 + 14864;
    memset_0(v6 + 12604, 0, 0x400u);
    v5 = qword_10049F360;
  }
  v7 = 2;
  if ( !*((_DWORD *)v5 + 3626)
    || (SOS_OS::GetOsProcessAffinity((struct SystemAffinity *)v27), SystemAffinity::IsEmpty((SystemAffinity *)v27)) )
  {
    if ( FUseReplicatedServerContext() )
      v12 = (char *)qword_10049F360 + 28520;
    else
      v12 = (char *)qword_10049F360 + 14864;
    v27[0] = *(_OWORD *)(v12 + 12604);
    v27[1] = *(_OWORD *)(v12 + 12620);
    v27[2] = *(_OWORD *)(v12 + 12636);
    v27[3] = *(_OWORD *)(v12 + 12652);
    v27[4] = *(_OWORD *)(v12 + 12668);
    v27[5] = *(_OWORD *)(v12 + 12684);
    v27[6] = *(_OWORD *)(v12 + 12700);
    v27[7] = *(_OWORD *)(v12 + 12716);
  }
  else if ( (SOS_PublicGlobals::sm_osStatus & 0x20) != 0 )
  {
    SOS_OS::LoadHardwareConfig((const struct SystemAffinity *)v27);
    v2 = (SOS_PublicGlobals::sm_osOptions & 0x40 | 0x80) >> 6;
  }
  else
  {
    LastGroupSet = (GroupAffinity *)SystemAffinity::GetLastGroupSet(v27, v29);
    Group = GroupAffinity::GetGroup(LastGroupSet);
    FirstGroupSet = (GroupAffinity *)SystemAffinity::GetFirstGroupSet(v27, v28);
    if ( GroupAffinity::GetGroup(FirstGroupSet) != Group )
    {
      LOBYTE(v26[0]) = 0;
      IsFeatureSwitchOn = HostReg_IsFeatureSwitchOn(L"SQL.Config", L"EnableSoftAffinityMode", v26);
      if ( LOBYTE(v26[0]) && IsFeatureSwitchOn )
      {
        v2 = 2;
        LogSystemMetadataNotSentToClient(L"%ls", L"SqlServer is starting with Soft-Affinity(AUTO) configuration");
      }
      else
      {
        LogSystemMetadataNotSentToClient(L"%ls", L"SqlServer is starting with Hard-Affinity(MANUAL) configuration");
      }
    }
  }
  if ( FUseReplicatedServerContext() )
    v13 = (RESOURCE *)((char *)qword_10049F360 + 28520);
  else
    v13 = (RESOURCE *)((char *)qword_10049F360 + 14864);
  if ( AffinityAutoConfiguration::ValidateProcessorAffinityNoX((const struct SystemAffinity *)v27, v13) )
  {
    scierrlog(0x42E9u);
    if ( FUseReplicatedServerContext() )
      v14 = (char *)qword_10049F360 + 28520;
    else
      v14 = (char *)qword_10049F360 + 14864;
    *((_DWORD *)v14 + 3076) = 0;
    if ( FUseReplicatedServerContext() )
      v15 = (char *)qword_10049F360 + 28520;
    else
      v15 = (char *)qword_10049F360 + 14864;
    *((_DWORD *)v15 + 3085) = 0;
  }
  else
  {
    if ( SystemAffinity::IsEmpty((SystemAffinity *)v27) )
      v2 = 2;
    v7 = v2;
  }
  if ( (*(_BYTE *)(qword_10049F340 + 1009) & 0x40) != 0 )
    v7 = 3;
  AffinityAutoConfiguration::AffinityAutoConfiguration(v31, v27, v7);
  AffinityAutoConfiguration::ApplyConfigChangesNoX((AffinityAutoConfiguration *)v31);
  AffinityAutoConfiguration::MarkComplete((AffinityAutoConfiguration *)v31);
  SOS_OS_InitialAffinityType = SOS_OS_AffinityType;
  v16 = qword_10049F360;
  v17 = *((_DWORD *)qword_10049F360 + 2935);
  if ( v17 == 1804890536 || v17 == 1020889822 )
  {
    if ( *((_DWORD *)qword_10049F360 + 3162) < SOS_PublicGlobals::sm_cpuCount )
    {
      scierrlog(0x431Au);
      if ( *((_DWORD *)qword_10049F360 + 3162) >= SOS_PublicGlobals::sm_cpuCount )
        v18 = SOS_PublicGlobals::sm_cpuCount;
      else
        v18 = *((_DWORD *)qword_10049F360 + 3162);
      v19 = 17179;
      goto LABEL_54;
    }
    v16 = qword_10049F360;
  }
  if ( *((_DWORD *)v16 + 3162) >= SOS_PublicGlobals::sm_cpuCount )
    v18 = SOS_PublicGlobals::sm_cpuCount;
  else
    v18 = *((_DWORD *)qword_10049F360 + 3162);
  v19 = 17164;
LABEL_54:
  scierrlog(
    v19,
    SOS_PublicGlobals::sm_cpuCount / SOS_OS_LPperPP,
    SOS_OS_LPperPP / SOS_OS_LPPerCore,
    SOS_OS_LPperPP,
    SOS_PublicGlobals::sm_cpuCount,
    v18);
  v20 = (*(__int64 (__fastcall **)(struct IServerConfiguration *))(*(_QWORD *)s_pServerConf + 504LL))(s_pServerConf);
  if ( SystemAffinity::GetCPUCount((SystemAffinity *)(v20 + 304)) )
  {
    v21 = (__int64 *)OsNumaConfig::Instance();
    SystemAffinity::SafeCopy(SOS_PublicGlobals::sm_AffinityMask, v30);
    v22 = *v21;
    v23 = SystemAffinity::GetFirstGroupSet(v30, v28);
    CurrentThread = GetCurrentThread();
    if ( !(*(unsigned int (__fastcall **)(__int64 *, HANDLE, __int64, _QWORD))(v22 + 48))(v21, CurrentThread, v23, 0) )
    {
      LastError = GetLastError();
      LogSystemMetadata(L"SetThreadAffinity failed: %d\n", LastError);
    }
  }
  AffinityAutoConfiguration::~AffinityAutoConfiguration((AffinityAutoConfiguration *)v31);
}

```

## disassembly

```asm
0x1004187d0  mov     rax, rsp
0x1004187d3  push    rbp
0x1004187d4  lea     rbp, [rax-718h]
0x1004187db  sub     rsp, 810h
0x1004187e2  mov     qword ptr [rsp+810h+var_7D8], 0FFFFFFFFFFFFFFFEh
0x1004187eb  mov     [rax+8], rbx
0x1004187ef  mov     [rax+10h], rsi
0x1004187f3  mov     [rax+18h], rdi
0x1004187f7  mov     rax, cs:__security_cookie
0x1004187fe  xor     rax, rsp
0x100418801  mov     [rbp+710h+var_10], rax
0x100418808  mov     rax, cs:qword_10049F360
0x10041880f  cmp     dword ptr [rax+38A8h], 0
0x100418816  jz      short loc_10041883F
0x100418818  call    cs:__imp_GetXdbServerGlobals
0x10041881e  cmp     dword ptr [rax+2EE0h], 0
0x100418825  jz      short loc_10041883F
0x100418827  lea     rdx, aSkippingAffini; "Skipping affinity refresh due to runnin"...
0x10041882e  lea     rcx, aLs; "%ls"
0x100418835  call    ?LogSystemMetadataNotSentToClient@@YAXPEB_WZZ; LogSystemMetadataNotSentToClient(wchar_t const *,...)
0x10041883a  jmp     loc_100418CE5
0x10041883f  lea     rcx, [rbp+710h+var_590]
0x100418846  call    cs:__imp_??0SystemAffinity@@QEAA@XZ; SystemAffinity::SystemAffinity(void)
0x10041884c  lea     rcx, [rbp+710h+var_510]
0x100418853  call    cs:__imp_??0SystemAffinity@@QEAA@XZ; SystemAffinity::SystemAffinity(void)
0x100418859  lea     rcx, [rbp+710h+var_490]
0x100418860  call    cs:__imp_??0SystemAffinity@@QEAA@XZ; SystemAffinity::SystemAffinity(void)
0x100418866  mov     esi, 1
0x10041886b  lea     rbx, [rbp+710h+var_410]
0x100418872  lea     edi, [rsi+3Fh]
0x100418875  mov     rcx, rbx
0x100418878  call    cs:__imp_??0GroupAffinity@@QEAA@XZ; GroupAffinity::GroupAffinity(void)
0x10041887e  add     rbx, 10h
0x100418882  sub     rdi, rsi
0x100418885  jnz     short loc_100418875
0x100418887  lea     rcx, [rsp+810h+var_7D8+8]
0x10041888c  call    cs:__imp_??0SystemAffinity@@QEAA@XZ; SystemAffinity::SystemAffinity(void)
0x100418892  mov     rax, cs:__imp_?s_pServerConf@@3PEAVIServerConfiguration@@EA; IServerConfiguration * s_pServerConf
0x100418899  mov     rcx, [rax]
0x10041889c  cmp     dword ptr [rcx+8], 3
0x1004188a0  jnz     short loc_1004188AF
0x1004188a2  mov     ecx, 1F51h
0x1004188a7  xor     edx, edx
0x1004188a9  call    cs:__imp_?TurnOn@CGlobalTraceFlags@@SA_NGW4FlagUsage@1@@Z; CGlobalTraceFlags::TurnOn(ushort,CGlobalTraceFlags::FlagUsage)
0x1004188af  call    cs:__imp_?CalculateMaxLogicalProcessors@StartUp@@SAXXZ; StartUp::CalculateMaxLogicalProcessors(void)
0x1004188b5  mov     rax, cs:qword_10049F360
0x1004188bc  test    byte ptr [rax+0BD7Ch], 81h
0x1004188c3  jz      short loc_100418901
0x1004188c5  call    cs:__imp_?FUseReplicatedServerContext@@YA_NXZ; FUseReplicatedServerContext(void)
0x1004188cb  mov     rcx, cs:qword_10049F360
0x1004188d2  test    al, al
0x1004188d4  jnz     short loc_1004188DF
0x1004188d6  add     rcx, 3A10h
0x1004188dd  jmp     short loc_1004188E6
0x1004188df  add     rcx, 6F68h
0x1004188e6  add     rcx, 313Ch; void *
0x1004188ed  xor     edx, edx; Val
0x1004188ef  mov     r8d, 400h; Size
0x1004188f5  call    memset_0
0x1004188fa  mov     rax, cs:qword_10049F360
0x100418901  mov     edi, 2
0x100418906  cmp     dword ptr [rax+38A8h], 0
0x10041890d  jz      loc_1004189EF
0x100418913  lea     rcx, [rsp+810h+var_7D8+8]
0x100418918  call    cs:__imp_?GetOsProcessAffinity@SOS_OS@@SAHPEAVSystemAffinity@@@Z; SOS_OS::GetOsProcessAffinity(SystemAffinity *)
0x10041891e  lea     rcx, [rsp+810h+var_7D8+8]
0x100418923  call    cs:__imp_?IsEmpty@SystemAffinity@@QEBAHXZ; SystemAffinity::IsEmpty(void)
0x100418929  test    eax, eax
0x10041892b  jnz     loc_1004189EF
0x100418931  mov     rax, cs:__imp_?sm_osStatus@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStatus
0x100418938  lea     rcx, [rsp+810h+var_7D8+8]
0x10041893d  test    byte ptr [rax], 20h
0x100418940  jz      short loc_100418960
0x100418942  mov     rax, cs:__imp_?sm_osOptions@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osOptions
0x100418949  mov     esi, [rax]
0x10041894b  call    cs:__imp_?LoadHardwareConfig@SOS_OS@@SAXAEBVSystemAffinity@@@Z; SOS_OS::LoadHardwareConfig(SystemAffinity const &)
0x100418951  and     esi, 40h
0x100418954  bts     esi, 7
0x100418958  shr     esi, 6
0x10041895b  jmp     loc_100418A6A
0x100418960  lea     rdx, [rbp+710h+var_740]
0x100418964  call    cs:__imp_?GetLastGroupSet@SystemAffinity@@QEBA?BVGroupAffinity@@XZ; SystemAffinity::GetLastGroupSet(void)
0x10041896a  mov     rcx, rax
0x10041896d  call    cs:__imp_?GetGroup@GroupAffinity@@QEBAGXZ; GroupAffinity::GetGroup(void)
0x100418973  movzx   ebx, ax
0x100418976  lea     rdx, [rbp+710h+var_750]
0x10041897a  lea     rcx, [rsp+810h+var_7D8+8]
0x10041897f  call    cs:__imp_?GetFirstGroupSet@SystemAffinity@@QEBA?BVGroupAffinity@@XZ; SystemAffinity::GetFirstGroupSet(void)
0x100418985  mov     rcx, rax
0x100418988  call    cs:__imp_?GetGroup@GroupAffinity@@QEBAGXZ; GroupAffinity::GetGroup(void)
0x10041898e  cmp     ax, bx
0x100418991  jz      loc_100418A6A
0x100418997  mov     byte ptr [rsp+810h+var_7E0], 0
0x10041899c  lea     r8, [rsp+810h+var_7E0]
0x1004189a1  lea     rdx, aEnablesoftaffi; "EnableSoftAffinityMode"
0x1004189a8  lea     rcx, aSqlConfig; "SQL.Config"
0x1004189af  call    cs:__imp_HostReg_IsFeatureSwitchOn
0x1004189b5  cmp     byte ptr [rsp+810h+var_7E0], 0
0x1004189ba  jz      short loc_1004189DA
0x1004189bc  test    al, al
0x1004189be  jz      short loc_1004189DA
0x1004189c0  mov     esi, edi
0x1004189c2  lea     rdx, aSqlserverIsSta; "SqlServer is starting with Soft-Affinit"...
0x1004189c9  lea     rcx, aLs; "%ls"
0x1004189d0  call    ?LogSystemMetadataNotSentToClient@@YAXPEB_WZZ; LogSystemMetadataNotSentToClient(wchar_t const *,...)
0x1004189d5  jmp     loc_100418A6A
0x1004189da  lea     rdx, aSqlserverIsSta_0; "SqlServer is starting with Hard-Affinit"...
0x1004189e1  lea     rcx, aLs; "%ls"
0x1004189e8  call    ?LogSystemMetadataNotSentToClient@@YAXPEB_WZZ; LogSystemMetadataNotSentToClient(wchar_t const *,...)
0x1004189ed  jmp     short loc_100418A6A
0x1004189ef  call    cs:__imp_?FUseReplicatedServerContext@@YA_NXZ; FUseReplicatedServerContext(void)
0x1004189f5  test    al, al
0x1004189f7  mov     rax, cs:qword_10049F360
0x1004189fe  jnz     short loc_100418A08
0x100418a00  add     rax, 3A10h
0x100418a06  jmp     short loc_100418A0E
0x100418a08  add     rax, 6F68h
0x100418a0e  movups  xmm0, xmmword ptr [rax+313Ch]
0x100418a15  movaps  [rsp+810h+var_7D8+8], xmm0
0x100418a1a  movups  xmm1, xmmword ptr [rax+314Ch]
0x100418a21  movaps  [rsp+810h+var_7C8+8], xmm1
0x100418a26  movups  xmm0, xmmword ptr [rax+315Ch]
0x100418a2d  movaps  [rsp+810h+var_7B8+8], xmm0
0x100418a32  movups  xmm1, xmmword ptr [rax+316Ch]
0x100418a39  movaps  [rsp+810h+var_7A8+8], xmm1
0x100418a3e  movups  xmm0, xmmword ptr [rax+317Ch]
0x100418a45  movaps  [rbp+710h+var_790], xmm0
0x100418a49  movups  xmm1, xmmword ptr [rax+318Ch]
0x100418a50  movaps  [rbp+710h+var_780], xmm1
0x100418a54  movups  xmm0, xmmword ptr [rax+319Ch]
0x100418a5b  movaps  [rbp+710h+var_770], xmm0
0x100418a5f  movups  xmm1, xmmword ptr [rax+31ACh]
0x100418a66  movaps  [rbp+710h+var_760], xmm1
0x100418a6a  call    cs:__imp_?FUseReplicatedServerContext@@YA_NXZ; FUseReplicatedServerContext(void)
0x100418a70  mov     rdx, cs:qword_10049F360
0x100418a77  test    al, al
0x100418a79  jnz     short loc_100418A84
0x100418a7b  add     rdx, 3A10h
0x100418a82  jmp     short loc_100418A8B
0x100418a84  add     rdx, 6F68h
0x100418a8b  lea     rcx, [rsp+810h+var_7D8+8]
0x100418a90  call    cs:__imp_?ValidateProcessorAffinityNoX@AffinityAutoConfiguration@@SAHAEBVSystemAffinity@@PEAVSysConfigPagePtr@@@Z; AffinityAutoConfiguration::ValidateProcessorAffinityNoX(SystemAffinity const &,SysConfigPagePtr *)
0x100418a96  test    eax, eax
0x100418a98  jz      short loc_100418AF8
0x100418a9a  mov     ecx, 42E9h; unsigned int
0x100418a9f  call    ?scierrlog@@YAXKZZ; scierrlog(ulong,...)
0x100418aa4  call    cs:__imp_?FUseReplicatedServerContext@@YA_NXZ; FUseReplicatedServerContext(void)
0x100418aaa  test    al, al
0x100418aac  mov     rax, cs:qword_10049F360
0x100418ab3  jnz     short loc_100418ABD
0x100418ab5  add     rax, 3A10h
0x100418abb  jmp     short loc_100418AC3
0x100418abd  add     rax, 6F68h
0x100418ac3  xor     ebx, ebx
0x100418ac5  mov     [rax+3010h], ebx
0x100418acb  call    cs:__imp_?FUseReplicatedServerContext@@YA_NXZ; FUseReplicatedServerContext(void)
0x100418ad1  test    al, al
0x100418ad3  mov     rax, cs:qword_10049F360
0x100418ada  jnz     short loc_100418AEA
0x100418adc  add     rax, 3A10h
0x100418ae2  mov     [rax+3034h], ebx
0x100418ae8  jmp     short loc_100418B0A
0x100418aea  add     rax, 6F68h
0x100418af0  mov     [rax+3034h], ebx
0x100418af6  jmp     short loc_100418B0A
0x100418af8  lea     rcx, [rsp+810h+var_7D8+8]
0x100418afd  call    cs:__imp_?IsEmpty@SystemAffinity@@QEBAHXZ; SystemAffinity::IsEmpty(void)
0x100418b03  test    eax, eax
0x100418b05  cmovnz  esi, edi
0x100418b08  mov     edi, esi
0x100418b0a  mov     rax, cs:qword_10049F340
0x100418b11  test    byte ptr [rax+3F1h], 40h
0x100418b18  mov     eax, 3
0x100418b1d  cmovnz  edi, eax
0x100418b20  mov     r8d, edi
0x100418b23  lea     rdx, [rsp+810h+var_7D8+8]
0x100418b28  lea     rcx, [rbp+710h+var_6B0]
0x100418b2c  call    cs:__imp_??0AffinityAutoConfiguration@@QEAA@AEBVSystemAffinity@@W4OS_AFFINITY@SOS_OS@@@Z; AffinityAutoConfiguration::AffinityAutoConfiguration(SystemAffinity const &,SOS_OS::OS_AFFINITY)
0x100418b32  nop
0x100418b33  lea     rcx, [rbp+710h+var_6B0]
0x100418b37  call    cs:__imp_?ApplyConfigChangesNoX@AffinityAutoConfiguration@@QEAAHXZ; AffinityAutoConfiguration::ApplyConfigChangesNoX(void)
0x100418b3d  lea     rcx, [rbp+710h+var_6B0]
0x100418b41  call    cs:__imp_?MarkComplete@AffinityAutoConfiguration@@QEAAXXZ; AffinityAutoConfiguration::MarkComplete(void)
0x100418b47  mov     rax, cs:__imp_?SOS_OS_AffinityType@@3W4OS_AFFINITY@SOS_OS@@A; SOS_OS::OS_AFFINITY SOS_OS_AffinityType
0x100418b4e  mov     ecx, [rax]
0x100418b50  mov     rax, cs:__imp_?SOS_OS_InitialAffinityType@@3W4OS_AFFINITY@SOS_OS@@A; SOS_OS::OS_AFFINITY SOS_OS_InitialAffinityType
0x100418b57  mov     [rax], ecx
0x100418b59  mov     rdx, cs:qword_10049F360
0x100418b60  mov     eax, [rdx+2DDCh]
0x100418b66  cmp     eax, 6B9471A8h
0x100418b6b  jz      short loc_100418B74
0x100418b6d  cmp     eax, 3CD98ADEh
0x100418b72  jnz     short loc_100418BD6
0x100418b74  mov     rax, cs:__imp_?sm_cpuCount@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_cpuCount
0x100418b7b  mov     ecx, [rax]
0x100418b7d  cmp     [rdx+3168h], ecx
0x100418b83  jnb     short loc_100418BCF
0x100418b85  mov     ecx, 431Ah; unsigned int
0x100418b8a  call    ?scierrlog@@YAXKZZ; scierrlog(ulong,...)
0x100418b8f  mov     rdx, cs:qword_10049F360
0x100418b96  mov     rax, cs:__imp_?sm_cpuCount@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_cpuCount
0x100418b9d  mov     ecx, [rax]
0x100418b9f  cmp     [rdx+3168h], ecx
0x100418ba5  jnb     short loc_100418BBD
0x100418ba7  mov     rax, cs:qword_10049F360
0x100418bae  mov     r9d, [rax+3168h]
0x100418bb5  mov     r11d, 431Bh
0x100418bbb  jmp     short loc_100418C07
0x100418bbd  mov     rax, cs:__imp_?sm_cpuCount@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_cpuCount
0x100418bc4  mov     r9d, [rax]
0x100418bc7  mov     r11d, 431Bh
0x100418bcd  jmp     short loc_100418C07
0x100418bcf  mov     rdx, cs:qword_10049F360
0x100418bd6  mov     rax, cs:__imp_?sm_cpuCount@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_cpuCount
0x100418bdd  mov     ecx, [rax]
0x100418bdf  cmp     [rdx+3168h], ecx
0x100418be5  jnb     short loc_100418BF7
0x100418be7  mov     rax, cs:qword_10049F360
0x100418bee  mov     r9d, [rax+3168h]
0x100418bf5  jmp     short loc_100418C01
0x100418bf7  mov     rax, cs:__imp_?sm_cpuCount@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_cpuCount
0x100418bfe  mov     r9d, [rax]
0x100418c01  mov     r11d, 430Ch
0x100418c07  mov     rax, cs:__imp_?sm_cpuCount@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_cpuCount
0x100418c0e  mov     ebx, [rax]
0x100418c10  mov     rax, cs:__imp_?SOS_OS_LPperPP@@3KA; ulong SOS_OS_LPperPP
0x100418c17  mov     r10d, [rax]
0x100418c1a  mov     rax, cs:__imp_?SOS_OS_LPPerCore@@3KA; ulong SOS_OS_LPPerCore
0x100418c21  mov     r8d, [rax]
0x100418c24  mov     rax, cs:__imp_?sm_cpuCount@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_cpuCount
0x100418c2b  mov     eax, [rax]
0x100418c2d  mov     rcx, cs:__imp_?SOS_OS_LPperPP@@3KA; ulong SOS_OS_LPperPP
0x100418c34  xor     edx, edx
0x100418c36  div     dword ptr [rcx]
0x100418c38  mov     ecx, eax
0x100418c3a  mov     eax, r10d
0x100418c3d  xor     edx, edx
0x100418c3f  div     r8d
0x100418c42  mov     dword ptr [rsp+810h+var_7E8], r9d
0x100418c47  mov     [rsp+810h+var_7F0], ebx
0x100418c4b  mov     r9d, r10d
0x100418c4e  mov     r8d, eax
0x100418c51  mov     edx, ecx
0x100418c53  mov     ecx, r11d; unsigned int
0x100418c56  call    ?scierrlog@@YAXKZZ; scierrlog(ulong,...)
0x100418c5b  mov     rax, cs:__imp_?s_pServerConf@@3PEAVIServerConfiguration@@EA; IServerConfiguration * s_pServerConf
0x100418c62  mov     rcx, [rax]
0x100418c65  mov     rax, [rcx]
0x100418c68  call    qword ptr [rax+1F8h]
0x100418c6e  lea     rcx, [rax+130h]
0x100418c75  call    cs:__imp_?GetCPUCount@SystemAffinity@@QEBAIXZ; SystemAffinity::GetCPUCount(void)
0x100418c7b  test    eax, eax
0x100418c7d  jz      short loc_100418CDB
0x100418c7f  call    cs:__imp_?Instance@OsNumaConfig@@SAPEAV1@XZ; OsNumaConfig::Instance(void)
0x100418c85  mov     rsi, rax
0x100418c88  lea     rdx, [rbp+710h+var_730]
0x100418c8c  mov     rcx, cs:__imp_?sm_AffinityMask@SOS_PublicGlobals@@2VSystemAffinity@@A; SystemAffinity SOS_PublicGlobals::sm_AffinityMask
0x100418c93  call    cs:__imp_?SafeCopy@SystemAffinity@@QEBA?AV1@XZ; SystemAffinity::SafeCopy(void)
0x100418c99  mov     rdi, [rsi]
0x100418c9c  lea     rdx, [rbp+710h+var_750]
0x100418ca0  lea     rcx, [rbp+710h+var_730]
0x100418ca4  call    cs:__imp_?GetFirstGroupSet@SystemAffinity@@QEBA?BVGroupAffinity@@XZ; SystemAffinity::GetFirstGroupSet(void)
0x100418caa  mov     rbx, rax
0x100418cad  call    cs:__imp_GetCurrentThread
0x100418cb3  mov     rdx, rax
0x100418cb6  xor     r9d, r9d
0x100418cb9  mov     r8, rbx
0x100418cbc  mov     rcx, rsi
0x100418cbf  call    qword ptr [rdi+30h]
0x100418cc2  test    eax, eax
0x100418cc4  jnz     short loc_100418CDB
0x100418cc6  call    cs:__imp_GetLastError
0x100418ccc  mov     edx, eax
0x100418cce  lea     rcx, aSetthreadaffin; "SetThreadAffinity failed: %d\n"
0x100418cd5  call    ?LogSystemMetadata@@YAXPEB_WZZ; LogSystemMetadata(wchar_t const *,...)
0x100418cda  nop
0x100418cdb  lea     rcx, [rbp+710h+var_6B0]
0x100418cdf  call    cs:__imp_??1AffinityAutoConfiguration@@QEAA@XZ; AffinityAutoConfiguration::~AffinityAutoConfiguration(void)
0x100418ce5  mov     rcx, [rbp+710h+var_10]
0x100418cec  xor     rcx, rsp; StackCookie
0x100418cef  call    __security_check_cookie
0x100418cf4  lea     r11, [rsp+810h+var_s0]
0x100418cfc  mov     rbx, [r11+10h]
0x100418d00  mov     rsi, [r11+18h]
0x100418d04  mov     rdi, [r11+20h]
0x100418d08  mov     rsp, r11
0x100418d0b  pop     rbp
0x100418d0c  retn
```
