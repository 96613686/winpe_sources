# ATL::CRegParser::CParseBuffer::~CParseBuffer(void)

- ea: `0x1800158a8`
- end: `0x1800158b3`
- name: `??1CParseBuffer@CRegParser@ATL@@QEAA@XZ`
- size: `11`
- prototype: `void __fastcall(LPVOID *this)`
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002fab4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800158ac`

## pseudocode

```c
void __fastcall ATL::CRegParser::CParseBuffer::~CParseBuffer(LPVOID *this)
{
  CoTaskMemFree(this[1]);
}

```

## disassembly

```asm
0x1800158a8  mov     rcx, [rcx+8]
0x1800158ac  jmp     cs:__imp_CoTaskMemFree
```
