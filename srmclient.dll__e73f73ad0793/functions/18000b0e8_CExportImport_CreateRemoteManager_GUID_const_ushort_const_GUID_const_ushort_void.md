# CExportImport::CreateRemoteManager(_GUID const &,ushort const *,_GUID const &,ushort *,void * *)

- ea: `0x18000b0e8`
- end: `0x18000b38c`
- name: `?CreateRemoteManager@CExportImport@@AEAAXAEBU_GUID@@PEBG0PEAGPEAPEAX@Z`
- size: `676`
- prototype: `void __fastcall(CExportImport *__hidden this, const struct _GUID *, const unsigned __int16 *, const struct _GUID *, unsigned __int16 *, void **)`
- caller_count: `6`
- callee_count: `11`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18000b3a0`
- `0x18000b5e0`
- `0x18000b820`
- `0x18000ba70`
- `0x18000bd50`
- `0x18000c030`

## callees

- `0x18000ad14`
- `0x18000af40`
- `0x18000b0e8`
- `0x18006fe68`
- `0x18006febc`
- `0x1800700b8`
- `0x180070d7c`
- `0x1800744e8`
- `0x180075034`
- `0x1800b078a`
- `0x1800b07d0`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18000b27c`
- `ole32!CoTaskMemFree` at `0x18000b27c`
- `KERNEL32!GetComputerNameW` at `0x18000b1bd`
- `KERNEL32!GetComputerNameW` at `0x18000b1bd`

## string_xrefs

- `0x18000b14f`: `SRMPATHH`
- `0x18000b1ff`: `SRMPATHH`
- `0x18000b324`: `SRMPATHH`
- `0x18000b138`: `base\fs\fsrm\service\srmclient\exportimport.cpp`
- `0x18000b144`: `CExportImport::CreateRemoteManager`
- `0x18000b339`: `GetComputerName`
- `0x18000b2f6`: `CoCreateInstanceEx CLSID_FsrmFileGroupManager`
- `0x18000b378`: `CoCreateInstanceEx CLSID_FsrmFileGroupManager`

## pseudocode

