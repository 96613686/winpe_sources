# CClassManager::FinalConstruct(void)

- ea: `0x1800672d4`
- end: `0x1800675f6`
- name: `?FinalConstruct@CClassManager@@QEAAJXZ`
- size: `802`
- prototype: `__int64 __fastcall(LPVOID *this)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x180005778`

## callees

- `0x180006a1c`
- `0x1800095f4`
- `0x180064c64`
- `0x1800672d4`
- `0x180069704`
- `0x18006ab04`
- `0x18006febc`
- `0x1800700b8`
- `0x180073a80`
- `0x180073f54`
- `0x1800b078a`
- `0x1800b07d0`
- `0x1800d5010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x180067396`
- `ole32!CoCreateInstance` at `0x180067396`
- `ole32!CoSetProxyBlanket` at `0x180067427`
- `ole32!CoSetProxyBlanket` at `0x180067427`

## string_xrefs

- `0x180067305`: `base\fs\fsrm\service\classmanager\classmanager.cpp`
- `0x1800673a2`: `Creating CLSID_FsrmClassificationManagerService returned 0x%08lx`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CClassManager::FinalConstruct(LPVOID *this)
{
  IUnknown **v2; // rsi
  HRESULT Instance; // ebx
  HRESULT v4; // eax
  int v5; // eax
  _QWORD *v6; // rbx
  _QWORD *v7; // rdi
  unsigned int v8; // ebx
  char Hr; // al
  int v11; // eax
  char v12; // al
  int v13; // eax
  char v14; // al
  LPVOID *ppv; // [rsp+20h] [rbp-198h]
  _QWORD *v16; // [rsp+40h] [rbp-178h] BYREF
  int v17; // [rsp+48h] [rbp-170h] BYREF
  _com_error *v18; // [rsp+50h] [rbp-168h] BYREF
  const exception *v19; // [rsp+58h] [rbp-160h] BYREF
  _QWORD v20[3]; // [rsp+60h] [rbp-158h] BYREF
  int v21; // [rsp+78h] [rbp-140h]
  int v22; // [rsp+7Ch] [rbp-13Ch]
  int v23; // [rsp+80h] [rbp-138h]
  char v24[96]; // [rsp+88h] [rbp-130h] BYREF
  int v25; // [rsp+E8h] [rbp-D0h]
  void **v26; // [rsp+F0h] [rbp-C8h] BYREF
  HRESULT v27; // [rsp+F8h] [rbp-C0h]
  unsigned int v28; // [rsp+11Ch] [rbp-9Ch]

  v16 = v20;
  v20[0] = L"base\\fs\\fsrm\\service\\classmanager\\classmanager.cpp";
  v20[1] = L"CClassManager::FinalConstruct";
  v20[2] = L"SRMCLSCC";
  v21 = 2374;
  v22 = 21;
  v23 = 255;
  v25 = 0x1000000;
  memset_0(v24, 0, sizeof(v24));
  CSrmFunctionTracer::CSrmFunctionTracer(&v26, v20, 0);
  try
  {
    v2 = (IUnknown **)(this + 14);
    Instance = CoCreateInstance(
                 &CLSID_FsrmClassificationManagerService,
                 0,
                 4u,
                 &IID_IFsrmClassificationManager2,
                 this + 14);
    LODWORD(ppv) = Instance;
    CSrmFunctionTracer::Trace(
      (CSrmFunctionTracer *)&v26,
      0x8Cu,
      0x954u,
      L"Creating CLSID_FsrmClassificationManagerService returned 0x%08lx",
      ppv);
    if ( (int)(Instance + 0x80000000) >= 0 && Instance != -2147221164 )
    {
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v26, Instance);
      Hr = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v26);
      CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v26, 0x956u, Hr, 0);
    }
    v27 = 0;
    if ( Instance >= 0 )
    {
      v4 = CoSetProxyBlanket(*v2, 0xFFFFFFFF, 0xFFFFFFFF, 0, 0, 3u, 0, 0);
      v27 = v4;
      if ( v4 < 0 )
      {
        v11 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v26);
        CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v26, v11);
        v12 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v26);
        CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v26, 0x969u, v12, 0);
      }
      v27 = v4;
      v16 = 0;
      v5 = ATL::CComObject<CSrmSink<CClassManager,&__s_GUID const _GUID_26942db0_dabf_41d8_bbdd_b129a9f70424>>::CreateInstance(&v16);
      v27 = v5;
      if ( v5 < 0 )
      {
        v13 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v26);
        CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v26, v13);
        v14 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v26);
        CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v26, 0x970u, v14, 0);
      }
      v27 = v5;
      v6 = v16;
      if ( v16 )
        (*(void (__fastcall **)(_QWORD *))(*v16 + 8LL))(v16);
      CSrmSink<CClassManager,&__s_GUID const _GUID_26942db0_dabf_41d8_bbdd_b129a9f70424>::Subscribe(v6, *v2, this);
      v7 = this + 15;
      if ( (_QWORD *)*v7 != v6 && v7 )
      {
        if ( v6 )
          (*(void (__fastcall **)(_QWORD *))(*v6 + 8LL))(v6);
        if ( *v7 )
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v7 + 16LL))(*v7);
        *v7 = v6;
      }
      if ( v6 )
        (*(void (__fastcall **)(_QWORD *))(*v6 + 16LL))(v6);
    }
    CClassManager::ReleaseClientPipeline(0);
  }
  catch ( long v17 )
  {
    CSrmFunctionTracer::HandleHresultException(
      (CSrmFunctionTracer *)&v26,
      v17,
      L"base\\fs\\fsrm\\service\\classmanager\\classmanager.cpp",
      L"SRMCLSCC",
      L"CClassManager::FinalConstruct",
      0x97Au,
      v28);
  }
  catch ( _com_error *v18 )
  {
    CSrmFunctionTracer::HandleComException(
      (CSrmFunctionTracer *)&v26,
      v18,
      L"base\\fs\\fsrm\\service\\classmanager\\classmanager.cpp",
      L"SRMCLSCC",
      L"CClassManager::FinalConstruct",
      0x97Au,
      v28);
  }
  catch ( std::bad_alloc )
  {
    CSrmFunctionTracer::HandleStdBadAllocException(
      (CSrmFunctionTracer *)&v26,
      L"base\\fs\\fsrm\\service\\classmanager\\classmanager.cpp",
      L"SRMCLSCC",
      L"CClassManager::FinalConstruct",
      0x97Au,
      v28);
  }
  catch ( const exception *v19 )
  {
    CSrmFunctionTracer::HandleStdGenericException(
      (CSrmFunctionTracer *)&v26,
      v19,
      L"base\\fs\\fsrm\\service\\classmanager\\classmanager.cpp",
      L"SRMCLSCC",
      L"CClassManager::FinalConstruct",
      0x97Au,
      v28);
  }
  v2 = (IUnknown **)(this + 14);
  Instance = CoCreateInstance(
               &CLSID_FsrmClassificationManagerService,
               0,
               4u,
               &IID_IFsrmClassificationManager2,
               this + 14);
  LODWORD(ppv) = Instance;
  CSrmFunctionTracer::Trace(
    (CSrmFunctionTracer *)&v26,
    0x8Cu,
    0x954u,
    L"Creating CLSID_FsrmClassificationManagerService returned 0x%08lx",
    ppv);
}

