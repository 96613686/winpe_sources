# CSpp::_CreateSnapshotSet(CVolumeEntryMap *,unsigned __int64,ulong,uchar,ulong,_SPP_WRITER_COMPONENT_INFO *,ulong const *,ulong,int,ulong,_SPP_ONDISK_SNAPSHOT_PROP *)

- ea: `0x18001431c`
- end: `0x180014c41`
- name: `?_CreateSnapshotSet@CSpp@@AEAAJPEAVCVolumeEntryMap@@_KKEKPEAU_SPP_WRITER_COMPONENT_INFO@@PEBKKHKPEAU_SPP_ONDISK_SNAPSHOT_PROP@@@Z`
- size: `2341`
- prototype: `__int64 __fastcall(CSpp *this, struct CVolumeEntryMap *, unsigned __int64, unsigned int, unsigned __int8, unsigned int, struct _SPP_WRITER_COMPONENT_INFO *, OLECHAR *, unsigned int, int, unsigned int, struct _GUID *)`
- caller_count: `2`
- callee_count: `33`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180006730`
- `0x180013c7c`

## callees

- `0x1800021f8`
- `0x18000220c`
- `0x18000232c`
- `0x180002ba0`
- `0x180002bd0`
- `0x18000702c`
- `0x180007344`
- `0x180008e0c`
- `0x18000dce0`
- `0x18000e58c`
- `0x180010e68`
- `0x180011198`
- `0x180011558`
- `0x1800131f0`
- `0x18001431c`
- `0x180014d00`
- `0x180016e24`
- `0x180017960`
- `0x180017c74`
- `0x18001e2dc`
- `0x18001eae8`
- `0x18001f714`
- `0x18001f808`
- `0x18001f8f4`
- `0x180020870`
- `0x180020908`
- `0x1800217d8`
- `0x1800268b4`
- `0x1800269ac`
- `0x18002e2ac`
- `0x180034afc`
- `0x180035bd0`
- `0x180037010`

## import_xrefs

- `KERNEL32!GetSystemTimeAsFileTime` at `0x180014575`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800145a8`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180014629`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18001465a`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18001477a`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800147d1`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180014824`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18001485a`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800148fc`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18001495a`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800149b1`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800149f5`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180014575`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800145a8`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180014629`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18001465a`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18001477a`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800147d1`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180014824`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18001485a`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800148fc`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18001495a`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800149b1`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800149f5`
- `VSSAPI!CreateVssBackupComponentsInternal` at `0x1800144bc`
- `VSSAPI!CreateVssBackupComponentsInternal` at `0x1800144bc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014a5f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014a5f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014af0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014b07`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014af0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014b07`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180014ab2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180014ab2`
- `OLEAUT32!__imp_SysFreeString` at `0x180014bb1`
- `OLEAUT32!__imp_SysFreeString` at `0x180014bb1`

## string_xrefs

- `0x1800143d7`: `CSpp::_CreateSnapshotSet`
- `0x180014ac8`: `SkipDeleteMetadataTestHook`

## pseudocode

