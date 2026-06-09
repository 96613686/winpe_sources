# ATL::CComContainedObject<CWLIDFDProv>::Release(void)

- ea: `0x180008350`
- end: `0x18000836a`
- name: `?Release@?$CComContainedObject@VCWLIDFDProv@@@ATL@@UEAAKXZ`
- size: `26`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180012010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CWLIDFDProv>::Release(__int64 a1)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 8) + 16LL))(*(_QWORD *)(a1 + 8));
}

```

## disassembly

```asm
0x180008350  sub     rsp, 28h
0x180008354  mov     rcx, [rcx+8]
0x180008358  mov     rax, [rcx]
0x18000835b  mov     rax, [rax+10h]
0x18000835f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008364  nop
0x180008365  add     rsp, 28h
0x180008369  retn
```
