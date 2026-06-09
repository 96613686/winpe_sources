# CspGetNodeMapEntryForURI(CspNodeMapBase const *,IConfigManager2URI *)

- ea: `0x180019d6c`
- end: `0x180019dd4`
- name: `?CspGetNodeMapEntryForURI@@YAPEBUCSP_NODEMAP_ENTRY@@PEBVCspNodeMapBase@@PEAUIConfigManager2URI@@@Z`
- size: `104`
- prototype: `const struct CSP_NODEMAP_ENTRY *__fastcall(const struct CspNodeMapBase *, struct IConfigManager2URI *)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000e610`
- `0x1800196a0`
- `0x1800198d0`

## callees

- `0x180019d6c`
- `0x180019ddc`
- `0x18001b010`

## pseudocode

```c
const struct CSP_NODEMAP_ENTRY *__fastcall CspGetNodeMapEntryForURI(
        const struct CspNodeMapBase *a1,
        struct IConfigManager2URI *a2)
{
  __int64 v4; // rsi
  unsigned int v5; // eax

  if ( a1
    && a2
    && (v4 = (*(__int64 (__fastcall **)(const struct CspNodeMapBase *))(*(_QWORD *)a1 + 8LL))(a1)) != 0
    && (v5 = (*(__int64 (__fastcall **)(const struct CspNodeMapBase *))(*(_QWORD *)a1 + 16LL))(a1), v5 != -1) )
  {
    return (const struct CSP_NODEMAP_ENTRY *)CspGetNodeMapEntryFromNodeMap(v4, v5, a2);
  }
  else
  {
    return 0;
  }
}

```

## disassembly

```asm
0x180019d6c  mov     [rsp+arg_0], rbx
0x180019d71  mov     [rsp+arg_8], rsi
0x180019d76  push    rdi
0x180019d77  sub     rsp, 20h
0x180019d7b  mov     rdi, rdx
0x180019d7e  mov     rbx, rcx
0x180019d81  test    rcx, rcx
0x180019d84  jz      short loc_180019DC2
0x180019d86  test    rdx, rdx
0x180019d89  jz      short loc_180019DC2
0x180019d8b  mov     rax, [rcx]
0x180019d8e  mov     rax, [rax+8]
0x180019d92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019d97  mov     rsi, rax
0x180019d9a  test    rax, rax
0x180019d9d  jz      short loc_180019DC2
0x180019d9f  mov     rcx, [rbx]
0x180019da2  mov     rax, [rcx+10h]
0x180019da6  mov     rcx, rbx
0x180019da9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019dae  cmp     eax, 0FFFFFFFFh
0x180019db1  jz      short loc_180019DC2
0x180019db3  mov     r8, rdi
0x180019db6  mov     edx, eax
0x180019db8  mov     rcx, rsi
0x180019dbb  call    CspGetNodeMapEntryFromNodeMap
0x180019dc0  jmp     short loc_180019DC4
0x180019dc2  xor     eax, eax
0x180019dc4  mov     rbx, [rsp+28h+arg_0]
0x180019dc9  mov     rsi, [rsp+28h+arg_8]
0x180019dce  add     rsp, 20h
0x180019dd2  pop     rdi
0x180019dd3  retn
```
