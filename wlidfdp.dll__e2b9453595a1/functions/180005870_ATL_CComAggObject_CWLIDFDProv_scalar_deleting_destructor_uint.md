# ATL::CComAggObject<CWLIDFDProv>::`scalar deleting destructor'(uint)

- ea: `0x180005870`
- end: `0x1800058a4`
- name: `??_G?$CComAggObject@VCWLIDFDProv@@@ATL@@UEAAPEAXI@Z`
- size: `52`
- prototype: `void *__fastcall(void *Block, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180002814`
- `0x180005408`
- `0x180005870`

## pseudocode

```c
void *__fastcall ATL::CComAggObject<CWLIDFDProv>::`scalar deleting destructor'(void *Block, char a2)
{
  ATL::CComAggObject<CWLIDFDProv>::~CComAggObject<CWLIDFDProv>((__int64)Block);
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x180005870  mov     [rsp+arg_0], rbx
0x180005875  push    rdi
0x180005876  sub     rsp, 20h
0x18000587a  mov     ebx, edx
0x18000587c  mov     rdi, rcx
0x18000587f  call    ??1?$CComAggObject@VCWLIDFDProv@@@ATL@@UEAA@XZ; ATL::CComAggObject<CWLIDFDProv>::~CComAggObject<CWLIDFDProv>(void)
0x180005884  test    bl, 1
0x180005887  jz      short loc_180005896
0x180005889  mov     edx, 0A8h
0x18000588e  mov     rcx, rdi; Block
0x180005891  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180005896  mov     rbx, [rsp+28h+arg_0]
0x18000589b  mov     rax, rdi
0x18000589e  add     rsp, 20h
0x1800058a2  pop     rdi
0x1800058a3  retn
```
