# CVssHardwareProviderWrapper::~CVssHardwareProviderWrapper(void)

- ea: `0x140087cfc`
- end: `0x140087e9b`
- name: `??1CVssHardwareProviderWrapper@@QEAA@XZ`
- size: `415`
- prototype: `void __fastcall(CVssHardwareProviderWrapper *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x1400a9628`

## callees

- `0x1400088fc`
- `0x1400137c0`
- `0x140013b00`
- `0x140018130`
- `0x1400514c0`
- `0x140087cfc`
- `0x140087ea4`
- `0x1400921dc`
- `0x1400a9654`
- `0x1400b1304`
- `0x1400b1e18`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140087dd2`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140087de4`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140087dd2`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140087de4`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140087e3e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140087e71`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140087e83`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140087e3e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140087e71`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140087e83`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140087d93`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140087d93`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CVssHardwareProviderWrapper::~CVssHardwareProviderWrapper(CVssHardwareProviderWrapper *this)
{
  void *v2; // rcx
  unsigned int v3; // edx
  VSS_SNAPSHOT_SET_LIST *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx
  _QWORD v7[3]; // [rsp+20h] [rbp-E0h] BYREF
  int v8; // [rsp+38h] [rbp-C8h]
  int v9; // [rsp+3Ch] [rbp-C4h]
  int v10; // [rsp+40h] [rbp-C0h]
  _BYTE v11[120]; // [rsp+48h] [rbp-B8h] BYREF
  int v12; // [rsp+C0h] [rbp-40h]
  LPVOID v13[14]; // [rsp+D0h] [rbp-30h] BYREF

  *(_QWORD *)this = &CVssHardwareProviderWrapper::`vftable';
  v7[0] = L"base\\stor\\vss\\modules\\coord\\src\\hardwrp.cxx";
  v7[1] = L"CVssHardwareProviderWrapper::~CVssHardwareProviderWrapper";
  v7[2] = L"CORHWPWC";
  v8 = 135;
  v9 = 1;
  v10 = 255;
  v12 = 0x1000000;
  memset_0(v11, 0, sizeof(v11));
  CVssFunctionTracer::CVssFunctionTracer((__int64)v13, (__int64)v7, 0);
  CVssHardwareProviderWrapper::DeleteCachedInfo(this);
  v2 = (void *)*((_QWORD *)this + 25);
  if ( v2 )
    CloseHandle(v2);
  CVssHardwareProviderWrapper::TrySaveData(this);
  while ( 1 )
  {
    v4 = (VSS_SNAPSHOT_SET_LIST *)*((_QWORD *)this + 22);
    if ( !v4 )
      break;
    *((_QWORD *)this + 22) = *(_QWORD *)v4;
    VSS_SNAPSHOT_SET_LIST::`scalar deleting destructor'(v4, v3);
  }
  CVssHardwareProviderWrapper::RemoveFromGlobalList(this);
  v5 = (void *)*((_QWORD *)this + 43);
  if ( v5 )
    free(v5);
  v6 = (void *)*((_QWORD *)this + 44);
  if ( v6 )
    free(v6);
  CVssFunctionTracer::~CVssFunctionTracer(v13);
  CVssDiag::~CVssDiag((CVssHardwareProviderWrapper *)((char *)this + 440));
  ATL::CComPtr<IMultiInterfacePublisherFilter>::~CComPtr<IMultiInterfacePublisherFilter>((__int64)this + 392);
  ATL::CComPtr<IMultiInterfacePublisherFilter>::~CComPtr<IMultiInterfacePublisherFilter>((__int64)this + 384);
  ATL::CComPtr<IMultiInterfacePublisherFilter>::~CComPtr<IMultiInterfacePublisherFilter>((__int64)this + 376);
  ATL::CComPtr<IMultiInterfacePublisherFilter>::~CComPtr<IMultiInterfacePublisherFilter>((__int64)this + 368);
  if ( *((_DWORD *)this + 84) == 1 )
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 296));
  ATL::CComPtr<IMultiInterfacePublisherFilter>::~CComPtr<IMultiInterfacePublisherFilter>((__int64)this + 288);
  CVssResyncMapping::~CVssResyncMapping((CVssHardwareProviderWrapper *)((char *)this + 216));
  ATL::CComPtr<IMultiInterfacePublisherFilter>::~CComPtr<IMultiInterfacePublisherFilter>((__int64)this + 112);
  if ( *((_DWORD *)this + 24) == 1 )
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
  if ( *((_DWORD *)this + 12) == 1 )
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
}

