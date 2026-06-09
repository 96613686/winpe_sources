# SetCommonModuleParams(InBoxModuleDefinition &,CFciModuleDefinitionBase *,ushort *,ushort *)

- ea: `0x18001cb84`
- end: `0x18001d438`
- name: `?SetCommonModuleParams@@YAXAEAUInBoxModuleDefinition@@PEAVCFciModuleDefinitionBase@@PEAG2@Z`
- size: `2228`
- prototype: `void __fastcall(struct InBoxModuleDefinition *, struct CFciModuleDefinitionBase *, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `23`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18001c1f0`

## callees

- `0x180001350`
- `0x1800020ba`
- `0x18000266c`
- `0x180006a1c`
- `0x1800095f4`
- `0x18000af40`
- `0x18000ead4`
- `0x18000ebd4`
- `0x180010b24`
- `0x180010bc4`
- `0x1800161d0`
- `0x18001af5c`
- `0x18001bc58`
- `0x18001bd9c`
- `0x18001cb84`
- `0x18001d440`
- `0x18001d934`
- `0x18006febc`
- `0x1800700b8`
- `0x180073a80`
- `0x1800b078a`
- `0x1800b07d0`
- `0x1800d5010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18001cee8`
- `ole32!CoTaskMemFree` at `0x18001cee8`
- `OLEAUT32!__imp_SysAllocString` at `0x18001d176`
- `OLEAUT32!__imp_SysAllocString` at `0x18001d191`
- `OLEAUT32!__imp_SysAllocString` at `0x18001d1ac`
- `OLEAUT32!__imp_SysAllocString` at `0x18001d176`
- `OLEAUT32!__imp_SysAllocString` at `0x18001d191`
- `OLEAUT32!__imp_SysAllocString` at `0x18001d1ac`
- `OLEAUT32!__imp_SysFreeString` at `0x18001ccd7`
- `OLEAUT32!__imp_SysFreeString` at `0x18001cd52`
- `OLEAUT32!__imp_SysFreeString` at `0x18001cd8d`
- `OLEAUT32!__imp_SysFreeString` at `0x18001d100`
- `OLEAUT32!__imp_SysFreeString` at `0x18001d10a`
- `OLEAUT32!__imp_SysFreeString` at `0x18001d114`
- `OLEAUT32!__imp_SysFreeString` at `0x18001ccd7`
- `OLEAUT32!__imp_SysFreeString` at `0x18001cd52`
- `OLEAUT32!__imp_SysFreeString` at `0x18001cd8d`
- `OLEAUT32!__imp_SysFreeString` at `0x18001d100`
- `OLEAUT32!__imp_SysFreeString` at `0x18001d10a`
- `OLEAUT32!__imp_SysFreeString` at `0x18001d114`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18001cef7`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18001d0cc`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18001cef7`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18001d0cc`

## string_xrefs

