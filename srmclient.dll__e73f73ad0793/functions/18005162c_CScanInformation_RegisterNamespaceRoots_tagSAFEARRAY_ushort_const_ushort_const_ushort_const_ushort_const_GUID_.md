# CScanInformation::RegisterNamespaceRoots(tagSAFEARRAY *,ushort const *,ushort const *,ushort const *,ushort const *,_GUID const &,_GUID const &,_FsrmExecutionOption,CSrmFileTime const &,ulong,IFsrmPipelineConsumer *)

- ea: `0x18005162c`
- end: `0x180052796`
- name: `?RegisterNamespaceRoots@CScanInformation@@QEAAXPEAUtagSAFEARRAY@@PEBG111AEBU_GUID@@2W4_FsrmExecutionOption@@AEBVCSrmFileTime@@KPEAUIFsrmPipelineConsumer@@@Z`
- size: `4458`
- prototype: `void(CScanInformation *__hidden this, struct tagSAFEARRAY *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const struct _GUID *, const struct _GUID *, enum _FsrmExecutionOption, const struct CSrmFileTime *, unsigned int, struct IFsrmPipelineConsumer *)`
- caller_count: `1`
- callee_count: `42`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18009a9a8`

## callees

- `0x180001304`
- `0x180001350`
- `0x180001418`
- `0x1800020ba`
- `0x180002a6c`
- `0x180006a1c`
- `0x1800095f4`
- `0x18000ad14`
- `0x18000af40`
- `0x180010bc4`
- `0x180012238`
- `0x18001fcd4`
- `0x180034b2c`
- `0x180040040`
- `0x1800403e0`
- `0x1800406b4`
- `0x18004f8d4`
- `0x18005162c`
- `0x180052e28`
- `0x180053974`
- `0x180053a04`
- `0x180053f08`
- `0x180058d98`
- `0x180058ec0`
- `0x180058f38`
- `0x180059008`
- `0x18006fe68`
- `0x18006febc`
- `0x18007006c`
- `0x1800700b8`
- `0x180070380`
- `0x180071efc`
- `0x180073a80`
- `0x180073f54`
- `0x180074d00`
- `0x18007c45c`
- `0x18007f760`
- `0x18007fbd8`
- `0x18008d668`
- `0x1800b078a`
- `0x1800b07d0`
- `0x1800d5010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180051968`
- `ole32!CoTaskMemFree` at `0x180051ab9`
- `ole32!CoTaskMemFree` at `0x180051c18`
- `ole32!CoTaskMemFree` at `0x180051e2d`
- `ole32!CoTaskMemFree` at `0x180051ea4`
- `ole32!CoTaskMemFree` at `0x180051eb9`
- `ole32!CoTaskMemFree` at `0x180051968`
- `ole32!CoTaskMemFree` at `0x180051ab9`
- `ole32!CoTaskMemFree` at `0x180051c18`
- `ole32!CoTaskMemFree` at `0x180051e2d`
- `ole32!CoTaskMemFree` at `0x180051ea4`
- `ole32!CoTaskMemFree` at `0x180051eb9`
- `OLEAUT32!__imp_SysAllocString` at `0x18005194e`
- `OLEAUT32!__imp_SysAllocString` at `0x180051a9f`
- `OLEAUT32!__imp_SysAllocString` at `0x180051bfe`
- `OLEAUT32!__imp_SysAllocString` at `0x180051e13`
- `OLEAUT32!__imp_SysAllocString` at `0x18005194e`
- `OLEAUT32!__imp_SysAllocString` at `0x180051a9f`
- `OLEAUT32!__imp_SysAllocString` at `0x180051bfe`
- `OLEAUT32!__imp_SysAllocString` at `0x180051e13`
- `OLEAUT32!__imp_SysFreeString` at `0x18005198c`
- `OLEAUT32!__imp_SysFreeString` at `0x180051e59`
- `OLEAUT32!__imp_SysFreeString` at `0x1800524ce`
- `OLEAUT32!__imp_SysFreeString` at `0x18005198c`
- `OLEAUT32!__imp_SysFreeString` at `0x180051e59`
- `OLEAUT32!__imp_SysFreeString` at `0x1800524ce`
- `OLEAUT32!__imp_VariantInit` at `0x180051754`
- `OLEAUT32!__imp_VariantInit` at `0x180051754`
- `OLEAUT32!__imp_VariantClear` at `0x1800517bc`
- `OLEAUT32!__imp_VariantClear` at `0x1800517bc`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18005178a`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18005178a`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180051765`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180051765`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x1800517d6`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x1800517d6`
- `KERNEL32!CreateFileW` at `0x180051b00`
- `KERNEL32!CreateFileW` at `0x180051b00`
- `KERNEL32!CloseHandle` at `0x180051c41`
- `KERNEL32!CloseHandle` at `0x180051c41`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18005216d`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800522e7`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18005216d`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800522e7`
- `KERNEL32!GetLastError` at `0x18005263e`
- `KERNEL32!GetLastError` at `0x18005263e`
- `KERNEL32!CompareFileTime` at `0x180052098`
- `KERNEL32!CompareFileTime` at `0x1800521ce`
- `KERNEL32!CompareFileTime` at `0x1800523b7`
- `KERNEL32!CompareFileTime` at `0x180052098`
- `KERNEL32!CompareFileTime` at `0x1800521ce`
- `KERNEL32!CompareFileTime` at `0x1800523b7`
- `KERNEL32!GetVolumePathNameW` at `0x180051c9b`
- `KERNEL32!GetVolumePathNameW` at `0x180051c9b`

## string_xrefs

- `0x1800516a1`: `base\fs\fsrm\service\pipeline\namespace.cpp`
- `0x18005187f`: `base\fs\fsrm\service\pipeline\namespace.cpp`
- `0x1800519d0`: `base\fs\fsrm\service\pipeline\namespace.cpp`
- `0x180051b3e`: `base\fs\fsrm\service\pipeline\namespace.cpp`
- `0x180051cf9`: `base\fs\fsrm\service\pipeline\namespace.cpp`
- `0x180052695`: `base\fs\fsrm\service\pipeline\namespace.cpp`
- `0x1800519a7`: `Invalid directory: %s`
- `0x180051856`: `Directory missing: %s`
- `0x1800526a9`: `GetVolumePathName`
- `0x180051b15`: `Directory cannot be opened: %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=48
void __fastcall CScanInformation::RegisterNamespaceRoots(
        CScanInformation *this,
        struct tagSAFEARRAY *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        OLECHAR *a5,
        OLECHAR *a6,
        const struct _GUID *a7,
        const struct _GUID *a8,
        enum _FsrmExecutionOption a9,
        FILETIME *a10,
        unsigned int a11,
        struct IFsrmPipelineConsumer *a12)
{
  unsigned __int16 *v12; // rdi
  CScanInformation *v14; // r13
  FILETIME *v15; // r12
  _QWORD *v16; // rax
  const char *v17; // rdx
  HRESULT LBound; // eax
  HRESULT UBound; // eax
  HRESULT v20; // eax
  HRESULT Element; // eax
  unsigned __int16 *v22; // rbx
  CSrmDebugInfo *v23; // rax
  __int64 v24; // r9
  const OLECHAR *v25; // rcx
  OLECHAR *v26; // rdi
  CSrmDebugInfo *v27; // rax
  __int64 v28; // r9
  const OLECHAR *v29; // rcx
  HANDLE FileW; // rax
  CSrmDebugInfo *v31; // rax
  __int64 v32; // r9
  const OLECHAR *v33; // rcx
  __int64 v34; // rdi
  unsigned __int16 *v35; // rsi
  BOOL VolumePathNameW; // eax
  bool v37; // dl
  OLECHAR *v38; // rdi
  struct CSrmDebugInfo *v39; // rax
  struct CSrmDebugInfo *v40; // rax
  CSrmDebugInfo *v41; // rax
  const OLECHAR *v42; // rcx
  int v43; // eax
  _QWORD *v44; // rbx
  _QWORD *i; // rsi
  _QWORD *v46; // rdx
  _QWORD *v47; // rcx
  unsigned __int64 v48; // r10
  unsigned __int64 v49; // r9
  unsigned __int64 v50; // r8
  __int64 **v51; // r11
  __int64 *j; // rdi
  _QWORD *v53; // r15
  _WORD *v54; // r8
  _QWORD *v55; // rcx
  unsigned __int64 v56; // r10
  unsigned __int64 v57; // r9
  unsigned __int64 v58; // rdx
  char v59; // r13
  const unsigned __int16 *v60; // r14
  _QWORD *v61; // r12
  const unsigned __int16 *v62; // rdx
  __int64 v63; // r8
  __int64 v64; // rcx
  __int64 v65; // rdi
  __int64 v66; // rax
  __int64 v67; // rdx
  const unsigned __int16 *v68; // rdx
  _QWORD *v69; // rdi
  __int64 v70; // r8
  _QWORD *v71; // rdi
  _QWORD *v72; // rax
  const char *v73; // rdx
  __int64 v74; // r8
  __int64 v75; // rcx
  _QWORD *v76; // rdi
  __int64 v77; // rax
  __int64 *v78; // rcx
  _QWORD **v79; // rdi
  __int64 v80; // rax
  __int64 v81; // rdx
  int Hr; // eax
  char v83; // al
  int v84; // eax
  char v85; // al
  signed int LastError; // eax
  unsigned int v87; // ebx
  __int64 v88; // rax
  char v89; // al
  int v90; // eax
  char v91; // al
  int v92; // eax
  char v93; // al
  DWORD dwCreationDisposition[2]; // [rsp+20h] [rbp-E0h]
  DWORD dwCreationDispositiona[2]; // [rsp+20h] [rbp-E0h]
  DWORD dwCreationDispositionb[2]; // [rsp+20h] [rbp-E0h]
  unsigned __int16 *v97; // [rsp+60h] [rbp-A0h] BYREF
  LPCWSTR lpFileName; // [rsp+68h] [rbp-98h] BYREF
  LONG rgIndices; // [rsp+70h] [rbp-90h] BYREF
  LONG plUbound; // [rsp+74h] [rbp-8Ch] BYREF
  LPWSTR lpszVolumePathName; // [rsp+78h] [rbp-88h] BYREF
  LONG plLbound; // [rsp+80h] [rbp-80h] BYREF
  BSTR bstrString; // [rsp+88h] [rbp-78h] BYREF
  FILETIME *lpFileTime1; // [rsp+90h] [rbp-70h]
  unsigned __int16 *v105; // [rsp+98h] [rbp-68h]
  LPVOID pv; // [rsp+A0h] [rbp-60h] BYREF
  LPVOID v107; // [rsp+A8h] [rbp-58h] BYREF
  LPVOID v108; // [rsp+B0h] [rbp-50h] BYREF
  LPVOID v109; // [rsp+B8h] [rbp-48h] BYREF
  OLECHAR *v110; // [rsp+C0h] [rbp-40h]
  OLECHAR *psz; // [rsp+C8h] [rbp-38h]
  unsigned __int16 *v112; // [rsp+D0h] [rbp-30h]
  CScanInformation *v113; // [rsp+D8h] [rbp-28h]
  const wchar_t **v114; // [rsp+E0h] [rbp-20h]
  _BYTE *v115; // [rsp+E8h] [rbp-18h]
  void **v116; // [rsp+F0h] [rbp-10h]
  VARIANTARG pvarg; // [rsp+F8h] [rbp-8h] BYREF
  void *v118[3]; // [rsp+110h] [rbp+10h] BYREF
  OLECHAR *v119; // [rsp+128h] [rbp+28h]
  OLECHAR *v120; // [rsp+130h] [rbp+30h]
  _BYTE pExceptionObject[24]; // [rsp+138h] [rbp+38h] BYREF
  _BYTE *v122; // [rsp+150h] [rbp+50h]
  _BYTE *v123; // [rsp+158h] [rbp+58h]
  _BYTE *v124; // [rsp+160h] [rbp+60h]
  _QWORD v125[3]; // [rsp+168h] [rbp+68h] BYREF
  int v126; // [rsp+180h] [rbp+80h]
  int v127; // [rsp+184h] [rbp+84h]
  int v128; // [rsp+188h] [rbp+88h]
  char v129[96]; // [rsp+190h] [rbp+90h] BYREF
  int v130; // [rsp+1F0h] [rbp+F0h]
  _QWORD v131[3]; // [rsp+1F8h] [rbp+F8h] BYREF
  int v132; // [rsp+210h] [rbp+110h]
  int v133; // [rsp+214h] [rbp+114h]
  int v134; // [rsp+218h] [rbp+118h]
  char v135[96]; // [rsp+220h] [rbp+120h] BYREF
  int v136; // [rsp+280h] [rbp+180h]
  void *Block[2]; // [rsp+290h] [rbp+190h] BYREF
  __int64 v138; // [rsp+2A0h] [rbp+1A0h]
  unsigned __int64 v139; // [rsp+2A8h] [rbp+1A8h]
  _QWORD *v140; // [rsp+2B8h] [rbp+1B8h] BYREF
  __int64 v141; // [rsp+2C0h] [rbp+1C0h]
  const wchar_t *v142; // [rsp+2D0h] [rbp+1D0h] BYREF
  const wchar_t *v143; // [rsp+2D8h] [rbp+1D8h]
  const wchar_t *v144; // [rsp+2E0h] [rbp+1E0h]
  __int64 v145; // [rsp+2E8h] [rbp+1E8h]
  int v146; // [rsp+2F0h] [rbp+1F0h]
  FILETIME FileTime2; // [rsp+2F8h] [rbp+1F8h] BYREF
  __int128 v148; // [rsp+300h] [rbp+200h] BYREF
  __int64 v149; // [rsp+310h] [rbp+210h]
  int v150; // [rsp+358h] [rbp+258h]
  void **v151; // [rsp+360h] [rbp+260h] BYREF
  HRESULT v152; // [rsp+368h] [rbp+268h]
  _QWORD v153[2]; // [rsp+410h] [rbp+310h] BYREF
  const wchar_t *v154; // [rsp+420h] [rbp+320h]
  __int64 v155; // [rsp+428h] [rbp+328h]
  int v156; // [rsp+430h] [rbp+330h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+438h] [rbp+338h] BYREF
  __int128 v158; // [rsp+440h] [rbp+340h] BYREF
  __int64 v159; // [rsp+450h] [rbp+350h]
  int v160; // [rsp+498h] [rbp+398h]
  _BYTE v161[208]; // [rsp+4A0h] [rbp+3A0h] BYREF
  _BYTE v162[208]; // [rsp+570h] [rbp+470h] BYREF
  _BYTE v163[208]; // [rsp+640h] [rbp+540h] BYREF
  void *v164[20]; // [rsp+710h] [rbp+610h] BYREF
  WCHAR szVolumeName[56]; // [rsp+7B0h] [rbp+6B0h] BYREF

