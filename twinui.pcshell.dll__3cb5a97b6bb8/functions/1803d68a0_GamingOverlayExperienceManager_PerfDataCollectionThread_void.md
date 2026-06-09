# GamingOverlayExperienceManager::PerfDataCollectionThread(void)

- ea: `0x1803d68a0`
- end: `0x1803d71ff`
- name: `?PerfDataCollectionThread@GamingOverlayExperienceManager@@AEAAJXZ`
- size: `2399`
- prototype: `__int64 __fastcall(GamingOverlayExperienceManager *__hidden this)`
- caller_count: `1`
- callee_count: `32`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1803dac30`

## callees

- `0x1800134f8`
- `0x1800237c8`
- `0x180031c70`
- `0x180051b40`
- `0x180056880`
- `0x18006047c`
- `0x18014acc0`
- `0x1801b4418`
- `0x180205a50`
- `0x180225300`
- `0x180271658`
- `0x180356360`
- `0x18035b7fd`
- `0x1803c7da4`
- `0x1803c7ffc`
- `0x1803cdbdc`
- `0x1803cedac`
- `0x1803cfc7c`
- `0x1803d6878`
- `0x1803d68a0`
- `0x1803db7f8`
- `0x1803de45c`
- `0x1803de6a0`
- `0x1803df360`
- `0x1803df4dc`
- `0x1803e006c`
- `0x1803e2f94`
- `0x1803e3070`
- `0x1803e3178`
- `0x1803e3364`
- `0x1803e34d4`
- `0x1806fa010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1803d70da`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1803d70da`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1803d6a53`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1803d6dac`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1803d6fd7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1803d704e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1803d70cf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1803d6a53`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1803d6dac`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1803d6fd7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1803d704e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1803d70cf`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1803d6ad1`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1803d6ad1`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x1803d6b2b`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x1803d6b2b`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1803d6a79`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1803d6a79`
- `api-ms-win-crt-time-l1-1-0!clock` at `0x1803d6901`
- `api-ms-win-crt-time-l1-1-0!clock` at `0x1803d6a65`
- `api-ms-win-crt-time-l1-1-0!clock` at `0x1803d6f09`
- `api-ms-win-crt-time-l1-1-0!clock` at `0x1803d6901`
- `api-ms-win-crt-time-l1-1-0!clock` at `0x1803d6a65`
- `api-ms-win-crt-time-l1-1-0!clock` at `0x1803d6f09`
- `pdh!PdhCollectQueryData` at `0x1803d6dd8`
- `pdh!PdhCollectQueryData` at `0x1803d6dd8`
- `pdh!PdhAddCounterW` at `0x1803d697e`
- `pdh!PdhAddCounterW` at `0x1803d697e`
- `pdh!PdhOpenQueryW` at `0x1803d6933`
- `pdh!PdhOpenQueryW` at `0x1803d6933`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall GamingOverlayExperienceManager::PerfDataCollectionThread(GamingOverlayExperienceManager *this)
{
  PDH_STATUS v2; // eax
  GamingOverlayExperienceManager *v3; // rcx
  int v4; // edx
  _QWORD *v5; // r14
  PDH_STATUS v6; // eax
  GamingOverlayExperienceManager *v7; // rcx
  int v8; // edx
  GamingOverlayExperienceManager *v9; // rcx
  int updated; // eax
  int PcwCounter; // ebx
  __int64 v12; // rdx
  DWORD v13; // edi
  unsigned __int64 v14; // r13
  _QWORD *v15; // r15
  DWORD v16; // ebx
  __int64 v17; // rax
  HRESULT v18; // eax
  BOOL ExitCodeProcess; // eax
  __int64 v20; // rdi
  __int64 (__fastcall *v21)(__int64, __int128 *, unsigned int *); // rbx
  int v22; // eax
  unsigned __int64 v23; // rax
  unsigned int v24; // r15d
  __int128 v25; // rcx
  _OWORD *v26; // rdi
  __int64 v27; // rax
  __int64 v28; // rbx
  __int64 v29; // rdx
  unsigned __int64 v30; // r12
  __int32 v31; // r14d
  int v32; // ebx
  unsigned int v33; // r15d
  unsigned __int64 *v34; // rax
  __int32 v35; // ecx
  void **v36; // rdi
  _DWORD *v37; // rdx
  PDH_STATUS Data; // eax
  GamingOverlayExperienceManager *v39; // rcx
  int v40; // edx
  wil::details::in1diag3 *v41; // rcx
  unsigned int *v42; // rbx
  int RawData; // eax
  GamingOverlayExperienceManager *v44; // rcx
  int v45; // edx
  Cpu *v46; // rcx
  __int64 v47; // r8
  unsigned int v48; // edx
  GamingOverlayExperienceManager *v49; // rcx
  Cpu *v50; // rcx
  _QWORD *v51; // rbx
  __int64 v52; // rcx
  double v53; // xmm0_8
  __int64 v54; // rax
  double v55; // xmm0_8
  double *v56; // rdx
  _QWORD *v57; // rbx
  _QWORD *v58; // rdx
  _QWORD *v59; // rbx
  struct _RTL_CRITICAL_SECTION *v60; // rax
  struct _RTL_CRITICAL_SECTION **v61; // rdx
  __int64 v62; // rdx
  unsigned __int64 v64; // r9
  int ppv; // [rsp+20h] [rbp-E0h]
  LPCRITICAL_SECTION v66; // [rsp+30h] [rbp-D0h] BYREF
  int v67; // [rsp+38h] [rbp-C8h] BYREF
  clock_t v68; // [rsp+3Ch] [rbp-C4h]
  DWORD v69; // [rsp+40h] [rbp-C0h]
  HANDLE hProcess; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v71[3]; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v72[3]; // [rsp+68h] [rbp-98h] BYREF
  char v73[8]; // [rsp+80h] [rbp-80h] BYREF
  char v74[8]; // [rsp+88h] [rbp-78h] BYREF
  char v75[8]; // [rsp+90h] [rbp-70h] BYREF
  char v76[24]; // [rsp+98h] [rbp-68h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+B0h] [rbp-50h] BYREF
  unsigned int v78; // [rsp+B8h] [rbp-48h] BYREF
  LPVOID v79; // [rsp+C0h] [rbp-40h] BYREF
  PDH_HQUERY phQuery; // [rsp+C8h] [rbp-38h] BYREF
  __int128 v81; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v82; // [rsp+E0h] [rbp-20h]
  unsigned __int64 v83; // [rsp+F0h] [rbp-10h]
  __int128 v84; // [rsp+F8h] [rbp-8h] BYREF
  void *v85[2]; // [rsp+108h] [rbp+8h] BYREF
  struct _COUNTER_BUFFER *v86[2]; // [rsp+118h] [rbp+18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+88h]

  v84 = 0u;
  v78 = 0;
  v81 = 0;
  v82 = 0;
  v83 = 0;
  std::_Container_base12::_Alloc_proxy<std::allocator<std::_Container_proxy>>(&v81);
  v68 = clock();
  v85[1] = 0;
  v85[0] = &Cpu::`vftable';
  *(_OWORD *)v86 = 0;
  hProcess = 0;
  phQuery = 0;
  v2 = PdhOpenQueryW(0, 0, &phQuery);
  if ( GamingOverlayExperienceManager::Pdh_Failed(v3, v2) && v4 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x478,
      (unsigned int)"pcshell\\twinui\\gamingoverlayexperiencemanager\\lib\\GamingOverlayExperienceManager.cpp",
      (const char *)(unsigned int)v4,
      ppv);
  v5 = (_QWORD *)((char *)this + 1168);
  v6 = PdhAddCounterW(phQuery, L"\\GPU Adapter Memory(*)\\Dedicated Usage", 0, (PDH_HCOUNTER *)this + 146);
  if ( GamingOverlayExperienceManager::Pdh_Failed(v7, v6) )
  {
    v9 = retaddr;
    if ( v8 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x47E,
        (unsigned int)"pcshell\\twinui\\gamingoverlayexperiencemanager\\lib\\GamingOverlayExperienceManager.cpp",
        (const char *)(unsigned int)v8,
        ppv);
  }
  _InterlockedExchange64((volatile __int64 *)this + 148, GamingOverlayExperienceManager::GetDedicatedVideoMemoryCap(v9));
  updated = Cpu::InitializeCpuQuery((Cpu *)v85);
  PcwCounter = updated;
  if ( updated >= 0 )
  {
    v13 = 0;
    v69 = 0;
    v14 = 0;
    v15 = (_QWORD *)((char *)this + 1144);
    while ( 1 )
    {
      v16 = *((_DWORD *)this + 264);
      if ( v16 && !*((_QWORD *)this + 120) || v13 != v16 || !*((_BYTE *)this + 1060) )
      {
        *((_BYTE *)this + 1060) = 1;
        v69 = v16;
        std::deque<tagPRESENTFRAME>::_Tidy(&v81);
        lpCriticalSection = 0;
        wil::EnterCriticalSection(&lpCriticalSection, (char *)this + 1072);
        v17 = *((_QWORD *)this + 139);
        if ( v17 != *((_QWORD *)this + 140) )
          *((_QWORD *)this + 140) = v17;
        if ( lpCriticalSection )
          LeaveCriticalSection(lpCriticalSection);
        _InterlockedExchange((volatile __int32 *)this + 266, 0);
        v14 = 0;
        v68 = clock();
        lpCriticalSection = (LPCRITICAL_SECTION)OpenProcess(0x1000u, 0, v16);
        wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
          &hProcess,
          &lpCriticalSection);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&lpCriticalSection);
        if ( !*((_DWORD *)this + 264) )
          goto LABEL_56;
        v79 = 0;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v79);
        v18 = CoCreateInstance(
                &GUID_805a61d6_44c1_48c0_8af1_721a248effed,
                0,
                4u,
                &GUID_2b43fa87_6398_400f_8ed8_0b5d2ed75db7,
                &v79);
        PcwCounter = v18;
        if ( v18 < 0 )
        {
          v62 = 1181;
          goto LABEL_98;
        }
        v18 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, char *))(*(_QWORD *)v79 + 24LL))(
                v79,
                *((unsigned int *)this + 264),
                (char *)this + 960);
        PcwCounter = v18;
        if ( v18 < 0 )
        {
          v62 = 1182;
LABEL_98:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v62,
            (unsigned int)"pcshell\\twinui\\gamingoverlayexperiencemanager\\lib\\GamingOverlayExperienceManager.cpp",
            (const char *)(unsigned int)v18,
            ppv);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v79);
          goto LABEL_106;
        }
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v79);
      }
      if ( *((_DWORD *)this + 264) )
      {
        LODWORD(lpCriticalSection) = 0;
        ExitCodeProcess = GetExitCodeProcess(hProcess, (LPDWORD)&lpCriticalSection);
        if ( (_DWORD)lpCriticalSection != 259 || !ExitCodeProcess )
          goto LABEL_99;
        v20 = *((_QWORD *)this + 120);
        v21 = *(__int64 (__fastcall **)(__int64, __int128 *, unsigned int *))(*(_QWORD *)v20 + 40LL);
        wil::unique_any_array_ptr<tagPRESENTFRAME,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(&v84);
        v22 = v21(v20, &v84, &v78);
        if ( v22 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x4B1,
            (unsigned int)"pcshell\\twinui\\gamingoverlayexperiencemanager\\lib\\GamingOverlayExperienceManager.cpp",
            (const char *)(unsigned int)v22,
            ppv);
        v23 = v83;
        if ( v78 || v83 )
        {
          v24 = 0;
          for ( *((_QWORD *)&v25 + 1) = *((_QWORD *)&v82 + 1); v24 < v78; ++v24 )
          {
            v26 = (_OWORD *)(v84 + 32LL * v24);
            *(_QWORD *)&v25 = v82;
            if ( (unsigned __int64)v82 <= v23 + 1 )
            {
              std::deque<tagPRESENTFRAME>::_Growmap(&v81);
              v25 = v82;
            }
            v27 = v25 - 1;
            v28 = (v25 - 1) & *((_QWORD *)&v25 + 1);
            *((_QWORD *)&v82 + 1) = v28;
            if ( !v28 )
              v28 = v25;
            *((_QWORD *)&v25 + 1) = v28 - 1;
            v29 = *((_QWORD *)&v81 + 1);
            if ( !*(_QWORD *)(*((_QWORD *)&v81 + 1) + 8 * (v27 & *((_QWORD *)&v25 + 1))) )
            {
              *(_QWORD *)(*((_QWORD *)&v81 + 1) + 8 * (v27 & *((_QWORD *)&v25 + 1))) = std::_Allocate<16,std::_Default_allocate_traits>(0x20u);
              *(_QWORD *)&v25 = v82;
              v29 = *((_QWORD *)&v81 + 1);
            }
            *(_QWORD *)&v25 = *(_QWORD *)(v29 + 8 * (*((_QWORD *)&v25 + 1) & (v25 - 1)));
            *(_OWORD *)v25 = *v26;
            *(_OWORD *)(v25 + 16) = v26[1];
            *((_QWORD *)&v82 + 1) = *((_QWORD *)&v25 + 1);
            v23 = ++v83;
          }
          if ( v23 > 0x3E8 )
          {
            v71[1] = 0;
            v71[0] = v81;
            v71[2] = *((_QWORD *)&v25 + 1) + v23;
            v72[1] = 0;
            v72[0] = v81;
            v72[2] = *((_QWORD *)&v25 + 1) + 1000LL;
            std::deque<tagPRESENTFRAME>::erase(&v81, v76, v72, v71);
          }
          v30 = *(_QWORD *)std::deque<winrt::guid>::at(&v81, 0) - 100000LL;
          v31 = 0;
          if ( !v14 )
            v14 = *(_QWORD *)std::deque<winrt::guid>::at(&v81, v83 - 1);
          v32 = 0;
          v67 = 0;
          v33 = v83;
          while ( (--v33 & 0x80000000) == 0 )
          {
            v34 = (unsigned __int64 *)std::deque<winrt::guid>::at(&v81, v33);
            v35 = v31 + 1;
            if ( *v34 < v30 )
              v35 = v31;
            v31 = v35;
            if ( *(_QWORD *)std::deque<winrt::guid>::at(&v81, v33) >= v14 )
            {
              if ( *(_QWORD *)std::deque<winrt::guid>::at(&v81, v33) >= v14 + 100000 )
              {
                v14 += 100000LL;
                v66 = 0;
                wil::EnterCriticalSection(&v66, (char *)this + 1072);
                v36 = (void **)((char *)this + 1112);
                v37 = (_DWORD *)*((_QWORD *)this + 140);
                if ( v37 == *((_DWORD **)this + 141) )
                {
                  std::vector<int>::_Emplace_reallocate<int>((char *)this + 1112, v37, &v67);
                }
                else
                {
                  *v37 = v32;
                  *((_QWORD *)this + 140) += 4LL;
                }
                v32 = 0;
                v67 = 0;
                if ( (unsigned __int64)((__int64)(*((_QWORD *)this + 140) - (_QWORD)*v36) >> 2) > 0x3C )
                {
                  memmove_0(*v36, (char *)*v36 + 4, *((_QWORD *)this + 140) - ((_QWORD)*v36 + 4));
                  *((_QWORD *)this + 140) -= 4LL;
                }
                if ( v66 )
                  LeaveCriticalSection(v66);
              }
              else
              {
                v67 = ++v32;
              }
            }
          }
          _InterlockedExchange((volatile __int32 *)this + 266, v31);
          v5 = (_QWORD *)((char *)this + 1168);
          v15 = (_QWORD *)((char *)this + 1144);
        }
      }
