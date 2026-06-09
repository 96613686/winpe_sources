# ProxyIoCompletionCallback(_EXTENSION_CONTROL_BLOCK *,void *,ulong,ulong)

- ea: `0x180011230`
- end: `0x180011279`
- name: `?ProxyIoCompletionCallback@@YAXPEAU_EXTENSION_CONTROL_BLOCK@@PEAXKK@Z`
- size: `73`
- prototype: `void(struct _EXTENSION_CONTROL_BLOCK *, void *, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000cee4`
- `0x180011230`
- `0x180025010`

## pseudocode

```c
void __fastcall ProxyIoCompletionCallback(
        struct _EXTENSION_CONTROL_BLOCK *a1,
        HTTP2IISTransportChannel *a2,
        unsigned int a3,
        int a4)
{
  if ( (*((unsigned int (__fastcall **)(struct _EXTENSION_CONTROL_BLOCK *))pRuntimeImportTable + 2))(a1) )
    HTTP2IISTransportChannel::IOCompleted(a2, a3, a4);
}

```

## disassembly

```asm
0x180011230  mov     [rsp+arg_0], rbx
0x180011235  mov     [rsp+arg_8], rsi
0x18001123a  push    rdi
0x18001123b  sub     rsp, 20h
0x18001123f  mov     rax, cs:?pRuntimeImportTable@@3PEAU_RUNTIME_IMPORT_TABLE@@EA; _RUNTIME_IMPORT_TABLE * pRuntimeImportTable
0x180011246  mov     ebx, r9d
0x180011249  mov     edi, r8d
0x18001124c  mov     rsi, rdx
0x18001124f  mov     rax, [rax+10h]
0x180011253  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011258  test    eax, eax
0x18001125a  jz      short loc_180011269
0x18001125c  mov     r8d, ebx; unsigned int
0x18001125f  mov     edx, edi; unsigned int
0x180011261  mov     rcx, rsi; this
0x180011264  call    ?IOCompleted@HTTP2IISTransportChannel@@QEAAXKK@Z; HTTP2IISTransportChannel::IOCompleted(ulong,ulong)
0x180011269  mov     rbx, [rsp+28h+arg_0]
0x18001126e  mov     rsi, [rsp+28h+arg_8]
0x180011273  add     rsp, 20h
0x180011277  pop     rdi
0x180011278  retn
```
