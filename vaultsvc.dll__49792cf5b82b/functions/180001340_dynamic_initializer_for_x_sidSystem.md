# _dynamic_initializer_for__x_sidSystem__

- ea: `0x180001340`
- end: `0x18000137e`
- name: `_dynamic_initializer_for__x_sidSystem__`
- size: `62`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## import_xrefs

- `ntdll!RtlInitializeSid` at `0x18000135a`
- `ntdll!RtlInitializeSid` at `0x18000135a`
- `ntdll!RtlSubAuthoritySid` at `0x180001365`
- `ntdll!RtlSubAuthoritySid` at `0x180001365`

## pseudocode

```c
PULONG dynamic_initializer_for__x_sidSystem__()
{
  PULONG result; // rax

  RtlInitializeSid(qword_18005F750, &IdentifierAuthority, 1u);
  result = RtlSubAuthoritySid(qword_18005F750, 0);
  qword_18005F728 = qword_18005F750;
  *result = 0x4000;
  return result;
}

```

## disassembly

```asm
0x180001340  push    rbx
0x180001342  sub     rsp, 20h
0x180001346  lea     rbx, qword_18005F750
0x18000134d  mov     r8b, 1; SubAuthorityCount
0x180001350  mov     rcx, rbx; Sid
0x180001353  lea     rdx, IdentifierAuthority; IdentifierAuthority
0x18000135a  call    cs:__imp_RtlInitializeSid
0x180001360  xor     edx, edx; SubAuthority
0x180001362  mov     rcx, rbx; Sid
0x180001365  call    cs:__imp_RtlSubAuthoritySid
0x18000136b  mov     cs:qword_18005F728, rbx
0x180001372  mov     dword ptr [rax], 4000h
0x180001378  add     rsp, 20h
0x18000137c  pop     rbx
0x18000137d  retn
```
