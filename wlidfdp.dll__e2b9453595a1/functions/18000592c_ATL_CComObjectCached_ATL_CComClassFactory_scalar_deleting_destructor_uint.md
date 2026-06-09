# ATL::CComObjectCached<ATL::CComClassFactory>::`scalar deleting destructor'(uint)

- ea: `0x18000592c`
- end: `0x180005950`
- name: `??_G?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@QEAAPEAXI@Z`
- size: `36`
- prototype: `void *__fastcall(void *Block)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800062b0`
- `0x1800083e0`

## callees

- `0x180002814`
- `0x18000548c`

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
0x18000592c  push    rbx
0x18000592e  sub     rsp, 20h
0x180005932  mov     rbx, rcx
0x180005935  call    ??1?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@QEAA@XZ; ATL::CComObjectCached<ATL::CComClassFactory>::~CComObjectCached<ATL::CComClassFactory>(void)
0x18000593a  mov     edx, 48h ; 'H'
0x18000593f  mov     rcx, rbx; Block
0x180005942  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180005947  mov     rax, rbx
0x18000594a  add     rsp, 20h
0x18000594e  pop     rbx
0x18000594f  retn
```