  v112 = a4;
  v12 = a3;
  v105 = a3;
  v14 = this;
  v113 = this;
  v15 = a10;
  lpFileTime1 = a10;
  psz = a5;
  v110 = a6;
  v114 = &v142;
  v142 = L"base\\fs\\fsrm\\service\\pipeline\\namespace.cpp";
  v143 = L"CScanInformation::RegisterNamespaceRoots";
  v144 = L"NAMESPCC";
  v145 = 0x1600000110LL;
  v146 = 255;
  v150 = 0x1000000;
  memset_0(&FileTime2, 0, 0x60u);
  CSrmFunctionTracer::CSrmFunctionTracer((__int64)&v151, (const struct CSrmDebugInfo *)&v142, 0);
  v116 = v118;
  v118[1] = 0;
  v16 = operator new(0xB0u);
  if ( !v16 )
  {
    std::bad_alloc::bad_alloc((std::bad_alloc *)pExceptionObject, v17);
    throw (std::bad_alloc *)pExceptionObject;
  }
  v118[0] = v16;
  *v16 = v16;
  v16[1] = v16;
  plLbound = 0;
  plUbound = 0;
  VariantInit(&pvarg);
  LBound = SafeArrayGetLBound(a2, 1u, &plLbound);
  v152 = LBound;
  if ( LBound < 0 )
  {
    Hr = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v151);
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v151, Hr);
    v83 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v151);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v151, 0x126u, v83, 0);
  }
  v152 = LBound;
  UBound = SafeArrayGetUBound(a2, 1u, &plUbound);
  v152 = UBound;
  if ( UBound < 0 )
  {
    v84 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v151);
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v151, v84);
    v85 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v151);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v151, 0x127u, v85, 0);
  }
  v152 = UBound;
  rgIndices = plLbound;
  if ( plLbound <= plUbound )
  {
    while ( 1 )
    {
      v20 = VariantClear(&pvarg);
      if ( v20 < 0 )
        _com_issue_error(v20);
      Element = SafeArrayGetElement(a2, &rgIndices, &pvarg);
      v152 = Element;
      if ( Element < 0 )
      {
        v90 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v151);
        CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v151, v90);
        v91 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v151);
        CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v151, 0x12Cu, v91, 0);
      }
      v152 = Element;
      if ( pvarg.vt != 8 )
      {
        CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v151, -2147024809);
        v89 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v151);
        CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v151, 0x12Eu, v89, 0);
      }
      v152 = 0;
      lpFileName = 0;
      CSrmAutoPWSZ::CopyFrom((CSrmAutoPWSZ *)&lpFileName, pvarg.bstrVal);
      v22 = (unsigned __int16 *)lpFileName;
      SrmTrimEdgeSpace((unsigned __int16 *)lpFileName);
      LODWORD(v97) = 0;
      if ( !SrmDoesPathExist(v22, (unsigned int *)&v97) )
        break;
      if ( ((unsigned __int8)v97 & 0x10) == 0 )
      {
        CSrmFunctionTracer::Trace((CSrmFunctionTracer *)&v151, 0x8Cu, 0x154u, L"Invalid directory: %s", v22);
        v122 = v161;
        v153[0] = L"base\\fs\\fsrm\\service\\pipeline\\namespace.cpp";
        v153[1] = L"CScanInformation::RegisterNamespaceRoots";
        v154 = L"NAMESPCC";
        v155 = 0x1600000156LL;
        v156 = 255;
        v160 = 0x1000000;
        memset_0(&SystemTimeAsFileTime, 0, 0x60u);
        v27 = CSrmDebugInfo::operator<<((struct CSrmDebugInfo *)v153, (CSrmDebugInfo *)v161, v22);
        CSrmFunctionTracer::LogError(&v151, 2147754022LL, v27, 2);
        CSrmDebugInfo::~CSrmDebugInfo((CSrmDebugInfo *)v153);
        if ( !a12 )
          goto LABEL_39;
        v29 = *(const OLECHAR **)SrmFormatString(&v107, 4401, v22, v28, *(_QWORD *)dwCreationDispositiona);
        if ( v29 )
        {
          v26 = SysAllocString(v29);
          v120 = v26;
          if ( !v26 )
          {
            LODWORD(v97) = -2147024882;
            throw (long *)&v97;
          }
        }
        else
        {
          v26 = 0;
          v120 = 0;
        }
        CoTaskMemFree(v107);
        v107 = 0;
        (*(void (__fastcall **)(struct IFsrmPipelineConsumer *, OLECHAR *))(*(_QWORD *)a12 + 112LL))(a12, v26);
        goto LABEL_15;
      }
      FileW = CreateFileW(v22, 0, 7u, 0, 3u, 0x2000000u, 0);
      if ( FileW != (HANDLE)-1LL )
      {
        CloseHandle(FileW);
        v97 = 0;
        SrmGetVolumeNameForPathName(v22, szVolumeName, 0x32u, 0, &v97);
        lpszVolumePathName = 0;
        v34 = -1;
        do
          ++v34;
        while ( v22[v34] );
        CSrmAutoPWSZ::Allocate((CSrmAutoPWSZ *)&lpszVolumePathName, v34 + 1);
        v35 = lpszVolumePathName;
        VolumePathNameW = GetVolumePathNameW(v22, lpszVolumePathName, v34 + 2);
        v38 = 0;
        if ( !VolumePathNameW )
        {
          LastError = GetLastError();
          if ( LastError > 0 )
            LastError = (unsigned __int16)LastError | 0x80070000;
          CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v151, LastError);
          v87 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v151);
          v115 = v162;
          v88 = CSrmDebugInfo::CSrmDebugInfo(
                  (__int64)v162,
                  (__int64)L"base\\fs\\fsrm\\service\\pipeline\\namespace.cpp",
                  (__int64)L"NAMESPCC",
                  (__int64)L"CScanInformation::RegisterNamespaceRoots",
                  409,
                  22);
          CSrmFunctionTracer::TranslatePathError(&v151, v88, v87, L"GetVolumePathName");
        }
        if ( SrmIsVolumeValid(szVolumeName, v37) )
        {
          CVolumePathInfo::CVolumePathInfo((CVolumePathInfo *)v164, pvarg.bstrVal, v97, szVolumeName, v35);
          CVolumePathInfoMapper::AppendVolumesForPath((CVolumePathInfoMapper *)v118, (struct CVolumePathInfo *)v164);
          CVolumePathInfo::~CVolumePathInfo(v164);
        }
        else
        {
          CSrmFunctionTracer::Trace(
            (CSrmFunctionTracer *)&v151,
            0x8Cu,
            0x1A1u,
            L"Invalid volume: %s (%s)",
            v35,
            szVolumeName);
          v115 = v161;
          v131[0] = L"base\\fs\\fsrm\\service\\pipeline\\namespace.cpp";
          v131[1] = L"CScanInformation::RegisterNamespaceRoots";
          v131[2] = L"NAMESPCC";
          v132 = 419;
          v133 = 22;
          v134 = 255;
          v136 = 0x1000000;
          memset_0(v135, 0, sizeof(v135));
          v39 = CSrmDebugInfo::operator<<((struct CSrmDebugInfo *)v131, (CSrmDebugInfo *)v162, v35);
          v40 = CSrmDebugInfo::operator<<(v39, (CSrmDebugInfo *)v163, szVolumeName);
          v41 = CSrmDebugInfo::operator<<(v40, (CSrmDebugInfo *)v161, v22);
          CSrmFunctionTracer::LogError(&v151, 2147754023LL, v41, 2);
          CSrmDebugInfo::~CSrmDebugInfo((CSrmDebugInfo *)v163);
          CSrmDebugInfo::~CSrmDebugInfo((CSrmDebugInfo *)v162);
          CSrmDebugInfo::~CSrmDebugInfo((CSrmDebugInfo *)v131);
          if ( a12 )
          {
            v42 = *(const OLECHAR **)SrmFormatString(&v109, 4403, v35, szVolumeName, v22);
            if ( v42 )
            {
              v38 = SysAllocString(v42);
              v114 = (const wchar_t **)v38;
              if ( !v38 )
              {
                LODWORD(v97) = -2147024882;
                throw (long *)&v97;
              }
            }
            else
            {
              v114 = 0;
            }
            CoTaskMemFree(v109);
            v109 = 0;
            (*(void (__fastcall **)(struct IFsrmPipelineConsumer *, OLECHAR *))(*(_QWORD *)a12 + 112LL))(a12, v38);
            SysFreeString(v38);
          }
        }
        CoTaskMemFree(v35);
        lpszVolumePathName = 0;
        goto LABEL_39;
      }
      CSrmFunctionTracer::Trace((CSrmFunctionTracer *)&v151, 0x8Cu, 0x173u, L"Directory cannot be opened: %s", v22);
      v123 = v161;
      v125[0] = L"base\\fs\\fsrm\\service\\pipeline\\namespace.cpp";
      v125[1] = L"CScanInformation::RegisterNamespaceRoots";
      v125[2] = L"NAMESPCC";
      v126 = 373;
      v127 = 22;
      v128 = 255;
      v130 = 0x1000000;
      memset_0(v129, 0, sizeof(v129));
      v31 = CSrmDebugInfo::operator<<((struct CSrmDebugInfo *)v125, (CSrmDebugInfo *)v161, v22);
      CSrmFunctionTracer::LogError(&v151, 2147754019LL, v31, 2);
      CSrmDebugInfo::~CSrmDebugInfo((CSrmDebugInfo *)v125);
      if ( a12 )
      {
        v33 = *(const OLECHAR **)SrmFormatString(&v108, 4402, v22, v32, *(_QWORD *)dwCreationDispositionb);
        if ( v33 )
        {
          v26 = SysAllocString(v33);
          v116 = (void **)v26;
          if ( !v26 )
          {
            LODWORD(v97) = -2147024882;
            throw (long *)&v97;
          }
        }
        else
        {
          v26 = 0;
          v116 = 0;
        }
        CoTaskMemFree(v108);
        v108 = 0;
        (*(void (__fastcall **)(struct IFsrmPipelineConsumer *, OLECHAR *))(*(_QWORD *)a12 + 112LL))(a12, v26);
LABEL_15:
        SysFreeString(v26);
      }
