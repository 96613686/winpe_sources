# CDevNode::GetProperty(_DEVPROPKEY const &,_bstr_t &)

- ea: `0x18000ae48`
- end: `0x18000aea4`
- name: `?GetProperty@CDevNode@@QEAAXAEBU_DEVPROPKEY@@AEAV_bstr_t@@@Z`
- size: `92`
- prototype: `void __fastcall(CDevNode *__hidden this, const struct _DEVPROPKEY *, struct _bstr_t *)`
- caller_count: `9`
- callee_count: `5`
- tags: ``

## callers

- `0x1800072b4`
- `0x180007b44`
- `0x180008290`
- `0x180008730`
- `0x180009260`
- `0x18000ab84`
- `0x18000aeac`
- `0x18000b5c8`
- `0x18000b96c`

## callees

- `0x180004060`
- `0x1800040cc`
- `0x180007afc`
- `0x18000ae48`
- `0x18000b464`

## pseudocode

```c
void __fastcall CDevNode::GetProperty(CDevNode *this, const struct _DEVPROPKEY *a2, struct _bstr_t *a3)
{
  __int64 v4; // rdx
  _QWORD *v5; // r10
  _QWORD *v6[5]; // [rsp+20h] [rbp-28h] BYREF
  int v7; // [rsp+68h] [rbp+20h] BYREF

  std::vector<_bstr_t>::vector<_bstr_t>(v6);
  v7 = 0;
  CDevNode::QueryDeviceProperty(v5, v4, (__int64)&v7, (__int64 *)v6);
  _bstr_t::operator=(a3, (const unsigned __int16 *)v6[0]);
  if ( v6[0] )
    std::_Deallocate<16>(v6[0], (char *)v6[2] - (char *)v6[0]);
}

```

## disassembly

```asm
0x18000ae48  push    rbx
0x18000ae4a  sub     rsp, 40h
0x18000ae4e  mov     rbx, r8
0x18000ae51  mov     r10, rcx
0x18000ae54  lea     rcx, [rsp+48h+var_28]
0x18000ae59  call    ??0?$vector@V_bstr_t@@V?$allocator@V_bstr_t@@@std@@@std@@QEAA@XZ; std::vector<_bstr_t>::vector<_bstr_t>(void)
0x18000ae5e  nop
0x18000ae5f  mov     [rsp+48h+arg_18], 0
0x18000ae67  lea     r9, [rsp+48h+var_28]
0x18000ae6c  lea     r8, [rsp+48h+arg_18]
0x18000ae71  mov     rcx, r10
0x18000ae74  call    ?QueryDeviceProperty@CDevNode@@AEAAXAEBU_DEVPROPKEY@@AEAKAEAV?$vector@EV?$allocator@E@std@@@std@@@Z; CDevNode::QueryDeviceProperty(_DEVPROPKEY const &,ulong &,std::vector<uchar> &)
0x18000ae79  mov     rdx, [rsp+48h+var_28]
0x18000ae7e  mov     rcx, rbx
0x18000ae81  call    ??4_bstr_t@@QEAAAEAV0@PEBG@Z; _bstr_t::operator=(ushort const *)
0x18000ae86  nop
0x18000ae87  mov     rcx, [rsp+48h+var_28]
0x18000ae8c  test    rcx, rcx
0x18000ae8f  jz      short loc_18000AE9E
0x18000ae91  mov     rdx, [rsp+48h+var_18]
0x18000ae96  sub     rdx, rcx
0x18000ae99  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000ae9e  add     rsp, 40h
0x18000aea2  pop     rbx
0x18000aea3  retn
```
