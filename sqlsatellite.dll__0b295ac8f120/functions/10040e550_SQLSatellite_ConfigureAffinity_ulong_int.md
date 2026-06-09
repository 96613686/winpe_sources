# SQLSatellite_ConfigureAffinity(ulong,int)

- ea: `0x10040e550`
- end: `0x10040e8b0`
- name: `?SQLSatellite_ConfigureAffinity@@YA?AW4SOS_RESULT@@KH@Z`
- size: `864`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x10040e530`

## callees

- `0x10040e550`
- `0x100486af0`

## import_xrefs

- `KERNEL32!GetCurrentThread` at `0x10040e855`
- `KERNEL32!GetCurrentThread` at `0x10040e855`
- `KERNEL32!GetSystemInfo` at `0x10040e580`
- `KERNEL32!GetSystemInfo` at `0x10040e580`
- `KERNEL32!GetLastError` at `0x10040e878`
- `KERNEL32!GetLastError` at `0x10040e878`
- `sqldk!?GetFirstGroupSet@SystemAffinity@@QEBA?BVGroupAffinity@@XZ` at `0x10040e84c`
- `sqldk!?GetFirstGroupSet@SystemAffinity@@QEBA?BVGroupAffinity@@XZ` at `0x10040e84c`
- `sqldk!?Instance@OsNumaConfig@@SAPEAV1@XZ` at `0x10040e838`
- `sqldk!?Instance@OsNumaConfig@@SAPEAV1@XZ` at `0x10040e838`
- `sqldk!?SetProcessAffinity@SOS_OS@@SA?AW4SOS_RESULT@@VSystemAffinity@@W4OS_AFFINITY@1@@Z` at `0x10040e7bc`
- `sqldk!?SetProcessAffinity@SOS_OS@@SA?AW4SOS_RESULT@@VSystemAffinity@@W4OS_AFFINITY@1@@Z` at `0x10040e7bc`
- `sqldk!?SetMaskGivenGroup@SystemAffinity@@QEAAXG_K@Z` at `0x10040e72f`
- `sqldk!?SetMaskGivenGroup@SystemAffinity@@QEAAXG_K@Z` at `0x10040e72f`
- `sqldk!?GetMaskGivenGroup@SystemAffinity@@QEBA_KG@Z` at `0x10040e697`
- `sqldk!?GetMaskGivenGroup@SystemAffinity@@QEBA_KG@Z` at `0x10040e697`
- `sqldk!?GetGroupCount@SystemAffinity@@SAGXZ` at `0x10040e641`
- `sqldk!?GetGroupCount@SystemAffinity@@SAGXZ` at `0x10040e641`
- `sqldk!?GetCPUCount@SystemAffinity@@QEBAIXZ` at `0x10040e625`
- `sqldk!?GetCPUCount@SystemAffinity@@QEBAIXZ` at `0x10040e637`
- `sqldk!?GetCPUCount@SystemAffinity@@QEBAIXZ` at `0x10040e625`
- `sqldk!?GetCPUCount@SystemAffinity@@QEBAIXZ` at `0x10040e637`
- `sqldk!?LoadHardwareConfig@SOS_OS@@SAXAEBVSystemAffinity@@@Z` at `0x10040e5f8`
- `sqldk!?LoadHardwareConfig@SOS_OS@@SAXAEBVSystemAffinity@@@Z` at `0x10040e5f8`
- `sqldk!?IsEmpty@SystemAffinity@@QEBAHXZ` at `0x10040e5ea`
- `sqldk!?IsEmpty@SystemAffinity@@QEBAHXZ` at `0x10040e5ea`
- `sqldk!?GetOsProcessAffinity@SOS_OS@@SAHPEAVSystemAffinity@@@Z` at `0x10040e5dc`
- `sqldk!?GetOsProcessAffinity@SOS_OS@@SAHPEAVSystemAffinity@@@Z` at `0x10040e5dc`
- `sqldk!??0SystemAffinity@@QEAA@XZ` at `0x10040e5d2`
- `sqldk!??0SystemAffinity@@QEAA@XZ` at `0x10040e5d2`
- `sqldk!?IsWinJobAffinityLimited@OsNumaConfig@@SAHXZ` at `0x10040e5c4`
- `sqldk!?IsWinJobAffinityLimited@OsNumaConfig@@SAHXZ` at `0x10040e5c4`
- `sqldk!?Attach@FakeOsNumaConfig@@UEAAXXZ` at `0x10040e5bc`
- `sqldk!?Attach@FakeOsNumaConfig@@UEAAXXZ` at `0x10040e5bc`
- `sqldk!?SetNode@FakeOsNumaConfig@@QEAAXGG_K@Z` at `0x10040e5a8`
- `sqldk!?SetNode@FakeOsNumaConfig@@QEAAXGG_K@Z` at `0x10040e5a8`
- `sqldk!?NotifyTraceOn@SOS_Tracing@@SAXK@Z` at `0x10040e766`
- `sqldk!?NotifyTraceOn@SOS_Tracing@@SAXK@Z` at `0x10040e766`
- `sqldk!?SafeCopy@SystemAffinity@@QEBA?AV1@XZ` at `0x10040e613`
- `sqldk!?SafeCopy@SystemAffinity@@QEBA?AV1@XZ` at `0x10040e613`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x10040e7cd`
- `sqldk!?SOS_OS_LogUnlocalizedRoutine@@3P6AXPEB_WZZEA` at `0x10040e86e`
- `sqldk!?sm_AffinityMask@SOS_PublicGlobals@@2VSystemAffinity@@A` at `0x10040e600`

