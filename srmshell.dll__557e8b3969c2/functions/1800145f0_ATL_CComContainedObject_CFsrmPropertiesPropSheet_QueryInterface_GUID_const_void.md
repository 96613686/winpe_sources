# ATL::CComContainedObject<CFsrmPropertiesPropSheet>::QueryInterface(_GUID const &,void * *)

- ea: `0x1800145f0`
- end: `0x180014609`
- name: `?QueryInterface@?$CComContainedObject@VCFsrmPropertiesPropSheet@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `25`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180020010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CFsrmPropertiesPropSheet>::QueryInterface(__int64 a1)
{
  return (***(__int64 (__fastcall ****)(_QWORD))(a1 + 8))(*(_QWORD *)(a1 + 8));
}

```

## disassembly

```asm
0x1800145f0  sub     rsp, 28h
0x1800145f4  mov     rcx, [rcx+8]
0x1800145f8  mov     rax, [rcx]
0x1800145fb  mov     rax, [rax]
0x1800145fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014603  nop
0x180014604  add     rsp, 28h
0x180014608  retn
```
