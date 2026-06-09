# CWinTaskClassFactoryT<CUsbCeipTask,1>::`scalar deleting destructor'(uint)

- ea: `0x180003060`
- end: `0x180003092`
- name: `??_G?$CWinTaskClassFactoryT@VCUsbCeipTask@@$00@@UEAAPEAXI@Z`
- size: `50`
- prototype: `_QWORD *__fastcall(_QWORD *, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, loader_planting, service_task`

## callees

- `0x180002434`
- `0x180003060`

## pseudocode

```c
_QWORD *__fastcall CWinTaskClassFactoryT<CUsbCeipTask,1>::`scalar deleting destructor'(_QWORD *a1, char a2)
{
  *a1 = &CWinTaskClassFactoryT<CUsbCeipTask,1>::`vftable';
  _InterlockedDecrement(&CWinTaskHandler::s_cInstances);
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x180003060  push    rbx
0x180003062  sub     rsp, 20h
0x180003066  lea     rax, ??_7?$CWinTaskClassFactoryT@VCUsbCeipTask@@$00@@6B@; const CWinTaskClassFactoryT<CUsbCeipTask,1>::`vftable'
0x18000306d  mov     rbx, rcx
0x180003070  mov     [rcx], rax
0x180003073  lock dec cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x18000307a  test    dl, 1
0x18000307d  jz      short loc_180003089
0x18000307f  mov     edx, 10h
0x180003084  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180003089  mov     rax, rbx
0x18000308c  add     rsp, 20h
0x180003090  pop     rbx
0x180003091  retn
```
