# ATL::CComObject<CWdsTransportNamespaceScheduledCastAutoStart>::~CComObject<CWdsTransportNamespaceScheduledCastAutoStart>(void)

- ea: `0x180010c60`
- end: `0x180010cbb`
- name: `??1?$CComObject@VCWdsTransportNamespaceScheduledCastAutoStart@@@ATL@@UEAA@XZ`
- size: `91`
- prototype: `__int64 __fastcall(CWdsTransportTftpClient *this)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180010d70`

## callees

- `0x180005f90`
- `0x18001432c`
- `0x180020010`

## pseudocode

```c
void __fastcall ATL::CComObject<CWdsTransportNamespaceScheduledCastAutoStart>::~CComObject<CWdsTransportNamespaceScheduledCastAutoStart>(
        CWdsTransportTftpClient *this)
{
  *(_QWORD *)this = &ATL::CComObject<CWdsTransportNamespaceScheduledCastAutoStart>::`vftable'{for `CWdsTransportNamespace'};
  *((_QWORD *)this + 26) = &ATL::CComObject<CWdsTransportNamespaceScheduledCastAutoStart>::`vftable'{for `ATL::IDispatchImpl<IWdsTransportNamespaceScheduledCast,&_GUID const IID_IWdsTransportNamespaceScheduledCast,&_GUID const LIBID_WdsTptMgmtLib,1,0,ATL::CComTypeInfoHolder>'};
  *((_QWORD *)this + 27) = &ATL::CComObject<CWdsTransportNamespaceScheduledCastAutoStart>::`vftable';
  *((_DWORD *)this + 2) = -1073741823;
  CWdsTransportNamespaceScheduledCastAutoStart::FinalRelease(this);
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  CWdsTransportTftpClient::~CWdsTransportTftpClient(this);
}

```

## disassembly

```asm
0x180010c60  push    rbx
0x180010c62  sub     rsp, 20h
0x180010c66  mov     rbx, rcx
0x180010c69  lea     rax, ??_7?$CComObject@VCWdsTransportNamespaceScheduledCastAutoStart@@@ATL@@6BCWdsTransportNamespace@@@; const ATL::CComObject<CWdsTransportNamespaceScheduledCastAutoStart>::`vftable'{for `CWdsTransportNamespace'}
0x180010c70  mov     [rcx], rax
0x180010c73  lea     rax, ??_7?$CComObject@VCWdsTransportNamespaceScheduledCastAutoStart@@@ATL@@6B?$IDispatchImpl@UIWdsTransportNamespaceScheduledCast@@$1?IID_IWdsTransportNamespaceScheduledCast@@3U_GUID@@B$1?LIBID_WdsTptMgmtLib@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComObject<CWdsTransportNamespaceScheduledCastAutoStart>::`vftable'{for `ATL::IDispatchImpl<IWdsTransportNamespaceScheduledCast,&_GUID const IID_IWdsTransportNamespaceScheduledCast,&_GUID const LIBID_WdsTptMgmtLib,1,0,ATL::CComTypeInfoHolder>'}
0x180010c7a  mov     [rcx+0D0h], rax
0x180010c81  lea     rax, ??_7?$CComObject@VCWdsTransportNamespaceScheduledCastAutoStart@@@ATL@@6B@; const ATL::CComObject<CWdsTransportNamespaceScheduledCastAutoStart>::`vftable'
0x180010c88  mov     [rcx+0D8h], rax
0x180010c8f  mov     dword ptr [rcx+8], 0C0000001h
0x180010c96  call    ?FinalRelease@CWdsTransportNamespaceScheduledCastAutoStart@@QEAAXXZ; CWdsTransportNamespaceScheduledCastAutoStart::FinalRelease(void)
0x180010c9b  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180010ca2  mov     rax, [rcx]
0x180010ca5  mov     rax, [rax+10h]
0x180010ca9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010cae  mov     rcx, rbx; this
0x180010cb1  add     rsp, 20h
0x180010cb5  pop     rbx
0x180010cb6  jmp     ??1CWdsTransportTftpClient@@QEAA@XZ; CWdsTransportTftpClient::~CWdsTransportTftpClient(void)
```