```

## disassembly

```asm
0x1800672d4  mov     [rsp+arg_8], rbx
0x1800672d9  mov     [rsp+arg_10], rsi
0x1800672de  push    rdi
0x1800672df  sub     rsp, 1B0h
0x1800672e6  mov     rax, cs:__security_cookie
0x1800672ed  xor     rax, rsp
0x1800672f0  mov     [rsp+1B8h+var_18], rax
0x1800672f8  mov     rdi, rcx
0x1800672fb  lea     rax, [rsp+1B8h+var_158]
0x180067300  mov     [rsp+1B8h+var_178], rax
0x180067305  lea     rax, aBaseFsFsrmServ_24; "base\\fs\\fsrm\\service\\classmanager\\"...
0x18006730c  mov     [rsp+1B8h+var_158], rax
0x180067311  lea     rax, aCclassmanagerF; "CClassManager::FinalConstruct"
0x180067318  mov     [rsp+1B8h+var_150], rax
0x18006731d  lea     rax, aSrmclscc; "SRMCLSCC"
0x180067324  mov     [rsp+1B8h+var_148], rax
0x180067329  mov     [rsp+1B8h+var_140], 946h
0x180067331  mov     [rsp+1B8h+var_13C], 15h
0x180067339  mov     [rsp+1B8h+var_138], 0FFh
0x180067344  mov     [rsp+1B8h+var_D0], 1000000h
0x18006734f  xor     edx, edx; Val
0x180067351  lea     r8d, [rdx+60h]; Size
0x180067355  lea     rcx, [rsp+1B8h+var_130]; void *
0x18006735d  call    memset_0
0x180067362  nop
0x180067363  xor     r8d, r8d
0x180067366  lea     rdx, [rsp+1B8h+var_158]
0x18006736b  lea     rcx, [rsp+1B8h+var_C8]
0x180067373  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x180067378  nop
0x180067379  lea     rsi, [rdi+70h]
0x18006737d  mov     [rsp+1B8h+ppv], rsi; ppv
0x180067382  lea     r9, IID_IFsrmClassificationManager2; riid
0x180067389  xor     edx, edx; pUnkOuter
0x18006738b  lea     r8d, [rdx+4]; dwClsContext
0x18006738f  lea     rcx, CLSID_FsrmClassificationManagerService; rclsid
0x180067396  call    cs:__imp_CoCreateInstance
0x18006739c  mov     ebx, eax
0x18006739e  mov     dword ptr [rsp+1B8h+ppv], eax
0x1800673a2  lea     r9, aCreatingClsidF; "Creating CLSID_FsrmClassificationManage"...
0x1800673a9  mov     edx, 8Ch; unsigned int
0x1800673ae  mov     r8d, 954h; unsigned int
0x1800673b4  lea     rcx, [rsp+1B8h+var_C8]; this
0x1800673bc  call    ?Trace@CSrmFunctionTracer@@QEAAXKKPEBGZZ; CSrmFunctionTracer::Trace(ulong,ulong,ushort const *,...)
0x1800673c1  mov     ecx, [rsp+1B8h+var_C0]
0x1800673c8  mov     [rsp+1B8h+var_C0], ecx
0x1800673cf  mov     eax, 80000000h
0x1800673d4  lea     ecx, [rbx+rax]
0x1800673d7  test    eax, ecx
0x1800673d9  jnz     short loc_1800673E7
0x1800673db  cmp     ebx, 80040154h
0x1800673e1  jnz     loc_18006753E
0x1800673e7  mov     [rsp+1B8h+var_C0], 0
0x1800673f2  test    ebx, ebx
0x1800673f4  js      loc_1800674E6
0x1800673fa  mov     [rsp+1B8h+dwCapabilities], 0; dwCapabilities
0x180067402  mov     [rsp+1B8h+pAuthInfo], 0; pAuthInfo
0x18006740b  mov     [rsp+1B8h+dwImpLevel], 3; dwImpLevel
0x180067413  mov     dword ptr [rsp+1B8h+ppv], 0; dwAuthnLevel
0x18006741b  xor     r9d, r9d; pServerPrincName
0x18006741e  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x180067421  mov     r8d, edx; dwAuthzSvc
0x180067424  mov     rcx, [rsi]; pProxy
0x180067427  call    cs:__imp_CoSetProxyBlanket
0x18006742d  mov     [rsp+1B8h+var_C0], eax
0x180067434  test    eax, eax
0x180067436  js      loc_180067572
0x18006743c  mov     [rsp+1B8h+var_C0], eax
0x180067443  mov     [rsp+1B8h+var_178], 0
0x18006744c  lea     rcx, [rsp+1B8h+var_178]
0x180067451  call    ?CreateInstance@?$CComObject@V?$CSrmSink@VCClassManager@@$1?_GUID_26942db0_dabf_41d8_bbdd_b129a9f70424@@3U__s_GUID@@B@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CSrmSink<CClassManager,&__s_GUID const _GUID_26942db0_dabf_41d8_bbdd_b129a9f70424>>::CreateInstance(ATL::CComObject<CSrmSink<CClassManager,&__s_GUID const _GUID_26942db0_dabf_41d8_bbdd_b129a9f70424>> * *)
0x180067456  mov     [rsp+1B8h+var_C0], eax
0x18006745d  test    eax, eax
0x18006745f  js      loc_1800675B3
0x180067465  mov     [rsp+1B8h+var_C0], eax
0x18006746c  mov     rbx, [rsp+1B8h+var_178]
0x180067471  mov     [rsp+1B8h+var_178], rbx
0x180067476  test    rbx, rbx
0x180067479  jz      short loc_18006748B
0x18006747b  mov     rax, [rbx]
0x18006747e  mov     rcx, rbx
0x180067481  mov     rax, [rax+8]
0x180067485  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006748a  nop
0x18006748b  mov     r8, rdi
0x18006748e  mov     rdx, [rsi]
0x180067491  mov     rcx, rbx
0x180067494  call    ?Subscribe@?$CSrmSink@VCClassManager@@$1?_GUID_26942db0_dabf_41d8_bbdd_b129a9f70424@@3U__s_GUID@@B@@QEAAXPEAUIUnknown@@PEAVCClassManager@@@Z; CSrmSink<CClassManager,&__s_GUID const _GUID_26942db0_dabf_41d8_bbdd_b129a9f70424>::Subscribe(IUnknown *,CClassManager *)
0x180067499  add     rdi, 78h ; 'x'
0x18006749d  cmp     [rdi], rbx
0x1800674a0  jz      short loc_1800674D2
0x1800674a2  test    rdi, rdi
0x1800674a5  jz      short loc_1800674D2
0x1800674a7  test    rbx, rbx
0x1800674aa  jz      short loc_1800674BB
0x1800674ac  mov     rax, [rbx]
0x1800674af  mov     rcx, rbx
0x1800674b2  mov     rax, [rax+8]
0x1800674b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800674bb  mov     rcx, [rdi]
0x1800674be  test    rcx, rcx
0x1800674c1  jz      short loc_1800674CF
0x1800674c3  mov     rax, [rcx]
0x1800674c6  mov     rax, [rax+10h]
0x1800674ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800674cf  mov     [rdi], rbx
0x1800674d2  test    rbx, rbx
0x1800674d5  jz      short loc_1800674E6
0x1800674d7  mov     rax, [rbx]
0x1800674da  mov     rcx, rbx
0x1800674dd  mov     rax, [rax+10h]
0x1800674e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800674e6  xor     ecx, ecx; bool
0x1800674e8  call    ?ReleaseClientPipeline@CClassManager@@CAX_N@Z; CClassManager::ReleaseClientPipeline(bool)
0x1800674ed  nop
0x1800674ee  mov     ebx, [rsp+1B8h+var_C0]
0x1800674f5  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x1800674fc  mov     [rsp+1B8h+var_C8], rax
0x180067504  lea     rcx, [rsp+1B8h+var_C8]; this
0x18006750c  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x180067511  mov     eax, ebx
0x180067513  mov     rcx, [rsp+1B8h+var_18]
0x18006751b  xor     rcx, rsp; StackCookie
0x18006751e  call    __security_check_cookie
0x180067523  lea     r11, [rsp+1B8h+var_8]
0x18006752b  mov     rbx, [r11+18h]
0x18006752f  mov     rsi, [r11+20h]
0x180067533  mov     rsp, r11
0x180067536  pop     rdi
0x180067537  retn
0x180067538  jmp     short loc_1800674EE
0x18006753a  jmp     short loc_1800674EE
0x18006753c  jmp     short loc_1800674EE
0x18006753e  mov     edx, ebx; int
0x180067540  lea     rcx, [rsp+1B8h+var_C8]; this
0x180067548  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x18006754d  lea     rcx, [rsp+1B8h+var_C8]; this
0x180067555  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18006755a  mov     r8d, eax; char
0x18006755d  xor     r9d, r9d; unsigned __int16 *
0x180067560  mov     edx, 956h; unsigned int
0x180067565  lea     rcx, [rsp+1B8h+var_C8]; this
0x18006756d  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
0x180067572  lea     rcx, [rsp+1B8h+var_C8]; this
0x18006757a  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18006757f  mov     edx, eax; int
0x180067581  lea     rcx, [rsp+1B8h+var_C8]; this
0x180067589  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x18006758e  lea     rcx, [rsp+1B8h+var_C8]; this
0x180067596  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18006759b  mov     r8d, eax; char
0x18006759e  xor     r9d, r9d; unsigned __int16 *
0x1800675a1  mov     edx, 969h; unsigned int
0x1800675a6  lea     rcx, [rsp+1B8h+var_C8]; this
0x1800675ae  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
0x1800675b3  lea     rcx, [rsp+1B8h+var_C8]; this
0x1800675bb  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x1800675c0  mov     edx, eax; int
0x1800675c2  lea     rcx, [rsp+1B8h+var_C8]; this
0x1800675ca  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x1800675cf  lea     rcx, [rsp+1B8h+var_C8]; this
0x1800675d7  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x1800675dc  mov     r8d, eax; char
0x1800675df  xor     r9d, r9d; unsigned __int16 *
0x1800675e2  mov     edx, 970h; unsigned int
0x1800675e7  lea     rcx, [rsp+1B8h+var_C8]; this
0x1800675ef  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
```
