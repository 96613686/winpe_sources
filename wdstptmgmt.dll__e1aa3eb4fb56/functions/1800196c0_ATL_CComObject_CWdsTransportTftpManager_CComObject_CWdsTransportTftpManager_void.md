# ATL::CComObject<CWdsTransportTftpManager>::~CComObject<CWdsTransportTftpManager>(void)

- ea: `0x1800196c0`
- end: `0x1800196ff`
- name: `??1?$CComObject@VCWdsTransportTftpManager@@@ATL@@UEAA@XZ`
- size: `63`
- prototype: `__int64 __fastcall(CWdsTransportConfigurationManager *this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180019710`

## callees

- `0x180009d9c`
- `0x180019a44`
- `0x180020010`

## pseudocode

```c
void __fastcall ATL::CComObject<CWdsTransportTftpManager>::~CComObject<CWdsTransportTftpManager>(
        CWdsTransportConfigurationManager *this)
{
  *(_QWORD *)this = &ATL::CComObject<CWdsTransportTftpManager>::`vftable';
  *((_DWORD *)this + 2) = -1073741823;
  CWdsTransportTftpManager::FinalRelease(this);
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  CWdsTransportConfigurationManager::~CWdsTransportConfigurationManager((struct _RTL_CRITICAL_SECTION *)this);
}

```

## disassembly

```asm
0x1800196c0  push    rbx
0x1800196c2  sub     rsp, 20h
0x1800196c6  mov     rbx, rcx
0x1800196c9  lea     rax, ??_7?$CComObject@VCWdsTransportTftpManager@@@ATL@@6B@; const ATL::CComObject<CWdsTransportTftpManager>::`vftable'
0x1800196d0  mov     [rcx], rax
0x1800196d3  mov     dword ptr [rcx+8], 0C0000001h
0x1800196da  call    ?FinalRelease@CWdsTransportTftpManager@@QEAAXXZ; CWdsTransportTftpManager::FinalRelease(void)
0x1800196df  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800196e6  mov     rax, [rcx]
0x1800196e9  mov     rax, [rax+10h]
0x1800196ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800196f2  mov     rcx, rbx; this
0x1800196f5  add     rsp, 20h
0x1800196f9  pop     rbx
0x1800196fa  jmp     ??1CWdsTransportConfigurationManager@@QEAA@XZ; CWdsTransportConfigurationManager::~CWdsTransportConfigurationManager(void)
```
