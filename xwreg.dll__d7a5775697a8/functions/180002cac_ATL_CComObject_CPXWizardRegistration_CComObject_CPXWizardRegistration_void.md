# ATL::CComObject<CPXWizardRegistration>::~CComObject<CPXWizardRegistration>(void)

- ea: `0x180002cac`
- end: `0x180002ce7`
- name: `??1?$CComObject@VCPXWizardRegistration@@@ATL@@UEAA@XZ`
- size: `59`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002f20`

## callees

- `0x180002d74`
- `0x180013010`

## pseudocode

```c
void __fastcall ATL::CComObject<CPXWizardRegistration>::~CComObject<CPXWizardRegistration>(__int64 a1)
{
  *(_DWORD *)(a1 + 8) = -1073741823;
  *(_QWORD *)a1 = &ATL::CComObject<CPXWizardRegistration>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection((ATL::CComSafeDeleteCriticalSection *)(a1 + 16));
}

```

## disassembly

```asm
0x180002cac  push    rbx
0x180002cae  sub     rsp, 20h
0x180002cb2  mov     dword ptr [rcx+8], 0C0000001h
0x180002cb9  lea     rax, ??_7?$CComObject@VCPXWizardRegistration@@@ATL@@6B@; const ATL::CComObject<CPXWizardRegistration>::`vftable'
0x180002cc0  mov     [rcx], rax
0x180002cc3  mov     rbx, rcx
0x180002cc6  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180002ccd  mov     rax, [rcx]
0x180002cd0  mov     rax, [rax+10h]
0x180002cd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002cd9  lea     rcx, [rbx+10h]; this
0x180002cdd  add     rsp, 20h
0x180002ce1  pop     rbx
0x180002ce2  jmp     ??1CComSafeDeleteCriticalSection@ATL@@QEAA@XZ; ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(void)
```
