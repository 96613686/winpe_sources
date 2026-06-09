# RpcAutoImpersonate::`scalar deleting destructor'(uint)

- ea: `0x18000c2f0`
- end: `0x18000c32b`
- name: `??_GRpcAutoImpersonate@@UEAAPEAXI@Z`
- size: `59`
- prototype: `void *__fastcall(RpcAutoImpersonate *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callees

- `0x18000c2f0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000c317`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000c317`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000c309`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000c309`

## pseudocode

```c
RpcAutoImpersonate *__fastcall RpcAutoImpersonate::`scalar deleting destructor'(RpcAutoImpersonate *this, char a2)
{
  *(_QWORD *)this = &RpcAutoImpersonate::`vftable';
  RevertToSelf();
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x18000c2f0  mov     [rsp+arg_0], rbx
0x18000c2f5  push    rdi
0x18000c2f6  sub     rsp, 20h
0x18000c2fa  lea     rax, ??_7RpcAutoImpersonate@@6B@; const RpcAutoImpersonate::`vftable'
0x18000c301  mov     ebx, edx
0x18000c303  mov     [rcx], rax
0x18000c306  mov     rdi, rcx
0x18000c309  call    cs:__imp_RevertToSelf
0x18000c30f  test    bl, 1
0x18000c312  jz      short loc_18000C31D
0x18000c314  mov     rcx, rdi
0x18000c317  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000c31d  mov     rbx, [rsp+28h+arg_0]
0x18000c322  mov     rax, rdi
0x18000c325  add     rsp, 20h
0x18000c329  pop     rdi
0x18000c32a  retn
```
