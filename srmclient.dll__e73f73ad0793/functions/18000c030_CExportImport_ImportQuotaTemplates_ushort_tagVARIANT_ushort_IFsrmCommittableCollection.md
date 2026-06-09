# CExportImport::ImportQuotaTemplates(ushort *,tagVARIANT *,ushort *,IFsrmCommittableCollection * *)

- ea: `0x18000c030`
- end: `0x18000c307`
- name: `?ImportQuotaTemplates@CExportImport@@UEAAJPEAGPEAUtagVARIANT@@0PEAPEAUIFsrmCommittableCollection@@@Z`
- size: `727`
- prototype: `int(CExportImport *__hidden this, unsigned __int16 *, struct tagVARIANT *, unsigned __int16 *, struct IFsrmCommittableCollection **)`
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x180006a1c`
- `0x18000b0e8`
- `0x18000c030`
- `0x18000c35c`
- `0x18006fe68`
- `0x18006febc`
- `0x1800700b8`
- `0x180073d04`
- `0x1800b078a`
- `0x1800b07d0`
- `0x1800d5010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18000c18e`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c18e`

## string_xrefs

- `0x18000c08d`: `SRMPATHH`
- `0x18000c22d`: `SRMPATHH`
- `0x18000c278`: `SRMPATHH`
- `0x18000c2d6`: `SRMPATHH`
- `0x18000c073`: `base\fs\fsrm\service\srmclient\exportimport.cpp`
- `0x18000c242`: `NULL file path parameter`
- `0x18000c28d`: `NULL template collection parameter`
- `0x18000c07f`: `CExportImport::ImportQuotaTemplates`
- `0x18000c2eb`: `IFsrmQuotaTemplateManager::ImportTemplates`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall CExportImport::ImportQuotaTemplates(
        CExportImport *this,
        unsigned __int16 *a2,
        struct tagVARIANT *a3,
        unsigned __int16 *a4,
        struct IFsrmCommittableCollection **a5)
{
  CExportImport *v8; // rcx
  const unsigned __int16 *v9; // r8
  CExportImport *v10; // rcx
  void *v11; // rbx
  struct IFsrmCommittableCollection *v12; // rax
  unsigned int v13; // ebx
  __int64 v15; // rax
  __int64 v16; // rax
  unsigned int Hr; // ebx
  __int64 v18; // rax
  struct IFsrmCommittableCollection *v19; // [rsp+40h] [rbp-1B8h] BYREF
  BSTR bstrString; // [rsp+48h] [rbp-1B0h] BYREF
  void *v21; // [rsp+50h] [rbp-1A8h] BYREF
  _QWORD *v22; // [rsp+58h] [rbp-1A0h]
  int v23; // [rsp+60h] [rbp-198h] BYREF
  _com_error *v24; // [rsp+68h] [rbp-190h] BYREF
  const exception *v25; // [rsp+70h] [rbp-188h] BYREF
  _QWORD v26[4]; // [rsp+78h] [rbp-180h] BYREF
  int v27; // [rsp+98h] [rbp-160h]
  _DWORD v28[28]; // [rsp+A0h] [rbp-158h] BYREF
  void **v29; // [rsp+110h] [rbp-E8h] BYREF
  int v30; // [rsp+118h] [rbp-E0h]
  unsigned int v31; // [rsp+13Ch] [rbp-BCh]

