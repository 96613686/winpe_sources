# ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)

- ea: `0x18000d578`
- end: `0x18000d5ca`
- name: `?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z`
- size: `82`
- prototype: `struct IUnknown *__fastcall(struct IUnknown **, struct IUnknown *)`
- caller_count: `12`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000e010`
- `0x18000f770`
- `0x18000fc8c`
- `0x18000fd20`
- `0x1800105cc`
- `0x18001369c`
- `0x180014880`
- `0x1800208f0`
- `0x1800222dc`
- `0x180026024`
- `0x18002a510`
- `0x18002a770`

## callees

- `0x18000d578`
- `0x180030010`

## pseudocode

```c
struct IUnknown *__fastcall ATL::AtlComPtrAssign(struct IUnknown **a1, struct IUnknown *a2)
{
  if ( !a1 )
    return 0;
  if ( a2 )
    ((void (__fastcall *)(struct IUnknown *))a2->lpVtbl->AddRef)(a2);
  if ( *a1 )
    ((void (__fastcall *)(_QWORD))(*a1)->lpVtbl->Release)(*a1);
  *a1 = a2;
  return a2;
}

```

## disassembly

```asm
0x18000d578  mov     [rsp+arg_0], rbx
0x18000d57d  push    rdi
0x18000d57e  sub     rsp, 20h
0x18000d582  mov     rbx, rdx
0x18000d585  mov     rdi, rcx
0x18000d588  test    rcx, rcx
0x18000d58b  jnz     short loc_18000D591
0x18000d58d  xor     eax, eax
0x18000d58f  jmp     short loc_18000D5BF
0x18000d591  test    rbx, rbx
0x18000d594  jz      short loc_18000D5A5
0x18000d596  mov     rax, [rdx]
0x18000d599  mov     rcx, rbx
0x18000d59c  mov     rax, [rax+8]
0x18000d5a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d5a5  mov     rcx, [rdi]
0x18000d5a8  test    rcx, rcx
0x18000d5ab  jz      short loc_18000D5B9
0x18000d5ad  mov     rax, [rcx]
0x18000d5b0  mov     rax, [rax+10h]
0x18000d5b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d5b9  mov     [rdi], rbx
0x18000d5bc  mov     rax, rbx
0x18000d5bf  mov     rbx, [rsp+28h+arg_0]
0x18000d5c4  add     rsp, 20h
0x18000d5c8  pop     rdi
0x18000d5c9  retn
```
