# _VSS_MGMT_OBJECT_PROP_Copy::copyDiffArea_::_1_::catch$3

- ea: `0x18004963d`
- end: `0x180049695`
- name: `_VSS_MGMT_OBJECT_PROP_Copy::copyDiffArea_::_1_::catch$3`
- size: `88`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180035360`

## string_xrefs

- `0x180049668`: `PRPCOPYC`
- `0x18004966f`: `base\stor\vss\modules\prop\copy.cxx`
- `0x18004965c`: `VSS_MGMT_OBJECT_PROP_Copy::copyDiffArea`

## pseudocode

```c
void __fastcall __noreturn VSS_MGMT_OBJECT_PROP_Copy::copyDiffArea_::_1_::catch_3(__int64 a1, __int64 a2)
{
  CVssFunctionTracer::HandleComException(
    (CVssFunctionTracer *)(a2 + 96),
    *(struct _com_error **)(a2 + 72),
    L"base\\stor\\vss\\modules\\prop\\copy.cxx",
    L"PRPCOPYC",
    L"VSS_MGMT_OBJECT_PROP_Copy::copyDiffArea",
    0x11Cu,
    *(_DWORD *)(a2 + 132));
}

```

## disassembly

```asm
0x18004963d  mov     [rsp+arg_8], rdx
0x180049642  push    rbp
0x180049643  sub     rsp, 40h
0x180049647  mov     rbp, rdx
0x18004964a  mov     eax, [rbp+84h]
0x180049650  mov     [rsp+48h+var_18], eax; unsigned int
0x180049654  mov     [rsp+48h+var_20], 11Ch; unsigned int
0x18004965c  lea     rax, aVssMgmtObjectP_0; "VSS_MGMT_OBJECT_PROP_Copy::copyDiffArea"
0x180049663  mov     [rsp+48h+var_28], rax; unsigned __int16 *
0x180049668  lea     r9, aPrpcopyc; "PRPCOPYC"
0x18004966f  lea     r8, aBaseStorVssMod_17; "base\\stor\\vss\\modules\\prop\\copy.cx"...
0x180049676  mov     rdx, [rbp+48h]; struct _com_error *
0x18004967a  lea     rcx, [rbp+60h]; this
0x18004967e  call    ?HandleComException@CVssFunctionTracer@@QEAAXAEAV_com_error@@PEBG11KK@Z; CVssFunctionTracer::HandleComException(_com_error &,ushort const *,ushort const *,ushort const *,ulong,ulong)
0x180049684  mov     rax, 0
0x18004968e  add     rsp, 40h
0x180049692  pop     rbp
0x180049693  retn
```
