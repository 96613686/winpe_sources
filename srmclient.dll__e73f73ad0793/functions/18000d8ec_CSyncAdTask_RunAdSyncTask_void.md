# CSyncAdTask::RunAdSyncTask(void)

- ea: `0x18000d8ec`
- end: `0x18000e280`
- name: `?RunAdSyncTask@CSyncAdTask@@SAXXZ`
- size: `2452`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18006ae28`

## callees

- `0x1800020ba`
- `0x180006a1c`
- `0x1800095f4`
- `0x18000d8ec`
- `0x1800176f4`
- `0x18006febc`
- `0x1800700b8`
- `0x180073a80`
- `0x180075510`
- `0x180075eb8`
- `0x18007691c`
- `0x1800b078a`
- `0x1800b07d0`
- `0x1800d5010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x18000db03`
- `ole32!CoCreateInstance` at `0x18000db03`
- `OLEAUT32!__imp_SysAllocString` at `0x18000d9e8`
- `OLEAUT32!__imp_SysAllocString` at `0x18000da05`
- `OLEAUT32!__imp_SysAllocString` at `0x18000dbe4`
- `OLEAUT32!__imp_SysAllocString` at `0x18000d9e8`
- `OLEAUT32!__imp_SysAllocString` at `0x18000da05`
- `OLEAUT32!__imp_SysAllocString` at `0x18000dbe4`
- `OLEAUT32!__imp_SysFreeString` at `0x18000da76`
- `OLEAUT32!__imp_SysFreeString` at `0x18000da80`
- `OLEAUT32!__imp_SysFreeString` at `0x18000dc17`
- `OLEAUT32!__imp_SysFreeString` at `0x18000de1f`
- `OLEAUT32!__imp_SysFreeString` at `0x18000de29`
- `OLEAUT32!__imp_SysFreeString` at `0x18000da76`
- `OLEAUT32!__imp_SysFreeString` at `0x18000da80`
- `OLEAUT32!__imp_SysFreeString` at `0x18000dc17`
- `OLEAUT32!__imp_SysFreeString` at `0x18000de1f`
- `OLEAUT32!__imp_SysFreeString` at `0x18000de29`
- `OLEAUT32!__imp_VariantInit` at `0x18000d9b9`
- `OLEAUT32!__imp_VariantInit` at `0x18000d9c4`
- `OLEAUT32!__imp_VariantInit` at `0x18000d9cf`
- `OLEAUT32!__imp_VariantInit` at `0x18000d9da`
- `OLEAUT32!__imp_VariantInit` at `0x18000d9b9`
- `OLEAUT32!__imp_VariantInit` at `0x18000d9c4`
- `OLEAUT32!__imp_VariantInit` at `0x18000d9cf`
- `OLEAUT32!__imp_VariantInit` at `0x18000d9da`
- `OLEAUT32!__imp_VariantClear` at `0x18000da6c`
- `OLEAUT32!__imp_VariantClear` at `0x18000da8b`
- `OLEAUT32!__imp_VariantClear` at `0x18000da96`
- `OLEAUT32!__imp_VariantClear` at `0x18000daa1`
- `OLEAUT32!__imp_VariantClear` at `0x18000daac`
- `OLEAUT32!__imp_VariantClear` at `0x18000de15`
- `OLEAUT32!__imp_VariantClear` at `0x18000de34`
- `OLEAUT32!__imp_VariantClear` at `0x18000de3f`
- `OLEAUT32!__imp_VariantClear` at `0x18000de4a`
- `OLEAUT32!__imp_VariantClear` at `0x18000de55`
- `OLEAUT32!__imp_VariantClear` at `0x18000da6c`
- `OLEAUT32!__imp_VariantClear` at `0x18000da8b`
- `OLEAUT32!__imp_VariantClear` at `0x18000da96`
- `OLEAUT32!__imp_VariantClear` at `0x18000daa1`
- `OLEAUT32!__imp_VariantClear` at `0x18000daac`
- `OLEAUT32!__imp_VariantClear` at `0x18000de15`
- `OLEAUT32!__imp_VariantClear` at `0x18000de34`
- `OLEAUT32!__imp_VariantClear` at `0x18000de3f`
- `OLEAUT32!__imp_VariantClear` at `0x18000de4a`
- `OLEAUT32!__imp_VariantClear` at `0x18000de55`
- `KERNEL32!Sleep` at `0x18000dd12`
- `KERNEL32!Sleep` at `0x18000dd12`

## string_xrefs

- `0x18000d922`: `base\fs\fsrm\service\globalstore\taskhandler.cpp`
- `0x18000d930`: `CSyncAdTask::RunAdSyncTask`
- `0x18000dd75`: `AdLeaveTaskEnabled`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void CSyncAdTask::RunAdSyncTask(void)
{
  char v0; // r14
  OLECHAR *v1; // rsi
  OLECHAR *v2; // rdi
  HRESULT v3; // eax
  int v4; // eax
  int v5; // eax
  __int64 *v6; // r15
  __int64 v7; // r13
  BSTR v8; // rax
  OLECHAR *v9; // rbx
  int v10; // eax
  int v11; // eax
  int v12; // eax
  int v13; // eax
  int v14; // ebx
  int v15; // eax
  bool v16; // r9
  int v17; // eax
  int v18; // eax
  char v19; // al
  int Hr; // eax
  char v21; // al
  int v22; // eax
  char v23; // al
  int v24; // eax
  char v25; // al
  int v26; // eax
  char v27; // al
  int v28; // eax
  char v29; // al
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
  unsigned int pExceptionObject; // [rsp+48h] [rbp-C0h] BYREF
  __int16 pExceptionObject_4; // [rsp+4Ch] [rbp-BCh] BYREF
  __int64 v46; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v47; // [rsp+58h] [rbp-B0h] BYREF
  LPVOID ppv; // [rsp+60h] [rbp-A8h] BYREF
  __int64 *v49; // [rsp+68h] [rbp-A0h] BYREF
  _QWORD v50[3]; // [rsp+70h] [rbp-98h] BYREF
  VARIANTARG v51; // [rsp+88h] [rbp-80h] BYREF
  VARIANTARG v52; // [rsp+A8h] [rbp-60h] BYREF
  VARIANTARG v53; // [rsp+C8h] [rbp-40h] BYREF
  VARIANTARG v54; // [rsp+E0h] [rbp-28h] BYREF
  VARIANTARG v55; // [rsp+F8h] [rbp-10h] BYREF
  VARIANTARG pvarg; // [rsp+110h] [rbp+8h] BYREF
  OLECHAR *v57; // [rsp+128h] [rbp+20h]
  OLECHAR *v58; // [rsp+130h] [rbp+28h]
  BSTR v59; // [rsp+138h] [rbp+30h]
  VARIANTARG v60; // [rsp+148h] [rbp+40h] BYREF
  VARIANTARG v61; // [rsp+168h] [rbp+60h] BYREF
  VARIANTARG v62; // [rsp+188h] [rbp+80h] BYREF
  _QWORD v63[3]; // [rsp+1A8h] [rbp+A0h] BYREF
  int v64; // [rsp+1C0h] [rbp+B8h]
  int v65; // [rsp+1C4h] [rbp+BCh]
  int v66; // [rsp+1C8h] [rbp+C0h]
  _BYTE v67[96]; // [rsp+1D0h] [rbp+C8h] BYREF
  int v68; // [rsp+230h] [rbp+128h]
  void **v69; // [rsp+238h] [rbp+130h] BYREF
  int v70; // [rsp+240h] [rbp+138h]

  v63[0] = L"base\\fs\\fsrm\\service\\globalstore\\taskhandler.cpp";
  v63[1] = L"CSyncAdTask::RunAdSyncTask";
  v63[2] = L"TSKNDLRC";
  v64 = 270;
  v65 = 30;
  v66 = 255;
  v68 = 0x1000000;
  v0 = 1;
  memset_0(v67, 0, sizeof(v67));
  CSrmFunctionTracer::CSrmFunctionTracer(&v69, v63, 0);
  ppv = 0;
  v49 = 0;
  v46 = 0;
  VariantInit(&pvarg);
  VariantInit(&v55);
  VariantInit(&v54);
  VariantInit(&v53);
  v1 = SysAllocString(L"\\");
  v57 = v1;
  if ( !v1 )
  {
    pExceptionObject = -2147024882;
    throw (long *)&pExceptionObject;
  }
  v2 = SysAllocString(L"\\");
  v58 = v2;
  if ( !v2 )
  {
    pExceptionObject = -2147024882;
    throw (long *)&pExceptionObject;
  }
  pExceptionObject_4 = 0;
  v51.vt = 3;
  v51.lVal = 0;
  v47 = 0;
  v50[2] = 0;
  v50[1] = 0;
  v50[0] = 131353;
  pExceptionObject = 0;
  if ( CAdReader::ShouldSkipSync() )
  {
    CSrmRegistryKey::~CSrmRegistryKey((CSrmRegistryKey *)v50);
    VariantClear(&v51);
    SysFreeString(v2);
    SysFreeString(v1);
    VariantClear(&v53);
    VariantClear(&v54);
    VariantClear(&v55);
    VariantClear(&pvarg);
  }
  else
  {
    v3 = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &IID_ITaskService, &ppv);
    v70 = v3;
    if ( v3 < 0 )
    {
      Hr = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v69);
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v69, Hr);
      v21 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v69);
      CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v69, 0x12Au, v21, 0);
    }
    v70 = v3;
    v60 = v53;
    v61 = v54;
    v62 = v55;
    v52 = pvarg;
    v4 = (*(__int64 (__fastcall **)(LPVOID, VARIANTARG *, VARIANTARG *, VARIANTARG *, VARIANTARG *))(*(_QWORD *)ppv + 80LL))(
           ppv,
           &v52,
           &v62,
           &v61,
           &v60);
    v70 = v4;
    if ( v4 < 0 )
    {
      v22 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v69);
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v69, v22);
      v23 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v69);
      CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v69, 0x12Cu, v23, 0);
    }
    v70 = v4;
    v5 = (*(__int64 (__fastcall **)(LPVOID, OLECHAR *, __int64 **))(*(_QWORD *)ppv + 56LL))(ppv, v1, &v49);
    v70 = v5;
    if ( v5 < 0 )
    {
      v24 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v69);
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v69, v24);
      v25 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v69);
      CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v69, 0x12Eu, v25, 0);
    }
    v70 = v5;
    v6 = v49;
    v7 = *v49;
    v8 = SysAllocString(L"\\Microsoft\\Windows\\File Classification Infrastructure\\Property Definition Sync");
    v9 = v8;
    v59 = v8;
    if ( !v8 )
    {
      pExceptionObject = -2147024882;
      throw (long *)&pExceptionObject;
    }
    v70 = (*(__int64 (__fastcall **)(__int64 *, BSTR, __int64 *))(v7 + 104))(v6, v8, &v46);
    SysFreeString(v9);
    if ( v70 < 0 )
    {
      v26 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v69);
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v69, v26);
      v27 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v69);
      CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v69, 0x130u, v27, 0);
    }
    v10 = (*(__int64 (__fastcall **)(__int64, __int16 *))(*(_QWORD *)v46 + 80LL))(v46, &pExceptionObject_4);
    v70 = v10;
    if ( v10 < 0 )
    {
      v28 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v69);
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v69, v28);
      v29 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v69);
      CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v69, 0x132u, v29, 0);
    }
    v70 = v10;
    v11 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v46 + 88LL))(v46, 0xFFFFFFFFLL);
    v70 = v11;
    if ( v11 < 0 )
    {
      v30 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v69);
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v69, v30);
      v31 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v69);
      CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v69, 0x134u, v31, 0);
    }
    v70 = v11;
    v52 = v51;
    v12 = (*(__int64 (__fastcall **)(__int64, VARIANTARG *, __int64))(*(_QWORD *)v46 + 104LL))(v46, &v52, 2);
    v70 = v12;
    if ( v12 < 0 )
    {
      v32 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v69);
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v69, v32);
      v33 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v69);
      CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v69, 0x136u, v33, 0);
    }
    v70 = v12;
    v13 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v46 + 72LL))(v46, &v47);
    v70 = v13;
    if ( v13 < 0 )
    {
      v34 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v69);
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v69, v34);
      v35 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v69);
      CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v69, 0x138u, v35, 0);
    }
    v14 = 120;
    v70 = v13;
    if ( (_DWORD)v47 != 3 )
    {
      do
      {
        if ( v14 <= 0 )
          goto LABEL_48;
        Sleep(0x1F4u);
        v15 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v46 + 72LL))(v46, &v47);
        v70 = v15;
        if ( v15 < 0 )
        {
          v38 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v69);
          CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v69, v38);
          v39 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v69);
          CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v69, 0x141u, v39, 0);
        }
        --v14;
        v70 = v15;
      }
      while ( (_DWORD)v47 != 3 );
      if ( v14 <= 0 )
      {
LABEL_48:
        (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v46 + 184LL))(v46, 0);
        v70 = -2147200144;
        v36 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v69);
        CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v69, v36);
        v37 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v69);
        CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v69, 0x14Au, v37, 0);
      }
    }
    if ( CSrmRegistryKey::Open(
           (CSrmRegistryKey *)v50,
           HKEY_LOCAL_MACHINE,
           L"Software\\Microsoft\\FileClassificationInfrastructure")
      && CSrmRegistryKey::GetValue((CSrmRegistryKey *)v50, L"AdLeaveTaskEnabled", &pExceptionObject, v16)
      && pExceptionObject )
    {
      v0 = 0;
    }
    if ( !pExceptionObject_4 && v0 )
    {
      v17 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v46 + 88LL))(v46, 0);
      v70 = v17;
      if ( v17 < 0 )
      {
        v40 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v69);
        CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v69, v40);
        v41 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v69);
        CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v69, 0x15Eu, v41, 0);
      }
      v70 = v17;
    }
    v70 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v46 + 128LL))(v46, (char *)&v47 + 4);
    if ( v70 < 0 )
    {
      v42 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v69);
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v69, v42);
      v43 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v69);
      CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v69, 0x162u, v43, 0);
    }
    v70 = HIDWORD(v47);
    if ( v47 < 0 )
    {
      v18 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v69);
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v69, v18);
      v19 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v69);
      CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v69, 0x164u, v19, 0);
    }
    v70 = HIDWORD(v47);
    CSrmRegistryKey::~CSrmRegistryKey((CSrmRegistryKey *)v50);
    VariantClear(&v51);
    SysFreeString(v2);
    SysFreeString(v1);
    VariantClear(&v53);
    VariantClear(&v54);
    VariantClear(&v55);
    VariantClear(&pvarg);
    if ( v46 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
    if ( v49 )
      (*(void (__fastcall **)(__int64 *))(*v49 + 16))(v49);
  }
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  v69 = &CSrmFunctionTracer::`vftable';
  CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)&v69);
}

