# DataStoreClient::~DataStoreClient(void)

- ea: `0x180039628`
- end: `0x180039670`
- name: `??1DataStoreClient@@UEAA@XZ`
- size: `72`
- prototype: `void __fastcall(DataStoreClient *__hidden this)`
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180039be0`
- `0x18003d140`
- `0x180043eec`
- `0x180056531`
- `0x1800567df`

## callees

- `0x180024cac`
- `0x18002efa0`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18003965a`
- `KERNEL32!DeleteCriticalSection` at `0x18003965a`

## pseudocode

```c
void __fastcall DataStoreClient::~DataStoreClient(DataStoreClient *this)
{
  *(_QWORD *)this = &DataStoreClient::`vftable';
  _bstr_t::_Free((DataStoreClient *)((char *)this + 72));
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((char *)this + 64);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((char *)this + 56);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  *(_QWORD *)this = &IDataStoreClient::`vftable';
}

```

## disassembly

```asm
0x180039628  push    rbx
0x18003962a  sub     rsp, 20h
0x18003962e  lea     rax, ??_7DataStoreClient@@6B@; const DataStoreClient::`vftable'
0x180039635  mov     rbx, rcx
0x180039638  mov     [rcx], rax
0x18003963b  add     rcx, 48h ; 'H'; this
0x18003963f  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x180039644  lea     rcx, [rbx+40h]
0x180039648  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003964d  lea     rcx, [rbx+38h]
0x180039651  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180039656  lea     rcx, [rbx+8]; lpCriticalSection
0x18003965a  call    cs:__imp_DeleteCriticalSection
0x180039660  lea     rax, ??_7IDataStoreClient@@6B@; const IDataStoreClient::`vftable'
0x180039667  mov     [rbx], rax
0x18003966a  add     rsp, 20h
0x18003966e  pop     rbx
0x18003966f  retn
```
