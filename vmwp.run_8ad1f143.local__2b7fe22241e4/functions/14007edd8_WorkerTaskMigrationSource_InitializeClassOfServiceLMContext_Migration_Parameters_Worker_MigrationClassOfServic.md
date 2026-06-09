# WorkerTaskMigrationSource::InitializeClassOfServiceLMContext(Migration::Parameters::Worker::MigrationClassOfServiceParams)

- ea: `0x14007edd8`
- end: `0x14007f404`
- name: `?InitializeClassOfServiceLMContext@WorkerTaskMigrationSource@@AEAAXUMigrationClassOfServiceParams@Worker@Parameters@Migration@@@Z`
- size: `1580`
- prototype: ``
- caller_count: `1`
- callee_count: `24`
- tags: `reparse_path, registry_config, loader_planting, service_task`

## callers

- `0x14021d49c`

## callees

- `0x140031ca8`
- `0x140042260`
- `0x14005497c`
- `0x14005b648`
- `0x140066780`
- `0x14006af58`
- `0x14007e5a0`
- `0x14007edd8`
- `0x14007f410`
- `0x14007f46c`
- `0x1400c5a3c`
- `0x140111090`
- `0x14011ffe8`
- `0x140120084`
- `0x1401200b0`
- `0x140132960`
- `0x14013361c`
- `0x14014d720`
- `0x14014db70`
- `0x14014dba0`
- `0x140219bc4`
- `0x14021bcc8`
- `0x14021c980`
- `0x1402c2010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x14007ef78`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x14007efb6`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x14007ef78`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x14007efb6`
- `vid!VidOpenStatisticsHandle` at `0x14007ee56`
- `vid!VidOpenStatisticsHandle` at `0x14007ee56`
- `vid!VidGetSystemInformation` at `0x14007f000`
- `vid!VidGetSystemInformation` at `0x14007f099`
- `vid!VidGetSystemInformation` at `0x14007f000`
- `vid!VidGetSystemInformation` at `0x14007f099`

## string_xrefs

- `0x14007eeed`: `onecore\vm\worker\migration\workertaskmigrationsource.cpp`
- `0x14007eed7`: `Class Of Service Index is undefined`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall WorkerTaskMigrationSource::InitializeClassOfServiceLMContext(__int64 a1, _BOOL8 a2)
{
  __int64 v2; // r14
  __int64 v4; // rcx
  void *v5; // rbx
  __int64 ClassOfServiceIndex; // rax
  int v7; // eax
  int MbaInitialThrottlePercentage; // r15d
  __int64 MbaThrottleStrategy; // rax
  char **v10; // rcx
  int v11; // eax
  char **v12; // rcx
  const char *v13; // r9
  const char *v14; // r9
  unsigned int v15; // eax
  char v16; // r8
  __int64 v17; // rcx
  unsigned __int64 v18; // rdx
  __int64 v19; // rcx
  double v20; // xmm1_8
  int v21; // eax
  const struct Vml::ExceptionTraceParameters *v22; // r8
  const char *v23; // rax
  int v25; // [rsp+20h] [rbp-518h]
  char *v26; // [rsp+30h] [rbp-508h]
  char *v27; // [rsp+30h] [rbp-508h]
  __int64 v28; // [rsp+38h] [rbp-500h]
  void *v29; // [rsp+50h] [rbp-4E8h] BYREF
  _BYTE *v30; // [rsp+58h] [rbp-4E0h]
  _BYTE v31[8]; // [rsp+60h] [rbp-4D8h] BYREF
  _BYTE v32[32]; // [rsp+68h] [rbp-4D0h] BYREF
  _BOOL8 v33; // [rsp+88h] [rbp-4B0h]
  __int128 v34; // [rsp+90h] [rbp-4A8h] BYREF
  char *v35[3]; // [rsp+A0h] [rbp-498h] BYREF
  unsigned __int64 v36; // [rsp+B8h] [rbp-480h]
  __int128 v37; // [rsp+C0h] [rbp-478h] BYREF
  char *v38[2]; // [rsp+D0h] [rbp-468h]
  __int128 v39; // [rsp+E0h] [rbp-458h] BYREF
  _QWORD v40[130]; // [rsp+F0h] [rbp-448h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+538h] [rbp+0h]

  v2 = a2;
  v33 = a2;
  v34 = 0;
  VmMigrationSettings::VmMigrationSettings((VmMigrationSettings *)&v34, a2);
  LOBYTE(v4) = VmMigrationSettings::IsMemoryBandwidthAllocationEnabled((VmMigrationSettings *)&v34);
  if ( *(_BYTE *)(v2 + 9) )
    LOBYTE(v4) = *(_BYTE *)(v2 + 8);
  v30 = (_BYTE *)(a1 + 696);
  *(_BYTE *)(a1 + 696) = v4;
  if ( (_BYTE)v4 )
  {
    v5 = (void *)VidOpenStatisticsHandle(v4);
    v29 = v5;
    v37 = 0;
    *(_OWORD *)v38 = 0;
    v39 = 0;
    memset_0(v40, 0, 0x408u);
    try
    {
      ClassOfServiceIndex = VmMigrationSettings::GetClassOfServiceIndex(&v34, v31);
      if ( *(_BYTE *)(ClassOfServiceIndex + 4) )
        v7 = *(_DWORD *)ClassOfServiceIndex;
      else
        v7 = -1;
      if ( *(_BYTE *)(v2 + 4) )
        v7 = *(_DWORD *)v2;
      *(_DWORD *)(a1 + 700) = v7;
      wil::details::in1diag3::Throw_HrIfMsg(
        retaddr,
        (void *)0x1137,
        (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationsource.cpp",
        (const char *)0x8007000DLL,
        v7 == -1,
        (bool)"Class Of Service Index is undefined",
        v26);
      MbaInitialThrottlePercentage = VmMigrationSettings::GetMbaInitialThrottlePercentage((VmMigrationSettings *)&v34);
      if ( *(_BYTE *)(v2 + 60) )
        MbaInitialThrottlePercentage = *(_DWORD *)(v2 + 56);
      MbaThrottleStrategy = VmMigrationSettings::GetMbaThrottleStrategy(&v34, v32);
      vmstd::optional<std::wstring>::value_or<std::wstring>(v2 + 16, v35, MbaThrottleStrategy);
      std::wstring::_Tidy_deallocate(v32);
      v10 = v35;
      if ( v36 > 7 )
        v10 = (char **)v35[0];
      if ( (unsigned int)_o__wcsnicmp(v10, L"Linear", 7) )
      {
        v12 = v35;
        if ( v36 > 7 )
          v12 = (char **)v35[0];
        if ( (unsigned int)_o__wcsnicmp(v12, L"Adaptive", 9) )
        {
          v23 = (const char *)v35;
          if ( v36 > 7 )
            v23 = v35[0];
          wil::details::in1diag3::Throw_HrMsg(
            retaddr,
            (void *)0x1146,
            (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationsource.cpp",
            (const char *)0x80070057LL,
            (int)"Invalid MBA throttle strategy:%ws",
            v23);
        }
        v11 = 2;
      }
      else
      {
        v11 = 1;
      }
      *(_DWORD *)(a1 + 704) = v11;
      if ( !(unsigned int)VidGetSystemInformation(v5, 3, 0) )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x114E,
          (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationsource.cpp",
          v13);
      wil::details::in1diag3::Throw_HrIfMsg(
        retaddr,
        (void *)0x1153,
        (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationsource.cpp",
        (const char *)0x80070032LL,
        (v37 & 0x20) == 0,
        (bool)"MBA is not supported on this system",
        0);
      LODWORD(v39) = 1;
      if ( !(unsigned int)VidGetSystemInformation(v5, 4, &v39) )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x115E,
          (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationsource.cpp",
          v14);
      wil::details::in1diag3::Throw_HrIfMsg(
        retaddr,
        (void *)0x1164,
        (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationsource.cpp",
        (const char *)0x80004005LL,
        HIDWORD(v38[0]) != LODWORD(v40[0]),
        (bool)"The number of MBA slots is not equal to the number of HV resource control value count. MemoryBandwidthSlot"
              "s:%u, HVResourceControlNumValues:%u",
        (const char *)HIDWORD(v38[0]),
        LODWORD(v40[0]));
      v15 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(*(_QWORD *)(a1 + 16) + 1040LL) + 680LL))(*(_QWORD *)(*(_QWORD *)(a1 + 16) + 1040LL));
      *(_DWORD *)(a1 + 708) = v15;
      v16 = *(_DWORD *)(a1 + 700) >= HIDWORD(v38[0]) || v15 >= HIDWORD(v38[0]);
      LODWORD(v28) = v15;
      LODWORD(v27) = *(_DWORD *)(a1 + 700);
      wil::details::in1diag3::Throw_HrIfMsg(
        retaddr,
        (void *)0x116E,
        (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationsource.cpp",
        (const char *)0x80004005LL,
        v16,
        (bool)"The LM CLOS or VM allocation id is beyond the MBA slots. LMClosIndex:%u, OriginalVMAllocationId:%u, Memory"
              "BandwidthSlots:%u",
        v27,
        v28,
        HIDWORD(v38[0]));
      v18 = v40[*(unsigned int *)(a1 + 708) + 1];
      *(_QWORD *)(a1 + 728) = v18;
      *(_BYTE *)(a1 + 712) = BYTE4(v38[1]) & 1;
      *(_QWORD *)(a1 + 720) = LODWORD(v38[1]);
      if ( MbaInitialThrottlePercentage )
        v18 = WorkerTaskMigrationSource::CalculateMbaThrottleValue(
                (WorkerTaskMigrationSource *)a1,
                (double)MbaInitialThrottlePercentage);
      *(_QWORD *)(a1 + 752) = v18;
      if ( *(_DWORD *)(a1 + 704) == 1 )
      {
        v19 = *(_QWORD *)(a1 + 720) - v18;
        if ( v19 < 0 )
          v20 = (double)(int)(v19 & 1 | ((unsigned __int64)v19 >> 1))
              + (double)(int)(v19 & 1 | ((unsigned __int64)v19 >> 1));
        else
          v20 = (double)(int)v19;
        *(_QWORD *)(a1 + 744) = WorkerTaskMigrationSource::GetNormalizedMBAThrottleValue(
                                  (WorkerTaskMigrationSource *)a1,
                                  v20 / (double)(*(_DWORD *)(a1 + 672) - *(_DWORD *)(a1 + 680) + 1));
      }
      WorkerTaskMigrationSource::SetHVResourceControl(v17, 1, *(unsigned int *)(a1 + 700), *(_QWORD *)(a1 + 728));
      if ( (v37 & 1) != 0 )
        WorkerTaskMigrationSource::SetProcessorCacheAllocationOnLMClos(
          (WorkerTaskMigrationSource *)a1,
          (struct _HV_RESOURCE_CONTROL_SUPPORT_PROPERTY *)&v37,
          v5);
      v21 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(*(_QWORD *)(a1 + 16) + 1040LL) + 688LL))(
              *(_QWORD *)(*(_QWORD *)(a1 + 16) + 1040LL),
              *(unsigned int *)(a1 + 700));
      if ( v21 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1195,
          (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationsource.cpp",
          (const char *)(unsigned int)v21,
          v25);
      if ( (unsigned int)VmlIsDebugTraceEnabled(53730) )
        VmlDebugTraceEx(53730, &off_1402DAEC0);
      std::wstring::_Tidy_deallocate(v35);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int VidCloseStatisticsHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int VidCloseStatisticsHandle(void *)>>(&v29);
    }
    catch ( ... )
    {
      LODWORD(v29) = Vml::GetHResultFromThrownExceptionAndTrace((Vml *)0x41E2, (unsigned __int16)&off_1402DAF68, v22);
      if ( (int)v29 < 0 )
      {
        if ( (unsigned int)VmlIsDebugTraceEnabled(16866) )
          VmlDebugTraceWithError(16866, &off_1402DB0C0, (unsigned int)v29);
        *v30 = 0;
      }
      v2 = v33;
    }
  }
  Vml::VmRegistryKey::Close((Vml::VmRegistryKey *)((char *)&v34 + 8));
  return std::wstring::_Tidy_deallocate(v2 + 16);
}

```

