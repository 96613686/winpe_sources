# ATL::CComObject<CPXWizardFactoryRegistration>::~CComObject<CPXWizardFactoryRegistration>(void)

- ea: `0x180002c68`
- end: `0x180002ca3`
- name: `??1?$CComObject@VCPXWizardFactoryRegistration@@@ATL@@UEAA@XZ`
- size: `59`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002ee0`

## callees

- `0x180002d74`
- `0x180013010`

## pseudocode

```c
void __fastcall ATL::CComObject<CPXWizardFactoryRegistration>::~CComObject<CPXWizardFactoryRegistration>(__int64 a1)
{
  *(_DWORD *)(a1 + 8) = -1073741823;
  *(_QWORD *)a1 = &ATL::CComObject<CPXWizardFactoryRegistration>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection((ATL::CComSafeDeleteCriticalSection *)(a1 + 16));
}

```

## disassembly

```asm
0x180002c68  push    rbx
0x180002c6a  sub     rsp, 20h
0x180002c6e  mov     dword ptr [rcx+8], 0C0000001h
0x180002c75  lea     rax, ??_7?$CComObject@VCPXWizardFactoryRegistration@@@ATL@@6B@; const ATL::CComObject<CPXWizardFactoryRegistration>::`vftable'
0x180002c7c  mov     [rcx], rax
0x180002c7f  mov     rbx, rcx
0x180002c82  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180002c89  mov     rax, [rcx]
0x180002c8c  mov     rax, [rax+10h]
0x180002c90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c95  lea     rcx, [rbx+10h]; this
0x180002c99  add     rsp, 20h
0x180002c9d  pop     rbx
0x180002c9e  jmp     ??1CComSafeDeleteCriticalSection@ATL@@QEAA@XZ; ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(void)
```