  v21 = v26;
  v26[0] = L"base\\fs\\fsrm\\service\\srmclient\\exportimport.cpp";
  v26[1] = L"CExportImport::ImportQuotaTemplates";
  v26[2] = L"SRMPATHH";
  v26[3] = 312;
  v27 = 255;
  v28[24] = 0x1000000;
  memset_0(v28, 0, 0x60u);
  CSrmFunctionTracer::CSrmFunctionTracer((__int64)&v29, (const struct CSrmDebugInfo *)v26, 0);
  try
  {
    v21 = 0;
    v19 = 0;
    bstrString = 0;
    if ( !a2 )
    {
      v22 = v26;
      v15 = CSrmDebugInfo::CSrmDebugInfo(
              (__int64)v26,
              (__int64)L"base\\fs\\fsrm\\service\\srmclient\\exportimport.cpp",
              (__int64)L"SRMPATHH",
              (__int64)L"CExportImport::ImportQuotaTemplates",
              322,
              0);
      CSrmFunctionTracer::Throw(&v29, v15, 2147942487LL, L"NULL file path parameter");
    }
    if ( !a5 )
    {
      v22 = v26;
      v16 = CSrmDebugInfo::CSrmDebugInfo(
              (__int64)v26,
              (__int64)L"base\\fs\\fsrm\\service\\srmclient\\exportimport.cpp",
              (__int64)L"SRMPATHH",
              (__int64)L"CExportImport::ImportQuotaTemplates",
              327,
              0);
      CSrmFunctionTracer::Throw(&v29, v16, 2147942487LL, L"NULL template collection parameter");
    }
    *a5 = 0;
    CExportImport::CreateRemoteManager(
      v8,
      &CLSID_FsrmQuotaTemplateManager,
      v9,
      &GUID_4173ac41_172d_4d52_963c_fdc7e415f717,
      a4,
      &v21);
    CExportImport::ReadXmlFromFile(v10, a2, &bstrString);
    v11 = v21;
    v30 = (*(__int64 (__fastcall **)(void *, BSTR, struct tagVARIANT *, struct IFsrmCommittableCollection **))(*(_QWORD *)v21 + 88LL))(
            v21,
            bstrString,
            a3,
            &v19);
    if ( v30 < 0 )
    {
      Hr = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v29);
      v22 = v26;
      v18 = CSrmDebugInfo::CSrmDebugInfo(
              (__int64)v26,
              (__int64)L"base\\fs\\fsrm\\service\\srmclient\\exportimport.cpp",
              (__int64)L"SRMPATHH",
              (__int64)L"CExportImport::ImportQuotaTemplates",
              345,
              0);
      CSrmFunctionTracer::Throw(&v29, v18, Hr, L"IFsrmQuotaTemplateManager::ImportTemplates");
    }
    v12 = v19;
    v19 = 0;
    *a5 = v12;
    SysFreeString(bstrString);
    if ( v19 )
      ((void (__fastcall *)(struct IFsrmCommittableCollection *))v19->lpVtbl->Release)(v19);
    if ( v11 )
      (*(void (__fastcall **)(void *))(*(_QWORD *)v11 + 16LL))(v11);
  }
  catch ( long v23 )
  {
    CSrmFunctionTracer::HandleHresultException(
      (CSrmFunctionTracer *)&v29,
      v23,
      L"base\\fs\\fsrm\\service\\srmclient\\exportimport.cpp",
      L"SRMPATHH",
      L"CExportImport::ImportQuotaTemplates",
      0x15Fu,
      v31);
  }
  catch ( _com_error *v24 )
  {
    CSrmFunctionTracer::HandleComException(
      (CSrmFunctionTracer *)&v29,
      v24,
      L"base\\fs\\fsrm\\service\\srmclient\\exportimport.cpp",
      L"SRMPATHH",
      L"CExportImport::ImportQuotaTemplates",
      0x15Fu,
      v31);
  }
  catch ( std::bad_alloc )
  {
    CSrmFunctionTracer::HandleStdBadAllocException(
      (CSrmFunctionTracer *)&v29,
      L"base\\fs\\fsrm\\service\\srmclient\\exportimport.cpp",
      L"SRMPATHH",
      L"CExportImport::ImportQuotaTemplates",
      0x15Fu,
      v31);
  }
  catch ( const exception *v25 )
  {
    CSrmFunctionTracer::HandleStdGenericException(
      (CSrmFunctionTracer *)&v29,
      v25,
      L"base\\fs\\fsrm\\service\\srmclient\\exportimport.cpp",
      L"SRMPATHH",
      L"CExportImport::ImportQuotaTemplates",
      0x15Fu,
      v31);
  }
  v13 = v30;
  v29 = &CSrmFunctionTracer::`vftable';
  CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)&v29);
  return v13;
}

```

## disassembly

