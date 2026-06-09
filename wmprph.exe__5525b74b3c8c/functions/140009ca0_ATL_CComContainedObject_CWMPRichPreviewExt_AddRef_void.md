# ATL::CComContainedObject<CWMPRichPreviewExt>::AddRef(void)

- ea: `0x140009ca0`
- end: `0x140009cb0`
- name: `?AddRef@?$CComContainedObject@VCWMPRichPreviewExt@@@ATL@@UEAAKXZ`
- size: `16`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140009cc0`
- `0x140009cd0`
- `0x140009ce0`

## callees

- `0x14000f010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CWMPRichPreviewExt>::AddRef(__int64 a1)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 32) + 8LL))(*(_QWORD *)(a1 + 32));
}

```

## disassembly

```asm
0x140009ca0  mov     rcx, [rcx+20h]
0x140009ca4  mov     rax, [rcx]
0x140009ca7  mov     rax, [rax+8]
0x140009cab  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
