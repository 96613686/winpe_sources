# CWLIDFDProv::InstanceQueryService(IFunctionInstance *,__int64,_GUID const &,_GUID const &,IUnknown * *)

- ea: `0x180007270`
- end: `0x180007276`
- name: `?InstanceQueryService@CWLIDFDProv@@UEAAJPEAUIFunctionInstance@@_JAEBU_GUID@@2PEAPEAUIUnknown@@@Z`
- size: `6`
- prototype: `__int64 __fastcall(CWLIDFDProv *this, struct IFunctionInstance *, __int64, const struct _GUID *)`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task`

## pseudocode

```c
__int64 __fastcall CWLIDFDProv::InstanceQueryService(
        CWLIDFDProv *this,
        struct IFunctionInstance *a2,
        __int64 a3,
        const struct _GUID *a4)
{
  return 2147500033LL;
}

```

## disassembly

```asm
0x180007270  mov     eax, 80004001h
0x180007275  retn
```
