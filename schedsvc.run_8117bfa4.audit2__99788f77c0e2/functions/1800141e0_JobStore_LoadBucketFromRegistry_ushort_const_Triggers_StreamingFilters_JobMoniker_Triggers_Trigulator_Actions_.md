# JobStore::LoadBucketFromRegistry(ushort const *,Triggers::StreamingFilters,JobMoniker &,Triggers::Trigulator *,Actions::ActionCollection *)

- ea: `0x1800141e0`
- end: `0x180014b1b`
- name: `?LoadBucketFromRegistry@JobStore@@QEAAJPEBGW4StreamingFilters@Triggers@@AEAVJobMoniker@@PEAVTrigulator@3@PEAVActionCollection@Actions@@@Z`
- size: `2363`
- prototype: ``
- caller_count: `10`
- callee_count: `32`
- tags: `file_ops, registry_config, service_task`

## callers

- `0x18001eae0`
- `0x18003a6e8`
- `0x180047ee0`
- `0x18004fc18`
- `0x180079560`
- `0x180079bfc`
- `0x18007a3b8`
- `0x18007a9dc`
- `0x18007ae0c`
- `0x18007bf60`

## callees

- `0x18000ba20`
- `0x18000bb10`
- `0x18000cbe0`
- `0x18000cc40`
- `0x18000d160`
- `0x18000fda4`
- `0x18000ff40`
- `0x180010390`
- `0x180011e40`
- `0x180012d40`
- `0x1800138d8`
- `0x180013a90`
- `0x1800141e0`
- `0x180015030`
- `0x18001d130`
- `0x180027910`
- `0x18002b210`
- `0x1800375e0`
- `0x180043478`
- `0x1800441c0`
- `0x180045d1c`
- `0x180047c88`
- `0x18004d278`
- `0x1800529a0`
- `0x180056714`
- `0x180059140`
- `0x180069f84`
- `0x18006a08c`
- `0x180071b54`
- `0x1800829fa`
- `0x180082a40`
- `0x180088010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800142d4`
- `OLEAUT32!__imp_SysAllocString` at `0x1800142d4`
- `OLEAUT32!__imp_SysFreeString` at `0x1800142c5`
- `OLEAUT32!__imp_SysFreeString` at `0x1800143f0`
- `OLEAUT32!__imp_SysFreeString` at `0x1800142c5`
- `OLEAUT32!__imp_SysFreeString` at `0x1800143f0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180014331`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180014331`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180014374`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180014817`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180014912`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180014374`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180014817`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180014912`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014407`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014a9c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014ab1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014407`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014a9c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014ab1`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall JobStore::LoadBucketFromRegistry(
        HKEY *a1,
        const unsigned __int16 *a2,
        unsigned int a3,
        __int64 a4,
        __int64 a5,
        __int64 *a6)
{
  BSTR v8; // rbx
  HKEY v9; // rsi
  HKEY v10; // r13
  int TreeInfo; // edi
  DWORD v12; // esi
  char v13; // r8
  __int64 v14; // rax
  LSTATUS v15; // eax
  LSTATUS v16; // eax
  int v17; // r8d
  JobBucket *v18; // rax
  JobBucket *v19; // rax
  JobBucket *v20; // rbx
  JobBucket *v21; // rcx
  JobBucket *v22; // rbx
  JobBucket *v23; // rcx
  JobBucket *v24; // rcx
  unsigned int v25; // ebx
  __int64 v26; // rdx
  __int64 v27; // r8
  JobBucket *v28; // rcx
  __int64 v29; // rcx
  DWORD v30; // r15d
  __int64 v31; // rdx
  __int64 v32; // r8
  volatile signed __int32 *v33; // rbx
  JobBucket *v34; // rbx
  __int64 *v35; // r12
  void *v36; // rax
  HKEY v37; // rbx
  bool v38; // sf
  __int64 v39; // rcx
  __int64 v40; // rcx
  JobBucket *v41; // rcx
  DWORD lpcbData; // [rsp+30h] [rbp-D0h] BYREF
  DWORD cbData; // [rsp+34h] [rbp-CCh] BYREF
  BYTE Data[8]; // [rsp+38h] [rbp-C8h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  DWORD Type; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v48; // [rsp+4Ch] [rbp-B4h]
  HKEY v49; // [rsp+50h] [rbp-B0h] BYREF
  HKEY v50; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v51; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v52; // [rsp+68h] [rbp-98h]
  char v53[8]; // [rsp+70h] [rbp-90h] BYREF
  __int64 *v54; // [rsp+78h] [rbp-88h]
  __int64 v55; // [rsp+80h] [rbp-80h]
  __int64 v56; // [rsp+88h] [rbp-78h]
  void *v57; // [rsp+90h] [rbp-70h]
  _OWORD v58[2]; // [rsp+98h] [rbp-68h] BYREF
  JobBucket *v59; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v60; // [rsp+C0h] [rbp-40h]
  volatile signed __int32 *v61; // [rsp+C8h] [rbp-38h] BYREF
  _BYTE v62[32]; // [rsp+D0h] [rbp-30h] BYREF
  char v63[16]; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v64; // [rsp+100h] [rbp+0h]
  GUID v65; // [rsp+108h] [rbp+8h] BYREF
  __int128 v66; // [rsp+118h] [rbp+18h] BYREF
  JobBucket *v67; // [rsp+128h] [rbp+28h] BYREF
  __int64 v68; // [rsp+130h] [rbp+30h]
  volatile signed __int32 *v69; // [rsp+138h] [rbp+38h]
  GUID iid; // [rsp+140h] [rbp+40h] BYREF
  __int128 v71; // [rsp+150h] [rbp+50h] BYREF
  JobBucket *v72; // [rsp+160h] [rbp+60h] BYREF
  struct _GUID v73; // [rsp+168h] [rbp+68h] BYREF
  BYTE v74[512]; // [rsp+180h] [rbp+80h] BYREF

  v55 = a4;
  v48 = a3;
  v56 = a5;
  v54 = a6;
  v73 = 0;
  JobMoniker::JobMoniker(&iid, 0, 0);
  v8 = 0;
  v9 = 0;
  v49 = 0;
  v10 = 0;
  v50 = 0;
  Triggers::Trigulator::Trigulator((Triggers::Trigulator *)v58);
  Actions::ActionCollection::ActionCollection((Actions::ActionCollection *)&v51);
  TreeInfo = JobStore::RegGetTreeInfo((JobStore *)a1, a2, &v73, 0);
  if ( TreeInfo < 0 )
    goto LABEL_111;
  Type = 0;
  cbData = 0;
  *(_DWORD *)Data = 0;
  hKey = 0;
  v12 = 0;
  lpcbData = 0;
  if ( a1[4] )
  {
    if ( a2 )
    {
      SysFreeString(0);
      v8 = SysAllocString(a2);
      v57 = v8;
      if ( !v8 )
        ATL::PrivateAtlThrow(0x8007000E);
    }
    LODWORD(v14) = 0;
    if ( *v8 )
    {
      do
      {
        if ( v8[(unsigned int)v14] == 92 )
          v8[(unsigned int)v14] = 47;
        v14 = (unsigned int)(v14 + 1);
      }
      while ( v8[v14] );
    }
    v15 = RegOpenKeyExW(a1[4], v8, 0, 0xF003Fu, &hKey);
    v13 = v15;
    if ( !v15 )
    {
      cbData = 4;
      v16 = RegQueryValueExW(hKey, L"StateFlags", 0, &Type, Data, &cbData);
      v13 = v16;
      if ( !v16 && Type == 4 && cbData == 4 )
      {
        if ( (*(_DWORD *)Data | 3) == 3 )
          v12 = *(_DWORD *)Data;
        lpcbData = v12;
      }
    }
  }
  else
  {
    v13 = 50;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_SSD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      88,
      (unsigned int)WPP_575a7bbfdfbc316314e49eeff74208de_Traceguids,
      (_DWORD)a2,
      (__int64)a2,
      v13);
  }
  SysFreeString(v8);
  if ( hKey )
    RegCloseKey(hKey);
  *(_QWORD *)&v66 = 0;
  v67 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_qS_guid_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, v17, (unsigned int)&v65, (__int64)a2, (__int64)&v73);
  }
  v18 = (JobBucket *)operator new(0xD8u);
  v57 = v18;
  if ( v18 )
  {
    v19 = JobBucket::JobBucket(v18);
    v20 = v19;
    if ( v19 )
      _InterlockedIncrement((volatile signed __int32 *)v19 + 2);
  }
  else
  {
    v20 = 0;
  }
  v21 = v67;
  if ( v67 && _InterlockedExchangeAdd((volatile signed __int32 *)v67 + 2, 0xFFFFFFFF) == 1 )
    (**(void (__fastcall ***)(JobBucket *, __int64))v21)(v21, 1);
  v67 = v20;
  JobMoniker::_SetPath((JobMoniker *)&v65, a2);
  v65 = v73;
  *((_DWORD *)v67 + 15) = 0;
  if ( (_QWORD)v66 )
    _InterlockedIncrement((volatile signed __int32 *)(v66 + 16));
  _bstr_t::~_bstr_t((_bstr_t *)&v71);
  v71 = v66;
  iid = v65;
  v22 = v67;
  if ( v67 )
    _InterlockedIncrement((volatile signed __int32 *)v67 + 2);
  v23 = v72;
  if ( v72 && _InterlockedExchangeAdd((volatile signed __int32 *)v72 + 2, 0xFFFFFFFF) == 1 )
    (**(void (__fastcall ***)(JobBucket *, __int64))v23)(v23, 1);
  v72 = v22;
  v24 = v67;
  if ( v67 && _InterlockedExchangeAdd((volatile signed __int32 *)v67 + 2, 0xFFFFFFFF) == 1 )
    (**(void (__fastcall ***)(JobBucket *, __int64))v24)(v24, 1);
  v67 = 0;
  _bstr_t::~_bstr_t((_bstr_t *)&v66);
  TreeInfo = JobStore::RegOpenTaskKey(a1, (struct JobMoniker *)&iid, &v49, 0x20019u);
  if ( TreeInfo < 0
    || v12
    && (TreeInfo = JobStore::RegOpenTaskOverrideKey((JobStore *)a1, a2, 0x20019u, 2, &v50), v10 = v50, TreeInfo < 0) )
  {
    v9 = v49;
    goto LABEL_111;
  }
  v9 = v49;
  Triggers::Trigulator::Trigulator((Triggers::Trigulator *)&v65);
  Triggers::Trigulator::Trigulator((Triggers::Trigulator *)v62);
  hKey = 0;
  v25 = v48;
  TreeInfo = Triggers::Trigulator::StreamIn((Triggers::Trigulator *)&v65, v9, v48, (unsigned __int64 *)&hKey);
  if ( TreeInfo < 0 )
    goto LABEL_58;
  if ( !v10 )
  {
    v58[0] = v65;
    v58[1] = v66;
    std::list<Triggers::Trigger *>::clear(&v59, v26, v27);
    v28 = v59;
    v59 = v67;
    v67 = v28;
    v29 = v60;
    v60 = v68;
    v68 = v29;
    wmi::AutoRef<JobBucket>::Release(&v61);
    v61 = v69;
    v69 = 0;
    TreeInfo = 0;
LABEL_58:
    v30 = lpcbData;
    goto LABEL_59;
  }
  TreeInfo = Triggers::Trigulator::StreamIn((Triggers::Trigulator *)v62, v10, v25, (unsigned __int64 *)&hKey);
  v30 = lpcbData;
  if ( TreeInfo >= 0 )
  {
    if ( (lpcbData & 1) != 0 )
      std::list<Triggers::Trigger *>::operator=(&v67, v63);
    if ( (lpcbData & 2) != 0 )
      *((_DWORD *)v69 + 4) = *(_DWORD *)(v64 + 16);
    Triggers::Trigulator::operator=(v58, &v65);
    TreeInfo = 0;
  }
