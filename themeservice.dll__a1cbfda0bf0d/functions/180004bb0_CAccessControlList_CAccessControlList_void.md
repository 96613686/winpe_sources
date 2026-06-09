# CAccessControlList::~CAccessControlList(void)

- ea: `0x180004bb0`
- end: `0x180004bda`
- name: `??1CAccessControlList@@QEAA@XZ`
- size: `42`
- prototype: `void __fastcall(CAccessControlList *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000eee8`

## callees

- `0x1800034c4`
- `0x180004800`

## pseudocode

```c
void __fastcall CAccessControlList::~CAccessControlList(CAccessControlList *this)
{
  *(_QWORD *)this = &CAccessControlList::`vftable';
  ReleaseMemoryWorker((char *)this + 24);
  CDynamicPointerArrayBase<_ACCESS_ALLOWED_ACE,CTOwnershipPolicy_LocalMem<_ACCESS_ALLOWED_ACE>>::~CDynamicPointerArrayBase<_ACCESS_ALLOWED_ACE,CTOwnershipPolicy_LocalMem<_ACCESS_ALLOWED_ACE>>((int *)this + 2);
}

```

## disassembly

```asm
0x180004bb0  push    rbx
0x180004bb2  sub     rsp, 20h
0x180004bb6  lea     rax, ??_7CAccessControlList@@6B@; const CAccessControlList::`vftable'
0x180004bbd  mov     rbx, rcx
0x180004bc0  mov     [rcx], rax
0x180004bc3  add     rcx, 18h
0x180004bc7  call    ReleaseMemoryWorker
0x180004bcc  lea     rcx, [rbx+8]
0x180004bd0  add     rsp, 20h
0x180004bd4  pop     rbx
0x180004bd5  jmp     ??1?$CDynamicPointerArrayBase@U_ACCESS_ALLOWED_ACE@@V?$CTOwnershipPolicy_LocalMem@U_ACCESS_ALLOWED_ACE@@@@@@IEAA@XZ; CDynamicPointerArrayBase<_ACCESS_ALLOWED_ACE,CTOwnershipPolicy_LocalMem<_ACCESS_ALLOWED_ACE>>::~CDynamicPointerArrayBase<_ACCESS_ALLOWED_ACE,CTOwnershipPolicy_LocalMem<_ACCESS_ALLOWED_ACE>>(void)
```