LABEL_56:
      Data = PdhCollectQueryData(phQuery);
      if ( GamingOverlayExperienceManager::Pdh_Failed(v39, Data) )
      {
        v41 = retaddr;
        if ( v40 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x4FB,
            (unsigned int)"pcshell\\twinui\\gamingoverlayexperiencemanager\\lib\\GamingOverlayExperienceManager.cpp",
            (const char *)(unsigned int)v40,
            ppv);
      }
      v42 = (unsigned int *)((char *)this + 1136);
      RawData = GamingOverlayExperienceManager::GetRawData(v41, *v5, (char *)this + 1136, v15);
      if ( GamingOverlayExperienceManager::Pdh_Failed(v44, RawData) )
      {
        v46 = retaddr;
        if ( v45 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x501,
            (unsigned int)"pcshell\\twinui\\gamingoverlayexperiencemanager\\lib\\GamingOverlayExperienceManager.cpp",
            (const char *)(unsigned int)v45,
            ppv);
      }
      v47 = 0;
      if ( *v42 )
      {
        v48 = 0;
        do
        {
          v46 = (Cpu *)(48LL * v48);
          v47 += *(_QWORD *)((char *)v46 + *v15 + 24);
          ++v48;
        }
        while ( v48 < *v42 );
      }
      _InterlockedExchange64((volatile __int64 *)this + 147, v47);
      PcwCounter = Cpu::TmQueryPcwCounter(v46, v86, &v86[1], v85[1]);
      if ( PcwCounter < 0 )
      {
        v64 = (unsigned int)PcwCounter;
        v12 = 1291;
        goto LABEL_105;
      }
      updated = Cpu::UpdateCpuQuery((Cpu *)v85, (double *)this + 157);
      PcwCounter = updated;
      if ( updated < 0 )
      {
        v12 = 1292;
        goto LABEL_103;
      }
      v66 = 0;
      updated = GamingOverlayExperienceManager::GetCpuSpeed(v49, (double *)&v66);
      PcwCounter = updated;
      if ( updated < 0 )
      {
        v12 = 1295;
        goto LABEL_103;
      }
      _InterlockedExchange64((volatile __int64 *)this + 158, (__int64)v66);
      v66 = 0;
      lpCriticalSection = 0;
      updated = Cpu::GetMemoryUsage(v50, (double *)&v66, (double *)&lpCriticalSection);
      PcwCounter = updated;
      if ( updated < 0 )
      {
        v12 = 1300;
        goto LABEL_103;
      }
      _InterlockedExchange64((volatile __int64 *)this + 167, (__int64)v66);
      _InterlockedExchange64((volatile __int64 *)this + 168, (__int64)lpCriticalSection);
      if ( clock() - v68 > 1000 )
      {
        v68 += 1000;
        v66 = 0;
        wil::EnterCriticalSection(&v66, (char *)this + 1192);
        v51 = (_QWORD *)((char *)this + 1232);
        v52 = *((_QWORD *)this + 147);
        if ( v52 < 0 )
        {
          v54 = *((_QWORD *)this + 147) & 1LL | ((unsigned __int64)v52 >> 1);
          v53 = (double)(int)v54 + (double)(int)v54;
        }
        else
        {
          v53 = (double)(int)v52;
        }
        v55 = v53 / 1048576000.0;
        lpCriticalSection = *(LPCRITICAL_SECTION *)&v55;
        v56 = (double *)*((_QWORD *)this + 155);
        if ( v56 == *((double **)this + 156) )
        {
          std::vector<double>::_Emplace_reallocate<double const &>((char *)this + 1232, v56, &lpCriticalSection);
        }
        else
        {
          *v56 = v55;
          *((_QWORD *)this + 155) = v56 + 1;
        }
        if ( (unsigned __int64)((__int64)(*((_QWORD *)this + 155) - *v51) >> 3) > 0x3C )
          std::vector<double>::erase((char *)this + 1232, v73, *v51);
        if ( v66 )
          LeaveCriticalSection(v66);
        v66 = 0;
        wil::EnterCriticalSection(&v66, (char *)this + 1272);
        v57 = (_QWORD *)((char *)this + 1312);
        v58 = (_QWORD *)*((_QWORD *)this + 165);
        if ( v58 == *((_QWORD **)this + 166) )
        {
          std::vector<double>::_Emplace_reallocate<double const &>((char *)this + 1312, v58, (char *)this + 1256);
        }
        else
        {
          *v58 = *((_QWORD *)this + 157);
          *((_QWORD *)this + 165) = v58 + 1;
        }
        if ( (unsigned __int64)((__int64)(*((_QWORD *)this + 165) - *v57) >> 3) > 0x3C )
          std::vector<double>::erase((char *)this + 1312, v74, *v57);
        if ( v66 )
          LeaveCriticalSection(v66);
        v66 = 0;
        wil::EnterCriticalSection(&v66, (char *)this + 1360);
        v59 = (_QWORD *)((char *)this + 1400);
        v60 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)this + 167);
        lpCriticalSection = v60;
        v61 = (struct _RTL_CRITICAL_SECTION **)*((_QWORD *)this + 176);
        if ( v61 == *((struct _RTL_CRITICAL_SECTION ***)this + 177) )
        {
          std::vector<double>::_Emplace_reallocate<double const &>((char *)this + 1400, v61, &lpCriticalSection);
        }
        else
        {
          *v61 = v60;
          *((_QWORD *)this + 176) = v61 + 1;
        }
        if ( (unsigned __int64)((__int64)(*((_QWORD *)this + 176) - *v59) >> 3) > 0x3C )
          std::vector<double>::erase((char *)this + 1400, v75, *v59);
        if ( v66 )
          LeaveCriticalSection(v66);
      }
      Sleep(0xC8u);
      if ( *((_BYTE *)this + 1352) )
      {
LABEL_99:
        GamingOverlayExperienceManager::StopPerfThread(this);
        wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long PdhCloseQuery(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long PdhCloseQuery(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phQuery);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hProcess);
        Cpu::~Cpu((Cpu *)v85);
        std::deque<tagPRESENTFRAME>::~deque<tagPRESENTFRAME>(&v81);
        wil::unique_any_array_ptr<tagPRESENTFRAME,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(&v84);
        return 0;
      }
      v13 = v69;
      v5 = (_QWORD *)((char *)this + 1168);
    }
  }
  v12 = 1155;
