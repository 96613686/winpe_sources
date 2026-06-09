# ATL::CComObject<CWdsTransportConfigurationManager>::~CComObject<CWdsTransportConfigurationManager>(void)

- ea: `0x18000b23c`
- end: `0x18000b27b`
- name: `??1?$CComObject@VCWdsTransportConfigurationManager@@@ATL@@UEAA@XZ`
- size: `63`
- prototype: `__int64 __fastcall(CWdsTransportConfigurationManager *this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000b290`

## callees

- `0x180009d9c`
- `0x18000b858`
- `0x180020010`

## pseudocode

```c
void __fastcall ATL::CComObject<CWdsTransportConfigurationManager>::~CComObject<CWdsTransportConfigurationManager>(
        CWdsTransportConfigurationManager *this)
{
  *(_QWORD *)this = &ATL::CComObject<CWdsTransportConfigurationManager>::`vftable';
  *((_DWORD *)this + 2) = -1073741823;
  CWdsTransportConfigurationManager::FinalRelease(this);
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  CWdsTransportConfigurationManager::~CWdsTransportConfigurationManager((struct _RTL_CRITICAL_SECTION *)this);
}

```

## disassembly

```asm
0x18000b23c  push    rbx
0x18000b23e  sub     rsp, 20h
0x18000b242  mov     rbx, rcx
0x18000b245  lea     rax, ??_7?$CComObject@VCWdsTransportConfigurationManager@@@ATL@@6B@; const ATL::CComObject<CWdsTransportConfigurationManager>::`vftable'
0x18000b24c  mov     [rcx], rax
0x18000b24f  mov     dword ptr [rcx+8], 0C0000001h
0x18000b256  call    ?FinalRelease@CWdsTransportConfigurationManager@@QEAAXXZ; CWdsTransportConfigurationManager::FinalRelease(void)
0x18000b25b  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000b262  mov     rax, [rcx]
0x18000b265  mov     rax, [rax+10h]
0x18000b269  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b26e  mov     rcx, rbx; this
0x18000b271  add     rsp, 20h
0x18000b275  pop     rbx
0x18000b276  jmp     ??1CWdsTransportConfigurationManager@@QEAA@XZ; CWdsTransportConfigurationManager::~CWdsTransportConfigurationManager(void)
```
