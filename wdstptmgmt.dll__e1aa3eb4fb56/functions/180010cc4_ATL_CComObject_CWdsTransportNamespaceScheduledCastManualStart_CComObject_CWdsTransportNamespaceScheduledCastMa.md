# ATL::CComObject<CWdsTransportNamespaceScheduledCastManualStart>::~CComObject<CWdsTransportNamespaceScheduledCastManualStart>(void)

- ea: `0x180010cc4`
- end: `0x180010d1f`
- name: `??1?$CComObject@VCWdsTransportNamespaceScheduledCastManualStart@@@ATL@@UEAA@XZ`
- size: `91`
- prototype: `__int64 __fastcall(CWdsTransportTftpClient *this)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180010db0`

## callees

- `0x180005f90`
- `0x180013fa8`
- `0x180020010`

## pseudocode

```c
void __fastcall ATL::CComObject<CWdsTransportNamespaceScheduledCastManualStart>::~CComObject<CWdsTransportNamespaceScheduledCastManualStart>(
        CWdsTransportTftpClient *this)
{
  *(_QWORD *)this = &ATL::CComObject<CWdsTransportNamespaceScheduledCastManualStart>::`vftable'{for `CWdsTransportNamespace'};
  *((_QWORD *)this + 26) = &ATL::CComObject<CWdsTransportNamespaceScheduledCastManualStart>::`vftable'{for `ATL::IDispatchImpl<IWdsTransportNamespaceScheduledCast,&_GUID const IID_IWdsTransportNamespaceScheduledCast,&_GUID const LIBID_WdsTptMgmtLib,1,0,ATL::CComTypeInfoHolder>'};
  *((_QWORD *)this + 27) = &ATL::CComObject<CWdsTransportNamespaceScheduledCastManualStart>::`vftable';
  *((_DWORD *)this + 2) = -1073741823;
  CWdsTransportNamespaceScheduledCastManualStart::FinalRelease(this);
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  CWdsTransportTftpClient::~CWdsTransportTftpClient(this);
}

```

## disassembly

```asm
0x180010cc4  push    rbx
0x180010cc6  sub     rsp, 20h
0x180010cca  mov     rbx, rcx
0x180010ccd  lea     rax, ??_7?$CComObject@VCWdsTransportNamespaceScheduledCastManualStart@@@ATL@@6BCWdsTransportNamespace@@@; const ATL::CComObject<CWdsTransportNamespaceScheduledCastManualStart>::`vftable'{for `CWdsTransportNamespace'}
0x180010cd4  mov     [rcx], rax
0x180010cd7  lea     rax, ??_7?$CComObject@VCWdsTransportNamespaceScheduledCastManualStart@@@ATL@@6B?$IDispatchImpl@UIWdsTransportNamespaceScheduledCast@@$1?IID_IWdsTransportNamespaceScheduledCast@@3U_GUID@@B$1?LIBID_WdsTptMgmtLib@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComObject<CWdsTransportNamespaceScheduledCastManualStart>::`vftable'{for `ATL::IDispatchImpl<IWdsTransportNamespaceScheduledCast,&_GUID const IID_IWdsTransportNamespaceScheduledCast,&_GUID const LIBID_WdsTptMgmtLib,1,0,ATL::CComTypeInfoHolder>'}
0x180010cde  mov     [rcx+0D0h], rax
0x180010ce5  lea     rax, ??_7?$CComObject@VCWdsTransportNamespaceScheduledCastManualStart@@@ATL@@6B@; const ATL::CComObject<CWdsTransportNamespaceScheduledCastManualStart>::`vftable'
0x180010cec  mov     [rcx+0D8h], rax
0x180010cf3  mov     dword ptr [rcx+8], 0C0000001h
0x180010cfa  call    ?FinalRelease@CWdsTransportNamespaceScheduledCastManualStart@@QEAAXXZ; CWdsTransportNamespaceScheduledCastManualStart::FinalRelease(void)
0x180010cff  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180010d06  mov     rax, [rcx]
0x180010d09  mov     rax, [rax+10h]
0x180010d0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010d12  mov     rcx, rbx; this
0x180010d15  add     rsp, 20h
0x180010d19  pop     rbx
0x180010d1a  jmp     ??1CWdsTransportTftpClient@@QEAA@XZ; CWdsTransportTftpClient::~CWdsTransportTftpClient(void)
```
