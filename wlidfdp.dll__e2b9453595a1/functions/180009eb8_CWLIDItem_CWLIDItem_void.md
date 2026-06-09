# CWLIDItem::~CWLIDItem(void)

- ea: `0x180009eb8`
- end: `0x180009f0d`
- name: `??1CWLIDItem@@UEAA@XZ`
- size: `85`
- prototype: `void __fastcall(CWLIDItem *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000a080`

## callees

- `0x180003728`
- `0x180008534`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180009f06`

## pseudocode

```c
void __fastcall CWLIDItem::~CWLIDItem(CWLIDItem *this)
{
  *(_QWORD *)this = &CWLIDItem::`vftable';
  ATL::CStringData::Release((ATL::CStringData *)(*((_QWORD *)this + 11) - 24LL));
  ATL::CComPtrBase<IFunctionInstanceCollection>::~CComPtrBase<IFunctionInstanceCollection>((__int64 *)this + 10);
  ATL::CComPtrBase<IFunctionInstanceCollection>::~CComPtrBase<IFunctionInstanceCollection>((__int64 *)this + 9);
  ATL::CComPtrBase<IFunctionInstanceCollection>::~CComPtrBase<IFunctionInstanceCollection>((__int64 *)this + 8);
  *(_QWORD *)this = &CRefCounted::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
}

```

## disassembly

```asm
0x180009eb8  push    rbx
0x180009eba  sub     rsp, 20h
0x180009ebe  mov     rbx, rcx
0x180009ec1  lea     rax, ??_7CWLIDItem@@6B@; const CWLIDItem::`vftable'
0x180009ec8  mov     [rcx], rax
0x180009ecb  mov     rcx, [rcx+58h]
0x180009ecf  sub     rcx, 18h; this
0x180009ed3  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180009ed8  lea     rcx, [rbx+50h]
0x180009edc  call    ??1?$CComPtrBase@UIFunctionInstanceCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IFunctionInstanceCollection>::~CComPtrBase<IFunctionInstanceCollection>(void)
0x180009ee1  lea     rcx, [rbx+48h]
0x180009ee5  call    ??1?$CComPtrBase@UIFunctionInstanceCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IFunctionInstanceCollection>::~CComPtrBase<IFunctionInstanceCollection>(void)
0x180009eea  lea     rcx, [rbx+40h]
0x180009eee  call    ??1?$CComPtrBase@UIFunctionInstanceCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IFunctionInstanceCollection>::~CComPtrBase<IFunctionInstanceCollection>(void)
0x180009ef3  lea     rax, ??_7CRefCounted@@6B@; const CRefCounted::`vftable'
0x180009efa  lea     rcx, [rbx+10h]
0x180009efe  mov     [rbx], rax
0x180009f01  add     rsp, 20h
0x180009f05  pop     rbx
0x180009f06  jmp     cs:__imp_DeleteCriticalSection
```
