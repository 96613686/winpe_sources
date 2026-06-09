# CExportImport::ImportFileGroups(ushort *,tagVARIANT *,ushort *,IFsrmCommittableCollection * *)

- ea: `0x18000ba70`
- end: `0x18000bd47`
- name: `?ImportFileGroups@CExportImport@@UEAAJPEAGPEAUtagVARIANT@@0PEAPEAUIFsrmCommittableCollection@@@Z`
- size: `727`
- prototype: `__int64 __fastcall(CExportImport *this, unsigned __int16 *, struct tagVARIANT *, unsigned __int16 *, struct IFsrmCommittableCollection **)`
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x180006a1c`
- `0x18000b0e8`
- `0x18000ba70`
- `0x18000c35c`
- `0x18006fe68`
- `0x18006febc`
- `0x1800700b8`
- `0x180073d04`
- `0x1800b078a`
- `0x1800b07d0`
- `0x1800d5010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18000bbce`
- `OLEAUT32!__imp_SysFreeString` at `0x18000bbce`

## string_xrefs

- `0x18000bacd`: `SRMPATHH`
- `0x18000bc6d`: `SRMPATHH`
- `0x18000bcb8`: `SRMPATHH`
- `0x18000bd16`: `SRMPATHH`
- `0x18000bab3`: `base\fs\fsrm\service\srmclient\exportimport.cpp`
- `0x18000bc82`: `NULL file path parameter`
- `0x18000bccd`: `NULL template collection parameter`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CExportImport::ImportFileGroups(
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
  v26[1] = L"CExportImport::ImportFileGroups";
  v26[2] = L"SRMPATHH";
  v26[3] = 112;
  v27 = 255;
  v28[24] = 0x1000000;
  memset_0(v28, 0, 0x60u);
  CSrmFunctionTracer::CSrmFunctionTracer(&v29, v26, 0);
  try
  {
    v21 = 0;
    v19 = 0;
    bstrString = 0;
    if ( !a2 )
    {
      v22 = v26;
      v15 = CSrmDebugInfo::CSrmDebugInfo(
              v26,
              L"base\\fs\\fsrm\\service\\srmclient\\exportimport.cpp",
              L"SRMPATHH",
              L"CExportImport::ImportFileGroups",
              122,
              0);
      CSrmFunctionTracer::Throw(&v29, v15, 2147942487LL, L"NULL file path parameter");
    }
    if ( !a5 )
    {
      v22 = v26;
      v16 = CSrmDebugInfo::CSrmDebugInfo(
              v26,
              L"base\\fs\\fsrm\\service\\srmclient\\exportimport.cpp",
              L"SRMPATHH",
              L"CExportImport::ImportFileGroups",
              127,
              0);
      CSrmFunctionTracer::Throw(&v29, v16, 2147942487LL, L"NULL template collection parameter");
    }
    *a5 = 0;
    CExportImport::CreateRemoteManager(
      v8,
      &CLSID_FsrmFileGroupManager,
      v9,
      &GUID_426677d5_018c_485c_8a51_20b86d00bdc4,
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
              v26,
              L"base\\fs\\fsrm\\service\\srmclient\\exportimport.cpp",
              L"SRMPATHH",
              L"CExportImport::ImportFileGroups",
              147,
              0);
      CSrmFunctionTracer::Throw(&v29, v18, Hr, L"IFsrmFileGroupManager::ImportFileGroups");
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
      L"CExportImport::ImportFileGroups",
      0x99u,
      v31);
  }
  catch ( _com_error *v24 )
  {
    CSrmFunctionTracer::HandleComException(
      (CSrmFunctionTracer *)&v29,
      v24,
      L"base\\fs\\fsrm\\service\\srmclient\\exportimport.cpp",
      L"SRMPATHH",
      L"CExportImport::ImportFileGroups",
      0x99u,
      v31);
  }
  catch ( std::bad_alloc )
  {
    CSrmFunctionTracer::HandleStdBadAllocException(
      (CSrmFunctionTracer *)&v29,
      L"base\\fs\\fsrm\\service\\srmclient\\exportimport.cpp",
      L"SRMPATHH",
      L"CExportImport::ImportFileGroups",
      0x99u,
      v31);
  }
  catch ( const exception *v25 )
  {
    CSrmFunctionTracer::HandleStdGenericException(
      (CSrmFunctionTracer *)&v29,
      v25,
      L"base\\fs\\fsrm\\service\\srmclient\\exportimport.cpp",
      L"SRMPATHH",
      L"CExportImport::ImportFileGroups",
      0x99u,
      v31);
  }
  v21 = 0;
  v19 = 0;
  bstrString = 0;
  if ( !a2 )
  {
    v22 = v26;
    v15 = CSrmDebugInfo::CSrmDebugInfo(
            v26,
            L"base\\fs\\fsrm\\service\\srmclient\\exportimport.cpp",
            L"SRMPATHH",
            L"CExportImport::ImportFileGroups",
            122,
            0);
    CSrmFunctionTracer::Throw(&v29, v15, 2147942487LL, L"NULL file path parameter");
  }
}

```

