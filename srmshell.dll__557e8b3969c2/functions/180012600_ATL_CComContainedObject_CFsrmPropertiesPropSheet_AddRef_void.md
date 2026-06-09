# ATL::CComContainedObject<CFsrmPropertiesPropSheet>::AddRef(void)

- ea: `0x180012600`
- end: `0x18001261a`
- name: `?AddRef@?$CComContainedObject@VCFsrmPropertiesPropSheet@@@ATL@@UEAAKXZ`
- size: `26`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180020010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CFsrmPropertiesPropSheet>::AddRef(__int64 a1)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 8) + 8LL))(*(_QWORD *)(a1 + 8));
}

```

## disassembly

```asm
0x180012600  sub     rsp, 28h
0x180012604  mov     rcx, [rcx+8]
0x180012608  mov     rax, [rcx]
0x18001260b  mov     rax, [rax+8]
0x18001260f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012614  nop
0x180012615  add     rsp, 28h
0x180012619  retn
```
