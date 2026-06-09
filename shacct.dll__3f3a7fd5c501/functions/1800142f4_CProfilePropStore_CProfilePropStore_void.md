# CProfilePropStore::~CProfilePropStore(void)

- ea: `0x1800142f4`
- end: `0x180014328`
- name: `??1CProfilePropStore@@AEAA@XZ`
- size: `52`
- prototype: `void __fastcall(CProfilePropStore *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x180009bc0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001430b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014315`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001430b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014315`

## pseudocode

```c
void __fastcall CProfilePropStore::~CProfilePropStore(LPVOID *this)
{
  *this = &CProfilePropStore::`vftable';
  CoTaskMemFree(this[2]);
  CoTaskMemFree(this[5]);
  _InterlockedDecrement(&g_cRefCount);
}

```

## disassembly

```asm
0x1800142f4  push    rbx
0x1800142f6  sub     rsp, 20h
0x1800142fa  lea     rax, ??_7CProfilePropStore@@6B@; const CProfilePropStore::`vftable'
0x180014301  mov     rbx, rcx
0x180014304  mov     [rcx], rax
0x180014307  mov     rcx, [rcx+10h]; pv
0x18001430b  call    cs:__imp_CoTaskMemFree
0x180014311  mov     rcx, [rbx+28h]; pv
0x180014315  call    cs:__imp_CoTaskMemFree
0x18001431b  lock dec cs:?g_cRefCount@@3JA; long g_cRefCount
0x180014322  add     rsp, 20h
0x180014326  pop     rbx
0x180014327  retn
```
