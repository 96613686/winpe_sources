# ATL::CComContainedObject<CPXWizardRegistration>::AddRef(void)

- ea: `0x1800032c0`
- end: `0x1800032da`
- name: `?AddRef@?$CComContainedObject@VCPXWizardRegistration@@@ATL@@UEAAKXZ`
- size: `26`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180013010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CPXWizardRegistration>::AddRef(__int64 a1)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 8) + 8LL))(*(_QWORD *)(a1 + 8));
}

```

## disassembly

```asm
0x1800032c0  sub     rsp, 28h
0x1800032c4  mov     rcx, [rcx+8]
0x1800032c8  mov     rax, [rcx]
0x1800032cb  mov     rax, [rax+8]
0x1800032cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800032d4  nop
0x1800032d5  add     rsp, 28h
0x1800032d9  retn
```