LABEL_39:
      CoTaskMemFree(v22);
      lpFileName = 0;
      if ( ++rgIndices > plUbound )
      {
        v12 = v105;
        goto LABEL_41;
      }
    }
    if ( CFsrmClusterUtil::IsInCluster(1, 0) )
      goto LABEL_39;
    CSrmFunctionTracer::Trace((CSrmFunctionTracer *)&v151, 0x8Cu, 0x13Fu, L"Directory missing: %s", v22);
    v124 = v161;
    v142 = L"base\\fs\\fsrm\\service\\pipeline\\namespace.cpp";
    v143 = L"CScanInformation::RegisterNamespaceRoots";
    v144 = L"NAMESPCC";
    v145 = 0x1600000141LL;
    v146 = 255;
    v150 = 0x1000000;
    memset_0(&FileTime2, 0, 0x60u);
    v23 = CSrmDebugInfo::operator<<((struct CSrmDebugInfo *)&v142, (CSrmDebugInfo *)v161, v22);
    CSrmFunctionTracer::LogError(&v151, 2147754021LL, v23, 2);
    CSrmDebugInfo::~CSrmDebugInfo((CSrmDebugInfo *)&v142);
    if ( !a12 )
      goto LABEL_39;
    v25 = *(const OLECHAR **)SrmFormatString(&pv, 4400, v22, v24, *(_QWORD *)dwCreationDisposition);
    if ( v25 )
    {
      v26 = SysAllocString(v25);
      v119 = v26;
      if ( !v26 )
      {
        LODWORD(v97) = -2147024882;
        throw (long *)&v97;
      }
    }
    else
    {
      v26 = 0;
      v119 = 0;
    }
    CoTaskMemFree(pv);
    pv = 0;
    (*(void (__fastcall **)(struct IFsrmPipelineConsumer *, OLECHAR *))(*(_QWORD *)a12 + 112LL))(a12, v26);
    goto LABEL_15;
  }
