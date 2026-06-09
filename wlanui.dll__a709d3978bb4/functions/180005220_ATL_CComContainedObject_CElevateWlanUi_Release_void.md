# ATL::CComContainedObject<CElevateWlanUi>::Release(void)

- ea: `0x180005220`
- end: `0x180005230`
- name: `?Release@?$CComContainedObject@VCElevateWlanUi@@@ATL@@UEAAKXZ`
- size: `16`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18001d010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CElevateWlanUi>::Release(__int64 a1)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 8) + 16LL))(*(_QWORD *)(a1 + 8));
}

```

## disassembly

```asm
0x180005220  mov     rcx, [rcx+8]
0x180005224  mov     rax, [rcx]
0x180005227  mov     rax, [rax+10h]
0x18000522b  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
