# JobStore::LoadBucketFromRegistry(ushort const *,Triggers::StreamingFilters,JobMoniker &,Triggers::Trigulator *,Actions::ActionCollection *)

- ea: `0x180023b60`
- end: `0x1800244a3`
- name: `?LoadBucketFromRegistry@JobStore@@QEAAJPEBGW4StreamingFilters@Triggers@@AEAVJobMoniker@@PEAVTrigulator@3@PEAVActionCollection@Actions@@@Z`
- size: `2371`
- prototype: `__int64 __fastcall(HKEY *, const unsigned __int16 *, unsigned int, __int64, __int64, __int64 *)`
- caller_count: `10`
- callee_count: `33`
- tags: `file_ops, registry_config, service_task`

## callers

- `0x180022668`
- `0x180022b80`
- `0x180045df0`
- `0x18004d868`
- `0x1800755e8`
- `0x180075c4c`
- `0x1800763cc`
- `0x1800769dc`
- `0x180076dcc`
- `0x180077e50`

## callees

- `0x180007ddc`
- `0x180007ec0`
- `0x180008660`
- `0x1800086c0`
- `0x18000b438`
- `0x18000dc30`
- `0x18000dcb0`
- `0x18000e4c0`
- `0x18000e510`
- `0x1800199c0`
- `0x18001a260`
- `0x18001a430`
- `0x18001ec90`
- `0x180023b60`
- `0x1800244ac`
- `0x1800245dc`
- `0x1800247e0`
- `0x180030f80`
- `0x1800322a0`
- `0x180040b70`
- `0x180043d78`
- `0x180045bb0`
- `0x18004ae48`
- `0x1800504b4`
- `0x180053e54`
- `0x180056794`
- `0x18005790c`
- `0x180066d5c`
- `0x180066e58`
- `0x18006e43c`
- `0x18007e68a`
- `0x18007e6d0`
- `0x180084010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180023c4d`
- `OLEAUT32!__imp_SysAllocString` at `0x180023c4d`
- `OLEAUT32!__imp_SysFreeString` at `0x180023c44`
- `OLEAUT32!__imp_SysFreeString` at `0x180023d55`
- `OLEAUT32!__imp_SysFreeString` at `0x180023c44`
- `OLEAUT32!__imp_SysFreeString` at `0x180023d55`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180023ca2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180023ca2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180023cdf`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800241b8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800242ad`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180023cdf`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800241b8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800242ad`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180023d66`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180024431`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180024440`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180023d66`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180024431`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180024440`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180023dc2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180023dc2`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
  JobBucket *v21; // r8
  JobBucket *v22; // rbx
  JobBucket *v23; // rcx
  JobBucket *v24; // rcx
  unsigned int v25; // ebx
  JobBucket *v26; // rcx
  __int64 v27; // rcx
  DWORD v28; // r15d
  __int64 v29; // rdx
  __int64 v30; // r8
  volatile signed __int32 *v31; // rbx
  JobBucket *v32; // rbx
  __int64 *v33; // r12
  void *v34; // rax
  HKEY v35; // rbx
  bool v36; // sf
  __int64 v37; // rcx
  __int64 v38; // rcx
  JobBucket *v39; // rcx
  DWORD lpcbData; // [rsp+30h] [rbp-D0h] BYREF
  DWORD cbData; // [rsp+34h] [rbp-CCh] BYREF
  BYTE Data[8]; // [rsp+38h] [rbp-C8h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  DWORD Type; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v46; // [rsp+4Ch] [rbp-B4h]
  HKEY v47; // [rsp+50h] [rbp-B0h] BYREF
  HKEY v48; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v49; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v50; // [rsp+68h] [rbp-98h]
  char v51[8]; // [rsp+70h] [rbp-90h] BYREF
  void **pExceptionObject; // [rsp+78h] [rbp-88h] BYREF
  char v53; // [rsp+80h] [rbp-80h]
  const unsigned __int16 *v54; // [rsp+88h] [rbp-78h]
  __int64 v55; // [rsp+90h] [rbp-70h]
  __int64 v56; // [rsp+98h] [rbp-68h] BYREF
  int v57; // [rsp+A0h] [rbp-60h]
  _BYTE v58[12]; // [rsp+A4h] [rbp-5Ch]
  __int64 *v59; // [rsp+B0h] [rbp-50h]
  __int64 v60; // [rsp+B8h] [rbp-48h]
  __int64 v61; // [rsp+C0h] [rbp-40h]
  BSTR v62; // [rsp+C8h] [rbp-38h]
  _OWORD v63[2]; // [rsp+D0h] [rbp-30h] BYREF
  JobBucket *v64; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v65; // [rsp+F8h] [rbp-8h]
  volatile signed __int32 *v66; // [rsp+100h] [rbp+0h] BYREF
  GUID v67; // [rsp+108h] [rbp+8h] BYREF
  __int128 v68; // [rsp+118h] [rbp+18h] BYREF
  JobBucket *v69; // [rsp+128h] [rbp+28h] BYREF
  __int64 v70; // [rsp+130h] [rbp+30h]
  volatile signed __int32 *v71; // [rsp+138h] [rbp+38h]
  GUID iid; // [rsp+140h] [rbp+40h] BYREF
  __int128 v73; // [rsp+150h] [rbp+50h] BYREF
  JobBucket *v74; // [rsp+160h] [rbp+60h] BYREF
  struct _GUID v75; // [rsp+168h] [rbp+68h] BYREF
  BYTE v76[512]; // [rsp+180h] [rbp+80h] BYREF

  v60 = a4;
  v46 = a3;
  v61 = a5;
  v59 = a6;
  v75 = 0;
  JobMoniker::JobMoniker(&iid, 0, 0);
  v8 = 0;
  v9 = 0;
  v47 = 0;
  v10 = 0;
  v48 = 0;
  Triggers::Trigulator::Trigulator((Triggers::Trigulator *)v63);
  Actions::ActionCollection::ActionCollection((Actions::ActionCollection *)&v49);
  TreeInfo = JobStore::RegGetTreeInfo((JobStore *)a1, a2, &v75, 0);
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
      v62 = v8;
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
  *(_QWORD *)&v68 = 0;
  v69 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_qS_guid_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, v17, (unsigned int)&v67, (__int64)a2, (__int64)&v75);
  }
  v18 = (JobBucket *)HeapAlloc(g_PrivateHeap, 0, 0xD8u);
  if ( !v18 )
  {
    v53 = 0;
    v54 = &qword_1800A4718;
    v55 = 0;
    v56 = 0;
    v57 = 14;
    *(_QWORD *)v58 = -1;
    pExceptionObject = &wmi::GenericException::`vftable';
    throw (wmi::OutOfMemoryException *)&pExceptionObject;
  }
  v19 = JobBucket::JobBucket(v18);
  v20 = v19;
  if ( v19 )
    _InterlockedIncrement((volatile signed __int32 *)v19 + 2);
  v21 = v69;
  if ( v69 && _InterlockedExchangeAdd((volatile signed __int32 *)v69 + 2, 0xFFFFFFFF) == 1 )
    (**(void (__fastcall ***)(JobBucket *, __int64))v21)(v21, 1);
  v69 = v20;
  JobMoniker::_SetPath((JobMoniker *)&v67, a2);
  v67 = v75;
  *((_DWORD *)v69 + 15) = 0;
  if ( (_QWORD)v68 )
    _InterlockedIncrement((volatile signed __int32 *)(v68 + 16));
  _bstr_t::~_bstr_t((_bstr_t *)&v73);
  v73 = v68;
  iid = v67;
  v22 = v69;
  if ( v69 )
    _InterlockedIncrement((volatile signed __int32 *)v69 + 2);
  v23 = v74;
  if ( v74 && _InterlockedExchangeAdd((volatile signed __int32 *)v74 + 2, 0xFFFFFFFF) == 1 )
    (**(void (__fastcall ***)(JobBucket *, __int64))v23)(v23, 1);
  v74 = v22;
  v24 = v69;
  if ( v69 && _InterlockedExchangeAdd((volatile signed __int32 *)v69 + 2, 0xFFFFFFFF) == 1 )
    (**(void (__fastcall ***)(JobBucket *, __int64))v24)(v24, 1);
  v69 = 0;
  _bstr_t::~_bstr_t((_bstr_t *)&v68);
  TreeInfo = JobStore::RegOpenTaskKey(a1, (struct JobMoniker *)&iid, &v47, 0x20019u);
  if ( TreeInfo < 0
    || v12
    && (TreeInfo = JobStore::RegOpenTaskOverrideKey((JobStore *)a1, a2, 0x20019u, 2, &v48), v10 = v48, TreeInfo < 0) )
  {
    v9 = v47;
    goto LABEL_111;
  }
  v9 = v47;
  Triggers::Trigulator::Trigulator((Triggers::Trigulator *)&v67);
  Triggers::Trigulator::Trigulator((Triggers::Trigulator *)&pExceptionObject);
  hKey = 0;
  v25 = v46;
  TreeInfo = Triggers::Trigulator::StreamIn((Triggers::Trigulator *)&v67, v9, v46, (unsigned __int64 *)&hKey);
  if ( TreeInfo < 0 )
    goto LABEL_58;
  if ( !v10 )
  {
    v63[0] = v67;
    v63[1] = v68;
    std::list<Triggers::Trigger *>::clear(&v64);
    v26 = v64;
    v64 = v69;
    v69 = v26;
    v27 = v65;
    v65 = v70;
    v70 = v27;
    wmi::AutoRef<JobBucket>::Release(&v66);
    v66 = v71;
    v71 = 0;
    TreeInfo = 0;
LABEL_58:
    v28 = lpcbData;
    goto LABEL_59;
  }
  TreeInfo = Triggers::Trigulator::StreamIn(
               (Triggers::Trigulator *)&pExceptionObject,
               v10,
               v25,
               (unsigned __int64 *)&hKey);
  v28 = lpcbData;
  if ( TreeInfo >= 0 )
  {
    if ( (lpcbData & 1) != 0 )
      std::list<Triggers::Trigger *>::operator=(&v69, &v56);
    if ( (lpcbData & 2) != 0 )
      *((_DWORD *)v71 + 4) = *(_DWORD *)(*(_QWORD *)&v58[4] + 16LL);
    Triggers::Trigulator::operator=(v63, &v67);
    TreeInfo = 0;
  }
