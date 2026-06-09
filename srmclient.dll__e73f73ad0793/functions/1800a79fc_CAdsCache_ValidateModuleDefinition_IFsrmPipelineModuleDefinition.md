# CAdsCache::ValidateModuleDefinition(IFsrmPipelineModuleDefinition *)

- ea: `0x1800a79fc`
- end: `0x1800a7e66`
- name: `?ValidateModuleDefinition@CAdsCache@@AEAAXPEAUIFsrmPipelineModuleDefinition@@@Z`
- size: `1130`
- prototype: `void __fastcall(CAdsCache *__hidden this, struct IFsrmPipelineModuleDefinition *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800a6f90`

## callees

- `0x180006a1c`
- `0x18000ac44`
- `0x18000f014`
- `0x18006fe68`
- `0x18006febc`
- `0x1800700b8`
- `0x180073d04`
- `0x1800744e8`
- `0x1800a79fc`
- `0x1800b0766`
- `0x1800b078a`
- `0x1800b07d0`
- `0x1800d5010`

## import_xrefs

- `ole32!CLSIDFromString` at `0x1800a7adb`
- `ole32!CLSIDFromString` at `0x1800a7adb`
- `OLEAUT32!__imp_SysFreeString` at `0x1800a7bb1`
- `OLEAUT32!__imp_SysFreeString` at `0x1800a7bb1`

## string_xrefs

