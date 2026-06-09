# ATL::CComContainedObject<CXmlContentFilter>::AddRef(void)

- ea: `0x1800102f0`
- end: `0x18001030a`
- name: `?AddRef@?$CComContainedObject@VCXmlContentFilter@@@ATL@@UEAAKXZ`
- size: `26`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180010310`
- `0x180010320`

## callees

- `0x180017010`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ATL::CComContainedObject<CXmlContentFilter>::AddRef(__int64 a1)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 24) + 8LL))(*(_QWORD *)(a1 + 24));
}

```

## disassembly

```asm
0x1800102f0  sub     rsp, 28h
0x1800102f4  mov     rcx, [rcx+18h]
0x1800102f8  mov     rax, [rcx]
0x1800102fb  mov     rax, [rax+8]
0x1800102ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010304  nop
0x180010305  add     rsp, 28h
0x180010309  retn
```
