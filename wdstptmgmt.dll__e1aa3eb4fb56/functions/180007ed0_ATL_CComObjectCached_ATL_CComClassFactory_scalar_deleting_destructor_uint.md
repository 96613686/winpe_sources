# ATL::CComObjectCached<ATL::CComClassFactory>::`scalar deleting destructor'(uint)

- ea: `0x180007ed0`
- end: `0x180007ef7`
- name: `??_G?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@QEAAPEAXI@Z`
- size: `39`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800081d0`
- `0x1800087e0`

## callees

- `0x180007dec`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180007ee1`
- `msvcrt!??3@YAXPEAX@Z` at `0x180007ee1`

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
0x180007ed0  push    rbx
0x180007ed2  sub     rsp, 20h
0x180007ed6  mov     rbx, rcx
0x180007ed9  call    ??1?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@QEAA@XZ; ATL::CComObjectCached<ATL::CComClassFactory>::~CComObjectCached<ATL::CComClassFactory>(void)
0x180007ede  mov     rcx, rbx
0x180007ee1  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180007ee8  nop     dword ptr [rax+rax+00h]
0x180007eed  mov     rax, rbx
0x180007ef0  add     rsp, 20h
0x180007ef4  pop     rbx
0x180007ef5  retn
```
