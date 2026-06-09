# ATL::CComContainedObject<CRecoExt>::Release(void)

- ea: `0x180001cb0`
- end: `0x180001cca`
- name: `?Release@?$CComContainedObject@VCRecoExt@@@ATL@@UEAAKXZ`
- size: `26`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180003400`
- `0x180003410`
- `0x180003420`
- `0x180003430`
- `0x180003440`
- `0x180003450`
- `0x180003460`

## callees

- `0x180010010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CRecoExt>::Release(__int64 a1)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 64) + 16LL))(*(_QWORD *)(a1 + 64));
}

```

## disassembly

```asm
0x180001cb0  sub     rsp, 28h
0x180001cb4  mov     rcx, [rcx+40h]
0x180001cb8  mov     rax, [rcx]
0x180001cbb  mov     rax, [rax+10h]
0x180001cbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001cc4  nop
0x180001cc5  add     rsp, 28h
0x180001cc9  retn
```