LABEL_103:
  v64 = (unsigned int)updated;
LABEL_105:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v12,
    (unsigned int)"pcshell\\twinui\\gamingoverlayexperiencemanager\\lib\\GamingOverlayExperienceManager.cpp",
    (const char *)v64,
    ppv);
LABEL_106:
  wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long PdhCloseQuery(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long PdhCloseQuery(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phQuery);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hProcess);
  Cpu::~Cpu((Cpu *)v85);
  std::deque<tagPRESENTFRAME>::~deque<tagPRESENTFRAME>(&v81);
  wil::unique_any_array_ptr<tagPRESENTFRAME,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(&v84);
  return (unsigned int)PcwCounter;
}

```

## disassembly

```asm
0x1803d68a0  mov     rax, rsp
0x1803d68a3  push    rbp
0x1803d68a4  push    rbx
0x1803d68a5  push    rsi
0x1803d68a6  push    rdi
0x1803d68a7  push    r12
0x1803d68a9  push    r13
0x1803d68ab  push    r14
0x1803d68ad  push    r15
0x1803d68af  lea     rbp, [rsp-48h]
0x1803d68b4  sub     rsp, 148h
0x1803d68bb  movaps  xmmword ptr [rax-58h], xmm6
0x1803d68bf  mov     rax, cs:__security_cookie
0x1803d68c6  xor     rax, rsp
0x1803d68c9  mov     [rbp+80h+var_58], rax
0x1803d68cd  mov     rsi, rcx
0x1803d68d0  xorps   xmm0, xmm0
0x1803d68d3  movups  [rbp+80h+var_88], xmm0
0x1803d68d7  xor     r12d, r12d
0x1803d68da  mov     qword ptr [rbp+80h+var_88], r12
0x1803d68de  mov     qword ptr [rbp+80h+var_88+8], r12
0x1803d68e2  mov     [rbp+80h+var_C8], r12d
0x1803d68e6  movdqu  [rbp+80h+var_B0], xmm0
0x1803d68eb  xorps   xmm1, xmm1
0x1803d68ee  movdqu  [rbp+80h+var_A0], xmm1
0x1803d68f3  mov     [rbp+80h+var_90], r12
0x1803d68f7  lea     rcx, [rbp+80h+var_B0]
0x1803d68fb  call    ??$_Alloc_proxy@V?$allocator@U_Container_proxy@std@@@std@@@_Container_base12@std@@QEAAX$$QEAV?$allocator@U_Container_proxy@std@@@1@@Z; std::_Container_base12::_Alloc_proxy<std::allocator<std::_Container_proxy>>(std::allocator<std::_Container_proxy> &&)
0x1803d6900  nop
0x1803d6901  call    cs:__imp_clock
0x1803d6907  mov     [rsp+180h+var_144], eax
0x1803d690b  xorps   xmm0, xmm0
0x1803d690e  movups  xmmword ptr [rbp+80h+var_78], xmm0
0x1803d6912  lea     rax, ??_7Cpu@@6B@; const Cpu::`vftable'
0x1803d6919  mov     [rbp+80h+var_78], rax
0x1803d691d  movdqu  xmmword ptr [rbp+80h+var_68], xmm0
0x1803d6922  mov     [rsp+180h+hProcess], r12
0x1803d6927  mov     [rbp+80h+phQuery], r12
0x1803d692b  lea     r8, [rbp+80h+phQuery]; phQuery
0x1803d692f  xor     edx, edx; dwUserData
0x1803d6931  xor     ecx, ecx; szDataSource
0x1803d6933  call    cs:__imp_PdhOpenQueryW
0x1803d6939  mov     edx, eax; int
0x1803d693b  call    ?Pdh_Failed@GamingOverlayExperienceManager@@AEAA_NJ@Z; GamingOverlayExperienceManager::Pdh_Failed(long)
0x1803d6940  lea     rdi, aPcshellTwinuiG_2; "pcshell\\twinui\\gamingoverlayexperienc"...
0x1803d6947  test    al, al
0x1803d6949  jz      short loc_1803D6966
0x1803d694b  mov     rcx, [rbp+88h]; this
0x1803d6952  test    edx, edx
0x1803d6954  jns     short loc_1803D6966
0x1803d6956  mov     r9d, edx; char *
0x1803d6959  mov     r8, rdi; unsigned int
0x1803d695c  mov     edx, 478h; void *
0x1803d6961  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1803d6966  lea     r14, [rsi+490h]
0x1803d696d  mov     r9, r14; phCounter
0x1803d6970  xor     r8d, r8d; dwUserData
0x1803d6973  lea     rdx, szFullCounterPath; "\\GPU Adapter Memory(*)\\Dedicated Usag"...
0x1803d697a  mov     rcx, [rbp+80h+phQuery]; hQuery
0x1803d697e  call    cs:__imp_PdhAddCounterW
0x1803d6984  mov     edx, eax; int
0x1803d6986  call    ?Pdh_Failed@GamingOverlayExperienceManager@@AEAA_NJ@Z; GamingOverlayExperienceManager::Pdh_Failed(long)
0x1803d698b  test    al, al
0x1803d698d  jz      short loc_1803D69AA
0x1803d698f  mov     rcx, [rbp+88h]; this
0x1803d6996  test    edx, edx
0x1803d6998  jns     short loc_1803D69AA
0x1803d699a  mov     r9d, edx; char *
0x1803d699d  mov     r8, rdi; unsigned int
0x1803d69a0  mov     edx, 47Eh; void *
0x1803d69a5  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1803d69aa  call    ?GetDedicatedVideoMemoryCap@GamingOverlayExperienceManager@@AEAA_KXZ; GamingOverlayExperienceManager::GetDedicatedVideoMemoryCap(void)
0x1803d69af  xchg    rax, [rsi+4A0h]
0x1803d69b6  lea     rcx, [rbp+80h+var_78]; this
0x1803d69ba  call    ?InitializeCpuQuery@Cpu@@QEAAJXZ; Cpu::InitializeCpuQuery(void)
0x1803d69bf  mov     ebx, eax
0x1803d69c1  test    eax, eax
0x1803d69c3  jns     short loc_1803D69D2
0x1803d69c5  mov     r8, rdi
0x1803d69c8  mov     edx, 483h
0x1803d69cd  jmp     loc_1803D7182
0x1803d69d2  mov     edi, r12d
0x1803d69d5  mov     [rsp+180h+var_140], r12d
0x1803d69da  mov     r13, r12
0x1803d69dd  lea     r15, [rsi+478h]
0x1803d69e4  xorps   xmm6, xmm6
0x1803d69e7  mov     ebx, [rsi+420h]
0x1803d69ed  test    ebx, ebx
0x1803d69ef  jz      short loc_1803D69FA
0x1803d69f1  cmp     [rsi+3C0h], r12
0x1803d69f8  jz      short loc_1803D6A0B
0x1803d69fa  cmp     edi, ebx
0x1803d69fc  jnz     short loc_1803D6A0B
0x1803d69fe  cmp     [rsi+424h], r12b
0x1803d6a05  jnz     loc_1803D6B11
0x1803d6a0b  mov     byte ptr [rsi+424h], 1
0x1803d6a12  mov     [rsp+180h+var_140], ebx
0x1803d6a16  lea     rcx, [rbp+80h+var_B0]
0x1803d6a1a  call    ?_Tidy@?$deque@UtagPRESENTFRAME@@V?$allocator@UtagPRESENTFRAME@@@std@@@std@@AEAAXXZ; std::deque<tagPRESENTFRAME>::_Tidy(void)
0x1803d6a1f  mov     [rbp+80h+lpCriticalSection], r12
0x1803d6a23  lea     rdx, [rsi+430h]
0x1803d6a2a  lea     rcx, [rbp+80h+lpCriticalSection]
0x1803d6a2e  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x1803d6a33  mov     rax, [rsi+458h]
0x1803d6a3a  cmp     rax, [rsi+460h]
0x1803d6a41  jz      short loc_1803D6A4A
0x1803d6a43  mov     [rsi+460h], rax
0x1803d6a4a  mov     rcx, [rbp+80h+lpCriticalSection]; lpCriticalSection
0x1803d6a4e  test    rcx, rcx
0x1803d6a51  jz      short loc_1803D6A59
0x1803d6a53  call    cs:__imp_LeaveCriticalSection
0x1803d6a59  mov     eax, r12d
0x1803d6a5c  xchg    eax, [rsi+428h]
0x1803d6a62  mov     r13, r12
0x1803d6a65  call    cs:__imp_clock
0x1803d6a6b  mov     [rsp+180h+var_144], eax
0x1803d6a6f  mov     r8d, ebx; dwProcessId
0x1803d6a72  xor     edx, edx; bInheritHandle
0x1803d6a74  mov     ecx, 1000h; dwDesiredAccess
0x1803d6a79  call    cs:__imp_OpenProcess
0x1803d6a7f  mov     [rbp+80h+lpCriticalSection], rax
0x1803d6a83  lea     rdx, [rbp+80h+lpCriticalSection]
0x1803d6a87  lea     rcx, [rsp+180h+hProcess]
0x1803d6a8c  call    ??4?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x1803d6a91  lea     rcx, [rbp+80h+lpCriticalSection]
0x1803d6a95  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1803d6a9a  cmp     [rsi+420h], r12d
0x1803d6aa1  jz      loc_1803D6DD4
0x1803d6aa7  mov     [rbp+80h+var_C0], r12
0x1803d6aab  lea     rcx, [rbp+80h+var_C0]
0x1803d6aaf  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1803d6ab4  lea     rax, [rbp+80h+var_C0]
0x1803d6ab8  mov     qword ptr [rsp+180h+ppv], rax; int
0x1803d6abd  lea     r9, _GUID_2b43fa87_6398_400f_8ed8_0b5d2ed75db7; riid
0x1803d6ac4  xor     edx, edx; pUnkOuter
0x1803d6ac6  lea     r8d, [rdx+4]; dwClsContext
0x1803d6aca  lea     rcx, _GUID_805a61d6_44c1_48c0_8af1_721a248effed; rclsid
0x1803d6ad1  call    cs:__imp_CoCreateInstance
0x1803d6ad7  mov     ebx, eax
0x1803d6ad9  test    eax, eax
0x1803d6adb  js      loc_1803D7102
0x1803d6ae1  mov     rcx, [rbp+80h+var_C0]
0x1803d6ae5  mov     rax, [rcx]
0x1803d6ae8  lea     r8, [rsi+3C0h]
0x1803d6aef  mov     edx, [rsi+420h]
0x1803d6af5  mov     rax, [rax+18h]
0x1803d6af9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803d6afe  mov     ebx, eax
0x1803d6b00  test    eax, eax
0x1803d6b02  js      loc_1803D70FB
0x1803d6b08  lea     rcx, [rbp+80h+var_C0]
0x1803d6b0c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1803d6b11  cmp     [rsi+420h], r12d
0x1803d6b18  jz      loc_1803D6DD4
0x1803d6b1e  mov     dword ptr [rbp+80h+lpCriticalSection], r12d
0x1803d6b22  lea     rdx, [rbp+80h+lpCriticalSection]; lpExitCode
0x1803d6b26  mov     rcx, [rsp+180h+hProcess]; hProcess
0x1803d6b2b  call    cs:__imp_GetExitCodeProcess
0x1803d6b31  cmp     dword ptr [rbp+80h+lpCriticalSection], 103h
0x1803d6b38  jnz     loc_1803D7129
0x1803d6b3e  test    eax, eax
0x1803d6b40  jz      loc_1803D7129
0x1803d6b46  mov     rdi, [rsi+3C0h]
0x1803d6b4d  mov     rax, [rdi]
0x1803d6b50  mov     rbx, [rax+28h]
0x1803d6b54  lea     rcx, [rbp+80h+var_88]
0x1803d6b58  call    ?reset@?$unique_any_array_ptr@UtagPRESENTFRAME@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@3@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<tagPRESENTFRAME,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(void)
0x1803d6b5d  lea     r8, [rbp+80h+var_C8]
0x1803d6b61  lea     rdx, [rbp+80h+var_88]
0x1803d6b65  mov     rcx, rdi
0x1803d6b68  mov     rax, rbx
0x1803d6b6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803d6b70  mov     rcx, [rbp+88h]; this
0x1803d6b77  test    eax, eax
0x1803d6b79  jns     short loc_1803D6B8F
0x1803d6b7b  mov     r9d, eax; char *
0x1803d6b7e  lea     r8, aPcshellTwinuiG_2; "pcshell\\twinui\\gamingoverlayexperienc"...
0x1803d6b85  mov     edx, 4B1h; void *
0x1803d6b8a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1803d6b8f  mov     rax, [rbp+80h+var_90]
0x1803d6b93  mov     ecx, [rbp+80h+var_C8]
0x1803d6b96  test    ecx, ecx
0x1803d6b98  jnz     short loc_1803D6BA3
0x1803d6b9a  test    rax, rax
0x1803d6b9d  jz      loc_1803D6DD4
0x1803d6ba3  mov     r15d, r12d
0x1803d6ba6  mov     rbx, qword ptr [rbp+80h+var_A0+8]
0x1803d6baa  test    ecx, ecx
0x1803d6bac  jz      loc_1803D6C4B
0x1803d6bb2  mov     edi, r15d
0x1803d6bb5  shl     rdi, 5
0x1803d6bb9  add     rdi, qword ptr [rbp+80h+var_88]
0x1803d6bbd  inc     rax
0x1803d6bc0  mov     rcx, qword ptr [rbp+80h+var_A0]
0x1803d6bc4  cmp     rcx, rax
0x1803d6bc7  ja      short loc_1803D6BDA
0x1803d6bc9  lea     rcx, [rbp+80h+var_B0]
0x1803d6bcd  call    ?_Growmap@?$deque@UtagPRESENTFRAME@@V?$allocator@UtagPRESENTFRAME@@@std@@@std@@AEAAX_K@Z; std::deque<tagPRESENTFRAME>::_Growmap(unsigned __int64)
0x1803d6bd2  mov     rbx, qword ptr [rbp+80h+var_A0+8]
0x1803d6bd6  mov     rcx, qword ptr [rbp+80h+var_A0]
0x1803d6bda  lea     rax, [rcx-1]
0x1803d6bde  and     rbx, rax
0x1803d6be1  mov     qword ptr [rbp+80h+var_A0+8], rbx
0x1803d6be5  cmovz   rbx, rcx
0x1803d6be9  dec     rbx
0x1803d6bec  mov     r14, rbx
0x1803d6bef  and     r14, rax
0x1803d6bf2  mov     rdx, qword ptr [rbp+80h+var_B0+8]
0x1803d6bf6  cmp     [rdx+r14*8], r12
0x1803d6bfa  jnz     short loc_1803D6C16
0x1803d6bfc  mov     ecx, 20h ; ' '
0x1803d6c01  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x1803d6c06  mov     rcx, qword ptr [rbp+80h+var_B0+8]
0x1803d6c0a  mov     [rcx+r14*8], rax
0x1803d6c0e  mov     rcx, qword ptr [rbp+80h+var_A0]
0x1803d6c12  mov     rdx, qword ptr [rbp+80h+var_B0+8]
0x1803d6c16  lea     rax, [rcx-1]
0x1803d6c1a  and     rax, rbx
0x1803d6c1d  mov     rcx, [rdx+rax*8]
0x1803d6c21  movups  xmm0, xmmword ptr [rdi]
0x1803d6c24  movups  xmmword ptr [rcx], xmm0
0x1803d6c27  movups  xmm1, xmmword ptr [rdi+10h]
0x1803d6c2b  movups  xmmword ptr [rcx+10h], xmm1
0x1803d6c2f  mov     qword ptr [rbp+80h+var_A0+8], rbx
0x1803d6c33  mov     rax, [rbp+80h+var_90]
0x1803d6c37  inc     rax
0x1803d6c3a  mov     [rbp+80h+var_90], rax
0x1803d6c3e  inc     r15d
0x1803d6c41  cmp     r15d, [rbp+80h+var_C8]
0x1803d6c45  jb      loc_1803D6BB2
0x1803d6c4b  cmp     rax, 3E8h
0x1803d6c51  jbe     short loc_1803D6C96
0x1803d6c53  add     rax, rbx
0x1803d6c56  mov     rcx, qword ptr [rbp+80h+var_B0]
0x1803d6c5a  mov     [rsp+180h+var_128], r12
0x1803d6c5f  mov     [rsp+180h+var_130], rcx
0x1803d6c64  mov     [rsp+180h+var_120], rax
0x1803d6c69  mov     [rsp+180h+var_110], r12
0x1803d6c6e  mov     [rsp+180h+var_118], rcx
0x1803d6c73  lea     rax, [rbx+3E8h]
0x1803d6c7a  mov     [rsp+180h+var_108], rax
0x1803d6c7f  lea     r9, [rsp+180h+var_130]
0x1803d6c84  lea     r8, [rsp+180h+var_118]
0x1803d6c89  lea     rdx, [rbp+80h+var_E8]
0x1803d6c8d  lea     rcx, [rbp+80h+var_B0]
0x1803d6c91  call    ?erase@?$deque@UtagPRESENTFRAME@@V?$allocator@UtagPRESENTFRAME@@@std@@@std@@QEAA?AV?$_Deque_iterator@V?$_Deque_val@U?$_Deque_simple_types@UtagPRESENTFRAME@@@std@@@std@@@2@V?$_Deque_const_iterator@V?$_Deque_val@U?$_Deque_simple_types@UtagPRESENTFRAME@@@std@@@std@@@2@0@Z; std::deque<tagPRESENTFRAME>::erase(std::_Deque_const_iterator<std::_Deque_val<std::_Deque_simple_types<tagPRESENTFRAME>>>,std::_Deque_const_iterator<std::_Deque_val<std::_Deque_simple_types<tagPRESENTFRAME>>>)
0x1803d6c96  xor     edx, edx
0x1803d6c98  lea     rcx, [rbp+80h+var_B0]
0x1803d6c9c  call    ?at@?$deque@Uguid@winrt@@V?$allocator@Uguid@winrt@@@std@@@std@@QEAAAEAUguid@winrt@@_K@Z; std::deque<winrt::guid>::at(unsigned __int64)
0x1803d6ca1  mov     r12, [rax]
0x1803d6ca4  sub     r12, 186A0h
0x1803d6cab  xor     r14d, r14d
0x1803d6cae  test    r13, r13
0x1803d6cb1  jnz     short loc_1803D6CC6
0x1803d6cb3  mov     rdx, [rbp+80h+var_90]
0x1803d6cb7  dec     rdx
0x1803d6cba  lea     rcx, [rbp+80h+var_B0]
0x1803d6cbe  call    ?at@?$deque@Uguid@winrt@@V?$allocator@Uguid@winrt@@@std@@@std@@QEAAAEAUguid@winrt@@_K@Z; std::deque<winrt::guid>::at(unsigned __int64)
0x1803d6cc3  mov     r13, [rax]
0x1803d6cc6  xor     ebx, ebx
0x1803d6cc8  mov     [rsp+180h+var_148], ebx
0x1803d6ccc  mov     r15d, dword ptr [rbp+80h+var_90]
0x1803d6cd0  jmp     loc_1803D6DB2
0x1803d6cd5  mov     edi, r15d
0x1803d6cd8  mov     edx, r15d
0x1803d6cdb  lea     rcx, [rbp+80h+var_B0]
0x1803d6cdf  call    ?at@?$deque@Uguid@winrt@@V?$allocator@Uguid@winrt@@@std@@@std@@QEAAAEAUguid@winrt@@_K@Z; std::deque<winrt::guid>::at(unsigned __int64)
0x1803d6ce4  lea     ecx, [r14+1]
0x1803d6ce8  cmp     [rax], r12
0x1803d6ceb  cmovb   ecx, r14d
0x1803d6cef  mov     r14d, ecx
0x1803d6cf2  mov     edx, r15d
0x1803d6cf5  lea     rcx, [rbp+80h+var_B0]
0x1803d6cf9  call    ?at@?$deque@Uguid@winrt@@V?$allocator@Uguid@winrt@@@std@@@std@@QEAAAEAUguid@winrt@@_K@Z; std::deque<winrt::guid>::at(unsigned __int64)
0x1803d6cfe  cmp     [rax], r13
0x1803d6d01  jb      loc_1803D6DB2
0x1803d6d07  mov     edx, edi
0x1803d6d09  lea     rcx, [rbp+80h+var_B0]
0x1803d6d0d  call    ?at@?$deque@Uguid@winrt@@V?$allocator@Uguid@winrt@@@std@@@std@@QEAAAEAUguid@winrt@@_K@Z; std::deque<winrt::guid>::at(unsigned __int64)
0x1803d6d12  lea     rcx, [r13+186A0h]
0x1803d6d19  cmp     [rax], rcx
0x1803d6d1c  jnb     short loc_1803D6D29
0x1803d6d1e  inc     ebx
0x1803d6d20  mov     [rsp+180h+var_148], ebx
0x1803d6d24  jmp     loc_1803D6DB2
0x1803d6d29  mov     r13, rcx
0x1803d6d2c  mov     [rsp+180h+var_150], 0
0x1803d6d35  lea     rdx, [rsi+430h]
0x1803d6d3c  lea     rcx, [rsp+180h+var_150]
0x1803d6d41  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x1803d6d46  nop
0x1803d6d47  lea     rdi, [rsi+458h]
0x1803d6d4e  mov     rdx, [rdi+8]
0x1803d6d52  cmp     rdx, [rdi+10h]
0x1803d6d56  jz      short loc_1803D6D61
0x1803d6d58  mov     [rdx], ebx
0x1803d6d5a  add     qword ptr [rdi+8], 4
0x1803d6d5f  jmp     short loc_1803D6D6E
0x1803d6d61  lea     r8, [rsp+180h+var_148]
0x1803d6d66  mov     rcx, rdi
  ... truncated ...
```
