# CRegMultyString::CStrRegValue::~CStrRegValue(void)

- ea: `0x180012510`
- end: `0x180012532`
- name: `??1CStrRegValue@CRegMultyString@@QEAA@XZ`
- size: `34`
- prototype: `void __fastcall(LPVOID *this)`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001251c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001251c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001252b`

## pseudocode

```c
void __fastcall CRegMultyString::CStrRegValue::~CStrRegValue(LPVOID *this)
{
  CoTaskMemFree(*this);
  CoTaskMemFree(this[1]);
}

```

## disassembly

```asm
0x180012510  push    rbx
0x180012512  sub     rsp, 20h
0x180012516  mov     rbx, rcx
0x180012519  mov     rcx, [rcx]; pv
0x18001251c  call    cs:__imp_CoTaskMemFree
0x180012522  mov     rcx, [rbx+8]
0x180012526  add     rsp, 20h
0x18001252a  pop     rbx
0x18001252b  jmp     cs:__imp_CoTaskMemFree
```
