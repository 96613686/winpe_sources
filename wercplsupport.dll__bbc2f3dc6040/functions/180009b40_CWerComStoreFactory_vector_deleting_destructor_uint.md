# CWerComStoreFactory::`vector deleting destructor'(uint)

- ea: `0x180009b40`
- end: `0x180009b6f`
- name: `??_ECWerComStoreFactory@@UEAAPEAXI@Z`
- size: `47`
- prototype: `void *__fastcall(CWerComStoreFactory *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001674`
- `0x1800092f8`
- `0x180009b40`

## pseudocode

```c
CWerComStoreFactory *__fastcall CWerComStoreFactory::`vector deleting destructor'(CWerComStoreFactory *this, char a2)
{
  CWerComStoreFactory::~CWerComStoreFactory(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180009b40  mov     [rsp+arg_0], rbx
0x180009b45  push    rdi
0x180009b46  sub     rsp, 20h
0x180009b4a  mov     ebx, edx
0x180009b4c  mov     rdi, rcx
0x180009b4f  call    ??1CWerComStoreFactory@@UEAA@XZ; CWerComStoreFactory::~CWerComStoreFactory(void)
0x180009b54  test    bl, 1
0x180009b57  jz      short loc_180009B61
0x180009b59  mov     rcx, rdi; Block
0x180009b5c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180009b61  mov     rbx, [rsp+28h+arg_0]
0x180009b66  mov     rax, rdi
0x180009b69  add     rsp, 20h
0x180009b6d  pop     rdi
0x180009b6e  retn
```
