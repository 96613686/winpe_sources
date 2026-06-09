# _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>::_AddRef(void)

- ea: `0x180050044`
- end: `0x180050062`
- name: `?_AddRef@?$_com_ptr_t@V?$_com_IIID@UIXMLDOMElement@MSXML2@@$1?_GUID_2933bf86_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@AEAAXXZ`
- size: `30`
- prototype: ``
- caller_count: `18`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180048268`
- `0x180049500`
- `0x18004a0c8`
- `0x18004a3b0`
- `0x18004b6d0`
- `0x18004bfc8`
- `0x18004c16c`
- `0x18004c610`
- `0x18004c8d0`
- `0x18004d4c8`
- `0x18004d900`
- `0x18004dea0`
- `0x18004e1b0`
- `0x18004e430`
- `0x18004e630`
- `0x18004ef90`
- `0x18004f2cc`
- `0x1800534b0`

## callees

- `0x180050044`
- `0x180058010`

## pseudocode

```c
__int64 __fastcall _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>::_AddRef(
        __int64 *a1)
{
  __int64 v1; // rcx
  __int64 result; // rax

  v1 = *a1;
  if ( v1 )
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v1 + 8LL))(v1);
  return result;
}

```

## disassembly

```asm
0x180050044  sub     rsp, 28h
0x180050048  mov     rcx, [rcx]
0x18005004b  test    rcx, rcx
0x18005004e  jz      short loc_18005005D
0x180050050  mov     rax, [rcx]
0x180050053  mov     rax, [rax+8]
0x180050057  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005005c  nop
0x18005005d  add     rsp, 28h
0x180050061  retn
```
