# ATL::CComObject<CWdsTransportNamespaceManager>::~CComObject<CWdsTransportNamespaceManager>(void)

- ea: `0x18000fe9c`
- end: `0x18000fedb`
- name: `??1?$CComObject@VCWdsTransportNamespaceManager@@@ATL@@UEAA@XZ`
- size: `63`
- prototype: `__int64 __fastcall(CWdsTransportConfigurationManager *this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000fef0`

## callees

- `0x180009d9c`
- `0x18001035c`
- `0x180020010`

## pseudocode

```c
void __fastcall ATL::CComObject<CWdsTransportNamespaceManager>::~CComObject<CWdsTransportNamespaceManager>(
        CWdsTransportConfigurationManager *this)
{
  *(_QWORD *)this = &ATL::CComObject<CWdsTransportNamespaceManager>::`vftable';
  *((_DWORD *)this + 2) = -1073741823;
  CWdsTransportNamespaceManager::FinalRelease(this);
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  CWdsTransportConfigurationManager::~CWdsTransportConfigurationManager((struct _RTL_CRITICAL_SECTION *)this);
}

```

## disassembly

```asm
0x18000fe9c  push    rbx
0x18000fe9e  sub     rsp, 20h
0x18000fea2  mov     rbx, rcx
0x18000fea5  lea     rax, ??_7?$CComObject@VCWdsTransportNamespaceManager@@@ATL@@6B@; const ATL::CComObject<CWdsTransportNamespaceManager>::`vftable'
0x18000feac  mov     [rcx], rax
0x18000feaf  mov     dword ptr [rcx+8], 0C0000001h
0x18000feb6  call    ?FinalRelease@CWdsTransportNamespaceManager@@QEAAXXZ; CWdsTransportNamespaceManager::FinalRelease(void)
0x18000febb  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000fec2  mov     rax, [rcx]
0x18000fec5  mov     rax, [rax+10h]
0x18000fec9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fece  mov     rcx, rbx; this
0x18000fed1  add     rsp, 20h
0x18000fed5  pop     rbx
0x18000fed6  jmp     ??1CWdsTransportConfigurationManager@@QEAA@XZ; CWdsTransportConfigurationManager::~CWdsTransportConfigurationManager(void)
```
