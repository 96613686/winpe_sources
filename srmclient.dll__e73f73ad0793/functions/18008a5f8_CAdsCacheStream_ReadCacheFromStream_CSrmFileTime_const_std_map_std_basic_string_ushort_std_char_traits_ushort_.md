# CAdsCacheStream::ReadCacheFromStream(CSrmFileTime const &,std::map<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,ATL::CAdapt<CSrmRefPtr<CSerializedPropertyDefinition>>,CCaseInsensitiveLess<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,ATL::CAdapt<CSrmRefPtr<CSerializedPropertyDefinition>>>>> const *)

- ea: `0x18008a5f8`
- end: `0x18008ae34`
- name: `?ReadCacheFromStream@CAdsCacheStream@@QEAAXAEBVCSrmFileTime@@PEBV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$CAdapt@V?$CSrmRefPtr@VCSerializedPropertyDefinition@@@@@ATL@@U?$CCaseInsensitiveLess@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$CAdapt@V?$CSrmRefPtr@VCSerializedPropertyDefinition@@@@@ATL@@@std@@@2@@std@@@Z`
- size: `2108`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180046a80`

## callees

- `0x180001350`
- `0x1800020ba`
- `0x180006a1c`
- `0x1800095f4`
- `0x18000eef4`
- `0x18001a184`
- `0x18006febc`
- `0x1800700b8`
- `0x180073a80`
- `0x180073f54`
- `0x180085a24`
- `0x1800860ac`
- `0x180088b50`
- `0x180089d38`
- `0x18008a5f8`
- `0x1800b078a`
- `0x1800b07d0`
- `0x1800d5010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18008ab4a`
- `OLEAUT32!__imp_SysAllocString` at `0x18008ab66`
- `OLEAUT32!__imp_SysAllocString` at `0x18008ab4a`
- `OLEAUT32!__imp_SysAllocString` at `0x18008ab66`
- `OLEAUT32!__imp_SysFreeString` at `0x18008ac14`
- `OLEAUT32!__imp_SysFreeString` at `0x18008ac1e`
- `OLEAUT32!__imp_SysFreeString` at `0x18008ac14`
- `OLEAUT32!__imp_SysFreeString` at `0x18008ac1e`
- `KERNEL32!CompareFileTime` at `0x18008a713`
- `KERNEL32!CompareFileTime` at `0x18008a753`
- `KERNEL32!CompareFileTime` at `0x18008a713`
- `KERNEL32!CompareFileTime` at `0x18008a753`
- `KERNEL32!LocalFree` at `0x18008ad2c`
- `KERNEL32!LocalFree` at `0x18008ad2c`

## string_xrefs

- `0x18008a64b`: `base\fs\fsrm\utilities\property\srmadscache.cpp`
- `0x18008ac48`: `base\fs\fsrm\utilities\property\srmadscache.cpp`
- `0x18008a659`: `CAdsCacheStream::ReadCacheFromStream`
- `0x18008ad94`: `Failed to de-serialize non-secure properties with status 0x%08lX from cache file '%s'`
- `0x18008aaba`: `Property name '%s' with type '%u' from cache file '%s' does not match defined property type '%u'`
- `0x18008abd2`: `Failed to apply property name '%s' with value '%s' from cache file '%s'`
- `0x18008ac57`: `CAdsCacheStream::ProcessFieldExtensions`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
void __fastcall CAdsCacheStream::ReadCacheFromStream(CPropertyBagFieldsBase **a1, const FILETIME *a2, __int64 a3)
{
  CPropertyBagFieldsBase **v4; // r15
  CPropertyBagFieldsBase **v5; // r14
  FILETIME v6; // rax
  FILETIME v7; // rax
  FILETIME v8; // rax
  unsigned __int64 *v9; // rcx
  FILETIME v10; // rax
  void **v11; // r8
  _QWORD *v12; // rdx
  unsigned int v13; // r10d
  CPropertyBagFieldsBase *v14; // rcx
  unsigned __int64 v15; // r8
  unsigned int v16; // edi
  unsigned int v17; // eax
  __int64 v18; // rax
  __int64 v19; // r11
  unsigned __int64 v20; // rax
  char *v21; // r11
  __int64 v22; // rax
  __int64 v23; // r12
  _QWORD *v24; // r13
  const OLECHAR *v25; // rcx
  BSTR v26; // rbx
  const OLECHAR *v27; // rcx
  OLECHAR *v28; // rdi
  _QWORD *v29; // rax
  _QWORD *v30; // rax
  const unsigned __int8 *v31; // r8
  unsigned __int64 v32; // rdx
  _QWORD *v33; // rax
  int Hr; // eax
  char v35; // al
  unsigned __int64 *v36; // [rsp+20h] [rbp-308h]
  __int64 v37; // [rsp+28h] [rbp-300h]
  __int64 v38; // [rsp+38h] [rbp-2F0h]
  FILETIME FileTime1; // [rsp+40h] [rbp-2E8h] BYREF
  FILETIME v40; // [rsp+48h] [rbp-2E0h] BYREF
  void **v41; // [rsp+50h] [rbp-2D8h] BYREF
  HLOCAL hMem; // [rsp+58h] [rbp-2D0h]
  OLECHAR *v43; // [rsp+60h] [rbp-2C8h]
  CPropertyBagFieldsBase **v44; // [rsp+68h] [rbp-2C0h]
  int pExceptionObject; // [rsp+78h] [rbp-2B0h] BYREF
  int v46; // [rsp+7Ch] [rbp-2ACh] BYREF
  unsigned int v47; // [rsp+80h] [rbp-2A8h]
  const unsigned __int16 **v48; // [rsp+88h] [rbp-2A0h] BYREF
  unsigned int *v49; // [rsp+90h] [rbp-298h]
  __int64 v50; // [rsp+98h] [rbp-290h]
  CPropertyBagFieldsBase **v51; // [rsp+A0h] [rbp-288h]
  int v52; // [rsp+B0h] [rbp-278h] BYREF
  const unsigned __int16 *v53; // [rsp+B8h] [rbp-270h] BYREF
  const wchar_t *v54; // [rsp+C0h] [rbp-268h]
  const unsigned __int16 *v55; // [rsp+C8h] [rbp-260h]
  int v56; // [rsp+D0h] [rbp-258h]
  int v57; // [rsp+D4h] [rbp-254h]
  int v58; // [rsp+D8h] [rbp-250h]
  _BYTE v59[96]; // [rsp+E0h] [rbp-248h] BYREF
  int v60; // [rsp+140h] [rbp-1E8h]
  _com_error *v61; // [rsp+148h] [rbp-1E0h] BYREF
  const exception *v62; // [rsp+150h] [rbp-1D8h] BYREF
  void *Block[2]; // [rsp+158h] [rbp-1D0h] BYREF
  __int64 v64; // [rsp+168h] [rbp-1C0h]
  unsigned __int64 v65; // [rsp+170h] [rbp-1B8h]
  void **v66; // [rsp+180h] [rbp-1A8h] BYREF
  int v67; // [rsp+188h] [rbp-1A0h]
  unsigned int v68; // [rsp+1ACh] [rbp-17Ch]
  _QWORD v69[22]; // [rsp+230h] [rbp-F8h] BYREF

  v4 = a1;
  v51 = a1;
  v5 = a1;
  v44 = a1;
  v50 = a3;
  v48 = &v53;
  v53 = L"base\\fs\\fsrm\\utilities\\property\\srmadscache.cpp";
  v54 = L"CAdsCacheStream::ReadCacheFromStream";
  v55 = L"SRMADSCC";
  v56 = 897;
  v57 = 17;
  v58 = 255;
  v60 = 0x1000000;
  memset_0(v59, 0, sizeof(v59));
  CSrmFunctionTracer::CSrmFunctionTracer((__int64)&v66, (const struct CSrmDebugInfo *)&v53, 0);
  if ( !(*(unsigned __int8 (__fastcall **)(CPropertyBagFieldsBase *, __int64))(*(_QWORD *)*v5 + 72LL))(*v5, 0x10000000)
    && ((_DWORD)v5[9] & 1) == 0 )
  {
    v6 = (FILETIME)v5[8];
    FileTime1 = v6;
    if ( CompareFileTime(&FileTime1, a2) == 1 )
    {
      v7 = *(FILETIME *)(*((_QWORD *)*v5 + 1) + 112LL);
      v40 = v7;
      v8 = (FILETIME)v5[8];
      FileTime1 = v8;
      if ( CompareFileTime(&v40, &FileTime1) != 1 )
      {
        v40 = 0;
        v65 = 7;
        v64 = 0;
        LOWORD(Block[0]) = 0;
        CPropertyBagFieldsBase::GetRelativePathAndName(*v5, Block);
        v9 = (unsigned __int64 *)*((_QWORD *)*v5 + 1);
        v10 = (FILETIME)v9[14];
        FileTime1 = v10;
        v11 = Block;
        if ( v65 >= 8 )
          v11 = (void **)Block[0];
        CAdsCacheStream::HashFileProperties(
          v9[8],
          v9[9],
          (const unsigned __int16 *)v11,
          FileTime1,
          (unsigned __int64 *)&v40);
        if ( v5[10] == *(CPropertyBagFieldsBase **)&v40 )
          (*(void (__fastcall **)(CPropertyBagFieldsBase *, __int64))(*(_QWORD *)*v5 + 56LL))(*v5, 0x10000000);
        if ( v65 >= 8 )
          operator delete(Block[0]);
        v65 = 7;
        v64 = 0;
        LOWORD(Block[0]) = 0;
      }
    }
  }
  hMem = 0;
  v41 = &CSrmAutoLocalPtr<_FCI_ADS_NON_SECURE_PROPERTY *>::`vftable';
  v49 = (unsigned int *)v4 + 19;
  if ( *((_DWORD *)v4 + 19) )
    CSrmAutoLocalPtr_Storage<_FCI_ADS_NON_SECURE_PROPERTY *>::AllocateBytes(&v41, 24LL * *((unsigned int *)v4 + 19));
  v12 = hMem;
  v13 = 0;
  if ( hMem )
    v13 = *v49;
  v14 = v4[12];
  if ( v14 )
    v15 = (unsigned __int64)v4[11];
  else
    v15 = 0;
  v16 = 0;
  if ( v13 )
  {
    while ( v15 >= 0x10 )
    {
      if ( *((_DWORD *)v14 + 2) <= 0x10u )
        break;
      if ( *((unsigned int *)v14 + 2) > v15 )
        break;
      v17 = *((_DWORD *)v14 + 3);
      if ( v17 <= 0x10 )
        break;
      if ( v17 >= *((_DWORD *)v14 + 2) )
        break;
      v18 = v17 - 16;
      v12[1] = 0;
      if ( (unsigned __int64)(v18 - 1) > 0xFFFE )
        break;
      if ( (v18 & 1) != 0 )
        break;
      if ( *((_WORD *)v14 + ((unsigned __int64)(unsigned int)v18 >> 1) + 7) )
        break;
      v12[1] = (char *)v14 + 16;
      v19 = *((unsigned int *)v14 + 3);
      v20 = (unsigned int)(*((_DWORD *)v14 + 2) - v19);
      v12[2] = 0;
      if ( v20 - 1 > 0xFFFE )
        break;
      if ( (v20 & 1) != 0 )
        break;
      v21 = (char *)v14 + v19;
      if ( *(_WORD *)&v21[2 * (v20 >> 1) - 2] )
        break;
      v12[2] = v21;
      *(_DWORD *)v12 = *(_DWORD *)v14;
      *((_DWORD *)v12 + 1) = *((_DWORD *)v14 + 1) & 0x5000;
      v22 = *((unsigned int *)v14 + 2);
      v15 -= v22;
      v14 = (CPropertyBagFieldsBase *)((char *)v14 + v22);
      ++v16;
      v12 += 3;
      if ( v16 >= v13 )
        goto LABEL_32;
    }
LABEL_61:
    v33 = v4 + 1;
    if ( (unsigned __int64)v4[4] >= 8 )
      v33 = (_QWORD *)*v33;
    LODWORD(v36) = -1073741811;
    CSrmFunctionTracer::Trace(
      (CSrmFunctionTracer *)&v66,
      0x28u,
      0x3A4u,
      L"Failed to de-serialize non-secure properties with status 0x%08lX from cache file '%s'",
      v36,
      v33);
    v67 = -2147200187;
    Hr = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v66);
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v66, Hr);
    v35 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v66);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v66, 0x3A6u, v35, 0);
  }
