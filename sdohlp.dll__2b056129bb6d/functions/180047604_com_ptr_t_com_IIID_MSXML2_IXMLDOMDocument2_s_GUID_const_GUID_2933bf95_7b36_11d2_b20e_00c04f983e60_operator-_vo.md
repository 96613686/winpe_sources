# _com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(void)

- ea: `0x180047604`
- end: `0x180047620`
- name: `??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMDocument2@MSXML2@@XZ`
- size: `28`
- prototype: ``
- caller_count: `26`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180047628`
- `0x1800477a4`
- `0x180048268`
- `0x180049500`
- `0x18004a0c8`
- `0x18004a3b0`
- `0x18004b6d0`
- `0x18004bdbc`
- `0x18004bfc8`
- `0x18004c16c`
- `0x18004c610`
- `0x18004c8d0`
- `0x18004cef4`
- `0x18004cf60`
- `0x18004cfcc`
- `0x18004d11c`
- `0x18004d4c8`
- `0x18004d900`
- `0x18004dea0`
- `0x18004e1b0`
- `0x18004e430`
- `0x18004e630`
- `0x18004ef90`
- `0x18004f2cc`
- `0x180052d80`
- `0x1800534b0`

## callees

- `0x180041148`
- `0x180047604`

## pseudocode

```c
__int64 __fastcall _com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(
        __int64 *a1)
{
  __int64 result; // rax

  result = *a1;
  if ( !*a1 )
    _com_issue_error(-2147467261);
  return result;
}

```

## disassembly

```asm
0x180047604  sub     rsp, 28h
0x180047608  mov     rax, [rcx]
0x18004760b  test    rax, rax
0x18004760e  jnz     short loc_18004761B
0x180047610  mov     ecx, 80004003h; int
0x180047615  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18004761b  add     rsp, 28h
0x18004761f  retn
```
