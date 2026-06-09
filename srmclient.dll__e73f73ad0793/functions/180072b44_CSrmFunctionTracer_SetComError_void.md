# CSrmFunctionTracer::SetComError(void)

- ea: `0x180072b44`
- end: `0x180072ed0`
- name: `?SetComError@CSrmFunctionTracer@@QEAAXXZ`
- size: `908`
- prototype: `void __fastcall(CSrmFunctionTracer *__hidden this)`
- caller_count: `100`
- callee_count: `11`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180021e20`
- `0x180022680`
- `0x1800245e0`
- `0x180024760`
- `0x180024910`
- `0x180024aa0`
- `0x180024ca0`
- `0x180024e40`
- `0x180025040`
- `0x180025150`
- `0x1800252d0`
- `0x1800254d0`
- `0x1800256d0`
- `0x180025940`
- `0x180025c50`
- `0x180025db0`
- `0x180025eb0`
- `0x1800269b0`
- `0x1800277f0`
- `0x18002f580`
- `0x18002f6d0`
- `0x18002f8e0`
- `0x18002fa90`
- `0x18002fbe0`
- `0x18002fd60`
- `0x1800300d0`
- `0x1800303e0`
- `0x180030540`
- `0x180030690`
- `0x1800309c0`
- `0x180030c20`
- `0x180035b70`
- `0x180035d70`
- `0x180035ec0`
- `0x1800360c0`
- `0x180036300`
- `0x180036490`
- `0x1800365f0`
- `0x1800372c0`
- `0x180037600`
- `0x180037be0`
- `0x180037db0`
- `0x18003a0d0`
- `0x18003a250`
- `0x18003a3f0`
- `0x18003a5f0`
- `0x18003a780`
- `0x18003a980`
- `0x18003ab00`
- `0x18003ac90`

## callees

- `0x180001350`
- `0x180006a1c`
- `0x18006fe68`
- `0x18006febc`
- `0x1800700b8`
- `0x1800718cc`
- `0x180072b44`
- `0x180073d04`
- `0x1800b078a`
- `0x1800b07d0`
- `0x1800d5010`

## import_xrefs

- `OLEAUT32!__imp_SetErrorInfo` at `0x180072ca5`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180072ca5`
- `OLEAUT32!__imp_CreateErrorInfo` at `0x180072c24`
- `OLEAUT32!__imp_CreateErrorInfo` at `0x180072c24`

## string_xrefs

