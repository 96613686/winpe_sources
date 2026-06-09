# ATL::CComContainedObject<CWdsSimpleDeviceController>::Release(void)

- ea: `0x180004e70`
- end: `0x180004e80`
- name: `?Release@?$CComContainedObject@VCWdsSimpleDeviceController@@@ATL@@UEAAKXZ`
- size: `16`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180004e90`

## callees

- `0x18000d010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CWdsSimpleDeviceController>::Release(__int64 a1)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 16) + 16LL))(*(_QWORD *)(a1 + 16));
}

```

## disassembly

```asm
0x180004e70  mov     rcx, [rcx+10h]
0x180004e74  mov     rax, [rcx]
0x180004e77  mov     rax, [rax+10h]
0x180004e7b  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
