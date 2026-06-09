# CPipeline::AddClassificationModulesToPipeline(void)

- ea: `0x180093344`
- end: `0x180093aa2`
- name: `?AddClassificationModulesToPipeline@CPipeline@@AEAAXXZ`
- size: `1886`
- prototype: `void __fastcall(CPipeline *__hidden this)`
- caller_count: `1`
- callee_count: `27`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180092b7c`

## callees

- `0x180006a1c`
- `0x1800095f4`
- `0x18000cda0`
- `0x18000ee10`
- `0x18000f014`
- `0x180012210`
- `0x180016540`
- `0x18001a184`
- `0x18001b4b8`
- `0x18004ff6c`
- `0x180058eb0`
- `0x18006fe68`
- `0x18006febc`
- `0x1800700b8`
- `0x180070648`
- `0x180070a14`
- `0x180071efc`
- `0x180072a80`
- `0x180073a80`
- `0x180093344`
- `0x180093ebc`
- `0x1800949fc`
- `0x18009caf8`
- `0x18009ea84`
- `0x1800b078a`
- `0x1800b07d0`
- `0x1800d5010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800934cb`
- `msvcrt!_wcsicmp` at `0x18009352e`
- `msvcrt!_wcsicmp` at `0x1800935b8`
- `msvcrt!_wcsicmp` at `0x180093610`
- `msvcrt!_wcsicmp` at `0x180093673`
- `msvcrt!_wcsicmp` at `0x1800936d3`
- `msvcrt!_wcsicmp` at `0x1800934cb`
- `msvcrt!_wcsicmp` at `0x18009352e`
- `msvcrt!_wcsicmp` at `0x1800935b8`
- `msvcrt!_wcsicmp` at `0x180093610`
- `msvcrt!_wcsicmp` at `0x180093673`
- `msvcrt!_wcsicmp` at `0x1800936d3`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180093779`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180093779`
- `KERNEL32!CompareFileTime` at `0x18009381f`
- `KERNEL32!CompareFileTime` at `0x18009381f`

## string_xrefs

- `0x18009338a`: `base\fs\fsrm\service\pipeline\pipeline.cpp`
- `0x1800938ab`: `base\fs\fsrm\service\pipeline\pipeline.cpp`
- `0x1800938dd`: `base\fs\fsrm\service\pipeline\pipeline.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
void __fastcall CPipeline::AddClassificationModulesToPipeline(CPipeline *this)
{
  __int64 v2; // rcx
  __int64 v3; // rdx
  __int64 v4; // r8
  __int64 v5; // r13
  _QWORD *v6; // rbx
  const wchar_t **v7; // r15
  const exception *v8; // r14
  __int64 *v9; // rsi
  _QWORD *v10; // r12
  const wchar_t *v11; // rcx
  const wchar_t *v12; // rdx
  const exception *v13; // rcx
  const wchar_t *v14; // rdx
  const wchar_t *v15; // rcx
  __int64 v16; // r14
  _QWORD *v17; // r13
  __int64 *v18; // rsi
  _QWORD *v19; // r12
  const wchar_t *v20; // rcx
  const wchar_t *v21; // rdx
  const wchar_t *v22; // rdx
  const wchar_t *v23; // rcx
  _QWORD *v24; // rsi
  __int64 *v25; // r14
  const wchar_t *v26; // rcx
  const wchar_t *v27; // rdx
  const wchar_t *v28; // rdx
  const wchar_t *v29; // rcx
  struct IFsrmPipelineModuleDefinition *v30; // r14
  __int64 (__fastcall ***v31)(_QWORD, GUID *, struct IFsrmCollection **); // rcx
  struct IFsrmCollection *v32; // rsi
  int v33; // eax
  struct CPipeline *v34; // r13
  struct CClassifierPipelineBuffer *v35; // r12
  __int64 v36; // rsi
  __int64 v37; // rcx
  __int64 v38; // r14
  __int64 v39; // rax
  struct _FILETIME *v40; // rax
  __int64 v41; // rax
  int Hr; // eax
  char v43; // al
  __int64 v44; // rcx
  const unsigned __int16 *v45; // rax
  ResIdOrStringParam *v46; // rax
  __int64 v47; // r9
  unsigned int v48; // ebx
  __int64 v49; // rax
  __int64 v50; // rax
  const exception *v51; // [rsp+48h] [rbp-320h]
  __int64 v52; // [rsp+50h] [rbp-318h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+58h] [rbp-310h] BYREF
  struct IFsrmCollection *v54; // [rsp+60h] [rbp-308h] BYREF
  struct IFsrmPipelineModuleDefinition *v55; // [rsp+68h] [rbp-300h]
  __int64 *v56; // [rsp+70h] [rbp-2F8h]
  __int64 v57; // [rsp+78h] [rbp-2F0h]
  __int64 *v58; // [rsp+80h] [rbp-2E8h]
  __int64 *v59; // [rsp+88h] [rbp-2E0h]
  struct CClassifierPipelineBuffer *v60; // [rsp+90h] [rbp-2D8h] BYREF
  _QWORD *v61; // [rsp+98h] [rbp-2D0h]
  __int64 v62; // [rsp+A0h] [rbp-2C8h] BYREF
  char v63; // [rsp+A8h] [rbp-2C0h]
  _QWORD *v64; // [rsp+B0h] [rbp-2B8h]
  struct CPipeline *v65; // [rsp+B8h] [rbp-2B0h]
  const FILETIME *v66; // [rsp+C0h] [rbp-2A8h] BYREF
  struct CClassifierPipelineBuffer *v67; // [rsp+C8h] [rbp-2A0h] BYREF
  __int64 v68; // [rsp+D0h] [rbp-298h]
  _QWORD *v69; // [rsp+D8h] [rbp-290h]
  int v70; // [rsp+E0h] [rbp-288h] BYREF
  const exception *v71; // [rsp+E8h] [rbp-280h]
  _BYTE *v72; // [rsp+F0h] [rbp-278h]
  _BYTE *v73; // [rsp+F8h] [rbp-270h]
  _QWORD *v74; // [rsp+100h] [rbp-268h] BYREF
  _QWORD *v75; // [rsp+108h] [rbp-260h] BYREF
  _QWORD *v76; // [rsp+110h] [rbp-258h]
  const exception *v77; // [rsp+118h] [rbp-250h]
  _com_error *v78; // [rsp+120h] [rbp-248h] BYREF
  const exception *v79[2]; // [rsp+128h] [rbp-240h] BYREF
  _QWORD v80[3]; // [rsp+138h] [rbp-230h] BYREF
  int v81; // [rsp+150h] [rbp-218h]
  int v82; // [rsp+154h] [rbp-214h]
  int v83; // [rsp+158h] [rbp-210h]
  _DWORD v84[26]; // [rsp+160h] [rbp-208h] BYREF
  _BYTE v85[152]; // [rsp+1C8h] [rbp-1A0h] BYREF
  void **v86; // [rsp+260h] [rbp-108h] BYREF
  int v87; // [rsp+268h] [rbp-100h]
  unsigned int v88; // [rsp+28Ch] [rbp-DCh]
  _BYTE v89[40]; // [rsp+310h] [rbp-58h] BYREF

  v65 = this;
  v61 = v80;
  v80[0] = L"base\\fs\\fsrm\\service\\pipeline\\pipeline.cpp";
  v80[1] = L"CPipeline::AddClassificationModulesToPipeline";
  v80[2] = L"PIPELINC";
  v81 = 226;
  v82 = 22;
  v83 = 255;
  v84[24] = 0x1000000;
  memset_0(v84, 0, 0x60u);
  CSrmFunctionTracer::CSrmFunctionTracer((__int64)&v86, (const struct CSrmDebugInfo *)v80, 0);
  v55 = 0;
  try
  {
    v2 = *(_QWORD *)this;
    v3 = *(_QWORD *)this - 8LL;
    v52 = v3;
    v4 = *(_QWORD *)this + 128LL;
    if ( !*(_QWORD *)this )
      v4 = 136;
    v61 = (_QWORD *)v4;
    v5 = v3 & -(__int64)(v2 != 0);
    v68 = v5;
    if ( v2 )
    {
      v57 = v3;
    }
    else
    {
      v52 = 0;
      v57 = 0;
    }
    v6 = **(_QWORD ***)v4;
    v69 = v6;
    while ( 1 )
    {
      if ( v6 == *(_QWORD **)v4 )
        goto LABEL_93;
      v7 = (const wchar_t **)(v6 + 2);
      v8 = *(const exception **)(v5 + 168);
      v9 = (__int64 *)*((_QWORD *)v8 + 1);
      v56 = v9;
      v71 = v8;
      v10 = v6 + 5;
      while ( !*((_BYTE *)v9 + 73) )
      {
        v11 = (const wchar_t *)(v9 + 3);
        v10 = v6 + 5;
        if ( v6[5] < 8u )
          v12 = (const wchar_t *)(v6 + 2);
        else
          v12 = *v7;
        if ( (unsigned __int64)v9[6] >= 8 )
          v11 = *(const wchar_t **)v11;
        if ( _wcsicmp(v11, v12) >= 0 )
        {
          v8 = (const exception *)v9;
          v71 = (const exception *)v9;
          v9 = (__int64 *)*v9;
        }
        else
        {
          v9 = (__int64 *)v9[2];
        }
        v56 = v9;
      }
      v13 = *(const exception **)(v5 + 168);
      v51 = v13;
      if ( v8 == v13 )
        goto LABEL_29;
      v14 = (const wchar_t *)((char *)v8 + 24);
      if ( *((_QWORD *)v8 + 6) < 8u )
        v10 = v6 + 5;
      else
        v14 = *(const wchar_t **)v14;
      v15 = *v10 < 8u ? (const wchar_t *)(v6 + 2) : *v7;
      if ( _wcsicmp(v15, v14) < 0 )
        break;
      v77 = v8;
      v13 = v8;
      v51 = v8;
LABEL_31:
      if ( v13 != *(const exception **)(v5 + 168) )
      {
        v16 = v57;
        v17 = *(_QWORD **)(v57 + 112);
        v18 = (__int64 *)v17[1];
        v58 = v18;
        v76 = v17;
        v19 = v6 + 5;
        while ( !*((_BYTE *)v18 + 73) )
        {
          v20 = (const wchar_t *)(v18 + 3);
          if ( *v19 < 8u )
            v21 = (const wchar_t *)(v6 + 2);
          else
            v21 = *v7;
          if ( (unsigned __int64)v18[6] >= 8 )
            v20 = *(const wchar_t **)v20;
          if ( _wcsicmp(v20, v21) >= 0 )
          {
            v17 = v18;
            v76 = v18;
            v18 = (__int64 *)*v18;
          }
          else
          {
            v18 = (__int64 *)v18[2];
          }
          v58 = v18;
        }
        if ( v17 == *(_QWORD **)(v16 + 112) )
          goto LABEL_51;
        v22 = (const wchar_t *)(v17 + 3);
        if ( v17[6] >= 8u )
          v22 = *(const wchar_t **)v22;
        v23 = *v19 < 8u ? (const wchar_t *)(v6 + 2) : *v7;
        if ( _wcsicmp(v23, v22) < 0 )
        {
LABEL_51:
          v17 = *(_QWORD **)(v16 + 112);
          v73 = v17;
        }
        else
        {
          v72 = v17;
        }
        v24 = *(_QWORD **)(v52 + 200);
        v25 = (__int64 *)v24[1];
        v59 = v25;
        v64 = v24;
        while ( !*((_BYTE *)v25 + 73) )
        {
          v26 = (const wchar_t *)(v25 + 3);
          if ( *v19 < 8u )
            v27 = (const wchar_t *)(v6 + 2);
          else
            v27 = *v7;
          if ( (unsigned __int64)v25[6] >= 8 )
            v26 = *(const wchar_t **)v26;
          if ( _wcsicmp(v26, v27) >= 0 )
          {
            v24 = v25;
            v64 = v25;
            v25 = (__int64 *)*v25;
          }
          else
          {
            v25 = (__int64 *)v25[2];
          }
          v59 = v25;
        }
        if ( v24 == *(_QWORD **)(v52 + 200) )
          goto LABEL_71;
        v28 = (const wchar_t *)(v24 + 3);
        if ( v24[6] >= 8u )
          v28 = *(const wchar_t **)v28;
        v29 = *v19 < 8u ? (const wchar_t *)(v6 + 2) : *v7;
        if ( _wcsicmp(v29, v28) < 0 )
        {
LABEL_71:
          v24 = *(_QWORD **)(v52 + 200);
          v75 = v24;
        }
        else
        {
          v74 = v24;
        }
        v30 = (struct IFsrmPipelineModuleDefinition *)v17[8];
        v55 = v30;
        v31 = (__int64 (__fastcall ***)(_QWORD, GUID *, struct IFsrmCollection **))*((_QWORD *)v51 + 8);
        v32 = (struct IFsrmCollection *)v24[8];
        v54 = 0;
        v33 = (**v31)(v31, &GUID_f76fbf3b_8ddd_4b42_b05a_cb1c3ff1fee8, &v54);
        v87 = v33;
        if ( v33 < 0 )
        {
          Hr = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v86);
          CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v86, Hr);
          v43 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v86);
          CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v86, 0x10Eu, v43, 0);
        }
        v87 = v33;
        v60 = 0;
        v34 = v65;
        CClassifierPipelineBuffer::CreateInstance(v65, *(struct CPipelineConfiguration **)v65, v30, v54, v32, &v60);
        GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
        v35 = v60;
        CClassifierPipelineBuffer::GetLastModified(v60, (struct CSrmFileTime *)&SystemTimeAsFileTime);
        v36 = *(_QWORD *)v34;
        v37 = *(_QWORD *)v34 + 288LL;
        if ( !*(_QWORD *)v34 )
          v37 = 296;
        v62 = v37;
        v63 = 0;
        CSrmCriticalSection::Lock((LPCRITICAL_SECTION)v37);
        v63 = 1;
        v38 = v36 + 360;
        if ( !v36 )
          v38 = 368;
        std::_Tree<std::_Tmap_traits<std::wstring,ATL::CAdapt<CSrmRefPtr<ATL::CComObject<CFciPropertyDefinition>>>,CCaseInsensitiveLess<std::wstring,std::wstring>,std::allocator<std::pair<std::wstring const,ATL::CAdapt<CSrmRefPtr<ATL::CComObject<CFciPropertyDefinition>>>>>,0>>::find(
          v38,
          &v66,
          v6 + 2);
        v39 = v36 + 368;
        if ( !v36 )
          v39 = 376;
        if ( v66 == *(const FILETIME **)v39 || CompareFileTime(&SystemTimeAsFileTime, v66 + 8) )
        {
          v40 = (struct _FILETIME *)std::map<std::wstring,CSrmFileTime,CCaseInsensitiveLess<std::wstring,std::wstring>,std::allocator<std::pair<std::wstring const,CSrmFileTime>>>::operator[](
                                      v38,
                                      v6 + 2);
          *v40 = SystemTimeAsFileTime;
          v41 = v36 + 352;
          if ( !v36 )
            v41 = 360;
          *(_BYTE *)v41 = 1;
          CSrmAutomaticLock::~CSrmAutomaticLock((LPCRITICAL_SECTION *)&v62);
        }
        else
        {
          CSrmAutomaticLock::~CSrmAutomaticLock((LPCRITICAL_SECTION *)&v62);
        }
        v67 = v35;
        std::vector<CPipelineBuffer *>::push_back((char *)v34 + 8, &v67);
        ATL::CComPtrBase<IFsrmPropertyDefinition2>::~CComPtrBase<IFsrmPropertyDefinition2>((__int64 *)&v54);
        v5 = v68;
      }
      v6 = (_QWORD *)*v6;
      v69 = v6;
      v4 = (__int64)v61;
    }
    v13 = *(const exception **)(v5 + 168);
    v51 = v13;
