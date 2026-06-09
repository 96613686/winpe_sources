# ATL::CComAggObject<CPXWizardFactoryRegistration>::~CComAggObject<CPXWizardFactoryRegistration>(void)

- ea: `0x180002b74`
- end: `0x180002baf`
- name: `??1?$CComAggObject@VCPXWizardFactoryRegistration@@@ATL@@UEAA@XZ`
- size: `59`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002e20`

## callees

- `0x180002d74`
- `0x180013010`

## pseudocode

```c
void __fastcall ATL::CComAggObject<CPXWizardFactoryRegistration>::~CComAggObject<CPXWizardFactoryRegistration>(
        __int64 a1)
{
  *(_DWORD *)(a1 + 8) = -1073741823;
  *(_QWORD *)a1 = &ATL::CComAggObject<CPXWizardFactoryRegistration>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection((ATL::CComSafeDeleteCriticalSection *)(a1 + 40));
}

```

## disassembly

```asm
0x180002b74  push    rbx
0x180002b76  sub     rsp, 20h
0x180002b7a  mov     dword ptr [rcx+8], 0C0000001h
0x180002b81  lea     rax, ??_7?$CComAggObject@VCPXWizardFactoryRegistration@@@ATL@@6B@; const ATL::CComAggObject<CPXWizardFactoryRegistration>::`vftable'
0x180002b88  mov     [rcx], rax
0x180002b8b  mov     rbx, rcx
0x180002b8e  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180002b95  mov     rax, [rcx]
0x180002b98  mov     rax, [rax+10h]
0x180002b9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ba1  lea     rcx, [rbx+28h]; this
0x180002ba5  add     rsp, 20h
0x180002ba9  pop     rbx
0x180002baa  jmp     ??1CComSafeDeleteCriticalSection@ATL@@QEAA@XZ; ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(void)
```
