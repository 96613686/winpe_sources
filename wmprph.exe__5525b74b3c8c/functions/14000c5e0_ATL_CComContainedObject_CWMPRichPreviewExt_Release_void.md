# ATL::CComContainedObject<CWMPRichPreviewExt>::Release(void)

- ea: `0x14000c5e0`
- end: `0x14000c5f0`
- name: `?Release@?$CComContainedObject@VCWMPRichPreviewExt@@@ATL@@UEAAKXZ`
- size: `16`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000c600`
- `0x14000c610`
- `0x14000c620`

## callees

- `0x14000f010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CWMPRichPreviewExt>::Release(__int64 a1)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 32) + 16LL))(*(_QWORD *)(a1 + 32));
}

```

## disassembly

```asm
0x14000c5e0  mov     rcx, [rcx+20h]
0x14000c5e4  mov     rax, [rcx]
0x14000c5e7  mov     rax, [rax+10h]
0x14000c5eb  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