LABEL_59:
  Triggers::Trigulator::~Trigulator((Triggers::Trigulator *)&pExceptionObject);
  Triggers::Trigulator::~Trigulator((Triggers::Trigulator *)&v67);
  if ( TreeInfo < 0 )
    goto LABEL_111;
  v31 = v66;
  if ( !v66 )
  {
    TreeInfo = -2147418113;
    goto LABEL_111;
  }
  *(_QWORD *)&v68 = 0;
  v69 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_qqq(*((_QWORD *)WPP_GLOBAL_Control + 2), v29, v30, &v67, &iid, v66);
  }
  if ( v31 )
    _InterlockedIncrement(v31 + 2);
  wmi::AutoRef<JobBucket>::Release(&v69);
  v69 = (JobBucket *)v31;
  if ( (_QWORD)v73 )
    _InterlockedIncrement((volatile signed __int32 *)(v73 + 16));
  _bstr_t::~_bstr_t((_bstr_t *)&v68);
  v68 = v73;
  v67 = iid;
  if ( (_QWORD)v73 )
    _InterlockedIncrement((volatile signed __int32 *)(v73 + 16));
  _bstr_t::~_bstr_t((_bstr_t *)&v73);
  v73 = v68;
  iid = v67;
  v32 = v69;
  if ( v69 )
    _InterlockedIncrement((volatile signed __int32 *)v69 + 2);
  wmi::AutoRef<JobBucket>::Release(&v74);
  v74 = v32;
  wmi::AutoRef<JobBucket>::Release(&v69);
  _bstr_t::~_bstr_t((_bstr_t *)&v68);
  v33 = v59;
  if ( !v59 )
    goto LABEL_103;
  memset_0(v76, 0, sizeof(v76));
  lpcbData = 512;
  cbData = 3;
  TreeInfo = RegQueryValueExW(v9, L"Actions", 0, &cbData, v76, &lpcbData);
  if ( TreeInfo )
  {
    if ( TreeInfo == 234 && cbData == 3 )
    {
      hKey = 0;
      v34 = operator new(lpcbData);
      wmi::AutoVectorPtr<unsigned char>::operator=(&hKey, v34);
      v35 = hKey;
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
        operator delete(v35);
      }
      else
      {
        TreeInfo = Actions::ActionCollection::ReadData(
                     (Actions::ActionCollection *)&v49,
                     (unsigned __int8 *)v35,
                     lpcbData,
                     0);
        operator delete(v35);
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
      v36 = TreeInfo < 0;
      if ( TreeInfo <= 0 )
      {
LABEL_102:
        if ( v36 )
          goto LABEL_111;
LABEL_103:
        *((_DWORD *)v74 + 5) = v28;
        TreeInfo = 0;
        JobMoniker::operator=(v60, &iid);
        if ( v61 )
          Triggers::Trigulator::operator=(v61, v63);
        if ( v33 )
        {
          if ( v33 != &v49 )
          {
            std::list<Task *>::clear(v33);
            v37 = *v33;
            *v33 = v49;
            v49 = v37;
            v38 = v33[1];
            v33[1] = v50;
            v50 = v38;
          }
          _bstr_t::operator=(v33 + 2, v51);
        }
        goto LABEL_111;
      }
      TreeInfo = (unsigned __int16)TreeInfo | 0x80070000;
    }
LABEL_101:
    v36 = TreeInfo < 0;
    goto LABEL_102;
  }
  if ( cbData == 3 )
  {
    TreeInfo = Actions::ActionCollection::ReadData((Actions::ActionCollection *)&v49, v76, lpcbData, 0);
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
  Actions::ActionCollection::~ActionCollection((Actions::ActionCollection *)&v49);
  Triggers::Trigulator::~Trigulator((Triggers::Trigulator *)v63);
  if ( v10 )
    RegCloseKey(v10);
  if ( v9 )
    RegCloseKey(v9);
  v39 = v74;
  if ( v74 && _InterlockedExchangeAdd((volatile signed __int32 *)v74 + 2, 0xFFFFFFFF) == 1 )
    (**(void (__fastcall ***)(JobBucket *, __int64))v39)(v39, 1);
  v74 = 0;
  _bstr_t::~_bstr_t((_bstr_t *)&v73);
  return (unsigned int)TreeInfo;
}

