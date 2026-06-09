# UniversalOrchestrator::SuspendSignal(void)

- ea: `0x1800716c0`
- end: `0x18007219f`
- name: `?SuspendSignal@UniversalOrchestrator@@UEAAJXZ`
- size: `2783`
- prototype: `__int64 __fastcall(UniversalOrchestrator *__hidden this)`
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180010890`
- `0x1800109f4`
- `0x180011680`
- `0x1800119a8`
- `0x18001b064`
- `0x1800420e0`
- `0x18006ea28`
- `0x180071600`
- `0x1800716c0`
- `0x1800740a4`
- `0x1800748f0`
- `0x1800dd930`
- `0x1800e4630`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180071b2d`
- `OLEAUT32!__imp_VariantInit` at `0x180071b2d`
- `OLEAUT32!__imp_VariantClear` at `0x18007210e`
- `OLEAUT32!__imp_VariantClear` at `0x18007210e`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x180071a32`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x180071c8f`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x180071cbf`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x180071a32`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x180071c8f`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x180071cbf`

## string_xrefs

- `0x180072152`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x180072172`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x18007218c`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x1800717fd`: `UniversalOrchestratorDisableIdleTask`
- `0x180071c56`: `Idle task creation blocked by OneSettings or by Wake on DC failure count`
- `0x180071927`: `UpdaterIdleTimeInMins`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
__int64 __fastcall UniversalOrchestrator::SuspendSignal(UniversalOrchestrator *this)
{
  __int64 *System; // rax
  _QWORD *v3; // rax
  UniversalOrchestrator *v4; // rcx
  char v5; // di
  const char *v6; // r9
  volatile signed __int32 *v7; // rbx
  volatile signed __int32 *v8; // rbx
  __int64 result; // rax
  __int64 *v10; // rax
  __int64 (__fastcall *v11)(__int64, __int128 *, __int64); // rbx
  __int16 *traits_2_unsigned_short; // rax
  __int64 v13; // r8
  const char *v14; // r9
  __int64 v15; // r11
  __int64 v16; // rax
  UniversalOrchestrator *v17; // rcx
  char v18; // di
  volatile signed __int32 *v19; // rbx
  volatile signed __int32 *v20; // rbx
  __int64 *v21; // rax
  int (__fastcall *v22)(__int64, __int128 *, __int128 *); // rbx
  int *v23; // rax
  const char *v24; // r9
  __int64 v25; // r11
  __int64 v26; // rax
  __int64 v27; // rbx
  volatile signed __int32 *v28; // rdi
  volatile signed __int32 *v29; // rdi
  __int64 *v30; // rax
  __int64 v31; // rax
  __int64 v32; // rsi
  void (__fastcall *v33)(__int64, __int128 *); // rdi
  volatile signed __int32 *v34; // rbx
  volatile signed __int32 *v35; // rbx
  __int64 *v36; // rax
  int (__fastcall *v37)(__int64, __int128 *, __int128 *); // rbx
  int *v38; // rax
  const char *v39; // r9
  __int64 v40; // r11
  __int64 v41; // rax
  __int64 v42; // rdi
  volatile signed __int32 *v43; // rbx
  volatile signed __int32 *v44; // rbx
  signed __int64 v45; // rbx
  __int64 *v46; // rax
  __int64 v47; // r10
  __int64 v48; // rax
  __int64 v49; // rax
  __int64 v50; // rax
  int SystemValueOrDefault; // edi
  volatile signed __int32 *v52; // rbx
  volatile signed __int32 *v53; // rbx
  unsigned int v54; // edi
  __int64 *v55; // rax
  __int64 v56; // rax
  __int64 v57; // r10
  void (__fastcall *v58)(__int64, __int128 *, __int128 *, __int128 *, _DWORD *); // r11
  __int64 v59; // rax
  __int64 v60; // rax
  __int64 v61; // rax
  volatile signed __int32 *v62; // rbx
  volatile signed __int32 *v63; // rbx
  __int64 *v64; // rax
  _QWORD *v65; // rax
  volatile signed __int32 *v66; // rbx
  volatile signed __int32 *v67; // rbx
  __int128 v68; // [rsp+30h] [rbp-E8h] BYREF
  __int128 v69; // [rsp+40h] [rbp-D8h] BYREF
  __int128 v70; // [rsp+50h] [rbp-C8h] BYREF
  __int128 v71; // [rsp+60h] [rbp-B8h] BYREF
  __int128 v72; // [rsp+70h] [rbp-A8h] BYREF
  __int128 v73; // [rsp+80h] [rbp-98h] BYREF
  __int128 v74; // [rsp+90h] [rbp-88h] BYREF
  __int64 v75; // [rsp+A0h] [rbp-78h] BYREF
  volatile signed __int32 *v76; // [rsp+A8h] [rbp-70h]
  _DWORD v77[8]; // [rsp+B0h] [rbp-68h] BYREF
  char v78; // [rsp+D0h] [rbp-48h]
  VARIANTARG pvarg; // [rsp+D8h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+0h]

  try
  {
    System = SystemInterface::Service::GetSystem((__int64 *)&v69);
    v3 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)*System + 56LL))(*System, &v70);
    v5 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v3 + 80LL))(*v3);
    v7 = (volatile signed __int32 *)*((_QWORD *)&v70 + 1);
    if ( *((_QWORD *)&v70 + 1) )
    {
      v4 = (UniversalOrchestrator *)(unsigned int)_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v70 + 1)
                                                                                                  + 8LL));
      if ( !(_DWORD)v4 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v7)(v7);
        if ( _InterlockedExchangeAdd(v7 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v7 + 8LL))(v7);
      }
    }
    v8 = (volatile signed __int32 *)*((_QWORD *)&v69 + 1);
    if ( *((_QWORD *)&v69 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v69 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v8)(v8);
        if ( _InterlockedExchangeAdd(v8 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v8 + 8LL))(v8);
      }
    }
    if ( v5 )
    {
      result = 0;
    }
    else
    {
      if ( UniversalOrchestrator::NeedPreHibernateTask(v4) )
      {
        v10 = SystemInterface::Service::GetSystem((__int64 *)&v72);
        v11 = *(__int64 (__fastcall **)(__int64, __int128 *, __int64))(**(_QWORD **)(*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)*v10 + 40LL))(
                                                                                      *v10,
                                                                                      &v69)
                                                                     + 64LL);
        traits_2_unsigned_short = (__int16 *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                                               L"UniversalOrchestratorDisableIdleTask",
                                               word_18012169A,
                                               0);
        if ( traits_2_unsigned_short == word_18012169A
          || (v16 = ((char *)traits_2_unsigned_short - (char *)L"UniversalOrchestratorDisableIdleTask") >> 1, v16 == -1) )
        {
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0xC9,
            (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
            v14);
        }
        *(_QWORD *)&v68 = L"UniversalOrchestratorDisableIdleTask";
        *((_QWORD *)&v68 + 1) = v16;
        v70 = v68;
        LOBYTE(v13) = 1;
        v18 = v11(v15, &v70, v13);
        v19 = (volatile signed __int32 *)*((_QWORD *)&v69 + 1);
        if ( *((_QWORD *)&v69 + 1) )
        {
          v17 = (UniversalOrchestrator *)(unsigned int)_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v69 + 1) + 8LL));
          if ( !(_DWORD)v17 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v19)(v19);
            if ( _InterlockedExchangeAdd(v19 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v19 + 8LL))(v19);
          }
        }
        v20 = (volatile signed __int32 *)*((_QWORD *)&v72 + 1);
        if ( *((_QWORD *)&v72 + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v72 + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v20)(v20);
            if ( _InterlockedExchangeAdd(v20 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v20 + 8LL))(v20);
          }
        }
        if ( !v18 || UniversalOrchestrator::IsWakeToRunDisabled(v17) )
        {
          *(_QWORD *)&v68 = L"Idle task creation blocked by OneSettings or by Wake on DC failure count";
          *((_QWORD *)&v68 + 1) = 72;
          v71 = v68;
          SystemInterface::Log<>(&v71);
        }
        else
        {
          v21 = SystemInterface::Service::GetSystem((__int64 *)&v71);
          v22 = *(int (__fastcall **)(__int64, __int128 *, __int128 *))(**(_QWORD **)(*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)*v21 + 40LL))(
                                                                                       *v21,
                                                                                       &v69)
                                                                      + 56LL);
          LODWORD(v72) = 60;
          v23 = (int *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                         L"UpdaterIdleTimeInMins",
                         &dword_1801217D4,
                         0);
          if ( v23 == &dword_1801217D4 || (v26 = ((char *)v23 - (char *)L"UpdaterIdleTimeInMins") >> 1, v26 == -1) )
            wil::details::in1diag3::_FailFast_Unexpected(
              retaddr,
              (void *)0xC9,
              (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
              v24);
          *(_QWORD *)&v68 = L"UpdaterIdleTimeInMins";
          *((_QWORD *)&v68 + 1) = v26;
          v70 = v68;
          v27 = v22(v25, &v70, &v72);
          v28 = (volatile signed __int32 *)*((_QWORD *)&v69 + 1);
          if ( *((_QWORD *)&v69 + 1) )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v69 + 1) + 8LL), 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v28)(v28);
              if ( _InterlockedExchangeAdd(v28 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v28 + 8LL))(v28);
            }
          }
          v29 = (volatile signed __int32 *)*((_QWORD *)&v71 + 1);
          if ( *((_QWORD *)&v71 + 1) )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v71 + 1) + 8LL), 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v29)(v29);
              if ( _InterlockedExchangeAdd(v29 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v29 + 8LL))(v29);
            }
          }
          v30 = SystemInterface::Service::GetSystem((__int64 *)&v70);
          v31 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)*v30 + 24LL))(*v30, &v71);
          v32 = *(_QWORD *)v31;
          v33 = *(void (__fastcall **)(__int64, __int128 *))(**(_QWORD **)v31 + 64LL);
          *(_QWORD *)&v68 = 0;
          GetSystemTimePreciseAsFileTime(&v68);
          *(_QWORD *)&v72 = (unsigned int)v68 + ((unsigned __int64)DWORD1(v68) << 32) + 600000000 * (v27 - 194074560);
          v33(v32, &v72);
          v34 = (volatile signed __int32 *)*((_QWORD *)&v71 + 1);
          if ( *((_QWORD *)&v71 + 1) )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v71 + 1) + 8LL), 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v34)(v34);
              if ( _InterlockedExchangeAdd(v34 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v34 + 8LL))(v34);
            }
          }
          v35 = (volatile signed __int32 *)*((_QWORD *)&v70 + 1);
          if ( *((_QWORD *)&v70 + 1) )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v70 + 1) + 8LL), 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v35)(v35);
              if ( _InterlockedExchangeAdd(v35 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v35 + 8LL))(v35);
            }
          }
        }
      }
      if ( *((_BYTE *)this + 104) )
      {
        *(_QWORD *)&v68 = L"There is an active DC wake session to track";
        *((_QWORD *)&v68 + 1) = 43;
        v71 = v68;
        SystemInterface::Log<>(&v71);
        VariantInit(&pvarg);
        v36 = SystemInterface::Service::GetSystem((__int64 *)&v69);
        v37 = *(int (__fastcall **)(__int64, __int128 *, __int128 *))(**(_QWORD **)(*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)*v36 + 40LL))(
                                                                                     *v36,
                                                                                     &v70)
                                                                    + 56LL);
        LODWORD(v72) = 4320;
        v38 = (int *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                       L"UniversalOrchestratorBatteryWakeMinutesToWait",
                       &dword_18012183C,
                       0);
        if ( v38 == &dword_18012183C
          || (v41 = ((char *)v38 - (char *)L"UniversalOrchestratorBatteryWakeMinutesToWait") >> 1, v41 == -1) )
        {
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0xC9,
            (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
            v39);
        }
        *(_QWORD *)&v68 = L"UniversalOrchestratorBatteryWakeMinutesToWait";
        *((_QWORD *)&v68 + 1) = v41;
        v71 = v68;
        v42 = v37(v40, &v71, &v72);
        v43 = (volatile signed __int32 *)*((_QWORD *)&v70 + 1);
        if ( *((_QWORD *)&v70 + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v70 + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v43)(v43);
            if ( _InterlockedExchangeAdd(v43 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v43 + 8LL))(v43);
          }
        }
        v44 = (volatile signed __int32 *)*((_QWORD *)&v69 + 1);
        if ( *((_QWORD *)&v69 + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v69 + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v44)(v44);
            if ( _InterlockedExchangeAdd(v44 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v44 + 8LL))(v44);
          }
        }
        if ( !*((_BYTE *)this + 104) )
          std::_Throw_bad_optional_access();
        *(_QWORD *)&v68 = 0;
        GetSystemTimePreciseAsFileTime(&v68);
        v45 = (unsigned int)v68 + ((unsigned __int64)DWORD1(v68) << 32) - *((_QWORD *)this + 12) - 116444736000000000LL;
        *(_QWORD *)&v68 = 0;
        GetSystemTimePreciseAsFileTime(&v68);
        if ( *((_QWORD *)this + 12) >= (signed __int64)((unsigned int)v68
                                                      + ((unsigned __int64)DWORD1(v68) << 32)
                                                      - 116444736000000000LL)
          || v45 == 600000000 * v42
          || v45 < 600000000 * v42 )
        {
          *((_BYTE *)this + 104) = 0;
        }
        else
        {
          LODWORD(v72) = (int)v45 / 600000000;
          LODWORD(v68) = v42;
          *(_QWORD *)&v69 = L"threshold: {}, minutesSinceWake: {}";
          *((_QWORD *)&v69 + 1) = 35;
          v71 = v69;
          SystemInterface::Log<int,int>(&v71, &v68, &v72);
          v46 = SystemInterface::Service::GetSystem((__int64 *)&v73);
          v47 = *(_QWORD *)(*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)*v46 + 32LL))(*v46, &v74);
          LODWORD(v68) = 0;
          v48 = -1;
          do
            ++v48;
          while ( UniversalOrchestrator::sc_wakeOnDcFailureCount[v48] );
          *(_QWORD *)&v69 = UniversalOrchestrator::sc_wakeOnDcFailureCount;
          *((_QWORD *)&v69 + 1) = v48;
          v49 = -1;
          do
            ++v49;
          while ( SystemInterface::Registry::USO_USCHEDULER_ROOT[v49] );
          *(_QWORD *)&v72 = SystemInterface::Registry::USO_USCHEDULER_ROOT;
          *((_QWORD *)&v72 + 1) = v49;
          *(_QWORD *)&v70 = SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID;
          v50 = -1;
          do
            ++v50;
          while ( SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID[v50] );
          *((_QWORD *)&v70 + 1) = v50;
          v71 = v69;
          v69 = v72;
          SystemValueOrDefault = SystemInterface::Registry::GetSystemValueOrDefault(
                                   v47,
                                   (unsigned int)&v70,
                                   (unsigned int)&v69,
                                   (unsigned int)&v71,
                                   (__int64)&v68);
          v52 = (volatile signed __int32 *)*((_QWORD *)&v74 + 1);
          if ( *((_QWORD *)&v74 + 1) )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v74 + 1) + 8LL), 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v52)(v52);
              if ( _InterlockedExchangeAdd(v52 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v52 + 8LL))(v52);
            }
          }
          v53 = (volatile signed __int32 *)*((_QWORD *)&v73 + 1);
          if ( *((_QWORD *)&v73 + 1) )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v73 + 1) + 8LL), 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v53)(v53);
              if ( _InterlockedExchangeAdd(v53 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v53 + 8LL))(v53);
            }
          }
          v54 = SystemValueOrDefault + 1;
          v55 = SystemInterface::Service::GetSystem(&v75);
          v56 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)*v55 + 32LL))(*v55, &v72);
          v57 = *(_QWORD *)v56;
          v58 = *(void (__fastcall **)(__int64, __int128 *, __int128 *, __int128 *, _DWORD *))(**(_QWORD **)v56 + 64LL);
          v77[0] = v54;
          v78 = 0;
          v59 = -1;
          do
            ++v59;
          while ( UniversalOrchestrator::sc_wakeOnDcFailureCount[v59] );
          *(_QWORD *)&v70 = UniversalOrchestrator::sc_wakeOnDcFailureCount;
          *((_QWORD *)&v70 + 1) = v59;
          v60 = -1;
          do
            ++v60;
          while ( SystemInterface::Registry::USO_USCHEDULER_ROOT[v60] );
          *(_QWORD *)&v69 = SystemInterface::Registry::USO_USCHEDULER_ROOT;
          *((_QWORD *)&v69 + 1) = v60;
          *(_QWORD *)&v68 = SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID;
          v61 = -1;
          do
            ++v61;
          while ( SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID[v61] );
          *((_QWORD *)&v68 + 1) = v61;
          v73 = v70;
          v74 = v69;
          v71 = v68;
          v58(v57, &v71, &v74, &v73, v77);
          if ( v78 != -1 && v78 && v78 != 1 )
            std::wstring::~wstring(v77);
          v62 = (volatile signed __int32 *)*((_QWORD *)&v72 + 1);
          if ( *((_QWORD *)&v72 + 1) )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v72 + 1) + 8LL), 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v62)(v62);
              if ( _InterlockedExchangeAdd(v62 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v62 + 8LL))(v62);
            }
          }
          v63 = v76;
          if ( v76 )
          {
            if ( _InterlockedExchangeAdd(v76 + 2, 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v63)(v63);
              if ( _InterlockedExchangeAdd(v63 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v63 + 8LL))(v63);
            }
          }
          v64 = SystemInterface::Service::GetSystem((__int64 *)&v73);
          v65 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)*v64 + 104LL))(*v64, &v75);
          (*(void (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v65 + 96LL))(*v65, v54);
          v66 = v76;
          if ( v76 )
          {
            if ( _InterlockedExchangeAdd(v76 + 2, 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v66)(v66);
              if ( _InterlockedExchangeAdd(v66 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v66 + 8LL))(v66);
            }
          }
          v67 = (volatile signed __int32 *)*((_QWORD *)&v73 + 1);
          if ( *((_QWORD *)&v73 + 1) )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v73 + 1) + 8LL), 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v67)(v67);
              if ( _InterlockedExchangeAdd(v67 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v67 + 8LL))(v67);
            }
          }
        }
        VariantClear(&pvarg);
      }
      result = 0;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x1DC,
                           (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\UnivOrchLib\\UniversalOrchestratorHelper.cpp",
                           v6);
  }
  return result;
}

```

