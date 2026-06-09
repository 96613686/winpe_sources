# ATL::CComContainedObject<ATL::CAxHostWindow>::GetControllingUnknown(void)

- ea: `0x140004a30`
- end: `0x140004a38`
- name: `?GetControllingUnknown@?$CComContainedObject@VCAxHostWindow@ATL@@@ATL@@UEAAPEAUIUnknown@@XZ`
- size: `8`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<ATL::CAxHostWindow>::GetControllingUnknown(__int64 a1)
{
  return *(_QWORD *)(a1 + 152);
}

```

## disassembly

```asm
0x140004a30  mov     rax, [rcx+98h]
0x140004a37  retn
```
