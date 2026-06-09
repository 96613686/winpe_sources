# CXmlStreamDocument::GetStream(void)

- ea: `0x180008490`
- end: `0x180008495`
- name: `?GetStream@CXmlStreamDocument@@UEAAPEAUIStream@@XZ`
- size: `5`
- prototype: `struct IStream *__fastcall(CXmlStreamDocument *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## pseudocode

```c
struct IStream *__fastcall CXmlStreamDocument::GetStream(CXmlStreamDocument *this)
{
  return (struct IStream *)*((_QWORD *)this + 9);
}

```

## disassembly

```asm
0x180008490  mov     rax, [rcx+48h]
0x180008494  retn
```
