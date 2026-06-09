# CWuaClassFactoryBase::`vector deleting destructor'(uint)

- ea: `0x14000be70`
- end: `0x14000bea4`
- name: `??_ECWuaClassFactoryBase@@MEAAPEAXI@Z`
- size: `52`
- prototype: `void *__fastcall(CWuaClassFactoryBase *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, authz_impersonation`

## callees

- `0x14000be70`
- `0x14000beac`
- `0x14001acf4`

## pseudocode

```c
CWuaClassFactoryBase *__fastcall CWuaClassFactoryBase::`vector deleting destructor'(
        CWuaClassFactoryBase *this,
        char a2)
{
  CWuaClassFactoryBase::~CWuaClassFactoryBase(this);
  if ( (a2 & 1) != 0 )
    operator delete(this, (const struct std::nothrow_t *)0x30);
  return this;
}

```

## disassembly

```asm
0x14000be70  mov     [rsp+arg_0], rbx
0x14000be75  push    rdi
0x14000be76  sub     rsp, 20h
0x14000be7a  mov     ebx, edx
0x14000be7c  mov     rdi, rcx
0x14000be7f  call    ??1CWuaClassFactoryBase@@MEAA@XZ; CWuaClassFactoryBase::~CWuaClassFactoryBase(void)
0x14000be84  test    bl, 1
0x14000be87  jz      short loc_14000BE96
0x14000be89  mov     edx, 30h ; '0'; struct std::nothrow_t *
0x14000be8e  mov     rcx, rdi; void *
0x14000be91  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000be96  mov     rbx, [rsp+28h+arg_0]
0x14000be9b  mov     rax, rdi
0x14000be9e  add     rsp, 20h
0x14000bea2  pop     rdi
0x14000bea3  retn
```