- `0x180072e5c`: `spCreateErrorInfo::SetDescription failed, %#x`
- `0x180072eb4`: `CreateErrorInfo failed, %#x`
- `0x180072e04`: `ICreateErrorInfo->QI(IErrorInfo) failed, %#x`
- `0x180072b86`: `CSrmFunctionTracer::SetComError`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
void __fastcall CSrmFunctionTracer::SetComError(CSrmFunctionTracer *this)
{
  void **v2; // rdx
  unsigned int v3; // ebx
  __int64 v4; // rax
  unsigned int v5; // ebx
  __int64 v6; // rax
  unsigned int v7; // ebx
  __int64 v8; // rax
  unsigned int Hr; // ebx
  __int64 v10; // rax
  __int64 v11; // [rsp+20h] [rbp-1E8h]
  __int64 v12; // [rsp+20h] [rbp-1E8h]
  __int64 v13; // [rsp+20h] [rbp-1E8h]
  __int64 v14; // [rsp+20h] [rbp-1E8h]
  ICreateErrorInfo *pperrinfo; // [rsp+40h] [rbp-1C8h] BYREF
  IErrorInfo *perrinfo; // [rsp+48h] [rbp-1C0h] BYREF
  _QWORD *v17; // [rsp+50h] [rbp-1B8h]
  int v18; // [rsp+58h] [rbp-1B0h] BYREF
  _QWORD v19[3]; // [rsp+60h] [rbp-1A8h] BYREF
  int v20; // [rsp+78h] [rbp-190h]
  int v21; // [rsp+7Ch] [rbp-18Ch]
  int v22; // [rsp+80h] [rbp-188h]
  _BYTE v23[96]; // [rsp+88h] [rbp-180h] BYREF
  int v24; // [rsp+E8h] [rbp-120h]
  _com_error *v25; // [rsp+F0h] [rbp-118h] BYREF
  const exception *v26; // [rsp+F8h] [rbp-110h] BYREF
  void *Block[3]; // [rsp+100h] [rbp-108h] BYREF
  unsigned __int64 v28; // [rsp+118h] [rbp-F0h]
  void **v29; // [rsp+130h] [rbp-D8h] BYREF
  HRESULT v30; // [rsp+138h] [rbp-D0h]
  unsigned int v31; // [rsp+15Ch] [rbp-ACh]

  perrinfo = (IErrorInfo *)v19;
  v19[0] = L"base\\fs\\fsrm\\utilities\\functracer\\functiontracer.cpp";
  v19[1] = L"CSrmFunctionTracer::SetComError";
  v19[2] = L"TRCTRCC";
  v20 = 2656;
  v21 = 17;
  v22 = 255;
  v24 = 0x1000000;
  memset_0(v23, 0, sizeof(v23));
  CSrmFunctionTracer::CSrmFunctionTracer((__int64)&v29, (const struct CSrmDebugInfo *)v19, 0);
  try
  {
    if ( *((int *)this + 2) < 0 )
    {
      CSrmFunctionTracerBase::GetErrorText(this, Block);
      pperrinfo = 0;
      perrinfo = 0;
      v30 = CreateErrorInfo(&pperrinfo);
      if ( v30 < 0 )
      {
        Hr = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v29);
        v17 = v19;
        v10 = CSrmDebugInfo::CSrmDebugInfo(
                (__int64)v19,
                (__int64)L"base\\fs\\fsrm\\utilities\\functracer\\functiontracer.cpp",
                (__int64)L"TRCTRCC",
                (__int64)L"CSrmFunctionTracer::SetComError",
                2672,
                17);
        LODWORD(v14) = Hr;
        CSrmFunctionTracer::Throw(&v29, v10, Hr, L"CreateErrorInfo failed, %#x", v14);
      }
      v2 = Block;
      if ( v28 >= 8 )
        v2 = (void **)Block[0];
      v30 = ((__int64 (__fastcall *)(ICreateErrorInfo *, void **))pperrinfo->lpVtbl->SetDescription)(pperrinfo, v2);
      if ( v30 < 0 )
      {
        v7 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v29);
        v17 = v19;
        v8 = CSrmDebugInfo::CSrmDebugInfo(
               (__int64)v19,
               (__int64)L"base\\fs\\fsrm\\utilities\\functracer\\functiontracer.cpp",
               (__int64)L"TRCTRCC",
               (__int64)L"CSrmFunctionTracer::SetComError",
               2677,
               17);
        LODWORD(v13) = v7;
        CSrmFunctionTracer::Throw(&v29, v8, v7, L"spCreateErrorInfo::SetDescription failed, %#x", v13);
      }
      v30 = ((__int64 (__fastcall *)(ICreateErrorInfo *, GUID *, IErrorInfo **))pperrinfo->lpVtbl->QueryInterface)(
              pperrinfo,
              &IID_IErrorInfo,
              &perrinfo);
      if ( v30 < 0 )
      {
        v5 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v29);
        v17 = v19;
        v6 = CSrmDebugInfo::CSrmDebugInfo(
               (__int64)v19,
               (__int64)L"base\\fs\\fsrm\\utilities\\functracer\\functiontracer.cpp",
               (__int64)L"TRCTRCC",
               (__int64)L"CSrmFunctionTracer::SetComError",
               2682,
               17);
        LODWORD(v12) = v5;
        CSrmFunctionTracer::Throw(&v29, v6, v5, L"ICreateErrorInfo->QI(IErrorInfo) failed, %#x", v12);
      }
      v30 = SetErrorInfo(0, perrinfo);
      if ( v30 < 0 )
      {
        v3 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v29);
        v17 = v19;
        v4 = CSrmDebugInfo::CSrmDebugInfo(
               (__int64)v19,
               (__int64)L"base\\fs\\fsrm\\utilities\\functracer\\functiontracer.cpp",
               (__int64)L"TRCTRCC",
               (__int64)L"CSrmFunctionTracer::SetComError",
               2687,
               17);
        LODWORD(v11) = v3;
        CSrmFunctionTracer::Throw(&v29, v4, v3, L"SetErrorInfo failed, %#x", v11);
      }
      if ( perrinfo )
        ((void (__fastcall *)(IErrorInfo *))perrinfo->lpVtbl->Release)(perrinfo);
      if ( pperrinfo )
        ((void (__fastcall *)(ICreateErrorInfo *))pperrinfo->lpVtbl->Release)(pperrinfo);
      if ( v28 >= 8 )
        operator delete(Block[0]);
      v28 = 7;
      Block[2] = 0;
      LOWORD(Block[0]) = 0;
    }
  }
  catch ( long v18 )
  {
    CSrmFunctionTracer::HandleHresultException(
      (CSrmFunctionTracer *)&v29,
      v18,
      L"base\\fs\\fsrm\\utilities\\functracer\\functiontracer.cpp",
      L"TRCTRCC",
      L"CSrmFunctionTracer::SetComError",
      0xA84u,
      v31);
  }
  catch ( _com_error *v25 )
  {
    CSrmFunctionTracer::HandleComException(
      (CSrmFunctionTracer *)&v29,
      v25,
      L"base\\fs\\fsrm\\utilities\\functracer\\functiontracer.cpp",
      L"TRCTRCC",
      L"CSrmFunctionTracer::SetComError",
      0xA84u,
      v31);
  }
  catch ( std::bad_alloc )
  {
    CSrmFunctionTracer::HandleStdBadAllocException(
      (CSrmFunctionTracer *)&v29,
      L"base\\fs\\fsrm\\utilities\\functracer\\functiontracer.cpp",
      L"TRCTRCC",
      L"CSrmFunctionTracer::SetComError",
      0xA84u,
      v31);
  }
  catch ( const exception *v26 )
  {
    CSrmFunctionTracer::HandleStdGenericException(
      (CSrmFunctionTracer *)&v29,
      v26,
      L"base\\fs\\fsrm\\utilities\\functracer\\functiontracer.cpp",
      L"TRCTRCC",
      L"CSrmFunctionTracer::SetComError",
      0xA84u,
      v31);
  }
  v29 = &CSrmFunctionTracer::`vftable';
  CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)&v29);
}

```

