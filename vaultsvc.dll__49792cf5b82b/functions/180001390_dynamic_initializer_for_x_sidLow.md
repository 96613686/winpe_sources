# _dynamic_initializer_for__x_sidLow__

- ea: `0x180001390`
- end: `0x1800013ce`
- name: `_dynamic_initializer_for__x_sidLow__`
- size: `62`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## import_xrefs

- `ntdll!RtlInitializeSid` at `0x1800013aa`
- `ntdll!RtlInitializeSid` at `0x1800013aa`
- `ntdll!RtlSubAuthoritySid` at `0x1800013b5`
- `ntdll!RtlSubAuthoritySid` at `0x1800013b5`

## pseudocode

```c
PULONG dynamic_initializer_for__x_sidLow__()
{
  PULONG result; // rax

  RtlInitializeSid(qword_18005F840, &IdentifierAuthority, 1u);
  result = RtlSubAuthoritySid(qword_18005F840, 0);
  pSid1 = qword_18005F840;
  *result = 4096;
  return result;
}

```

## disassembly

```asm
0x180001390  push    rbx
0x180001392  sub     rsp, 20h
0x180001396  lea     rbx, qword_18005F840
0x18000139d  mov     r8b, 1; SubAuthorityCount
0x1800013a0  mov     rcx, rbx; Sid
0x1800013a3  lea     rdx, IdentifierAuthority; IdentifierAuthority
0x1800013aa  call    cs:__imp_RtlInitializeSid
0x1800013b0  xor     edx, edx; SubAuthority
0x1800013b2  mov     rcx, rbx; Sid
0x1800013b5  call    cs:__imp_RtlSubAuthoritySid
0x1800013bb  mov     cs:pSid1, rbx
0x1800013c2  mov     dword ptr [rax], 1000h
0x1800013c8  add     rsp, 20h
0x1800013cc  pop     rbx
0x1800013cd  retn
```
