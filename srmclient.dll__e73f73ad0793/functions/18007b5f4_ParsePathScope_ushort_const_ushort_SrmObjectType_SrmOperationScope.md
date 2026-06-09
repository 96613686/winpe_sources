# ParsePathScope(ushort const *,ushort * *,_SrmObjectType *,_SrmOperationScope *)

- ea: `0x18007b5f4`
- end: `0x18007bffa`
- name: `?ParsePathScope@@YAJPEBGPEAPEAGPEAW4_SrmObjectType@@PEAW4_SrmOperationScope@@@Z`
- size: `2566`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 **, enum _SrmObjectType *, enum _SrmOperationScope *)`
- caller_count: `1`
- callee_count: `23`
- tags: `reparse_path, service_task, broker_com_uri`

## callers

- `0x18006fb7c`

## callees

- `0x1800020ba`
- `0x180006a1c`
- `0x18000ac44`
- `0x18000ad14`
- `0x18000af40`
- `0x180017fd8`
- `0x18006fe68`
- `0x18006febc`
- `0x1800700b8`
- `0x180073d04`
- `0x180074048`
- `0x180074a04`
- `0x180077704`
- `0x18007b114`
- `0x18007b4e0`
- `0x18007b5f4`
- `0x18007d4c4`
- `0x18007ecc8`
- `0x18007f760`
- `0x18007fbd8`
- `0x1800b078a`
- `0x1800b07a2`
- `0x1800b07d0`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18007bdaf`
- `ole32!CoTaskMemFree` at `0x18007bdc4`
- `ole32!CoTaskMemFree` at `0x18007bdaf`
- `ole32!CoTaskMemFree` at `0x18007bdc4`
- `OLEAUT32!__imp_SysAllocString` at `0x18007b91c`
- `OLEAUT32!__imp_SysAllocString` at `0x18007b995`
- `OLEAUT32!__imp_SysAllocString` at `0x18007b91c`
- `OLEAUT32!__imp_SysAllocString` at `0x18007b995`
- `OLEAUT32!__imp_SysFreeString` at `0x18007b957`
- `OLEAUT32!__imp_SysFreeString` at `0x18007b9b1`
- `OLEAUT32!__imp_SysFreeString` at `0x18007bda3`
- `OLEAUT32!__imp_SysFreeString` at `0x18007b957`
- `OLEAUT32!__imp_SysFreeString` at `0x18007b9b1`
- `OLEAUT32!__imp_SysFreeString` at `0x18007bda3`
- `OLEAUT32!__imp_SysStringLen` at `0x18007b936`
- `OLEAUT32!__imp_SysStringLen` at `0x18007b972`
- `OLEAUT32!__imp_SysStringLen` at `0x18007b936`
- `OLEAUT32!__imp_SysStringLen` at `0x18007b972`
- `KERNEL32!GetLastError` at `0x18007bbae`
- `KERNEL32!GetLastError` at `0x18007bbae`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x18007ba24`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x18007ba24`

## string_xrefs

- `0x18007b64b`: `base\fs\fsrm\utilities\path\srmpath.cpp`
- `0x18007b6fe`: `base\fs\fsrm\utilities\path\srmpath.cpp`
- `0x18007ba44`: `base\fs\fsrm\utilities\path\srmpath.cpp`
- `0x18007bafd`: `base\fs\fsrm\utilities\path\srmpath.cpp`
- `0x18007bc0c`: `base\fs\fsrm\utilities\path\srmpath.cpp`
- `0x18007be5d`: `base\fs\fsrm\utilities\path\srmpath.cpp`
- `0x18007bed1`: `base\fs\fsrm\utilities\path\srmpath.cpp`
- `0x18007bfc0`: `base\fs\fsrm\utilities\path\srmpath.cpp`
- `0x18007b667`: `SRMPATHC`
- `0x18007b71c`: `SRMPATHC`
- `0x18007ba62`: `SRMPATHC`
- `0x18007bb1b`: `SRMPATHC`
- `0x18007bc2a`: `SRMPATHC`
- `0x18007be56`: `SRMPATHC`
- `0x18007beca`: `SRMPATHC`
- `0x18007bfb9`: `SRMPATHC`
- `0x18007be77`: `CheckAndPreparePath(%s) failed`
- `0x18007b659`: `ParsePathScope`
- `0x18007ba53`: `ParsePathScope`
- `0x18007bb0c`: `ParsePathScope`
- `0x18007bc1b`: `ParsePathScope`
- `0x18007be4f`: `ParsePathScope`
- `0x18007bec3`: `ParsePathScope`
- `0x18007bfb2`: `ParsePathScope`
- `0x18007bc8e`: `Path<%s>`
- `0x18007bfde`: `GetVolumeNameForMountPoint(%s) returned %#x`
- `0x18007bb82`: `Mountpoint<%s>`

## pseudocode

