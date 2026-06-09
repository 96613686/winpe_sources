# WcmCommon::Xml::Details::Document::Document(_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument3,&__s_GUID const _GUID_2933bf96_7b36_11d2_b20e_00c04f983e60>> const &)

- ea: `0x180028998`
- end: `0x180028b0d`
- name: `??0Document@Details@Xml@WcmCommon@@QEAA@AEBV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument3@MSXML2@@$1?_GUID_2933bf96_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@@Z`
- size: `373`
- prototype: `struct IUnknown **__fastcall(struct IUnknown **, struct IUnknown **)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180023974`

## callees

- `0x180002590`
- `0x1800029c0`
- `0x18002857c`
- `0x180028678`
- `0x180028998`
- `0x180028be8`
- `0x18003127c`
- `0x180031290`
- `0x180033010`

## pseudocode

```c
struct IUnknown **__fastcall WcmCommon::Xml::Details::Document::Document(struct IUnknown **a1, struct IUnknown **a2)
{
  struct IUnknown *v3; // rcx
  WcmCommon::Xml::Node *v4; // r14
  struct IUnknown *v5; // rdi
  int v6; // eax
  __int64 v7; // rsi
  struct NodeVtbl **v8; // rax
  struct NodeVtbl *v9; // rdi
  __int64 v10; // rax
  __int64 v12; // [rsp+20h] [rbp-48h] BYREF
  Node v13; // [rsp+28h] [rbp-40h] BYREF
  _QWORD v14[3]; // [rsp+30h] [rbp-38h] BYREF
  __int64 v15; // [rsp+48h] [rbp-20h] BYREF

  v14[1] = a1;
  LODWORD(v15) = 0;
  v3 = *a2;
  *a1 = *a2;
  if ( v3 )
    ((void (__fastcall *)(struct IUnknown *))v3->lpVtbl->AddRef)(v3);
  v4 = (WcmCommon::Xml::Node *)operator new(0x10u);
  v14[2] = v4;
  *(_OWORD *)v4 = 0;
  v5 = *a1;
  if ( !*a1 )
    _com_issue_error(-2147467261);
  v15 = 0;
  v6 = ((__int64 (__fastcall *)(struct IUnknown *, __int64 *))v5->lpVtbl[15].QueryInterface)(v5, &v15);
  if ( v6 < 0 )
    _com_issue_errorex(v6, v5, &GUID_2933bf81_7b36_11d2_b20e_00c04f983e60);
  v7 = v15;
  v12 = v15;
  LODWORD(v15) = 9;
  v8 = (struct NodeVtbl **)_com_ptr_t<_com_IIID<MSXML2::IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>>::_com_ptr_t<_com_IIID<MSXML2::IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>>(
                             v14,
                             &v12);
  LODWORD(v15) = 11;
  v9 = *v8;
  v13.lpVtbl = v9;
  if ( v9 )
    (*((void (__fastcall **)(struct NodeVtbl *))v9->QueryInterface + 1))(v9);
  LODWORD(v15) = 15;
  v10 = WcmCommon::Xml::Node::Node(v4, &v13);
  std::shared_ptr<WcmCommon::Xml::Document>::shared_ptr<WcmCommon::Xml::Document>(a1 + 1, v10);
  LODWORD(v15) = 11;
  if ( v9 )
    (*((void (__fastcall **)(struct NodeVtbl *))v9->QueryInterface + 2))(v9);
  LODWORD(v15) = 9;
  if ( v14[0] )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v14[0] + 16LL))(v14[0]);
  if ( v7 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  return a1;
}

```

## disassembly

