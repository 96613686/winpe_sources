# ATL::CComObjectCached<ATL::CComClassFactory>::`scalar deleting destructor'(uint)

- ea: `0x1800036c8`
- end: `0x1800036e7`
- name: `??_G?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@QEAAPEAXI@Z`
- size: `31`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180003960`
- `0x180003d90`

## callees

- `0x180001cc8`
- `0x1800035fc`

## pseudocode

```c
void *__fastcall ATL::CComObjectCached<ATL::CComClassFactory>::`scalar deleting destructor'(void *Block)
{
  ATL::CComObjectCached<ATL::CComClassFactory>::~CComObjectCached<ATL::CComClassFactory>();
  operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x1800036c8  push    rbx
0x1800036ca  sub     rsp, 20h
0x1800036ce  mov     rbx, rcx
0x1800036d1  call    ??1?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@QEAA@XZ; ATL::CComObjectCached<ATL::CComClassFactory>::~CComObjectCached<ATL::CComClassFactory>(void)
0x1800036d6  mov     rcx, rbx; Block
0x1800036d9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800036de  mov     rax, rbx
0x1800036e1  add     rsp, 20h
0x1800036e5  pop     rbx
0x1800036e6  retn
```