```

## disassembly

```asm
0x180023b60  mov     [rsp-8+arg_10], rbx
0x180023b65  push    rbp
0x180023b66  push    rsi
0x180023b67  push    rdi
0x180023b68  push    r12
0x180023b6a  push    r13
0x180023b6c  push    r14
0x180023b6e  push    r15
0x180023b70  lea     rbp, [rsp-290h]
0x180023b78  sub     rsp, 390h
0x180023b7f  mov     rax, cs:__security_cookie
0x180023b86  xor     rax, rsp
0x180023b89  mov     [rbp+2C0h+var_40], rax
0x180023b90  mov     [rbp+2C0h+var_308], r9
0x180023b94  mov     [rsp+3C0h+var_374], r8d
0x180023b99  mov     r12, rdx
0x180023b9c  mov     r15, rcx
0x180023b9f  mov     rax, [rbp+2C0h+arg_20]
0x180023ba6  mov     [rbp+2C0h+var_300], rax
0x180023baa  mov     rax, [rbp+2C0h+arg_28]
0x180023bb1  mov     [rbp+2C0h+var_310], rax
0x180023bb5  xorps   xmm0, xmm0
0x180023bb8  movups  xmmword ptr [rbp+2C0h+var_258.Data1], xmm0
0x180023bbc  xor     r8d, r8d; unsigned __int16 *
0x180023bbf  xor     edx, edx; psz
0x180023bc1  lea     rcx, [rbp+2C0h+iid]; lpiid
0x180023bc5  call    ??0JobMoniker@@QEAA@PEBG0@Z; JobMoniker::JobMoniker(ushort const *,ushort const *)
0x180023bca  nop
0x180023bcb  xor     ebx, ebx
0x180023bcd  mov     esi, ebx
0x180023bcf  mov     [rsp+3C0h+var_370], rbx
0x180023bd4  mov     r13d, ebx
0x180023bd7  mov     [rsp+3C0h+var_368], rbx
0x180023bdc  lea     rcx, [rbp+2C0h+var_2F0]; this
0x180023be0  call    ??0Trigulator@Triggers@@QEAA@XZ; Triggers::Trigulator::Trigulator(void)
0x180023be5  nop
0x180023be6  lea     rcx, [rsp+3C0h+var_360]; this
0x180023beb  call    ??0ActionCollection@Actions@@QEAA@XZ; Actions::ActionCollection::ActionCollection(void)
0x180023bf0  nop
0x180023bf1  xor     r9d, r9d; enum JobStore::TaskIndex *
0x180023bf4  lea     r8, [rbp+2C0h+var_258]; struct _GUID *
0x180023bf8  mov     rdx, r12; unsigned __int16 *
0x180023bfb  mov     rcx, r15; this
0x180023bfe  call    ?RegGetTreeInfo@JobStore@@QEBAJPEBGPEAU_GUID@@PEAW4TaskIndex@1@@Z; JobStore::RegGetTreeInfo(ushort const *,_GUID *,JobStore::TaskIndex *)
0x180023c03  mov     edi, eax
0x180023c05  mov     r14d, 0FFFFFFFFh
0x180023c0b  test    eax, eax
0x180023c0d  js      loc_180024414
0x180023c13  mov     [rsp+3C0h+Type], ebx
0x180023c17  mov     [rsp+3C0h+cbData], ebx
0x180023c1b  mov     dword ptr [rsp+3C0h+Data], ebx
0x180023c1f  mov     [rsp+3C0h+hKey], rbx
0x180023c24  xor     edi, edi
0x180023c26  mov     esi, edi
0x180023c28  mov     [rsp+3C0h+var_390], edi
0x180023c2c  cmp     [r15+20h], rsi
0x180023c30  jnz     short loc_180023C3D
0x180023c32  mov     r8d, 32h ; '2'
0x180023c38  jmp     loc_180023D0D
0x180023c3d  test    r12, r12
0x180023c40  jz      short loc_180023C6A
0x180023c42  xor     ecx, ecx; bstrString
0x180023c44  call    cs:__imp_SysFreeString
0x180023c4a  mov     rcx, r12; psz
0x180023c4d  call    cs:__imp_SysAllocString
0x180023c53  mov     rbx, rax
0x180023c56  mov     [rbp+2C0h+var_2F8], rax
0x180023c5a  test    rax, rax
0x180023c5d  jnz     short loc_180023C6A
0x180023c5f  mov     ecx, 8007000Eh; unsigned int
0x180023c64  call    ?PrivateAtlThrow@ATL@@YAXJ@Z; ATL::PrivateAtlThrow(long)
0x180023c6a  mov     eax, edi
0x180023c6c  cmp     [rbx], di
0x180023c6f  jz      short loc_180023C88
0x180023c71  mov     ecx, eax
0x180023c73  cmp     word ptr [rbx+rcx*2], 5Ch ; '\'
0x180023c78  jnz     short loc_180023C80
0x180023c7a  mov     word ptr [rbx+rcx*2], 2Fh ; '/'
0x180023c80  inc     eax
0x180023c82  cmp     [rbx+rax*2], si
0x180023c86  jnz     short loc_180023C71
0x180023c88  lea     rax, [rsp+3C0h+hKey]
0x180023c8d  mov     [rsp+3C0h+phkResult], rax; phkResult
0x180023c92  mov     r9d, 0F003Fh; samDesired
0x180023c98  xor     r8d, r8d; ulOptions
0x180023c9b  mov     rdx, rbx; lpSubKey
0x180023c9e  mov     rcx, [r15+20h]; hKey
0x180023ca2  call    cs:__imp_RegOpenKeyExW
0x180023ca8  mov     r8d, eax
0x180023cab  test    eax, eax
0x180023cad  jnz     short loc_180023D0D
0x180023caf  mov     [rsp+3C0h+cbData], 4
0x180023cb7  lea     rax, [rsp+3C0h+cbData]
0x180023cbc  mov     [rsp+3C0h+lpcbData], rax; lpcbData
0x180023cc1  lea     rax, [rsp+3C0h+Data]
0x180023cc6  mov     [rsp+3C0h+phkResult], rax; lpData
0x180023ccb  lea     r9, [rsp+3C0h+Type]; lpType
0x180023cd0  xor     r8d, r8d; lpReserved
0x180023cd3  lea     rdx, aStateflags; "StateFlags"
0x180023cda  mov     rcx, [rsp+3C0h+hKey]; hKey
0x180023cdf  call    cs:__imp_RegQueryValueExW
0x180023ce5  mov     r8d, eax
0x180023ce8  test    eax, eax
0x180023cea  jnz     short loc_180023D0D
0x180023cec  cmp     [rsp+3C0h+Type], 4
0x180023cf1  jnz     short loc_180023D0D
0x180023cf3  cmp     [rsp+3C0h+cbData], 4
0x180023cf8  jnz     short loc_180023D0D
0x180023cfa  mov     eax, dword ptr [rsp+3C0h+Data]
0x180023cfe  or      eax, 3
0x180023d01  cmp     eax, 3
0x180023d04  cmovz   esi, dword ptr [rsp+3C0h+Data]
0x180023d09  mov     [rsp+3C0h+var_390], esi
0x180023d0d  lea     rax, WPP_GLOBAL_Control
0x180023d14  mov     rcx, cs:WPP_GLOBAL_Control
0x180023d1b  cmp     rcx, rax
0x180023d1e  jz      short loc_180023D52
0x180023d20  test    dword ptr [rcx+1Ch], 40000h
0x180023d27  jz      short loc_180023D52
0x180023d29  cmp     byte ptr [rcx+19h], 2
0x180023d2d  jb      short loc_180023D52
0x180023d2f  mov     edx, 58h ; 'X'
0x180023d34  mov     dword ptr [rsp+3C0h+lpcbData], r8d
0x180023d39  mov     [rsp+3C0h+phkResult], r12
0x180023d3e  mov     r9, r12
0x180023d41  lea     r8, WPP_575a7bbfdfbc316314e49eeff74208de_Traceguids
0x180023d48  mov     rcx, [rcx+10h]
0x180023d4c  call    WPP_SF_SSD
0x180023d51  nop
0x180023d52  mov     rcx, rbx; bstrString
0x180023d55  call    cs:__imp_SysFreeString
0x180023d5b  nop
0x180023d5c  mov     rcx, [rsp+3C0h+hKey]; hKey
0x180023d61  test    rcx, rcx
0x180023d64  jz      short loc_180023D6C
0x180023d66  call    cs:__imp_RegCloseKey
0x180023d6c  mov     qword ptr [rbp+2C0h+var_2A8], rdi
0x180023d70  mov     [rbp+2C0h+var_298], rdi
0x180023d74  mov     rcx, cs:WPP_GLOBAL_Control
0x180023d7b  lea     rax, WPP_GLOBAL_Control
0x180023d82  cmp     rcx, rax
0x180023d85  jz      short loc_180023DB3
0x180023d87  test    byte ptr [rcx+1Ch], 40h
0x180023d8b  jz      short loc_180023DB3
0x180023d8d  cmp     byte ptr [rcx+19h], 4
0x180023d91  jb      short loc_180023DB3
0x180023d93  mov     edx, 0Bh
0x180023d98  lea     rax, [rbp+2C0h+var_258]
0x180023d9c  mov     [rsp+3C0h+lpcbData], rax
0x180023da1  mov     [rsp+3C0h+phkResult], r12
0x180023da6  lea     r9, [rbp+2C0h+var_2B8]
0x180023daa  mov     rcx, [rcx+10h]
0x180023dae  call    WPP_SF_qS_guid_
0x180023db3  xor     edx, edx; dwFlags
0x180023db5  mov     r8d, 0D8h; dwBytes
0x180023dbb  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x180023dc2  call    cs:__imp_HeapAlloc
0x180023dc8  test    rax, rax
0x180023dcb  jnz     short loc_180023E10
0x180023dcd  mov     [rbp+2C0h+var_340], al
0x180023dd0  lea     rax, qword_1800A4718
0x180023dd7  mov     [rbp+2C0h+var_338], rax
0x180023ddb  mov     [rbp+2C0h+var_330], rdi
0x180023ddf  mov     [rbp+2C0h+var_328], rdi
0x180023de3  mov     [rbp+2C0h+var_320], 0Eh
0x180023dea  mov     qword ptr [rbp+2C0h+var_31C], 0FFFFFFFFFFFFFFFFh
0x180023df2  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180023df9  mov     [rsp+3C0h+pExceptionObject], rax
0x180023dfe  lea     rdx, _TI4?AVOutOfMemoryException@wmi@@; pThrowInfo
0x180023e05  lea     rcx, [rsp+3C0h+pExceptionObject]; pExceptionObject
0x180023e0a  call    _CxxThrowException_0
0x180023e10  mov     rcx, rax; this
0x180023e13  call    ??0JobBucket@@QEAA@XZ; JobBucket::JobBucket(void)
0x180023e18  mov     rbx, rax
0x180023e1b  test    rax, rax
0x180023e1e  jz      short loc_180023E24
0x180023e20  lock inc dword ptr [rax+8]
0x180023e24  mov     r8, [rbp+2C0h+var_298]
0x180023e28  test    r8, r8
0x180023e2b  jz      short loc_180023E4B
0x180023e2d  mov     ecx, r14d
0x180023e30  lock xadd [r8+8], ecx
0x180023e36  cmp     ecx, 1
0x180023e39  jnz     short loc_180023E4B
0x180023e3b  mov     rax, [r8]
0x180023e3e  mov     edx, ecx
0x180023e40  mov     rcx, r8
0x180023e43  mov     rax, [rax]
0x180023e46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023e4b  mov     [rbp+2C0h+var_298], rbx
0x180023e4f  mov     rdx, r12; unsigned __int16 *
0x180023e52  lea     rcx, [rbp+2C0h+var_2B8]; this
0x180023e56  call    ?_SetPath@JobMoniker@@AEAAXPEBG@Z; JobMoniker::_SetPath(ushort const *)
0x180023e5b  movups  xmm0, xmmword ptr [rbp+2C0h+var_258.Data1]
0x180023e5f  movups  [rbp+2C0h+var_2B8], xmm0
0x180023e63  mov     rax, [rbp+2C0h+var_298]
0x180023e67  mov     [rax+3Ch], edi
0x180023e6a  mov     rax, qword ptr [rbp+2C0h+var_2A8]
0x180023e6e  test    rax, rax
0x180023e71  jz      short loc_180023E77
0x180023e73  lock inc dword ptr [rax+10h]
0x180023e77  lea     rcx, [rbp+2C0h+var_270]; this
0x180023e7b  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180023e80  mov     rax, qword ptr [rbp+2C0h+var_2A8]
0x180023e84  mov     qword ptr [rbp+2C0h+var_270], rax
0x180023e88  mov     rax, qword ptr [rbp+2C0h+var_2A8+8]
0x180023e8c  mov     qword ptr [rbp+2C0h+var_270+8], rax
0x180023e90  movups  xmm0, [rbp+2C0h+var_2B8]
0x180023e94  movups  xmmword ptr [rbp+2C0h+iid.Data1], xmm0
0x180023e98  mov     rbx, [rbp+2C0h+var_298]
0x180023e9c  test    rbx, rbx
0x180023e9f  jz      short loc_180023EA5
0x180023ea1  lock inc dword ptr [rbx+8]
0x180023ea5  mov     rcx, [rbp+2C0h+var_260]
0x180023ea9  test    rcx, rcx
0x180023eac  jz      short loc_180023ECB
0x180023eae  mov     eax, r14d
0x180023eb1  lock xadd [rcx+8], eax
0x180023eb6  cmp     eax, 1
0x180023eb9  jnz     short loc_180023ECB
0x180023ebb  mov     rax, [rcx]
0x180023ebe  mov     edx, 1
0x180023ec3  mov     rax, [rax]
0x180023ec6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023ecb  mov     [rbp+2C0h+var_260], rbx
0x180023ecf  mov     rcx, [rbp+2C0h+var_298]
0x180023ed3  test    rcx, rcx
0x180023ed6  jz      short loc_180023EF5
0x180023ed8  mov     eax, r14d
0x180023edb  lock xadd [rcx+8], eax
0x180023ee0  cmp     eax, 1
0x180023ee3  jnz     short loc_180023EF5
0x180023ee5  mov     rax, [rcx]
0x180023ee8  mov     edx, 1
0x180023eed  mov     rax, [rax]
0x180023ef0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023ef5  xor     ebx, ebx
0x180023ef7  mov     [rbp+2C0h+var_298], rbx
0x180023efb  lea     rcx, [rbp+2C0h+var_2A8]; this
0x180023eff  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180023f04  mov     r9d, 20019h; unsigned int
0x180023f0a  lea     r8, [rsp+3C0h+var_370]; HKEY *
0x180023f0f  lea     rdx, [rbp+2C0h+iid]; struct JobMoniker *
0x180023f13  mov     rcx, r15; this
0x180023f16  call    ?RegOpenTaskKey@JobStore@@QEAAJAEAVJobMoniker@@PEAPEAUHKEY__@@K@Z; JobStore::RegOpenTaskKey(JobMoniker &,HKEY__ * *,ulong)
0x180023f1b  mov     edi, eax
0x180023f1d  test    eax, eax
0x180023f1f  js      loc_18002440F
0x180023f25  test    esi, esi
0x180023f27  jz      short loc_180023F59
0x180023f29  lea     rax, [rsp+3C0h+var_368]
0x180023f2e  mov     [rsp+3C0h+phkResult], rax; HKEY *
0x180023f33  mov     r9d, 2; unsigned int
0x180023f39  mov     r8d, 20019h; unsigned int
0x180023f3f  mov     rdx, r12; unsigned __int16 *
0x180023f42  mov     rcx, r15; this
0x180023f45  call    ?RegOpenTaskOverrideKey@JobStore@@AEBAJPEBGKKPEAPEAUHKEY__@@@Z; JobStore::RegOpenTaskOverrideKey(ushort const *,ulong,ulong,HKEY__ * *)
0x180023f4a  mov     edi, eax
0x180023f4c  mov     r13, [rsp+3C0h+var_368]
0x180023f51  test    eax, eax
0x180023f53  js      loc_18002440F
0x180023f59  mov     rsi, [rsp+3C0h+var_370]
0x180023f5e  lea     rcx, [rbp+2C0h+var_2B8]; this
0x180023f62  call    ??0Trigulator@Triggers@@QEAA@XZ; Triggers::Trigulator::Trigulator(void)
0x180023f67  nop
0x180023f68  lea     rcx, [rsp+3C0h+pExceptionObject]; this
0x180023f6d  call    ??0Trigulator@Triggers@@QEAA@XZ; Triggers::Trigulator::Trigulator(void)
0x180023f72  nop
0x180023f73  mov     [rsp+3C0h+hKey], rbx
0x180023f78  lea     r9, [rsp+3C0h+hKey]; unsigned __int64 *
0x180023f7d  mov     ebx, [rsp+3C0h+var_374]
0x180023f81  mov     r8d, ebx; unsigned int
0x180023f84  mov     rdx, rsi; HKEY
0x180023f87  lea     rcx, [rbp+2C0h+var_2B8]; this
0x180023f8b  call    ?StreamIn@Trigulator@Triggers@@QEAAJPEAUHKEY__@@KPEA_K@Z; Triggers::Trigulator::StreamIn(HKEY__ *,ulong,unsigned __int64 *)
0x180023f90  mov     edi, eax
0x180023f92  test    eax, eax
0x180023f94  js      loc_180024051
0x180023f9a  test    r13, r13
0x180023f9d  jnz     short loc_180023FF3
0x180023f9f  movups  xmm0, [rbp+2C0h+var_2B8]
0x180023fa3  movups  [rbp+2C0h+var_2F0], xmm0
0x180023fa7  movups  xmm1, [rbp+2C0h+var_2A8]
0x180023fab  movups  [rbp+2C0h+var_2E0], xmm1
0x180023faf  lea     rcx, [rbp+2C0h+var_2D0]
0x180023fb3  call    ?clear@?$list@PEAUTrigger@Triggers@@V?$allocator@PEAUTrigger@Triggers@@@std@@@std@@QEAAXXZ; std::list<Triggers::Trigger *>::clear(void)
0x180023fb8  mov     rcx, [rbp+2C0h+var_2D0]
0x180023fbc  mov     rax, [rbp+2C0h+var_298]
0x180023fc0  mov     [rbp+2C0h+var_2D0], rax
0x180023fc4  mov     [rbp+2C0h+var_298], rcx
0x180023fc8  mov     rcx, [rbp+2C0h+var_2C8]
0x180023fcc  mov     rax, [rbp+2C0h+var_290]
0x180023fd0  mov     [rbp+2C0h+var_2C8], rax
0x180023fd4  mov     [rbp+2C0h+var_290], rcx
0x180023fd8  lea     rcx, [rbp+2C0h+var_2C0]
0x180023fdc  call    ?Release@?$AutoRef@VJobBucket@@@wmi@@QEAAXXZ; wmi::AutoRef<JobBucket>::Release(void)
0x180023fe1  mov     rax, [rbp+2C0h+var_288]
0x180023fe5  mov     [rbp+2C0h+var_2C0], rax
0x180023fe9  xor     ebx, ebx
0x180023feb  mov     [rbp+2C0h+var_288], rbx
  ... truncated ...
```
