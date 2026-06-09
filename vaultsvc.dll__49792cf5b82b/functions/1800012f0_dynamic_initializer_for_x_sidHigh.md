# _dynamic_initializer_for__x_sidHigh__

- ea: `0x1800012f0`
- end: `0x18000132e`
- name: `_dynamic_initializer_for__x_sidHigh__`
- size: `62`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## import_xrefs

- `ntdll!RtlInitializeSid` at `0x18000130a`
- `ntdll!RtlInitializeSid` at `0x18000130a`
- `ntdll!RtlSubAuthoritySid` at `0x180001315`
- `ntdll!RtlSubAuthoritySid` at `0x180001315`

## pseudocode

```c
PULONG dynamic_initializer_for__x_sidHigh__()
{
  PULONG result; // rax

  RtlInitializeSid(qword_18005F7A0, &IdentifierAuthority, 1u);
  result = RtlSubAuthoritySid(qword_18005F7A0, 0);
  qword_18005F730 = qword_18005F7A0;
  *result = 12288;
  return result;
}

```

## disassembly

```asm
0x1800012f0  push    rbx
0x1800012f2  sub     rsp, 20h
0x1800012f6  lea     rbx, qword_18005F7A0
0x1800012fd  mov     r8b, 1; SubAuthorityCount
0x180001300  mov     rcx, rbx; Sid
0x180001303  lea     rdx, IdentifierAuthority; IdentifierAuthority
0x18000130a  call    cs:__imp_RtlInitializeSid
0x180001310  xor     edx, edx; SubAuthority
0x180001312  mov     rcx, rbx; Sid
0x180001315  call    cs:__imp_RtlSubAuthoritySid
0x18000131b  mov     cs:qword_18005F730, rbx
0x180001322  mov     dword ptr [rax], 3000h
0x180001328  add     rsp, 20h
0x18000132c  pop     rbx
0x18000132d  retn
```