LABEL_32:
  if ( v15 )
    goto LABEL_61;
  for ( FileTime1 = 0; *(unsigned __int64 *)&FileTime1 < *v49; ++*(_QWORD *)&FileTime1 )
  {
    v23 = 3LL * *(_QWORD *)&FileTime1;
    v24 = hMem;
    v25 = (const OLECHAR *)*((_QWORD *)hMem + 3 * *(_QWORD *)&FileTime1 + 1);
    if ( v25 )
    {
      v26 = SysAllocString(v25);
      v43 = v26;
      if ( !v26 )
      {
        pExceptionObject = -2147024882;
        throw (long *)&pExceptionObject;
      }
    }
    else
    {
      v26 = 0;
      v43 = 0;
    }
    v27 = (const OLECHAR *)v24[v23 + 2];
    if ( v27 )
    {
      v28 = SysAllocString(v27);
      v40 = (FILETIME)v28;
      if ( !v28 )
      {
        v46 = -2147024882;
        throw (long *)&v46;
      }
    }
    else
    {
      v28 = 0;
      v40 = 0;
    }
    v47 = HIDWORD(v24[v23]) & 0x5000;
    std::wstring::wstring(Block, v26);
    std::_Tree<std::_Tmap_traits<std::wstring,ATL::CAdapt<CSrmRefPtr<ATL::CComObject<CFciPropertyDefinition>>>,CCaseInsensitiveLess<std::wstring,std::wstring>,std::allocator<std::pair<std::wstring const,ATL::CAdapt<CSrmRefPtr<ATL::CComObject<CFciPropertyDefinition>>>>>,0>>::find(
      v50,
      &v48,
      Block);
    if ( v65 >= 8 )
      operator delete(Block[0]);
    v65 = 7;
    v64 = 0;
    LOWORD(Block[0]) = 0;
    if ( v48 != *(const unsigned __int16 ***)(v50 + 8) && *((_DWORD *)v48[8] + 16) != LODWORD(v24[v23]) )
    {
      v29 = v51 + 1;
      if ( (unsigned __int64)v51[4] >= 8 )
        v29 = (_QWORD *)*v29;
      LODWORD(v38) = *((_DWORD *)v48[8] + 16);
      LODWORD(v37) = v24[v23];
      CSrmFunctionTracer::Trace(
        (CSrmFunctionTracer *)&v66,
        0x3Cu,
        0x3D1u,
        L"Property name '%s' with type '%u' from cache file '%s' does not match defined property type '%u'",
        v26,
        v37,
        v29,
        v38);
    }
    try
    {
      CSrmFunctionTracer::Trace((CSrmFunctionTracer *)&v66, 0x8Cu, 0x3DAu, L"prop name = %s", v26);
      CSrmFunctionTracer::Trace((CSrmFunctionTracer *)&v66, 0x8Cu, 0x3DBu, L"prop value = '%s'", v28);
      (*(void (__fastcall **)(CPropertyBagFieldsBase *, BSTR, OLECHAR *, _QWORD, _DWORD, _DWORD))(*(_QWORD *)*v4 + 80LL))(
        *v4,
        v26,
        v28,
        v47,
        0,
        0);
    }
    catch ( long v52 )
    {
      CSrmFunctionTracer::HandleHresultException(
        (CSrmFunctionTracer *)&v66,
        v52,
        L"base\\fs\\fsrm\\utilities\\property\\srmadscache.cpp",
        L"SRMADSCC",
        L"CAdsCacheStream::ReadCacheFromStream",
        0x3DFu,
        v68);
      v5 = v44;
      v4 = v44;
      v28 = (OLECHAR *)v40;
      v26 = v43;
    }
    catch ( _com_error *v61 )
    {
      CSrmFunctionTracer::HandleComException(
        (CSrmFunctionTracer *)&v66,
        v61,
        L"base\\fs\\fsrm\\utilities\\property\\srmadscache.cpp",
        L"SRMADSCC",
        L"CAdsCacheStream::ReadCacheFromStream",
        0x3DFu,
        v68);
    }
    catch ( std::bad_alloc )
    {
      CSrmFunctionTracer::HandleStdBadAllocException(
        (CSrmFunctionTracer *)&v66,
        L"base\\fs\\fsrm\\utilities\\property\\srmadscache.cpp",
        L"SRMADSCC",
        L"CAdsCacheStream::ReadCacheFromStream",
        0x3DFu,
        v68);
      v5 = v44;
      v4 = v44;
      v28 = (OLECHAR *)v40;
      v26 = v43;
    }
    catch ( const exception *v62 )
    {
      CSrmFunctionTracer::HandleStdGenericException(
        (CSrmFunctionTracer *)&v66,
        v62,
        L"base\\fs\\fsrm\\utilities\\property\\srmadscache.cpp",
        L"SRMADSCC",
        L"CAdsCacheStream::ReadCacheFromStream",
        0x3DFu,
        v68);
    }
    if ( v67 < 0 )
    {
      v30 = v51 + 1;
      if ( (unsigned __int64)v51[4] >= 8 )
        v30 = (_QWORD *)*v30;
      CSrmFunctionTracer::Trace(
        (CSrmFunctionTracer *)&v66,
        0x28u,
        0x3E3u,
        L"Failed to apply property name '%s' with value '%s' from cache file '%s'",
        v26,
        v28,
        v30);
      (*(void (__fastcall **)(CPropertyBagFieldsBase *, __int64, BSTR, _QWORD))(*(_QWORD *)*v4 + 88LL))(
        *v4,
        4453,
        v26,
        (unsigned int)v67);
    }
    SysFreeString(v28);
    SysFreeString(v26);
  }
  v48 = &v53;
  v53 = L"base\\fs\\fsrm\\utilities\\property\\srmadscache.cpp";
  v54 = L"CAdsCacheStream::ProcessFieldExtensions";
  v55 = L"SRMADSCC";
  v56 = 1250;
  v57 = 17;
  v58 = 255;
  v60 = 0x1000000;
  memset_0(v59, 0, sizeof(v59));
  CSrmFunctionTracer::CSrmFunctionTracer((__int64)v69, (const struct CSrmDebugInfo *)&v53, 0);
  v31 = (const unsigned __int8 *)v5[16];
  if ( v31 )
  {
    v32 = (unsigned __int64)v5[15];
    if ( v32 )
      CPropertyBagFieldsBase::SetNextVersionAdsFields(*v4, v32, v31);
  }
  v69[0] = &CSrmFunctionTracer::`vftable';
  CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)v69);
  (*(void (__fastcall **)(CPropertyBagFieldsBase *, __int64))(*(_QWORD *)*v4 + 56LL))(*v4, 0x1000000);
  v41 = &CSrmAuto<_FCI_ADS_NON_SECURE_PROPERTY *,CSrmAutoLocalPtr_Storage<_FCI_ADS_NON_SECURE_PROPERTY *>>::`vftable';
  if ( hMem )
    LocalFree(hMem);
  v41 = &CSrmAutoLocalPtr_Storage<void *>::`vftable';
  hMem = 0;
  v66 = &CSrmFunctionTracer::`vftable';
  CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)&v66);
}