```c
// Hidden C++ exception states: #wind=13 #try_helpers=1
__int64 __fastcall ParsePathScope(
        const unsigned __int16 *a1,
        unsigned __int16 **a2,
        enum _SrmObjectType *a3,
        enum _SrmOperationScope *a4)
{
  signed int LastError; // edi
  int v9; // r12d
  unsigned __int16 i; // cx
  __int64 v11; // r13
  unsigned __int64 v12; // rax
  const unsigned __int16 *v13; // rcx
  char *v14; // r8
  int v15; // eax
  int v16; // edx
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rbx
  wchar_t *v20; // rbx
  OLECHAR *v21; // rax
  unsigned __int16 *v22; // rbx
  UINT v23; // eax
  int v24; // eax
  OLECHAR *v25; // rbx
  UINT v26; // eax
  int v27; // eax
  unsigned int v28; // r15d
  WCHAR *v29; // rbx
  bool v30; // dl
  LPWSTR v31; // r9
  unsigned __int16 j; // cx
  wchar_t *v33; // r9
  unsigned __int16 k; // cx
  wchar_t *v35; // r9
  unsigned __int16 m; // cx
  int v37; // eax
  wchar_t *v38; // rcx
  unsigned int v39; // ebx
  unsigned __int16 *Buffer; // rbx
  __int64 v42; // rax
  unsigned int Hr; // ebx
  __int64 v44; // rax
  unsigned __int16 *v45; // r14
  unsigned int v46; // ebx
  __int64 v47; // rax
  __int64 v48; // [rsp+28h] [rbp-490h]
  wchar_t *String2; // [rsp+40h] [rbp-478h] BYREF
  int v50; // [rsp+48h] [rbp-470h]
  LPWSTR lpszVolumeName; // [rsp+50h] [rbp-468h] BYREF
  unsigned __int16 v52; // [rsp+58h] [rbp-460h]
  unsigned __int16 v53; // [rsp+5Ch] [rbp-45Ch]
  unsigned __int16 v54; // [rsp+60h] [rbp-458h]
  unsigned __int16 v55; // [rsp+64h] [rbp-454h]
  int v56; // [rsp+68h] [rbp-450h]
  const unsigned __int16 **v57; // [rsp+70h] [rbp-448h]
  LPCWSTR lpszVolumeMountPoint; // [rsp+78h] [rbp-440h] BYREF
  int pExceptionObject; // [rsp+80h] [rbp-438h] BYREF
  int v60; // [rsp+84h] [rbp-434h] BYREF
  int v61; // [rsp+88h] [rbp-430h] BYREF
  int v62; // [rsp+8Ch] [rbp-42Ch] BYREF
  int v63; // [rsp+90h] [rbp-428h]
  enum _SrmOperationScope *v64; // [rsp+98h] [rbp-420h]
  _QWORD *v65; // [rsp+A0h] [rbp-418h]
  signed int v66; // [rsp+A8h] [rbp-410h]
  unsigned __int16 **v67; // [rsp+B0h] [rbp-408h]
  enum _SrmObjectType *v68; // [rsp+B8h] [rbp-400h]
  const unsigned __int16 *v69; // [rsp+C0h] [rbp-3F8h] BYREF
  const unsigned __int16 *v70; // [rsp+C8h] [rbp-3F0h]
  const unsigned __int16 *v71; // [rsp+D0h] [rbp-3E8h]
  __int64 v72; // [rsp+D8h] [rbp-3E0h]
  int v73; // [rsp+E0h] [rbp-3D8h]
  _QWORD v74[12]; // [rsp+E8h] [rbp-3D0h] BYREF
  int v75; // [rsp+148h] [rbp-370h]
  _QWORD v76[3]; // [rsp+160h] [rbp-358h] BYREF
  int v77; // [rsp+178h] [rbp-340h]
  int v78; // [rsp+17Ch] [rbp-33Ch]
  int v79; // [rsp+180h] [rbp-338h]
  _QWORD v80[12]; // [rsp+188h] [rbp-330h]
  __int16 v81; // [rsp+1E8h] [rbp-2D0h]
  char v82; // [rsp+1EAh] [rbp-2CEh]
  char v83; // [rsp+1EBh] [rbp-2CDh]
  _QWORD v84[3]; // [rsp+1F0h] [rbp-2C8h] BYREF
  int v85; // [rsp+208h] [rbp-2B0h]
  int v86; // [rsp+20Ch] [rbp-2ACh]
  int v87; // [rsp+210h] [rbp-2A8h]
  _QWORD v88[12]; // [rsp+218h] [rbp-2A0h]
  __int16 v89; // [rsp+278h] [rbp-240h]
  char v90; // [rsp+27Ah] [rbp-23Eh]
  char v91; // [rsp+27Bh] [rbp-23Dh]
  _QWORD v92[3]; // [rsp+280h] [rbp-238h] BYREF
  int v93; // [rsp+298h] [rbp-220h]
  int v94; // [rsp+29Ch] [rbp-21Ch]
  int v95; // [rsp+2A0h] [rbp-218h]
  _QWORD v96[12]; // [rsp+2A8h] [rbp-210h]
  __int16 v97; // [rsp+308h] [rbp-1B0h]
  char v98; // [rsp+30Ah] [rbp-1AEh]
  char v99; // [rsp+30Bh] [rbp-1ADh]
  void **v100; // [rsp+310h] [rbp-1A8h] BYREF
  int v101; // [rsp+318h] [rbp-1A0h]
  _QWORD v102[22]; // [rsp+3C0h] [rbp-F8h] BYREF

  v64 = a4;
  v68 = a3;
  v67 = a2;
  v69 = L"base\\fs\\fsrm\\utilities\\path\\srmpath.cpp";
  v70 = L"ParsePathScope";
  v71 = L"SRMPATHC";
  v72 = 260;
  v73 = 255;
  v75 = 0x1000000;
  memset_0(v74, 0, sizeof(v74));
  CSrmFunctionTracer::CSrmFunctionTracer((__int64)&v100, (const struct CSrmDebugInfo *)&v69, 0);
  LastError = 0;
  *(_DWORD *)a3 = 0;
  *(_DWORD *)a4 = 0;
  *a2 = 0;
  lpszVolumeName = 0;
  String2 = 0;
  v50 = 0;
  v9 = 0;
  v56 = 0;
  v57 = (const unsigned __int16 **)v92;
  v92[0] = L"base\\fs\\fsrm\\utilities\\path\\srmpath.cpp";
  v92[1] = L"IsRecursivePattern";
  v92[2] = L"SRMPATHC";
  v93 = 76;
  v94 = 0;
  v95 = 255;
  v97 = 0;
  v98 = 0;
  v99 = 1;
  for ( i = 0; ; ++i )
  {
    v52 = i;
    if ( i >= 0xCu )
      break;
    v96[i] = 0;
  }
  CSrmFunctionTracer::CSrmFunctionTracer((__int64)v102, (const struct CSrmDebugInfo *)v92, 0);
  v11 = -1;
  v12 = -1;
  do
    ++v12;
  while ( a1[v12] );
  if ( v12 < 4 )
    goto LABEL_16;
  v13 = &a1[v12 - 4];
  v14 = (char *)((char *)L"\\..." - (char *)v13);
  do
  {
    v15 = *(unsigned __int16 *)&v14[(_QWORD)v13];
    v16 = *v13 - v15;
    if ( v16 )
      break;
    ++v13;
  }
  while ( v15 );
  if ( v16 )
  {
LABEL_16:
    v102[0] = &CSrmFunctionTracer::`vftable';
    CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)v102);
    if ( IsWildcardPattern(a1) )
    {
      v50 = 2;
      CSrmAutoPWSZ::CopyFrom((CSrmAutoPWSZ *)&String2, a1);
      v18 = -1;
      do
        ++v18;
      while ( String2[v18] );
      String2[v18 - 1] = 0;
    }
    else
    {
      v50 = 1;
      v19 = -1;
      do
        ++v19;
      while ( a1[v19] );
      if ( a1[v19 - 1] == 92 )
      {
        CSrmAutoPWSZ::CopyFrom((CSrmAutoPWSZ *)&String2, a1);
      }
      else
      {
        CSrmAutoPWSZ::Allocate((CSrmAutoPWSZ *)&String2, v19 + 1);
        v101 = StringCchPrintfW(String2, v19 + 2, L"%s\\", a1);
        if ( v101 < 0 )
        {
          Hr = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v100);
          v64 = (enum _SrmOperationScope *)v76;
          v44 = CSrmDebugInfo::CSrmDebugInfo(
                  (__int64)v76,
                  (__int64)L"base\\fs\\fsrm\\utilities\\path\\srmpath.cpp",
                  (__int64)L"SRMPATHC",
                  (__int64)L"ParsePathScope",
                  322,
                  17);
          CSrmFunctionTracer::TranslateGenericError(&v100, v44, Hr, L"StringCchPrintf failed");
        }
      }
    }
  }
  else
  {
    v102[0] = &CSrmFunctionTracer::`vftable';
    CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)v102);
    v50 = 3;
    CSrmAutoPWSZ::CopyFrom((CSrmAutoPWSZ *)&String2, a1);
    v17 = -1;
    do
      ++v17;
    while ( String2[v17] );
    String2[v17 - 3] = 0;
  }
  if ( !CheckAndPreparePath(String2) )
  {
    Buffer = CSrmOutputBuffer::GetBuffer((CSrmOutputBuffer *)&String2);
    v64 = (enum _SrmOperationScope *)v76;
    v42 = CSrmDebugInfo::CSrmDebugInfo(
            (__int64)v76,
            (__int64)L"base\\fs\\fsrm\\utilities\\path\\srmpath.cpp",
            (__int64)L"SRMPATHC",
            (__int64)L"ParsePathScope",
            329,
            17);
    CSrmFunctionTracer::Throw(&v100, v42, 2147942487LL, L"CheckAndPreparePath(%s) failed", Buffer);
  }
  lpszVolumeMountPoint = 0;
  v20 = String2;
  if ( wcsncmp_0(L"\\\\?\\", String2, 4u) )
  {
    v21 = SysAllocString(L"\\\\?\\");
    v22 = v21;
    v57 = (const unsigned __int16 **)v21;
    if ( !v21 )
    {
      pExceptionObject = -2147024882;
      throw (long *)&pExceptionObject;
    }
    v23 = SysStringLen(v21);
    v24 = CSrmComBSTR::Append((CSrmComBSTR *)&lpszVolumeMountPoint, v22, v23);
    if ( v24 < 0 )
    {
      v60 = v24;
      throw (long *)&v60;
    }
    SysFreeString(v22);
    v20 = String2;
  }
  if ( v20 )
  {
    v25 = SysAllocString(v20);
    v57 = (const unsigned __int16 **)v25;
    if ( !v25 )
    {
      v61 = -2147024882;
      throw (long *)&v61;
    }
  }
  else
  {
    v25 = 0;
    v57 = 0;
  }
  v26 = SysStringLen(v25);
  v27 = CSrmComBSTR::Append((CSrmComBSTR *)&lpszVolumeMountPoint, v25, v26);
  if ( v27 < 0 )
  {
    v62 = v27;
    throw (long *)&v62;
  }
  SysFreeString(v25);
  v28 = 49;
  v63 = 49;
  CSrmAutoPWSZ::Allocate((CSrmAutoPWSZ *)&lpszVolumeName, 0x31u);
  v29 = (WCHAR *)lpszVolumeMountPoint;
  SrmGetVolumeNameForPathName(lpszVolumeMountPoint, lpszVolumeName, 0x32u, 0, 0);
  if ( SrmIsVolumeValid(lpszVolumeName, v30) )
  {
    if ( SrmIsPathDirectoryJunction(v29) )
    {
LABEL_54:
      v9 = 2;
      v56 = 2;
      goto LABEL_71;
    }
    while ( 1 )
    {
      if ( GetVolumeNameForVolumeMountPointW(v29, lpszVolumeName, v28 + 1) )
      {
        v31 = lpszVolumeName;
        v57 = &v69;
        v69 = L"base\\fs\\fsrm\\utilities\\path\\srmpath.cpp";
        v70 = L"ParsePathScope";
        v71 = L"SRMPATHC";
        v72 = 0x1100000171LL;
        v73 = 255;
        v75 = 0x1000000;
        for ( j = 0; ; ++j )
        {
          v53 = j;
          if ( j >= 0xCu )
            break;
          v74[j] = 0;
        }
        CSrmFunctionTracer::Trace(&v100, &v69, L"Volume<%s>", v31);
        v33 = String2;
        v65 = v84;
        v84[0] = L"base\\fs\\fsrm\\utilities\\path\\srmpath.cpp";
        v84[1] = L"ParsePathScope";
        v84[2] = L"SRMPATHC";
        v85 = 370;
        v86 = 17;
        v87 = 255;
        v89 = 0;
        v90 = 0;
        v91 = 1;
        for ( k = 0; ; ++k )
        {
          v54 = k;
          if ( k >= 0xCu )
            break;
          v88[k] = 0;
        }
        CSrmFunctionTracer::Trace(&v100, v84, L"Mountpoint<%s>", v33);
        v9 = 1;
        v56 = 1;
      }
      else
      {
        LastError = GetLastError();
        v66 = LastError;
      }
      if ( LastError != 234 )
        break;
      v28 *= 2;
      v63 = v28;
      CSrmAutoPWSZ::Allocate((CSrmAutoPWSZ *)&lpszVolumeName, v28);
    }
    switch ( LastError )
    {
      case 4390:
        v35 = String2;
        v65 = v76;
        v76[0] = L"base\\fs\\fsrm\\utilities\\path\\srmpath.cpp";
        v76[1] = L"ParsePathScope";
        v76[2] = L"SRMPATHC";
        v77 = 391;
        v78 = 17;
        v79 = 255;
        v81 = 0;
        v82 = 0;
        v83 = 1;
        for ( m = 0; ; ++m )
        {
          v55 = m;
          if ( m >= 0xCu )
            break;
          v80[m] = 0;
        }
        CSrmFunctionTracer::Trace(&v100, v76, L"Path<%s>", v35);
        goto LABEL_54;
      case 2:
        v101 = -2147200252;
        goto LABEL_77;
      case 1:
        v101 = -2147200235;
        goto LABEL_77;
      case 123:
      case 3:
      case 1920:
      case 87:
        v101 = -2147200250;
        break;
      case 5:
        v101 = -2147024891;
        goto LABEL_77;
      case 1392:
        v101 = -2147200225;
        goto LABEL_77;
      default:
        if ( LastError )
        {
          v45 = CSrmOutputBuffer::GetBuffer((CSrmOutputBuffer *)&lpszVolumeMountPoint);
          if ( LastError > 0 )
            v46 = (unsigned __int16)LastError | 0x80070000;
          else
            v46 = LastError;
          v65 = v76;
          v47 = CSrmDebugInfo::CSrmDebugInfo(
                  (__int64)v76,
                  (__int64)L"base\\fs\\fsrm\\utilities\\path\\srmpath.cpp",
                  (__int64)L"SRMPATHC",
                  (__int64)L"ParsePathScope",
                  425,
                  17);
          LODWORD(v48) = LastError;
          CSrmFunctionTracer::TranslateGenericError(
            &v100,
            v47,
            v46,
            L"GetVolumeNameForMountPoint(%s) returned %#x",
            v45,
            v48);
        }
        break;
    }
  }
  else
  {
    v101 = -2147200235;
  }
LABEL_71:
  if ( v101 >= 0 )
  {
    v37 = IsVolumeRootPath(String2);
    v38 = String2;
    if ( !v37 )
    {
      do
        ++v11;
      while ( String2[v11] );
      if ( String2[v11 - 1] == 92 )
      {
        String2[v11 - 1] = 0;
        v38 = String2;
      }
    }
    String2 = 0;
    *v67 = v38;
    *(_DWORD *)v68 = v9;
    *(_DWORD *)v64 = v50;
  }
LABEL_77:
  SysFreeString(v29);
  CoTaskMemFree(String2);
  String2 = 0;
  CoTaskMemFree(lpszVolumeName);
  lpszVolumeName = 0;
  v39 = v101;
  v100 = &CSrmFunctionTracer::`vftable';
  CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)&v100);
  return v39;
}

