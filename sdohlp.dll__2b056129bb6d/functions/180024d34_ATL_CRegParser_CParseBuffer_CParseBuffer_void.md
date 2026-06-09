# ATL::CRegParser::CParseBuffer::~CParseBuffer(void)

- ea: `0x180024d34`
- end: `0x180024d3f`
- name: `??1CParseBuffer@CRegParser@ATL@@QEAA@XZ`
- size: `11`
- prototype: `void __fastcall(ATL::CRegParser::CParseBuffer *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: `service_task`

## callers

- `0x180055fb6`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180024d38`

## pseudocode

```c
void __fastcall ATL::CRegParser::CParseBuffer::~CParseBuffer(LPVOID *this)
{
  CoTaskMemFree(this[1]);
}

```

## disassembly

```asm
0x180024d34  mov     rcx, [rcx+8]
0x180024d38  jmp     cs:__imp_CoTaskMemFree
```
