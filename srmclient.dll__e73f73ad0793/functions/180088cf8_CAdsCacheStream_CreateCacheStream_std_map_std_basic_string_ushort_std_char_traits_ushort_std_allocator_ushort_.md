# CAdsCacheStream::CreateCacheStream(std::map<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,ATL::CAdapt<CSrmRefPtr<CSerializedPropertyDefinition>>,CCaseInsensitiveLess<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,ATL::CAdapt<CSrmRefPtr<CSerializedPropertyDefinition>>>>> const *,ulong)

- ea: `0x180088cf8`
- end: `0x180089a24`
- name: `?CreateCacheStream@CAdsCacheStream@@QEAA_NPEBV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$CAdapt@V?$CSrmRefPtr@VCSerializedPropertyDefinition@@@@@ATL@@U?$CCaseInsensitiveLess@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$CAdapt@V?$CSrmRefPtr@VCSerializedPropertyDefinition@@@@@ATL@@@std@@@2@@std@@K@Z`
- size: `3372`
- prototype: `__int64 __fastcall(CAdsCacheStream *this)`
- caller_count: `1`
- callee_count: `30`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180047c30`

## callees

- `0x180001350`
- `0x180006a1c`
- `0x1800095f4`
- `0x18000eef4`
- `0x18001a184`
- `0x18003ff90`
- `0x18004ce20`
- `0x18004d628`
- `0x18005ac64`
- `0x18006fe68`
- `0x18006febc`
- `0x1800700b8`
- `0x180073a80`
- `0x180073d04`
- `0x180073f54`
- `0x180075448`
- `0x18007c000`
- `0x180084bc4`
- `0x180085a24`
- `0x180088834`
- `0x1800889d4`
- `0x180088b50`
- `0x180088cf8`
- `0x180089d38`
- `0x1800a3574`
- `0x1800a36c0`
- `0x1800a3888`
- `0x1800b078a`
- `0x1800b07d0`
- `0x1800d5010`

## import_xrefs

- `msvcrt!wcschr` at `0x18008934c`
- `msvcrt!wcschr` at `0x18008934c`
- `ntdll!RtlNtStatusToDosError` at `0x180089728`
- `ntdll!RtlNtStatusToDosError` at `0x180089795`
- `ntdll!RtlNtStatusToDosError` at `0x180089802`
- `ntdll!RtlNtStatusToDosError` at `0x18008995f`
- `ntdll!RtlNtStatusToDosError` at `0x180089728`
- `ntdll!RtlNtStatusToDosError` at `0x180089795`
- `ntdll!RtlNtStatusToDosError` at `0x180089802`
- `ntdll!RtlNtStatusToDosError` at `0x18008995f`
- `KERNEL32!LocalFree` at `0x180089643`
- `KERNEL32!LocalFree` at `0x180089672`
- `KERNEL32!LocalFree` at `0x180089698`
- `KERNEL32!LocalFree` at `0x1800896c7`
- `KERNEL32!LocalFree` at `0x180089643`
- `KERNEL32!LocalFree` at `0x180089672`
- `KERNEL32!LocalFree` at `0x180089698`
- `KERNEL32!LocalFree` at `0x1800896c7`
- `KERNEL32!LocalAlloc` at `0x1800891a5`
- `KERNEL32!LocalAlloc` at `0x1800891a5`

## string_xrefs

- `0x180088d40`: `base\fs\fsrm\utilities\property\srmadscache.cpp`
- `0x180089764`: `base\fs\fsrm\utilities\property\srmadscache.cpp`
- `0x1800897d1`: `base\fs\fsrm\utilities\property\srmadscache.cpp`
- `0x18008983e`: `base\fs\fsrm\utilities\property\srmadscache.cpp`
- `0x18008999b`: `base\fs\fsrm\utilities\property\srmadscache.cpp`
- `0x1800899f1`: `base\fs\fsrm\utilities\property\srmadscache.cpp`
- `0x180088d4b`: `CAdsCacheStream::CreateCacheStream`
- `0x180089756`: `CAdsCacheStream::CreateCacheStream`
- `0x1800897c3`: `CAdsCacheStream::CreateCacheStream`
- `0x180089830`: `CAdsCacheStream::CreateCacheStream`
- `0x18008998d`: `CAdsCacheStream::CreateCacheStream`
- `0x1800899e3`: `CAdsCacheStream::CreateCacheStream`
- `0x180089a07`: `Cache size is too large: size = %I64u`

## pseudocode

```c
// Hidden C++ exception states: #wind=31
char __fastcall CAdsCacheStream::CreateCacheStream(CAdsCacheStream *this, struct _FILETIME a2, unsigned int a3)
{
  _DWORD *v5; // r13
  __int64 v6; // rsi
  __int64 v7; // rcx
  _QWORD *v8; // rcx
  unsigned int i; // r14d
  __int64 v10; // rbx
  __int64 v11; // rdi
  int v12; // edx
  __int64 v13; // rsi
  __int64 v14; // rax
  unsigned int v15; // r15d
  NTSTATUS v16; // eax
  NTSTATUS v17; // edi
  size_t v18; // rbx
  NTSTATUS v19; // eax
  NTSTATUS v20; // edi
  void *v21; // r14
  char *v22; // rsi
  SIZE_T v23; // rbx
  __int64 *v24; // rbx
  __int64 v25; // rdi
  __int64 v26; // r14
  __int64 v27; // r15
  int v28; // ecx
  const wchar_t *v29; // r8
  int v30; // ecx
  int v31; // ecx
  int v32; // ecx
  int v33; // ecx
  int v34; // ecx
  int v35; // eax
  __int64 *j; // rax
  __int64 *v37; // rcx
  size_t v38; // rbx
  unsigned int v39; // eax
  int v40; // eax
  _QWORD *v41; // r9
  unsigned int *v42; // rcx
  unsigned __int64 *v43; // rcx
  struct _FILETIME v44; // rax
  const unsigned __int16 *v45; // r8
  NTSTATUS v46; // eax
  __int64 v47; // rdx
  NTSTATUS v48; // edi
  size_t v49; // rbx
  NTSTATUS v50; // eax
  NTSTATUS v51; // edi
  signed int v53; // eax
  unsigned int v54; // ebx
  __int64 v55; // rax
  signed int v56; // eax
  unsigned int v57; // ebx
  __int64 v58; // rax
  signed int v59; // eax
  unsigned int v60; // ebx
  __int64 v61; // rax
  int v62; // eax
  char v63; // al
  int v64; // eax
  char v65; // al
  char v66; // al
  char Hr; // al
  signed int v68; // eax
  unsigned int v69; // ebx
  __int64 v70; // rax
  __int64 v71; // rax
  unsigned __int64 *v72; // [rsp+20h] [rbp-E0h]
  unsigned __int64 *v73; // [rsp+20h] [rbp-E0h]
  unsigned __int64 *v74; // [rsp+20h] [rbp-E0h]
  unsigned __int64 *v75; // [rsp+20h] [rbp-E0h]
  const unsigned __int16 **v76; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v77; // [rsp+48h] [rbp-B8h]
  int v78; // [rsp+50h] [rbp-B0h]
  size_t Size[2]; // [rsp+58h] [rbp-A8h] BYREF
  struct _FILETIME v80; // [rsp+68h] [rbp-98h]
  void **v81; // [rsp+70h] [rbp-90h]
  char *v82; // [rsp+78h] [rbp-88h]
  void **v83; // [rsp+80h] [rbp-80h] BYREF
  void *v84; // [rsp+88h] [rbp-78h]
  void **v85; // [rsp+90h] [rbp-70h] BYREF
  void *v86; // [rsp+98h] [rbp-68h]
  void **v87; // [rsp+A0h] [rbp-60h] BYREF
  _DWORD *v88; // [rsp+A8h] [rbp-58h]
  HLOCAL hMem; // [rsp+B0h] [rbp-50h] BYREF
  unsigned int v90; // [rsp+B8h] [rbp-48h]
  const unsigned __int16 *v91; // [rsp+C0h] [rbp-40h] BYREF
  const wchar_t *v92; // [rsp+C8h] [rbp-38h]
  unsigned __int64 v93; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v94; // [rsp+D8h] [rbp-28h] BYREF
  void *v95; // [rsp+E0h] [rbp-20h]
  _QWORD v96[2]; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v97; // [rsp+F8h] [rbp-8h]
  unsigned int *v98; // [rsp+100h] [rbp+0h]
  int v99; // [rsp+148h] [rbp+48h]
  char v100[8]; // [rsp+150h] [rbp+50h] BYREF
  __int64 *v101; // [rsp+158h] [rbp+58h]
  __int64 v102; // [rsp+160h] [rbp+60h]
  _QWORD v103[3]; // [rsp+170h] [rbp+70h] BYREF
  int v104; // [rsp+188h] [rbp+88h]
  int v105; // [rsp+18Ch] [rbp+8Ch]
  int v106; // [rsp+190h] [rbp+90h]
  char v107[96]; // [rsp+198h] [rbp+98h] BYREF
  int v108; // [rsp+1F8h] [rbp+F8h]
  void *Block[2]; // [rsp+200h] [rbp+100h] BYREF
  __int64 v110; // [rsp+210h] [rbp+110h]
  unsigned __int64 v111; // [rsp+218h] [rbp+118h]
  unsigned __int16 *v112[2]; // [rsp+228h] [rbp+128h] BYREF
  __int64 v113; // [rsp+238h] [rbp+138h]
  unsigned __int64 v114; // [rsp+240h] [rbp+140h]
  void *v115[2]; // [rsp+250h] [rbp+150h] BYREF
  __int64 v116; // [rsp+260h] [rbp+160h]
  unsigned __int64 v117; // [rsp+268h] [rbp+168h]
  void **v118; // [rsp+280h] [rbp+180h] BYREF
  int v119; // [rsp+288h] [rbp+188h]
  void **v120; // [rsp+330h] [rbp+230h] BYREF
  int v121; // [rsp+338h] [rbp+238h]

  v90 = a3;
  v80 = a2;
  v76 = &v91;
  v91 = L"base\\fs\\fsrm\\utilities\\property\\srmadscache.cpp";
  v92 = L"CAdsCacheStream::CreateCacheStream";
  v93 = (unsigned __int64)L"SRMADSCC";
  v94 = 0x1100000105LL;
  LODWORD(v95) = 255;
  v99 = 0x1000000;
  memset_0(v96, 0, 0x60u);
  CSrmFunctionTracer::CSrmFunctionTracer((__int64)&v118, (const struct CSrmDebugInfo *)&v91, 0);
  memset_0(&v91, 0, 0x48u);
  v5 = 0;
  v88 = 0;
  v87 = &CSrmAutoLocalPtr<_FCI_ADS_NON_SECURE_PROPERTY *>::`vftable';
  std::map<std::wstring,unsigned long,CCaseInsensitiveLess<std::wstring,std::wstring>,std::allocator<std::pair<std::wstring const,unsigned long>>>::map<std::wstring,unsigned long,CCaseInsensitiveLess<std::wstring,std::wstring>,std::allocator<std::pair<std::wstring const,unsigned long>>>(v100);
  v6 = 0;
  v78 = 0;
  v7 = *(_QWORD *)(*(_QWORD *)this + 16LL);
  if ( *(_DWORD *)(v7 + 16) )
  {
    CSrmAutoLocalPtr_Storage<_FCI_ADS_NON_SECURE_PROPERTY *>::AllocateBytes(&v87, 24LL * *(unsigned int *)(v7 + 16));
    v5 = v88;
  }
  v8 = *(_QWORD **)this;
  if ( *(_DWORD *)(*(_QWORD *)(*(_QWORD *)this + 16LL) + 16LL) )
  {
    for ( i = 0; i < *(_DWORD *)(*(_QWORD *)(*(_QWORD *)this + 16LL) + 16LL); ++i )
    {
      v10 = 32LL * i;
      v11 = *(_QWORD *)(v8[2] + 24LL);
      v12 = *(_DWORD *)(v11 + v10 + 24);
      if ( (v12 & 0x10) == 0 )
      {
        if ( (v12 & 1) != 0 )
        {
          if ( (*(unsigned __int8 (__fastcall **)(_QWORD *, __int64))(*v8 + 72LL))(v8, 4096) )
            goto LABEL_22;
          v8 = *(_QWORD **)this;
        }
        if ( (*(_DWORD *)(v11 + v10 + 24) & 0x40) != 0 )
        {
          (*(void (__fastcall **)(_QWORD *, __int64))(*v8 + 56LL))(v8, 0x8000000);
          if ( *(_QWORD *)(v11 + v10 + 8) )
          {
            v8 = *(_QWORD **)this;
LABEL_12:
            if ( (*(_DWORD *)(v11 + v10 + 24) & 0x800) != 0 )
            {
              v76 = *(const unsigned __int16 ***)(v11 + 32LL * i);
              LODWORD(v77) = i;
              v14 = std::_Tree_val<std::_Tmap_traits<std::wstring,unsigned long,CCaseInsensitiveLess<std::wstring,std::wstring>,std::allocator<std::pair<std::wstring const,unsigned long>>,0>>::_Buynode<std::pair<unsigned short *,unsigned long>>(
                      v100,
                      &v76);
              std::_Tree<std::_Tmap_traits<std::wstring,unsigned long,CCaseInsensitiveLess<std::wstring,std::wstring>,std::allocator<std::pair<std::wstring const,unsigned long>>,0>>::_Linsert(
                v100,
                Size,
                v14);
            }
            else if ( (*(_DWORD *)(v8[1] + 128LL) & 0x10) == 0 )
            {
              v13 = 3 * v6;
              v5[2 * v13] = 0;
              std::wstring::wstring(Block, *(_WORD **)(v11 + 32LL * i));
              ((void (__fastcall *)(_QWORD, _QWORD, _QWORD))std::_Tree<std::_Tmap_traits<std::wstring,ATL::CAdapt<CSrmRefPtr<ATL::CComObject<CFciPropertyDefinition>>>,CCaseInsensitiveLess<std::wstring,std::wstring>,std::allocator<std::pair<std::wstring const,ATL::CAdapt<CSrmRefPtr<ATL::CComObject<CFciPropertyDefinition>>>>>,0>>::find)(
                a2,
                &hMem,
                Block);
              if ( v111 >= 8 )
                operator delete(Block[0]);
              v111 = 7;
              v110 = 0;
              LOWORD(Block[0]) = 0;
              if ( hMem != *(HLOCAL *)(*(_QWORD *)&a2 + 8LL) )
                v5[2 * v13] = *(_DWORD *)(*((_QWORD *)hMem + 8) + 64LL);
              *(_QWORD *)&v5[2 * v13 + 2] = *(_QWORD *)(v11 + 32LL * i);
              *(_QWORD *)&v5[2 * v13 + 4] = *(_QWORD *)(v11 + v10 + 8);
              v5[2 * v13 + 1] = *(_DWORD *)(v11 + v10 + 24) & 0x5000;
              v6 = (unsigned int)++v78;
            }
          }
        }
        else
        {
          if ( *(_QWORD *)(v11 + v10 + 8) )
            goto LABEL_12;
          CSrmFunctionTracer::Trace(
            (CSrmFunctionTracer *)&v118,
            0x28u,
            0x14Cu,
            L"No value available for property %s",
            *(_QWORD *)(v11 + 32LL * i));
          (*(void (__fastcall **)(_QWORD, __int64))(**(_QWORD **)this + 56LL))(*(_QWORD *)this, 0x8000000);
        }
      }
LABEL_22:
      v8 = *(_QWORD **)this;
    }
  }
  v15 = 0;
  hMem = 0;
  v86 = 0;
  v85 = &CSrmAutoLocalPtr<_FCI_ADS_NON_SECURE_PROPERTY *>::`vftable';
  if ( (_DWORD)v6 )
  {
    Size[0] = 0;
    v16 = FciAdsSerializeNonSecureProperties(v5, (unsigned int)v6, &v94, Size);
    v17 = v16;
    if ( v16 != -2147483643 )
    {
      v56 = RtlNtStatusToDosError(v16);
      v57 = v56;
      if ( v56 > 0 )
        v57 = (unsigned __int16)v56 | 0x80070000;
      v76 = &v91;
      v58 = CSrmDebugInfo::CSrmDebugInfo(
              (__int64)&v91,
              (__int64)L"base\\fs\\fsrm\\utilities\\property\\srmadscache.cpp",
              (__int64)L"SRMADSCC",
              (__int64)L"CAdsCacheStream::CreateCacheStream",
              410,
              17);
      LODWORD(v73) = v17;
      CSrmFunctionTracer::Throw(&v118, v58, v57, L"Non-secure property serialization failed with error %ld", v73);
    }
    v18 = Size[0];
    CSrmAutoLocalPtr_Storage<unsigned char *>::AllocateBytes(&v85, Size[0]);
    v94 = v18;
    hMem = v86;
    v95 = v86;
    v19 = FciAdsSerializeNonSecureProperties(v5, (unsigned int)v6, &v94, Size);
    v20 = v19;
    if ( v19 < 0 )
    {
      v59 = RtlNtStatusToDosError(v19);
      v60 = v59;
      if ( v59 > 0 )
        v60 = (unsigned __int16)v59 | 0x80070000;
      v76 = &v91;
      v61 = CSrmDebugInfo::CSrmDebugInfo(
              (__int64)&v91,
              (__int64)L"base\\fs\\fsrm\\utilities\\property\\srmadscache.cpp",
              (__int64)L"SRMADSCC",
              (__int64)L"CAdsCacheStream::CreateCacheStream",
              432,
              17);
      LODWORD(v74) = v20;
      CSrmFunctionTracer::Throw(&v118, v61, v60, L"Non-secure property serialization failed with error %ld", v74);
    }
  }
  v21 = 0;
  v84 = 0;
  v83 = &CSrmAutoLocalPtr<_FCI_ADS_NON_SECURE_PROPERTY *>::`vftable';
  v22 = 0;
  v82 = 0;
  v81 = &CSrmAutoLocalPtr<_FCI_ADS_NON_SECURE_PROPERTY *>::`vftable';
  if ( v102 )
  {
    v23 = 32 * v102;
    v76 = (const unsigned __int16 **)v103;
    v103[0] = L"base\\fs\\fsrm\\utilities\\inc\\srmtypes.h";
    v103[1] = L"CSrmAutoLocalPtr_Storage<struct _FCI_ADS_SECURE_PROPERTY *>::AllocateBytes";
    v103[2] = L"INCTYPEH";
    v104 = 1418;
    v105 = 17;
    v106 = 255;
    v108 = 0x1000000;
    memset_0(v107, 0, sizeof(v107));
    CSrmFunctionTracer::CSrmFunctionTracer((__int64)&v120, (const struct CSrmDebugInfo *)v103, 0);
    v82 = 0;
    v22 = (char *)LocalAlloc(0, v23);
    v82 = v22;
    if ( !v22 )
    {
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v120, -2147024882);
      Hr = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v120);
      CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v120, 0x591u, Hr, 0);
    }
    LODWORD(Size[0]) = 0;
    v121 = 0;
    v120 = &CSrmFunctionTracer::`vftable';
    CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)&v120);
    memset_0(v22, 0, 32 * v102);
    v24 = (__int64 *)*v101;
    while ( 1 )
    {
      if ( v24 == v101 )
      {
        Size[0] = 0;
        if ( (unsigned int)FciAdsSerializeSecureProperties(v22, v15, v96, Size) != -2147483643 )
        {
          CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v118, -2147200234);
          v66 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v118);
          CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v118, 0x20Du, v66, 0);
        }
        v119 = 0;
        v38 = Size[0];
        CSrmAutoLocalPtr_Storage<unsigned char *>::AllocateBytes(&v83, Size[0]);
        v21 = v84;
        memset_0(v84, 0, v38);
        v96[0] = v38;
        v96[1] = v21;
        v39 = FciAdsSerializeSecureProperties(v22, v15, v96, Size);
        v40 = HRESULTFromNTSTATUS(v39);
        v119 = v40;
        if ( v40 < 0 )
        {
          v64 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v118);
          CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v118, v64);
          v65 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v118);
          CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v118, 0x218u, v65, 0);
        }
        v119 = v40;
        break;
      }
      v25 = 32LL * *((unsigned int *)v24 + 16);
      v26 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)this + 16LL) + 24LL);
      v27 = 32LL * v15;
      std::wstring::wstring(Block, *(_WORD **)(v25 + v26));
      ((void (__fastcall *)(_QWORD, _QWORD, _QWORD))std::_Tree<std::_Tmap_traits<std::wstring,ATL::CAdapt<CSrmRefPtr<ATL::CComObject<CFciPropertyDefinition>>>,CCaseInsensitiveLess<std::wstring,std::wstring>,std::allocator<std::pair<std::wstring const,ATL::CAdapt<CSrmRefPtr<ATL::CComObject<CFciPropertyDefinition>>>>>,0>>::find)(
        v80,
        &v76,
        Block);
      if ( v111 >= 8 )
        operator delete(Block[0]);
      v111 = 7;
      v110 = 0;
      LOWORD(Block[0]) = 0;
      if ( v76 == *(const unsigned __int16 ***)(*(_QWORD *)&v80 + 8LL) )
        v28 = *(_DWORD *)(v25 + v26 + 28);
      else
        v28 = *((_DWORD *)v76[8] + 16);
      *(_DWORD *)&v22[v27 + 4] = *(_DWORD *)(v25 + v26 + 24) & 0x5000;
      *(_QWORD *)&v22[v27 + 16] = *(_QWORD *)(v25 + v26);
      v29 = *(const wchar_t **)(v25 + v26 + 8);
      *(_QWORD *)&v22[v27 + 24] = v29;
      v30 = v28 - 1;
      if ( v30 )
      {
        v31 = v30 - 1;
        if ( !v31 )
          goto LABEL_48;
        v32 = v31 - 1;
        if ( !v32 )
          goto LABEL_47;
        v33 = v32 - 1;
        if ( !v33 )
          goto LABEL_47;
        v34 = v33 - 1;
        if ( !v34 )
        {
LABEL_48:
          if ( v29 && wcschr(v29, 0x7Cu) )
          {
            v35 = 5;
            goto LABEL_42;
          }
LABEL_47:
          v35 = 4;
          goto LABEL_42;
        }
        if ( (unsigned int)(v34 - 1) > 1 )
        {
          v119 = -2147200234;
          v62 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v118);
          CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v118, v62);
          v63 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v118);
          CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v118, 0x200u, v63, 0);
        }
      }
      v35 = 6;
LABEL_42:
      *(_DWORD *)&v22[v27] = v35;
      v15 = ++LODWORD(Size[0]);
      if ( !*((_BYTE *)v24 + 73) )
      {
        j = (__int64 *)v24[2];
        if ( *((_BYTE *)j + 73) )
        {
          for ( j = (__int64 *)v24[1]; !*((_BYTE *)j + 73) && v24 == (__int64 *)j[2]; j = (__int64 *)j[1] )
            v24 = j;
LABEL_55:
          v24 = j;
        }
        else
        {
          v37 = (__int64 *)*j;
          if ( *(_BYTE *)(*j + 73) )
            goto LABEL_55;
          do
          {
            v24 = v37;
            v37 = (__int64 *)*v37;
          }
          while ( !*((_BYTE *)v37 + 73) );
        }
      }
    }
  }
  v41 = *(_QWORD **)this;
  v42 = *(unsigned int **)(*(_QWORD *)this + 32LL);
  if ( v42 )
  {
    v97 = *v42;
    v98 = v42 + 1;
  }
  else
  {
    v97 = 0;
    v98 = 0;
  }
  v91 = (const unsigned __int16 *)*(unsigned int *)(v41[1] + 120LL);
  LODWORD(v92) = (*(unsigned __int8 (__fastcall **)(_QWORD *, __int64))(*v41 + 72LL))(v41, 0x8000000) != 0;
  v114 = 7;
  v113 = 0;
  LOWORD(v112[0]) = 0;
  CPropertyBagFieldsBase::GetRelativePathAndName(*(_QWORD *)this, v112);
  if ( (*(unsigned __int8 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)this + 72LL))(*(_QWORD *)this, 0x20000) )
  {
    v93 = 0;
  }
  else
  {
    v43 = *(unsigned __int64 **)(*(_QWORD *)this + 8LL);
    v44 = (struct _FILETIME)v43[14];
    v80 = v44;
    v45 = (const unsigned __int16 *)v112;
    if ( v114 >= 8 )
      v45 = v112[0];
    CAdsCacheStream::HashFileProperties(v43[8], v43[9], v45, v80, &v93);
  }
  HIDWORD(v92) = v78;
  v76 = 0;
  v77 = 0;
  Size[0] = 0;
  v46 = FciAdsSerializeAds(&v91, &v76, Size);
  v48 = v46;
  if ( v46 != -2147483643 )
  {
    v68 = RtlNtStatusToDosError(v46);
    v69 = v68;
    if ( v68 > 0 )
      v69 = (unsigned __int16)v68 | 0x80070000;
    v76 = &v91;
    v70 = CSrmDebugInfo::CSrmDebugInfo(
            (__int64)&v91,
            (__int64)L"base\\fs\\fsrm\\utilities\\property\\srmadscache.cpp",
            (__int64)L"SRMADSCC",
            (__int64)L"CAdsCacheStream::CreateCacheStream",
            605,
            17);
    LODWORD(v75) = v48;
    CSrmFunctionTracer::Throw(&v118, v70, v69, L"ADS stream serialization failed with error %ld", v75);
  }
  v49 = Size[0];
  if ( Size[0] > v90 )
  {
    v76 = &v91;
    v71 = CSrmDebugInfo::CSrmDebugInfo(
            (__int64)&v91,
            (__int64)L"base\\fs\\fsrm\\utilities\\property\\srmadscache.cpp",
            (__int64)L"SRMADSCC",
            (__int64)L"CAdsCacheStream::CreateCacheStream",
            616,
            17);
    CSrmFunctionTracer::Throw(&v118, v71, 2147942623LL, L"Cache size is too large: size = %I64u", v49);
  }
  v117 = 7;
  v116 = 0;
  LOWORD(v115[0]) = 0;
  LOBYTE(v47) = 1;
  CPropertyBagFieldsBase::BuildFullPath(*(_QWORD *)this, v47, L"FSRM{ef88c031-5950-4164-ab92-eec5f16005a5}", v115);
  SrmConvertToLongPath(v115);
  CAdsCacheStream::Allocate(this);
  v76 = (const unsigned __int16 **)v49;
  v77 = *((_QWORD *)this + 6) + 4LL;
  v50 = FciAdsSerializeAds(&v91, &v76, Size);
  v51 = v50;
  if ( v50 < 0 )
  {
    v53 = RtlNtStatusToDosError(v50);
    v54 = v53;
    if ( v53 > 0 )
      v54 = (unsigned __int16)v53 | 0x80070000;
    v76 = &v91;
    v55 = CSrmDebugInfo::CSrmDebugInfo(
            (__int64)&v91,
            (__int64)L"base\\fs\\fsrm\\utilities\\property\\srmadscache.cpp",
            (__int64)L"SRMADSCC",
            (__int64)L"CAdsCacheStream::CreateCacheStream",
            654,
            17);
    LODWORD(v72) = v51;
    CSrmFunctionTracer::Throw(&v118, v55, v54, L"ADS stream serialization failed with error %ld", v72);
  }
  if ( v117 >= 8 )
    operator delete(v115[0]);
  v117 = 7;
  v116 = 0;
  LOWORD(v115[0]) = 0;
  if ( v114 >= 8 )
    operator delete(v112[0]);
  v114 = 7;
  v113 = 0;
  LOWORD(v112[0]) = 0;
  v81 = &CSrmAuto<_FCI_ADS_NON_SECURE_PROPERTY *,CSrmAutoLocalPtr_Storage<_FCI_ADS_NON_SECURE_PROPERTY *>>::`vftable';
  if ( v22 )
    LocalFree(v22);
  v81 = &CSrmAutoLocalPtr_Storage<void *>::`vftable';
  v82 = 0;
  v83 = &CSrmAuto<_FCI_ADS_NON_SECURE_PROPERTY *,CSrmAutoLocalPtr_Storage<_FCI_ADS_NON_SECURE_PROPERTY *>>::`vftable';
  if ( v21 )
    LocalFree(v21);
  v83 = &CSrmAutoLocalPtr_Storage<void *>::`vftable';
  v84 = 0;
  v85 = &CSrmAuto<_FCI_ADS_NON_SECURE_PROPERTY *,CSrmAutoLocalPtr_Storage<_FCI_ADS_NON_SECURE_PROPERTY *>>::`vftable';
  if ( hMem )
    LocalFree(hMem);
  v85 = &CSrmAutoLocalPtr_Storage<void *>::`vftable';
  v86 = 0;
  std::_Tree<std::_Tmap_traits<std::wstring,unsigned long,CCaseInsensitiveLess<std::wstring,std::wstring>,std::allocator<std::pair<std::wstring const,unsigned long>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,unsigned long,CCaseInsensitiveLess<std::wstring,std::wstring>,std::allocator<std::pair<std::wstring const,unsigned long>>,0>>(v100);
  v87 = &CSrmAuto<_FCI_ADS_NON_SECURE_PROPERTY *,CSrmAutoLocalPtr_Storage<_FCI_ADS_NON_SECURE_PROPERTY *>>::`vftable';
  if ( v5 )
    LocalFree(v5);
  v87 = &CSrmAutoLocalPtr_Storage<void *>::`vftable';
  v88 = 0;
  v118 = &CSrmFunctionTracer::`vftable';
  CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)&v118);
  return 1;
}

