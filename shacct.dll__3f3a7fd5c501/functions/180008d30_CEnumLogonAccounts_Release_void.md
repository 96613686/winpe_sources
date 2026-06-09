# CEnumLogonAccounts::Release(void)

- ea: `0x180008d30`
- end: `0x180008d81`
- name: `?Release@CEnumLogonAccounts@@UEAAKXZ`
- size: `81`
- prototype: `unsigned int __fastcall(CEnumLogonAccounts *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x180008d30`
- `0x18000c7e0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008d5f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008d5f`

## pseudocode

```c
__int64 __fastcall CEnumLogonAccounts::Release(CEnumLogonAccounts *this)
{
  unsigned __int32 v2; // edi

  v2 = _InterlockedDecrement((volatile signed __int32 *)this + 2);
  if ( !v2 && this )
  {
    *(_QWORD *)this = &CEnumLogonAccounts::`vftable';
    CoTaskMemFree(*((LPVOID *)this + 2));
    _InterlockedDecrement(&g_cRefCount);
    operator delete(this);
  }
  return v2;
}

```

## disassembly

```asm
0x180008d30  mov     [rsp+arg_0], rbx
0x180008d35  push    rdi
0x180008d36  sub     rsp, 20h
0x180008d3a  mov     rbx, rcx
0x180008d3d  mov     edi, 0FFFFFFFFh
0x180008d42  lock xadd [rcx+8], edi
0x180008d47  sub     edi, 1
0x180008d4a  jnz     short loc_180008D74
0x180008d4c  test    rcx, rcx
0x180008d4f  jz      short loc_180008D74
0x180008d51  lea     rax, ??_7CEnumLogonAccounts@@6B@; const CEnumLogonAccounts::`vftable'
0x180008d58  mov     [rcx], rax
0x180008d5b  mov     rcx, [rcx+10h]; pv
0x180008d5f  call    cs:__imp_CoTaskMemFree
0x180008d65  lock dec cs:?g_cRefCount@@3JA; long g_cRefCount
0x180008d6c  mov     rcx, rbx; Block
0x180008d6f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180008d74  mov     rbx, [rsp+28h+arg_0]
0x180008d79  mov     eax, edi
0x180008d7b  add     rsp, 20h
0x180008d7f  pop     rdi
0x180008d80  retn
```
