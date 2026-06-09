# ATL::CComContainedObject<CRecoExt>::GetControllingUnknown(void)

- ea: `0x180001990`
- end: `0x180001995`
- name: `?GetControllingUnknown@?$CComContainedObject@VCRecoExt@@@ATL@@UEAAPEAUIUnknown@@XZ`
- size: `5`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CRecoExt>::GetControllingUnknown(__int64 a1)
{
  return *(_QWORD *)(a1 + 64);
}

```

## disassembly

```asm
0x180001990  mov     rax, [rcx+40h]
0x180001994  retn
```