```c
void __fastcall CExportImport::CreateRemoteManager(
        CExportImport *this,
        const struct _GUID *a2,
        const unsigned __int16 *a3,
        const struct _GUID *a4,
        unsigned __int16 *a5,
        void **a6)
{
  LPWSTR v8; // rbx
  __int128 v9; // xmm6
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rax
  LPWSTR lpBuffer; // [rsp+48h] [rbp-C0h] BYREF
  const unsigned __int16 **nSize; // [rsp+50h] [rbp-B8h]
  DWORD nSize_8[4]; // [rsp+58h] [rbp-B0h] BYREF
  const struct _GUID *v16; // [rsp+68h] [rbp-A0h]
  void *v17; // [rsp+70h] [rbp-98h]
  __int64 v18; // [rsp+78h] [rbp-90h]
  const unsigned __int16 *v19; // [rsp+80h] [rbp-88h] BYREF
  const wchar_t *v20; // [rsp+88h] [rbp-80h]
  const unsigned __int16 *v21; // [rsp+90h] [rbp-78h]
  __int64 v22; // [rsp+98h] [rbp-70h]
  int v23; // [rsp+A0h] [rbp-68h]
  _BYTE v24[96]; // [rsp+A8h] [rbp-60h] BYREF
  int v25; // [rsp+108h] [rbp+0h]
  void **v26; // [rsp+118h] [rbp+10h] BYREF
  int v27; // [rsp+120h] [rbp+18h]

  *(_QWORD *)nSize_8 = &v19;
  v19 = L"base\\fs\\fsrm\\service\\srmclient\\exportimport.cpp";
  v20 = L"CExportImport::CreateRemoteManager";
  v21 = L"SRMPATHH";
  v22 = 513;
  v23 = 255;
  v25 = 0x1000000;
  memset_0(v24, 0, sizeof(v24));
  CSrmFunctionTracer::CSrmFunctionTracer(&v26, &v19, 0);
  lpBuffer = 0;
  if ( a5 )
  {
    CSrmAutoPWSZ::CopyFrom((CSrmAutoPWSZ *)&lpBuffer, a5);
    v8 = lpBuffer;
  }
  else
  {
    nSize_8[0] = 16;
    CSrmAutoPWSZ::Allocate((CSrmAutoPWSZ *)&lpBuffer, 0x10u);
    v8 = lpBuffer;
    if ( !GetComputerNameW(lpBuffer, nSize_8) )
    {
      nSize = &v19;
      v11 = CSrmDebugInfo::CSrmDebugInfo(
              &v19,
              L"base\\fs\\fsrm\\service\\srmclient\\exportimport.cpp",
              L"SRMPATHH",
              L"CExportImport::CreateRemoteManager",
              530,
              0);
      CSrmFunctionTracer::TranslateWin32Error(&v26, v11, L"GetComputerName");
    }
  }
  v16 = a4;
  v17 = 0;
  v18 = 0;
  v9 = (__int128)*a2;
  nSize = &v19;
  v19 = L"base\\fs\\fsrm\\service\\srmclient\\exportimport.cpp";
  v20 = L"CExportImport::CreateRemoteManager";
  v21 = L"SRMPATHH";
  v22 = 541;
  v23 = 255;
  v25 = 0x1000000;
  memset_0(v24, 0, sizeof(v24));
  *(_OWORD *)nSize_8 = v9;
  CSrmFunctionTracer::CoCreateInstanceExWithLog(&v26, &v19, nSize_8);
  if ( v27 < 0 )
  {
    nSize = &v19;
    v12 = CSrmDebugInfo::CSrmDebugInfo(
            &v19,
            L"base\\fs\\fsrm\\service\\srmclient\\exportimport.cpp",
            L"SRMPATHH",
            L"CExportImport::CreateRemoteManager",
            550,
            0);
    CSrmFunctionTracer::TranslateComError(&v26, v12, L"CoCreateInstanceEx CLSID_FsrmFileGroupManager");
  }
  if ( (int)v18 < 0 )
  {
    nSize = &v19;
    v10 = CSrmDebugInfo::CSrmDebugInfo(
            &v19,
            L"base\\fs\\fsrm\\service\\srmclient\\exportimport.cpp",
            L"SRMPATHH",
            L"CExportImport::CreateRemoteManager",
            555,
            0);
    CSrmFunctionTracer::TranslateComError(&v26, v10, L"CoCreateInstanceEx CLSID_FsrmFileGroupManager");
  }
  *a6 = v17;
  CoTaskMemFree(v8);
  lpBuffer = 0;
  v26 = &CSrmFunctionTracer::`vftable';
  CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)&v26);
}