- `0x18001cbbd`: `base\fs\fsrm\service\globalstore\inboxmodules.cpp`
- `0x18001cbc8`: `SetCommonModuleParams`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
void __fastcall SetCommonModuleParams(
        struct InBoxModuleDefinition *a1,
        struct CFciModuleDefinitionBase *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4)
{
  OLECHAR *v8; // rsi
  __int64 v9; // rdx
  int v10; // eax
  void *StringW; // rax
  const OLECHAR *v12; // rdi
  OLECHAR *v13; // r14
  int v14; // eax
  void *v15; // rax
  const OLECHAR *v16; // rdi
  int v17; // eax
  OLECHAR *v18; // rdi
  int v19; // eax
  int v20; // eax
  int v21; // eax
  __int64 v22; // rdx
  int v23; // eax
  int v24; // eax
  SAFEARRAY *v25; // r15
  const unsigned __int16 *v26; // rdx
  int v27; // eax
  int v28; // eax
  __int64 v29; // rax
  void *v30; // r15
  void *v31; // rbx
  SAFEARRAY *v32; // r13
  int v33; // eax
  __int64 v34; // rcx
  __int64 v35; // r12
  int v36; // eax
  char v37; // al
  int Hr; // eax
  char v39; // al
  int v40; // eax
  char v41; // al
  int v42; // eax
  char v43; // al
  int v44; // eax
  char v45; // al
  int v46; // eax
  char v47; // al
  int v48; // eax
  char v49; // al
  int v50; // eax
  char v51; // al
  int v52; // eax
  char v53; // al
  int v54; // eax
  char v55; // al
  int v56; // eax
  char v57; // al
  __int64 pExceptionObject; // [rsp+20h] [rbp-E0h] BYREF
  SAFEARRAY *psa; // [rsp+28h] [rbp-D8h] BYREF
  LPVOID pv; // [rsp+30h] [rbp-D0h] BYREF
  OLECHAR *v61; // [rsp+38h] [rbp-C8h]
  OLECHAR *v62; // [rsp+40h] [rbp-C0h]
  OLECHAR *v63; // [rsp+48h] [rbp-B8h]
  void **v64; // [rsp+50h] [rbp-B0h]
  SAFEARRAY *v65; // [rsp+58h] [rbp-A8h]
  void *v66[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v67; // [rsp+70h] [rbp-90h]
  _QWORD v68[4]; // [rsp+80h] [rbp-80h] BYREF
  int v69; // [rsp+A0h] [rbp-60h]
  _BYTE v70[96]; // [rsp+A8h] [rbp-58h] BYREF
  int v71; // [rsp+108h] [rbp+8h]
  OLECHAR *psz[2]; // [rsp+110h] [rbp+10h] BYREF
  __int64 v73; // [rsp+120h] [rbp+20h]
  unsigned __int64 v74; // [rsp+128h] [rbp+28h]
  void **v75; // [rsp+140h] [rbp+40h] BYREF
  int v76; // [rsp+148h] [rbp+48h]
  void *Block[3]; // [rsp+1F0h] [rbp+F0h] BYREF
  unsigned __int64 v78; // [rsp+208h] [rbp+108h]
  void *Src[2]; // [rsp+218h] [rbp+118h] BYREF
  __int64 v80; // [rsp+228h] [rbp+128h]
  unsigned __int64 v81; // [rsp+230h] [rbp+130h]
  GUID pclsid; // [rsp+240h] [rbp+140h] BYREF
  void *v83[5]; // [rsp+250h] [rbp+150h] BYREF

  v68[0] = L"base\\fs\\fsrm\\service\\globalstore\\inboxmodules.cpp";
  v68[1] = L"SetCommonModuleParams";
  v68[2] = L"CINBOXMD";
  v68[3] = 398;
  v8 = 0;
  v69 = 255;
  v71 = 0x1000000;
  memset_0(v70, 0, sizeof(v70));
  CSrmFunctionTracer::CSrmFunctionTracer((__int64)&v75, (const struct CSrmDebugInfo *)v68, 0);
  v74 = 7;
  v73 = 0;
  LOWORD(psz[0]) = 0;
  v61 = 0;
  v62 = 0;
  v63 = 0;
  pclsid = GUID_NULL;
  CSrmID::Initialize(&pclsid, (struct CSrmFunctionTracer *)&v75, *(LPCOLESTR *)a1, -2147418113);
  *(GUID *)((char *)a2 + 8) = pclsid;
  LOWORD(v9) = -(*((_BYTE *)a1 + 8) != 0);
  v10 = (*(__int64 (__fastcall **)(struct CFciModuleDefinitionBase *, __int64))(*(_QWORD *)a2 + 160LL))(a2, v9);
  v76 = v10;
  if ( v10 < 0 )
  {
    Hr = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v75);
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v75, Hr);
    v39 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v75);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v75, 0x19Eu, v39, 0);
  }
  v76 = v10;
  StringW = (void *)CSrmResource::LoadStringW(Block, *((_DWORD *)a1 + 6));
  std::wstring::assign(psz, StringW);
  if ( v78 >= 8 )
    operator delete(Block[0]);
  v12 = (const OLECHAR *)psz;
  if ( v74 >= 8 )
    v12 = psz[0];
  SysFreeString(0);
  if ( v12 )
  {
    v13 = SysAllocString(v12);
    v61 = v13;
    if ( !v13 )
    {
      LODWORD(pExceptionObject) = -2147024882;
      throw (long *)&pExceptionObject;
    }
  }
  else
  {
    v13 = 0;
    v61 = 0;
  }
  v14 = (*(__int64 (__fastcall **)(struct CFciModuleDefinitionBase *, OLECHAR *))(*(_QWORD *)a2 + 32LL))(a2, v13);
  v76 = v14;
  if ( v14 < 0 )
  {
    v40 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v75);
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v75, v40);
    v41 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v75);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v75, 0x1A3u, v41, 0);
  }
  v76 = v14;
  v15 = (void *)CSrmResource::LoadStringW(Block, *((_DWORD *)a1 + 10));
  std::wstring::assign(psz, v15);
  if ( v78 >= 8 )
    operator delete(Block[0]);
  v16 = (const OLECHAR *)psz;
  if ( v74 >= 8 )
    v16 = psz[0];
  SysFreeString(0);
  if ( v16 )
  {
    v8 = SysAllocString(v16);
    v62 = v8;
    if ( !v8 )
    {
      LODWORD(pExceptionObject) = -2147024882;
      throw (long *)&pExceptionObject;
    }
  }
  else
  {
    v62 = 0;
  }
  v17 = (*(__int64 (__fastcall **)(struct CFciModuleDefinitionBase *, OLECHAR *))(*(_QWORD *)a2 + 16LL))(a2, v8);
  v76 = v17;
  if ( v17 < 0 )
  {
    v42 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v75);
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v75, v42);
    v43 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v75);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v75, 0x1A8u, v43, 0);
  }
  v76 = v17;
  v18 = (OLECHAR *)*((_QWORD *)a1 + 2);
  SysFreeString(0);
  if ( v18 )
  {
    v18 = SysAllocString(v18);
    v63 = v18;
    if ( !v18 )
    {
      LODWORD(pExceptionObject) = -2147024882;
      throw (long *)&pExceptionObject;
    }
  }
  else
  {
    v63 = 0;
  }
  v19 = (*(__int64 (__fastcall **)(struct CFciModuleDefinitionBase *, OLECHAR *))(*(_QWORD *)a2 + 104LL))(a2, v18);
  v76 = v19;
  if ( v19 < 0 )
  {
    v44 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v75);
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v75, v44);
    v45 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v75);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v75, 0x1ACu, v45, 0);
  }
  v76 = v19;
  v20 = (*(__int64 (__fastcall **)(struct CFciModuleDefinitionBase *, unsigned __int16 *))(*(_QWORD *)a2 + 120LL))(
          a2,
          a3);
  v76 = v20;
  if ( v20 < 0 )
  {
    v46 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v75);
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v75, v46);
    v47 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v75);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v75, 0x1AFu, v47, 0);
  }
  v76 = v20;
  v21 = (*(__int64 (__fastcall **)(struct CFciModuleDefinitionBase *, unsigned __int16 *))(*(_QWORD *)a2 + 136LL))(
          a2,
          a4);
  v76 = v21;
  if ( v21 < 0 )
  {
    v48 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v75);
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v75, v48);
    v49 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v75);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v75, 0x1B0u, v49, 0);
  }
  v76 = v21;
  LOWORD(v22) = -(*((_BYTE *)a1 + 44) != 0);
  v23 = (*(__int64 (__fastcall **)(struct CFciModuleDefinitionBase *, __int64))(*(_QWORD *)a2 + 176LL))(a2, v22);
  v76 = v23;
  if ( v23 < 0 )
  {
    v50 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v75);
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v75, v50);
    v51 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v75);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v75, 0x1B3u, v51, 0);
  }
  v76 = v23;
  v24 = (*(__int64 (__fastcall **)(struct CFciModuleDefinitionBase *, _QWORD))(*(_QWORD *)a2 + 192LL))(
          a2,
          *((unsigned int *)a1 + 12));
  v76 = v24;
  if ( v24 < 0 )
  {
    v52 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v75);
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v75, v52);
    v53 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v75);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v75, 0x1B6u, v53, 0);
  }
  v76 = v24;
  psa = 0;
  v25 = 0;
  v65 = 0;
  v64 = &CSrmAuto<tagSAFEARRAY *,CSrmAutoGenericValue_Storage<tagSAFEARRAY *,0,long (*)(tagSAFEARRAY *),&long SafeArrayDestroy(tagSAFEARRAY *),tagSAFEARRAY * & (*)(tagSAFEARRAY * &),&public: static tagSAFEARRAY * & DTyper<tagSAFEARRAY *>::Identity(tagSAFEARRAY * &)>>::`vftable';
  LODWORD(pExceptionObject) = 0;
  v26 = (const unsigned __int16 *)*((_QWORD *)a1 + 7);
  if ( v26 && *v26 )
  {
    pv = 0;
    CSrmAutoPWSZ::CopyFrom(&pv, v26);
    v27 = ParseStringToSafearray((OLECHAR *)pv, &psa, (int *)&pExceptionObject);
    v76 = v27;
    if ( v27 < 0 )
    {
      v54 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v75);
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v75, v54);
      v55 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v75);
      CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v75, 0x1C3u, v55, 0, pExceptionObject);
    }
    v76 = v27;
    v25 = psa;
    v65 = psa;
    v28 = (*(__int64 (__fastcall **)(struct CFciModuleDefinitionBase *, SAFEARRAY *))(*(_QWORD *)a2 + 208LL))(a2, psa);
    v76 = v28;
    if ( v28 < 0 )
    {
      v56 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v75);
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v75, v56);
      v57 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v75);
      CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v75, 0x1C7u, v57, 0, pExceptionObject);
    }
    v76 = v28;
    CoTaskMemFree(pv);
  }
  if ( v25 )
    SafeArrayDestroy(v25);
  *(_OWORD *)v66 = 0;
  v67 = 0;
  v65 = 0;
  v64 = &CSrmAuto<tagSAFEARRAY *,CSrmAutoGenericValue_Storage<tagSAFEARRAY *,0,long (*)(tagSAFEARRAY *),&long SafeArrayDestroy(tagSAFEARRAY *),tagSAFEARRAY * & (*)(tagSAFEARRAY * &),&public: static tagSAFEARRAY * & DTyper<tagSAFEARRAY *>::Identity(tagSAFEARRAY * &)>>::`vftable';
  psa = 0;
  SrmDelimitedStringToVector(*((unsigned __int16 **)a1 + 8));
  v81 = 7;
  v80 = 0;
  LOWORD(Src[0]) = 0;
  std::wstring::assign(Src, L"StaticModuleName");
  std::wstring::append(Src, L"=");
  std::wstring::append(Src, *((void **)a1 + 4));
  std::vector<std::wstring>::push_back(v66, Src);
  if ( *((_DWORD *)a1 + 18) != -1 )
  {
    v78 = 7;
    Block[2] = 0;
    LOWORD(Block[0]) = 0;
    std::wstring::assign(Block, L"ParameterDescription=");
    v29 = CSrmResource::LoadStringW(v83, *((_DWORD *)a1 + 18));
    std::wstring::append(Block, v29, 0, -1);
    if ( v83[3] >= (void *)8 )
      operator delete(v83[0]);
    std::vector<std::wstring>::push_back(v66, Block);
    if ( v78 >= 8 )
      operator delete(Block[0]);
  }
  v30 = v66[1];
  v31 = v66[0];
  SrmStringRangeToSafeArray<std::_Vector_const_iterator<std::_Vector_val<std::wstring>>>(
    (__int64)v66[0],
    (__int64)v66[1],
    0xCCCCCCCCCCCCCCCDuLL * (((char *)v66[1] - (char *)v66[0]) >> 3),
    &psa);
  v32 = psa;
  v65 = psa;
  v33 = (*(__int64 (__fastcall **)(struct CFciModuleDefinitionBase *, SAFEARRAY *))(*(_QWORD *)a2 + 48LL))(a2, psa);
  v76 = v33;
  if ( v33 < 0 )
  {
    v36 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v75);
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v75, v36);
    v37 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v75);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v75, 0x1E9u, v37, 0, pExceptionObject);
  }
  v76 = v33;
  if ( v81 >= 8 )
    operator delete(Src[0]);
  v81 = 7;
  v80 = 0;
  LOWORD(Src[0]) = 0;
  if ( v32 )
    SafeArrayDestroy(v32);
  if ( v31 )
  {
    if ( v31 != v30 )
    {
      v35 = (__int64)v31;
      do
      {
        std::_Dest_val<std::allocator<std::wstring>,std::wstring>(v34, v35);
        v35 += 40;
      }
      while ( (void *)v35 != v30 );
    }
    operator delete(v31);
  }
  SysFreeString(v18);
  SysFreeString(v8);
  SysFreeString(v13);
  if ( v74 >= 8 )
    operator delete(psz[0]);
  v74 = 7;
  v73 = 0;
  LOWORD(psz[0]) = 0;
  v75 = &CSrmFunctionTracer::`vftable';
  CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)&v75);
}

```

