# CUxpUIWrapper_Remote::InitializeWlidUx(void)

- ea: `0x18003bd60`
- end: `0x18003be84`
- name: `?InitializeWlidUx@CUxpUIWrapper_Remote@@MEAAJXZ`
- size: `292`
- prototype: `__int64 __fastcall(CUxpUIWrapper_Remote *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000c354`
- `0x18000cc9c`
- `0x18000e870`
- `0x18003aec8`
- `0x18003bd60`
- `0x180053890`
- `0x180063010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003bdf0`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003bdf0`

## string_xrefs

- `0x18003bdfd`: `hr = ::CoCreateInstance( CLSID_UIWrapper, NULL, ::CLSCTX_LOCAL_SERVER|::CLSCTX_ACTIVATE_32_BIT_SERVER, IID_IUIWrapper, (void**)&m_spComUIWrapper )`
- `0x18003be47`: `hr = m_spComUIWrapper->CoInitializeUXPlatform()`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CUxpUIWrapper_Remote::InitializeWlidUx(CUxpUIWrapper_Remote *this)
{
  _QWORD *v2; // rdi
  HRESULT Instance; // eax
  int v4; // eax
  unsigned int v5; // ebx
  LPVOID *ppv; // [rsp+20h] [rbp-48h]
  _BYTE v8[16]; // [rsp+30h] [rbp-38h] BYREF
  _QWORD v9[5]; // [rsp+40h] [rbp-28h] BYREF
  int v10; // [rsp+90h] [rbp+28h] BYREF

  v10 = 0;
  ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::CComCritSecLock<ATL::CComAutoCriticalSection>(
    (__int64)v8,
    (struct _RTL_CRITICAL_SECTION *)((char *)this + 88));
  v9[0] = "CUxpUIWrapper_Remote::InitializeWlidUx";
  v9[1] = &v10;
  v9[2] = 0;
  v9[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"clientcore\\ds\\ext\\live\\identity\\api\\classic\\uxpuiwrapper.cpp",
    "CUxpUIWrapper_Remote::InitializeWlidUx",
    (const char *)0x53D,
    0,
    (const unsigned __int16 *)ppv);
  if ( !*((_BYTE *)this + 128) )
  {
    v2 = (_QWORD *)((char *)this + 136);
    Instance = CoCreateInstance(&CLSID_UIWrapper, 0, 0x40004u, &IID_IUIWrapper, (LPVOID *)this + 17);
    v10 = Instance;
    if ( Instance >= 0 )
    {
      if ( *v2 )
      {
        v4 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v2 + 40LL))(*v2);
        v10 = v4;
        if ( v4 >= 0 )
          *((_BYTE *)this + 128) = 1;
        else
          Telemetry::IfFailExit(
            "clientcore\\ds\\ext\\live\\identity\\api\\classic\\uxpuiwrapper.cpp",
            "CUxpUIWrapper_Remote::InitializeWlidUx",
            0x55Eu,
            v4,
            "hr = m_spComUIWrapper->CoInitializeUXPlatform()");
      }
      else
      {
        v10 = -2147418113;
      }
    }
    else
    {
      Telemetry::IfFailExit(
        "clientcore\\ds\\ext\\live\\identity\\api\\classic\\uxpuiwrapper.cpp",
        "CUxpUIWrapper_Remote::InitializeWlidUx",
        0x553u,
        Instance,
        "hr = ::CoCreateInstance( CLSID_UIWrapper, NULL, ::CLSCTX_LOCAL_SERVER|::CLSCTX_ACTIVATE_32_BIT_SERVER, IID_IUIWr"
        "apper, (void**)&m_spComUIWrapper )");
    }
  }
  v5 = v10;
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v9);
  CComCritSecLockWTry<CComAutoCriticalSectionWTry>::~CComCritSecLockWTry<CComAutoCriticalSectionWTry>((__int64)v8);
  return v5;
}

```

## disassembly

