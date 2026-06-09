# ATL::CComContainedObject<CPXWizardRegistration>::QueryInterface(_GUID const &,void * *)

- ea: `0x1800050b0`
- end: `0x1800050c9`
- name: `?QueryInterface@?$CComContainedObject@VCPXWizardRegistration@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `25`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180013010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CPXWizardRegistration>::QueryInterface(__int64 a1)
{
  return (***(__int64 (__fastcall ****)(_QWORD))(a1 + 8))(*(_QWORD *)(a1 + 8));
}

```

## disassembly

```asm
0x1800050b0  sub     rsp, 28h
0x1800050b4  mov     rcx, [rcx+8]
0x1800050b8  mov     rax, [rcx]
0x1800050bb  mov     rax, [rax]
0x1800050be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800050c3  nop
0x1800050c4  add     rsp, 28h
0x1800050c8  retn
```