```

## disassembly

```asm
0x140087cfc  mov     [rsp-8+arg_0], rbx
0x140087d01  push    rbp
0x140087d02  lea     rbp, [rsp-40h]
0x140087d07  sub     rsp, 140h
0x140087d0e  mov     rbx, rcx
0x140087d11  lea     rax, ??_7CVssHardwareProviderWrapper@@6B@; const CVssHardwareProviderWrapper::`vftable'
0x140087d18  mov     [rcx], rax
0x140087d1b  lea     rax, aBaseStorVssMod_19; "base\\stor\\vss\\modules\\coord\\src\\h"...
0x140087d22  mov     [rsp+140h+var_120], rax
0x140087d27  lea     rax, aCvsshardwarepr_199; "CVssHardwareProviderWrapper::~CVssHardw"...
0x140087d2e  mov     [rsp+140h+var_118], rax
0x140087d33  lea     rax, aCorhwpwc; "CORHWPWC"
0x140087d3a  mov     [rsp+140h+var_110], rax
0x140087d3f  mov     [rsp+140h+var_108], 87h
0x140087d47  mov     [rsp+140h+var_104], 1
0x140087d4f  mov     [rsp+140h+var_100], 0FFh
0x140087d57  mov     [rbp+40h+var_80], 1000000h
0x140087d5e  xor     edx, edx; Val
0x140087d60  lea     r8d, [rdx+78h]; Size
0x140087d64  lea     rcx, [rsp+140h+var_F8]; void *
0x140087d69  call    memset_0
0x140087d6e  xor     r8d, r8d
0x140087d71  lea     rdx, [rsp+140h+var_120]
0x140087d76  lea     rcx, [rbp+40h+var_70]
0x140087d7a  call    ??0CVssFunctionTracer@@QEAA@UCVssDebugInfo@@QEAG@Z; CVssFunctionTracer::CVssFunctionTracer(CVssDebugInfo,ushort * const)
0x140087d7f  mov     rcx, rbx; this
0x140087d82  call    ?DeleteCachedInfo@CVssHardwareProviderWrapper@@AEAAXXZ; CVssHardwareProviderWrapper::DeleteCachedInfo(void)
0x140087d87  mov     rcx, [rbx+0C8h]; hObject
0x140087d8e  test    rcx, rcx
0x140087d91  jz      short loc_140087D99
0x140087d93  call    cs:__imp_CloseHandle
0x140087d99  mov     rcx, rbx; this
0x140087d9c  call    ?TrySaveData@CVssHardwareProviderWrapper@@AEAAXXZ; CVssHardwareProviderWrapper::TrySaveData(void)
0x140087da1  jmp     short loc_140087DB2
0x140087da3  mov     rax, [rcx]
0x140087da6  mov     [rbx+0B0h], rax
0x140087dad  call    ??_GVSS_SNAPSHOT_SET_LIST@@QEAAPEAXI@Z; VSS_SNAPSHOT_SET_LIST::`scalar deleting destructor'(uint)
0x140087db2  mov     rcx, [rbx+0B0h]; this
0x140087db9  test    rcx, rcx
0x140087dbc  jnz     short loc_140087DA3
0x140087dbe  mov     rcx, rbx; this
0x140087dc1  call    ?RemoveFromGlobalList@CVssHardwareProviderWrapper@@QEAAXXZ; CVssHardwareProviderWrapper::RemoveFromGlobalList(void)
0x140087dc6  mov     rcx, [rbx+158h]; Block
0x140087dcd  test    rcx, rcx
0x140087dd0  jz      short loc_140087DD8
0x140087dd2  call    cs:__imp_free
0x140087dd8  mov     rcx, [rbx+160h]; Block
0x140087ddf  test    rcx, rcx
0x140087de2  jz      short loc_140087DEA
0x140087de4  call    cs:__imp_free
0x140087dea  lea     rcx, [rbp+40h+var_70]; this
0x140087dee  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x140087df3  lea     rcx, [rbx+1B8h]; this
0x140087dfa  call    ??1CVssDiag@@QEAA@XZ; CVssDiag::~CVssDiag(void)
0x140087dff  lea     rcx, [rbx+188h]
0x140087e06  call    ??1?$CComPtr@UIMultiInterfacePublisherFilter@@@ATL@@QEAA@XZ; ATL::CComPtr<IMultiInterfacePublisherFilter>::~CComPtr<IMultiInterfacePublisherFilter>(void)
0x140087e0b  lea     rcx, [rbx+180h]
0x140087e12  call    ??1?$CComPtr@UIMultiInterfacePublisherFilter@@@ATL@@QEAA@XZ; ATL::CComPtr<IMultiInterfacePublisherFilter>::~CComPtr<IMultiInterfacePublisherFilter>(void)
0x140087e17  lea     rcx, [rbx+178h]
0x140087e1e  call    ??1?$CComPtr@UIMultiInterfacePublisherFilter@@@ATL@@QEAA@XZ; ATL::CComPtr<IMultiInterfacePublisherFilter>::~CComPtr<IMultiInterfacePublisherFilter>(void)
0x140087e23  lea     rcx, [rbx+170h]
0x140087e2a  call    ??1?$CComPtr@UIMultiInterfacePublisherFilter@@@ATL@@QEAA@XZ; ATL::CComPtr<IMultiInterfacePublisherFilter>::~CComPtr<IMultiInterfacePublisherFilter>(void)
0x140087e2f  lea     rcx, [rbx+128h]; lpCriticalSection
0x140087e36  mov     eax, [rcx+28h]
0x140087e39  cmp     eax, 1
0x140087e3c  jnz     short loc_140087E44
0x140087e3e  call    cs:__imp_DeleteCriticalSection
0x140087e44  lea     rcx, [rbx+120h]
0x140087e4b  call    ??1?$CComPtr@UIMultiInterfacePublisherFilter@@@ATL@@QEAA@XZ; ATL::CComPtr<IMultiInterfacePublisherFilter>::~CComPtr<IMultiInterfacePublisherFilter>(void)
0x140087e50  lea     rcx, [rbx+0D8h]; this
0x140087e57  call    ??1CVssResyncMapping@@QEAA@XZ; CVssResyncMapping::~CVssResyncMapping(void)
0x140087e5c  lea     rcx, [rbx+70h]
0x140087e60  call    ??1?$CComPtr@UIMultiInterfacePublisherFilter@@@ATL@@QEAA@XZ; ATL::CComPtr<IMultiInterfacePublisherFilter>::~CComPtr<IMultiInterfacePublisherFilter>(void)
0x140087e65  lea     rcx, [rbx+38h]; lpCriticalSection
0x140087e69  mov     eax, [rcx+28h]
0x140087e6c  cmp     eax, 1
0x140087e6f  jnz     short loc_140087E77
0x140087e71  call    cs:__imp_DeleteCriticalSection
0x140087e77  lea     rcx, [rbx+8]; lpCriticalSection
0x140087e7b  mov     eax, [rcx+28h]
0x140087e7e  cmp     eax, 1
0x140087e81  jnz     short loc_140087E8A
0x140087e83  call    cs:__imp_DeleteCriticalSection
0x140087e89  nop
0x140087e8a  mov     rbx, [rsp+140h+arg_0]
0x140087e92  add     rsp, 140h
0x140087e99  pop     rbp
0x140087e9a  retn
```
