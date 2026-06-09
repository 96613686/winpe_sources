# CLoggedOnAccounts::~CLoggedOnAccounts(void)

- ea: `0x180008c70`
- end: `0x180008ca3`
- name: `??1CLoggedOnAccounts@@AEAA@XZ`
- size: `51`
- prototype: `void __fastcall(CLoggedOnAccounts *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x180013c50`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008c87`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008c87`

## pseudocode

```c
void __fastcall CLoggedOnAccounts::~CLoggedOnAccounts(LPVOID *this)
{
  *this = &CLoggedOnAccounts::`vftable';
  CoTaskMemFree(this[2]);
  this[2] = 0;
  *((_DWORD *)this + 3) = 0;
  _InterlockedDecrement(&g_cRefCount);
}

```

## disassembly

```asm
0x180008c70  push    rbx
0x180008c72  sub     rsp, 20h
0x180008c76  lea     rax, ??_7CLoggedOnAccounts@@6B@; const CLoggedOnAccounts::`vftable'
0x180008c7d  mov     rbx, rcx
0x180008c80  mov     [rcx], rax
0x180008c83  mov     rcx, [rcx+10h]; pv
0x180008c87  call    cs:__imp_CoTaskMemFree
0x180008c8d  xor     eax, eax
0x180008c8f  mov     [rbx+10h], rax
0x180008c93  mov     [rbx+0Ch], eax
0x180008c96  lock dec cs:?g_cRefCount@@3JA; long g_cRefCount
0x180008c9d  add     rsp, 20h
0x180008ca1  pop     rbx
0x180008ca2  retn
```
