# ATL::CComContainedObject<CXmlContentFilter>::QueryInterface(_GUID const &,void * *)

- ea: `0x180012170`
- end: `0x180012189`
- name: `?QueryInterface@?$CComContainedObject@VCXmlContentFilter@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `25`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180012190`
- `0x1800121a0`

## callees

- `0x180017010`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ATL::CComContainedObject<CXmlContentFilter>::QueryInterface(__int64 a1)
{
  return (***(__int64 (__fastcall ****)(_QWORD))(a1 + 24))(*(_QWORD *)(a1 + 24));
}

```

## disassembly

```asm
0x180012170  sub     rsp, 28h
0x180012174  mov     rcx, [rcx+18h]
0x180012178  mov     rax, [rcx]
0x18001217b  mov     rax, [rax]
0x18001217e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012183  nop
0x180012184  add     rsp, 28h
0x180012188  retn
```