LABEL_41:
  bstrString = 0;
  if ( a12 )
  {
    v43 = (*(__int64 (__fastcall **)(struct IFsrmPipelineConsumer *, BSTR *))(*(_QWORD *)a12 + 56LL))(a12, &bstrString);
    v152 = v43;
    if ( v43 < 0 )
    {
      v92 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v151);
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v151, v92);
      v93 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v151);
      CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v151, 0x1C5u, v93, 0);
    }
    v152 = v43;
  }
  v44 = v118[0];
LABEL_45:
  v44 = (_QWORD *)*v44;
  if ( v44 != v118[0] )
  {
    for ( i = **(_QWORD ***)v14; ; i = (_QWORD *)*i )
    {
      if ( i == *(_QWORD **)v14 )
      {
        v68 = (const unsigned __int16 *)(v44 + 17);
        if ( v44[20] >= 8u )
          v68 = *(const unsigned __int16 **)v68;
        CNamespaceContext::CNamespaceContext(
          (CNamespaceContext *)v161,
          v68,
          v12,
          v112,
          psz,
          v110,
          a7,
          a8,
          a9,
          a11,
          bstrString);
        v69 = v44 + 7;
        if ( v44[10] >= 8u )
          v69 = (_QWORD *)*v69;
        v145 = 7;
        v144 = 0;
        LOWORD(v142) = 0;
        GetSystemTimeAsFileTime(&FileTime2);
        v148 = 0;
        v149 = 0;
        v70 = -1;
        do
          ++v70;
        while ( *((_WORD *)v69 + v70) );
        std::wstring::assign(&v142, v69);
        FileTime2 = 0;
        v71 = v44 + 12;
        if ( v44[15] >= 8u )
          v71 = (_QWORD *)*v71;
        v139 = 7;
        v138 = 0;
        LOWORD(Block[0]) = 0;
        v115 = &v140;
        v141 = 0;
        v72 = operator new(0x60u);
        if ( !v72 )
        {
          std::bad_alloc::bad_alloc((std::bad_alloc *)pExceptionObject, v73);
          throw (std::bad_alloc *)pExceptionObject;
        }
        v140 = v72;
        *v72 = v72;
        v72[1] = v72;
        v74 = -1;
        do
          ++v74;
        while ( *((_WORD *)v71 + v74) );
        std::wstring::assign(Block, v71);
        std::vector<CNamespaceContext>::push_back(&v148, v161);
        if ( CompareFileTime(v15, &FileTime2) == 1 )
          FileTime2 = *v15;
        v76 = v140;
        v77 = std::_List_val<CVolumeNamespaceRoot>::_Buynode(v75, v140, v140[1], &v142);
        if ( v141 == 0x333333333333332LL
          || (++v141,
              v76[1] = v77,
              v78 = *(__int64 **)(v77 + 8),
              *v78 = v77,
              v79 = *(_QWORD ***)v14,
              v80 = std::_List_val<CVolumeNamespaces>::_Buynode(
                      v78,
                      *(_QWORD *)v14,
                      *(_QWORD *)(*(_QWORD *)v14 + 8LL),
                      Block),
              v81 = *((_QWORD *)v14 + 1),
              v81 == 0x3FFFFFFFFFFFFFELL) )
        {
          std::_Xlength_error("list<T> too long");
        }
        *((_QWORD *)v14 + 1) = v81 + 1;
        v79[1] = (_QWORD *)v80;
        **(_QWORD **)(v80 + 8) = v80;
        std::list<CVolumeNamespaceRoot>::~list<CVolumeNamespaceRoot>(&v140);
        if ( v139 >= 8 )
          operator delete(Block[0]);
        v139 = 7;
        v138 = 0;
        LOWORD(Block[0]) = 0;
        CVolumeNamespaceRoot::~CVolumeNamespaceRoot((CVolumeNamespaceRoot *)&v142);
        CNamespaceContext::~CNamespaceContext((CNamespaceContext *)v161);
        goto LABEL_113;
      }
      v46 = v44 + 12;
      if ( v44[15] >= 8u )
        v46 = (_QWORD *)*v46;
      v47 = i + 2;
      v48 = v44[14];
      v49 = i[4];
      v50 = v49;
      if ( v49 >= v48 )
        v50 = v44[14];
      if ( i[5] >= 8u )
        v47 = (_QWORD *)*v47;
      if ( v50 )
      {
        while ( *(_WORD *)v47 == *(_WORD *)v46 )
        {
          v47 = (_QWORD *)((char *)v47 + 2);
          v46 = (_QWORD *)((char *)v46 + 2);
          if ( !--v50 )
            goto LABEL_57;
        }
      }
      else
      {
LABEL_57:
        if ( v49 >= v48 && v49 == v48 )
        {
          v51 = (__int64 **)i[7];
          for ( j = *v51; ; j = (__int64 *)*j )
          {
            v53 = v44 + 7;
            if ( j == (__int64 *)v51 )
            {
              v59 = 0;
              v60 = (const unsigned __int16 *)(v44 + 17);
              v61 = v44 + 20;
              goto LABEL_82;
            }
            if ( v44[10] < 8u )
              v54 = v44 + 7;
            else
              v54 = (_WORD *)*v53;
            v55 = j + 2;
            v56 = v44[9];
            v57 = j[4];
            v58 = v57;
            if ( v57 >= v56 )
              v58 = v44[9];
            if ( (unsigned __int64)j[5] >= 8 )
              v55 = (_QWORD *)*v55;
            if ( v58 )
            {
              while ( *(_WORD *)v55 == *v54 )
              {
                v55 = (_QWORD *)((char *)v55 + 2);
                ++v54;
                if ( !--v58 )
                  goto LABEL_72;
              }
            }
            else
            {
LABEL_72:
              if ( v57 >= v56 && v57 == v56 )
              {
                v59 = 1;
                v60 = (const unsigned __int16 *)(v44 + 17);
                v61 = v44 + 20;
                if ( v44[20] < 8u )
                  v62 = (const unsigned __int16 *)(v44 + 17);
                else
                  v62 = *(const unsigned __int16 **)v60;
                CNamespaceContext::CNamespaceContext(
                  (CNamespaceContext *)v162,
                  v62,
                  v105,
                  v112,
                  psz,
                  v110,
                  a7,
                  a8,
                  a9,
                  a11,
                  bstrString);
                std::vector<CNamespaceContext>::push_back(j + 8, v162);
                if ( CompareFileTime(lpFileTime1, (const FILETIME *)j + 7) == 1 )
                  j[7] = (__int64)*lpFileTime1;
                CNamespaceContext::~CNamespaceContext((CNamespaceContext *)v162);
LABEL_82:
                if ( v59 )
                {
                  v15 = lpFileTime1;
                }
                else
                {
                  if ( *v61 >= 8u )
                    v60 = *(const unsigned __int16 **)v60;
                  CNamespaceContext::CNamespaceContext(
                    (CNamespaceContext *)v163,
                    v60,
                    v105,
                    v112,
                    psz,
                    v110,
                    a7,
                    a8,
                    a9,
                    a11,
                    bstrString);
                  if ( v44[10] >= 8u )
                    v53 = (_QWORD *)*v53;
                  v155 = 7;
                  v154 = 0;
                  LOWORD(v153[0]) = 0;
                  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
                  v158 = 0;
                  v159 = 0;
                  v63 = -1;
                  do
                    ++v63;
                  while ( *((_WORD *)v53 + v63) );
                  std::wstring::assign(v153, v53);
                  SystemTimeAsFileTime = 0;
                  std::vector<CNamespaceContext>::push_back(&v158, v163);
                  v15 = lpFileTime1;
                  if ( CompareFileTime(lpFileTime1, &SystemTimeAsFileTime) == 1 )
                    SystemTimeAsFileTime = *v15;
                  v65 = i[7];
                  v66 = std::_List_val<CVolumeNamespaceRoot>::_Buynode(v64, v65, *(_QWORD *)(v65 + 8), v153);
                  v67 = i[8];
                  if ( v67 == 0x333333333333332LL )
                    std::_Xlength_error("list<T> too long");
                  i[8] = v67 + 1;
                  *(_QWORD *)(v65 + 8) = v66;
                  **(_QWORD **)(v66 + 8) = v66;
                  CVolumeNamespaceRoot::~CVolumeNamespaceRoot((CVolumeNamespaceRoot *)v153);
                  CNamespaceContext::~CNamespaceContext((CNamespaceContext *)v163);
                }
                v14 = v113;
LABEL_113:
                v12 = v105;
                goto LABEL_45;
              }
            }
          }
        }
      }
    }
  }
  SysFreeString(bstrString);
  _variant_t::~_variant_t(&pvarg);
  std::list<CVolumePathInfo>::~list<CVolumePathInfo>(v118);
  v151 = &CSrmFunctionTracer::`vftable';
  CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)&v151);
}

```

