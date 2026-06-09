# ATL::CComContainedObject<CFciPropertiesShellExt>::QueryInterface(_GUID const &,void * *)

- ea: `0x1800145c0`
- end: `0x1800145d9`
- name: `?QueryInterface@?$CComContainedObject@VCFciPropertiesShellExt@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `25`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800145e0`

## callees

- `0x180020010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CFciPropertiesShellExt>::QueryInterface(__int64 a1)
{
  return (***(__int64 (__fastcall ****)(_QWORD))(a1 + 16))(*(_QWORD *)(a1 + 16));
}

```

## disassembly

```asm
0x1800145c0  sub     rsp, 28h
0x1800145c4  mov     rcx, [rcx+10h]
0x1800145c8  mov     rax, [rcx]
0x1800145cb  mov     rax, [rax]
0x1800145ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800145d3  nop
0x1800145d4  add     rsp, 28h
0x1800145d8  retn
```
