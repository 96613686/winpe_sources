# CEventBroker::STDLoadStarted(ATL::CComObject<CMyBindStatusCallback<CTDCCtl>> *,uchar)

- ea: `0x18000e8b0`
- end: `0x18000e8b7`
- name: `?STDLoadStarted@CEventBroker@@UEAAJPEAV?$CComObject@V?$CMyBindStatusCallback@VCTDCCtl@@@@@ATL@@E@Z`
- size: `7`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
__int64 __fastcall CEventBroker::STDLoadStarted(__int64 a1, __int64 a2)
{
  *(_QWORD *)(a1 + 8) = a2;
  return 0;
}

```

## disassembly

```asm
0x18000e8b0  mov     [rcx+8], rdx
0x18000e8b4  xor     eax, eax
0x18000e8b6  retn
```