```c
__int64 __fastcall CSpp::_CreateSnapshotSet(
        CSpp *this,
        struct CVolumeEntryMap *a2,
        unsigned __int64 a3,
        unsigned int a4,
        unsigned __int8 a5,
        unsigned int a6,
        struct _SPP_WRITER_COMPONENT_INFO *a7,
        OLECHAR *a8,
        unsigned int a9,
        int a10,
        unsigned int a11,
        struct _GUID *a12)
{
  GUID v16; // xmm1
  __int64 v17; // rdx
  __int16 v18; // ax
  struct CSxVolumeInfoArray *v19; // rdi
  int v20; // r14d
  int v21; // r15d
  __int16 v22; // ax
  CSpp *v23; // rcx
  __int64 v24; // rdx
  __int64 v25; // r8
  CSpp *v26; // rcx
  CSpp *v27; // rcx
  __int64 v28; // r8
  __int16 v29; // ax
  __int64 v30; // r8
  CSpp *v31; // rcx
  CSpp *v32; // rcx
  CSpp *v33; // rcx
  __int64 v34; // r8
  __int64 v35; // r8
  CSpp *v36; // rcx
  CSpp *v37; // rcx
  __int16 v38; // ax
  __int64 v39; // r8
  __int64 v40; // r8
  CSpp *v41; // rcx
  HKEY v42; // rcx
  char v43; // dl
  ATL::CComBSTR *v44; // rax
  char v45; // al
  __int64 v46; // rax
  unsigned int v47; // ebx
  __int64 v48; // rdx
  __int64 v49; // r8
  int phkResult; // [rsp+20h] [rbp-E0h]
  struct IVssBackupComponents *v52[2]; // [rsp+78h] [rbp-88h] BYREF
  struct _FILETIME v53; // [rsp+88h] [rbp-78h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+90h] [rbp-70h] BYREF
  unsigned int v55; // [rsp+98h] [rbp-68h] BYREF
  int Instance; // [rsp+A0h] [rbp-60h] BYREF
  __int16 v57; // [rsp+A4h] [rbp-5Ch]
  __int16 v58; // [rsp+A6h] [rbp-5Ah]
  struct IVssAsync *v59; // [rsp+D8h] [rbp-28h] BYREF
  HKEY hKey; // [rsp+E0h] [rbp-20h] BYREF
  int v61; // [rsp+E8h] [rbp-18h]
  unsigned int v62; // [rsp+ECh] [rbp-14h]
  unsigned int v63; // [rsp+F0h] [rbp-10h]
  int v64; // [rsp+F4h] [rbp-Ch]
  struct CSxVolumeInfoArray *v65; // [rsp+F8h] [rbp-8h] BYREF
  struct _SPP_WRITER_COMPONENT_INFO *v66; // [rsp+100h] [rbp+0h]
  BSTR bstrString[2]; // [rsp+110h] [rbp+10h] BYREF
  unsigned __int16 *v68[2]; // [rsp+120h] [rbp+20h] BYREF
  __int128 v69; // [rsp+130h] [rbp+30h]
  __int64 v70; // [rsp+140h] [rbp+40h]
  GUID v71; // [rsp+148h] [rbp+48h]

  LODWORD(hKey) = a6;
  v66 = a7;
  bstrString[0] = a8;
  v63 = a9;
  v62 = a11;
  v61 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_qq(*((_QWORD *)WPP_GLOBAL_Control + 2), 106, a3, a2, a12);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&Instance, "CSpp::_CreateSnapshotSet", 6216, 1);
  ATL::CComPtr<IVssBackupComponents>::CComPtr<IVssBackupComponents>(v52);
  ATL::CComPtr<IVssBackupComponents>::CComPtr<IVssBackupComponents>(&v59);
  v16 = GUID_NULL;
  v17 = 0;
  v70 = 0;
  v65 = 0;
  v18 = 6234;
  v19 = 0;
  v55 = 0;
  v64 = 0;
  SystemTimeAsFileTime = 0;
  v53 = 0;
  v71 = GUID_NULL;
  *(_OWORD *)v68 = 0;
  v69 = 0;
  if ( !a12 )
    goto LABEL_5;
  v57 = 6234;
  if ( !a2 && !v66 && !a5 )
  {
    v18 = 6235;
LABEL_5:
    Instance = -2147024809;
    v20 = 0;
    v58 = v18;
    v21 = 0;
    goto LABEL_60;
  }
  Instance = 0;
  v57 = 6235;
  if ( !*((_QWORD *)this + 4) )
  {
    Instance = CSxArrayBuilder<unsigned short *,&void Free_String(unsigned short * *),&void SxDefaultInit<unsigned short *>(unsigned short * *),&void SxDefaultTransfer<unsigned short *>(unsigned short * *,unsigned short * *)>::CreateInstance((char *)this + 32);
    v22 = 6239;
    if ( Instance < 0 )
    {
LABEL_12:
      v58 = v22;
      v20 = 0;
      v21 = 0;
      goto LABEL_60;
    }
    v16 = GUID_NULL;
    v57 = 6239;
  }
  *a12 = v16;
  Instance = CreateVssBackupComponentsInternal(v52, v17);
  v22 = 6244;
  if ( Instance < 0 )
    goto LABEL_12;
  v57 = 6244;
  Instance = (*(__int64 (__fastcall **)(struct IVssBackupComponents *, _QWORD))(*(_QWORD *)v52[0] + 40LL))(v52[0], 0);
  v22 = 6246;
  if ( Instance < 0 )
    goto LABEL_12;
  v57 = 6246;
  Instance = CSpp::_SetSnapshotContext(v23, v52[0], a4);
  v22 = 6248;
  if ( Instance < 0 )
    goto LABEL_12;
  v57 = 6248;
  LOBYTE(phkResult) = 1;
  LOBYTE(v25) = 1;
  LOBYTE(v24) = 1;
  Instance = (*(__int64 (__fastcall **)(struct IVssBackupComponents *, __int64, __int64, _QWORD, int))(*(_QWORD *)v52[0] + 48LL))(
               v52[0],
               v24,
               v25,
               (a4 & 8 | 2) >> 1,
               phkResult);
  v22 = 6251;
  if ( Instance < 0 )
    goto LABEL_12;
  v57 = 6251;
  Instance = CSpp::_EnableInterestingWriters(v26, a10, v52[0]);
  v22 = 6253;
  if ( Instance < 0 )
    goto LABEL_12;
  v57 = 6253;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  Instance = CSpp::_StartSnapshotSet(v27, v52[0], a3, a2, a12);
  v22 = 6256;
  if ( Instance < 0 )
    goto LABEL_12;
  v57 = 6256;
  GetSystemTimeAsFileTime(&v53);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
    WPP_SF_I(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      107,
      v28,
      (*(_QWORD *)&v53 - *(_QWORD *)&SystemTimeAsFileTime) / 0x2710uLL);
  v21 = 1;
  Instance = CSxVolumeInfoArray::CreateInstance(&v65);
  v29 = 6270;
  if ( Instance < 0 )
  {
    v19 = v65;
LABEL_25:
    v20 = 0;
    v58 = v29;
    goto LABEL_60;
  }
  v57 = 6270;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v19 = v65;
  Instance = CSpp::_GatherWriterMetadata(this, v52[0], v65, a3);
  v29 = 6273;
  if ( Instance < 0 )
    goto LABEL_25;
  v57 = 6273;
  GetSystemTimeAsFileTime(&v53);
  v31 = (CSpp *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
    WPP_SF_I(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      108,
      v30,
      (*(_QWORD *)&v53 - *(_QWORD *)&SystemTimeAsFileTime) / 0x2710uLL);
  if ( (a4 & 4) != 0 )
  {
    Instance = CSpp::_VerifySystemWriterPresent(v31, v19);
    v29 = 6284;
    if ( Instance < 0 )
      goto LABEL_25;
    v57 = 6284;
  }
  Instance = CSpp::_VerifyMustHaveWritersPresent(v31, v19);
  v29 = 6287;
  if ( Instance < 0 )
    goto LABEL_25;
  v57 = 6287;
  Instance = CSpp::_AddInterestingComponents(
               this,
               a5,
               v52[0],
               v19,
               a2,
               (unsigned int)hKey,
               v66,
               a4,
               (unsigned int *)bstrString[0],
               v63,
               v62,
               (struct _SPP_ONDISK_SNAPSHOT_PROP *)a12,
               (struct _SPP_METADATA_PROP *)v68);
  v29 = 6304;
  if ( Instance < 0 )
    goto LABEL_25;
  v57 = 6304;
  Instance = CSpp::_AddVolumes(v32, v52[0], (struct _SPP_ONDISK_SNAPSHOT_PROP *)a12);
  v29 = 6306;
  if ( Instance < 0 )
    goto LABEL_25;
  v57 = 6306;
  ATL::CComPtrBase<IVssWMComponent>::Release(&v59);
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  Instance = (*(__int64 (__fastcall **)(struct IVssBackupComponents *, struct IVssAsync **))(*(_QWORD *)v52[0] + 112LL))(
               v52[0],
               &v59);
  v29 = 6311;
  if ( Instance < 0 )
    goto LABEL_25;
  v57 = 6311;
  Instance = CSpp::_AsyncWaitWithTimeout(v33, v59, 0xFFFFFFFF, a3);
  v29 = 6312;
  if ( Instance < 0 )
    goto LABEL_25;
  v57 = 6312;
  GetSystemTimeAsFileTime(&v53);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
    WPP_SF_I(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      109,
      v34,
      (*(_QWORD *)&v53 - *(_QWORD *)&SystemTimeAsFileTime) / 0x2710uLL);
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  Instance = CSpp::_CheckWriterStatus((__int64)this, (__int64 *)v52[0], v19, a3, 1);
  v29 = 6318;
  if ( Instance < 0 )
    goto LABEL_25;
  v57 = 6318;
  GetSystemTimeAsFileTime(&v53);
  v36 = (CSpp *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
    WPP_SF_I(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      110,
      v35,
      (*(_QWORD *)&v53 - *(_QWORD *)&SystemTimeAsFileTime) / 0x2710uLL);
  Instance = CSpp::_GetBackupDocument(v36, v52[0], v68);
  v29 = 6323;
  if ( Instance < 0 )
    goto LABEL_25;
  v57 = 6323;
  Instance = CSpp::_WriteGroupMetadata(this, (struct _SPP_ONDISK_SNAPSHOT_PROP *)a12, (struct _SPP_METADATA_PROP *)v68);
  v29 = 6329;
  if ( Instance < 0 )
    goto LABEL_25;
  v55 = 1;
  v21 = 0;
  v57 = 6329;
  ATL::CComPtrBase<IVssWMComponent>::Release(&v59);
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  Instance = (*(__int64 (__fastcall **)(struct IVssBackupComponents *, struct IVssAsync **))(*(_QWORD *)v52[0] + 304LL))(
               v52[0],
               &v59);
  v38 = 6341;
  if ( Instance < 0
    || (v57 = 6341, Instance = CSpp::_AsyncWaitWithTimeout(v37, v59, 0xFFFFFFFF, a3), v38 = 6343, Instance < 0) )
  {
    v58 = v38;
    v20 = 0;
    goto LABEL_60;
  }
  v57 = 6343;
  GetSystemTimeAsFileTime(&v53);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
    WPP_SF_I(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      111,
      v39,
      (*(_QWORD *)&v53 - *(_QWORD *)&SystemTimeAsFileTime) / 0x2710uLL);
  if ( (a4 & 2) == 0 )
  {
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    Instance = CSpp::_CheckWriterStatus((__int64)this, (__int64 *)v52[0], v19, a3, 2);
    if ( Instance < 0 )
    {
      v20 = 1;
      v58 = 6361;
      goto LABEL_60;
    }
    v57 = 6361;
    GetSystemTimeAsFileTime(&v53);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
      WPP_SF_I(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        112,
        v40,
        (*(_QWORD *)&v53 - *(_QWORD *)&SystemTimeAsFileTime) / 0x2710uLL);
  }
  v20 = 0;
  ATL::CComPtr<IVssBackupComponents>::operator=((struct IUnknown **)this + 10, (struct IUnknown **)v52);
  Free_SPP_COMPONENT_PROP_Array(*((_DWORD *)this + 22), *((struct _SPP_COMPONENT_PROP **)this + 12));
  CoTaskMemFree(*((LPVOID *)this + 12));
  *((_QWORD *)this + 12) = v70;
  *((_DWORD *)this + 22) = DWORD2(v69);
  v70 = 0;
LABEL_60:
  Free_SPP_METADATA_PROP((struct _SPP_METADATA_PROP *)v68);
  if ( v55 )
  {
    v55 = 0;
    hKey = 0;
    if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Windows NT\\CurrentVersion\\SPP", 0, 0x2001Fu, &hKey)
      || (SxRegReadDWORD(hKey, L"SkipDeleteMetadataTestHook", &v55, 1), !v55) )
    {
      CSpp::_DeleteGroupMetadata(v41, (struct _SPP_ONDISK_SNAPSHOT_PROP *)a12);
    }
    v42 = hKey;
    if ( hKey )
    {
      if ( hKey != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
      {
        RegCloseKey(hKey);
        v42 = 0;
        hKey = 0;
      }
      if ( (unsigned __int64)v42 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
        RegCloseKey(v42);
    }
  }
  if ( ATL::CComPtrBase<IVssBackupComponents>::operator!=(v52, 0) && v21 )
    (*(void (__fastcall **)(struct IVssBackupComponents *))(*(_QWORD *)v52[0] + 120LL))(v52[0]);
  if ( ATL::CComPtrBase<IVssBackupComponents>::operator!=(v52, 0) && a12 && v20 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) == 0 )
    {
      v45 = v43;
    }
    else
    {
      v44 = ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)bstrString, a12);
      WPP_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        113,
        &WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids,
        *(_QWORD *)v44);
      v45 = 1;
    }
    if ( (v45 & 1) != 0 )
      SysFreeString(bstrString[0]);
    v46 = *(_QWORD *)v52[0];
    *(struct _GUID *)bstrString = *a12;
    (*(void (__fastcall **)(struct IVssBackupComponents *, BSTR *, __int64))(v46 + 312))(v52[0], bstrString, 2);
  }
  v47 = Instance;
  if ( v19 )
    CWriterEntryArray::Release(v19);
  ATL::CComPtr<IVssExamineWriterMetadata>::~CComPtr<IVssExamineWriterMetadata>();
  ATL::CComPtr<IVssExamineWriterMetadata>::~CComPtr<IVssExamineWriterMetadata>();
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&Instance, v48, v49);
  return v47;
}

```

