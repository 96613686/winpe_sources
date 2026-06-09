# CSyncAdTask::AdSyncTaskThreadProc(void *)

- ea: `0x18000d1e0`
- end: `0x18000d55a`
- name: `?AdSyncTaskThreadProc@CSyncAdTask@@CAKPEAX@Z`
- size: `890`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x180006a1c`
- `0x1800095f4`
- `0x18000d114`
- `0x18000d1e0`
- `0x18006febc`
- `0x1800700b8`
- `0x180073a80`
- `0x1800b078a`
- `0x1800b07d0`
- `0x1800d5010`

## import_xrefs

- `ole32!CoUninitialize` at `0x18000d3fd`
- `ole32!CoUninitialize` at `0x18000d3fd`
- `ole32!CoInitializeEx` at `0x18000d291`
- `ole32!CoInitializeEx` at `0x18000d291`
- `ole32!CoCreateInstance` at `0x18000d2f0`
- `ole32!CoCreateInstance` at `0x18000d2f0`

## string_xrefs

- `0x18000d20a`: `base\fs\fsrm\service\globalstore\taskhandler.cpp`
- `0x18000d218`: `CSyncAdTask::AdSyncTaskThreadProc`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CSyncAdTask::AdSyncTaskThreadProc(CSyncAdTask *Parameter)
{
  HRESULT v1; // eax
  unsigned int v2; // esi
  HRESULT v3; // eax
  CSyncAdTask *v4; // rdi
  int v5; // eax
  int v6; // eax
  unsigned int v7; // ebx
  int Hr; // eax
  char v10; // r8
  int v11; // eax
  char v12; // r8
  int v13; // eax
  char v14; // al
  int v15; // eax
  char v16; // al
  LPVOID ppv; // [rsp+40h] [rbp-1A8h] BYREF
  __int64 v18; // [rsp+48h] [rbp-1A0h] BYREF
  __int64 v19; // [rsp+50h] [rbp-198h] BYREF
  CSyncAdTask *v20; // [rsp+58h] [rbp-190h]
  int v21; // [rsp+60h] [rbp-188h] BYREF
  int v22; // [rsp+64h] [rbp-184h] BYREF
  _com_error *v23; // [rsp+68h] [rbp-180h] BYREF
  const exception *v24; // [rsp+70h] [rbp-178h] BYREF
  _com_error *v25; // [rsp+78h] [rbp-170h] BYREF
  const exception *v26; // [rsp+80h] [rbp-168h] BYREF
  _QWORD v27[3]; // [rsp+88h] [rbp-160h] BYREF
  int v28; // [rsp+A0h] [rbp-148h]
  int v29; // [rsp+A4h] [rbp-144h]
  int v30; // [rsp+A8h] [rbp-140h]
  _DWORD v31[28]; // [rsp+B0h] [rbp-138h] BYREF
  void **v32; // [rsp+120h] [rbp-C8h] BYREF
  HRESULT v33; // [rsp+128h] [rbp-C0h]
  unsigned int v34; // [rsp+14Ch] [rbp-9Ch]

  v20 = Parameter;
  v27[0] = L"base\\fs\\fsrm\\service\\globalstore\\taskhandler.cpp";
  v27[1] = L"CSyncAdTask::AdSyncTaskThreadProc";
  v27[2] = L"TSKNDLRC";
  v28 = 204;
  v29 = 30;
  v30 = 255;
  v31[24] = 0x1000000;
  memset_0(v31, 0, 0x60u);
  CSrmFunctionTracer::CSrmFunctionTracer((__int64)&v32, (const struct CSrmDebugInfo *)v27, 0);
  v1 = CoInitializeEx(0, 0);
  v33 = v1;
  if ( v1 < 0 )
  {
    Hr = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v32);
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v32, Hr);
    v10 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v32);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v32, 0xCEu, v10, 0);
  }
  try
  {
    v33 = v1;
    CSyncAdTask::AdSyncTaskImpl(v20);
  }
  catch ( long v21 )
  {
    CSrmFunctionTracer::HandleHresultException(
      (CSrmFunctionTracer *)&v32,
      v21,
      L"base\\fs\\fsrm\\service\\globalstore\\taskhandler.cpp",
      L"TSKNDLRC",
      L"CSyncAdTask::AdSyncTaskThreadProc",
      0xDBu,
      v34);
  }
  catch ( _com_error *v23 )
  {
    CSrmFunctionTracer::HandleComException(
      (CSrmFunctionTracer *)&v32,
      v23,
      L"base\\fs\\fsrm\\service\\globalstore\\taskhandler.cpp",
      L"TSKNDLRC",
      L"CSyncAdTask::AdSyncTaskThreadProc",
      0xDBu,
      v34);
  }
  catch ( std::bad_alloc )
  {
    CSrmFunctionTracer::HandleStdBadAllocException(
      (CSrmFunctionTracer *)&v32,
      L"base\\fs\\fsrm\\service\\globalstore\\taskhandler.cpp",
      L"TSKNDLRC",
      L"CSyncAdTask::AdSyncTaskThreadProc",
      0xDBu,
      v34);
  }
  catch ( const exception *v24 )
  {
    CSrmFunctionTracer::HandleStdGenericException(
      (CSrmFunctionTracer *)&v32,
      v24,
      L"base\\fs\\fsrm\\service\\globalstore\\taskhandler.cpp",
      L"TSKNDLRC",
      L"CSyncAdTask::AdSyncTaskThreadProc",
      0xDBu,
      v34);
  }
  try
  {
    v2 = v33;
    ppv = 0;
    v18 = 0;
    v19 = 0;
    v3 = CoCreateInstance(&CLSID_StdGlobalInterfaceTable, 0, 1u, &IID_IGlobalInterfaceTable, &ppv);
    v33 = v3;
    if ( v3 < 0 )
    {
      v11 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v32);
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v32, v11);
      v12 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v32);
      CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v32, 0xEDu, v12, 0);
    }
    v33 = v3;
    v4 = v20;
    v5 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, GUID *, __int64 *))(*(_QWORD *)ppv + 40LL))(
           ppv,
           *((unsigned int *)v20 + 20),
           &IID_IUnknown,
           &v18);
    v33 = v5;
    if ( v5 < 0 )
    {
      v13 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v32);
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v32, v13);
      v14 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v32);
      CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v32, 0xEFu, v14, 0);
    }
    v33 = v5;
    (*(void (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 32LL))(ppv, *((unsigned int *)v4 + 20));
    v6 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v18)(v18, &IID_ITaskHandlerStatus, &v19);
    v33 = v6;
    if ( v6 < 0 )
    {
      v15 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v32);
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v32, v15);
      v16 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v32);
      CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v32, 0xF3u, v16, 0);
    }
    v33 = v6;
    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v19 + 32LL))(v19, v2);
    if ( v19 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    if ( v18 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    if ( ppv )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  }
  catch ( long v22 )
  {
    CSrmFunctionTracer::HandleHresultException(
      (CSrmFunctionTracer *)&v32,
      v22,
      L"base\\fs\\fsrm\\service\\globalstore\\taskhandler.cpp",
      L"TSKNDLRC",
      L"CSyncAdTask::AdSyncTaskThreadProc",
      0xF8u,
      v34);
  }
  catch ( _com_error *v25 )
  {
    CSrmFunctionTracer::HandleComException(
      (CSrmFunctionTracer *)&v32,
      v25,
      L"base\\fs\\fsrm\\service\\globalstore\\taskhandler.cpp",
      L"TSKNDLRC",
      L"CSyncAdTask::AdSyncTaskThreadProc",
      0xF8u,
      v34);
  }
  catch ( std::bad_alloc )
  {
    CSrmFunctionTracer::HandleStdBadAllocException(
      (CSrmFunctionTracer *)&v32,
      L"base\\fs\\fsrm\\service\\globalstore\\taskhandler.cpp",
      L"TSKNDLRC",
      L"CSyncAdTask::AdSyncTaskThreadProc",
      0xF8u,
      v34);
  }
  catch ( const exception *v26 )
  {
    CSrmFunctionTracer::HandleStdGenericException(
      (CSrmFunctionTracer *)&v32,
      v26,
      L"base\\fs\\fsrm\\service\\globalstore\\taskhandler.cpp",
      L"TSKNDLRC",
      L"CSyncAdTask::AdSyncTaskThreadProc",
      0xF8u,
      v34);
  }
  (*(void (__fastcall **)(CSyncAdTask *))(*(_QWORD *)v20 + 16LL))(v20);
  CoUninitialize();
  v7 = v33;
  v32 = &CSrmFunctionTracer::`vftable';
  CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)&v32);
  return v7;
}

