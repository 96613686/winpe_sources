# ATL::CComContainedObject<CWLIDFDProv>::`vector deleting destructor'(uint)

- ea: `0x1800058b0`
- end: `0x1800058e4`
- name: `??_E?$CComContainedObject@VCWLIDFDProv@@@ATL@@UEAAPEAXI@Z`
- size: `52`
- prototype: `CWLIDFDProv *__fastcall(CWLIDFDProv *Block, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180002814`
- `0x18000579c`
- `0x1800058b0`

## pseudocode

```c
CWLIDFDProv *__fastcall ATL::CComContainedObject<CWLIDFDProv>::`vector deleting destructor'(
        CWLIDFDProv *Block,
        char a2)
{
  CWLIDFDProv::~CWLIDFDProv(Block);
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x1800058b0  mov     [rsp+arg_0], rbx
0x1800058b5  push    rdi
0x1800058b6  sub     rsp, 20h
0x1800058ba  mov     ebx, edx
0x1800058bc  mov     rdi, rcx
0x1800058bf  call    ??1CWLIDFDProv@@UEAA@XZ; CWLIDFDProv::~CWLIDFDProv(void)
0x1800058c4  test    bl, 1
0x1800058c7  jz      short loc_1800058D6
0x1800058c9  mov     edx, 90h
0x1800058ce  mov     rcx, rdi; Block
0x1800058d1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800058d6  mov     rbx, [rsp+28h+arg_0]
0x1800058db  mov     rax, rdi
0x1800058de  add     rsp, 20h
0x1800058e2  pop     rdi
0x1800058e3  retn
```
