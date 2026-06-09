# CWLIDFDProv::~CWLIDFDProv(void)

- ea: `0x18000579c`
- end: `0x1800057d4`
- name: `??1CWLIDFDProv@@UEAA@XZ`
- size: `56`
- prototype: `void __fastcall(CWLIDFDProv *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180005408`
- `0x18000544c`
- `0x1800058b0`

## callees

- `0x180003728`
- `0x18000576c`
- `0x180006410`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800057c0`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800057c0`

## pseudocode

```c
void __fastcall CWLIDFDProv::~CWLIDFDProv(CWLIDFDProv *this)
{
  CWLIDFDProv::EndQuery(this);
  ATL::CComPtrBase<IFunctionInstanceCollection>::~CComPtrBase<IFunctionInstanceCollection>((__int64 *)this + 14);
  ATL::CComPtrBase<IFunctionInstanceCollection>::~CComPtrBase<IFunctionInstanceCollection>((__int64 *)this + 13);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection((CWLIDFDProv *)((char *)this + 16));
}

```

## disassembly

```asm
0x18000579c  push    rbx
0x18000579e  sub     rsp, 20h
0x1800057a2  mov     rbx, rcx
0x1800057a5  call    ?EndQuery@CWLIDFDProv@@UEAAJXZ; CWLIDFDProv::EndQuery(void)
0x1800057aa  lea     rcx, [rbx+70h]
0x1800057ae  call    ??1?$CComPtrBase@UIFunctionInstanceCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IFunctionInstanceCollection>::~CComPtrBase<IFunctionInstanceCollection>(void)
0x1800057b3  lea     rcx, [rbx+68h]
0x1800057b7  call    ??1?$CComPtrBase@UIFunctionInstanceCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IFunctionInstanceCollection>::~CComPtrBase<IFunctionInstanceCollection>(void)
0x1800057bc  lea     rcx, [rbx+40h]; lpCriticalSection
0x1800057c0  call    cs:__imp_DeleteCriticalSection
0x1800057c6  lea     rcx, [rbx+10h]; this
0x1800057ca  add     rsp, 20h
0x1800057ce  pop     rbx
0x1800057cf  jmp     ??1CComSafeDeleteCriticalSection@ATL@@QEAA@XZ; ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(void)
```
