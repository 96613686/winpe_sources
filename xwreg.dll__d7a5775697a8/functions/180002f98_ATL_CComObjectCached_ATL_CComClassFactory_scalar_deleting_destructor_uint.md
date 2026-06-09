# ATL::CComObjectCached<ATL::CComClassFactory>::`scalar deleting destructor'(uint)

- ea: `0x180002f98`
- end: `0x180002fb8`
- name: `??_G?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@QEAAPEAXI@Z`
- size: `32`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180004500`
- `0x180005d60`

## callees

- `0x180002d34`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180002fa9`
- `msvcrt!??3@YAXPEAX@Z` at `0x180002fa9`

## pseudocode

```c
void *__fastcall ATL::CComObjectCached<ATL::CComClassFactory>::`scalar deleting destructor'(void *a1)
{
  ATL::CComObjectCached<ATL::CComClassFactory>::~CComObjectCached<ATL::CComClassFactory>();
  operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x180002f98  push    rbx
0x180002f9a  sub     rsp, 20h
0x180002f9e  mov     rbx, rcx
0x180002fa1  call    ??1?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@QEAA@XZ; ATL::CComObjectCached<ATL::CComClassFactory>::~CComObjectCached<ATL::CComClassFactory>(void)
0x180002fa6  mov     rcx, rbx
0x180002fa9  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180002faf  mov     rax, rbx
0x180002fb2  add     rsp, 20h
0x180002fb6  pop     rbx
0x180002fb7  retn
```
