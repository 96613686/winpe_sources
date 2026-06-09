# ATL::CComObject<CWdsTransportNamespaceAutoCast>::~CComObject<CWdsTransportNamespaceAutoCast>(void)

- ea: `0x180010c0c`
- end: `0x180010c59`
- name: `??1?$CComObject@VCWdsTransportNamespaceAutoCast@@@ATL@@UEAA@XZ`
- size: `77`
- prototype: `__int64 __fastcall(CWdsTransportTftpClient *this)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180010d30`

## callees

- `0x180005f90`
- `0x180013ac0`
- `0x180020010`

## pseudocode

```c
void __fastcall ATL::CComObject<CWdsTransportNamespaceAutoCast>::~CComObject<CWdsTransportNamespaceAutoCast>(
        CWdsTransportTftpClient *this)
{
  *(_QWORD *)this = &ATL::CComObject<CWdsTransportNamespaceAutoCast>::`vftable'{for `CWdsTransportNamespace'};
  *((_QWORD *)this + 26) = &ATL::CComObject<CWdsTransportNamespaceAutoCast>::`vftable'{for `ATL::IDispatchImpl<IWdsTransportNamespaceAutoCast,&_GUID const IID_IWdsTransportNamespaceAutoCast,&_GUID const LIBID_WdsTptMgmtLib,1,0,ATL::CComTypeInfoHolder>'};
  *((_DWORD *)this + 2) = -1073741823;
  CWdsTransportNamespaceAutoCast::FinalRelease(this);
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  CWdsTransportTftpClient::~CWdsTransportTftpClient(this);
}

```

## disassembly

```asm
0x180010c0c  push    rbx
0x180010c0e  sub     rsp, 20h
0x180010c12  mov     rbx, rcx
0x180010c15  lea     rax, ??_7?$CComObject@VCWdsTransportNamespaceAutoCast@@@ATL@@6BCWdsTransportNamespace@@@; const ATL::CComObject<CWdsTransportNamespaceAutoCast>::`vftable'{for `CWdsTransportNamespace'}
0x180010c1c  mov     [rcx], rax
0x180010c1f  lea     rax, ??_7?$CComObject@VCWdsTransportNamespaceAutoCast@@@ATL@@6B?$IDispatchImpl@UIWdsTransportNamespaceAutoCast@@$1?IID_IWdsTransportNamespaceAutoCast@@3U_GUID@@B$1?LIBID_WdsTptMgmtLib@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComObject<CWdsTransportNamespaceAutoCast>::`vftable'{for `ATL::IDispatchImpl<IWdsTransportNamespaceAutoCast,&_GUID const IID_IWdsTransportNamespaceAutoCast,&_GUID const LIBID_WdsTptMgmtLib,1,0,ATL::CComTypeInfoHolder>'}
0x180010c26  mov     [rcx+0D0h], rax
0x180010c2d  mov     dword ptr [rcx+8], 0C0000001h
0x180010c34  call    ?FinalRelease@CWdsTransportNamespaceAutoCast@@QEAAXXZ; CWdsTransportNamespaceAutoCast::FinalRelease(void)
0x180010c39  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180010c40  mov     rax, [rcx]
0x180010c43  mov     rax, [rax+10h]
0x180010c47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010c4c  mov     rcx, rbx; this
0x180010c4f  add     rsp, 20h
0x180010c53  pop     rbx
0x180010c54  jmp     ??1CWdsTransportTftpClient@@QEAA@XZ; CWdsTransportTftpClient::~CWdsTransportTftpClient(void)
```
