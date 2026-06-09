# ATL::CComAggObject<CPXWizardTypeRegistration>::~CComAggObject<CPXWizardTypeRegistration>(void)

- ea: `0x180002bfc`
- end: `0x180002c37`
- name: `??1?$CComAggObject@VCPXWizardTypeRegistration@@@ATL@@UEAA@XZ`
- size: `59`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002ea0`

## callees

- `0x180002d74`
- `0x180013010`

## pseudocode

```c
void __fastcall ATL::CComAggObject<CPXWizardTypeRegistration>::~CComAggObject<CPXWizardTypeRegistration>(__int64 a1)
{
  *(_DWORD *)(a1 + 8) = -1073741823;
  *(_QWORD *)a1 = &ATL::CComAggObject<CPXWizardTypeRegistration>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection((ATL::CComSafeDeleteCriticalSection *)(a1 + 40));
}

```

## disassembly

```asm
0x180002bfc  push    rbx
0x180002bfe  sub     rsp, 20h
0x180002c02  mov     dword ptr [rcx+8], 0C0000001h
0x180002c09  lea     rax, ??_7?$CComAggObject@VCPXWizardTypeRegistration@@@ATL@@6B@; const ATL::CComAggObject<CPXWizardTypeRegistration>::`vftable'
0x180002c10  mov     [rcx], rax
0x180002c13  mov     rbx, rcx
0x180002c16  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180002c1d  mov     rax, [rcx]
0x180002c20  mov     rax, [rax+10h]
0x180002c24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c29  lea     rcx, [rbx+28h]; this
0x180002c2d  add     rsp, 20h
0x180002c31  pop     rbx
0x180002c32  jmp     ??1CComSafeDeleteCriticalSection@ATL@@QEAA@XZ; ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(void)
```