## string_xrefs

- `0x10040e880`: `SetThreadAffinity failed: %d\n`

## pseudocode

```c
__int64 __fastcall SQLSatellite_ConfigureAffinity(unsigned int a1, int a2)
{
  DWORD i; // ebx
  char v4; // bl
  unsigned int v5; // edi
  int j; // esi
  unsigned __int64 MaskGivenGroup; // r9
  unsigned __int64 v8; // rbx
  __int64 v9; // rcx
  unsigned int k; // edx
  __int64 v11; // rax
  __int64 result; // rax
  unsigned int v13; // r14d
  _OWORD *v14; // rax
  __int64 *v15; // rdi
  __int64 v16; // rsi
  __int64 FirstGroupSet; // rbx
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  _OWORD v20[8]; // [rsp+20h] [rbp-E0h] BYREF
  _SYSTEM_INFO SystemInfo; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v22; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v23; // [rsp+E0h] [rbp-20h]
  __int128 v24; // [rsp+F0h] [rbp-10h]
  __int128 v25; // [rsp+100h] [rbp+0h]
  __int128 v26; // [rsp+110h] [rbp+10h]
  __int128 v27; // [rsp+120h] [rbp+20h]
  __int128 v28; // [rsp+130h] [rbp+30h]
  __int128 v29; // [rsp+140h] [rbp+40h]
  _BYTE v30[16]; // [rsp+150h] [rbp+50h] BYREF
  _BYTE v31[128]; // [rsp+160h] [rbp+60h] BYREF

  if ( a2 )
  {
    GetSystemInfo(&SystemInfo);
    for ( i = 0; i < SystemInfo.dwNumberOfProcessors; ++i )
      FakeOsNumaConfig::SetNode((FakeOsNumaConfig *)qword_10052E450, i, 0, 1LL << i);
    FakeOsNumaConfig::Attach((FakeOsNumaConfig *)qword_10052E450);
  }
  v4 = 0;
  if ( (unsigned int)OsNumaConfig::IsWinJobAffinityLimited() )
  {
    SystemAffinity::SystemAffinity((SystemAffinity *)v31);
    if ( SOS_OS::GetOsProcessAffinity((struct SystemAffinity *)v31) )
    {
      if ( !SystemAffinity::IsEmpty((SystemAffinity *)v31) )
      {
        SOS_OS::LoadHardwareConfig((const struct SystemAffinity *)v31);
        v4 = 1;
      }
    }
  }
  SystemAffinity::SafeCopy(SOS_PublicGlobals::sm_AffinityMask, &v22);
  if ( a1 && SystemAffinity::GetCPUCount((SystemAffinity *)&v22) > a1 )
  {
    v5 = SystemAffinity::GetCPUCount((SystemAffinity *)&v22) - a1;
    for ( j = SystemAffinity::GetGroupCount() - 1; v5; LOWORD(j) = j - 1 )
    {
      MaskGivenGroup = SystemAffinity::GetMaskGivenGroup((SystemAffinity *)&v22, j);
      v8 = (0x101010101010101LL
          * ((((MaskGivenGroup - ((MaskGivenGroup >> 1) & 0x5555555555555555LL)) & 0x3333333333333333LL)
            + (((MaskGivenGroup - ((MaskGivenGroup >> 1) & 0x5555555555555555LL)) >> 2) & 0x3333333333333333LL)
            + ((((MaskGivenGroup - ((MaskGivenGroup >> 1) & 0x5555555555555555LL)) & 0x3333333333333333LL)
              + (((MaskGivenGroup - ((MaskGivenGroup >> 1) & 0x5555555555555555LL)) >> 2) & 0x3333333333333333LL)) >> 4))
           & 0xF0F0F0F0F0F0F0FLL)) >> 56;
      if ( v8 >= v5 )
        LODWORD(v8) = v5;
      if ( (_DWORD)v8 )
      {
        _mm_lfence();
        v9 = 0;
        for ( k = 1; ; ++k )
        {
          v11 = MaskGivenGroup;
          if ( v9 )
            v11 = MaskGivenGroup & ~(v9 | (v9 - 1));
          v9 = v11 & ~(v11 - 1);
          if ( !v9 || k >= (unsigned int)v8 )
            break;
        }
        SystemAffinity::SetMaskGivenGroup((SystemAffinity *)&v22, j, MaskGivenGroup & ~(v9 | (v9 - 1)));
        v5 -= v8;
      }
    }
  }
  else if ( !v4 )
  {
    goto LABEL_26;
  }
  SOS_Tracing::NotifyTraceOn(0x1F51u);
LABEL_26:
  v20[0] = v22;
  v20[1] = v23;
  v20[2] = v24;
  v20[3] = v25;
  v20[4] = v26;
  v20[5] = v27;
  v20[6] = v28;
  v20[7] = v29;
  result = SOS_OS::SetProcessAffinity(v20, 3);
  v13 = result;
  if ( !(_DWORD)result )
  {
    v14 = (_OWORD *)(*(__int64 (__fastcall **)(struct IServerConfiguration *))(*(_QWORD *)s_pServerConf + 504LL))(s_pServerConf);
    v14[19] = v22;
    v14[20] = v23;
    v14[21] = v24;
    v14[22] = v25;
    v14[23] = v26;
    v14[24] = v27;
    v14[25] = v28;
    v14[26] = v29;
    v15 = (__int64 *)OsNumaConfig::Instance();
    v16 = *v15;
    FirstGroupSet = SystemAffinity::GetFirstGroupSet(&v22, v30);
    CurrentThread = GetCurrentThread();
    if ( !(*(unsigned int (__fastcall **)(__int64 *, HANDLE, __int64, _QWORD))(v16 + 48))(
            v15,
            CurrentThread,
            FirstGroupSet,
            0) )
    {
      LastError = GetLastError();
      SOS_OS_LogUnlocalizedRoutine(L"SetThreadAffinity failed: %d\n", LastError);
    }
    return v13;
  }
  return result;
}

```