```asm
0x180028998  push    rbp
0x18002899a  push    rbx
0x18002899b  push    rsi
0x18002899c  push    rdi
0x18002899d  push    r14
0x18002899f  push    r15
0x1800289a1  mov     rbp, rsp
0x1800289a4  sub     rsp, 68h
0x1800289a8  mov     rax, cs:__security_cookie
0x1800289af  xor     rax, rsp
0x1800289b2  mov     [rbp+var_18], rax
0x1800289b6  mov     rbx, rcx
0x1800289b9  mov     [rbp+var_30], rcx
0x1800289bd  mov     dword ptr [rbp+var_20], 0
0x1800289c4  mov     rcx, [rdx]
0x1800289c7  mov     [rbx], rcx
0x1800289ca  test    rcx, rcx
0x1800289cd  jz      short loc_1800289DC
0x1800289cf  mov     rax, [rcx]
0x1800289d2  mov     rax, [rax+8]
0x1800289d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800289db  nop
0x1800289dc  mov     ecx, 10h; Size
0x1800289e1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800289e6  mov     r14, rax
0x1800289e9  mov     [rbp+var_28], rax
0x1800289ed  xorps   xmm0, xmm0
0x1800289f0  movups  xmmword ptr [rax], xmm0
0x1800289f3  mov     rdi, [rbx]
0x1800289f6  test    rdi, rdi
0x1800289f9  jz      loc_180028B02
0x1800289ff  mov     [rbp+var_20], 0
0x180028a07  mov     rax, [rdi]
0x180028a0a  lea     rdx, [rbp+var_20]
0x180028a0e  mov     rcx, rdi
0x180028a11  mov     rax, [rax+168h]
0x180028a18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028a1d  test    eax, eax
0x180028a1f  js      loc_180028AF0
0x180028a25  mov     rsi, [rbp+var_20]
0x180028a29  mov     [rbp+var_48], rsi
0x180028a2d  mov     dword ptr [rbp+var_20], 9
0x180028a34  lea     rdx, [rbp+var_48]
0x180028a38  lea     rcx, [rbp+var_38]
0x180028a3c  call    ??$?0V?$_com_IIID@UIXMLDOMElement@MSXML2@@$1?_GUID_2933bf86_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@$0A@@?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEAA@AEBV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMElement@MSXML2@@$1?_GUID_2933bf86_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@@Z; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>>::_com_ptr_t<_com_IIID<MSXML2::IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>>(_com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>> const &)
0x180028a41  nop
0x180028a42  mov     dword ptr [rbp+var_20], 0Bh
0x180028a49  mov     rdi, [rax]
0x180028a4c  mov     [rbp+var_40.lpVtbl], rdi
0x180028a50  test    rdi, rdi
0x180028a53  jz      short loc_180028A65
0x180028a55  mov     rax, [rdi]
0x180028a58  mov     rcx, rdi
0x180028a5b  mov     rax, [rax+8]
0x180028a5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028a64  nop
0x180028a65  mov     dword ptr [rbp+var_20], 0Fh
0x180028a6c  lea     rdx, [rbp+var_40]; struct Node *
0x180028a70  mov     rcx, r14; this
0x180028a73  call    ??0Node@Xml@WcmCommon@@AEAA@AEBU0Details@12@@Z; WcmCommon::Xml::Node::Node(WcmCommon::Xml::Details::Node const &)
0x180028a78  nop
0x180028a79  mov     rdx, rax
0x180028a7c  lea     rcx, [rbx+8]
0x180028a80  call    ??$?0VDocument@Xml@WcmCommon@@$0A@@?$shared_ptr@VDocument@Xml@WcmCommon@@@std@@QEAA@PEAVDocument@Xml@WcmCommon@@@Z; std::shared_ptr<WcmCommon::Xml::Document>::shared_ptr<WcmCommon::Xml::Document>(WcmCommon::Xml::Document *)
0x180028a85  nop
0x180028a86  mov     dword ptr [rbp+var_20], 0Bh
0x180028a8d  test    rdi, rdi
0x180028a90  jz      short loc_180028AA2
0x180028a92  mov     rax, [rdi]
0x180028a95  mov     rcx, rdi
0x180028a98  mov     rax, [rax+10h]
0x180028a9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028aa1  nop
0x180028aa2  mov     dword ptr [rbp+var_20], 9
0x180028aa9  mov     rcx, [rbp+var_38]
0x180028aad  test    rcx, rcx
0x180028ab0  jz      short loc_180028ABF
0x180028ab2  mov     rax, [rcx]
0x180028ab5  mov     rax, [rax+10h]
0x180028ab9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028abe  nop
0x180028abf  test    rsi, rsi
0x180028ac2  jz      short loc_180028AD4
0x180028ac4  mov     rdx, [rsi]
0x180028ac7  mov     rcx, rsi
0x180028aca  mov     rax, [rdx+10h]
0x180028ace  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028ad3  nop
0x180028ad4  mov     rax, rbx
0x180028ad7  mov     rcx, [rbp+var_18]
0x180028adb  xor     rcx, rsp; StackCookie
0x180028ade  call    __security_check_cookie
0x180028ae3  add     rsp, 68h
0x180028ae7  pop     r15
0x180028ae9  pop     r14
0x180028aeb  pop     rdi
0x180028aec  pop     rsi
0x180028aed  pop     rbx
0x180028aee  pop     rbp
0x180028aef  retn
0x180028af0  lea     r8, _GUID_2933bf81_7b36_11d2_b20e_00c04f983e60; struct _GUID *
0x180028af7  mov     rdx, rdi; struct IUnknown *
0x180028afa  mov     ecx, eax; int
0x180028afc  call    ?_com_issue_errorex@@YAXJPEAUIUnknown@@AEBU_GUID@@@Z; _com_issue_errorex(long,IUnknown *,_GUID const &)
0x180028b02  mov     ecx, 80004003h; int
0x180028b07  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
```