```

## disassembly

```asm
0x180088cf8  mov     [rsp-8+arg_10], rbx
0x180088cfd  push    rbp
0x180088cfe  push    rsi
0x180088cff  push    rdi
0x180088d00  push    r12
0x180088d02  push    r13
0x180088d04  push    r14
0x180088d06  push    r15
0x180088d08  lea     rbp, [rsp-2F0h]
0x180088d10  sub     rsp, 3F0h
0x180088d17  mov     rax, cs:__security_cookie
0x180088d1e  xor     rax, rsp
0x180088d21  mov     [rbp+320h+var_40], rax
0x180088d28  mov     [rbp+320h+var_368], r8d
0x180088d2c  mov     r15, rdx
0x180088d2f  mov     qword ptr [rsp+420h+var_3B8.dwLowDateTime], rdx
0x180088d34  mov     r12, rcx
0x180088d37  lea     rax, [rbp+320h+var_360]
0x180088d3b  mov     [rsp+420h+var_3E0], rax
0x180088d40  lea     rax, aBaseFsFsrmUtil; "base\\fs\\fsrm\\utilities\\property\\sr"...
0x180088d47  mov     [rbp+320h+var_360], rax
0x180088d4b  lea     rax, aCadscachestrea_1; "CAdsCacheStream::CreateCacheStream"
0x180088d52  mov     [rbp+320h+var_358], rax
0x180088d56  lea     rax, aSrmadscc; "SRMADSCC"
0x180088d5d  mov     [rbp+320h+var_350], rax
0x180088d61  mov     dword ptr [rbp+320h+var_348], 105h
0x180088d68  mov     dword ptr [rbp+320h+var_348+4], 11h
0x180088d6f  mov     dword ptr [rbp+320h+var_340], 0FFh
0x180088d76  mov     [rbp+320h+var_2D8], 1000000h
0x180088d7d  xor     edx, edx; Val
0x180088d7f  lea     r8d, [rdx+60h]; Size
0x180088d83  lea     rcx, [rbp+320h+var_338]; void *
0x180088d87  call    memset_0
0x180088d8c  nop
0x180088d8d  xor     r8d, r8d
0x180088d90  lea     rdx, [rbp+320h+var_360]
0x180088d94  lea     rcx, [rbp+320h+var_1A0]
0x180088d9b  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x180088da0  nop
0x180088da1  xor     edx, edx; Val
0x180088da3  lea     r8d, [rdx+48h]; Size
0x180088da7  lea     rcx, [rbp+320h+var_360]; void *
0x180088dab  call    memset_0
0x180088db0  lea     rax, ??_7?$CSrmAutoLocalPtr_Storage@PEAX@@6B@; const CSrmAutoLocalPtr_Storage<void *>::`vftable'
0x180088db7  mov     [rbp+320h+var_380], rax
0x180088dbb  mov     [rbp+320h+var_378], 0
0x180088dc3  lea     rax, ??_7?$CSrmAutoLocalPtr_Storage@PEAE@@6B@; const CSrmAutoLocalPtr_Storage<uchar *>::`vftable'
0x180088dca  mov     [rbp+320h+var_380], rax
0x180088dce  lea     rax, ??_7?$CSrmAuto@PEAU_FCI_ADS_NON_SECURE_PROPERTY@@V?$CSrmAutoLocalPtr_Storage@PEAU_FCI_ADS_NON_SECURE_PROPERTY@@@@@@6B@; const CSrmAuto<_FCI_ADS_NON_SECURE_PROPERTY *,CSrmAutoLocalPtr_Storage<_FCI_ADS_NON_SECURE_PROPERTY *>>::`vftable'
0x180088dd5  mov     [rbp+320h+var_380], rax
0x180088dd9  xor     r13d, r13d
0x180088ddc  mov     [rbp+320h+var_378], r13
0x180088de0  lea     rax, ??_7?$CSrmAutoLocalPtr@PEAU_FCI_ADS_NON_SECURE_PROPERTY@@@@6B@; const CSrmAutoLocalPtr<_FCI_ADS_NON_SECURE_PROPERTY *>::`vftable'
0x180088de7  mov     [rbp+320h+var_380], rax
0x180088deb  lea     rcx, [rbp+320h+var_2D0]
0x180088def  call    ??0?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KU?$CCaseInsensitiveLess@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@@std@@QEAA@XZ; std::map<std::wstring,ulong,CCaseInsensitiveLess<std::wstring,std::wstring>,std::allocator<std::pair<std::wstring const,ulong>>>::map<std::wstring,ulong,CCaseInsensitiveLess<std::wstring,std::wstring>,std::allocator<std::pair<std::wstring const,ulong>>>(void)
0x180088df4  nop
0x180088df5  xor     esi, esi
0x180088df7  mov     [rsp+420h+var_3D0], esi
0x180088dfb  mov     rax, [r12]
0x180088dff  mov     rcx, [rax+10h]
0x180088e03  cmp     [rcx+10h], esi
0x180088e06  jbe     short loc_180088E20
0x180088e08  mov     eax, [rcx+10h]
0x180088e0b  lea     rdx, [rax+rax*2]
0x180088e0f  shl     rdx, 3
0x180088e13  lea     rcx, [rbp+320h+var_380]
0x180088e17  call    ?AllocateBytes@?$CSrmAutoLocalPtr_Storage@PEAU_FCI_ADS_NON_SECURE_PROPERTY@@@@QEAAX_K@Z; CSrmAutoLocalPtr_Storage<_FCI_ADS_NON_SECURE_PROPERTY *>::AllocateBytes(unsigned __int64)
0x180088e1c  mov     r13, [rbp+320h+var_378]
0x180088e20  mov     rcx, [r12]
0x180088e24  mov     rax, [rcx+10h]
0x180088e28  cmp     [rax+10h], esi
0x180088e2b  jbe     loc_180088FF6
0x180088e31  xor     r14d, r14d
0x180088e34  mov     rax, [rcx+10h]
0x180088e38  mov     ebx, r14d
0x180088e3b  shl     rbx, 5
0x180088e3f  mov     rdi, [rax+18h]
0x180088e43  mov     edx, [rdi+rbx+18h]
0x180088e47  test    dl, 10h
0x180088e4a  jnz     loc_180088FE1
0x180088e50  test    dl, 1
0x180088e53  jz      short loc_180088E72
0x180088e55  mov     rax, [rcx]
0x180088e58  mov     edx, 1000h
0x180088e5d  mov     rax, [rax+48h]
0x180088e61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088e66  test    al, al
0x180088e68  jnz     loc_180088FE1
0x180088e6e  mov     rcx, [r12]
0x180088e72  mov     eax, [rdi+rbx+18h]
0x180088e76  test    al, 40h
0x180088e78  jz      loc_180088F6A
0x180088e7e  mov     rax, [rcx]
0x180088e81  mov     edx, 8000000h
0x180088e86  mov     rax, [rax+38h]
0x180088e8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088e8f  cmp     qword ptr [rdi+rbx+8], 0
0x180088e95  jz      loc_180088FE1
0x180088e9b  mov     rcx, [r12]
0x180088e9f  test    dword ptr [rdi+rbx+18h], 800h
0x180088ea7  jnz     loc_180088FB4
0x180088ead  mov     rax, [rcx+8]
0x180088eb1  mov     ecx, [rax+80h]
0x180088eb7  test    cl, 10h
0x180088eba  jnz     loc_180088FE1
0x180088ec0  lea     rsi, [rsi+rsi*2]
0x180088ec4  mov     dword ptr [r13+rsi*8+0], 0
0x180088ecd  mov     rdx, [rdi+rbx]
0x180088ed1  lea     rcx, [rbp+320h+Block]; void *
0x180088ed8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180088edd  nop
0x180088ede  lea     r8, [rbp+320h+Block]
0x180088ee5  lea     rdx, [rbp+320h+hMem]
0x180088ee9  mov     rcx, r15
0x180088eec  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$CAdapt@V?$CSrmRefPtr@V?$CComObject@VCFciPropertyDefinition@@@ATL@@@@@ATL@@U?$CCaseInsensitiveLess@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$CAdapt@V?$CSrmRefPtr@V?$CComObject@VCFciPropertyDefinition@@@ATL@@@@@ATL@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$CAdapt@V?$CSrmRefPtr@V?$CComObject@VCFciPropertyDefinition@@@ATL@@@@@ATL@@U?$CCaseInsensitiveLess@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$CAdapt@V?$CSrmRefPtr@V?$CComObject@VCFciPropertyDefinition@@@ATL@@@@@ATL@@@std@@@2@$0A@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,ATL::CAdapt<CSrmRefPtr<ATL::CComObject<CFciPropertyDefinition>>>,CCaseInsensitiveLess<std::wstring,std::wstring>,std::allocator<std::pair<std::wstring const,ATL::CAdapt<CSrmRefPtr<ATL::CComObject<CFciPropertyDefinition>>>>>,0>>::find(std::wstring const &)
0x180088ef1  nop
0x180088ef2  cmp     [rbp+320h+var_208], 8
0x180088efa  jb      short loc_180088F08
0x180088efc  mov     rcx, [rbp+320h+Block]; Block
0x180088f03  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180088f08  mov     [rbp+320h+var_208], 7
0x180088f13  mov     [rbp+320h+var_210], 0
0x180088f1e  xor     eax, eax
0x180088f20  mov     word ptr [rbp+320h+Block], ax
0x180088f27  mov     rax, [rbp+320h+hMem]
0x180088f2b  cmp     rax, [r15+8]
0x180088f2f  jz      short loc_180088F3D
0x180088f31  mov     rcx, [rax+40h]
0x180088f35  mov     eax, [rcx+40h]
0x180088f38  mov     [r13+rsi*8+0], eax
0x180088f3d  mov     rax, [rdi+rbx]
0x180088f41  mov     [r13+rsi*8+8], rax
0x180088f46  mov     rax, [rdi+rbx+8]
0x180088f4b  mov     [r13+rsi*8+10h], rax
0x180088f50  mov     eax, [rdi+rbx+18h]
0x180088f54  and     eax, 5000h
0x180088f59  mov     [r13+rsi*8+4], eax
0x180088f5e  mov     esi, [rsp+420h+var_3D0]
0x180088f62  inc     esi
0x180088f64  mov     [rsp+420h+var_3D0], esi
0x180088f68  jmp     short loc_180088FE1
0x180088f6a  cmp     qword ptr [rdi+rbx+8], 0
0x180088f70  jnz     loc_180088E9F
0x180088f76  mov     rax, [rdi+rbx]
0x180088f7a  mov     [rsp+420h+var_400], rax
0x180088f7f  lea     r9, aNoValueAvailab; "No value available for property %s"
0x180088f86  mov     edx, 28h ; '('; unsigned int
0x180088f8b  mov     r8d, 14Ch; unsigned int
0x180088f91  lea     rcx, [rbp+320h+var_1A0]; this
0x180088f98  call    ?Trace@CSrmFunctionTracer@@QEAAXKKPEBGZZ; CSrmFunctionTracer::Trace(ulong,ulong,ushort const *,...)
0x180088f9d  mov     rcx, [r12]
0x180088fa1  mov     rax, [rcx]
0x180088fa4  mov     edx, 8000000h
0x180088fa9  mov     rax, [rax+38h]
0x180088fad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088fb2  jmp     short loc_180088FE1
0x180088fb4  mov     rax, [rdi+rbx]
0x180088fb8  mov     [rsp+420h+var_3E0], rax
0x180088fbd  mov     dword ptr [rsp+420h+var_3D8], r14d
0x180088fc2  lea     rdx, [rsp+420h+var_3E0]
0x180088fc7  lea     rcx, [rbp+320h+var_2D0]
0x180088fcb  call    ??$_Buynode@U?$pair@PEAGK@std@@@?$_Tree_val@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KU?$CCaseInsensitiveLess@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@$0A@@std@@@std@@QEAAPEAU_Node@?$_Tree_nod@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KU?$CCaseInsensitiveLess@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@$0A@@std@@@1@$$QEAU?$pair@PEAGK@1@@Z; std::_Tree_val<std::_Tmap_traits<std::wstring,ulong,CCaseInsensitiveLess<std::wstring,std::wstring>,std::allocator<std::pair<std::wstring const,ulong>>,0>>::_Buynode<std::pair<ushort *,ulong>>(std::pair<ushort *,ulong> &&)
0x180088fd0  mov     r8, rax
0x180088fd3  lea     rdx, [rsp+420h+Size]
0x180088fd8  lea     rcx, [rbp+320h+var_2D0]
0x180088fdc  call    ?_Linsert@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KU?$CCaseInsensitiveLess@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KU?$CCaseInsensitiveLess@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@$0A@@std@@@std@@@std@@_N@2@PEAU_Node@?$_Tree_nod@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KU?$CCaseInsensitiveLess@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@$0A@@std@@@2@_N@Z; std::_Tree<std::_Tmap_traits<std::wstring,ulong,CCaseInsensitiveLess<std::wstring,std::wstring>,std::allocator<std::pair<std::wstring const,ulong>>,0>>::_Linsert(std::_Tree_nod<std::_Tmap_traits<std::wstring,ulong,CCaseInsensitiveLess<std::wstring,std::wstring>,std::allocator<std::pair<std::wstring const,ulong>>,0>>::_Node *,bool)
0x180088fe1  inc     r14d
0x180088fe4  mov     rcx, [r12]
0x180088fe8  mov     rax, [rcx+10h]
0x180088fec  cmp     r14d, [rax+10h]
0x180088ff0  jb      loc_180088E34
0x180088ff6  lea     rax, ??_7?$CSrmAutoLocalPtr_Storage@PEAX@@6B@; const CSrmAutoLocalPtr_Storage<void *>::`vftable'
0x180088ffd  mov     [rbp+320h+var_390], rax
0x180089001  mov     [rbp+320h+var_388], 0
0x180089009  lea     r14, ??_7?$CSrmAutoLocalPtr_Storage@PEAE@@6B@; const CSrmAutoLocalPtr_Storage<uchar *>::`vftable'
0x180089010  mov     [rbp+320h+var_390], r14
0x180089014  lea     rax, ??_7?$CSrmAuto@PEAU_FCI_ADS_NON_SECURE_PROPERTY@@V?$CSrmAutoLocalPtr_Storage@PEAU_FCI_ADS_NON_SECURE_PROPERTY@@@@@@6B@; const CSrmAuto<_FCI_ADS_NON_SECURE_PROPERTY *,CSrmAutoLocalPtr_Storage<_FCI_ADS_NON_SECURE_PROPERTY *>>::`vftable'
0x18008901b  mov     [rbp+320h+var_390], rax
0x18008901f  xor     r15d, r15d
0x180089022  mov     [rbp+320h+hMem], r15
0x180089026  mov     [rbp+320h+var_388], r15
0x18008902a  lea     rax, ??_7?$CSrmAutoLocalPtr@PEAU_FCI_ADS_NON_SECURE_PROPERTY@@@@6B@; const CSrmAutoLocalPtr<_FCI_ADS_NON_SECURE_PROPERTY *>::`vftable'
0x180089031  mov     [rbp+320h+var_390], rax
0x180089035  test    esi, esi
0x180089037  jz      short loc_1800890A3
0x180089039  mov     [rsp+420h+Size], r15
0x18008903e  lea     r9, [rsp+420h+Size]
0x180089043  lea     r8, [rbp+320h+var_348]
0x180089047  mov     edx, esi
0x180089049  mov     rcx, r13
0x18008904c  call    FciAdsSerializeNonSecureProperties
0x180089051  mov     edi, eax
0x180089053  cmp     eax, 80000005h
0x180089058  jnz     loc_180089793
0x18008905e  mov     rbx, [rsp+420h+Size]
0x180089063  mov     rdx, rbx
0x180089066  lea     rcx, [rbp+320h+var_390]
0x18008906a  call    ?AllocateBytes@?$CSrmAutoLocalPtr_Storage@PEAE@@QEAAX_K@Z; CSrmAutoLocalPtr_Storage<uchar *>::AllocateBytes(unsigned __int64)
0x18008906f  mov     [rbp+320h+var_348], rbx
0x180089073  mov     rax, [rbp+320h+var_388]
0x180089077  mov     [rbp+320h+hMem], rax
0x18008907b  mov     [rbp+320h+var_340], rax
0x18008907f  lea     r9, [rsp+420h+Size]
0x180089084  lea     r8, [rbp+320h+var_348]
0x180089088  mov     edx, esi
0x18008908a  mov     rcx, r13
0x18008908d  call    FciAdsSerializeNonSecureProperties
0x180089092  mov     edi, eax
0x180089094  test    eax, eax
0x180089096  js      loc_180089800
0x18008909c  lea     rax, ??_7?$CSrmAutoLocalPtr@PEAU_FCI_ADS_NON_SECURE_PROPERTY@@@@6B@; const CSrmAutoLocalPtr<_FCI_ADS_NON_SECURE_PROPERTY *>::`vftable'
0x1800890a3  lea     rcx, ??_7?$CSrmAutoLocalPtr_Storage@PEAX@@6B@; const CSrmAutoLocalPtr_Storage<void *>::`vftable'
0x1800890aa  mov     [rbp+320h+var_3A0], rcx
0x1800890ae  mov     [rbp+320h+var_398], r15
0x1800890b2  mov     [rbp+320h+var_3A0], r14
0x1800890b6  lea     rcx, ??_7?$CSrmAuto@PEAU_FCI_ADS_NON_SECURE_PROPERTY@@V?$CSrmAutoLocalPtr_Storage@PEAU_FCI_ADS_NON_SECURE_PROPERTY@@@@@@6B@; const CSrmAuto<_FCI_ADS_NON_SECURE_PROPERTY *,CSrmAutoLocalPtr_Storage<_FCI_ADS_NON_SECURE_PROPERTY *>>::`vftable'
0x1800890bd  mov     [rbp+320h+var_3A0], rcx
0x1800890c1  mov     r14, r15
0x1800890c4  mov     [rbp+320h+var_398], r15
0x1800890c8  mov     [rbp+320h+var_3A0], rax
0x1800890cc  lea     rax, ??_7?$CSrmAutoLocalPtr_Storage@PEAX@@6B@; const CSrmAutoLocalPtr_Storage<void *>::`vftable'
0x1800890d3  mov     [rsp+420h+var_3B0], rax
0x1800890d8  mov     [rsp+420h+var_3A8], r15
0x1800890dd  lea     rax, ??_7?$CSrmAutoLocalPtr_Storage@PEAE@@6B@; const CSrmAutoLocalPtr_Storage<uchar *>::`vftable'
0x1800890e4  mov     [rsp+420h+var_3B0], rax
0x1800890e9  lea     rax, ??_7?$CSrmAuto@PEAU_FCI_ADS_NON_SECURE_PROPERTY@@V?$CSrmAutoLocalPtr_Storage@PEAU_FCI_ADS_NON_SECURE_PROPERTY@@@@@@6B@; const CSrmAuto<_FCI_ADS_NON_SECURE_PROPERTY *,CSrmAutoLocalPtr_Storage<_FCI_ADS_NON_SECURE_PROPERTY *>>::`vftable'
0x1800890f0  mov     [rsp+420h+var_3B0], rax
0x1800890f5  mov     rsi, r15
0x1800890f8  mov     [rsp+420h+var_3A8], r15
0x1800890fd  lea     rax, ??_7?$CSrmAutoLocalPtr@PEAU_FCI_ADS_NON_SECURE_PROPERTY@@@@6B@; const CSrmAutoLocalPtr<_FCI_ADS_NON_SECURE_PROPERTY *>::`vftable'
0x180089104  mov     [rsp+420h+var_3B0], rax
0x180089109  mov     rbx, [rbp+320h+var_2C0]
0x18008910d  mov     edi, 1
0x180089112  test    rbx, rbx
0x180089115  jz      loc_180089414
0x18008911b  shl     rbx, 5
0x18008911f  lea     rax, [rbp+320h+var_2B0]
0x180089123  mov     [rsp+420h+var_3E0], rax
0x180089128  lea     rax, aBaseFsFsrmUtil_1; "base\\fs\\fsrm\\utilities\\inc\\srmtype"...
0x18008912f  mov     [rbp+320h+var_2B0], rax
0x180089133  lea     rax, aCsrmautolocalp_3; "CSrmAutoLocalPtr_Storage<struct _FCI_AD"...
0x18008913a  mov     [rbp+320h+var_2A8], rax
0x18008913e  lea     rax, aInctypeh; "INCTYPEH"
0x180089145  mov     [rbp+320h+var_2A0], rax
0x18008914c  mov     [rbp+320h+var_298], 58Ah
0x180089156  mov     [rbp+320h+var_294], 11h
0x180089160  mov     [rbp+320h+var_290], 0FFh
0x18008916a  mov     [rbp+320h+var_228], 1000000h
0x180089174  xor     edx, edx; Val
0x180089176  lea     r8d, [rdi+5Fh]; Size
0x18008917a  lea     rcx, [rbp+320h+var_288]; void *
0x180089181  call    memset_0
0x180089186  nop
0x180089187  xor     r8d, r8d
0x18008918a  lea     rdx, [rbp+320h+var_2B0]
0x18008918e  lea     rcx, [rbp+320h+var_F0]
0x180089195  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x18008919a  nop
0x18008919b  mov     [rsp+420h+var_3A8], r15
0x1800891a0  mov     rdx, rbx; uBytes
0x1800891a3  xor     ecx, ecx; uFlags
0x1800891a5  call    cs:__imp_LocalAlloc
0x1800891ab  mov     rsi, rax
0x1800891ae  mov     [rsp+420h+var_3A8], rax
0x1800891b3  mov     eax, [rbp+320h+var_E8]
0x1800891b9  mov     [rbp+320h+var_E8], eax
0x1800891bf  test    rsi, rsi
0x1800891c2  jz      loc_180089928
0x1800891c8  mov     dword ptr [rsp+420h+Size], r15d
0x1800891cd  mov     [rbp+320h+var_E8], 0
0x1800891d7  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x1800891de  mov     [rbp+320h+var_F0], rax
0x1800891e5  lea     rcx, [rbp+320h+var_F0]; this
0x1800891ec  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x1800891f1  mov     r8, [rbp+320h+var_2C0]
0x1800891f5  shl     r8, 5; Size
0x1800891f9  xor     edx, edx; Val
0x1800891fb  mov     rcx, rsi; void *
0x1800891fe  call    memset_0
0x180089203  mov     rbx, [rbp+320h+var_2C8]
0x180089207  mov     rbx, [rbx]
0x18008920a  xor     edx, edx
0x18008920c  cmp     rbx, [rbp+320h+var_2C8]
0x180089210  jz      loc_18008937E
0x180089216  mov     edi, [rbx+40h]
0x180089219  shl     rdi, 5
0x18008921d  mov     rax, [r12]
0x180089221  mov     rcx, [rax+10h]
0x180089225  mov     r14, [rcx+18h]
0x180089229  mov     r15d, r15d
0x18008922c  shl     r15, 5
0x180089230  mov     rdx, [rdi+r14]
0x180089234  lea     rcx, [rbp+320h+Block]; void *
0x18008923b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180089240  nop
0x180089241  lea     r8, [rbp+320h+Block]
0x180089248  lea     rdx, [rsp+420h+var_3E0]
0x18008924d  mov     rcx, qword ptr [rsp+420h+var_3B8.dwLowDateTime]
0x180089252  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$CAdapt@V?$CSrmRefPtr@V?$CComObject@VCFciPropertyDefinition@@@ATL@@@@@ATL@@U?$CCaseInsensitiveLess@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$CAdapt@V?$CSrmRefPtr@V?$CComObject@VCFciPropertyDefinition@@@ATL@@@@@ATL@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$CAdapt@V?$CSrmRefPtr@V?$CComObject@VCFciPropertyDefinition@@@ATL@@@@@ATL@@U?$CCaseInsensitiveLess@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$CAdapt@V?$CSrmRefPtr@V?$CComObject@VCFciPropertyDefinition@@@ATL@@@@@ATL@@@std@@@2@$0A@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,ATL::CAdapt<CSrmRefPtr<ATL::CComObject<CFciPropertyDefinition>>>,CCaseInsensitiveLess<std::wstring,std::wstring>,std::allocator<std::pair<std::wstring const,ATL::CAdapt<CSrmRefPtr<ATL::CComObject<CFciPropertyDefinition>>>>>,0>>::find(std::wstring const &)
  ... truncated ...
```