## disassembly

```asm
0x10040e550  push    rbp
0x10040e552  push    rbx
0x10040e553  push    rsi
0x10040e554  push    r14
0x10040e556  lea     rbp, [rsp-0F8h]
0x10040e55e  sub     rsp, 1F8h
0x10040e565  mov     rax, cs:__security_cookie
0x10040e56c  xor     rax, rsp
0x10040e56f  mov     [rbp+110h+var_30], rax
0x10040e576  mov     esi, ecx
0x10040e578  test    edx, edx
0x10040e57a  jz      short loc_10040E5C2
0x10040e57c  lea     rcx, [rbp+110h+SystemInfo]; lpSystemInfo
0x10040e580  call    cs:__imp_GetSystemInfo
0x10040e586  xor     ebx, ebx
0x10040e588  cmp     [rbp+110h+SystemInfo.dwNumberOfProcessors], ebx
0x10040e58b  jbe     short loc_10040E5B5
0x10040e58d  nop     dword ptr [rax]
0x10040e590  mov     ecx, ebx
0x10040e592  mov     r9d, 1
0x10040e598  shl     r9, cl
0x10040e59b  xor     r8d, r8d
0x10040e59e  lea     rcx, qword_10052E450
0x10040e5a5  movzx   edx, bx
0x10040e5a8  call    cs:__imp_?SetNode@FakeOsNumaConfig@@QEAAXGG_K@Z; FakeOsNumaConfig::SetNode(ushort,ushort,unsigned __int64)
0x10040e5ae  inc     ebx
0x10040e5b0  cmp     ebx, [rbp+110h+SystemInfo.dwNumberOfProcessors]
0x10040e5b3  jb      short loc_10040E590
0x10040e5b5  lea     rcx, qword_10052E450
0x10040e5bc  call    cs:__imp_?Attach@FakeOsNumaConfig@@UEAAXXZ; FakeOsNumaConfig::Attach(void)
0x10040e5c2  xor     bl, bl
0x10040e5c4  call    cs:__imp_?IsWinJobAffinityLimited@OsNumaConfig@@SAHXZ; OsNumaConfig::IsWinJobAffinityLimited(void)
0x10040e5ca  test    eax, eax
0x10040e5cc  jz      short loc_10040E600
0x10040e5ce  lea     rcx, [rbp+110h+var_B0]
0x10040e5d2  call    cs:__imp_??0SystemAffinity@@QEAA@XZ; SystemAffinity::SystemAffinity(void)
0x10040e5d8  lea     rcx, [rbp+110h+var_B0]
0x10040e5dc  call    cs:__imp_?GetOsProcessAffinity@SOS_OS@@SAHPEAVSystemAffinity@@@Z; SOS_OS::GetOsProcessAffinity(SystemAffinity *)
0x10040e5e2  test    eax, eax
0x10040e5e4  jz      short loc_10040E600
0x10040e5e6  lea     rcx, [rbp+110h+var_B0]
0x10040e5ea  call    cs:__imp_?IsEmpty@SystemAffinity@@QEBAHXZ; SystemAffinity::IsEmpty(void)
0x10040e5f0  test    eax, eax
0x10040e5f2  jnz     short loc_10040E600
0x10040e5f4  lea     rcx, [rbp+110h+var_B0]
0x10040e5f8  call    cs:__imp_?LoadHardwareConfig@SOS_OS@@SAXAEBVSystemAffinity@@@Z; SOS_OS::LoadHardwareConfig(SystemAffinity const &)
0x10040e5fe  mov     bl, 1
0x10040e600  mov     rcx, cs:__imp_?sm_AffinityMask@SOS_PublicGlobals@@2VSystemAffinity@@A; SystemAffinity SOS_PublicGlobals::sm_AffinityMask
0x10040e607  lea     rdx, [rbp+110h+var_140]
0x10040e60b  mov     [rsp+210h+arg_0], rdi
0x10040e613  call    cs:__imp_?SafeCopy@SystemAffinity@@QEBA?AV1@XZ; SystemAffinity::SafeCopy(void)
0x10040e619  test    esi, esi
0x10040e61b  jz      loc_10040E75D
0x10040e621  lea     rcx, [rbp+110h+var_140]
0x10040e625  call    cs:__imp_?GetCPUCount@SystemAffinity@@QEBAIXZ; SystemAffinity::GetCPUCount(void)
0x10040e62b  cmp     eax, esi
0x10040e62d  jbe     loc_10040E75D
0x10040e633  lea     rcx, [rbp+110h+var_140]
0x10040e637  call    cs:__imp_?GetCPUCount@SystemAffinity@@QEBAIXZ; SystemAffinity::GetCPUCount(void)
0x10040e63d  mov     edi, eax
0x10040e63f  sub     edi, esi
0x10040e641  call    cs:__imp_?GetGroupCount@SystemAffinity@@SAGXZ; SystemAffinity::GetGroupCount(void)
0x10040e647  lea     esi, [rax-1]
0x10040e64a  test    edi, edi
0x10040e64c  jz      loc_10040E761
0x10040e652  mov     [rsp+210h+arg_8], r12
0x10040e65a  mov     r14d, 0FFFFh
0x10040e660  mov     [rsp+210h+arg_10], r13
0x10040e668  mov     r12, 5555555555555555h
0x10040e672  mov     [rsp+210h+var_20], r15
0x10040e67a  mov     r13, 0F0F0F0F0F0F0F0Fh
0x10040e684  mov     r15, 3333333333333333h
0x10040e68e  xchg    ax, ax
0x10040e690  movzx   edx, si
0x10040e693  lea     rcx, [rbp+110h+var_140]
0x10040e697  call    cs:__imp_?GetMaskGivenGroup@SystemAffinity@@QEBA_KG@Z; SystemAffinity::GetMaskGivenGroup(ushort)
0x10040e69d  mov     rcx, rax
0x10040e6a0  mov     rdx, rax
0x10040e6a3  shr     rcx, 1
0x10040e6a6  mov     r9, rax
0x10040e6a9  and     rcx, r12
0x10040e6ac  mov     rax, 101010101010101h
0x10040e6b6  sub     rdx, rcx
0x10040e6b9  mov     rcx, rdx
0x10040e6bc  and     rdx, r15
0x10040e6bf  shr     rcx, 2
0x10040e6c3  and     rcx, r15
0x10040e6c6  add     rcx, rdx
0x10040e6c9  mov     rbx, rcx
0x10040e6cc  shr     rbx, 4
0x10040e6d0  add     rbx, rcx
0x10040e6d3  and     rbx, r13
0x10040e6d6  imul    rbx, rax
0x10040e6da  mov     eax, edi
0x10040e6dc  shr     rbx, 38h
0x10040e6e0  cmp     rbx, rax
0x10040e6e3  cmovnb  ebx, edi
0x10040e6e6  test    ebx, ebx
0x10040e6e8  jz      short loc_10040E737
0x10040e6ea  lfence
0x10040e6ed  xor     ecx, ecx
0x10040e6ef  lea     edx, [rcx+1]
0x10040e6f2  mov     rax, r9
0x10040e6f5  test    rcx, rcx
0x10040e6f8  jz      short loc_10040E707
0x10040e6fa  lea     rax, [rcx-1]
0x10040e6fe  or      rax, rcx
0x10040e701  not     rax
0x10040e704  and     rax, r9
0x10040e707  lea     rcx, [rax-1]
0x10040e70b  not     rcx
0x10040e70e  and     rcx, rax
0x10040e711  jz      short loc_10040E71B
0x10040e713  cmp     edx, ebx
0x10040e715  jnb     short loc_10040E71B
0x10040e717  inc     edx
0x10040e719  jmp     short loc_10040E6F2
0x10040e71b  lea     r8, [rcx-1]
0x10040e71f  movzx   edx, si
0x10040e722  or      r8, rcx
0x10040e725  lea     rcx, [rbp+110h+var_140]
0x10040e729  not     r8
0x10040e72c  and     r8, r9
0x10040e72f  call    cs:__imp_?SetMaskGivenGroup@SystemAffinity@@QEAAXG_K@Z; SystemAffinity::SetMaskGivenGroup(ushort,unsigned __int64)
0x10040e735  sub     edi, ebx
0x10040e737  add     si, r14w
0x10040e73b  test    edi, edi
0x10040e73d  jnz     loc_10040E690
0x10040e743  mov     r15, [rsp+210h+var_20]
0x10040e74b  mov     r13, [rsp+210h+arg_10]
0x10040e753  mov     r12, [rsp+210h+arg_8]
0x10040e75b  jmp     short loc_10040E761
0x10040e75d  test    bl, bl
0x10040e75f  jz      short loc_10040E76C
0x10040e761  mov     ecx, 1F51h
0x10040e766  call    cs:__imp_?NotifyTraceOn@SOS_Tracing@@SAXK@Z; SOS_Tracing::NotifyTraceOn(ulong)
0x10040e76c  movaps  xmm0, [rbp+110h+var_140]
0x10040e770  lea     rcx, [rsp+210h+var_1F0]
0x10040e775  movaps  xmm1, [rbp+110h+var_130]
0x10040e779  mov     edx, 3
0x10040e77e  movaps  [rsp+210h+var_1F0], xmm0
0x10040e783  movaps  xmm0, [rbp+110h+var_120]
0x10040e787  movaps  [rsp+210h+var_1E0], xmm1
0x10040e78c  movaps  xmm1, [rbp+110h+var_110]
0x10040e790  movaps  [rsp+210h+var_1D0], xmm0
0x10040e795  movaps  xmm0, [rbp+110h+var_100]
0x10040e799  movaps  [rsp+210h+var_1C0], xmm1
0x10040e79e  movaps  xmm1, [rbp+110h+var_F0]
0x10040e7a2  movaps  [rsp+210h+var_1B0], xmm0
0x10040e7a7  movaps  xmm0, [rbp+110h+var_E0]
0x10040e7ab  movaps  [rsp+210h+var_1A0], xmm1
0x10040e7b0  movaps  xmm1, [rbp+110h+var_D0]
0x10040e7b4  movaps  [rbp+110h+var_190], xmm0
0x10040e7b8  movaps  [rbp+110h+var_180], xmm1
0x10040e7bc  call    cs:__imp_?SetProcessAffinity@SOS_OS@@SA?AW4SOS_RESULT@@VSystemAffinity@@W4OS_AFFINITY@1@@Z; SOS_OS::SetProcessAffinity(SystemAffinity,SOS_OS::OS_AFFINITY)
0x10040e7c2  mov     r14d, eax
0x10040e7c5  test    eax, eax
0x10040e7c7  jnz     loc_10040E88C
0x10040e7cd  mov     rcx, cs:__imp_?s_pServerConf@@3PEAVIServerConfiguration@@EA; IServerConfiguration * s_pServerConf
0x10040e7d4  mov     rcx, [rcx]
0x10040e7d7  mov     rdx, [rcx]
0x10040e7da  call    qword ptr [rdx+1F8h]
0x10040e7e0  movaps  xmm0, [rbp+110h+var_140]
0x10040e7e4  movups  xmmword ptr [rax+130h], xmm0
0x10040e7eb  movaps  xmm1, [rbp+110h+var_130]
0x10040e7ef  movups  xmmword ptr [rax+140h], xmm1
0x10040e7f6  movaps  xmm0, [rbp+110h+var_120]
0x10040e7fa  movups  xmmword ptr [rax+150h], xmm0
0x10040e801  movaps  xmm1, [rbp+110h+var_110]
0x10040e805  movups  xmmword ptr [rax+160h], xmm1
0x10040e80c  movaps  xmm0, [rbp+110h+var_100]
0x10040e810  movups  xmmword ptr [rax+170h], xmm0
0x10040e817  movaps  xmm1, [rbp+110h+var_F0]
0x10040e81b  movups  xmmword ptr [rax+180h], xmm1
0x10040e822  movaps  xmm0, [rbp+110h+var_E0]
0x10040e826  movups  xmmword ptr [rax+190h], xmm0
0x10040e82d  movaps  xmm1, [rbp+110h+var_D0]
0x10040e831  movups  xmmword ptr [rax+1A0h], xmm1
0x10040e838  call    cs:__imp_?Instance@OsNumaConfig@@SAPEAV1@XZ; OsNumaConfig::Instance(void)
0x10040e83e  lea     rdx, [rbp+110h+var_C0]
0x10040e842  mov     rdi, rax
0x10040e845  lea     rcx, [rbp+110h+var_140]
0x10040e849  mov     rsi, [rax]
0x10040e84c  call    cs:__imp_?GetFirstGroupSet@SystemAffinity@@QEBA?BVGroupAffinity@@XZ; SystemAffinity::GetFirstGroupSet(void)
0x10040e852  mov     rbx, rax
0x10040e855  call    cs:__imp_GetCurrentThread
0x10040e85b  xor     r9d, r9d
0x10040e85e  mov     r8, rbx
0x10040e861  mov     rdx, rax
0x10040e864  mov     rcx, rdi
0x10040e867  call    qword ptr [rsi+30h]
0x10040e86a  test    eax, eax
0x10040e86c  jnz     short loc_10040E889
0x10040e86e  mov     rax, cs:__imp_?SOS_OS_LogUnlocalizedRoutine@@3P6AXPEB_WZZEA; void (*SOS_OS_LogUnlocalizedRoutine)(wchar_t const *,...)
0x10040e875  mov     rbx, [rax]
0x10040e878  call    cs:__imp_GetLastError
0x10040e87e  mov     edx, eax
0x10040e880  lea     rcx, aSetthreadaffin; "SetThreadAffinity failed: %d\n"
0x10040e887  call    rbx
0x10040e889  mov     eax, r14d
0x10040e88c  mov     rdi, [rsp+210h+arg_0]
0x10040e894  mov     rcx, [rbp+110h+var_30]
0x10040e89b  xor     rcx, rsp; StackCookie
0x10040e89e  call    __security_check_cookie
0x10040e8a3  add     rsp, 1F8h
0x10040e8aa  pop     r14
0x10040e8ac  pop     rsi
0x10040e8ad  pop     rbx
0x10040e8ae  pop     rbp
0x10040e8af  retn
```
