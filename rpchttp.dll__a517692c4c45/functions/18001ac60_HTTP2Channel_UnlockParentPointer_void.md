# HTTP2Channel::UnlockParentPointer(void)

- ea: `0x18001ac60`
- end: `0x18001ac86`
- name: `?UnlockParentPointer@HTTP2Channel@@QEAAXXZ`
- size: `38`
- prototype: `void __fastcall(HTTP2Channel *__hidden this)`
- caller_count: `18`
- callee_count: `1`
- tags: ``

## callers

- `0x180004130`
- `0x180004180`
- `0x1800041d0`
- `0x180005320`
- `0x18000a094`
- `0x18000a184`
- `0x18000a3b4`
- `0x18000a44c`
- `0x18000cda4`
- `0x18000dfe8`
- `0x18000f140`
- `0x18000f1f0`
- `0x18000f74c`
- `0x180010864`
- `0x180011108`
- `0x180017510`
- `0x180018340`
- `0x1800195c0`

## callees

- `0x180025010`

## pseudocode

```c
void __fastcall HTTP2Channel::UnlockParentPointer(HTTP2Channel *this)
{
  (*((void (**)(void))pRuntimeImportTable + 78))();
  _InterlockedDecrement((volatile signed __int32 *)this + 14);
}

```

## disassembly

```asm
0x18001ac60  push    rbx
0x18001ac62  sub     rsp, 20h
0x18001ac66  mov     rax, cs:?pRuntimeImportTable@@3PEAU_RUNTIME_IMPORT_TABLE@@EA; _RUNTIME_IMPORT_TABLE * pRuntimeImportTable
0x18001ac6d  mov     rbx, rcx
0x18001ac70  mov     rax, [rax+270h]
0x18001ac77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ac7c  lock dec dword ptr [rbx+38h]
0x18001ac80  add     rsp, 20h
0x18001ac84  pop     rbx
0x18001ac85  retn
```
