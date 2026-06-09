# CTDCCtl::UpdateReadyState(long)

- ea: `0x1800097d4`
- end: `0x180009816`
- name: `?UpdateReadyState@CTDCCtl@@QEAAXJ@Z`
- size: `66`
- prototype: `void __fastcall(CTDCCtl *__hidden this, int)`
- caller_count: `3`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180006c40`
- `0x180007780`
- `0x18000a740`

## callees

- `0x180005504`
- `0x180005670`
- `0x1800097d4`
- `0x180015010`

## pseudocode

```c
void __fastcall CTDCCtl::UpdateReadyState(CTDCCtl *this)
{
  __int64 v2; // rcx

  v2 = *((_QWORD *)this + 70);
  if ( v2 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 160LL))(v2);
  }
  else
  {
    ATL::CComControl<CTDCCtl,ATL::CWindowImpl<CTDCCtl,ATL::CWindow,ATL::CWinTraits<1442840576,0>>>::FireOnChanged((__int64)this);
    CProxyITDCCtlEvents<CTDCCtl>::FireOnReadyStateChanged((char *)this + 280);
  }
}

```

## disassembly

```asm
0x1800097d4  push    rbx
0x1800097d6  sub     rsp, 20h
0x1800097da  mov     rbx, rcx
0x1800097dd  mov     rcx, [rcx+230h]
0x1800097e4  test    rcx, rcx
0x1800097e7  jz      short loc_1800097FD
0x1800097e9  mov     rax, [rcx]
0x1800097ec  mov     rax, [rax+0A0h]
0x1800097f3  add     rsp, 20h
0x1800097f7  pop     rbx
0x1800097f8  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x1800097fd  mov     rcx, rbx
0x180009800  call    ?FireOnChanged@?$CComControl@VCTDCCtl@@V?$CWindowImpl@VCTDCCtl@@VCWindow@ATL@@V?$CWinTraits@$0FGAAAAAA@$0A@@3@@ATL@@@ATL@@QEAAJJ@Z; ATL::CComControl<CTDCCtl,ATL::CWindowImpl<CTDCCtl,ATL::CWindow,ATL::CWinTraits<1442840576,0>>>::FireOnChanged(long)
0x180009805  lea     rcx, [rbx+118h]
0x18000980c  add     rsp, 20h
0x180009810  pop     rbx
0x180009811  jmp     ?FireOnReadyStateChanged@?$CProxyITDCCtlEvents@VCTDCCtl@@@@QEAAXXZ; CProxyITDCCtlEvents<CTDCCtl>::FireOnReadyStateChanged(void)
```