```

## disassembly

```asm
0x18007b5f4  mov     r11, rsp
0x18007b5f7  push    rbx
0x18007b5f8  push    rsi
0x18007b5f9  push    rdi
0x18007b5fa  push    r12
0x18007b5fc  push    r13
0x18007b5fe  push    r14
0x18007b600  push    r15
0x18007b602  sub     rsp, 480h
0x18007b609  mov     rax, cs:__security_cookie
0x18007b610  xor     rax, rsp
0x18007b613  mov     [rsp+4B8h+var_48], rax
0x18007b61b  mov     r15, r9
0x18007b61e  mov     [rsp+4B8h+var_420], r9
0x18007b626  mov     r14, r8
0x18007b629  mov     [rsp+4B8h+var_400], r8
0x18007b631  mov     rbx, rdx
0x18007b634  mov     [rsp+4B8h+var_408], rdx
0x18007b63c  mov     rsi, rcx
0x18007b63f  lea     rax, [r11-3F8h]
0x18007b646  mov     [rsp+4B8h+var_448], rax
0x18007b64b  lea     rax, aBaseFsFsrmUtil_6; "base\\fs\\fsrm\\utilities\\path\\srmpat"...
0x18007b652  mov     [r11-3F8h], rax
0x18007b659  lea     rax, aParsepathscope; "ParsePathScope"
0x18007b660  mov     [r11-3F0h], rax
0x18007b667  lea     rax, aSrmpathc; "SRMPATHC"
0x18007b66e  mov     [r11-3E8h], rax
0x18007b675  mov     qword ptr [r11-3E0h], 104h
0x18007b680  xor     r12d, r12d
0x18007b683  mov     [rsp+4B8h+var_3D8], 0FFh
0x18007b68e  mov     [rsp+4B8h+var_370], 1000000h
0x18007b699  xor     edx, edx; Val
0x18007b69b  lea     r13d, [r12+1]
0x18007b6a0  lea     r8d, [r12+60h]; Size
0x18007b6a5  lea     rcx, [r11-3D0h]; void *
0x18007b6ac  call    memset_0
0x18007b6b1  nop
0x18007b6b2  xor     r8d, r8d
0x18007b6b5  lea     rdx, [rsp+4B8h+var_3F8]
0x18007b6bd  lea     rcx, [rsp+4B8h+var_1A8]
0x18007b6c5  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x18007b6ca  nop
0x18007b6cb  mov     edi, r12d
0x18007b6ce  mov     [r14], r12d
0x18007b6d1  mov     [r15], r12d
0x18007b6d4  xor     r15d, r15d
0x18007b6d7  mov     [rbx], r15
0x18007b6da  mov     [rsp+4B8h+lpszVolumeName], r15
0x18007b6df  mov     [rsp+4B8h+String2], r15
0x18007b6e4  mov     [rsp+4B8h+var_470], r15d
0x18007b6e9  mov     r12d, r15d
0x18007b6ec  mov     [rsp+4B8h+var_450], r15d
0x18007b6f1  lea     rdx, [rsp+4B8h+var_238]
0x18007b6f9  mov     [rsp+4B8h+var_448], rdx
0x18007b6fe  lea     rax, aBaseFsFsrmUtil_6; "base\\fs\\fsrm\\utilities\\path\\srmpat"...
0x18007b705  mov     [rsp+4B8h+var_238], rax
0x18007b70d  lea     rax, aIsrecursivepat; "IsRecursivePattern"
0x18007b714  mov     [rsp+4B8h+var_230], rax
0x18007b71c  lea     rax, aSrmpathc; "SRMPATHC"
0x18007b723  mov     [rsp+4B8h+var_228], rax
0x18007b72b  mov     [rsp+4B8h+var_220], 4Ch ; 'L'
0x18007b736  mov     [rsp+4B8h+var_21C], r15d
0x18007b73e  mov     [rsp+4B8h+var_218], 0FFh
0x18007b749  mov     [rsp+4B8h+var_1B0], r15w
0x18007b752  mov     [rsp+4B8h+var_1AE], r15b
0x18007b75a  mov     [rsp+4B8h+var_1AD], r13b
0x18007b762  mov     ecx, r15d
0x18007b765  mov     [rsp+4B8h+var_460], cx
0x18007b76a  cmp     cx, 0Ch
0x18007b76e  jnb     short loc_18007B781
0x18007b770  movzx   eax, cx
0x18007b773  mov     [rsp+rax*8+4B8h+var_210], r15
0x18007b77b  add     cx, r13w
0x18007b77f  jmp     short loc_18007B765
0x18007b781  xor     r8d, r8d
0x18007b784  lea     rcx, [rsp+4B8h+var_F8]
0x18007b78c  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x18007b791  nop
0x18007b792  or      r13, 0FFFFFFFFFFFFFFFFh
0x18007b796  mov     rax, r13
0x18007b799  inc     rax
0x18007b79c  cmp     [rsi+rax*2], r15w
0x18007b7a1  jnz     short loc_18007B799
0x18007b7a3  cmp     rax, 4
0x18007b7a7  jb      loc_18007B837
0x18007b7ad  lea     rcx, [rsi-8]
0x18007b7b1  lea     rcx, [rcx+rax*2]
0x18007b7b5  lea     r8, asc_1800EFAB0; "\\..."
0x18007b7bc  sub     r8, rcx
0x18007b7bf  movzx   edx, word ptr [rcx]
0x18007b7c2  movzx   eax, word ptr [rcx+r8]
0x18007b7c7  sub     edx, eax
0x18007b7c9  jnz     short loc_18007B7D3
0x18007b7cb  add     rcx, 2
0x18007b7cf  test    eax, eax
0x18007b7d1  jnz     short loc_18007B7BF
0x18007b7d3  test    edx, edx
0x18007b7d5  jnz     short loc_18007B837
0x18007b7d7  lea     r14, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x18007b7de  mov     [rsp+4B8h+var_F8], r14
0x18007b7e6  lea     rcx, [rsp+4B8h+var_F8]; this
0x18007b7ee  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x18007b7f3  mov     [rsp+4B8h+var_470], 3
0x18007b7fb  mov     rdx, rsi; unsigned __int16 *
0x18007b7fe  lea     rcx, [rsp+4B8h+String2]; this
0x18007b803  call    ?CopyFrom@CSrmAutoPWSZ@@QEAAXPEBG@Z; CSrmAutoPWSZ::CopyFrom(ushort const *)
0x18007b808  mov     rdx, [rsp+4B8h+String2]
0x18007b80d  mov     rcx, r13
0x18007b810  inc     rcx
0x18007b813  cmp     [rdx+rcx*2], r15w
0x18007b818  jnz     short loc_18007B810
0x18007b81a  mov     [rdx+rcx*2-6], r15w
0x18007b820  mov     rcx, [rsp+4B8h+String2]; String2
0x18007b825  call    ?CheckAndPreparePath@@YA_NPEAG@Z; CheckAndPreparePath(ushort *)
0x18007b82a  test    al, al
0x18007b82c  jz      loc_18007BE22
0x18007b832  jmp     loc_18007B8F2
0x18007b837  lea     r14, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x18007b83e  mov     [rsp+4B8h+var_F8], r14
0x18007b846  lea     rcx, [rsp+4B8h+var_F8]; this
0x18007b84e  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x18007b853  mov     rcx, rsi; unsigned __int16 *
0x18007b856  call    ?IsWildcardPattern@@YA_NPEBG@Z; IsWildcardPattern(ushort const *)
0x18007b85b  test    al, al
0x18007b85d  jz      short loc_18007B88E
0x18007b85f  mov     [rsp+4B8h+var_470], 2
0x18007b867  mov     rdx, rsi; unsigned __int16 *
0x18007b86a  lea     rcx, [rsp+4B8h+String2]; this
0x18007b86f  call    ?CopyFrom@CSrmAutoPWSZ@@QEAAXPEBG@Z; CSrmAutoPWSZ::CopyFrom(ushort const *)
0x18007b874  mov     rdx, [rsp+4B8h+String2]
0x18007b879  mov     rcx, r13
0x18007b87c  inc     rcx
0x18007b87f  cmp     [rdx+rcx*2], r15w
0x18007b884  jnz     short loc_18007B87C
0x18007b886  mov     [rdx+rcx*2-2], r15w
0x18007b88c  jmp     short loc_18007B820
0x18007b88e  mov     [rsp+4B8h+var_470], 1
0x18007b896  mov     rbx, r13
0x18007b899  inc     rbx
0x18007b89c  cmp     [rsi+rbx*2], r15w
0x18007b8a1  jnz     short loc_18007B899
0x18007b8a3  lea     rcx, [rsp+4B8h+String2]; this
0x18007b8a8  cmp     word ptr [rsi+rbx*2-2], 5Ch ; '\'
0x18007b8ae  jnz     short loc_18007B8BD
0x18007b8b0  mov     rdx, rsi; unsigned __int16 *
0x18007b8b3  call    ?CopyFrom@CSrmAutoPWSZ@@QEAAXPEBG@Z; CSrmAutoPWSZ::CopyFrom(ushort const *)
0x18007b8b8  jmp     loc_18007B820
0x18007b8bd  lea     rdx, [rbx+1]; unsigned __int64
0x18007b8c1  call    ?Allocate@CSrmAutoPWSZ@@QEAAX_K@Z; CSrmAutoPWSZ::Allocate(unsigned __int64)
0x18007b8c6  lea     rdx, [rbx+2]; unsigned __int64
0x18007b8ca  mov     r9, rsi
0x18007b8cd  lea     r8, aS_2; "%s\\"
0x18007b8d4  mov     rcx, [rsp+4B8h+String2]; unsigned __int16 *
0x18007b8d9  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18007b8de  mov     [rsp+4B8h+var_1A0], eax
0x18007b8e5  test    eax, eax
0x18007b8e7  js      loc_18007BE94
0x18007b8ed  jmp     loc_18007B820
0x18007b8f2  mov     [rsp+4B8h+lpszVolumeMountPoint], r15
0x18007b8f7  mov     r8d, 4; MaxCount
0x18007b8fd  mov     rbx, [rsp+4B8h+String2]
0x18007b902  mov     rdx, rbx; String2
0x18007b905  lea     rcx, asc_1800EFAE0; "\\\\?\\"
0x18007b90c  call    wcsncmp_0
0x18007b911  test    eax, eax
0x18007b913  jz      short loc_18007B962
0x18007b915  lea     rcx, asc_1800EFAE0; "\\\\?\\"
0x18007b91c  call    cs:__imp_SysAllocString
0x18007b922  mov     rbx, rax
0x18007b925  mov     [rsp+4B8h+var_448], rax
0x18007b92a  test    rax, rax
0x18007b92d  jz      loc_18007BF01
0x18007b933  mov     rcx, rbx; pbstr
0x18007b936  call    cs:__imp_SysStringLen
0x18007b93c  mov     r8d, eax; int
0x18007b93f  mov     rdx, rbx; unsigned __int16 *
0x18007b942  lea     rcx, [rsp+4B8h+lpszVolumeMountPoint]; this
0x18007b947  call    ?Append@CSrmComBSTR@@QEAAJPEBGH@Z; CSrmComBSTR::Append(ushort const *,int)
0x18007b94c  test    eax, eax
0x18007b94e  js      loc_18007BF21
0x18007b954  mov     rcx, rbx; bstrString
0x18007b957  call    cs:__imp_SysFreeString
0x18007b95d  mov     rbx, [rsp+4B8h+String2]
0x18007b962  test    rbx, rbx
0x18007b965  jnz     short loc_18007B992
0x18007b967  mov     rbx, r15
0x18007b96a  mov     [rsp+4B8h+var_448], rbx
0x18007b96f  mov     rcx, rbx; pbstr
0x18007b972  call    cs:__imp_SysStringLen
0x18007b978  mov     r8d, eax; int
0x18007b97b  mov     rdx, rbx; unsigned __int16 *
0x18007b97e  lea     rcx, [rsp+4B8h+lpszVolumeMountPoint]; this
0x18007b983  call    ?Append@CSrmComBSTR@@QEAAJPEBGH@Z; CSrmComBSTR::Append(ushort const *,int)
0x18007b988  test    eax, eax
0x18007b98a  js      loc_18007BF3D
0x18007b990  jmp     short loc_18007B9AE
0x18007b992  mov     rcx, rbx; psz
0x18007b995  call    cs:__imp_SysAllocString
0x18007b99b  mov     rbx, rax
0x18007b99e  mov     [rsp+4B8h+var_448], rax
0x18007b9a3  test    rax, rax
0x18007b9a6  jz      loc_18007BF59
0x18007b9ac  jmp     short loc_18007B96F
0x18007b9ae  mov     rcx, rbx; bstrString
0x18007b9b1  call    cs:__imp_SysFreeString
0x18007b9b7  mov     r15d, 31h ; '1'
0x18007b9bd  mov     [rsp+4B8h+var_428], r15d
0x18007b9c5  mov     edx, r15d; unsigned __int64
0x18007b9c8  lea     rcx, [rsp+4B8h+lpszVolumeName]; this
0x18007b9cd  call    ?Allocate@CSrmAutoPWSZ@@QEAAX_K@Z; CSrmAutoPWSZ::Allocate(unsigned __int64)
0x18007b9d2  xor     esi, esi
0x18007b9d4  mov     [rsp+4B8h+var_498], rsi; unsigned __int16 **
0x18007b9d9  xor     r9d, r9d; bool
0x18007b9dc  lea     r8d, [r15+1]; unsigned int
0x18007b9e0  mov     rdx, [rsp+4B8h+lpszVolumeName]; lpszVolumeName
0x18007b9e5  mov     rbx, [rsp+4B8h+lpszVolumeMountPoint]
0x18007b9ea  mov     rcx, rbx; lpszFileName
0x18007b9ed  call    ?SrmGetVolumeNameForPathName@@YAXPEBGPEAGK_NPEAPEAG@Z; SrmGetVolumeNameForPathName(ushort const *,ushort *,ulong,bool,ushort * *)
0x18007b9f2  mov     rcx, [rsp+4B8h+lpszVolumeName]; unsigned __int16 *
0x18007b9f7  call    ?SrmIsVolumeValid@@YA_NPEBG_N@Z; SrmIsVolumeValid(ushort const *,bool)
0x18007b9fc  test    al, al
0x18007b9fe  jz      loc_18007BD32
0x18007ba04  mov     rcx, rbx; lpFileName
0x18007ba07  call    ?SrmIsPathDirectoryJunction@@YA_NPEBG@Z; SrmIsPathDirectoryJunction(ushort const *)
0x18007ba0c  test    al, al
0x18007ba0e  jnz     loc_18007BCA2
0x18007ba14  lea     esi, [r15-20h]
0x18007ba18  lea     r8d, [r15+1]; cchBufferLength
0x18007ba1c  mov     rdx, [rsp+4B8h+lpszVolumeName]; lpszVolumeName
0x18007ba21  mov     rcx, rbx; lpszVolumeMountPoint
0x18007ba24  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x18007ba2a  test    eax, eax
0x18007ba2c  jz      loc_18007BBAE
0x18007ba32  mov     r9, [rsp+4B8h+lpszVolumeName]
0x18007ba37  lea     rax, [rsp+4B8h+var_3F8]
0x18007ba3f  mov     [rsp+4B8h+var_448], rax
0x18007ba44  lea     rax, aBaseFsFsrmUtil_6; "base\\fs\\fsrm\\utilities\\path\\srmpat"...
0x18007ba4b  mov     [rsp+4B8h+var_3F8], rax
0x18007ba53  lea     rax, aParsepathscope; "ParsePathScope"
0x18007ba5a  mov     [rsp+4B8h+var_3F0], rax
0x18007ba62  lea     rax, aSrmpathc; "SRMPATHC"
0x18007ba69  mov     [rsp+4B8h+var_3E8], rax
0x18007ba71  mov     [rsp+4B8h+var_3E0], 171h
0x18007ba7c  mov     [rsp+4B8h+var_3DC], esi
0x18007ba83  mov     [rsp+4B8h+var_3D8], 0FFh
0x18007ba8e  xor     r12d, r12d
0x18007ba91  mov     word ptr [rsp+4B8h+var_370], r12w
0x18007ba9a  mov     byte ptr [rsp+4B8h+var_370+2], r12b
0x18007baa2  lea     edx, [r12+1]
0x18007baa7  mov     byte ptr [rsp+4B8h+var_370+3], dl
0x18007baae  mov     ecx, r12d
0x18007bab1  mov     [rsp+4B8h+var_45C], cx
0x18007bab6  cmp     cx, 0Ch
0x18007baba  jnb     short loc_18007BACC
0x18007babc  movzx   eax, cx
0x18007babf  mov     [rsp+rax*8+4B8h+var_3D0], r12
0x18007bac7  add     cx, dx
0x18007baca  jmp     short loc_18007BAB1
0x18007bacc  lea     r8, aVolumeS; "Volume<%s>"
0x18007bad3  lea     rdx, [rsp+4B8h+var_3F8]
0x18007badb  lea     rcx, [rsp+4B8h+var_1A8]
0x18007bae3  call    ?Trace@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@PEBGZZ; CSrmFunctionTracer::Trace(CSrmDebugInfo,ushort const *,...)
0x18007bae8  mov     r9, [rsp+4B8h+String2]
0x18007baed  lea     rax, [rsp+4B8h+var_2C8]
0x18007baf5  mov     [rsp+4B8h+var_418], rax
0x18007bafd  lea     rax, aBaseFsFsrmUtil_6; "base\\fs\\fsrm\\utilities\\path\\srmpat"...
0x18007bb04  mov     [rsp+4B8h+var_2C8], rax
0x18007bb0c  lea     rax, aParsepathscope; "ParsePathScope"
0x18007bb13  mov     [rsp+4B8h+var_2C0], rax
0x18007bb1b  lea     rax, aSrmpathc; "SRMPATHC"
0x18007bb22  mov     [rsp+4B8h+var_2B8], rax
0x18007bb2a  mov     [rsp+4B8h+var_2B0], 172h
0x18007bb35  mov     [rsp+4B8h+var_2AC], esi
0x18007bb3c  mov     [rsp+4B8h+var_2A8], 0FFh
0x18007bb47  mov     [rsp+4B8h+var_240], r12w
0x18007bb50  mov     [rsp+4B8h+var_23E], r12b
0x18007bb58  mov     edx, 1
0x18007bb5d  mov     [rsp+4B8h+var_23D], dl
0x18007bb64  mov     ecx, r12d
0x18007bb67  mov     [rsp+4B8h+var_458], cx
0x18007bb6c  cmp     cx, 0Ch
0x18007bb70  jnb     short loc_18007BB82
0x18007bb72  movzx   eax, cx
0x18007bb75  mov     [rsp+rax*8+4B8h+var_2A0], r12
0x18007bb7d  add     cx, dx
0x18007bb80  jmp     short loc_18007BB67
0x18007bb82  lea     r8, aMountpointS; "Mountpoint<%s>"
0x18007bb89  lea     rdx, [rsp+4B8h+var_2C8]
0x18007bb91  lea     rcx, [rsp+4B8h+var_1A8]
0x18007bb99  call    ?Trace@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@PEBGZZ; CSrmFunctionTracer::Trace(CSrmDebugInfo,ushort const *,...)
0x18007bb9e  mov     r8d, 1
0x18007bba4  mov     r12d, r8d
0x18007bba7  mov     [rsp+4B8h+var_450], r8d
0x18007bbac  jmp     short loc_18007BBC3
0x18007bbae  call    cs:__imp_GetLastError
0x18007bbb4  mov     edi, eax
0x18007bbb6  mov     [rsp+4B8h+var_410], eax
0x18007bbbd  mov     r8d, 1
0x18007bbc3  cmp     edi, 0EAh
0x18007bbc9  jnz     short loc_18007BBEB
  ... truncated ...
```
