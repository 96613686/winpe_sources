# ATL::CComContainedObject<ATL::CAxHostWindow>::AddRef(void)

- ea: `0x1400029d0`
- end: `0x1400029e0`
- name: `?AddRef@?$CComContainedObject@VCAxHostWindow@ATL@@@ATL@@UEAAKXZ`
- size: `16`
- prototype: ``
- caller_count: `9`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400029f0`
- `0x140002a00`
- `0x140002a10`
- `0x140002a20`
- `0x140002a30`
- `0x140002a40`
- `0x140002a50`
- `0x140002a60`
- `0x140002a70`

## callees

- `0x14000f010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<ATL::CAxHostWindow>::AddRef(__int64 a1)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 88) + 8LL))(*(_QWORD *)(a1 + 88));
}

```

## disassembly

```asm
0x1400029d0  mov     rcx, [rcx+58h]
0x1400029d4  mov     rax, [rcx]
0x1400029d7  mov     rax, [rax+8]
0x1400029db  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
