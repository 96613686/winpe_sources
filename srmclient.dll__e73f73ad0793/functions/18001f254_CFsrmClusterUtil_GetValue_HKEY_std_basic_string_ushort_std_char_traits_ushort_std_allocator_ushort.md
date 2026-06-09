# CFsrmClusterUtil::GetValue(HKEY__ *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>)

- ea: `0x18001f254`
- end: `0x18001f834`
- name: `?GetValue@CFsrmClusterUtil@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUHKEY__@@V23@@Z`
- size: `1504`
- prototype: `__int64 __fastcall(void *, HKEY hKey, LPCWSTR lpszValueName)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, registry_config, service_task`

## callers

- `0x180020d48`

## callees

- `0x180001350`
- `0x180006a1c`
- `0x1800095f4`
- `0x18000ed14`
- `0x180010b24`
- `0x180010bc4`
- `0x18001dbb0`
- `0x18001f254`
- `0x1800205f8`
- `0x1800206a4`
- `0x18006fe68`
- `0x18006febc`
- `0x1800700b8`
- `0x180073d04`
- `0x180074048`
- `0x180074a04`
- `0x1800b078a`
- `0x1800b07d0`

## import_xrefs

- `CLUSAPI!ClusterRegQueryValue` at `0x18001f32a`
- `CLUSAPI!ClusterRegQueryValue` at `0x18001f3b9`
- `CLUSAPI!ClusterRegQueryValue` at `0x18001f32a`
- `CLUSAPI!ClusterRegQueryValue` at `0x18001f3b9`

## string_xrefs