```

## disassembly

```asm
0x18008a5f8  mov     r11, rsp
0x18008a5fb  push    rbx
0x18008a5fc  push    rsi
0x18008a5fd  push    rdi
0x18008a5fe  push    r12
0x18008a600  push    r13
0x18008a602  push    r14
0x18008a604  push    r15
0x18008a606  sub     rsp, 2F0h
0x18008a60d  mov     rax, cs:__security_cookie
0x18008a614  xor     rax, rsp
0x18008a617  mov     [rsp+328h+var_48], rax
0x18008a61f  mov     rdi, rdx
0x18008a622  mov     r15, rcx
0x18008a625  mov     [rsp+328h+var_288], rcx
0x18008a62d  mov     r14, rcx
0x18008a630  mov     [rsp+328h+var_2C0], rcx
0x18008a635  mov     [rsp+328h+var_290], r8
0x18008a63d  lea     rax, [r11-270h]
0x18008a644  mov     [r11-2A0h], rax
0x18008a64b  lea     rax, aBaseFsFsrmUtil; "base\\fs\\fsrm\\utilities\\property\\sr"...
0x18008a652  mov     [r11-270h], rax
0x18008a659  lea     rax, aCadscachestrea_4; "CAdsCacheStream::ReadCacheFromStream"
0x18008a660  mov     [r11-268h], rax
0x18008a667  lea     rax, aSrmadscc; "SRMADSCC"
0x18008a66e  mov     [r11-260h], rax
0x18008a675  mov     [rsp+328h+var_258], 381h
0x18008a680  mov     [rsp+328h+var_254], 11h
0x18008a68b  mov     [rsp+328h+var_250], 0FFh
0x18008a696  xor     esi, esi
0x18008a698  mov     [rsp+328h+var_1E8], 1000000h
0x18008a6a3  xor     edx, edx; Val
0x18008a6a5  lea     r8d, [rsi+60h]; Size
0x18008a6a9  lea     rcx, [r11-248h]; void *
0x18008a6b0  call    memset_0
0x18008a6b5  nop
0x18008a6b6  xor     r8d, r8d
0x18008a6b9  lea     rdx, [rsp+328h+var_270]
0x18008a6c1  lea     rcx, [rsp+328h+var_1A8]
0x18008a6c9  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x18008a6ce  nop
0x18008a6cf  mov     rcx, [r14]
0x18008a6d2  mov     rax, [rcx]
0x18008a6d5  mov     r12d, 10000000h
0x18008a6db  mov     edx, r12d
0x18008a6de  mov     rax, [rax+48h]
0x18008a6e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a6e7  test    al, al
0x18008a6e9  jnz     loc_18008A832
0x18008a6ef  mov     eax, [r14+48h]
0x18008a6f3  test    al, 1
0x18008a6f5  jnz     loc_18008A832
0x18008a6fb  mov     rax, [r14+40h]
0x18008a6ff  mov     [rsp+328h+FileTime1.dwLowDateTime], eax
0x18008a703  shr     rax, 20h
0x18008a707  mov     [rsp+328h+FileTime1.dwHighDateTime], eax
0x18008a70b  mov     rdx, rdi; lpFileTime2
0x18008a70e  lea     rcx, [rsp+328h+FileTime1]; lpFileTime1
0x18008a713  call    cs:__imp_CompareFileTime
0x18008a719  cmp     eax, 1
0x18008a71c  jnz     loc_18008A832
0x18008a722  mov     rax, [r14]
0x18008a725  mov     rcx, [rax+8]
0x18008a729  mov     rax, [rcx+70h]
0x18008a72d  mov     [rsp+328h+var_2E0.dwLowDateTime], eax
0x18008a731  shr     rax, 20h
0x18008a735  mov     [rsp+328h+var_2E0.dwHighDateTime], eax
0x18008a739  mov     rax, [r14+40h]
0x18008a73d  mov     [rsp+328h+FileTime1.dwLowDateTime], eax
0x18008a741  shr     rax, 20h
0x18008a745  mov     [rsp+328h+FileTime1.dwHighDateTime], eax
0x18008a749  lea     rdx, [rsp+328h+FileTime1]; lpFileTime2
0x18008a74e  lea     rcx, [rsp+328h+var_2E0]; lpFileTime1
0x18008a753  call    cs:__imp_CompareFileTime
0x18008a759  cmp     eax, 1
0x18008a75c  jz      loc_18008A832
0x18008a762  mov     qword ptr [rsp+328h+var_2E0.dwLowDateTime], rsi
0x18008a767  mov     [rsp+328h+var_1B8], 7
0x18008a773  mov     [rsp+328h+var_1C0], rsi
0x18008a77b  mov     word ptr [rsp+328h+Block], si
0x18008a783  lea     rdx, [rsp+328h+Block]
0x18008a78b  mov     rcx, [r14]
0x18008a78e  call    ?GetRelativePathAndName@CPropertyBagFieldsBase@@QEBAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CPropertyBagFieldsBase::GetRelativePathAndName(std::wstring &)
0x18008a793  mov     rax, [r14]
0x18008a796  mov     rcx, [rax+8]
0x18008a79a  mov     rax, [rcx+70h]
0x18008a79e  mov     [rsp+328h+FileTime1.dwLowDateTime], eax
0x18008a7a2  shr     rax, 20h
0x18008a7a6  mov     [rsp+328h+FileTime1.dwHighDateTime], eax
0x18008a7aa  lea     r8, [rsp+328h+Block]
0x18008a7b2  cmp     [rsp+328h+var_1B8], 8
0x18008a7bb  cmovnb  r8, [rsp+328h+Block]; unsigned __int16 *
0x18008a7c4  lea     rax, [rsp+328h+var_2E0]
0x18008a7c9  mov     [rsp+328h+var_308], rax; unsigned __int64 *
0x18008a7ce  mov     r9, qword ptr [rsp+328h+FileTime1.dwLowDateTime]; struct _FILETIME
0x18008a7d3  mov     rdx, [rcx+48h]; unsigned __int64
0x18008a7d7  mov     rcx, [rcx+40h]; unsigned __int64
0x18008a7db  call    ?HashFileProperties@CAdsCacheStream@@SAX_K0PEBGU_FILETIME@@PEA_K@Z; CAdsCacheStream::HashFileProperties(unsigned __int64,unsigned __int64,ushort const *,_FILETIME,unsigned __int64 *)
0x18008a7e0  mov     rax, qword ptr [rsp+328h+var_2E0.dwLowDateTime]
0x18008a7e5  cmp     [r14+50h], rax
0x18008a7e9  jnz     short loc_18008A7FE
0x18008a7eb  mov     rcx, [r14]
0x18008a7ee  mov     rax, [rcx]
0x18008a7f1  mov     edx, r12d
0x18008a7f4  mov     rax, [rax+38h]
0x18008a7f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a7fd  nop
0x18008a7fe  cmp     [rsp+328h+var_1B8], 8
0x18008a807  jb      short loc_18008A816
0x18008a809  mov     rcx, [rsp+328h+Block]; Block
0x18008a811  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18008a816  mov     [rsp+328h+var_1B8], 7
0x18008a822  mov     [rsp+328h+var_1C0], rsi
0x18008a82a  mov     word ptr [rsp+328h+Block], si
0x18008a832  lea     r12, ??_7?$CSrmAutoLocalPtr_Storage@PEAX@@6B@; const CSrmAutoLocalPtr_Storage<void *>::`vftable'
0x18008a839  mov     [rsp+328h+var_2D8], r12
0x18008a83e  mov     [rsp+328h+hMem], rsi
0x18008a843  lea     rax, ??_7?$CSrmAutoLocalPtr_Storage@PEAE@@6B@; const CSrmAutoLocalPtr_Storage<uchar *>::`vftable'
0x18008a84a  mov     [rsp+328h+var_2D8], rax
0x18008a84f  lea     r13, ??_7?$CSrmAuto@PEAU_FCI_ADS_NON_SECURE_PROPERTY@@V?$CSrmAutoLocalPtr_Storage@PEAU_FCI_ADS_NON_SECURE_PROPERTY@@@@@@6B@; const CSrmAuto<_FCI_ADS_NON_SECURE_PROPERTY *,CSrmAutoLocalPtr_Storage<_FCI_ADS_NON_SECURE_PROPERTY *>>::`vftable'
0x18008a856  mov     [rsp+328h+var_2D8], r13
0x18008a85b  mov     [rsp+328h+hMem], rsi
0x18008a860  lea     rax, ??_7?$CSrmAutoLocalPtr@PEAU_FCI_ADS_NON_SECURE_PROPERTY@@@@6B@; const CSrmAutoLocalPtr<_FCI_ADS_NON_SECURE_PROPERTY *>::`vftable'
0x18008a867  mov     [rsp+328h+var_2D8], rax
0x18008a86c  lea     rax, [r15+4Ch]
0x18008a870  mov     [rsp+328h+var_298], rax
0x18008a878  cmp     [rax], esi
0x18008a87a  jbe     short loc_18008A890
0x18008a87c  mov     eax, [rax]
0x18008a87e  lea     rdx, [rax+rax*2]
0x18008a882  shl     rdx, 3
0x18008a886  lea     rcx, [rsp+328h+var_2D8]
0x18008a88b  call    ?AllocateBytes@?$CSrmAutoLocalPtr_Storage@PEAU_FCI_ADS_NON_SECURE_PROPERTY@@@@QEAAX_K@Z; CSrmAutoLocalPtr_Storage<_FCI_ADS_NON_SECURE_PROPERTY *>::AllocateBytes(unsigned __int64)
0x18008a890  mov     rdx, [rsp+328h+hMem]
0x18008a895  mov     r10d, esi
0x18008a898  mov     rax, [rsp+328h+var_298]
0x18008a8a0  test    rdx, rdx
0x18008a8a3  cmovnz  r10d, [rax]
0x18008a8a7  mov     rcx, [r15+60h]
0x18008a8ab  test    rcx, rcx
0x18008a8ae  jz      short loc_18008A8B6
0x18008a8b0  mov     r8, [r15+58h]
0x18008a8b4  jmp     short loc_18008A8B9
0x18008a8b6  mov     r8, rsi
0x18008a8b9  mov     edi, esi
0x18008a8bb  test    r10d, r10d
0x18008a8be  jz      loc_18008A99A
0x18008a8c4  cmp     r8, 10h
0x18008a8c8  jb      loc_18008AD79
0x18008a8ce  cmp     dword ptr [rcx+8], 10h
0x18008a8d2  jbe     loc_18008AD79
0x18008a8d8  mov     eax, [rcx+8]
0x18008a8db  cmp     rax, r8
0x18008a8de  ja      loc_18008AD79
0x18008a8e4  mov     eax, [rcx+0Ch]
0x18008a8e7  cmp     eax, 10h
0x18008a8ea  jbe     loc_18008AD79
0x18008a8f0  cmp     eax, [rcx+8]
0x18008a8f3  jnb     loc_18008AD79
0x18008a8f9  add     eax, 0FFFFFFF0h
0x18008a8fc  mov     r9d, eax
0x18008a8ff  mov     [rdx+8], rsi
0x18008a903  dec     rax
0x18008a906  cmp     rax, 0FFFEh
0x18008a90c  ja      loc_18008AD79
0x18008a912  test    r9b, 1
0x18008a916  jnz     loc_18008AD79
0x18008a91c  lea     rax, [rcx+10h]
0x18008a920  shr     r9, 1
0x18008a923  cmp     si, [rax+r9*2-2]
0x18008a929  jnz     loc_18008AD79
0x18008a92f  mov     [rdx+8], rax
0x18008a933  mov     r11d, [rcx+0Ch]
0x18008a937  mov     eax, [rcx+8]
0x18008a93a  sub     eax, r11d
0x18008a93d  mov     r9d, eax
0x18008a940  mov     [rdx+10h], rsi
0x18008a944  dec     rax
0x18008a947  cmp     rax, 0FFFEh
0x18008a94d  ja      loc_18008AD79
0x18008a953  test    r9b, 1
0x18008a957  jnz     loc_18008AD79
0x18008a95d  add     r11, rcx
0x18008a960  shr     r9, 1
0x18008a963  cmp     si, [r11+r9*2-2]
0x18008a969  jnz     loc_18008AD79
0x18008a96f  mov     [rdx+10h], r11
0x18008a973  mov     eax, [rcx]
0x18008a975  mov     [rdx], eax
0x18008a977  mov     eax, [rcx+4]
0x18008a97a  and     eax, 5000h
0x18008a97f  mov     [rdx+4], eax
0x18008a982  mov     eax, [rcx+8]
0x18008a985  sub     r8, rax
0x18008a988  add     rcx, rax
0x18008a98b  inc     edi
0x18008a98d  add     rdx, 18h
0x18008a991  cmp     edi, r10d
0x18008a994  jb      loc_18008A8C4
0x18008a99a  test    r8, r8
0x18008a99d  jnz     loc_18008AD79
0x18008a9a3  mov     qword ptr [rsp+328h+FileTime1.dwLowDateTime], rsi
0x18008a9a8  mov     rax, [rsp+328h+var_298]
0x18008a9b0  mov     ecx, [rax]
0x18008a9b2  mov     rax, qword ptr [rsp+328h+FileTime1.dwLowDateTime]
0x18008a9b7  cmp     rax, rcx
0x18008a9ba  jnb     loc_18008AC38
0x18008a9c0  lea     r12, [rax+rax*2]
0x18008a9c4  mov     r13, [rsp+328h+hMem]
0x18008a9c9  mov     rcx, [r13+r12*8+8]; psz
0x18008a9ce  test    rcx, rcx
0x18008a9d1  jnz     loc_18008AB4A
0x18008a9d7  mov     rbx, rsi
0x18008a9da  mov     [rsp+328h+var_2C8], rbx
0x18008a9df  mov     rcx, [r13+r12*8+10h]; psz
0x18008a9e4  test    rcx, rcx
0x18008a9e7  jnz     loc_18008AB66
0x18008a9ed  mov     rdi, rsi
0x18008a9f0  mov     qword ptr [rsp+328h+var_2E0.dwLowDateTime], rsi
0x18008a9f5  mov     eax, [r13+r12*8+4]
0x18008a9fa  and     eax, 5000h
0x18008a9ff  mov     [rsp+328h+var_2A8], eax
0x18008aa06  mov     rdx, rbx
0x18008aa09  lea     rcx, [rsp+328h+Block]; void *
0x18008aa11  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x18008aa16  nop
0x18008aa17  lea     r8, [rsp+328h+Block]
0x18008aa1f  lea     rdx, [rsp+328h+var_2A0]
0x18008aa27  mov     rcx, [rsp+328h+var_290]
0x18008aa2f  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$CAdapt@V?$CSrmRefPtr@V?$CComObject@VCFciPropertyDefinition@@@ATL@@@@@ATL@@U?$CCaseInsensitiveLess@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$CAdapt@V?$CSrmRefPtr@V?$CComObject@VCFciPropertyDefinition@@@ATL@@@@@ATL@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$CAdapt@V?$CSrmRefPtr@V?$CComObject@VCFciPropertyDefinition@@@ATL@@@@@ATL@@U?$CCaseInsensitiveLess@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$CAdapt@V?$CSrmRefPtr@V?$CComObject@VCFciPropertyDefinition@@@ATL@@@@@ATL@@@std@@@2@$0A@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,ATL::CAdapt<CSrmRefPtr<ATL::CComObject<CFciPropertyDefinition>>>,CCaseInsensitiveLess<std::wstring,std::wstring>,std::allocator<std::pair<std::wstring const,ATL::CAdapt<CSrmRefPtr<ATL::CComObject<CFciPropertyDefinition>>>>>,0>>::find(std::wstring const &)
0x18008aa34  nop
0x18008aa35  cmp     [rsp+328h+var_1B8], 8
0x18008aa3e  jb      short loc_18008AA4D
0x18008aa40  mov     rcx, [rsp+328h+Block]; Block
0x18008aa48  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18008aa4d  mov     [rsp+328h+var_1B8], 7
0x18008aa59  mov     [rsp+328h+var_1C0], rsi
0x18008aa61  mov     word ptr [rsp+328h+Block], si
0x18008aa69  mov     rax, [rsp+328h+var_2A0]
0x18008aa71  mov     rcx, [rsp+328h+var_290]
0x18008aa79  cmp     rax, [rcx+8]
0x18008aa7d  jz      short loc_18008AADA
0x18008aa7f  mov     edx, [r13+r12*8+0]
0x18008aa84  mov     rcx, [rax+40h]
0x18008aa88  mov     r8d, [rcx+40h]
0x18008aa8c  cmp     r8d, edx
0x18008aa8f  jz      short loc_18008AADA
0x18008aa91  mov     rax, [rsp+328h+var_288]
0x18008aa99  add     rax, 8
0x18008aa9d  cmp     qword ptr [rax+18h], 8
0x18008aaa2  jb      short loc_18008AAA7
0x18008aaa4  mov     rax, [rax]
0x18008aaa7  mov     dword ptr [rsp+328h+var_2F0], r8d
0x18008aaac  mov     [rsp+328h+var_2F8], rax
0x18008aab1  mov     dword ptr [rsp+328h+var_300], edx
0x18008aab5  mov     [rsp+328h+var_308], rbx
0x18008aaba  lea     r9, aPropertyNameSW; "Property name '%s' with type '%u' from "...
0x18008aac1  mov     edx, 3Ch ; '<'; unsigned int
0x18008aac6  mov     r8d, 3D1h; unsigned int
0x18008aacc  lea     rcx, [rsp+328h+var_1A8]; this
0x18008aad4  call    ?Trace@CSrmFunctionTracer@@QEAAXKKPEBGZZ; CSrmFunctionTracer::Trace(ulong,ulong,ushort const *,...)
0x18008aad9  nop
0x18008aada  mov     [rsp+328h+var_308], rbx
0x18008aadf  lea     r9, aPropNameS; "prop name = %s"
0x18008aae6  mov     edx, 8Ch; unsigned int
0x18008aaeb  mov     r8d, 3DAh; unsigned int
0x18008aaf1  lea     rcx, [rsp+328h+var_1A8]; this
0x18008aaf9  call    ?Trace@CSrmFunctionTracer@@QEAAXKKPEBGZZ; CSrmFunctionTracer::Trace(ulong,ulong,ushort const *,...)
0x18008aafe  mov     [rsp+328h+var_308], rdi
0x18008ab03  lea     r9, aPropValueS; "prop value = '%s'"
0x18008ab0a  mov     edx, 8Ch; unsigned int
0x18008ab0f  mov     r8d, 3DBh; unsigned int
0x18008ab15  lea     rcx, [rsp+328h+var_1A8]; this
0x18008ab1d  call    ?Trace@CSrmFunctionTracer@@QEAAXKKPEBGZZ; CSrmFunctionTracer::Trace(ulong,ulong,ushort const *,...)
0x18008ab22  mov     rcx, [r15]
0x18008ab25  mov     rax, [rcx]
0x18008ab28  mov     dword ptr [rsp+328h+var_300], esi
0x18008ab2c  mov     dword ptr [rsp+328h+var_308], esi
0x18008ab30  mov     r9d, [rsp+328h+var_2A8]
0x18008ab38  mov     r8, rdi
0x18008ab3b  mov     rdx, rbx
0x18008ab3e  mov     rax, [rax+50h]
0x18008ab42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008ab47  nop
0x18008ab48  jmp     short loc_18008AB96
0x18008ab4a  call    cs:__imp_SysAllocString
0x18008ab50  mov     rbx, rax
0x18008ab53  mov     [rsp+328h+var_2C8], rax
0x18008ab58  test    rax, rax
0x18008ab5b  jz      loc_18008AE00
0x18008ab61  jmp     loc_18008A9DF
0x18008ab66  call    cs:__imp_SysAllocString
0x18008ab6c  mov     rdi, rax
0x18008ab6f  mov     qword ptr [rsp+328h+var_2E0.dwLowDateTime], rax
0x18008ab74  test    rax, rax
0x18008ab77  jz      loc_18008AE1A
0x18008ab7d  jmp     loc_18008A9F5
0x18008ab82  mov     r14, [rsp+328h+var_2C0]
0x18008ab87  mov     r15, r14
0x18008ab8a  mov     rdi, qword ptr [rsp+328h+var_2E0.dwLowDateTime]
  ... truncated ...
```
