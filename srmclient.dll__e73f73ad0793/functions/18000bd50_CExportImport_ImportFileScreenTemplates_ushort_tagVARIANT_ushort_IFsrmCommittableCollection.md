# CExportImport::ImportFileScreenTemplates(ushort *,tagVARIANT *,ushort *,IFsrmCommittableCollection * *)

- ea: `0x18000bd50`
- end: `0x18000c027`
- name: `?ImportFileScreenTemplates@CExportImport@@UEAAJPEAGPEAUtagVARIANT@@0PEAPEAUIFsrmCommittableCollection@@@Z`
- size: `727`
- prototype: `int(CExportImport *__hidden this, unsigned __int16 *, struct tagVARIANT *, unsigned __int16 *, struct IFsrmCommittableCollection **)`
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x180006a1c`
- `0x18000b0e8`
- `0x18000bd50`
- `0x18000c35c`
- `0x18006fe68`
- `0x18006febc`
- `0x1800700b8`
- `0x180073d04`
- `0x1800b078a`
- `0x1800b07d0`
- `0x1800d5010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18000beae`
- `OLEAUT32!__imp_SysFreeString` at `0x18000beae`

## string_xrefs

- `0x18000bdad`: `SRMPATHH`
- `0x18000bf4d`: `SRMPATHH`
- `0x18000bf98`: `SRMPATHH`
- `0x18000bff6`: `SRMPATHH`
- `0x18000bd93`: `base\fs\fsrm\service\srmclient\exportimport.cpp`
- `0x18000bf62`: `NULL file path parameter`
- `0x18000bfad`: `NULL template collection parameter`
- `0x18000bd9f`: `CExportImport::ImportFileScreenTemplates`
- `0x18000c00b`: `IFsrmFileScreenTemplateManager::ImportTemplates`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall CExportImport::ImportFileScreenTemplates(
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
  v26[1] = L"CExportImport::ImportFileScreenTemplates";
  v26[2] = L"SRMPATHH";
  v26[3] = 212;
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
              (__int64)L"CExportImport::ImportFileScreenTemplates",
              222,
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
              (__int64)L"CExportImport::ImportFileScreenTemplates",
              227,
              0);
      CSrmFunctionTracer::Throw(&v29, v16, 2147942487LL, L"NULL template collection parameter");
    }
    *a5 = 0;
    CExportImport::CreateRemoteManager(
      v8,
      &CLSID_FsrmFileScreenTemplateManager,
      v9,
      &GUID_cfe36cba_1949_4e74_a14f_f1d580ceaf13,
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
              (__int64)L"CExportImport::ImportFileScreenTemplates",
              247,
              0);
      CSrmFunctionTracer::Throw(&v29, v18, Hr, L"IFsrmFileScreenTemplateManager::ImportTemplates");
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
      L"CExportImport::ImportFileScreenTemplates",
      0xFDu,
      v31);
  }
  catch ( _com_error *v24 )
  {
    CSrmFunctionTracer::HandleComException(
      (CSrmFunctionTracer *)&v29,
      v24,
      L"base\\fs\\fsrm\\service\\srmclient\\exportimport.cpp",
      L"SRMPATHH",
      L"CExportImport::ImportFileScreenTemplates",
      0xFDu,
      v31);
  }
  catch ( std::bad_alloc )
  {
    CSrmFunctionTracer::HandleStdBadAllocException(
      (CSrmFunctionTracer *)&v29,
      L"base\\fs\\fsrm\\service\\srmclient\\exportimport.cpp",
      L"SRMPATHH",
      L"CExportImport::ImportFileScreenTemplates",
      0xFDu,
      v31);
  }
  catch ( const exception *v25 )
  {
    CSrmFunctionTracer::HandleStdGenericException(
      (CSrmFunctionTracer *)&v29,
      v25,
      L"base\\fs\\fsrm\\service\\srmclient\\exportimport.cpp",
      L"SRMPATHH",
      L"CExportImport::ImportFileScreenTemplates",
      0xFDu,
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
0x18000bd50  mov     r11, rsp
0x18000bd53  mov     [r11+8], rbx
0x18000bd57  push    rsi
0x18000bd58  push    rdi
0x18000bd59  push    r12
0x18000bd5b  push    r13
0x18000bd5d  push    r14
0x18000bd5f  sub     rsp, 1D0h
0x18000bd66  mov     rax, cs:__security_cookie
0x18000bd6d  xor     rax, rsp
0x18000bd70  mov     [rsp+1F8h+var_38], rax
0x18000bd78  mov     r14, r9
0x18000bd7b  mov     rsi, r8
0x18000bd7e  mov     rbx, rdx
0x18000bd81  mov     rdi, [rsp+1F8h+arg_20]
0x18000bd89  lea     rax, [rsp+1F8h+var_180]
0x18000bd8e  mov     [rsp+1F8h+var_1A8], rax
0x18000bd93  lea     r12, aBaseFsFsrmServ_0; "base\\fs\\fsrm\\service\\srmclient\\exp"...
0x18000bd9a  mov     [rsp+1F8h+var_180], r12
0x18000bd9f  lea     r13, aCexportimportI_0; "CExportImport::ImportFileScreenTemplate"...
0x18000bda6  mov     [r11-178h], r13
0x18000bdad  lea     rax, aSrmpathh; "SRMPATHH"
0x18000bdb4  mov     [r11-170h], rax
0x18000bdbb  mov     qword ptr [r11-168h], 0D4h
0x18000bdc6  mov     [rsp+1F8h+var_160], 0FFh
0x18000bdd1  mov     [rsp+1F8h+var_F8], 1000000h
0x18000bddc  xor     edx, edx; Val
0x18000bdde  lea     r8d, [rdx+60h]; Size
0x18000bde2  lea     rcx, [r11-158h]; void *
0x18000bde9  call    memset_0
0x18000bdee  nop
0x18000bdef  xor     r8d, r8d
0x18000bdf2  lea     rdx, [rsp+1F8h+var_180]
0x18000bdf7  lea     rcx, [rsp+1F8h+var_E8]
0x18000bdff  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x18000be04  nop
0x18000be05  mov     [rsp+1F8h+var_1A8], 0
0x18000be0e  mov     [rsp+1F8h+var_1B8], 0
0x18000be17  mov     [rsp+1F8h+bstrString], 0
0x18000be20  test    rbx, rbx
0x18000be23  jz      loc_18000BF34
0x18000be29  test    rdi, rdi
0x18000be2c  jz      loc_18000BF7F
0x18000be32  mov     qword ptr [rdi], 0
0x18000be39  lea     rax, [rsp+1F8h+var_1A8]
0x18000be3e  mov     [rsp+1F8h+var_1D0], rax; void **
0x18000be43  mov     [rsp+1F8h+var_1D8], r14; unsigned __int16 *
0x18000be48  lea     r9, _GUID_cfe36cba_1949_4e74_a14f_f1d580ceaf13; struct _GUID *
0x18000be4f  lea     rdx, CLSID_FsrmFileScreenTemplateManager; struct _GUID *
0x18000be56  call    ?CreateRemoteManager@CExportImport@@AEAAXAEBU_GUID@@PEBG0PEAGPEAPEAX@Z; CExportImport::CreateRemoteManager(_GUID const &,ushort const *,_GUID const &,ushort *,void * *)
0x18000be5b  lea     r8, [rsp+1F8h+bstrString]; struct CSrmComBSTR *
0x18000be60  mov     rdx, rbx; unsigned __int16 *
0x18000be63  call    ?ReadXmlFromFile@CExportImport@@AEAAXPEBGAEAVCSrmComBSTR@@@Z; CExportImport::ReadXmlFromFile(ushort const *,CSrmComBSTR &)
0x18000be68  mov     rbx, [rsp+1F8h+var_1A8]
0x18000be6d  mov     rax, [rbx]
0x18000be70  lea     r9, [rsp+1F8h+var_1B8]
0x18000be75  mov     r8, rsi
0x18000be78  mov     rdx, [rsp+1F8h+bstrString]
0x18000be7d  mov     rcx, rbx
0x18000be80  mov     rax, [rax+58h]
0x18000be84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be89  mov     [rsp+1F8h+var_E0], eax
0x18000be90  test    eax, eax
0x18000be92  js      loc_18000BFCA
0x18000be98  mov     rax, [rsp+1F8h+var_1B8]
0x18000be9d  mov     [rsp+1F8h+var_1B8], 0
0x18000bea6  mov     [rdi], rax
0x18000bea9  mov     rcx, [rsp+1F8h+bstrString]; bstrString
0x18000beae  call    cs:__imp_SysFreeString
0x18000beb4  nop
0x18000beb5  mov     rcx, [rsp+1F8h+var_1B8]
0x18000beba  test    rcx, rcx
0x18000bebd  jz      short loc_18000BECC
0x18000bebf  mov     rax, [rcx]
0x18000bec2  mov     rax, [rax+10h]
0x18000bec6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000becb  nop
0x18000becc  test    rbx, rbx
0x18000becf  jz      short loc_18000BEE1
0x18000bed1  mov     rax, [rbx]
0x18000bed4  mov     rcx, rbx
0x18000bed7  mov     rax, [rax+10h]
0x18000bedb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bee0  nop
0x18000bee1  mov     ebx, [rsp+1F8h+var_E0]
0x18000bee8  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x18000beef  mov     [rsp+1F8h+var_E8], rax
0x18000bef7  lea     rcx, [rsp+1F8h+var_E8]; this
0x18000beff  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x18000bf04  mov     eax, ebx
0x18000bf06  mov     rcx, [rsp+1F8h+var_38]
0x18000bf0e  xor     rcx, rsp; StackCookie
0x18000bf11  call    __security_check_cookie
0x18000bf16  mov     rbx, [rsp+1F8h+arg_0]
0x18000bf1e  add     rsp, 1D0h
0x18000bf25  pop     r14
0x18000bf27  pop     r13
0x18000bf29  pop     r12
0x18000bf2b  pop     rdi
0x18000bf2c  pop     rsi
0x18000bf2d  retn
0x18000bf2e  jmp     short loc_18000BEE1
0x18000bf30  jmp     short loc_18000BEE1
0x18000bf32  jmp     short loc_18000BEE1
0x18000bf34  lea     rax, [rsp+1F8h+var_180]
0x18000bf39  mov     [rsp+1F8h+var_1A0], rax
0x18000bf3e  mov     dword ptr [rsp+1F8h+var_1D0], ebx
0x18000bf42  mov     dword ptr [rsp+1F8h+var_1D8], 0DEh
0x18000bf4a  mov     r9, r13
0x18000bf4d  lea     r8, aSrmpathh; "SRMPATHH"
0x18000bf54  mov     rdx, r12
0x18000bf57  lea     rcx, [rsp+1F8h+var_180]
0x18000bf5c  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x18000bf61  nop
0x18000bf62  lea     r9, aNullFilePathPa; "NULL file path parameter"
0x18000bf69  mov     r8d, 80070057h
0x18000bf6f  mov     rdx, rax
0x18000bf72  lea     rcx, [rsp+1F8h+var_E8]
0x18000bf7a  call    ?Throw@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@JPEBGZZ; CSrmFunctionTracer::Throw(CSrmDebugInfo,long,ushort const *,...)
0x18000bf7f  lea     rax, [rsp+1F8h+var_180]
0x18000bf84  mov     [rsp+1F8h+var_1A0], rax
0x18000bf89  mov     dword ptr [rsp+1F8h+var_1D0], edi
0x18000bf8d  mov     dword ptr [rsp+1F8h+var_1D8], 0E3h
0x18000bf95  mov     r9, r13
0x18000bf98  lea     r8, aSrmpathh; "SRMPATHH"
0x18000bf9f  mov     rdx, r12
0x18000bfa2  lea     rcx, [rsp+1F8h+var_180]
0x18000bfa7  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x18000bfac  nop
0x18000bfad  lea     r9, aNullTemplateCo; "NULL template collection parameter"
0x18000bfb4  mov     r8d, 80070057h
0x18000bfba  mov     rdx, rax
0x18000bfbd  lea     rcx, [rsp+1F8h+var_E8]
0x18000bfc5  call    ?Throw@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@JPEBGZZ; CSrmFunctionTracer::Throw(CSrmDebugInfo,long,ushort const *,...)
0x18000bfca  lea     rcx, [rsp+1F8h+var_E8]; this
0x18000bfd2  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18000bfd7  mov     ebx, eax
0x18000bfd9  lea     rax, [rsp+1F8h+var_180]
0x18000bfde  mov     [rsp+1F8h+var_1A0], rax
0x18000bfe3  mov     dword ptr [rsp+1F8h+var_1D0], 0
0x18000bfeb  mov     dword ptr [rsp+1F8h+var_1D8], 0F7h
0x18000bff3  mov     r9, r13
0x18000bff6  lea     r8, aSrmpathh; "SRMPATHH"
0x18000bffd  mov     rdx, r12
0x18000c000  lea     rcx, [rsp+1F8h+var_180]
0x18000c005  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x18000c00a  nop
0x18000c00b  lea     r9, aIfsrmfilescree; "IFsrmFileScreenTemplateManager::ImportT"...
0x18000c012  mov     r8d, ebx
0x18000c015  mov     rdx, rax
0x18000c018  lea     rcx, [rsp+1F8h+var_E8]
0x18000c020  call    ?Throw@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@JPEBGZZ; CSrmFunctionTracer::Throw(CSrmDebugInfo,long,ushort const *,...)
```
