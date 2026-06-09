# ATL::CComContainedObject<ATL::CAxHostWindow>::Release(void)

- ea: `0x140007910`
- end: `0x140007920`
- name: `?Release@?$CComContainedObject@VCAxHostWindow@ATL@@@ATL@@UEAAKXZ`
- size: `16`
- prototype: ``
- caller_count: `9`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140007930`
- `0x140007940`
- `0x140007950`
- `0x140007960`
- `0x140007970`
- `0x140007980`
- `0x140007990`
- `0x1400079a0`
- `0x1400079b0`

## callees

- `0x14000f010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<ATL::CAxHostWindow>::Release(__int64 a1)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 88) + 16LL))(*(_QWORD *)(a1 + 88));
}

```

## disassembly

```asm
0x140007910  mov     rcx, [rcx+58h]
0x140007914  mov     rax, [rcx]
0x140007917  mov     rax, [rax+10h]
0x14000791b  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
