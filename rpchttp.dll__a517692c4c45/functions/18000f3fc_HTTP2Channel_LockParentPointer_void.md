# HTTP2Channel::LockParentPointer(void)

- ea: `0x18000f3fc`
- end: `0x18000f431`
- name: `?LockParentPointer@HTTP2Channel@@QEAAPEAVHTTP2VirtualConnection@@XZ`
- size: `53`
- prototype: `struct HTTP2VirtualConnection *__fastcall(HTTP2Channel *__hidden this)`
- caller_count: `18`
- callee_count: `2`
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

- `0x18000f3fc`
- `0x180025010`

## pseudocode

```c
struct HTTP2VirtualConnection *__fastcall HTTP2Channel::LockParentPointer(HTTP2Channel *this)
{
  __int64 v1; // rbx

  _InterlockedIncrement((volatile signed __int32 *)this + 14);
  v1 = *((_QWORD *)this + 6);
  if ( v1 )
    (*((void (**)(void))pRuntimeImportTable + 77))();
  else
    _InterlockedDecrement((volatile signed __int32 *)this + 14);
  return (struct HTTP2VirtualConnection *)v1;
}

```

## disassembly

```asm
0x18000f3fc  push    rbx
0x18000f3fe  sub     rsp, 20h
0x18000f402  lock inc dword ptr [rcx+38h]
0x18000f406  mov     rbx, [rcx+30h]
0x18000f40a  test    rbx, rbx
0x18000f40d  jnz     short loc_18000F415
0x18000f40f  lock dec dword ptr [rcx+38h]
0x18000f413  jmp     short loc_18000F428
0x18000f415  mov     rcx, cs:?pRuntimeImportTable@@3PEAU_RUNTIME_IMPORT_TABLE@@EA; _RUNTIME_IMPORT_TABLE * pRuntimeImportTable
0x18000f41c  mov     rax, [rcx+268h]
0x18000f423  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f428  mov     rax, rbx
0x18000f42b  add     rsp, 20h
0x18000f42f  pop     rbx
0x18000f430  retn
```