## disassembly

```asm
0x18001431c  push    rbp
0x18001431e  push    rbx
0x18001431f  push    rsi
0x180014320  push    rdi
0x180014321  push    r12
0x180014323  push    r13
0x180014325  push    r14
0x180014327  push    r15
0x180014329  lea     rbp, [rsp-68h]
0x18001432e  sub     rsp, 168h
0x180014335  mov     rax, cs:__security_cookie
0x18001433c  xor     rax, rsp
0x18001433f  mov     [rbp+0A0h+var_48], rax
0x180014343  mov     al, [rbp+0A0h+arg_20]
0x180014349  mov     r13d, r9d
0x18001434c  mov     rsi, [rbp+0A0h+arg_58]
0x180014353  mov     r12, r8
0x180014356  mov     r15d, [rbp+0A0h+arg_48]
0x18001435d  mov     r14, rdx
0x180014360  mov     [rsp+1A0h+var_12C], al
0x180014364  mov     rbx, rcx
0x180014367  mov     eax, [rbp+0A0h+arg_28]
0x18001436d  mov     dword ptr [rbp+0A0h+hKey], eax
0x180014370  mov     rax, [rbp+0A0h+arg_30]
0x180014377  mov     [rbp+0A0h+var_A0], rax
0x18001437b  mov     rax, [rbp+0A0h+arg_38]
0x180014382  mov     [rbp+0A0h+bstrString], rax
0x180014386  mov     eax, [rbp+0A0h+arg_40]
0x18001438c  mov     [rbp+0A0h+var_B0], eax
0x18001438f  mov     eax, [rbp+0A0h+arg_50]
0x180014395  mov     [rbp+0A0h+var_B4], eax
0x180014398  mov     [rbp+0A0h+var_B8], 0
0x18001439f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800143a6  lea     rax, WPP_GLOBAL_Control
0x1800143ad  cmp     rcx, rax
0x1800143b0  jz      short loc_1800143D1
0x1800143b2  test    dword ptr [rcx+1Ch], 20000000h
0x1800143b9  jz      short loc_1800143D1
0x1800143bb  mov     rcx, [rcx+10h]
0x1800143bf  mov     edx, 6Ah ; 'j'
0x1800143c4  mov     r9, r14
0x1800143c7  mov     [rsp+1A0h+phkResult], rsi
0x1800143cc  call    WPP_SF_qq
0x1800143d1  mov     r9d, 1; unsigned __int16
0x1800143d7  lea     rdx, aCsppCreatesnap; "CSpp::_CreateSnapshotSet"
0x1800143de  mov     r8d, 1848h; unsigned __int16
0x1800143e4  lea     rcx, [rbp+0A0h+var_100]; this
0x1800143e8  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x1800143ed  lea     rcx, [rsp+1A0h+var_128]
0x1800143f2  call    ??0?$CComPtr@VIVssBackupComponents@@@ATL@@QEAA@H@Z; ATL::CComPtr<IVssBackupComponents>::CComPtr<IVssBackupComponents>(int)
0x1800143f7  lea     rcx, [rbp+0A0h+var_C8]
0x1800143fb  call    ??0?$CComPtr@VIVssBackupComponents@@@ATL@@QEAA@H@Z; ATL::CComPtr<IVssBackupComponents>::CComPtr<IVssBackupComponents>(int)
0x180014400  movups  xmm1, xmmword ptr cs:GUID_NULL.Data1
0x180014407  xor     edx, edx
0x180014409  xor     eax, eax
0x18001440b  mov     [rbp+0A0h+var_60], rax
0x18001440f  xorps   xmm0, xmm0
0x180014412  mov     [rbp+0A0h+var_A8], rdx
0x180014416  mov     eax, 185Ah
0x18001441b  mov     [rsp+1A0h+var_130], edx
0x18001441f  mov     edi, edx
0x180014421  mov     [rbp+0A0h+var_108], edx
0x180014424  mov     [rbp+0A0h+var_AC], edx
0x180014427  mov     qword ptr [rbp+0A0h+SystemTimeAsFileTime.dwLowDateTime], rdx
0x18001442b  mov     qword ptr [rbp+0A0h+var_118.dwLowDateTime], rdx
0x18001442f  movdqu  [rbp+0A0h+var_58], xmm1
0x180014434  movups  xmmword ptr [rbp+0A0h+var_80], xmm0
0x180014438  movups  [rbp+0A0h+var_70], xmm0
0x18001443c  test    rsi, rsi
0x18001443f  jnz     short loc_180014457
0x180014441  mov     [rbp+0A0h+var_100], 80070057h
0x180014448  mov     r14d, edx
0x18001444b  mov     [rbp+0A0h+var_FA], ax
0x18001444f  mov     r15d, edx
0x180014452  jmp     loc_180014A77
0x180014457  mov     [rbp+0A0h+var_FC], ax
0x18001445b  test    r14, r14
0x18001445e  jnz     short loc_180014473
0x180014460  cmp     [rbp+0A0h+var_A0], rdx
0x180014464  jnz     short loc_180014473
0x180014466  cmp     [rsp+1A0h+var_12C], dl
0x18001446a  jnz     short loc_180014473
0x18001446c  mov     eax, 185Bh
0x180014471  jmp     short loc_180014441
0x180014473  lea     rcx, [rbx+20h]
0x180014477  mov     [rbp+0A0h+var_100], edx
0x18001447a  mov     eax, 185Bh
0x18001447f  mov     [rbp+0A0h+var_FC], ax
0x180014483  cmp     [rcx], rdx
0x180014486  jnz     short loc_1800144B3
0x180014488  call    ?CreateInstance@?$CSxArrayBuilder@PEAG$1?Free_String@@YAXPEAPEAG@Z$1??$SxDefaultInit@PEAG@@YAX0@Z$1??$SxDefaultTransfer@PEAG@@YAX00@Z@@SAJPEAPEAV1@@Z; CSxArrayBuilder<ushort *,&Free_String(ushort * *),&SxDefaultInit<ushort *>(ushort * *),&SxDefaultTransfer<ushort *>(ushort * *,ushort * *)>::CreateInstance(CSxArrayBuilder<ushort *,&Free_String(ushort * *),&SxDefaultInit<ushort *>(ushort * *),&SxDefaultTransfer<ushort *>(ushort * *,ushort * *)> * *)
0x18001448d  mov     [rbp+0A0h+var_100], eax
0x180014490  test    eax, eax
0x180014492  mov     eax, 185Fh
0x180014497  jns     short loc_1800144A8
0x180014499  mov     [rbp+0A0h+var_FA], ax
0x18001449d  mov     r14d, edi
0x1800144a0  mov     r15d, edi
0x1800144a3  jmp     loc_180014A77
0x1800144a8  movups  xmm1, xmmword ptr cs:GUID_NULL.Data1
0x1800144af  mov     [rbp+0A0h+var_FC], ax
0x1800144b3  lea     rcx, [rsp+1A0h+var_128]
0x1800144b8  movdqu  xmmword ptr [rsi], xmm1
0x1800144bc  call    cs:__imp_CreateVssBackupComponentsInternal
0x1800144c2  mov     [rbp+0A0h+var_100], eax
0x1800144c5  test    eax, eax
0x1800144c7  mov     eax, 1864h
0x1800144cc  js      short loc_180014499
0x1800144ce  mov     rcx, [rsp+1A0h+var_128]
0x1800144d3  xor     edx, edx
0x1800144d5  mov     [rbp+0A0h+var_FC], ax
0x1800144d9  mov     rax, [rcx]
0x1800144dc  mov     rax, [rax+28h]
0x1800144e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800144e5  mov     [rbp+0A0h+var_100], eax
0x1800144e8  test    eax, eax
0x1800144ea  mov     eax, 1866h
0x1800144ef  js      short loc_180014499
0x1800144f1  mov     rdx, [rsp+1A0h+var_128]; struct IVssBackupComponents *
0x1800144f6  mov     r8d, r13d; unsigned int
0x1800144f9  mov     [rbp+0A0h+var_FC], ax
0x1800144fd  call    ?_SetSnapshotContext@CSpp@@AEAAJPEAVIVssBackupComponents@@K@Z; CSpp::_SetSnapshotContext(IVssBackupComponents *,ulong)
0x180014502  mov     [rbp+0A0h+var_100], eax
0x180014505  test    eax, eax
0x180014507  mov     eax, 1868h
0x18001450c  js      short loc_180014499
0x18001450e  mov     rcx, [rsp+1A0h+var_128]
0x180014513  mov     r9d, r13d
0x180014516  mov     [rbp+0A0h+var_FC], ax
0x18001451a  and     r9d, 8
0x18001451e  or      r9d, 2
0x180014522  mov     byte ptr [rsp+1A0h+phkResult], 1
0x180014527  mov     r8b, 1
0x18001452a  shr     r9d, 1
0x18001452d  mov     rax, [rcx]
0x180014530  mov     dl, r8b
0x180014533  mov     rax, [rax+30h]
0x180014537  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001453c  mov     [rbp+0A0h+var_100], eax
0x18001453f  test    eax, eax
0x180014541  mov     eax, 186Bh
0x180014546  js      loc_180014499
0x18001454c  mov     r8, [rsp+1A0h+var_128]; struct IVssBackupComponents *
0x180014551  mov     edx, r15d; int
0x180014554  mov     [rbp+0A0h+var_FC], ax
0x180014558  call    ?_EnableInterestingWriters@CSpp@@AEAAJHPEAVIVssBackupComponents@@@Z; CSpp::_EnableInterestingWriters(int,IVssBackupComponents *)
0x18001455d  mov     [rbp+0A0h+var_100], eax
0x180014560  test    eax, eax
0x180014562  mov     eax, 186Dh
0x180014567  js      loc_180014499
0x18001456d  lea     rcx, [rbp+0A0h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180014571  mov     [rbp+0A0h+var_FC], ax
0x180014575  call    cs:__imp_GetSystemTimeAsFileTime
0x18001457b  mov     rdx, [rsp+1A0h+var_128]; struct IVssBackupComponents *
0x180014580  mov     r9, r14; struct CVolumeEntryMap *
0x180014583  mov     r8, r12; unsigned __int64
0x180014586  mov     [rsp+1A0h+phkResult], rsi; struct _GUID *
0x18001458b  call    ?_StartSnapshotSet@CSpp@@AEAAJPEAVIVssBackupComponents@@_KPEAVCVolumeEntryMap@@PEAU_GUID@@@Z; CSpp::_StartSnapshotSet(IVssBackupComponents *,unsigned __int64,CVolumeEntryMap *,_GUID *)
0x180014590  mov     [rbp+0A0h+var_100], eax
0x180014593  test    eax, eax
0x180014595  mov     eax, 1870h
0x18001459a  js      loc_180014499
0x1800145a0  lea     rcx, [rbp+0A0h+var_118]; lpSystemTimeAsFileTime
0x1800145a4  mov     [rbp+0A0h+var_FC], ax
0x1800145a8  call    cs:__imp_GetSystemTimeAsFileTime
0x1800145ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1800145b5  lea     rdx, WPP_GLOBAL_Control
0x1800145bc  mov     rax, 346DC5D63886594Bh
0x1800145c6  cmp     rcx, rdx
0x1800145c9  jz      short loc_1800145F4
0x1800145cb  test    dword ptr [rcx+1Ch], 8000000h
0x1800145d2  jz      short loc_1800145F4
0x1800145d4  mov     rdx, qword ptr [rbp+0A0h+var_118.dwLowDateTime]
0x1800145d8  sub     rdx, qword ptr [rbp+0A0h+SystemTimeAsFileTime.dwLowDateTime]
0x1800145dc  mov     rcx, [rcx+10h]
0x1800145e0  mul     rdx
0x1800145e3  mov     r9, rdx
0x1800145e6  mov     edx, 6Bh ; 'k'
0x1800145eb  shr     r9, 0Bh
0x1800145ef  call    WPP_SF_I
0x1800145f4  lea     rcx, [rbp+0A0h+var_A8]; struct CSxVolumeInfoArray **
0x1800145f8  mov     r15d, 1
0x1800145fe  call    ?CreateInstance@CSxVolumeInfoArray@@SAJPEAPEAV1@@Z; CSxVolumeInfoArray::CreateInstance(CSxVolumeInfoArray * *)
0x180014603  mov     [rbp+0A0h+var_100], eax
0x180014606  test    eax, eax
0x180014608  mov     eax, 187Eh
0x18001460d  jns     short loc_180014621
0x18001460f  mov     rdi, [rbp+0A0h+var_A8]
0x180014613  mov     r14d, [rsp+1A0h+var_130]
0x180014618  mov     [rbp+0A0h+var_FA], ax
0x18001461c  jmp     loc_180014A77
0x180014621  lea     rcx, [rbp+0A0h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180014625  mov     [rbp+0A0h+var_FC], ax
0x180014629  call    cs:__imp_GetSystemTimeAsFileTime
0x18001462f  mov     rdi, [rbp+0A0h+var_A8]
0x180014633  mov     r9, r12; unsigned __int64
0x180014636  mov     rdx, [rsp+1A0h+var_128]; struct IVssBackupComponents *
0x18001463b  mov     r8, rdi; struct CWriterEntryArray *
0x18001463e  mov     rcx, rbx; this
0x180014641  call    ?_GatherWriterMetadata@CSpp@@AEAAJPEAVIVssBackupComponents@@PEAVCWriterEntryArray@@_K@Z; CSpp::_GatherWriterMetadata(IVssBackupComponents *,CWriterEntryArray *,unsigned __int64)
0x180014646  mov     [rbp+0A0h+var_100], eax
0x180014649  test    eax, eax
0x18001464b  mov     eax, 1881h
0x180014650  js      short loc_180014613
0x180014652  lea     rcx, [rbp+0A0h+var_118]; lpSystemTimeAsFileTime
0x180014656  mov     [rbp+0A0h+var_FC], ax
0x18001465a  call    cs:__imp_GetSystemTimeAsFileTime
0x180014660  mov     rcx, cs:WPP_GLOBAL_Control
0x180014667  lea     rax, WPP_GLOBAL_Control
0x18001466e  cmp     rcx, rax
0x180014671  jz      short loc_1800146A6
0x180014673  test    dword ptr [rcx+1Ch], 8000000h
0x18001467a  jz      short loc_1800146A6
0x18001467c  mov     rdx, qword ptr [rbp+0A0h+var_118.dwLowDateTime]
0x180014680  mov     rax, 346DC5D63886594Bh
0x18001468a  sub     rdx, qword ptr [rbp+0A0h+SystemTimeAsFileTime.dwLowDateTime]
0x18001468e  mov     rcx, [rcx+10h]
0x180014692  mul     rdx
0x180014695  mov     r9, rdx
0x180014698  mov     edx, 6Ch ; 'l'
0x18001469d  shr     r9, 0Bh
0x1800146a1  call    WPP_SF_I
0x1800146a6  test    r13b, 4
0x1800146aa  jz      short loc_1800146C8
0x1800146ac  mov     rdx, rdi; struct CWriterEntryArray *
0x1800146af  call    ?_VerifySystemWriterPresent@CSpp@@AEAAJPEAVCWriterEntryArray@@@Z; CSpp::_VerifySystemWriterPresent(CWriterEntryArray *)
0x1800146b4  mov     [rbp+0A0h+var_100], eax
0x1800146b7  test    eax, eax
0x1800146b9  mov     eax, 188Ch
0x1800146be  js      loc_180014613
0x1800146c4  mov     [rbp+0A0h+var_FC], ax
0x1800146c8  mov     rdx, rdi; struct CWriterEntryArray *
0x1800146cb  call    ?_VerifyMustHaveWritersPresent@CSpp@@AEAAJPEAVCWriterEntryArray@@@Z; CSpp::_VerifyMustHaveWritersPresent(CWriterEntryArray *)
0x1800146d0  mov     [rbp+0A0h+var_100], eax
0x1800146d3  test    eax, eax
0x1800146d5  mov     eax, 188Fh
0x1800146da  js      loc_180014613
0x1800146e0  movzx   edx, [rsp+1A0h+var_12C]; int
0x1800146e5  mov     r9, rdi; struct CWriterEntryArray *
0x1800146e8  mov     r8, [rsp+1A0h+var_128]; struct IVssBackupComponents *
0x1800146ed  mov     rcx, rbx; this
0x1800146f0  mov     [rbp+0A0h+var_FC], ax
0x1800146f4  lea     rax, [rbp+0A0h+var_80]
0x1800146f8  mov     [rsp+1A0h+var_140], rax; struct _SPP_METADATA_PROP *
0x1800146fd  mov     eax, [rbp+0A0h+var_B4]
0x180014700  mov     [rsp+1A0h+var_148], rsi; struct _SPP_ONDISK_SNAPSHOT_PROP *
0x180014705  mov     [rsp+1A0h+var_150], eax; unsigned int
0x180014709  mov     eax, [rbp+0A0h+var_B0]
0x18001470c  mov     [rsp+1A0h+var_158], eax; unsigned int
0x180014710  mov     rax, [rbp+0A0h+bstrString]
0x180014714  mov     [rsp+1A0h+var_160], rax; unsigned int *
0x180014719  mov     rax, [rbp+0A0h+var_A0]
0x18001471d  mov     [rsp+1A0h+var_168], r13d; unsigned int
0x180014722  mov     [rsp+1A0h+var_170], rax; struct _SPP_WRITER_COMPONENT_INFO *
0x180014727  mov     eax, dword ptr [rbp+0A0h+hKey]
0x18001472a  mov     [rsp+1A0h+var_178], eax; unsigned int
0x18001472e  mov     [rsp+1A0h+phkResult], r14; struct CVolumeEntryMap *
0x180014733  call    ?_AddInterestingComponents@CSpp@@AEAAJHPEAVIVssBackupComponents@@PEAVCWriterEntryArray@@PEAVCVolumeEntryMap@@KPEAU_SPP_WRITER_COMPONENT_INFO@@KPEBKKKPEAU_SPP_ONDISK_SNAPSHOT_PROP@@PEAU_SPP_METADATA_PROP@@@Z; CSpp::_AddInterestingComponents(int,IVssBackupComponents *,CWriterEntryArray *,CVolumeEntryMap *,ulong,_SPP_WRITER_COMPONENT_INFO *,ulong,ulong const *,ulong,ulong,_SPP_ONDISK_SNAPSHOT_PROP *,_SPP_METADATA_PROP *)
0x180014738  mov     [rbp+0A0h+var_100], eax
0x18001473b  test    eax, eax
0x18001473d  mov     eax, 18A0h
0x180014742  js      loc_180014613
0x180014748  mov     rdx, [rsp+1A0h+var_128]; struct IVssBackupComponents *
0x18001474d  mov     r8, rsi; struct _SPP_ONDISK_SNAPSHOT_PROP *
0x180014750  mov     [rbp+0A0h+var_FC], ax
0x180014754  call    ?_AddVolumes@CSpp@@AEAAJPEAVIVssBackupComponents@@PEAU_SPP_ONDISK_SNAPSHOT_PROP@@@Z; CSpp::_AddVolumes(IVssBackupComponents *,_SPP_ONDISK_SNAPSHOT_PROP *)
0x180014759  mov     [rbp+0A0h+var_100], eax
0x18001475c  test    eax, eax
0x18001475e  mov     eax, 18A2h
0x180014763  js      loc_180014613
0x180014769  lea     rcx, [rbp+0A0h+var_C8]
0x18001476d  mov     [rbp+0A0h+var_FC], ax
0x180014771  call    ?Release@?$CComPtrBase@VIVssWMComponent@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IVssWMComponent>::Release(void)
0x180014776  lea     rcx, [rbp+0A0h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18001477a  call    cs:__imp_GetSystemTimeAsFileTime
0x180014780  mov     rcx, [rsp+1A0h+var_128]
0x180014785  lea     rdx, [rbp+0A0h+var_C8]
0x180014789  mov     rax, [rcx]
0x18001478c  mov     rax, [rax+70h]
0x180014790  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014795  mov     [rbp+0A0h+var_100], eax
0x180014798  test    eax, eax
0x18001479a  mov     eax, 18A7h
0x18001479f  js      loc_180014613
0x1800147a5  mov     rdx, [rbp+0A0h+var_C8]; struct IVssAsync *
0x1800147a9  mov     r9, r12; unsigned __int64
0x1800147ac  or      r8d, 0FFFFFFFFh; unsigned int
0x1800147b0  mov     [rbp+0A0h+var_FC], ax
0x1800147b4  call    ?_AsyncWaitWithTimeout@CSpp@@AEAAJPEAUIVssAsync@@K_K@Z; CSpp::_AsyncWaitWithTimeout(IVssAsync *,ulong,unsigned __int64)
0x1800147b9  mov     [rbp+0A0h+var_100], eax
0x1800147bc  test    eax, eax
0x1800147be  mov     eax, 18A8h
0x1800147c3  js      loc_180014613
0x1800147c9  lea     rcx, [rbp+0A0h+var_118]; lpSystemTimeAsFileTime
0x1800147cd  mov     [rbp+0A0h+var_FC], ax
0x1800147d1  call    cs:__imp_GetSystemTimeAsFileTime
0x1800147d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800147de  lea     rax, WPP_GLOBAL_Control
0x1800147e5  mov     r14d, 8000000h
0x1800147eb  cmp     rcx, rax
  ... truncated ...
```
