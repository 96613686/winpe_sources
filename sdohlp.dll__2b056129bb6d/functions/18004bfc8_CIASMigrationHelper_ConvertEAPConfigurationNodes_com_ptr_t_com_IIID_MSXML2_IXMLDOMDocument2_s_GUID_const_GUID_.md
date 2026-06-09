# CIASMigrationHelper::ConvertEAPConfigurationNodes(_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>> &)

- ea: `0x18004bfc8`
- end: `0x18004c166`
- name: `?ConvertEAPConfigurationNodes@CIASMigrationHelper@@SAJAEAV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@@Z`
- size: `414`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180047628`

## callees

- `0x180024cac`
- `0x18002d08c`
- `0x180047604`
- `0x18004bdbc`
- `0x18004bfc8`
- `0x18004d1ec`
- `0x180050044`
- `0x180051e7c`
- `0x1800524fc`
- `0x180058010`

## string_xrefs

- `0x18004bfff`: `//Properties/msEAPConfiguration`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CIASMigrationHelper::ConvertEAPConfigurationNodes(__int64 a1)
{
  __int64 v1; // rdi
  __int64 v2; // rbx
  struct IUnknown *v3; // rax
  __int64 v4; // rax
  struct IUnknown *v5; // rsi
  __int64 *v6; // rax
  __int64 v7; // rsi
  __int64 v8; // r14
  struct IUnknown *v9; // rax
  __int64 *Node; // rax
  int v11; // esi
  struct IUnknown *v12; // rax
  __int64 *v13; // rax
  __int64 v14; // rsi
  __int64 v16; // [rsp+20h] [rbp-20h]
  _BYTE v17[24]; // [rsp+28h] [rbp-18h] BYREF
  __int64 v18; // [rsp+78h] [rbp+38h] BYREF
  __int64 v19; // [rsp+80h] [rbp+40h] BYREF
  __int64 v20; // [rsp+88h] [rbp+48h] BYREF

  v1 = 0;
  v19 = 0;
  v2 = 0;
  v18 = 0;
  v3 = (struct IUnknown *)_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(a1);
  v4 = MSXML2::IXMLDOMDocument::GetdocumentElement(v3);
  v5 = (struct IUnknown *)_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(v4);
  _bstr_t::_bstr_t((_bstr_t *)&v20, L"//Properties/msEAPConfiguration");
  v6 = (__int64 *)MSXML2::IXMLDOMNode::selectNodes(v5);
  v7 = *v6;
  v8 = 0;
  if ( *v6 )
  {
    v1 = *v6;
    v19 = *v6;
    _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>::_AddRef(&v19);
    v8 = v7;
  }
  if ( v16 )
    (*(void (__fastcall **)())(*(_QWORD *)v16 + 16LL))();
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v17);
  if ( v8 )
  {
    v9 = (struct IUnknown *)_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(&v19);
    Node = (__int64 *)MSXML2::IXMLDOMNodeList::nextNode(v9);
    if ( *Node )
    {
      v2 = *Node;
      v18 = *Node;
      _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>::_AddRef(&v18);
    }
    if ( v20 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    while ( v2 )
    {
      v11 = CIASMigrationHelper::ConvertEAPBlob((__int64)&v18);
      if ( v11 < 0 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
        if ( v1 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v1 + 16LL))(v1);
        return (unsigned int)v11;
      }
      v12 = (struct IUnknown *)_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(&v19);
      v13 = (__int64 *)MSXML2::IXMLDOMNodeList::nextNode(v12);
      if ( v2 != *v13 )
      {
        v14 = v2;
        v2 = *v13;
        v18 = *v13;
        _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>::_AddRef(&v18);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
      }
      if ( v20 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    }
    if ( v1 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v1 + 16LL))(v1);
  }
  return 0;
}