## disassembly

```asm
0x18000ba70  mov     r11, rsp
0x18000ba73  mov     [r11+8], rbx
0x18000ba77  push    rsi
0x18000ba78  push    rdi
0x18000ba79  push    r12
0x18000ba7b  push    r13
0x18000ba7d  push    r14
0x18000ba7f  sub     rsp, 1D0h
0x18000ba86  mov     rax, cs:__security_cookie
0x18000ba8d  xor     rax, rsp
0x18000ba90  mov     [rsp+1F8h+var_38], rax
0x18000ba98  mov     r14, r9
0x18000ba9b  mov     rsi, r8
0x18000ba9e  mov     rbx, rdx
0x18000baa1  mov     rdi, [rsp+1F8h+arg_20]
0x18000baa9  lea     rax, [rsp+1F8h+var_180]
0x18000baae  mov     [rsp+1F8h+var_1A8], rax
0x18000bab3  lea     r12, aBaseFsFsrmServ_0; "base\\fs\\fsrm\\service\\srmclient\\exp"...
0x18000baba  mov     [rsp+1F8h+var_180], r12
0x18000babf  lea     r13, aCexportimportI_1; "CExportImport::ImportFileGroups"
0x18000bac6  mov     [r11-178h], r13
0x18000bacd  lea     rax, aSrmpathh; "SRMPATHH"
0x18000bad4  mov     [r11-170h], rax
0x18000badb  mov     qword ptr [r11-168h], 70h ; 'p'
0x18000bae6  mov     [rsp+1F8h+var_160], 0FFh
0x18000baf1  mov     [rsp+1F8h+var_F8], 1000000h
0x18000bafc  xor     edx, edx; Val
0x18000bafe  lea     r8d, [rdx+60h]; Size
0x18000bb02  lea     rcx, [r11-158h]; void *
0x18000bb09  call    memset_0
0x18000bb0e  nop
0x18000bb0f  xor     r8d, r8d
0x18000bb12  lea     rdx, [rsp+1F8h+var_180]
0x18000bb17  lea     rcx, [rsp+1F8h+var_E8]
0x18000bb1f  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x18000bb24  nop
0x18000bb25  mov     [rsp+1F8h+var_1A8], 0
0x18000bb2e  mov     [rsp+1F8h+var_1B8], 0
0x18000bb37  mov     [rsp+1F8h+bstrString], 0
0x18000bb40  test    rbx, rbx
0x18000bb43  jz      loc_18000BC54
0x18000bb49  test    rdi, rdi
0x18000bb4c  jz      loc_18000BC9F
0x18000bb52  mov     qword ptr [rdi], 0
0x18000bb59  lea     rax, [rsp+1F8h+var_1A8]
0x18000bb5e  mov     [rsp+1F8h+var_1D0], rax; void **
0x18000bb63  mov     [rsp+1F8h+var_1D8], r14; unsigned __int16 *
0x18000bb68  lea     r9, _GUID_426677d5_018c_485c_8a51_20b86d00bdc4; struct _GUID *
0x18000bb6f  lea     rdx, CLSID_FsrmFileGroupManager; struct _GUID *
0x18000bb76  call    ?CreateRemoteManager@CExportImport@@AEAAXAEBU_GUID@@PEBG0PEAGPEAPEAX@Z; CExportImport::CreateRemoteManager(_GUID const &,ushort const *,_GUID const &,ushort *,void * *)
0x18000bb7b  lea     r8, [rsp+1F8h+bstrString]; struct CSrmComBSTR *
0x18000bb80  mov     rdx, rbx; unsigned __int16 *
0x18000bb83  call    ?ReadXmlFromFile@CExportImport@@AEAAXPEBGAEAVCSrmComBSTR@@@Z; CExportImport::ReadXmlFromFile(ushort const *,CSrmComBSTR &)
0x18000bb88  mov     rbx, [rsp+1F8h+var_1A8]
0x18000bb8d  mov     rax, [rbx]
0x18000bb90  lea     r9, [rsp+1F8h+var_1B8]
0x18000bb95  mov     r8, rsi
0x18000bb98  mov     rdx, [rsp+1F8h+bstrString]
0x18000bb9d  mov     rcx, rbx
0x18000bba0  mov     rax, [rax+58h]
0x18000bba4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bba9  mov     [rsp+1F8h+var_E0], eax
0x18000bbb0  test    eax, eax
0x18000bbb2  js      loc_18000BCEA
0x18000bbb8  mov     rax, [rsp+1F8h+var_1B8]
0x18000bbbd  mov     [rsp+1F8h+var_1B8], 0
0x18000bbc6  mov     [rdi], rax
0x18000bbc9  mov     rcx, [rsp+1F8h+bstrString]; bstrString
0x18000bbce  call    cs:__imp_SysFreeString
0x18000bbd4  nop
0x18000bbd5  mov     rcx, [rsp+1F8h+var_1B8]
0x18000bbda  test    rcx, rcx
0x18000bbdd  jz      short loc_18000BBEC
0x18000bbdf  mov     rax, [rcx]
0x18000bbe2  mov     rax, [rax+10h]
0x18000bbe6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bbeb  nop
0x18000bbec  test    rbx, rbx
0x18000bbef  jz      short loc_18000BC01
0x18000bbf1  mov     rax, [rbx]
0x18000bbf4  mov     rcx, rbx
0x18000bbf7  mov     rax, [rax+10h]
0x18000bbfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bc00  nop
0x18000bc01  mov     ebx, [rsp+1F8h+var_E0]
0x18000bc08  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x18000bc0f  mov     [rsp+1F8h+var_E8], rax
0x18000bc17  lea     rcx, [rsp+1F8h+var_E8]; this
0x18000bc1f  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x18000bc24  mov     eax, ebx
0x18000bc26  mov     rcx, [rsp+1F8h+var_38]
0x18000bc2e  xor     rcx, rsp; StackCookie
0x18000bc31  call    __security_check_cookie
0x18000bc36  mov     rbx, [rsp+1F8h+arg_0]
0x18000bc3e  add     rsp, 1D0h
0x18000bc45  pop     r14
0x18000bc47  pop     r13
0x18000bc49  pop     r12
0x18000bc4b  pop     rdi
0x18000bc4c  pop     rsi
0x18000bc4d  retn
0x18000bc4e  jmp     short loc_18000BC01
0x18000bc50  jmp     short loc_18000BC01
0x18000bc52  jmp     short loc_18000BC01
0x18000bc54  lea     rax, [rsp+1F8h+var_180]
0x18000bc59  mov     [rsp+1F8h+var_1A0], rax
0x18000bc5e  mov     dword ptr [rsp+1F8h+var_1D0], ebx
0x18000bc62  mov     dword ptr [rsp+1F8h+var_1D8], 7Ah ; 'z'
0x18000bc6a  mov     r9, r13
0x18000bc6d  lea     r8, aSrmpathh; "SRMPATHH"
0x18000bc74  mov     rdx, r12
0x18000bc77  lea     rcx, [rsp+1F8h+var_180]
0x18000bc7c  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x18000bc81  nop
0x18000bc82  lea     r9, aNullFilePathPa; "NULL file path parameter"
0x18000bc89  mov     r8d, 80070057h
0x18000bc8f  mov     rdx, rax
0x18000bc92  lea     rcx, [rsp+1F8h+var_E8]
0x18000bc9a  call    ?Throw@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@JPEBGZZ; CSrmFunctionTracer::Throw(CSrmDebugInfo,long,ushort const *,...)
0x18000bc9f  lea     rax, [rsp+1F8h+var_180]
0x18000bca4  mov     [rsp+1F8h+var_1A0], rax
0x18000bca9  mov     dword ptr [rsp+1F8h+var_1D0], edi
0x18000bcad  mov     dword ptr [rsp+1F8h+var_1D8], 7Fh
0x18000bcb5  mov     r9, r13
0x18000bcb8  lea     r8, aSrmpathh; "SRMPATHH"
0x18000bcbf  mov     rdx, r12
0x18000bcc2  lea     rcx, [rsp+1F8h+var_180]
0x18000bcc7  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x18000bccc  nop
0x18000bccd  lea     r9, aNullTemplateCo; "NULL template collection parameter"
0x18000bcd4  mov     r8d, 80070057h
0x18000bcda  mov     rdx, rax
0x18000bcdd  lea     rcx, [rsp+1F8h+var_E8]
0x18000bce5  call    ?Throw@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@JPEBGZZ; CSrmFunctionTracer::Throw(CSrmDebugInfo,long,ushort const *,...)
0x18000bcea  lea     rcx, [rsp+1F8h+var_E8]; this
0x18000bcf2  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18000bcf7  mov     ebx, eax
0x18000bcf9  lea     rax, [rsp+1F8h+var_180]
0x18000bcfe  mov     [rsp+1F8h+var_1A0], rax
0x18000bd03  mov     dword ptr [rsp+1F8h+var_1D0], 0
0x18000bd0b  mov     dword ptr [rsp+1F8h+var_1D8], 93h
0x18000bd13  mov     r9, r13
0x18000bd16  lea     r8, aSrmpathh; "SRMPATHH"
0x18000bd1d  mov     rdx, r12
0x18000bd20  lea     rcx, [rsp+1F8h+var_180]
0x18000bd25  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x18000bd2a  nop
0x18000bd2b  lea     r9, aIfsrmfilegroup; "IFsrmFileGroupManager::ImportFileGroups"
0x18000bd32  mov     r8d, ebx
0x18000bd35  mov     rdx, rax
0x18000bd38  lea     rcx, [rsp+1F8h+var_E8]
0x18000bd40  call    ?Throw@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@JPEBGZZ; CSrmFunctionTracer::Throw(CSrmDebugInfo,long,ushort const *,...)
```
