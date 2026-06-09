# ATL::CComObject<CWLIDFDProv>::`scalar deleting destructor'(uint)

- ea: `0x1800058f0`
- end: `0x180005924`
- name: `??_G?$CComObject@VCWLIDFDProv@@@ATL@@UEAAPEAXI@Z`
- size: `52`
- prototype: `CWLIDFDProv *__fastcall(CWLIDFDProv *Block, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180002814`
- `0x18000544c`
- `0x1800058f0`

## pseudocode

```c
CWLIDFDProv *__fastcall ATL::CComObject<CWLIDFDProv>::`scalar deleting destructor'(CWLIDFDProv *Block, char a2)
{
  ATL::CComObject<CWLIDFDProv>::~CComObject<CWLIDFDProv>(Block);
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x1800058f0  mov     [rsp+arg_0], rbx
0x1800058f5  push    rdi
0x1800058f6  sub     rsp, 20h
0x1800058fa  mov     ebx, edx
0x1800058fc  mov     rdi, rcx
0x1800058ff  call    ??1?$CComObject@VCWLIDFDProv@@@ATL@@UEAA@XZ; ATL::CComObject<CWLIDFDProv>::~CComObject<CWLIDFDProv>(void)
0x180005904  test    bl, 1
0x180005907  jz      short loc_180005916
0x180005909  mov     edx, 90h
0x18000590e  mov     rcx, rdi; Block
0x180005911  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180005916  mov     rbx, [rsp+28h+arg_0]
0x18000591b  mov     rax, rdi
0x18000591e  add     rsp, 20h
0x180005922  pop     rdi
0x180005923  retn
```
