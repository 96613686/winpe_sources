# winrt::com_ptr<IXMLDOMAttribute>::~com_ptr<IXMLDOMAttribute>(void)

- ea: `0x140011304`
- end: `0x140011318`
- name: `??1?$com_ptr@UIXMLDOMAttribute@@@winrt@@QEAA@XZ`
- size: `20`
- prototype: ``
- caller_count: `14`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140031a20`
- `0x140031a40`
- `0x140031ce0`
- `0x140031db0`
- `0x14003250a`
- `0x1400325b4`
- `0x1400325d8`
- `0x1400325ea`
- `0x1400325fc`
- `0x140032644`
- `0x14003268b`
- `0x1400326d3`
- `0x140032b7a`
- `0x140032b8c`

## callees

- `0x140011304`
- `0x140011570`

## pseudocode

```c
__int64 __fastcall winrt::com_ptr<IXMLDOMAttribute>::~com_ptr<IXMLDOMAttribute>(_QWORD *a1)
{
  __int64 result; // rax

  if ( *a1 )
    return winrt::com_ptr<IXMLDOMParseError>::unconditional_release_ref(a1);
  return result;
}

```

## disassembly

```asm
0x140011304  sub     rsp, 28h
0x140011308  cmp     qword ptr [rcx], 0
0x14001130c  jz      short loc_140011313
0x14001130e  call    ?unconditional_release_ref@?$com_ptr@UIXMLDOMParseError@@@winrt@@AEAAXXZ; winrt::com_ptr<IXMLDOMParseError>::unconditional_release_ref(void)
0x140011313  add     rsp, 28h
0x140011317  retn
```
