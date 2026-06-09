# std::pair<ushort *,IXMLDOMDocument2 *>::pair<ushort *,IXMLDOMDocument2 *>(void)

- ea: `0x1800142cc`
- end: `0x1800142df`
- name: `??0?$pair@PEAGPEAUIXMLDOMDocument2@@@std@@QEAA@XZ`
- size: `19`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x1800176dc`

## pseudocode

```c
_QWORD *__fastcall std::pair<unsigned short *,IXMLDOMDocument2 *>::pair<unsigned short *,IXMLDOMDocument2 *>(
        _QWORD *a1)
{
  _QWORD *result; // rax

  *a1 = 0;
  result = a1;
  a1[1] = 0;
  return result;
}

```

## disassembly

```asm
0x1800142cc  mov     qword ptr [rcx], 0
0x1800142d3  mov     rax, rcx
0x1800142d6  mov     qword ptr [rcx+8], 0
0x1800142de  retn
```
