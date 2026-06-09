# ATL::CComContainedObject<CFciPropertiesShellExt>::AddRef(void)

- ea: `0x1800125d0`
- end: `0x1800125ea`
- name: `?AddRef@?$CComContainedObject@VCFciPropertiesShellExt@@@ATL@@UEAAKXZ`
- size: `26`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800125f0`

## callees

- `0x180020010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CFciPropertiesShellExt>::AddRef(__int64 a1)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 16) + 8LL))(*(_QWORD *)(a1 + 16));
}

```

## disassembly

```asm
0x1800125d0  sub     rsp, 28h
0x1800125d4  mov     rcx, [rcx+10h]
0x1800125d8  mov     rax, [rcx]
0x1800125db  mov     rax, [rax+8]
0x1800125df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800125e4  nop
0x1800125e5  add     rsp, 28h
0x1800125e9  retn
```