LABEL_29:
    v79[1] = v13;
    goto LABEL_31;
  }
  catch ( long v70 )
  {
    CSrmFunctionTracer::HandleHresultException(
      (CSrmFunctionTracer *)&v86,
      v70,
      L"base\\fs\\fsrm\\service\\pipeline\\pipeline.cpp",
      L"PIPELINC",
      L"CPipeline::AddClassificationModulesToPipeline",
      0x12Bu,
      v88);
  }
  catch ( _com_error *v78 )
  {
    CSrmFunctionTracer::HandleComException(
      (CSrmFunctionTracer *)&v86,
      v78,
      L"base\\fs\\fsrm\\service\\pipeline\\pipeline.cpp",
      L"PIPELINC",
      L"CPipeline::AddClassificationModulesToPipeline",
      0x12Bu,
      v88);
  }
  catch ( std::bad_alloc )
  {
    CSrmFunctionTracer::HandleStdBadAllocException(
      (CSrmFunctionTracer *)&v86,
      L"base\\fs\\fsrm\\service\\pipeline\\pipeline.cpp",
      L"PIPELINC",
      L"CPipeline::AddClassificationModulesToPipeline",
      0x12Bu,
      v88);
  }
  catch ( const exception *v79 )
  {
    CSrmFunctionTracer::HandleStdGenericException(
      (CSrmFunctionTracer *)&v86,
      v79[0],
      L"base\\fs\\fsrm\\service\\pipeline\\pipeline.cpp",
      L"PIPELINC",
      L"CPipeline::AddClassificationModulesToPipeline",
      0x12Bu,
      v88);
  }
