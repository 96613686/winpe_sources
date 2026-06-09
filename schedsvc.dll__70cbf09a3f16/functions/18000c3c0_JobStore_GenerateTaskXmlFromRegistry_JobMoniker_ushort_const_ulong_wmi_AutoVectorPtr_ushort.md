# JobStore::GenerateTaskXmlFromRegistry(JobMoniker &,ushort const *,ulong *,wmi::AutoVectorPtr<ushort> &)

- ea: `0x18000c3c0`
- end: `0x18000dc1b`
- name: `?GenerateTaskXmlFromRegistry@JobStore@@QEAAJAEAVJobMoniker@@PEBGPEAKAEAV?$AutoVectorPtr@G@wmi@@@Z`
- size: `6235`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `41`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180009010`

## callees

- `0x180007ddc`
- `0x180007ec0`
- `0x180008318`
- `0x180008330`
- `0x180008660`
- `0x1800086c0`
- `0x18000b438`
- `0x18000c3c0`
- `0x18000dc30`
- `0x18000dcb0`
- `0x18000e468`
- `0x18000e4c0`
- `0x18000e510`
- `0x18000e910`
- `0x18000fa4c`
- `0x180019860`
- `0x18001a260`
- `0x180021300`
- `0x18002132c`
- `0x18002643c`
- `0x18002fe50`
- `0x180030f80`
- `0x180031120`
- `0x18003a3c0`
- `0x18003f130`
- `0x18003fa50`
- `0x1800408b0`
- `0x180043d78`
- `0x180043dec`
- `0x1800504b4`
- `0x180052118`
- `0x180054084`
- `0x180056794`
- `0x18005790c`
- `0x180066e58`
- `0x180068060`
- `0x18006efc4`
- `0x180071e50`
- `0x18007e68a`
- `0x18007e6d0`
- `0x180084010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18000c7cb`
- `OLEAUT32!__imp_SysAllocString` at `0x18000c7cb`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18000cf26`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18000cf26`
- `OLEAUT32!__imp_SysFreeString` at `0x18000cf3a`
- `OLEAUT32!__imp_SysFreeString` at `0x18000cfaf`
- `OLEAUT32!__imp_SysFreeString` at `0x18000cfd8`
- `OLEAUT32!__imp_SysFreeString` at `0x18000cfe0`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d0ac`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d171`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d1b7`
- `OLEAUT32!__imp_SysFreeString` at `0x18000db26`
- `OLEAUT32!__imp_SysFreeString` at `0x18000cf3a`
- `OLEAUT32!__imp_SysFreeString` at `0x18000cfaf`
- `OLEAUT32!__imp_SysFreeString` at `0x18000cfd8`
- `OLEAUT32!__imp_SysFreeString` at `0x18000cfe0`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d0ac`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d171`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d1b7`
- `OLEAUT32!__imp_SysFreeString` at `0x18000db26`
- `OLEAUT32!__imp_SysStringLen` at `0x18000cff0`
- `OLEAUT32!__imp_SysStringLen` at `0x18000cff0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d8d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d91a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d96c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d8d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d91a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d96c`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000c433`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000c441`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000c433`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000c441`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000c5a3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000c643`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000c768`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000c819`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000c909`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000d2e7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000d4b0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000d5c9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000d792`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000c5a3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000c643`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000c768`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000c819`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000c909`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000d2e7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000d4b0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000d5c9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000d792`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000cbd7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000cbd7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c497`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c86e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c897`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000caf1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000cb33`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000cbc4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000cf02`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d106`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d12c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d193`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d1f2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d285`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000dbd2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000dc01`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c497`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c86e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c897`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000caf1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000cb33`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000cbc4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000cf02`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d106`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d12c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d193`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d1f2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d285`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000dbd2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000dc01`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000c514`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000c7a2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000cceb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000cdcc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000ce53`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000d01c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000c514`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000c7a2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000cceb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000cdcc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000ce53`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000d01c`
- `api-ms-win-core-localization-l1-2-0!SetThreadPreferredUILanguages` at `0x18000cd8c`
- `api-ms-win-core-localization-l1-2-0!SetThreadPreferredUILanguages` at `0x18000dbc0`
- `api-ms-win-core-localization-l1-2-0!SetThreadPreferredUILanguages` at `0x18000dbef`
- `api-ms-win-core-localization-l1-2-0!SetThreadPreferredUILanguages` at `0x18000cd8c`
- `api-ms-win-core-localization-l1-2-0!SetThreadPreferredUILanguages` at `0x18000dbc0`
- `api-ms-win-core-localization-l1-2-0!SetThreadPreferredUILanguages` at `0x18000dbef`
- `api-ms-win-core-localization-l1-2-0!GetThreadPreferredUILanguages` at `0x18000cd36`
- `api-ms-win-core-localization-l1-2-0!GetThreadPreferredUILanguages` at `0x18000cd73`
- `api-ms-win-core-localization-l1-2-0!GetThreadPreferredUILanguages` at `0x18000cd36`
- `api-ms-win-core-localization-l1-2-0!GetThreadPreferredUILanguages` at `0x18000cd73`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
__int64 __fastcall JobStore::GenerateTaskXmlFromRegistry(
        HKEY *a1,
        JobMoniker *a2,
        wmi::RefBase *a3,
        BYTE *a4,
        wmi::RefBase *a5)
{
  ULONG *v5; // r13
  wmi::RefBase *v6; // r12
  int v7; // ebx
  __int64 v8; // rcx
  _QWORD *v9; // rax
  _QWORD *i; // rbx
  void **v11; // r8
  void **v12; // rbx
  BYTE *v13; // rbx
  JobBucket *v14; // rax
  JobBucket *v15; // rax
  JobBucket *v16; // rdi
  JobBucket *v17; // rcx
  HKEY v18; // rsi
  LSTATUS v19; // eax
  int v20; // edx
  unsigned __int64 v21; // rcx
  int v22; // r14d
  JobBucket *v23; // rax
  LPVOID v24; // rcx
  int RegistrationData; // edi
  BYTE *lpData; // r15
  DWORD v27; // esi
  void (__fastcall ***v28)(_QWORD, __int64); // rcx
  BYTE *v29; // r12
  LSTATUS v30; // eax
  const OLECHAR *v31; // rsi
  JobBucket *v32; // r13
  BSTR *v33; // rax
  BSTR *v34; // rdi
  BSTR v35; // rax
  struct IErrorInfo *v36; // rdx
  HKEY v37; // r13
  LSTATUS v38; // eax
  JobBucket *v39; // rdi
  HKEY v40; // rdi
  LSTATUS v41; // eax
  __int64 v42; // rdx
  __int64 v43; // r8
  int v44; // ebx
  _QWORD *v45; // rcx
  JobBucket *v46; // rbx
  JobMoniker *v47; // rsi
  __int64 v48; // rax
  __int64 v49; // rcx
  JobBucket *v50; // rbx
  JobBucket *v51; // rcx
  __int64 v52; // rcx
  _QWORD *v53; // rdi
  _QWORD *j; // rbx
  _QWORD *v55; // r8
  BSTR *v56; // rbx
  void ***v57; // rax
  void ***k; // rbx
  void **v59; // r8
  void **v60; // rbx
  JobBucket *v61; // rcx
  void (__fastcall ***v63)(_QWORD, __int64); // rcx
  void **v64; // rcx
  unsigned int Path; // eax
  int v66; // edx
  int v67; // r8d
  __int64 v68; // rax
  unsigned __int64 v69; // rbx
  SIZE_T v70; // rax
  unsigned __int64 v71; // kr00_8
  BYTE *v72; // rax
  WCHAR *v73; // rsi
  unsigned __int64 m; // rdx
  LPVOID *v75; // r13
  __int64 v76; // rdi
  __int64 v77; // rbx
  StringStream *v78; // rcx
  __int64 v79; // rcx
  struct IErrorInfo *v80; // rdx
  int v81; // r14d
  wmi::RefBase *v82; // rdi
  wmi::RefBase *v83; // rbx
  wmi::RefBase *v84; // rax
  wmi::RefBase *v85; // r14
  OLECHAR *v86; // rbx
  __int64 v87; // r14
  OLECHAR *v88; // r15
  OLECHAR *v89; // r12
  unsigned __int64 v90; // r10
  __int64 n; // r11
  unsigned __int64 v92; // rcx
  OLECHAR *v93; // rdx
  unsigned __int64 v94; // r9
  OLECHAR *v95; // r8
  OLECHAR v96; // ax
  __int64 v97; // rax
  unsigned __int64 v98; // r14
  unsigned __int64 v99; // r12
  SIZE_T v100; // rax
  OLECHAR *v101; // r15
  OLECHAR *v102; // rcx
  OLECHAR v103; // ax
  wmi::RefBase *v104; // rcx
  PZZWSTR v105; // rbx
  _QWORD *v106; // rbx
  BSTR v107; // rcx
  PZZWSTR v108; // rbx
  unsigned int v109; // edx
  WCHAR v110; // ax
  LPVOID v111; // rax
  BYTE *v112; // rax
  bool IsErrorNotFound; // al
  unsigned int v114; // ecx
  __int64 v115; // r9
  bool v116; // sf
  unsigned __int64 v117; // rsi
  LPVOID v118; // rax
  int v119; // eax
  LPVOID v120; // rax
  LPBYTE v121; // rbx
  LSTATUS v122; // eax
  DWORD LastError; // eax
  DWORD v124; // ebx
  DWORD v125; // eax
  unsigned int v126; // edx
  unsigned int v127; // edx
  DWORD Type; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cbData[2]; // [rsp+48h] [rbp-B8h] BYREF
  DWORD v130[2]; // [rsp+50h] [rbp-B0h] BYREF
  wmi::RefBase *v131; // [rsp+58h] [rbp-A8h] BYREF
  DWORD lpcbData; // [rsp+68h] [rbp-98h] BYREF
  LPVOID lpMem; // [rsp+70h] [rbp-90h] BYREF
  __int64 v134; // [rsp+78h] [rbp-88h]
  LPVOID v135; // [rsp+80h] [rbp-80h]
  HKEY hKey; // [rsp+90h] [rbp-70h] BYREF
  wmi::RefBase *v137; // [rsp+98h] [rbp-68h] BYREF
  char v138; // [rsp+A0h] [rbp-60h] BYREF
  int v139; // [rsp+A1h] [rbp-5Fh]
  __int16 v140; // [rsp+A5h] [rbp-5Bh]
  char v141; // [rsp+A7h] [rbp-59h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+A8h] [rbp-58h] BYREF
  char v143; // [rsp+B0h] [rbp-50h]
  int v144; // [rsp+B1h] [rbp-4Fh]
  __int16 v145; // [rsp+B5h] [rbp-4Bh]
  char v146; // [rsp+B7h] [rbp-49h]
  struct _FILETIME v147; // [rsp+B8h] [rbp-48h] BYREF
  LPVOID v148[2]; // [rsp+C0h] [rbp-40h] BYREF
  JobBucket *v149; // [rsp+D0h] [rbp-30h]
  HKEY v150; // [rsp+D8h] [rbp-28h]
  LPBYTE v151; // [rsp+E0h] [rbp-20h] BYREF
  JobMoniker *v152; // [rsp+E8h] [rbp-18h]
  _QWORD v153[2]; // [rsp+F0h] [rbp-10h] BYREF
  void *v154; // [rsp+100h] [rbp+0h]
  __int128 pExceptionObject; // [rsp+108h] [rbp+8h] BYREF
  const unsigned __int16 *v156; // [rsp+118h] [rbp+18h] BYREF
  __int64 v157; // [rsp+120h] [rbp+20h]
  JobBucket *v158; // [rsp+128h] [rbp+28h] BYREF
  int v159; // [rsp+130h] [rbp+30h]
  __int64 v160; // [rsp+134h] [rbp+34h]
  BYTE Data[16]; // [rsp+140h] [rbp+40h] BYREF
  __int128 v162; // [rsp+150h] [rbp+50h]

  v5 = (ULONG *)a4;
  v151 = a4;
  v6 = a3;
  v131 = a3;
  v152 = a2;
  v137 = a5;
  hKey = 0;
  v7 = JobStore::RegOpenTaskKey(a1, a2, &hKey, 0x20019u);
  if ( v7 < 0 )
    goto LABEL_282;
  v138 = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v143 = 0;
  GetSystemTimeAsFileTime(&v147);
  *(_OWORD *)v148 = 0;
  v9 = (_QWORD *)std::_List_alloc<0,std::_List_base_types<Triggers::Trigger *>>::_Buynode0(v8, 0, 0);
  v148[0] = v9;
  v149 = 0;
  if ( v148[1] )
  {
    for ( i = (_QWORD *)*v9; i != v9; i = (_QWORD *)*i )
    {
      v28 = (void (__fastcall ***)(_QWORD, __int64))i[2];
      if ( v28 )
      {
        (**v28)(v28, 1);
        i[2] = 0;
        v9 = v148[0];
      }
    }
    v11 = (void **)*v9;
    *v9 = v9;
    *((LPVOID *)v148[0] + 1) = v148[0];
    v148[1] = 0;
    if ( v11 != v148[0] )
    {
      do
      {
        v12 = (void **)*v11;
        HeapFree(g_PrivateHeap, 0, v11);
        v11 = v12;
      }
      while ( v12 != v148[0] );
    }
  }
  v138 = 0;
  v139 = *(_DWORD *)((char *)&v131 + 1);
  v140 = *(_WORD *)((char *)&v131 + 5);
  v141 = HIBYTE(v131);
  SystemTimeAsFileTime = (struct _FILETIME)-1LL;
  v143 = 0;
  v144 = *(_DWORD *)((char *)&v131 + 1);
  v145 = *(_WORD *)((char *)&v131 + 5);
  v146 = HIBYTE(v131);
  v147 = 0;
  v13 = 0;
  v154 = 0;
  memset_0(Data, 0, 0x400u);
  v14 = (JobBucket *)HeapAlloc(g_PrivateHeap, 0, 0xD8u);
  if ( !v14 )
  {
    BYTE8(pExceptionObject) = 0;
    v156 = &qword_1800A4718;
    v157 = 0;
    v158 = 0;
    v159 = 14;
    v160 = -1;
    *(_QWORD *)&pExceptionObject = &wmi::GenericException::`vftable';
    throw (wmi::OutOfMemoryException *)&pExceptionObject;
  }
  v15 = JobBucket::JobBucket(v14);
  v16 = v15;
  if ( v15 )
    _InterlockedIncrement((volatile signed __int32 *)v15 + 2);
  v17 = v149;
  if ( v149 && _InterlockedExchangeAdd((volatile signed __int32 *)v149 + 2, 0xFFFFFFFF) == 1 )
    (**(void (__fastcall ***)(JobBucket *))v17)(v17);
  v149 = v16;
  if ( !v16 )
  {
    v22 = -2147024882;
LABEL_161:
    Triggers::Trigulator::~Trigulator((Triggers::Trigulator *)&v138);
    wmi::AutoRegKey::Close(&hKey);
    return (unsigned int)v22;
  }
  v18 = hKey;
  v150 = hKey;
  cbData[0] = 1024;
  lpMem = 0;
  Type = 0;
  v19 = RegQueryValueExW(hKey, L"Hash", 0, &Type, Data, cbData);
  v21 = (unsigned int)v19;
  v22 = -2147024882;
  if ( !v19 && cbData[0] == 32 && Type == 3 )
  {
    v23 = v149;
    *(_OWORD *)((char *)v149 + 28) = *(_OWORD *)Data;
    *(_OWORD *)((char *)v23 + 44) = v162;
    *((_DWORD *)v23 + 15) = 1;
  }
  else
  {
    *((_DWORD *)v149 + 15) = 0;
    if ( v19 > 0 )
      v21 = (unsigned __int16)v19 | 0x80070000;
    IsErrorNotFound = tsched::IsErrorNotFound((tsched *)v21, v20);
    v115 = 0;
    if ( !IsErrorNotFound )
      v115 = v114;
    if ( (int)v115 < 0 )
    {
      v24 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_2e3cbcf08cb7377099a4c131f2f33a2b_Traceguids, v115);
      }
      RegistrationData = -2147216607;
      goto LABEL_45;
    }
  }
  operator delete(0);
  RegistrationData = Triggers::Trigulator::ReadRegistrationData((Triggers::Trigulator *)&v138, v18, Data, 0x400u);
  if ( RegistrationData < 0 )
    goto LABEL_45;
  cbData[0] = 0;
  lpcbData = 1024;
  RegistrationData = RegQueryValueExW(v18, L"Triggers", 0, cbData, Data, &lpcbData);
  if ( RegistrationData == 234 )
  {
    v112 = (BYTE *)operator new(lpcbData);
    v13 = v112;
    v154 = v112;
    if ( !v112 )
    {
      RegistrationData = -2147024882;
      goto LABEL_45;
    }
    lpData = v112;
    RegistrationData = RegQueryValueExW(v18, L"Triggers", 0, cbData, v112, &lpcbData);
  }
  else
  {
    lpData = Data;
  }
  if ( !RegistrationData )
  {
    if ( cbData[0] != 3 || (v27 = lpcbData, lpcbData != 8) && lpcbData < 0x28 )
    {
      RegistrationData = -2147418113;
      goto LABEL_45;
    }
LABEL_30:
    LOBYTE(lpMem) = 0;
    *(_DWORD *)((char *)&lpMem + 1) = *(_DWORD *)((char *)&v131 + 1);
    *(_WORD *)((char *)&lpMem + 5) = *(_WORD *)((char *)&v131 + 5);
    HIBYTE(lpMem) = HIBYTE(v131);
    v134 = -1;
    LOBYTE(v153[0]) = 0;
    *(_DWORD *)((char *)v153 + 1) = *(_DWORD *)((char *)&v131 + 1);
    *(_WORD *)((char *)v153 + 5) = *(_WORD *)((char *)&v131 + 5);
    HIBYTE(v153[0]) = HIBYTE(v131);
    v153[1] = 0;
    RegistrationData = Triggers::Trigulator::ParseTriggerBlobData(&v138, lpData, v27, v153, &lpMem, 15, 0);
    if ( RegistrationData < 0 )
      goto LABEL_45;
    v29 = 0;
    v153[0] = 0;
    v130[0] = 0;
    Type = 1024;
    v30 = RegQueryValueExW(v150, L"Package", 0, v130, lpData, &Type);
    RegistrationData = v30;
    if ( v30 )
    {
      if ( v30 == 2 )
      {
        v31 = 0;
        goto LABEL_34;
      }
    }
    else if ( v130[0] == 1 )
    {
      v31 = (const OLECHAR *)lpData;
      goto LABEL_34;
    }
    v31 = 0;
    if ( v30 == 234 )
    {
      if ( Type )
      {
        v111 = operator new(Type);
        wmi::AutoVectorPtr<unsigned char>::operator=(v153, v111);
        v29 = (BYTE *)v153[0];
        if ( !v153[0] )
        {
          LOWORD(RegistrationData) = 8;
          goto LABEL_200;
        }
      }
      RegistrationData = RegQueryValueExW(v150, L"Package", 0, v130, v29, &Type);
      if ( !RegistrationData && v130[0] == 1 )
        v31 = (const OLECHAR *)v29;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        (unsigned int)WPP_2e3cbcf08cb7377099a4c131f2f33a2b_Traceguids,
        (unsigned int)L"Package",
        RegistrationData);
    }
    if ( RegistrationData )
    {
      if ( RegistrationData <= 0 )
      {
LABEL_201:
        operator delete(v29);
        goto LABEL_44;
      }
LABEL_200:
      RegistrationData = (unsigned __int16)RegistrationData | 0x80070000;
      goto LABEL_201;
    }
LABEL_34:
    v32 = v149;
    _bstr_t::~_bstr_t((JobBucket *)((char *)v149 + 176));
    v33 = (BSTR *)HeapAlloc(g_PrivateHeap, 0, 0x18u);
    v34 = v33;
    if ( !v33 )
    {
      BYTE8(pExceptionObject) = 0;
      v156 = &qword_1800A4718;
      v157 = 0;
      v158 = 0;
      v159 = 14;
      v160 = -1;
      *(_QWORD *)&pExceptionObject = &wmi::GenericException::`vftable';
      throw (wmi::OutOfMemoryException *)&pExceptionObject;
    }
    lpMem = v33;
    v33[1] = 0;
    *((_DWORD *)v33 + 4) = 1;
    v35 = SysAllocString(v31);
    *v34 = v35;
    if ( !v35 && v31 )
      _com_raise_error(-2147024882, v36);
    *((_QWORD *)v32 + 22) = v34;
    Type = 0;
    v130[0] = 1024;
    v37 = v150;
    v38 = RegQueryValueExW(v150, L"Capabilities", 0, &Type, lpData, v130);
    RegistrationData = v38;
    if ( v38 )
    {
      if ( v38 == 2 )
      {
        std::vector<_bstr_t>::clear((char *)v149 + 184);
LABEL_40:
        if ( v29 )
          HeapFree(g_PrivateHeap, 0, v29);
        RegistrationData = 0;
        goto LABEL_43;
      }
    }
    else if ( Type == 7 )
    {
      v117 = v130[0] >> 1;
      goto LABEL_39;
    }
    lpData = 0;
    v117 = 0;
    if ( v38 == 234 )
    {
      if ( v130[0] )
      {
        v118 = operator new(v130[0]);
        wmi::AutoVectorPtr<unsigned char>::operator=(v153, v118);
        v29 = (BYTE *)v153[0];
        if ( !v153[0] )
        {
          LOWORD(RegistrationData) = 8;
          goto LABEL_203;
        }
      }
      RegistrationData = RegQueryValueExW(v37, L"Capabilities", 0, &Type, v29, v130);
      if ( !RegistrationData && Type == 7 )
      {
        lpData = v29;
        v117 = v130[0] >> 1;
      }
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        12,
        (unsigned int)WPP_2e3cbcf08cb7377099a4c131f2f33a2b_Traceguids,
        (unsigned int)L"Capabilities",
        RegistrationData);
    }
    if ( RegistrationData )
    {
      if ( RegistrationData <= 0 )
      {
LABEL_204:
        operator delete(v29);
LABEL_43:
        v5 = (ULONG *)v151;
LABEL_44:
        v6 = v131;
        goto LABEL_45;
      }
LABEL_203:
      RegistrationData = (unsigned __int16)RegistrationData | 0x80070000;
      goto LABEL_204;
    }
