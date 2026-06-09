# RpcAutoImpersonate::~RpcAutoImpersonate(void)

- ea: `0x18000c1a0`
- end: `0x18000c1b1`
- name: `??1RpcAutoImpersonate@@UEAA@XZ`
- size: `17`
- prototype: `void __fastcall(RpcAutoImpersonate *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000f914`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000c1aa`

## pseudocode

```c
void __fastcall RpcAutoImpersonate::~RpcAutoImpersonate(RpcAutoImpersonate *this)
{
  *(_QWORD *)this = &RpcAutoImpersonate::`vftable';
  RevertToSelf();
}

```

## disassembly

```asm
0x18000c1a0  lea     rax, ??_7RpcAutoImpersonate@@6B@; const RpcAutoImpersonate::`vftable'
0x18000c1a7  mov     [rcx], rax
0x18000c1aa  jmp     cs:__imp_RevertToSelf
```