LABEL_93:
  if ( v87 < 0 )
  {
    std::wstring::wstring(v89);
    CPipeline::GetModuleName(v44, v55, v89);
    v45 = (const unsigned __int16 *)std::wstring::c_str(v89);
    ResIdOrStringParam::ResIdOrStringParam((ResIdOrStringParam *)&v75, v45);
    v46 = ResIdOrStringParam::ResIdOrStringParam((ResIdOrStringParam *)&v74, 0x60Fu);
    CSrmFunctionTracerBase::AddContext(&v86, 1, v46, v47);
    v48 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v86);
    v73 = v85;
    v49 = CSrmDebugInfo::CSrmDebugInfo(
            (__int64)v85,
            (__int64)L"base\\fs\\fsrm\\service\\pipeline\\pipeline.cpp",
            (__int64)L"PIPELINC",
            (__int64)L"CPipeline::AddClassificationModulesToPipeline",
            307,
            22);
    CSrmFunctionTracer::AddGenericErrorContext(&v86, v49, v48);
    v72 = v85;
    v50 = CSrmDebugInfo::CSrmDebugInfo(
            (__int64)v85,
            (__int64)L"base\\fs\\fsrm\\service\\pipeline\\pipeline.cpp",
            (__int64)L"PIPELINC",
            (__int64)L"CPipeline::AddClassificationModulesToPipeline",
            309,
            22);
    CSrmFunctionTracer::LogError((__int64)&v86, 0x8004202C, v50, 1u);
    CSrmFunctionTracer::ReThrow((CSrmFunctionTracer *)&v86);
  }
  v86 = &CSrmFunctionTracer::`vftable';
  CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)&v86);
}

```

