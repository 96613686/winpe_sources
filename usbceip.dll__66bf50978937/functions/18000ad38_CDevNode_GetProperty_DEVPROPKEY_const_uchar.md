# CDevNode::GetProperty(_DEVPROPKEY const &,uchar &)

- ea: `0x18000ad38`
- end: `0x18000ad8e`
- name: `?GetProperty@CDevNode@@QEAAXAEBU_DEVPROPKEY@@AEAE@Z`
- size: `86`
- prototype: `void __fastcall(CDevNode *this, const struct _DEVPROPKEY *, bool *)`
- caller_count: `7`
- callee_count: `4`
- tags: ``

## callers

- `0x180004388`
- `0x180005a48`
- `0x180006d2c`
- `0x180007b44`
- `0x180008518`
- `0x180008ac0`
- `0x18000b2e0`

## callees

- `0x180004060`
- `0x1800040cc`
- `0x18000ad38`
- `0x18000b464`

## pseudocode

```c
void __fastcall CDevNode::GetProperty(CDevNode *this, const struct _DEVPROPKEY *a2, bool *a3)
{
  __int64 v4; // rdx
  _QWORD *v5; // r10
  _QWORD *v6; // rcx
  __int64 v7[5]; // [rsp+20h] [rbp-28h] BYREF
  int v8; // [rsp+68h] [rbp+20h] BYREF

  std::vector<_bstr_t>::vector<_bstr_t>(v7);
  v8 = 0;
  CDevNode::QueryDeviceProperty(v5, v4, (__int64)&v8, v7);
  v6 = (_QWORD *)v7[0];
  *a3 = *(_BYTE *)v7[0] != 0;
  if ( v6 )
    std::_Deallocate<16>(v6, v7[2] - (_QWORD)v6);
}

```

## disassembly

```asm
0x18000ad38  push    rbx
0x18000ad3a  sub     rsp, 40h
0x18000ad3e  mov     rbx, r8
0x18000ad41  mov     r10, rcx
0x18000ad44  lea     rcx, [rsp+48h+var_28]
0x18000ad49  call    ??0?$vector@V_bstr_t@@V?$allocator@V_bstr_t@@@std@@@std@@QEAA@XZ; std::vector<_bstr_t>::vector<_bstr_t>(void)
0x18000ad4e  nop
0x18000ad4f  mov     [rsp+48h+arg_18], 0
0x18000ad57  lea     r9, [rsp+48h+var_28]
0x18000ad5c  lea     r8, [rsp+48h+arg_18]
0x18000ad61  mov     rcx, r10
0x18000ad64  call    ?QueryDeviceProperty@CDevNode@@AEAAXAEBU_DEVPROPKEY@@AEAKAEAV?$vector@EV?$allocator@E@std@@@std@@@Z; CDevNode::QueryDeviceProperty(_DEVPROPKEY const &,ulong &,std::vector<uchar> &)
0x18000ad69  mov     rcx, [rsp+48h+var_28]
0x18000ad6e  cmp     byte ptr [rcx], 0
0x18000ad71  setnz   al
0x18000ad74  mov     [rbx], al
0x18000ad76  test    rcx, rcx
0x18000ad79  jz      short loc_18000AD88
0x18000ad7b  mov     rdx, [rsp+48h+var_18]
0x18000ad80  sub     rdx, rcx
0x18000ad83  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000ad88  add     rsp, 40h
0x18000ad8c  pop     rbx
0x18000ad8d  retn
```
