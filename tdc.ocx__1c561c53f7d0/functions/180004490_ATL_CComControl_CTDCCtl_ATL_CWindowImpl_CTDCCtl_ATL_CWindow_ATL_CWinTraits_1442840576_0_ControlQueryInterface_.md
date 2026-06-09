# ATL::CComControl<CTDCCtl,ATL::CWindowImpl<CTDCCtl,ATL::CWindow,ATL::CWinTraits<1442840576,0>>>::ControlQueryInterface(_GUID const &,void * *)

- ea: `0x180004490`
- end: `0x1800044a2`
- name: `?ControlQueryInterface@?$CComControl@VCTDCCtl@@V?$CWindowImpl@VCTDCCtl@@VCWindow@ATL@@V?$CWinTraits@$0FGAAAAAA@$0A@@3@@ATL@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `18`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180015010`

## pseudocode

```c
__int64 __fastcall ATL::CComControl<CTDCCtl,ATL::CWindowImpl<CTDCCtl,ATL::CWindow,ATL::CWinTraits<1442840576,0>>>::ControlQueryInterface(
        __int64 a1)
{
  return (**(__int64 (__fastcall ***)(__int64))(a1 + 176))(a1 + 176);
}

```

## disassembly

```asm
0x180004490  add     rcx, 0B0h
0x180004497  mov     rax, [rcx]
0x18000449a  mov     rax, [rax]
0x18000449d  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
