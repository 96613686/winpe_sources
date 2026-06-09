# SAXWriter::AddRef(void)

- ea: `0x10041d000`
- end: `0x10041d00d`
- name: `?AddRef@SAXWriter@@UEAAKXZ`
- size: `13`
- prototype: `unsigned int __fastcall(SAXWriter *__hidden this)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x100420280`
- `0x1004202a0`
- `0x1004202d0`
- `0x100420300`
- `0x100420340`

## pseudocode

```c
__int64 __fastcall SAXWriter::AddRef(SAXWriter *this)
{
  return (unsigned int)_InterlockedIncrement((volatile signed __int32 *)this + 12);
}

```

## disassembly

```asm
0x10041d000  mov     eax, 1
0x10041d005  lock xadd [rcx+30h], eax
0x10041d00a  inc     eax
0x10041d00c  retn
```