```

## disassembly

```asm
0x18000b0e8  mov     rax, rsp
0x18000b0eb  push    rbp
0x18000b0ec  push    rbx
0x18000b0ed  push    rsi
0x18000b0ee  push    rdi
0x18000b0ef  push    r12
0x18000b0f1  push    r13
0x18000b0f3  push    r14
0x18000b0f5  push    r15
0x18000b0f7  lea     rbp, [rax-128h]
0x18000b0fe  sub     rsp, 1E8h
0x18000b105  movaps  xmmword ptr [rax-58h], xmm6
0x18000b109  mov     rax, cs:__security_cookie
0x18000b110  xor     rax, rsp
0x18000b113  mov     [rbp+120h+var_60], rax
0x18000b11a  mov     r14, r9
0x18000b11d  mov     rsi, rdx
0x18000b120  mov     rbx, [rbp+120h+arg_20]
0x18000b127  mov     rdi, [rbp+120h+arg_28]
0x18000b12e  lea     rax, [rsp+220h+var_1A8]
0x18000b133  mov     qword ptr [rsp+220h+nSize+8], rax
0x18000b138  lea     r12, aBaseFsFsrmServ_0; "base\\fs\\fsrm\\service\\srmclient\\exp"...
0x18000b13f  mov     [rsp+220h+var_1A8], r12
0x18000b144  lea     r13, aCexportimportC; "CExportImport::CreateRemoteManager"
0x18000b14b  mov     [rbp+120h+var_1A0], r13
0x18000b14f  lea     rax, aSrmpathh; "SRMPATHH"
0x18000b156  mov     [rbp+120h+var_198], rax
0x18000b15a  mov     [rbp+120h+var_190], 201h
0x18000b162  xor     r15d, r15d
0x18000b165  mov     [rbp+120h+var_188], 0FFh
0x18000b16c  mov     [rbp+120h+var_120], 1000000h
0x18000b173  xor     edx, edx; Val
0x18000b175  lea     r8d, [r15+60h]; Size
0x18000b179  lea     rcx, [rbp+120h+var_180]; void *
0x18000b17d  call    memset_0
0x18000b182  nop
0x18000b183  xor     r8d, r8d
0x18000b186  lea     rdx, [rsp+220h+var_1A8]
0x18000b18b  lea     rcx, [rbp+120h+var_110]
0x18000b18f  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x18000b194  nop
0x18000b195  mov     [rsp+220h+lpBuffer], r15
0x18000b19a  lea     rcx, [rsp+220h+lpBuffer]; this
0x18000b19f  test    rbx, rbx
0x18000b1a2  jnz     short loc_18000B1CD
0x18000b1a4  lea     edx, [rbx+10h]; unsigned __int64
0x18000b1a7  mov     [rsp+220h+nSize+8], edx
0x18000b1ab  call    ?Allocate@CSrmAutoPWSZ@@QEAAX_K@Z; CSrmAutoPWSZ::Allocate(unsigned __int64)
0x18000b1b0  lea     rdx, [rsp+220h+nSize+8]; nSize
0x18000b1b5  mov     rbx, [rsp+220h+lpBuffer]
0x18000b1ba  mov     rcx, rbx; lpBuffer
0x18000b1bd  call    cs:__imp_GetComputerNameW
0x18000b1c3  test    eax, eax
0x18000b1c5  jz      loc_18000B30A
0x18000b1cb  jmp     short loc_18000B1DA
0x18000b1cd  mov     rdx, rbx; unsigned __int16 *
0x18000b1d0  call    ?CopyFrom@CSrmAutoPWSZ@@QEAAXPEBG@Z; CSrmAutoPWSZ::CopyFrom(ushort const *)
0x18000b1d5  mov     rbx, [rsp+220h+lpBuffer]
0x18000b1da  mov     [rsp+220h+var_1C0], r14
0x18000b1df  mov     [rsp+220h+var_1B8], r15
0x18000b1e4  mov     [rsp+220h+var_1B0], r15
0x18000b1e9  movups  xmm6, xmmword ptr [rsi]
0x18000b1ec  lea     rax, [rsp+220h+var_1A8]
0x18000b1f1  mov     qword ptr [rsp+220h+nSize], rax
0x18000b1f6  mov     [rsp+220h+var_1A8], r12
0x18000b1fb  mov     [rbp+120h+var_1A0], r13
0x18000b1ff  lea     rsi, aSrmpathh; "SRMPATHH"
0x18000b206  mov     [rbp+120h+var_198], rsi
0x18000b20a  mov     [rbp+120h+var_190], 21Dh
0x18000b212  mov     [rbp+120h+var_188], 0FFh
0x18000b219  mov     [rbp+120h+var_120], 1000000h
0x18000b220  xor     edx, edx; Val
0x18000b222  lea     r8d, [rdx+60h]; Size
0x18000b226  lea     rcx, [rbp+120h+var_180]; void *
0x18000b22a  call    memset_0
0x18000b22f  nop
0x18000b230  movdqu  xmmword ptr [rsp+220h+nSize+8], xmm6
0x18000b236  lea     rax, [rsp+220h+var_1C0]
0x18000b23b  mov     [rsp+220h+var_1E8], rax
0x18000b240  mov     [rsp+28h], rbx
0x18000b245  mov     dword ptr [rsp+220h+var_200], 14h
0x18000b24d  lea     r8, [rsp+220h+nSize+8]
0x18000b252  lea     rdx, [rsp+220h+var_1A8]
0x18000b257  lea     rcx, [rbp+120h+var_110]
0x18000b25b  call    ?CoCreateInstanceExWithLog@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@U_GUID@@PEBGKPEAGKPEAUtagMULTI_QI@@@Z; CSrmFunctionTracer::CoCreateInstanceExWithLog(CSrmDebugInfo,_GUID,ushort const *,ulong,ushort *,ulong,tagMULTI_QI *)
0x18000b260  cmp     [rbp+120h+var_108], r15d
0x18000b264  jl      loc_18000B34D
0x18000b26a  cmp     dword ptr [rsp+220h+var_1B0], r15d
0x18000b26f  jl      short loc_18000B2CB
0x18000b271  mov     rax, [rsp+220h+var_1B8]
0x18000b276  mov     [rdi], rax
0x18000b279  mov     rcx, rbx; pv
0x18000b27c  call    cs:__imp_CoTaskMemFree
0x18000b282  mov     [rsp+220h+lpBuffer], r15
0x18000b287  mov     [rsp+220h+lpBuffer], r15
0x18000b28c  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x18000b293  mov     [rbp+120h+var_110], rax
0x18000b297  lea     rcx, [rbp+120h+var_110]; this
0x18000b29b  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x18000b2a0  mov     rcx, [rbp+120h+var_60]
0x18000b2a7  xor     rcx, rsp; StackCookie
0x18000b2aa  call    __security_check_cookie
0x18000b2af  movaps  xmm6, [rsp+220h+var_58+8]
0x18000b2b7  add     rsp, 1E8h
0x18000b2be  pop     r15
0x18000b2c0  pop     r14
0x18000b2c2  pop     r13
0x18000b2c4  pop     r12
0x18000b2c6  pop     rdi
0x18000b2c7  pop     rsi
0x18000b2c8  pop     rbx
0x18000b2c9  pop     rbp
0x18000b2ca  retn
0x18000b2cb  lea     rax, [rsp+220h+var_1A8]
0x18000b2d0  mov     qword ptr [rsp+220h+nSize], rax
0x18000b2d5  mov     [rsp+28h], r15d
0x18000b2da  mov     dword ptr [rsp+220h+var_200], 22Bh
0x18000b2e2  mov     r9, r13
0x18000b2e5  mov     r8, rsi
0x18000b2e8  mov     rdx, r12
0x18000b2eb  lea     rcx, [rsp+220h+var_1A8]
0x18000b2f0  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x18000b2f5  nop
0x18000b2f6  lea     r8, aCocreateinstan; "CoCreateInstanceEx CLSID_FsrmFileGroupM"...
0x18000b2fd  mov     rdx, rax
0x18000b300  lea     rcx, [rbp+120h+var_110]
0x18000b304  call    ?TranslateComError@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@PEBGZZ; CSrmFunctionTracer::TranslateComError(CSrmDebugInfo,ushort const *,...)
0x18000b30a  lea     rax, [rsp+220h+var_1A8]
0x18000b30f  mov     qword ptr [rsp+220h+nSize], rax
0x18000b314  mov     [rsp+28h], r15d
0x18000b319  mov     dword ptr [rsp+220h+var_200], 212h
0x18000b321  mov     r9, r13
0x18000b324  lea     r8, aSrmpathh; "SRMPATHH"
0x18000b32b  mov     rdx, r12
0x18000b32e  lea     rcx, [rsp+220h+var_1A8]
0x18000b333  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x18000b338  nop
0x18000b339  lea     r8, aGetcomputernam; "GetComputerName"
0x18000b340  mov     rdx, rax
0x18000b343  lea     rcx, [rbp+120h+var_110]
0x18000b347  call    ?TranslateWin32Error@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@PEBGZZ; CSrmFunctionTracer::TranslateWin32Error(CSrmDebugInfo,ushort const *,...)
0x18000b34d  lea     rax, [rsp+220h+var_1A8]
0x18000b352  mov     qword ptr [rsp+220h+nSize], rax
0x18000b357  mov     [rsp+28h], r15d
0x18000b35c  mov     dword ptr [rsp+220h+var_200], 226h
0x18000b364  mov     r9, r13
0x18000b367  mov     r8, rsi
0x18000b36a  mov     rdx, r12
0x18000b36d  lea     rcx, [rsp+220h+var_1A8]
0x18000b372  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x18000b377  nop
0x18000b378  lea     r8, aCocreateinstan; "CoCreateInstanceEx CLSID_FsrmFileGroupM"...
0x18000b37f  mov     rdx, rax
0x18000b382  lea     rcx, [rbp+120h+var_110]
0x18000b386  call    ?TranslateComError@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@PEBGZZ; CSrmFunctionTracer::TranslateComError(CSrmDebugInfo,ushort const *,...)
```