## disassembly

```asm
0x14007edd8  mov     [rsp+arg_10], rbx
0x14007eddd  push    rsi
0x14007edde  push    r12
0x14007ede0  push    r13
0x14007ede2  push    r14
0x14007ede4  push    r15
0x14007ede6  sub     rsp, 510h
0x14007eded  mov     rax, cs:__security_cookie
0x14007edf4  xor     rax, rsp
0x14007edf7  mov     [rsp+538h+var_38], rax
0x14007edff  mov     r14, rdx
0x14007ee02  mov     rsi, rcx
0x14007ee05  mov     [rsp+538h+var_4B0], rdx
0x14007ee0d  xorps   xmm0, xmm0
0x14007ee10  movups  [rsp+538h+var_4A8], xmm0
0x14007ee18  lea     rcx, [rsp+538h+var_4A8]; this
0x14007ee20  call    ??0VmMigrationSettings@@QEAA@_N@Z; VmMigrationSettings::VmMigrationSettings(bool)
0x14007ee25  nop
0x14007ee26  lea     rcx, [rsp+538h+var_4A8]; this
0x14007ee2e  call    ?IsMemoryBandwidthAllocationEnabled@VmMigrationSettings@@UEBA_NXZ; VmMigrationSettings::IsMemoryBandwidthAllocationEnabled(void)
0x14007ee33  mov     cl, al
0x14007ee35  cmp     byte ptr [r14+9], 0
0x14007ee3a  jz      short loc_14007EE40
0x14007ee3c  mov     cl, [r14+8]
0x14007ee40  lea     rax, [rsi+2B8h]
0x14007ee47  mov     [rsp+538h+var_4E0], rax
0x14007ee4c  mov     [rax], cl
0x14007ee4e  test    cl, cl
0x14007ee50  jz      loc_14007F3C3
0x14007ee56  call    cs:__imp_VidOpenStatisticsHandle
0x14007ee5d  nop     dword ptr [rax+rax+00h]
0x14007ee62  mov     rbx, rax
0x14007ee65  mov     [rsp+538h+var_4E8], rax
0x14007ee6a  xorps   xmm0, xmm0
0x14007ee6d  movups  [rsp+538h+var_478], xmm0
0x14007ee75  movups  xmmword ptr [rsp+538h+var_468], xmm0
0x14007ee7d  movups  [rsp+538h+var_458], xmm0
0x14007ee85  xor     edx, edx; Val
0x14007ee87  mov     r8d, 408h; Size
0x14007ee8d  lea     rcx, [rsp+538h+var_448]; void *
0x14007ee95  call    memset_0
0x14007ee9a  lea     rdx, [rsp+538h+var_4D8]
0x14007ee9f  lea     rcx, [rsp+538h+var_4A8]
0x14007eea7  call    ?GetClassOfServiceIndex@VmMigrationSettings@@UEBA?AV?$optional@I@std@@XZ; VmMigrationSettings::GetClassOfServiceIndex(void)
0x14007eeac  cmp     byte ptr [rax+4], 0
0x14007eeb0  jz      short loc_14007EEB6
0x14007eeb2  mov     eax, [rax]
0x14007eeb4  jmp     short loc_14007EEB9
0x14007eeb6  or      eax, 0FFFFFFFFh
0x14007eeb9  cmp     byte ptr [r14+4], 0
0x14007eebe  jz      short loc_14007EEC3
0x14007eec0  mov     eax, [r14]
0x14007eec3  mov     [rsi+2BCh], eax
0x14007eec9  cmp     eax, 0FFFFFFFFh
0x14007eecc  setz    al
0x14007eecf  mov     rcx, [rsp+538h]; this
0x14007eed7  lea     rdx, aClassOfService; "Class Of Service Index is undefined"
0x14007eede  mov     [rsp+538h+var_510], rdx; bool
0x14007eee3  mov     [rsp+538h+var_518], al; char
0x14007eee7  mov     r9d, 8007000Dh; char *
0x14007eeed  lea     r13, aOnecoreVmWorke_0; "onecore\\vm\\worker\\migration\\workert"...
0x14007eef4  mov     r8, r13; unsigned int
0x14007eef7  mov     edx, 1137h; void *
0x14007eefc  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x14007ef01  lea     rcx, [rsp+538h+var_4A8]; this
0x14007ef09  call    ?GetMbaInitialThrottlePercentage@VmMigrationSettings@@UEBAIXZ; VmMigrationSettings::GetMbaInitialThrottlePercentage(void)
0x14007ef0e  mov     r15d, eax
0x14007ef11  cmp     byte ptr [r14+3Ch], 0
0x14007ef16  jz      short loc_14007EF1C
0x14007ef18  mov     r15d, [r14+38h]
0x14007ef1c  lea     rdx, [rsp+538h+var_4D0]
0x14007ef21  lea     rcx, [rsp+538h+var_4A8]
0x14007ef29  call    ?GetMbaThrottleStrategy@VmMigrationSettings@@UEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; VmMigrationSettings::GetMbaThrottleStrategy(void)
0x14007ef2e  nop
0x14007ef2f  lea     rcx, [r14+10h]
0x14007ef33  mov     r8, rax
0x14007ef36  lea     rdx, [rsp+538h+var_498]
0x14007ef3e  call    ??$value_or@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@vmstd@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$QEAV23@@Z; vmstd::optional<std::wstring>::value_or<std::wstring>(std::wstring &&)
0x14007ef43  nop
0x14007ef44  lea     rcx, [rsp+538h+var_4D0]
0x14007ef49  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14007ef4e  lea     rcx, [rsp+538h+var_498]
0x14007ef56  cmp     [rsp+538h+var_480], 7
0x14007ef5f  cmova   rcx, [rsp+538h+var_498]
0x14007ef68  mov     r8d, 7
0x14007ef6e  lea     r12, aLinear; "Linear"
0x14007ef75  mov     rdx, r12
0x14007ef78  call    cs:__imp__o__wcsnicmp
0x14007ef7f  nop     dword ptr [rax+rax+00h]
0x14007ef84  test    eax, eax
0x14007ef86  jnz     short loc_14007EF8F
0x14007ef88  mov     eax, 1
0x14007ef8d  jmp     short loc_14007EFCF
0x14007ef8f  lea     rcx, [rsp+538h+var_498]
0x14007ef97  cmp     [rsp+538h+var_480], 7
0x14007efa0  cmova   rcx, [rsp+538h+var_498]
0x14007efa9  mov     r8d, 9
0x14007efaf  lea     rdx, aAdaptive; "Adaptive"
0x14007efb6  call    cs:__imp__o__wcsnicmp
0x14007efbd  nop     dword ptr [rax+rax+00h]
0x14007efc2  test    eax, eax
0x14007efc4  jnz     loc_14007F342
0x14007efca  mov     eax, 2
0x14007efcf  mov     [rsi+2C0h], eax
0x14007efd5  mov     [rsp+538h+var_508], 0; char *
0x14007efde  mov     dword ptr [rsp+538h+var_510], 20h ; ' '
0x14007efe6  lea     rax, [rsp+538h+var_478]
0x14007efee  mov     qword ptr [rsp+538h+var_518], rax
0x14007eff3  xor     r9d, r9d
0x14007eff6  xor     r8d, r8d
0x14007eff9  lea     edx, [r9+3]
0x14007effd  mov     rcx, rbx
0x14007f000  call    cs:__imp_VidGetSystemInformation
0x14007f007  nop     dword ptr [rax+rax+00h]
0x14007f00c  mov     rcx, [rsp+538h]; this
0x14007f014  mov     r8, r13; unsigned int
0x14007f017  test    eax, eax
0x14007f019  jnz     short loc_14007F025
0x14007f01b  mov     edx, 114Eh; void *
0x14007f020  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x14007f025  mov     eax, dword ptr [rsp+538h+var_478]
0x14007f02c  shr     eax, 5
0x14007f02f  not     al
0x14007f031  and     al, 1
0x14007f033  mov     rcx, [rsp+538h]; this
0x14007f03b  lea     rdx, aMbaIsNotSuppor; "MBA is not supported on this system"
0x14007f042  mov     [rsp+538h+var_510], rdx; bool
0x14007f047  mov     [rsp+538h+var_518], al; char
0x14007f04b  mov     r9d, 80070032h; char *
0x14007f051  mov     edx, 1153h; void *
0x14007f056  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x14007f05b  mov     dword ptr [rsp+538h+var_458], 1
0x14007f066  mov     [rsp+538h+var_508], 0
0x14007f06f  mov     dword ptr [rsp+538h+var_510], 408h
0x14007f077  lea     rax, [rsp+538h+var_448]
0x14007f07f  mov     qword ptr [rsp+538h+var_518], rax
0x14007f084  mov     r9d, 10h
0x14007f08a  lea     r8, [rsp+538h+var_458]
0x14007f092  lea     edx, [r9-0Ch]
0x14007f096  mov     rcx, rbx
0x14007f099  call    cs:__imp_VidGetSystemInformation
0x14007f0a0  nop     dword ptr [rax+rax+00h]
0x14007f0a5  mov     rcx, [rsp+538h]; this
0x14007f0ad  test    eax, eax
0x14007f0af  jnz     short loc_14007F0BE
0x14007f0b1  mov     r8, r13; unsigned int
0x14007f0b4  mov     edx, 115Eh; void *
0x14007f0b9  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x14007f0be  mov     edx, dword ptr [rsp+538h+var_468+4]
0x14007f0c5  mov     rax, [rsp+538h+var_448]
0x14007f0cd  cmp     edx, eax
0x14007f0cf  setnz   r8b
0x14007f0d3  mov     rcx, [rsp+538h]; this
0x14007f0db  mov     dword ptr [rsp+538h+var_500], eax
0x14007f0df  mov     dword ptr [rsp+538h+var_508], edx; char *
0x14007f0e3  lea     rax, aTheNumberOfMba; "The number of MBA slots is not equal to"...
0x14007f0ea  mov     [rsp+538h+var_510], rax; bool
0x14007f0ef  mov     [rsp+538h+var_518], r8b; char
0x14007f0f4  mov     r9d, 80004005h; char *
0x14007f0fa  mov     r8, r13; unsigned int
0x14007f0fd  mov     edx, 1164h; void *
0x14007f102  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x14007f107  mov     rax, [rsi+10h]
0x14007f10b  mov     rcx, [rax+410h]
0x14007f112  mov     rax, [rcx]
0x14007f115  mov     rax, [rax+2A8h]
0x14007f11c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007f121  mov     [rsi+2C4h], eax
0x14007f127  mov     r9d, [rsi+2BCh]
0x14007f12e  mov     edx, dword ptr [rsp+538h+var_468+4]
0x14007f135  cmp     r9d, edx
0x14007f138  jnb     short loc_14007F143
0x14007f13a  cmp     eax, edx
0x14007f13c  jnb     short loc_14007F143
0x14007f13e  xor     r8d, r8d
0x14007f141  jmp     short loc_14007F146
0x14007f143  mov     r8b, 1
0x14007f146  mov     rcx, [rsp+538h]; this
0x14007f14e  mov     dword ptr [rsp+538h+var_4F8], edx
0x14007f152  mov     dword ptr [rsp+538h+var_500], eax
0x14007f156  mov     dword ptr [rsp+538h+var_508], r9d; char *
0x14007f15b  lea     rax, aTheLmClosOrVmA; "The LM CLOS or VM allocation id is beyo"...
0x14007f162  mov     [rsp+538h+var_510], rax; bool
0x14007f167  mov     [rsp+538h+var_518], r8b; int
0x14007f16c  mov     r9d, 80004005h; char *
0x14007f172  mov     r8, r13; unsigned int
0x14007f175  mov     edx, 116Eh; void *
0x14007f17a  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x14007f17f  mov     eax, [rsi+2C4h]
0x14007f185  mov     rdx, [rsp+rax*8+538h+var_440]
0x14007f18d  mov     [rsi+2D8h], rdx
0x14007f194  mov     al, byte ptr [rsp+538h+var_468+0Ch]
0x14007f19b  and     al, 1
0x14007f19d  mov     [rsi+2C8h], al
0x14007f1a3  mov     eax, dword ptr [rsp+538h+var_468+8]
0x14007f1aa  mov     [rsi+2D0h], rax
0x14007f1b1  test    r15d, r15d
0x14007f1b4  jz      short loc_14007F1CC
0x14007f1b6  mov     eax, r15d
0x14007f1b9  xorps   xmm1, xmm1
0x14007f1bc  cvtsi2sd xmm1, rax; double
0x14007f1c1  mov     rcx, rsi; this
0x14007f1c4  call    ?CalculateMbaThrottleValue@WorkerTaskMigrationSource@@AEAA_KN@Z; WorkerTaskMigrationSource::CalculateMbaThrottleValue(double)
0x14007f1c9  mov     rdx, rax
0x14007f1cc  mov     [rsi+2F0h], rdx
0x14007f1d3  cmp     dword ptr [rsi+2C0h], 1
0x14007f1da  jnz     short loc_14007F230
0x14007f1dc  mov     rcx, [rsi+2D0h]
0x14007f1e3  sub     rcx, rdx
0x14007f1e6  xorps   xmm1, xmm1
0x14007f1e9  js      short loc_14007F1F2
0x14007f1eb  cvtsi2sd xmm1, rcx
0x14007f1f0  jmp     short loc_14007F207
0x14007f1f2  mov     rax, rcx
0x14007f1f5  shr     rax, 1
0x14007f1f8  and     ecx, 1
0x14007f1fb  or      rax, rcx
0x14007f1fe  cvtsi2sd xmm1, rax
0x14007f203  addsd   xmm1, xmm1
0x14007f207  mov     eax, [rsi+2A0h]
0x14007f20d  sub     eax, [rsi+2A8h]
0x14007f213  inc     eax
0x14007f215  xorps   xmm0, xmm0
0x14007f218  cvtsi2sd xmm0, rax
0x14007f21d  divsd   xmm1, xmm0; double
0x14007f221  mov     rcx, rsi; this
0x14007f224  call    ?GetNormalizedMBAThrottleValue@WorkerTaskMigrationSource@@AEAA_KN@Z; WorkerTaskMigrationSource::GetNormalizedMBAThrottleValue(double)
0x14007f229  mov     [rsi+2E8h], rax
0x14007f230  mov     r9, [rsi+2D8h]
0x14007f237  mov     r8d, [rsi+2BCh]
0x14007f23e  mov     edx, 1
0x14007f243  call    ?SetHVResourceControl@WorkerTaskMigrationSource@@AEAAXW4_HV_RESOURCE_CONTROL_TYPE@@I_K@Z; WorkerTaskMigrationSource::SetHVResourceControl(_HV_RESOURCE_CONTROL_TYPE,uint,unsigned __int64)
0x14007f248  test    byte ptr [rsp+538h+var_478], 1
0x14007f250  jz      short loc_14007F265
0x14007f252  mov     r8, rbx; void *
0x14007f255  lea     rdx, [rsp+538h+var_478]; struct _HV_RESOURCE_CONTROL_SUPPORT_PROPERTY *
0x14007f25d  mov     rcx, rsi; this
0x14007f260  call    ?SetProcessorCacheAllocationOnLMClos@WorkerTaskMigrationSource@@AEAAXAEAU_HV_RESOURCE_CONTROL_SUPPORT_PROPERTY@@PEAX@Z; WorkerTaskMigrationSource::SetProcessorCacheAllocationOnLMClos(_HV_RESOURCE_CONTROL_SUPPORT_PROPERTY &,void *)
0x14007f265  mov     rax, [rsi+10h]
0x14007f269  mov     rcx, [rax+410h]
0x14007f270  mov     rax, [rcx]
0x14007f273  mov     edx, [rsi+2BCh]
0x14007f279  mov     rax, [rax+2B0h]
0x14007f280  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007f285  mov     rcx, [rsp+538h]; this
0x14007f28d  test    eax, eax
0x14007f28f  jns     short loc_14007F2A1
0x14007f291  mov     r9d, eax; char *
0x14007f294  mov     r8, r13; unsigned int
0x14007f297  mov     edx, 1195h; void *
0x14007f29c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14007f2a1  mov     ebx, 0D1E2h
0x14007f2a6  mov     ecx, ebx
0x14007f2a8  call    VmlIsDebugTraceEnabled
0x14007f2ad  test    eax, eax
0x14007f2af  jz      short loc_14007F324
0x14007f2b1  lea     rax, [rsp+538h+var_498]
0x14007f2b9  cmp     [rsp+538h+var_480], 7
0x14007f2c2  cmova   rax, [rsp+538h+var_498]
0x14007f2cb  lea     rdx, aNonlinear; "NonLinear"
0x14007f2d2  cmp     byte ptr [rsi+2C8h], 0
0x14007f2d9  cmovz   r12, rdx
0x14007f2dd  mov     [rsp+538h+var_4F8], rax
0x14007f2e2  mov     rax, [rsi+2D0h]
0x14007f2e9  mov     [rsp+538h+var_500], rax
0x14007f2ee  mov     rax, [rsi+2F0h]
0x14007f2f5  mov     [rsp+538h+var_508], rax
0x14007f2fa  mov     rax, [rsi+2D8h]
0x14007f301  mov     [rsp+538h+var_510], rax
0x14007f306  mov     qword ptr [rsp+538h+var_518], r12
0x14007f30b  mov     r9d, r15d
0x14007f30e  mov     r8d, [rsi+2BCh]
0x14007f315  lea     rdx, off_1402DAEC0; "MBA is enabled. Index:%u,InitialThrottl"...
0x14007f31c  mov     ecx, ebx
0x14007f31e  call    VmlDebugTraceEx
0x14007f323  nop
0x14007f324  lea     rcx, [rsp+538h+var_498]
0x14007f32c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14007f331  nop
0x14007f332  lea     rcx, [rsp+538h+var_4E8]
0x14007f337  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?VidCloseStatisticsHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&VidCloseStatisticsHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&VidCloseStatisticsHandle(void *)>>(void)
0x14007f33c  nop
0x14007f33d  jmp     loc_14007F3C3
0x14007f342  lea     rax, [rsp+538h+var_498]
0x14007f34a  cmp     [rsp+538h+var_480], 7
0x14007f353  cmova   rax, [rsp+538h+var_498]
0x14007f35c  mov     rcx, [rsp+538h]; this
0x14007f364  mov     [rsp+538h+var_510], rax; char *
0x14007f369  lea     rax, aInvalidMbaThro_0; "Invalid MBA throttle strategy:%ws"
0x14007f370  mov     qword ptr [rsp+538h+var_518], rax; int
0x14007f375  mov     r9d, 80070057h; char *
0x14007f37b  mov     r8, r13; unsigned int
0x14007f37e  mov     edx, 1146h; void *
0x14007f383  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
0x14007f389  cmp     dword ptr [rsp+538h+var_4E8], 0
0x14007f38e  jge     short loc_14007F3BB
0x14007f390  mov     ebx, 41E2h
0x14007f395  mov     ecx, ebx
0x14007f397  call    VmlIsDebugTraceEnabled
0x14007f39c  test    eax, eax
  ... truncated ...
```