- `0x18001f2a1`: `base\fs\fsrm\service\globalstore\clusterutil.cpp`
- `0x18001f3eb`: `base\fs\fsrm\service\globalstore\clusterutil.cpp`
- `0x18001f547`: `base\fs\fsrm\service\globalstore\clusterutil.cpp`
- `0x18001f703`: `base\fs\fsrm\service\globalstore\clusterutil.cpp`
- `0x18001f7fe`: `base\fs\fsrm\service\globalstore\clusterutil.cpp`
- `0x18001f713`: `ERROR: invalid registry type`
- `0x18001f7ac`: `ERROR: invalid registry type`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
_QWORD *__fastcall CFsrmClusterUtil::GetValue(_QWORD *a1, HKEY hKey, _QWORD *lpszValueName)
{
  HKEY v4; // r14
  const WCHAR *v6; // rdx
  int v7; // eax
  BYTE *v8; // r15
  BYTE *v9; // rbx
  const WCHAR *v10; // rdx
  int v11; // eax
  DWORD v12; // r12d
  DWORD v13; // r13d
  _QWORD *v14; // r14
  DWORD v15; // ecx
  unsigned __int64 v16; // rcx
  unsigned __int64 v17; // rax
  void **v18; // rbx
  _QWORD *result; // rax
  __int64 v20; // rax
  unsigned int Hr; // eax
  __int64 v22; // rdx
  __int64 v23; // rax
  unsigned int v24; // eax
  __int64 v25; // rdx
  LPDWORD lpcbData; // [rsp+20h] [rbp-E0h]
  __int64 v27; // [rsp+28h] [rbp-D8h]
  __int16 v28; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cbData; // [rsp+48h] [rbp-B8h] BYREF
  DWORD v30; // [rsp+4Ch] [rbp-B4h] BYREF
  DWORD dwValueType[2]; // [rsp+50h] [rbp-B0h] BYREF
  HKEY v32; // [rsp+58h] [rbp-A8h]
  LPBYTE lpData[2]; // [rsp+68h] [rbp-98h] BYREF
  __int64 v34; // [rsp+78h] [rbp-88h]
  const wchar_t *v35; // [rsp+90h] [rbp-70h] BYREF
  const wchar_t *v36; // [rsp+98h] [rbp-68h]
  const wchar_t *v37; // [rsp+A0h] [rbp-60h]
  __int64 v38; // [rsp+A8h] [rbp-58h]
  int v39; // [rsp+B0h] [rbp-50h]
  _BYTE v40[96]; // [rsp+B8h] [rbp-48h] BYREF
  int v41; // [rsp+118h] [rbp+18h]
  _QWORD v42[4]; // [rsp+120h] [rbp+20h] BYREF
  int v43; // [rsp+140h] [rbp+40h]
  _BYTE v44[96]; // [rsp+148h] [rbp+48h] BYREF
  int v45; // [rsp+1A8h] [rbp+A8h]
  _QWORD *v46; // [rsp+1B0h] [rbp+B0h]
  void *Src[2]; // [rsp+1B8h] [rbp+B8h] BYREF
  __int64 v48; // [rsp+1C8h] [rbp+C8h]
  unsigned __int64 v49; // [rsp+1D0h] [rbp+D0h]
  void *Block[3]; // [rsp+1E0h] [rbp+E0h] BYREF
  unsigned __int64 v51; // [rsp+1F8h] [rbp+F8h]
  _QWORD v52[22]; // [rsp+210h] [rbp+110h] BYREF

  v4 = hKey;
  v32 = hKey;
  dwValueType[1] = HIDWORD(a1);
  v46 = lpszValueName;
  v35 = L"base\\fs\\fsrm\\service\\globalstore\\clusterutil.cpp";
  v36 = L"CFsrmClusterUtil::GetValue";
  v37 = L"CLUSUTLC";
  v38 = 384;
  v39 = 255;
  v41 = 0x1000000;
  memset_0(v40, 0, sizeof(v40));
  CSrmFunctionTracer::CSrmFunctionTracer(
    (__int64)v52,
    (const struct CSrmDebugInfo *)&v35,
    (__int64)L"CFsrmClusterUtil::GetValue");
  dwValueType[0] = 0;
  cbData = 0;
  if ( lpszValueName[3] < 8u )
    v6 = (const WCHAR *)lpszValueName;
  else
    v6 = (const WCHAR *)*lpszValueName;
  v7 = ClusterRegQueryValue(v4, v6, dwValueType, 0, &cbData);
  if ( v7 == 2 || v7 == 259 )
  {
    v42[0] = L"base\\fs\\fsrm\\service\\globalstore\\clusterutil.cpp";
    v42[1] = L"CFsrmClusterUtil::GetValue";
    v42[2] = L"CLUSUTLC";
    v42[3] = 398;
    v43 = 255;
    v45 = 0x1000000;
    memset_0(v44, 0, sizeof(v44));
    CSrmFunctionTracer::Trace(v52, v42, L"- WARNING: the value does not exist...");
    a1[3] = 7;
    a1[2] = 0;
    *(_WORD *)a1 = 0;
    std::wstring::assign(a1, (void *)&dword_1800DC394);
  }
  else
  {
    if ( v7 )
    {
      if ( v7 > 0 )
        v7 = (unsigned __int16)v7 | 0x80070000;
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)v52, v7);
      CSrmDebugInfo::CSrmDebugInfo(
        (__int64)v42,
        (__int64)L"base\\fs\\fsrm\\service\\globalstore\\clusterutil.cpp",
        (__int64)L"CLUSUTLC",
        (__int64)L"CFsrmClusterUtil::GetValue",
        409,
        0);
      Hr = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)v52);
      CSrmFunctionTracer::TranslateGenericError(v52, v22, Hr, L"ClusterRegQueryValue()");
    }
    if ( dwValueType[0] != 1 )
    {
      v23 = CSrmDebugInfo::CSrmDebugInfo(
              (__int64)v42,
              (__int64)L"base\\fs\\fsrm\\service\\globalstore\\clusterutil.cpp",
              (__int64)L"CLUSUTLC",
              (__int64)L"CFsrmClusterUtil::GetValue",
              413,
              0);
      CSrmFunctionTracer::Throw(v52, v23, 2147767062LL, L"ERROR: invalid registry type");
    }
    v30 = 2 * (cbData >> 1);
    v28 = 0;
    *(_OWORD *)lpData = 0;
    v34 = 0;
    std::vector<unsigned short>::_Construct_n(lpData, (cbData >> 1) + 1, &v28);
