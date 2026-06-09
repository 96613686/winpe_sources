# JobStore::GenerateTaskXmlFromRegistry(JobMoniker &,ushort const *,ulong *,wmi::AutoVectorPtr<ushort> &)

- ea: `0x1800104c0`
- end: `0x180011e37`
- name: `?GenerateTaskXmlFromRegistry@JobStore@@QEAAJAEAVJobMoniker@@PEBGPEAKAEAV?$AutoVectorPtr@G@wmi@@@Z`
- size: `6519`
- prototype: ``
- caller_count: `1`
- callee_count: `41`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x18000d8a0`

## callees

- `0x18000b8c4`
- `0x18000ba20`
- `0x18000bb10`
- `0x18000bc60`
- `0x18000cbe0`
- `0x18000cc40`
- `0x18000ce10`
- `0x18000ce30`
- `0x18000d160`
- `0x18000fda4`
- `0x18000ff40`
- `0x180010390`
- `0x1800103d4`
- `0x1800104c0`
- `0x180011e40`
- `0x180012d40`
- `0x180015920`
- `0x180015a60`
- `0x18002123c`
- `0x180026880`
- `0x180027910`
- `0x18002db40`
- `0x18002db74`
- `0x18003b1b0`
- `0x180040a70`
- `0x180040fd0`
- `0x1800423e0`
- `0x180045d1c`
- `0x180045df8`
- `0x1800529a0`
- `0x180054824`
- `0x180056954`
- `0x180059140`
- `0x18005a2bc`
- `0x18006a08c`
- `0x18006b398`
- `0x18007272c`
- `0x1800757c0`
- `0x1800829fa`
- `0x180082a40`
- `0x180088010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800108fb`
- `OLEAUT32!__imp_SysAllocString` at `0x1800108fb`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800110a5`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800110a5`
- `OLEAUT32!__imp_SysFreeString` at `0x1800110bf`
- `OLEAUT32!__imp_SysFreeString` at `0x18001113c`
- `OLEAUT32!__imp_SysFreeString` at `0x18001116b`
- `OLEAUT32!__imp_SysFreeString` at `0x180011179`
- `OLEAUT32!__imp_SysFreeString` at `0x180011253`
- `OLEAUT32!__imp_SysFreeString` at `0x180011327`
- `OLEAUT32!__imp_SysFreeString` at `0x180011379`
- `OLEAUT32!__imp_SysFreeString` at `0x180011d24`
- `OLEAUT32!__imp_SysFreeString` at `0x1800110bf`
- `OLEAUT32!__imp_SysFreeString` at `0x18001113c`
- `OLEAUT32!__imp_SysFreeString` at `0x18001116b`
- `OLEAUT32!__imp_SysFreeString` at `0x180011179`
- `OLEAUT32!__imp_SysFreeString` at `0x180011253`
- `OLEAUT32!__imp_SysFreeString` at `0x180011327`
- `OLEAUT32!__imp_SysFreeString` at `0x180011379`
- `OLEAUT32!__imp_SysFreeString` at `0x180011d24`
- `OLEAUT32!__imp_SysStringLen` at `0x18001118f`
- `OLEAUT32!__imp_SysStringLen` at `0x18001118f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011ac2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011b0c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011b64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011ac2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011b0c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011b64`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180010533`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180010547`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180010533`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180010547`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800106bb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180010761`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001088c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001094f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180010a51`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800114bb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001168a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800117a9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180011978`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800106bb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180010761`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001088c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001094f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180010a51`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800114bb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001168a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800117a9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180011978`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010d22`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010d22`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800105a3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800109aa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800109d9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010c72`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010d09`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001107b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800112b3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800112dc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001134f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800113ba`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011453`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011ddc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011e17`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800105a3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800109aa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800109d9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010c72`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010d09`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001107b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800112b3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800112dc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001134f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800113ba`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011453`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011ddc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011e17`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180010626`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800108cc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180010e3b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180010f39`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180010fc6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800111c1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180010626`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800108cc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180010e3b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180010f39`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180010fc6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800111c1`
- `api-ms-win-core-localization-l1-2-0!SetThreadPreferredUILanguages` at `0x180010eee`
- `api-ms-win-core-localization-l1-2-0!SetThreadPreferredUILanguages` at `0x180011dc4`
- `api-ms-win-core-localization-l1-2-0!SetThreadPreferredUILanguages` at `0x180011dff`
- `api-ms-win-core-localization-l1-2-0!SetThreadPreferredUILanguages` at `0x180010eee`
- `api-ms-win-core-localization-l1-2-0!SetThreadPreferredUILanguages` at `0x180011dc4`
- `api-ms-win-core-localization-l1-2-0!SetThreadPreferredUILanguages` at `0x180011dff`
- `api-ms-win-core-localization-l1-2-0!GetThreadPreferredUILanguages` at `0x180010e8c`
- `api-ms-win-core-localization-l1-2-0!GetThreadPreferredUILanguages` at `0x180010ecf`
- `api-ms-win-core-localization-l1-2-0!GetThreadPreferredUILanguages` at `0x180010e8c`
- `api-ms-win-core-localization-l1-2-0!GetThreadPreferredUILanguages` at `0x180010ecf`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
__int64 __fastcall JobStore::GenerateTaskXmlFromRegistry(
        JobStore *a1,
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
  signed int v22; // r14d
  JobBucket *v23; // rax
  void *v24; // rcx
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
  __int64 v57; // rdx
  void **v58; // r8
  void ***v59; // rax
  void ***k; // rbx
  void **v61; // rbx
  JobBucket *v62; // rcx
  void (__fastcall ***v64)(_QWORD, __int64); // rcx
  void **v65; // rcx
  unsigned int Path; // eax
  int v67; // edx
  int v68; // r8d
  __int64 v69; // rax
  unsigned __int64 v70; // rbx
  SIZE_T v71; // rax
  unsigned __int64 v72; // kr00_8
  BYTE *v73; // rax
  WCHAR *v74; // rsi
  unsigned __int64 m; // rdx
  LPVOID *v76; // r13
  __int64 v77; // rdi
  __int64 v78; // rbx
  StringStream *v79; // rcx
  __int64 v80; // rcx
  struct IErrorInfo *v81; // rdx
  int v82; // r14d
  wmi::RefBase *v83; // rdi
  wmi::RefBase *v84; // rbx
  wmi::RefBase *v85; // rax
  wmi::RefBase *v86; // r14
  OLECHAR *v87; // rbx
  __int64 v88; // r14
  OLECHAR *v89; // r15
  OLECHAR *v90; // r12
  unsigned __int64 v91; // r10
  __int64 n; // r11
  unsigned __int64 v93; // rcx
  OLECHAR *v94; // rdx
  unsigned __int64 v95; // r9
  OLECHAR *v96; // r8
  OLECHAR v97; // ax
  __int64 v98; // rax
  unsigned __int64 v99; // r14
  unsigned __int64 v100; // r12
  SIZE_T v101; // rax
  OLECHAR *v102; // r15
  OLECHAR *v103; // rcx
  OLECHAR v104; // ax
  wmi::RefBase *v105; // rcx
  PZZWSTR v106; // rbx
  _QWORD *v107; // rbx
  BSTR v108; // rcx
  PZZWSTR v109; // rbx
  WCHAR v110; // ax
  void *v111; // rax
  BYTE *v112; // rax
  bool IsErrorNotFound; // al
  unsigned int v114; // ecx
  __int64 v115; // r9
  bool v116; // sf
  unsigned __int64 v117; // rsi
  void *v118; // rax
  int v119; // eax
  void *v120; // rax
  LPBYTE v121; // rbx
  LSTATUS v122; // eax
  DWORD LastError; // eax
  DWORD v124; // ebx
  DWORD v125; // eax
  DWORD Type; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cbData[2]; // [rsp+48h] [rbp-B8h] BYREF
  DWORD v128[2]; // [rsp+50h] [rbp-B0h] BYREF
  wmi::RefBase *v129; // [rsp+58h] [rbp-A8h] BYREF
  DWORD lpcbData; // [rsp+68h] [rbp-98h] BYREF
  void *v131; // [rsp+70h] [rbp-90h] BYREF
  __int64 v132; // [rsp+78h] [rbp-88h]
  LPVOID v133; // [rsp+80h] [rbp-80h]
  HKEY hKey; // [rsp+90h] [rbp-70h] BYREF
  wmi::RefBase *v135; // [rsp+98h] [rbp-68h] BYREF
  char v136; // [rsp+A0h] [rbp-60h] BYREF
  int v137; // [rsp+A1h] [rbp-5Fh]
  __int16 v138; // [rsp+A5h] [rbp-5Bh]
  char v139; // [rsp+A7h] [rbp-59h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+A8h] [rbp-58h] BYREF
  char v141; // [rsp+B0h] [rbp-50h]
  int v142; // [rsp+B1h] [rbp-4Fh]
  __int16 v143; // [rsp+B5h] [rbp-4Bh]
  char v144; // [rsp+B7h] [rbp-49h]
  struct _FILETIME v145; // [rsp+B8h] [rbp-48h] BYREF
  LPVOID lpMem[2]; // [rsp+C0h] [rbp-40h] BYREF
  JobBucket *v147; // [rsp+D0h] [rbp-30h]
  HKEY v148; // [rsp+D8h] [rbp-28h]
  LPBYTE v149; // [rsp+E0h] [rbp-20h] BYREF
  JobMoniker *v150; // [rsp+E8h] [rbp-18h]
  _QWORD v151[2]; // [rsp+F0h] [rbp-10h] BYREF
  void *v152; // [rsp+100h] [rbp+0h]
  __int128 pExceptionObject; // [rsp+108h] [rbp+8h] BYREF
  const unsigned __int16 *v154; // [rsp+118h] [rbp+18h] BYREF
  __int64 v155; // [rsp+120h] [rbp+20h]
  JobBucket *v156; // [rsp+128h] [rbp+28h] BYREF
  int v157; // [rsp+130h] [rbp+30h]
  __int64 v158; // [rsp+134h] [rbp+34h]
  BYTE Data[16]; // [rsp+140h] [rbp+40h] BYREF
  __int128 v160; // [rsp+150h] [rbp+50h]

  v5 = (ULONG *)a4;
  v149 = a4;
  v6 = a3;
  v129 = a3;
  v150 = a2;
  v135 = a5;
  hKey = 0;
  v7 = JobStore::RegOpenTaskKey(a1, a2, &hKey, 0x20019u);
  if ( v7 < 0 )
    goto LABEL_280;
  v136 = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v141 = 0;
  GetSystemTimeAsFileTime(&v145);
  *(_OWORD *)lpMem = 0;
  v9 = (_QWORD *)std::_List_alloc<0,std::_List_base_types<Triggers::Trigger *>>::_Buynode0(v8, 0, 0);
  lpMem[0] = v9;
  v147 = 0;
  if ( lpMem[1] )
  {
    for ( i = (_QWORD *)*v9; i != v9; i = (_QWORD *)*i )
    {
      v28 = (void (__fastcall ***)(_QWORD, __int64))i[2];
      if ( v28 )
      {
        (**v28)(v28, 1);
        i[2] = 0;
        v9 = lpMem[0];
      }
    }
    v11 = (void **)*v9;
    *v9 = v9;
    *((LPVOID *)lpMem[0] + 1) = lpMem[0];
    lpMem[1] = 0;
    if ( v11 != lpMem[0] )
    {
      do
      {
        v12 = (void **)*v11;
        HeapFree(g_PrivateHeap, 0, v11);
        v11 = v12;
      }
      while ( v12 != lpMem[0] );
    }
  }
  v136 = 0;
  v137 = *(_DWORD *)((char *)&v129 + 1);
  v138 = *(_WORD *)((char *)&v129 + 5);
  v139 = HIBYTE(v129);
  SystemTimeAsFileTime = (struct _FILETIME)-1LL;
  v141 = 0;
  v142 = *(_DWORD *)((char *)&v129 + 1);
  v143 = *(_WORD *)((char *)&v129 + 5);
  v144 = HIBYTE(v129);
  v145 = 0;
  v13 = 0;
  v152 = 0;
  memset_0(Data, 0, 0x400u);
  v14 = (JobBucket *)HeapAlloc(g_PrivateHeap, 0, 0xD8u);
  if ( !v14 )
  {
    BYTE8(pExceptionObject) = 0;
    v154 = &qword_1800A8718;
    v155 = 0;
    v156 = 0;
    v157 = 14;
    v158 = -1;
    *(_QWORD *)&pExceptionObject = &wmi::GenericException::`vftable';
    throw (wmi::OutOfMemoryException *)&pExceptionObject;
  }
  v15 = JobBucket::JobBucket(v14);
  v16 = v15;
  if ( v15 )
    _InterlockedIncrement((volatile signed __int32 *)v15 + 2);
  v17 = v147;
  if ( v147 && _InterlockedExchangeAdd((volatile signed __int32 *)v147 + 2, 0xFFFFFFFF) == 1 )
    (**(void (__fastcall ***)(JobBucket *))v17)(v17);
  v147 = v16;
  if ( !v16 )
  {
    v22 = -2147024882;
LABEL_159:
    Triggers::Trigulator::~Trigulator((Triggers::Trigulator *)&v136);
    wmi::AutoRegKey::Close((wmi::AutoRegKey *)&hKey);
    return (unsigned int)v22;
  }
  v18 = hKey;
  v148 = hKey;
  cbData[0] = 1024;
  v131 = 0;
  Type = 0;
  v19 = RegQueryValueExW(hKey, L"Hash", 0, &Type, Data, cbData);
  v21 = (unsigned int)v19;
  v22 = -2147024882;
  if ( !v19 && cbData[0] == 32 && Type == 3 )
  {
    v23 = v147;
    *(_OWORD *)((char *)v147 + 28) = *(_OWORD *)Data;
    *(_OWORD *)((char *)v23 + 44) = v160;
    *((_DWORD *)v23 + 15) = 1;
  }
  else
  {
    *((_DWORD *)v147 + 15) = 0;
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
  RegistrationData = Triggers::Trigulator::ReadRegistrationData((Triggers::Trigulator *)&v136, v18, Data, 0x400u);
  if ( RegistrationData < 0 )
    goto LABEL_45;
  cbData[0] = 0;
  lpcbData = 1024;
  RegistrationData = RegQueryValueExW(v18, L"Triggers", 0, cbData, Data, &lpcbData);
  if ( RegistrationData == 234 )
  {
    v112 = (BYTE *)operator new(lpcbData);
    v13 = v112;
    v152 = v112;
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
    LOBYTE(v131) = 0;
    *(_DWORD *)((char *)&v131 + 1) = *(_DWORD *)((char *)&v129 + 1);
    *(_WORD *)((char *)&v131 + 5) = *(_WORD *)((char *)&v129 + 5);
    HIBYTE(v131) = HIBYTE(v129);
    v132 = -1;
    LOBYTE(v151[0]) = 0;
    *(_DWORD *)((char *)v151 + 1) = *(_DWORD *)((char *)&v129 + 1);
    *(_WORD *)((char *)v151 + 5) = *(_WORD *)((char *)&v129 + 5);
    HIBYTE(v151[0]) = HIBYTE(v129);
    v151[1] = 0;
    RegistrationData = Triggers::Trigulator::ParseTriggerBlobData(&v136, lpData, v27, v151, &v131, 15, 0);
    if ( RegistrationData < 0 )
      goto LABEL_45;
    v29 = 0;
    v151[0] = 0;
    v128[0] = 0;
    Type = 1024;
    v30 = RegQueryValueExW(v148, L"Package", 0, v128, lpData, &Type);
    RegistrationData = v30;
    if ( v30 )
    {
      if ( v30 == 2 )
      {
        v31 = 0;
        goto LABEL_34;
      }
    }
    else if ( v128[0] == 1 )
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
        wmi::AutoVectorPtr<unsigned char>::operator=(v151, v111);
        v29 = (BYTE *)v151[0];
        if ( !v151[0] )
        {
          LOWORD(RegistrationData) = 8;
          goto LABEL_198;
        }
      }
      RegistrationData = RegQueryValueExW(v148, L"Package", 0, v128, v29, &Type);
      if ( !RegistrationData && v128[0] == 1 )
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
LABEL_199:
        operator delete(v29);
        goto LABEL_44;
      }
LABEL_198:
      RegistrationData = (unsigned __int16)RegistrationData | 0x80070000;
      goto LABEL_199;
    }
LABEL_34:
    v32 = v147;
    _bstr_t::~_bstr_t((JobBucket *)((char *)v147 + 176));
    v33 = (BSTR *)HeapAlloc(g_PrivateHeap, 0, 0x18u);
    v34 = v33;
    if ( !v33 )
    {
      BYTE8(pExceptionObject) = 0;
      v154 = &qword_1800A8718;
      v155 = 0;
      v156 = 0;
      v157 = 14;
      v158 = -1;
      *(_QWORD *)&pExceptionObject = &wmi::GenericException::`vftable';
      throw (wmi::OutOfMemoryException *)&pExceptionObject;
    }
    v131 = v33;
    v33[1] = 0;
    *((_DWORD *)v33 + 4) = 1;
    v35 = SysAllocString(v31);
    *v34 = v35;
    if ( !v35 && v31 )
      _com_raise_error(-2147024882, v36);
    *((_QWORD *)v32 + 22) = v34;
    Type = 0;
    v128[0] = 1024;
    v37 = v148;
    v38 = RegQueryValueExW(v148, L"Capabilities", 0, &Type, lpData, v128);
    RegistrationData = v38;
    if ( v38 )
    {
      if ( v38 == 2 )
      {
        std::vector<_bstr_t>::clear((char *)v147 + 184);
LABEL_40:
        if ( v29 )
          HeapFree(g_PrivateHeap, 0, v29);
        RegistrationData = 0;
        goto LABEL_43;
      }
    }
    else if ( Type == 7 )
    {
      v117 = v128[0] >> 1;
      goto LABEL_39;
    }
    lpData = 0;
    v117 = 0;
    if ( v38 == 234 )
    {
      if ( v128[0] )
      {
        v118 = operator new(v128[0]);
        wmi::AutoVectorPtr<unsigned char>::operator=(v151, v118);
        v29 = (BYTE *)v151[0];
        if ( !v151[0] )
        {
          LOWORD(RegistrationData) = 8;
          goto LABEL_201;
        }
      }
      RegistrationData = RegQueryValueExW(v37, L"Capabilities", 0, &Type, v29, v128);
      if ( !RegistrationData && Type == 7 )
      {
        lpData = v29;
        v117 = v128[0] >> 1;
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
LABEL_202:
        operator delete(v29);
LABEL_43:
        v5 = (ULONG *)v149;
LABEL_44:
        v6 = v129;
        goto LABEL_45;
      }
LABEL_201:
      RegistrationData = (unsigned __int16)RegistrationData | 0x80070000;
      goto LABEL_202;
    }
LABEL_39:
    v39 = v147;
    std::vector<_bstr_t>::clear((char *)v147 + 184);
    if ( lpData && (_DWORD)v117 )
    {
      v131 = 0;
      while ( v117 && *(_WORD *)lpData )
      {
        JobBucket::AddCapability(v39, (const unsigned __int16 *)lpData);
        v119 = StringCchLengthW((const unsigned __int16 *)lpData, v117, (unsigned __int64 *)&v131);
        if ( v119 < 0 )
        {
          BYTE8(pExceptionObject) = 0;
          *(_QWORD *)&pExceptionObject = &wmi::GenericException::`vftable';
          v154 = &qword_1800A8718;
          v155 = 0;
          v156 = 0;
          v157 = v119;
          v158 = -1;
          throw (wmi::GenericException *)&pExceptionObject;
        }
        v24 = v131;
        lpData += 2 * (_QWORD)v131 + 2;
        v117 += -1LL - (_QWORD)v131;
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
    goto LABEL_159;
  }
  v132 = 0;
  v131 = (void *)std::_List_alloc<0,std::_List_base_types<Triggers::Trigger *>>::_Buynode0(v24, 0, 0);
  v133 = 0;
  memset_0(Data, 0, 0x200u);
  v128[0] = 512;
  Type = 3;
  v40 = v148;
  v41 = RegQueryValueExW(v148, L"Actions", 0, &Type, Data, v128);
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
    v149 = 0;
    v120 = operator new(v128[0]);
    wmi::AutoVectorPtr<unsigned char>::operator=(&v149, v120);
    v121 = v149;
    if ( v149 )
    {
      v122 = RegQueryValueExW(v40, L"Actions", 0, &Type, v149, v128);
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
        v22 = Actions::ActionCollection::ReadData((Actions::ActionCollection *)&v131, v121, v128[0], 0);
        operator delete(v121);
        v45 = WPP_GLOBAL_Control;
      }
      goto LABEL_51;
    }
    operator delete(0);
LABEL_253:
    Actions::ActionCollection::~ActionCollection((Actions::ActionCollection *)&v131);
    goto LABEL_159;
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
    goto LABEL_253;
  }
  v22 = Actions::ActionCollection::ReadData((Actions::ActionCollection *)&v131, Data, v128[0], 0);
  v45 = WPP_GLOBAL_Control;
LABEL_51:
  if ( v22 < 0 )
    goto LABEL_253;
  v46 = v147;
  if ( !v147 )
  {
    Actions::ActionCollection::~ActionCollection((Actions::ActionCollection *)&v131);
    Triggers::Trigulator::~Trigulator((Triggers::Trigulator *)&v136);
    wmi::AutoRegKey::Close((wmi::AutoRegKey *)&hKey);
    return 2147549183LL;
  }
  v154 = 0;
  v156 = 0;
  if ( v45 != &WPP_GLOBAL_Control && (*((_BYTE *)v45 + 28) & 0x40) != 0 )
  {
    v47 = v150;
    if ( *((_BYTE *)v45 + 25) >= 4u )
      WPP_SF_qqq(v45[2], v42, v43, &pExceptionObject, v150, v147);
  }
  else
  {
    v47 = v150;
  }
  if ( v46 )
    _InterlockedIncrement((volatile signed __int32 *)v46 + 2);
  wmi::AutoRef<JobBucket>::Release(&v156);
  v156 = v46;
  v48 = *((_QWORD *)v47 + 2);
  if ( v48 )
    _InterlockedIncrement((volatile signed __int32 *)(v48 + 16));
  _bstr_t::~_bstr_t((_bstr_t *)&v154);
  v49 = *((_QWORD *)v47 + 2);
  v154 = (const unsigned __int16 *)v49;
  v155 = *((_QWORD *)v47 + 3);
  pExceptionObject = *(_OWORD *)v47;
  if ( v49 )
    _InterlockedIncrement((volatile signed __int32 *)(v49 + 16));
  _bstr_t::~_bstr_t((JobMoniker *)((char *)v47 + 16));
  *((_QWORD *)v47 + 2) = v154;
  *((_QWORD *)v47 + 3) = v155;
  *(_OWORD *)v47 = pExceptionObject;
  v50 = v156;
  if ( v156 )
    _InterlockedIncrement((volatile signed __int32 *)v156 + 2);
  wmi::AutoRef<JobBucket>::Release((char *)v47 + 32);
  *((_QWORD *)v47 + 4) = v50;
  v51 = v156;
  if ( v156 && _InterlockedExchangeAdd((volatile signed __int32 *)v156 + 2, 0xFFFFFFFF) == 1 )
    (**(void (__fastcall ***)(JobBucket *, __int64))v51)(v51, 1);
  v156 = 0;
  _bstr_t::~_bstr_t((_bstr_t *)&v154);
  v22 = JobStore::GenerateTaskXmlFromCollections(v52, v47, &v136, &v131, v135);
  if ( v22 < 0 )
    goto LABEL_253;
  if ( !v5 || !*v5 )
  {
LABEL_70:
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      Path = (unsigned int)JobMoniker::GetPath(v47);
      WPP_SF_S_guid_(*((_QWORD *)WPP_GLOBAL_Control + 2), v67, v68, Path, (__int64)v47);
    }
    if ( v132 )
    {
      v53 = v131;
      for ( j = *(_QWORD **)v131; j != v53; j = (_QWORD *)*j )
      {
        v64 = (void (__fastcall ***)(_QWORD, __int64))j[2];
        if ( v64 )
        {
          (**v64)(v64, 1);
          j[2] = 0;
        }
      }
      v55 = (_QWORD *)*v53;
      *v53 = v53;
      v53[1] = v53;
      v132 = 0;
      if ( v55 != v53 )
      {
        do
        {
          v107 = (_QWORD *)*v55;
          HeapFree(g_PrivateHeap, 0, v55);
          v55 = v107;
        }
        while ( v107 != v53 );
      }
    }
    v56 = (BSTR *)v133;
    if ( v133 )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v133 + 4, 0xFFFFFFFF) == 1 )
      {
        if ( *v56 )
        {
          SysFreeString(*v56);
          *v56 = 0;
        }
        v108 = v56[1];
        if ( v108 )
        {
          operator delete(v108);
          v56[1] = 0;
        }
        HeapFree(g_PrivateHeap, 0, v56);
      }
      v133 = 0;
    }
    std::list<Task *>::clear(&v131);
    operator delete(v131);
    if ( lpMem[1] )
    {
      v59 = (void ***)lpMem[0];
      for ( k = *(void ****)lpMem[0]; k != v59; k = (void ***)*k )
      {
        v65 = k[2];
        if ( v65 )
        {
          (*(void (__fastcall **)(void **, __int64))*v65)(v65, 1);
          k[2] = 0;
          v59 = (void ***)lpMem[0];
        }
      }
      v58 = *v59;
      *v59 = (void **)v59;
      *((LPVOID *)lpMem[0] + 1) = lpMem[0];
      lpMem[1] = 0;
      if ( v58 != lpMem[0] )
      {
        do
        {
          v61 = (void **)*v58;
          HeapFree(g_PrivateHeap, 0, v58);
          v58 = v61;
        }
        while ( v61 != lpMem[0] );
      }
    }
    v136 = 0;
    v137 = *(_DWORD *)((char *)&v129 + 1);
    v138 = *(_WORD *)((char *)&v129 + 5);
    v139 = HIBYTE(v129);
    SystemTimeAsFileTime = (struct _FILETIME)-1LL;
    v141 = 0;
    v142 = *(_DWORD *)((char *)&v129 + 1);
    v143 = *(_WORD *)((char *)&v129 + 5);
    v144 = HIBYTE(v129);
    v145 = 0;
    v62 = v147;
    if ( v147 && _InterlockedExchangeAdd((volatile signed __int32 *)v147 + 2, 0xFFFFFFFF) == 1 )
      (**(void (__fastcall ***)(JobBucket *, __int64, void **))v62)(v62, 1, v58);
    v147 = 0;
    std::list<Triggers::Trigger *>::clear(lpMem, v57, v58);
    if ( lpMem[0] )
      HeapFree(g_PrivateHeap, 0, lpMem[0]);
LABEL_88:
    if ( v148 )
      RegCloseKey(v148);
    return (unsigned int)v22;
  }
  v69 = -1;
  do
    ++v69;
  while ( *((_WORD *)v6 + v69) );
  v70 = v69 + 1;
  v72 = v69 + 2;
  v71 = 2 * (v69 + 2);
  if ( !is_mul_ok(v72, 2u) )
    v71 = -1;
  v73 = (BYTE *)HeapAlloc(g_PrivateHeap, 0, v71);
  v74 = (WCHAR *)v73;
  if ( !v73 )
  {
    BYTE8(pExceptionObject) = 0;
    v154 = &qword_1800A8718;
    v155 = 0;
    v156 = 0;
    v157 = 14;
    v158 = -1;
    *(_QWORD *)&pExceptionObject = &wmi::GenericException::`vftable';
    throw (wmi::OutOfMemoryException *)&pExceptionObject;
  }
  v149 = v73;
  for ( m = 0; m < v70; ++m )
  {
    v110 = 0;
    if ( *((_WORD *)v6 + m) != 92 )
      v110 = *((_WORD *)v6 + m);
    v74[m] = v110;
  }
  v74[v70] = 0;
  *(_QWORD *)v128 = 0;
  Type = 0;
  cbData[0] = 0;
  if ( !GetThreadPreferredUILanguages(0x48u, &Type, 0, cbData) )
  {
    LastError = GetLastError();
    BYTE8(pExceptionObject) = 0;
    *(_QWORD *)&pExceptionObject = &wmi::GenericException::`vftable';
    v154 = &qword_1800A8718;
    v155 = 0;
    v156 = 0;
    v157 = LastError;
    v158 = -1;
    throw (wmi::GenericException *)&pExceptionObject;
  }
  *(_QWORD *)v128 = operator new(saturated_mul(cbData[0], 2u));
  if ( !GetThreadPreferredUILanguages(0x48u, &Type, *(PZZWSTR *)v128, cbData) )
  {
    v124 = GetLastError();
    wmi::AutoVectorPtr<unsigned short>::operator=(v128, 0);
    BYTE8(pExceptionObject) = 0;
    *(_QWORD *)&pExceptionObject = &wmi::GenericException::`vftable';
    v154 = &qword_1800A8718;
    v155 = 0;
    v156 = 0;
    v157 = v124;
    v158 = -1;
    throw (wmi::GenericException *)&pExceptionObject;
  }
  if ( !SetThreadPreferredUILanguages(8u, v74, v5) )
  {
    v125 = GetLastError();
    BYTE8(pExceptionObject) = 0;
    *(_QWORD *)&pExceptionObject = &wmi::GenericException::`vftable';
    v154 = &qword_1800A8718;
    v155 = 0;
    v156 = 0;
    v157 = v125;
    v158 = -1;
    throw (wmi::GenericException *)&pExceptionObject;
  }
  *(_QWORD *)cbData = 0;
  v76 = (LPVOID *)v135;
  v77 = *(_QWORD *)v135;
  if ( !*(_QWORD *)v135 )
  {
    ATL::CComPtrBase<IStream>::~CComPtrBase<IStream>(cbData);
    AutoThreadUIPreferredLanguages::~AutoThreadUIPreferredLanguages((AutoThreadUIPreferredLanguages *)v128);
    operator delete(v74);
    Actions::ActionCollection::~ActionCollection((Actions::ActionCollection *)&v131);
    Triggers::Trigulator::~Trigulator((Triggers::Trigulator *)&v136);
    wmi::AutoRegKey::Close((wmi::AutoRegKey *)&hKey);
    return 2147942487LL;
  }
  v78 = -1;
  do
    ++v78;
  while ( *(_WORD *)(v77 + 2 * v78) );
  v79 = (StringStream *)HeapAlloc(g_PrivateHeap, 0, 0x28u);
  if ( !v79 )
  {
    BYTE8(pExceptionObject) = 0;
    v154 = &qword_1800A8718;
    v155 = 0;
    v156 = 0;
    v157 = 14;
    v158 = -1;
    *(_QWORD *)&pExceptionObject = &wmi::GenericException::`vftable';
    throw (wmi::OutOfMemoryException *)&pExceptionObject;
  }
  StringStream::StringStream(v79);
  *(_QWORD *)v80 = &StringReader::`vftable';
  *(_QWORD *)(v80 + 16) = -1;
  *(_DWORD *)(v80 + 24) = v78;
  *(_QWORD *)(v80 + 32) = v77;
  v135 = 0;
  v82 = ((__int64 (__fastcall *)(__int64, GUID *, wmi::RefBase **))StringReader::`vftable')(
          v80,
          &GUID_0000000c_0000_0000_c000_000000000046,
          &v135);
  if ( v82 < 0 )
  {
    ATL::CComPtrBase<IStream>::~CComPtrBase<IStream>(cbData);
    v83 = 0;
    *(_QWORD *)cbData = 0;
    v84 = 0;
  }
  else
  {
    v83 = v135;
    *(_QWORD *)cbData = v135;
    v84 = v135;
  }
  if ( (int)(v82 + 0x80000000) >= 0 && v82 != -2147467262 )
    _com_raise_error(v82, v81);
  if ( !v84 )
  {
    BYTE8(pExceptionObject) = 0;
    v154 = &qword_1800A8718;
    v155 = 0;
    v156 = 0;
    v157 = 14;
    v158 = -1;
    *(_QWORD *)&pExceptionObject = &wmi::GenericException::`vftable';
    throw (wmi::OutOfMemoryException *)&pExceptionObject;
  }
  v85 = (wmi::RefBase *)HeapAlloc(g_PrivateHeap, 0, 0x460u);
  v86 = v85;
  v135 = v85;
  if ( !v85 )
  {
    BYTE8(pExceptionObject) = 0;
    v154 = &qword_1800A8718;
    v155 = 0;
    v156 = 0;
    v157 = 14;
    v158 = -1;
    *(_QWORD *)&pExceptionObject = &wmi::GenericException::`vftable';
    throw (wmi::OutOfMemoryException *)&pExceptionObject;
  }
  *(_QWORD *)v85 = &wmi::RefBase::`vftable';
  *((_DWORD *)v85 + 2) = 0;
  *(_QWORD *)v85 = &TaskXmlReader::`vftable';
  *((_QWORD *)v85 + 2) = 0;
  *((_QWORD *)v85 + 3) = 0;
  *((_QWORD *)v85 + 4) = v84;
  (*(void (__fastcall **)(wmi::RefBase *))(*(_QWORD *)v84 + 8LL))(v84);
  *((_BYTE *)v86 + 40) = 1;
  *((_QWORD *)v86 + 6) = 0;
  *((_QWORD *)v86 + 7) = 0;
  *((_BYTE *)v86 + 1106) &= 0xFCu;
  *((_DWORD *)v86 + 16) = 0;
  *((_QWORD *)v86 + 9) = 0;
  *((_WORD *)v86 + 40) = 0;
  *((_BYTE *)v86 + 1112) = 0;
  *((_DWORD *)v86 + 279) = 65542;
  v129 = v86;
  _InterlockedIncrement((volatile signed __int32 *)v86 + 2);
  v7 = TaskXmlReader::ProcessXml(v86, 0);
  if ( v7 >= 0 )
  {
    if ( *v76 )
      HeapFree(g_PrivateHeap, 0, *v76);
    *v76 = 0;
    v87 = 0;
    v152 = 0;
    v88 = *((_QWORD *)v86 + 3);
    if ( !v88 )
      ATL::PrivateAtlThrow(0x80004005);
    v89 = SysAllocStringLen(0, *(_DWORD *)(v88 + 16));
    if ( v89 )
    {
      SysFreeString(0);
      v90 = v89;
      v91 = *(_QWORD *)(v88 + 16) + 1LL;
      for ( n = *(_QWORD *)(v88 + 24); n; n = *(_QWORD *)(n + 16) )
      {
        if ( !v91 )
          goto LABEL_134;
        if ( v91 > 0x7FFFFFFF || (v93 = *(_QWORD *)(n + 8), v93 > 0x7FFFFFFE) )
        {
          *v90 = 0;
LABEL_134:
          SysFreeString(v89);
          goto LABEL_137;
        }
        v94 = *(OLECHAR **)n;
        v95 = v91;
        v96 = v90;
        while ( v93 )
        {
          v97 = *v94;
          if ( !*v94 )
            break;
          ++v94;
          *v96++ = v97;
          --v93;
          if ( !--v95 )
          {
            *(v96 - 1) = 0;
            goto LABEL_134;
          }
        }
        *v96 = 0;
        v98 = *(_QWORD *)(n + 8);
        v90 += v98;
        v91 -= v98;
      }
      SysFreeString(0);
      SysFreeString(0);
      v87 = v89;
      v152 = v89;
    }
    else
    {
      SysFreeString(0);
    }
LABEL_137:
    v99 = SysStringLen(v87);
    v100 = v99 + 1;
    v101 = 2 * (v99 + 1);
    if ( !is_mul_ok(v99 + 1, 2u) )
      v101 = -1;
    v102 = (OLECHAR *)HeapAlloc(g_PrivateHeap, 0, v101);
    if ( !v102 )
    {
      BYTE8(pExceptionObject) = 0;
      v154 = &qword_1800A8718;
      v155 = 0;
      v156 = 0;
      v157 = 14;
      v158 = -1;
      *(_QWORD *)&pExceptionObject = &wmi::GenericException::`vftable';
      throw (wmi::OutOfMemoryException *)&pExceptionObject;
    }
    if ( *v76 )
      HeapFree(g_PrivateHeap, 0, *v76);
    *v76 = v102;
    if ( v100 > 0x7FFFFFFF )
    {
      v22 = -2147024809;
      *v102 = 0;
    }
    else if ( v99 > 0x7FFFFFFE )
    {
      v22 = -2147024809;
      *v102 = 0;
    }
    else
    {
      v103 = v87;
      while ( v99 )
      {
        v104 = *v103;
        if ( !*v103 )
          break;
        ++v103;
        *v102++ = v104;
        --v99;
        if ( !--v100 )
          goto LABEL_148;
      }
      v22 = 0;
      if ( !v100 )
      {
LABEL_148:
        --v102;
        v22 = -2147024774;
      }
      *v102 = 0;
      if ( v22 >= 0 )
      {
        SysFreeString(v87);
        v105 = v135;
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v135 + 2, 0xFFFFFFFF) == 1 )
          (**(void (__fastcall ***)(wmi::RefBase *, __int64))v105)(v105, 1);
        (*(void (__fastcall **)(wmi::RefBase *))(*(_QWORD *)v83 + 16LL))(v83);
        v106 = *(PZZWSTR *)v128;
        if ( *(_QWORD *)v128 )
        {
          cbData[0] = 0;
          SetThreadPreferredUILanguages(8u, *(PCZZWSTR *)v128, cbData);
          HeapFree(g_PrivateHeap, 0, v106);
        }
        HeapFree(g_PrivateHeap, 0, v74);
        v47 = v150;
        goto LABEL_70;
      }
    }
    SysFreeString(v87);
    wmi::RefBase::Release(v135);
    (*(void (__fastcall **)(wmi::RefBase *))(*(_QWORD *)v83 + 16LL))(v83);
    v109 = *(PZZWSTR *)v128;
    if ( *(_QWORD *)v128 )
    {
      cbData[0] = 0;
      SetThreadPreferredUILanguages(8u, *(PCZZWSTR *)v128, cbData);
      HeapFree(g_PrivateHeap, 0, v109);
    }
    HeapFree(g_PrivateHeap, 0, v74);
    Actions::ActionCollection::~ActionCollection((Actions::ActionCollection *)&v131);
    Triggers::Trigulator::~Trigulator((Triggers::Trigulator *)&v136);
    goto LABEL_88;
  }
  wmi::AutoRef<TaskXmlReader>::Release(&v129);
  ATL::CComPtrBase<IStream>::~CComPtrBase<IStream>(cbData);
  AutoThreadUIPreferredLanguages::~AutoThreadUIPreferredLanguages((AutoThreadUIPreferredLanguages *)v128);
  operator delete(v74);
  Actions::ActionCollection::~ActionCollection((Actions::ActionCollection *)&v131);
  Triggers::Trigulator::~Trigulator((Triggers::Trigulator *)&v136);
LABEL_280:
  wmi::AutoRegKey::Close((wmi::AutoRegKey *)&hKey);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800104c0  push    rbp
0x1800104c2  push    rbx
0x1800104c3  push    rsi
0x1800104c4  push    rdi
0x1800104c5  push    r12
0x1800104c7  push    r13
0x1800104c9  push    r14
0x1800104cb  push    r15
0x1800104cd  lea     rbp, [rsp-458h]
0x1800104d5  sub     rsp, 558h
0x1800104dc  mov     rax, cs:__security_cookie
0x1800104e3  xor     rax, rsp
0x1800104e6  mov     [rbp+490h+var_50], rax
0x1800104ed  mov     r13, r9
0x1800104f0  mov     [rbp+490h+var_4B0], r9
0x1800104f4  mov     r12, r8
0x1800104f7  mov     [rsp+590h+var_538], r8
0x1800104fc  mov     [rbp+490h+var_4A8], rdx
0x180010500  mov     rax, [rbp+490h+arg_20]
0x180010507  mov     [rbp+490h+var_4F8], rax
0x18001050b  xor     r15d, r15d
0x18001050e  mov     [rbp+490h+hKey], r15
0x180010512  mov     r9d, 20019h; unsigned int
0x180010518  lea     r8, [rbp+490h+hKey]; HKEY *
0x18001051c  call    ?RegOpenTaskKey@JobStore@@QEAAJAEAVJobMoniker@@PEAPEAUHKEY__@@K@Z; JobStore::RegOpenTaskKey(JobMoniker &,HKEY__ * *,ulong)
0x180010521  mov     ebx, eax
0x180010523  test    eax, eax
0x180010525  js      loc_180011D14
0x18001052b  mov     [rbp+490h+var_4F0], r15b
0x18001052f  lea     rcx, [rbp+490h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180010533  call    cs:__imp_GetSystemTimeAsFileTime
0x18001053a  nop     dword ptr [rax+rax+00h]
0x18001053f  mov     [rbp+490h+var_4E0], r15b
0x180010543  lea     rcx, [rbp+490h+var_4D8]; lpSystemTimeAsFileTime
0x180010547  call    cs:__imp_GetSystemTimeAsFileTime
0x18001054e  nop     dword ptr [rax+rax+00h]
0x180010553  xorps   xmm0, xmm0
0x180010556  movdqu  xmmword ptr [rbp+490h+lpMem], xmm0
0x18001055b  xor     r8d, r8d
0x18001055e  xor     edx, edx
0x180010560  call    ?_Buynode0@?$_List_alloc@$0A@U?$_List_base_types@PEAUTrigger@Triggers@@V?$allocator@PEAUTrigger@Triggers@@@std@@@std@@@std@@QEAAPEAU?$_List_node@PEAUTrigger@Triggers@@PEAX@2@PEAU32@0@Z; std::_List_alloc<0,std::_List_base_types<Triggers::Trigger *>>::_Buynode0(std::_List_node<Triggers::Trigger *,void *> *,std::_List_node<Triggers::Trigger *,void *> *)
0x180010565  mov     [rbp+490h+lpMem], rax
0x180010569  mov     [rbp+490h+var_4C0], r15
0x18001056d  cmp     [rbp+490h+lpMem+8], r15
0x180010571  jz      short loc_1800105B8
0x180010573  mov     rbx, [rax]
0x180010576  cmp     rbx, rax
0x180010579  jnz     loc_1800107A5
0x18001057f  mov     r8, [rax]; lpMem
0x180010582  mov     [rax], rax
0x180010585  mov     rax, [rbp+490h+lpMem]
0x180010589  mov     [rax+8], rax
0x18001058d  mov     [rbp+490h+lpMem+8], r15
0x180010591  cmp     r8, [rbp+490h+lpMem]
0x180010595  jz      short loc_1800105B8
0x180010597  mov     rbx, [r8]
0x18001059a  xor     edx, edx; dwFlags
0x18001059c  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x1800105a3  call    cs:__imp_HeapFree
0x1800105aa  nop     dword ptr [rax+rax+00h]
0x1800105af  mov     r8, rbx
0x1800105b2  cmp     rbx, [rbp+490h+lpMem]
0x1800105b6  jnz     short loc_180010597
0x1800105b8  mov     [rbp+490h+var_4F0], 0
0x1800105bc  mov     eax, dword ptr [rsp+590h+var_538+1]
0x1800105c0  mov     [rbp+490h+var_4EF], eax
0x1800105c3  movzx   eax, word ptr [rsp+590h+var_538+5]
0x1800105c8  mov     [rbp+490h+var_4EB], ax
0x1800105cc  movzx   eax, byte ptr [rsp+590h+var_538+7]
0x1800105d1  mov     [rbp+490h+var_4E9], al
0x1800105d4  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x1800105db  mov     qword ptr [rbp+490h+SystemTimeAsFileTime.dwLowDateTime], rsi
0x1800105df  mov     [rbp+490h+var_4E0], 0
0x1800105e3  mov     eax, dword ptr [rsp+590h+var_538+1]
0x1800105e7  mov     [rbp+490h+var_4DF], eax
0x1800105ea  movzx   eax, word ptr [rsp+590h+var_538+5]
0x1800105ef  mov     [rbp+490h+var_4DB], ax
0x1800105f3  movzx   eax, byte ptr [rsp+590h+var_538+7]
0x1800105f8  mov     [rbp+490h+var_4D9], al
0x1800105fb  mov     qword ptr [rbp+490h+var_4D8.dwLowDateTime], r15
0x1800105ff  mov     rbx, r15
0x180010602  mov     [rbp+490h+var_490], rbx
0x180010606  xor     edx, edx; Val
0x180010608  mov     r8d, 400h; Size
0x18001060e  lea     rcx, [rbp+490h+Data]; void *
0x180010612  call    memset_0
0x180010617  xor     edx, edx; dwFlags
0x180010619  mov     r8d, 0D8h; dwBytes
0x18001061f  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x180010626  call    cs:__imp_HeapAlloc
0x18001062d  nop     dword ptr [rax+rax+00h]
0x180010632  test    rax, rax
0x180010635  jz      loc_1800115CE
0x18001063b  mov     rcx, rax; this
0x18001063e  call    ??0JobBucket@@QEAA@XZ; JobBucket::JobBucket(void)
0x180010643  mov     rdi, rax
0x180010646  test    rax, rax
0x180010649  jz      short loc_18001064F
0x18001064b  lock inc dword ptr [rax+8]
0x18001064f  mov     rcx, [rbp+490h+var_4C0]
0x180010653  test    rcx, rcx
0x180010656  jz      short loc_18001066F
0x180010658  mov     edx, esi
0x18001065a  lock xadd [rcx+8], edx
0x18001065f  cmp     edx, 1
0x180010662  jnz     short loc_18001066F
0x180010664  mov     rax, [rcx]
0x180010667  mov     rax, [rax]
0x18001066a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001066f  mov     [rbp+490h+var_4C0], rdi
0x180010673  test    rdi, rdi
0x180010676  jz      loc_1800112F6
0x18001067c  mov     rsi, [rbp+490h+hKey]
0x180010680  mov     [rbp+490h+var_4B8], rsi
0x180010684  mov     [rsp+590h+cbData], 400h
0x18001068c  mov     [rsp+590h+var_520], r15
0x180010691  mov     [rsp+590h+Type], r15d
0x180010696  lea     rax, [rsp+590h+cbData]
0x18001069b  mov     [rsp+590h+lpcbData], rax; lpcbData
0x1800106a0  lea     rax, [rbp+490h+Data]
0x1800106a4  mov     [rsp+590h+lpData], rax; lpData
0x1800106a9  lea     r9, [rsp+590h+Type]; lpType
0x1800106ae  xor     r8d, r8d; lpReserved
0x1800106b1  lea     rdx, aHash; "Hash"
0x1800106b8  mov     rcx, rsi; hKey
0x1800106bb  call    cs:__imp_RegQueryValueExW
0x1800106c2  nop     dword ptr [rax+rax+00h]
0x1800106c7  mov     ecx, eax
0x1800106c9  mov     r14d, 8007000Eh
0x1800106cf  test    eax, eax
0x1800106d1  jnz     loc_1800114CE
0x1800106d7  cmp     [rsp+590h+cbData], 20h ; ' '
0x1800106dc  jnz     loc_1800114CE
0x1800106e2  cmp     [rsp+590h+Type], 3
0x1800106e7  jnz     loc_1800114CE
0x1800106ed  mov     rax, [rbp+490h+var_4C0]
0x1800106f1  movaps  xmm0, xmmword ptr [rbp+490h+Data]
0x1800106f5  movups  xmmword ptr [rax+1Ch], xmm0
0x1800106f9  movaps  xmm1, [rbp+490h+var_440]
0x1800106fd  movups  xmmword ptr [rax+2Ch], xmm1
0x180010701  mov     dword ptr [rax+3Ch], 1
0x180010708  xor     ecx, ecx; void *
0x18001070a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001070f  mov     r9d, 400h; unsigned int
0x180010715  lea     r8, [rbp+490h+Data]; unsigned __int8 *
0x180010719  mov     rdx, rsi; HKEY
0x18001071c  lea     rcx, [rbp+490h+var_4F0]; this
0x180010720  call    ?ReadRegistrationData@Trigulator@Triggers@@AEAAJPEAUHKEY__@@PEAEK@Z; Triggers::Trigulator::ReadRegistrationData(HKEY__ *,uchar *,ulong)
0x180010725  mov     edi, eax
0x180010727  test    eax, eax
0x180010729  js      loc_1800109C1
0x18001072f  mov     [rsp+590h+cbData], r15d
0x180010734  mov     [rsp+590h+var_528], 400h
0x18001073c  lea     rax, [rsp+590h+var_528]
0x180010741  mov     [rsp+590h+lpcbData], rax; lpcbData
0x180010746  lea     rax, [rbp+490h+Data]
0x18001074a  mov     [rsp+590h+lpData], rax; lpData
0x18001074f  lea     r9, [rsp+590h+cbData]; lpType
0x180010754  xor     r8d, r8d; lpReserved
0x180010757  lea     rdx, aTriggers; "Triggers"
0x18001075e  mov     rcx, rsi; hKey
0x180010761  call    cs:__imp_RegQueryValueExW
0x180010768  nop     dword ptr [rax+rax+00h]
0x18001076d  mov     edi, eax
0x18001076f  cmp     eax, 0EAh
0x180010774  jz      loc_18001147E
0x18001077a  lea     r15, [rbp+490h+Data]
0x18001077e  test    edi, edi
0x180010780  jnz     loc_180011618
0x180010786  cmp     [rsp+590h+cbData], 3
0x18001078b  jnz     short loc_18001079B
0x18001078d  mov     esi, [rsp+590h+var_528]
0x180010791  cmp     esi, 8
0x180010794  jz      short loc_1800107D4
0x180010796  cmp     esi, 28h ; '('
0x180010799  jnb     short loc_1800107D4
0x18001079b  mov     edi, 8000FFFFh
0x1800107a0  jmp     loc_1800109C1
0x1800107a5  mov     rcx, [rbx+10h]
0x1800107a9  test    rcx, rcx
0x1800107ac  jz      short loc_1800107C6
0x1800107ae  mov     rax, [rcx]
0x1800107b1  mov     edx, 1
0x1800107b6  mov     rax, [rax]
0x1800107b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800107be  mov     [rbx+10h], r15
0x1800107c2  mov     rax, [rbp+490h+lpMem]
0x1800107c6  mov     rbx, [rbx]
0x1800107c9  jmp     loc_180010576
0x1800107ce  js      loc_1800109C1
0x1800107d4  mov     byte ptr [rsp+590h+var_520], 0
0x1800107d9  mov     eax, dword ptr [rsp+590h+var_538+1]
0x1800107dd  mov     dword ptr [rsp+590h+var_520+1], eax
0x1800107e1  movzx   eax, word ptr [rsp+590h+var_538+5]
0x1800107e6  mov     word ptr [rsp+590h+var_520+5], ax
0x1800107eb  movzx   eax, byte ptr [rsp+590h+var_538+7]
0x1800107f0  mov     byte ptr [rsp+590h+var_520+7], al
0x1800107f4  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800107fb  mov     [rsp+590h+var_518], rcx
0x180010800  mov     byte ptr [rbp+490h+var_4A0], 0
0x180010804  mov     eax, dword ptr [rsp+590h+var_538+1]
0x180010808  mov     dword ptr [rbp+490h+var_4A0+1], eax
0x18001080b  movzx   eax, word ptr [rsp+590h+var_538+5]
0x180010810  mov     word ptr [rbp+490h+var_4A0+5], ax
0x180010814  movzx   eax, byte ptr [rsp+590h+var_538+7]
0x180010819  mov     byte ptr [rbp+490h+var_4A0+7], al
0x18001081c  xor     eax, eax
0x18001081e  mov     [rbp+490h+var_498], rax
0x180010822  mov     [rsp+590h+var_560], rax
0x180010827  mov     dword ptr [rsp+590h+lpcbData], 0Fh
0x18001082f  lea     rax, [rsp+590h+var_520]
0x180010834  mov     [rsp+590h+lpData], rax
0x180010839  lea     r9, [rbp+490h+var_4A0]
0x18001083d  mov     r8d, esi
0x180010840  mov     rdx, r15
0x180010843  lea     rcx, [rbp+490h+var_4F0]
0x180010847  call    ?ParseTriggerBlobData@Trigulator@Triggers@@AEAAJPEAEKVTSTime@@1KPEA_K@Z; Triggers::Trigulator::ParseTriggerBlobData(uchar *,ulong,TSTime,TSTime,ulong,unsigned __int64 *)
0x18001084c  mov     edi, eax
0x18001084e  test    eax, eax
0x180010850  js      loc_1800109C1
0x180010856  xor     r12d, r12d
0x180010859  mov     [rbp+490h+var_4A0], r12
0x18001085d  mov     [rsp+590h+var_540], r12d
0x180010862  mov     [rsp+590h+Type], 400h
0x18001086a  lea     rax, [rsp+590h+Type]
0x18001086f  mov     [rsp+590h+lpcbData], rax; lpcbData
0x180010874  mov     [rsp+590h+lpData], r15; lpData
0x180010879  lea     r9, [rsp+590h+var_540]; lpType
0x18001087e  xor     r8d, r8d; lpReserved
0x180010881  lea     rdx, aPackage; "Package"
0x180010888  mov     rcx, [rbp+490h+var_4B8]; hKey
0x18001088c  call    cs:__imp_RegQueryValueExW
0x180010893  nop     dword ptr [rax+rax+00h]
0x180010898  mov     edi, eax
0x18001089a  test    eax, eax
0x18001089c  jz      loc_180011400
0x1800108a2  cmp     eax, 2
0x1800108a5  jnz     loc_180011407
0x1800108ab  xor     esi, esi
0x1800108ad  mov     r13, [rbp+490h+var_4C0]
0x1800108b1  lea     rcx, [r13+0B0h]; this
0x1800108b8  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x1800108bd  xor     edx, edx; dwFlags
0x1800108bf  mov     r8d, 18h; dwBytes
0x1800108c5  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x1800108cc  call    cs:__imp_HeapAlloc
0x1800108d3  nop     dword ptr [rax+rax+00h]
0x1800108d8  mov     rdi, rax
0x1800108db  test    rax, rax
0x1800108de  jz      loc_1800116F8
0x1800108e4  mov     [rsp+590h+var_520], rax
0x1800108e9  mov     qword ptr [rax+8], 0
0x1800108f1  mov     dword ptr [rax+10h], 1
0x1800108f8  mov     rcx, rsi; psz
0x1800108fb  call    cs:__imp_SysAllocString
0x180010902  nop     dword ptr [rax+rax+00h]
0x180010907  mov     [rdi], rax
0x18001090a  test    rax, rax
0x18001090d  jz      loc_180011464
0x180010913  mov     [r13+0B0h], rdi
0x18001091a  mov     [rsp+590h+Type], 0
0x180010922  mov     [rsp+590h+var_540], 400h
0x18001092a  lea     rax, [rsp+590h+var_540]
0x18001092f  mov     [rsp+590h+lpcbData], rax; lpcbData
0x180010934  mov     [rsp+590h+lpData], r15; lpData
0x180010939  lea     r9, [rsp+590h+Type]; lpType
0x18001093e  xor     r8d, r8d; lpReserved
0x180010941  lea     rdx, aCapabilities; "Capabilities"
0x180010948  mov     r13, [rbp+490h+var_4B8]
0x18001094c  mov     rcx, r13; hKey
0x18001094f  call    cs:__imp_RegQueryValueExW
0x180010956  nop     dword ptr [rax+rax+00h]
0x18001095b  mov     edi, eax
0x18001095d  test    eax, eax
0x18001095f  jz      loc_18001173C
0x180010965  cmp     eax, 2
0x180010968  jnz     loc_18001174E
0x18001096e  mov     rcx, [rbp+490h+var_4C0]
0x180010972  add     rcx, 0B8h
0x180010979  call    ?clear@?$vector@V_bstr_t@@V?$allocator@V_bstr_t@@@std@@@std@@QEAAXXZ; std::vector<_bstr_t>::clear(void)
0x18001097e  jmp     short loc_180010999
0x180010980  mov     rdi, [rbp+490h+var_4C0]
0x180010984  lea     rcx, [rdi+0B8h]
0x18001098b  call    ?clear@?$vector@V_bstr_t@@V?$allocator@V_bstr_t@@@std@@@std@@QEAAXXZ; std::vector<_bstr_t>::clear(void)
0x180010990  test    r15, r15
0x180010993  jnz     loc_18001181A
0x180010999  test    r12, r12
0x18001099c  jz      short loc_1800109B6
0x18001099e  mov     r8, r12; lpMem
0x1800109a1  xor     edx, edx; dwFlags
0x1800109a3  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x1800109aa  call    cs:__imp_HeapFree
0x1800109b1  nop     dword ptr [rax+rax+00h]
0x1800109b6  xor     edi, edi
0x1800109b8  mov     r13, [rbp+490h+var_4B0]
0x1800109bc  mov     r12, [rsp+590h+var_538]
0x1800109c1  lea     r15, WPP_GLOBAL_Control
0x1800109c8  test    rbx, rbx
0x1800109cb  jz      short loc_1800109E5
0x1800109cd  mov     r8, rbx; lpMem
  ... truncated ...
```