## disassembly

```asm
0x18001cb84  push    rbp
0x18001cb86  push    rbx
0x18001cb87  push    rsi
0x18001cb88  push    rdi
0x18001cb89  push    r12
0x18001cb8b  push    r13
0x18001cb8d  push    r14
0x18001cb8f  push    r15
0x18001cb91  lea     rbp, [rsp-188h]
0x18001cb99  sub     rsp, 288h
0x18001cba0  mov     rax, cs:__security_cookie
0x18001cba7  xor     rax, rsp
0x18001cbaa  mov     [rbp+1C0h+var_48], rax
0x18001cbb1  mov     r13, r9
0x18001cbb4  mov     r15, r8
0x18001cbb7  mov     r12, rdx
0x18001cbba  mov     rbx, rcx
0x18001cbbd  lea     rax, aBaseFsFsrmServ_2; "base\\fs\\fsrm\\service\\globalstore\\i"...
0x18001cbc4  mov     [rbp+1C0h+var_240], rax
0x18001cbc8  lea     rax, aSetcommonmodul; "SetCommonModuleParams"
0x18001cbcf  mov     [rbp+1C0h+var_238], rax
0x18001cbd3  lea     rax, aCinboxmd; "CINBOXMD"
0x18001cbda  mov     [rbp+1C0h+var_230], rax
0x18001cbde  mov     [rbp+1C0h+var_228], 18Eh
0x18001cbe6  xor     esi, esi
0x18001cbe8  mov     [rbp+1C0h+var_220], 0FFh
0x18001cbef  mov     [rbp+1C0h+var_1B8], 1000000h
0x18001cbf6  xor     edx, edx; Val
0x18001cbf8  lea     r8d, [rsi+60h]; Size
0x18001cbfc  lea     rcx, [rbp+1C0h+var_218]; void *
0x18001cc00  call    memset_0
0x18001cc05  xor     r8d, r8d
0x18001cc08  lea     rdx, [rbp+1C0h+var_240]
0x18001cc0c  lea     rcx, [rbp+1C0h+var_180]
0x18001cc10  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x18001cc15  nop
0x18001cc16  mov     [rbp+1C0h+var_198], 7
0x18001cc1e  mov     [rbp+1C0h+var_1A0], rsi
0x18001cc22  mov     word ptr [rbp+1C0h+psz], si
0x18001cc26  mov     [rsp+2C0h+var_288], rsi
0x18001cc2b  mov     [rsp+2C0h+var_280], rsi
0x18001cc30  mov     [rsp+2C0h+var_278], rsi
0x18001cc35  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18001cc3c  movdqu  xmmword ptr [rbp+1C0h+pclsid.Data1], xmm0
0x18001cc44  mov     r9d, 8000FFFFh; int
0x18001cc4a  mov     r8, [rbx]; lpsz
0x18001cc4d  lea     rdx, [rbp+1C0h+var_180]; this
0x18001cc51  lea     rcx, [rbp+1C0h+pclsid]; pclsid
0x18001cc58  call    ?Initialize@CSrmID@@QEAAXAEAVCSrmFunctionTracer@@PEBGJ@Z; CSrmID::Initialize(CSrmFunctionTracer &,ushort const *,long)
0x18001cc5d  movaps  xmm0, xmmword ptr [rbp+1C0h+pclsid.Data1]
0x18001cc64  movdqu  xmmword ptr [r12+8], xmm0
0x18001cc6b  mov     r8, [r12]
0x18001cc6f  mov     al, [rbx+8]
0x18001cc72  neg     al
0x18001cc74  sbb     dx, dx
0x18001cc77  mov     rcx, r12
0x18001cc7a  mov     rax, [r8+0A0h]
0x18001cc81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cc86  mov     [rbp+1C0h+var_178], eax
0x18001cc89  test    eax, eax
0x18001cc8b  js      loc_18001D244
0x18001cc91  mov     [rbp+1C0h+var_178], eax
0x18001cc94  mov     edx, [rbx+18h]; uID
0x18001cc97  lea     rcx, [rbp+1C0h+Block]; void *
0x18001cc9e  call    ?LoadStringW@CSrmResource@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@I@Z; CSrmResource::LoadStringW(uint)
0x18001cca3  nop
0x18001cca4  mov     rdx, rax; Src
0x18001cca7  lea     rcx, [rbp+1C0h+psz]; void *
0x18001ccab  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@$$QEAV12@@Z; std::wstring::assign(std::wstring &&)
0x18001ccb0  nop
0x18001ccb1  cmp     [rbp+1C0h+var_B8], 8
0x18001ccb9  jb      short loc_18001CCC7
0x18001ccbb  mov     rcx, [rbp+1C0h+Block]; Block
0x18001ccc2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001ccc7  lea     rdi, [rbp+1C0h+psz]
0x18001cccb  cmp     [rbp+1C0h+var_198], 8
0x18001ccd0  cmovnb  rdi, [rbp+1C0h+psz]
0x18001ccd5  xor     ecx, ecx; bstrString
0x18001ccd7  call    cs:__imp_SysFreeString
0x18001ccdd  test    rdi, rdi
0x18001cce0  jnz     loc_18001D173
0x18001cce6  mov     r14, rsi
0x18001cce9  mov     [rsp+2C0h+var_288], rsi
0x18001ccee  mov     rax, [r12]
0x18001ccf2  mov     rdx, r14
0x18001ccf5  mov     rcx, r12
0x18001ccf8  mov     rax, [rax+20h]
0x18001ccfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cd01  mov     [rbp+1C0h+var_178], eax
0x18001cd04  test    eax, eax
0x18001cd06  js      loc_18001D276
0x18001cd0c  mov     [rbp+1C0h+var_178], eax
0x18001cd0f  mov     edx, [rbx+28h]; uID
0x18001cd12  lea     rcx, [rbp+1C0h+Block]; void *
0x18001cd19  call    ?LoadStringW@CSrmResource@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@I@Z; CSrmResource::LoadStringW(uint)
0x18001cd1e  nop
0x18001cd1f  mov     rdx, rax; Src
0x18001cd22  lea     rcx, [rbp+1C0h+psz]; void *
0x18001cd26  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@$$QEAV12@@Z; std::wstring::assign(std::wstring &&)
0x18001cd2b  nop
0x18001cd2c  cmp     [rbp+1C0h+var_B8], 8
0x18001cd34  jb      short loc_18001CD42
0x18001cd36  mov     rcx, [rbp+1C0h+Block]; Block
0x18001cd3d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001cd42  lea     rdi, [rbp+1C0h+psz]
0x18001cd46  cmp     [rbp+1C0h+var_198], 8
0x18001cd4b  cmovnb  rdi, [rbp+1C0h+psz]
0x18001cd50  xor     ecx, ecx; bstrString
0x18001cd52  call    cs:__imp_SysFreeString
0x18001cd58  test    rdi, rdi
0x18001cd5b  jnz     loc_18001D18E
0x18001cd61  mov     [rsp+2C0h+var_280], rsi
0x18001cd66  mov     rax, [r12]
0x18001cd6a  mov     rdx, rsi
0x18001cd6d  mov     rcx, r12
0x18001cd70  mov     rax, [rax+10h]
0x18001cd74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cd79  mov     [rbp+1C0h+var_178], eax
0x18001cd7c  test    eax, eax
0x18001cd7e  js      loc_18001D2A8
0x18001cd84  mov     [rbp+1C0h+var_178], eax
0x18001cd87  mov     rdi, [rbx+10h]
0x18001cd8b  xor     ecx, ecx; bstrString
0x18001cd8d  call    cs:__imp_SysFreeString
0x18001cd93  test    rdi, rdi
0x18001cd96  jnz     loc_18001D1A9
0x18001cd9c  mov     [rsp+2C0h+var_278], rdi
0x18001cda1  mov     rax, [r12]
0x18001cda5  mov     rdx, rdi
0x18001cda8  mov     rcx, r12
0x18001cdab  mov     rax, [rax+68h]
0x18001cdaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cdb4  mov     [rbp+1C0h+var_178], eax
0x18001cdb7  test    eax, eax
0x18001cdb9  js      loc_18001D2DA
0x18001cdbf  mov     [rbp+1C0h+var_178], eax
0x18001cdc2  mov     rax, [r12]
0x18001cdc6  mov     rdx, r15
0x18001cdc9  mov     rcx, r12
0x18001cdcc  mov     rax, [rax+78h]
0x18001cdd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cdd5  mov     [rbp+1C0h+var_178], eax
0x18001cdd8  test    eax, eax
0x18001cdda  js      loc_18001D30C
0x18001cde0  mov     [rbp+1C0h+var_178], eax
0x18001cde3  mov     rax, [r12]
0x18001cde7  mov     rdx, r13
0x18001cdea  mov     rcx, r12
0x18001cded  mov     rax, [rax+88h]
0x18001cdf4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cdf9  mov     [rbp+1C0h+var_178], eax
0x18001cdfc  xor     r13d, r13d
0x18001cdff  test    eax, eax
0x18001ce01  js      loc_18001D33E
0x18001ce07  mov     [rbp+1C0h+var_178], eax
0x18001ce0a  mov     r8, [r12]
0x18001ce0e  mov     al, [rbx+2Ch]
0x18001ce11  neg     al
0x18001ce13  sbb     dx, dx
0x18001ce16  mov     rcx, r12
0x18001ce19  mov     rax, [r8+0B0h]
0x18001ce20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ce25  mov     [rbp+1C0h+var_178], eax
0x18001ce28  test    eax, eax
0x18001ce2a  js      loc_18001D370
0x18001ce30  mov     [rbp+1C0h+var_178], eax
0x18001ce33  mov     rax, [r12]
0x18001ce37  mov     edx, [rbx+30h]
0x18001ce3a  mov     rcx, r12
0x18001ce3d  mov     rax, [rax+0C0h]
0x18001ce44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ce49  mov     [rbp+1C0h+var_178], eax
0x18001ce4c  test    eax, eax
0x18001ce4e  js      loc_18001D3A2
0x18001ce54  mov     [rbp+1C0h+var_178], eax
0x18001ce57  mov     [rsp+2C0h+psa], r13
0x18001ce5c  mov     r15d, r13d
0x18001ce5f  mov     [rsp+2C0h+var_268], r13
0x18001ce64  lea     rax, ??_7?$CSrmAuto@PEAUtagSAFEARRAY@@V?$CSrmAutoGenericValue_Storage@PEAUtagSAFEARRAY@@$0A@P6AJPEAU1@@Z$1?SafeArrayDestroy@@YAJ0@ZP6AAEAPEAU1@AEAPEAU1@@Z$1?Identity@?$DTyper@PEAUtagSAFEARRAY@@@@SAAEAPEAU1@1@Z@@@@6B@; const CSrmAuto<tagSAFEARRAY *,CSrmAutoGenericValue_Storage<tagSAFEARRAY *,0,long (*)(tagSAFEARRAY *),&SafeArrayDestroy(tagSAFEARRAY *),tagSAFEARRAY * & (*)(tagSAFEARRAY * &),&DTyper<tagSAFEARRAY *>::Identity(tagSAFEARRAY * &)>>::`vftable'
0x18001ce6b  mov     [rsp+2C0h+var_270], rax
0x18001ce70  mov     dword ptr [rsp+2C0h+pExceptionObject], r13d
0x18001ce75  mov     rdx, [rbx+38h]; unsigned __int16 *
0x18001ce79  test    rdx, rdx
0x18001ce7c  jz      short loc_18001CEEF
0x18001ce7e  cmp     [rdx], r13w
0x18001ce82  jz      short loc_18001CEEF
0x18001ce84  mov     [rsp+2C0h+pv], r13
0x18001ce89  lea     rcx, [rsp+2C0h+pv]; this
0x18001ce8e  call    ?CopyFrom@CSrmAutoPWSZ@@QEAAXPEBG@Z; CSrmAutoPWSZ::CopyFrom(ushort const *)
0x18001ce93  lea     r8, [rsp+2C0h+pExceptionObject]; int *
0x18001ce98  lea     rdx, [rsp+2C0h+psa]; struct tagSAFEARRAY **
0x18001ce9d  mov     rcx, [rsp+2C0h+pv]; psz
0x18001cea2  call    ?ParseStringToSafearray@@YAJPEAGPEAPEAUtagSAFEARRAY@@PEAJ@Z; ParseStringToSafearray(ushort *,tagSAFEARRAY * *,long *)
0x18001cea7  mov     [rbp+1C0h+var_178], eax
0x18001ceaa  test    eax, eax
0x18001ceac  js      loc_18001D3D4
0x18001ceb2  mov     [rbp+1C0h+var_178], eax
0x18001ceb5  mov     r15, [rsp+2C0h+psa]
0x18001ceba  mov     [rsp+2C0h+var_268], r15
0x18001cebf  mov     rax, [r12]
0x18001cec3  mov     rdx, r15
0x18001cec6  mov     rcx, r12
0x18001cec9  mov     rax, [rax+0D0h]
0x18001ced0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ced5  mov     [rbp+1C0h+var_178], eax
0x18001ced8  test    eax, eax
0x18001ceda  js      loc_18001D406
0x18001cee0  mov     [rbp+1C0h+var_178], eax
0x18001cee3  mov     rcx, [rsp+2C0h+pv]; pv
0x18001cee8  call    cs:__imp_CoTaskMemFree
0x18001ceee  nop
0x18001ceef  test    r15, r15
0x18001cef2  jz      short loc_18001CEFD
0x18001cef4  mov     rcx, r15; psa
0x18001cef7  call    cs:__imp_SafeArrayDestroy
0x18001cefd  xorps   xmm0, xmm0
0x18001cf00  movdqu  xmmword ptr [rsp+2C0h+var_260], xmm0
0x18001cf06  mov     [rsp+2C0h+var_250], r13
0x18001cf0b  mov     [rsp+2C0h+var_268], r13
0x18001cf10  lea     rax, ??_7?$CSrmAuto@PEAUtagSAFEARRAY@@V?$CSrmAutoGenericValue_Storage@PEAUtagSAFEARRAY@@$0A@P6AJPEAU1@@Z$1?SafeArrayDestroy@@YAJ0@ZP6AAEAPEAU1@AEAPEAU1@@Z$1?Identity@?$DTyper@PEAUtagSAFEARRAY@@@@SAAEAPEAU1@1@Z@@@@6B@; const CSrmAuto<tagSAFEARRAY *,CSrmAutoGenericValue_Storage<tagSAFEARRAY *,0,long (*)(tagSAFEARRAY *),&SafeArrayDestroy(tagSAFEARRAY *),tagSAFEARRAY * & (*)(tagSAFEARRAY * &),&DTyper<tagSAFEARRAY *>::Identity(tagSAFEARRAY * &)>>::`vftable'
0x18001cf17  mov     [rsp+2C0h+var_270], rax
0x18001cf1c  mov     [rsp+2C0h+psa], r13
0x18001cf21  lea     r8, [rsp+2C0h+var_260]
0x18001cf26  mov     rcx, [rbx+40h]; unsigned __int16 *
0x18001cf2a  call    ?SrmDelimitedStringToVector@@YAXPEBGGAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; SrmDelimitedStringToVector(ushort const *,ushort,std::vector<std::wstring> &)
0x18001cf2f  mov     r15d, 7
0x18001cf35  mov     [rbp+1C0h+var_90], r15
0x18001cf3c  mov     [rbp+1C0h+var_98], r13
0x18001cf43  mov     word ptr [rbp+1C0h+Src], r13w
0x18001cf4b  lea     r8d, [r15+9]
0x18001cf4f  lea     rdx, aStaticmodulena; "StaticModuleName"
0x18001cf56  lea     rcx, [rbp+1C0h+Src]; void *
0x18001cf5d  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x18001cf62  nop
0x18001cf63  lea     rdx, asc_1800DFDEC; "="
0x18001cf6a  lea     rcx, [rbp+1C0h+Src]; Src
0x18001cf71  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x18001cf76  mov     rdx, [rbx+20h]; void *
0x18001cf7a  lea     rcx, [rbp+1C0h+Src]; Src
0x18001cf81  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x18001cf86  lea     rdx, [rbp+1C0h+Src]
0x18001cf8d  lea     rcx, [rsp+2C0h+var_260]
0x18001cf92  call    ?push_back@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::vector<std::wstring>::push_back(std::wstring const &)
0x18001cf97  cmp     dword ptr [rbx+48h], 0FFFFFFFFh
0x18001cf9b  jz      loc_18001D034
0x18001cfa1  mov     [rbp+1C0h+var_B8], r15
0x18001cfa8  mov     [rbp+1C0h+var_C0], r13
0x18001cfaf  mov     word ptr [rbp+1C0h+Block], r13w
0x18001cfb7  lea     r8d, [r15+0Eh]
0x18001cfbb  lea     rdx, aParameterdescr; "ParameterDescription="
0x18001cfc2  lea     rcx, [rbp+1C0h+Block]; void *
0x18001cfc9  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x18001cfce  nop
0x18001cfcf  mov     edx, [rbx+48h]; uID
0x18001cfd2  lea     rcx, [rbp+1C0h+var_70]; void *
0x18001cfd9  call    ?LoadStringW@CSrmResource@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@I@Z; CSrmResource::LoadStringW(uint)
0x18001cfde  nop
0x18001cfdf  or      r9, 0FFFFFFFFFFFFFFFFh
0x18001cfe3  xor     r8d, r8d
0x18001cfe6  mov     rdx, rax
0x18001cfe9  lea     rcx, [rbp+1C0h+Block]
0x18001cff0  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::append(std::wstring const &,unsigned __int64,unsigned __int64)
0x18001cff5  nop
0x18001cff6  cmp     [rbp+1C0h+var_58], 8
0x18001cffe  jb      short loc_18001D00C
0x18001d000  mov     rcx, [rbp+1C0h+var_70]; Block
0x18001d007  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001d00c  lea     rdx, [rbp+1C0h+Block]
0x18001d013  lea     rcx, [rsp+2C0h+var_260]
0x18001d018  call    ?push_back@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::vector<std::wstring>::push_back(std::wstring const &)
0x18001d01d  nop
0x18001d01e  cmp     [rbp+1C0h+var_B8], 8
0x18001d026  jb      short loc_18001D034
0x18001d028  mov     rcx, [rbp+1C0h+Block]; Block
0x18001d02f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001d034  mov     r15, [rsp+2C0h+var_260+8]
0x18001d039  mov     rbx, [rsp+2C0h+var_260]
0x18001d03e  mov     r8, r15
0x18001d041  sub     r8, rbx
0x18001d044  sar     r8, 3
0x18001d048  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18001d052  imul    r8, rax
0x18001d056  lea     r9, [rsp+2C0h+psa]
0x18001d05b  mov     rdx, r15
0x18001d05e  mov     rcx, rbx
0x18001d061  call    ??$SrmStringRangeToSafeArray@V?$_Vector_const_iterator@V?$_Vector_val@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@std@@@@YAXV?$_Vector_const_iterator@V?$_Vector_val@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@std@@0_KPEAPEAUtagSAFEARRAY@@@Z; SrmStringRangeToSafeArray<std::_Vector_const_iterator<std::_Vector_val<std::wstring>>>(std::_Vector_const_iterator<std::_Vector_val<std::wstring>>,std::_Vector_const_iterator<std::_Vector_val<std::wstring>>,unsigned __int64,tagSAFEARRAY * *)
0x18001d066  mov     r13, [rsp+2C0h+psa]
0x18001d06b  mov     [rsp+2C0h+var_268], r13
0x18001d070  mov     rax, [r12]
0x18001d074  mov     rdx, r13
0x18001d077  mov     rcx, r12
0x18001d07a  mov     rax, [rax+30h]
0x18001d07e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d083  mov     [rbp+1C0h+var_178], eax
0x18001d086  xor     r12d, r12d
0x18001d089  test    eax, eax
0x18001d08b  js      loc_18001D1C4
0x18001d091  mov     [rbp+1C0h+var_178], eax
0x18001d094  cmp     [rbp+1C0h+var_90], 8
0x18001d09c  jb      short loc_18001D0AA
  ... truncated ...
```
