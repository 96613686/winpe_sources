# SaveInBoxModuleDefinitions(ulong,int)

- ea: `0x18001c1f0`
- end: `0x18001cb7d`
- name: `?SaveInBoxModuleDefinitions@@YAXKH@Z`
- size: `2445`
- prototype: `void __fastcall(unsigned int, int)`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18000d560`

## callees

- `0x180001350`
- `0x1800020ba`
- `0x180006a1c`
- `0x1800095f4`
- `0x18000af40`
- `0x18001b800`
- `0x18001b8cc`
- `0x18001bc58`
- `0x18001bd9c`
- `0x18001c1f0`
- `0x18001cb84`
- `0x180039858`
- `0x18006febc`
- `0x1800700b8`
- `0x180070648`
- `0x180073a80`
- `0x1800b078a`
- `0x1800b07d0`
- `0x1800d5010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18001c690`
- `ole32!CoTaskMemFree` at `0x18001c769`
- `ole32!CoTaskMemFree` at `0x18001c690`
- `ole32!CoTaskMemFree` at `0x18001c769`
- `OLEAUT32!__imp_SysAllocString` at `0x18001c3e2`
- `OLEAUT32!__imp_SysAllocString` at `0x18001c3fe`
- `OLEAUT32!__imp_SysAllocString` at `0x18001c3e2`
- `OLEAUT32!__imp_SysAllocString` at `0x18001c3fe`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c825`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c831`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c825`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c831`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18001c69f`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18001c778`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18001c69f`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18001c778`

## string_xrefs

- `0x18001c217`: `base\fs\fsrm\service\globalstore\inboxmodules.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=13 #try_helpers=1
void __fastcall SaveInBoxModuleDefinitions()
{
  __int64 StringW; // rax
  __int64 v1; // rax
  struct tagSAFEARRAY *v2; // rbx
  int v3; // eax
  __int64 v4; // r15
  struct tagSAFEARRAY *v5; // r14
  struct CFciModuleDefinitionBase *v6; // rdx
  int v7; // eax
  __int64 v8; // rdx
  int v9; // eax
  int v10; // eax
  char *v11; // rbx
  int v12; // eax
  char *v13; // r15
  char *v14; // r14
  struct CFciModuleDefinitionBase *v15; // rdx
  SAFEARRAY *v16; // r15
  const unsigned __int16 *v17; // rdx
  int v18; // eax
  int v19; // eax
  SAFEARRAY *v20; // r15
  const unsigned __int16 *v21; // rdx
  int v22; // eax
  int v23; // eax
  int v24; // eax
  int v25; // eax
  int Hr; // eax
  char v27; // r8
  int v28; // eax
  char v29; // r8
  int v30; // eax
  char v31; // al
  int v32; // eax
  char v33; // al
  int v34; // eax
  char v35; // al
  int v36; // eax
  char v37; // al
  int v38; // eax
  char v39; // al
  int v40; // eax
  char v41; // al
  int v42; // eax
  char v43; // al
  int v44; // eax
  char v45; // al
  int v46; // eax
  char v47; // al
  int i; // [rsp+40h] [rbp-268h]
  int j; // [rsp+40h] [rbp-268h]
  LPVOID pv; // [rsp+48h] [rbp-260h] BYREF
  struct tagSAFEARRAY *v51; // [rsp+50h] [rbp-258h] BYREF
  __int64 v52; // [rsp+58h] [rbp-250h] BYREF
  int v53; // [rsp+60h] [rbp-248h] BYREF
  int v54; // [rsp+64h] [rbp-244h]
  BSTR bstrString; // [rsp+68h] [rbp-240h]
  BSTR v56; // [rsp+70h] [rbp-238h]
  int pExceptionObject; // [rsp+78h] [rbp-230h] BYREF
  int v58; // [rsp+7Ch] [rbp-22Ch] BYREF
  char *v59; // [rsp+80h] [rbp-228h]
  void **v60; // [rsp+88h] [rbp-220h]
  struct tagSAFEARRAY *v61; // [rsp+90h] [rbp-218h]
  void **v62; // [rsp+98h] [rbp-210h]
  struct tagSAFEARRAY *v63; // [rsp+A0h] [rbp-208h]
  int v64; // [rsp+ACh] [rbp-1FCh] BYREF
  _com_error *v65; // [rsp+C0h] [rbp-1E8h] BYREF
  const exception *v66; // [rsp+C8h] [rbp-1E0h] BYREF
  _QWORD v67[4]; // [rsp+D0h] [rbp-1D8h] BYREF
  int v68; // [rsp+F0h] [rbp-1B8h]
  _DWORD v69[26]; // [rsp+F8h] [rbp-1B0h] BYREF
  void **v70; // [rsp+160h] [rbp-148h] BYREF
  int v71; // [rsp+168h] [rbp-140h]
  unsigned int v72; // [rsp+18Ch] [rbp-11Ch]
  void *Block[3]; // [rsp+210h] [rbp-98h] BYREF
  unsigned __int64 v74; // [rsp+228h] [rbp-80h]
  void *v75[3]; // [rsp+238h] [rbp-70h] BYREF
  unsigned __int64 v76; // [rsp+250h] [rbp-58h]

  v67[0] = L"base\\fs\\fsrm\\service\\globalstore\\inboxmodules.cpp";
  v67[1] = L"SaveInBoxModuleDefinitions";
  v67[2] = L"CINBOXMD";
  v67[3] = 499;
  v68 = 255;
  v69[24] = 0x1000000;
  memset_0(v69, 0, 0x60u);
  CSrmFunctionTracer::CSrmFunctionTracer((__int64)&v70, (const struct CSrmDebugInfo *)v67, 0);
  v51 = (struct tagSAFEARRAY *)1856;
  v52 = 0;
  CSrmFunctionTracerBase::AddContext(&v70, 0, &v52, &v51);
  StringW = CSrmResource::LoadStringW(Block, 0xFE6u);
  if ( *(_QWORD *)(StringW + 24) >= 8u )
    StringW = *(_QWORD *)StringW;
  if ( StringW )
  {
    v56 = SysAllocString((const OLECHAR *)StringW);
    if ( !v56 )
    {
      pExceptionObject = -2147024882;
      throw (long *)&pExceptionObject;
    }
  }
  else
  {
    v56 = 0;
  }
  if ( v74 >= 8 )
    operator delete(Block[0]);
  v74 = 7;
  Block[2] = 0;
  LOWORD(Block[0]) = 0;
  v1 = CSrmResource::LoadStringW(v75, 0xFE7u);
  if ( *(_QWORD *)(v1 + 24) >= 8u )
    v1 = *(_QWORD *)v1;
  if ( v1 )
  {
    bstrString = SysAllocString((const OLECHAR *)v1);
    if ( !bstrString )
    {
      v58 = -2147024882;
      throw (long *)&v58;
    }
  }
  else
  {
    bstrString = 0;
  }
  if ( v76 >= 8 )
    operator delete(v75[0]);
  v76 = 7;
  v75[2] = 0;
  LOWORD(v75[0]) = 0;
  v54 = 0;
  for ( i = 0; (unsigned __int64)i < 4; ++i )
  {
    if ( *(_DWORD *)(0x18000004CLL + 104LL * i + 1151776) > v54 && !*(_BYTE *)(0x180000050LL + 104LL * i + 1151776) )
    {
      v52 = 0;
      v2 = 0;
      v51 = 0;
      v3 = ATL::CComObject<CFciStorageModuleDefinition>::CreateInstance(&v52);
      v71 = v3;
      if ( v3 < 0 )
      {
        Hr = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v70);
        CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v70, Hr);
        v27 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v70);
        CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v70, 0x218u, v27, 0);
      }
      v71 = v3;
      v4 = v52;
      v5 = (struct tagSAFEARRAY *)(v52 + 16);
      if ( v52 != -16 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)&v5->cDims + 8LL))(v52 + 16);
        v2 = v5;
        v51 = v5;
      }
      v6 = (struct CFciModuleDefinitionBase *)(v4 + 24);
      if ( !v4 )
        v6 = 0;
      SetCommonModuleParams((struct InBoxModuleDefinition *)(0x180000000LL + 104LL * i + 1151776), v6, v56, bstrString);
      v7 = (*(__int64 (__fastcall **)(struct tagSAFEARRAY *, _QWORD))(*(_QWORD *)&v5->cDims + 256LL))(
             v5,
             (unsigned int)dword_180119378[26 * i]);
      v71 = v7;
      if ( v7 < 0 )
      {
        v28 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v70);
        CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v70, v28);
        v29 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v70);
        CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v70, 0x21Fu, v29, 0);
      }
      v71 = v7;
      CFciStorageModuleDefinition::SetInternalStorageType(v4, (unsigned int)dword_18011937C[26 * i]);
      LOWORD(v8) = -(byte_180119380[104 * i] != 0);
      v9 = (*(__int64 (__fastcall **)(struct tagSAFEARRAY *, __int64))(*(_QWORD *)&v5->cDims + 288LL))(v5, v8);
      v71 = v9;
      if ( v9 < 0 )
      {
        v30 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v70);
        CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v70, v30);
        v31 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v70);
        CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v70, 0x225u, v31, 0);
      }
      v71 = v9;
      v10 = (*(__int64 (__fastcall **)(struct tagSAFEARRAY *))(*(_QWORD *)&v5->cDims + 88LL))(v5);
      v71 = v10;
      if ( v10 < 0 )
      {
        v32 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v70);
        CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v70, v32);
        v33 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v70);
        CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v70, 0x228u, v33, 0);
      }
      v71 = v10;
      if ( v2 )
        (*(void (__fastcall **)(struct tagSAFEARRAY *))(*(_QWORD *)&v2->cDims + 16LL))(v2);
    }
  }
  for ( j = 0; (unsigned __int64)j < 3; ++j )
  {
    v52 = 112LL * j;
    if ( *(_DWORD *)(0x18000004CLL + v52 + 1152192) > v54 && !*(_BYTE *)(0x180000050LL + 112LL * j + 1152192) )
    {
      pv = 0;
      v11 = 0;
      v59 = 0;
      v12 = ATL::CComObject<CFciClassifierModuleDefinition>::CreateInstance(&pv);
      try
      {
        v71 = v12;
        if ( v12 < 0 )
        {
          v34 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v70);
          CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v70, v34);
          v35 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v70);
          CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v70, 0x23Eu, v35, 0);
        }
        v71 = v12;
        v13 = (char *)pv;
        v14 = (char *)pv + 8;
        if ( pv != (LPVOID)-8LL )
        {
          (*(void (__fastcall **)(char *))(*(_QWORD *)v14 + 8LL))((char *)pv + 8);
          v11 = v14;
          v59 = v14;
        }
        v15 = (struct CFciModuleDefinitionBase *)(v13 + 16);
        if ( !v13 )
          v15 = 0;
        SetCommonModuleParams(
          (struct InBoxModuleDefinition *)(0x180000000LL + 112LL * j + 1152192),
          v15,
          v56,
          bstrString);
        v51 = 0;
        v53 = 0;
        v16 = 0;
        v61 = 0;
        v60 = &CSrmAuto<tagSAFEARRAY *,CSrmAutoGenericValue_Storage<tagSAFEARRAY *,0,long (*)(tagSAFEARRAY *),&long SafeArrayDestroy(tagSAFEARRAY *),tagSAFEARRAY * & (*)(tagSAFEARRAY * &),&public: static tagSAFEARRAY * & DTyper<tagSAFEARRAY *>::Identity(tagSAFEARRAY * &)>>::`vftable';
        v17 = *(const unsigned __int16 **)((char *)off_180119518 + v52);
        if ( v17 && *v17 )
        {
          pv = 0;
          CSrmAutoPWSZ::CopyFrom((CSrmAutoPWSZ *)&pv, v17);
          v18 = ParseStringToSafearray((OLECHAR *)pv, &v51, &v53);
          v71 = v18;
          if ( v18 < 0 )
          {
            v36 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v70);
            CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v70, v36);
            v37 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v70);
            CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v70, 0x24Fu, v37, 0);
          }
          v71 = v18;
          v16 = v51;
          v61 = v51;
          v19 = (*(__int64 (__fastcall **)(char *, struct tagSAFEARRAY *))(*(_QWORD *)v14 + 256LL))(v14, v51);
          v71 = v19;
          if ( v19 < 0 )
          {
            v38 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v70);
            CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v70, v38);
            v39 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v70);
            CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v70, 0x253u, v39, 0);
          }
          v71 = v19;
          CoTaskMemFree(pv);
        }
        if ( v16 )
          SafeArrayDestroy(v16);
        v60 = &CSrmAutoGenericValue_Storage<tagSAFEARRAY *,0,long (*)(tagSAFEARRAY *),&long SafeArrayDestroy(tagSAFEARRAY *),tagSAFEARRAY * & (*)(tagSAFEARRAY * &),&public: static tagSAFEARRAY * & DTyper<tagSAFEARRAY *>::Identity(tagSAFEARRAY * &)>::`vftable';
        v61 = 0;
        v51 = 0;
        v20 = 0;
        v63 = 0;
        v62 = &CSrmAuto<tagSAFEARRAY *,CSrmAutoGenericValue_Storage<tagSAFEARRAY *,0,long (*)(tagSAFEARRAY *),&long SafeArrayDestroy(tagSAFEARRAY *),tagSAFEARRAY * & (*)(tagSAFEARRAY * &),&public: static tagSAFEARRAY * & DTyper<tagSAFEARRAY *>::Identity(tagSAFEARRAY * &)>>::`vftable';
        v53 = 0;
        v21 = *(const unsigned __int16 **)((char *)&off_180119520 + v52);
        if ( v21 && *v21 )
        {
          pv = 0;
          CSrmAutoPWSZ::CopyFrom((CSrmAutoPWSZ *)&pv, v21);
          v22 = ParseStringToSafearray((OLECHAR *)pv, &v51, &v53);
          v71 = v22;
          if ( v22 < 0 )
          {
            v40 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v70);
            CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v70, v40);
            v41 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v70);
            CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v70, 0x262u, v41, 0);
          }
          v71 = v22;
          v20 = v51;
          v63 = v51;
          v23 = (*(__int64 (__fastcall **)(char *, struct tagSAFEARRAY *))(*(_QWORD *)v14 + 272LL))(v14, v51);
          v71 = v23;
          if ( v23 < 0 )
          {
            v42 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v70);
            CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v70, v42);
            v43 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v70);
            CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v70, 0x266u, v43, 0);
          }
          v71 = v23;
          CoTaskMemFree(pv);
        }
        if ( v20 )
          SafeArrayDestroy(v20);
        v62 = &CSrmAutoGenericValue_Storage<tagSAFEARRAY *,0,long (*)(tagSAFEARRAY *),&long SafeArrayDestroy(tagSAFEARRAY *),tagSAFEARRAY * & (*)(tagSAFEARRAY * &),&public: static tagSAFEARRAY * & DTyper<tagSAFEARRAY *>::Identity(tagSAFEARRAY * &)>::`vftable';
        v63 = 0;
        LOWORD(v21) = -(*((_BYTE *)&qword_180119528 + v52) != 0);
        v24 = (*(__int64 (__fastcall **)(char *, const unsigned __int16 *))(*(_QWORD *)v14 + 288LL))(v14, v21);
        v71 = v24;
        if ( v24 < 0 )
        {
          v44 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v70);
          CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v70, v44);
          v45 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v70);
          CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v70, 0x26Bu, v45, 0);
        }
        v71 = v24;
        v25 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v14 + 88LL))(v14);
        v71 = v25;
        if ( v25 < 0 )
        {
          v46 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v70);
          CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v70, v46);
          v47 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v70);
          CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v70, 0x26Du, v47, 0);
        }
        v71 = v25;
        if ( v11 )
          (*(void (__fastcall **)(char *))(*(_QWORD *)v11 + 16LL))(v11);
      }
      catch ( long v64 )
      {
        CSrmFunctionTracer::HandleHresultException(
          (CSrmFunctionTracer *)&v70,
          v64,
          L"base\\fs\\fsrm\\service\\globalstore\\inboxmodules.cpp",
          L"CINBOXMD",
          L"SaveInBoxModuleDefinitions",
          0x270u,
          v72);
        continue;
      }
      catch ( _com_error *v65 )
      {
        CSrmFunctionTracer::HandleComException(
          (CSrmFunctionTracer *)&v70,
          v65,
          L"base\\fs\\fsrm\\service\\globalstore\\inboxmodules.cpp",
          L"CINBOXMD",
          L"SaveInBoxModuleDefinitions",
          0x270u,
          v72);
      }
      catch ( std::bad_alloc )
      {
        CSrmFunctionTracer::HandleStdBadAllocException(
          (CSrmFunctionTracer *)&v70,
          L"base\\fs\\fsrm\\service\\globalstore\\inboxmodules.cpp",
          L"CINBOXMD",
          L"SaveInBoxModuleDefinitions",
          0x270u,
          v72);
        continue;
      }
      catch ( const exception *v66 )
      {
        CSrmFunctionTracer::HandleStdGenericException(
          (CSrmFunctionTracer *)&v70,
          v66,
          L"base\\fs\\fsrm\\service\\globalstore\\inboxmodules.cpp",
          L"CINBOXMD",
          L"SaveInBoxModuleDefinitions",
          0x270u,
          v72);
      }
    }
  }
  SysFreeString(bstrString);
  SysFreeString(v56);
  v70 = &CSrmFunctionTracer::`vftable';
  CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)&v70);
}

```