LABEL_9:
    v8 = lpData[0];
    v9 = lpData[1];
    while ( 1 )
    {
      v10 = lpszValueName[3] < 8u ? (const WCHAR *)lpszValueName : (const WCHAR *)*lpszValueName;
      v11 = ClusterRegQueryValue(v4, v10, dwValueType, v8, &v30);
      if ( !v11 )
        break;
      if ( v11 != 234 )
      {
        if ( v11 > 0 )
          v11 = (unsigned __int16)v11 | 0x80070000;
        CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)v52, v11);
        CSrmDebugInfo::CSrmDebugInfo(
          (__int64)v42,
          (__int64)L"base\\fs\\fsrm\\service\\globalstore\\clusterutil.cpp",
          (__int64)L"CLUSUTLC",
          (__int64)L"CFsrmClusterUtil::GetValue",
          453,
          0);
        v24 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)v52);
        CSrmFunctionTracer::TranslateGenericError(v52, v25, v24, L"ClusterRegQueryValue()");
      }
      v12 = v30;
      v13 = cbData;
      if ( lpszValueName[3] < 8u )
        v14 = lpszValueName;
      else
        v14 = (_QWORD *)*lpszValueName;
      v35 = L"base\\fs\\fsrm\\service\\globalstore\\clusterutil.cpp";
      v36 = L"CFsrmClusterUtil::GetValue";
      v37 = L"CLUSUTLC";
      v38 = 437;
      v39 = 255;
      v41 = 0x1000000;
      memset_0(v40, 0, sizeof(v40));
      LODWORD(v27) = v12;
      LODWORD(lpcbData) = v13;
      CSrmFunctionTracer::Trace(
        v52,
        &v35,
        L"ClusterRegQueryValue requires a larger buffer for %s : current size= %lu, required size= %lu",
        v14,
        lpcbData,
        v27);
      cbData = v30;
      v15 = v30 >> 1;
      v30 = 2 * (v30 >> 1);
      v28 = 0;
      v16 = v15 + 1;
      v17 = (v9 - v8) >> 1;
      if ( v17 < v16 )
      {
        std::vector<unsigned short>::_Insert_n(lpData, v9, v16 - v17, &v28);
        v4 = v32;
        goto LABEL_9;
      }
      v4 = v32;
      if ( v17 > v16 && &v8[2 * v16] != v9 )
      {
        v9 = &v8[2 * v16];
        lpData[1] = v9;
      }
    }
    if ( dwValueType[0] != 1 )
    {
      v20 = CSrmDebugInfo::CSrmDebugInfo(
              (__int64)v42,
              (__int64)L"base\\fs\\fsrm\\service\\globalstore\\clusterutil.cpp",
              (__int64)L"CLUSUTLC",
              (__int64)L"CFsrmClusterUtil::GetValue",
              461,
              0);
      CSrmFunctionTracer::Throw(v52, v20, 2147767062LL, L"ERROR: invalid registry type");
    }
    v49 = 7;
    v48 = 0;
    LOWORD(Src[0]) = 0;
    std::wstring::assign<std::_Vector_iterator<std::_Vector_val<unsigned short>>>(Src);
    v51 = 7;
    Block[2] = 0;
    LOWORD(Block[0]) = 0;
    std::wstring::assign(Block);
    v18 = Block;
    if ( v51 >= 8 )
      v18 = (void **)Block[0];
    v35 = L"base\\fs\\fsrm\\service\\globalstore\\clusterutil.cpp";
    v36 = L"CFsrmClusterUtil::GetValue";
    v37 = L"CLUSUTLC";
    v38 = 467;
    v39 = 255;
    v41 = 0x1000000;
    memset_0(v40, 0, sizeof(v40));
    CSrmFunctionTracer::Trace(v52, &v35, L"- Found data: '%s'", v18);
    if ( v51 >= 8 )
      operator delete(Block[0]);
    a1[3] = 7;
    a1[2] = 0;
    *(_WORD *)a1 = 0;
    std::wstring::assign(a1, Src);
    if ( v49 >= 8 )
      operator delete(Src[0]);
    v49 = 7;
    v48 = 0;
    LOWORD(Src[0]) = 0;
    if ( v8 )
      operator delete(v8);
  }
  v52[0] = &CSrmFunctionTracer::`vftable';
  CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)v52);
  if ( lpszValueName[3] >= 8u )
    operator delete((void *)*lpszValueName);
  lpszValueName[3] = 7;
  lpszValueName[2] = 0;
  result = a1;
  *(_WORD *)lpszValueName = 0;
  return result;
}

```

