# ATL::CComContainedObject<CElevateWlanUi>::AddRef(void)

- ea: `0x180003010`
- end: `0x180003020`
- name: `?AddRef@?$CComContainedObject@VCElevateWlanUi@@@ATL@@UEAAKXZ`
- size: `16`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18001d010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CElevateWlanUi>::AddRef(__int64 a1)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 8) + 8LL))(*(_QWORD *)(a1 + 8));
}

```

## disassembly

```asm
0x180003010  mov     rcx, [rcx+8]
0x180003014  mov     rax, [rcx]
0x180003017  mov     rax, [rax+8]
0x18000301b  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