LABEL_59:
  Triggers::Trigulator::~Trigulator((Triggers::Trigulator *)v62);
  Triggers::Trigulator::~Trigulator((Triggers::Trigulator *)&v65);
  if ( TreeInfo < 0 )
    goto LABEL_111;
  v33 = v61;
  if ( !v61 )
  {
    TreeInfo = -2147418113;
    goto LABEL_111;
  }
  *(_QWORD *)&v66 = 0;
  v67 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_qqq(*((_QWORD *)WPP_GLOBAL_Control + 2), v31, v32, &v65, &iid, v61);
  }
  if ( v33 )
    _InterlockedIncrement(v33 + 2);
  wmi::AutoRef<JobBucket>::Release(&v67);
  v67 = (JobBucket *)v33;
  if ( (_QWORD)v71 )
    _InterlockedIncrement((volatile signed __int32 *)(v71 + 16));
  _bstr_t::~_bstr_t((_bstr_t *)&v66);
  v66 = v71;
  v65 = iid;
  if ( (_QWORD)v71 )
    _InterlockedIncrement((volatile signed __int32 *)(v71 + 16));
  _bstr_t::~_bstr_t((_bstr_t *)&v71);
  v71 = v66;
  iid = v65;
  v34 = v67;
  if ( v67 )
    _InterlockedIncrement((volatile signed __int32 *)v67 + 2);
  wmi::AutoRef<JobBucket>::Release(&v72);
  v72 = v34;
  wmi::AutoRef<JobBucket>::Release(&v67);
  _bstr_t::~_bstr_t((_bstr_t *)&v66);
  v35 = v54;
  if ( !v54 )
    goto LABEL_103;
  memset_0(v74, 0, sizeof(v74));
  lpcbData = 512;
  cbData = 3;
  TreeInfo = RegQueryValueExW(v9, L"Actions", 0, &cbData, v74, &lpcbData);
  if ( TreeInfo )
  {
    if ( TreeInfo == 234 && cbData == 3 )
    {
      hKey = 0;
      v36 = operator new(lpcbData);
      wmi::AutoVectorPtr<unsigned char>::operator=(&hKey, v36);
      v37 = hKey;
      if ( !hKey )
      {
        operator delete(0);
        TreeInfo = -2147024882;
        goto LABEL_111;
      }
      TreeInfo = RegQueryValueExW(v9, L"Actions", 0, &cbData, (LPBYTE)hKey, &lpcbData);
      if ( TreeInfo )
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
            TreeInfo);
        }
        if ( TreeInfo > 0 )
          TreeInfo = (unsigned __int16)TreeInfo | 0x80070000;
        operator delete(v37);
      }
      else
      {
        TreeInfo = Actions::ActionCollection::ReadData(
                     (Actions::ActionCollection *)&v51,
                     (unsigned __int8 *)v37,
                     lpcbData,
                     0);
        operator delete(v37);
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          10,
          (unsigned int)WPP_fa1b8c42477831648a2e44d3a9ea2fb6_Traceguids,
          (unsigned int)L"Actions",
          TreeInfo);
      }
      v38 = TreeInfo < 0;
      if ( TreeInfo <= 0 )
      {
LABEL_102:
        if ( v38 )
          goto LABEL_111;
LABEL_103:
        *((_DWORD *)v72 + 5) = v30;
        TreeInfo = 0;
        JobMoniker::operator=(v55, &iid);
        if ( v56 )
          Triggers::Trigulator::operator=(v56, v58);
        if ( v35 )
        {
          if ( v35 != &v51 )
          {
            std::list<Task *>::clear(v35);
            v39 = *v35;
            *v35 = v51;
            v51 = v39;
            v40 = v35[1];
            v35[1] = v52;
            v52 = v40;
          }
          _bstr_t::operator=(v35 + 2, v53);
        }
        goto LABEL_111;
      }
      TreeInfo = (unsigned __int16)TreeInfo | 0x80070000;
    }