```asm
0x18000c030  mov     r11, rsp
0x18000c033  mov     [r11+8], rbx
0x18000c037  push    rsi
0x18000c038  push    rdi
0x18000c039  push    r12
0x18000c03b  push    r13
0x18000c03d  push    r14
0x18000c03f  sub     rsp, 1D0h
0x18000c046  mov     rax, cs:__security_cookie
0x18000c04d  xor     rax, rsp
0x18000c050  mov     [rsp+1F8h+var_38], rax
0x18000c058  mov     r14, r9
0x18000c05b  mov     rsi, r8
0x18000c05e  mov     rbx, rdx
0x18000c061  mov     rdi, [rsp+1F8h+arg_20]
0x18000c069  lea     rax, [rsp+1F8h+var_180]
0x18000c06e  mov     [rsp+1F8h+var_1A8], rax
0x18000c073  lea     r12, aBaseFsFsrmServ_0; "base\\fs\\fsrm\\service\\srmclient\\exp"...
0x18000c07a  mov     [rsp+1F8h+var_180], r12
0x18000c07f  lea     r13, aCexportimportI; "CExportImport::ImportQuotaTemplates"
0x18000c086  mov     [r11-178h], r13
0x18000c08d  lea     rax, aSrmpathh; "SRMPATHH"
0x18000c094  mov     [r11-170h], rax
0x18000c09b  mov     qword ptr [r11-168h], 138h
0x18000c0a6  mov     [rsp+1F8h+var_160], 0FFh
0x18000c0b1  mov     [rsp+1F8h+var_F8], 1000000h
0x18000c0bc  xor     edx, edx; Val
0x18000c0be  lea     r8d, [rdx+60h]; Size
0x18000c0c2  lea     rcx, [r11-158h]; void *
0x18000c0c9  call    memset_0
0x18000c0ce  nop
0x18000c0cf  xor     r8d, r8d
0x18000c0d2  lea     rdx, [rsp+1F8h+var_180]
0x18000c0d7  lea     rcx, [rsp+1F8h+var_E8]
0x18000c0df  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x18000c0e4  nop
0x18000c0e5  mov     [rsp+1F8h+var_1A8], 0
0x18000c0ee  mov     [rsp+1F8h+var_1B8], 0
0x18000c0f7  mov     [rsp+1F8h+bstrString], 0
0x18000c100  test    rbx, rbx
0x18000c103  jz      loc_18000C214
0x18000c109  test    rdi, rdi
0x18000c10c  jz      loc_18000C25F
0x18000c112  mov     qword ptr [rdi], 0
0x18000c119  lea     rax, [rsp+1F8h+var_1A8]
0x18000c11e  mov     [rsp+1F8h+var_1D0], rax; void **
0x18000c123  mov     [rsp+1F8h+var_1D8], r14; unsigned __int16 *
0x18000c128  lea     r9, _GUID_4173ac41_172d_4d52_963c_fdc7e415f717; struct _GUID *
0x18000c12f  lea     rdx, CLSID_FsrmQuotaTemplateManager; struct _GUID *
0x18000c136  call    ?CreateRemoteManager@CExportImport@@AEAAXAEBU_GUID@@PEBG0PEAGPEAPEAX@Z; CExportImport::CreateRemoteManager(_GUID const &,ushort const *,_GUID const &,ushort *,void * *)
0x18000c13b  lea     r8, [rsp+1F8h+bstrString]; struct CSrmComBSTR *
0x18000c140  mov     rdx, rbx; unsigned __int16 *
0x18000c143  call    ?ReadXmlFromFile@CExportImport@@AEAAXPEBGAEAVCSrmComBSTR@@@Z; CExportImport::ReadXmlFromFile(ushort const *,CSrmComBSTR &)
0x18000c148  mov     rbx, [rsp+1F8h+var_1A8]
0x18000c14d  mov     rax, [rbx]
0x18000c150  lea     r9, [rsp+1F8h+var_1B8]
0x18000c155  mov     r8, rsi
0x18000c158  mov     rdx, [rsp+1F8h+bstrString]
0x18000c15d  mov     rcx, rbx
0x18000c160  mov     rax, [rax+58h]
0x18000c164  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c169  mov     [rsp+1F8h+var_E0], eax
0x18000c170  test    eax, eax
0x18000c172  js      loc_18000C2AA
0x18000c178  mov     rax, [rsp+1F8h+var_1B8]
0x18000c17d  mov     [rsp+1F8h+var_1B8], 0
0x18000c186  mov     [rdi], rax
0x18000c189  mov     rcx, [rsp+1F8h+bstrString]; bstrString
0x18000c18e  call    cs:__imp_SysFreeString
0x18000c194  nop
0x18000c195  mov     rcx, [rsp+1F8h+var_1B8]
0x18000c19a  test    rcx, rcx
0x18000c19d  jz      short loc_18000C1AC
0x18000c19f  mov     rax, [rcx]
0x18000c1a2  mov     rax, [rax+10h]
0x18000c1a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c1ab  nop
0x18000c1ac  test    rbx, rbx
0x18000c1af  jz      short loc_18000C1C1
0x18000c1b1  mov     rax, [rbx]
0x18000c1b4  mov     rcx, rbx
0x18000c1b7  mov     rax, [rax+10h]
0x18000c1bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c1c0  nop
0x18000c1c1  mov     ebx, [rsp+1F8h+var_E0]
0x18000c1c8  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x18000c1cf  mov     [rsp+1F8h+var_E8], rax
0x18000c1d7  lea     rcx, [rsp+1F8h+var_E8]; this
0x18000c1df  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x18000c1e4  mov     eax, ebx
0x18000c1e6  mov     rcx, [rsp+1F8h+var_38]
0x18000c1ee  xor     rcx, rsp; StackCookie
0x18000c1f1  call    __security_check_cookie
0x18000c1f6  mov     rbx, [rsp+1F8h+arg_0]
0x18000c1fe  add     rsp, 1D0h
0x18000c205  pop     r14
0x18000c207  pop     r13
0x18000c209  pop     r12
0x18000c20b  pop     rdi
0x18000c20c  pop     rsi
0x18000c20d  retn
0x18000c20e  jmp     short loc_18000C1C1
0x18000c210  jmp     short loc_18000C1C1
0x18000c212  jmp     short loc_18000C1C1
0x18000c214  lea     rax, [rsp+1F8h+var_180]
0x18000c219  mov     [rsp+1F8h+var_1A0], rax
0x18000c21e  mov     dword ptr [rsp+1F8h+var_1D0], ebx
0x18000c222  mov     dword ptr [rsp+1F8h+var_1D8], 142h
0x18000c22a  mov     r9, r13
0x18000c22d  lea     r8, aSrmpathh; "SRMPATHH"
0x18000c234  mov     rdx, r12
0x18000c237  lea     rcx, [rsp+1F8h+var_180]
0x18000c23c  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x18000c241  nop
0x18000c242  lea     r9, aNullFilePathPa; "NULL file path parameter"
0x18000c249  mov     r8d, 80070057h
0x18000c24f  mov     rdx, rax
0x18000c252  lea     rcx, [rsp+1F8h+var_E8]
0x18000c25a  call    ?Throw@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@JPEBGZZ; CSrmFunctionTracer::Throw(CSrmDebugInfo,long,ushort const *,...)
0x18000c25f  lea     rax, [rsp+1F8h+var_180]
0x18000c264  mov     [rsp+1F8h+var_1A0], rax
0x18000c269  mov     dword ptr [rsp+1F8h+var_1D0], edi
0x18000c26d  mov     dword ptr [rsp+1F8h+var_1D8], 147h
0x18000c275  mov     r9, r13
0x18000c278  lea     r8, aSrmpathh; "SRMPATHH"
0x18000c27f  mov     rdx, r12
0x18000c282  lea     rcx, [rsp+1F8h+var_180]
0x18000c287  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x18000c28c  nop
0x18000c28d  lea     r9, aNullTemplateCo; "NULL template collection parameter"
0x18000c294  mov     r8d, 80070057h
0x18000c29a  mov     rdx, rax
0x18000c29d  lea     rcx, [rsp+1F8h+var_E8]
0x18000c2a5  call    ?Throw@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@JPEBGZZ; CSrmFunctionTracer::Throw(CSrmDebugInfo,long,ushort const *,...)
0x18000c2aa  lea     rcx, [rsp+1F8h+var_E8]; this
0x18000c2b2  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18000c2b7  mov     ebx, eax
0x18000c2b9  lea     rax, [rsp+1F8h+var_180]
0x18000c2be  mov     [rsp+1F8h+var_1A0], rax
0x18000c2c3  mov     dword ptr [rsp+1F8h+var_1D0], 0
0x18000c2cb  mov     dword ptr [rsp+1F8h+var_1D8], 159h
0x18000c2d3  mov     r9, r13
0x18000c2d6  lea     r8, aSrmpathh; "SRMPATHH"
0x18000c2dd  mov     rdx, r12
0x18000c2e0  lea     rcx, [rsp+1F8h+var_180]
0x18000c2e5  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x18000c2ea  nop
0x18000c2eb  lea     r9, aIfsrmquotatemp_0; "IFsrmQuotaTemplateManager::ImportTempla"...
0x18000c2f2  mov     r8d, ebx
0x18000c2f5  mov     rdx, rax
0x18000c2f8  lea     rcx, [rsp+1F8h+var_E8]
0x18000c300  call    ?Throw@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@JPEBGZZ; CSrmFunctionTracer::Throw(CSrmDebugInfo,long,ushort const *,...)
```
