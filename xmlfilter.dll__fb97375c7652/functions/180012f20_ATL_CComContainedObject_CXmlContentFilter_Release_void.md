# ATL::CComContainedObject<CXmlContentFilter>::Release(void)

- ea: `0x180012f20`
- end: `0x180012f3a`
- name: `?Release@?$CComContainedObject@VCXmlContentFilter@@@ATL@@UEAAKXZ`
- size: `26`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180012f40`
- `0x180012f50`

## callees

- `0x180017010`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ATL::CComContainedObject<CXmlContentFilter>::Release(__int64 a1)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 24) + 16LL))(*(_QWORD *)(a1 + 24));
}

```

## disassembly

```asm
0x180012f20  sub     rsp, 28h
0x180012f24  mov     rcx, [rcx+18h]
0x180012f28  mov     rax, [rcx]
0x180012f2b  mov     rax, [rax+10h]
0x180012f2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012f34  nop
0x180012f35  add     rsp, 28h
0x180012f39  retn
```