## disassembly

```asm
0x180093344  mov     r11, rsp
0x180093347  mov     [r11+10h], rbx
0x18009334b  mov     [r11+18h], rsi
0x18009334f  push    rdi
0x180093350  push    r12
0x180093352  push    r13
0x180093354  push    r14
0x180093356  push    r15
0x180093358  sub     rsp, 340h
0x18009335f  mov     rax, cs:__security_cookie
0x180093366  xor     rax, rsp
0x180093369  mov     [rsp+368h+var_30], rax
0x180093371  mov     rbx, rcx
0x180093374  mov     [rsp+368h+var_2B0], rcx
0x18009337c  lea     rax, [r11-230h]
0x180093383  mov     [r11-2D0h], rax
0x18009338a  lea     rsi, aBaseFsFsrmServ_43; "base\\fs\\fsrm\\service\\pipeline\\pipe"...
0x180093391  mov     [r11-230h], rsi
0x180093398  lea     r15, aCpipelineAddcl; "CPipeline::AddClassificationModulesToPi"...
0x18009339f  mov     [r11-228h], r15
0x1800933a6  lea     r12, aPipelinc; "PIPELINC"
0x1800933ad  mov     [r11-220h], r12
0x1800933b4  mov     [rsp+368h+var_218], 0E2h
0x1800933bf  mov     [rsp+368h+var_214], 16h
0x1800933ca  mov     [rsp+368h+var_210], 0FFh
0x1800933d5  xor     edi, edi
0x1800933d7  mov     [rsp+368h+var_1A8], 1000000h
0x1800933e2  xor     edx, edx; Val
0x1800933e4  lea     r8d, [rdi+60h]; Size
0x1800933e8  lea     rcx, [r11-208h]; void *
0x1800933ef  call    memset_0
0x1800933f4  nop
0x1800933f5  xor     r8d, r8d
0x1800933f8  lea     rdx, [rsp+368h+var_230]
0x180093400  lea     rcx, [rsp+368h+var_108]
0x180093408  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x18009340d  nop
0x18009340e  mov     [rsp+368h+var_300], rdi
0x180093413  mov     rcx, [rbx]
0x180093416  lea     rdx, [rcx-8]
0x18009341a  mov     [rsp+368h+var_318], rdx
0x18009341f  lea     r8, [rcx+80h]
0x180093426  mov     eax, 88h
0x18009342b  test    rcx, rcx
0x18009342e  cmovz   r8, rax
0x180093432  mov     [rsp+368h+var_2D0], r8
0x18009343a  mov     rax, rcx
0x18009343d  neg     rax
0x180093440  sbb     r13, r13
0x180093443  and     r13, rdx
0x180093446  mov     [rsp+368h+var_298], r13
0x18009344e  test    rcx, rcx
0x180093451  jz      short loc_18009345A
0x180093453  mov     [rsp+368h+var_2F0], rdx
0x180093458  jmp     short loc_180093464
0x18009345a  mov     [rsp+368h+var_318], rdi
0x18009345f  mov     [rsp+368h+var_2F0], rdi
0x180093464  mov     rbx, [r8]
0x180093467  mov     rbx, [rbx]
0x18009346a  mov     [rsp+368h+var_290], rbx
0x180093472  mov     rax, [r8]
0x180093475  mov     [rsp+368h+var_320], rax
0x18009347a  cmp     rbx, rax
0x18009347d  jnz     short loc_180093484
0x18009347f  jmp     loc_1800938E4
0x180093484  lea     r15, [rbx+10h]
0x180093488  mov     r14, [r13+0A8h]
0x18009348f  mov     rsi, [r14+8]
0x180093493  mov     [rsp+368h+var_2F8], rsi
0x180093498  mov     [rsp+368h+var_280], r14
0x1800934a0  lea     r12, [r15+18h]
0x1800934a4  cmp     [rsi+49h], dil
0x1800934a8  jnz     short loc_1800934F0
0x1800934aa  lea     rcx, [rsi+18h]
0x1800934ae  lea     r12, [r15+18h]
0x1800934b2  cmp     qword ptr [r12], 8
0x1800934b7  jb      short loc_1800934BE
0x1800934b9  mov     rdx, [r15]
0x1800934bc  jmp     short loc_1800934C1
0x1800934be  mov     rdx, r15; String2
0x1800934c1  cmp     qword ptr [rcx+18h], 8
0x1800934c6  jb      short loc_1800934CB
0x1800934c8  mov     rcx, [rcx]; String1
0x1800934cb  call    cs:__imp__wcsicmp
0x1800934d1  test    eax, eax
0x1800934d3  jns     short loc_1800934DB
0x1800934d5  mov     rsi, [rsi+10h]
0x1800934d9  jmp     short loc_1800934E9
0x1800934db  mov     r14, rsi
0x1800934de  mov     [rsp+368h+var_280], rsi
0x1800934e6  mov     rsi, [rsi]
0x1800934e9  mov     [rsp+368h+var_2F8], rsi
0x1800934ee  jmp     short loc_1800934A4
0x1800934f0  mov     [rsp+368h+var_320], r14
0x1800934f5  mov     rcx, [r13+0A8h]
0x1800934fc  mov     [rsp+368h+var_320], rcx
0x180093501  mov     [rsp+368h+var_328], rcx
0x180093506  cmp     r14, rcx
0x180093509  jz      short loc_180093544
0x18009350b  lea     rdx, [r14+18h]; String2
0x18009350f  cmp     qword ptr [rdx+18h], 8
0x180093514  jb      short loc_18009351B
0x180093516  mov     rdx, [rdx]
0x180093519  jmp     short loc_18009351F
0x18009351b  lea     r12, [r15+18h]
0x18009351f  cmp     qword ptr [r12], 8
0x180093524  jb      short loc_18009352B
0x180093526  mov     rcx, [r15]
0x180093529  jmp     short loc_18009352E
0x18009352b  mov     rcx, r15; String1
0x18009352e  call    cs:__imp__wcsicmp
0x180093534  test    eax, eax
0x180093536  jns     short loc_18009354E
0x180093538  mov     rcx, [r13+0A8h]
0x18009353f  mov     [rsp+368h+var_320], rcx
0x180093544  mov     [rsp+368h+var_238], rcx
0x18009354c  jmp     short loc_18009355E
0x18009354e  mov     [rsp+368h+var_250], r14
0x180093556  mov     rcx, r14
0x180093559  mov     [rsp+368h+var_320], rcx
0x18009355e  mov     rax, [r13+0A8h]
0x180093565  mov     [rsp+368h+var_328], rax
0x18009356a  cmp     rcx, rax
0x18009356d  jnz     short loc_180093574
0x18009356f  jmp     loc_18009389B
0x180093574  mov     r14, [rsp+368h+var_2F0]
0x180093579  mov     r13, [r14+70h]
0x18009357d  mov     rsi, [r13+8]
0x180093581  mov     [rsp+368h+var_2E8], rsi
0x180093589  mov     [rsp+368h+var_258], r13
0x180093591  lea     r12, [r15+18h]
0x180093595  cmp     [rsi+49h], dil
0x180093599  jnz     short loc_1800935E0
0x18009359b  lea     rcx, [rsi+18h]
0x18009359f  cmp     qword ptr [r12], 8
0x1800935a4  jb      short loc_1800935AB
0x1800935a6  mov     rdx, [r15]
0x1800935a9  jmp     short loc_1800935AE
0x1800935ab  mov     rdx, r15; String2
0x1800935ae  cmp     qword ptr [rcx+18h], 8
0x1800935b3  jb      short loc_1800935B8
0x1800935b5  mov     rcx, [rcx]; String1
0x1800935b8  call    cs:__imp__wcsicmp
0x1800935be  test    eax, eax
0x1800935c0  jns     short loc_1800935C8
0x1800935c2  mov     rsi, [rsi+10h]
0x1800935c6  jmp     short loc_1800935D6
0x1800935c8  mov     r13, rsi
0x1800935cb  mov     [rsp+368h+var_258], rsi
0x1800935d3  mov     rsi, [rsi]
0x1800935d6  mov     [rsp+368h+var_2E8], rsi
0x1800935de  jmp     short loc_180093595
0x1800935e0  mov     [rsp+368h+var_328], r13
0x1800935e5  mov     rax, [r14+70h]
0x1800935e9  mov     [rsp+368h+var_328], rax
0x1800935ee  cmp     r13, rax
0x1800935f1  jz      short loc_180093624
0x1800935f3  lea     rdx, [r13+18h]
0x1800935f7  cmp     qword ptr [rdx+18h], 8
0x1800935fc  jb      short loc_180093601
0x1800935fe  mov     rdx, [rdx]; String2
0x180093601  cmp     qword ptr [r12], 8
0x180093606  jb      short loc_18009360D
0x180093608  mov     rcx, [r15]
0x18009360b  jmp     short loc_180093610
0x18009360d  mov     rcx, r15; String1
0x180093610  call    cs:__imp__wcsicmp
0x180093616  test    eax, eax
0x180093618  js      short loc_180093624
0x18009361a  mov     [rsp+368h+var_278], r13
0x180093622  jmp     short loc_180093630
0x180093624  mov     r13, [r14+70h]
0x180093628  mov     [rsp+368h+var_270], r13
0x180093630  mov     rax, [rsp+368h+var_318]
0x180093635  mov     rsi, [rax+0C8h]
0x18009363c  mov     r14, [rsi+8]
0x180093640  mov     [rsp+368h+var_2E0], r14
0x180093648  mov     [rsp+368h+var_2B8], rsi
0x180093650  cmp     [r14+49h], dil
0x180093654  jnz     short loc_18009369B
0x180093656  lea     rcx, [r14+18h]
0x18009365a  cmp     qword ptr [r12], 8
0x18009365f  jb      short loc_180093666
0x180093661  mov     rdx, [r15]
0x180093664  jmp     short loc_180093669
0x180093666  mov     rdx, r15; String2
0x180093669  cmp     qword ptr [rcx+18h], 8
0x18009366e  jb      short loc_180093673
0x180093670  mov     rcx, [rcx]; String1
0x180093673  call    cs:__imp__wcsicmp
0x180093679  test    eax, eax
0x18009367b  jns     short loc_180093683
0x18009367d  mov     r14, [r14+10h]
0x180093681  jmp     short loc_180093691
0x180093683  mov     rsi, r14
0x180093686  mov     [rsp+368h+var_2B8], r14
0x18009368e  mov     r14, [r14]
0x180093691  mov     [rsp+368h+var_2E0], r14
0x180093699  jmp     short loc_180093650
0x18009369b  mov     [rsp+368h+var_328], rsi
0x1800936a0  mov     r14, [rsp+368h+var_318]
0x1800936a5  mov     rax, [r14+0C8h]
0x1800936ac  mov     [rsp+368h+var_328], rax
0x1800936b1  cmp     rsi, rax
0x1800936b4  jz      short loc_1800936E7
0x1800936b6  lea     rdx, [rsi+18h]
0x1800936ba  cmp     qword ptr [rdx+18h], 8
0x1800936bf  jb      short loc_1800936C4
0x1800936c1  mov     rdx, [rdx]; String2
0x1800936c4  cmp     qword ptr [r12], 8
0x1800936c9  jb      short loc_1800936D0
0x1800936cb  mov     rcx, [r15]
0x1800936ce  jmp     short loc_1800936D3
0x1800936d0  mov     rcx, r15; String1
0x1800936d3  call    cs:__imp__wcsicmp
0x1800936d9  test    eax, eax
0x1800936db  js      short loc_1800936E7
0x1800936dd  mov     [rsp+368h+var_268], rsi
0x1800936e5  jmp     short loc_1800936F6
0x1800936e7  mov     rsi, [r14+0C8h]
0x1800936ee  mov     [rsp+368h+var_260], rsi
0x1800936f6  mov     r14, [r13+40h]
0x1800936fa  mov     [rsp+368h+var_300], r14
0x1800936ff  mov     rax, [rsp+368h+var_320]
0x180093704  mov     rcx, [rax+40h]
0x180093708  mov     rsi, [rsi+40h]
0x18009370c  mov     [rsp+368h+var_308], rdi
0x180093711  mov     rax, [rcx]
0x180093714  lea     r8, [rsp+368h+var_308]
0x180093719  lea     rdx, _GUID_f76fbf3b_8ddd_4b42_b05a_cb1c3ff1fee8
0x180093720  mov     rax, [rax]
0x180093723  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093728  mov     [rsp+368h+var_100], eax
0x18009372f  test    eax, eax
0x180093731  js      loc_180093940
0x180093737  mov     [rsp+368h+var_100], eax
0x18009373e  mov     [rsp+368h+var_2D8], rdi
0x180093746  lea     rax, [rsp+368h+var_2D8]
0x18009374e  mov     [rsp+368h+var_340], rax; struct CClassifierPipelineBuffer **
0x180093753  mov     [rsp+368h+var_348], rsi; struct IFsrmCollection *
0x180093758  mov     r9, [rsp+368h+var_308]; struct IFsrmCollection *
0x18009375d  mov     r8, r14; struct IFsrmPipelineModuleDefinition *
0x180093760  mov     r13, [rsp+368h+var_2B0]
0x180093768  mov     rdx, [r13+0]; struct CPipelineConfiguration *
0x18009376c  mov     rcx, r13; struct CPipeline *
0x18009376f  call    ?CreateInstance@CClassifierPipelineBuffer@@SAXAEAVCPipeline@@PEAVCPipelineConfiguration@@PEAUIFsrmPipelineModuleDefinition@@PEAUIFsrmCollection@@3PEAPEAV1@@Z; CClassifierPipelineBuffer::CreateInstance(CPipeline &,CPipelineConfiguration *,IFsrmPipelineModuleDefinition *,IFsrmCollection *,IFsrmCollection *,CClassifierPipelineBuffer * *)
0x180093774  lea     rcx, [rsp+368h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180093779  call    cs:__imp_GetSystemTimeAsFileTime
0x18009377f  lea     rdx, [rsp+368h+SystemTimeAsFileTime]; struct CSrmFileTime *
0x180093784  mov     r12, [rsp+368h+var_2D8]
0x18009378c  mov     rcx, r12; this
0x18009378f  call    ?GetLastModified@CClassifierPipelineBuffer@@QEAAXAEAVCSrmFileTime@@@Z; CClassifierPipelineBuffer::GetLastModified(CSrmFileTime &)
0x180093794  mov     rsi, [r13+0]
0x180093798  lea     rcx, [rsi+120h]
0x18009379f  mov     eax, 128h
0x1800937a4  test    rsi, rsi
0x1800937a7  cmovz   rcx, rax; lpCriticalSection
0x1800937ab  mov     [rsp+368h+var_2C8], rcx
0x1800937b3  mov     [rsp+368h+var_2C0], dil
0x1800937bb  call    ?Lock@CSrmCriticalSection@@QEAAXXZ; CSrmCriticalSection::Lock(void)
0x1800937c0  mov     [rsp+368h+var_2C0], 1
0x1800937c8  lea     r14, [rsi+168h]
0x1800937cf  mov     eax, 170h
0x1800937d4  test    rsi, rsi
0x1800937d7  cmovz   r14, rax
0x1800937db  mov     r8, r15
0x1800937de  lea     rdx, [rsp+368h+var_2A8]
0x1800937e6  mov     rcx, r14
0x1800937e9  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$CAdapt@V?$CSrmRefPtr@V?$CComObject@VCFciPropertyDefinition@@@ATL@@@@@ATL@@U?$CCaseInsensitiveLess@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$CAdapt@V?$CSrmRefPtr@V?$CComObject@VCFciPropertyDefinition@@@ATL@@@@@ATL@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$CAdapt@V?$CSrmRefPtr@V?$CComObject@VCFciPropertyDefinition@@@ATL@@@@@ATL@@U?$CCaseInsensitiveLess@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$CAdapt@V?$CSrmRefPtr@V?$CComObject@VCFciPropertyDefinition@@@ATL@@@@@ATL@@@std@@@2@$0A@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,ATL::CAdapt<CSrmRefPtr<ATL::CComObject<CFciPropertyDefinition>>>,CCaseInsensitiveLess<std::wstring,std::wstring>,std::allocator<std::pair<std::wstring const,ATL::CAdapt<CSrmRefPtr<ATL::CComObject<CFciPropertyDefinition>>>>>,0>>::find(std::wstring const &)
0x1800937ee  lea     rax, [rsi+170h]
0x1800937f5  mov     ecx, 178h
0x1800937fa  test    rsi, rsi
0x1800937fd  cmovz   rax, rcx
0x180093801  mov     rax, [rax]
0x180093804  mov     [rsp+368h+var_328], rax
0x180093809  mov     rdx, [rsp+368h+var_2A8]
0x180093811  cmp     rdx, rax
0x180093814  jz      short loc_180093838
0x180093816  add     rdx, 40h ; '@'; lpFileTime2
0x18009381a  lea     rcx, [rsp+368h+SystemTimeAsFileTime]; lpFileTime1
0x18009381f  call    cs:__imp_CompareFileTime
0x180093825  test    eax, eax
0x180093827  jnz     short loc_180093838
0x180093829  lea     rcx, [rsp+368h+var_2C8]; this
0x180093831  call    ??1CSrmAutomaticLock@@QEAA@XZ; CSrmAutomaticLock::~CSrmAutomaticLock(void)
0x180093836  jmp     short loc_18009386E
0x180093838  mov     rdx, r15
0x18009383b  mov     rcx, r14
0x18009383e  call    ??A?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VCSrmFileTime@@U?$CCaseInsensitiveLess@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VCSrmFileTime@@@std@@@2@@std@@QEAAAEAVCSrmFileTime@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,CSrmFileTime,CCaseInsensitiveLess<std::wstring,std::wstring>,std::allocator<std::pair<std::wstring const,CSrmFileTime>>>::operator[](std::wstring const &)
0x180093843  mov     rcx, qword ptr [rsp+368h+SystemTimeAsFileTime.dwLowDateTime]
0x180093848  mov     [rax], rcx
0x18009384b  lea     rax, [rsi+160h]
0x180093852  mov     ecx, 168h
0x180093857  test    rsi, rsi
0x18009385a  cmovz   rax, rcx
0x18009385e  mov     byte ptr [rax], 1
0x180093861  lea     rcx, [rsp+368h+var_2C8]; this
0x180093869  call    ??1CSrmAutomaticLock@@QEAA@XZ; CSrmAutomaticLock::~CSrmAutomaticLock(void)
0x18009386e  mov     [rsp+368h+var_2A0], r12
0x180093876  lea     rcx, [r13+8]
  ... truncated ...
```