## disassembly

```asm
0x18001f254  mov     [rsp-8+arg_18], rbx
0x18001f259  push    rbp
0x18001f25a  push    rsi
0x18001f25b  push    rdi
0x18001f25c  push    r12
0x18001f25e  push    r13
0x18001f260  push    r14
0x18001f262  push    r15
0x18001f264  lea     rbp, [rsp-1D0h]
0x18001f26c  sub     rsp, 2D0h
0x18001f273  mov     rax, cs:__security_cookie
0x18001f27a  xor     rax, rsp
0x18001f27d  mov     [rbp+200h+var_40], rax
0x18001f284  mov     rdi, r8
0x18001f287  mov     r14, rdx
0x18001f28a  mov     [rsp+300h+var_2A8], rdx
0x18001f28f  mov     rsi, rcx
0x18001f292  mov     qword ptr [rsp+300h+dwValueType], rcx
0x18001f297  mov     [rbp+200h+var_150], r8
0x18001f29e  xor     r12d, r12d
0x18001f2a1  lea     rbx, aBaseFsFsrmServ_40; "base\\fs\\fsrm\\service\\globalstore\\c"...
0x18001f2a8  mov     [rbp+200h+var_270], rbx
0x18001f2ac  lea     r13, aCfsrmclusterut_7; "CFsrmClusterUtil::GetValue"
0x18001f2b3  mov     [rbp+200h+var_268], r13
0x18001f2b7  lea     r15, aClusutlc; "CLUSUTLC"
0x18001f2be  mov     [rbp+200h+var_260], r15
0x18001f2c2  mov     [rbp+200h+var_258], 180h
0x18001f2ca  mov     [rbp+200h+var_250], 0FFh
0x18001f2d1  mov     [rbp+200h+var_1E8], 1000000h
0x18001f2d8  xor     edx, edx; Val
0x18001f2da  lea     r8d, [r12+60h]; Size
0x18001f2df  lea     rcx, [rbp+200h+var_248]; void *
0x18001f2e3  call    memset_0
0x18001f2e8  mov     r8, r13
0x18001f2eb  lea     rdx, [rbp+200h+var_270]
0x18001f2ef  lea     rcx, [rbp+200h+var_F0]
0x18001f2f6  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x18001f2fb  nop
0x18001f2fc  mov     [rsp+300h+dwValueType], r12d
0x18001f301  mov     [rsp+300h+cbData], r12d
0x18001f306  cmp     qword ptr [rdi+18h], 8
0x18001f30b  jb      short loc_18001F312
0x18001f30d  mov     rdx, [rdi]
0x18001f310  jmp     short loc_18001F315
0x18001f312  mov     rdx, rdi; lpszValueName
0x18001f315  lea     rax, [rsp+300h+cbData]
0x18001f31a  mov     [rsp+300h+lpcbData], rax; lpcbData
0x18001f31f  xor     r9d, r9d; lpData
0x18001f322  lea     r8, [rsp+300h+dwValueType]; lpdwValueType
0x18001f327  mov     rcx, r14; hKey
0x18001f32a  call    cs:__imp_ClusterRegQueryValue
0x18001f330  cmp     eax, 2
0x18001f333  jz      loc_18001F615
0x18001f339  cmp     eax, 103h
0x18001f33e  jz      loc_18001F615
0x18001f344  test    eax, eax
0x18001f346  jnz     loc_18001F730
0x18001f34c  cmp     [rsp+300h+dwValueType], 1
0x18001f351  jnz     loc_18001F78D
0x18001f357  mov     ecx, [rsp+300h+cbData]
0x18001f35b  shr     ecx, 1
0x18001f35d  lea     eax, [rcx+rcx]
0x18001f360  mov     [rsp+300h+var_2B4], eax
0x18001f364  mov     [rsp+300h+var_2C0], r12w
0x18001f36a  xorps   xmm0, xmm0
0x18001f36d  movdqu  xmmword ptr [rsp+300h+lpData], xmm0
0x18001f373  mov     [rsp+300h+var_288], r12
0x18001f378  lea     edx, [rcx+1]
0x18001f37b  lea     r8, [rsp+300h+var_2C0]
0x18001f380  lea     rcx, [rsp+300h+lpData]
0x18001f385  call    ?_Construct_n@?$vector@GV?$allocator@G@std@@@std@@QEAAX_KPEBG@Z; std::vector<ushort>::_Construct_n(unsigned __int64,ushort const *)
0x18001f38a  nop
0x18001f38b  mov     r15, [rsp+300h+lpData]
0x18001f390  mov     rbx, [rsp+300h+lpData+8]
0x18001f395  cmp     qword ptr [rdi+18h], 8
0x18001f39a  jb      short loc_18001F3A1
0x18001f39c  mov     rdx, [rdi]
0x18001f39f  jmp     short loc_18001F3A4
0x18001f3a1  mov     rdx, rdi; lpszValueName
0x18001f3a4  lea     rax, [rsp+300h+var_2B4]
0x18001f3a9  mov     [rsp+300h+lpcbData], rax; lpcbData
0x18001f3ae  mov     r9, r15; lpData
0x18001f3b1  lea     r8, [rsp+300h+dwValueType]; lpdwValueType
0x18001f3b6  mov     rcx, r14; hKey
0x18001f3b9  call    cs:__imp_ClusterRegQueryValue
0x18001f3bf  test    eax, eax
0x18001f3c1  jz      loc_18001F4C6
0x18001f3c7  cmp     eax, 0EAh
0x18001f3cc  jnz     loc_18001F7C9
0x18001f3d2  mov     r12d, [rsp+300h+var_2B4]
0x18001f3d7  mov     r13d, [rsp+300h+cbData]
0x18001f3dc  cmp     qword ptr [rdi+18h], 8
0x18001f3e1  jb      short loc_18001F3E8
0x18001f3e3  mov     r14, [rdi]
0x18001f3e6  jmp     short loc_18001F3EB
0x18001f3e8  mov     r14, rdi
0x18001f3eb  lea     rax, aBaseFsFsrmServ_40; "base\\fs\\fsrm\\service\\globalstore\\c"...
0x18001f3f2  mov     [rbp+200h+var_270], rax
0x18001f3f6  lea     rax, aCfsrmclusterut_7; "CFsrmClusterUtil::GetValue"
0x18001f3fd  mov     [rbp+200h+var_268], rax
0x18001f401  lea     rax, aClusutlc; "CLUSUTLC"
0x18001f408  mov     [rbp+200h+var_260], rax
0x18001f40c  mov     [rbp+200h+var_258], 1B5h
0x18001f414  mov     [rbp+200h+var_250], 0FFh
0x18001f41b  mov     [rbp+200h+var_1E8], 1000000h
0x18001f422  xor     edx, edx; Val
0x18001f424  lea     r8d, [rdx+60h]; Size
0x18001f428  lea     rcx, [rbp+200h+var_248]; void *
0x18001f42c  call    memset_0
0x18001f431  mov     dword ptr [rsp+300h+var_2D8], r12d
0x18001f436  mov     dword ptr [rsp+300h+lpcbData], r13d
0x18001f43b  mov     r9, r14
0x18001f43e  lea     r8, aClusterregquer; "ClusterRegQueryValue requires a larger "...
0x18001f445  lea     rdx, [rbp+200h+var_270]
0x18001f449  lea     rcx, [rbp+200h+var_F0]
0x18001f450  call    ?Trace@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@PEBGZZ; CSrmFunctionTracer::Trace(CSrmDebugInfo,ushort const *,...)
0x18001f455  mov     ecx, [rsp+300h+var_2B4]
0x18001f459  mov     [rsp+300h+cbData], ecx
0x18001f45d  shr     ecx, 1
0x18001f45f  lea     eax, [rcx+rcx]
0x18001f462  mov     [rsp+300h+var_2B4], eax
0x18001f466  xor     r12d, r12d
0x18001f469  mov     [rsp+300h+var_2C0], r12w
0x18001f46f  inc     ecx
0x18001f471  mov     rax, rbx
0x18001f474  sub     rax, r15
0x18001f477  sar     rax, 1
0x18001f47a  cmp     rax, rcx
0x18001f47d  jnb     short loc_18001F4A1
0x18001f47f  sub     rcx, rax
0x18001f482  lea     r9, [rsp+300h+var_2C0]
0x18001f487  mov     r8, rcx
0x18001f48a  mov     rdx, rbx
0x18001f48d  lea     rcx, [rsp+300h+lpData]
0x18001f492  call    ?_Insert_n@?$vector@GV?$allocator@G@std@@@std@@IEAAXV?$_Vector_const_iterator@V?$_Vector_val@GV?$allocator@G@std@@@std@@@2@_KAEBG@Z; std::vector<ushort>::_Insert_n(std::_Vector_const_iterator<std::_Vector_val<ushort>>,unsigned __int64,ushort const &)
0x18001f497  mov     r14, [rsp+300h+var_2A8]
0x18001f49c  jmp     loc_18001F38B
0x18001f4a1  mov     r14, [rsp+300h+var_2A8]
0x18001f4a6  jbe     loc_18001F395
0x18001f4ac  lea     rax, [r15+rcx*2]
0x18001f4b0  cmp     rax, rbx
0x18001f4b3  jz      loc_18001F395
0x18001f4b9  mov     rbx, rax
0x18001f4bc  mov     [rsp+300h+lpData+8], rax
0x18001f4c1  jmp     loc_18001F395
0x18001f4c6  cmp     [rsp+300h+dwValueType], 1
0x18001f4cb  jnz     loc_18001F6E8
0x18001f4d1  mov     r14d, 7
0x18001f4d7  mov     [rbp+200h+var_130], r14
0x18001f4de  mov     [rbp+200h+var_138], r12
0x18001f4e5  mov     word ptr [rbp+200h+Src], r12w
0x18001f4ed  mov     r8, rbx
0x18001f4f0  mov     rdx, r15
0x18001f4f3  lea     rcx, [rbp+200h+Src]; Src
0x18001f4fa  call    ??$assign@V?$_Vector_iterator@V?$_Vector_val@GV?$allocator@G@std@@@std@@@std@@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@V?$_Vector_iterator@V?$_Vector_val@GV?$allocator@G@std@@@std@@@1@0@Z; std::wstring::assign<std::_Vector_iterator<std::_Vector_val<ushort>>>(std::_Vector_iterator<std::_Vector_val<ushort>>,std::_Vector_iterator<std::_Vector_val<ushort>>)
0x18001f4ff  mov     [rbp+200h+var_108], r14
0x18001f506  mov     [rbp+200h+var_110], r12
0x18001f50d  mov     word ptr [rbp+200h+Block], r12w
0x18001f515  lea     r9d, [r14+2Bh]
0x18001f519  xor     r8d, r8d
0x18001f51c  lea     rdx, [rbp+200h+Src]
0x18001f523  lea     rcx, [rbp+200h+Block]; void *
0x18001f52a  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x18001f52f  nop
0x18001f530  lea     rbx, [rbp+200h+Block]
0x18001f537  cmp     [rbp+200h+var_108], 8
0x18001f53f  cmovnb  rbx, [rbp+200h+Block]
0x18001f547  lea     rax, aBaseFsFsrmServ_40; "base\\fs\\fsrm\\service\\globalstore\\c"...
0x18001f54e  mov     [rbp+200h+var_270], rax
0x18001f552  lea     rax, aCfsrmclusterut_7; "CFsrmClusterUtil::GetValue"
0x18001f559  mov     [rbp+200h+var_268], rax
0x18001f55d  lea     rax, aClusutlc; "CLUSUTLC"
0x18001f564  mov     [rbp+200h+var_260], rax
0x18001f568  mov     [rbp+200h+var_258], 1D3h
0x18001f570  mov     [rbp+200h+var_250], 0FFh
0x18001f577  mov     [rbp+200h+var_1E8], 1000000h
0x18001f57e  xor     edx, edx; Val
0x18001f580  lea     r8d, [r14+59h]; Size
0x18001f584  lea     rcx, [rbp+200h+var_248]; void *
0x18001f588  call    memset_0
0x18001f58d  mov     r9, rbx
0x18001f590  lea     r8, aFoundDataS; "- Found data: '%s'"
0x18001f597  lea     rdx, [rbp+200h+var_270]
0x18001f59b  lea     rcx, [rbp+200h+var_F0]
0x18001f5a2  call    ?Trace@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@PEBGZZ; CSrmFunctionTracer::Trace(CSrmDebugInfo,ushort const *,...)
0x18001f5a7  nop
0x18001f5a8  cmp     [rbp+200h+var_108], 8
0x18001f5b0  jb      short loc_18001F5BE
0x18001f5b2  mov     rcx, [rbp+200h+Block]; Block
0x18001f5b9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001f5be  mov     [rsi+18h], r14
0x18001f5c2  mov     [rsi+10h], r12
0x18001f5c6  mov     [rsi], r12w
0x18001f5ca  lea     rdx, [rbp+200h+Src]; Src
0x18001f5d1  mov     rcx, rsi; void *
0x18001f5d4  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@$$QEAV12@@Z; std::wstring::assign(std::wstring &&)
0x18001f5d9  nop
0x18001f5da  cmp     [rbp+200h+var_130], 8
0x18001f5e2  jb      short loc_18001F5F0
0x18001f5e4  mov     rcx, [rbp+200h+Src]; Block
0x18001f5eb  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001f5f0  mov     [rbp+200h+var_130], r14
0x18001f5f7  mov     [rbp+200h+var_138], r12
0x18001f5fe  mov     word ptr [rbp+200h+Src], r12w
0x18001f606  test    r15, r15
0x18001f609  jz      short loc_18001F685
0x18001f60b  mov     rcx, r15; Block
0x18001f60e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001f613  jmp     short loc_18001F685
0x18001f615  mov     [rbp+200h+var_1E0], rbx
0x18001f619  mov     [rbp+200h+var_1D8], r13
0x18001f61d  mov     [rbp+200h+var_1D0], r15
0x18001f621  mov     [rbp+200h+var_1C8], 18Eh
0x18001f629  mov     [rbp+200h+var_1C0], 0FFh
0x18001f630  mov     [rbp+200h+var_158], 1000000h
0x18001f63a  xor     edx, edx; Val
0x18001f63c  lea     r8d, [rdx+60h]; Size
0x18001f640  lea     rcx, [rbp+200h+var_1B8]; void *
0x18001f644  call    memset_0
0x18001f649  lea     r8, aWarningTheValu; "- WARNING: the value does not exist..."
0x18001f650  lea     rdx, [rbp+200h+var_1E0]
0x18001f654  lea     rcx, [rbp+200h+var_F0]
0x18001f65b  call    ?Trace@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@PEBGZZ; CSrmFunctionTracer::Trace(CSrmDebugInfo,ushort const *,...)
0x18001f660  mov     r14d, 7
0x18001f666  mov     [rsi+18h], r14
0x18001f66a  mov     [rsi+10h], r12
0x18001f66e  mov     [rsi], r12w
0x18001f672  xor     r8d, r8d
0x18001f675  lea     rdx, dword_1800DC394; Src
0x18001f67c  mov     rcx, rsi; void *
0x18001f67f  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x18001f684  nop
0x18001f685  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x18001f68c  mov     [rbp+200h+var_F0], rax
0x18001f693  lea     rcx, [rbp+200h+var_F0]; this
0x18001f69a  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x18001f69f  nop
0x18001f6a0  cmp     qword ptr [rdi+18h], 8
0x18001f6a5  jb      short loc_18001F6AF
0x18001f6a7  mov     rcx, [rdi]; Block
0x18001f6aa  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001f6af  mov     [rdi+18h], r14
0x18001f6b3  mov     [rdi+10h], r12
0x18001f6b7  mov     rax, rsi
0x18001f6ba  mov     [rdi], r12w
0x18001f6be  mov     rcx, [rbp+200h+var_40]
0x18001f6c5  xor     rcx, rsp; StackCookie
0x18001f6c8  call    __security_check_cookie
0x18001f6cd  mov     rbx, [rsp+300h+arg_18]
0x18001f6d5  add     rsp, 2D0h
0x18001f6dc  pop     r15
0x18001f6de  pop     r14
0x18001f6e0  pop     r13
0x18001f6e2  pop     r12
0x18001f6e4  pop     rdi
0x18001f6e5  pop     rsi
0x18001f6e6  pop     rbp
0x18001f6e7  retn
0x18001f6e8  mov     dword ptr [rsp+300h+var_2D8], r12d
0x18001f6ed  mov     dword ptr [rsp+300h+lpcbData], 1CDh
0x18001f6f5  lea     r9, aCfsrmclusterut_7; "CFsrmClusterUtil::GetValue"
0x18001f6fc  lea     r8, aClusutlc; "CLUSUTLC"
0x18001f703  lea     rdx, aBaseFsFsrmServ_40; "base\\fs\\fsrm\\service\\globalstore\\c"...
0x18001f70a  lea     rcx, [rbp+200h+var_1E0]
0x18001f70e  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x18001f713  lea     r9, aErrorInvalidRe; "ERROR: invalid registry type"
0x18001f71a  mov     r8d, 80045316h
0x18001f720  mov     rdx, rax
0x18001f723  lea     rcx, [rbp+200h+var_F0]
0x18001f72a  call    ?Throw@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@JPEBGZZ; CSrmFunctionTracer::Throw(CSrmDebugInfo,long,ushort const *,...)
0x18001f730  jle     short loc_18001F73A
0x18001f732  movzx   eax, ax
0x18001f735  or      eax, 80070000h
0x18001f73a  mov     edx, eax; int
0x18001f73c  lea     rcx, [rbp+200h+var_F0]; this
0x18001f743  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x18001f748  mov     dword ptr [rsp+300h+var_2D8], r12d
0x18001f74d  mov     dword ptr [rsp+300h+lpcbData], 199h
0x18001f755  mov     r9, r13
0x18001f758  mov     r8, r15
0x18001f75b  mov     rdx, rbx
0x18001f75e  lea     rcx, [rbp+200h+var_1E0]
0x18001f762  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x18001f767  mov     rdx, rax
0x18001f76a  lea     rcx, [rbp+200h+var_F0]; this
0x18001f771  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18001f776  mov     r8d, eax
0x18001f779  lea     r9, aClusterregquer_0; "ClusterRegQueryValue()"
0x18001f780  lea     rcx, [rbp+200h+var_F0]
0x18001f787  call    ?TranslateGenericError@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@JPEBGZZ; CSrmFunctionTracer::TranslateGenericError(CSrmDebugInfo,long,ushort const *,...)
0x18001f78d  mov     dword ptr [rsp+300h+var_2D8], r12d
0x18001f792  mov     dword ptr [rsp+300h+lpcbData], 19Dh
0x18001f79a  mov     r9, r13
0x18001f79d  mov     r8, r15
0x18001f7a0  mov     rdx, rbx
0x18001f7a3  lea     rcx, [rbp+200h+var_1E0]
0x18001f7a7  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x18001f7ac  lea     r9, aErrorInvalidRe; "ERROR: invalid registry type"
0x18001f7b3  mov     r8d, 80045316h
0x18001f7b9  mov     rdx, rax
  ... truncated ...
```
