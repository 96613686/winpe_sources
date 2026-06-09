# FreeSendContextAndPossiblyData(HTTP2SendContext *)

- ea: `0x18000aafc`
- end: `0x18000ab3a`
- name: `?FreeSendContextAndPossiblyData@@YAXPEAVHTTP2SendContext@@@Z`
- size: `62`
- prototype: `void __fastcall(struct HTTP2SendContext *)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x18000a44c`
- `0x1800111a4`
- `0x180014850`
- `0x1800183e0`
- `0x180018690`
- `0x180018930`

## callees

- `0x18000aafc`
- `0x180025010`

## pseudocode

```c
void __fastcall FreeSendContextAndPossiblyData(struct HTTP2SendContext *a1)
{
  void (*v2)(void); // rax

  v2 = (void (*)(void))*((_QWORD *)pRuntimeImportTable + 1);
  if ( *((struct HTTP2SendContext **)a1 + 6) != (struct HTTP2SendContext *)((char *)a1 + 104) )
  {
    v2();
    v2 = (void (*)(void))*((_QWORD *)pRuntimeImportTable + 1);
  }
  ((void (__fastcall *)(struct HTTP2SendContext *))v2)(a1);
}

```

## disassembly

```asm
0x18000aafc  push    rbx
0x18000aafe  sub     rsp, 20h
0x18000ab02  mov     rbx, rcx
0x18000ab05  mov     rcx, [rcx+30h]
0x18000ab09  lea     rax, [rbx+68h]
0x18000ab0d  cmp     rcx, rax
0x18000ab10  mov     rax, cs:?pRuntimeImportTable@@3PEAU_RUNTIME_IMPORT_TABLE@@EA; _RUNTIME_IMPORT_TABLE * pRuntimeImportTable
0x18000ab17  mov     rax, [rax+8]
0x18000ab1b  jz      short loc_18000AB2D
0x18000ab1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ab22  mov     rax, cs:?pRuntimeImportTable@@3PEAU_RUNTIME_IMPORT_TABLE@@EA; _RUNTIME_IMPORT_TABLE * pRuntimeImportTable
0x18000ab29  mov     rax, [rax+8]
0x18000ab2d  mov     rcx, rbx
0x18000ab30  add     rsp, 20h
0x18000ab34  pop     rbx
0x18000ab35  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
