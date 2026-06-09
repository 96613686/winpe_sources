# CRegistryEventRequest::ResetOnChangeHandle(void)

- ea: `0x180008300`
- end: `0x180008364`
- name: `?ResetOnChangeHandle@CRegistryEventRequest@@QEAAHXZ`
- size: `100`
- prototype: `_BOOL8 __fastcall(CRegistryEventRequest *this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800081c0`

## callees

- `0x180017010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x18000834a`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x18000834a`

## pseudocode

```c
_BOOL8 __fastcall CRegistryEventRequest::ResetOnChangeHandle(CRegistryEventRequest *this)
{
  __int64 v1; // rax
  void *v3; // rbx
  int v4; // eax

  v1 = *(_QWORD *)this;
  v3 = (void *)*((_QWORD *)this + 19);
  *((_DWORD *)this + 42) = 0;
  v4 = (*(__int64 (**)(void))(v1 + 24))();
  return RegNotifyChangeKeyValue(*((HKEY *)this + 18), v4 == 2, 7u, v3, 1) == 0;
}

```

## disassembly

```asm
0x180008300  mov     [rsp+arg_0], rbx
0x180008305  push    rdi
0x180008306  sub     rsp, 30h
0x18000830a  mov     rax, [rcx]
0x18000830d  mov     rdi, rcx
0x180008310  mov     rbx, [rcx+98h]
0x180008317  mov     dword ptr [rcx+0A8h], 0
0x180008321  mov     rax, [rax+18h]
0x180008325  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000832a  mov     rcx, [rdi+90h]; hKey
0x180008331  xor     edx, edx
0x180008333  cmp     eax, 2
0x180008336  mov     [rsp+38h+fAsynchronous], 1; fAsynchronous
0x18000833e  mov     r9, rbx; hEvent
0x180008341  mov     r8d, 7; dwNotifyFilter
0x180008347  setz    dl; bWatchSubtree
0x18000834a  call    cs:__imp_RegNotifyChangeKeyValue
0x180008350  mov     rbx, [rsp+38h+arg_0]
0x180008355  xor     ecx, ecx
0x180008357  test    eax, eax
0x180008359  setz    cl
0x18000835c  mov     eax, ecx
0x18000835e  add     rsp, 30h
0x180008362  pop     rdi
0x180008363  retn
```
