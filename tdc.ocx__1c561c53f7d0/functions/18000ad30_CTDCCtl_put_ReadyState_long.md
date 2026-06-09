# CTDCCtl::put_ReadyState(long)

- ea: `0x18000ad30`
- end: `0x18000ad47`
- name: `?put_ReadyState@CTDCCtl@@UEAAJJ@Z`
- size: `23`
- prototype: `__int64 __fastcall(CTDCCtl *__hidden this, int)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180005504`

## pseudocode

```c
__int64 __fastcall CTDCCtl::put_ReadyState(CTDCCtl *this)
{
  ATL::CComControl<CTDCCtl,ATL::CWindowImpl<CTDCCtl,ATL::CWindow,ATL::CWinTraits<1442840576,0>>>::FireOnChanged((__int64)this - 176);
  return 0;
}

```

## disassembly

```asm
0x18000ad30  sub     rsp, 28h
0x18000ad34  add     rcx, 0FFFFFFFFFFFFFF50h
0x18000ad3b  call    ?FireOnChanged@?$CComControl@VCTDCCtl@@V?$CWindowImpl@VCTDCCtl@@VCWindow@ATL@@V?$CWinTraits@$0FGAAAAAA@$0A@@3@@ATL@@@ATL@@QEAAJJ@Z; ATL::CComControl<CTDCCtl,ATL::CWindowImpl<CTDCCtl,ATL::CWindow,ATL::CWinTraits<1442840576,0>>>::FireOnChanged(long)
0x18000ad40  xor     eax, eax
0x18000ad42  add     rsp, 28h
0x18000ad46  retn
```
