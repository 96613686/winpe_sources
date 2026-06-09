# ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)

- ea: `0x180005c08`
- end: `0x180005c5a`
- name: `?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z`
- size: `82`
- prototype: `struct IUnknown *__fastcall(struct IUnknown **, struct IUnknown *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180007120`

## callees

- `0x180005c08`
- `0x180012010`

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
0x180005c08  mov     [rsp+arg_0], rbx
0x180005c0d  push    rdi
0x180005c0e  sub     rsp, 20h
0x180005c12  mov     rbx, rdx
0x180005c15  mov     rdi, rcx
0x180005c18  test    rcx, rcx
0x180005c1b  jnz     short loc_180005C21
0x180005c1d  xor     eax, eax
0x180005c1f  jmp     short loc_180005C4F
0x180005c21  test    rbx, rbx
0x180005c24  jz      short loc_180005C35
0x180005c26  mov     rax, [rdx]
0x180005c29  mov     rcx, rbx
0x180005c2c  mov     rax, [rax+8]
0x180005c30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c35  mov     rcx, [rdi]
0x180005c38  test    rcx, rcx
0x180005c3b  jz      short loc_180005C49
0x180005c3d  mov     rax, [rcx]
0x180005c40  mov     rax, [rax+10h]
0x180005c44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c49  mov     [rdi], rbx
0x180005c4c  mov     rax, rbx
0x180005c4f  mov     rbx, [rsp+28h+arg_0]
0x180005c54  add     rsp, 20h
0x180005c58  pop     rdi
0x180005c59  retn
```