```

## disassembly

```asm
0x18004bfc8  push    rbp
0x18004bfca  push    rbx
0x18004bfcb  push    rsi
0x18004bfcc  push    rdi
0x18004bfcd  push    r14
0x18004bfcf  mov     rbp, rsp
0x18004bfd2  sub     rsp, 40h
0x18004bfd6  xor     edi, edi
0x18004bfd8  mov     [rbp+arg_10], rdi
0x18004bfdc  xor     ebx, ebx
0x18004bfde  mov     [rbp+arg_8], rbx
0x18004bfe2  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMDocument2@MSXML2@@XZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(void)
0x18004bfe7  lea     rdx, [rbp+var_18]
0x18004bfeb  mov     rcx, rax; struct IUnknown *
0x18004bfee  call    ?GetdocumentElement@IXMLDOMDocument@MSXML2@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMElement@MSXML2@@$1?_GUID_2933bf86_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@XZ; MSXML2::IXMLDOMDocument::GetdocumentElement(void)
0x18004bff3  nop
0x18004bff4  mov     rcx, rax
0x18004bff7  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMDocument2@MSXML2@@XZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(void)
0x18004bffc  mov     rsi, rax
0x18004bfff  lea     rdx, ?m_migEAPNodeQuery@CIASMigrationHelper@@1QBGB; "//Properties/msEAPConfiguration"
0x18004c006  lea     rcx, [rbp+arg_18]; this
0x18004c00a  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18004c00f  mov     r8, rax
0x18004c012  lea     rdx, [rbp+var_20]
0x18004c016  mov     rcx, rsi; struct IUnknown *
0x18004c019  call    ?selectNodes@IXMLDOMNode@MSXML2@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNodeList@MSXML2@@$1?_GUID_2933bf82_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@V_bstr_t@@@Z; MSXML2::IXMLDOMNode::selectNodes(_bstr_t)
0x18004c01e  mov     rsi, [rax]
0x18004c021  xor     r14d, r14d
0x18004c024  test    rsi, rsi
0x18004c027  jz      short loc_18004C03C
0x18004c029  mov     rdi, rsi
0x18004c02c  mov     [rbp+arg_10], rsi
0x18004c030  lea     rcx, [rbp+arg_10]
0x18004c034  call    ?_AddRef@?$_com_ptr_t@V?$_com_IIID@UIXMLDOMElement@MSXML2@@$1?_GUID_2933bf86_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>::_AddRef(void)
0x18004c039  mov     r14, rsi
0x18004c03c  mov     rcx, [rbp+var_20]
0x18004c040  test    rcx, rcx
0x18004c043  jz      short loc_18004C052
0x18004c045  mov     rax, [rcx]
0x18004c048  mov     rax, [rax+10h]
0x18004c04c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c051  nop
0x18004c052  lea     rcx, [rbp+var_18]
0x18004c056  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18004c05b  test    r14, r14
0x18004c05e  jnz     short loc_18004C065
0x18004c060  jmp     loc_18004C159
0x18004c065  lea     rcx, [rbp+arg_10]
0x18004c069  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMDocument2@MSXML2@@XZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(void)
0x18004c06e  lea     rdx, [rbp+arg_18]
0x18004c072  mov     rcx, rax; struct IUnknown *
0x18004c075  call    ?nextNode@IXMLDOMNodeList@MSXML2@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@XZ; MSXML2::IXMLDOMNodeList::nextNode(void)
0x18004c07a  nop
0x18004c07b  cmp     qword ptr [rax], 0
0x18004c07f  jz      short loc_18004C092
0x18004c081  mov     rbx, [rax]
0x18004c084  mov     [rbp+arg_8], rbx
0x18004c088  lea     rcx, [rbp+arg_8]
0x18004c08c  call    ?_AddRef@?$_com_ptr_t@V?$_com_IIID@UIXMLDOMElement@MSXML2@@$1?_GUID_2933bf86_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>::_AddRef(void)
0x18004c091  nop
0x18004c092  mov     rcx, [rbp+arg_18]
0x18004c096  test    rcx, rcx
0x18004c099  jz      short loc_18004C0A8
0x18004c09b  mov     rax, [rcx]
0x18004c09e  mov     rax, [rax+10h]
0x18004c0a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c0a7  nop
0x18004c0a8  test    rbx, rbx
0x18004c0ab  jz      loc_18004C144
0x18004c0b1  lea     rcx, [rbp+arg_8]
0x18004c0b5  call    ?ConvertEAPBlob@CIASMigrationHelper@@KAJAEAV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@@Z; CIASMigrationHelper::ConvertEAPBlob(_com_ptr_t<_com_IIID<MSXML2::IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>> &)
0x18004c0ba  mov     esi, eax
0x18004c0bc  test    eax, eax
0x18004c0be  js      short loc_18004C11B
0x18004c0c0  lea     rcx, [rbp+arg_10]
0x18004c0c4  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMDocument2@MSXML2@@XZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(void)
0x18004c0c9  lea     rdx, [rbp+arg_18]
0x18004c0cd  mov     rcx, rax; struct IUnknown *
0x18004c0d0  call    ?nextNode@IXMLDOMNodeList@MSXML2@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@XZ; MSXML2::IXMLDOMNodeList::nextNode(void)
0x18004c0d5  nop
0x18004c0d6  cmp     rbx, [rax]
0x18004c0d9  jz      short loc_18004C103
0x18004c0db  mov     rsi, rbx
0x18004c0de  mov     rbx, [rax]
0x18004c0e1  mov     [rbp+arg_8], rbx
0x18004c0e5  lea     rcx, [rbp+arg_8]
0x18004c0e9  call    ?_AddRef@?$_com_ptr_t@V?$_com_IIID@UIXMLDOMElement@MSXML2@@$1?_GUID_2933bf86_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>::_AddRef(void)
0x18004c0ee  test    rsi, rsi
0x18004c0f1  jz      short loc_18004C103
0x18004c0f3  mov     rax, [rsi]
0x18004c0f6  mov     rcx, rsi
0x18004c0f9  mov     rax, [rax+10h]
0x18004c0fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c102  nop
0x18004c103  mov     rcx, [rbp+arg_18]
0x18004c107  test    rcx, rcx
0x18004c10a  jz      short loc_18004C119
0x18004c10c  mov     rax, [rcx]
0x18004c10f  mov     rax, [rax+10h]
0x18004c113  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c118  nop
0x18004c119  jmp     short loc_18004C0A8
0x18004c11b  mov     rax, [rbx]
0x18004c11e  mov     rcx, rbx
0x18004c121  mov     rax, [rax+10h]
0x18004c125  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c12a  nop
0x18004c12b  test    rdi, rdi
0x18004c12e  jz      short loc_18004C140
0x18004c130  mov     rax, [rdi]
0x18004c133  mov     rcx, rdi
0x18004c136  mov     rax, [rax+10h]
0x18004c13a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c13f  nop
0x18004c140  mov     eax, esi
0x18004c142  jmp     short loc_18004C15B
0x18004c144  test    rdi, rdi
0x18004c147  jz      short loc_18004C159
0x18004c149  mov     rax, [rdi]
0x18004c14c  mov     rcx, rdi
0x18004c14f  mov     rax, [rax+10h]
0x18004c153  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c158  nop
0x18004c159  xor     eax, eax
0x18004c15b  add     rsp, 40h
0x18004c15f  pop     r14
0x18004c161  pop     rdi
0x18004c162  pop     rsi
0x18004c163  pop     rbx
0x18004c164  pop     rbp
0x18004c165  retn
```