```asm
0x18003bd60  push    rbp
0x18003bd62  push    rbx
0x18003bd63  push    rdi
0x18003bd64  push    r14
0x18003bd66  mov     rbp, rsp
0x18003bd69  sub     rsp, 68h
0x18003bd6d  mov     rbx, rcx
0x18003bd70  mov     [rbp+arg_0], 0
0x18003bd77  lea     rdx, [rcx+58h]
0x18003bd7b  lea     rcx, [rbp+var_38]
0x18003bd7f  call    ??0?$CComCritSecLock@VCComAutoCriticalSection@ATL@@@ATL@@QEAA@AEAVCComAutoCriticalSection@1@_N@Z; ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::CComCritSecLock<ATL::CComAutoCriticalSection>(ATL::CComAutoCriticalSection &,bool)
0x18003bd84  nop
0x18003bd85  lea     r14, aCuxpuiwrapperR_1; "CUxpUIWrapper_Remote::InitializeWlidUx"
0x18003bd8c  mov     [rbp+var_28], r14
0x18003bd90  lea     rax, [rbp+arg_0]
0x18003bd94  mov     [rbp+var_20], rax
0x18003bd98  mov     [rbp+var_18], 0
0x18003bda0  mov     [rbp+var_10], 0
0x18003bda8  xor     r9d, r9d; unsigned int
0x18003bdab  mov     r8d, 53Dh; char *
0x18003bdb1  mov     rdx, r14; char *
0x18003bdb4  lea     rcx, aClientcoreDsEx_7; "clientcore\\ds\\ext\\live\\identity\\ap"...
0x18003bdbb  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x18003bdc0  nop
0x18003bdc1  cmp     byte ptr [rbx+80h], 0
0x18003bdc8  jnz     loc_18003BE62
0x18003bdce  lea     rdi, [rbx+88h]
0x18003bdd5  mov     [rsp+68h+ppv], rdi; ppv
0x18003bdda  lea     r9, IID_IUIWrapper; riid
0x18003bde1  xor     edx, edx; pUnkOuter
0x18003bde3  mov     r8d, 40004h; dwClsContext
0x18003bde9  lea     rcx, CLSID_UIWrapper; rclsid
0x18003bdf0  call    cs:__imp_CoCreateInstance
0x18003bdf6  mov     [rbp+arg_0], eax
0x18003bdf9  test    eax, eax
0x18003bdfb  jns     short loc_18003BE23
0x18003bdfd  lea     r8, aHrCocreateinst; "hr = ::CoCreateInstance( CLSID_UIWrappe"...
0x18003be04  mov     [rsp+68h+ppv], r8; char *
0x18003be09  mov     r8d, 553h; unsigned int
0x18003be0f  mov     r9d, eax; int
0x18003be12  mov     rdx, r14; char *
0x18003be15  lea     rcx, aClientcoreDsEx_7; "clientcore\\ds\\ext\\live\\identity\\ap"...
0x18003be1c  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x18003be21  jmp     short loc_18003BE62
0x18003be23  mov     rcx, [rdi]
0x18003be26  test    rcx, rcx
0x18003be29  jnz     short loc_18003BE34
0x18003be2b  mov     [rbp+arg_0], 8000FFFFh
0x18003be32  jmp     short loc_18003BE62
0x18003be34  mov     rax, [rcx]
0x18003be37  mov     rax, [rax+28h]
0x18003be3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003be40  mov     [rbp+arg_0], eax
0x18003be43  test    eax, eax
0x18003be45  jns     short loc_18003BE5B
0x18003be47  lea     rcx, aHrMSpcomuiwrap_2; "hr = m_spComUIWrapper->CoInitializeUXPl"...
0x18003be4e  mov     [rsp+68h+ppv], rcx
0x18003be53  mov     r8d, 55Eh
0x18003be59  jmp     short loc_18003BE0F
0x18003be5b  mov     byte ptr [rbx+80h], 1
0x18003be62  mov     ebx, [rbp+arg_0]
0x18003be65  lea     rcx, [rbp+var_28]
0x18003be69  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x18003be6e  nop
0x18003be6f  lea     rcx, [rbp+var_38]
0x18003be73  call    ??1?$CComCritSecLockWTry@VCComAutoCriticalSectionWTry@@@@QEAA@XZ; CComCritSecLockWTry<CComAutoCriticalSectionWTry>::~CComCritSecLockWTry<CComAutoCriticalSectionWTry>(void)
0x18003be78  mov     eax, ebx
0x18003be7a  add     rsp, 68h
0x18003be7e  pop     r14
0x18003be80  pop     rdi
0x18003be81  pop     rbx
0x18003be82  pop     rbp
0x18003be83  retn
```
