# CVssDiffAreaCandidate::~CVssDiffAreaCandidate(void)

- ea: `0x18001f350`
- end: `0x18001f36f`
- name: `??1CVssDiffAreaCandidate@@QEAA@XZ`
- size: `31`
- prototype: `void __fastcall(LPVOID *this)`
- caller_count: `4`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x180046a10`
- `0x180048f97`
- `0x180049028`
- `0x180049205`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f35c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f35c`

## pseudocode

```c
void __fastcall CVssDiffAreaCandidate::~CVssDiffAreaCandidate(LPVOID *this)
{
  CoTaskMemFree(*this);
  *this = 0;
}

```

## disassembly

```asm
0x18001f350  push    rbx
0x18001f352  sub     rsp, 20h
0x18001f356  mov     rbx, rcx
0x18001f359  mov     rcx, [rcx]; pv
0x18001f35c  call    cs:__imp_CoTaskMemFree
0x18001f362  mov     qword ptr [rbx], 0
0x18001f369  add     rsp, 20h
0x18001f36d  pop     rbx
0x18001f36e  retn
```
