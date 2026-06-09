# CWcnPageApTest::~CWcnPageApTest(void)

- ea: `0x180019a50`
- end: `0x180019aaa`
- name: `??1CWcnPageApTest@@UEAA@XZ`
- size: `90`
- prototype: `void __fastcall(CWcnPageApTest *__hidden this)`
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180003034`
- `0x180003530`
- `0x18000425c`

## callees

- `0x180003abc`
- `0x180003b58`
- `0x180019d3c`
- `0x180019fc0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180019a65`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180019a65`

## pseudocode

```c
void __fastcall CWcnPageApTest::~CWcnPageApTest(CWcnPageApTest *this)
{
  CWcnPageApTest::CancelBackgroundWork(this);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 408));
  ATL::CComPtrBase<IWCNDevicePrivate>::~CComPtrBase<IWCNDevicePrivate>((char *)this + 392);
  ATL::CComPtrBase<IWCNDevicePrivate>::~CComPtrBase<IWCNDevicePrivate>((char *)this + 384);
  Microsoft::WRL::ComPtr<IWCNDiscoveryProvider>::InternalRelease((char *)this + 376);
  *((_QWORD *)this + 43) = &CXWizardDUIBaseClass::`vftable';
  CXWizardPageWTLBaseClass<1570,CWcnPageCFEPin,&_GUID const CLSID_WcnPageCFEPin,0,700,0,0,0,0,0>::~CXWizardPageWTLBaseClass<1570,CWcnPageCFEPin,&_GUID const CLSID_WcnPageCFEPin,0,700,0,0,0,0,0>(this);
}

```

## disassembly

```asm
0x180019a50  push    rbx
0x180019a52  sub     rsp, 20h
0x180019a56  mov     rbx, rcx
0x180019a59  call    ?CancelBackgroundWork@CWcnPageApTest@@AEAAXXZ; CWcnPageApTest::CancelBackgroundWork(void)
0x180019a5e  lea     rcx, [rbx+198h]; lpCriticalSection
0x180019a65  call    cs:__imp_DeleteCriticalSection
0x180019a6b  lea     rcx, [rbx+188h]
0x180019a72  call    ??1?$CComPtrBase@UIWCNDevicePrivate@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IWCNDevicePrivate>::~CComPtrBase<IWCNDevicePrivate>(void)
0x180019a77  lea     rcx, [rbx+180h]
0x180019a7e  call    ??1?$CComPtrBase@UIWCNDevicePrivate@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IWCNDevicePrivate>::~CComPtrBase<IWCNDevicePrivate>(void)
0x180019a83  lea     rcx, [rbx+178h]
0x180019a8a  call    ?InternalRelease@?$ComPtr@UIWCNDiscoveryProvider@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IWCNDiscoveryProvider>::InternalRelease(void)
0x180019a8f  lea     rax, ??_7CXWizardDUIBaseClass@@6B@; const CXWizardDUIBaseClass::`vftable'
0x180019a96  mov     [rbx+158h], rax
0x180019a9d  mov     rcx, rbx
0x180019aa0  add     rsp, 20h
0x180019aa4  pop     rbx
0x180019aa5  jmp     ??1?$CXWizardPageWTLBaseClass@$0GCC@VCWcnPageCFEPin@@$1?CLSID_WcnPageCFEPin@@3U_GUID@@B$0A@$0CLM@$0A@$0A@$0A@$0A@$0A@@@UEAA@XZ; CXWizardPageWTLBaseClass<1570,CWcnPageCFEPin,&_GUID const CLSID_WcnPageCFEPin,0,700,0,0,0,0,0>::~CXWizardPageWTLBaseClass<1570,CWcnPageCFEPin,&_GUID const CLSID_WcnPageCFEPin,0,700,0,0,0,0,0>(void)
```