LABEL_39:
    v39 = v149;
    std::vector<_bstr_t>::clear((char *)v149 + 184);
    if ( lpData && (_DWORD)v117 )
    {
      lpMem = 0;
      while ( v117 && *(_WORD *)lpData )
      {
        JobBucket::AddCapability(v39, (const unsigned __int16 *)lpData);
        v119 = StringCchLengthW((const unsigned __int16 *)lpData, v117, (unsigned __int64 *)&lpMem);
        if ( v119 < 0 )
        {
          BYTE8(pExceptionObject) = 0;
          *(_QWORD *)&pExceptionObject = &wmi::GenericException::`vftable';
          v156 = &qword_1800A4718;
          v157 = 0;
          v158 = 0;
          v159 = v119;
          v160 = -1;
          throw (wmi::GenericException *)&pExceptionObject;
        }
        v24 = lpMem;
        lpData += 2 * (_QWORD)lpMem + 2;
        v117 += -1LL - (_QWORD)lpMem;
      }
    }
    goto LABEL_40;
  }
  lpData = 0;
  v27 = 1024;
  v24 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_Sdd(*((_QWORD *)WPP_GLOBAL_Control + 2));
  }
  v116 = RegistrationData < 0;
  if ( RegistrationData > 0 )
  {
    RegistrationData = (unsigned __int16)RegistrationData | 0x80070000;
    v116 = RegistrationData < 0;
  }
  if ( !v116 )
    goto LABEL_30;
LABEL_45:
  if ( v13 )
    HeapFree(g_PrivateHeap, 0, v13);
  if ( RegistrationData < 0 )
  {
    v22 = RegistrationData;
    goto LABEL_161;
  }
  v134 = 0;
  lpMem = (LPVOID)std::_List_alloc<0,std::_List_base_types<Triggers::Trigger *>>::_Buynode0(v24, 0, 0);
  v135 = 0;
  memset_0(Data, 0, 0x200u);
  v130[0] = 512;
  Type = 3;
  v40 = v150;
  v41 = RegQueryValueExW(v150, L"Actions", 0, &Type, Data, v130);
  v44 = v41;
  if ( v41 )
  {
    if ( v41 != 234 || Type != 3 )
    {
      v45 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          10,
          (unsigned int)WPP_fa1b8c42477831648a2e44d3a9ea2fb6_Traceguids,
          (unsigned int)L"Actions",
          v41);
        v45 = WPP_GLOBAL_Control;
      }
      if ( v44 > 0 )
        v22 = (unsigned __int16)v44 | 0x80070000;
      else
        v22 = v44;
      goto LABEL_51;
    }
    v151 = 0;
    v120 = operator new(v130[0]);
    wmi::AutoVectorPtr<unsigned char>::operator=(&v151, v120);
    v121 = v151;
    if ( v151 )
    {
      v122 = RegQueryValueExW(v40, L"Actions", 0, &Type, v151, v130);
      v22 = v122;
      if ( v122 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            12,
            (unsigned int)WPP_fa1b8c42477831648a2e44d3a9ea2fb6_Traceguids,
            (unsigned int)L"Actions",
            v122);
        }
        if ( v22 > 0 )
          v22 = (unsigned __int16)v22 | 0x80070000;
        operator delete(v121);
        v45 = WPP_GLOBAL_Control;
      }
      else
      {
        v22 = Actions::ActionCollection::ReadData((Actions::ActionCollection *)&lpMem, v121, v130[0], 0);
        operator delete(v121);
        v45 = WPP_GLOBAL_Control;
      }
      goto LABEL_51;
    }
    operator delete(0);
LABEL_255:
    Actions::ActionCollection::~ActionCollection((Actions::ActionCollection *)&lpMem, v42);
    goto LABEL_161;
  }
  if ( Type != 3 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        (unsigned int)WPP_fa1b8c42477831648a2e44d3a9ea2fb6_Traceguids,
        (unsigned int)L"Actions",
        255);
    }
    v22 = -2147418113;
    goto LABEL_255;
  }
  v22 = Actions::ActionCollection::ReadData((Actions::ActionCollection *)&lpMem, Data, v130[0], 0);
  v45 = WPP_GLOBAL_Control;
LABEL_51:
  if ( v22 < 0 )
    goto LABEL_255;
  v46 = v149;
  if ( !v149 )
  {
    Actions::ActionCollection::~ActionCollection((Actions::ActionCollection *)&lpMem, v42);
    Triggers::Trigulator::~Trigulator((Triggers::Trigulator *)&v138);
    wmi::AutoRegKey::Close(&hKey);
    return 2147549183LL;
  }
  v156 = 0;
  v158 = 0;
  if ( v45 != &WPP_GLOBAL_Control && (*((_BYTE *)v45 + 28) & 0x40) != 0 )
  {
    v47 = v152;
    if ( *((_BYTE *)v45 + 25) >= 4u )
      WPP_SF_qqq(v45[2], v42, v43, &pExceptionObject, v152, v149);
  }
  else
  {
    v47 = v152;
  }
  if ( v46 )
    _InterlockedIncrement((volatile signed __int32 *)v46 + 2);
  wmi::AutoRef<JobBucket>::Release(&v158);
  v158 = v46;
  v48 = *((_QWORD *)v47 + 2);
  if ( v48 )
    _InterlockedIncrement((volatile signed __int32 *)(v48 + 16));
  _bstr_t::~_bstr_t((_bstr_t *)&v156);
  v49 = *((_QWORD *)v47 + 2);
  v156 = (const unsigned __int16 *)v49;
  v157 = *((_QWORD *)v47 + 3);
  pExceptionObject = *(_OWORD *)v47;
  if ( v49 )
    _InterlockedIncrement((volatile signed __int32 *)(v49 + 16));
  _bstr_t::~_bstr_t((JobMoniker *)((char *)v47 + 16));
  *((_QWORD *)v47 + 2) = v156;
  *((_QWORD *)v47 + 3) = v157;
  *(_OWORD *)v47 = pExceptionObject;
  v50 = v158;
  if ( v158 )
    _InterlockedIncrement((volatile signed __int32 *)v158 + 2);
  wmi::AutoRef<JobBucket>::Release((char *)v47 + 32);
  *((_QWORD *)v47 + 4) = v50;
  v51 = v158;
  if ( v158 && _InterlockedExchangeAdd((volatile signed __int32 *)v158 + 2, 0xFFFFFFFF) == 1 )
    (**(void (__fastcall ***)(JobBucket *, __int64))v51)(v51, 1);
  v158 = 0;
  _bstr_t::~_bstr_t((_bstr_t *)&v156);
  v22 = JobStore::GenerateTaskXmlFromCollections(v52, v47, &v138, &lpMem, v137);
  if ( v22 < 0 )
    goto LABEL_255;
  if ( !v5 || !*v5 )
  {
LABEL_70:
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      Path = (unsigned int)JobMoniker::GetPath(v47);
      WPP_SF_S_guid_(*((_QWORD *)WPP_GLOBAL_Control + 2), v66, v67, Path, (__int64)v47);
    }
    if ( v134 )
    {
      v53 = lpMem;
      for ( j = *(_QWORD **)lpMem; j != v53; j = (_QWORD *)*j )
      {
        v63 = (void (__fastcall ***)(_QWORD, __int64))j[2];
        if ( v63 )
        {
          (**v63)(v63, 1);
          j[2] = 0;
        }
      }
      v55 = (_QWORD *)*v53;
      *v53 = v53;
      v53[1] = v53;
      v134 = 0;
      if ( v55 != v53 )
      {
        do
        {
          v106 = (_QWORD *)*v55;
          HeapFree(g_PrivateHeap, 0, v55);
          v55 = v106;
        }
        while ( v106 != v53 );
      }
    }
    v56 = (BSTR *)v135;
    if ( v135 )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v135 + 4, 0xFFFFFFFF) == 1 )
      {
        if ( *v56 )
        {
          SysFreeString(*v56);
          *v56 = 0;
        }
        v107 = v56[1];
        if ( v107 )
        {
          operator delete(v107);
          v56[1] = 0;
        }
        HeapFree(g_PrivateHeap, 0, v56);
      }
      v135 = 0;
    }
    std::list<Task *>::clear((__int64)&lpMem);
    if ( lpMem )
      HeapFree(g_PrivateHeap, 0, lpMem);
    if ( v148[1] )
    {
      v57 = (void ***)v148[0];
      for ( k = *(void ****)v148[0]; k != v57; k = (void ***)*k )
      {
        v64 = k[2];
        if ( v64 )
        {
          (*(void (__fastcall **)(void **, __int64))*v64)(v64, 1);
          k[2] = 0;
          v57 = (void ***)v148[0];
        }
      }
      v59 = *v57;
      *v57 = (void **)v57;
      *((LPVOID *)v148[0] + 1) = v148[0];
      v148[1] = 0;
      if ( v59 != v148[0] )
      {
        do
        {
          v60 = (void **)*v59;
          HeapFree(g_PrivateHeap, 0, v59);
          v59 = v60;
        }
        while ( v60 != v148[0] );
      }
    }
    v138 = 0;
    v139 = *(_DWORD *)((char *)&v131 + 1);
    v140 = *(_WORD *)((char *)&v131 + 5);
    v141 = HIBYTE(v131);
    SystemTimeAsFileTime = (struct _FILETIME)-1LL;
    v143 = 0;
    v144 = *(_DWORD *)((char *)&v131 + 1);
    v145 = *(_WORD *)((char *)&v131 + 5);
    v146 = HIBYTE(v131);
    v147 = 0;
    v61 = v149;
    if ( v149 && _InterlockedExchangeAdd((volatile signed __int32 *)v149 + 2, 0xFFFFFFFF) == 1 )
      (**(void (__fastcall ***)(JobBucket *, __int64))v61)(v61, 1);
    v149 = 0;
    std::list<Triggers::Trigger *>::clear(v148);
    if ( v148[0] )
      HeapFree(g_PrivateHeap, 0, v148[0]);
LABEL_90:
    if ( v150 )
      RegCloseKey(v150);
    return (unsigned int)v22;
  }
  v68 = -1;
  do
    ++v68;
  while ( *((_WORD *)v6 + v68) );
  v69 = v68 + 1;
  v71 = v68 + 2;
  v70 = 2 * (v68 + 2);
  if ( !is_mul_ok(v71, 2u) )
    v70 = -1;
  v72 = (BYTE *)HeapAlloc(g_PrivateHeap, 0, v70);
  v73 = (WCHAR *)v72;
  if ( !v72 )
  {
    BYTE8(pExceptionObject) = 0;
    v156 = &qword_1800A4718;
    v157 = 0;
    v158 = 0;
    v159 = 14;
    v160 = -1;
    *(_QWORD *)&pExceptionObject = &wmi::GenericException::`vftable';
    throw (wmi::OutOfMemoryException *)&pExceptionObject;
  }
  v151 = v72;
  for ( m = 0; m < v69; ++m )
  {
    v110 = 0;
    if ( *((_WORD *)v6 + m) != 92 )
      v110 = *((_WORD *)v6 + m);
    v73[m] = v110;
  }
  v73[v69] = 0;
  *(_QWORD *)v130 = 0;
  Type = 0;
  cbData[0] = 0;
  if ( !GetThreadPreferredUILanguages(0x48u, &Type, 0, cbData) )
  {
    LastError = GetLastError();
    BYTE8(pExceptionObject) = 0;
    *(_QWORD *)&pExceptionObject = &wmi::GenericException::`vftable';
    v156 = &qword_1800A4718;
    v157 = 0;
    v158 = 0;
    v159 = LastError;
    v160 = -1;
    throw (wmi::GenericException *)&pExceptionObject;
  }
  *(_QWORD *)v130 = operator new(saturated_mul(cbData[0], 2u));
  if ( !GetThreadPreferredUILanguages(0x48u, &Type, *(PZZWSTR *)v130, cbData) )
  {
    v124 = GetLastError();
    wmi::AutoVectorPtr<unsigned short>::operator=(v130, 0);
    BYTE8(pExceptionObject) = 0;
    *(_QWORD *)&pExceptionObject = &wmi::GenericException::`vftable';
    v156 = &qword_1800A4718;
    v157 = 0;
    v158 = 0;
    v159 = v124;
    v160 = -1;
    throw (wmi::GenericException *)&pExceptionObject;
  }
  if ( !SetThreadPreferredUILanguages(8u, v73, v5) )
  {
    v125 = GetLastError();
    BYTE8(pExceptionObject) = 0;
    *(_QWORD *)&pExceptionObject = &wmi::GenericException::`vftable';
    v156 = &qword_1800A4718;
    v157 = 0;
    v158 = 0;
    v159 = v125;
    v160 = -1;
    throw (wmi::GenericException *)&pExceptionObject;
  }
  *(_QWORD *)cbData = 0;
  v75 = (LPVOID *)v137;
  v76 = *(_QWORD *)v137;
  if ( !*(_QWORD *)v137 )
  {
    ATL::CComPtrBase<IStream>::~CComPtrBase<IStream>((__int64 *)cbData);
    AutoThreadUIPreferredLanguages::~AutoThreadUIPreferredLanguages((LPVOID *)v130);
    operator delete(v73);
    Actions::ActionCollection::~ActionCollection((Actions::ActionCollection *)&lpMem, v126);
    Triggers::Trigulator::~Trigulator((Triggers::Trigulator *)&v138);
    wmi::AutoRegKey::Close(&hKey);
    return 2147942487LL;
  }
  v77 = -1;
  do
    ++v77;
  while ( *(_WORD *)(v76 + 2 * v77) );
  v78 = (StringStream *)HeapAlloc(g_PrivateHeap, 0, 0x28u);
  if ( !v78 )
  {
    BYTE8(pExceptionObject) = 0;
    v156 = &qword_1800A4718;
    v157 = 0;
    v158 = 0;
    v159 = 14;
    v160 = -1;
    *(_QWORD *)&pExceptionObject = &wmi::GenericException::`vftable';
    throw (wmi::OutOfMemoryException *)&pExceptionObject;
  }
  StringStream::StringStream(v78);
  *(_QWORD *)v79 = &StringReader::`vftable';
  *(_QWORD *)(v79 + 16) = -1;
  *(_DWORD *)(v79 + 24) = v77;
  *(_QWORD *)(v79 + 32) = v76;
  v137 = 0;
  v81 = ((__int64 (__fastcall *)(__int64, GUID *, wmi::RefBase **))StringReader::`vftable')(
          v79,
          &GUID_0000000c_0000_0000_c000_000000000046,
          &v137);
  if ( v81 < 0 )
  {
    ATL::CComPtrBase<IStream>::~CComPtrBase<IStream>((__int64 *)cbData);
    v82 = 0;
    *(_QWORD *)cbData = 0;
    v83 = 0;
  }
  else
  {
    v82 = v137;
    *(_QWORD *)cbData = v137;
    v83 = v137;
  }
  if ( (int)(v81 + 0x80000000) >= 0 && v81 != -2147467262 )
    _com_raise_error(v81, v80);
  if ( !v83 )
  {
    BYTE8(pExceptionObject) = 0;
    v156 = &qword_1800A4718;
    v157 = 0;
    v158 = 0;
    v159 = 14;
    v160 = -1;
    *(_QWORD *)&pExceptionObject = &wmi::GenericException::`vftable';
    throw (wmi::OutOfMemoryException *)&pExceptionObject;
  }
  v84 = (wmi::RefBase *)HeapAlloc(g_PrivateHeap, 0, 0x460u);
  v85 = v84;
  v137 = v84;
  if ( !v84 )
  {
    BYTE8(pExceptionObject) = 0;
    v156 = &qword_1800A4718;
    v157 = 0;
    v158 = 0;
    v159 = 14;
    v160 = -1;
    *(_QWORD *)&pExceptionObject = &wmi::GenericException::`vftable';
    throw (wmi::OutOfMemoryException *)&pExceptionObject;
  }
  *(_QWORD *)v84 = &wmi::RefBase::`vftable';
  *((_DWORD *)v84 + 2) = 0;
  *(_QWORD *)v84 = &TaskXmlReader::`vftable';
  *((_QWORD *)v84 + 2) = 0;
  *((_QWORD *)v84 + 3) = 0;
  *((_QWORD *)v84 + 4) = v83;
  (*(void (__fastcall **)(wmi::RefBase *))(*(_QWORD *)v83 + 8LL))(v83);
  *((_BYTE *)v85 + 40) = 1;
  *((_QWORD *)v85 + 6) = 0;
  *((_QWORD *)v85 + 7) = 0;
  *((_BYTE *)v85 + 1106) &= 0xFCu;
  *((_DWORD *)v85 + 16) = 0;
  *((_QWORD *)v85 + 9) = 0;
  *((_WORD *)v85 + 40) = 0;
  *((_BYTE *)v85 + 1112) = 0;
  *((_DWORD *)v85 + 279) = 65542;
  v131 = v85;
  _InterlockedIncrement((volatile signed __int32 *)v85 + 2);
  v7 = TaskXmlReader::ProcessXml(v85, 0);
  if ( v7 >= 0 )
  {
    if ( *v75 )
      HeapFree(g_PrivateHeap, 0, *v75);
    *v75 = 0;
    v86 = 0;
    v154 = 0;
    v87 = *((_QWORD *)v85 + 3);
    if ( !v87 )
      ATL::PrivateAtlThrow(0x80004005);
    v88 = SysAllocStringLen(0, *(_DWORD *)(v87 + 16));
    if ( v88 )
    {
      SysFreeString(0);
      v89 = v88;
      v90 = *(_QWORD *)(v87 + 16) + 1LL;
      for ( n = *(_QWORD *)(v87 + 24); n; n = *(_QWORD *)(n + 16) )
      {
        if ( !v90 )
          goto LABEL_136;
        if ( v90 > 0x7FFFFFFF || (v92 = *(_QWORD *)(n + 8), v92 > 0x7FFFFFFE) )
        {
          *v89 = 0;
LABEL_136:
          SysFreeString(v88);
          goto LABEL_139;
        }
        v93 = *(OLECHAR **)n;
        v94 = v90;
        v95 = v89;
        while ( v92 )
        {
          v96 = *v93;
          if ( !*v93 )
            break;
          ++v93;
          *v95++ = v96;
          --v92;
          if ( !--v94 )
          {
            *(v95 - 1) = 0;
            goto LABEL_136;
          }
        }
        *v95 = 0;
        v97 = *(_QWORD *)(n + 8);
        v89 += v97;
        v90 -= v97;
      }
      SysFreeString(0);
      SysFreeString(0);
      v86 = v88;
      v154 = v88;
    }
    else
    {
      SysFreeString(0);
    }
LABEL_139:
    v98 = SysStringLen(v86);
    v99 = v98 + 1;
    v100 = 2 * (v98 + 1);
    if ( !is_mul_ok(v98 + 1, 2u) )
      v100 = -1;
    v101 = (OLECHAR *)HeapAlloc(g_PrivateHeap, 0, v100);
    if ( !v101 )
    {
      BYTE8(pExceptionObject) = 0;
      v156 = &qword_1800A4718;
      v157 = 0;
      v158 = 0;
      v159 = 14;
      v160 = -1;
      *(_QWORD *)&pExceptionObject = &wmi::GenericException::`vftable';
      throw (wmi::OutOfMemoryException *)&pExceptionObject;
    }
    if ( *v75 )
      HeapFree(g_PrivateHeap, 0, *v75);
    *v75 = v101;
    if ( v99 > 0x7FFFFFFF )
    {
      v22 = -2147024809;
      *v101 = 0;
    }
    else if ( v98 > 0x7FFFFFFE )
    {
      v22 = -2147024809;
      *v101 = 0;
    }
    else
    {
      v102 = v86;
      while ( v98 )
      {
        v103 = *v102;
        if ( !*v102 )
          break;
        ++v102;
        *v101++ = v103;
        --v98;
        if ( !--v99 )
          goto LABEL_150;
      }
      v22 = 0;
      if ( !v99 )
      {
LABEL_150:
        --v101;
        v22 = -2147024774;
      }
      *v101 = 0;
      if ( v22 >= 0 )
      {
        SysFreeString(v86);
        v104 = v137;
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v137 + 2, 0xFFFFFFFF) == 1 )
          (**(void (__fastcall ***)(wmi::RefBase *, __int64))v104)(v104, 1);
        (*(void (__fastcall **)(wmi::RefBase *))(*(_QWORD *)v82 + 16LL))(v82);
        v105 = *(PZZWSTR *)v130;
        if ( *(_QWORD *)v130 )
        {
          cbData[0] = 0;
          SetThreadPreferredUILanguages(8u, *(PCZZWSTR *)v130, cbData);
          HeapFree(g_PrivateHeap, 0, v105);
        }
        HeapFree(g_PrivateHeap, 0, v73);
        v47 = v152;
        goto LABEL_70;
      }
    }
    SysFreeString(v86);
    wmi::RefBase::Release(v137);
    (*(void (__fastcall **)(wmi::RefBase *))(*(_QWORD *)v82 + 16LL))(v82);
    v108 = *(PZZWSTR *)v130;
    if ( *(_QWORD *)v130 )
    {
      cbData[0] = 0;
      SetThreadPreferredUILanguages(8u, *(PCZZWSTR *)v130, cbData);
      HeapFree(g_PrivateHeap, 0, v108);
    }
    HeapFree(g_PrivateHeap, 0, v73);
    Actions::ActionCollection::~ActionCollection((Actions::ActionCollection *)&lpMem, v109);
    Triggers::Trigulator::~Trigulator((Triggers::Trigulator *)&v138);
    goto LABEL_90;
  }
  wmi::AutoRef<TaskXmlReader>::Release(&v131);
  ATL::CComPtrBase<IStream>::~CComPtrBase<IStream>((__int64 *)cbData);
  AutoThreadUIPreferredLanguages::~AutoThreadUIPreferredLanguages((LPVOID *)v130);
  operator delete(v73);
  Actions::ActionCollection::~ActionCollection((Actions::ActionCollection *)&lpMem, v127);
  Triggers::Trigulator::~Trigulator((Triggers::Trigulator *)&v138);
LABEL_282:
  wmi::AutoRegKey::Close(&hKey);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000c3c0  push    rbp
0x18000c3c2  push    rbx
0x18000c3c3  push    rsi
0x18000c3c4  push    rdi
0x18000c3c5  push    r12
0x18000c3c7  push    r13
0x18000c3c9  push    r14
0x18000c3cb  push    r15
0x18000c3cd  lea     rbp, [rsp-458h]
0x18000c3d5  sub     rsp, 558h
0x18000c3dc  mov     rax, cs:__security_cookie
0x18000c3e3  xor     rax, rsp
0x18000c3e6  mov     [rbp+490h+var_50], rax
0x18000c3ed  mov     r13, r9
0x18000c3f0  mov     [rbp+490h+var_4B0], r9
0x18000c3f4  mov     r12, r8
0x18000c3f7  mov     [rsp+590h+var_538], r8
0x18000c3fc  mov     [rbp+490h+var_4A8], rdx
0x18000c400  mov     rax, [rbp+490h+arg_20]
0x18000c407  mov     [rbp+490h+var_4F8], rax
0x18000c40b  xor     r15d, r15d
0x18000c40e  mov     [rbp+490h+hKey], r15
0x18000c412  mov     r9d, 20019h; unsigned int
0x18000c418  lea     r8, [rbp+490h+hKey]; HKEY *
0x18000c41c  call    ?RegOpenTaskKey@JobStore@@QEAAJAEAVJobMoniker@@PEAPEAUHKEY__@@K@Z; JobStore::RegOpenTaskKey(JobMoniker &,HKEY__ * *,ulong)
0x18000c421  mov     ebx, eax
0x18000c423  test    eax, eax
0x18000c425  js      loc_18000DB16
0x18000c42b  mov     [rbp+490h+var_4F0], r15b
0x18000c42f  lea     rcx, [rbp+490h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000c433  call    cs:__imp_GetSystemTimeAsFileTime
0x18000c439  mov     [rbp+490h+var_4E0], r15b
0x18000c43d  lea     rcx, [rbp+490h+var_4D8]; lpSystemTimeAsFileTime
0x18000c441  call    cs:__imp_GetSystemTimeAsFileTime
0x18000c447  xorps   xmm0, xmm0
0x18000c44a  movdqu  xmmword ptr [rbp+490h+var_4D0], xmm0
0x18000c44f  xor     r8d, r8d
0x18000c452  xor     edx, edx
0x18000c454  call    ?_Buynode0@?$_List_alloc@$0A@U?$_List_base_types@PEAUTrigger@Triggers@@V?$allocator@PEAUTrigger@Triggers@@@std@@@std@@@std@@QEAAPEAU?$_List_node@PEAUTrigger@Triggers@@PEAX@2@PEAU32@0@Z; std::_List_alloc<0,std::_List_base_types<Triggers::Trigger *>>::_Buynode0(std::_List_node<Triggers::Trigger *,void *> *,std::_List_node<Triggers::Trigger *,void *> *)
0x18000c459  mov     [rbp+490h+var_4D0], rax
0x18000c45d  mov     [rbp+490h+var_4C0], r15
0x18000c461  cmp     [rbp+490h+var_4D0+8], r15
0x18000c465  jz      short loc_18000C4A6
0x18000c467  mov     rbx, [rax]
0x18000c46a  cmp     rbx, rax
0x18000c46d  jnz     loc_18000C681
0x18000c473  mov     r8, [rax]; lpMem
0x18000c476  mov     [rax], rax
0x18000c479  mov     rax, [rbp+490h+var_4D0]
0x18000c47d  mov     [rax+8], rax
0x18000c481  mov     [rbp+490h+var_4D0+8], r15
0x18000c485  cmp     r8, [rbp+490h+var_4D0]
0x18000c489  jz      short loc_18000C4A6
0x18000c48b  mov     rbx, [r8]
0x18000c48e  xor     edx, edx; dwFlags
0x18000c490  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x18000c497  call    cs:__imp_HeapFree
0x18000c49d  mov     r8, rbx
0x18000c4a0  cmp     rbx, [rbp+490h+var_4D0]
0x18000c4a4  jnz     short loc_18000C48B
0x18000c4a6  mov     [rbp+490h+var_4F0], 0
0x18000c4aa  mov     eax, dword ptr [rsp+590h+var_538+1]
0x18000c4ae  mov     [rbp+490h+var_4EF], eax
0x18000c4b1  movzx   eax, word ptr [rsp+590h+var_538+5]
0x18000c4b6  mov     [rbp+490h+var_4EB], ax
0x18000c4ba  movzx   eax, byte ptr [rsp+590h+var_538+7]
0x18000c4bf  mov     [rbp+490h+var_4E9], al
0x18000c4c2  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x18000c4c9  mov     qword ptr [rbp+490h+SystemTimeAsFileTime.dwLowDateTime], rsi
0x18000c4cd  mov     [rbp+490h+var_4E0], 0
0x18000c4d1  mov     eax, dword ptr [rsp+590h+var_538+1]
0x18000c4d5  mov     [rbp+490h+var_4DF], eax
0x18000c4d8  movzx   eax, word ptr [rsp+590h+var_538+5]
0x18000c4dd  mov     [rbp+490h+var_4DB], ax
0x18000c4e1  movzx   eax, byte ptr [rsp+590h+var_538+7]
0x18000c4e6  mov     [rbp+490h+var_4D9], al
0x18000c4e9  mov     qword ptr [rbp+490h+var_4D8.dwLowDateTime], r15
0x18000c4ed  mov     rbx, r15
0x18000c4f0  mov     [rbp+490h+var_490], rbx
0x18000c4f4  xor     edx, edx; Val
0x18000c4f6  mov     r8d, 400h; Size
0x18000c4fc  lea     rcx, [rbp+490h+Data]; void *
0x18000c500  call    memset_0
0x18000c505  xor     edx, edx; dwFlags
0x18000c507  mov     r8d, 0D8h; dwBytes
0x18000c50d  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x18000c514  call    cs:__imp_HeapAlloc
0x18000c51a  test    rax, rax
0x18000c51d  jz      loc_18000D3F4
0x18000c523  mov     rcx, rax; this
0x18000c526  call    ??0JobBucket@@QEAA@XZ; JobBucket::JobBucket(void)
0x18000c52b  mov     rdi, rax
0x18000c52e  test    rax, rax
0x18000c531  jz      short loc_18000C537
0x18000c533  lock inc dword ptr [rax+8]
0x18000c537  mov     rcx, [rbp+490h+var_4C0]
0x18000c53b  test    rcx, rcx
0x18000c53e  jz      short loc_18000C557
0x18000c540  mov     edx, esi
0x18000c542  lock xadd [rcx+8], edx
0x18000c547  cmp     edx, 1
0x18000c54a  jnz     short loc_18000C557
0x18000c54c  mov     rax, [rcx]
0x18000c54f  mov     rax, [rax]
0x18000c552  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c557  mov     [rbp+490h+var_4C0], rdi
0x18000c55b  test    rdi, rdi
0x18000c55e  jz      loc_18000D140
0x18000c564  mov     rsi, [rbp+490h+hKey]
0x18000c568  mov     [rbp+490h+var_4B8], rsi
0x18000c56c  mov     [rsp+590h+cbData], 400h
0x18000c574  mov     [rsp+590h+lpMem], r15
0x18000c579  mov     [rsp+590h+Type], r15d
0x18000c57e  lea     rax, [rsp+590h+cbData]
0x18000c583  mov     [rsp+590h+lpcbData], rax; lpcbData
0x18000c588  lea     rax, [rbp+490h+Data]
0x18000c58c  mov     [rsp+590h+lpData], rax; lpData
0x18000c591  lea     r9, [rsp+590h+Type]; lpType
0x18000c596  xor     r8d, r8d; lpReserved
0x18000c599  lea     rdx, aHash; "Hash"
0x18000c5a0  mov     rcx, rsi; hKey
0x18000c5a3  call    cs:__imp_RegQueryValueExW
0x18000c5a9  mov     ecx, eax
0x18000c5ab  mov     r14d, 8007000Eh
0x18000c5b1  test    eax, eax
0x18000c5b3  jnz     loc_18000D2F4
0x18000c5b9  cmp     [rsp+590h+cbData], 20h ; ' '
0x18000c5be  jnz     loc_18000D2F4
0x18000c5c4  cmp     [rsp+590h+Type], 3
0x18000c5c9  jnz     loc_18000D2F4
0x18000c5cf  mov     rax, [rbp+490h+var_4C0]
0x18000c5d3  movaps  xmm0, xmmword ptr [rbp+490h+Data]
0x18000c5d7  movups  xmmword ptr [rax+1Ch], xmm0
0x18000c5db  movaps  xmm1, [rbp+490h+var_440]
0x18000c5df  movups  xmmword ptr [rax+2Ch], xmm1
0x18000c5e3  mov     dword ptr [rax+3Ch], 1
0x18000c5ea  xor     ecx, ecx; void *
0x18000c5ec  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000c5f1  mov     r9d, 400h; unsigned int
0x18000c5f7  lea     r8, [rbp+490h+Data]; unsigned __int8 *
0x18000c5fb  mov     rdx, rsi; HKEY
0x18000c5fe  lea     rcx, [rbp+490h+var_4F0]; this
0x18000c602  call    ?ReadRegistrationData@Trigulator@Triggers@@AEAAJPEAUHKEY__@@PEAEK@Z; Triggers::Trigulator::ReadRegistrationData(HKEY__ *,uchar *,ulong)
0x18000c607  mov     edi, eax
0x18000c609  test    eax, eax
0x18000c60b  js      loc_18000C87F
0x18000c611  mov     [rsp+590h+cbData], r15d
0x18000c616  mov     [rsp+590h+var_528], 400h
0x18000c61e  lea     rax, [rsp+590h+var_528]
0x18000c623  mov     [rsp+590h+lpcbData], rax; lpcbData
0x18000c628  lea     rax, [rbp+490h+Data]
0x18000c62c  mov     [rsp+590h+lpData], rax; lpData
0x18000c631  lea     r9, [rsp+590h+cbData]; lpType
0x18000c636  xor     r8d, r8d; lpReserved
0x18000c639  lea     rdx, aTriggers; "Triggers"
0x18000c640  mov     rcx, rsi; hKey
0x18000c643  call    cs:__imp_RegQueryValueExW
0x18000c649  mov     edi, eax
0x18000c64b  cmp     eax, 0EAh
0x18000c650  jz      loc_18000D2AA
0x18000c656  lea     r15, [rbp+490h+Data]
0x18000c65a  test    edi, edi
0x18000c65c  jnz     loc_18000D43E
0x18000c662  cmp     [rsp+590h+cbData], 3
0x18000c667  jnz     short loc_18000C677
0x18000c669  mov     esi, [rsp+590h+var_528]
0x18000c66d  cmp     esi, 8
0x18000c670  jz      short loc_18000C6B0
0x18000c672  cmp     esi, 28h ; '('
0x18000c675  jnb     short loc_18000C6B0
0x18000c677  mov     edi, 8000FFFFh
0x18000c67c  jmp     loc_18000C87F
0x18000c681  mov     rcx, [rbx+10h]
0x18000c685  test    rcx, rcx
0x18000c688  jz      short loc_18000C6A2
0x18000c68a  mov     rax, [rcx]
0x18000c68d  mov     edx, 1
0x18000c692  mov     rax, [rax]
0x18000c695  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c69a  mov     [rbx+10h], r15
0x18000c69e  mov     rax, [rbp+490h+var_4D0]
0x18000c6a2  mov     rbx, [rbx]
0x18000c6a5  jmp     loc_18000C46A
0x18000c6aa  js      loc_18000C87F
0x18000c6b0  mov     byte ptr [rsp+590h+lpMem], 0
0x18000c6b5  mov     eax, dword ptr [rsp+590h+var_538+1]
0x18000c6b9  mov     dword ptr [rsp+590h+lpMem+1], eax
0x18000c6bd  movzx   eax, word ptr [rsp+590h+var_538+5]
0x18000c6c2  mov     word ptr [rsp+590h+lpMem+5], ax
0x18000c6c7  movzx   eax, byte ptr [rsp+590h+var_538+7]
0x18000c6cc  mov     byte ptr [rsp+590h+lpMem+7], al
0x18000c6d0  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000c6d7  mov     [rsp+590h+var_518], rcx
0x18000c6dc  mov     byte ptr [rbp+490h+var_4A0], 0
0x18000c6e0  mov     eax, dword ptr [rsp+590h+var_538+1]
0x18000c6e4  mov     dword ptr [rbp+490h+var_4A0+1], eax
0x18000c6e7  movzx   eax, word ptr [rsp+590h+var_538+5]
0x18000c6ec  mov     word ptr [rbp+490h+var_4A0+5], ax
0x18000c6f0  movzx   eax, byte ptr [rsp+590h+var_538+7]
0x18000c6f5  mov     byte ptr [rbp+490h+var_4A0+7], al
0x18000c6f8  xor     eax, eax
0x18000c6fa  mov     [rbp+490h+var_498], rax
0x18000c6fe  mov     [rsp+590h+var_560], rax
0x18000c703  mov     dword ptr [rsp+590h+lpcbData], 0Fh
0x18000c70b  lea     rax, [rsp+590h+lpMem]
0x18000c710  mov     [rsp+590h+lpData], rax
0x18000c715  lea     r9, [rbp+490h+var_4A0]
0x18000c719  mov     r8d, esi
0x18000c71c  mov     rdx, r15
0x18000c71f  lea     rcx, [rbp+490h+var_4F0]
0x18000c723  call    ?ParseTriggerBlobData@Trigulator@Triggers@@AEAAJPEAEKVTSTime@@1KPEA_K@Z; Triggers::Trigulator::ParseTriggerBlobData(uchar *,ulong,TSTime,TSTime,ulong,unsigned __int64 *)
0x18000c728  mov     edi, eax
0x18000c72a  test    eax, eax
0x18000c72c  js      loc_18000C87F
0x18000c732  xor     r12d, r12d
0x18000c735  mov     [rbp+490h+var_4A0], r12
0x18000c739  mov     [rsp+590h+var_540], r12d
0x18000c73e  mov     [rsp+590h+Type], 400h
0x18000c746  lea     rax, [rsp+590h+Type]
0x18000c74b  mov     [rsp+590h+lpcbData], rax; lpcbData
0x18000c750  mov     [rsp+590h+lpData], r15; lpData
0x18000c755  lea     r9, [rsp+590h+var_540]; lpType
0x18000c75a  xor     r8d, r8d; lpReserved
0x18000c75d  lea     rdx, aPackage; "Package"
0x18000c764  mov     rcx, [rbp+490h+var_4B8]; hKey
0x18000c768  call    cs:__imp_RegQueryValueExW
0x18000c76e  mov     edi, eax
0x18000c770  test    eax, eax
0x18000c772  jz      loc_18000D232
0x18000c778  cmp     eax, 2
0x18000c77b  jnz     loc_18000D239
0x18000c781  xor     esi, esi
0x18000c783  mov     r13, [rbp+490h+var_4C0]
0x18000c787  lea     rcx, [r13+0B0h]; this
0x18000c78e  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18000c793  xor     edx, edx; dwFlags
0x18000c795  mov     r8d, 18h; dwBytes
0x18000c79b  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x18000c7a2  call    cs:__imp_HeapAlloc
0x18000c7a8  mov     rdi, rax
0x18000c7ab  test    rax, rax
0x18000c7ae  jz      loc_18000D518
0x18000c7b4  mov     [rsp+590h+lpMem], rax
0x18000c7b9  mov     qword ptr [rax+8], 0
0x18000c7c1  mov     dword ptr [rax+10h], 1
0x18000c7c8  mov     rcx, rsi; psz
0x18000c7cb  call    cs:__imp_SysAllocString
0x18000c7d1  mov     [rdi], rax
0x18000c7d4  test    rax, rax
0x18000c7d7  jz      loc_18000D290
0x18000c7dd  mov     [r13+0B0h], rdi
0x18000c7e4  mov     [rsp+590h+Type], 0
0x18000c7ec  mov     [rsp+590h+var_540], 400h
0x18000c7f4  lea     rax, [rsp+590h+var_540]
0x18000c7f9  mov     [rsp+590h+lpcbData], rax; lpcbData
0x18000c7fe  mov     [rsp+590h+lpData], r15; lpData
0x18000c803  lea     r9, [rsp+590h+Type]; lpType
0x18000c808  xor     r8d, r8d; lpReserved
0x18000c80b  lea     rdx, aCapabilities; "Capabilities"
0x18000c812  mov     r13, [rbp+490h+var_4B8]
0x18000c816  mov     rcx, r13; hKey
0x18000c819  call    cs:__imp_RegQueryValueExW
0x18000c81f  mov     edi, eax
0x18000c821  test    eax, eax
0x18000c823  jz      loc_18000D55C
0x18000c829  cmp     eax, 2
0x18000c82c  jnz     loc_18000D56E
0x18000c832  mov     rcx, [rbp+490h+var_4C0]
0x18000c836  add     rcx, 0B8h
0x18000c83d  call    ?clear@?$vector@V_bstr_t@@V?$allocator@V_bstr_t@@@std@@@std@@QEAAXXZ; std::vector<_bstr_t>::clear(void)
0x18000c842  jmp     short loc_18000C85D
0x18000c844  mov     rdi, [rbp+490h+var_4C0]
0x18000c848  lea     rcx, [rdi+0B8h]
0x18000c84f  call    ?clear@?$vector@V_bstr_t@@V?$allocator@V_bstr_t@@@std@@@std@@QEAAXXZ; std::vector<_bstr_t>::clear(void)
0x18000c854  test    r15, r15
0x18000c857  jnz     loc_18000D634
0x18000c85d  test    r12, r12
0x18000c860  jz      short loc_18000C874
0x18000c862  mov     r8, r12; lpMem
0x18000c865  xor     edx, edx; dwFlags
0x18000c867  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x18000c86e  call    cs:__imp_HeapFree
0x18000c874  xor     edi, edi
0x18000c876  mov     r13, [rbp+490h+var_4B0]
0x18000c87a  mov     r12, [rsp+590h+var_538]
0x18000c87f  lea     r15, WPP_GLOBAL_Control
0x18000c886  test    rbx, rbx
0x18000c889  jz      short loc_18000C89D
0x18000c88b  mov     r8, rbx; lpMem
0x18000c88e  xor     edx, edx; dwFlags
0x18000c890  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x18000c897  call    cs:__imp_HeapFree
0x18000c89d  test    edi, edi
0x18000c89f  js      loc_18000D6D3
0x18000c8a5  xor     esi, esi
0x18000c8a7  mov     [rsp+590h+var_518], rsi
0x18000c8ac  xor     r8d, r8d
0x18000c8af  xor     edx, edx
0x18000c8b1  call    ?_Buynode0@?$_List_alloc@$0A@U?$_List_base_types@PEAUTrigger@Triggers@@V?$allocator@PEAUTrigger@Triggers@@@std@@@std@@@std@@QEAAPEAU?$_List_node@PEAUTrigger@Triggers@@PEAX@2@PEAU32@0@Z; std::_List_alloc<0,std::_List_base_types<Triggers::Trigger *>>::_Buynode0(std::_List_node<Triggers::Trigger *,void *> *,std::_List_node<Triggers::Trigger *,void *> *)
0x18000c8b6  mov     [rsp+590h+lpMem], rax
  ... truncated ...
```