```

## disassembly

```asm
0x18000d8ec  mov     rax, rsp
0x18000d8ef  push    rbp
0x18000d8f0  push    rbx
0x18000d8f1  push    rsi
0x18000d8f2  push    rdi
0x18000d8f3  push    r12
0x18000d8f5  push    r13
0x18000d8f7  push    r14
0x18000d8f9  push    r15
0x18000d8fb  lea     rbp, [rax-258h]
0x18000d902  sub     rsp, 318h
0x18000d909  movaps  xmmword ptr [rax-58h], xmm6
0x18000d90d  movaps  xmmword ptr [rax-68h], xmm7
0x18000d911  mov     rax, cs:__security_cookie
0x18000d918  xor     rax, rsp
0x18000d91b  mov     [rbp+250h+var_70], rax
0x18000d922  lea     rax, aBaseFsFsrmServ_39; "base\\fs\\fsrm\\service\\globalstore\\t"...
0x18000d929  mov     [rbp+250h+var_1B0], rax
0x18000d930  lea     rax, aCsyncadtaskRun; "CSyncAdTask::RunAdSyncTask"
0x18000d937  mov     [rbp+250h+var_1A8], rax
0x18000d93e  lea     rax, aTskndlrc; "TSKNDLRC"
0x18000d945  mov     [rbp+250h+var_1A0], rax
0x18000d94c  mov     [rbp+250h+var_198], 10Eh
0x18000d956  mov     [rbp+250h+var_194], 1Eh
0x18000d960  mov     [rbp+250h+var_190], 0FFh
0x18000d96a  xor     r12d, r12d
0x18000d96d  mov     [rbp+250h+var_128], 1000000h
0x18000d977  xor     edx, edx; Val
0x18000d979  lea     r14d, [r12+1]
0x18000d97e  lea     r8d, [r12+60h]; Size
0x18000d983  lea     rcx, [rbp+250h+var_188]; void *
0x18000d98a  call    memset_0
0x18000d98f  xor     r8d, r8d
0x18000d992  lea     rdx, [rbp+250h+var_1B0]
0x18000d999  lea     rcx, [rbp+250h+var_120]
0x18000d9a0  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x18000d9a5  nop
0x18000d9a6  mov     [rsp+350h+var_2F8], r12
0x18000d9ab  mov     [rsp+350h+var_2F0], r12
0x18000d9b0  mov     [rsp+350h+var_308], r12
0x18000d9b5  lea     rcx, [rbp+250h+pvarg]; pvarg
0x18000d9b9  call    cs:__imp_VariantInit
0x18000d9bf  nop
0x18000d9c0  lea     rcx, [rbp+250h+var_260]; pvarg
0x18000d9c4  call    cs:__imp_VariantInit
0x18000d9ca  nop
0x18000d9cb  lea     rcx, [rbp+250h+var_278]; pvarg
0x18000d9cf  call    cs:__imp_VariantInit
0x18000d9d5  nop
0x18000d9d6  lea     rcx, [rbp+250h+var_290]; pvarg
0x18000d9da  call    cs:__imp_VariantInit
0x18000d9e0  nop
0x18000d9e1  lea     rcx, psz; "\\"
0x18000d9e8  call    cs:__imp_SysAllocString
0x18000d9ee  mov     rsi, rax
0x18000d9f1  mov     [rbp+250h+var_230], rax
0x18000d9f5  test    rax, rax
0x18000d9f8  jz      loc_18000DF2A
0x18000d9fe  lea     rcx, psz; "\\"
0x18000da05  call    cs:__imp_SysAllocString
0x18000da0b  mov     rdi, rax
0x18000da0e  mov     [rbp+250h+var_228], rax
0x18000da12  test    rax, rax
0x18000da15  jz      loc_18000DF44
0x18000da1b  mov     word ptr [rsp+350h+pExceptionObject+4], r12w
0x18000da21  lea     eax, [r12+3]
0x18000da26  mov     word ptr [rbp+250h+var_2D0], ax
0x18000da2a  mov     dword ptr [rbp+250h+var_2D0+8], r12d
0x18000da2e  mov     dword ptr [rsp+350h+var_300], r12d
0x18000da33  mov     [rsp+350h+var_2D8], r12
0x18000da38  mov     [rsp+350h+var_2E0], r12
0x18000da3d  mov     [rsp+350h+var_2E8], 20119h
0x18000da46  mov     dword ptr [rsp+350h+pExceptionObject], r12d
0x18000da4b  mov     dword ptr [rsp+350h+var_300+4], r12d
0x18000da50  call    ?ShouldSkipSync@CAdReader@@SA_NXZ; CAdReader::ShouldSkipSync(void)
0x18000da55  test    al, al
0x18000da57  jz      loc_18000DAE6
0x18000da5d  lea     rcx, [rsp+350h+var_2E8]; this
0x18000da62  call    ??1CSrmRegistryKey@@QEAA@XZ; CSrmRegistryKey::~CSrmRegistryKey(void)
0x18000da67  nop
0x18000da68  lea     rcx, [rbp+250h+var_2D0]; pvarg
0x18000da6c  call    cs:__imp_VariantClear
0x18000da72  nop
0x18000da73  mov     rcx, rdi; bstrString
0x18000da76  call    cs:__imp_SysFreeString
0x18000da7c  nop
0x18000da7d  mov     rcx, rsi; bstrString
0x18000da80  call    cs:__imp_SysFreeString
0x18000da86  nop
0x18000da87  lea     rcx, [rbp+250h+var_290]; pvarg
0x18000da8b  call    cs:__imp_VariantClear
0x18000da91  nop
0x18000da92  lea     rcx, [rbp+250h+var_278]; pvarg
0x18000da96  call    cs:__imp_VariantClear
0x18000da9c  nop
0x18000da9d  lea     rcx, [rbp+250h+var_260]; pvarg
0x18000daa1  call    cs:__imp_VariantClear
0x18000daa7  nop
0x18000daa8  lea     rcx, [rbp+250h+pvarg]; pvarg
0x18000daac  call    cs:__imp_VariantClear
0x18000dab2  nop
0x18000dab3  mov     rcx, [rsp+350h+var_308]
0x18000dab8  test    rcx, rcx
0x18000dabb  jz      short loc_18000DACA
0x18000dabd  mov     rax, [rcx]
0x18000dac0  mov     rax, [rax+10h]
0x18000dac4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dac9  nop
0x18000daca  mov     rcx, [rsp+350h+var_2F0]
0x18000dacf  test    rcx, rcx
0x18000dad2  jz      short loc_18000DAE1
0x18000dad4  mov     rax, [rcx]
0x18000dad7  mov     rax, [rax+10h]
0x18000dadb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dae0  nop
0x18000dae1  jmp     loc_18000DE8A
0x18000dae6  lea     rax, [rsp+350h+var_2F8]
0x18000daeb  mov     [rsp+350h+ppv], rax; ppv
0x18000daf0  lea     r9, IID_ITaskService; riid
0x18000daf7  mov     r8d, r14d; dwClsContext
0x18000dafa  xor     edx, edx; pUnkOuter
0x18000dafc  lea     rcx, CLSID_TaskScheduler; rclsid
0x18000db03  call    cs:__imp_CoCreateInstance
0x18000db09  mov     [rbp+250h+var_118], eax
0x18000db0f  test    eax, eax
0x18000db11  js      loc_18000DF5E
0x18000db17  mov     [rbp+250h+var_118], eax
0x18000db1d  mov     rcx, [rsp+350h+var_2F8]
0x18000db22  movups  xmm0, xmmword ptr [rbp+250h+var_290]
0x18000db26  movsd   xmm1, qword ptr [rbp+250h+var_290+10h]
0x18000db2b  movups  xmm2, xmmword ptr [rbp+250h+var_278]
0x18000db2f  movsd   xmm3, qword ptr [rbp+250h+var_278+10h]
0x18000db34  movups  xmm4, xmmword ptr [rbp+250h+var_260]
0x18000db38  movsd   xmm5, qword ptr [rbp+250h+var_260+10h]
0x18000db3d  movups  xmm6, xmmword ptr [rbp+250h+pvarg]
0x18000db41  movsd   xmm7, qword ptr [rbp+250h+pvarg+10h]
0x18000db46  movaps  [rbp+250h+var_210], xmm0
0x18000db4a  movsd   [rbp+250h+var_200], xmm1
0x18000db4f  movaps  [rbp+250h+var_1F0], xmm2
0x18000db53  movsd   [rbp+250h+var_1E0], xmm3
0x18000db58  movaps  [rbp+250h+var_1D0], xmm4
0x18000db5f  movsd   [rbp+250h+var_1C0], xmm5
0x18000db67  movaps  [rbp+250h+var_2B0], xmm6
0x18000db6b  movsd   [rbp+250h+var_2A0], xmm7
0x18000db70  mov     rax, [rcx]
0x18000db73  lea     rdx, [rbp+250h+var_210]
0x18000db77  mov     [rsp+350h+ppv], rdx
0x18000db7c  lea     r9, [rbp+250h+var_1F0]
0x18000db80  lea     r8, [rbp+250h+var_1D0]
0x18000db87  lea     rdx, [rbp+250h+var_2B0]
0x18000db8b  mov     rax, [rax+50h]
0x18000db8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000db94  mov     [rbp+250h+var_118], eax
0x18000db9a  test    eax, eax
0x18000db9c  js      loc_18000DF9C
0x18000dba2  mov     [rbp+250h+var_118], eax
0x18000dba8  mov     rcx, [rsp+350h+var_2F8]
0x18000dbad  mov     rax, [rcx]
0x18000dbb0  lea     r8, [rsp+350h+var_2F0]
0x18000dbb5  mov     rdx, rsi
0x18000dbb8  mov     rax, [rax+38h]
0x18000dbbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dbc1  mov     [rbp+250h+var_118], eax
0x18000dbc7  test    eax, eax
0x18000dbc9  js      loc_18000DFDA
0x18000dbcf  mov     [rbp+250h+var_118], eax
0x18000dbd5  mov     r15, [rsp+350h+var_2F0]
0x18000dbda  mov     r13, [r15]
0x18000dbdd  lea     rcx, aMicrosoftWindo; "\\Microsoft\\Windows\\File Classificati"...
0x18000dbe4  call    cs:__imp_SysAllocString
0x18000dbea  mov     rbx, rax
0x18000dbed  mov     [rbp+250h+var_220], rax
0x18000dbf1  test    rax, rax
0x18000dbf4  jz      loc_18000E018
0x18000dbfa  lea     r8, [rsp+350h+var_308]
0x18000dbff  mov     rdx, rax
0x18000dc02  mov     rcx, r15
0x18000dc05  mov     rax, [r13+68h]
0x18000dc09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dc0e  mov     [rbp+250h+var_118], eax
0x18000dc14  mov     rcx, rbx; bstrString
0x18000dc17  call    cs:__imp_SysFreeString
0x18000dc1d  mov     eax, [rbp+250h+var_118]
0x18000dc23  test    eax, eax
0x18000dc25  js      loc_18000E032
0x18000dc2b  mov     [rbp+250h+var_118], eax
0x18000dc31  mov     rcx, [rsp+350h+var_308]
0x18000dc36  mov     rax, [rcx]
0x18000dc39  lea     rdx, [rsp+350h+pExceptionObject+4]
0x18000dc3e  mov     rax, [rax+50h]
0x18000dc42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dc47  mov     [rbp+250h+var_118], eax
0x18000dc4d  test    eax, eax
0x18000dc4f  js      loc_18000E070
0x18000dc55  mov     [rbp+250h+var_118], eax
0x18000dc5b  mov     rcx, [rsp+350h+var_308]
0x18000dc60  mov     rax, [rcx]
0x18000dc63  or      edx, 0FFFFFFFFh
0x18000dc66  mov     rax, [rax+58h]
0x18000dc6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dc6f  mov     [rbp+250h+var_118], eax
0x18000dc75  test    eax, eax
0x18000dc77  js      loc_18000E0AE
0x18000dc7d  mov     [rbp+250h+var_118], eax
0x18000dc83  mov     rcx, [rsp+350h+var_308]
0x18000dc88  movups  xmm0, xmmword ptr [rbp+250h+var_2D0]
0x18000dc8c  movaps  [rbp+250h+var_2B0], xmm0
0x18000dc90  movsd   xmm1, qword ptr [rbp+250h+var_2D0+10h]
0x18000dc95  movsd   [rbp+250h+var_2A0], xmm1
0x18000dc9a  mov     rax, [rcx]
0x18000dc9d  mov     [rsp+350h+var_328], r12
0x18000dca2  mov     [rsp+350h+ppv], r12
0x18000dca7  xor     r9d, r9d
0x18000dcaa  lea     r8d, [r9+2]
0x18000dcae  lea     rdx, [rbp+250h+var_2B0]
0x18000dcb2  mov     rax, [rax+68h]
0x18000dcb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dcbb  mov     [rbp+250h+var_118], eax
0x18000dcc1  test    eax, eax
0x18000dcc3  js      loc_18000E0EC
0x18000dcc9  mov     [rbp+250h+var_118], eax
0x18000dccf  mov     rcx, [rsp+350h+var_308]
0x18000dcd4  mov     rax, [rcx]
0x18000dcd7  lea     rdx, [rsp+350h+var_300]
0x18000dcdc  mov     rax, [rax+48h]
0x18000dce0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dce5  mov     [rbp+250h+var_118], eax
0x18000dceb  test    eax, eax
0x18000dced  js      loc_18000E12A
0x18000dcf3  mov     ebx, 78h ; 'x'
0x18000dcf8  mov     [rbp+250h+var_118], eax
0x18000dcfe  cmp     dword ptr [rsp+350h+var_300], 3
0x18000dd03  jz      short loc_18000DD54
0x18000dd05  test    ebx, ebx
0x18000dd07  jle     loc_18000E168
0x18000dd0d  mov     ecx, 1F4h; dwMilliseconds
0x18000dd12  call    cs:__imp_Sleep
0x18000dd18  mov     rcx, [rsp+350h+var_308]
0x18000dd1d  mov     rax, [rcx]
0x18000dd20  lea     rdx, [rsp+350h+var_300]
0x18000dd25  mov     rax, [rax+48h]
0x18000dd29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dd2e  mov     [rbp+250h+var_118], eax
0x18000dd34  test    eax, eax
0x18000dd36  js      loc_18000E1C6
0x18000dd3c  sub     ebx, r14d
0x18000dd3f  mov     [rbp+250h+var_118], eax
0x18000dd45  cmp     dword ptr [rsp+350h+var_300], 3
0x18000dd4a  jnz     short loc_18000DD05
0x18000dd4c  test    ebx, ebx
0x18000dd4e  jle     loc_18000E168
0x18000dd54  lea     r8, aSoftwareMicros; "Software\\Microsoft\\FileClassification"...
0x18000dd5b  mov     rdx, 0FFFFFFFF80000002h; hKey
0x18000dd62  lea     rcx, [rsp+350h+var_2E8]; this
0x18000dd67  call    ?Open@CSrmRegistryKey@@QEAA_NPEAUHKEY__@@PEBGZZ; CSrmRegistryKey::Open(HKEY__ *,ushort const *,...)
0x18000dd6c  test    al, al
0x18000dd6e  jz      short loc_18000DD93
0x18000dd70  lea     r8, [rsp+350h+pExceptionObject]; unsigned int *
0x18000dd75  lea     rdx, aAdleavetaskena; "AdLeaveTaskEnabled"
0x18000dd7c  lea     rcx, [rsp+350h+var_2E8]; this
0x18000dd81  call    ?GetValue@CSrmRegistryKey@@QEAA_NPEBGPEAK_N@Z; CSrmRegistryKey::GetValue(ushort const *,ulong *,bool)
0x18000dd86  test    al, al
0x18000dd88  jz      short loc_18000DD93
0x18000dd8a  cmp     dword ptr [rsp+350h+pExceptionObject], r12d
0x18000dd8f  cmovnz  r14d, r12d
0x18000dd93  cmp     word ptr [rsp+350h+pExceptionObject+4], r12w
0x18000dd99  jnz     short loc_18000DDC7
0x18000dd9b  test    r14b, r14b
0x18000dd9e  jz      short loc_18000DDC7
0x18000dda0  mov     rcx, [rsp+350h+var_308]
0x18000dda5  mov     rax, [rcx]
0x18000dda8  xor     edx, edx
0x18000ddaa  mov     rax, [rax+58h]
0x18000ddae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ddb3  mov     [rbp+250h+var_118], eax
0x18000ddb9  test    eax, eax
0x18000ddbb  js      loc_18000E204
0x18000ddc1  mov     [rbp+250h+var_118], eax
0x18000ddc7  mov     rcx, [rsp+350h+var_308]
0x18000ddcc  mov     rax, [rcx]
0x18000ddcf  lea     rdx, [rsp+350h+var_300+4]
0x18000ddd4  mov     rax, [rax+80h]
0x18000dddb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dde0  mov     [rbp+250h+var_118], eax
0x18000dde6  test    eax, eax
0x18000dde8  js      loc_18000E242
0x18000ddee  mov     eax, dword ptr [rsp+350h+var_300+4]
0x18000ddf2  mov     [rbp+250h+var_118], eax
0x18000ddf8  test    eax, eax
0x18000ddfa  js      loc_18000DEEC
0x18000de00  mov     [rbp+250h+var_118], eax
0x18000de06  lea     rcx, [rsp+350h+var_2E8]; this
0x18000de0b  call    ??1CSrmRegistryKey@@QEAA@XZ; CSrmRegistryKey::~CSrmRegistryKey(void)
0x18000de10  nop
0x18000de11  lea     rcx, [rbp+250h+var_2D0]; pvarg
0x18000de15  call    cs:__imp_VariantClear
0x18000de1b  nop
0x18000de1c  mov     rcx, rdi; bstrString
0x18000de1f  call    cs:__imp_SysFreeString
0x18000de25  nop
  ... truncated ...
```
