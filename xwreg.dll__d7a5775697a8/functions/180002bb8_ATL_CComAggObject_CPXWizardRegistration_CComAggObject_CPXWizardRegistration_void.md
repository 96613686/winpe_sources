# ATL::CComAggObject<CPXWizardRegistration>::~CComAggObject<CPXWizardRegistration>(void)

- ea: `0x180002bb8`
- end: `0x180002bf3`
- name: `??1?$CComAggObject@VCPXWizardRegistration@@@ATL@@UEAA@XZ`
- size: `59`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002e60`

## callees

- `0x180002d74`
- `0x180013010`

## pseudocode

```c
void __fastcall ATL::CComAggObject<CPXWizardRegistration>::~CComAggObject<CPXWizardRegistration>(__int64 a1)
{
  *(_DWORD *)(a1 + 8) = -1073741823;
  *(_QWORD *)a1 = &ATL::CComAggObject<CPXWizardRegistration>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection((ATL::CComSafeDeleteCriticalSection *)(a1 + 40));
}

```

## disassembly

```asm
0x180002bb8  push    rbx
0x180002bba  sub     rsp, 20h
0x180002bbe  mov     dword ptr [rcx+8], 0C0000001h
0x180002bc5  lea     rax, ??_7?$CComAggObject@VCPXWizardRegistration@@@ATL@@6B@; const ATL::CComAggObject<CPXWizardRegistration>::`vftable'
0x180002bcc  mov     [rcx], rax
0x180002bcf  mov     rbx, rcx
0x180002bd2  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180002bd9  mov     rax, [rcx]
0x180002bdc  mov     rax, [rax+10h]
0x180002be0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002be5  lea     rcx, [rbx+28h]; this
0x180002be9  add     rsp, 20h
0x180002bed  pop     rbx
0x180002bee  jmp     ??1CComSafeDeleteCriticalSection@ATL@@QEAA@XZ; ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(void)
```
