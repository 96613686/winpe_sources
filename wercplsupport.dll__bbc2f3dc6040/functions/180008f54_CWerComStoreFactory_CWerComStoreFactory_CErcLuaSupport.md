# CWerComStoreFactory::CWerComStoreFactory(CErcLuaSupport *)

- ea: `0x180008f54`
- end: `0x180008fa8`
- name: `??0CWerComStoreFactory@@QEAA@PEAVCErcLuaSupport@@@Z`
- size: `84`
- prototype: `CWerComStoreFactory *__fastcall(CWerComStoreFactory *__hidden this, struct CErcLuaSupport *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180002470`

## callees

- `0x1800073d4`
- `0x180008f54`
- `0x180013010`

## pseudocode

```c
CWerComStoreFactory *__fastcall CWerComStoreFactory::CWerComStoreFactory(
        CWerComStoreFactory *this,
        struct CErcLuaSupport *a2)
{
  CManagedObj::CManagedObj(this);
  *((_QWORD *)this + 4) = a2;
  *(_QWORD *)this = &CWerComStoreFactory::`vftable'{for `CManagedObj'};
  *((_QWORD *)this + 3) = &CWerComStoreFactory::`vftable'{for `IWerStoreFactory'};
  if ( a2 )
    (*(void (__fastcall **)(struct CErcLuaSupport *))(*(_QWORD *)a2 + 8LL))(a2);
  _InterlockedIncrement((volatile signed __int32 *)this + 2);
  return this;
}

```

## disassembly

```asm
0x180008f54  mov     [rsp+arg_0], rbx
0x180008f59  push    rdi
0x180008f5a  sub     rsp, 20h
0x180008f5e  mov     rdi, rdx
0x180008f61  mov     rbx, rcx
0x180008f64  call    ??0CManagedObj@@QEAA@XZ; CManagedObj::CManagedObj(void)
0x180008f69  mov     [rbx+20h], rdi
0x180008f6d  lea     rax, ??_7CWerComStoreFactory@@6BCManagedObj@@@; const CWerComStoreFactory::`vftable'{for `CManagedObj'}
0x180008f74  mov     [rbx], rax
0x180008f77  lea     rax, ??_7CWerComStoreFactory@@6BIWerStoreFactory@@@; const CWerComStoreFactory::`vftable'{for `IWerStoreFactory'}
0x180008f7e  mov     [rbx+18h], rax
0x180008f82  test    rdi, rdi
0x180008f85  jz      short loc_180008F96
0x180008f87  mov     rax, [rdi]
0x180008f8a  mov     rcx, rdi
0x180008f8d  mov     rax, [rax+8]
0x180008f91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f96  lock inc dword ptr [rbx+8]
0x180008f9a  mov     rax, rbx
0x180008f9d  mov     rbx, [rsp+28h+arg_0]
0x180008fa2  add     rsp, 20h
0x180008fa6  pop     rdi
0x180008fa7  retn
```
