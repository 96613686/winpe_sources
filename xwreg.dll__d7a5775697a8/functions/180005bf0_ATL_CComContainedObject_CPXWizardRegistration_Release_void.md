# ATL::CComContainedObject<CPXWizardRegistration>::Release(void)

- ea: `0x180005bf0`
- end: `0x180005c0a`
- name: `?Release@?$CComContainedObject@VCPXWizardRegistration@@@ATL@@UEAAKXZ`
- size: `26`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180013010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CPXWizardRegistration>::Release(__int64 a1)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 8) + 16LL))(*(_QWORD *)(a1 + 8));
}

```

## disassembly

```asm
0x180005bf0  sub     rsp, 28h
0x180005bf4  mov     rcx, [rcx+8]
0x180005bf8  mov     rax, [rcx]
0x180005bfb  mov     rax, [rax+10h]
0x180005bff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c04  nop
0x180005c05  add     rsp, 28h
0x180005c09  retn
```