## disassembly

```asm
0x18001c1f0  mov     r11, rsp
0x18001c1f3  push    rbx
0x18001c1f4  push    rsi
0x18001c1f5  push    rdi
0x18001c1f6  push    r12
0x18001c1f8  push    r13
0x18001c1fa  push    r14
0x18001c1fc  push    r15
0x18001c1fe  sub     rsp, 270h
0x18001c205  mov     rax, cs:__security_cookie
0x18001c20c  xor     rax, rsp
0x18001c20f  mov     [rsp+2A8h+var_48], rax
0x18001c217  lea     rax, aBaseFsFsrmServ_2; "base\\fs\\fsrm\\service\\globalstore\\i"...
0x18001c21e  mov     [r11-1D8h], rax
0x18001c225  lea     rax, aSaveinboxmodul; "SaveInBoxModuleDefinitions"
0x18001c22c  mov     [r11-1D0h], rax
0x18001c233  lea     rax, aCinboxmd; "CINBOXMD"
0x18001c23a  mov     [r11-1C8h], rax
0x18001c241  mov     qword ptr [r11-1C0h], 1F3h
0x18001c24c  xor     edi, edi
0x18001c24e  mov     [rsp+2A8h+var_1B8], 0FFh
0x18001c259  mov     [rsp+2A8h+var_150], 1000000h
0x18001c264  xor     edx, edx; Val
0x18001c266  lea     r8d, [rdi+60h]; Size
0x18001c26a  lea     rcx, [r11-1B0h]; void *
0x18001c271  call    memset_0
0x18001c276  xor     r8d, r8d
0x18001c279  lea     rdx, [rsp+2A8h+var_1D8]
0x18001c281  lea     rcx, [rsp+2A8h+var_148]
0x18001c289  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x18001c28e  nop
0x18001c28f  mov     [rsp+2A8h+var_258], 740h
0x18001c298  mov     [rsp+2A8h+var_250], rdi
0x18001c29d  lea     r9, [rsp+2A8h+var_258]
0x18001c2a2  lea     r8, [rsp+2A8h+var_250]
0x18001c2a7  xor     edx, edx
0x18001c2a9  lea     rcx, [rsp+2A8h+var_148]
0x18001c2b1  call    ?AddContext@CSrmFunctionTracerBase@@QEAAXW4_SrmContextType@@AEBUResIdOrStringParam@@1@Z; CSrmFunctionTracerBase::AddContext(_SrmContextType,ResIdOrStringParam const &,ResIdOrStringParam const &)
0x18001c2b6  mov     edx, 0FE6h; uID
0x18001c2bb  lea     rcx, [rsp+2A8h+Block]; void *
0x18001c2c3  call    ?LoadStringW@CSrmResource@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@I@Z; CSrmResource::LoadStringW(uint)
0x18001c2c8  nop
0x18001c2c9  cmp     qword ptr [rax+18h], 8
0x18001c2ce  jb      short loc_18001C2D3
0x18001c2d0  mov     rax, [rax]
0x18001c2d3  test    rax, rax
0x18001c2d6  jnz     loc_18001C3DF
0x18001c2dc  mov     [rsp+2A8h+var_238], rdi
0x18001c2e1  cmp     [rsp+2A8h+var_80], 8
0x18001c2ea  jb      short loc_18001C2F9
0x18001c2ec  mov     rcx, [rsp+2A8h+Block]; Block
0x18001c2f4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001c2f9  mov     ebx, 7
0x18001c2fe  mov     [rsp+2A8h+var_80], rbx
0x18001c306  mov     [rsp+2A8h+var_88], rdi
0x18001c30e  mov     word ptr [rsp+2A8h+Block], di
0x18001c316  mov     edx, 0FE7h; uID
0x18001c31b  lea     rcx, [rsp+2A8h+var_70]; void *
0x18001c323  call    ?LoadStringW@CSrmResource@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@I@Z; CSrmResource::LoadStringW(uint)
0x18001c328  nop
0x18001c329  cmp     qword ptr [rax+18h], 8
0x18001c32e  jb      short loc_18001C333
0x18001c330  mov     rax, [rax]
0x18001c333  test    rax, rax
0x18001c336  jnz     loc_18001C3FB
0x18001c33c  mov     [rsp+2A8h+bstrString], rdi
0x18001c341  cmp     [rsp+2A8h+var_58], 8
0x18001c34a  jb      short loc_18001C359
0x18001c34c  mov     rcx, [rsp+2A8h+var_70]; Block
0x18001c354  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001c359  mov     [rsp+2A8h+var_58], rbx
0x18001c361  mov     [rsp+2A8h+var_60], rdi
0x18001c369  mov     word ptr [rsp+2A8h+var_70], di
0x18001c371  mov     [rsp+2A8h+var_244], edi
0x18001c375  mov     [rsp+2A8h+var_268], edi
0x18001c379  lea     rsi, cs:180000000h
0x18001c380  movsxd  rax, [rsp+2A8h+var_268]
0x18001c385  cmp     rax, 4
0x18001c389  jnb     loc_18001C528
0x18001c38f  imul    r13, rax, 68h ; 'h'
0x18001c393  lea     r12, [r13+119320h]
0x18001c39a  add     r12, rsi
0x18001c39d  mov     eax, [rsp+2A8h+var_244]
0x18001c3a1  cmp     [r12+4Ch], eax
0x18001c3a6  jle     loc_18001C51B
0x18001c3ac  cmp     [r12+50h], dil
0x18001c3b1  jnz     loc_18001C51B
0x18001c3b7  mov     [rsp+2A8h+var_250], rdi
0x18001c3bc  mov     rbx, rdi
0x18001c3bf  mov     [rsp+2A8h+var_258], rbx
0x18001c3c4  lea     rcx, [rsp+2A8h+var_250]
0x18001c3c9  call    ?CreateInstance@?$CComObject@VCFciStorageModuleDefinition@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CFciStorageModuleDefinition>::CreateInstance(ATL::CComObject<CFciStorageModuleDefinition> * *)
0x18001c3ce  mov     [rsp+2A8h+var_140], eax
0x18001c3d5  test    eax, eax
0x18001c3d7  js      loc_18001C877
0x18001c3dd  jmp     short loc_18001C417
0x18001c3df  mov     rcx, rax; psz
0x18001c3e2  call    cs:__imp_SysAllocString
0x18001c3e8  mov     [rsp+2A8h+var_238], rax
0x18001c3ed  test    rax, rax
0x18001c3f0  jz      loc_18001C8B9
0x18001c3f6  jmp     loc_18001C2E1
0x18001c3fb  mov     rcx, rax; psz
0x18001c3fe  call    cs:__imp_SysAllocString
0x18001c404  mov     [rsp+2A8h+bstrString], rax
0x18001c409  test    rax, rax
0x18001c40c  jz      loc_18001C8D3
0x18001c412  jmp     loc_18001C341
0x18001c417  mov     [rsp+2A8h+var_140], eax
0x18001c41e  mov     r15, [rsp+2A8h+var_250]
0x18001c423  lea     r14, [r15+10h]
0x18001c427  test    r14, r14
0x18001c42a  jz      short loc_18001C443
0x18001c42c  mov     rax, [r14]
0x18001c42f  mov     rcx, r14
0x18001c432  mov     rax, [rax+8]
0x18001c436  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c43b  mov     rbx, r14
0x18001c43e  mov     [rsp+2A8h+var_258], rbx
0x18001c443  test    r15, r15
0x18001c446  lea     rdx, [r15+18h]
0x18001c44a  jnz     short loc_18001C44F
0x18001c44c  mov     rdx, rdi; struct CFciModuleDefinitionBase *
0x18001c44f  mov     r9, [rsp+2A8h+bstrString]; unsigned __int16 *
0x18001c454  mov     r8, [rsp+2A8h+var_238]; unsigned __int16 *
0x18001c459  mov     rcx, r12; struct InBoxModuleDefinition *
0x18001c45c  call    ?SetCommonModuleParams@@YAXAEAUInBoxModuleDefinition@@PEAVCFciModuleDefinitionBase@@PEAG2@Z; SetCommonModuleParams(InBoxModuleDefinition &,CFciModuleDefinitionBase *,ushort *,ushort *)
0x18001c461  mov     rax, [r14]
0x18001c464  mov     edx, rva dword_180119378[rsi+r13]
0x18001c46c  mov     rcx, r14
0x18001c46f  mov     rax, [rax+100h]
0x18001c476  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c47b  mov     [rsp+2A8h+var_140], eax
0x18001c482  test    eax, eax
0x18001c484  js      loc_18001C8ED
0x18001c48a  mov     [rsp+2A8h+var_140], eax
0x18001c491  mov     edx, rva dword_18011937C[rsi+r13]
0x18001c499  mov     rcx, r15
0x18001c49c  call    ?SetInternalStorageType@CFciStorageModuleDefinition@@QEAAXW4_FsrmStorageModuleTypeInternal@@@Z; CFciStorageModuleDefinition::SetInternalStorageType(_FsrmStorageModuleTypeInternal)
0x18001c4a1  mov     r8, [r14]
0x18001c4a4  mov     al, rva byte_180119380[rsi+r13]
0x18001c4ac  neg     al
0x18001c4ae  sbb     dx, dx
0x18001c4b1  mov     rcx, r14
0x18001c4b4  mov     rax, [r8+120h]
0x18001c4bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c4c0  mov     [rsp+2A8h+var_140], eax
0x18001c4c7  test    eax, eax
0x18001c4c9  js      loc_18001C92E
0x18001c4cf  mov     [rsp+2A8h+var_140], eax
0x18001c4d6  mov     rax, [r14]
0x18001c4d9  mov     rcx, r14
0x18001c4dc  mov     rax, [rax+58h]
0x18001c4e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c4e5  mov     [rsp+2A8h+var_140], eax
0x18001c4ec  test    eax, eax
0x18001c4ee  js      loc_18001C96F
0x18001c4f4  mov     [rsp+2A8h+var_140], eax
0x18001c4fb  test    rbx, rbx
0x18001c4fe  jz      short loc_18001C510
0x18001c500  mov     rax, [rbx]
0x18001c503  mov     rcx, rbx
0x18001c506  mov     rax, [rax+10h]
0x18001c50a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c50f  nop
0x18001c510  jmp     short loc_18001C51B
0x18001c512  lea     rsi, cs:180000000h
0x18001c519  xor     edi, edi
0x18001c51b  inc     [rsp+2A8h+var_268]
0x18001c51f  jmp     loc_18001C380
0x18001c524  jmp     short loc_18001C512
0x18001c526  jmp     short loc_18001C512
0x18001c528  mov     [rsp+2A8h+var_268], edi
0x18001c52c  lea     r12, ??_7?$CSrmAuto@PEAUtagSAFEARRAY@@V?$CSrmAutoGenericValue_Storage@PEAUtagSAFEARRAY@@$0A@P6AJPEAU1@@Z$1?SafeArrayDestroy@@YAJ0@ZP6AAEAPEAU1@AEAPEAU1@@Z$1?Identity@?$DTyper@PEAUtagSAFEARRAY@@@@SAAEAPEAU1@1@Z@@@@6B@; const CSrmAuto<tagSAFEARRAY *,CSrmAutoGenericValue_Storage<tagSAFEARRAY *,0,long (*)(tagSAFEARRAY *),&SafeArrayDestroy(tagSAFEARRAY *),tagSAFEARRAY * & (*)(tagSAFEARRAY * &),&DTyper<tagSAFEARRAY *>::Identity(tagSAFEARRAY * &)>>::`vftable'
0x18001c533  movsxd  rax, [rsp+2A8h+var_268]
0x18001c538  cmp     rax, 3
0x18001c53c  jnb     loc_18001C820
0x18001c542  imul    rax, 70h ; 'p'
0x18001c546  mov     [rsp+2A8h+var_250], rax
0x18001c54b  lea     r13, [rax+1194C0h]
0x18001c552  add     r13, rsi
0x18001c555  mov     eax, [rsp+2A8h+var_244]
0x18001c559  cmp     [r13+4Ch], eax
0x18001c55d  jle     loc_18001C813
0x18001c563  cmp     [r13+50h], dil
0x18001c567  jnz     loc_18001C813
0x18001c56d  mov     [rsp+2A8h+pv], rdi
0x18001c572  mov     rbx, rdi
0x18001c575  mov     [rsp+2A8h+var_228], rbx
0x18001c57d  lea     rcx, [rsp+2A8h+pv]
0x18001c582  call    ?CreateInstance@?$CComObject@VCFciClassifierModuleDefinition@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CFciClassifierModuleDefinition>::CreateInstance(ATL::CComObject<CFciClassifierModuleDefinition> * *)
0x18001c587  mov     [rsp+2A8h+var_140], eax
0x18001c58e  test    eax, eax
0x18001c590  js      loc_18001C9B1
0x18001c596  mov     [rsp+2A8h+var_140], eax
0x18001c59d  mov     r15, [rsp+2A8h+pv]
0x18001c5a2  lea     r14, [r15+8]
0x18001c5a6  test    r14, r14
0x18001c5a9  jz      short loc_18001C5C5
0x18001c5ab  mov     rax, [r14]
0x18001c5ae  mov     rcx, r14
0x18001c5b1  mov     rax, [rax+8]
0x18001c5b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c5ba  mov     rbx, r14
0x18001c5bd  mov     [rsp+2A8h+var_228], rbx
0x18001c5c5  test    r15, r15
0x18001c5c8  lea     rdx, [r15+10h]
0x18001c5cc  jnz     short loc_18001C5D1
0x18001c5ce  mov     rdx, rdi; struct CFciModuleDefinitionBase *
0x18001c5d1  mov     r9, [rsp+2A8h+bstrString]; unsigned __int16 *
0x18001c5d6  mov     r8, [rsp+2A8h+var_238]; unsigned __int16 *
0x18001c5db  mov     rcx, r13; struct InBoxModuleDefinition *
0x18001c5de  call    ?SetCommonModuleParams@@YAXAEAUInBoxModuleDefinition@@PEAVCFciModuleDefinitionBase@@PEAG2@Z; SetCommonModuleParams(InBoxModuleDefinition &,CFciModuleDefinitionBase *,ushort *,ushort *)
0x18001c5e3  mov     [rsp+2A8h+var_258], rdi
0x18001c5e8  mov     [rsp+2A8h+var_248], edi
0x18001c5ec  mov     r15, rdi
0x18001c5ef  mov     [rsp+2A8h+var_218], rdi
0x18001c5f7  mov     [rsp+2A8h+var_220], r12
0x18001c5ff  mov     rdx, [rsp+2A8h+var_250]
0x18001c604  mov     rdx, [rdx+rsi+119518h]; unsigned __int16 *
0x18001c60c  test    rdx, rdx
0x18001c60f  jz      loc_18001C697
0x18001c615  cmp     [rdx], di
0x18001c618  jz      short loc_18001C697
0x18001c61a  mov     [rsp+2A8h+pv], rdi
0x18001c61f  lea     rcx, [rsp+2A8h+pv]; this
0x18001c624  call    ?CopyFrom@CSrmAutoPWSZ@@QEAAXPEBG@Z; CSrmAutoPWSZ::CopyFrom(ushort const *)
0x18001c629  lea     r8, [rsp+2A8h+var_248]; int *
0x18001c62e  lea     rdx, [rsp+2A8h+var_258]; struct tagSAFEARRAY **
0x18001c633  mov     rcx, [rsp+2A8h+pv]; psz
0x18001c638  call    ?ParseStringToSafearray@@YAJPEAGPEAPEAUtagSAFEARRAY@@PEAJ@Z; ParseStringToSafearray(ushort *,tagSAFEARRAY * *,long *)
0x18001c63d  mov     [rsp+2A8h+var_140], eax
0x18001c644  test    eax, eax
0x18001c646  js      loc_18001C9F3
0x18001c64c  mov     [rsp+2A8h+var_140], eax
0x18001c653  mov     r15, [rsp+2A8h+var_258]
0x18001c658  mov     [rsp+2A8h+var_218], r15
0x18001c660  mov     rax, [r14]
0x18001c663  mov     rdx, r15
0x18001c666  mov     rcx, r14
0x18001c669  mov     rax, [rax+100h]
0x18001c670  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c675  mov     [rsp+2A8h+var_140], eax
0x18001c67c  test    eax, eax
0x18001c67e  js      loc_18001CA34
0x18001c684  mov     [rsp+2A8h+var_140], eax
0x18001c68b  mov     rcx, [rsp+2A8h+pv]; pv
0x18001c690  call    cs:__imp_CoTaskMemFree
0x18001c696  nop
0x18001c697  test    r15, r15
0x18001c69a  jz      short loc_18001C6A5
0x18001c69c  mov     rcx, r15; psa
0x18001c69f  call    cs:__imp_SafeArrayDestroy
0x18001c6a5  lea     r13, ??_7?$CSrmAutoGenericValue_Storage@PEAUtagSAFEARRAY@@$0A@P6AJPEAU1@@Z$1?SafeArrayDestroy@@YAJ0@ZP6AAEAPEAU1@AEAPEAU1@@Z$1?Identity@?$DTyper@PEAUtagSAFEARRAY@@@@SAAEAPEAU1@1@Z@@6B@; const CSrmAutoGenericValue_Storage<tagSAFEARRAY *,0,long (*)(tagSAFEARRAY *),&SafeArrayDestroy(tagSAFEARRAY *),tagSAFEARRAY * & (*)(tagSAFEARRAY * &),&DTyper<tagSAFEARRAY *>::Identity(tagSAFEARRAY * &)>::`vftable'
0x18001c6ac  mov     [rsp+2A8h+var_220], r13
0x18001c6b4  mov     [rsp+2A8h+var_218], rdi
0x18001c6bc  mov     [rsp+2A8h+var_258], rdi
0x18001c6c1  mov     r15, rdi
0x18001c6c4  mov     [rsp+2A8h+var_208], rdi
0x18001c6cc  mov     [rsp+2A8h+var_210], r12
0x18001c6d4  mov     [rsp+2A8h+var_248], edi
0x18001c6d8  mov     rax, [rsp+2A8h+var_250]
0x18001c6dd  mov     rdx, [rax+rsi+119520h]; unsigned __int16 *
0x18001c6e5  test    rdx, rdx
0x18001c6e8  jz      loc_18001C770
0x18001c6ee  cmp     [rdx], di
0x18001c6f1  jz      short loc_18001C770
0x18001c6f3  mov     [rsp+2A8h+pv], rdi
0x18001c6f8  lea     rcx, [rsp+2A8h+pv]; this
0x18001c6fd  call    ?CopyFrom@CSrmAutoPWSZ@@QEAAXPEBG@Z; CSrmAutoPWSZ::CopyFrom(ushort const *)
0x18001c702  lea     r8, [rsp+2A8h+var_248]; int *
0x18001c707  lea     rdx, [rsp+2A8h+var_258]; struct tagSAFEARRAY **
0x18001c70c  mov     rcx, [rsp+2A8h+pv]; psz
0x18001c711  call    ?ParseStringToSafearray@@YAJPEAGPEAPEAUtagSAFEARRAY@@PEAJ@Z; ParseStringToSafearray(ushort *,tagSAFEARRAY * *,long *)
0x18001c716  mov     [rsp+2A8h+var_140], eax
0x18001c71d  test    eax, eax
0x18001c71f  js      loc_18001CA76
0x18001c725  mov     [rsp+2A8h+var_140], eax
0x18001c72c  mov     r15, [rsp+2A8h+var_258]
0x18001c731  mov     [rsp+2A8h+var_208], r15
0x18001c739  mov     rax, [r14]
0x18001c73c  mov     rdx, r15
0x18001c73f  mov     rcx, r14
0x18001c742  mov     rax, [rax+110h]
0x18001c749  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c74e  mov     [rsp+2A8h+var_140], eax
0x18001c755  test    eax, eax
0x18001c757  js      loc_18001CAB7
0x18001c75d  mov     [rsp+2A8h+var_140], eax
0x18001c764  mov     rcx, [rsp+2A8h+pv]; pv
0x18001c769  call    cs:__imp_CoTaskMemFree
0x18001c76f  nop
0x18001c770  test    r15, r15
0x18001c773  jz      short loc_18001C77E
0x18001c775  mov     rcx, r15; psa
0x18001c778  call    cs:__imp_SafeArrayDestroy
0x18001c77e  mov     [rsp+2A8h+var_210], r13
0x18001c786  mov     [rsp+2A8h+var_208], rdi
0x18001c78e  mov     r8, [r14]
0x18001c791  mov     rax, [rsp+2A8h+var_250]
  ... truncated ...
```
