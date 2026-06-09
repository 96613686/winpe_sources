# WorkerTaskMigrationSource::InitializeClassOfServiceLMContext(Migration::Parameters::Worker::MigrationClassOfServiceParams)

- ea: `0x14008ff84`
- end: `0x1400905b0`
- name: `?InitializeClassOfServiceLMContext@WorkerTaskMigrationSource@@AEAAXUMigrationClassOfServiceParams@Worker@Parameters@Migration@@@Z`
- size: `1580`
- prototype: ``
- caller_count: `1`
- callee_count: `24`
- tags: `reparse_path, registry_config, loader_planting, service_task`

## callers

- `0x1402114f0`

## callees

- `0x1400364a0`
- `0x14003d828`
- `0x1400544a8`
- `0x140066eec`
- `0x140073f70`
- `0x140078628`
- `0x140083990`
- `0x14008ff18`
- `0x14008ff84`
- `0x1400905c0`
- `0x14009061c`
- `0x140102580`
- `0x140110658`
- `0x1401106f4`
- `0x140110720`
- `0x14011ea40`
- `0x14011f6fc`
- `0x1401399d0`
- `0x140139e20`
- `0x140139e50`
- `0x14020b974`
- `0x14020e0b8`
- `0x1402107d0`
- `0x1402cb010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x140090124`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x140090162`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x140090124`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x140090162`
- `vid!VidOpenStatisticsHandle` at `0x140090002`
- `vid!VidOpenStatisticsHandle` at `0x140090002`
- `vid!VidGetSystemInformation` at `0x1400901ac`
- `vid!VidGetSystemInformation` at `0x140090245`
- `vid!VidGetSystemInformation` at `0x1400901ac`
- `vid!VidGetSystemInformation` at `0x140090245`

## string_xrefs

- `0x140090099`: `onecore\vm\worker\migration\workertaskmigrationsource.cpp`
- `0x140090083`: `Class Of Service Index is undefined`

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
  v30 = (_BYTE *)(a1 + 1136);
  *(_BYTE *)(a1 + 1136) = v4;
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
      *(_DWORD *)(a1 + 1140) = v7;
      wil::details::in1diag3::Throw_HrIfMsg(
        retaddr,
        (void *)0x11E1,
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
            (void *)0x11F0,
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
      *(_DWORD *)(a1 + 1144) = v11;
      if ( !(unsigned int)VidGetSystemInformation(v5, 3, 0) )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x11F8,
          (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationsource.cpp",
          v13);
      wil::details::in1diag3::Throw_HrIfMsg(
        retaddr,
        (void *)0x11FD,
        (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationsource.cpp",
        (const char *)0x80070032LL,
        (v37 & 0x20) == 0,
        (bool)"MBA is not supported on this system",
        0);
      LODWORD(v39) = 1;
      if ( !(unsigned int)VidGetSystemInformation(v5, 4, &v39) )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x1208,
          (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationsource.cpp",
          v14);
      wil::details::in1diag3::Throw_HrIfMsg(
        retaddr,
        (void *)0x120E,
        (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationsource.cpp",
        (const char *)0x80004005LL,
        HIDWORD(v38[0]) != LODWORD(v40[0]),
        (bool)"The number of MBA slots is not equal to the number of HV resource control value count. MemoryBandwidthSlot"
              "s:%u, HVResourceControlNumValues:%u",
        (const char *)HIDWORD(v38[0]),
        LODWORD(v40[0]));
      v15 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(*(_QWORD *)(a1 + 16) + 1040LL) + 680LL))(*(_QWORD *)(*(_QWORD *)(a1 + 16) + 1040LL));
      *(_DWORD *)(a1 + 1148) = v15;
      v16 = *(_DWORD *)(a1 + 1140) >= HIDWORD(v38[0]) || v15 >= HIDWORD(v38[0]);
      LODWORD(v28) = v15;
      LODWORD(v27) = *(_DWORD *)(a1 + 1140);
      wil::details::in1diag3::Throw_HrIfMsg(
        retaddr,
        (void *)0x1218,
        (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationsource.cpp",
        (const char *)0x80004005LL,
        v16,
        (bool)"The LM CLOS or VM allocation id is beyond the MBA slots. LMClosIndex:%u, OriginalVMAllocationId:%u, Memory"
              "BandwidthSlots:%u",
        v27,
        v28,
        HIDWORD(v38[0]));
      v18 = v40[*(unsigned int *)(a1 + 1148) + 1];
      *(_QWORD *)(a1 + 1168) = v18;
      *(_BYTE *)(a1 + 1152) = BYTE4(v38[1]) & 1;
      *(_QWORD *)(a1 + 1160) = LODWORD(v38[1]);
      if ( MbaInitialThrottlePercentage )
        v18 = WorkerTaskMigrationSource::CalculateMbaThrottleValue(
                (WorkerTaskMigrationSource *)a1,
                (double)MbaInitialThrottlePercentage);
      *(_QWORD *)(a1 + 1192) = v18;
      if ( *(_DWORD *)(a1 + 1144) == 1 )
      {
        v19 = *(_QWORD *)(a1 + 1160) - v18;
        if ( v19 < 0 )
          v20 = (double)(int)(v19 & 1 | ((unsigned __int64)v19 >> 1))
              + (double)(int)(v19 & 1 | ((unsigned __int64)v19 >> 1));
        else
          v20 = (double)(int)v19;
        *(_QWORD *)(a1 + 1184) = WorkerTaskMigrationSource::GetNormalizedMBAThrottleValue(
                                   (WorkerTaskMigrationSource *)a1,
                                   v20 / (double)(*(_DWORD *)(a1 + 1112) - *(_DWORD *)(a1 + 1120) + 1));
      }
      WorkerTaskMigrationSource::SetHVResourceControl(v17, 1, *(unsigned int *)(a1 + 1140), *(_QWORD *)(a1 + 1168));
      if ( (v37 & 1) != 0 )
        WorkerTaskMigrationSource::SetProcessorCacheAllocationOnLMClos(
          (WorkerTaskMigrationSource *)a1,
          (struct _HV_RESOURCE_CONTROL_SUPPORT_PROPERTY *)&v37,
          v5);
      v21 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(*(_QWORD *)(a1 + 16) + 1040LL) + 688LL))(
              *(_QWORD *)(*(_QWORD *)(a1 + 16) + 1040LL),
              *(unsigned int *)(a1 + 1140));
      if ( v21 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x123F,
          (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationsource.cpp",
          (const char *)(unsigned int)v21,
          v25);
      if ( (unsigned int)VmlIsDebugTraceEnabled(53730) )
        VmlDebugTraceEx(53730, &off_1402E4388);
      std::wstring::_Tidy_deallocate(v35);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int VidCloseStatisticsHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int VidCloseStatisticsHandle(void *)>>(&v29);
    }
    catch ( ... )
    {
      LODWORD(v29) = Vml::GetHResultFromThrownExceptionAndTrace((Vml *)0x41E2, (unsigned __int16)&off_1402E4448, v22);
      if ( (int)v29 < 0 )
      {
        if ( (unsigned int)VmlIsDebugTraceEnabled(16866) )
          VmlDebugTraceWithError(16866, &off_1402E45B0, (unsigned int)v29);
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
0x14008ff84  mov     [rsp+arg_10], rbx
0x14008ff89  push    rsi
0x14008ff8a  push    r12
0x14008ff8c  push    r13
0x14008ff8e  push    r14
0x14008ff90  push    r15
0x14008ff92  sub     rsp, 510h
0x14008ff99  mov     rax, cs:__security_cookie
0x14008ffa0  xor     rax, rsp
0x14008ffa3  mov     [rsp+538h+var_38], rax
0x14008ffab  mov     r14, rdx
0x14008ffae  mov     rsi, rcx
0x14008ffb1  mov     [rsp+538h+var_4B0], rdx
0x14008ffb9  xorps   xmm0, xmm0
0x14008ffbc  movups  [rsp+538h+var_4A8], xmm0
0x14008ffc4  lea     rcx, [rsp+538h+var_4A8]; this
0x14008ffcc  call    ??0VmMigrationSettings@@QEAA@_N@Z; VmMigrationSettings::VmMigrationSettings(bool)
0x14008ffd1  nop
0x14008ffd2  lea     rcx, [rsp+538h+var_4A8]; this
0x14008ffda  call    ?IsMemoryBandwidthAllocationEnabled@VmMigrationSettings@@UEBA_NXZ; VmMigrationSettings::IsMemoryBandwidthAllocationEnabled(void)
0x14008ffdf  mov     cl, al
0x14008ffe1  cmp     byte ptr [r14+9], 0
0x14008ffe6  jz      short loc_14008FFEC
0x14008ffe8  mov     cl, [r14+8]
0x14008ffec  lea     rax, [rsi+470h]
0x14008fff3  mov     [rsp+538h+var_4E0], rax
0x14008fff8  mov     [rax], cl
0x14008fffa  test    cl, cl
0x14008fffc  jz      loc_14009056F
0x140090002  call    cs:__imp_VidOpenStatisticsHandle
0x140090009  nop     dword ptr [rax+rax+00h]
0x14009000e  mov     rbx, rax
0x140090011  mov     [rsp+538h+var_4E8], rax
0x140090016  xorps   xmm0, xmm0
0x140090019  movups  [rsp+538h+var_478], xmm0
0x140090021  movups  xmmword ptr [rsp+538h+var_468], xmm0
0x140090029  movups  [rsp+538h+var_458], xmm0
0x140090031  xor     edx, edx; Val
0x140090033  mov     r8d, 408h; Size
0x140090039  lea     rcx, [rsp+538h+var_448]; void *
0x140090041  call    memset_0
0x140090046  lea     rdx, [rsp+538h+var_4D8]
0x14009004b  lea     rcx, [rsp+538h+var_4A8]
0x140090053  call    ?GetClassOfServiceIndex@VmMigrationSettings@@UEBA?AV?$optional@I@std@@XZ; VmMigrationSettings::GetClassOfServiceIndex(void)
0x140090058  cmp     byte ptr [rax+4], 0
0x14009005c  jz      short loc_140090062
0x14009005e  mov     eax, [rax]
0x140090060  jmp     short loc_140090065
0x140090062  or      eax, 0FFFFFFFFh
0x140090065  cmp     byte ptr [r14+4], 0
0x14009006a  jz      short loc_14009006F
0x14009006c  mov     eax, [r14]
0x14009006f  mov     [rsi+474h], eax
0x140090075  cmp     eax, 0FFFFFFFFh
0x140090078  setz    al
0x14009007b  mov     rcx, [rsp+538h]; this
0x140090083  lea     rdx, aClassOfService; "Class Of Service Index is undefined"
0x14009008a  mov     [rsp+538h+var_510], rdx; bool
0x14009008f  mov     [rsp+538h+var_518], al; char
0x140090093  mov     r9d, 8007000Dh; char *
0x140090099  lea     r13, aOnecoreVmWorke_0; "onecore\\vm\\worker\\migration\\workert"...
0x1400900a0  mov     r8, r13; unsigned int
0x1400900a3  mov     edx, 11E1h; void *
0x1400900a8  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x1400900ad  lea     rcx, [rsp+538h+var_4A8]; this
0x1400900b5  call    ?GetMbaInitialThrottlePercentage@VmMigrationSettings@@UEBAIXZ; VmMigrationSettings::GetMbaInitialThrottlePercentage(void)
0x1400900ba  mov     r15d, eax
0x1400900bd  cmp     byte ptr [r14+3Ch], 0
0x1400900c2  jz      short loc_1400900C8
0x1400900c4  mov     r15d, [r14+38h]
0x1400900c8  lea     rdx, [rsp+538h+var_4D0]
0x1400900cd  lea     rcx, [rsp+538h+var_4A8]
0x1400900d5  call    ?GetMbaThrottleStrategy@VmMigrationSettings@@UEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; VmMigrationSettings::GetMbaThrottleStrategy(void)
0x1400900da  nop
0x1400900db  lea     rcx, [r14+10h]
0x1400900df  mov     r8, rax
0x1400900e2  lea     rdx, [rsp+538h+var_498]
0x1400900ea  call    ??$value_or@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@vmstd@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$QEAV23@@Z; vmstd::optional<std::wstring>::value_or<std::wstring>(std::wstring &&)
0x1400900ef  nop
0x1400900f0  lea     rcx, [rsp+538h+var_4D0]
0x1400900f5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400900fa  lea     rcx, [rsp+538h+var_498]
0x140090102  cmp     [rsp+538h+var_480], 7
0x14009010b  cmova   rcx, [rsp+538h+var_498]
0x140090114  mov     r8d, 7
0x14009011a  lea     r12, aLinear; "Linear"
0x140090121  mov     rdx, r12
0x140090124  call    cs:__imp__o__wcsnicmp
0x14009012b  nop     dword ptr [rax+rax+00h]
0x140090130  test    eax, eax
0x140090132  jnz     short loc_14009013B
0x140090134  mov     eax, 1
0x140090139  jmp     short loc_14009017B
0x14009013b  lea     rcx, [rsp+538h+var_498]
0x140090143  cmp     [rsp+538h+var_480], 7
0x14009014c  cmova   rcx, [rsp+538h+var_498]
0x140090155  mov     r8d, 9
0x14009015b  lea     rdx, aAdaptive; "Adaptive"
0x140090162  call    cs:__imp__o__wcsnicmp
0x140090169  nop     dword ptr [rax+rax+00h]
0x14009016e  test    eax, eax
0x140090170  jnz     loc_1400904EE
0x140090176  mov     eax, 2
0x14009017b  mov     [rsi+478h], eax
0x140090181  mov     [rsp+538h+var_508], 0; char *
0x14009018a  mov     dword ptr [rsp+538h+var_510], 20h ; ' '
0x140090192  lea     rax, [rsp+538h+var_478]
0x14009019a  mov     qword ptr [rsp+538h+var_518], rax
0x14009019f  xor     r9d, r9d
0x1400901a2  xor     r8d, r8d
0x1400901a5  lea     edx, [r9+3]
0x1400901a9  mov     rcx, rbx
0x1400901ac  call    cs:__imp_VidGetSystemInformation
0x1400901b3  nop     dword ptr [rax+rax+00h]
0x1400901b8  mov     rcx, [rsp+538h]; this
0x1400901c0  mov     r8, r13; unsigned int
0x1400901c3  test    eax, eax
0x1400901c5  jnz     short loc_1400901D1
0x1400901c7  mov     edx, 11F8h; void *
0x1400901cc  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1400901d1  mov     eax, dword ptr [rsp+538h+var_478]
0x1400901d8  shr     eax, 5
0x1400901db  not     al
0x1400901dd  and     al, 1
0x1400901df  mov     rcx, [rsp+538h]; this
0x1400901e7  lea     rdx, aMbaIsNotSuppor; "MBA is not supported on this system"
0x1400901ee  mov     [rsp+538h+var_510], rdx; bool
0x1400901f3  mov     [rsp+538h+var_518], al; char
0x1400901f7  mov     r9d, 80070032h; char *
0x1400901fd  mov     edx, 11FDh; void *
0x140090202  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x140090207  mov     dword ptr [rsp+538h+var_458], 1
0x140090212  mov     [rsp+538h+var_508], 0
0x14009021b  mov     dword ptr [rsp+538h+var_510], 408h
0x140090223  lea     rax, [rsp+538h+var_448]
0x14009022b  mov     qword ptr [rsp+538h+var_518], rax
0x140090230  mov     r9d, 10h
0x140090236  lea     r8, [rsp+538h+var_458]
0x14009023e  lea     edx, [r9-0Ch]
0x140090242  mov     rcx, rbx
0x140090245  call    cs:__imp_VidGetSystemInformation
0x14009024c  nop     dword ptr [rax+rax+00h]
0x140090251  mov     rcx, [rsp+538h]; this
0x140090259  test    eax, eax
0x14009025b  jnz     short loc_14009026A
0x14009025d  mov     r8, r13; unsigned int
0x140090260  mov     edx, 1208h; void *
0x140090265  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x14009026a  mov     edx, dword ptr [rsp+538h+var_468+4]
0x140090271  mov     rax, [rsp+538h+var_448]
0x140090279  cmp     edx, eax
0x14009027b  setnz   r8b
0x14009027f  mov     rcx, [rsp+538h]; this
0x140090287  mov     dword ptr [rsp+538h+var_500], eax
0x14009028b  mov     dword ptr [rsp+538h+var_508], edx; char *
0x14009028f  lea     rax, aTheNumberOfMba; "The number of MBA slots is not equal to"...
0x140090296  mov     [rsp+538h+var_510], rax; bool
0x14009029b  mov     [rsp+538h+var_518], r8b; char
0x1400902a0  mov     r9d, 80004005h; char *
0x1400902a6  mov     r8, r13; unsigned int
0x1400902a9  mov     edx, 120Eh; void *
0x1400902ae  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x1400902b3  mov     rax, [rsi+10h]
0x1400902b7  mov     rcx, [rax+410h]
0x1400902be  mov     rax, [rcx]
0x1400902c1  mov     rax, [rax+2A8h]
0x1400902c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400902cd  mov     [rsi+47Ch], eax
0x1400902d3  mov     r9d, [rsi+474h]
0x1400902da  mov     edx, dword ptr [rsp+538h+var_468+4]
0x1400902e1  cmp     r9d, edx
0x1400902e4  jnb     short loc_1400902EF
0x1400902e6  cmp     eax, edx
0x1400902e8  jnb     short loc_1400902EF
0x1400902ea  xor     r8d, r8d
0x1400902ed  jmp     short loc_1400902F2
0x1400902ef  mov     r8b, 1
0x1400902f2  mov     rcx, [rsp+538h]; this
0x1400902fa  mov     dword ptr [rsp+538h+var_4F8], edx
0x1400902fe  mov     dword ptr [rsp+538h+var_500], eax
0x140090302  mov     dword ptr [rsp+538h+var_508], r9d; char *
0x140090307  lea     rax, aTheLmClosOrVmA; "The LM CLOS or VM allocation id is beyo"...
0x14009030e  mov     [rsp+538h+var_510], rax; bool
0x140090313  mov     [rsp+538h+var_518], r8b; int
0x140090318  mov     r9d, 80004005h; char *
0x14009031e  mov     r8, r13; unsigned int
0x140090321  mov     edx, 1218h; void *
0x140090326  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x14009032b  mov     eax, [rsi+47Ch]
0x140090331  mov     rdx, [rsp+rax*8+538h+var_440]
0x140090339  mov     [rsi+490h], rdx
0x140090340  mov     al, byte ptr [rsp+538h+var_468+0Ch]
0x140090347  and     al, 1
0x140090349  mov     [rsi+480h], al
0x14009034f  mov     eax, dword ptr [rsp+538h+var_468+8]
0x140090356  mov     [rsi+488h], rax
0x14009035d  test    r15d, r15d
0x140090360  jz      short loc_140090378
0x140090362  mov     eax, r15d
0x140090365  xorps   xmm1, xmm1
0x140090368  cvtsi2sd xmm1, rax; double
0x14009036d  mov     rcx, rsi; this
0x140090370  call    ?CalculateMbaThrottleValue@WorkerTaskMigrationSource@@AEAA_KN@Z; WorkerTaskMigrationSource::CalculateMbaThrottleValue(double)
0x140090375  mov     rdx, rax
0x140090378  mov     [rsi+4A8h], rdx
0x14009037f  cmp     dword ptr [rsi+478h], 1
0x140090386  jnz     short loc_1400903DC
0x140090388  mov     rcx, [rsi+488h]
0x14009038f  sub     rcx, rdx
0x140090392  xorps   xmm1, xmm1
0x140090395  js      short loc_14009039E
0x140090397  cvtsi2sd xmm1, rcx
0x14009039c  jmp     short loc_1400903B3
0x14009039e  mov     rax, rcx
0x1400903a1  shr     rax, 1
0x1400903a4  and     ecx, 1
0x1400903a7  or      rax, rcx
0x1400903aa  cvtsi2sd xmm1, rax
0x1400903af  addsd   xmm1, xmm1
0x1400903b3  mov     eax, [rsi+458h]
0x1400903b9  sub     eax, [rsi+460h]
0x1400903bf  inc     eax
0x1400903c1  xorps   xmm0, xmm0
0x1400903c4  cvtsi2sd xmm0, rax
0x1400903c9  divsd   xmm1, xmm0; double
0x1400903cd  mov     rcx, rsi; this
0x1400903d0  call    ?GetNormalizedMBAThrottleValue@WorkerTaskMigrationSource@@AEAA_KN@Z; WorkerTaskMigrationSource::GetNormalizedMBAThrottleValue(double)
0x1400903d5  mov     [rsi+4A0h], rax
0x1400903dc  mov     r9, [rsi+490h]
0x1400903e3  mov     r8d, [rsi+474h]
0x1400903ea  mov     edx, 1
0x1400903ef  call    ?SetHVResourceControl@WorkerTaskMigrationSource@@AEAAXW4_HV_RESOURCE_CONTROL_TYPE@@I_K@Z; WorkerTaskMigrationSource::SetHVResourceControl(_HV_RESOURCE_CONTROL_TYPE,uint,unsigned __int64)
0x1400903f4  test    byte ptr [rsp+538h+var_478], 1
0x1400903fc  jz      short loc_140090411
0x1400903fe  mov     r8, rbx; void *
0x140090401  lea     rdx, [rsp+538h+var_478]; struct _HV_RESOURCE_CONTROL_SUPPORT_PROPERTY *
0x140090409  mov     rcx, rsi; this
0x14009040c  call    ?SetProcessorCacheAllocationOnLMClos@WorkerTaskMigrationSource@@AEAAXAEAU_HV_RESOURCE_CONTROL_SUPPORT_PROPERTY@@PEAX@Z; WorkerTaskMigrationSource::SetProcessorCacheAllocationOnLMClos(_HV_RESOURCE_CONTROL_SUPPORT_PROPERTY &,void *)
0x140090411  mov     rax, [rsi+10h]
0x140090415  mov     rcx, [rax+410h]
0x14009041c  mov     rax, [rcx]
0x14009041f  mov     edx, [rsi+474h]
0x140090425  mov     rax, [rax+2B0h]
0x14009042c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140090431  mov     rcx, [rsp+538h]; this
0x140090439  test    eax, eax
0x14009043b  jns     short loc_14009044D
0x14009043d  mov     r9d, eax; char *
0x140090440  mov     r8, r13; unsigned int
0x140090443  mov     edx, 123Fh; void *
0x140090448  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14009044d  mov     ebx, 0D1E2h
0x140090452  mov     ecx, ebx
0x140090454  call    VmlIsDebugTraceEnabled
0x140090459  test    eax, eax
0x14009045b  jz      short loc_1400904D0
0x14009045d  lea     rax, [rsp+538h+var_498]
0x140090465  cmp     [rsp+538h+var_480], 7
0x14009046e  cmova   rax, [rsp+538h+var_498]
0x140090477  lea     rdx, aNonlinear; "NonLinear"
0x14009047e  cmp     byte ptr [rsi+480h], 0
0x140090485  cmovz   r12, rdx
0x140090489  mov     [rsp+538h+var_4F8], rax
0x14009048e  mov     rax, [rsi+488h]
0x140090495  mov     [rsp+538h+var_500], rax
0x14009049a  mov     rax, [rsi+4A8h]
0x1400904a1  mov     [rsp+538h+var_508], rax
0x1400904a6  mov     rax, [rsi+490h]
0x1400904ad  mov     [rsp+538h+var_510], rax
0x1400904b2  mov     qword ptr [rsp+538h+var_518], r12
0x1400904b7  mov     r9d, r15d
0x1400904ba  mov     r8d, [rsi+474h]
0x1400904c1  lea     rdx, off_1402E4388; "MBA is enabled. Index:%u,InitialThrottl"...
0x1400904c8  mov     ecx, ebx
0x1400904ca  call    VmlDebugTraceEx
0x1400904cf  nop
0x1400904d0  lea     rcx, [rsp+538h+var_498]
0x1400904d8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400904dd  nop
0x1400904de  lea     rcx, [rsp+538h+var_4E8]
0x1400904e3  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?VidCloseStatisticsHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&VidCloseStatisticsHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&VidCloseStatisticsHandle(void *)>>(void)
0x1400904e8  nop
0x1400904e9  jmp     loc_14009056F
0x1400904ee  lea     rax, [rsp+538h+var_498]
0x1400904f6  cmp     [rsp+538h+var_480], 7
0x1400904ff  cmova   rax, [rsp+538h+var_498]
0x140090508  mov     rcx, [rsp+538h]; this
0x140090510  mov     [rsp+538h+var_510], rax; char *
0x140090515  lea     rax, aInvalidMbaThro_0; "Invalid MBA throttle strategy:%ws"
0x14009051c  mov     qword ptr [rsp+538h+var_518], rax; int
0x140090521  mov     r9d, 80070057h; char *
0x140090527  mov     r8, r13; unsigned int
0x14009052a  mov     edx, 11F0h; void *
0x14009052f  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
0x140090535  cmp     dword ptr [rsp+538h+var_4E8], 0
0x14009053a  jge     short loc_140090567
0x14009053c  mov     ebx, 41E2h
0x140090541  mov     ecx, ebx
0x140090543  call    VmlIsDebugTraceEnabled
0x140090548  test    eax, eax
  ... truncated ...
```
