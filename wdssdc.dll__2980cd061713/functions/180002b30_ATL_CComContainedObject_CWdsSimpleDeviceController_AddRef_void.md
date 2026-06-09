# ATL::CComContainedObject<CWdsSimpleDeviceController>::AddRef(void)

- ea: `0x180002b30`
- end: `0x180002b40`
- name: `?AddRef@?$CComContainedObject@VCWdsSimpleDeviceController@@@ATL@@UEAAKXZ`
- size: `16`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180002b50`

## callees

- `0x18000d010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CWdsSimpleDeviceController>::AddRef(__int64 a1)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 16) + 8LL))(*(_QWORD *)(a1 + 16));
}

```

## disassembly

```asm
0x180002b30  mov     rcx, [rcx+10h]
0x180002b34  mov     rax, [rcx]
0x180002b37  mov     rax, [rax+8]
0x180002b3b  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
