# ATL::AtlComQIPtrAssign(IUnknown * *,IUnknown *,_GUID const &)

- ea: `0x18000df08`
- end: `0x18000df6b`
- name: `?AtlComQIPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@AEBU_GUID@@@Z`
- size: `99`
- prototype: `struct IUnknown *__fastcall(struct IUnknown **, struct IUnknown *, const struct _GUID *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000d000`

## callees

- `0x18000df08`
- `0x180021010`

## pseudocode

```c
struct IUnknown *__fastcall ATL::AtlComQIPtrAssign(struct IUnknown **a1, struct IUnknown *a2, const struct _GUID *a3)
{
  struct IUnknown *v3; // r9
  __int64 v5; // rdi

  v3 = a2;
  if ( !a1 )
    return 0;
  v5 = (__int64)*a1;
  *a1 = 0;
  if ( a2 )
    ((void (__fastcall *)(struct IUnknown *, const struct _GUID *, struct IUnknown **))a2->lpVtbl->QueryInterface)(
      a2,
      a3,
      a1);
  if ( v5 )
    (*(void (__fastcall **)(__int64, struct IUnknown *, const struct _GUID *, struct IUnknown *))(*(_QWORD *)v5 + 16LL))(
      v5,
      a2,
      a3,
      v3);
  return *a1;
}

```

## disassembly

```asm
0x18000df08  mov     [rsp+arg_0], rbx
0x18000df0d  push    rdi
0x18000df0e  sub     rsp, 20h
0x18000df12  mov     r10, r8
0x18000df15  mov     r9, rdx
0x18000df18  mov     rbx, rcx
0x18000df1b  test    rcx, rcx
0x18000df1e  jz      short loc_18000DF56
0x18000df20  mov     rdi, [rcx]
0x18000df23  mov     qword ptr [rcx], 0
0x18000df2a  test    rdx, rdx
0x18000df2d  jz      short loc_18000DF43
0x18000df2f  mov     rax, [rdx]
0x18000df32  mov     r8, rcx
0x18000df35  mov     rdx, r10
0x18000df38  mov     rcx, r9
0x18000df3b  mov     rax, [rax]
0x18000df3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000df43  test    rdi, rdi
0x18000df46  jnz     short loc_18000DF5A
0x18000df48  mov     rax, [rbx]
0x18000df4b  mov     rbx, [rsp+28h+arg_0]
0x18000df50  add     rsp, 20h
0x18000df54  pop     rdi
0x18000df55  retn
0x18000df56  xor     eax, eax
0x18000df58  jmp     short loc_18000DF4B
0x18000df5a  mov     rax, [rdi]
0x18000df5d  mov     rcx, rdi
0x18000df60  mov     rax, [rax+10h]
0x18000df64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000df69  jmp     short loc_18000DF48
```
