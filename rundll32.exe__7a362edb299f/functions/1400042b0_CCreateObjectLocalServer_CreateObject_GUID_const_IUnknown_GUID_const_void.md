# CCreateObjectLocalServer::CreateObject(_GUID const &,IUnknown *,_GUID const &,void * *)

- ea: `0x1400042b0`
- end: `0x140004309`
- name: `?CreateObject@CCreateObjectLocalServer@@UEAAJAEBU_GUID@@PEAUIUnknown@@0PEAPEAX@Z`
- size: `89`
- prototype: `__int64 __fastcall(IUnknown *this, const struct _GUID *, struct IUnknown *, const struct _GUID *, void **ppv)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1400042e7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1400042e7`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHSetThreadRef` at `0x1400042c8`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHSetThreadRef` at `0x1400042f1`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHSetThreadRef` at `0x1400042c8`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHSetThreadRef` at `0x1400042f1`

## pseudocode

```c
__int64 __fastcall CCreateObjectLocalServer::CreateObject(
        IUnknown *this,
        const struct _GUID *a2,
        struct IUnknown *a3,
        const struct _GUID *a4,
        void **ppv)
{
  SHSetThreadRef(this);
  LODWORD(a4) = CoCreateInstance(a2, a3, 1u, a4, ppv);
  SHSetThreadRef(0);
  return (unsigned int)a4;
}

```

## disassembly

```asm
0x1400042b0  mov     [rsp+arg_0], rbx
0x1400042b5  mov     [rsp+arg_8], rsi
0x1400042ba  push    rdi
0x1400042bb  sub     rsp, 30h
0x1400042bf  mov     rbx, r9
0x1400042c2  mov     rdi, r8
0x1400042c5  mov     rsi, rdx
0x1400042c8  call    cs:__imp_SHSetThreadRef
0x1400042ce  mov     rax, [rsp+38h+arg_20]
0x1400042d3  mov     r9, rbx; riid
0x1400042d6  mov     r8d, 1; dwClsContext
0x1400042dc  mov     [rsp+38h+ppv], rax; ppv
0x1400042e1  mov     rdx, rdi; pUnkOuter
0x1400042e4  mov     rcx, rsi; rclsid
0x1400042e7  call    cs:__imp_CoCreateInstance
0x1400042ed  xor     ecx, ecx; punk
0x1400042ef  mov     ebx, eax
0x1400042f1  call    cs:__imp_SHSetThreadRef
0x1400042f7  mov     rsi, [rsp+38h+arg_8]
0x1400042fc  mov     eax, ebx
0x1400042fe  mov     rbx, [rsp+38h+arg_0]
0x140004303  add     rsp, 30h
0x140004307  pop     rdi
0x140004308  retn
```
