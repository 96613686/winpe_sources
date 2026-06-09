# CWcnPageProfileCreateNew::~CWcnPageProfileCreateNew(void)

- ea: `0x18001405c`
- end: `0x1800140ae`
- name: `??1CWcnPageProfileCreateNew@@QEAA@XZ`
- size: `82`
- prototype: `void __fastcall(CWcnPageProfileCreateNew *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800032a4`
- `0x180003830`

## callees

- `0x180003abc`
- `0x180003b18`
- `0x18001405c`
- `0x18001d718`

## import_xrefs

- `GDI32!DeleteObject` at `0x180014071`
- `GDI32!DeleteObject` at `0x180014083`
- `GDI32!DeleteObject` at `0x180014071`
- `GDI32!DeleteObject` at `0x180014083`

## pseudocode

```c
void __fastcall CWcnPageProfileCreateNew::~CWcnPageProfileCreateNew(CWcnPageProfileCreateNew *this)
{
  void *v2; // rcx
  void *v3; // rcx

  v2 = (void *)*((_QWORD *)this + 28);
  if ( v2 )
    DeleteObject(v2);
  v3 = (void *)*((_QWORD *)this + 29);
  if ( v3 )
    DeleteObject(v3);
  ATL::CComPtrBase<IWCNDevicePrivate>::~CComPtrBase<IWCNDevicePrivate>((char *)this + 288);
  CWcnToggleButton::~CWcnToggleButton((CWcnPageProfileCreateNew *)((char *)this + 240));
  CXWizardPageClass<CWcnPageProfileUseExisting,&_GUID const CLSID_WcnPageProfileUseExisting,0>::~CXWizardPageClass<CWcnPageProfileUseExisting,&_GUID const CLSID_WcnPageProfileUseExisting,0>(this);
}

```

## disassembly

```asm
0x18001405c  push    rbx
0x18001405e  sub     rsp, 20h
0x180014062  mov     rbx, rcx
0x180014065  mov     rcx, [rcx+0E0h]; ho
0x18001406c  test    rcx, rcx
0x18001406f  jz      short loc_180014077
0x180014071  call    cs:__imp_DeleteObject
0x180014077  mov     rcx, [rbx+0E8h]; ho
0x18001407e  test    rcx, rcx
0x180014081  jz      short loc_180014089
0x180014083  call    cs:__imp_DeleteObject
0x180014089  lea     rcx, [rbx+120h]
0x180014090  call    ??1?$CComPtrBase@UIWCNDevicePrivate@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IWCNDevicePrivate>::~CComPtrBase<IWCNDevicePrivate>(void)
0x180014095  lea     rcx, [rbx+0F0h]; this
0x18001409c  call    ??1CWcnToggleButton@@QEAA@XZ; CWcnToggleButton::~CWcnToggleButton(void)
0x1800140a1  mov     rcx, rbx
0x1800140a4  add     rsp, 20h
0x1800140a8  pop     rbx
0x1800140a9  jmp     ??1?$CXWizardPageClass@VCWcnPageProfileUseExisting@@$1?CLSID_WcnPageProfileUseExisting@@3U_GUID@@B$0A@@@QEAA@XZ; CXWizardPageClass<CWcnPageProfileUseExisting,&_GUID const CLSID_WcnPageProfileUseExisting,0>::~CXWizardPageClass<CWcnPageProfileUseExisting,&_GUID const CLSID_WcnPageProfileUseExisting,0>(void)
```
