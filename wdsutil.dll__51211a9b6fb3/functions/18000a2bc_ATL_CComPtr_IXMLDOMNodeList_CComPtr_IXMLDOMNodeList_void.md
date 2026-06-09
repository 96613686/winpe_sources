# ATL::CComPtr<IXMLDOMNodeList>::~CComPtr<IXMLDOMNodeList>(void)

- ea: `0x18000a2bc`
- end: `0x18000a2e4`
- name: `??1?$CComPtr@UIXMLDOMNodeList@@@ATL@@QEAA@XZ`
- size: `40`
- prototype: ``
- caller_count: `9`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180032114`
- `0x180032126`
- `0x180032138`
- `0x18003214a`
- `0x180032f6e`
- `0x180032f80`
- `0x180032f92`
- `0x180032fa4`
- `0x1800331d4`

## callees

- `0x18000a2bc`
- `0x180034010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CComPtr<IXMLDOMNodeList>::~CComPtr<IXMLDOMNodeList>(__int64 *a1)
{
  __int64 v1; // rcx
  __int64 result; // rax

  v1 = *a1;
  if ( v1 )
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v1 + 16LL))(v1);
  return result;
}

```

## disassembly

```asm
0x18000a2bc  sub     rsp, 38h
0x18000a2c0  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x18000a2c9  mov     rcx, [rcx]
0x18000a2cc  test    rcx, rcx
0x18000a2cf  jz      short loc_18000A2DE
0x18000a2d1  mov     rax, [rcx]
0x18000a2d4  mov     rax, [rax+10h]
0x18000a2d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a2dd  nop
0x18000a2de  add     rsp, 38h
0x18000a2e2  retn
```