```

## disassembly

```asm
0x18000d1e0  mov     r11, rsp
0x18000d1e3  mov     [r11+10h], rbx
0x18000d1e7  mov     [r11+18h], rsi
0x18000d1eb  push    rdi
0x18000d1ec  sub     rsp, 1E0h
0x18000d1f3  mov     rax, cs:__security_cookie
0x18000d1fa  xor     rax, rsp
0x18000d1fd  mov     [rsp+1E8h+var_18], rax
0x18000d205  mov     [rsp+1E8h+var_190], rcx
0x18000d20a  lea     rax, aBaseFsFsrmServ_39; "base\\fs\\fsrm\\service\\globalstore\\t"...
0x18000d211  mov     [r11-160h], rax
0x18000d218  lea     rax, aCsyncadtaskAds; "CSyncAdTask::AdSyncTaskThreadProc"
0x18000d21f  mov     [r11-158h], rax
0x18000d226  lea     rax, aTskndlrc; "TSKNDLRC"
0x18000d22d  mov     [r11-150h], rax
0x18000d234  mov     [rsp+1E8h+var_148], 0CCh
0x18000d23f  mov     [rsp+1E8h+var_144], 1Eh
0x18000d24a  mov     [rsp+1E8h+var_140], 0FFh
0x18000d255  xor     ebx, ebx
0x18000d257  mov     [rsp+1E8h+var_D8], 1000000h
0x18000d262  xor     edx, edx; Val
0x18000d264  lea     r8d, [rbx+60h]; Size
0x18000d268  lea     rcx, [r11-138h]; void *
0x18000d26f  call    memset_0
0x18000d274  xor     r8d, r8d
0x18000d277  lea     rdx, [rsp+1E8h+var_160]
0x18000d27f  lea     rcx, [rsp+1E8h+var_C8]
0x18000d287  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x18000d28c  nop
0x18000d28d  xor     edx, edx; dwCoInit
0x18000d28f  xor     ecx, ecx; pvReserved
0x18000d291  call    cs:__imp_CoInitializeEx
0x18000d297  mov     [rsp+1E8h+var_C0], eax
0x18000d29e  test    eax, eax
0x18000d2a0  js      loc_18000D453
0x18000d2a6  mov     [rsp+1E8h+var_C0], eax
0x18000d2ad  mov     rcx, [rsp+1E8h+var_190]; this
0x18000d2b2  call    ?AdSyncTaskImpl@CSyncAdTask@@AEAAXXZ; CSyncAdTask::AdSyncTaskImpl(void)
0x18000d2b7  nop
0x18000d2b8  jmp     short loc_18000D2BC
0x18000d2ba  xor     ebx, ebx
0x18000d2bc  mov     esi, [rsp+1E8h+var_C0]
0x18000d2c3  mov     [rsp+1E8h+var_1A8], rbx
0x18000d2c8  mov     [rsp+1E8h+var_1A0], rbx
0x18000d2cd  mov     [rsp+1E8h+var_198], rbx
0x18000d2d2  lea     rax, [rsp+1E8h+var_1A8]
0x18000d2d7  mov     [rsp+1E8h+ppv], rax; ppv
0x18000d2dc  lea     r9, IID_IGlobalInterfaceTable; riid
0x18000d2e3  xor     edx, edx; pUnkOuter
0x18000d2e5  lea     r8d, [rdx+1]; dwClsContext
0x18000d2e9  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x18000d2f0  call    cs:__imp_CoCreateInstance
0x18000d2f6  mov     [rsp+1E8h+var_C0], eax
0x18000d2fd  test    eax, eax
0x18000d2ff  js      loc_18000D495
0x18000d305  jmp     short loc_18000D30B
0x18000d307  jmp     short loc_18000D2BA
0x18000d309  jmp     short loc_18000D2BA
0x18000d30b  mov     [rsp+1E8h+var_C0], eax
0x18000d312  mov     rcx, [rsp+1E8h+var_1A8]
0x18000d317  mov     rdi, [rsp+1E8h+var_190]
0x18000d31c  mov     rax, [rcx]
0x18000d31f  lea     r9, [rsp+1E8h+var_1A0]
0x18000d324  lea     r8, IID_IUnknown
0x18000d32b  mov     edx, [rdi+50h]
0x18000d32e  mov     rax, [rax+28h]
0x18000d332  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d337  mov     [rsp+1E8h+var_C0], eax
0x18000d33e  test    eax, eax
0x18000d340  js      loc_18000D4D6
0x18000d346  mov     [rsp+1E8h+var_C0], eax
0x18000d34d  mov     rcx, [rsp+1E8h+var_1A8]
0x18000d352  mov     rax, [rcx]
0x18000d355  mov     edx, [rdi+50h]
0x18000d358  mov     rax, [rax+20h]
0x18000d35c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d361  mov     rcx, [rsp+1E8h+var_1A0]
0x18000d366  mov     rax, [rcx]
0x18000d369  lea     r8, [rsp+1E8h+var_198]
0x18000d36e  lea     rdx, IID_ITaskHandlerStatus
0x18000d375  mov     rax, [rax]
0x18000d378  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d37d  mov     [rsp+1E8h+var_C0], eax
0x18000d384  test    eax, eax
0x18000d386  js      loc_18000D517
0x18000d38c  mov     [rsp+1E8h+var_C0], eax
0x18000d393  mov     rcx, [rsp+1E8h+var_198]
0x18000d398  mov     rax, [rcx]
0x18000d39b  mov     edx, esi
0x18000d39d  mov     rax, [rax+20h]
0x18000d3a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d3a6  nop
0x18000d3a7  mov     rcx, [rsp+1E8h+var_198]
0x18000d3ac  test    rcx, rcx
0x18000d3af  jz      short loc_18000D3BE
0x18000d3b1  mov     rax, [rcx]
0x18000d3b4  mov     rax, [rax+10h]
0x18000d3b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d3bd  nop
0x18000d3be  mov     rcx, [rsp+1E8h+var_1A0]
0x18000d3c3  test    rcx, rcx
0x18000d3c6  jz      short loc_18000D3D5
0x18000d3c8  mov     rax, [rcx]
0x18000d3cb  mov     rax, [rax+10h]
0x18000d3cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d3d4  nop
0x18000d3d5  mov     rcx, [rsp+1E8h+var_1A8]
0x18000d3da  test    rcx, rcx
0x18000d3dd  jz      short loc_18000D3EC
0x18000d3df  mov     rax, [rcx]
0x18000d3e2  mov     rax, [rax+10h]
0x18000d3e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d3eb  nop
0x18000d3ec  mov     rcx, [rsp+1E8h+var_190]
0x18000d3f1  mov     rax, [rcx]
0x18000d3f4  mov     rax, [rax+10h]
0x18000d3f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d3fd  call    cs:__imp_CoUninitialize
0x18000d403  mov     ebx, [rsp+1E8h+var_C0]
0x18000d40a  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x18000d411  mov     [rsp+1E8h+var_C8], rax
0x18000d419  lea     rcx, [rsp+1E8h+var_C8]; this
0x18000d421  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x18000d426  mov     eax, ebx
0x18000d428  mov     rcx, [rsp+1E8h+var_18]
0x18000d430  xor     rcx, rsp; StackCookie
0x18000d433  call    __security_check_cookie
0x18000d438  lea     r11, [rsp+1E8h+var_8]
0x18000d440  mov     rbx, [r11+18h]
0x18000d444  mov     rsi, [r11+20h]
0x18000d448  mov     rsp, r11
0x18000d44b  pop     rdi
0x18000d44c  retn
0x18000d44d  jmp     short loc_18000D3EC
0x18000d44f  jmp     short loc_18000D3EC
0x18000d451  jmp     short loc_18000D3EC
0x18000d453  lea     rcx, [rsp+1E8h+var_C8]; this
0x18000d45b  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18000d460  mov     edx, eax; int
0x18000d462  lea     rcx, [rsp+1E8h+var_C8]; this
0x18000d46a  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x18000d46f  lea     rcx, [rsp+1E8h+var_C8]; this
0x18000d477  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18000d47c  mov     r8d, eax; char
0x18000d47f  xor     r9d, r9d; unsigned __int16 *
0x18000d482  mov     edx, 0CEh; unsigned int
0x18000d487  lea     rcx, [rsp+1E8h+var_C8]; this
0x18000d48f  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
0x18000d495  lea     rcx, [rsp+1E8h+var_C8]; this
0x18000d49d  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18000d4a2  mov     edx, eax; int
0x18000d4a4  lea     rcx, [rsp+1E8h+var_C8]; this
0x18000d4ac  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x18000d4b1  lea     rcx, [rsp+1E8h+var_C8]; this
0x18000d4b9  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18000d4be  mov     r8d, eax; char
0x18000d4c1  xor     r9d, r9d; unsigned __int16 *
0x18000d4c4  mov     edx, 0EDh; unsigned int
0x18000d4c9  lea     rcx, [rsp+1E8h+var_C8]; this
0x18000d4d1  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
0x18000d4d6  lea     rcx, [rsp+1E8h+var_C8]; this
0x18000d4de  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18000d4e3  mov     edx, eax; int
0x18000d4e5  lea     rcx, [rsp+1E8h+var_C8]; this
0x18000d4ed  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x18000d4f2  lea     rcx, [rsp+1E8h+var_C8]; this
0x18000d4fa  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18000d4ff  mov     r8d, eax; char
0x18000d502  xor     r9d, r9d; unsigned __int16 *
0x18000d505  mov     edx, 0EFh; unsigned int
0x18000d50a  lea     rcx, [rsp+1E8h+var_C8]; this
0x18000d512  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
0x18000d517  lea     rcx, [rsp+1E8h+var_C8]; this
0x18000d51f  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18000d524  mov     edx, eax; int
0x18000d526  lea     rcx, [rsp+1E8h+var_C8]; this
0x18000d52e  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x18000d533  lea     rcx, [rsp+1E8h+var_C8]; this
0x18000d53b  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18000d540  mov     r8d, eax; char
0x18000d543  xor     r9d, r9d; unsigned __int16 *
0x18000d546  mov     edx, 0F3h; unsigned int
0x18000d54b  lea     rcx, [rsp+1E8h+var_C8]; this
0x18000d553  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
```