- `0x1800a7a3c`: `base\fs\fsrm\service\moduleimpl\adscache.cpp`
- `0x1800a7a48`: `CAdsCache::ValidateModuleDefinition`
- `0x1800a7ce1`: `Module definition has the wrong CLSID: %s`
- `0x1800a7c8d`: `IFsrmPipelineModuleDefinition::get_ModuleClsid`
- `0x1800a7c40`: `CLSIDFromString(%s) failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void __fastcall CAdsCache::ValidateModuleDefinition(CAdsCache *this, struct IFsrmPipelineModuleDefinition *a2)
{
  int v3; // edi
  int v4; // ebx
  unsigned __int16 *Buffer; // rdi
  unsigned int v6; // ebx
  __int64 v7; // rax
  unsigned int Hr; // ebx
  __int64 v9; // rax
  unsigned __int16 *v10; // rbx
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  unsigned int v14; // ebx
  __int64 v15; // rax
  __int64 v16; // rax
  unsigned int v17; // ebx
  __int64 v18; // rax
  __int64 v19; // [rsp+20h] [rbp-E0h]
  __int64 v20; // [rsp+20h] [rbp-E0h]
  int v21; // [rsp+48h] [rbp-B8h] BYREF
  int v22; // [rsp+4Ch] [rbp-B4h] BYREF
  LPCOLESTR lpsz; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v24; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v25[3]; // [rsp+60h] [rbp-A0h] BYREF
  int v26; // [rsp+78h] [rbp-88h]
  int v27; // [rsp+7Ch] [rbp-84h]
  int v28; // [rsp+80h] [rbp-80h]
  _BYTE v29[96]; // [rsp+88h] [rbp-78h] BYREF
  int v30; // [rsp+E8h] [rbp-18h]
  GUID pclsid; // [rsp+F0h] [rbp-10h] BYREF
  void **v32; // [rsp+100h] [rbp+0h] BYREF
  HRESULT v33; // [rsp+108h] [rbp+8h]

  v25[0] = L"base\\fs\\fsrm\\service\\moduleimpl\\adscache.cpp";
  v25[1] = L"CAdsCache::ValidateModuleDefinition";
  v25[2] = L"ADSCACHC";
  v26 = 306;
  v27 = 22;
  v28 = 255;
  v30 = 0x1000000;
  memset_0(v29, 0, sizeof(v29));
  CSrmFunctionTracer::CSrmFunctionTracer((__int64)&v32, (const struct CSrmDebugInfo *)v25, 0);
  lpsz = 0;
  pclsid = 0;
  v33 = ((__int64 (__fastcall *)(struct IFsrmPipelineModuleDefinition *, LPCOLESTR *))a2->lpVtbl->get_ModuleClsid)(
          a2,
          &lpsz);
  if ( v33 < 0 )
  {
    Hr = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v32);
    v9 = CSrmDebugInfo::CSrmDebugInfo(
           (__int64)v25,
           (__int64)L"base\\fs\\fsrm\\service\\moduleimpl\\adscache.cpp",
           (__int64)L"ADSCACHC",
           (__int64)L"CAdsCache::ValidateModuleDefinition",
           316,
           22);
    CSrmFunctionTracer::Throw(&v32, v9, Hr, L"IFsrmPipelineModuleDefinition::get_ModuleClsid");
  }
  v33 = CLSIDFromString(lpsz, &pclsid);
  if ( v33 < 0 )
  {
    Buffer = CSrmOutputBuffer::GetBuffer((CSrmOutputBuffer *)&lpsz);
    v6 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v32);
    v7 = CSrmDebugInfo::CSrmDebugInfo(
           (__int64)v25,
           (__int64)L"base\\fs\\fsrm\\service\\moduleimpl\\adscache.cpp",
           (__int64)L"ADSCACHC",
           (__int64)L"CAdsCache::ValidateModuleDefinition",
           322,
           22);
    CSrmFunctionTracer::Throw(&v32, v7, v6, L"CLSIDFromString(%s) failed", Buffer);
  }
  if ( memcmp_0(&pclsid, &CLSID_FsrmAdsCacheModule, 0x10u) )
  {
    v10 = CSrmOutputBuffer::GetBuffer((CSrmOutputBuffer *)&lpsz);
    v11 = CSrmDebugInfo::CSrmDebugInfo(
            (__int64)v25,
            (__int64)L"base\\fs\\fsrm\\service\\moduleimpl\\adscache.cpp",
            (__int64)L"ADSCACHC",
            (__int64)L"CAdsCache::ValidateModuleDefinition",
            327,
            22);
    CSrmFunctionTracer::Throw(&v32, v11, 2147942487LL, L"Module definition has the wrong CLSID: %s", v10);
  }
  v21 = 0;
  v33 = ((__int64 (__fastcall *)(struct IFsrmPipelineModuleDefinition *, int *))a2->lpVtbl->get_ModuleType)(a2, &v21);
  if ( v33 < 0 )
  {
    v17 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v32);
    v18 = CSrmDebugInfo::CSrmDebugInfo(
            (__int64)v25,
            (__int64)L"base\\fs\\fsrm\\service\\moduleimpl\\adscache.cpp",
            (__int64)L"ADSCACHC",
            (__int64)L"CAdsCache::ValidateModuleDefinition",
            337,
            22);
    CSrmFunctionTracer::Throw(&v32, v18, v17, L"IFsrmPipelineModuleDefinition::get_ModuleType");
  }
  v3 = v21;
  if ( v21 != 1 )
  {
    v12 = CSrmDebugInfo::CSrmDebugInfo(
            (__int64)v25,
            (__int64)L"base\\fs\\fsrm\\service\\moduleimpl\\adscache.cpp",
            (__int64)L"ADSCACHC",
            (__int64)L"CAdsCache::ValidateModuleDefinition",
            342,
            22);
    LODWORD(v19) = v3;
    CSrmFunctionTracer::Throw(&v32, v12, 2147942487LL, L"Module definition has the wrong type: %d", v19);
  }
  v24 = 0;
  v33 = ((__int64 (__fastcall *)(struct IFsrmPipelineModuleDefinition *, GUID *, __int64 *))a2->lpVtbl->QueryInterface)(
          a2,
          &GUID_15a81350_497d_4aba_80e9_d4dbcc5521fe,
          &v24);
  if ( v33 < 0 )
  {
    v16 = CSrmDebugInfo::CSrmDebugInfo(
            (__int64)v25,
            (__int64)L"base\\fs\\fsrm\\service\\moduleimpl\\adscache.cpp",
            (__int64)L"ADSCACHC",
            (__int64)L"CAdsCache::ValidateModuleDefinition",
            352,
            22);
    CSrmFunctionTracer::TranslateComError(
      &v32,
      v16,
      L"QueryInterface IFsrmStorageModuleDefinition from IFsrmPipelineModuleDefinition");
  }
  v22 = 0;
  v33 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v24 + 264LL))(v24, &v22);
  if ( v33 < 0 )
  {
    v14 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v32);
    v15 = CSrmDebugInfo::CSrmDebugInfo(
            (__int64)v25,
            (__int64)L"base\\fs\\fsrm\\service\\moduleimpl\\adscache.cpp",
            (__int64)L"ADSCACHC",
            (__int64)L"CAdsCache::ValidateModuleDefinition",
            362,
            22);
    CSrmFunctionTracer::Throw(&v32, v15, v14, L"IFsrmStorageModuleDefinition::get_StorageType");
  }
  v4 = v22;
  if ( v22 != v3 )
  {
    v13 = CSrmDebugInfo::CSrmDebugInfo(
            (__int64)v25,
            (__int64)L"base\\fs\\fsrm\\service\\moduleimpl\\adscache.cpp",
            (__int64)L"ADSCACHC",
            (__int64)L"CAdsCache::ValidateModuleDefinition",
            367,
            22);
    LODWORD(v20) = v4;
    CSrmFunctionTracer::Throw(&v32, v13, 2147942487LL, L"Module definition has the wrong storage type: %d", v20);
  }
  ATL::CComPtrBase<IFsrmPropertyDefinition2>::~CComPtrBase<IFsrmPropertyDefinition2>(&v24);
  SysFreeString((BSTR)lpsz);
  v32 = &CSrmFunctionTracer::`vftable';
  CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)&v32);
}

