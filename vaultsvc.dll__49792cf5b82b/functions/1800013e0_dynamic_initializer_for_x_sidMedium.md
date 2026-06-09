# _dynamic_initializer_for__x_sidMedium__

- ea: `0x1800013e0`
- end: `0x18000141e`
- name: `_dynamic_initializer_for__x_sidMedium__`
- size: `62`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## import_xrefs

- `ntdll!RtlInitializeSid` at `0x1800013fa`
- `ntdll!RtlInitializeSid` at `0x1800013fa`
- `ntdll!RtlSubAuthoritySid` at `0x180001405`
- `ntdll!RtlSubAuthoritySid` at `0x180001405`

## pseudocode

```c
PULONG dynamic_initializer_for__x_sidMedium__()
{
  PULONG result; // rax

  RtlInitializeSid(qword_18005F7F0, &IdentifierAuthority, 1u);
  result = RtlSubAuthoritySid(qword_18005F7F0, 0);
  pSid2 = qword_18005F7F0;
  *result = 0x2000;
  return result;
}

```

## disassembly

```asm
0x1800013e0  push    rbx
0x1800013e2  sub     rsp, 20h
0x1800013e6  lea     rbx, qword_18005F7F0
0x1800013ed  mov     r8b, 1; SubAuthorityCount
0x1800013f0  mov     rcx, rbx; Sid
0x1800013f3  lea     rdx, IdentifierAuthority; IdentifierAuthority
0x1800013fa  call    cs:__imp_RtlInitializeSid
0x180001400  xor     edx, edx; SubAuthority
0x180001402  mov     rcx, rbx; Sid
0x180001405  call    cs:__imp_RtlSubAuthoritySid
0x18000140b  mov     cs:pSid2, rbx
0x180001412  mov     dword ptr [rax], 2000h
0x180001418  add     rsp, 20h
0x18000141c  pop     rbx
0x18000141d  retn
```
