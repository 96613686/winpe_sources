# ATL::CComObject<CWdsTransportServicePolicy>::~CComObject<CWdsTransportServicePolicy>(void)

- ea: `0x18000c704`
- end: `0x18000c743`
- name: `??1?$CComObject@VCWdsTransportServicePolicy@@@ATL@@UEAA@XZ`
- size: `63`
- prototype: `__int64 __fastcall(CWdsTransportConfigurationManager *this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000c750`

## callees

- `0x180009d9c`
- `0x18000d05c`
- `0x180020010`

## pseudocode

```c
void __fastcall ATL::CComObject<CWdsTransportServicePolicy>::~CComObject<CWdsTransportServicePolicy>(
        CWdsTransportConfigurationManager *this)
{
  *(_QWORD *)this = &ATL::CComObject<CWdsTransportServicePolicy>::`vftable';
  *((_DWORD *)this + 2) = -1073741823;
  CWdsTransportServicePolicy::FinalRelease(this);
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  CWdsTransportConfigurationManager::~CWdsTransportConfigurationManager((struct _RTL_CRITICAL_SECTION *)this);
}

```

## disassembly

```asm
0x18000c704  push    rbx
0x18000c706  sub     rsp, 20h
0x18000c70a  mov     rbx, rcx
0x18000c70d  lea     rax, ??_7?$CComObject@VCWdsTransportServicePolicy@@@ATL@@6B@; const ATL::CComObject<CWdsTransportServicePolicy>::`vftable'
0x18000c714  mov     [rcx], rax
0x18000c717  mov     dword ptr [rcx+8], 0C0000001h
0x18000c71e  call    ?FinalRelease@CWdsTransportServicePolicy@@QEAAXXZ; CWdsTransportServicePolicy::FinalRelease(void)
0x18000c723  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000c72a  mov     rax, [rcx]
0x18000c72d  mov     rax, [rax+10h]
0x18000c731  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c736  mov     rcx, rbx; this
0x18000c739  add     rsp, 20h
0x18000c73d  pop     rbx
0x18000c73e  jmp     ??1CWdsTransportConfigurationManager@@QEAA@XZ; CWdsTransportConfigurationManager::~CWdsTransportConfigurationManager(void)
```
