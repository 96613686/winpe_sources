# RegistryFunctions::`vector deleting destructor'(uint)

- ea: `0x18000fd90`
- end: `0x18000fdbb`
- name: `??_ERegistryFunctions@@UEAAPEAXI@Z`
- size: `43`
- prototype: `RegistryFunctions *__fastcall(RegistryFunctions *this, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, registry_config`

## callees

- `0x180002814`
- `0x18000fd90`

## pseudocode

```c
RegistryFunctions *__fastcall RegistryFunctions::`vector deleting destructor'(RegistryFunctions *this, char a2)
{
  *(_QWORD *)this = &IRegistryFunctions::`vftable';
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x18000fd90  push    rbx
0x18000fd92  sub     rsp, 20h
0x18000fd96  lea     rax, ??_7IRegistryFunctions@@6B@; const IRegistryFunctions::`vftable'
0x18000fd9d  mov     rbx, rcx
0x18000fda0  mov     [rcx], rax
0x18000fda3  test    dl, 1
0x18000fda6  jz      short loc_18000FDB2
0x18000fda8  mov     edx, 8
0x18000fdad  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000fdb2  mov     rax, rbx
0x18000fdb5  add     rsp, 20h
0x18000fdb9  pop     rbx
0x18000fdba  retn
```
