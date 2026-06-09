# ATL::CComContainedObject<CWLIDFDProv>::AddRef(void)

- ea: `0x180005bb0`
- end: `0x180005bca`
- name: `?AddRef@?$CComContainedObject@VCWLIDFDProv@@@ATL@@UEAAKXZ`
- size: `26`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180012010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CWLIDFDProv>::AddRef(__int64 a1)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 8) + 8LL))(*(_QWORD *)(a1 + 8));
}

```

## disassembly

```asm
0x180005bb0  sub     rsp, 28h
0x180005bb4  mov     rcx, [rcx+8]
0x180005bb8  mov     rax, [rcx]
0x180005bbb  mov     rax, [rax+8]
0x180005bbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005bc4  nop
0x180005bc5  add     rsp, 28h
0x180005bc9  retn
```
