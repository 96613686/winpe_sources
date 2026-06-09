# ATL::CRegParser::CParseBuffer::~CParseBuffer(void)

- ea: `0x180011fe4`
- end: `0x180011ff8`
- name: `??1CParseBuffer@CRegParser@ATL@@QEAA@XZ`
- size: `20`
- prototype: `void __fastcall(LPVOID *this)`
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001e81e`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011fec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011fec`

## pseudocode

```c
void __fastcall ATL::CRegParser::CParseBuffer::~CParseBuffer(LPVOID *this)
{
  CoTaskMemFree(this[1]);
}

```

## disassembly

```asm
0x180011fe4  sub     rsp, 28h
0x180011fe8  mov     rcx, [rcx+8]; pv
0x180011fec  call    cs:__imp_CoTaskMemFree
0x180011ff2  nop
0x180011ff3  add     rsp, 28h
0x180011ff7  retn
```
