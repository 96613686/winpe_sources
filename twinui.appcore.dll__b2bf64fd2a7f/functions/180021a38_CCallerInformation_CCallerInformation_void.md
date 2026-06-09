# CCallerInformation::~CCallerInformation(void)

- ea: `0x180021a38`
- end: `0x180021a82`
- name: `??1CCallerInformation@@QEAA@XZ`
- size: `74`
- prototype: `void __fastcall(CCallerInformation *__hidden this)`
- caller_count: `4`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x180021a04`
- `0x18004be58`
- `0x180081d69`
- `0x18008424b`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021a44`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021a4e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021a58`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021a62`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021a6c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021a44`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021a4e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021a58`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021a62`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021a6c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021a7b`

## pseudocode

```c
void __fastcall CCallerInformation::~CCallerInformation(LPVOID *this)
{
  CoTaskMemFree(*this);
  CoTaskMemFree(this[1]);
  CoTaskMemFree(this[2]);
  CoTaskMemFree(this[3]);
  CoTaskMemFree(this[4]);
  CoTaskMemFree(this[5]);
}

```

## disassembly

```asm
0x180021a38  push    rbx
0x180021a3a  sub     rsp, 20h
0x180021a3e  mov     rbx, rcx
0x180021a41  mov     rcx, [rcx]; pv
0x180021a44  call    cs:__imp_CoTaskMemFree
0x180021a4a  mov     rcx, [rbx+8]; pv
0x180021a4e  call    cs:__imp_CoTaskMemFree
0x180021a54  mov     rcx, [rbx+10h]; pv
0x180021a58  call    cs:__imp_CoTaskMemFree
0x180021a5e  mov     rcx, [rbx+18h]; pv
0x180021a62  call    cs:__imp_CoTaskMemFree
0x180021a68  mov     rcx, [rbx+20h]; pv
0x180021a6c  call    cs:__imp_CoTaskMemFree
0x180021a72  mov     rcx, [rbx+28h]
0x180021a76  add     rsp, 20h
0x180021a7a  pop     rbx
0x180021a7b  jmp     cs:__imp_CoTaskMemFree
```
