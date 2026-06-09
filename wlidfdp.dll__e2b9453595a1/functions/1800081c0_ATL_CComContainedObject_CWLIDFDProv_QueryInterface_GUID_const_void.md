# ATL::CComContainedObject<CWLIDFDProv>::QueryInterface(_GUID const &,void * *)

- ea: `0x1800081c0`
- end: `0x1800081d9`
- name: `?QueryInterface@?$CComContainedObject@VCWLIDFDProv@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `25`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180012010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CWLIDFDProv>::QueryInterface(__int64 a1)
{
  return (***(__int64 (__fastcall ****)(_QWORD))(a1 + 8))(*(_QWORD *)(a1 + 8));
}

```

## disassembly

```asm
0x1800081c0  sub     rsp, 28h
0x1800081c4  mov     rcx, [rcx+8]
0x1800081c8  mov     rax, [rcx]
0x1800081cb  mov     rax, [rax]
0x1800081ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800081d3  nop
0x1800081d4  add     rsp, 28h
0x1800081d8  retn
```