## disassembly

```asm
0x18005162c  push    rbp
0x18005162e  push    rbx
0x18005162f  push    rsi
0x180051630  push    rdi
0x180051631  push    r12
0x180051633  push    r13
0x180051635  push    r14
0x180051637  push    r15
0x180051639  lea     rbp, [rsp-738h]
0x180051641  sub     rsp, 838h
0x180051648  mov     rax, cs:__security_cookie
0x18005164f  xor     rax, rsp
0x180051652  mov     [rbp+770h+var_50], rax
0x180051659  mov     [rbp+770h+var_7A0], r9
0x18005165d  mov     rdi, r8
0x180051660  mov     [rbp+770h+var_7D8], r8
0x180051664  mov     r15, rdx
0x180051667  mov     r13, rcx
0x18005166a  mov     [rbp+770h+var_798], rcx
0x18005166e  mov     r12, [rbp+770h+arg_48]
0x180051675  mov     [rbp+770h+lpFileTime1], r12
0x180051679  mov     rax, [rbp+770h+arg_20]
0x180051680  mov     [rbp+770h+psz], rax
0x180051684  mov     rax, [rbp+770h+arg_28]
0x18005168b  mov     [rbp+770h+var_7B0], rax
0x18005168f  mov     r14, [rbp+770h+arg_58]
0x180051696  lea     rax, [rbp+770h+var_5A0]
0x18005169d  mov     [rbp+770h+var_790], rax
0x1800516a1  lea     rax, aBaseFsFsrmServ_34; "base\\fs\\fsrm\\service\\pipeline\\name"...
0x1800516a8  mov     [rbp+770h+var_5A0], rax
0x1800516af  lea     rax, aCscaninformati_4; "CScanInformation::RegisterNamespaceRoot"...
0x1800516b6  mov     [rbp+770h+var_598], rax
0x1800516bd  lea     rax, aNamespcc; "NAMESPCC"
0x1800516c4  mov     [rbp+770h+var_590], rax
0x1800516cb  mov     dword ptr [rbp+770h+var_588], 110h
0x1800516d5  mov     dword ptr [rbp+770h+var_588+4], 16h
0x1800516df  mov     [rbp+770h+var_580], 0FFh
0x1800516e9  xor     esi, esi
0x1800516eb  mov     [rbp+770h+var_518], 1000000h
0x1800516f5  xor     edx, edx; Val
0x1800516f7  lea     r8d, [rsi+60h]; Size
0x1800516fb  lea     rcx, [rbp+770h+FileTime2]; void *
0x180051702  call    memset_0
0x180051707  nop
0x180051708  xor     r8d, r8d
0x18005170b  lea     rdx, [rbp+770h+var_5A0]
0x180051712  lea     rcx, [rbp+770h+var_510]
0x180051719  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x18005171e  nop
0x18005171f  lea     rax, [rbp+770h+var_760]
0x180051723  mov     [rbp+770h+var_780], rax
0x180051727  mov     [rbp+770h+var_758], rsi
0x18005172b  mov     ecx, 0B0h; Size
0x180051730  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180051735  test    rax, rax
0x180051738  jz      loc_180052540
0x18005173e  mov     [rbp+770h+var_760], rax
0x180051742  mov     [rax], rax
0x180051745  mov     [rax+8], rax
0x180051749  mov     [rbp+770h+plLbound], esi
0x18005174c  mov     [rsp+870h+plUbound], esi
0x180051750  lea     rcx, [rbp+770h+pvarg]; pvarg
0x180051754  call    cs:__imp_VariantInit
0x18005175a  nop
0x18005175b  lea     r8, [rbp+770h+plLbound]; plLbound
0x18005175f  lea     edx, [rsi+1]; nDim
0x180051762  mov     rcx, r15; psa
0x180051765  call    cs:__imp_SafeArrayGetLBound
0x18005176b  mov     [rbp+770h+var_508], eax
0x180051771  test    eax, eax
0x180051773  js      loc_18005255A
0x180051779  mov     [rbp+770h+var_508], eax
0x18005177f  lea     r8, [rsp+870h+plUbound]; plUbound
0x180051784  lea     edx, [rsi+1]; nDim
0x180051787  mov     rcx, r15; psa
0x18005178a  call    cs:__imp_SafeArrayGetUBound
0x180051790  mov     [rbp+770h+var_508], eax
0x180051796  test    eax, eax
0x180051798  js      loc_180052598
0x18005179e  mov     [rbp+770h+var_508], eax
0x1800517a4  mov     eax, [rbp+770h+plLbound]
0x1800517a7  mov     [rsp+870h+rgIndices], eax
0x1800517ab  lea     ebx, [rsi+8]
0x1800517ae  cmp     eax, [rsp+870h+plUbound]
0x1800517b2  jg      loc_180051EE7
0x1800517b8  lea     rcx, [rbp+770h+pvarg]; pvarg
0x1800517bc  call    cs:__imp_VariantClear
0x1800517c2  test    eax, eax
0x1800517c4  js      loc_180052736
0x1800517ca  lea     r8, [rbp+770h+pvarg]; pv
0x1800517ce  lea     rdx, [rsp+870h+rgIndices]; rgIndices
0x1800517d3  mov     rcx, r15; psa
0x1800517d6  call    cs:__imp_SafeArrayGetElement
0x1800517dc  mov     [rbp+770h+var_508], eax
0x1800517e2  test    eax, eax
0x1800517e4  js      loc_1800526F8
0x1800517ea  mov     [rbp+770h+var_508], eax
0x1800517f0  mov     [rbp+770h+var_508], eax
0x1800517f6  cmp     bx, word ptr [rbp+770h+pvarg]
0x1800517fa  jnz     loc_1800526C3
0x180051800  mov     [rbp+770h+var_508], esi
0x180051806  mov     [rsp+870h+lpFileName], rsi
0x18005180b  mov     rdx, qword ptr [rbp+770h+pvarg+8]; unsigned __int16 *
0x18005180f  lea     rcx, [rsp+870h+lpFileName]; this
0x180051814  call    ?CopyFrom@CSrmAutoPWSZ@@QEAAXPEBG@Z; CSrmAutoPWSZ::CopyFrom(ushort const *)
0x180051819  mov     rbx, [rsp+870h+lpFileName]
0x18005181e  mov     rcx, rbx; unsigned __int16 *
0x180051821  call    ?SrmTrimEdgeSpace@@YAXPEAG@Z; SrmTrimEdgeSpace(ushort *)
0x180051826  mov     dword ptr [rsp+870h+var_810], esi
0x18005182a  lea     rdx, [rsp+870h+var_810]; unsigned int *
0x18005182f  mov     rcx, rbx; unsigned __int16 *
0x180051832  call    ?SrmDoesPathExist@@YA_NPEBGPEAK@Z; SrmDoesPathExist(ushort const *,ulong *)
0x180051837  test    al, al
0x180051839  jnz     loc_180051997
0x18005183f  xor     edx, edx; int
0x180051841  lea     ecx, [rdx+1]; int
0x180051844  call    ?IsInCluster@CFsrmClusterUtil@@SA_NHH@Z; CFsrmClusterUtil::IsInCluster(int,int)
0x180051849  test    al, al
0x18005184b  jnz     loc_180051EB6
0x180051851  mov     qword ptr [rsp+870h+dwCreationDisposition], rbx
0x180051856  lea     r9, aDirectoryMissi; "Directory missing: %s"
0x18005185d  mov     edx, 8Ch; unsigned int
0x180051862  mov     r8d, 13Fh; unsigned int
0x180051868  lea     rcx, [rbp+770h+var_510]; this
0x18005186f  call    ?Trace@CSrmFunctionTracer@@QEAAXKKPEBGZZ; CSrmFunctionTracer::Trace(ulong,ulong,ushort const *,...)
0x180051874  lea     rax, [rbp+770h+var_3D0]
0x18005187b  mov     [rbp+770h+var_710], rax
0x18005187f  lea     rax, aBaseFsFsrmServ_34; "base\\fs\\fsrm\\service\\pipeline\\name"...
0x180051886  mov     [rbp+770h+var_5A0], rax
0x18005188d  lea     rax, aCscaninformati_4; "CScanInformation::RegisterNamespaceRoot"...
0x180051894  mov     [rbp+770h+var_598], rax
0x18005189b  lea     rax, aNamespcc; "NAMESPCC"
0x1800518a2  mov     [rbp+770h+var_590], rax
0x1800518a9  mov     dword ptr [rbp+770h+var_588], 141h
0x1800518b3  mov     dword ptr [rbp+770h+var_588+4], 16h
0x1800518bd  mov     [rbp+770h+var_580], 0FFh
0x1800518c7  mov     [rbp+770h+var_518], 1000000h
0x1800518d1  xor     edx, edx; Val
0x1800518d3  lea     r8d, [rdx+60h]; Size
0x1800518d7  lea     rcx, [rbp+770h+FileTime2]; void *
0x1800518de  call    memset_0
0x1800518e3  nop
0x1800518e4  mov     r8, rbx; unsigned __int16 *
0x1800518e7  lea     rdx, [rbp+770h+var_3D0]; this
0x1800518ee  lea     rcx, [rbp+770h+var_5A0]; struct CSrmDebugInfo *
0x1800518f5  call    ??6CSrmDebugInfo@@QEAA?AU0@PEBG@Z; CSrmDebugInfo::operator<<(ushort const *)
0x1800518fa  nop
0x1800518fb  mov     r9d, 2
0x180051901  mov     r8, rax
0x180051904  mov     edx, 80042025h
0x180051909  lea     rcx, [rbp+770h+var_510]
0x180051910  call    ?LogError@CSrmFunctionTracer@@QEAAXKUCSrmDebugInfo@@G@Z; CSrmFunctionTracer::LogError(ulong,CSrmDebugInfo,ushort)
0x180051915  nop
0x180051916  lea     rcx, [rbp+770h+var_5A0]; this
0x18005191d  call    ??1CSrmDebugInfo@@QEAA@XZ; CSrmDebugInfo::~CSrmDebugInfo(void)
0x180051922  test    r14, r14
0x180051925  jz      loc_180051EB6
0x18005192b  mov     r8, rbx
0x18005192e  mov     edx, 1130h
0x180051933  lea     rcx, [rbp+770h+pv]
0x180051937  call    ?SrmFormatString@@YA?AVCSrmAutoPWSZ@@IZZ; SrmFormatString(uint,...)
0x18005193c  nop
0x18005193d  mov     rcx, [rax]; psz
0x180051940  test    rcx, rcx
0x180051943  jnz     short loc_18005194E
0x180051945  mov     rdi, rsi
0x180051948  mov     [rbp+770h+var_748], rsi
0x18005194c  jmp     short loc_180051964
0x18005194e  call    cs:__imp_SysAllocString
0x180051954  mov     rdi, rax
0x180051957  mov     [rbp+770h+var_748], rax
0x18005195b  test    rax, rax
0x18005195e  jz      loc_1800525D6
0x180051964  mov     rcx, [rbp+770h+pv]; pv
0x180051968  call    cs:__imp_CoTaskMemFree
0x18005196e  mov     [rbp+770h+pv], rsi
0x180051972  mov     [rbp+770h+pv], rsi
0x180051976  mov     rax, [r14]
0x180051979  mov     rdx, rdi
0x18005197c  mov     rcx, r14
0x18005197f  mov     rax, [rax+70h]
0x180051983  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051988  nop
0x180051989  mov     rcx, rdi; bstrString
0x18005198c  call    cs:__imp_SysFreeString
0x180051992  jmp     loc_180051EB6
0x180051997  test    byte ptr [rsp+870h+var_810], 10h
0x18005199c  jnz     loc_180051ADF
0x1800519a2  mov     qword ptr [rsp+870h+dwCreationDisposition], rbx
0x1800519a7  lea     r9, aInvalidDirecto; "Invalid directory: %s"
0x1800519ae  mov     edx, 8Ch; unsigned int
0x1800519b3  mov     r8d, 154h; unsigned int
0x1800519b9  lea     rcx, [rbp+770h+var_510]; this
0x1800519c0  call    ?Trace@CSrmFunctionTracer@@QEAAXKKPEBGZZ; CSrmFunctionTracer::Trace(ulong,ulong,ushort const *,...)
0x1800519c5  lea     rax, [rbp+770h+var_3D0]
0x1800519cc  mov     [rbp+770h+var_720], rax
0x1800519d0  lea     rax, aBaseFsFsrmServ_34; "base\\fs\\fsrm\\service\\pipeline\\name"...
0x1800519d7  mov     [rbp+770h+var_460], rax
0x1800519de  lea     rax, aCscaninformati_4; "CScanInformation::RegisterNamespaceRoot"...
0x1800519e5  mov     [rbp+770h+var_458], rax
0x1800519ec  lea     rax, aNamespcc; "NAMESPCC"
0x1800519f3  mov     [rbp+770h+var_450], rax
0x1800519fa  mov     dword ptr [rbp+770h+var_448], 156h
0x180051a04  mov     dword ptr [rbp+770h+var_448+4], 16h
0x180051a0e  mov     [rbp+770h+var_440], 0FFh
0x180051a18  mov     [rbp+770h+var_3D8], 1000000h
0x180051a22  xor     edx, edx; Val
0x180051a24  lea     r8d, [rdx+60h]; Size
0x180051a28  lea     rcx, [rbp+770h+SystemTimeAsFileTime]; void *
0x180051a2f  call    memset_0
0x180051a34  nop
0x180051a35  mov     r8, rbx; unsigned __int16 *
0x180051a38  lea     rdx, [rbp+770h+var_3D0]; this
0x180051a3f  lea     rcx, [rbp+770h+var_460]; struct CSrmDebugInfo *
0x180051a46  call    ??6CSrmDebugInfo@@QEAA?AU0@PEBG@Z; CSrmDebugInfo::operator<<(ushort const *)
0x180051a4b  nop
0x180051a4c  mov     r9d, 2
0x180051a52  mov     r8, rax
0x180051a55  mov     edx, 80042026h
0x180051a5a  lea     rcx, [rbp+770h+var_510]
0x180051a61  call    ?LogError@CSrmFunctionTracer@@QEAAXKUCSrmDebugInfo@@G@Z; CSrmFunctionTracer::LogError(ulong,CSrmDebugInfo,ushort)
0x180051a66  nop
0x180051a67  lea     rcx, [rbp+770h+var_460]; this
0x180051a6e  call    ??1CSrmDebugInfo@@QEAA@XZ; CSrmDebugInfo::~CSrmDebugInfo(void)
0x180051a73  test    r14, r14
0x180051a76  jz      loc_180051EB6
0x180051a7c  mov     r8, rbx
0x180051a7f  mov     edx, 1131h
0x180051a84  lea     rcx, [rbp+770h+var_7C8]
0x180051a88  call    ?SrmFormatString@@YA?AVCSrmAutoPWSZ@@IZZ; SrmFormatString(uint,...)
0x180051a8d  nop
0x180051a8e  mov     rcx, [rax]; psz
0x180051a91  test    rcx, rcx
0x180051a94  jnz     short loc_180051A9F
0x180051a96  mov     rdi, rsi
0x180051a99  mov     [rbp+770h+var_740], rsi
0x180051a9d  jmp     short loc_180051AB5
0x180051a9f  call    cs:__imp_SysAllocString
0x180051aa5  mov     rdi, rax
0x180051aa8  mov     [rbp+770h+var_740], rax
0x180051aac  test    rax, rax
0x180051aaf  jz      loc_1800525F0
0x180051ab5  mov     rcx, [rbp+770h+var_7C8]; pv
0x180051ab9  call    cs:__imp_CoTaskMemFree
0x180051abf  mov     [rbp+770h+var_7C8], rsi
0x180051ac3  mov     [rbp+770h+var_7C8], rsi
0x180051ac7  mov     rax, [r14]
0x180051aca  mov     rdx, rdi
0x180051acd  mov     rcx, r14
0x180051ad0  mov     rax, [rax+70h]
0x180051ad4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051ad9  nop
0x180051ada  jmp     loc_180051989
0x180051adf  mov     [rsp+870h+hTemplateFile], rsi; hTemplateFile
0x180051ae4  mov     [rsp+870h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x180051aec  mov     [rsp+870h+dwCreationDisposition], 3; dwCreationDisposition
0x180051af4  xor     r9d, r9d; lpSecurityAttributes
0x180051af7  xor     edx, edx; dwDesiredAccess
0x180051af9  lea     r8d, [r9+7]; dwShareMode
0x180051afd  mov     rcx, rbx; lpFileName
0x180051b00  call    cs:__imp_CreateFileW
0x180051b06  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180051b0a  jnz     loc_180051C3E
0x180051b10  mov     qword ptr [rsp+870h+dwCreationDisposition], rbx
0x180051b15  lea     r9, aDirectoryCanno; "Directory cannot be opened: %s"
0x180051b1c  mov     edx, 8Ch; unsigned int
0x180051b21  mov     r8d, 173h; unsigned int
0x180051b27  lea     rcx, [rbp+770h+var_510]; this
0x180051b2e  call    ?Trace@CSrmFunctionTracer@@QEAAXKKPEBGZZ; CSrmFunctionTracer::Trace(ulong,ulong,ushort const *,...)
0x180051b33  lea     rax, [rbp+770h+var_3D0]
0x180051b3a  mov     [rbp+770h+var_718], rax
0x180051b3e  lea     rax, aBaseFsFsrmServ_34; "base\\fs\\fsrm\\service\\pipeline\\name"...
0x180051b45  mov     [rbp+770h+var_708], rax
0x180051b49  lea     rax, aCscaninformati_4; "CScanInformation::RegisterNamespaceRoot"...
0x180051b50  mov     [rbp+770h+var_700], rax
0x180051b54  lea     rax, aNamespcc; "NAMESPCC"
0x180051b5b  mov     [rbp+770h+var_6F8], rax
0x180051b5f  mov     [rbp+770h+var_6F0], 175h
0x180051b69  mov     [rbp+770h+var_6EC], 16h
0x180051b73  mov     [rbp+770h+var_6E8], 0FFh
0x180051b7d  mov     [rbp+770h+var_680], 1000000h
0x180051b87  xor     edx, edx; Val
0x180051b89  lea     r8d, [rdx+60h]; Size
0x180051b8d  lea     rcx, [rbp+770h+var_6E0]; void *
0x180051b94  call    memset_0
0x180051b99  nop
0x180051b9a  mov     r8, rbx; unsigned __int16 *
0x180051b9d  lea     rdx, [rbp+770h+var_3D0]; this
0x180051ba4  lea     rcx, [rbp+770h+var_708]; struct CSrmDebugInfo *
0x180051ba8  call    ??6CSrmDebugInfo@@QEAA?AU0@PEBG@Z; CSrmDebugInfo::operator<<(ushort const *)
0x180051bad  nop
0x180051bae  mov     r9d, 2
0x180051bb4  mov     r8, rax
0x180051bb7  mov     edx, 80042023h
0x180051bbc  lea     rcx, [rbp+770h+var_510]
0x180051bc3  call    ?LogError@CSrmFunctionTracer@@QEAAXKUCSrmDebugInfo@@G@Z; CSrmFunctionTracer::LogError(ulong,CSrmDebugInfo,ushort)
0x180051bc8  nop
0x180051bc9  lea     rcx, [rbp+770h+var_708]; this
0x180051bcd  call    ??1CSrmDebugInfo@@QEAA@XZ; CSrmDebugInfo::~CSrmDebugInfo(void)
0x180051bd2  test    r14, r14
  ... truncated ...
```