```

## disassembly

```asm
0x1800a79fc  mov     [rsp-8+arg_0], rbx
0x1800a7a01  mov     [rsp-8+arg_10], rdi
0x1800a7a06  push    rbp
0x1800a7a07  push    r12
0x1800a7a09  push    r13
0x1800a7a0b  push    r14
0x1800a7a0d  push    r15
0x1800a7a0f  lea     rbp, [rsp-0C0h]
0x1800a7a17  sub     rsp, 1C0h
0x1800a7a1e  mov     rax, cs:__security_cookie
0x1800a7a25  xor     rax, rsp
0x1800a7a28  mov     [rbp+0E0h+var_30], rax
0x1800a7a2f  mov     rbx, rdx
0x1800a7a32  lea     rax, [rsp+1E0h+var_180]
0x1800a7a37  mov     [rsp+1E0h+var_1A0], rax
0x1800a7a3c  lea     r14, aBaseFsFsrmServ_16; "base\\fs\\fsrm\\service\\moduleimpl\\ad"...
0x1800a7a43  mov     [rsp+1E0h+var_180], r14
0x1800a7a48  lea     r15, aCadscacheValid; "CAdsCache::ValidateModuleDefinition"
0x1800a7a4f  mov     [rsp+1E0h+var_178], r15
0x1800a7a54  lea     r12, aAdscachc; "ADSCACHC"
0x1800a7a5b  mov     [rsp+1E0h+var_170], r12
0x1800a7a60  mov     [rsp+1E0h+var_168], 132h
0x1800a7a68  mov     r13d, 16h
0x1800a7a6e  mov     [rsp+1E0h+var_164], r13d
0x1800a7a73  mov     [rbp+0E0h+var_160], 0FFh
0x1800a7a7a  mov     [rbp+0E0h+var_F8], 1000000h
0x1800a7a81  xor     edx, edx; Val
0x1800a7a83  lea     r8d, [r13+4Ah]; Size
0x1800a7a87  lea     rcx, [rbp+0E0h+var_158]; void *
0x1800a7a8b  call    memset_0
0x1800a7a90  nop
0x1800a7a91  xor     r8d, r8d
0x1800a7a94  lea     rdx, [rsp+1E0h+var_180]
0x1800a7a99  lea     rcx, [rbp+0E0h+var_E0]
0x1800a7a9d  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x1800a7aa2  nop
0x1800a7aa3  mov     [rsp+1E0h+lpsz], 0
0x1800a7aac  xorps   xmm0, xmm0
0x1800a7aaf  movups  xmmword ptr [rbp+0E0h+pclsid.Data1], xmm0
0x1800a7ab3  mov     rax, [rbx]
0x1800a7ab6  lea     rdx, [rsp+1E0h+lpsz]
0x1800a7abb  mov     rcx, rbx
0x1800a7abe  mov     rax, [rax+60h]
0x1800a7ac2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a7ac7  mov     [rbp+0E0h+var_D8], eax
0x1800a7aca  test    eax, eax
0x1800a7acc  js      loc_1800A7C57
0x1800a7ad2  lea     rdx, [rbp+0E0h+pclsid]; pclsid
0x1800a7ad6  mov     rcx, [rsp+1E0h+lpsz]; lpsz
0x1800a7adb  call    cs:__imp_CLSIDFromString
0x1800a7ae1  mov     [rbp+0E0h+var_D8], eax
0x1800a7ae4  test    eax, eax
0x1800a7ae6  js      loc_1800A7BF8
0x1800a7aec  lea     r8d, [r13-6]; Size
0x1800a7af0  lea     rdx, CLSID_FsrmAdsCacheModule; Buf2
0x1800a7af7  lea     rcx, [rbp+0E0h+pclsid]; Buf1
0x1800a7afb  call    memcmp_0
0x1800a7b00  test    eax, eax
0x1800a7b02  jnz     loc_1800A7CA4
0x1800a7b08  mov     [rsp+1E0h+var_198], eax
0x1800a7b0c  mov     rax, [rbx]
0x1800a7b0f  lea     rdx, [rsp+1E0h+var_198]
0x1800a7b14  mov     rcx, rbx
0x1800a7b17  mov     rax, [rax+0A0h]
0x1800a7b1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a7b23  mov     [rbp+0E0h+var_D8], eax
0x1800a7b26  test    eax, eax
0x1800a7b28  js      loc_1800A7E19
0x1800a7b2e  mov     edi, [rsp+1E0h+var_198]
0x1800a7b32  cmp     edi, 1
0x1800a7b35  jnz     loc_1800A7CFB
0x1800a7b3b  mov     [rsp+1E0h+var_188], 0
0x1800a7b44  mov     rax, [rbx]
0x1800a7b47  lea     r8, [rsp+1E0h+var_188]
0x1800a7b4c  lea     rdx, _GUID_15a81350_497d_4aba_80e9_d4dbcc5521fe
0x1800a7b53  mov     rcx, rbx
0x1800a7b56  mov     rax, [rax]
0x1800a7b59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a7b5e  mov     [rbp+0E0h+var_D8], eax
0x1800a7b61  test    eax, eax
0x1800a7b63  js      loc_1800A7DDA
0x1800a7b69  mov     [rsp+1E0h+var_194], 0
0x1800a7b71  mov     rcx, [rsp+1E0h+var_188]
0x1800a7b76  mov     rax, [rcx]
0x1800a7b79  lea     rdx, [rsp+1E0h+var_194]
0x1800a7b7e  mov     rax, [rax+108h]
0x1800a7b85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a7b8a  mov     [rbp+0E0h+var_D8], eax
0x1800a7b8d  test    eax, eax
0x1800a7b8f  js      loc_1800A7D8D
0x1800a7b95  mov     ebx, [rsp+1E0h+var_194]
0x1800a7b99  cmp     ebx, edi
0x1800a7b9b  jnz     loc_1800A7D44
0x1800a7ba1  lea     rcx, [rsp+1E0h+var_188]
0x1800a7ba6  call    ??1?$CComPtrBase@UIFsrmPropertyDefinition2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IFsrmPropertyDefinition2>::~CComPtrBase<IFsrmPropertyDefinition2>(void)
0x1800a7bab  nop
0x1800a7bac  mov     rcx, [rsp+1E0h+lpsz]; bstrString
0x1800a7bb1  call    cs:__imp_SysFreeString
0x1800a7bb7  nop
0x1800a7bb8  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x1800a7bbf  mov     [rbp+0E0h+var_E0], rax
0x1800a7bc3  lea     rcx, [rbp+0E0h+var_E0]; this
0x1800a7bc7  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x1800a7bcc  mov     rcx, [rbp+0E0h+var_30]
0x1800a7bd3  xor     rcx, rsp; StackCookie
0x1800a7bd6  call    __security_check_cookie
0x1800a7bdb  lea     r11, [rsp+1E0h+var_20]
0x1800a7be3  mov     rbx, [r11+30h]
0x1800a7be7  mov     rdi, [r11+40h]
0x1800a7beb  mov     rsp, r11
0x1800a7bee  pop     r15
0x1800a7bf0  pop     r14
0x1800a7bf2  pop     r13
0x1800a7bf4  pop     r12
0x1800a7bf6  pop     rbp
0x1800a7bf7  retn
0x1800a7bf8  lea     rcx, [rsp+1E0h+lpsz]; this
0x1800a7bfd  call    ?GetBuffer@CSrmOutputBuffer@@QEAAPEAGXZ; CSrmOutputBuffer::GetBuffer(void)
0x1800a7c02  mov     rdi, rax
0x1800a7c05  lea     rcx, [rbp+0E0h+var_E0]; this
0x1800a7c09  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x1800a7c0e  mov     ebx, eax
0x1800a7c10  lea     rax, [rsp+1E0h+var_180]
0x1800a7c15  mov     [rsp+1E0h+var_1A0], rax
0x1800a7c1a  mov     [rsp+1E0h+var_1B8], r13d
0x1800a7c1f  mov     dword ptr [rsp+1E0h+var_1C0], 142h
0x1800a7c27  mov     r9, r15
0x1800a7c2a  mov     r8, r12
0x1800a7c2d  mov     rdx, r14
0x1800a7c30  lea     rcx, [rsp+1E0h+var_180]
0x1800a7c35  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x1800a7c3a  nop
0x1800a7c3b  mov     [rsp+1E0h+var_1C0], rdi
0x1800a7c40  lea     r9, aClsidfromstrin; "CLSIDFromString(%s) failed"
0x1800a7c47  mov     r8d, ebx
0x1800a7c4a  mov     rdx, rax
0x1800a7c4d  lea     rcx, [rbp+0E0h+var_E0]
0x1800a7c51  call    ?Throw@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@JPEBGZZ; CSrmFunctionTracer::Throw(CSrmDebugInfo,long,ushort const *,...)
0x1800a7c57  lea     rcx, [rbp+0E0h+var_E0]; this
0x1800a7c5b  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x1800a7c60  mov     ebx, eax
0x1800a7c62  lea     rax, [rsp+1E0h+var_180]
0x1800a7c67  mov     [rsp+1E0h+var_1A0], rax
0x1800a7c6c  mov     [rsp+1E0h+var_1B8], r13d
0x1800a7c71  mov     dword ptr [rsp+1E0h+var_1C0], 13Ch
0x1800a7c79  mov     r9, r15
0x1800a7c7c  mov     r8, r12
0x1800a7c7f  mov     rdx, r14
0x1800a7c82  lea     rcx, [rsp+1E0h+var_180]
0x1800a7c87  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x1800a7c8c  nop
0x1800a7c8d  lea     r9, aIfsrmpipelinem_0; "IFsrmPipelineModuleDefinition::get_Modu"...
0x1800a7c94  mov     r8d, ebx
0x1800a7c97  mov     rdx, rax
0x1800a7c9a  lea     rcx, [rbp+0E0h+var_E0]
0x1800a7c9e  call    ?Throw@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@JPEBGZZ; CSrmFunctionTracer::Throw(CSrmDebugInfo,long,ushort const *,...)
0x1800a7ca4  lea     rcx, [rsp+1E0h+lpsz]; this
0x1800a7ca9  call    ?GetBuffer@CSrmOutputBuffer@@QEAAPEAGXZ; CSrmOutputBuffer::GetBuffer(void)
0x1800a7cae  mov     rbx, rax
0x1800a7cb1  lea     rax, [rsp+1E0h+var_180]
0x1800a7cb6  mov     [rsp+1E0h+var_1A0], rax
0x1800a7cbb  mov     [rsp+1E0h+var_1B8], r13d
0x1800a7cc0  mov     dword ptr [rsp+1E0h+var_1C0], 147h
0x1800a7cc8  mov     r9, r15
0x1800a7ccb  mov     r8, r12
0x1800a7cce  mov     rdx, r14
0x1800a7cd1  lea     rcx, [rsp+1E0h+var_180]
0x1800a7cd6  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x1800a7cdb  nop
0x1800a7cdc  mov     [rsp+1E0h+var_1C0], rbx
0x1800a7ce1  lea     r9, aModuleDefiniti_0; "Module definition has the wrong CLSID: "...
0x1800a7ce8  mov     r8d, 80070057h
0x1800a7cee  mov     rdx, rax
0x1800a7cf1  lea     rcx, [rbp+0E0h+var_E0]
0x1800a7cf5  call    ?Throw@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@JPEBGZZ; CSrmFunctionTracer::Throw(CSrmDebugInfo,long,ushort const *,...)
0x1800a7cfb  lea     rax, [rsp+1E0h+var_180]
0x1800a7d00  mov     [rsp+1E0h+var_1A0], rax
0x1800a7d05  mov     [rsp+1E0h+var_1B8], r13d
0x1800a7d0a  mov     dword ptr [rsp+1E0h+var_1C0], 156h
0x1800a7d12  mov     r9, r15
0x1800a7d15  mov     r8, r12
0x1800a7d18  mov     rdx, r14
0x1800a7d1b  lea     rcx, [rsp+1E0h+var_180]
0x1800a7d20  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x1800a7d25  nop
0x1800a7d26  mov     dword ptr [rsp+1E0h+var_1C0], edi
0x1800a7d2a  lea     r9, aModuleDefiniti_1; "Module definition has the wrong type: %"...
0x1800a7d31  mov     r8d, 80070057h
0x1800a7d37  mov     rdx, rax
0x1800a7d3a  lea     rcx, [rbp+0E0h+var_E0]
0x1800a7d3e  call    ?Throw@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@JPEBGZZ; CSrmFunctionTracer::Throw(CSrmDebugInfo,long,ushort const *,...)
0x1800a7d44  lea     rax, [rsp+1E0h+var_180]
0x1800a7d49  mov     [rsp+1E0h+var_1A0], rax
0x1800a7d4e  mov     [rsp+1E0h+var_1B8], r13d
0x1800a7d53  mov     dword ptr [rsp+1E0h+var_1C0], 16Fh
0x1800a7d5b  mov     r9, r15
0x1800a7d5e  mov     r8, r12
0x1800a7d61  mov     rdx, r14
0x1800a7d64  lea     rcx, [rsp+1E0h+var_180]
0x1800a7d69  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x1800a7d6e  nop
0x1800a7d6f  mov     dword ptr [rsp+1E0h+var_1C0], ebx
0x1800a7d73  lea     r9, aModuleDefiniti; "Module definition has the wrong storage"...
0x1800a7d7a  mov     r8d, 80070057h
0x1800a7d80  mov     rdx, rax
0x1800a7d83  lea     rcx, [rbp+0E0h+var_E0]
0x1800a7d87  call    ?Throw@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@JPEBGZZ; CSrmFunctionTracer::Throw(CSrmDebugInfo,long,ushort const *,...)
0x1800a7d8d  lea     rcx, [rbp+0E0h+var_E0]; this
0x1800a7d91  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x1800a7d96  mov     ebx, eax
0x1800a7d98  lea     rax, [rsp+1E0h+var_180]
0x1800a7d9d  mov     [rsp+1E0h+var_1A0], rax
0x1800a7da2  mov     [rsp+1E0h+var_1B8], r13d
0x1800a7da7  mov     dword ptr [rsp+1E0h+var_1C0], 16Ah
0x1800a7daf  mov     r9, r15
0x1800a7db2  mov     r8, r12
0x1800a7db5  mov     rdx, r14
0x1800a7db8  lea     rcx, [rsp+1E0h+var_180]
0x1800a7dbd  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x1800a7dc2  nop
0x1800a7dc3  lea     r9, aIfsrmstoragemo; "IFsrmStorageModuleDefinition::get_Stora"...
0x1800a7dca  mov     r8d, ebx
0x1800a7dcd  mov     rdx, rax
0x1800a7dd0  lea     rcx, [rbp+0E0h+var_E0]
0x1800a7dd4  call    ?Throw@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@JPEBGZZ; CSrmFunctionTracer::Throw(CSrmDebugInfo,long,ushort const *,...)
0x1800a7dda  lea     rax, [rsp+1E0h+var_180]
0x1800a7ddf  mov     [rsp+1E0h+var_1A0], rax
0x1800a7de4  mov     [rsp+1E0h+var_1B8], r13d
0x1800a7de9  mov     dword ptr [rsp+1E0h+var_1C0], 160h
0x1800a7df1  mov     r9, r15
0x1800a7df4  mov     r8, r12
0x1800a7df7  mov     rdx, r14
0x1800a7dfa  lea     rcx, [rsp+1E0h+var_180]
0x1800a7dff  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x1800a7e04  nop
0x1800a7e05  lea     r8, aQueryinterface_1; "QueryInterface IFsrmStorageModuleDefini"...
0x1800a7e0c  mov     rdx, rax
0x1800a7e0f  lea     rcx, [rbp+0E0h+var_E0]
0x1800a7e13  call    ?TranslateComError@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@PEBGZZ; CSrmFunctionTracer::TranslateComError(CSrmDebugInfo,ushort const *,...)
0x1800a7e19  lea     rcx, [rbp+0E0h+var_E0]; this
0x1800a7e1d  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x1800a7e22  mov     ebx, eax
0x1800a7e24  lea     rax, [rsp+1E0h+var_180]
0x1800a7e29  mov     [rsp+1E0h+var_1A0], rax
0x1800a7e2e  mov     [rsp+1E0h+var_1B8], r13d
0x1800a7e33  mov     dword ptr [rsp+1E0h+var_1C0], 151h
0x1800a7e3b  mov     r9, r15
0x1800a7e3e  mov     r8, r12
0x1800a7e41  mov     rdx, r14
0x1800a7e44  lea     rcx, [rsp+1E0h+var_180]
0x1800a7e49  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x1800a7e4e  nop
0x1800a7e4f  lea     r9, aIfsrmpipelinem_1; "IFsrmPipelineModuleDefinition::get_Modu"...
0x1800a7e56  mov     r8d, ebx
0x1800a7e59  mov     rdx, rax
0x1800a7e5c  lea     rcx, [rbp+0E0h+var_E0]
0x1800a7e60  call    ?Throw@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@JPEBGZZ; CSrmFunctionTracer::Throw(CSrmDebugInfo,long,ushort const *,...)
```
