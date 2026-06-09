# CWcnWfdGoTransport::~CWcnWfdGoTransport(void)

- ea: `0x18004d780`
- end: `0x18004d7f1`
- name: `??1CWcnWfdGoTransport@@UEAA@XZ`
- size: `113`
- prototype: `void __fastcall(CWcnWfdGoTransport *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18004d800`

## callees

- `0x18000d998`
- `0x18001e490`
- `0x180052b20`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004d7a5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004d7a5`

## pseudocode

```c
void __fastcall CWcnWfdGoTransport::~CWcnWfdGoTransport(CWcnWfdGoTransport *this)
{
  *(_QWORD *)this = &CWcnWfdGoTransport::`vftable'{for `IWcnTransport'};
  *((_QWORD *)this + 2) = &CWcnWfdGoTransport::`vftable'{for `IWcnSinkController'};
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 328));
  std::_Tree<std::_Tmap_traits<enum tagWCN_DATATYPE,CWcnAttributeRules::tagWCN_DATATYPE_RULE const *,std::less<enum tagWCN_DATATYPE>,std::allocator<std::pair<enum tagWCN_DATATYPE const,CWcnAttributeRules::tagWCN_DATATYPE_RULE const *>>,0>>::~_Tree<std::_Tmap_traits<enum tagWCN_DATATYPE,CWcnAttributeRules::tagWCN_DATATYPE_RULE const *,std::less<enum tagWCN_DATATYPE>,std::allocator<std::pair<enum tagWCN_DATATYPE const,CWcnAttributeRules::tagWCN_DATATYPE_RULE const *>>,0>>((char *)this + 368);
  CWcnWfdGoApiWrapper::~CWcnWfdGoApiWrapper((CWcnWfdGoTransport *)((char *)this + 192));
  CWcnMessage::Clear((CWcnWfdGoTransport *)((char *)this + 136));
  CWcnMessage::Clear((CWcnWfdGoTransport *)((char *)this + 80));
  CWcnMessage::Clear((CWcnWfdGoTransport *)((char *)this + 24));
  *(_QWORD *)this = &IWcnTransport::`vftable';
}

```

## disassembly

```asm
0x18004d780  push    rbx
0x18004d782  sub     rsp, 20h
0x18004d786  lea     rax, ??_7CWcnWfdGoTransport@@6BIWcnTransport@@@; const CWcnWfdGoTransport::`vftable'{for `IWcnTransport'}
0x18004d78d  mov     rbx, rcx
0x18004d790  mov     [rcx], rax
0x18004d793  lea     rax, ??_7CWcnWfdGoTransport@@6BIWcnSinkController@@@; const CWcnWfdGoTransport::`vftable'{for `IWcnSinkController'}
0x18004d79a  mov     [rcx+10h], rax
0x18004d79e  add     rcx, 148h; lpCriticalSection
0x18004d7a5  call    cs:__imp_DeleteCriticalSection
0x18004d7ab  lea     rcx, [rbx+170h]
0x18004d7b2  call    ??1?$_Tree@V?$_Tmap_traits@W4tagWCN_DATATYPE@@PEBUtagWCN_DATATYPE_RULE@CWcnAttributeRules@@U?$less@W4tagWCN_DATATYPE@@@std@@V?$allocator@U?$pair@$$CBW4tagWCN_DATATYPE@@PEBUtagWCN_DATATYPE_RULE@CWcnAttributeRules@@@std@@@5@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<tagWCN_DATATYPE,CWcnAttributeRules::tagWCN_DATATYPE_RULE const *,std::less<tagWCN_DATATYPE>,std::allocator<std::pair<tagWCN_DATATYPE const,CWcnAttributeRules::tagWCN_DATATYPE_RULE const *>>,0>>::~_Tree<std::_Tmap_traits<tagWCN_DATATYPE,CWcnAttributeRules::tagWCN_DATATYPE_RULE const *,std::less<tagWCN_DATATYPE>,std::allocator<std::pair<tagWCN_DATATYPE const,CWcnAttributeRules::tagWCN_DATATYPE_RULE const *>>,0>>(void)
0x18004d7b7  lea     rcx, [rbx+0C0h]; this
0x18004d7be  call    ??1CWcnWfdGoApiWrapper@@QEAA@XZ; CWcnWfdGoApiWrapper::~CWcnWfdGoApiWrapper(void)
0x18004d7c3  lea     rcx, [rbx+88h]; this
0x18004d7ca  call    ?Clear@CWcnMessage@@QEAAXXZ; CWcnMessage::Clear(void)
0x18004d7cf  lea     rcx, [rbx+50h]; this
0x18004d7d3  call    ?Clear@CWcnMessage@@QEAAXXZ; CWcnMessage::Clear(void)
0x18004d7d8  lea     rcx, [rbx+18h]; this
0x18004d7dc  call    ?Clear@CWcnMessage@@QEAAXXZ; CWcnMessage::Clear(void)
0x18004d7e1  lea     rax, ??_7IWcnTransport@@6B@; const IWcnTransport::`vftable'
0x18004d7e8  mov     [rbx], rax
0x18004d7eb  add     rsp, 20h
0x18004d7ef  pop     rbx
0x18004d7f0  retn
```
