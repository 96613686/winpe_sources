# ATL::CComObjectCached<ATL::CComClassFactory>::`scalar deleting destructor'(uint)

- ea: `0x18002602c`
- end: `0x180026050`
- name: `??_G?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@QEAAPEAXI@Z`
- size: `36`
- prototype: `void *__fastcall(void *Block)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180026810`
- `0x180026bc0`

## callees

- `0x180002360`
- `0x180025880`

## pseudocode

```c
void *__fastcall ATL::CComObjectCached<ATL::CComClassFactory>::`scalar deleting destructor'(void *Block)
{
  ATL::CComObjectCached<ATL::CComClassFactory>::~CComObjectCached<ATL::CComClassFactory>((__int64)Block);
  operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x18002602c  push    rbx
0x18002602e  sub     rsp, 20h
0x180026032  mov     rbx, rcx
0x180026035  call    ??1?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@QEAA@XZ; ATL::CComObjectCached<ATL::CComClassFactory>::~CComObjectCached<ATL::CComClassFactory>(void)
0x18002603a  mov     edx, 48h ; 'H'
0x18002603f  mov     rcx, rbx; Block
0x180026042  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180026047  mov     rax, rbx
0x18002604a  add     rsp, 20h
0x18002604e  pop     rbx
0x18002604f  retn
```