## disassembly

```asm
0x180072b44  mov     [rsp+arg_8], rbx
0x180072b49  mov     [rsp+arg_10], rsi
0x180072b4e  push    r12
0x180072b50  push    r14
0x180072b52  push    r15
0x180072b54  sub     rsp, 1F0h
0x180072b5b  mov     rax, cs:__security_cookie
0x180072b62  xor     rax, rsp
0x180072b65  mov     [rsp+208h+var_28], rax
0x180072b6d  mov     rbx, rcx
0x180072b70  lea     rax, [rsp+208h+var_1A8]
0x180072b75  mov     [rsp+208h+perrinfo], rax
0x180072b7a  lea     rsi, aBaseFsFsrmUtil_9; "base\\fs\\fsrm\\utilities\\functracer\\"...
0x180072b81  mov     [rsp+208h+var_1A8], rsi
0x180072b86  lea     r14, aCsrmfunctiontr_2; "CSrmFunctionTracer::SetComError"
0x180072b8d  mov     [rsp+208h+var_1A0], r14
0x180072b92  lea     r15, aTrctrcc; "TRCTRCC"
0x180072b99  mov     [rsp+208h+var_198], r15
0x180072b9e  mov     [rsp+208h+var_190], 0A60h
0x180072ba6  mov     r12d, 11h
0x180072bac  mov     [rsp+208h+var_18C], r12d
0x180072bb1  mov     [rsp+208h+var_188], 0FFh
0x180072bbc  mov     [rsp+208h+var_120], 1000000h
0x180072bc7  xor     edx, edx; Val
0x180072bc9  lea     r8d, [r12+4Fh]; Size
0x180072bce  lea     rcx, [rsp+208h+var_180]; void *
0x180072bd6  call    memset_0
0x180072bdb  nop
0x180072bdc  xor     r8d, r8d
0x180072bdf  lea     rdx, [rsp+208h+var_1A8]
0x180072be4  lea     rcx, [rsp+208h+var_D8]
0x180072bec  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x180072bf1  nop
0x180072bf2  cmp     dword ptr [rbx+8], 0
0x180072bf6  jge     loc_180072D22
0x180072bfc  lea     rdx, [rsp+208h+Block]
0x180072c04  mov     rcx, rbx
0x180072c07  call    ?GetErrorText@CSrmFunctionTracerBase@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; CSrmFunctionTracerBase::GetErrorText(void)
0x180072c0c  nop
0x180072c0d  mov     [rsp+208h+pperrinfo], 0
0x180072c16  mov     [rsp+208h+perrinfo], 0
0x180072c1f  lea     rcx, [rsp+208h+pperrinfo]; pperrinfo
0x180072c24  call    cs:__imp_CreateErrorInfo
0x180072c2a  mov     [rsp+208h+var_D0], eax
0x180072c31  test    eax, eax
0x180072c33  js      loc_180072E76
0x180072c39  mov     rcx, [rsp+208h+pperrinfo]
0x180072c3e  mov     rax, [rcx]
0x180072c41  lea     rdx, [rsp+208h+Block]
0x180072c49  cmp     [rsp+208h+var_F0], 8
0x180072c52  cmovnb  rdx, [rsp+208h+Block]
0x180072c5b  mov     rax, [rax+28h]
0x180072c5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072c64  mov     [rsp+208h+var_D0], eax
0x180072c6b  test    eax, eax
0x180072c6d  js      loc_180072E1E
0x180072c73  mov     rcx, [rsp+208h+pperrinfo]
0x180072c78  mov     rax, [rcx]
0x180072c7b  lea     r8, [rsp+208h+perrinfo]
0x180072c80  lea     rdx, IID_IErrorInfo
0x180072c87  mov     rax, [rax]
0x180072c8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072c8f  mov     [rsp+208h+var_D0], eax
0x180072c96  test    eax, eax
0x180072c98  js      loc_180072DC6
0x180072c9e  mov     rdx, [rsp+208h+perrinfo]; perrinfo
0x180072ca3  xor     ecx, ecx; dwReserved
0x180072ca5  call    cs:__imp_SetErrorInfo
0x180072cab  mov     [rsp+208h+var_D0], eax
0x180072cb2  test    eax, eax
0x180072cb4  js      loc_180072D6E
0x180072cba  mov     rcx, [rsp+208h+perrinfo]
0x180072cbf  test    rcx, rcx
0x180072cc2  jz      short loc_180072CD1
0x180072cc4  mov     rax, [rcx]
0x180072cc7  mov     rax, [rax+10h]
0x180072ccb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072cd0  nop
0x180072cd1  mov     rcx, [rsp+208h+pperrinfo]
0x180072cd6  test    rcx, rcx
0x180072cd9  jz      short loc_180072CE8
0x180072cdb  mov     rax, [rcx]
0x180072cde  mov     rax, [rax+10h]
0x180072ce2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072ce7  nop
0x180072ce8  cmp     [rsp+208h+var_F0], 8
0x180072cf1  jb      short loc_180072D00
0x180072cf3  mov     rcx, [rsp+208h+Block]; Block
0x180072cfb  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180072d00  mov     [rsp+208h+var_F0], 7
0x180072d0c  mov     [rsp+208h+var_F8], 0
0x180072d18  xor     eax, eax
0x180072d1a  mov     word ptr [rsp+208h+Block], ax
0x180072d22  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x180072d29  mov     [rsp+208h+var_D8], rax
0x180072d31  lea     rcx, [rsp+208h+var_D8]; this
0x180072d39  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x180072d3e  mov     rcx, [rsp+208h+var_28]
0x180072d46  xor     rcx, rsp; StackCookie
0x180072d49  call    __security_check_cookie
0x180072d4e  lea     r11, [rsp+208h+var_18]
0x180072d56  mov     rbx, [r11+28h]
0x180072d5a  mov     rsi, [r11+30h]
0x180072d5e  mov     rsp, r11
0x180072d61  pop     r15
0x180072d63  pop     r14
0x180072d65  pop     r12
0x180072d67  retn
0x180072d68  jmp     short loc_180072D22
0x180072d6a  jmp     short loc_180072D22
0x180072d6c  jmp     short loc_180072D22
0x180072d6e  lea     rcx, [rsp+208h+var_D8]; this
0x180072d76  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x180072d7b  mov     ebx, eax
0x180072d7d  lea     rax, [rsp+208h+var_1A8]
0x180072d82  mov     [rsp+208h+var_1B8], rax
0x180072d87  mov     [rsp+208h+var_1E0], r12d
0x180072d8c  mov     dword ptr [rsp+208h+var_1E8], 0A7Fh
0x180072d94  mov     r9, r14
0x180072d97  mov     r8, r15
0x180072d9a  mov     rdx, rsi
0x180072d9d  lea     rcx, [rsp+208h+var_1A8]
0x180072da2  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x180072da7  nop
0x180072da8  mov     dword ptr [rsp+208h+var_1E8], ebx
0x180072dac  lea     r9, aSeterrorinfoFa; "SetErrorInfo failed, %#x"
0x180072db3  mov     r8d, ebx
0x180072db6  mov     rdx, rax
0x180072db9  lea     rcx, [rsp+208h+var_D8]
0x180072dc1  call    ?Throw@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@JPEBGZZ; CSrmFunctionTracer::Throw(CSrmDebugInfo,long,ushort const *,...)
0x180072dc6  lea     rcx, [rsp+208h+var_D8]; this
0x180072dce  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x180072dd3  mov     ebx, eax
0x180072dd5  lea     rax, [rsp+208h+var_1A8]
0x180072dda  mov     [rsp+208h+var_1B8], rax
0x180072ddf  mov     [rsp+208h+var_1E0], r12d
0x180072de4  mov     dword ptr [rsp+208h+var_1E8], 0A7Ah
0x180072dec  mov     r9, r14
0x180072def  mov     r8, r15
0x180072df2  mov     rdx, rsi
0x180072df5  lea     rcx, [rsp+208h+var_1A8]
0x180072dfa  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x180072dff  nop
0x180072e00  mov     dword ptr [rsp+208h+var_1E8], ebx
0x180072e04  lea     r9, aIcreateerrorin; "ICreateErrorInfo->QI(IErrorInfo) failed"...
0x180072e0b  mov     r8d, ebx
0x180072e0e  mov     rdx, rax
0x180072e11  lea     rcx, [rsp+208h+var_D8]
0x180072e19  call    ?Throw@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@JPEBGZZ; CSrmFunctionTracer::Throw(CSrmDebugInfo,long,ushort const *,...)
0x180072e1e  lea     rcx, [rsp+208h+var_D8]; this
0x180072e26  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x180072e2b  mov     ebx, eax
0x180072e2d  lea     rax, [rsp+208h+var_1A8]
0x180072e32  mov     [rsp+208h+var_1B8], rax
0x180072e37  mov     [rsp+208h+var_1E0], r12d
0x180072e3c  mov     dword ptr [rsp+208h+var_1E8], 0A75h
0x180072e44  mov     r9, r14
0x180072e47  mov     r8, r15
0x180072e4a  mov     rdx, rsi
0x180072e4d  lea     rcx, [rsp+208h+var_1A8]
0x180072e52  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x180072e57  nop
0x180072e58  mov     dword ptr [rsp+208h+var_1E8], ebx
0x180072e5c  lea     r9, aSpcreateerrori_0; "spCreateErrorInfo::SetDescription faile"...
0x180072e63  mov     r8d, ebx
0x180072e66  mov     rdx, rax
0x180072e69  lea     rcx, [rsp+208h+var_D8]
0x180072e71  call    ?Throw@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@JPEBGZZ; CSrmFunctionTracer::Throw(CSrmDebugInfo,long,ushort const *,...)
0x180072e76  lea     rcx, [rsp+208h+var_D8]; this
0x180072e7e  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x180072e83  mov     ebx, eax
0x180072e85  lea     rax, [rsp+208h+var_1A8]
0x180072e8a  mov     [rsp+208h+var_1B8], rax
0x180072e8f  mov     [rsp+208h+var_1E0], r12d
0x180072e94  mov     dword ptr [rsp+208h+var_1E8], 0A70h
0x180072e9c  mov     r9, r14
0x180072e9f  mov     r8, r15
0x180072ea2  mov     rdx, rsi
0x180072ea5  lea     rcx, [rsp+208h+var_1A8]
0x180072eaa  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x180072eaf  nop
0x180072eb0  mov     dword ptr [rsp+208h+var_1E8], ebx
0x180072eb4  lea     r9, aCreateerrorinf; "CreateErrorInfo failed, %#x"
0x180072ebb  mov     r8d, ebx
0x180072ebe  mov     rdx, rax
0x180072ec1  lea     rcx, [rsp+208h+var_D8]
0x180072ec9  call    ?Throw@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@JPEBGZZ; CSrmFunctionTracer::Throw(CSrmDebugInfo,long,ushort const *,...)
```
