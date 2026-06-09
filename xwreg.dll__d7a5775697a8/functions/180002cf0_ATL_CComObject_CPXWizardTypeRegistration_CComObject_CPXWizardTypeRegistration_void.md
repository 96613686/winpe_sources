# ATL::CComObject<CPXWizardTypeRegistration>::~CComObject<CPXWizardTypeRegistration>(void)

- ea: `0x180002cf0`
- end: `0x180002d2b`
- name: `??1?$CComObject@VCPXWizardTypeRegistration@@@ATL@@UEAA@XZ`
- size: `59`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002f60`

## callees

- `0x180002d74`
- `0x180013010`

## pseudocode

```c
void __fastcall ATL::CComObject<CPXWizardTypeRegistration>::~CComObject<CPXWizardTypeRegistration>(__int64 a1)
{
  *(_DWORD *)(a1 + 8) = -1073741823;
  *(_QWORD *)a1 = &ATL::CComObject<CPXWizardTypeRegistration>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection((ATL::CComSafeDeleteCriticalSection *)(a1 + 16));
}

```

## disassembly

```asm
0x180002cf0  push    rbx
0x180002cf2  sub     rsp, 20h
0x180002cf6  mov     dword ptr [rcx+8], 0C0000001h
0x180002cfd  lea     rax, ??_7?$CComObject@VCPXWizardTypeRegistration@@@ATL@@6B@; const ATL::CComObject<CPXWizardTypeRegistration>::`vftable'
0x180002d04  mov     [rcx], rax
0x180002d07  mov     rbx, rcx
0x180002d0a  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180002d11  mov     rax, [rcx]
0x180002d14  mov     rax, [rax+10h]
0x180002d18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d1d  lea     rcx, [rbx+10h]; this
0x180002d21  add     rsp, 20h
0x180002d25  pop     rbx
0x180002d26  jmp     ??1CComSafeDeleteCriticalSection@ATL@@QEAA@XZ; ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(void)
```
