# ATL::CComContainedObject<CWdsSimpleDeviceController>::QueryInterface(_GUID const &,void * *)

- ea: `0x180004000`
- end: `0x18000400f`
- name: `?QueryInterface@?$CComContainedObject@VCWdsSimpleDeviceController@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `15`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180004020`

## callees

- `0x18000d010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CWdsSimpleDeviceController>::QueryInterface(__int64 a1)
{
  return (***(__int64 (__fastcall ****)(_QWORD))(a1 + 16))(*(_QWORD *)(a1 + 16));
}

```

## disassembly

```asm
0x180004000  mov     rcx, [rcx+10h]
0x180004004  mov     rax, [rcx]
0x180004007  mov     rax, [rax]
0x18000400a  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
