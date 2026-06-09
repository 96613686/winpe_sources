# _com_ptr_t<_com_IIID<MSXML2::IXMLDOMNodeList,&__s_GUID const _GUID_2933bf82_7b36_11d2_b20e_00c04f983e60>>::~_com_ptr_t<_com_IIID<MSXML2::IXMLDOMNodeList,&__s_GUID const _GUID_2933bf82_7b36_11d2_b20e_00c04f983e60>>(void)

- ea: `0x180048c58`
- end: `0x180048c76`
- name: `??1?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNodeList@MSXML2@@$1?_GUID_2933bf82_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEAA@XZ`
- size: `30`
- prototype: ``
- caller_count: `21`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180056a62`
- `0x180056a86`
- `0x180056aaa`
- `0x180056abc`
- `0x180056ace`
- `0x180056ae0`
- `0x180056b28`
- `0x180056b4c`
- `0x180056bb8`
- `0x180056bca`
- `0x180056bdc`
- `0x180056bee`
- `0x180056c36`
- `0x180056c48`
- `0x180056c5a`
- `0x180056ca2`
- `0x180056ceb`
- `0x180056d0f`
- `0x180056e28`
- `0x180056e4c`
- `0x180056e70`

## callees

- `0x180048c58`
- `0x180058010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall _com_ptr_t<_com_IIID<MSXML2::IXMLDOMNodeList,&__s_GUID const _GUID_2933bf82_7b36_11d2_b20e_00c04f983e60>>::~_com_ptr_t<_com_IIID<MSXML2::IXMLDOMNodeList,&__s_GUID const _GUID_2933bf82_7b36_11d2_b20e_00c04f983e60>>(
        __int64 *a1)
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
0x180048c58  sub     rsp, 28h
0x180048c5c  mov     rcx, [rcx]
0x180048c5f  test    rcx, rcx
0x180048c62  jz      short loc_180048C71
0x180048c64  mov     rax, [rcx]
0x180048c67  mov     rax, [rax+10h]
0x180048c6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048c70  nop
0x180048c71  add     rsp, 28h
0x180048c75  retn
```
