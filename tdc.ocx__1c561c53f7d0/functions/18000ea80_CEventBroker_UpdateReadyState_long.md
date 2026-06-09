# CEventBroker::UpdateReadyState(long)

- ea: `0x18000ea80`
- end: `0x18000eae7`
- name: `?UpdateReadyState@CEventBroker@@UEAAJJ@Z`
- size: `103`
- prototype: `__int64 __fastcall(CEventBroker *__hidden this, int)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180005504`
- `0x180005670`
- `0x18000ea80`

## pseudocode

```c
__int64 __fastcall CEventBroker::UpdateReadyState(CEventBroker *this, int a2)
{
  __int64 v3; // rcx
  __int64 v4; // rdx
  int v5; // eax
  __int64 v6; // rdx
  int v7; // eax

  if ( *((_DWORD *)this + 12) != a2 )
  {
    *((_DWORD *)this + 12) = a2;
    v3 = *((_QWORD *)this + 7);
    if ( v3 )
    {
      ATL::CComControl<CTDCCtl,ATL::CWindowImpl<CTDCCtl,ATL::CWindow,ATL::CWinTraits<1442840576,0>>>::FireOnChanged(v3);
      v4 = *((_QWORD *)this + 7);
      v5 = 0;
      if ( *(_DWORD *)(v4 + 508) + 1 >= 0 )
        v5 = *(_DWORD *)(v4 + 508) + 1;
      *(_DWORD *)(v4 + 508) = v5;
      CProxyITDCCtlEvents<CTDCCtl>::FireOnReadyStateChanged(*((_QWORD *)this + 7) + 280LL);
      v6 = *((_QWORD *)this + 7);
      v7 = 0;
      if ( *(_DWORD *)(v6 + 508) - 1 >= 0 )
        v7 = *(_DWORD *)(v6 + 508) - 1;
      *(_DWORD *)(v6 + 508) = v7;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000ea80  push    rbx
0x18000ea82  sub     rsp, 20h
0x18000ea86  mov     rbx, rcx
0x18000ea89  cmp     [rcx+30h], edx
0x18000ea8c  jz      short loc_18000EADF
0x18000ea8e  mov     [rcx+30h], edx
0x18000ea91  mov     rcx, [rcx+38h]
0x18000ea95  test    rcx, rcx
0x18000ea98  jz      short loc_18000EADF
0x18000ea9a  call    ?FireOnChanged@?$CComControl@VCTDCCtl@@V?$CWindowImpl@VCTDCCtl@@VCWindow@ATL@@V?$CWinTraits@$0FGAAAAAA@$0A@@3@@ATL@@@ATL@@QEAAJJ@Z; ATL::CComControl<CTDCCtl,ATL::CWindowImpl<CTDCCtl,ATL::CWindow,ATL::CWinTraits<1442840576,0>>>::FireOnChanged(long)
0x18000ea9f  mov     rdx, [rbx+38h]
0x18000eaa3  xor     eax, eax
0x18000eaa5  mov     ecx, [rdx+1FCh]
0x18000eaab  add     ecx, 1
0x18000eaae  cmovns  eax, ecx
0x18000eab1  mov     [rdx+1FCh], eax
0x18000eab7  mov     rcx, [rbx+38h]
0x18000eabb  add     rcx, 118h
0x18000eac2  call    ?FireOnReadyStateChanged@?$CProxyITDCCtlEvents@VCTDCCtl@@@@QEAAXXZ; CProxyITDCCtlEvents<CTDCCtl>::FireOnReadyStateChanged(void)
0x18000eac7  mov     rdx, [rbx+38h]
0x18000eacb  xor     eax, eax
0x18000eacd  mov     ecx, [rdx+1FCh]
0x18000ead3  sub     ecx, 1
0x18000ead6  cmovns  eax, ecx
0x18000ead9  mov     [rdx+1FCh], eax
0x18000eadf  xor     eax, eax
0x18000eae1  add     rsp, 20h
0x18000eae5  pop     rbx
0x18000eae6  retn
```