## disassembly

```asm
0x1800716c0  mov     [rsp+arg_8], rbx
0x1800716c5  mov     [rsp+arg_10], rsi
0x1800716ca  mov     [rsp+arg_18], rdi
0x1800716cf  push    r12
0x1800716d1  push    r14
0x1800716d3  push    r15
0x1800716d5  sub     rsp, 100h
0x1800716dc  mov     rax, cs:__security_cookie
0x1800716e3  xor     rax, rsp
0x1800716e6  mov     [rsp+118h+var_28], rax
0x1800716ee  mov     r15, rcx
0x1800716f1  lea     rcx, [rsp+118h+var_D8]
0x1800716f6  call    ?GetSystem@Service@SystemInterface@@YA?AV?$shared_ptr@VSystem@Service@SystemInterface@@@std@@XZ; SystemInterface::Service::GetSystem(void)
0x1800716fb  nop
0x1800716fc  mov     rcx, [rax]
0x1800716ff  mov     rax, [rcx]
0x180071702  lea     rdx, [rsp+118h+var_C8]
0x180071707  mov     rax, [rax+38h]
0x18007170b  call    _guard_dispatch_icall
0x180071710  nop
0x180071711  mov     rcx, [rax]
0x180071714  mov     rax, [rcx]
0x180071717  mov     rax, [rax+50h]
0x18007171b  call    _guard_dispatch_icall
0x180071720  mov     dil, al
0x180071723  mov     rbx, qword ptr [rsp+118h+var_C8+8]
0x180071728  xor     r12d, r12d
0x18007172b  or      r14, 0FFFFFFFFFFFFFFFFh
0x18007172f  test    rbx, rbx
0x180071732  jz      short loc_18007176C
0x180071734  mov     ecx, r14d
0x180071737  lock xadd [rbx+8], ecx
0x18007173c  add     ecx, r14d
0x18007173f  jnz     short loc_18007176C
0x180071741  mov     rax, [rbx]
0x180071744  mov     rcx, rbx
0x180071747  mov     rax, [rax]
0x18007174a  call    _guard_dispatch_icall
0x18007174f  mov     eax, r14d
0x180071752  lock xadd [rbx+0Ch], eax
0x180071757  add     eax, r14d
0x18007175a  jnz     short loc_18007176C
0x18007175c  mov     rax, [rbx]
0x18007175f  mov     rcx, rbx
0x180071762  mov     rax, [rax+8]
0x180071766  call    _guard_dispatch_icall
0x18007176b  nop
0x18007176c  mov     rbx, qword ptr [rsp+118h+var_D8+8]
0x180071771  test    rbx, rbx
0x180071774  jz      short loc_1800717AD
0x180071776  mov     eax, r14d
0x180071779  lock xadd [rbx+8], eax
0x18007177e  add     eax, r14d
0x180071781  jnz     short loc_1800717AD
0x180071783  mov     rax, [rbx]
0x180071786  mov     rcx, rbx
0x180071789  mov     rax, [rax]
0x18007178c  call    _guard_dispatch_icall
0x180071791  mov     eax, r14d
0x180071794  lock xadd [rbx+0Ch], eax
0x180071799  add     eax, r14d
0x18007179c  jnz     short loc_1800717AD
0x18007179e  mov     rax, [rbx]
0x1800717a1  mov     rcx, rbx
0x1800717a4  mov     rax, [rax+8]
0x1800717a8  call    _guard_dispatch_icall
0x1800717ad  test    dil, dil
0x1800717b0  jz      short loc_1800717B9
0x1800717b2  xor     eax, eax
0x1800717b4  jmp     loc_18007211C
0x1800717b9  call    ?NeedPreHibernateTask@UniversalOrchestrator@@AEAA_NXZ; UniversalOrchestrator::NeedPreHibernateTask(void)
0x1800717be  test    al, al
0x1800717c0  jz      loc_180071AF1
0x1800717c6  lea     rcx, [rsp+118h+var_A8]
0x1800717cb  call    ?GetSystem@Service@SystemInterface@@YA?AV?$shared_ptr@VSystem@Service@SystemInterface@@@std@@XZ; SystemInterface::Service::GetSystem(void)
0x1800717d0  nop
0x1800717d1  mov     rcx, [rax]
0x1800717d4  mov     rax, [rcx]
0x1800717d7  lea     rdx, [rsp+118h+var_D8]
0x1800717dc  mov     rax, [rax+28h]
0x1800717e0  call    _guard_dispatch_icall
0x1800717e5  nop
0x1800717e6  mov     r11, [rax]
0x1800717e9  mov     rax, [r11]
0x1800717ec  mov     rbx, [rax+40h]
0x1800717f0  xor     r8d, r8d
0x1800717f3  lea     rdi, word_18012169A
0x1800717fa  mov     rdx, rdi
0x1800717fd  lea     rsi, aUniversalorche_2; "UniversalOrchestratorDisableIdleTask"
0x180071804  mov     rcx, rsi
0x180071807  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_2_unsigned_short_
0x18007180c  cmp     rax, rdi
0x18007180f  jz      loc_180072184
0x180071815  sub     rax, rsi
0x180071818  sar     rax, 1
0x18007181b  cmp     rax, r14
0x18007181e  jz      loc_180072184
0x180071824  mov     qword ptr [rsp+118h+var_E8], rsi
0x180071829  mov     qword ptr [rsp+118h+var_E8+8], rax
0x18007182e  movaps  xmm0, [rsp+118h+var_E8]
0x180071833  movdqa  [rsp+118h+var_C8], xmm0
0x180071839  mov     r8b, 1
0x18007183c  lea     rdx, [rsp+118h+var_C8]
0x180071841  mov     rcx, r11
0x180071844  mov     rax, rbx
0x180071847  call    _guard_dispatch_icall
0x18007184c  mov     dil, al
0x18007184f  mov     rbx, qword ptr [rsp+118h+var_D8+8]
0x180071854  test    rbx, rbx
0x180071857  jz      short loc_180071891
0x180071859  mov     ecx, r14d
0x18007185c  lock xadd [rbx+8], ecx
0x180071861  add     ecx, r14d
0x180071864  jnz     short loc_180071891
0x180071866  mov     rax, [rbx]
0x180071869  mov     rcx, rbx
0x18007186c  mov     rax, [rax]
0x18007186f  call    _guard_dispatch_icall
0x180071874  mov     eax, r14d
0x180071877  lock xadd [rbx+0Ch], eax
0x18007187c  add     eax, r14d
0x18007187f  jnz     short loc_180071891
0x180071881  mov     rax, [rbx]
0x180071884  mov     rcx, rbx
0x180071887  mov     rax, [rax+8]
0x18007188b  call    _guard_dispatch_icall
0x180071890  nop
0x180071891  mov     rbx, qword ptr [rsp+118h+var_A8+8]
0x180071896  test    rbx, rbx
0x180071899  jz      short loc_1800718D2
0x18007189b  mov     eax, r14d
0x18007189e  lock xadd [rbx+8], eax
0x1800718a3  add     eax, r14d
0x1800718a6  jnz     short loc_1800718D2
0x1800718a8  mov     rax, [rbx]
0x1800718ab  mov     rcx, rbx
0x1800718ae  mov     rax, [rax]
0x1800718b1  call    _guard_dispatch_icall
0x1800718b6  mov     eax, r14d
0x1800718b9  lock xadd [rbx+0Ch], eax
0x1800718be  add     eax, r14d
0x1800718c1  jnz     short loc_1800718D2
0x1800718c3  mov     rax, [rbx]
0x1800718c6  mov     rcx, rbx
0x1800718c9  mov     rax, [rax+8]
0x1800718cd  call    _guard_dispatch_icall
0x1800718d2  test    dil, dil
0x1800718d5  jz      loc_180071C56
0x1800718db  call    ?IsWakeToRunDisabled@UniversalOrchestrator@@AEAA_NXZ; UniversalOrchestrator::IsWakeToRunDisabled(void)
0x1800718e0  test    al, al
0x1800718e2  jnz     loc_180071C56
0x1800718e8  lea     rcx, [rsp+118h+var_B8]
0x1800718ed  call    ?GetSystem@Service@SystemInterface@@YA?AV?$shared_ptr@VSystem@Service@SystemInterface@@@std@@XZ; SystemInterface::Service::GetSystem(void)
0x1800718f2  nop
0x1800718f3  mov     rcx, [rax]
0x1800718f6  mov     rax, [rcx]
0x1800718f9  lea     rdx, [rsp+118h+var_D8]
0x1800718fe  mov     rax, [rax+28h]
0x180071902  call    _guard_dispatch_icall
0x180071907  nop
0x180071908  mov     r11, [rax]
0x18007190b  mov     rax, [r11]
0x18007190e  mov     rbx, [rax+38h]
0x180071912  mov     dword ptr [rsp+118h+var_A8], 3Ch ; '<'
0x18007191a  xor     r8d, r8d
0x18007191d  lea     rdi, dword_1801217D4
0x180071924  mov     rdx, rdi
0x180071927  lea     rsi, aUpdateridletim; "UpdaterIdleTimeInMins"
0x18007192e  mov     rcx, rsi
0x180071931  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_2_unsigned_short_
0x180071936  cmp     rax, rdi
0x180071939  jz      loc_18007216A
0x18007193f  sub     rax, rsi
0x180071942  sar     rax, 1
0x180071945  cmp     rax, r14
0x180071948  jz      loc_18007216A
0x18007194e  mov     qword ptr [rsp+118h+var_E8], rsi
0x180071953  mov     qword ptr [rsp+118h+var_E8+8], rax
0x180071958  movaps  xmm0, [rsp+118h+var_E8]
0x18007195d  movdqa  [rsp+118h+var_C8], xmm0
0x180071963  lea     r8, [rsp+118h+var_A8]
0x180071968  lea     rdx, [rsp+118h+var_C8]
0x18007196d  mov     rcx, r11
0x180071970  mov     rax, rbx
0x180071973  call    _guard_dispatch_icall
0x180071978  movsxd  rbx, eax
0x18007197b  mov     rdi, qword ptr [rsp+118h+var_D8+8]
0x180071980  test    rdi, rdi
0x180071983  jz      short loc_1800719BD
0x180071985  mov     eax, r14d
0x180071988  lock xadd [rdi+8], eax
0x18007198d  add     eax, r14d
0x180071990  jnz     short loc_1800719BD
0x180071992  mov     rax, [rdi]
0x180071995  mov     rcx, rdi
0x180071998  mov     rax, [rax]
0x18007199b  call    _guard_dispatch_icall
0x1800719a0  mov     eax, r14d
0x1800719a3  lock xadd [rdi+0Ch], eax
0x1800719a8  add     eax, r14d
0x1800719ab  jnz     short loc_1800719BD
0x1800719ad  mov     rax, [rdi]
0x1800719b0  mov     rcx, rdi
0x1800719b3  mov     rax, [rax+8]
0x1800719b7  call    _guard_dispatch_icall
0x1800719bc  nop
0x1800719bd  mov     rdi, qword ptr [rsp+118h+var_B8+8]
0x1800719c2  test    rdi, rdi
0x1800719c5  jz      short loc_1800719FE
0x1800719c7  mov     eax, r14d
0x1800719ca  lock xadd [rdi+8], eax
0x1800719cf  add     eax, r14d
0x1800719d2  jnz     short loc_1800719FE
0x1800719d4  mov     rax, [rdi]
0x1800719d7  mov     rcx, rdi
0x1800719da  mov     rax, [rax]
0x1800719dd  call    _guard_dispatch_icall
0x1800719e2  mov     eax, r14d
0x1800719e5  lock xadd [rdi+0Ch], eax
0x1800719ea  add     eax, r14d
0x1800719ed  jnz     short loc_1800719FE
0x1800719ef  mov     rax, [rdi]
0x1800719f2  mov     rcx, rdi
0x1800719f5  mov     rax, [rax+8]
0x1800719f9  call    _guard_dispatch_icall
0x1800719fe  lea     rcx, [rsp+118h+var_C8]
0x180071a03  call    ?GetSystem@Service@SystemInterface@@YA?AV?$shared_ptr@VSystem@Service@SystemInterface@@@std@@XZ; SystemInterface::Service::GetSystem(void)
0x180071a08  nop
0x180071a09  mov     rcx, [rax]
0x180071a0c  mov     rax, [rcx]
0x180071a0f  lea     rdx, [rsp+118h+var_B8]
0x180071a14  mov     rax, [rax+18h]
0x180071a18  call    _guard_dispatch_icall
0x180071a1d  nop
0x180071a1e  mov     rsi, [rax]
0x180071a21  mov     rax, [rsi]
0x180071a24  mov     rdi, [rax+40h]
0x180071a28  mov     qword ptr [rsp+118h+var_E8], r12
0x180071a2d  lea     rcx, [rsp+118h+var_E8]
0x180071a32  call    cs:__imp_GetSystemTimePreciseAsFileTime
0x180071a38  lea     rdx, [rbx-0B9157C0h]
0x180071a3f  imul    r8, rdx, 23C34600h
0x180071a46  mov     edx, dword ptr [rsp+118h+var_E8+4]
0x180071a4a  shl     rdx, 20h
0x180071a4e  add     r8, rdx
0x180071a51  mov     edx, dword ptr [rsp+118h+var_E8]
0x180071a55  add     r8, rdx
0x180071a58  mov     qword ptr [rsp+118h+var_A8], r8
0x180071a5d  lea     rdx, [rsp+118h+var_A8]
0x180071a62  mov     rcx, rsi
0x180071a65  mov     rax, rdi
0x180071a68  call    _guard_dispatch_icall
0x180071a6d  nop
0x180071a6e  mov     rbx, qword ptr [rsp+118h+var_B8+8]
0x180071a73  test    rbx, rbx
0x180071a76  jz      short loc_180071AB0
0x180071a78  mov     eax, r14d
0x180071a7b  lock xadd [rbx+8], eax
0x180071a80  add     eax, r14d
0x180071a83  jnz     short loc_180071AB0
0x180071a85  mov     rax, [rbx]
0x180071a88  mov     rcx, rbx
0x180071a8b  mov     rax, [rax]
0x180071a8e  call    _guard_dispatch_icall
0x180071a93  mov     eax, r14d
0x180071a96  lock xadd [rbx+0Ch], eax
0x180071a9b  add     eax, r14d
0x180071a9e  jnz     short loc_180071AB0
0x180071aa0  mov     rax, [rbx]
0x180071aa3  mov     rcx, rbx
0x180071aa6  mov     rax, [rax+8]
0x180071aaa  call    _guard_dispatch_icall
0x180071aaf  nop
0x180071ab0  mov     rbx, qword ptr [rsp+118h+var_C8+8]
0x180071ab5  test    rbx, rbx
0x180071ab8  jz      short loc_180071AF1
0x180071aba  mov     eax, r14d
0x180071abd  lock xadd [rbx+8], eax
0x180071ac2  add     eax, r14d
0x180071ac5  jnz     short loc_180071AF1
0x180071ac7  mov     rax, [rbx]
0x180071aca  mov     rcx, rbx
0x180071acd  mov     rax, [rax]
0x180071ad0  call    _guard_dispatch_icall
0x180071ad5  mov     eax, r14d
0x180071ad8  lock xadd [rbx+0Ch], eax
0x180071add  add     eax, r14d
0x180071ae0  jnz     short loc_180071AF1
0x180071ae2  mov     rax, [rbx]
0x180071ae5  mov     rcx, rbx
0x180071ae8  mov     rax, [rax+8]
0x180071aec  call    _guard_dispatch_icall
0x180071af1  cmp     [r15+68h], r12b
0x180071af5  jz      loc_180072114
0x180071afb  lea     rax, aThereIsAnActiv; "There is an active DC wake session to t"...
0x180071b02  mov     qword ptr [rsp+118h+var_E8], rax
0x180071b07  mov     qword ptr [rsp+118h+var_E8+8], 2Bh ; '+'
0x180071b10  movaps  xmm0, [rsp+118h+var_E8]
0x180071b15  movdqa  [rsp+118h+var_B8], xmm0
0x180071b1b  lea     rcx, [rsp+118h+var_B8]
  ... truncated ...
```