LABEL_101:
    v38 = TreeInfo < 0;
    goto LABEL_102;
  }
  if ( cbData == 3 )
  {
    TreeInfo = Actions::ActionCollection::ReadData((Actions::ActionCollection *)&v51, v74, lpcbData, 0);
    goto LABEL_101;
  }
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
  TreeInfo = -2147418113;
LABEL_111:
  Actions::ActionCollection::~ActionCollection((Actions::ActionCollection *)&v51);
  Triggers::Trigulator::~Trigulator((Triggers::Trigulator *)v58);
  if ( v10 )
    RegCloseKey(v10);
  if ( v9 )
    RegCloseKey(v9);
  v41 = v72;
  if ( v72 && _InterlockedExchangeAdd((volatile signed __int32 *)v72 + 2, 0xFFFFFFFF) == 1 )
    (**(void (__fastcall ***)(JobBucket *, __int64))v41)(v41, 1);
  v72 = 0;
  _bstr_t::~_bstr_t((_bstr_t *)&v71);
  return (unsigned int)TreeInfo;
}

```

## disassembly

```asm
0x1800141e0  mov     [rsp-8+arg_10], rbx
0x1800141e5  push    rbp
0x1800141e6  push    rsi
0x1800141e7  push    rdi
0x1800141e8  push    r12
0x1800141ea  push    r13
0x1800141ec  push    r14
0x1800141ee  push    r15
0x1800141f0  lea     rbp, [rsp-290h]
0x1800141f8  sub     rsp, 390h
0x1800141ff  mov     rax, cs:__security_cookie
0x180014206  xor     rax, rsp
0x180014209  mov     [rbp+2C0h+var_40], rax
0x180014210  mov     [rbp+2C0h+var_340], r9
0x180014214  mov     [rsp+3C0h+var_374], r8d
0x180014219  mov     r12, rdx
0x18001421c  mov     r15, rcx
0x18001421f  mov     rax, [rbp+2C0h+arg_20]
0x180014226  mov     [rbp+2C0h+var_338], rax
0x18001422a  mov     rax, [rbp+2C0h+arg_28]
0x180014231  mov     [rsp+3C0h+var_348], rax
0x180014236  xorps   xmm0, xmm0
0x180014239  movups  xmmword ptr [rbp+2C0h+var_258.Data1], xmm0
0x18001423d  xor     r8d, r8d; unsigned __int16 *
0x180014240  xor     edx, edx; psz
0x180014242  lea     rcx, [rbp+2C0h+iid]; lpiid
0x180014246  call    ??0JobMoniker@@QEAA@PEBG0@Z; JobMoniker::JobMoniker(ushort const *,ushort const *)
0x18001424b  nop
0x18001424c  xor     ebx, ebx
0x18001424e  mov     esi, ebx
0x180014250  mov     [rsp+3C0h+var_370], rbx
0x180014255  mov     r13d, ebx
0x180014258  mov     [rsp+3C0h+var_368], rbx
0x18001425d  lea     rcx, [rbp+2C0h+var_328]; this
0x180014261  call    ??0Trigulator@Triggers@@QEAA@XZ; Triggers::Trigulator::Trigulator(void)
0x180014266  nop
0x180014267  lea     rcx, [rsp+3C0h+var_360]; this
0x18001426c  call    ??0ActionCollection@Actions@@QEAA@XZ; Actions::ActionCollection::ActionCollection(void)
0x180014271  nop
0x180014272  xor     r9d, r9d; enum JobStore::TaskIndex *
0x180014275  lea     r8, [rbp+2C0h+var_258]; struct _GUID *
0x180014279  mov     rdx, r12; unsigned __int16 *
0x18001427c  mov     rcx, r15; this
0x18001427f  call    ?RegGetTreeInfo@JobStore@@QEBAJPEBGPEAU_GUID@@PEAW4TaskIndex@1@@Z; JobStore::RegGetTreeInfo(ushort const *,_GUID *,JobStore::TaskIndex *)
0x180014284  mov     edi, eax
0x180014286  mov     r14d, 0FFFFFFFFh
0x18001428c  test    eax, eax
0x18001428e  js      loc_180014A7F
0x180014294  mov     [rsp+3C0h+Type], ebx
0x180014298  mov     [rsp+3C0h+cbData], ebx
0x18001429c  mov     dword ptr [rsp+3C0h+Data], ebx
0x1800142a0  mov     [rsp+3C0h+hKey], rbx
0x1800142a5  xor     edi, edi
0x1800142a7  mov     esi, edi
0x1800142a9  mov     [rsp+3C0h+var_390], edi
0x1800142ad  cmp     [r15+20h], rsi
0x1800142b1  jnz     short loc_1800142BE
0x1800142b3  mov     r8d, 32h ; '2'
0x1800142b9  jmp     loc_1800143A8
0x1800142be  test    r12, r12
0x1800142c1  jz      short loc_1800142F7
0x1800142c3  xor     ecx, ecx; bstrString
0x1800142c5  call    cs:__imp_SysFreeString
0x1800142cc  nop     dword ptr [rax+rax+00h]
0x1800142d1  mov     rcx, r12; psz
0x1800142d4  call    cs:__imp_SysAllocString
0x1800142db  nop     dword ptr [rax+rax+00h]
0x1800142e0  mov     rbx, rax
0x1800142e3  mov     [rbp+2C0h+var_330], rax
0x1800142e7  test    rax, rax
0x1800142ea  jnz     short loc_1800142F7
0x1800142ec  mov     ecx, 8007000Eh; unsigned int
0x1800142f1  call    ?PrivateAtlThrow@ATL@@YAXJ@Z; ATL::PrivateAtlThrow(long)
0x1800142f7  mov     eax, edi
0x1800142f9  cmp     [rbx], ax
0x1800142fc  jz      short loc_180014317
0x1800142fe  xchg    ax, ax
0x180014300  mov     ecx, eax
0x180014302  cmp     word ptr [rbx+rcx*2], 5Ch ; '\'
0x180014307  jnz     short loc_18001430F
0x180014309  mov     word ptr [rbx+rcx*2], 2Fh ; '/'
0x18001430f  inc     eax
0x180014311  cmp     [rbx+rax*2], si
0x180014315  jnz     short loc_180014300
0x180014317  lea     rax, [rsp+3C0h+hKey]
0x18001431c  mov     [rsp+3C0h+phkResult], rax; phkResult
0x180014321  mov     r9d, 0F003Fh; samDesired
0x180014327  xor     r8d, r8d; ulOptions
0x18001432a  mov     rdx, rbx; lpSubKey
0x18001432d  mov     rcx, [r15+20h]; hKey
0x180014331  call    cs:__imp_RegOpenKeyExW
0x180014338  nop     dword ptr [rax+rax+00h]
0x18001433d  mov     r8d, eax
0x180014340  test    eax, eax
0x180014342  jnz     short loc_1800143A8
0x180014344  mov     [rsp+3C0h+cbData], 4
0x18001434c  lea     rax, [rsp+3C0h+cbData]
0x180014351  mov     [rsp+3C0h+lpcbData], rax; lpcbData
0x180014356  lea     rax, [rsp+3C0h+Data]
0x18001435b  mov     [rsp+3C0h+phkResult], rax; lpData
0x180014360  lea     r9, [rsp+3C0h+Type]; lpType
0x180014365  xor     r8d, r8d; lpReserved
0x180014368  lea     rdx, aStateflags; "StateFlags"
0x18001436f  mov     rcx, [rsp+3C0h+hKey]; hKey
0x180014374  call    cs:__imp_RegQueryValueExW
0x18001437b  nop     dword ptr [rax+rax+00h]
0x180014380  mov     r8d, eax
0x180014383  test    eax, eax
0x180014385  jnz     short loc_1800143A8
0x180014387  cmp     [rsp+3C0h+Type], 4
0x18001438c  jnz     short loc_1800143A8
0x18001438e  cmp     [rsp+3C0h+cbData], 4
0x180014393  jnz     short loc_1800143A8
0x180014395  mov     eax, dword ptr [rsp+3C0h+Data]
0x180014399  or      eax, 3
0x18001439c  cmp     eax, 3
0x18001439f  cmovz   esi, dword ptr [rsp+3C0h+Data]
0x1800143a4  mov     [rsp+3C0h+var_390], esi
0x1800143a8  lea     rax, WPP_GLOBAL_Control
0x1800143af  mov     rcx, cs:WPP_GLOBAL_Control
0x1800143b6  cmp     rcx, rax
0x1800143b9  jz      short loc_1800143ED
0x1800143bb  test    dword ptr [rcx+1Ch], 40000h
0x1800143c2  jz      short loc_1800143ED
0x1800143c4  cmp     byte ptr [rcx+19h], 2
0x1800143c8  jb      short loc_1800143ED
0x1800143ca  mov     edx, 58h ; 'X'
0x1800143cf  mov     dword ptr [rsp+3C0h+lpcbData], r8d
0x1800143d4  mov     [rsp+3C0h+phkResult], r12
0x1800143d9  mov     r9, r12
0x1800143dc  lea     r8, WPP_575a7bbfdfbc316314e49eeff74208de_Traceguids
0x1800143e3  mov     rcx, [rcx+10h]
0x1800143e7  call    WPP_SF_SSD
0x1800143ec  nop
0x1800143ed  mov     rcx, rbx; bstrString
0x1800143f0  call    cs:__imp_SysFreeString
0x1800143f7  nop     dword ptr [rax+rax+00h]
0x1800143fc  nop
0x1800143fd  mov     rcx, [rsp+3C0h+hKey]; hKey
0x180014402  test    rcx, rcx
0x180014405  jz      short loc_180014413
0x180014407  call    cs:__imp_RegCloseKey
0x18001440e  nop     dword ptr [rax+rax+00h]
0x180014413  mov     qword ptr [rbp+2C0h+var_2A8], rdi
0x180014417  mov     [rbp+2C0h+var_298], rdi
0x18001441b  mov     rcx, cs:WPP_GLOBAL_Control
0x180014422  lea     rax, WPP_GLOBAL_Control
0x180014429  cmp     rcx, rax
0x18001442c  jz      short loc_18001445A
0x18001442e  test    byte ptr [rcx+1Ch], 40h
0x180014432  jz      short loc_18001445A
0x180014434  cmp     byte ptr [rcx+19h], 4
0x180014438  jb      short loc_18001445A
0x18001443a  mov     edx, 0Bh
0x18001443f  lea     rax, [rbp+2C0h+var_258]
0x180014443  mov     [rsp+3C0h+lpcbData], rax
0x180014448  mov     [rsp+3C0h+phkResult], r12
0x18001444d  lea     r9, [rbp+2C0h+var_2B8]
0x180014451  mov     rcx, [rcx+10h]
0x180014455  call    WPP_SF_qS_guid_
0x18001445a  mov     ecx, 0D8h; dwBytes
0x18001445f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180014464  mov     [rbp+2C0h+var_330], rax
0x180014468  test    rax, rax
0x18001446b  jz      short loc_180014483
0x18001446d  mov     rcx, rax; this
0x180014470  call    ??0JobBucket@@QEAA@XZ; JobBucket::JobBucket(void)
0x180014475  mov     rbx, rax
0x180014478  test    rax, rax
0x18001447b  jz      short loc_180014486
0x18001447d  lock inc dword ptr [rax+8]
0x180014481  jmp     short loc_180014486
0x180014483  mov     rbx, rdi
0x180014486  mov     rcx, [rbp+2C0h+var_298]
0x18001448a  test    rcx, rcx
0x18001448d  jz      short loc_1800144AC
0x18001448f  mov     eax, r14d
0x180014492  lock xadd [rcx+8], eax
0x180014497  cmp     eax, 1
0x18001449a  jnz     short loc_1800144AC
0x18001449c  mov     rax, [rcx]
0x18001449f  mov     edx, 1
0x1800144a4  mov     rax, [rax]
0x1800144a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800144ac  mov     [rbp+2C0h+var_298], rbx
0x1800144b0  mov     rdx, r12; unsigned __int16 *
0x1800144b3  lea     rcx, [rbp+2C0h+var_2B8]; this
0x1800144b7  call    ?_SetPath@JobMoniker@@AEAAXPEBG@Z; JobMoniker::_SetPath(ushort const *)
0x1800144bc  movups  xmm0, xmmword ptr [rbp+2C0h+var_258.Data1]
0x1800144c0  movups  [rbp+2C0h+var_2B8], xmm0
0x1800144c4  mov     rax, [rbp+2C0h+var_298]
0x1800144c8  mov     [rax+3Ch], edi
0x1800144cb  mov     rax, qword ptr [rbp+2C0h+var_2A8]
0x1800144cf  test    rax, rax
0x1800144d2  jz      short loc_1800144D8
0x1800144d4  lock inc dword ptr [rax+10h]
0x1800144d8  lea     rcx, [rbp+2C0h+var_270]; this
0x1800144dc  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x1800144e1  mov     rax, qword ptr [rbp+2C0h+var_2A8]
0x1800144e5  mov     qword ptr [rbp+2C0h+var_270], rax
0x1800144e9  mov     rax, qword ptr [rbp+2C0h+var_2A8+8]
0x1800144ed  mov     qword ptr [rbp+2C0h+var_270+8], rax
0x1800144f1  movups  xmm0, [rbp+2C0h+var_2B8]
0x1800144f5  movups  xmmword ptr [rbp+2C0h+iid.Data1], xmm0
0x1800144f9  mov     rbx, [rbp+2C0h+var_298]
0x1800144fd  test    rbx, rbx
0x180014500  jz      short loc_180014506
0x180014502  lock inc dword ptr [rbx+8]
0x180014506  mov     rcx, [rbp+2C0h+var_260]
0x18001450a  test    rcx, rcx
0x18001450d  jz      short loc_18001452C
0x18001450f  mov     eax, r14d
0x180014512  lock xadd [rcx+8], eax
0x180014517  cmp     eax, 1
0x18001451a  jnz     short loc_18001452C
0x18001451c  mov     rax, [rcx]
0x18001451f  mov     edx, 1
0x180014524  mov     rax, [rax]
0x180014527  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001452c  mov     [rbp+2C0h+var_260], rbx
0x180014530  mov     rcx, [rbp+2C0h+var_298]
0x180014534  test    rcx, rcx
0x180014537  jz      short loc_180014556
0x180014539  mov     eax, r14d
0x18001453c  lock xadd [rcx+8], eax
0x180014541  cmp     eax, 1
0x180014544  jnz     short loc_180014556
0x180014546  mov     rax, [rcx]
0x180014549  mov     edx, 1
0x18001454e  mov     rax, [rax]
0x180014551  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014556  xor     ebx, ebx
0x180014558  mov     [rbp+2C0h+var_298], rbx
0x18001455c  lea     rcx, [rbp+2C0h+var_2A8]; this
0x180014560  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180014565  mov     r9d, 20019h; unsigned int
0x18001456b  lea     r8, [rsp+3C0h+var_370]; HKEY *
0x180014570  lea     rdx, [rbp+2C0h+iid]; struct JobMoniker *
0x180014574  mov     rcx, r15; this
0x180014577  call    ?RegOpenTaskKey@JobStore@@QEAAJAEAVJobMoniker@@PEAPEAUHKEY__@@K@Z; JobStore::RegOpenTaskKey(JobMoniker &,HKEY__ * *,ulong)
0x18001457c  mov     edi, eax
0x18001457e  test    eax, eax
0x180014580  js      loc_180014A7A
0x180014586  test    esi, esi
0x180014588  jz      short loc_1800145BA
0x18001458a  lea     rax, [rsp+3C0h+var_368]
0x18001458f  mov     [rsp+3C0h+phkResult], rax; HKEY *
0x180014594  mov     r9d, 2; unsigned int
0x18001459a  mov     r8d, 20019h; unsigned int
0x1800145a0  mov     rdx, r12; unsigned __int16 *
0x1800145a3  mov     rcx, r15; this
0x1800145a6  call    ?RegOpenTaskOverrideKey@JobStore@@AEBAJPEBGKKPEAPEAUHKEY__@@@Z; JobStore::RegOpenTaskOverrideKey(ushort const *,ulong,ulong,HKEY__ * *)
0x1800145ab  mov     edi, eax
0x1800145ad  mov     r13, [rsp+3C0h+var_368]
0x1800145b2  test    eax, eax
0x1800145b4  js      loc_180014A7A
0x1800145ba  mov     rsi, [rsp+3C0h+var_370]
0x1800145bf  lea     rcx, [rbp+2C0h+var_2B8]; this
0x1800145c3  call    ??0Trigulator@Triggers@@QEAA@XZ; Triggers::Trigulator::Trigulator(void)
0x1800145c8  nop
0x1800145c9  lea     rcx, [rbp+2C0h+var_2F0]; this
0x1800145cd  call    ??0Trigulator@Triggers@@QEAA@XZ; Triggers::Trigulator::Trigulator(void)
0x1800145d2  nop
0x1800145d3  mov     [rsp+3C0h+hKey], rbx
0x1800145d8  lea     r9, [rsp+3C0h+hKey]; unsigned __int64 *
0x1800145dd  mov     ebx, [rsp+3C0h+var_374]
0x1800145e1  mov     r8d, ebx; unsigned int
0x1800145e4  mov     rdx, rsi; HKEY
0x1800145e7  lea     rcx, [rbp+2C0h+var_2B8]; this
0x1800145eb  call    ?StreamIn@Trigulator@Triggers@@QEAAJPEAUHKEY__@@KPEA_K@Z; Triggers::Trigulator::StreamIn(HKEY__ *,ulong,unsigned __int64 *)
0x1800145f0  mov     edi, eax
0x1800145f2  test    eax, eax
0x1800145f4  js      loc_1800146B0
0x1800145fa  test    r13, r13
0x1800145fd  jnz     short loc_180014653
0x1800145ff  movups  xmm0, [rbp+2C0h+var_2B8]
0x180014603  movups  [rbp+2C0h+var_328], xmm0
0x180014607  movups  xmm1, [rbp+2C0h+var_2A8]
0x18001460b  movups  [rbp+2C0h+var_318], xmm1
0x18001460f  lea     rcx, [rbp+2C0h+var_308]
0x180014613  call    ?clear@?$list@PEAUTrigger@Triggers@@V?$allocator@PEAUTrigger@Triggers@@@std@@@std@@QEAAXXZ; std::list<Triggers::Trigger *>::clear(void)
0x180014618  mov     rcx, [rbp+2C0h+var_308]
0x18001461c  mov     rax, [rbp+2C0h+var_298]
0x180014620  mov     [rbp+2C0h+var_308], rax
0x180014624  mov     [rbp+2C0h+var_298], rcx
0x180014628  mov     rcx, [rbp+2C0h+var_300]
0x18001462c  mov     rax, [rbp+2C0h+var_290]
0x180014630  mov     [rbp+2C0h+var_300], rax
0x180014634  mov     [rbp+2C0h+var_290], rcx
0x180014638  lea     rcx, [rbp+2C0h+var_2F8]
0x18001463c  call    ?Release@?$AutoRef@VJobBucket@@@wmi@@QEAAXXZ; wmi::AutoRef<JobBucket>::Release(void)
0x180014641  mov     rax, [rbp+2C0h+var_288]
0x180014645  mov     [rbp+2C0h+var_2F8], rax
0x180014649  xor     ebx, ebx
0x18001464b  mov     [rbp+2C0h+var_288], rbx
0x18001464f  mov     edi, ebx
0x180014651  jmp     short loc_1800146B2
0x180014653  lea     r9, [rsp+3C0h+hKey]; unsigned __int64 *
0x180014658  mov     r8d, ebx; unsigned int
0x18001465b  mov     rdx, r13; HKEY
  ... truncated ...
```
